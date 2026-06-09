# __imp_load_DeriveAppContainerSidFromAppContainerName

- ea: `0x180011f35`
- end: `0x180011f41`
- name: `__imp_load_DeriveAppContainerSidFromAppContainerName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180011e86`

## import_xrefs

- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x180011f35`

## pseudocode

```c
__int64 load_DeriveAppContainerSidFromAppContainerName()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x180011f35  lea     rax, __imp_DeriveAppContainerSidFromAppContainerName
0x180011f3c  jmp     __tailMerge_userenv_dll
```
