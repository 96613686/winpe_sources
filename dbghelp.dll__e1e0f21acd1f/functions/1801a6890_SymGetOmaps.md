# SymGetOmaps

- ea: `0x1801a6890`
- end: `0x1801a6948`
- name: `SymGetOmaps`
- size: `184`
- prototype: `BOOL __stdcall(HANDLE hProcess, DWORD64 BaseOfDll, POMAP *OmapTo, PDWORD64 cOmapTo, POMAP *OmapFrom, PDWORD64 cOmapFrom)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000aeec`
- `0x180016718`
- `0x1801a6890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6935`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6935`

## pseudocode

```c

```
