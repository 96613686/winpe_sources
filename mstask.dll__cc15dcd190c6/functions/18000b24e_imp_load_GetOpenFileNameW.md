# __imp_load_GetOpenFileNameW

- ea: `0x18000b24e`
- end: `0x18000b25a`
- name: `__imp_load_GetOpenFileNameW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b1cf`

## import_xrefs

- `COMDLG32!GetOpenFileNameW` at `0x18000b24e`

## pseudocode

```c
__int64 load_GetOpenFileNameW()
{
  return _tailMerge_comdlg32_dll();
}

```

## disassembly

```asm
0x18000b24e  lea     rax, __imp_GetOpenFileNameW
0x18000b255  jmp     __tailMerge_comdlg32_dll
```
