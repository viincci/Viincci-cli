# Viincci-cli 

[![PyPI version](https://img.shields.io/pypi/v/vinci-cli.svg)](https://pypi.org/project/vinci-cli/)
[![Python Versions](https://img.shields.io/pypi/pyversions/vinci-cli.svg)](https://pypi.org/project/vinci-cli/)
[![License](https://img.shields.io/github/license/yourusername/vinci-cli.svg)](LICENSE)

> A Python-based command-line interface tool for quickly scaffolding projects and automating development workflows.
> Note the code already exist I am just doing a slow upload unless I get another contributer
## 🎨 Overview

`viincci-cli` is a developer productivity tool designed to eliminate boilerplate and automate repetitive tasks. Named after Leonardo da Vinci, who combined art and engineering, this tool aims to bring the same creative efficiency to your development process.

- **Project Scaffolding**: Create new projects from customizable templates
- **Workflow Automation**: Define and run common development tasks
- **Flexible Templating**: Use built-in templates or create your own
- **Language Agnostic**: Templates for Python, JavaScript, and more

## 🚀 Installation

```bash
pip install viincci-cli
```

Or install with advanced features:

```bash
pip install "viincci-cli[full]"
```

## 🛠️ Quick Start

### Create a new project

```bash
viincci new python-package myproject
```

This command creates a new Python package project named "myproject" using the built-in template.

### List available templates

```bash
viincci template list
```

### Run a development workflow

```bash
viincci run test-and-lint
```

## 📋 Commands

### Create a new project

```bash
viincci new [template] [project-name] [options]
```

Options:
- `--output-dir, -o`: Specify output directory
- `--variables, -v`: Set template variables (format: KEY=VALUE)
- `--skip-hooks`: Skip post-creation hooks

### Manage templates

```bash
viincci template list [--category CATEGORY]
viincci template add PATH [--name NAME]
```

### Run workflows

```bash
viincci run [workflow] [--param KEY=VALUE]
```

### Configure settings

```bash
viincci config [--get KEY] [--set KEY=VALUE]
```

## 🧩 Templates

Built-in templates include:

- **Python**: Basic script, package, Flask app, FastAPI service
- **JavaScript**: Node.js app, React app, Express API
- **Configuration**: Docker, GitHub Actions, pre-commit

### Creating custom templates

Templates are directories with files that can include Jinja2 template variables. Create a template.yaml file in the root:

```yaml
name: My Custom Template
description: A detailed description of the template
variables:
  project_name:
    description: Name of the project
    default: awesome-project
  author:
    description: Your name
hooks:
  post_generate:
    - git init
    - pip install -e .
```

## ⚙️ Workflows

Workflows are defined as YAML files that specify a sequence of actions:

```yaml
name: test-and-lint
description: Run tests and linting
steps:
  - name: Run tests
    action: python.test
    params:
      path: tests/
  
  - name: Run linter
    action: python.lint
    params:
      path: .
      fix: true
```

## 🔧 Configuration

Configuration is stored in `~/.config/viincci/config.yaml` by default:

```yaml
templates_dir: ~/.viincci/templates
workflows_dir: ~/.viincci/workflows
default_variables:
  author: Your Name
  license: MIT
```

## 🧪 Development

To set up for development:

```bash
git clone https://github.com/yourusername/viincci-cli.git
cd viincci-cli
pip install -e ".[dev]"
```

Run tests:

```bash
pytest
```

## 📚 Documentation

For full documentation, visit: [https://vuincci-cli.readthedocs.io](https://viincci-cli.readthedocs.io)

## 🤝 Contributing

Contributions are welcome! Please check out our [contributing guidelines](CONTRIBUTING.md).

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
