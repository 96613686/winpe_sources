# DllUnregisterServer

- ea: `0x1800140e0`
- end: `0x1800141c0`
- name: `DllUnregisterServer`
- size: `224`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180012cd4`
- `0x1800140e0`
- `0x180014410`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x1800140ea`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x1800140ea`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x1800140f7`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180014122`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x1800140f7`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180014122`
- `RPCRT4!NdrDllUnregisterProxy` at `0x18001418c`
- `RPCRT4!NdrDllUnregisterProxy` at `0x18001418c`
- `RPCRT4!NdrDllRegisterProxy` at `0x180014159`
- `RPCRT4!NdrDllRegisterProxy` at `0x180014159`

## string_xrefs

- `0x1800141a0`: `DllUnregisterServer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  int v1; // edx
  ATL::CAtlComModule *v2; // rcx
  const struct _GUID *v3; // r8
  int v4; // eax
  HRESULT v5; // ebx
  PCInterfaceStubVtblList v6; // rax
  const CLSID *piid; // r8
  HRESULT result; // eax
  PCInterfaceStubVtblList v9; // rax
  const CLSID *v10; // r8
  unsigned int v11; // eax
  __int64 v12; // rcx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (v4 = ATL::_pPerfUnRegFunc(), v4 >= 0) )
    v4 = ATL::CAtlComModule::UnregisterServer(v2, v1, v3);
  v5 = 0;
  if ( v4 < 0 )
    v5 = v4;
  SetThreadLocale(ThreadLocale);
  if ( v5 < 0 )
    return v5;
  v6 = *aProxyFileList->pStubVtblList;
  if ( v6 )
    piid = v6->header.piid;
  else
    piid = 0;
  result = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
  if ( result >= 0 )
  {
    v9 = *aProxyFileList->pStubVtblList;
    if ( v9 )
      v10 = v9->header.piid;
    else
      v10 = 0;
    v11 = NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, v10);
    v5 = v11;
    if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
      McTemplateU0sd_EventWriteTransfer(v12, mbaeapi_cpp170, "DllUnregisterServer", v11);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800140e0  mov     [rsp+arg_0], rbx
0x1800140e5  push    rdi
0x1800140e6  sub     rsp, 20h
0x1800140ea  call    cs:__imp_GetThreadLocale
0x1800140f0  mov     edi, eax
0x1800140f2  mov     ecx, 800h; Locale
0x1800140f7  call    cs:__imp_SetThreadLocale
0x1800140fd  nop
0x1800140fe  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180014105  test    rax, rax
0x180014108  jz      short loc_180014113
0x18001410a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001410f  test    eax, eax
0x180014111  js      short loc_180014119
0x180014113  call    ?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlComModule::UnregisterServer(int,_GUID const *)
0x180014118  nop
0x180014119  xor     ebx, ebx
0x18001411b  test    eax, eax
0x18001411d  cmovs   ebx, eax
0x180014120  mov     ecx, edi; Locale
0x180014122  call    cs:__imp_SetThreadLocale
0x180014128  test    ebx, ebx
0x18001412a  js      loc_1800141B3
0x180014130  mov     rax, cs:aProxyFileList
0x180014137  mov     rcx, [rax+8]
0x18001413b  mov     rax, [rcx]
0x18001413e  test    rax, rax
0x180014141  jz      short loc_180014148
0x180014143  mov     r8, [rax]
0x180014146  jmp     short loc_18001414B
0x180014148  xor     r8d, r8d; pclsid
0x18001414b  lea     rdx, aProxyFileList; pProxyFileList
0x180014152  mov     rcx, cs:hProxyDll; hDll
0x180014159  call    cs:__imp_NdrDllRegisterProxy
0x18001415f  test    eax, eax
0x180014161  js      short loc_1800141B5
0x180014163  mov     rax, cs:aProxyFileList
0x18001416a  mov     rcx, [rax+8]
0x18001416e  mov     rax, [rcx]
0x180014171  test    rax, rax
0x180014174  jz      short loc_18001417B
0x180014176  mov     r8, [rax]
0x180014179  jmp     short loc_18001417E
0x18001417b  xor     r8d, r8d; pclsid
0x18001417e  lea     rdx, aProxyFileList; pProxyFileList
0x180014185  mov     rcx, cs:hProxyDll; hDll
0x18001418c  call    cs:__imp_NdrDllUnregisterProxy
0x180014192  mov     ebx, eax
0x180014194  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x18001419b  jz      short loc_1800141B3
0x18001419d  mov     r9d, eax
0x1800141a0  lea     r8, aDllunregisters_0; "DllUnregisterServer"
0x1800141a7  lea     rdx, mbaeapi_cpp170
0x1800141ae  call    McTemplateU0sd_EventWriteTransfer
0x1800141b3  mov     eax, ebx
0x1800141b5  mov     rbx, [rsp+28h+arg_0]
0x1800141ba  add     rsp, 20h
0x1800141be  pop     rdi
0x1800141bf  retn
```
