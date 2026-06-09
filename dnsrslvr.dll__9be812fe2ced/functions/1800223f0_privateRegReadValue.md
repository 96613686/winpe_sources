# privateRegReadValue

- ea: `0x1800223f0`
- end: `0x1800226cd`
- name: `privateRegReadValue`
- size: `733`
- prototype: `LSTATUS __fastcall(HKEY hKey, LPCWSTR lpValueName, __int64, int, BYTE *, DWORD *)`
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800205d0`
- `0x18002078c`
- `0x180021590`
- `0x1800217f0`
- `0x180022140`
- `0x18004d2f4`
- `0x1800623a4`

## callees

- `0x1800223f0`
- `0x180046ec0`
- `0x180047818`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022601`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002269c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022601`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002269c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022616`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022616`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800224d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800224d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022449`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022516`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022449`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022516`

## pseudocode

```c

```
