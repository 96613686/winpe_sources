# __imp_load_SHCreateShellItemArrayFromDataObject

- ea: `0x180002fd0`
- end: `0x180002fdc`
- name: `__imp_load_SHCreateShellItemArrayFromDataObject`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002f51`

## import_xrefs

- `ext-ms-win-shell-shell32-l1-2-2!SHCreateShellItemArrayFromDataObject` at `0x180002fd0`

## pseudocode

```c
__int64 load_SHCreateShellItemArrayFromDataObject()
{
  return _tailMerge_ext_ms_win_shell_shell32_l1_2_2_dll();
}

```

## disassembly

```asm
0x180002fd0  lea     rax, __imp_SHCreateShellItemArrayFromDataObject
0x180002fd7  jmp     __tailMerge_ext_ms_win_shell_shell32_l1_2_2_dll
```
