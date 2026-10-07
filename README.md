# 🚀 AI Global Disaster Coordination Platform

<div align="center">

![Status](https://img.shields.io/badge/status-active-success?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.109-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Gemini](https://img.shields.io/badge/Gemini-1.5_Flash-4285F4?style=for-the-badge&logo=google&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

**Multi-Agent AI System for Global Disaster Response & Coordination**

*6 specialized AI agents working together to save lives during disasters*

[Features](#-features) • [Architecture](#-architecture) • [Tech Stack](#-tech-stack) • [Setup](#-quick-start) • [API](#-api-endpoints) • [Screenshots](#-screenshots)

</div>

---

## 🌍 What Is This?

**AI Global Disaster Coordination Platform** is a multi-agent AI system that coordinates emergency response during disasters (earthquakes, floods, fires, hurricanes). When a disaster strikes, **6 specialized AI agents** powered by **Google Gemini** work in parallel to plan and execute the optimal response.

An **Orchestrator Agent** then merges all agent outputs into a single **master action plan** — including rescue deployment, drone surveillance, hospital allocation, weather forecasting, logistics routing, and public communication.

> 💡 **Built with CPU-friendly architecture** — all AI inference runs on Google Gemini's cloud API. No local GPU required.

---

## 🎯 The 6 AI Agents

| Agent | Icon | Responsibility |
|-------|------|----------------|
| **Rescue Agent** | 🚁 | Deploys rescue teams to high-priority hotspots based on severity |
| **Drone Agent** | 🛩️ | Plans surveillance flight paths & reconnaissance zones |
| **Hospital Agent** | 🏥 | Allocates nearest hospitals, beds, ambulances & medical staff |
| **Weather Agent** | 🌦️ | Predicts 24-hour weather risk & recommends safe windows |
| **Logistics Agent** | 📦 | Routes food, water, medicine, shelter kits to affected zones |
| **Communication Agent** | 📡 | Broadcasts public alerts via SMS, radio, social media |
| **Orchestrator** | 🧠 | Merges all agent outputs into a unified master plan |

---

## ✨ Features

### 🤖 Multi-Agent Intelligence
- **6 specialized agents** powered by Google Gemini 1.5 Flash
- **Parallel execution** — all agents run simultaneously for speed
- **Orchestrator pattern** — merges outputs into one master plan
- **Structured JSON outputs** — easy to render on frontend

### 🗺️ GIS & Live Mapping
- **Interactive map** with Leaflet + OpenStreetMap (no API key needed)
- **Real-time disaster markers** with severity color coding
- **Resource markers** (rescue teams, hospitals, drones, supply depots)
- **Heatmap layer** for disaster density visualization
- **Pulsing animations** on active disaster zones

### 🛰️ Satellite AI
- **Upload satellite images** → Gemini Vision analyzes damage
- **Damage classification**: None / Low / Moderate / Severe / Catastrophic
- **Auto-generated reports** with affected area estimates
- **Before/After comparison** support

### 📊 Real-Time Dashboard
- **WebSocket live updates** — agent status streams in real time
- **Live mission timeline** with connector lines
- **Severity charts** (Recharts) for analytics
- **Resource utilization** metrics
- **Communication feed** with priority badges

### 💾 Database
- **SQLite** — zero-config, lightweight, perfect for practice
- **8 tables**: disasters, agents, missions, resources, assignments, communications, satellite analyses, logs
- **Seeded demo data** for instant testing

### 🎨 Beautiful UI
- **Dark theme** with glassmorphism effects
- **Neon accents** (red emergency / amber warning / green safe)
- **Smooth animations** via Framer Motion
- **Fully responsive** — mobile, tablet, desktop

---

## 🏗️ Architecture




---

## 🛠️ Tech Stack

### Backend
- **FastAPI** — Modern async Python web framework
- **SQLAlchemy** — ORM for SQLite
- **Pydantic** — Data validation & settings
- **Google Generative AI** — Gemini 1.5 Flash for LLM + Vision
- **WebSockets** — Real-time agent status streaming
- **Uvicorn** — ASGI server

### Frontend
- **React 18** + **Vite** — Fast dev experience
- **TailwindCSS** — Utility-first styling
- **React Router** — Client-side routing
- **Leaflet** + **React-Leaflet** — Interactive maps
- **Recharts** — Charts & analytics
- **Framer Motion** — Smooth animations
- **Axios** — HTTP client
- **Lucide React** — Icon library
- **React Hot Toast** — Notifications

### Database
- **SQLite** — File-based, zero-config

---

## 📁 Project Structure



Full structure → [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md)

---

## 🚀 Quick Start

### Prerequisites
- Python 3.11+
- Node.js 20+
- Google Gemini API Key ([get free key](https://aistudio.google.com/app/apikey))
- Git

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/vishakha2121/ai-disaster-coordination-platform.git
cd ai-disaster-coordination-platform


cd backend
python -m venv venv

# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate

pip install -r requirements.txt

# Create .env file
echo "GEMINI_API_KEY=your_api_key_here" > .env
echo "DATABASE_URL=sqlite:///./data/disasters.db" >> .env

# Initialize & seed DB
python scripts/init_db.py
python scripts/seed_db.py

# Run server
python run.py