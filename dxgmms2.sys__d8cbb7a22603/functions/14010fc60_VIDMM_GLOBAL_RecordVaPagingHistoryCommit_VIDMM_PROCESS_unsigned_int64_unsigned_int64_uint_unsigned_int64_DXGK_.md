# VIDMM_GLOBAL::RecordVaPagingHistoryCommit(VIDMM_PROCESS *,unsigned __int64,unsigned __int64,uint,unsigned __int64,_DXGK_ADL const *,void *,VIDMM_VAD_OWNER_TYPE)

- ea: `0x14010fc60`
- end: `0x14010fd46`
- name: `?RecordVaPagingHistoryCommit@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_PROCESS@@_K1I1PEBU_DXGK_ADL@@PEAXW4VIDMM_VAD_OWNER_TYPE@@@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140099e9c`

## callees

- `0x14002a670`
- `0x14010fc60`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14010fc7e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14010fc7e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010fc8f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010fc8f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010fd22`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010fd22`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010fd2e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010fd2e`

## pseudocode

```c

```
