1. Create/ Use the database
    ```use DATABASE_NAME```

2. Show current database
    ```db```

3. Show all databases
    ```show dbs```

4. Insert document into collection
    ```db.collection_name.insert({"key":"value"})```

5. Delete current database
    ```db.dropDatabase()```

6. Create collection
    ```db.createCollection(name[, options])```

    Example:
    ```db.createCollection("myCollection")```

7. Delete a collection
    ```db.collection_name.drop()```

8. Insert multiple documents in collection
    ```db.collection_name.insert({"key1":"value1"},{"key2":"value2"})```

9. Query data from collection
    ```db.collection_name.find()```

10. Query data from collection with pretty output
    ```db.collection_name.find().pretty()```

11. Query only one object
    ```findOne()```

12. Oprations for find //passed in as arguments to find(...)
    * Equality
      ```{<key>:<value>}```
    * Less Than
      ```{<key>:{$lt:<value>}}```
    
    Similarly...
    * Less Than Equals - ```$lte```
    * Greater Than - ```$gt```
    * Greater Than Equals - ```$gte```
    * Not Equals - ```$ne```

  * AND
  ```{
         $and: [
             {key1: value1}, {key2:value2}
         ]
     }
  ```
  * OR
  ```{
          $or: [
              {key1: value1}, {key2:value2}
          ]
     }
  ```
  * AND and OR Together
  
    ```db.mycol.find({condition1}, $or: [{condition2},{condition3}])  ```

13. Update values in the existing document         ```db.collection_name.update(SELECTION_CRITERIA, UPDATED_DATA)```
Example:
    ```db.mycol.update({'key':'old_value'},{$set:{'key':'new_value'}})```
    To update multiple documents - ```{multi:true}```

14. *Replace* existing document with a new document passed in the save() method
```db.collection_name.save(NEW_DATA)```

15. Remove document form collection
```db.collection_name.remove(DELETION_CRITERIA[,justOne])```
Example:
```db.mycol.remove({'kay':'value'})```
If justOne is 1, mongo will remove only one document
If you dont specify deletion criteria, mongo will delete all docs form the collection

16. Projection - Select necessary data only
```db.collection_name.find({},{KEY1:1,KEY2:0}) #1->Show, 2->Hide```

17. See first N documents
```db.collection_name.find().limit(N)```

18. Skip first N documents
```db.collection_name.find().skip(N)```

19. Sort records
```db.collection_name.find().sort({KEY:1})```
1->Ascending, 2->Descending

20. Aggregation
```db.collection_name.aggregate(AGGREGATE_OPERATION)```
Aggregate Expressions:
```$sum, $avg, $min, $max, $push, $addToSet, $first, $last```
Stages in aggregation framework:
```$project, $match, $group, $sort, $skip, $limit, $unwind```

Mongo Datatypes:
```String, Integer, Boolean, Double, Min/ Max keys, Arrays, Timestamp, Object, Null, Symbol, Date, Object ID, Binary data, Code, Regular Expression.```

Note: 
* _id field is always displayed while executing find() method, if you don't want this field, then you need to set it as 0.

* Collection is automatically created while insert if it dosen't exist
Arguments inside [] are optional

Advanced (for later)

* db.createCollection("mycol", { capped : true, autoIndexId : true, size : 6142800, max : 10000 } )

