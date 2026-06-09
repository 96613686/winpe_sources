# LsapDbLookupNameChainRequestLegacy(_LSAPR_TRUST_INFORMATION_EX *,ulong,_UNICODE_STRING *,_LSA_REFERENCED_DOMAIN_LIST * *,_LSA_TRANSLATED_SID_EX2 * *,_LSAP_LOOKUP_LEVEL,ulong *,ulong *)

- ea: `0x180102324`
- end: `0x1801028d5`
- name: `?LsapDbLookupNameChainRequestLegacy@@YAJPEAU_LSAPR_TRUST_INFORMATION_EX@@KPEAU_UNICODE_STRING@@PEAPEAU_LSA_REFERENCED_DOMAIN_LIST@@PEAPEAU_LSA_TRANSLATED_SID_EX2@@W4_LSAP_LOOKUP_LEVEL@@PEAK5@Z`
- size: `1457`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801035d0`

## callees

- `0x180013b20`
- `0x1800293c0`
- `0x180071d00`
- `0x18008e360`
- `0x180097c3c`
- `0x1800b1b90`
- `0x1800c7e28`
- `0x1800ec654`
- `0x18010141c`
- `0x180101d1c`
- `0x180102324`
- `0x1801032e8`
- `0x1801038f8`
- `0x18011d48c`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801025c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102870`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801025c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102870`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801023c5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180102797`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801023c5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180102797`
- `ntdll!RtlInitUnicodeString` at `0x1801027d9`
- `ntdll!RtlInitUnicodeString` at `0x1801027d9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaICLookupNamesWithCreds` at `0x1801024e0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaICLookupNamesWithCreds` at `0x1801024e0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180102855`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180102855`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaICLookupNames` at `0x1801026c2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaICLookupNames` at `0x1801026c2`

## pseudocode

```c

```
