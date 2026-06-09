# PeerTimerDeinit(_PEER_TIMER *)

- ea: `0x140079240`
- end: `0x14007930f`
- name: `?PeerTimerDeinit@@YAXPEAU_PEER_TIMER@@@Z`
- size: `207`
- prototype: `void __fastcall(struct _PEER_TIMER *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140078160`
- `0x140079318`

## callees

- `0x14000d21c`
- `0x140079240`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400792c0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400792c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400792d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400792d1`
- `NDIS!NdisFreeTimerObject` at `0x14007929e`
- `NDIS!NdisFreeTimerObject` at `0x14007929e`
- `NDIS!NdisCancelTimerObject` at `0x14007928f`
- `NDIS!NdisCancelTimerObject` at `0x14007928f`

## pseudocode

```c

```
