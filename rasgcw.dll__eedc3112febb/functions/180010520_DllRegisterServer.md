# DllRegisterServer

- ea: `0x180010520`
- end: `0x1800105b4`
- name: `DllRegisterServer`
- size: `148`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007214`
- `0x18000e100`
- `0x180010520`
- `0x180030010`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x18001054f`
- `RPCRT4!NdrDllRegisterProxy` at `0x18001054f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8
  __int64 v2; // rbx
  HRESULT result; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rax

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  if ( NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid) < 0 )
    return -2147467259;
  v2 = qword_18004D998;
  if ( qword_18004D998 )
  {
    while ( *(_QWORD *)v2 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v2 + 8))(1);
      if ( result < 0 )
        return result;
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v2 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v2, v4, 1);
      if ( result < 0 )
        return result;
      v2 += 72;
    }
  }
  return ATL::CAtlModuleT<ATL::CComModule>::RegisterServer();
}

```

## disassembly

```asm
0x180010520  push    rbx
0x180010522  sub     rsp, 20h
0x180010526  mov     rax, cs:aProxyFileList
0x18001052d  mov     rcx, [rax+8]
0x180010531  mov     rax, [rcx]
0x180010534  test    rax, rax
0x180010537  jz      short loc_18001053E
0x180010539  mov     r8, [rax]
0x18001053c  jmp     short loc_180010541
0x18001053e  xor     r8d, r8d; pclsid
0x180010541  lea     rdx, aProxyFileList; pProxyFileList
0x180010548  mov     rcx, cs:hProxyDll; hDll
0x18001054f  call    cs:__imp_NdrDllRegisterProxy
0x180010555  test    eax, eax
0x180010557  js      short loc_1800105A9
0x180010559  mov     rbx, cs:qword_18004D998
0x180010560  test    rbx, rbx
0x180010563  jz      short loc_1800105A1
0x180010565  jmp     short loc_18001059B
0x180010567  mov     ecx, 1
0x18001056c  mov     rax, [rbx+8]
0x180010570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010575  test    eax, eax
0x180010577  js      short loc_1800105A7
0x180010579  mov     rax, [rbx+38h]
0x18001057d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010582  mov     r8d, 1; int
0x180010588  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18001058b  mov     rcx, [rbx]; rguid
0x18001058e  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180010593  test    eax, eax
0x180010595  js      short loc_1800105A7
0x180010597  add     rbx, 48h ; 'H'
0x18001059b  cmp     qword ptr [rbx], 0
0x18001059f  jnz     short loc_180010567
0x1800105a1  call    ?RegisterServer@?$CAtlModuleT@VCComModule@ATL@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<ATL::CComModule>::RegisterServer(int,_GUID const *)
0x1800105a6  nop
0x1800105a7  jmp     short loc_1800105AE
0x1800105a9  mov     eax, 80004005h
0x1800105ae  add     rsp, 20h
0x1800105b2  pop     rbx
0x1800105b3  retn
```
