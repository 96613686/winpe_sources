# CRDPENCONTCPListener::CreatePendingConnection(CRDPENCONPort *)

- ea: `0x14006ba00`
- end: `0x14006becd`
- name: `?CreatePendingConnection@CRDPENCONTCPListener@@IEAAXPEAVCRDPENCONPort@@@Z`
- size: `1229`
- prototype: `void __fastcall(CRDPENCONTCPListener *__hidden this, struct CRDPENCONPort *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x14006e19c`

## callees

- `0x1400019e8`
- `0x140003b2c`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001e158`
- `0x140063b70`
- `0x140069204`
- `0x14006a0c8`
- `0x14006a4d4`
- `0x14006ba00`
- `0x14006bf14`
- `0x140090d34`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x14006bd7b`
- `KERNEL32!GetTickCount` at `0x14006bd7b`
- `ADVAPI32!EventActivityIdControl` at `0x14006ba65`
- `ADVAPI32!EventActivityIdControl` at `0x14006be86`
- `ADVAPI32!EventActivityIdControl` at `0x14006ba65`
- `ADVAPI32!EventActivityIdControl` at `0x14006be86`
- `WS2_32!WSAEventSelect` at `0x14006bd96`
- `WS2_32!WSAEventSelect` at `0x14006bd96`
- `WS2_32!__imp_accept` at `0x14006bb21`
- `WS2_32!__imp_accept` at `0x14006bb21`
- `WS2_32!__imp_closesocket` at `0x14006be77`
- `WS2_32!__imp_closesocket` at `0x14006be77`

## string_xrefs

- `0x14006bb43`: `CreatePendingConnection`
- `0x14006bc3c`: `Failed to create the endpoint`
- `0x14006bae4`: `Failed to create the endpoint connection UUID`

## pseudocode

```c

```
