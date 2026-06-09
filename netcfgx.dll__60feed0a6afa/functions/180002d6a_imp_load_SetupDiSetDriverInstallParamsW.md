# __imp_load_SetupDiSetDriverInstallParamsW

- ea: `0x180002d6a`
- end: `0x180002d76`
- name: `__imp_load_SetupDiSetDriverInstallParamsW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002afd`

## import_xrefs

- `SETUPAPI!SetupDiSetDriverInstallParamsW` at `0x180002d6a`

## pseudocode

```c
__int64 load_SetupDiSetDriverInstallParamsW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180002d6a  lea     rax, __imp_SetupDiSetDriverInstallParamsW
0x180002d71  jmp     __tailMerge_setupapi_dll
```
