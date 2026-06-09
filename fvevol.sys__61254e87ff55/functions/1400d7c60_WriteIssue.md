# WriteIssue

- ea: `0x1400d7c60`
- end: `0x1400d7dbc`
- name: `WriteIssue`
- size: `348`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400bd590`
- `0x1400d7370`

## callees

- `0x1400d7c60`
- `0x1400d7dc4`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x1400d7d59`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400d7d59`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d7d03`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d7d3b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d7d03`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d7d3b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d7ca5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d7d13`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d7ca5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d7d13`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7d8c`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7daf`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7d8c`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7daf`

## pseudocode

```c

```
