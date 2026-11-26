# RETAINFLOW — MASTER HACKCANTON SEASON 4 BUILD BRIEF

**Repository:** https://github.com/sopskistar/RetainFlow  
**Project:** RetainFlow  
**Primary track:** RWA & Business Workflows  
**Possible secondary track:** Open Track, ONLY if its rules and fit justify it  
**Status:** New project; implement a genuine Canton-native MVP, not a cosmetic prototype.  
**Contest scheduling:** The AppsFactory HackCanton page currently says Season 4 is postponed. Recheck official dates, rules and eligibility, and do not treat the originally advertised 6 December 2026 deadline as confirmed.

## 0. NON-NEGOTIABLE CORRECTION: WHO IS THE CLIENT?

Read this carefully and do not reinterpret the pilot.

**My brother is the MAIN CLIENT/PROJECT OWNER for the first RetainFlow pilot.** He has personal property, including his house, for which he can commission painting work. He can hire and pay one of the painting workers/subcontractors he already works with. **That worker is the CONTRACTOR in our first pilot.** This is a legitimate, real client–contractor relationship. Do NOT require an unrelated homeowner, a wealthy outside client, a construction firm, or an extra party before building or testing RetainFlow.

My brother is also a professional painting contractor in his own business. At other times he wins client jobs, delegates work to his workers, inspects their output and pays them. This explains his expertise, and later provides a useful additional business workflow, but **the first demo starts with him as the CLIENT who hires a worker**. An independent verifier/mediator is OPTIONAL and appears only in a mutually agreed dispute flow.

The project originated from something personal: my brother once used his own funds to complete a painting job and the customer refused to pay afterward. Other tradespeople around us have experienced nonpayment or disputes. Build a serious, fair product that helps both paying clients and the contractors who perform work. Do not exploit or embellish this story or invent quotes, statistics, reviews or actual customer outcomes.

## 1. MISSION AND COMPETITIVE THESIS

Build **RetainFlow: privately agreed work milestones, verifiable completion evidence, controlled dispute resolution and transparent payment obligations for small construction and skilled-trades projects.** It should work for painters first and be adaptable to electricians, plumbers, carpenters, tilers, repair and renovation contractors later.

### Core insight

Payment disputes often begin **before** payment time: an unwritten scope, unclear completion criteria, unauthorized extra work, unacknowledged progress, mismatched expectations about deposits or materials, and no jointly accepted record. A simple invoice, task tracker, chat or wallet cannot solve all these problems.

### Distinctive mechanism — Mutual Commitment Gate

Before the first milestone becomes active, the CLIENT and CONTRACTOR must explicitly accept the scope, total/individual milestone amounts, what counts as done, material responsibilities, due dates and the permitted dispute path. Changes need both parties' approval (or other explicitly agreed authority). Work can be submitted with privacy-preserving evidence hashes and timestamps. Acceptance, rejection with reasons, escalation, agreement amendments and payment-obligation states are governed by real Daml contract choices and authorizations.

Make this an **enforceable workflow / verification product**, not a vague 'blockchain escrow' pitch. It must never say it guarantees payment if no money has been actually funded and controlled by a supported integration. Explore optional genuinely pre-funded milestones later, but do not fake custody, token transfers or deposit guarantees.

### Why Canton rather than an ordinary SaaS database?

Canton/Daml should hold shared, permissioned multi-party commitments; validate who is authorized to create, consent to, reject, amend, arbitrate or fulfill an obligation; and expose a verifiable event history to relevant parties without publicizing all client identities and contractual terms. Prove these properties on the ledger, including **negative tests**. Keep evidence photos/files in authorized off-ledger storage, with hashes/references and limited disclosure on ledger where appropriate. Be precise about what privacy is provided by the ledger versus application/storage controls.

## 2. HACKCANTON RESEARCH MANDATE — RESEARCH BEFORE CODING

