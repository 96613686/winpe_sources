# __imp_load_WSACreateEvent

- ea: `0x18000db3c`
- end: `0x18000db48`
- name: `__imp_load_WSACreateEvent`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d9c6`

## import_xrefs

- `WS2_32!WSACreateEvent` at `0x18000db3c`

## pseudocode

```c
__int64 load_WSACreateEvent()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x18000db3c  lea     rax, __imp_WSACreateEvent
0x18000db43  jmp     __tailMerge_ws2_32_dll
```
