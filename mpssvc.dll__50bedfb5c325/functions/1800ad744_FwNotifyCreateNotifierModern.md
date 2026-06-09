# FwNotifyCreateNotifierModern

- ea: `0x1800ad744`
- end: `0x1800adb89`
- name: `FwNotifyCreateNotifierModern`
- size: `1093`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180053eb4`

## callees

- `0x18005b334`
- `0x180067c5c`
- `0x1800729c0`
- `0x18007a2e4`
- `0x1800ac938`
- `0x1800acd84`
- `0x1800ace70`
- `0x1800ace9c`
- `0x1800acee8`
- `0x1800ad27c`
- `0x1800ad4b8`
- `0x1800ad5d4`
- `0x1800ad744`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800ad9c1`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800ad9c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad7c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad96d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad9ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adb15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adb51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad7c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad96d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad9ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adb15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adb51`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall FwNotifyCreateNotifierModern(
        void *a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned __int64 a9,
        int a10)
{
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v16; // rax
  int v17; // ecx
  int v18; // eax
  unsigned int v19; // ebx
  const char *v20; // r9
  unsigned int LastError; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-C8h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-C8h]
  __int64 v26; // [rsp+30h] [rbp-B8h] BYREF
  _DWORD v27[5]; // [rsp+38h] [rbp-B0h] BYREF
  bool v28; // [rsp+4Ch] [rbp-9Ch]
  bool v29; // [rsp+4Dh] [rbp-9Bh]
  bool v30; // [rsp+4Eh] [rbp-9Ah]
  bool v31; // [rsp+4Fh] [rbp-99h]
  unsigned __int16 *v32[2]; // [rsp+50h] [rbp-98h] BYREF
  unsigned __int64 v33; // [rsp+60h] [rbp-88h] BYREF
  unsigned __int64 v34; // [rsp+68h] [rbp-80h]
  int v35; // [rsp+70h] [rbp-78h]
  bool v36; // [rsp+74h] [rbp-74h]
  bool v37; // [rsp+75h] [rbp-73h]
  bool v38; // [rsp+76h] [rbp-72h]
  bool v39; // [rsp+77h] [rbp-71h]
  HSTRING string; // [rsp+78h] [rbp-70h] BYREF
  void *phNewToken; // [rsp+80h] [rbp-68h] BYREF
  HANDLE hExistingToken; // [rsp+88h] [rbp-60h] BYREF
  _DWORD v43[5]; // [rsp+90h] [rbp-58h] BYREF
  bool v44; // [rsp+A4h] [rbp-44h]
  bool v45; // [rsp+A5h] [rbp-43h]
  char v46; // [rsp+A6h] [rbp-42h]
  bool v47; // [rsp+A7h] [rbp-41h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  hExistingToken = a1;
  v33 = a9;
  string = 0;
  v13 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((Microsoft::WRL::Wrappers::HString *)&string);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
      (const char *)(unsigned int)v13,
      TokenType);
    WindowsDeleteString(string);
    return v14;
  }
  *(_OWORD *)v32 = 0;
  v33 = a9;
  v16 = -1;
  do
    ++v16;
  while ( *(_WORD *)(a9 + 2 * v16) );
  v34 = v16;
  GetImageNameFromFullPath(v32, &v33);
  v43[0] = a3;
  v43[1] = a6;
  v43[2] = a7;
  v43[3] = a8;
  v43[4] = a10;
  v44 = a5 != 0;
  v17 = *(_DWORD *)(a2 + 72);
  v45 = (v17 & 8) != 0;
  v46 = BYTE1(v17) & 1;
  v47 = a4 != 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::GetImpl'::`2'::impl) )
  {
    phNewToken = 0;
    if ( !DuplicateTokenEx(hExistingToken, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x8E,
                    (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
                    v20);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      WindowsDeleteString(string);
      return LastError;
    }
    hExistingToken = 0;
    wil::impersonate_token(&hExistingToken, phNewToken);
    wil::CoCreateInstanceEx<Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog>((unsigned int)&v26);
    v27[0] = a3;
    v27[1] = a6;
    v27[2] = a7;
    v27[3] = a8;
    v27[4] = a10;
    v28 = v44;
    v29 = v45;
    v30 = v46 != 0;
    v31 = v47;
    v33 = 16;
    NetworkingTriageScenario::FirewallUX::DialogTriggered(
      (const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)&v33,
      (const struct NetworkingTriageScenario::FirewallUX::NotificationFields *)v27,
      v32[0]);
    v22 = (*(__int64 (__fastcall **)(__int64, _DWORD *, HSTRING))(*(_QWORD *)v26 + 48LL))(v26, v43, string);
    v23 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
        (const char *)(unsigned int)v22,
        TokenTypea);
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v26);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hExistingToken);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      WindowsDeleteString(string);
      return v23;
    }
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v26);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hExistingToken);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
  }
  else
  {
    wil::CoCreateInstanceEx<Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog>((unsigned int)&phNewToken);
    v33 = __PAIR64__(a6, a3);
    v34 = __PAIR64__(a8, a7);
    v35 = a10;
    v36 = v44;
    v37 = v45;
    v38 = v46 != 0;
    v39 = v47;
    hExistingToken = (HANDLE)16;
    NetworkingTriageScenario::FirewallUX::DialogTriggered(
      (const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)&hExistingToken,
      (const struct NetworkingTriageScenario::FirewallUX::NotificationFields *)&v33,
      v32[0]);
    v18 = (*(__int64 (__fastcall **)(void *, _DWORD *, HSTRING))(*(_QWORD *)phNewToken + 48LL))(phNewToken, v43, string);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
        (const char *)(unsigned int)v18,
        TokenType);
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&phNewToken);
      WindowsDeleteString(string);
      return v19;
    }
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&phNewToken);
  }
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x1800ad744  push    rbx
0x1800ad746  push    rsi
0x1800ad747  push    rdi
0x1800ad748  push    r12
0x1800ad74a  push    r13
0x1800ad74c  push    r14
0x1800ad74e  push    r15
0x1800ad750  sub     rsp, 0B0h
0x1800ad757  mov     rax, cs:__security_cookie
0x1800ad75e  xor     rax, rsp
0x1800ad761  mov     [rsp+0E8h+var_40], rax
0x1800ad769  mov     r12d, r9d
0x1800ad76c  mov     r15d, r8d
0x1800ad76f  mov     r13, rdx
0x1800ad772  mov     [rsp+0E8h+hExistingToken], rcx
0x1800ad77a  mov     rdi, [rsp+0E8h+arg_40]
0x1800ad782  mov     [rsp+0E8h+var_88], rdi
0x1800ad787  xor     esi, esi
0x1800ad789  mov     [rsp+0E8h+string], rsi
0x1800ad78e  lea     rdx, [rsp+0E8h+var_88]
0x1800ad793  lea     rcx, [rsp+0E8h+string]; this
0x1800ad798  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ad79d  mov     ebx, eax
0x1800ad79f  test    eax, eax
0x1800ad7a1  jns     short loc_1800AD7D6
0x1800ad7a3  mov     rcx, [rsp+0E8h]; this
0x1800ad7ab  mov     r9d, eax; char *
0x1800ad7ae  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800ad7b5  lea     edx, [rsi+76h]; void *
0x1800ad7b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad7bd  nop
0x1800ad7be  mov     rcx, [rsp+0E8h+string]; string
0x1800ad7c3  call    cs:__imp_WindowsDeleteString
0x1800ad7ca  nop     dword ptr [rax+rax+00h]
0x1800ad7cf  mov     eax, ebx
0x1800ad7d1  jmp     loc_1800ADB65
0x1800ad7d6  xorps   xmm0, xmm0
0x1800ad7d9  movups  xmmword ptr [rsp+0E8h+var_98], xmm0
0x1800ad7de  mov     [rsp+0E8h+var_88], rdi
0x1800ad7e3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ad7e7  inc     rax
0x1800ad7ea  cmp     [rdi+rax*2], si
0x1800ad7ee  jnz     short loc_1800AD7E7
0x1800ad7f0  mov     [rsp+0E8h+var_80], rax
0x1800ad7f5  lea     rdx, [rsp+0E8h+var_88]
0x1800ad7fa  lea     rcx, [rsp+0E8h+var_98]
0x1800ad7ff  call    ?GetImageNameFromFullPath@@YA?AV?$basic_zstring_view@G@wil@@AEBV12@@Z; GetImageNameFromFullPath(wil::basic_zstring_view<ushort> const &)
0x1800ad804  mov     [rsp+0E8h+var_58], r15d
0x1800ad80c  mov     ebx, [rsp+0E8h+arg_28]
0x1800ad813  mov     [rsp+0E8h+var_54], ebx
0x1800ad81a  mov     edi, [rsp+0E8h+arg_30]
0x1800ad821  mov     [rsp+0E8h+var_50], edi
0x1800ad828  mov     esi, [rsp+0E8h+arg_38]
0x1800ad82f  mov     [rsp+0E8h+var_4C], esi
0x1800ad836  mov     r14d, [rsp+0E8h+arg_48]
0x1800ad83e  mov     [rsp+0E8h+var_48], r14d
0x1800ad846  cmp     [rsp+0E8h+arg_20], 0
0x1800ad84e  setnbe  [rsp+0E8h+var_44]
0x1800ad856  mov     ecx, [r13+48h]
0x1800ad85a  mov     eax, ecx
0x1800ad85c  shr     eax, 3
0x1800ad85f  and     al, 1
0x1800ad861  mov     [rsp+0E8h+var_43], al
0x1800ad868  shr     ecx, 8
0x1800ad86b  and     cl, 1
0x1800ad86e  mov     [rsp+0E8h+var_42], cl
0x1800ad875  xor     r13d, r13d
0x1800ad878  test    r12d, r12d
0x1800ad87b  setnz   [rsp+0E8h+var_41]
0x1800ad883  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs> `wil::Feature<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::GetImpl(void)'::`2'::impl
0x1800ad88a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::__private_IsEnabled(void)
0x1800ad88f  test    al, al
0x1800ad891  jnz     loc_1800AD992
0x1800ad897  lea     r8d, [r13+4]
0x1800ad89b  lea     rcx, [rsp+0E8h+var_68]
0x1800ad8a3  call    ??$CoCreateInstanceEx@UIFirewallNotificationDialog@Firewall@NetworkUX@Internal@Windows@@@wil@@YA?A_PAEBU_GUID@@W4tagCLSCTX@@@Z
0x1800ad8a8  nop
0x1800ad8a9  mov     dword ptr [rsp+0E8h+var_88], r15d
0x1800ad8ae  mov     dword ptr [rsp+0E8h+var_88+4], ebx
0x1800ad8b2  mov     dword ptr [rsp+0E8h+var_80], edi
0x1800ad8b6  mov     dword ptr [rsp+0E8h+var_80+4], esi
0x1800ad8ba  mov     [rsp+0E8h+var_78], r14d
0x1800ad8bf  cmp     [rsp+0E8h+var_44], r13b
0x1800ad8c7  setnz   [rsp+0E8h+var_74]
0x1800ad8cc  cmp     [rsp+0E8h+var_43], r13b
0x1800ad8d4  setnz   [rsp+0E8h+var_73]
0x1800ad8d9  cmp     [rsp+0E8h+var_42], r13b
0x1800ad8e1  setnz   [rsp+0E8h+var_72]
0x1800ad8e6  cmp     [rsp+0E8h+var_41], r13b
0x1800ad8ee  setnz   [rsp+0E8h+var_71]
0x1800ad8f3  mov     [rsp+0E8h+hExistingToken], 10h
0x1800ad8ff  mov     r8, [rsp+0E8h+var_98]; unsigned __int16 *
0x1800ad904  lea     rdx, [rsp+0E8h+var_88]; struct NetworkingTriageScenario::FirewallUX::NotificationFields *
0x1800ad909  lea     rcx, [rsp+0E8h+hExistingToken]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x1800ad911  call    ?DialogTriggered@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@AEBUNotificationFields@12@PEBG@Z; NetworkingTriageScenario::FirewallUX::DialogTriggered(NetworkingTriageScenario::FirewallUX::RequiredFields const &,NetworkingTriageScenario::FirewallUX::NotificationFields const &,ushort const *)
0x1800ad916  mov     rcx, [rsp+0E8h+var_68]
0x1800ad91e  mov     rax, [rcx]
0x1800ad921  mov     r8, [rsp+0E8h+string]
0x1800ad926  lea     rdx, [rsp+0E8h+var_58]
0x1800ad92e  mov     rax, [rax+30h]
0x1800ad932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad937  mov     ebx, eax
0x1800ad939  test    eax, eax
0x1800ad93b  jns     short loc_1800AD980
0x1800ad93d  mov     rcx, [rsp+0E8h]; this
0x1800ad945  mov     r9d, eax; char *
0x1800ad948  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800ad94f  mov     edx, 0B9h; void *
0x1800ad954  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad959  nop
0x1800ad95a  lea     rcx, [rsp+0E8h+var_68]
0x1800ad962  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800ad967  nop
0x1800ad968  mov     rcx, [rsp+0E8h+string]; string
0x1800ad96d  call    cs:__imp_WindowsDeleteString
0x1800ad974  nop     dword ptr [rax+rax+00h]
0x1800ad979  mov     eax, ebx
0x1800ad97b  jmp     loc_1800ADB65
0x1800ad980  lea     rcx, [rsp+0E8h+var_68]
0x1800ad988  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800ad98d  jmp     loc_1800ADB4C
0x1800ad992  mov     [rsp+0E8h+var_68], r13
0x1800ad99a  lea     rax, [rsp+0E8h+var_68]
0x1800ad9a2  mov     [rsp+0E8h+phNewToken], rax; phNewToken
0x1800ad9a7  mov     r9d, 2; ImpersonationLevel
0x1800ad9ad  mov     [rsp+0E8h+TokenType], r9d; int
0x1800ad9b2  xor     r8d, r8d; lpTokenAttributes
0x1800ad9b5  lea     edx, [r9+0Ah]; dwDesiredAccess
0x1800ad9b9  mov     rcx, [rsp+0E8h+hExistingToken]; hExistingToken
0x1800ad9c1  call    cs:__imp_DuplicateTokenEx
0x1800ad9c8  nop     dword ptr [rax+rax+00h]
0x1800ad9cd  test    eax, eax
0x1800ad9cf  jnz     short loc_1800ADA12
0x1800ad9d1  mov     rcx, [rsp+0E8h]; this
0x1800ad9d9  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800ad9e0  mov     edx, 8Eh; void *
0x1800ad9e5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ad9ea  mov     ebx, eax
0x1800ad9ec  lea     rcx, [rsp+0E8h+var_68]
0x1800ad9f4  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ad9f9  nop
0x1800ad9fa  mov     rcx, [rsp+0E8h+string]; string
0x1800ad9ff  call    cs:__imp_WindowsDeleteString
0x1800ada06  nop     dword ptr [rax+rax+00h]
0x1800ada0b  mov     eax, ebx
0x1800ada0d  jmp     loc_1800ADB65
0x1800ada12  mov     [rsp+0E8h+hExistingToken], r13
0x1800ada1a  mov     rdx, [rsp+0E8h+var_68]
0x1800ada22  lea     rcx, [rsp+0E8h+hExistingToken]
0x1800ada2a  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x1800ada2f  nop
0x1800ada30  mov     r8d, 100004h
0x1800ada36  lea     rcx, [rsp+0E8h+var_B8]
0x1800ada3b  call    ??$CoCreateInstanceEx@UIFirewallNotificationDialog@Firewall@NetworkUX@Internal@Windows@@@wil@@YA?A_PAEBU_GUID@@W4tagCLSCTX@@@Z
0x1800ada40  nop
0x1800ada41  mov     [rsp+0E8h+var_B0], r15d
0x1800ada46  mov     [rsp+0E8h+var_AC], ebx
0x1800ada4a  mov     [rsp+0E8h+var_A8], edi
0x1800ada4e  mov     [rsp+0E8h+var_A4], esi
0x1800ada52  mov     [rsp+0E8h+var_A0], r14d
0x1800ada57  cmp     [rsp+0E8h+var_44], r13b
0x1800ada5f  setnz   [rsp+0E8h+var_9C]
0x1800ada64  cmp     [rsp+0E8h+var_43], r13b
0x1800ada6c  setnz   [rsp+0E8h+var_9B]
0x1800ada71  cmp     [rsp+0E8h+var_42], r13b
0x1800ada79  setnz   [rsp+0E8h+var_9A]
0x1800ada7e  cmp     [rsp+0E8h+var_41], r13b
0x1800ada86  setnz   [rsp+0E8h+var_99]
0x1800ada8b  mov     [rsp+0E8h+var_88], 10h
0x1800ada94  mov     r8, [rsp+0E8h+var_98]; unsigned __int16 *
0x1800ada99  lea     rdx, [rsp+0E8h+var_B0]; struct NetworkingTriageScenario::FirewallUX::NotificationFields *
0x1800ada9e  lea     rcx, [rsp+0E8h+var_88]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x1800adaa3  call    ?DialogTriggered@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@AEBUNotificationFields@12@PEBG@Z; NetworkingTriageScenario::FirewallUX::DialogTriggered(NetworkingTriageScenario::FirewallUX::RequiredFields const &,NetworkingTriageScenario::FirewallUX::NotificationFields const &,ushort const *)
0x1800adaa8  mov     rcx, [rsp+0E8h+var_B8]
0x1800adaad  mov     rax, [rcx]
0x1800adab0  mov     r8, [rsp+0E8h+string]
0x1800adab5  lea     rdx, [rsp+0E8h+var_58]
0x1800adabd  mov     rax, [rax+30h]
0x1800adac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adac6  mov     ebx, eax
0x1800adac8  test    eax, eax
0x1800adaca  jns     short loc_1800ADB25
0x1800adacc  mov     rcx, [rsp+0E8h]; this
0x1800adad4  mov     r9d, eax; char *
0x1800adad7  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800adade  mov     edx, 0A4h; void *
0x1800adae3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adae8  nop
0x1800adae9  lea     rcx, [rsp+0E8h+var_B8]
0x1800adaee  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800adaf3  nop
0x1800adaf4  lea     rcx, [rsp+0E8h+hExistingToken]
0x1800adafc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800adb01  nop
0x1800adb02  lea     rcx, [rsp+0E8h+var_68]
0x1800adb0a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800adb0f  nop
0x1800adb10  mov     rcx, [rsp+0E8h+string]; string
0x1800adb15  call    cs:__imp_WindowsDeleteString
0x1800adb1c  nop     dword ptr [rax+rax+00h]
0x1800adb21  mov     eax, ebx
0x1800adb23  jmp     short loc_1800ADB65
0x1800adb25  lea     rcx, [rsp+0E8h+var_B8]
0x1800adb2a  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800adb2f  nop
0x1800adb30  lea     rcx, [rsp+0E8h+hExistingToken]
0x1800adb38  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800adb3d  nop
0x1800adb3e  lea     rcx, [rsp+0E8h+var_68]
0x1800adb46  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800adb4b  nop
0x1800adb4c  mov     rcx, [rsp+0E8h+string]; string
0x1800adb51  call    cs:__imp_WindowsDeleteString
0x1800adb58  nop     dword ptr [rax+rax+00h]
0x1800adb5d  xor     eax, eax
0x1800adb5f  jmp     short loc_1800ADB65
0x1800adb61  mov     eax, dword ptr [rsp+0E8h+string]
0x1800adb65  mov     rcx, [rsp+0E8h+var_40]
0x1800adb6d  xor     rcx, rsp; StackCookie
0x1800adb70  call    __security_check_cookie
0x1800adb75  add     rsp, 0B0h
0x1800adb7c  pop     r15
0x1800adb7e  pop     r14
0x1800adb80  pop     r13
0x1800adb82  pop     r12
0x1800adb84  pop     rdi
0x1800adb85  pop     rsi
0x1800adb86  pop     rbx
0x1800adb87  retn
```
