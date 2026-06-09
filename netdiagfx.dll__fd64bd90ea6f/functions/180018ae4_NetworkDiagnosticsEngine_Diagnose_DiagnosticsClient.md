# NetworkDiagnosticsEngine::Diagnose(DiagnosticsClient *)

- ea: `0x180018ae4`
- end: `0x18001a47d`
- name: `?Diagnose@NetworkDiagnosticsEngine@@QEAAJPEAVDiagnosticsClient@@@Z`
- size: `6553`
- prototype: `__int64 __fastcall(NetworkDiagnosticsEngine *__hidden this, struct DiagnosticsClient *)`
- caller_count: `1`
- callee_count: `51`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180004940`

## callees

- `0x180001010`
- `0x180001214`
- `0x18000506c`
- `0x1800056bc`
- `0x18000579c`
- `0x180006d58`
- `0x1800074a4`
- `0x180008248`
- `0x1800083a0`
- `0x1800083e0`
- `0x180008d38`
- `0x180009b8c`
- `0x18000a3e8`
- `0x18000b098`
- `0x18000bca0`
- `0x18000bda4`
- `0x18000c42c`
- `0x18000d028`
- `0x18000d2d8`
- `0x18000fb34`
- `0x180010254`
- `0x180017b94`
- `0x180017d34`
- `0x180017f74`
- `0x180017f94`
- `0x18001845c`
- `0x1800184d4`
- `0x1800185b0`
- `0x180018ae4`
- `0x18001a5b4`
- `0x18001a668`
- `0x18001a9a4`
- `0x18001ad94`
- `0x18001ae00`
- `0x18001b3f0`
- `0x18001b418`
- `0x18001b5dc`
- `0x18001b6e8`
- `0x18001ba6c`
- `0x18001bfc0`
- `0x18001ddb8`
- `0x1800215e4`
- `0x180021704`
- `0x18002172c`
- `0x180021a1c`
- `0x180021db8`
- `0x180021f88`
- `0x180023ac8`
- `0x18002c802`
- `0x18002c840`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18001a1aa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001a1aa`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001a1bd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001a1bd`
- `KERNEL32!WaitForSingleObject` at `0x18001a110`
- `KERNEL32!WaitForSingleObject` at `0x18001a110`
- `KERNEL32!GetTickCount64` at `0x180018b61`
- `KERNEL32!GetTickCount64` at `0x18001a1e8`
- `KERNEL32!GetTickCount64` at `0x180018b61`
- `KERNEL32!GetTickCount64` at `0x18001a1e8`
- `wdi!WdiAddParameter` at `0x180018dfe`
- `wdi!WdiAddParameter` at `0x18001922b`
- `wdi!WdiAddParameter` at `0x18001a41b`
- `wdi!WdiAddParameter` at `0x180018dfe`
- `wdi!WdiAddParameter` at `0x18001922b`
- `wdi!WdiAddParameter` at `0x18001a41b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019d45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019d45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019095`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a3cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019095`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a3cb`

## string_xrefs

- `0x18001988b`: `Duplicate Repair. HelperClass: %s, Description: %s`
- `0x180019a54`: `Skipping repro repair from %s as other repairs exist in the scenario. `
- `0x1800199e1`: `Failed while adding a repair to the diagnostics client. HR=%x`
- `0x180019b82`: `Failed while adding the repair and root cause to the collector. HR=%x`
- `0x180019be8`: `Repair`

## pseudocode

```c
__int64 __fastcall NetworkDiagnosticsEngine::Diagnose(NetworkDiagnosticsEngine *this, struct DiagnosticsClient *a2)
{
  struct DiagnosticsClient *v2; // rdi
  NetworkDiagnosticsEngine *v3; // r13
  NetworkDiagnosticsEngine *v5; // rcx
  int NLMStatus; // eax
  __int64 v7; // r8
  const wchar_t *NLMStatusString; // rdx
  PVOID v9; // rbx
  NdfTelemetryProviderSingleton *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // ebx
  __int64 v14; // rax
  NdfTelemetryProviderSingleton *v15; // r15
  _QWORD *TickCount; // rax
  int RepairOptions; // esi
  struct tagHELPER_ATTRIBUTE *v18; // rdx
  const unsigned __int16 *v19; // rdx
  struct tagHELPER_ATTRIBUTE *v20; // r13
  unsigned int v21; // edi
  struct tagHELPER_ATTRIBUTE *v22; // rsi
  int v23; // eax
  unsigned int v24; // ebx
  const unsigned __int16 *v25; // rdx
  int All; // eax
  NetworkDiagnosticsEngine *v27; // rbx
  __int64 *v28; // rcx
  __int64 v29; // rax
  struct tagHELPER_ATTRIBUTE *v30; // rbx
  NdfTelemetryProviderSingleton *v31; // rcx
  char v32; // bl
  struct tagHELPER_ATTRIBUTE *v33; // rdi
  unsigned int v34; // esi
  _QWORD *v35; // rax
  __int64 v36; // rcx
  NetworkDiagnosticsEngine *v37; // rbx
  struct tagHELPER_ATTRIBUTE *v38; // r9
  char *v39; // rax
  int v40; // eax
  int *v41; // rbx
  struct tagHELPER_ATTRIBUTE *v42; // rbx
  __int64 v43; // rbx
  __int64 v44; // rcx
  struct tagRepairInfo **v45; // rax
  struct ProblemNode **v46; // rax
  int v47; // eax
  __int64 v48; // rbx
  _QWORD *v49; // rsi
  NetworkDiagnosticsEngine *v50; // rbx
  __int64 *v51; // rcx
  __int64 v52; // rax
  struct tagHELPER_ATTRIBUTE *v53; // rbx
  __int64 v54; // r8
  struct ProblemNode *v55; // rbx
  unsigned __int64 v56; // rdi
  __int64 v57; // rdx
  __int64 *v58; // rdx
  __int64 v59; // rax
  signed int v60; // ecx
  struct tagRepairInfo *v61; // rdi
  int v62; // eax
  unsigned int v63; // eax
  __int64 v64; // rcx
  struct ProblemNode *v65; // rdx
  int i; // r8d
  struct ProblemNode *v67; // rax
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 v70; // rbx
  _QWORD *v71; // rbx
  __int64 v72; // rdi
  __int64 v73; // rcx
  unsigned int v74; // ebx
  struct DiagnosticsClient *v75; // rdi
  struct ProblemNode *v76; // rbx
  int v77; // eax
  NetworkDiagnosticsEngine *v78; // rbx
  __int64 *v79; // rcx
  __int64 v80; // rax
  __int64 v81; // rbx
  __int64 v82; // rbx
  int v83; // eax
  void *v84; // rdx
  __int64 v85; // r8
  NetworkDiagnosticsEngine *v86; // rbx
  _QWORD *v87; // rax
  __int64 *v88; // rcx
  __int64 v89; // rax
  struct tagHELPER_ATTRIBUTE *v90; // rbx
  const wchar_t *v91; // r8
  __int64 v92; // rbx
  __int64 v93; // rcx
  int v94; // eax
  SIZE_T v95; // rbx
  struct tagRootCauseInfo *v96; // rax
  struct tagRootCauseInfo *v97; // rcx
  int v98; // eax
  struct tagRootCauseInfo *j; // rdx
  int v100; // eax
  char *v101; // rbx
  unsigned __int16 v102; // r13
  _QWORD *v103; // rdi
  __int64 v104; // rcx
  NetworkDiagnosticsEngine *v105; // rbx
  __int64 *v106; // rcx
  __int64 v107; // rax
  _QWORD *v108; // rbx
  __int64 v109; // rcx
  _QWORD *v110; // rax
  __int64 v111; // r12
  void (__fastcall *v112)(__int64, _QWORD, char *); // rdi
  unsigned int v113; // eax
  __int64 v114; // rcx
  DWORD v115; // eax
  int v116; // ebx
  NdfTelemetryProviderSingleton *v117; // rcx
  NdfTelemetryProviderSingleton *v118; // r15
  NdfTelemetryProviderSingleton *v119; // rcx
  const unsigned __int16 *v120; // r12
  int v121; // r13d
  ULONGLONG v122; // rdi
  NetworkDiagnosticsEngine *v123; // rcx
  const wchar_t *v124; // r8
  char v125; // dl
  PVOID v126; // rbx
  NdfTelemetryProviderSingleton *v127; // rcx
  __int64 v128; // r8
  __int64 v129; // r9
  int v130; // [rsp+20h] [rbp-308h]
  unsigned __int8 v131[8]; // [rsp+90h] [rbp-298h] BYREF
  unsigned __int16 v132[4]; // [rsp+98h] [rbp-290h] BYREF
  unsigned int v133; // [rsp+A0h] [rbp-288h] BYREF
  struct tagHELPER_ATTRIBUTE *v134; // [rsp+A8h] [rbp-280h] BYREF
  NLM_CONNECTIVITY v135; // [rsp+B0h] [rbp-278h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-270h] BYREF
  int v137; // [rsp+C0h] [rbp-268h]
  char v138[4]; // [rsp+C4h] [rbp-264h] BYREF
  _QWORD *v139; // [rsp+C8h] [rbp-260h] BYREF
  NLM_CONNECTIVITY v140; // [rsp+D0h] [rbp-258h] BYREF
  unsigned int v141; // [rsp+D4h] [rbp-254h] BYREF
  struct tagHELPER_ATTRIBUTE *v142; // [rsp+D8h] [rbp-250h] BYREF
  int v143[2]; // [rsp+E0h] [rbp-248h] BYREF
  struct tagHELPER_ATTRIBUTE *v144; // [rsp+E8h] [rbp-240h] BYREF
  int v145[4]; // [rsp+F0h] [rbp-238h] BYREF
  unsigned __int64 v146; // [rsp+100h] [rbp-228h]
  int v147[2]; // [rsp+108h] [rbp-220h] BYREF
  struct ProblemNode *v148; // [rsp+110h] [rbp-218h]
  CTraceController *v149; // [rsp+118h] [rbp-210h] BYREF
  NetworkDiagnosticsEngine *v150; // [rsp+120h] [rbp-208h]
  volatile signed __int32 *v151; // [rsp+128h] [rbp-200h]
  char *v152; // [rsp+130h] [rbp-1F8h] BYREF
  NetworkDiagnosticsEngine *v153; // [rsp+138h] [rbp-1F0h]
  __int64 v154; // [rsp+140h] [rbp-1E8h] BYREF
  NdfTelemetryProviderSingleton *v155; // [rsp+148h] [rbp-1E0h] BYREF
  struct DiagnosticsClient *v156; // [rsp+150h] [rbp-1D8h] BYREF
  CTraceController *SessionGuid; // [rsp+158h] [rbp-1D0h] BYREF
  struct DiagnosticsClient *v158; // [rsp+160h] [rbp-1C8h]
  const wchar_t *v159; // [rsp+168h] [rbp-1C0h] BYREF
  LPVOID v160; // [rsp+170h] [rbp-1B8h] BYREF
  ULONGLONG TickCount64; // [rsp+178h] [rbp-1B0h]
  struct tagHELPER_ATTRIBUTE *v162; // [rsp+180h] [rbp-1A8h]
  struct DiagnosticsClient *v163; // [rsp+188h] [rbp-1A0h]
  __int128 v164; // [rsp+190h] [rbp-198h] BYREF
  __int64 v165; // [rsp+1A0h] [rbp-188h]
  __int128 v166; // [rsp+1A8h] [rbp-180h]
  _QWORD v167[3]; // [rsp+1B8h] [rbp-170h] BYREF
  __int64 v168; // [rsp+1D0h] [rbp-158h]
  __int64 v169; // [rsp+1D8h] [rbp-150h]
  _QWORD v170[3]; // [rsp+1E0h] [rbp-148h] BYREF
  unsigned __int64 v171; // [rsp+1F8h] [rbp-130h]
  __int64 v172; // [rsp+200h] [rbp-128h]
  __int64 *v173; // [rsp+208h] [rbp-120h] BYREF
  __int128 v174; // [rsp+220h] [rbp-108h] BYREF
  struct tagRepairInfo *v175; // [rsp+230h] [rbp-F8h] BYREF
  struct ProblemNode *v176[11]; // [rsp+238h] [rbp-F0h]
  struct ProblemNode *v177[12]; // [rsp+290h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  v2 = a2;
  v158 = a2;
  v156 = a2;
  v3 = qword_180041BB8;
  v153 = qword_180041BB8;
  if ( !a2 )
  {
    if ( *(_QWORD *)qword_180041BB8 )
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)qword_180041BB8 + 56LL))(
        *(_QWORD *)qword_180041BB8,
        2147942406LL,
        0);
    return 2147942406LL;
  }
  TickCount64 = GetTickCount64();
  v140 = NLM_CONNECTIVITY_DISCONNECTED;
  v131[0] = 0;
  NLMStatus = NetworkDiagnosticsEngine::GetNLMStatus(v5, &v140, v131);
  v147[1] = v140;
  if ( NLMStatus < 0 )
  {
    NLMStatusString = L"Unknown";
    LOBYTE(v7) = 0;
    v131[0] = 0;
  }
  else
  {
    NLMStatusString = GetNLMStatusString(v140);
    LOBYTE(v7) = v131[0];
  }
  SessionGuid = (CTraceController *)NLMStatusString;
  v9 = CallbackContext;
  if ( *(_DWORD *)CallbackContext > 5u )
  {
    v10 = (NdfTelemetryProviderSingleton *)*((_QWORD *)CallbackContext + 3);
    if ( (*((_QWORD *)CallbackContext + 2) & 0x400000000000LL) != 0
      && (NdfTelemetryProviderSingleton *)((unsigned __int64)v10 & 0x400000000000LL) == v10 )
    {
      v135 = v140;
      LOBYTE(v132[0]) = v7;
      v139 = NLMStatusString;
      *(_QWORD *)v145 = NdfTelemetryProviderSingleton::GetSessionGuid(v10);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        (__int64)v9,
        (__int64)byte_180039B35,
        v11,
        v12,
        (__int64)v145,
        &v139);
    }
  }
  v174 = 0;
  v13 = (*(__int64 (__fastcall **)(struct DiagnosticsClient *, __int128 *, __int64))(*(_QWORD *)v2 + 72LL))(
          v2,
          &v174,
          v7);
  if ( v13 < 0 )
  {
    if ( *(_QWORD *)v3 )
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)v3 + 56LL))(*(_QWORD *)v3, (unsigned int)v13, 0);
    return (unsigned int)v13;
  }
  v14 = std::_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>::find(
          (char *)v3 + 8,
          &v149,
          &v174);
  if ( *(_QWORD *)v14 == *((_QWORD *)v3 + 1)
    || (v15 = *(NdfTelemetryProviderSingleton **)(*(_QWORD *)v14 + 48LL), (v155 = v15) == 0) )
  {
    if ( *(_QWORD *)v3 )
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)v3 + 56LL))(*(_QWORD *)v3, 2147942487LL, 0);
    return 2147942487LL;
  }
  v162 = (struct tagHELPER_ATTRIBUTE *)((char *)v15 + 92);
  v163 = v2;
  TickCount = (_QWORD *)ATL::CFileTime::GetTickCount((struct _FILETIME *)&v149);
  v159 = (const wchar_t *)((char *)v15 + 64);
  *((_QWORD *)v15 + 8) = *TickCount;
  RepairOptions = 0;
  NetworkIncident::InitializeTracing(v15, *((struct IUnknown **)v3 + 3));
  v149 = (NdfTelemetryProviderSingleton *)((char *)v15 + 128);
  v152 = (char *)v15 + 128;
  v18 = (struct tagHELPER_ATTRIBUTE *)((char *)v15 + 24);
  v151 = (volatile signed __int32 *)((char *)v15 + 24);
  if ( !*((_DWORD *)v15 + 6) )
  {
    v133 = 0;
    v134 = 0;
    pv = 0;
    *(_DWORD *)v138 = 0;
    v13 = (**(__int64 (__fastcall ***)(struct DiagnosticsClient *, LPVOID *))v2)(v2, &pv);
    if ( v13 < 0 )
    {
      if ( !*(_QWORD *)v3 )
      {
LABEL_22:
        CTraceAutoSuspend::~CTraceAutoSuspend((CTraceAutoSuspend *)&v152);
        v132[0] = *((_WORD *)v15 + 46);
        WdiAddParameter(*((_QWORD *)v2 + 1), 0, L"NDFStopStatus", 2, v132);
        return (unsigned int)v13;
      }
LABEL_21:
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)v3 + 56LL))(*(_QWORD *)v3, (unsigned int)v13, 0);
      goto LABEL_22;
    }
    v13 = (*(__int64 (__fastcall **)(struct DiagnosticsClient *, unsigned int *, struct tagHELPER_ATTRIBUTE **))(*(_QWORD *)v2 + 8LL))(
            v2,
            &v133,
            &v134);
    if ( v13 < 0
      || (v13 = (*(__int64 (__fastcall **)(struct DiagnosticsClient *, char *))(*(_QWORD *)v2 + 16LL))(v2, v138), v13 < 0) )
    {
      if ( pv )
        CoTaskMemFree(pv);
      if ( !*(_QWORD *)v3 )
        goto LABEL_22;
      goto LABEL_21;
    }
    *(_OWORD *)v145 = 0;
    LODWORD(v146) = 0;
    v20 = 0;
    v144 = 0;
    v21 = v133;
    v22 = v134;
    v23 = 0;
    v24 = 0;
    if ( v133 )
    {
      while ( v23 >= 0 )
      {
        v23 = HelperAttributeList::AddItem((HelperAttributeList *)v145, &v22[v24++]);
        if ( v24 >= v21 )
        {
          if ( v23 < 0 )
            break;
          goto LABEL_33;
        }
      }
    }
    else
    {
LABEL_33:
      if ( (int)HelperAttributeList::GetAttribute((HelperAttributeList *)v145, v19, &v144) >= 0 )
        HelperAttributeList::Remove((HelperAttributeList *)v145, v25);
      if ( (unsigned int)v146 < v133 )
      {
        v142 = 0;
        v141 = 0;
        All = HelperAttributeList::GetAll((HelperAttributeList *)v145, &v142, &v141);
        if ( (int)(All + 0x80000000) < 0 || All == -2147024664 )
        {
          FreeHelperAttributes(v134, v133, 1);
          v134 = v142;
          v133 = v141;
        }
      }
      v20 = v144;
    }
    v27 = v153;
    if ( *(_QWORD *)v153 )
    {
      (*(void (__fastcall **)(_QWORD, LPVOID, _QWORD, struct tagHELPER_ATTRIBUTE *))(**(_QWORD **)v153 + 40LL))(
        *(_QWORD *)v153,
        pv,
        v133,
        v134);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v142);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (__int64)&v142,
        (__int64)L"Network Diagnostics Engine Version %s",
        L"1.0");
      v28 = *(__int64 **)v27;
      v29 = **(_QWORD **)v27;
      v30 = v142;
      (*(void (__fastcall **)(__int64 *, __int64, struct tagHELPER_ATTRIBUTE *))(v29 + 96))(v28, 6, v142);
      ATL::CStringData::Release((ATL::CStringData *)((char *)&v30[-1].OctetString + 104));
    }
    v31 = (NdfTelemetryProviderSingleton *)*((_QWORD *)v15 + 15);
    if ( v31 )
      (*(void (__fastcall **)(NdfTelemetryProviderSingleton *, const wchar_t *))(*(_QWORD *)v31 + 176LL))(v31, L"1.0");
    NdfTelemetryProviderSingleton::AddHelperClass(v31, (const unsigned __int16 *)pv);
    v32 = v138[0];
    v33 = v134;
    v34 = v133;
    v35 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                      (__int64)&v139,
                      (__int64)pv);
    RepairOptions = NetworkIncident::Initialize(v15, v35, v34, (__int64)v33, v32);
    CoTaskMemFree(pv);
    if ( v134 )
      FreeHelperAttributes(v134, v133, 1);
    if ( RepairOptions >= 0 )
    {
      _InterlockedCompareExchange(v151, 1, 0);
      if ( !v20 )
      {
LABEL_53:
        HelperAttributeList::~HelperAttributeList((HelperAttributeList *)v145);
        v2 = v158;
        v3 = v153;
        v18 = (struct tagHELPER_ATTRIBUTE *)v151;
        goto LABEL_54;
      }
      v36 = *((_QWORD *)v15 + 15);
      if ( v36 )
      {
        (*(void (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v36 + 232LL))(v36, v20->Int64);
        if ( *(_QWORD *)v153 )
          (*(void (**)(_QWORD, __int64, const wchar_t *, ...))(**(_QWORD **)v153 + 104LL))(
            *(_QWORD *)v153,
            6,
            L"Caller application is %s",
            v20->Int64);
      }
    }
    if ( v20 )
      FreeHelperAttributes(v20, 1u, 1);
    goto LABEL_53;
  }
