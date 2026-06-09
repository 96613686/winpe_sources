# Osf::FluidControlApi::GetNativeInfo(IExecuteArgumentSet *,Osf::IFluidControlApiUser const *)

- ea: `0x180f776a4`
- end: `0x180f78a97`
- name: `?GetNativeInfo@FluidControlApi@Osf@@CAXPEAUIExecuteArgumentSet@@PEBUIFluidControlApiUser@2@@Z`
- size: `5107`
- prototype: `void __fastcall(struct IExecuteArgumentSet *, const struct Osf::IFluidControlApiUser *)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1808e4714`

## callees

- `0x18002d954`
- `0x18002e214`
- `0x18002e308`
- `0x18006eaec`
- `0x180094190`
- `0x180094440`
- `0x18009456c`
- `0x180164b00`
- `0x18019b8ac`
- `0x1802e2190`
- `0x1802e5170`
- `0x1802e5190`
- `0x180389390`
- `0x1803ac6f8`
- `0x1804cf3dc`
- `0x1804cfa30`
- `0x18059e664`
- `0x1806c2130`
- `0x1807e7004`
- `0x18080cab0`
- `0x1809134f8`
- `0x180f76b14`
- `0x180f776a4`
- `0x180f78bc0`
- `0x180f79260`
- `0x180f79350`
- `0x180f7a474`
- `0x180f7a900`

## import_xrefs

- `Mso30Win32Client!__imp_?CreateConfigUrlBuilder@OfficeWebServiceApi@Mso@@YA?AV?$TCntPtr@UIUrlBuilder@OfficeWebServiceApi@Mso@@@2@VMsoReserveTag@@W4URL@ConfigURL@12@@Z` at `0x180f77964`
- `Mso30Win32Client!__imp_?CreateConfigUrlBuilder@OfficeWebServiceApi@Mso@@YA?AV?$TCntPtr@UIUrlBuilder@OfficeWebServiceApi@Mso@@@2@VMsoReserveTag@@W4URL@ConfigURL@12@@Z` at `0x180f77964`
- `Mso30Win32Client!__imp_?IsOneAuthEnabled@IdentityFlights@Authentication@Mso@@YA_NXZ` at `0x180f787e5`
- `Mso30Win32Client!__imp_?IsOneAuthEnabled@IdentityFlights@Authentication@Mso@@YA_NXZ` at `0x180f787e5`
- `Mso20Win32Client!__imp_?GetChannel@AudienceApi@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ` at `0x180f7784c`
- `Mso20Win32Client!__imp_?GetChannel@AudienceApi@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ` at `0x180f7784c`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f788cc`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f788cc`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f7846b`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f784eb`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f786a6`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f78798`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f7846b`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f784eb`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f786a6`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f78798`
- `Mso20Win32Client!__imp_?GetAudienceGroup@AudienceApi@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ` at `0x180f777c9`
- `Mso20Win32Client!__imp_?GetAudienceGroup@AudienceApi@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ` at `0x180f777c9`
- `Mso20Win32Client!__imp_?CreateJsonWriter@Json@Mso@@YA?AV?$TCntPtr@UIJsonWriter@Json@Mso@@@2@XZ` at `0x180f776e9`
- `Mso20Win32Client!__imp_?CreateJsonWriter@Json@Mso@@YA?AV?$TCntPtr@UIJsonWriter@Json@Mso@@@2@XZ` at `0x180f776e9`

## string_xrefs

- `0x180f77d9e`: `isReadOnly`
- `0x180f780f0`: `linkUrl`
- `0x180f77b21`: `Invalid json for OEP.FluidHost.FluidSettingOverrides`
- `0x180f77de2`: `loopComponentPropertiesAreEnabled`
- `0x180f77d5a`: `linkProblemState`
- `0x180f77e68`: `createParams`
- `0x180f782cf`: `manifestData`
- `0x180f7839a`: `safeLinkWrappedUrl`
- `0x180f78803`: `useTokenCache`
- `0x180f78098`: `linkText`

## pseudocode

