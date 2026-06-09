# __imp_load_WSACleanup

- ea: `0x18000aab4`
- end: `0x18000aac0`
- name: `__imp_load_WSACleanup`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000a950`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x18000aab4`

## pseudocode

```c
__int64 load_WSACleanup()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x18000aab4  lea     rax, __imp_WSACleanup
0x18000aabb  jmp     __tailMerge_ws2_32_dll
```
