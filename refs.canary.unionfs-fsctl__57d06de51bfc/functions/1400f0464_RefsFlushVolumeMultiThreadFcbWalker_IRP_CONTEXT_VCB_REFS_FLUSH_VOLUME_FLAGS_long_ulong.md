# RefsFlushVolumeMultiThreadFcbWalker(_IRP_CONTEXT *,_VCB *,REFS_FLUSH_VOLUME_FLAGS,long *,ulong)

- ea: `0x1400f0464`
- end: `0x1400f0765`
- name: `?RefsFlushVolumeMultiThreadFcbWalker@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@W4REFS_FLUSH_VOLUME_FLAGS@@PEAJK@Z`
- size: `769`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140334a20`

## callees

- `0x140081670`
- `0x14008dbd0`
- `0x1400ca788`
- `0x1400f0464`
- `0x1401e9ce0`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1400f05c0`
- `ntoskrnl!ExQueueWorkItem` at `0x1400f05c0`
- `ntoskrnl!KeSetEvent` at `0x1400f062d`
- `ntoskrnl!KeSetEvent` at `0x1400f062d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f05f7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f0660`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f05f7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f0660`
- `ntoskrnl!KeInitializeEvent` at `0x1400f0500`
- `ntoskrnl!KeInitializeEvent` at `0x1400f0523`
- `ntoskrnl!KeInitializeEvent` at `0x1400f0546`
- `ntoskrnl!KeInitializeEvent` at `0x1400f0500`
- `ntoskrnl!KeInitializeEvent` at `0x1400f0523`
- `ntoskrnl!KeInitializeEvent` at `0x1400f0546`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f0739`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f0739`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400f0564`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400f0564`

## pseudocode

```c

```
