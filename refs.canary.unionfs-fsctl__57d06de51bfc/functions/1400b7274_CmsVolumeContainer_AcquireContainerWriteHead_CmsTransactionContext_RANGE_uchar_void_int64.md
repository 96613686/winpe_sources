# CmsVolumeContainer::AcquireContainerWriteHead(CmsTransactionContext *,_RANGE,uchar,void * *,__int64 *)

- ea: `0x1400b7274`
- end: `0x1400b7856`
- name: `?AcquireContainerWriteHead@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@U_RANGE@@EPEAPEAXPEA_J@Z`
- size: `1506`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1400b7274`
- `0x1400cb9d0`
- `0x140132c18`

## callees

- `0x140045910`
- `0x140046220`
- `0x14008e900`
- `0x1400b7274`
- `0x1400cae64`
- `0x1400f79e4`
- `0x140136560`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b75b3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b76a1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b75b3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b76a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b7652`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b76dd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b780b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b7652`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b76dd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b780b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b767b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b767b`
- `ntoskrnl!KeInitializeEvent` at `0x1400b7402`
- `ntoskrnl!KeInitializeEvent` at `0x1400b7402`
- `HAL!KeQueryPerformanceCounter` at `0x1400b7431`
- `HAL!KeQueryPerformanceCounter` at `0x1400b7796`
- `HAL!KeQueryPerformanceCounter` at `0x1400b7431`
- `HAL!KeQueryPerformanceCounter` at `0x1400b7796`

## pseudocode

```c

```
