# __imp_load_CertDeleteCTLFromStore

- ea: `0x180014bac`
- end: `0x180014bb8`
- name: `__imp_load_CertDeleteCTLFromStore`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001408b`

## import_xrefs

- `CRYPT32!CertDeleteCTLFromStore` at `0x180014bac`

## pseudocode

```c
__int64 load_CertDeleteCTLFromStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180014bac  lea     rax, __imp_CertDeleteCTLFromStore
0x180014bb3  jmp     __tailMerge_crypt32_dll
```
