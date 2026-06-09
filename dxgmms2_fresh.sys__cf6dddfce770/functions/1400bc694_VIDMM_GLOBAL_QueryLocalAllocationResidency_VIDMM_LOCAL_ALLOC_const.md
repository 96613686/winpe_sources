# VIDMM_GLOBAL::QueryLocalAllocationResidency(VIDMM_LOCAL_ALLOC const *)

- ea: `0x1400bc694`
- end: `0x1400bc85b`
- name: `?QueryLocalAllocationResidency@VIDMM_GLOBAL@@QEAA?AW4_D3DKMT_ALLOCATIONRESIDENCYSTATUS@@PEBUVIDMM_LOCAL_ALLOC@@@Z`
- size: `455`
- prototype: `enum _D3DKMT_ALLOCATIONRESIDENCYSTATUS __fastcall(VIDMM_GLOBAL *__hidden this, const struct VIDMM_LOCAL_ALLOC *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400bc67c`
- `0x14011c13c`

## callees

- `0x140004268`
- `0x14002bc54`
- `0x1400bc694`

## import_xrefs

- `ntoskrnl!ZwQueryVirtualMemory` at `0x1400bc77a`
- `ntoskrnl!ZwQueryVirtualMemory` at `0x1400bc77a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bc82c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bc82c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bc838`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bc838`
- `watchdog!WdLogSingleEntry0` at `0x1400bc7d2`
- `watchdog!WdLogSingleEntry0` at `0x1400bc7d2`

## string_xrefs

- `0x1400bc7e7`: `Query allocation residency failed or didn't return the expected scanned size\n`

## pseudocode

```c

```
