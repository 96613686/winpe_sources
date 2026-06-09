# TeredoUPnP::GetInterfaceGuidForIpAddress(in_addr const *,_GUID *)

- ea: `0x180028fc0`
- end: `0x1800291e6`
- name: `?GetInterfaceGuidForIpAddress@TeredoUPnP@@AEAAJPEBUin_addr@@PEAU_GUID@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(TeredoUPnP *__hidden this, const struct in_addr *, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180028644`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x180012dcc`
- `0x1800190f0`
- `0x180028fc0`
- `0x18004b5f0`
- `0x18004c134`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002918f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002918f`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18002913c`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18002913c`
- `IPHLPAPI!GetIpAddrTable` at `0x180029003`
- `IPHLPAPI!GetIpAddrTable` at `0x180029048`
- `IPHLPAPI!GetIpAddrTable` at `0x180029003`
- `IPHLPAPI!GetIpAddrTable` at `0x180029048`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800290c4`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800290c4`
- `WS2_32!__imp_inet_ntoa` at `0x1800290e2`
- `WS2_32!__imp_inet_ntoa` at `0x18002910d`
- `WS2_32!__imp_inet_ntoa` at `0x1800290e2`
- `WS2_32!__imp_inet_ntoa` at `0x18002910d`

## string_xrefs

- `0x1800291aa`: `Failed to copy GUID 0x%x`

## pseudocode

```c

```
