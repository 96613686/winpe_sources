# __imp_load_WSACleanup

- ea: `0x1800014a7`
- end: `0x1800014b3`
- name: `__imp_load_WSACleanup`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800013e0`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x1800014a7`

## pseudocode

```c
__int64 load_WSACleanup()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x1800014a7  lea     rax, __imp_WSACleanup
0x1800014ae  jmp     __tailMerge_ws2_32_dll
```
