# __imp_load_SetupWriteTextLog

- ea: `0x18000214e`
- end: `0x18000215a`
- name: `__imp_load_SetupWriteTextLog`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800020bd`

## import_xrefs

- `SETUPAPI!SetupWriteTextLog` at `0x18000214e`

## pseudocode

```c
__int64 load_SetupWriteTextLog()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x18000214e  lea     rax, __imp_SetupWriteTextLog
0x180002155  jmp     __tailMerge_setupapi_dll
```
