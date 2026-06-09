# __imp_load_LsaIFreeSupplementalTokenInfo

- ea: `0x18002249a`
- end: `0x1800224a6`
- name: `__imp_load_LsaIFreeSupplementalTokenInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800223c1`

## import_xrefs

- `LSASRV!LsaIFreeSupplementalTokenInfo` at `0x18002249a`

## pseudocode

```c
__int64 load_LsaIFreeSupplementalTokenInfo()
{
  return _tailMerge_lsasrv_dll();
}

```

## disassembly

```asm
0x18002249a  lea     rax, __imp_LsaIFreeSupplementalTokenInfo
0x1800224a1  jmp     __tailMerge_lsasrv_dll
```
