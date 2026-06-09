# RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl(wchar_t const *,PPID const &,ulong,ulong,void *,wchar_t const *,ulong,ulong *,DlpAction *,wchar_t * *,wchar_t * *)

- ea: `0x1801888c8`
- end: `0x18018baba`
- name: `?CheckAccessForBufferImpl@CRtpDlpEngine@RealtimeProtection@@QEAAJPEB_WAEBUPPID@@KKPEAX0KPEAKPEAUDlpAction@@PEAPEA_W5@Z`
- size: `12786`
- prototype: `__int64 __fastcall(RealtimeProtection::CRtpDlpEngine *__hidden this, const wchar_t *, const struct PPID *, unsigned int, wchar_t *, void *, const wchar_t *, char, unsigned int *, struct DlpAction *, wchar_t **, wchar_t **)`
- caller_count: `2`
- callee_count: `75`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b43fc`
- `0x180161ed0`

## callees

- `0x180005c28`
- `0x1800099b0`
- `0x18001a444`
- `0x1800249f0`
- `0x180026c70`
- `0x180028d80`
- `0x180029590`
- `0x18002ec38`
- `0x180034420`
- `0x1800374f8`
- `0x180038450`
- `0x1800385a0`
- `0x1800398a0`
- `0x180046d10`
- `0x180049b34`
- `0x18004b3bc`
- `0x180050300`
- `0x1800542d0`
- `0x180057b84`
- `0x18005c704`
- `0x18005c748`
- `0x18006af4c`
- `0x18006b998`
- `0x180079594`
- `0x180079dc0`
- `0x18007aebc`
- `0x1800809d0`
- `0x1800810e0`
- `0x1800839a0`
- `0x180083b10`
- `0x1800878ec`
- `0x180089510`
- `0x18008acf0`
- `0x180091450`
- `0x18009351c`
- `0x180095410`
- `0x18009be50`
- `0x18009f730`
- `0x1800a4c30`
- `0x1800a9cd4`
- `0x1800ac9e8`
- `0x1800adb0c`
- `0x1800ae95c`
- `0x1800afa84`
- `0x1800b3710`
- `0x1800b3c58`
- `0x1800b6228`
- `0x1800b6894`
- `0x1800b8fcc`
- `0x180104f64`

## import_xrefs

- `KERNEL32!Sleep` at `0x180188fbb`
- `KERNEL32!Sleep` at `0x180188fbb`
- `KERNEL32!DeleteFileW` at `0x18018b6b1`
- `KERNEL32!DeleteFileW` at `0x18018b6b1`
- `KERNEL32!GetTickCount64` at `0x180188aaf`
- `KERNEL32!GetTickCount64` at `0x180188abd`
- `KERNEL32!GetTickCount64` at `0x180188acb`
- `KERNEL32!GetTickCount64` at `0x180188bd1`
- `KERNEL32!GetTickCount64` at `0x180189726`
- `KERNEL32!GetTickCount64` at `0x18018ad66`
- `KERNEL32!GetTickCount64` at `0x18018b6f4`
- `KERNEL32!GetTickCount64` at `0x180188aaf`
- `KERNEL32!GetTickCount64` at `0x180188abd`
- `KERNEL32!GetTickCount64` at `0x180188acb`
- `KERNEL32!GetTickCount64` at `0x180188bd1`
- `KERNEL32!GetTickCount64` at `0x180189726`
- `KERNEL32!GetTickCount64` at `0x18018ad66`
- `KERNEL32!GetTickCount64` at `0x18018b6f4`
- `KERNEL32!DebugBreak` at `0x180188d94`
- `KERNEL32!DebugBreak` at `0x180188d94`

## string_xrefs

- `0x180188b9a`: `RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl`
- `0x180188bfb`: `RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl`
- `0x180188d5f`: `RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl`
- `0x180188ff4`: `RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl`
- `0x180189887`: `RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl`
- `0x18018a60c`: `RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl`
- `0x18018ad53`: `RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl`
- `0x18018b2fc`: `RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl`
- `0x18018b6be`: `RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl`
- `0x18018b6e1`: `RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl`
- `0x180188bb1`: `[DlpPasteToBrowser] %hs Cache hit: %ls`
- `0x180188bc5`: `%hs: Created the PTB stub file: %ls`
- `0x180188d84`: `MpDlp_DebugCheckAccessForBufferImpl`
- `0x18018b6c5`: `%hs: Deleted the PTB stub file due to ShouldReclassify the file: %ls`
- `0x18018b6e8`: `%hs: Failed to delete the PTB stub file: %ls, hr = %lx`

## pseudocode

```c
// Hidden C++ exception states: #wind=39 #try_helpers=3
__int64 __fastcall RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl(
        RealtimeProtection::CRtpDlpEngine *this,
        wchar_t *a2,
        wchar_t *a3,
        unsigned int a4,
        wchar_t *a5,
        void *a6,
        const wchar_t *a7,
        unsigned int a8,
        unsigned int *a9,
        struct DlpAction *a10,
        wchar_t **a11,
        wchar_t **a12)
{
  const wchar_t *v13; // r11
  PVOID *v14; // r10
  int v15; // eax
  const wchar_t *v16; // rax
  void *v17; // rdi
  const void *v18; // r9
  RealtimeProtection::CRtpDlpEngine *v19; // rsi
  int v20; // eax
  const struct std::nothrow_t *v21; // rdx
  unsigned int v22; // ebx
  WCHAR *v24; // rbx
  const struct std::nothrow_t *v25; // rdx
  int v26; // eax
  void **v27; // r9
  wchar_t *v28; // rsi
  int ClassificationUserSid; // eax
  const struct std::nothrow_t *v30; // rdx
  unsigned int v31; // edi
  __int64 v32; // rax
  int SyncClassificationEvent; // eax
  int FileApplicationAccess; // esi
  __int64 v35; // rax
  const struct std::nothrow_t *v36; // rdx
  __int64 v37; // rax
  enum _DLP_JIT_POLICY_TYPE *v38; // rdx
  int JitDefaultFallbackPolicy; // eax
  const wchar_t *v40; // rdx
  unsigned int v41; // r8d
  int v42; // ecx
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  int v46; // eax
  int v47; // esi
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  wchar_t *i; // rax
  __int64 v52; // rax
  _DWORD *v53; // rsi
  int v54; // eax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rcx
  int v58; // r8d
  bool v59; // zf
  char v60; // al
  unsigned int v61; // r8d
  PVOID *v62; // rcx
  __int64 v63; // rdx
  const wchar_t *v64; // rax
  __int64 v65; // rax
  char IsJitCandidateOrFallBackPolicy; // dl
  bool *v67; // r8
  unsigned int v68; // r12d
  __int64 v69; // rax
  __int64 v70; // rdx
  char v71; // r14
  _OWORD *v72; // rax
  wchar_t *v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 LastFailure; // r14
  struct DlpTraceInfoEx *v77; // rdx
  PVOID *v78; // rsi
  __int64 v79; // rax
  __int64 v80; // r8
  __int64 v81; // rax
  const struct std::nothrow_t *v82; // rdx
  const struct std::nothrow_t *v83; // rdx
  void *v84; // rcx
  char v85; // si
  int v86; // eax
  unsigned int v87; // eax
  unsigned int v88; // ecx
  wchar_t *v89; // r9
  const struct std::nothrow_t *v90; // rdx
  wchar_t *v91; // rdx
  int v92; // r12d
  void *v93; // rsi
  _QWORD *v94; // r14
  const struct std::nothrow_t *v95; // rdx
  int v96; // esi
  const struct std::nothrow_t *v97; // rdx
  void *v98; // rax
  int v99; // r12d
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rax
  __int64 v103; // r8
  __int64 v104; // rdx
  __int64 v105; // r14
  __int64 v106; // r8
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rdx
  const wchar_t *v110; // r8
  const struct std::nothrow_t *v111; // rdx
  int v112; // r14d
  const struct std::nothrow_t *v113; // rdx
  const struct std::nothrow_t *v114; // rdx
  const struct std::nothrow_t *v115; // rdx
  __int64 v116; // r12
  __int64 v117; // r15
  char v118; // r14
  __int64 v119; // rax
  __int64 v120; // rcx
  int v121; // eax
  unsigned int v122; // eax
  unsigned int v123; // ecx
  unsigned int v124; // esi
  int v125; // eax
  unsigned int v126; // esi
  const struct std::nothrow_t *v127; // rdx
  int v128; // eax
  const struct std::nothrow_t *v129; // rdx
  unsigned int v130; // esi
  const struct std::nothrow_t *v131; // rdx
  void *v132; // rsi
  __int64 v133; // r8
  __int64 v134; // rax
  __int64 v135; // rdx
  __int64 v136; // r8
  __int64 v137; // rdx
  const wchar_t *v138; // rax
  int v139; // eax
  const struct std::nothrow_t *v140; // rdx
  unsigned int v141; // r14d
  const struct std::nothrow_t *v142; // rdx
  __int64 v143; // r14
  int v144; // eax
  const struct std::nothrow_t *v145; // rdx
  BOOL v146; // r14d
  RealtimeProtection::CRtpDlpEngine *v147; // r10
  unsigned int v148; // eax
  char v149; // cl
  int v150; // eax
  unsigned int v151; // esi
  const wchar_t *v152; // r8
  int v153; // eax
  unsigned int v154; // eax
  unsigned int v155; // ecx
  int FallbackPolicyInfo; // eax
  _QWORD *v157; // rsi
  int v158; // eax
  const struct std::nothrow_t *v159; // rdx
  const struct std::nothrow_t *v160; // rdx
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // rax
  __int64 v164; // r8
  __int64 v165; // rdx
  const wchar_t *v166; // rax
  int v167; // eax
  const struct std::nothrow_t *v168; // rdx
  const struct std::nothrow_t *v169; // rdx
  unsigned int v170; // r12d
  const wchar_t *v171; // rax
  __int64 v172; // rax
  __int64 v173; // rcx
  __int64 v174; // rax
  __int64 v175; // rcx
  wchar_t *v176; // rcx
  __int64 v177; // r8
  char v178; // dl
  int v179; // r10d
  wchar_t *v180; // [rsp+20h] [rbp-1148h]
  wchar_t *v181; // [rsp+20h] [rbp-1148h]
  wchar_t **v182; // [rsp+28h] [rbp-1140h]
  wchar_t **v183; // [rsp+28h] [rbp-1140h]
  wchar_t **v184; // [rsp+30h] [rbp-1138h]
  wchar_t **v185; // [rsp+30h] [rbp-1138h]
  wchar_t **v186; // [rsp+30h] [rbp-1138h]
  bool v187; // [rsp+38h] [rbp-1130h]
  bool v188[8]; // [rsp+38h] [rbp-1130h]
  unsigned int v189; // [rsp+40h] [rbp-1128h]
  wchar_t v190; // [rsp+D0h] [rbp-1098h] BYREF
  char ShouldReclassifyFile; // [rsp+D2h] [rbp-1096h]
  _BYTE v192[13]; // [rsp+D3h] [rbp-1095h] BYREF
  unsigned int v193; // [rsp+E0h] [rbp-1088h] BYREF
  unsigned __int8 v194; // [rsp+E4h] [rbp-1084h]
  int v195; // [rsp+E8h] [rbp-1080h]
  unsigned int v196; // [rsp+ECh] [rbp-107Ch]
  unsigned int v197; // [rsp+F0h] [rbp-1078h]
  unsigned int v198; // [rsp+F4h] [rbp-1074h]
  int v199; // [rsp+F8h] [rbp-1070h] BYREF
  unsigned int v200; // [rsp+FCh] [rbp-106Ch] BYREF
  __int64 v201; // [rsp+100h] [rbp-1068h] BYREF
  RealtimeProtection::CRtpDlpEngine *v202; // [rsp+108h] [rbp-1060h]
  __int64 v203; // [rsp+110h] [rbp-1058h]
  wchar_t *v204; // [rsp+118h] [rbp-1050h]
  __int64 v205; // [rsp+120h] [rbp-1048h] BYREF
  __int64 v206; // [rsp+128h] [rbp-1040h] BYREF
  wchar_t *v207; // [rsp+130h] [rbp-1038h]
  _BYTE v208[32]; // [rsp+138h] [rbp-1030h] BYREF
  char v209; // [rsp+158h] [rbp-1010h]
  wchar_t **v210; // [rsp+160h] [rbp-1008h]
  LPCWSTR lpFileName; // [rsp+168h] [rbp-1000h] BYREF
  __int64 v212; // [rsp+170h] [rbp-FF8h] BYREF
  int v213; // [rsp+178h] [rbp-FF0h] BYREF
  int v214; // [rsp+17Ch] [rbp-FECh] BYREF
  void *v215; // [rsp+180h] [rbp-FE8h] BYREF
  void *v216; // [rsp+188h] [rbp-FE0h]
  _QWORD v217[2]; // [rsp+190h] [rbp-FD8h] BYREF
  wchar_t **v218; // [rsp+1A0h] [rbp-FC8h]
  unsigned int *v219; // [rsp+1A8h] [rbp-FC0h]
  wchar_t *v220; // [rsp+1B0h] [rbp-FB8h]
  __int64 v221; // [rsp+1B8h] [rbp-FB0h] BYREF
  __int64 v222; // [rsp+1C0h] [rbp-FA8h] BYREF
  __int64 v223; // [rsp+1C8h] [rbp-FA0h] BYREF
  __int64 v224; // [rsp+1D0h] [rbp-F98h] BYREF
  __int64 v225; // [rsp+1D8h] [rbp-F90h] BYREF
  __int64 v226; // [rsp+1E0h] [rbp-F88h] BYREF
  __int64 v227; // [rsp+1E8h] [rbp-F80h] BYREF
  __int64 TickCount64; // [rsp+1F0h] [rbp-F78h] BYREF
  __int64 v229; // [rsp+1F8h] [rbp-F70h] BYREF
  _OWORD *v230; // [rsp+200h] [rbp-F68h] BYREF
  _QWORD v231[4]; // [rsp+208h] [rbp-F60h] BYREF
  _QWORD v232[7]; // [rsp+228h] [rbp-F40h] BYREF
  unsigned __int8 v233; // [rsp+260h] [rbp-F08h] BYREF
  char v234; // [rsp+261h] [rbp-F07h] BYREF
  char v235; // [rsp+262h] [rbp-F06h] BYREF
  void *v236; // [rsp+268h] [rbp-F00h] BYREF
  char v237[8]; // [rsp+270h] [rbp-EF8h] BYREF
  wchar_t *v238[2]; // [rsp+278h] [rbp-EF0h] BYREF
  __m128i si128; // [rsp+288h] [rbp-EE0h]
  void *v240; // [rsp+298h] [rbp-ED0h] BYREF
  _BYTE v241[32]; // [rsp+2A0h] [rbp-EC8h] BYREF
  _OWORD v242[2]; // [rsp+2C0h] [rbp-EA8h] BYREF
  std::_Ref_count_base *v243[2]; // [rsp+2E0h] [rbp-E88h] BYREF
  char v244; // [rsp+2F0h] [rbp-E78h]
  __int64 v245; // [rsp+2F8h] [rbp-E70h]
  std::_Ref_count_base *v246; // [rsp+300h] [rbp-E68h]
  char v247; // [rsp+308h] [rbp-E60h]
  int v248; // [rsp+310h] [rbp-E58h]
  __int64 v249; // [rsp+318h] [rbp-E50h]
  char v250; // [rsp+320h] [rbp-E48h]
  _BYTE v251[40]; // [rsp+330h] [rbp-E38h] BYREF
  _BYTE v252[32]; // [rsp+358h] [rbp-E10h] BYREF
  _BYTE v253[40]; // [rsp+378h] [rbp-DF0h] BYREF
  _OWORD v254[4]; // [rsp+3A0h] [rbp-DC8h] BYREF
  _QWORD v255[4]; // [rsp+3E0h] [rbp-D88h] BYREF
  wchar_t v256[136]; // [rsp+400h] [rbp-D68h] BYREF
  wchar_t v257[136]; // [rsp+510h] [rbp-C58h] BYREF
  _BYTE v258[616]; // [rsp+620h] [rbp-B48h] BYREF
  char v259; // [rsp+888h] [rbp-8E0h]
  wchar_t v260[464]; // [rsp+890h] [rbp-8D8h] BYREF
  _BYTE v261[1184]; // [rsp+C30h] [rbp-538h] BYREF
  char Src[80]; // [rsp+10D0h] [rbp-98h] BYREF

  v196 = a4;
  v204 = a3;
  v220 = a2;
  v202 = this;
  v221 = (__int64)a2;
  v13 = a7;
  v203 = (__int64)a7;
  v222 = (__int64)this;
  v207 = a2;
  v229 = (__int64)a2;
  v223 = (__int64)a3;
  LODWORD(v206) = a4;
  v224 = (__int64)a7;
  v219 = a9;
  v226 = (__int64)a9;
  v216 = a10;
  v218 = a11;
  v210 = a12;
  v227 = (__int64)a12;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      725,
      &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
      a8,
      *((_DWORD *)a3 + 2));
    v14 = (PVOID *)WPP_GLOBAL_Control;
    v13 = (const wchar_t *)v203;
  }
  v195 = a8 & 0x800;
  LODWORD(v205) = v195;
  if ( (a8 & 0x800) != 0 || (v15 = 1, (a8 & 0x200) == 0) )
    v15 = 0;
  v214 = v15;
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 )
  {
    v16 = v13;
    if ( !v13 )
      v16 = &qword_18025C818;
    WPP_SF_sDSDSdd(
      (TRACEHANDLE)v14[2],
      *((_DWORD *)a3 + 2),
      (__int64)v207,
      a8,
      (__int64)v16,
      BYTE1(a8) & 1,
      (a8 & 0x800) != 0);
  }
  TickCount64 = GetTickCount64();
  v225 = GetTickCount64();
  GetTickCount64();
  v236 = *(void **)a3;
  v17 = 0;
  v215 = 0;
  lpFileName = 0;
  *(_QWORD *)&v192[5] = 0;
  LOBYTE(v184) = 1;
  LOBYTE(v18) = a8 & 1;
  v19 = v202;
  v20 = RealtimeProtection::DlpUtils::WriteBufferToCache(
          *((wchar_t **)v202 + 19),
          (const wchar_t *)(unsigned int)a5,
          a6,
          v18,
          (bool)&lpFileName,
          (wchar_t **)&v192[5],
          v184,
          v187);
  v22 = v20;
  if ( v20 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        727,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)v20);
    if ( *(_QWORD *)&v192[5] )
      operator delete(*(void **)&v192[5], v21);
    if ( lpFileName )
      operator delete((void *)lpFileName, v21);
    return v22;
  }
  v24 = (WCHAR *)lpFileName;
  if ( v20 == 1 )
  {
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"[DlpPasteToBrowser] %hs Cache hit: %ls",
      "RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl",
      lpFileName);
    v26 = 1;
  }
  else
  {
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"%hs: Created the PTB stub file: %ls",
      "RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl",
      lpFileName);
    v225 = GetTickCount64();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        728,
        (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)"RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl",
        (__int64)v24);
    v28 = v204;
    ClassificationUserSid = RealtimeProtection::DlpUserSidCache::GetClassificationUserSid(
                              (RealtimeProtection::DlpUserSidCache *)v196,
                              (unsigned int)v204,
                              (const struct PPID *)&v215,
                              v27);
    v31 = ClassificationUserSid;
    if ( ClassificationUserSid < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          729,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)ClassificationUserSid);
      if ( *(_QWORD *)&v192[5] )
        operator delete(*(void **)&v192[5], v30);
      if ( v24 )
        operator delete(v24, v30);
      if ( v215 )
        operator delete(v215);
      return v31;
    }
    v217[0] = v24;
    v32 = -1;
    do
      ++v32;
    while ( v24[v32] );
    v217[1] = v32;
    v17 = v215;
    SyncClassificationEvent = EndpointDlp::Client::GenerateSyncClassificationEvent(
                                (unsigned int)v217,
                                (_DWORD)v215,
                                *((_DWORD *)v28 + 2),
                                (_DWORD)v236,
                                6);
    FileApplicationAccess = SyncClassificationEvent;
    if ( SyncClassificationEvent < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          730,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)SyncClassificationEvent);
