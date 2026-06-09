# RealtimeProtection::CRtpDlpEngine::CheckAccessForOperation(MpDlpOnOperationActionType,RealtimeProtection::MpDlpOperationOrigin,PPID const &,ulong,wchar_t const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> *,MpDlpResultAccessDecision *,MpDlpResultAccessReason *,bool,_DLPEVENT_EXTRAINFO * const,DlpEnforcementLevel *,bool,ulong,ulong,CommonUtil::CPrinterInformationJSONParser *,_DLP_JIT_SYNC_CLASSIFICATION_REASON *)

- ea: `0x180075448`
- end: `0x180076e6e`
- name: `?CheckAccessForOperation@CRtpDlpEngine@RealtimeProtection@@QEAAJW4MpDlpOnOperationActionType@@W4MpDlpOperationOrigin@2@AEBUPPID@@KPEB_WPEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@PEAW4MpDlpResultAccessDecision@@PEAW4MpDlpResultAccessReason@@_NQEAU_DLPEVENT_EXTRAINFO@@PEAW4DlpEnforcementLevel@@7KKPEAVCPrinterInformationJSONParser@CommonUtil@@PEAW4_DLP_JIT_SYNC_CLASSIFICATION_REASON@@@Z`
- size: `6694`
- prototype: `__int64 __fastcall(_BYTE *, unsigned int, int, RealtimeProtection::DlpProcessCache *, int, const WCHAR *, __int64, wchar_t *, unsigned int *, char, __int64, unsigned int *, char, int, int, __int64, _DWORD *)`
- caller_count: `7`
- callee_count: `62`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180069cb8`
- `0x180075250`
- `0x1800a9460`
- `0x18018babc`
- `0x18018cc50`
- `0x1801920b4`
- `0x1801a17cc`

## callees

- `0x180024ac0`
- `0x180027a90`
- `0x180028d80`
- `0x180029560`
- `0x180029590`
- `0x180034420`
- `0x180038450`
- `0x1800398a0`
- `0x180042950`
- `0x180042f68`
- `0x180046d10`
- `0x180048e20`
- `0x18004de68`
- `0x18004de90`
- `0x180050300`
- `0x1800542d0`
- `0x180054320`
- `0x1800543e0`
- `0x180069a7c`
- `0x18006f7a4`
- `0x180074248`
- `0x180075448`
- `0x180076f28`
- `0x180079348`
- `0x18007a698`
- `0x180080030`
- `0x1800809d0`
- `0x180089510`
- `0x18008a644`
- `0x18008ac70`
- `0x18008b160`
- `0x1800964f4`
- `0x1800a0720`
- `0x1800a2940`
- `0x1800a4c30`
- `0x1800a4cc4`
- `0x1800a6c4c`
- `0x1800a70b0`
- `0x1800a967c`
- `0x1800aca08`
- `0x1800b36cc`
- `0x1800b4380`
- `0x1800b5600`
- `0x1800b61fc`
- `0x1800b7ed0`
- `0x1800b7ef0`
- `0x1800b8e40`
- `0x1800bc560`
- `0x1800be984`
- `0x1800c27c0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18007584a`
- `KERNEL32!CompareStringOrdinal` at `0x18007584a`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800758e1`
- `KERNEL32!ReleaseSRWLockShared` at `0x180075948`
- `KERNEL32!ReleaseSRWLockShared` at `0x180075b8a`
- `KERNEL32!ReleaseSRWLockShared` at `0x180075c92`
- `KERNEL32!ReleaseSRWLockShared` at `0x180076021`
- `KERNEL32!ReleaseSRWLockShared` at `0x180076472`
- `KERNEL32!ReleaseSRWLockShared` at `0x18007654f`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800767c1`
- `KERNEL32!ReleaseSRWLockShared` at `0x180076d70`
- `KERNEL32!ReleaseSRWLockShared` at `0x180076e14`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800758e1`
- `KERNEL32!ReleaseSRWLockShared` at `0x180075948`
- `KERNEL32!ReleaseSRWLockShared` at `0x180075b8a`
- `KERNEL32!ReleaseSRWLockShared` at `0x180075c92`
- `KERNEL32!ReleaseSRWLockShared` at `0x180076021`
- `KERNEL32!ReleaseSRWLockShared` at `0x180076472`
- `KERNEL32!ReleaseSRWLockShared` at `0x18007654f`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800767c1`
- `KERNEL32!ReleaseSRWLockShared` at `0x180076d70`
- `KERNEL32!ReleaseSRWLockShared` at `0x180076e14`
- `KERNEL32!DebugBreak` at `0x180075612`
- `KERNEL32!DebugBreak` at `0x180075612`

## string_xrefs

- `0x1800755ca`: `MpDlp_DebugCheckAccessForOperation`
- `0x1800755ee`: `MpDlp_DebugCheckAccessForOperationAction`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall RealtimeProtection::CRtpDlpEngine::CheckAccessForOperation(
        _BYTE *a1,
        unsigned int a2,
        int a3,
        RealtimeProtection::DlpProcessCache *a4,
        int a5,
        const WCHAR *a6,
        __int64 a7,
        wchar_t *a8,
        unsigned int *a9,
        char a10,
        __int64 a11,
        unsigned int *a12,
        char a13,
        int a14,
        int a15,
        __int64 a16,
        _DWORD *a17)
{
  unsigned int *v18; // r14
  unsigned int *v20; // r9
  __int64 v21; // rax
  __int64 v22; // rdx
  int v23; // r8d
  PVOID *v24; // rsi
  const wchar_t *v25; // r8
  __int64 v26; // r8
  char v27; // r10
  char v28; // r11
  int v29; // eax
  int v30; // ebx
  wchar_t *v31; // rsi
  const WCHAR *v32; // rbx
  __int64 v33; // rax
  const struct std::nothrow_t *v34; // rdx
  _BYTE *v35; // rbx
  const struct std::nothrow_t *v36; // rdx
  const struct std::nothrow_t *v37; // rdx
  __int64 v38; // rbx
  bool *v39; // r9
  _QWORD *v40; // rcx
  _QWORD *v41; // rax
  LPCWCH v42; // r15
  int IsRDPSharePath; // eax
  __int64 v44; // rcx
  PVOID v45; // rcx
  const struct std::nothrow_t *v46; // rdx
  char v47; // al
  PVOID v48; // rcx
  const struct std::nothrow_t *v49; // rdx
  unsigned int v50; // ebx
  __int64 v51; // rdx
  char v52; // al
  __int64 v53; // rax
  _BYTE *v54; // r8
  void *v55; // rax
  PVOID *v56; // rsi
  __int64 *v57; // r8
  __int64 v58; // rcx
  unsigned int v59; // ebx
  __int64 v60; // rcx
  _QWORD *v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // rcx
  const struct std::nothrow_t *v64; // rdx
  __int64 v65; // r9
  _BYTE *i; // rbx
  __int64 last_of; // rax
  RealtimeProtection::DlpProcessCache *v68; // rax
  int v69; // eax
  __int64 v70; // rcx
  const struct std::nothrow_t *v71; // rdx
  __int64 v72; // rcx
  const struct std::nothrow_t *v73; // rdx
  __int64 *v74; // rax
  __int64 v75; // rdx
  __int64 v76; // r8
  __int64 v77; // r9
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 v80; // rax
  __int64 v81; // rdx
  __int64 v82; // rax
  __int64 v83; // r8
  __int64 v84; // r9
  __int64 v85; // r10
  char v86; // r11
  __int64 v87; // rcx
  const struct std::nothrow_t *v88; // rdx
  int v89; // eax
  unsigned int v90; // ebx
  __int64 v91; // r9
  RealtimeProtection::DlpProcessCache *v92; // rsi
  __int64 v93; // rdx
  __int64 v94; // r8
  __int64 v95; // r9
  const wchar_t *v96; // r8
  __int64 v97; // r10
  __int64 v98; // r8
  const char *v99; // r15
  _QWORD *v100; // r14
  _QWORD *v101; // rsi
  const WCHAR *v102; // rax
  __int64 *v103; // rdi
  char v104; // bl
  __int64 v105; // rax
  __int64 v106; // rdx
  __int64 v107; // rax
  __int64 v108; // r8
  int v109; // eax
  __int64 v110; // rdx
  __int64 v111; // r8
  __int64 v112; // r10
  char v113; // r11
  __int64 v114; // rcx
  unsigned int *v115; // rsi
  wchar_t *v116; // r15
  unsigned int v117; // [rsp+A0h] [rbp-998h] BYREF
  char v118[4]; // [rsp+A4h] [rbp-994h]
  int v119; // [rsp+A8h] [rbp-990h]
  int v120; // [rsp+ACh] [rbp-98Ch]
  char v121[4]; // [rsp+B0h] [rbp-988h]
  RealtimeProtection::DlpProcessCache *v122; // [rsp+B8h] [rbp-980h]
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-978h] BYREF
  char v124; // [rsp+C8h] [rbp-970h]
  _BYTE *v125; // [rsp+D0h] [rbp-968h]
  int v126; // [rsp+D8h] [rbp-960h] BYREF
  _BYTE v127[16]; // [rsp+E0h] [rbp-958h] BYREF
  LPCWCH lpString1; // [rsp+F0h] [rbp-948h]
  unsigned int *v129; // [rsp+F8h] [rbp-940h]
  wchar_t *v130; // [rsp+100h] [rbp-938h]
  char v131[8]; // [rsp+108h] [rbp-930h] BYREF
  _QWORD *v132; // [rsp+110h] [rbp-928h]
  __int64 v133; // [rsp+118h] [rbp-920h]
  __int64 v134; // [rsp+120h] [rbp-918h]
  __int64 v135; // [rsp+128h] [rbp-910h]
  _DWORD *v136; // [rsp+130h] [rbp-908h]
  unsigned int *v137; // [rsp+138h] [rbp-900h]
  wchar_t *v138; // [rsp+140h] [rbp-8F8h]
  unsigned int *v139; // [rsp+148h] [rbp-8F0h]
  __int64 v140; // [rsp+150h] [rbp-8E8h]
  __int64 *v141; // [rsp+158h] [rbp-8E0h]
  __int64 v142; // [rsp+160h] [rbp-8D8h]
  __int64 v143[4]; // [rsp+168h] [rbp-8D0h] BYREF
  char v144; // [rsp+188h] [rbp-8B0h]
  __int64 v145[4]; // [rsp+190h] [rbp-8A8h] BYREF
  char v146; // [rsp+1B0h] [rbp-888h]
  char v147[16]; // [rsp+1C0h] [rbp-878h] BYREF
  char v148[16]; // [rsp+1D0h] [rbp-868h] BYREF
  unsigned int v149; // [rsp+1E0h] [rbp-858h] BYREF
  unsigned int v150; // [rsp+1E4h] [rbp-854h] BYREF
  unsigned int v151; // [rsp+1E8h] [rbp-850h] BYREF
  wchar_t v152; // [rsp+1ECh] [rbp-84Ch] BYREF
  char v153; // [rsp+1EEh] [rbp-84Ah] BYREF
  char v154; // [rsp+1EFh] [rbp-849h] BYREF
  void *v155; // [rsp+1F0h] [rbp-848h] BYREF
  unsigned int v156[2]; // [rsp+1F8h] [rbp-840h] BYREF
  __int128 v157; // [rsp+200h] [rbp-838h] BYREF
  std::_Ref_count_base *v158[2]; // [rsp+210h] [rbp-828h] BYREF
  _BYTE v159[32]; // [rsp+220h] [rbp-818h] BYREF
  __int64 v160; // [rsp+240h] [rbp-7F8h]
  _BYTE v161[32]; // [rsp+248h] [rbp-7F0h] BYREF
  _QWORD v162[4]; // [rsp+268h] [rbp-7D0h] BYREF
  _QWORD v163[4]; // [rsp+288h] [rbp-7B0h] BYREF
  _BYTE v164[32]; // [rsp+2A8h] [rbp-790h] BYREF
  _BYTE v165[32]; // [rsp+2C8h] [rbp-770h] BYREF
  __int128 v166; // [rsp+2E8h] [rbp-750h] BYREF
  __m128i si128; // [rsp+2F8h] [rbp-740h]
  char v168; // [rsp+308h] [rbp-730h]
  _OWORD v169[2]; // [rsp+310h] [rbp-728h] BYREF
  _BYTE v170[32]; // [rsp+330h] [rbp-708h] BYREF
  __int64 v171[3]; // [rsp+350h] [rbp-6E8h] BYREF
  unsigned __int64 v172; // [rsp+368h] [rbp-6D0h]
  int v173; // [rsp+394h] [rbp-6A4h]
  __int64 v174; // [rsp+3A8h] [rbp-690h] BYREF
  __int64 v175; // [rsp+3B0h] [rbp-688h]
  char v176; // [rsp+400h] [rbp-638h]
  _BYTE v177[32]; // [rsp+430h] [rbp-608h] BYREF
  _BYTE Src[32]; // [rsp+450h] [rbp-5E8h] BYREF
  __int64 v179; // [rsp+470h] [rbp-5C8h] BYREF
  __int64 v180; // [rsp+478h] [rbp-5C0h]
  int v181; // [rsp+480h] [rbp-5B8h]
  int v182; // [rsp+484h] [rbp-5B4h]
  char v183; // [rsp+4A8h] [rbp-590h]
  char v184[24]; // [rsp+4B0h] [rbp-588h] BYREF
  __int64 v185; // [rsp+4C8h] [rbp-570h]
  __int128 v186; // [rsp+4D0h] [rbp-568h]
  __m128i v187; // [rsp+4E0h] [rbp-558h]
  char v188; // [rsp+4F0h] [rbp-548h]
  _BYTE v189[1184]; // [rsp+550h] [rbp-4E8h] BYREF

  v122 = a4;
  *(_DWORD *)v121 = a3;
  v125 = a1;
  lpString1 = a6;
  *(_DWORD *)v118 = a5;
  v133 = a7;
  v130 = a8;
  v138 = a8;
  v18 = a9;
  v137 = a9;
  v139 = a9;
  v135 = a11;
  v129 = a12;
  v140 = (__int64)a12;
  v134 = a16;
  v136 = a17;
  v120 = 0;
  if ( !a8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 372, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, 2147942487LL);
    return 2147942487LL;
  }
  if ( a1[69] == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 373, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, 2147947423LL);
    return 2147947423LL;
  }
  if ( (unsigned int)RealtimeProtection::DlpUtils::DlpMpLookupMiscConfigFlag(
                       (RealtimeProtection::DlpUtils *)L"MpDlp_DebugCheckAccessForOperation",
                       a8) )
  {
    v156[0] = 100;
    if ( (int)RealtimeProtection::DlpUtils::DlpGetMiscDwordValue(
                (RealtimeProtection::DlpUtils *)L"MpDlp_DebugCheckAccessForOperationAction",
                (const wchar_t *)0x64,
                (unsigned int)v156,
                v20) < 0
      || v156[0] >= 6
      || v156[0] == a2 )
    {
      DebugBreak();
    }
  }
  v21 = RealtimeProtection::DlpAutoEtwPerfOperation::DlpAutoEtwPerfOperation(v127, 5, a2);
  v24 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
  {
    LOBYTE(v21) = a10;
    v119 = v21;
  }
  else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LOBYTE(v21) = a10;
    v119 = v21;
    v25 = a6;
    if ( !a6 )
      v25 = L"none";
    RealtimeProtection::DlpUtils::MpDlpOnOperationActionTypeToStr(a2, v22, v25);
    WPP_SF_SDSdddd((TRACEHANDLE)v24[2], *((_DWORD *)v122 + 2), v26, v118[0], v27, v28, v121[0]);
    v24 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    LOBYTE(v23) = a10;
    v119 = v23;
  }
  v117 = 0;
  v29 = RealtimeProtection::DlpUtils::ConvertDlpActionEnum(a2, &v117);
  v30 = v29;
  v156[0] = v29;
  if ( v29 < 0 )
  {
    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 )
      WPP_SF_d(v24[2], 375, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, (unsigned int)v29);
LABEL_171:
    RealtimeProtection::DlpAutoEtwPerfOperation::~DlpAutoEtwPerfOperation((RealtimeProtection::DlpAutoEtwPerfOperation *)v127);
    return (unsigned int)v30;
  }
  v155 = 0;
  v151 = 0;
  v150 = 0;
  v149 = 0;
  v31 = v130;
  *(_DWORD *)v130 = 1;
  if ( a9 )
    *a9 = 0;
  if ( v129 )
    *v129 = 0;
  v32 = lpString1;
  if ( lpString1 )
  {
    v158[0] = (std::_Ref_count_base *)lpString1;
    v33 = -1;
    do
      ++v33;
    while ( lpString1[v33] );
    v158[1] = (std::_Ref_count_base *)v33;
    if ( (unsigned __int8)Dlp::Utils::IsAlternateDataStream(v158)
      && (unsigned __int8)Dlp::FeatureControl::GetBoolValue(145, v34) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 376, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v32);
LABEL_39:
      *(_DWORD *)v31 = 1;
      if ( a9 )
        *a9 = 6;
      goto LABEL_229;
    }
    if ( (unsigned __int8)Dlp::FeatureControl::GetBoolValue(267, v34)
      && v117 == 1
      && *(_DWORD *)v121 == 1
      && CompareStringOrdinal(v32, -1, L"\\Device\\Mup\\;LanmanRedirector\\", -1, 1) == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 377, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
      goto LABEL_39;
    }
  }
  v35 = v125;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>(
    &SRWLock,
    v125 + 16);
  if ( *((_DWORD *)v35 + 2) != 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 378, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, 2147947423LL);
    if ( v124 )
      ReleaseSRWLockShared(SRWLock);
    if ( v155 )
      operator delete(v155, v36);
    v30 = -2147019873;
    goto LABEL_171;
  }
  if ( *(_DWORD *)v121 != 6
    && (unsigned __int8)RealtimeProtection::CRtpDlpEngine::IsCheckAccessForOperationRedundant(
                          v35,
                          a2,
                          *(unsigned int *)v121,
                          v122) )
  {
    if ( a9 )
      *a9 = 9;
    if ( v124 )
      ReleaseSRWLockShared(SRWLock);
    if ( v155 )
      operator delete(v155, v37);
    goto LABEL_231;
  }
  RealtimeProtection::ActionEnforcementState::ActionEnforcementState((RealtimeProtection::ActionEnforcementState *)v171);
  std::wstring::wstring(v163, &qword_18025C818);
  std::wstring::wstring(v162, &qword_18025C818);
  std::wstring::wstring(v164, &qword_18025C818);
  std::wstring::wstring(v165, &qword_18025C818);
  v157 = 0u;
  std::list<unsigned long>::_Alloc_sentinel_and_proxy(&v157);
  v38 = v157;
  if ( *((_QWORD *)&v157 + 1) == 0xAAAAAAAAAAAAAAALL )
    std::_Xlength_error("list too long");
  std::_List_node_emplace_op2<std::allocator<std::_List_node<int,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<int,void *>>>(
    v131,
    &v157,
    &v117);
  ++*((_QWORD *)&v157 + 1);
  v40 = *(_QWORD **)(v38 + 8);
  *v132 = v38;
  v132[1] = v40;
  v41 = v132;
  v132 = 0;
  *(_QWORD *)(v38 + 8) = v41;
  *v40 = v41;
  if ( v132 )
    std::_Deallocate<16>(v132, 24);
  v42 = lpString1;
  if ( v117 != 1 || !lpString1 )
    goto LABEL_94;
  v152 = 0;
  IsRDPSharePath = CommonUtil::UtilIsRDPSharePath((wchar_t *)lpString1, &v152, (bool *)&v152 + 1, v39);
  v30 = IsRDPSharePath;
  v156[0] = IsRDPSharePath;
  if ( IsRDPSharePath < 0 )
  {
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        379,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)IsRDPSharePath);
    std::_List_node<unsigned __int64,void *>::_Free_non_head<std::allocator<std::_List_node<unsigned __int64,void *>>>(
      v45,
      v157);
    std::_Deallocate<16>(v157, 24);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v165);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v164);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v162);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v163);
    RealtimeProtection::ActionEnforcementState::~ActionEnforcementState((RealtimeProtection::ActionEnforcementState *)v171);
    if ( v124 )
      ReleaseSRWLockShared(SRWLock);
    if ( v155 )
      operator delete(v155, v46);
    goto LABEL_171;
  }
  v47 = Dlp::FeatureControl::GetFlag<enum Dlp::FeatureControl::RemovableMediaFlags,void,void>(v44, 2);
  if ( HIBYTE(v152) && !v47 )
  {
    v48 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v42, v118[0]);
    std::_List_node<unsigned __int64,void *>::_Free_non_head<std::allocator<std::_List_node<unsigned __int64,void *>>>(
      v48,
      v157);
    std::_Deallocate<16>(v157, 24);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v165);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v164);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v162);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v163);
    RealtimeProtection::ActionEnforcementState::~ActionEnforcementState((RealtimeProtection::ActionEnforcementState *)v171);
    if ( v124 )
      ReleaseSRWLockShared(SRWLock);
    if ( v155 )
      operator delete(v155, v49);
    goto LABEL_231;
  }
  if ( (_BYTE)v152
    && (v126 = 8, std::list<enum DlpActionType>::push_back(&v157, &v126), WPP_GLOBAL_Control != &WPP_GLOBAL_Control)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v50 = *(_DWORD *)v118;
    WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v42, v118[0]);
  }
  else
  {
LABEL_94:
    v50 = *(_DWORD *)v118;
  }
  memset(v189, 0, 0x498u);
  v154 = 1;
  v153 = 0;
  RealtimeProtection::DlpUserSidCache::TryGetClassificationUserSidString(v159, v50, v122);
  if ( !(unsigned __int8)Dlp::FeatureControl::GetBoolValue(217, v51) )
    goto LABEL_98;
  v52 = v160;
  if ( (_BYTE)v160 )
  {
    v53 = std::optional<std::wstring>::value(v159);
    RealtimeProtection::DlpUserConfigManagement::CheckAndQueueUserConfigInitRequest(v50, v53);
LABEL_98:
    v52 = v160;
  }
  v54 = v125;
  LOBYTE(v152) = v125[84] & 1;
  if ( v52 )
  {
    v55 = (void *)std::optional<std::wstring>::value(v159);
    HIBYTE(v152) = RealtimeProtection::DlpEngineUtils::IsTrustContainerEnabled(v55);
    v54 = v125;
  }
  else
  {
    HIBYTE(v152) = 0;
  }
  v126 = *((_DWORD *)v54 + 20) & 0x8000;
  v56 = (PVOID *)WPP_GLOBAL_Control;
  while ( 1 )
  {
    if ( !*((_QWORD *)&v157 + 1) || v149 )
    {
      if ( ((*(_DWORD *)v121 - 4) & 0xFFFFFFFD) == 0 )
      {
        v89 = (unsigned __int8)v119;
        if ( v149 == 1 )
          v89 = 1;
        v119 = v89;
      }
      v90 = v117;
      if ( v125[94] && v117 == 3 && *(_DWORD *)v121 == 6 )
      {
        v91 = (v175 - v174) >> 9;
        if ( v91 == 1 && (v125[104] & 4) != 0 )
        {
          if ( v149 == 2 )
          {
            LOBYTE(v152) = 0;
            v156[0] = RealtimeProtection::DlpProcessCache::CheckIfDismissed(
                        (unsigned int)&v152,
                        6,
                        (unsigned int)v171,
                        v117,
                        v174);
            if ( (v156[0] & 0x80000000) == 0 && (_BYTE)v152 )
            {
              v149 = 3;
              LOBYTE(v119) = 0;
            }
          }
          else if ( v149 == 3 )
          {
            *v136 = *(_DWORD *)(v174 + 484);
          }
        }
        else if ( v56 != &WPP_GLOBAL_Control && (*((_BYTE *)v56 + 28) & 2) != 0 )
        {
          WPP_SF_d(v56[2], 387, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v91);
        }
      }
      v168 = 0;
      if ( v42 )
      {
        std::wstring::wstring(&v166, v42);
        v168 = 1;
      }
      *(_OWORD *)v158 = 0;
      LODWORD(v179) = 1179926;
      v92 = v122;
      HIDWORD(v179) = *((_DWORD *)v122 + 2);
      v180 = *(_QWORD *)v122;
      v181 = *(_DWORD *)v118;
      v182 = 0;
      v183 = 0;
      std::wstring::wstring(v184, &qword_18025C818);
      v188 = 0;
      if ( v168 )
      {
        v186 = v166;
        v187 = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v166) = 0;
        v188 = 1;
      }
      std::make_shared<EndpointDlp::Client::DeviceAccessInformation,EndpointDlp::Client::DeviceAccessInformation>(
        v158,
        &v179);
      EndpointDlp::Client::DeviceAccessInformation::~DeviceAccessInformation((EndpointDlp::Client::DeviceAccessInformation *)&v179);
      if ( v149 == 3 )
      {
        if ( v150 != 15 || v151 != 2 )
          goto LABEL_199;
        v150 = 1;
        LOBYTE(v119) = 0;
      }
      if ( !v149 )
      {
LABEL_207:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v99 = L"true";
          if ( !v176 )
            v99 = L"false";
          v100 = v162;
          if ( v162[3] > 7u )
            v100 = (_QWORD *)v162[0];
          v101 = v163;
          if ( v163[3] > 7u )
            v101 = (_QWORD *)v163[0];
          v102 = lpString1;
          if ( !lpString1 )
            v102 = L"none";
          lpString1 = v102;
          v103 = v171;
          if ( v172 > 7 )
            v103 = (__int64 *)v171[0];
          v104 = v153 != 0;
          RealtimeProtection::DlpUtils::MpDlpResultAccessReasonToStr(v150, v93, v94, v95);
          v105 = RealtimeProtection::DlpUtils::DlpEnforcementLevelToStr(v149);
          v107 = RealtimeProtection::DlpUtils::DlpActionTypeToStr(v117, v106, v105);
          v109 = RealtimeProtection::DlpUtils::MpDlpResultAccessDecisionToStr(v151, v107, v108);
          WPP_SF_SSSSdDSSSSSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v110,
            v111,
            v109,
            v110,
            v111,
            v112,
            v104,
            v113,
            (__int64)v103,
            (__int64)lpString1,
            (__int64)v101,
            (__int64)v100,
            (__int64)v99);
          v18 = v137;
        }
        if ( v158[1] )
          std::_Ref_count_base::_Decref(v158[1]);
        std::optional<std::wstring>::~optional<std::wstring>(&v166);
        std::optional<std::wstring>::~optional<std::wstring>(v159);
        std::_List_node<unsigned __int64,void *>::_Free_non_head<std::allocator<std::_List_node<unsigned __int64,void *>>>(
          v114,
          v157);
        std::_Deallocate<16>(v157, 24);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v165);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v164);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v162);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v163);
        RealtimeProtection::ActionEnforcementState::~ActionEnforcementState((RealtimeProtection::ActionEnforcementState *)v171);
        v30 = v156[0];
        v115 = v129;
        v116 = v130;
        if ( (v156[0] & 0x80000000) != 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              390,
              &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
              v156[0]);
          if ( v124 )
            ReleaseSRWLockShared(SRWLock);
          if ( v155 )
            operator delete(v155, v34);
          goto LABEL_171;
        }
        if ( v124 )
          ReleaseSRWLockShared(SRWLock);
        if ( v18 )
          *v18 = v150;
        *(_DWORD *)v116 = v151;
        if ( v115 )
          *v115 = v149;
LABEL_229:
        if ( v155 )
          operator delete(v155, v34);
        goto LABEL_231;
      }
LABEL_199:
      if ( (_BYTE)v119 )
      {
        v156[0] = RealtimeProtection::CRtpDlpEngine::DoAccessOperationReporting(
                    (_DWORD)v125,
                    (unsigned int)v158,
                    v90,
                    (unsigned int)v189,
                    (__int64)v155,
                    v151,
                    v150,
                    v149,
                    (__int64)v171,
                    v154,
                    v153,
                    a14,
                    a13,
                    v135);
        if ( (v156[0] & 0x80000000) != 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v96 = L"none";
            if ( v42 )
              v96 = v42;
            RealtimeProtection::DlpUtils::MpDlpOnOperationActionTypeToStr(0, v93, v96);
            WPP_SF_SDSd(*(_QWORD *)(v97 + 16), *((_DWORD *)v92 + 2), v98, v118[0]);
          }
          v156[0] = 0;
        }
      }
      goto LABEL_207;
    }
    v57 = *(__int64 **)(v157 + 8);
    v117 = *((_DWORD *)v57 + 4);
    v58 = *v57;
    --*((_QWORD *)&v157 + 1);
    *(_QWORD *)v57[1] = v58;
    *(_QWORD *)(v58 + 8) = v57[1];
    std::_Deallocate<16>(v57, 24);
    v146 = 0;
    v144 = 0;
    v59 = v117;
    if ( (unsigned int)RealtimeProtection::DlpProcessCache::GetActionState(
                         v122,
                         v152,
                         SHIBYTE(v152),
                         v133,
                         (__int64)v171,
                         (__int64)v143,
                         (__int64)v145) == 1 )
    {
      if ( *(_DWORD *)v121 == 1 )
      {
        v61 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_114;
        v62 = 382;
      }
      else
      {
        v61 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_114;
        v62 = 383;
      }
      WPP_SF_Dd(v61[2], v62, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v59, *((_DWORD *)v122 + 2));
LABEL_114:
      *(_DWORD *)v130 = 1;
      if ( a9 )
        *a9 = 6;
      if ( v129 )
        *v129 = 0;
      std::optional<std::wstring>::~optional<std::wstring>(v159);
      std::_List_node<unsigned __int64,void *>::_Free_non_head<std::allocator<std::_List_node<unsigned __int64,void *>>>(
        v63,
        v157);
      std::_Deallocate<16>(v157, 24);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v165);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v164);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v162);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v163);
      RealtimeProtection::ActionEnforcementState::~ActionEnforcementState((RealtimeProtection::ActionEnforcementState *)v171);
      if ( v124 )
        ReleaseSRWLockShared(SRWLock);
      if ( v155 )
        operator delete(v155, v64);
      goto LABEL_231;
    }
    if ( (unsigned __int8)Dlp::FeatureControl::GetFlag<enum Dlp::FeatureControl::ClipboardFlags,void,void>(v60, 2)
      && v173 == 20
      && v42
      && v59 <= 1 )
    {
      std::wstring::wstring(Src, v42);
      RealtimeProtection::DlpUtils::GetFileName(v161, Src);
      `vector constructor iterator'(v169, 0x10u, 2u, std::optional<PPID>::optional<PPID>);
      LOBYTE(v65) = 1;
      v169[0] = *(_OWORD *)RealtimeProtection::DlpProcessCache::GetOwnerFromFilePasteInformation(v147, v122, v161, v65);
      v169[1] = *(_OWORD *)RealtimeProtection::DlpProcessCache::GetOwnerFromFilePasteInformation(v148, v122, v161, 0);
      for ( i = v169; i != v170; i += 16 )
      {
        if ( i[12] )
        {
          last_of = std::wstring::find_last_of(v161, L".");
          if ( last_of == -1 )
            std::wstring::wstring(v170, v161);
          else
            std::wstring::substr(v161, v170, 0, last_of);
          v120 |= 1u;
          RealtimeProtection::DlpUtils::GetFileExtensions(v177, v161);
          RealtimeProtection::ActionEnforcementState::ActionEnforcementState((RealtimeProtection::ActionEnforcementState *)&v179);
          *(_QWORD *)v156 = v143;
          std::wstring::wstring(v143, v177);
          v144 = 1;
          v141 = v145;
          std::wstring::wstring(v145, v170);
          v146 = 1;
          v68 = (RealtimeProtection::DlpProcessCache *)std::optional<PPID>::value(i);
          if ( (int)RealtimeProtection::DlpProcessCache::GetActionState(
                      v68,
                      v152,
                      SHIBYTE(v152),
                      v133,
                      (__int64)&v179,
                      (__int64)v145,
                      (__int64)v143) >= 0
            && v185 != (_QWORD)v186 )
          {
            std::vector<RealtimeProtection::FileProps>::insert<std::move_iterator<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<RealtimeProtection::FileProps>>>>,0>(
              (unsigned int)&v174,
              (unsigned int)v131,
              v175,
              v185,
              v186);
          }
          RealtimeProtection::ActionEnforcementState::~ActionEnforcementState((RealtimeProtection::ActionEnforcementState *)&v179);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v177);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v170);
        }
      }
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v161);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
      v59 = v117;
    }
    BYTE4(v142) = 0;
    v69 = RealtimeProtection::CRtpDlpEngine::DetermineOperationFiles(
            v125,
            v122,
            *(unsigned int *)v118,
            v59,
            *(_DWORD *)v121,
            v159,
            v42,
            v142,
            a15,
            v171,
            v135,
            v134,
            v171);
    v30 = v69;
    if ( v69 < 0 )
      break;
    v153 = 0;
    v161[16] = 0;
    v74 = v171;
    if ( v172 > 7 )
      v74 = (__int64 *)v171[0];
    v30 = RealtimeProtection::CRtpDlpEngine::DetermineOperationEnforcement(
            (_DWORD)v125,
            v117,
            (_DWORD)v122,
            (unsigned int)v159,
            *(_DWORD *)v118,
            (__int64)v74,
            (__int64)v42,
            v119,
            (__int64)v171,
            (__int64)&v149,
            (__int64)&v151,
            (__int64)&v150,
            (__int64)&v153,
            (__int64)&v155,
            (__int64)v161,
            (__int64)v189,
            (__int64)&v154,
            *(_DWORD *)v121,
            v134);
    v156[0] = v30;
    v56 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      RealtimeProtection::DlpUtils::MpDlpResultAccessReasonToStr(v150, v75, v76, v77);
      RealtimeProtection::DlpUtils::MpDlpResultAccessDecisionToStr(v151, v78, v79);
      v80 = RealtimeProtection::DlpUtils::DlpEnforcementLevelToStr(v149);
      v82 = RealtimeProtection::DlpUtils::DlpActionTypeToStr(v117, v81, v80);
      WPP_SF_DSSSSd((TRACEHANDLE)v56[2], v82, v83, v84, v85, v86);
      v56 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v30 < 0 )
    {
      if ( v56 != &WPP_GLOBAL_Control && (*((_BYTE *)v56 + 28) & 1) != 0 )
        WPP_SF_d(v56[2], 386, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, (unsigned int)v30);
      std::optional<std::wstring>::~optional<std::wstring>(v159);
      std::_List_node<unsigned __int64,void *>::_Free_non_head<std::allocator<std::_List_node<unsigned __int64,void *>>>(
        v87,
        v157);
      std::_Deallocate<16>(v157, 24);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v165);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v164);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v162);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v163);
      RealtimeProtection::ActionEnforcementState::~ActionEnforcementState((RealtimeProtection::ActionEnforcementState *)v171);
      if ( v124 )
        ReleaseSRWLockShared(SRWLock);
      if ( v155 )
        operator delete(v155, v88);
      goto LABEL_171;
    }
  }
  if ( v69 != -2147023728 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        384,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)v69);
    std::optional<std::wstring>::~optional<std::wstring>(v159);
    std::_List_node<unsigned __int64,void *>::_Free_non_head<std::allocator<std::_List_node<unsigned __int64,void *>>>(
      v72,
      v157);
    std::_Deallocate<16>(v157, 24);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v165);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v164);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v162);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v163);
    RealtimeProtection::ActionEnforcementState::~ActionEnforcementState((RealtimeProtection::ActionEnforcementState *)v171);
    if ( v124 )
      ReleaseSRWLockShared(SRWLock);
    if ( v155 )
      operator delete(v155, v73);
    goto LABEL_171;
  }
  *(_DWORD *)v130 = 0;
  if ( a9 )
    *a9 = 7;
  if ( v129 )
    *v129 = 0;
  std::optional<std::wstring>::~optional<std::wstring>(v159);
  std::_List_node<unsigned __int64,void *>::_Free_non_head<std::allocator<std::_List_node<unsigned __int64,void *>>>(
    v70,
    v157);
  std::_Deallocate<16>(v157, 24);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v165);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v164);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v162);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v163);
  RealtimeProtection::ActionEnforcementState::~ActionEnforcementState((RealtimeProtection::ActionEnforcementState *)v171);
  if ( v124 )
    ReleaseSRWLockShared(SRWLock);
  if ( v155 )
    operator delete(v155, v71);
