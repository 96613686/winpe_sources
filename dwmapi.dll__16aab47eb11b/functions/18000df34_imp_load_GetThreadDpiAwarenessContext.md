# __imp_load_GetThreadDpiAwarenessContext

- ea: `0x18000df34`
- end: `0x18000df40`
- name: `__imp_load_GetThreadDpiAwarenessContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000deb5`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x18000df34`

## pseudocode

```c
__int64 load_GetThreadDpiAwarenessContext()
{
  return _tailMerge_ext_ms_win_rtcore_ntuser_dpi_l1_2_0_dll();
}

```

## disassembly

```asm
0x18000df34  lea     rax, __imp_GetThreadDpiAwarenessContext
0x18000df3b  jmp     __tailMerge_ext_ms_win_rtcore_ntuser_dpi_l1_2_0_dll
```
