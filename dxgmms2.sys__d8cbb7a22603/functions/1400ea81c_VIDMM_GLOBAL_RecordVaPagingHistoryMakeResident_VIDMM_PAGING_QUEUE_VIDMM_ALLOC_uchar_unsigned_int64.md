# VIDMM_GLOBAL::RecordVaPagingHistoryMakeResident(VIDMM_PAGING_QUEUE *,VIDMM_ALLOC *,uchar,unsigned __int64)

- ea: `0x1400ea81c`
- end: `0x1400ea8fd`
- name: `?RecordVaPagingHistoryMakeResident@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_QUEUE@@PEAUVIDMM_ALLOC@@E_K@Z`
- size: `225`
- prototype: `void __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_PAGING_QUEUE *, struct VIDMM_ALLOC *, unsigned __int8, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400ea180`

## callees

- `0x14002a670`
- `0x1400ea81c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ea83a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ea83a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ea84b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ea84b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ea8d7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ea8d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ea8e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ea8e3`

## pseudocode

```c

```
