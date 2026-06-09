# WriteIssueDirect

- ea: `0x1400d81d4`
- end: `0x1400d857e`
- name: `WriteIssueDirect`
- size: `938`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1400cdd10`
- `0x1400d7774`
- `0x1400d8070`

## callees

- `0x14002c140`
- `0x14009c22c`
- `0x1400ced90`
- `0x1400d3a70`
- `0x1400d81d4`
- `0x1400ea008`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400d839b`
- `ntoskrnl!IofCallDriver` at `0x1400d839b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400d8285`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400d8285`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400d829a`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400d829a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d8312`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d8312`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d82b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d82b4`
- `ntoskrnl!KeBugCheckEx` at `0x1400d83d2`
- `ntoskrnl!KeBugCheckEx` at `0x1400d83d2`

## pseudocode

```c

```
