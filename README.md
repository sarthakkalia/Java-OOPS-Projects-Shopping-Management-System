# Shopping Management System - Java OOPs Based

This project is an **Online Shopping Management System** implemented in Java, utilizing Object-Oriented Programming (OOP) principles such as **abstraction**, **inheritance**, **polymorphism**, and **encapsulation**. The system also integrates **JDBC** for database interaction with **MySQL** to store and manage user and product information.

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [Future Enhancements](#future-enhancements)
- [Contributors](#contributors)

## Project Overview
The **Shopping Management System** allows users to register, log in, browse items, and manage their shopping carts, while administrators can manage the system by adding, removing, or updating items. This system is built using **Java**, and employs **OOP concepts** such as **abstraction** (using interfaces), **polymorphism** (method overloading and overriding), **inheritance** (class hierarchies), and **encapsulation** (hiding sensitive data using private attributes and accessors). 

The application uses **JDBC** to connect to a **MySQL** database for managing users, items, and shopping transactions.

## Features
- **User Registration and Login**: Customers can register and log in with unique credentials.
- **Admin Login**: Admins can log in to manage the store inventory and track user activities.
- **Browse Products**: Customers can browse items and add/remove them to/from the shopping cart.
- **Shopping Cart Management**: Customers can manage their cart and proceed with payments.
- **Abstraction & Polymorphism**: Leveraged to implement methods and enhance reusability and maintainability.
- **JDBC Integration**: Connects to a MySQL database for persistent storage of users and items.
- **Payment Handling**: Simulates payment functionality for completing purchases.

## Technologies Used
- **Java** (JDK 8 or higher)
- **MySQL** for database management
- **JDBC** for database connectivity
- **Scanner** for input handling
- **OOP Concepts**: Abstraction, Inheritance, Polymorphism, Encapsulation

## Installation

### 1. Clone the repository
```bash
git clone https://github.com/sarthakkalia/Java-OOPS-Projects-Shopping-Management-System.git
```

### 2. Install MySQL
Make sure you have MySQL installed and running on your machine. Create a database for the shopping management system.

### 3. Set up the MySQL database
- Create a MySQL database named `shop_db`.
- Import the necessary SQL tables (as described in the **Database Schema** section below).

```sql
CREATE DATABASE shop_db;
USE shop_db;
-- Create tables for users, admins, and products.
CREATE TABLE admin (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    mobno VARCHAR(15),
    username VARCHAR(100),
    password VARCHAR(100),
    UID VARCHAR(50)
);

CREATE TABLE user (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    mobno VARCHAR(15),
    username VARCHAR(100),
    password VARCHAR(100),
    UserUID VARCHAR(50),
    LastPayment DOUBLE DEFAULT 0,
    Wallet DOUBLE DEFAULT 0
);

CREATE TABLE items (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    price DOUBLE,
    stock INT
);
```

### 4. Update Database Configuration in Code
In your `src` folder, update the database connection URL, username, and password in the JDBC connection string:
```java
String url = "jdbc:mysql://localhost:3306/shopping_management";
String user = "your_mysql_username";
String password = "your_mysql_password";
```

### 5. Compile and Run the Application
Compile and run the project using any Java IDE (e.g., IntelliJ IDEA, Eclipse) or using the command line.

```bash
javac -d bin src/*.java
java -cp bin Shopping
```

## Project Structure

```
.
├── src
│   ├── shop
│   │   ├── Admin.java              # Admin functionalities (Adding/Removing products, etc.)
│   │   ├── Cart.java               # Cart functionalities for adding/removing items
│   │   ├── Items.java              # Item management (products)
│   │   ├── Payment.java            # Handles payment process
│   │   └── User.java               # User functionalities (registration, login, cart handling)
│   └── Shopping.java               # Main entry point of the system
├── .gitignore                      # Git ignore file
├── README.md                       # Project documentation
└── requirements.txt                # External libraries (if any)
```

## Usage

### Admin
1. Log in as an admin using the admin credentials.
2. Admins can add new items to the store, update item details, or remove items from the store.
3. Admins can also view customer details and their orders.

### Customer
1. Register as a new customer with a unique username.
2. Log in using your credentials.
3. Browse items, add items to your cart, and manage your cart.
4. Proceed to checkout and make a payment.

### Example Workflow
Upon starting the application, the user is greeted with options:
```plaintext
WELCOME TO ONLINE SHOPPING SYSTEM
---------------------------------
1 - REGISTER AS CUSTOMER
2 - LOGIN AS CUSTOMER
3 - LOGIN AS ADMIN
4 - EXIT
```

### Admin Example
Once logged in as an **Admin**, you can perform the following operations:

```java
System.out.println("1 - MANAGE PRODUCTS");  // Add, remove, or update products.
System.out.println("2 - ADD CUSTOMERS");  // Register new customers.
System.out.println("3 - VIEW CUSTOMERS");  // View a list of all customers.
System.out.println("4 - EDIT PROFILE");  // Edit your admin profile (name, mobile, password).
System.out.println("5 - ADD NEW ADMIN");  // Register a new admin.
System.out.println("6 - REMOVE CUSTOMERS");  // Delete a customer from the system.
System.out.println("7 - LOGOUT FROM SYSTEM");  // Exit the system.
```

### User Example
Once logged in as a **User**, you can perform the following operations:

```java
System.out.println("1 - VIEW GROCERIES LIST");  // Browse the list of available products.
System.out.println("2 - ADD PRODUCT TO CART");  // Add a selected product to the cart.
System.out.println("3 - REMOVE PRODUCT FROM CART");  // Remove a product from the cart.
System.out.println("4 - VIEW CART");  // View the contents of the shopping cart.
System.out.println("5 - PROCEED TO PAYMENT");  // Proceed to complete the purchase.
System.out.println("6 - EDIT PROFILE");  // Edit your user profile (name, mobile, password).
System.out.println("7 - LOGOUT FROM SYSTEM");  // Exit the system.
```

Each option allows the admin or user to interact with the system to manage products, customers, and the shopping experience.


## OOP Concepts

### 1. **Abstraction**
   - Abstracted the core functionalities of the system (like admin and user operations) into their respective classes, making the code modular and easy to manage.

### 2. **Polymorphism**
   - Overloading and overriding methods to handle various scenarios, especially during product management and cart operations.

### 3. **Encapsulation**
   - Ensured that sensitive information like user details are kept private within the class and exposed via getter and setter methods.

### 4. **Inheritance**
   - Admin and User classes extend base functionalities where applicable.

## Future Enhancements
- Integrate a payment gateway for real transactions.
- Enhance the user interface by developing a graphical front-end.
- Improve security by adding password encryption.
- Implement additional features like product reviews, discount coupons, etc.

## Contributors
- **Sarthak Kumar Kalia** - [LinkedIn](https://www.linkedin.com/in/sarthak-kalia/)
