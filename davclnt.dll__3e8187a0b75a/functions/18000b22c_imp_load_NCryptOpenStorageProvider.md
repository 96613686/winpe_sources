# __imp_load_NCryptOpenStorageProvider

- ea: `0x18000b22c`
- end: `0x18000b238`
- name: `__imp_load_NCryptOpenStorageProvider`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b1ad`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x18000b22c`

## pseudocode

```c
__int64 load_NCryptOpenStorageProvider()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x18000b22c  lea     rax, __imp_NCryptOpenStorageProvider
0x18000b233  jmp     __tailMerge_ncrypt_dll
```