Read the current official organizer material at https://appsfactory.cc/hackathons and applicable linked rules; determine the actual status, eligibility, dates, judging criteria, accepted technologies, submission fields, team rules, video requirements, permitted existing code, track prizes and network rules. Recheck closer to submission. The older Season 4 brief provided this structure: Problem -> ICP -> Validation -> GTM -> MVP -> Pitch; five tracks; up to two tracks; online program; DevNet support; AI optional. RWA & Business Workflows expects an **end-to-end workflow (create -> update status -> transfer/fulfill -> audit/report)**, role-based UI, 1-page business brief (ICP, buyer, why Canton), and a 2–3-step pilot plan/integrations. Treat these as initial source-provided requirements until you verify the latest published rules. The advertised prize pool was **up to $50,000 in cash AND credits**; do not call it $50,000 guaranteed cash.

Research previous seasons and competing submissions. In Season 3 the reported overall winners were Canborsa Lending, Exodus and Tavryn; PledgeGuard won the RWA/Business Workflows track; Plimsoll and Alluvren won other tracks. Inspect what PledgeGuard and Tavryn actually implemented before finalizing positioning. Also look for construction payment, escrow, invoice financing, retention, milestone/payment approval and dispute-resolution apps both on and outside Canton. Prepare a concise **competitor matrix**, including established alternatives (contracts + bank transfers, invoicing software, project-management tools, escrow systems) and adjacent Canton competitors, with evidence-backed comparisons and an honest gap. Do not invent an empty competitive field. Be able to answer seven questions:

1. Who suffers, and what independently observed evidence supports the pain?
2. What surprising insight makes our approach different?
3. Which specific mechanism is differentiated and native to Canton?
4. What makes people return or pay for it?
5. What actual, reproducible multi-party execution can judges see?
6. What can be realistically built in our available time and tools?
7. How does it match the specific track, judges, sponsor expectations and a credible pilot?

Produce `docs/HACKCANTON_RESEARCH.md`, `docs/COMPETITOR_MATRIX.md`, `docs/PRODUCT_THESIS.md`, and `docs/SUBMISSION_REQUIREMENTS.md`. Clearly distinguish verified organizer statements, facts from sources, hypotheses, decisions and still-unknown requirements. Don't let research turn into indefinite delay; move into implementation promptly.

## 3. AUTHENTIC PILOT DESIGN — NO OUTSIDE CLIENT REQUIRED

Primary demo/first pilot:
- **Client:** My brother, acting as the owner of his own house or another property he controls, commissioning a painting job and owing payment.
- **Contractor:** One consenting real painting worker he hires for the job, with a separate login/ledger identity.
- **Independent reviewer:** Optional third party only if both sides select and authorize one for a disputed milestone. A project should work fully without one.
- **Project:** A small interior/exterior painting assignment with a documented scope, agreed price in **NGN**, materials and labor responsibilities, 2–3 milestones, due dates and acceptance standards.

Use plausible **explicitly fictionalized sample values**, e.g. ₦120,000 labor divided into clearly labeled milestone amounts. Do not imply the sample figures are an actual signed contract. In live pilot, capture only information that brother/worker consent to disclose. No requirement to bring a 'big man' outside client. No requirement to send real money or use a $20 deposit to prove eligibility. The zero-spend technical demonstration should use real Canton ledger operations and only sample amounts/test assets; actual currency settlement is a separate, opt-in integration milestone.

Interview my brother and a worker (if they consent) about prior agreements, nonpayment, inspections, change orders and what they would actually use. Include interview templates, a consent checklist, a pilot observation log and feedback questions. No invented interviews or fake testimonials. Keep personally identifying client data out of source control and public sample assets. Keep genuine user tests distinct from synthetic E2E tests and distinguish self-reported savings from measured metrics.

## 4. END-TO-END PRODUCT REQUIREMENTS

### Roles and permissions

- Client/project owner: creates invite/agreement, proposes scope, reviews/accepts/declines changes, reviews work evidence, approves milestones or opens justified disputes, attests payments where relevant.
- Contractor/worker: accepts/declines terms, views entitlements, submits progress and evidence, proposes change orders, responds to disputes, acknowledges payment.
- Optional neutral reviewer: can see only disputes/records to which explicitly authorized; can record an agreed recommendation or binding decision **only under rules both original parties consented to**.
- Service admin: maintains operational health, **cannot impersonate clients, forge consent, seize funds, rewrite agreement history or override Daml authorizations**.

