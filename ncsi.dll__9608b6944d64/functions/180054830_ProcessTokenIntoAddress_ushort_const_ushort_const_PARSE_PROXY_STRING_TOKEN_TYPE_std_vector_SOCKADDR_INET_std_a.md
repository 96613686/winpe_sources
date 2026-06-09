# ProcessTokenIntoAddress(ushort const *,ushort const *,PARSE_PROXY_STRING_TOKEN_TYPE,std::vector<_SOCKADDR_INET,std::allocator<_SOCKADDR_INET>> &)

- ea: `0x180054830`
- end: `0x180054be3`
- name: `?ProcessTokenIntoAddress@@YAXPEBG0W4PARSE_PROXY_STRING_TOKEN_TYPE@@AEAV?$vector@T_SOCKADDR_INET@@V?$allocator@T_SOCKADDR_INET@@@std@@@std@@@Z`
- size: `947`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1800544a4`
- `0x180054658`

## callees

- `0x18000e59c`
- `0x18000eea0`
- `0x180011a58`
- `0x18002283c`
- `0x1800255f4`
- `0x180047240`
- `0x180047f78`
- `0x1800533a4`
- `0x18005386c`
- `0x180053a4c`
- `0x180053a98`
- `0x180054830`

## import_xrefs

- `ntdll!RtlIpv4StringToAddressW` at `0x180054b45`
- `ntdll!RtlIpv4StringToAddressW` at `0x180054b45`
- `ntdll!RtlIpv6StringToAddressW` at `0x180054b67`
- `ntdll!RtlIpv6StringToAddressW` at `0x180054b67`
- `WS2_32!GetAddrInfoW` at `0x1800549a4`
- `WS2_32!GetAddrInfoW` at `0x1800549a4`

## pseudocode

```c

```
