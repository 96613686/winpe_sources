# __imp_load_?DmGetAadDeviceTokenWithDiscovery@@YAJPEBG00PEAPEAG11@Z

- ea: `0x180004807`
- end: `0x180004813`
- name: `__imp_load_?DmGetAadDeviceTokenWithDiscovery@@YAJPEBG00PEAPEAG11@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003601`

## import_xrefs

- `DMCmnUtils!DmGetAadDeviceTokenWithDiscovery` at `0x180004807`

## pseudocode

```c
__int64 load__DmGetAadDeviceTokenWithDiscovery__YAJPEBG00PEAPEAG11_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x180004807  lea     rax, __imp_?DmGetAadDeviceTokenWithDiscovery@@YAJPEBG00PEAPEAG11@Z; DmGetAadDeviceTokenWithDiscovery(ushort const *,ushort const *,ushort const *,ushort * *,ushort * *,ushort * *)
0x18000480e  jmp     __tailMerge_dmcmnutils_dll
```