LABEL_43:
      if ( *(_QWORD *)&v192[5] )
        operator delete(*(void **)&v192[5], v25);
      if ( v24 )
        operator delete(v24, v25);
      if ( v17 )
        operator delete(v17);
      return (unsigned int)FileApplicationAccess;
    }
    v26 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        731,
        (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)"RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl",
        (__int64)v24);
      v26 = 0;
    }
    v19 = v202;
  }
  v213 = v26;
  if ( (unsigned int)RealtimeProtection::DlpUtils::DlpMpLookupMiscConfigFlag(
                       (RealtimeProtection::DlpUtils *)L"MpDlp_DebugCheckAccessForBufferImpl",
                       (const wchar_t *)v25) )
    DebugBreak();
  BYTE4(v238[1]) = 0;
  v35 = std::wstring::wstring(v208, v24);
  RealtimeProtection::DlpPathCache::GetFilterPath(v251, v35, v238);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v208);
  if ( !v251[32] )
  {
    std::optional<std::wstring>::~optional<std::wstring>(v251);
    if ( *(_QWORD *)&v192[5] )
      operator delete(*(void **)&v192[5], v36);
    if ( v24 )
      operator delete(v24, v36);
    if ( v17 )
      operator delete(v17);
    return 2147942487LL;
  }
  v37 = std::optional<std::wstring>::value(v251);
  std::wstring::wstring(v241, v37);
  v197 = 0;
  v198 = 1000 * *((_DWORD *)v19 + 9) / 0xC8u;
  memset(v256, 0, 0x10Eu);
  memset(v261, 0, 0x498u);
  v194 = 0;
  memset(Src, 0, sizeof(Src));
  LODWORD(v201) = 10;
  *(_WORD *)v192 = 1;
  v200 = 2;
  JitDefaultFallbackPolicy = EndpointDlp::Client::GetJitDefaultFallbackPolicy((EndpointDlp::Client *)&v200, v38);
  v42 = v200;
  if ( JitDefaultFallbackPolicy < 0 )
    v42 = 2;
  if ( !*((_BYTE *)v202 + 76) )
  {
    v200 = 3;
    goto LABEL_70;
  }
  v200 = 3;
  if ( v42 != 3 )
  {
LABEL_70:
    HIBYTE(v190) = 0;
    goto LABEL_71;
  }
  HIBYTE(v190) = 1;