LABEL_54:
  v37 = v3;
  v150 = v3;
  v144 = v162;
  v38 = v18;
  v142 = v18;
  v39 = (char *)v15;
  pv = v15;
  v147[0] = 0;
  v160 = 0;
  if ( RepairOptions < 0 )
    goto LABEL_73;
  while ( 1 )
  {
    v141 = 0;
    _InterlockedCompareExchange((volatile signed __int32 *)v18, 2, 1);
    if ( LODWORD(v38->pwszName) == 13 )
    {
      if ( *(_QWORD *)v3 )
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)v3 + 48LL))(*(_QWORD *)v3, 6, 2147500037LL);
      CTraceAutoSuspend::~CTraceAutoSuspend((CTraceAutoSuspend *)&v152);
      v132[0] = (unsigned __int16)v162->pwszName;
      WdiAddParameter(*((_QWORD *)v163 + 1), 0, L"NDFStopStatus", 2, v132);
      return 2147500037LL;
    }
    v40 = NetworkIncident::Diagnose(v15, (int *)&v141);
    RepairOptions = v40;
    if ( v40 >= 0 )
      break;
    if ( v40 != -2147483638 )
      goto LABEL_72;
    _InterlockedCompareExchange(v151, 3, 2);
    if ( LODWORD(v142->pwszName) == 13 )
      goto LABEL_63;
    v115 = WaitForSingleObject(*((HANDLE *)v15 + 9), 1000 * v141);
    if ( v115 == 258 )
    {
      NetworkIncident::CheckDeferredProblems(v15);
    }
    else if ( !v115 )
    {
      goto LABEL_63;
    }
    v18 = (struct tagHELPER_ATTRIBUTE *)v151;
    _InterlockedCompareExchange(v151, 2, 3);
    if ( !v141 )
      goto LABEL_72;
    v38 = v142;
    if ( LODWORD(v142->pwszName) == 13 )
    {
      v41 = (int *)((char *)v15 + 96);
      goto LABEL_213;
    }
  }
  if ( ((*(_DWORD *)(*(_QWORD *)pv + 32LL) - 8) & 0xFFFFFFFB) == 0 )
  {
    RepairOptions = 1;
    *(_DWORD *)v138 = 1;
    goto LABEL_189;
  }
  RepairOptions = NetworkIncident::FindRepairOptions(v15, v147, (int **)&v160);
  *(_DWORD *)v132 = RepairOptions;
  if ( RepairOptions < 0 )
  {
LABEL_72:
    v39 = (char *)pv;
LABEL_73:
    v41 = (int *)(v39 + 96);
    if ( RepairOptions != -2147467260 )
    {
LABEL_213:
      v152 = 0;
      CTraceController::Stop(v149);
      LOWORD(v144->pwszName) = 0;
      *v41 = RepairOptions;
      NetworkDiagnosticsEngine::SendReport(v3, v15);
      goto LABEL_214;
    }
LABEL_74:
    LOWORD(v144->pwszName) = 6;
    *v41 = -2147467260;
    goto LABEL_214;
  }
  if ( LODWORD(v142->pwszName) == 13 )
  {
LABEL_63:
    RepairOptions = -2147467260;
    v41 = (int *)((char *)v15 + 96);
    goto LABEL_74;
  }
  *(_DWORD *)v138 = 0;
  v135 = NLM_CONNECTIVITY_DISCONNECTED;
  if ( !*((_DWORD *)v15 + 28) )
  {
    if ( !*((_DWORD *)v15 + 22) )
    {
      RepairOptions = 1;
      if ( *(_QWORD *)v3 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v139);
        (*(void (__fastcall **)(_QWORD, _QWORD, const wchar_t *))(**(_QWORD **)v3 + 96LL))(
          *(_QWORD *)v3,
          0,
          L"No instance confirmed, and no workarounds were returned. The 'no issues' UI will be shown.");
        ATL::CStringData::Release((ATL::CStringData *)(v139 - 3));
      }
      goto LABEL_189;
    }
