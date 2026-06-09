# __imp_load_MsiSetInternalUI

- ea: `0x140003a81`
- end: `0x140003a8d`
- name: `__imp_load_MsiSetInternalUI`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiSetInternalUI` at `0x140003a81`

## pseudocode

```c
__int64 load_MsiSetInternalUI()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x140003a81  lea     rax, __imp_MsiSetInternalUI
0x140003a88  jmp     __tailMerge_msi_dll
```
