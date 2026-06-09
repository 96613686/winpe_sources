# LsapPerUserCacheRefreshNeeded(_PER_USER_CACHE_ENTRY *,int *)

- ea: `0x1800639fc`
- end: `0x180063c1b`
- name: `?LsapPerUserCacheRefreshNeeded@@YAJPEAU_PER_USER_CACHE_ENTRY@@PEAH@Z`
- size: `543`
- prototype: `__int64 __fastcall(struct _PER_USER_CACHE_ENTRY *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800638ec`
- `0x180063e80`

## callees

- `0x1800639fc`
- `0x1800b212c`
- `0x1800b2fd4`
- `0x1801082a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063b67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063b67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063ba4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063ba4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180063ad2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180063ad2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063a6a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063a6a`
- `ntdll!RtlConvertExclusiveToShared` at `0x180063b53`
- `ntdll!RtlConvertExclusiveToShared` at `0x180063be1`
- `ntdll!RtlConvertExclusiveToShared` at `0x180063b53`
- `ntdll!RtlConvertExclusiveToShared` at `0x180063be1`
- `ntdll!RtlConvertSharedToExclusive` at `0x180063b31`
- `ntdll!RtlConvertSharedToExclusive` at `0x180063bbf`
- `ntdll!RtlConvertSharedToExclusive` at `0x180063b31`
- `ntdll!RtlConvertSharedToExclusive` at `0x180063bbf`

## pseudocode

```c

```
