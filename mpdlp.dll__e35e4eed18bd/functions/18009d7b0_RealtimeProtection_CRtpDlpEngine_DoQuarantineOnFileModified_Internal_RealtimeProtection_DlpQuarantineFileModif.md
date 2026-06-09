# RealtimeProtection::CRtpDlpEngine::DoQuarantineOnFileModified_Internal(RealtimeProtection::_DlpQuarantineFileModifiedInfoSource,PPID const &,wchar_t const *,ulong)

- ea: `0x18009d7b0`
- end: `0x18009f47e`
- name: `?DoQuarantineOnFileModified_Internal@CRtpDlpEngine@RealtimeProtection@@QEAAJW4_DlpQuarantineFileModifiedInfoSource@2@AEBUPPID@@PEB_WK@Z`
- size: `7374`
- prototype: `int __high(enum RealtimeProtection::_DlpQuarantineFileModifiedInfoSource, const struct PPID *, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `96`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009d750`

## callees

- `0x18001a444`
- `0x18001b220`
- `0x18001b9ec`
- `0x18001bc6c`
- `0x18001e3c4`
- `0x180027a90`
- `0x180028a10`
- `0x180028d80`
- `0x180029290`
- `0x180029590`
- `0x180029830`
- `0x18002a4e0`
- `0x18002bf88`
- `0x18002c150`
- `0x180034420`
- `0x180037afc`
- `0x180038450`
- `0x1800399c0`
- `0x18003df30`
- `0x180042594`
- `0x180042950`
- `0x1800456c8`
- `0x1800456fc`
- `0x180046d10`
- `0x180046d7c`
- `0x180049090`
- `0x180049b34`
- `0x18004b3bc`
- `0x18004de90`
- `0x180050300`
- `0x1800542e8`
- `0x18005d680`
- `0x18006b998`
- `0x18006bbd0`
- `0x180074f60`
- `0x180080030`
- `0x1800809d0`
- `0x180084c44`
- `0x180089510`
- `0x18008acf0`
- `0x18008c840`
- `0x180092740`
- `0x180092a68`
- `0x1800943fc`
- `0x18009711c`
- `0x1800984f0`
- `0x18009be50`
- `0x18009d7b0`
- `0x18009f730`
- `0x1800a3548`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18009e2e6`
- `KERNEL32!CompareStringOrdinal` at `0x18009e2e6`
- `KERNEL32!CloseHandle` at `0x18009dddd`
- `KERNEL32!CloseHandle` at `0x18009de0e`
- `KERNEL32!CloseHandle` at `0x18009de74`
- `KERNEL32!CloseHandle` at `0x18009df24`
- `KERNEL32!CloseHandle` at `0x18009e060`
- `KERNEL32!CloseHandle` at `0x18009e073`
- `KERNEL32!CloseHandle` at `0x18009eed5`
- `KERNEL32!CloseHandle` at `0x18009dddd`
- `KERNEL32!CloseHandle` at `0x18009de0e`
- `KERNEL32!CloseHandle` at `0x18009de74`
- `KERNEL32!CloseHandle` at `0x18009df24`
- `KERNEL32!CloseHandle` at `0x18009e060`
- `KERNEL32!CloseHandle` at `0x18009e073`
- `KERNEL32!CloseHandle` at `0x18009eed5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18009e9b3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18009e9b3`
- `KERNEL32!DebugBreak` at `0x18009e08b`
- `KERNEL32!DebugBreak` at `0x18009e08b`
- `ADVAPI32!RevertToSelf` at `0x18009dffb`
- `ADVAPI32!RevertToSelf` at `0x18009e00e`
- `ADVAPI32!RevertToSelf` at `0x18009e285`
- `ADVAPI32!RevertToSelf` at `0x18009e29e`
- `ADVAPI32!RevertToSelf` at `0x18009e989`
- `ADVAPI32!RevertToSelf` at `0x18009ec47`
- `ADVAPI32!RevertToSelf` at `0x18009ec64`
- `ADVAPI32!RevertToSelf` at `0x18009f370`
- `ADVAPI32!RevertToSelf` at `0x18009dffb`
- `ADVAPI32!RevertToSelf` at `0x18009e00e`
- `ADVAPI32!RevertToSelf` at `0x18009e285`
- `ADVAPI32!RevertToSelf` at `0x18009e29e`
- `ADVAPI32!RevertToSelf` at `0x18009e989`
- `ADVAPI32!RevertToSelf` at `0x18009ec47`
- `ADVAPI32!RevertToSelf` at `0x18009ec64`
- `ADVAPI32!RevertToSelf` at `0x18009f370`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall RealtimeProtection::CRtpDlpEngine::DoQuarantineOnFileModified_Internal(
        struct _FILETIME a1,
        int a2,
        FILETIME *a3,
        WCHAR *a4,
        __int16 a5)
{
  int v9; // eax
  struct RealtimeProtection::_QuarantineParams *v10; // rdx
  __int64 v11; // rcx
  int QuarantineItemStatus; // ebx
  char v13; // bl
  __int64 v14; // rcx
  char v15; // al
  __m128i si128; // xmm6
  int QuarantineConfig; // eax
  bool v18; // dl
  RealtimeProtection::DlpProcessCache *v19; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  char v22; // si
  __int64 v23; // rcx
  unsigned __int8 v24; // al
  struct _FILETIME v25; // rcx
  __int64 v26; // rcx
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  const wchar_t *v29; // rdx
  __int64 last_of; // rax
  __int64 v31; // rax
  LPCWCH *v32; // rcx
  const wchar_t *v33; // rdx
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  wchar_t *v36; // rcx
  LPCWCH *v37; // r9
  int v38; // ebx
  _QWORD *v39; // rcx
  __int64 v40; // rdx
  WCHAR *v41; // r9
  __int64 v42; // rax
  const wchar_t *v43; // rdx
  void **v44; // r9
  int v45; // eax
  HANDLE v46; // rbx
  int v47; // eax
  __int64 v48; // rax
  void **v49; // r9
  int v50; // eax
  int v51; // eax
  int VolumeDeviceCharacteristics; // eax
  int v53; // ebx
  char v54; // al
  __int64 FilterPath; // rax
  _QWORD *v56; // rcx
  WCHAR *v57; // r9
  __int64 v58; // rdx
  char v59; // cl
  __int64 DosPathW2K; // rax
  const WCHAR *v61; // rcx
  const wchar_t *v62; // rdx
  WCHAR *v63; // rcx
  const wchar_t *v64; // rdx
  WCHAR *v65; // rcx
  int ClassificationUserSidString; // eax
  int v67; // edx
  int v68; // r8d
  LPCWSTR *v69; // r9
  LPCWSTR *v70; // r9
  unsigned int *v71; // r9
  __int64 v72; // rax
  __int64 v73; // rcx
  int v74; // eax
  int v75; // ebx
  PVOID *v76; // rcx
  __int64 DlpFileUniqueId; // rax
  unsigned int v78; // edx
  __int64 v79; // rcx
  enum RealtimeProtection::_DlpQuarantineStatus *v80; // r8
  enum RealtimeProtection::_DlpQuarantineStatus *v81; // r8
  _QWORD *v82; // rcx
  __int64 v83; // rdx
  __int64 v84; // r9
  _QWORD *v85; // rax
  RealtimeProtection::DlpProcessCache *v86; // rcx
  int ModifiedTime; // eax
  unsigned int Value; // eax
  bool *v89; // r8
  unsigned int v90; // ebx
  CommonUtil *v91; // rax
  const unsigned __int64 *v92; // rdx
  unsigned __int64 v93; // r9
  __int64 v94; // rdx
  int AppNameFromAppDelegationCache; // eax
  __int64 v96; // rax
  const wchar_t *v97; // r8
  __int64 v98; // rax
  const WCHAR *v99; // rbx
  void **v100; // r9
  int PrimaryToken; // eax
  _QWORD *v102; // rcx
  __int64 v103; // rdx
  unsigned int v104; // eax
  __int64 v105; // rax
  __int64 v106; // rax
  int v107; // r13d
  _QWORD *v108; // rdi
  LPCWSTR *v109; // rbx
  int v110; // eax
  LPCWCH *v111; // rdx
  __int128 *v112; // rcx
  LPCWCH *v113; // rdi
  __int64 v114; // rbx
  bool v115; // cf
  int v116; // eax
  unsigned int bIgnoreCase; // [rsp+28h] [rbp-130h]
  unsigned int *bIgnoreCasea; // [rsp+28h] [rbp-130h]
  char v119; // [rsp+D8h] [rbp-80h]
  char v120; // [rsp+D8h] [rbp-80h]
  char v121; // [rsp+D9h] [rbp-7Fh]
  int v122; // [rsp+DCh] [rbp-7Ch]
  BOOL v123; // [rsp+DCh] [rbp-7Ch]
  unsigned int v124; // [rsp+E0h] [rbp-78h] BYREF
  HANDLE hObject; // [rsp+E8h] [rbp-70h] BYREF
  HANDLE hExistingToken[2]; // [rsp+F0h] [rbp-68h] BYREF
  int v127; // [rsp+100h] [rbp-58h]
  _BYTE v128[32]; // [rsp+108h] [rbp-50h] BYREF
  char v129; // [rsp+128h] [rbp-30h]
  char v130; // [rsp+148h] [rbp-10h]
  ULONG SessionId[4]; // [rsp+158h] [rbp+0h] BYREF
  __int64 v132; // [rsp+168h] [rbp+10h] BYREF
  LPCWCH lpString1[2]; // [rsp+170h] [rbp+18h] BYREF
  __int64 v134; // [rsp+180h] [rbp+28h]
  unsigned __int64 v135; // [rsp+188h] [rbp+30h]
  __int128 v136; // [rsp+190h] [rbp+38h] BYREF
  __int64 v137; // [rsp+1A0h] [rbp+48h]
  __int64 v138; // [rsp+1A8h] [rbp+50h]
  _BYTE v139[40]; // [rsp+1B0h] [rbp+58h] BYREF
  _BYTE v140[40]; // [rsp+1D8h] [rbp+80h] BYREF
  void *Block; // [rsp+200h] [rbp+A8h] BYREF
  HANDLE phNewToken[2]; // [rsp+208h] [rbp+B0h] BYREF
  struct _FILETIME v143[2]; // [rsp+218h] [rbp+C0h] BYREF
  WCHAR szFileName[12]; // [rsp+228h] [rbp+D0h] BYREF
  unsigned __int64 v145; // [rsp+240h] [rbp+E8h]
  char v146; // [rsp+248h] [rbp+F0h]
  unsigned int v147[6]; // [rsp+250h] [rbp+F8h] BYREF
  unsigned __int64 v148; // [rsp+268h] [rbp+110h]
  char v149; // [rsp+270h] [rbp+118h]
  LPCWSTR StringSid[2]; // [rsp+278h] [rbp+120h] BYREF
  __int64 v151; // [rsp+288h] [rbp+130h]
  unsigned __int64 v152; // [rsp+290h] [rbp+138h]
  void *v153[2]; // [rsp+298h] [rbp+140h] BYREF
  __m128i v154; // [rsp+2A8h] [rbp+150h]
  _BYTE v155[16]; // [rsp+2B8h] [rbp+160h] BYREF
  char v156; // [rsp+2C8h] [rbp+170h]
  __m128i v157; // [rsp+2D8h] [rbp+180h] BYREF
  char v158; // [rsp+2E8h] [rbp+190h]
  _OWORD v159[2]; // [rsp+2F8h] [rbp+1A0h] BYREF
  __int128 v160; // [rsp+318h] [rbp+1C0h]
  __m128i v161; // [rsp+328h] [rbp+1D0h]
  __int128 v162; // [rsp+338h] [rbp+1E0h]
  __m128i v163; // [rsp+348h] [rbp+1F0h]
  RealtimeProtection::DlpProcessCache *v164; // [rsp+358h] [rbp+200h]
  _BYTE v165[24]; // [rsp+368h] [rbp+210h] BYREF
  _QWORD v166[4]; // [rsp+380h] [rbp+228h] BYREF
  char v167; // [rsp+3A0h] [rbp+248h]
  char v168; // [rsp+3A8h] [rbp+250h]
  _BYTE v169[64]; // [rsp+3B8h] [rbp+260h] BYREF
  char v170; // [rsp+3F8h] [rbp+2A0h]
  int v171[2]; // [rsp+408h] [rbp+2B0h] BYREF
  _BYTE v172[64]; // [rsp+410h] [rbp+2B8h] BYREF
  DWORD FileSystemFlags[2]; // [rsp+450h] [rbp+2F8h] BYREF
  _BYTE v174[64]; // [rsp+458h] [rbp+300h] BYREF
  _OWORD v175[2]; // [rsp+498h] [rbp+340h] BYREF
  __int128 v176; // [rsp+4B8h] [rbp+360h] BYREF
  __m128i v177; // [rsp+4C8h] [rbp+370h]
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+4D8h] [rbp+380h] BYREF
  __int128 v179; // [rsp+4E8h] [rbp+390h]
  __m128i v180; // [rsp+4F8h] [rbp+3A0h]
  __int128 v181; // [rsp+508h] [rbp+3B0h]
  __m128i v182; // [rsp+518h] [rbp+3C0h]
  __int128 v183; // [rsp+528h] [rbp+3D0h]
  __m128i v184; // [rsp+538h] [rbp+3E0h]
  __int128 v185; // [rsp+548h] [rbp+3F0h]
  __m128i v186; // [rsp+558h] [rbp+400h]
  __int128 v187; // [rsp+568h] [rbp+410h]
  __m128i v188; // [rsp+578h] [rbp+420h]
  __int64 v189[2]; // [rsp+588h] [rbp+430h] BYREF
  __m128i v190; // [rsp+598h] [rbp+440h]
  _OWORD v191[2]; // [rsp+5A8h] [rbp+450h] BYREF
  _OWORD v192[2]; // [rsp+5C8h] [rbp+470h] BYREF
  _OWORD v193[2]; // [rsp+5E8h] [rbp+490h] BYREF
  __int128 v194; // [rsp+608h] [rbp+4B0h] BYREF
  __int64 v195; // [rsp+618h] [rbp+4C0h]
  _BYTE v196[32]; // [rsp+630h] [rbp+4D8h] BYREF
  _BYTE v197[72]; // [rsp+650h] [rbp+4F8h] BYREF
  _BYTE v198[272]; // [rsp+698h] [rbp+540h] BYREF

  v127 = a2;
  v143[0] = a1;
  if ( a4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_SLDd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, (_DWORD)a3, (_DWORD)a4, a3[1].dwLowDateTime, a5, a2);
    *(_OWORD *)SessionId = 0;
    v132 = 0;
    *(_OWORD *)lpString1 = 0;
    v134 = 0;
    v135 = 7;
    LOWORD(lpString1[0]) = 0;
    v136 = 0;
    v137 = 0;
    v138 = 7;
    LOWORD(v136) = 0;
    v139[32] = 0;
    v140[32] = 0;
    Block = 0;
    phNewToken[0] = 0;
    *(FILETIME *)SessionId = *a3;
    SessionId[2] = a3[1].dwLowDateTime;
    v9 = RealtimeProtection::DlpProcessCache::GetSessionId(a3, (const struct PPID *)&SessionId[3], (unsigned int *)a3);
    QuarantineItemStatus = v9;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          239,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)v9);
      goto LABEL_371;
    }
    if ( !SessionId[3] )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          240,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          a3[1].dwLowDateTime);
LABEL_23:
      QuarantineItemStatus = 1;
LABEL_371:
      RealtimeProtection::_DlpQuarantineProcessInfo::~_DlpQuarantineProcessInfo((RealtimeProtection::_DlpQuarantineProcessInfo *)SessionId);
      return (unsigned int)QuarantineItemStatus;
    }
    if ( a2 == 2 )
    {
      v13 = Dlp::FeatureControl::GetFlag<enum Dlp::FeatureControl::UnsavedDocumentEnforcementFlags,void,void>(v11, 2);
      v15 = Dlp::FeatureControl::GetFlag<enum Dlp::FeatureControl::UnsavedDocumentEnforcementFlags,void,void>(v14, 4);
      if ( v13 )
      {
        if ( v15 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 241, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, a4);
          goto LABEL_23;
        }
      }
    }
    v159[0] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v159[1] = si128;
    LOWORD(v159[0]) = 0;
    v160 = 0;
    v161 = si128;
    LOWORD(v160) = 0;
    v162 = 0;
    v163 = si128;
    LOWORD(v162) = 0;
    v164 = 0;
    QuarantineConfig = RealtimeProtection::DlpEngineUtils::ReadQuarantineConfig(
                         (RealtimeProtection::DlpEngineUtils *)v159,
                         v10);
    QuarantineItemStatus = QuarantineConfig;
    if ( QuarantineConfig < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_29;
      v21 = 242;
      goto LABEL_28;
    }
    v22 = (char)v164;
    LOBYTE(v19) = (_BYTE)v164;
    QuarantineConfig = RealtimeProtection::DlpProcessCache::SetQuarantineEngineStatus(v19, v18);
    QuarantineItemStatus = QuarantineConfig;
    if ( QuarantineConfig < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_29;
      v21 = 243;
      goto LABEL_28;
    }
    v24 = Dlp::FeatureControl::GetFlag<enum Dlp::FeatureControl::QuarantineSettingFlags,void,void>(v23, 1);
    if ( !v22 || !v24 )
    {
      *(_BYTE *)(*(_QWORD *)v143 + 95LL) = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 244, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v24);
      goto LABEL_375;
    }
    v25 = v143[0];
    *(_BYTE *)(*(_QWORD *)v143 + 95LL) = 1;
    if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD))Dlp::FeatureControl::GetFlag<enum Dlp::FeatureControl::QuarantineSettingFlags,void,void>)(
                             v25,
                             8) )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_375;
      v28 = 245;
LABEL_44:
      WPP_SF_(v27[2], v28, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
LABEL_375:
      RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent::~DlpThrottleAnyAppEvent((RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent *)v159);
      RealtimeProtection::_DlpQuarantineProcessInfo::~_DlpQuarantineProcessInfo((RealtimeProtection::_DlpQuarantineProcessInfo *)SessionId);
      return 1;
    }
    if ( !(unsigned __int8)Dlp::FeatureControl::GetFlag<enum Dlp::FeatureControl::QuarantineSettingFlags,void,void>(
                             v26,
                             2) )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_375;
      v28 = 246;
      goto LABEL_44;
    }
    v124 = 0;
    v143[0] = *a3;
    v143[1].dwLowDateTime = a3[1].dwLowDateTime;
    QuarantineConfig = RealtimeProtection::DlpProcessCache::GetKnownProcessType(v143, &v124);
    QuarantineItemStatus = QuarantineConfig;
    if ( QuarantineConfig < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_29;
      v21 = 247;
LABEL_28:
      WPP_SF_d(v20[2], v21, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, (unsigned int)QuarantineConfig);
LABEL_29:
      RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent::~DlpThrottleAnyAppEvent((RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent *)v159);
      goto LABEL_371;
    }
    if ( (int)RealtimeProtection::DlpProcessCache::GetApplicationName(a3, lpString1) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          248,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          a3[1].dwLowDateTime);
      if ( (int)Dlp::Utils::GetProcessImageName((void **)a3[1].dwLowDateTime) < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            249,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            a3[1].dwLowDateTime);
        std::wstring::assign(lpString1, L"Unknown");
      }
      else
      {
        last_of = std::wstring::find_last_of(lpString1, L"\\");
        if ( last_of != -1 )
        {
          v31 = std::wstring::substr(lpString1, v155, last_of + 1, -1);
          std::wstring::operator=(lpString1, v31);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v155);
        }
      }
    }
    v32 = lpString1;
    if ( v135 > 7 )
      v32 = (LPCWCH *)lpString1[0];
    if ( !RealtimeProtection::DlpRtpPluginQuery::IsUnsavedDocumentProcessIncluded(
            (RealtimeProtection::DlpRtpPluginQuery *)v32,
            v29) )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_375;
      v35 = 250;
LABEL_72:
      v37 = lpString1;
      if ( v135 > 7 )
        v37 = (LPCWCH *)lpString1[0];
      WPP_SF_S(v34[2], v35, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v37);
      goto LABEL_375;
    }
    v36 = (wchar_t *)lpString1;
    if ( v135 > 7 )
      v36 = (wchar_t *)lpString1[0];
    if ( RealtimeProtection::DlpRtpPluginQuery::IsUnsavedDocumentProcessExcluded(v36, v33) )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_375;
      v35 = 251;
      goto LABEL_72;
    }
    v146 = 0;
    v149 = 0;
    if ( v127 == 1 )
    {
      v38 = a5 & 0x10;
      if ( (a5 & 0x805) == 0 && (a5 & 0x10) == 0 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_194;
        v40 = 252;
        goto LABEL_81;
      }
      if ( (unsigned __int8)RealtimeProtection::DlpUtils::IsOfficeProcess(v124) )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_194;
        v40 = 253;
LABEL_81:
        v41 = a4;
LABEL_193:
        WPP_SF_S(v39[2], v40, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v41);
LABEL_194:
        std::optional<std::wstring>::~optional<std::wstring>(v147);
        std::optional<std::wstring>::~optional<std::wstring>(szFileName);
        RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent::~DlpThrottleAnyAppEvent((RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent *)v159);
        QuarantineItemStatus = 1;
        goto LABEL_371;
      }
      v42 = std::wstring::wstring(v155, a4);
      std::optional<std::wstring>::operator=<std::wstring,0>(v147, v42);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v155);
      if ( !v38 )
      {
LABEL_133:
        if ( (unsigned int)RealtimeProtection::DlpUtils::DlpMpLookupMiscConfigFlag(
                             (RealtimeProtection::DlpUtils *)L"MpDlp_DebugCheckQuarantine",
                             v43) )
          DebugBreak();
        v119 = 0;
        v53 = a5 & 0x10;
        v124 = v53;
        v153[0] = (void *)((unsigned __int64)phNewToken[0] & -(__int64)(v53 != 0));
        *(_OWORD *)&v143[0].dwLowDateTime = 0;
        CommonUtil::CAutoImpersonateToken::CAutoImpersonateToken((CommonUtil::CAutoImpersonateToken *)v143, v153[0]);
        v54 = v149;
        if ( !v149 )
        {
          v157.m128i_i8[12] = 0;
          if ( !v146 )
            std::_Throw_bad_optional_access();
          FilterPath = RealtimeProtection::DlpPathCache::GetFilterPath(v128, szFileName, &v157);
          if ( *(_BYTE *)(FilterPath + 32) )
          {
            std::_Optional_construct_base<std::wstring>::_Assign<std::wstring>(v147, FilterPath);
          }
          else if ( v149 )
          {
            std::wstring::`scalar deleting destructor'(v147);
            v149 = 0;
          }
          std::optional<std::wstring>::~optional<std::wstring>(v128);
          v54 = v149;
          if ( !v149 )
          {
            v56 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v57 = szFileName;
              if ( v145 > 7 )
                v57 = *(WCHAR **)szFileName;
              v58 = 260;
LABEL_164:
              WPP_SF_S(v56[2], v58, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v57);
              goto LABEL_165;
            }
            goto LABEL_165;
          }
        }
        v59 = v146;
        if ( !v146 )
        {
          if ( !v54 )
            std::_Throw_bad_optional_access();
          if ( (unsigned __int8)Dlp::Utils::IsImDisk(v147, 0) )
          {
            v119 = 1;
            if ( !v149 )
              std::_Throw_bad_optional_access();
            DosPathW2K = RealtimeProtection::DlpPathCache::GetDosPathW2K(v128, v147);
          }
          else
          {
            if ( !v149 )
              std::_Throw_bad_optional_access();
            DosPathW2K = RealtimeProtection::DlpPathCache::GetDosPath(v128, v147);
          }
          if ( *(_BYTE *)(DosPathW2K + 32) )
          {
            std::_Optional_construct_base<std::wstring>::_Assign<std::wstring>(szFileName, DosPathW2K);
          }
          else if ( v146 )
          {
            std::wstring::`scalar deleting destructor'(szFileName);
            v146 = 0;
          }
          std::optional<std::wstring>::~optional<std::wstring>(v128);
          v59 = v146;
          if ( !v146 )
          {
            v56 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v57 = (WCHAR *)v147;
              if ( v148 > 7 )
                v57 = *(WCHAR **)v147;
              v58 = 261;
              goto LABEL_164;
            }
LABEL_165:
            if ( LOBYTE(v143[1].dwLowDateTime) )
              RevertToSelf();
            goto LABEL_370;
          }
          v54 = v149;
        }
        if ( LOBYTE(v143[1].dwLowDateTime) )
        {
          RevertToSelf();
          v59 = v146;
          v54 = v149;
        }
        if ( !v59 || !v54 )
          std::_Throw_bad_optional_access();
        v121 = 0;
        v61 = (const WCHAR *)lpString1;
        if ( v135 > 7 )
          v61 = lpString1[0];
        if ( CompareStringOrdinal(v61, -1, L"explorer.exe", -1, 1) == 2 )
        {
          v121 = RealtimeProtection::DlpProcessCache::CheckExclusionProtectionFileInfo(a3, v53 != 0, v147);
          if ( !v121 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                262,
                &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                a3[1].dwLowDateTime);
            goto LABEL_194;
          }
        }
        v63 = szFileName;
        if ( v145 > 7 )
          v63 = *(WCHAR **)szFileName;
        if ( !RealtimeProtection::DlpRtpPluginQuery::IsUnsavedDocumentPathIncluded(
                (RealtimeProtection::DlpRtpPluginQuery *)v63,
                v62) )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_194;
          v40 = 263;
          goto LABEL_191;
        }
        v65 = szFileName;
        if ( v145 > 7 )
          v65 = *(WCHAR **)szFileName;
        if ( RealtimeProtection::DlpRtpPluginQuery::IsUnsavedDocumentPathExcluded(
               (RealtimeProtection::DlpRtpPluginQuery *)v65,
               v64) )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_194;
          v40 = 264;
LABEL_191:
          v41 = szFileName;
          if ( v145 > 7 )
            v41 = *(WCHAR **)szFileName;
          goto LABEL_193;
        }
        *(_OWORD *)StringSid = 0;
        v151 = 0;
        v152 = 7;
        LOWORD(StringSid[0]) = 0;
        ClassificationUserSidString = RealtimeProtection::DlpUserSidCache::GetClassificationUserSidString(
                                        SessionId[3],
                                        a3,
                                        StringSid);
        v122 = ClassificationUserSidString;
        if ( ClassificationUserSidString < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              265,
              &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
              (unsigned int)ClassificationUserSidString);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(StringSid);
          goto LABEL_102;
        }
        if ( !v151 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              266,
              &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
              SessionId[3],
              a3[1].dwLowDateTime);
          goto LABEL_369;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v69 = StringSid;
          if ( v152 > 7 )
            LODWORD(v69) = StringSid[0];
          WPP_SF_SLL(*((_QWORD *)WPP_GLOBAL_Control + 2), v67, v68, (_DWORD)v69, SessionId[3], a3[1].dwLowDateTime);
        }
        std::optional<std::wstring>::operator=<std::wstring &,0>(v140, StringSid);
        memset(v198, 0, 0x10Eu);
        v123 = v53 != 0;
        LODWORD(hExistingToken[0]) = v123;
        LODWORD(hObject) = RealtimeProtection::DlpEngineUtils::GetEffectiveUnsavedDocumentEnforcementMode(
                             (unsigned int)hExistingToken,
                             (unsigned int)StringSid,
                             (unsigned int)szFileName,
                             (unsigned int)lpString1,
                             (__int64)a3,
                             SessionId[3],
                             (__int64)v198);
        if ( !(_DWORD)hObject && !v121 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v70 = StringSid;
            if ( v152 > 7 )
              v70 = (LPCWSTR *)StringSid[0];
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 268, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v70);
          }
          goto LABEL_216;
        }
        *(_QWORD *)v171 = 0;
        v172[32] = 0;
        v172[56] = 0;
        *(_QWORD *)FileSystemFlags = 0;
        RealtimeProtection::FileUniqueId::FileUniqueId((RealtimeProtection::FileUniqueId *)v174);
        v175[0] = 0;
        v175[1] = si128;
        LOWORD(v175[0]) = 0;
        v176 = 0;
        v177 = si128;
        LOWORD(v176) = 0;
        *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
        v179 = 0;
        v180 = si128;
        LOWORD(v179) = 0;
        v181 = 0;
        v182 = si128;
        LOWORD(v181) = 0;
        v183 = 0;
        v184 = si128;
        LOWORD(v183) = 0;
        v185 = 0;
        v186 = si128;
        LOWORD(v185) = 0;
        v187 = 0;
        v188 = si128;
        LOWORD(v187) = 0;
        v156 = 0;
        if ( v119 )
        {
          *(_OWORD *)&v143[0].dwLowDateTime = 0;
          v189[0] = 0;
          std::wstring::wstring(&v189[1], L"7357");
          std::wstring::wstring((char *)v191 + 8, L"7357");
          std::wstring::wstring((char *)v192 + 8, L"7357");
          std::wstring::wstring((char *)v193 + 8, L"ImDisk");
          std::wstring::wstring((char *)&v194 + 8, L"DeviceId");
          std::wstring::wstring(v196, L"SCSI\\DISK&VEN_MSFT&PROD_VIRTUAL_DISK\\5&32292CC9&0&000000");
          std::wstring::wstring(v197, L"HardwareId");
          v197[64] = 0;
          std::make_shared<EndpointDlp::Client::DeviceInformation,EndpointDlp::Client::DeviceInformation>(v143, v189);
          EndpointDlp::Client::DeviceInformation::~DeviceInformation((EndpointDlp::Client::DeviceInformation *)v189);
          if ( v156 )
          {
            std::shared_ptr<Dlp::TelemetryFilterManager::DlpTelemetryFilter>::operator=(v155, v143);
          }
          else
          {
            std::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore>::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore>(
              v155,
              v143);
            v156 = 1;
          }
          if ( v143[1] )
            std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v143[1]);
        }
        v71 = v147;
        if ( v148 > 7 )
          LODWORD(v71) = v147[0];
        v158 = 0;
        if ( v156 )
        {
          std::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore>::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore>(
            &v157,
            v155);
          v158 = 1;
        }
        v72 = Dlp::DeviceAttribute::DetermineAuthorizedGroupAttributes(
                (unsigned int)v128,
                (unsigned int)&v157,
                v123,
                (_DWORD)v71,
                SessionId[3]);
        Dlp::DeviceAttribute::AuthorizedGroupAttributes::operator=(v172, v72);
        Dlp::DeviceAttribute::AuthorizedGroupAttributes::~AuthorizedGroupAttributes((Dlp::DeviceAttribute::AuthorizedGroupAttributes *)v128);
        LODWORD(hExistingToken[0]) = 0;
        Dlp::DeviceAttribute::AuthorizedGroupAttributes::AuthorizedGroupAttributes(
          (Dlp::DeviceAttribute::AuthorizedGroupAttributes *)v128,
          (const struct Dlp::DeviceAttribute::AuthorizedGroupAttributes *)v172);
        v130 = 1;
        bIgnoreCasea = v147;
        v74 = RealtimeProtection::CRtpDlpEngine::DetermineMaxEnforcementLevelForAction(
                v73,
                v53 != 0,
                lpString1,
                StringSid);
        if ( v74 >= 0 )
        {
          v75 = (int)hExistingToken[0];
        }
        else
        {
          v75 = 0;
          v76 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          {
LABEL_237:
            if ( v156 )
              std::shared_ptr<EndpointDlp::Client::ApplicationSourceData>::`scalar deleting destructor'(v155);
            goto LABEL_239;
          }
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
LABEL_234:
            if ( v76 != &WPP_GLOBAL_Control && (*((_BYTE *)v76 + 28) & 4) != 0 )
              WPP_SF_S(v76[2], 270, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, a4);
            goto LABEL_237;
          }
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            269,
            (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            (_DWORD)a4,
            v74);
        }
        if ( !v75 )
        {
          v76 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_234;
        }
        if ( v156 )
          std::shared_ptr<EndpointDlp::Client::ApplicationSourceData>::`scalar deleting destructor'(v155);
        v168 = 0;
        *(_OWORD *)&v143[0].dwLowDateTime = 0;
        CommonUtil::CAutoImpersonateToken::CAutoImpersonateToken((CommonUtil::CAutoImpersonateToken *)v143, v153[0]);
        DlpFileUniqueId = Dlp::Utils::GetDlpFileUniqueId(v128, szFileName);
        if ( *(_BYTE *)(DlpFileUniqueId + 64) )
        {
          std::_Optional_construct_base<RealtimeProtection::FileUniqueId>::_Assign<RealtimeProtection::FileUniqueId>(
            v165,
            DlpFileUniqueId);
        }
        else if ( v168 )
        {
          RealtimeProtection::FileUniqueId::`scalar deleting destructor'((RealtimeProtection::FileUniqueId *)v165, v78);
          v168 = 0;
        }
        std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(v128);
        if ( !v168 || !v167 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 271, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, a4);
          if ( LOBYTE(v143[1].dwLowDateTime) )
            RevertToSelf();
          goto LABEL_368;
        }
        if ( LOBYTE(v143[1].dwLowDateTime) )
          RevertToSelf();
        v120 = Dlp::FeatureControl::GetFlag<enum Dlp::FeatureControl::UnsavedDocumentEnforcementFlags,void,void>(v79, 1);
        if ( !v168 )
          std::_Throw_bad_optional_access();
        v170 = 0;
        GetSystemTimeAsFileTime(SystemTimeAsFileTime);
        RealtimeProtection::FileUniqueId::operator=(v174, v165);
        LODWORD(hExistingToken[0]) = 0;
        QuarantineItemStatus = RealtimeProtection::DlpProcessCache::GetQuarantineItemStatus(
                                 (RealtimeProtection::DlpProcessCache *)v165,
                                 (const struct RealtimeProtection::FileUniqueId *)hExistingToken,
                                 v80);
        if ( QuarantineItemStatus == -2147023728 )
        {
          if ( v127 == 2
            && v120
            && (int)RealtimeProtection::DlpProcessCache::GetQuarantineFileIdFromFilePath(szFileName, v169) >= 0
            && v170 )
          {
            RealtimeProtection::DlpProcessCache::GetQuarantineItemStatus(
              (RealtimeProtection::DlpProcessCache *)v169,
              (const struct RealtimeProtection::FileUniqueId *)hExistingToken,
              v81);
          }
        }
        else if ( QuarantineItemStatus < 0 )
        {
          v82 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_263;
          v83 = 272;
LABEL_261:
          v84 = (unsigned int)QuarantineItemStatus;
LABEL_262:
          WPP_SF_d(v82[2], v83, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v84);
LABEL_263:
          std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(v169);
          std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(v165);
          RealtimeProtection::_DlpQuarantineItemInformation::~_DlpQuarantineItemInformation((RealtimeProtection::_DlpQuarantineItemInformation *)v171);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(StringSid);
LABEL_93:
          std::optional<std::wstring>::~optional<std::wstring>(v147);
          std::optional<std::wstring>::~optional<std::wstring>(szFileName);
          goto LABEL_29;
        }
        if ( LODWORD(hExistingToken[0]) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v85 = v166;
            if ( v166[3] > 7u )
              v85 = (_QWORD *)v166[0];
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              273,
              (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
              (_DWORD)a4,
              (__int64)v85);
          }
          v86 = (RealtimeProtection::DlpProcessCache *)v169;
          if ( !v170 )
            v86 = (RealtimeProtection::DlpProcessCache *)v165;
          ModifiedTime = RealtimeProtection::DlpProcessCache::SetQuarantineItemLastModifiedTime(
                           v86,
                           SystemTimeAsFileTime,
                           (const struct _FILETIME *)v81);
          QuarantineItemStatus = ModifiedTime;
          if ( ModifiedTime >= 0 )
          {
            std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(v169);
            std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(v165);
            RealtimeProtection::_DlpQuarantineItemInformation::~_DlpQuarantineItemInformation((RealtimeProtection::_DlpQuarantineItemInformation *)v171);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(StringSid);
            std::optional<std::wstring>::~optional<std::wstring>(v147);
            std::optional<std::wstring>::~optional<std::wstring>(szFileName);
            RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent::~DlpThrottleAnyAppEvent((RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent *)v159);
            QuarantineItemStatus = 0;
            goto LABEL_371;
          }
          v82 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_263;
          v83 = 274;
          v84 = (unsigned int)ModifiedTime;
          goto LABEL_262;
        }
        Value = Dlp::FeatureControl::GetValue(v124 != 0 ? 226LL : 172LL);
        v90 = 0;
        if ( !v121 )
          v90 = Value;
        if ( v90 )
        {
          v143[0] = 0;
          AddressOfGetSystemTimePreciseAsFileTime();
          v157.m128i_i8[8] = 0;
          *(_OWORD *)hExistingToken = 0;
          CommonUtil::CAutoImpersonateToken::CAutoImpersonateToken(
            (CommonUtil::CAutoImpersonateToken *)hExistingToken,
            v153[0]);
          v157 = *(__m128i *)Dlp::Utils::GetFileCreationTime(v153, szFileName);
          if ( !(unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v157, 8)) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 275, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, a4);
            if ( LOBYTE(hExistingToken[1]) )
              RevertToSelf();
            std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(v169);
