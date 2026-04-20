# Imposter AI

A social deduction party game. 3–12 players share one phone. Everyone sees a secret word except one player — the Imposter — who must bluff. Players give one-word clues, then vote to catch the Imposter.

## Play it online

Once you deploy to GitHub Pages, the game will be available at:

```
https://<your-username>.github.io/<your-repo-name>/
```

## Installing on your phone

### iPhone (Safari)
1. Open the site in **Safari** (not Chrome — iOS only allows Safari to install PWAs).
2. Tap the **Share** button (square with up-arrow).
3. Scroll down and tap **Add to Home Screen**.
4. Tap **Add**. The app appears as an icon on your home screen.

### Android (Chrome)
1. Open the site in **Chrome**.
2. Tap the **⋮** menu → **Add to Home screen** (or **Install app**).
3. Confirm. The app appears on your home screen and can be launched fullscreen.

Once installed, the app works **offline** — pre-made categories and the whole game flow cache automatically. Only the "✨ Create with AI" feature needs internet.

## Deploy to GitHub Pages

1. Create a new **public** repo on GitHub (e.g. `imposter-ai`).
2. Upload every file in this folder (preserving the `icons/` subfolder structure).
3. In the repo, go to **Settings → Pages**.
4. Under "Build and deployment", pick:
   - **Source:** Deploy from a branch
   - **Branch:** `main` (or `master`) and folder `/ (root)`
5. Save. Wait ~30 seconds, then open `https://<your-username>.github.io/<your-repo-name>/`.

## Using AI categories (optional)

The "✨ Create with AI" button uses [Groq](https://console.groq.com) to generate custom 40-word categories.

1. Get a free API key at [console.groq.com](https://console.groq.com/keys).
2. Open `index.html` in a text editor.
3. Find the line `const GROQ_API_KEY = "YOUR_KEY_HERE";` (near the top of the `<script>` tag).
4. Replace `YOUR_KEY_HERE` with your key.
5. Save, re-upload, done.

> ⚠️ **Heads-up:** Putting an API key in a public repo means anyone who finds it can use your free Groq quota. The free tier is generous, but if you care, either keep the repo private or leave the key out and only add it locally.

## File structure

```
.
├── index.html              # the whole game (HTML + CSS + JS in one file)
├── manifest.webmanifest    # PWA manifest — makes it installable
├── sw.js                   # service worker — enables offline play
├── .nojekyll               # tells GitHub Pages not to process files
├── icons/
│   ├── favicon-64.png
│   ├── apple-touch-icon.png      # iOS home-screen icon
│   ├── icon-192.png              # Android home-screen icon
│   ├── icon-512.png              # High-res PWA icon
│   └── icon-maskable-512.png     # Android adaptive icon
└── README.md
```

## How to play

1. **Add 3–12 players** and pick a character for each.
2. **Pick a category** — 16 built-in options, or create your own with AI.
3. **Pass the phone around.** Each player taps the card to see their secret word. One player sees "You are the Imposter 🤫" instead.
4. **Clue phase.** Each player says ONE word related to the secret. The Imposter has to bluff by listening to everyone else.
5. **Vote.** Everyone votes for the Imposter. If the majority catches them → players win. If not → the Imposter wins.
