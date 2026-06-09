# __imp_load_SafeArrayUnaccessData

- ea: `0x180021a58`
- end: `0x180021a64`
- name: `__imp_load_SafeArrayUnaccessData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180021991`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180021a58`

## pseudocode

```c
__int64 load_SafeArrayUnaccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x180021a58  lea     rax, __imp_SafeArrayUnaccessData
0x180021a5f  jmp     __tailMerge_oleaut32_dll
```
