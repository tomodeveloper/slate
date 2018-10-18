---
title: API Reference

language_tabs:
  - shell

  

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Selamat datang di API Toko Modern Fastpay. Anda bisa mendapatkan informasi produk yang ada di Toko Modern fastpay.

# SignOn

API Tomo menggunakan Basic Auth dan key untuk akses. Berikut contoh format key:

`curl -H TOMO-API-KEY:key`

<aside class="notice">
Anda harus mengganti `key` dengan key personal anda. Basic Auth menggunakan `username` dan `pin` yang anda dapatkan.
</aside>

# Category
## get Category
> Sample Request:

```shell

curl -X GET -H
"TOMO-API-KEY: 8s4ww0gg8o"
http://devapiproduk.fastpay.co.id/v2/category

```
> Sample Response:

```json

[
  {
  "id_kategori": "2",
  "name": "HANDPHONE & TABLET",
  "parent": [{
    "id_kategori": "6224",
    "name": "Handphone",
    "parent": [{
      "id_kategori": "6369",
      "name": "Smartphone,BB, dan Iphone"
    }, {
      "id_kategori": "6370",
      "name": "Handphone Biasa"
    }, {
      "id_kategori": "8063",
      "name": "Lainnya"
    }]
  }, {
    "id_kategori": "6225",
    "name": "Tablet",
    "parent": []
  }, {
    "id_kategori": "6226",
    "name": "Powerbank",
    "parent": []
  }, {
    "id_kategori": "6227",
    "name": "Accessories",
    "parent": [{
      "id_kategori": "6371",
      "name": "Pelindung layar"
    }, {
      "id_kategori": "6372",
      "name": "Cassing"
    }, {
      "id_kategori": "6373",
      "name": "Kabel data"
    }, {
      "id_kategori": "6374",
      "name": "Charger"
    }, {
      "id_kategori": "6375",
      "name": "Selengkapnya"
    }, {
      "id_kategori": "8084",
      "name": "Lainnya"
    }]
  }]
}
]
```


Berikut adalah endpoint untuk mengambil list kategori Tomo

### HTTP Request

`GET http://devapiproduk.fastpay.co.id/v2/category`

### Parameters
None



# Product NON FMCG
## Search Engine Produk

> Sample Request:

```shell
curl -X GET  
http://35.187.249.107/api_produk_elastic/search_elastic.php?query=kopi

```


Berikut adalah cara untuk search produk. 


### HTTP Request

`GET http://35.187.249.107/api_produk_elastic/search_elastic.php?query=:query`

### URL Parameters

Parameter | |Description
--------- | ----------- |-----------
query | **required** | Kata Kunci Produk


## List Data Produk


> Sample Request:

```json
{
    "query":"",
    "category":"",
    "id_category":"",
    "price_gte":"",
    "price_lte":"",
    "province":"",
    "area":"",
    "index_page":1,
    "per_page":30,
    "date_sort":"desc",
    "price_sort":"desc",
    

}

```



Berikut adalah penjelasan dari value respon yang didapatkan ketika request

Properti | Deskripsi
-------------- | -------------- 
Product_owner | Biller produk yang diserap oleh TOMO. Value yang tersedia `BUKALAPAK` dan `SBF`


### HTTP Request

`POST 35.187.249.107/api_produk_elastic/search_list_product.php`

### Parameters

Parameter |  | Description
--------- | ------- | -----------
query | optional | Keyword yang digunakan untuk pencarian.
kategori | optional | Pencarian berdasarkan kategori menggunakan string.
id_category | optional | Pencarian berdasarkan kategori menggunakan id_kategori.
price_gte | optional | Minimal Harga Produk
price_lte | optional | Maksimal Harga Produk
province | optional | List berdasar `Provinsi` tertentu. menggunakan string
area | optional | List berdasar `Kota` tertentu. menggunakan string
index_page | optional | Paging
per_page | optional | Maksimal produk tampil per-page
date_sort | optional | Listing terbaru atau terlama `asc` atau `desc`



## Produk Detail

> Sample Request:

```shell
curl -X GET -H
"TOMO-API-KEY: 8s4ww0gg8o"
http://devapiproduk.fastpay.co.id/v2/detail_product/9a117t
```

> Sample Response

