# TxfCLRAndUndoWriteFile

- ea: `0x1401032b0`
- end: `0x140103f68`
- name: `TxfCLRAndUndoWriteFile`
- size: `3256`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x140133f80`
- `0x1401d8390`

## callees

- `0x140007ea0`
- `0x140059440`
- `0x1400b6e90`
- `0x1401032b0`
- `0x140107228`
- `0x140133244`
- `0x140163fc8`
- `0x14018e688`
- `0x14020bbc0`
- `0x140294b6c`

## import_xrefs

- `ntoskrnl!CcMapData` at `0x14010354b`
- `ntoskrnl!CcMapData` at `0x14010354b`
- `ntoskrnl!CcPreparePinWrite` at `0x140103634`
- `ntoskrnl!CcPreparePinWrite` at `0x140103634`
- `ntoskrnl!KeReleaseMutex` at `0x140103dc0`
- `ntoskrnl!KeReleaseMutex` at `0x140103e0a`
- `ntoskrnl!KeReleaseMutex` at `0x140103f2f`
- `ntoskrnl!KeReleaseMutex` at `0x1402c5101`
- `ntoskrnl!KeReleaseMutex` at `0x140103dc0`
- `ntoskrnl!KeReleaseMutex` at `0x140103e0a`
- `ntoskrnl!KeReleaseMutex` at `0x140103f2f`
- `ntoskrnl!KeReleaseMutex` at `0x1402c5101`
- `ntoskrnl!DbgPrintEx` at `0x1401037df`
- `ntoskrnl!DbgPrintEx` at `0x1401039db`
- `ntoskrnl!DbgPrintEx` at `0x1401037df`
- `ntoskrnl!DbgPrintEx` at `0x1401039db`
- `ntoskrnl!KeWaitForSingleObject` at `0x140103c7b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140103e5d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140103c7b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140103e5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140103e1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c504e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c511c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140103e1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c504e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c511c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140103b43`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140103b43`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140103d09`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140103e80`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140103d09`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140103e80`
- `ntoskrnl!CcUnpinData` at `0x140103903`
- `ntoskrnl!CcUnpinData` at `0x14010391c`
- `ntoskrnl!CcUnpinData` at `0x1402c501a`
- `ntoskrnl!CcUnpinData` at `0x1402c5033`
- `ntoskrnl!CcUnpinData` at `0x140103903`
- `ntoskrnl!CcUnpinData` at `0x14010391c`
- `ntoskrnl!CcUnpinData` at `0x1402c501a`
- `ntoskrnl!CcUnpinData` at `0x1402c5033`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103934`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103985`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103c4d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103c91`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103de1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103f50`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c506c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c50c0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103934`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103985`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103c4d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103c91`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103de1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140103f50`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c506c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c50c0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140103c0a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140103c0a`
- `ntoskrnl!ExRaiseStatus` at `0x140103ad3`
- `ntoskrnl!ExRaiseStatus` at `0x140103ad3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x140103b05`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x140103b05`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140103c28`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140103d27`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140103e9e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140103c28`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140103d27`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140103e9e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x140103405`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x140103405`

## pseudocode

```c

```
