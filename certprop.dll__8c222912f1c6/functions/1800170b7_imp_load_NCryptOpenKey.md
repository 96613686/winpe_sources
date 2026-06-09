# __imp_load_NCryptOpenKey

- ea: `0x1800170b7`
- end: `0x1800170c3`
- name: `__imp_load_NCryptOpenKey`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180017002`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x1800170b7`

## pseudocode

```c
__int64 load_NCryptOpenKey()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x1800170b7  lea     rax, __imp_NCryptOpenKey
0x1800170be  jmp     __tailMerge_ncrypt_dll
```
