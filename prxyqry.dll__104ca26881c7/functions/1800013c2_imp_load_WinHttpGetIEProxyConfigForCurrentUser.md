# __imp_load_WinHttpGetIEProxyConfigForCurrentUser

- ea: `0x1800013c2`
- end: `0x1800013ce`
- name: `__imp_load_WinHttpGetIEProxyConfigForCurrentUser`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180001331`

## import_xrefs

- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800013c2`

## pseudocode

```c
__int64 load_WinHttpGetIEProxyConfigForCurrentUser()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x1800013c2  lea     rax, __imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800013c9  jmp     __tailMerge_winhttp_dll
```
