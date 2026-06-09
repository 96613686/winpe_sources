# __imp_load_WSACloseEvent

- ea: `0x18001ddba`
- end: `0x18001ddc6`
- name: `__imp_load_WSACloseEvent`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001dcf3`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x18001ddba`

## pseudocode

```c
__int64 load_WSACloseEvent()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x18001ddba  lea     rax, __imp_WSACloseEvent
0x18001ddc1  jmp     __tailMerge_ws2_32_dll
```
