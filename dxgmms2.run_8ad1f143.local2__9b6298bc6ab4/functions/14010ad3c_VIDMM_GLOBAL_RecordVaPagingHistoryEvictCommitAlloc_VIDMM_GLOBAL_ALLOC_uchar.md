# VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(VIDMM_GLOBAL_ALLOC *,uchar)

- ea: `0x14010ad3c`
- end: `0x14010adf3`
- name: `?RecordVaPagingHistoryEvictCommitAlloc@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@E@Z`
- size: `183`
- prototype: `void(VIDMM_GLOBAL *__hidden this, struct VIDMM_GLOBAL_ALLOC *, unsigned __int8)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140094660`
- `0x14009fbf4`
- `0x1400a23e0`
- `0x1400a2a34`
- `0x1400a4490`

## callees

- `0x14002d790`
- `0x14003a468`
- `0x14010ad3c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14010ad55`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14010ad55`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010ad66`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010ad66`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010add1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010add1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010addd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010addd`

## pseudocode

```c

```
