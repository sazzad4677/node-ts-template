# Node TypeScript Boilerplate

A modern and minimalistic boilerplate for Node.js applications using TypeScript. This template is designed to provide a solid foundation for building scalable backend applications.

---

## Features

- **Express Framework**: Lightweight and flexible web framework.
- **TypeScript**: Strongly typed JavaScript for better code quality and scalability.
- **Environment Configuration**: Built-in support for `.env` files using `dotenv`.
- **Linting and Formatting**: Integrated ESLint and Prettier for code consistency.
- **Hot Reloading**: Development-friendly with `ts-node-dev`.
- **MongoDB Integration**: `mongoose` for database interaction.
- **Production-Ready**: Easy-to-build scripts for deployment.
- **Modular Structure**: Organized and scalable code with a modular architecture.

---

## Getting Started

### Prerequisites

- **Node.js**: Version 16+ required.
- **Yarn**: Preferred package manager (optional but recommended).

### Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/sazzad4677/node-ts-template.git
   cd node-ts-template
   ```

2. **Install dependencies:**

   ```bash
   yarn install
   # or
   npm install
   ```

3. **Set up environment variables:**

   Create a `.env` file in the root of your project based on `.env.example`. Replace `<UserName>`, `<Password>`, and `<DatabaseName>` with your actual database credentials:

   ```env
   PORT=3000
   MONGO_URI=mongodb+srv://<UserName>:<Password>@cluster0.vwiqv.mongodb.net/<DatabaseName>?retryWrites=true&w=majority
   ```

4. **Run the application:**

   - Development mode (with hot reloading):

     ```bash
     yarn start-dev
     ```

   - Production mode:

     ```bash
     yarn start-prod
     ```

---

## Project Structure

```plaintext
node-typescript-boilerplate/
├── dist/                # Compiled output (generated during build)
├── node_modules/        # Dependencies
├── src/                 # Source files
│   ├── app/
│   │   ├── config/       # Configuration files
│   │   ├── modules/      # Modularized features or routes
│   │   │   └── example/  # Example module
│   │   │       ├── example.controller.ts   # Handles HTTP requests and responses
│   │   │       ├── example.interfaces.ts   # TypeScript interfaces for the module
│   │   │       ├── example.model.ts        # Database schema and model
│   │   │       ├── example.route.ts        # Defines API routes for the module
│   │   │       └── example.service.ts      # Business logic for the module
│   │   └── app.ts        # Main application setup
│   ├── server.ts        # Entry point
├── .env                 # Environment variables
├── .gitignore           # Ignored files for Git
├── .prettierrc          # Prettier configuration
├── eslint.config.mjs    # ESLint configuration
├── tsconfig.json        # TypeScript configuration
├── package.json         # Project metadata and scripts
├── yarn.lock            # Dependency lock file
```

---

## Modular Architecture

This boilerplate uses a modular structure to organize code. Each module encapsulates related functionality, making the application easy to scale and maintain.

### Example Module

Each module follows this structure:

```plaintext
src/app/modules/<module-name>/
├── <module-name>.controller.ts   # Handles HTTP requests and responses
├── <module-name>.interfaces.ts   # TypeScript interfaces or types for the module
├── <module-name>.model.ts        # Database schema and interactions
├── <module-name>.route.ts        # Defines and exports the module's API routes
├── <module-name>.service.ts      # Business logic for the module
```

### Adding a New Module

1. Create a new folder in `src/app/modules/` with your module's name.
2. Add the required files (`controller`, `service`, `model`, `route`, and `interfaces`).
3. Register the module in `app.ts` or `server.ts` by importing its routes.

Example route registration in `server.ts`:

```typescript
import exampleRoutes from './app/modules/example/example.route';

app.use('/api/example', exampleRoutes);
```

---

## Available Scripts

- **`yarn start-dev`**: Start the app in development mode with hot reloading.
- **`yarn start-prod`**: Run the compiled app in production mode.
- **`yarn format`**: Format the code using Prettier.
- **`yarn lint`**: Check for linting errors using ESLint.
- **`yarn lint:fix`**: Fix linting issues automatically.

---

## Dependencies

### Core Dependencies

- **Express**: Web framework for building APIs.
- **Mongoose**: ODM for MongoDB.
- **dotenv**: Environment variable management.
- **cors**: Enable cross-origin requests.

### Development Dependencies

- **TypeScript**: Type-safe JavaScript.
- **ts-node-dev**: Hot reloading for development.
- **ESLint**: Static code analysis.
- **Prettier**: Code formatter.

---

## Contributing

Contributions are welcome! Please fork this repository, create a feature branch, and submit a pull request.

---

## License

This project is licensed under the [ISC License](LICENSE).

---