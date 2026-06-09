# __imp_load_NduQueryAppToken

- ea: `0x18001c89b`
- end: `0x18001c8a7`
- name: `__imp_load_NduQueryAppToken`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c7c2`

## import_xrefs

- `NduProv!__imp_NduQueryAppToken` at `0x18001c89b`

## pseudocode

```c
__int64 load_NduQueryAppToken()
{
  return _tailMerge_nduprov_dll();
}

```

## disassembly

```asm
0x18001c89b  lea     rax, __imp_NduQueryAppToken
0x18001c8a2  jmp     __tailMerge_nduprov_dll
```
