Rocket.Chat Technical Assessment

In this document, I'll cover how using the Rocket.Chat API with Postman to perform tasks such as logging in, creating a new user, getting information about a room, and retrieving a list of user roles.

Login to Rocket.Chat

First to log in and obtain an authentication token. I’ve logged in using Postman, following these steps:
1.	Open Postman.
2.	Select the "POST" method.
3.	Enter the URL https://192.168.86.163/api/v1/login in the address bar.
4.	In the "Header" tab, I’ve added the Content Type as “application/json”.
5.	In the “Body” tab I’ve entered the following JSON object in the body

{
  "user": "rofreixo",
  "password": "Fre6969*"
}

6.	Click the "Send" button to execute the request.

The response contains a JSON object with a user and authToken field, which I used for the subsequent requests to authenticate as the user.
	
	The file Login output in Github contains the response

Create a New User

To create a new user in Rocket.Chat using the API, I’ve followed these steps:

1.	Open Postman.
2.	Select the "POST" method.
3.	Enter the URL https://192.168.86.163/api/v1/users.create in the address bar
4.	In the "Header" tab, I’ve added the following KEYs “X-User-Id”, “X-Auth-Token” with the authentication token obtained from the login request, and selected the Content Type as “application/json”.
5.	In the "Body" tab, select the "raw" format.
6.	Enter the following JSON object in the body:

{
  "email": "jujufreixo@gmail.com",
  "name": "jujufreixo",
  "password": "dalila13",
  "username": "jujufreixo",
  "active": true
}

7.	Click the "Send" button to execute the request.

The response contains a JSON object with information about the newly created user.

	The file Create New User output contains the response

Get Room Information

To get information about a specific room in Rocket.Chat, I’ve followed these steps:

1.	Open Postman.
2.	Select the "GET" method.
3.	Enter the URL https://192.168.86.163/api/v1/rooms.info in the address bar.
4.	In the "Header" tab, I’ve added the following KEYs “X-User-Id”, “X-Auth-Token” with the authentication token obtained from the login request and selected the Content Type as “application/json”.
5.	In the "Params" tab, add a key-value pair for the roomName parameter, with the “general” as the value. 
6.	6. Click the "Send" button to execute the request.

The response contains a JSON object with information about the specified room, including its name, type, and a list of members.

		The file Get the room information output contains the response

Get List of User Roles

To retrieve a list of all user roles in Rocket.Chat, follow these steps:
1.	Open Postman.
2.	Select the "GET" method.
3.	Enter the URL https://192.168.86.163/api/v1/roles.list in the address bar.
4.	In the "Header" tab, I’ve added the following KEYs “X-User-Id”, “X-Auth-Token” with the authentication token obtained from the login request and selected the Content Type as “application/json”.
5.	Click the "Send" button to execute the request.

The response contains a JSON object with an array of user roles, each with information about the role's name and permissions.

		The file Get List of User Roles output contains the response

Conclusion

In this document, I've covered the basics of using the Rocket.Chat API with Postman to perform tasks such as logging in, creating a new user, getting information about a room, and retrieving a list of user roles.
