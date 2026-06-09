# FwNotifyWarningOfUnsupportedAttemptModern

- ea: `0x1800a7f20`
- end: `0x1800a82a0`
- name: `FwNotifyWarningOfUnsupportedAttemptModern`
- size: `896`
- prototype: `__int64 __fastcall(HANDLE hExistingToken)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009c4e8`

## callees

- `0x180056974`
- `0x18006444c`
- `0x18006f520`
- `0x180076bb4`
- `0x1800a6d40`
- `0x1800a6df8`
- `0x1800a719c`
- `0x1800a727c`
- `0x1800a72a0`
- `0x1800a72e8`
- `0x1800a7678`
- `0x1800a7888`
- `0x1800a79a0`
- `0x1800a7f20`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800a7f7f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800a7f7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a801d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a80db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a819b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8265`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a801d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a80db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a819b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8265`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall FwNotifyWarningOfUnsupportedAttemptModern(HANDLE hExistingToken, __int64 a2)
{
  __int64 v3; // rdx
  const char *v4; // r9
  unsigned int LastError; // ebx
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // ebx
  void *v10; // rdx
  int v11; // eax
  unsigned int v12; // ebx
  void *v13; // rdx
  void *v14; // rdx
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-78h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-78h]
  __int64 v21; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int16 *v22[2]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v23[24]; // [rsp+48h] [rbp-50h] BYREF
  __int64 v24; // [rsp+60h] [rbp-38h] BYREF
  HSTRING string; // [rsp+68h] [rbp-30h] BYREF
  HANDLE v26; // [rsp+70h] [rbp-28h] BYREF
  void *phNewToken; // [rsp+78h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v24 = a2;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::GetImpl'::`2'::impl) )
  {
    phNewToken = 0;
    if ( !DuplicateTokenEx(hExistingToken, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x44,
                    (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
                    v4);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      return LastError;
    }
    v26 = 0;
    wil::impersonate_token(&v26, phNewToken);
    wil::CoCreateInstanceEx<Windows::Internal::NetworkUX::Firewall::IFirewallWarningDialog>(&v21, v7, 0x100004u);
    string = 0;
    v8 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((Microsoft::WRL::Wrappers::HString *)&string);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
        (const char *)(unsigned int)v8,
        TokenTypea);
      WindowsDeleteString(string);
      string = 0;
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v21);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
        &v26,
        v10);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      return v9;
    }
    *(_OWORD *)v22 = 0;
    wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(v23, &v24);
    GetImageNameFromFullPath(v22, v23);
    v24 = 0x100000010LL;
    NetworkingTriageScenario::FirewallUX::DialogTriggered(
      (const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)&v24,
      (const struct NetworkingTriageScenario::FirewallUX::NotificationFields *)v23,
      v22[0]);
    v11 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v21 + 48LL))(v21, string);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
        (const char *)(unsigned int)v11,
        TokenTypea);
      WindowsDeleteString(string);
      string = 0;
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v21);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
        &v26,
        v13);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      return v12;
    }
    WindowsDeleteString(string);
    string = 0;
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v21);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
      &v26,
      v14);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
  }
  else
  {
    wil::CoCreateInstanceEx<Windows::Internal::NetworkUX::Firewall::IFirewallWarningDialog>(&v26, v3, 4u);
    string = 0;
    v15 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((Microsoft::WRL::Wrappers::HString *)&string);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
        (const char *)(unsigned int)v15,
        TokenType);
      WindowsDeleteString(string);
      string = 0;
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>((__int64 *)&v26);
      return v16;
    }
    *(_OWORD *)v22 = 0;
    wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(v23, &v24);
    GetImageNameFromFullPath(v22, v23);
    v24 = 0x100000010LL;
    NetworkingTriageScenario::FirewallUX::DialogTriggered(
      (const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)&v24,
      (const struct NetworkingTriageScenario::FirewallUX::NotificationFields *)v23,
      v22[0]);
    v17 = (*(__int64 (__fastcall **)(HANDLE, HSTRING))(*(_QWORD *)v26 + 48LL))(v26, string);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
        (const char *)(unsigned int)v17,
        TokenType);
      WindowsDeleteString(string);
      string = 0;
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>((__int64 *)&v26);
      return v18;
    }
    WindowsDeleteString(string);
    string = 0;
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>((__int64 *)&v26);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a7f20  push    rbx
0x1800a7f22  sub     rsp, 90h
0x1800a7f29  mov     rax, cs:__security_cookie
0x1800a7f30  xor     rax, rsp
0x1800a7f33  mov     [rsp+98h+var_18], rax
0x1800a7f3b  mov     rbx, rcx
0x1800a7f3e  mov     [rsp+98h+var_38], rdx
0x1800a7f43  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs> `wil::Feature<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::GetImpl(void)'::`2'::impl
0x1800a7f4a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::__private_IsEnabled(void)
0x1800a7f4f  test    al, al
0x1800a7f51  jz      loc_1800A814A
0x1800a7f57  mov     [rsp+98h+var_20], 0
0x1800a7f60  lea     rax, [rsp+98h+var_20]
0x1800a7f65  mov     [rsp+98h+phNewToken], rax; phNewToken
0x1800a7f6a  mov     r9d, 2; ImpersonationLevel
0x1800a7f70  mov     [rsp+98h+TokenType], r9d; int
0x1800a7f75  xor     r8d, r8d; lpTokenAttributes
0x1800a7f78  lea     edx, [r9+0Ah]; dwDesiredAccess
0x1800a7f7c  mov     rcx, rbx; hExistingToken
0x1800a7f7f  call    cs:__imp_DuplicateTokenEx
0x1800a7f85  test    eax, eax
0x1800a7f87  jnz     short loc_1800A7FB3
0x1800a7f89  mov     rcx, [rsp+98h]; this
0x1800a7f91  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800a7f98  lea     edx, [rax+44h]; void *
0x1800a7f9b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a7fa0  mov     ebx, eax
0x1800a7fa2  lea     rcx, [rsp+98h+var_20]
0x1800a7fa7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a7fac  mov     eax, ebx
0x1800a7fae  jmp     loc_1800A8286
0x1800a7fb3  mov     [rsp+98h+var_28], 0
0x1800a7fbc  mov     rdx, [rsp+98h+var_20]
0x1800a7fc1  lea     rcx, [rsp+98h+var_28]
0x1800a7fc6  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x1800a7fcb  nop
0x1800a7fcc  mov     r8d, 100004h
0x1800a7fd2  lea     rcx, [rsp+98h+var_68]
0x1800a7fd7  call    ??$CoCreateInstanceEx@UIFirewallWarningDialog@Firewall@NetworkUX@Internal@Windows@@@wil@@YA?A_PAEBU_GUID@@W4tagCLSCTX@@@Z
0x1800a7fdc  nop
0x1800a7fdd  mov     [rsp+98h+string], 0
0x1800a7fe6  lea     rdx, [rsp+98h+var_38]
0x1800a7feb  lea     rcx, [rsp+98h+string]; this
0x1800a7ff0  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a7ff5  mov     ebx, eax
0x1800a7ff7  test    eax, eax
0x1800a7ff9  jns     short loc_1800A8053
0x1800a7ffb  mov     rcx, [rsp+98h]; this
0x1800a8003  mov     r9d, eax; char *
0x1800a8006  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800a800d  mov     edx, 4Ch ; 'L'; void *
0x1800a8012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8017  nop
0x1800a8018  mov     rcx, [rsp+98h+string]; string
0x1800a801d  call    cs:__imp_WindowsDeleteString
0x1800a8023  mov     [rsp+98h+string], 0
0x1800a802c  lea     rcx, [rsp+98h+var_68]
0x1800a8031  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800a8036  nop
0x1800a8037  lea     rcx, [rsp+98h+var_28]
0x1800a803c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800a8041  nop
0x1800a8042  lea     rcx, [rsp+98h+var_20]
0x1800a8047  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a804c  mov     eax, ebx
0x1800a804e  jmp     loc_1800A8286
0x1800a8053  xorps   xmm0, xmm0
0x1800a8056  movups  xmmword ptr [rsp+98h+var_60], xmm0
0x1800a805b  lea     rdx, [rsp+98h+var_38]
0x1800a8060  lea     rcx, [rsp+98h+var_50]
0x1800a8065  call    ??$?0AEAPEBG$0A@@?$basic_zstring_view@G@wil@@QEAA@AEAPEBG@Z; wil::basic_zstring_view<ushort>::basic_zstring_view<ushort>(ushort const * &)
0x1800a806a  lea     rdx, [rsp+98h+var_50]
0x1800a806f  lea     rcx, [rsp+98h+var_60]
0x1800a8074  call    ?GetImageNameFromFullPath@@YA?AV?$basic_zstring_view@G@wil@@AEBV12@@Z; GetImageNameFromFullPath(wil::basic_zstring_view<ushort> const &)
0x1800a8079  mov     dword ptr [rsp+98h+var_38], 10h
0x1800a8081  mov     dword ptr [rsp+98h+var_38+4], 1
0x1800a8089  mov     r8, [rsp+98h+var_60]; unsigned __int16 *
0x1800a808e  lea     rdx, [rsp+98h+var_50]; struct NetworkingTriageScenario::FirewallUX::NotificationFields *
0x1800a8093  lea     rcx, [rsp+98h+var_38]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x1800a8098  call    ?DialogTriggered@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@AEBUNotificationFields@12@PEBG@Z; NetworkingTriageScenario::FirewallUX::DialogTriggered(NetworkingTriageScenario::FirewallUX::RequiredFields const &,NetworkingTriageScenario::FirewallUX::NotificationFields const &,ushort const *)
0x1800a809d  mov     rcx, [rsp+98h+var_68]
0x1800a80a2  mov     rax, [rcx]
0x1800a80a5  mov     rdx, [rsp+98h+string]
0x1800a80aa  mov     rax, [rax+30h]
0x1800a80ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a80b3  mov     ebx, eax
0x1800a80b5  test    eax, eax
0x1800a80b7  jns     short loc_1800A8111
0x1800a80b9  mov     rcx, [rsp+98h]; this
0x1800a80c1  mov     r9d, eax; char *
0x1800a80c4  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800a80cb  mov     edx, 53h ; 'S'; void *
0x1800a80d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a80d5  nop
0x1800a80d6  mov     rcx, [rsp+98h+string]; string
0x1800a80db  call    cs:__imp_WindowsDeleteString
0x1800a80e1  mov     [rsp+98h+string], 0
0x1800a80ea  lea     rcx, [rsp+98h+var_68]
0x1800a80ef  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800a80f4  nop
0x1800a80f5  lea     rcx, [rsp+98h+var_28]
0x1800a80fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800a80ff  nop
0x1800a8100  lea     rcx, [rsp+98h+var_20]
0x1800a8105  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a810a  mov     eax, ebx
0x1800a810c  jmp     loc_1800A8286
0x1800a8111  mov     rcx, [rsp+98h+string]; string
0x1800a8116  call    cs:__imp_WindowsDeleteString
0x1800a811c  mov     [rsp+98h+string], 0
0x1800a8125  lea     rcx, [rsp+98h+var_68]
0x1800a812a  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800a812f  nop
0x1800a8130  lea     rcx, [rsp+98h+var_28]
0x1800a8135  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800a813a  nop
0x1800a813b  lea     rcx, [rsp+98h+var_20]
0x1800a8140  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a8145  jmp     loc_1800A827E
0x1800a814a  mov     r8d, 4
0x1800a8150  lea     rcx, [rsp+98h+var_28]
0x1800a8155  call    ??$CoCreateInstanceEx@UIFirewallWarningDialog@Firewall@NetworkUX@Internal@Windows@@@wil@@YA?A_PAEBU_GUID@@W4tagCLSCTX@@@Z
0x1800a815a  nop
0x1800a815b  mov     [rsp+98h+string], 0
0x1800a8164  lea     rdx, [rsp+98h+var_38]
0x1800a8169  lea     rcx, [rsp+98h+string]; this
0x1800a816e  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a8173  mov     ebx, eax
0x1800a8175  test    eax, eax
0x1800a8177  jns     short loc_1800A81BB
0x1800a8179  mov     rcx, [rsp+98h]; this
0x1800a8181  mov     r9d, eax; char *
0x1800a8184  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800a818b  mov     edx, 5Ah ; 'Z'; void *
0x1800a8190  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8195  nop
0x1800a8196  mov     rcx, [rsp+98h+string]; string
0x1800a819b  call    cs:__imp_WindowsDeleteString
0x1800a81a1  mov     [rsp+98h+string], 0
0x1800a81aa  lea     rcx, [rsp+98h+var_28]
0x1800a81af  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800a81b4  mov     eax, ebx
0x1800a81b6  jmp     loc_1800A8286
0x1800a81bb  xorps   xmm0, xmm0
0x1800a81be  movups  xmmword ptr [rsp+98h+var_60], xmm0
0x1800a81c3  lea     rdx, [rsp+98h+var_38]
0x1800a81c8  lea     rcx, [rsp+98h+var_50]
0x1800a81cd  call    ??$?0AEAPEBG$0A@@?$basic_zstring_view@G@wil@@QEAA@AEAPEBG@Z; wil::basic_zstring_view<ushort>::basic_zstring_view<ushort>(ushort const * &)
0x1800a81d2  lea     rdx, [rsp+98h+var_50]
0x1800a81d7  lea     rcx, [rsp+98h+var_60]
0x1800a81dc  call    ?GetImageNameFromFullPath@@YA?AV?$basic_zstring_view@G@wil@@AEBV12@@Z; GetImageNameFromFullPath(wil::basic_zstring_view<ushort> const &)
0x1800a81e1  mov     dword ptr [rsp+98h+var_38], 10h
0x1800a81e9  mov     dword ptr [rsp+98h+var_38+4], 1
0x1800a81f1  mov     r8, [rsp+98h+var_60]; unsigned __int16 *
0x1800a81f6  lea     rdx, [rsp+98h+var_50]; struct NetworkingTriageScenario::FirewallUX::NotificationFields *
0x1800a81fb  lea     rcx, [rsp+98h+var_38]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x1800a8200  call    ?DialogTriggered@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@AEBUNotificationFields@12@PEBG@Z; NetworkingTriageScenario::FirewallUX::DialogTriggered(NetworkingTriageScenario::FirewallUX::RequiredFields const &,NetworkingTriageScenario::FirewallUX::NotificationFields const &,ushort const *)
0x1800a8205  mov     rcx, [rsp+98h+var_28]
0x1800a820a  mov     rax, [rcx]
0x1800a820d  mov     rdx, [rsp+98h+string]
0x1800a8212  mov     rax, [rax+30h]
0x1800a8216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a821b  mov     ebx, eax
0x1800a821d  test    eax, eax
0x1800a821f  jns     short loc_1800A8260
0x1800a8221  mov     rcx, [rsp+98h]; this
0x1800a8229  mov     r9d, eax; char *
0x1800a822c  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800a8233  mov     edx, 61h ; 'a'; void *
0x1800a8238  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a823d  nop
0x1800a823e  mov     rcx, [rsp+98h+string]; string
0x1800a8243  call    cs:__imp_WindowsDeleteString
0x1800a8249  mov     [rsp+98h+string], 0
0x1800a8252  lea     rcx, [rsp+98h+var_28]
0x1800a8257  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800a825c  mov     eax, ebx
0x1800a825e  jmp     short loc_1800A8286
0x1800a8260  mov     rcx, [rsp+98h+string]; string
0x1800a8265  call    cs:__imp_WindowsDeleteString
0x1800a826b  mov     [rsp+98h+string], 0
0x1800a8274  lea     rcx, [rsp+98h+var_28]
0x1800a8279  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800a827e  xor     eax, eax
0x1800a8280  jmp     short loc_1800A8286
0x1800a8282  mov     eax, dword ptr [rsp+98h+string]
0x1800a8286  mov     rcx, [rsp+98h+var_18]
0x1800a828e  xor     rcx, rsp; StackCookie
0x1800a8291  call    __security_check_cookie
0x1800a8296  add     rsp, 90h
0x1800a829d  pop     rbx
0x1800a829e  retn
```
