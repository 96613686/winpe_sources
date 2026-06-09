# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x18000230f`
- end: `0x18000231b`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002290`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000230f`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18000230f  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x180002316  jmp     __tailMerge_bcrypt_dll
```
