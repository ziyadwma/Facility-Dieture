# FacilityFlow

Manage facility issues with strict SLAs, photo-only attachments, PR workflow, and dashboards.

## Tech
- Next.js 14 (App Router) + TypeScript + Server Actions
- Tailwind + shadcn/ui + dark mode
- NextAuth (email + Google/Microsoft SSO)
- Postgres via Prisma
- S3-compatible storage (e.g., Cloudflare R2)
- BullMQ (Redis) background jobs for 24h ack & 72h repair alert, ETA escalations, reminders, thumbnails
- Nodemailer (SMTP) or Resend for email; Twilio for SMS

## Getting Started
1. Copy `.env.example` to `.env.local` and fill values.
2. `pnpm i` (or `npm i`/`yarn`)
3. `pnpm prisma:generate && pnpm db:push && pnpm db:seed`
4. Start app & worker in two terminals:
   - App: `pnpm dev`
   - Worker: `pnpm worker`

## Scripts
- `dev` Next dev server
- `build` Production build
- `start` Start Next
- `worker` Start background worker (BullMQ)
- `db:push` Prisma migrate dev
- `db:seed` Seed departments, areas, demo users
- `test` Run vitest

## Roles
Admin, OperationsManager, DepartmentManager, Technician, Requester, Procurement, Viewer
