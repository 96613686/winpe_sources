# MRxSmbShutdownRecurrentService

- ea: `0x14003cd50`
- end: `0x14003cddd`
- name: `MRxSmbShutdownRecurrentService`
- size: `141`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400823ac`

## callees

- `0x14003cd50`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003cd64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003cd64`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cd9f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cd9f`
- `rdbss!RxCancelPreAllocatedTimerRequest` at `0x14003cdc2`
- `rdbss!RxCancelPreAllocatedTimerRequest` at `0x14003cdc2`

## pseudocode

```c

```
