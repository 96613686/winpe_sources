# IsGatewayAddress(std::tuple<_GUID,std::basic_string<char,std::char_traits<char>,std::allocator<char>>> const &,_IP_ADAPTER_ADDRESSES_LH const *)

- ea: `0x18002e194`
- end: `0x18002e402`
- name: `?IsGatewayAddress@@YA_NAEBV?$tuple@U_GUID@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEBU_IP_ADAPTER_ADDRESSES_LH@@@Z`
- size: `622`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e790`
- `0x18002f260`

## callees

- `0x180013748`
- `0x18002e194`
- `0x18002e408`
- `0x18002e688`
- `0x18002fe74`
- `0x18005d69c`
- `0x18008fbd4`
- `0x1800a88a0`
- `0x1800a8d70`
- `0x1800a9738`
- `0x1800aba19`
- `0x1800baf04`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002e211`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002e211`
- `WS2_32!GetAddrInfoW` at `0x18002e2cb`
- `WS2_32!GetAddrInfoW` at `0x18002e2cb`
- `WS2_32!FreeAddrInfoW` at `0x18002e37d`
- `WS2_32!FreeAddrInfoW` at `0x18002e3c1`
- `WS2_32!FreeAddrInfoW` at `0x18002e37d`
- `WS2_32!FreeAddrInfoW` at `0x18002e3c1`
- `WS2_32!__imp_WSAGetLastError` at `0x18002e2d5`
- `WS2_32!__imp_WSAGetLastError` at `0x18002e2d5`
- `WINHTTP!WinHttpCrackUrl` at `0x18002e28a`
- `WINHTTP!WinHttpCrackUrl` at `0x18002e28a`

## string_xrefs

- `0x18002e29c`: `onecore\net\netprofiles\service\src\igd\lib\igdresolver.cpp`
- `0x18002e2e6`: `onecore\net\netprofiles\service\src\igd\lib\igdresolver.cpp`

## pseudocode

```c

```
