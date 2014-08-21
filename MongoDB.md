# MongoDB

## install MongoDB

sudo mkdir -p /data/db
sudo chown 'wongxming' /data/db
mongod

mongo shell
----------------------
MongoDB shell version: 2.6.4
connecting to: test
Server has startup 
> ~db
> test
> ~show dbs
> admin  (empty)
> local  0.078GB
> test   0.078GB
> ~show collections
> system.indexes
> testData
> ~db.testData.find()
> { "_id" : ObjectId("53f471f5f9d316272ad95f5d"), "name" : "wongm" }
> { "_id" : ObjectId("53f54ff8ce1dd8bc531ed811"), "name" : "wongm", "age" : 18 }
> { "_id" : ObjectId("53f5506cce1dd8bc531ed812"), "name" : "wongm", "age" : 18, "home" : "beijing" }

> ~db.testData.find( { "age": { $lt: 42} }, { "_id": 0, "name": 1 , "age": 1 } ). sort({"age": 1 })
> { "name" : "wongm", "age" : 18 }
> { "name" : "wongm", "age" : 18 }

> ~j={name:"wongm",age:18}
> { "name" : "wongm", "age" : 18 }
> ~db.testData.insert(j)
> WriteResult({ "nInserted" : 1 })

> ~db.testData.findOne()
> { "_id" : ObjectId("53f471f5f9d316272ad95f5d"), "name" : "wongm" }
