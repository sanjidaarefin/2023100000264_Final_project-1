# 🔍 Active Reconnaissance Report

> **Assessment Type:** Active Reconnaissance
> **Framework Reference:** TryHackMe — Active Reconnaissance Module
> **Visibility Level:** High (Direct Host Interaction)

---

## Objective

Conduct active reconnaissance against designated target systems to identify exposed services, open ports, and potential entry points that could be leveraged during later exploitation phases.

---

## Activities Performed

The following techniques were applied directly against the target infrastructure:

- **Host Discovery & Network Scanning** — Utilized `Nmap` to detect live hosts and map the network perimeter
- **Port Enumeration** — Systematically identified open TCP/UDP ports and the services bound to them
- **Service & OS Fingerprinting** — Extracted running service versions and inferred operating system details through banner analysis
- **Web Enumeration** — Inspected exposed web applications for structural and configuration disclosures

---

## Key Findings

| Finding | Detail |
|---|---|
| Open Ports | Multiple ports exposed directly to the internet |
| Identified Services | HTTP, SMB, RPC, and additional network services detected |
| Version Disclosure | Service banners revealed precise software versions, enabling fingerprinting |
| Outdated Services | Several running services appeared unpatched and potentially vulnerable |

---

## Security Impact

The services uncovered during this phase directly expand the organization's **external attack surface**. Exposed version information enables adversaries to cross-reference running software against public vulnerability databases (e.g., CVE registries, Exploit-DB), dramatically reducing the effort required to identify and launch targeted attacks.

Unfiltered access to services such as SMB and RPC further introduces the risk of lateral movement and credential-based exploitation from external threat actors.

---

## Recommendations

The following mitigations should be prioritized to reduce the identified attack surface:

1. **Disable Unnecessary Services & Ports** — Shut down any service not required for business operations and close associated ports at the firewall level
2. **Restrict External Access** — Enforce strict inbound firewall rules; only allow explicitly required traffic from trusted sources
3. **Patch & Update Regularly** — Establish a routine patch cycle for all internet-facing services to address known vulnerabilities promptly
4. **Suppress Version Disclosure** — Configure services and web servers to withhold software version details from response headers and banners
5. **Deploy Network Monitoring & IDS** — Implement intrusion detection systems (IDS) and continuous traffic monitoring to detect and alert on reconnaissance activity in real time

---

## Conclusion

The active reconnaissance phase successfully mapped the target's externally accessible services and identified several potential attack vectors. The findings confirm that without prompt remediation, the exposed infrastructure could be leveraged by an attacker during subsequent exploitation phases.

Immediate action on the recommendations above will significantly harden the target environment and reduce the risk of a successful intrusion.

---

*Report generated following TryHackMe Active Reconnaissance methodology.*
