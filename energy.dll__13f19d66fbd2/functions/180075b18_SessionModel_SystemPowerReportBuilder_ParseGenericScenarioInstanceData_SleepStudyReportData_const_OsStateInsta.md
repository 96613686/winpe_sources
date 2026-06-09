# SessionModel::SystemPowerReportBuilder::ParseGenericScenarioInstanceData(SleepStudyReportData const &,OsStateInstance const &,ScenarioSegment)

- ea: `0x180075b18`
- end: `0x180076fa1`
- name: `?ParseGenericScenarioInstanceData@SystemPowerReportBuilder@SessionModel@@AEAAXAEBUSleepStudyReportData@@AEBVOsStateInstance@@W4ScenarioSegment@@@Z`
- size: `5257`
- prototype: ``
- caller_count: `1`
- callee_count: `66`
- tags: `registry_config, service_task`

## callers

- `0x180075610`

## callees

- `0x18000486c`
- `0x18000b6f0`
- `0x180011990`
- `0x18001464c`
- `0x180014868`
- `0x180014e34`
- `0x1800182f4`
- `0x18001c8cc`
- `0x18001cf30`
- `0x18001f17c`
- `0x18001fcac`
- `0x180020208`
- `0x1800253e0`
- `0x18002ac08`
- `0x18002b644`
- `0x18002eca0`
- `0x180032110`
- `0x180034814`
- `0x180035934`
- `0x18003bb60`
- `0x18003bce0`
- `0x18003d470`
- `0x180043240`
- `0x180046884`
- `0x180047ab0`
- `0x180048710`
- `0x180048f68`
- `0x18004ca90`
- `0x1800584cc`
- `0x180064840`
- `0x180069f54`
- `0x180069f80`
- `0x180069fac`
- `0x180069fd8`
- `0x18006a040`
- `0x18006bc6c`
- `0x18006bca0`
- `0x18006c3cc`
- `0x18006ce68`
- `0x18006d604`
- `0x18006dac4`
- `0x18006e9a4`
- `0x18006ec10`
- `0x18006ed9c`
- `0x18006efd0`
- `0x18006f244`
- `0x18006f3b8`
- `0x18006f614`
- `0x18006f8cc`
- `0x180071bcc`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180076594`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180076594`

## string_xrefs

- `0x180076634`: `Instance Path`
- `0x1800765fc`: `Service Name`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall SessionModel::SystemPowerReportBuilder::ParseGenericScenarioInstanceData(
        unsigned int *a1,
        __int64 a2,
        __int64 a3,
        int a4)
{
  __int64 v4; // r12
  __int64 v8; // rsi
  __int64 *v9; // rcx
  __int64 *v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r14
  const struct CustomData **v14; // rbx
  const struct CustomData **v15; // rdi
  __int64 v16; // rax
  unsigned int v17; // edi
  unsigned int v18; // ebx
  __int64 SprSessionTransitionReasonString; // rax
  __int64 v20; // rax
  _DWORD *v21; // rax
  _DWORD *v22; // rdi
  __m128i si128; // xmm6
  SegmentData *v24; // rdi
  unsigned __int64 v25; // rdx
  SessionModel::SessionBuilder *v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  union _LARGE_INTEGER StartTime; // rax
  __int64 EntryBatteryFullCapacity; // rbx
  __int64 EntryBatteryRemainingCapacity; // rdx
  __int64 v36; // rax
  __int64 ExitBatteryFullCapacity; // rbx
  __int64 ExitBatteryRemainingCapacity; // rcx
  __int64 v39; // rax
  bool v40; // r9
  bool v41; // r8
  bool v42; // dl
  bool v43; // cl
  _BYTE *v44; // rax
  bool v45; // r9
  bool v46; // r8
  bool v47; // dl
  bool v48; // cl
  _BYTE *v49; // rax
  _QWORD *v50; // rax
  __int64 v51; // rbx
  SrumKey *v52; // rax
  _QWORD *v53; // rax
  __int64 v54; // rbx
  SrumKey *v55; // rax
  _QWORD *v56; // rax
  __int64 v57; // rbx
  SrumKey *v58; // rax
  _QWORD *v59; // rax
  __int64 v60; // rbx
  SrumKey *v61; // rax
  __int64 *v62; // rbx
  __int64 **v63; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  unsigned __int64 *v66; // r15
  unsigned __int64 *k; // rbx
  unsigned __int64 v68; // rdi
  const struct BlockerData **m; // rbx
  const struct BlockerData **v70; // rdi
  const struct FxDeviceData **v71; // rdi
  const struct FxDeviceData **n; // rbx
  const struct BlockerData **v73; // rdi
  const struct BlockerData **ii; // rbx
  unsigned int v75; // edi
  _QWORD *v76; // rbx
  _QWORD *v77; // rax
  _QWORD *v78; // rcx
  _QWORD *v79; // rcx
  _QWORD *v80; // rcx
  _QWORD *v81; // rcx
  struct _GUID *v82; // rdx
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // r13
  __int64 v86; // r12
  __int64 v87; // r15
  __int64 v88; // r14
  __int64 v89; // rsi
  __int64 v90; // rdi
  __int64 v91; // rbx
  int v92; // eax
  __int64 v93; // rbx
  __m128i *v94; // rbx
  __int64 v95; // rax
  __int64 v96; // rax
  struct _GUID **v97; // r15
  struct _GUID **v98; // rdi
  SessionModel::SystemPowerReportBuilder *v99; // rbx
  struct _GUID *v100; // r9
  __int64 v101; // rbx
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rax
  wchar_t *v105; // rcx
  __int64 v106; // rax
  _OWORD *v107; // rax
  __int64 v108; // rax
  __int64 v109; // r14
  int v110; // eax
  int v111; // r9d
  const struct DripsWakeSource *v112; // rbx
  const struct DripsWakeSource *v113; // r15
  DripsWakeSource *v114; // rdi
  __int64 v115; // r9
  __int64 v116; // r9
  __int64 v117; // rax
  SessionModel::SystemPowerReportBuilder *v118; // rcx
  __int64 v119; // rax
  const struct DripsBucket **v120; // rbx
  const struct DripsBucket **v121; // rdi
  DripsBucket *v122; // rax
  __int64 v123; // rbx
  __int64 *v124; // rbx
  _QWORD *v125; // rdi
  _QWORD *v126; // rsi
  __int64 v127; // rax
  __int64 v128; // rax
  __int64 **v129; // rcx
  __int64 *jj; // rax
  __int64 *kk; // rcx
  int v132; // [rsp+28h] [rbp-150h]
  __int64 v133; // [rsp+30h] [rbp-148h]
  int v134; // [rsp+38h] [rbp-140h]
  __int64 v135; // [rsp+38h] [rbp-140h]
  __int64 v136; // [rsp+40h] [rbp-138h]
  int v137; // [rsp+48h] [rbp-130h]
  __int64 v138; // [rsp+50h] [rbp-128h]
  int v139; // [rsp+58h] [rbp-120h]
  __int64 v140; // [rsp+60h] [rbp-118h]
  int v141; // [rsp+68h] [rbp-110h]
  __int64 v142; // [rsp+70h] [rbp-108h]
  int v143; // [rsp+78h] [rbp-100h]
  __int64 v144; // [rsp+80h] [rbp-F8h]
  int v145; // [rsp+88h] [rbp-F0h]
  __int64 v146; // [rsp+90h] [rbp-E8h]
  int v147; // [rsp+98h] [rbp-E0h]
  __int64 v148; // [rsp+A0h] [rbp-D8h]
  bool v149; // [rsp+F8h] [rbp-80h] BYREF
  bool v150; // [rsp+F9h] [rbp-7Fh] BYREF
  _BYTE v151[6]; // [rsp+FAh] [rbp-7Eh] BYREF
  unsigned __int64 v152; // [rsp+100h] [rbp-78h] BYREF
  int v153; // [rsp+108h] [rbp-70h] BYREF
  SessionModel::SystemPowerReportBuilder *v154; // [rsp+110h] [rbp-68h] BYREF
  GUID v155; // [rsp+118h] [rbp-60h] BYREF
  int v156; // [rsp+128h] [rbp-50h]
  __int128 *v157; // [rsp+130h] [rbp-48h] BYREF
  __int64 v158; // [rsp+138h] [rbp-40h]
  __int128 v159; // [rsp+140h] [rbp-38h] BYREF
  __m128i v160; // [rsp+150h] [rbp-28h]
  __int128 v161; // [rsp+160h] [rbp-18h] BYREF
  __int64 v162; // [rsp+170h] [rbp-8h]
  char v163[32]; // [rsp+178h] [rbp+0h] BYREF
  _BYTE v164[80]; // [rsp+198h] [rbp+20h] BYREF
  char v165[8]; // [rsp+1E8h] [rbp+70h] BYREF
  _BYTE v166[112]; // [rsp+1F0h] [rbp+78h] BYREF
  unsigned int v167; // [rsp+260h] [rbp+E8h]
  struct _GUID v168; // [rsp+2D8h] [rbp+160h] BYREF
  __int64 v169; // [rsp+2E8h] [rbp+170h]
  unsigned __int64 v170; // [rsp+2F0h] [rbp+178h]
  DripsBucket *v171[2]; // [rsp+2F8h] [rbp+180h] BYREF
  __m128i v172; // [rsp+308h] [rbp+190h]
  struct _GUID v173; // [rsp+318h] [rbp+1A0h] BYREF
  _QWORD v174[2]; // [rsp+328h] [rbp+1B0h] BYREF
  __m128i v175; // [rsp+338h] [rbp+1C0h]
  __int128 v176; // [rsp+360h] [rbp+1E8h] BYREF
  __m128i v177; // [rsp+370h] [rbp+1F8h]
  __int128 Src; // [rsp+380h] [rbp+208h] BYREF
  __m128i v179; // [rsp+390h] [rbp+218h]
  _BYTE v180[32]; // [rsp+3A0h] [rbp+228h] BYREF
  _BYTE v181[32]; // [rsp+3C0h] [rbp+248h] BYREF
  _BYTE v182[32]; // [rsp+3E0h] [rbp+268h] BYREF
  _BYTE v183[32]; // [rsp+400h] [rbp+288h] BYREF
  _BYTE v184[32]; // [rsp+420h] [rbp+2A8h] BYREF
  _BYTE v185[32]; // [rsp+440h] [rbp+2C8h] BYREF

  v4 = a4;
  v156 = a4;
  v154 = (SessionModel::SystemPowerReportBuilder *)a1;
  std::wstring::wstring(&Src);
  std::wstring::wstring(&v176);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v165);
  v8 = 0;
  v158 = 0;
  v9 = *(__int64 **)(a2 + 328);
  v10 = *(__int64 **)(a2 + 336);
  if ( v9 != v10 )
  {
    while ( *(_QWORD *)(*v9 + 184) != *(_QWORD *)(a3 + 168) || *(_DWORD *)(*v9 + 192) != *(_DWORD *)(a3 + 176) )
    {
      if ( ++v9 == v10 )
        goto LABEL_7;
    }
    v8 = *v9;
    v158 = *v9;
  }
