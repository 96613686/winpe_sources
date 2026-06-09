# __imp_load_SetupDiSetClassInstallParamsW

- ea: `0x180002cfe`
- end: `0x180002d0a`
- name: `__imp_load_SetupDiSetClassInstallParamsW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002afd`

## import_xrefs

- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180002cfe`

## pseudocode

```c
__int64 load_SetupDiSetClassInstallParamsW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180002cfe  lea     rax, __imp_SetupDiSetClassInstallParamsW
0x180002d05  jmp     __tailMerge_setupapi_dll
```
