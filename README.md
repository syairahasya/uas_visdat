# Analisis Kemiskinan Indonesia 2025

Dashboard visualisasi data dan analisis multivariat mengenai kemiskinan di Indonesia dengan pendekatan Principal Component Analysis (PCA), pengelompokan provinsi, serta eksplorasi indikator sosial-ekonomi.

## Deskripsi Proyek

Proyek ini berisi:

- dashboard interaktif dalam format HTML untuk visualisasi kemiskinan Indonesia 2025
- notebook analisis PCA dan preprocessing data
- dataset Excel yang berisi indikator kemiskinan dan indikator pendukung antar provinsi

Tujuan utama proyek ini adalah untuk mengukur dan memvisualisasikan kondisi kemiskinan Indonesia dengan pendekatan data multidimensi, khususnya melalui reduksi dimensi dan interpretasi indikator yang paling berpengaruh terhadap variasi antar provinsi.

## Fokus Analisis

Analisis dalam notebook mencakup beberapa tahap berikut:

- audit dan validasi struktur data dari file Excel
- preprocessing data antar sheet
- standardisasi z-score agar variabel memiliki skala yang setara
- rekayasa arah variabel agar indikator negatif dan positif memiliki interpretasi yang konsisten
- uji asumsi PCA, seperti Bartlett Test dan KMO
- reduksi dimensi menggunakan PCA
- clustering menggunakan K-Means
- deteksi outlier menggunakan Isolation Forest
- visualisasi hasil dalam bentuk dashboard dan analisis tematik

## Data yang Digunakan

Proyek ini menggunakan data yang tersimpan dalam file Excel berikut:

- `kumpulan data.xlsx`
- `hierarki_tingkat.xlsx`

Data utama mencakup indikator seperti:

- IPM
- Kedalaman Kemiskinan (P1)
- Kematian Bayi
- Sanitasi
- Gini
- TPT (Tingkat Pengangguran Terbuka)
- PDRB per Kapita
- Pekerja Formal
- APK PT
- Internet / Blank Spot

Data difilter untuk 38 provinsi di Indonesia dan dilakukan penanganan missing value serta standarisasi indikator sebelum analisis PCA.

## Struktur Folder

```text
uas_visdat/
├── README.md
├── Kemiskinan Indonesia 2025_ dasbor visualisasi data.html
├── PCA_Visdat_(4).ipynb
├── kumpulan data.xlsx
├── hierarki_tingkat.xlsx
└── .git/
```

## File Utama

### 1. Dashboard HTML

File:

- `Kemiskinan Indonesia 2025_ dasbor visualisasi data.html`

Fungsi:

- menampilkan dashboard visualisasi data secara interaktif
- menyajikan insight kemiskinan Indonesia dalam bentuk tampilan modern
- dapat dibuka langsung di browser tanpa proses build

### 2. Notebook PCA

File:

- `PCA_Visdat_(4).ipynb`

Fungsi:

- menganalisis data dengan Python
- melakukan preprocessing dan standardisasi
- menjalankan PCA, K-Means, dan Isolation Forest
- mengevaluasi asumsi statistik PCA

## Persyaratan

Untuk menjalankan notebook, diperlukan environment Python dengan paket berikut:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn plotly factor_analyzer altair vega_datasets jupyter
```

Untuk menjalankan dashboard HTML, cukup dibuka dengan browser modern seperti:

- Google Chrome
- Microsoft Edge
- Firefox

## Cara Menjalankan Proyek

### A. Menjalankan dashboard HTML

1. Buka file `Kemiskinan Indonesia 2025_ dasbor visualisasi data.html`.
2. File bisa dibuka langsung dari browser.
3. Jika browser memblokir beberapa fitur lokal, gunakan mode browser yang diizinkan untuk file lokal.

### B. Menjalankan notebook PCA

1. Buka Jupyter Notebook atau VS Code dengan dukungan Python.
2. Jalankan notebook `PCA_Visdat_(4).ipynb`.
3. Pastikan file `kumpulan data.xlsx` tersedia di folder kerja yang sama atau sesuaikan path di notebook.

Catatan penting:

- Dalam notebook terdapa path default seperti `/content/kumpulan data.xlsx`.
- Jika dijalankan di lingkungan lokal, sesuaikan path menjadi lokasi file Excel Anda.

## Metodologi Singkat

### Preprocessing

- membaca 10 sheet dari data Excel utama
- memilih kolom provinsi dan indikator yang relevan
- membersihkan nama kolom
- mengubah tipe data ke numerik
- filtering hanya 38 provinsi
- menghilangkan duplikat provinsi
- imputasi missing values menggunakan median
- membalik polaritas untuk variabel negatif agar interpretasi konsisten
- standardisasi z-score untuk setiap variabel

### PCA

- dilakukan reduksi dimensi agar data lebih mudah dipahami
- variabel dengan kontribusi tinggi pada komponen utama diidentifikasi
- hasil PCA digunakan untuk melihat struktur variasi antar provinsi

### Clustering dan Outlier Detection

- K-Means digunakan untuk membentuk kelompok provinsi berdasarkan kesamaan indikator
- Isolation Forest digunakan untuk mendeteksi provinsi yang tergolong pencilan

## Interpretasi Umum

Proyek ini bertujuan untuk menggambarkan bagaimana kondisi kesejahteraan dan kemiskinan antar provinsi beragam, serta melihat indikator yang paling berpengaruh dalam membedakan kondisi satu provinsi dengan provinsi lainnya.

Secara umum, indikator yang sering berperan penting dalam analisis multivariat kemiskinan adalah:

- tingkat pendapatan atau PDRB per kapita
- tingkat pengangguran
- tingkat kedalaman kemiskinan
- akses sanitasi dan internet
- ketimpangan pendapatan (Gini)
- kesehatan dan mortalitas bayi

## Kebutuhan Pengembangan Lebih Lanjut

Beberapa pengembangan yang mungkin dilakukan ke depan:

- menambahkan data tahun lebih banyak untuk analisis time-series
- membandingkan kondisi kemiskinan antar tahun
- menambahkan visualisasi interaktif berbasis Plotly atau dashboard web dinamis
- membuat laporan formal dengan ringkasan temuan dan rekomendasi
- mengintegrasikan data geospatial kabupaten/kota

## Catatan

Proyek ini dibuat untuk keperluan tugas visualisasi data / analisis multivariat dan bersifat edukatif. Hasil analisis dapat dimodifikasi sesuai kebutuhan akademik atau penelitian lanjutan.

## Lisensi

Belum ditetapkan secara eksplisit pada proyek ini. Jika akan digunakan untuk publikasi atau pembelajaran formal, disarankan untuk menambahkan lisensi yang sesuai.

## Penulis

Proyek ini dikembangkan untuk kebutuhan studi terkait kemiskinan Indonesia dan visualisasi data berbasis analisis multivariat.

---

Jika Anda ingin, saya juga bisa membuat versi README yang lebih singkat untuk GitHub, atau versi yang lebih formal untuk laporan tugas akademik.
