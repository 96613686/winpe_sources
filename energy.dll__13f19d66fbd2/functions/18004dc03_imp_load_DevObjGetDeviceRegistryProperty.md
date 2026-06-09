# __imp_load_DevObjGetDeviceRegistryProperty

- ea: `0x18004dc03`
- end: `0x18004dc0f`
- name: `__imp_load_DevObjGetDeviceRegistryProperty`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18004db4e`

## import_xrefs

- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18004dc03`

## pseudocode

```c
__int64 load_DevObjGetDeviceRegistryProperty()
{
  return _tailMerge_devobj_dll();
}

```

## disassembly

```asm
0x18004dc03  lea     rax, __imp_DevObjGetDeviceRegistryProperty
0x18004dc0a  jmp     __tailMerge_devobj_dll
```
