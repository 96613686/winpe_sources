# __imp_load_SetupDiGetDriverInstallParamsW

- ea: `0x180002d46`
- end: `0x180002d52`
- name: `__imp_load_SetupDiGetDriverInstallParamsW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002afd`

## import_xrefs

- `SETUPAPI!SetupDiGetDriverInstallParamsW` at `0x180002d46`

## pseudocode

```c
__int64 load_SetupDiGetDriverInstallParamsW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180002d46  lea     rax, __imp_SetupDiGetDriverInstallParamsW
0x180002d4d  jmp     __tailMerge_setupapi_dll
```
