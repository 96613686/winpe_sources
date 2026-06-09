# __imp_load_NCryptOpenStorageProvider

- ea: `0x180006e33`
- end: `0x180006e3f`
- name: `__imp_load_NCryptOpenStorageProvider`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006d90`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x180006e33`

## pseudocode

```c
__int64 load_NCryptOpenStorageProvider()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x180006e33  lea     rax, __imp_NCryptOpenStorageProvider
0x180006e3a  jmp     __tailMerge_ncrypt_dll
```
