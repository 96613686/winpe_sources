# RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance::AdjustEnforcementByJit(DlpActionType,wchar_t const *,wchar_t const *,PPID const &,ulong const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong,wchar_t const *,wchar_t const *,ulong,uchar *,bool,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,DlpEnforcementLevel &,_DLP_JIT_SYNC_CLASSIFICATION_REASON &,DlpEnforcementLevel,bool,std::optional<RealtimeProtection::FileEvaluationContext> &&)

- ea: `0x180046db0`
- end: `0x1800489dc`
- name: `?AdjustEnforcementByJit@DlpJitStateMachineInstance@DlpJitStateMachine@RealtimeProtection@@QEAAJW4DlpActionType@@PEB_W1AEBUPPID@@AEBKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K11KPEAE_NAEAV67@AEAW4DlpEnforcementLevel@@AEAW4_DLP_JIT_SYNC_CLASSIFICATION_REASON@@W48@6$$QEAV?$optional@UFileEvaluationContext@RealtimeProtection@@@7@@Z`
- size: `7212`
- prototype: ``
- caller_count: `1`
- callee_count: `55`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800489dc`

## callees

- `0x1800058a4`
- `0x18001a444`
- `0x180028a10`
- `0x180028d80`
- `0x180029590`
- `0x18002e3e4`
- `0x18002e484`
- `0x18002ece0`
- `0x18002f970`
- `0x1800301a0`
- `0x180034420`
- `0x180038450`
- `0x1800399c0`
- `0x18003ea30`
- `0x18003eb14`
- `0x180046db0`
- `0x18004b3bc`
- `0x18005759c`
- `0x180069a7c`
- `0x180080030`
- `0x1800809d0`
- `0x180087f60`
- `0x18008ad00`
- `0x1800943fc`
- `0x180097340`
- `0x18009d648`
- `0x18009f730`
- `0x1800a4378`
- `0x1800b33b8`
- `0x1800b6228`
- `0x1800bb288`
- `0x1800bbc64`
- `0x1800bd370`
- `0x180106b64`
- `0x18010b558`
- `0x18010b568`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18010d5dc`
- `0x180119428`
- `0x1801459c8`
- `0x18014f16c`
- `0x18016a258`
- `0x18016a99c`
- `0x180178ba8`
- `0x18017e1a0`
- `0x18017e594`
- `0x1801d532c`
- `0x18020b8d8`
- `0x18020cd94`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x180047557`
- `KERNEL32!AcquireSRWLockShared` at `0x180047c2e`
- `KERNEL32!AcquireSRWLockShared` at `0x180047557`
- `KERNEL32!AcquireSRWLockShared` at `0x180047c2e`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800475c3`
- `KERNEL32!ReleaseSRWLockShared` at `0x18004766c`
- `KERNEL32!ReleaseSRWLockShared` at `0x180047c58`
- `KERNEL32!ReleaseSRWLockShared` at `0x180047cb5`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800475c3`
- `KERNEL32!ReleaseSRWLockShared` at `0x18004766c`
- `KERNEL32!ReleaseSRWLockShared` at `0x180047c58`
- `KERNEL32!ReleaseSRWLockShared` at `0x180047cb5`
- `ADVAPI32!EventWriteTransfer` at `0x180047782`
- `ADVAPI32!EventWriteTransfer` at `0x180047782`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance::AdjustEnforcementByJit(
        RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance *a1,
        int a2,
        wchar_t *a3,
        wchar_t *a4,
        __int64 *a5,
        _DWORD *a6,
        wchar_t *a7,
        char a8,
        const wchar_t *a9,
        __int64 a10,
        unsigned int a11,
        unsigned __int8 *a12,
        char a13,
        ULONGLONG *a14,
        int *a15,
        _DWORD *a16,
        int a17,
        char a18,
        __int64 a19)
{
  wchar_t *v19; // r13
  __int64 v20; // r12
  unsigned __int8 *v21; // rdi
  wchar_t *v22; // rax
  int JitFeaturesForUser; // ebx
  PVOID *v24; // rcx
  __int64 result; // rax
  int v26; // esi
  ULONGLONG v27; // rax
  _QWORD *Instance; // rax
  char IsJitCandidatePolicy; // bl
  void *v30; // rax
  __int64 v31; // rbx
  unsigned __int8 *v32; // r8
  bool v33; // bl
  char Value; // al
  char v35; // r11
  EndpointDlp::endpointDlpImpl **v36; // rax
  __int64 v37; // rdx
  bool IsDlpEnabledForFile; // bl
  __int64 v39; // r8
  ULONGLONG Keyword; // rcx
  std::_Ref_count_base *v41; // rbx
  __int64 *v42; // rdi
  unsigned int *v43; // r9
  unsigned int v44; // edi
  int MiscDwordValue; // eax
  const char *v46; // rax
  const char *v47; // rdx
  __int64 v48; // r8
  char ShouldReclassifyFile; // bl
  const struct std::nothrow_t *v50; // rdx
  _BYTE *v51; // r8
  unsigned __int64 ClassificationTimeFromEA; // r13
  wchar_t *v53; // rdi
  unsigned __int8 *v54; // r8
  const wchar_t *v55; // r8
  int v56; // esi
  unsigned int v57; // r15d
  const WCHAR *v58; // rdx
  int v59; // eax
  unsigned int v60; // ebx
  unsigned int v61; // r12d
  void *v62; // r15
  __int64 v63; // rbx
  __int64 v64; // rsi
  RTL_SRWLOCK *v65; // rdi
  const struct EndpointDlp::Telemetry::SyncClassificationEvent *v66; // rdx
  struct EndpointDlp::TraceLoggingProvider *v67; // rax
  int v68; // edx
  __int64 v69; // r8
  __int64 v70; // r9
  _DWORD *v71; // rcx
  int v72; // ebx
  struct EndpointDlp::TraceLoggingProvider *v73; // rax
  _DWORD *v74; // rcx
  int v75; // ebx
  char v76; // dl
  const wchar_t *v77; // rbx
  EndpointDlp::endpointDlpImpl **v78; // rax
  unsigned __int8 *v79; // r12
  int IsSyncClassificationRequired; // ebx
  int v81; // ecx
  char v82; // dl
  EndpointDlp::endpointDlpImpl **v83; // rax
  unsigned __int8 *v84; // r9
  unsigned int v85; // r12d
  int IsClassificationOutdated; // ebx
  void *v87; // rax
  _QWORD *v88; // rax
  char v89; // bl
  unsigned __int8 *v90; // r8
  bool v91; // zf
  __int64 v92; // rdi
  int v93; // r12d
  __int64 v94; // rax
  struct EndpointDlp::TraceLoggingProvider *v95; // rax
  __int64 v96; // r8
  __int64 v97; // r9
  _DWORD *v98; // rcx
  int v99; // ecx
  int v100; // esi
  int ActionsByPolicyType; // eax
  int v102; // r8d
  int JitFileCloudApplicationPolicy; // ebx
  PVOID *v104; // r10
  int v105; // edi
  const wchar_t *v106; // r12
  int v107; // r15d
  EVENT_DESCRIPTOR *p_EventDescriptor; // rbx
  int v109; // edi
  const wchar_t *v110; // rdx
  int v111; // r8d
  bool v112; // r15
  int v113; // esi
  int v114; // r12d
  int v115; // eax
  bool v116; // al
  __int16 v117; // r12
  bool v118; // zf
  char v119; // r15
  bool v120; // si
  const wchar_t *v121; // r8
  PVOID *v122; // rcx
  const wchar_t *v123; // rdx
  _QWORD *v124; // rax
  char IsJITActionNeedToClassify; // si
  const char *v126; // r8
  const char *v127; // rax
  _QWORD *v128; // r12
  const WCHAR *v129; // rdx
  int v130; // eax
  ULONGLONG v131; // rcx
  int SyncClassificationEvent; // eax
  unsigned int v133; // edi
  const wchar_t *v134; // rcx
  struct _EVENT_DATA_DESCRIPTOR *v135; // rbx
  int v136; // esi
  const wchar_t *v137; // rdx
  int v138; // r8d
  PVOID *v139; // rcx
  int v140; // eax
  unsigned int v141; // ecx
  unsigned int v142; // eax
  int v143; // ecx
  char v144; // si
  wchar_t *v145; // rdx
  int v146; // eax
  PVOID *v147; // rcx
  char UserDataCounta; // [rsp+20h] [rbp-388h]
  ULONG UserDataCount[2]; // [rsp+20h] [rbp-388h]
  PEVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-380h]
  char v151[8]; // [rsp+30h] [rbp-378h]
  __int64 v152; // [rsp+38h] [rbp-370h]
  char v153; // [rsp+70h] [rbp-338h]
  bool v154; // [rsp+71h] [rbp-337h]
  char v155[4]; // [rsp+74h] [rbp-334h] BYREF
  char v156[4]; // [rsp+78h] [rbp-330h]
  char IsJitRuleId; // [rsp+7Ch] [rbp-32Ch]
  const wchar_t *v158; // [rsp+80h] [rbp-328h] BYREF
  unsigned int v159; // [rsp+88h] [rbp-320h]
  unsigned int v160; // [rsp+8Ch] [rbp-31Ch]
  unsigned int v161; // [rsp+90h] [rbp-318h] BYREF
  wchar_t *v162; // [rsp+98h] [rbp-310h]
  __int64 *v163; // [rsp+A0h] [rbp-308h]
  wchar_t *v164; // [rsp+A8h] [rbp-300h]
  RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance *v165; // [rsp+B0h] [rbp-2F8h]
  void *v166; // [rsp+B8h] [rbp-2F0h] BYREF
  std::_Ref_count_base *v167; // [rsp+C0h] [rbp-2E8h]
  __int64 v168; // [rsp+C8h] [rbp-2E0h]
  unsigned __int64 v169; // [rsp+D0h] [rbp-2D8h]
  int v170; // [rsp+D8h] [rbp-2D0h] BYREF
  __int64 v171; // [rsp+E0h] [rbp-2C8h]
  __int64 v172; // [rsp+E8h] [rbp-2C0h]
  __int64 v173; // [rsp+F0h] [rbp-2B8h]
  _DWORD *v174; // [rsp+F8h] [rbp-2B0h]
  int *v175; // [rsp+100h] [rbp-2A8h]
  const wchar_t *v176; // [rsp+108h] [rbp-2A0h]
  __int64 v177; // [rsp+110h] [rbp-298h]
  void *v178; // [rsp+118h] [rbp-290h]
  wchar_t *v179; // [rsp+120h] [rbp-288h]
  wchar_t *v180; // [rsp+128h] [rbp-280h]
  _DWORD *v181; // [rsp+130h] [rbp-278h]
  _BYTE v182[32]; // [rsp+138h] [rbp-270h] BYREF
  char v183; // [rsp+158h] [rbp-250h]
  unsigned int v184; // [rsp+168h] [rbp-240h] BYREF
  char v185[4]; // [rsp+16Ch] [rbp-23Ch] BYREF
  unsigned __int8 *v186; // [rsp+170h] [rbp-238h] BYREF
  void *Block; // [rsp+178h] [rbp-230h] BYREF
  std::_Ref_count_base *v188; // [rsp+180h] [rbp-228h]
  _BYTE v189[32]; // [rsp+188h] [rbp-220h] BYREF
  _QWORD v190[3]; // [rsp+1A8h] [rbp-200h] BYREF
  unsigned __int64 v191; // [rsp+1C0h] [rbp-1E8h]
  char v192; // [rsp+1C8h] [rbp-1E0h]
  _BYTE v193[272]; // [rsp+1D0h] [rbp-1D8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+2E0h] [rbp-C8h] BYREF
  char v195; // [rsp+300h] [rbp-A8h]
  struct _EVENT_DATA_DESCRIPTOR v196; // [rsp+310h] [rbp-98h] BYREF
  unsigned __int64 v197; // [rsp+320h] [rbp-88h]
  __int64 v198; // [rsp+328h] [rbp-80h]
  _QWORD v199[4]; // [rsp+330h] [rbp-78h] BYREF
  char v200; // [rsp+350h] [rbp-58h]
  __int64 v201; // [rsp+358h] [rbp-50h]

  v164 = a4;
  v19 = a3;
  v162 = a3;
  *(_DWORD *)v156 = a2;
  v165 = a1;
  v176 = a9;
  v170 = a2;
  v179 = a3;
  v180 = a4;
  v163 = a5;
  v174 = a6;
  v20 = (__int64)a7;
  v171 = (__int64)a7;
  v172 = a10;
  v21 = a12;
  v186 = a12;
  v178 = a14;
  v175 = a15;
  v181 = a16;
  v177 = a19;
  v160 = 0;
  v159 = 0;
  *a16 = 0;
  *(_DWORD *)v185 = 0;
  v173 = *a5;
  *(_DWORD *)v155 = 0;
  v22 = a7;
  if ( *((_QWORD *)a7 + 3) > 7u )
    v22 = *(wchar_t **)a7;
  *(_QWORD *)&EventDescriptor.Id = v22;
  EventDescriptor.Keyword = *((_QWORD *)a7 + 2);
  JitFeaturesForUser = EndpointDlp::Client::GetJitFeaturesForUser(&EventDescriptor, v155);
  if ( JitFeaturesForUser < 0 )
  {
    v24 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        if ( *((_QWORD *)a7 + 3) > 7u )
          v20 = *(_QWORD *)a7;
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)&WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
          v20,
          (__int64)v19);
        v24 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 )
        WPP_SF_d(v24[2], 11, &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids, (unsigned int)JitFeaturesForUser);
    }
    return (unsigned int)JitFeaturesForUser;
  }
  IsJitRuleId = RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance::IsJitRuleId(a14);
  if ( IsJitRuleId )
    v26 = 0;
  else
    v26 = *a15;
  v161 = *v175;
  v153 = 0;
  v154 = 0;
  if ( (Dlp::FeatureControl::GetValue(85) & 4) != 0 )
  {
    std::wstring::wstring(v189, v19);
    v159 = 1;
    if ( !(unsigned __int8)EndpointDlp::Client::IsPathFromOutlookInetCache(v189) )
      goto LABEL_34;
    v27 = (ULONGLONG)a14;
    if ( a14[3] > 7 )
      v27 = *a14;
    *(_QWORD *)&EventDescriptor.Id = v27;
    EventDescriptor.Keyword = a14[2];
    Instance = (_QWORD *)EndpointDlp::endpointDlpImpl::GetInstance(&Block);
    IsJitCandidatePolicy = EndpointDlp::endpointDlpImpl::IsJitCandidatePolicy(*Instance, &EventDescriptor, 0);
    if ( v188 )
      std::_Ref_count_base::_Decref(v188);
    if ( IsJitCandidatePolicy )
      goto LABEL_33;
    v30 = a14;
    if ( a14[3] > 7 )
      v30 = (void *)*a14;
    Block = v30;
    v188 = (std::_Ref_count_base *)a14[2];
    v31 = *(_QWORD *)EndpointDlp::endpointDlpImpl::GetInstance(&EventDescriptor);
    v33 = (unsigned __int8)EndpointDlp::endpointDlpImpl::IsJitAsyncClassificationPolicy(v31, &Block)
       || (unsigned __int8)EndpointDlp::endpointDlpImpl::IsJitCandidatePolicy(v31, &Block, 0);
    if ( EventDescriptor.Keyword )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)EventDescriptor.Keyword);
    if ( v33 || EndpointDlp::Client::IsFileConsiderNoEA((EndpointDlp::Client *)a11, (unsigned int)a12, v32) )
LABEL_33:
      v153 = 1;
    else
LABEL_34:
      v153 = 0;
    v160 = 0;
    v159 = 0;
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v189);
  }
  Value = Dlp::FeatureControl::GetValue(261);
  v35 = v156[0];
  if ( (Value & 2) != 0 && *(_DWORD *)v156 == 6 )
  {
    v36 = (EndpointDlp::endpointDlpImpl **)EndpointDlp::endpointDlpImpl::GetInstance(&EventDescriptor);
    IsDlpEnabledForFile = EndpointDlp::endpointDlpImpl::IsDlpEnabledForFile(*v36, v19);
    Keyword = EventDescriptor.Keyword;
    if ( EventDescriptor.Keyword )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)EventDescriptor.Keyword);
    if ( !IsDlpEnabledForFile )
    {
      Lock_shared_ptr_spin_lock(Keyword, v37, v39);
      v41 = qword_180314278;
      if ( qword_180314278 )
      {
        _InterlockedIncrement((volatile signed __int32 *)qword_180314278 + 2);
        v41 = qword_180314278;
      }
      v42 = (__int64 *)qword_180314270;
      Unlock_shared_ptr_spin_lock();
      if ( v42 )
      {
        if ( !*((_QWORD *)a7 + 2)
          || (std::_Tree<std::_Tmap_traits<std::wstring,EndpointDlp::Policy::UserConfig::DlpUserConfiguration::UserData,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::pair<std::wstring const,EndpointDlp::Policy::UserConfig::DlpUserConfiguration::UserData>>,0>>::find(
                v42,
                &Block,
                a7),
              Block == (void *)*v42) )
        {
          v44 = 0;
        }
        else
        {
          v44 = *((_DWORD *)Block + 22);
        }
        if ( v41 )
          std::_Ref_count_base::_Decref(v41);
      }
      else
      {
        if ( v41 )
          std::_Ref_count_base::_Decref(v41);
        v44 = 0;
      }
      v184 = 0;
      MiscDwordValue = RealtimeProtection::DlpUtils::DlpGetMiscDwordValue(
                         (RealtimeProtection::DlpUtils *)L"MpDlp_ExclusionProtectionEnforcementMode",
                         0,
                         (unsigned int)&v184,
                         v43);
      if ( MiscDwordValue >= 0 && MiscDwordValue != 1 )
        v44 = v184;
      v154 = v44 == 2;
      v21 = v186;
    }
    v35 = v156[0];
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v46 = L"true";
    if ( a11 )
      v46 = L"false";
    v47 = L"true";
    if ( !IsJitRuleId )
      v47 = L"false";
    v48 = (__int64)a7;
    if ( *((_QWORD *)a7 + 3) > 7u )
      v48 = *(_QWORD *)a7;
    WPP_SF_DSSDSSDddS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (__int64)v164,
      (__int64)v19,
      v35,
      v48,
      (__int64)v47,
      v155[0],
      a18,
      v153,
      (__int64)v46);
  }
  *v175 = v26;
  if ( (Dlp::FeatureControl::GetValue(218) & 2) != 0 )
  {
    Block = &EventDescriptor;
    EventDescriptor = 0;
    std::wstring::wstring(&v166, v19);
    ShouldReclassifyFile = EndpointDlp::Client::ShouldReclassifyFile(v21, a11, &v166, &EventDescriptor);
    if ( v169 > 7 )
    {
      v50 = (const struct std::nothrow_t *)(2 * v169 + 2);
      v51 = v166;
      if ( (unsigned __int64)v50 >= 0x1000 )
      {
        v50 = (const struct std::nothrow_t *)(2 * v169 + 41);
        v51 = (_BYTE *)*((_QWORD *)v166 - 1);
        if ( (unsigned __int64)((_BYTE *)v166 - v51 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v51, v50);
    }
    v168 = 0;
    v169 = 7;
    LOWORD(v166) = 0;
    if ( ShouldReclassifyFile )
    {
      ClassificationTimeFromEA = 0;
      v53 = v162;
      std::wstring::wstring(v189, v162);
      if ( a11 )
      {
        _mm_lfence();
        ClassificationTimeFromEA = EndpointDlp::Client::GetClassificationTimeFromEA(
                                     (EndpointDlp::Client *)a11,
                                     (unsigned int)v186,
                                     v54);
      }
      RealtimeProtection::DlpLRUCache<std::wstring,unsigned __int64>::get((char *)v165 + 88, &EventDescriptor, v189);
      if ( LOBYTE(EventDescriptor.Keyword) && *(_QWORD *)&EventDescriptor.Id == ClassificationTimeFromEA )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          UserDataCounta = ClassificationTimeFromEA;
          v19 = v162;
          WPP_SF_SI(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)&WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
            (_DWORD)v162,
            UserDataCounta);
          v56 = -2147023782;
          v57 = 4;
LABEL_123:
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v189);
          goto LABEL_125;
        }
        v56 = -2147023782;
        v57 = 4;
LABEL_122:
        v19 = v162;
        goto LABEL_123;
      }
      Block = 0;
      v58 = a7;
      if ( *((_QWORD *)a7 + 3) > 7u )
        v58 = *(const WCHAR **)a7;
      v59 = CommonUtil::UtilConvertStringSidToSid((CommonUtil *)&Block, v58, v55);
      v60 = v59;
      if ( v59 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
            (unsigned int)v59);
        if ( Block )
          operator delete(Block);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v189);
        return v60;
      }
      v61 = *((_DWORD *)v163 + 2);
      v62 = Block;
      v63 = -1;
      do
        ++v63;
      while ( v53[v63] );
      v64 = *(_QWORD *)EndpointDlp::endpointDlpImpl::GetInstance(&v166);
      if ( *v53 && v62 )
      {
        v65 = (RTL_SRWLOCK *)(v64 + 368);
        AcquireSRWLockShared((PSRWLOCK)(v64 + 368));
        if ( !*(_BYTE *)(v64 + 376) )
        {
          v67 = EndpointDlp::TraceLoggingProvider::Instance();
          v71 = *(_DWORD **)v67;
          if ( **(_DWORD **)v67 <= 2u )
          {
            v56 = -2147023782;
          }
          else
          {
            v158 = L"Call to DlpGenerateSyncClassificationEvent before Initialization";
            v56 = -2147023782;
            v184 = -2147023782;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
              (__int64)v71,
              (unsigned __int8 *)byte_1802C1E49,
              v69,
              v70,
              (__int64)&v184,
              &v158);
          }
          if ( v65 )
            ReleaseSRWLockShared(v65);
          v72 = -2147023782;
          v57 = 4;
          LODWORD(v53) = (_DWORD)v162;
          goto LABEL_112;
        }
        v196.Ptr = (ULONGLONG)v162;
        *(_QWORD *)&v196.Size = v63;
        v197 = v61;
        v198 = v173;
        v199[0] = v62;
        v200 = 0;
        v201 = 15;
        EndpointDlp::Telemetry::SendSyncClassificationEvent((EndpointDlp::Telemetry *)&v196, v66);
        if ( v200 != -1 && v200 )
          std::wstring::`scalar deleting destructor'(v199);
        if ( v64 != -368 )
          ReleaseSRWLockShared((PSRWLOCK)(v64 + 368));
        v72 = 0;
        LODWORD(v53) = (_DWORD)v162;
      }
      else
      {
        v73 = EndpointDlp::TraceLoggingProvider::Instance();
        v74 = *(_DWORD **)v73;
        if ( **(_DWORD **)v73 > 2u )
        {
          v72 = -2147024809;
          v184 = -2147024809;
          v199[2] = L"Invalid argument for DlpGenerateSyncClassificationEvent";
          v199[3] = 112;
          v199[0] = &v184;
          v57 = 4;
          v199[1] = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 2;
          EventDescriptor.Keyword = 0;
          v196.Ptr = *((_QWORD *)v74 + 1);
          v196.Size = *(unsigned __int16 *)v196.Ptr;
          v196.Reserved = 2;
          v197 = (unsigned __int64)&dword_1802BF174;
          v198 = 0x100000024LL;
          LODWORD(v158) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(*((_QWORD *)v74 + 4), &EventDescriptor, 0, 0, 4u, &v196);
LABEL_111:
          v56 = -2147023782;
LABEL_112:
          if ( v167 )
            std::_Ref_count_base::_Decref(v167);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SIL(*((_QWORD *)WPP_GLOBAL_Control + 2), v68, v69, (_DWORD)v53, ClassificationTimeFromEA, v72);
          if ( v72 >= 0 )
          {
            RealtimeProtection::DlpLRUCache<std::wstring,unsigned __int64>::add(
              (char *)v165 + 88,
              &v196,
              v189,
              ClassificationTimeFromEA);
            std::optional<std::wstring>::~optional<std::wstring>(&v196);
          }
          if ( Block )
            operator delete(Block);
          v20 = v171;
          goto LABEL_122;
        }
        v72 = -2147024809;
      }
      v57 = 4;
      goto LABEL_111;
    }
  }
  v57 = 4;
  v56 = -2147023782;
