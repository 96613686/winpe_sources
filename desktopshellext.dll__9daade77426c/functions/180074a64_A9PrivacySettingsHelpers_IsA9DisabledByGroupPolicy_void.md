# A9PrivacySettingsHelpers::IsA9DisabledByGroupPolicy(void)

- ea: `0x180074a64`
- end: `0x180074cda`
- name: `?IsA9DisabledByGroupPolicy@A9PrivacySettingsHelpers@@YA_NXZ`
- size: `630`
- prototype: `bool __fastcall(A9PrivacySettingsHelpers *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180074600`

## callees

- `0x180014114`
- `0x180021690`
- `0x18002a3d0`
- `0x180073fbc`
- `0x1800741cc`
- `0x18007444c`
- `0x1800744c4`
- `0x180074a64`
- `0x180075a5c`
- `0x1800791bc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180074b5c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180074b5c`
- `ntdll!RtlIsFeatureEnabledForEnterprise` at `0x180074b25`
- `ntdll!RtlIsFeatureEnabledForEnterprise` at `0x180074b25`
- `MDMRegistration!IsDeviceRegisteredWithManagement` at `0x180074b3c`
- `MDMRegistration!IsDeviceRegisteredWithManagement` at `0x180074b3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall A9PrivacySettingsHelpers::IsA9DisabledByGroupPolicy(A9PrivacySettingsHelpers *this)
{
  bool v1; // bl
  const char *v2; // r9
  char IsFeatureEnabledForEnterprise; // di
  bool v5; // al
  int Int32; // esi
  const char *v7; // r9
  int v8; // edi
  const char *v9; // r9
  bool v10; // [rsp+20h] [rbp-288h]
  char v11; // [rsp+20h] [rbp-288h]
  int v12; // [rsp+24h] [rbp-284h]
  _BYTE v13[8]; // [rsp+28h] [rbp-280h] BYREF
  int v14; // [rsp+30h] [rbp-278h] BYREF
  int v15; // [rsp+38h] [rbp-270h] BYREF
  DWORD nSize; // [rsp+40h] [rbp-268h] BYREF
  _BYTE v17[32]; // [rsp+48h] [rbp-260h] BYREF
  _BYTE v18[40]; // [rsp+68h] [rbp-240h] BYREF
  WCHAR Buffer[256]; // [rsp+90h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_51549795>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_51549795>::GetImpl'::`2'::impl) )
  {
    IsFeatureEnabledForEnterprise = RtlIsFeatureEnabledForEnterprise(51549795);
    v15 = 0;
    IsDeviceRegisteredWithManagement(&v15, 0, 0);
    nSize = 256;
    v5 = GetComputerNameExW(ComputerNamePhysicalDnsDomain, Buffer, &nSize) && Buffer[0] != 0;
    if ( !IsFeatureEnabledForEnterprise || v15 || (v11 = 0, v5) )
      v11 = 1;
    try
    {
      winrt::Windows::System::User::GetDefault();
      winrt::param::hstring::hstring((winrt::param::hstring *)v18, L"DisableAIDataAnalysis");
      winrt::param::hstring::hstring((winrt::param::hstring *)v17, L"WindowsAI");
      winrt::Windows::Management::Policies::NamedPolicy::GetPolicyFromPathForUser(
        (const struct winrt::Windows::System::User *)&v14,
        (const struct winrt::param::hstring *)v13,
        (const struct winrt::param::hstring *)v17);
      if ( (unsigned __int8)winrt::impl::consume_Windows_Management_Policies_INamedPolicyData<winrt::Windows::Management::Policies::INamedPolicyData>::IsManaged(&v14) )
        Int32 = winrt::impl::consume_Windows_Management_Policies_INamedPolicyData<winrt::Windows::Management::Policies::INamedPolicyData>::GetInt32(&v14);
      else
        Int32 = -1;
      v12 = Int32;
      winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager((winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager *)&v14);
      winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager((winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager *)v13);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x2B,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\A9DisabledByGroupPolicyHelper.h",
        v7);
      Int32 = v12;
    }
    try
    {
      v14 = -1;
      winrt::param::hstring::hstring((winrt::param::hstring *)v18, L"DisableAIDataAnalysis");
      winrt::param::hstring::hstring((winrt::param::hstring *)v17, L"WindowsAI");
      winrt::Windows::Management::Policies::NamedPolicy::GetPolicyFromPath(
        (const struct winrt::param::hstring *)v13,
        (const struct winrt::param::hstring *)v17);
      if ( (unsigned __int8)winrt::impl::consume_Windows_Management_Policies_INamedPolicyData<winrt::Windows::Management::Policies::INamedPolicyData>::IsManaged(v13) )
        v8 = winrt::impl::consume_Windows_Management_Policies_INamedPolicyData<winrt::Windows::Management::Policies::INamedPolicyData>::GetInt32(v13);
      else
        v8 = -1;
      v14 = v8;
      winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager((winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager *)v13);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x33,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\A9DisabledByGroupPolicyHelper.h",
        v9);
      Int32 = v12;
      v8 = v14;
    }
    return Int32 == 1 || v8 == 1 || Int32 == -1 && v8 == -1 && v11;
  }
  else
  {
    try
    {
      winrt::Windows::System::User::GetDefault();
      winrt::param::hstring::hstring((winrt::param::hstring *)v17, L"DisableAIDataAnalysis");
      winrt::param::hstring::hstring((winrt::param::hstring *)v18, L"WindowsAI");
      winrt::Windows::Management::Policies::NamedPolicy::GetPolicyFromPathForUser(
        (const struct winrt::Windows::System::User *)v13,
        (const struct winrt::param::hstring *)&nSize,
        (const struct winrt::param::hstring *)v18);
      v1 = (unsigned int)winrt::impl::consume_Windows_Management_Policies_INamedPolicyData<winrt::Windows::Management::Policies::INamedPolicyData>::GetInt32(v13) == 1;
      v10 = v1;
      winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager((winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager *)v13);
      winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager((winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager *)&nSize);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x54,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\A9DisabledByGroupPolicyHelper.h",
        v2);
      return v10;
    }
    return v1;
  }
}

