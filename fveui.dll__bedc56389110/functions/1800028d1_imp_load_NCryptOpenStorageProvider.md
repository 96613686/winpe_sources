# __imp_load_NCryptOpenStorageProvider

- ea: `0x1800028d1`
- end: `0x1800028dd`
- name: `__imp_load_NCryptOpenStorageProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000282e`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x1800028d1`

## pseudocode

```c
__int64 load_NCryptOpenStorageProvider()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x1800028d1  lea     rax, __imp_NCryptOpenStorageProvider
0x1800028d8  jmp     __tailMerge_ncrypt_dll
```
