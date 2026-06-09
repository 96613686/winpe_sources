# WriteIssueDirect

- ea: `0x1400d7dc4`
- end: `0x1400d8168`
- name: `WriteIssueDirect`
- size: `932`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1400d5620`
- `0x1400d7370`
- `0x1400d7c60`

## callees

- `0x14002d140`
- `0x14009e22c`
- `0x1400d66b0`
- `0x1400d7dc4`
- `0x1400edab0`
- `0x1400ef008`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400d7f85`
- `ntoskrnl!IofCallDriver` at `0x1400d7f85`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400d7e75`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400d7e75`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400d7e8a`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400d7e8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d7efc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d7efc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d7ea4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d7ea4`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7fbc`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7fbc`

## pseudocode

```c

```
