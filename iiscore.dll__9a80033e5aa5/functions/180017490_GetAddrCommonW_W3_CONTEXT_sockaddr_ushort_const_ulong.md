# GetAddrCommonW(W3_CONTEXT *,sockaddr *,ushort const * *,ulong *)

- ea: `0x180017490`
- end: `0x180017536`
- name: `?GetAddrCommonW@@YAJPEAVW3_CONTEXT@@PEAUsockaddr@@PEAPEBGPEAK@Z`
- size: `166`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, struct sockaddr *, const unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017470`
- `0x18002aa80`

## callees

- `0x180017490`
- `0x180035010`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExW` at `0x1800174ee`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800174ee`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18001752e`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18001752e`

## pseudocode

```c

```
