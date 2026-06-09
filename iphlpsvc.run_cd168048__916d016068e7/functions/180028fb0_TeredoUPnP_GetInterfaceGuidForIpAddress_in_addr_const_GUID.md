# TeredoUPnP::GetInterfaceGuidForIpAddress(in_addr const *,_GUID *)

- ea: `0x180028fb0`
- end: `0x1800291d6`
- name: `?GetInterfaceGuidForIpAddress@TeredoUPnP@@AEAAJPEBUin_addr@@PEAU_GUID@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(TeredoUPnP *__hidden this, const struct in_addr *, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180028634`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x180012dbc`
- `0x1800190e0`
- `0x180028fb0`
- `0x18004b630`
- `0x18004c174`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002917f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002917f`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18002912c`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18002912c`
- `IPHLPAPI!GetIpAddrTable` at `0x180028ff3`
- `IPHLPAPI!GetIpAddrTable` at `0x180029038`
- `IPHLPAPI!GetIpAddrTable` at `0x180028ff3`
- `IPHLPAPI!GetIpAddrTable` at `0x180029038`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800290b4`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800290b4`
- `WS2_32!__imp_inet_ntoa` at `0x1800290d2`
- `WS2_32!__imp_inet_ntoa` at `0x1800290fd`
- `WS2_32!__imp_inet_ntoa` at `0x1800290d2`
- `WS2_32!__imp_inet_ntoa` at `0x1800290fd`

## string_xrefs

- `0x18002919a`: `Failed to copy GUID 0x%x`

## pseudocode

```c

```
