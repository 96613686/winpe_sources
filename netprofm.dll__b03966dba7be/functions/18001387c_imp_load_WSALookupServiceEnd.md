# __imp_load_WSALookupServiceEnd

- ea: `0x18001387c`
- end: `0x180013888`
- name: `__imp_load_WSALookupServiceEnd`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180013701`

## import_xrefs

- `WS2_32!WSALookupServiceEnd` at `0x18001387c`

## pseudocode

```c
__int64 load_WSALookupServiceEnd()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x18001387c  lea     rax, __imp_WSALookupServiceEnd
0x180013883  jmp     __tailMerge_ws2_32_dll
```
