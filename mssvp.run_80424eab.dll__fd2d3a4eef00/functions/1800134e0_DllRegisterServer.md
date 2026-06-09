# DllRegisterServer

- ea: `0x1800134e0`
- end: `0x18001356d`
- name: `DllRegisterServer`
- size: `141`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000bee8`
- `0x18001058c`
- `0x1800134e0`
- `0x18003d010`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x180013561`
- `RPCRT4!NdrDllRegisterProxy` at `0x180013561`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rbx
  HRESULT result; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v2; // rax
  PCInterfaceStubVtblList v3; // rax
  const CLSID *piid; // r8

  v0 = qword_1800546E8;
  if ( qword_1800546E8 )
  {
    while ( *(_QWORD *)v0 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v0 + 8))(1);
      if ( result < 0 )
        goto LABEL_8;
      v2 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v0 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v0, v2, 1);
      if ( result < 0 )
        goto LABEL_8;
      v0 += 72;
    }
  }
  result = ATL::CAtlModuleT<ATL::CComModule>::RegisterServer();
LABEL_8:
  if ( result >= 0 )
  {
    v3 = *aProxyFileList->pStubVtblList;
    if ( v3 )
      piid = v3->header.piid;
    else
      piid = 0;
    return NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
  }
  return result;
}

```

## disassembly

```asm
0x1800134e0  push    rbx
0x1800134e2  sub     rsp, 20h
0x1800134e6  mov     rbx, cs:qword_1800546E8
0x1800134ed  test    rbx, rbx
0x1800134f0  jz      short loc_18001352E
0x1800134f2  jmp     short loc_180013528
0x1800134f4  mov     ecx, 1
0x1800134f9  mov     rax, [rbx+8]
0x1800134fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013502  test    eax, eax
0x180013504  js      short loc_180013534
0x180013506  mov     rax, [rbx+38h]
0x18001350a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001350f  mov     r8d, 1; int
0x180013515  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180013518  mov     rcx, [rbx]; rguid
0x18001351b  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180013520  test    eax, eax
0x180013522  js      short loc_180013534
0x180013524  add     rbx, 48h ; 'H'
0x180013528  cmp     qword ptr [rbx], 0
0x18001352c  jnz     short loc_1800134F4
0x18001352e  call    ?RegisterServer@?$CAtlModuleT@VCComModule@ATL@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<ATL::CComModule>::RegisterServer(int,_GUID const *)
0x180013533  nop
0x180013534  test    eax, eax
0x180013536  js      short loc_180013567
0x180013538  mov     rax, cs:aProxyFileList
0x18001353f  mov     rcx, [rax+8]
0x180013543  mov     rax, [rcx]
0x180013546  test    rax, rax
0x180013549  jz      short loc_180013550
0x18001354b  mov     r8, [rax]
0x18001354e  jmp     short loc_180013553
0x180013550  xor     r8d, r8d; pclsid
0x180013553  lea     rdx, aProxyFileList; pProxyFileList
0x18001355a  mov     rcx, cs:hProxyDll; hDll
0x180013561  call    cs:__imp_NdrDllRegisterProxy
0x180013567  add     rsp, 20h
0x18001356b  pop     rbx
0x18001356c  retn
```
