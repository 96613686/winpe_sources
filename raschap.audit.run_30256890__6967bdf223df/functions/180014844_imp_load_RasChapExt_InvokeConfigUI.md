# __imp_load_RasChapExt_InvokeConfigUI

- ea: `0x180014844`
- end: `0x180014850`
- name: `__imp_load_RasChapExt_InvokeConfigUI`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180014739`

## import_xrefs

- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_InvokeConfigUI` at `0x180014844`

## pseudocode

```c
__int64 load_RasChapExt_InvokeConfigUI()
{
  return _tailMerge_ext_ms_win_raschapext_eap_l1_1_0_dll();
}

```

## disassembly

```asm
0x180014844  lea     rax, __imp_RasChapExt_InvokeConfigUI
0x18001484b  jmp     __tailMerge_ext_ms_win_raschapext_eap_l1_1_0_dll
```
