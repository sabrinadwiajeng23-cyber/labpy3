# labpy3

Latihan 1 - Bilangan Acak
📝 Deskripsi Program
Program ini menampilkan n bilangan acak yang nilainya lebih kecil dari 0.5. Nilai n ditentukan oleh user saat runtime.
🔄 Alur Algoritma

Import Library

Import fungsi random dari module random


Input dari User

Program meminta user memasukkan nilai N
Nilai N disimpan dalam variabel n


Inisialisasi Variabel

Membuat variabel count dengan nilai awal 0
Variabel ini digunakan untuk menghitung jumlah bilangan yang sudah ditampilkan


Perulangan While

Selama count < n, lakukan:

Generate bilangan acak menggunakan random()
Cek apakah bilangan tersebut < 0.5
Jika ya:

Tambah nilai count sebesar 1
Tampilkan bilangan dengan format: data ke: {count} => {angka}


Jika tidak, ulangi generate bilangan baru




Output Akhir

Tampilkan pesan "Selesai"



💻 Kode Program
pythonfrom random import random

# Meminta input n dari user
n = int(input("Masukkan nilai N: "))

# Menampilkan n bilangan acak yang lebih kecil dari 0.5
count = 0

while count < n:
    angka = random()
    if angka < 0.5:
        count += 1
        Contoh Output:
Masukkan nilai N: 5
data ke: 1 => 0.172949220435756
data ke: 2 => 0.08717360127477924
data ke: 3 => 0.05051607654502832
data ke: 4 => 0.27535124215716744
data ke: 5 => 0.39262323000723776
Selesai
🎯 Penjelasan Konsep

Menggunakan perulangan while (uncounted loop) karena tidak tahu pasti berapa kali harus generate bilangan
Menggunakan conditional if untuk memfilter hanya bilangan < 0.5
Kombinasi while dan if membuat program efisien


Latihan 2 - Perhitungan Laba Usaha
📝 Deskripsi Program
Program menghitung total keuntungan seorang pengusaha selama 8 bulan dengan modal awal 100 juta rupiah, dengan persentase laba yang berbeda-beda setiap bulannya.
🔄 Alur Algoritma

Inisialisasi Variabel

modal_awal = 100.000.000 (100 juta rupiah)
total_laba = 0


Perulangan For (8 Bulan)

Loop dari bulan 1 sampai bulan 8


Logika Perhitungan Laba per Bulan

Bulan 1-2: Laba 0% (belum dapat laba)
Bulan 3-4: Laba 1% dari modal
Bulan 5-7: Laba 5% dari modal (naik 4%)
Bulan 8: Laba 2% dari modal (turun 3% dari bulan sebelumnya)


Perhitungan

Untuk setiap bulan:

Hitung laba_bulan_ini = modal_awal × (laba_persen / 100)
Tambahkan ke total_laba
Tampilkan laba bulan tersebut




Output Akhir

Tampilkan total laba selama 8 bulan



💻 Kode Program
python# Modal awal
modal_awal = 100_000_000

# Inisialisasi variabel
total_laba = 0

# Perhitungan laba per bulan
for bulan in range(1, 9):
    # Menentukan persentase laba per bulan
    if bulan <= 2:
        laba_persen = 0  # Bulan 1-2: tidak ada laba
    elif bulan <= 4:
        laba_persen = 1  # Bulan 3-4: laba 1%
    elif bulan <= 7:
        laba_persen = 5  # Bulan 5-7: laba 5%
    else:
        laba_persen = 2  # Bulan 8: laba 2%
    
    # Hitung laba bulan ini
    laba_bulan_ini = modal_awal * (laba_persen / 100)
    total_laba += laba_bulan_ini
    
    # Tampilkan informasi per bulan
    print(f"laba bulan ke- {bulan} sebesar: {int(laba_bulan_ini)}")

print(f"Total laba adalah: {int(total_laba)}")
Output:
laba bulan ke- 1 sebesar: 0
laba bulan ke- 2 sebesar: 0
laba bulan ke- 3 sebesar: 1000000
laba bulan ke- 4 sebesar: 1000000
laba bulan ke- 5 sebesar: 5000000
laba bulan ke- 6 sebesar: 5000000
laba bulan ke- 7 sebesar: 5000000
laba bulan ke- 8 sebesar: 2000000
Total laba adalah: 19000000
🎯 Penjelasan Konsep

