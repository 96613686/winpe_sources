# VIDMM_GLOBAL::RecordVaPagingHistoryUpdatePte(VIDMM_PROCESS *,_DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE *,VIDMM_ALLOC *,VIDMM_GLOBAL_ALLOC *,uint)

- ea: `0x1400ff530`
- end: `0x1400ff729`
- name: `?RecordVaPagingHistoryUpdatePte@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_PROCESS@@PEAU_DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE@@PEAUVIDMM_ALLOC@@PEAUVIDMM_GLOBAL_ALLOC@@I@Z`
- size: `505`
- prototype: `void __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_PROCESS *, struct _DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE *, struct VIDMM_ALLOC *, struct VIDMM_GLOBAL_ALLOC *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140097f10`

## callees

- `0x14002d790`
- `0x1400ff530`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ff577`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ff577`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ff58c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ff58c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ff697`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ff697`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ff6a3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ff6a3`

## pseudocode

```c

```
