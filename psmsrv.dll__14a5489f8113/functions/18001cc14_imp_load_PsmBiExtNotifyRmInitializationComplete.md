# __imp_load_PsmBiExtNotifyRmInitializationComplete

- ea: `0x18001cc14`
- end: `0x18001cc20`
- name: `__imp_load_PsmBiExtNotifyRmInitializationComplete`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001ca7a`

## import_xrefs

- `ext-ms-win-core-psm-bi-l1-2-0!PsmBiExtNotifyRmInitializationComplete` at `0x18001cc14`

## pseudocode

```c
__int64 load_PsmBiExtNotifyRmInitializationComplete()
{
  return _tailMerge_ext_ms_win_core_psm_bi_l1_2_0_dll();
}

```

## disassembly

```asm
0x18001cc14  lea     rax, __imp_PsmBiExtNotifyRmInitializationComplete
0x18001cc1b  jmp     __tailMerge_ext_ms_win_core_psm_bi_l1_2_0_dll
```
