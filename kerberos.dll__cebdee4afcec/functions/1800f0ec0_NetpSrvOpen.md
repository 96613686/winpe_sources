# NetpSrvOpen

- ea: `0x1800f0ec0`
- end: `0x1800f1445`
- name: `NetpSrvOpen`
- size: `1413`
- prototype: `__int64 __fastcall(PCSTR pszName, DWORD Options, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1800949bc`

## callees

- `0x18006ccec`
- `0x18006d73c`
- `0x180070680`
- `0x180090aac`
- `0x1800c6980`
- `0x1800f0998`
- `0x1800f0ec0`
- `0x1800f1608`
- `0x1800f16a0`
- `0x1800f1724`
- `0x1800f17b8`
- `0x1800f1854`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800f11ae`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800f11ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f10d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f10d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f12af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f139f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f12af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f139f`
- `ntdll!NtQuerySystemTime` at `0x1800f0f09`
- `ntdll!NtQuerySystemTime` at `0x1800f0f09`
- `DNSAPI!DnsQuery_UTF8` at `0x1800f0f90`
- `DNSAPI!DnsQuery_UTF8` at `0x1800f0f90`
- `DNSAPI!DnsFree` at `0x1800f1419`
- `DNSAPI!DnsFree` at `0x1800f1419`

## pseudocode

```c

```
