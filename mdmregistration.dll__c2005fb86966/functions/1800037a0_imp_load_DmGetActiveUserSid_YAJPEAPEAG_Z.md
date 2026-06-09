# __imp_load_?DmGetActiveUserSid@@YAJPEAPEAG@Z

- ea: `0x1800037a0`
- end: `0x1800037ac`
- name: `__imp_load_?DmGetActiveUserSid@@YAJPEAPEAG@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003601`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x1800037a0`

## pseudocode

```c
__int64 load__DmGetActiveUserSid__YAJPEAPEAG_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x1800037a0  lea     rax, __imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800037a7  jmp     __tailMerge_dmcmnutils_dll
```
