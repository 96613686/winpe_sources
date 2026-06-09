# RealtimeProtection::CRtpDlpEngine::GetFileApplicationAccessFromPolicy(wchar_t const *,wchar_t const *,PPID const &,ulong,std::optional<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> const &,bool,EndpointDlp::Client::ExtendedAttributes const &,uchar *,ulong *,DlpAction *,RealtimeProtection::MpDlpPolicyTraceInfo &,DlpAppGroupInfo &,DlpUnallowedAppType *)

- ea: `0x1800857d0`
- end: `0x1800872ea`
- name: `?GetFileApplicationAccessFromPolicy@CRtpDlpEngine@RealtimeProtection@@QEAAJPEB_W0AEBUPPID@@KAEBV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_NAEBUExtendedAttributes@Client@EndpointDlp@@PEAEPEAKPEAUDlpAction@@AEAUMpDlpPolicyTraceInfo@2@AEAUDlpAppGroupInfo@@PEAW4DlpUnallowedAppType@@@Z`
- size: `6938`
- prototype: ``
- caller_count: `5`
- callee_count: `42`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180076f64`
- `0x180084f38`
- `0x180185714`
- `0x18018d9f0`
- `0x1801927b4`

## callees

- `0x1800249f0`
- `0x180028a10`
- `0x180028d80`
- `0x180029590`
- `0x18002bf88`
- `0x18002ec38`
- `0x18002ece0`
- `0x18002ed90`
- `0x180034420`
- `0x180037afc`
- `0x180038450`
- `0x1800385a0`
- `0x18003f3f8`
- `0x180046d10`
- `0x18004b3bc`
- `0x1800542e8`
- `0x18005c748`
- `0x18005c780`
- `0x1800809d0`
- `0x1800857d0`
- `0x180089510`
- `0x180089fa0`
- `0x180092a68`
- `0x18009351c`
- `0x180095514`
- `0x180097010`
- `0x1800a3610`
- `0x1800ab8fc`
- `0x18010b550`
- `0x18010cb40`
- `0x18010ce3c`
- `0x180119428`
- `0x1801459c8`
- `0x1801481a8`
- `0x18016a4c4`
- `0x180177a48`
- `0x1801a3bbc`
- `0x1801a4188`
- `0x1801a7408`
- `0x1801ef33c`
- `0x18023a310`
- `0x18023a6d0`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x180085b10`
- `MpClient!MpFreeMemory` at `0x180085b10`
- `KERNEL32!CompareStringOrdinal` at `0x180086881`
- `KERNEL32!CompareStringOrdinal` at `0x180086ffc`
- `KERNEL32!CompareStringOrdinal` at `0x18008704a`
- `KERNEL32!CompareStringOrdinal` at `0x180086881`
- `KERNEL32!CompareStringOrdinal` at `0x180086ffc`
- `KERNEL32!CompareStringOrdinal` at `0x18008704a`
- `KERNEL32!DebugBreak` at `0x180085a0c`
- `KERNEL32!DebugBreak` at `0x180085a0c`

## string_xrefs