LABEL_125:
  v75 = *(_DWORD *)v155;
  if ( (v155[0] & 1) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids, v19);
    return 0;
  }
  if ( *(_DWORD *)v156 == 5 )
    return 0;
  if ( (a8 & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids, v19);
    return 0;
  }
  if ( !a13
    && !v153
    && !v154
    && RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance::IsJitFileExcluded(v19) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids, v19);
    return 0;
  }
  if ( (v75 & 0x80u) == 0
    && RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance::IsJitProcessExcluded(v164) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)&WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
        (_DWORD)v19,
        (__int64)v164);
    return 0;
  }
  v76 = v153;
  if ( v153 && !a11 )
  {
    if ( !a18 )
    {
      v79 = v186;
      goto LABEL_168;
    }
  }
  else if ( !a18 )
  {
    v77 = (const wchar_t *)v20;
    if ( *(_QWORD *)(v20 + 24) > 7u )
      v77 = *(const wchar_t **)v20;
    v78 = (EndpointDlp::endpointDlpImpl **)EndpointDlp::endpointDlpImpl::GetInstance(&v166);
    v79 = v186;
    IsSyncClassificationRequired = EndpointDlp::endpointDlpImpl::endpointDlpIsSyncClassificationRequired(
                                     *v78,
                                     v19,
                                     v77,
                                     a11,
                                     v186,
                                     (enum _DLP_JIT_SYNC_CLASSIFICATION_REASON *)v185);
    if ( v167 )
      std::_Ref_count_base::_Decref(v167);
    if ( IsSyncClassificationRequired < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
          (unsigned int)IsSyncClassificationRequired);
      return (unsigned int)IsSyncClassificationRequired;
    }
    v76 = v153;
    goto LABEL_168;
  }
  v79 = v186;
  if ( (v75 & 0x40000) != 0 )
  {
    v81 = 1;
    *(_DWORD *)v185 = 1;
    goto LABEL_169;
  }
