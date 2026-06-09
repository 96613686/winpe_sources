# __imp_load_?DmGetCurrentUserSid@@YAJPEAPEAG@Z

- ea: `0x180001edf`
- end: `0x180001eeb`
- name: `__imp_load_?DmGetCurrentUserSid@@YAJPEAPEAG@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001e60`

## import_xrefs

- `DMCmnUtils!DmGetCurrentUserSid` at `0x180001edf`

## pseudocode

```c
__int64 load__DmGetCurrentUserSid__YAJPEAPEAG_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x180001edf  lea     rax, __imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x180001ee6  jmp     __tailMerge_dmcmnutils_dll
```
