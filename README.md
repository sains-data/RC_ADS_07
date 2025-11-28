# Ringkasan
Tugas ini bertujuan untuk menganalisis perbedaan rata-rata pengeluaran makanan mahasiswa berdasarkan tempat tinggal (Rumah, Kos, Asrama) menggunakan metode ANOVA dan uji non-parametrik sebagai alternatif. Analisis ini menggunakan data survei mahasiswa Institut Teknologi Sumatera (ITERA) dengan fokus pada hubungan antara tempat tinggal dan pengeluaran makanan.

# Struktur Repositori
```
main/
├── data/
│   ├── Dataset Tugas Besar ADS 2025.xlsx
│   ├── Dataset Tugas Besar ADS 2025.csv
│   └── Dataset Tugas Besar ADS 2025 (Bersih).xlsx
│
├── code/
│   └── Perbedaan Rata-Rata Pengeluaran Makanan Mahasiswa Berdasarkan Tempat Tinggal (Rumah, Kos, Asrama) Menggunakan ANOVA.Rmd
│
├── output/
│   ├── hasil_analisis/
│   │   ├── data_bersih.csv
│   │   ├── statistik_deskriptif.csv
│   │   ├── hasil_anova.csv
│   │   ├── hasil_kruskal.csv
│   │   ├── hasil_posthoc_tukey.csv
│   │   ├── data_visualisasi.csv
│   │   └── ringkasan_hasil.txt
│   │
│   └── visualisasi/
│       ├── distribusi_uang_saku.png
│       ├── qq_plot.png
│       ├── perbandingan_varians.png
│       └── rata_rata_uang_saku.png
│
├── poster/
│   └── Perbedaan Rata-rata Pengeluaran Mahasiswa Berdasarkan Tempat Tinggal.png
│
└── README.md
```

# Dataset
Dataset yang digunakan merupakan data survei mahasiswa ITERA tahun 2025 yang berisi informasi:
- Demografi mahasiswa (jenis kelamin, asal daerah, program studi)
- Karakteristik ekonomi (uang saku, pekerjaan orang tua, pendapatan keluarga)
- Kondisi tempat tinggal (jenis tempat tinggal, jarak dari kampus)
- Kebiasaan belajar dan keterlibatan dalam organisasi

Dataset utama berisi 458 responden dengan 19 variabel. Analisis ini terutama menggunakan variabel:
- **Uang Saku** (diasumsikan sebagai proksi pengeluaran makanan)
- **Jenis Tempat Tinggal** (Rumah, Kos, Asrama)

*Catatan: Pengeluaran makanan spesifik tidak tersedia di dataset sehingga menggunakan uang saku sebagai variabel pengganti.*

## Cara Menjalankan Script

## Prasyarat
- R versi 4.0 atau lebih baru
- RStudio (direkomendasikan)

## Langkah-langkah
1. Clone repositori ini:
```bash
git clone https://github.com/sains-data/RC_ADS_07.git
cd analisis-pengeluaran-makanan-mahasiswa
```

2. Buka RStudio dan atur working directory ke folder project:
```r
setwd("path/to/analisis-pengeluaran-makanan-mahasiswa")
```

3. Install paket yang diperlukan:
```r
# Jalankan perintah berikut jika belum menginstall paket-paket yang dibutuhkan
install.packages(c("dplyr", "ggplot2", "car", "ggpubr", "tidyr", "rstatix", "dunn.test", "broom", "scales"))
```

4. Jalankan script analisis utama:
```r
source("code/analisis_anova.R")
```

5. Untuk mengekspor hasil analisis ke format CSV:
```r
source("code/export_results.R")
```

# Hasil Analisis
Ringkasan Hasil Analisis
========================

Judul Analisis: Perbedaan Rata-Rata Pengeluaran Makanan Mahasiswa Berdasarkan Tempat Tinggal
Metode Analisis: ANOVA dan Kruskal-Wallis

Jumlah Sampel per Kelompok:

| Asrama | Kos | Rumah |
| :----: | :-: | :---: |
|   27   | 270 |  111  | 

|                |     |
|----------------|-----|
| **Keputusan**  | : Tolak H0 |
| **Kesimpulan** | : Terdapat perbedaan signifikan |
| **p-value**    | : 0.000274 |

# Paket R yang Digunakan
Berikut adalah paket-paket R yang digunakan dalam analisis ini:

| Paket | Fungsi Utama |
|-------|--------------|
| `dplyr` | Manipulasi dan transformasi data |
| `ggplot2` | Visualisasi data |
| `car` | Analisis regresi dan ANOVA |
| `ggpubr` | Visualisasi hasil statistik |
| `tidyr` | Reshaping data |
| `rstatix` | Uji statistik non-parametrik |
| `dunn.test` | Uji post-hoc untuk Kruskal-Wallis |
| `broom` | Konversi hasil model ke format tidy |
| `scales` | Format angka pada visualisasi |
