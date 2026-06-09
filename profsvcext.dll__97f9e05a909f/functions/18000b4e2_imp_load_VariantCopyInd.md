# __imp_load_VariantCopyInd

- ea: `0x18000b4e2`
- end: `0x18000b4ee`
- name: `__imp_load_VariantCopyInd`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000af52`

## import_xrefs

- `OLEAUT32!__imp_VariantCopyInd` at `0x18000b4e2`

## pseudocode

```c
__int64 load_VariantCopyInd()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000b4e2  lea     rax, __imp_VariantCopyInd
0x18000b4e9  jmp     __tailMerge_oleaut32_dll
```
