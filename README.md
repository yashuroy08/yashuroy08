<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,100:00d4ff&height=120&section=header&text=&fontColor=ffffff&fontSize=40&fontAlignY=35&animation=fadeIn" />

# Yashwanth Patam

**Backend Engineer · Spring Boot · Security Architecture · DevOps**

<a href="https://linkedin.com/in/yashwanth-patam/">
  <img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/>
</a>
<a href="https://yashwanth-portfolio-sigma.vercel.app/">
  <img src="https://img.shields.io/badge/Portfolio-Live-00d4ff?style=for-the-badge&logo=vercel&logoColor=black"/>
</a>
<a href="mailto:royyashwanth52@gmail.com">
  <img src="https://img.shields.io/badge/Email-Hire_Me-D14836?style=for-the-badge&logo=gmail&logoColor=white"/>
</a>
<a href="https://leetcode.com/u/Yashuroy08/">
  <img src="https://img.shields.io/badge/LeetCode-Profile-FFA116?style=for-the-badge&logo=leetcode&logoColor=black"/>
</a>

<br/><br/>

<img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&weight=600&size=18&pause=1200&color=00D4FF&center=true&vCenter=true&width=600&lines=Spring+Boot+%7C+Security+Architecture;JWT+%2B+MFA+%2B+RBAC+systems;Redis+%7C+PostgreSQL+%7C+Docker;Building+backends+that+don't+break" />

</div>

---

## Who I Am

I'm a backend engineer focused on **Java and the Spring ecosystem** — specifically the parts that keep systems secure, fast, and honest under pressure.

I build things like adaptive auth systems, identity management APIs, and e-commerce backends — not just to learn, but to understand *why* the architecture decisions matter. I care about clean code, real-world deployment, and security that goes beyond slapping a JWT on an endpoint.

Currently based in Chennai. Open to backend roles — remote or in India.

---

## What I Work With

<div align="center">

<img src="https://skillicons.dev/icons?i=java,spring,postgres,redis,mongodb,docker,nginx,github&theme=dark" />

<br/><br/>

