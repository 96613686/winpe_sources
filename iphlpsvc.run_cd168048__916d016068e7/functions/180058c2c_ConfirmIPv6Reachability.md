# ConfirmIPv6Reachability

- ea: `0x180058c2c`
- end: `0x180058f27`
- name: `ConfirmIPv6Reachability`
- size: `763`
- prototype: `__int64 __fastcall(SOCKADDR *pSockaddr)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18004ff68`

## callees

- `0x18000d7b0`
- `0x18004b630`
- `0x180058c2c`

## import_xrefs

- `IPHLPAPI!FreeMibTable` at `0x180058e87`
- `IPHLPAPI!FreeMibTable` at `0x180058e87`
- `IPHLPAPI!Icmp6CreateFile` at `0x180058caf`
- `IPHLPAPI!Icmp6CreateFile` at `0x180058caf`
- `IPHLPAPI!Icmp6SendEcho2` at `0x180058d4c`
- `IPHLPAPI!Icmp6SendEcho2` at `0x180058d4c`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058d8f`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058e9a`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058ec3`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058ee7`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058d8f`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058e9a`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058ec3`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058ee7`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x180058dd5`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x180058dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058cc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058d6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058cc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058d6c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180058cf8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180058d5a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180058cf8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180058d5a`
- `WS2_32!getnameinfo` at `0x180058c8e`
- `WS2_32!getnameinfo` at `0x180058e57`
- `WS2_32!getnameinfo` at `0x180058c8e`
- `WS2_32!getnameinfo` at `0x180058e57`

## string_xrefs

- `0x180058cd0`: `Icmp6CreateFile: error %d`

## pseudocode

```c

```
