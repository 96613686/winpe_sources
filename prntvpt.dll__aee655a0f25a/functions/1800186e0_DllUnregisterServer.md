# DllUnregisterServer

- ea: `0x1800186e0`
- end: `0x180018830`
- name: `DllUnregisterServer`
- size: `336`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800180bc`
- `0x180018544`
- `0x180018588`
- `0x1800186e0`
- `0x180023010`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x18001881f`
- `RPCRT4!NdrDllUnregisterProxy` at `0x18001881f`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT result; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v1; // rbx
  __int64 *v2; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v3; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v5; // rbx
  __int64 *v6; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v7; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v8; // rax
  PCInterfaceStubVtblList v9; // rax
  const CLSID *piid; // r8

  result = CMyDllModule::UpdateRegistryAppId(0);
  if ( result >= 0 )
  {
    if ( !ATL::_pPerfUnRegFunc || (result = ATL::_pPerfUnRegFunc(), result >= 0) )
    {
      v1 = off_1800316B0;
      v2 = off_1800316B8;
      while ( v1 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v2 )
      {
        v3 = *v1;
        if ( *v1 )
        {
          v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v3 + 7))();
          result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v3, v4, 0);
          if ( result < 0 )
            return result;
          result = (*((__int64 (__fastcall **)(_QWORD))v3 + 1))(0);
          if ( result < 0 )
            return result;
          v2 = off_1800316B8;
        }
        ++v1;
      }
      result = CMyDllModuleAC::UpdateRegistryAppId(0);
      if ( result >= 0 )
      {
        if ( !ATL::_pPerfUnRegFunc || (result = ATL::_pPerfUnRegFunc(), result >= 0) )
        {
          v5 = off_1800316B0;
          v6 = off_1800316B8;
          while ( v5 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v6 )
          {
            v7 = *v5;
            if ( *v5 )
            {
              v8 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v7 + 7))();
              result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v7, v8, 0);
              if ( result < 0 )
                return result;
              result = (*((__int64 (__fastcall **)(_QWORD))v7 + 1))(0);
              if ( result < 0 )
                return result;
              v6 = off_1800316B8;
            }
            ++v5;
          }
          v9 = *aProxyFileList->pStubVtblList;
          if ( v9 )
            piid = v9->header.piid;
          else
            piid = 0;
          return NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800186e0  mov     [rsp+arg_0], rbx
0x1800186e5  push    rdi
0x1800186e6  sub     rsp, 20h
0x1800186ea  xor     ecx, ecx; int
0x1800186ec  call    ?UpdateRegistryAppId@CMyDllModule@@SAJH@Z; CMyDllModule::UpdateRegistryAppId(int)
0x1800186f1  test    eax, eax
0x1800186f3  js      loc_180018825
0x1800186f9  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180018700  test    rax, rax
0x180018703  jz      short loc_180018712
0x180018705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001870a  test    eax, eax
0x18001870c  js      loc_180018825
0x180018712  mov     rbx, cs:off_1800316B0
0x180018719  xor     eax, eax
0x18001871b  mov     rcx, cs:off_1800316B8
0x180018722  jmp     short loc_180018769
0x180018724  mov     rdi, [rbx]
0x180018727  test    rdi, rdi
0x18001872a  jz      short loc_180018765
0x18001872c  mov     rax, [rdi+38h]
0x180018730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018735  mov     rcx, [rdi]; rguid
0x180018738  xor     r8d, r8d; int
0x18001873b  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18001873e  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180018743  test    eax, eax
0x180018745  js      loc_180018825
0x18001874b  mov     rax, [rdi+8]
0x18001874f  xor     ecx, ecx
0x180018751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018756  test    eax, eax
0x180018758  js      loc_180018825
0x18001875e  mov     rcx, cs:off_1800316B8
0x180018765  add     rbx, 8
0x180018769  cmp     rbx, rcx
0x18001876c  jb      short loc_180018724
0x18001876e  test    eax, eax
0x180018770  js      loc_180018825
0x180018776  xor     ecx, ecx; int
0x180018778  call    ?UpdateRegistryAppId@CMyDllModuleAC@@SAJH@Z; CMyDllModuleAC::UpdateRegistryAppId(int)
0x18001877d  test    eax, eax
0x18001877f  js      loc_180018825
0x180018785  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x18001878c  test    rax, rax
0x18001878f  jz      short loc_18001879E
0x180018791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018796  test    eax, eax
0x180018798  js      loc_180018825
0x18001879e  mov     rbx, cs:off_1800316B0
0x1800187a5  xor     eax, eax
0x1800187a7  mov     rcx, cs:off_1800316B8
0x1800187ae  jmp     short loc_1800187ED
0x1800187b0  mov     rdi, [rbx]
0x1800187b3  test    rdi, rdi
0x1800187b6  jz      short loc_1800187E9
0x1800187b8  mov     rax, [rdi+38h]
0x1800187bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187c1  mov     rcx, [rdi]; rguid
0x1800187c4  xor     r8d, r8d; int
0x1800187c7  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1800187ca  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800187cf  test    eax, eax
0x1800187d1  js      short loc_180018825
0x1800187d3  mov     rax, [rdi+8]
0x1800187d7  xor     ecx, ecx
0x1800187d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187de  test    eax, eax
0x1800187e0  js      short loc_180018825
0x1800187e2  mov     rcx, cs:off_1800316B8
0x1800187e9  add     rbx, 8
0x1800187ed  cmp     rbx, rcx
0x1800187f0  jb      short loc_1800187B0
0x1800187f2  test    eax, eax
0x1800187f4  js      short loc_180018825
0x1800187f6  mov     rax, cs:aProxyFileList
0x1800187fd  mov     rcx, [rax+8]
0x180018801  mov     rax, [rcx]
0x180018804  test    rax, rax
0x180018807  jz      short loc_18001880E
0x180018809  mov     r8, [rax]
0x18001880c  jmp     short loc_180018811
0x18001880e  xor     r8d, r8d; pclsid
0x180018811  mov     rcx, cs:hProxyDll; hDll
0x180018818  lea     rdx, aProxyFileList; pProxyFileList
0x18001881f  call    cs:__imp_NdrDllUnregisterProxy
0x180018825  mov     rbx, [rsp+28h+arg_0]
0x18001882a  add     rsp, 20h
0x18001882e  pop     rdi
0x18001882f  retn
```
