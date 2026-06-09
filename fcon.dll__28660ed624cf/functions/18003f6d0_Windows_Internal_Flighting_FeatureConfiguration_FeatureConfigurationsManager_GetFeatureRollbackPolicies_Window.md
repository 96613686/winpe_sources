# Windows::Internal::Flighting::FeatureConfiguration::FeatureConfigurationsManager::GetFeatureRollbackPolicies(Windows::Foundation::Collections::IVectorView<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy> * *)

- ea: `0x18003f6d0`
- end: `0x18003fb7e`
- name: `?GetFeatureRollbackPolicies@FeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@Windows@@UEAAJPEAPEAU?$IVectorView@UFeatureRollbackPolicy@FeatureConfiguration@Flighting@Internal@Windows@@@Collections@Foundation@5@@Z`
- size: `1198`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180003220`
- `0x18000796c`
- `0x180010450`
- `0x180010810`
- `0x1800109ac`
- `0x180015af4`
- `0x180019704`
- `0x180019890`
- `0x180027290`
- `0x180032cec`
- `0x1800352c0`
- `0x18003f6d0`
- `0x180044a38`
- `0x18004c024`
- `0x18004c7a8`
- `0x18004ca60`
- `0x180075fa0`
- `0x1800761a0`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003f852`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003f895`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003f9d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003fa1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003f852`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003f895`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003f9d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003fa1a`

## string_xrefs

