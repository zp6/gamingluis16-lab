<h1 align="center">Silicon Pulse Security Research</h1>

<p align="center">
  <strong>Passive Network Intelligence · RouterOS Security · MikroTik Research</strong><br/>
  <em>Discovering what others call impossible</em>
</p>

---

## What I Do

I build passive security analysis tools that reveal deep network intelligence using only read access — no credentials, no intrusion, no noise.

**Core research areas:**
- **RouterOS/MikroTik security** — PPTP session prediction, boot PRNG reconstruction, Winbox fingerprinting
- **SNMP-based traffic intelligence** — Session correlation, entropy modeling, behavioral profiling
- **Network pattern analysis** — Finding signals in traffic that others overlook

---

## Silicon Pulse Framework

> *Predict, fingerprint, and profile MikroTik networks using only SNMP read access.*

| Capability | Method | Accuracy |
|---|---|---|
| PPTP Call ID prediction | sysUpTime time-series | ±1 CID/hour |
| Boot PRNG reconstruction | FNV-1a + XorShift128+ | ±1 second |
| Admin session detection | Winbox keepalive (60s / 148–310B) | Passive |
| Traffic behavior profiling | Entropy + cross-correlation | r=0.99 |

**→ [silicon-pulse](https://github.com/gamingluis16-lab/silicon-pulse)** — open-source, MIT licensed

---

## Findings (RouterOS 6.x)

- `call_id = (sysUpTime_seconds) % 65535` — fully predictable from SNMP
- Boot seed: `FNV-1a(serial) XOR boot_epoch` — reconstructable via 2 public OIDs
- Winbox sessions leave a detectable 60.0s ±0.3s signature on MGMT interface
- VPN session traffic correlates at r=0.99 — coordinated access patterns visible passively

**Affected:** RouterOS 6.x (all), partially mitigated in 6.49.8+  
**Disclosed:** MikroTik notified via security@mikrotik.com

---

## Services

Available for:
- **RouterOS / MikroTik security audits** — passive assessment, no disruption
- **ISP network security consulting** — traffic analysis, vulnerability assessment
- **Custom security research** — if you have an interesting problem, I have unconventional methods

**Contact:** silicon.pulse.sec@proton.me

---

## Stack

```
Python 3  ·  SNMP (net-snmp)  ·  RouterOS  ·  Network protocols
Passive analysis  ·  Statistical modeling  ·  Time-series prediction
```

---

<p align="center">
  <em>"Without asking, nothing is discovered."</em>
</p>
