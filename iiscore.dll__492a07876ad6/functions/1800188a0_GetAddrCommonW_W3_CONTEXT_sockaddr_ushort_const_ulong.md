# GetAddrCommonW(W3_CONTEXT *,sockaddr *,ushort const * *,ulong *)

- ea: `0x1800188a0`
- end: `0x180018953`
- name: `?GetAddrCommonW@@YAJPEAVW3_CONTEXT@@PEAUsockaddr@@PEAPEBGPEAK@Z`
- size: `179`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, struct sockaddr *, const unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018880`
- `0x18002d070`

## callees

- `0x1800188a0`
- `0x180038010`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExW` at `0x1800188fe`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800188fe`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180018945`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180018945`

## pseudocode

```c

```
