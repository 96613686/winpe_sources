# CModule::InitPresentEffectsEligibility(void)

- ea: `0x1800650dc`
- end: `0x180065793`
- name: `?InitPresentEffectsEligibility@CModule@@QEAAXXZ`
- size: `1719`
- prototype: `void __fastcall(CModule *__hidden this)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005be40`
- `0x180066040`

## callees

- `0x18000c6b0`
- `0x18001c7a4`
- `0x18001c934`
- `0x18001cf1c`
- `0x18001d4cc`
- `0x1800306f4`
- `0x180055ed4`
- `0x18005d2d0`
- `0x18005ed64`
- `0x18006445c`
- `0x180064640`
- `0x180064fe4`
- `0x1800650dc`
- `0x180067db4`
- `0x18006bae0`
- `0x18006c7f4`
- `0x18008a1ec`
- `0x18008af48`
- `0x18008d830`
- `0x18008f19c`
- `0x180090878`
- `0x180092128`
- `0x180092224`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800654a9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800654a9`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryUserGlobalSettings` at `0x1800651c1`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryUserGlobalSettings` at `0x1800651c1`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabaseConfig` at `0x180065207`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabaseConfig` at `0x1800653bf`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabaseConfig` at `0x180065207`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabaseConfig` at `0x1800653bf`
- `ext-ms-win-dx-dxdbhelper-l1-1-2!__imp_QueryFullPreferenceData` at `0x180065285`
- `ext-ms-win-dx-dxdbhelper-l1-1-2!__imp_QueryFullPreferenceData` at `0x180065285`
- `ext-ms-win-dx-dxdbhelper-l1-1-1!__imp_WriteUserGlobalSetting` at `0x1800656c7`
- `ext-ms-win-dx-dxdbhelper-l1-1-1!__imp_WriteUserGlobalSetting` at `0x180065729`
- `ext-ms-win-dx-dxdbhelper-l1-1-1!__imp_WriteUserGlobalSetting` at `0x1800656c7`
- `ext-ms-win-dx-dxdbhelper-l1-1-1!__imp_WriteUserGlobalSetting` at `0x180065729`

## string_xrefs

- `0x1800653d3`: `Failed to query effects device config`
- `0x1800653f3`: `PresentFx.DeviceConfigOverride`
- `0x1800654ce`: `Res limits enabled by registry`
- `0x1800654c7`: `Res limits disabled by registry`
- `0x18006563d`: `PresentFx.ForceComposeDx11`
- `0x180065769`: `HdrToSdrShimOverride`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CModule::InitPresentEffectsEligibility(CModule *this)
{
  char *v2; // r15
  char *v3; // r12
  int v4; // esi
  CModule *v5; // rcx
  unsigned __int8 v6; // di
  _BYTE *v7; // r14
  char v8; // dl
  signed int UserGlobalSettings; // eax
  CModule *v10; // rcx
  bool v11; // r9
  __int64 v12; // rdx
  unsigned int v13; // edi
  signed int FullPreferenceData; // eax
  CModule *v15; // rcx
  bool v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  bool v20; // si
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // rdx
  signed int v25; // eax
  CModule *v26; // rcx
  bool v27; // r9
  _DWORD *v28; // rsi
  bool v29; // si
  LSTATUS ValueW; // eax
  CModule *v31; // rcx
  bool v32; // r9
  bool v33; // sf
  const char *v34; // r8
  unsigned int v35; // eax
  unsigned int v36; // eax
  char v37; // si
  char v38; // si
  __int64 v39; // rcx
  _BOOL8 v40; // rax
  unsigned __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rdx
  bool IsPresentEffectsPackagePresent; // cl
  CModule *v45; // rcx
  unsigned __int64 v46; // rax
  unsigned int v47; // eax
  bool v48; // r9
  CModule *v49; // rcx
  __int64 v50; // rdx
  unsigned int v51; // eax
  bool v52; // r9
  CModule *v53; // rcx
  __int64 v54; // r8
  __int64 v55; // rdx
  unsigned __int64 pvData; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int64 pcbData; // [rsp+88h] [rbp+48h] BYREF
  HKEY hkey; // [rsp+90h] [rbp+50h] BYREF

  v2 = (char *)this + 680;
  v3 = (char *)this + 664;
  pvData = 0;
  v4 = CompatValueImpl("PresentFxOverride", &pvData, 0);
  v6 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl)
     ^ 1;
  if ( *((_BYTE *)this + 672) )
  {
    if ( !v4 )
    {
      v7 = (char *)this + 1064;
      goto LABEL_39;
    }
  }
  else if ( !v4 )
  {
    *(_QWORD *)v2 = 0;
    *(_QWORD *)v3 = 0x8000000000000000uLL;
    UserGlobalSettings = QueryUserGlobalSettings(13, RecordJournal, v3);
    if ( UserGlobalSettings < 0 )
      CModule::RecordJournalImpl(v10, UserGlobalSettings, "Unexpected failure for global settings.", v11);
    if ( *(_QWORD *)v3 == 0x8000000000000000uLL )
    {
      LODWORD(pvData) = 0;
      LODWORD(pcbData) = 4;
      if ( (int)QueryDirectXDatabaseConfig(5, 0, 0, 0, &pvData, &pcbData) >= 0 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
          v13 = (unsigned int)pvData >> 3;
        else
          LOBYTE(v13) = (unsigned __int8)pvData >> 2;
        v6 = v13 & 1;
      }
      *(_QWORD *)v3 = 0;
      DXGI_EFFECT_STATE::SetEffectTypeUserMode(v3, v12, v6);
    }
    *(_QWORD *)v2 = 0x8000000000000000uLL;
    FullPreferenceData = QueryFullPreferenceData(13, 0, 0, RecordJournal, v2, 8, 0);
    if ( FullPreferenceData < 0 )
      CModule::RecordJournalImpl(v15, FullPreferenceData, "Unexpected failure for per-app user settings.", v16);
    *((_BYTE *)this + 672) = 1;
    *((_BYTE *)this + 656) = 1;
    goto LABEL_19;
  }
  *((_BYTE *)this + 672) = 1;
  *(_QWORD *)v2 = pvData;
  *((_BYTE *)this + 685) |= 2u;
  *((_BYTE *)this + 688) = pvData | 3;
  if ( !CModule::IsPresentEffectsPackagePresent(this) )
  {
    *((_BYTE *)this + 700) = v8;
    *((_WORD *)this + 352) = 1337;
  }
LABEL_19:
  *(_QWORD *)((char *)this + 689) = 0;
  *(_WORD *)((char *)this + 697) = 0;
  *((_BYTE *)this + 699) = 0;
  *((_BYTE *)this + 690) = CompatValueOrDefault("PresentFx.BltWorkaround", 0, 0) != 0;
  *((_BYTE *)this + 691) = BinaryCompatValue<22>("PresentFx.AllowHybrid");
  *((_BYTE *)this + 692) = BinaryCompatValue<22>("PresentFx.CASOProxy");
  *((_BYTE *)this + 693) = BinaryCompatValue<21>("PresentFx.InternalDeviceList", v17, 0);
  LOBYTE(v18) = v4 != 0;
  *((_BYTE *)this + 694) = BinaryCompatValue<21>("PresentFx.AllowAnyAdapter", v19, v18);
  v20 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_SelfhostMode>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_SelfhostMode>::GetImpl'::`2'::impl) )
    v20 = (*(_DWORD *)CModule::GetEffectsConfig(this, &pvData) & 0x20) != 0;
  LOBYTE(v22) = v20;
  *((_BYTE *)this + 696) = BinaryCompatValue<21>("PresentFx.AllowAnyPowerState", v21, v22);
  LOBYTE(v23) = v20;
  *((_BYTE *)this + 697) = BinaryCompatValue<21>("PresentFx.AllowAnyDisplay", v24, v23);
  if ( !*((_BYTE *)this + 1028) )
  {
    LODWORD(pvData) = 4;
    v25 = QueryDirectXDatabaseConfig(7, 0, 0, 0, (char *)this + 1032, &pvData);
    v28 = (_DWORD *)((char *)this + 1032);
    if ( v25 < 0 )
    {
      *v28 = 0;
      CModule::RecordJournalImpl(v26, v25, "Failed to query effects device config", v27);
    }
    *((_BYTE *)this + 1028) = 1;
    pcbData = 0;
    if ( (unsigned int)CompatValueImpl("PresentFx.DeviceConfigOverride", &pcbData, 0) )
      *v28 = pcbData;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2601>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2601>::GetImpl'::`2'::impl) )
      *((_BYTE *)this + 689) = (*v28 & 0x80) != 0;
  }
  CModule::UpdateSystemPowerStatus(this);
  v7 = (char *)this + 1064;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
  {
    if ( (*v7 & 1) == 0 )
    {
      v29 = (*((_DWORD *)this + 258) & 0x10) != 0;
      hkey = 0;
      if ( (int)wil::reg::open_unique_key_nothrow(v5, 1, &hkey) >= 0 )
      {
        LODWORD(pvData) = 0;
        LODWORD(pcbData) = 4;
        ValueW = RegGetValueW(hkey, 0, L"ForceEnableResLimit", 0x10u, 0, &pvData, (LPDWORD)&pcbData);
        v33 = ValueW < 0;
        if ( ValueW > 0 )
          v33 = 1;
        if ( !v33 )
        {
          v29 = (_DWORD)pvData != 0;
          v34 = "Res limits enabled by registry";
          if ( !(_DWORD)pvData )
            v34 = "Res limits disabled by registry";
          CModule::RecordJournalImpl(v31, 0, v34, v32);
        }
      }
      *v7 = (2 * v29) | pvData & 0xFD | 1;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    }
  }
  else
  {
    *v7 = pvData & 0xFC | 1;
  }
