# __imp_load_Tbsip_Submit_Command_NonBlocking

- ea: `0x180003ee0`
- end: `0x180003eec`
- name: `__imp_load_Tbsip_Submit_Command_NonBlocking`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003e19`

## import_xrefs

- `tbs!Tbsip_Submit_Command_NonBlocking` at `0x180003ee0`

## pseudocode

```c
__int64 load_Tbsip_Submit_Command_NonBlocking()
{
  return _tailMerge_tbs_dll();
}

```

## disassembly

```asm
0x180003ee0  lea     rax, __imp_Tbsip_Submit_Command_NonBlocking
0x180003ee7  jmp     __tailMerge_tbs_dll
```
