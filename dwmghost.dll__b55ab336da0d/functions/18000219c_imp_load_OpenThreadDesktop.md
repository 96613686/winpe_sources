# __imp_load_OpenThreadDesktop

- ea: `0x18000219c`
- end: `0x1800021a8`
- name: `__imp_load_OpenThreadDesktop`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000211d`

## import_xrefs

- `ext-ms-win-ntuser-windowstation-l1-1-0!OpenThreadDesktop` at `0x18000219c`

## pseudocode

```c
__int64 load_OpenThreadDesktop()
{
  return _tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000219c  lea     rax, __imp_OpenThreadDesktop
0x1800021a3  jmp     __tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll
```
