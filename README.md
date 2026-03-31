# QuickHire Platform

QuickHire is a freelancer marketplace platform that connects clients with freelancers. It allows clients to post jobs, freelancers to apply, and manages file uploads such as resumes and logos.

## Architecture

This is a microservices-based platform built with Spring Boot and Spring Cloud.
```
quickhire-main/
├── platform/          # Infrastructure services
│   ├── config-server  # Centralized configuration server
│   ├── eureka-server  # Service discovery
│   └── api-gateway    # API Gateway and routing
├── services/          # Business services
│   ├── user-service   # Client and freelancer management
│   ├── job-service    # Job posting management
│   └── file-service   # Resume and logo file management
├── quickhire-frontend # React frontend
└── uploads/           # Local file storage
```

## Tech Stack

- **Backend:** Java 25, Spring Boot 4, Spring Cloud
- **Frontend:** React 19, Vite, React Router
- **Databases:** PostgreSQL (users), MongoDB (jobs)
- **Infrastructure:** Google Cloud Platform, Cloud Run, Cloud SQL
- **Service Discovery:** Netflix Eureka
- **Configuration:** Spring Cloud Config Server (GitHub backed)
- **API Gateway:** Spring Cloud Gateway

## Getting Started

### Prerequisites
- Java 25
- Maven
- Node.js 22
- Docker (optional)

### Build Platform Services
```bash
cd platform
mvn clean package
```

### Build Business Services
```bash
cd services
mvn clean package
```

### Run Frontend
```bash
cd quickhire-frontend
npm install
npm run dev
```

## Deployment

Services are deployed on Google Cloud Platform using PM2 for process management.

### Start Order
1. Config Server (port 9000)
2. Eureka Server (port 8761)
3. API Gateway (port 8080)
4. Business Services (user: 8081, job: 8082, file: 8083)
