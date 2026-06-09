# __imp_load_WSAGetLastError

- ea: `0x1800019f3`
- end: `0x1800019ff`
- name: `__imp_load_WSAGetLastError`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001950`

## import_xrefs

- `WS2_32!__imp_WSAGetLastError` at `0x1800019f3`

## pseudocode

```c
__int64 __fastcall load_WSAGetLastError(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_ws2_32_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800019f3  lea     rax, __imp_WSAGetLastError
0x1800019fa  jmp     __tailMerge_ws2_32_dll
```
