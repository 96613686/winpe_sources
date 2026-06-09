# __imp_load_DevObjOpenDeviceInfo

- ea: `0x18004dbcd`
- end: `0x18004dbd9`
- name: `__imp_load_DevObjOpenDeviceInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004db4e`

## import_xrefs

- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18004dbcd`

## pseudocode

```c
__int64 load_DevObjOpenDeviceInfo()
{
  return _tailMerge_devobj_dll();
}

```

## disassembly

```asm
0x18004dbcd  lea     rax, __imp_DevObjOpenDeviceInfo
0x18004dbd4  jmp     __tailMerge_devobj_dll
```