### Critical workflow (must really execute on Canton)

A. Client drafts scope, milestones, amount and acceptance criteria and invites worker. Drafting can be off-ledger, but an actual proposal/commitment must be on ledger.  
B. Worker reviews and explicitly accepts or declines; an active agreement cannot be manufactured by the client acting for the worker.  
C. Work milestone starts; contractor submits evidence metadata/hash, notes and completion claim.  
D. Client approves, requests correction or raises a dispute with a recorded reason. No silent or unilateral rewriting of the agreed amount or scope.  
E. If approved, record a clear **payment obligation or release authorization**; if disputed, document response/escalation/settlement under legitimate agreement rules.  
F. Record actual payment only with appropriately labeled verified proof or separate mutual acknowledgement; NEVER represent a self-reported payment as confirmed bank settlement or on-ledger transfer.  
G. Close the job when milestone obligations are handled, and display a private timeline/exportable audit summary containing verifiable ledger identifiers.

### Differentiators with sensible priority

**Must-have:** Mutual Commitment Gate; bilateral scope/price acceptance; contractor proof-of-work pack; enforceable approval/dispute state machine; role privacy; ledger evidence view.  
**Strong next additions:** mutually signed change orders; time-bounded dispute escalation only if reliable time/oracle rules are proven; explicit materials advance versus labor classification; partial completion and proportional milestone approval; evidence export; mobile-first WhatsApp-compatible invitation links (links only, no WhatsApp API required).  
**Later, not in MVP unless robust:** verified escrow/custody, true on-ledger token settlement, bank/PSP integrations, automatic release of real money, third-party arbitration businesses, payment financing, KYC/AML procedures, AI adjudication, elaborate reputation scoring, on-chain RWA issuance for buildings.

### Payment and money safety

Separate states: `No funding claimed`, `Funding claimed but unverified`, `Funding externally verified` (only if a genuine verification adapter exists), `Test asset funded` (if verifiable on supported test environment), `Milestone approved`, `Payment due`, `Payment self-reported`, `Payment mutually acknowledged`, `On-ledger paid` (ONLY on actual supported transfer proof). Label every surface clearly. **A recorded agreement is not escrow; an authorization is not a transfer; a transfer is not a bank deposit.** No private keys or funds held by RetainFlow. If evaluating a future token integration, study Canton Token Standard/CIP-0056 and official wallet APIs and confirm deployed compatibility. Do not ask me to deposit money or buy a host without prior permission.

### UX and product pages

Public landing page with authentic founder story (no unsupported claims), how it works, specific benefits to both client and contractor, transparent demo status, a clear call to action. Signed-in app: overview, jobs, create job/agreement wizard, invitation/acceptance, milestone detail + evidence, change orders, disputes, audit timeline/export, identity/settings, network/data-health page. Separate client and contractor perspectives, contextual education in plain English, mobile-first inputs, NGN formatting, clear time zones, accessible states. 'Network Connected' status must derive from an actual health check.

## 5. CANTON IMPLEMENTATION AND REPRODUCIBLE EVIDENCE

Start with current official docs:
- https://docs.canton.network/llms.txt (WARNING: Daml 2.x is outdated; use Canton/Daml 3.x docs)
- https://docs.canton.network/shared/version-compatibility-dashboard
- https://docs.canton.network/appdev/quickstart
- https://docs.canton.network/sdks-tools/development-tools/localnet
- https://docs.canton.network/appdev/get-started/choose-your-path
- https://docs.canton.network/overview/learn/privacy-model
- https://docs.canton.network/appdev/modules/m3-dev-environment
- https://docs.canton.network/sdks-tools/api-reference/ledger-api
- https://docs.canton.network/appdev/quickstart/deploy-to-devnet
- https://github.com/digital-asset/cn-quickstart
- https://github.com/canton-network/wallet/tree/main/sdk/dapp-sdk

Before pinning versions or choosing SDKs, verify compatibility for the actual node, network, wallet and package releases. Prefer official, maintained 3.x tooling and validate instructions against source documentation rather than outdated snippets. For a new project, **do not paste an entire unrelated starter UI as the product**. You may use its LocalNet stack or adapt its working multi-party patterns and replace the application with the original RetainFlow architecture.

