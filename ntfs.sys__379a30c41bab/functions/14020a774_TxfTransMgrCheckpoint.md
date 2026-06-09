# TxfTransMgrCheckpoint

- ea: `0x14020a774`
- end: `0x14020b1fc`
- name: `TxfTransMgrCheckpoint`
- size: `2696`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, ULONG fFlags, __int64, char, char, char)`
- caller_count: `7`
- callee_count: `16`
- tags: ``

## callers

- `0x1400fa6e8`
- `0x1400fdc04`
- `0x140102550`
- `0x1401031ac`
- `0x1401d2fa0`
- `0x1401d6998`
- `0x14025a318`

## callees

- `0x140008740`
- `0x14000cb00`
- `0x14000d1e0`
- `0x140010be0`
- `0x140010c54`
- `0x1400291f0`
- `0x140029d80`
- `0x14004173c`
- `0x1400592c0`
- `0x140059740`
- `0x14013add0`
- `0x1401403d0`
- `0x140191424`
- `0x140209960`
- `0x14020a774`
- `0x14020b644`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14020a957`
- `ntoskrnl!KeReleaseMutex` at `0x14020aa5f`
- `ntoskrnl!KeReleaseMutex` at `0x14020aa74`
- `ntoskrnl!KeReleaseMutex` at `0x14020b1e1`
- `ntoskrnl!KeReleaseMutex` at `0x1402b3f4b`
- `ntoskrnl!KeReleaseMutex` at `0x14020a957`
- `ntoskrnl!KeReleaseMutex` at `0x14020aa5f`
- `ntoskrnl!KeReleaseMutex` at `0x14020aa74`
- `ntoskrnl!KeReleaseMutex` at `0x14020b1e1`
- `ntoskrnl!KeReleaseMutex` at `0x1402b3f4b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020a8dc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020a9b8`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020aa3b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020ad25`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020a8dc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020a9b8`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020aa3b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020ad25`
- `ntoskrnl!ExReleaseResourceLite` at `0x14020ab5f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14020ab5f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14020a9f5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14020aed6`
- `ntoskrnl!ExAcquireFastMutex` at `0x14020a9f5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14020aed6`
- `ntoskrnl!ExReleaseFastMutex` at `0x14020aa1b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14020af0b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14020aa1b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14020af0b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14020aa8c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14020aa8c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020a900`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020a9d6`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020aae3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020af69`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020af8f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020b010`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020a900`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020a9d6`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020aae3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020af69`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020af8f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020b010`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020aef4`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020afad`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020afcb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020b02a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020b048`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020b180`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020aef4`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020afad`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020afcb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020b02a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020b048`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020b180`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14020ab01`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14020ab32`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14020ab01`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14020ab32`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsWriteRestartArea` at `0x14020ae5b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsWriteRestartArea` at `0x14020ae5b`

## pseudocode

```c

```