```json

{
  "status": "ok",
  "product_list": [
    {
      "id_produk": "9a117t",
      "id_kategori_produk": "7749",
      "category": "Jaket Motor & ATV \/ Aksesoris Motor \/ OTOMOTIF | BUKU, GAMES & MUSIK",
      "produk": "Sarung Tangan Batok Rockstar Merah Full Finger",
      "product_owner": "BUKALAPAK",
      "bobot": "100",
      "harga": "29900.00",
      "deskripsi": {
        
      },
      "is_barang_baru": "1",
      "deskripsi_bisnis": "Sarung Tangan Batok<br\/><br\/>- All size<br\/>- Warna hitam<br\/>- Melindungi tangan pada saat berkendara<br\/>- Membuat tangan tetap halus (tidak kapalan)<br\/>- Melindungi dari sinar matahari langsung<br\/>- Barang ready stok.",
      "created": "2017-07-23 14:56:12",
      "qty": "12",
      "updated": "2017-10-09 05:12:09.853208",
      "diskon_prosentase": "0",
      "diskon_flat_nominal": "0",
      "jumlah_dilihat": "0",
      "jumlah_diminati": "0",
      "jumlah_terjual": "0",
      "city_origin_supplier": null,
      "id_member": "SB999",
      "is_deleted": "0",
      "harga_coret": 35200,
      "harga_non_coret": 32442,
      "hpp_core": 27359,
      "service_fee": 2542,
      "diskon": 0,
      "harga_up": 2758,
      "service_fee_persen": "8.50",
      "service_fee_fix": "0.00",
      "up_harga_fix": "0.00",
      "up_harga_persen": "0.00",
      "foto": [
        "https:\/\/s2.bukalapak.com\/img\/7569750931\/large\/Sarung_Tangan_Batok_Rockstar_Merah_Full_Finger.jpg",
        "https:\/\/s2.bukalapak.com\/img\/2569750931\/large\/Sarung_Tangan_Batok_Rockstar_Merah_Full_Finger.jpg",
        "https:\/\/s2.bukalapak.com\/img\/2469750931\/large\/Sarung_Tangan_Batok_Rockstar_Merah_Full_Finger.jpg",
        "https:\/\/s2.bukalapak.com\/img\/7369750931\/large\/Sarung_Tangan_Batok_Rockstar_Merah_Full_Finger.jpg",
        "https:\/\/s2.bukalapak.com\/img\/2769750931\/large\/Sarung_Tangan_Batok_Rockstar_Merah_Full_Finger.jpg"
      ],
      "courier": [
        "Pos",
        "JNE",
        "J&T",
        "TIKI"
      ]
    }
  ]
}
```

Berikut adalah cara untuk mengambil detail dari produk. 


### HTTP Request

`GET http://devapiproduk.fastpay.co.id/v2/detail_product/:id/:id_outlet`

### URL Parameters

Parameter | |Description
--------- | ----------- |-----------
ID | **required** | id produk yang akan dibaca
ID | optional | isi dengan id outlet jika ingin memunculkan komisi


## Shipping Fee Product

> Sample Request per courier:

```shell
curl -X GET -H
"TOMO-API-KEY: 8s4ww0gg8o"
http://devapiproduk.fastpay.co.id/index.php/v2/cek_ongkir_product?
id_produk=7j0ezz&city_destination=250
&to_area=10150&kode_pos=61256&courier=JNE&quantity=1
```

> Sample Response

```shell

{
  "status": "ok",
  "result": [{
    "service": "JNE REG",
    "harga": 180000,
    "eta": "6",
    "insurance_cost": 5523
  }]
}
```

> Sample Request all courier:

```shell
curl -X GET -H
"TOMO-API-KEY: 8s4ww0gg8o"
http://devapiproduk.fastpay.co.id/index.php/v2/cek_ongkir_product?
id_produk=7j0ezz&city_destination=250
&to_area=10150&kode_pos=61256&courier=all&quantity=1
```

> Sample Response

```json

{
  "status": "ok",
  "result": [{
      "courier_name": "jnt",
      "couriers": [{
        "service": "J&T REG",
        "price": 26000,
        "eta": "2-3",
        "insurance_cost": 0
      }]
    },
    {
      "courier_name": "poskilat",
      "couriers": [{
        "service": "Pos Kilat Khusus",
        "price": 16665,
        "eta": "2",
        "insurance_cost": 0
      }]
    },
    {
      "courier_name": "jne",
      "couriers": [{
        "service": "JNE REG",
        "price": 36000,
        "eta": "3-6",
        "insurance_cost": 0
      }]
    },
    {
      "courier_name": "tiki",
      "couriers": [{
          "service": "TIKI Reg",
          "price": 36500,
          "eta": 3,
          "insurance_cost": 0
        },
        {
          "service": "TIKI ONS",
          "price": 29000,
          "eta": 1,
          "insurance_cost": 0
        }
      ]
    }
  ]
}

```

Berikut adalah cara untuk mengambil data ongkos kirim dari produk. 


### HTTP Request

`GET http://devapiproduk.fastpay.co.id/v2/cek_ongkir_product`

### URL Parameters

Parameter | |Description
--------- | ----------- |-----------
id_produk | **required** | id produk
city_destination | **required** | Id kota tujuan pengiriman
to_area  | **required** | Id Kecamatan Pengiriman
kode_pos | **required** | Kode Pos Pengiriman
courier | **required** | nama ekspedisi
quantity | **required** | Jumlah Pembelian

 

Courier List| 
--------- | -----------
pos| 
jne|
tiki|
wahana|
rpx|
sicepat|
ninja|
jnt|
all|

## Propinsi Pengiriman

> Sample Request:

```shell
curl -X GET  
http://devapiproduk.fastpay.co.id/v2/list_propinsi

```