Propose the simplest sound architecture for my Windows + WSL Ubuntu development environment, likely Daml contracts + supported JSON Ledger API backend/adapter + Next.js/TypeScript UI + optional PostgreSQL (Neon) for off-ledger metadata. Vercel may host the UI/BFF, but it is not a Canton participant/validator host. Keep ledger connectivity real and document how a deployed site reaches a running node or managed DevNet service. Do not expose node admin APIs, tokens, signing secrets, unsafe development JWTs or files publicly. Support local Docker Compose and write precise start/stop/troubleshooting commands. Use cloud infrastructure only where genuinely necessary and with free tooling where possible.

Design and test the following possible Daml model (adapt to valid Daml patterns): proposal, active bilateral agreement, milestone obligation, submitted evidence hash, review/approval, disputed milestone, mutually consented amendment, payment status/receipt and final audit representation. Choose signatories, observers and controllers with real privacy/authorization semantics; avoid invalid or overexposed party visibility. Document the actual state machine and why it satisfies the RWA track `create -> status -> fulfill -> audit` demand. If a proposed transition is impossible or unsafe, simplify it and explain why.

**Required negative tests:** Client cannot accept for the worker; worker cannot approve their own milestone as client; outsider cannot read protected job terms or exercise choices; unilateral price/scope amendment fails; duplicate finalization or duplicate receipt cannot silently occur; unresolved dispute cannot be bypassed by inappropriate actor; client cannot claim verified payment without required evidence; compromised frontend state cannot override on-ledger rules. Also test happy path, revisions, rejection, appeal, data validation, amount rounding, idempotency, retries and time/date transitions.

Provide evidence containing network/environment, package/build IDs, parties, commands, contract IDs, transaction/update IDs where available, actual responses, negative test outputs, reproducible scripts and screenshots/video of real moving interaction. Do not leak secrets or private documents. Keep evidence under `docs/PROOF/` and include `docs/CANTON_ARCHITECTURE.md`, `docs/CONTRACT_STATE_MACHINE.md`, `docs/SECURITY_AND_PRIVACY.md`, `docs/DEPLOYMENT.md`, `docs/TEST_RESULTS.md` and `docs/DEMO_RUNBOOK.md`.

## 6. BUILD CHECKPOINTS — IMPLEMENT, DO NOT JUST PLAN

Implement in small, independently tested checkpoints, preserving working code and making sensible commits. **Do not stop after producing only a plan**; complete as much of the functional vertical slice as the environment allows, and clearly report external blockers.

- **M0 — Foundations:** inspect repo/tools/skills; research and competition matrix; architecture decision record; scaffold; lint/typecheck/test/CI; clear README and `.env.example` without secrets.
- **M1 — On-ledger baseline:** working Daml contract + executable bilateral proposal/acceptance + negative authorization test on LocalNet.
- **M2 — Full milestone chain:** submit work, attach evidence hash/reference, approve/request correction/dispute, resolve according to rules, record legitimate payment obligation; actual contract state transitions and tested event history.
- **M3 — App integration:** identity/party mapping, API server, authenticated client and contractor UI; no fake read/write paths; complete real ledger interaction.
- **M4 — Pilot-ready evidence:** brother-as-client + worker-as-contractor test scenario, seeded synthetic example, usable mobile workflows, screenshot/video capture, independent contract/transaction checks, recovery from failed requests.
- **M5 — Product and submission:** polish design; accessibility, security and responsive QA; 1-page business brief, credible GTM, pilot plan, competitor comparison, technical architecture and evidence links; submission checklist.
- **M6 — Video WHEN REQUESTED or officially required:** storyboard, genuine screen recording, cinematic product demonstration and verified playable MP4, under organizer time limit. Don't spend early development cycles on a final video while ledger features are broken.

If DevNet provisioning is unavailable, document the exact access blocker, keep verified LocalNet proof and a runnable DevNet deployment path; do not claim DevNet success. Production/MainNet is not automatically required unless official current rules say otherwise.

