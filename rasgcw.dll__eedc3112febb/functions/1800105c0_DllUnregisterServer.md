# DllUnregisterServer

- ea: `0x1800105c0`
- end: `0x18001064e`
- name: `DllUnregisterServer`
- size: `142`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007214`
- `0x18000f2d4`
- `0x1800105c0`
- `0x180030010`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x1800105ef`
- `RPCRT4!NdrDllUnregisterProxy` at `0x1800105ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllUnregisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8
  __int64 v2; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v3; // rax
  HRESULT result; // eax

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  if ( NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid) < 0 )
    return -2147467259;
  v2 = qword_18004D998;
  if ( qword_18004D998 )
  {
    while ( *(_QWORD *)v2 )
    {
      v3 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v2 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v2, v3, 0);
      if ( result < 0 )
        return result;
      result = (*(__int64 (__fastcall **)(_QWORD))(v2 + 8))(0);
      if ( result < 0 )
        return result;
      v2 += 72;
    }
  }
  return ATL::CAtlModuleT<ATL::CComModule>::UnregisterServer();
}

```

## disassembly

```asm
0x1800105c0  push    rbx
0x1800105c2  sub     rsp, 20h
0x1800105c6  mov     rax, cs:aProxyFileList
0x1800105cd  mov     rcx, [rax+8]
0x1800105d1  mov     rax, [rcx]
0x1800105d4  test    rax, rax
0x1800105d7  jz      short loc_1800105DE
0x1800105d9  mov     r8, [rax]
0x1800105dc  jmp     short loc_1800105E1
0x1800105de  xor     r8d, r8d; pclsid
0x1800105e1  lea     rdx, aProxyFileList; pProxyFileList
0x1800105e8  mov     rcx, cs:hProxyDll; hDll
0x1800105ef  call    cs:__imp_NdrDllUnregisterProxy
0x1800105f5  test    eax, eax
0x1800105f7  js      short loc_180010643
0x1800105f9  mov     rbx, cs:qword_18004D998
0x180010600  test    rbx, rbx
0x180010603  jz      short loc_18001063B
0x180010605  jmp     short loc_180010635
0x180010607  mov     rax, [rbx+38h]
0x18001060b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010610  xor     r8d, r8d; int
0x180010613  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180010616  mov     rcx, [rbx]; rguid
0x180010619  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18001061e  test    eax, eax
0x180010620  js      short loc_180010641
0x180010622  xor     ecx, ecx
0x180010624  mov     rax, [rbx+8]
0x180010628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001062d  test    eax, eax
0x18001062f  js      short loc_180010641
0x180010631  add     rbx, 48h ; 'H'
0x180010635  cmp     qword ptr [rbx], 0
0x180010639  jnz     short loc_180010607
0x18001063b  call    ?UnregisterServer@?$CAtlModuleT@VCComModule@ATL@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<ATL::CComModule>::UnregisterServer(int,_GUID const *)
0x180010640  nop
0x180010641  jmp     short loc_180010648
0x180010643  mov     eax, 80004005h
0x180010648  add     rsp, 20h
0x18001064c  pop     rbx
0x18001064d  retn
```