LABEL_231:
  RealtimeProtection::DlpAutoEtwPerfOperation::~DlpAutoEtwPerfOperation((RealtimeProtection::DlpAutoEtwPerfOperation *)v127);
  return 0;
}

```

## disassembly

```asm
0x180075448  push    rbx
0x18007544a  push    rsi
0x18007544b  push    rdi
0x18007544c  push    r12
0x18007544e  push    r13
0x180075450  push    r14
0x180075452  push    r15
0x180075454  sub     rsp, 0A00h
0x18007545b  mov     rax, cs:__security_cookie
0x180075462  xor     rax, rsp
0x180075465  mov     [rsp+0A38h+var_48], rax
0x18007546d  mov     [rsp+0A38h+var_980], r9
0x180075475  mov     dword ptr [rsp+0A38h+var_988], r8d
0x18007547d  mov     r15d, edx
0x180075480  mov     [rsp+0A38h+var_968], rcx
0x180075488  mov     rbx, [rsp+0A38h+arg_28]
0x180075490  mov     [rsp+0A38h+lpString1], rbx
0x180075498  mov     eax, [rsp+0A38h+arg_20]
0x18007549f  mov     dword ptr [rsp+0A38h+var_994], eax
0x1800754a6  mov     rax, [rsp+0A38h+arg_30]
0x1800754ae  mov     [rsp+0A38h+var_920], rax
0x1800754b6  mov     rdx, [rsp+0A38h+arg_38]; wchar_t *
0x1800754be  mov     [rsp+0A38h+var_938], rdx
0x1800754c6  mov     [rsp+0A38h+var_8F8], rdx
0x1800754ce  mov     r14, [rsp+0A38h+arg_40]
0x1800754d6  mov     [rsp+0A38h+var_900], r14
0x1800754de  mov     [rsp+0A38h+var_8F0], r14
0x1800754e6  mov     rax, [rsp+0A38h+arg_50]
0x1800754ee  mov     [rsp+0A38h+var_910], rax
0x1800754f6  mov     rax, [rsp+0A38h+arg_58]
0x1800754fe  mov     [rsp+0A38h+var_940], rax
0x180075506  mov     [rsp+0A38h+var_8E8], rax
0x18007550e  mov     rax, [rsp+0A38h+arg_78]
0x180075516  mov     [rsp+0A38h+var_918], rax
0x18007551e  mov     rax, [rsp+0A38h+arg_80]
0x180075526  mov     [rsp+0A38h+var_908], rax
0x18007552e  xor     r12d, r12d
0x180075531  mov     [rsp+0A38h+var_98C], r12d
0x180075539  test    rdx, rdx
0x18007553c  jnz     short loc_180075580
0x18007553e  lea     rax, WPP_GLOBAL_Control
0x180075545  mov     rcx, cs:WPP_GLOBAL_Control
0x18007554c  cmp     rcx, rax
0x18007554f  jz      short loc_180075576
0x180075551  lea     r13d, [rdx+1]
0x180075555  test    [rcx+1Ch], r13b
0x180075559  jz      short loc_180075576
0x18007555b  mov     edx, 174h
0x180075560  mov     r9d, 80070057h
0x180075566  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18007556d  mov     rcx, [rcx+10h]
0x180075571  call    WPP_SF_d
0x180075576  mov     eax, 80070057h
0x18007557b  jmp     loc_180076E3D
0x180075580  mov     r13d, 1
0x180075586  cmp     [rcx+45h], r13b
0x18007558a  jnz     short loc_1800755CA
0x18007558c  lea     rax, WPP_GLOBAL_Control
0x180075593  mov     rcx, cs:WPP_GLOBAL_Control
0x18007559a  cmp     rcx, rax
0x18007559d  jz      short loc_1800755C0
0x18007559f  test    [rcx+1Ch], r13b
0x1800755a3  jz      short loc_1800755C0
0x1800755a5  mov     edx, 175h
0x1800755aa  mov     r9d, 8007139Fh
0x1800755b0  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x1800755b7  mov     rcx, [rcx+10h]
0x1800755bb  call    WPP_SF_d
0x1800755c0  mov     eax, 8007139Fh
0x1800755c5  jmp     loc_180076E3D
0x1800755ca  lea     rcx, aMpdlpDebugchec_0; "MpDlp_DebugCheckAccessForOperation"
0x1800755d1  call    ?DlpMpLookupMiscConfigFlag@DlpUtils@RealtimeProtection@@YAHPEB_W@Z; RealtimeProtection::DlpUtils::DlpMpLookupMiscConfigFlag(wchar_t const *)
0x1800755d6  test    eax, eax
0x1800755d8  jz      short loc_180075618
0x1800755da  mov     edx, 64h ; 'd'; wchar_t *
0x1800755df  mov     [rsp+0A38h+var_840], edx
0x1800755e6  lea     r8, [rsp+0A38h+var_840]; unsigned int
0x1800755ee  lea     rcx, aMpdlpDebugchec; "MpDlp_DebugCheckAccessForOperationActio"...
0x1800755f5  call    ?DlpGetMiscDwordValue@DlpUtils@RealtimeProtection@@YAJPEB_WKPEAK@Z; RealtimeProtection::DlpUtils::DlpGetMiscDwordValue(wchar_t const *,ulong,ulong *)
0x1800755fa  test    eax, eax
0x1800755fc  js      short loc_180075612
0x1800755fe  cmp     [rsp+0A38h+var_840], 6
0x180075606  jnb     short loc_180075612
0x180075608  cmp     [rsp+0A38h+var_840], r15d
0x180075610  jnz     short loc_180075618
0x180075612  call    cs:__imp_DebugBreak
0x180075618  xor     r9d, r9d
0x18007561b  mov     r8d, r15d
0x18007561e  lea     edx, [r9+5]
0x180075622  lea     rcx, [rsp+0A38h+var_958]
0x18007562a  call    ??0DlpAutoEtwPerfOperation@RealtimeProtection@@QEAA@W4DlpOperationType@@W4MpDlpOnOperationActionType@@W4DlpFileAccessCheckType@@@Z; RealtimeProtection::DlpAutoEtwPerfOperation::DlpAutoEtwPerfOperation(DlpOperationType,MpDlpOnOperationActionType,DlpFileAccessCheckType)
0x18007562f  nop
0x180075630  lea     rdi, WPP_GLOBAL_Control
0x180075637  mov     rsi, cs:WPP_GLOBAL_Control
0x18007563e  cmp     rsi, rdi
0x180075641  jz      loc_1800756DC
0x180075647  test    byte ptr [rsi+1Ch], 4
0x18007564b  jz      short loc_1800756CA
0x18007564d  movzx   r11d, [rsp+0A38h+arg_60]
0x180075656  mov     al, [rsp+0A38h+arg_48]
0x18007565d  mov     [rsp+0A38h+var_990], eax
0x180075664  movzx   r10d, al
0x180075668  lea     rax, aNone; "none"
0x18007566f  mov     r8, rbx
0x180075672  test    rbx, rbx
0x180075675  cmovz   r8, rax
0x180075679  mov     ecx, r15d
0x18007567c  call    ?MpDlpOnOperationActionTypeToStr@DlpUtils@RealtimeProtection@@YAPEB_WW4MpDlpOnOperationActionType@@@Z; RealtimeProtection::DlpUtils::MpDlpOnOperationActionTypeToStr(MpDlpOnOperationActionType)
0x180075681  mov     r9, rax
0x180075684  mov     ecx, dword ptr [rsp+0A38h+var_988]
0x18007568b  mov     dword ptr [rsp+0A38h+var_9F0], ecx; char
0x18007568f  mov     dword ptr [rsp+0A38h+var_9F8], r11d; char
0x180075694  mov     dword ptr [rsp+0A38h+var_A00], r10d; char
0x180075699  mov     eax, dword ptr [rsp+0A38h+var_994]
0x1800756a0  mov     dword ptr [rsp+0A38h+var_A08], eax; char
0x1800756a4  mov     qword ptr [rsp+0A38h+var_A10], r8; __int64
0x1800756a9  mov     rax, [rsp+0A38h+var_980]
0x1800756b1  mov     eax, [rax+8]
0x1800756b4  mov     [rsp+0A38h+bIgnoreCase], eax; char
0x1800756b8  mov     rcx, [rsi+10h]; LoggerHandle
0x1800756bc  call    WPP_SF_SDSdddd
0x1800756c1  mov     rsi, cs:WPP_GLOBAL_Control
0x1800756c8  jmp     short loc_1800756EA
0x1800756ca  mov     r8b, [rsp+0A38h+arg_48]
0x1800756d2  mov     [rsp+0A38h+var_990], r8d
0x1800756da  jmp     short loc_1800756EA
0x1800756dc  mov     al, [rsp+0A38h+arg_48]
0x1800756e3  mov     [rsp+0A38h+var_990], eax
0x1800756ea  mov     [rsp+0A38h+var_998], r12d
0x1800756f2  lea     rdx, [rsp+0A38h+var_998]
0x1800756fa  mov     ecx, r15d
0x1800756fd  call    ?ConvertDlpActionEnum@DlpUtils@RealtimeProtection@@YAJW4MpDlpOnOperationActionType@@PEAW4DlpActionType@@@Z; RealtimeProtection::DlpUtils::ConvertDlpActionEnum(MpDlpOnOperationActionType,DlpActionType *)
0x180075702  mov     ebx, eax
0x180075704  mov     [rsp+0A38h+var_840], eax
0x18007570b  test    eax, eax
0x18007570d  jns     short loc_18007573F
0x18007570f  cmp     rsi, rdi
0x180075712  jz      loc_180076E2E
0x180075718  test    [rsi+1Ch], r13b
0x18007571c  jz      loc_180076E2E
0x180075722  mov     edx, 177h
0x180075727  mov     r9d, eax
0x18007572a  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180075731  mov     rcx, [rsi+10h]
0x180075735  call    WPP_SF_d
0x18007573a  jmp     loc_180076E2E
0x18007573f  mov     [rsp+0A38h+var_848], r12
0x180075747  mov     [rsp+0A38h+var_850], r12d
0x18007574f  mov     [rsp+0A38h+var_854], r12d
0x180075757  mov     [rsp+0A38h+var_858], r12d
0x18007575f  mov     rsi, [rsp+0A38h+var_938]
0x180075767  mov     [rsi], r13d
0x18007576a  test    r14, r14
0x18007576d  jz      short loc_180075772
0x18007576f  mov     [r14], r12d
0x180075772  mov     rax, [rsp+0A38h+var_940]
0x18007577a  test    rax, rax
0x18007577d  jz      short loc_180075782
0x18007577f  mov     [rax], r12d
0x180075782  mov     rbx, [rsp+0A38h+lpString1]
0x18007578a  test    rbx, rbx
0x18007578d  jz      loc_180075881
0x180075793  mov     [rsp+0A38h+var_828], rbx
0x18007579b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007579f  inc     rax
0x1800757a2  cmp     [rbx+rax*2], r12w
0x1800757a7  jnz     short loc_18007579F
0x1800757a9  mov     [rsp+0A38h+var_828+8], rax
0x1800757b1  lea     rcx, [rsp+0A38h+var_828]
0x1800757b9  call    ?IsAlternateDataStream@Utils@Dlp@@YA_NAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Dlp::Utils::IsAlternateDataStream(std::wstring_view const &)
0x1800757be  test    al, al
0x1800757c0  jz      short loc_180075812
0x1800757c2  mov     ecx, 91h
0x1800757c7  call    ?GetBoolValue@FeatureControl@Dlp@@YA_NW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetBoolValue(FeatureControlEnum)
0x1800757cc  test    al, al
0x1800757ce  jz      short loc_180075812
0x1800757d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800757d7  cmp     rcx, rdi
0x1800757da  jz      short loc_1800757FA
0x1800757dc  test    byte ptr [rcx+1Ch], 4
0x1800757e0  jz      short loc_1800757FA
0x1800757e2  mov     edx, 178h
0x1800757e7  mov     r9, rbx
0x1800757ea  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x1800757f1  mov     rcx, [rcx+10h]
0x1800757f5  call    WPP_SF_S
0x1800757fa  mov     [rsi], r13d
0x1800757fd  test    r14, r14
0x180075800  jz      loc_180076D9D
0x180075806  mov     dword ptr [r14], 6
0x18007580d  jmp     loc_180076D9D
0x180075812  mov     ecx, 10Bh
0x180075817  call    ?GetBoolValue@FeatureControl@Dlp@@YA_NW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetBoolValue(FeatureControlEnum)
0x18007581c  test    al, al
0x18007581e  jz      short loc_180075881
0x180075820  cmp     [rsp+0A38h+var_998], r13d
0x180075828  jnz     short loc_180075881
0x18007582a  cmp     dword ptr [rsp+0A38h+var_988], r13d
0x180075832  jnz     short loc_180075881
0x180075834  mov     [rsp+0A38h+bIgnoreCase], r13d; bIgnoreCase
0x180075839  or      r9d, 0FFFFFFFFh; cchCount2
0x18007583d  lea     r8, aDeviceMupLanma_0; "\\Device\\Mup\\;LanmanRedirector\\"
0x180075844  or      edx, r9d; cchCount1
0x180075847  mov     rcx, rbx; lpString1
0x18007584a  call    cs:__imp_CompareStringOrdinal
0x180075850  cmp     eax, 2
0x180075853  jnz     short loc_180075881
0x180075855  mov     rcx, cs:WPP_GLOBAL_Control
0x18007585c  cmp     rcx, rdi
0x18007585f  jz      short loc_1800757FA
0x180075861  test    byte ptr [rcx+1Ch], 4
0x180075865  jz      short loc_1800757FA
0x180075867  mov     edx, 179h
0x18007586c  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180075873  mov     rcx, [rcx+10h]
0x180075877  call    WPP_SF_
0x18007587c  jmp     loc_1800757FA
0x180075881  mov     rbx, [rsp+0A38h+var_968]
0x180075889  lea     rdx, [rbx+10h]
0x18007588d  lea     rcx, [rsp+0A38h+SRWLock]
0x180075895  call    ??0?$CGenericAutoLock@U?$CMpReadLockFunctor@VCMpSRWLock@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpSRWLock@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>(CommonUtil::CMpSRWLock const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>::ENUM_LOCK_INITIAL_STATE)
0x18007589a  nop
0x18007589b  cmp     dword ptr [rbx+8], 2
0x18007589f  jz      short loc_180075904
0x1800758a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800758a8  cmp     rcx, rdi
0x1800758ab  jz      short loc_1800758CF
0x1800758ad  test    [rcx+1Ch], r13b
0x1800758b1  jz      short loc_1800758CF
0x1800758b3  mov     edx, 17Ah
0x1800758b8  mov     r9d, 8007139Fh
0x1800758be  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x1800758c5  mov     rcx, [rcx+10h]
0x1800758c9  call    WPP_SF_d
0x1800758ce  nop
0x1800758cf  cmp     [rsp+0A38h+var_970], r12b
0x1800758d7  jz      short loc_1800758E8
0x1800758d9  mov     rcx, [rsp+0A38h+SRWLock]; SRWLock
0x1800758e1  call    cs:__imp_ReleaseSRWLockShared
0x1800758e7  nop
0x1800758e8  mov     rcx, [rsp+0A38h+var_848]; void *
0x1800758f0  test    rcx, rcx
0x1800758f3  jz      short loc_1800758FA
0x1800758f5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800758fa  mov     ebx, 8007139Fh
0x1800758ff  jmp     loc_180076E2E
0x180075904  mov     eax, dword ptr [rsp+0A38h+var_988]
0x18007590b  cmp     eax, 6
0x18007590e  jz      short loc_180075976
0x180075910  mov     r9, [rsp+0A38h+var_980]
0x180075918  mov     r8d, eax
0x18007591b  mov     edx, r15d
0x18007591e  mov     rcx, rbx
0x180075921  call    ?IsCheckAccessForOperationRedundant@CRtpDlpEngine@RealtimeProtection@@AEAA_NW4MpDlpOnOperationActionType@@W4MpDlpOperationOrigin@2@AEBUPPID@@@Z; RealtimeProtection::CRtpDlpEngine::IsCheckAccessForOperationRedundant(MpDlpOnOperationActionType,RealtimeProtection::MpDlpOperationOrigin,PPID const &)
0x180075926  test    al, al
0x180075928  jz      short loc_180075976
0x18007592a  test    r14, r14
0x18007592d  jz      short loc_180075936
0x18007592f  mov     dword ptr [r14], 9
0x180075936  cmp     [rsp+0A38h+var_970], r12b
0x18007593e  jz      short loc_18007594F
0x180075940  mov     rcx, [rsp+0A38h+SRWLock]; SRWLock
0x180075948  call    cs:__imp_ReleaseSRWLockShared
0x18007594e  nop
0x18007594f  mov     rcx, [rsp+0A38h+var_848]; void *
0x180075957  test    rcx, rcx
0x18007595a  jz      short loc_180075962
0x18007595c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180075961  nop
0x180075962  lea     rcx, [rsp+0A38h+var_958]; this
0x18007596a  call    ??1DlpAutoEtwPerfOperation@RealtimeProtection@@QEAA@XZ; RealtimeProtection::DlpAutoEtwPerfOperation::~DlpAutoEtwPerfOperation(void)
0x18007596f  xor     eax, eax
0x180075971  jmp     loc_180076E3D
0x180075976  lea     rcx, [rsp+0A38h+var_6E8]; this
0x18007597e  call    ??0ActionEnforcementState@RealtimeProtection@@QEAA@XZ; RealtimeProtection::ActionEnforcementState::ActionEnforcementState(void)
0x180075983  nop
0x180075984  lea     rbx, qword_18025C818
0x18007598b  mov     rdx, rbx
0x18007598e  lea     rcx, [rsp+0A38h+var_7B0]
0x180075996  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18007599b  nop
0x18007599c  mov     rdx, rbx
0x18007599f  lea     rcx, [rsp+0A38h+var_7D0]
0x1800759a7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800759ac  nop
0x1800759ad  mov     rdx, rbx
0x1800759b0  lea     rcx, [rsp+0A38h+var_790]
0x1800759b8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800759bd  nop
0x1800759be  mov     rdx, rbx
0x1800759c1  lea     rcx, [rsp+0A38h+var_770]
0x1800759c9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800759ce  nop
0x1800759cf  xorps   xmm0, xmm0
0x1800759d2  movups  [rsp+0A38h+var_838], xmm0
0x1800759da  mov     qword ptr [rsp+0A38h+var_838], r12
0x1800759e2  mov     qword ptr [rsp+0A38h+var_838+8], r12
0x1800759ea  lea     rcx, [rsp+0A38h+var_838]
0x1800759f2  call    ?_Alloc_sentinel_and_proxy@?$list@KV?$allocator@K@std@@@std@@AEAAXXZ; std::list<ulong>::_Alloc_sentinel_and_proxy(void)
0x1800759f7  nop
  ... truncated ...
```
