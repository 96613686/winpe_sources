# __imp_load_AcceptSecurityContext

- ea: `0x180014c18`
- end: `0x180014c24`
- name: `__imp_load_AcceptSecurityContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800147fb`

## import_xrefs

- `SspiCli!AcceptSecurityContext` at `0x180014c18`

## pseudocode

```c
__int64 load_AcceptSecurityContext()
{
  return _tailMerge_sspicli_dll();
}

```

## disassembly

```asm
0x180014c18  lea     rax, __imp_AcceptSecurityContext
0x180014c1f  jmp     __tailMerge_sspicli_dll
```
