# __imp_load_PfRpcSendCommand

- ea: `0x18005872c`
- end: `0x180058738`
- name: `__imp_load_PfRpcSendCommand`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800586ad`

## import_xrefs

- `ext-ms-win-sysmain-pfapi-l1-1-0!PfRpcSendCommand` at `0x18005872c`

## pseudocode

```c
__int64 load_PfRpcSendCommand()
{
  return _tailMerge_ext_ms_win_sysmain_pfapi_l1_1_0_dll();
}

```

## disassembly

```asm
0x18005872c  lea     rax, __imp_PfRpcSendCommand
0x180058733  jmp     __tailMerge_ext_ms_win_sysmain_pfapi_l1_1_0_dll
```
