# CloudExperienceHostAPI::OobePrivacySettings::_ShouldShowPrivacySettingForPrivacyConsentsPending(OOBE_PROTECTPC_BOOLEAN_SETTING,uchar *)

- ea: `0x18009a1e4`
- end: `0x18009a3ee`
- name: `?_ShouldShowPrivacySettingForPrivacyConsentsPending@OobePrivacySettings@CloudExperienceHostAPI@@AEAAJW4OOBE_PROTECTPC_BOOLEAN_SETTING@@PEAE@Z`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800987b0`

## callees

- `0x180008544`
- `0x180030280`
- `0x18003b0e0`
- `0x18003e664`
- `0x1800950e0`
- `0x180098438`
- `0x180098740`
- `0x180098860`
- `0x180099788`
- `0x18009a08c`
- `0x18009a1b4`
- `0x18009a1e4`
- `0x18009a3f4`
- `0x18009a594`
- `0x18009a60c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a26b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a26b`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18009a221`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18009a221`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18009a39a`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18009a39a`

## string_xrefs

- `0x18009a31d`: `shell\oobe\machine\plugins\adapters\winrt\oobesettings.cpp`
- `0x18009a25d`: `SOFTWARE\Microsoft\Windows\CurrentVersion\CapabilityAccessManager\Capabilities\humanPresence`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostAPI::OobePrivacySettings::_ShouldShowPrivacySettingForPrivacyConsentsPending(
        __int64 a1,
        __int64 a2,
        _BYTE *a3)
{
  unsigned int v4; // edi
  char v6; // r14
  bool v7; // bl
  int ShouldSetMachineSettings; // eax
  CloudExperienceHostAPI::OobePrivacySettings *v9; // rcx
  unsigned int v10; // ebx
  char ShouldShowTelemetrySetting; // bl
  __int64 v13; // r8
  int phkResult; // [rsp+20h] [rbp-38h]
  _BYTE v15[8]; // [rsp+30h] [rbp-28h] BYREF
  HKEY v16; // [rsp+38h] [rbp-20h] BYREF
  __int64 v17; // [rsp+40h] [rbp-18h] BYREF
  _BYTE v18[16]; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  int v20; // [rsp+A8h] [rbp+50h] BYREF

  v4 = a2;
  v20 = 0;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_InitiateNTHPrivacyOnServer>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_InitiateNTHPrivacyOnServer>::GetImpl'::`2'::impl,
    a2);
  v20 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v20, 0);
  if ( v20 != 9 )
  {
    if ( v4 == 6 )
    {
      v16 = 0;
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager\\Capabilities\\humanPresence",
             0,
             0x20019u,
             &v16) )
      {
        *a3 = 0;
        return 0;
      }
      winrt::Windows::Devices::Sensors::HumanPresenceSettings::GetCurrentSettings();
      v17 = 0;
      v6 = 1;
      v20 = 1;
      v7 = 1;
      if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(v15, &v17) )
      {
        v6 = 3;
        if ( *(_QWORD *)winrt::impl::consume_Windows_Devices_Sensors_IHumanPresenceSettings<winrt::Windows::Devices::Sensors::IHumanPresenceSettings>::SensorId(
                          v15,
                          v18) )
          v7 = 0;
      }
      if ( (v6 & 2) != 0 )
        winrt::handle_type<winrt::impl::hstring_traits>::close(v18);
      if ( v7 )
      {
        *a3 = 0;
        winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)v15);
        return 0;
      }
      winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)v15);
    }
    if ( IsUserOOBE() )
    {
      ShouldShowTelemetrySetting = 1;
    }
    else
    {
      LOBYTE(v20) = 0;
      ShouldSetMachineSettings = CloudExperienceHostAPI::OobePrivacySettings::GetShouldSetMachineSettings(
                                   (CloudExperienceHostAPI::OobePrivacySettings *)(a1 + 40),
                                   (unsigned __int8 *)&v20);
      v10 = ShouldSetMachineSettings;
      if ( ShouldSetMachineSettings < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14B,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobesettings.cpp",
          (const char *)(unsigned int)ShouldSetMachineSettings,
          phkResult);
        return v10;
      }
      if ( v4 == 2 )
      {
        ShouldShowTelemetrySetting = CloudExperienceHostAPI::OobePrivacySettings::_ShouldShowTelemetrySetting(
                                       v9,
                                       (_BYTE)v20 != 0);
LABEL_30:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobePersonalizedOffers>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OobePersonalizedOffers>::GetImpl'::`2'::impl) )
        {
          if ( v4 == 3 )
          {
            ShouldShowTelemetrySetting = !IsPersonalizedOffersPolicyApplicable();
          }
          else if ( v4 == 7 )
          {
            ShouldShowTelemetrySetting = IsPersonalizedOffersPolicyApplicable();
          }
        }
        *a3 = ShouldShowTelemetrySetting;
        return 0;
      }
      v13 = 8;
      if ( (_BYTE)v20 )
        v13 = 12;
      ShouldShowTelemetrySetting = CloudExperienceHostAPI::OobePrivacySettings::_DoesOobeSettingHaveAnyOptionSet(
                                     v9,
                                     v4,
                                     v13);
    }
    if ( v4 == 4 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAdID>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RemoveAdID>::GetImpl'::`2'::impl) )
      {
        ShouldShowTelemetrySetting = 0;
      }
      else
      {
        v20 = 0;
        if ( (int)PolicyManager_GetPolicyInt(L"Privacy", L"DisableAdvertisingId", &v20) >= 0 && v20 == 1 )
          ShouldShowTelemetrySetting = 0;
      }
    }
    goto LABEL_30;
  }
  *a3 = v4 == 2;
  return 0;
}

