# NlInitTrustList(_DOMAIN_INFO *)

- ea: `0x18006a67c`
- end: `0x18006ab77`
- name: `?NlInitTrustList@@YAJPEAU_DOMAIN_INFO@@@Z`
- size: `1275`
- prototype: `__int64 __fastcall(struct _DOMAIN_INFO *)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x180026518`
- `0x180026d40`

## callees

- `0x180007518`
- `0x18000c440`
- `0x18000de8c`
- `0x18000e0e0`
- `0x180029c68`
- `0x180040f18`
- `0x180058b30`
- `0x18006834c`
- `0x180069a30`
- `0x18006a67c`
- `0x18006b5b4`
- `0x18006c3e4`
- `0x18006f6b0`
- `0x180088584`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18006aa73`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18006aa73`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006a70b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006a70b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a71b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006aa83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a71b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006aa83`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER_EX` at `0x18006a784`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER_EX` at `0x18006ab38`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER_EX` at `0x18006a784`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER_EX` at `0x18006ab38`
- `LSASRV!LsarEnumerateTrustedDomainsEx` at `0x18006a7c8`
- `LSASRV!LsarEnumerateTrustedDomainsEx` at `0x18006a7c8`
- `LSASRV!LsaIQueryForestTrustInfo` at `0x18006a915`
- `LSASRV!LsaIQueryForestTrustInfo` at `0x18006a915`
- `LSASRV!LsaIFreeForestTrustInfo` at `0x18006ab28`
- `LSASRV!LsaIFreeForestTrustInfo` at `0x18006ab28`
- `ntdll!RtlEqualDomainName` at `0x18006a851`
- `ntdll!RtlEqualDomainName` at `0x18006a851`
- `ntdll!RtlLeaveCriticalSection` at `0x18006aafc`
- `ntdll!RtlLeaveCriticalSection` at `0x18006aafc`
- `ntdll!RtlEnterCriticalSection` at `0x18006a6f8`
- `ntdll!RtlEnterCriticalSection` at `0x18006a6f8`
- `netutils!NetApiBufferFree` at `0x18006ab4d`
- `netutils!NetApiBufferFree` at `0x18006ab4d`

## string_xrefs

- `0x18006a8dd`: `NlInitTrustList: %wZ NlUpdateTrustList failed 0x%lx\n`
- `0x18006aabd`: `NlInitTrustList: Deleted from local trust list\n`

## pseudocode

```c

```
