# ClientOps-Portal
A multi-tenant IT support portal that lets teams manage customer accounts and cases with role-based access control and an audit trail (plus basic alerts) so actions are secure, accountable, and easy to review.

## Vision
SupportOps Portal is a multi-tenant internal portal for IT support teams to manage customer accounts and support cases with role-based access control and an append-only audit trail, plus basic alerting for suspicious or high-risk activity.

The goal is to build a production-minded full-stack app that demonstrates real software engineering practices — authentication, role-based access control, database migrations, testing/CI, and deployment — with a security-minded differentiator: an append-only audit trail and basic alerting on suspicious or high-risk activity.

### Who is it for? 
- Managed IT / tech support teams who handle multiple customer organisations.
- Teams that need roles (Owner/Admin/Agent/ReadOnly) and an audit trail for compliance, dispute resolution, and operational clarity.

### Problem it solves
Support teams often spread customer details, cases, and internal actions across multiple tools or spreadsheets. This portal provides:
- a single place to manage customer records and service cases,
- controlled access (least privilege),
- and a reliable record of “who did what, when” for sensitive actions.

### Core outcomes (what the app will do)
- Users can securely sign in and operate only within their organisation (tenant).
- Owners/Admins can manage users and assign roles.
- Agents can create/update customers and cases/tickets, and add notes.
- Key actions create audit events (logins, role changes, exports, API key changes).
- Audit events are searchable and exportable (admin-facing).
- Simple alert rules detect suspicious patterns (e.g., repeated failed logins, mass exports, unusual access patterns).

### Non-goals (for realistic scope)
- Not a full ITSM product (no deep incident management, SLAs, or complex workflows initially).
- No complex permissions engine beyond RBAC.
- Not a SIEM: alerts are lightweight and exist to demonstrate security-minded engineering.

### How success is measured
- The project runs from a clean clone using documented steps.
- A live demo deployment exists (with demo accounts).
- CI is green and tests cover auth/permissions/audit.
- A short demo video and a brief case study explain architecture and trade-offs.

## Key decisions (living)
- Stack: React + TypeScript (frontend), FastAPI (backend), Postgres (database)
- Local dev: Docker Compose for backend + database
- Schema changes: Alembic migrations only (no manual DB edits)
- Auth model: (choose later) cookie sessions OR JWT + refresh
- Audit: append-only events (no edits/deletes)

