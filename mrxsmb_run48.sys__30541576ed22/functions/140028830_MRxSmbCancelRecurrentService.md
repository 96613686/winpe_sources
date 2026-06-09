# MRxSmbCancelRecurrentService

- ea: `0x140028830`
- end: `0x1400288bd`
- name: `MRxSmbCancelRecurrentService`
- size: `141`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140014030`
- `0x140014400`

## callees

- `0x140028830`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028844`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028844`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002887f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002887f`
- `rdbss!RxCancelPreAllocatedTimerRequest` at `0x1400288a2`
- `rdbss!RxCancelPreAllocatedTimerRequest` at `0x1400288a2`

## pseudocode

```c

```
