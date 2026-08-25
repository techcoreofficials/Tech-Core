[README.md](https://github.com/user-attachments/files/31412005/README.md)
Tech Core — Starter

This repository is a scaffold for the Tech Core website (Next.js + Tailwind + Prisma).

What is included
- Next.js frontend pages (index, admin)
- Tailwind CSS setup
- Prisma schema (SQLite dev by default)
- API endpoint for contact form (saves to DB and sends email via SMTP if configured)
- NextAuth credentials-based auth and admin content API (seed endpoint available for initial admin creation)

Getting started (local)
1. cd tech-core
2. npm install
3. Create a .env file (see example below)
4. npx prisma generate
5. npx prisma migrate dev --name init
6. npm run dev

.env example (create .env at project root):

DATABASE_URL="file:./dev.db"
NEXTAUTH_SECRET="long_random_string_here"
ADMIN_INITIAL_EMAIL="you@yourdomain.com"
ADMIN_INITIAL_PASSWORD="StrongPassword123"
SMTP_HOST="smtp.example.com"    # optional, for email notifications
SMTP_PORT="587"
SMTP_USER="smtp_user"
SMTP_PASS="smtp_pass"
SMTP_FROM="no-reply@yourdomain.com"
CONTACT_EMAIL="officialstechcore@gmail.com"

Deploy to Vercel
- Use a PostgreSQL database for production (Vercel Postgres or Supabase). Update DATABASE_URL in Vercel Environment Variables.
- Set NEXTAUTH_SECRET and SMTP_* in Vercel Environment Variables.

Admin setup (one-time)
1. Start the app locally: npm run dev
2. Visit /api/seed-admin to create the initial admin (reads ADMIN_INITIAL_EMAIL and ADMIN_INITIAL_PASSWORD from .env). Remove or disable this endpoint after use.
3. Sign in at /api/auth/signin using the credentials provider.

Next steps
- Replace placeholder content and add portfolio/services entries in the DB (admin UI will be extended to manage collections)
- Add image files to /public (logo.png etc.)

Assets provided by user: logo (copied to /public/logo.png)
