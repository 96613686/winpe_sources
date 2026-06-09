# VIDMM_GLOBAL::RecordVaPagingHistoryUpdatePte(VIDMM_PROCESS *,_DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE *,VIDMM_ALLOC *,VIDMM_GLOBAL_ALLOC *,uint)

- ea: `0x140108ff0`
- end: `0x1401091e9`
- name: `?RecordVaPagingHistoryUpdatePte@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_PROCESS@@PEAU_DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE@@PEAUVIDMM_ALLOC@@PEAUVIDMM_GLOBAL_ALLOC@@I@Z`
- size: `505`
- prototype: `void __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_PROCESS *, struct _DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE *, struct VIDMM_ALLOC *, struct VIDMM_GLOBAL_ALLOC *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14009ba58`

## callees

- `0x14002a670`
- `0x140108ff0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140109037`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140109037`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010904c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010904c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140109157`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140109157`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140109163`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140109163`

## pseudocode

```c

```
