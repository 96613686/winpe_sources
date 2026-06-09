# __imp_load_DevObjCreateClassDeviceInfoList

- ea: `0x180001f41`
- end: `0x180001f4d`
- name: `__imp_load_DevObjCreateClassDeviceInfoList`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001eb0`

## import_xrefs

- `DEVOBJ!DevObjCreateClassDeviceInfoList` at `0x180001f41`

## pseudocode

```c
__int64 load_DevObjCreateClassDeviceInfoList()
{
  return _tailMerge_devobj_dll();
}

```

## disassembly

```asm
0x180001f41  lea     rax, __imp_DevObjCreateClassDeviceInfoList
0x180001f48  jmp     __tailMerge_devobj_dll
```
