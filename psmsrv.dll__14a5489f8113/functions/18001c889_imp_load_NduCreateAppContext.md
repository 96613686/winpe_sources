# __imp_load_NduCreateAppContext

- ea: `0x18001c889`
- end: `0x18001c895`
- name: `__imp_load_NduCreateAppContext`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c7c2`

## import_xrefs

- `NduProv!__imp_NduCreateAppContext` at `0x18001c889`

## pseudocode

```c
__int64 load_NduCreateAppContext()
{
  return _tailMerge_nduprov_dll();
}

```

## disassembly

```asm
0x18001c889  lea     rax, __imp_NduCreateAppContext
0x18001c890  jmp     __tailMerge_nduprov_dll
```
