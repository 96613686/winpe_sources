# __imp_load_QuerySecurityPackageInfoW

- ea: `0x180021ad9`
- end: `0x180021ae5`
- name: `__imp_load_QuerySecurityPackageInfoW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180021a5a`

## import_xrefs

- `SspiCli!QuerySecurityPackageInfoW` at `0x180021ad9`

## pseudocode

```c
__int64 load_QuerySecurityPackageInfoW()
{
  return _tailMerge_sspicli_dll();
}

```

## disassembly

```asm
0x180021ad9  lea     rax, __imp_QuerySecurityPackageInfoW
0x180021ae0  jmp     __tailMerge_sspicli_dll
```
