# FlagConfigurationEngine::ConvertInventoryFlagToFlag(ConfigurationManagement::Flags::DataModel::InventoryFlag const &,Windows::Internal::ConfigurationManagement::Flags::IFlag * *,ConfigurationManagement::Flags::FlagStateInformation const *,Windows::Internal::ConfigurationManagement::Flags::OperationResult)

- ea: `0x18009e708`
- end: `0x18009ee75`
- name: `?ConvertInventoryFlagToFlag@FlagConfigurationEngine@@AEAAJAEBUInventoryFlag@DataModel@Flags@ConfigurationManagement@@PEAPEAUIFlag@45Internal@Windows@@PEBUFlagStateInformation@45@W4OperationResult@4578@@Z`
- size: `1901`
- prototype: ``
- caller_count: `8`
- callee_count: `32`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18009e0f8`
- `0x1800a0980`
- `0x1800a0ce0`
- `0x1800a1320`
- `0x1800a1500`
- `0x1800a17a0`
- `0x1800a2360`
- `0x1800a2ae0`

## callees

- `0x180003220`
- `0x18000796c`
- `0x18000949c`
- `0x18000fef0`
- `0x180019788`
- `0x180019890`
- `0x1800277f0`
- `0x180043ce8`
- `0x18004b4dc`
- `0x180074708`
- `0x180075064`
- `0x180076d10`
- `0x18007fe40`
- `0x18009b27c`
- `0x18009b7dc`
- `0x18009b98c`
- `0x18009c90c`
- `0x18009d1cc`
- `0x18009d2c4`
- `0x18009d3d0`
- `0x18009e708`
- `0x18009ee7c`
- `0x18009fdc0`
- `0x1800a0640`
- `0x1800a0b04`
- `0x1800a3738`
- `0x1800a4ec0`
- `0x1800a58f8`
- `0x1800a596c`
- `0x1800a9228`
- `0x1800aa264`
- `0x1800b7010`

## string_xrefs

- `0x18009e75a`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x18009e798`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x18009e95d`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x18009ea57`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x18009ebda`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FlagConfigurationEngine::ConvertInventoryFlagToFlag(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        _BYTE *a4,
        int a5)
{
  unsigned int v8; // ebx
  _DWORD *v10; // rbx
  _DWORD *v11; // rcx
  __int64 Key; // rax
  __int64 v13; // rdx
  int v14; // eax
  _DWORD *v15; // rdi
  _DWORD *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // r8
  struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2 *v19; // rax
  __int64 **v20; // rdi
  __int64 *v21; // rbx
  FlagConfigurationEngine *v22; // rcx
  int v23; // eax
  unsigned int v24; // r14d
  __int64 v25; // rdx
  _DWORD *v26; // rcx
  const struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *v27; // rax
  __int64 v28; // rdx
  FlagConfigurationEngine *v29; // rcx
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  _QWORD *FeatureStateProvider; // rax
  __int64 v35; // rax
  _BYTE *v36; // rbx
  FlagConfigurationEngine *v37; // rcx
  int v38; // edi
  __int64 v39; // rdx
  _DWORD *v40; // rcx
  struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2 *v41; // rcx
  int v42; // edx
  __int64 v43; // rax
  int v44; // edx
  __int64 v45; // rax
  FlagConfigurationEngine *v46; // rcx
  struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2 *v47; // rdi
  int v48; // ecx
  __int64 v49; // rax
  int v50; // ecx
  __int64 v51; // rax
  _DWORD *v52; // rax
  _DWORD *v53; // rcx
  _DWORD *v54; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v55; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v56; // [rsp+38h] [rbp-C8h]
  struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2 *v57; // [rsp+40h] [rbp-C0h] BYREF
  struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2 *v58; // [rsp+48h] [rbp-B8h] BYREF
  struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2 *v59; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v60; // [rsp+58h] [rbp-A8h]
  _BYTE v61[144]; // [rsp+60h] [rbp-A0h] BYREF
  int v62; // [rsp+F0h] [rbp-10h]
  char v63; // [rsp+F4h] [rbp-Ch]
  __int16 v64; // [rsp+F5h] [rbp-Bh]
  char v65; // [rsp+F7h] [rbp-9h]
  char v66; // [rsp+FCh] [rbp-4h]
  char v67; // [rsp+104h] [rbp+4h]
  char v68; // [rsp+10Ch] [rbp+Ch]
  char v69; // [rsp+114h] [rbp+14h]
  _BYTE v70[184]; // [rsp+120h] [rbp+20h] BYREF
  struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2 *v71; // [rsp+1D8h] [rbp+D8h] BYREF
  std::_Ref_count_base *v72; // [rsp+1E0h] [rbp+E0h]
  _BYTE v73[56]; // [rsp+210h] [rbp+110h] BYREF
  char v74; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v60 = a1;
  if ( !a3 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x425,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
      (const char *)0x80070057LL,
      (int)v54);
    return v8;
  }
  *a3 = 0;
  Microsoft::WRL::Details::Make<Windows::Internal::ConfigurationManagement::Flags::Flag,>(&v54);
  v10 = v54;
  if ( !v54 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x429,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
      (const char *)0x8007000ELL,
      0);
LABEL_6:
    v11 = v54;
    if ( v54 )
    {
      v54 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Flighting::FeatureTuning::ISmartFeatureTuningManager>::Release(v11);
    }
    return v8;
  }
  Key = ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::GetKey(a2, &v71);
  ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::SetKey(v10 + 18, Key);
  std::wstring::_Tidy_deallocate(&v71, v13);
  ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::SetId(
    (ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)(v54 + 18),
    *(_DWORD *)(a2 + 32));
  if ( *(_DWORD *)(a2 + 68) == 1 )
  {
    v14 = 1;
  }
  else if ( *(_DWORD *)(a2 + 68) == 3 )
  {
    v14 = 3;
  }
  else
  {
    v14 = 0;
  }
  v54[32] = v14;
  v15 = v54;
  v16 = v54 + 34;
  if ( v54 + 34 != (_DWORD *)(a2 + 176) )
  {
    *v16 = *(_DWORD *)(a2 + 176);
    std::list<std::pair<std::wstring const,std::wstring>>::_Assign_cast<std::pair<std::wstring,std::wstring> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>>(
      v16 + 2,
      **(_QWORD **)(a2 + 184),
      *(_QWORD *)(a2 + 184));
    v17 = std::_Hash<std::_Umap_traits<unsigned int,enum Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfigurationState,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,enum Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfigurationState>>,0>>::_Desired_grow_bucket_count(
            v16,
            *((_QWORD *)v16 + 2));
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(
      v16,
      v17);
    v71 = 0;
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(&v71);
    v15 = v54;
  }
  *((_BYTE *)v15 + 200) = FlagConfigurationEngine::IsFlagReadOnly((const struct ConfigurationManagement::Flags::DataModel::InventoryFlag *)a2);
  v55 = 0;
  v56 = 0;
  v19 = 0;
  v57 = 0;
  v20 = *(__int64 ***)(a2 + 120);
  v21 = *v20;
  while ( v21 != (__int64 *)v20 )
  {
    v71 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
    v23 = FlagConfigurationEngine::ConvertInventoryFlagToFlagConfiguration2(
            v22,
            (const struct ConfigurationManagement::Flags::DataModel::InventoryFlag *)a2,
            (const struct ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration *)(v21 + 2),
            &v71);
    v24 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x436,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
        (const char *)(unsigned int)v23,
        (int)v54);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
      if ( (_QWORD)v55 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>>>(
          v55,
          *((_QWORD *)&v55 + 1));
        std::_Deallocate<16>(v55, (v56 - v55) & 0xFFFFFFFFFFFFFFF8uLL);
        v55 = 0;
        v56 = 0;
      }
      v26 = v54;
      if ( v54 )
      {
        v54 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Flighting::FeatureTuning::ISmartFeatureTuningManager>::Release(v26);
      }
      return v24;
    }
    v25 = *((_QWORD *)&v55 + 1);
    if ( *((_QWORD *)&v55 + 1) == v56 )
    {
      std::vector<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> const &>(
        &v55,
        *((_QWORD *)&v55 + 1),
        &v71);
    }
    else
    {
      **((_QWORD **)&v55 + 1) = v71;
      Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::InternalAddRef(v25);
      *((_QWORD *)&v55 + 1) += 8LL;
    }
    if ( *((_BYTE *)v21 + 72) && !v57 )
      Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::operator=(
        &v57,
        &v71);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
    v21 = (__int64 *)*v21;
    v19 = v57;
  }
  if ( !v19 )
  {
    LOBYTE(v18) = *(_BYTE *)(a2 + 56);
    v27 = (const struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(
                                                                                            &v71,
                                                                                            *(unsigned int *)(a2 + 32),
                                                                                            v18,
                                                                                            *(unsigned int *)(a2 + 80));
    ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(
      (ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)v73,
      v27);
    v74 = 0;
    std::wstring::_Tidy_deallocate(&v71, v28);
    v74 = 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
    v30 = FlagConfigurationEngine::ConvertInventoryFlagToFlagConfiguration2(
            v29,
            (const struct ConfigurationManagement::Flags::DataModel::InventoryFlag *)a2,
            (const struct ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration *)v73,
            &v57);
    v8 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x447,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
        (const char *)(unsigned int)v30,
        (int)v54);
      std::wstring::_Tidy_deallocate(v73, v31);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
      if ( (_QWORD)v55 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>>>(
          v55,
          *((_QWORD *)&v55 + 1));
        std::_Deallocate<16>(v55, (v56 - v55) & 0xFFFFFFFFFFFFFFF8uLL);
        v55 = 0;
        v56 = 0;
      }
      goto LABEL_6;
    }
    v32 = *((_QWORD *)&v55 + 1);
    if ( *((_QWORD *)&v55 + 1) == v56 )
    {
      std::vector<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> const &>(
        &v55,
        *((_QWORD *)&v55 + 1),
        &v57);
    }
    else
    {
      **((_QWORD **)&v55 + 1) = v57;
      Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::InternalAddRef(v32);
      *((_QWORD *)&v55 + 1) += 8LL;
    }
    std::wstring::_Tidy_deallocate(v73, v33);
  }
  v61[64] = 0;
  v61[136] = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  if ( !a4 )
  {
    FeatureStateProvider = (_QWORD *)FlagConfigurationEngine::GetFeatureStateProvider(v60, &v71);
    v35 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(*(_QWORD *)*FeatureStateProvider + 8LL))(
            *FeatureStateProvider,
            v70,
            a2);
    ConfigurationManagement::Flags::FlagStateInformation::operator=(v61, v35);
    ConfigurationManagement::Flags::FlagStateInformation::~FlagStateInformation((ConfigurationManagement::Flags::FlagStateInformation *)v70);
    if ( v72 )
      std::_Ref_count_base::_Decref(v72);
  }
  v36 = v61;
  if ( a4 )
    v36 = a4;
  v59 = 0;
  v58 = 0;
  if ( v36[64] )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
    if ( !v36[64] )
      goto LABEL_85;
    v38 = FlagConfigurationEngine::ConvertInventoryFlagToFlagConfiguration2(
            v37,
            (const struct ConfigurationManagement::Flags::DataModel::InventoryFlag *)a2,
            (const struct ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration *)v36,
            &v59);
    if ( v38 < 0 )
    {
      v39 = 1116;
LABEL_47:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v39,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
        (const char *)(unsigned int)v38,
        (int)v54);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
      ConfigurationManagement::Flags::FlagStateInformation::~FlagStateInformation((ConfigurationManagement::Flags::FlagStateInformation *)v61);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
      if ( (_QWORD)v55 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>>>(
          v55,
          *((_QWORD *)&v55 + 1));
        std::_Deallocate<16>(v55, (v56 - v55) & 0xFFFFFFFFFFFFFFF8uLL);
        v55 = 0;
        v56 = 0;
      }
      v40 = v54;
      if ( v54 )
      {
        v54 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Flighting::FeatureTuning::ISmartFeatureTuningManager>::Release(v40);
      }
      return (unsigned int)v38;
    }
    v41 = v59;
    if ( v36[156] )
      v42 = *((_DWORD *)v36 + 38);
    else
      v42 = 0;
    v43 = (__int64)v59 + 88;
    if ( !v59 )
      v43 = 136;
    *(_DWORD *)v43 = v42;
    if ( v36[172] )
      v44 = *((_DWORD *)v36 + 42);
    else
      v44 = 0;
    v45 = (__int64)v41 + 92;
    if ( !v41 )
      v45 = 140;
    *(_DWORD *)v45 = v44;
  }
  if ( !v36[136] )
    goto LABEL_80;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  if ( !v36[136] )
LABEL_85:
    std::_Throw_bad_optional_access();
  v38 = FlagConfigurationEngine::ConvertInventoryFlagToFlagConfiguration2(
          v46,
          (const struct ConfigurationManagement::Flags::DataModel::InventoryFlag *)a2,
          (const struct ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration *)(v36 + 72),
          &v58);
  if ( v38 < 0 )
  {
    v39 = 1129;
    goto LABEL_47;
  }
  v47 = v58;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::GetImpl'::`2'::impl) )
  {
    if ( v36[164] )
      v48 = *((_DWORD *)v36 + 40);
    else
      v48 = 0;
    v49 = (__int64)v47 + 88;
    if ( !v47 )
      v49 = 136;
    *(_DWORD *)v49 = v48;
  }
  if ( v36[180] )
    v50 = *((_DWORD *)v36 + 44);
  else
    v50 = 0;
  v51 = (__int64)v47 + 92;
  if ( !v47 )
    v51 = 140;
  *(_DWORD *)v51 = v50;
