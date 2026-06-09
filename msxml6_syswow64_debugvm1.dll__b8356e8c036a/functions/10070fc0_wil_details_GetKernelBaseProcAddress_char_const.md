# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x10070fc0`
- end: `0x10070ff2`
- name: `?wil_details_GetKernelBaseProcAddress@@YGP6GHXZPBD@Z`
- size: `50`
- prototype: `int (__stdcall *__userpurge@<eax>(const char *procName@<ecx>))()`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1006f2c0`
- `0x10071430`

## callees

- `0x10070fc0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x10070fd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x10070fd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10070fe5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10070fe5`

## string_xrefs

- `0x10070fcf`: `kernelbase.dll`

## pseudocode

```c

```
