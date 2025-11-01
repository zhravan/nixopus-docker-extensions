<h1 align="center">
  Nixopus Docker Extensions
</h1>

<h2>
  Architecture
</h2>

```
┌─────────────────────────────────────────────────────────┐
│  Separate Compose Repository (GitHub/GitLab/etc)        │
│  https://github.com/zhravan/nixopus-docker-extensions   │
│  └── postiz/docker-compose.yml                          │
└─────────────────────────────────────────────────────────┘
                         v
                         v Download via curl
┌─────────────────────────────────────────────────────────┐
│  Nixopus Extension (deploy-postiz.yaml)                │
│  1. Downloads compose file from URL                     │
│  2. Generates .env with user variables                  │
│  3. Runs docker compose up                              │
└─────────────────────────────────────────────────────────┘
                         v
                         v
┌─────────────────────────────────────────────────────────┐
│  Target Server (/opt/postiz/)                          │
│  ├── docker-compose.yml (downloaded)                    │
│  └── .env (generated from extension variables)          │
└─────────────────────────────────────────────────────────┘
```
