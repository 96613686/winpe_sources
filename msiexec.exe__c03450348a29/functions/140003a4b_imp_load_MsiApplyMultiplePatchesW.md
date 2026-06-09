# __imp_load_MsiApplyMultiplePatchesW

- ea: `0x140003a4b`
- end: `0x140003a57`
- name: `__imp_load_MsiApplyMultiplePatchesW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiApplyMultiplePatchesW` at `0x140003a4b`

## pseudocode

```c
__int64 load_MsiApplyMultiplePatchesW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x140003a4b  lea     rax, __imp_MsiApplyMultiplePatchesW
0x140003a52  jmp     __tailMerge_msi_dll
```
