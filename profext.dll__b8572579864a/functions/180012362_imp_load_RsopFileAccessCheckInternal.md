# __imp_load_RsopFileAccessCheckInternal

- ea: `0x180012362`
- end: `0x18001236e`
- name: `__imp_load_RsopFileAccessCheckInternal`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180012245`

## import_xrefs

- `ext-ms-win-gpsvc-grouppolicy-l1-1-0!RsopFileAccessCheckInternal` at `0x180012362`

## pseudocode

```c
__int64 load_RsopFileAccessCheckInternal()
{
  return _tailMerge_ext_ms_win_gpsvc_grouppolicy_l1_1_0_dll();
}

```

## disassembly

```asm
0x180012362  lea     rax, __imp_RsopFileAccessCheckInternal
0x180012369  jmp     __tailMerge_ext_ms_win_gpsvc_grouppolicy_l1_1_0_dll
```