- `0x180085946`: `MpDlp_DebugGetFileApplicationAccessPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RealtimeProtection::CRtpDlpEngine::GetFileApplicationAccessFromPolicy(
        __int64 a1,
        _WORD *a2,
        const WCHAR *a3,
        FILETIME *a4,
        int a5,
        __int64 a6,
        char a7,
        EndpointDlp::Client::ExtendedAttributes *a8,
        unsigned __int8 *a9,
        unsigned int *a10,
        struct DlpAction *a11,
        void *a12,
        void *a13,
        _DWORD *a14)
{
  __int64 *v14; // rdi
  const wchar_t *v15; // r15
  _WORD *v16; // r14
  char v17; // r13
  wchar_t **v18; // r8
  int MiscStringValue; // eax
  __int64 v20; // rbx
  __int128 *v21; // r8
  _QWORD *v22; // r15
  unsigned __int64 v23; // rax
  char *v24; // rdi
  __int64 v25; // rax
  const struct std::nothrow_t *v26; // rdx
  void *v27; // rcx
  const struct std::nothrow_t *v28; // rdx
  void *v29; // rcx
  int Value; // eax
  FILETIME *v31; // rbx
  int AppNameFromAppDelegationCache; // eax
  __int64 *v33; // rax
  bool *v34; // r8
  _WORD *v35; // rax
  unsigned int *v36; // r14
  int FileApplicationAccess; // eax
  unsigned int v38; // ebx
  PVOID *v39; // rcx
  const struct std::nothrow_t *v40; // rdx
  void *v41; // rcx
  int DlpDelegationFlag; // eax
  wchar_t **v44; // r8
  unsigned int v45; // r15d
  DWORD dwLowDateTime; // r15d
  __int64 v47; // rbx
  const WCHAR *v48; // rdi
  __int64 v49; // rax
  const WCHAR *v50; // r13
  __int64 v51; // rcx
  int PolicyActionsByExtension; // ebx
  unsigned int v53; // edi
  unsigned int v54; // eax
  unsigned __int64 v55; // r8
  __int64 v56; // rcx
  __int64 v57; // rax
  struct DlpAction *v58; // r10
  _DWORD *v59; // rdx
  int v60; // r14d
  __int64 v61; // rbx
  void **v62; // rdx
  size_t v63; // rbx
  char *v64; // r15
  __int64 v65; // rbx
  void **v66; // rdx
  char *v67; // rcx
  __int64 v68; // rbx
  void **v69; // rdx
  int v70; // ebx
  int v71; // eax
  wchar_t *v72; // rbx
  DWORD v73; // ebx
  bool v74; // zf
  const WCHAR *v75; // rcx
  __int64 v76; // rax
  __int64 v77; // rax
  _QWORD *Instance; // rax
  unsigned int v79; // eax
  unsigned __int64 v80; // r8
  __int64 v81; // rcx
  __int64 v82; // rax
  struct DlpAction *v83; // r10
  _DWORD *v84; // rdx
  __int64 v85; // rbx
  void **v86; // rdx
  size_t v87; // rbx
  _WORD *v88; // r15
  __int64 v89; // rbx
  void **v90; // rdx
  __int64 v91; // rbx
  void **v92; // rdx
  int v93; // ebx
  int v94; // eax
  const struct std::nothrow_t *v95; // rdx
  unsigned __int8 v96; // r13
  int v97; // r14d
  __int64 v98; // rcx
  wchar_t *v99; // rbx
  __int64 v100; // rax
  int v101; // eax
  __int64 v102; // r8
  __int64 v103; // rcx
  __int64 v104; // rax
  __int64 v105; // rcx
  void **v106; // rdx
  __int64 v107; // rbx
  __int64 v108; // rbx
  void **v109; // rdx
  __int64 v110; // rbx
  void **v111; // rdx
  int v112; // eax
  __int64 v113; // rcx
  __int64 v114; // rax
  int v115; // eax
  __int64 v116; // r8
  __int64 v117; // rcx
  __int64 v118; // rax
  __int64 v119; // rcx
  void **v120; // rdx
  __int64 v121; // rbx
  __int64 v122; // rbx
  void **v123; // rdx
  __int64 v124; // rax
  int v125; // ebx
  int v126; // eax
  const WCHAR *v127; // r8
  _QWORD *v128; // r15
  const WCHAR *v129; // rcx
  int v130; // eax
  _QWORD *v131; // rbx
  const WCHAR *v132; // r8
  const WCHAR *v133; // rcx
  unsigned __int8 v134; // cl
  const struct std::nothrow_t *v135; // rdx
  unsigned __int8 v136; // al
  unsigned int v137; // r9d
  unsigned int *v138; // r8
  signed __int64 v139; // r11
  int v140; // eax
  unsigned int v141; // r10d
  unsigned int v142; // edx
  unsigned int v143; // ecx
  LPCWCH *v144; // rax
  const struct std::nothrow_t *v145; // rdx
  _BYTE v146[32]; // [rsp+0h] [rbp-648h] BYREF
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-628h]
  struct DlpAction *v148; // [rsp+28h] [rbp-620h]
  unsigned __int8 v149[16]; // [rsp+50h] [rbp-5F8h] BYREF
  void *v150; // [rsp+60h] [rbp-5E8h]
  wchar_t v151[4]; // [rsp+70h] [rbp-5D8h] BYREF
  void *v152; // [rsp+78h] [rbp-5D0h]
  const WCHAR *v153; // [rsp+80h] [rbp-5C8h]
  __int64 v154; // [rsp+88h] [rbp-5C0h]
  wchar_t *v155; // [rsp+90h] [rbp-5B8h]
  __int64 *v156; // [rsp+98h] [rbp-5B0h]
  EndpointDlp::Client::ExtendedAttributes *v157; // [rsp+A0h] [rbp-5A8h]
  unsigned int *v158; // [rsp+A8h] [rbp-5A0h]
  void *v159; // [rsp+B0h] [rbp-598h]
  __int64 v160; // [rsp+C0h] [rbp-588h]
  unsigned __int8 *v161; // [rsp+C8h] [rbp-580h]
  struct DlpAction *v162; // [rsp+D0h] [rbp-578h]
  wchar_t *v163; // [rsp+E0h] [rbp-568h] BYREF
  __int64 v164; // [rsp+E8h] [rbp-560h]
  void *v165; // [rsp+F0h] [rbp-558h]
  _DWORD *v166; // [rsp+F8h] [rbp-550h]
  _WORD *v167; // [rsp+100h] [rbp-548h]
  LPCWCH v168; // [rsp+108h] [rbp-540h] BYREF
  __int64 v169; // [rsp+110h] [rbp-538h]
  LPCWCH lpString2; // [rsp+118h] [rbp-530h] BYREF
  std::_Ref_count_base *v171; // [rsp+120h] [rbp-528h]
  char v172; // [rsp+128h] [rbp-520h]
  FILETIME *lpFileTime1; // [rsp+130h] [rbp-518h]
  wchar_t *v174; // [rsp+140h] [rbp-508h] BYREF
  std::_Ref_count_base *v175; // [rsp+148h] [rbp-500h]
  const std::exception *v176; // [rsp+158h] [rbp-4F0h] BYREF
  const std::exception *v177; // [rsp+160h] [rbp-4E8h] BYREF
  LPCWCH lpString1; // [rsp+168h] [rbp-4E0h] BYREF
  __int64 v179[2]; // [rsp+170h] [rbp-4D8h] BYREF
  __m128i si128; // [rsp+180h] [rbp-4C8h]
  LPCWCH v181[2]; // [rsp+190h] [rbp-4B8h] BYREF
  __m128i v182; // [rsp+1A0h] [rbp-4A8h]
  LPCWCH v183[2]; // [rsp+1B0h] [rbp-498h] BYREF
  __m128i v184; // [rsp+1C0h] [rbp-488h]
  _QWORD v185[2]; // [rsp+1D0h] [rbp-478h] BYREF
  unsigned __int64 v186; // [rsp+1E0h] [rbp-468h]
  unsigned __int64 v187; // [rsp+1E8h] [rbp-460h]
  __int128 v188; // [rsp+1F0h] [rbp-458h] BYREF
  __m128i v189; // [rsp+200h] [rbp-448h]
  _OWORD v190[2]; // [rsp+210h] [rbp-438h] BYREF
  _BYTE v191[4]; // [rsp+230h] [rbp-418h] BYREF
  int v192; // [rsp+234h] [rbp-414h]
  _BYTE v193[384]; // [rsp+238h] [rbp-410h] BYREF
  void *Src[2]; // [rsp+3B8h] [rbp-290h] BYREF
  unsigned __int64 v195; // [rsp+3C8h] [rbp-280h]
  unsigned __int64 v196; // [rsp+3D0h] [rbp-278h]
  void *v197[2]; // [rsp+3D8h] [rbp-270h] BYREF
  unsigned __int64 v198; // [rsp+3E8h] [rbp-260h]
  unsigned __int64 v199; // [rsp+3F0h] [rbp-258h]
  void *v200[2]; // [rsp+3F8h] [rbp-250h] BYREF
  unsigned __int64 v201; // [rsp+408h] [rbp-240h]
  unsigned __int64 v202; // [rsp+410h] [rbp-238h]
  char v203; // [rsp+418h] [rbp-230h]
  _BYTE v204[32]; // [rsp+420h] [rbp-228h] BYREF
  _BYTE v205[32]; // [rsp+440h] [rbp-208h] BYREF
  _BYTE v206[48]; // [rsp+460h] [rbp-1E8h] BYREF
  char v207; // [rsp+490h] [rbp-1B8h]
  char v208; // [rsp+498h] [rbp-1B0h]
  _WORD v209[136]; // [rsp+4A0h] [rbp-1A8h] BYREF
  __int64 v210; // [rsp+5B0h] [rbp-98h] BYREF
  __int128 v211; // [rsp+5B8h] [rbp-90h]
  __int128 v212; // [rsp+5C8h] [rbp-80h]
  __int128 v213; // [rsp+5D8h] [rbp-70h]
  __int128 v214; // [rsp+5E8h] [rbp-60h]
  __int64 v215; // [rsp+5F8h] [rbp-50h]

  v14 = (__int64 *)a4;
  v156 = (__int64 *)a4;
  v15 = a3;
  lpString2 = a3;
  v167 = a2;
  v16 = a2;
  v165 = a2;
  v152 = a4;
  v155 = a2;
  v174 = a2;
  v153 = a3;
  lpFileTime1 = a4;
  v168 = (LPCWCH)a4;
  v154 = a6;
  v157 = a8;
  v163 = (wchar_t *)a8;
  v161 = a9;
  v158 = a10;
  v162 = a11;
  v159 = a12;
  v150 = a13;
  v166 = a14;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
  memset(v209, 0, 0x10Eu);
  *(_OWORD *)v179 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v179[0]) = 0;
  v17 = 0;
  *(_QWORD *)v151 = 0;
  MiscStringValue = RealtimeProtection::DlpUtils::DlpGetMiscStringValue(
                      (RealtimeProtection::DlpUtils *)L"MpDlp_DebugGetFileApplicationAccessPath",
                      v151,
                      v18);
  v20 = *(_QWORD *)v151;
  if ( MiscStringValue >= 0 && *(_QWORD *)v151 )
  {
    try
    {
      std::wstring::wstring(&v188, *(_QWORD *)v151);
      std::wstring::wstring(v185, v155);
      v21 = &v188;
      if ( v189.m128i_i64[1] > 7uLL )
        v21 = (__int128 *)v188;
      v22 = v185;
      v23 = v187;
      if ( v187 > 7 )
        v22 = (_QWORD *)v185[0];
      if ( v189.m128i_i64[0] <= v186 )
      {
        _mm_lfence();
        if ( !v189.m128i_i64[0]
          || (v24 = (char *)v22 + 2 * v186, v25 = _std_search_2(v22, v24, v21, v189.m128i_i64[0]), (char *)v25 != v24)
          && (v25 - (__int64)v22) >> 1 != -1 )
        {
          DebugBreak();
        }
        v23 = v187;
      }
    }
    catch ( const std::exception *v176 )
    {
      CommonUtil::HrFromStdException(v176, (const struct std::exception *)v146);
    }
    catch ( ... )
    {
      v15 = v153;
      v16 = v165;
      lpString2 = v153;
      v14 = (__int64 *)v152;
      v167 = v165;
      v20 = *(_QWORD *)v151;
      v17 = 0;
      goto LABEL_26;
    }
    if ( v23 > 7 )
    {
      v26 = (const struct std::nothrow_t *)(2 * v23 + 2);
      v27 = (void *)v185[0];
      if ( (unsigned __int64)v26 >= 0x1000 )
      {
        v26 = (const struct std::nothrow_t *)(2 * v23 + 41);
        v27 = *(void **)(v185[0] - 8LL);
        if ( (unsigned __int64)(v185[0] - (_QWORD)v27 - 8LL) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v27, v26);
    }
    v186 = 0;
    v187 = 7;
    LOWORD(v185[0]) = 0;
    if ( v189.m128i_i64[1] > 7uLL )
    {
      v28 = (const struct std::nothrow_t *)(2 * v189.m128i_i64[1] + 2);
      v29 = (void *)v188;
      if ( (unsigned __int64)v28 >= 0x1000 )
      {
        v28 = (const struct std::nothrow_t *)(2 * v189.m128i_i64[1] + 41);
        v29 = *(void **)(v188 - 8);
        if ( (unsigned __int64)(v188 - (_QWORD)v29 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v29, v28);
    }
    v14 = v156;
    v15 = lpString2;
  }
LABEL_26:
  if ( v20 )
    MpFreeMemory(v20);
  Value = Dlp::FeatureControl::GetValue(166);
  v31 = lpFileTime1;
  if ( Value )
  {
    AppNameFromAppDelegationCache = RealtimeProtection::DlpProcessCache::GetAppNameFromAppDelegationCache(
                                      lpFileTime1,
                                      v179);
    if ( AppNameFromAppDelegationCache < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          101,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          v31[1].dwLowDateTime,
          AppNameFromAppDelegationCache);
    }
    else
    {
      v17 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v33 = v179;
        if ( si128.m128i_i64[1] > 7uLL )
          v33 = (__int64 *)v179[0];
        WPP_SF_dSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v15, (__int64)v33);
      }
    }
  }
  if ( v161 )
    *v161 = 0;
  v188 = 0;
  v189 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v188) = 0;
  v190[0] = 0;
  v190[1] = v189;
  LOWORD(v190[0]) = 0;
  std::wstring::operator=(v159, &v188);
  v165 = (char *)v159 + 32;
  std::wstring::operator=((char *)v159 + 32, v190);
  RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)&v188);
  v35 = v150;
  *(_WORD *)v150 = 0;
  v152 = v35 + 73;
  v35[73] = 0;
  *(_QWORD *)v151 = v35 + 202;
  v35[202] = 0;
  if ( byte_180313780 )
  {
    if ( v17 )
    {
      v15 = (const wchar_t *)v179;
      if ( si128.m128i_i64[1] > 7uLL )
        v15 = (const wchar_t *)v179[0];
    }
    v36 = v158;
    FileApplicationAccess = RealtimeProtection::TestDlpPolicyCache::GetFileApplicationAccess(
                              (RealtimeProtection::TestDlpPolicyCache *)(v35 + 73),
                              v155,
                              v15,
                              v161,
                              v158,
                              v162,
                              (struct DlpTraceInfo *)v209);
    v38 = FileApplicationAccess;
    v39 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v15, FileApplicationAccess);
        v39 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v39 != &WPP_GLOBAL_Control && (*((_BYTE *)v39 + 28) & 4) != 0 )
        WPP_SF_Dd(v39[2], 102, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v38, *v36);
    }
    try
    {
      std::wstring::assign(v165, &v209[61]);
      std::wstring::assign(v159, v209);
    }
    catch ( const std::exception *v177 )
    {
      CommonUtil::HrFromStdException(v177, (const struct std::exception *)v146);
    }
    catch ( ... )
    {
      LODWORD(v153) = -2147467259;
      v38 = -2147467259;
      goto LABEL_51;
    }
    if ( (v38 & 0x80000000) != 0 )
    {
LABEL_51:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v38);
    }
    if ( si128.m128i_i64[1] > 7uLL )
    {
      v40 = (const struct std::nothrow_t *)(2 * si128.m128i_i64[1] + 2);
      v41 = (void *)v179[0];
      if ( (unsigned __int64)v40 >= 0x1000 )
      {
        v40 = (const struct std::nothrow_t *)(2 * si128.m128i_i64[1] + 41);
        v41 = *(void **)(v179[0] - 8);
        if ( (unsigned __int64)(v179[0] - (_QWORD)v41 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v41, v40);
    }
    return v38;
  }
  v149[0] = 0;
  DlpDelegationFlag = RealtimeProtection::DlpProcessCache::GetDlpDelegationFlag(v31, (const struct PPID *)v149, v34);
  v45 = DlpDelegationFlag;
  if ( DlpDelegationFlag < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        104,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)DlpDelegationFlag);
    v45 = 0;
  }
  LODWORD(v153) = v149[0] != 0;
  v149[0] = 0;
  LODWORD(v156) = 0;
  v160 = *v14;
  if ( a7 )
  {
    if ( *((_BYTE *)v163 + 64) && *((_DWORD *)v163 + 12) || !*(_BYTE *)(v154 + 32) )
    {
      v53 = 10;
      v50 = lpString2;
      v60 = (int)v156;
      goto LABEL_134;
    }
    v208 = 0;
    dwLowDateTime = v31[1].dwLowDateTime;
    v47 = -1;
    if ( v17 )
    {
      v48 = (const WCHAR *)v179;
      if ( si128.m128i_i64[1] > 7uLL )
        v48 = (const WCHAR *)v179[0];
      do
        ++v47;
      while ( v48[v47] );
      v163 = v174;
      v49 = -1;
      do
        ++v49;
      while ( v16[v49] );
      v50 = lpString2;
    }
    else
    {
      v50 = lpString2;
      v48 = lpString2;
      do
        ++v47;
      while ( lpString2[v47] );
      v163 = v174;
      v49 = -1;
      do
        ++v49;
      while ( v16[v49] );
    }
    v164 = v49;
    v51 = *(_QWORD *)EndpointDlp::endpointDlpImpl::GetInstance(&v174);
    lpString2 = v48;
    v171 = (std::_Ref_count_base *)v47;
    v172 = 1;
    PolicyActionsByExtension = EndpointDlp::endpointDlpImpl::GetPolicyActionsByExtension(
                                 v51,
                                 v154,
                                 (unsigned int)&v163,
                                 (unsigned int)&lpString2,
                                 dwLowDateTime,
                                 v160,
                                 a5,
                                 (_DWORD)v153,
                                 (__int64)v191);
    if ( v175 )
      std::_Ref_count_base::_Decref(v175);
    if ( PolicyActionsByExtension < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)PolicyActionsByExtension);
LABEL_85:
      if ( v208 )
      {
        if ( v207 )
        {
          std::optional<std::wstring>::~optional<std::wstring>(v206);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v205);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v204);
        }
        if ( v203 )
        {
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v200);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v197);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
        }
        EndpointDlp::Client::FileRuleInfo::~FileRuleInfo((EndpointDlp::Client::FileRuleInfo *)v193);
      }
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v179);
      return (unsigned int)PolicyActionsByExtension;
    }
    v53 = 10;
    if ( !v208 )
    {
      v149[0] = 0;
      *v158 = 0;
      v209[0] = 0;
      v209[61] = 0;
      v60 = 0;
      LODWORD(v156) = 0;
      goto LABEL_115;
    }
    v149[0] = v191[0];
    v54 = *v158;
    if ( *v158 >= 0xA )
    {
      v55 = 10;
      *v158 = 10;
      v56 = 0;
    }
    else
    {
      v55 = v54;
      *v158 = v54;
      v56 = 0;
      if ( !v54 )
        goto LABEL_100;
    }
    v57 = 0;
    v58 = v162;
    do
    {
      v59 = (_DWORD *)((char *)v58 + 8 * v57);
      *v59 = v56;
      if ( (unsigned __int64)(int)v56 >= 0xA )
        std::array<EndpointDlp::Client::DlpActionInfoRuleType,10>::_Xran(v56, v59, v55);
      v59[1] = *(_DWORD *)&v193[32 * (int)v56 + 4];
      v56 = (unsigned int)(v56 + 1);
      v57 = (unsigned int)v56;
    }
    while ( (unsigned int)v56 < v55 );
LABEL_100:
    EndpointDlp::Interop::_anonymous_namespace_::MarshalTraceInfo(v191, v209, v55);
    v60 = v192;
    LODWORD(v156) = v192;
    if ( v203 )
    {
      v61 = 72;
      if ( v195 < 0x48 )
        v61 = v195;
      v62 = Src;
      if ( v196 > 7 )
        v62 = (void **)Src[0];
      v63 = 2 * v61;
      v64 = (char *)v150;
      memmove(v150, v62, v63);
      *(_WORD *)&v64[v63] = 0;
      v65 = 128;
      if ( v198 < 0x80 )
        v65 = v198;
      v66 = v197;
      if ( v199 > 7 )
        v66 = (void **)v197[0];
      memmove(v152, v66, 2 * v65);
      v67 = (char *)v150;
      *((_WORD *)v150 + v65 + 73) = 0;
      v68 = 256;
      if ( v201 < 0x100 )
        v68 = v201;
      v69 = v200;
      if ( v202 > 7 )
        v69 = (void **)v200[0];
      memmove(v67 + 404, v69, 2 * v68);
      *((_WORD *)v150 + v68 + 202) = 0;
LABEL_116:
      if ( !*(_BYTE *)(v154 + 32) )
        std::_Throw_bad_optional_access();
      v70 = (int)v155;
      v71 = RealtimeProtection::DlpUtils::ResolvePolicyTraceInfoByExtension(v155);
      v45 = v71;
      if ( v71 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            106,
            (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            v70,
            v71);
        if ( v208 )
        {
          if ( v207 )
          {
            std::optional<std::wstring>::~optional<std::wstring>(v206);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v205);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v204);
          }
          if ( v203 )
          {
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v200);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v197);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
          }
          EndpointDlp::Client::FileRuleInfo::~FileRuleInfo((EndpointDlp::Client::FileRuleInfo *)v193);
        }
LABEL_188:
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v179);
        return v45;
      }
      if ( v208 )
      {
        if ( v207 )
        {
          std::optional<std::wstring>::~optional<std::wstring>(v206);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v205);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v204);
        }
        if ( v203 )
        {
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v200);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v197);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
        }
        EndpointDlp::Client::FileRuleInfo::~FileRuleInfo((EndpointDlp::Client::FileRuleInfo *)v193);
        v72 = (wchar_t *)(v168 + 4);
        goto LABEL_182;
      }
LABEL_134:
      v72 = (wchar_t *)(v168 + 4);
      goto LABEL_182;
    }
LABEL_115:
    *(_WORD *)v150 = 0;
    *(_WORD *)v152 = 0;
    **(_WORD **)v151 = 0;
    goto LABEL_116;
  }
  v208 = 0;
  v174 = (wchar_t *)&v31[1];
  v73 = v31[1].dwLowDateTime;
  v74 = v17 == 0;
  v50 = lpString2;
  if ( v74 )
  {
    v75 = lpString2;
  }
  else
  {
    v75 = (const WCHAR *)v179;
    if ( si128.m128i_i64[1] > 7uLL )
      v75 = (const WCHAR *)v179[0];
  }
  v168 = v75;
  v76 = -1;
  do
    ++v76;
  while ( v75[v76] );
  v169 = v76;
  v163 = v155;
  v77 = -1;
  do
    ++v77;
  while ( v167[v77] );
  v164 = v77;
  Instance = (_QWORD *)EndpointDlp::endpointDlpImpl::GetInstance(&lpString2);
  PolicyActionsByExtension = EndpointDlp::endpointDlpImpl::GetFileApplicationAccess(
                               *Instance,
                               (unsigned int)&v163,
                               (unsigned int)&v168,
                               v154,
                               v73,
                               v160,
                               a5,
                               (__int64)v157,
                               (_DWORD)v153,
                               (__int64)v191);
  if ( v171 )
    std::_Ref_count_base::_Decref(v171);
  if ( PolicyActionsByExtension < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)PolicyActionsByExtension);
    goto LABEL_85;
  }
  v53 = 10;
  if ( !v208 )
  {
    v149[0] = 0;
    *v158 = 0;
    v60 = 0;
    LODWORD(v156) = 0;
    goto LABEL_172;
  }
  v149[0] = v191[0];
  v79 = *v158;
  if ( *v158 >= 0xA )
  {
    v80 = 10;
    *v158 = 10;
    v81 = 0;
  }
  else
  {
    v80 = v79;
    *v158 = v79;
    v81 = 0;
    if ( !v79 )
      goto LABEL_157;
  }
  v82 = 0;
  v83 = v162;
  do
  {
    v84 = (_DWORD *)((char *)v83 + 8 * v82);
    *v84 = v81;
    if ( (unsigned __int64)(int)v81 >= 0xA )
      std::array<EndpointDlp::Client::DlpActionInfoRuleType,10>::_Xran(v81, v84, v80);
    v84[1] = *(_DWORD *)&v193[32 * (int)v81 + 4];
    v81 = (unsigned int)(v81 + 1);
    v82 = (unsigned int)v81;
  }
  while ( (unsigned int)v81 < v80 );
LABEL_157:
  EndpointDlp::Interop::_anonymous_namespace_::MarshalTraceInfo(v191, v209, v80);
  v60 = v192;
  LODWORD(v156) = v192;
  if ( v203 )
  {
    v85 = 72;
    if ( v195 < 0x48 )
      v85 = v195;
    v86 = Src;
    if ( v196 > 7 )
      v86 = (void **)Src[0];
    v87 = v85;
    v88 = v150;
    memmove(v150, v86, v87 * 2);
    v88[v87] = 0;
    v89 = 128;
    if ( v198 < 0x80 )
      v89 = v198;
    v90 = v197;
    if ( v199 > 7 )
      v90 = (void **)v197[0];
    memmove(v88 + 73, v90, 2 * v89);
    v88[v89 + 73] = 0;
    v91 = 256;
    if ( v201 < 0x100 )
      v91 = v201;
    v92 = v200;
    if ( v202 > 7 )
      v92 = (void **)v200[0];
    memmove(v88 + 202, v92, 2 * v91);
    v88[v91 + 202] = 0;
    goto LABEL_173;
  }
LABEL_172:
  *(_WORD *)v150 = 0;
  *(_WORD *)v152 = 0;
  **(_WORD **)v151 = 0;
LABEL_173:
  v93 = (int)v155;
  v94 = RealtimeProtection::DlpUtils::ResolvePolicyTraceInfo(v155, v154, v157, v209, v159);
  v45 = v94;
  if ( v94 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        108,
        (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        v93,
        v94);
    if ( v208 )
      EndpointDlp::Client::FileAccessInfo::~FileAccessInfo((EndpointDlp::Client::FileAccessInfo *)v191);
    goto LABEL_188;
  }
  if ( v208 )
    EndpointDlp::Client::FileAccessInfo::~FileAccessInfo((EndpointDlp::Client::FileAccessInfo *)v191);
  v72 = v174;
LABEL_182:
  *v161 = v149[0];
  if ( v166 )
    *v166 = v60;
  lpString1 = 0;
  if ( (int)RealtimeProtection::DlpProcessCache::GetApplicationOriginalFileName(
              (RealtimeProtection::DlpProcessCache *)lpFileTime1,
              (const struct PPID *)&lpString1,
              v44) < 0
    || CompareStringOrdinal(lpString1, -1, v50, -1, 1) == 2 )
  {
    goto LABEL_186;
  }
  v96 = 0;
  v210 = 0;
  v211 = 0;
  v212 = 0;
  v213 = 0;
  v214 = 0;
  v215 = 0;
  memset(v209, 0, 0x10Eu);
  v97 = 0;
  *(_OWORD *)v181 = 0;
  v182 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v181[0]) = 0;
  *(_OWORD *)v183 = 0;
  v184 = v182;
  LOWORD(v183[0]) = 0;
  if ( a7 )
  {
    if ( EndpointDlp::Client::ExtendedAttributes::IsDlpExtendedAttributeHasData(v157) || !*(_BYTE *)(v154 + 32) )
      goto LABEL_258;
    v208 = 0;
    v168 = lpString1;
    v98 = -1;
    do
      ++v98;
    while ( lpString1[v98] );
    v169 = v98;
    v99 = v155;
    v163 = v155;
    v100 = -1;
    do
      ++v100;
    while ( v167[v100] );
    v164 = v100;
    v101 = EndpointDlp::Client::GetPolicyActionsByExtension(
             v154,
             (unsigned int)&v163,
             (unsigned int)&v168,
             lpFileTime1[1].dwLowDateTime,
             v160,
             a5,
             (_DWORD)v153,
             (__int64)v191);
    if ( v101 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          109,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)v101);
LABEL_225:
      if ( v208 )
        EndpointDlp::Client::FileAccessInfo::~FileAccessInfo((EndpointDlp::Client::FileAccessInfo *)v191);
      RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v181);
LABEL_186:
      if ( lpString1 )
        operator delete((void *)lpString1, v95);
      goto LABEL_188;
    }
    if ( v208 )
    {
      v96 = v191[0];
      v103 = 0;
      v104 = 0;
      do
      {
        *((_DWORD *)&v210 + 2 * v104) = v103;
        if ( (unsigned __int64)(int)v103 >= 0xA )
          std::array<EndpointDlp::Client::DlpActionInfoRuleType,10>::_Xran(v103, 8 * v104, v102);
        *((_DWORD *)&v210 + 2 * v104 + 1) = *(_DWORD *)&v193[32 * (int)v103 + 4];
        v103 = (unsigned int)(v103 + 1);
        v104 = (unsigned int)v103;
      }
      while ( (unsigned int)v103 < 0xAuLL );
      EndpointDlp::Interop::_anonymous_namespace_::MarshalTraceInfo(v191, v209, v102);
      v97 = v192;
      if ( v203 )
      {
        v105 = 72;
        if ( v195 < 0x48 )
          v105 = v195;
        v106 = Src;
        if ( v196 > 7 )
          v106 = (void **)Src[0];
        v107 = 2 * v105;
        memmove(v150, v106, 2 * v105);
        *(_WORD *)((char *)v150 + v107) = 0;
        v108 = 128;
        if ( v198 < 0x80 )
          v108 = v198;
        v109 = v197;
        if ( v199 > 7 )
          v109 = (void **)v197[0];
        memmove(v152, v109, 2 * v108);
        *((_WORD *)v150 + v108 + 73) = 0;
        v110 = 256;
        if ( v201 < 0x100 )
          v110 = v201;
        v111 = v200;
        if ( v202 > 7 )
          v111 = (void **)v200[0];
        memmove(*(void **)v151, v111, 2 * v110);
        *((_WORD *)v150 + v110 + 202) = 0;
        v99 = v155;
LABEL_220:
        if ( !*(_BYTE *)(v154 + 32) )
          std::_Throw_bad_optional_access();
        v112 = RealtimeProtection::DlpUtils::ResolvePolicyTraceInfoByExtension(v99);
        if ( v112 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              110,
              (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
              (_DWORD)v99,
              v112);
          goto LABEL_225;
        }
        goto LABEL_256;
      }
    }
    else
    {
      v96 = 0;
      v53 = 0;
      v97 = 0;
    }
    *(_WORD *)v150 = 0;
    *(_WORD *)v152 = 0;
    **(_WORD **)v151 = 0;
    goto LABEL_220;
  }
  v208 = 0;
  v168 = lpString1;
  v113 = -1;
  do
    ++v113;
  while ( lpString1[v113] );
  v169 = v113;
  v163 = v155;
  v114 = -1;
  do
    ++v114;
  while ( v167[v114] );
  v164 = v114;
  v115 = EndpointDlp::Client::GetFileApplicationAccess(
           (unsigned int)&v163,
           (unsigned int)&v168,
           v154,
           *(_DWORD *)v72,
           v160,
           a5,
           (__int64)v157,
           (_DWORD)v153,
           (__int64)v191);
  if ( v115 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        111,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)v115);
    goto LABEL_225;
  }
  if ( !v208 )
  {
    v96 = 0;
    v53 = 0;
    v97 = 0;
LABEL_251:
    *(_WORD *)v150 = 0;
    *(_WORD *)v152 = 0;
    **(_WORD **)v151 = 0;
    goto LABEL_252;
  }
  v96 = v191[0];
  v117 = 0;
  v118 = 0;
  do
  {
    *((_DWORD *)&v210 + 2 * v118) = v117;
    if ( (unsigned __int64)(int)v117 >= 0xA )
      std::array<EndpointDlp::Client::DlpActionInfoRuleType,10>::_Xran(v117, 8 * v118, v116);
    *((_DWORD *)&v210 + 2 * v118 + 1) = *(_DWORD *)&v193[32 * (int)v117 + 4];
    v117 = (unsigned int)(v117 + 1);
    v118 = (unsigned int)v117;
  }
  while ( (unsigned int)v117 < 0xAuLL );
  EndpointDlp::Interop::_anonymous_namespace_::MarshalTraceInfo(v191, v209, v116);
  v97 = v192;
  if ( !v203 )
    goto LABEL_251;
  v119 = 72;
  if ( v195 < 0x48 )
    v119 = v195;
  v120 = Src;
  if ( v196 > 7 )
    v120 = (void **)Src[0];
  v121 = 2 * v119;
  memmove(v150, v120, 2 * v119);
  *(_WORD *)((char *)v150 + v121) = 0;
  v122 = 128;
  if ( v198 < 0x80 )
    v122 = v198;
  v123 = v197;
  if ( v199 > 7 )
    v123 = (void **)v197[0];
  memmove(v152, v123, 2 * v122);
  *((_WORD *)v150 + v122 + 73) = 0;
  v124 = std::wstring::copy(v200, *(void **)v151);
  *((_WORD *)v150 + v124 + 202) = 0;
LABEL_252:
  v125 = (int)v155;
  v126 = RealtimeProtection::DlpUtils::ResolvePolicyTraceInfo(v155, v154, v157, v209, v181);
  if ( v126 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        112,
        (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        v125,
        v126);
    goto LABEL_225;
  }
LABEL_256:
  if ( v208 )
    EndpointDlp::Client::FileAccessInfo::~FileAccessInfo((EndpointDlp::Client::FileAccessInfo *)v191);
LABEL_258:
  if ( v53 != *v158 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v53, *v158);
LABEL_319:
    RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v181);
    if ( lpString1 )
      operator delete((void *)lpString1, v145);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v179);
    return 1;
  }
  v127 = (const WCHAR *)v181;
  if ( v182.m128i_i64[1] > 7uLL )
    v127 = v181[0];
  v128 = v159;
  v129 = (const WCHAR *)v159;
  if ( *((_QWORD *)v159 + 3) > 7u )
    v129 = *(const WCHAR **)v159;
  v130 = CompareStringOrdinal(v129, -1, v127, -1, 1);
  v131 = v165;
  if ( v130 != 2 )
    goto LABEL_311;
  v132 = (const WCHAR *)v183;
  if ( v184.m128i_i64[1] > 7uLL )
    v132 = v183[0];
  v133 = (const WCHAR *)v165;
  if ( *((_QWORD *)v165 + 3) > 7u )
    v133 = *(const WCHAR **)v165;
  if ( CompareStringOrdinal(v133, -1, v132, -1, 1) != 2 )
  {
LABEL_311:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( v131[3] > 7u )
        v131 = (_QWORD *)*v131;
      v144 = v183;
      if ( v184.m128i_i64[1] > 7uLL )
        v144 = (LPCWCH *)v183[0];
      if ( v128[3] > 7u )
        v128 = (_QWORD *)*v128;
      WPP_SF_SSSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v128, (__int64)v144, (__int64)v131);
    }
    goto LABEL_319;
  }
  if ( (_DWORD)v156 && (v97 && v97 != (_DWORD)v156 || v96) || (v134 = v149[0], v97) && v149[0] )
  {
    *v161 = v96;
    if ( v166 )
      *v166 = v97;
    memmove(v162, &v210, 8LL * v53);
  }
  else
  {
    if ( v166 )
    {
      if ( (_DWORD)v156 )
        v97 = (int)v156;
      *v166 = v97;
    }
    v136 = v134 || v96;
    *v161 = v136;
    v137 = 0;
    if ( v53 )
    {
      v138 = (unsigned int *)((char *)v162 + 4);
      v139 = (char *)&v210 - (char *)v162;
      while ( 1 )
      {
        v140 = *(unsigned int *)((char *)v138 + v139 - 4);
        if ( v140 != *(v138 - 1) )
          break;
        v141 = *(unsigned int *)((char *)v138 + v139);
        v142 = 0;
        if ( v141 != 5 )
          v142 = *(unsigned int *)((char *)v138 + v139);
        v143 = 0;
        if ( *v138 != 5 )
          v143 = *v138;
        if ( v142 == 4 )
          v142 = 1;
        if ( v143 == 4 )
          v143 = 1;
        if ( v142 > v143 )
          *v138 = v141;
        ++v137;
        v138 += 2;
        if ( v137 >= v53 )
          goto LABEL_281;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LODWORD(v148) = *(v138 - 1);
        bIgnoreCase[0] = v140;
        WPP_SF_LdL(*((_QWORD *)WPP_GLOBAL_Control + 2));
      }
      goto LABEL_319;
    }
  }
LABEL_281:
  RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v181);
  if ( lpString1 )
    operator delete((void *)lpString1, v135);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v179);
  return 0;
}

```

