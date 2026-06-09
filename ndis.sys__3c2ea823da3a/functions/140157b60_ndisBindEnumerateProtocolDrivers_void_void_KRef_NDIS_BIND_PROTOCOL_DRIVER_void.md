# ndisBindEnumerateProtocolDrivers(void (*)(void *,KRef<NDIS_BIND_PROTOCOL_DRIVER>),void *)

- ea: `0x140157b60`
- end: `0x140157cfa`
- name: `?ndisBindEnumerateProtocolDrivers@@YAXP6AXPEAXV?$KRef@UNDIS_BIND_PROTOCOL_DRIVER@@@@@Z0@Z`
- size: `410`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140146280`
- `0x1401462f0`
- `0x140159200`
- `0x14015dc40`

## callees

- `0x1400e6240`
- `0x140157b60`
- `0x140157d00`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140157be3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140157ca4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140157cd6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140157be3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140157ca4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140157cd6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140157b7b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140157c08`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140157b7b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140157c08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157c7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157c7d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140157b8c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140157c19`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140157b8c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140157c19`
- `ntoskrnl!ExReleasePushLockEx` at `0x140157bd7`
- `ntoskrnl!ExReleasePushLockEx` at `0x140157c98`
- `ntoskrnl!ExReleasePushLockEx` at `0x140157cca`
- `ntoskrnl!ExReleasePushLockEx` at `0x140157bd7`
- `ntoskrnl!ExReleasePushLockEx` at `0x140157c98`
- `ntoskrnl!ExReleasePushLockEx` at `0x140157cca`

## pseudocode

```c

```
