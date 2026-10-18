# Podcast Studio - Stakeholders and Real-world Scope

## Part 1 - Project snapshot

Podcast Studio - Daily Lesson Recapper was built to help bootcamp students revisit large volumes of lesson notes through short audio summaries. Its intended beneficiary is a student who wants to review course material while commuting or doing everyday activities. According to the supplied project summary, Sergii and PietFALB completed an educational MVP that accepts TXT, Markdown, text-based PDF, and pasted text, then generates a transcript and downloadable MP3 through a Python/Gradio pipeline using OpenAI. The reported delivery includes Lesson Recap and Exam Preparation with three self-check questions and answers, target durations of three or five minutes, demonstration assets, documentation, a five-slide presentation, and 14 passing automated tests. These are team-reported outcomes; permanent public hosting, actual course submission, and the final grade are not confirmed.

## Part 2 - Stakeholder impact

**Context:** the developers and educational setting are reported in the summary; learner needs are the project's intended value proposition, not validated interview findings. Client, operations, privacy, and budget roles below are prospective roles for a hypothetical education-provider rollout, not people already appointed or consulted. Direct/indirect describes contact with delivery or use; High/Low influence and interest are analytical judgments for that rollout, not measured ratings.

| Stakeholder | Contact | Role / relationship | Need from the outcome | Risk if ignored | Influence | Interest |
| --- | --- | --- | --- | --- | --- | --- |
| Student learner | Direct | Intended user of lesson recap and exam preparation | Understandable, source-faithful revision material with transcript access | Fluent but incorrect audio may reinforce misconceptions | Low | High |
| Sergii and Pieter | Direct | Reported two-person delivery team; potential initial maintainers | Reproducible setup and bounded maintenance responsibilities | Environment drift and unsupported requests consume delivery time | High | High |
| Ironhack instructor / assessor | Indirect | Educational evaluator, not a confirmed commercial sponsor | Clear evidence of the delivered MVP and honest limitations | Demonstration readiness may be mistaken for production readiness | High | High |
| Prospective education-provider sponsor | Indirect | Would authorize pilot scope and acceptance | Evidence of useful revision within agreed quality, time, and spending limits | An open-ended feature list replaces a usable, bounded pilot | High | High |
| Prospective IT / operations owner | Direct | Would run the service and handle incidents after handoff | Deployable configuration, safe diagnostics, recovery instructions, and explicit ownership | Failed generations become prolonged outages with no responder | High | High |
| Prospective privacy / security reviewer | Indirect | Would assess uploaded lesson content and access boundaries | Documented data flow, controlled access, and demonstrable deletion | Sensitive notes or transcripts may be exposed or retained unexpectedly | High | Low |
| Prospective budget owner / finance | Indirect | Would fund API usage and infrastructure | Usage visibility and enforceable spending limits | Long inputs, retries, or repeated generation create unplanned charges | High | Low |
| Learner with hearing or access needs | Direct | Easy-to-forget user who may depend on transcript and accessible controls | Usable transcript and keyboard-accessible generation/download flow | An audio-focused design excludes a learner despite nominal feature completion | Low | High |
| Teacher / lesson-content owner | Indirect | Supplies or owns material used for revision | Appropriate use of material and a clear distinction between source and generated explanation | Misleading summaries may be attributed to the teacher or unauthorized material reused | Low | High |

**Who needs attention first:** before any external pilot, involve the prospective sponsor, delivery team, and operations owner to agree boundaries and ownership; involve privacy/security and finance early because they can block a safe, funded launch even if their routine interest is low. Give learners, including those with access needs, an early opportunity to review outputs and the interface, and ask a teacher to review sample accuracy: low formal influence must not mean low priority. Keep the assessor informed about the educational evidence separately from any proposed client acceptance. The access-needs row is the optional stretch stakeholder: an available transcript alone does not prove the whole workflow is accessible.

## Part 3 - From demo to real project

Each paragraph distinguishes the summary's current-state evidence from a proposed rollout change; missing evidence is not proof that a control is absent.

### 1. Operations

The summary reports local Windows/macOS checks, staged progress messages, and API error handling, but does not confirm permanent hosting, service monitoring, backups, or an on-call owner. A rollout would require an assigned operations owner, failure and latency monitoring that excludes lesson content, an incident/recovery runbook, and tested restoration of configuration and any retained artifacts. Pipeline percentages would remain stage indicators rather than service-health measurements.