LABEL_69:
    RepairOptions = (*(__int64 (__fastcall **)(struct DiagnosticsClient *, _QWORD))(*(_QWORD *)v2 + 24LL))(
                      v2,
                      *(_QWORD *)(*((_QWORD *)v15 + 7) + 80LL));
    *(_DWORD *)v132 = RepairOptions;
    if ( RepairOptions < 0 )
    {
      if ( *(_QWORD *)v3 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v142);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          (__int64)&v142,
          (__int64)L"Failed while adding the root cause string to the diagnostics client. HR=%x",
          (unsigned int)RepairOptions);
        v42 = v142;
        (*(void (__fastcall **)(_QWORD, _QWORD, struct tagHELPER_ATTRIBUTE *))(**(_QWORD **)v3 + 96LL))(
          *(_QWORD *)v3,
          0,
          v142);
        ATL::CStringData::Release((ATL::CStringData *)((char *)&v42[-1].OctetString + 104));
      }
      goto LABEL_72;
    }
    goto LABEL_77;
  }
  if ( *((_DWORD *)v15 + 22) )
    goto LABEL_69;
  *(_DWORD *)v138 = 1;
  v135 = NLM_CONNECTIVITY_IPV4_NOTRAFFIC;
  if ( *(_QWORD *)v3 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v139);
    (*(void (__fastcall **)(_QWORD, _QWORD, const wchar_t *))(**(_QWORD **)v3 + 96LL))(
      *(_QWORD *)v3,
      0,
      L"No instance confirmed, but workarounds were returned. The workaround UI will be shown.");
    ATL::CStringData::Release((ATL::CStringData *)(v139 - 3));
  }