LABEL_7:
  if ( !(_DWORD)v4 && v8 )
  {
    if ( SegmentData::GetDurationInUs((SegmentData *)(v8 + 1448)) < a1[12] )
      v8 = 0;
    v158 = v8;
  }
  v11 = *(_QWORD *)(a3 + 168);
  *(_QWORD *)&v168.Data1 = *(unsigned int *)(a3 + 176);
  if ( (_DWORD)v4 )
  {
    *(_QWORD *)v168.Data4 = v11;
    v12 = SessionModel::SystemPowerReportBuilder::CreateModernSleepSession(a1, &v168);
  }
  else
  {
    *(_QWORD *)v168.Data4 = v11 - 1;
    v12 = SessionModel::SystemPowerReportBuilder::CreateScreenOffSession(a1, &v168);
  }
  v13 = v12;
  v157 = (__int128 *)v12;
  v14 = *(const struct CustomData ***)(a3 + 208);
  v15 = *(const struct CustomData ***)(a3 + 216);
  while ( v14 != v15 )
  {
    v16 = SessionModel::Metadata::Metadata((SessionModel::Metadata *)&v173, *v14);
    v168 = GUID_SPR_SESSION_METADATA_CONTAINER;
    SessionModel::SessionBuilder::AddMetadata(v13, &v168, v16);
    ++v14;
  }
  if ( !*(_BYTE *)(a3 + 20) )
    *(_DWORD *)(*(_QWORD *)(v13 + 8) + 176LL) = 4;
  if ( (_DWORD)v4 )
  {
    v17 = 257;
  }
  else
  {
    v17 = *(_DWORD *)(a3 + 36);
    if ( *(_BYTE *)(a3 + 232) )
    {
      v18 = 257;
      goto LABEL_25;
    }
  }
  v18 = *(_DWORD *)(a3 + 108);
LABEL_25:
  SprSessionTransitionReasonString = GetSprSessionTransitionReasonString(v17);
  std::wstring::assign(&Src, SprSessionTransitionReasonString);
  v20 = GetSprSessionTransitionReasonString(v18);
  std::wstring::assign(&v176, v20);
  if ( v8 )
  {
    v21 = *(_DWORD **)(v8 + 1304);
    v152 = (unsigned __int64)v21;
    if ( v21 && *v21 == v17 )
    {
      std::wstring::_Append<unsigned short>(&Src);
      std::wstring::_Append<unsigned short>(&Src);
    }
    v22 = *(_DWORD **)(v8 + 1312);
    if ( v22 && *v22 == v18 )
    {
      std::wstring::_Append<unsigned short>(&v176);
      std::wstring::_Append<unsigned short>(&v176);
    }
  }
  v159 = Src;
  v160 = v179;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v179 = si128;
  LOWORD(Src) = 0;
  SessionModel::SessionBuilder::SetEntryReason(v13, &v159);
  v159 = v176;
  v160 = v177;
  v177 = si128;
  LOWORD(v176) = 0;
  SessionModel::SessionBuilder::SetExitReason(v13, &v159);
  *(_BYTE *)(*(_QWORD *)(v13 + 8) + 224LL) = *(_DWORD *)(a3 + 188) != 0;
  *(_BYTE *)(*(_QWORD *)(v13 + 8) + 225LL) = *(_BYTE *)(a3 + 192) != 0;
  if ( v8 )
  {
    v24 = (SegmentData *)(v8 + (v4 << 7) + 1448);
    SegmentData::GetStartTime(v24);
    SessionModel::SessionBuilder::SetEntryTimeInUs((SessionModel::SessionBuilder *)v13, v152 / 0xA, 1);
    v25 = v152 / 0xA + SegmentData::GetDurationInUs(v24);
LABEL_37:
    SessionModel::SessionBuilder::SetExitTimeInUs((SessionModel::SessionBuilder *)v13, v25, 1);
    EntryBatteryFullCapacity = SegmentData::GetEntryBatteryFullCapacity(v24);
    EntryBatteryRemainingCapacity = SegmentData::GetEntryBatteryRemainingCapacity(v24);
    *(_QWORD *)(v13 + 16) |= 4uLL;
    v36 = *(_QWORD *)(v13 + 8);
    *(_QWORD *)(v36 + 184) = EntryBatteryFullCapacity;
    *(_QWORD *)(v36 + 192) = EntryBatteryRemainingCapacity;
    ExitBatteryFullCapacity = SegmentData::GetExitBatteryFullCapacity(v24);
    ExitBatteryRemainingCapacity = SegmentData::GetExitBatteryRemainingCapacity(v24);
    *(_QWORD *)(v13 + 16) |= 0x20uLL;
    v39 = *(_QWORD *)(v13 + 8);
    *(_QWORD *)(v39 + 200) = ExitBatteryFullCapacity;
    *(_QWORD *)(v39 + 208) = ExitBatteryRemainingCapacity;
    goto LABEL_38;
  }
  if ( *(_DWORD *)(a3 + 16) != 12 )
  {
    v24 = (SegmentData *)(a3 + 120 * (v4 + 2));
    StartTime = SegmentData::GetStartTime(v24);
    SessionModel::SessionBuilder::SetEntryTimeInUs(
      (SessionModel::SessionBuilder *)v13,
      *(_QWORD *)StartTime.QuadPart / 0xAuLL,
      1);
    v25 = *(_QWORD *)SegmentData::GetExitTime(v24).QuadPart / 0xAuLL;
    goto LABEL_37;
  }
  SessionModel::SessionBuilder::SetEntryTimeInUs(
    (SessionModel::SessionBuilder *)v13,
    *(_QWORD *)(a3 + 24) / 0xAuLL,
    *(_BYTE *)(a3 + 32) != 0);
  SessionModel::SessionBuilder::SetExitTimeInUs(v26, *(_QWORD *)(a3 + 96) / 0xAuLL, *(_BYTE *)(a3 + 104) != 0);
  v27 = *(unsigned int *)(a3 + 88);
  v28 = *(unsigned int *)(a3 + 84);
  *(_QWORD *)(v13 + 16) |= 4uLL;
  v29 = *(_QWORD *)(v13 + 8);
  *(_QWORD *)(v29 + 184) = v27;
  *(_QWORD *)(v29 + 192) = v28;
  v30 = *(unsigned int *)(a3 + 160);
  v31 = *(unsigned int *)(a3 + 156);
  *(_QWORD *)(v13 + 16) |= 0x20uLL;
  v32 = *(_QWORD *)(v13 + 8);
  *(_QWORD *)(v32 + 200) = v30;
  *(_QWORD *)(v32 + 208) = v31;
