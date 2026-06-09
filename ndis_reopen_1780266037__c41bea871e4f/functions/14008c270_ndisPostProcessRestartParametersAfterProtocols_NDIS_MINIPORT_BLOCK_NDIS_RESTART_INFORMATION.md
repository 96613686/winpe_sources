# ndisPostProcessRestartParametersAfterProtocols(_NDIS_MINIPORT_BLOCK *,NDIS_RESTART_INFORMATION *)

- ea: `0x14008c270`
- end: `0x14008c3a6`
- name: `?ndisPostProcessRestartParametersAfterProtocols@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAUNDIS_RESTART_INFORMATION@@@Z`
- size: `310`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct NDIS_RESTART_INFORMATION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14015eda0`

## callees

- `0x140009320`
- `0x140009370`
- `0x1400110b0`
- `0x140088a2c`
- `0x14008c270`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14008c329`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14008c329`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c29f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c2c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c29f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c2c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008c311`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008c38e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008c311`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008c38e`

## pseudocode

```c

```
