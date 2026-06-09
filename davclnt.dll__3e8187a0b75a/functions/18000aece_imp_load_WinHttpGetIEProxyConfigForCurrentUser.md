# __imp_load_WinHttpGetIEProxyConfigForCurrentUser

- ea: `0x18000aece`
- end: `0x18000aeda`
- name: `__imp_load_WinHttpGetIEProxyConfigForCurrentUser`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000ad9b`

## import_xrefs

- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18000aece`

## pseudocode

```c
__int64 load_WinHttpGetIEProxyConfigForCurrentUser()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x18000aece  lea     rax, __imp_WinHttpGetIEProxyConfigForCurrentUser
0x18000aed5  jmp     __tailMerge_winhttp_dll
```
