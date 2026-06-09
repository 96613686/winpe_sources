# __imp_load_GetOpenFileNameW

- ea: `0x18000a9ac`
- end: `0x18000a9b8`
- name: `__imp_load_GetOpenFileNameW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a92d`

## import_xrefs

- `COMDLG32!GetOpenFileNameW` at `0x18000a9ac`

## pseudocode

```c
__int64 load_GetOpenFileNameW()
{
  return _tailMerge_comdlg32_dll();
}

```

## disassembly

```asm
0x18000a9ac  lea     rax, __imp_GetOpenFileNameW
0x18000a9b3  jmp     __tailMerge_comdlg32_dll
```
