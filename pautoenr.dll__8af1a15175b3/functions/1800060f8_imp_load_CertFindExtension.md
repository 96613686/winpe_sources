# __imp_load_CertFindExtension

- ea: `0x1800060f8`
- end: `0x180006104`
- name: `__imp_load_CertFindExtension`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005caf`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x1800060f8`

## pseudocode

```c
__int64 load_CertFindExtension()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x1800060f8  lea     rax, __imp_CertFindExtension
0x1800060ff  jmp     __tailMerge_crypt32_dll
```
