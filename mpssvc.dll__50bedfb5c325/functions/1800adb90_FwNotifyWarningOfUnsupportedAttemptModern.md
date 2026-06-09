# FwNotifyWarningOfUnsupportedAttemptModern

- ea: `0x1800adb90`
- end: `0x1800adf39`
- name: `FwNotifyWarningOfUnsupportedAttemptModern`
- size: `937`
- prototype: `__int64 __fastcall(HANDLE hExistingToken)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a1918`

## callees

- `0x18005b334`
- `0x180067c5c`
- `0x1800729c0`
- `0x18007a2e4`
- `0x1800ac9cc`
- `0x1800acd84`
- `0x1800ace70`
- `0x1800ace9c`
- `0x1800acee8`
- `0x1800ad27c`
- `0x1800ad4b8`
- `0x1800ad5d4`
- `0x1800adb90`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800adbf6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800adbf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adc92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800add5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800add97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ade1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adef0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adc92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800add5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800add97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ade1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adef0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall FwNotifyWarningOfUnsupportedAttemptModern(HANDLE hExistingToken, unsigned __int16 *a2)
{
  const char *v4; // r9
  unsigned int LastError; // ebx
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rax
  int v15; // eax
  unsigned int v16; // ebx
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-78h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-78h]
  unsigned __int16 *v19[2]; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int16 *v20[2]; // [rsp+40h] [rbp-58h] BYREF
  _QWORD v21[2]; // [rsp+58h] [rbp-40h] BYREF
  HSTRING string; // [rsp+68h] [rbp-30h] BYREF
  __int64 v23; // [rsp+70h] [rbp-28h] BYREF
  void *phNewToken; // [rsp+78h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v21[0] = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::GetImpl'::`2'::impl) )
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
    v23 = 0;
    wil::impersonate_token(&v23, phNewToken);
    wil::CoCreateInstanceEx<Windows::Internal::NetworkUX::Firewall::IFirewallWarningDialog>((unsigned int)v19);
    string = 0;
    v7 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((Microsoft::WRL::Wrappers::HString *)&string);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
        (const char *)(unsigned int)v7,
        TokenTypea);
      WindowsDeleteString(string);
      string = 0;
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(v19);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v23);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      return v8;
    }
    *(_OWORD *)v20 = 0;
    v21[0] = a2;
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    v21[1] = v9;
    GetImageNameFromFullPath(v20, v21);
    v21[0] = 0x100000010LL;
    NetworkingTriageScenario::FirewallUX::DialogTriggered(
      (const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)v21,
      (const struct NetworkingTriageScenario::FirewallUX::NotificationFields *)v20,
      v20[0]);
    v10 = (*(__int64 (__fastcall **)(unsigned __int16 *, HSTRING))(*(_QWORD *)v19[0] + 48LL))(v19[0], string);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
        (const char *)(unsigned int)v10,
        TokenTypea);
      WindowsDeleteString(string);
      string = 0;
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(v19);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v23);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      return v11;
    }
    WindowsDeleteString(string);
    string = 0;
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(v19);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v23);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
  }
  else
  {
    wil::CoCreateInstanceEx<Windows::Internal::NetworkUX::Firewall::IFirewallWarningDialog>((unsigned int)&v23);
    string = 0;
    v12 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((Microsoft::WRL::Wrappers::HString *)&string);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
        (const char *)(unsigned int)v12,
        TokenType);
      WindowsDeleteString(string);
      string = 0;
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v23);
      return v13;
    }
    *(_OWORD *)v19 = 0;
    v20[0] = a2;
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    v20[1] = (unsigned __int16 *)v14;
    GetImageNameFromFullPath(v19, v20);
    v21[0] = 0x100000010LL;
    NetworkingTriageScenario::FirewallUX::DialogTriggered(
      (const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)v21,
      (const struct NetworkingTriageScenario::FirewallUX::NotificationFields *)v20,
      v19[0]);
    v15 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v23 + 48LL))(v23, string);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
        (const char *)(unsigned int)v15,
        TokenType);
      WindowsDeleteString(string);
      string = 0;
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v23);
      return v16;
    }
    WindowsDeleteString(string);
    string = 0;
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v23);
  }
  return 0;
}