LABEL_77:
  v139 = v15;
  v43 = 96;
  memset_0(&v175, 0, 0x60u);
  memset_0(v177, 0, sizeof(v177));
  v44 = 96;
  v45 = &v175;
  do
  {
    *(_BYTE *)v45 = 0;
    v45 = (struct tagRepairInfo **)((char *)v45 + 1);
    --v44;
  }
  while ( v44 );
  v46 = v177;
  do
  {
    *(_BYTE *)v46 = 0;
    v46 = (struct ProblemNode **)((char *)v46 + 1);
    --v43;
  }
  while ( v43 );
  std::queue<int>::queue<int,std::deque<int>>(v167);
  std::queue<int>::queue<int,std::deque<int>>(v170);
  v164 = 0;
  v165 = 0;
  v166 = 0;
  *(_QWORD *)&v166 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ProblemNode * const,tagRepairInfoEx>>>::_Buyheadnode();
  v47 = 0;
  v137 = 0;
  if ( v147[0] > 0 )
  {
    while ( 1 )
    {
      v143[0] = *((_DWORD *)v160 + v47);
      v48 = v143[0];
      v49 = v139;
      std::deque<ProblemNode *>::push_back(v167, v139[4] + 8LL * v143[0]);
      std::deque<int>::push_back(v170, v143);
      RepairOptions = CRootCauseInfoCollector::AddRootCauseAndRepair(
                        (CRootCauseInfoCollector *)&v164,
                        *(struct ProblemNode **)(v49[4] + 8 * v48),
                        0,
                        0);
      *(_DWORD *)v132 = RepairOptions;
      if ( RepairOptions < 0 )
        break;
      v47 = v137 + 1;
      v137 = v47;
      if ( v47 >= v147[0] )
        goto LABEL_87;
    }
    v50 = v150;
    if ( *(_QWORD *)v150 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v134);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (__int64)&v134,
        (__int64)L"Failed while adding the root cause to the collector. HR=%x",
        (unsigned int)RepairOptions);
      v51 = *(__int64 **)v50;
      v52 = **(_QWORD **)v50;
      v53 = v134;
      (*(void (__fastcall **)(__int64 *, _QWORD, struct tagHELPER_ATTRIBUTE *))(v52 + 96))(v51, 0, v134);
      ATL::CStringData::Release((ATL::CStringData *)((char *)&v53[-1].OctetString + 104));
    }
  }
LABEL_87:
  v137 = 0;
  v133 = 0;
  do
  {
    if ( !v169 || RepairOptions < 0 )
      break;
    std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(
      (std::_Iterator_base12 *)v145,
      v168,
      (const struct std::_Container_base12 *)v167);
    if ( *(_QWORD *)v145 )
      v54 = **(_QWORD **)v145;
    else
      v54 = 0;
    v55 = *(struct ProblemNode **)(*(_QWORD *)(*(_QWORD *)(v54 + 8) + 8 * ((v146 >> 1) & (*(_QWORD *)(v54 + 16) - 1LL)))
                                 + 8 * (v146 & 1));
    *(_QWORD *)v145 = v55;
    if ( v169 )
    {
      if ( --v169 )
        ++v168;
      else
        v168 = 0;
    }
    v56 = v171;
    v173 = 0;
    std::_Iterator_base12::_Adopt((std::_Iterator_base12 *)&v173, (const struct std::_Container_base12 *)v170);
    if ( v173 )
      v57 = *v173;
    else
      v57 = 0;
    LODWORD(v148) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v57 + 8) + 8 * ((v56 >> 2) & (*(_QWORD *)(v57 + 16) - 1LL)))
                              + 4 * (v56 & 3));
    LODWORD(v134) = (_DWORD)v148;
    if ( v172 )
    {
      if ( --v172 )
        ++v171;
      else
        v171 = 0;
    }
    if ( v55 && *((_DWORD *)v55 + 24) != 4 )
    {
      v58 = *(__int64 **)v55;
      if ( *(_DWORD *)(*(_QWORD *)v55 + 104LL) )
      {
        v59 = 0;
        v143[0] = 0;
        v60 = v133;
        while ( v60 < 12 )
        {
          v61 = (struct tagRepairInfo *)(v58[14] + 112 * v59);
          if ( (unsigned int)IsDuplicateRepair(v61, &v175) )
          {
            if ( *(_QWORD *)v3 )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v154);
              v68 = *(_QWORD *)(*(_QWORD *)v55 + 16LL);
              if ( !*(_DWORD *)(v68 - 16) )
                v68 = **(_QWORD **)v55;
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                (__int64)&v154,
                (__int64)L"Duplicate Repair. HelperClass: %s, Description: %s",
                v68,
                v61->pwszDescription);
              v69 = *(_QWORD *)(*(_QWORD *)v55 + 40LL);
              v70 = v154;
              (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**(_QWORD **)v3 + 112LL))(
                *(_QWORD *)v3,
                0,
                v154,
                v69);
              ATL::CStringData::Release((ATL::CStringData *)(v70 - 24));
              v55 = *(struct ProblemNode **)v145;
            }
            CRootCauseInfoCollector::RemoveRootCause((CRootCauseInfoCollector *)&v164, v55);
            break;
          }
          v62 = v137;
          if ( (v61->flags & 0x200000) == 0 )
            v62 = 1;
          v137 = v62;
          v61->rootCauseIndex = (int)v148;
          v63 = 0;
          while ( 1 )
          {
            v64 = v63;
            v65 = v176[v63 - 1];
            if ( !v65 )
              break;
            if ( (*((_DWORD *)v65 + 10) & 0x20000000) != 0 && (v61->flags & 0x20000000) == 0 )
            {
              for ( i = 10; i >= 0; --i )
              {
                v67 = v176[(unsigned int)i - 1];
                if ( v67 )
                {
                  if ( (*((_DWORD *)v67 + 10) & 0x20000000) == 0 )
                    break;
                  v176[i] = v67;
                  v177[(unsigned int)i + 1] = v177[i];
                }
              }
              v176[v64 - 1] = (struct ProblemNode *)v61;
              v177[v64] = v55;
              v60 = v133;
              goto LABEL_126;
            }
            if ( (int)++v63 >= 12 )
            {
              v60 = v133;
              goto LABEL_118;
            }
          }
          v176[v63 - 1] = (struct ProblemNode *)v61;
          v177[v63] = v55;
          v60 = v133;
          if ( (v61->flags & 0x20000000) == 0 )
