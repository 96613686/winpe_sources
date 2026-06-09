# __imp_load_JetPrepareUpdate

- ea: `0x18000cdd7`
- end: `0x18000cde3`
- name: `__imp_load_JetPrepareUpdate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000ccec`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x18000cdd7`

## pseudocode

```c
__int64 load_JetPrepareUpdate()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x18000cdd7  lea     rax, __imp_JetPrepareUpdate
0x18000cdde  jmp     __tailMerge_esent_dll
```
