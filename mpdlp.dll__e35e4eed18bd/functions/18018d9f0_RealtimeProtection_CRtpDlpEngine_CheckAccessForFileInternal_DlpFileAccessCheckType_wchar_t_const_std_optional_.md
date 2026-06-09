# RealtimeProtection::CRtpDlpEngine::CheckAccessForFileInternal(DlpFileAccessCheckType,wchar_t const *,std::optional<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> const &,wchar_t const *,wchar_t const *,PPID const &,_MP_KNOWN_PROCESS_TYPE,std::optional<RealtimeProtection::FileUniqueId> const &,ulong,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,MpDlpResultAccessDecision *,MpDlpResultAccessReason *)

- ea: `0x18018d9f0`
- end: `0x1801920b2`
- name: `?CheckAccessForFileInternal@CRtpDlpEngine@RealtimeProtection@@AEAAJW4DlpFileAccessCheckType@@PEB_WAEBV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@11AEBUPPID@@W4_MP_KNOWN_PROCESS_TYPE@@AEBV?$optional@VFileUniqueId@RealtimeProtection@@@5@KKPEAEK6K6KPEAW4MpDlpResultAccessDecision@@PEAW4MpDlpResultAccessReason@@@Z`
- size: `18114`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, wchar_t *String1, FILETIME *lpFileTime1, int, __int64, int, rsize_t SourceSize, __int64, int, __int64, int, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `150`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800538c4`

## callees

- `0x18001b9a0`
- `0x18001bad0`
- `0x18001bc6c`
- `0x18001bc88`
- `0x18001e348`
- `0x18002082c`
- `0x1800249f0`
- `0x180026360`
- `0x180026460`
- `0x180026c70`
- `0x180027a90`
- `0x180028a10`
- `0x180028d80`
- `0x180029560`
- `0x180029590`
- `0x1800297d0`
- `0x180029cf0`
- `0x18002b050`
- `0x18002c150`
- `0x18002d608`
- `0x18002e484`
- `0x18002ece0`
- `0x18002f970`
- `0x180033eb0`
- `0x180034420`
- `0x180038450`
- `0x1800398a0`
- `0x18003e644`
- `0x18003ea30`
- `0x18003eb14`
- `0x18003f0a8`
- `0x18003f870`
- `0x18003fa60`
- `0x18003fb10`
- `0x180040920`
- `0x180040d60`
- `0x180042594`
- `0x180042a8c`
- `0x180042c98`
- `0x180044eb0`
- `0x180046354`
- `0x1800463b8`
- `0x1800489dc`
- `0x180048e20`
- `0x180049b34`
- `0x18004ca00`
- `0x18004e000`
- `0x18004f370`
- `0x1800542e8`
- `0x180054320`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x18018dcfc`
- `MpClient!MpFreeMemory` at `0x18018dd8a`
- `MpClient!MpFreeMemory` at `0x18018dcfc`
- `MpClient!MpFreeMemory` at `0x18018dd8a`
- `MpClient!MpClientUtilExportFunctions` at `0x18018dca2`
- `MpClient!MpClientUtilExportFunctions` at `0x18018dca2`
- `KERNEL32!AcquireSRWLockShared` at `0x18018db48`
- `KERNEL32!AcquireSRWLockShared` at `0x18018de1d`
- `KERNEL32!AcquireSRWLockShared` at `0x1801911c7`
- `KERNEL32!AcquireSRWLockShared` at `0x18018db48`
- `KERNEL32!AcquireSRWLockShared` at `0x18018de1d`
- `KERNEL32!AcquireSRWLockShared` at `0x1801911c7`
- `KERNEL32!ReleaseSRWLockShared` at `0x18018db8c`
- `KERNEL32!ReleaseSRWLockShared` at `0x18018dbff`
- `KERNEL32!ReleaseSRWLockShared` at `0x18018de59`
- `KERNEL32!ReleaseSRWLockShared` at `0x18018f4cb`
- `KERNEL32!ReleaseSRWLockShared` at `0x180190459`
- `KERNEL32!ReleaseSRWLockShared` at `0x180190df7`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801911fe`
- `KERNEL32!ReleaseSRWLockShared` at `0x18019122e`
- `KERNEL32!ReleaseSRWLockShared` at `0x180191fe9`
- `KERNEL32!ReleaseSRWLockShared` at `0x18018db8c`
- `KERNEL32!ReleaseSRWLockShared` at `0x18018dbff`
- `KERNEL32!ReleaseSRWLockShared` at `0x18018de59`
- `KERNEL32!ReleaseSRWLockShared` at `0x18018f4cb`
- `KERNEL32!ReleaseSRWLockShared` at `0x180190459`
- `KERNEL32!ReleaseSRWLockShared` at `0x180190df7`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801911fe`
- `KERNEL32!ReleaseSRWLockShared` at `0x18019122e`
- `KERNEL32!ReleaseSRWLockShared` at `0x180191fe9`
- `KERNEL32!GetTickCount64` at `0x18018fafd`
- `KERNEL32!GetTickCount64` at `0x18018fb79`
- `KERNEL32!GetTickCount64` at `0x18018fafd`
- `KERNEL32!GetTickCount64` at `0x18018fb79`

## string_xrefs

