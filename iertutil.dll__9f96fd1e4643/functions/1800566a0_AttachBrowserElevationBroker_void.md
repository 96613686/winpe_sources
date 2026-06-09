# AttachBrowserElevationBroker(void)

- ea: `0x1800566a0`
- end: `0x180056989`
- name: `?AttachBrowserElevationBroker@@YAJXZ`
- size: `745`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180018410`
- `0x180031f00`
- `0x180051704`
- `0x1800566a0`
- `0x180057e48`
- `0x18005d720`
- `0x18005dfb0`
- `0x18005e040`
- `0x18005e278`
- `0x18005e8e4`
- `0x180083c10`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180056824`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180056824`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800568ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800568ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180056734`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800567a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800567da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180056734`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800567a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800567da`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800566fd`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800566fd`

## string_xrefs

- `0x1800566e1`: `onecoreuap\inetcore\iertutil\userbroker.cpp`
- `0x180056745`: `onecoreuap\inetcore\iertutil\userbroker.cpp`
- `0x18005676a`: `onecoreuap\inetcore\iertutil\userbroker.cpp`
- `0x180056806`: `onecoreuap\inetcore\iertutil\userbroker.cpp`
- `0x180056835`: `onecoreuap\inetcore\iertutil\userbroker.cpp`
- `0x1800568ec`: `onecoreuap\inetcore\iertutil\userbroker.cpp`
- `0x180056938`: `onecoreuap\inetcore\iertutil\userbroker.cpp`
- `0x1800567f7`: `Failed to launch browser_broker`

## pseudocode

```c
__int64 AttachBrowserElevationBroker(void)
{
  const char *v0; // r9
  HRESULT Instance; // eax
  unsigned int v2; // ebx
  const char *v3; // r9
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // rcx
  __int64 (__fastcall *v6)(LPVOID, _QWORD, WCHAR *, __int64); // r14
  __int64 String; // rsi
  __int64 v8; // rbx
  __int64 v9; // rdi
  DWORD CurrentProcessId; // eax
  int v11; // eax
  int v12; // eax
  unsigned int v13; // ebx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  const char *v17; // [rsp+28h] [rbp-D8h]
  __int64 v18; // [rsp+30h] [rbp-D0h]
  HRESULT v19; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v20; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !(unsigned __int8)IEConfiguration_GetBool(536870913) )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecoreuap\\inetcore\\iertutil\\userbroker.cpp",
      (const char *)0x8000000ELL,
      ppv);
  if ( GetSystemMetrics(0x2000) )
  {
    return (unsigned int)-2147023706;
  }
  else
  {
    if ( !g_pGIT )
    {
      Instance = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &g_pGIT);
      if ( Instance < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"onecoreuap\\inetcore\\iertutil\\userbroker.cpp",
          (const char *)(unsigned int)Instance,
          ppva);
    }
    if ( g_dwBrowserBrokerClassFactory_GITCookie )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\userbroker.cpp",
        v0);
    v20 = 0;
    v19 = CoCreateInstance(&CLSID_BrowserBroker, 0, 4u, &GUID_7179e7f6_4fe0_48b3_8b6a_bb413bf6ea0d, &v20);
    v2 = v19;
    if ( v19 < 0 )
    {
      BrowserTelemetry::ElevationBrokerAttach_FirstCoCreateFailed<long &>(&v19);
      v19 = CoCreateInstance(&CLSID_BrowserBroker, 0, 4u, &GUID_7179e7f6_4fe0_48b3_8b6a_bb413bf6ea0d, &v20);
      v2 = v19;
      BrowserTelemetry::ElevationBrokerAttach_SecondCoCreateResult<long &>(&v19);
    }
    wil::details::in1diag3::FailFast_IfFailedMsg(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\inetcore\\iertutil\\userbroker.cpp",
      (const char *)v2,
      (int)"Failed to launch browser_broker",
      v17);
    if ( !GetModuleFileNameW(0, Filename, 0x104u) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\userbroker.cpp",
        v3);
    v4 = -1;
    do
      ++v4;
    while ( Filename[v4] );
    if ( v4 > 0xC )
    {
      v5 = 2 * v4 - 36;
      if ( v5 >= 0x208 )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)Filename + v5) = 0;
    }
    v6 = *(__int64 (__fastcall **)(LPVOID, _QWORD, WCHAR *, __int64))(*(_QWORD *)v20 + 24LL);
    String = IEConfiguration_GetString(268435507);
    v8 = IEConfiguration_GetString(268435506);
    v9 = IEConfiguration_GetString(268435499);
    CurrentProcessId = GetCurrentProcessId();
    v18 = String;
    HIDWORD(v17) = HIDWORD(v8);
    v11 = v6(v20, CurrentProcessId, Filename, v9);
    if ( v11 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\userbroker.cpp",
        (const char *)(unsigned int)v11,
        (int)&word_1801758E4);
    v12 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, GUID *, unsigned int *))(*(_QWORD *)g_pGIT + 24LL))(
            g_pGIT,
            v20,
            &GUID_7179e7f6_4fe0_48b3_8b6a_bb413bf6ea0d,
            &g_dwBrowserBrokerClassFactory_GITCookie);
    if ( v12 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\userbroker.cpp",
        (const char *)(unsigned int)v12,
        (int)&word_1801758E4);
    v13 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
  }
  return v13;
}

```