LABEL_126:
            v133 = ++v60;
LABEL_118:
          v59 = (unsigned int)(v143[0] + 1);
          v143[0] = v59;
          v58 = *(__int64 **)v55;
          if ( (unsigned int)v59 >= *(_DWORD *)(*(_QWORD *)v55 + 104LL) )
            break;
        }
      }
      *((_DWORD *)v55 + 24) = 4;
    }
    v71 = (_QWORD *)**((_QWORD **)v55 + 8);
    v72 = *(_QWORD *)v145;
    while ( v71 != *(_QWORD **)(v72 + 64) )
    {
      v73 = v71[2];
      v71 = (_QWORD *)*v71;
      *(_QWORD *)v145 = v73;
      if ( *(_DWORD *)(v73 + 96) != 4 )
      {
        std::deque<ProblemNode *>::push_back(v167, v145);
        std::deque<int>::push_back(v170, &v134);
      }
    }
  }
  while ( (int)v133 < 12 );
  v74 = 0;
  v75 = v158;
  while ( 1 )
  {
    v133 = v74;
    if ( v74 >= 0xC )
      break;
    v154 = (int)v74;
    v76 = v176[(int)v74 - 1];
    v134 = (struct tagHELPER_ATTRIBUTE *)v76;
    if ( !v76 )
      goto LABEL_164;
    v77 = *((_DWORD *)v76 + 10);
    if ( (v77 & 0x40000000) != 0 )
    {
      *((_DWORD *)v76 + 10) = v77 | 0x20000000;
    }
    else if ( (v77 & 0x200000) != 0 && v137 )
    {
      if ( *(_QWORD *)v3 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v145);
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            (__int64)v145,
            (__int64)L"Skipping repro repair from %s as other repairs exist in the scenario. ",
            *((_QWORD *)v76 + 2));
          v82 = *(_QWORD *)v145;
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)v3 + 112LL))(
            *(_QWORD *)v3,
            0,
            *(_QWORD *)v145,
            *(_QWORD *)(*(_QWORD *)v177[v154] + 40LL));
          ATL::CStringData::Release((ATL::CStringData *)(v82 - 24));
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', 0) )
          {
            RepairOptions = *(_DWORD *)v132;
            v15 = v155;
            *(_DWORD *)v138 = v135;
            v3 = v153;
            v75 = v156;
            v158 = v156;
            __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180019AAC);
          }
        }
      }
      goto LABEL_164;
    }
    RepairOptions = (*(__int64 (__fastcall **)(struct DiagnosticsClient *, struct ProblemNode *))(*(_QWORD *)v75 + 32LL))(
                      v75,
                      v76);
    if ( RepairOptions < 0 )
    {
      v78 = v150;
      if ( *(_QWORD *)v150 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v145);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          (__int64)v145,
          (__int64)L"Failed while adding a repair to the diagnostics client. HR=%x",
          (unsigned int)RepairOptions);
        v79 = *(__int64 **)v78;
        v80 = **(_QWORD **)v78;
        v81 = *(_QWORD *)v145;
        (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))(v80 + 96))(v79, 0, *(_QWORD *)v145);
        goto LABEL_148;
      }
      goto LABEL_166;
    }
    v132[0] = 0;
    v83 = IntToUShort(v133 + 1, v132);
    if ( v83 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, v84, v85, (const char *)(unsigned int)v83, v130);
    v148 = v177[v154];
    RepairOptions = CRootCauseInfoCollector::AddRootCauseAndRepair(
                      (CRootCauseInfoCollector *)&v164,
                      v148,
                      (struct tagRepairInfo *)v76,
                      v132[0]);
    *(_DWORD *)v132 = RepairOptions;
    v86 = v150;
    v87 = *(_QWORD **)v150;
    if ( RepairOptions < 0 )
    {
      if ( v87 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v145);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          (__int64)v145,
          (__int64)L"Failed while adding the repair and root cause to the collector. HR=%x",
          (unsigned int)RepairOptions);
        v88 = *(__int64 **)v86;
        v89 = **(_QWORD **)v86;
        v81 = *(_QWORD *)v145;
        (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))(v89 + 96))(v88, 0, *(_QWORD *)v145);
LABEL_148:
        ATL::CStringData::Release((ATL::CStringData *)(v81 - 24));
      }
LABEL_166:
      CRootCauseInfoCollector::~CRootCauseInfoCollector((CRootCauseInfoCollector *)&v164);
      std::deque<int>::~deque<int>(v170);
      std::deque<ProblemNode *>::~deque<ProblemNode *>((__int64)v167);
      goto LABEL_72;
    }
    v90 = v134;
    if ( v87 && *((int *)&v134->OctetString + 6) >= 0 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v143);
      v91 = L"Workaround";
      if ( (*((_DWORD *)&v90->OctetString + 6) & 0x20000000) == 0 )
        v91 = L"Repair";
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (__int64)v143,
        (__int64)L"%s below from %s",
        v91,
        v90->Int64);
      v92 = *(_QWORD *)v143;
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)v3 + 112LL))(
        *(_QWORD *)v3,
        0,
        *(_QWORD *)v143,
        *(_QWORD *)(*(_QWORD *)v148 + 40LL));
      (*(void (__fastcall **)(_QWORD, _QWORD, BYTE *))(**(_QWORD **)v3 + 96LL))(
        *(_QWORD *)v3,
        0,
        v134->OctetString.lpValue);
      (*(void (__fastcall **)(_QWORD, _QWORD, struct tagHELPER_ATTRIBUTE *))(**(_QWORD **)v3 + 72LL))(
        *(_QWORD *)v3,
        *(_QWORD *)v148,
        v134);
      ATL::CStringData::Release((ATL::CStringData *)(v92 - 24));
      v90 = v134;
    }
    v93 = *((_QWORD *)v15 + 15);
    if ( v93 )
    {
      (*(void (__fastcall **)(__int64, struct tagHELPER_ATTRIBUTE *, _QWORD))(*(_QWORD *)v93 + 184LL))(v93, v90, v133);
      (*(void (__fastcall **)(_QWORD, struct tagHELPER_ATTRIBUTE *, struct ProblemNode *))(**((_QWORD **)v15 + 15)
                                                                                         + 200LL))(
        *((_QWORD *)v15 + 15),
        v90,
        v148);
    }
LABEL_164:
    v74 = v133 + 1;
  }
  if ( RepairOptions < 0 )
    goto LABEL_166;
  v94 = wil::safe_cast_failfast<int,unsigned __int64,0>((__int64)(*((_QWORD *)&v164 + 1) - v164) >> 3);
  v143[0] = v94;
  if ( v94 > 0 )
  {
    v95 = (__int64)v94 << 6;
    v96 = (struct tagRootCauseInfo *)CoTaskMemAlloc(v95);
    v97 = v96;
    v156 = (struct DiagnosticsClient *)v96;
    if ( v96 )
    {
      *(_QWORD *)v145 = v96;
      v98 = v143[0];
      v145[2] = v143[0];
      v145[3] = 1;
      for ( j = v97; v95; --v95 )
      {
        LOBYTE(j->pwszDescription) = 0;
        j = (struct tagRootCauseInfo *)((char *)j + 1);
      }
      RepairOptions = CRootCauseInfoCollector::GetRootCauseInfoList((struct ProblemInstance ****)&v164, v97, v98);
      if ( RepairOptions >= 0 )
      {
        v100 = 0;
        v135 = NLM_CONNECTIVITY_DISCONNECTED;
        while ( 1 )
        {
          v101 = (char *)v156 + 64 * (unsigned __int64)(unsigned int)v100;
          RepairOptions = (*(__int64 (__fastcall **)(struct DiagnosticsClient *, char *))(*(_QWORD *)v75 + 40LL))(
                            v75,
                            v101);
          if ( RepairOptions < 0 )
            break;
          v132[0] = 0;
          if ( *((_WORD *)v101 + 28) )
          {
            v102 = 0;
            v103 = v139;
            do
            {
              v155 = (NdfTelemetryProviderSingleton *)(120LL * v102);
              NdfTelemetryProviderSingleton::AddRepairGuid(
                v155,
                (const struct _GUID *)((char *)v155 + *((_QWORD *)v101 + 6)));
              v104 = v103[15];
              if ( v104 )
                (*(void (__fastcall **)(__int64, char *, char *))(*(_QWORD *)v104 + 192LL))(
                  v104,
                  (char *)v155 + *((_QWORD *)v101 + 6),
                  v101);
              ++v102;
            }
            while ( v102 < *((_WORD *)v101 + 28) );
            v75 = v158;
            v3 = v153;
          }
          v100 = v135 + 1;
          v135 = v100;
          if ( v100 >= v143[0] )
            goto LABEL_184;
        }
        v105 = v150;
        if ( *(_QWORD *)v150 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v139);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            (__int64)&v139,
            (__int64)L"Failed while adding a RootCauseInfo to the diagnostics client. HR=%x",
            (unsigned int)RepairOptions);
          v106 = *(__int64 **)v105;
          v107 = **(_QWORD **)v105;
          v108 = v139;
          (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD *))(v107 + 96))(v106, 0, v139);
          ATL::CStringData::Release((ATL::CStringData *)(v108 - 3));
        }
      }
