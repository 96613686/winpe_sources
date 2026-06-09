# __imp_load_?DmGetAadDeviceToken@@YAJPEBG00PEAPEAG@Z

- ea: `0x180004873`
- end: `0x18000487f`
- name: `__imp_load_?DmGetAadDeviceToken@@YAJPEBG00PEAPEAG@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003601`

## import_xrefs

- `DMCmnUtils!DmGetAadDeviceToken` at `0x180004873`

## pseudocode

```c
__int64 load__DmGetAadDeviceToken__YAJPEBG00PEAPEAG_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x180004873  lea     rax, __imp_?DmGetAadDeviceToken@@YAJPEBG00PEAPEAG@Z; DmGetAadDeviceToken(ushort const *,ushort const *,ushort const *,ushort * *)
0x18000487a  jmp     __tailMerge_dmcmnutils_dll
```