- `0x18018e992`: `RealtimeProtection::DlpCEngine::DlpQueryEngineIsFileSourceMonitoringPathExcluded`
- `0x18018fb17`: `DLP::CheckAccessForFile: It's time to dump the user agent process cache into a file`
- `0x1801901c1`: `DLP::CheckAccessForfile: Using any app enforcement from signature`
- `0x180191331`: `browser_broker.exe`
- `0x180191360`: `RuntimeBroker.exe`
- `0x180191421`: `Detected %ls opening sensitive. Associating session %lu cbdhsvc pid %lu with sensitive file (hr=%#lx): %ls`
- `0x18019145f`: `Detected %ls opening sensitive file. Failed to find session %lu cbdhsvc pid for sensitive file, clipboard enforcement might not work: %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RealtimeProtection::CRtpDlpEngine::CheckAccessForFileInternal(
        __int64 a1,
        int a2,
        wchar_t *a3,
        __int64 a4,
        const char *a5,
        wchar_t *String1,
        FILETIME *lpFileTime1,
        unsigned int a8,
        __int64 a9,
        int a10,
        rsize_t SourceSize,
        void *a12,
        unsigned int a13,
        __int64 a14,
        unsigned int a15,
        __int64 a16,
        unsigned int a17,
        int *a18,
        RealtimeProtection::DlpProcessCache *a19)
{
  wchar_t *v19; // rbx
  const WCHAR *v20; // r14
  __int64 v21; // r13
  __int64 v22; // r12
  RealtimeProtection::DlpProcessCache *v23; // rdi
  int v24; // esi
  const wchar_t *v25; // r8
  enum RealtimeProtection::AppBlanketLevel *v26; // r8
  int AppBlanketEnforcementLevel; // edi
  bool *v29; // r8
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  RealtimeProtection::DlpProcessCache *v32; // rdi
  int EngineConfigForAppBlanketEnforcement; // eax
  __int64 v34; // rdx
  PVOID v35; // rcx
  __int64 v36; // r8
  __int64 v37; // rax
  wchar_t **v38; // r8
  wchar_t *v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  std::_Ref_count_base *v43; // rdi
  RealtimeProtection::DlpProcessCache::DlpProcessStateCache *v44; // rbx
  struct RealtimeProtection::DlpCEngine **v45; // rdx
  __int64 v46; // r8
  PVOID *v47; // rcx
  __int64 v48; // rdx
  std::_Ref_count_base *v49; // rbx
  __int128 *v50; // rax
  int v51; // edi
  int v52; // eax
  __int128 *v53; // r9
  BOOL v54; // edi
  std::_Ref_count_base *v55; // rbx
  RealtimeProtection::DlpProcessCache::DlpProcessStateCache *v56; // rsi
  char IsTrustContainerEnabled; // al
  __int64 v58; // rcx
  std::_Ref_count_base **v59; // rax
  int LabelInfo; // ebx
  const struct std::nothrow_t *v61; // rdx
  void *v62; // rcx
  __int128 v63; // xmm0
  __int128 v64; // xmm1
  const wchar_t *v65; // rbx
  EndpointDlp::endpointDlpImpl **Instance; // rax
  const wchar_t *v67; // rdx
  int v68; // eax
  EndpointDlp::endpointDlpImpl **v69; // rax
  bool v70; // bl
  int Value; // eax
  __int64 v72; // r8
  int v73; // esi
  bool v74; // r14
  std::_Ref_count_base *v75; // rcx
  std::_Ref_count_base *v76; // r15
  volatile signed __int32 *v77; // r12
  std::_Ref_count_base *v78; // rbx
  std::_Ref_count_base **v79; // rax
  std::_Ref_count_base *v80; // r13
  std::_Ref_count_base *v81; // rsi
  std::_Ref_count_base *v82; // rax
  const wchar_t *v83; // rsi
  struct RealtimeProtection::DlpCEngine **v84; // rdx
  __int64 v85; // rbx
  _QWORD *v86; // rcx
  __int64 v87; // rdx
  std::_Ref_count_base *v88; // r9
  std::_Ref_count_base **v89; // rcx
  __int64 *v90; // rax
  bool v91; // r14
  int v92; // eax
  int v93; // esi
  PVOID *v94; // rcx
  struct RealtimeProtection::DlpCEngine **v95; // rdx
  __int64 v96; // rbx
  int v97; // eax
  int v98; // esi
  PVOID *v99; // rcx
  __int128 v100; // xmm0
  int v101; // ebx
  std::_Ref_count_base *v102; // r15
  __int128 *v103; // rdx
  std::_Ref_count_base *v104; // r9
  int v105; // ebx
  std::_Ref_count_base **v106; // rdx
  __int64 v107; // rax
  __int64 v108; // r10
  std::_Ref_count_base *v109; // rcx
  bool v110; // bl
  __int64 v111; // rcx
  std::_Ref_count_base *v112; // rcx
  wchar_t *v113; // r14
  __int64 *v114; // rax
  int JitFeaturesForUser; // eax
  PVOID *v116; // r10
  __int64 v117; // r11
  RealtimeProtection::DlpJitStateMachine *v118; // rcx
  wchar_t *v119; // rdi
  const wchar_t *JitExpirationTimeOut; // rax
  char updated; // al
  RealtimeProtection::DlpRtpPluginQuery *v122; // r14
  int v123; // eax
  int v124; // eax
  const wchar_t *v125; // rdx
  unsigned int AnyFileUserScope; // ebx
  const wchar_t *v127; // rdx
  wchar_t *v128; // rcx
  const wchar_t *v129; // rdx
  bool v130; // r14
  int v131; // eax
  int v132; // eax
  char v133; // al
  __int64 v134; // rdi
  __int16 v135; // si
  char v136; // bl
  int CbdhsvcPpid; // ebx
  _QWORD *v138; // rcx
  __int64 v139; // rdx
  std::_Ref_count_base *v140; // rcx
  RTL_SRWLOCK *v141; // rcx
  const wchar_t *v142; // rbx
  __int64 v143; // r9
  EndpointDlp::endpointDlpImpl **v144; // rax
  __int64 *v145; // rcx
  __int64 *v146; // rax
  std::_Ref_count_base *v147; // rcx
  __int64 v148; // rdx
  unsigned __int8 v149; // r14
  unsigned int v150; // ecx
  BOOL v151; // ebx
  __int64 v152; // rsi
  __int64 v153; // rdx
  unsigned int v154; // eax
  _DWORD *v155; // rcx
  bool v156; // si
  __int64 v157; // rdx
  __int64 v158; // rcx
  __int64 v159; // r8
  std::_Ref_count_base *v160; // rbx
  RealtimeProtection::DlpProcessCache::DlpProcessStateCache *v161; // rdi
  int FileIdFromQuarantineFilePath; // eax
  __int64 v163; // rbx
  const wchar_t *v164; // rdx
  void *v165; // rbx
  RealtimeProtection::DlpPlugin *v166; // rcx
  struct RealtimeProtection::CPluginWorkItemQueue *PluginWorkItemQueue; // rax
  const wchar_t *v168; // rdx
  void *v169; // rbx
  __int64 v170; // rax
  int v171; // eax
  char v172; // bl
  unsigned int v173; // eax
  struct PPID *v174; // r14
  LPCWCH v175; // rbx
  int v176; // eax
  WCHAR *v177; // r14
  _QWORD *v178; // rcx
  char IsSupported3PBrowserProcess; // si
  unsigned int v180; // r8d
  char v181; // bl
  const wchar_t *v182; // rdx
  int v183; // ecx
  __int64 v184; // r8
  unsigned int v185; // r15d
  const struct std::nothrow_t *v186; // rdx
  RealtimeProtection::DlpProcessCache *v187; // rcx
  __int64 v188; // r10
  unsigned int v189; // ebx
  char v190; // al
  __int64 v191; // r10
  int v192; // ebx
  int v193; // eax
  unsigned int v194; // ebx
  unsigned int v195; // ecx
  unsigned int v196; // ecx
  unsigned int v197; // ecx
  unsigned int v198; // ecx
  _QWORD *v199; // rcx
  __int64 v200; // rdx
  int v201; // eax
  int v202; // eax
  const struct std::nothrow_t *v203; // rdx
  int v204; // eax
  int v205; // eax
  bool v206; // r13
  char v207; // cl
  WCHAR *v208; // rsi
  __int64 *v209; // rdi
  int v210; // ebx
  __int64 v211; // r8
  __int64 v212; // r9
  char v213; // r15
  __int64 *v214; // rbx
  __int64 *v215; // rdi
  const char *v216; // rsi
  int v217; // r14d
  __int64 v218; // rcx
  __int64 v219; // rdx
  __int64 v220; // r8
  __int64 v221; // r8
  __int64 v222; // rdx
  __int64 v223; // rax
  __int64 v224; // rdx
  int v225; // eax
  __int64 v226; // r8
  __int64 v227; // r10
  __int64 v228; // r11
  RealtimeProtection::DlpProcessCache *v229; // rcx
  __int64 *v230; // rbx
  const char *v231; // rsi
  int v232; // r14d
  __int64 v233; // rdx
  __int64 v234; // r8
  __int64 v235; // rdx
  __int64 v236; // r8
  __int64 v237; // rax
  __int64 v238; // rdx
  int v239; // eax
  __int64 v240; // r8
  __int64 v241; // r10
  __int64 v242; // r11
  wchar_t *v243; // r14
  RealtimeProtection::DlpProcessCache *v244; // rdi
  int v245; // ebx
  int v246; // eax
  const struct std::nothrow_t *v247; // rdx
  _QWORD *v248; // rax
  int v249; // edx
  const struct std::nothrow_t *v250; // rdx
  const wchar_t *v251; // r8
  bool v252; // r9
  _QWORD *v253; // rcx
  __int64 v254; // rdx
  PVOID v255; // rcx
  bool IsJitProcessExcluded; // bl
  const wchar_t *v257; // r9
  bool IsJitFileExcluded; // al
  __int64 v259; // rdi
  bool v260; // al
  RealtimeProtection::DlpProcessCache *v261; // rdi
  int v262; // eax
  const wchar_t *v263; // r9
  PVOID *v264; // r10
  __int64 v265; // xmm6_8
  int v266; // edi
  RTL_SRWLOCK *v267; // rbx
  RTL_SRWLOCK *v268; // rdi
  int v269; // ebx
  __int64 v270; // rdi
  _QWORD *v271; // rcx
  __int64 v272; // rdx
  __int64 v273; // rcx
  __int64 v274; // rcx
  const struct PPID *v275; // rax
  const wchar_t *v276; // r9
  RealtimeProtection::DlpProcessCache *v277; // rax
  const struct RealtimeProtection::FileUniqueId *v278; // rdx
  bool v279; // r12
  __int64 v280; // r14
  __int64 v281; // r15
  __int64 v282; // rbx
  unsigned int v283; // edi
  unsigned int v284; // esi
  __int64 v285; // rax
  RealtimeProtection::DlpProcessCache *v286; // r14
  char v287; // r15
  bool v288; // r14
  __int64 v289; // rdx
  RealtimeProtection::DlpProcessCache *v290; // rcx
  int v291; // eax
  __int64 *v292; // rdx
  const struct RealtimeProtection::DlpThrottle::DlpThrottleCloudEgressEvent *v293; // rdx
  _QWORD *v294; // r15
  __int64 v295; // rsi
  __int64 v296; // rdi
  __int64 v297; // rbx
  const wchar_t *v298; // r14
  __int64 v299; // r12
  char v300; // r13
  std::_Ref_count_base **v301; // r15
  __int64 v302; // rbx
  int v303; // edi
  int v304; // eax
  __int64 v305; // rcx
  __int16 v306; // bx
  char CacheSettings; // bl
  RealtimeProtection::DlpProcessCache *v308; // rcx
  unsigned int v309; // eax
  __int64 *v310; // rdx
  const struct RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent *v311; // rdx
  _QWORD *v312; // rsi
  __int64 v313; // rdi
  __int64 v314; // rbx
  char v315; // si
  unsigned int v316; // r14d
  __int16 v317; // r13
  __int128 *v318; // rdi
  __int64 *v319; // rdx
  const struct RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *v320; // rdx
  _QWORD *v321; // rdi
  __int64 v322; // rbx
  int v323; // ebx
  int v324; // eax
  __int64 v325; // rcx
  const struct std::nothrow_t *v326; // rdx
  const char *v327; // rbx
  const char *v328; // rdi
  const char *v329; // rsi
  __int64 v330; // r15
  __int64 v331; // rdx
  __int64 v332; // r8
  __int64 v333; // r9
  __int64 v334; // r12
  int v335; // r13d
  unsigned int v336; // eax
  char v337; // r14
  __int64 v338; // rbx
  __int64 v339; // rdx
  __int64 v340; // r8
  __int64 v341; // rdx
  __int64 v342; // r8
  __int64 v343; // rax
  __int64 v344; // rdx
  int v345; // eax
  int v346; // edx
  __int64 v347; // r8
  __int64 v348; // r10
  __int64 v349; // r11
  int v350; // eax
  wchar_t **Reserved; // [rsp+20h] [rbp-130h]
  char v352[8]; // [rsp+28h] [rbp-128h]
  __int64 *v353; // [rsp+30h] [rbp-120h]
  unsigned __int8 *v354; // [rsp+38h] [rbp-118h]
  _OWORD *v355; // [rsp+48h] [rbp-108h]
  __int64 v356; // [rsp+50h] [rbp-100h]
  __int64 v357; // [rsp+50h] [rbp-100h]
  __int64 v358; // [rsp+58h] [rbp-F8h]
  __int64 v359; // [rsp+58h] [rbp-F8h]
  unsigned int *v360; // [rsp+60h] [rbp-F0h]
  __int64 v361; // [rsp+80h] [rbp-D0h]
  unsigned int v362; // [rsp+88h] [rbp-C8h]
  __int64 v363; // [rsp+B8h] [rbp-98h]
  bool IsDlpEnabledForFile; // [rsp+D0h] [rbp-80h]
  char v365; // [rsp+D0h] [rbp-80h]
  unsigned __int8 v366; // [rsp+D1h] [rbp-7Fh]
  char v367; // [rsp+D2h] [rbp-7Eh] BYREF
  bool v368; // [rsp+D3h] [rbp-7Dh]
  unsigned int v369; // [rsp+D4h] [rbp-7Ch]
  char v370; // [rsp+D8h] [rbp-78h]
  unsigned __int8 v371[7]; // [rsp+D9h] [rbp-77h] BYREF
  int v372[2]; // [rsp+E0h] [rbp-70h]
  unsigned int v373; // [rsp+E8h] [rbp-68h]
  int v374[3]; // [rsp+ECh] [rbp-64h] BYREF
  wchar_t *v375; // [rsp+F8h] [rbp-58h]
  RealtimeProtection::DlpProcessCache *v376; // [rsp+100h] [rbp-50h]
  LPCWCH lpString1; // [rsp+108h] [rbp-48h]
  RealtimeProtection::DlpProcessCache *v378; // [rsp+110h] [rbp-40h]
  _BYTE v379[16]; // [rsp+118h] [rbp-38h] BYREF
  std::_Ref_count_base *v380[2]; // [rsp+128h] [rbp-28h] BYREF
  __int64 v381; // [rsp+138h] [rbp-18h] BYREF
  unsigned int v382; // [rsp+140h] [rbp-10h]
  void *Source; // [rsp+148h] [rbp-8h]
  std::_Ref_count_base *v384[2]; // [rsp+150h] [rbp+0h] BYREF
  std::_Ref_count_base *v385[2]; // [rsp+160h] [rbp+10h] BYREF
  __int64 v386; // [rsp+170h] [rbp+20h]
  __int64 v387; // [rsp+178h] [rbp+28h]
  int *v388; // [rsp+180h] [rbp+30h]
  const wchar_t *v389; // [rsp+188h] [rbp+38h]
  int v390[2]; // [rsp+190h] [rbp+40h] BYREF
  int v391; // [rsp+198h] [rbp+48h]
  __int128 v392; // [rsp+1A0h] [rbp+50h] BYREF
  __int64 v393; // [rsp+1B0h] [rbp+60h]
  char v394; // [rsp+1C0h] [rbp+70h]
  _BYTE v395[16]; // [rsp+1D0h] [rbp+80h] BYREF
  char v396; // [rsp+1E0h] [rbp+90h]
  unsigned int v397; // [rsp+1E8h] [rbp+98h] BYREF
  unsigned int v398; // [rsp+1ECh] [rbp+9Ch] BYREF
  __int128 v399; // [rsp+1F0h] [rbp+A0h] BYREF
  char v400; // [rsp+200h] [rbp+B0h]
  __int128 v401; // [rsp+208h] [rbp+B8h] BYREF
  unsigned __int8 v402; // [rsp+218h] [rbp+C8h] BYREF
  char v403; // [rsp+219h] [rbp+C9h] BYREF
  unsigned __int8 v404; // [rsp+21Ah] [rbp+CAh] BYREF
  unsigned int v405; // [rsp+21Ch] [rbp+CCh] BYREF
  char v406; // [rsp+220h] [rbp+D0h] BYREF
  unsigned int v407; // [rsp+224h] [rbp+D4h] BYREF
  wchar_t *String2; // [rsp+228h] [rbp+D8h] BYREF
  __int64 v409; // [rsp+230h] [rbp+E0h] BYREF
  void *v410; // [rsp+238h] [rbp+E8h] BYREF
  _DWORD v411[4]; // [rsp+240h] [rbp+F0h] BYREF
  __int64 v412[2]; // [rsp+250h] [rbp+100h] BYREF
  __int64 v413; // [rsp+260h] [rbp+110h]
  unsigned __int64 v414; // [rsp+268h] [rbp+118h]
  __int64 Src[2]; // [rsp+270h] [rbp+120h] BYREF
  __int64 v416; // [rsp+280h] [rbp+130h]
  unsigned __int64 v417; // [rsp+288h] [rbp+138h]
  __int64 v418[4]; // [rsp+290h] [rbp+140h] BYREF
  char v419; // [rsp+2B0h] [rbp+160h]
  const char *v420; // [rsp+2B8h] [rbp+168h] BYREF
  unsigned int v421; // [rsp+2C0h] [rbp+170h]
  char v422; // [rsp+2C4h] [rbp+174h]
  __int128 v423; // [rsp+2D0h] [rbp+180h] BYREF
  __int128 v424; // [rsp+2E0h] [rbp+190h]
  _BYTE v425[32]; // [rsp+2F0h] [rbp+1A0h] BYREF
  char v426[16]; // [rsp+310h] [rbp+1C0h] BYREF
  __int64 v427; // [rsp+330h] [rbp+1E0h]
  std::_Ref_count_base *v428; // [rsp+340h] [rbp+1F0h] BYREF
  std::_Ref_count_base *v429; // [rsp+348h] [rbp+1F8h]
  std::_Ref_count_base *v430; // [rsp+350h] [rbp+200h]
  std::_Ref_count_base *v431; // [rsp+358h] [rbp+208h]
  char v432; // [rsp+360h] [rbp+210h]
  __int128 v433; // [rsp+368h] [rbp+218h] BYREF
  __int128 v434; // [rsp+378h] [rbp+228h]
  char v435; // [rsp+388h] [rbp+238h]
  __int64 v436[2]; // [rsp+390h] [rbp+240h] BYREF
  __int64 v437; // [rsp+3A0h] [rbp+250h]
  __int64 v438; // [rsp+3A8h] [rbp+258h]
  wchar_t *v439[4]; // [rsp+3B0h] [rbp+260h] BYREF
  __int64 v440[4]; // [rsp+3D0h] [rbp+280h] BYREF
  char v441; // [rsp+3F0h] [rbp+2A0h]
  __int64 v442[2]; // [rsp+3F8h] [rbp+2A8h] BYREF
  __int64 v443; // [rsp+408h] [rbp+2B8h]
  __int64 v444; // [rsp+410h] [rbp+2C0h]
  __int64 v445; // [rsp+420h] [rbp+2D0h] BYREF
  volatile signed __int32 *v446; // [rsp+428h] [rbp+2D8h]
  char v447; // [rsp+430h] [rbp+2E0h]
  __int64 v448; // [rsp+438h] [rbp+2E8h] BYREF
  __int64 v449; // [rsp+440h] [rbp+2F0h]
  char v450; // [rsp+448h] [rbp+2F8h]
  int v451; // [rsp+450h] [rbp+300h]
  char v452; // [rsp+460h] [rbp+310h]
  _BYTE v453[16]; // [rsp+470h] [rbp+320h] BYREF
  _BYTE v454[32]; // [rsp+480h] [rbp+330h] BYREF
  __int64 v455[2]; // [rsp+4A0h] [rbp+350h] BYREF
  __int64 v456; // [rsp+4B0h] [rbp+360h]
  __int64 v457; // [rsp+4B8h] [rbp+368h]
  __int128 v458; // [rsp+4C0h] [rbp+370h] BYREF
  __int64 v459; // [rsp+4D0h] [rbp+380h]
  __int64 v460; // [rsp+4D8h] [rbp+388h]
  __int64 v461[2]; // [rsp+4E0h] [rbp+390h] BYREF
  __int128 v462; // [rsp+4F0h] [rbp+3A0h]
  __int128 v463; // [rsp+500h] [rbp+3B0h]
  __int128 v464; // [rsp+510h] [rbp+3C0h]
  __int128 v465; // [rsp+520h] [rbp+3D0h] BYREF
  __int64 v466; // [rsp+530h] [rbp+3E0h]
  __int64 v467; // [rsp+538h] [rbp+3E8h]
  __int128 v468; // [rsp+540h] [rbp+3F0h] BYREF
  __int64 v469; // [rsp+550h] [rbp+400h]
  __int64 v470; // [rsp+558h] [rbp+408h]
  __int128 v471; // [rsp+560h] [rbp+410h] BYREF
  __int64 v472; // [rsp+570h] [rbp+420h]
  __int64 v473; // [rsp+578h] [rbp+428h]
  __int128 v474; // [rsp+580h] [rbp+430h] BYREF
  __int64 v475; // [rsp+590h] [rbp+440h]
  __int64 v476; // [rsp+598h] [rbp+448h]
  std::_Ref_count_base *v477[2]; // [rsp+5A0h] [rbp+450h] BYREF
  __int64 v478; // [rsp+5B0h] [rbp+460h]
  char v479; // [rsp+800h] [rbp+6B0h]
  _BYTE v480[928]; // [rsp+810h] [rbp+6C0h] BYREF
  __int64 v481[148]; // [rsp+BB0h] [rbp+A60h] BYREF
  _OWORD v482[5]; // [rsp+1050h] [rbp+F00h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1108h] [rbp+FB8h]

  *(_QWORD *)v390 = a4;
  v19 = a3;
  *(_QWORD *)&v374[1] = a3;
  LODWORD(v375) = a2;
  *(_QWORD *)v372 = a1;
  v420 = a5;
  v20 = String1;
  lpString1 = String1;
  v376 = (RealtimeProtection::DlpProcessCache *)lpFileTime1;
  v387 = a9;
  v374[0] = a10;
  v411[0] = a10;
  Source = a12;
  v21 = a14;
  v22 = a16;
  v388 = a18;
  v23 = a19;
  v378 = a19;
  v24 = 0;
  v373 = 0;
  RealtimeProtection::DlpAutoEtwPerfOperation::DlpAutoEtwPerfOperation(v379, 4, 0xFFFFFFFFLL);
  *v388 = 1;
  if ( v23 )
    *(_DWORD *)v23 = 0;
  if ( (_DWORD)v375 == 2
    && !(unsigned int)RealtimeProtection::DlpProcessCache::AddFileSection(
                        (RealtimeProtection::DlpProcessCache *)lpFileTime1,
                        v19,
                        v25) )
  {
    *v388 = 1;
LABEL_900:
    RealtimeProtection::DlpAutoEtwPerfOperation::~DlpAutoEtwPerfOperation((RealtimeProtection::DlpAutoEtwPerfOperation *)v379);
    return 0;
  }
  v398 = 0;
  LODWORD(String2) = 0;
  RealtimeProtection::DlpUserSidCache::TryGetClassificationUserSidString(v418, (unsigned int)v374[0], lpFileTime1);
  if ( (unsigned int)Dlp::FeatureControl::GetValue(217) && v419 )
    RealtimeProtection::DlpUserConfigManagement::CheckAndQueueUserConfigInitRequest((unsigned int)v374[0], v418);
  AcquireSRWLockShared((PSRWLOCK)(*(_QWORD *)v372 + 16LL));
  if ( *(_DWORD *)(*(_QWORD *)v372 + 8LL) != 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, 2147947423LL);
    ReleaseSRWLockShared((PSRWLOCK)(*(_QWORD *)v372 + 16LL));
    std::optional<std::wstring>::~optional<std::wstring>(v418);
    RealtimeProtection::DlpAutoEtwPerfOperation::~DlpAutoEtwPerfOperation((RealtimeProtection::DlpAutoEtwPerfOperation *)v379);
    return 2147947423LL;
  }
  AppBlanketEnforcementLevel = RealtimeProtection::DlpProcessCache::GetAppBlanketEnforcementLevel(
                                 lpFileTime1,
                                 (const struct PPID *)&String2,
                                 v26);
  if ( AppBlanketEnforcementLevel < 0 )
  {
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v31 = 177;
LABEL_18:
    WPP_SF_d(v30[2], v31, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, (unsigned int)AppBlanketEnforcementLevel);
LABEL_19:
    ReleaseSRWLockShared((PSRWLOCK)(*(_QWORD *)v372 + 16LL));
    std::optional<std::wstring>::~optional<std::wstring>(v418);
    RealtimeProtection::DlpAutoEtwPerfOperation::~DlpAutoEtwPerfOperation((RealtimeProtection::DlpAutoEtwPerfOperation *)v379);
    return (unsigned int)AppBlanketEnforcementLevel;
  }
  v382 = (unsigned int)String2;
  if ( !(_DWORD)String2 )
  {
    v367 = 0;
    v32 = v376;
    EngineConfigForAppBlanketEnforcement = RealtimeProtection::DlpEngineUtils::GetEngineConfigForAppBlanketEnforcement(
                                             v376,
                                             (const struct PPID *)&v367,
                                             v29);
    if ( EngineConfigForAppBlanketEnforcement >= 0 )
    {
      if ( !v367 )
      {
        v382 = 2;
        goto LABEL_28;
      }
    }
    else
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          178,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)EngineConfigForAppBlanketEnforcement);
        v382 = 1;
LABEL_28:
        LODWORD(String2) = 0;
        v37 = MpClientUtilExportFunctions(v35, v34, v36);
        if ( (*(int (__fastcall **)(wchar_t **))(v37 + 152))(&String2) < 0 || !(_DWORD)String2 )
          goto LABEL_43;
        String2 = 0;
        if ( (int)RealtimeProtection::DlpUtils::DlpGetMiscStringValue(
                    (RealtimeProtection::DlpUtils *)L"MpDlp_TestProcessNoBlanketPolicy",
                    (wchar_t *)&String2,
                    v38) >= 0 )
        {
          v39 = String2;
          if ( String2 )
            goto LABEL_36;
        }
        else if ( String2 )
        {
          MpFreeMemory(String2);
          String2 = 0;
        }
        if ( (int)MpAllocSprintfW(&String2, L"%s", L"filetest.exe") < 0 )
        {
LABEL_41:
          if ( String2 )
            MpFreeMemory(String2);
LABEL_43:
          AppBlanketEnforcementLevel = RealtimeProtection::DlpProcessCache::SetAppBlanketEnforcementLevel(v32, v382);
          if ( AppBlanketEnforcementLevel < 0 )
          {
            v30 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_19;
            v31 = 180;
            goto LABEL_18;
          }
          goto LABEL_47;
        }
        v39 = String2;
        if ( !String2 )
          goto LABEL_43;
LABEL_36:
        if ( !wcsicmp(String1, v39) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              179,
              &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
              String1);
          v382 = 2;
        }
        goto LABEL_41;
      }
    }
    v382 = 1;
    goto LABEL_28;
  }
LABEL_47:
  if ( *(_BYTE *)(*(_QWORD *)v372 + 95LL) && (Dlp::FeatureControl::GetValue(114) & 4) != 0 )
  {
    Lock_shared_ptr_spin_lock(v41, v40, v42);
    v43 = qword_180314488;
    if ( qword_180314488 )
    {
      _InterlockedIncrement((volatile signed __int32 *)qword_180314488 + 2);
      v43 = qword_180314488;
    }
    v44 = qword_180314480;
    Unlock_shared_ptr_spin_lock();
    if ( !v44 )
    {
      if ( v43 )
        std::_Ref_count_base::_Decref(v43);
      AppBlanketEnforcementLevel = -2147483634;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v31 = 181;
      goto LABEL_18;
    }
    AcquireSRWLockShared((PSRWLOCK)v44 + 58);
    v385[0] = 0;
    std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(
      (char *)v44 + 200,
      v385,
      v376);
    if ( v385[0] != *((std::_Ref_count_base **)v44 + 26) )
      v24 = *((_DWORD *)v385[0] + 93);
    ReleaseSRWLockShared((PSRWLOCK)v44 + 58);
    if ( v43 )
      std::_Ref_count_base::_Decref(v43);
    AppBlanketEnforcementLevel = 0;
    v20 = lpString1;
    if ( v24 || !lpString1 )
      goto LABEL_103;
    std::wstring::wstring(&v423, lpString1);
    if ( !(_QWORD)v424 )
    {
      v47 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v48 = 74;
LABEL_66:
        WPP_SF_(v47[2], v48, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids);
        goto LABEL_96;
      }
      goto LABEL_96;
    }
    v385[0] = 0;
    RealtimeProtection::DlpPlugin::GetEngine((RealtimeProtection::DlpPlugin *)v385, v45);
    v49 = v385[0];
    if ( !v385[0] )
    {
      v47 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v48 = 75;
        goto LABEL_66;
      }
LABEL_96:
      v54 = (_BYTE)v24 != 0;
      Lock_shared_ptr_spin_lock(v47, v45, v46);
      v55 = qword_180314488;
      if ( qword_180314488 )
      {
        _InterlockedIncrement((volatile signed __int32 *)qword_180314488 + 2);
        v55 = qword_180314488;
      }
      v56 = qword_180314480;
      Unlock_shared_ptr_spin_lock();
      if ( v56 )
      {
        AppBlanketEnforcementLevel = RealtimeProtection::DlpProcessCache::DlpProcessStateCache::SetSectionMapSettingForQuarantine(
                                       v56,
                                       v376,
                                       (unsigned int)(v54 + 1));
        if ( v55 )
          std::_Ref_count_base::_Decref(v55);
        if ( AppBlanketEnforcementLevel >= 0 )
        {
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v423);
          v20 = lpString1;
LABEL_103:
          v19 = *(wchar_t **)&v374[1];
          goto LABEL_104;
        }
      }
      else
      {
        if ( v55 )
          std::_Ref_count_base::_Decref(v55);
        AppBlanketEnforcementLevel = -2147483634;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          183,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)AppBlanketEnforcementLevel);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v423);
      goto LABEL_19;
    }
    v50 = &v423;
    if ( *((_QWORD *)&v424 + 1) > 7u )
      v50 = (__int128 *)v423;
    LOBYTE(v24) = 0;
    if ( !v50 )
    {
      v47 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_2f1a258b79b036cc8d24fffabf360af1_Traceguids);
        v47 = (PVOID *)WPP_GLOBAL_Control;
      }
      v51 = -2147024809;
      goto LABEL_80;
    }
    v401 = (unsigned __int64)v50;
    v52 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int128 *, __int64))v385[0] + 2))(
            *((_QWORD *)v385[0] + 3),
            16585,
            &v401,
            16);
    v51 = v52;
    if ( v52 >= 0 )
    {
      LOBYTE(v24) = DWORD2(v401) == 1;
      v51 = 0;
    }
    else
    {
      v47 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_80:
        if ( v51 >= 0 )
        {
          if ( v47 != &WPP_GLOBAL_Control && (*((_BYTE *)v47 + 28) & 4) != 0 )
          {
            v53 = &v423;
            if ( *((_QWORD *)&v424 + 1) > 7u )
              LODWORD(v53) = v423;
            WPP_SF_Sd(
              (unsigned int)v47[2],
              77,
              (unsigned int)&WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
              (_DWORD)v53,
              v24);
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v49 + 2, 0xFFFFFFFF) <= 1 )
          {
            _mm_lfence();
            (**(void (__fastcall ***)(std::_Ref_count_base *, __int64))v49)(v49, 1);
          }
        }
        else
        {
          if ( v47 != &WPP_GLOBAL_Control && (*((_BYTE *)v47 + 28) & 1) != 0 )
            WPP_SF_d(v47[2], 76, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids, (unsigned int)v51);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v49 + 2, 0xFFFFFFFF) <= 1 )
          {
            _mm_lfence();
            (**(void (__fastcall ***)(std::_Ref_count_base *, __int64))v49)(v49, 1);
          }
          LOBYTE(v24) = 0;
          v47 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              182,
              &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
              (unsigned int)v51);
        }
        goto LABEL_96;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_2f1a258b79b036cc8d24fffabf360af1_Traceguids,
        (unsigned int)v52);
    }
    v47 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_80;
  }
LABEL_104:
  if ( v419 )
    IsTrustContainerEnabled = RealtimeProtection::DlpEngineUtils::IsTrustContainerEnabled(v418);
  else
    IsTrustContainerEnabled = 0;
  v370 = IsTrustContainerEnabled;
  v435 = 0;
  *(_QWORD *)&v399 = 0;
  if ( !IsTrustContainerEnabled )
    goto LABEL_140;
  v423 = 0;
  *(_QWORD *)&v424 = 0;
  *((_QWORD *)&v424 + 1) = 7;
  LOWORD(v423) = 0;
  std::wstring::wstring(&v428, v19);
  v58 = *(_QWORD *)EndpointDlp::endpointDlpImpl::GetInstance(v380);
  v59 = &v428;
  if ( (unsigned __int64)v431 > 7 )
    v59 = (std::_Ref_count_base **)v428;
  *(_QWORD *)&v401 = v59;
  *((_QWORD *)&v401 + 1) = v430;
  LabelInfo = EndpointDlp::endpointDlpImpl::TrustContainerReadLabelInfo(
                v58,
                (_DWORD)Source,
                SourceSize,
                (unsigned int)&v401,
                (__int64)&v423,
                (__int64)&v399);
  if ( v380[1] )
    std::_Ref_count_base::_Decref(v380[1]);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v428);
  if ( LabelInfo >= 0 )
  {
    if ( v435 )
    {
      if ( *((_QWORD *)&v434 + 1) > 7u )
      {
        v61 = (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v434 + 1) + 2);
        v62 = (void *)v433;
        if ( (unsigned __int64)v61 >= 0x1000 )
        {
          v61 = (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v434 + 1) + 41);
          v62 = *(void **)(v433 - 8);
          if ( (unsigned __int64)(v433 - (_QWORD)v62 - 8) > 0x1F )
            invoke_watson(0, 0, 0, 0, 0);
        }
        operator delete(v62, v61);
      }
    }
    else
    {
      v435 = 1;
    }
    v63 = v423;
    v64 = v424;
    LOWORD(v423) = 0;
    *((_QWORD *)&v424 + 1) = 7;
    *(_QWORD *)&v424 = 0;
    v434 = v64;
    v433 = v63;
  }
  else if ( LabelInfo == -2147023728 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v20, *(__int64 *)&v374[1]);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_DSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v20, *(__int64 *)&v374[1], LabelInfo);
  }
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v423);
  v367 = 1;
  if ( !v435 )
LABEL_140:
    v367 = 0;
  v402 = 0;
  v407 = 10;
  memset(v482, 0, sizeof(v482));
  *(_OWORD *)v412 = 0;
  v413 = 0;
  v414 = 7;
  LOWORD(v412[0]) = 0;
  *(_OWORD *)Src = 0;
  v416 = 0;
  v417 = 7;
  LOWORD(Src[0]) = 0;
  v369 = 0;
  v405 = 0;
  memset(v480, 0, 0x396u);
  *(_OWORD *)v461 = 0;
  v462 = 0;
  v463 = 0;
  v464 = 0;
  v65 = *(const wchar_t **)&v374[1];
  RealtimeProtection::DlpUtils::GetFileExtensions(v439, *(_QWORD *)&v374[1]);
  v366 = 0;
  v371[0] = 0;
  Instance = (EndpointDlp::endpointDlpImpl **)EndpointDlp::endpointDlpImpl::GetInstance(v380);
  IsDlpEnabledForFile = EndpointDlp::endpointDlpImpl::IsDlpEnabledForFile(*Instance, v65);
  if ( v380[1] )
    std::_Ref_count_base::_Decref(v380[1]);
  if ( !v65 || !v20 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        244,
        (unsigned int)&WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (_DWORD)v65,
        (__int64)v20);
    goto LABEL_160;
  }
  if ( !RealtimeProtection::DlpUtils::IsSupported3PBrowserProcess(v20, v67) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 245, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids, v20);
    goto LABEL_160;
  }
  LODWORD(String2) = 0;
  v68 = RealtimeProtection::DlpEngineUtils::CheckExclusionProtectionForCloudEgress(
          (unsigned int)v374[0],
          v418,
          &String2);
  if ( v68 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        246,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v68);
    goto LABEL_160;
  }
  if ( !(_DWORD)String2 )
  {
LABEL_160:
    v368 = 0;
    goto LABEL_161;
  }
  v69 = (EndpointDlp::endpointDlpImpl **)EndpointDlp::endpointDlpImpl::GetInstance(v380);
  v70 = EndpointDlp::endpointDlpImpl::IsDlpEnabledForFile(*v69, v65);
  if ( v380[1] )
    std::_Ref_count_base::_Decref(v380[1]);
  v368 = !v70;
  v65 = *(const wchar_t **)&v374[1];
LABEL_161:
  v389 = v65;
  if ( *(_BYTE *)(*(_QWORD *)v390 + 32LL) )
  {
    v389 = *(const wchar_t **)v390;
    if ( *(_QWORD *)(*(_QWORD *)v390 + 24LL) > 7u )
      v389 = **(const wchar_t ***)v390;
  }
  Value = Dlp::FeatureControl::GetValue(177);
  v73 = Value;
  LOBYTE(v73) = Value & 1;
  LODWORD(String2) = v73;
  v401 = 0;
  *(_OWORD *)v384 = 0;
  v74 = 0;
  if ( (Value & 1) != 0 )
  {
    if ( a15 )
    {
      EndpointDlp::_anonymous_namespace_::GetTextEaDataHelper_EndpointDlp::Client::MarkOfTheWebData_(&v399, a15, v22);
      __SET_PAIR__((unsigned __int64)v77, (unsigned __int64)v76, v399);
      v385[0] = (std::_Ref_count_base *)v399;
      v401 = v399;
      v78 = (std::_Ref_count_base *)*((_QWORD *)&v399 + 1);
      v75 = 0;
    }
    else
    {
      v75 = 0;
      v76 = 0;
      v385[0] = 0;
      v401 = 0u;
      v77 = 0;
      v78 = 0;
    }
    v373 = 0;
    if ( a13 )
    {
      v373 = 8;
      EndpointDlp::_anonymous_namespace_::GetTextEaDataHelper_EndpointDlp::Client::ApplicationSourceData_(
        &v399,
        a13,
        v21);
      v79 = (std::_Ref_count_base **)&v399;
      v80 = (std::_Ref_count_base *)v399;
      v75 = 0;
      v72 = v373;
    }
    else
    {
      v72 = 4;
      v373 = 4;
      v380[1] = 0;
      v79 = v380;
      v80 = 0;
    }
    v81 = v79[1];
    *v79 = 0;
    v79[1] = 0;
    v384[0] = v80;
    v384[1] = v81;
    if ( (v72 & 8) != 0 )
    {
      v72 = (unsigned int)v72 & 0xFFFFFFF7;
      v373 = v72;
      v75 = (std::_Ref_count_base *)*((_QWORD *)&v399 + 1);
      if ( *((_QWORD *)&v399 + 1) )
      {
        std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v399 + 1));
        v72 = v373;
      }
    }
    if ( (v72 & 4) != 0 )
    {
      v72 = (unsigned int)v72 & 0xFFFFFFFB;
      v373 = v72;
      v75 = v380[1];
      if ( v380[1] )
        std::_Ref_count_base::_Decref(v380[1]);
    }
    if ( (_DWORD)v375 == 4 )
    {
      v432 = 0;
      std::wstring::wstring(&v423, v389);
      AppBlanketEnforcementLevel = RealtimeProtection::DlpFileSourceDataCache::GetEa(v387, &v423, &v428);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v423);
      if ( AppBlanketEnforcementLevel < 0 )
      {
        v75 = (std::_Ref_count_base *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            186,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            (unsigned int)AppBlanketEnforcementLevel);
        AppBlanketEnforcementLevel = 0;
      }
      if ( v432 )
      {
        v75 = v431;
        if ( v431 )
        {
          _InterlockedIncrement((volatile signed __int32 *)v431 + 2);
          v75 = v431;
        }
        v76 = v430;
        v385[0] = v430;
        *(_QWORD *)&v401 = v430;
        v77 = (volatile signed __int32 *)v75;
        *((_QWORD *)&v401 + 1) = v75;
        if ( v78 )
        {
          std::_Ref_count_base::_Decref(v78);
          v75 = v431;
        }
        if ( !v432 )
          std::_Throw_bad_optional_access();
        v82 = v429;
        if ( v429 )
        {
          _InterlockedIncrement((volatile signed __int32 *)v429 + 2);
          v75 = v431;
          v82 = v429;
        }
        v80 = v428;
        v384[0] = v428;
        v384[1] = v82;
        if ( v81 )
        {
          std::_Ref_count_base::_Decref(v81);
          v75 = v431;
          v82 = v429;
        }
        if ( v432 )
        {
          if ( v75 )
          {
            std::_Ref_count_base::_Decref(v75);
            v82 = v429;
          }
          if ( v82 )
            std::_Ref_count_base::_Decref(v82);
        }
      }
    }
    if ( !v76 && !v80 )
      goto LABEL_208;
    v83 = v389;
    if ( !v389 || !(unsigned int)RealtimeProtection::DlpPlugin::IsPluginInitialized(v75) )
      goto LABEL_207;
    *(_QWORD *)&v399 = 0;
    RealtimeProtection::DlpPlugin::GetEngine((RealtimeProtection::DlpPlugin *)&v399, v84);
    v85 = v399;
    if ( !(_QWORD)v399 )
    {
      v86 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_207;
      v87 = 36;
LABEL_206:
      WPP_SF_(v86[2], v87, WPP_9bce63ce04f53a278728ac7dd0e232b4_Traceguids);
LABEL_207:
      v74 = 1;
LABEL_208:
      v88 = v385[0];
      LOBYTE(v73) = (_BYTE)String2;
      goto LABEL_209;
    }
    v91 = 1;
    *((_QWORD *)&v399 + 1) = 1;
    *(_QWORD *)&v399 = v83;
    v92 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, __int64))(v85 + 16))(
            *(_QWORD *)(v85 + 24),
            16590,
            &v399,
            16);
    v93 = v92;
    if ( v92 >= 0 )
    {
      v91 = DWORD2(v399) == 1;
      v93 = 0;
    }
    else
    {
      v94 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_217:
        if ( v93 < 0 )
        {
          if ( v94 != &WPP_GLOBAL_Control && (*((_BYTE *)v94 + 28) & 1) != 0 )
            WPP_SF_d(v94[2], 37, WPP_9bce63ce04f53a278728ac7dd0e232b4_Traceguids, (unsigned int)v93);
          v91 = 1;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v85 + 8), 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (**(void (__fastcall ***)(__int64, __int64))v85)(v85, 1);
        }
        if ( v91
          || !lpString1
          || !(unsigned int)RealtimeProtection::DlpPlugin::IsPluginInitialized((RealtimeProtection::DlpPlugin *)v94) )
        {
          goto LABEL_207;
        }
        *(_QWORD *)&v399 = 0;
        RealtimeProtection::DlpPlugin::GetEngine((RealtimeProtection::DlpPlugin *)&v399, v95);
        v96 = v399;
        if ( !(_QWORD)v399 )
        {
          v86 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_207;
          v87 = 38;
          goto LABEL_206;
        }
        v74 = 1;
        *((_QWORD *)&v399 + 1) = 1;
        *(_QWORD *)&v399 = lpString1;
        v97 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, __int64))(v96 + 16))(
                *(_QWORD *)(v96 + 24),
                16589,
                &v399,
                16);
        v98 = v97;
        if ( v97 >= 0 )
        {
          v74 = DWORD2(v399) == 1;
          v98 = 0;
        }
        else
        {
          v99 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
LABEL_237:
            if ( v98 < 0 )
            {
              if ( v99 != &WPP_GLOBAL_Control && (*((_BYTE *)v99 + 28) & 1) != 0 )
                WPP_SF_d(v99[2], 39, WPP_9bce63ce04f53a278728ac7dd0e232b4_Traceguids, (unsigned int)v98);
              v74 = 1;
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v96 + 8), 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (**(void (__fastcall ***)(__int64, __int64))v96)(v96, 1);
            }
            if ( !v74 )
              goto LABEL_208;
            goto LABEL_207;
          }
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52,
            (unsigned int)WPP_2f1a258b79b036cc8d24fffabf360af1_Traceguids,
            (unsigned int)"RealtimeProtection::DlpCEngine::DlpQueryEngineIsFileSourceMonitoringProcessExcluded",
            v97);
        }
        v99 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_237;
      }
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        (unsigned int)WPP_2f1a258b79b036cc8d24fffabf360af1_Traceguids,
        (unsigned int)"RealtimeProtection::DlpCEngine::DlpQueryEngineIsFileSourceMonitoringPathExcluded",
        v92);
    }
    v94 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_217;
  }
  v77 = (volatile signed __int32 *)*((_QWORD *)&v401 + 1);
  v88 = (std::_Ref_count_base *)v401;
  v80 = v384[0];
LABEL_209:
  if ( (_DWORD)SourceSize )
  {
    LODWORD(v380[0]) = SourceSize;
    v380[1] = (std::_Ref_count_base *)Source;
    LOBYTE(v381) = 1;
    v89 = v380;
    v90 = &v381;
  }
  else
  {
    v454[0] = 0;
    v89 = (std::_Ref_count_base **)v453;
    v90 = (__int64 *)v454;
  }
  if ( *(_BYTE *)v90 )
    v100 = *(_OWORD *)v89;
  else
    v100 = *(_OWORD *)v380;
  LOBYTE(v386) = *(_BYTE *)v90 != 0;
  *(_DWORD *)((char *)&v386 + 1) = *(_DWORD *)((char *)&v381 + 1);
  *(_WORD *)((char *)&v386 + 5) = *(_WORD *)((char *)&v381 + 5);
  HIBYTE(v386) = HIBYTE(v381);
  if ( !v80 || v74 )
  {
    v101 = v373 | 0x20;
    v454[0] = 0;
    v103 = (__int128 *)v453;
    v102 = v384[1];
  }
  else
  {
    v101 = v373 | 0x10;
    v102 = v384[1];
    if ( v384[1] )
      _InterlockedIncrement((volatile signed __int32 *)v384[1] + 2);
    *(_QWORD *)&v399 = v80;
    *((_QWORD *)&v399 + 1) = v102;
    v400 = 1;
    v103 = &v399;
  }
  std::optional<std::shared_ptr<EndpointDlp::Client::ApplicationSourceData> const>::optional<std::shared_ptr<EndpointDlp::Client::ApplicationSourceData> const>(
    &v428,
    v103,
    v72,
    v88);
  if ( !v104 || v74 )
  {
    v105 = v101 | 0x80;
    v373 = v105;
    v396 = 0;
    v106 = (std::_Ref_count_base **)v395;
  }
  else
  {
    v105 = v101 | 0x40;
    v373 = v105;
    if ( v77 )
      _InterlockedIncrement(v77 + 2);
    v380[0] = v104;
    v380[1] = (std::_Ref_count_base *)v77;
    LOBYTE(v381) = 1;
    v106 = v380;
  }
  v107 = std::optional<std::shared_ptr<EndpointDlp::Client::MarkOfTheWebData> const>::optional<std::shared_ptr<EndpointDlp::Client::MarkOfTheWebData> const>(
           &v423,
           v106);
  v392 = v100;
  v393 = v386;
  EndpointDlp::Client::ExtendedAttributes::ExtendedAttributes(&v445, v107, v108, &v392);
  if ( (v105 & 0x80u) != 0 )
  {
    v105 &= ~0x80u;
    v373 = v105;
    if ( v396 )
      std::shared_ptr<EndpointDlp::Policy::UserConfig::DlpUserConfiguration const>::~shared_ptr<EndpointDlp::Policy::UserConfig::DlpUserConfiguration const>(v395);
  }
  if ( (v105 & 0x40) != 0 )
  {
    v105 &= ~0x40u;
    v373 = v105;
    if ( (_BYTE)v381 )
    {
      v109 = v380[1];
      if ( v380[1] )
        std::_Ref_count_base::_Decref(v380[1]);
    }
  }
  if ( (v105 & 0x20) != 0 )
  {
    v105 &= ~0x20u;
    v373 = v105;
    if ( v454[0] )
      std::_Ptr_base<EndpointDlp::endpointDlpImpl>::_Decref(v453);
  }
  if ( (v105 & 0x10) != 0 )
  {
    v373 = v105 & 0xFFFFFFEF;
    if ( v400 )
    {
      v109 = (std::_Ref_count_base *)*((_QWORD *)&v399 + 1);
      if ( *((_QWORD *)&v399 + 1) )
        std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v399 + 1));
    }
  }
  v110 = v452 && v451;
  if ( (_BYTE)v73 )
  {
    *(_OWORD *)v380 = 0;
    v381 = 0;
    v400 = 0;
    if ( v450 )
    {
      v111 = v449;
      if ( v449 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v449 + 8));
        v111 = v449;
      }
      *(_QWORD *)&v399 = v448;
      *((_QWORD *)&v399 + 1) = v111;
      v400 = 1;
    }
    LOBYTE(v386) = 0;
    if ( v447 )
    {
      v112 = (std::_Ref_count_base *)v446;
      if ( v446 )
      {
        _InterlockedIncrement(v446 + 2);
        v112 = (std::_Ref_count_base *)v446;
      }
      v385[0] = (std::_Ref_count_base *)v445;
      v385[1] = v112;
      LOBYTE(v386) = 1;
    }
    v113 = (wchar_t *)v389;
    std::wstring::wstring(&v423, v389);
    Reserved = (wchar_t **)&v399;
    EndpointDlp::Client::GetRuleIdsFromFileSourceMonitoringEAs(v380, v418, &v423, v385);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v423);
    if ( v110 || v380[0] != v380[1] )
    {
      v110 = 1;
      std::vector<std::wstring>::~vector<std::wstring>(v380);
    }
    else
    {
      std::vector<std::wstring>::~vector<std::wstring>(v380);
    }
  }
  else
  {
    v113 = (wchar_t *)v389;
  }
  v404 = 0;
  if ( !v419 )
    goto LABEL_319;
  LODWORD(String2) = 0;
  v114 = v418;
  if ( v418[3] > 7uLL )
    v114 = (__int64 *)v418[0];
  v380[0] = (std::_Ref_count_base *)v114;
  v380[1] = (std::_Ref_count_base *)v418[2];
  JitFeaturesForUser = EndpointDlp::Client::GetJitFeaturesForUser(v380, &String2);
  AppBlanketEnforcementLevel = JitFeaturesForUser;
  if ( JitFeaturesForUser < 0 )
  {
    v116 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_302;
    goto LABEL_301;
  }
  v117 = *(_QWORD *)v372;
  if ( *(_BYTE *)(*(_QWORD *)v372 + 76LL) && ((unsigned int)String2 & 0x40000) != 0 )
  {
    v353 = (__int64 *)&v404;
    LODWORD(Reserved) = (_DWORD)String2;
    JitFeaturesForUser = RealtimeProtection::CRtpDlpEngine::CheckIfShadowFile(
                           *(_QWORD *)v372,
                           *(_QWORD *)&v374[1],
                           a8,
                           (unsigned int)SourceSize);
    AppBlanketEnforcementLevel = JitFeaturesForUser;
    if ( JitFeaturesForUser < 0 )
    {
      v116 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_302;
LABEL_301:
      WPP_SF_DSSd((TRACEHANDLE)v116[2], (__int64)lpString1, *(__int64 *)&v374[1], JitFeaturesForUser);
      v116 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_302;
    }
    if ( v404 )
    {
      v118 = (RealtimeProtection::DlpJitStateMachine *)WPP_GLOBAL_Control;
      v119 = *(wchar_t **)&v374[1];
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)lpString1, *(__int64 *)&v374[1]);
      if ( v405 == 3 )
        v405 = 0;
      JitExpirationTimeOut = (const wchar_t *)RealtimeProtection::DlpJitStateMachine::GetJitExpirationTimeOut(v118);
      updated = RealtimeProtection::DlpProcessCache::UpdateShadowFileStatus(
                  v376,
                  v119,
                  JitExpirationTimeOut,
                  0,
                  (bool)Reserved);
      v116 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_dSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v119, updated);
        v116 = (PVOID *)WPP_GLOBAL_Control;
        AppBlanketEnforcementLevel = 0;
        goto LABEL_320;
      }
LABEL_302:
      AppBlanketEnforcementLevel = 0;
LABEL_320:
      v117 = *(_QWORD *)v372;
      goto LABEL_321;
    }
LABEL_319:
    v116 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_320;
  }
  v116 = (PVOID *)WPP_GLOBAL_Control;
LABEL_321:
  if ( !byte_180313780 && !v110 )
  {
    if ( (_DWORD)SourceSize )
    {
      v130 = IsDlpEnabledForFile;
LABEL_385:
      v142 = lpString1;
      goto LABEL_386;
    }
    v407 = 10;
    v482[0] = _mm_load_si128((const __m128i *)&_xmm);
    v482[1] = _mm_load_si128((const __m128i *)&_xmm);
    v482[2] = _mm_load_si128((const __m128i *)&_xmm);
    v482[3] = _mm_load_si128((const __m128i *)&_xmm);
    v482[4] = _mm_load_si128((const __m128i *)&_xmm);
    v122 = *(RealtimeProtection::DlpRtpPluginQuery **)&v374[1];
    if ( a8 <= 0x10 )
    {
      v123 = 97392;
      if ( _bittest(&v123, a8) )
      {
        if ( *(_QWORD *)&v374[1] )
        {
          switch ( (unsigned int)RealtimeProtection::DlpUtils::GetFileMpExtensionId(*(_QWORD *)&v374[1]) )
          {
            case 2u:
              if ( a8 - 4 > 2 )
                goto LABEL_329;
              LOBYTE(v369) = 1;
              v116 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_331;
            case 4u:
            case 5u:
            case 6u:
            case 7u:
            case 8u:
            case 9u:
            case 0xAu:
            case 0xBu:
            case 0xCu:
            case 0xDu:
            case 0xEu:
            case 0xFu:
            case 0x10u:
            case 0x11u:
            case 0x12u:
            case 0x13u:
            case 0x14u:
            case 0x15u:
            case 0x16u:
            case 0x17u:
            case 0x18u:
            case 0x19u:
            case 0x1Au:
            case 0x1Bu:
            case 0x1Cu:
            case 0x1Eu:
            case 0x1Fu:
            case 0x20u:
            case 0x24u:
              v124 = 134305904;
              if ( _bittest(&v124, a8) )
                goto LABEL_354;
              goto LABEL_329;
            case 0x1Du:
              if ( (unsigned __int8)RealtimeProtection::DlpUtils::IsOfficeProcess(a8) )
                goto LABEL_354;
              v132 = 134308864;
              if ( !_bittest(&v132, a8) )
                goto LABEL_329;
              LOBYTE(v369) = 1;
              v116 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_331;
            case 0x26u:
            case 0x27u:
            case 0x28u:
            case 0x29u:
            case 0x2Au:
            case 0x2Bu:
              if ( a8 != 16 )
                goto LABEL_329;
LABEL_354:
              LOBYTE(v369) = 1;
              v116 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_331;
            default:
LABEL_329:
              v116 = (PVOID *)WPP_GLOBAL_Control;
              break;
          }
        }
      }
    }
    LOBYTE(v369) = 0;
LABEL_331:
    if ( (_DWORD)v375 == 1 && v374[0] && v439[2] && v419 )
    {
      AnyFileUserScope = EndpointDlp::Client::GetAnyFileUserScope(v418);
      if ( (AnyFileUserScope & 1) == 0 || RealtimeProtection::DlpRtpPluginQuery::IsAnyFilePathExcluded(v122, v125) )
        goto LABEL_356;
      v128 = (wchar_t *)v439;
      if ( v439[3] > (wchar_t *)7 )
        v128 = v439[0];
      if ( RealtimeProtection::DlpRtpPluginQuery::IsAnyFileExtensionExcluded(v128, v127) )
      {
LABEL_356:
        v130 = IsDlpEnabledForFile;
      }
      else
      {
        v130 = IsDlpEnabledForFile;
        if ( !RealtimeProtection::DlpRtpPluginQuery::IsAnyFileProcessExcluded((wchar_t *)lpString1, v129)
          && IsDlpEnabledForFile )
        {
          if ( !v419 )
            std::_Throw_bad_optional_access();
          v360 = &v405;
          v355 = v482;
          v354 = &v402;
          v353 = v418;
          *(_DWORD *)&v352[4] = HIDWORD(lpString1);
          Reserved = v439;
          v131 = RealtimeProtection::CRtpDlpEngine::GetAndUpdateExtensionBasedPolicyInternal(
                   *(_QWORD *)v372,
                   AnyFileUserScope,
                   v376,
                   (unsigned int)v374[0]);
          AppBlanketEnforcementLevel = v131;
          if ( v131 >= 0 )
          {
            v116 = (PVOID *)WPP_GLOBAL_Control;
            v109 = (std::_Ref_count_base *)v371[0];
            v366 = v371[0];
          }
          else
          {
            v116 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_DSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)lpString1, *(__int64 *)&v374[1], v131);
              v116 = (PVOID *)WPP_GLOBAL_Control;
            }
            AppBlanketEnforcementLevel = 0;
            LOBYTE(v109) = 0;
            v366 = 0;
          }
LABEL_360:
          if ( !(_BYTE)v369 && !(_BYTE)v109 && !v367 && !v404 )
          {
            v133 = Dlp::FeatureControl::GetFlag<enum Dlp::FeatureControl::OutlookAttachmentSubstitutionFlags,void,void>(
                     v109,
                     4);
            v134 = *(_QWORD *)&v374[1];
            if ( v133 )
            {
              std::wstring::wstring(&v423, *(_QWORD *)&v374[1]);
              v135 = v373 | 0x100;
              if ( (unsigned __int8)EndpointDlp::Client::IsPathFromOutlookInetCache(&v423) )
              {
                v136 = 1;
                goto LABEL_369;
              }
            }
            else
            {
              v135 = v373;
            }
            v136 = 0;
LABEL_369:
            if ( (v135 & 0x100) != 0 )
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v423);
            if ( v136 )
            {
              CbdhsvcPpid = RealtimeProtection::DlpProcessCache::AddFile(
                              (_DWORD)v376,
                              v374[0],
                              a8,
                              (_DWORD)lpString1,
                              v402 != 0,
                              v134,
                              (__int64)v420,
                              v387,
                              a17,
                              v407,
                              (__int64)v482,
                              (__int64)v412,
                              (__int64)v480,
                              v405 == 5,
                              (__int64)&v445,
                              v370);
              if ( CbdhsvcPpid < 0 )
              {
                v138 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_377;
                v139 = 192;
LABEL_376:
                WPP_SF_d(v138[2], v139, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, (unsigned int)CbdhsvcPpid);
LABEL_377:
                EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)&v445);
                if ( !v102 )
                {
LABEL_380:
                  if ( v77 )
                    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v77);
                  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v439);
                  RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v412);
                  std::optional<std::wstring>::~optional<std::wstring>(&v433);
                  v141 = (RTL_SRWLOCK *)(*(_QWORD *)v372 + 16LL);
LABEL_383:
                  ReleaseSRWLockShared(v141);
                  std::optional<std::wstring>::~optional<std::wstring>(v418);
                  RealtimeProtection::DlpAutoEtwPerfOperation::~DlpAutoEtwPerfOperation((RealtimeProtection::DlpAutoEtwPerfOperation *)v379);
                  return (unsigned int)CbdhsvcPpid;
                }
                v140 = v102;
LABEL_379:
                std::_Ref_count_base::_Decref(v140);
                goto LABEL_380;
              }
            }
            goto LABEL_421;
          }
          goto LABEL_385;
        }
      }
      v116 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      v130 = IsDlpEnabledForFile;
    }
    LOBYTE(v109) = 0;
    goto LABEL_360;
  }
  v142 = lpString1;
  AppBlanketEnforcementLevel = RealtimeProtection::CRtpDlpEngine::GetFileApplicationAccessFromPolicy(
                                 v117,
                                 v113,
                                 lpString1,
                                 (FILETIME *)v376,
                                 v374[0],
                                 (__int64)v418,
                                 0,
                                 (EndpointDlp::Client::ExtendedAttributes *)&v445,
                                 &v402,
                                 &v407,
                                 (struct DlpAction *)v482,
                                 v412,
                                 v480,
                                 &v405);
  v116 = (PVOID *)WPP_GLOBAL_Control;
  v130 = IsDlpEnabledForFile;
LABEL_386:
  if ( AppBlanketEnforcementLevel < 0 )
  {
    if ( v116 != &WPP_GLOBAL_Control && (*((_BYTE *)v116 + 28) & 1) != 0 )
      WPP_SF_d(v116[2], 193, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, (unsigned int)AppBlanketEnforcementLevel);
    std::_Optional_destruct_base<std::shared_ptr<EndpointDlp::Client::ApplicationSourceData> const,0>::~_Optional_destruct_base<std::shared_ptr<EndpointDlp::Client::ApplicationSourceData> const,0>(&v448);
    std::_Optional_destruct_base<std::shared_ptr<MipDlp::MipDlpEventInfo>,0>::~_Optional_destruct_base<std::shared_ptr<MipDlp::MipDlpEventInfo>,0>(&v445);
    if ( v102 )
      std::_Ref_count_base::_Decref(v102);
    if ( v77 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v77);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v439);
    RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v412);
    std::optional<std::wstring>::~optional<std::wstring>(&v433);
    goto LABEL_19;
  }
  v143 = v405;
  if ( (!v405 || v405 == 6) && a8 == 16 )
  {
    v371[0] = 0;
    v144 = (EndpointDlp::endpointDlpImpl **)EndpointDlp::endpointDlpImpl::GetInstance(v380);
    CbdhsvcPpid = EndpointDlp::endpointDlpImpl::endpointDlpCheckIsCloudSyncApp(*v144, v142, v371);
    if ( v380[1] )
      std::_Ref_count_base::_Decref(v380[1]);
    if ( CbdhsvcPpid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23,
        (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Client\\src\\EndpointDlpPrivateClient.cpp",
        (const char *)(unsigned int)CbdhsvcPpid,
        (int)Reserved);
      v138 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_377;
      v139 = 194;
      goto LABEL_376;
    }
    v116 = (PVOID *)WPP_GLOBAL_Control;
    if ( v371[0] == 1 )
    {
      v143 = 3;
      v405 = 3;
    }
    else
    {
      v143 = v405;
    }
  }
  if ( v404 || v368 )
  {
    if ( (_DWORD)v143 == 3 )
    {
      v143 = 0;
      v405 = 0;
    }
    goto LABEL_430;
  }
  if ( !v130 )
  {
    if ( (_DWORD)v143 != 3 )
    {
      if ( v116 != &WPP_GLOBAL_Control && (*((_BYTE *)v116 + 28) & 4) != 0 )
      {
        v145 = v412;
        if ( v414 > 7 )
          v145 = (__int64 *)v412[0];
        v146 = Src;
        if ( v417 > 7 )
          v146 = (__int64 *)Src[0];
        WPP_SF_DSSSS((TRACEHANDLE)v116[2], (__int64)lpString1, *(__int64 *)&v374[1], (__int64)v146, (__int64)v145);
      }
      *v388 = 0;
      if ( v378 )
        *(_DWORD *)v378 = 6;
LABEL_421:
      EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)&v445);
      if ( !v102 )
      {
LABEL_709:
        if ( v77 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v77);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v439);
        RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v412);
        std::optional<std::wstring>::~optional<std::wstring>(&v433);
        ReleaseSRWLockShared((PSRWLOCK)(*(_QWORD *)v372 + 16LL));
LABEL_899:
        std::optional<std::wstring>::~optional<std::wstring>(v418);
        goto LABEL_900;
      }
      v147 = v102;
LABEL_708:
      std::_Ref_count_base::_Decref(v147);
      goto LABEL_709;
    }
LABEL_430:
    v149 = (*(_DWORD *)(*(_QWORD *)v372 + 80LL) & 0x8000) == 0 && (_DWORD)SourceSize;
    v150 = 0;
    if ( v407 )
    {
      while ( *((_DWORD *)v482 + 2 * v150) == v150 )
      {
        if ( !v149 )
          v149 = *((_DWORD *)v482 + 2 * v150 + 1) != 0;
        if ( ++v150 >= v407 )
          goto LABEL_439;
      }
      if ( v116 == &WPP_GLOBAL_Control || (*((_BYTE *)v116 + 28) & 1) == 0 )
        goto LABEL_578;
      v148 = 197;
      goto LABEL_427;
    }
LABEL_439:
    LOBYTE(v151) = v369;
    v152 = *(_QWORD *)&v374[1];
    if ( *(_BYTE *)(*(_QWORD *)v372 + 76LL)
      && *(_BYTE *)(*(_QWORD *)v372 + 77LL)
      && !v149
      && !(_BYTE)v369
      && v407
      && (_DWORD)SourceSize )
    {
      v151 = !RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance::IsJitFileExcluded(*(const wchar_t **)&v374[1]);
      v369 = v151;
      v116 = (PVOID *)WPP_GLOBAL_Control;
      v143 = v405;
    }
    if ( v116 != &WPP_GLOBAL_Control && (*((_BYTE *)v116 + 28) & 4) != 0 )
    {
      LODWORD(v354) = v143;
      LODWORD(v353) = v404;
      *(_DWORD *)v352 = v151;
      LODWORD(Reserved) = v149;
      WPP_SF_ddddd(
        v116[2],
        198,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        4507,
        Reserved,
        *(_QWORD *)v352,
        v353,
        v354);
      v116 = (PVOID *)WPP_GLOBAL_Control;
      v143 = v405;
    }
    v153 = (unsigned int)SourceSize;
    if ( (!(_DWORD)SourceSize || !Source) && v116 != &WPP_GLOBAL_Control && (*((_BYTE *)v116 + 28) & 1) != 0 )
    {
      WPP_SF_dddS((TRACEHANDLE)v116[2], v151, v149, v152);
      v143 = v405;
      v153 = (unsigned int)SourceSize;
    }
    if ( (((_DWORD)v375 - 4) & 0xFFFFFFFD) != 0 )
    {
LABEL_474:
      v163 = *(_QWORD *)v372;
      if ( (*(_DWORD *)(*(_QWORD *)v372 + 112LL) & 1) != 0
        && (*(_DWORD *)(*(_QWORD *)v372 + 112LL) & 8) != 0
        && GetTickCount64() > *(_QWORD *)(v163 + 120) + 21600000LL )
      {
        RealtimeProtection::MpLogMessageImpl(
          (RealtimeProtection *)L"DLP::CheckAccessForFile: It's time to dump the user agent process cache into a file",
          v164);
        v165 = operator new(0x48u);
        *(_OWORD *)v165 = 0;
        *((_OWORD *)v165 + 1) = 0;
        *((_OWORD *)v165 + 2) = 0;
        *((_OWORD *)v165 + 3) = 0;
        *((_QWORD *)v165 + 8) = 0;
        PluginWorkItemQueue = RealtimeProtection::DlpPlugin::GetPluginWorkItemQueue(v166);
        RealtimeProtection::CMpPluginWorkItemBase::CMpPluginWorkItemBase(v165, PluginWorkItemQueue, 34);
        *(_QWORD *)v165 = &RealtimeProtection::CDlpDumpUserAgentProcessCacheWorkItem::`vftable';
        _InterlockedIncrement((volatile signed __int32 *)v165 + 2);
        RealtimeProtection::CMpPluginWorkItemBase::PrioritizedDispatchJob(v165, 9);
        *(_QWORD *)(*(_QWORD *)v372 + 120LL) = GetTickCount64();
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v165 + 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (**(void (__fastcall ***)(void *, __int64))v165)(v165, 1);
        }
      }
      v168 = (const wchar_t *)(unsigned int)v375;
      if ( (_DWORD)v375 == 6 )
      {
        *v388 = 0;
        if ( v378 )
          *(_DWORD *)v378 = 7;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), v152);
        std::_Optional_destruct_base<std::shared_ptr<EndpointDlp::Client::ApplicationSourceData> const,0>::~_Optional_destruct_base<std::shared_ptr<EndpointDlp::Client::ApplicationSourceData> const,0>(&v448);
        std::_Optional_destruct_base<std::shared_ptr<MipDlp::MipDlpEventInfo>,0>::~_Optional_destruct_base<std::shared_ptr<MipDlp::MipDlpEventInfo>,0>(&v445);
        if ( !v102 )
          goto LABEL_709;
        v147 = v102;
        goto LABEL_708;
      }
      v172 = v367;
      if ( !v149 && !(_BYTE)v369 && !v366 && !v367 && !v404 )
      {
        v173 = v405;
        if ( v405 == 3 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), v152);
          v174 = v376;
          RealtimeProtection::DlpProcessCache::UpdateQuarantineStatusByFileName(v376, v152, 6, v143);
          v173 = v405;
          LODWORD(v168) = (_DWORD)v375;
        }
        else
        {
          v174 = v376;
        }
        *v388 = 0;
        if ( v378 )
          *(_DWORD *)v378 = 7;
        if ( (_DWORD)v168 == 4 )
        {
          v175 = lpString1;
          v176 = RealtimeProtection::DlpProcessCache::UpdateFile(
                   v174,
                   v387,
                   v407,
                   (__int64)v482,
                   (__int64)v412,
                   (__int64)v480,
                   v173 == 5,
                   SourceSize,
                   (__int64)Source,
                   v370);
          if ( v176 >= 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                205,
                (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                v152,
                (__int64)v175);
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v175, v176);
          }
        }
        goto LABEL_421;
      }
      if ( v405 && v405 != 6 )
      {
        v177 = (WCHAR *)lpString1;
        goto LABEL_532;
      }
      v177 = (WCHAR *)lpString1;
      if ( RealtimeProtection::DlpEngineUtils::IsUnallowedRDPApp(
             (RealtimeProtection::DlpEngineUtils *)lpString1,
             (const wchar_t *)(unsigned int)v375) )
      {
        if ( v407 > 8 && DWORD1(v482[4]) )
        {
          v178 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_530;
          goto LABEL_529;
        }
        if ( v172 )
        {
          v178 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_530;
LABEL_529:
          WPP_SF_dS(v178[2], (__int64)v177);
LABEL_530:
          v405 = 4;
        }
      }
