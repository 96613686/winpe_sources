# __imp_load_NCryptOpenStorageProvider

- ea: `0x180005a53`
- end: `0x180005a5f`
- name: `__imp_load_NCryptOpenStorageProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800059d4`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x180005a53`

## pseudocode

```c
__int64 load_NCryptOpenStorageProvider()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x180005a53  lea     rax, __imp_NCryptOpenStorageProvider
0x180005a5a  jmp     __tailMerge_ncrypt_dll
```