```

## disassembly

```asm
0x180074a64  mov     [rsp+arg_0], rbx
0x180074a69  mov     [rsp+arg_8], rsi
0x180074a6e  push    rdi
0x180074a6f  sub     rsp, 2A0h
0x180074a76  mov     rax, cs:__security_cookie
0x180074a7d  xor     rax, rsp
0x180074a80  mov     [rsp+2A8h+var_18], rax
0x180074a88  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_51549795@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_51549795@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51549795> `wil::Feature<__WilFeatureTraits_Feature_51549795>::GetImpl(void)'::`2'::impl
0x180074a8f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_51549795@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51549795>::__private_IsEnabled(void)
0x180074a94  xor     ebx, ebx
0x180074a96  test    al, al
0x180074a98  jnz     loc_180074B20
0x180074a9e  mov     [rsp+2A8h+var_288], bl
0x180074aa2  lea     rcx, [rsp+2A8h+nSize]
0x180074aa7  call    ?GetDefault@User@System@Windows@winrt@@SA@XZ; winrt::Windows::System::User::GetDefault(void)
0x180074aac  nop
0x180074aad  lea     rdx, aDisableaidataa; "DisableAIDataAnalysis"
0x180074ab4  lea     rcx, [rsp+2A8h+var_260]; this
0x180074ab9  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180074abe  lea     rdx, aWindowsai; "WindowsAI"
0x180074ac5  lea     rcx, [rsp+2A8h+var_240]; this
0x180074aca  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180074acf  lea     r9, [rsp+2A8h+var_260]
0x180074ad4  lea     r8, [rsp+2A8h+var_240]; struct winrt::param::hstring *
0x180074ad9  lea     rdx, [rsp+2A8h+nSize]; struct winrt::param::hstring *
0x180074ade  lea     rcx, [rsp+2A8h+var_280]; struct winrt::Windows::System::User *
0x180074ae3  call    ?GetPolicyFromPathForUser@NamedPolicy@Policies@Management@Windows@winrt@@SA@AEBUUser@System@45@AEBUhstring@param@5@1@Z; winrt::Windows::Management::Policies::NamedPolicy::GetPolicyFromPathForUser(winrt::Windows::System::User const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x180074ae8  nop
0x180074ae9  lea     rcx, [rsp+2A8h+var_280]
0x180074aee  call    ?GetInt32@?$consume_Windows_Management_Policies_INamedPolicyData@UINamedPolicyData@Policies@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Policies_INamedPolicyData<winrt::Windows::Management::Policies::INamedPolicyData>::GetInt32(void)
0x180074af3  cmp     eax, 1
0x180074af6  setz    bl
0x180074af9  mov     [rsp+2A8h+var_288], bl
0x180074afd  lea     rcx, [rsp+2A8h+var_280]; this
0x180074b02  call    ??1SmartFeatureTuningManager@FeatureTuning@Flighting@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager(void)
0x180074b07  nop
0x180074b08  lea     rcx, [rsp+2A8h+nSize]; this
0x180074b0d  call    ??1SmartFeatureTuningManager@FeatureTuning@Flighting@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager(void)
0x180074b12  nop
0x180074b13  jmp     short loc_180074B19
0x180074b15  mov     bl, [rsp+2A8h+var_288]
0x180074b19  mov     al, bl
0x180074b1b  jmp     loc_180074CB5
0x180074b20  mov     ecx, 3129663h
0x180074b25  call    cs:__imp_RtlIsFeatureEnabledForEnterprise
0x180074b2b  mov     dil, al
0x180074b2e  mov     [rsp+2A8h+var_270], ebx
0x180074b32  xor     r8d, r8d
0x180074b35  xor     edx, edx
0x180074b37  lea     rcx, [rsp+2A8h+var_270]
0x180074b3c  call    cs:__imp_IsDeviceRegisteredWithManagement
0x180074b42  mov     [rsp+2A8h+nSize], 100h
0x180074b4a  lea     r8, [rsp+2A8h+nSize]; nSize
0x180074b4f  lea     rdx, [rsp+2A8h+Buffer]; lpBuffer
0x180074b57  mov     ecx, 6; NameType
0x180074b5c  call    cs:__imp_GetComputerNameExW
0x180074b62  test    eax, eax
0x180074b64  jz      short loc_180074B73
0x180074b66  cmp     [rsp+2A8h+Buffer], bx
0x180074b6e  setnz   al
0x180074b71  jmp     short loc_180074B75
0x180074b73  mov     al, bl
0x180074b75  test    dil, dil
0x180074b78  jz      short loc_180074B88
0x180074b7a  cmp     [rsp+2A8h+var_270], ebx
0x180074b7e  jnz     short loc_180074B88
0x180074b80  test    al, al
0x180074b82  mov     [rsp+2A8h+var_288], bl
0x180074b86  jz      short loc_180074B8D
0x180074b88  mov     [rsp+2A8h+var_288], 1
0x180074b8d  mov     [rsp+2A8h+var_284], 0FFFFFFFFh
0x180074b95  lea     rcx, [rsp+2A8h+var_280]
0x180074b9a  call    ?GetDefault@User@System@Windows@winrt@@SA@XZ; winrt::Windows::System::User::GetDefault(void)
0x180074b9f  nop
0x180074ba0  lea     rdx, aDisableaidataa; "DisableAIDataAnalysis"
0x180074ba7  lea     rcx, [rsp+2A8h+var_240]; this
0x180074bac  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180074bb1  lea     rdx, aWindowsai; "WindowsAI"
0x180074bb8  lea     rcx, [rsp+2A8h+var_260]; this
0x180074bbd  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180074bc2  lea     r9, [rsp+2A8h+var_240]
0x180074bc7  lea     r8, [rsp+2A8h+var_260]; struct winrt::param::hstring *
0x180074bcc  lea     rdx, [rsp+2A8h+var_280]; struct winrt::param::hstring *
0x180074bd1  lea     rcx, [rsp+2A8h+var_278]; struct winrt::Windows::System::User *
0x180074bd6  call    ?GetPolicyFromPathForUser@NamedPolicy@Policies@Management@Windows@winrt@@SA@AEBUUser@System@45@AEBUhstring@param@5@1@Z; winrt::Windows::Management::Policies::NamedPolicy::GetPolicyFromPathForUser(winrt::Windows::System::User const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x180074bdb  nop
0x180074bdc  lea     rcx, [rsp+2A8h+var_278]
0x180074be1  call    ?IsManaged@?$consume_Windows_Management_Policies_INamedPolicyData@UINamedPolicyData@Policies@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Policies_INamedPolicyData<winrt::Windows::Management::Policies::INamedPolicyData>::IsManaged(void)
0x180074be6  test    al, al
0x180074be8  jz      short loc_180074BF8
0x180074bea  lea     rcx, [rsp+2A8h+var_278]
0x180074bef  call    ?GetInt32@?$consume_Windows_Management_Policies_INamedPolicyData@UINamedPolicyData@Policies@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Policies_INamedPolicyData<winrt::Windows::Management::Policies::INamedPolicyData>::GetInt32(void)
0x180074bf4  mov     esi, eax
0x180074bf6  jmp     short loc_180074BFB
0x180074bf8  or      esi, 0FFFFFFFFh
0x180074bfb  mov     [rsp+2A8h+var_284], esi
0x180074bff  lea     rcx, [rsp+2A8h+var_278]; this
0x180074c04  call    ??1SmartFeatureTuningManager@FeatureTuning@Flighting@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager(void)
0x180074c09  nop
0x180074c0a  lea     rcx, [rsp+2A8h+var_280]; this
0x180074c0f  call    ??1SmartFeatureTuningManager@FeatureTuning@Flighting@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager(void)
0x180074c14  nop
0x180074c15  jmp     short loc_180074C1D
0x180074c17  xor     ebx, ebx
0x180074c19  mov     esi, [rsp+2A8h+var_284]
0x180074c1d  mov     [rsp+2A8h+var_278], 0FFFFFFFFh
0x180074c25  lea     rdx, aDisableaidataa; "DisableAIDataAnalysis"
0x180074c2c  lea     rcx, [rsp+2A8h+var_240]; this
0x180074c31  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180074c36  lea     rdx, aWindowsai; "WindowsAI"
0x180074c3d  lea     rcx, [rsp+2A8h+var_260]; this
0x180074c42  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180074c47  lea     r8, [rsp+2A8h+var_240]
0x180074c4c  lea     rdx, [rsp+2A8h+var_260]; struct winrt::param::hstring *
0x180074c51  lea     rcx, [rsp+2A8h+var_280]; struct winrt::param::hstring *
0x180074c56  call    ?GetPolicyFromPath@NamedPolicy@Policies@Management@Windows@winrt@@SA@AEBUhstring@param@5@0@Z; winrt::Windows::Management::Policies::NamedPolicy::GetPolicyFromPath(winrt::param::hstring const &,winrt::param::hstring const &)
0x180074c5b  nop
0x180074c5c  lea     rcx, [rsp+2A8h+var_280]
0x180074c61  call    ?IsManaged@?$consume_Windows_Management_Policies_INamedPolicyData@UINamedPolicyData@Policies@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Policies_INamedPolicyData<winrt::Windows::Management::Policies::INamedPolicyData>::IsManaged(void)
0x180074c66  test    al, al
0x180074c68  jz      short loc_180074C78
0x180074c6a  lea     rcx, [rsp+2A8h+var_280]
0x180074c6f  call    ?GetInt32@?$consume_Windows_Management_Policies_INamedPolicyData@UINamedPolicyData@Policies@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Policies_INamedPolicyData<winrt::Windows::Management::Policies::INamedPolicyData>::GetInt32(void)
0x180074c74  mov     edi, eax
0x180074c76  jmp     short loc_180074C7B
0x180074c78  or      edi, 0FFFFFFFFh
0x180074c7b  mov     [rsp+2A8h+var_278], edi
0x180074c7f  lea     rcx, [rsp+2A8h+var_280]; this
0x180074c84  call    ??1SmartFeatureTuningManager@FeatureTuning@Flighting@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager(void)
0x180074c89  nop
0x180074c8a  jmp     short loc_180074C96
0x180074c8c  xor     ebx, ebx
0x180074c8e  mov     esi, [rsp+2A8h+var_284]
0x180074c92  mov     edi, [rsp+2A8h+var_278]
0x180074c96  cmp     esi, 1
0x180074c99  jz      short loc_180074CB3
0x180074c9b  cmp     edi, 1
0x180074c9e  jz      short loc_180074CB3
0x180074ca0  cmp     esi, 0FFFFFFFFh
0x180074ca3  jnz     short loc_180074CAF
0x180074ca5  cmp     edi, esi
0x180074ca7  jnz     short loc_180074CAF
0x180074ca9  cmp     [rsp+2A8h+var_288], bl
0x180074cad  jnz     short loc_180074CB3
0x180074caf  xor     al, al
0x180074cb1  jmp     short loc_180074CB5
0x180074cb3  mov     al, 1
0x180074cb5  mov     rcx, [rsp+2A8h+var_18]
0x180074cbd  xor     rcx, rsp; StackCookie
0x180074cc0  call    __security_check_cookie
0x180074cc5  lea     r11, [rsp+2A8h+var_8]
0x180074ccd  mov     rbx, [r11+10h]
0x180074cd1  mov     rsi, [r11+18h]
0x180074cd5  mov     rsp, r11
0x180074cd8  pop     rdi
0x180074cd9  retn
```
