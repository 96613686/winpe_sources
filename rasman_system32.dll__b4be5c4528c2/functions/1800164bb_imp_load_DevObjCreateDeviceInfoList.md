# __imp_load_DevObjCreateDeviceInfoList

- ea: `0x1800164bb`
- end: `0x1800164c7`
- name: `__imp_load_DevObjCreateDeviceInfoList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180016406`

## import_xrefs

- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800164bb`

## pseudocode

```c
__int64 load_DevObjCreateDeviceInfoList()
{
  return _tailMerge_devobj_dll();
}

```

## disassembly

```asm
0x1800164bb  lea     rax, __imp_DevObjCreateDeviceInfoList
0x1800164c2  jmp     __tailMerge_devobj_dll
```