LABEL_168:
  v81 = *(_DWORD *)v185;
LABEL_169:
  if ( v76 )
  {
    v81 = 13;
    *(_DWORD *)v185 = 13;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)&WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
      (_DWORD)v19,
      v81);
    v81 = *(_DWORD *)v185;
  }
  v82 = v155[0];
  if ( v81 || (v155[0] & 2) == 0 )
  {
    v85 = a11;
  }
  else
  {
    v83 = (EndpointDlp::endpointDlpImpl **)EndpointDlp::endpointDlpImpl::GetInstance(&v166);
    v84 = v79;
    v85 = a11;
    IsClassificationOutdated = EndpointDlp::endpointDlpImpl::endpointDlpIsClassificationOutdated(
                                 *v83,
                                 v19,
                                 a11,
                                 v84,
                                 (enum _DLP_JIT_SYNC_CLASSIFICATION_REASON *)v185);
    if ( v167 )
      std::_Ref_count_base::_Decref(v167);
    v82 = v155[0];
    if ( IsClassificationOutdated >= 0 )
    {
      v81 = *(_DWORD *)v185;
    }
    else
    {
      v81 = 0;
      *(_DWORD *)v185 = 0;
    }
  }
  if ( v154 )
  {
    v87 = v178;
    if ( *((_QWORD *)v178 + 3) > 7u )
      v87 = *(void **)v178;
    *(_QWORD *)&EventDescriptor.Id = v87;
    EventDescriptor.Keyword = *((_QWORD *)v178 + 2);
    v88 = (_QWORD *)EndpointDlp::endpointDlpImpl::GetInstance(&v166);
    v89 = EndpointDlp::endpointDlpImpl::IsJitCandidatePolicy(*v88, &EventDescriptor, 0);
    if ( v167 )
      std::_Ref_count_base::_Decref(v167);
    if ( !v89
      && !EndpointDlp::Client::IsFileConsiderNoEA((EndpointDlp::Client *)v85, (unsigned int)v186, v90)
      && !*(_DWORD *)v185 )
    {
      return 0;
    }
    *(_DWORD *)v185 = 13;
    goto LABEL_191;
  }
  if ( !v81 || v81 == 18 )
    return 0;
  if ( (unsigned int)(v81 - 4) > 1 )
  {
    if ( (unsigned int)(v81 - 2) <= 1 )
    {
      v91 = (v82 & 8) == 0;
    }
    else
    {
      if ( v81 != 7 )
      {
LABEL_191:
        v91 = (v155[0] & 1) == 0;
        goto LABEL_401;
      }
      v91 = (v82 & 2) == 0;
    }
LABEL_401:
    if ( v91 )
      return 0;
    goto LABEL_200;
  }
  if ( (v82 & 4) == 0 )
    return 0;
