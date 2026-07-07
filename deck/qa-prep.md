# Signal — Q&A prep (20 minutes with the panel)

## The two override anecdotes (rehearse as 20-second stories)

**1 · The auto-resolve refusal.** "During ideation the model proposed auto-resolving *low-risk* security events — statistically sensible, and exactly how trust dies. I made human-in-the-loop structural: Security is *locked* from auto-handling in the controls, not just discouraged. You can see the locked toggle in the prototype."

**2 · Auditing the auditor.** "Near the end I turned the design skills and our own competitive research on my own prototype — 17 findings. But I still overrode the tool twice: I kept the em-dashes in notification titles where they read naturally, and I rejected a suggestion to soften the destructive-red revoke button. The audit is evidence; judgement is the filter."

## Anticipated questions

**Why an admin center and not something in Xero's world?**
Deliberate. The panel are the domain experts on accounting — any simplification gets critiqued on realism instead of design. An Atlassian-style admin center keeps every property that matters (B2B, small business, money-adjacent, can't-miss-criticals) while the argument stays about *notification design*. And the pattern transfers: Xero has an org/subscription admin surface too.

**How does the severity scoring actually work?**
Today: a typed rules table — event type × scope × anomaly signals → severity + impact. That's honest scaffolding, and it's deliberately the *interface* a real model plugs into later. The tiers, the "why now" line, and the activity log don't change when the model does — which is the point: the trust surfaces are model-independent.

**What happens when the AI is wrong?**
Three answers, in order: it never auto-acts on security/access (wrong = a bad *recommendation*, not a bad *action*); everything it does autonomously is in the activity log with one-tap undo; and the false-interrupt rate and AI-accept rate are first-class HEART metrics — being wrong is measured, not hidden.

**Why wouldn't Mara just use PagerDuty / Opsgenie?**
Those are on-call tools for ops teams — rotas, escalation policies, configuration-heavy. Mara is the anti-persona for that: no team, no rota, no appetite for setup. Signal borrows their best idea (severity routing) and deletes the configuration. For the *enterprise* archetype we route *into* PagerDuty/Slack rather than compete with them.

**How does this scale to the enterprise admin?**
Same engine, different delivery: multi-admin dedupe, team routing, governance/audit exports, and channels they already run (SIEM, Slack, PagerDuty). It's board 05's journey — deliberately sequenced after Mara because the SME owner is the harder trust problem.

**Isn't the digest just burying things?**
The digest is *earned* by the routing rule: anything that needs a human never lands there — it breaks through or gets a timed push. And the digest states its own negative: "0 need you" is information, not absence. Silence is visible by design.

**What would you validate first with real users?**
Whether Mara *believes* "Handled for you" — the let-go metric. One observed session each with five admins: do they open the activity log to check the AI's work, and does that checking *decrease* over two weeks? That's trust, measured.

**How did you use AI, concretely?**
One MD master-prompt defined the process with hard checkpoints. Between gates AI did divergence (18 ideas), competitive sweeps (26 cited Mobbin patterns), board and prototype generation, and a self-audit. At the gates — context, archetypes, problem selection, the A+B-now-C-later call, wireframe direction, which audit findings to apply — every decision was mine, and they're all in the decision log.

**Why three tiers and not a ranked list?**
Tried it (board 21 shows the options). A single ranked list makes rank 4 look almost as urgent as rank 1; tiers encode *kind* of attention — decide now / verify later / read at your rhythm — which is the actual mental model split. Filter chips cover the domain-navigation need.

**What's the business case?**
Missed criticals are breaches, outages and suspended subscriptions; alert fatigue is silent churn of trust in the platform. Fewer missed criticals + fewer false interrupts → admins trust the hub → retention and expansion. The HEART board ties every experience metric up to that north star.
