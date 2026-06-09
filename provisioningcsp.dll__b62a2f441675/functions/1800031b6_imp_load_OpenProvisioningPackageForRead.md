# __imp_load_OpenProvisioningPackageForRead

- ea: `0x1800031b6`
- end: `0x1800031c2`
- name: `__imp_load_OpenProvisioningPackageForRead`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003137`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x1800031b6`

## pseudocode

```c
__int64 load_OpenProvisioningPackageForRead()
{
  return _tailMerge_provpackageapidll_dll();
}

```

## disassembly

```asm
0x1800031b6  lea     rax, __imp_OpenProvisioningPackageForRead
0x1800031bd  jmp     __tailMerge_provpackageapidll_dll
```
