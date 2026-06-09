# __imp_load_EdpDllCredSvcControl

- ea: `0x180002615`
- end: `0x180002621`
- name: `__imp_load_EdpDllCredSvcControl`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllCredSvcControl` at `0x180002615`

## pseudocode

```c
__int64 load_EdpDllCredSvcControl()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002615  lea     rax, __imp_EdpDllCredSvcControl
0x18000261c  jmp     __tailMerge_efscore_dll
```
