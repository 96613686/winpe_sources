# __imp_load_DeleteSecurityContext

- ea: `0x180014c3c`
- end: `0x180014c48`
- name: `__imp_load_DeleteSecurityContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800147fb`

## import_xrefs

- `SspiCli!DeleteSecurityContext` at `0x180014c3c`

## pseudocode

```c
__int64 load_DeleteSecurityContext()
{
  return _tailMerge_sspicli_dll();
}

```

## disassembly

```asm
0x180014c3c  lea     rax, __imp_DeleteSecurityContext
0x180014c43  jmp     __tailMerge_sspicli_dll
```
