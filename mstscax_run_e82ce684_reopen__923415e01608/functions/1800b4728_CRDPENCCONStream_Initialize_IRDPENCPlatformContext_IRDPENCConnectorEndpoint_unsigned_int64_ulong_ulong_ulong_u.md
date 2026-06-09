# CRDPENCCONStream::Initialize(IRDPENCPlatformContext *,IRDPENCConnectorEndpoint *,unsigned __int64,ulong,ulong,ulong,ulong)

- ea: `0x1800b4728`
- end: `0x1800b51ba`
- name: `?Initialize@CRDPENCCONStream@@IEAAJPEAUIRDPENCPlatformContext@@PEAUIRDPENCConnectorEndpoint@@_KKKKK@Z`
- size: `2706`
- prototype: `__int64 __fastcall(CRDPENCCONStream *__hidden this, struct IRDPENCPlatformContext *, struct IRDPENCConnectorEndpoint *, unsigned __int64, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x180369188`

## callees

- `0x1800172ec`
- `0x1800186a0`
- `0x1800186d0`
- `0x18001f5d0`
- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x18009fbcc`
- `0x1800b4728`
- `0x1800dcaec`
- `0x1800dcebc`
- `0x1800e9b1c`
- `0x1800f7748`
- `0x180101fbc`
- `0x180223b28`
- `0x18022400c`
- `0x18036903c`
- `0x180369bd0`
- `0x180373468`
- `0x180373638`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800b4ab8`
- `KERNEL32!GetLastError` at `0x1800b4ab8`
- `KERNEL32!GetTickCount` at `0x1800b4f94`
- `KERNEL32!GetTickCount` at `0x1800b4f94`
- `KERNEL32!CreateEventW` at `0x1800b4aa6`
- `KERNEL32!CreateEventW` at `0x1800b4aa6`
- `OLEAUT32!__imp_VariantInit` at `0x1800b47a7`
- `OLEAUT32!__imp_VariantInit` at `0x1800b47a7`
- `OLEAUT32!__imp_VariantClear` at `0x1800b5166`
- `OLEAUT32!__imp_VariantClear` at `0x1800b5166`
- `ADVAPI32!EventActivityIdControl` at `0x1800b4a27`
- `ADVAPI32!EventActivityIdControl` at `0x1800b4a8f`
- `ADVAPI32!EventActivityIdControl` at `0x1800b4d0a`
- `ADVAPI32!EventActivityIdControl` at `0x1800b5093`
- `ADVAPI32!EventActivityIdControl` at `0x1800b4a27`
- `ADVAPI32!EventActivityIdControl` at `0x1800b4a8f`
- `ADVAPI32!EventActivityIdControl` at `0x1800b4d0a`
- `ADVAPI32!EventActivityIdControl` at `0x1800b5093`
- `WS2_32!WSAIoctl` at `0x1800b4d71`
- `WS2_32!WSAIoctl` at `0x1800b4d71`
- `WS2_32!__imp_setsockopt` at `0x1800b4c99`
- `WS2_32!__imp_setsockopt` at `0x1800b4cc7`
- `WS2_32!__imp_setsockopt` at `0x1800b4cf2`
- `WS2_32!__imp_setsockopt` at `0x1800b4c99`
- `WS2_32!__imp_setsockopt` at `0x1800b4cc7`
- `WS2_32!__imp_setsockopt` at `0x1800b4cf2`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b4d96`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b4d96`
- `WS2_32!__imp_WSAStartup` at `0x1800b4c0a`
- `WS2_32!__imp_WSAStartup` at `0x1800b4c0a`

## string_xrefs

- `0x1800b4b55`: `Failed to create IO Context pool`
- `0x1800b4bf3`: `Failed to create Large StreamBuffer pool`
- `0x1800b4baa`: `Failed to create Small StreamBuffer pool`
- `0x1800b5030`: `Failed to associate sock with IO completion port.`

## pseudocode

```c

```
