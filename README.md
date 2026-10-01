# Kargo Hiring Dashboard

Ranked PM / SPM shortlist for Arjun (Kargo, Series A logistics SaaS). **The system recommends. Arjun decides.**

Live: https://kargo-hiring-sandy.vercel.app (passcode protected)

## Flow
Upload CV + applied role → **PII split** (name/email/phone stored separately, never sent to AI) → **Gemini scores** against PM *and* SPM rubrics → **rank** (top 5 above a 55/100 quality floor = invite) → **3-sentence interview brief** + **personalised draft email** (invite or warm rejection) → Arjun reviews, overrides if needed, clicks **Confirm & send** → **Resend**.

## Rubric
Derived from Kargo's 8 past hires, not the JDs (see `rubric.txt`). Exceeds-rated hires shared: operations-floor exposure, unprompted fixes others adopted, and owning failure in the open. Credentials / MBA / years of experience are deliberately not scored.

## The Cut (Checks 06 + 09)
No auto-rejection. Every email — invite or rejection — goes out only on the founder's click.

## Stack
Next.js 15 · Supabase (Postgres, RLS on, server-only access) · Gemini Flash · Resend · Vercel

## Setup
1. Run `supabase/schema.sql` in Supabase → SQL Editor.
2. Copy `.env.example` to `.env.local` and fill in the keys.
3. `npm install && npm run dev`

Env vars: `SUPABASE_URL`, `SUPABASE_SERVICE_ROLE_KEY`, `GEMINI_API_KEY`, `GEMINI_MODEL`, `RESEND_API_KEY`, `RESEND_FROM`, `TEST_INBOX`, `APP_PASSCODE`, `SHORTLIST_SIZE`, `MIN_INVITE_SCORE`.
