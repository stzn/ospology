---
title: "第 5 章: オープンソースのセキュリティ管理"
status: Completed
weight: 60
---

- [Introduction](#introduction)
- [Training and Education](#training-and-education)
- [Key Steps](#key-steps)
- [Applying This to Your Organization](#applying-this-to-your-organization)
- [Resources and Footnotes](#resources-and-footnotes)

## 序文

> 注: 本章は、Open Source Security Foundation（OpenSSF）の代表者たちの専門知識に基づき、TODO Groupの支援を受けて作成されました。

> NOTE: This chapter has been developed through the expertise of Open Source Security Foundation (OpenSSF) representatives, with support from the TODO Group

オープンソースソフトウェアは、ソフトウェアサプライチェーンの重要な要素です。このため、OSPO の責任の一環として、オープンソースサプライチェーンのセキュリティを確保するための支援が求められます。これには次のタスクが含まれます。

Open source software is an important part of the software supply chain. Because of this, it's part of an OSPO's responsibility to help secure the OSS supply chain. This includes tasks such as:

- 製品で利用するオープンソースのセキュリティを評価する開発チームを支援すること
- 開発チームのアップストリームのオープンソースプロジェクトへの貢献を促進し、そのセキュリティを向上させること
- 企業が維持、貢献、リードするオープンソースプロジェクトにおいて、セキュアなソフトウェア開発のベストプラクティスを遵守すること

- Helping development teams assess the security of the OSS they use in products.
- Encouraging development teams to contribute to upstream open source projects to help improve their security.
- Following secure software development best practices in open source projects that the company maintains, contributes to, or leads.

本章には、OSPO とオープンソース開発者が利用するソフトウェアと作成するソフトウェアの両方で、セキュアなソフトウェア開発とサプライチェーンのベストプラクティスを適用するための有用なリソースが含まれています。

This chapter includes useful resources to help OSPOs and open source developers apply secure software development and supply chain best practices - both in the software they use and the software they create.

ある意味では、セキュリティは他の要件と変わりません。しかし、多くのソフトウェア開発者とそのマネージャーは、セキュリティに関する十分なトレーニングを受けていません。また、セキュリティとは、知能的な攻撃者から守ることであり、システムの一部ではなく、システム全体の連携によって実現されることが多々あります。

In some ways, security is just like any other requirement. However, many software developers and their managers haven't received enough training in security. Also, security is about defending against intelligent attackers, and it often depends on how the entire system works together — not just on one part.

セキュリティ問題を後から修正するのは往往にして高コストです。予防し、発生する確率や影響を軽減し、万一発生した場合に備えることが重要です。また、最初から計画を立て、セキュリティを適切に扱うためのリソース（時間や資金など）を割り当てることは重要です。オープンソースソフトウェアは、大規模なピアレビューが可能で「オープンデザイン」の原則に従うため、セキュリティ上の優位性を持つ可能性があります。しかし、これらのメリットは自動で得られるものではありません。

Fixing security problems later is often expensive. It's better to prevent them, reduce their chances or impact, and be prepared in case something still goes wrong. It's important to plan from the beginning and allocate resources (such as time and money) to handle security properly. Open source software can have a security advantage because it allows for mass peer review and follows the principle of "open design" — but these benefits don't happen automatically.

トレーニングと教育
多くのソフトウェア開発者やマネージャーは、セキュリティに関する必要な知識を持っていません。この知識の不足は、しばしば問題を引き起こします。以下に、理解すべき重要な領域と、役立つ無料の OpenSSF コースへのリンクをまとめました。これらの特定のコースは必須ではありませんが、ソフトウェア開発に関わる全員が適切なトレーニングを受けることが重要です。
マネージャー（オープンソースとクローズドソースの両方のプロジェクト）は、セキュアなソフトウェア開発を管理する方法を理解する必要があります。これには、基本的なセキュリティ用語の理解、リスク管理の方法、設計段階でのセキュリティの組み込み、すべての環境の保護、リスクの早期発見、ステークホルダーとの明確な期待値の設定が含まれます。マネージャーは、開発者が学ぶべき内容も理解する必要があります。まだトレーニングを受けていない場合は、Open Source Security Foundation の無料コース「Security for Software Development Managers (LFD125)」を受講できます。
開発者は、セキュアなソフトウェア開発に関するコースを受講する必要があります。これには、計画、設計、コーディング、テスト、リリース各段階でのセキュアなソフトウェアの構築方法が含まれます。開発者は、サードパーティソフトウェアの評価方法も理解する必要があります。OWASP Top Ten for web apps 2 や CWE Top 25 for general software 3 などに含まれる一般的な脆弱性とその回避方法も理解する必要があります。また、開発環境のセキュリティ確保や脆弱性報告への対応方法も把握する必要があります。このトレーニングを受けていない場合は、無料の OpenSSF コース「Developing Secure Software (LFD121)」を受講できます。4.
開発者とマネージャーは、遵守が必要な法律や規制を必ず理解する必要があります。例えば、欧州連合（EU）で使用される可能性があるソフトウェアに関与する者は、EU サイバーレジリエンス法（CRA）を理解する必要があります。これには、CRA の適用範囲、定義される役割（製造者やオープンソース管理者など）、および CRA が定める法的責任が含まれます。CRA は広範な範囲をカバーし、厳しい罰則を定めているため、理解が必要な人は、OpenSSF の無料コース「Understanding the European Union (EU) Cyber Resilience Act (CRA)」（LFEL1001）を受講できます。
主要なステップ
自社ソフトウェアの開発の場合：
OpenSSF の「より安全なソフトウェア開発のための簡潔なガイド」を確認し、実践的なリソースへのリンクを参照してください 6.
OpenSSF の「Baseline」を満たすよう努めてください。これはセキュリティチェックの短いリストです 7.
プロジェクトに OpenSSF の「Best Practices」バッジを取得してください。最初は「パス」から始め、時間をかけて「シルバー」または「ゴールド」を目指す計画を立ててください 8.
OpenSSF スコアカードのスコアを向上させましょう。これは他のプロジェクトの評価によく使用されますが、自身の進捗を測定するのにも役立ちます 9.
現代のほとんどのソフトウェアは他のソフトウェアを再利用しています。オープンソースコンポーネントを選択し、慎重に使用してください：
「オープンソースソフトウェアの評価のための簡潔なガイド」を使用してください 10.
ソフトウェア名を再確認し、「タイポスクワッティング」攻撃（悪意のあるパッケージが信頼できるパッケージと似た名前を使用する攻撃）を回避してください。
OpenSSF スコアカードを使用して、使用前にソフトウェアを評価してください 9.
開発、ビルド、テスト、配布を含む環境を保護してください：
多要素認証（MFA）を使用して、攻撃者がアクセスしにくくしてください。
ビルド環境を保護してください。詳細なガイドラインは OpenSSF SLSA を参照してください 11.
継続的インテグレーション（CI）パイプラインで自動化されたツールを使用して、セキュリティ問題を早期に検出してください：
複数の種類のツールを使用してください。各ツールは異なる問題を検出する可能性があるため、セキュリティツールガイドを参照してください 12.
新規プロジェクト（グリーンフィールド）では、すべてのセキュリティチェックを有効化してください。既存プロジェクト（ブラウンフィールド）では、レポートが管理可能な範囲で最も重要なチェックから開始してください
再利用コンポーネントの既知の脆弱性を検出するツールを有効化してください
脆弱性報告に備えてください — どのプロジェクトにも発生する可能性があります。脆弱性を報告する方法について明確に説明してください。オープンソースプロジェクトは、OpenSSF の「協調的な脆弱性開示プロセスの実施ガイド」をレビューしてください 13.
組織への適用
組織内の OSS のセキュリティを向上させることは、ツールを使用するだけではありません。文化や日常の業務プロセスにおける変更も必要です。最初のステップの 1 つは、セキュリティは小さなチームの役割ではなく、全員の責任であるという意識を築くことです。リーダーは、セキュアなソフトウェア開発が重要であることを明確に伝え、時間、リソース、そして取り組む人への評価で支援する必要があります。
セキュリティ実践は日常の開発作業の一部であり、別物ではありません。例えば、セキュリティチェックを時々行うのではなく、スコアカードや脆弱性スキャンなどのツールを CI/CD パイプラインの定期的なプロセスに組み込むようにします。これにより、セキュリティがチームがソフトウェアを構築する際に当然かつ期待される部分となります。
トレーニングと教育は定期的に実施すべきで、一度きりで済ませるべきではありません。開発者やマネージャーは、セキュアなソフトウェア開発の基礎を学ぶよう奨励すべきです。これには OpenSSF の無料コースや他のプログラムが含まれます。チームがセキュリティの学習が重要であり、評価されることを理解するようにしましょう。これにより、長期的な関心と責任感が育まれます。
セキュリティの進捗状況をオープンにすることも重要です。チームが目標（例：ベストプラクティスバッジの取得やスコアカード結果の改善）の進捗を追跡し共有するよう促しましょう。これにより、問題が発生した際に責任を問われるのではなく、互いに助け合い改善するポジティブな環境が生まれます。
最後に、継続的な改善を支援しましょう。セキュリティは完了するものではなく、常に変化するものです。リスクのレビュー、ツールや実践方法の更新、チームが学んだことを共有する定期的な時間を設定しましょう。開発プロセス初期段階でセキュリティに関する意思決定をチームに委ねるようにし、問題が発生した後や最終段階で判断するのではなく、早期に判断できるようにしましょう。
共有責任の文化を築き、セキュリティを日常業務に組み込み、学習に投資し、オープンさを促進し、継続的に改善することで、組織は構築・利用する OSS のセキュリティ強化において真の進展を実現できます。

## Training and Education

Many software developers and managers don't know what they need to know about security. This lack of knowledge often causes problems. Here are some key areas to understand, along with links to free OpenSSF courses that can help. These specific courses aren't required, but it's important that everyone involved in software development gets the right training.

Managers (of both open and closed source projects) should understand how to manage secure software development. This includes knowing basic security terms, how to manage risks, how to build security into the design, how to protect all environments, how to identify risks early, and how to set clear expectations with stakeholders. Managers should also understand what their developers need to learn. If they haven't been trained yet, they can take the free Open Source Security Foundation OpenSSF course *Security for Software Development Managers (LFD125)* [^1].

Developers should take a course on secure software development. This includes how to build secure software during planning, design, coding, testing, and release. Developers also need to know how to evaluate third-party software. They should understand common vulnerabilities (like those in the OWASP Top Ten for web apps [^2] and CWE Top 25 for general software [^3]) and how to avoid them. They should also know how to secure development environments and respond to vulnerability reports. If they haven't had this training, they can take the free OpenSSF course Developing Secure Software (LFD121) [^4].

Both developers and managers must understand any laws or regulations they need to follow. For example, anyone involved in software that may be used in the European Union (EU) should understand the EU Cyber Resilience Act (CRA). This includes knowing what the CRA applies to, the different roles it defines (such as manufacturer or open source steward), and the legal responsibilities it creates. Because the CRA covers a wide range and includes strong penalties, those who need to understand it can take the free OpenSSF course Understanding the European Union (EU) Cyber Resilience Act (CRA) (LFEL1001) [^5].

## Key Steps

**For developing your own software:**

1. Review the OpenSSF Concise Guide for Developing More Secure Software, which links to practical resources [^6].

1. Work to meet the OpenSSF Baseline, a short list of security checks [^7].

1. Earn an OpenSSF Best Practices badge for your project. Start with "passing" and plan to achieve "silver" or "gold" over time [^8].

1. Improve your OpenSSF Scorecard score. While this is often used to evaluate other projects, it can also help you measure your own [^9].

**Most modern software reuses other software. Choose and use open source components carefully:**

1. Use the Concise Guide for Evaluating Open Source Software [^10].

1. Double-check software names to avoid "typosquatting" attacks (where malicious packages have names similar to trusted ones).

1. Use the OpenSSF Scorecard to evaluate software before using it [^9].


**Protect your environments, including development, build, test, and distribution:**

1. Use multi-factor authentication (MFA) to make it harder for attackers to gain access.
1. Secure your build environment. See OpenSSF SLSA for more guidance [^11].

**Use automated tools in your continuous integration (CI) pipeline to catch security issues early:**

1. Use multiple types of tools, as each may find different problems, see the Guide to Security Tools [^12].

1. For new projects ("green field"), enable all security checks. For older projects ("brown field"), start with the most important checks so the reports are manageable

1. Enable tools that detect known vulnerabilities in reused components

Prepare for vulnerability reports — they can happen to any project. Clearly explain how people can report vulnerabilities. Open source projects should review the OpenSSF Guide to implementing a coordinated vulnerability disclosure process [^13].

## Applying This to Your Organization

Improving the security of OSS in your organization isn't just about using tools. It also requires changes in culture and daily work processes. One of the first steps is to build a mindset where security is everyone's responsibility, not just the job of a small team. Leaders should clearly communicate that secure software development is important and support this with time, resources, and recognition for those who work on it.

Security practices should be part of everyday development work, not something separate. For example, instead of running security checks only once in a while, make tools like scorecards and vulnerability scans part of your regular CI/CD pipeline. This helps make security a normal and expected part of how your team builds software.

Training and education should happen regularly, not just once. Developers and managers should be encouraged to learn the basics of secure software development. This can include free OpenSSF courses and other programs. Make sure your teams know that learning about security is important and will be recognized. This builds long-term interest and responsibility.

It also helps to be open about security progress. Encourage teams to track and share their progress on goals like earning Best Practices badges or improving their Scorecard results. This creates a positive environment where teams help each other and improve together, instead of feeling blamed when something goes wrong.

Lastly, support continuous improvement. Security isn't something you finish — it's always changing. Set up regular times to review risks, update tools and practices, and share what your teams have learned. Give teams the freedom to make decisions about security early in the development process, not just at the end or after a problem happens.

By creating a culture of shared responsibility, adding security into everyday work, investing in learning, encouraging openness, and improving over time, your organization can make real progress in securing the OSS it builds and uses.

## Resources and Footnotes

### Resources

- OpenSSF: https://openssf.org/
- OWASP: https://owasp.org/
- CWE: https://cwe.mitre.org/index.html

### Footnotes

[^1]: Open Source Security Foundation OpenSSF course *Security for Software Development Managers (LFD125)*: https://training.linuxfoundation.org/training/security-for-software-development-managers-lfd125/

[^2]: OWASP Top Ten for web apps: https://owasp.org/www-project-top-ten/

[^3]: CWE Top 25 for general software: https://cwe.mitre.org/top25/

[^4]: OpenSSF course Developing Secure Software (LFD121): https://training.linuxfoundation.org/training/developing-secure-software-lfd121/

[^5]: Understanding the EU Cyber Resilience Act (CRA): https://training.linuxfoundation.org/express-learning/understanding-the-eu-cyber-resilience-act-cra-lfel1001/

[^6]: Concise Guide for Developing More Secure Software: https://best.openssf.org/Concise-Guide-for-Developing-More-Secure-Software

[^7]: OpenSSF Baseline: https://baseline.openssf.org/

[^8]: OpenSSF Best Practices badge: https://www.bestpractices.dev/

[^9]: OpenSSF Scorecard: https://github.com/ossf/scorecard

[^10]: Concise Guide for Evaluating Open Source Software: https://best.openssf.org/Concise-Guide-for-Evaluating-Open-Source-Software

[^11]: OpenSSF SLSA: https://slsa.dev/

[^12]: Guide to Security Tools: https://github.com/ossf/wg-security-tooling/blob/main/guide.md#readme

[^13]: OpenSSF Guide to implementing a coordinated vulnerability disclosure process: https://github.com/ossf/oss-vulnerability-guide/blob/main/maintainer-guide.md#readme
