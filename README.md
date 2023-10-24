# Spring Boot Microservices Project

This repository contains a suite of microservices developed with Spring Boot. Each microservice has a distinct role and can be run independently or in unison.
![My Image](https://github.com/slim20000/backend-microservices/blob/slim20000-patch-1/Blank%20board%20(1).png)

## Table of Contents

- [Microservices Overview](#microservices-overview)
- [Prerequisites](#prerequisites)
- [Setup & Running](#setup--running)
- [Databases](#databases)
- [Additional Notes](#additional-notes)

## Microservices Overview

### Core Services

- **API Gateway**: A gateway for routing requests to appropriate services.
- **Config Server**: Offers external configurations for the services. Ensure Gmail SMTP and Stripe API tokens are set correctly.
- **Discovery Server**: Facilitates service registration and discovery.

### Application Services

- **Candidate Service**: Handles candidate operations and communicates with **Application Service** using `RestTemplate`.
- **Application Service**: Manages general application features.
- **Article Service**: Looks after articles and related data.
- **Company Service**: Manages company data and operations.

- **Booking Service**: Responsible for booking operations and integrates with **Room**, **Availability**, and **Payment** services using `WebClient`.
  
- **Room Service**: Deals with room functionalities.
  
- **Availability Service**: Checks room availability.
  
- **Payment Service**: Manages payment operations.

### Auxiliary Services

- **Event Service**
- **Exchange Service**
- **Identity Service**

## Prerequisites

- Java 8 or newer
- Maven
- IntelliJ IDEA
- Docker
- MongoDB & MySQL databases

## Setup & Running

### IntelliJ IDEA

1. **Clone the Repository**:
    ```
    git clone [repository_url]
    ```

2. **Open in IntelliJ IDEA**:
   - Launch IntelliJ IDEA.
   - Navigate to `File` > `Open` and select the cloned directory.

3. **Run Services**:
   - In IntelliJ, navigate to the desired service's directory.
   - Right-click on the `pom.xml` file and select `Run`.

### Docker

For Docker users:

```bash
docker build -t [service_name] ./[service_directory]
docker run -p [port]:[port] [service_name]

## Databases

- **MongoDB**: Utilized by specific services for document-oriented storage. Ensure MongoDB is active and accessible.
  
- **MySQL**: Employed for relational data management. Confirm that the MySQL server is operational and can be connected to.

## Additional Notes

- It's crucial to initiate the `configserver` and `discoveryserver` prior to other services.
- Thoroughly inspect Gmail SMTP settings and Stripe API tokens within the `configserver`.
- Database-related configurations should be accurately established in either the `configserver` or the respective service's configuration files.

