# PrintNetworkConnection(wil::com_ptr_t<INetworkConnection,wil::err_exception_policy> const &)

- ea: `0x180011634`
- end: `0x180011875`
- name: `?PrintNetworkConnection@@YAXAEBV?$com_ptr_t@UINetworkConnection@@Uerr_exception_policy@wil@@@wil@@@Z`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002b9d0`

## callees

- `0x180011634`
- `0x18001187c`
- `0x180011ae8`
- `0x1800120d0`
- `0x180012f40`
- `0x18002a928`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001177c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800117c2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001177c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800117c2`

## string_xrefs

- `0x180011695`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`
- `0x1800116d1`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`
- `0x18001170d`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`
- `0x180011749`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`

## pseudocode

```c
__int64 __fastcall PrintNetworkConnection(_QWORD *a1)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax
  int v5; // eax
  __int64 result; // rax
  const char *v7; // r9
  enum NLM_CONNECTIVITY v8; // [rsp+20h] [rbp-E8h] BYREF
  enum NLM_DOMAIN_TYPE v9; // [rsp+24h] [rbp-E4h] BYREF
  GUID rguid; // [rsp+28h] [rbp-E0h] BYREF
  GUID v11; // [rsp+38h] [rbp-D0h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-B8h] BYREF
  OLECHAR v13[40]; // [rsp+A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  try
  {
    g_netshPrintMessageFromModule(g_moduleHandle, 0x1B58u);
    rguid = 0;
    v2 = (*(__int64 (__fastcall **)(_QWORD, GUID *))(*(_QWORD *)*a1 + 96LL))(*a1, &rguid);
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x187,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
        (const char *)(unsigned int)v2,
        v8);
    v11 = 0;
    v3 = (*(__int64 (__fastcall **)(_QWORD, GUID *))(*(_QWORD *)*a1 + 88LL))(*a1, &v11);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x18A,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
        (const char *)(unsigned int)v3,
        v8);
    v8 = NLM_CONNECTIVITY_DISCONNECTED;
    v4 = (*(__int64 (__fastcall **)(_QWORD, enum NLM_CONNECTIVITY *))(*(_QWORD *)*a1 + 80LL))(*a1, &v8);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x18D,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
        (const char *)(unsigned int)v4,
        v8);
    v9 = NLM_DOMAIN_TYPE_NON_DOMAIN_NETWORK;
    v5 = (*(__int64 (__fastcall **)(_QWORD, enum NLM_DOMAIN_TYPE *))(*(_QWORD *)*a1 + 104LL))(*a1, &v9);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x190,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
        (const char *)(unsigned int)v5,
        v8);
    memset_0(sz, 0, 0x4Eu);
    StringFromGUID2(&rguid, sz, 39);
    g_netshPrintMessageFromModule(g_moduleHandle, 7001u, sz);
    memset_0(v13, 0, 0x4Eu);
    StringFromGUID2(&v11, v13, 39);
    g_netshPrintMessageFromModule(g_moduleHandle, 7002u, v13);
    g_netshPrintMessageFromModule(g_moduleHandle, 7003u);
    PrintNetworkConnectivity(v8);
    g_netshPrintMessageFromModule(g_moduleHandle, 4001u);
    g_netshPrintMessageFromModule(g_moduleHandle, 7004u);
    PrintNetworkDomainType(v9);
    result = ((__int64 (__fastcall *)(HINSTANCE, __int64))g_netshPrintMessageFromModule)(g_moduleHandle, 4001);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0x1A2,
             (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
             v7);
  }
  return result;
}

```

## disassembly

