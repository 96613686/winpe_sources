# NetpSrvOpen

- ea: `0x180001e30`
- end: `0x1800023e9`
- name: `NetpSrvOpen`
- size: `1465`
- prototype: `__int64 __fastcall(PCSTR pszName, DWORD Options)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180081b1c`

## callees

- `0x180001e30`
- `0x1800039e0`
- `0x18000e270`
- `0x180018414`
- `0x18001843c`
- `0x18001847c`
- `0x18001858c`
- `0x18007e350`
- `0x180087030`
- `0x1800870c4`
- `0x180087160`
- `0x18008728c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180002131`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180002131`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002064`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002064`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002235`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002336`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002235`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002336`
- `ntdll!NtQuerySystemTime` at `0x180001e6d`
- `ntdll!NtQuerySystemTime` at `0x180001e6d`
- `DNSAPI!DnsFree` at `0x1800023bf`
- `DNSAPI!DnsFree` at `0x1800023bf`
- `DNSAPI!DnsQuery_UTF8` at `0x180001ef7`
- `DNSAPI!DnsQuery_UTF8` at `0x180001ef7`

## pseudocode

```c

```
