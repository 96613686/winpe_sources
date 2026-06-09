# __imp_load_AccTreeResetNamedSecurityInfo

- ea: `0x18001266e`
- end: `0x18001267a`
- name: `__imp_load_AccTreeResetNamedSecurityInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800125ef`

## import_xrefs

- `NTMARTA!AccTreeResetNamedSecurityInfo` at `0x18001266e`

## pseudocode

```c
__int64 load_AccTreeResetNamedSecurityInfo()
{
  return _tailMerge_ntmarta_dll();
}

```

## disassembly

```asm
0x18001266e  lea     rax, __imp_AccTreeResetNamedSecurityInfo
0x180012675  jmp     __tailMerge_ntmarta_dll
```
