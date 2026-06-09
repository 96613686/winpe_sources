# __imp_load_RegDeleteKeyA

- ea: `0x180001390`
- end: `0x18000139c`
- name: `__imp_load_RegDeleteKeyA`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180001311`

## import_xrefs

- `ADVAPI32!RegDeleteKeyA` at `0x180001390`

## pseudocode

```c
__int64 load_RegDeleteKeyA()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180001390  lea     rax, __imp_RegDeleteKeyA
0x180001397  jmp     __tailMerge_advapi32_dll
```
