# DllMain

- ea: `0x18003ed04`
- end: `0x18003ee63`
- name: `DllMain`
- size: `351`
- prototype: `int __fastcall(void *hInstance, unsigned int dwReason, void *lpvReserved)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180052204`

## callees

- `0x18001341c`
- `0x18001fae8`
- `0x18001fb94`
- `0x18001fe14`
- `0x1800201f4`
- `0x180024708`
- `0x180024d0c`
- `0x180025bf4`
- `0x18003ed04`
- `0x18003ee6c`
- `0x180052390`

## import_xrefs

- `ntdll!RtlGetNtSystemRoot` at `0x18003ed50`
- `ntdll!RtlGetNtSystemRoot` at `0x18003ed50`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ed74`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ed74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ed81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ed81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee03`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18003ed91`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18003ed91`
- `api-ms-win-core-com-private-l1-1-0!CleanupOleStateInAllTls` at `0x18003edec`
- `api-ms-win-core-com-private-l1-1-0!CleanupOleStateInAllTls` at `0x18003edec`
- `api-ms-win-core-com-private-l1-1-0!CleanupTlsOleState` at `0x18003ee36`
- `api-ms-win-core-com-private-l1-1-0!CleanupTlsOleState` at `0x18003ee36`

## string_xrefs

- `0x18003ed56`: `%s\system32\oleaut32.dll`

## pseudocode

```c

```
