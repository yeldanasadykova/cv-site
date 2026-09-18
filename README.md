# Yeldana Sadykova — CV site

A static one-page site. No build step, no dependencies — just `index.html`, `styles.css`, and `script.js`.

## View it locally

Open `index.html` directly in a browser, or run a tiny local server:

```bash
cd cv-site
python3 -m http.server 8000
```

Then visit http://localhost:8000

## Deploy to Vercel (no CLI needed)

1. Create a new GitHub repository (e.g. `cv-site`) and push these three files to it:
   ```bash
   cd cv-site
   git init
   git add .
   git commit -m "Initial CV site"
   git branch -M main
   git remote add origin https://github.com/yeldanasadykova/cv-site.git
   git push -u origin main
   ```
2. Go to https://vercel.com and sign in with your GitHub account.
3. Click **Add New → Project**, then select the `cv-site` repo.
4. Framework preset: choose **Other** (it's a plain static site — no build command, no output directory needed).
5. Click **Deploy**. Vercel gives you a live `https://cv-site-<something>.vercel.app` URL within a minute.
6. Optional: in the project's **Settings → Domains**, add a custom domain if you have one.

Any time you edit the files and push to `main`, Vercel redeploys automatically.

## Adding a chat/assistant feature later

This is a static site, so it can't run a live AI chat on its own. When you're ready:
- Add a [Vercel Function](https://vercel.com/docs/functions) (a small serverless API route) that calls the Anthropic API.
- Point a chat widget on the page at that function instead of calling any API directly from the browser (keeps your API key private).
- This is a good point to bring in Claude Code — it can scaffold the function, wire up the widget, and handle env vars/secrets for you.
