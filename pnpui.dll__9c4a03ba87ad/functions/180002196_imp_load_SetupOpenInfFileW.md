# __imp_load_SetupOpenInfFileW

- ea: `0x180002196`
- end: `0x1800021a2`
- name: `__imp_load_SetupOpenInfFileW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800020bd`

## import_xrefs

- `SETUPAPI!SetupOpenInfFileW` at `0x180002196`

## pseudocode

```c
__int64 load_SetupOpenInfFileW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180002196  lea     rax, __imp_SetupOpenInfFileW
0x18000219d  jmp     __tailMerge_setupapi_dll
```
