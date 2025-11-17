# Ulangan Tengah Semester Sistem Terdistribus dan terdesentralisasi
 
# NIM : 245410055
# Nama : Muhammad Zaenal Abidin


## Jawaban Soal

# 1. Jelaskan teorema CAP dan BASE dan keterkaitan keduanya. Jelaskan menggunakan contoh yang pernah anda gunakan. 

Teorema CAP

CAP - Consistency: Setiap operasi baca mengembalikan penulisan terbaru, memastikan
semua klien memiliki tampilan data yang sama.
Availability: Setiap permintaan menerima respons,
meskipun bukan data terbaru. Partition Tolerance:
Sistem tetap beroperasi dan berfungsi meskipun
komunikasi antar node terputus atau terfragmentasi.

### cap

1. Tidak mungkin mendapat Consistency + Availability +Partition Tolerance sekaligus. 
2.   Sistem harus memilih trade-off Teorema CAP benar karena dalam partisi jaringan,sistem terdistribusi harus memilih antara (Consistency/Avaibility)

Harus memilih salah satu untuk perngorbanan

Contoh CAP: Sistem Stok Barang di Toko Online
  

2. BASE

BASE adalah pendekatan dari sistem NoSQL modern untuk mengatasi keterbatasan CAP.
BASE adalah kebalikan dari ACID (strong consistency).
BASE terdiri dari:

### base

1. Soft State Data di node yang berbeda bisa sementara tidak sinkron.
2. Basically Available Sistem dioptimalkan agar selalu available.
3. Soft State Data di node yang berbeda bisa sementara tidak sinkron.
4. Eventual Consistency Data akan konsisten pada akhirnya, asalkan tidak ada update baru.

BASE cocok untuk sistem berskala besar yang membutuhkan performa tinggi dan tetap bekerja walau terjadi network partition.

Contoh BASE: Sistem Stok Toko Online

3. Keterkaitan CAP dan BASE
Konsep	Fokus	Hubungan
CAP	Batasan teoretis sistem terdistribusi	Menjelaskan kenapa kita tidak bisa mendapatkan semuanya (CA, AP, CP)
## Tables

| Cap  | Base |
| ------------- |:-------------:|
| CAP	Batasan teoretis sistem terdistribusi	Menjelaskan kenapa kita tidak bsa mendapatkan semuanya (CA, AP, CP)      | BASE	Pendekatan praktis	Menyediakan solusi untuk sistem yang memilih Availability + Partition Tolerance (AP)    |

Relasi melalui contoh yang sama:
CAP	Keputusan	BASE yang cocok
Pilih AP (Availability + Partition Tolerance)	Sistem tetap menerima pesanan meskipun stok belum sinkron	Gunakan Eventual Consistency agar data sinkron nanti
Tinggalkan Consistency kuat	Data bisa tidak konsisten.

# 2. Jelaskan keterkaitan antara GraphQL dengan komunikasi antar proses pada sistem terdistribusi. Buat diagramnya.

GraphQL sebagai Abstraksi Komunikasi

GraphQL pada dasarnya adalah bahasa kueri untuk API Anda, dan runtime sisi server untuk memenuhi kueri tersebut dengan data yang Anda definisikan. Dalam sistem terdistribusi, ini berarti GraphQL dapat bertindak sebagai lapisan abstraksi yang menyederhanakan cara klien berinteraksi dengan berbagai layanan mikro atau komponen terdistribusi.

## Berikut adalah beberapa keterkaitannya:

| Left columns  | 
| ------------- |
| Orkestrasi Data dari Berbagai Sumber: Dalam sistem terdistribusi, data yang dibutuhkan oleh klien seringkali tersebar di berbagai layanan atau database yang berbeda.      | 
| Mengurangi Overhead Jaringan (Over-fetching/Under-fetching): Salah satu masalah umum dalam sistem terdistribusi dengan API REST adalah over-fetching (menerima lebih banyak data dari yang dibutuhkan) atau under-fetching (membutuhkan beberapa permintaan untuk mendapatkan semua data yang dibutuhkan).       | 
| Gateway API: GraphQL sering digunakan sebagai lapisan gateway API di depan serangkaian layanan mikro. Gateway ini menerima permintaan GraphQL dari klien, kemudian mengurai kueri tersebut dan mendelegasikannya ke layanan mikro yang relevan.     | 

 ## Images

Contoh Diagram. ![Diagram](image.png) 

