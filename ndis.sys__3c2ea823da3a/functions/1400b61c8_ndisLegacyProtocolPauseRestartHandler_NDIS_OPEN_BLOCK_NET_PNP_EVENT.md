# ndisLegacyProtocolPauseRestartHandler(_NDIS_OPEN_BLOCK *,_NET_PNP_EVENT *)

- ea: `0x1400b61c8`
- end: `0x1400b6319`
- name: `?ndisLegacyProtocolPauseRestartHandler@@YAXPEAU_NDIS_OPEN_BLOCK@@PEAU_NET_PNP_EVENT@@@Z`
- size: `337`
- prototype: `void __fastcall(struct _NDIS_OPEN_BLOCK *, struct _NET_PNP_EVENT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140175e50`

## callees

- `0x14001d350`
- `0x14004f200`
- `0x1400b61c8`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x1400b62a5`
- `ntoskrnl!KeClearEvent` at `0x1400b62a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b625b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b62ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b625b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b62ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b623a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b6273`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b623a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b6273`

## pseudocode

```c

```
