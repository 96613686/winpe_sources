# __imp_load_DevObjCreateDeviceInfoList

- ea: `0x180015b1b`
- end: `0x180015b27`
- name: `__imp_load_DevObjCreateDeviceInfoList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180015a66`

## import_xrefs

- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180015b1b`

## pseudocode

```c
__int64 load_DevObjCreateDeviceInfoList()
{
  return _tailMerge_devobj_dll();
}

```

## disassembly

```asm
0x180015b1b  lea     rax, __imp_DevObjCreateDeviceInfoList
0x180015b22  jmp     __tailMerge_devobj_dll
```
