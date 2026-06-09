# __imp_load_TreeResetNamedSecurityInfoW

- ea: `0x180012759`
- end: `0x180012765`
- name: `__imp_load_TreeResetNamedSecurityInfoW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800126da`

## import_xrefs

- `ext-ms-win-advapi32-ntmarta-l1-1-0!TreeResetNamedSecurityInfoW` at `0x180012759`

## pseudocode

```c
__int64 load_TreeResetNamedSecurityInfoW()
{
  return _tailMerge_ext_ms_win_advapi32_ntmarta_l1_1_0_dll();
}

```

## disassembly

```asm
0x180012759  lea     rax, __imp_TreeResetNamedSecurityInfoW
0x180012760  jmp     __tailMerge_ext_ms_win_advapi32_ntmarta_l1_1_0_dll
```
