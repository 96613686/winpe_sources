# __imp_load_WinHttpOpen

- ea: `0x18000ae86`
- end: `0x18000ae92`
- name: `__imp_load_WinHttpOpen`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ad9b`

## import_xrefs

- `WINHTTP!WinHttpOpen` at `0x18000ae86`

## pseudocode

```c
__int64 load_WinHttpOpen()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x18000ae86  lea     rax, __imp_WinHttpOpen
0x18000ae8d  jmp     __tailMerge_winhttp_dll
```