## 7. VALIDATION, BUSINESS CASE AND PITCH MATERIALS

Create usable artifacts:
- `docs/VALIDATION_PLAN.md`: 20-minute interview questions for brother (actual homeowner/client and experienced contractor) and one of his real workers; non-leading questions; no invented findings.
- `docs/PILOT_PLAN.md`: (1) brother commissions or authorizes a small painting task; (2) one consenting worker accepts and records real/rehearsal progress with permission; (3) both test approval/payment recording and provide candid feedback. Consent and synthetic/live boundaries explicit.
- `docs/BUSINESS_BRIEF.md`: 1-page ICP, evidence of pain, product, why Canton, who buys (small contractors, homeowners, property managers), simple potential pricing hypotheses, buyer acquisition channels, business risks, 2–3 pilot steps, and next integrations.
- `docs/PRODUCT_METRICS.md`: define measured onboarding time, agreement acceptance time, task completion rates, dispute cycle, successful authorized vs rejected transitions. Never claim money was recovered or payments prevented without actual evidence.
- `docs/PITCH.md`: concise story from real brother's experience -> shared problem -> actual user -> distinct mechanism -> working verified demo -> revenue hypothesis -> expansion route -> clear request to accelerator/judges.
- `docs/HACKATHON_SUBMISSION.md`: accurate URLs, demo runbook, technical evidence, team, track rationale, limitations, actual user testing (if completed), and status matrix.

Ask early whether the product is compelling even without crypto. Validate whether clients and workers would sign and use it; avoid treating a family-member test as independently proven demand. Avoid unnecessary guarantees regarding Nigerian contract enforcement, labor law, escrow regulation or payment providers. If AI improves the app, keep it assistive (e.g. help draft scope/acceptance criteria) and subject to review; avoid autonomous legal decisions or fake advanced AI.

## 8. MASTER CREATIVE DIRECTION — UI, BRANDING, ANIMATION AND DEMO VIDEO

### 8.1 Discover and use installed GLOBAL Codex skills

Before design or video work, inspect the installed skill directories and use compatible existing global skills, not guesses:
- Hallmark
- Impeccable
- UI UX Pro Max
- Premium UI Design
- Brand Identity Studio
- Frontend Motion Design
- Frontend Visual QA
- Design System
- Remotion Agent Skills
- Hackathon Video Studio

Reuse installed skills, dependencies and my global Creative Studio; do not reinstall working tools or create needless duplicate setups. If a skill is absent, report this accurately and continue using existing available tools.

### 8.2 Research strong design references

Inspect public, free reference material from:
- https://www.framer.com/marketplace/templates/
- https://21st.dev
- https://recent.design
- https://mobbin.com
- https://landdding.com
- https://motionin.design
- https://60fps.design
- https://reactbits.dev
- https://magicui.design
- https://beui.dev
- https://ui.shadcn.com
- https://footer.design
- https://backgrounds.supply

Study typography, layout, density, spacing, mobile navigation, clarity of complex transactions, form design, composition, data hierarchy, branding and subtle motion. Browse only legally accessible references, don't buy templates or copy restricted assets. Use reference research to establish an **original RetainFlow identity** suited to trustworthy trades, building work, accountability and simple financial operations. Avoid generic AI-looking SaaS pages, random gradients, meaningless glassmorphism, repetitive cards and a generic AI chatbot interface.

### 8.3 Professional brand identity

Use Brand Identity Studio for thoughtful original icon concepts, a unique icon-only mark, wordmark, scalable SVG, PNG assets, light/dark variants, chosen type and palette, favicon/app icons, social/Open Graph image, GitHub repo preview and video intro/outro assets where relevant. Consider visual metaphors like measured progress, a jointly completed handoff or two sides agreeing—without blindly choosing a shield, hexagon, blockchain cube, lock or stock fintech icon. Use free and properly licensed fonts/assets. Preserve any later approved brand rather than casually replacing it.

### 8.4 Interaction and motion

