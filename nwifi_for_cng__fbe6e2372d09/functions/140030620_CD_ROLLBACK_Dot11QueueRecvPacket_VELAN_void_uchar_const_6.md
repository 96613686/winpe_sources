# CD_ROLLBACK::Dot11QueueRecvPacket(_VELAN *,void *,uchar const (*)[6])

- ea: `0x140030620`
- end: `0x14003073b`
- name: `?Dot11QueueRecvPacket@CD_ROLLBACK@@YAXPEAU_VELAN@@PEAXPEAY05$$CBE@Z`
- size: `283`
- prototype: `void __fastcall(CD_ROLLBACK *__hidden this, struct _VELAN *, void *, const unsigned __int8 (*)[6])`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140030620`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140030724`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030724`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003063d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003063d`
- `NDIS!NdisFIndicateReceiveNetBufferLists` at `0x140030688`
- `NDIS!NdisFIndicateReceiveNetBufferLists` at `0x140030688`

## pseudocode

```c

```
