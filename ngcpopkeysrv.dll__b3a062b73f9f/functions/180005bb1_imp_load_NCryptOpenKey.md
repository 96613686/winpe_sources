# __imp_load_NCryptOpenKey

- ea: `0x180005bb1`
- end: `0x180005bbd`
- name: `__imp_load_NCryptOpenKey`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800059d4`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x180005bb1`

## pseudocode

```c
__int64 load_NCryptOpenKey()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x180005bb1  lea     rax, __imp_NCryptOpenKey
0x180005bb8  jmp     __tailMerge_ncrypt_dll
```
