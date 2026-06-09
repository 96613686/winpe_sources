# __imp_load_UpdateWindow

- ea: `0x18000400a`
- end: `0x180004016`
- name: `__imp_load_UpdateWindow`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180003ddb`

## import_xrefs

- `USER32!UpdateWindow` at `0x18000400a`

## pseudocode

```c
__int64 load_UpdateWindow()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x18000400a  lea     rax, __imp_UpdateWindow
0x180004011  jmp     __tailMerge_user32_dll
```
