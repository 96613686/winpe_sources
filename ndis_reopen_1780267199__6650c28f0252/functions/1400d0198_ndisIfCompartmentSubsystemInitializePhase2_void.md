# ndisIfCompartmentSubsystemInitializePhase2(void)

- ea: `0x1400d0198`
- end: `0x1400d064c`
- name: `?ndisIfCompartmentSubsystemInitializePhase2@@YAJXZ`
- size: `1204`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14014f1e0`

## callees

- `0x14001cf60`
- `0x14002ab60`
- `0x140054a80`
- `0x1400d0198`
- `0x1400d0c88`
- `0x1400eb380`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0375`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d05de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0375`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d05de`
- `ntoskrnl!ExAllocatePool2` at `0x1400d03d1`
- `ntoskrnl!ExAllocatePool2` at `0x1400d03d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d05a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d05a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d0572`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d0572`
- `NETIO!NsiSetAllParametersEx` at `0x1400d0355`
- `NETIO!NsiSetAllParametersEx` at `0x1400d0547`
- `NETIO!NsiSetAllParametersEx` at `0x1400d0355`
- `NETIO!NsiSetAllParametersEx` at `0x1400d0547`
- `NETIO!NsiEnumerateObjectsAllParametersEx` at `0x1400d0282`
- `NETIO!NsiEnumerateObjectsAllParametersEx` at `0x1400d0403`
- `NETIO!NsiEnumerateObjectsAllParametersEx` at `0x1400d0282`
- `NETIO!NsiEnumerateObjectsAllParametersEx` at `0x1400d0403`

## string_xrefs

- `0x1400d0321`: `Default Compartment`
- `0x1400d04be`: `Default Compartment`

## pseudocode

```c

```