LABEL_532:
      IsSupported3PBrowserProcess = RealtimeProtection::DlpUtils::IsSupported3PBrowserProcess(v177, v168);
      if ( IsSupported3PBrowserProcess
        && !(unsigned int)Dlp::BrowserCache::IsBrowserCacheEnabled(v177, (const wchar_t *)(unsigned int)v374[0], v180) )
      {
        v402 = 0;
      }
      v403 = 0;
      *(_OWORD *)v455 = 0;
      v456 = 0;
      v457 = 7;
      LOWORD(v455[0]) = 0;
      v458 = 0;
      v459 = 0;
      v460 = 7;
      LOWORD(v458) = 0;
      v181 = 0;
      v365 = 0;
      v441 = 0;
      LOWORD(v409) = 0;
      memset(v481, 0, 0x498u);
      v406 = 1;
      *(_OWORD *)v436 = 0;
      v437 = 0;
      v183 = 7;
      v438 = 7;
      LOWORD(v436[0]) = 0;
      *(_OWORD *)v442 = 0;
      v443 = 0;
      v444 = 7;
      LOWORD(v442[0]) = 0;
      v410 = 0;
      v184 = (unsigned int)v375;
      if ( (unsigned int)((_DWORD)v375 - 4) <= 1 )
      {
        if ( v402 )
        {
          v185 = 6;
        }
        else if ( v405 == 2 )
        {
          v185 = 7;
        }
        else
        {
          v185 = 8;
          if ( v405 != 4 )
            v185 = 5;
        }
        v369 = v185;
        v397 = *((_DWORD *)v482 + 2 * v185 + 1);
        v398 = 1;
        if ( v378 )
          *(_DWORD *)v378 = 8;
      }
      else
      {
        if ( v402 )
        {
          v185 = 6;
          v369 = 6;
          v186 = (const struct std::nothrow_t *)v366;
          v187 = v378;
          if ( v366 )
          {
            v397 = 0;
            v398 = 1;
            if ( v378 )
              *(_DWORD *)v378 = 0;
            goto LABEL_621;
          }
          v397 = 3;
          v398 = 2;
          if ( v378 )
          {
            v188 = *(_QWORD *)v372;
LABEL_584:
            v201 = 3;
            if ( !*(_DWORD *)(v188 + 52) )
              v201 = 1;
            *(_DWORD *)v187 = v201;
            goto LABEL_622;
          }
LABEL_621:
          LODWORD(v188) = v372[0];
          goto LABEL_622;
        }
        v189 = a8;
        if ( v405 == 6 )
        {
          LODWORD(Reserved) = a8;
          v190 = RealtimeProtection::CRtpDlpEngine::CheckAnyAppExclusion(
                   *(_QWORD *)v372,
                   (unsigned int)v374[0],
                   v376,
                   v177,
                   Reserved);
          v191 = *(_QWORD *)v372;
          if ( v190 )
          {
            v405 = 0;
            HIDWORD(v482[2]) = 0;
          }
          else
          {
            v192 = *(_DWORD *)(*(_QWORD *)v372 + 116LL);
            if ( v192 )
            {
              RealtimeProtection::MpLogMessageImpl(
                (RealtimeProtection *)L"DLP::CheckAccessForfile: Using any app enforcement from signature",
                v182);
              HIDWORD(v482[2]) = v192;
              v191 = *(_QWORD *)v372;
            }
            v189 = a8;
          }
          v183 = 7;
        }
        else
        {
          v191 = *(_QWORD *)v372;
        }
        if ( v405 != 2 )
        {
          v183 = 8;
          if ( v405 != 4 )
            v183 = 5;
        }
        v369 = v183;
        if ( IsSupported3PBrowserProcess && v405 != 6 )
        {
          LODWORD(String2) = 0;
          v369 = 6;
          LODWORD(Reserved) = v374[0];
          v193 = RealtimeProtection::CRtpDlpEngine::CheckAccessForBrowsers(
                   v191,
                   *(wchar_t **)&v374[1],
                   *(struct _FILETIME *)v390,
                   v177,
                   (wchar_t *)Reserved,
                   (__int64)v376,
                   v189,
                   (__int64)v418,
                   a17,
                   (__int64)&v445,
                   &String2,
                   v481,
                   (_BYTE *)&v409 + 1,
                   &v406,
                   v455,
                   v442,
                   v436,
                   &v409,
                   v461,
                   (__int64)v440,
                   v404);
          if ( v193 < 0 || v193 == 1 )
          {
            v369 = 5;
          }
          else
          {
            DWORD1(v482[3]) = (_DWORD)String2;
            if ( (_DWORD)String2 )
              v365 = 1;
          }
        }
        v194 = v369;
        v195 = *((_DWORD *)v482 + 2 * v369 + 1);
        v397 = v195;
        if ( !v195 || (v196 = v195 - 1) == 0 )
        {
LABEL_606:
          v398 = 1;
          v185 = v369;
          v181 = v365;
          LODWORD(v188) = v372[0];
          v186 = (const struct std::nothrow_t *)v366;
          if ( v378 )
          {
            v205 = 2;
            if ( !v397 )
              v205 = 7;
            *(_DWORD *)v378 = v205;
          }
          v184 = (unsigned int)v375;
          goto LABEL_622;
        }
        v197 = v196 - 1;
        if ( v197 )
        {
          v198 = v197 - 1;
          if ( !v198 )
          {
            v398 = 2;
            v187 = v378;
            v188 = *(_QWORD *)v372;
            v185 = v369;
            v181 = v365;
            v186 = (const struct std::nothrow_t *)v366;
            v184 = (unsigned int)v375;
            if ( !v378 )
              goto LABEL_622;
            goto LABEL_584;
          }
          if ( v198 != 1 )
          {
            v199 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_573;
            v200 = 210;
LABEL_572:
            WPP_SF_d(v199[2], v200, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, 2147549183LL);
LABEL_573:
            if ( v410 )
              operator delete(v410, (const struct std::nothrow_t *)v182);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v442);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v436);
            if ( v441 )
              std::string::_Tidy_deallocate(v440);
            RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v455);
            goto LABEL_578;
          }
          if ( !(unsigned __int8)Dlp::FeatureControl::GetBoolValue(132, v182) )
          {
            v199 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_573;
            v200 = 208;
            goto LABEL_572;
          }
          goto LABEL_606;
        }
        if ( v410 )
          operator delete(v410, (const struct std::nothrow_t *)v182);
        v202 = RealtimeProtection::DlpProcessCache::CheckIfBypassed(
                 (unsigned int)&v403,
                 (unsigned int)&v410,
                 (_DWORD)v376,
                 v374[0],
                 (__int64)v177,
                 v194,
                 *(__int64 *)&v374[1],
                 *(__int64 *)v390);
        CbdhsvcPpid = v202;
        if ( v202 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              209,
              &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
              (unsigned int)v202);
          if ( v410 )
            operator delete(v410, v203);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v442);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v436);
          if ( v441 )
            std::string::_Tidy_deallocate(v440);
          RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v455);
          goto LABEL_377;
        }
        if ( !v403 )
        {
          v398 = 2;
          LODWORD(v188) = v372[0];
          v185 = v369;
          v181 = v365;
          v186 = (const struct std::nothrow_t *)v366;
          v184 = (unsigned int)v375;
          if ( v378 )
          {
            v204 = 4;
            if ( !*(_DWORD *)(*(_QWORD *)v372 + 52LL) )
              v204 = 1;
            *(_DWORD *)v378 = v204;
          }
LABEL_622:
          v206 = v370 && (v185 < 2 || v185 == 6 || v185 - 7 <= 1) && v435;
          if ( !v402 && v185 == 6 && !v181 && (_DWORD)v184 == 1 && IsSupported3PBrowserProcess == 1 )
          {
            v207 = 1;
            v206 = 0;
          }
          else
          {
            v207 = 0;
            if ( (unsigned int)(v184 - 4) <= 1 )
              goto LABEL_685;
          }
          if ( !(_BYTE)v409 && !(_BYTE)v186 )
          {
            v208 = (WCHAR *)lpString1;
            if ( v207 )
              goto LABEL_686;
            LODWORD(String2) = 0;
            v479 = 0;
            v209 = *(__int64 **)&v374[1];
            v210 = RealtimeProtection::CRtpDlpEngine::AdjustEnforcementByJit(
                     v188,
                     v185,
                     v374[1],
                     (_DWORD)lpString1,
                     (__int64)v376,
                     v374[0],
                     a17,
                     0,
                     0,
                     SourceSize,
                     (__int64)Source,
                     0,
                     (__int64)Src,
                     (__int64)&v397,
                     (__int64)&String2,
                     0,
                     0,
                     (__int64)&v465);
            if ( v479 )
              RealtimeProtection::FileEvaluationContext::~FileEvaluationContext((RealtimeProtection::FileEvaluationContext *)&v465);
            if ( v210 < 0 )
            {
              v186 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v209);
            }
            else
            {
              v213 = (char)String2;
              if ( (_DWORD)String2 )
              {
                if ( v397 - 2 <= 1 )
                {
                  v229 = v378;
                  if ( v378 )
                    *(_DWORD *)v378 = 12;
                  v398 = 2;
                  v186 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  {
                    v230 = v412;
                    if ( v414 > 7 )
                      v230 = (__int64 *)v412[0];
                    v209 = Src;
                    if ( v417 > 7 )
                      v209 = (__int64 *)Src[0];
                    v231 = L"true";
                    if ( (_DWORD)SourceSize )
                      v231 = L"false";
                    v232 = *((_DWORD *)v376 + 2);
                    if ( v229 )
                      v229 = (RealtimeProtection::DlpProcessCache *)*(unsigned int *)v229;
                    RealtimeProtection::DlpUtils::MpDlpResultAccessReasonToStr(v229, &WPP_GLOBAL_Control, v211, v212);
                    RealtimeProtection::DlpUtils::DlpActionTypeToStr(v369, v233, v234);
                    v237 = RealtimeProtection::DlpUtils::MpDlpResultAccessDecisionToStr(2, v235, v236);
                    v239 = RealtimeProtection::DlpUtils::DlpFileAccessCheckTypeToStr((unsigned int)v375, v238, v237);
                    v358 = (__int64)v209;
                    v357 = (__int64)v231;
                    LODWORD(v209) = v374[1];
                    v208 = (WCHAR *)lpString1;
                    WPP_SF_SSSSDSSSSSD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      211,
                      v240,
                      v239,
                      v240,
                      v241,
                      v242,
                      v232,
                      (__int64)lpString1,
                      *(__int64 *)&v374[1],
                      v357,
                      v358,
                      (__int64)v230,
                      v213);
                  }
                  HIDWORD(v461[0]) = 3;
                  v184 = 1;
                  LODWORD(v461[1]) = 1;
                  v185 = v369;
                  if ( v369 != 8 && v369 != 7 )
                    goto LABEL_660;
                  v479 = 0;
                  v374[0] = v369;
                  RealtimeProtection::DlpJitStateMachine::AddFileToBlockedBySyncClassificationCache(
                    (_DWORD)v209,
                    (_DWORD)v376,
                    (_DWORD)v208,
                    (unsigned int)v374,
                    (_DWORD)Reserved,
                    *(_DWORD *)v352,
                    (__int64)v411,
                    (__int64)&v465);
                  if ( v479 )
                    RealtimeProtection::FileEvaluationContext::~FileEvaluationContext((RealtimeProtection::FileEvaluationContext *)&v465);
                  v374[0] = v411[0];
                  goto LABEL_659;
                }
                if ( v397 == 1 || v397 == 4 )
                {
                  v184 = 1;
                  v398 = 1;
                  HIDWORD(v461[0]) = 3;
                  LODWORD(v461[1]) = 3;
                  v186 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                  {
                    v185 = v369;
LABEL_660:
                    if ( v397 - 2 > 1 )
                      v398 = 1;
LABEL_686:
                    if ( !v206 || !v435 || v398 == 2 || v405 == 3 )
                    {
                      v244 = v376;
                      v243 = *(wchar_t **)&v374[1];
                    }
                    else
                    {
                      v398 = 2;
                      v397 = 3;
                      if ( v378 )
                        *(_DWORD *)v378 = 14;
                      std::wstring::wstring(&v428, v208);
                      std::wstring::wstring(&v392, v412);
                      v394 = 1;
                      v454[16] = 0;
                      v243 = *(wchar_t **)&v374[1];
                      std::wstring::wstring(&v423, *(_QWORD *)&v374[1]);
                      LODWORD(v354) = v374[0];
                      v244 = v376;
                      LODWORD(Reserved) = v185;
                      v245 = RealtimeProtection::CRtpDlpEngine::CreateAndRaiseEventsForTrustContainerEncryptionRequest(
                               *(_QWORD *)v372,
                               &v423,
                               v453,
                               &v392,
                               Reserved,
                               &v428,
                               v376,
                               v354,
                               &v433);
                      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v423);
                      std::optional<std::wstring>::~optional<std::wstring>(v453);
                      std::optional<std::wstring>::~optional<std::wstring>(&v392);
                      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v428);
                      if ( v245 < 0
                        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v243);
                      }
                    }
                    if ( v398 != 1 )
                    {
LABEL_809:
                      if ( (unsigned int)((_DWORD)v375 - 4) <= 1 )
                        goto LABEL_880;
                      if ( *(_BYTE *)(v387 + 64) )
                      {
                        v277 = (RealtimeProtection::DlpProcessCache *)std::optional<RealtimeProtection::FileUniqueId>::value(v387);
                        if ( !RealtimeProtection::DlpProcessCache::IsFileAccessAllowedByQuarantineStatus(v277, v278)
                          || v405 == 3 )
                        {
                          v411[0] = 0;
                          v279 = v370 && v435;
                          v280 = (__int64)v410;
                          v281 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(Src);
                          v282 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v412);
                          v283 = v405;
                          v284 = v397;
                          v285 = std::optional<RealtimeProtection::FileUniqueId>::value(v387);
                          LOBYTE(v360) = v279;
                          v359 = v280;
                          LODWORD(v354) = v283;
                          LODWORD(v353) = v284;
                          *(_DWORD *)v352 = v374[0];
                          v286 = v376;
                          v270 = *(_QWORD *)v372;
                          CbdhsvcPpid = RealtimeProtection::CRtpDlpEngine::CheckQuarantineForCloudSyncApp(
                                          *(_QWORD *)v372,
                                          v376,
                                          lpString1,
                                          *(_QWORD *)&v374[1],
                                          v285,
                                          *(_QWORD *)v352,
                                          v353,
                                          v354,
                                          v282,
                                          v281,
                                          v480,
                                          v359,
                                          v360,
                                          &v433,
                                          SourceSize,
                                          Source,
                                          &v398,
                                          v411);
                          if ( CbdhsvcPpid < 0 )
                          {
                            v271 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                            {
                              goto LABEL_785;
                            }
                            v272 = 226;
                            goto LABEL_784;
                          }
                          v287 = v365;
                          if ( v378 )
                            *(_DWORD *)v378 = v411[0];
LABEL_882:
                          v326 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                          {
                            v327 = L"true";
                            v328 = L"true";
                            if ( !v366 )
                              v328 = L"false";
                            v329 = L"true";
                            if ( !v287 )
                              v329 = L"false";
                            v330 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v412);
                            v334 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(Src);
                            if ( (_DWORD)SourceSize )
                              v327 = L"false";
                            v420 = v327;
                            v335 = *((_DWORD *)v286 + 2);
                            v336 = 0;
                            v337 = v403 != 0;
                            if ( v378 )
                              v336 = *(_DWORD *)v378;
                            v338 = RealtimeProtection::DlpUtils::MpDlpResultAccessReasonToStr(v336, v331, v332, v333);
                            RealtimeProtection::DlpUtils::DlpEnforcementLevelToStr(v397);
                            RealtimeProtection::DlpUtils::DlpActionTypeToStr(v369, v339, v340);
                            v343 = RealtimeProtection::DlpUtils::MpDlpResultAccessDecisionToStr(v398, v341, v342);
                            v345 = RealtimeProtection::DlpUtils::DlpFileAccessCheckTypeToStr(
                                     (unsigned int)v375,
                                     v344,
                                     v343);
                            WPP_SF_SSSSSdDSSSSSSS(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              v346,
                              v347,
                              v345,
                              v347,
                              v348,
                              v349,
                              v338,
                              v337,
                              v335,
                              (__int64)lpString1,
                              *(__int64 *)&v374[1],
                              (__int64)v420,
                              v334,
                              v330,
                              (__int64)v329,
                              (__int64)v328);
                          }
                          if ( v410 )
                            operator delete(v410, v326);
                          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v442);
                          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v436);
                          std::_Non_trivial_move<std::_Optional_construct_base<std::string>,std::string>::~_Non_trivial_move<std::_Optional_construct_base<std::string>,std::string>(v440);
                          RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v455);
                          EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)&v445);
                          std::_Ptr_base<EndpointDlp::endpointDlpImpl>::_Decref(v384);
                          std::shared_ptr<EndpointDlp::Policy::UserConfig::DlpUserConfiguration const>::~shared_ptr<EndpointDlp::Policy::UserConfig::DlpUserConfiguration const>(&v401);
                          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v439);
                          RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v412);
                          std::optional<std::wstring>::~optional<std::wstring>(&v433);
                          ReleaseSRWLockShared((PSRWLOCK)(*(_QWORD *)v372 + 16LL));
                          v350 = v398;
                          if ( v398 == 1 && v382 == 1 )
                          {
                            v350 = 3;
                            v398 = 3;
                          }
                          *v388 = v350;
                          goto LABEL_899;
                        }
                      }
                      if ( !v397 )
                        goto LABEL_880;
                      v288 = 0;
                      if ( v378 )
                        v288 = *(_DWORD *)v378 == 14;
                      if ( v185 == 6 )
                      {
                        v287 = v365;
                        if ( v365 == 1 )
                          RealtimeProtection::MpDlpPolicyTraceInfo::operator=(v412, v455);
                        std::wstring::wstring(&v423);
                        if ( BYTE1(v409) )
                        {
                          v291 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v436);
                          RealtimeProtection::DlpEngineUtils::PrepareDlpEventGroupsOverrideJson(
                            (unsigned int)v481,
                            (unsigned int)&v481[18] + 2,
                            v291,
                            6,
                            (__int64)&v423);
                        }
                        if ( v397 == 1 && (RealtimeProtection::DlpProcessCache::GetCacheSettings(v290) & 4) != 0 )
                        {
                          v477[0] = 0;
                          std::wstring::wstring(&v465);
                          std::wstring::wstring(&v468);
                          std::wstring::wstring(&v471);
                          std::wstring::wstring(&v474);
                          *(_DWORD *)((char *)v477 + 2) = 0;
                          HIWORD(v477[0]) = 0;
                          std::wstring::operator=(&v465, *(void **)&v374[1]);
                          v292 = Src;
                          if ( v365 )
                            v292 = (__int64 *)&v458;
                          std::wstring::operator=(&v468, v292);
                          LOBYTE(v477[0]) = v403;
                          BYTE1(v477[0]) = v406;
                          std::wstring::operator=(&v471, v436);
                          std::wstring::operator=(&v474, v442);
                          if ( RealtimeProtection::DlpThrottle::DlpCloudEgressThrottling::AddAndCheckThrottled(
                                 (RealtimeProtection::DlpThrottle::DlpCloudEgressThrottling *)&v465,
                                 v293) )
                          {
                            v288 = 1;
                            v294 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                            {
                              v295 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v474);
                              v296 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v471);
                              v297 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v468);
                              std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v465);
                              WPP_SF_SSSSdd(v294[2], v297, v296, v295, SBYTE1(v477[0]), (char)v477[0]);
                            }
                            v287 = v365;
                          }
                          RealtimeProtection::MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS::~MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS((RealtimeProtection::MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS *)&v465);
                        }
                        if ( v288 )
                        {
                          v286 = v376;
                          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v423);
                        }
                        else
                        {
                          std::vector<RealtimeProtection::DlpEngineTelemetry::DlpTelemetryEvent>::__autoclassinit2(
                            v453,
                            v289);
                          if ( v287 )
                          {
                            v298 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(Src);
                            v299 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v423);
                            v300 = v406;
                            v373 |= 0x200u;
                            v301 = (std::_Ref_count_base **)std::optional<std::string>::optional<std::string>(
                                                              &v392,
                                                              v440);
                          }
                          else
                          {
                            v298 = &qword_18025C818;
                            v299 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v423);
                            v373 |= 0x400u;
                            v432 = 0;
                            v301 = &v428;
                            v300 = v406;
                          }
                          v302 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v436);
                          v303 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v412);
                          v304 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(Src);
                          v363 = (__int64)v298;
                          v361 = (__int64)v301;
                          v287 = v365;
                          v286 = v376;
                          RealtimeProtection::DlpEngineTelemetry::GenerateDlpTelemetryEvent(
                            (unsigned int)v453,
                            v304,
                            v303,
                            v397,
                            6,
                            *(_DWORD *)(*(_QWORD *)v372 + 88LL),
                            *(__int64 *)&v374[1],
                            v302,
                            (__int64)lpString1,
                            (__int64)v376,
                            v374[0],
                            v403,
                            (__int64)v410,
                            0,
                            (__int64)v461,
                            v365,
                            v361,
                            0,
                            (__int64)v480,
                            (__int64)&v480[146],
                            v300,
                            v299,
                            0,
                            v363,
                            (__int64)&qword_18025C818,
                            0);
                          v306 = v373;
                          if ( (v373 & 0x400) != 0 )
                          {
                            v306 = v373 & 0xFBFF;
                            std::_Non_trivial_move<std::_Optional_construct_base<std::string>,std::string>::~_Non_trivial_move<std::_Optional_construct_base<std::string>,std::string>(&v428);
                          }
                          if ( (v306 & 0x200) != 0 )
                            std::_Non_trivial_move<std::_Optional_construct_base<std::string>,std::string>::~_Non_trivial_move<std::_Optional_construct_base<std::string>,std::string>(&v392);
                          RealtimeProtection::CRtpDlpEngine::SendDlpTelemetryEvent(v305, v453);
                          std::vector<RealtimeProtection::DlpEngineTelemetry::DlpTelemetryEvent>::_Tidy(v453);
                          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v423);
                        }
                        goto LABEL_882;
                      }
                      if ( v185 == 5 )
                      {
                        CacheSettings = RealtimeProtection::DlpProcessCache::GetCacheSettings(v378);
                        v309 = RealtimeProtection::DlpProcessCache::GetCacheSettings(v308) & 8;
                        if ( (CacheSettings & 0x10) != 0 && v397 - 2 > 1 && v405 == 6 )
                        {
                          v427 = 0;
                          std::wstring::wstring(&v423);
                          std::wstring::wstring(v425);
                          std::wstring::wstring(v426);
                          *(_DWORD *)((char *)&v427 + 1) = 0;
                          *(_WORD *)((char *)&v427 + 5) = 0;
                          HIBYTE(v427) = 0;
                          std::wstring::operator=(&v423, v208);
                          std::wstring::operator=(v425, *(void **)&v374[1]);
                          v310 = Src;
                          if ( v365 )
                            v310 = (__int64 *)&v458;
                          std::wstring::operator=(v426, v310);
                          LOBYTE(v427) = v403;
                          if ( RealtimeProtection::DlpThrottle::DlpAnyAppThrottling::AddAndCheckThrottled(
                                 (RealtimeProtection::DlpThrottle::DlpAnyAppThrottling *)&v423,
                                 v311) )
                          {
                            v288 = 1;
                            v312 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                            {
                              v313 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v426);
                              v314 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v425);
                              std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v423);
                              WPP_SF_SSSd(v312[2], v314, v313, v427);
                            }
                          }
                          RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent::~DlpThrottleAnyAppEvent((RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent *)&v423);
                        }
                        else if ( v309 )
                        {
                          *(_OWORD *)v426 = 0;
                          std::wstring::wstring(&v423);
                          std::wstring::wstring(v425);
                          *(_DWORD *)&v426[10] = 0;
                          *(_WORD *)&v426[14] = 0;
                          std::wstring::operator=(&v423, *(void **)&v374[1]);
                          v319 = Src;
                          v315 = v365;
                          if ( v365 )
                            v319 = (__int64 *)&v458;
                          std::wstring::operator=(v425, v319);
                          v426[8] = v403;
                          v426[9] = v406;
                          *(_DWORD *)&v426[4] = v405;
                          *(_DWORD *)v426 = a8;
                          if ( RealtimeProtection::DlpThrottle::DlpUnallowedAppsThrottling::AddAndCheckThrottled(
                                 (RealtimeProtection::DlpThrottle::DlpUnallowedAppsThrottling *)&v423,
                                 v320) )
                          {
                            v288 = 1;
                            v321 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                            {
                              v322 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v425);
                              std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v423);
                              WPP_SF_SSdddd(v321[2], v322, v426[4], v426[0], v426[9], v426[8]);
                            }
                          }
                          RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)&v423);
