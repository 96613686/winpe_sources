# ndisIfCompartmentSubsystemInitializePhase2(void)

- ea: `0x1400cafe8`
- end: `0x1400cb49c`
- name: `?ndisIfCompartmentSubsystemInitializePhase2@@YAJXZ`
- size: `1204`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140148240`

## callees

- `0x140028e00`
- `0x140029620`
- `0x14004f390`
- `0x1400cafe8`
- `0x1400cbad8`
- `0x1400e6160`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb1c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb42e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb1c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb42e`
- `ntoskrnl!ExAllocatePool2` at `0x1400cb221`
- `ntoskrnl!ExAllocatePool2` at `0x1400cb221`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cb3f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cb3f8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cb3c2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cb3c2`
- `NETIO!NsiSetAllParametersEx` at `0x1400cb1a5`
- `NETIO!NsiSetAllParametersEx` at `0x1400cb397`
- `NETIO!NsiSetAllParametersEx` at `0x1400cb1a5`
- `NETIO!NsiSetAllParametersEx` at `0x1400cb397`
- `NETIO!NsiEnumerateObjectsAllParametersEx` at `0x1400cb0d2`
- `NETIO!NsiEnumerateObjectsAllParametersEx` at `0x1400cb253`
- `NETIO!NsiEnumerateObjectsAllParametersEx` at `0x1400cb0d2`
- `NETIO!NsiEnumerateObjectsAllParametersEx` at `0x1400cb253`

## string_xrefs

- `0x1400cb171`: `Default Compartment`
- `0x1400cb30e`: `Default Compartment`

## pseudocode

```c

```
