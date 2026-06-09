# VIDMM_PAGE_TABLE::InvalidatePageTable(VIDMM_GLOBAL *,uint,uint,COMMIT_VA_STATE *)

- ea: `0x140103950`
- end: `0x140103b5b`
- name: `?InvalidatePageTable@VIDMM_PAGE_TABLE@@QEAAXPEAVVIDMM_GLOBAL@@IIPEAUCOMMIT_VA_STATE@@@Z`
- size: `523`
- prototype: `void __fastcall(VIDMM_PAGE_TABLE *__hidden this, struct VIDMM_GLOBAL *, unsigned int, unsigned int, struct COMMIT_VA_STATE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400994b0`
- `0x14009b008`

## callees

- `0x140103950`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140103a71`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140103a71`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140103a86`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140103a86`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140103b12`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140103b12`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140103b1e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140103b1e`

## pseudocode

```c

```