LABEL_38:
  v40 = *(_BYTE *)(a3 + 193) != 0;
  v41 = *(_BYTE *)(a3 + 194) != 0;
  v42 = *(_BYTE *)(a3 + 195) != 0;
  v43 = *(_BYTE *)(a3 + 196) != 0;
  *(_QWORD *)(v13 + 16) |= 0x40uLL;
  v44 = *(_BYTE **)(v13 + 8);
  v44[216] = v40;
  v44[217] = v41;
  v44[218] = v42;
  v44[219] = v43;
  v45 = *(_BYTE *)(a3 + 197) != 0;
  v46 = *(_BYTE *)(a3 + 198) != 0;
  v47 = *(_BYTE *)(a3 + 199) != 0;
  v48 = *(_BYTE *)(a3 + 200) != 0;
  *(_QWORD *)(v13 + 16) |= 0x80uLL;
  v49 = *(_BYTE **)(v13 + 8);
  v49[220] = v45;
  v49[221] = v46;
  v49[222] = v47;
  v49[223] = v48;
  if ( v8 && (_DWORD)v4 == 1 )
  {
    v50 = **(_QWORD ***)(v8 + 1240);
    v152 = (unsigned __int64)v50;
    while ( !*((_BYTE *)v50 + 25) )
    {
      v51 = v50[10];
      v52 = SrumKey::SrumKey((SrumKey *)&v173, (const struct SrumKey *)(v50 + 4));
      SessionModel::SessionBuilder::AddEnergyEstimationRecord(v13, v52, v51);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<SrumKey const,EnergyEstimationInfo *>>>,std::_Iterator_base0>::operator++(&v152);
      v50 = (_QWORD *)v152;
    }
    v53 = **(_QWORD ***)(v8 + 1224);
    v152 = (unsigned __int64)v53;
    while ( !*((_BYTE *)v53 + 25) )
    {
      v54 = v53[10];
      v55 = SrumKey::SrumKey((SrumKey *)&v173, (const struct SrumKey *)(v53 + 4));
      SessionModel::SessionBuilder::AddEnergyEstimationRecord(v13, v55, v54);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<SrumKey const,EnergyEstimationInfo *>>>,std::_Iterator_base0>::operator++(&v152);
      v53 = (_QWORD *)v152;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SrumDataForScreenoffSleepStudy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SrumDataForScreenoffSleepStudy>::GetImpl'::`2'::impl) )
  {
    if ( !v8 )
      goto LABEL_114;
    if ( !(_DWORD)v4 )
    {
      v56 = **(_QWORD ***)(v8 + 1280);
      v152 = (unsigned __int64)v56;
      while ( !*((_BYTE *)v56 + 25) )
      {
        v57 = v56[10];
        v58 = SrumKey::SrumKey((SrumKey *)&v173, (const struct SrumKey *)(v56 + 4));
        SessionModel::SessionBuilder::AddEnergyEstimationRecord(v13, v58, v57);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<SrumKey const,EnergyEstimationInfo *>>>,std::_Iterator_base0>::operator++(&v152);
        v56 = (_QWORD *)v152;
      }
      v59 = **(_QWORD ***)(v8 + 1264);
      v152 = (unsigned __int64)v59;
      while ( !*((_BYTE *)v59 + 25) )
      {
        v60 = v59[10];
        v61 = SrumKey::SrumKey((SrumKey *)&v173, (const struct SrumKey *)(v59 + 4));
        SessionModel::SessionBuilder::AddEnergyEstimationRecord(v13, v61, v60);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<SrumKey const,EnergyEstimationInfo *>>>,std::_Iterator_base0>::operator++(&v152);
        v59 = (_QWORD *)v152;
      }
    }
  }
  if ( v8 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SleepStudySubSystemAPI>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SleepStudySubSystemAPI>::GetImpl'::`2'::impl) )
    {
      v62 = **(__int64 ***)(v8 + 16 * (v4 + 30));
      while ( !*((_BYTE *)v62 + 25) )
      {
        v173 = (struct _GUID)*((_OWORD *)v62 + 2);
        std::wstring::wstring((__int64)v174, v62 + 6);
        v171[0] = (DripsBucket *)v174[0];
        v171[1] = (DripsBucket *)v174[1];
        v172 = v175;
        v175 = si128;
        LOWORD(v174[0]) = 0;
        v168 = v173;
        SessionModel::SessionBuilder::AddSessionBlockerGroup(v13, &v168, v171);
        std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v174);
        v63 = (__int64 **)v62[2];
        if ( *((_BYTE *)v63 + 25) )
        {
          for ( i = (__int64 *)v62[1]; !*((_BYTE *)i + 25) && v62 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v62 = i;
          v62 = i;
        }
        else
        {
          v62 = (__int64 *)v62[2];
          for ( j = *v63; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v62 = j;
        }
      }
    }
    v159 = 0;
    v160.m128i_i64[0] = 0;
    v66 = *(unsigned __int64 **)(v8 + 296);
    for ( k = *(unsigned __int64 **)(v8 + 288); k != v66; ++k )
    {
      v68 = *k;
      v152 = v68;
      if ( (unsigned int)BlockerData::GetSegment(v68) == (_DWORD)v4 && *(_DWORD *)(v68 + 576) != 8 )
      {
        if ( *((_QWORD *)&v159 + 1) == v160.m128i_i64[0] )
        {
          std::vector<CustomDatum *>::_Emplace_reallocate<CustomDatum * const &>(&v159, *((_QWORD *)&v159 + 1), &v152);
        }
        else
        {
          **((_QWORD **)&v159 + 1) = v68;
          *((_QWORD *)&v159 + 1) += 8LL;
        }
      }
    }
    v70 = (const struct BlockerData **)*((_QWORD *)&v159 + 1);
    for ( m = (const struct BlockerData **)v159; m != v70; ++m )
    {
      v168 = GUID_SPR_BLOCKER_GROUP_PDC_PHASES;
      SessionModel::SystemPowerReportBuilder::ParseBlocker(
        (SessionModel::SystemPowerReportBuilder *)a1,
        (struct SessionModel::SessionBuilder *)v13,
        &v168,
        *m);
    }
    if ( (_DWORD)v4 == 1 )
    {
      v168 = GUID_SPR_BLOCKER_GROUP_ACTIVATORS;
      SessionModel::SystemPowerReportBuilder::ParseBlockerGroup<ScenarioBlockerData>(
        (SessionModel::SystemPowerReportBuilder *)a1,
        (struct SessionModel::SessionBuilder *)v13,
        &v168,
        (const struct BlockerData ***)(v8 + 336));
      v71 = *(const struct FxDeviceData ***)(v8 + 520);
      for ( n = *(const struct FxDeviceData ***)(v8 + 512); n != v71; ++n )
      {
        v168 = GUID_SPR_BLOCKER_GROUP_FX_DEVICES;
        SessionModel::SystemPowerReportBuilder::ParseBlocker(
          (SessionModel::SystemPowerReportBuilder *)a1,
          (struct SessionModel::SessionBuilder *)v13,
          &v168,
          *n);
      }
      v73 = *(const struct BlockerData ***)(v8 + 320);
      for ( ii = *(const struct BlockerData ***)(v8 + 312); ii != v73; ++ii )
      {
        v168 = GUID_SPR_BLOCKER_GROUP_PROCESSORS;
        SessionModel::SystemPowerReportBuilder::ParseBlocker(
          (SessionModel::SystemPowerReportBuilder *)a1,
          (struct SessionModel::SessionBuilder *)v13,
          &v168,
          *ii);
      }
      v168 = GUID_SPR_BLOCKER_GROUP_PEP_PRE_VETOES;
      SessionModel::SystemPowerReportBuilder::ParseBlockerGroup<ScenarioBlockerData>(
        (SessionModel::SystemPowerReportBuilder *)a1,
        (struct SessionModel::SessionBuilder *)v13,
        &v168,
        (const struct BlockerData ***)(v8 + 384));
      v168 = GUID_SPR_BLOCKER_GROUP_SOC_SUBSYSTEMS;
      SessionModel::SystemPowerReportBuilder::ParseBlockerGroup<ScenarioBlockerData>(
        (SessionModel::SystemPowerReportBuilder *)a1,
        (struct SessionModel::SessionBuilder *)v13,
        &v168,
        (const struct BlockerData ***)(v8 + 408));
      v75 = 0;
      v153 = 0;
      v76 = *(_QWORD **)(v8 + 360);
      v152 = (unsigned __int64)v76;
      *(_QWORD *)&v155.Data1 = *(_QWORD *)(v8 + 368);
      if ( v76 != *(_QWORD **)&v155.Data1 )
      {
        do
        {
          v77 = (_QWORD *)*v76;
          if ( !*(_BYTE *)(*v76 + 757LL) )
          {
            v78 = v77 + 1;
            if ( v77[4] > 7u )
              v78 = (_QWORD *)*v78;
            if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                     v78,
                                     v77[3],
                                     &qword_18009CA18,
                                     0) )
            {
              v79 = (_QWORD *)(*v76 + 600LL);
              if ( *(_QWORD *)(*v76 + 624LL) > 7u )
                v79 = (_QWORD *)*v79;
              if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                       v79,
                                       *(_QWORD *)(*v76 + 616LL),
                                       &qword_18009CA18,
                                       0) )
              {
                v80 = (_QWORD *)(*v76 + 632LL);
                if ( *(_QWORD *)(*v76 + 656LL) > 7u )
                  v80 = (_QWORD *)*v80;
                if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                         v80,
                                         *(_QWORD *)(*v76 + 648LL),
                                         &qword_18009CA18,
                                         0) )
                {
                  v81 = (_QWORD *)(*v76 + 664LL);
                  if ( *(_QWORD *)(*v76 + 688LL) > 7u )
                    v81 = (_QWORD *)*v81;
                  if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                           v81,
                                           *(_QWORD *)(*v76 + 680LL),
                                           &qword_18009CA18,
                                           0) )
                  {
                    std::wstring::wstring((__int64)&v168, (__int64)&qword_18009CA18);
                    std::basic_stringbuf<unsigned short>::_Tidy(v166);
                    v82 = &v168;
                    if ( v170 > 7 )
                      v82 = *(struct _GUID **)&v168.Data1;
                    std::basic_stringbuf<unsigned short>::_Init(v166, v82, v169, v167);
                    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v168);
                    v83 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                            (__int64)v165,
                            (__int64)L"RegisteredDevices.");
                    v84 = std::basic_ostream<unsigned short>::operator<<(v83, v75);
                    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v84, (__int64)L".");
                    v85 = *v76 + 664LL;
                    std::basic_stringbuf<unsigned short>::str(v166, v180);
                    v86 = std::operator+<unsigned short>(&v173, v180, L"Unique ID");
                    v87 = *v76 + 632LL;
                    std::basic_stringbuf<unsigned short>::str(v166, v183);
                    v88 = std::operator+<unsigned short>(v185, v183, L"Service Name");
                    v89 = *v76 + 600LL;
                    std::basic_stringbuf<unsigned short>::str(v166, v182);
                    v90 = std::operator+<unsigned short>(v184, v182, L"Instance Path");
                    v91 = *v76;
                    std::basic_stringbuf<unsigned short>::str(v166, v181);
                    v92 = std::operator+<unsigned short>(v163, v181, L"_Header");
                    v168 = GUID_SPR_BLOCKER_GROUP_FX_DEVICES;
                    v135 = v88;
                    v13 = (__int64)v157;
                    SessionModel::SessionBuilder::AddMetadataValues<std::wstring &,std::wstring,std::wstring &,std::wstring,std::wstring &,std::wstring,std::wstring &>(
                      (_DWORD)v157,
                      (unsigned int)&v168,
                      v92,
                      v91 + 8,
                      v90,
                      v89,
                      v135,
                      v87,
                      v86,
                      v85);
                    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v181);
                    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v184);
                    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v182);
                    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v185);
                    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v183);
                    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v173);
                    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v180);
                    v76 = (_QWORD *)v152;
                    if ( *(_BYTE *)(*(_QWORD *)v152 + 757LL) )
                    {
                      v149 = 1;
                      *(_QWORD *)&v168.Data1 = &v173;
                      std::basic_stringbuf<unsigned short>::str(v166, v180);
                      v93 = std::operator+<unsigned short>(&v173, v180, L"Mocked Device");
                      v168 = *(struct _GUID *)(*(__int64 (__fastcall **)(_QWORD, DripsBucket **))(**(_QWORD **)v152
                                                                                                + 48LL))(
                                                *(_QWORD *)v152,
                                                v171);
                      SessionModel::SessionBuilder::AddMetadata<bool>(v13, &v168, v93);
                      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v180);
                      v76 = (_QWORD *)v152;
                    }
                    v75 = ++v153;
                  }
                }
              }
            }
          }
          v152 = (unsigned __int64)++v76;
        }
        while ( v76 != *(_QWORD **)&v155.Data1 );
        if ( v75 )
        {
          v94 = (__m128i *)std::wstring::wstring((__int64)&v173, (__int64)L"RegisteredDevices._Header");
          *(_QWORD *)&v168.Data1 = v94;
          *(__m128i *)v171 = *v94;
          v172 = v94[1];
          v94[1].m128i_i64[0] = 0;
          v94[1].m128i_i64[1] = 7;
          v94->m128i_i16[0] = 0;
          v95 = SessionModel::Metadata::Metadata(v164, v171, L"Registered Devices");
          v155 = GUID_SPR_BLOCKER_GROUP_FX_DEVICES;
          SessionModel::SessionBuilder::AddMetadata(v13, &v155, v95);
          std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v94);
        }
        LODWORD(v4) = v156;
        v8 = v158;
      }
    }
    v96 = (int)v4 + 18LL;
    v97 = *(struct _GUID ***)(v8 + 24 * v96 + 8);
    v98 = *(struct _GUID ***)(v8 + 24 * v96);
    if ( v98 != v97 )
    {
      v99 = v154;
      do
      {
        v100 = *v98;
        v168 = (*v98)[37];
        SessionModel::SystemPowerReportBuilder::ParseBlocker(
          v99,
          (struct SessionModel::SessionBuilder *)v13,
          &v168,
          (const struct BlockerData *)v100);
        ++v98;
      }
      while ( v98 != v97 );
    }
    if ( (_QWORD)v159 )
      std::_Deallocate<16>((void *)v159, (v160.m128i_i64[0] - v159) & 0xFFFFFFFFFFFFFFF8uLL);
  }
