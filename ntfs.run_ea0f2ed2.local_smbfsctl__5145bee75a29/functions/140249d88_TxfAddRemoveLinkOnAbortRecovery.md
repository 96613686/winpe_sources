# TxfAddRemoveLinkOnAbortRecovery

- ea: `0x140249d88`
- end: `0x14024a58e`
- name: `TxfAddRemoveLinkOnAbortRecovery`
- size: `2054`
- prototype: `__int64 __fastcall(int, int, int, int, char, CLFS_LSN *plsn2, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x14010778c`
- `0x1401085c0`
- `0x14010d5e8`
- `0x14010d9c8`
- `0x14010dad0`

## callees

- `0x140007ea0`
- `0x140020de0`
- `0x1400370bc`
- `0x1400389a4`
- `0x140059250`
- `0x1400596c0`
- `0x1401331f4`
- `0x14018e638`
- `0x140249d88`
- `0x14024a898`
- `0x14024a9a8`
- `0x14024ad14`
- `0x140294b1c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140249efe`
- `ntoskrnl!DbgPrintEx` at `0x140249f8f`
- `ntoskrnl!DbgPrintEx` at `0x14024a3cc`
- `ntoskrnl!DbgPrintEx` at `0x14024a559`
- `ntoskrnl!DbgPrintEx` at `0x140249efe`
- `ntoskrnl!DbgPrintEx` at `0x140249f8f`
- `ntoskrnl!DbgPrintEx` at `0x14024a3cc`
- `ntoskrnl!DbgPrintEx` at `0x14024a559`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14024a245`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14024a245`
- `ntoskrnl!ExRaiseStatus` at `0x14024a0f8`
- `ntoskrnl!ExRaiseStatus` at `0x14024a1cb`
- `ntoskrnl!ExRaiseStatus` at `0x14024a3f4`
- `ntoskrnl!ExRaiseStatus` at `0x14024a581`
- `ntoskrnl!ExRaiseStatus` at `0x14024a0f8`
- `ntoskrnl!ExRaiseStatus` at `0x14024a1cb`
- `ntoskrnl!ExRaiseStatus` at `0x14024a3f4`
- `ntoskrnl!ExRaiseStatus` at `0x14024a581`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14024a21c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14024a21c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x140249f49`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x140249f49`

## pseudocode

```c

```
