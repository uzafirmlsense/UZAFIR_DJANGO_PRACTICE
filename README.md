# transactions-categorization
# API and React App for Transaction Categorization Dashboard Project
This is the web app for the Transaction Categorization Dashboard project.


# Some Coding Practices to Follow
Please try to ensure these standards whenever you are coding in Python.

- Module and file names should follow [snake casing](https://en.wikipedia.org/wiki/Snake_case).
- All variable and function names should also follow snake casing.
- Class names should follow [Pascal case](https://www.theserverside.com/definition/Pascal-case).
- Global variables or constants should be in all caps.

IMPORTANT: Please be vary of accidently pushing any credentials/secrets in the repo.


# Deployment
We are currenlty not using any deployment but will be deployed using github actions. 

### CAUTION: Before deploying, make sure you have ```DEBUG=False``` in the .env file.

1) Do a fresh build of the frontend by running 
   ```
   npm install
   npm run build
   ```
   inside the 'frontend' folder.


2) To deploy the app to App Engine, just push to master (coming soon)

3) If you see any permission errors, contact the project lead.

# Local Development Setup

1) After cloning the repo, create a virtual env by running this in the root directory:
   
   ```
   python -m venv .venv
   ```

2) Activate the virtual venv either by opening up a new terminal in VSCode (it will automatically activate) or run:
   
   ```
   .venv\\Scripts\\activate
   ```
   
   (change with forward-slash for linux)

3) Install dependencies:
   
   ```
   pip install -r requirements.txt
   ```
   
   Follow the guidelines in the other Transaction Categorization repos for installing our private packages.

4) SKIP: Place the ```.env``` file in the root directory (if you don't have this file, ask the repo owner)
   
   The .env file also has settings for the production Cloud SQL database. If you want to use that database, create a new variable named ```GAE_APPLICATION``` in the .env file and assign it the value 1 or True. Then in the ```DB_PORT``` variable, use the port number that the cloud_sql_proxy is listening on. [Here's](https://cloud.google.com/sql/docs/mysql/connect-instance-auth-proxy) some help on cloud_sql_proxy and how to connect to the remote database. 

6) Change into the ```frontend``` folder and run the following (suggest you do this in a separate terminal):
   ```
   npm install
   npm run build
   ```
7) Now run these in the root:
   ```
   python manage.py makemigrations
   python manage.py migrate
   ```
8) Finally run the server with:
   
   ```python manage.py runserver```