LABEL_39:
  v35 = *((_DWORD *)v2 + 1);
  if ( v2[1] )
    v36 = v35 >> 13;
  else
    v36 = v35 >> 10;
  v37 = v36 & 1;
  if ( *((_WORD *)this + 311) )
    v37 = 1;
  *((_BYTE *)this + 577) = v37;
  if ( (*v7 & 2) != 0 )
    *((_BYTE *)this + 577) = v37 | CModule::CompatShimExists(v5, (const char *)1);
  if ( *((_BYTE *)this + 524) )
  {
    v38 = *((_BYTE *)this + 528) & 1;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl)
      && !v38
      && (*((_DWORD *)v2 + 1) & 0x200) == 0 )
    {
      v2[3] = 0;
      v2[1] = 0;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
    {
      v40 = v38
         && CModule::IsPresentEffectsPackagePresent(this)
         && !(unsigned __int8)CModule::IsPresentEffectsDisabledByPreference(v39, 2);
      v41 = 0;
      if ( (*((_BYTE *)this + 1032) & 2) == 0 )
        v41 = v40;
      *((_BYTE *)this + 695) = CompatValueOrDefault("PresentFx.AllowStartInPassthrough", v41, 0) != 0;
      v42 = *((_DWORD *)this + 258) >> 5;
      LOBYTE(v42) = (*((_DWORD *)this + 258) & 0x20) == 0;
      *((_BYTE *)this + 698) = BinaryCompatValue<21>("PresentFx.AllowCheckSupport", v43, v42);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_AllowForceCompose>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_AllowForceCompose>::GetImpl'::`2'::impl) )
        *((_BYTE *)this + 699) = CompatValueOrDefault(
                                   "PresentFx.ForceComposeDx11",
                                   ((unsigned __int64)*((unsigned int *)this + 258) >> 6) & 1,
                                   0) != 0;
    }
  }
  IsPresentEffectsPackagePresent = CModule::IsPresentEffectsPackagePresent(this);
  if ( (*v7 & 2) != 0 )
    IsPresentEffectsPackagePresent = 1;
  if ( (*((_BYTE *)this + 578) || g_DetourBehaviors) && !IsPresentEffectsPackagePresent )
  {
    CModule::RestoreOriginalMode(this);
    CModule::ClearResolutionFilterQuirks(v45);
    v46 = *(_QWORD *)v3;
    HIDWORD(pvData) = HIDWORD(*(_QWORD *)v3);
    pvData = __PAIR64__(HIDWORD(pvData), v46 & 0xFFFFFBF8 | 0x400) | 0x10000000000LL;
    v47 = WriteUserGlobalSetting(13, 0, &pvData, 8);
    v49 = (CModule *)(v47 + 0x80000000);
    if ( ((unsigned int)v49 & 0x80000000) == 0 && v47 != -2147024891 )
      CModule::RecordJournalImpl(v49, v47, "Failed to disable effects global setting", v48);
  }
  if ( CModule::IsPresentEffectsPackagePresent(this) && (*((_DWORD *)v3 + 1) & 0x100) != 0 )
  {
    pvData = *(_QWORD *)v3;
    DXGI_EFFECT_STATE::SetEffectTypeUserMode(&pvData, v50, v6 != 0);
    HIDWORD(pvData) &= ~0x100u;
    v51 = WriteUserGlobalSetting(13, 0, &pvData, 8);
    v53 = (CModule *)(v51 + 0x80000000);
    if ( ((unsigned int)v53 & 0x80000000) == 0 && v51 != -2147024891 )
      CModule::RecordJournalImpl(v53, v51, "Failed to restore effects global setting", v52);
  }
  CModule::InitPresentEffectsDeviceApplicability(this);
  CModule::ApplyResolutionFilterQuirks(this);
  LOBYTE(v54) = CModule::IsPresentEffectsEnabled(this, 2);
  byte_180108A71 = BinaryCompatValue<21>("HdrToSdrShimOverride", v55, v54);
}

