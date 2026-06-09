# __imp_load_NetSetupDeleteObject

- ea: `0x180002b60`
- end: `0x180002b6c`
- name: `__imp_load_NetSetupDeleteObject`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002aab`

## import_xrefs

- `NetSetupApi!NetSetupDeleteObject` at `0x180002b60`

## pseudocode

```c
__int64 load_NetSetupDeleteObject()
{
  return _tailMerge_netsetupapi_dll();
}

```

## disassembly

```asm
0x180002b60  lea     rax, __imp_NetSetupDeleteObject
0x180002b67  jmp     __tailMerge_netsetupapi_dll
```
