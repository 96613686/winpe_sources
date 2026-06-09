# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x1800055f7`
- end: `0x180005603`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800054c4`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800055f7`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x1800055f7  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x1800055fe  jmp     __tailMerge_bcrypt_dll
```
