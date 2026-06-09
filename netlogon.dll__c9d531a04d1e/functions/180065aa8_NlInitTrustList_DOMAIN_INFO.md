# NlInitTrustList(_DOMAIN_INFO *)

- ea: `0x180065aa8`
- end: `0x180065f54`
- name: `?NlInitTrustList@@YAJPEAU_DOMAIN_INFO@@@Z`
- size: `1196`
- prototype: `__int64 __fastcall(struct _DOMAIN_INFO *)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x18002545c`
- `0x180025bc0`

## callees

- `0x180007278`
- `0x18000bd98`
- `0x18000d874`
- `0x18000da94`
- `0x180028750`
- `0x18003e71c`
- `0x180054f60`
- `0x1800639e0`
- `0x180064f64`
- `0x180065aa8`
- `0x180066904`
- `0x18006769c`
- `0x18006a694`
- `0x1800824b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180065e75`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180065e75`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180065b31`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180065b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065b3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065e7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065b3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065e7f`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER_EX` at `0x180065b9e`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER_EX` at `0x180065f22`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER_EX` at `0x180065b9e`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER_EX` at `0x180065f22`
- `LSASRV!LsarEnumerateTrustedDomainsEx` at `0x180065bdc`
- `LSASRV!LsarEnumerateTrustedDomainsEx` at `0x180065bdc`
- `LSASRV!LsaIQueryForestTrustInfo` at `0x180065d1d`
- `LSASRV!LsaIQueryForestTrustInfo` at `0x180065d1d`
- `LSASRV!LsaIFreeForestTrustInfo` at `0x180065f18`
- `LSASRV!LsaIFreeForestTrustInfo` at `0x180065f18`
- `ntdll!RtlEqualDomainName` at `0x180065c5f`
- `ntdll!RtlEqualDomainName` at `0x180065c5f`
- `ntdll!RtlLeaveCriticalSection` at `0x180065ef2`
- `ntdll!RtlLeaveCriticalSection` at `0x180065ef2`
- `ntdll!RtlEnterCriticalSection` at `0x180065b24`
- `ntdll!RtlEnterCriticalSection` at `0x180065b24`
- `netutils!NetApiBufferFree` at `0x180065f31`
- `netutils!NetApiBufferFree` at `0x180065f31`

## string_xrefs

- `0x180065ce5`: `NlInitTrustList: %wZ NlUpdateTrustList failed 0x%lx\n`
- `0x180065eb3`: `NlInitTrustList: Deleted from local trust list\n`

## pseudocode

```c

```
