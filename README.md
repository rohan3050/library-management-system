Library Management System
Installation
To run the app flawlessly, satisfy the requirements

pip install -r requirements.txt
Set Environment Variables
Replace .env.example with .env file and update the environment vaiables.

FLASK_APP=app.py
FLASK_ENV=development
FLASK_DEBUG=True

# DB info
MYSQL_HOST=localhost
MYSQL_USER=root
MYSQL_PASSWORD=
MYSQL_DB=lms
Note: If you update the MYSQL_DB variable, remember to also update the corresponding value in the docker-compose.yaml file to ensure consistency when using Docker. There's an exceptioin for MYSQL_HOST which should set set within docker-compose.yaml file explicitly.

To setup a mail server you can set the below variable in .env file.

# SMTP credentials
MAIL_SERVER=smtp.gmail.com
MAIL_PORT=587 
MAIL_USERNAME=
MAIL_PASSWORD=
MAIL_USE_TLS=True
MAIL_USE_SSL=
MAIL_DEBUG=1
MAIL_DEFAULT_SENDER=sender@domain.com
I'm using Flask-Mail for managing emails. For more information, visit https://flask-mail.readthedocs.io/en/latest/

Setup Datbase
Export lms.sql database from within db directory using Phpmyadmin or terminal:

mysql -u <username> -p <password> lms < lms.sql
Start Server
flask run
Or run this command

python -m flask run
Debugging
Start flask with auto reload on code change

flask run --reload
