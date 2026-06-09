# __imp_load_JetUpdate

- ea: `0x18000cf75`
- end: `0x18000cf81`
- name: `__imp_load_JetUpdate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000ccec`

## import_xrefs

- `ESENT!JetUpdate` at `0x18000cf75`

## pseudocode

```c
__int64 load_JetUpdate()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x18000cf75  lea     rax, __imp_JetUpdate
0x18000cf7c  jmp     __tailMerge_esent_dll
```
