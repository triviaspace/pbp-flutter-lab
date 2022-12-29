# Tugas 7

## Stateless Widget dan Stateful Widget
Stateless widget adalah jenis widget yang bersifat final, artinya tidak dapat diubah atau tidak akan pernah berubah.

Misal kita mempunya widget yang berisi text “Halo Flutter!”, maka dari mulai text itu dibuat sampai aplikasi berjalan pun text tersebut tetap akan selalu menjadi “Halo Flutter!“.

Stateful Widget merupakan widget yang dinamis atau dapat berubah. Berkebalikan dengan stateless, stateful widget dapat melakukan update tampilan, mengubah warna, menambah jumlah baris, dll. Jadi dapat disimpulkan bahwa apapun widget yang dapat berubah maka itulah stateful widget.

Merujuk pada contoh kasus sebelumnya, dengan text “Halo Flutter!”, maka di stateful widget kita dapat mengubah text tersebut sesuai kebutuhan. Kita bisa mengubah warna atau font ketika kita melakukan suatu event (seperti tekan button).


## Widget yang dipakai
- Row: Widget yang berfungsi untuk menampilkan widget-widget tersusun secara horizontal.
- Padding: Widget yang berfungsi untuk memberikan padding pada widget yang dimaksud.
- SizedBox: Widget yang saya gunakan untuk menghilangkan button "-" ketika angka masih 0.
- FloatingActionButton: Widget button berbentuk lingkaran.
- Text: Widget untuk menampilkan text.


## Fungsi setState()
setState adalah cara flutter untuk melakukan rebuild wigdet dan turunannya. Ketika dilakukan rebuild, nilai dari variabel-variabel terbaru akan ter-update ke dalam UI yang dibuat dalam aplikasi yang kita buat.

## Const vs Final
a. Final <br>
Final (variabel yang menggunakan keyword final) diinialisasi pada saat pertama kali digunakan dan hanya disetel sekali. Dengan kata lain nilai final akan diketahui pada saat run-time. Final dapat digunakan untuk deklarasi variabel immutable yang nilainya sudah ataupun belum diketahui pada saat waktu kompilasi berjalan.

	Misal kita telah menetepkan nilai dari variabel umur = 21, jadi pada saat di compile, 
	nilai variabel sudah diketahui nilainya karena diinialisasi secara langsung dengan sebuah value. 
	Sehingga ketika di kompilasi nilainya sudah ada.
  
b. Const <br>
Const dapat digunakan untuk deklarasi variabel immutable yang nilainya bersifat konstan dan harus sudah diketahui pada saat waktu kompilasi (Compile time) berjalan, artinya adalah nilai dari variabel tersebut harus sudah di berikan value secara langsung. Artinya ketika di-compile, nilai variabel sudah diketahui, variabelnya sudah diberi nilai secara langsung.

## Implementasi tugas 7
1. Membuat app Flutter baru dengan menjalankan perintah flutter create counter_7 di CMD.
2. Melakukan perubahan pada main.dart yang terletak di dalam folder lib.
3. Membuat fungsi _decrementCounter() untuk pengurangannya.
4. Menambahkan widget floatingActionButton dengan flex row dan padding serta alignment spaceBetween.
5. Membuat conditional pada widget floatingActionButton bila value counter masih 0, maka akan digantikan dengan sizedBox transparan.
6. Mem-bind kedua button dengan fungsi increment atau decrement yang tadi sudah dibuat.
7. Membuat widget Text dengan conditional berisi warna text, merah bila value counter genap dan biru bila value counter ganjil.
8. Melakukan testing dengan menjalankan perintah flutter run di CMD.


# Tugas 8
## Navigator.push dan Navigator.pushReplacement
`Navigator.push` adalah method untuk melakukan push ke stack Navigator. `Navigator.pushReplacement` adalah method untuk mengganti route yang sedang ditampilkan dengan push route atau halaman baru ke stack Navigator.