LABEL_200:
  v92 = *(_QWORD *)EndpointDlp::endpointDlpImpl::GetInstance(&v166);
  v93 = 2;
  AcquireSRWLockShared((PSRWLOCK)(v92 + 368));
  if ( *(_BYTE *)(v92 + 376) && (v94 = *(_QWORD *)(v92 + 384)) != 0 )
  {
    v93 = *(_DWORD *)(v94 + 444);
    if ( v92 != -368 )
      ReleaseSRWLockShared((PSRWLOCK)(v92 + 368));
    v56 = 0;
  }
  else
  {
    v95 = EndpointDlp::TraceLoggingProvider::Instance();
    v98 = *(_DWORD **)v95;
    if ( **(_DWORD **)v95 > 2u )
    {
      Block = L"Call to DlpGetJitDefaultFallbackPolicy before Initialization";
      v184 = -2147023782;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        (__int64)v98,
        (unsigned __int8 *)byte_1802C10D9,
        v96,
        v97,
        (__int64)&v184,
        (const wchar_t **)&Block);
    }
    if ( v92 != -368 )
      ReleaseSRWLockShared((PSRWLOCK)(v92 + 368));
  }
  if ( v167 )
    std::_Ref_count_base::_Decref(v167);
  if ( v56 < 0 )
    v93 = 2;
  LODWORD(v162) = v93;
  memset(v193, 0, 0x10Eu);
  LODWORD(v158) = 0;
  switch ( *(_DWORD *)v185 )
  {
    case 1:
    case 2:
    case 3:
    case 4:
    case 5:
    case 7:
    case 0xD:
      v57 = 1;
      goto LABEL_216;
    case 8:
    case 9:
      v57 = v93;
      goto LABEL_216;
    case 0x11:
LABEL_216:
      v184 = v57;
      v100 = v171;
      ActionsByPolicyType = RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance::GetActionsByPolicyType(
                              v99,
                              (unsigned int)&v184,
                              (unsigned int)&v170,
                              v171,
                              (__int64)v19,
                              (__int64)v164,
                              (__int64)v163,
                              v173,
                              *v174,
                              (__int64)&v158,
                              (__int64)v193);
      JitFileCloudApplicationPolicy = ActionsByPolicyType;
      v104 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
        v105 = (int)v158;
      }
      else
      {
        v105 = (int)v158;
        WPP_SF_SDL(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v102, (_DWORD)v19, (char)v158, ActionsByPolicyType);
        v104 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( JitFileCloudApplicationPolicy < 0 )
      {
        if ( v104 != &WPP_GLOBAL_Control && (*((_BYTE *)v104 + 28) & 1) != 0 )
          WPP_SF_d(
            v104[2],
            24,
            &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
            (unsigned int)JitFileCloudApplicationPolicy);
        return (unsigned int)JitFileCloudApplicationPolicy;
      }
      v106 = v176;
      if ( v176 || v172 )
      {
        v107 = *(_DWORD *)v156;
        if ( *(_DWORD *)v156 == 6 )
        {
          if ( v172 )
          {
            std::wstring::wstring(&EventDescriptor, v172);
            v195 = 1;
            p_EventDescriptor = &EventDescriptor;
            v109 = 36;
          }
          else
          {
            v183 = 0;
            p_EventDescriptor = (EVENT_DESCRIPTOR *)v182;
            v109 = 2;
          }
          v159 = v109;
          v160 = v109;
          v110 = &qword_18025C818;
          if ( v106 )
            v110 = v106;
          std::wstring::wstring(&v166, v110);
          std::wstring::wstring(v189, v19);
          JitFileCloudApplicationPolicy = EndpointDlp::Client::GetJitFileCloudApplicationPolicy(
                                            v184,
                                            (unsigned int)v189,
                                            v100,
                                            (unsigned int)&v166,
                                            (__int64)p_EventDescriptor,
                                            (__int64)&v158);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v189);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v166);
          if ( (v109 & 4) != 0 )
          {
            v109 &= ~4u;
            v160 = v109;
            v159 = v109;
            std::optional<std::wstring>::~optional<std::wstring>(&EventDescriptor);
          }
          if ( (v109 & 2) != 0 )
          {
            v160 = v109 & 0xFFFFFFFD;
            v159 = v109 & 0xFFFFFFFD;
            std::optional<std::wstring>::~optional<std::wstring>(v182);
          }
          v104 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            v105 = (int)v158;
          }
          else
          {
            v105 = (int)v158;
            WPP_SF_SDL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              v111,
              (_DWORD)v19,
              (char)v158,
              JitFileCloudApplicationPolicy);
            v104 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( JitFileCloudApplicationPolicy < 0 )
          {
            if ( v104 != &WPP_GLOBAL_Control && (*((_BYTE *)v104 + 28) & 1) != 0 )
              WPP_SF_d(
                v104[2],
                26,
                &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
                (unsigned int)JitFileCloudApplicationPolicy);
            return (unsigned int)JitFileCloudApplicationPolicy;
          }
        }
      }
      else
      {
        v107 = *(_DWORD *)v156;
      }
      if ( !v105 )
        return 0;
      v112 = (v107 & 0xFFFFFFFC) == 0 && v107 != 2;
      v113 = *(_DWORD *)v155 & 0x20000;
      if ( v104 == &WPP_GLOBAL_Control || (*((_BYTE *)v104 + 28) & 0x10) == 0 )
      {
        v114 = a17;
      }
      else
      {
        v114 = a17;
        LODWORD(v152) = a17;
        *(_DWORD *)v151 = v105;
        LODWORD(UserData) = *(_DWORD *)v185;
        UserDataCount[0] = v112;
        WPP_SF_ddddd(
          v104[2],
          27,
          &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
          v113 != 0,
          *(_QWORD *)UserDataCount,
          UserData,
          *(_QWORD *)v151,
          v152);
      }
      v116 = 0;
      if ( *(_DWORD *)v185 <= 0x11u )
      {
        v115 = 131842;
        if ( _bittest(&v115, *(unsigned int *)v185) )
          v116 = 1;
      }
      if ( v113 && v112 && !v153 )
      {
        if ( v116 )
          v105 = v114;
        LODWORD(v158) = v105;
      }
      v117 = *(_WORD *)v155;
      if ( (v155[0] & 0x10) != 0 )
        goto LABEL_290;
      if ( (unsigned int)(*(_DWORD *)v185 - 4) <= 1 )
      {
        v118 = (v155[0] & 0x20) == 0;
      }
      else if ( (unsigned int)(*(_DWORD *)v185 - 2) <= 1 )
      {
        v118 = (v155[0] & 0x40) == 0;
      }
      else
      {
        if ( *(_DWORD *)v185 != 7 )
          goto LABEL_275;
        v118 = (*(_WORD *)v155 & 0x200) == 0;
      }
      if ( !v118 )
      {
LABEL_290:
        v105 = 1;
        LODWORD(v158) = 1;
        goto LABEL_291;
      }
