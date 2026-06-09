# DllRegisterServer

- ea: `0x1800127b0`
- end: `0x180012891`
- name: `DllRegisterServer`
- size: `225`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ee8c`
- `0x18000f150`
- `0x1800127b0`
- `0x180014010`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x1800127e3`
- `RPCRT4!NdrDllRegisterProxy` at `0x1800127e3`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8
  HRESULT result; // eax
  const unsigned __int16 *v3; // rdx
  struct ATL::_ATL_MODULE *v4; // rcx
  __int64 v5; // rbx
  HRESULT v6; // edi
  __int64 (*v7)(void); // rax
  int v8; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v9; // rax

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  result = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
  if ( result >= 0 )
  {
    v5 = qword_180024B20;
    v6 = 0;
    if ( qword_180024B20 )
    {
      if ( *(_QWORD *)qword_180024B20 )
      {
        do
        {
          v7 = *(__int64 (**)(void))(v5 + 48);
          if ( !v7 || !v7() )
          {
            v6 = (*(__int64 (__fastcall **)(__int64))(v5 + 8))(1);
            if ( v6 < 0 )
              return v6;
            v8 = _Module;
            if ( _Module != 248 )
              goto LABEL_13;
            v9 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v5 + 56))();
            v6 = ATL::AtlRegisterClassCategoriesHelper(*(const struct _GUID **)v5, v9, 1);
            if ( v6 < 0 )
              return v6;
          }
          v8 = _Module;
LABEL_13:
          if ( v8 == 176 )
            v5 += 56;
          else
            v5 += 72;
        }
        while ( *(_QWORD *)v5 );
      }
      return ATL::AtlModuleRegisterTypeLib(v4, v3);
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1800127b0  mov     [rsp+arg_0], rbx
0x1800127b5  push    rdi
0x1800127b6  sub     rsp, 20h
0x1800127ba  mov     rax, cs:aProxyFileList
0x1800127c1  mov     rcx, [rax+8]
0x1800127c5  mov     rax, [rcx]
0x1800127c8  test    rax, rax
0x1800127cb  jz      short loc_1800127D2
0x1800127cd  mov     r8, [rax]
0x1800127d0  jmp     short loc_1800127D5
0x1800127d2  xor     r8d, r8d; pclsid
0x1800127d5  mov     rcx, cs:hProxyDll; hDll
0x1800127dc  lea     rdx, aProxyFileList; pProxyFileList
0x1800127e3  call    cs:__imp_NdrDllRegisterProxy
0x1800127e9  test    eax, eax
0x1800127eb  js      loc_180012886
0x1800127f1  mov     rbx, cs:qword_180024B20
0x1800127f8  xor     edi, edi
0x1800127fa  test    rbx, rbx
0x1800127fd  jz      loc_180012884
0x180012803  cmp     [rbx], rdi
0x180012806  jz      short loc_18001287D
0x180012808  mov     rax, [rbx+30h]
0x18001280c  test    rax, rax
0x18001280f  jz      short loc_18001281B
0x180012811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012816  test    rax, rax
0x180012819  jnz     short loc_18001285C
0x18001281b  mov     rax, [rbx+8]
0x18001281f  mov     ecx, 1
0x180012824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012829  mov     edi, eax
0x18001282b  test    eax, eax
0x18001282d  js      short loc_180012884
0x18001282f  mov     eax, cs:?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x180012835  cmp     eax, 0F8h
0x18001283a  jnz     short loc_180012862
0x18001283c  mov     rax, [rbx+38h]
0x180012840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012845  mov     rcx, [rbx]; struct _GUID *
0x180012848  mov     r8d, 1; int
0x18001284e  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180012851  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180012856  mov     edi, eax
0x180012858  test    eax, eax
0x18001285a  js      short loc_180012884
0x18001285c  mov     eax, cs:?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x180012862  cmp     eax, 0B0h
0x180012867  jnz     short loc_18001286F
0x180012869  add     rbx, 38h ; '8'
0x18001286d  jmp     short loc_180012873
0x18001286f  add     rbx, 48h ; 'H'
0x180012873  cmp     qword ptr [rbx], 0
0x180012877  jnz     short loc_180012808
0x180012879  test    edi, edi
0x18001287b  js      short loc_180012884
0x18001287d  call    ?AtlModuleRegisterTypeLib@ATL@@YAJPEAU_ATL_MODULE@1@PEBG@Z; ATL::AtlModuleRegisterTypeLib(ATL::_ATL_MODULE *,ushort const *)
0x180012882  mov     edi, eax
0x180012884  mov     eax, edi
0x180012886  mov     rbx, [rsp+28h+arg_0]
0x18001288b  add     rsp, 20h
0x18001288f  pop     rdi
0x180012890  retn
```
