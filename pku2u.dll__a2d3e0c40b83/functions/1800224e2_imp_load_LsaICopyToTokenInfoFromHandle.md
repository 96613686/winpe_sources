# __imp_load_LsaICopyToTokenInfoFromHandle

- ea: `0x1800224e2`
- end: `0x1800224ee`
- name: `__imp_load_LsaICopyToTokenInfoFromHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800223c1`

## import_xrefs

- `LSASRV!LsaICopyToTokenInfoFromHandle` at `0x1800224e2`

## pseudocode

```c
__int64 load_LsaICopyToTokenInfoFromHandle()
{
  return _tailMerge_lsasrv_dll();
}

```

## disassembly

```asm
0x1800224e2  lea     rax, __imp_LsaICopyToTokenInfoFromHandle
0x1800224e9  jmp     __tailMerge_lsasrv_dll
```
