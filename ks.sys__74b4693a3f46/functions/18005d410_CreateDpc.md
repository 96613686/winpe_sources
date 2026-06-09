# CreateDpc

- ea: `0x18005d410`
- end: `0x18005d51c`
- name: `CreateDpc`
- size: `268`
- prototype: `__int64 __fastcall(PVOID DeferredContext, PKDEFERRED_ROUTINE DeferredRoutine, KDPC_IMPORTANCE Importance)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004b128`

## callees

- `0x180019fc0`
- `0x18005d410`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x18005d4ca`
- `ntoskrnl!KeInitializeDpc` at `0x18005d4ca`
- `ntoskrnl!KeSetImportanceDpc` at `0x18005d4dc`
- `ntoskrnl!KeSetImportanceDpc` at `0x18005d4dc`
- `ntoskrnl!KeInitializeSpinLock` at `0x18005d4fb`
- `ntoskrnl!KeInitializeSpinLock` at `0x18005d4fb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d43f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d48e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d43f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d48e`

## pseudocode

```c

```
