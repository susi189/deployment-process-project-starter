## Architecture

![Architecture](./screenshots/Architecture.jpg)

The front and backend is running on AMS (Amazon Web Services).

### Web hosting

![s3](./screenshots/S3.png)

The application Udagram:

- Frontend build with Angular
- User registration and login is supported with Bcryptjs and JWT token
- User has the option to upload photos/create post.

This application is hosted on S3 (Simple Storage Service). For this purpose a Bucket (udagram4563728948) is created where all the files related to the frontend are stored. In case a user creates a post the files are upleaded here as well (currently this function is not available due to unresolved aws-sdk issues with JavaScript).

### Database

![database](./screenshots/db.png)

The database RDS (Relational Database Service). Is a PostgreSQl database, where user credentials and login infos are stored. Each time the user is trying to log in or register the server request/posts data to the database. The database is listening on PORT 5432.

### Server/Environment

![eb](./screenshots/EB.png)

The server is built with Node.js and Express.

The app is deployed with Elastic Beanstalk (EB), which allows this app to run on AWS cloud services. Through this deployment process an environment is created where the connection between EC2 (Elastic Compute Cloud) for server hosting and S3 is made.