LABEL_80:
  Windows::Internal::ConfigurationManagement::Flags::Flag::set_AvailableConfigurations(v54, &v55);
  Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::operator=(
    v54 + 68,
    v59);
  Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::operator=(
    v54 + 70,
    v58);
  Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::operator=(
    v54 + 74,
    v57);
  v54[76] = *((_DWORD *)v36 + 36);
  v54[77] = a5;
  v52 = v54;
  v54 = 0;
  *a3 = (unsigned __int64)(v52 + 12) & -(__int64)(v52 != 0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
  ConfigurationManagement::Flags::FlagStateInformation::~FlagStateInformation((ConfigurationManagement::Flags::FlagStateInformation *)v61);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  if ( (_QWORD)v55 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>>>(
      v55,
      *((_QWORD *)&v55 + 1));
    std::_Deallocate<16>(v55, (v56 - v55) & 0xFFFFFFFFFFFFFFF8uLL);
    v55 = 0;
    v56 = 0;
  }
  v53 = v54;
  if ( v54 )
  {
    v54 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Flighting::FeatureTuning::ISmartFeatureTuningManager>::Release(v53);
  }
  return 0;
}

```

## disassembly

```asm
0x18009e708  push    rbp
0x18009e70a  push    rbx
0x18009e70b  push    rsi
0x18009e70c  push    rdi
0x18009e70d  push    r12
0x18009e70f  push    r13
0x18009e711  push    r14
0x18009e713  push    r15
0x18009e715  lea     rbp, [rsp-168h]
0x18009e71d  sub     rsp, 268h
0x18009e724  mov     rax, cs:__security_cookie
0x18009e72b  xor     rax, rsp
0x18009e72e  mov     [rbp+1A0h+var_50], rax
0x18009e735  mov     r12, r9
0x18009e738  mov     r13, r8
0x18009e73b  mov     rsi, rdx
0x18009e73e  mov     [rsp+2A0h+var_248], rcx
0x18009e743  xor     r14d, r14d
0x18009e746  test    r8, r8
0x18009e749  jnz     short loc_18009E772
0x18009e74b  mov     rcx, [rbp+1A8h]; this
0x18009e752  mov     ebx, 80070057h
0x18009e757  mov     r9d, ebx; char *
0x18009e75a  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x18009e761  mov     edx, 425h; void *
0x18009e766  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e76b  mov     eax, ebx
0x18009e76d  jmp     loc_18009EE4C
0x18009e772  mov     [r8], r14
0x18009e775  lea     rcx, [rsp+2A0h+var_280]
0x18009e77a  call    ??$Make@VFlag@Flags@ConfigurationManagement@Internal@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VFlag@Flags@ConfigurationManagement@Internal@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::Internal::ConfigurationManagement::Flags::Flag,>(void)
0x18009e77f  mov     rbx, [rsp+2A0h+var_280]
0x18009e784  test    rbx, rbx
0x18009e787  jnz     short loc_18009E7BF
0x18009e789  mov     rcx, [rbp+1A8h]; this
0x18009e790  mov     ebx, 8007000Eh
0x18009e795  mov     r9d, ebx; char *
0x18009e798  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x18009e79f  mov     edx, 429h; void *
0x18009e7a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e7a9  mov     rcx, [rsp+2A0h+var_280]
0x18009e7ae  test    rcx, rcx
0x18009e7b1  jz      short loc_18009E76B
0x18009e7b3  mov     [rsp+2A0h+var_280], r14
0x18009e7b8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UISmartFeatureTuningManager@FeatureTuning@Flighting@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Flighting::FeatureTuning::ISmartFeatureTuningManager>::Release(void)
0x18009e7bd  jmp     short loc_18009E76B
0x18009e7bf  lea     rdx, [rbp+1A0h+var_C8]
0x18009e7c6  mov     rcx, rsi
0x18009e7c9  call    ?GetKey@FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::GetKey(void)
0x18009e7ce  nop
0x18009e7cf  lea     rcx, [rbx+48h]
0x18009e7d3  mov     rdx, rax
0x18009e7d6  call    ?SetKey@FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::SetKey(std::wstring const &)
0x18009e7db  nop
0x18009e7dc  lea     rcx, [rbp+1A0h+var_C8]
0x18009e7e3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009e7e8  mov     rcx, [rsp+2A0h+var_280]
0x18009e7ed  add     rcx, 48h ; 'H'; this
0x18009e7f1  mov     edx, [rsi+20h]; unsigned int
0x18009e7f4  call    ?SetId@FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAAXI@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::SetId(uint)
0x18009e7f9  nop
0x18009e7fa  mov     rdx, [rsp+2A0h+var_280]
0x18009e7ff  mov     ecx, [rsi+44h]
0x18009e802  sub     ecx, 1
0x18009e805  jz      short loc_18009E818
0x18009e807  cmp     ecx, 2
0x18009e80a  jz      short loc_18009E811
0x18009e80c  mov     eax, r14d
0x18009e80f  jmp     short loc_18009E81D
0x18009e811  mov     eax, 3
0x18009e816  jmp     short loc_18009E81D
0x18009e818  mov     eax, 1
0x18009e81d  mov     [rdx+80h], eax
0x18009e823  mov     rdi, [rsp+2A0h+var_280]
0x18009e828  lea     rdx, [rsi+0B0h]
0x18009e82f  lea     rbx, [rdi+88h]
0x18009e836  cmp     rbx, rdx
0x18009e839  jz      short loc_18009E881
0x18009e83b  mov     eax, [rdx]
0x18009e83d  mov     [rbx], eax
0x18009e83f  mov     rdx, [rdx+8]
0x18009e843  lea     rcx, [rbx+8]
0x18009e847  mov     r8, rdx
0x18009e84a  mov     rdx, [rdx]
0x18009e84d  call    ??$_Assign_cast@AEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@2@@?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<std::pair<std::wstring const,std::wstring>>::_Assign_cast<std::pair<std::wstring,std::wstring> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>)
0x18009e852  mov     rdx, [rbx+10h]
0x18009e856  mov     rcx, rbx
0x18009e859  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@IW4PreviewFeatureConfigurationState@FeatureConfiguration@Flighting@Internal@Windows@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIW4PreviewFeatureConfigurationState@FeatureConfiguration@Flighting@Internal@Windows@@@std@@@7@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<uint,Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfigurationState,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfigurationState>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18009e85e  mov     rdx, rax
0x18009e861  mov     rcx, rbx
0x18009e864  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(unsigned __int64)
0x18009e869  mov     [rbp+1A0h+var_C8], r14
0x18009e870  lea     rcx, [rbp+1A0h+var_C8]
0x18009e877  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18009e87c  mov     rdi, [rsp+2A0h+var_280]
0x18009e881  mov     rcx, rsi; struct ConfigurationManagement::Flags::DataModel::InventoryFlag *
0x18009e884  call    ?IsFlagReadOnly@FlagConfigurationEngine@@CA_NAEBUInventoryFlag@DataModel@Flags@ConfigurationManagement@@@Z; FlagConfigurationEngine::IsFlagReadOnly(ConfigurationManagement::Flags::DataModel::InventoryFlag const &)
0x18009e889  mov     [rdi+0C8h], al
0x18009e88f  xorps   xmm0, xmm0
0x18009e892  movdqu  [rsp+2A0h+var_278], xmm0
0x18009e898  mov     [rsp+2A0h+var_268], r14
0x18009e89d  mov     rax, r14
0x18009e8a0  mov     [rsp+2A0h+var_260], rax
0x18009e8a5  mov     rdi, [rsi+78h]
0x18009e8a9  mov     rbx, [rdi]
0x18009e8ac  cmp     rbx, rdi
0x18009e8af  jz      loc_18009E9E0
0x18009e8b5  mov     [rbp+1A0h+var_C8], r14
0x18009e8bc  lea     rcx, [rbp+1A0h+var_C8]
0x18009e8c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e8c8  lea     r9, [rbp+1A0h+var_C8]; struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2 **
0x18009e8cf  lea     r8, [rbx+10h]; struct ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration *
0x18009e8d3  mov     rdx, rsi; struct ConfigurationManagement::Flags::DataModel::InventoryFlag *
0x18009e8d6  call    ?ConvertInventoryFlagToFlagConfiguration2@FlagConfigurationEngine@@AEAAJAEBUInventoryFlag@DataModel@Flags@ConfigurationManagement@@AEBUInventoryFlagConfiguration@345@PEAPEAUIFlagConfiguration2@45Internal@Windows@@@Z; FlagConfigurationEngine::ConvertInventoryFlagToFlagConfiguration2(ConfigurationManagement::Flags::DataModel::InventoryFlag const &,ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration const &,Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2 * *)
0x18009e8db  mov     r14d, eax
0x18009e8de  test    eax, eax
0x18009e8e0  js      short loc_18009E953
0x18009e8e2  mov     rdx, qword ptr [rsp+2A0h+var_278+8]
0x18009e8e7  cmp     rdx, [rsp+2A0h+var_268]
0x18009e8ec  jz      short loc_18009E908
0x18009e8ee  mov     rax, [rbp+1A0h+var_C8]
0x18009e8f5  mov     [rdx], rax
0x18009e8f8  mov     rcx, rdx
0x18009e8fb  call    ?InternalAddRef@?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::InternalAddRef(void)
0x18009e900  add     qword ptr [rsp+2A0h+var_278+8], 8
0x18009e906  jmp     short loc_18009E919
0x18009e908  lea     r8, [rbp+1A0h+var_C8]
0x18009e90f  lea     rcx, [rsp+2A0h+var_278]
0x18009e914  call    ??$_Emplace_reallocate@AEBV?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> const &>(Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> * const,Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> const &)
0x18009e919  xor     r14d, r14d
0x18009e91c  cmp     [rbx+48h], r14b
0x18009e920  jz      short loc_18009E93A
0x18009e922  cmp     [rsp+2A0h+var_260], r14
0x18009e927  jnz     short loc_18009E93A
0x18009e929  lea     rdx, [rbp+1A0h+var_C8]
0x18009e930  lea     rcx, [rsp+2A0h+var_260]
0x18009e935  call    ??4?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::operator=(Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> const &)
0x18009e93a  lea     rcx, [rbp+1A0h+var_C8]
0x18009e941  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e946  mov     rbx, [rbx]
0x18009e949  mov     rax, [rsp+2A0h+var_260]
0x18009e94e  jmp     loc_18009E8AC
0x18009e953  mov     rcx, [rbp+1A8h]; this
0x18009e95a  mov     r9d, r14d; char *
0x18009e95d  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x18009e964  mov     edx, 436h; void *
0x18009e969  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e96e  lea     rcx, [rbp+1A0h+var_C8]
0x18009e975  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e97a  lea     rcx, [rsp+2A0h+var_260]
0x18009e97f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e984  mov     rcx, qword ptr [rsp+2A0h+var_278]
0x18009e989  test    rcx, rcx
0x18009e98c  jz      short loc_18009E9C0
0x18009e98e  mov     rdx, qword ptr [rsp+2A0h+var_278+8]
0x18009e993  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>>>(Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> *,Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> * const,std::allocator<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>> &)
0x18009e998  mov     rcx, qword ptr [rsp+2A0h+var_278]
0x18009e99d  mov     rdx, [rsp+2A0h+var_268]
0x18009e9a2  sub     rdx, rcx
0x18009e9a5  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18009e9a9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009e9ae  xorps   xmm0, xmm0
0x18009e9b1  movdqu  [rsp+2A0h+var_278], xmm0
0x18009e9b7  mov     [rsp+2A0h+var_268], 0
0x18009e9c0  mov     rcx, [rsp+2A0h+var_280]
0x18009e9c5  test    rcx, rcx
0x18009e9c8  jz      short loc_18009E9D8
0x18009e9ca  mov     [rsp+2A0h+var_280], 0
0x18009e9d3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UISmartFeatureTuningManager@FeatureTuning@Flighting@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Flighting::FeatureTuning::ISmartFeatureTuningManager>::Release(void)
0x18009e9d8  mov     eax, r14d
0x18009e9db  jmp     loc_18009EE4C
0x18009e9e0  test    rax, rax
0x18009e9e3  jnz     loc_18009EAFE
0x18009e9e9  mov     r9d, [rsi+50h]
0x18009e9ed  mov     r8b, [rsi+38h]
0x18009e9f1  mov     edx, [rsi+20h]
0x18009e9f4  lea     rcx, [rbp+1A0h+var_C8]
0x18009e9fb  call    ??0FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAA@IEW4_RTL_FEATURE_ENABLED_STATE@@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(uint,uchar,_RTL_FEATURE_ENABLED_STATE)
0x18009ea00  mov     rdx, rax; struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *
0x18009ea03  lea     rcx, [rbp+1A0h+var_90]; this
0x18009ea0a  call    ??0FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAA@AEBV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey const &)
0x18009ea0f  mov     [rbp+1A0h+var_58], r14b
0x18009ea16  lea     rcx, [rbp+1A0h+var_C8]
0x18009ea1d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009ea22  mov     [rbp+1A0h+var_58], 1
0x18009ea29  lea     rcx, [rsp+2A0h+var_260]
0x18009ea2e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ea33  lea     r9, [rsp+2A0h+var_260]; struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2 **
0x18009ea38  lea     r8, [rbp+1A0h+var_90]; struct ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration *
0x18009ea3f  mov     rdx, rsi; struct ConfigurationManagement::Flags::DataModel::InventoryFlag *
0x18009ea42  call    ?ConvertInventoryFlagToFlagConfiguration2@FlagConfigurationEngine@@AEAAJAEBUInventoryFlag@DataModel@Flags@ConfigurationManagement@@AEBUInventoryFlagConfiguration@345@PEAPEAUIFlagConfiguration2@45Internal@Windows@@@Z; FlagConfigurationEngine::ConvertInventoryFlagToFlagConfiguration2(ConfigurationManagement::Flags::DataModel::InventoryFlag const &,ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration const &,Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2 * *)
0x18009ea47  mov     ebx, eax
0x18009ea49  test    eax, eax
0x18009ea4b  jns     short loc_18009EABF
0x18009ea4d  mov     rcx, [rbp+1A8h]; this
0x18009ea54  mov     r9d, eax; char *
0x18009ea57  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x18009ea5e  mov     edx, 447h; void *
0x18009ea63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ea68  lea     rcx, [rbp+1A0h+var_90]
0x18009ea6f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009ea74  lea     rcx, [rsp+2A0h+var_260]
0x18009ea79  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ea7e  mov     rcx, qword ptr [rsp+2A0h+var_278]
0x18009ea83  test    rcx, rcx
0x18009ea86  jz      loc_18009E7A9
0x18009ea8c  mov     rdx, qword ptr [rsp+2A0h+var_278+8]
0x18009ea91  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>>>(Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> *,Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> * const,std::allocator<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>> &)
0x18009ea96  mov     rcx, qword ptr [rsp+2A0h+var_278]
0x18009ea9b  mov     rdx, [rsp+2A0h+var_268]
0x18009eaa0  sub     rdx, rcx
0x18009eaa3  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18009eaa7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009eaac  xorps   xmm0, xmm0
0x18009eaaf  movdqu  [rsp+2A0h+var_278], xmm0
0x18009eab5  mov     [rsp+2A0h+var_268], r14
0x18009eaba  jmp     loc_18009E7A9
0x18009eabf  mov     rdx, qword ptr [rsp+2A0h+var_278+8]
0x18009eac4  cmp     rdx, [rsp+2A0h+var_268]
0x18009eac9  jz      short loc_18009EAE3
0x18009eacb  mov     rax, [rsp+2A0h+var_260]
0x18009ead0  mov     [rdx], rax
0x18009ead3  mov     rcx, rdx
0x18009ead6  call    ?InternalAddRef@?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::InternalAddRef(void)
0x18009eadb  add     qword ptr [rsp+2A0h+var_278+8], 8
0x18009eae1  jmp     short loc_18009EAF2
0x18009eae3  lea     r8, [rsp+2A0h+var_260]
0x18009eae8  lea     rcx, [rsp+2A0h+var_278]
0x18009eaed  call    ??$_Emplace_reallocate@AEBV?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> const &>(Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> * const,Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> const &)
0x18009eaf2  lea     rcx, [rbp+1A0h+var_90]
0x18009eaf9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009eafe  mov     [rbp+1A0h+var_200], r14b
0x18009eb02  mov     [rbp+1A0h+var_1B8], r14b
0x18009eb06  mov     [rbp+1A0h+var_1B0], r14d
0x18009eb0a  mov     [rbp+1A0h+var_1AC], r14b
0x18009eb0e  xor     eax, eax
0x18009eb10  mov     [rbp+1A0h+var_1AB], ax
0x18009eb14  mov     [rbp+1A0h+var_1A9], al
0x18009eb17  mov     [rbp+1A0h+var_1A4], r14b
0x18009eb1b  mov     [rbp+1A0h+var_19C], r14b
0x18009eb1f  mov     [rbp+1A0h+var_194], r14b
0x18009eb23  mov     [rbp+1A0h+var_18C], r14b
0x18009eb27  test    r12, r12
0x18009eb2a  jnz     short loc_18009EB7A
0x18009eb2c  lea     rdx, [rbp+1A0h+var_C8]
0x18009eb33  mov     rcx, [rsp+2A0h+var_248]
0x18009eb38  call    ?GetFeatureStateProvider@FlagConfigurationEngine@@QEAA?AV?$shared_ptr@VIFeatureStateProvider@Flags@ConfigurationManagement@@@std@@XZ; FlagConfigurationEngine::GetFeatureStateProvider(void)
0x18009eb3d  mov     rcx, [rax]
0x18009eb40  mov     rax, [rcx]
0x18009eb43  mov     r8, rsi
0x18009eb46  lea     rdx, [rbp+1A0h+var_180]
0x18009eb4a  mov     rax, [rax+8]
0x18009eb4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eb53  mov     rdx, rax
0x18009eb56  lea     rcx, [rsp+2A0h+var_240]
0x18009eb5b  call    ??4FlagStateInformation@Flags@ConfigurationManagement@@QEAAAEAU012@$$QEAU012@@Z; ConfigurationManagement::Flags::FlagStateInformation::operator=(ConfigurationManagement::Flags::FlagStateInformation &&)
0x18009eb60  lea     rcx, [rbp+1A0h+var_180]; this
0x18009eb64  call    ??1FlagStateInformation@Flags@ConfigurationManagement@@QEAA@XZ; ConfigurationManagement::Flags::FlagStateInformation::~FlagStateInformation(void)
0x18009eb69  mov     rcx, [rbp+1A0h+var_C0]; this
0x18009eb70  test    rcx, rcx
0x18009eb73  jz      short loc_18009EB7A
0x18009eb75  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009eb7a  lea     rbx, [rsp+2A0h+var_240]
0x18009eb7f  test    r12, r12
0x18009eb82  cmovnz  rbx, r12
0x18009eb86  mov     [rsp+2A0h+var_250], r14
0x18009eb8b  mov     [rsp+2A0h+var_258], r14
0x18009eb90  mov     r15d, 88h
0x18009eb96  lea     r12d, [r15+4]
0x18009eb9a  cmp     [rbx+40h], r14b
0x18009eb9e  jz      loc_18009ECAF
0x18009eba4  lea     rcx, [rsp+2A0h+var_250]
0x18009eba9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ebae  cmp     [rbx+40h], r14b
0x18009ebb2  jz      loc_18009EE6F
0x18009ebb8  lea     r9, [rsp+2A0h+var_250]; struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2 **
0x18009ebbd  mov     r8, rbx; struct ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration *
0x18009ebc0  mov     rdx, rsi; struct ConfigurationManagement::Flags::DataModel::InventoryFlag *
0x18009ebc3  call    ?ConvertInventoryFlagToFlagConfiguration2@FlagConfigurationEngine@@AEAAJAEBUInventoryFlag@DataModel@Flags@ConfigurationManagement@@AEBUInventoryFlagConfiguration@345@PEAPEAUIFlagConfiguration2@45Internal@Windows@@@Z; FlagConfigurationEngine::ConvertInventoryFlagToFlagConfiguration2(ConfigurationManagement::Flags::DataModel::InventoryFlag const &,ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration const &,Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2 * *)
0x18009ebc8  mov     edi, eax
0x18009ebca  test    eax, eax
0x18009ebcc  jns     loc_18009EC68
0x18009ebd2  mov     edx, 45Ch; void *
0x18009ebd7  mov     r9d, edi; char *
0x18009ebda  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x18009ebe1  mov     rcx, [rbp+1A8h]; this
0x18009ebe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ebed  lea     rcx, [rsp+2A0h+var_258]
0x18009ebf2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ebf7  lea     rcx, [rsp+2A0h+var_250]
0x18009ebfc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ec01  lea     rcx, [rsp+2A0h+var_240]; this
0x18009ec06  call    ??1FlagStateInformation@Flags@ConfigurationManagement@@QEAA@XZ; ConfigurationManagement::Flags::FlagStateInformation::~FlagStateInformation(void)
0x18009ec0b  lea     rcx, [rsp+2A0h+var_260]
0x18009ec10  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ec15  mov     rcx, qword ptr [rsp+2A0h+var_278]
0x18009ec1a  test    rcx, rcx
0x18009ec1d  jz      short loc_18009EC4D
0x18009ec1f  mov     rdx, qword ptr [rsp+2A0h+var_278+8]
0x18009ec24  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>>>(Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> *,Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2> * const,std::allocator<Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>> &)
  ... truncated ...
```
