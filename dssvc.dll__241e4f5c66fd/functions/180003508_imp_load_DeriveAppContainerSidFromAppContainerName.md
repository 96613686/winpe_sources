# __imp_load_DeriveAppContainerSidFromAppContainerName

- ea: `0x180003508`
- end: `0x180003514`
- name: `__imp_load_DeriveAppContainerSidFromAppContainerName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003489`

## import_xrefs

- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x180003508`

## pseudocode

```c
__int64 load_DeriveAppContainerSidFromAppContainerName()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x180003508  lea     rax, __imp_DeriveAppContainerSidFromAppContainerName
0x18000350f  jmp     __tailMerge_userenv_dll
```
