# LsapDbLookupNameChainRequestNew(_LSAPR_TRUST_INFORMATION_EX *,ulong,_UNICODE_STRING *,_LSA_REFERENCED_DOMAIN_LIST * *,_LSA_TRANSLATED_SID_EX2 * *,_LSAP_LOOKUP_LEVEL,ulong *)

- ea: `0x1801028dc`
- end: `0x180102de8`
- name: `?LsapDbLookupNameChainRequestNew@@YAJPEAU_LSAPR_TRUST_INFORMATION_EX@@KPEAU_UNICODE_STRING@@PEAPEAU_LSA_REFERENCED_DOMAIN_LIST@@PEAPEAU_LSA_TRANSLATED_SID_EX2@@W4_LSAP_LOOKUP_LEVEL@@PEAK@Z`
- size: `1292`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801035d0`

## callees

- `0x180013b20`
- `0x1800293c0`
- `0x180071d00`
- `0x180080430`
- `0x18008e360`
- `0x180091cb4`
- `0x180097c3c`
- `0x1800b1b90`
- `0x1800c7e28`
- `0x18010141c`
- `0x1801028dc`
- `0x1801038f8`
- `0x18011d48c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102b9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102bb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102da5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102db5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102dc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102b9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102bb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102da5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102db5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102dc4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180102bc9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180102bc9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180102975`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180102cdc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180102975`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180102cdc`
- `ntdll!RtlInitUnicodeString` at `0x180102d31`
- `ntdll!RtlInitUnicodeString` at `0x180102d31`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaICLookupNamesWithCreds` at `0x180102a5a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaICLookupNamesWithCreds` at `0x180102a5a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaICLookupNames` at `0x180102afe`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaICLookupNames` at `0x180102afe`

## pseudocode

```c

```