```

## disassembly

```asm
0x1800adb90  mov     [rsp+arg_10], rbx
0x1800adb95  mov     [rsp+arg_18], rsi
0x1800adb9a  push    rdi
0x1800adb9b  sub     rsp, 90h
0x1800adba2  mov     rax, cs:__security_cookie
0x1800adba9  xor     rax, rsp
0x1800adbac  mov     [rsp+98h+var_18], rax
0x1800adbb4  mov     rbx, rdx
0x1800adbb7  mov     rdi, rcx
0x1800adbba  mov     [rsp+98h+var_40], rdx
0x1800adbbf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs> `wil::Feature<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::GetImpl(void)'::`2'::impl
0x1800adbc6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::__private_IsEnabled(void)
0x1800adbcb  xor     esi, esi
0x1800adbcd  test    al, al
0x1800adbcf  jz      loc_1800ADDCD
0x1800adbd5  mov     [rsp+98h+var_20], rsi
0x1800adbda  lea     rax, [rsp+98h+var_20]
0x1800adbdf  mov     [rsp+98h+phNewToken], rax; phNewToken
0x1800adbe4  lea     r9d, [rsi+2]; ImpersonationLevel
0x1800adbe8  mov     [rsp+98h+TokenType], r9d; int
0x1800adbed  xor     r8d, r8d; lpTokenAttributes
0x1800adbf0  lea     edx, [rsi+0Ch]; dwDesiredAccess
0x1800adbf3  mov     rcx, rdi; hExistingToken
0x1800adbf6  call    cs:__imp_DuplicateTokenEx
0x1800adbfd  nop     dword ptr [rax+rax+00h]
0x1800adc02  test    eax, eax
0x1800adc04  jnz     short loc_1800ADC30
0x1800adc06  mov     rcx, [rsp+98h]; this
0x1800adc0e  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800adc15  lea     edx, [rsi+44h]; void *
0x1800adc18  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800adc1d  mov     ebx, eax
0x1800adc1f  lea     rcx, [rsp+98h+var_20]
0x1800adc24  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800adc29  mov     eax, ebx
0x1800adc2b  jmp     loc_1800ADF13
0x1800adc30  mov     [rsp+98h+var_28], rsi
0x1800adc35  mov     rdx, [rsp+98h+var_20]
0x1800adc3a  lea     rcx, [rsp+98h+var_28]
0x1800adc3f  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x1800adc44  nop
0x1800adc45  mov     r8d, 100004h
0x1800adc4b  lea     rcx, [rsp+98h+var_68]
0x1800adc50  call    ??$CoCreateInstanceEx@UIFirewallWarningDialog@Firewall@NetworkUX@Internal@Windows@@@wil@@YA?A_PAEBU_GUID@@W4tagCLSCTX@@@Z
0x1800adc55  nop
0x1800adc56  mov     [rsp+98h+string], rsi
0x1800adc5b  lea     rdx, [rsp+98h+var_40]
0x1800adc60  lea     rcx, [rsp+98h+string]; this
0x1800adc65  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800adc6a  mov     edi, eax
0x1800adc6c  test    eax, eax
0x1800adc6e  jns     short loc_1800ADCCA
0x1800adc70  mov     rcx, [rsp+98h]; this
0x1800adc78  mov     r9d, eax; char *
0x1800adc7b  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800adc82  mov     edx, 4Ch ; 'L'; void *
0x1800adc87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adc8c  nop
0x1800adc8d  mov     rcx, [rsp+98h+string]; string
0x1800adc92  call    cs:__imp_WindowsDeleteString
0x1800adc99  nop     dword ptr [rax+rax+00h]
0x1800adc9e  mov     [rsp+98h+string], rsi
0x1800adca3  lea     rcx, [rsp+98h+var_68]
0x1800adca8  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800adcad  nop
0x1800adcae  lea     rcx, [rsp+98h+var_28]
0x1800adcb3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800adcb8  nop
0x1800adcb9  lea     rcx, [rsp+98h+var_20]
0x1800adcbe  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800adcc3  mov     eax, edi
0x1800adcc5  jmp     loc_1800ADF13
0x1800adcca  xorps   xmm0, xmm0
0x1800adccd  movups  xmmword ptr [rsp+98h+var_58], xmm0
0x1800adcd2  mov     [rsp+98h+var_40], rbx
0x1800adcd7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800adcdb  inc     rax
0x1800adcde  cmp     [rbx+rax*2], si
0x1800adce2  jnz     short loc_1800ADCDB
0x1800adce4  mov     [rsp+98h+var_38], rax
0x1800adce9  lea     rdx, [rsp+98h+var_40]
0x1800adcee  lea     rcx, [rsp+98h+var_58]
0x1800adcf3  call    ?GetImageNameFromFullPath@@YA?AV?$basic_zstring_view@G@wil@@AEBV12@@Z; GetImageNameFromFullPath(wil::basic_zstring_view<ushort> const &)
0x1800adcf8  mov     dword ptr [rsp+98h+var_40], 10h
0x1800add00  mov     dword ptr [rsp+98h+var_40+4], 1
0x1800add08  mov     r8, [rsp+98h+var_58]; unsigned __int16 *
0x1800add0d  lea     rdx, [rsp+98h+var_58]; struct NetworkingTriageScenario::FirewallUX::NotificationFields *
0x1800add12  lea     rcx, [rsp+98h+var_40]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x1800add17  call    ?DialogTriggered@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@AEBUNotificationFields@12@PEBG@Z; NetworkingTriageScenario::FirewallUX::DialogTriggered(NetworkingTriageScenario::FirewallUX::RequiredFields const &,NetworkingTriageScenario::FirewallUX::NotificationFields const &,ushort const *)
0x1800add1c  mov     rcx, [rsp+98h+var_68]
0x1800add21  mov     rax, [rcx]
0x1800add24  mov     rdx, [rsp+98h+string]
0x1800add29  mov     rax, [rax+30h]
0x1800add2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add32  mov     ebx, eax
0x1800add34  test    eax, eax
0x1800add36  jns     short loc_1800ADD92
0x1800add38  mov     rcx, [rsp+98h]; this
0x1800add40  mov     r9d, eax; char *
0x1800add43  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800add4a  mov     edx, 53h ; 'S'; void *
0x1800add4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800add54  nop
0x1800add55  mov     rcx, [rsp+98h+string]; string
0x1800add5a  call    cs:__imp_WindowsDeleteString
0x1800add61  nop     dword ptr [rax+rax+00h]
0x1800add66  mov     [rsp+98h+string], rsi
0x1800add6b  lea     rcx, [rsp+98h+var_68]
0x1800add70  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800add75  nop
0x1800add76  lea     rcx, [rsp+98h+var_28]
0x1800add7b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800add80  nop
0x1800add81  lea     rcx, [rsp+98h+var_20]
0x1800add86  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800add8b  mov     eax, ebx
0x1800add8d  jmp     loc_1800ADF13
0x1800add92  mov     rcx, [rsp+98h+string]; string
0x1800add97  call    cs:__imp_WindowsDeleteString
0x1800add9e  nop     dword ptr [rax+rax+00h]
0x1800adda3  mov     [rsp+98h+string], rsi
0x1800adda8  lea     rcx, [rsp+98h+var_68]
0x1800addad  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800addb2  nop
0x1800addb3  lea     rcx, [rsp+98h+var_28]
0x1800addb8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800addbd  nop
0x1800addbe  lea     rcx, [rsp+98h+var_20]
0x1800addc3  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800addc8  jmp     loc_1800ADF0B
0x1800addcd  mov     r8d, 4
0x1800addd3  lea     rcx, [rsp+98h+var_28]
0x1800addd8  call    ??$CoCreateInstanceEx@UIFirewallWarningDialog@Firewall@NetworkUX@Internal@Windows@@@wil@@YA?A_PAEBU_GUID@@W4tagCLSCTX@@@Z
0x1800adddd  nop
0x1800addde  mov     [rsp+98h+string], rsi
0x1800adde3  lea     rdx, [rsp+98h+var_40]
0x1800adde8  lea     rcx, [rsp+98h+string]; this
0x1800added  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800addf2  mov     edi, eax
0x1800addf4  test    eax, eax
0x1800addf6  jns     short loc_1800ADE3C
0x1800addf8  mov     rcx, [rsp+98h]; this
0x1800ade00  mov     r9d, eax; char *
0x1800ade03  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800ade0a  mov     edx, 5Ah ; 'Z'; void *
0x1800ade0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ade14  nop
0x1800ade15  mov     rcx, [rsp+98h+string]; string
0x1800ade1a  call    cs:__imp_WindowsDeleteString
0x1800ade21  nop     dword ptr [rax+rax+00h]
0x1800ade26  mov     [rsp+98h+string], rsi
0x1800ade2b  lea     rcx, [rsp+98h+var_28]
0x1800ade30  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800ade35  mov     eax, edi
0x1800ade37  jmp     loc_1800ADF13
0x1800ade3c  xorps   xmm0, xmm0
0x1800ade3f  movups  xmmword ptr [rsp+98h+var_68], xmm0
0x1800ade44  mov     [rsp+98h+var_58], rbx
0x1800ade49  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ade4d  inc     rax
0x1800ade50  cmp     [rbx+rax*2], si
0x1800ade54  jnz     short loc_1800ADE4D
0x1800ade56  mov     [rsp+98h+var_58+8], rax
0x1800ade5b  lea     rdx, [rsp+98h+var_58]
0x1800ade60  lea     rcx, [rsp+98h+var_68]
0x1800ade65  call    ?GetImageNameFromFullPath@@YA?AV?$basic_zstring_view@G@wil@@AEBV12@@Z; GetImageNameFromFullPath(wil::basic_zstring_view<ushort> const &)
0x1800ade6a  mov     dword ptr [rsp+98h+var_40], 10h
0x1800ade72  mov     dword ptr [rsp+98h+var_40+4], 1
0x1800ade7a  mov     r8, [rsp+98h+var_68]; unsigned __int16 *
0x1800ade7f  lea     rdx, [rsp+98h+var_58]; struct NetworkingTriageScenario::FirewallUX::NotificationFields *
0x1800ade84  lea     rcx, [rsp+98h+var_40]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x1800ade89  call    ?DialogTriggered@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@AEBUNotificationFields@12@PEBG@Z; NetworkingTriageScenario::FirewallUX::DialogTriggered(NetworkingTriageScenario::FirewallUX::RequiredFields const &,NetworkingTriageScenario::FirewallUX::NotificationFields const &,ushort const *)
0x1800ade8e  mov     rcx, [rsp+98h+var_28]
0x1800ade93  mov     rax, [rcx]
0x1800ade96  mov     rdx, [rsp+98h+string]
0x1800ade9b  mov     rax, [rax+30h]
0x1800ade9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adea4  mov     ebx, eax
0x1800adea6  test    eax, eax
0x1800adea8  jns     short loc_1800ADEEB
0x1800adeaa  mov     rcx, [rsp+98h]; this
0x1800adeb2  mov     r9d, eax; char *
0x1800adeb5  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800adebc  mov     edx, 61h ; 'a'; void *
0x1800adec1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adec6  nop
0x1800adec7  mov     rcx, [rsp+98h+string]; string
0x1800adecc  call    cs:__imp_WindowsDeleteString
0x1800aded3  nop     dword ptr [rax+rax+00h]
0x1800aded8  mov     [rsp+98h+string], rsi
0x1800adedd  lea     rcx, [rsp+98h+var_28]
0x1800adee2  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800adee7  mov     eax, ebx
0x1800adee9  jmp     short loc_1800ADF13
0x1800adeeb  mov     rcx, [rsp+98h+string]; string
0x1800adef0  call    cs:__imp_WindowsDeleteString
0x1800adef7  nop     dword ptr [rax+rax+00h]
0x1800adefc  mov     [rsp+98h+string], rsi
0x1800adf01  lea     rcx, [rsp+98h+var_28]
0x1800adf06  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800adf0b  xor     eax, eax
0x1800adf0d  jmp     short loc_1800ADF13
0x1800adf0f  mov     eax, dword ptr [rsp+98h+string]
0x1800adf13  mov     rcx, [rsp+98h+var_18]
0x1800adf1b  xor     rcx, rsp; StackCookie
0x1800adf1e  call    __security_check_cookie
0x1800adf23  lea     r11, [rsp+98h+var_8]
0x1800adf2b  mov     rbx, [r11+20h]
0x1800adf2f  mov     rsi, [r11+28h]
0x1800adf33  mov     rsp, r11
0x1800adf36  pop     rdi
0x1800adf37  retn
```
