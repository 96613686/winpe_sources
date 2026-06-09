# VidSchiCreateHwContextInternal(_VIDSCH_DEVICE *,_VIDSCH_CONTEXT_DATA *,DXGCONTEXT *)

- ea: `0x140042228`
- end: `0x1400427f6`
- name: `?VidSchiCreateHwContextInternal@@YAPEAUVIDSCH_HW_CONTEXT@@PEAU_VIDSCH_DEVICE@@PEAU_VIDSCH_CONTEXT_DATA@@PEAVDXGCONTEXT@@@Z`
- size: `1486`
- prototype: `struct VIDSCH_HW_CONTEXT *__fastcall(struct _VIDSCH_DEVICE *, struct _VIDSCH_CONTEXT_DATA *, struct DXGCONTEXT *)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x1400d931c`
- `0x140114970`

## callees

- `0x140002138`
- `0x140009790`
- `0x14000a358`
- `0x1400246a4`
- `0x1400246c0`
- `0x14002f510`
- `0x14003b25c`
- `0x1400416d8`
- `0x140042228`
- `0x140044e68`
- `0x14005159c`
- `0x140058680`
- `0x140058ac0`
- `0x1401162bc`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400426b5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400426b5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400427d3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400427d3`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x140042761`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1400427bc`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x140042761`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1400427bc`
- `ntoskrnl!KeInitializeEvent` at `0x14004234d`
- `ntoskrnl!KeInitializeEvent` at `0x14004234d`
- `ntoskrnl!ExAllocatePool2` at `0x140042274`
- `ntoskrnl!ExAllocatePool2` at `0x1400423b2`
- `ntoskrnl!ExAllocatePool2` at `0x140042274`
- `ntoskrnl!ExAllocatePool2` at `0x1400423b2`
- `watchdog!WdLogSingleEntry0` at `0x14004228b`
- `watchdog!WdLogSingleEntry0` at `0x1400423ca`
- `watchdog!WdLogSingleEntry0` at `0x14004228b`
- `watchdog!WdLogSingleEntry0` at `0x1400423ca`

## pseudocode

```c

```
