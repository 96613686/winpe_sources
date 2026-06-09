# RasDialW

- ea: `0x1800293d0`
- end: `0x180029aaa`
- name: `RasDialW`
- size: `1754`
- prototype: `DWORD __stdcall(struct tagRASDIALEXTENSIONS *, LPCWSTR, struct tagRASDIALPARAMSW *, DWORD, LPVOID, HRASCONN *)`
- caller_count: `4`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180086bf0`
- `0x18008a200`
- `0x18008b360`
- `0x18008fec0`

## callees

- `0x180010d10`
- `0x1800111f4`
- `0x1800293d0`
- `0x180029ab0`
- `0x180029cd0`
- `0x18004e580`
- `0x18004e984`
- `0x18008f99c`
- `0x1800decee`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `msvcrt!wcsstr` at `0x180029707`
- `msvcrt!wcsstr` at `0x180029757`
- `msvcrt!wcsstr` at `0x180029707`
- `msvcrt!wcsstr` at `0x180029757`
- `msvcrt!_wcsicmp` at `0x180029727`
- `msvcrt!_wcsicmp` at `0x18002976d`
- `msvcrt!_wcsicmp` at `0x180029727`
- `msvcrt!_wcsicmp` at `0x18002976d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800297ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800297ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002995d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002995d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002985b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002985b`
- `CRYPT32!CryptProtectMemory` at `0x18002984a`
- `CRYPT32!CryptProtectMemory` at `0x18002984a`

## pseudocode

```c

```
