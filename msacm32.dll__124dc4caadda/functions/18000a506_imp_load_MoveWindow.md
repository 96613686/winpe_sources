# __imp_load_MoveWindow

- ea: `0x18000a506`
- end: `0x18000a512`
- name: `__imp_load_MoveWindow`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000a487`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-1!MoveWindow` at `0x18000a506`

## pseudocode

```c
__int64 load_MoveWindow()
{
  return _tailMerge_ext_ms_win_ntuser_window_l1_1_1_dll();
}

```

## disassembly

```asm
0x18000a506  lea     rax, __imp_MoveWindow
0x18000a50d  jmp     __tailMerge_ext_ms_win_ntuser_window_l1_1_1_dll
```
