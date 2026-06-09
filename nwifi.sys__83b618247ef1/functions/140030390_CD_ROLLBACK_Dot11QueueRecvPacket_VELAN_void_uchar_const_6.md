# CD_ROLLBACK::Dot11QueueRecvPacket(_VELAN *,void *,uchar const (*)[6])

- ea: `0x140030390`
- end: `0x1400304ab`
- name: `?Dot11QueueRecvPacket@CD_ROLLBACK@@YAXPEAU_VELAN@@PEAXPEAY05$$CBE@Z`
- size: `283`
- prototype: `void __fastcall(CD_ROLLBACK *__hidden this, struct _VELAN *, void *, const unsigned __int8 (*)[6])`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140030390`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140030494`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030494`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400303ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400303ad`
- `NDIS!NdisFIndicateReceiveNetBufferLists` at `0x1400303f8`
- `NDIS!NdisFIndicateReceiveNetBufferLists` at `0x1400303f8`

## pseudocode

```c

```
