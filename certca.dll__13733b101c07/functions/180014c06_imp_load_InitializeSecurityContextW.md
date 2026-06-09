# __imp_load_InitializeSecurityContextW

- ea: `0x180014c06`
- end: `0x180014c12`
- name: `__imp_load_InitializeSecurityContextW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800147fb`

## import_xrefs

- `SspiCli!InitializeSecurityContextW` at `0x180014c06`

## pseudocode

```c
__int64 load_InitializeSecurityContextW()
{
  return _tailMerge_sspicli_dll();
}

```

## disassembly

```asm
0x180014c06  lea     rax, __imp_InitializeSecurityContextW
0x180014c0d  jmp     __tailMerge_sspicli_dll
```