LABEL_184:
      TNDFDeallocator<tagRootCauseInfo *,&void FreeRootCauseInfos(tagRootCauseInfo *,unsigned long,int)>::~TNDFDeallocator<tagRootCauseInfo *,&void FreeRootCauseInfos(tagRootCauseInfo *,unsigned long,int)>(v145);
      if ( RepairOptions < 0 )
        goto LABEL_166;
    }
  }
  v109 = *((_QWORD *)v15 + 15);
  if ( v109 )
    (*(void (__fastcall **)(__int64, struct tagRepairInfo *, struct ProblemNode *, struct ProblemNode *))(*(_QWORD *)v109 + 72LL))(
      v109,
      v175,
      v176[0],
      v176[1]);
  CRootCauseInfoCollector::~CRootCauseInfoCollector((CRootCauseInfoCollector *)&v164);
  std::deque<int>::~deque<int>(v170);
  std::deque<ProblemNode *>::~deque<ProblemNode *>((__int64)v167);
  v37 = v150;
LABEL_189:
  if ( *((_QWORD *)v15 + 15) )
  {
    v110 = (_QWORD *)ATL::CFileTime::GetTickCount((struct _FILETIME *)&v149);
    (*(void (__fastcall **)(_QWORD, unsigned __int64))(**((_QWORD **)v15 + 15) + 88LL))(
      *((_QWORD *)v15 + 15),
      (*v110 - (unsigned __int64)*(unsigned int *)v159) / 0x989680);
  }
  if ( RepairOptions == 1 )
  {
    LOWORD(v144->pwszName) = 10;
  }
  else if ( *((_DWORD *)v15 + 28) )
  {
    LOWORD(v144->pwszName) = 3;
  }
  else
  {
    LOWORD(v144->pwszName) = 13;
  }
  *((_DWORD *)v15 + 24) = RepairOptions;
  if ( RepairOptions )
  {
    _InterlockedCompareExchange(v151, 14, 2);
    if ( *(_QWORD *)v37 )
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)v37 + 64LL))(*(_QWORD *)v37, 0, 0);
  }
  else
  {
    _InterlockedCompareExchange(v151, 4, 2);
    v111 = *(_QWORD *)v37;
    if ( *(_QWORD *)v37 )
    {
      v112 = *(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v111 + 64LL);
      v113 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>((__int64)(*((_QWORD *)v15 + 5)
                                                                               - *((_QWORD *)v15 + 4)) >> 3);
      v112(v111, v113, (char *)v15 + 32);
      if ( LODWORD(v142->pwszName) == 13 )
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)v150 + 48LL))(*(_QWORD *)v150, 6, 2147500037LL);
    }
  }
  *(struct _FILETIME *)((char *)v15 + 100) = *ATL::CFileTime::GetTickCount((struct _FILETIME *)&v149);
  if ( *(_DWORD *)v138 )
  {
    v114 = *((_QWORD *)v15 + 15);
    if ( v114 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v114 + 128LL))(v114, 0);
  }
LABEL_214:
  v116 = v147[0];
  AcquireSRWLockExclusive(&stru_180041D10);
  dword_180041DA0 += v116;
  ReleaseSRWLockExclusive(&stru_180041D10);
  v118 = (NdfTelemetryProviderSingleton *)NdfTelemetryProviderSingleton::OutputHelperClasses(v117);
  v120 = NdfTelemetryProviderSingleton::OutputRepairGuids(v119);
  v121 = dword_180041DA0;
  LODWORD(v134) = (unsigned __int16)word_180041DA4;
  v122 = GetTickCount64();
  LOBYTE(v132[0]) = 0;
  if ( (int)NetworkDiagnosticsEngine::GetNLMStatus(v123, &v140, (unsigned __int8 *)v132) < 0 )
  {
    v125 = 0;
    v124 = L"Unknown";
  }
  else
  {
    v124 = GetNLMStatusString(v140);
    v125 = v132[0];
  }
  v126 = CallbackContext;
  if ( *(_DWORD *)CallbackContext > 5u )
  {
    v127 = (NdfTelemetryProviderSingleton *)*((_QWORD *)CallbackContext + 3);
    if ( (*((_QWORD *)CallbackContext + 2) & 0x800000000000LL) != 0
      && (NdfTelemetryProviderSingleton *)((unsigned __int64)v127 & 0x800000000000LL) == v127 )
    {
      LODWORD(v148) = RepairOptions;
      TickCount64 = v122 - TickCount64;
      LOBYTE(v132[0]) = v125;
      v149 = SessionGuid;
      v135 = v140;
      v159 = v124;
      v156 = (struct DiagnosticsClient *)v120;
      v143[0] = v121;
      v155 = v118;
      SessionGuid = (CTraceController *)NdfTelemetryProviderSingleton::GetSessionGuid(v127);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v126,
        (__int64)byte_180039A19,
        v128,
        v129,
        (__int64)&SessionGuid,
        &v155,
        (__int64)v143,
        &v156,
        &v159,
        (__int64)&v135,
        &v149);
    }
  }
  if ( v160 )
    CoTaskMemFree(v160);
  CTraceAutoSuspend::~CTraceAutoSuspend((CTraceAutoSuspend *)&v152);
  v132[0] = (unsigned __int16)v162->pwszName;
  WdiAddParameter(*((_QWORD *)v163 + 1), 0, L"NDFStopStatus", 2, v132);
  return (unsigned int)RepairOptions;
}

