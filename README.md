# DemoApp

A full-stack application consisting of a React client, Node.js server, and PostgreSQL database.

## Project Structure

The project is organized into three main components:

- `react-client/`: Frontend React application (submodule)
- `react-server/`: Backend Node.js server (submodule)
- `db/`: Database initialization scripts

## Prerequisites

Before you begin, ensure you have the following installed:

- Docker and Docker Compose
- Git

## Getting Started

### Using Docker (Recommended)

1. Clone the repository with submodules:

   ```bash
   # Clone the main repository
   git clone https://github.com/sekharkasi/demoApp.git
   cd demoApp

   # Initialize and update submodules
   git submodule init
   git submodule update
   ```

2. Start the application using Docker Compose:
   ```bash
   docker-compose up --build
   ```

This will automatically:

- Start the React client on http://localhost:3000
- Start the Node.js server on http://localhost:19200
- Set up and start PostgreSQL database on port 5433
- Initialize the database with the required schema

### Troubleshooting

If you encounter issues with submodules:

1. Verify submodule status:

   ```bash
   git submodule status
   ```

2. If submodules are not properly initialized:

   ```bash
   git submodule init
   git submodule update
   ```

3. If you still have issues, try:
   ```bash
   git submodule update --init --recursive
   ```

### Manual Setup (Development)

If you prefer to run the services individually for development:

1. Set up the server:

   ```bash
   cd react-server
   npm install
   # Create .env file with necessary environment variables
   npm start
   ```

2. Set up the client:
   ```bash
   cd react-client
   npm install
   npm start
   ```

Note: For manual setup, you'll need to set up your own PostgreSQL database and configure the environment variables accordingly.

## Environment Variables

The server requires the following environment variables (already configured in docker-compose.yml):

- `DB_HOST`: Database host (default: db)
- `DB_PORT`: Database port (default: 5432)
- `DB_USER`: Database username (default: postgres)
- `DB_PASSWORD`: Database password (default: postgres)
- `DB_NAME`: Database name (default: demoapp)
- `PORT`: Server port (default: 19200)
- `NODE_ENV`: Environment (development/production)

## Repository Structure

This project uses Git submodules to manage the client and server components:

- `react-client`: [https://github.com/sekharkasi/react-client.git](https://github.com/sekharkasi/react-client.git)
- `react-server`: [https://github.com/sekharkasi/react-server.git](https://github.com/sekharkasi/react-server.git)

Each submodule is maintained in its own repository, allowing for independent version control and development.