LABEL_275:
      if ( (unsigned int)(v105 - 2) <= 1 )
      {
LABEL_276:
        v119 = 1;
        goto LABEL_277;
      }
LABEL_291:
      v124 = (_QWORD *)EndpointDlp::endpointDlpImpl::GetInstance(&v166);
      IsJITActionNeedToClassify = EndpointDlp::endpointDlpImpl::endpointDlpIsJITActionNeedToClassify(
                                    *v124,
                                    *(unsigned int *)v156);
      if ( v167 )
        std::_Ref_count_base::_Decref(v167);
      if ( IsJITActionNeedToClassify )
        goto LABEL_276;
      v119 = 0;
LABEL_277:
      if ( (v117 & 0x1000) != 0 && v105 )
        v119 = 1;
      v120 = 0;
      *(_QWORD *)&EventDescriptor.Id = *v163;
      LODWORD(EventDescriptor.Keyword) = *((_DWORD *)v163 + 2);
      BYTE4(EventDescriptor.Keyword) = 1;
      std::wstring::wstring(v189, v19);
      RealtimeProtection::DlpPathCache::GetFilterPath(v190, v189, &EventDescriptor);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v189);
      if ( v192 )
        goto LABEL_284;
      v122 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids, v19);
LABEL_284:
        v122 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v119 )
      {
        v184 = 0;
        if ( v192 )
        {
          v123 = (const wchar_t *)v190;
          if ( v191 > 7 )
            v123 = (const wchar_t *)v190[0];
        }
        else
        {
          v123 = v19;
        }
        RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance::GetFileBlockedBySyncClassificationStatus(
          v165,
          v123,
          &v184);
        if ( (v184 & 1) != 0 )
          v119 = 0;
        v120 = (v184 & 2) != 0;
        if ( (v117 & 0x100) != 0 )
          v120 = 0;
        v122 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v122 != &WPP_GLOBAL_Control && (*((_BYTE *)v122 + 28) & 0x10) != 0 )
      {
        v126 = L"true";
        v127 = L"true";
        if ( !v120 )
          v127 = L"false";
        if ( !v119 )
          v126 = L"false";
        WPP_SF_SS(
          (unsigned int)v122[2],
          29,
          (unsigned int)&WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
          (_DWORD)v126,
          (__int64)v127);
      }
      if ( v119 )
      {
        v186 = 0;
        v128 = (_QWORD *)v171;
        v129 = (const WCHAR *)v171;
        if ( *(_QWORD *)(v171 + 24) > 7u )
          v129 = *(const WCHAR **)v171;
        v130 = CommonUtil::UtilConvertStringSidToSid((CommonUtil *)&v186, v129, v121);
        JitFileCloudApplicationPolicy = v130;
        if ( v130 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              30,
              &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
              (unsigned int)v130);
          if ( v186 )
            operator delete(v186);
LABEL_390:
          std::optional<std::wstring>::~optional<std::wstring>(v190);
          return (unsigned int)JitFileCloudApplicationPolicy;
        }
        *(_QWORD *)&EventDescriptor.Id = v19;
        v131 = -1;
        do
          ++v131;
        while ( v19[v131] );
        EventDescriptor.Keyword = v131;
        SyncClassificationEvent = EndpointDlp::Client::GenerateSyncClassificationEvent(
                                    (unsigned int)&EventDescriptor,
                                    (_DWORD)v186,
                                    *((_DWORD *)v163 + 2),
                                    v173,
                                    *(_DWORD *)v185);
        JitFileCloudApplicationPolicy = SyncClassificationEvent;
        if ( SyncClassificationEvent < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
              (unsigned int)SyncClassificationEvent);
          if ( v186 )
            operator delete(v186);
          goto LABEL_390;
        }
        if ( v186 )
          operator delete(v186);
      }
      else
      {
        v128 = (_QWORD *)v171;
      }
      if ( !v120 )
        goto LABEL_363;
      v133 = (unsigned int)v162;
      if ( (*(_WORD *)v155 & 0x2000) != 0 )
        v133 = 2;
      if ( ((v184 = v133, (v134 = v176) != 0) || v172) && *(_DWORD *)v156 == 6 )
      {
        if ( v172 )
        {
          std::wstring::wstring(v182, v172);
          v183 = 1;
          v135 = (struct _EVENT_DATA_DESCRIPTOR *)v182;
          v136 = v160 | 0x50;
          v134 = v176;
        }
        else
        {
          LOBYTE(v199[0]) = 0;
          v135 = &v196;
          v136 = v160 | 8;
        }
        v159 = v136;
        v137 = &qword_18025C818;
        if ( v134 )
          v137 = v134;
        std::wstring::wstring(&EventDescriptor, v137);
        std::wstring::wstring(&v166, v19);
        JitFileCloudApplicationPolicy = EndpointDlp::Client::GetJitFileCloudApplicationPolicy(
                                          v133,
                                          (unsigned int)&v166,
                                          (_DWORD)v128,
                                          (unsigned int)&EventDescriptor,
                                          (__int64)v135,
                                          (__int64)&v158);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v166);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&EventDescriptor);
        if ( (v136 & 0x10) != 0 )
        {
          LOBYTE(v136) = v136 & 0xEF;
          std::optional<std::wstring>::~optional<std::wstring>(v182);
        }
        if ( (v136 & 8) != 0 )
          std::optional<std::wstring>::~optional<std::wstring>(&v196);
        v139 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        {
          v105 = (int)v158;
        }
        else
        {
          v105 = (int)v158;
          WPP_SF_SDL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            v138,
            (_DWORD)v19,
            (char)v158,
            JitFileCloudApplicationPolicy);
          v139 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( JitFileCloudApplicationPolicy < 0 )
        {
          if ( v139 != &WPP_GLOBAL_Control && (*((_BYTE *)v139 + 28) & 1) != 0 )
            WPP_SF_d(
              v139[2],
              33,
              &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
              (unsigned int)JitFileCloudApplicationPolicy);
          goto LABEL_390;
        }
      }
      else
      {
        v140 = RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance::GetActionsByPolicyType(
                 (_DWORD)v176,
                 (unsigned int)&v184,
                 (unsigned int)&v170,
                 (_DWORD)v128,
                 (__int64)v19,
                 (__int64)v164,
                 (__int64)v163,
                 v173,
                 *v174,
                 (__int64)&v158,
                 (__int64)v193);
        JitFileCloudApplicationPolicy = v140;
        if ( v140 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              34,
              &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
              (unsigned int)v140);
          goto LABEL_390;
        }
        v105 = (int)v158;
      }
      if ( (v155[0] & 0x10) != 0 && v105 )
      {
        v105 = 1;
      }
      else
      {
LABEL_363:
        if ( v105 == 2 )
          v105 = 3;
      }
      if ( !IsJitRuleId )
      {
        v141 = v161;
        if ( v161 == 5 )
          v141 = 0;
        v142 = v105;
        if ( v105 == 5 )
          v142 = 0;
        if ( v141 == 4 )
          v141 = 1;
        if ( v142 == 4 )
          v142 = 1;
        if ( v141 > v142 )
        {
          *v175 = v161;
          *(_DWORD *)v185 = 0;
          std::optional<std::wstring>::~optional<std::wstring>(v190);
          return 0;
        }
      }
      v143 = *(_DWORD *)v185;
      if ( *(_DWORD *)v185 && (unsigned int)(v105 - 2) <= 1 )
      {
        v144 = 1;
      }
      else
      {
        v144 = 0;
        if ( !v119 )
          goto LABEL_394;
      }
      v161 = *(_DWORD *)v156;
      v151[0] = v144;
      LOBYTE(UserData) = 0;
      if ( v192 )
      {
        v145 = (wchar_t *)v190;
        if ( v191 > 7 )
          v145 = (wchar_t *)v190[0];
      }
      else
      {
        v145 = v19;
      }
      v146 = RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance::AddFileToBlockedBySyncClassificationCache(
               v165,
               v145,
               v163,
               v164,
               &v161,
               (_DWORD)UserData,
               *(_DWORD *)v151,
               v174,
               v177);
      JitFileCloudApplicationPolicy = v146;
      if ( v146 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
            (unsigned int)v146);
        goto LABEL_390;
      }
      if ( v144 )
        std::wstring::assign(v178, &v193[122]);
      v143 = *(_DWORD *)v185;
