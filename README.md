AI-Powered Fitness Microservices Platform
Overview
This is a comprehensive full-stack microservices application designed to track user fitness activities and provide AI-driven insights using Google Gemini. The system utilizes a modern event-driven architecture with Apache Kafka and follows Clean Architecture principles to ensure scalability and maintainability.

Architecture Diagram
Core Features
User Management: Secure user registration and profile management using Supabase (PostgreSQL).

Activity Tracking: Real-time logging of fitness activities (running, cycling, etc.) stored in MongoDB Atlas.

AI Insights: Asynchronous processing of activity data via Kafka to generate personalized fitness coaching via Google Gemini API.

Service Discovery: Dynamic service registration and health monitoring with Netflix Eureka.

API Gateway: Centralized entry point for the frontend, handling routing and cross-origin (CORS) policies.

Cloud-Native Integration: Fully integrated with cloud-managed services (Aiven Kafka, MongoDB Atlas, Supabase) to eliminate local infrastructure dependencies.

Tech Stack
Backend (Java / Spring Boot)
Spring Cloud Gateway: Centralized routing.

Spring Cloud Eureka: Service discovery.

Spring Data JPA & MongoDB: Polyglot persistence.

Spring Kafka: Event-driven communication.

Frontend (React)
Vite: Fast build tool and development server.

Axios: HTTP client for API communication.

Tailwind CSS: Responsive and modern UI styling.

Infrastructure & Security
Apache Kafka (Aiven): Managed serverless messaging.

MongoDB Atlas: Managed NoSQL database.

Supabase: Managed PostgreSQL database.

Google Gemini API: Generative AI for fitness insights.

SSL/mTLS: Secure communication with Kafka using JKS keystores.

fitness-microservices/
├── backend/                  # Spring Boot Services
│   ├── activity-service/     # Activity logging & MongoDB integration
│   ├── ai-service/           # Kafka consumer & Gemini AI integration
│   ├── gateway-service/      # API Gateway (Port: 8080)
│   ├── eureka-server/        # Discovery Server (Port: 8761)
│   └── user-service/         # User profiles & Supabase integration
├── frontend/                 # React (Vite) Application
└── certs/                    # SSL Certificates for Aiven Kafka (Ignored by Git)