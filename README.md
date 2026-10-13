# vps deals: How to Tell a Real Discount From a Teaser Price, and What DMIT's Current Plans Actually Cost

Type "vps deals" into a search box and you get a wall of two-dollar headlines. Click through and the fine print says the price only holds if you prepay three years up front, the port is 100Mbps, and month 37 renews at four times that. The advertised number and the number you actually pay have almost nothing to do with each other, and that gap is the whole game.

So this isn't a list of ninety hosts. It's how to read a VPS offer — what genuinely pushes the price down, which "discounts" are just a payment schedule wearing a costume, and how to check a specific plan before you hand over money. For the second half I'll use DMIT as the worked example, because its lineup happens to illustrate every one of these traps and one or two of the good patterns too.

## The three numbers that decide whether a deal is real

**The renewal price.** Nearly every cheap VPS listicle quotes the introductory rate. What matters is what the invoice says on the second cycle. A provider that charges $18 for year one and $72 for year two is a $45/year host, not an $18/year host. Find the renewal figure before you find your wallet.

**What happens after the traffic meter runs out.** Two hosts can both advertise 1TB and behave completely differently at 1.01TB. Some throttle you to a crawl, some keep the port open and bill overage, some suspend the instance until the next cycle. The throttle number is usually buried on the plan page, and it's often the single most useful specification on it.

**Which node you actually land on.** Same CPU count and same RAM can mean wildly different prices, because the difference isn't hardware. It's the return route back to wherever your users are. If you're paying a premium for a premium route and your traffic never touches that route, you've bought nothing.

A fourth thing, harder to measure: whether the node is oversold. Shared vCPU is normal and fine until the host packs three times the tenants it should onto one chassis. This is where published benchmarks mislead — they measure one instance on one node on one day. You can check it yourself after the fact: run `top` and watch the `st` (steal time) figure, or `vmstat 1 10` and watch the `st` column. Under 1% is healthy. Consistently above 5% means you're paying for CPU you aren't getting.

## Where VPS discounts actually come from

There are only five levers, and every "deal" you'll ever see is one of them.

**Billing cycle.** Annual prepay is the most common real discount. Depending on the line, it works out to roughly 20–25% below the effective monthly rate. Quarterly and semi-annual land somewhere in between. This is a genuine discount, not a gimmick — you're trading flexibility for the host's cash flow — but it only pays off if you're confident you'll keep the box.

**Network tier.** Routing costs money, and the host passes that on. The same 2 vCPU / 2GB box can be three times the price on a China-optimized route as on plain international transit. That's not a markup on nothing; it's the only reason the two products exist separately.

**Hardware generation.** Vendors resell the same configuration on older and newer AMD EPYC platforms at different prices. Older silicon is cheaper per core and perfectly adequate for a static site or a relay. Newer silicon costs more and pays off only if you're CPU-bound — databases, build servers, anything single-thread sensitive.

**Restocks and limited editions.** Small hosts buy bandwidth and capacity in batches. When a batch lands, a handful of configurations go up at a price that won't come back. This is where genuinely good deals live, and it's also why inventory flickers: a plan showing on the store page this morning can be sold out by lunch.

**Coupon codes.** These come in two flavors, and mixing them up wastes your time. One-time codes knock a percentage off the first invoice. Recurring codes apply to every renewal for the life of the service, which is worth far more. When you see a code, check which one it is before you get excited.

> Real recurring discounts are rare and usually tied to a campaign that has already ended. Code lists you find on aggregator blogs are, more often than not, archives of past promotions with the dates quietly stripped out.

## DMIT, and how its pricing actually works

DMIT is a US-registered host that's been running VPS since 2017–2018, with KVM instances in Los Angeles, Hong Kong, and Tokyo. The pitch is unglamorous: AMD EPYC processors, NVMe storage, no overselling, and routes bought properly rather than resold. Payment runs through Alipay, PayPal, and standard credit cards, which matters more than it should if your card doesn't play nicely with foreign processors.

Everything in the catalog splits three ways by network:

- **Premium (.Pro)** — China Telecom CN2 GIA on the return path, the top tier for mainland-facing traffic
- **Eyeball (.EB)** — CMIN2 and AS9929 routes, one step below Premium at a noticeably lower price
- **Tier 1 (.T1)** — plain international transit, no China optimization at all, and by far the cheapest

That's the first thing to get right, and it's the step people skip. Choosing between a $10.90 Premium TINY and a $10.90 Eyeball TINY isn't a specification question. It's a question about who visits your site.

