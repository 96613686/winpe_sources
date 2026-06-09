# __imp_load_CACloseCertType

- ea: `0x180002779`
- end: `0x180002785`
- name: `__imp_load_CACloseCertType`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002658`

## import_xrefs

- `certca!__imp_CACloseCertType` at `0x180002779`

## pseudocode

```c
__int64 load_CACloseCertType()
{
  return _tailMerge_certca_dll();
}

```

## disassembly

```asm
0x180002779  lea     rax, __imp_CACloseCertType
0x180002780  jmp     __tailMerge_certca_dll
```
