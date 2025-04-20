# Digantara SRE Assessment

## 🚀 Objective

The goal of this project is to set up a self-hosted **Gitea** instance for Git repository management and **Grafana** for monitoring and visualization, with **Single Sign-On (SSO)** integration via **Authelia**. All services are routed through a reverse proxy (**Nginx**) for secure access and authentication.

---

## 🧱 Architecture

The system follows this architecture:

![SSO Architecture](./SSO%20Architecture.png)

### Components:

- **User**: Accesses services over the internet.
- **Nginx Reverse Proxy**: Handles incoming traffic and routes it to internal services.
- **Authelia**: Provides Single Sign-On (SSO) authentication for Gitea and Grafana.
- **Gitea**: A self-hosted Git service for source code management.
- **Grafana**: Visualization and monitoring platform.
- **Prometheus**: Collects and aggregates metrics.
- **Log Flow**: Gitea and Authelia logs are to be sent to Prometheus for future aggregation.
- **Grafana**: Uses Prometheus data for dashboards and monitoring.

---

## ⚙️ Prerequisites

Ensure Docker and Docker Compose are installed. Then:

1. Create a custom Docker bridge network:

   ```
   docker network create digantara
   ```
2. Clone the repository and navigate to the project directory:
    
    ```
    git clone https://github.com/sreehariskumar/Digantara_SRE_Assessment.git
    cd Digantara_SRE_Assessment
    ```
3. Run the containers:
    ```
    docker-compose up -d
    ```
