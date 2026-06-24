# Tendria Website

This repository contains Tendria's public privacy and support website for GitHub Pages.

The site is intentionally static:

- no build step
- no React
- no npm
- no Jekyll theme
- no remote JavaScript
- no external fonts
- no analytics
- no cookies
- no tracking pixels
- no web forms

Support email: `tendria.support@gmail.com`

## File Structure

```text
tendria-site/
├── index.html
├── privacy/
│   └── index.html
├── support/
│   └── index.html
├── es/
│   ├── privacy/
│   │   └── index.html
│   └── support/
│       └── index.html
├── zh-hans/
│   ├── privacy/
│   │   └── index.html
│   └── support/
│       └── index.html
├── zh-hant/
│   ├── privacy/
│   │   └── index.html
│   └── support/
│       └── index.html
├── assets/
│   └── styles.css
├── 404.html
├── .nojekyll
├── .gitignore
└── README.md
```

## Preview Locally

From this repository:

```sh
cd "/Users/xiao/Documents/New project/tendria-site"
python3 -m http.server 8000
```

Then open:

```text
http://127.0.0.1:8000/
http://127.0.0.1:8000/privacy/
http://127.0.0.1:8000/support/
```

To preview GitHub Project Pages path behavior, serve from the parent directory:

```sh
cd "/Users/xiao/Documents/New project"
python3 -m http.server 8000
```

Then test:

```text
http://127.0.0.1:8000/tendria-site/
http://127.0.0.1:8000/tendria-site/privacy/
http://127.0.0.1:8000/tendria-site/support/
http://127.0.0.1:8000/tendria-site/404.html
```

The `404.html` file includes `<base href="/tendria-site/">` so CSS and navigation work from nested missing URLs on GitHub Project Pages. If the repository name changes, update that base path. If Tendria later moves to a custom domain, review the base path and internal links before publishing.

## GitHub Pages Publishing

Assuming the GitHub repository is named `tendria-site`:

1. Create a public GitHub repository named `tendria-site`.
2. Push the `main` branch.
3. In GitHub, open repository Settings.
4. Go to Pages.
5. Set Source to `Deploy from a branch`.
6. Set Branch to `main`.
7. Set Folder to `/ (root)`.
8. Save and wait for GitHub Pages to publish.

No GitHub Actions workflow is needed for this static site.

## Expected Default URLs

Replace `OWNER` with the GitHub username or organization:

```text
https://OWNER.github.io/tendria-site/
https://OWNER.github.io/tendria-site/privacy/
https://OWNER.github.io/tendria-site/support/
https://OWNER.github.io/tendria-site/es/privacy/
https://OWNER.github.io/tendria-site/es/support/
https://OWNER.github.io/tendria-site/zh-hans/privacy/
https://OWNER.github.io/tendria-site/zh-hans/support/
https://OWNER.github.io/tendria-site/zh-hant/privacy/
https://OWNER.github.io/tendria-site/zh-hant/support/
```

Use `/privacy/` for the App Store Connect Privacy Policy URL and `/support/` for the Support URL.

After final public URLs are known, update Tendria's in-app About links separately in the app repository.

## Custom Domain Later

If Tendria later uses a custom domain:

1. Add a `CNAME` file containing the domain.
2. Configure DNS according to GitHub Pages instructions.
3. Review `404.html` and the `<base>` path.
4. Update App Store Connect URLs after the domain is live.
5. Re-check all internal links after the change.

## Updating Policy Text

Update the English page first, then update Spanish, Simplified Chinese, and Traditional Chinese to match. Keep the effective date current when the policy meaning changes.

The privacy policy must continue to reflect the real Tendria app implementation. Do not claim cloud sync, analytics, encryption behavior, medical accuracy, legal entity details, retention periods, or App Store availability unless the app and public release state actually support those claims.

Keep App Store age-rating answers consistent with Tendria's product positioning and this public policy.

## Public Data Boundary

This public website must not contain:

- private app source
- private user data
- certificates
- keys
- signing files
- screenshots containing private records
- HealthKit samples
- session records
- private notes
- debug logs

The Tendria app repository is separate and private. Do not copy private app code, signing assets, user records, or internal release material into this website repository.

## Validation Checklist

Before publishing:

- Confirm every internal link resolves.
- Confirm there are no developer placeholders or publication reminders.
- Confirm there are no external scripts or fonts.
- Confirm there are no analytics, cookies, tracking pixels, or third-party forms.
- Confirm all privacy and support pages exist in English, Spanish, Simplified Chinese, and Traditional Chinese.
- Confirm the site looks readable on mobile, tablet, and desktop widths.
- Confirm light and dark mode are readable.
- Confirm policy wording still matches the current Tendria app behavior.
- Confirm `404.html` works from the `/tendria-site/` project path.
