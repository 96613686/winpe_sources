# Dot11PacketConverterSendPacket(_VELAN *,_NET_BUFFER_LIST *,uchar *,ushort)

- ea: `0x14000e25c`
- end: `0x14000e63d`
- name: `?Dot11PacketConverterSendPacket@@YAHPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@PEAEG@Z`
- size: `993`
- prototype: `int(struct _VELAN *, struct _NET_BUFFER_LIST *, unsigned __int8 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000d77c`

## callees

- `0x14000e25c`
- `0x140010510`
- `0x140057340`
- `0x14009bbb0`
- `0x14009bbf0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000e437`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000e437`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x14000e3d5`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x14000e3d5`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x14000e3ff`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x14000e5ac`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x14000e3ff`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x14000e5ac`

## pseudocode

```c

```
