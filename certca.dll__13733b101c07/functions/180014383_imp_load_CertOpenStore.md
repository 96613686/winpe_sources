# __imp_load_CertOpenStore

- ea: `0x180014383`
- end: `0x18001438f`
- name: `__imp_load_CertOpenStore`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001408b`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x180014383`

## pseudocode

```c
__int64 load_CertOpenStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180014383  lea     rax, __imp_CertOpenStore
0x18001438a  jmp     __tailMerge_crypt32_dll
```
