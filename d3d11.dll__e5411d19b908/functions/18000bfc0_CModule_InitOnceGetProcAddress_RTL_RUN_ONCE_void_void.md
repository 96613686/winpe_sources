# CModule::InitOnceGetProcAddress(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18000bfc0`
- end: `0x18000c015`
- name: `?InitOnceGetProcAddress@CModule@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `85`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b8bc`
- `0x18000bfc0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000bfe9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000bfe9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bff9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bff9`

## string_xrefs

- `0x18000bff2`: `CompatValue`

## pseudocode

```c

```
