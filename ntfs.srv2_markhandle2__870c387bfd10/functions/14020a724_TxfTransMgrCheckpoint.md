# TxfTransMgrCheckpoint

- ea: `0x14020a724`
- end: `0x14020b1ac`
- name: `TxfTransMgrCheckpoint`
- size: `2696`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, ULONG fFlags, __int64, char, char, char)`
- caller_count: `7`
- callee_count: `16`
- tags: ``

## callers

- `0x1400fa698`
- `0x1400fdbb4`
- `0x140102500`
- `0x14010315c`
- `0x1401d2f50`
- `0x1401d6948`
- `0x14025a2c8`

## callees

- `0x140008740`
- `0x14000cb00`
- `0x14000d1e0`
- `0x140010be0`
- `0x140010c54`
- `0x1400291f0`
- `0x140029d80`
- `0x14004173c`
- `0x140059250`
- `0x1400596c0`
- `0x14013ad80`
- `0x140140380`
- `0x1401913d4`
- `0x140209910`
- `0x14020a724`
- `0x14020b5f4`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14020a907`
- `ntoskrnl!KeReleaseMutex` at `0x14020aa0f`
- `ntoskrnl!KeReleaseMutex` at `0x14020aa24`
- `ntoskrnl!KeReleaseMutex` at `0x14020b191`
- `ntoskrnl!KeReleaseMutex` at `0x1402b3efb`
- `ntoskrnl!KeReleaseMutex` at `0x14020a907`
- `ntoskrnl!KeReleaseMutex` at `0x14020aa0f`
- `ntoskrnl!KeReleaseMutex` at `0x14020aa24`
- `ntoskrnl!KeReleaseMutex` at `0x14020b191`
- `ntoskrnl!KeReleaseMutex` at `0x1402b3efb`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020a88c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020a968`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020a9eb`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020acd5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020a88c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020a968`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020a9eb`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020acd5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14020ab0f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14020ab0f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14020a9a5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14020ae86`
- `ntoskrnl!ExAcquireFastMutex` at `0x14020a9a5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14020ae86`
- `ntoskrnl!ExReleaseFastMutex` at `0x14020a9cb`
- `ntoskrnl!ExReleaseFastMutex` at `0x14020aebb`
- `ntoskrnl!ExReleaseFastMutex` at `0x14020a9cb`
- `ntoskrnl!ExReleaseFastMutex` at `0x14020aebb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14020aa3c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14020aa3c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020a8b0`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020a986`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020aa93`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020af19`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020af3f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020afc0`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020a8b0`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020a986`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020aa93`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020af19`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020af3f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14020afc0`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020aea4`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020af5d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020af7b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020afda`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020aff8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020b130`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020aea4`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020af5d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020af7b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020afda`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020aff8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14020b130`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14020aab1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14020aae2`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14020aab1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14020aae2`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsWriteRestartArea` at `0x14020ae0b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsWriteRestartArea` at `0x14020ae0b`

## pseudocode

```c

```
