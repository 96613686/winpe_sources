# __imp_load_NduDeleteAppContext

- ea: `0x18001c865`
- end: `0x18001c871`
- name: `__imp_load_NduDeleteAppContext`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c7c2`

## import_xrefs

- `NduProv!__imp_NduDeleteAppContext` at `0x18001c865`

## pseudocode

```c
__int64 load_NduDeleteAppContext()
{
  return _tailMerge_nduprov_dll();
}

```

## disassembly

```asm
0x18001c865  lea     rax, __imp_NduDeleteAppContext
0x18001c86c  jmp     __tailMerge_nduprov_dll
```
