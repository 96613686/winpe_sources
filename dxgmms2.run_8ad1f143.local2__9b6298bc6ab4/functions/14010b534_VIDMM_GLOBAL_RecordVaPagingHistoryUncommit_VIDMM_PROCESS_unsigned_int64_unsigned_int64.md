# VIDMM_GLOBAL::RecordVaPagingHistoryUncommit(VIDMM_PROCESS *,unsigned __int64,unsigned __int64)

- ea: `0x14010b534`
- end: `0x14010b5e0`
- name: `?RecordVaPagingHistoryUncommit@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_PROCESS@@_K1@Z`
- size: `172`
- prototype: `void __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_PROCESS *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14009634c`

## callees

- `0x14002d790`
- `0x14010b534`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14010b552`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14010b552`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010b563`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010b563`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010b5bc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010b5bc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010b5c8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010b5c8`

## pseudocode

```c

```
