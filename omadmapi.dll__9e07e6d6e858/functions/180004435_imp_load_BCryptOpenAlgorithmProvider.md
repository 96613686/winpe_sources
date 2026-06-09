# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x180004435`
- end: `0x180004441`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800043a4`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180004435`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180004435  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x18000443c  jmp     __tailMerge_bcrypt_dll
```
