# VIDMM_GLOBAL::RecordVaPagingHistoryCommit(VIDMM_PROCESS *,unsigned __int64,unsigned __int64,uint,unsigned __int64,_DXGK_ADL const *,void *,VIDMM_VAD_OWNER_TYPE)

- ea: `0x14010c048`
- end: `0x14010c12e`
- name: `?RecordVaPagingHistoryCommit@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_PROCESS@@_K1I1PEBU_DXGK_ADL@@PEAXW4VIDMM_VAD_OWNER_TYPE@@@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14009634c`

## callees

- `0x14002d790`
- `0x14010c048`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14010c066`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14010c066`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010c077`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010c077`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010c10a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010c10a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010c116`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010c116`

## pseudocode

```c

```
