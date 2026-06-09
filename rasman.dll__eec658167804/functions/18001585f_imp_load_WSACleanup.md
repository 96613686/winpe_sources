# __imp_load_WSACleanup

- ea: `0x18001585f`
- end: `0x18001586b`
- name: `__imp_load_WSACleanup`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180015670`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x18001585f`

## pseudocode

```c
__int64 load_WSACleanup()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x18001585f  lea     rax, __imp_WSACleanup
0x180015866  jmp     __tailMerge_ws2_32_dll
```
