# NdisAcquireReadWriteLock

- ea: `0x140046f20`
- end: `0x14004714f`
- name: `NdisAcquireReadWriteLock`
- size: `559`
- prototype: `void __stdcall(PNDIS_RW_LOCK Lock, BOOLEAN fWrite, PLOCK_STATE LockState)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140046f20`
- `0x1400473c0`
- `0x140047460`
- `0x14004b5b0`
- `0x1400c6548`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140046f3b`
- `ntoskrnl!KfRaiseIrql` at `0x140047082`
- `ntoskrnl!KfRaiseIrql` at `0x140046f3b`
- `ntoskrnl!KfRaiseIrql` at `0x140047082`
- `ntoskrnl!KeTestSpinLock` at `0x140046f76`
- `ntoskrnl!KeTestSpinLock` at `0x140046f76`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140046fc7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140046fc7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400470dc`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400470dc`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400470ed`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400470ed`
- `HAL!KeStallExecutionProcessor` at `0x14004706a`
- `HAL!KeStallExecutionProcessor` at `0x14004706a`

## pseudocode

```c

```
