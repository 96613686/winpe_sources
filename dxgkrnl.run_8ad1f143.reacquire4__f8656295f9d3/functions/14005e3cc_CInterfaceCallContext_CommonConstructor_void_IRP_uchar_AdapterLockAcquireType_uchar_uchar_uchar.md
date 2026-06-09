# CInterfaceCallContext::CommonConstructor(void *,_IRP *,uchar,AdapterLockAcquireType,uchar,uchar,uchar)

- ea: `0x14005e3cc`
- end: `0x14005e6d8`
- name: `?CommonConstructor@CInterfaceCallContext@@AEAAXPEAXPEAU_IRP@@EW4AdapterLockAcquireType@@EEE@Z`
- size: `780`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400537ec`
- `0x14008c408`

## callees

- `0x140022264`
- `0x14005e3cc`
- `0x14008c5b8`
- `0x1401fd48c`
- `0x1401fd870`
- `0x1403668f8`
- `0x1403676e0`
- `0x14037b2b0`
- `0x1403e2c50`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e534`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e534`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e458`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e4d6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e550`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e458`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e4d6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e550`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e5d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e6b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e5d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e6b7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005e483`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005e57f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005e483`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005e57f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005e4ef`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005e4ef`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e5cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e6ab`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e5cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e6ab`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14005e40a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14005e40a`
- `watchdog!WdLogSingleEntry1` at `0x14005e423`
- `watchdog!WdLogSingleEntry1` at `0x14005e66e`
- `watchdog!WdLogSingleEntry1` at `0x14005e423`
- `watchdog!WdLogSingleEntry1` at `0x14005e66e`

## pseudocode

```c

```
