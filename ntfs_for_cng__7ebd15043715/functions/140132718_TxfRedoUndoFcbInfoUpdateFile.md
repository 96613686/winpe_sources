# TxfRedoUndoFcbInfoUpdateFile

- ea: `0x140132718`
- end: `0x1401331ee`
- name: `TxfRedoUndoFcbInfoUpdateFile`
- size: `2774`
- prototype: `void __fastcall(__int64, const CLFS_LSN *, _BYTE *, const CLFS_LSN *)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140133f30`
- `0x1401d8340`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000d1e0`
- `0x140012e70`
- `0x140020de0`
- `0x1400410a8`
- `0x140059250`
- `0x1400593c0`
- `0x1400596c0`
- `0x1400f957c`
- `0x1401250b0`
- `0x1401261d0`
- `0x140131620`
- `0x140132718`
- `0x1401331f4`
- `0x140140380`
- `0x1401419ec`
- `0x1401620c0`
- `0x14018e638`
- `0x1401913d4`
- `0x1401982b0`
- `0x14019a718`
- `0x1401aab20`
- `0x1401e0660`
- `0x140294b1c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140132e06`
- `ntoskrnl!DbgPrintEx` at `0x140132f29`
- `ntoskrnl!DbgPrintEx` at `0x140132e06`
- `ntoskrnl!DbgPrintEx` at `0x140132f29`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401330aa`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401330aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013318a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6416`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013318a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6416`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140132903`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140132903`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140132ca2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140132ca2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140133052`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401331c7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a63ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x140133052`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401331c7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a63ce`
- `ntoskrnl!ExRaiseStatus` at `0x140132e6f`
- `ntoskrnl!ExRaiseStatus` at `0x140132e6f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401328db`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401328db`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140133078`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140133078`

## pseudocode

```c

```
