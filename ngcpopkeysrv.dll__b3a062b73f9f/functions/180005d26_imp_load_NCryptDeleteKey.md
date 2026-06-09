# __imp_load_NCryptDeleteKey

- ea: `0x180005d26`
- end: `0x180005d32`
- name: `__imp_load_NCryptDeleteKey`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800059d4`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x180005d26`

## pseudocode

```c
__int64 load_NCryptDeleteKey()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x180005d26  lea     rax, __imp_NCryptDeleteKey
0x180005d2d  jmp     __tailMerge_ncrypt_dll
```
