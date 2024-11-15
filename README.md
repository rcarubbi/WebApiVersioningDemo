# WebApiVersioningDemo

This project demonstrates implementing API versioning in ASP.NET Core Web API using Microsoft's API Versioning library.

## Overview

The WebApiVersioningDemo showcases how to set up and manage multiple API versions within an ASP.NET Core application. It includes examples of versioned controllers and demonstrates how to configure API versioning in the `Startup.cs` file.

## Features

- **API Versioning**: Implements versioning using Microsoft's API Versioning library.
- **Versioned Controllers**: Provides separate controllers for each API version.
- **Swagger Integration**: Configures Swagger to display and interact with different API versions.

## Getting Started

Follow these steps to run the project locally.

### Prerequisites

- [.NET SDK](https://dotnet.microsoft.com/download) (version 3.1 or later)
- [Visual Studio](https://visualstudio.microsoft.com/) or [Visual Studio Code](https://code.visualstudio.com/)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/rcarubbi/WebApiVersioningDemo.git
   ```

2. **Navigate to the project directory:**
   ```bash
   cd WebApiVersioningDemo/WebApiVersioningDemo
   ```

3. **Restore dependencies:**
   ```bash
   dotnet restore
   ```

4. **Build the project:**
   ```bash
   dotnet build
   ```

5. **Run the application:**
   ```bash
   dotnet run
   ```

## Usage

Once the application is running, you can access the API endpoints using a tool like [Postman](https://www.postman.com/) or a web browser.

### Available Endpoints

- **Version 1**: `GET /api/v1/values`
- **Version 2**: `GET /api/v2/values`

Each endpoint returns a simple list of values, demonstrating how different versions can coexist.

## API Versioning Configuration

The API versioning is configured in the `Startup.cs` file using the following code:

```csharp
services.AddApiVersioning(config =>
{
    config.DefaultApiVersion = new ApiVersion(1, 0);
    config.AssumeDefaultVersionWhenUnspecified = true;
    config.ReportApiVersions = true;
    config.ApiVersionReader = new HeaderApiVersionReader("x-api-version");
});
```

This configuration sets the default API version to 1.0, assumes the default version when none is specified, reports API versions in responses, and reads the API version from the `x-api-version` header.

## Swagger Integration

Swagger is configured to support multiple API versions. After running the application, navigate to `http://localhost:5000/swagger` to view the Swagger UI, which lists all available API versions and their endpoints.

## Contributing

Contributions are welcome. Feel free to open issues or submit pull requests to improve the project.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Microsoft API Versioning Library](https://github.com/microsoft/aspnet-api-versioning)
- [Swagger](https://swagger.io/)
