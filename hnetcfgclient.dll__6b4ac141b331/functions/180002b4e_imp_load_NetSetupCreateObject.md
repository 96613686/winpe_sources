# __imp_load_NetSetupCreateObject

- ea: `0x180002b4e`
- end: `0x180002b5a`
- name: `__imp_load_NetSetupCreateObject`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002aab`

## import_xrefs

- `NetSetupApi!NetSetupCreateObject` at `0x180002b4e`

## pseudocode

```c
__int64 load_NetSetupCreateObject()
{
  return _tailMerge_netsetupapi_dll();
}

```

## disassembly

```asm
0x180002b4e  lea     rax, __imp_NetSetupCreateObject
0x180002b55  jmp     __tailMerge_netsetupapi_dll
```
