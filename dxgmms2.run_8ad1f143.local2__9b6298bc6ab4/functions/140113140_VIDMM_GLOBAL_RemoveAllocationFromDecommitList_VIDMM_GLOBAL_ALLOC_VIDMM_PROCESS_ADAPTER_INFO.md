# VIDMM_GLOBAL::RemoveAllocationFromDecommitList(VIDMM_GLOBAL_ALLOC *,VIDMM_PROCESS_ADAPTER_INFO *)

- ea: `0x140113140`
- end: `0x140113208`
- name: `?RemoveAllocationFromDecommitList@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@PEAUVIDMM_PROCESS_ADAPTER_INFO@@@Z`
- size: `200`
- prototype: `void __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_GLOBAL_ALLOC *, struct VIDMM_PROCESS_ADAPTER_INFO *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14009ced0`
- `0x14010416c`
- `0x140113110`

## callees

- `0x140113140`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401131a1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401131a1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140113172`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140113172`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140113161`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140113161`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401131ad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401131ad`

## pseudocode

```c

```
