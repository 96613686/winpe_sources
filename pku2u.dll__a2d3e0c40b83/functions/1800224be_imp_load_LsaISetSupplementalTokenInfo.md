# __imp_load_LsaISetSupplementalTokenInfo

- ea: `0x1800224be`
- end: `0x1800224ca`
- name: `__imp_load_LsaISetSupplementalTokenInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800223c1`

## import_xrefs

- `LSASRV!LsaISetSupplementalTokenInfo` at `0x1800224be`

## pseudocode

```c
__int64 load_LsaISetSupplementalTokenInfo()
{
  return _tailMerge_lsasrv_dll();
}

```

## disassembly

```asm
0x1800224be  lea     rax, __imp_LsaISetSupplementalTokenInfo
0x1800224c5  jmp     __tailMerge_lsasrv_dll
```
