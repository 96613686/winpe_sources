# CreateDpc

- ea: `0x18005d5b0`
- end: `0x18005d6bc`
- name: `CreateDpc`
- size: `268`
- prototype: `__int64 __fastcall(PVOID DeferredContext, PKDEFERRED_ROUTINE DeferredRoutine, KDPC_IMPORTANCE Importance)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004b268`

## callees

- `0x18001a000`
- `0x18005d5b0`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x18005d66a`
- `ntoskrnl!KeInitializeDpc` at `0x18005d66a`
- `ntoskrnl!KeSetImportanceDpc` at `0x18005d67c`
- `ntoskrnl!KeSetImportanceDpc` at `0x18005d67c`
- `ntoskrnl!KeInitializeSpinLock` at `0x18005d69b`
- `ntoskrnl!KeInitializeSpinLock` at `0x18005d69b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d5df`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d62e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d5df`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d62e`

## pseudocode

```c

```
