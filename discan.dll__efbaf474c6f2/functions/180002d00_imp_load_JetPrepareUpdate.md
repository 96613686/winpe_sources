# __imp_load_JetPrepareUpdate

- ea: `0x180002d00`
- end: `0x180002d0c`
- name: `__imp_load_JetPrepareUpdate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002abf`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x180002d00`

## pseudocode

```c
__int64 load_JetPrepareUpdate()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002d00  lea     rax, __imp_JetPrepareUpdate
0x180002d07  jmp     __tailMerge_esent_dll
```
