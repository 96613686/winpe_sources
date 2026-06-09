# __imp_load_SetupDiOpenDevRegKey

- ea: `0x180002cec`
- end: `0x180002cf8`
- name: `__imp_load_SetupDiOpenDevRegKey`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002afd`

## import_xrefs

- `SETUPAPI!SetupDiOpenDevRegKey` at `0x180002cec`

## pseudocode

```c
__int64 load_SetupDiOpenDevRegKey()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180002cec  lea     rax, __imp_SetupDiOpenDevRegKey
0x180002cf3  jmp     __tailMerge_setupapi_dll
```
