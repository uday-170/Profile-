```markdown
# Project Vault

A small Next.js + Prisma MVP application to store Projects, Certificates, and a Resume.

Features (MVP)
- Sign in (no signup page)
- Add Projects: title, description, link, optional file upload
- Add Certificates: name, issuer, date, optional file upload
- Upload a single Resume file
- Local file storage: saved to public/uploads (for development). Use S3 in production.

Quick start (local)
1. Install
   npm install

2. Set environment variables (create a .env file or copy .env.example):
   DATABASE_URL="file:./dev.db"
   NEXTAUTH_URL="http://localhost:3000"
   NEXTAUTH_SECRET="a-long-random-string"

3. Initialize database (Prisma)
   npx prisma generate
   npx prisma migrate dev --name init

4. Create at least one user (there is no signup page)
   Option A — run the included script (recommended):
     node scripts/create-user.js username password "Full Name" email@example.com

     Example:
     node scripts/create-user.js alice s3cret "Alice Example" alice@example.com

   Option B — use Prisma Studio:
     npx prisma studio
     - Insert a User row and ensure password is a bcrypt hash (or use the script above).

5. Run dev server
   npm run dev

6. Open http://localhost:3000 and click Sign in.

Notes
- There is intentionally no signup page. Users must be created by an admin (via the script or Prisma Studio).
- For production, do not use local filesystem for uploads in serverless environments — use S3 or other object storage.
- Set NEXTAUTH_SECRET to a long random string in production.
```
