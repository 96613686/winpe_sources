# __imp_load_MsiGetSummaryInformationW

- ea: `0x140003961`
- end: `0x14000396d`
- name: `__imp_load_MsiGetSummaryInformationW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiGetSummaryInformationW` at `0x140003961`

## pseudocode

```c
__int64 load_MsiGetSummaryInformationW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x140003961  lea     rax, __imp_MsiGetSummaryInformationW
0x140003968  jmp     __tailMerge_msi_dll
```
