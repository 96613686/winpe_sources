# __imp_load_JetRollback

- ea: `0x180002c70`
- end: `0x180002c7c`
- name: `__imp_load_JetRollback`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002abf`

## import_xrefs

- `ESENT!JetRollback` at `0x180002c70`

## pseudocode

```c
__int64 load_JetRollback()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002c70  lea     rax, __imp_JetRollback
0x180002c77  jmp     __tailMerge_esent_dll
```
