# Product Director Skill

A Codex skill for turning ideas, requirements, AI-generated implementations, feature requests, PRDs, workflows, and code reviews into sharper product decisions.

The skill helps Codex look beyond whether code merely runs. It adds a product-director review lens for user workflow, requirements quality, UX friction, data flow, edge cases, engineering taste, and the common failure mode where AI-generated code optimizes for execution success instead of product correctness.

## What It Is For

Use `product-director` when you want Codex to evaluate or improve:

- Product plans, feature scopes, and PRDs
- AI-generated implementations that may be executable but not product-correct
- UX flows, empty states, failure states, and operational friction
- API contracts, data ownership, permissions, and system boundaries
- Engineering tradeoffs where product behavior matters more than local code shape
- RLVR or executable-code-bias risks such as silent fallbacks, swallowed errors, or overly defensive logic

## Repository Layout

```text
product-director-skill/
├── README.md
├── LICENSE
└── skills/
    └── product-director/
        └── SKILL.md
```

The distributable skill itself is the `product-director` folder. The `SKILL.md` file includes the required frontmatter fields:

- `name: product-director`
- `description: ...`

## Install

### With Codex Skill Installer

```text
$skill-installer install https://github.com/univerSpace2/productive-director-skill/tree/main/skills/product-director
```

After installation, restart Codex to pick up the new skill.

### With the skills CLI

Install from repository discovery:

```bash
npx skills add univerSpace2/productive-director-skill --list
npx skills add univerSpace2/productive-director-skill --skill product-director -g -a codex
```

Or install directly from the skill folder URL:

```bash
npx skills add https://github.com/univerSpace2/productive-director-skill/tree/main/skills/product-director -g -a codex
```

## Verify

Confirm that the installed skill appears under your Codex skills directory:

```bash
ls ~/.codex/skills/product-director
```

The installed folder should contain:

```text
SKILL.md
```

You can also verify that the frontmatter is present:

```bash
sed -n '1,8p' ~/.codex/skills/product-director/SKILL.md
```

## Usage

Once installed and Codex has been restarted, trigger the skill by asking for product-direction work, for example:

```text
$product-director review this implementation for product correctness
```

```text
Use product-director to sharpen this PRD before we create issues.
```

```text
Check whether this AI-generated feature is merely executable or actually correct for the user workflow.
```

## License

This project is released under the terms in [LICENSE](LICENSE).
