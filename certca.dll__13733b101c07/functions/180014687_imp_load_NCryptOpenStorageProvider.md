# __imp_load_NCryptOpenStorageProvider

- ea: `0x180014687`
- end: `0x180014693`
- name: `__imp_load_NCryptOpenStorageProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001414c`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x180014687`

## pseudocode

```c
__int64 load_NCryptOpenStorageProvider()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x180014687  lea     rax, __imp_NCryptOpenStorageProvider
0x18001468e  jmp     __tailMerge_ncrypt_dll
```
