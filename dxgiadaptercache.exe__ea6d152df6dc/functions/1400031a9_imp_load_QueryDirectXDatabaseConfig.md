# __imp_load_QueryDirectXDatabaseConfig

- ea: `0x1400031a9`
- end: `0x1400031b5`
- name: `__imp_load_QueryDirectXDatabaseConfig`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x14000312a`

## import_xrefs

- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabaseConfig` at `0x1400031a9`

## pseudocode

```c
__int64 load_QueryDirectXDatabaseConfig()
{
  return _tailMerge_ext_ms_win_dx_dxdbhelper_l1_1_0_dll();
}

```

## disassembly

```asm
0x1400031a9  lea     rax, __imp_QueryDirectXDatabaseConfig
0x1400031b0  jmp     __tailMerge_ext_ms_win_dx_dxdbhelper_l1_1_0_dll
```