LABEL_394:
      *v175 = v105;
      *v181 = v143;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        if ( v128[3] > 7u )
          v128 = (_QWORD *)*v128;
        WPP_SF_DDDSSDS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v143,
          *((_DWORD *)v163 + 2),
          (__int64)v164,
          (__int64)v19,
          v156[0],
          (__int64)v128);
      }
      std::optional<std::wstring>::~optional<std::wstring>(v190);
      if ( JitFileCloudApplicationPolicy < 0 )
      {
        v147 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v164, JitFileCloudApplicationPolicy);
            v147 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v147 != &WPP_GLOBAL_Control && (*((_BYTE *)v147 + 28) & 1) != 0 )
            WPP_SF_d(
              v147[2],
              38,
              &WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids,
              (unsigned int)JitFileCloudApplicationPolicy);
        }
      }
      result = (unsigned int)JitFileCloudApplicationPolicy;
      break;
    default:
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180046db0  push    rbx
0x180046db2  push    rsi
0x180046db3  push    rdi
0x180046db4  push    r12
0x180046db6  push    r13
0x180046db8  push    r14
0x180046dba  push    r15
0x180046dbc  sub     rsp, 370h
0x180046dc3  mov     rax, cs:__security_cookie
0x180046dca  xor     rax, rsp
0x180046dcd  mov     [rsp+3A8h+var_48], rax
0x180046dd5  mov     rax, r9
0x180046dd8  mov     [rsp+3A8h+var_300], rax
0x180046de0  mov     r13, r8
0x180046de3  mov     [rsp+3A8h+var_310], r8
0x180046deb  mov     dword ptr [rsp+3A8h+var_330], edx
0x180046def  mov     [rsp+3A8h+var_2F8], rcx
0x180046df7  mov     rcx, [rsp+3A8h+arg_40]
0x180046dff  mov     [rsp+3A8h+var_2A0], rcx
0x180046e07  mov     r15d, dword ptr [rsp+3A8h+arg_50]
0x180046e0f  mov     [rsp+3A8h+var_2D0], edx
0x180046e16  mov     [rsp+3A8h+var_288], r8
0x180046e1e  mov     [rsp+3A8h+var_280], rax
0x180046e26  mov     rcx, [rsp+3A8h+arg_20]
0x180046e2e  mov     [rsp+3A8h+var_308], rcx
0x180046e36  mov     rax, [rsp+3A8h+arg_28]
0x180046e3e  mov     [rsp+3A8h+var_2B0], rax
0x180046e46  mov     r12, [rsp+3A8h+arg_30]
0x180046e4e  mov     [rsp+3A8h+var_2C8], r12
0x180046e56  mov     rax, [rsp+3A8h+arg_48]
0x180046e5e  mov     [rsp+3A8h+var_2C0], rax
0x180046e66  mov     rdi, [rsp+3A8h+arg_58]
0x180046e6e  mov     [rsp+3A8h+var_238], rdi
0x180046e76  mov     r14, [rsp+3A8h+arg_68]
0x180046e7e  mov     [rsp+3A8h+var_290], r14
0x180046e86  mov     rsi, [rsp+3A8h+arg_70]
0x180046e8e  mov     [rsp+3A8h+var_2A8], rsi
0x180046e96  mov     rdx, [rsp+3A8h+arg_78]
0x180046e9e  mov     [rsp+3A8h+var_278], rdx
0x180046ea6  mov     rax, [rsp+3A8h+arg_90]
0x180046eae  mov     [rsp+3A8h+var_298], rax
0x180046eb6  xor     r8d, r8d
0x180046eb9  mov     eax, r8d
0x180046ebc  mov     [rsp+3A8h+var_31C], eax
0x180046ec3  mov     [rsp+3A8h+var_320], eax
0x180046eca  mov     [rdx], r8d
0x180046ecd  mov     dword ptr [rsp+3A8h+var_23C], r8d
0x180046ed5  mov     edx, [rcx+4]
0x180046ed8  shl     rdx, 20h
0x180046edc  mov     eax, [rcx]
0x180046ede  or      rdx, rax
0x180046ee1  mov     [rsp+3A8h+var_2B8], rdx
0x180046ee9  mov     dword ptr [rsp+3A8h+var_334], r8d
0x180046eee  mov     rax, r12
0x180046ef1  cmp     qword ptr [r12+18h], 7
0x180046ef7  jbe     short loc_180046EFD
0x180046ef9  mov     rax, [r12]
0x180046efd  mov     qword ptr [rsp+3A8h+EventDescriptor.Id], rax
0x180046f05  mov     rax, [r12+10h]
0x180046f0a  mov     [rsp+3A8h+EventDescriptor.Keyword], rax
0x180046f12  lea     rdx, [rsp+3A8h+var_334]
0x180046f17  lea     rcx, [rsp+3A8h+EventDescriptor]
0x180046f1f  call    ?GetJitFeaturesForUser@Client@EndpointDlp@@YAJAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAK@Z; EndpointDlp::Client::GetJitFeaturesForUser(std::wstring_view const &,ulong &)
0x180046f24  mov     ebx, eax
0x180046f26  test    eax, eax
0x180046f28  jns     short loc_180046F9D
0x180046f2a  lea     r14, WPP_GLOBAL_Control
0x180046f31  mov     rcx, cs:WPP_GLOBAL_Control
0x180046f38  cmp     rcx, r14
0x180046f3b  jz      short loc_180046F96
0x180046f3d  test    byte ptr [rcx+1Ch], 10h
0x180046f41  jz      short loc_180046F73
0x180046f43  cmp     qword ptr [r12+18h], 7
0x180046f49  jbe     short loc_180046F4F
0x180046f4b  mov     r12, [r12]
0x180046f4f  mov     edx, 0Ah
0x180046f54  mov     qword ptr [rsp+3A8h+UserDataCount], r13
0x180046f59  mov     r9, r12
0x180046f5c  lea     r8, WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids
0x180046f63  mov     rcx, [rcx+10h]
0x180046f67  call    WPP_SF_SS
0x180046f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180046f73  cmp     rcx, r14
0x180046f76  jz      short loc_180046F96
0x180046f78  test    byte ptr [rcx+1Ch], 1
0x180046f7c  jz      short loc_180046F96
0x180046f7e  mov     edx, 0Bh
0x180046f83  mov     r9d, ebx
0x180046f86  lea     r8, WPP_20c3a48328dc3e4d2b3e8c5711e98a8d_Traceguids
0x180046f8d  mov     rcx, [rcx+10h]
0x180046f91  call    WPP_SF_d
0x180046f96  mov     eax, ebx
0x180046f98  jmp     loc_18004895B
0x180046f9d  mov     rcx, r14
0x180046fa0  call    ?IsJitRuleId@DlpJitStateMachineInstance@DlpJitStateMachine@RealtimeProtection@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance::IsJitRuleId(std::wstring const &)
0x180046fa5  mov     [rsp+3A8h+var_32C], al
0x180046fa9  test    al, al
0x180046fab  jz      short loc_180046FB3
0x180046fad  xor     ebx, ebx
0x180046faf  mov     esi, ebx
0x180046fb1  jmp     short loc_180046FB5
0x180046fb3  mov     esi, [rsi]
0x180046fb5  mov     rax, [rsp+3A8h+var_2A8]
0x180046fbd  mov     ecx, [rax]
0x180046fbf  mov     [rsp+3A8h+var_318], ecx
0x180046fc6  mov     [rsp+3A8h+var_338], 0
0x180046fcb  mov     [rsp+3A8h+var_337], 0
0x180046fd0  mov     ecx, 55h ; 'U'
0x180046fd5  call    ?GetValue@FeatureControl@Dlp@@YAIW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetValue(FeatureControlEnum)
0x180046fda  test    al, 4
0x180046fdc  jz      loc_180047127
0x180046fe2  mov     rdx, r13
0x180046fe5  lea     rcx, [rsp+3A8h+var_220]
0x180046fed  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180046ff2  nop
0x180046ff3  mov     [rsp+3A8h+var_320], 1
0x180046ffe  lea     rcx, [rsp+3A8h+var_220]; Src
0x180047006  call    ?IsPathFromOutlookInetCache@Client@EndpointDlp@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; EndpointDlp::Client::IsPathFromOutlookInetCache(std::wstring const &)
0x18004700b  test    al, al
0x18004700d  jz      loc_1800470FF
0x180047013  mov     rax, r14
0x180047016  cmp     qword ptr [r14+18h], 7
0x18004701b  jbe     short loc_180047020
0x18004701d  mov     rax, [r14]
0x180047020  mov     qword ptr [rsp+3A8h+EventDescriptor.Id], rax
0x180047028  mov     rax, [r14+10h]
0x18004702c  mov     [rsp+3A8h+EventDescriptor.Keyword], rax
0x180047034  lea     rcx, [rsp+3A8h+Block]
0x18004703c  call    ?GetInstance@endpointDlpImpl@EndpointDlp@@SA?AV?$shared_ptr@VendpointDlpImpl@EndpointDlp@@@std@@XZ; EndpointDlp::endpointDlpImpl::GetInstance(void)
0x180047041  xor     r8d, r8d
0x180047044  lea     rdx, [rsp+3A8h+EventDescriptor]
0x18004704c  mov     rcx, [rax]
0x18004704f  call    ?IsJitCandidatePolicy@endpointDlpImpl@EndpointDlp@@QEBA_NAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N@Z; EndpointDlp::endpointDlpImpl::IsJitCandidatePolicy(std::wstring_view const &,bool)
0x180047054  movzx   ebx, al
0x180047057  mov     rcx, [rsp+3A8h+var_228]; this
0x18004705f  test    rcx, rcx
0x180047062  jz      short loc_180047069
0x180047064  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180047069  test    bl, bl
0x18004706b  jnz     loc_1800470F8
0x180047071  mov     rax, r14
0x180047074  cmp     qword ptr [r14+18h], 7
0x180047079  jbe     short loc_18004707E
0x18004707b  mov     rax, [r14]
0x18004707e  mov     [rsp+3A8h+Block], rax
0x180047086  mov     rax, [r14+10h]
0x18004708a  mov     [rsp+3A8h+var_228], rax
0x180047092  lea     rcx, [rsp+3A8h+EventDescriptor]
0x18004709a  call    ?GetInstance@endpointDlpImpl@EndpointDlp@@SA?AV?$shared_ptr@VendpointDlpImpl@EndpointDlp@@@std@@XZ; EndpointDlp::endpointDlpImpl::GetInstance(void)
0x18004709f  mov     rbx, [rax]
0x1800470a2  lea     rdx, [rsp+3A8h+Block]
0x1800470aa  mov     rcx, rbx
0x1800470ad  call    ?IsJitAsyncClassificationPolicy@endpointDlpImpl@EndpointDlp@@QEBA_NAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N@Z; EndpointDlp::endpointDlpImpl::IsJitAsyncClassificationPolicy(std::wstring_view const &,bool)
0x1800470b2  test    al, al
0x1800470b4  jnz     short loc_1800470D1
0x1800470b6  xor     r8d, r8d
0x1800470b9  lea     rdx, [rsp+3A8h+Block]
0x1800470c1  mov     rcx, rbx
0x1800470c4  call    ?IsJitCandidatePolicy@endpointDlpImpl@EndpointDlp@@QEBA_NAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N@Z; EndpointDlp::endpointDlpImpl::IsJitCandidatePolicy(std::wstring_view const &,bool)
0x1800470c9  test    al, al
0x1800470cb  jnz     short loc_1800470D1
0x1800470cd  xor     bl, bl
0x1800470cf  jmp     short loc_1800470D3
0x1800470d1  mov     bl, 1
0x1800470d3  mov     rcx, [rsp+3A8h+EventDescriptor.Keyword]; this
0x1800470db  test    rcx, rcx
0x1800470de  jz      short loc_1800470E5
0x1800470e0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800470e5  test    bl, bl
0x1800470e7  jnz     short loc_1800470F8
0x1800470e9  mov     rdx, rdi; unsigned int
0x1800470ec  mov     ecx, r15d; this
0x1800470ef  call    ?IsFileConsiderNoEA@Client@EndpointDlp@@YA_NKPEAE@Z; EndpointDlp::Client::IsFileConsiderNoEA(ulong,uchar *)
0x1800470f4  test    al, al
0x1800470f6  jz      short loc_1800470FF
0x1800470f8  mov     [rsp+3A8h+var_338], 1
0x1800470fd  jmp     short loc_180047104
0x1800470ff  mov     [rsp+3A8h+var_338], 0
0x180047104  xor     r14d, r14d
0x180047107  mov     eax, r14d
0x18004710a  mov     [rsp+3A8h+var_31C], eax
0x180047111  mov     [rsp+3A8h+var_320], eax
0x180047118  lea     rcx, [rsp+3A8h+var_220]; void *
0x180047120  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180047125  jmp     short loc_18004712A
0x180047127  xor     r14d, r14d
0x18004712a  mov     ecx, 105h
0x18004712f  call    ?GetValue@FeatureControl@Dlp@@YAIW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetValue(FeatureControlEnum)
0x180047134  mov     r11d, dword ptr [rsp+3A8h+var_330]
0x180047139  test    al, 2
0x18004713b  jz      loc_18004723E
0x180047141  cmp     r11d, 6
0x180047145  jnz     loc_18004723E
0x18004714b  lea     rcx, [rsp+3A8h+EventDescriptor]
0x180047153  call    ?GetInstance@endpointDlpImpl@EndpointDlp@@SA?AV?$shared_ptr@VendpointDlpImpl@EndpointDlp@@@std@@XZ; EndpointDlp::endpointDlpImpl::GetInstance(void)
0x180047158  mov     rdx, r13; wchar_t *
0x18004715b  mov     rcx, [rax]; this
0x18004715e  call    ?IsDlpEnabledForFile@endpointDlpImpl@EndpointDlp@@QEBA_NQEB_W@Z; EndpointDlp::endpointDlpImpl::IsDlpEnabledForFile(wchar_t const * const)
0x180047163  movzx   ebx, al
0x180047166  mov     rcx, [rsp+3A8h+EventDescriptor.Keyword]; this
0x18004716e  test    rcx, rcx
0x180047171  jz      short loc_180047178
0x180047173  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180047178  test    bl, bl
0x18004717a  jnz     loc_180047239
0x180047180  call    _Lock_shared_ptr_spin_lock
0x180047185  mov     rbx, cs:qword_180314278
0x18004718c  test    rbx, rbx
0x18004718f  jz      short loc_18004719C
0x180047191  lock inc dword ptr [rbx+8]
0x180047195  mov     rbx, cs:qword_180314278
0x18004719c  mov     rdi, cs:qword_180314270
0x1800471a3  call    _Unlock_shared_ptr_spin_lock
0x1800471a8  test    rdi, rdi
0x1800471ab  jnz     short loc_1800471BF
0x1800471ad  test    rbx, rbx
0x1800471b0  jz      short loc_1800471BA
0x1800471b2  mov     rcx, rbx; this
0x1800471b5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800471ba  mov     edi, r14d
0x1800471bd  jmp     short loc_1800471FC
0x1800471bf  cmp     qword ptr [r12+10h], 0
0x1800471c5  jz      short loc_1800471EC
0x1800471c7  mov     r8, r12
0x1800471ca  lea     rdx, [rsp+3A8h+Block]
0x1800471d2  mov     rcx, rdi
0x1800471d5  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUserData@DlpUserConfiguration@UserConfig@Policy@EndpointDlp@@UwstringOrdinalCompareInsensitive@Common@7@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUserData@DlpUserConfiguration@UserConfig@Policy@EndpointDlp@@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUserData@DlpUserConfiguration@UserConfig@Policy@EndpointDlp@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,EndpointDlp::Policy::UserConfig::DlpUserConfiguration::UserData,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::pair<std::wstring const,EndpointDlp::Policy::UserConfig::DlpUserConfiguration::UserData>>,0>>::find(std::wstring const &)
0x1800471da  mov     rax, [rsp+3A8h+Block]
0x1800471e2  cmp     rax, [rdi]
0x1800471e5  jz      short loc_1800471EC
0x1800471e7  mov     edi, [rax+58h]
0x1800471ea  jmp     short loc_1800471EF
0x1800471ec  mov     edi, r14d
0x1800471ef  test    rbx, rbx
0x1800471f2  jz      short loc_1800471FC
0x1800471f4  mov     rcx, rbx; this
0x1800471f7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800471fc  mov     [rsp+3A8h+var_240], r14d
0x180047204  lea     r8, [rsp+3A8h+var_240]; unsigned int
0x18004720c  xor     edx, edx; wchar_t *
0x18004720e  lea     rcx, aMpdlpExclusion; "MpDlp_ExclusionProtectionEnforcementMod"...
0x180047215  call    ?DlpGetMiscDwordValue@DlpUtils@RealtimeProtection@@YAJPEB_WKPEAK@Z; RealtimeProtection::DlpUtils::DlpGetMiscDwordValue(wchar_t const *,ulong,ulong *)
0x18004721a  test    eax, eax
0x18004721c  js      short loc_180047229
0x18004721e  cmp     eax, 1
0x180047221  cmovnz  edi, [rsp+3A8h+var_240]
0x180047229  cmp     edi, 2
0x18004722c  setz    [rsp+3A8h+var_337]
0x180047231  mov     rdi, [rsp+3A8h+var_238]
0x180047239  mov     r11d, dword ptr [rsp+3A8h+var_330]
0x18004723e  lea     r14, WPP_GLOBAL_Control
0x180047245  mov     rcx, cs:WPP_GLOBAL_Control
0x18004724c  cmp     rcx, r14
0x18004724f  jz      loc_1800472EE
0x180047255  test    byte ptr [rcx+1Ch], 10h
0x180047259  jz      loc_1800472EE
0x18004725f  lea     r8, aFalse_0; "false"
0x180047266  lea     rbx, aTrue; "true"
0x18004726d  mov     rax, rbx
0x180047270  test    r15d, r15d
0x180047273  cmovnz  rax, r8
0x180047277  movzx   r9d, [rsp+3A8h+var_338]
0x18004727d  movzx   r10d, [rsp+3A8h+arg_88]
0x180047286  mov     rdx, rbx
0x180047289  cmp     [rsp+3A8h+var_32C], 0
0x18004728e  cmovz   rdx, r8
0x180047292  mov     r8, r12
0x180047295  cmp     qword ptr [r12+18h], 7
0x18004729b  jbe     short loc_1800472A1
0x18004729d  mov     r8, [r12]
0x1800472a1  mov     [rsp+3A8h+var_348], rax; __int64
0x1800472a6  mov     dword ptr [rsp+3A8h+var_350], r9d; char
0x1800472ab  mov     dword ptr [rsp+3A8h+var_358], r10d; char
0x1800472b0  mov     eax, dword ptr [rsp+3A8h+var_334]
0x1800472b4  mov     dword ptr [rsp+3A8h+var_360], eax; char
0x1800472b8  mov     qword ptr [rsp+3A8h+var_368], rdx; __int64
0x1800472bd  mov     [rsp+3A8h+var_370], r8; __int64
0x1800472c2  mov     dword ptr [rsp+3A8h+var_378], r11d; char
0x1800472c7  mov     [rsp+3A8h+UserData], r13; __int64
0x1800472cc  mov     rax, [rsp+3A8h+var_300]
0x1800472d4  mov     qword ptr [rsp+3A8h+UserDataCount], rax; __int64
0x1800472d9  mov     r9, [rsp+3A8h+var_308]
0x1800472e1  mov     r9d, [r9+8]
0x1800472e5  mov     rcx, [rcx+10h]; LoggerHandle
0x1800472e9  call    WPP_SF_DSSDSSDddS
0x1800472ee  mov     rax, [rsp+3A8h+var_2A8]
0x1800472f6  mov     [rax], esi
0x1800472f8  mov     ecx, 0DAh
0x1800472fd  call    ?GetValue@FeatureControl@Dlp@@YAIW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetValue(FeatureControlEnum)
0x180047302  test    al, 2
0x180047304  jz      loc_18004783A
0x18004730a  lea     rax, [rsp+3A8h+EventDescriptor]
0x180047312  mov     [rsp+3A8h+Block], rax
0x18004731a  xorps   xmm0, xmm0
0x18004731d  movdqu  xmmword ptr [rsp+3A8h+EventDescriptor.Id], xmm0
0x180047326  mov     rdx, r13
0x180047329  lea     rcx, [rsp+3A8h+var_2F0]
0x180047331  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180047336  nop
0x180047337  lea     r9, [rsp+3A8h+EventDescriptor]
  ... truncated ...
```
