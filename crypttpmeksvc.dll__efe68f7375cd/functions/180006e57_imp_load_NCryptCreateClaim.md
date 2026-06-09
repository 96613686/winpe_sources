# __imp_load_NCryptCreateClaim

- ea: `0x180006e57`
- end: `0x180006e63`
- name: `__imp_load_NCryptCreateClaim`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006d90`

## import_xrefs

- `ncrypt!NCryptCreateClaim` at `0x180006e57`

## pseudocode

```c
__int64 load_NCryptCreateClaim()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x180006e57  lea     rax, __imp_NCryptCreateClaim
0x180006e5e  jmp     __tailMerge_ncrypt_dll
```
