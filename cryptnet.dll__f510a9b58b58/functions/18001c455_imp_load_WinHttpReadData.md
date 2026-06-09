# __imp_load_WinHttpReadData

- ea: `0x18001c455`
- end: `0x18001c461`
- name: `__imp_load_WinHttpReadData`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c2fe`

## import_xrefs

- `WINHTTP!WinHttpReadData` at `0x18001c455`

## pseudocode

```c
__int64 load_WinHttpReadData()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x18001c455  lea     rax, __imp_WinHttpReadData
0x18001c45c  jmp     __tailMerge_winhttp_dll
```
