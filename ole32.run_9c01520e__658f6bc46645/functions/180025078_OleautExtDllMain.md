# OleautExtDllMain

- ea: `0x180025078`
- end: `0x18002513e`
- name: `OleautExtDllMain`
- size: `198`
- prototype: `int __fastcall(HINSTANCE__ *dwReason, unsigned int lpReserved, void *hModule)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180041910`

## callees

- `0x180025078`
- `0x180025144`
- `0x1800253cc`
- `0x180046460`

## import_xrefs

- `ntdll!RtlGetNtSystemRoot` at `0x1800250d2`
- `ntdll!RtlGetNtSystemRoot` at `0x1800250d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800250fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800250fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002510f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002510f`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180025125`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180025125`

## string_xrefs

- `0x1800250de`: `%s\system32\oleaut32.dll`

## pseudocode

```c

```
