# 🚀 Rocketseat Java Challenge: Courses API 📚

![Java](https://img.shields.io/badge/Java-21-007396?style=for-the-badge&logo=java)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.1.4-6DB33F?style=for-the-badge&logo=spring)
![Maven](https://img.shields.io/badge/Maven-4.0.0-C71A36?style=for-the-badge&logo=apache-maven)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

> 🌟 **A RESTful API for managing courses** as part of a Rocketseat challenge. Designed with clean architecture, modern Java practices, and Spring Boot—a powerful framework that boosts productivity and scalability.

---

## ⚡ Features
✅ **CRUD for Courses** (Create, Read, Update, Delete)  
✅ **Pagination and Dynamic Filtering** (e.g., by `name` or `category`)  
✅ **Toggle Course Status** (Activate/Deactivate using `PATCH`)  
✅ **Error Handling and Validation**  
✅ Fully versioned: `/api/v1`  
✅ 💼 **Enterprise-ready practices**: Logs, Exception Handlers, DTOs, and layers  

---

## 🎯 API Endpoints

🔗 **Base URL**: `/api/v1/cursos`

| HTTP Method | Endpoint                  | Description                        |
|-------------|---------------------------|------------------------------------|
| **POST**    | `/cursos`                 | Create a new course               |
| **GET**     | `/cursos`                 | List courses with pagination      |
| **GET**     | `/cursos/{id}`            | Retrieve a specific course by ID  |
| **PUT**     | `/cursos/{id}`            | Partially update course details   |
| **PATCH**   | `/cursos/{id}/active`     | Toggle course active status       |
| **DELETE**  | `/cursos/{id}`            | Delete a specific course          |

---

## 🗂️ System Architecture

Follows the **Controller → Service → Repository** layered architecture principle:  
- **Controller**: Handles HTTP requests and responses.  
- **Service**: Business logic layer.  
- **Repository**: Persistence layer using JPA.  

### 📋 Project Layers Overview
```text
src/
├── main/
│   ├── java/com/rocketseat/courses/
│   │       ├── controller/
│   │       ├── service/
│   │       ├── repository/
│   │       ├── dto/
│   │       ├── exception/
│   │       └── entity/
│   └── resources/
│           ├── application.properties
│           └── application-dev.properties
└── test/
```

---

## 🛠️ Tech Stack
🔧 **Core**  
- **Java 21 (LTS)**  
- **Spring Boot 3.1.4**  
- **Maven** for dependency management  

🛢️ **Database**  
- PostgreSQL  
- JPA / Hibernate  
- `@CreationTimestamp` and `@UpdateTimestamp` for automatic timestamps  

⚙️ **Tools & Utilities**  
- Docker Compose (for local setup)  
- SLF4J (logging)  
- Spring Validation (`@Valid`)  

---

## 🚧 Getting Started

### 🐘 Prerequisites
- Java 21 installed
- Maven 3.8+ installed
- PostgreSQL installed locally or via Docker

---

### 🚀 Running Locally
1. **Clone the repository**:
   ```bash
   git clone https://github.com/YOUR_GITHUB_USERNAME/rocketseat-java-courses-api.git
   cd rocketseat-java-courses-api
   ```

2. **Set up the database**:  
   Either manually configure PostgreSQL or use Docker Compose:
   ```bash
   docker-compose up -d
   ```

3. **Create application properties**:  
   Update `src/main/resources/application-dev.properties`:
   ```properties
   spring.datasource.url=jdbc:postgresql://localhost:5432/courses_db
   spring.datasource.username=postgres
   spring.datasource.password=secret
   spring.jpa.hibernate.ddl-auto=update

   # Logging level
   logging.level.org.springframework=INFO
   ```

4. **Build and run the project**:
   ```bash
   mvn clean install
   mvn spring-boot:run
   ```

---

## 🧪 Running Tests
To ensure the app works as expected, execute the following:
```bash
mvn test
```

- **Unit tests**: Validates Services with Mockito.  
- **Integration tests**: Confirms endpoint behavior with WebMvc.

---

## 📖 Documentation
This project includes **OpenAPI 3** documentation via Swagger.  
Access the Swagger UI after running the app:  
📚 `http://localhost:8080/swagger-ui/index.html`

---

## ⚙️ Key Design Decisions

- **Field Validation**: `@Valid`, `@NotBlank`, `@Size` ensure clean data inputs.  
- **Layered Architecture**: Centralized business rules in Services for maintainability.  
- **Global Exception Handling**: Consistent responses for all errors via `@ControllerAdvice`.  
- **Path Versioning**: `/api/v1`, preparing for backward compatibility.  

---

## 📊 Database Schema
```sql
CREATE TABLE courses (
    id UUID PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    category VARCHAR(100) NOT NULL,
    active BOOLEAN DEFAULT TRUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

## 📄 License
This project is licensed under the MIT License. See [LICENSE](./LICENSE) for details.

---

## 📞 Contact
<p>
  <a href="https://www.linkedin.com/in/pedro-solozabal/" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
  <a href="https://github.com/solozabal" target="_blank">
    <img src="https://img.shields.io/badge/GitHub-121212?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
  </a>
  <a href="https://t.me/pedrosolozabal" target="_blank">
    <img src="https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram" />
  </a>
</p>
