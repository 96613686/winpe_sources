# LegacyFeatureStateProvider::GetFeatureState(ConfigurationManagement::Flags::DataModel::InventoryFlag const &)

- ea: `0x1800a8060`
- end: `0x1800a8751`
- name: `?GetFeatureState@LegacyFeatureStateProvider@@UEAA?AUFlagStateInformation@Flags@ConfigurationManagement@@AEBUInventoryFlag@DataModel@34@@Z`
- size: `1777`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180003220`
- `0x180006ae8`
- `0x180019890`
- `0x180034c5c`
- `0x180035334`
- `0x180076994`
- `0x180076a24`
- `0x180094f50`
- `0x18009b544`
- `0x18009c90c`
- `0x18009c954`
- `0x18009d1cc`
- `0x18009d314`
- `0x18009d340`
- `0x18009d598`
- `0x1800a3738`
- `0x1800a38b4`
- `0x1800a38d4`
- `0x1800a4ec0`
- `0x1800a7fd4`
- `0x1800a8060`

## import_xrefs

- `ntdll!RtlQueryInternalFeatureConfiguration` at `0x1800a8115`
- `ntdll!RtlQueryInternalFeatureConfiguration` at `0x1800a823e`
- `ntdll!RtlQueryInternalFeatureConfiguration` at `0x1800a8115`
- `ntdll!RtlQueryInternalFeatureConfiguration` at `0x1800a823e`

## string_xrefs

- `0x1800a873c`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\legacyfeaturestateprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall LegacyFeatureStateProvider::GetFeatureState(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r13
  bool v4; // r14
  unsigned int v5; // esi
  __int64 v6; // r9
  int v7; // r12d
  __m128i si128; // xmm1
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // r15d
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 HighestMutablePersistedFeaturePriority; // rax
  char v18; // di
  unsigned int *v19; // rsi
  __int64 v20; // r8
  int v21; // edi
  __int64 v22; // rax
  __int64 v23; // rdx
  char v24; // al
  __int128 *v25; // rsi
  const struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // r8
  int v29; // ecx
  __int64 v30; // rdx
  bool v31; // zf
  __int64 v32; // rdx
  wil::details::in1diag3 *v33; // r9
  int v34; // ebx
  __int64 v35; // rax
  __int64 v36; // r8
  __int64 v37; // r9
  bool v38; // bl
  char v39; // al
  __int64 v40; // rdx
  __int64 v41; // rdx
  char IsEnabled; // al
  __int64 v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // rdx
  char v49; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v50; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v51; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v52[64]; // [rsp+40h] [rbp-C0h] BYREF
  char v53; // [rsp+80h] [rbp-80h]
  _BYTE v54[72]; // [rsp+88h] [rbp-78h] BYREF
  int v55; // [rsp+D0h] [rbp-30h]
  bool v56; // [rsp+D4h] [rbp-2Ch]
  __int16 v57; // [rsp+D5h] [rbp-2Bh]
  char v58; // [rsp+D7h] [rbp-29h]
  __int64 v59; // [rsp+D8h] [rbp-28h]
  __int64 v60; // [rsp+E0h] [rbp-20h]
  __int64 v61; // [rsp+E8h] [rbp-18h]
  __int64 v62; // [rsp+F0h] [rbp-10h]
  int v63; // [rsp+100h] [rbp+0h]
  __int64 v64; // [rsp+108h] [rbp+8h]
  _BYTE v65[136]; // [rsp+110h] [rbp+10h] BYREF
  char v66; // [rsp+198h] [rbp+98h]
  _BYTE v67[144]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v68[144]; // [rsp+230h] [rbp+130h] BYREF
  __int128 v69; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v70; // [rsp+2D0h] [rbp+1D0h] BYREF
  _QWORD v71[7]; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v72; // [rsp+318h] [rbp+218h]
  _OWORD v73[2]; // [rsp+320h] [rbp+220h] BYREF
  __int64 v74; // [rsp+340h] [rbp+240h]
  int v75; // [rsp+348h] [rbp+248h]
  char v76; // [rsp+34Ch] [rbp+24Ch]
  int v77; // [rsp+350h] [rbp+250h]
  _OWORD v78[2]; // [rsp+358h] [rbp+258h] BYREF
  __int64 v79; // [rsp+378h] [rbp+278h]
  int v80; // [rsp+380h] [rbp+280h]
  char v81; // [rsp+384h] [rbp+284h]
  int v82; // [rsp+388h] [rbp+288h]
  _OWORD v83[2]; // [rsp+390h] [rbp+290h] BYREF
  __int64 v84; // [rsp+3B0h] [rbp+2B0h]
  int v85; // [rsp+3B8h] [rbp+2B8h]
  char v86; // [rsp+3BCh] [rbp+2BCh]
  int v87; // [rsp+3C0h] [rbp+2C0h]
  _BYTE v88[56]; // [rsp+3C8h] [rbp+2C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+348h]

  v3 = a3;
  v64 = a2;
  v50 = a2;
  v4 = 0;
  v63 = 0;
  v53 = 0;
  v54[64] = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  BYTE4(v59) = 0;
  BYTE4(v60) = 0;
  BYTE4(v61) = 0;
  BYTE4(v62) = 0;
  v5 = *(_DWORD *)(a3 + 32);
  v51 = 0;
  v50 = 0;
  v69 = 0;
  v70 = 0;
  v6 = *(unsigned int *)(a3 + 80);
  LOBYTE(a3) = *(_BYTE *)(a3 + 56);
  ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(v88, v5, a3, v6);
  v7 = RtlQueryInternalFeatureConfiguration(v5, 0, &v51, &v69);
  v78[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v78[1] = si128;
  LOWORD(v78[0]) = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  if ( !v7 )
  {
    v9 = DWORD1(v69) >> 8;
    LOBYTE(v9) = BYTE5(v69) & 0x3F;
    v10 = ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(
            v71,
            (unsigned int)v69,
            v9,
            (DWORD1(v69) >> 4) & 3);
    ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator=(v78, v10);
    std::wstring::_Tidy_deallocate(v71, v11);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  v83[0] = 0;
  v83[1] = si128;
  LOWORD(v83[0]) = 0;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v12 = *(_DWORD *)(v3 + 68);
  if ( v12 == 3 )
  {
    if ( !*(_BYTE *)(v3 + 76)
      || *(_DWORD *)std::optional<unsigned long>::value(v3 + 72)
      && *(_DWORD *)std::optional<unsigned long>::value(v3 + 72) != 1 )
    {
LABEL_9:
      v13 = -1073741823;
      if ( v12 != 1 )
        goto LABEL_12;
      goto LABEL_10;
    }
    v12 = *(_DWORD *)std::optional<unsigned long>::value(v3 + 72);
  }
  if ( v12 )
    goto LABEL_9;
LABEL_10:
  v13 = RtlQueryInternalFeatureConfiguration(v5, 1, &v50, &v70);
  if ( !v13 )
  {
    v14 = DWORD1(v70) >> 8;
    LOBYTE(v14) = BYTE5(v70) & 0x3F;
    v15 = ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(
            v71,
            (unsigned int)v70,
            v14,
            (DWORD1(v70) >> 4) & 3);
    ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator=(v83, v15);
    std::wstring::_Tidy_deallocate(v71, v16);
  }
LABEL_12:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::GetImpl'::`2'::impl) )
  {
    HighestMutablePersistedFeaturePriority = StagingControls_TryGetHighestMutablePersistedFeaturePriority(v68, v5);
    v18 = 1;
  }
  else
  {
    HighestMutablePersistedFeaturePriority = StagingControls_TryGetPersistedFeatureForPriority(v67, 11, v5);
    v18 = 2;
  }
  v66 = 0;
  if ( *(_BYTE *)(HighestMutablePersistedFeaturePriority + 136) )
  {
    _RTL_FEATURE_CONFIGURATION_DESCRIPTOR::_RTL_FEATURE_CONFIGURATION_DESCRIPTOR(
      v65,
      HighestMutablePersistedFeaturePriority);
    v66 = 1;
  }
  if ( (v18 & 2) != 0 )
  {
    v18 &= ~2u;
    std::_Optional_destruct_base<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR,0>::~_Optional_destruct_base<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR,0>(v67);
  }
  if ( (v18 & 1) != 0 )
    std::_Optional_destruct_base<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR,0>::~_Optional_destruct_base<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR,0>(v68);
  v49 = v66;
  v73[0] = 0;
  v73[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v73[0]) = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  if ( v66 )
  {
    v19 = (unsigned int *)std::optional<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>::value(v65);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::GetImpl'::`2'::impl) )
    {
      v4 = v19[1] == 11;
      v21 = v4 + 2;
    }
    else
    {
      v4 = 1;
      v21 = 3;
    }
    LOBYTE(v20) = *((_BYTE *)v19 + 16);
    v22 = ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(v71, *v19, v20, v19[2]);
    ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator=(v73, v22);
    std::wstring::_Tidy_deallocate(v71, v23);
  }
  else
  {
    v21 = 0;
  }
  if ( v12 == 3 )
  {
    v24 = 1;
    v25 = &v69;
  }
  else
  {
    v24 = 0;
    v7 = v13;
    v25 = &v70;
  }
  v26 = (const struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)v83;
  if ( v24 )
    v26 = (const struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)v78;
  if ( v7 )
  {
    ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(
      (ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)v71,
      (const struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)v88);
    v72 = 0;
    std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>(
      v52,
      v71);
    std::wstring::_Tidy_deallocate(v71, v32);
    v29 = 1;
    BYTE4(v61) = 1;
    v31 = *(_DWORD *)(v3 + 80) == 2;
  }
  else
  {
    ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(
      (ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)v71,
      v26);
    v72 = 0;
    std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>(
      v52,
      v71);
    std::wstring::_Tidy_deallocate(v71, v27);
    LODWORD(v59) = *((_DWORD *)v25 + 1) & 0xF;
    BYTE4(v59) = 1;
    *(_WORD *)((char *)&v59 + 5) = *(_WORD *)((char *)&v50 + 5);
    HIBYTE(v59) = HIBYTE(v50);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::GetImpl'::`2'::impl);
    v30 = *((unsigned int *)v25 + 1);
    BYTE4(v61) = 1;
    v29 = 3 - ((v30 & 0xF) != 11);
    LOBYTE(v30) = v30 & 0x30;
    v31 = (_BYTE)v30 == 32;
  }
  *(_WORD *)((char *)&v61 + 5) = *(_WORD *)((char *)&v50 + 5);
  v56 = v31;
  HIBYTE(v61) = HIBYTE(v50);
  LODWORD(v61) = v29;
  v55 = 0;
  v33 = retaddr;
  if ( !v53 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\legacyfeaturestateprovider.cpp",
      (const char *)retaddr);
  v34 = v12 - 1;
  if ( v34 )
  {
    if ( v34 == 2 )
    {
      v38 = 0;
      if ( v49 )
      {
        if ( v29 != v21
          || (v35 = std::optional<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::value(
                      v52,
                      v30,
                      v28,
                      retaddr),
              !(unsigned __int8)ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator==(
                                  v35,
                                  v73,
                                  v36,
                                  v37)) )
        {
          v38 = 1;
        }
      }
      v71[0] = &v49;
      v71[1] = v52;
      v71[2] = v25;
      v71[3] = v88;
      v39 = _lambda_3304a7ba869cfdc51ba00a54e1acd87b_::operator()(v71, v30, v28, v33);
      if ( v38 )
      {
        ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(
          (ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)v71,
          (const struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)v73);
        v72 = 0;
        std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>(
          v54,
          v71);
        std::wstring::_Tidy_deallocate(v71, v40);
        v55 = 1;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::GetImpl'::`2'::impl) )
        {
          LODWORD(v60) = *(_DWORD *)(std::optional<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>::value(v65) + 4);
          BYTE4(v60) = 1;
          *(_WORD *)((char *)&v60 + 5) = *(_WORD *)((char *)&v50 + 5);
          HIBYTE(v60) = HIBYTE(v50);
          LODWORD(v62) = v4 + 2;
        }
        else
        {
          LODWORD(v62) = 3;
        }
        goto LABEL_49;
      }
      if ( v39 )
      {
        ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(
          (ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)v71,
          (const struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)v88);
        v72 = 0;
        std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>(
          v54,
          v71);
        std::wstring::_Tidy_deallocate(v71, v41);
        v55 = 1;
        LODWORD(v62) = 1;
LABEL_49:
        BYTE4(v62) = 1;
        *(_WORD *)((char *)&v62 + 5) = *(_WORD *)((char *)&v50 + 5);
        HIBYTE(v62) = HIBYTE(v50);
      }
    }
  }
  else if ( !v7
         && (!(unsigned __int8)ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator==(
                                 v52,
                                 v78,
                                 v28,
                                 retaddr)
          || v50 != v51) )
  {
    v55 = 2;
    std::optional<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::operator=(v54, v52);
    v62 = v61;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::GetImpl'::`2'::impl);
    v43 = v60;
    if ( IsEnabled )
      v43 = v59;
    v60 = v43;
  }
  ConfigurationManagement::Flags::FlagStateInformation::FlagStateInformation(v64, v52, v28, v33);
  std::wstring::_Tidy_deallocate(v73, v44);
  std::_Optional_destruct_base<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR,0>::~_Optional_destruct_base<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR,0>(v65);
  std::wstring::_Tidy_deallocate(v83, v45);
  std::wstring::_Tidy_deallocate(v78, v46);
  std::wstring::_Tidy_deallocate(v88, v47);
  ConfigurationManagement::Flags::FlagStateInformation::~FlagStateInformation((ConfigurationManagement::Flags::FlagStateInformation *)v52);
  return v64;
}

