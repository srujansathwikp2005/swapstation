# Battery Swapping Station Management System

## Overview

This is a full-stack web application for managing battery swapping stations, built with React on the frontend and Express.js on the backend. The system provides real-time monitoring, inventory management, and operational oversight for electric vehicle battery swapping networks.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query (React Query) for server state management
- **UI Framework**: Shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with custom design system
- **Build Tool**: Vite for development and bundling

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Database**: PostgreSQL via Neon serverless
- **ORM**: Drizzle ORM for type-safe database operations
- **Authentication**: Replit Auth with OpenID Connect
- **Session Management**: PostgreSQL-based session storage

## Key Components

### Database Schema
The system uses a PostgreSQL database with the following core entities:
- **Users**: Authentication and role management (admin/operator)
- **Stations**: Physical battery swapping locations with capacity and status tracking
- **Batteries**: Individual battery units with charge levels and location tracking
- **Swaps**: Transaction records of battery exchanges
- **Alerts**: System notifications and warnings
- **Operator Check-ins**: Staff activity tracking
- **QR Codes**: Digital identifiers for batteries and stations
- **Sessions**: Authentication session storage

### Frontend Structure
- **Pages**: Dashboard, Stations, Batteries, Swap History, Operators, QR Codes
- **Components**: Reusable UI components organized by feature
- **Hooks**: Custom hooks for authentication and mobile detection
- **Forms**: Validated forms using React Hook Form and Zod schemas

### Backend Structure
- **Routes**: RESTful API endpoints for CRUD operations
- **Storage Layer**: Abstracted database operations with TypeScript interfaces
- **Authentication Middleware**: Replit Auth integration with role-based access

## Data Flow

1. **Authentication**: Users authenticate via Replit Auth (OpenID Connect)
2. **Session Management**: Sessions stored in PostgreSQL with automatic cleanup
3. **API Communication**: Frontend communicates with backend via REST APIs
4. **Real-time Updates**: TanStack Query provides automatic data synchronization
5. **Form Validation**: Client and server-side validation using Zod schemas

## External Dependencies

### Core Framework Dependencies
- **@neondatabase/serverless**: Serverless PostgreSQL connection
- **drizzle-orm**: Type-safe ORM with PostgreSQL dialect
- **@tanstack/react-query**: Server state management
- **@radix-ui/***: Headless UI component primitives
- **react-hook-form**: Form state management and validation
- **zod**: Schema validation library

### Authentication
- **openid-client**: OpenID Connect client for Replit Auth
- **passport**: Authentication middleware
- **connect-pg-simple**: PostgreSQL session store

### Development Tools
- **Vite**: Build tool and development server
- **TypeScript**: Type checking and compilation
- **Tailwind CSS**: Utility-first CSS framework
- **ESBuild**: Fast JavaScript bundler for production

## Deployment Strategy

### Development Environment
- **Vite Dev Server**: Hot module replacement and fast development builds
- **Replit Integration**: Built-in support for Replit development environment
- **Environment Variables**: Database URL and session secrets via environment

### Production Build
- **Frontend**: Vite builds React app to static files
- **Backend**: ESBuild bundles Express server for Node.js runtime
- **Database**: PostgreSQL via Neon serverless with connection pooling
- **Static Assets**: Served from Express with Vite-built frontend

### Database Management
- **Migrations**: Drizzle Kit handles schema migrations
- **Connection Pooling**: Neon serverless WebSocket connections
- **Session Storage**: PostgreSQL table with automatic TTL cleanup

The application is designed as a monorepo with shared TypeScript schemas between frontend and backend, ensuring type safety across the entire stack. The authentication system integrates seamlessly with Replit's infrastructure while maintaining flexibility for other deployment environments.