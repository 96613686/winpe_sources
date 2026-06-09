# __imp_load_PSPropertyBag_ReadInt

- ea: `0x180003ac7`
- end: `0x180003ad3`
- name: `__imp_load_PSPropertyBag_ReadInt`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003a36`

## import_xrefs

- `PROPSYS!PSPropertyBag_ReadInt` at `0x180003ac7`

## pseudocode

```c
__int64 load_PSPropertyBag_ReadInt()
{
  return _tailMerge_propsys_dll();
}

```

## disassembly

```asm
0x180003ac7  lea     rax, __imp_PSPropertyBag_ReadInt
0x180003ace  jmp     __tailMerge_propsys_dll
```
