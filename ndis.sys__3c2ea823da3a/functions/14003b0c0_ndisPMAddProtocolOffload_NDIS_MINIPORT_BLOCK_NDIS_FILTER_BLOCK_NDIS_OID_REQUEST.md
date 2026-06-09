# ndisPMAddProtocolOffload(_NDIS_MINIPORT_BLOCK *,_NDIS_FILTER_BLOCK *,_NDIS_OID_REQUEST *)

- ea: `0x14003b0c0`
- end: `0x14003b508`
- name: `?ndisPMAddProtocolOffload@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_FILTER_BLOCK@@PEAU_NDIS_OID_REQUEST@@@Z`
- size: `1096`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_FILTER_BLOCK *, struct _NDIS_OID_REQUEST *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14001acc0`

## callees

- `0x140015280`
- `0x1400283f0`
- `0x140028e00`
- `0x14002b150`
- `0x14002b980`
- `0x14003aa00`
- `0x14003b0c0`
- `0x14003c960`
- `0x1400857b0`
- `0x1400b0bb0`
- `0x1400e6160`
- `0x1400e65c0`
- `0x1401564e0`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14003b1dc`
- `ntoskrnl!KeReleaseSemaphore` at `0x14003b1dc`
- `ntoskrnl!EtwActivityIdControl` at `0x14003b29c`
- `ntoskrnl!EtwActivityIdControl` at `0x14003b33b`
- `ntoskrnl!EtwActivityIdControl` at `0x14003b29c`
- `ntoskrnl!EtwActivityIdControl` at `0x14003b33b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b3aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b4ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b3aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b4ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003b43b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003b43b`

## pseudocode

```c

```
