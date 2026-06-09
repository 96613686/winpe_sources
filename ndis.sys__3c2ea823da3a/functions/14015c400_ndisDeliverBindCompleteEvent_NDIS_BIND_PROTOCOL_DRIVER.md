# ndisDeliverBindCompleteEvent(NDIS_BIND_PROTOCOL_DRIVER *)

- ea: `0x14015c400`
- end: `0x14015c4de`
- name: `?ndisDeliverBindCompleteEvent@@YAXPEAUNDIS_BIND_PROTOCOL_DRIVER@@@Z`
- size: `222`
- prototype: `void __fastcall(struct NDIS_BIND_PROTOCOL_DRIVER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14015c350`

## callees

- `0x14005a5c0`
- `0x14005b1f0`
- `0x14015c400`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015c463`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015c4b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015c463`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015c4b2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015c418`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015c418`
- `ntoskrnl!ExQueueWorkItem` at `0x14015c489`
- `ntoskrnl!ExQueueWorkItem` at `0x14015c489`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14015c429`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14015c429`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14015c457`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14015c4a6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14015c457`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14015c4a6`

## pseudocode

```c

```
