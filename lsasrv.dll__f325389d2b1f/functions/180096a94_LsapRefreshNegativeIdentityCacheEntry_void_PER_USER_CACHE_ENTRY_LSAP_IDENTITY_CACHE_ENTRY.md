# LsapRefreshNegativeIdentityCacheEntry(void *,_PER_USER_CACHE_ENTRY *,_LSAP_IDENTITY_CACHE_ENTRY *)

- ea: `0x180096a94`
- end: `0x180096d21`
- name: `?LsapRefreshNegativeIdentityCacheEntry@@YAJPEAXPEAU_PER_USER_CACHE_ENTRY@@PEAU_LSAP_IDENTITY_CACHE_ENTRY@@@Z`
- size: `653`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle, struct _PER_USER_CACHE_ENTRY *, struct _LSAP_IDENTITY_CACHE_ENTRY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180064da4`

## callees

- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x180096a94`
- `0x1800b2f90`
- `0x1800b86d0`
- `0x180114630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096c5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096c5d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180096b01`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180096b01`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180096c47`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180096c47`
- `ntdll!RtlConvertExclusiveToShared` at `0x180096b72`
- `ntdll!RtlConvertExclusiveToShared` at `0x180096c8b`
- `ntdll!RtlConvertExclusiveToShared` at `0x180096b72`
- `ntdll!RtlConvertExclusiveToShared` at `0x180096c8b`
- `ntdll!RtlConvertSharedToExclusive` at `0x180096b53`
- `ntdll!RtlConvertSharedToExclusive` at `0x180096c1a`
- `ntdll!RtlConvertSharedToExclusive` at `0x180096b53`
- `ntdll!RtlConvertSharedToExclusive` at `0x180096c1a`
- `ntdll!NtClose` at `0x180096ca4`
- `ntdll!NtClose` at `0x180096ca4`
- `ntdll!NtDuplicateToken` at `0x180096bfd`
- `ntdll!NtDuplicateToken` at `0x180096bfd`

## pseudocode

```c

```
