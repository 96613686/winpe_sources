# FlagConfigurationEngine::GetFlagConfigurationEnablementState(ConfigurationManagement::Flags::DataModel::InventoryFlag const &)

- ea: `0x18009fe6c`
- end: `0x1800a0388`
- name: `?GetFlagConfigurationEnablementState@FlagConfigurationEngine@@AEAA?AUFlagStateInformation@Flags@ConfigurationManagement@@AEBUInventoryFlag@DataModel@34@@Z`
- size: `1308`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18009dfb0`
- `0x1800a0830`
- `0x1800a25a0`

## callees

- `0x180003220`
- `0x180019890`
- `0x180035334`
- `0x180076a24`
- `0x180094f50`
- `0x18009b504`
- `0x18009b544`
- `0x18009c90c`
- `0x18009d314`
- `0x18009d340`
- `0x18009d598`
- `0x18009fe6c`
- `0x1800a36fc`
- `0x1800a38b4`
- `0x1800a38d4`
- `0x1800a4ec0`

## import_xrefs

- `ntdll!RtlQueryInternalFeatureConfiguration` at `0x18009ff0c`
- `ntdll!RtlQueryInternalFeatureConfiguration` at `0x1800a0024`
- `ntdll!RtlQueryInternalFeatureConfiguration` at `0x18009ff0c`
- `ntdll!RtlQueryInternalFeatureConfiguration` at `0x1800a0024`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall FlagConfigurationEngine::GetFlagConfigurationEnablementState(__int64 a1, __int64 a2, __int64 a3)
{
  bool v5; // bl
  unsigned int v6; // r15d
  int v7; // r12d
  __m128i si128; // xmm1
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rdx
  int v12; // r14d
  int v13; // edi
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rdx
  unsigned int *v17; // rax
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rdx
  char v21; // r15
  __int64 *v22; // rdx
  _QWORD *j; // r8
  _QWORD *v24; // r9
  _QWORD **v25; // r12
  __int64 **v26; // rdi
  __int64 *i; // rbx
  int v28; // r14d
  __int64 v29; // rcx
  _QWORD *v30; // r8
  __int64 v31; // rax
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  _QWORD **v38; // rdi
  _QWORD *k; // rbx
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // r8
  __int64 v43; // r9
  _QWORD **v44; // rdi
  _QWORD *m; // rbx
  __int64 v46; // rcx
  __int64 v47; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v48[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v49[136]; // [rsp+40h] [rbp-C0h] BYREF
  char v50; // [rsp+C8h] [rbp-38h]
  __int128 v51; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v52; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v53[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v54; // [rsp+110h] [rbp+10h]
  int v55; // [rsp+118h] [rbp+18h]
  char v56; // [rsp+11Ch] [rbp+1Ch]
  int v57; // [rsp+120h] [rbp+20h]
  _OWORD v58[2]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v59; // [rsp+148h] [rbp+48h]
  int v60; // [rsp+150h] [rbp+50h]
  char v61; // [rsp+154h] [rbp+54h]
  int v62; // [rsp+158h] [rbp+58h]
  _OWORD v63[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v64; // [rsp+180h] [rbp+80h]
  int v65; // [rsp+188h] [rbp+88h]
  char v66; // [rsp+18Ch] [rbp+8Ch]
  int v67; // [rsp+190h] [rbp+90h]
  _BYTE v68[64]; // [rsp+1A0h] [rbp+A0h] BYREF

  v48[1] = a2;
  v5 = 0;
  *(_BYTE *)(a2 + 64) = 0;
  *(_BYTE *)(a2 + 136) = 0;
  *(_DWORD *)(a2 + 144) = 0;
  *(_BYTE *)(a2 + 148) = 0;
  *(_BYTE *)(a2 + 156) = 0;
  *(_BYTE *)(a2 + 164) = 0;
  *(_BYTE *)(a2 + 172) = 0;
  *(_BYTE *)(a2 + 180) = 0;
  v6 = *(_DWORD *)(a3 + 32);
  v47 = 0;
  v48[0] = 0;
  v52 = 0;
  v51 = 0;
  v7 = RtlQueryInternalFeatureConfiguration(v6, 0, &v47, &v52);
  v63[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v63[1] = si128;
  LOWORD(v63[0]) = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  if ( !v7 )
  {
    v9 = DWORD1(v52) >> 8;
    LOBYTE(v9) = BYTE5(v52) & 0x3F;
    v10 = ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(
            v53,
            (unsigned int)v52,
            v9,
            (DWORD1(v52) >> 4) & 3);
    ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator=(v63, v10);
    std::wstring::_Tidy_deallocate(v53, v11);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    if ( *(_DWORD *)(a3 + 68) == 3 )
    {
      *(_DWORD *)(a2 + 144) = 0;
      *(_BYTE *)(a2 + 148) = (BYTE4(v52) & 0x30) == 32;
    }
  }
  v53[0] = 0;
  v53[1] = si128;
  LOWORD(v53[0]) = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v12 = *(_DWORD *)(a3 + 68);
  if ( v12 == 3 )
  {
    if ( !*(_BYTE *)(a3 + 76) )
      goto LABEL_12;
    if ( *(_DWORD *)std::optional<unsigned long>::value(a3 + 72)
      && *(_DWORD *)std::optional<unsigned long>::value(a3 + 72) != 1 )
    {
      v5 = 0;
      goto LABEL_12;
    }
    v12 = *(_DWORD *)std::optional<unsigned long>::value(a3 + 72);
    v5 = 0;
  }
  if ( v12 )
  {
LABEL_12:
    v13 = -1073741823;
    if ( v12 != 1 )
      goto LABEL_15;
  }
  v13 = RtlQueryInternalFeatureConfiguration(v6, 1, v48, &v51);
  if ( !v13 )
  {
    v14 = DWORD1(v51) >> 8;
    LOBYTE(v14) = BYTE5(v51) & 0x3F;
    v15 = ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(
            v68,
            (unsigned int)v51,
            v14,
            (DWORD1(v51) >> 4) & 3);
    ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator=(v53, v15);
    std::wstring::_Tidy_deallocate(v68, v16);
    *(_DWORD *)(a2 + 144) = 0;
    *(_BYTE *)(a2 + 148) = (BYTE4(v51) & 0x30) == 32;
  }
LABEL_15:
  StagingControls_TryGetPersistedFeatureForPriority(v49, 11, v6);
  v58[0] = 0;
  v58[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v58[0]) = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  if ( v50 )
  {
    v17 = (unsigned int *)std::optional<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>::value(v49);
    LOBYTE(v18) = *((_BYTE *)v17 + 16);
    v19 = ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(v68, *v17, v18, v17[2]);
    ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator=(v58, v19);
    std::wstring::_Tidy_deallocate(v68, v20);
  }
  v21 = 0;
  if ( v13 && v7 )
    v5 = 1;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_ExplicitConfigs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_ExplicitConfigs>::GetImpl'::`2'::impl) )
  {
LABEL_23:
    if ( v5 )
      goto LABEL_24;
LABEL_30:
    v25 = (_QWORD **)(a3 + 120);
    goto LABEL_31;
  }
  if ( v12 == 3 )
  {
    v5 = v7 != 0;
    goto LABEL_23;
  }
  if ( !v13 )
    goto LABEL_30;
