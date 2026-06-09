# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x1800022df`
- end: `0x1800022eb`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002260`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800022df`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x1800022df  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x1800022e6  jmp     __tailMerge_bcrypt_dll
```
