# Panti_Jompo
> Anggota Kelompok :
> 1. 1907051004 - Gista Anggraini MZ
> 2. 1907051010 - Winda Ayu Triyani 
> 3. 1907051029 - Faris Ubad Alfharuq
> 
> Sistem ini dapat di gunakan untuk menginputkan data pasien, penanggung jawab,perawat,kamar,dan ranjang
> 
> Pada class diagram ini menggunkan relasi assosiasi karena setiap classnya memiliki satu hubungan dengan class tertentu atau lainnya. Dimana dashboard sebagai parents atau induknya yang memiliki class diantaranya :
> 1.  Penanggung_jawab
> 2.  Pasien
> 3.  Perawat
> 4.  Kamar
> 5.  Ranjang
> 
> Yang masing-masing class nya pula memiliki connector yaitu berupa class baru dengan nama:
> 1.  Data_pj
> 2.  Data_pasien
> 3.  Data_perawat
> 4.  Data_kamar
> 5.  Data_ranjang
> 
> Pada ERD ini menggunakan has diantara relasinya. Maksudnya has disini semua kelas saling memiliki, adapun penjabarannya :
>Dashboard sebagai class parents atau induk memiliki 5 buah anak class (classnya) diantaranya, class penanggung_jawab, class pasien, class perawat, class kamar, dan class ranjang. 
>
>Dimana masing masing class tersebut juga memiliki sebuah class connector yang diantaranya :
>Data_pj, data_pasien, data_perawat, data_kamar, dan data_ranjang. Maka dari itu menggunakan has karena dari setiap class tersebut saling memiliki.

Libraries and Tools of this project:
- mysql-connector-java-8.0.19.jar
- scene builder
- mysql server 
- netbean editor
- VS Code installed plugin
  - Markdown All in one
  - Markdown preview
  - Live Server
  
## Desain
To view the diagrams below install mermaid-diagram plugin at https://github.com/Redisrupt/mermaid-diagrams 

### classDiagram
```mermaid
classDiagram
    Dashboard <|-- penanggung_jawab
    Dashboard <|-- pasien
    Dashboard <|-- perawat
    Dashboard <|-- kamar
    Dashboard <|-- ranjang

        penanggung_jawab <|-- data_pj
    data_pj : int id_pj
    data_pj : String nama_pj
    data_pj : String jenis_kelamin
    data_pj : String status
    data_pj : String alamat
    data_pj : int no_hp
    data_pj : getAlamat()
    data_pj : getId_pj()
    data_pj : getJenis_kelamin()
    data_pj : getNama_pj()
    data_pj : getNo_hp()
    data_pj : getStatus_keluarga()
    data_pj : setAlamat()
    data_pj : setId_pj()
    data_pj : setJenis_kelamin()
    data_pj : setNama_pj()
    data_pj : setNo_hp()
    data_pj : setStatus_keluarga()
    

    pasien <|-- data_pasien
    data_pasien : int Id_pasien
    data_pasien : String nama_pasien
    data_pasien : String jenis_kelamin
    data_pasien : int umur
    data_pasien : String status
    data_pasien : String tanggal_lahir
    data_pasien : String tanggal_masuk
    data_pasien : getId_pasien()
    data_pasien : getId_pj()
    data_pasien : getJenis_kelamin()
    data_pasien : getNama_pasien()
    data_pasien : getStatus()
    data_pasien : getTanggal_lahir()
    data_pasien : getTanggal_masuk()
    data_pasien : getUmur()
    data_pasien : setId_pasien()
    data_pasien : setId_pj()
    data_pasien : setJenis_kelamin()
    data_pasien : setNama_pasien()
    data_pasien : setStatus()
    data_pasien : setTanggal_lahir()
    data_pasien : setTanggal_masuk()
    data_pasien : setUmur()

    perawat <|-- data_perawat
    data_perawat : int id_perawat
    data_perawat : String nama_perawat
    data_perawat : String jenis_kelamin
    data_perawat : int id_pasien
    data_perawat : getId_perawat()
    data_perawat : getId_pasien()
    data_perawat : getJenis_kelamin()
    data_perawat : getNama_perawat()
    data_perawat : setId_perawat()
    data_perawat : setId_pasien()
    data_perawat : setJenis_Kelamin()
    data_perawat : setNama_perawat()

    kamar <|-- data_kamar
    data_kamar : int no_kamar
    data_kamar : String nama_kamar
    data_kamar : int kapasitas
    data_kamar : int id_pasien
    data_kamar : int id_pj
    data_kamar : getId_pasien()
    data_kamar : getId_pj()
    data_kamar : getNama_kamar()
    data_kamar : getNo_kamar()
    data_kamar : setId_pasien()
    data_kamar : setId_pj()
    data_kamar : setKapasitas()
    data_kamar : setNama_kamar()

    ranjang <|-- data_ranjang
    data_ranjang : int no_ranjang
    data_ranjang : int id_pj
    data_ranjang : int id_pasien
    data_ranjang : int id_perawat
    data_ranjang : int no_kamar
    data_ranjang : getId_pasien()
    data_ranjang : getId_perawat()
    data_ranjang : getId_pj()
    data_ranjang : getNo_kamar()
    data_ranjang : getNo_ranjang()
    data_ranjang : setId_pasien()
    data_ranjang : setId_perawat()
    data_ranjang : setId_pj()
    data_ranjang : setNo_kamar()
    data_ranjang : setNo_ranjang()

    Dashboard : +pj()
    Dashboard : +perawat()
    Dashboard : +pasien()
    Dashboard : +kamar()
    Dashboard : +ranjang()
    class penanggung_jawab{
      +kembali()
      +getConnection()
      +getDataList()
      +showData()
      +tambah()
      +click()
    }
    class pasien{
      -kembali()
      +getConnection()
      +getDataList()
      +executeQuery()
      +tambah()
      +update()
      +click()
    }
    class perawat{
      -kembali()
      +getConnection()
      +getDataList()
      +showData()
      +executeQuery()
      +tambah()
      +click()
    }
    class kamar{
      -kembali()
      +getConnection()
      +getDataList()
      +showData()
      +executeQuery()
      +tambah()
      +update()
      +click()
    }
    class ranjang{
      -kembali()
      +getConnection()
      +getDataList()
      +showData()
      +executeQuery()
      +tambah()
      +hapus()
      +click()
    }
            
```

### ER Diagram
```mermaid
erDiagram
          DASHBOARD }|..|{ PENANGGUNG_JAWAB : has
          DASHBOARD ||--o{ PASIEN : has
          DASHBOARD ||--o{ PERAWAT : has
          DASHBOARD ||--o{ KAMAR : has
          DASHBOARD ||--o{ RANJANG : has
          PENANGGUNG_JAWAB ||--o{ data_pj : has
          PASIEN ||--o{ data_pasien : has
          PERAWAT ||--o{ data_perawat : has
          KAMAR ||--o{ data_kamar : has
          RANJANG ||--o{ data_ranjang : has
```



