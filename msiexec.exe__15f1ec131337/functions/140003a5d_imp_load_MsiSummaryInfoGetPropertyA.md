# __imp_load_MsiSummaryInfoGetPropertyA

- ea: `0x140003a5d`
- end: `0x140003a69`
- name: `__imp_load_MsiSummaryInfoGetPropertyA`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiSummaryInfoGetPropertyA` at `0x140003a5d`

## pseudocode

```c
__int64 load_MsiSummaryInfoGetPropertyA()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x140003a5d  lea     rax, __imp_MsiSummaryInfoGetPropertyA
0x140003a64  jmp     __tailMerge_msi_dll
```