LABEL_71:
  v193 = RealtimeProtection::DlpUtils::DlpMpLookupMiscConfig(
           (RealtimeProtection::DlpUtils *)L"MpDlp_SimulateSensitiveBuffer",
           v40,
           v41);
  v46 = v198;
  if ( v193 == 102 )
    v46 = 5;
  v198 = v46;
  ShouldReclassifyFile = 0;
  v47 = 0;
  v199 = 0;
  HIDWORD(v212) = 1000 * RealtimeProtection::DlpPlugin::GetFcValue(265, v43, v44, v45);
  LODWORD(v212) = RealtimeProtection::DlpPlugin::GetFcValue(264, v48, v49, v50);
  for ( i = v204 + 4; ; i = (wchar_t *)v217[0] )
  {
    v217[0] = i;
    if ( v197 >= v198 )
    {
      v146 = v195 != 0;
      *(_DWORD *)v188 = v194;
      LODWORD(v185) = v192[1];
      LODWORD(v182) = v146;
      LODWORD(v180) = *((_DWORD *)v202 + 10);
      RealtimeProtection::MpLogMessageImpl(
        (RealtimeProtection *)L"%hs:  %ls: policy evaluation timeout. Flags %d, FallbackMode %d, IsEdge %d, EmptyPolicy %d"
                               ", CandidatePolicy %d",
        "RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl",
        v24,
        a8,
        v180,
        v182,
        v185,
        *(_QWORD *)v188);
      v217[0] = GetTickCount64();
      memset(v257, 0, 0x10Eu);
      v147 = v202;
      v148 = *((_DWORD *)v202 + 10);
      if ( v148 && v148 <= 4 )
      {
        if ( v148 >= 2 )
        {
          v149 = HIBYTE(v190);
LABEL_375:
          if ( v148 != 4 )
          {
            if ( v148 == 1 || v148 == 2 && !v149 )
            {
              v150 = 1;
              v200 = 1;
              v151 = 2;
            }
            else
            {
              v150 = 3;
              v151 = 3;
            }
            v193 = v150;
            *(_DWORD *)&Src[76] = v150;
            v154 = *v219;
            v155 = v201;
            if ( *v219 > (unsigned int)v201 )
            {
              *v219 = v201;
              v154 = v155;
            }
            memmove(v216, Src, 8LL * v154);
            FallbackPolicyInfo = EndpointDlp::Client::GetFallbackPolicyInfo(v151, v257);
            LODWORD(LastFailure) = FallbackPolicyInfo;
            v199 = FallbackPolicyInfo;
            if ( FallbackPolicyInfo < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  762,
                  &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                  (unsigned int)FallbackPolicyInfo);
LABEL_213:
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v241);
              std::optional<std::wstring>::~optional<std::wstring>(v251);
              v84 = *(void **)&v192[5];
              if ( *(_QWORD *)&v192[5] )
LABEL_458:
                operator delete(v84, v83);
LABEL_459:
              if ( v24 )
                operator delete(v24, v83);
              if ( v17 )
                operator delete(v17);
              return (unsigned int)LastFailure;
            }
            v157 = v218;
            if ( v218 )
            {
              v236 = 0;
              v158 = CommonUtil::NewSprintfW((CommonUtil *)&v236, (wchar_t **)L"%ls", v257);
              LODWORD(LastFailure) = v158;
              v199 = v158;
              if ( v158 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    763,
                    &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                    (unsigned int)v158);
                if ( v236 )
                  operator delete(v236, v159);
                std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v241);
                std::optional<std::wstring>::~optional<std::wstring>(v251);
                if ( *(_QWORD *)&v192[5] )
                  operator delete(*(void **)&v192[5], v160);
                if ( v24 )
                  operator delete(v24, v160);
                if ( v17 )
                  operator delete(v17);
                return (unsigned int)LastFailure;
              }
              *v157 = v236;
            }
            std::wstring::wstring(v253, &v257[61]);
            v93 = *(void **)&v192[5];
            if ( v195 )
            {
              v161 = std::wstring::wstring(v238, *(_QWORD *)&v192[5]);
              v162 = std::operator+<wchar_t>(v252, L"#", v161);
              v163 = std::operator+<wchar_t>(v208, v162, L".txt");
              std::wstring::append(v253, v163);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v208);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v252);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v238);
              v164 = std::to_wstring(v252, 0);
              v165 = std::operator+<wchar_t>(v208, L"#", v164);
              std::wstring::append(v253, v165);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v208);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v252);
            }
            if ( v210 )
            {
              v236 = 0;
              v166 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v253);
              v167 = CommonUtil::NewSprintfW((CommonUtil *)&v236, (wchar_t **)L"%ls", v166);
              LODWORD(LastFailure) = v167;
              v199 = v167;
              if ( v167 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    764,
                    &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                    (unsigned int)v167);
                if ( v236 )
                  operator delete(v236, v168);
                std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v253);
                std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v241);
                std::optional<std::wstring>::~optional<std::wstring>(v251);
                if ( v93 )
                  operator delete(v93, v169);
                if ( v24 )
                  operator delete(v24, v169);
                if ( v17 )
                  operator delete(v17);
                return (unsigned int)LastFailure;
              }
              *v210 = (wchar_t *)v236;
            }
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v253);
            v170 = v200;
            v171 = &qword_18025C818;
            if ( v210 )
              v171 = *v210;
            LODWORD(v186) = LastFailure;
            LODWORD(v181) = *v219;
            RealtimeProtection::MpLogMessageImpl(
              (RealtimeProtection *)L"%hs: TimeOut and fallback audit mode. File %ls, Enforcement %d, numActions %d, RuleI"
                                     "dInfo %ls, hr=0x%x",
              "RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl",
              v24,
              v200,
              v181,
              v171,
              v186);
            if ( !v195 )
            {
              *(_OWORD *)v238 = 0;
              si128.m128i_i64[0] = 0;
              v209 = 0;
              v172 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v241);
              RealtimeProtection::DlpEngineTelemetry::GenerateDlpTelemetryEvent(
                (unsigned int)v238,
                (unsigned int)&v257[61],
                (unsigned int)v257,
                v170,
                9,
                *((_DWORD *)v202 + 22),
                v172,
                v203,
                (__int64)v207,
                (__int64)v204,
                v196,
                0,
                (__int64)&qword_18025C818,
                0,
                0,
                0,
                (__int64)v208,
                0,
                (__int64)&qword_18025C818,
                (__int64)&qword_18025C818,
                0,
                (__int64)&qword_18025C818,
                0,
                (__int64)&qword_18025C818,
                (__int64)&qword_18025C818,
                0);
              if ( v209 )
                std::string::`scalar deleting destructor'(v208);
              RealtimeProtection::CRtpDlpEngine::SendDlpTelemetryEvent(v173, v238);
              std::vector<RealtimeProtection::DlpEngineTelemetry::DlpTelemetryEvent>::_Tidy(v238);
            }
LABEL_440:
            v176 = v256;
            v91 = v257;
            v177 = 2;
            do
            {
              *(_OWORD *)v176 = *(_OWORD *)v91;
              *((_OWORD *)v176 + 1) = *((_OWORD *)v91 + 1);
              *((_OWORD *)v176 + 2) = *((_OWORD *)v91 + 2);
              *((_OWORD *)v176 + 3) = *((_OWORD *)v91 + 3);
              *((_OWORD *)v176 + 4) = *((_OWORD *)v91 + 4);
              *((_OWORD *)v176 + 5) = *((_OWORD *)v91 + 5);
              *((_OWORD *)v176 + 6) = *((_OWORD *)v91 + 6);
              v176 += 64;
              *((_OWORD *)v176 - 1) = *((_OWORD *)v91 + 7);
              v91 += 64;
              --v177;
            }
            while ( v177 );
            *(_QWORD *)v176 = *(_QWORD *)v91;
            *((_DWORD *)v176 + 2) = *((_DWORD *)v91 + 2);
            v176[6] = v91[6];
            v92 = 1;
            goto LABEL_443;
          }
LABEL_382:
          v152 = (const wchar_t *)v203;
          if ( !v203 )
            v152 = &qword_18025C818;
          LODWORD(v183) = v196;
          RealtimeProtection::DlpPasteCache::AddPendingFile(
            *((wchar_t **)v147 + 19),
            v24,
            v152,
            v207,
            v204,
            (const struct PPID *)v183,
            a8,
            *((_DWORD *)v147 + 11),
            v189);
          v153 = EndpointDlp::Client::GetFallbackPolicyInfo(3, v257);
          FileApplicationAccess = v153;
          if ( v153 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                761,
                &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                (unsigned int)v153);
            goto LABEL_124;
          }
          if ( (a8 & 0x200) == 0 && (!v195 || v192[0]) )
          {
            memset(v254, 0, sizeof(v254));
            *(_QWORD *)&v254[0] = 0x300000107LL;
            DWORD2(v254[0]) = 1;
            *(_OWORD *)v238 = 0;
            si128.m128i_i64[0] = 0;
            v209 = 0;
            v174 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v241);
            RealtimeProtection::DlpEngineTelemetry::GenerateDlpTelemetryEvent(
              (unsigned int)v238,
              (unsigned int)L"6abb5bf8-7ae6-4f97-9c9a-9fcb60c0f230:00573cd5-48f0-4fc1-8ea0-4ee0e749f9b7",
              (unsigned int)v257,
              3,
              9,
              *((_DWORD *)v202 + 22),
              v174,
              v203,
              (__int64)v207,
              (__int64)v204,
              v196,
              0,
              (__int64)&qword_18025C818,
              6,
              (__int64)v254,
              0,
              (__int64)v208,
              0,
              (__int64)&qword_18025C818,
              (__int64)&qword_18025C818,
              0,
              (__int64)&qword_18025C818,
              0,
              (__int64)&qword_18025C818,
              (__int64)&qword_18025C818,
              v146);
            if ( v209 )
              std::string::`scalar deleting destructor'(v208);
            RealtimeProtection::CRtpDlpEngine::SendDlpTelemetryEvent(v175, v238);
            std::vector<RealtimeProtection::DlpEngineTelemetry::DlpTelemetryEvent>::_Tidy(v238);
          }
          LODWORD(LastFailure) = -2147024638;
          v93 = *(void **)&v192[5];
          goto LABEL_440;
        }
      }
      else
      {
        *((_DWORD *)v202 + 10) = 1;
        v148 = 1;
      }
      v149 = HIBYTE(v190);
      if ( HIBYTE(v190) )
        goto LABEL_382;
      goto LABEL_375;
    }
    Sleep(0xC8u);
    if ( (_DWORD)v212 && (v199 = v47 + 200, (unsigned int)(v47 + 200) >= HIDWORD(v212)) )
    {
      v199 = 0;
      RealtimeProtection::MpLogMessageImpl(
        (RealtimeProtection *)L"[DlpPasteToBrowser] %hs: Send the sync classification request again for the file %ls ",
        "RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl",
        v24);
      v232[0] = v24;
      v52 = -1;
      do
        ++v52;
      while ( v24[v52] );
      v232[1] = v52;
      v53 = (_DWORD *)v217[0];
      v54 = EndpointDlp::Client::GenerateSyncClassificationEvent(
              (unsigned int)v232,
              (_DWORD)v17,
              *(_DWORD *)v217[0],
              (_DWORD)v236,
              6);
      if ( v54 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v24, v54);
    }
    else
    {
      v53 = (_DWORD *)v217[0];
    }
    memset(v260, 0, 0x396u);
    LOBYTE(v190) = 0;
    *(_OWORD *)v243 = 0;
    v244 = 1;
    v245 = 0;
    v246 = 0;
    v247 = 1;
    v248 = 0;
    v249 = 0;
    v250 = 1;
    v259 = 0;
    v209 = 0;
    v231[0] = v207;
    v55 = -1;
    do
      ++v55;
    while ( v220[v55] );
    v231[1] = v55;
    v255[0] = v24;
    v56 = -1;
    do
      ++v56;
    while ( v24[v56] );
    v255[1] = v56;
    FileApplicationAccess = EndpointDlp::Client::GetFileApplicationAccess(
                              (unsigned int)v255,
                              (unsigned int)v231,
                              (unsigned int)v208,
                              *v53,
                              (__int64)v236,
                              v196,
                              (__int64)v243,
                              1,
                              (__int64)v258);
    std::optional<std::wstring>::~optional<std::wstring>(v208);
    if ( FileApplicationAccess == -805306316 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 733, v58, (_DWORD)v24, v197, 52);
      v59 = v259 == 0;
      goto LABEL_93;
    }
    if ( FileApplicationAccess == -805306286 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 734, v58, (_DWORD)v24, v197, 82);
      LOBYTE(v190) = 1;
      ShouldReclassifyFile = 0;
      goto LABEL_128;
    }
    if ( FileApplicationAccess )
      break;
    v60 = v259;
    if ( v259 )
      goto LABEL_125;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        735,
        (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (_DWORD)v24,
        v197);
      v60 = v259;
    }
    v59 = v60 == 0;
