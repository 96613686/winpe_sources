# __imp_load_WSACreateEvent

- ea: `0x18001a777`
- end: `0x18001a783`
- name: `__imp_load_WSACreateEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001a5c6`

## import_xrefs

- `WS2_32!WSACreateEvent` at `0x18001a777`

## pseudocode

```c
__int64 load_WSACreateEvent()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x18001a777  lea     rax, __imp_WSACreateEvent
0x18001a77e  jmp     __tailMerge_ws2_32_dll
```
