# TxfDoWriteFileLogging

- ea: `0x14010046c`
- end: `0x140100a04`
- name: `TxfDoWriteFileLogging`
- size: `1432`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64, __int64, unsigned __int64, __int64, int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140039038`
- `0x140100f30`

## callees

- `0x140059250`
- `0x1400596c0`
- `0x14010046c`
- `0x14018e638`
- `0x1401902dc`
- `0x1401909d0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140100956`
- `ntoskrnl!KeReleaseMutex` at `0x14010099d`
- `ntoskrnl!KeReleaseMutex` at `0x1402c4a00`
- `ntoskrnl!KeReleaseMutex` at `0x140100956`
- `ntoskrnl!KeReleaseMutex` at `0x14010099d`
- `ntoskrnl!KeReleaseMutex` at `0x1402c4a00`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010081f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010081f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401008b5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401008b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401007f0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100835`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100970`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401007f0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100835`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100970`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401007bb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401007bb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1401007d2`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1401008cc`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1401007d2`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1401008cc`

## pseudocode

```c

```