LABEL_368:
            std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(v165);
            RealtimeProtection::_DlpQuarantineItemInformation::~_DlpQuarantineItemInformation((RealtimeProtection::_DlpQuarantineItemInformation *)v171);
LABEL_369:
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(StringSid);
LABEL_370:
            std::optional<std::wstring>::~optional<std::wstring>(v147);
            std::optional<std::wstring>::~optional<std::wstring>(szFileName);
            RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent::~DlpThrottleAnyAppEvent((RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent *)v159);
            QuarantineItemStatus = -2147467259;
            goto LABEL_371;
          }
          if ( LOBYTE(hExistingToken[1]) )
            RevertToSelf();
          v91 = (CommonUtil *)std::optional<web::json::value>::value(&v157);
          v153[0] = (void *)CommonUtil::UtilFileTimeFromUlong64(v91, v92);
          if ( (int)RealtimeProtection::DlpUtils::CompareFileTimeByMs(
                      (RealtimeProtection::DlpUtils *)v153,
                      v143,
                      (const struct _FILETIME *)(1000LL * v90),
                      v93) < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 276, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, a4);
            goto LABEL_293;
          }
        }
        if ( (int)RealtimeProtection::DlpProcessCache::GetDlpDelegationFlag(a3, (const struct PPID *)&v132, v89) < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            277,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            a3[1].dwLowDateTime);
        }
        if ( (unsigned __int8)Dlp::FeatureControl::GetBoolValue(166, v94) )
        {
          *(_OWORD *)v153 = 0;
          v154 = si128;
          LOWORD(v153[0]) = 0;
          AppNameFromAppDelegationCache = RealtimeProtection::DlpProcessCache::GetAppNameFromAppDelegationCache(
                                            a3,
                                            v153);
          if ( AppNameFromAppDelegationCache >= 0 )
          {
            std::optional<std::wstring>::operator=<std::wstring &,0>(v139, v153);
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              278,
              &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
              a3[1].dwLowDateTime,
              AppNameFromAppDelegationCache);
          }
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v153);
        }
        std::wstring::operator=(&v136, lpString1);
        v96 = std::wstring::rfind(lpString1, 46, -1);
        if ( v96 != -1 && v96 )
        {
          v98 = std::wstring::substr(lpString1, v153, 0, v96);
          std::wstring::operator=(lpString1, v98);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v153);
        }
        v99 = (const WCHAR *)StringSid;
        if ( v152 > 7 )
          v99 = StringSid[0];
        if ( Block )
        {
          operator delete(Block);
          Block = 0;
        }
        QuarantineItemStatus = CommonUtil::UtilConvertStringSidToSid((CommonUtil *)&Block, v99, v97);
        if ( QuarantineItemStatus < 0 )
        {
          v82 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_263;
          v83 = 279;
          goto LABEL_261;
        }
        if ( !phNewToken[0] )
        {
          hExistingToken[0] = 0;
          PrimaryToken = RealtimeProtection::DlpUserSidCache::GetPrimaryToken(
                           SessionId[3],
                           (unsigned int)a3,
                           (const struct PPID *)hExistingToken,
                           v100);
          QuarantineItemStatus = PrimaryToken;
          if ( PrimaryToken < 0 )
          {
            v102 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_322;
            v103 = 280;
LABEL_321:
            WPP_SF_d(v102[2], v103, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, (unsigned int)PrimaryToken);
LABEL_322:
            CommonUtil::CAutoUniqueWinHandle<CommonUtil::CAutoWinProcessTag,CommonUtil::DefaultNullPolicy<void *>>::~CAutoUniqueWinHandle<CommonUtil::CAutoWinProcessTag,CommonUtil::DefaultNullPolicy<void *>>(hExistingToken);
            goto LABEL_263;
          }
          if ( phNewToken[0] )
          {
            CloseHandle(phNewToken[0]);
            phNewToken[0] = 0;
          }
          PrimaryToken = CommonUtil::UtilDuplicateToken(
                           phNewToken,
                           hExistingToken[0],
                           SecurityImpersonation,
                           0xCu,
                           (unsigned int)bIgnoreCasea);
          QuarantineItemStatus = PrimaryToken;
          if ( PrimaryToken < 0 )
          {
            v102 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_322;
            v103 = 281;
            goto LABEL_321;
          }
          CommonUtil::CAutoUniqueWinHandle<CommonUtil::CAutoWinProcessTag,CommonUtil::DefaultNullPolicy<void *>>::~CAutoUniqueWinHandle<CommonUtil::CAutoWinProcessTag,CommonUtil::DefaultNullPolicy<void *>>(hExistingToken);
        }
        v104 = Dlp::FeatureControl::GetValue(171);
        if ( v104 )
          SystemTimeAsFileTime[1] = (struct _FILETIME)(1000LL * v104);
        if ( (int)Dlp::Utils::GetVolumeFileSystemFlags(szFileName, FileSystemFlags) < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 282, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, a4);
        }
        v105 = std::filesystem::path::path(v153, szFileName);
        std::filesystem::path::operator=(&v176, v105);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v153);
        v106 = std::filesystem::path::path(v153, v147);
        std::filesystem::path::operator=(v175, v106);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v153);
        *(_WORD *)((char *)v171 + 3) = 0;
        BYTE2(v171[1]) = 0;
        v107 = 0;
        if ( v127 == 2 && v120 )
          v107 = 3;
        if ( (_DWORD)hObject != 1 )
        {
          *(_OWORD *)v189 = 0;
          v190 = si128;
          LOWORD(v189[0]) = 0;
          v191[0] = 0;
          v191[1] = si128;
          LOWORD(v191[0]) = 0;
          v192[0] = 0;
          v192[1] = si128;
          LOWORD(v192[0]) = 0;
          v193[0] = 0;
          v193[1] = si128;
          LOWORD(v193[0]) = 0;
          v194 = 0;
          v195 = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v113 = lpString1;
            if ( v135 > 7 )
              v113 = (LPCWCH *)lpString1[0];
            v114 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v166);
            std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(szFileName);
            WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v114, (__int64)v113);
          }
          v115 = v124 != 0;
          v124 = -v124;
          v116 = RealtimeProtection::DlpProcessCache::AddQuarantineFileByProtectionStatus(
                   (unsigned int)v115 + 2,
                   4,
                   (int)v171,
                   (__int64)SessionId,
                   (__int64)v189,
                   v159,
                   v107);
          QuarantineItemStatus = v116;
          if ( v116 >= 0 )
          {
            RealtimeProtection::_DlpQuarantinePolicyInformation::~_DlpQuarantinePolicyInformation((RealtimeProtection::_DlpQuarantinePolicyInformation *)v189);
            std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(v169);
            std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(v165);
            RealtimeProtection::_DlpQuarantineItemInformation::~_DlpQuarantineItemInformation((RealtimeProtection::_DlpQuarantineItemInformation *)v171);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(StringSid);
            std::optional<std::wstring>::~optional<std::wstring>(v147);
            std::optional<std::wstring>::~optional<std::wstring>(szFileName);
            RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent::~DlpThrottleAnyAppEvent((RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent *)v159);
            RealtimeProtection::_DlpQuarantineProcessInfo::~_DlpQuarantineProcessInfo((RealtimeProtection::_DlpQuarantineProcessInfo *)SessionId);
            return 0;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              285,
              &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
              (unsigned int)v116);
          RealtimeProtection::_DlpQuarantinePolicyInformation::~_DlpQuarantinePolicyInformation((RealtimeProtection::_DlpQuarantinePolicyInformation *)v189);
          goto LABEL_263;
        }
        v108 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v109 = StringSid;
          if ( v152 > 7 )
            v109 = (LPCWSTR *)StringSid[0];
          v110 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(szFileName);
          WPP_SF_SS(v108[2], 283, (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v110, (__int64)v109);
        }
        *(_OWORD *)v153 = 0;
        v154.m128i_i64[0] = 0;
        v129 = 0;
        v111 = lpString1;
        if ( v135 > 7 )
          v111 = (LPCWCH *)lpString1[0];
        v112 = &v176;
        if ( v177.m128i_i64[1] > 7uLL )
          v112 = (__int128 *)v176;
        RealtimeProtection::DlpEngineTelemetry::GenerateDlpTelemetryEvent(
          (unsigned int)v153,
          (unsigned int)&v198[122],
          (unsigned int)v198,
          4,
          v123,
          0,
          (__int64)L"(UnsavedDocument)",
          (__int64)v112,
          (__int64)v111,
          (__int64)SessionId,
          SessionId[3],
          0,
          0,
          0,
          0,
          0,
          (__int64)v128,
          0,
          (__int64)&qword_18025C818,
          (__int64)&qword_18025C818,
          1,
          (__int64)&qword_18025C818,
          0,
          (__int64)&qword_18025C818,
          (__int64)&qword_18025C818,
          0);
        if ( v129 )
          std::string::`scalar deleting destructor'(v128);
        RealtimeProtection::DlpEngineTelemetry::SendDlpTelemetryEvent(v153);
        std::vector<RealtimeProtection::DlpEngineTelemetry::DlpTelemetryEvent>::_Tidy(v153);
LABEL_293:
        std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(v169);
        std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(v165);
LABEL_239:
        RealtimeProtection::_DlpQuarantineItemInformation::~_DlpQuarantineItemInformation((RealtimeProtection::_DlpQuarantineItemInformation *)v171);
LABEL_216:
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(StringSid);
        goto LABEL_194;
      }
      hObject = 0;
      v45 = RealtimeProtection::DlpUserSidCache::GetPrimaryToken(
              SessionId[3],
              (unsigned int)a3,
              (const struct PPID *)&hObject,
              v44);
      QuarantineItemStatus = v45;
      if ( v45 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            254,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            (unsigned int)v45);
LABEL_91:
        if ( hObject )
          CloseHandle(hObject);
        goto LABEL_93;
      }
      if ( phNewToken[0] )
      {
        CloseHandle(phNewToken[0]);
        phNewToken[0] = 0;
      }
      v46 = hObject;
      v47 = CommonUtil::UtilDuplicateToken(phNewToken, hObject, SecurityImpersonation, 0xCu, bIgnoreCase);
      v122 = v47;
      if ( v47 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            255,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            (unsigned int)v47);
LABEL_100:
        if ( v46 )
          CloseHandle(v46);
LABEL_102:
        std::optional<std::wstring>::~optional<std::wstring>(v147);
        std::optional<std::wstring>::~optional<std::wstring>(szFileName);
        RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent::~DlpThrottleAnyAppEvent((RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent *)v159);
        QuarantineItemStatus = v122;
        goto LABEL_371;
      }
    }
    else
    {
      v48 = std::wstring::wstring(v155, a4);
      std::optional<std::wstring>::operator=<std::wstring,0>(szFileName, v48);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v155);
      hObject = 0;
      v50 = RealtimeProtection::DlpUserSidCache::GetPrimaryToken(
              SessionId[3],
              (unsigned int)a3,
              (const struct PPID *)&hObject,
              v49);
      QuarantineItemStatus = v50;
      if ( v50 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            256,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            (unsigned int)v50);
        goto LABEL_91;
      }
      if ( phNewToken[0] )
      {
        CloseHandle(phNewToken[0]);
        phNewToken[0] = 0;
      }
      v46 = hObject;
      v51 = CommonUtil::UtilDuplicateToken(phNewToken, hObject, SecurityImpersonation, 0xCu, bIgnoreCase);
      v122 = v51;
      if ( v51 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            257,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            (unsigned int)v51);
        goto LABEL_100;
      }
      *(_OWORD *)&v143[0].dwLowDateTime = 0;
      CommonUtil::CAutoImpersonateToken::CAutoImpersonateToken((CommonUtil::CAutoImpersonateToken *)v143, phNewToken[0]);
      if ( !v146 )
        std::_Throw_bad_optional_access();
      VolumeDeviceCharacteristics = Dlp::Utils::GetVolumeDeviceCharacteristics(szFileName, &a5);
      v122 = VolumeDeviceCharacteristics;
      v43 = 0;
      if ( VolumeDeviceCharacteristics < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            258,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            (unsigned int)VolumeDeviceCharacteristics);
        if ( LOBYTE(v143[1].dwLowDateTime) )
          RevertToSelf();
        goto LABEL_100;
      }
      if ( LOBYTE(v143[1].dwLowDateTime) )
        RevertToSelf();
      if ( (a5 & 0x805) == 0 && (a5 & 0x10) == 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 259, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, a4);
        if ( v46 )
          CloseHandle(v46);
        goto LABEL_194;
      }
    }
    if ( v46 )
      CloseHandle(v46);
    goto LABEL_133;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18009d7b0  mov     rax, rsp
0x18009d7b3  mov     [rax+10h], rbx
0x18009d7b7  push    rbp
0x18009d7b8  push    rsi
0x18009d7b9  push    rdi
0x18009d7ba  push    r12
0x18009d7bc  push    r13
0x18009d7be  push    r14
0x18009d7c0  push    r15
0x18009d7c2  lea     rbp, [rax-6A8h]
0x18009d7c9  sub     rsp, 7C0h
0x18009d7d0  movaps  xmmword ptr [rax-48h], xmm6
0x18009d7d4  mov     rax, cs:__security_cookie
0x18009d7db  xor     rax, rsp
0x18009d7de  mov     [rbp+6A0h+var_50], rax
0x18009d7e5  mov     r13, r9
0x18009d7e8  mov     rdi, r8
0x18009d7eb  mov     esi, edx
0x18009d7ed  mov     [rbp+6A0h+var_6F8], edx
0x18009d7f0  mov     qword ptr [rbp+6A0h+var_5E0.dwLowDateTime], rcx
0x18009d7f7  xor     r15d, r15d
0x18009d7fa  test    r9, r9
0x18009d7fd  jnz     short loc_18009D83B
0x18009d7ff  lea     r14, WPP_GLOBAL_Control
0x18009d806  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d80d  cmp     rcx, r14
0x18009d810  jz      short loc_18009D831
0x18009d812  lea     r15d, [r9+1]
0x18009d816  test    [rcx+1Ch], r15b
0x18009d81a  jz      short loc_18009D831
0x18009d81c  mov     edx, 0EDh
0x18009d821  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18009d828  mov     rcx, [rcx+10h]
0x18009d82c  call    WPP_SF_
0x18009d831  mov     eax, 80070057h
0x18009d836  jmp     loc_18009F425
0x18009d83b  lea     r14, WPP_GLOBAL_Control
0x18009d842  mov     eax, [rbp+6A0h+arg_20]
0x18009d848  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d84f  cmp     rcx, r14
0x18009d852  jz      short loc_18009D873
0x18009d854  test    byte ptr [rcx+1Ch], 4
0x18009d858  jz      short loc_18009D873
0x18009d85a  mov     [rsp+7F0h+var_7C0], esi
0x18009d85e  mov     dword ptr [rsp+7F0h+var_7C8], eax
0x18009d862  mov     eax, [r8+8]
0x18009d866  mov     [rsp+7F0h+bIgnoreCase], eax; unsigned int
0x18009d86a  mov     rcx, [rcx+10h]
0x18009d86e  call    WPP_SF_SLDd
0x18009d873  xor     eax, eax
0x18009d875  xorps   xmm0, xmm0
0x18009d878  movups  xmmword ptr [rbp+6A0h+SessionId], xmm0
0x18009d87c  mov     [rbp+6A0h+var_690], rax
0x18009d880  movups  xmmword ptr [rbp+6A0h+lpString1], xmm0
0x18009d884  mov     [rbp+6A0h+var_678], r15
0x18009d888  mov     eax, 7
0x18009d88d  mov     [rbp+6A0h+var_670], rax
0x18009d891  mov     word ptr [rbp+6A0h+lpString1], r15w
0x18009d896  movups  [rbp+6A0h+var_668], xmm0
0x18009d89a  mov     [rbp+6A0h+var_658], r15
0x18009d89e  mov     [rbp+6A0h+var_650], rax
0x18009d8a2  mov     word ptr [rbp+6A0h+var_668], r15w
0x18009d8a7  mov     [rbp+6A0h+var_628], r15b
0x18009d8ab  mov     [rbp+6A0h+var_600], r15b
0x18009d8b2  mov     [rbp+6A0h+Block], r15
0x18009d8b9  mov     [rbp+6A0h+phNewToken], r15
0x18009d8c0  movsd   xmm0, qword ptr [rdi]
0x18009d8c4  movsd   qword ptr [rbp+6A0h+SessionId], xmm0
0x18009d8c9  mov     eax, [rdi+8]
0x18009d8cc  mov     [rbp+6A0h+SessionId+8], eax
0x18009d8cf  lea     rdx, [rbp+6A0h+SessionId+0Ch]; struct PPID *
0x18009d8d3  mov     rcx, rdi; this
0x18009d8d6  call    ?GetSessionId@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@AEAK@Z; RealtimeProtection::DlpProcessCache::GetSessionId(PPID const &,ulong &)
0x18009d8db  mov     ebx, eax
0x18009d8dd  test    eax, eax
0x18009d8df  jns     short loc_18009D91E
0x18009d8e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d8e8  cmp     rcx, r14
0x18009d8eb  jz      loc_18009F3C9
0x18009d8f1  mov     r15d, 1
0x18009d8f7  test    [rcx+1Ch], r15b
0x18009d8fb  jz      loc_18009F3C9
0x18009d901  mov     edx, 0EFh
0x18009d906  mov     r9d, eax
0x18009d909  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18009d910  mov     rcx, [rcx+10h]
0x18009d914  call    WPP_SF_d
0x18009d919  jmp     loc_18009F3C9
0x18009d91e  cmp     [rbp+6A0h+SessionId+0Ch], r15d
0x18009d922  jnz     short loc_18009D957
0x18009d924  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d92b  cmp     rcx, r14
0x18009d92e  jz      short loc_18009D9A8
0x18009d930  mov     r12d, 2
0x18009d936  test    [rcx+1Ch], r12b
0x18009d93a  jz      short loc_18009D9A8
0x18009d93c  mov     edx, 0F0h
0x18009d941  mov     r9d, [rdi+8]
0x18009d945  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18009d94c  mov     rcx, [rcx+10h]
0x18009d950  call    WPP_SF_d
0x18009d955  jmp     short loc_18009D9A8
0x18009d957  mov     r12d, 2
0x18009d95d  cmp     esi, r12d
0x18009d960  jnz     short loc_18009D9B2
0x18009d962  mov     edx, r12d
0x18009d965  call    ??$GetFlag@W4UnsavedDocumentEnforcementFlags@FeatureControl@Dlp@@XX@FeatureControl@Dlp@@YA_NW4FeatureControlEnum@@W4UnsavedDocumentEnforcementFlags@01@@Z; Dlp::FeatureControl::GetFlag<Dlp::FeatureControl::UnsavedDocumentEnforcementFlags,void,void>(FeatureControlEnum,Dlp::FeatureControl::UnsavedDocumentEnforcementFlags)
0x18009d96a  mov     bl, al
0x18009d96c  lea     edx, [r12+2]
0x18009d971  call    ??$GetFlag@W4UnsavedDocumentEnforcementFlags@FeatureControl@Dlp@@XX@FeatureControl@Dlp@@YA_NW4FeatureControlEnum@@W4UnsavedDocumentEnforcementFlags@01@@Z; Dlp::FeatureControl::GetFlag<Dlp::FeatureControl::UnsavedDocumentEnforcementFlags,void,void>(FeatureControlEnum,Dlp::FeatureControl::UnsavedDocumentEnforcementFlags)
0x18009d976  test    bl, bl
0x18009d978  jz      short loc_18009D9B2
0x18009d97a  test    al, al
0x18009d97c  jz      short loc_18009D9B2
0x18009d97e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d985  cmp     rcx, r14
0x18009d988  jz      short loc_18009D9A8
0x18009d98a  test    byte ptr [rcx+1Ch], 4
0x18009d98e  jz      short loc_18009D9A8
0x18009d990  mov     edx, 0F1h
0x18009d995  mov     r9, r13
0x18009d998  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18009d99f  mov     rcx, [rcx+10h]
0x18009d9a3  call    WPP_SF_S
0x18009d9a8  mov     ebx, 1
0x18009d9ad  jmp     loc_18009F3C9
0x18009d9b2  xorps   xmm0, xmm0
0x18009d9b5  movups  [rbp+6A0h+var_500], xmm0
0x18009d9bc  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18009d9c4  movdqa  [rbp+6A0h+var_4F0], xmm6
0x18009d9cc  mov     word ptr [rbp+6A0h+var_500], r15w
0x18009d9d4  movups  [rbp+6A0h+var_4E0], xmm0
0x18009d9db  movdqa  [rbp+6A0h+var_4D0], xmm6
0x18009d9e3  mov     word ptr [rbp+6A0h+var_4E0], r15w
0x18009d9eb  movups  [rbp+6A0h+var_4C0], xmm0
0x18009d9f2  movdqa  [rbp+6A0h+var_4B0], xmm6
0x18009d9fa  mov     word ptr [rbp+6A0h+var_4C0], r15w
0x18009da02  xor     eax, eax
0x18009da04  mov     [rbp+6A0h+var_4A0], rax
0x18009da0b  lea     rcx, [rbp+6A0h+var_500]; this
0x18009da12  call    ?ReadQuarantineConfig@DlpEngineUtils@RealtimeProtection@@YAJAEAU_QuarantineParams@2@@Z; RealtimeProtection::DlpEngineUtils::ReadQuarantineConfig(RealtimeProtection::_QuarantineParams &)
0x18009da17  mov     ebx, eax
0x18009da19  test    eax, eax
0x18009da1b  jns     short loc_18009DA5F
0x18009da1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009da24  cmp     rcx, r14
0x18009da27  jz      short loc_18009DA4E
0x18009da29  mov     r15d, 1
0x18009da2f  test    [rcx+1Ch], r15b
0x18009da33  jz      short loc_18009DA4E
0x18009da35  mov     edx, 0F2h
0x18009da3a  mov     r9d, eax
0x18009da3d  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18009da44  mov     rcx, [rcx+10h]
0x18009da48  call    WPP_SF_d
0x18009da4d  nop
0x18009da4e  lea     rcx, [rbp+6A0h+var_500]; this
0x18009da55  call    ??1DlpThrottleAnyAppEvent@DlpThrottle@RealtimeProtection@@QEAA@XZ; RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent::~DlpThrottleAnyAppEvent(void)
0x18009da5a  jmp     loc_18009F3C9
0x18009da5f  mov     sil, byte ptr [rbp+6A0h+var_4A0]
0x18009da66  mov     cl, sil; this
0x18009da69  call    ?SetQuarantineEngineStatus@DlpProcessCache@RealtimeProtection@@YAJ_N@Z; RealtimeProtection::DlpProcessCache::SetQuarantineEngineStatus(bool)
0x18009da6e  mov     ebx, eax
0x18009da70  test    eax, eax
0x18009da72  jns     short loc_18009DA93
0x18009da74  mov     rcx, cs:WPP_GLOBAL_Control
0x18009da7b  cmp     rcx, r14
0x18009da7e  jz      short loc_18009DA4E
0x18009da80  mov     r15d, 1
0x18009da86  test    [rcx+1Ch], r15b
0x18009da8a  jz      short loc_18009DA4E
0x18009da8c  mov     edx, 0F3h
0x18009da91  jmp     short loc_18009DA3A
0x18009da93  mov     r15d, 1
0x18009da99  mov     edx, r15d
0x18009da9c  call    ??$GetFlag@W4QuarantineSettingFlags@FeatureControl@Dlp@@XX@FeatureControl@Dlp@@YA_NW4FeatureControlEnum@@W4QuarantineSettingFlags@01@@Z; Dlp::FeatureControl::GetFlag<Dlp::FeatureControl::QuarantineSettingFlags,void,void>(FeatureControlEnum,Dlp::FeatureControl::QuarantineSettingFlags)
0x18009daa1  xor     ebx, ebx
0x18009daa3  test    sil, sil
0x18009daa6  jz      loc_18009F3D6
0x18009daac  test    al, al
0x18009daae  jz      loc_18009F3D6
0x18009dab4  mov     rcx, qword ptr [rbp+6A0h+var_5E0.dwLowDateTime]
0x18009dabb  mov     [rcx+5Fh], r15b
0x18009dabf  lea     edx, [rbx+8]
0x18009dac2  call    ??$GetFlag@W4QuarantineSettingFlags@FeatureControl@Dlp@@XX@FeatureControl@Dlp@@YA_NW4FeatureControlEnum@@W4QuarantineSettingFlags@01@@Z; Dlp::FeatureControl::GetFlag<Dlp::FeatureControl::QuarantineSettingFlags,void,void>(FeatureControlEnum,Dlp::FeatureControl::QuarantineSettingFlags)
0x18009dac7  test    al, al
0x18009dac9  jnz     short loc_18009DAEC
0x18009dacb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dad2  cmp     rcx, r14
0x18009dad5  jz      loc_18009F40C
0x18009dadb  test    byte ptr [rcx+1Ch], 10h
0x18009dadf  jz      loc_18009F40C
0x18009dae5  mov     edx, 0F5h
0x18009daea  jmp     short loc_18009DB17
0x18009daec  mov     edx, r12d
0x18009daef  call    ??$GetFlag@W4QuarantineSettingFlags@FeatureControl@Dlp@@XX@FeatureControl@Dlp@@YA_NW4FeatureControlEnum@@W4QuarantineSettingFlags@01@@Z; Dlp::FeatureControl::GetFlag<Dlp::FeatureControl::QuarantineSettingFlags,void,void>(FeatureControlEnum,Dlp::FeatureControl::QuarantineSettingFlags)
0x18009daf4  test    al, al
0x18009daf6  jnz     short loc_18009DB2C
0x18009daf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009daff  cmp     rcx, r14
0x18009db02  jz      loc_18009F40C
0x18009db08  test    byte ptr [rcx+1Ch], 10h
0x18009db0c  jz      loc_18009F40C
0x18009db12  mov     edx, 0F6h
0x18009db17  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18009db1e  mov     rcx, [rcx+10h]
0x18009db22  call    WPP_SF_
0x18009db27  jmp     loc_18009F40C
0x18009db2c  mov     [rbp+6A0h+var_718], ebx
0x18009db2f  movsd   xmm0, qword ptr [rdi]
0x18009db33  movsd   qword ptr [rbp+6A0h+var_5E0.dwLowDateTime], xmm0
0x18009db3b  mov     eax, [rdi+8]
0x18009db3e  mov     [rbp+6A0h+var_5E0.dwLowDateTime+8], eax
0x18009db44  lea     rdx, [rbp+6A0h+var_718]
0x18009db48  lea     rcx, [rbp+6A0h+var_5E0]
0x18009db4f  call    ?GetKnownProcessType@DlpProcessCache@RealtimeProtection@@YAJUPPID@@AEAW4_MP_KNOWN_PROCESS_TYPE@@@Z; RealtimeProtection::DlpProcessCache::GetKnownProcessType(PPID,_MP_KNOWN_PROCESS_TYPE &)
0x18009db54  mov     ebx, eax
0x18009db56  test    eax, eax
0x18009db58  jns     short loc_18009DB7E
0x18009db5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009db61  cmp     rcx, r14
0x18009db64  jz      loc_18009DA4E
0x18009db6a  test    [rcx+1Ch], r15b
0x18009db6e  jz      loc_18009DA4E
0x18009db74  mov     edx, 0F7h
0x18009db79  jmp     loc_18009DA3A
0x18009db7e  lea     rdx, [rbp+6A0h+lpString1]
0x18009db82  mov     rcx, rdi
0x18009db85  call    ?GetApplicationName@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RealtimeProtection::DlpProcessCache::GetApplicationName(PPID const &,std::wstring &)
0x18009db8a  lea     rsi, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18009db91  xor     ebx, ebx
0x18009db93  test    eax, eax
0x18009db95  jns     loc_18009DC51
0x18009db9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dba2  cmp     rcx, r14
0x18009dba5  jz      short loc_18009DBC2
0x18009dba7  test    [rcx+1Ch], r12b
0x18009dbab  jz      short loc_18009DBC2
0x18009dbad  mov     edx, 0F8h
0x18009dbb2  mov     r9d, [rdi+8]
0x18009dbb6  mov     r8, rsi
0x18009dbb9  mov     rcx, [rcx+10h]
0x18009dbbd  call    WPP_SF_d
0x18009dbc2  lea     rdx, [rbp+6A0h+lpString1]
0x18009dbc6  mov     ecx, [rdi+8]; void **
0x18009dbc9  call    ?GetProcessImageName@Utils@Dlp@@YAJKAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Dlp::Utils::GetProcessImageName(ulong,std::wstring &)
0x18009dbce  test    eax, eax
0x18009dbd0  js      short loc_18009DC1A
0x18009dbd2  lea     rdx, SubBlock; "\\"
0x18009dbd9  lea     rcx, [rbp+6A0h+lpString1]
0x18009dbdd  call    ?find_last_of@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KQEB_W_K@Z; std::wstring::find_last_of(wchar_t const * const,unsigned __int64)
0x18009dbe2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009dbe6  jz      short loc_18009DC51
0x18009dbe8  lea     r8, [rax+1]
0x18009dbec  or      r9, 0FFFFFFFFFFFFFFFFh
0x18009dbf0  lea     rdx, [rbp+6A0h+var_540]
0x18009dbf7  lea     rcx, [rbp+6A0h+lpString1]
0x18009dbfb  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18009dc00  mov     rdx, rax
0x18009dc03  lea     rcx, [rbp+6A0h+lpString1]
0x18009dc07  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009dc0c  lea     rcx, [rbp+6A0h+var_540]; void *
0x18009dc13  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18009dc18  jmp     short loc_18009DC51
0x18009dc1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dc21  cmp     rcx, r14
0x18009dc24  jz      short loc_18009DC41
0x18009dc26  test    [rcx+1Ch], r12b
0x18009dc2a  jz      short loc_18009DC41
0x18009dc2c  mov     edx, 0F9h
0x18009dc31  mov     r9d, [rdi+8]
0x18009dc35  mov     r8, rsi
0x18009dc38  mov     rcx, [rcx+10h]
0x18009dc3c  call    WPP_SF_d
0x18009dc41  lea     rdx, aUnknown_1; "Unknown"
0x18009dc48  lea     rcx, [rbp+6A0h+lpString1]; void *
0x18009dc4c  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18009dc51  lea     rcx, [rbp+6A0h+lpString1]
0x18009dc55  cmp     [rbp+6A0h+var_670], 7
0x18009dc5a  cmova   rcx, [rbp+6A0h+lpString1]; this
0x18009dc5f  call    ?IsUnsavedDocumentProcessIncluded@DlpRtpPluginQuery@RealtimeProtection@@YA_NPEB_W@Z; RealtimeProtection::DlpRtpPluginQuery::IsUnsavedDocumentProcessIncluded(wchar_t const *)
0x18009dc64  test    al, al
0x18009dc66  jnz     short loc_18009DC89
0x18009dc68  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dc6f  cmp     rcx, r14
0x18009dc72  jz      loc_18009F40C
0x18009dc78  test    byte ptr [rcx+1Ch], 4
0x18009dc7c  jz      loc_18009F40C
0x18009dc82  mov     edx, 0FAh
0x18009dc87  jmp     short loc_18009DCBF
0x18009dc89  lea     rcx, [rbp+6A0h+lpString1]
0x18009dc8d  cmp     [rbp+6A0h+var_670], 7
0x18009dc92  cmova   rcx, [rbp+6A0h+lpString1]; this
0x18009dc97  call    ?IsUnsavedDocumentProcessExcluded@DlpRtpPluginQuery@RealtimeProtection@@YA_NPEB_W@Z; RealtimeProtection::DlpRtpPluginQuery::IsUnsavedDocumentProcessExcluded(wchar_t const *)
0x18009dc9c  test    al, al
0x18009dc9e  jz      short loc_18009DCDE
0x18009dca0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dca7  cmp     rcx, r14
0x18009dcaa  jz      loc_18009F40C
0x18009dcb0  test    byte ptr [rcx+1Ch], 4
  ... truncated ...
```