LABEL_24:
  v25 = (_QWORD **)(a3 + 120);
  v26 = *(__int64 ***)(a3 + 120);
  for ( i = *v26; i != (__int64 *)v26; i = (__int64 *)*i )
  {
    v22 = i + 2;
    if ( *((_BYTE *)i + 72) )
    {
      std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration const &>(
        a2,
        v22);
      *(_DWORD *)(a2 + 144) = 0;
      *(_BYTE *)(a2 + 148) = *(_DWORD *)(a3 + 80) == 2;
      v21 = 1;
    }
  }
LABEL_31:
  if ( v12 )
  {
    v28 = v12 - 1;
    if ( v28 )
    {
      if ( v28 == 2 )
      {
        if ( !v21 )
        {
          v24 = *(_QWORD **)(a3 + 120);
          for ( j = (_QWORD *)*v24; j != v24; j = (_QWORD *)*v30 )
          {
            if ( (unsigned __int8)ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator==(
                                    j + 2,
                                    v63,
                                    j,
                                    v24) )
            {
              std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration const &>(
                a2,
                v29);
              *(_DWORD *)(a2 + 144) = 0;
              *(_BYTE *)(a2 + 148) = (BYTE4(v52) & 0x30) == 32;
              break;
            }
          }
        }
        if ( *(_BYTE *)(a2 + 64) )
        {
          if ( v50 )
          {
            v31 = std::optional<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::value(
                    a2,
                    v22,
                    j,
                    v24);
            if ( !(unsigned __int8)ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator==(
                                     v31,
                                     v58,
                                     v32,
                                     v33) )
            {
              ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(
                (ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)v68,
                (const struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)v58);
              v68[56] = 0;
              std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>(
                a2 + 72,
                v68);
              std::wstring::_Tidy_deallocate(v68, v34);
              *(_DWORD *)(a2 + 144) = 1;
            }
          }
        }
      }
    }
    else
    {
      if ( !v21 )
      {
        v38 = (_QWORD **)*v25;
        for ( k = (_QWORD *)**v25; k != v38; k = (_QWORD *)*k )
        {
          if ( (unsigned __int8)ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator==(
                                  k + 2,
                                  v53,
                                  j,
                                  v24) )
          {
            std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration const &>(
              a2,
              v40);
            *(_BYTE *)(a2 + 148) = (BYTE4(v51) & 0x30) == 32;
          }
        }
      }
      if ( *(_BYTE *)(a2 + 64) )
      {
        if ( v21
          || (v41 = std::optional<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::value(
                      a2,
                      v22,
                      j,
                      v24),
              (unsigned __int8)ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator==(
                                 v41,
                                 v63,
                                 v42,
                                 v43))
          && v48[0] == v47 )
        {
          *(_DWORD *)(a2 + 144) = 0;
        }
        else
        {
          *(_DWORD *)(a2 + 144) = 2;
          std::optional<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::operator=(a2 + 72, a2);
        }
      }
    }
  }
  else if ( !v21 )
  {
    v44 = (_QWORD **)*v25;
    for ( m = (_QWORD *)**v25; m != v44; m = (_QWORD *)*m )
    {
      if ( (unsigned __int8)ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator==(
                              m + 2,
                              v53,
                              j,
                              v24) )
      {
        std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration const &>(
          a2,
          v46);
        *(_DWORD *)(a2 + 144) = 0;
        *(_BYTE *)(a2 + 148) = (BYTE4(v51) & 0x30) == 32;
      }
    }
  }
  std::wstring::_Tidy_deallocate(v58, v22);
  std::_Optional_destruct_base<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR,0>::~_Optional_destruct_base<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR,0>(v49);
  std::wstring::_Tidy_deallocate(v53, v35);
  std::wstring::_Tidy_deallocate(v63, v36);
  return a2;
}

