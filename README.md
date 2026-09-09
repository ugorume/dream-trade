# Dream Trade

A static, interactive crypto broker dashboard concept built with plain HTML, CSS, and JavaScript.

## Run

Open `index.html` directly in a browser. Vercel also uses `index.html` as the root static entry point. No build step or package installation is required.

## Included

- Dream Trade market dashboard in a yellow and black visual system
- Animated price chart with live-looking updates every five seconds
- Searchable asset table and interactive watchlist stars
- Buy/sell order ticket with estimated crypto amount
- Login and create-account modal with Google sign-in option
- Responsive layout for desktop and mobile screens
- Live USD prices and 24-hour changes from CoinGecko, with an offline demo fallback
- Click any market, ticker, or watchlist asset to load its chart and order ticket
- Persistent light/dark mode and an animated interactive Dream Trade rocket space scene
- 100+ crypto pairs with selectable candle, line, and bar chart modes
- Sandbox funding panel with generated session addresses and simulated balance credits

Authentication, order placement, and funding are demo UI only. The generated addresses are not blockchain deposit addresses and must not receive real crypto. For production, connect a regulated custody/payment provider, server-side wallet generation, deposit webhooks, confirmations, ledgering, KYC/AML, and withdrawal controls before accepting funds.

## Authentication setup

Authentication is wired to Supabase Auth. The browser-safe project URL and anon key belong in `supabase-config.js`; never put a Supabase service-role key in this file.

1. Create a Supabase project.
2. Copy **Project Settings > API > Project URL** and **anon public key** into `supabase-config.js`.
3. In Supabase, open **Authentication > Providers > Google** and enable Google.
4. In Google Cloud, create OAuth credentials and add the Supabase callback URL shown in the provider settings.
5. Add your hosted URL under Supabase **Authentication > URL Configuration > Site URL / Redirect URLs**.
6. Serve the site over HTTPS when hosted. Google OAuth will not complete from a `file://` URL.

The app now uses Supabase for Google OAuth, email login, account creation, sessions, and password handling. Supabase still needs email confirmation, password reset, rate limiting, and any production user policies configured in its dashboard.
