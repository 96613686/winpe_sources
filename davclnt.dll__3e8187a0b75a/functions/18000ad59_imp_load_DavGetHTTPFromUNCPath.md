# __imp_load_DavGetHTTPFromUNCPath

- ea: `0x18000ad59`
- end: `0x18000ad65`
- name: `__imp_load_DavGetHTTPFromUNCPath`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000acda`

## import_xrefs

- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x18000ad59`

## pseudocode

```c
__int64 load_DavGetHTTPFromUNCPath()
{
  return _tailMerge_davhlpr_dll();
}

```

## disassembly

```asm
0x18000ad59  lea     rax, __imp_DavGetHTTPFromUNCPath
0x18000ad60  jmp     __tailMerge_davhlpr_dll
```
