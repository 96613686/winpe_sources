# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x18001a59b`
- end: `0x18001a5a7`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001a4e6`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001a59b`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18001a59b  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x18001a5a2  jmp     __tailMerge_bcrypt_dll
```
