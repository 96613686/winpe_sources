# __imp_load_QueryDirectXDatabaseConfig

- ea: `0x140003c10`
- end: `0x140003c1c`
- name: `__imp_load_QueryDirectXDatabaseConfig`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140003b91`

## import_xrefs

- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabaseConfig` at `0x140003c10`

## pseudocode

```c
__int64 load_QueryDirectXDatabaseConfig()
{
  return _tailMerge_ext_ms_win_dx_dxdbhelper_l1_1_0_dll();
}

```

## disassembly

```asm
0x140003c10  lea     rax, __imp_QueryDirectXDatabaseConfig
0x140003c17  jmp     __tailMerge_ext_ms_win_dx_dxdbhelper_l1_1_0_dll
```
