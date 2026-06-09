# __imp_load_CACloseCertType

- ea: `0x180006468`
- end: `0x180006474`
- name: `__imp_load_CACloseCertType`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000637d`

## import_xrefs

- `certca!__imp_CACloseCertType` at `0x180006468`

## pseudocode

```c
__int64 load_CACloseCertType()
{
  return _tailMerge_certca_dll();
}

```

## disassembly

```asm
0x180006468  lea     rax, __imp_CACloseCertType
0x18000646f  jmp     __tailMerge_certca_dll
```
