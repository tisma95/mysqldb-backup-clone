# Mysql Database Clone or Backup

## Author

**Name**: Ismaël Maurice

**Github**: https://github.com/tisma95

**Email**: ismael.tuo@edigrp.com <br>

## Description

This repository goal is to permits to execute the following action on MySQL/Maria instance of users its permits the following actions:

+ permit to clone one or all of its databases from one host to another host
+ permit to backup in location one or all user databases
+ permit to restore from location one or all user databases

**WARNING:**
You should specific the full path of folder not only relative path and should be sure that user has access to folder and database.
You should use the user with only read access to host databases.

## Requirement

Before starting the project you need to install on your computer the following packages:

[Python >=3.9](https://www.python.org/downloads/)

[MySQL Command Line](https://dev.mysql.com/downloads/mysql/) is required if you want to backup inside the folder

[MySQL Shell](https://dev.mysql.com/downloads/installer/) is required if you want to read the database

Create the user with access minimun in read to host database.

## Started

Run the commands inside the folder:

1. If no **env** folder exists init the environment else skip this step
```cmd
    python -m venv env
```
or
```cmd
    python3 -m venv env
```
or for ubuntu
```cmd
    virtualenv venv
```

```node
    If any problem follow this page to fix and intall virutalenv: https://gist.github.com/frfahim/73c0fad6350332cef7a653bcd762f08d
```

2. If the env folder already exists, run the following command to activate it
```cmd
    source env/bin/activate
```
or for windows
```cmd
    env\Scripts\activate.bat
```

3. Run the installation of package via following command
```cmd
    pip install -r requirements.txt
```

4. Run the script with command `python main.py` or `python3 main.py`

## Environment variables ##

Create the file **.env** inside folder with following example variable

```yaml
# Add the host source here where the database to backup are located
HOST_SRC = example.com
# Add the port of host source the def
PORT_SRC = 3306
# Add the host source user
USER_SRC = root
# Add the host source password
PASSWORD_SRC = root
# Database folder => the folder where to save the database or where the database to restore are located example /home/toto or C:\users\toto for windows
FOLDER = /home/toto
# Add the host destination here where the database should be clone (src host db will be clone) or backup (the db file of folder will be located here)
HOST_DST = example.com
# Add the port of host destination
PORT_DST = 3306
# Add the host destination user
USER_DST = root
# Add the host destination password
USER_DST = root
```

**INFORATION:**

If you want to backup the database in folder you should specify:

    - HOST_SRC
    - PORT_SRC
    - USER_SRC
    - PASSWORD_SRC
    - FOLDER


If you want to clone the database from one host to another you should specify:


    - HOST_SRC
    - PORT_SRC
    - USER_SRC
    - PASSWORD_SRC
    - HOST_DST
    - PORT_DST
    - USER_DST
    - USER_DST


If you want to backup the folder database inside the host you should specify:

    - FOLDER
    - HOST_DST
    - PORT_DST
    - USER_DST
    - USER_DST

## Other informations

+ If new package is install we can update the **requirements.txt** with command `pip freeze > requirements.txt` or `python3 -m pip freeze > requirements.txt`

+ Exit the env via: `deactivate` or for windows `env\Scripts\activate.bat`

## Useful packages

[python-dotenv Documentation](https://pypi.org/project/python-dotenv/)
