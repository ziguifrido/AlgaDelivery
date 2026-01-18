![GitHub](https://img.shields.io/github/license/ziguifrido/AlgaDelivery)
![GitHub top language](https://img.shields.io/github/languages/top/ziguifrido/AlgaDelivery)
![GitHub last commit](https://img.shields.io/github/last-commit/ziguifrido/AlgaDelivery)

# AlgaDelivery

This project is a microservices-based application for managing deliveries and couriers, developed with Java and Spring Boot.

## Overview

AlgaDelivery is a system for managing the entire delivery lifecycle, from creating deliveries and assigning them to couriers, to tracking their status until completion. It also includes a module for managing couriers and calculating their payments.

The project is divided into the following microservices:

- **Delivery-Tracking**: Manages the lifecycle of deliveries.
- **Courier-Management**: Manages courier information.
- **Gateway**: An API Gateway for the microservices.
- **Service-Registry**: A service registry for microservice discovery.

The project uses the following main technologies:

- Java / Spring Boot
- PostgreSQL
- Apache Kafka
- Docker

## How to Run

You need to have Docker and Docker Compose installed to run the application.

1.  **Start the infrastructure:**

    Use Docker Compose to start the necessary services (PostgreSQL, Kafka, etc.):

    ```bash
    docker-compose up -d
    ```

2.  **Run the microservices:**

    Navigate to the directory of each microservice (`Delivery-Tracking`, `Courier-Management`, `Gateway`, `Service-Registry`) and run the following command to start it:

    ```bash
    mvn spring-boot:run
    ```

## API Documentation

The API documentation is defined in the `open-api.yml` file. You can import it on a HTTP Client like Postman to test the APIs.

### Main Endpoints

#### Couriers

-   `POST /api/v1/couriers`: Create a new courier.
-   `GET /api/v1/couriers`: List couriers.
-   `GET /api/v1/couriers/{courierId}`: Get a courier by ID.
-   `PUT /api/v1/couriers/{courierId}`: Update a courier.
-   `POST /api/v1/couriers/payout-calculation`: Calculate payment for a courier.

#### Deliveries

-   `POST /api/v1/deliveries`: Create a new delivery.
-   `GET /api/v1/deliveries`: List deliveries.
-   `GET /api/v1/deliveries/{deliveryId}`: Get a delivery by ID.
-   `PUT /api/v1/deliveries/{deliveryId}`: Update a delivery.
-   `POST /api/v1/deliveries/{deliveryId}/placement`: Place a delivery for pickup.
-   `POST /api/v1/deliveries/{deliveryId}/pickups`: Register a delivery pickup.
-   `POST /api/v1/deliveries/{deliveryId}/completion`: Register the completion of a delivery.

## License 

MIT License