Berikut adalah cara untuk search produk. 


### HTTP Request

`GET http://devapiproduk.fastpay.co.id/v2/list_propinsi`

### URL Parameters
none


## Kota Pengiriman

> Sample Request:

```shell
curl -X GET  
http://devapiproduk.fastpay.co.id/v2/list_kota?id=10

```


Berikut adalah cara untuk search produk. 


### HTTP Request

`GET http://devapiproduk.fastpay.co.id/v2/list_kota?id=:id`

### URL Parameters

Parameter | |Description
--------- | ----------- |-----------
id | **required** | id propinsi yang didapatkan dari [propinsi pengiriman](#propinsi-pengiriman)

## Kecamatan Pengiriman

> Sample Request:

```shell
curl -X GET  
http://devapiproduk.fastpay.co.id/v2/list_kecamatan?id=157

```


Berikut adalah cara untuk search produk. 


### HTTP Request

`GET http://devapiproduk.fastpay.co.id/v2/list_kecamatan?id=:id`

### URL Parameters

Parameter | |Description
--------- | ----------- |-----------
id | **required** | id Kota yang didapatkan dari [kota pengiriman](#kota-pengiriman)


# product FMCG

FMCG di Tomo adalah layanan penjualan produk sehari hari yang pengirimannya dilakukan oleh Supplier FMCG. Saat ini Supplier FMCG Tomo ada di tabel bawah ini

ID Supplier | Keterangan 
-------------- | -------------- 
SB114759 | Vifa Grosir


## Search Engine product

> Sample Request:

```shell
curl -X GET  
http://35.187.249.107/api_produk_elastic/search_elastic.php?query=kopi
&is_direct_expedition=true&id_member=SB114759

```


Berikut adalah cara untuk search produk. 


### HTTP Request

`GET http://35.187.249.107/api_produk_elastic/search_elastic.php?query=:query&is_direct_expedition=:is_direct_expedition&id_member=:id_member`

### URL Parameters

Parameter | |Description
--------- | ----------- |-----------
query | **required** | Kata Kunci Produk
is_direct_expedition | optional | Isi dengan `'true'` jika barang FMCG dan `'false'` jika barang `non fmcg`. Default barang non fmcg
id_member | **required** | Produk oleh supplier tertentu

## List Data Produk


> Sample Request:

```json
{
    "query":"",
    "category":"",
    "id_category":"",
    "price_gte":"",
    "price_lte":"",
    "province":"",
    "area":"",
    "index_page":1,
    "per_page":30,
    "date_sort":"desc",
    "price_sort":"desc",
    "is_direct_expedition":"true",
    "id_member":"SB114759"

}

```



Berikut adalah penjelasan dari value respon yang didapatkan ketika request

Properti | Deskripsi
-------------- | -------------- 
Product_owner | Biller produk yang diserap oleh TOMO. Value yang tersedia `BUKALAPAK` dan `SBF`


### HTTP Request

`POST 35.187.249.107/api_produk_elastic/search_list_product.php`

### Parameters

Parameter |  | Description
--------- | ------- | -----------
query | optional | Keyword yang digunakan untuk pencarian.
kategori | optional | Pencarian berdasarkan kategori menggunakan string.
id_category | optional | Pencarian berdasarkan kategori menggunakan id_kategori.
price_gte | optional | Minimal Harga Produk
price_lte | optional | Maksimal Harga Produk
province | optional | List berdasar `Provinsi` tertentu. menggunakan string
area | optional | List berdasar `Kota` tertentu. menggunakan string
index_page | optional | Paging
per_page | optional | Maksimal produk tampil per-page
date_sort | optional | Listing terbaru atau terlama `asc` atau `desc`
is_direct_expedition | **required** | `'true'` untuk filter barang fmcg
id_member | **required** | id supplier fmcg

## Insert cart
```json
[{
	"id_produk": 31407,
	"qty": 1
}, {
	"id_produk": 31408,
	"qty": 1
}]
```

> Sample Response

```json
{
    "status": "ok",
    "id_cart": "23"
}
```
### HTTP Request

`POST http://devapiproduk.fastpay.co.id/index.php/v2/insert_cart`

### URL Parameters

Parameter | |Description
--------- | ----------- |-----------
id_produk | **required** | id produk fmcg
qty | **required** | jumlah beli produk

## Cart list
> Sample Request:

```shell
curl -X GET 
http://devapiproduk.fastpay.co.id/v2/cart_list?id_cart=23

```

> Sample Response

```json

{
    "status": "ok",
    "supplier_info": {
        "nama_pemilik": "Internal Tester",
        "jumlah_barang": "2",
        "id_supplier": "BS0004",
        "logo_supplier": "https://static.scash.bz/supplier_sbf/image_supplier/BS0004_07052018_81484c89213141c8bc269498c02af177.jpeg",
        "catatan_pengiriman": "<p>dfdsfsdf</p>",
        "minimum_belanja": "100000"
    },
    "result": {
        "id_cart": "23",
        "list_produk": [
            {
                "id_produk": "31407",
                "id_member": "BS0004",
                "produk": "Abon sapi",
                "qty": "1",
                "harga": 40000,
                "diskon": 0,
                "url_image": "https://static.scash.bz/tomo/image_produk/image_produk/BS0004_02082018_caddfb48f5fb0f8bcf8e428805296396.compressed.jpeg"
            },
            {
                "id_produk": "31408",
                "id_member": "BS0004",
                "produk": "kornet sapi",
                "qty": "1",
                "harga": 25000,
                "diskon": 0,
                "url_image": "https://static.scash.bz/tomo/image_produk/image_produk/BS0004_02082018_6a738e2c09acbe02d6a2202af12f01be.compressed.jpeg"
            }
        ]
    }
}

```

API untuk mengambil cart list yang dimasukkan dari API [insert cart](#insert-cart)

### HTTP Request

`GET http://devapiproduk.fastpay.co.id/v2/cart_list?id_cart=:id_cart`

### Parameters

Parameter |  | Description
--------- | ------- | -----------
id_cart |  **required** | ID yang didapatkan dari API [insert cart](#insert-cart).

## Propinsi Pengiriman
> Sample Request:

```shell
curl -X GET 
http://devapiproduk.fastpay.co.id/v2/list_propinsi_fmcg?id_supplier=SB114759

```

> Sample Response

```json
{
	"status": "ok",
	"result": [{
		"id_propinsi": "28",
		"nama_propinsi": "Jawa Timur"
	}]
}
```

Api ini untuk mengambil propinsi mana yang disupport pengiriman oleh supplier FMCG

### HTTP Request

`GET http://devapiproduk.fastpay.co.id/v2/list_propinsi_fmcg?id_supplier=:id_supplier`

### Parameters

Parameter |  | Description
--------- | ------- | -----------
id_supplier |  **required** | Id supplier FMCG.



## Kota Pengiriman
> Sample Request:

```shell
curl -X GET 
http://devapiproduk.fastpay.co.id/v2/list_kota_fmcg?id_supplier=SB114759&id_propinsi=28

```

> Sample Response

```json
{
	"status": "ok",
	"result": [{
		"id_kota": "264",
		"nama_kota": "Kota Surabaya"
	}]
}
```

Api ini untuk mengambil kota mana yang disupport pengiriman oleh supplier FMCG

### HTTP Request

`GET http://devapiproduk.fastpay.co.id/v2/list_kota_fmcg?id_supplier=:id_supplier&id_propinsi=:id_propinsi`

### Parameters

Parameter |  | Description
--------- | ------- | -----------
id_supplier |  **required** | Id supplier FMCG.
id_propinsi |  **required** | id_propinsi didapatkan dari [list propinsi](#propinsi-pengiriman-2)

## Kecamatan Pengiriman
> Sample Request:

```shell
curl -X GET 
http://devapiproduk.fastpay.co.id/v2/list_kecamatan_fmcg?id_supplier=SB114759&id_kota=264

```

> Sample Response

```json
{
	"status": "ok",
	"result": [{
		"id_kecamatan": "3893",
		"nama_kecamatan": "GAYUNGAN"
	}]
}
```

Api ini untuk mengambil kecamatan mana yang disupport pengiriman oleh supplier FMCG

### HTTP Request

`GET http://devapiproduk.fastpay.co.id/v2/list_kecamatan_fmcg?id_supplier=:id_supplier&id_kota=:id_kota`

### Parameters

Parameter |  | Description
--------- | ------- | -----------
id_supplier |  **required** | Id supplier FMCG.
id_kota |  **required** | id_propinsi didapatkan dari [list kota](#kota-pengiriman-2)


## kodepos Pengiriman
> Sample Request:

```shell
curl -X GET 
http://devapiproduk.fastpay.co.id/v2/list_kodepos?id=264

```

> Sample Response

```json
{
	"status": "ok",
	"result": [{
		"id_kecamatan": "3893",
		"nama_kecamatan": "GAYUNGAN"
	}]
}
```

Api ini untuk mengambil list kodepos dari kota tertentu

### HTTP Request

`GET http://devapiproduk.fastpay.co.id/v2/list_kodepos?id:id`

### Parameters

Parameter |  | Description
--------- | ------- | -----------
id |  **required** | Id kota.

# Voucher
## voucher non fmcg
> Sample Request:

```shell
curl -X GET 
http://devapiproduk.fastpay.co.id/v2/cek_voucher?kode_voucher=GR64645&no_hp_pembeli=082244409356&id_produk=afg07j&id_outlet=FA92804&qty=1&paket_ekspedisi=JNE%20REG&ongkir=120000

```

> Sample Response

```json

{
  "status": "ok",
  "result": {
    "nominal_voucher": "1000",
    "rule_unique_nomor_hp": "t",
    "rule_potong_ongkir": "t",
    "resp_type": "0",
    "key_voucher": "ZM94yq8IfC20171013142444"
  }
}

```


Berikut adalah penjelasan dari value respon yang didapatkan ketika request

Properti | Deskripsi
-------------- | -------------- 
nominal_voucher | Nominal voucher yang didapatkan
rule_unique_nomor_hp | Voucher yang hanya bisa digunakan satu kali dalam satu no hp. value `t` dan `f`
rule_potong_ongkir | Voucher untuk free ongkir. value `t` dan `f`
key_voucher | key voucher untuk inputan booking

### HTTP Request

`GET http://devapiproduk.fastpay.co.id/v2/cek_voucher`

### Parameters

Parameter |  | Description
--------- | ------- | -----------
kode_voucher |  **required** | Kode Voucher tomo.
id_produk |  **required** | id produk .
id_outlet |  **required** | Id outlet login tomo
qty |  **required** | jumlah beli
paket_ekspedisi |  **required** | jenis paket ekspedisi
ongkir |  **required** | harga ongkos kirim jenis paket ekspedisi 

## voucher fmcg
```json
{
  "kode_voucher": "FA544",
  "no_hp_pembeli": "082244409356",
  "id_outlet": "FA56239",
  "list_produk": [
    {
      "id_produk": "31407",
      "qty": "1"
    },
    {
      "id_produk": "31408",
      "qty": "1"
    }
  ]
}
```

> Sample Response

```json

{
    "status": "ok",
    "result": {
        "nominal_voucher_didapat": 10000,
        "list_key_voucher": [
            {
                "id_produk": "31407",
                "total_harga": 40000,
                "voucher_didapat": "10000",
                "key_voucher": "LR51xIq8f120180802105557"
            }
        ]
    }
}
```
### HTTP Request

`POST http://devapiproduk.fastpay.co.id/index.php/v2/cek_voucher_fmcg`

### URL Parameters

Parameter | |Description
--------- | ----------- |-----------
kode_voucher | **required** | Kode Voucher

# Get nearest loket

> Sample Request:

```shell
curl -X GET -H
"TOMO-API-KEY: 8s4ww0gg8o"
http://devapiproduk.fastpay.co.id/v2/nearest_loket?latitude=-7.3601523&longitude=112.7432411&%20total_belanja=1000

```

> Sample Response

```json

{
  "status": "ok",
  "result": [{
    "id_outlet": "BS0004",
    "latitude": "-7.3601492",
    "longitude": "112.7432416",
    "jarak_meter": "0",
    "nama_pemilik": "Internal Tester",
    "alamat_pemilik": "SIDOARJO",
    "notelp_pemilik": "08563396898",
    "notelp_outlet": "081310095830",
    "nomor_whatsapp_outlet": "08224"
  }, {
    "id_outlet": "FA32481",
    "latitude": "-7.360148",
    "longitude": "112.7432596",
    "jarak_meter": "2",
    "nama_pemilik": "OPERATIONAL MARKETING SBF",
    "alamat_pemilik": "Jl DELTA RAYA UTARA KAV 49 50 DELTASARI BARU WARU  SDA  081234228787",
    "notelp_pemilik": "082139972979",
    "notelp_outlet": "03131034354",
    "nomor_whatsapp_outlet": "083849262697"
  }, {
    "id_outlet": "FA47880",
    "latitude": "-7.3601676",
    "longitude": "112.7432598",
    "jarak_meter": "3",
    "nama_pemilik": "DANTE",
    "alamat_pemilik": "BOULEVARD OF BROKEN DREAM",
    "notelp_pemilik": "081235449898",
    "notelp_outlet": "085720416911",
    "nomor_whatsapp_outlet": "085731921365"
  }, {
    "id_outlet": "FA9919",
    "latitude": "-7.3601545",
    "longitude": "112.7432887",
    "jarak_meter": "5",
    "nama_pemilik": "Fitra Alfiananto",
    "alamat_pemilik": "Jalan Made Karyo 31",
    "notelp_pemilik": "085648889293",
    "notelp_outlet": "085648889293",
    "nomor_whatsapp_outlet": "085648889293"
  }, {
    "id_outlet": "FA73863",
    "latitude": "-7.3601062",
    "longitude": "112.7432261",
    "jarak_meter": "5",
    "nama_pemilik": "Zunita Rachmanniar",
    "alamat_pemilik": "Sidokare Asri SS - 11 Sidoarjo",
    "notelp_pemilik": "082218706946",
    "notelp_outlet": "0318532580",
    "nomor_whatsapp_outlet": "082218706946"
  }]
}

```


Berikut adalah penjelasan dari value respon yang didapatkan ketika request

Properti | Deskripsi
-------------- | -------------- 
id_outlet | Id Outlet terdekat
latitude | Nilai latitude lokasi outlet
longitude | Nilai longitude lokasi outlet
jarak_meter | jarak loket dari lokasi request dalam meter
nama_pemilik | Nama pemilik loket
alamat_pemilik | Alamat loket
notelp_pemilik | No telp pemilik
notelp_outlet | No telp loket
nomor_whatsapp_outlet | No whatsapp loket

### HTTP Request

`GET http://devapiproduk.fastpay.co.id/v2/nearest_loket`

### Parameters

Parameter |  | Description
--------- | ------- | -----------
latitude |  **required** | Nilai latitude pembeli.
longitude |  **required** | Nilai longitude pembeli.
total_belanja |  **required** | Total belanja

# Payment Process NON FMCG

## Booking

> Sample Request:

```json
{
  "type": "DATA",
  "data": {
    "product_id": "hgwr5",
    "product_qty": "3",
    "product_variant_id": "",
    "customer_name": "AGUNG",
    "customer_address": "",
    "customer_area_code": "232",
    "customer_to_area": "6204",
    "customer_phone": "082244409356",
    "customer_email": "",
    "customer_postcode": "61177",
    "ekspedition_id": "0",
    "ekspedition_paket_code": "J&T",
    "ekspedition_paket_name": "J&T REG",
    "ekspedition_estimate_day": "2-3",
    "ekspedition_price": 72000,
    "insurance_cost": 6375,
    "catatan": "",
    "key_voucher": ""
  },
  "version": "1.0",
  "mode": "development"
}
```

> Sample Response

```json

{
  "status": "00",
  "description": "SUCCESSFUL",
  "type": "DATA",
  "transaction_datetime": "20170814115221",
  "outlet_id": "FA92804",
  "pin": "----",
  "version": "1.0",
  "mode": "development",
  "data": {
    "product_id": "hgwr5",
    "product_qty": "3",
    "product_variant_id": "",
    "customer_name": "AGUNG",
    "customer_address": "",
    "customer_area_code": "232",
    "customer_to_area": "6204",
    "customer_phone": "082244409356",
    "customer_email": "",
    "customer_postcode": "61177",
    "ekspedition_id": "0",
    "ekspedition_paket_code": "J&T",
    "ekspedition_paket_name": "J&T REG",
    "ekspedition_estimate_day": "2-3",
    "ekspedition_price": 72000,
    "insurance_cost": 6375,
    "catatan": "",
    "key_voucher": ""
  },
  "result": {
    "booking_date": "20170814115221",
    "booking_payment_code": "3567"
  }
}
```

### HTTP Request

`POST http://devapiproduk.fastpay.co.id/index.php/transaksi`


<aside class="notice">
Untuk booking menggunakan basic auth dan header `TOMO-API-KEY`. Basic Auth menggunakan `username` dan `pin` yang anda dapatkan. Untuk mendapatkan `TOMO-API-KEY`, hubungi Tim Tomo.
</aside>

### URL Parameters

Parameter | |Description
--------- | ----------- |-----------
product_id | **required** | Id Produk
product_qty | **required** | Jumlah Produk yang dibeli
product_variant_id | optional | id varian produk
customer_name  | **required**  |  Nama pembeli
customer_address | optional | alamat Pembeli
customer_area_code | **required** | kode kota pembeli
customer_to_area   | **required**  | kode kecamatan pembeli
customer_phone | **required** | no hp pembeli
customer_email | **required** | email pembeli
customer_postcode | **required** | kode pos
ekspedition_paket_code | **required** | nama ekspedisi
ekspedition_paket_name | **required** | nama service ekspedisi
ekspedition_price | **required** | harga pengiriman
insurance_cost  |  **required** | Harga asuransi pengiriman (Bukalapak)
catatan  |  optional  | Catatan pengiriman
key_voucher  | optional  |  Key voucher yang didapatkan saat cek voucher


## Inquiry

> Sample Request:

```json
{
    "type":"INQ",
    "data":{
        "booking_payment_code":"2082"
  },
    "version":"1.0",
    "mode":"development"
}
```

> Sample Response

```json

{
   "status":"00",
    "description":"SUCCESSFUL",
    "type":"INQ",
    "transaction_datetime":"20170707145836",
    "outlet_id":"BS0004",
    "pin":"----",
    "version":"1.0",
    "mode":"development",
    "data":{
        "booking_payment_code":"2082"
    },
    "result":{
        "booking_payment_code":"2082",
        "product_id":"433452",
        "reff_id":"760148636"
    }
}
```
### HTTP Request

`POST http://devapiproduk.fastpay.co.id/index.php/transaksi`

### URL Parameters

Parameter | |Description
--------- | ----------- |-----------
booking_payment_code | **required** | kode booking


## Payment

> Sample Request:

```json
{
    "type":"PAY",
    "data":{
        "booking_payment_code":"2082",
        "reff_id":"760148636"
  },
    "version":"1.0",
    "mode":"development"
}
```

> Sample Response

```json

{
    "status":"00",
    "description":"SUCCESSFUL",
    "type":"PAY",
    "transaction_datetime":"20170710101603",
    "outlet_id":"BS0004",
    "pin":"----",
    "version":"1.0",
    "mode":"development",
    "data":{
        "booking_payment_code":"2082",
        "reff_id":"760148636"
    },
    "result":{
        "booking_payment_code":"2082",
        "product_id":"433452",
        "reff_id":"760149784"
    }
}
```
### HTTP Request

`POST http://devapiproduk.fastpay.co.id/index.php/transaksi`

### URL Parameters

Parameter | |Description
--------- | ----------- |-----------
booking_payment_code | **required** | kode booking
reff_id | **required** | reff_id yang didapat ketika inquiry

# Payment Process FMCG

## Booking

> Sample Request:

```json
{
	"type": "DATA",
	"data": {
		"id_outlet": "BS0004",
		"customer_name": "robby adnan fanani",
		"customer_address": "tanggulangin",
		"customer_phone": "082244409356",
		"customer_email": "robby.adnan@corp.bm.co.id",
		"catatan": "",
		"via": "TOMOFASTPAY",
		"list_product": [{
				"product_id": "31407",
				"product_qty": "1",
        "key_voucher": "0b1gjnCDF320181017113052"

			},
			{
				"product_id": "31408",
				"product_qty": "1",
        "key_voucher": "0b1gjnCDF320181017113052"
			}
		]
	},
	"version": "1.0",
	"mode": "development"
}
```

> Sample Response

```json

{
	"status": "00",
	"description": "SUCCESSFUL",
	"type": "DATA",
	"outlet_id": "BS0004",
	"pin": "----",
	"version": "1.0",
	"mode": "development",
	"data": {
		"id_outlet": "BS0004",
		"id_outlet_afiliasi": "",
		"customer_name": "robby adnan fanani",
		"customer_address": "tanggulangin",
		"customer_phone": "082244409356",
		"customer_email": "robby.adnan@corp.bm.co.id",
		"customer_district": "61272",
		"insurance_cost": 0,
		"catatan": "",
		"via": "TOMOFASTPAY",
		"list_product": [{
			"product_id": "31407",
			"product_qty": "1"
		}, {
			"product_id": "31408",
			"product_qty": "1"
		}]
	},
	"result": {
		"id_order_fmcg": "69",
		"result_book": [{
			"status": "00",
			"description": "SUCCESSFUL",
			"transaction_datetime": "20181017163733",
			"result": {
				"booking_date": "20181017163733",
				"booking_payment_code": "30315",
				"id_produk": "31407"
			}
		}, {
			"status": "00",
			"description": "SUCCESSFUL",
			"transaction_datetime": "20181017163733",
			"result": {
				"booking_date": "20181017163733",
				"booking_payment_code": "30316",
				"id_produk": "31408"
			}
		}]
	}
}
```

### HTTP Request

`POST http://devapiproduk.fastpay.co.id/index.php/transaksi/fmcg`


<aside class="notice">
Untuk booking menggunakan basic auth dan header `TOMO-API-KEY`. Basic Auth menggunakan `username` dan `pin` yang anda dapatkan. Untuk mendapatkan `TOMO-API-KEY`, hubungi Tim Tomo.
</aside>

### URL Parameters

Parameter | |Description
--------- | ----------- |-----------
id_outlet | **required** | Id Outlet yang melakukan transaksi
customer_name  | **required**  |  Nama pembeli
customer_address | optional | alamat Pembeli
customer_phone | **required** | no hp pembeli
customer_email | **required** | email pembeli
catatan  |  optional  | Catatan pengiriman
product_id | **required** | Id Produk
product_qty | **required** | Jumlah Produk yang dibeli
key_voucher  | optional  |  Key voucher yang didapatkan saat cek voucher


# See Transaction
## Transaction Status
> Sample Request:

```shell

curl -X GET -H
"TOMO-API-KEY: 8s4ww0gg8o"
http://devapiproduk.fastpay.co.id/v2/get_transaction_status?id_transaksi=1112691550&kode_pembayaran=27971

```
> Sample Response:

```json

{
  "status": "error",
  "result": {
    "step": "4",
    "keterangan": "Pesanan telah sampai tujuan",
    "detail_pembayaran": {
      "payment_code": "27971",
      "kode_pembayaran": "1112691550",
      "id_produk": "94vcla",
      "produk": "U9 Smartwatch - Smartwatch DZ09 - Jam Tangan Pintar Support SIM card bisa nelp sms browsing",
      "harga_jual_produk": "146250",
      "jumlah_beli": "1",
      "ongkos_kirim": "57000",
      "kode_voucher": null,
      "nominal_voucher": "0",
      "diskon": null,
      "biaya_asuransi": "0",
      "total_belanja": "203250",
      "id_outlet": "FA56024"
    },
    "detail_ekspedisi": {
      "ekspedisi": "jne",
      "paket_name": "JNE REG",
      "est_day": null,
      "ongkos_kirim": "57000",
      "no_resi": "011330124767718"
    },
    "detail_pemesan": {
      "nama": "Arjuni",
      "kecamatan": "LAUNG TUHUP",
      "kota": "Kabupaten Murung Raya",
      "propinsi": "Kalimantan Tengah",
      "kodepos": "73991",
      "alamat": "Jl veteran rt 9 no 94",
      "telepon": "085251182633",
      "email": "Arjunizaky@gmail.com ",
      "catatan": null
    }
  }
}

```

Berikut adalah endpoint untuk mengambil list kategori Tomo

### HTTP Request

`GET http://devapiproduk.fastpay.co.id/v2/get_transaction_status?id_transaksi=:id_transaksi&kode_pembayaran=:kode_pembayaran`

### Parameters
Parameter | |Description
--------- | ----------- |-----------
id_transaksi | **required** | id_transaksi di dapat di [Payment](#payment) di bagian reff_id pada field result.
kode_pembayaran | **required** | Kode pembayaran adalah booking payment code.

### Step list
Step | Description
--------- | ----------- |-----------
1  | Menunggu Pesanan diterima Supplier.
2  | Pesanan diterima supplier dan menunggu dikirim oleh supplier.
3  | Pesanan telah dikirim.
4  | Pesanan telah sampai tujuan.
-1  | Pesanan Dibatalkan Supplier.

## Set received status
> Sample Request:

```shell

curl -X POST 
-F "id_transaksi=1112691550" -F "kode_pembayaran=2522797198" -F "confirm_received_by=user" 
http://devapiproduk.fastpay.co.id/v2/set_received_transaction

```
> Sample Response:

```json

{
    "status": "ok",
    "result": "Pesanan anda berhasil di konfirmasi sampai pada tujuan"
}

```


Berikut adalah endpoint untuk mengambil list kategori Tomo

### HTTP Request

`POST http://devapiproduk.fastpay.co.id/v2/get_transaction_status?id_transaksi=:id_transaksi&kode_pembayaran=:kode_pembayaran`

### Parameters
Parameter | |Description
--------- | ----------- |-----------
id_transaksi | **required** | id_transaksi di dapat di [Payment](#payment) di bagian reff_id pada field result.
kode_pembayaran | **required** | Kode pembayaran adalah booking payment code.

## Tracking Resi
> Sample Request:

```shell

curl -X GET -H
http://dev2apiproduk.fastpay.co.id/index.php/v2/tracking_resi?reff_id=1113870141

```
> Sample Response:

```json
{
  "status": "00",
  "keterangan": "sukses",
  "result": {
    "tujuan_pengiriman": "IDN",
    "detail": [
      {
        "waktu": "2018-09-11 18:30:00",
        "posisi": "Indonesia",
        "pesan": "SHIPMENT RECEIVED BY JNE COUNTER OFFICER AT [YOGYAKARTA]",
        "status": "InTransit"
      },
      {
        "waktu": "2018-09-11 20:30:00",
        "posisi": "Indonesia",
        "pesan": "SHIPMENT PICKED UP BY JNE COURIER [YOGYAKARTA]",
        "status": "InTransit"
      },
      {
        "waktu": "2018-09-11 21:48:00",
        "posisi": "Indonesia",
        "pesan": "RECEIVED AT SORTING CENTER [YOGYAKARTA]",
        "status": "InTransit"
      },
      {
        "waktu": "2018-09-11 23:28:00",
        "posisi": "Indonesia",
        "pesan": "PROCESSED AT SORTING CENTER [YOGYAKARTA]",
        "status": "InTransit"
      },
      {
        "waktu": "2018-09-12 15:29:00",
        "posisi": "Indonesia",
        "pesan": "DEPARTED FROM TRANSIT [GATEWAY JAKARTA]",
        "status": "InTransit"
      },
      {
        "waktu": "2018-09-12 15:54:00",
        "posisi": "Indonesia",
        "pesan": "RECEIVED AT WAREHOUSE [TANGERANG]",
        "status": "InTransit"
      },
      {
        "waktu": "2018-09-12 16:00:00",
        "posisi": "Indonesia",
        "pesan": "SHIPMENT FORWARDED TO DESTINATION [TANGERANG, HUB GAPLEK]",
        "status": "InTransit"
      },
      {
        "waktu": "2018-09-13 05:00:00",
        "posisi": "Indonesia",
        "pesan": "WITH DELIVERY COURIER [TANGERANG]",
        "status": "InTransit"
      },
      {
        "waktu": "2018-09-13 11:44:00",
        "posisi": "Indonesia",
        "pesan": "DELIVERED TO [ PIPIH | 13-09-2018 11:44 ]",
        "status": "Delivered"
      }
    ],
    "nama_penerima": "PIPIH FEBRI YANTI",
    "tipe_pengiriman": "REG15",
    "no_resi_pengiriman": "140160034976718",
    "status": "received",
    "nama_pengirim": null,
    "tanggal_pengiriman": "2018-09-20T02:49:46+00:00",
    "asal_pengiriman": null,
    "tanggal_diterima_pembeli": "2018-09-20 02:49:46",
    "courier": "JNE"
  }
}

```


Berikut adalah endpoint untuk mengambil list kategori Tomo

### HTTP Request

`GET http://dev2apiproduk.fastpay.co.id/index.php/v2/tracking_resi?reff_id=:reff_id`

### Parameters
Parameter | |Description
--------- | ----------- |-----------
reff_id | **required** | reff_id di dapat di [Payment](#payment) di bagian reff_id pada field result.

