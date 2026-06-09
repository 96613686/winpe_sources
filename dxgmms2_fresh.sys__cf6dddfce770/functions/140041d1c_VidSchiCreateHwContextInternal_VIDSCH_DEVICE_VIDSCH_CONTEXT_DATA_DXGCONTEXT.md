# VidSchiCreateHwContextInternal(_VIDSCH_DEVICE *,_VIDSCH_CONTEXT_DATA *,DXGCONTEXT *)

- ea: `0x140041d1c`
- end: `0x1400422ea`
- name: `?VidSchiCreateHwContextInternal@@YAPEAUVIDSCH_HW_CONTEXT@@PEAU_VIDSCH_DEVICE@@PEAU_VIDSCH_CONTEXT_DATA@@PEAVDXGCONTEXT@@@Z`
- size: `1486`
- prototype: `struct VIDSCH_HW_CONTEXT *__fastcall(struct _VIDSCH_DEVICE *, struct _VIDSCH_CONTEXT_DATA *, struct DXGCONTEXT *)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x1400e177c`
- `0x1401184f0`

## callees

- `0x140002138`
- `0x140009420`
- `0x140009fe8`
- `0x140021784`
- `0x1400217a0`
- `0x14002c5d0`
- `0x140039f6c`
- `0x1400403fc`
- `0x140041d1c`
- `0x14004506c`
- `0x140051cac`
- `0x140058f50`
- `0x140059380`
- `0x140119bac`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400421a9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400421a9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400422c7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400422c7`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x140042255`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1400422b0`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x140042255`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1400422b0`
- `ntoskrnl!KeInitializeEvent` at `0x140041e41`
- `ntoskrnl!KeInitializeEvent` at `0x140041e41`
- `ntoskrnl!ExAllocatePool2` at `0x140041d68`
- `ntoskrnl!ExAllocatePool2` at `0x140041ea6`
- `ntoskrnl!ExAllocatePool2` at `0x140041d68`
- `ntoskrnl!ExAllocatePool2` at `0x140041ea6`
- `watchdog!WdLogSingleEntry0` at `0x140041d7f`
- `watchdog!WdLogSingleEntry0` at `0x140041ebe`
- `watchdog!WdLogSingleEntry0` at `0x140041d7f`
- `watchdog!WdLogSingleEntry0` at `0x140041ebe`

## pseudocode

```c

```
