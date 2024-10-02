This page collects all the issues affecting the current design of today's PSL. The goal is to have a better understanding of the limitations to (hopefully) come with a better one.

## Issues

- Static list (akin to hosts.txt) vs Server-Based Solution

  This is a static list.  When list is infrequently updated this is a speed enhancement as a local source file, but when updates occur it can lead to stale behavior (a common example of this was during the 2014+ nTLDs sometimes being sent to search vs DNS by omnibox browsers with an old version of PSL locally, where an OS or software update that would update to catch up and remedy may have had long spans between)

- Power User Considerations - referral entries

  CDN / Cloud or other providers' needs for frequent updates or large inclusion blocks might merit considering the PSL including a new record type to refer a subsequent lookup to those providers' self-managed entries or evolving considerations such as DNS-based standards as they emerge, such as DBOUND via the IETF

- Finite resource

  This makes harder to consider patches such as https://github.com/publicsuffix/list/pull/277 that requires the merge of 19k `.NAME` rules.

- Intentional expression of intentional subdomain function is too blunt

  When a domain owner is using the PSL to express the manner in which there is preference of handling, it could be more crisp and deliberate.  Example: Domain owner seeks that cookies should exist in the subspace for foo.bar.com but may want to have/not have wildcard certificates issued for those same subspaces.

- Variance in the `*` or `!` interpretation and use

  For some of the more deliberately expressed entry use-cases, there seems to be variation in the use of ! or * prefixes which conflict; or, variance in the manner in which these are implemented in services, software or systems that utilize the PSL exist; or, some of these entries are ignored, not imported or used

- More richful format

  Use something different than a simple list of strings, that allows extensibility and extra fields. A possible alternative is either JSON or YAML.

- List metadata

  As for previous point, a different format may allow metadata to be added to the list (e.g. last update).

- Split private vs non-private

  There have been an increasing demand to separate the two lists for better management and reduce on-the-fly parsing.

- Convert to A-labels

  No UTF-8 please. (Follow [Universal Acceptance Steering Group](https://uasg.tech) recommendations.)

- Wildcard

  Clarify the use of wildcard. Today we implicitly support any wildcards, but all implementations support only left-outermost wildcard.

  Additionally, the behavior of wildcard and its use and implementation may vary by use-case

