This is a base node js Project template,which anyone can use as it has been prepared,
by keeping some of the most important code principles and project management recommendations.
Feel free to change anything.

`src` -> Inside the src folder all the actual source code regarding the project will reside,
this will not include any kind of tests.(You might want to make separate tests folder)

Lets take a look inside the `src` folder

 - `config` -> In this folder anything and everything regarding any configuration or the setup of a library
 or module  will be done. For example : setting up `dotenv` so that we can use the environment variables 
 anywhere in a cleaner fashion, this is done in the `server-config.js`.One more example can be setup your 
 logging library that can help you to prepare meaningful logs,so configuration for this library should 
 also be done here.

 - `routes` -> In the routes folder, we register a route and the corresponding middleware and controllers to it.

 - `middleware` -> they are just going to intercept the incoming request where we can write our validators,authentications etc.

 - `controllers` -> they are kind of the last middlewares as post them you call your business layer to execute the business logic.
 In controllers, we just receive the incoming request and data and pass it to the business layer, and once business layer
 returns an output, we structure the API responsein controllers and send the output.

 - `repositories` ->  this folder contains all the logic using which we interact the DB by writing queries,all the RAW queries 
 or ORM queries will go here. 

- `services` -> contains the business logic and interacts with the repositories for the data from the database.

 - `utils` -> It is just contains the helper methods, error classes etc.

### Setup the Project 

- Download this template from github and and open it in your favourite text editor.
- In the root directory,create a `.env` file and add the following env variables
  
  ```
      PORT = <port number of your choice>
  ```
  ex : 
  ```
      PORT = 3000
  ```

  - Inside a `src/config` folder create a file named as `config.json`
  and write the following code

  ```
  {
  "development": {
    "username": "root",
    "password": null,
    "database": "database_development",
    "host": "127.0.0.1",
    "dialect": "mysql"
  },
  "test": {
    "username": "root",
    "password": null,
    "database": "database_test",
    "host": "127.0.0.1",
    "dialect": "mysql"
  },
  "production": {
    "username": "root",
    "password": null,
    "database": "database_production",
    "host": "127.0.0.1",
    "dialect": "mysql"
  }
}
```

 - If you are setting up your development environment, then write the username of your DB, password of your DB,
 and in dialect mention whatever DB you are using. for example : mysql, mariadb etc.

 - If you are setting up test or produuction environment, make sure you also replace the host with the hosted DB URL.
