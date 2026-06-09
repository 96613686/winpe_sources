# __imp_load_LsaIGetSupplementalTokenInfo

- ea: `0x180022488`
- end: `0x180022494`
- name: `__imp_load_LsaIGetSupplementalTokenInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800223c1`

## import_xrefs

- `LSASRV!LsaIGetSupplementalTokenInfo` at `0x180022488`

## pseudocode

```c
__int64 load_LsaIGetSupplementalTokenInfo()
{
  return _tailMerge_lsasrv_dll();
}

```

## disassembly

```asm
0x180022488  lea     rax, __imp_LsaIGetSupplementalTokenInfo
0x18002248f  jmp     __tailMerge_lsasrv_dll
```
