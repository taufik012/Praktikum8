# Flowchart

![Flowchart](https://user-images.githubusercontent.com/115480692/207221430-e59235da-f34b-4fe4-a2a3-5db9fd8f713f.png)

# Diagram

<img width="334" alt="Diagram" src="https://user-images.githubusercontent.com/115480692/207221520-fb09dfde-ca0b-4868-800c-b3d774d497a9.png">

#

## Membuat Class
    
    def __init__(self, nama, nim, tugas, uts, uas):
        self.nama = nama
        self.nim = nim
        self.tugas = tugas
        self.uts = uts
        self.uas = uas

## Menambahkan Data
        
    def tambah(self, nama, nim, tugas, uts, uas):
        data.nama.append(nama)
        data.nim.append(nim)
        data.tugas.append(tugas)
        data.uts.append(uts)
        data.uas.append(uas)

## Melihat Data

    def lihat(self):
        for i in range(len(data.nama)):
            print("|", i + 1, "  |", end="")
            print('{0:<25}'.format(self.nama[i]), end="")
            print("|", self.nim[i], end="")
            print(" |", self.tugas[i], end="")
            print("    |", self.uts[i], end="")
            print("  |", self.uas[i], " | ", end="")
            print(f'{((self.tugas[i] * 30 / 100) + (self.uts[i] * 35 / 100) + (self.uas[i] * 35 / 100)) :.2f}', " |")

## Mengubah Data

    def ubah(self, nama, nim, tugas, uts, uas):
        self.nama[no] = nama
        self.nim[no] = nim
        self.tugas[no] = tugas
        self.uts[no] = uts
        self.uas[no] = uas

## Menghapus Data

    def hapus(self):
        del self.nama[no]
        del self.nim[no]
        del self.tugas[no]
        del self.uts[no]
        del self.uas[no]

## Dictonary

data = Mahasiswa([], [], [], [], [])

## Menjalankan Program

while True:
    menu = input("(1)Tambah data, (2)Tampilkan data, (3)Ubah data, (4)Hapus data, (5)Keluar: ")

    if menu == "1":
        print("\nTAMBAH DATA")
        data.tambah(
            input("Masukkan Nama  \t  : "),
            input("Masukkan NIM   \t  : "),
            int(input("Nilai Tugas\t  : ")),
            int(input("Nilai UTS  \t  : ")),
            int(input("Nilai UAS  \t  : "))
        )
        print("\nData berhasil ditambahkan")

    elif menu == "2":
        print()
        print("=" * 74)
        print("|                        DAFTAR NILAI MAHASISWA                          |")
        print("=" * 74)
        print("| No  |          Nama           |    NIM    | TUGAS | UTS | UAS |  AKHIR |")
        print("=" * 74)
        if len(data.nama) != 0:
            data.lihat()
        else:
            print("|                             TIDAK ADA DATA                             |")
        print("=" * 74)

    elif menu == "3":
        print("\nUBAH DATA")
        print("Masukkan Nama Yang Ingin di Ubah")
        ubah = input("Masukkan Nama : ")
        if ubah in data.nama:
            no = data.nama.index(ubah)
            print()
            print("Masukkan Data Baru")
            data.ubah(
                input("Masukkan Nama  \t  : "),
                input("Masukkan NIM   \t  : "),
                int(input("Nilai Tugas\t  : ")),
                int(input("Nilai UTS  \t  : ")),
                int(input("Nilai UAS  \t  : "))
            )
        else:
            print(ubah, "DATA TIDAK DITEMUKAN")

    elif menu == "4":
        print("\nHAPUS DATA")
        print("Masukkan Nama Yang Ingin di Hapus")
        hapus = input("Masukkan Nama : ")
        if hapus in data.nama:
            no = data.nama.index(hapus)
            data.hapus()
            print("Data", hapus, "Berhasil dihapus")
        else:
            print(hapus, "DATA TIDAK DITEMUKAN")

## Menghentikan Program
            
    elif menu == "5":
        print("\nHATUR NUHUN :)\n")
        break
    else:
        print("\nPerintah yang dimasukkan salah!\n")
