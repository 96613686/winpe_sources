# __imp_load_CertFindExtension

- ea: `0x180014249`
- end: `0x180014255`
- name: `__imp_load_CertFindExtension`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001408b`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x180014249`

## pseudocode

```c
__int64 load_CertFindExtension()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180014249  lea     rax, __imp_CertFindExtension
0x180014250  jmp     __tailMerge_crypt32_dll
```
