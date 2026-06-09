# AcquireControl

- ea: `0x1400dad50`
- end: `0x1400dae7a`
- name: `AcquireControl`
- size: `298`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400eb300`

## callees

- `0x14002e630`
- `0x1400dad50`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1400dada2`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400dada2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400dad67`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400dad67`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400daded`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400daded`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400dadc0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400dadc0`
- `ntoskrnl!KeBugCheckEx` at `0x1400dae6d`
- `ntoskrnl!KeBugCheckEx` at `0x1400dae6d`

## pseudocode

```c

```
