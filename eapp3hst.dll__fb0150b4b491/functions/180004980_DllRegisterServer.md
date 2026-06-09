# DllRegisterServer

- ea: `0x180004980`
- end: `0x180004a15`
- name: `DllRegisterServer`
- size: `149`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004980`
- `0x180010f84`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x1800049cc`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x1800049f1`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x1800049cc`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x1800049f1`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x1800049bf`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x1800049bf`
- `RPCRT4!NdrDllRegisterProxy` at `0x1800049b3`
- `RPCRT4!NdrDllRegisterProxy` at `0x1800049b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8
  int v2; // ebx
  LCID ThreadLocale; // edi
  unsigned int v4; // edx
  ATL::CAtlModule *v5; // rcx
  struct ATL::_ATL_REGMAP_ENTRY *v6; // r9

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  v2 = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
  if ( v2 >= 0 )
  {
    ThreadLocale = GetThreadLocale();
    SetThreadLocale(0x800u);
    v2 = 0;
    if ( ATL::_pPerfRegFunc )
      v2 = ATL::_pPerfRegFunc(hModule);
    SetThreadLocale(ThreadLocale);
    if ( v2 >= 0 )
      return ATL::CAtlModule::UpdateRegistryFromResourceS(v5, v4, 1, v6);
  }
  return v2;
}

```

## disassembly

```asm
0x180004980  mov     [rsp+arg_0], rbx
0x180004985  push    rdi
0x180004986  sub     rsp, 20h
0x18000498a  mov     rax, cs:aProxyFileList
0x180004991  mov     rcx, [rax+8]
0x180004995  mov     rax, [rcx]
0x180004998  test    rax, rax
0x18000499b  jz      short loc_1800049A2
0x18000499d  mov     r8, [rax]
0x1800049a0  jmp     short loc_1800049A5
0x1800049a2  xor     r8d, r8d; pclsid
0x1800049a5  lea     rdx, aProxyFileList; pProxyFileList
0x1800049ac  mov     rcx, cs:hProxyDll; hDll
0x1800049b3  call    cs:__imp_NdrDllRegisterProxy
0x1800049b9  mov     ebx, eax
0x1800049bb  test    eax, eax
0x1800049bd  js      short loc_180004A08
0x1800049bf  call    cs:__imp_GetThreadLocale
0x1800049c5  mov     edi, eax
0x1800049c7  mov     ecx, 800h; Locale
0x1800049cc  call    cs:__imp_SetThreadLocale
0x1800049d2  nop
0x1800049d3  xor     ebx, ebx
0x1800049d5  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x1800049dc  test    rax, rax
0x1800049df  jz      short loc_1800049EF
0x1800049e1  mov     rcx, cs:hModule
0x1800049e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ed  mov     ebx, eax
0x1800049ef  mov     ecx, edi; Locale
0x1800049f1  call    cs:__imp_SetThreadLocale
0x1800049f7  test    ebx, ebx
0x1800049f9  js      short loc_180004A08
0x1800049fb  mov     r8d, 1; int
0x180004a01  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180004a06  mov     ebx, eax
0x180004a08  mov     eax, ebx
0x180004a0a  mov     rbx, [rsp+28h+arg_0]
0x180004a0f  add     rsp, 20h
0x180004a13  pop     rdi
0x180004a14  retn
```
