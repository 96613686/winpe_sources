# NlDnsAddDomainRecords(_DOMAIN_INFO *,ulong)

- ea: `0x18001fe18`
- end: `0x180020474`
- name: `?NlDnsAddDomainRecords@@YAKPEAU_DOMAIN_INFO@@K@Z`
- size: `1628`
- prototype: `unsigned int __fastcall(struct _DOMAIN_INFO *, unsigned int)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x180020480`
- `0x1800267ec`
- `0x180029218`

## callees

- `0x18000c440`
- `0x18000e910`
- `0x18001fe18`
- `0x180020a34`
- `0x180021540`
- `0x1800239e8`
- `0x180025114`
- `0x180025a38`
- `0x180025a74`
- `0x1800276ac`
- `0x1800453e0`
- `0x18004a234`
- `0x18008927c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800200c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800200c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fed2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fed2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fef4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800203f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020443`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fef4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800203f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020443`
- `ntdll!RtlLeaveCriticalSection` at `0x1800200ff`
- `ntdll!RtlLeaveCriticalSection` at `0x1800203da`
- `ntdll!RtlLeaveCriticalSection` at `0x1800200ff`
- `ntdll!RtlLeaveCriticalSection` at `0x1800203da`
- `ntdll!RtlEnterCriticalSection` at `0x18001ff52`
- `ntdll!RtlEnterCriticalSection` at `0x180020094`
- `ntdll!RtlEnterCriticalSection` at `0x18001ff52`
- `ntdll!RtlEnterCriticalSection` at `0x180020094`
- `netutils!NetApiBufferFree` at `0x180020407`
- `netutils!NetApiBufferFree` at `0x18002041b`
- `netutils!NetApiBufferFree` at `0x180020407`
- `netutils!NetApiBufferFree` at `0x18002041b`
- `DNSAPI!DnsScreenLocalAddrsForRegistration` at `0x18001ff18`
- `DNSAPI!DnsScreenLocalAddrsForRegistration` at `0x18001ff18`

## string_xrefs

- `0x18002011a`: `NlDnsAddDomainRecords: Skipping name %ws (per registry)\n`

## pseudocode

```c

```
