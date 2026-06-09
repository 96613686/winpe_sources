# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x180001f33`
- end: `0x180001f3f`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001e6c`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180001f33`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180001f33  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x180001f3a  jmp     __tailMerge_bcrypt_dll
```
