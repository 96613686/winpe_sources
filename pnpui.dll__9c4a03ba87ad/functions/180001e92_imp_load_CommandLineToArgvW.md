# __imp_load_CommandLineToArgvW

- ea: `0x180001e92`
- end: `0x180001e9e`
- name: `__imp_load_CommandLineToArgvW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001e13`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x180001e92`

## pseudocode

```c
__int64 load_CommandLineToArgvW()
{
  return _tailMerge_api_ms_win_shcore_obsolete_l1_1_0_dll();
}

```

## disassembly

```asm
0x180001e92  lea     rax, __imp_CommandLineToArgvW
0x180001e99  jmp     __tailMerge_api_ms_win_shcore_obsolete_l1_1_0_dll
```
