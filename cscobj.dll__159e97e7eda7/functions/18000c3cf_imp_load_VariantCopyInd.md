# __imp_load_VariantCopyInd

- ea: `0x18000c3cf`
- end: `0x18000c3db`
- name: `__imp_load_VariantCopyInd`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c259`

## import_xrefs

- `OLEAUT32!__imp_VariantCopyInd` at `0x18000c3cf`

## pseudocode

```c
__int64 load_VariantCopyInd()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000c3cf  lea     rax, __imp_VariantCopyInd
0x18000c3d6  jmp     __tailMerge_oleaut32_dll
```
