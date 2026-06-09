# __imp_load_WSACloseEvent

- ea: `0x18000db4e`
- end: `0x18000db5a`
- name: `__imp_load_WSACloseEvent`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000d9c6`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x18000db4e`

## pseudocode

```c
__int64 load_WSACloseEvent()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x18000db4e  lea     rax, __imp_WSACloseEvent
0x18000db55  jmp     __tailMerge_ws2_32_dll
```