Menggunakan perulangan for (counted loop) karena jumlah perulangan sudah pasti (8 bulan)
Menggunakan conditional if-elif-else untuk menentukan persentase laba setiap bulan
Akumulasi laba menggunakan operator +=

📈 Rincian Perhitungan
BulanPersentase LabaLaba (Rp)Keterangan10%0Belum dapat laba20%0Belum dapat laba31%1.000.000Mulai dapat laba41%1.000.000Laba tetap55%5.000.000Naik 4%65%5.000.000Laba tetap75%5.000.000Laba tetap82%2.000.000Turun 3%Total-19.000.000-

Latihan 3 - Simulasi ATM
📝 Deskripsi Program
Program simulasi mesin ATM sederhana yang memungkinkan pengguna untuk menarik uang dari saldo awal Rp 1.000.000 hingga saldo habis atau memilih untuk keluar.
🔄 Alur Algoritma

Inisialisasi Variabel

saldo = 1.000.000 (saldo awal)


Perulangan While

Selama saldo > 0, lakukan:


Tampilan Menu

Tampilkan saldo saat ini
Tampilkan menu:



Tarik Uang




Keluar




Minta user memilih menu


Proses Pilihan Menu
Jika pilihan = 1 (Tarik Uang):

Minta input jumlah penarikan
Cek apakah jumlah ≤ saldo

Jika ya: kurangi saldo, tampilkan "Penarikan berhasil!"
Jika tidak: tampilkan "Saldo tidak cukup!"



Jika pilihan = 2 (Keluar):

Tampilkan pesan terima kasih
Keluar dari program (break)

Jika pilihan tidak valid:

Tampilkan pesan error


Pengecekan Saldo Habis

Jika saldo = 0, tampilkan pesan saldo habis dan program berhenti



💻 Kode Program
python# Saldo awal
saldo = 1000000

while saldo > 0:
    print(f"Saldo saat ini: Rp {saldo}")
    print("1. Tarik Uang")
    print("2. Keluar")
    pilihan = int(input("Pilih menu (1/2): "))
    
    if pilihan == 1:
        # Tarik uang
        jumlah = int(input("Masukkan jumlah penarikan: "))
        
        if jumlah <= saldo:
            saldo -= jumlah
            print("Penarikan berhasil!")
        else:
            print("Saldo tidak cukup!")
    
    elif pilihan == 2:
        # Keluar
        print("Terima kasih telah menggunakan ATM!")
        break
    
    else:
        print("Pilihan tidak valid!")

# Jika saldo habis
if saldo == 0:
    print("Saldo Anda habis! Terima kasih telah menggunakan ATM!")
Contoh Output:
Saldo saat ini: Rp 1000000
1. Tarik Uang
2. Keluar
Pilih menu (1/2): 1
Masukkan jumlah penarikan: 300000
Penarikan berhasil!

Saldo saat ini: Rp 700000
1. Tarik Uang
2. Keluar
Pilih menu (1/2): 2
Terima kasih telah menggunakan ATM!
🎯 Penjelasan Konsep

Menggunakan perulangan while karena jumlah transaksi tidak tentu
Menggunakan conditional if-elif-else untuk memproses pilihan menu
Menggunakan break untuk menghentikan perulangan saat user memilih keluar
Validasi input untuk memastikan penarikan tidak melebihi saldo

🔍 Flowchart Logika
START
  ↓
Saldo = 1000000
  ↓
Apakah saldo > 0?
  ↓ Ya
Tampilkan Menu
  ↓
Input Pilihan
  ↓
Pilihan = 1? → Ya → Input Jumlah → Cek Saldo Cukup? → Ya → Kurangi Saldo
  ↓                                      ↓ Tidak           ↓
Pilihan = 2? → Ya → Keluar               Pesan Error      Pesan Sukses
  ↓ Tidak                ↓                                    ↓
Pesan Error              END              ← ← ← ← ← ← ← ← ← ←
  ↓                                       (Kembali ke awal loop)
Kembali ke awal
        print(f"data ke: {count} => {angka}")

print("Selesai")