```

## disassembly

```asm
0x1800650dc  mov     [rsp-38h+arg_18], rbx
0x1800650e1  push    rbp
0x1800650e2  push    rsi
0x1800650e3  push    rdi
0x1800650e4  push    r12
0x1800650e6  push    r13
0x1800650e8  push    r14
0x1800650ea  push    r15
0x1800650ec  mov     rbp, rsp
0x1800650ef  sub     rsp, 40h
0x1800650f3  mov     rbx, rcx
0x1800650f6  lea     r15, [rcx+2A8h]
0x1800650fd  lea     r12, [rcx+298h]
0x180065104  xor     r13d, r13d
0x180065107  mov     [rbp+arg_0], r13
0x18006510b  xor     r8d, r8d; bool
0x18006510e  lea     rdx, [rbp+arg_0]; unsigned __int64 *
0x180065112  lea     rcx, aPresentfxoverr; "PresentFxOverride"
0x180065119  call    ?CompatValueImpl@@YAHPEBDPEA_K_N@Z; CompatValueImpl(char const *,unsigned __int64 *,bool)
0x18006511e  mov     esi, eax
0x180065120  test    eax, eax
0x180065122  setnz   r14b
0x180065126  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x18006512d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x180065132  mov     dil, al
0x180065135  lea     edx, [r13+1]
0x180065139  xor     dil, dl
0x18006513c  cmp     [rbx+2A0h], r13b
0x180065143  jz      short loc_180065155
0x180065145  test    esi, esi
0x180065147  jnz     short loc_180065159
0x180065149  lea     r14, [rbx+428h]
0x180065150  jmp     loc_18006550D
0x180065155  test    esi, esi
0x180065157  jz      short loc_18006519C
0x180065159  mov     [rbx+2A0h], dl
0x18006515f  mov     rax, [rbp+arg_0]
0x180065163  mov     [r15], rax
0x180065166  or      byte ptr [rbx+2ADh], 2
0x18006516d  mov     al, byte ptr [rbp+arg_0]
0x180065170  or      al, 3
0x180065172  mov     [rbx+2B0h], al
0x180065178  mov     rcx, rbx; this
0x18006517b  call    ?IsPresentEffectsPackagePresent@CModule@@QEBA_NXZ; CModule::IsPresentEffectsPackagePresent(void)
0x180065180  test    al, al
0x180065182  jnz     loc_1800652AB
0x180065188  mov     [rbx+2BCh], dl
0x18006518e  mov     word ptr [rbx+2C0h], 539h
0x180065197  jmp     loc_1800652AB
0x18006519c  mov     [r15], r13
0x18006519f  mov     rsi, 8000000000000000h
0x1800651a9  mov     [r12], rsi
0x1800651ad  mov     r9d, 8
0x1800651b3  mov     r8, r12
0x1800651b6  lea     rdx, ?RecordJournal@@YAXIPEBD_N@Z; RecordJournal(uint,char const *,bool)
0x1800651bd  lea     ecx, [r9+5]
0x1800651c1  call    cs:__imp_QueryUserGlobalSettings
0x1800651c7  test    eax, eax
0x1800651c9  jns     short loc_1800651D9
0x1800651cb  lea     r8, aUnexpectedFail_5; "Unexpected failure for global settings."
0x1800651d2  mov     edx, eax; unsigned int
0x1800651d4  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800651d9  cmp     [r12], rsi
0x1800651dd  jnz     short loc_180065252
0x1800651df  mov     dword ptr [rbp+arg_0], r13d
0x1800651e3  mov     dword ptr [rbp+arg_8], 4
0x1800651ea  lea     rax, [rbp+arg_8]
0x1800651ee  mov     [rsp+40h+pvData], rax
0x1800651f3  lea     rax, [rbp+arg_0]
0x1800651f7  mov     [rsp+40h+pdwType], rax
0x1800651fc  xor     r9d, r9d
0x1800651ff  xor     r8d, r8d
0x180065202  xor     edx, edx
0x180065204  lea     ecx, [rdx+5]
0x180065207  call    cs:__imp_QueryDirectXDatabaseConfig
0x18006520d  test    eax, eax
0x18006520f  js      short loc_18006523B
0x180065211  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x180065218  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x18006521d  mov     esi, 1
0x180065222  test    al, al
0x180065224  jz      short loc_180065231
0x180065226  mov     edi, dword ptr [rbp+arg_0]
0x180065229  shr     edi, 3
0x18006522c  and     dil, sil
0x18006522f  jmp     short loc_180065240
0x180065231  mov     dil, byte ptr [rbp+arg_0]
0x180065235  shr     dil, 2
0x180065239  jmp     short loc_18006522C
0x18006523b  mov     esi, 1
0x180065240  mov     [r12], r13
0x180065244  movzx   r8d, dil
0x180065248  mov     rcx, r12
0x18006524b  call    ?SetEffectTypeUserMode@DXGI_EFFECT_STATE@@QEAAXEW4DXGI_EFFECT_MODE@@@Z; DXGI_EFFECT_STATE::SetEffectTypeUserMode(uchar,DXGI_EFFECT_MODE)
0x180065250  jmp     short loc_180065257
0x180065252  mov     esi, 1
0x180065257  mov     rax, 8000000000000000h
0x180065261  mov     [r15], rax
0x180065264  mov     [rsp+40h+pcbData], r13
0x180065269  mov     dword ptr [rsp+40h+pvData], 8
0x180065271  mov     [rsp+40h+pdwType], r15
0x180065276  lea     r9, ?RecordJournal@@YAXIPEBD_N@Z; RecordJournal(uint,char const *,bool)
0x18006527d  xor     r8d, r8d
0x180065280  xor     edx, edx
0x180065282  lea     ecx, [rdx+0Dh]
0x180065285  call    cs:__imp_QueryFullPreferenceData
0x18006528b  test    eax, eax
0x18006528d  jns     short loc_18006529D
0x18006528f  lea     r8, aUnexpectedFail_7; "Unexpected failure for per-app user set"...
0x180065296  mov     edx, eax; unsigned int
0x180065298  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18006529d  mov     [rbx+2A0h], sil
0x1800652a4  mov     [rbx+290h], sil
0x1800652ab  xor     eax, eax
0x1800652ad  mov     [rbx+2B1h], rax
0x1800652b4  mov     [rbx+2B9h], ax
0x1800652bb  mov     [rbx+2BBh], al
0x1800652c1  xor     r8d, r8d; bool
0x1800652c4  xor     edx, edx; unsigned __int64
0x1800652c6  lea     rcx, aPresentfxBltwo; "PresentFx.BltWorkaround"
0x1800652cd  call    ?CompatValueOrDefault@@YA_KPEBD_K_N@Z; CompatValueOrDefault(char const *,unsigned __int64,bool)
0x1800652d2  test    rax, rax
0x1800652d5  setnz   al
0x1800652d8  mov     [rbx+2B2h], al
0x1800652de  lea     rcx, aPresentfxAllow; "PresentFx.AllowHybrid"
0x1800652e5  call    ??$BinaryCompatValue@$0BG@@@YA_NAEAY0BG@$$CBD_N1@Z; BinaryCompatValue<22>(char const (&)[22],bool,bool)
0x1800652ea  mov     [rbx+2B3h], al
0x1800652f0  lea     rcx, aPresentfxCasop; "PresentFx.CASOProxy"
0x1800652f7  call    ??$BinaryCompatValue@$0BG@@@YA_NAEAY0BG@$$CBD_N1@Z; BinaryCompatValue<22>(char const (&)[22],bool,bool)
0x1800652fc  mov     [rbx+2B4h], al
0x180065302  xor     r8d, r8d
0x180065305  lea     rcx, aPresentfxInter; "PresentFx.InternalDeviceList"
0x18006530c  call    ??$BinaryCompatValue@$0BF@@@YA_NAEAY0BF@$$CBD_N1@Z; BinaryCompatValue<21>(char const (&)[21],bool,bool)
0x180065311  mov     [rbx+2B5h], al
0x180065317  mov     r8b, r14b
0x18006531a  lea     rcx, aPresentfxAllow_2; "PresentFx.AllowAnyAdapter"
0x180065321  call    ??$BinaryCompatValue@$0BF@@@YA_NAEAY0BF@$$CBD_N1@Z; BinaryCompatValue<21>(char const (&)[21],bool,bool)
0x180065326  mov     [rbx+2B6h], al
0x18006532c  mov     sil, r13b
0x18006532f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_SelfhostMode@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_SelfhostMode@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_SelfhostMode> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_SelfhostMode>::GetImpl(void)'::`2'::impl
0x180065336  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_SelfhostMode@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_SelfhostMode>::__private_IsEnabled(void)
0x18006533b  test    al, al
0x18006533d  jz      short loc_18006535B
0x18006533f  lea     rdx, [rbp+arg_0]
0x180065343  mov     rcx, rbx
0x180065346  call    ?GetEffectsConfig@CModule@@QEAA?AUDXGI_EFFECT_CONFIG@@XZ; CModule::GetEffectsConfig(void)
0x18006534b  mov     esi, [rax]
0x18006534d  shr     esi, 5
0x180065350  mov     r14d, 1
0x180065356  and     sil, r14b
0x180065359  jmp     short loc_180065361
0x18006535b  mov     r14d, 1
0x180065361  mov     r8b, sil
0x180065364  lea     rcx, aPresentfxAllow_3; "PresentFx.AllowAnyPowerState"
0x18006536b  call    ??$BinaryCompatValue@$0BF@@@YA_NAEAY0BF@$$CBD_N1@Z; BinaryCompatValue<21>(char const (&)[21],bool,bool)
0x180065370  mov     [rbx+2B8h], al
0x180065376  mov     r8b, sil
0x180065379  lea     rcx, aPresentfxAllow_1; "PresentFx.AllowAnyDisplay"
0x180065380  call    ??$BinaryCompatValue@$0BF@@@YA_NAEAY0BF@$$CBD_N1@Z; BinaryCompatValue<21>(char const (&)[21],bool,bool)
0x180065385  mov     [rbx+2B9h], al
0x18006538b  cmp     [rbx+404h], r13b
0x180065392  jnz     loc_180065426
0x180065398  mov     dword ptr [rbp+arg_0], 4
0x18006539f  lea     rax, [rbx+408h]
0x1800653a6  lea     rcx, [rbp+arg_0]
0x1800653aa  mov     [rsp+40h+pvData], rcx
0x1800653af  mov     [rsp+40h+pdwType], rax
0x1800653b4  xor     r9d, r9d
0x1800653b7  xor     r8d, r8d
0x1800653ba  xor     edx, edx
0x1800653bc  lea     ecx, [rdx+7]
0x1800653bf  call    cs:__imp_QueryDirectXDatabaseConfig
0x1800653c5  lea     rsi, [rbx+408h]
0x1800653cc  test    eax, eax
0x1800653ce  jns     short loc_1800653E1
0x1800653d0  mov     [rsi], r13d
0x1800653d3  lea     r8, aFailedToQueryE_0; "Failed to query effects device config"
0x1800653da  mov     edx, eax; unsigned int
0x1800653dc  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800653e1  mov     [rbx+404h], r14b
0x1800653e8  mov     [rbp+arg_8], r13
0x1800653ec  xor     r8d, r8d; bool
0x1800653ef  lea     rdx, [rbp+arg_8]; unsigned __int64 *
0x1800653f3  lea     rcx, aPresentfxDevic; "PresentFx.DeviceConfigOverride"
0x1800653fa  call    ?CompatValueImpl@@YAHPEBDPEA_K_N@Z; CompatValueImpl(char const *,unsigned __int64 *,bool)
0x1800653ff  test    eax, eax
0x180065401  jz      short loc_180065408
0x180065403  mov     eax, dword ptr [rbp+arg_8]
0x180065406  mov     [rsi], eax
0x180065408  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_2601@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2601@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2601> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_2601>::GetImpl(void)'::`2'::impl
0x18006540f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2601@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2601>::__private_IsEnabled(void)
0x180065414  test    al, al
0x180065416  jz      short loc_180065426
0x180065418  mov     eax, [rsi]
0x18006541a  shr     eax, 7
0x18006541d  and     al, r14b
0x180065420  mov     [rbx+2B1h], al
0x180065426  mov     rcx, rbx; this
0x180065429  call    ?UpdateSystemPowerStatus@CModule@@QEAAJXZ; CModule::UpdateSystemPowerStatus(void)
0x18006542e  lea     r14, [rbx+428h]
0x180065435  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x18006543c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x180065441  mov     edx, 1; char *
0x180065446  test    al, al
0x180065448  jz      loc_180065503
0x18006544e  test    [r14], dl
0x180065451  jnz     loc_18006550D
0x180065457  mov     esi, [rbx+408h]
0x18006545d  shr     esi, 4
0x180065460  and     sil, dl
0x180065463  mov     [rbp+hkey], r13
0x180065467  lea     r8, [rbp+hkey]
0x18006546b  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180065470  test    eax, eax
0x180065472  js      short loc_1800654E3
0x180065474  mov     dword ptr [rbp+arg_0], r13d
0x180065478  mov     dword ptr [rbp+arg_8], 4
0x18006547f  lea     rax, [rbp+arg_8]
0x180065483  mov     [rsp+40h+pcbData], rax; pcbData
0x180065488  lea     rax, [rbp+arg_0]
0x18006548c  mov     [rsp+40h+pvData], rax; pvData
0x180065491  mov     [rsp+40h+pdwType], r13; pdwType
0x180065496  mov     r9d, 10h; dwFlags
0x18006549c  lea     r8, aForceenableres; "ForceEnableResLimit"
0x1800654a3  xor     edx, edx; lpSubKey
0x1800654a5  mov     rcx, [rbp+hkey]; hkey
0x1800654a9  call    cs:__imp_RegGetValueW
0x1800654af  test    eax, eax
0x1800654b1  jle     short loc_1800654BD
0x1800654b3  movzx   eax, ax
0x1800654b6  or      eax, 80070000h
0x1800654bb  test    eax, eax
0x1800654bd  js      short loc_1800654E3
0x1800654bf  cmp     dword ptr [rbp+arg_0], r13d
0x1800654c3  setnz   sil
0x1800654c7  lea     rax, aResLimitsDisab; "Res limits disabled by registry"
0x1800654ce  lea     r8, aResLimitsEnabl; "Res limits enabled by registry"
0x1800654d5  test    sil, sil
0x1800654d8  cmovz   r8, rax; char *
0x1800654dc  xor     edx, edx; unsigned int
0x1800654de  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800654e3  mov     al, byte ptr [rbp+arg_0]
0x1800654e6  and     al, 0FDh
0x1800654e8  add     sil, sil
0x1800654eb  or      al, sil
0x1800654ee  or      al, 1
0x1800654f0  mov     [r14], al
0x1800654f3  lea     rcx, [rbp+hkey]
0x1800654f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800654fc  mov     edx, 1
0x180065501  jmp     short loc_18006550D
0x180065503  mov     al, byte ptr [rbp+arg_0]
0x180065506  and     al, 0FDh
0x180065508  or      al, dl
0x18006550a  mov     [r14], al
0x18006550d  mov     eax, [r15+4]
0x180065511  cmp     [r15+1], r13b
0x180065515  jz      short loc_18006551C
0x180065517  shr     eax, 0Dh
0x18006551a  jmp     short loc_18006551F
0x18006551c  shr     eax, 0Ah
0x18006551f  and     al, dl
0x180065521  movzx   esi, al
0x180065524  cmp     [rbx+26Eh], r13w
0x18006552c  cmovnz  esi, edx
0x18006552f  mov     [rbx+241h], sil
0x180065536  test    byte ptr [r14], 2
0x18006553a  jz      short loc_18006554F
0x18006553c  call    ?CompatShimExists@CModule@@AEAA_NPEBD@Z; CModule::CompatShimExists(char const *)
0x180065541  or      al, sil
0x180065544  mov     [rbx+241h], al
0x18006554a  mov     edx, 1
0x18006554f  cmp     [rbx+20Ch], r13b
0x180065556  jz      loc_180065657
0x18006555c  mov     sil, [rbx+210h]
0x180065563  and     sil, dl
0x180065566  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x18006556d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x180065572  test    al, al
0x180065574  jnz     short loc_18006558D
0x180065576  test    sil, sil
0x180065579  jnz     short loc_18006558D
0x18006557b  test    dword ptr [r15+4], 200h
0x180065583  jnz     short loc_18006558D
0x180065585  mov     [r15+3], r13b
0x180065589  mov     [r15+1], r13b
0x18006558d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x180065594  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x180065599  test    al, al
0x18006559b  jz      loc_180065657
0x1800655a1  test    sil, sil
0x1800655a4  jz      short loc_1800655C9
0x1800655a6  mov     rcx, rbx; this
0x1800655a9  call    ?IsPresentEffectsPackagePresent@CModule@@QEBA_NXZ; CModule::IsPresentEffectsPackagePresent(void)
0x1800655ae  test    al, al
0x1800655b0  jz      short loc_1800655C9
0x1800655b2  mov     edx, 2
0x1800655b7  call    ?IsPresentEffectsDisabledByPreference@CModule@@QEAA_NW4DXGI_EFFECT_TYPE@@@Z; CModule::IsPresentEffectsDisabledByPreference(DXGI_EFFECT_TYPE)
0x1800655bc  test    al, al
0x1800655be  jnz     short loc_1800655C9
  ... truncated ...
```
