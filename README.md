# Vital API Definition

Tagging a release on this repository will update the:

  - [Python SDK](https://github.com/tryVital/vital-python)
  - [Java SDK](https://github.com/tryVital/vital-java)
  - [TypeScript SDK](https://github.com/tryVital/vital-node)
  - [Go SDK](https://github.com/tryVital/vital-go)

## What is in this repository?

This repository contains

- Vital's OpenAPI spec which lives in the [openapi](./fern/api/openapi/) folder
- Generators (see [generators.yml](./fern/api/generators.yml))

To make sure that the OpenAPI is valid, you can use the Fern CLI.

```bash
npm install -g fern-api
fern check
```

## What are generators?

Generators read in your API Definition and output artifacts (e.g. TypeScript SDK) 
and are tracked in [generators.yml](./fern/api/generators.yml).

```bash
fern generate --group java-sdk --version <release version>
fern generate --group node-sdk --version <release version>
fern generate --group python-sdk --version <release version>
fern generate --group go-sdk --version <release version>
```

## How to preview generated SDKs locally?

```bash
fern generate --group local-preview
```

The generated code would be located at `./generated/`.

## How to make a release? 

To release the generators, create a Github release that is formatted "<language>@<version>". 
So, if you wanted to release version 3.4.0 of the python SDK, the Github release should 
be tagged "python@3.4.0". 