```c
void __fastcall Osf::FluidControlApi::GetNativeInfo(
        struct IExecuteArgumentSet *a1,
        const struct Osf::IFluidControlApiUser *a2,
        int a3)
{
  __int64 v5; // rdi
  char v6; // r15
  char v7; // bl
  char v8; // r12
  const struct Osf::LoopInfo *v9; // rax
  __int64 v10; // rax
  _QWORD *v11; // r8
  char *v12; // r8
  _QWORD *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // r8
  _QWORD *v16; // rdx
  _QWORD *v17; // r8
  char *v18; // r8
  _QWORD *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // r8
  _QWORD *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // r8
  struct tagVARIANT *v33; // rdx
  __int64 v34; // rax
  int v35; // r9d
  __int64 v36; // rax
  _QWORD *v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // r8
  _QWORD *v42; // rdx
  __int64 v43; // rax
  __int64 v44; // r8
  _QWORD *v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rdx
  bool IsOptionalConnectedExperiencesEnabled; // bl
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rax
  __int64 v71; // rax
  bool v72; // bl
  __int64 v73; // rax
  __int64 v74; // rbx
  void (__fastcall *v75)(__int64, _QWORD *); // rdi
  _QWORD *v76; // rax
  bool v77; // bl
  __int64 v78; // rax
  __int64 v79; // rbx
  void (__fastcall *v80)(__int64, _QWORD *); // rdi
  _QWORD *v81; // rax
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rdx
  __int64 v88; // rax
  __int64 v89; // r8
  _QWORD *v90; // rdx
  __int64 v91; // rax
  __int64 v92; // r8
  _QWORD *v93; // rdx
  __int64 v94; // rax
  __int64 v95; // r8
  _QWORD *v96; // rdx
  __int64 v97; // rax
  __int64 v98; // r8
  _QWORD *v99; // rdx
  __int64 v100; // rax
  __int64 v101; // r8
  _QWORD *v102; // rdx
  __int64 v103; // rax
  __int64 v104; // r8
  _QWORD *v105; // rdx
  __int64 v106; // rax
  __int64 v107; // r8
  _QWORD *v108; // rdx
  __int64 v109; // rax
  __int64 v110; // r8
  _QWORD *v111; // rdx
  __int64 v112; // rax
  __int64 v113; // r8
  _QWORD *v114; // rdx
  __int64 v115; // rax
  __int64 v116; // rax
  __int64 v117; // rbx
  __int64 v118; // rax
  char v119; // al
  bool v120; // cl
  char v121; // bl
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rdx
  bool v125; // al
  __int64 v126; // rax
  __int64 v127; // rax
  __int64 *v128; // rbx
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 **v131; // rax
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rdi
  void (__fastcall *v137)(__int64, _QWORD); // rbx
  int TelemetryBatchDuration; // eax
  __int64 v139; // rax
  __int64 v140; // rax
  __int64 v141; // rdx
  bool v142; // al
  __int64 v143; // rax
  __int64 v144; // rax
  __int64 v145; // rdx
  __int64 v146; // rax
  __int64 v147; // rax
  __int64 v148; // rdx
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 v151; // rdx
  Mso::Authentication::IdentityFlights *v152; // rcx
  bool v153; // al
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 v156; // rdx
  __int64 v157; // rax
  __int64 v158; // rax
  __int64 v159; // rdx
  __int64 v160; // rax
  __int64 v161; // rdi
  void (__fastcall *v162)(__int64, struct tagVARIANT *); // rbx
  __int64 v163; // rax
  struct tagVARIANT *v164; // rdx
  bool v165; // al
  __int64 v166; // rax
  __int64 v167; // rbx
  void (__fastcall *v168)(__int64, _QWORD *); // rdi
  _QWORD *v169; // rax
  __int64 v170; // rax
  __int64 v171; // rax
  int v172; // edx
  const wchar_t *v173; // r8
  __int64 v174; // rcx
  __int64 v175; // [rsp+30h] [rbp-D0h] BYREF
  char v176; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v177; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v178; // [rsp+48h] [rbp-B8h] BYREF
  struct tagVARIANT v179; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v180; // [rsp+68h] [rbp-98h]
  _QWORD v181[3]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v182; // [rsp+88h] [rbp-78h]
  _QWORD v183[3]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v184; // [rsp+A8h] [rbp-58h]
  wchar_t *v185[2]; // [rsp+B0h] [rbp-50h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-40h]
  _QWORD v187[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v188[4]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v189[4]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v190[4]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v191[4]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v192[4]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v193[4]; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v194[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v195[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v196[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD v197[4]; // [rsp+210h] [rbp+110h] BYREF
  _QWORD v198[4]; // [rsp+230h] [rbp+130h] BYREF
  _QWORD v199[4]; // [rsp+250h] [rbp+150h] BYREF
  char v200; // [rsp+270h] [rbp+170h]
  _BYTE v201[42]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v202[6]; // [rsp+2AAh] [rbp+1AAh] BYREF

  Osf::CSafeArrayWriter::CSafeArrayWriter((Osf::CSafeArrayWriter *)&v177, (int)a2, a3);
  Mso::Json::CreateJsonWriter(&v175);
  *(_OWORD *)v185 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v185[0]) = 0;
  v5 = (*(int (__fastcall **)(const struct Osf::IFluidControlApiUser *))(*(_QWORD *)a2 + 136LL))(a2);
  v6 = (*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *))(*(_QWORD *)a2 + 144LL))(a2);
  (*(void (__fastcall **)(const struct Osf::IFluidControlApiUser *, _QWORD *))(*(_QWORD *)a2 + 128LL))(a2, v190);
  v7 = (*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *))(*(_QWORD *)a2 + 192LL))(a2);
  v8 = (**(__int64 (__fastcall ***)(const struct Osf::IFluidControlApiUser *))a2)(a2);
  (*(void (__fastcall **)(const struct Osf::IFluidControlApiUser *, _QWORD *))(*(_QWORD *)a2 + 8LL))(a2, v189);
  v9 = (const struct Osf::LoopInfo *)(*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *))(*(_QWORD *)a2 + 152LL))(a2);
  Osf::LoopInfo::LoopInfo((Osf::LoopInfo *)v191, v9);
  v10 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  Mso::AudienceApi::GetAudienceGroup(v183);
  v11 = v183;
  if ( v184 > 0xF )
    v11 = (_QWORD *)v183[0];
  v12 = (char *)v11 + v183[2];
  v13 = v183;
  if ( v184 > 0xF )
    v13 = (_QWORD *)v183[0];
  std::wstring::wstring(v188, v13, v12);
  v14 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v14 + 48LL))(v14, L"audienceGroup");
  v15 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  v16 = v188;
  if ( v188[3] > 7u )
    v16 = (_QWORD *)v188[0];
  (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v15 + 56LL))(v15, v16);
  Mso::AudienceApi::GetChannel(v181);
  v17 = v181;
  if ( v182 > 0xF )
    v17 = (_QWORD *)v181[0];
  v18 = (char *)v17 + v181[2];
  v19 = v181;
  if ( v182 > 0xF )
    v19 = (_QWORD *)v181[0];
  std::wstring::wstring(v187, v19, v18);
  v20 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v20 + 48LL))(v20, L"channel");
  v21 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  v22 = v187;
  if ( v187[3] > 7u )
    v22 = (_QWORD *)v187[0];
  (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v21 + 56LL))(v21, v22);
  v23 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v23 + 48LL))(v23, L"enableRightToLeftSplashScreen");
  v24 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  LOBYTE(v25) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 64LL))(v24, v25);
  v26 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v26 + 48LL))(v26, L"enableShowLoopGlowBorderEvent");
  v27 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  LOBYTE(v28) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 64LL))(v27, v28);
  Mso::OfficeWebServiceApi::CreateConfigUrlBuilder(&v178, 504673955, 358);
  if ( v178 )
  {
    v29 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v178);
    v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 160LL))(v29);
    std::wstring::wstring(&v179, v30);
    v31 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v31 + 48LL))(v31, L"graphEndpoint");
    v32 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    v33 = &v179;
    if ( v180 > 7 )
      v33 = *(struct tagVARIANT **)&v179.vt;
    (*(void (__fastcall **)(__int64, struct tagVARIANT *))(*(_QWORD *)v32 + 56LL))(v32, v33);
    std::wstring::~wstring(&v179);
  }
  if ( dword_1815BAC20 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 16LL) )
  {
    Init_thread_header(&dword_1815BAC20);
    if ( dword_1815BAC20 == -1 )
    {
      std::wstring::wstring(v201, &WindowName);
      *(_QWORD *)&v179.vt = "FluidHost.FluidSettingOverrides";
      v176 = 52;
      Mso::AB::Optimized::Setting<std::wstring>::Setting<std::wstring>(
        (unsigned int)qword_1815BAC30,
        (unsigned int)&v176,
        (unsigned int)&v179,
        (unsigned int)v201,
        0);
      std::wstring::~wstring(v201);
      atexit(sub_1808B8AC0);
      Init_thread_footer(&dword_1815BAC20);
    }
  }
  if ( *(_QWORD *)(Mso::AB::Optimized::Setting<std::wstring>::operator std::wstring const &(qword_1815BAC30) + 16) )
  {
    v34 = Mso::AB::Optimized::Setting<std::wstring>::operator std::wstring const &(qword_1815BAC30);
    if ( *(_QWORD *)(v34 + 24) > 7u )
      v34 = *(_QWORD *)v34;
    if ( Osf::FluidControlApi::IsValidJson((const wchar_t *)v34) )
    {
      v36 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
      (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v36 + 48LL))(v36, L"fluidSettingOverrides");
      v37 = (_QWORD *)Mso::AB::Optimized::Setting<std::wstring>::operator std::wstring const &(qword_1815BAC30);
      if ( v37[3] > 7u )
        v37 = (_QWORD *)*v37;
      Osf::FluidControlApi::WriteJson(&v175, v37);
    }
    else
    {
      *(_QWORD *)&v179.vt = "Invalid json for OEP.FluidHost.FluidSettingOverrides";
      Mso::Diagnostics::SendDiagnosticTrace<>(512340195, 2489, 10, v35, (__int64)&v179);
    }
  }
  v38 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v38 + 48LL))(v38, L"host");
  v39 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v39 + 56LL))(v39, L"fluidControlApi");
  v40 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v40 + 48LL))(v40, L"hydrateId");
  v41 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  v42 = v190;
  if ( v190[3] > 7u )
    v42 = (_QWORD *)v190[0];
  (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v41 + 56LL))(v41, v42);
  v43 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v43 + 48LL))(v43, L"hydrateScenarioEntryPoint");
  v44 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  v45 = v189;
  if ( v189[3] > 7u )
    v45 = (_QWORD *)v189[0];
  (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v44 + 56LL))(v44, v45);
  v46 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v46 + 48LL))(v46, L"isCardChannelProviderEnabled");
  v47 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  LOBYTE(v48) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v47 + 64LL))(v47, v48);
  v49 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v49 + 48LL))(v49, L"isDarkBackground");
  v50 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  LOBYTE(v51) = v7;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 64LL))(v50, v51);
  v52 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v52 + 48LL))(v52, L"isInEditableDocument");
  v53 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  LOBYTE(v54) = v8;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 64LL))(v53, v54);
  IsOptionalConnectedExperiencesEnabled = Osf::FluidControlApi::IsOptionalConnectedExperiencesEnabled();
  v56 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v56 + 48LL))(
    v56,
    L"isOptionalConnectedExperiencesEnabled");
  v57 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  LOBYTE(v58) = IsOptionalConnectedExperiencesEnabled;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v57 + 64LL))(v57, v58);
  v59 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v59 + 48LL))(v59, L"linkProblemState");
  v60 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v60 + 72LL))(v60, v5);
  v61 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v61 + 48LL))(v61, L"isReadOnly");
  v62 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  LOBYTE(v63) = v6;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 64LL))(v62, v63);
  v64 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v64 + 48LL))(v64, L"loopComponentPropertiesAreEnabled");
  v65 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  LOBYTE(v66) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v65 + 64LL))(v65, v66);
  v67 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v67 + 48LL))(v67, L"useLoopContentWidthEnabled");
  v68 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  LOBYTE(v69) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 64LL))(v68, v69);
  v70 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v70 + 48LL))(v70, L"createParams");
  v71 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
  v72 = *(_QWORD *)((*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *, _BYTE *))(*(_QWORD *)a2 + 112LL))(
                      a2,
                      v201)
                  + 16) != 0;
  std::wstring::~wstring(v201);
  if ( v72 )
  {
    v73 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v73 + 48LL))(v73, L"loopFileName");
    v74 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    v75 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v74 + 56LL);
    v76 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *, _BYTE *))(*(_QWORD *)a2 + 112LL))(
                      a2,
                      v201);
    if ( v76[3] > 7u )
      v76 = (_QWORD *)*v76;
    v75(v74, v76);
    std::wstring::~wstring(v201);
  }
  v77 = *(_QWORD *)((*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *, _BYTE *))(*(_QWORD *)a2 + 120LL))(
                      a2,
                      v201)
                  + 16) != 0;
  std::wstring::~wstring(v201);
  if ( v77 )
  {
    v78 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v78 + 48LL))(v78, L"loopFolderName");
    v79 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    v80 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v79 + 56LL);
    v81 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *, _BYTE *))(*(_QWORD *)a2 + 120LL))(
                      a2,
                      v201);
    if ( v81[3] > 7u )
      v81 = (_QWORD *)*v81;
    v80(v79, v81);
    std::wstring::~wstring(v201);
  }
  v82 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 24LL))(v82);
  v83 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v83 + 48LL))(v83, L"loopInfo");
  v84 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
  v85 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v85 + 48LL))(v85, L"isFluidLoop");
  v86 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  LOBYTE(v87) = v200;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v86 + 64LL))(v86, v87);
  if ( v191[2] )
  {
    v88 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v88 + 48LL))(v88, L"linkText");
    v89 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    v90 = v191;
    if ( v191[3] > 7u )
      v90 = (_QWORD *)v191[0];
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v89 + 56LL))(v89, v90);
  }
  if ( v192[2] )
  {
    v91 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v91 + 48LL))(v91, L"linkUrl");
    v92 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    v93 = v192;
    if ( v192[3] > 7u )
      v93 = (_QWORD *)v192[0];
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v92 + 56LL))(v92, v93);
  }
  if ( v193[2] )
  {
    v94 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v94 + 48LL))(v94, L"loopData");
    v95 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    v96 = v193;
    if ( v193[3] > 7u )
      v96 = (_QWORD *)v193[0];
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v95 + 56LL))(v95, v96);
  }
  if ( v194[2] )
  {
    v97 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v97 + 48LL))(v97, L"loopIconUrl");
    v98 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    v99 = v194;
    if ( v194[3] > 7u )
      v99 = (_QWORD *)v194[0];
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v98 + 56LL))(v98, v99);
  }
  if ( v195[2] )
  {
    v100 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v100 + 48LL))(v100, L"loopName");
    v101 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    v102 = v195;
    if ( v195[3] > 7u )
      v102 = (_QWORD *)v195[0];
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v101 + 56LL))(v101, v102);
  }
  if ( v196[2] )
  {
    v103 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v103 + 48LL))(v103, L"loopTitle");
    v104 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    v105 = v196;
    if ( v196[3] > 7u )
      v105 = (_QWORD *)v196[0];
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v104 + 56LL))(v104, v105);
  }
  if ( v197[2] )
  {
    v106 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v106 + 48LL))(v106, L"manifestData");
    v107 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    v108 = v197;
    if ( v197[3] > 7u )
      v108 = (_QWORD *)v197[0];
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v107 + 56LL))(v107, v108);
  }
  if ( v198[2] )
  {
    v109 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v109 + 48LL))(v109, L"registrationId");
    v110 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    v111 = v198;
    if ( v198[3] > 7u )
      v111 = (_QWORD *)v198[0];
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v110 + 56LL))(v110, v111);
  }
  if ( v199[2] && !v200 )
  {
    v112 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v112 + 48LL))(v112, L"safeLinkWrappedUrl");
    v113 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    v114 = v199;
    if ( v199[3] > 7u )
      v114 = (_QWORD *)v199[0];
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v113 + 56LL))(v113, v114);
  }
  v115 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v115 + 24LL))(v115);
  v116 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v116 + 48LL))(v116, L"scenarioStartTime");
  v117 = (*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *))(*(_QWORD *)a2 + 160LL))(a2);
  v118 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v118 + 80LL))(v118, v117);
  v119 = byte_18154C6E8;
  if ( byte_18154C6E8 < 0 )
  {
    v120 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_18154C6E8);
    v119 = byte_18154C6E8;
  }
  else
  {
    v120 = byte_18154C6E8 != 0;
  }
  if ( v120 )
  {
    v121 = (*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *))(*(_QWORD *)a2 + 216LL))(a2);
    v122 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v122 + 48LL))(v122, L"showTeachingCallout");
    v123 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    LOBYTE(v124) = v121;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v123 + 64LL))(v123, v124);
    v119 = byte_18154C6E8;
  }
  if ( v119 < 0 )
    v125 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_18154C6E8);
  else
    v125 = v119 != 0;
  if ( v125 )
  {
    GetTeachingCalloutColors(&v179);
    v126 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v126 + 48LL))(v126, L"teachingCalloutColors");
    v127 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
    v128 = **(__int64 ***)&v179.vt;
    while ( !*((_BYTE *)v128 + 25) )
    {
      v129 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v129 + 48LL))(v129, v128[4]);
      v130 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v130 + 72LL))(v130, *((unsigned int *)v128 + 10));
      v131 = (__int64 **)v128[2];
      if ( *((_BYTE *)v131 + 25) )
      {
        for ( i = (__int64 *)v128[1]; !*((_BYTE *)i + 25) && v128 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v128 = i;
        v128 = i;
      }
      else
      {
        v128 = (__int64 *)v128[2];
        for ( j = *v131; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v128 = j;
      }
    }
    v134 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 24LL))(v134);
    std::_Tree<std::_Tset_traits<Jot::CGraphDiffOperation *,std::less<Jot::CGraphDiffOperation *>,std::allocator<Jot::CGraphDiffOperation *>,0>>::~_Tree<std::_Tset_traits<Jot::CGraphDiffOperation *,std::less<Jot::CGraphDiffOperation *>,std::allocator<Jot::CGraphDiffOperation *>,0>>(&v179);
  }
  v135 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v135 + 48LL))(v135, L"telemetryBatchDurationMs");
  v136 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  v137 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v136 + 72LL);
  TelemetryBatchDuration = Osf::FluidControlApi::GetTelemetryBatchDuration();
  v137(v136, TelemetryBatchDuration);
  v139 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v139 + 48LL))(v139, L"useDevicePixelRatio");
  v140 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  LOBYTE(v141) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v140 + 64LL))(v140, v141);
  if ( byte_18154C7C8 < 0 )
    v142 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_18154C7C8);
  else
    v142 = byte_18154C7C8 != 0;
  if ( v142 || !v200 )
  {
    v143 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v143 + 48LL))(v143, L"useGenericLoader");
    v144 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    LOBYTE(v145) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v144 + 64LL))(v144, v145);
  }
  v146 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v146 + 48LL))(v146, L"useLoopBrand");
  v147 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  LOBYTE(v148) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v147 + 64LL))(v147, v148);
  v149 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v149 + 48LL))(v149, L"useNewAnimatedSplashScreen");
  v150 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  LOBYTE(v151) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v150 + 64LL))(v150, v151);
  if ( byte_18154C7D8 < 0 )
    v153 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_18154C7D8);
  else
    v153 = byte_18154C7D8 != 0;
  if ( v153 )
  {
    v154 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v154 + 48LL))(v154, L"consoleLogEnabled");
    v155 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    LOBYTE(v156) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v155 + 64LL))(v155, v156);
  }
  if ( Mso::Authentication::IdentityFlights::IsOneAuthEnabled(v152) )
  {
    v157 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v157 + 48LL))(v157, L"useTokenCache");
    v158 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    LOBYTE(v159) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v158 + 64LL))(v158, v159);
  }
  v160 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v160 + 48LL))(v160, L"version");
  v161 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  v162 = *(void (__fastcall **)(__int64, struct tagVARIANT *))(*(_QWORD *)v161 + 56LL);
  v163 = std::_UIntegral_to_buff<wchar_t,unsigned long>(v202, 33);
  std::wstring::wstring(&v179, v163, v202);
  v164 = &v179;
  if ( v180 > 7 )
    v164 = *(struct tagVARIANT **)&v179.vt;
  v162(v161, v164);
  std::wstring::~wstring(&v179);
  if ( byte_18154C7B8 < 0 )
    v165 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_18154C7B8);
  else
    v165 = byte_18154C7B8 != 0;
  if ( v165 )
  {
    v166 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v166 + 48LL))(v166, L"invokeBotResponse");
    v167 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
    v168 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v167 + 56LL);
    v169 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *, _BYTE *))(*(_QWORD *)a2 + 328LL))(
                       a2,
                       v201);
    if ( v169[3] > 7u )
      v169 = (_QWORD *)*v169;
    v168(v167, v169);
    std::wstring::~wstring(v201);
  }
  v170 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v170 + 24LL))(v170);
  v171 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v175);
  (*(void (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v171 + 120LL))(v171, v185);
  v179.vt = 3;
  v179.lVal = 0;
  Osf::CSafeArrayWriter::SetElementAtIndex((Osf::CSafeArrayWriter *)&v177, 0, &v179);
  v173 = (const wchar_t *)v185;
  if ( si128.m128i_i64[1] > 7uLL )
    v173 = v185[0];
  Osf::CSafeArrayWriter::SetStringAtIndex((Osf::CSafeArrayWriter *)&v177, v172, v173);
  (*(void (__fastcall **)(struct IExecuteArgumentSet *, __int64))(*(_QWORD *)a1 + 136LL))(a1, v177);
  (*(void (__fastcall **)(struct IExecuteArgumentSet *, _QWORD))(*(_QWORD *)a1 + 80LL))(a1, 0);
  (*(void (__fastcall **)(struct IExecuteArgumentSet *))(*(_QWORD *)a1 + 24LL))(a1);
  Mso::TCntPtr<RequestIt::RequestThrottledError>::~TCntPtr<RequestIt::RequestThrottledError>(&v178);
  std::wstring::~wstring(v187);
  std::string::~string(v181);
  std::wstring::~wstring(v188);
  std::string::~string(v183);
  Osf::LoopInfo::~LoopInfo((Osf::LoopInfo *)v191);
  std::wstring::~wstring(v189);
  std::wstring::~wstring(v190);
  std::wstring::~wstring(v185);
  v174 = v175;
  if ( v175 )
  {
    v175 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v174 + 8LL))(v174);
  }
}

```

