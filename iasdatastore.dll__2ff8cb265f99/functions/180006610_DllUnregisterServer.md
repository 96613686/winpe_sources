# DllUnregisterServer

- ea: `0x180006610`
- end: `0x18000670b`
- name: `DllUnregisterServer`
- size: `251`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800032f8`
- `0x180006610`
- `0x180010010`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x180006643`
- `RPCRT4!NdrDllUnregisterProxy` at `0x180006643`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HRESULT __stdcall DllUnregisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8
  HRESULT result; // eax
  __int64 v3; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rax
  __int64 *v5; // rbx
  __int64 *v6; // rcx
  __int64 v7; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v8; // rax

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  result = NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
  if ( result >= 0 )
  {
    v3 = qword_180019A58;
    if ( qword_180019A58 )
    {
      while ( *(_QWORD *)v3 )
      {
        v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v3 + 56))();
        result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v3, v4, 0);
        if ( result < 0 )
          return result;
        result = (*(__int64 (__fastcall **)(_QWORD))(v3 + 8))(0);
        if ( result < 0 )
          return result;
        v3 += 72;
      }
    }
    if ( !ATL::_pPerfUnRegFunc || (result = ATL::_pPerfUnRegFunc(), result >= 0) )
    {
      result = 0;
      v5 = (__int64 *)off_180019190[0];
      v6 = (__int64 *)off_180019198;
      while ( v5 < v6 )
      {
        v7 = *v5;
        if ( *v5 )
        {
          v8 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v7 + 56))();
          result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v7, v8, 0);
          if ( result < 0 )
            return result;
          result = (*(__int64 (__fastcall **)(_QWORD))(v7 + 8))(0);
          if ( result < 0 )
            return result;
          v6 = (__int64 *)off_180019198;
        }
        ++v5;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006610  mov     [rsp+arg_0], rbx
0x180006615  push    rdi
0x180006616  sub     rsp, 20h
0x18000661a  mov     rax, cs:aProxyFileList
0x180006621  mov     rcx, [rax+8]
0x180006625  mov     rax, [rcx]
0x180006628  test    rax, rax
0x18000662b  jz      short loc_180006632
0x18000662d  mov     r8, [rax]
0x180006630  jmp     short loc_180006635
0x180006632  xor     r8d, r8d; pclsid
0x180006635  lea     rdx, aProxyFileList; pProxyFileList
0x18000663c  mov     rcx, cs:hProxyDll; hDll
0x180006643  call    cs:__imp_NdrDllUnregisterProxy
0x180006649  test    eax, eax
0x18000664b  js      loc_180006700
0x180006651  mov     rbx, cs:qword_180019A58
0x180006658  test    rbx, rbx
0x18000665b  jz      short loc_180006697
0x18000665d  jmp     short loc_180006691
0x18000665f  mov     rax, [rbx+38h]
0x180006663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006668  xor     r8d, r8d; int
0x18000666b  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000666e  mov     rcx, [rbx]; rguid
0x180006671  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180006676  test    eax, eax
0x180006678  js      loc_180006700
0x18000667e  xor     ecx, ecx
0x180006680  mov     rax, [rbx+8]
0x180006684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006689  test    eax, eax
0x18000668b  js      short loc_180006700
0x18000668d  add     rbx, 48h ; 'H'
0x180006691  cmp     qword ptr [rbx], 0
0x180006695  jnz     short loc_18000665F
0x180006697  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x18000669e  test    rax, rax
0x1800066a1  jz      short loc_1800066AC
0x1800066a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066a8  test    eax, eax
0x1800066aa  js      short loc_180006700
0x1800066ac  xor     eax, eax
0x1800066ae  mov     rbx, cs:off_180019190
0x1800066b5  mov     rcx, cs:off_180019198
0x1800066bc  jmp     short loc_1800066FB
0x1800066be  mov     rdi, [rbx]
0x1800066c1  test    rdi, rdi
0x1800066c4  jz      short loc_1800066F7
0x1800066c6  mov     rax, [rdi+38h]
0x1800066ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066cf  xor     r8d, r8d; int
0x1800066d2  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1800066d5  mov     rcx, [rdi]; rguid
0x1800066d8  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800066dd  test    eax, eax
0x1800066df  js      short loc_180006700
0x1800066e1  xor     ecx, ecx
0x1800066e3  mov     rax, [rdi+8]
0x1800066e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066ec  test    eax, eax
0x1800066ee  js      short loc_180006700
0x1800066f0  mov     rcx, cs:off_180019198
0x1800066f7  add     rbx, 8
0x1800066fb  cmp     rbx, rcx
0x1800066fe  jb      short loc_1800066BE
0x180006700  mov     rbx, [rsp+28h+arg_0]
0x180006705  add     rsp, 20h
0x180006709  pop     rdi
0x18000670a  retn
```
