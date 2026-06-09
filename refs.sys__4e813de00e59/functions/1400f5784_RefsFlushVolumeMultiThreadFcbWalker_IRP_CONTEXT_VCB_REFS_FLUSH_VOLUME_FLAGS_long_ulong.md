# RefsFlushVolumeMultiThreadFcbWalker(_IRP_CONTEXT *,_VCB *,REFS_FLUSH_VOLUME_FLAGS,long *,ulong)

- ea: `0x1400f5784`
- end: `0x1400f5a85`
- name: `?RefsFlushVolumeMultiThreadFcbWalker@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@W4REFS_FLUSH_VOLUME_FLAGS@@PEAJK@Z`
- size: `769`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1403366e0`

## callees

- `0x140076ad0`
- `0x1400862c0`
- `0x1400d0fd8`
- `0x1400f5784`
- `0x1401f3fc0`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1400f58e0`
- `ntoskrnl!ExQueueWorkItem` at `0x1400f58e0`
- `ntoskrnl!KeSetEvent` at `0x1400f594d`
- `ntoskrnl!KeSetEvent` at `0x1400f594d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f5917`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f5980`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f5917`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f5980`
- `ntoskrnl!KeInitializeEvent` at `0x1400f5820`
- `ntoskrnl!KeInitializeEvent` at `0x1400f5843`
- `ntoskrnl!KeInitializeEvent` at `0x1400f5866`
- `ntoskrnl!KeInitializeEvent` at `0x1400f5820`
- `ntoskrnl!KeInitializeEvent` at `0x1400f5843`
- `ntoskrnl!KeInitializeEvent` at `0x1400f5866`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f5a59`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f5a59`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400f5884`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400f5884`

## pseudocode

```c

```
