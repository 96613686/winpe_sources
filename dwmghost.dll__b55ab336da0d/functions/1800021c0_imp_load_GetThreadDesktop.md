# __imp_load_GetThreadDesktop

- ea: `0x1800021c0`
- end: `0x1800021cc`
- name: `__imp_load_GetThreadDesktop`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000211d`

## import_xrefs

- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x1800021c0`

## pseudocode

```c
__int64 load_GetThreadDesktop()
{
  return _tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800021c0  lea     rax, __imp_GetThreadDesktop
0x1800021c7  jmp     __tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll
```