```asm
0x180011634  push    rbx
0x180011636  sub     rsp, 100h
0x18001163d  mov     rax, cs:__security_cookie
0x180011644  xor     rax, rsp
0x180011647  mov     [rsp+108h+var_18], rax
0x18001164f  mov     rbx, rcx
0x180011652  mov     edx, 1B58h
0x180011657  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x18001165e  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x180011665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001166a  xorps   xmm0, xmm0
0x18001166d  movups  xmmword ptr [rsp+108h+rguid.Data1], xmm0
0x180011672  mov     rcx, [rbx]
0x180011675  mov     rax, [rcx]
0x180011678  lea     rdx, [rsp+108h+rguid]
0x18001167d  mov     rax, [rax+60h]
0x180011681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011686  mov     rcx, [rsp+108h]; this
0x18001168e  test    eax, eax
0x180011690  jns     short loc_1800116A6
0x180011692  mov     r9d, eax; char *
0x180011695  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x18001169c  mov     edx, 187h; void *
0x1800116a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800116a6  xorps   xmm0, xmm0
0x1800116a9  movups  xmmword ptr [rsp+108h+var_D0.Data1], xmm0
0x1800116ae  mov     rcx, [rbx]
0x1800116b1  mov     rax, [rcx]
0x1800116b4  lea     rdx, [rsp+108h+var_D0]
0x1800116b9  mov     rax, [rax+58h]
0x1800116bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116c2  mov     rcx, [rsp+108h]; this
0x1800116ca  test    eax, eax
0x1800116cc  jns     short loc_1800116E2
0x1800116ce  mov     r9d, eax; char *
0x1800116d1  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x1800116d8  mov     edx, 18Ah; void *
0x1800116dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800116e2  mov     [rsp+108h+var_E8], 0; int
0x1800116ea  mov     rcx, [rbx]
0x1800116ed  mov     rax, [rcx]
0x1800116f0  lea     rdx, [rsp+108h+var_E8]
0x1800116f5  mov     rax, [rax+50h]
0x1800116f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116fe  mov     rcx, [rsp+108h]; this
0x180011706  test    eax, eax
0x180011708  jns     short loc_18001171E
0x18001170a  mov     r9d, eax; char *
0x18001170d  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x180011714  mov     edx, 18Dh; void *
0x180011719  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001171e  mov     [rsp+108h+var_E4], 0
0x180011726  mov     rcx, [rbx]
0x180011729  mov     rax, [rcx]
0x18001172c  lea     rdx, [rsp+108h+var_E4]
0x180011731  mov     rax, [rax+68h]
0x180011735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001173a  mov     rcx, [rsp+108h]; this
0x180011742  test    eax, eax
0x180011744  jns     short loc_18001175A
0x180011746  mov     r9d, eax; char *
0x180011749  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x180011750  mov     edx, 190h; void *
0x180011755  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001175a  mov     ebx, 4Eh ; 'N'
0x18001175f  mov     r8d, ebx; Size
0x180011762  xor     edx, edx; Val
0x180011764  lea     rcx, [rsp+108h+sz]; void *
0x180011769  call    memset_0
0x18001176e  lea     r8d, [rbx-27h]; cchMax
0x180011772  lea     rdx, [rsp+108h+sz]; lpsz
0x180011777  lea     rcx, [rsp+108h+rguid]; rguid
0x18001177c  call    cs:__imp_StringFromGUID2
0x180011782  lea     r8, [rsp+108h+sz]
0x180011787  mov     edx, 1B59h
0x18001178c  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x180011793  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x18001179a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001179f  mov     r8d, ebx; Size
0x1800117a2  xor     edx, edx; Val
0x1800117a4  lea     rcx, [rsp+108h+var_68]; void *
0x1800117ac  call    memset_0
0x1800117b1  lea     r8d, [rbx-27h]; cchMax
0x1800117b5  lea     rdx, [rsp+108h+var_68]; lpsz
0x1800117bd  lea     rcx, [rsp+108h+var_D0]; rguid
0x1800117c2  call    cs:__imp_StringFromGUID2
0x1800117c8  lea     r8, [rsp+108h+var_68]
0x1800117d0  mov     edx, 1B5Ah
0x1800117d5  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x1800117dc  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x1800117e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117e8  mov     edx, 1B5Bh
0x1800117ed  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x1800117f4  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x1800117fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011800  mov     ecx, [rsp+108h+var_E8]; enum NLM_CONNECTIVITY
0x180011804  call    ?PrintNetworkConnectivity@@YAXW4NLM_CONNECTIVITY@@@Z; PrintNetworkConnectivity(NLM_CONNECTIVITY)
0x180011809  mov     ebx, 0FA1h
0x18001180e  mov     edx, ebx
0x180011810  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x180011817  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x18001181e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011823  mov     edx, 1B5Ch
0x180011828  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x18001182f  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x180011836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001183b  mov     ecx, [rsp+108h+var_E4]; enum NLM_DOMAIN_TYPE
0x18001183f  call    ?PrintNetworkDomainType@@YAXW4NLM_DOMAIN_TYPE@@@Z; PrintNetworkDomainType(NLM_DOMAIN_TYPE)
0x180011844  mov     edx, ebx
0x180011846  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x18001184d  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x180011854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011859  nop
0x18001185a  jmp     short $+2
0x18001185c  mov     rcx, [rsp+108h+var_18]
0x180011864  xor     rcx, rsp; StackCookie
0x180011867  call    __security_check_cookie
0x18001186c  add     rsp, 100h
0x180011873  pop     rbx
0x180011874  retn
```
