# Secrets App

## Overview

The Secrets App is a Node.js application that allows users to securely register, log in, and submit their secrets. The application employs authentication mechanisms, including local and Google OAuth2, and uses PostgreSQL as the database for storing user credentials and secrets.

## Features

- User Registration and Login
- Local Authentication using email and password
- Google OAuth2 Authentication
- Secure storage of user secrets
- Ability for authenticated users to submit and view secrets

## Technologies Used

- Node.js
- Express.js
- PostgreSQL
- Passport.js (Local and Google OAuth2 strategies)
- Bcrypt (for password hashing)
- EJS (for templating)
- dotenv (for environment variable management)
- Express-Session (for session management)
- Body-Parser (for handling request bodies)

## Prerequisites

- Node.js installed
- PostgreSQL installed and running
- Google Developer account for OAuth2 setup
- `.env` file with the following environment variables:

```
SESSION_SECRET=your_session_secret
PG_USER=your_pg_user
PG_HOST=your_pg_host
PG_DATABASE=your_pg_database
PG_PASSWORD=your_pg_password
PG_PORT=your_pg_port
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
```

## Installation

1. Clone the repository:

```sh
git clone https://github.com/yourusername/secrets-app.git
cd secrets-app
```

2. Install the dependencies:

```sh
npm install
```

3. Set up the PostgreSQL database:

Create a database and a users table using the following SQL commands:

```sql
CREATE DATABASE secretsapp;
\c secretsapp

CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    email VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    secret TEXT
);
```

4. Create a `.env` file in the root directory and add the required environment variables.

5. Start the server:

```sh
npm start
```

The server will run on `http://localhost:3000`.

## Usage

1. Navigate to `http://localhost:3000` to access the home page.
2. Register a new account or log in with an existing account.
3. After logging in, submit your secret on the `/submit` page.
4. View submitted secrets on the `/secrets` page (only available to authenticated users).

## Project Structure

```
.
├── public
│   └── css
│       └── styles.css
├── views
│   ├── home.ejs
│   ├── login.ejs
│   ├── register.ejs
│   ├── secrets.ejs
│   └── submit.ejs
├── .env
├── app.js
└── package.json
```


## License

This project is licensed under the MIT License. See the LICENSE file for more details.
