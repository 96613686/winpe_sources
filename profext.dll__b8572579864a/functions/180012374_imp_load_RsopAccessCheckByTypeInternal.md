# __imp_load_RsopAccessCheckByTypeInternal

- ea: `0x180012374`
- end: `0x180012380`
- name: `__imp_load_RsopAccessCheckByTypeInternal`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180012245`

## import_xrefs

- `ext-ms-win-gpsvc-grouppolicy-l1-1-0!RsopAccessCheckByTypeInternal` at `0x180012374`

## pseudocode

```c
__int64 load_RsopAccessCheckByTypeInternal()
{
  return _tailMerge_ext_ms_win_gpsvc_grouppolicy_l1_1_0_dll();
}

```

## disassembly

```asm
0x180012374  lea     rax, __imp_RsopAccessCheckByTypeInternal
0x18001237b  jmp     __tailMerge_ext_ms_win_gpsvc_grouppolicy_l1_1_0_dll
```
