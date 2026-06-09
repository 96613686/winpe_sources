# Dot11FreeRecvPacket(_NET_BUFFER_LIST * *)

- ea: `0x1400137a0`
- end: `0x140013827`
- name: `?Dot11FreeRecvPacket@@YAXPEAPEAU_NET_BUFFER_LIST@@@Z`
- size: `135`
- prototype: `void __fastcall(struct _NET_BUFFER_LIST **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000f440`
- `0x140031f60`

## callees

- `0x1400137a0`
- `0x140013b90`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400137e8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400137e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400137f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400137f9`
- `NDIS!NdisFreeNetBufferList` at `0x140013808`
- `NDIS!NdisFreeNetBufferList` at `0x140013808`

## pseudocode

```c

```
