## MongoDB Shell Commands
####  Basic MongoDB Shell Commands
- Here is a list of useful MongoDB commands that you can use inside the shell.

1. Show Databases
- List all databases in the MongoDB server.

```javascript
show databases
```
2. Switch to myDatabase
- Switch to the myDatabase database.

```javascript
use myDatabase
```
3. Show Collections
- List all collections in the current database.

```javascript
show collections
```
4. Show Current Database
- Display the name of the current database.

```javascript
db
```
5. Collection Count
- Get the number of collections in the current database.

```javascript
db.getCollectionNames().length
```
6. View Database Stats
- Retrieve statistics about the current database.

```javascript
db.stats()
```
7. Show Collection Stats
- Retrieve statistics about a particular collection.

```javascript
db.collection_name.stats()
```
8. Create a New Collection
- Create a new collection in the database.

```javascript
db.createCollection("newCollection")
```
9. Insert Data into a Collection
- Insert a sample document into a collection.

```javascript
db.myCollection.insertOne({ name: "John Doe", age: 30, city: "New York" })
```
10. Find Documents in a Collection
- Query all documents in a collection.

```javascript
db.myCollection.find().pretty()
```
11. Find Documents with a Query
- Query documents in a collection with a specific condition.

```javascript
db.myCollection.find({ age: { $gt: 25 } }).pretty()
```
12. Create an Index
- Create an index on a specific field in a collection.

```javascript
db.myCollection.createIndex({ name: 1 })
```
13. List Indexes
- List all indexes in a collection.

```javascript
db.myCollection.getIndexes()
```
14. Drop an Index
- Drop a specific index in a collection.

```javascript
db.myCollection.dropIndex("index_name")
```
15. Update a Document
- Update a document in a collection.

```javascript
db.myCollection.updateOne({ name: "John Doe" }, { $set: { age: 31 } })
```
16. Delete a Document
- Delete a specific document from a collection.

```javascript
db.myCollection.deleteOne({ name: "John Doe" })
```
17. Delete Many Documents
- Delete multiple documents based on a condition.

```javascript
db.myCollection.deleteMany({ age: { $lt: 30 } })
```
18. Drop a Collection
- Drop an entire collection from the database.

```javascript
db.myCollection.drop()
```
19. Show Index Stats
- Display index size statistics for a collection.

```javascript
db.myCollection.stats().indexSize
```
20. Drop the Database
- Drop the current database, removing all collections and indexes.

```javascript
db.dropDatabase()
```
21. Backup Database (Outside Mongo Shell)
- Use mongoexport to export data from a collection for backup.

```bash
mongoexport --db=myDatabase --collection=myCollection --out=backup.json
```
22. Restore Data (Outside Mongo Shell)
- Use mongoimport to import data from a backup file.

```bash
mongoimport --db=myDatabase --collection=myCollection --file=backup.json
```
23. Get Server Status
- Get server information like memory usage and uptime.

```javascript
db.serverStatus()
```
24. Show File System Stats
- Display the file system usage statistics.

```javascript
db.stats().fsUsedSize
db.stats().fsTotalSize
```
25. List Users
- List all users in the current database.

```javascript
db.getUsers()
```
26. Create a User
- Create a user with a specified name, password, and roles. For example, to create a user r0han with the password 2580 and readWrite access to myDatabase, you can use:

```javascript
db.createUser({
  user: "r0han",
  pwd: "2580",
  roles: [{ role: "readWrite", db: "myDatabase" }]
})
```
27. Drop a User
- Drop a user from the database.

```javascript
db.dropUser("r0han")
```
28. List All Collections in myDatabase
- List all collections in the current database (myDatabase).

```javascript
db.getCollectionNames()
```

#### Clear the MongoDB Shell screen (like bash clear):

- You can type the following command in the MongoDB shell to clear the screen:

```javascript
cls()
```
- This will clear the screen in the MongoDB shell, just like the clear command in the bash shell.

#### Clear MongoDB Shell History (without closing mongosh):

- If you want to clear the command history in the current session, you can simply reset it by running the following:

```javascript
// This will clear the history from the current session
.exit
```