## disassembly

```asm
0x180f776a4  mov     [rsp-8+arg_10], rbx
0x180f776a9  push    rbp
0x180f776aa  push    rsi
0x180f776ab  push    rdi
0x180f776ac  push    r12
0x180f776ae  push    r13
0x180f776b0  push    r14
0x180f776b2  push    r15
0x180f776b4  lea     rbp, [rsp-1C0h]
0x180f776bc  sub     rsp, 2C0h
0x180f776c3  mov     rax, cs:__security_cookie
0x180f776ca  xor     rax, rsp
0x180f776cd  mov     [rbp+1F0h+var_40], rax
0x180f776d4  mov     rsi, rdx
0x180f776d7  mov     r14, rcx
0x180f776da  lea     rcx, [rsp+2F0h+var_2B0]; this
0x180f776df  call    ??0CSafeArrayWriter@Osf@@QEAA@JJ@Z; Osf::CSafeArrayWriter::CSafeArrayWriter(long,long)
0x180f776e4  lea     rcx, [rsp+2F0h+var_2C0]
0x180f776e9  call    cs:__imp_?CreateJsonWriter@Json@Mso@@YA?AV?$TCntPtr@UIJsonWriter@Json@Mso@@@2@XZ; Mso::Json::CreateJsonWriter(void)
0x180f776ef  xorps   xmm0, xmm0
0x180f776f2  movups  xmmword ptr [rbp+1F0h+var_240], xmm0
0x180f776f6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180f776fe  movdqu  [rbp+1F0h+var_230], xmm1
0x180f77703  xor     r13d, r13d
0x180f77706  mov     word ptr [rbp+1F0h+var_240], r13w
0x180f7770b  mov     rax, [rsi]
0x180f7770e  mov     rcx, rsi
0x180f77711  mov     rax, [rax+88h]
0x180f77718  call    cs:__guard_dispatch_icall_fptr
0x180f7771e  movsxd  rdi, eax
0x180f77721  mov     rcx, [rsi]
0x180f77724  mov     rax, [rcx+90h]
0x180f7772b  mov     rcx, rsi
0x180f7772e  call    cs:__guard_dispatch_icall_fptr
0x180f77734  mov     r15b, al
0x180f77737  mov     rcx, [rsi]
0x180f7773a  mov     rax, [rcx+80h]
0x180f77741  lea     rdx, [rbp+1F0h+var_1C0]
0x180f77745  mov     rcx, rsi
0x180f77748  call    cs:__guard_dispatch_icall_fptr
0x180f7774e  mov     rcx, [rsi]
0x180f77751  mov     rax, [rcx+0C0h]
0x180f77758  mov     rcx, rsi
0x180f7775b  call    cs:__guard_dispatch_icall_fptr
0x180f77761  mov     bl, al
0x180f77763  mov     rcx, [rsi]
0x180f77766  mov     rax, [rcx]
0x180f77769  mov     rcx, rsi
0x180f7776c  call    cs:__guard_dispatch_icall_fptr
0x180f77772  mov     r12b, al
0x180f77775  mov     rcx, [rsi]
0x180f77778  mov     rax, [rcx+8]
0x180f7777c  lea     rdx, [rbp+1F0h+var_1E0]
0x180f77780  mov     rcx, rsi
0x180f77783  call    cs:__guard_dispatch_icall_fptr
0x180f77789  mov     rcx, [rsi]
0x180f7778c  mov     rax, [rcx+98h]
0x180f77793  mov     rcx, rsi
0x180f77796  call    cs:__guard_dispatch_icall_fptr
0x180f7779c  mov     rdx, rax; struct Osf::LoopInfo *
0x180f7779f  lea     rcx, [rbp+1F0h+var_1A0]; this
0x180f777a3  call    ??0LoopInfo@Osf@@QEAA@AEBU01@@Z; Osf::LoopInfo::LoopInfo(Osf::LoopInfo const &)
0x180f777a8  lea     rcx, [rsp+2F0h+var_2C0]
0x180f777ad  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f777b2  mov     rdx, rax
0x180f777b5  mov     rcx, [rax]
0x180f777b8  mov     rax, [rcx+10h]
0x180f777bc  mov     rcx, rdx
0x180f777bf  call    cs:__guard_dispatch_icall_fptr
0x180f777c5  lea     rcx, [rbp+1F0h+var_260]
0x180f777c9  call    cs:__imp_?GetAudienceGroup@AudienceApi@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Mso::AudienceApi::GetAudienceGroup(void)
0x180f777cf  lea     r8, [rbp+1F0h+var_260]
0x180f777d3  cmp     [rbp+1F0h+var_248], 0Fh
0x180f777d8  cmova   r8, [rbp+1F0h+var_260]
0x180f777dd  add     r8, [rbp+1F0h+var_250]
0x180f777e1  lea     rdx, [rbp+1F0h+var_260]
0x180f777e5  cmp     [rbp+1F0h+var_248], 0Fh
0x180f777ea  cmova   rdx, [rbp+1F0h+var_260]
0x180f777ef  lea     rcx, [rbp+1F0h+var_200]
0x180f777f3  call    ??$?0V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@1@0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::allocator<wchar_t> const &)
0x180f777f8  lea     rcx, [rsp+2F0h+var_2C0]
0x180f777fd  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77802  mov     r8, rax
0x180f77805  mov     rcx, [rax]
0x180f77808  mov     rax, [rcx+30h]
0x180f7780c  lea     rdx, aAudiencegroup; "audienceGroup"
0x180f77813  mov     rcx, r8
0x180f77816  call    cs:__guard_dispatch_icall_fptr
0x180f7781c  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77821  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77826  mov     r8, rax
0x180f77829  mov     rcx, [rax]
0x180f7782c  mov     rax, [rcx+38h]
0x180f77830  lea     rdx, [rbp+1F0h+var_200]
0x180f77834  cmp     [rbp+1F0h+var_1E8], 7
0x180f77839  cmova   rdx, [rbp+1F0h+var_200]
0x180f7783e  mov     rcx, r8
0x180f77841  call    cs:__guard_dispatch_icall_fptr
0x180f77847  lea     rcx, [rsp+2F0h+var_280]
0x180f7784c  call    cs:__imp_?GetChannel@AudienceApi@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Mso::AudienceApi::GetChannel(void)
0x180f77852  lea     r8, [rsp+2F0h+var_280]
0x180f77857  cmp     [rbp+1F0h+var_268], 0Fh
0x180f7785c  cmova   r8, [rsp+2F0h+var_280]
0x180f77862  add     r8, [rbp+1F0h+var_270]
0x180f77866  lea     rdx, [rsp+2F0h+var_280]
0x180f7786b  cmp     [rbp+1F0h+var_268], 0Fh
0x180f77870  cmova   rdx, [rsp+2F0h+var_280]
0x180f77876  lea     rcx, [rbp+1F0h+var_220]
0x180f7787a  call    ??$?0V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@1@0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::allocator<wchar_t> const &)
0x180f7787f  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77884  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77889  mov     r8, rax
0x180f7788c  mov     rcx, [rax]
0x180f7788f  mov     rax, [rcx+30h]
0x180f77893  lea     rdx, aChannel; "channel"
0x180f7789a  mov     rcx, r8
0x180f7789d  call    cs:__guard_dispatch_icall_fptr
0x180f778a3  lea     rcx, [rsp+2F0h+var_2C0]
0x180f778a8  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f778ad  mov     r8, rax
0x180f778b0  mov     rcx, [rax]
0x180f778b3  mov     rax, [rcx+38h]
0x180f778b7  lea     rdx, [rbp+1F0h+var_220]
0x180f778bb  cmp     [rbp+1F0h+var_208], 7
0x180f778c0  cmova   rdx, [rbp+1F0h+var_220]
0x180f778c5  mov     rcx, r8
0x180f778c8  call    cs:__guard_dispatch_icall_fptr
0x180f778ce  lea     rcx, [rsp+2F0h+var_2C0]
0x180f778d3  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f778d8  mov     r8, rax
0x180f778db  mov     rcx, [rax]
0x180f778de  mov     rax, [rcx+30h]
0x180f778e2  lea     rdx, aEnablerighttol; "enableRightToLeftSplashScreen"
0x180f778e9  mov     rcx, r8
0x180f778ec  call    cs:__guard_dispatch_icall_fptr
0x180f778f2  lea     rcx, [rsp+2F0h+var_2C0]
0x180f778f7  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f778fc  mov     r8, rax
0x180f778ff  mov     rcx, [rax]
0x180f77902  mov     rax, [rcx+40h]
0x180f77906  mov     dl, 1
0x180f77908  mov     rcx, r8
0x180f7790b  call    cs:__guard_dispatch_icall_fptr
0x180f77911  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77916  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f7791b  mov     r8, rax
0x180f7791e  mov     rcx, [rax]
0x180f77921  mov     rax, [rcx+30h]
0x180f77925  lea     rdx, aEnableshowloop; "enableShowLoopGlowBorderEvent"
0x180f7792c  mov     rcx, r8
0x180f7792f  call    cs:__guard_dispatch_icall_fptr
0x180f77935  lea     rcx, [rsp+2F0h+var_2C0]
0x180f7793a  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f7793f  mov     r8, rax
0x180f77942  mov     rcx, [rax]
0x180f77945  mov     rax, [rcx+40h]
0x180f77949  mov     dl, 1
0x180f7794b  mov     rcx, r8
0x180f7794e  call    cs:__guard_dispatch_icall_fptr
0x180f77954  mov     edx, 1E14B6A3h
0x180f77959  mov     r8d, 166h
0x180f7795f  lea     rcx, [rsp+2F0h+var_2A8]
0x180f77964  call    cs:__imp_?CreateConfigUrlBuilder@OfficeWebServiceApi@Mso@@YA?AV?$TCntPtr@UIUrlBuilder@OfficeWebServiceApi@Mso@@@2@VMsoReserveTag@@W4URL@ConfigURL@12@@Z; Mso::OfficeWebServiceApi::CreateConfigUrlBuilder(MsoReserveTag,Mso::OfficeWebServiceApi::ConfigURL::URL)
0x180f7796a  cmp     [rsp+2F0h+var_2A8], r13
0x180f7796f  jz      loc_180F779FE
0x180f77975  lea     rcx, [rsp+2F0h+var_2A8]
0x180f7797a  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f7797f  mov     rdx, rax
0x180f77982  mov     rcx, [rax]
0x180f77985  mov     rax, [rcx+0A0h]
0x180f7798c  mov     rcx, rdx
0x180f7798f  call    cs:__guard_dispatch_icall_fptr
0x180f77995  mov     rdx, rax
0x180f77998  lea     rcx, [rsp+2F0h+var_2A0]
0x180f7799d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180f779a2  lea     rcx, [rsp+2F0h+var_2C0]
0x180f779a7  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f779ac  mov     r8, rax
0x180f779af  mov     rcx, [rax]
0x180f779b2  mov     rax, [rcx+30h]
0x180f779b6  lea     rdx, aGraphendpoint; "graphEndpoint"
0x180f779bd  mov     rcx, r8
0x180f779c0  call    cs:__guard_dispatch_icall_fptr
0x180f779c6  lea     rcx, [rsp+2F0h+var_2C0]
0x180f779cb  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f779d0  mov     r8, rax
0x180f779d3  mov     rcx, [rax]
0x180f779d6  mov     rax, [rcx+38h]
0x180f779da  lea     rdx, [rsp+2F0h+var_2A0]
0x180f779df  cmp     [rsp+2F0h+var_288], 7
0x180f779e5  cmova   rdx, qword ptr [rsp+2F0h+var_2A0]
0x180f779eb  mov     rcx, r8
0x180f779ee  call    cs:__guard_dispatch_icall_fptr
0x180f779f4  lea     rcx, [rsp+2F0h+var_2A0]; void *
0x180f779f9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180f779fe  mov     ecx, cs:_tls_index
0x180f77a04  mov     rax, gs:58h
0x180f77a0d  mov     edx, 10h
0x180f77a12  mov     rax, [rax+rcx*8]
0x180f77a16  mov     eax, [rdx+rax]
0x180f77a19  cmp     cs:dword_1815BAC20, eax
0x180f77a1f  jle     short loc_180F77AA0
0x180f77a21  lea     rcx, dword_1815BAC20
0x180f77a28  call    _Init_thread_header
0x180f77a2d  cmp     cs:dword_1815BAC20, 0FFFFFFFFh
0x180f77a34  jnz     short loc_180F77AA0
0x180f77a36  lea     rdx, WindowName
0x180f77a3d  lea     rcx, [rbp+1F0h+var_70]
0x180f77a44  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180f77a49  lea     rax, aFluidhostFluid; "FluidHost.FluidSettingOverrides"
0x180f77a50  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180f77a55  mov     [rsp+2F0h+var_2B8], 34h ; '4'
0x180f77a5a  mov     [rsp+2F0h+var_2D0], r13
0x180f77a5f  lea     r9, [rbp+1F0h+var_70]
0x180f77a66  lea     r8, [rsp+2F0h+var_2A0]
0x180f77a6b  lea     rdx, [rsp+2F0h+var_2B8]
0x180f77a70  lea     rcx, qword_1815BAC30
0x180f77a77  call    ??0?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Optimized@AB@Mso@@QEAA@AEBW4TeamEnum@23@AEBV?$StringLiteral@D@StringLiterals@3@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@P6A?BU?$pair@PEBU?$pair@VScopeEnum@AB@Mso@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEBU12@@8@X_E@Z; Mso::AB::Optimized::Setting<std::wstring>::Setting<std::wstring>(Mso::AB::TeamEnum const &,Mso::StringLiterals::StringLiteral<char> const &,std::wstring &&,std::pair<std::pair<Mso::AB::ScopeEnum,std::wstring> const *,std::pair<Mso::AB::ScopeEnum,std::wstring> const *> const (*)(void),...)
0x180f77a7c  lea     rcx, [rbp+1F0h+var_70]; void *
0x180f77a83  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180f77a88  lea     rcx, sub_1808B8AC0; void (__cdecl *)()
0x180f77a8f  call    atexit
0x180f77a94  lea     rcx, dword_1815BAC20
0x180f77a9b  call    _Init_thread_footer
0x180f77aa0  lea     rcx, qword_1815BAC30
0x180f77aa7  call    ??B?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Optimized@AB@Mso@@QEGBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::AB::Optimized::Setting<std::wstring>::operator std::wstring const &(void)
0x180f77aac  cmp     [rax+10h], r13
0x180f77ab0  jz      loc_180F77B4C
0x180f77ab6  lea     rcx, qword_1815BAC30
0x180f77abd  call    ??B?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Optimized@AB@Mso@@QEGBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::AB::Optimized::Setting<std::wstring>::operator std::wstring const &(void)
0x180f77ac2  cmp     qword ptr [rax+18h], 7
0x180f77ac7  jbe     short loc_180F77ACC
0x180f77ac9  mov     rax, [rax]
0x180f77acc  mov     rcx, rax; wchar_t *
0x180f77acf  call    ?IsValidJson@FluidControlApi@Osf@@CA_NPEB_W@Z; Osf::FluidControlApi::IsValidJson(wchar_t const *)
0x180f77ad4  test    al, al
0x180f77ad6  jz      short loc_180F77B21
0x180f77ad8  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77add  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77ae2  mov     r8, rax
0x180f77ae5  mov     rcx, [rax]
0x180f77ae8  mov     rax, [rcx+30h]
0x180f77aec  lea     rdx, aFluidsettingov; "fluidSettingOverrides"
0x180f77af3  mov     rcx, r8
0x180f77af6  call    cs:__guard_dispatch_icall_fptr
0x180f77afc  lea     rcx, qword_1815BAC30
0x180f77b03  call    ??B?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Optimized@AB@Mso@@QEGBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::AB::Optimized::Setting<std::wstring>::operator std::wstring const &(void)
0x180f77b08  cmp     qword ptr [rax+18h], 7
0x180f77b0d  jbe     short loc_180F77B12
0x180f77b0f  mov     rax, [rax]
0x180f77b12  mov     rdx, rax
0x180f77b15  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77b1a  call    ?WriteJson@FluidControlApi@Osf@@CAXAEBV?$TCntPtr@UIJsonWriter@Json@Mso@@@Mso@@PEB_W@Z; Osf::FluidControlApi::WriteJson(Mso::TCntPtr<Mso::Json::IJsonWriter> const &,wchar_t const *)
0x180f77b1f  jmp     short loc_180F77B4C
0x180f77b21  lea     rax, aInvalidJsonFor; "Invalid json for OEP.FluidHost.FluidSet"...
0x180f77b28  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180f77b2d  lea     rax, [rsp+2F0h+var_2A0]
0x180f77b32  mov     [rsp+2F0h+var_2D0], rax
0x180f77b37  mov     edx, 9B9h
0x180f77b3c  mov     ecx, 1E89B0E3h
0x180f77b41  mov     r8d, 0Ah
0x180f77b47  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x180f77b4c  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77b51  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77b56  mov     r8, rax
0x180f77b59  mov     rcx, [rax]
0x180f77b5c  mov     rax, [rcx+30h]
0x180f77b60  lea     rdx, aHost; "host"
0x180f77b67  mov     rcx, r8
0x180f77b6a  call    cs:__guard_dispatch_icall_fptr
0x180f77b70  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77b75  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77b7a  mov     r8, rax
0x180f77b7d  mov     rcx, [rax]
0x180f77b80  mov     rax, [rcx+38h]
0x180f77b84  lea     rdx, aFluidcontrolap; "fluidControlApi"
0x180f77b8b  mov     rcx, r8
0x180f77b8e  call    cs:__guard_dispatch_icall_fptr
0x180f77b94  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77b99  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77b9e  mov     r8, rax
0x180f77ba1  mov     rcx, [rax]
0x180f77ba4  mov     rax, [rcx+30h]
0x180f77ba8  lea     rdx, aHydrateid_0; "hydrateId"
0x180f77baf  mov     rcx, r8
0x180f77bb2  call    cs:__guard_dispatch_icall_fptr
0x180f77bb8  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77bbd  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77bc2  mov     r8, rax
0x180f77bc5  mov     rcx, [rax]
0x180f77bc8  mov     rax, [rcx+38h]
0x180f77bcc  lea     rdx, [rbp+1F0h+var_1C0]
0x180f77bd0  cmp     [rbp+1F0h+var_1A8], 7
0x180f77bd5  cmova   rdx, [rbp+1F0h+var_1C0]
0x180f77bda  mov     rcx, r8
0x180f77bdd  call    cs:__guard_dispatch_icall_fptr
0x180f77be3  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77be8  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77bed  mov     r8, rax
0x180f77bf0  mov     rcx, [rax]
  ... truncated ...
```
