# __imp_load_GetNextAppContainerSid

- ea: `0x180012081`
- end: `0x18001208d`
- name: `__imp_load_GetNextAppContainerSid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180011fa8`

## import_xrefs

- `profapi!__imp_GetNextAppContainerSid` at `0x180012081`

## pseudocode

```c
__int64 load_GetNextAppContainerSid()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x180012081  lea     rax, __imp_GetNextAppContainerSid
0x180012088  jmp     __tailMerge_profapi_dll
```
