# VIDMM_GLOBAL::RecordVaPagingHistoryMakeResident(VIDMM_PAGING_QUEUE *,VIDMM_ALLOC *,uchar,unsigned __int64)

- ea: `0x1400e241c`
- end: `0x1400e24fd`
- name: `?RecordVaPagingHistoryMakeResident@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_QUEUE@@PEAUVIDMM_ALLOC@@E_K@Z`
- size: `225`
- prototype: `void __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_PAGING_QUEUE *, struct VIDMM_ALLOC *, unsigned __int8, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400e1d30`

## callees

- `0x14002d790`
- `0x1400e241c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e243a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e243a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e244b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e244b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e24d7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e24d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e24e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e24e3`

## pseudocode

```c

```
