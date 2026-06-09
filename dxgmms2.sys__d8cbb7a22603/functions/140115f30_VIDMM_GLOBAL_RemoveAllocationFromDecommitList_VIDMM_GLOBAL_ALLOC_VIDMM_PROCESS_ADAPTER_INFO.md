# VIDMM_GLOBAL::RemoveAllocationFromDecommitList(VIDMM_GLOBAL_ALLOC *,VIDMM_PROCESS_ADAPTER_INFO *)

- ea: `0x140115f30`
- end: `0x140115ff8`
- name: `?RemoveAllocationFromDecommitList@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@PEAUVIDMM_PROCESS_ADAPTER_INFO@@@Z`
- size: `200`
- prototype: `void __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_GLOBAL_ALLOC *, struct VIDMM_PROCESS_ADAPTER_INFO *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140097580`
- `0x1400f24e0`
- `0x140115f00`

## callees

- `0x140115f30`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140115f91`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140115f91`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140115f62`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140115f62`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140115f51`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140115f51`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140115f9d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140115f9d`

## pseudocode

```c

```
