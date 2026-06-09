# __imp_load_?DmInvalidateAadDeviceToken@@YAJPEBG00@Z

- ea: `0x180004861`
- end: `0x18000486d`
- name: `__imp_load_?DmInvalidateAadDeviceToken@@YAJPEBG00@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003601`

## import_xrefs

- `DMCmnUtils!DmInvalidateAadDeviceToken` at `0x180004861`

## pseudocode

```c
__int64 load__DmInvalidateAadDeviceToken__YAJPEBG00_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x180004861  lea     rax, __imp_?DmInvalidateAadDeviceToken@@YAJPEBG00@Z; DmInvalidateAadDeviceToken(ushort const *,ushort const *,ushort const *)
0x180004868  jmp     __tailMerge_dmcmnutils_dll
```
