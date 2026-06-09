# __imp_load_MsiSetExternalUIA

- ea: `0x140003a27`
- end: `0x140003a33`
- name: `__imp_load_MsiSetExternalUIA`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiSetExternalUIA` at `0x140003a27`

## pseudocode

```c
__int64 load_MsiSetExternalUIA()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x140003a27  lea     rax, __imp_MsiSetExternalUIA
0x140003a2e  jmp     __tailMerge_msi_dll
```
