# __imp_load_PSPropertyBag_ReadStr

- ea: `0x180003aeb`
- end: `0x180003af7`
- name: `__imp_load_PSPropertyBag_ReadStr`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003a36`

## import_xrefs

- `PROPSYS!PSPropertyBag_ReadStr` at `0x180003aeb`

## pseudocode

```c
__int64 load_PSPropertyBag_ReadStr()
{
  return _tailMerge_propsys_dll();
}

```

## disassembly

```asm
0x180003aeb  lea     rax, __imp_PSPropertyBag_ReadStr
0x180003af2  jmp     __tailMerge_propsys_dll
```
