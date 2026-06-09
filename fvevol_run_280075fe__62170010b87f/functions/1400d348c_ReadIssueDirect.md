# ReadIssueDirect

- ea: `0x1400d348c`
- end: `0x1400d3643`
- name: `ReadIssueDirect`
- size: `439`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400cdd10`
- `0x1400d3820`
- `0x1400d6d48`

## callees

- `0x14002c140`
- `0x14009c22c`
- `0x1400d348c`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400d3580`
- `ntoskrnl!IofCallDriver` at `0x1400d3580`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d3554`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d3554`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d3500`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d3500`
- `ntoskrnl!KeBugCheckEx` at `0x1400d35b5`
- `ntoskrnl!KeBugCheckEx` at `0x1400d35b5`

## pseudocode

```c

```
