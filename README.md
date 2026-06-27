# 🛡️ Sentinel — LLM Firewall

> Pare-feu applicatif pour agents IA. Intercepte chaque prompt avant qu'il n'atteigne le modèle et bloque automatiquement les fuites de credentials, données personnelles et informations d'infrastructure — selon une politique définie par le DSI.

![Status](https://img.shields.io/badge/status-en%20développement-blue?style=flat-square)
![Stack](https://img.shields.io/badge/stack-Python%20%7C%20FastAPI%20%7C%20React-3887FF?style=flat-square)
![Licence](https://img.shields.io/badge/licence-MIT-00FFFF?style=flat-square)

---

## Le problème

Les développeurs utilisent quotidiennement des agents IA (Claude Code, GitHub Copilot, ChatGPT…) pour déboguer, refactoriser et documenter. Sans s'en rendre compte, ils partagent :

- 🔑 Des **credentials hardcodés** — clés API, mots de passe, tokens
- 🏗️ De l'**architecture interne** — IPs privées, endpoints, noms de services
- 👤 Des **données personnelles** — logs clients, dumps de base (RGPD)

Sentinel s'insère entre vos outils et les LLMs pour bloquer ces fuites **avant** qu'elles n'atteignent le modèle.

---

## Comment ça marche

```
Développeur → [Sentinel Proxy] → LLM (Claude, GPT-4, Mistral…)
                     │
              Policy Engine DSI
              ┌─────────────────┐
              │ Regex patterns  │
              │ Entropie Shannon│
              │ NLP classifiers │
              └─────────────────┘
                     │
              BLOQUÉ → Log SIEM
              AUTORISÉ → Forward
```

1. Le développeur envoie un prompt via son outil habituel
2. Sentinel intercepte la requête via son proxy API
3. Le **Policy Engine** analyse le prompt contre les règles définies par le DSI
4. Le prompt est **bloqué** (violation critique), **signalé** (avertissement) ou **transmis** (clean)
5. Chaque événement est loggué et exportable vers un SIEM

---

## Fonctionnalités

| Feature | Statut |
|---|---|
| Scan regex multi-patterns (credentials, IPs, PII…) | ✅ Disponible |
| Détection par entropie de Shannon | 🔧 En cours |
| Dashboard DSI / RSSI | 🔧 En cours |
| Politique de sécurité no-code (YAML + UI) | 📋 Planifié |
| Intégration CI/CD (Jenkins, GitLab CI) | 📋 Planifié |
| Alertes SIEM (Splunk, Elastic, Wazuh) | 📋 Planifié |
| Rapport conformité RGPD automatique | 📋 Planifié |
| Hébergement souverain (France) | 📋 Planifié |

---

## Stack technique

- **Proxy API** — Python / FastAPI
- **Policy Engine** — Python (regex, entropie, NLP)
- **Dashboard** — React / Tailwind CSS
- **Auth** — JWT + OAuth2
- **Logs** — Structured JSON → SIEM compatible
- **Déploiement** — Docker / Docker Compose

---

## LLMs compatibles

Claude · ChatGPT / OpenAI · GitHub Copilot · Mistral AI · Azure OpenAI · AWS Bedrock · Tout LLM exposé via API REST

---

## Démo

Une démo interactive est disponible sur la landing page :
**[sentinel-llm.fr](https://sentinel-llm.fr)** *(à venir)*

---

## Lancement

> 🗓️ **Disponible Q3 2026** — Accès anticipé ouvert

Les 50 premiers inscrits bénéficient de 3 mois offerts et d'un onboarding personnalisé.

👉 **[Rejoindre la liste d'attente](https://sentinel-llm.fr#waitlist)**

---

## Auteur

Développé par **Rayan** — Apprenti Ingénieur DevOps · ESIEE Paris (Réseaux & Sécurité)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue?style=flat-square&logo=linkedin)](https://linkedin.com/in/tonprofil)

---

## Licence

MIT © 2026 Sentinel


