# KsAcquireDeviceSecurityLock

- ea: `0x180037910`
- end: `0x18003795d`
- name: `KsAcquireDeviceSecurityLock`
- size: `77`
- prototype: `void __stdcall(KSDEVICE_HEADER Header, BOOLEAN Exclusive)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180037910`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180037920`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180037920`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180037937`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180037937`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180037945`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180037945`

## pseudocode

```c

```
