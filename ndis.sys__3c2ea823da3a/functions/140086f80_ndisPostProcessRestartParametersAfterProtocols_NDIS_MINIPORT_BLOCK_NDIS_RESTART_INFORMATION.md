# ndisPostProcessRestartParametersAfterProtocols(_NDIS_MINIPORT_BLOCK *,NDIS_RESTART_INFORMATION *)

- ea: `0x140086f80`
- end: `0x1400870b6`
- name: `?ndisPostProcessRestartParametersAfterProtocols@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAUNDIS_RESTART_INFORMATION@@@Z`
- size: `310`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct NDIS_RESTART_INFORMATION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140157e00`

## callees

- `0x140015280`
- `0x1400152d0`
- `0x14001cf50`
- `0x1400837ac`
- `0x140086f80`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x140087039`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140087039`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086faf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086fd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086faf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086fd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087021`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008709e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087021`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008709e`

## pseudocode

```c

```
