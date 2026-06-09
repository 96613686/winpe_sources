# __imp_load_WSAStartup

- ea: `0x18000145f`
- end: `0x18000146b`
- name: `__imp_load_WSAStartup`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800013e0`

## import_xrefs

- `WS2_32!__imp_WSAStartup` at `0x18000145f`

## pseudocode

```c
__int64 __fastcall load_WSAStartup(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_ws2_32_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000145f  lea     rax, __imp_WSAStartup
0x180001466  jmp     __tailMerge_ws2_32_dll
```