LABEL_114:
  v101 = *(_QWORD *)(v13 + 8);
  v102 = std::wstring::wstring((__int64)&v173, (__int64)L"Info.EnterReason");
  v168 = GUID_SPR_SESSION_METADATA_CONTAINER;
  SessionModel::SessionBuilder::AddMetadataValues<std::wstring const &,unsigned short const (&)[16],std::wstring const &>(
    v13,
    &v168,
    v102,
    v101 + 232);
  if ( !v8 )
    goto LABEL_160;
  *(_BYTE *)(v13 + 24) = 1;
  v149 = *(_BYTE *)(v8 + 244) != 0;
  v150 = *(_BYTE *)(v8 + 129) != 0;
  v103 = std::wstring::wstring((__int64)&v173, (__int64)L"Settings.EnergySaverInStandby");
  v168 = GUID_SPR_SESSION_METADATA_CONTAINER;
  SessionModel::SessionBuilder::AddMetadataValues<bool,unsigned short const (&)[27],bool>(v13, &v168, v103, &v150);
  if ( (_DWORD)v4 )
  {
    v153 = *(unsigned __int8 *)(v8 + 272);
    LODWORD(v152) = *(unsigned __int8 *)(v8 + 156);
    v150 = *(_BYTE *)(v8 + 122) != 0;
    v149 = *(_BYTE *)(v8 + 121) != 0;
    v151[0] = *(_BYTE *)(v8 + 120) == 0;
    v107 = (_OWORD *)std::wstring::wstring((__int64)&v173, (__int64)L"Settings.ConnectedStandby");
    v168 = GUID_SPR_SESSION_METADATA_CONTAINER;
    SessionModel::SessionBuilder::AddMetadataValues<bool,unsigned short const (&)[25],bool,unsigned short const (&)[30],bool,unsigned short const (&)[32],unsigned long const &,unsigned short const (&)[23],unsigned long const &,unsigned short const (&)[27],unsigned long,unsigned short const (&)[34],unsigned long const &,unsigned short const (&)[24],unsigned long,unsigned short const (&)[39],unsigned long const &>(
      v13,
      (__int128 *)&v168,
      v107,
      (__int64)v151,
      v132,
      (__int64)&v149,
      v134,
      (__int64)&v150,
      v137,
      v8 + 124,
      v139,
      v8 + 276,
      v141,
      (__int64)&v152,
      v143,
      v8 + 240,
      v145,
      (__int64)&v153,
      v147,
      v8 + 260);
  }
  else
  {
    v104 = *(unsigned int *)(v8 + 152);
    if ( (unsigned int)v104 >= 6 )
      v105 = (wchar_t *)L"Unknown";
    else
      v105 = off_180097AA0[v104];
    v154 = (SessionModel::SystemPowerReportBuilder *)v105;
    v150 = *(_BYTE *)(v8 + 144) != 0;
    v106 = std::wstring::wstring((__int64)&v173, (__int64)L"Settings.IsLockConsoleTimeoutActive");
    v168 = GUID_SPR_SESSION_METADATA_CONTAINER;
    SessionModel::SessionBuilder::AddMetadataValues<bool,unsigned short const (&)[31],unsigned long const &,unsigned short const (&)[37],unsigned long const &,unsigned short const (&)[33],unsigned long const &,unsigned short const (&)[40],unsigned long const &,unsigned short const (&)[27],unsigned short const * &>(
      v13,
      &v168,
      v106,
      &v150);
  }
  v151[0] = *(_BYTE *)(v8 + 245) != 0;
  v108 = std::wstring::wstring((__int64)&v173, (__int64)L"Settings.Hibernate.IsHibernateEnabled");
  v168 = GUID_SPR_SESSION_METADATA_CONTAINER;
  SessionModel::SessionBuilder::AddMetadataValues<bool,unsigned short const (&)[45],unsigned long const &>(
    v13,
    &v168,
    v108,
    v151);
  if ( !*(_QWORD *)(v8 + 1296) )
    goto LABEL_125;
  if ( !ScenarioInstanceData::IsSleepPresent((ScenarioInstanceData *)v8) || (_DWORD)v4 == 1 )
  {
    v109 = *(_QWORD *)(v8 + 1296);
    *(_QWORD *)&v155.Data1 = v109 + 56;
    v154 = (SessionModel::SystemPowerReportBuilder *)(*(unsigned int *)(v109 + 44)
                                                    - *(_QWORD *)(v109 + 72)
                                                    - *(_QWORD *)(v109 + 64)
                                                    - *(_QWORD *)(v109 + 56));
    v110 = std::wstring::wstring((__int64)&v173, (__int64)L"MSExitPerformance.TotalInMs");
    v168 = GUID_SPR_SESSION_METADATA_CONTAINER;
    v111 = v109 + 80;
    v148 = v109 + 36;
    v146 = v109 + 32;
    v144 = v109 + 28;
    v142 = v109 + 40;
    v140 = v109 + 24;
    v138 = v109 + 20;
    v136 = v109 + 16;
    v133 = v109 + 12;
    v13 = (__int64)v157;
    SessionModel::SessionBuilder::AddMetadataValues<unsigned long &,unsigned short const (&)[37],unsigned long &,unsigned short const (&)[43],unsigned long &,unsigned short const (&)[30],unsigned long &,unsigned short const (&)[30],unsigned long &,unsigned short const (&)[38],unsigned long &,unsigned short const (&)[30],unsigned long &,unsigned short const (&)[32],unsigned long &,unsigned short const (&)[37],unsigned long &,unsigned short const (&)[35],unsigned long &,unsigned short const (&)[28],unsigned __int64 &,unsigned short const (&)[35],unsigned __int64 &,unsigned short const (&)[37],unsigned __int64 &,unsigned short const (&)[35],unsigned __int64 &>(
      (_DWORD)v157,
      (unsigned int)&v168,
      v110,
      v111,
      v132,
      v133,
      v134,
      v136,
      v137,
      v138,
      v139,
      v140,
      v141,
      v142,
      v143,
      v144,
      v145,
      v146,
      v147,
      v148);
    v8 = v158;
    LODWORD(v4) = v156;
LABEL_125:
    if ( (_DWORD)v4 == 1 )
    {
      v112 = *(const struct DripsWakeSource **)(v8 + 1320);
      v113 = *(const struct DripsWakeSource **)(v8 + 1328);
      while ( v112 != v113 )
      {
        v114 = DripsWakeSource::DripsWakeSource((DripsWakeSource *)&v173, v112);
        *(_QWORD *)&v168.Data1 = v114;
        v115 = *(_QWORD *)(v13 + 8);
        if ( *(_QWORD *)(v115 + 392) == *(_QWORD *)(v115 + 400) )
        {
          std::vector<DripsWakeSource>::_Emplace_reallocate<DripsWakeSource>(v115 + 384, *(_QWORD *)(v115 + 392), v114);
        }
        else
        {
          DripsWakeSource::DripsWakeSource(*(_QWORD *)(v115 + 392), v114);
          *(_QWORD *)(v116 + 392) += 64LL;
        }
        std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>((char *)v114 + 32);
        v112 = (const struct DripsWakeSource *)((char *)v112 + 64);
      }
      v154 = *(SessionModel::SystemPowerReportBuilder **)(v8 + 56);
      *(_QWORD *)(*(_QWORD *)(v13 + 8) + 416LL) = v154;
      v117 = std::wstring::wstring((__int64)&v173, (__int64)L"Info.SwLowPowerStateTime");
      v168 = GUID_SPR_SESSION_METADATA_CONTAINER;
      SessionModel::SessionBuilder::AddMetadataValues<unsigned __int64 &,>(v13, &v168, v117, &v154);
      v118 = *(SessionModel::SystemPowerReportBuilder **)(v8 + 64);
      v154 = v118;
      *(_QWORD *)(*(_QWORD *)(v13 + 8) + 408LL) = v118;
      if ( v118 != (SessionModel::SystemPowerReportBuilder *)-1LL )
      {
        v119 = std::wstring::wstring((__int64)&v173, (__int64)L"Info.HwLowPowerStateTime");
        v168 = GUID_SPR_SESSION_METADATA_CONTAINER;
        SessionModel::SessionBuilder::AddMetadataValues<unsigned __int64 &,>(v13, &v168, v119, &v154);
      }
      v120 = *(const struct DripsBucket ***)(v8 + 584);
      v121 = *(const struct DripsBucket ***)(v8 + 592);
      if ( v120 != v121 )
      {
        *(_OWORD *)v171 = 0;
        v122 = 0;
        for ( v172.m128i_i64[0] = 0; ; v122 = (DripsBucket *)v172.m128i_i64[0] )
        {
          if ( v171[1] == v122 )
          {
            std::vector<DripsBucket>::_Emplace_reallocate<DripsBucket const &>(v171, v171[1], *v120);
          }
          else
          {
            DripsBucket::DripsBucket(v171[1], *v120);
            v171[1] = (DripsBucket *)((char *)v171[1] + 48);
          }
          if ( ++v120 == v121 )
            break;
        }
        v161 = 0;
        v162 = 0;
        if ( 0xAAAAAAAAAAAAAAABuLL * ((v171[1] - v171[0]) >> 4) )
        {
          std::vector<DripsBucket>::_Buy_nonzero(&v161);
          v157 = &v161;
          *((_QWORD *)&v161 + 1) = std::_Uninitialized_copy<DripsBucket *,DripsBucket *,std::allocator<DripsBucket>>(
                                     v171[0],
                                     v171[1],
                                     (DripsBucket *)v161);
          v157 = 0;
          std::_Tidy_guard<std::vector<DripsBucket>>::~_Tidy_guard<std::vector<DripsBucket>>(&v157);
        }
        v123 = *(_QWORD *)(v13 + 8) + 360LL;
        if ( (__int128 *)v123 != &v161 )
        {
          std::vector<DripsBucket>::_Tidy(*(_QWORD *)(v13 + 8) + 360LL);
          *(_OWORD *)v123 = v161;
          *(_QWORD *)(v123 + 16) = v162;
          v161 = 0;
          v162 = 0;
        }
        std::vector<DripsBucket>::_Tidy(&v161);
        std::vector<DripsBucket>::_Tidy(v171);
      }
    }
  }
  v124 = **(__int64 ***)(v8 + 1352);
  while ( !*((_BYTE *)v124 + 25) )
  {
    v125 = (_QWORD *)v124[6];
    v126 = (_QWORD *)v124[7];
    while ( v125 != v126 )
    {
      v127 = std::wstring::wstring((__int64)&v173, v125);
      v128 = SessionModel::Metadata::Metadata(v164, v127, v125 + 4);
      v168 = (struct _GUID)*((_OWORD *)v124 + 2);
      SessionModel::SessionBuilder::AddMetadata(v13, &v168, v128);
      v125 += 9;
    }
    v129 = (__int64 **)v124[2];
    if ( *((_BYTE *)v129 + 25) )
    {
      for ( jj = (__int64 *)v124[1]; !*((_BYTE *)jj + 25) && v124 == (__int64 *)jj[2]; jj = (__int64 *)jj[1] )
        v124 = jj;
      v124 = jj;
    }
    else
    {
      v124 = (__int64 *)v124[2];
      for ( kk = *v129; !*((_BYTE *)kk + 25); kk = (__int64 *)*kk )
        v124 = kk;
    }
  }
