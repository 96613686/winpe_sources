# ndisBindEnumerateProtocolDrivers(void (*)(void *,KRef<NDIS_BIND_PROTOCOL_DRIVER>),void *)

- ea: `0x14015eb00`
- end: `0x14015ec9a`
- name: `?ndisBindEnumerateProtocolDrivers@@YAXP6AXPEAXV?$KRef@UNDIS_BIND_PROTOCOL_DRIVER@@@@@Z0@Z`
- size: `410`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14014d220`
- `0x14014d290`
- `0x1401601a0`
- `0x140164be0`

## callees

- `0x1400eb460`
- `0x14015eb00`
- `0x14015eca0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015eb83`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015ec44`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015ec76`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015eb83`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015ec44`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015ec76`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015eb1b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015eba8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015eb1b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015eba8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015ec1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015ec1d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14015eb2c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14015ebb9`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14015eb2c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14015ebb9`
- `ntoskrnl!ExReleasePushLockEx` at `0x14015eb77`
- `ntoskrnl!ExReleasePushLockEx` at `0x14015ec38`
- `ntoskrnl!ExReleasePushLockEx` at `0x14015ec6a`
- `ntoskrnl!ExReleasePushLockEx` at `0x14015eb77`
- `ntoskrnl!ExReleasePushLockEx` at `0x14015ec38`
- `ntoskrnl!ExReleasePushLockEx` at `0x14015ec6a`

## pseudocode

```c

```
