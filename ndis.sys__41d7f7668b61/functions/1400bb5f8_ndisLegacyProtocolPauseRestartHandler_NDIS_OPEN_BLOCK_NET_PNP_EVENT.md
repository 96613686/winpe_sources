# ndisLegacyProtocolPauseRestartHandler(_NDIS_OPEN_BLOCK *,_NET_PNP_EVENT *)

- ea: `0x1400bb5f8`
- end: `0x1400bb749`
- name: `?ndisLegacyProtocolPauseRestartHandler@@YAXPEAU_NDIS_OPEN_BLOCK@@PEAU_NET_PNP_EVENT@@@Z`
- size: `337`
- prototype: `void __fastcall(struct _NDIS_OPEN_BLOCK *, struct _NET_PNP_EVENT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14017be20`

## callees

- `0x1400114b0`
- `0x1400548f0`
- `0x1400bb5f8`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x1400bb6d5`
- `ntoskrnl!KeClearEvent` at `0x1400bb6d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bb68b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bb6ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bb68b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bb6ea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bb66a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bb6a3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bb66a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bb6a3`

## pseudocode

```c

```
