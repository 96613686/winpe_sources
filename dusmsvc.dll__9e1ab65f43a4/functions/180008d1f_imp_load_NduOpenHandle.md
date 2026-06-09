# __imp_load_NduOpenHandle

- ea: `0x180008d1f`
- end: `0x180008d2b`
- name: `__imp_load_NduOpenHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008ca0`

## import_xrefs

- `NduProv!__imp_NduOpenHandle` at `0x180008d1f`

## pseudocode

```c
__int64 load_NduOpenHandle()
{
  return _tailMerge_nduprov_dll();
}

```

## disassembly

```asm
0x180008d1f  lea     rax, __imp_NduOpenHandle
0x180008d26  jmp     __tailMerge_nduprov_dll
```
