# __imp_load_PSPropertyBag_WriteUnknown

- ea: `0x180003ab5`
- end: `0x180003ac1`
- name: `__imp_load_PSPropertyBag_WriteUnknown`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003a36`

## import_xrefs

- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x180003ab5`

## pseudocode

```c
__int64 load_PSPropertyBag_WriteUnknown()
{
  return _tailMerge_propsys_dll();
}

```

## disassembly

```asm
0x180003ab5  lea     rax, __imp_PSPropertyBag_WriteUnknown
0x180003abc  jmp     __tailMerge_propsys_dll
```
