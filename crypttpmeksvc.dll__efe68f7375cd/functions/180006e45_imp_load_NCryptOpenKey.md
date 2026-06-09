# __imp_load_NCryptOpenKey

- ea: `0x180006e45`
- end: `0x180006e51`
- name: `__imp_load_NCryptOpenKey`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006d90`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x180006e45`

## pseudocode

```c
__int64 load_NCryptOpenKey()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x180006e45  lea     rax, __imp_NCryptOpenKey
0x180006e4c  jmp     __tailMerge_ncrypt_dll
```
