# Plum & Thread — Apparel Manufacturing Website

A responsive React + Vite landing page concept for the SuperLabs frontend developer assessment. It includes a product showcase, manufacturing story, FAQ, contact section and an interactive quotation calculator. No backend is required.

## Requirements
- Node.js 18.18+ (Node 20+ recommended)
- npm

## Run locally

```bash
npm install
npm run dev
```

Open the local URL printed by Vite (usually `http://localhost:5173`).

## Production build

```bash
npm run build
npm run preview
```

The optimized static site is generated in `dist/`. Deploy that folder to Vercel, Netlify, or any static hosting provider. For Vercel/Netlify, the build command is `npm run build` and the output directory is `dist`.

## Project structure

```text
src/
  components/
    Logo.jsx
    Navbar.jsx
    ProductCard.jsx
    QuoteCalculator.jsx
    SectionHeading.jsx
  data/
    products.js
  App.jsx
  main.jsx
  styles.css
  utils.js
index.html
```

## Quotation calculation

The product catalogue is centralized in `src/data/products.js`. Each product has a base price and its own GST percentage. For each selected line:

- Line subtotal = unit price × quantity
- Line GST = line subtotal × product GST rate ÷ 100
- Line total = line subtotal + line GST
- Grand total = sum of line subtotals + sum of line GST

The quote state is held in React state as a product-ID-to-quantity object. The calculator derives totals from that state, prevents quantities below one for selected rows, removes a row when its quantity is reduced to zero, and supports add, increase, decrease, remove, reset, empty state and copy-to-clipboard actions.

## Design and technical decisions

- React functional components keep page sections and repeated UI modular.
- Vite provides a small, fast development server and optimized production build.
- CSS custom properties establish a consistent warm-paper, plum and muted-olive palette.
- CSS Grid and responsive breakpoints adapt the hero, product cards, quote calculator and content sections for desktop, tablet and mobile.
- Semantic landmarks, skip navigation, descriptive button labels, `aria-expanded`, visible focus handling from browser defaults, lazy-loaded supporting imagery and reduced-motion support improve accessibility and usability.
- Lucide React supplies lightweight interface icons.
- The quote calculator is entirely client-side; no customer data is transmitted or persisted.

## Content and assets to review before real-world use

Plum & Thread is fictional for this assessment. Statistics and testimonials are deliberately presented as illustrative rather than factual. Replace the demo email address `hello@plumandthread.example` with an approved business contact, and use verified company claims and customer testimonials before publishing as a real company website. Product photography currently uses remote Unsplash image URLs; replace with licensed, optimized brand photography for production. The site uses Google Fonts with system-serif fallbacks.

## AI usage disclosure

OpenAI ChatGPT was used to help interpret the assessment brief, scaffold the React component structure, write responsive styling, and implement the quotation calculator and documentation. The project owner should review, understand, test, and be prepared to explain and modify all code before submission.
