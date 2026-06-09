# __imp_load_WSALookupServiceBeginW

- ea: `0x18001386a`
- end: `0x180013876`
- name: `__imp_load_WSALookupServiceBeginW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180013701`

## import_xrefs

- `WS2_32!WSALookupServiceBeginW` at `0x18001386a`

## pseudocode

```c
__int64 load_WSALookupServiceBeginW()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x18001386a  lea     rax, __imp_WSALookupServiceBeginW
0x180013871  jmp     __tailMerge_ws2_32_dll
```
