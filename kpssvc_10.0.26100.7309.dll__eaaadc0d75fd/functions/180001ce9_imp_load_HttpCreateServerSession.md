# __imp_load_HttpCreateServerSession

- ea: `0x180001ce9`
- end: `0x180001cf5`
- name: `__imp_load_HttpCreateServerSession`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001c10`

## import_xrefs

- `HTTPAPI!HttpCreateServerSession` at `0x180001ce9`

## pseudocode

```c
__int64 load_HttpCreateServerSession()
{
  return _tailMerge_httpapi_dll();
}

```

## disassembly

```asm
0x180001ce9  lea     rax, __imp_HttpCreateServerSession
0x180001cf0  jmp     __tailMerge_httpapi_dll
```
