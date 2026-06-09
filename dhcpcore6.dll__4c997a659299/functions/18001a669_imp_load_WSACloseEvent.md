# __imp_load_WSACloseEvent

- ea: `0x18001a669`
- end: `0x18001a675`
- name: `__imp_load_WSACloseEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001a5c6`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x18001a669`

## pseudocode

```c
__int64 load_WSACloseEvent()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x18001a669  lea     rax, __imp_WSACloseEvent
0x18001a670  jmp     __tailMerge_ws2_32_dll
```
