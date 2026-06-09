# __imp_load_SxsOleAut32MapIIDToTLBPath

- ea: `0x18004ecb3`
- end: `0x18004ecbf`
- name: `__imp_load_SxsOleAut32MapIIDToTLBPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004ebfe`

## import_xrefs

- `ext-ms-win-sxs-oleautomation-l1-1-0!SxsOleAut32MapIIDToTLBPath` at `0x18004ecb3`

## pseudocode

```c
__int64 load_SxsOleAut32MapIIDToTLBPath()
{
  return _tailMerge_ext_ms_win_sxs_oleautomation_l1_1_0_dll();
}

```

## disassembly

```asm
0x18004ecb3  lea     rax, __imp_SxsOleAut32MapIIDToTLBPath
0x18004ecba  jmp     __tailMerge_ext_ms_win_sxs_oleautomation_l1_1_0_dll
```
