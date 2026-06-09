# __imp_load_?DmGetCurrentUserSid@@YAJPEAPEAG@Z

- ea: `0x180004750`
- end: `0x18000475c`
- name: `__imp_load_?DmGetCurrentUserSid@@YAJPEAPEAG@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800045f9`

## import_xrefs

- `DMCmnUtils!DmGetCurrentUserSid` at `0x180004750`

## pseudocode

```c
__int64 load__DmGetCurrentUserSid__YAJPEAPEAG_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x180004750  lea     rax, __imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x180004757  jmp     __tailMerge_dmcmnutils_dll
```
