# __imp_load_PSPropertyBag_ReadType

- ea: `0x180003ad9`
- end: `0x180003ae5`
- name: `__imp_load_PSPropertyBag_ReadType`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003a36`

## import_xrefs

- `PROPSYS!PSPropertyBag_ReadType` at `0x180003ad9`

## pseudocode

```c
__int64 load_PSPropertyBag_ReadType()
{
  return _tailMerge_propsys_dll();
}

```

## disassembly

```asm
0x180003ad9  lea     rax, __imp_PSPropertyBag_ReadType
0x180003ae0  jmp     __tailMerge_propsys_dll
```
