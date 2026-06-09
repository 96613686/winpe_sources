# CLONE_SYSPREP_MODULE::CompareSysprepModule(CLONE_SYSPREP_MODULE const *,CLONE_SYSPREP_MODULE const *)

- ea: `0x180025848`
- end: `0x180025887`
- name: `?CompareSysprepModule@CLONE_SYSPREP_MODULE@@SAHPEBV1@0@Z`
- size: `63`
- prototype: `int __fastcall(wchar_t *String1, wchar_t *String2)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800254ec`
- `0x1800258c0`
- `0x180025a74`

## callees

- `0x180025848`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180025876`
- `msvcrt!_wcsicmp` at `0x180025876`
- `ntdll!_stricmp` at `0x180025866`
- `ntdll!_stricmp` at `0x180025866`

## pseudocode

```c

```
