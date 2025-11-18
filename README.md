# Job Portal

A full-stack MERN application designed to connect job seekers with recruiters. Users can search for jobs, apply, and manage their applications, while companies can post and manage job listings and review applicants.

## Features

### For Job Seekers
- **User Authentication**: Secure sign-up and login using Clerk.
- **Job Search & Filtering**: Browse, search, and filter jobs by title, location, and category.
- **Apply for Jobs**: Easily apply for jobs with an uploaded resume.
- **Resume Management**: Upload and update PDF resumes.
- **Application Tracking**: View the status of all submitted job applications (Pending, Accepted, Rejected).

### For Recruiters
- **Company Authentication**: Secure registration and JWT-based login for companies.
- **Post Jobs**: A rich-text editor to create and post detailed job descriptions.
- **Manage Jobs**: View all posted jobs, see the number of applicants, and toggle job visibility.
- **Review Applicants**: View a list of applicants for each job, download their resumes, and change their application status.

---

## Tech Stack

- **Frontend**: React, Vite, Tailwind CSS
- **Backend**: Node.js, Express.js
- **Database**: MongoDB, Mongoose
- **Authentication**: Clerk (for users), JSON Web Tokens (JWT) (for companies)
- **File Storage**: Cloudinary (for resumes and company logos)
- **Deployment**: Vercel

---

## Getting Started

### Prerequisites

- Node.js and npm
- MongoDB URI
- Cloudinary Account
- Clerk Account

### Installation

1.  **Clone the repository:**
    ```sh
    git clone <repository-url>
    cd job-portal
    ```

2.  **Install server dependencies:**
    ```sh
    cd server
    npm install
    ```

3.  **Install client dependencies:**
    ```sh
    cd ../client
    npm install
    ```

4.  **Set up environment variables:**

    Create a `.env` file in the `server` directory and add the following:
    ```env
    # filepath: server/.env
    JWT_SECRET="your_jwt_secret"
    MONGODB_URI="your_mongodb_uri"
    CLOUDINARY_NAME="your_cloudinary_name"
    CLOUDINARY_API_KEY="your_cloudinary_api_key"
    CLOUDINARY_SECRET_KEY="your_cloudinary_secret_key"
    CLERK_WEBHOOK_SECRET="your_clerk_webhook_secret"
    ```

    Create a `.env` file in the `client` directory and add the following:
    ```env
    # filepath: client/.env
    VITE_CLERK_PUBLISHABLE_KEY="your_clerk_publishable_key"
    VITE_BACKEND_URL="http://localhost:5000"
    ```

5.  **Run the application:**

    - **Start the backend server:**
      ```sh
      # From the /server directory
      npm run server
      ```
    - **Start the frontend client:**
      ```sh
      # From the /client directory
      npm run dev
      ```

The client will be running on `http://localhost:5173` and the server on `http://localhost:5000`.

---

## API Endpoints

The server exposes the following REST API endpoints:

-   `/api/users`: Routes for user data, job applications, and resume updates.
-   `/api/jobs`: Routes to get all jobs and a single job by its ID.
-   `/api/company`: Routes for company registration, login, job posting, and applicant management.
-   `/webhooks`: Webhook endpoint for Clerk to sync user data with the database.
