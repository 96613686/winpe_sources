# MRxSmbActivateRecurrentService

- ea: `0x14003cc80`
- end: `0x14003cd48`
- name: `MRxSmbActivateRecurrentService`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140026464`
- `0x1400822b0`

## callees

- `0x14003cc80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003cc94`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003cc94`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cd30`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cd30`
- `rdbss!RxPostPreAllocatedOneShotTimerRequest` at `0x14003cd11`
- `rdbss!RxPostPreAllocatedOneShotTimerRequest` at `0x14003cd11`

## pseudocode

```c

```
