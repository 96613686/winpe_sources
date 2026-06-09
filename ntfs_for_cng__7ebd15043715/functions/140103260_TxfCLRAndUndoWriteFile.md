# TxfCLRAndUndoWriteFile

- ea: `0x140103260`
- end: `0x140103f18`
- name: `TxfCLRAndUndoWriteFile`
- size: `3256`
- prototype: `void(__int64, __int64, __int64, const CLFS_LSN *, ...)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x140133f30`
- `0x1401d8340`

## callees

- `0x140007ea0`
- `0x1400593c0`
- `0x1400b6e90`
- `0x140103260`
- `0x1401071d8`
- `0x1401331f4`
- `0x140163f78`
- `0x14018e638`
- `0x14020bb70`
- `0x140294b1c`

## import_xrefs

- `ntoskrnl!CcMapData` at `0x1401034fb`
- `ntoskrnl!CcMapData` at `0x1401034fb`
- `ntoskrnl!CcPreparePinWrite` at `0x1401035e4`
- `ntoskrnl!CcPreparePinWrite` at `0x1401035e4`
- `ntoskrnl!KeReleaseMutex` at `0x140103d70`
- `ntoskrnl!KeReleaseMutex` at `0x140103dba`
- `ntoskrnl!KeReleaseMutex` at `0x140103edf`
- `ntoskrnl!KeReleaseMutex` at `0x1402c50b1`
- `ntoskrnl!KeReleaseMutex` at `0x140103d70`
- `ntoskrnl!KeReleaseMutex` at `0x140103dba`
- `ntoskrnl!KeReleaseMutex` at `0x140103edf`
- `ntoskrnl!KeReleaseMutex` at `0x1402c50b1`
- `ntoskrnl!DbgPrintEx` at `0x14010378f`
- `ntoskrnl!DbgPrintEx` at `0x14010398b`
- `ntoskrnl!DbgPrintEx` at `0x14010378f`
- `ntoskrnl!DbgPrintEx` at `0x14010398b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140103c2b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140103e0d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140103c2b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140103e0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140103dcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c4ffe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c50cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140103dcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c4ffe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c50cc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140103af3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140103af3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140103cb9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140103e30`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140103cb9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140103e30`
- `ntoskrnl!CcUnpinData` at `0x1401038b3`
- `ntoskrnl!CcUnpinData` at `0x1401038cc`
- `ntoskrnl!CcUnpinData` at `0x1402c4fca`
- `ntoskrnl!CcUnpinData` at `0x1402c4fe3`
- `ntoskrnl!CcUnpinData` at `0x1401038b3`
- `ntoskrnl!CcUnpinData` at `0x1401038cc`
- `ntoskrnl!CcUnpinData` at `0x1402c4fca`
- `ntoskrnl!CcUnpinData` at `0x1402c4fe3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401038e4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103935`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103bfd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103c41`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103d91`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103f00`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c501c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5070`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401038e4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103935`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103bfd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103c41`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103d91`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103f00`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c501c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5070`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140103bba`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140103bba`
- `ntoskrnl!ExRaiseStatus` at `0x140103a83`
- `ntoskrnl!ExRaiseStatus` at `0x140103a83`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x140103ab5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x140103ab5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140103bd8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140103cd7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140103e4e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140103bd8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140103cd7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140103e4e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401033b5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401033b5`

## pseudocode

```c

```
