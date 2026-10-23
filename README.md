# VIBRANCY AI — Generation X Workspace

Created by **Sayeef Adnan**.

This project is a futuristic, responsive AI-chat interface built with plain HTML, CSS, and JavaScript. It is suitable for GitHub Pages as a frontend. It does **not** include an AI provider key or a production backend.

## Features

- Responsive sidebar and mobile navigation drawer
- New conversations, locally saved conversation history, rename-by-first-message, and delete
- Prompt suggestions and prompt library
- Markdown-style response formatting and copy controls
- Export conversation as Markdown
- Text-file attachment (content is sent with the next prompt)
- Dark/light appearance preferences
- Configurable backend endpoint
- Honest setup/error states when no backend is connected
- Reduced-motion support and keyboard controls

## Run locally

Open `index.html` in a modern browser. For best results, use a local static server (for example, VS Code Live Server). No build step is required.

## Connect a real AI backend

Open **Connection settings** in the app and enter your backend endpoint. The frontend sends:

```json
{
  "messages": [
    {"role": "user", "content": "Hello"}
  ],
  "stream": false
}
```

The endpoint should return JSON with a string field named `reply`, `message`, or `content`, for example:

```json
{"reply":"Hello! How can I help?"}
```

Your backend must:
- call the AI provider server-side;
- keep provider API keys in server environment variables;
- validate requests and enforce rate limits;
- set CORS to allow only the intended website origin;
- handle provider errors and timeouts;
- avoid logging private conversation data unnecessarily.

Do not paste provider API keys into this static site, localStorage, or a public repository. GitHub Pages serves static files and does not run a private backend by itself.

## Security action required

The previous version of `index.html` contained API-key-looking values in client-side JavaScript. Treat any credentials that were ever committed to a public repository as exposed: review the relevant provider dashboards, revoke/rotate those credentials if they are real, and check usage. Removing a key from the latest file does not erase it from Git history.

## Known limitations

- Real AI responses require a compatible backend endpoint.
- File attachment currently supports text-like files only and sends their text content with the next message.
- Conversation history is stored in the current browser only; it does not synchronize across devices.
- No authentication or multi-user database is included.
- The frontend expects a JSON response, not a streaming response.

## Deploy to GitHub Pages

1. Replace the repository's `index.html` with this file.
2. Commit and push the change.
3. In GitHub, open **Settings → Pages** and confirm the desired branch/folder is published.
4. Configure a separate backend if you want live AI responses.

## Project identity

**VIBRANCY AI — Generation X Workspace**  
Created and designed by **Sayeef Adnan**.
