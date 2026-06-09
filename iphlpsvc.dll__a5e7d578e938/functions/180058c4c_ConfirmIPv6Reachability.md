# ConfirmIPv6Reachability

- ea: `0x180058c4c`
- end: `0x180058f47`
- name: `ConfirmIPv6Reachability`
- size: `763`
- prototype: `__int64 __fastcall(SOCKADDR *pSockaddr)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18004ff28`

## callees

- `0x18000d7c0`
- `0x18004b5f0`
- `0x180058c4c`

## import_xrefs

- `IPHLPAPI!FreeMibTable` at `0x180058ea7`
- `IPHLPAPI!FreeMibTable` at `0x180058ea7`
- `IPHLPAPI!Icmp6CreateFile` at `0x180058ccf`
- `IPHLPAPI!Icmp6CreateFile` at `0x180058ccf`
- `IPHLPAPI!Icmp6SendEcho2` at `0x180058d6c`
- `IPHLPAPI!Icmp6SendEcho2` at `0x180058d6c`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058daf`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058eba`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058ee3`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058f07`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058daf`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058eba`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058ee3`
- `IPHLPAPI!IcmpCloseHandle` at `0x180058f07`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x180058df5`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x180058df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058ce4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058ce4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058d8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180058d18`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180058d7a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180058d18`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180058d7a`
- `WS2_32!getnameinfo` at `0x180058cae`
- `WS2_32!getnameinfo` at `0x180058e77`
- `WS2_32!getnameinfo` at `0x180058cae`
- `WS2_32!getnameinfo` at `0x180058e77`

## string_xrefs

- `0x180058cf0`: `Icmp6CreateFile: error %d`

## pseudocode

```c

```
