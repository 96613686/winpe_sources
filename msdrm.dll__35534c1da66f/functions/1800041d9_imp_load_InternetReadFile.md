# __imp_load_InternetReadFile

- ea: `0x1800041d9`
- end: `0x1800041e5`
- name: `__imp_load_InternetReadFile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180004070`

## import_xrefs

- `WININET!InternetReadFile` at `0x1800041d9`

## pseudocode

```c
__int64 load_InternetReadFile()
{
  return _tailMerge_wininet_dll();
}

```

## disassembly

```asm
0x1800041d9  lea     rax, __imp_InternetReadFile
0x1800041e0  jmp     __tailMerge_wininet_dll
```
