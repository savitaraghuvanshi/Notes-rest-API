# Notes-rest-API
RESTful API for a “notes” application
Software requirements 

-Java 7
-Jersey
-Hibernate 3.6.4
-Jpa2
-Mysql 5.0.8
-Google chrome postman rest client to test
-Eclipse
-Tomcat7

Highlightes :
-Created UnAutherisedUserException,DatanotFoundException,InvalidDataInputException and a generic exception with valid codes.
-Created a seprate service layer to service resource file .
-Dao layer followed DAO design pattern.
-Created DtoToModelTransformer and ModelToDtoTransformer
-Extensive use of generics
-Established relationship between entities using JPA and Hiberlate .

Highlevel flow :

Resource>service>Dao>DB


Assumption
-Since access should be restricted to the owner of the note ,I dont find need of nested URIS for users and then its notes  .
we are just getting user id from authentication string and performing crud operation for that user .

Header input data :

Content-Type : application/json
Content-MD5:Q2hlY2sgSW50ZWdyaXR5IQ==
userid and password which you enter in user table .

URIs
http://localhost:8082/notesProject/webapi/notes  Get >get all notes resource
http://localhost:8082/notesProject/webapi/notes/{id}   Get >get specfic record {id}=resource id
http://localhost:8082/notesProject/webapi/notes    Post >Create new resource
{
   
    "noteDescription": "This is user note4",
    "title": "test12345678test12345678test12345678test12345678test12345678test12345678test12345678"
}


http://localhost:8082/notesProject/webapi/notes/1   put >update resource

{  
    "noteDescription": "This is user note 5",
    "title": "title new "
}

http://localhost:8082/notesProject/webapi/notes/1 delete

