# CRDPENCONTCPListener::CreatePendingConnection(CRDPENCONPort *)

- ea: `0x140069890`
- end: `0x140069d5d`
- name: `?CreatePendingConnection@CRDPENCONTCPListener@@IEAAXPEAVCRDPENCONPort@@@Z`
- size: `1229`
- prototype: `void __fastcall(CRDPENCONTCPListener *__hidden this, struct CRDPENCONPort *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x14006c02c`

## callees

- `0x1400019e8`
- `0x140003b2c`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001e158`
- `0x140061a00`
- `0x140067094`
- `0x140067f58`
- `0x140068364`
- `0x140069890`
- `0x140069da4`
- `0x14008ebc4`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140069c0b`
- `KERNEL32!GetTickCount` at `0x140069c0b`
- `ADVAPI32!EventActivityIdControl` at `0x1400698f5`
- `ADVAPI32!EventActivityIdControl` at `0x140069d16`
- `ADVAPI32!EventActivityIdControl` at `0x1400698f5`
- `ADVAPI32!EventActivityIdControl` at `0x140069d16`
- `WS2_32!WSAEventSelect` at `0x140069c26`
- `WS2_32!WSAEventSelect` at `0x140069c26`
- `WS2_32!__imp_accept` at `0x1400699b1`
- `WS2_32!__imp_accept` at `0x1400699b1`
- `WS2_32!__imp_closesocket` at `0x140069d07`
- `WS2_32!__imp_closesocket` at `0x140069d07`

## string_xrefs

- `0x1400699d3`: `CreatePendingConnection`
- `0x140069acc`: `Failed to create the endpoint`
- `0x140069974`: `Failed to create the endpoint connection UUID`

## pseudocode

```c

```