## disassembly

```asm
0x1800857d0  push    rbx
0x1800857d2  push    rsi
0x1800857d3  push    rdi
0x1800857d4  push    r12
0x1800857d6  push    r13
0x1800857d8  push    r14
0x1800857da  push    r15
0x1800857dc  sub     rsp, 610h
0x1800857e3  mov     rax, cs:__security_cookie
0x1800857ea  xor     rax, rsp
0x1800857ed  mov     [rsp+648h+var_48], rax
0x1800857f5  mov     rdi, r9
0x1800857f8  mov     [rsp+648h+var_5B0], r9
0x180085800  mov     r15, r8
0x180085803  mov     [rsp+648h+lpString2], r8
0x18008580b  mov     [rsp+648h+var_548], rdx
0x180085813  mov     r14, rdx
0x180085816  mov     [rsp+648h+var_558], rdx
0x18008581e  mov     rcx, [rsp+648h+arg_58]
0x180085826  mov     [rsp+648h+var_5D0], r9
0x18008582b  mov     [rsp+648h+var_5B8], rdx
0x180085833  mov     [rsp+648h+var_508], rdx
0x18008583b  mov     [rsp+648h+var_5C8], r8
0x180085843  mov     [rsp+648h+lpFileTime1], r9
0x18008584b  mov     [rsp+648h+var_540], r9
0x180085853  mov     rax, [rsp+648h+arg_28]
0x18008585b  mov     [rsp+648h+var_5C0], rax
0x180085863  mov     rax, [rsp+648h+arg_38]
0x18008586b  mov     [rsp+648h+var_5A8], rax
0x180085873  mov     [rsp+648h+var_568], rax
0x18008587b  mov     rax, [rsp+648h+arg_40]
0x180085883  mov     [rsp+648h+var_580], rax
0x18008588b  mov     rax, [rsp+648h+arg_48]
0x180085893  mov     [rsp+648h+var_5A0], rax
0x18008589b  mov     rax, [rsp+648h+arg_50]
0x1800858a3  mov     [rsp+648h+var_578], rax
0x1800858ab  mov     [rsp+648h+var_598], rcx
0x1800858b3  mov     rax, [rsp+648h+arg_60]
0x1800858bb  mov     [rsp+648h+var_5E8], rax
0x1800858c0  mov     rax, [rsp+648h+arg_68]
0x1800858c8  mov     [rsp+648h+var_550], rax
0x1800858d0  lea     r12, WPP_GLOBAL_Control
0x1800858d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800858de  cmp     rcx, r12
0x1800858e1  jz      short loc_1800858FE
0x1800858e3  test    byte ptr [rcx+1Ch], 4
0x1800858e7  jz      short loc_1800858FE
0x1800858e9  mov     edx, 63h ; 'c'
0x1800858ee  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x1800858f5  mov     rcx, [rcx+10h]
0x1800858f9  call    WPP_SF_
0x1800858fe  xor     edx, edx; Val
0x180085900  mov     r8d, 10Eh; Size
0x180085906  lea     rcx, [rsp+648h+var_1A8]; void *
0x18008590e  call    memset
0x180085913  xorps   xmm0, xmm0
0x180085916  movups  xmmword ptr [rsp+648h+var_4D8], xmm0
0x18008591e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180085926  movdqu  [rsp+648h+var_4C8], xmm1
0x18008592f  xor     esi, esi
0x180085931  mov     word ptr [rsp+648h+var_4D8], si
0x180085939  xor     r13b, r13b
0x18008593c  mov     qword ptr [rsp+648h+var_5D8], rsi
0x180085941  lea     rdx, [rsp+648h+var_5D8]; wchar_t *
0x180085946  lea     rcx, aMpdlpDebuggetf
0x18008594d  call    ?DlpGetMiscStringValue@DlpUtils@RealtimeProtection@@YAJPEB_WPEAPEA_W@Z
0x180085952  mov     rbx, qword ptr [rsp+648h+var_5D8]
0x180085957  test    eax, eax
0x180085959  js      loc_180085B08
0x18008595f  test    rbx, rbx
0x180085962  jz      loc_180085B08
0x180085968  mov     rdx, rbx
0x18008596b  lea     rcx, [rsp+648h+var_458]
0x180085973  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z
0x180085978  nop
0x180085979  mov     rdx, [rsp+648h+var_5B8]
0x180085981  lea     rcx, [rsp+648h+var_478]
0x180085989  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z
0x18008598e  mov     r9, qword ptr [rsp+648h+var_448]
0x180085996  lea     r8, [rsp+648h+var_458]
0x18008599e  cmp     qword ptr [rsp+648h+var_448+8], 7
0x1800859a7  cmova   r8, qword ptr [rsp+648h+var_458]
0x1800859b0  lea     r15, [rsp+648h+var_478]
0x1800859b8  mov     rax, [rsp+648h+var_460]
0x1800859c0  cmp     rax, 7
0x1800859c4  cmova   r15, [rsp+648h+var_478]
0x1800859cd  cmp     r9, [rsp+648h+var_468]
0x1800859d5  ja      short loc_180085A1A
0x1800859d7  lfence
0x1800859da  cmp     qword ptr [rsp+648h+var_448], rsi
0x1800859e2  jz      short loc_180085A0C
0x1800859e4  mov     rax, [rsp+648h+var_468]
0x1800859ec  lea     rdi, [r15+rax*2]
0x1800859f0  mov     rdx, rdi
0x1800859f3  mov     rcx, r15
0x1800859f6  call    __std_search_2
0x1800859fb  cmp     rax, rdi
0x1800859fe  jz      short loc_180085A12
0x180085a00  sub     rax, r15
0x180085a03  sar     rax, 1
0x180085a06  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180085a0a  jz      short loc_180085A12
0x180085a0c  call    cs:__imp_DebugBreak
0x180085a12  mov     rax, [rsp+648h+var_460]
0x180085a1a  cmp     rax, 7
0x180085a1e  jbe     short loc_180085A5A
0x180085a20  lea     rdx, ds:2[rax*2]
0x180085a28  mov     rcx, [rsp+648h+var_478]
0x180085a30  mov     rax, rcx
0x180085a33  cmp     rdx, 1000h
0x180085a3a  jb      short loc_180085A55
0x180085a3c  add     rdx, 27h ; '''; struct std::nothrow_t *
0x180085a40  mov     rcx, [rcx-8]; void *
0x180085a44  sub     rax, rcx
0x180085a47  sub     rax, 8
0x180085a4b  cmp     rax, 1Fh
0x180085a4f  ja      loc_180087287
0x180085a55  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180085a5a  mov     [rsp+648h+var_468], rsi
0x180085a62  mov     [rsp+648h+var_460], 7
0x180085a6e  mov     word ptr [rsp+648h+var_478], si
0x180085a76  mov     rdx, qword ptr [rsp+648h+var_448+8]
0x180085a7e  cmp     rdx, 7
0x180085a82  jbe     short loc_180085ABF
0x180085a84  lea     rdx, ds:2[rdx*2]
0x180085a8c  mov     rcx, qword ptr [rsp+648h+var_458]
0x180085a94  mov     rax, rcx
0x180085a97  cmp     rdx, 1000h
0x180085a9e  jb      short loc_180085AB9
0x180085aa0  add     rdx, 27h ; '''; struct std::nothrow_t *
0x180085aa4  mov     rcx, [rcx-8]; void *
0x180085aa8  sub     rax, rcx
0x180085aab  sub     rax, 8
0x180085aaf  cmp     rax, 1Fh
0x180085ab3  ja      loc_18008729C
0x180085ab9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180085abe  nop
0x180085abf  mov     rdi, [rsp+648h+var_5B0]
0x180085ac7  mov     r15, [rsp+648h+lpString2]
0x180085acf  jmp     short loc_180085B08
0x180085ad1  mov     r15, [rsp+648h+var_5C8]
0x180085ad9  mov     r14, [rsp+648h+var_558]
0x180085ae1  xor     esi, esi
0x180085ae3  mov     [rsp+648h+lpString2], r15
0x180085aeb  mov     rdi, [rsp+648h+var_5D0]
0x180085af0  mov     [rsp+648h+var_548], r14
0x180085af8  mov     rbx, qword ptr [rsp+648h+var_5D8]
0x180085afd  movzx   r13d, sil
0x180085b01  lea     r12, WPP_GLOBAL_Control
0x180085b08  test    rbx, rbx
0x180085b0b  jz      short loc_180085B16
0x180085b0d  mov     rcx, rbx
0x180085b10  call    cs:__imp_MpFreeMemory
0x180085b16  mov     ecx, 0A6h
0x180085b1b  call    ?GetValue@FeatureControl@Dlp@@YAIW4FeatureControlEnum@@@Z
0x180085b20  mov     rbx, [rsp+648h+lpFileTime1]
0x180085b28  test    eax, eax
0x180085b2a  jz      loc_180085BC7
0x180085b30  lea     rdx, [rsp+648h+var_4D8]
0x180085b38  mov     rcx, rbx
0x180085b3b  call    ?GetAppNameFromAppDelegationCache@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z
0x180085b40  test    eax, eax
0x180085b42  js      short loc_180085B98
0x180085b44  mov     r13b, 1
0x180085b47  mov     rcx, cs:WPP_GLOBAL_Control
0x180085b4e  cmp     rcx, r12
0x180085b51  jz      short loc_180085BC7
0x180085b53  test    byte ptr [rcx+1Ch], 4
0x180085b57  jz      short loc_180085BC7
0x180085b59  lea     rax, [rsp+648h+var_4D8]
0x180085b61  cmp     qword ptr [rsp+648h+var_4C8+8], 7
0x180085b6a  cmova   rax, [rsp+648h+var_4D8]
0x180085b73  mov     edx, 64h ; 'd'
0x180085b78  mov     [rsp+648h+var_620], rax; __int64
0x180085b7d  mov     qword ptr [rsp+648h+bIgnoreCase], r15; __int64
0x180085b82  mov     r9d, [rbx+8]
0x180085b86  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180085b8d  mov     rcx, [rcx+10h]; LoggerHandle
0x180085b91  call    WPP_SF_dSS
0x180085b96  jmp     short loc_180085BC7
0x180085b98  mov     rcx, cs:WPP_GLOBAL_Control
0x180085b9f  cmp     rcx, r12
0x180085ba2  jz      short loc_180085BC7
0x180085ba4  test    byte ptr [rcx+1Ch], 1
0x180085ba8  jz      short loc_180085BC7
0x180085baa  mov     edx, 65h ; 'e'
0x180085baf  mov     [rsp+648h+bIgnoreCase], eax
0x180085bb3  mov     r9d, [rbx+8]
0x180085bb7  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180085bbe  mov     rcx, [rcx+10h]
0x180085bc2  call    WPP_SF_Dd
0x180085bc7  mov     rax, [rsp+648h+var_580]
0x180085bcf  test    rax, rax
0x180085bd2  jz      short loc_180085BD7
0x180085bd4  mov     byte ptr [rax], 0
0x180085bd7  xorps   xmm0, xmm0
0x180085bda  movups  [rsp+648h+var_458], xmm0
0x180085be2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180085bea  movdqa  [rsp+648h+var_448], xmm1
0x180085bf3  mov     word ptr [rsp+648h+var_458], si
0x180085bfb  movups  [rsp+648h+var_438], xmm0
0x180085c03  movdqa  [rsp+648h+var_428], xmm1
0x180085c0c  mov     word ptr [rsp+648h+var_438], si
0x180085c14  lea     rdx, [rsp+648h+var_458]
0x180085c1c  mov     rcx, [rsp+648h+var_598]
0x180085c24  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z
0x180085c29  mov     rax, [rsp+648h+var_598]
0x180085c31  add     rax, 20h ; ' '
0x180085c35  mov     [rsp+648h+var_558], rax
0x180085c3d  lea     rdx, [rsp+648h+var_438]
0x180085c45  mov     rcx, rax
0x180085c48  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z
0x180085c4d  lea     rcx, [rsp+648h+var_458]; this
0x180085c55  call    ??1DlpThrottleUnallowedAppsEvent@DlpThrottle@RealtimeProtection@@QEAA@XZ
0x180085c5a  mov     rax, [rsp+648h+var_5E8]
0x180085c5f  mov     [rax], si
0x180085c62  lea     rcx, [rax+92h]; this
0x180085c69  mov     [rsp+648h+var_5D0], rcx
0x180085c6e  mov     [rcx], si
0x180085c71  add     rax, 194h
0x180085c77  mov     qword ptr [rsp+648h+var_5D8], rax
0x180085c7c  mov     [rax], si
0x180085c7f  cmp     cs:byte_180313780, 0
0x180085c86  jz      loc_180085E21
0x180085c8c  test    r13b, r13b
0x180085c8f  jz      short loc_180085CAB
0x180085c91  lea     r15, [rsp+648h+var_4D8]
0x180085c99  cmp     qword ptr [rsp+648h+var_4C8+8], 7
0x180085ca2  cmova   r15, [rsp+648h+var_4D8]
0x180085cab  lea     rax, [rsp+648h+var_1A8]
0x180085cb3  mov     [rsp+648h+var_618], rax; struct DlpTraceInfo *
0x180085cb8  mov     r10, [rsp+648h+var_578]
0x180085cc0  mov     [rsp+648h+var_620], r10; struct DlpAction *
0x180085cc5  mov     r14, [rsp+648h+var_5A0]
0x180085ccd  mov     qword ptr [rsp+648h+bIgnoreCase], r14; unsigned int *
0x180085cd2  mov     r9, [rsp+648h+var_580]; unsigned __int8 *
0x180085cda  mov     r8, r15; wchar_t *
0x180085cdd  mov     rdi, [rsp+648h+var_5B8]
0x180085ce5  mov     rdx, rdi; wchar_t *
0x180085ce8  call    ?GetFileApplicationAccess@TestDlpPolicyCache@RealtimeProtection@@QEAAJPEB_W0PEAEPEAKPEAUDlpAction@@PEAUDlpTraceInfo@@@Z
0x180085ced  mov     ebx, eax
0x180085cef  mov     rcx, cs:WPP_GLOBAL_Control
0x180085cf6  cmp     rcx, r12
0x180085cf9  jz      short loc_180085D54
0x180085cfb  test    byte ptr [rcx+1Ch], 4
0x180085cff  jz      short loc_180085D29
0x180085d01  mov     edx, 30h ; '0'
0x180085d06  mov     dword ptr [rsp+648h+var_620], eax; char
0x180085d0a  mov     qword ptr [rsp+648h+bIgnoreCase], r15; __int64
0x180085d0f  mov     r9, rdi
0x180085d12  lea     r8, WPP_27da8331ef6f30a08ac47a47043e3cc2_Traceguids
0x180085d19  mov     rcx, [rcx+10h]; LoggerHandle
0x180085d1d  call    WPP_SF_SSD
0x180085d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180085d29  cmp     rcx, r12
0x180085d2c  jz      short loc_180085D54
0x180085d2e  test    byte ptr [rcx+1Ch], 4
0x180085d32  jz      short loc_180085D54
0x180085d34  mov     edx, 66h ; 'f'
0x180085d39  mov     eax, [r14]
0x180085d3c  mov     [rsp+648h+bIgnoreCase], eax
0x180085d40  mov     r9d, ebx
0x180085d43  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180085d4a  mov     rcx, [rcx+10h]
0x180085d4e  call    WPP_SF_Dd
0x180085d53  nop
0x180085d54  lea     rdx, [rsp+648h+var_12E]; Src
0x180085d5c  mov     rcx, [rsp+648h+var_558]; void *
0x180085d64  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z
0x180085d69  lea     rdx, [rsp+648h+var_1A8]; Src
0x180085d71  mov     rcx, [rsp+648h+var_598]; void *
0x180085d79  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z
0x180085d7e  nop
0x180085d7f  jmp     short loc_180085D91
0x180085d81  lea     r12, WPP_GLOBAL_Control
0x180085d88  xor     esi, esi
0x180085d8a  mov     ebx, dword ptr [rsp+648h+var_5C8]
0x180085d91  test    ebx, ebx
0x180085d93  jns     short loc_180085DD2
0x180085d95  jmp     short loc_180085DA7
0x180085d97  lea     r12, WPP_GLOBAL_Control
0x180085d9e  xor     esi, esi
0x180085da0  mov     ebx, dword ptr [rsp+648h+var_5C8]
0x180085da7  mov     rcx, cs:WPP_GLOBAL_Control
0x180085dae  cmp     rcx, r12
0x180085db1  jz      short loc_180085DD2
0x180085db3  test    byte ptr [rcx+1Ch], 1
0x180085db7  jz      short loc_180085DD2
0x180085db9  mov     edx, 67h ; 'g'
0x180085dbe  mov     r9d, ebx
0x180085dc1  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180085dc8  mov     rcx, [rcx+10h]
0x180085dcc  call    WPP_SF_d
0x180085dd1  nop
0x180085dd2  mov     rdx, qword ptr [rsp+648h+var_4C8+8]
0x180085dda  cmp     rdx, 7
0x180085dde  jbe     short loc_180085E1A
0x180085de0  lea     rdx, ds:2[rdx*2]
0x180085de8  mov     rcx, [rsp+648h+var_4D8]
0x180085df0  mov     rax, rcx
  ... truncated ...
```
