# Proyek Klasifikasi Gambar: Buah

Proyek ini bertujuan untuk membangun model jaringan saraf tiruan (Convolutional Neural Network) yang mampu mengklasifikasikan 260 jenis buah yang berbeda berdasarkan gambar.

## Informasi Penulis
* **Nama:** Annisa Yusri Nur Rochmah
* **Email:** annisayusri59@gmail.com

---

## Informasi Dataset
Dataset yang digunakan dalam proyek ini adalah [Fruits 360](https://www.kaggle.com/datasets/moltean/fruits) dari Kaggle.
* **Total Gambar:** 137.221 gambar
* **Jumlah Kelas:** 260 kelas (termasuk berbagai jenis Apel, Pisang, Ceri, dll.)
* **Resolusi Gambar:** 100x100 pixels
* **Proporsi Pembagian Data:** 80% Data Latih (Train), 10% Data Validasi (Val), dan 10% Data Uji (Test).

---

## Arsitektur dan Performa Model
Model dibangun menggunakan antarmuka `tf.keras.Sequential` dengan arsitektur *Convolutional Neural Network* (CNN) kustom.

**Ringkasan Arsitektur:**
1.  6 lapisan `Conv2D` dengan filter yang bertambah (32, 64, 128, 256).
2.  Penggunaan `BatchNormalization` untuk menstabilkan pembelajaran.
3.  Penggunaan `MaxPooling2D` untuk reduksi dimensi.
4.  Penggunaan `Dropout` yang agresif (0.25 hingga 0.5) untuk mencegah *overfitting*.
5.  Lapisan klasifikasi terdiri dari `Flatten` dan 3 lapisan `Dense`.

**Hasil Evaluasi:**
Model berhasil mencapai target akurasi di atas 95% dan berhenti pelatihan (Early Stopping / Custom Callback) pada epoch ke-16 berkat optimasi algoritma.

| Metrik Evaluasi | Akurasi |
| :--- | :--- |
| **Training Accuracy** | 95.15% |
| **Validation Accuracy** | 97.84% |
| **Test Accuracy** | 98.04% |

---

## Struktur Direktori
Sesuai dengan format submission, berikut adalah struktur file yang disertakan:

```text
submission/
├── tfjs_model/           # Model hasil ekspor ke format TensorFlow.js
│   ├── group1-shardXofX.bin
│   └── model.json
├── tflite/               # Model hasil ekspor ke format TensorFlow Lite
│   ├── model.tflite
│   └── label.txt         # Daftar 260 kelas buah
├── saved_model/          # Model asli dalam format SavedModel (PB)
│   ├── saved_model.pb
│   └── variables/
├── Klasifikasi_Gambar_buah_Annisa Yusri.ipynb        # Source code lengkap (Google Colab)
├── README.md             # Dokumentasi proyek (file ini)
└── requirements.txt      # Daftar dependensi library
