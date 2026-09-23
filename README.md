# Software Feasibility Scout

> Discover and validate software opportunities before you build.
>
> 在写代码之前，发现并验证值得做的软件机会。

[English](#english) · [中文](#中文)

---

## English

### What is it?
Software Feasibility Scout is a reusable skill for AI agents. It helps an individual developer turn a broad direction such as “social products”, “gaming tools”, “creator software”, or “AI utilities” into evidence-backed software opportunities.

The skill is designed for people who can build websites, mobile apps, browser tools, or AI-powered products and want to reduce the risk of spending two weeks building something nobody needs. It is a research workflow, not a lead database and not a promise of business success.

### The problem it solves

Many product ideas start with a feature instead of a painful task. A trend may be popular but have no software opportunity. A Reddit post may describe a problem that was already fixed years ago. A competitor may exist, but users may still be dissatisfied with one specific part of the workflow.

This skill connects those pieces and asks:

- Who has the problem?
- What exact task are they trying to complete?
- What do they do today: a product, spreadsheet, group chat, manual work, or outsourcing?
- What is still slow, expensive, unreliable, or frustrating?
- Is the problem current, recurring, seasonal, event-driven, or already fading?
- Who uses the solution and who pays for it?
- Why would someone switch from an existing alternative?
- Can a focused version be tested or shipped quickly?

### How it works

The workflow has five main stages.

1. **Define the search boundary**

   The user may provide an industry, audience, task, country, language, product type, or budget. If no direction is provided, the agent chooses a bounded exploration area and explains why. The direction can be broad, but the final opportunity is narrowed to one user group and one core task.

2. **Discover signals from multiple sources**

   The agent tries several independent discovery routes:

   - Public communities and forums: concrete complaints, requests, workarounds, and follow-up results.
   - Google Trends and related search intent: sudden events, recurring searches, rising tasks, and seasonal windows.
   - TikTok Creative Center and accessible videos/comments: tutorials, workarounds, repeated questions, and emerging behavior.
   - Additional sources selected for the candidate: official documentation, product updates, app-store reviews, GitHub issues, industry forums, public procurement, or outsourcing requests.

   These sources are not added together as if they represented the same number of users. A view count, search trend, upvote, or comment count is a signal, not proof of willingness to pay.

3. **Verify the strongest candidates**

   Each serious candidate is checked against four evidence categories:

   - User experience: a specific person describing a specific task and obstacle.
   - Existing solutions: official features, competitors, free tools, manual processes, or outsourcing.
   - Economic evidence: existing spending, paid alternatives, event fees, procurement, or a concrete purchase action.
   - Currentness: recent evidence, recurring workflow, seasonality, event timing, version changes, and the next review trigger.

   The agent also searches for counter-evidence, such as a feature already being fixed, a free tool being sufficient, strong migration resistance, or users complaining without having purchase authority.

4. **Choose an action level**

   The skill does not force every lead into a product recommendation:

   - **Build**: evidence supports a focused first version and a realistic user entry point.
   - **Experiment**: the pain is credible, but payment, differentiation, or distribution still needs testing.
   - **Watch**: the signal is interesting but currentness, independent evidence, or commercial value is incomplete.
   - **Archive**: existing solutions or decisive counter-evidence make the opportunity weak for now.

5. **Save a traceable research record**

   Reports retain source links, dates, evidence types, access gaps, screening records, opportunity IDs, review dates, and state changes. This makes it possible to revisit a lead later and tell whether it is genuinely new evidence or merely the same old discussion.

### What it can help you do

- Find software opportunities in any industry where a digital workflow can help.
- Explore a direction when you have only a vague idea.
- Validate a concrete product hypothesis before coding.
- Find complaints that are specific enough to become a paid tool.
- Identify temporary opportunities driven by a trend, event, regulation, release, or seasonal workflow.
- Compare competitors with manual workarounds and free alternatives.
- Decide whether to build, test with a small experiment, wait, or abandon the idea.
- Track previously discovered opportunities and review whether the demand is still real.
- Produce a concise daily shortlist with no more than three action recommendations.

### What it does not claim

- It does not provide a statistically representative survey of the whole market.
- It does not turn search volume, video views, or community activity into guaranteed customers.
- It does not automatically obtain Reddit or TikTok API access.
- It does not bypass logins, paywalls, robots rules, or platform restrictions.
- It does not contact users, publish posts, purchase data, start development, or deploy a product without a separate user instruction.
- It does not replace customer interviews or payment validation when a product decision depends on them.

### TikTok login behavior

TikTok Creative Center may require a user login to expose complete trend details. The skill checks this early. If the page requires login and no authorized browser session is available, the agent asks the user to log in through their own browser session. The user never needs to send a password or verification code.

The research can continue with other sources while TikTok is unavailable, but the report must mark the TikTok route as a gap. A successful login also does not guarantee that every region, trend, video, or comment is accessible.

### Installation

#### Codex

Copy the `software-feasibility-scout` folder into your Codex skills directory:

```text
%USERPROFILE%\\.codex\\skills\\software-feasibility-scout
```

The folder must contain at least:

```text
software-feasibility-scout/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── evidence-and-decisions.md
    ├── records-and-reports.md
    ├── search-and-sampling.md
    └── trend-discovery.md
```

Restart or refresh the agent application if the skill list is cached. The skill can be invoked explicitly as `$software-feasibility-scout`.

#### Other agent platforms

The core instructions are plain Markdown. For another agent that supports skills or instruction files, copy `SKILL.md` and the `references/` directory into that platform's skill or prompt directory. If the platform supports YAML metadata, adapt `agents/openai.yaml` to its own format. The agent must have access to web search and page-reading tools for live research; installing the Markdown files alone does not provide data access or platform credentials.

### Usage

Basic discovery:

```text
$software-feasibility-scout Find promising software opportunities in the social space.
```

With a defined audience:

```text
$software-feasibility-scout
Look for paid software opportunities for small event organizers in English-speaking markets. Focus on problems that a solo developer can validate quickly. Do not plan a budget yet.
```

With a concrete hypothesis:

```text
$software-feasibility-scout
Validate whether independent game developers need a better way to collect and prioritize player feedback. Check current user evidence, existing tools, payment signals, and what a two-week MVP could cover.
```

For a repeat review:

```text
$software-feasibility-scout Review the tracked opportunities and tell me which ones still have current evidence.
```

You may set a direction, market, language, budget, development time, or excluded category. If the budget is not ready, say so; the skill can complete discovery while marking cost planning as deferred.

### Typical output

A completed run normally includes:

- A conclusion at the top: what is most worth testing now.
- One to three recommended opportunities, or an explicit zero recommendation.
- The user, payer, task, trigger, and current workaround.
- Source links, dates, evidence summaries, and independent-experience deduplication.
- Existing competitors, free alternatives, and reasons a user might switch.
- Currentness and opportunity-window analysis.
- Payment evidence separated from assumptions.
- A counter-evidence section and the largest unknown.
- A small first-version scope and a concrete next experiment.
- Access gaps, such as blocked pages or unavailable TikTok trend details.
- A saved Markdown report, JSON run record, and screening file when the environment is writable.

### Expected effect

The skill helps you move from “this sounds like a good idea” to “this is a specific user task with evidence, a known alternative, a testable gap, and a clear next step.” It cannot guarantee product-market fit, but it can reduce avoidable mistakes:

- building from a single vague complaint;
- confusing attention with demand;
- ignoring existing free tools;
- treating old discussions as current demand;
- missing a real payment signal;
- expanding an MVP before the core task is validated.

The strongest result is not always a product idea. Sometimes the correct result is a fast experiment, a request for better evidence, or a decision to stop.

### Data and privacy notes

The skill uses public pages or user-authorized browser sessions. It should store only the minimum information needed to locate and evaluate evidence, not private profiles or unnecessary personal data. Do not provide account passwords, verification codes, private messages, or private community content to the agent.

### License

Add the license that matches your repository and distribution model. If you publish this skill as an open-source project, include a `LICENSE` file at the repository root.

---

## 中文

### 这是什么？

Software Feasibility Scout 是一个供 AI Agent 使用的可复用 Skill。它帮助个人开发者把“社交产品”“游戏工具”“创作者软件”“AI 工具”等宽泛方向，逐步收敛成有证据支持的软件机会。

它适合会开发网站、手机 App、浏览器工具或 AI 产品，但希望在投入两周开发时间之前，先确认用户是否真的有问题、现有方案哪里不够、是否存在直接收费可能性的开发者。它是一套调研流程，不是需求数据库，也不承诺任何项目一定成功。

### 它解决什么问题？

很多产品想法从功能开始，而不是从真实任务开始。一个热词可能只有围观，没有软件机会；一条社区抱怨可能几年前就已经被解决；一个竞品可能存在，但目标用户仍然在某个具体环节上不满意。

这个 Skill 会围绕以下问题组织调研：谁遇到了问题、想完成什么任务、现在怎么解决、哪里仍然浪费时间或金钱、需求是否仍然有效、谁使用并付费、为什么愿意换新工具，以及能否快速做出一个足够小的版本进行验证。

### 工作原理

它先确定搜索边界，再从公开社区、Google 搜索趋势、TikTok 内容趋势和其他相关来源发现候选，之后核查真实用户经历、现有替代、付费信号、时间因素和反证。搜索量、播放量、点赞数和评论数只作为发现信号，不会被直接当成用户数量或收入预测。

最终会把机会分成四类：可以开发的小版本、需要先做的快速实验、继续观察的线索，以及已有充分反证、暂时归档的机会。每轮结果都尽量保存来源、日期、访问缺口、复查时间和状态变化，避免下一次把旧讨论误判为新需求。

### 安装与调用

在 Codex 中，把 `software-feasibility-scout` 文件夹放到：

```text
%USERPROFILE%\\.codex\\skills\\software-feasibility-scout
```

然后使用：

```text
$software-feasibility-scout 帮我找一下社交领域有哪些值得开发的软件机会
```

也可以指定行业、人群、地区、语言、预算、开发周期或排除项。如果暂时不想规划预算，可以直接说明，Skill 会先做需求和竞品核验，并把预算标记为延期。

### TikTok 登录说明

TikTok Creative Center 的完整趋势数据可能要求登录。Skill 会在调研开始阶段检查这一点。如果确实需要登录，会尽早提醒用户在自己的浏览器中登录；用户不需要把密码或验证码发给 Agent。未登录时仍可以继续 Reddit、Google 和其他来源，但报告会明确标记 TikTok 路线缺失，而不会假装已经完成三平台核验。

### 调研结果

正常情况下会得到一份中文报告，包括最值得继续验证的机会、真实用户证据、竞品和免费替代、付款依据、需求时间窗口、最大反证、第一版范围以及下一步实验。若证据不足，报告也会明确告诉你暂时不适合开发，而不是强行给出一个产品点子。

### 边界

这个 Skill 不会把搜索热度当成收入保证，不会绕过平台登录或访问限制，不会自动联系用户、发帖、购买数据、开始开发或部署产品。安装 Markdown 文件也不会自动获得 Reddit、Google 或 TikTok 的 API 权限。

它最适合帮助你减少这些错误：凭一条抱怨就开始开发、把热度当成需求、忽略免费替代、把历史讨论当成实时需求、没有核对付费依据，以及在核心任务还没验证前不断扩大 MVP。

### License

请根据你的代码仓库和分发方式选择许可证，并在仓库根目录增加 `LICENSE` 文件。
