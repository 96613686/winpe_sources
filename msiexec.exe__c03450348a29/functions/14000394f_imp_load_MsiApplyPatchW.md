# __imp_load_MsiApplyPatchW

- ea: `0x14000394f`
- end: `0x14000395b`
- name: `__imp_load_MsiApplyPatchW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiApplyPatchW` at `0x14000394f`

## pseudocode

```c
__int64 load_MsiApplyPatchW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x14000394f  lea     rax, __imp_MsiApplyPatchW
0x140003956  jmp     __tailMerge_msi_dll
```
