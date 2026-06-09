# __imp_load_EdpDllCredSvcControl

- ea: `0x1800025e5`
- end: `0x1800025f1`
- name: `__imp_load_EdpDllCredSvcControl`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllCredSvcControl` at `0x1800025e5`

## pseudocode

```c
__int64 load_EdpDllCredSvcControl()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800025e5  lea     rax, __imp_EdpDllCredSvcControl
0x1800025ec  jmp     __tailMerge_efscore_dll
```
