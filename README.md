

# **UTS Praktikum Deep Learning: Klasifikasi Digit MNIST dan Evaluasi Data Kustom**

## **Deskripsi Proyek**

Proyek ini merupakan Ujian Tengah Semester (UTS) mata kuliah Deep Learning.1 Tujuan utamanya adalah untuk mengimplementasikan, melatih, dan mengevaluasi dua arsitektur Convolutional Neural Network (CNN) untuk tugas klasifikasi digit tulisan tangan.

1. **Model A (CNN Kustom):** Sebuah arsitektur CNN yang dirancang dan dilatih dari awal (*from scratch*).1  
2. **Model B (Transfer Learning):** Sebuah arsitektur *pre-trained* (misalnya VGG16) yang diadaptasi dan di-*fine-tuning* untuk tugas klasifikasi MNIST.1

Kedua model dilatih pada dataset MNIST standar dan kemudian diuji kinerjanya menggunakan dataset kustom yang terdiri dari 30 citra tulisan tangan pribadi (berdasarkan 3 digit terakhir NIM).

## **Hasil Kinerja Utama**

Berikut adalah ringkasan kinerja akhir dari kedua model saat diuji pada 30 citra tulisan tangan kustom :

| Model | Arsitektur | Akurasi Validasi MNIST | Akurasi Data Kustom |
| :---- | :---- | :---- | :---- |
| **Model A** | CNN Kustom | 99.65% | **96.67%** |
| **Model B** | Transfer Learning (VGG16) | 83.86% (Tidak Stabil) | **66.67%** |

**Kesimpulan Utama:** Model CNN kustom (Model A) yang dirancang spesifik untuk tugas ini menunjukkan kinerja yang jauh lebih unggul dan stabil dibandingkan dengan pendekatan *transfer learning* (Model B). Hal ini kemungkinan besar disebabkan oleh ketidaksesuaian domain fitur antara ImageNet (sumber Model B) dan MNIST (tugas target), serta kompleksitas berlebih (*overkill*) dari arsitektur Model B untuk masalah topologi yang relatif sederhana.1

## **Kebutuhan Dependensi**

Proyek ini dikembangkan menggunakan Python. Pastikan Anda memiliki *library* berikut terinstal: pip install tensorflow numpy matplotlib opencv-python

## **Cara Menjalankan**

1. **Clone Repositori:**  
   Bash  
   git clone  
   cd

2. Instal Dependensi:  
   Pastikan semua library yang tercantum di atas telah terinstal di lingkungan Python Anda.  
3. **Siapkan Data Kustom (PENTING):**  
   * Buat sebuah folder baru di direktori utama proyek dengan nama data\_kustom/.  
   * Buat 30 citra tulisan tangan Anda sesuai instruksi: 10 citra untuk masing-masing dari 3 digit terakhir NIM Anda.1  
   * Tempatkan ke-30 citra tersebut di dalam folder data\_kustom/.  
   * **Catatan:** *Pipeline* pra-pemrosesan di dalam notebook (langkah-langkah seperti inversi warna, *resizing* ke 28x28, dan normalisasi) dirancang untuk memproses citra-citra mentah ini.1 Anda mungkin perlu menyesuaikan *path* (lokasi file) di dalam notebook jika Anda menamai folder secara berbeda.  
4. **Jalankan Notebook:**  
   * Buka file .ipynb (misalnya, UTS\_DEEPL\_\_\[NIM\]\_\[NAMA\].ipynb) menggunakan Jupyter Notebook atau Google Colab.  
   * Jalankan sel-sel kode secara berurutan dari atas ke bawah.  
   * Notebook ini akan secara otomatis:  
     1. Memuat dan memproses dataset MNIST.1  
     2. Membangun, mengompilasi, dan melatih Model A (CNN Kustom).1  
     3. Membangun, mengompilasi, dan melatih Model B (Transfer Learning).1  
     4. Memuat, memproses, dan mengevaluasi 30 citra kustom Anda pada kedua model.  
     5. Menampilkan plot *history* pelatihan dan hasil akurasi akhir.1