- `0x18003f7e0`: `RollbackPolicy`
- `0x18003f93b`: `RollbackPolicy`
- `0x18003faed`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`
- `0x18003fb02`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`
- `0x18003fb17`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`
- `0x18003fb2c`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`
- `0x18003fb41`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`
- `0x18003fb56`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`
- `0x18003fb6b`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::Flighting::FeatureConfiguration::FeatureConfigurationsManager::GetFeatureRollbackPolicies(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  int v4; // eax
  const WCHAR *v5; // rdi
  __int64 *v6; // r14
  __int64 v7; // rbx
  __int64 v8; // rsi
  __int64 v9; // rax
  HRESULT v10; // eax
  __int64 v11; // rax
  HRESULT v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  HSTRING v15; // rbx
  HRESULT v16; // eax
  __int64 v17; // rax
  HRESULT v18; // eax
  int v19; // eax
  const char *v20; // r9
  __int64 result; // rax
  int v22; // [rsp+20h] [rbp-F8h]
  __int64 v23; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v24; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+40h] [rbp-D8h]
  HSTRING v26; // [rsp+48h] [rbp-D0h] BYREF
  const WCHAR *v27; // [rsp+50h] [rbp-C8h] BYREF
  __int64 *v28; // [rsp+58h] [rbp-C0h]
  HSTRING newString[2]; // [rsp+70h] [rbp-A8h] BYREF
  HSTRING v30[6]; // [rsp+80h] [rbp-98h] BYREF
  HSTRING v31[2]; // [rsp+B0h] [rbp-68h] BYREF
  HSTRING v32[2]; // [rsp+C0h] [rbp-58h] BYREF
  __int128 hstringHeader; // [rsp+D0h] [rbp-48h] BYREF
  __int128 hstringHeader_16; // [rsp+E0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v23 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  v4 = Windows::Foundation::Collections::Internal::Vector<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy,FeatureRollbackPolicyEquality,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy>>::Make(
         v3,
         &v23);
  try
  {
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2FF,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
        (const char *)(unsigned int)v4,
        v22);
    StagingControls_GetPersistedFeaturesForPriority(&v27, 4);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_alrStagingTool>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_alrStagingTool>::GetImpl'::`2'::impl) )
    {
      StagingControls_GetPersistedFeaturesForPriority(newString, 8);
      std::vector<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>>>,0>(
        (unsigned int)&v27,
        (unsigned int)&v26,
        (_DWORD)v28,
        newString[0],
        (__int64)newString[1]);
      std::vector<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>::_Tidy(newString);
    }
    v5 = v27;
    v6 = v28;
    while ( v5 != (const WCHAR *)v6 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_alrStagingTool>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_alrStagingTool>::GetImpl'::`2'::impl) )
      {
        if ( (v5[54] & 8) != 0 && *((_DWORD *)v5 + 25) != 3 )
        {
          v7 = *((_QWORD *)v5 + 14);
          v8 = *((_QWORD *)v5 + 15);
          while ( v7 != v8 )
          {
            v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
            if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                    v9,
                                    *(_QWORD *)(v7 + 16),
                                    L"RollbackPolicy",
                                    14) )
            {
              *(_OWORD *)newString = 0;
              *(_OWORD *)v30 = 0;
              LODWORD(newString[0]) = *(_DWORD *)v5;
              if ( *((_DWORD *)v5 + 1) == 4 && (v5[54] & 1) != 0 )
              {
                *((_QWORD *)&hstringHeader_16 + 1) = 0;
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                  (HSTRING_HEADER *)&hstringHeader,
                  v5 + 32,
                  0xCu,
                  0xBu);
                v10 = WindowsDuplicateString(*((HSTRING *)&hstringHeader_16 + 1), &newString[1]);
                if ( v10 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x31C,
                    (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigur"
                                  "ationsmanager.cpp",
                    (const char *)(unsigned int)v10,
                    v22);
              }
              v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7 + 32);
              v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v24);
              v12 = WindowsDuplicateString(*(HSTRING *)(v11 + 24), v30);
              if ( v12 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x31E,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
                  (const char *)(unsigned int)v12,
                  v22);
              HIDWORD(newString[0]) = *((_DWORD *)v5 + 1);
              hstringHeader = *(_OWORD *)newString;
              hstringHeader_16 = *(_OWORD *)v30;
              v13 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v23 + 104LL))(v23, &hstringHeader);
              if ( v13 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x320,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
                  (const char *)(unsigned int)v13,
                  v22);
              break;
            }
            v7 += 72;
          }
        }
      }
      else if ( (v5[54] & 9) == 9 && *((_DWORD *)v5 + 25) != 3 )
      {
        v25 = *(_QWORD *)v5;
        StagingControls_GetFeatureProperties(newString, v25);
        std::wstring::wstring(&hstringHeader);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
          newString,
          &v26,
          &hstringHeader);
        std::wstring::_Tidy_deallocate(&hstringHeader, v14);
        v15 = v26;
        if ( v26 != newString[1] )
        {
          *(_OWORD *)v31 = 0;
          *(_OWORD *)v32 = 0;
          LODWORD(v31[0]) = *(_DWORD *)v5;
          *((_QWORD *)&hstringHeader_16 + 1) = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            (HSTRING_HEADER *)&hstringHeader,
            v5 + 32,
            0xCu,
            0xBu);
          v16 = WindowsDuplicateString(*((HSTRING *)&hstringHeader_16 + 1), &v31[1]);
          if ( v16 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x335,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
              (const char *)(unsigned int)v16,
              v22);
          v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15 + 12);
          v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v24);
          v18 = WindowsDuplicateString(*(HSTRING *)(v17 + 24), v32);
          if ( v18 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x336,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
              (const char *)(unsigned int)v18,
              v22);
          hstringHeader = *(_OWORD *)v31;
          hstringHeader_16 = *(_OWORD *)v32;
          (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v23 + 104LL))(v23, &hstringHeader);
        }
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(newString);
      }
      v5 += 68;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 64LL))(v23, a2);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33D,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
        (const char *)(unsigned int)v19,
        v22);
    std::vector<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>::_Tidy(&v27);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x340,
                           (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featurec"
                                         "onfigurationsmanager.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x18003f6d0  mov     [rsp+arg_0], rbx
0x18003f6d5  mov     [rsp+arg_10], rsi
0x18003f6da  push    rdi
0x18003f6db  push    r14
0x18003f6dd  push    r15
0x18003f6df  sub     rsp, 100h
0x18003f6e6  mov     rax, cs:__security_cookie
0x18003f6ed  xor     rax, rsp
0x18003f6f0  mov     [rsp+118h+var_28], rax
0x18003f6f8  mov     r15, rdx
0x18003f6fb  mov     [rsp+118h+var_E8], 0
0x18003f704  lea     rcx, [rsp+118h+var_E8]
0x18003f709  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f70e  lea     rdx, [rsp+118h+var_E8]
0x18003f713  call    ?Make@?$Vector@UFeatureRollbackPolicy@FeatureConfiguration@Flighting@Internal@Windows@@UFeatureRollbackPolicyEquality@@UPodLifetimeTraits@XWinRT@@U?$DefaultVectorOptions@UFeatureRollbackPolicy@FeatureConfiguration@Flighting@Internal@Windows@@@4Collections@Foundation@5@@Internal@Collections@Foundation@Windows@@SAJAEBUFeatureRollbackPolicyEquality@@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy,FeatureRollbackPolicyEquality,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy>>::Make(FeatureRollbackPolicyEquality const &,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy,FeatureRollbackPolicyEquality,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy>> * *)
0x18003f718  mov     rcx, [rsp+118h]; this
0x18003f720  test    eax, eax
0x18003f722  js      loc_18003FAEA
0x18003f728  mov     edx, 4
0x18003f72d  lea     rcx, [rsp+118h+var_C8]
0x18003f732  call    ?StagingControls_GetPersistedFeaturesForPriority@@YA?AV?$vector@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@@std@@W4_RTL_FEATURE_CONFIGURATION_PRIORITY@@@Z; StagingControls_GetPersistedFeaturesForPriority(_RTL_FEATURE_CONFIGURATION_PRIORITY)
0x18003f737  nop
0x18003f738  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_alrStagingTool@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_alrStagingTool@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_alrStagingTool> `wil::Feature<__WilFeatureTraits_Feature_alrStagingTool>::GetImpl(void)'::`2'::impl
0x18003f73f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_alrStagingTool@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_alrStagingTool>::__private_IsEnabled(void)
0x18003f744  test    al, al
0x18003f746  jz      short loc_18003F786
0x18003f748  mov     edx, 8
0x18003f74d  lea     rcx, [rsp+118h+newString]
0x18003f752  call    ?StagingControls_GetPersistedFeaturesForPriority@@YA?AV?$vector@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@@std@@W4_RTL_FEATURE_CONFIGURATION_PRIORITY@@@Z; StagingControls_GetPersistedFeaturesForPriority(_RTL_FEATURE_CONFIGURATION_PRIORITY)
0x18003f757  nop
0x18003f758  mov     rax, [rsp+118h+newString+8]
0x18003f75d  mov     qword ptr [rsp+118h+var_F8], rax; int
0x18003f762  mov     r9, [rsp+118h+newString]
0x18003f767  mov     r8, [rsp+118h+var_C0]
0x18003f76c  lea     rdx, [rsp+118h+var_D0]
0x18003f771  lea     rcx, [rsp+118h+var_C8]
0x18003f776  call    ??$insert@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@@std@@@std@@$0A@@?$vector@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@@std@@@1@V21@1@Z; std::vector<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>>>,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>>>)
0x18003f77b  nop
0x18003f77c  lea     rcx, [rsp+118h+newString]
0x18003f781  call    ?_Tidy@?$vector@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@@std@@AEAAXXZ; std::vector<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>::_Tidy(void)
0x18003f786  mov     rdi, [rsp+118h+var_C8]
0x18003f78b  mov     r14, [rsp+118h+var_C0]
0x18003f790  cmp     rdi, r14
0x18003f793  jz      loc_18003FA80
0x18003f799  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_alrStagingTool@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_alrStagingTool@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_alrStagingTool> `wil::Feature<__WilFeatureTraits_Feature_alrStagingTool>::GetImpl(void)'::`2'::impl
0x18003f7a0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_alrStagingTool@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_alrStagingTool>::__private_IsEnabled(void)
0x18003f7a5  test    al, al
0x18003f7a7  jz      loc_18003F906
0x18003f7ad  test    byte ptr [rdi+6Ch], 8
0x18003f7b1  jz      loc_18003FA74
0x18003f7b7  cmp     dword ptr [rdi+64h], 3
0x18003f7bb  jz      loc_18003FA74
0x18003f7c1  mov     rbx, [rdi+70h]
0x18003f7c5  mov     rsi, [rdi+78h]
0x18003f7c9  cmp     rbx, rsi
0x18003f7cc  jz      loc_18003FA74
0x18003f7d2  mov     rcx, rbx
0x18003f7d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f7da  mov     r9d, 0Eh
0x18003f7e0  lea     r8, ?RollbackPolicy@FeatureMetadataUtils@@3QBGB; "RollbackPolicy"
0x18003f7e7  mov     rdx, [rbx+10h]
0x18003f7eb  mov     rcx, rax
0x18003f7ee  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18003f7f3  test    al, al
0x18003f7f5  jz      loc_18003F8FD
0x18003f7fb  xorps   xmm0, xmm0
0x18003f7fe  movups  xmmword ptr [rsp+118h+newString], xmm0
0x18003f803  movups  xmmword ptr [rsp+118h+var_98], xmm0
0x18003f80b  mov     eax, [rdi]
0x18003f80d  mov     dword ptr [rsp+118h+newString], eax
0x18003f811  cmp     dword ptr [rdi+4], 4
0x18003f815  jnz     short loc_18003F868
0x18003f817  test    byte ptr [rdi+6Ch], 1
0x18003f81b  jz      short loc_18003F868
0x18003f81d  mov     [rsp+118h+string], 0
0x18003f829  lea     rdx, [rdi+40h]; sourceString
0x18003f82d  mov     r9d, 0Bh; unsigned int
0x18003f833  lea     r8d, [r9+1]; unsigned int
0x18003f837  lea     rcx, [rsp+118h+hstringHeader]; hstringHeader
0x18003f83f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003f844  nop
0x18003f845  lea     rdx, [rsp+118h+newString+8]; newString
0x18003f84a  mov     rcx, [rsp+118h+string]; string
0x18003f852  call    cs:__imp_WindowsDuplicateString
0x18003f858  mov     rcx, [rsp+118h]; this
0x18003f860  test    eax, eax
0x18003f862  js      loc_18003FAFF
0x18003f868  lea     rcx, [rbx+20h]
0x18003f86c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f871  mov     [rsp+118h+var_E0], rax
0x18003f876  lea     rdx, [rsp+118h+var_E0]
0x18003f87b  lea     rcx, [rsp+118h+hstringHeader]
0x18003f883  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003f888  nop
0x18003f889  lea     rdx, [rsp+118h+var_98]; newString
0x18003f891  mov     rcx, [rax+18h]; string
0x18003f895  call    cs:__imp_WindowsDuplicateString
0x18003f89b  mov     rcx, [rsp+118h]; this
0x18003f8a3  test    eax, eax
0x18003f8a5  js      loc_18003FB14
0x18003f8ab  mov     eax, [rdi+4]
0x18003f8ae  mov     dword ptr [rsp+118h+newString+4], eax
0x18003f8b2  mov     rcx, [rsp+118h+var_E8]
0x18003f8b7  movups  xmm0, xmmword ptr [rsp+118h+newString]
0x18003f8bc  movaps  xmmword ptr [rsp+118h+hstringHeader.Reserved], xmm0
0x18003f8c4  movups  xmm1, xmmword ptr [rsp+118h+var_98]
0x18003f8cc  movaps  xmmword ptr [rsp+0E0h], xmm1
0x18003f8d4  mov     rax, [rcx]
0x18003f8d7  lea     rdx, [rsp+118h+hstringHeader]
0x18003f8df  mov     rax, [rax+68h]
0x18003f8e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8e8  mov     rcx, [rsp+118h]; this
0x18003f8f0  test    eax, eax
0x18003f8f2  js      loc_18003FB29
0x18003f8f8  jmp     loc_18003FA74
0x18003f8fd  add     rbx, 48h ; 'H'
0x18003f901  jmp     loc_18003F7C9
0x18003f906  mov     eax, [rdi+6Ch]
0x18003f909  and     eax, 9
0x18003f90c  cmp     al, 9
0x18003f90e  jnz     loc_18003FA74
0x18003f914  cmp     dword ptr [rdi+64h], 3
0x18003f918  jz      loc_18003FA74
0x18003f91e  mov     eax, [rdi]
0x18003f920  mov     dword ptr [rsp+118h+var_D8], eax
0x18003f924  mov     eax, [rdi+4]
0x18003f927  mov     dword ptr [rsp+118h+var_D8+4], eax
0x18003f92b  mov     rdx, [rsp+118h+var_D8]
0x18003f930  lea     rcx, [rsp+118h+newString]
0x18003f935  call    ?StagingControls_GetFeatureProperties@@YA?AV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@U_RTL_FEATURE_CONFIGURATION_ID@@@Z; StagingControls_GetFeatureProperties(_RTL_FEATURE_CONFIGURATION_ID)
0x18003f93a  nop
0x18003f93b  lea     rdx, ?RollbackPolicy@FeatureMetadataUtils@@3QBGB; "RollbackPolicy"
0x18003f942  lea     rcx, [rsp+118h+hstringHeader]
0x18003f94a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003f94f  lea     r8, [rsp+118h+hstringHeader]
0x18003f957  lea     rdx, [rsp+118h+var_D0]
0x18003f95c  lea     rcx, [rsp+118h+newString]
0x18003f961  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x18003f966  lea     rcx, [rsp+118h+hstringHeader]
0x18003f96e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003f973  mov     rbx, [rsp+118h+var_D0]
0x18003f978  cmp     rbx, [rsp+118h+newString+8]
0x18003f97d  jz      loc_18003FA6A
0x18003f983  xorps   xmm0, xmm0
0x18003f986  movups  xmmword ptr [rsp+118h+var_68], xmm0
0x18003f98e  movups  xmmword ptr [rsp+118h+var_58], xmm0
0x18003f996  mov     eax, [rdi]
0x18003f998  mov     dword ptr [rsp+118h+var_68], eax
0x18003f99f  mov     [rsp+118h+string], 0
0x18003f9ab  lea     rdx, [rdi+40h]; sourceString
0x18003f9af  mov     r9d, 0Bh; unsigned int
0x18003f9b5  lea     r8d, [r9+1]; unsigned int
0x18003f9b9  lea     rcx, [rsp+118h+hstringHeader]; hstringHeader
0x18003f9c1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003f9c6  nop
0x18003f9c7  lea     rdx, [rsp+118h+var_68+8]; newString
0x18003f9cf  mov     rcx, [rsp+118h+string]; string
0x18003f9d7  call    cs:__imp_WindowsDuplicateString
0x18003f9dd  mov     rcx, [rsp+118h]; this
0x18003f9e5  test    eax, eax
0x18003f9e7  js      loc_18003FB3E
0x18003f9ed  lea     rcx, [rbx+30h]
0x18003f9f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f9f6  mov     [rsp+118h+var_E0], rax
0x18003f9fb  lea     rdx, [rsp+118h+var_E0]
0x18003fa00  lea     rcx, [rsp+118h+hstringHeader]
0x18003fa08  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003fa0d  nop
0x18003fa0e  lea     rdx, [rsp+118h+var_58]; newString
0x18003fa16  mov     rcx, [rax+18h]; string
0x18003fa1a  call    cs:__imp_WindowsDuplicateString
0x18003fa20  mov     rcx, [rsp+118h]; this
0x18003fa28  test    eax, eax
0x18003fa2a  js      loc_18003FB53
0x18003fa30  mov     rcx, [rsp+118h+var_E8]
0x18003fa35  movups  xmm0, xmmword ptr [rsp+118h+var_68]
0x18003fa3d  movaps  xmmword ptr [rsp+118h+hstringHeader.Reserved], xmm0
0x18003fa45  movups  xmm1, xmmword ptr [rsp+118h+var_58]
0x18003fa4d  movaps  xmmword ptr [rsp+0E0h], xmm1
0x18003fa55  mov     rax, [rcx]
0x18003fa58  lea     rdx, [rsp+118h+hstringHeader]
0x18003fa60  mov     rax, [rax+68h]
0x18003fa64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa69  nop
0x18003fa6a  lea     rcx, [rsp+118h+newString]
0x18003fa6f  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18003fa74  add     rdi, 88h
0x18003fa7b  jmp     loc_18003F790
0x18003fa80  mov     rcx, [rsp+118h+var_E8]
0x18003fa85  mov     rax, [rcx]
0x18003fa88  mov     rdx, r15
0x18003fa8b  mov     rax, [rax+40h]
0x18003fa8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa94  mov     rcx, [rsp+118h]; this
0x18003fa9c  test    eax, eax
0x18003fa9e  js      loc_18003FB68
0x18003faa4  lea     rcx, [rsp+118h+var_C8]
0x18003faa9  call    ?_Tidy@?$vector@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@@std@@AEAAXXZ; std::vector<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>::_Tidy(void)
0x18003faae  nop
0x18003faaf  lea     rcx, [rsp+118h+var_E8]
0x18003fab4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003fab9  xor     eax, eax
0x18003fabb  jmp     short loc_18003FAC1
0x18003fabd  mov     eax, dword ptr [rsp+118h+var_E8]
0x18003fac1  mov     rcx, [rsp+118h+var_28]
0x18003fac9  xor     rcx, rsp; StackCookie
0x18003facc  call    __security_check_cookie
0x18003fad1  lea     r11, [rsp+118h+var_18]
0x18003fad9  mov     rbx, [r11+20h]
0x18003fadd  mov     rsi, [r11+30h]
0x18003fae1  mov     rsp, r11
0x18003fae4  pop     r15
0x18003fae6  pop     r14
0x18003fae8  pop     rdi
0x18003fae9  retn
0x18003faea  mov     r9d, eax; char *
0x18003faed  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x18003faf4  mov     edx, 2FFh; void *
0x18003faf9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003faff  mov     r9d, eax; char *
0x18003fb02  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x18003fb09  mov     edx, 31Ch; void *
0x18003fb0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003fb14  mov     r9d, eax; char *
0x18003fb17  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x18003fb1e  mov     edx, 31Eh; void *
0x18003fb23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003fb29  mov     r9d, eax; char *
0x18003fb2c  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x18003fb33  mov     edx, 320h; void *
0x18003fb38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003fb3e  mov     r9d, eax; char *
0x18003fb41  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x18003fb48  mov     edx, 335h; void *
0x18003fb4d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003fb53  mov     r9d, eax; char *
0x18003fb56  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x18003fb5d  mov     edx, 336h; void *
0x18003fb62  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003fb68  mov     r9d, eax; char *
0x18003fb6b  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x18003fb72  mov     edx, 33Dh; void *
0x18003fb77  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
