# __imp_load_DevObjCreateDeviceInfoList

- ea: `0x1800064dc`
- end: `0x1800064e8`
- name: `__imp_load_DevObjCreateDeviceInfoList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006427`

## import_xrefs

- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800064dc`

## pseudocode

```c
__int64 load_DevObjCreateDeviceInfoList()
{
  return _tailMerge_devobj_dll();
}

```

## disassembly

```asm
0x1800064dc  lea     rax, __imp_DevObjCreateDeviceInfoList
0x1800064e3  jmp     __tailMerge_devobj_dll
```