```

## disassembly

```asm
0x180018ae4  mov     [rsp+arg_0], rbx
0x180018ae9  mov     [rsp+arg_10], rsi
0x180018aee  push    rdi
0x180018aef  push    r12
0x180018af1  push    r13
0x180018af3  push    r14
0x180018af5  push    r15
0x180018af7  sub     rsp, 300h
0x180018afe  mov     rax, cs:__security_cookie
0x180018b05  xor     rax, rsp
0x180018b08  mov     [rsp+328h+var_38], rax
0x180018b10  mov     rdi, rdx
0x180018b13  mov     [rsp+328h+var_1C8], rdx
0x180018b1b  mov     [rsp+328h+var_1D8], rdx
0x180018b23  mov     r13, cs:qword_180041BB8
0x180018b2a  mov     [rsp+328h+var_1F0], r13
0x180018b32  xor     r14d, r14d
0x180018b35  test    rdx, rdx
0x180018b38  jnz     short loc_180018B61
0x180018b3a  mov     rcx, [r13+0]
0x180018b3e  test    rcx, rcx
0x180018b41  jz      short loc_180018B57
0x180018b43  mov     rax, [rcx]
0x180018b46  xor     r8d, r8d
0x180018b49  mov     edx, 80070006h
0x180018b4e  mov     rax, [rax+38h]
0x180018b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b57  mov     eax, 80070006h
0x180018b5c  jmp     loc_18001A447
0x180018b61  call    cs:__imp_GetTickCount64
0x180018b67  mov     [rsp+328h+var_1B0], rax
0x180018b6f  mov     [rsp+328h+var_258], r14d
0x180018b77  mov     [rsp+328h+var_298], r14b
0x180018b7f  lea     r8, [rsp+328h+var_298]; unsigned __int8 *
0x180018b87  lea     rdx, [rsp+328h+var_258]; enum NLM_CONNECTIVITY *
0x180018b8f  call    ?GetNLMStatus@NetworkDiagnosticsEngine@@AEAAJPEAW4NLM_CONNECTIVITY@@PEAE@Z; NetworkDiagnosticsEngine::GetNLMStatus(NLM_CONNECTIVITY *,uchar *)
0x180018b94  mov     ecx, [rsp+328h+var_258]; enum NLM_CONNECTIVITY
0x180018b9b  mov     [rsp+328h+var_21C], ecx
0x180018ba2  test    eax, eax
0x180018ba4  js      short loc_180018BB8
0x180018ba6  call    ?GetNLMStatusString@@YAPEBGW4NLM_CONNECTIVITY@@@Z; GetNLMStatusString(NLM_CONNECTIVITY)
0x180018bab  mov     rdx, rax
0x180018bae  mov     r8b, [rsp+328h+var_298]
0x180018bb6  jmp     short loc_180018BCA
0x180018bb8  lea     rdx, aUnknown; "Unknown"
0x180018bbf  mov     r8b, r14b
0x180018bc2  mov     [rsp+328h+var_298], r14b
0x180018bca  mov     [rsp+328h+var_1D0], rdx
0x180018bd2  mov     rbx, cs:CallbackContext
0x180018bd9  mov     eax, [rbx]
0x180018bdb  cmp     eax, 5
0x180018bde  jbe     loc_180018C74
0x180018be4  mov     rcx, [rbx+18h]; this
0x180018be8  mov     rax, [rbx+10h]
0x180018bec  mov     r9, 400000000000h
0x180018bf6  test    r9, rax
0x180018bf9  jz      short loc_180018C74
0x180018bfb  mov     rax, rcx
0x180018bfe  and     rax, r9
0x180018c01  cmp     rax, rcx
0x180018c04  jnz     short loc_180018C74
0x180018c06  mov     eax, [rsp+328h+var_258]
0x180018c0d  mov     [rsp+328h+var_278], eax
0x180018c14  mov     byte ptr [rsp+328h+var_290], r8b
0x180018c1c  mov     [rsp+328h+var_260], rdx
0x180018c24  call    ?GetSessionGuid@NdfTelemetryProviderSingleton@@QEAAAEBU_GUID@@XZ; NdfTelemetryProviderSingleton::GetSessionGuid(void)
0x180018c29  mov     qword ptr [rsp+328h+var_238], rax
0x180018c31  lea     rax, [rsp+328h+var_278]
0x180018c39  mov     [rsp+328h+var_2F0], rax
0x180018c3e  lea     rax, [rsp+328h+var_290]
0x180018c46  mov     [rsp+328h+var_2F8], rax
0x180018c4b  lea     rax, [rsp+328h+var_260]
0x180018c53  mov     [rsp+328h+var_300], rax
0x180018c58  lea     rax, [rsp+328h+var_238]
0x180018c60  mov     qword ptr [rsp+328h+var_308], rax; int
0x180018c65  lea     rdx, byte_180039B35
0x180018c6c  mov     rcx, rbx
0x180018c6f  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x180018c74  xorps   xmm0, xmm0
0x180018c77  movups  [rsp+328h+var_108], xmm0
0x180018c7f  mov     rax, [rdi]
0x180018c82  lea     rdx, [rsp+328h+var_108]
0x180018c8a  mov     rcx, rdi
0x180018c8d  mov     rax, [rax+48h]
0x180018c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c96  mov     ebx, eax
0x180018c98  test    eax, eax
0x180018c9a  jns     short loc_180018CC0
0x180018c9c  mov     r9, [r13+0]
0x180018ca0  test    r9, r9
0x180018ca3  jz      short loc_180018CB9
0x180018ca5  mov     rcx, [r9]
0x180018ca8  mov     rax, [rcx+38h]
0x180018cac  xor     r8d, r8d
0x180018caf  mov     edx, ebx
0x180018cb1  mov     rcx, r9
0x180018cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cb9  mov     eax, ebx
0x180018cbb  jmp     loc_18001A447
0x180018cc0  lea     r8, [rsp+328h+var_108]
0x180018cc8  lea     rdx, [rsp+328h+var_210]
0x180018cd0  lea     rcx, [r13+8]
0x180018cd4  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVNetworkIncident@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>::find(_GUID const &)
0x180018cd9  mov     r15, [rax]
0x180018cdc  cmp     r15, [r13+8]
0x180018ce0  jz      loc_18001A425
0x180018ce6  mov     r15, [r15+30h]
0x180018cea  mov     [rsp+328h+var_1E0], r15
0x180018cf2  test    r15, r15
0x180018cf5  jz      loc_18001A425
0x180018cfb  lea     r12, [r15+5Ch]
0x180018cff  mov     [rsp+328h+var_1A8], r12
0x180018d07  mov     [rsp+328h+var_1A0], rdi
0x180018d0f  lea     rcx, [rsp+328h+var_210]
0x180018d17  call    ?GetTickCount@CFileTime@ATL@@SA?AV12@XZ; ATL::CFileTime::GetTickCount(void)
0x180018d1c  lea     rcx, [r15+40h]
0x180018d20  mov     [rsp+328h+var_1C0], rcx
0x180018d28  mov     rax, [rax]
0x180018d2b  mov     [rcx], rax
0x180018d2e  mov     esi, r14d
0x180018d31  mov     rdx, [r13+18h]; struct INDFHelperClassRegistry *
0x180018d35  mov     rcx, r15; this
0x180018d38  call    ?InitializeTracing@NetworkIncident@@QEAAJPEAUINDFHelperClassRegistry@@@Z; NetworkIncident::InitializeTracing(INDFHelperClassRegistry *)
0x180018d3d  lea     rax, [r15+80h]
0x180018d44  mov     [rsp+328h+var_210], rax
0x180018d4c  mov     [rsp+328h+var_1F8], rax
0x180018d54  lea     rdx, [r15+18h]
0x180018d58  mov     [rsp+328h+var_200], rdx
0x180018d60  cmp     [rdx], r14d
0x180018d63  jnz     loc_180019152
0x180018d69  mov     [rsp+328h+var_288], r14d
0x180018d71  mov     [rsp+328h+var_280], r14
0x180018d79  mov     [rsp+328h+pv], r14
0x180018d81  mov     dword ptr [rsp+328h+var_264], r14d
0x180018d89  mov     rax, [rdi]
0x180018d8c  lea     rdx, [rsp+328h+pv]
0x180018d94  mov     rcx, rdi
0x180018d97  mov     rax, [rax]
0x180018d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d9f  mov     ebx, eax
0x180018da1  test    eax, eax
0x180018da3  jns     short loc_180018E09
0x180018da5  mov     r9, [r13+0]
0x180018da9  test    r9, r9
0x180018dac  jz      short loc_180018DC3
0x180018dae  mov     rcx, [r9]
0x180018db1  mov     rax, [rcx+38h]
0x180018db5  mov     rcx, r9
0x180018db8  mov     edx, ebx
0x180018dba  xor     r8d, r8d
0x180018dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dc2  nop
0x180018dc3  lea     rcx, [rsp+328h+var_1F8]; this
0x180018dcb  call    ??1CTraceAutoSuspend@@QEAA@XZ; CTraceAutoSuspend::~CTraceAutoSuspend(void)
0x180018dd0  nop
0x180018dd1  movzx   eax, word ptr [r12]
0x180018dd6  mov     [rsp+328h+var_290], ax
0x180018dde  lea     rax, [rsp+328h+var_290]
0x180018de6  mov     qword ptr [rsp+328h+var_308], rax
0x180018deb  mov     r9d, 2
0x180018df1  lea     r8, aNdfstopstatus; "NDFStopStatus"
0x180018df8  xor     edx, edx
0x180018dfa  mov     rcx, [rdi+8]
0x180018dfe  call    cs:__imp_WdiAddParameter
0x180018e04  jmp     loc_180018CB9
0x180018e09  mov     rax, [rdi]
0x180018e0c  lea     r8, [rsp+328h+var_280]
0x180018e14  lea     rdx, [rsp+328h+var_288]
0x180018e1c  mov     rcx, rdi
0x180018e1f  mov     rax, [rax+8]
0x180018e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e28  mov     ebx, eax
0x180018e2a  test    eax, eax
0x180018e2c  jns     short loc_180018E5A
0x180018e2e  mov     rcx, [rsp+328h+pv]; pv
0x180018e36  test    rcx, rcx
0x180018e39  jz      short loc_180018E41
0x180018e3b  call    cs:__imp_CoTaskMemFree
0x180018e41  mov     rcx, [r13+0]
0x180018e45  test    rcx, rcx
0x180018e48  jz      loc_180018DC3
0x180018e4e  mov     rax, [rcx]
0x180018e51  mov     rax, [rax+38h]
0x180018e55  jmp     loc_180018DB8
0x180018e5a  mov     rax, [rdi]
0x180018e5d  lea     rdx, [rsp+328h+var_264]
0x180018e65  mov     rcx, rdi
0x180018e68  mov     rax, [rax+10h]
0x180018e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e71  mov     ebx, eax
0x180018e73  test    eax, eax
0x180018e75  js      short loc_180018E2E
0x180018e77  xorps   xmm0, xmm0
0x180018e7a  movdqu  xmmword ptr [rsp+328h+var_238], xmm0
0x180018e83  mov     dword ptr [rsp+328h+var_228], r14d
0x180018e8b  mov     r13, r14
0x180018e8e  mov     [rsp+328h+var_240], r14
0x180018e96  mov     edi, [rsp+328h+var_288]
0x180018e9d  mov     rsi, [rsp+328h+var_280]
0x180018ea5  mov     eax, r14d
0x180018ea8  mov     ebx, r14d
0x180018eab  mov     r12d, 1
0x180018eb1  test    edi, edi
0x180018eb3  jz      short loc_180018EE6
0x180018eb5  test    eax, eax
0x180018eb7  js      loc_180018F99
0x180018ebd  mov     eax, ebx
0x180018ebf  lea     rdx, [rax+rax*8]
0x180018ec3  shl     rdx, 4
0x180018ec7  add     rdx, rsi; struct tagHELPER_ATTRIBUTE *
0x180018eca  lea     rcx, [rsp+328h+var_238]; this
0x180018ed2  call    ?AddItem@HelperAttributeList@@AEAAJAEBUtagHELPER_ATTRIBUTE@@@Z; HelperAttributeList::AddItem(tagHELPER_ATTRIBUTE const &)
0x180018ed7  add     ebx, r12d
0x180018eda  cmp     ebx, edi
0x180018edc  jb      short loc_180018EB5
0x180018ede  test    eax, eax
0x180018ee0  js      loc_180018F99
0x180018ee6  lea     r8, [rsp+328h+var_240]; struct tagHELPER_ATTRIBUTE **
0x180018eee  lea     rcx, [rsp+328h+var_238]; this
0x180018ef6  call    ?GetAttribute@HelperAttributeList@@QEAAJPEBGPEAPEAUtagHELPER_ATTRIBUTE@@@Z; HelperAttributeList::GetAttribute(ushort const *,tagHELPER_ATTRIBUTE * *)
0x180018efb  test    eax, eax
0x180018efd  js      short loc_180018F0C
0x180018eff  lea     rcx, [rsp+328h+var_238]; this
0x180018f07  call    ?Remove@HelperAttributeList@@QEAAJPEBG@Z; HelperAttributeList::Remove(ushort const *)
0x180018f0c  mov     eax, [rsp+328h+var_288]
0x180018f13  cmp     dword ptr [rsp+328h+var_228], eax
0x180018f1a  jnb     short loc_180018F91
0x180018f1c  mov     [rsp+328h+var_250], r14
0x180018f24  mov     [rsp+328h+var_254], r14d
0x180018f2c  lea     r8, [rsp+328h+var_254]; unsigned int *
0x180018f34  lea     rdx, [rsp+328h+var_250]; struct tagHELPER_ATTRIBUTE **
0x180018f3c  lea     rcx, [rsp+328h+var_238]; this
0x180018f44  call    ?GetAll@HelperAttributeList@@QEAAJPEAPEAUtagHELPER_ATTRIBUTE@@PEAK@Z; HelperAttributeList::GetAll(tagHELPER_ATTRIBUTE * *,ulong *)
0x180018f49  mov     edx, 80000000h
0x180018f4e  lea     ecx, [rax+rdx]
0x180018f51  test    edx, ecx
0x180018f53  jnz     short loc_180018F5C
0x180018f55  cmp     eax, 800700E8h
0x180018f5a  jnz     short loc_180018F91
0x180018f5c  mov     r8d, r12d; int
0x180018f5f  mov     edx, [rsp+328h+var_288]; unsigned int
0x180018f66  mov     rcx, [rsp+328h+var_280]; pv
0x180018f6e  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x180018f73  mov     rax, [rsp+328h+var_250]
0x180018f7b  mov     [rsp+328h+var_280], rax
0x180018f83  mov     eax, [rsp+328h+var_254]
0x180018f8a  mov     [rsp+328h+var_288], eax
0x180018f91  mov     r13, [rsp+328h+var_240]
0x180018f99  mov     rbx, [rsp+328h+var_1F0]
0x180018fa1  mov     rcx, [rbx]
0x180018fa4  test    rcx, rcx
0x180018fa7  jz      short loc_18001901F
0x180018fa9  mov     rax, [rcx]
0x180018fac  mov     r9, [rsp+328h+var_280]
0x180018fb4  mov     r8d, [rsp+328h+var_288]
0x180018fbc  mov     rdx, [rsp+328h+pv]
0x180018fc4  mov     rax, [rax+28h]
0x180018fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fcd  lea     rcx, [rsp+328h+var_250]
0x180018fd5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018fda  nop
0x180018fdb  lea     r8, a10; "1.0"
0x180018fe2  lea     rdx, aNetworkDiagnos_0; "Network Diagnostics Engine Version %s"
0x180018fe9  lea     rcx, [rsp+328h+var_250]
0x180018ff1  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180018ff6  mov     rcx, [rbx]
0x180018ff9  mov     rax, [rcx]
0x180018ffc  mov     rbx, [rsp+328h+var_250]
0x180019004  mov     r8, rbx
0x180019007  mov     edx, 6
0x18001900c  mov     rax, [rax+60h]
0x180019010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019015  nop
0x180019016  lea     rcx, [rbx-18h]; this
0x18001901a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001901f  mov     rcx, [r15+78h]
0x180019023  test    rcx, rcx
0x180019026  jz      short loc_18001903E
0x180019028  mov     rax, [rcx]
0x18001902b  lea     rdx, a10; "1.0"
0x180019032  mov     rax, [rax+0B0h]
0x180019039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001903e  mov     rdx, [rsp+328h+pv]; unsigned __int16 *
0x180019046  call    ?AddHelperClass@NdfTelemetryProviderSingleton@@QEAAXPEBG@Z; NdfTelemetryProviderSingleton::AddHelperClass(ushort const *)
0x18001904b  mov     ebx, dword ptr [rsp+328h+var_264]
0x180019052  mov     rdi, [rsp+328h+var_280]
0x18001905a  mov     esi, [rsp+328h+var_288]
0x180019061  mov     rdx, [rsp+328h+pv]
0x180019069  lea     rcx, [rsp+328h+var_260]
0x180019071  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180019076  mov     dword ptr [rsp+328h+var_308], ebx; char
0x18001907a  mov     r9, rdi
0x18001907d  mov     r8d, esi
0x180019080  mov     rdx, rax
0x180019083  mov     rcx, r15; this
0x180019086  call    ?Initialize@NetworkIncident@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAUtagHELPER_ATTRIBUTE@@K@Z; NetworkIncident::Initialize(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,uint,tagHELPER_ATTRIBUTE *,ulong)
0x18001908b  mov     esi, eax
0x18001908d  mov     rcx, [rsp+328h+pv]; pv
0x180019095  call    cs:__imp_CoTaskMemFree
0x18001909b  mov     rcx, [rsp+328h+var_280]; pv
  ... truncated ...
```
