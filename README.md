# Wilds Go — Strapi CMS

This is the headless CMS backend for [Wilds Go](https://github.com/vaibhav-tpvp/wildsGo), an Indian wildlife travel booking platform. It is deployed on Strapi Cloud and serves content to the Next.js frontend via the REST API.

## Content Types

### Collection Types
| Name | Purpose |
|---|---|
| **NationalPark** | India's national parks — hero images, wildlife, best time to visit, location |
| **TravelPackage** | Bookable safari and holiday packages with itinerary, pricing, availability |
| **Blog** | Field journal articles with rich text, author info, and cross-links to parks/packages |
| **Testimonial** | Guest reviews with rating, verified badge, and package link |
| **LegalPage** | Editable policy pages (cookie, shipping, cancellation) identified by slug |

### Single Types
| Name | Purpose |
|---|---|
| **SiteSettings** | Global config: logo, contact details, social links, footer links |
| **AboutPage** | Mission statement, company story, team members, impact stats |

### Shared Components
| Component | Used by |
|---|---|
| `shared.seo` | All collection + single types |
| `shared.itinerary-day` | TravelPackage itinerary |
| `shared.package-highlight` | TravelPackage highlights |
| `shared.available-date` | TravelPackage available dates |
| `shared.team-member` | AboutPage team section |
| `shared.impact-stat` | AboutPage stats section |
| `shared.social-links` | SiteSettings |
| `shared.footer-link` | SiteSettings footer |

## Permissions Setup

After deploy, go to **Settings → Roles → Public** and enable `find` + `findOne` on:
- NationalPark, TravelPackage, Blog, Testimonial, LegalPage, SiteSettings, AboutPage

## Webhook (Cache Revalidation)

Configure a webhook in **Settings → Webhooks** pointing to:
```
POST https://your-frontend.vercel.app/api/strapi-webhook
Authorization: Bearer <STRAPI_WEBHOOK_SECRET>
```
Trigger on: Entry publish, update, unpublish for all collections.

---

# 🚀 Getting started with Strapi

Strapi comes with a full featured [Command Line Interface](https://docs.strapi.io/dev-docs/cli) (CLI) which lets you scaffold and manage your project in seconds.

### `develop`

Start your Strapi application with autoReload enabled. [Learn more](https://docs.strapi.io/dev-docs/cli#strapi-develop)

```
npm run develop
# or
yarn develop
```

### `start`

Start your Strapi application with autoReload disabled. [Learn more](https://docs.strapi.io/dev-docs/cli#strapi-start)

```
npm run start
# or
yarn start
```

### `build`

Build your admin panel. [Learn more](https://docs.strapi.io/dev-docs/cli#strapi-build)

```
npm run build
# or
yarn build
```

## ⚙️ Deployment

Strapi gives you many possible deployment options for your project including [Strapi Cloud](https://cloud.strapi.io). Browse the [deployment section of the documentation](https://docs.strapi.io/dev-docs/deployment) to find the best solution for your use case.

```
yarn strapi deploy
```

## 📚 Learn more

- [Resource center](https://strapi.io/resource-center) - Strapi resource center.
- [Strapi documentation](https://docs.strapi.io) - Official Strapi documentation.
- [Strapi tutorials](https://strapi.io/tutorials) - List of tutorials made by the core team and the community.
- [Strapi blog](https://strapi.io/blog) - Official Strapi blog containing articles made by the Strapi team and the community.
- [Changelog](https://strapi.io/changelog) - Find out about the Strapi product updates, new features and general improvements.

Feel free to check out the [Strapi GitHub repository](https://github.com/strapi/strapi). Your feedback and contributions are welcome!

## ✨ Community

- [Discord](https://discord.strapi.io) - Come chat with the Strapi community including the core team.
- [Forum](https://forum.strapi.io/) - Place to discuss, ask questions and find answers, show your Strapi project and get feedback or just talk with other Community members.
- [Awesome Strapi](https://github.com/strapi/awesome-strapi) - A curated list of awesome things related to Strapi.

---

<sub>🤫 Psst! [Strapi is hiring](https://strapi.io/careers).</sub>