LABEL_863:
                          if ( !v288 )
                          {
                            std::vector<RealtimeProtection::DlpEngineTelemetry::DlpTelemetryEvent>::__autoclassinit2(
                              v453,
                              v186);
                            v316 = v405;
                            if ( v315 )
                            {
                              v317 = v373 | 0x800;
                              v318 = (__int128 *)std::optional<std::string>::optional<std::string>(&v428, v440);
                            }
                            else
                            {
                              v317 = v373 | 0x1000;
                              v425[0] = 0;
                              v318 = &v423;
                            }
                            v323 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v412);
                            v324 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(Src);
                            v362 = v316;
                            v286 = v376;
                            RealtimeProtection::DlpEngineTelemetry::GenerateDlpTelemetryEvent(
                              (unsigned int)v453,
                              v324,
                              v323,
                              v397,
                              v185,
                              *(_DWORD *)(*(_QWORD *)v372 + 88LL),
                              *(__int64 *)&v374[1],
                              0,
                              (__int64)lpString1,
                              (__int64)v376,
                              v374[0],
                              v403,
                              (__int64)v410,
                              0,
                              (__int64)v461,
                              v365,
                              (__int64)v318,
                              v362,
                              (__int64)v480,
                              (__int64)&v480[146],
                              1,
                              (__int64)&qword_18025C818,
                              0,
                              (__int64)&qword_18025C818,
                              (__int64)&qword_18025C818,
                              0);
                            if ( (v317 & 0x1000) != 0 )
                            {
                              v317 &= ~0x1000u;
                              std::_Non_trivial_move<std::_Optional_construct_base<std::string>,std::string>::~_Non_trivial_move<std::_Optional_construct_base<std::string>,std::string>(&v423);
                            }
                            if ( (v317 & 0x800) != 0 )
                              std::_Non_trivial_move<std::_Optional_construct_base<std::string>,std::string>::~_Non_trivial_move<std::_Optional_construct_base<std::string>,std::string>(&v428);
                            RealtimeProtection::CRtpDlpEngine::SendDlpTelemetryEvent(v325, v453);
                            std::vector<RealtimeProtection::DlpEngineTelemetry::DlpTelemetryEvent>::_Tidy(v453);
                            goto LABEL_881;
                          }
