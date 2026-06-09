# ndisPMAddProtocolOffload(_NDIS_MINIPORT_BLOCK *,_NDIS_FILTER_BLOCK *,_NDIS_OID_REQUEST *)

- ea: `0x140064e60`
- end: `0x1400652a8`
- name: `?ndisPMAddProtocolOffload@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_FILTER_BLOCK@@PEAU_NDIS_OID_REQUEST@@@Z`
- size: `1096`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_FILTER_BLOCK *, struct _NDIS_OID_REQUEST *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14000ed60`

## callees

- `0x140009320`
- `0x14001c550`
- `0x14001cf60`
- `0x14001f200`
- `0x14001fa30`
- `0x14003f110`
- `0x140064e60`
- `0x1400652b0`
- `0x14008aa30`
- `0x1400b5fe0`
- `0x1400eb380`
- `0x1400eb7c0`
- `0x14015d480`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x140064f7c`
- `ntoskrnl!KeReleaseSemaphore` at `0x140064f7c`
- `ntoskrnl!EtwActivityIdControl` at `0x14006503c`
- `ntoskrnl!EtwActivityIdControl` at `0x1400650db`
- `ntoskrnl!EtwActivityIdControl` at `0x14006503c`
- `ntoskrnl!EtwActivityIdControl` at `0x1400650db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006514a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006524e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006514a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006524e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400651db`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400651db`

## pseudocode

```c

```
