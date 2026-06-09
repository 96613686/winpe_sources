# DllUnregisterServer

- ea: `0x180004a20`
- end: `0x180004a90`
- name: `DllUnregisterServer`
- size: `112`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004a20`
- `0x180010f84`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180004a62`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180004a7d`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180004a62`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180004a7d`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180004a55`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180004a55`
- `RPCRT4!NdrDllUnregisterProxy` at `0x180004a4f`
- `RPCRT4!NdrDllUnregisterProxy` at `0x180004a4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllUnregisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8
  LCID ThreadLocale; // ebx
  unsigned int v3; // edx
  ATL::CAtlModule *v4; // rcx
  struct ATL::_ATL_REGMAP_ENTRY *v5; // r9

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( ATL::_pPerfUnRegFunc )
    ATL::_pPerfUnRegFunc();
  SetThreadLocale(ThreadLocale);
  return ATL::CAtlModule::UpdateRegistryFromResourceS(v4, v3, 0, v5);
}

```

## disassembly

```asm
0x180004a20  push    rbx
0x180004a22  sub     rsp, 20h
0x180004a26  mov     rax, cs:aProxyFileList
0x180004a2d  mov     rcx, [rax+8]
0x180004a31  mov     rax, [rcx]
0x180004a34  test    rax, rax
0x180004a37  jz      short loc_180004A3E
0x180004a39  mov     r8, [rax]
0x180004a3c  jmp     short loc_180004A41
0x180004a3e  xor     r8d, r8d; pclsid
0x180004a41  lea     rdx, aProxyFileList; pProxyFileList
0x180004a48  mov     rcx, cs:hProxyDll; hDll
0x180004a4f  call    cs:__imp_NdrDllUnregisterProxy
0x180004a55  call    cs:__imp_GetThreadLocale
0x180004a5b  mov     ebx, eax
0x180004a5d  mov     ecx, 800h; Locale
0x180004a62  call    cs:__imp_SetThreadLocale
0x180004a68  nop
0x180004a69  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180004a70  test    rax, rax
0x180004a73  jz      short loc_180004A7B
0x180004a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a7a  nop
0x180004a7b  mov     ecx, ebx; Locale
0x180004a7d  call    cs:__imp_SetThreadLocale
0x180004a83  xor     r8d, r8d; int
0x180004a86  add     rsp, 20h
0x180004a8a  pop     rbx
0x180004a8b  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
