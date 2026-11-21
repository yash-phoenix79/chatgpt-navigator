# ChatGPT Navigator

A local-first Chrome Manifest V3 extension that indexes user questions in a ChatGPT conversation, groups them by topic, searches them, and jumps to the original message.

## Status
Initial implementation. Automated tests and CI are included; real ChatGPT DOM compatibility is a separate smoke-test gate.

## Development
```bash
npm install
npx playwright install chromium
npm test
npm run lint
npm run test:e2e
npm run test:all
```

## Privacy
Conversation content is processed locally in the browser. No external API is used. The extension requests only the permissions required for its side panel, local storage, active tab, and ChatGPT hosts.

## Test strategy
Unit tests use synthetic DOM fixtures. Playwright loads the extension into isolated Chromium and serves a fixture page on localhost. Production manifest does not include localhost permissions.

## Install
1. Download/clone the repository.
2. Open `chrome://extensions`.
3. Enable Developer Mode.
4. Load unpacked and select the repository root.
5. Open a ChatGPT conversation and open the extension side panel.
