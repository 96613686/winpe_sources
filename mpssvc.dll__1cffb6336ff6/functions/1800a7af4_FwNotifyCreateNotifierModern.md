# FwNotifyCreateNotifierModern

- ea: `0x1800a7af4`
- end: `0x1800a7f19`
- name: `FwNotifyCreateNotifierModern`
- size: `1061`
- prototype: `__int64 __usercall@<rax>(HANDLE hExistingToken@<rcx>, int, int, int, int, __int64, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005d6c4`

## callees

- `0x180056974`
- `0x18006444c`
- `0x18006f520`
- `0x180076bb4`
- `0x1800a6d40`
- `0x1800a6d64`
- `0x1800a719c`
- `0x1800a727c`
- `0x1800a72a0`
- `0x1800a72e8`
- `0x1800a7678`
- `0x1800a7888`
- `0x1800a79a0`
- `0x1800a7af4`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800a7d5f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800a7d5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7b73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7d16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7d9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7eae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7ee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7b73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7d16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7d9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7eae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7ee4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall FwNotifyCreateNotifierModern(
        HANDLE hExistingToken,
        __int64 a2,
        unsigned int a3,
        int a4,
        int a5,
        unsigned int a6,
        int a7,
        int a8,
        __int64 a9,
        int a10)
{
  int v14; // eax
  unsigned int v15; // ebx
  int v17; // ecx
  __int64 v18; // rdx
  int v19; // eax
  unsigned int v20; // ebx
  const char *v21; // r9
  unsigned int LastError; // ebx
  __int64 v23; // rdx
  int v24; // eax
  unsigned int v25; // ebx
  void *v26; // rdx
  void *v27; // rdx
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-C8h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-C8h]
  unsigned __int64 v30; // [rsp+30h] [rbp-B8h] BYREF
  int v31; // [rsp+38h] [rbp-B0h]
  int v32; // [rsp+3Ch] [rbp-ACh]
  int v33; // [rsp+40h] [rbp-A8h]
  bool v34; // [rsp+44h] [rbp-A4h]
  bool v35; // [rsp+45h] [rbp-A3h]
  bool v36; // [rsp+46h] [rbp-A2h]
  bool v37; // [rsp+47h] [rbp-A1h]
  __int64 v38; // [rsp+48h] [rbp-A0h] BYREF
  _DWORD v39[5]; // [rsp+50h] [rbp-98h] BYREF
  bool v40; // [rsp+64h] [rbp-84h]
  bool v41; // [rsp+65h] [rbp-83h]
  bool v42; // [rsp+66h] [rbp-82h]
  bool v43; // [rsp+67h] [rbp-81h]
  unsigned __int16 *v44[2]; // [rsp+68h] [rbp-80h] BYREF
  __int64 v45; // [rsp+78h] [rbp-70h] BYREF
  HSTRING string; // [rsp+80h] [rbp-68h] BYREF
  void *phNewToken; // [rsp+88h] [rbp-60h] BYREF
  _DWORD v48[5]; // [rsp+90h] [rbp-58h] BYREF
  bool v49; // [rsp+A4h] [rbp-44h]
  bool v50; // [rsp+A5h] [rbp-43h]
  char v51; // [rsp+A6h] [rbp-42h]
  bool v52; // [rsp+A7h] [rbp-41h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v45 = a9;
  string = 0;
  v14 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((Microsoft::WRL::Wrappers::HString *)&string);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
      (const char *)(unsigned int)v14,
      TokenType);
    WindowsDeleteString(string);
    return v15;
  }
  *(_OWORD *)v44 = 0;
  wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(&v30, &v45);
  GetImageNameFromFullPath(v44, &v30);
  v48[0] = a3;
  v48[1] = a6;
  v48[2] = a7;
  v48[3] = a8;
  v48[4] = a10;
  v49 = a5 != 0;
  v17 = *(_DWORD *)(a2 + 72);
  v50 = (v17 & 8) != 0;
  v51 = BYTE1(v17) & 1;
  v52 = a4 != 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::GetImpl'::`2'::impl) )
  {
    phNewToken = 0;
    if ( !DuplicateTokenEx(hExistingToken, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x8E,
                    (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
                    v21);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      WindowsDeleteString(string);
      return LastError;
    }
    v45 = 0;
    wil::impersonate_token(&v45, phNewToken);
    wil::CoCreateInstanceEx<Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog>(&v38, v23, 0x100004u);
    v39[0] = a3;
    v39[1] = a6;
    v39[2] = a7;
    v39[3] = a8;
    v39[4] = a10;
    v40 = v49;
    v41 = v50;
    v42 = v51 != 0;
    v43 = v52;
    v30 = 16;
    NetworkingTriageScenario::FirewallUX::DialogTriggered(
      (const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)&v30,
      (const struct NetworkingTriageScenario::FirewallUX::NotificationFields *)v39,
      v44[0]);
    v24 = (*(__int64 (__fastcall **)(__int64, _DWORD *, HSTRING))(*(_QWORD *)v38 + 48LL))(v38, v48, string);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
        (const char *)(unsigned int)v24,
        TokenTypea);
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v38);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
        (HANDLE *)&v45,
        v26);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      WindowsDeleteString(string);
      return v25;
    }
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v38);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
      (HANDLE *)&v45,
      v27);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
  }
  else
  {
    wil::CoCreateInstanceEx<Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog>(&phNewToken, v18, 4u);
    v30 = __PAIR64__(a6, a3);
    v31 = a7;
    v32 = a8;
    v33 = a10;
    v34 = v49;
    v35 = v50;
    v36 = v51 != 0;
    v37 = v52;
    v45 = 16;
    NetworkingTriageScenario::FirewallUX::DialogTriggered(
      (const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)&v45,
      (const struct NetworkingTriageScenario::FirewallUX::NotificationFields *)&v30,
      v44[0]);
    v19 = (*(__int64 (__fastcall **)(void *, _DWORD *, HSTRING))(*(_QWORD *)phNewToken + 48LL))(phNewToken, v48, string);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_modern_notify.cpp",
        (const char *)(unsigned int)v19,
        TokenType);
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>((__int64 *)&phNewToken);
      WindowsDeleteString(string);
      return v20;
    }
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>((__int64 *)&phNewToken);
  }
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x1800a7af4  mov     r11, rsp
0x1800a7af7  push    rbx
0x1800a7af8  push    rsi
0x1800a7af9  push    rdi
0x1800a7afa  push    r12
0x1800a7afc  push    r13
0x1800a7afe  push    r14
0x1800a7b00  push    r15
0x1800a7b02  sub     rsp, 0B0h
0x1800a7b09  mov     rax, cs:__security_cookie
0x1800a7b10  xor     rax, rsp
0x1800a7b13  mov     [rsp+0E8h+var_40], rax
0x1800a7b1b  mov     esi, r9d
0x1800a7b1e  mov     edi, r8d
0x1800a7b21  mov     r14, rdx
0x1800a7b24  mov     r15, rcx
0x1800a7b27  mov     rax, [rsp+0E8h+arg_40]
0x1800a7b2f  mov     [r11-70h], rax
0x1800a7b33  mov     qword ptr [r11-68h], 0
0x1800a7b3b  lea     rdx, [r11-70h]
0x1800a7b3f  lea     rcx, [r11-68h]; this
0x1800a7b43  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a7b48  mov     ebx, eax
0x1800a7b4a  test    eax, eax
0x1800a7b4c  jns     short loc_1800A7B80
0x1800a7b4e  mov     rcx, [rsp+0E8h]; this
0x1800a7b56  mov     r9d, eax; char *
0x1800a7b59  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800a7b60  mov     edx, 76h ; 'v'; void *
0x1800a7b65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7b6a  nop
0x1800a7b6b  mov     rcx, [rsp+0E8h+string]; string
0x1800a7b73  call    cs:__imp_WindowsDeleteString
0x1800a7b79  mov     eax, ebx
0x1800a7b7b  jmp     loc_1800A7EF5
0x1800a7b80  xorps   xmm0, xmm0
0x1800a7b83  movups  xmmword ptr [rsp+0E8h+var_80], xmm0
0x1800a7b88  lea     rdx, [rsp+0E8h+var_70]
0x1800a7b8d  lea     rcx, [rsp+0E8h+var_B8]
0x1800a7b92  call    ??$?0AEAPEBG$0A@@?$basic_zstring_view@G@wil@@QEAA@AEAPEBG@Z; wil::basic_zstring_view<ushort>::basic_zstring_view<ushort>(ushort const * &)
0x1800a7b97  lea     rdx, [rsp+0E8h+var_B8]
0x1800a7b9c  lea     rcx, [rsp+0E8h+var_80]
0x1800a7ba1  call    ?GetImageNameFromFullPath@@YA?AV?$basic_zstring_view@G@wil@@AEBV12@@Z; GetImageNameFromFullPath(wil::basic_zstring_view<ushort> const &)
0x1800a7ba6  mov     [rsp+0E8h+var_58], edi
0x1800a7bad  mov     ebx, [rsp+0E8h+arg_28]
0x1800a7bb4  mov     [rsp+0E8h+var_54], ebx
0x1800a7bbb  mov     r12d, [rsp+0E8h+arg_30]
0x1800a7bc3  mov     [rsp+0E8h+var_50], r12d
0x1800a7bcb  mov     r13d, [rsp+0E8h+arg_38]
0x1800a7bd3  mov     [rsp+0E8h+var_4C], r13d
0x1800a7bdb  mov     eax, [rsp+0E8h+arg_48]
0x1800a7be2  mov     [rsp+0E8h+var_48], eax
0x1800a7be9  cmp     [rsp+0E8h+arg_20], 0
0x1800a7bf1  setnbe  [rsp+0E8h+var_44]
0x1800a7bf9  mov     ecx, [r14+48h]
0x1800a7bfd  mov     eax, ecx
0x1800a7bff  shr     eax, 3
0x1800a7c02  and     al, 1
0x1800a7c04  mov     [rsp+0E8h+var_43], al
0x1800a7c0b  shr     ecx, 8
0x1800a7c0e  and     cl, 1
0x1800a7c11  mov     [rsp+0E8h+var_42], cl
0x1800a7c18  xor     r14d, r14d
0x1800a7c1b  test    esi, esi
0x1800a7c1d  setnz   [rsp+0E8h+var_41]
0x1800a7c25  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs> `wil::Feature<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::GetImpl(void)'::`2'::impl
0x1800a7c2c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_ImpersonateFwDialogs>::__private_IsEnabled(void)
0x1800a7c31  test    al, al
0x1800a7c33  jnz     loc_1800A7D35
0x1800a7c39  lea     r8d, [r14+4]
0x1800a7c3d  lea     rcx, [rsp+0E8h+var_60]
0x1800a7c45  call    ??$CoCreateInstanceEx@UIFirewallNotificationDialog@Firewall@NetworkUX@Internal@Windows@@@wil@@YA?A_PAEBU_GUID@@W4tagCLSCTX@@@Z
0x1800a7c4a  nop
0x1800a7c4b  mov     dword ptr [rsp+0E8h+var_B8], edi
0x1800a7c4f  mov     dword ptr [rsp+0E8h+var_B8+4], ebx
0x1800a7c53  mov     [rsp+0E8h+var_B0], r12d
0x1800a7c58  mov     [rsp+0E8h+var_AC], r13d
0x1800a7c5d  mov     eax, [rsp+0E8h+arg_48]
0x1800a7c64  mov     [rsp+0E8h+var_A8], eax
0x1800a7c68  cmp     [rsp+0E8h+var_44], r14b
0x1800a7c70  setnz   [rsp+0E8h+var_A4]
0x1800a7c75  cmp     [rsp+0E8h+var_43], r14b
0x1800a7c7d  setnz   [rsp+0E8h+var_A3]
0x1800a7c82  cmp     [rsp+0E8h+var_42], r14b
0x1800a7c8a  setnz   [rsp+0E8h+var_A2]
0x1800a7c8f  cmp     [rsp+0E8h+var_41], r14b
0x1800a7c97  setnz   [rsp+0E8h+var_A1]
0x1800a7c9c  mov     [rsp+0E8h+var_70], 10h
0x1800a7ca5  mov     r8, [rsp+0E8h+var_80]; unsigned __int16 *
0x1800a7caa  lea     rdx, [rsp+0E8h+var_B8]; struct NetworkingTriageScenario::FirewallUX::NotificationFields *
0x1800a7caf  lea     rcx, [rsp+0E8h+var_70]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x1800a7cb4  call    ?DialogTriggered@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@AEBUNotificationFields@12@PEBG@Z; NetworkingTriageScenario::FirewallUX::DialogTriggered(NetworkingTriageScenario::FirewallUX::RequiredFields const &,NetworkingTriageScenario::FirewallUX::NotificationFields const &,ushort const *)
0x1800a7cb9  mov     rcx, [rsp+0E8h+var_60]
0x1800a7cc1  mov     rax, [rcx]
0x1800a7cc4  mov     r8, [rsp+0E8h+string]
0x1800a7ccc  lea     rdx, [rsp+0E8h+var_58]
0x1800a7cd4  mov     rax, [rax+30h]
0x1800a7cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7cdd  mov     ebx, eax
0x1800a7cdf  test    eax, eax
0x1800a7ce1  jns     short loc_1800A7D23
0x1800a7ce3  mov     rcx, [rsp+0E8h]; this
0x1800a7ceb  mov     r9d, eax; char *
0x1800a7cee  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800a7cf5  mov     edx, 0B9h; void *
0x1800a7cfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7cff  nop
0x1800a7d00  lea     rcx, [rsp+0E8h+var_60]
0x1800a7d08  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800a7d0d  nop
0x1800a7d0e  mov     rcx, [rsp+0E8h+string]; string
0x1800a7d16  call    cs:__imp_WindowsDeleteString
0x1800a7d1c  mov     eax, ebx
0x1800a7d1e  jmp     loc_1800A7EF5
0x1800a7d23  lea     rcx, [rsp+0E8h+var_60]
0x1800a7d2b  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800a7d30  jmp     loc_1800A7EDC
0x1800a7d35  mov     [rsp+0E8h+var_60], r14
0x1800a7d3d  lea     rax, [rsp+0E8h+var_60]
0x1800a7d45  mov     [rsp+0E8h+phNewToken], rax; phNewToken
0x1800a7d4a  mov     r9d, 2; ImpersonationLevel
0x1800a7d50  mov     [rsp+0E8h+TokenType], r9d; int
0x1800a7d55  xor     r8d, r8d; lpTokenAttributes
0x1800a7d58  lea     edx, [r9+0Ah]; dwDesiredAccess
0x1800a7d5c  mov     rcx, r15; hExistingToken
0x1800a7d5f  call    cs:__imp_DuplicateTokenEx
0x1800a7d65  test    eax, eax
0x1800a7d67  jnz     short loc_1800A7DA7
0x1800a7d69  mov     rcx, [rsp+0E8h]; this
0x1800a7d71  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800a7d78  mov     edx, 8Eh; void *
0x1800a7d7d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a7d82  mov     ebx, eax
0x1800a7d84  lea     rcx, [rsp+0E8h+var_60]
0x1800a7d8c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a7d91  nop
0x1800a7d92  mov     rcx, [rsp+0E8h+string]; string
0x1800a7d9a  call    cs:__imp_WindowsDeleteString
0x1800a7da0  mov     eax, ebx
0x1800a7da2  jmp     loc_1800A7EF5
0x1800a7da7  mov     [rsp+0E8h+var_70], r14
0x1800a7dac  mov     rdx, [rsp+0E8h+var_60]
0x1800a7db4  lea     rcx, [rsp+0E8h+var_70]
0x1800a7db9  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x1800a7dbe  nop
0x1800a7dbf  mov     r8d, 100004h
0x1800a7dc5  lea     rcx, [rsp+0E8h+var_A0]
0x1800a7dca  call    ??$CoCreateInstanceEx@UIFirewallNotificationDialog@Firewall@NetworkUX@Internal@Windows@@@wil@@YA?A_PAEBU_GUID@@W4tagCLSCTX@@@Z
0x1800a7dcf  nop
0x1800a7dd0  mov     [rsp+0E8h+var_98], edi
0x1800a7dd4  mov     [rsp+0E8h+var_94], ebx
0x1800a7dd8  mov     [rsp+0E8h+var_90], r12d
0x1800a7ddd  mov     [rsp+0E8h+var_8C], r13d
0x1800a7de2  mov     eax, [rsp+0E8h+arg_48]
0x1800a7de9  mov     [rsp+0E8h+var_88], eax
0x1800a7ded  cmp     [rsp+0E8h+var_44], r14b
0x1800a7df5  setnz   [rsp+0E8h+var_84]
0x1800a7dfa  cmp     [rsp+0E8h+var_43], r14b
0x1800a7e02  setnz   [rsp+0E8h+var_83]
0x1800a7e07  cmp     [rsp+0E8h+var_42], r14b
0x1800a7e0f  setnz   [rsp+0E8h+var_82]
0x1800a7e14  cmp     [rsp+0E8h+var_41], r14b
0x1800a7e1c  setnz   [rsp+0E8h+var_81]
0x1800a7e21  mov     [rsp+0E8h+var_B8], 10h
0x1800a7e2a  mov     r8, [rsp+0E8h+var_80]; unsigned __int16 *
0x1800a7e2f  lea     rdx, [rsp+0E8h+var_98]; struct NetworkingTriageScenario::FirewallUX::NotificationFields *
0x1800a7e34  lea     rcx, [rsp+0E8h+var_B8]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x1800a7e39  call    ?DialogTriggered@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@AEBUNotificationFields@12@PEBG@Z; NetworkingTriageScenario::FirewallUX::DialogTriggered(NetworkingTriageScenario::FirewallUX::RequiredFields const &,NetworkingTriageScenario::FirewallUX::NotificationFields const &,ushort const *)
0x1800a7e3e  mov     rcx, [rsp+0E8h+var_A0]
0x1800a7e43  mov     rax, [rcx]
0x1800a7e46  mov     r8, [rsp+0E8h+string]
0x1800a7e4e  lea     rdx, [rsp+0E8h+var_58]
0x1800a7e56  mov     rax, [rax+30h]
0x1800a7e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7e5f  mov     ebx, eax
0x1800a7e61  test    eax, eax
0x1800a7e63  jns     short loc_1800A7EB8
0x1800a7e65  mov     rcx, [rsp+0E8h]; this
0x1800a7e6d  mov     r9d, eax; char *
0x1800a7e70  lea     r8, aOnecoreNetMpss_1; "onecore\\net\\mpssvc\\lics\\fw\\fw_mode"...
0x1800a7e77  mov     edx, 0A4h; void *
0x1800a7e7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7e81  nop
0x1800a7e82  lea     rcx, [rsp+0E8h+var_A0]
0x1800a7e87  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800a7e8c  nop
0x1800a7e8d  lea     rcx, [rsp+0E8h+var_70]
0x1800a7e92  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800a7e97  nop
0x1800a7e98  lea     rcx, [rsp+0E8h+var_60]
0x1800a7ea0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a7ea5  nop
0x1800a7ea6  mov     rcx, [rsp+0E8h+string]; string
0x1800a7eae  call    cs:__imp_WindowsDeleteString
0x1800a7eb4  mov     eax, ebx
0x1800a7eb6  jmp     short loc_1800A7EF5
0x1800a7eb8  lea     rcx, [rsp+0E8h+var_A0]
0x1800a7ebd  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800a7ec2  nop
0x1800a7ec3  lea     rcx, [rsp+0E8h+var_70]
0x1800a7ec8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800a7ecd  nop
0x1800a7ece  lea     rcx, [rsp+0E8h+var_60]
0x1800a7ed6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a7edb  nop
0x1800a7edc  mov     rcx, [rsp+0E8h+string]; string
0x1800a7ee4  call    cs:__imp_WindowsDeleteString
0x1800a7eea  xor     eax, eax
0x1800a7eec  jmp     short loc_1800A7EF5
0x1800a7eee  mov     eax, dword ptr [rsp+0E8h+string]
0x1800a7ef5  mov     rcx, [rsp+0E8h+var_40]
0x1800a7efd  xor     rcx, rsp; StackCookie
0x1800a7f00  call    __security_check_cookie
0x1800a7f05  add     rsp, 0B0h
0x1800a7f0c  pop     r15
0x1800a7f0e  pop     r14
0x1800a7f10  pop     r13
0x1800a7f12  pop     r12
0x1800a7f14  pop     rdi
0x1800a7f15  pop     rsi
0x1800a7f16  pop     rbx
0x1800a7f17  retn
```