LABEL_93:
    if ( !v59 )
      EndpointDlp::Client::FileAccessInfo::~FileAccessInfo((EndpointDlp::Client::FileAccessInfo *)v258);
    if ( v247 && v246 )
      std::_Ref_count_base::_Decref(v246);
    if ( v244 && v243[1] )
      std::_Ref_count_base::_Decref(v243[1]);
LABEL_370:
    ++v197;
    v47 = v199;
  }
  if ( FileApplicationAccess < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        736,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)FileApplicationAccess);
    if ( v259 )
      EndpointDlp::Client::FileAccessInfo::~FileAccessInfo((EndpointDlp::Client::FileAccessInfo *)v258);
    if ( v247 && v246 )
      std::_Ref_count_base::_Decref(v246);
    if ( v244 && v243[1] )
      std::_Ref_count_base::_Decref(v243[1]);
    goto LABEL_124;
  }
LABEL_125:
  if ( !ShouldReclassifyFile
    && (unsigned __int8)Dlp::FeatureControl::GetFlag<enum Dlp::FeatureControl::ReclassifyFlags,void,void>(v57, 1) )
  {
    v230 = v242;
    v242[0] = 0;
    std::wstring::wstring(v208, v24);
    ShouldReclassifyFile = EndpointDlp::Client::ShouldReclassifyFile(0, 0, v208, v242);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v208);
  }
