# How to X

## Project Management

All projects at the UW Math AI Lab need to culminate in a tangible contribution, such as a research paper or a significant open source contribution. The role of the project leader is to plan the project, keep it on track, and submit the paper/open-source contribution. Project members perform the experiments and report the results.

The leader should spend at least 5 hours a week, with at least 1 hour spent planning, outside meetings. The members should spend 5-15 hours a week (less during exam weeks and more on other weeks).

### Doc

To plan the project and keep it on track, the project leader should make a Google Doc with the project proposal in the one tab and weekly meeting notes in the another tab. Make a copy of the [template](https://docs.google.com/document/d/1H5iHiiPxrOKZBDsisBAIvSP42xxkBcjn2bFcFxEuwhc/edit?usp=sharing) to get started. Two examples: [one](https://docs.google.com/document/d/1K8cSDExXdD9WatxWGj3LZvsvf6gDMi-GTlXRbKkd--w/edit?usp=sharing), [two](https://docs.google.com/document/d/1WpYN8_pDrO3BbSr7FkX-eN4rDBhKxFkKAVyaOYjojf0/edit?usp=sharing). While it is tempting to write the proposal with an LLM, the project leader should write it manually, because it leads to improved understanding of the scope and results in a much higher signal/noise ratio.

### Weekly meetings

Each meeting follows the same protocol:

- (3 minutes) silently write the notes
- (~5-10 minutes per member) tell everyone what you've accomplished since last meeting. Questions and discussion are encouraged. Write TODOs.
- (rest of the time) work on the TODOs.

During the meeting each member must clearly describe their accomplishments and get a clear and specific task. The project leader is responsible for keeping up this protocol and assigning specific tasks.

## Tools

All projects must use a single GitHub repository in the [UW-Math-AI org](https://github.com/uw-math-ai). A single branch is recommended. Each member should be added as a collaborator. To ensure code reuse push often; it also helps minimize merge conflicts.

### Lean

Formalization projects should use

- [LeanSearch](https://leansearch.net/) or [LeanExplore](https://www.leanexplore.com/) to find existing theorems in Mathlib
- [Zulip](https://leanprover.zulipchat.com/) to ask questions to the Lean community
- [Aristotle](https://aristotle.harmonic.fun/) to speed up formalization
- [Mathlib Index](https://leanprover-community.github.io/mathlib4_docs/) to learn the state of the library
- [Lean4Web](https://live.lean-lang.org/) for quick prototyping in the browser

### AI tools

AI projects should use

- [AWS Bedrock](https://aws.amazon.com/bedrock/) (Claude, DeepSeek) or [Token Factory](https://tokenfactory.nebius.com/) (all open source LLMs) or [LiteLLM](https://www.litellm.ai/) (all LLMs) for LLM inference.
- [Tillicum](https://github.com/UWrc/tillicum-onboarding) (GPU, $0.9/hour) or [Hyak Klone](https://hyak.uw.edu/docs/) via [RCC](https://depts.washington.edu/uwrcc/) (CPU, free) or [AWS EC2](https://aws.amazon.com/ec2/) (CPU, cheap and GPU, expensive) for compute and storage. When using Tillicum, you **have to** use [batch jobs](https://hyak.uw.edu/docs/hyak101/basics/nn_batch/#batch-jobs) after the initial debugging.
- [Lean Interact](https://github.com/augustepoiroux/LeanInteract) for interfacing between Python and Lean.

It is also strongly recommended to use

- [Weights & Biases](https://wandb.ai/) for model training logging
- [LangFuse](https://langfuse.com/) for LLM output tracing

Ask Vasily Ilin for API keys.

## Contribute to Mathlib

[Mathlib](https://github.com/leanprover-community/mathlib4) is the standard mathematical library of Lean. It is by far the largest collection of formalized mathematics, and growing it is extremely valuable to the community. Because of mathlib's size and importance, contributing is not an easy process, perhaps even comparable to a small paper.

1. Use [LeanSearch](https://leansearch.net/) and [Mathlib Index](https://leanprover-community.github.io/mathlib4_docs/) to check whether your theorem is already in Mathlib.
2. Formalize your theorem in Lean, yourself or with Aristotle's help. If your theorem is general enough, it belongs in Mathlib
3. Condense the proof to <10 lines or split it up into separate lemmas.
4. Generalize the assumptions, e.g. Ring instead of CRing.
5. Choose the file in Mathlib where your theorem(s) go. Use `#find_home your_lemma_name` in [Lean4Web](https://live.lean-lang.org/). Try not to add new imports.
6. Clone the [UW-Math-AI fork](https://github.com/uw-math-ai/mathlib4) of Mathlib, open it in VSCode and run `lake exe cache get` in the terminal.
7. Put your theorem(s) in the chosen file, make sure it compiles (no red underlines).
8. Use the correct formatting and indentation.
9. Push to GitHub, and open a PR to Mathlib from the fork. Write the correct PR description. Assign the reviewer; choose someone who has contributed to your file, using the commit history.
10. Follow the reviewers' suggestions. Treat the review as a gift, since the reviewers are volunteers. It is also a great learning opportunity. Consider messaging the reviewer on Zulip to thank them and ask for advice. Ping in Zulip or Github if you have not received a review after 3 days.

Read the [contributor's guide](https://leanprover-community.github.io/contribute/index.html) for more details on what to contribute, the recommended workflow, and the naming and style conventions.

## Publish

Most Lean formalizations should aim to result in several Mathlib PRs. Most AI/ML projects should aim to result in a publication at a top conference such as NeurIPS, ICML, ICLR, EMNLP, AAAI, AISTATS, COLM, KDD or a journal such as TMLR, JMLR.

There are three levels of venues:

1. ArXiv pre-print: no review, low prestige
2. Workshop paper + poster: some review, medium prestige, not a publication
3. Conference publication + poster: rigorous review, high prestige

Conference submission deadline is ~5-7 months before the conference. Workshops are announced ~4 months before the conference. Conference review takes ~2-3 months, and workshop review takes ~4 weeks.

### Choose the venue

To choose the venue, look where similar papers have been published and note the submission deadlines. Since a workshop poster is not a publication, you can submit both to a workshop and a conference at the same time.

### Submit

Use the LaTeX template of the chosen conference. Most conference papers are between 8 and 10 pages, excluding references and the appendix. Most conferences and workshops use OpenReview, make an account in advance.
