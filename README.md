# Contact API with Secure JWT Authentication (Django Rest Framework)
## Introduction
This is a Contact API built using Django Rest Framework (DRF) that provides endpoints for user registration, login, and managing contacts. The API uses JWT (JSON Web Tokens) for secure authentication. Users can register, log in, view their contacts, perform CRUD operations on their contacts, mark contacts as favorites, and more.

## Requirements
Python 3.x
Django 3.x
Django Rest Framework 3.x
djangorestframework-simplejwt
Other dependencies (specified in requirements.txt)

## Installation
Clone the repository or download the source code.

Create a virtual environment and activate it.

Install the required dependencies:

pip install -r requirements.txt

Set up the database:

python manage.py makemigrations

python manage.py migrate

Create a superuser:

python manage.py createsuperuser

Start the development server:

python manage.py runserver

## Authentication
The API uses JWT authentication for secure user authentication. To access protected endpoints, users need to include their JWT token in the "Authorization" header of their HTTP requests using the "Bearer" scheme.

### Registration
Endpoint: /api/register/

Method: POST
#### Parameters:
username (string): The username of the user.

password (string): The password for the user account.

Response: A JWT token on successful registration.
### Login
Endpoint: /api/login/

Method: POST
#### Parameters:
username (string): The username of the user.

password (string): The password for the user account.

Response: A JWT token on successful login.
## Contact Management
To access the contact management endpoints, users need to be authenticated with a valid JWT token.

### View All Contacts
Endpoint: /api/contacts/

Method: GET

Response: A list of contacts belonging to the authenticated user.
### Create a Contact
Endpoint: /api/contacts/

Method: POST
#### Parameters:
name (string): The name of the contact.

email (string): The email address of the contact.

phone (string): The phone number of the contact.

Response: The created contact object.
### View a Contact
Endpoint: /api/contacts/<contact_id>/

Method: GET
#### Parameters:
contact_id (integer): The ID of the contact to retrieve.

Response: The contact object with the specified ID.
### Update a Contact
Endpoint: /api/contacts/<contact_id>/

Method: PUT or PATCH
#### Parameters:
contact_id (integer): The ID of the contact to update.

name (string): The updated name of the contact.

email (string): The updated email address of the contact.

phone (string): The updated phone number of the contact.

Response: The updated contact object.
### Delete a Contact
Endpoint: /api/contacts/<contact_id>/

Method: DELETE
#### Parameters:
contact_id (integer): The ID of the contact to delete.

Response: Status code indicating the success of the deletion.
### Mark a Contact as Favorite
Endpoint: /api/contacts/<contact_id>/favorite/

Method: POST
#### Parameters:
contact_id (integer): The ID of the contact to mark as favorite.

Response: The updated contact object with the favorite status.
## Error Handling
The API handles various error scenarios and returns appropriate status codes and error messages in the response.

## Conclusion
This Contact API provides secure authentication using JWT tokens and allows users to perform CRUD operations on their contacts, as well as mark contacts as favorites. It serves as a foundation for building more complex contact management systems or integrating contact functionalities into existing applications.




