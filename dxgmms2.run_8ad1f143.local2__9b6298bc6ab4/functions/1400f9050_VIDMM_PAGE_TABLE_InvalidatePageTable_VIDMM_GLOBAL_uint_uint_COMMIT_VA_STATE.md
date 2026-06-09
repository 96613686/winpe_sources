# VIDMM_PAGE_TABLE::InvalidatePageTable(VIDMM_GLOBAL *,uint,uint,COMMIT_VA_STATE *)

- ea: `0x1400f9050`
- end: `0x1400f925b`
- name: `?InvalidatePageTable@VIDMM_PAGE_TABLE@@QEAAXPEAVVIDMM_GLOBAL@@IIPEAUCOMMIT_VA_STATE@@@Z`
- size: `523`
- prototype: `void __fastcall(VIDMM_PAGE_TABLE *__hidden this, struct VIDMM_GLOBAL *, unsigned int, unsigned int, struct COMMIT_VA_STATE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140095960`
- `0x1400974b8`

## callees

- `0x1400f9050`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f9171`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f9171`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400f9186`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400f9186`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400f9212`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400f9212`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f921e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f921e`

## pseudocode

```c

```
