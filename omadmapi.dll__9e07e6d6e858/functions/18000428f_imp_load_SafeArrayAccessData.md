# __imp_load_SafeArrayAccessData

- ea: `0x18000428f`
- end: `0x18000429b`
- name: `__imp_load_SafeArrayAccessData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003f54`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000428f`

## pseudocode

```c
__int64 load_SafeArrayAccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000428f  lea     rax, __imp_SafeArrayAccessData
0x180004296  jmp     __tailMerge_oleaut32_dll
```
