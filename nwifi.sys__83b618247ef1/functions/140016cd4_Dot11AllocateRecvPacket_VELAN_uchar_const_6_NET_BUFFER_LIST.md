# Dot11AllocateRecvPacket(_VELAN *,uchar const (*)[6],_NET_BUFFER_LIST * *)

- ea: `0x140016cd4`
- end: `0x140016df2`
- name: `?Dot11AllocateRecvPacket@@YAHPEAU_VELAN@@PEAY05$$CBEPEAPEAU_NET_BUFFER_LIST@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(struct _VELAN *, const unsigned __int8 (*)[6], struct _NET_BUFFER_LIST **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140031ce8`

## callees

- `0x140016cd4`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140016d25`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140016d25`
- `NDIS!NdisAllocateNetBufferList` at `0x140016cf5`
- `NDIS!NdisAllocateNetBufferList` at `0x140016cf5`
- `NDIS!NdisFreeNetBufferList` at `0x140016d3e`
- `NDIS!NdisFreeNetBufferList` at `0x140016d3e`

## pseudocode

```c

```
