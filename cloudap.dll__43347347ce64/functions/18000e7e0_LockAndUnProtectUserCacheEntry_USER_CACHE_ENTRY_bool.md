# LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)

- ea: `0x18000e7e0`
- end: `0x18000e8f4`
- name: `?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z`
- size: `276`
- prototype: `void __fastcall(struct _USER_CACHE_ENTRY *, bool)`
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800035b4`
- `0x18000e990`
- `0x180016a10`
- `0x180017780`
- `0x180027320`
- `0x180033750`
- `0x180037240`
- `0x18003e2f0`
- `0x1800476a0`
- `0x1800479f0`
- `0x180048530`
- `0x180048e60`
- `0x18004a870`
- `0x18004bb2c`
- `0x180052358`
- `0x1800545f0`
- `0x1800571b0`
- `0x1800579a0`

## callees

- `0x18000e7e0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000e8b0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000e8b0`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e88d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e8bb`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e88d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e8bb`
- `ntdll!RtlReleaseResource` at `0x18000e8a5`
- `ntdll!RtlReleaseResource` at `0x18000e8a5`
- `ntdll!RtlAcquireResourceShared` at `0x18000e802`
- `ntdll!RtlAcquireResourceShared` at `0x18000e802`
- `ntdll!RtlEnterCriticalSection` at `0x18000e80c`
- `ntdll!RtlEnterCriticalSection` at `0x18000e80c`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e886`

## pseudocode

```c

```
