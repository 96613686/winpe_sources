# AcquireControl

- ea: `0x1400cf640`
- end: `0x1400cf769`
- name: `AcquireControl`
- size: `297`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400cee94`

## callees

- `0x14002d630`
- `0x1400cf640`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1400cf691`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400cf691`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400cf657`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400cf657`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cf6dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cf6dc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cf6af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cf6af`
- `ntoskrnl!KeBugCheckEx` at `0x1400cf75c`
- `ntoskrnl!KeBugCheckEx` at `0x1400cf75c`

## pseudocode

```c

```
