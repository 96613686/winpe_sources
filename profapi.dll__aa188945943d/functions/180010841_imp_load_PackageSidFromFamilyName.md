# __imp_load_PackageSidFromFamilyName

- ea: `0x180010841`
- end: `0x18001084d`
- name: `__imp_load_PackageSidFromFamilyName`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800107c2`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x180010841`

## pseudocode

```c
__int64 load_PackageSidFromFamilyName()
{
  return _tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_2_dll();
}

```

## disassembly

```asm
0x180010841  lea     rax, __imp_PackageSidFromFamilyName
0x180010848  jmp     __tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_2_dll
```
