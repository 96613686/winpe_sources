# KsAcquireDeviceSecurityLock

- ea: `0x180037800`
- end: `0x18003784d`
- name: `KsAcquireDeviceSecurityLock`
- size: `77`
- prototype: `void __stdcall(KSDEVICE_HEADER Header, BOOLEAN Exclusive)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180037800`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180037810`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180037810`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180037827`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180037827`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180037835`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180037835`

## pseudocode

```c

```