```

## disassembly

```asm
0x18009fe6c  mov     [rsp-8+arg_0], rbx
0x18009fe71  push    rbp
0x18009fe72  push    rsi
0x18009fe73  push    rdi
0x18009fe74  push    r12
0x18009fe76  push    r13
0x18009fe78  push    r14
0x18009fe7a  push    r15
0x18009fe7c  lea     rbp, [rsp-0F0h]
0x18009fe84  sub     rsp, 1F0h
0x18009fe8b  mov     rax, cs:__security_cookie
0x18009fe92  xor     rax, rsp
0x18009fe95  mov     [rbp+120h+var_40], rax
0x18009fe9c  mov     r13, r8
0x18009fe9f  mov     rsi, rdx
0x18009fea2  mov     [rsp+220h+var_1E8], rdx
0x18009fea7  xor     ebx, ebx
0x18009fea9  mov     [rsp+220h+var_200], ebx
0x18009fead  mov     [rdx+40h], bl
0x18009feb0  mov     [rdx+88h], bl
0x18009feb6  mov     [rdx+90h], ebx
0x18009febc  mov     [rdx+94h], bl
0x18009fec2  mov     [rdx+9Ch], bl
0x18009fec8  mov     [rdx+0A4h], bl
0x18009fece  mov     [rdx+0ACh], bl
0x18009fed4  mov     [rdx+0B4h], bl
0x18009feda  mov     [rsp+220h+var_200], 1
0x18009fee2  mov     r15d, [r8+20h]
0x18009fee6  mov     [rsp+220h+var_1F8], rbx
0x18009feeb  mov     [rsp+220h+var_1F0], rbx
0x18009fef0  xorps   xmm0, xmm0
0x18009fef3  movups  [rbp+120h+var_140], xmm0
0x18009fef7  xorps   xmm1, xmm1
0x18009fefa  movups  [rbp+120h+var_150], xmm1
0x18009fefe  lea     r9, [rbp+120h+var_140]
0x18009ff02  lea     r8, [rsp+220h+var_1F8]
0x18009ff07  xor     edx, edx
0x18009ff09  mov     ecx, r15d
0x18009ff0c  call    cs:__imp_RtlQueryInternalFeatureConfiguration
0x18009ff12  mov     r12d, eax
0x18009ff15  xorps   xmm0, xmm0
0x18009ff18  movups  [rbp+120h+var_C0], xmm0
0x18009ff1c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18009ff24  movdqu  [rbp+120h+var_B0], xmm1
0x18009ff29  mov     word ptr [rbp+120h+var_C0], bx
0x18009ff2d  mov     [rbp+120h+var_A0], rbx
0x18009ff34  mov     [rbp+120h+var_98], ebx
0x18009ff3a  mov     [rbp+120h+var_94], bl
0x18009ff40  mov     [rbp+120h+var_90], ebx
0x18009ff46  test    eax, eax
0x18009ff48  jnz     short loc_18009FFA7
0x18009ff4a  mov     r8d, dword ptr [rbp+120h+var_140+4]
0x18009ff4e  mov     r9d, r8d
0x18009ff51  shr     r9d, 4
0x18009ff55  and     r9d, 3
0x18009ff59  shr     r8d, 8
0x18009ff5d  and     r8b, 3Fh
0x18009ff61  mov     edx, dword ptr [rbp+120h+var_140]
0x18009ff64  lea     rcx, [rbp+120h+var_130]
0x18009ff68  call    ??0FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAA@IEW4_RTL_FEATURE_ENABLED_STATE@@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(uint,uchar,_RTL_FEATURE_ENABLED_STATE)
0x18009ff6d  mov     rdx, rax
0x18009ff70  lea     rcx, [rbp+120h+var_C0]
0x18009ff74  call    ??4FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAAAEAV0123@$$QEAV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator=(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey &&)
0x18009ff79  lea     rcx, [rbp+120h+var_130]
0x18009ff7d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009ff82  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18009ff8a  cmp     dword ptr [r13+44h], 3
0x18009ff8f  jnz     short loc_18009FFA7
0x18009ff91  mov     [rsi+90h], ebx
0x18009ff97  mov     eax, dword ptr [rbp+120h+var_140+4]
0x18009ff9a  and     al, 30h
0x18009ff9c  cmp     al, 20h ; ' '
0x18009ff9e  setz    al
0x18009ffa1  mov     [rsi+94h], al
0x18009ffa7  xorps   xmm0, xmm0
0x18009ffaa  movups  [rbp+120h+var_130], xmm0
0x18009ffae  movdqu  [rbp+120h+var_120], xmm1
0x18009ffb3  mov     word ptr [rbp+120h+var_130], bx
0x18009ffb7  mov     [rbp+120h+var_110], rbx
0x18009ffbb  mov     [rbp+120h+var_108], ebx
0x18009ffbe  mov     [rbp+120h+var_104], bl
0x18009ffc1  mov     [rbp+120h+var_100], ebx
0x18009ffc4  mov     r14d, [r13+44h]
0x18009ffc8  cmp     r14d, 3
0x18009ffcc  jnz     short loc_18009FFFF
0x18009ffce  cmp     [r13+4Ch], bl
0x18009ffd2  jz      short loc_1800A0008
0x18009ffd4  lea     rbx, [r13+48h]
0x18009ffd8  mov     rcx, rbx
0x18009ffdb  call    ?value@?$optional@K@std@@QEGBAAEBKXZ; std::optional<ulong>::value(void)
0x18009ffe0  cmp     dword ptr [rax], 0
0x18009ffe3  jz      short loc_18009FFF2
0x18009ffe5  mov     rcx, rbx
0x18009ffe8  call    ?value@?$optional@K@std@@QEGBAAEBKXZ; std::optional<ulong>::value(void)
0x18009ffed  cmp     dword ptr [rax], 1
0x18009fff0  jnz     short loc_1800A0006
0x18009fff2  mov     rcx, rbx
0x18009fff5  call    ?value@?$optional@K@std@@QEGBAAEBKXZ; std::optional<ulong>::value(void)
0x18009fffa  mov     r14d, [rax]
0x18009fffd  xor     ebx, ebx
0x18009ffff  test    r14d, r14d
0x1800a0002  jz      short loc_1800A0013
0x1800a0004  jmp     short loc_1800A0008
0x1800a0006  xor     ebx, ebx
0x1800a0008  mov     edi, 0C0000001h
0x1800a000d  cmp     r14d, 1
0x1800a0011  jnz     short loc_1800A0084
0x1800a0013  lea     r9, [rbp+120h+var_150]
0x1800a0017  lea     r8, [rsp+220h+var_1F0]
0x1800a001c  mov     edx, 1
0x1800a0021  mov     ecx, r15d
0x1800a0024  call    cs:__imp_RtlQueryInternalFeatureConfiguration
0x1800a002a  mov     edi, eax
0x1800a002c  test    eax, eax
0x1800a002e  jnz     short loc_1800A0084
0x1800a0030  mov     r8d, dword ptr [rbp+120h+var_150+4]
0x1800a0034  mov     r9d, r8d
0x1800a0037  shr     r9d, 4
0x1800a003b  and     r9d, 3
0x1800a003f  shr     r8d, 8
0x1800a0043  and     r8b, 3Fh
0x1800a0047  mov     edx, dword ptr [rbp+120h+var_150]
0x1800a004a  lea     rcx, [rbp+120h+var_80]
0x1800a0051  call    ??0FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAA@IEW4_RTL_FEATURE_ENABLED_STATE@@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(uint,uchar,_RTL_FEATURE_ENABLED_STATE)
0x1800a0056  mov     rdx, rax
0x1800a0059  lea     rcx, [rbp+120h+var_130]
0x1800a005d  call    ??4FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAAAEAV0123@$$QEAV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator=(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey &&)
0x1800a0062  lea     rcx, [rbp+120h+var_80]
0x1800a0069  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a006e  mov     [rsi+90h], ebx
0x1800a0074  mov     eax, dword ptr [rbp+120h+var_150+4]
0x1800a0077  and     al, 30h
0x1800a0079  cmp     al, 20h ; ' '
0x1800a007b  setz    al
0x1800a007e  mov     [rsi+94h], al
0x1800a0084  mov     r8d, r15d
0x1800a0087  mov     edx, 0Bh
0x1800a008c  lea     rcx, [rsp+220h+var_1E0]
0x1800a0091  call    ?StagingControls_TryGetPersistedFeatureForPriority@@YA?AV?$optional@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@II@Z; StagingControls_TryGetPersistedFeatureForPriority(uint,uint)
0x1800a0096  nop
0x1800a0097  xorps   xmm0, xmm0
0x1800a009a  movups  [rbp+120h+var_F8], xmm0
0x1800a009e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800a00a6  movdqu  [rbp+120h+var_E8], xmm1
0x1800a00ab  mov     word ptr [rbp+120h+var_F8], bx
0x1800a00af  mov     [rbp+120h+var_D8], 0
0x1800a00b7  mov     [rbp+120h+var_D0], ebx
0x1800a00ba  mov     [rbp+120h+var_CC], bl
0x1800a00bd  mov     [rbp+120h+var_C8], ebx
0x1800a00c0  cmp     [rbp+120h+var_158], bl
0x1800a00c3  jz      short loc_1800A00FD
0x1800a00c5  lea     rcx, [rsp+220h+var_1E0]
0x1800a00ca  call    ?value@?$optional@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@QEGAAAEAU_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@XZ; std::optional<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>::value(void)
0x1800a00cf  mov     r9d, [rax+8]
0x1800a00d3  mov     r8b, [rax+10h]
0x1800a00d7  mov     edx, [rax]
0x1800a00d9  lea     rcx, [rbp+120h+var_80]
0x1800a00e0  call    ??0FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAA@IEW4_RTL_FEATURE_ENABLED_STATE@@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(uint,uchar,_RTL_FEATURE_ENABLED_STATE)
0x1800a00e5  mov     rdx, rax
0x1800a00e8  lea     rcx, [rbp+120h+var_F8]
0x1800a00ec  call    ??4FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAAAEAV0123@$$QEAV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator=(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey &&)
0x1800a00f1  lea     rcx, [rbp+120h+var_80]
0x1800a00f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a00fd  mov     r15b, bl
0x1800a0100  test    edi, edi
0x1800a0102  jz      short loc_1800A010B
0x1800a0104  test    r12d, r12d
0x1800a0107  jz      short loc_1800A010B
0x1800a0109  mov     bl, 1
0x1800a010b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FCON_WinCs_ExplicitConfigs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FCON_WinCs_ExplicitConfigs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_ExplicitConfigs> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_ExplicitConfigs>::GetImpl(void)'::`2'::impl
0x1800a0112  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FCON_WinCs_ExplicitConfigs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_ExplicitConfigs>::__private_IsEnabled(void)
0x1800a0117  test    al, al
0x1800a0119  jz      short loc_1800A0127
0x1800a011b  cmp     r14d, 3
0x1800a011f  jnz     short loc_1800A016D
0x1800a0121  test    r12d, r12d
0x1800a0124  setnz   bl
0x1800a0127  test    bl, bl
0x1800a0129  jz      short loc_1800A0171
0x1800a012b  lea     r12, [r13+78h]
0x1800a012f  mov     rdi, [r12]
0x1800a0133  mov     rbx, [rdi]
0x1800a0136  cmp     rbx, rdi
0x1800a0139  jz      short loc_1800A0175
0x1800a013b  lea     rdx, [rbx+10h]
0x1800a013f  cmp     byte ptr [rdx+38h], 0
0x1800a0143  jz      short loc_1800A0168
0x1800a0145  mov     rcx, rsi
0x1800a0148  call    ??$_Assign@AEBUInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@?$_Optional_construct_base@UInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@std@@QEAAXAEBUInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@Z; std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration const &>(ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration const &)
0x1800a014d  mov     dword ptr [rsi+90h], 0
0x1800a0157  cmp     dword ptr [r13+50h], 2
0x1800a015c  setz    al
0x1800a015f  mov     [rsi+94h], al
0x1800a0165  mov     r15b, 1
0x1800a0168  mov     rbx, [rbx]
0x1800a016b  jmp     short loc_1800A0136
0x1800a016d  test    edi, edi
0x1800a016f  jnz     short loc_1800A012B
0x1800a0171  lea     r12, [r13+78h]
0x1800a0175  test    r14d, r14d
0x1800a0178  jz      loc_1800A0333
0x1800a017e  sub     r14d, 1
0x1800a0182  jz      loc_1800A0294
0x1800a0188  cmp     r14d, 2
0x1800a018c  jnz     loc_1800A023F
0x1800a0192  test    r15b, r15b
0x1800a0195  jnz     short loc_1800A01DE
0x1800a0197  mov     r9, [r13+78h]
0x1800a019b  mov     r8, [r9]
0x1800a019e  cmp     r8, r9
0x1800a01a1  jz      short loc_1800A01DE
0x1800a01a3  lea     rcx, [r8+10h]
0x1800a01a7  lea     rdx, [rbp+120h+var_C0]
0x1800a01ab  call    ??8FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEBA_NAEBV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator==(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey const &)
0x1800a01b0  test    al, al
0x1800a01b2  jnz     short loc_1800A01B9
0x1800a01b4  mov     r8, [r8]
0x1800a01b7  jmp     short loc_1800A019E
0x1800a01b9  mov     rdx, rcx
0x1800a01bc  mov     rcx, rsi
0x1800a01bf  call    ??$_Assign@AEBUInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@?$_Optional_construct_base@UInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@std@@QEAAXAEBUInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@Z; std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration const &>(ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration const &)
0x1800a01c4  mov     dword ptr [rsi+90h], 0
0x1800a01ce  mov     eax, dword ptr [rbp+120h+var_140+4]
0x1800a01d1  and     al, 30h
0x1800a01d3  cmp     al, 20h ; ' '
0x1800a01d5  setz    al
0x1800a01d8  mov     [rsi+94h], al
0x1800a01de  cmp     byte ptr [rsi+40h], 0
0x1800a01e2  jz      short loc_1800A023F
0x1800a01e4  cmp     [rbp+120h+var_158], 0
0x1800a01e8  jz      short loc_1800A023F
0x1800a01ea  mov     rcx, rsi
0x1800a01ed  call    ?value@?$optional@UInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@std@@QEGAAAEAUInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@XZ; std::optional<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::value(void)
0x1800a01f2  lea     rdx, [rbp+120h+var_F8]
0x1800a01f6  mov     rcx, rax
0x1800a01f9  call    ??8FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEBA_NAEBV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator==(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey const &)
0x1800a01fe  test    al, al
0x1800a0200  jnz     short loc_1800A023F
0x1800a0202  lea     rdx, [rbp+120h+var_F8]; struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *
0x1800a0206  lea     rcx, [rbp+120h+var_80]; this
0x1800a020d  call    ??0FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAA@AEBV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey const &)
0x1800a0212  mov     [rbp+120h+var_48], 0
0x1800a0219  lea     rdx, [rbp+120h+var_80]
0x1800a0220  lea     rcx, [rsi+48h]
0x1800a0224  call    ??$_Assign@UInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@?$_Optional_construct_base@UInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@std@@QEAAX$$QEAUInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@Z; std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>(ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration &&)
0x1800a0229  lea     rcx, [rbp+120h+var_80]
0x1800a0230  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a0235  mov     dword ptr [rsi+90h], 1
0x1800a023f  lea     rcx, [rbp+120h+var_F8]
0x1800a0243  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a0248  nop
0x1800a0249  lea     rcx, [rsp+220h+var_1E0]
0x1800a024e  call    ??1?$_Optional_destruct_base@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR,0>::~_Optional_destruct_base<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR,0>(void)
0x1800a0253  nop
0x1800a0254  lea     rcx, [rbp+120h+var_130]
0x1800a0258  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a025d  nop
0x1800a025e  lea     rcx, [rbp+120h+var_C0]
0x1800a0262  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a0267  mov     rax, rsi
0x1800a026a  mov     rcx, [rbp+120h+var_40]
0x1800a0271  xor     rcx, rsp; StackCookie
0x1800a0274  call    __security_check_cookie
0x1800a0279  mov     rbx, [rsp+220h+arg_0]
0x1800a0281  add     rsp, 1F0h
0x1800a0288  pop     r15
0x1800a028a  pop     r14
0x1800a028c  pop     r13
0x1800a028e  pop     r12
0x1800a0290  pop     rdi
0x1800a0291  pop     rsi
0x1800a0292  pop     rbp
0x1800a0293  retn
0x1800a0294  test    r15b, r15b
0x1800a0297  jnz     short loc_1800A02D6
0x1800a0299  mov     rdi, [r12]
0x1800a029d  mov     rbx, [rdi]
0x1800a02a0  cmp     rbx, rdi
0x1800a02a3  jz      short loc_1800A02D6
0x1800a02a5  lea     rcx, [rbx+10h]
0x1800a02a9  lea     rdx, [rbp+120h+var_130]
0x1800a02ad  call    ??8FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEBA_NAEBV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::operator==(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey const &)
0x1800a02b2  test    al, al
0x1800a02b4  jz      short loc_1800A02D1
0x1800a02b6  mov     rdx, rcx
0x1800a02b9  mov     rcx, rsi
0x1800a02bc  call    ??$_Assign@AEBUInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@?$_Optional_construct_base@UInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@std@@QEAAXAEBUInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@Z; std::_Optional_construct_base<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::_Assign<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration const &>(ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration const &)
0x1800a02c1  mov     eax, dword ptr [rbp+120h+var_150+4]
0x1800a02c4  and     al, 30h
0x1800a02c6  cmp     al, 20h ; ' '
0x1800a02c8  setz    al
0x1800a02cb  mov     [rsi+94h], al
0x1800a02d1  mov     rbx, [rbx]
0x1800a02d4  jmp     short loc_1800A02A0
0x1800a02d6  cmp     byte ptr [rsi+40h], 0
0x1800a02da  jz      loc_1800A023F
0x1800a02e0  test    r15b, r15b
0x1800a02e3  jnz     short loc_1800A0324
0x1800a02e5  mov     rcx, rsi
0x1800a02e8  call    ?value@?$optional@UInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@@std@@QEGAAAEAUInventoryFlagConfiguration@DataModel@Flags@ConfigurationManagement@@XZ; std::optional<ConfigurationManagement::Flags::DataModel::InventoryFlagConfiguration>::value(void)
  ... truncated ...
```
