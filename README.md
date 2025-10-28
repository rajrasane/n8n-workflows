# n8n Workflow Backups 🔄

Automated backup system for n8n workflows using GitHub as version control.

## 📋 Overview

This repository serves as an automated backup solution for all n8n workflows. Every workflow is automatically backed up to GitHub, providing version control, change tracking, and disaster recovery capabilities.

## 🚀 Features

- **Automated Daily Backups** - Runs every day at 2:00 AM IST
- **Smart Change Detection** - Identifies new, modified, and unchanged workflows
- **Version Control** - Full Git history of all workflow changes
- **Automatic Commits** - Descriptive commit messages for each backup
- **Manual Trigger** - Can be executed on-demand anytime

## 📁 Repository Structure

```
n8n-workflows/
├── workflows/           # All backed up n8n workflows (JSON format)
│   ├── Workflow Backup.json
│   └── Test Workflow - Hello World.json
└── README.md
```

## 🔧 How It Works

The backup system uses an n8n workflow that:

1. **Fetches** all workflows from the n8n instance via API
2. **Compares** each workflow with the version stored in GitHub
3. **Detects** changes using JSON comparison
4. **Creates/Updates** workflow files in GitHub based on status:
   - `new` - Creates a new file for workflows not yet backed up
   - `different` - Updates existing files when changes are detected
   - `same` - Skips unchanged workflows

## 📊 Backup Status

Each backup creates a commit with a descriptive message:
- `[N8N Backup] <workflow-name>.json (new)` - New workflow added
- `[N8N Backup] <workflow-name>.json (different)` - Workflow updated
- `[N8N Backup] <workflow-name>.json (same)` - No changes (skipped)

## ⏰ Schedule

- **Automatic**: Daily at 2:00 AM IST
- **Manual**: Can be triggered anytime from n8n

## 🛠️ Technical Details

- **n8n Instance**: https://n8n-evh2.onrender.com
- **API Authentication**: Uses n8n API key for secure access
- **GitHub Integration**: Uses GitHub API for file operations
- **Backup Location**: `workflows/` directory

## 📝 Workflow Files

All workflows are stored as JSON files containing:
- Node configurations
- Connection mappings
- Workflow settings
- Credentials references (IDs only, not actual credentials)

## 🔒 Security

- API keys and credentials are stored securely in n8n
- Only workflow structure and configuration are backed up
- Actual credential values are never stored in this repository

## 📈 Benefits

- **Disaster Recovery** - Restore workflows if n8n instance fails
- **Change Tracking** - See what changed and when
- **Collaboration** - Share workflows with team members
- **Version History** - Rollback to previous versions if needed
- **Documentation** - Workflows serve as documentation

## 🔗 Links

- [n8n Documentation](https://docs.n8n.io/)
- [n8n Community](https://community.n8n.io/)

---

**Last Updated**: October 28, 2025  
**Maintained by**: Raj Rasane  
**Backup System**: Active ✅