LABEL_128:
  EndpointDlp::Interop::MarshalFileAccessInfo(
    (unsigned int)v258,
    (unsigned int)&v192[1],
    (unsigned int)&v201,
    (unsigned int)Src,
    (__int64)v256,
    (__int64)&v230,
    (__int64)v260);
  v61 = v193;
  if ( v193 )
  {
    v62 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 737, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v193);
      v62 = (PVOID *)WPP_GLOBAL_Control;
      v61 = v193;
    }
    wcscpy(v256, L"MpDlp_SimulateSensitiveBuffer_Version");
    if ( v61 - 101 <= 1 )
    {
      if ( v62 != &WPP_GLOBAL_Control && (*((_BYTE *)v62 + 28) & 4) != 0 )
      {
        v63 = 738;
LABEL_160:
        WPP_SF_(v62[2], v63, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
      }
LABEL_161:
      v64 = L"6abb5bf8-7ae6-4f97-9c9a-9fcb60c0f230:00573cd5-48f0-4fc1-8ea0-4ee0e749f9b7";
    }
    else
    {
      if ( v197 <= 1 )
      {
        if ( v62 != &WPP_GLOBAL_Control && (*((_BYTE *)v62 + 28) & 4) != 0 )
        {
          v63 = 739;
          goto LABEL_160;
        }
        goto LABEL_161;
      }
      switch ( v61 )
      {
        case 1u:
          if ( v62 != &WPP_GLOBAL_Control && (*((_BYTE *)v62 + 28) & 4) != 0 )
            WPP_SF_(v62[2], 740, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
          *(_DWORD *)&Src[76] = 1;
          break;
        case 2u:
          if ( v62 != &WPP_GLOBAL_Control && (*((_BYTE *)v62 + 28) & 4) != 0 )
            WPP_SF_(v62[2], 741, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
          *(_DWORD *)&Src[76] = 2;
          break;
        case 0x64u:
          if ( v62 != &WPP_GLOBAL_Control && (*((_BYTE *)v62 + 28) & 4) != 0 )
            WPP_SF_(v62[2], 742, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
          *(_DWORD *)&Src[76] = 0;
          break;
        default:
          if ( v62 != &WPP_GLOBAL_Control && (*((_BYTE *)v62 + 28) & 4) != 0 )
            WPP_SF_(v62[2], 743, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
          *(_DWORD *)&Src[76] = 3;
          break;
      }
      v64 = L"00000000-0000-0000-0000-000000000008:00000000-0000-0000-0000-000000000008";
      LODWORD(v201) = 10;
    }
    *(_OWORD *)&v256[61] = *(_OWORD *)v64;
    *(_OWORD *)&v256[69] = *((_OWORD *)v64 + 1);
    *(_OWORD *)&v256[77] = *((_OWORD *)v64 + 2);
    *(_OWORD *)&v256[85] = *((_OWORD *)v64 + 3);
    *(_OWORD *)&v256[93] = *((_OWORD *)v64 + 4);
    *(_OWORD *)&v256[101] = *((_OWORD *)v64 + 5);
    *(_OWORD *)&v256[109] = *((_OWORD *)v64 + 6);
    *(_OWORD *)&v256[117] = *((_OWORD *)v64 + 7);
    *(_OWORD *)&v256[125] = *((_OWORD *)v64 + 8);
    *(_DWORD *)&v256[133] = *((_DWORD *)v64 + 36);
  }
  v238[0] = &v256[61];
  v65 = -1;
  do
    ++v65;
  while ( v256[v65 + 61] );
  v238[1] = (wchar_t *)v65;
  IsJitCandidateOrFallBackPolicy = EndpointDlp::Client::IsJitCandidateOrFallBackPolicy(v238);
  v194 = IsJitCandidateOrFallBackPolicy;
  LOBYTE(v67) = v256[61] == 0;
  v192[1] = v256[61] == 0;
  if ( !IsJitCandidateOrFallBackPolicy && v256[61] && !(_BYTE)v190 )
  {
    v68 = *(_DWORD *)&Src[76];
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v69 = RealtimeProtection::DlpUtils::DlpEnforcementLevelToStr(*(unsigned int *)&Src[76]);
      WPP_SF_SdSSD(*(_QWORD *)(v70 + 16), v197, (__int64)&v256[61], v69, FileApplicationAccess);
    }
    v217[0] = GetTickCount64();
    v198 = v68;
    v254[0] = 0;
    v254[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v254[0]) = 0;
    v254[2] = 0;
    v254[3] = v254[1];
    LOWORD(v254[2]) = 0;
    if ( !wcsncmp(&v256[61], L"multirules://", 0xDu) )
    {
      v71 = 1;
      LOBYTE(v190) = 1;
      v209 = 0;
      FileApplicationAccess = RealtimeProtection::DlpUtils::ResolvePolicyTraceInfo(v24, v208, v243, v256, v254);
      std::optional<std::wstring>::~optional<std::wstring>(v208);
      if ( FileApplicationAccess < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_sSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v24, FileApplicationAccess);
        RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v254);
        std::_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>::~_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>(v258);
        EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)v243);
LABEL_124:
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v241);
        std::optional<std::wstring>::~optional<std::wstring>(v251);
        goto LABEL_43;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v72 = &v254[2];
        if ( *((_QWORD *)&v254[3] + 1) > 7u )
          v72 = *(_OWORD **)&v254[2];
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          753,
          (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)"RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl",
          (__int64)v72);
      }
    }
    else
    {
      v71 = 0;
      LOBYTE(v190) = 0;
    }
    *(_DWORD *)v237 = 0;
    std::wstring::wstring(v252, &qword_18025C818);
    memset(v257, 0, 0x88u);
    v233 = 1;
    v234 = 0;
    std::wstring::wstring(v253, &qword_18025C818);
    if ( v71 )
    {
      v73 = (wchar_t *)&v254[2];
      if ( *((_QWORD *)&v254[3] + 1) > 7u )
        v73 = *(wchar_t **)&v254[2];
    }
    else
    {
      v73 = &v256[61];
    }
    v238[0] = v73;
    v74 = -1;
    v75 = -1;
    do
      ++v75;
    while ( v73[v75] );
    v238[1] = (wchar_t *)v75;
    *(_QWORD *)&v242[0] = v203;
    do
      ++v74;
    while ( *(_WORD *)(v203 + 2 * v74) );
    *((_QWORD *)&v242[0] + 1) = v74;
    LODWORD(LastFailure) = EndpointDlp::Client::GetPasteEnforcementLevel(v242, v238, v261, v237, &v234, &v233, v257);
    if ( (int)LastFailure < 0 )
    {
LABEL_199:
      v78 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      if ( *(_DWORD *)&v257[62] )
      {
        std::wstring::assign(v252, *(void **)&v257[64]);
        EndpointDlp::Client::FreeArchiveFileTraceInfo((EndpointDlp::Client *)v257, v77);
      }
      v78 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v79 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v252);
        WPP_SF_sddddS((TRACEHANDLE)v78[2], v234, Src[76], v237[0], v233, v79);
        v78 = (PVOID *)WPP_GLOBAL_Control;
      }
      v68 = *(_DWORD *)v237;
      v198 = *(_DWORD *)v237;
      if ( v234 )
      {
        RealtimeProtection::DlpEngineUtils::PrepareDlpEventGroupsOverrideJson(
          (unsigned int)v261,
          (unsigned int)&v261[146],
          v203,
          9,
          (__int64)v253);
        goto LABEL_199;
      }
    }
    if ( v193 )
    {
      if ( v78 != &WPP_GLOBAL_Control && (*((_BYTE *)v78 + 28) & 4) != 0 )
      {
        RealtimeProtection::DlpUtils::DlpEnforcementLevelToStr(*(unsigned int *)&Src[76]);
        RealtimeProtection::DlpUtils::DlpEnforcementLevelToStr(v68);
        WPP_SF_SSS((TRACEHANDLE)v78[2], v203, v80);
      }
      v68 = *(_DWORD *)&Src[76];
      v198 = *(_DWORD *)&Src[76];
    }
    v235 = 0;
    v240 = 0;
    if ( v68 == 2 )
    {
      v209 = 0;
      v81 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v241);
      LODWORD(LastFailure) = RealtimeProtection::DlpProcessCache::CheckIfBypassed(
                               (unsigned int)&v235,
                               (unsigned int)&v240,
                               (_DWORD)v204,
                               v196,
                               (__int64)v207,
                               9,
                               v81,
                               (__int64)v208);
      std::optional<std::wstring>::~optional<std::wstring>(v208);
      if ( (int)LastFailure < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            756,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            (unsigned int)LastFailure);
        if ( v240 )
          operator delete(v240, v82);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v253);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v252);
        RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v254);
        std::_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>::~_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>(v258);
        EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)v243);
        goto LABEL_213;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v85 = v235;
        v86 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v241);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          757,
          (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          v86,
          v85);
      }
      if ( v235 )
        v68 = 1;
      v198 = v68;
    }
    *(_DWORD *)&Src[76] = v68;
    v87 = *v219;
    v88 = v201;
    if ( *v219 > (unsigned int)v201 )
    {
      *v219 = v201;
      v87 = v88;
    }
    memmove(v216, Src, 8LL * v87);
    if ( (_BYTE)v190 )
    {
      v89 = (wchar_t *)&v254[2];
      if ( *((_QWORD *)&v254[3] + 1) > 7u )
        v89 = *(wchar_t **)&v254[2];
    }
    else
    {
      v89 = &v256[61];
    }
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"%!FUNC! File %ls, Enforcement %d, RuleId %ls",
      v24,
      v68,
      v89);
    if ( !v68 )
    {
      if ( v240 )
        operator delete(v240, v90);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v253);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v252);
      RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v254);
      std::_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>::~_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>(v258);
      EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)v243);
      v92 = 0;
      v93 = *(void **)&v192[5];
      goto LABEL_443;
    }
    v94 = v218;
    if ( v218 )
    {
      v236 = 0;
      v96 = CommonUtil::NewSprintfW((CommonUtil *)&v236, (wchar_t **)L"%ls", v256);
      if ( v96 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            758,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            (unsigned int)v96);
        if ( v236 )
          operator delete(v236, v95);
        if ( v240 )
          operator delete(v240, v95);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v253);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v252);
        RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v254);
        std::_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>::~_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>(v258);
        EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)v243);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v241);
        std::optional<std::wstring>::~optional<std::wstring>(v251);
        if ( *(_QWORD *)&v192[5] )
          operator delete(*(void **)&v192[5], v97);
        if ( v24 )
          operator delete(v24, v97);
        if ( v17 )
          operator delete(v17);
        return (unsigned int)v96;
      }
      *v94 = v236;
    }
    *(_OWORD *)v238 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v238[0]) = 0;
    v98 = (void *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v252);
    v99 = v195;
    std::wstring::assign(v238, v98);
    if ( v99 )
    {
      v93 = *(void **)&v192[5];
      v100 = std::wstring::wstring(v255, *(_QWORD *)&v192[5]);
      v101 = std::operator+<wchar_t>(v242, L"#", v100);
      v102 = std::operator+<wchar_t>(v208, v101, L".txt");
      std::wstring::append(v238, v102);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v208);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v242);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v255);
      v103 = std::to_wstring(v242, v233);
      v104 = std::operator+<wchar_t>(v208, L"#", v103);
      std::wstring::append(v238, v104);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v208);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v242);
      if ( v234 )
      {
        v105 = std::wstring::wstring(v232, &v261[146]);
        v106 = std::wstring::wstring(v231, v261);
        v107 = std::operator+<wchar_t>(v255, L"#", v106);
        v108 = std::operator+<wchar_t>(v242, v107, L",");
        v109 = std::operator+<wchar_t>(v208, v108, v105);
        std::wstring::append(v238, v109);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v208);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v242);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v255);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v231);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v232);
      }
      v99 = v195;
    }
    else
    {
      v93 = *(void **)&v192[5];
    }
    if ( v210 )
    {
      v236 = 0;
      v110 = (const wchar_t *)v238;
      if ( si128.m128i_i64[1] > 7uLL )
        v110 = v238[0];
      v112 = CommonUtil::NewSprintfW((CommonUtil *)&v236, (wchar_t **)L"%ls", v110);
      if ( v112 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            759,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            (unsigned int)v112);
        if ( v236 )
          operator delete(v236, v111);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v238);
        if ( v240 )
          operator delete(v240, v113);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v253);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v252);
        RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v254);
        std::_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>::~_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>(v258);
        EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)v243);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v241);
        std::optional<std::wstring>::~optional<std::wstring>(v251);
        if ( v93 )
          operator delete(v93, v114);
        if ( v24 )
          operator delete(v24, v114);
        if ( v17 )
          operator delete(v17);
        return (unsigned int)v112;
      }
      *v210 = (wchar_t *)v236;
    }
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v238);
    if ( !v99 )
    {
      *(_OWORD *)v238 = 0;
      si128.m128i_i64[0] = 0;
      v116 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v252);
      v117 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v253);
      v118 = v233 != 0;
      v209 = 0;
      v119 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v241);
      RealtimeProtection::DlpEngineTelemetry::GenerateDlpTelemetryEvent(
        (unsigned int)v238,
        (unsigned int)&v256[61],
        (unsigned int)v256,
        v198,
        9,
        *((_DWORD *)v202 + 22),
        v119,
        v203,
        (__int64)v207,
        (__int64)v204,
        v196,
        v235,
        (__int64)v240,
        0,
        0,
        0,
        (__int64)v208,
        0,
        (__int64)&qword_18025C818,
        (__int64)&qword_18025C818,
        v118,
        v117,
        0,
        v116,
        (__int64)&qword_18025C818,
        0);
      if ( v209 )
        std::string::`scalar deleting destructor'(v208);
      RealtimeProtection::CRtpDlpEngine::SendDlpTelemetryEvent(v120, v238);
      std::vector<RealtimeProtection::DlpEngineTelemetry::DlpTelemetryEvent>::_Tidy(v238);
    }
    LODWORD(LastFailure) = 0;
    if ( v240 )
      operator delete(v240, v115);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v253);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v252);
    RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v254);
    std::_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>::~_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>(v258);
    EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)v243);
    v92 = 0;
LABEL_443:
    if ( ShouldReclassifyFile && (unsigned int)CommonUtil::UtilIsFileExists((CommonUtil *)v24, v91) != -2147024894 )
    {
      if ( DeleteFileW(v24) )
      {
        RealtimeProtection::MpLogMessageImpl(
          (RealtimeProtection *)L"%hs: Deleted the PTB stub file due to ShouldReclassify the file: %ls",
          "RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl",
          v24);
      }
      else
      {
        LastFailure = (unsigned int)HrGetLastFailure();
        RealtimeProtection::MpLogMessageImpl(
          (RealtimeProtection *)L"%hs: Failed to delete the PTB stub file: %ls, hr = %lx",
          "RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl",
          v24,
          LastFailure);
      }
    }
    v178 = GetTickCount64() - TickCount64;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_SSddSdiii(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (__int64)&v256[61],
        v197,
        (char)a5,
        (__int64)v24,
        ShouldReclassifyFile,
        v225 - TickCount64,
        LOBYTE(v217[0]) - v225,
        v178);
    if ( g_pcsAsimovLock )
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v238);
      if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
        && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
      {
        v212 = *(_QWORD *)((char *)g_aAsimov + 68);
        LODWORD(v206) = *((_DWORD *)g_aAsimov + 16);
        LODWORD(v205) = *((unsigned __int8 *)g_aAsimov + 60);
        v200 = *((unsigned __int8 *)g_aAsimov + 59);
        v199 = *((unsigned __int8 *)g_aAsimov + 58);
        v193 = *((unsigned __int8 *)g_aAsimov + 57);
        *(_DWORD *)v237 = *((unsigned __int8 *)g_aAsimov + 56);
        v229 = *((_QWORD *)g_aAsimov + 6);
        TickCount64 = *((_QWORD *)g_aAsimov + 5);
        v227 = *((_QWORD *)g_aAsimov + 4);
        v226 = *((_QWORD *)g_aAsimov + 3);
        v225 = *((_QWORD *)g_aAsimov + 2);
        v224 = *((_QWORD *)g_aAsimov + 1);
        v223 = 0x2000000;
        LODWORD(v201) = v92;
        v192[0] = *((_BYTE *)v216 + 76);
        v222 = (__int64)&v256[61];
        v221 = (__int64)v207;
        v236 = (void *)1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v179,
          (int)&unk_1802C3BA0,
          (__int64)&v221,
          (__int64)&v222,
          (__int64)v192,
          (__int64)&v214,
          (__int64)&v213,
          (__int64)&v201,
          (__int64)&v223,
          (__int64)&v224,
          (__int64)&v225,
          (__int64)&v226,
          (__int64)&v227,
          (__int64)&TickCount64,
          (__int64)&v229,
          (__int64)v237,
          (__int64)&v193,
          (__int64)&v199,
          (__int64)&v200,
          (__int64)&v205,
          (__int64)&v206,
          (__int64)&v212,
          (__int64)&v212 + 4);
      }
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v238);
    }
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v241);
    std::optional<std::wstring>::~optional<std::wstring>(v251);
    if ( v93 )
    {
      v84 = v93;
      goto LABEL_458;
    }
    goto LABEL_459;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_sSdddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (__int64)v24,
      v197,
      (char)v67,
      IsJitCandidateOrFallBackPolicy,
      v190);
  if ( (*((_DWORD *)v202 + 10) != 2 || !HIBYTE(v190)) && *((_DWORD *)v202 + 10) != 4 )
  {
LABEL_369:
    std::_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>::~_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>(v258);
    EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)v243);
    goto LABEL_370;
  }
  LOBYTE(v190) = 0;
  v121 = RealtimeProtection::DlpPasteCache::CheckCacheFileClassificationExpiryState(v24, &v190, v67);
  if ( v121 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        750,
        (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (_DWORD)v24,
        v121);
    goto LABEL_369;
  }
  v192[0] = 0;
  if ( !(_BYTE)v190 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 749, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
    goto LABEL_369;
  }
  LOBYTE(v190) = 1;
  std::wstring::wstring(v242, &qword_18025C818);
  v193 = 0;
  Dlp::PTBUtils::GetPTBMaxTimeOutFallbackSettingsInfo(v242);
  v122 = *v219;
  v123 = v201;
  if ( *v219 > (unsigned int)v201 )
  {
    *v219 = v201;
    v122 = v123;
  }
  v124 = v193;
  *(_DWORD *)&Src[76] = v193;
  memmove(v216, Src, 8LL * v122);
  RealtimeProtection::MpLogMessageImpl(
    (RealtimeProtection *)L"[DlpPasteToBrowser] %hs: Sense classification max timeout for PTB. Going with enforcement %d, "
                           "fSendEvent %d for current file %ls",
    "RealtimeProtection::CRtpDlpEngine::CheckAccessForBufferImpl",
    v124,
    (unsigned __int8)v190,
    v24);
  if ( (_BYTE)v190 )
  {
    memset(v260, 0, 0x10Eu);
    v125 = EndpointDlp::Client::GetFallbackPolicyInfo(3, v260);
    v126 = v125;
    if ( v125 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          745,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)v125);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v242);
      if ( v259 )
        EndpointDlp::Client::FileAccessInfo::~FileAccessInfo((EndpointDlp::Client::FileAccessInfo *)v258);
      if ( v247 && v246 )
        std::_Ref_count_base::_Decref(v246);
      if ( v244 && v243[1] )
        std::_Ref_count_base::_Decref(v243[1]);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v241);
      std::optional<std::wstring>::~optional<std::wstring>(v251);
      if ( *(_QWORD *)&v192[5] )
        operator delete(*(void **)&v192[5], v127);
      if ( v24 )
        operator delete(v24, v127);
      if ( v17 )
        operator delete(v17);
      return v126;
    }
    if ( v218 )
    {
      v236 = 0;
      v128 = CommonUtil::NewSprintfW((CommonUtil *)&v236, (wchar_t **)L"%ls", v260);
      v130 = v128;
      if ( v128 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            746,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            (unsigned int)v128);
        if ( v236 )
          operator delete(v236, v129);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v242);
        if ( v259 )
          EndpointDlp::Client::FileAccessInfo::~FileAccessInfo((EndpointDlp::Client::FileAccessInfo *)v258);
        if ( v247 && v246 )
          std::_Ref_count_base::_Decref(v246);
        if ( v244 && v243[1] )
          std::_Ref_count_base::_Decref(v243[1]);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v241);
        std::optional<std::wstring>::~optional<std::wstring>(v251);
        if ( *(_QWORD *)&v192[5] )
          operator delete(*(void **)&v192[5], v131);
        if ( v24 )
          operator delete(v24, v131);
        if ( v17 )
          operator delete(v17);
        return v130;
      }
      *v218 = (wchar_t *)v236;
    }
    std::wstring::wstring(v255, v242);
    v132 = *(void **)&v192[5];
    if ( v195 )
    {
      v133 = std::wstring::wstring(v231, *(_QWORD *)&v192[5]);
      v134 = std::operator+<wchar_t>(v238, L"#", v133);
      v135 = std::operator+<wchar_t>(v208, v134, L".txt");
      std::wstring::append(v255, v135);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v208);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v238);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v231);
      v136 = std::to_wstring(v238, 0);
      v137 = std::operator+<wchar_t>(v208, L"#", v136);
      std::wstring::append(v255, v137);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v208);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v238);
    }
    if ( v210 )
    {
      v236 = 0;
      v138 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v255);
      v139 = CommonUtil::NewSprintfW((CommonUtil *)&v236, (wchar_t **)L"%ls", v138);
      v141 = v139;
      if ( v139 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            747,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            (unsigned int)v139);
        if ( v236 )
          operator delete(v236, v140);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v255);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v242);
        std::_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>::~_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>(v258);
        EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)v243);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v241);
        std::optional<std::wstring>::~optional<std::wstring>(v251);
        if ( v132 )
          operator delete(v132, v142);
        if ( v24 )
          operator delete(v24, v142);
        if ( v17 )
          operator delete(v17);
        return v141;
      }
      *v210 = (wchar_t *)v236;
    }
    if ( !v195 )
    {
      *(_OWORD *)v238 = 0;
      si128.m128i_i64[0] = 0;
      v209 = 0;
      v143 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v241);
      v144 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v242);
      RealtimeProtection::DlpEngineTelemetry::GenerateDlpTelemetryEvent(
        (unsigned int)v238,
        v144,
        (unsigned int)v260,
        v193,
        9,
        *((_DWORD *)v202 + 22),
        v143,
        v203,
        (__int64)v207,
        (__int64)v204,
        v196,
        0,
        0,
        0,
        0,
        0,
        (__int64)v208,
        0,
        (__int64)&qword_18025C818,
        (__int64)&qword_18025C818,
        1,
        (__int64)&qword_18025C818,
        0,
        (__int64)&qword_18025C818,
        (__int64)&qword_18025C818,
        0);
      if ( v209 )
        std::string::`scalar deleting destructor'(v208);
      std::vector<RealtimeProtection::DlpEngineTelemetry::DlpTelemetryEvent>::_Tidy(v238);
    }
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v255);
  }
  else
  {
    v132 = *(void **)&v192[5];
  }
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v242);
  std::_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>::~_Optional_destruct_base<EndpointDlp::Client::FileAccessInfo,0>(v258);
  EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)v243);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v241);
  std::optional<std::wstring>::~optional<std::wstring>(v251);
  if ( v132 )
    operator delete(v132, v145);
  if ( v24 )
    operator delete(v24, v145);
  if ( v17 )
    operator delete(v17);
  return 0;
}

