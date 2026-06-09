# __imp_load_CreateWindowExW

- ea: `0x1800020ed`
- end: `0x1800020f9`
- name: `__imp_load_CreateWindowExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001d2f`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800020ed`

## pseudocode

```c
__int64 load_CreateWindowExW()
{
  return _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800020ed  lea     rax, __imp_CreateWindowExW
0x1800020f4  jmp     __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll
```
