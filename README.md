# Flight Booking System

A full-stack flight-booking application with an ASP.NET Core Web API and a React frontend. The repository contains the API, booking and payment workflows, and the web client.

## What it covers

- Flight, route, airport, airline, aircraft, and seat data management.
- Account endpoints with JWT bearer authentication and authorization.
- Booking, seat selection, checkout validation, and checkout creation workflows.
- Payment simulation and payment-finalization services.
- A dashboard API and public-facing endpoints.
- Swagger/OpenAPI support for exploring the API during development.

## Technology

| Layer | Technologies |
|---|---|
| Backend | ASP.NET Core 8, C#, Entity Framework Core |
| Database | SQLite |
| Authentication | JWT Bearer |
| API documentation | Swagger / OpenAPI |
| Frontend | React 19, Vite, JavaScript |
| Frontend networking and routing | Axios, React Router |

## Repository structure

```text
FlightBookingSystem.Web/   ASP.NET Core API, controllers, data and services
flight-booking-frontend/   React + Vite web application
FlightBookingSystem.sln    .NET solution
```

## Run locally

### Prerequisites

- .NET 8 SDK
- Node.js and npm

### 1. Configure the backend

Configure these settings locally before starting the API:

- `ConnectionStrings:DefaultConnection`
- `Jwt:Key`
- `Jwt:Issuer`
- `Jwt:Audience`

Use .NET User Secrets or another local configuration source for sensitive values. Do not commit credentials, signing keys, or production connection strings.

Restore and run the API:

```powershell
cd FlightBookingSystem.Web
dotnet restore
dotnet run
```

Swagger/OpenAPI is enabled when the application runs in the Development environment.

### 2. Run the frontend

In a separate terminal:

```powershell
cd flight-booking-frontend
npm install
npm run dev
```

The Vite development server is configured for the local API integration. The API CORS policy currently allows the local frontend origins configured in `Program.cs`.

## Notes

- Payment-related services in this repository include simulation and finalization workflows; this README does not claim a live payment-gateway integration.
- No public deployment or demo URL is documented in the repository.
- Source code and local configuration are the implementation references. Keep secrets and local environment files out of version control.
