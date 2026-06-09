# __imp_load_SafeArrayUnaccessData

- ea: `0x1800025fa`
- end: `0x180002606`
- name: `__imp_load_SafeArrayUnaccessData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000230f`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800025fa`

## pseudocode

```c
__int64 load_SafeArrayUnaccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x1800025fa  lea     rax, __imp_SafeArrayUnaccessData
0x180002601  jmp     __tailMerge_oleaut32_dll
```
