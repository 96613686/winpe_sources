# __imp_load_VariantCopy

- ea: `0x18000c3ab`
- end: `0x18000c3b7`
- name: `__imp_load_VariantCopy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c259`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18000c3ab`

## pseudocode

```c
__int64 load_VariantCopy()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000c3ab  lea     rax, __imp_VariantCopy
0x18000c3b2  jmp     __tailMerge_oleaut32_dll
```
