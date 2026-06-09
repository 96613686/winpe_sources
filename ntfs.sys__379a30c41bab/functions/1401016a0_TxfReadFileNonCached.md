# TxfReadFileNonCached

- ea: `0x1401016a0`
- end: `0x1401018a4`
- name: `TxfReadFileNonCached`
- size: `516`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PLARGE_INTEGER StartingOffset, ULONG Length, PVOID VirtualAddress)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140100f80`

## callees

- `0x140007ea0`
- `0x1401016a0`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1401016e5`
- `ntoskrnl!IoAllocateMdl` at `0x1401016e5`
- `ntoskrnl!MmProbeAndLockPages` at `0x140101735`
- `ntoskrnl!MmProbeAndLockPages` at `0x140101735`
- `ntoskrnl!IoFreeMdl` at `0x140101885`
- `ntoskrnl!IoFreeMdl` at `0x1402c4dea`
- `ntoskrnl!IoFreeMdl` at `0x140101885`
- `ntoskrnl!IoFreeMdl` at `0x1402c4dea`
- `ntoskrnl!MmUnlockPages` at `0x140101876`
- `ntoskrnl!MmUnlockPages` at `0x1402c4dd9`
- `ntoskrnl!MmUnlockPages` at `0x140101876`
- `ntoskrnl!MmUnlockPages` at `0x1402c4dd9`
- `ntoskrnl!IoPageRead` at `0x140101774`
- `ntoskrnl!IoPageRead` at `0x140101774`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401017a1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401017a1`
- `ntoskrnl!KeInitializeEvent` at `0x140101750`
- `ntoskrnl!KeInitializeEvent` at `0x140101750`
- `ntoskrnl!ExRaiseStatus` at `0x14010171f`
- `ntoskrnl!ExRaiseStatus` at `0x1401017f4`
- `ntoskrnl!ExRaiseStatus` at `0x140101866`
- `ntoskrnl!ExRaiseStatus` at `0x14010171f`
- `ntoskrnl!ExRaiseStatus` at `0x1401017f4`
- `ntoskrnl!ExRaiseStatus` at `0x140101866`

## pseudocode

```c

```
