# PWA Submission Guide

Everything you need to get your PWA listed on pwa.mobi — step by step, no friction.

---

## Before You Start — Checklist

Run through this before touching anything else. If any item is not ready, fix it first.

- [ ] My PWA is live and accessible over **HTTPS** right now
- [ ] I have a valid **`manifest.json`** file served from my domain
- [ ] I have a registered **Service Worker**
- [ ] My PWA works **offline** or shows a meaningful offline page
- [ ] I have a **512×512px PNG icon** accessible via a public URL
- [ ] My Lighthouse PWA score is **85 or above** — check at [web.dev/measure](https://web.dev/measure)
- [ ] I have a **GitHub account**

Not sure about your Lighthouse score? Run it free at [web.dev/measure](https://web.dev/measure). Enter your PWA URL and check the scores. We look for Performance, Accessibility, Best Practices and SEO all in good shape.

---

## Step 1 — Fork the Registry

> **What is forking?** Forking creates your own personal copy of the registry that you can edit freely. Your changes won't affect the main registry until you submit them for review.

1. Make sure you are **logged into GitHub** with your personal account
2. Go to [github.com/pwamobi/registry](https://github.com/pwamobi/registry)
3. Click the **"Fork"** button at the top right of the page
4. On the fork screen:
   - **Owner:** make sure it shows **your username** — not pwamobi
   - **Repository name:** leave as `registry`
   - **Copy the main branch only:** leave this checked ✅
5. Click **"Create fork"**

✅ You now have your own copy at `github.com/YOUR_USERNAME/registry`

---

## Step 2 — Navigate to the Apps Folder

> ⚠️ **THIS IS THE MOST IMPORTANT STEP.** Your YAML file MUST be created inside the `apps/` folder. If you create it anywhere else, the registry will not find it and your app will not be listed. Read this step carefully.

1. You should be looking at your forked repo at `github.com/YOUR_USERNAME/registry`
2. Look at the file list and find the folder named **`apps`**
3. Click on the **`apps`** folder to open it
4. You should now see the URL change to: `github.com/YOUR_USERNAME/registry/tree/main/apps`
5. You should see two files inside: `.gitkeep` and `_template.yaml`

**✅ Confirm you are inside the `apps/` folder before continuing.**
**❌ Do NOT create your file from the root of the repository.**

---

## Step 3 — Create Your YAML File

> You are still inside the `apps/` folder from Step 2. Do not navigate away.

1. Click **"Add file"** → **"Create new file"**
2. In the filename box at the top, type your app's filename:
   - Use lowercase letters and hyphens only
   - End with `.yaml`
   - Examples: `my-app.yaml`, `coolnotes.yaml`, `workflowpro.yaml`
   - ✅ Good: `younu.yaml`
   - ❌ Bad: `YouNu.yaml`, `my app.yaml`, `myapp.json`
3. **Double check the path shown above the filename box** — it must show:
   ```
   pwamobi / registry / apps / your-app-name.yaml
   ```
   If it shows `pwamobi / registry / your-app-name.yaml` (no `apps/`) — **stop and go back to Step 2**

---

## Step 4 — Fill In Your App Details

Copy the template below and paste it into the file editor. Then fill in every field with your app's real information. Delete all comment lines (lines starting with `#`) before submitting.

```yaml
name: Your App Name
tagline: One line that explains your app in under 80 characters

category: productivity

url: https://yourapp.com
manifest_url: https://yourapp.com/manifest.json

developer:
  name: Your Name or Company
  github: your-github-username
  email: you@yourapp.com
  website: https://yourwebsite.com

listing:
  description: |
    Write a clear honest description of your PWA here.
    What does it do? Who is it for? What makes it useful?
    Minimum 50 characters, maximum 500 characters.

  icon_url: https://yourapp.com/icons/icon-512.png

  screenshots:
    - https://yourapp.com/screenshots/screen1.png
    - https://yourapp.com/screenshots/screen2.png

  tags:
    - productivity
    - offline
    - free-tier

payment_model: freemium

pricing_url: https://yourapp.com/pricing

open_source_url:

submitted_by: your-github-username
submission_date: 2026-03-25
```

### Field Reference

| Field | Required | Description |
|---|---|---|
| `name` | ✅ | Display name, max 60 chars |
| `tagline` | ✅ | One liner, max 80 chars |
| `category` | ✅ | See category list below |
| `url` | ✅ | Must start with `https://` |
| `manifest_url` | ✅ | Full URL to your `manifest.json` |
| `developer.name` | ✅ | Your name or company name |
| `developer.github` | ✅ | Your GitHub username |
| `developer.email` | ✅ | Not public — registry contact only |
| `listing.description` | ✅ | 50–500 characters |
| `listing.icon_url` | ✅ | Must be 512×512px PNG, `https://` |
| `listing.screenshots` | Optional | Up to 5 URLs |
| `listing.tags` | Optional | Up to 8 lowercase tags |
| `payment_model` | ✅ | `free` / `freemium` / `paid` / `open-source` |
| `pricing_url` | Optional | Link to your pricing page |
| `open_source_url` | Optional | GitHub/GitLab URL if open source |
| `submitted_by` | ✅ | Must match your GitHub username exactly |
| `submission_date` | ✅ | Today's date in `YYYY-MM-DD` format |

### Categories

```
productivity    communication   finance         health
education       entertainment   utilities       developer-tools
social          news            travel          food
shopping        lifestyle       creativity      business
games           sports          weather         other
```

---

## Step 5 — Commit Your File

1. When your YAML is filled in, click the green **"Commit changes"** button at the top right
2. A popup will appear — fill it in:
   - **Commit message:** `feat: add YourAppName to registry`
   - **Description:** leave empty
   - Keep **"Commit directly to the main branch"** selected
3. Click **"Commit changes"**

✅ Your file is now saved in your fork.

---

## Step 6 — Open a Pull Request

> A Pull Request (PR) is how you say "I'd like to add my app to the registry." It lets the maintainers review your submission before it goes live.

1. After committing, you'll be taken back to your fork's file list
2. Look for the message: **"This branch is 1 commit ahead of pwamobi/registry:main"**
3. Click **"Contribute"** → **"Open pull request"**
4. You'll see the PR form — fill it in:
   - **Title:** `feat: add YourAppName to registry`
   - **Description:** Fill in the checklist — change every `- [ ]` to `- [x]` for items you confirm, and fill in the About This App section at the bottom
5. Click the green **"Create pull request"** button

✅ Your submission is now open for review.

---

## Step 7 — Wait for the Audit Bot

Within a few minutes of opening your PR, our automated audit bot will run and post a comment on your PR with results like this:

```
✅ HTTPS                    Pass
✅ Web App Manifest         Pass
✅ Service Worker           Pass
✅ Lighthouse PWA Score     94/100
✅ Icon (512×512)           Pass
✅ Security Headers         Pass
✅ Domain Reputation        Clean
✅ YAML Schema              Valid
```

**If everything passes** — your PR gets labeled `audit-passed` and a maintainer will review and merge it shortly. Your app will appear in the directory within minutes of merging.

**If something fails** — the bot will tell you exactly what to fix. Fix it on your live site, then push a new commit to your PR branch. The audit runs again automatically.

---

## Step 8 — You're Listed! 🎉

Once your PR is merged:
- Your app appears on [pwa.mobi/apps.html](https://pwa.mobi/apps.html)
- It carries the **pwa.mobi verified badge**
- Users can discover, read about, and install your PWA directly

No fees. No ongoing compliance. No revenue sharing. Ever.

---

## Updating Your Listing

To update your app's metadata after it has been listed:

1. Go to your fork (or re-fork the registry)
2. Edit your existing `apps/your-app-name.yaml` file
3. Open a new PR with the changes
4. The audit will re-run to confirm your live app still passes
5. Maintainer merges — your listing updates

---

## Removing Your Listing

Open an issue in the registry with the label `remove-my-listing` and include your app's YAML filename. We'll remove it within 48 hours. No questions asked.

---

## Common Mistakes to Avoid

| Mistake | Fix |
|---|---|
| YAML file created in repo root instead of `apps/` | Always navigate into `apps/` folder before creating your file |
| Icon URL returns 404 | Make sure your icon file is uploaded and publicly accessible |
| `submitted_by` doesn't match GitHub username | Copy your exact GitHub username — it's case sensitive |
| Description too short | Minimum 50 characters — be descriptive |
| URL without HTTPS | All URLs must start with `https://` |
| Wrong category | Pick the closest match from the category list |
| Checkbox format wrong | Use `- [x]` not `- [X]` or `- [ x]` |

---

## Need Help?

- 💬 Join the [pwa.mobi Discord](https://discord.gg/46Dm7n4spf) — the community is happy to help
- 🐛 Open a [GitHub Discussion](https://github.com/pwamobi/registry/discussions) for technical questions
- 📧 Email [hello@pwa.mobi](mailto:hello@pwa.mobi) for anything else

---

*pwa.mobi is a [Simple Minds](https://simpleminds.dev) initiative · The web is the platform*
