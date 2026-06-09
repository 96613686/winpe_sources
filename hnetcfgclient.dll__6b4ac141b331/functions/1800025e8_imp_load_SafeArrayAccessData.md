# __imp_load_SafeArrayAccessData

- ea: `0x1800025e8`
- end: `0x1800025f4`
- name: `__imp_load_SafeArrayAccessData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000230f`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800025e8`

## pseudocode

```c
__int64 load_SafeArrayAccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x1800025e8  lea     rax, __imp_SafeArrayAccessData
0x1800025ef  jmp     __tailMerge_oleaut32_dll
```
