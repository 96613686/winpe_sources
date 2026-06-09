# __imp_load_BCryptCreateHash

- ea: `0x1800038ed`
- end: `0x1800038f9`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000384a`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1800038ed`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x1800038ed  lea     rax, __imp_BCryptCreateHash
0x1800038f4  jmp     __tailMerge_bcrypt_dll
```
