# TxfReadFileNonCached

- ea: `0x140101650`
- end: `0x140101854`
- name: `TxfReadFileNonCached`
- size: `516`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PLARGE_INTEGER StartingOffset, ULONG Length, PVOID VirtualAddress)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140100f30`

## callees

- `0x140007ea0`
- `0x140101650`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x140101695`
- `ntoskrnl!IoAllocateMdl` at `0x140101695`
- `ntoskrnl!MmProbeAndLockPages` at `0x1401016e5`
- `ntoskrnl!MmProbeAndLockPages` at `0x1401016e5`
- `ntoskrnl!IoFreeMdl` at `0x140101835`
- `ntoskrnl!IoFreeMdl` at `0x1402c4d9a`
- `ntoskrnl!IoFreeMdl` at `0x140101835`
- `ntoskrnl!IoFreeMdl` at `0x1402c4d9a`
- `ntoskrnl!MmUnlockPages` at `0x140101826`
- `ntoskrnl!MmUnlockPages` at `0x1402c4d89`
- `ntoskrnl!MmUnlockPages` at `0x140101826`
- `ntoskrnl!MmUnlockPages` at `0x1402c4d89`
- `ntoskrnl!IoPageRead` at `0x140101724`
- `ntoskrnl!IoPageRead` at `0x140101724`
- `ntoskrnl!KeWaitForSingleObject` at `0x140101751`
- `ntoskrnl!KeWaitForSingleObject` at `0x140101751`
- `ntoskrnl!KeInitializeEvent` at `0x140101700`
- `ntoskrnl!KeInitializeEvent` at `0x140101700`
- `ntoskrnl!ExRaiseStatus` at `0x1401016cf`
- `ntoskrnl!ExRaiseStatus` at `0x1401017a4`
- `ntoskrnl!ExRaiseStatus` at `0x140101816`
- `ntoskrnl!ExRaiseStatus` at `0x1401016cf`
- `ntoskrnl!ExRaiseStatus` at `0x1401017a4`
- `ntoskrnl!ExRaiseStatus` at `0x140101816`

## pseudocode

```c

```
