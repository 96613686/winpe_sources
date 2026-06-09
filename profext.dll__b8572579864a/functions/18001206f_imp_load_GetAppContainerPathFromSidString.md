# __imp_load_GetAppContainerPathFromSidString

- ea: `0x18001206f`
- end: `0x18001207b`
- name: `__imp_load_GetAppContainerPathFromSidString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180011fa8`

## import_xrefs

- `profapi!__imp_GetAppContainerPathFromSidString` at `0x18001206f`

## pseudocode

```c
__int64 load_GetAppContainerPathFromSidString()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x18001206f  lea     rax, __imp_GetAppContainerPathFromSidString
0x180012076  jmp     __tailMerge_profapi_dll
```