## disassembly

```asm
0x1800566a0  push    rbp
0x1800566a2  push    rbx
0x1800566a3  push    rsi
0x1800566a4  push    rdi
0x1800566a5  push    r14
0x1800566a7  push    r15
0x1800566a9  lea     rbp, [rsp-178h]
0x1800566b1  sub     rsp, 278h
0x1800566b8  mov     rax, cs:__security_cookie
0x1800566bf  xor     rax, rsp
0x1800566c2  mov     [rbp+1A0h+var_40], rax
0x1800566c9  mov     ecx, 20000001h
0x1800566ce  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800566d3  xor     r15d, r15d
0x1800566d6  test    al, al
0x1800566d8  jnz     short loc_1800566F8
0x1800566da  mov     rcx, [rbp+1A8h]; this
0x1800566e1  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\iertutil\\userbro"...
0x1800566e8  mov     r9d, 8000000Eh; char *
0x1800566ee  lea     edx, [r15+66h]; void *
0x1800566f2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800566f8  mov     ecx, 2000h; nIndex
0x1800566fd  call    cs:__imp_GetSystemMetrics
0x180056703  test    eax, eax
0x180056705  jnz     loc_180056963
0x18005670b  cmp     cs:?g_pGIT@@3PEAUIGlobalInterfaceTable@@EA, r15; IGlobalInterfaceTable * g_pGIT
0x180056712  jnz     short loc_18005675A
0x180056714  xor     edx, edx; pUnkOuter
0x180056716  lea     rax, ?g_pGIT@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pGIT
0x18005671d  lea     r9, IID_IGlobalInterfaceTable; riid
0x180056724  mov     [rsp+2A0h+ppv], rax; int
0x180056729  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180056730  lea     r8d, [rdx+1]; dwClsContext
0x180056734  call    cs:__imp_CoCreateInstance
0x18005673a  test    eax, eax
0x18005673c  jns     short loc_18005675A
0x18005673e  mov     rcx, [rbp+1A8h]; this
0x180056745  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\iertutil\\userbro"...
0x18005674c  mov     r9d, eax; char *
0x18005674f  mov     edx, 71h ; 'q'; void *
0x180056754  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005675a  cmp     cs:?g_dwBrowserBrokerClassFactory_GITCookie@@3KA, r15d; ulong g_dwBrowserBrokerClassFactory_GITCookie
0x180056761  jz      short loc_18005677C
0x180056763  mov     rcx, [rbp+1A8h]; this
0x18005676a  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\iertutil\\userbro"...
0x180056771  mov     edx, 74h ; 't'; void *
0x180056776  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005677c  lea     rax, [rsp+2A0h+var_258]
0x180056781  mov     [rsp+2A0h+var_258], r15
0x180056786  mov     edi, 4
0x18005678b  mov     [rsp+2A0h+ppv], rax; ppv
0x180056790  mov     r8d, edi; dwClsContext
0x180056793  lea     r9, _GUID_7179e7f6_4fe0_48b3_8b6a_bb413bf6ea0d; riid
0x18005679a  xor     edx, edx; pUnkOuter
0x18005679c  lea     rcx, CLSID_BrowserBroker; rclsid
0x1800567a3  call    cs:__imp_CoCreateInstance
0x1800567a9  mov     [rsp+2A0h+var_260], eax
0x1800567ad  mov     ebx, eax
0x1800567af  test    eax, eax
0x1800567b1  jns     short loc_1800567F0
0x1800567b3  lea     rcx, [rsp+2A0h+var_260]
0x1800567b8  call    ??$ElevationBrokerAttach_FirstCoCreateFailed@AEAJ@BrowserTelemetry@@SAXAEAJ@Z; BrowserTelemetry::ElevationBrokerAttach_FirstCoCreateFailed<long &>(long &)
0x1800567bd  lea     rax, [rsp+2A0h+var_258]
0x1800567c2  mov     r8d, edi; dwClsContext
0x1800567c5  lea     r9, _GUID_7179e7f6_4fe0_48b3_8b6a_bb413bf6ea0d; riid
0x1800567cc  mov     [rsp+2A0h+ppv], rax; ppv
0x1800567d1  xor     edx, edx; pUnkOuter
0x1800567d3  lea     rcx, CLSID_BrowserBroker; rclsid
0x1800567da  call    cs:__imp_CoCreateInstance
0x1800567e0  lea     rcx, [rsp+2A0h+var_260]
0x1800567e5  mov     [rsp+2A0h+var_260], eax
0x1800567e9  mov     ebx, eax
0x1800567eb  call    ??$ElevationBrokerAttach_SecondCoCreateResult@AEAJ@BrowserTelemetry@@SAXAEAJ@Z; BrowserTelemetry::ElevationBrokerAttach_SecondCoCreateResult<long &>(long &)
0x1800567f0  mov     rcx, [rbp+1A8h]; this
0x1800567f7  lea     rax, aFailedToLaunch; "Failed to launch browser_broker"
0x1800567fe  mov     r9d, ebx; char *
0x180056801  mov     [rsp+2A0h+ppv], rax; int
0x180056806  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\iertutil\\userbro"...
0x18005680d  mov     edx, 8Dh; void *
0x180056812  call    ?FailFast_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180056817  mov     r8d, 104h; nSize
0x18005681d  lea     rdx, [rsp+2A0h+Filename]; lpFilename
0x180056822  xor     ecx, ecx; hModule
0x180056824  call    cs:__imp_GetModuleFileNameW
0x18005682a  test    eax, eax
0x18005682c  jnz     short loc_180056847
0x18005682e  mov     rcx, [rbp+1A8h]; this
0x180056835  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\iertutil\\userbro"...
0x18005683c  mov     edx, 91h; void *
0x180056841  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180056847  lea     rcx, [rsp+2A0h+Filename]
0x18005684c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180056850  inc     rax
0x180056853  cmp     [rcx+rax*2], r15w
0x180056858  jnz     short loc_180056850
0x18005685a  cmp     rax, 0Ch
0x18005685e  jbe     short loc_18005687B
0x180056860  lea     rcx, ds:0FFFFFFFFFFFFFFDCh[rax*2]
0x180056868  cmp     rcx, 208h
0x18005686f  jnb     loc_180056901
0x180056875  mov     [rsp+rcx+2A0h+Filename], r15w
0x18005687b  mov     rax, [rsp+2A0h+var_258]
0x180056880  mov     rcx, [rax]
0x180056883  mov     r14, [rcx+18h]
0x180056887  mov     ecx, 10000033h
0x18005688c  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x180056891  mov     ecx, 10000032h
0x180056896  mov     rsi, rax
0x180056899  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x18005689e  mov     ecx, 1000002Bh
0x1800568a3  mov     rbx, rax
0x1800568a6  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x1800568ab  mov     rdi, rax
0x1800568ae  call    cs:__imp_GetCurrentProcessId
0x1800568b4  lea     rcx, word_1801758E4
0x1800568bb  mov     [rsp+2A0h+var_270], rsi
0x1800568c0  mov     edx, eax
0x1800568c2  mov     [rsp+2A0h+var_278], rbx
0x1800568c7  mov     [rsp+2A0h+ppv], rcx; int
0x1800568cc  lea     r8, [rsp+2A0h+Filename]
0x1800568d1  mov     rcx, [rsp+2A0h+var_258]
0x1800568d6  mov     r9, rdi
0x1800568d9  mov     rax, r14
0x1800568dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800568e1  test    eax, eax
0x1800568e3  jns     short loc_180056907
0x1800568e5  mov     rcx, [rbp+1A8h]; this
0x1800568ec  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\iertutil\\userbro"...
0x1800568f3  mov     r9d, eax; char *
0x1800568f6  mov     edx, 9Eh; void *
0x1800568fb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180056901  call    __report_rangecheckfailure
0x180056907  mov     rcx, cs:?g_pGIT@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pGIT
0x18005690e  lea     r9, ?g_dwBrowserBrokerClassFactory_GITCookie@@3KA; ulong g_dwBrowserBrokerClassFactory_GITCookie
0x180056915  mov     rdx, [rsp+2A0h+var_258]
0x18005691a  lea     r8, _GUID_7179e7f6_4fe0_48b3_8b6a_bb413bf6ea0d
0x180056921  mov     rax, [rcx]
0x180056924  mov     rax, [rax+18h]
0x180056928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005692d  test    eax, eax
0x18005692f  jns     short loc_18005694D
0x180056931  mov     rcx, [rbp+1A8h]; this
0x180056938  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\iertutil\\userbro"...
0x18005693f  mov     r9d, eax; char *
0x180056942  mov     edx, 0A3h; void *
0x180056947  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005694d  mov     rcx, [rsp+2A0h+var_258]
0x180056952  mov     ebx, r15d
0x180056955  mov     rax, [rcx]
0x180056958  mov     rax, [rax+10h]
0x18005695c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056961  jmp     short loc_180056968
0x180056963  mov     ebx, 800704A6h
0x180056968  mov     eax, ebx
0x18005696a  mov     rcx, [rbp+1A0h+var_40]
0x180056971  xor     rcx, rsp; StackCookie
0x180056974  call    __security_check_cookie
0x180056979  add     rsp, 278h
0x180056980  pop     r15
0x180056982  pop     r14
0x180056984  pop     rdi
0x180056985  pop     rsi
0x180056986  pop     rbx
0x180056987  pop     rbp
0x180056988  retn
```
