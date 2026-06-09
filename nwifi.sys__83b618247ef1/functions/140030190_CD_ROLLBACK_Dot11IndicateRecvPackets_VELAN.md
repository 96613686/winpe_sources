# CD_ROLLBACK::Dot11IndicateRecvPackets(_VELAN *)

- ea: `0x140030190`
- end: `0x140030227`
- name: `?Dot11IndicateRecvPackets@CD_ROLLBACK@@YAXPEAU_VELAN@@@Z`
- size: `151`
- prototype: `void __fastcall(CD_ROLLBACK *__hidden this, struct _VELAN *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140030190`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14003020f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003020f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400301a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400301a7`
- `NDIS!NdisFIndicateReceiveNetBufferLists` at `0x1400301f6`
- `NDIS!NdisFIndicateReceiveNetBufferLists` at `0x1400301f6`

## pseudocode

```c

```
