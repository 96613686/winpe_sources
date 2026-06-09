# __imp_load_WinHttpGetProxyForUrl

- ea: `0x1800013b0`
- end: `0x1800013bc`
- name: `__imp_load_WinHttpGetProxyForUrl`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001331`

## import_xrefs

- `WINHTTP!WinHttpGetProxyForUrl` at `0x1800013b0`

## pseudocode

```c
__int64 __fastcall load_WinHttpGetProxyForUrl(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_winhttp_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800013b0  lea     rax, __imp_WinHttpGetProxyForUrl
0x1800013b7  jmp     __tailMerge_winhttp_dll
```