## Widget yang dipakai
1. TextFormField -> field untuk mengambil input dari user.
2. Drawer -> menu hamburger untuk melakukan navigasi ke page berbeda.
3. DropdownButtonFormField -> dropdown berisi pilihan input, pemasukan atau pengeluaran.
4. FloatingActionButton -> button yang di-bind untuk menambah data ke dalam list
5. Card -> menampilkan data input yang ada pada list.
6. Row and Column -> menyusun tata letak isi widget secara horizontal dan vertikal
7. Container -> menampung widget-widget agar dapat dimodifikasi secara bersamaan
8. Visibility -> menyembunyikan child didalamnya dengan kondisi tertentu
9. Navigator -> mengelola route pada program menggunakan Stack
10. Form -> wadah untuk mengelompokkan widget-widget form yang diperlukan

## Event pada Flutter
1. onPressed()
2. onChanged()
3. onSaved()

## Navigator dalam "mengganti" halaman Aplikasi Flutter
Navigator menggunakan struktur data tipe stack. Stack ini digunakan untuk layar sehingga method push menampilkan top of stack dari stack layar tersebut.

## Implementasi Tugas 8
1. Menambahkan drawer untuk menu counter, form, dan data budget
2. Menambahkan halaman form dengan input (berupa string, integer, dropdown, atau button). Input yang telah diambil akan dimasukkan kedalam list untuk disimpan agar bisa ditampilkan pada halaman budget data
3. Menambahkan halaman budget data untuk menunjukkan data yang sudah diinput pengguna dengan menggunakan ListView.Builder agar setiap objek pada list dapat ditunjukkan

# Tugas 9
## Pengambilan data JSON tanpa membuat model
Kita bisa mengambil data JSON tanpa membuat model, tetapi akan tidak praktis apabila data JSON banyak. Data JSON yang banyak akan menambah risiko terjadi ketidaksesuaian struktur sehingga susah untuk kita memperbaikinya. Selain itu, pembuatan model akan menjaga kejelasan kode dan juga efisiensi.

## Widget yang dipakai
1. Text -> memberikan style pada tulisan
2. Row and Column -> menyusun tata letak isi widget secara horizontal dan vertikal
3. Container -> menampung widget-widget agar dapat dimodifikasi secara bersamaan
4. Visibility -> menyembunyikan child didalamnya dengan kondisi tertentu
5. MainAxisAlignment -> memposisikan children pada sumbu utama row dan column
6. Center -> membuat posisi children ke tengah
7. Navigator -> mengelola route pada program menggunakan Stack
8. Expanded, memperluas child dari baris dan kolom untuk mengisi ruang yang ada
9. Drawer -> membuat panel di sisi layar agar user bisa mengganti halaman
10. Form -> mengelompokkan widget-widget form yang diperlukan
11. Future Builder -> membuat widget berdasarkan snapshot yang diambil dari Future
12. TextSpan -> Menampilkan teks immutable secara merentang
13. SizedBox ->  Menampilkan sebuah box dengan ukuran tertentu

## Mekanisme pengambilan data dari JSON hingga dapat ditampilkan pada Flutter
Menambahkan depedensi HTTP, lalu melakukan GET pada data json yang selanjutnya dikonversikan ke dalam suatu model yang dibuat. Setelah itu, data json ditampilkan dengan menggunakan FutureBuilder.

## Implementasi Tugas 9
1. Menambahkan menu mywatchlist pada drawer dengan ListTile
2. Membuat file dart baru di dalam model yang berisi code dari quicktype
3. Membuat file baru untuk memuat data-data pada tugas 3 Django dan menambahkan link data tersebut agar kita dapat mengambil dan menampilkan data menggunakan fetch
4. Menampilkan data dengan ListView.Builder dan menulis code dalam OnTap() agar film dapat ditekan dan dapat dilihat detailnya
5. Menambahkan button pada paling bawah laman detail yang akan mengembalikan pengguna ke halaman page mywatchlist