Use Frontend Motion Design and selectively inspect React Bits, Magic UI, beUI and 60fps.design. Support polished page and state transitions, microinteractions, onboarding, loading/success/error states, thoughtful scrolling, and where appropriate card flips or animated diagrams. Motion must improve clarity, never interrupt financial work. Honor `prefers-reduced-motion` and optimize low-powered mobile browsers. Build forms and role views that people with minimal technical knowledge can actually use.

### 8.5 Hackathon video — only when requested or required

Use the global Hackathon Video Studio and `~/hackathon-video-studio`. Inspect exact official duration/format rules, verified implementation and actual proof. Choose the right style for RetainFlow from cinematic product launch, animated explainer, page/card flip, keynote presentation, technical architecture animation, real product walkthrough, 3D, or hybrid; do not impose the same style as other projects.

Before rendering, write a storyboard, narration, timed scene list and visual direction. Use Remotion, official Remotion Agent Skills, Playwright, FFmpeg/FFprobe and optionally Three.js or other properly licensed free tools. **Record the actual moving product interface**, genuine signed multi-party actions and ledger proof, synchronized with narration, clear zooms and restrained animated overlays. No slideshow pretending to be a live demo, fabricated payments, fake testimonials, simulated MainNet claims, unlicensed music or paid APIs. Render and verify a playable 1920x1080, 30fps, 16:9 MP4 unless the event requires different output. Test the exported file with FFprobe, inspect selected frames and audio synchronization; publish only verified claims.

### 8.6 Visual and functional quality gates

Before frontend completion: inspect real screenshots at desktop, tablet and mobile widths; run Hallmark and Impeccable critiques; fix typography, layout, spacing, hierarchy and composition; verify accessibility, keyboard navigation, contrast, broken states and reduced-motion; test real forms, actions, routing, authentication, ledger states, loading, reconciliation, and responsive behavior. Use Playwright browser flows and attach real evidence. Don't claim tests or a visual/video audit passed unless executed.

## 9. SECURITY, REPRODUCIBILITY AND BUDGET RULES

Use only free tools and resources for now; do not purchase hosting, APIs, voice credits, domain names or custody services. Never ask for or commit production private keys. Keep separate dev/demo/prod configurations; safe session handling; least-privilege identity binding; secure file upload; rate limiting; input validation; scoped authorization, secure webhooks if later adopted; signed/approved actions; audit-friendly error handling; backup/recovery documentation. Secrets must be `.gitignore`d and never exposed through Vercel/browser logs. Avoid storing raw client names, addresses, actual financial details or personal photos in a public repository. If the first verified prototype is local-only, be honest and provide runnable commands, not a deceptive live status. Do not create unverified claims, testimonials, links or proof screenshots.

Generate accurate README with business story and technical diagram, setup prerequisites, tool versions, local run, contract build/test/deploy, authenticated usage, limitations, verification evidence and screenshots of actual implementation. GitHub Actions should run suitable build, unit, Daml tests and lint where possible; explain if CI cannot spin up LocalNet economically. Make each milestone reversible and protect prior passing tests. Avoid putting unrelated project code in this repository.

## 10. WHAT TO DO IMMEDIATELY

1. Inspect the new `RetainFlow` repository, working tree, installed skills, Ubuntu/WSL, Docker and available Canton tooling.
2. Validate the HackCanton status and track rules, official Canton docs and current version compatibility; write minimal research and architecture files.
3. Choose a real Canton-first stack and a tight milestone state machine for **BROTHER AS CLIENT / HIRED PAINTER AS CONTRACTOR**.
4. Implement M0 and M1 immediately. Run and record actual Daml unit and ledger tests; if environment allows, continue into M2 and a minimal vertical slice without waiting for routine approvals.
5. Show a concise end-of-run report: commits/files changed; research sources; tests and ledger commands actually executed; proof links/IDs; screenshots inspected; what remains mocked/unverified; concrete blockers; next checkpoint.

**North-star demo:** A real client creates a painting agreement, an independent worker accepts it, the worker submits evidence, the client issues an authorized approval or recorded dispute, the ledger rejects a prohibited action, and RetainFlow displays an honest audit trail and payment obligation. The app must be credible and understandable to my brother and his workers—not just attractive to blockchain developers.