```

## disassembly

```asm
0x1801888c8  push    rbx
0x1801888ca  push    rsi
0x1801888cb  push    rdi
0x1801888cc  push    r12
0x1801888ce  push    r13
0x1801888d0  push    r14
0x1801888d2  push    r15
0x1801888d4  mov     eax, 1130h
0x1801888d9  call    _alloca_probe
0x1801888de  sub     rsp, rax
0x1801888e1  mov     rax, cs:__security_cookie
0x1801888e8  xor     rax, rsp
0x1801888eb  mov     [rsp+1168h+var_48], rax
0x1801888f3  mov     dword ptr [rsp+1168h+var_107C], r9d
0x1801888fb  mov     rdi, r8
0x1801888fe  mov     [rsp+1168h+var_1050], r8
0x180188906  mov     [rsp+1168h+var_FB8], rdx
0x18018890e  mov     [rsp+1168h+var_1060], rcx
0x180188916  mov     [rsp+1168h+var_FB0], rdx
0x18018891e  mov     r11, [rsp+1168h+arg_30]
0x180188926  mov     [rsp+1168h+var_1058], r11
0x18018892e  mov     [rsp+1168h+var_FA8], rcx
0x180188936  mov     [rsp+1168h+var_1038], rdx
0x18018893e  mov     [rsp+1168h+var_F70], rdx
0x180188946  mov     [rsp+1168h+var_FA0], r8
0x18018894e  mov     dword ptr [rsp+1168h+var_1040], r9d
0x180188956  mov     rsi, [rsp+1168h+arg_28]
0x18018895e  mov     [rsp+1168h+var_F98], r11
0x180188966  mov     rax, [rsp+1168h+arg_40]
0x18018896e  mov     [rsp+1168h+var_FC0], rax
0x180188976  mov     [rsp+1168h+var_F88], rax
0x18018897e  mov     rax, [rsp+1168h+arg_48]
0x180188986  mov     [rsp+1168h+var_FE0], rax
0x18018898e  mov     rax, [rsp+1168h+arg_50]
0x180188996  mov     [rsp+1168h+var_FC8], rax
0x18018899e  mov     rax, [rsp+1168h+arg_58]
0x1801889a6  mov     [rsp+1168h+var_1008], rax
0x1801889ae  mov     [rsp+1168h+var_F80], rax
0x1801889b6  lea     r12, WPP_GLOBAL_Control
0x1801889bd  mov     r10, cs:WPP_GLOBAL_Control
0x1801889c4  lea     r14, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x1801889cb  cmp     r10, r12
0x1801889ce  jz      short loc_180188A07
0x1801889d0  test    byte ptr [r10+1Ch], 4
0x1801889d5  jz      short loc_180188A07
0x1801889d7  mov     edx, 2D5h
0x1801889dc  mov     eax, [r8+8]
0x1801889e0  mov     dword ptr [rsp+1168h+var_1148], eax
0x1801889e4  mov     r9d, dword ptr [rsp+1168h+arg_38]
0x1801889ec  mov     r8, r14
0x1801889ef  mov     rcx, [r10+10h]
0x1801889f3  call    WPP_SF_Dd
0x1801889f8  mov     r10, cs:WPP_GLOBAL_Control
0x1801889ff  mov     r11, [rsp+1168h+var_1058]
0x180188a07  mov     r8d, dword ptr [rsp+1168h+arg_38]
0x180188a0f  mov     edx, r8d
0x180188a12  shr     edx, 8
0x180188a15  mov     r15d, 1
0x180188a1b  and     edx, r15d
0x180188a1e  mov     r9d, r8d
0x180188a21  and     r9d, 800h
0x180188a28  mov     [rsp+1168h+var_1080], r9d
0x180188a30  mov     dword ptr [rsp+1168h+var_1048], r9d
0x180188a38  mov     ebx, r8d
0x180188a3b  and     ebx, r15d
0x180188a3e  xor     r13d, r13d
0x180188a41  test    r9d, r9d
0x180188a44  jnz     short loc_180188A50
0x180188a46  bt      r8d, 9
0x180188a4b  mov     eax, r15d
0x180188a4e  jb      short loc_180188A53
0x180188a50  mov     eax, r13d
0x180188a53  mov     dword ptr [rsp+1168h+var_FF0+4], eax
0x180188a5a  cmp     r10, r12
0x180188a5d  jz      short loc_180188AAF
0x180188a5f  test    byte ptr [r10+1Ch], 4
0x180188a64  jz      short loc_180188AAF
0x180188a66  mov     ecx, r13d
0x180188a69  test    r9d, r9d
0x180188a6c  setnz   cl
0x180188a6f  lea     r9, qword_18025C818
0x180188a76  mov     rax, r11
0x180188a79  test    r11, r11
0x180188a7c  cmovz   rax, r9
0x180188a80  mov     dword ptr [rsp+1168h+var_1120], ecx; char
0x180188a84  mov     dword ptr [rsp+1168h+var_1128], edx; unsigned int
0x180188a88  mov     qword ptr [rsp+1168h+var_1130], rax; bool
0x180188a8d  mov     dword ptr [rsp+1168h+var_1138], r8d; char
0x180188a92  mov     rcx, [rsp+1168h+var_1038]
0x180188a9a  mov     [rsp+1168h+var_1140], rcx; __int64
0x180188a9f  mov     eax, [rdi+8]
0x180188aa2  mov     dword ptr [rsp+1168h+var_1148], eax; char
0x180188aa6  mov     rcx, [r10+10h]; LoggerHandle
0x180188aaa  call    WPP_SF_sDSDSdd
0x180188aaf  call    cs:__imp_GetTickCount64
0x180188ab5  mov     [rsp+1168h+var_F78], rax
0x180188abd  call    cs:__imp_GetTickCount64
0x180188ac3  mov     [rsp+1168h+var_F90], rax
0x180188acb  call    cs:__imp_GetTickCount64
0x180188ad1  mov     eax, [rdi+4]
0x180188ad4  shl     rax, 20h
0x180188ad8  mov     ecx, [rdi]
0x180188ada  or      rax, rcx
0x180188add  mov     [rsp+1168h+var_F00], rax
0x180188ae5  mov     rdi, r13
0x180188ae8  mov     [rsp+1168h+var_FE8], r13
0x180188af0  mov     [rsp+1168h+lpFileName], r13
0x180188af8  mov     qword ptr [rsp+1168h+var_1095+5], r13
0x180188b00  mov     byte ptr [rsp+1168h+var_1138], r15b; wchar_t **
0x180188b05  lea     rax, [rsp+1168h+var_1095+5]
0x180188b0d  mov     [rsp+1168h+var_1140], rax; wchar_t **
0x180188b12  lea     rax, [rsp+1168h+lpFileName]
0x180188b1a  mov     [rsp+1168h+var_1148], rax; bool
0x180188b1f  mov     r9b, bl; void *
0x180188b22  mov     r8, rsi; void *
0x180188b25  mov     edx, dword ptr [rsp+1168h+arg_20]; wchar_t *
0x180188b2c  mov     rsi, [rsp+1168h+var_1060]
0x180188b34  mov     rcx, [rsi+98h]; this
0x180188b3b  call    ?WriteBufferToCache@DlpUtils@RealtimeProtection@@YAJPEB_WKPEBX_NPEAPEA_W32@Z; RealtimeProtection::DlpUtils::WriteBufferToCache(wchar_t const *,ulong,void const *,bool,wchar_t * *,wchar_t * *,bool)
0x180188b40  mov     ebx, eax
0x180188b42  test    eax, eax
0x180188b44  jns     short loc_180188B9A
0x180188b46  mov     rcx, cs:WPP_GLOBAL_Control
0x180188b4d  cmp     rcx, r12
0x180188b50  jz      short loc_180188B6D
0x180188b52  test    [rcx+1Ch], r15b
0x180188b56  jz      short loc_180188B6D
0x180188b58  mov     edx, 2D7h
0x180188b5d  mov     r9d, eax
0x180188b60  mov     r8, r14
0x180188b63  mov     rcx, [rcx+10h]
0x180188b67  call    WPP_SF_d
0x180188b6c  nop
0x180188b6d  mov     rcx, qword ptr [rsp+1168h+var_1095+5]; void *
0x180188b75  test    rcx, rcx
0x180188b78  jz      short loc_180188B80
0x180188b7a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180188b7f  nop
0x180188b80  mov     rcx, [rsp+1168h+lpFileName]; void *
0x180188b88  test    rcx, rcx
0x180188b8b  jz      short loc_180188B93
0x180188b8d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180188b92  nop
0x180188b93  mov     eax, ebx
0x180188b95  jmp     loc_18018BA97
0x180188b9a  lea     rdx, aRealtimeprotec_28; "RealtimeProtection::CRtpDlpEngine::Chec"...
0x180188ba1  cmp     ebx, r15d
0x180188ba4  mov     rbx, [rsp+1168h+lpFileName]
0x180188bac  mov     r8, rbx
0x180188baf  jnz     short loc_180188BC5
0x180188bb1  lea     rcx, aDlppastetobrow_11; "[DlpPasteToBrowser] %hs Cache hit: %ls"
0x180188bb8  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x180188bbd  mov     eax, r15d
0x180188bc0  jmp     loc_180188D7D
0x180188bc5  lea     rcx, aHsCreatedThePt; "%hs: Created the PTB stub file: %ls"
0x180188bcc  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x180188bd1  call    cs:__imp_GetTickCount64
0x180188bd7  mov     [rsp+1168h+var_F90], rax
0x180188bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180188be6  cmp     rcx, r12
0x180188be9  jz      short loc_180188C0E
0x180188beb  test    byte ptr [rcx+1Ch], 4
0x180188bef  jz      short loc_180188C0E
0x180188bf1  mov     edx, 2D8h
0x180188bf6  mov     [rsp+1168h+var_1148], rbx
0x180188bfb  lea     r9, aRealtimeprotec_28; "RealtimeProtection::CRtpDlpEngine::Chec"...
0x180188c02  mov     r8, r14
0x180188c05  mov     rcx, [rcx+10h]
0x180188c09  call    WPP_SF_sS
0x180188c0e  lea     r8, [rsp+1168h+var_FE8]; struct PPID *
0x180188c16  mov     rsi, [rsp+1168h+var_1050]
0x180188c1e  mov     rdx, rsi; unsigned int
0x180188c21  mov     ecx, dword ptr [rsp+1168h+var_107C]; this
0x180188c28  call    ?GetClassificationUserSid@DlpUserSidCache@RealtimeProtection@@YAJKAEBUPPID@@PEAPEAX@Z; RealtimeProtection::DlpUserSidCache::GetClassificationUserSid(ulong,PPID const &,void * *)
0x180188c2d  mov     edi, eax
0x180188c2f  test    eax, eax
0x180188c31  jns     short loc_180188C94
0x180188c33  mov     rcx, cs:WPP_GLOBAL_Control
0x180188c3a  cmp     rcx, r12
0x180188c3d  jz      short loc_180188C5A
0x180188c3f  test    [rcx+1Ch], r15b
0x180188c43  jz      short loc_180188C5A
0x180188c45  mov     edx, 2D9h
0x180188c4a  mov     r9d, eax
0x180188c4d  mov     r8, r14
0x180188c50  mov     rcx, [rcx+10h]
0x180188c54  call    WPP_SF_d
0x180188c59  nop
0x180188c5a  mov     rcx, qword ptr [rsp+1168h+var_1095+5]; void *
0x180188c62  test    rcx, rcx
0x180188c65  jz      short loc_180188C6D
0x180188c67  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180188c6c  nop
0x180188c6d  test    rbx, rbx
0x180188c70  jz      short loc_180188C7B
0x180188c72  mov     rcx, rbx; void *
0x180188c75  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180188c7a  nop
0x180188c7b  mov     rcx, [rsp+1168h+var_FE8]; Block
0x180188c83  test    rcx, rcx
0x180188c86  jz      short loc_180188C8D
0x180188c88  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180188c8d  mov     eax, edi
0x180188c8f  jmp     loc_18018BA97
0x180188c94  mov     [rsp+1168h+var_FD8], rbx
0x180188c9c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180188ca0  inc     rax
0x180188ca3  cmp     [rbx+rax*2], r13w
0x180188ca8  jnz     short loc_180188CA0
0x180188caa  mov     [rsp+1168h+var_FD0], rax
0x180188cb2  mov     dword ptr [rsp+1168h+var_1148], 6
0x180188cba  mov     r9, [rsp+1168h+var_F00]
0x180188cc2  mov     r8d, [rsi+8]
0x180188cc6  mov     rdi, [rsp+1168h+var_FE8]
0x180188cce  mov     rdx, rdi
0x180188cd1  lea     rcx, [rsp+1168h+var_FD8]
0x180188cd9  call    ?GenerateSyncClassificationEvent@Client@EndpointDlp@@YAJAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAXK_KW4_DLP_JIT_SYNC_CLASSIFICATION_REASON@@@Z; EndpointDlp::Client::GenerateSyncClassificationEvent(std::wstring_view const &,void *,ulong,unsigned __int64,_DLP_JIT_SYNC_CLASSIFICATION_REASON)
0x180188cde  mov     esi, eax
0x180188ce0  test    eax, eax
0x180188ce2  jns     short loc_180188D40
0x180188ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x180188ceb  cmp     rcx, r12
0x180188cee  jz      short loc_180188D0B
0x180188cf0  test    [rcx+1Ch], r15b
0x180188cf4  jz      short loc_180188D0B
0x180188cf6  mov     edx, 2DAh
0x180188cfb  mov     r9d, eax
0x180188cfe  mov     r8, r14
0x180188d01  mov     rcx, [rcx+10h]
0x180188d05  call    WPP_SF_d
0x180188d0a  nop
0x180188d0b  mov     rcx, qword ptr [rsp+1168h+var_1095+5]; void *
0x180188d13  test    rcx, rcx
0x180188d16  jz      short loc_180188D1E
0x180188d18  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180188d1d  nop
0x180188d1e  test    rbx, rbx
0x180188d21  jz      short loc_180188D2C
0x180188d23  mov     rcx, rbx; void *
0x180188d26  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180188d2b  nop
0x180188d2c  test    rdi, rdi
0x180188d2f  jz      short loc_180188D39
0x180188d31  mov     rcx, rdi; Block
0x180188d34  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180188d39  mov     eax, esi
0x180188d3b  jmp     loc_18018BA97
0x180188d40  mov     eax, r13d
0x180188d43  mov     rcx, cs:WPP_GLOBAL_Control
0x180188d4a  cmp     rcx, r12
0x180188d4d  jz      short loc_180188D75
0x180188d4f  test    byte ptr [rcx+1Ch], 4
0x180188d53  jz      short loc_180188D75
0x180188d55  mov     edx, 2DBh
0x180188d5a  mov     [rsp+1168h+var_1148], rbx
0x180188d5f  lea     r9, aRealtimeprotec_28; "RealtimeProtection::CRtpDlpEngine::Chec"...
0x180188d66  mov     r8, r14
0x180188d69  mov     rcx, [rcx+10h]
0x180188d6d  call    WPP_SF_sS
0x180188d72  mov     eax, r13d
0x180188d75  mov     rsi, [rsp+1168h+var_1060]
0x180188d7d  mov     dword ptr [rsp+1168h+var_FF0], eax
0x180188d84  lea     rcx, aMpdlpDebugchec_3; "MpDlp_DebugCheckAccessForBufferImpl"
0x180188d8b  call    ?DlpMpLookupMiscConfigFlag@DlpUtils@RealtimeProtection@@YAHPEB_W@Z; RealtimeProtection::DlpUtils::DlpMpLookupMiscConfigFlag(wchar_t const *)
0x180188d90  test    eax, eax
0x180188d92  jz      short loc_180188D9A
0x180188d94  call    cs:__imp_DebugBreak
0x180188d9a  mov     byte ptr [rsp+1168h+var_EF0+0Ch], r13b
0x180188da2  mov     rdx, rbx
0x180188da5  lea     rcx, [rsp+1168h+var_1030]
0x180188dad  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180188db2  nop
0x180188db3  lea     r8, [rsp+1168h+var_EF0]
0x180188dbb  mov     rdx, rax
0x180188dbe  lea     rcx, [rsp+1168h+var_E38]
0x180188dc6  call    ?GetFilterPath@DlpPathCache@RealtimeProtection@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@AEBV?$optional@UPPID@@@4@@Z; RealtimeProtection::DlpPathCache::GetFilterPath(std::wstring const &,std::optional<PPID> const &)
0x180188dcb  nop
0x180188dcc  lea     rcx, [rsp+1168h+var_1030]; void *
0x180188dd4  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180188dd9  cmp     [rsp+1168h+var_E18], r13b
0x180188de1  jnz     short loc_180188E29
0x180188de3  lea     rcx, [rsp+1168h+var_E38]
0x180188deb  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x180188df0  nop
0x180188df1  mov     rcx, qword ptr [rsp+1168h+var_1095+5]; void *
0x180188df9  test    rcx, rcx
0x180188dfc  jz      short loc_180188E04
0x180188dfe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180188e03  nop
0x180188e04  test    rbx, rbx
0x180188e07  jz      short loc_180188E12
0x180188e09  mov     rcx, rbx; void *
0x180188e0c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180188e11  nop
0x180188e12  test    rdi, rdi
0x180188e15  jz      short loc_180188E1F
0x180188e17  mov     rcx, rdi; Block
0x180188e1a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180188e1f  mov     eax, 80070057h
0x180188e24  jmp     loc_18018BA97
  ... truncated ...
```
