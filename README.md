# Mongo docker & Instructions for Remote Connect
mongo dockerfile with custom config file

##Build & Run 

- sudo docker build -t mongo .
- sudo docker run --name mymongo -d -p 27017:27017  mongo

## Add user

- use admin
- db.createUser({ user: "myuser", pwd: "mypwd", roles: ["root","userAdminAnyDatabase"] })

## Edit Config

- nano /etc/mongod.conf 
- uncomment: auth=true
- comment out: noauth = true

## Restart container

- sudo  docker restart mymongo

## Connect Mongo with Username

- mongo -u myuser -p mypwd --authenticationDatabase admin


