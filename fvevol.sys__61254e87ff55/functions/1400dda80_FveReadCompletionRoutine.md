# FveReadCompletionRoutine

- ea: `0x1400dda80`
- end: `0x1400de03f`
- name: `FveReadCompletionRoutine`
- size: `1471`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400dda30`
- `0x1400ef498`

## callees

- `0x14000b998`
- `0x140022bf0`
- `0x140023040`
- `0x14002a2a0`
- `0x14002d140`
- `0x1400bd078`
- `0x1400d4a70`
- `0x1400d83c0`
- `0x1400d87d0`
- `0x1400dda80`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x1400dddfe`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400dddfe`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400ddf9e`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400ddf9e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ddd38`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400dde1d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ddf5e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ddf78`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ddd38`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400dde1d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ddf5e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ddf78`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ddccc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ddd5f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ddccc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ddd5f`
- `ntoskrnl!MmUnlockPages` at `0x1400ddc3d`
- `ntoskrnl!MmUnlockPages` at `0x1400ddc3d`
- `ntoskrnl!KeBugCheckEx` at `0x1400dde8a`
- `ntoskrnl!KeBugCheckEx` at `0x1400ddeb7`
- `ntoskrnl!KeBugCheckEx` at `0x1400dded9`
- `ntoskrnl!KeBugCheckEx` at `0x1400ddfe8`
- `ntoskrnl!KeBugCheckEx` at `0x1400de010`
- `ntoskrnl!KeBugCheckEx` at `0x1400de032`
- `ntoskrnl!KeBugCheckEx` at `0x1400dde8a`
- `ntoskrnl!KeBugCheckEx` at `0x1400ddeb7`
- `ntoskrnl!KeBugCheckEx` at `0x1400dded9`
- `ntoskrnl!KeBugCheckEx` at `0x1400ddfe8`
- `ntoskrnl!KeBugCheckEx` at `0x1400de010`
- `ntoskrnl!KeBugCheckEx` at `0x1400de032`

## pseudocode

```c

```
