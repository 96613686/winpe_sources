# CRegistry::EnumAllRegistryVals(ulong *)

- ea: `0x180044bb8`
- end: `0x180044d54`
- name: `?EnumAllRegistryVals@CRegistry@@QEAAJPEAK@Z`
- size: `412`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180044960`
- `0x180045cac`

## callees

- `0x180029560`
- `0x180044bb8`
- `0x18004535c`
- `0x18007e700`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x180044c95`
- `ADVAPI32!RegEnumValueW` at `0x180044c95`
- `ADVAPI32!RegEnumKeyExW` at `0x180044c36`
- `ADVAPI32!RegEnumKeyExW` at `0x180044ce2`
- `ADVAPI32!RegEnumKeyExW` at `0x180044c36`
- `ADVAPI32!RegEnumKeyExW` at `0x180044ce2`
- `ADVAPI32!RegCloseKey` at `0x180044ca6`
- `ADVAPI32!RegCloseKey` at `0x180044ca6`

## string_xrefs

- `0x180044d12`: `<CRegistry::EnumAllRegistryVals|Trace|HR> `

## pseudocode

```c

```