LABEL_160:
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v165);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v176);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&Src);
}

```

## disassembly

```asm
0x180075b18  mov     rax, rsp
0x180075b1b  push    rbp
0x180075b1c  push    rbx
0x180075b1d  push    rsi
0x180075b1e  push    rdi
0x180075b1f  push    r12
0x180075b21  push    r13
0x180075b23  push    r14
0x180075b25  push    r15
0x180075b27  lea     rbp, [rax-348h]
0x180075b2e  sub     rsp, 478h
0x180075b35  movaps  xmmword ptr [rax-58h], xmm6
0x180075b39  mov     rax, cs:__security_cookie
0x180075b40  xor     rax, rsp
0x180075b43  mov     qword ptr [rbp+340h+var_58], rax
0x180075b4a  movsxd  r12, r9d
0x180075b4d  mov     [rbp+340h+var_390], r12d
0x180075b51  mov     r15, r8
0x180075b54  mov     rbx, rdx
0x180075b57  mov     r13, rcx
0x180075b5a  mov     [rbp+340h+var_3A8], rcx
0x180075b5e  lea     rcx, [rbp+340h+Src]; void *
0x180075b65  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180075b6a  nop
0x180075b6b  lea     rcx, [rbp+340h+var_158]; void *
0x180075b72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180075b77  nop
0x180075b78  lea     rcx, [rbp+340h+var_2D0]
0x180075b7c  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180075b81  nop
0x180075b82  xor     esi, esi
0x180075b84  mov     [rbp+340h+var_380], rsi
0x180075b88  mov     rcx, [rbx+148h]
0x180075b8f  mov     r8, [rbx+150h]
0x180075b96  cmp     rcx, r8
0x180075b99  jz      short loc_180075BCF
0x180075b9b  mov     r9, [r15+0A8h]
0x180075ba2  mov     rdx, [rcx]
0x180075ba5  cmp     [rdx+0B8h], r9
0x180075bac  jnz     short loc_180075BBD
0x180075bae  mov     eax, [r15+0B0h]
0x180075bb5  cmp     [rdx+0C0h], eax
0x180075bbb  jz      short loc_180075BC8
0x180075bbd  add     rcx, 8
0x180075bc1  cmp     rcx, r8
0x180075bc4  jnz     short loc_180075BA2
0x180075bc6  jmp     short loc_180075BCF
0x180075bc8  mov     rsi, rdx
0x180075bcb  mov     [rbp+340h+var_380], rdx
0x180075bcf  test    r12d, r12d
0x180075bd2  jnz     short loc_180075BF6
0x180075bd4  test    rsi, rsi
0x180075bd7  jz      short loc_180075BF6
0x180075bd9  lea     rcx, [rsi+5A8h]; this
0x180075be0  call    ?GetDurationInUs@SegmentData@@QEBA_KXZ; SegmentData::GetDurationInUs(void)
0x180075be5  mov     edx, [r13+30h]
0x180075be9  xor     ecx, ecx
0x180075beb  cmp     rax, rdx
0x180075bee  cmovb   rsi, rcx
0x180075bf2  mov     [rbp+340h+var_380], rsi
0x180075bf6  mov     eax, [r15+0B0h]
0x180075bfd  mov     rcx, [r15+0A8h]
0x180075c04  mov     qword ptr [rbp+340h+var_1E0.Data1], rax
0x180075c0b  lea     rdx, [rbp+340h+var_1E0]
0x180075c12  test    r12d, r12d
0x180075c15  jnz     short loc_180075C2C
0x180075c17  lea     rax, [rcx-1]
0x180075c1b  mov     qword ptr [rbp+340h+var_1E0.Data4], rax
0x180075c22  mov     rcx, r13
0x180075c25  call    ?CreateScreenOffSession@SystemPowerReportBuilder@SessionModel@@QEAAPEAVScreenOffSessionBuilder@2@UOsSessionId@2@@Z; SessionModel::SystemPowerReportBuilder::CreateScreenOffSession(SessionModel::OsSessionId)
0x180075c2a  jmp     short loc_180075C3B
0x180075c2c  mov     qword ptr [rbp+340h+var_1E0.Data4], rcx
0x180075c33  mov     rcx, r13
0x180075c36  call    ?CreateModernSleepSession@SystemPowerReportBuilder@SessionModel@@QEAAPEAVModernSleepSessionBuilder@2@UOsSessionId@2@@Z; SessionModel::SystemPowerReportBuilder::CreateModernSleepSession(SessionModel::OsSessionId)
0x180075c3b  mov     r14, rax
0x180075c3e  mov     [rbp+340h+var_388], rax
0x180075c42  mov     rbx, [r15+0D0h]
0x180075c49  mov     rdi, [r15+0D8h]
0x180075c50  jmp     short loc_180075C86
0x180075c52  mov     rdx, [rbx]; struct CustomData *
0x180075c55  lea     rcx, [rbp+340h+var_1A0]; this
0x180075c5c  call    ??0Metadata@SessionModel@@QEAA@AEBUCustomData@@@Z; SessionModel::Metadata::Metadata(CustomData const &)
0x180075c61  movups  xmm0, xmmword ptr cs:GUID_SPR_SESSION_METADATA_CONTAINER.Data1
0x180075c68  movdqu  xmmword ptr [rbp+340h+var_1E0.Data1], xmm0
0x180075c70  mov     r8, rax
0x180075c73  lea     rdx, [rbp+340h+var_1E0]
0x180075c7a  mov     rcx, r14
0x180075c7d  call    ?AddMetadata@SessionBuilder@SessionModel@@QEAAXU_GUID@@VMetadata@2@@Z; SessionModel::SessionBuilder::AddMetadata(_GUID,SessionModel::Metadata)
0x180075c82  add     rbx, 8
0x180075c86  cmp     rbx, rdi
0x180075c89  jnz     short loc_180075C52
0x180075c8b  cmp     byte ptr [r15+14h], 0
0x180075c90  jnz     short loc_180075CA0
0x180075c92  mov     rax, [r14+8]
0x180075c96  mov     dword ptr [rax+0B0h], 4
0x180075ca0  test    r12d, r12d
0x180075ca3  jnz     short loc_180075CB9
0x180075ca5  mov     edi, [r15+24h]
0x180075ca9  cmp     [r15+0E8h], r12b
0x180075cb0  jz      short loc_180075CBE
0x180075cb2  mov     ebx, 101h
0x180075cb7  jmp     short loc_180075CC2
0x180075cb9  mov     edi, 101h
0x180075cbe  mov     ebx, [r15+6Ch]
0x180075cc2  mov     ecx, edi
0x180075cc4  call    ?GetSprSessionTransitionReasonString@@YAPEBGT_SPR_SESSION_TRANSITION_REASON@@@Z; GetSprSessionTransitionReasonString(_SPR_SESSION_TRANSITION_REASON)
0x180075cc9  mov     rdx, rax
0x180075ccc  lea     rcx, [rbp+340h+Src]
0x180075cd3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180075cd8  mov     ecx, ebx
0x180075cda  call    ?GetSprSessionTransitionReasonString@@YAPEBGT_SPR_SESSION_TRANSITION_REASON@@@Z; GetSprSessionTransitionReasonString(_SPR_SESSION_TRANSITION_REASON)
0x180075cdf  mov     rdx, rax
0x180075ce2  lea     rcx, [rbp+340h+var_158]
0x180075ce9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180075cee  test    rsi, rsi
0x180075cf1  jz      loc_180075D8D
0x180075cf7  mov     rax, [rsi+518h]
0x180075cfe  mov     [rbp+340h+var_3B8], rax
0x180075d02  test    rax, rax
0x180075d05  jz      short loc_180075D46
0x180075d07  cmp     [rax], edi
0x180075d09  jnz     short loc_180075D46
0x180075d0b  mov     r8d, 3
0x180075d11  lea     rdx, asc_1800A5F60; " : "
0x180075d18  lea     rcx, [rbp+340h+Src]; Src
0x180075d1f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180075d24  mov     rdx, [rbp+340h+var_3B8]
0x180075d28  add     rdx, 28h ; '('
0x180075d2c  mov     r8, [rdx+10h]
0x180075d30  cmp     qword ptr [rdx+18h], 7
0x180075d35  jbe     short loc_180075D3A
0x180075d37  mov     rdx, [rdx]
0x180075d3a  lea     rcx, [rbp+340h+Src]; Src
0x180075d41  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180075d46  mov     rdi, [rsi+520h]
0x180075d4d  test    rdi, rdi
0x180075d50  jz      short loc_180075D8D
0x180075d52  cmp     [rdi], ebx
0x180075d54  jnz     short loc_180075D8D
0x180075d56  mov     r8d, 3
0x180075d5c  lea     rdx, asc_1800A5F60; " : "
0x180075d63  lea     rcx, [rbp+340h+var_158]; Src
0x180075d6a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180075d6f  lea     rdx, [rdi+28h]
0x180075d73  mov     r8, [rdx+10h]
0x180075d77  cmp     qword ptr [rdx+18h], 7
0x180075d7c  jbe     short loc_180075D81
0x180075d7e  mov     rdx, [rdx]
0x180075d81  lea     rcx, [rbp+340h+var_158]; Src
0x180075d88  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180075d8d  movups  xmm0, [rbp+340h+Src]
0x180075d94  movups  [rbp+340h+var_378], xmm0
0x180075d98  movups  xmm1, [rbp+340h+var_128]
0x180075d9f  movups  [rbp+340h+var_368], xmm1
0x180075da3  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180075dab  movdqu  [rbp+340h+var_128], xmm6
0x180075db3  xor     edi, edi
0x180075db5  mov     word ptr [rbp+340h+Src], di
0x180075dbc  lea     rdx, [rbp+340h+var_378]
0x180075dc0  mov     rcx, r14
0x180075dc3  call    ?SetEntryReason@SessionBuilder@SessionModel@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SessionModel::SessionBuilder::SetEntryReason(std::wstring)
0x180075dc8  movups  xmm0, [rbp+340h+var_158]
0x180075dcf  movups  [rbp+340h+var_378], xmm0
0x180075dd3  movups  xmm1, [rbp+340h+var_148]
0x180075dda  movups  [rbp+340h+var_368], xmm1
0x180075dde  movdqu  [rbp+340h+var_148], xmm6
0x180075de6  mov     word ptr [rbp+340h+var_158], di
0x180075ded  lea     rdx, [rbp+340h+var_378]
0x180075df1  mov     rcx, r14
0x180075df4  call    ?SetExitReason@SessionBuilder@SessionModel@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SessionModel::SessionBuilder::SetExitReason(std::wstring)
0x180075df9  cmp     [r15+0BCh], edi
0x180075e00  setnz   cl
0x180075e03  mov     rax, [r14+8]
0x180075e07  mov     [rax+0E0h], cl
0x180075e0d  cmp     [r15+0C0h], dil
0x180075e14  setnz   cl
0x180075e17  mov     rax, [r14+8]
0x180075e1b  mov     [rax+0E1h], cl
0x180075e21  test    rsi, rsi
0x180075e24  jz      short loc_180075E77
0x180075e26  mov     rdi, r12
0x180075e29  shl     rdi, 7
0x180075e2d  add     rdi, 5A8h
0x180075e34  add     rdi, rsi
0x180075e37  lea     rdx, [rbp+340h+var_3B8]
0x180075e3b  mov     rcx, rdi; this
0x180075e3e  call    ?GetStartTime@SegmentData@@QEBA?AT_LARGE_INTEGER@@XZ; SegmentData::GetStartTime(void)
0x180075e43  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180075e4d  mul     [rbp+340h+var_3B8]
0x180075e51  mov     rbx, rdx
0x180075e54  shr     rbx, 3
0x180075e58  mov     r8b, 1; bool
0x180075e5b  mov     rdx, rbx; unsigned __int64
0x180075e5e  mov     rcx, r14; this
0x180075e61  call    ?SetEntryTimeInUs@SessionBuilder@SessionModel@@QEAAX_K_N@Z; SessionModel::SessionBuilder::SetEntryTimeInUs(unsigned __int64,bool)
0x180075e66  mov     rcx, rdi; this
0x180075e69  call    ?GetDurationInUs@SegmentData@@QEBA_KXZ; SegmentData::GetDurationInUs(void)
0x180075e6e  lea     rdx, [rbx+rax]
0x180075e72  jmp     loc_180075F5B
0x180075e77  cmp     dword ptr [r15+10h], 0Ch
0x180075e7c  jnz     loc_180075F08
0x180075e82  cmp     [r15+20h], dil
0x180075e86  setnz   r8b; bool
0x180075e8a  mov     rbx, 0CCCCCCCCCCCCCCCDh
0x180075e94  mov     rax, rbx
0x180075e97  mul     qword ptr [r15+18h]
0x180075e9b  shr     rdx, 3; unsigned __int64
0x180075e9f  mov     rcx, r14; this
0x180075ea2  call    ?SetEntryTimeInUs@SessionBuilder@SessionModel@@QEAAX_K_N@Z; SessionModel::SessionBuilder::SetEntryTimeInUs(unsigned __int64,bool)
0x180075ea7  cmp     [r15+68h], dil
0x180075eab  setnz   r8b; bool
0x180075eaf  mov     rax, rbx
0x180075eb2  mul     qword ptr [r15+60h]
0x180075eb6  shr     rdx, 3; unsigned __int64
0x180075eba  call    ?SetExitTimeInUs@SessionBuilder@SessionModel@@QEAAX_K_N@Z; SessionModel::SessionBuilder::SetExitTimeInUs(unsigned __int64,bool)
0x180075ebf  mov     ecx, [r15+58h]
0x180075ec3  mov     edx, [r15+54h]
0x180075ec7  or      qword ptr [r14+10h], 4
0x180075ecc  mov     rax, [r14+8]
0x180075ed0  mov     [rax+0B8h], rcx
0x180075ed7  mov     [rax+0C0h], rdx
0x180075ede  mov     ecx, [r15+0A0h]
0x180075ee5  mov     edx, [r15+9Ch]
0x180075eec  or      qword ptr [r14+10h], 20h
0x180075ef1  mov     rax, [r14+8]
0x180075ef5  mov     [rax+0C8h], rcx
0x180075efc  mov     [rax+0D0h], rdx
0x180075f03  jmp     loc_180075FBE
0x180075f08  lea     rax, [r12+2]
0x180075f0d  imul    rdi, rax, 78h ; 'x'
0x180075f11  add     rdi, r15
0x180075f14  lea     rdx, [rbp+340h+var_3A0]
0x180075f18  mov     rcx, rdi; this
0x180075f1b  call    ?GetStartTime@SegmentData@@QEBA?AT_LARGE_INTEGER@@XZ; SegmentData::GetStartTime(void)
0x180075f20  mov     rcx, rax
0x180075f23  mov     rbx, 0CCCCCCCCCCCCCCCDh
0x180075f2d  mov     rax, rbx
0x180075f30  mul     qword ptr [rcx]
0x180075f33  shr     rdx, 3; unsigned __int64
0x180075f37  mov     r8b, 1; bool
0x180075f3a  mov     rcx, r14; this
0x180075f3d  call    ?SetEntryTimeInUs@SessionBuilder@SessionModel@@QEAAX_K_N@Z; SessionModel::SessionBuilder::SetEntryTimeInUs(unsigned __int64,bool)
0x180075f42  lea     rdx, [rbp+340h+var_3A0]
0x180075f46  mov     rcx, rdi; this
0x180075f49  call    ?GetExitTime@SegmentData@@QEBA?AT_LARGE_INTEGER@@XZ; SegmentData::GetExitTime(void)
0x180075f4e  mov     rcx, rax
0x180075f51  mov     rax, rbx
0x180075f54  mul     qword ptr [rcx]
0x180075f57  shr     rdx, 3; unsigned __int64
0x180075f5b  mov     r8b, 1; bool
0x180075f5e  mov     rcx, r14; this
0x180075f61  call    ?SetExitTimeInUs@SessionBuilder@SessionModel@@QEAAX_K_N@Z; SessionModel::SessionBuilder::SetExitTimeInUs(unsigned __int64,bool)
0x180075f66  mov     rcx, rdi; this
0x180075f69  call    ?GetEntryBatteryFullCapacity@SegmentData@@QEBAKXZ; SegmentData::GetEntryBatteryFullCapacity(void)
0x180075f6e  mov     ebx, eax
0x180075f70  mov     rcx, rdi; this
0x180075f73  call    ?GetEntryBatteryRemainingCapacity@SegmentData@@QEBAKXZ; SegmentData::GetEntryBatteryRemainingCapacity(void)
0x180075f78  mov     edx, eax
0x180075f7a  or      qword ptr [r14+10h], 4
0x180075f7f  mov     rax, [r14+8]
0x180075f83  mov     [rax+0B8h], rbx
0x180075f8a  mov     [rax+0C0h], rdx
0x180075f91  mov     rcx, rdi; this
0x180075f94  call    ?GetExitBatteryFullCapacity@SegmentData@@QEBAKXZ; SegmentData::GetExitBatteryFullCapacity(void)
0x180075f99  mov     ebx, eax
0x180075f9b  mov     rcx, rdi; this
0x180075f9e  call    ?GetExitBatteryRemainingCapacity@SegmentData@@QEBAKXZ; SegmentData::GetExitBatteryRemainingCapacity(void)
0x180075fa3  mov     ecx, eax
0x180075fa5  or      qword ptr [r14+10h], 20h
0x180075faa  mov     rax, [r14+8]
0x180075fae  mov     [rax+0C8h], rbx
0x180075fb5  xor     edi, edi
0x180075fb7  mov     [rax+0D0h], rcx
0x180075fbe  cmp     [r15+0C1h], dil
0x180075fc5  setnz   r9b
0x180075fc9  cmp     [r15+0C2h], dil
0x180075fd0  setnz   r8b
0x180075fd4  cmp     [r15+0C3h], dil
0x180075fdb  setnz   dl
0x180075fde  cmp     [r15+0C4h], dil
0x180075fe5  setnz   cl
0x180075fe8  or      qword ptr [r14+10h], 40h
0x180075fed  mov     rax, [r14+8]
0x180075ff1  mov     [rax+0D8h], r9b
0x180075ff8  mov     [rax+0D9h], r8b
0x180075fff  mov     [rax+0DAh], dl
0x180076005  mov     [rax+0DBh], cl
0x18007600b  cmp     [r15+0C5h], dil
0x180076012  setnz   r9b
0x180076016  cmp     [r15+0C6h], dil
0x18007601d  setnz   r8b
0x180076021  cmp     [r15+0C7h], dil
0x180076028  setnz   dl
0x18007602b  cmp     [r15+0C8h], dil
0x180076032  setnz   cl
0x180076035  bts     qword ptr [r14+10h], 7
0x18007603b  mov     rax, [r14+8]
0x18007603f  mov     [rax+0DCh], r9b
0x180076046  mov     [rax+0DDh], r8b
0x18007604d  mov     [rax+0DEh], dl
  ... truncated ...
```
