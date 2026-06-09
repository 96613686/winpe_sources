# __imp_load_NCryptOpenStorageProvider

- ea: `0x180017093`
- end: `0x18001709f`
- name: `__imp_load_NCryptOpenStorageProvider`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180017002`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x180017093`

## pseudocode

```c
__int64 load_NCryptOpenStorageProvider()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x180017093  lea     rax, __imp_NCryptOpenStorageProvider
0x18001709a  jmp     __tailMerge_ncrypt_dll
```
