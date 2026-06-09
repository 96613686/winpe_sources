# VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(VIDMM_GLOBAL_ALLOC *,uchar)

- ea: `0x14010e858`
- end: `0x14010e90f`
- name: `?RecordVaPagingHistoryEvictCommitAlloc@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@E@Z`
- size: `183`
- prototype: `void(VIDMM_GLOBAL *__hidden this, struct VIDMM_GLOBAL_ALLOC *, unsigned __int8)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400982d0`
- `0x1400a0d94`
- `0x1400a3580`
- `0x1400a4770`
- `0x1400a8924`

## callees

- `0x14002a670`
- `0x1400393e8`
- `0x14010e858`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14010e871`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14010e871`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010e882`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010e882`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010e8ed`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010e8ed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010e8f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010e8f9`

## pseudocode

```c

```
