# __imp_load_WinHttpOpen

- ea: `0x18001c37d`
- end: `0x18001c389`
- name: `__imp_load_WinHttpOpen`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c2fe`

## import_xrefs

- `WINHTTP!WinHttpOpen` at `0x18001c37d`

## pseudocode

```c
__int64 load_WinHttpOpen()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x18001c37d  lea     rax, __imp_WinHttpOpen
0x18001c384  jmp     __tailMerge_winhttp_dll
```
