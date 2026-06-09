# VIDMM_GLOBAL::RecordVaPagingHistoryUncommit(VIDMM_PROCESS *,unsigned __int64,unsigned __int64)

- ea: `0x14010f14c`
- end: `0x14010f1f8`
- name: `?RecordVaPagingHistoryUncommit@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_PROCESS@@_K1@Z`
- size: `172`
- prototype: `void __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_PROCESS *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140099e9c`

## callees

- `0x14002a670`
- `0x14010f14c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14010f16a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14010f16a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010f17b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010f17b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010f1d4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010f1d4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010f1e0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010f1e0`

## pseudocode

```c

```
