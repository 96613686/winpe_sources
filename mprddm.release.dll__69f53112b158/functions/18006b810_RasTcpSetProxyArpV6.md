# RasTcpSetProxyArpV6

- ea: `0x18006b810`
- end: `0x18006bcea`
- name: `RasTcpSetProxyArpV6`
- size: `1242`
- prototype: `void __fastcall(struct in6_addr *Addr, unsigned int, __int64, NET_IF_COMPARTMENT_ID, SOCKET *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004f8c4`

## callees

- `0x18006b0a4`
- `0x18006b13c`
- `0x18006b810`
- `0x18006c3c4`
- `0x1800755b8`
- `0x180079774`
- `0x18007f074`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringA` at `0x18006b90c`
- `ntdll!RtlIpv6AddressToStringA` at `0x18006bbc1`
- `ntdll!RtlIpv6AddressToStringA` at `0x18006b90c`
- `ntdll!RtlIpv6AddressToStringA` at `0x18006bbc1`
- `WS2_32!__imp_setsockopt` at `0x18006bbff`
- `WS2_32!__imp_setsockopt` at `0x18006bbff`
- `WS2_32!__imp_WSAGetLastError` at `0x18006bc0f`
- `WS2_32!__imp_WSAGetLastError` at `0x18006bc0f`
- `IPHLPAPI!FreeMibTable` at `0x18006bcb3`
- `IPHLPAPI!FreeMibTable` at `0x18006bcb3`

## pseudocode

```c

```
