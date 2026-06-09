# __imp_load_MsiGetProductInfoW

- ea: `0x1400039a9`
- end: `0x1400039b5`
- name: `__imp_load_MsiGetProductInfoW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiGetProductInfoW` at `0x1400039a9`

## pseudocode

```c
__int64 load_MsiGetProductInfoW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x1400039a9  lea     rax, __imp_MsiGetProductInfoW
0x1400039b0  jmp     __tailMerge_msi_dll
```
