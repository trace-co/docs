# Documentation agent instructions

## Project context

This is the documentation site for **Trace OCR**, a REST API for text detection and recognition. The docs are built with [Mintlify](https://mintlify.com/) and hosted from the `trace-co/docs` repository.

The API source code lives in a separate repository.

## Mintlify basics

- Configuration lives in `docs.json` — check it before making structural changes
- Use MDX format for documentation pages
- Run `mint dev` locally to preview changes before committing
- Run `mint broken-links` to check for broken links

## Content conventions

- The API has four endpoints: `/ocr`, `/detection`, `/recognition`, `/kie`
- API reference pages are auto-generated from `api-reference/openapi.json` — do not create manual endpoint pages
- To update the API reference, re-export the OpenAPI spec from the FastAPI app
- Always refer to the product as "Trace OCR"
- Detection models are specified via the `detection_model` query parameter
- Recognition models are specified via the `recognition_model` query parameter
- Geometry values are normalized floats between 0 and 1

## Mintlify components

Use Mintlify's built-in components for consistent formatting. See https://www.mintlify.com/docs/components for all available components.

## Style and formatting

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- When referencing UI elements, use bold: Click **Settings**
- Use code formatting for: file names, commands, paths, and code references

## Code examples

- Include language identifiers in fenced code blocks
- Use `CodeGroup` to show curl, Python, and JavaScript variants
- Show realistic parameter values, not placeholders like `foo` or `bar`
- File upload examples should use `multipart/form-data`

## Content structure

- Add frontmatter (`title`, `description`) to every page
- Use `sidebarTitle` in frontmatter if the nav title should differ from the page title
- Include introductory context before diving into steps or details
- The reusable snippet `snippets/supported-formats.mdx` lists accepted file types

## What to avoid

- Don't edit `docs.json` without understanding the navigation structure
- Don't remove existing pages without checking for inbound links
- Don't use HTML when an MDX component exists for the same purpose
- Don't add pages to navigation that don't exist yet
- Don't create manual API endpoint pages — they are generated from the OpenAPI spec
