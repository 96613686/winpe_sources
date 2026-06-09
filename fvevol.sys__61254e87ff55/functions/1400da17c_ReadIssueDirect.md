# ReadIssueDirect

- ea: `0x1400da17c`
- end: `0x1400da333`
- name: `ReadIssueDirect`
- size: `439`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400d55d0`
- `0x1400d5620`
- `0x1400d6968`
- `0x1400d8588`

## callees

- `0x14002d140`
- `0x14009e22c`
- `0x1400da17c`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400da270`
- `ntoskrnl!IofCallDriver` at `0x1400da270`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400da244`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400da244`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400da1f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400da1f0`
- `ntoskrnl!KeBugCheckEx` at `0x1400da2a5`
- `ntoskrnl!KeBugCheckEx` at `0x1400da2a5`

## pseudocode

```c

```
