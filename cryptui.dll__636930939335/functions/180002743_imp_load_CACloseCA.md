# __imp_load_CACloseCA

- ea: `0x180002743`
- end: `0x18000274f`
- name: `__imp_load_CACloseCA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002658`

## import_xrefs

- `certca!__imp_CACloseCA` at `0x180002743`

## pseudocode

```c
__int64 load_CACloseCA()
{
  return _tailMerge_certca_dll();
}

```

## disassembly

```asm
0x180002743  lea     rax, __imp_CACloseCA
0x18000274a  jmp     __tailMerge_certca_dll
```
