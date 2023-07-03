# Hotel Realta Backend

Untuk menggunakan RestAPI ini ada beberapa daftar environment pendukung yang harus di setting : 
1. Install Postgre dan PGAdmin dan pastikan pengaturan yang harus dimiliki pada saat menset database : 
   - DATABASE PORT = 5432 // Contoh
   - DATABASE HOST = localhost // contoh atau bisa bebas
   - DATABASE NAME = HotelRealtaDB
   - DATABASE USER = postgres
   - DB_PASSWORD = root
2. Selanjutnya buatlah file .env  : 
   - PORT= 5000
   - DB_PORT=5432 
   - DB_HOST=localhost 
   - DB_NAME=HotelRealtaDB 
   - DB_USER= postgres   
   - DB_PASSWORD= root
   - SECRET_KEY=hotelrealtabackendbatch220230126 // bisa diganti sesuaikan saja
3. - kemudian jalankan query berikut agar menginsert data dummy kedalam database HotelRealtaDB : 
   -> link : https://drive.google.com/file/d/1kc3IUwjDOj-x_dsE07n9GUTMjyljkhj5/view?usp=drive_link
4. Kemudian jalankan perintah berikut di terminal agar menggenerate tabel-tabel pada postgres menjadi sebuah model didalam project : 
   - "db_resto": "stg -D postgres -o models/restoSchema -h localhost -p 5432 -d HotelRealtaDB -u postgres -x 12345 --indices --associations-file association.csv -s resto",
   - "db_hotels": "stg -D postgres -o models/hotelSchema -h localhost -p 5432 -s hotel -d HotelRealtaDB -u postgres -x 123456 --indices",
   - "db_master": "stg -D postgres -o models/masterSchema -h localhost -s master -p 5432 -d HotelRealtaDB -u postgres -x 123456 --indices ",
   - "db_user": "stg -D postgres -o models/usersSchema -h localhost -p 5432 -s users -d HotelRealtaDB -u postgres -x 123456 --indices",
   - "pgScript": "stg -D postgres -o models/masterSchema -h localhost -p 5432 -d HotelRealtaDB -s master -u postgres -x root --indices --associations-file association.csv --clean",
   - "pg:generate-payment": "stg -D postgres -o models/paymentSchema -s payment -h localhost -p 5432 -d HotelRealtaDB -u postgres -x catecute07 --indices --associations-file ./association.csv ",
   - "pg:generate-users": "stg -D postgres -o models/usersSchema -s users -h localhost -p 5432 -d HotelRealtaDB -u postgres -x catecute07 --indices --associations-file association.csv ",
   - "pg:generate-booking": "stg -D postgres -o models/bookingSchema -s booking -h localhost -p 5432 -d HotelRealtaDB -u postgres -x catecute07 --indices --associations-file association.csv ",
   - "pg:generate-resto": "stg -D postgres -o models/restoSchema -s resto -h localhost -p 5432 -d HotelRealtaDB -u postgres -x catecute07 --indices --associations-file association.csv ",
   - "db_booking": "stg -D postgres -o models/bookingSchema -s booking --cm c -h localhost -p 5432 -d HotelRealtaDB -u postgres -x root --indices --associations-file association.csv --clean"
5. Jalankan npm install pada terminal, kemudian setelah package telah terinstall kedalam node_modules.
6. npm start:dev -> perintah untuk menjalankan project development, npm start:prod -> untuk production
7. ketik http://localhost:5000/ kedalam search bar browser
8. selesai
