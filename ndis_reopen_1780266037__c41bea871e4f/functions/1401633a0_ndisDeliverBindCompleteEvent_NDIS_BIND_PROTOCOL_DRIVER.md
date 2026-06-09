# ndisDeliverBindCompleteEvent(NDIS_BIND_PROTOCOL_DRIVER *)

- ea: `0x1401633a0`
- end: `0x14016347e`
- name: `?ndisDeliverBindCompleteEvent@@YAXPEAUNDIS_BIND_PROTOCOL_DRIVER@@@Z`
- size: `222`
- prototype: `void __fastcall(struct NDIS_BIND_PROTOCOL_DRIVER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1401632f0`

## callees

- `0x14005eaa0`
- `0x14005f7e0`
- `0x1401633a0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140163403`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140163452`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140163403`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140163452`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401633b8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401633b8`
- `ntoskrnl!ExQueueWorkItem` at `0x140163429`
- `ntoskrnl!ExQueueWorkItem` at `0x140163429`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401633c9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401633c9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401633f7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140163446`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401633f7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140163446`

## pseudocode

```c

```