Two structural things about how DMIT discounts work. First, there are no standing public coupon codes worth hunting for; discounts are built into the billing cycle and into periodic campaigns, and the campaigns come with names long enough to be their own paragraph. Second, because those campaign codes are recurring rather than one-shot, an old code either applies to your order forever or doesn't apply at all — there's no partial credit, and no harm in pasting one into the validation box at checkout to see what happens.

👉 [Check the current DMIT lineup](https://www.dmit.io/aff.php?aff=12046)

## Every DMIT plan currently listed, with prices

Prices below are monthly unless marked `/yr`. Every configuration ships with 1 IPv4 and an IPv6 /64 block; WEE plans are annual-only.

### Los Angeles

| Line | Plan | Specs | Traffic @ port | Throttled to | Price | Order |
| --- | --- | --- | --- | --- | --- | --- |
| LAX Pro | TINY | 1 vCPU / 2GB / 20GB | 1000GB @ 1Gbps | 4Mbps | $10.90/mo | [Check price](https://www.dmit.io/aff.php?aff=12046) |
| LAX Pro | Pocket | 2 vCPU / 2GB / 40GB | 1500GB @ 4Gbps | 4Mbps | $16.90/mo | [Check price](https://www.dmit.io/aff.php?aff=12046) |
| LAX Pro | STARTER | 2 vCPU / 2GB / 80GB | 3000GB @ 10Gbps | 4Mbps | $34.90/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| LAX Pro | MINI | 4 vCPU / 4GB / 80GB | 5000GB @ 10Gbps | 8Mbps | $62.90/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| LAX Pro | MICRO | 4 vCPU / 4GB / 160GB | 7000GB @ 10Gbps | 8Mbps | $87.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |
| LAX Pro | MEDIUM | 6 vCPU / 8GB / 160GB | 14000GB @ 10Gbps | 10Mbps | $199.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |
| LAX EB | TINY | 1 vCPU / 2GB / 20GB | 1500GB @ 2Gbps | 4Mbps | $10.90/mo | [Check price](https://www.dmit.io/aff.php?aff=12046) |
| LAX EB | Pocket | 2 vCPU / 2GB / 40GB | 3000GB @ 4Gbps | 4Mbps | $16.90/mo | [Check price](https://www.dmit.io/aff.php?aff=12046) |
| LAX EB | STARTER | 2 vCPU / 2GB / 80GB | 5000GB @ 10Gbps | 4Mbps | $34.90/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| LAX EB | MINI | 4 vCPU / 4GB / 80GB | 10000GB @ 10Gbps | 8Mbps | $62.90/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| LAX EB | MICRO | 4 vCPU / 4GB / 160GB | 14000GB @ 10Gbps | 8Mbps | $87.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |
| LAX EB | MEDIUM | 6 vCPU / 8GB / 160GB | 30000GB @ 10Gbps | 10Mbps | $199.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |
| LAX T1 | WEE | 1 vCPU / 1GB / 20GB | 1000GB @ 4Gbps | 100Mbps | $36.90/yr | [Order WEE](https://www.dmit.io/aff.php?aff=12046) |
| LAX T1 | TINY | 1 vCPU / 1GB / 20GB | 2000GB @ 4Gbps | 200Mbps | $6.90/mo | [Check price](https://www.dmit.io/aff.php?aff=12046) |
| LAX T1 | STARTER | 2 vCPU / 2GB / 40GB | 4000GB @ 10Gbps | 200Mbps | $12.90/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| LAX T1 | MINI | 2 vCPU / 4GB / 80GB | 8000GB @ 10Gbps | 200Mbps | $21.90/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| LAX T1 | MICRO | 4 vCPU / 4GB / 120GB | 16000GB @ 10Gbps | 500Mbps | $32.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |

### Hong Kong

| Line | Plan | Specs | Traffic @ port | Price | Order |
| --- | --- | --- | --- | --- | --- |
| HKG Pro (AS3) | TINY | 1 vCPU / 1GB / 20GB | 500GB @ 1Gbps | $39.90/mo | [Check price](https://www.dmit.io/aff.php?aff=12046) |
| HKG Pro (AS3) | STARTER | 1 vCPU / 2GB / 40GB | 1000GB @ 1Gbps | $79.90/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG Pro (AS3) | MINI | 2 vCPU / 2GB / 60GB | 1500GB @ 1Gbps | $126.90/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG Pro (AS3) | MICRO | 2 vCPU / 4GB / 80GB | 2000GB @ 1Gbps | $179.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |
| HKG Pro (AS3) | MEDIUM | 4 vCPU / 4GB / 160GB | 2500GB @ 1Gbps | $239.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |
| HKG Pro (AN5) | MINI | 2 vCPU / 2GB / 80GB | 1500GB @ 1Gbps | $149.90/mo | [Check price](https://www.dmit.io/aff.php?aff=12046) |
| HKG Pro (AN5) | MICRO | 2 vCPU / 4GB / 160GB | 2000GB @ 1Gbps | $159.90/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG Pro (AN5) | MEDIUM | 4 vCPU / 4GB / 160GB | 2500GB @ 1Gbps | $180.00/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG Pro (AN5) | LARGE | 4 vCPU / 8GB / 320GB | 3000GB @ 1Gbps | $240.00/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |
| HKG Pro (AN5) | GIANT | 8 vCPU / 16GB / 640GB | 6000GB @ 1Gbps | $500.00/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |
| HKG T1 | WEE | 1 vCPU / 1GB / 20GB | 1000GB | $36.90/yr | [Order WEE](https://www.dmit.io/aff.php?aff=12046) |
| HKG T1 | TINY | 1 vCPU / 1GB / 20GB | 2000GB | $6.90/mo | [Check price](https://www.dmit.io/aff.php?aff=12046) |
| HKG T1 | STARTER | 1 vCPU / 2GB / 40GB | 4000GB | $12.90/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG T1 | MINI | 2 vCPU / 2GB / 60GB | 8000GB | $21.90/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG T1 | MICRO | 4 vCPU / 4GB / 80GB | 16000GB | $32.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |
| HKG T1 | MEDIUM | 4 vCPU / 8GB / 160GB | 32000GB | $49.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |
| HKG T1 | LARGE | 8 vCPU / 16GB / 320GB | 64000GB | $99.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |
| HKG T1 | GIANT | 8 vCPU / 24GB / 640GB | 128000GB | $199.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |

### Tokyo

| Line | Plan | Specs | Traffic @ port | Price | Order |
| --- | --- | --- | --- | --- | --- |
| TYO Pro | TINY | 1 vCPU / 1GB / 20GB | 500GB @ 1Gbps | $21.90/mo | [Check price](https://www.dmit.io/aff.php?aff=12046) |
| TYO Pro | STARTER | 1 vCPU / 2GB / 40GB | 1000GB @ 1Gbps | $45.90/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| TYO T1 | WEE | 1 vCPU / 1GB / 20GB | 1000GB | $36.90/yr | [Order WEE](https://www.dmit.io/aff.php?aff=12046) |
| TYO T1 | TINY | 1 vCPU / 1GB / 20GB | 2000GB | $6.90/mo | [Check price](https://www.dmit.io/aff.php?aff=12046) |
| TYO T1 | STARTER | 1 vCPU / 2GB / 40GB | 4000GB | $12.90/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| TYO T1 | MINI | 2 vCPU / 2GB / 60GB | 8000GB | $21.90/mo | [See this plan](https://www.dmit.io/aff.php?aff=12046) |
| TYO T1 | MICRO | 4 vCPU / 4GB / 80GB | 16000GB | $32.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |
| TYO T1 | MEDIUM | 4 vCPU / 8GB / 160GB | 32000GB | $49.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |
| TYO T1 | LARGE | 8 vCPU / 16GB / 320GB | 64000GB | $99.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |
| TYO T1 | GIANT | 8 vCPU / 24GB / 640GB | 128000GB | $199.90/mo | [Check stock](https://www.dmit.io/aff.php?aff=12046) |

A few notes that matter more than they look.

The same configuration is often sold on more than one AMD platform — EPYC 7003 ("AS3"), 9004 ("AN4"), and 9005 ("AN5") — at different prices. That's why Hong Kong Premium shows MINI at both $126.90 and $149.90. Older listings for the LAX Pro and LAX EB entry tier quote $9.99 rather than $10.90 for the same slot; the store page is the only number that's binding.

Tokyo Premium's larger sizes are quoted inconsistently across third-party summaries, so I've left them out rather than print a figure that might be wrong. Los Angeles has the deepest bench and the most frequent restocks; Hong Kong and Tokyo are thinner and sell out faster.

## Pro vs Eyeball vs Tier 1: what the extra money buys

With Premium in Los Angeles, Telecom inbound runs over CN2 GIA (AS4809), Unicom comes in direct on AS4837, Mobile enters through Hong Kong Mobile (AS58453), and all three carriers return over AS4809. You're buying the return path specifically, because that's the direction your site's data travels when a visitor loads a page.

Eyeball is the budget answer to the same problem: Telecom gets load-balanced across AS9929 and AS58807, Unicom rides AS9929, Mobile rides AS58807. On the TINY tier it costs exactly the same as Premium and gives you 1.5TB instead of 1TB plus a 2Gbps port instead of 1Gbps. You trade route quality for headroom, and that's a coherent trade rather than a downgrade.

Hong Kong Premium returns through Hong Kong CTG into CN2 GIA, with Telecom inbound over GIA, Unicom via AS4837 and AS10099, and Mobile over CMI. It costs roughly four times Los Angeles Premium for a fraction of the traffic, which is the physical-cost reality of Asian bandwidth, not a premium for a brand name.

Tier 1 runs plain international transit — Telia, Zayo, Cogent — with no China engineering at all. If your readers are in North America or Europe, this is the correct product and everything above is wasted money.

## Matching a plan to a situation

**Mainland-China readers, normal site traffic.** LAX Pro TINY at $10.90 or Pocket at $16.90. 2GB handles a cached WordPress site comfortably. Going to Hong Kong Pro for the latency is the most common expensive mistake here: a stable 150ms beats an unstable 40ms, and the Hong Kong plans give you 500GB where LAX gives you 1000GB for a quarter of the price.

**Budget first, but default routing stings.** LAX EB TINY, $10.90. Twice the traffic of the Premium equivalent at the same price, on a route that's better than generic transit without pretending to be the top tier.

**Nobody in China.** LAX T1 TINY at $6.90, or WEE at $36.90/year, which is about $3.08 a month. Same specs as TINY, less traffic, and your money is locked in only for twelve months.

**Traffic-heavy workloads — backups, mirrors, media.** The Tier 1 large tiers. HKG T1 STARTER gives 4TB for $12.90; LAX T1 MICRO gives 16TB for $32.90 with a 500Mbps post-overage throttle. That throttle is the reason these plans are usable for bulk transfer at all.

**Sub-50ms latency matters.** Hong Kong Pro, starting at $39.90. It's the product for remote desktop work, game-adjacent services, and anything where every keystroke round trip is felt.

👉 [Compare all DMIT plans and current stock](https://www.dmit.io/aff.php?aff=12046)

## The fine print that changes the math

**You get throttled, not evicted.** When the traffic allocation runs out, the instance keeps running at a reduced speed — as low as 4Mbps on the Pro and EB tiers, and between 100Mbps and 1Gbps on Tier 1 depending on the configuration. For a website, 4Mbps is survivable. For bulk file transfer it isn't, so pick your line knowing which one you need.

**IP replacement.** Reviews of DMIT's policy describe one free IP swap roughly every 15 days, with later replacements around $5. That's cheaper than the $8–10 several competitors charge, and it matters because a blocked IP is the single most common reason a working server becomes useless.

**Refunds are short.** The first-purchase refund window described in DMIT's terms is around three days, conditional on usage and on the IP not being blocked. Treat it as a mistake-correction window, not a trial.

**The LAX AS3 line comes with a caveat, from DMIT itself.** The company notes that platform is still under optimization, and that disk performance and SLA may sit below what a mature platform delivers. If your workload is disk-IO sensitive, that's a reason to pick a different generation.

**Payment and support.** Alipay, PayPal, and cards are all accepted. Support runs on tickets, in Chinese and English, and it is not a chat window — a few hours of turnaround on a ticket is normal. If you need someone to debug your Nginx config, that's a different product category and a different price bracket.

**The terms are strict and enforced.** Outbound port scanning, DDoS, spam, and copyright complaints are grounds for termination without refund. Nothing unusual, but DMIT acts on these rather than warning first.

## Questions people ask before buying

*Is the cheap annual plan actually cheaper if I leave after five months?* No. Annual prepay discounts are real but they're priced against a twelve-month commitment. If there's a real chance you'll walk, monthly at a higher rate is the cheaper choice.

*Should I buy the smallest plan and upgrade later?* On DMIT, upgrades recalculate at current pricing rather than the price you originally paid, and older listings have already moved. If you think you'll need Pocket specs, buy Pocket.

*Do I need a China-optimized route if only some of my visitors are there?* Probably not. Routing tiers are linear pricing for a benefit that only materializes for one segment of your audience. If mainland traffic is under, say, a fifth of your total, Tier 1 in Los Angeles plus a CDN will cost less and serve the other four-fifths better.

## The short version

A VPS deal is only a deal once you know the renewal price, the throttle threshold, and which route you're actually buying. Sort providers by those three things and most of the "$1.99/month forever" noise disappears on its own.

DMIT is what the opposite end looks like: no coupon theatre, prices set by the route you're paying for, and a catalog where the cheapest option ($6.90/month or $36.90/year for a 1GB instance) and the most expensive one (a $500/month Hong Kong configuration) exist for genuinely different jobs. The entry prices are lower than the brand's reputation suggests, which is exactly the kind of gap worth exploiting — and the reason restocks sell out the day they land.

👉 [See live DMIT pricing and availability](https://www.dmit.io/aff.php?aff=12046)
