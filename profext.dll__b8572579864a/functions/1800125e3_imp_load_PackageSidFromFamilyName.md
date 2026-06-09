# __imp_load_PackageSidFromFamilyName

- ea: `0x1800125e3`
- end: `0x1800125ef`
- name: `__imp_load_PackageSidFromFamilyName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180012564`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x1800125e3`

## pseudocode

```c
__int64 load_PackageSidFromFamilyName()
{
  return _tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_2_dll();
}

```

## disassembly

```asm
0x1800125e3  lea     rax, __imp_PackageSidFromFamilyName
0x1800125ea  jmp     __tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_2_dll
```
