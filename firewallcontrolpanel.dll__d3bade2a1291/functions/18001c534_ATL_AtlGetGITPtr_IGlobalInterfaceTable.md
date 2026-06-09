# ATL::AtlGetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18001c534`
- end: `0x18001c58d`
- name: `?AtlGetGITPtr@ATL@@YAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `89`
- prototype: `HRESULT __fastcall(LPVOID *ppv)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c594`
- `0x18001c838`
- `0x18001e5b0`

## callees

- `0x18001c534`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c56c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c56c`

## pseudocode

```c
HRESULT __fastcall ATL::AtlGetGITPtr(LPVOID *ppv)
{
  if ( !ppv )
    return -2147467261;
  if ( ATL::_pAtlModule )
    return (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, LPVOID *))(*(_QWORD *)ATL::_pAtlModule + 32LL))(
             ATL::_pAtlModule,
             ppv);
  return CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, ppv);
}

```

## disassembly

```asm
0x18001c534  sub     rsp, 38h
0x18001c538  test    rcx, rcx
0x18001c53b  jnz     short loc_18001C547
0x18001c53d  mov     eax, 80004003h
0x18001c542  add     rsp, 38h
0x18001c546  retn
0x18001c547  mov     r8, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001c54e  test    r8, r8
0x18001c551  jnz     short loc_18001C577
0x18001c553  xor     edx, edx; pUnkOuter
0x18001c555  mov     [rsp+38h+ppv], rcx; ppv
0x18001c55a  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18001c561  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18001c568  lea     r8d, [rdx+1]; dwClsContext
0x18001c56c  call    cs:__imp_CoCreateInstance
0x18001c572  add     rsp, 38h
0x18001c576  retn
0x18001c577  mov     rax, [r8]
0x18001c57a  mov     rdx, rcx
0x18001c57d  mov     rcx, r8
0x18001c580  mov     rax, [rax+20h]
0x18001c584  add     rsp, 38h
0x18001c588  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