LABEL_880:
                          v286 = v376;
LABEL_881:
                          v287 = v365;
                          goto LABEL_882;
                        }
                      }
                      v315 = v365;
                      goto LABEL_863;
                    }
                    if ( (_DWORD)v375 == 4 )
                    {
                      HIDWORD(v482[2]) = 0;
                      v246 = RealtimeProtection::DlpProcessCache::UpdateFile(
                               v376,
                               v387,
                               v407,
                               (__int64)v482,
                               (__int64)v412,
                               (__int64)v480,
                               v405 == 5,
                               SourceSize,
                               (__int64)Source,
                               v370);
                      CbdhsvcPpid = v246;
                      if ( v246 == 1 )
                      {
                        *v388 = 0;
                        if ( v378 )
                          *(_DWORD *)v378 = 6;
                        if ( v410 )
                          operator delete(v410, v247);
                        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v442);
                        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v436);
                        if ( v441 )
                          std::string::_Tidy_deallocate(v440);
                        RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v455);
                        EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)&v445);
                        if ( !v384[1] )
                          goto LABEL_709;
                        v147 = v384[1];
                        goto LABEL_708;
                      }
                      if ( v246 < 0 )
                      {
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            215,
                            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                            (unsigned int)v246);
                        if ( v410 )
                          operator delete(v410, v247);
