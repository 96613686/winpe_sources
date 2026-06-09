# CD_ROLLBACK::Dot11IndicateRecvPackets(_VELAN *)

- ea: `0x140030420`
- end: `0x1400304b7`
- name: `?Dot11IndicateRecvPackets@CD_ROLLBACK@@YAXPEAU_VELAN@@@Z`
- size: `151`
- prototype: `void __fastcall(CD_ROLLBACK *__hidden this, struct _VELAN *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140030420`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14003049f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003049f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030437`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030437`
- `NDIS!NdisFIndicateReceiveNetBufferLists` at `0x140030486`
- `NDIS!NdisFIndicateReceiveNetBufferLists` at `0x140030486`

## pseudocode

```c

```
