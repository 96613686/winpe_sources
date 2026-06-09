# __imp_load_RemovePropW

- ea: `0x18000a5e6`
- end: `0x18000a5f2`
- name: `__imp_load_RemovePropW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000a34d`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!RemovePropW` at `0x18000a5e6`

## pseudocode

```c
__int64 load_RemovePropW()
{
  return _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a5e6  lea     rax, __imp_RemovePropW
0x18000a5ed  jmp     __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll
```
