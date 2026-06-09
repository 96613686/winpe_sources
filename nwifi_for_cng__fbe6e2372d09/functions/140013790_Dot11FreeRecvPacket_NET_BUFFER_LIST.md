# Dot11FreeRecvPacket(_NET_BUFFER_LIST * *)

- ea: `0x140013790`
- end: `0x140013817`
- name: `?Dot11FreeRecvPacket@@YAXPEAPEAU_NET_BUFFER_LIST@@@Z`
- size: `135`
- prototype: `void __fastcall(struct _NET_BUFFER_LIST **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000f430`
- `0x140032180`

## callees

- `0x140013790`
- `0x140013b80`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400137d8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400137d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400137e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400137e9`
- `NDIS!NdisFreeNetBufferList` at `0x1400137f8`
- `NDIS!NdisFreeNetBufferList` at `0x1400137f8`

## pseudocode

```c

```
