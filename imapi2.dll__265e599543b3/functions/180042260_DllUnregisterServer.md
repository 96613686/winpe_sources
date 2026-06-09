# DllUnregisterServer

- ea: `0x180042260`
- end: `0x180042321`
- name: `DllUnregisterServer`
- size: `193`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180010ef0`
- `0x1800140f4`
- `0x1800420e4`
- `0x18004217c`
- `0x180042260`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x1800422d1`
- `RPCRT4!NdrDllUnregisterProxy` at `0x1800422d1`
- `KERNEL32!SetThreadLocale` at `0x180042277`
- `KERNEL32!SetThreadLocale` at `0x180042293`
- `KERNEL32!SetThreadLocale` at `0x180042277`
- `KERNEL32!SetThreadLocale` at `0x180042293`
- `KERNEL32!GetThreadLocale` at `0x18004226a`
- `KERNEL32!GetThreadLocale` at `0x18004226a`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  HRESULT updated; // ebx
  PCInterfaceStubVtblList v2; // rax
  const CLSID *piid; // r8

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  updated = ATL::CAtlModuleT<CImapi2Module>::UnregisterServer();
  if ( updated >= 0 )
    updated = CImapi2Module::UpdateRegistryAppId(0);
  SetThreadLocale(ThreadLocale);
  if ( updated < 0
    || (updated = PrxDllRegisterServer(), updated < 0)
    || ((v2 = *aProxyFileList->pStubVtblList) == 0 ? (piid = 0) : (piid = v2->header.piid),
        updated = NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid),
        updated < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        13,
        WPP_4ee8c0ccf5b13ef7721a296dee7fcadd_Traceguids,
        (unsigned int)updated);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180042260  mov     [rsp+arg_0], rbx
0x180042265  push    rdi
0x180042266  sub     rsp, 20h
0x18004226a  call    cs:__imp_GetThreadLocale
0x180042270  mov     ecx, 800h; Locale
0x180042275  mov     edi, eax
0x180042277  call    cs:__imp_SetThreadLocale
0x18004227d  call    ?UnregisterServer@?$CAtlModuleT@VCImapi2Module@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CImapi2Module>::UnregisterServer(int,_GUID const *)
0x180042282  mov     ebx, eax
0x180042284  test    eax, eax
0x180042286  js      short loc_180042291
0x180042288  xor     ecx, ecx; int
0x18004228a  call    ?UpdateRegistryAppId@CImapi2Module@@SAJH@Z; CImapi2Module::UpdateRegistryAppId(int)
0x18004228f  mov     ebx, eax
0x180042291  mov     ecx, edi; Locale
0x180042293  call    cs:__imp_SetThreadLocale
0x180042299  test    ebx, ebx
0x18004229b  js      short loc_1800422DD
0x18004229d  call    PrxDllRegisterServer
0x1800422a2  mov     ebx, eax
0x1800422a4  test    eax, eax
0x1800422a6  js      short loc_1800422DD
0x1800422a8  mov     rax, cs:aProxyFileList
0x1800422af  mov     rcx, [rax+8]
0x1800422b3  mov     rax, [rcx]
0x1800422b6  test    rax, rax
0x1800422b9  jz      short loc_1800422C0
0x1800422bb  mov     r8, [rax]
0x1800422be  jmp     short loc_1800422C3
0x1800422c0  xor     r8d, r8d; pclsid
0x1800422c3  mov     rcx, cs:hProxyDll; hDll
0x1800422ca  lea     rdx, aProxyFileList; pProxyFileList
0x1800422d1  call    cs:__imp_NdrDllUnregisterProxy
0x1800422d7  mov     ebx, eax
0x1800422d9  test    eax, eax
0x1800422db  jns     short loc_180042314
0x1800422dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800422e4  lea     rax, WPP_GLOBAL_Control
0x1800422eb  cmp     rcx, rax
0x1800422ee  jz      short loc_180042314
0x1800422f0  test    byte ptr [rcx+44h], 1
0x1800422f4  jz      short loc_180042314
0x1800422f6  cmp     byte ptr [rcx+41h], 3
0x1800422fa  jb      short loc_180042314
0x1800422fc  mov     rcx, [rcx+38h]
0x180042300  lea     r8, WPP_4ee8c0ccf5b13ef7721a296dee7fcadd_Traceguids
0x180042307  mov     edx, 0Dh
0x18004230c  mov     r9d, ebx
0x18004230f  call    WPP_SF_d
0x180042314  mov     rbx, [rsp+28h+arg_0]
0x180042319  xor     eax, eax
0x18004231b  add     rsp, 20h
0x18004231f  pop     rdi
0x180042320  retn
```
