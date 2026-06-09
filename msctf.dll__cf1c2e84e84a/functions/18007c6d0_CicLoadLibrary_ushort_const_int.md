# CicLoadLibrary(ushort const *,int)

- ea: `0x18007c6d0`
- end: `0x18007c814`
- name: `?CicLoadLibrary@@YAPEAUHINSTANCE__@@PEBGH@Z`
- size: `324`
- prototype: `HINSTANCE __fastcall(LPCWSTR lpLibFileName, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180024b88`

## callees

- `0x18003a930`
- `0x18007c6d0`
- `0x1800944a8`
- `0x1800a18d4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007c78d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007c78d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007c6fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007c6fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c7fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c7fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c6f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c6f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007c725`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007c7b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007c725`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007c7b2`

## pseudocode

```c

```
