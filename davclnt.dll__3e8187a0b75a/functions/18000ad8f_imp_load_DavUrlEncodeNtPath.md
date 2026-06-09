# __imp_load_DavUrlEncodeNtPath

- ea: `0x18000ad8f`
- end: `0x18000ad9b`
- name: `__imp_load_DavUrlEncodeNtPath`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000acda`

## import_xrefs

- `DAVHLPR!DavUrlEncodeNtPath` at `0x18000ad8f`

## pseudocode

```c
__int64 load_DavUrlEncodeNtPath()
{
  return _tailMerge_davhlpr_dll();
}

```

## disassembly

```asm
0x18000ad8f  lea     rax, __imp_DavUrlEncodeNtPath
0x18000ad96  jmp     __tailMerge_davhlpr_dll
```
