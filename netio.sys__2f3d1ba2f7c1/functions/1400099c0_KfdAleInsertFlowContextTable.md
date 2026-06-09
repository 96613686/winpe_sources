# KfdAleInsertFlowContextTable

- ea: `0x1400099c0`
- end: `0x140009c40`
- name: `KfdAleInsertFlowContextTable`
- size: `640`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140019f10`

## callees

- `0x1400099c0`
- `0x140009c50`
- `0x140009e00`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x140009a97`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140009a97`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140009a40`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140009aca`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140009a40`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140009aca`
- `ntoskrnl!KeGetCurrentIrql` at `0x140009a08`
- `ntoskrnl!KeGetCurrentIrql` at `0x140009a08`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009a23`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009a23`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009af4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009af4`

## string_xrefs

- `0x140009bd6`: `RtlCreateHashTable`

## pseudocode

```c

```
