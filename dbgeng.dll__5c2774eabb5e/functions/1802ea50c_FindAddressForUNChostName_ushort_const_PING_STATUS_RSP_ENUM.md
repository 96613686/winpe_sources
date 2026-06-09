# FindAddressForUNChostName(ushort const *,PING_STATUS_RSP_ENUM *)

- ea: `0x1802ea50c`
- end: `0x1802ea6bf`
- name: `?FindAddressForUNChostName@@YA_NPEBGPEAW4PING_STATUS_RSP_ENUM@@@Z`
- size: `435`
- prototype: `bool __fastcall(const unsigned __int16 *, enum PING_STATUS_RSP_ENUM *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800e5780`

## callees

- `0x1800e5a38`
- `0x1800e5b60`
- `0x1800f0f40`
- `0x180159910`
- `0x1802ea50c`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802ea581`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802ea581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ea5e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ea5e9`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1802ea5ae`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1802ea5ae`
- `WS2_32!FreeAddrInfoW` at `0x1802ea67e`
- `WS2_32!FreeAddrInfoW` at `0x1802ea67e`
- `WS2_32!GetAddrInfoW` at `0x1802ea626`
- `WS2_32!GetAddrInfoW` at `0x1802ea626`
- `WS2_32!__imp_WSAStartup` at `0x1802ea5d9`
- `WS2_32!__imp_WSAStartup` at `0x1802ea5d9`
- `WS2_32!__imp_WSACleanup` at `0x1802ea68a`
- `WS2_32!__imp_WSACleanup` at `0x1802ea68a`

## pseudocode

```c

```
