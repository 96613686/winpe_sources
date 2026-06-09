# RtlAcquireReadLock

- ea: `0x140034bb0`
- end: `0x140034c31`
- name: `RtlAcquireReadLock`
- size: `129`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140023a40`
- `0x1400348f0`
- `0x140034ad0`
- `0x140034b40`
- `0x14005cce0`
- `0x1400605c8`
- `0x140060664`
- `0x1400741a0`

## callees

- `0x140034bb0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140034bc2`
- `ntoskrnl!KfRaiseIrql` at `0x140034bc2`
- `ntoskrnl!KeTestSpinLock` at `0x140034be6`
- `ntoskrnl!KeTestSpinLock` at `0x140034be6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140034c0e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140034c0e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140034c23`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140034c23`

## pseudocode

```c

```
