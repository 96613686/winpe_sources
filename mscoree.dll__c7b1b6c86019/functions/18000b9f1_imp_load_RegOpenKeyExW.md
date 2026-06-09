# __imp_load_RegOpenKeyExW

- ea: `0x18000b9f1`
- end: `0x18000b9fd`
- name: `__imp_load_RegOpenKeyExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000b972`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000b9f1`

## pseudocode

```c
__int64 load_RegOpenKeyExW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000b9f1  lea     rax, __imp_RegOpenKeyExW
0x18000b9f8  jmp     __tailMerge_advapi32_dll
```
