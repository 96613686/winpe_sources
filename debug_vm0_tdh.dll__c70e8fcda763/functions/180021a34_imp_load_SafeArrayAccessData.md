# __imp_load_SafeArrayAccessData

- ea: `0x180021a34`
- end: `0x180021a40`
- name: `__imp_load_SafeArrayAccessData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180021991`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180021a34`

## pseudocode

```c
__int64 load_SafeArrayAccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x180021a34  lea     rax, __imp_SafeArrayAccessData
0x180021a3b  jmp     __tailMerge_oleaut32_dll
```
