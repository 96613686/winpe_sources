# RefsSynchronousMetadataIo

- ea: `0x1c003d7f8`
- end: `0x1c003dd32`
- name: `RefsSynchronousMetadataIo`
- size: `1338`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, ULONG Length, PVOID VirtualAddress, __int64, int, char)`
- caller_count: `9`
- callee_count: `16`
- tags: ``

## callers

- `0x1c003cff4`
- `0x1c003d28c`
- `0x1c003d730`
- `0x1c003d790`
- `0x1c009bed0`
- `0x1c009c560`
- `0x1c016f1bc`
- `0x1c019a088`
- `0x1c01d1084`

## callees

- `0x1c000f920`
- `0x1c0011660`
- `0x1c00133b0`
- `0x1c00133f0`
- `0x1c0014410`
- `0x1c003d7f8`
- `0x1c003de14`
- `0x1c003de50`
- `0x1c003e360`
- `0x1c003e3c4`
- `0x1c0068960`
- `0x1c0092bf0`
- `0x1c0092d08`
- `0x1c00980c8`
- `0x1c00b2300`
- `0x1c00b35c0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1c003da33`
- `ntoskrnl!KeInitializeEvent` at `0x1c003da33`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c003dbb0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c003dbb0`
- `ntoskrnl!DbgPrintEx` at `0x1c003dc00`
- `ntoskrnl!DbgPrintEx` at `0x1c003dca3`
- `ntoskrnl!DbgPrintEx` at `0x1c003dc00`
- `ntoskrnl!DbgPrintEx` at `0x1c003dca3`
- `ntoskrnl!IoAllocateMdl` at `0x1c003d94e`
- `ntoskrnl!IoAllocateMdl` at `0x1c003d94e`
- `ntoskrnl!MmProbeAndLockPages` at `0x1c003d96b`
- `ntoskrnl!MmProbeAndLockPages` at `0x1c003d96b`
- `ntoskrnl!IoFreeMdl` at `0x1c003d99c`
- `ntoskrnl!IoFreeMdl` at `0x1c003dccd`
- `ntoskrnl!IoFreeMdl` at `0x1c003d99c`
- `ntoskrnl!IoFreeMdl` at `0x1c003dccd`
- `ntoskrnl!MmUnlockPages` at `0x1c003dcbd`
- `ntoskrnl!MmUnlockPages` at `0x1c003dcbd`
- `ntoskrnl!MmMdlPageContentsState` at `0x1c003d980`
- `ntoskrnl!MmMdlPageContentsState` at `0x1c003d980`
- `ntoskrnl!IoFreeIrp` at `0x1c003d9b0`
- `ntoskrnl!IoFreeIrp` at `0x1c003dcf6`
- `ntoskrnl!IoFreeIrp` at `0x1c003d9b0`
- `ntoskrnl!IoFreeIrp` at `0x1c003dcf6`

## string_xrefs

- `0x1c003dbf2`: `SynchronousMinstoreIo (readcopy) to Vcb: %p TargetDeviceObject: %p returned unexpected status %08lx (will be reported only once)\n`
- `0x1c003dc6f`: `write`

## pseudocode

```c

```
