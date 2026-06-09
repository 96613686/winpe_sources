# NlDnsAddDomainRecords(_DOMAIN_INFO *,ulong)

- ea: `0x18001efcc`
- end: `0x18001f5db`
- name: `?NlDnsAddDomainRecords@@YAKPEAU_DOMAIN_INFO@@K@Z`
- size: `1551`
- prototype: `__int64 __fastcall(struct _DOMAIN_INFO *, char)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x18001f5f0`
- `0x180025708`
- `0x180027d78`

## callees

- `0x18000bd98`
- `0x18000e270`
- `0x18001efcc`
- `0x18001fb74`
- `0x18002063c`
- `0x1800228ac`
- `0x180024074`
- `0x180024a64`
- `0x180024adc`
- `0x18002647c`
- `0x1800426cc`
- `0x1800470e0`
- `0x1800830e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f256`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f256`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f082`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f082`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f09e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f573`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f5b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f09e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f573`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f5b1`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f28b`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f560`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f28b`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f560`
- `ntdll!RtlEnterCriticalSection` at `0x18001f0f0`
- `ntdll!RtlEnterCriticalSection` at `0x18001f22c`
- `ntdll!RtlEnterCriticalSection` at `0x18001f0f0`
- `ntdll!RtlEnterCriticalSection` at `0x18001f22c`
- `netutils!NetApiBufferFree` at `0x18001f581`
- `netutils!NetApiBufferFree` at `0x18001f58f`
- `netutils!NetApiBufferFree` at `0x18001f581`
- `netutils!NetApiBufferFree` at `0x18001f58f`
- `DNSAPI!DnsScreenLocalAddrsForRegistration` at `0x18001f0bc`
- `DNSAPI!DnsScreenLocalAddrsForRegistration` at `0x18001f0bc`

## string_xrefs

- `0x18001f2a0`: `NlDnsAddDomainRecords: Skipping name %ws (per registry)\n`

## pseudocode

```c

```
