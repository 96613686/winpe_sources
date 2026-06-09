# __imp_load_MsiAdvertiseProductExW

- ea: `0x140003a15`
- end: `0x140003a21`
- name: `__imp_load_MsiAdvertiseProductExW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiAdvertiseProductExW` at `0x140003a15`

## pseudocode

```c
__int64 load_MsiAdvertiseProductExW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x140003a15  lea     rax, __imp_MsiAdvertiseProductExW
0x140003a1c  jmp     __tailMerge_msi_dll
```
