# __imp_load_SetupDiGetClassInstallParamsW

- ea: `0x180002d10`
- end: `0x180002d1c`
- name: `__imp_load_SetupDiGetClassInstallParamsW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002afd`

## import_xrefs

- `SETUPAPI!SetupDiGetClassInstallParamsW` at `0x180002d10`

## pseudocode

```c
__int64 load_SetupDiGetClassInstallParamsW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180002d10  lea     rax, __imp_SetupDiGetClassInstallParamsW
0x180002d17  jmp     __tailMerge_setupapi_dll
```
