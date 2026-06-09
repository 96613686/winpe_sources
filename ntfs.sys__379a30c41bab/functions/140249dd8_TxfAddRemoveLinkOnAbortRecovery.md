# TxfAddRemoveLinkOnAbortRecovery

- ea: `0x140249dd8`
- end: `0x14024a5de`
- name: `TxfAddRemoveLinkOnAbortRecovery`
- size: `2054`
- prototype: `__int64 __fastcall(int, int, int, int, char, CLFS_LSN *plsn2, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1401077dc`
- `0x140108610`
- `0x14010d638`
- `0x14010da18`
- `0x14010db20`

## callees

- `0x140007ea0`
- `0x140020de0`
- `0x1400370bc`
- `0x1400389a4`
- `0x1400592c0`
- `0x140059740`
- `0x140133244`
- `0x14018e688`
- `0x140249dd8`
- `0x14024a8e8`
- `0x14024a9f8`
- `0x14024ad64`
- `0x140294b6c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140249f4e`
- `ntoskrnl!DbgPrintEx` at `0x140249fdf`
- `ntoskrnl!DbgPrintEx` at `0x14024a41c`
- `ntoskrnl!DbgPrintEx` at `0x14024a5a9`
- `ntoskrnl!DbgPrintEx` at `0x140249f4e`
- `ntoskrnl!DbgPrintEx` at `0x140249fdf`
- `ntoskrnl!DbgPrintEx` at `0x14024a41c`
- `ntoskrnl!DbgPrintEx` at `0x14024a5a9`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14024a295`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14024a295`
- `ntoskrnl!ExRaiseStatus` at `0x14024a148`
- `ntoskrnl!ExRaiseStatus` at `0x14024a21b`
- `ntoskrnl!ExRaiseStatus` at `0x14024a444`
- `ntoskrnl!ExRaiseStatus` at `0x14024a5d1`
- `ntoskrnl!ExRaiseStatus` at `0x14024a148`
- `ntoskrnl!ExRaiseStatus` at `0x14024a21b`
- `ntoskrnl!ExRaiseStatus` at `0x14024a444`
- `ntoskrnl!ExRaiseStatus` at `0x14024a5d1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14024a26c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14024a26c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x140249f99`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x140249f99`

## pseudocode

```c

```