```

## disassembly

```asm
0x1800a8060  mov     [rsp-8+arg_0], rbx
0x1800a8065  push    rbp
0x1800a8066  push    rsi
0x1800a8067  push    rdi
0x1800a8068  push    r12
0x1800a806a  push    r13
0x1800a806c  push    r14
0x1800a806e  push    r15
0x1800a8070  lea     rbp, [rsp-310h]
0x1800a8078  sub     rsp, 410h
0x1800a807f  mov     rax, cs:__security_cookie
0x1800a8086  xor     rax, rsp
0x1800a8089  mov     [rbp+340h+var_40], rax
0x1800a8090  mov     r13, r8
0x1800a8093  mov     [rbp+340h+var_338], rdx
0x1800a8097  mov     [rsp+440h+var_418], rdx
0x1800a809c  xor     r14d, r14d
0x1800a809f  mov     [rbp+340h+var_340], r14d
0x1800a80a3  mov     [rbp+340h+var_3C0], r14b
0x1800a80a7  mov     [rbp+340h+var_378], r14b
0x1800a80ab  mov     [rbp+340h+var_370], r14d
0x1800a80af  mov     [rbp+340h+var_36C], r14b
0x1800a80b3  xor     eax, eax
0x1800a80b5  mov     [rbp+340h+var_36B], ax
0x1800a80b9  mov     [rbp+340h+var_369], al
0x1800a80bc  mov     byte ptr [rbp+340h+var_368+4], r14b
0x1800a80c0  mov     byte ptr [rbp+340h+var_360+4], r14b
0x1800a80c4  mov     byte ptr [rbp+340h+var_358+4], r14b
0x1800a80c8  mov     byte ptr [rbp+340h+var_350+4], r14b
0x1800a80cc  mov     esi, [r8+20h]
0x1800a80d0  mov     [rsp+440h+var_410], r14
0x1800a80d5  mov     [rsp+440h+var_418], r14
0x1800a80da  xorps   xmm0, xmm0
0x1800a80dd  movups  [rbp+340h+var_180], xmm0
0x1800a80e4  xorps   xmm1, xmm1
0x1800a80e7  movups  [rbp+340h+var_170], xmm1
0x1800a80ee  mov     r9d, [r8+50h]
0x1800a80f2  mov     r8b, [r8+38h]
0x1800a80f6  mov     edx, esi
0x1800a80f8  lea     rcx, [rbp+340h+var_78]
0x1800a80ff  call    ??0FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAA@IEW4_RTL_FEATURE_ENABLED_STATE@@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(uint,uchar,_RTL_FEATURE_ENABLED_STATE)
0x1800a8104  nop
0x1800a8105  lea     r9, [rbp+340h+var_180]
0x1800a810c  lea     r8, [rsp+440h+var_410]
0x1800a8111  xor     edx, edx
0x1800a8113  mov     ecx, esi
0x1800a8115  call    cs:__imp_RtlQueryInternalFeatureConfiguration
0x1800a811b  mov     r12d, eax
0x1800a811e  xorps   xmm0, xmm0
0x1800a8121  movups  [rbp+340h+var_E8], xmm0
0x1800a8128  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800a8130  movdqu  [rbp+340h+var_D8], xmm1
0x1800a8138  mov     word ptr [rbp+340h+var_E8], r14w
0x1800a8140  mov     [rbp+340h+var_C8], r14
0x1800a8147  mov     [rbp+340h+var_C0], r14d
0x1800a814e  mov     [rbp+340h+var_BC], r14b
0x1800a8155  mov     [rbp+340h+var_B8], r14d
0x1800a815c  test    eax, eax
0x1800a815e  jnz     short loc_1800A81AF
0x1800a8160  mov     r8d, dword ptr [rbp+340h+var_180+4]
0x1800a8167  mov     r9d, r8d
0x1800a816a  shr     r9d, 4
0x1800a816e  and     r9d, 3
0x1800a8172  shr     r8d, 8
0x1800a8176  and     r8b, 3Fh
0x1800a817a  mov     edx, dword ptr [rbp+340h+var_180]
0x1800a8180  lea     rcx, [rbp+340h+var_160]
0x1800a8187  call    ??0FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAA@IEW4_RTL_FEATURE_ENABLED_STATE@@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(uint,uchar,_RTL_FEATURE_ENABLED_STATE)
0x1800a818c  mov     rdx, rax
0x1800a818f  lea     rcx, [rbp+340h+var_E8]
0x1800a8196  call    ??4FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAAAEAV0123@$$QEAV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator=(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey &&)
0x1800a819b  lea     rcx, [rbp+340h+var_160]
0x1800a81a2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a81a7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800a81af  xorps   xmm0, xmm0
0x1800a81b2  movups  [rbp+340h+var_B0], xmm0
0x1800a81b9  movdqu  [rbp+340h+var_A0], xmm1
0x1800a81c1  mov     word ptr [rbp+340h+var_B0], r14w
0x1800a81c9  mov     [rbp+340h+var_90], r14
0x1800a81d0  mov     [rbp+340h+var_88], r14d
0x1800a81d7  mov     [rbp+340h+var_84], r14b
0x1800a81de  mov     [rbp+340h+var_80], r14d
0x1800a81e5  mov     ebx, [r13+44h]
0x1800a81e9  cmp     ebx, 3
0x1800a81ec  jnz     short loc_1800A821C
0x1800a81ee  cmp     [r13+4Ch], r14b
0x1800a81f2  jz      short loc_1800A8220
0x1800a81f4  lea     rdi, [r13+48h]
0x1800a81f8  mov     rcx, rdi
0x1800a81fb  call    ?value@?$optional@K@std@@QEGBAAEBKXZ; std::optional<ulong>::value(void)
0x1800a8200  cmp     [rax], r14d
0x1800a8203  jz      short loc_1800A8212
0x1800a8205  mov     rcx, rdi
0x1800a8208  call    ?value@?$optional@K@std@@QEGBAAEBKXZ; std::optional<ulong>::value(void)
0x1800a820d  cmp     dword ptr [rax], 1
0x1800a8210  jnz     short loc_1800A8220
0x1800a8212  mov     rcx, rdi
0x1800a8215  call    ?value@?$optional@K@std@@QEGBAAEBKXZ; std::optional<ulong>::value(void)
0x1800a821a  mov     ebx, [rax]
0x1800a821c  test    ebx, ebx
0x1800a821e  jz      short loc_1800A822B
0x1800a8220  mov     r15d, 0C0000001h
0x1800a8226  cmp     ebx, 1
0x1800a8229  jnz     short loc_1800A8292
0x1800a822b  lea     r9, [rbp+340h+var_170]
0x1800a8232  lea     r8, [rsp+440h+var_418]
0x1800a8237  mov     edx, 1
0x1800a823c  mov     ecx, esi
0x1800a823e  call    cs:__imp_RtlQueryInternalFeatureConfiguration
0x1800a8244  mov     r15d, eax
0x1800a8247  test    eax, eax
0x1800a8249  jnz     short loc_1800A8292
0x1800a824b  mov     r8d, dword ptr [rbp+340h+var_170+4]
0x1800a8252  mov     r9d, r8d
0x1800a8255  shr     r9d, 4
0x1800a8259  and     r9d, 3
0x1800a825d  shr     r8d, 8
0x1800a8261  and     r8b, 3Fh
0x1800a8265  mov     edx, dword ptr [rbp+340h+var_170]
0x1800a826b  lea     rcx, [rbp+340h+var_160]
0x1800a8272  call    ??0FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAA@IEW4_RTL_FEATURE_ENABLED_STATE@@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(uint,uchar,_RTL_FEATURE_ENABLED_STATE)
0x1800a8277  mov     rdx, rax
0x1800a827a  lea     rcx, [rbp+340h+var_B0]
0x1800a8281  call    ??4FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAAAEAV0123@$$QEAV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator=(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey &&)
0x1800a8286  lea     rcx, [rbp+340h+var_160]
0x1800a828d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8292  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::GetImpl(void)'::`2'::impl
0x1800a8299  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::__private_IsEnabled(void)
0x1800a829e  test    al, al
0x1800a82a0  jz      short loc_1800A82B8
0x1800a82a2  mov     edx, esi
0x1800a82a4  lea     rcx, [rbp+340h+var_210]
0x1800a82ab  call    ?StagingControls_TryGetHighestMutablePersistedFeaturePriority@@YA?AV?$optional@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@I@Z; StagingControls_TryGetHighestMutablePersistedFeaturePriority(uint)
0x1800a82b0  nop
0x1800a82b1  mov     edi, 1
0x1800a82b6  jmp     short loc_1800A82D1
0x1800a82b8  mov     r8d, esi
0x1800a82bb  mov     edx, 0Bh
0x1800a82c0  lea     rcx, [rbp+340h+var_2A0]
0x1800a82c7  call    ?StagingControls_TryGetPersistedFeatureForPriority@@YA?AV?$optional@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@II@Z; StagingControls_TryGetPersistedFeatureForPriority(uint,uint)
0x1800a82cc  mov     edi, 2
0x1800a82d1  mov     [rbp+340h+var_2A8], r14b
0x1800a82d8  cmp     [rax+88h], r14b
0x1800a82df  jz      short loc_1800A82F4
0x1800a82e1  mov     rdx, rax
0x1800a82e4  lea     rcx, [rbp+340h+var_330]
0x1800a82e8  call    ??0_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@QEAA@$$QEAU0@@Z; _RTL_FEATURE_CONFIGURATION_DESCRIPTOR::_RTL_FEATURE_CONFIGURATION_DESCRIPTOR(_RTL_FEATURE_CONFIGURATION_DESCRIPTOR &&)
0x1800a82ed  mov     [rbp+340h+var_2A8], 1
0x1800a82f4  test    dil, 2
0x1800a82f8  jz      short loc_1800A830A
0x1800a82fa  and     edi, 0FFFFFFFDh
0x1800a82fd  lea     rcx, [rbp+340h+var_2A0]
0x1800a8304  call    ??1?$_Optional_destruct_base@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR,0>::~_Optional_destruct_base<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR,0>(void)
0x1800a8309  nop
0x1800a830a  test    dil, 1
0x1800a830e  jz      short loc_1800A831C
0x1800a8310  lea     rcx, [rbp+340h+var_210]
0x1800a8317  call    ??1?$_Optional_destruct_base@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR,0>::~_Optional_destruct_base<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR,0>(void)
0x1800a831c  mov     cl, [rbp+340h+var_2A8]
0x1800a8322  mov     [rsp+440h+var_420], cl
0x1800a8326  xorps   xmm0, xmm0
0x1800a8329  movups  [rbp+340h+var_120], xmm0
0x1800a8330  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800a8338  movdqu  [rbp+340h+var_110], xmm1
0x1800a8340  mov     word ptr [rbp+340h+var_120], r14w
0x1800a8348  mov     [rbp+340h+var_100], r14
0x1800a834f  mov     [rbp+340h+var_F8], r14d
0x1800a8356  mov     [rbp+340h+var_F4], r14b
0x1800a835d  mov     [rbp+340h+var_F0], r14d
0x1800a8364  test    cl, cl
0x1800a8366  jz      short loc_1800A83D0
0x1800a8368  lea     rcx, [rbp+340h+var_330]
0x1800a836c  call    ?value@?$optional@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@QEGAAAEAU_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@XZ; std::optional<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>::value(void)
0x1800a8371  mov     rsi, rax
0x1800a8374  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::GetImpl(void)'::`2'::impl
0x1800a837b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::__private_IsEnabled(void)
0x1800a8380  test    al, al
0x1800a8382  jz      short loc_1800A8395
0x1800a8384  cmp     dword ptr [rsi+4], 0Bh
0x1800a8388  setz    r14b
0x1800a838c  movzx   edi, r14b
0x1800a8390  add     edi, 2
0x1800a8393  jmp     short loc_1800A839D
0x1800a8395  mov     r14b, 1
0x1800a8398  mov     edi, 3
0x1800a839d  mov     r9d, [rsi+8]
0x1800a83a1  mov     r8b, [rsi+10h]
0x1800a83a5  mov     edx, [rsi]
0x1800a83a7  lea     rcx, [rbp+340h+var_160]
0x1800a83ae  call    ??0FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAA@IEW4_RTL_FEATURE_ENABLED_STATE@@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(uint,uchar,_RTL_FEATURE_ENABLED_STATE)
0x1800a83b3  mov     rdx, rax
0x1800a83b6  lea     rcx, [rbp+340h+var_120]
0x1800a83bd  call    ??4FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAAAEAV0123@$$QEAV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator=(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey &&)
0x1800a83c2  lea     rcx, [rbp+340h+var_160]
0x1800a83c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a83ce  jmp     short loc_1800A83D2
0x1800a83d0  xor     edi, edi
0x1800a83d2  cmp     ebx, 3
0x1800a83d5  jnz     short loc_1800A83E2
0x1800a83d7  mov     al, 1
0x1800a83d9  lea     rsi, [rbp+340h+var_180]
0x1800a83e0  jmp     short loc_1800A83EE
0x1800a83e2  xor     al, al
0x1800a83e4  mov     r12d, r15d
0x1800a83e7  lea     rsi, [rbp+340h+var_170]
0x1800a83ee  lea     rdx, [rbp+340h+var_B0]
0x1800a83f5  lea     rcx, [rbp+340h+var_E8]
0x1800a83fc  xor     r15d, r15d
0x1800a83ff  test    al, al
0x1800a8401  cmovnz  rdx, rcx; struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *
0x1800a8405  lea     rcx, [rbp+340h+var_160]; this
0x1800a840c  test    r12d, r12d
0x1800a840f  jnz     short loc_1800A8482
0x1800a8411  call    ??0FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAA@AEBV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey const &)
0x1800a8416  mov     [rbp+340h+var_128], r15b
0x1800a841d  lea     rdx, [rbp+340h+var_160]
0x1800a8424  lea     rcx, [rsp+440h+var_400]
0x1800a8429  call    ??$_Assign@UInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@?$_Optional_construct_base@UInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@std@@QEAAX$$QEAUInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@Z; std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>(ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration &&)
0x1800a842e  lea     rcx, [rbp+340h+var_160]
0x1800a8435  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a843a  mov     eax, [rsi+4]
0x1800a843d  and     eax, 0Fh
0x1800a8440  mov     dword ptr [rbp+340h+var_368], eax
0x1800a8443  mov     byte ptr [rbp+340h+var_368+4], 1
0x1800a8447  movzx   eax, word ptr [rsp+440h+var_418+5]
0x1800a844c  mov     word ptr [rbp+340h+var_368+5], ax
0x1800a8450  mov     al, byte ptr [rsp+440h+var_418+7]
0x1800a8454  mov     byte ptr [rbp+340h+var_368+7], al
0x1800a8457  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::GetImpl(void)'::`2'::impl
0x1800a845e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinCs_UseRegistryScanPendingConfigs>::__private_IsEnabled(void)
0x1800a8463  mov     edx, [rsi+4]
0x1800a8466  mov     byte ptr [rbp+340h+var_358+4], 1
0x1800a846a  test    al, al
0x1800a846c  mov     eax, edx
0x1800a846e  and     eax, 0Fh
0x1800a8471  sub     al, 0Bh
0x1800a8473  neg     al
0x1800a8475  sbb     ecx, ecx
0x1800a8477  add     ecx, 3
0x1800a847a  and     dl, 30h
0x1800a847d  cmp     dl, 20h ; ' '
0x1800a8480  jmp     short loc_1800A84BF
0x1800a8482  lea     rdx, [rbp+340h+var_78]; struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *
0x1800a8489  call    ??0FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAA@AEBV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey const &)
0x1800a848e  mov     [rbp+340h+var_128], r15b
0x1800a8495  lea     rdx, [rbp+340h+var_160]
0x1800a849c  lea     rcx, [rsp+440h+var_400]
0x1800a84a1  call    ??$_Assign@UInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@?$_Optional_construct_base@UInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@std@@QEAAX$$QEAUInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@Z; std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>(ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration &&)
0x1800a84a6  lea     rcx, [rbp+340h+var_160]
0x1800a84ad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a84b2  mov     ecx, 1
0x1800a84b7  mov     byte ptr [rbp+340h+var_358+4], cl
0x1800a84ba  cmp     dword ptr [r13+50h], 2
0x1800a84bf  movzx   eax, word ptr [rsp+440h+var_418+5]
0x1800a84c4  mov     word ptr [rbp+340h+var_358+5], ax
0x1800a84c8  mov     al, byte ptr [rsp+440h+var_418+7]
0x1800a84cc  setz    [rbp+340h+var_36C]
0x1800a84d0  mov     byte ptr [rbp+340h+var_358+7], al
0x1800a84d3  mov     dword ptr [rbp+340h+var_358], ecx
0x1800a84d6  mov     [rbp+340h+var_370], r15d
0x1800a84da  cmp     [rbp+340h+var_3C0], r15b
0x1800a84de  setz    al
0x1800a84e1  mov     r9, [rbp+348h]; char *
0x1800a84e8  test    al, al
0x1800a84ea  jnz     loc_1800A873C
0x1800a84f0  sub     ebx, 1
0x1800a84f3  jz      loc_1800A8659
0x1800a84f9  cmp     ebx, 2
0x1800a84fc  jnz     loc_1800A86B7
0x1800a8502  cmp     [rsp+440h+var_420], r15b
0x1800a8507  jz      short loc_1800A852E
0x1800a8509  cmp     ecx, edi
0x1800a850b  jnz     short loc_1800A852A
0x1800a850d  lea     rcx, [rsp+440h+var_400]
0x1800a8512  call    ?value@?$optional@UInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@std@@QEGAAAEAUInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@XZ; std::optional<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::value(void)
0x1800a8517  lea     rdx, [rbp+340h+var_120]
0x1800a851e  mov     rcx, rax
0x1800a8521  call    ??8FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEBA_NAEBV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator==(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey const &)
0x1800a8526  test    al, al
0x1800a8528  jnz     short loc_1800A852E
0x1800a852a  mov     bl, 1
0x1800a852c  jmp     short loc_1800A8531
0x1800a852e  mov     bl, r15b
0x1800a8531  lea     rax, [rsp+440h+var_420]
0x1800a8536  mov     [rbp+340h+var_160], rax
0x1800a853d  lea     rax, [rsp+440h+var_400]
0x1800a8542  mov     [rbp+340h+var_158], rax
0x1800a8549  mov     [rbp+340h+var_150], rsi
0x1800a8550  lea     rax, [rbp+340h+var_78]
0x1800a8557  mov     [rbp+340h+var_148], rax
0x1800a855e  lea     rcx, [rbp+340h+var_160]
0x1800a8565  call    ??R_lambda_3304a7ba869cfdc51ba00a54e1acd87b_@@QEBA@XZ; _lambda_3304a7ba869cfdc51ba00a54e1acd87b_::operator()(void)
0x1800a856a  test    bl, bl
0x1800a856c  jz      loc_1800A85F7
0x1800a8572  lea     rdx, [rbp+340h+var_120]; struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *
0x1800a8579  lea     rcx, [rbp+340h+var_160]; this
0x1800a8580  call    ??0FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAA@AEBV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey const &)
0x1800a8585  mov     [rbp+340h+var_128], r15b
0x1800a858c  lea     rdx, [rbp+340h+var_160]
0x1800a8593  lea     rcx, [rbp+340h+var_3B8]
  ... truncated ...
```
