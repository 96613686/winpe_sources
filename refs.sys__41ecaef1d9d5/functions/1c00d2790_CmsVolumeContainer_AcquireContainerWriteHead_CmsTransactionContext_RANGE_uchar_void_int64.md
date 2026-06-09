# CmsVolumeContainer::AcquireContainerWriteHead(CmsTransactionContext *,_RANGE,uchar,void * *,__int64 *)

- ea: `0x1c00d2790`
- end: `0x1c00d2da7`
- name: `?AcquireContainerWriteHead@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@U_RANGE@@EPEAPEAXPEA_J@Z`
- size: `1559`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x1c00b1354`
- `0x1c00d2790`
- `0x1c00d2ff4`

## callees

- `0x1c0014760`
- `0x1c0024b68`
- `0x1c002bca4`
- `0x1c0068960`
- `0x1c006a644`
- `0x1c006a684`
- `0x1c006ac80`
- `0x1c00d2790`
- `0x1c00da1e4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1c00d295b`
- `ntoskrnl!KeInitializeEvent` at `0x1c00d295b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c00d2bda`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c00d2bda`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00d2b11`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00d2bfc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00d2b11`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00d2bfc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00d2bad`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00d2c37`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00d2d55`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00d2bad`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00d2c37`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00d2d55`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d29a8`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d2cda`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d29a8`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d2cda`

## pseudocode

```c

```
