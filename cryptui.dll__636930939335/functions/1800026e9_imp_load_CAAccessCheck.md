# __imp_load_CAAccessCheck

- ea: `0x1800026e9`
- end: `0x1800026f5`
- name: `__imp_load_CAAccessCheck`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002658`

## import_xrefs

- `certca!__imp_CAAccessCheck` at `0x1800026e9`

## pseudocode

```c
__int64 load_CAAccessCheck()
{
  return _tailMerge_certca_dll();
}

```

## disassembly

```asm
0x1800026e9  lea     rax, __imp_CAAccessCheck
0x1800026f0  jmp     __tailMerge_certca_dll
```