LABEL_718:
                        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v442);
                        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v436);
                        if ( v441 )
                          std::string::_Tidy_deallocate(v440);
                        RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v455);
                        EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)&v445);
                        if ( !v384[1] )
                          goto LABEL_380;
                        v140 = v384[1];
                        goto LABEL_379;
                      }
LABEL_751:
                      IsJitProcessExcluded = 0;
                      if ( (unsigned __int8)RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance::IsJitRuleId(Src) )
                      {
                        IsJitProcessExcluded = RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance::IsJitProcessExcluded(v208);
                        IsJitFileExcluded = RealtimeProtection::DlpJitStateMachine::DlpJitStateMachineInstance::IsJitFileExcluded(v243);
                        v259 = *(_QWORD *)v372;
                        if ( !*(_BYTE *)(*(_QWORD *)v372 + 76LL) || IsJitProcessExcluded || IsJitFileExcluded )
                          IsJitProcessExcluded = 1;
                      }
                      else
                      {
                        v259 = *(_QWORD *)v372;
                      }
                      v260 = HIDWORD(v482[1]) && *(_DWORD *)(v259 + 72) == 2;
                      if ( *(_BYTE *)(v259 + 109) || !IsJitProcessExcluded && (DWORD1(v482[1]) || v260) )
                      {
                        v261 = v376;
                        v262 = RealtimeProtection::DlpInjection::InjectEnforcementDllAsync(
                                 (RealtimeProtection::DlpInjection *)*(unsigned int *)(*(_QWORD *)v372 + 56LL),
                                 v376,
                                 (const struct PPID *)v208,
                                 v257);
                        CbdhsvcPpid = v262;
                        v264 = (PVOID *)WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                        {
                          WPP_SF_SLSD(*((_QWORD *)WPP_GLOBAL_Control + 2), *((_DWORD *)v261 + 2), (__int64)v243, v262);
                          v264 = (PVOID *)WPP_GLOBAL_Control;
                        }
                        if ( CbdhsvcPpid < 0 )
                        {
                          if ( v264 != &WPP_GLOBAL_Control && (*((_BYTE *)v264 + 28) & 1) != 0 )
                          {
                            v254 = 222;
                            v255 = v264[2];
                            goto LABEL_743;
                          }
LABEL_744:
                          if ( v410 )
                            operator delete(v410, v250);
                          goto LABEL_718;
                        }
                        LODWORD(v399) = 0;
                        *(_QWORD *)((char *)&v399 + 4) = 0;
                        if ( !*(_BYTE *)(*(_QWORD *)v372 + 109LL) )
                        {
                          v265 = *(_QWORD *)v261;
                          v266 = *((_DWORD *)v261 + 2);
                          *(_OWORD *)v385 = 0;
                          std::atomic_load<RealtimeProtection::DlpProcessCache::DlpProcessStateCache>(v385);
                          v267 = (RTL_SRWLOCK *)v385[0];
                          *(_QWORD *)&v399 = v265;
                          DWORD2(v399) = v266;
                          if ( v385[0] )
                          {
                            *(_QWORD *)v390 = v265;
                            v391 = v266;
                            v268 = (RTL_SRWLOCK *)((char *)v385[0] + 464);
                            AcquireSRWLockShared((PSRWLOCK)v385[0] + 58);
                            v420 = 0;
                            std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(
                              &v267[25],
                              &v420,
                              v390);
                            if ( v420 == v267[26].Ptr )
                            {
                              ReleaseSRWLockShared(v267 + 58);
                              v269 = 0;
                            }
                            else
                            {
                              *(_QWORD *)&v399 = *((_QWORD *)v420 + 56);
                              DWORD2(v399) = *((_DWORD *)v420 + 114);
                              v269 = *((_DWORD *)v420 + 110);
                              ReleaseSRWLockShared(v268);
                            }
                            if ( v385[1] )
                              std::_Ref_count_base::_Decref(v385[1]);
                            if ( v269 == 1 )
                              goto LABEL_780;
                          }
                          else
                          {
                            std::shared_ptr<EndpointDlp::Policy::UserConfig::DlpUserConfiguration const>::~shared_ptr<EndpointDlp::Policy::UserConfig::DlpUserConfiguration const>(v385);
                          }
                          v270 = *(_QWORD *)v372;
                          goto LABEL_790;
                        }
LABEL_780:
                        v270 = *(_QWORD *)v372;
                        CbdhsvcPpid = RealtimeProtection::DlpInjection::InjectEnforcementDllAsync(
                                        (RealtimeProtection::DlpInjection *)*(unsigned int *)(*(_QWORD *)v372 + 56LL),
                                        (const struct PPID *)&v399,
                                        (const struct PPID *)v208,
                                        v263);
                        if ( CbdhsvcPpid < 0 )
                        {
                          v271 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                          {
                            goto LABEL_785;
                          }
                          v272 = 223;
LABEL_784:
                          WPP_SF_d(
                            v271[2],
                            v272,
                            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                            (unsigned int)CbdhsvcPpid);
LABEL_785:
                          if ( v410 )
                            operator delete(v410, v186);
                          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v442);
                          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v436);
                          std::_Non_trivial_move<std::_Optional_construct_base<std::string>,std::string>::~_Non_trivial_move<std::_Optional_construct_base<std::string>,std::string>(v440);
                          RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v455);
                          EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)&v445);
                          std::_Ptr_base<EndpointDlp::endpointDlpImpl>::_Decref(v384);
                          std::shared_ptr<EndpointDlp::Policy::UserConfig::DlpUserConfiguration const>::~shared_ptr<EndpointDlp::Policy::UserConfig::DlpUserConfiguration const>(&v401);
                          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v439);
                          RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v412);
                          std::optional<std::wstring>::~optional<std::wstring>(&v433);
                          v141 = (RTL_SRWLOCK *)(v270 + 16);
                          goto LABEL_383;
                        }