![Spring Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=for-the-badge&logo=springsecurity&logoColor=white)
![Hibernate](https://img.shields.io/badge/Hibernate-59666C?style=for-the-badge&logo=hibernate&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![JUnit5](https://img.shields.io/badge/JUnit5-25A162?style=for-the-badge&logo=junit5&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=for-the-badge&logo=playwright&logoColor=white)

</div>

<br/>

<div align="center">

<img src="https://github-profile-trophy.vercel.app/?username=yashuroy08&theme=tokyonight&no-frame=true&row=1&column=6" />

</div>

---

## Projects I'm Proud Of

### 🔐 RBAC Identity Service — [Live Demo](https://rbac-guard.vercel.app) · [Code](https://github.com/yashuroy08/RBAC)

A production-grade identity and access management system that goes well beyond basic auth. Built this because most tutorials stop at "issue a JWT" — this one handles what comes after.

**What it actually does:**
- **Adaptive MFA** — triggers additional verification when login comes from a new IP, unknown device, or flagged geography
- **Geo-fencing** — blocks or challenges logins outside a defined region
- **Trusted device tracking** — users can view and revoke active sessions per device
- **Redis-backed sessions** — stateful session invalidation without sacrificing speed
- **Nginx reverse proxy** — rate limiting, CSP headers, PII log masking baked in
- **Full Docker Compose stack** with GoAccess traffic analytics and RedisInsight

`Spring Boot 3` · `PostgreSQL 15` · `Redis 7` · `Docker` · `Nginx` · `React (Vite)` · `GitHub Actions`

<div align="center">

<details>
<summary><b>🏗️ Click to see Spring Boot Architecture</b></summary>

<br/>

```
┌─────────────────────────────────────────────────────────────┐
│                     CLIENT (React / Vite)                   │
└───────────────────────────┬─────────────────────────────────┘
                            │ HTTPS
┌───────────────────────────▼─────────────────────────────────┐
│               NGINX (Reverse Proxy / Edge)                  │
│         Rate Limiting · CSP · XSS Protection · Logs         │
└───────────────────────────┬─────────────────────────────────┘
                            │ /api/*
┌───────────────────────────▼─────────────────────────────────┐
│              SPRING BOOT (Core Identity Engine)             │
│                                                             │
│   ┌──────────────┐  ┌───────────────┐  ┌────────────────┐  │
│   │ Auth Filter  │  │  RBAC Engine  │  │  MFA Service   │  │
│   │ JWT Validate │  │  Role / Perm  │  │  TOTP / OTP    │  │
│   └──────┬───────┘  └───────┬───────┘  └───────┬────────┘  │
│          │                  │                   │           │
│   ┌──────▼───────────────────▼───────────────────▼──────┐   │
│   │              Business Logic Layer                    │   │
│   │  Device Trust · Geo-Fence · Session Management      │   │
│   └──────────────────────┬───────────────────────────────┘  │
│                          │                                  │
│          ┌───────────────┼────────────────┐                 │
│          │               │                │                 │
│   ┌──────▼──────┐ ┌──────▼──────┐ ┌──────▼──────┐         │
│   │ PostgreSQL  │ │    Redis    │ │   GoAccess  │         │
│   │  Users/Roles│ │  Sessions   │ │  Analytics  │         │
│   │  Audit Logs │ │  MFA Tokens │ │             │         │
│   └─────────────┘ └─────────────┘ └─────────────┘         │
└─────────────────────────────────────────────────────────────┘
```

</details>

</div>

---

### 🛒 Threads Fashion —  [Live Demo](https://threads-fashion.vercel.ap) · [Code](https://github.com/yashuroy08/Threads-Fashion)

Backend engine for a fashion e-commerce platform. Focused on building an API that's both secure and operationally clean.

**What it handles:**
- Full order lifecycle — cart → checkout → payment → fulfilment state machine
- Payment workflow integration with proper failure/retry handling
- Input sanitization and security filters throughout
- MongoDB document modelling for flexible product catalogue

`Spring Boot` · `MongoDB` · `Spring Security` · `REST API`

---

### 🏛️ AP Public Grievance System — `In Progress`

Building a grievance redressal platform for the **Andhra Pradesh Government** — a citizen-facing backend that manages complaint submissions, tracks resolution workflows, and routes issues to the right department in real time.

**What it covers:**
- Multi-department complaint routing with role-based officer access
- Status tracking lifecycle — Submitted → Assigned → Under Review → Resolved
- Citizen authentication with OTP-based verification
- Admin dashboard APIs for grievance analytics and SLA breach detection
- Designed for scale across AP's district and mandal hierarchy

`Spring Boot` · `PostgreSQL` · `Spring Security` · `REST API` · `Docker`

---

## GitHub Activity

<div align="center">

<img height="180em" src="https://github-readme-stats-sigma-five.vercel.app/api?username=yashuroy08&show_icons=true&theme=tokyonight&hide_border=true&include_all_commits=true&count_private=true"/>
<img height="180em" src="https://github-readme-stats-sigma-five.vercel.app/api/top-langs/?username=yashuroy08&layout=compact&theme=tokyonight&hide_border=true&langs_count=6"/>

<br/>

<img src="https://github-readme-streak-stats.herokuapp.com?user=yashuroy08&theme=tokyonight&hide_border=true&date_format=M%20j%5B%2C%20Y%5D" />

<br/>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=yashuroy08&theme=tokyo-night&hide_border=true&area=true" />

</div>

---

## Let's Talk

If you're building something with Java and need someone who takes security seriously — or if you just want to talk backend architecture — reach out.

<div align="center">

<a href="https://linkedin.com/in/yashwanth-patam/">
  <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/>
</a>
<a href="mailto:royyashwanth52@gmail.com">
  <img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white"/>
</a>
<a href="https://yashwanth-portfolio-sigma.vercel.app/">
  <img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white"/>
</a>

<br/>



<br/><br/>



<img src="https://capsule-render.vercel.app/api?type=waving&color=0:00d4ff,100:0d1117&height=100&section=footer" />

</div>
