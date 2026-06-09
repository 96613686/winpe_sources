# VIDMM_GLOBAL::QueryLocalAllocationResidency(VIDMM_LOCAL_ALLOC const *)

- ea: `0x1400b8cac`
- end: `0x1400b8e73`
- name: `?QueryLocalAllocationResidency@VIDMM_GLOBAL@@QEAA?AW4_D3DKMT_ALLOCATIONRESIDENCYSTATUS@@PEBUVIDMM_LOCAL_ALLOC@@@Z`
- size: `455`
- prototype: `enum _D3DKMT_ALLOCATIONRESIDENCYSTATUS __fastcall(VIDMM_GLOBAL *__hidden this, const struct VIDMM_LOCAL_ALLOC *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400b8c94`
- `0x140118600`

## callees

- `0x1400045ec`
- `0x14002eb94`
- `0x1400b8cac`

## import_xrefs

- `ntoskrnl!ZwQueryVirtualMemory` at `0x1400b8d92`
- `ntoskrnl!ZwQueryVirtualMemory` at `0x1400b8d92`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400b8e44`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400b8e44`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b8e50`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b8e50`
- `watchdog!WdLogSingleEntry0` at `0x1400b8dea`
- `watchdog!WdLogSingleEntry0` at `0x1400b8dea`

## string_xrefs

- `0x1400b8dff`: `Query allocation residency failed or didn't return the expected scanned size\n`

## pseudocode

```c

```
