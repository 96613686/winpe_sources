# __imp_load_NCryptCreatePersistedKey

- ea: `0x180005d4a`
- end: `0x180005d56`
- name: `__imp_load_NCryptCreatePersistedKey`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800059d4`

## import_xrefs

- `ncrypt!NCryptCreatePersistedKey` at `0x180005d4a`

## pseudocode

```c
__int64 load_NCryptCreatePersistedKey()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x180005d4a  lea     rax, __imp_NCryptCreatePersistedKey
0x180005d51  jmp     __tailMerge_ncrypt_dll
```
