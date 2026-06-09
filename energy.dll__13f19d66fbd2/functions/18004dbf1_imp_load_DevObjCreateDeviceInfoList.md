# __imp_load_DevObjCreateDeviceInfoList

- ea: `0x18004dbf1`
- end: `0x18004dbfd`
- name: `__imp_load_DevObjCreateDeviceInfoList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004db4e`

## import_xrefs

- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18004dbf1`

## pseudocode

```c
__int64 load_DevObjCreateDeviceInfoList()
{
  return _tailMerge_devobj_dll();
}

```

## disassembly

```asm
0x18004dbf1  lea     rax, __imp_DevObjCreateDeviceInfoList
0x18004dbf8  jmp     __tailMerge_devobj_dll
```
