# __imp_load_?DmGetUserTokenFromSid@@YAJPEBGPEAPEAXPEAK@Z

- ea: `0x18000473e`
- end: `0x18000474a`
- name: `__imp_load_?DmGetUserTokenFromSid@@YAJPEBGPEAPEAXPEAK@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x1800045f9`

## import_xrefs

- `DMCmnUtils!DmGetUserTokenFromSid` at `0x18000473e`

## pseudocode

```c
__int64 load__DmGetUserTokenFromSid__YAJPEBGPEAPEAXPEAK_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x18000473e  lea     rax, __imp_?DmGetUserTokenFromSid@@YAJPEBGPEAPEAXPEAK@Z; DmGetUserTokenFromSid(ushort const *,void * *,ulong *)
0x180004745  jmp     __tailMerge_dmcmnutils_dll
```
