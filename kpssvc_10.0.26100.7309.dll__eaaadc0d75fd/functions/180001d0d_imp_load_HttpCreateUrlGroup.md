# __imp_load_HttpCreateUrlGroup

- ea: `0x180001d0d`
- end: `0x180001d19`
- name: `__imp_load_HttpCreateUrlGroup`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c10`

## import_xrefs

- `HTTPAPI!HttpCreateUrlGroup` at `0x180001d0d`

## pseudocode

```c
__int64 load_HttpCreateUrlGroup()
{
  return _tailMerge_httpapi_dll();
}

```

## disassembly

```asm
0x180001d0d  lea     rax, __imp_HttpCreateUrlGroup
0x180001d14  jmp     __tailMerge_httpapi_dll
```
