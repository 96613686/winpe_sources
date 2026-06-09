# ClassSendDeviceIoControlSynchronous

- ea: `0x14005e2e0`
- end: `0x14005e518`
- name: `ClassSendDeviceIoControlSynchronous`
- size: `568`
- prototype: `void __stdcall(ULONG IoControlCode, PDEVICE_OBJECT TargetDeviceObject, PVOID Buffer, ULONG InputBufferLength, ULONG OutputBufferLength, BOOLEAN InternalDeviceIoControl, PIO_STATUS_BLOCK IoStatus)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140014198`
- `0x140017df8`
- `0x14003aed8`
- `0x14003b364`
- `0x1400579b4`
- `0x140058e90`
- `0x14005e0a0`

## callees

- `0x140017630`
- `0x14003e640`
- `0x14005e2e0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14005e413`
- `ntoskrnl!IoFreeIrp` at `0x14005e473`
- `ntoskrnl!IoFreeIrp` at `0x14005e4ab`
- `ntoskrnl!IoFreeIrp` at `0x140061841`
- `ntoskrnl!IoFreeIrp` at `0x14005e413`
- `ntoskrnl!IoFreeIrp` at `0x14005e473`
- `ntoskrnl!IoFreeIrp` at `0x14005e4ab`
- `ntoskrnl!IoFreeIrp` at `0x140061841`
- `ntoskrnl!IoAllocateMdl` at `0x1400617ed`
- `ntoskrnl!IoAllocateMdl` at `0x1400617ed`
- `ntoskrnl!ExAllocatePool2` at `0x14005e379`
- `ntoskrnl!ExAllocatePool2` at `0x14005e379`
- `ntoskrnl!IoFreeMdl` at `0x14005e45b`
- `ntoskrnl!IoFreeMdl` at `0x140061832`
- `ntoskrnl!IoFreeMdl` at `0x14005e45b`
- `ntoskrnl!IoFreeMdl` at `0x140061832`
- `ntoskrnl!IoAllocateIrp` at `0x14005e30a`
- `ntoskrnl!IoAllocateIrp` at `0x14005e30a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e400`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e400`
- `ntoskrnl!MmUnlockPages` at `0x14005e44b`
- `ntoskrnl!MmUnlockPages` at `0x14005e44b`
- `ntoskrnl!MmProbeAndLockPages` at `0x140061815`
- `ntoskrnl!MmProbeAndLockPages` at `0x140061815`

## pseudocode

```c

```
