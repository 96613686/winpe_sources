# __imp_load_EtwLogSysConfigRundown

- ea: `0x180001fbd`
- end: `0x180001fc9`
- name: `__imp_load_EtwLogSysConfigRundown`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180001f3e`

## import_xrefs

- `ext-ms-win-eventing-rundown-l1-1-0!EtwLogSysConfigRundown` at `0x180001fbd`

## pseudocode

```c
__int64 load_EtwLogSysConfigRundown()
{
  return _tailMerge_ext_ms_win_eventing_rundown_l1_1_0_dll();
}

```

## disassembly

```asm
0x180001fbd  lea     rax, __imp_EtwLogSysConfigRundown
0x180001fc4  jmp     __tailMerge_ext_ms_win_eventing_rundown_l1_1_0_dll
```
