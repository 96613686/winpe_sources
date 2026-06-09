# __imp_load_SetupDiCallClassInstaller

- ea: `0x180002d49`
- end: `0x180002d55`
- name: `__imp_load_SetupDiCallClassInstaller`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002c94`

## import_xrefs

- `SETUPAPI!SetupDiCallClassInstaller` at `0x180002d49`

## pseudocode

```c
__int64 load_SetupDiCallClassInstaller()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180002d49  lea     rax, __imp_SetupDiCallClassInstaller
0x180002d50  jmp     __tailMerge_setupapi_dll
```