LABEL_790:
                        v273 = -1;
                        while ( 1 )
                        {
                          if ( v208[v273 + 1] != aBrowserBrokerE[v273 + 1] )
                          {
LABEL_794:
                            v186 = (const struct std::nothrow_t *)L"RuntimeBroker.exe";
                            v274 = 0;
                            while ( v208[v274] == aRuntimebrokerE[v274] && v208[v274 + 1] == aRuntimebrokerE[v274 + 1] )
                            {
                              v274 += 2;
                              if ( v274 == 18 )
                                goto LABEL_798;
                            }
                            goto LABEL_809;
                          }
                          v273 += 2;
                          if ( v273 == 19 )
                            break;
                          if ( v208[v273] != aBrowserBrokerE[v273] )
                            goto LABEL_794;
                        }
LABEL_798:
                        v422 = 0;
                        CbdhsvcPpid = RealtimeProtection::DlpProcessCache::GetCbdhsvcPpid((unsigned int)v374[0], &v420);
                        if ( CbdhsvcPpid >= 0 )
                        {
                          if ( !v422 || !v421 )
                          {
                            RealtimeProtection::MpLogMessageImpl(
                              (RealtimeProtection *)L"Detected %ls opening sensitive file. Failed to find session %lu cbdh"
                                                     "svc pid for sensitive file, clipboard enforcement might not work: %ls",
                              v208,
                              (unsigned int)v374[0],
                              v243,
                              Reserved);
                            goto LABEL_809;
                          }
                          v275 = (const struct PPID *)std::optional<PPID>::value(&v420);
                          CbdhsvcPpid = RealtimeProtection::DlpInjection::InjectEnforcementDllAsync(
                                          (RealtimeProtection::DlpInjection *)*(unsigned int *)(v270 + 56),
                                          v275,
                                          (const struct PPID *)L"cbdhsvc",
                                          v276);
                          LODWORD(Reserved) = CbdhsvcPpid;
                          RealtimeProtection::MpLogMessageImpl(
                            (RealtimeProtection *)L"Detected %ls opening sensitive. Associating session %lu cbdhsvc pid %l"
                                                   "u with sensitive file (hr=%#lx): %ls",
                            v208,
                            (unsigned int)v374[0],
                            v421,
                            Reserved,
                            v243);
                          if ( CbdhsvcPpid >= 0 )
                            goto LABEL_809;
                          v271 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                          {
                            v272 = 225;
                            goto LABEL_784;
                          }
                        }
                        else
                        {
                          v271 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                          {
                            v272 = 224;
                            goto LABEL_784;
                          }
                        }
                        goto LABEL_785;
                      }
                      goto LABEL_809;
                    }
                    if ( v397 || v405 != 3 )
                    {
                      if ( !v368 )
                      {
                        CbdhsvcPpid = RealtimeProtection::DlpProcessCache::AddFile(
                                        (_DWORD)v244,
                                        v374[0],
                                        a8,
                                        (_DWORD)v208,
                                        v402 != 0,
                                        (__int64)v243,
                                        (__int64)v420,
                                        v387,
                                        a17,
                                        v407,
                                        (__int64)v482,
                                        (__int64)v412,
                                        (__int64)v480,
                                        v405 == 5,
                                        (__int64)&v445,
                                        v370);
                        if ( CbdhsvcPpid < 0 )
                        {
                          v253 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                          {
                            goto LABEL_744;
                          }
                          v254 = 218;
                          goto LABEL_742;
                        }
                        goto LABEL_729;
                      }
                    }
                    else if ( !v368 )
                    {
                      v248 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                      {
                        v249 = 217;
LABEL_728:
                        WPP_SF_SS(
                          v248[2],
                          v249,
                          (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                          (_DWORD)v208,
                          (__int64)v243);
                        goto LABEL_729;
                      }
                      goto LABEL_729;
                    }
                    v248 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      v249 = 216;
                      goto LABEL_728;
                    }
LABEL_729:
                    if ( (_DWORD)v375 != 2 )
                      goto LABEL_751;
                    CbdhsvcPpid = RealtimeProtection::DlpProcessCache::AddFileSection(v244, v243, (const wchar_t *)v184);
                    if ( CbdhsvcPpid >= 0 )
                    {
                      CbdhsvcPpid = RealtimeProtection::DlpProcessCache::DereferenceFile(
                                      v244,
                                      (const struct PPID *)v243,
                                      v251,
                                      v252);
                      if ( CbdhsvcPpid >= 0 )
                        goto LABEL_751;
                      v253 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                        goto LABEL_744;
                      v254 = 220;
                    }
                    else
                    {
                      v253 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                        goto LABEL_744;
                      v254 = 219;
                    }
LABEL_742:
                    v255 = (PVOID)v253[2];
LABEL_743:
                    WPP_SF_d(v255, v254, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, (unsigned int)CbdhsvcPpid);
                    goto LABEL_744;
                  }
                  v214 = v412;
                  if ( v414 > 7 )
                    v214 = (__int64 *)v412[0];
                  v215 = Src;
                  if ( v417 > 7 )
                    v215 = (__int64 *)Src[0];
                  v216 = L"true";
                  if ( (_DWORD)SourceSize )
                    v216 = L"false";
                  v217 = *((_DWORD *)v376 + 2);
                  if ( v378 )
                    v218 = *(unsigned int *)v378;
                  else
                    v218 = 0;
                  RealtimeProtection::DlpUtils::MpDlpResultAccessReasonToStr(v218, &WPP_GLOBAL_Control, 1, v212);
                  RealtimeProtection::DlpUtils::DlpActionTypeToStr(v369, v219, v220);
                  v223 = RealtimeProtection::DlpUtils::MpDlpResultAccessDecisionToStr((unsigned int)v221, v222, v221);
                  v225 = RealtimeProtection::DlpUtils::DlpFileAccessCheckTypeToStr((unsigned int)v375, v224, v223);
                  v356 = (__int64)v216;
                  v208 = (WCHAR *)lpString1;
                  WPP_SF_SSSSDSSSSSD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    212,
                    v226,
                    v225,
                    v226,
                    v227,
                    v228,
                    v217,
                    (__int64)lpString1,
                    *(__int64 *)&v374[1],
                    v356,
                    (__int64)v215,
                    (__int64)v214,
                    v213);
                }
              }
              v185 = v369;
            }
LABEL_659:
            v184 = 1;
            goto LABEL_660;
          }
LABEL_685:
          v208 = (WCHAR *)lpString1;
          goto LABEL_686;
        }
        v398 = 1;
        if ( v378 )
          *(_DWORD *)v378 = 5;
        v397 = 1;
        v185 = v369;
        v181 = v365;
        v184 = (unsigned int)v375;
      }
      v186 = (const struct std::nothrow_t *)v366;
      goto LABEL_621;
    }
    v371[0] = 0;
    if ( v368 && !v407 )
    {
      v407 = 10;
      v154 = 0;
      v155 = (_DWORD *)v482 + 1;
      do
      {
        *(v155 - 1) = v154;
        *v155 = 0;
        ++v154;
        v155 += 2;
      }
      while ( v154 < 0xA );
    }
    LODWORD(v355) = v407;
    LODWORD(v353) = v153;
    *(_DWORD *)v352 = v143;
    RealtimeProtection::CRtpDlpEngine::DispatchJITEvaluationCompleteEvent(
      *(_QWORD *)v372,
      v153,
      v152,
      (unsigned int)v374[0],
      v412,
      *(_QWORD *)v352,
      v353,
      Source,
      v480,
      v355,
      v482,
      v371);
    v156 = (_DWORD)v375 == 6;
    Lock_shared_ptr_spin_lock(v158, v157, v159);
    v160 = qword_180314488;
    if ( qword_180314488 )
    {
      _InterlockedIncrement((volatile signed __int32 *)qword_180314488 + 2);
      v160 = qword_180314488;
    }
    v161 = qword_180314480;
    Unlock_shared_ptr_spin_lock();
    if ( v161 )
    {
      RealtimeProtection::DlpProcessCache::DlpProcessStateCache::UpdateFileEaCache(
        (_DWORD)v161,
        v374[1],
        v387,
        v156,
        SourceSize,
        (__int64)Source);
      if ( !v160 )
        goto LABEL_469;
    }
    else if ( !v160 )
    {
LABEL_469:
      v426[0] = 0;
      v152 = *(_QWORD *)&v374[1];
      FileIdFromQuarantineFilePath = RealtimeProtection::DlpProcessCache::GetFileIdFromQuarantineFilePath(
                                       *(_QWORD *)&v374[1],
                                       &v423);
      if ( FileIdFromQuarantineFilePath >= 0 )
      {
        v465 = 0;
        v466 = 0;
        v467 = 7;
        LOWORD(v465) = 0;
        v468 = 0;
        v469 = 0;
        v470 = 7;
        LOWORD(v468) = 0;
        v471 = 0;
        v472 = 0;
        v473 = 7;
        LOWORD(v471) = 0;
        v474 = 0;
        v475 = 0;
        v476 = 7;
        LOWORD(v474) = 0;
        *(_OWORD *)v477 = 0;
        v478 = 0;
        std::wstring::operator=(&v465, Src);
        std::wstring::operator=(&v468, v412);
        if ( (_DWORD)SourceSize )
        {
          v169 = Source;
          if ( Source )
          {
            v170 = std::make_shared<std::vector<unsigned char>,unsigned long &>(v380, &SourceSize);
            std::shared_ptr<RealtimeProtection::CSenseCloudCncProxy>::operator=(v477, v170);
            std::shared_ptr<EndpointDlp::Policy::UserConfig::DlpUserConfiguration const>::~shared_ptr<EndpointDlp::Policy::UserConfig::DlpUserConfiguration const>(v380);
            memcpy_s(*(void *const *)v477[0], (unsigned int)SourceSize, v169, (unsigned int)SourceSize);
          }
        }
        v171 = RealtimeProtection::DlpProcessCache::UpdateQuarantineItemPolicyInfo(
                 (unsigned int)&v423,
                 (_DWORD)v376,
                 0,
                 v152,
                 (__int64)&v465);
        if ( v171 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_DSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)lpString1, v152, v171);
        if ( v477[1] )
          std::_Ref_count_base::_Decref(v477[1]);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v474);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v471);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v468);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v465);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)lpString1, v152, FileIdFromQuarantineFilePath);
      }
      std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(&v423);
      goto LABEL_474;
    }
    std::_Ref_count_base::_Decref(v160);
    goto LABEL_469;
  }
  if ( v407 == 10 )
    goto LABEL_430;
  if ( v116 == &WPP_GLOBAL_Control || (*((_BYTE *)v116 + 28) & 1) == 0 )
    goto LABEL_578;
  v148 = 196;
LABEL_427:
  WPP_SF_d(v116[2], v148, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, 2147549183LL);
LABEL_578:
  EndpointDlp::Client::ExtendedAttributes::~ExtendedAttributes((EndpointDlp::Client::ExtendedAttributes *)&v445);
  if ( v102 )
    std::_Ref_count_base::_Decref(v102);
  if ( v77 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v77);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v439);
  RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v412);
  std::optional<std::wstring>::~optional<std::wstring>(&v433);
  ReleaseSRWLockShared((PSRWLOCK)(*(_QWORD *)v372 + 16LL));
  std::optional<std::wstring>::~optional<std::wstring>(v418);
  RealtimeProtection::DlpAutoEtwPerfOperation::~DlpAutoEtwPerfOperation((RealtimeProtection::DlpAutoEtwPerfOperation *)v379);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18018d9f0  push    rbp
