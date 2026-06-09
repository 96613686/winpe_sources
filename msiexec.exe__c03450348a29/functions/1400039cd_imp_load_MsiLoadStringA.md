# __imp_load_MsiLoadStringA

- ea: `0x1400039cd`
- end: `0x1400039d9`
- name: `__imp_load_MsiLoadStringA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiLoadStringA` at `0x1400039cd`

## pseudocode

```c
__int64 load_MsiLoadStringA()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x1400039cd  lea     rax, __imp_MsiLoadStringA
0x1400039d4  jmp     __tailMerge_msi_dll
```
