# REST API Basics

the app is applied django rest-framework
the stranth point :

- authentication
- view posts
- create, update , retrive , delete (CRUD)
- used some mixin inside of classes
- visual API is the most usefull benifit

# the endpoints are in local host

    http://127.0.0.1:8000/api/postings // this for list and view
    http://127.0.0.1:8000/api/postings/(?P<pk>\d+) // this is for CRUD oprations like this http://127.0.0.1:8000/api/postings/1

# for deployment you have to use djanog-host for rubust uri and fetching and posting data to the server

### Software

thank for :

- Django 1.11.8 (https://kirr.co/hjogvt)
- Python 3.6.3 (https://kirr.co/ftq97z)
- Django Rest Framework 3.7.3 (https://kirr.co/svez0s)
- Django Rest Framework JWT 1.11.0 (https://kirr.co/vpibmo)

### Initial Setup

```
virtualenv -p python3 restapi-basics

# activate it
# mac: `source bin/activate`
# windows: `.\Scripts\activate`

$pip install django==1.11.8 djangorestframework==3.7.3 djangorestframework-jwt==1.11.0

### Or you can do $pip install -r requirments.txt --user

mkdir src && cd src

django-admin startproject cfehome .
django-admin startapp postings
```

### Update your settings to reflect the following:

```
INSTALLED_APPS = [
    ...
    'rest_framework',
    'postings'
]



REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': (
        'rest_framework.permissions.IsAuthenticated',
    ),
    'DEFAULT_AUTHENTICATION_CLASSES': (
        'rest_framework_jwt.authentication.JSONWebTokenAuthentication',
        'rest_framework.authentication.SessionAuthentication',
        'rest_framework.authentication.BasicAuthentication',
    ),
}
```
