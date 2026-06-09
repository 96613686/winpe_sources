# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x10070f30`
- end: `0x10070f62`
- name: `?wil_details_GetKernelBaseProcAddress@@YGP6GHXZPBD@Z`
- size: `50`
- prototype: `int (__stdcall *__userpurge@<eax>(const char *procName@<ecx>))()`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1006f230`
- `0x10071390`

## callees

- `0x10070f30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x10070f44`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x10070f44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10070f55`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10070f55`

## string_xrefs

- `0x10070f3f`: `kernelbase.dll`

## pseudocode

```c

```
