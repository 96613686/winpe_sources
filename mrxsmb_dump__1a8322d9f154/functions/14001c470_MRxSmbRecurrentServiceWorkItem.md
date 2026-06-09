# MRxSmbRecurrentServiceWorkItem

- ea: `0x14001c470`
- end: `0x14001c5e9`
- name: `MRxSmbRecurrentServiceWorkItem`
- size: `377`
- prototype: `void __stdcall(PVOID Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x14001c470`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c47d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c4e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c47d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c4e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c4c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c55f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c58f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c4c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c55f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c58f`
- `rdbss!RxPostPreAllocatedOneShotTimerRequest` at `0x14001c539`
- `rdbss!RxPostPreAllocatedOneShotTimerRequest` at `0x14001c539`

## pseudocode

```c

```
