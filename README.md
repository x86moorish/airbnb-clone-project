# Airbnb Clone Project

## Team Roles

- **Backend Developer**:  
  Responsible for developing the server-side logic of the application, building RESTful APIs, integrating database models, and ensuring high performance and responsiveness.

- **Database Administrator (DBA)**:  
  Designs and manages the relational database system. Ensures data integrity, optimizes queries, and manages migrations, backups, and security of sensitive information.

- **DevOps Engineer**:  
  Sets up and maintains CI/CD pipelines, manages containerization (Docker), and ensures smooth deployment workflows across development, staging, and production environments.

- **Security Engineer**:  
  Implements key security measures like authentication, authorization, rate limiting, and data encryption to protect users, payments, and sensitive business logic.

- **Technical Writer**:  
  Documents the architecture, APIs, development workflows, database schemas, and team responsibilities to ensure clarity, maintainability, and project scalability.

---

## Technology Stack

- **Django**:  
  A high-level Python web framework used to build the server-side backend and develop RESTful APIs for the application.

- **MySQL**:  
  A powerful relational database management system (RDBMS) used to store structured data like users, properties, bookings, and reviews.

- **Docker**:  
  A containerization tool that packages the application and its dependencies into portable containers for consistent development and deployment.

- **GitHub Actions**:  
  A CI/CD tool used to automate workflows like testing, building, and deploying the application when changes are pushed to the repository.

- **GraphQL**:  
  A query language for APIs that can be used optionally for more efficient data fetching and updating, especially for complex relationships like properties and bookings.

---

## Database Design

### Entities and Key Fields:

- **User**:
  - `id`: Unique identifier
  - `username`: User's login name
  - `email`: User's email address
  - `password_hash`: Hashed password for security
  - `role`: Defines if the user is a guest, host, or admin

- **Property**:
  - `id`: Unique identifier
  - `owner_id`: Foreign key referencing User
  - `title`: Name of the property
  - `description`: Detailed information about the property
  - `price_per_night`: Cost to book per night

- **Booking**:
  - `id`: Unique identifier
  - `user_id`: Foreign key referencing User
  - `property_id`: Foreign key referencing Property
  - `start_date`: Start of the booking
  - `end_date`: End of the booking

- **Review**:
  - `id`: Unique identifier
  - `user_id`: Foreign key referencing User
  - `property_id`: Foreign key referencing Property
  - `rating`: Rating out of 5
  - `comment`: User feedback

- **Payment**:
  - `id`: Unique identifier
  - `booking_id`: Foreign key referencing Booking
  - `amount`: Payment amount
  - `payment_status`: Status of the transaction (e.g., completed, pending)

### Relationships:

- A **User** can have multiple **Properties**.
- A **Property** can have many **Bookings**.
- A **Booking** belongs to one **User** and one **Property**.
- A **Property** can have multiple **Reviews**.
- A **Payment** is linked to exactly one **Booking**.

---

## Feature Breakdown

- **User Management**:  
  Allows users to register, log in, manage profiles, and define roles (guest, host, admin). Essential for personalizing the user experience and securing access.

- **Property Management**:  
  Enables hosts to create, edit, and delete property listings. Crucial for allowing the platform to grow with diverse accommodation options.

- **Booking System**:  
  Lets users search for properties, book stays for specific dates, and manage reservations. Core functionality that drives platform engagement.

- **Review System**:  
  Permits users to leave feedback and ratings on properties they have stayed in. Builds trust and enhances decision-making for future guests.

- **Payment Integration**:  
  Handles secure payment processing for bookings. Ensures seamless transactions between guests and hosts, supporting business operations.

---

## API Security

- **Authentication**:  
  Verifies the identity of users using secure methods (e.g., JWT tokens). Crucial for protecting personal accounts and preventing unauthorized access.

- **Authorization**:  
  Ensures users only access resources they are permitted to (e.g., only hosts can manage properties). Critical for enforcing data ownership and privacy.

- **Rate Limiting**:  
  Limits the number of API requests per user/IP to prevent abuse (e.g., DDoS attacks). Protects server resources and ensures fair usage.

- **Data Validation and Sanitization**:  
  Validates incoming data and removes malicious inputs to prevent attacks like SQL injection or XSS.

- **Secure Payment Processing**:  
  Protects payment details using encryption and secure third-party services. Vital for maintaining trust and complying with legal standards (e.g., PCI-DSS).

---

## CI/CD Pipeline

- **What is CI/CD?**:  
  CI/CD stands for Continuous Integration and Continuous Deployment. It is a method where code changes are automatically tested, built, and deployed with minimal human intervention.

- **Importance for the Project**:  
  CI/CD ensures that new features and bug fixes are delivered quickly and reliably, reduces manual errors during deployment, and keeps the production environment stable.

- **Tools Used**:
  - **GitHub Actions**: Automates testing, building Docker images, and deploying the application on every push.
  - **Docker**: Ensures that the application runs consistently across development, testing, and production by using containers.

