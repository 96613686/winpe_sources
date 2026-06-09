# __imp_load_WSALookupServiceNextW

- ea: `0x180013858`
- end: `0x180013864`
- name: `__imp_load_WSALookupServiceNextW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180013701`

## import_xrefs

- `WS2_32!WSALookupServiceNextW` at `0x180013858`

## pseudocode

```c
__int64 load_WSALookupServiceNextW()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x180013858  lea     rax, __imp_WSALookupServiceNextW
0x18001385f  jmp     __tailMerge_ws2_32_dll
```
