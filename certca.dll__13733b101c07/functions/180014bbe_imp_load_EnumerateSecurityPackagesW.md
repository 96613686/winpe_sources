# __imp_load_EnumerateSecurityPackagesW

- ea: `0x180014bbe`
- end: `0x180014bca`
- name: `__imp_load_EnumerateSecurityPackagesW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800147fb`

## import_xrefs

- `SspiCli!EnumerateSecurityPackagesW` at `0x180014bbe`

## pseudocode

```c
__int64 load_EnumerateSecurityPackagesW()
{
  return _tailMerge_sspicli_dll();
}

```

## disassembly

```asm
0x180014bbe  lea     rax, __imp_EnumerateSecurityPackagesW
0x180014bc5  jmp     __tailMerge_sspicli_dll
```
