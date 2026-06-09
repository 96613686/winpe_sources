# __imp_load_SetupDiSetClassInstallParamsW

- ea: `0x180002d37`
- end: `0x180002d43`
- name: `__imp_load_SetupDiSetClassInstallParamsW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002c94`

## import_xrefs

- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180002d37`

## pseudocode

```c
__int64 load_SetupDiSetClassInstallParamsW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180002d37  lea     rax, __imp_SetupDiSetClassInstallParamsW
0x180002d3e  jmp     __tailMerge_setupapi_dll
```
