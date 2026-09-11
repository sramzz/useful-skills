---
name: humanizer
description: Rewrite or edit prose to remove formulaic AI-writing patterns while preserving facts, meaning, and the author's voice. Use when the user asks to humanize text, make writing sound natural, or review prose for AI-like phrasing.
---

# Humanizer

Edit prose so it sounds like a person wrote it. Preserve the source's meaning, claims, names, numbers, dates, quotations, citations, and link targets. Never add factual detail that is absent from the source or supplied context.

## Calibrate the voice

If the user provides a writing sample, study its sentence lengths, vocabulary, punctuation, paragraph openings, transitions, recurring phrases, and deliberate quirks. Match those habits. The sample outranks this skill's default preferences.

Without a sample, use clear, direct language and natural variation in rhythm. Keep the register appropriate to the material. Neutral prose is right for technical, legal, encyclopedic, and reference text. Personality, uncertainty, humor, or first-person stance belong only where the source and genre support them.

## Edit the prose

1. Read the entire source before editing. Identify clusters of AI-like patterns, not isolated words.
2. Preserve information rather than sentence or paragraph shape. Merge, split, compress, or reorder material when that improves the writing without changing its meaning.
3. Prefer specific nouns, active constructions, and simple verbs. Use `is`, `are`, and `has` when an ornate substitute adds nothing.
4. Remove empty significance, promotional language, vague attribution, fake depth, repeated conclusions, chatbot artifacts, canned transitions, and unsupported speculation.
5. Vary sentence length and structure by ear. Do not force symmetrical paragraphs, lists, or groups of three.
6. Preserve quotations, proper names, code blocks, frontmatter, structured data, citations, URLs, and examples that discuss a watched phrase rather than use it.
7. Read [references/patterns.md](references/patterns.md) when performing a full humanization pass or when the prose needs diagnosis. It contains the detailed pattern catalog, false-positive checks, and editing tests.

Do not flatten strong human details, mixed feelings, purposeful repetition, genuine asides, era-specific references, or defensible stylistic choices merely because they are unusual.

## Punctuation and formatting

Avoid em dashes, en dashes, semicolons, excessive bolding, decorative emoji, title-case headings, and inline-header lists unless the user supplied a writing sample that makes them part of the voice or the source requires them. Never alter punctuation inside a quotation simply to satisfy this preference.

Use straight or curly quotation marks according to the source, locale, or user's sample. Do not impose a single quotation style globally.

When editing a file, change prose only. Leave non-prose content and link targets untouched.

## Verify

Before returning the result, check:

- Does every factual claim come from the source or user-provided context?
- Did any name, number, date, quotation, citation, or technical qualification change?
- Does the rewrite still contain clustered patterns from the reference catalog?
- Does it sound natural when read aloud?
- Did the edit erase a distinctive part of the author's voice?
- Are any forbidden punctuation marks left outside protected source material?

If a sentence resists repair, restate its point naturally instead of patching individual words.

## Invocation modes

Choose the mode from the request:

- **Pasted text:** Return a draft rewrite, a short audit of remaining AI-like traits or factual-risk checks, and a polished final rewrite. If the user asks only for the rewritten text, honor that format.
- **File:** Run the draft, audit, and revision internally. Rewrite the file in place so it contains the final version, then report a concise summary. Preserve code blocks, frontmatter, data, citations, and link targets.
- **Embedded:** When this skill is one step in a larger task, run the checks internally and return only the final prose requested by the caller.

Do not add warnings, a recap, or an invitation for more work unless the user asks for them.
