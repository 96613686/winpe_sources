# AslpFileGetVersionBlock

- ea: `0x18003f0c0`
- end: `0x18003f707`
- name: `AslpFileGetVersionBlock`
- size: `1607`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003efd4`

## callees

- `0x180005e98`
- `0x180012920`
- `0x180019c84`
- `0x18002e9cc`
- `0x18003f0c0`
- `0x180056262`
- `0x18007a9cf`
- `0x1800838c8`
- `0x180083910`
- `0x1800840ac`
- `0x1800840f0`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003f553`
- `msvcrt!_wcsicmp` at `0x18003f584`
- `msvcrt!_wcsicmp` at `0x18003f553`
- `msvcrt!_wcsicmp` at `0x18003f584`
- `ntdll!LdrResSearchResource` at `0x18003f227`
- `ntdll!LdrResSearchResource` at `0x18003f397`
- `ntdll!LdrResSearchResource` at `0x18003f227`
- `ntdll!LdrResSearchResource` at `0x18003f397`
- `ntdll!RtlVerifyVersionInfo` at `0x18003f2c6`
- `ntdll!RtlVerifyVersionInfo` at `0x18003f2c6`
- `ntdll!RtlAllocateHeap` at `0x18003f4ee`
- `ntdll!RtlAllocateHeap` at `0x18003f4ee`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18003f2a3`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18003f2b2`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18003f2a3`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18003f2b2`

## string_xrefs

- `0x18003f4c7`: `Version block has bad size (falls outside file)`
- `0x18003f64c`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c

```
