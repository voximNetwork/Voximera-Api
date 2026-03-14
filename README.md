📦 Backend — Voxim Flow API

A scalable backend powering Voxim Flow, a programmable financial coordination protocol built on the Stellar ecosystem.

This service orchestrates escrow agreements, DAO treasury management, decentralized identity, payment coordination, and AI-powered financial insights.

🏗 Architecture Overview

The backend acts as the coordination layer between:

Stellar blockchain

Soroban smart contracts

Web & mobile clients

AI intelligence services

It handles:

Smart contract event indexing

Agreement lifecycle management

DAO governance workflows

Payment orchestration

Reputation computation

AI assistance services

⚙️ Tech Stack
Component	Technology
Framework	NestJS
Language	TypeScript
Database	PostgreSQL
Queue	BullMQ
Cache	Redis
Auth	JWT
Blockchain	Stellar SDK
Smart Contracts	Soroban
AI Layer	OpenAI / LLM APIs
Realtime	WebSockets
📁 Project Structure
apps/api/

src/
│
├── modules/
│   ├── auth/
│   ├── users/
│   ├── escrow/
│   ├── payments/
│   ├── dao/
│   ├── identity/
│   ├── reputation/
│   ├── ai/
│   └── notifications/
│
├── blockchain/
│   ├── stellar.service.ts
│   ├── soroban.listener.ts
│   └── contract.service.ts
│
├── queues/
│   ├── payment.processor.ts
│   ├── escrow.processor.ts
│   └── reputation.processor.ts
│
├── common/
│   ├── guards/
│   ├── interceptors/
│   └── decorators/
│
└── main.ts
🔑 Core Modules
Authentication

Provides secure API access.

Features:

JWT authentication

Wallet signature verification

Refresh tokens

Role-based access

Endpoints:

POST /auth/login
POST /auth/verify-wallet
POST /auth/refresh
💰 Escrow Engine

Manages programmable escrow agreements backed by Soroban smart contracts.

Capabilities:

Agreement creation

Milestone tracking

Automated release

Dispute workflow

Event synchronization

Example Flow:

User creates escrow

Contract deployed

Funds locked

Milestones verified

Funds released

Endpoints:

POST /escrow/create
GET /escrow/:id
POST /escrow/release
POST /escrow/dispute
💸 Payment Infrastructure

Handles cross-border payments using Stellar path payments.

Features:

XLM payments

Stablecoin support

FX conversion

QR payments

Payment links

Endpoints:

POST /payments/send
POST /payments/path
GET /payments/history
🏛 DAO Treasury

Enables decentralized governance and treasury disbursement.

Capabilities:

Proposal creation

On-chain voting

Treasury payouts

Grant automation

Endpoints:

POST /dao/proposal
POST /dao/vote
GET /dao/proposals
POST /dao/execute
🆔 Decentralized Identity (VoxID)

Manages on-chain identity NFTs and reputation scores.

Features:

Identity minting

Badge system

Transaction reputation

Trust score computation

Endpoints:

POST /identity/create
GET /identity/:address
POST /identity/badge
🤖 AI Assistant

Provides contextual financial guidance.

Capabilities:

Contract explanation

Risk analysis

Agreement generation

Portfolio summaries

Endpoints:

POST /ai/explain-contract
POST /ai/analyze-risk
POST /ai/generate-agreement
🔗 Blockchain Integration

The backend listens to Soroban events.

Events tracked:

EscrowCreated

EscrowReleased

ProposalCreated

VoteCast

IdentityMinted

Listener Service:

soroban.listener.ts

This service:

Subscribes to contract events

Updates backend state

Triggers workflows

⚡ Queue System

Background jobs are handled via BullMQ.

Queues include:

escrow-processing

payment-settlement

reputation-updates

notifications

Benefits:

High scalability

Retry logic

async workflows

🔐 Security Model

The backend enforces:

Non-custodial wallet architecture

JWT authentication

Role permissions

Smart contract validation

Rate limiting

Sensitive operations require:

Wallet signature

Multi-sig validation

🚀 Local Development
Install dependencies
npm install
Start services
docker-compose up

Includes:

PostgreSQL

Redis

Run backend
npm run start:dev

Server runs on:

http://localhost:4000
📊 Environment Variables
DATABASE_URL=
REDIS_HOST=
REDIS_PORT=
JWT_SECRET=
STELLAR_NETWORK=testnet
STELLAR_RPC_URL=
OPENAI_API_KEY=
🧪 Testing
npm run test
npm run test:e2e
📈 Future Improvements

GraphQL API

Event sourcing

zk identity proofs

Cross-chain settlement

ML-based fraud detection

📜 License
MIT License
