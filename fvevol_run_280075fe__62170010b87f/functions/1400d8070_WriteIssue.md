# WriteIssue

- ea: `0x1400d8070`
- end: `0x1400d81cc`
- name: `WriteIssue`
- size: `348`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400d7774`

## callees

- `0x1400d8070`
- `0x1400d81d4`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x1400d8169`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400d8169`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d8113`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d814b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d8113`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d814b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d80b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d8123`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d80b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d8123`
- `ntoskrnl!KeBugCheckEx` at `0x1400d819c`
- `ntoskrnl!KeBugCheckEx` at `0x1400d81bf`
- `ntoskrnl!KeBugCheckEx` at `0x1400d819c`
- `ntoskrnl!KeBugCheckEx` at `0x1400d81bf`

## pseudocode

```c

```
