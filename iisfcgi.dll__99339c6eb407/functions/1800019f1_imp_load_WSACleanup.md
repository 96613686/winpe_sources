# __imp_load_WSACleanup

- ea: `0x1800019f1`
- end: `0x1800019fd`
- name: `__imp_load_WSACleanup`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001960`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x1800019f1`

## pseudocode

```c
__int64 load_WSACleanup()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x1800019f1  lea     rax, __imp_WSACleanup
0x1800019f8  jmp     __tailMerge_ws2_32_dll
```
