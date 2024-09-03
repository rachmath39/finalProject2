- schema
- install package 
    - npm i express pg sequelize cors
    - npm init -y
- install sequelize
    - npm install --save-dev sequelize-cli  -> to install sequelize-cli
    - npx sequelize-cli init  -> to init sequelize-cli command & generate 4 dir
    - pada bagian config sesuaikan DB postgres
- create database
    - npx sequelize db:create

- create table
    - npx sequelize-cli model:generate --name User --attributes name:string,email:string,phone:string,address:string,gender:string,role:string,password:string
    - sesuaikan attribut, datatype, contrain dll pada dir migration
    - npx sequelize db:migrate
        (to modify,add table atribute after table creation, we can create migration file scheme and retry migrate)
        - npx sequelize migration:create --name add-totalAmount-to-orders
    - npx sequelize db:migrate:status
    - npx sequelize db:migrate:undo
- insert dummy data/seeding
    - npx sequelize seed:create --name seed-all-movies
    - akan mengenerate file di dir seeders (sesuaikan query & data pada directory seeders)
    - npx sequelize db:seed --seed 2024082607392.js

- create app
- Intall package encrypt & JWT
    - npm i bcrypt
    - npm i jsonwebtoken
    - npm i dotenv  -> membaca .env


catatan: 
token jwt meliputi 
- header
{
  "alg": "HS256",
  "typ": "JWT"
}
- payload data
{
  "name": "User1",
  "email": "user1@gmail.com",
  "role": "customer",
  "iat": 1724683068
}
- verify signature
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),secret
) 

echo "# finalProject2" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/rachmath39/finalProject2.git
git push -u origin main


secret = kode rahasia yang diencrypt dgn secret base64 encoded