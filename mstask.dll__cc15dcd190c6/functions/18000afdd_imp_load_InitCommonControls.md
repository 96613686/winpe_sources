# __imp_load_InitCommonControls

- ea: `0x18000afdd`
- end: `0x18000afe9`
- name: `__imp_load_InitCommonControls`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000af5e`

## import_xrefs

- `COMCTL32!__imp_InitCommonControls` at `0x18000afdd`

## pseudocode

```c
__int64 load_InitCommonControls()
{
  return _tailMerge_comctl32_dll();
}

```

## disassembly

```asm
0x18000afdd  lea     rax, __imp_InitCommonControls
0x18000afe4  jmp     __tailMerge_comctl32_dll
```
