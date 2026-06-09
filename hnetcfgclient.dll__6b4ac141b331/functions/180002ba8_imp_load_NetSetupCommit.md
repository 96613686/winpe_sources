# __imp_load_NetSetupCommit

- ea: `0x180002ba8`
- end: `0x180002bb4`
- name: `__imp_load_NetSetupCommit`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002aab`

## import_xrefs

- `NetSetupApi!NetSetupCommit` at `0x180002ba8`

## pseudocode

```c
__int64 load_NetSetupCommit()
{
  return _tailMerge_netsetupapi_dll();
}

```

## disassembly

```asm
0x180002ba8  lea     rax, __imp_NetSetupCommit
0x180002baf  jmp     __tailMerge_netsetupapi_dll
```
