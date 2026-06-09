# __imp_load_HttpCreateRequestQueue

- ea: `0x180001d79`
- end: `0x180001d85`
- name: `__imp_load_HttpCreateRequestQueue`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001c10`

## import_xrefs

- `HTTPAPI!HttpCreateRequestQueue` at `0x180001d79`

## pseudocode

```c
__int64 load_HttpCreateRequestQueue()
{
  return _tailMerge_httpapi_dll();
}

```

## disassembly

```asm
0x180001d79  lea     rax, __imp_HttpCreateRequestQueue
0x180001d80  jmp     __tailMerge_httpapi_dll
```
