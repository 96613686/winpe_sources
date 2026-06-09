# __imp_load_NCryptCreateClaim

- ea: `0x180005c96`
- end: `0x180005ca2`
- name: `__imp_load_NCryptCreateClaim`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800059d4`

## import_xrefs

- `ncrypt!NCryptCreateClaim` at `0x180005c96`

## pseudocode

```c
__int64 load_NCryptCreateClaim()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x180005c96  lea     rax, __imp_NCryptCreateClaim
0x180005c9d  jmp     __tailMerge_ncrypt_dll
```
