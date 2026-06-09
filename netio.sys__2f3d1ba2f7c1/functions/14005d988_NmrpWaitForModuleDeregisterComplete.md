# NmrpWaitForModuleDeregisterComplete

- ea: `0x14005d988`
- end: `0x14005da25`
- name: `NmrpWaitForModuleDeregisterComplete`
- size: `157`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14005d4e0`
- `0x14005d510`

## callees

- `0x14002cfe8`
- `0x14005d988`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14005d9ff`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005d9ff`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d9ac`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d9ac`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d9c3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d9d6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d9c3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d9d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005da10`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005da10`

## pseudocode

```c

```
