# __imp_load_OpenDesktopW

- ea: `0x18000224b`
- end: `0x180002257`
- name: `__imp_load_OpenDesktopW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800021cc`

## import_xrefs

- `ext-ms-win-ntuser-windowstation-l1-1-2!OpenDesktopW` at `0x18000224b`

## pseudocode

```c
__int64 load_OpenDesktopW()
{
  return _tailMerge_ext_ms_win_ntuser_windowstation_l1_1_2_dll();
}

```

## disassembly

```asm
0x18000224b  lea     rax, __imp_OpenDesktopW
0x180002252  jmp     __tailMerge_ext_ms_win_ntuser_windowstation_l1_1_2_dll
```
