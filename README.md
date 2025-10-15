# TA^2 — Limited Tee Store (MVP)

A super‑simple Next.js + Tailwind site to sell a single limited‑edition shirt. **No Stripe** — checkout is a preorder form that emails you via **Formspree**.

---

## Features

* Minimal, fast storefront (one product)
* Size & quantity selection
* Preorder (no on‑site payment)
* Formspree email notification
* One‑click deploy to Vercel

---

## Tech Stack

* [Next.js](https://nextjs.org/) (App Router, TypeScript)
* [Tailwind CSS](https://tailwindcss.com/)
* [Vercel](https://vercel.com/) (hosting)
* [Formspree](https://formspree.io/) (form handling)

---

## Quick Start

```bash
# 1) Clone
git clone https://github.com/<your-username>/tshirt-store.git
cd tshirt-store

# 2) Install deps
npm install

# 3) Run locally
npm run dev
# open http://localhost:3000
```

> Assets live in `/public` (e.g., `logo-ta2.svg`, `tee-front.png`).

---

## Project Structure

```
/src
  /app
    /(site)
      /shop/page.tsx        # Product page
      /checkout/page.tsx    # Preorder form (Formspree)
    layout.tsx
    page.tsx                # Home
  /components
    ProductHero.tsx
  /data
    product.ts              # Product data (name, price, sizes, etc.)
/public                     # Images, logo
```

---

## Configure Formspree (Required)

1. Create a form at **formspree.io**.
2. Copy the endpoint ID (looks like `https://formspree.io/f/abcdwxyz`).
3. In `/src/app/(site)/checkout/page.tsx`, replace `YOUR_FORMSPREE_ID` with your ID.
4. Deploy and submit a test to confirm you receive the email.

*Optional*: add spam protection (honeypot or reCAPTCHA) in Formspree settings.

---

## Edit Product Info

Change name, price, sizes, and description in `/src/data/product.ts`.

---

## Deploy to Vercel

1. Push this repo to GitHub.
2. In Vercel → **New Project** → Import your repo.
3. Framework: **Next.js** (autodetected). No env vars needed.
4. Deploy → share the live URL.

---

## Common Tasks

* **Change price/copy** → `/src/data/product.ts`
* **Update images** → add files to `/public` and update `images` array in `product.ts`
* **Branding** → edit colors/fonts in Tailwind classes; global styles in `/src/styles/globals.css`
* **Inventory cap** (later) → add simple server action or KV to limit reservations
* **Real payments** (later) → swap Formspree for Stripe/Shopify/Lemon Squeezy

---

## Contributing

* Create a branch: `git checkout -b feature/your-change`
* Commit: `git commit -m "feat: describe change"`
* Push: `git push -u origin feature/your-change`
* Open a Pull Request

---

## License

MIT © <your‑name>
