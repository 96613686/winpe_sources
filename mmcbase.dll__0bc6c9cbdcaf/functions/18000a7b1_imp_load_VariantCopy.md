# __imp_load_VariantCopy

- ea: `0x18000a7b1`
- end: `0x18000a7bd`
- name: `__imp_load_VariantCopy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000a720`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18000a7b1`

## pseudocode

```c
__int64 load_VariantCopy()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000a7b1  lea     rax, __imp_VariantCopy
0x18000a7b8  jmp     __tailMerge_oleaut32_dll
```