```

## disassembly

```asm
0x18009a1e4  push    rbp
0x18009a1e6  push    rbx
0x18009a1e7  push    rsi
0x18009a1e8  push    rdi
0x18009a1e9  push    r14
0x18009a1eb  push    r15
0x18009a1ed  mov     rbp, rsp
0x18009a1f0  sub     rsp, 58h
0x18009a1f4  mov     rsi, r8
0x18009a1f7  mov     edi, edx
0x18009a1f9  mov     r15, rcx
0x18009a1fc  mov     [rbp+arg_18], 0
0x18009a203  mov     dl, 1
0x18009a205  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InitiateNTHPrivacyOnServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InitiateNTHPrivacyOnServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InitiateNTHPrivacyOnServer> `wil::Feature<__WilFeatureTraits_Feature_InitiateNTHPrivacyOnServer>::GetImpl(void)'::`2'::impl
0x18009a20c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_InitiateNTHPrivacyOnServer@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InitiateNTHPrivacyOnServer>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18009a211  mov     [rbp+arg_18], 0
0x18009a218  xor     r8d, r8d
0x18009a21b  lea     rdx, [rbp+arg_18]
0x18009a21f  xor     ecx, ecx
0x18009a221  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18009a227  cmp     [rbp+arg_18], 9
0x18009a22b  jnz     short loc_18009A23A
0x18009a22d  cmp     edi, 2
0x18009a230  setz    al
0x18009a233  mov     [rsi], al
0x18009a235  jmp     loc_18009A3DF
0x18009a23a  cmp     edi, 6
0x18009a23d  jnz     loc_18009A2F7
0x18009a243  mov     [rbp+var_20], 0
0x18009a24b  lea     rax, [rbp+var_20]
0x18009a24f  mov     qword ptr [rsp+58h+phkResult], rax; int
0x18009a254  mov     r9d, 20019h; samDesired
0x18009a25a  xor     r8d, r8d; ulOptions
0x18009a25d  lea     rdx, aSoftwareMicros_17; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18009a264  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009a26b  call    cs:__imp_RegOpenKeyExW
0x18009a271  test    eax, eax
0x18009a273  jz      short loc_18009A27D
0x18009a275  mov     byte ptr [rsi], 0
0x18009a278  jmp     loc_18009A3DF
0x18009a27d  lea     rcx, [rbp+var_28]
0x18009a281  call    ?GetCurrentSettings@HumanPresenceSettings@Sensors@Devices@Windows@winrt@@SA@XZ; winrt::Windows::Devices::Sensors::HumanPresenceSettings::GetCurrentSettings(void)
0x18009a286  nop
0x18009a287  mov     [rbp+var_18], 0
0x18009a28f  mov     r14d, 1
0x18009a295  mov     [rbp+arg_18], r14d
0x18009a299  lea     rdx, [rbp+var_18]
0x18009a29d  lea     rcx, [rbp+var_28]
0x18009a2a1  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18009a2a6  test    al, al
0x18009a2a8  jnz     short loc_18009A2C7
0x18009a2aa  lea     rdx, [rbp+var_10]
0x18009a2ae  lea     rcx, [rbp+var_28]
0x18009a2b2  call    ?SensorId@?$consume_Windows_Devices_Sensors_IHumanPresenceSettings@UIHumanPresenceSettings@Sensors@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Sensors_IHumanPresenceSettings<winrt::Windows::Devices::Sensors::IHumanPresenceSettings>::SensorId(void)
0x18009a2b7  mov     r14d, 3
0x18009a2bd  cmp     qword ptr [rax], 0
0x18009a2c1  jz      short loc_18009A2C7
0x18009a2c3  xor     bl, bl
0x18009a2c5  jmp     short loc_18009A2C9
0x18009a2c7  mov     bl, 1
0x18009a2c9  test    r14b, 2
0x18009a2cd  jz      short loc_18009A2D9
0x18009a2cf  lea     rcx, [rbp+var_10]
0x18009a2d3  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18009a2d8  nop
0x18009a2d9  test    bl, bl
0x18009a2db  jz      short loc_18009A2EE
0x18009a2dd  mov     byte ptr [rsi], 0
0x18009a2e0  lea     rcx, [rbp+var_28]; this
0x18009a2e4  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x18009a2e9  jmp     loc_18009A3DF
0x18009a2ee  lea     rcx, [rbp+var_28]; this
0x18009a2f2  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x18009a2f7  call    ?IsUserOOBE@@YA_NXZ; IsUserOOBE(void)
0x18009a2fc  test    al, al
0x18009a2fe  jnz     short loc_18009A366
0x18009a300  mov     byte ptr [rbp+arg_18], al
0x18009a303  lea     rcx, [r15+28h]; this
0x18009a307  lea     rdx, [rbp+arg_18]; unsigned __int8 *
0x18009a30b  call    ?GetShouldSetMachineSettings@OobePrivacySettings@CloudExperienceHostAPI@@UEAAJPEAE@Z; CloudExperienceHostAPI::OobePrivacySettings::GetShouldSetMachineSettings(uchar *)
0x18009a310  mov     ebx, eax
0x18009a312  test    eax, eax
0x18009a314  jns     short loc_18009A335
0x18009a316  mov     rcx, [rbp+30h]; this
0x18009a31a  mov     r9d, eax; char *
0x18009a31d  lea     r8, aShellOobeMachi_4; "shell\\oobe\\machine\\plugins\\adapters"...
0x18009a324  mov     edx, 14Bh; void *
0x18009a329  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a32e  mov     eax, ebx
0x18009a330  jmp     loc_18009A3E1
0x18009a335  cmp     edi, 2
0x18009a338  jnz     short loc_18009A34A
0x18009a33a  cmp     byte ptr [rbp+arg_18], 0
0x18009a33e  setnz   dl; bool
0x18009a341  call    ?_ShouldShowTelemetrySetting@OobePrivacySettings@CloudExperienceHostAPI@@AEAA_N_N@Z; CloudExperienceHostAPI::OobePrivacySettings::_ShouldShowTelemetrySetting(bool)
0x18009a346  mov     bl, al
0x18009a348  jmp     short loc_18009A3B0
0x18009a34a  mov     eax, 0Ch
0x18009a34f  lea     r8d, [rax-4]
0x18009a353  cmp     byte ptr [rbp+arg_18], 0
0x18009a357  cmovnz  r8d, eax
0x18009a35b  mov     edx, edi
0x18009a35d  call    ?_DoesOobeSettingHaveAnyOptionSet@OobePrivacySettings@CloudExperienceHostAPI@@AEAA_NW4OOBE_PROTECTPC_BOOLEAN_SETTING@@W4ProtectCommitOptions@@@Z; CloudExperienceHostAPI::OobePrivacySettings::_DoesOobeSettingHaveAnyOptionSet(OOBE_PROTECTPC_BOOLEAN_SETTING,ProtectCommitOptions)
0x18009a362  mov     bl, al
0x18009a364  jmp     short loc_18009A368
0x18009a366  mov     bl, 1
0x18009a368  cmp     edi, 4
0x18009a36b  jnz     short loc_18009A3B0
0x18009a36d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RemoveAdID@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveAdID@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAdID> `wil::Feature<__WilFeatureTraits_Feature_RemoveAdID>::GetImpl(void)'::`2'::impl
0x18009a374  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveAdID@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAdID>::__private_IsEnabled(void)
0x18009a379  test    al, al
0x18009a37b  jz      short loc_18009A381
0x18009a37d  xor     bl, bl
0x18009a37f  jmp     short loc_18009A3B0
0x18009a381  mov     [rbp+arg_18], 0
0x18009a388  lea     r8, [rbp+arg_18]
0x18009a38c  lea     rdx, aDisableadverti; "DisableAdvertisingId"
0x18009a393  lea     rcx, aPrivacy; "Privacy"
0x18009a39a  call    cs:__imp_PolicyManager_GetPolicyInt
0x18009a3a0  test    eax, eax
0x18009a3a2  js      short loc_18009A3B0
0x18009a3a4  movzx   ebx, bl
0x18009a3a7  xor     eax, eax
0x18009a3a9  cmp     [rbp+arg_18], 1
0x18009a3ad  cmovz   ebx, eax
0x18009a3b0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OobePersonalizedOffers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OobePersonalizedOffers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobePersonalizedOffers> `wil::Feature<__WilFeatureTraits_Feature_OobePersonalizedOffers>::GetImpl(void)'::`2'::impl
0x18009a3b7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OobePersonalizedOffers@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobePersonalizedOffers>::__private_IsEnabled(void)
0x18009a3bc  test    al, al
0x18009a3be  jz      short loc_18009A3DD
0x18009a3c0  cmp     edi, 3
0x18009a3c3  jnz     short loc_18009A3D1
0x18009a3c5  call    ?IsPersonalizedOffersPolicyApplicable@@YA_NXZ; IsPersonalizedOffersPolicyApplicable(void)
0x18009a3ca  test    al, al
0x18009a3cc  setz    bl
0x18009a3cf  jmp     short loc_18009A3DD
0x18009a3d1  cmp     edi, 7
0x18009a3d4  jnz     short loc_18009A3DD
0x18009a3d6  call    ?IsPersonalizedOffersPolicyApplicable@@YA_NXZ; IsPersonalizedOffersPolicyApplicable(void)
0x18009a3db  mov     bl, al
0x18009a3dd  mov     [rsi], bl
0x18009a3df  xor     eax, eax
0x18009a3e1  add     rsp, 58h
0x18009a3e5  pop     r15
0x18009a3e7  pop     r14
0x18009a3e9  pop     rdi
0x18009a3ea  pop     rsi
0x18009a3eb  pop     rbx
0x18009a3ec  pop     rbp
0x18009a3ed  retn
```
