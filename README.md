# Excali Draw | Collaborative Whiteboard

A browser-based digital whiteboard built with **React** and the **ZEGO SuperBoard Web SDK**. Excali Draw provides a focused canvas and a set of drawing and interaction tools for sketching ideas, adding text, creating shapes, and pointing out details.

<p align="center">
  <a href="https://white-board-rust-three.vercel.app/"><strong>Live Demo</strong></a>
  &nbsp;·&nbsp;
  <a href="https://github.com/webdev-anup/White-Board"><strong>Source Code</strong></a>
</p>

## Project Overview

Excali Draw integrates ZEGO's web-based whiteboard SDK into a React application. The app connects to a configured ZEGO room, initializes a whiteboard view, and presents a compact toolbar for switching between canvas tools.

The project demonstrates component-based React development, third-party SDK integration, and a Vite-based frontend workflow.

## Features

- **Pen** — draw and sketch freely on the canvas.
- **Text** — add text to the whiteboard.
- **Line** — create straight lines.
- **Rectangle** — draw rectangular shapes.
- **Ellipse** — draw circles and oval shapes.
- **Select** — select and interact with canvas objects.
- **Eraser** — remove unwanted content.
- **Laser** — point to or highlight an area during a session.
- **Click** — use the SDK's click interaction tool.
- **ZEGO integration** — initialize the SuperBoard view and connect to a configured room through ZEGO Express Engine.

> Collaboration behavior depends on the ZEGO room, board, and user configuration. The current demo uses fixed room and user values in `src/App.jsx`; configure unique user identities and shared-board handling before using it as a multi-user production service.

## Tech Stack

| Technology | Role |
|---|---|
| React 19 | UI and component architecture |
| JavaScript (ES modules) | Application logic |
| Vite 8 | Development server and production build |
| Tailwind CSS 4 | Utility-first styling |
| ZEGO SuperBoard Web SDK | Whiteboard rendering and canvas tools |
| ZEGO Express Engine WebRTC | ZEGO room connection |
| React Icons | Toolbar icons |

## Getting Started

### Prerequisites

- Node.js **20.19+** or **22.12+**
- npm
- A ZEGO project with the required App ID and a valid access token

### 1. Clone the repository

```bash
git clone https://github.com/webdev-anup/White-Board.git
cd White-Board
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure ZEGO

Create a `.env` file in the project root:

```env
VITE_ZEGO_TOKEN=your_valid_zego_token
```

The current demo also defines its ZEGO App ID, room ID, user ID, user name, and server address in `src/App.jsx`. Update those values to match your ZEGO project before running the app.

**Security note:** Vite exposes variables prefixed with `VITE_` to browser-side code. Treat `VITE_ZEGO_TOKEN` as public once the app is built. Never put a ZEGO ServerSecret or other private server credential in a frontend environment variable. For a public production deployment, use short-lived tokens issued by a trusted token-generation service and rotate any token that has been exposed.

### 4. Start the development server

```bash
npm run dev
```

Open the local URL printed by Vite in your terminal.

## Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Start the local development server |
| `npm run build` | Create the production build in `dist/` |
| `npm run preview` | Preview the production build locally |
| `npm run lint` | Run ESLint checks |

Before deploying, run:

```bash
npm run lint
npm run build
```

## Project Structure

```text
White-Board/
├── public/             # Static assets
├── src/
│   ├── App.jsx         # ZEGO initialization and whiteboard layout
│   ├── Tools.jsx       # Whiteboard tool toolbar
│   ├── App.css         # Application styles
│   ├── index.css       # Global Tailwind import
│   └── main.jsx        # React application entry point
├── .env                # Local ZEGO token (not committed)
├── .gitignore
├── index.html
├── package.json
├── package-lock.json
└── vite.config.js
```

## Deployment

The application is deployed on Vercel:

**Live application:** https://white-board-rust-three.vercel.app/

For a Vercel deployment, add the required environment variable in the project's environment settings and trigger a new deployment after changing environment values. Do not commit your local `.env` file.

## Future Improvements

- Secure token issuance and token renewal for production use.
- Unique user identities and room access controls.
- Reuse or retrieve an existing shared whiteboard instead of creating a new one on every client initialization.
- Clear loading, connection, and error states.
- Responsive toolbar and canvas layout for smaller screens.
- Improve initial loading by reviewing the large third-party SDK bundle.

## Author

**Anup Patwa**  
B.Sc. Information Technology | Frontend Developer

- GitHub: [@webdev-anup](https://github.com/webdev-anup)
- Project repository: [White-Board](https://github.com/webdev-anup/White-Board)
- Live demo: [Excali Draw](https://white-board-rust-three.vercel.app/)

---

*Built with React, Vite, Tailwind CSS, and ZEGO SuperBoard.*
