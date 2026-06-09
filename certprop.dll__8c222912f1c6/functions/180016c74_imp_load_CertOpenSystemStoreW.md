# __imp_load_CertOpenSystemStoreW

- ea: `0x180016c74`
- end: `0x180016c80`
- name: `__imp_load_CertOpenSystemStoreW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180016b22`

## import_xrefs

- `CRYPT32!CertOpenSystemStoreW` at `0x180016c74`

## pseudocode

```c
__int64 load_CertOpenSystemStoreW()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180016c74  lea     rax, __imp_CertOpenSystemStoreW
0x180016c7b  jmp     __tailMerge_crypt32_dll
```
