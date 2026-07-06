# Schmerbert

I build small, verifiable environments for AI agents — memory that can be trusted, handoffs that survive a context window, and tests that prove the machinery refuses bad data instead of just claiming to.

## The problem I keep working on

AI assistants forget everything between sessions — and the common fixes make it worse. Memory files rot. Summaries come back as facts. A model's guess gets written down once and every future session inherits it as ground truth. If you've watched an agent confidently misremember something *you never said*, that's the problem.

## The repos

### [TheMarble](https://github.com/schmerbert/TheMarble) — persistent memory and session handoff for AI agents

The main event. A manual plus six working example implementations of **marbles**: small inheritable environments for recurring AI work. Stored context is labeled by provenance (user-decided / model-inferred / unverified), writes to trusted memory pass through executable gates that can refuse, and hostile test suites — 120 tests across four suites — prove the refusals are real. Built and validated across four different AI builders (Claude Fable 5, Claude Code, Cursor, Codex). Start with `START_HERE.md`: ten minutes, one cold demo.

**Use it if:** your agent's memory drifts, your CLAUDE.md contradicts your code, or every new session starts from archaeology.

### [The_Inn](https://github.com/schmerbert/The_Inn) — a writer's memory environment, built in public

A working marble for one long-form writing project — and the whole record of how a marble gets made. The first commit is the complete map with zero construction; every commit after is execution, and the design conversations that produced each decision are in `logs/`, verbatim. Its one law: **nobody puts words in anyone's mouth.** Everything is signed; nothing enters the writer's canon except through their own quoted, dated adopting words; nothing is deleted — superseded material falls into the woods with its ancestry intact.

**Use it if:** you want to see agent memory discipline applied to a real creative project, or you're a model learning how a marble gets built — the history is the curriculum.

### [The_Forest](https://github.com/schmerbert/The_Forest) — AI memory that tracks where text came from

A spec for provenance-aware agent memory: a small constitution (`FOREST.md`) plus a SQLite schema that stores *custody* with the text. RAG retrieves by similarity, but similarity can't tell you whether a sentence was said by the user, guessed by the model, superseded, or rejected. Forest can: every stored entry carries a bucket, a signature, and ancestry, and nothing becomes ground truth without a recorded adoption ceremony. Hostile tests enforce the refusals. **Similarity can retrieve. Similarity cannot promote.**

**Use it if:** you're building RAG or agent memory and need to know *whether to trust* what retrieval returns, not just what matches.

## Reading me with an AI?

Good — these repos were written to be operated by models. Point your agent at [TheMarble](https://github.com/schmerbert/TheMarble), have it read `AGENTS.md`, and ask it to build a marble for a recurring kind of work. The tests will tell you both whether it worked.
