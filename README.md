# Retail Data Pipeline & Analytics (Big Data Project)

Proyek ini mendemonstrasikan implementasi pipeline data end-to-end menggunakan ekosistem Big Data modern. Fokus utama proyek ini adalah mengolah dataset transaksi retail menggunakan Apache Spark dengan arsitektur pemisahan antara Compute (Spark) dan Storage (MinIO S3), serta integrasi Hive Metastore.

##  Stack Teknologi
*   **Engine Pengolahan:** Apache Spark 3.5.0
*   **Object Storage:** MinIO (S3-Compatible)
*   **Data Warehouse/Metastore:** Apache Hive 4.0.0
*   **Metadata DB:** PostgreSQL 15
*   **Orkestrasi:** Docker Compose
*   **Workspace:** PySpark (Jupyter Notebook)

##  Struktur Proyek
*   **`conf/`**: Konfigurasi `hive-site.xml` dan `spark-defaults.conf` untuk integrasi layanan.
*   **`data/`**: Direktori dataset mentah (mapped ke container Jupyter).
*   **`notebooks/`**: Alur kerja langkah-demi-langkah:
    1. `01_ingestion.ipynb`: Load data ke MinIO bucket.
    2. `02_eda_data_cleaning.ipynb`: Pembersihan data dengan PySpark.
    3. `03_data_transformation_segmentation.ipynb`: Agregasi dan segmentasi data.
    4. `04_hive_regist.ipynb`: Registrasi tabel ke Hive Metastore.
*   **`docker-compose.yml`**: Konfigurasi infrastruktur multi-container.
*   **`postgresql-jdbc.jar`**: Driver untuk koneksi Hive ke Postgres.

## 🚀 Cara Menjalankan
1.  **Setup Environment**: Jalankan `docker-compose up -d`.
2.  **Akses Jupyter**: Buka `localhost:8888` dengan token `bigdata2026`.
3.  **Akses MinIO**: Pantau data di `localhost:9001` (admin/admin).
4.  **Eksekusi**: Jalankan notebook 01-04 secara berurutan.

## 📊 Alur Kerja Data
1.  **Ingestion**: Memindahkan data lokal ke MinIO S3 Bucket.
2.  **Cleaning**: Menangani missing values dan tipe data secara terdistribusi.
3.  **Transformation & Segmentation**: Pembuatan fitur segmentasi pelanggan.
4.  **Storage**: Menyimpan data akhir dalam format Parquet/Table Hive untuk query SQL.
