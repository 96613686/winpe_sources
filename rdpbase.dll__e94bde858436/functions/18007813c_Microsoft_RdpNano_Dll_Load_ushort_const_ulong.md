# Microsoft::RdpNano::Dll::Load(ushort const *,ulong)

- ea: `0x18007813c`
- end: `0x1800781e4`
- name: `?Load@Dll@RdpNano@Microsoft@@QEAAJPEBGK@Z`
- size: `168`
- prototype: `__int64 __fastcall(Microsoft::RdpNano::Dll *__hidden this, LPCWSTR lpLibFileName, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18010cf60`
- `0x18011e610`

## callees

- `0x18007813c`
- `0x1800781ec`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078181`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078181`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180078154`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180078154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007818f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007818f`

## pseudocode

```c

```
