# Lala Tech — Request Tracker

A lightweight, single-file operations tracker built for Lala Tech LLC to replace
their scattered WhatsApp / email / spreadsheet workflow.

## The Problem

Lala Tech manages client requests across WhatsApp, email, and spreadsheets, with
no single source of truth. This caused:

- Requests getting lost or forgotten
- Follow-ups being missed or delayed
- No clear view of what's pending or who owns it
- Managers manually chasing employees for status updates
- Context scattered across chats, inboxes, and spreadsheets
- Manual, error-prone spreadsheet upkeep

## The Solution

A single-page request tracker — not a CRM/ERP — that gives the team one place to
log, own, and track every client request through its actual lifecycle:

**New Request → Needs Clarification → Ready to Assign → In Progress → Waiting on Client → Done**

The key design decision: requests blocked on the *client* (needing clarification,
or waiting on something from them) are tracked separately from requests blocked on
*the team*. A request waiting on a client response is never flagged as overdue or
"forgotten" the way a genuinely stalled internal task is — because that delay
isn't the team's fault.

## Core Features

- **At-a-glance dashboard panel**: Waiting for Us / Waiting for Client /
  Unassigned / Overdue — the four views a manager actually needs, without asking
  anyone.
- **Automatic staleness detection**: any internally-owned task untouched for 2+
  days is flagged automatically — no manual status-chasing.
- **Per-request context log**: timestamped notes attached directly to each
  request, replacing scattered chat/email history.
- **Filtering & search**: by owner, status, and "our court vs. their court."
- **Zero setup**: single HTML file, no build step, no backend, no dependencies.
  Data persists locally via `localStorage`.

## Running It

Just open `index.html` in a browser — or in VS Code, right-click it and choose
"Open with Live Server" for auto-refresh while editing.

No `npm install`, no server, no database setup required.

## Demo Data

Click **"Load demo data"** to populate the tracker with a realistic set of
requests that demonstrate every part of the workflow, including a request that's
past its due date but correctly *not* flagged overdue because it's waiting on the
client, not the team.

## Impact

- **Manager status-checks**: from manually pinging multiple people → one glance
  at the "At a glance" panel
- **False "overdue" alarms eliminated**: client-blocked requests no longer look
  like forgotten internal work
- **Time to log a request**: ~10 seconds vs. digging it out of chat/email later
- **Spreadsheet maintenance**: fully replaced — no manual upkeep, no broken
  formulas

## Tech

Vanilla HTML/CSS/JavaScript, single file, `localStorage` for persistence. No
frameworks, no build tooling — chosen deliberately to eliminate setup/deployment
risk under a hard time constraint, and to keep the MVP focused on solving the
actual workflow problem rather than infrastructure.
