# PeerTimerDeinit(_PEER_TIMER *)

- ea: `0x140077a10`
- end: `0x140077adf`
- name: `?PeerTimerDeinit@@YAXPEAU_PEER_TIMER@@@Z`
- size: `207`
- prototype: `void __fastcall(struct _PEER_TIMER *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140076930`
- `0x140077ae8`

## callees

- `0x14000d22c`
- `0x140077a10`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140077a90`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140077a90`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077aa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077aa1`
- `NDIS!NdisFreeTimerObject` at `0x140077a6e`
- `NDIS!NdisFreeTimerObject` at `0x140077a6e`
- `NDIS!NdisCancelTimerObject` at `0x140077a5f`
- `NDIS!NdisCancelTimerObject` at `0x140077a5f`

## pseudocode

```c

```
