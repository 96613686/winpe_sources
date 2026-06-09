# DllRegisterServer

- ea: `0x1800064c0`
- end: `0x180006602`
- name: `DllRegisterServer`
- size: `322`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800032f8`
- `0x1800037c0`
- `0x180005b1c`
- `0x1800064c0`
- `0x180010010`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x1800065ec`
- `RPCRT4!NdrDllRegisterProxy` at `0x1800065ec`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const unsigned __int16 *v0; // rdx
  __int64 v1; // rbx
  HRESULT result; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v3; // rax
  __int64 *v4; // rbx
  __int64 *i; // rcx
  __int64 v6; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax
  PCInterfaceStubVtblList v8; // rax
  const CLSID *piid; // r8

  v1 = qword_180019A58;
  if ( qword_180019A58 )
  {
    while ( *(_QWORD *)v1 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v1 + 8))(1);
      if ( result < 0 )
        goto LABEL_16;
      v3 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v1 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v1, v3, 1);
      if ( result < 0 )
        goto LABEL_16;
      v1 += 72;
    }
  }
  v4 = (__int64 *)off_180019190[0];
  for ( i = (__int64 *)off_180019198; v4 < i; ++v4 )
  {
    v6 = *v4;
    if ( *v4 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v6 + 8))(1);
      if ( result < 0 )
        goto LABEL_16;
      v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v6 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v6, v7, 1);
      if ( result < 0 )
        goto LABEL_16;
      i = (__int64 *)off_180019198;
    }
  }
  result = ATL::AtlRegisterTypeLib(off_180019188, v0);
  if ( result >= 0 && ATL::_pPerfRegFunc )
    result = ((__int64 (__fastcall *)(HMODULE))ATL::_pPerfRegFunc)(hInstance);
LABEL_16:
  if ( result >= 0 )
  {
    result = ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_Module, 2u, 1, 0);
    if ( result >= 0 )
    {
      v8 = *aProxyFileList->pStubVtblList;
      if ( v8 )
        piid = v8->header.piid;
      else
        piid = 0;
      return NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800064c0  mov     [rsp+arg_0], rbx
0x1800064c5  mov     [rsp+arg_8], rsi
0x1800064ca  push    rdi
0x1800064cb  sub     rsp, 20h
0x1800064cf  mov     rbx, cs:qword_180019A58
0x1800064d6  mov     esi, 1
0x1800064db  test    rbx, rbx
0x1800064de  jz      short loc_18000651E
0x1800064e0  jmp     short loc_180006518
0x1800064e2  mov     ecx, esi
0x1800064e4  mov     rax, [rbx+8]
0x1800064e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ed  test    eax, eax
0x1800064ef  js      loc_1800065A5
0x1800064f5  mov     rax, [rbx+38h]
0x1800064f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064fe  mov     r8d, esi; int
0x180006501  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180006504  mov     rcx, [rbx]; rguid
0x180006507  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000650c  test    eax, eax
0x18000650e  js      loc_1800065A5
0x180006514  add     rbx, 48h ; 'H'
0x180006518  cmp     qword ptr [rbx], 0
0x18000651c  jnz     short loc_1800064E2
0x18000651e  xor     eax, eax
0x180006520  mov     rbx, cs:off_180019190
0x180006527  mov     rcx, cs:off_180019198
0x18000652e  cmp     rbx, rcx
0x180006531  jnb     short loc_180006579
0x180006533  mov     rdi, [rbx]
0x180006536  test    rdi, rdi
0x180006539  jz      short loc_18000656C
0x18000653b  mov     ecx, esi
0x18000653d  mov     rax, [rdi+8]
0x180006541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006546  test    eax, eax
0x180006548  js      short loc_1800065A5
0x18000654a  mov     rax, [rdi+38h]
0x18000654e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006553  mov     r8d, esi; int
0x180006556  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180006559  mov     rcx, [rdi]; rguid
0x18000655c  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180006561  test    eax, eax
0x180006563  js      short loc_1800065A5
0x180006565  mov     rcx, cs:off_180019198
0x18000656c  add     rbx, 8
0x180006570  cmp     rbx, rcx
0x180006573  jb      short loc_180006533
0x180006575  test    eax, eax
0x180006577  js      short loc_1800065A5
0x180006579  mov     rcx, cs:off_180019188; HINSTANCE
0x180006580  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x180006585  test    eax, eax
0x180006587  js      short loc_1800065A5
0x180006589  mov     rdx, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180006590  test    rdx, rdx
0x180006593  jz      short loc_1800065A5
0x180006595  mov     rcx, cs:hInstance
0x18000659c  mov     rax, rdx
0x18000659f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065a4  nop
0x1800065a5  test    eax, eax
0x1800065a7  js      short loc_1800065F2
0x1800065a9  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x1800065ac  mov     r8d, esi; int
0x1800065af  lea     edx, [r9+2]; unsigned int
0x1800065b3  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x1800065ba  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x1800065bf  test    eax, eax
0x1800065c1  js      short loc_1800065F2
0x1800065c3  mov     rax, cs:aProxyFileList
0x1800065ca  mov     rcx, [rax+8]
0x1800065ce  mov     rax, [rcx]
0x1800065d1  test    rax, rax
0x1800065d4  jz      short loc_1800065DB
0x1800065d6  mov     r8, [rax]
0x1800065d9  jmp     short loc_1800065DE
0x1800065db  xor     r8d, r8d; pclsid
0x1800065de  lea     rdx, aProxyFileList; pProxyFileList
0x1800065e5  mov     rcx, cs:hProxyDll; hDll
0x1800065ec  call    cs:__imp_NdrDllRegisterProxy
0x1800065f2  mov     rbx, [rsp+28h+arg_0]
0x1800065f7  mov     rsi, [rsp+28h+arg_8]
0x1800065fc  add     rsp, 20h
0x180006600  pop     rdi
0x180006601  retn
```
