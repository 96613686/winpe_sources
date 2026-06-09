# JAmsi::JAmsiInitialize(void)

- ea: `0x180040224`
- end: `0x1800403a7`
- name: `?JAmsiInitialize@JAmsi@@QEAA_NXZ`
- size: `387`
- prototype: `bool __fastcall(JAmsi *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180013e80`
- `0x18003e5f0`

## callees

- `0x180040224`
- `0x1800403b0`
- `0x180040644`
- `0x180064e50`
- `0x18006f9f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180040325`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180040325`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180040265`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180040265`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004039f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004039f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040285`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800402a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800402cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040285`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800402a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800402cd`

## string_xrefs

- `0x18004025e`: `amsi.dll`
- `0x18004029b`: `AmsiScanBuffer`
- `0x1800402bf`: `AmsiUninitialize`
- `0x18004027b`: `AmsiInitialize`

## pseudocode

```c

```
