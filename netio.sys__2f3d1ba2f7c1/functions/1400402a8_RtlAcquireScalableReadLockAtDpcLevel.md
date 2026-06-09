# RtlAcquireScalableReadLockAtDpcLevel

- ea: `0x1400402a8`
- end: `0x140040320`
- name: `RtlAcquireScalableReadLockAtDpcLevel`
- size: `120`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14003ffa8`
- `0x140040194`

## callees

- `0x1400402a8`

## import_xrefs

- `ntoskrnl!KeTestSpinLock` at `0x1400402d7`
- `ntoskrnl!KeTestSpinLock` at `0x1400402d7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400402f3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400402f3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140040308`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140040308`

## pseudocode

```c

```
