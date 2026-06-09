# __imp_load_JetRollback

- ea: `0x18000cf87`
- end: `0x18000cf93`
- name: `__imp_load_JetRollback`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000ccec`

## import_xrefs

- `ESENT!JetRollback` at `0x18000cf87`

## pseudocode

```c
__int64 load_JetRollback()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x18000cf87  lea     rax, __imp_JetRollback
0x18000cf8e  jmp     __tailMerge_esent_dll
```
