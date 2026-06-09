# __imp_load_MsiGetProductCodeFromPackageCodeW

- ea: `0x140003985`
- end: `0x140003991`
- name: `__imp_load_MsiGetProductCodeFromPackageCodeW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiGetProductCodeFromPackageCodeW` at `0x140003985`

## pseudocode

```c
__int64 load_MsiGetProductCodeFromPackageCodeW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x140003985  lea     rax, __imp_MsiGetProductCodeFromPackageCodeW
0x14000398c  jmp     __tailMerge_msi_dll
```