### 2. Security and review gates

The summary describes keeping the API key in an excluded `.env` file with a safe `.env.example`, while user accounts and access management are not implemented. Before a restricted pilot, the team would establish authenticated access, server-side secret management, upload limits, and a documented security/privacy review of the actual data flow and external processing. Access-denial and secret-exposure checks would become acceptance evidence; no compliance certification or legal conclusion is asserted here.

### 3. Data lifecycle

The summary distinguishes committed demonstration assets from runtime MP3 output excluded from Git, but does not establish retention or deletion rules for uploaded documents, transcripts, or audio; exclusion from Git does not establish deletion. A rollout would document where each artifact travels and is stored, who can access it, and how local and provider-side handling is verified, then implement and test an agreed retention/deletion policy. The proposed first pilot would use approved non-sensitive lesson material and synthetic evaluation fixtures, not assume that classroom inputs are suitable production data.

### 4. Handoff and support

The team reports an updated README, demo source/script/MP3, and 14 passing tests, most using mocked API calls, alongside reported manual end-to-end checks. Client handoff would add a named support owner, installation and troubleshooting walkthrough, a versioned release reference, and an explicit support boundary for API quota, model access, and environment failures. Acceptance would require client staff to reproduce the approved workflow and recovery steps without the original developers; a passing test count alone would not constitute handoff.

### 5. Scope, quality, and accessibility

The MVP supports two modes and transcript/audio output, but exact duration, OCR, automated factual verification, and production accessibility validation are not established as delivered capabilities. The first pilot would retain the supported text formats and both modes, exclude scanned PDFs and exact-duration guarantees, and evaluate generated recaps and the three exam questions against approved source material using human review. Keyboard navigation, readable transcripts, unsupported-input behavior, and understandable API-failure messages would be checked explicitly, while learning gains and multilingual performance would remain unproven until evaluated.

### 6. Cost and capacity

The summary reports reliance on paid API access and a resolved model-access error, without recorded total spending, latency benchmarks, or concurrent-user capacity. Before a pilot, the budget owner and team would agree a spending ceiling and input/concurrency limits, measure cost and latency per completed podcast, bound retries, and pause generation when the ceiling is reached. These are proposed controls, not a detailed cost model or a claim that the original project exceeded its budget.

## Part 4 - Revision brief

### Before - retrospective reconstruction, not a recorded kickoff statement

At the start, we would have described success as helping students revise lesson notes conveniently by delivering a working text-to-podcast MVP within the bootcamp project window and the capacity of a two-person team. We would have focused on the visible workflow: submit supported notes, generate a concise lesson recap, and play or download the MP3, with a reproducible demonstration and documentation. The summary does not provide an approved original baseline, exact schedule, or budget, so this paragraph reconstructs likely framing rather than inventing a historical commitment.

### After - proposed next engagement, not completed work

We would reframe the next engagement as enabling a restricted group of students to review approved non-sensitive lesson material reliably, with source-faithful content and an accessible transcript, before considering a public service. We would retain the delivered modes and text formats, exclude OCR, exact audio timing, user history, and public launch, and require sponsor agreement on a pilot window and spending ceiling before work begins. Proposed acceptance would require both modes to pass an agreed, versioned fixture set with teacher review of recap accuracy and all three exam questions/answers, a successful keyboard-only workflow, verified deletion and access controls, enforced spending limits, and a support-owner handoff; thresholds and dates must be agreed rather than presented as already achieved. Any additional feature would be assessed for its effect on quality, time, and cost, approved by the sponsor, and reflected in the versioned scope and acceptance checklist before implementation.

## Lab checkpoints - in the required order

- [x] **Recognize:** named Podcast Studio and identified a student learner as the intended beneficiary (Part 1).
- [x] **Apply:** nine stakeholder rows include role, need, risk, and High/Low influence and interest (Part 2).
- [x] **Integrate:** six distinct demo-to-real dimensions describe current evidence and concrete changes (Part 3).
- [x] **Verify:** before/after shifts success from a demonstrable MVP to a bounded pilot with acceptance gates and ownership (Part 4).
- [x] **Stretch (optional):** included a learner with access needs and explained why that stakeholder matters (Part 2).
