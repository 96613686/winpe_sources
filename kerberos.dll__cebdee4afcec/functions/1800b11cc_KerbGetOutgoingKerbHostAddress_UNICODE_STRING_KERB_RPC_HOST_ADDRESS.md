# KerbGetOutgoingKerbHostAddress(_UNICODE_STRING *,_KERB_RPC_HOST_ADDRESS * *)

- ea: `0x1800b11cc`
- end: `0x1800b1612`
- name: `?KerbGetOutgoingKerbHostAddress@@YAJPEAU_UNICODE_STRING@@PEAPEAU_KERB_RPC_HOST_ADDRESS@@@Z`
- size: `1094`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1, struct _KERB_RPC_HOST_ADDRESS **)`
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x1800b0398`
- `0x1800b0688`
- `0x1800b1f98`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x18002c31c`
- `0x180037e30`
- `0x180065c48`
- `0x1800744cf`
- `0x18008a114`
- `0x18008b2f4`
- `0x18008b70c`
- `0x1800b02e4`
- `0x1800b11cc`
- `0x1800b3eec`

## import_xrefs

- `WS2_32!WSAIoctl` at `0x1800b1418`
- `WS2_32!WSAIoctl` at `0x1800b14a8`
- `WS2_32!WSAIoctl` at `0x1800b1418`
- `WS2_32!WSAIoctl` at `0x1800b14a8`
- `WS2_32!GetAddrInfoW` at `0x1800b1322`
- `WS2_32!GetAddrInfoW` at `0x1800b1322`
- `WS2_32!FreeAddrInfoW` at `0x1800b15bd`
- `WS2_32!FreeAddrInfoW` at `0x1800b15bd`
- `WS2_32!__imp_closesocket` at `0x1800b15d9`
- `WS2_32!__imp_closesocket` at `0x1800b15d9`
- `WS2_32!__imp_socket` at `0x1800b139c`
- `WS2_32!__imp_socket` at `0x1800b139c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b13af`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b1423`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b14b3`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b13af`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b1423`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b14b3`

## string_xrefs

- `0x1800b13b5`: `KerbGetOutgoingKerbHostAddress: Unable to create a socket: %d\n`

## pseudocode

```c

```
