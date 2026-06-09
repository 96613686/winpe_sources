# DllUnregisterServer

- ea: `0x180028470`
- end: `0x180028531`
- name: `DllUnregisterServer`
- size: `193`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800063b8`
- `0x180025864`
- `0x180027f74`
- `0x18002800c`
- `0x180028470`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x18002847a`
- `KERNEL32!GetThreadLocale` at `0x18002847a`
- `KERNEL32!SetThreadLocale` at `0x180028487`
- `KERNEL32!SetThreadLocale` at `0x1800284a3`
- `KERNEL32!SetThreadLocale` at `0x180028487`
- `KERNEL32!SetThreadLocale` at `0x1800284a3`
- `RPCRT4!NdrDllUnregisterProxy` at `0x1800284e1`
- `RPCRT4!NdrDllUnregisterProxy` at `0x1800284e1`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  int updated; // ebx
  PCInterfaceStubVtblList v2; // rax
  const CLSID *piid; // r8

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  updated = ATL::CAtlModuleT<CFileSystemImagingModule>::UnregisterServer();
  if ( updated >= 0 )
    updated = CFileSystemImagingModule::UpdateRegistryAppId(0);
  SetThreadLocale(ThreadLocale);
  if ( updated < 0
    || (int)PrxDllRegisterServer() < 0
    || ((v2 = *aProxyFileList->pStubVtblList) == 0 ? (piid = 0) : (piid = v2->header.piid),
        NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid) < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, WPP_3f8da94856503e18e8b1748b7bc6ee3e_Traceguids);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180028470  mov     [rsp+arg_0], rbx
0x180028475  push    rdi
0x180028476  sub     rsp, 20h
0x18002847a  call    cs:__imp_GetThreadLocale
0x180028480  mov     ecx, 800h; Locale
0x180028485  mov     edi, eax
0x180028487  call    cs:__imp_SetThreadLocale
0x18002848d  call    ?UnregisterServer@?$CAtlModuleT@VCFileSystemImagingModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CFileSystemImagingModule>::UnregisterServer(int,_GUID const *)
0x180028492  mov     ebx, eax
0x180028494  test    eax, eax
0x180028496  js      short loc_1800284A1
0x180028498  xor     ecx, ecx; int
0x18002849a  call    ?UpdateRegistryAppId@CFileSystemImagingModule@@SAJH@Z; CFileSystemImagingModule::UpdateRegistryAppId(int)
0x18002849f  mov     ebx, eax
0x1800284a1  mov     ecx, edi; Locale
0x1800284a3  call    cs:__imp_SetThreadLocale
0x1800284a9  test    ebx, ebx
0x1800284ab  js      short loc_1800284ED
0x1800284ad  call    PrxDllRegisterServer
0x1800284b2  mov     ebx, eax
0x1800284b4  test    eax, eax
0x1800284b6  js      short loc_1800284ED
0x1800284b8  mov     rax, cs:aProxyFileList
0x1800284bf  mov     rcx, [rax+8]
0x1800284c3  mov     rax, [rcx]
0x1800284c6  test    rax, rax
0x1800284c9  jz      short loc_1800284D0
0x1800284cb  mov     r8, [rax]
0x1800284ce  jmp     short loc_1800284D3
0x1800284d0  xor     r8d, r8d; pclsid
0x1800284d3  mov     rcx, cs:hProxyDll; hDll
0x1800284da  lea     rdx, aProxyFileList; pProxyFileList
0x1800284e1  call    cs:__imp_NdrDllUnregisterProxy
0x1800284e7  mov     ebx, eax
0x1800284e9  test    eax, eax
0x1800284eb  jns     short loc_180028524
0x1800284ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284f4  lea     rax, WPP_GLOBAL_Control
0x1800284fb  cmp     rcx, rax
0x1800284fe  jz      short loc_180028524
0x180028500  test    byte ptr [rcx+44h], 4
0x180028504  jz      short loc_180028524
0x180028506  cmp     byte ptr [rcx+41h], 3
0x18002850a  jb      short loc_180028524
0x18002850c  mov     rcx, [rcx+38h]
0x180028510  lea     r8, WPP_3f8da94856503e18e8b1748b7bc6ee3e_Traceguids
0x180028517  mov     edx, 0Eh
0x18002851c  mov     r9d, ebx
0x18002851f  call    WPP_SF_d
0x180028524  mov     rbx, [rsp+28h+arg_0]
0x180028529  xor     eax, eax
0x18002852b  add     rsp, 20h
0x18002852f  pop     rdi
0x180028530  retn
```