0x18018d9f2  push    rbx
0x18018d9f3  push    rsi
0x18018d9f4  push    rdi
0x18018d9f5  push    r12
0x18018d9f7  push    r13
0x18018d9f9  push    r14
0x18018d9fb  push    r15
0x18018d9fd  lea     rbp, [rsp-0F78h]
0x18018da05  mov     eax, 10C8h
0x18018da0a  call    _alloca_probe
0x18018da0f  sub     rsp, rax
0x18018da12  movaps  [rsp+1100h+var_50], xmm6
0x18018da1a  mov     rax, cs:__security_cookie
0x18018da21  xor     rax, rsp
0x18018da24  mov     [rbp+0FB0h+var_60], rax
0x18018da2b  mov     qword ptr [rbp+0FB0h+var_F70], r9
0x18018da2f  mov     rbx, r8
0x18018da32  mov     qword ptr [rbp+0FB0h+var_1014+4], rbx
0x18018da36  mov     dword ptr [rbp+0FB0h+var_1008], edx
0x18018da39  mov     qword ptr [rbp+0FB0h+var_1020], rcx
0x18018da3d  mov     rax, [rbp+0FB0h+arg_20]
0x18018da44  mov     [rbp+0FB0h+var_E48], rax
0x18018da4b  mov     r14, [rbp+0FB0h+String1]
0x18018da52  mov     [rbp+0FB0h+lpString1], r14
0x18018da56  mov     r15, [rbp+0FB0h+lpFileTime1]
0x18018da5d  mov     [rbp+0FB0h+var_1000], r15
0x18018da61  mov     rax, [rbp+0FB0h+arg_40]
0x18018da68  mov     [rbp+0FB0h+var_F88], rax
0x18018da6c  mov     eax, [rbp+0FB0h+arg_48]
0x18018da72  mov     dword ptr [rbp+0FB0h+var_1014], eax
0x18018da75  mov     [rbp+0FB0h+var_EC0], eax
0x18018da7b  mov     rax, [rbp+0FB0h+arg_58]
0x18018da82  mov     [rbp+0FB0h+Source], rax
0x18018da86  mov     r13, [rbp+0FB0h+arg_68]
0x18018da8d  mov     r12, [rbp+0FB0h+arg_78]
0x18018da94  mov     rax, [rbp+0FB0h+arg_88]
0x18018da9b  mov     [rbp+0FB0h+var_F80], rax
0x18018da9f  mov     rdi, [rbp+0FB0h+arg_90]
0x18018daa6  mov     [rbp+0FB0h+var_FF0], rdi
0x18018daaa  xor     esi, esi
0x18018daac  mov     [rbp+0FB0h+var_1018], esi
0x18018daaf  mov     r9d, edx
0x18018dab2  mov     edx, 4
0x18018dab7  mov     r8d, 0FFFFFFFFh
0x18018dabd  lea     rcx, [rbp+0FB0h+var_FE8]
0x18018dac1  call    ??0DlpAutoEtwPerfOperation@RealtimeProtection@@QEAA@W4DlpOperationType@@W4MpDlpOnOperationActionType@@W4DlpFileAccessCheckType@@@Z; RealtimeProtection::DlpAutoEtwPerfOperation::DlpAutoEtwPerfOperation(DlpOperationType,MpDlpOnOperationActionType,DlpFileAccessCheckType)
0x18018dac6  mov     rax, [rbp+0FB0h+var_F80]
0x18018daca  mov     dword ptr [rax], 1
0x18018dad0  test    rdi, rdi
0x18018dad3  jz      short loc_18018DAD7
0x18018dad5  mov     [rdi], esi
0x18018dad7  cmp     dword ptr [rbp+0FB0h+var_1008], 2
0x18018dadb  jnz     short loc_18018DAFB
0x18018dadd  mov     rdx, rbx; wchar_t *
0x18018dae0  mov     rcx, r15; this
0x18018dae3  call    ?AddFileSection@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@PEB_W@Z; RealtimeProtection::DlpProcessCache::AddFileSection(PPID const &,wchar_t const *)
0x18018dae8  test    eax, eax
0x18018daea  jnz     short loc_18018DAFB
0x18018daec  mov     rax, [rbp+0FB0h+var_F80]
0x18018daf0  mov     dword ptr [rax], 1
0x18018daf6  jmp     loc_18019201C
0x18018dafb  mov     [rbp+0FB0h+var_F14], esi
0x18018db01  mov     dword ptr [rbp+0FB0h+String2], esi
0x18018db07  mov     r8, r15
0x18018db0a  mov     edi, dword ptr [rbp+0FB0h+var_1014]
0x18018db0d  mov     edx, edi
0x18018db0f  lea     rcx, [rbp+0FB0h+var_E70]
0x18018db16  call    ?TryGetClassificationUserSidString@DlpUserSidCache@RealtimeProtection@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@KAEBUPPID@@@Z; RealtimeProtection::DlpUserSidCache::TryGetClassificationUserSidString(ulong,PPID const &)
0x18018db1b  mov     ecx, 0D9h
0x18018db20  call    ?GetValue@FeatureControl@Dlp@@YAIW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetValue(FeatureControlEnum)
0x18018db25  test    eax, eax
0x18018db27  jz      short loc_18018DB40
0x18018db29  cmp     [rbp+0FB0h+var_E50], sil
0x18018db30  jz      short loc_18018DB40
0x18018db32  lea     rdx, [rbp+0FB0h+var_E70]
0x18018db39  mov     ecx, edi
0x18018db3b  call    ?CheckAndQueueUserConfigInitRequest@DlpUserConfigManagement@RealtimeProtection@@YAJKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RealtimeProtection::DlpUserConfigManagement::CheckAndQueueUserConfigInitRequest(ulong,std::wstring const &)
0x18018db40  mov     rdi, qword ptr [rbp+0FB0h+var_1020]
0x18018db44  lea     rcx, [rdi+10h]; SRWLock
0x18018db48  call    cs:__imp_AcquireSRWLockShared
0x18018db4e  cmp     dword ptr [rdi+8], 2
0x18018db52  jz      short loc_18018DBB1
0x18018db54  lea     rax, WPP_GLOBAL_Control
0x18018db5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18018db62  cmp     rcx, rax
0x18018db65  jz      short loc_18018DB88
0x18018db67  test    byte ptr [rcx+1Ch], 1
0x18018db6b  jz      short loc_18018DB88
0x18018db6d  mov     edx, 0B0h
0x18018db72  mov     r9d, 8007139Fh
0x18018db78  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18018db7f  mov     rcx, [rcx+10h]
0x18018db83  call    WPP_SF_d
0x18018db88  lea     rcx, [rdi+10h]; SRWLock
0x18018db8c  call    cs:__imp_ReleaseSRWLockShared
0x18018db92  lea     rcx, [rbp+0FB0h+var_E70]
0x18018db99  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x18018db9e  lea     rcx, [rbp+0FB0h+var_FE8]; this
0x18018dba2  call    ??1DlpAutoEtwPerfOperation@RealtimeProtection@@QEAA@XZ; RealtimeProtection::DlpAutoEtwPerfOperation::~DlpAutoEtwPerfOperation(void)
0x18018dba7  mov     eax, 8007139Fh
0x18018dbac  jmp     loc_180192027
0x18018dbb1  lea     rdx, [rbp+0FB0h+String2]; struct PPID *
0x18018dbb8  mov     rcx, r15; lpFileTime1
0x18018dbbb  call    ?GetAppBlanketEnforcementLevel@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@PEAW4AppBlanketLevel@2@@Z; RealtimeProtection::DlpProcessCache::GetAppBlanketEnforcementLevel(PPID const &,RealtimeProtection::AppBlanketLevel *)
0x18018dbc0  mov     edi, eax
0x18018dbc2  test    eax, eax
0x18018dbc4  jns     short loc_18018DC21
0x18018dbc6  lea     rax, WPP_GLOBAL_Control
0x18018dbcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18018dbd4  cmp     rcx, rax
0x18018dbd7  jz      short loc_18018DBF7
0x18018dbd9  test    byte ptr [rcx+1Ch], 1
0x18018dbdd  jz      short loc_18018DBF7
0x18018dbdf  mov     edx, 0B1h
0x18018dbe4  mov     r9d, edi
0x18018dbe7  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18018dbee  mov     rcx, [rcx+10h]
0x18018dbf2  call    WPP_SF_d
0x18018dbf7  mov     rcx, qword ptr [rbp+0FB0h+var_1020]
0x18018dbfb  add     rcx, 10h; SRWLock
0x18018dbff  call    cs:__imp_ReleaseSRWLockShared
0x18018dc05  lea     rcx, [rbp+0FB0h+var_E70]
0x18018dc0c  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x18018dc11  lea     rcx, [rbp+0FB0h+var_FE8]; this
0x18018dc15  call    ??1DlpAutoEtwPerfOperation@RealtimeProtection@@QEAA@XZ; RealtimeProtection::DlpAutoEtwPerfOperation::~DlpAutoEtwPerfOperation(void)
0x18018dc1a  mov     eax, edi
0x18018dc1c  jmp     loc_180192027
0x18018dc21  lea     r15, WPP_GLOBAL_Control
0x18018dc28  mov     eax, dword ptr [rbp+0FB0h+String2]
0x18018dc2e  mov     [rbp+0FB0h+var_FC0], eax
0x18018dc31  test    eax, eax
0x18018dc33  jnz     loc_18018DDC5
0x18018dc39  mov     [rbp+0FB0h+var_102E], sil
0x18018dc3d  lea     rdx, [rbp+0FB0h+var_102E]; struct PPID *
0x18018dc41  mov     rdi, [rbp+0FB0h+var_1000]
0x18018dc45  mov     rcx, rdi; this
0x18018dc48  call    ?GetEngineConfigForAppBlanketEnforcement@DlpEngineUtils@RealtimeProtection@@YAJAEBUPPID@@PEA_N@Z; RealtimeProtection::DlpEngineUtils::GetEngineConfigForAppBlanketEnforcement(PPID const &,bool *)
0x18018dc4d  test    eax, eax
0x18018dc4f  jns     short loc_18018DC85
0x18018dc51  mov     rcx, cs:WPP_GLOBAL_Control
0x18018dc58  cmp     rcx, r15
0x18018dc5b  jz      short loc_18018DC8B
0x18018dc5d  test    byte ptr [rcx+1Ch], 1
0x18018dc61  jz      short loc_18018DC8B
0x18018dc63  mov     edx, 0B2h
0x18018dc68  mov     r9d, eax
0x18018dc6b  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18018dc72  mov     rcx, [rcx+10h]
0x18018dc76  call    WPP_SF_d
0x18018dc7b  mov     eax, 1
0x18018dc80  mov     [rbp+0FB0h+var_FC0], eax
0x18018dc83  jmp     short loc_18018DC9C
0x18018dc85  cmp     [rbp+0FB0h+var_102E], sil
0x18018dc89  jz      short loc_18018DC95
0x18018dc8b  mov     eax, 1
0x18018dc90  mov     [rbp+0FB0h+var_FC0], eax
0x18018dc93  jmp     short loc_18018DC9C
0x18018dc95  mov     [rbp+0FB0h+var_FC0], 2
0x18018dc9c  mov     dword ptr [rbp+0FB0h+String2], esi
0x18018dca2  call    cs:__imp_MpClientUtilExportFunctions
0x18018dca8  lea     rcx, [rbp+0FB0h+String2]
0x18018dcaf  mov     rax, [rax+98h]
0x18018dcb6  call    cs:__guard_dispatch_icall_fptr
0x18018dcbc  nop
0x18018dcbd  test    eax, eax
0x18018dcbf  js      loc_18018DD90
0x18018dcc5  cmp     dword ptr [rbp+0FB0h+String2], 0
0x18018dccc  jz      loc_18018DD90
0x18018dcd2  mov     [rbp+0FB0h+String2], rsi
0x18018dcd9  lea     rdx, [rbp+0FB0h+String2]; wchar_t *
0x18018dce0  lea     rcx, aMpdlpTestproce; "MpDlp_TestProcessNoBlanketPolicy"
0x18018dce7  call    ?DlpGetMiscStringValue@DlpUtils@RealtimeProtection@@YAJPEB_WPEAPEA_W@Z; RealtimeProtection::DlpUtils::DlpGetMiscStringValue(wchar_t const *,wchar_t * *)
0x18018dcec  test    eax, eax
0x18018dcee  jns     short loc_18018DD0B
0x18018dcf0  mov     rcx, [rbp+0FB0h+String2]
0x18018dcf7  test    rcx, rcx
0x18018dcfa  jz      short loc_18018DD17
0x18018dcfc  call    cs:__imp_MpFreeMemory
0x18018dd02  mov     [rbp+0FB0h+String2], rsi
0x18018dd09  jmp     short loc_18018DD17
0x18018dd0b  mov     rdx, [rbp+0FB0h+String2]
0x18018dd12  test    rdx, rdx
0x18018dd15  jnz     short loc_18018DD41
0x18018dd17  lea     r8, aFiletestExe; "filetest.exe"
0x18018dd1e  lea     rdx, aS_2; "%s"
0x18018dd25  lea     rcx, [rbp+0FB0h+String2]
0x18018dd2c  call    MpAllocSprintfW
0x18018dd31  test    eax, eax
0x18018dd33  js      short loc_18018DD7E
0x18018dd35  mov     rdx, [rbp+0FB0h+String2]; String2
0x18018dd3c  test    rdx, rdx
0x18018dd3f  jz      short loc_18018DD90
0x18018dd41  mov     rcx, r14; String1
0x18018dd44  call    _wcsicmp
0x18018dd49  test    eax, eax
0x18018dd4b  jnz     short loc_18018DD7E
0x18018dd4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18018dd54  cmp     rcx, r15
0x18018dd57  jz      short loc_18018DD77
0x18018dd59  test    byte ptr [rcx+1Ch], 4
0x18018dd5d  jz      short loc_18018DD77
0x18018dd5f  mov     edx, 0B3h
0x18018dd64  mov     r9, r14
0x18018dd67  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18018dd6e  mov     rcx, [rcx+10h]
0x18018dd72  call    WPP_SF_S
0x18018dd77  mov     [rbp+0FB0h+var_FC0], 2
0x18018dd7e  mov     rcx, [rbp+0FB0h+String2]
0x18018dd85  test    rcx, rcx
0x18018dd88  jz      short loc_18018DD90
0x18018dd8a  call    cs:__imp_MpFreeMemory
0x18018dd90  mov     edx, [rbp+0FB0h+var_FC0]
0x18018dd93  mov     rcx, rdi
0x18018dd96  call    ?SetAppBlanketEnforcementLevel@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@W4AppBlanketLevel@2@@Z; RealtimeProtection::DlpProcessCache::SetAppBlanketEnforcementLevel(PPID const &,RealtimeProtection::AppBlanketLevel)
0x18018dd9b  mov     edi, eax
0x18018dd9d  test    eax, eax
0x18018dd9f  jns     short loc_18018DDC5
0x18018dda1  mov     rcx, cs:WPP_GLOBAL_Control
0x18018dda8  cmp     rcx, r15
0x18018ddab  jz      loc_18018DBF7
0x18018ddb1  test    byte ptr [rcx+1Ch], 1
0x18018ddb5  jz      loc_18018DBF7
0x18018ddbb  mov     edx, 0B4h
0x18018ddc0  jmp     loc_18018DBE4
0x18018ddc5  mov     rax, qword ptr [rbp+0FB0h+var_1020]
0x18018ddc9  cmp     byte ptr [rax+5Fh], 0
0x18018ddcd  jz      loc_18018E12B
0x18018ddd3  mov     ecx, 72h ; 'r'
0x18018ddd8  call    ?GetValue@FeatureControl@Dlp@@YAIW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetValue(FeatureControlEnum)
0x18018dddd  test    al, 4
0x18018dddf  jz      loc_18018E12B
0x18018dde5  call    _Lock_shared_ptr_spin_lock
0x18018ddea  mov     rdi, cs:qword_180314488
0x18018ddf1  test    rdi, rdi
0x18018ddf4  jz      short loc_18018DE01
0x18018ddf6  lock inc dword ptr [rdi+8]
0x18018ddfa  mov     rdi, cs:qword_180314488
0x18018de01  mov     rbx, cs:qword_180314480
0x18018de08  call    _Unlock_shared_ptr_spin_lock
0x18018de0d  test    rbx, rbx
0x18018de10  jz      loc_18018E196
0x18018de16  lea     rcx, [rbx+1D0h]; SRWLock
0x18018de1d  call    cs:__imp_AcquireSRWLockShared
0x18018de23  mov     [rbp+0FB0h+var_FA0], 0
0x18018de2b  mov     r8, [rbp+0FB0h+var_1000]
0x18018de2f  lea     rdx, [rbp+0FB0h+var_FA0]
0x18018de33  lea     rcx, [rbx+0C8h]
0x18018de3a  call    ?find@?$_Hash@V?$_Umap_traits@UPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@UPPID@@UPPIDHasher@DlpUtils@RealtimeProtection@@UPPIDComparer@34@@std@@V?$allocator@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@7@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@std@@@std@@@2@AEBUPPID@@@Z; std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(PPID const &)
0x18018de3f  mov     rax, [rbp+0FB0h+var_FA0]
0x18018de43  cmp     rax, [rbx+0D0h]
0x18018de4a  jz      short loc_18018DE52
0x18018de4c  mov     esi, [rax+174h]
0x18018de52  lea     rcx, [rbx+1D0h]; SRWLock
0x18018de59  call    cs:__imp_ReleaseSRWLockShared
0x18018de5f  test    rdi, rdi
0x18018de62  jz      short loc_18018DE6C
0x18018de64  mov     rcx, rdi; this
0x18018de67  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018de6c  xor     ebx, ebx
0x18018de6e  mov     edi, ebx
0x18018de70  mov     r14, [rbp+0FB0h+lpString1]
0x18018de74  test    esi, esi
0x18018de76  jnz     loc_18018E125
0x18018de7c  test    r14, r14
0x18018de7f  jz      loc_18018E125
0x18018de85  mov     rdx, r14
0x18018de88  lea     rcx, [rbp+0FB0h+var_E30]
0x18018de8f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18018de94  movzx   r14d, sil
0x18018de98  cmp     qword ptr [rbp+0FB0h+var_E20], rbx
0x18018de9f  jnz     short loc_18018DEC2
0x18018dea1  mov     rcx, cs:WPP_GLOBAL_Control
0x18018dea8  cmp     rcx, r15
0x18018deab  jz      loc_18018E0BC
0x18018deb1  test    byte ptr [rcx+1Ch], 1
0x18018deb5  jz      loc_18018E0BC
0x18018debb  mov     edx, 4Ah ; 'J'
0x18018dec0  jmp     short loc_18018DEF7
0x18018dec2  mov     [rbp+0FB0h+var_FA0], rbx
0x18018dec6  lea     rcx, [rbp+0FB0h+var_FA0]; this
0x18018deca  call    ?GetEngine@DlpPlugin@RealtimeProtection@@YAXPEAPEAVDlpCEngine@2@@Z; RealtimeProtection::DlpPlugin::GetEngine(RealtimeProtection::DlpCEngine * *)
0x18018decf  mov     rbx, [rbp+0FB0h+var_FA0]
0x18018ded3  test    rbx, rbx
0x18018ded6  jnz     short loc_18018DF0C
0x18018ded8  mov     rcx, cs:WPP_GLOBAL_Control
0x18018dedf  cmp     rcx, r15
0x18018dee2  jz      loc_18018E0BC
0x18018dee8  test    byte ptr [rcx+1Ch], 1
0x18018deec  jz      loc_18018E0BC
0x18018def2  mov     edx, 4Bh ; 'K'
0x18018def7  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18018defe  mov     rcx, [rcx+10h]
0x18018df02  call    WPP_SF_
0x18018df07  jmp     loc_18018E0BC
0x18018df0c  lea     rax, [rbp+0FB0h+var_E30]
0x18018df13  cmp     qword ptr [rbp+0FB0h+var_E20+8], 7
0x18018df1b  cmova   rax, qword ptr [rbp+0FB0h+var_E30]
0x18018df23  xor     sil, sil
0x18018df26  test    rax, rax
  ... truncated ...
```
