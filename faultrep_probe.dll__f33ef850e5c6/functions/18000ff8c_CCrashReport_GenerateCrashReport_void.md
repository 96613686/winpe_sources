# CCrashReport::GenerateCrashReport(void)

- ea: `0x18000ff8c`
- end: `0x180011a2f`
- name: `?GenerateCrashReport@CCrashReport@@AEAAJXZ`
- size: `6819`
- prototype: `__int64 __fastcall(CCrashReport *__hidden this)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001541c`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180003474`
- `0x180004688`
- `0x1800046fc`
- `0x18000760c`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x180009f40`
- `0x18000fdec`
- `0x18000ff8c`
- `0x180011a38`
- `0x180011e34`
- `0x180012ef0`
- `0x180013568`
- `0x18001385c`
- `0x1800138bc`
- `0x180015830`
- `0x180015c00`
- `0x1800160a4`
- `0x180016414`
- `0x180016764`
- `0x180019258`
- `0x1800199f8`
- `0x18001a3a4`
- `0x18001bd2c`
- `0x18001ce20`
- `0x18001e888`
- `0x18001eadc`
- `0x18001ed50`
- `0x1800273d8`
- `0x180027e14`
- `0x18002847c`
- `0x180028550`
- `0x180028614`
- `0x1800287ec`
- `0x180038c0c`
- `0x180039e4c`
- `0x18003adbc`
- `0x18003e5a8`
- `0x180049280`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800113dd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800113dd`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180010621`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001190b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180010621`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001190b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180010648`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180011940`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180010648`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180011940`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800111ed`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800111ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119a0`
- `ntdll!NtQueryInformationProcess` at `0x18001023b`
- `ntdll!NtQueryInformationProcess` at `0x18001023b`
- `ntdll!NtSetSystemInformation` at `0x180010290`
- `ntdll!NtSetSystemInformation` at `0x180010290`
- `ntdll!RtlInitUnicodeString` at `0x180010279`
- `ntdll!RtlInitUnicodeString` at `0x180010279`
- `ntdll!NtSetInformationProcess` at `0x18001047e`
- `ntdll!NtSetInformationProcess` at `0x18001047e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010613`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001194f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010613`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001194f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800106ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010d23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800106ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010d23`
- `wer!WerReportCloseHandle` at `0x1800106da`
- `wer!WerReportCloseHandle` at `0x180010fc7`
- `wer!WerReportCloseHandle` at `0x1800106da`
- `wer!WerReportCloseHandle` at `0x180010fc7`
- `wer!WerpGetStoreLocation` at `0x180011899`
- `wer!WerpGetStoreLocation` at `0x180011899`
- `wer!WerReportSubmit` at `0x180011788`
- `wer!WerReportSubmit` at `0x180011788`
- `wer!WerpAddMemoryBlock` at `0x180011740`
- `wer!WerpAddMemoryBlock` at `0x180011740`
- `wer!WerpReportSetMaxProcessHoldMilliseconds` at `0x1800116d5`
- `wer!WerpReportSetMaxProcessHoldMilliseconds` at `0x1800116d5`
- `wer!WerpAddIfRegisteredForAppLocalDump` at `0x18001165a`
- `wer!WerpAddIfRegisteredForAppLocalDump` at `0x18001165a`
- `wer!WerpAddRegisteredDumpsToReport` at `0x18001160e`
- `wer!WerpAddRegisteredDumpsToReport` at `0x18001160e`
- `wer!WerpAddRegisteredDataToReport` at `0x1800115d0`
- `wer!WerpAddRegisteredDataToReport` at `0x1800115d0`
- `wer!WerpSetCallBack` at `0x1800115b6`
- `wer!WerpSetCallBack` at `0x1800115b6`
- `wer!WerpSetQuickDumpType` at `0x180011571`
- `wer!WerpSetQuickDumpType` at `0x180011571`
- `wer!WerReportAddDump` at `0x180011520`
- `wer!WerReportAddDump` at `0x180011520`
- `wer!WerpSetReportIsFatal` at `0x18001121d`
- `wer!WerpSetReportIsFatal` at `0x18001121d`
- `wer!WerpSetIntegratorReportId` at `0x18001109c`
- `wer!WerpSetIntegratorReportId` at `0x18001109c`
- `wer!WerpGetReportId` at `0x180011010`
- `wer!WerpGetReportId` at `0x180011010`
- `wer!WerReportCreate` at `0x180010fe4`
- `wer!WerReportCreate` at `0x180010fe4`
- `wer!WerpSetTelemetryServiceParams` at `0x180011186`
- `wer!WerpSetTelemetryServiceParams` at `0x180011186`
- `wer!WerpSetProcessTimelines` at `0x18001113e`
- `wer!WerpSetProcessTimelines` at `0x18001113e`
- `wer!WerpSetTelemetryAppParams` at `0x180011101`
- `wer!WerpSetTelemetryAppParams` at `0x180011101`
- `wer!WerpAddTerminationReason` at `0x180010639`
- `wer!WerpAddTerminationReason` at `0x180011923`
- `wer!WerpAddTerminationReason` at `0x180010639`
- `wer!WerpAddTerminationReason` at `0x180011923`
- `wer!WerpGetExtendedDiagData` at `0x180011715`
- `wer!WerpGetExtendedDiagData` at `0x180011715`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x18001129b`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x18001129b`
- `RPCRT4!UuidCreate` at `0x18001014f`
- `RPCRT4!UuidCreate` at `0x18001014f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CCrashReport::GenerateCrashReport(CCrashReport *this)
{
  RPC_STATUS v2; // eax
  NTSTATUS InformationProcess; // eax
  NTSTATUS v4; // eax
  int ProcessAppSessionGuid; // eax
  int ProcessTelemetryTargetAppParams; // eax
  int ProcessTimelines; // eax
  int v8; // edx
  int v9; // ecx
  int v10; // r13d
  __int64 v11; // rsi
  unsigned int v12; // r15d
  __int64 v13; // r9
  int v14; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  char *v17; // rsi
  DWORD v18; // eax
  _WORD *v20; // rbx
  __int64 v21; // r8
  void *v22; // rax
  BOOL v23; // r14d
  __int64 v24; // r9
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // eax
  _QWORD *v29; // r10
  unsigned int i; // ebx
  void **v31; // rbx
  const wchar_t *v32; // rdx
  int v33; // r8d
  __int64 v34; // r12
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rsi
  __int16 *v38; // rbx
  _OWORD *v39; // rax
  _OWORD *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rdx
  _WORD *v44; // r8
  __int16 v45; // cx
  _WORD *v46; // rcx
  int v47; // edx
  int updated; // eax
  CPluginList *v49; // rcx
  void *v50; // rcx
  _QWORD *v51; // r10
  unsigned int v52; // ebx
  unsigned int j; // eax
  int matched; // eax
  int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // rax
  struct WER_PLUGIN_SIG_ELEMENT *v58; // rsi
  unsigned int v59; // r14d
  HREPORT v60; // rcx
  __int64 v61; // rbx
  int ReportId; // eax
  wchar_t *v63; // rcx
  wchar_t *v64; // rax
  wchar_t v65; // r8
  wchar_t *v66; // rcx
  _QWORD *v67; // rcx
  __int64 v68; // rdx
  int IsFatal; // eax
  const wchar_t *v70; // rdx
  const wchar_t *v71; // r8
  DWORD v72; // r9d
  int Settings; // eax
  __int64 v74; // rax
  WER_DUMP_TYPE v75; // r14d
  _QWORD *v76; // rcx
  __int64 v77; // rdx
  int v78; // esi
  int v79; // eax
  _QWORD *v80; // rcx
  DWORD dwFlags; // ebx
  int v82; // eax
  int v83; // eax
  int v84; // eax
  unsigned int MaxProcessHoldMilliseconds; // eax
  int v86; // eax
  int v87; // eax
  const wchar_t *v88; // rdx
  DWORD ProcessId; // eax
  int v90; // eax
  signed int LastError; // eax
  char *hObject; // [rsp+90h] [rbp-80h]
  HREPORT hReportHandle; // [rsp+98h] [rbp-78h] BYREF
  int v94; // [rsp+A0h] [rbp-70h]
  _WER_SUBMIT_RESULT pSubmitResult; // [rsp+A4h] [rbp-6Ch] BYREF
  __int64 v96; // [rsp+A8h] [rbp-68h] BYREF
  int v97; // [rsp+B0h] [rbp-60h] BYREF
  int v98; // [rsp+B4h] [rbp-5Ch] BYREF
  int v99; // [rsp+B8h] [rbp-58h] BYREF
  wchar_t *v100; // [rsp+C0h] [rbp-50h] BYREF
  wchar_t *v101; // [rsp+C8h] [rbp-48h]
  _WORD v102[8]; // [rsp+D0h] [rbp-40h] BYREF
  __int64 v103; // [rsp+E0h] [rbp-30h] BYREF
  __int64 v104; // [rsp+E8h] [rbp-28h] BYREF
  void *v105; // [rsp+F0h] [rbp-20h] BYREF
  _WORD *v106; // [rsp+F8h] [rbp-18h]
  _WORD v107[8]; // [rsp+100h] [rbp-10h] BYREF
  __int128 v108; // [rsp+110h] [rbp+0h] BYREF
  _WER_EXCEPTION_INFORMATION pExceptionParam; // [rsp+120h] [rbp+10h] BYREF
  __int64 v110; // [rsp+130h] [rbp+20h] BYREF
  _QWORD v111[3]; // [rsp+138h] [rbp+28h] BYREF
  void *v112; // [rsp+150h] [rbp+40h]
  __int64 v113; // [rsp+168h] [rbp+58h]
  __int64 v114; // [rsp+180h] [rbp+70h]
  int v115; // [rsp+188h] [rbp+78h]
  __int64 v116; // [rsp+198h] [rbp+88h]
  int v117; // [rsp+1A0h] [rbp+90h]
  __int64 v118; // [rsp+1B0h] [rbp+A0h]
  int v119; // [rsp+1B8h] [rbp+A8h]
  __int64 v120; // [rsp+1C8h] [rbp+B8h]
  int v121; // [rsp+1D0h] [rbp+C0h]
  __int64 v122; // [rsp+1E0h] [rbp+D0h]
  int v123; // [rsp+1E8h] [rbp+D8h]
  __int64 v124; // [rsp+1F8h] [rbp+E8h]
  int v125; // [rsp+200h] [rbp+F0h]
  _BYTE v126[592]; // [rsp+210h] [rbp+100h] BYREF
  _QWORD v127[31]; // [rsp+460h] [rbp+350h] BYREF
  int v128; // [rsp+558h] [rbp+448h]
  int v129; // [rsp+55Ch] [rbp+44Ch]
  __int64 v130; // [rsp+560h] [rbp+450h]
  __int64 v131; // [rsp+568h] [rbp+458h]
  __int64 v132; // [rsp+570h] [rbp+460h]
  int v133; // [rsp+578h] [rbp+468h]
  int v134; // [rsp+57Ch] [rbp+46Ch]
  char *v135; // [rsp+580h] [rbp+470h]
  char *v136; // [rsp+588h] [rbp+478h]
  __int64 v137; // [rsp+590h] [rbp+480h]
  __int64 v138; // [rsp+598h] [rbp+488h]
  wchar_t *v139; // [rsp+5A0h] [rbp+490h]
  int v140; // [rsp+5A8h] [rbp+498h]
  int v141; // [rsp+5ACh] [rbp+49Ch]
  __int64 v142; // [rsp+5B0h] [rbp+4A0h]
  __int64 v143; // [rsp+5C0h] [rbp+4B0h] BYREF
  _QWORD v144[30]; // [rsp+5C8h] [rbp+4B8h] BYREF
  unsigned int v145; // [rsp+6B8h] [rbp+5A8h]
  _QWORD v146[31]; // [rsp+6C0h] [rbp+5B0h] BYREF
  int v147; // [rsp+7B8h] [rbp+6A8h]
  struct _WER_DUMP_CUSTOM_OPTIONS pDumpCustomOptions; // [rsp+7C0h] [rbp+6B0h] BYREF
  __int64 v149; // [rsp+9F8h] [rbp+8E8h]
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+A10h] [rbp+900h] BYREF
  UUID Uuid; // [rsp+13E0h] [rbp+12D0h] BYREF
  UUID SystemInformation; // [rsp+13F0h] [rbp+12E0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+1400h] [rbp+12F0h] BYREF
  int v154; // [rsp+1410h] [rbp+1300h]
  int v155; // [rsp+1414h] [rbp+1304h]
  __int64 v156; // [rsp+1418h] [rbp+1308h]
  __int64 v157; // [rsp+1420h] [rbp+1310h]
  char ProcessInformation[8]; // [rsp+1428h] [rbp+1318h] BYREF
  __int64 v159; // [rsp+1430h] [rbp+1320h]
  _BYTE v160[1672]; // [rsp+1440h] [rbp+1330h] BYREF
  __int64 v161; // [rsp+1AC8h] [rbp+19B8h]
  __int64 v162; // [rsp+1B20h] [rbp+1A10h]
  char v163; // [rsp+2758h] [rbp+2648h]
  int v164; // [rsp+275Ch] [rbp+264Ch]
  wchar_t *String; // [rsp+2760h] [rbp+2650h]
  int v166; // [rsp+27B8h] [rbp+26A8h]
  int v167; // [rsp+2828h] [rbp+2718h]
  __int64 v168; // [rsp+282Ch] [rbp+271Ch]
  __int16 v169; // [rsp+2834h] [rbp+2724h]
  char v170; // [rsp+2836h] [rbp+2726h]
  __int64 v171; // [rsp+2838h] [rbp+2728h]
  int v172; // [rsp+2840h] [rbp+2730h]
  _QWORD v173[36]; // [rsp+2850h] [rbp+2740h] BYREF
  wchar_t v174[264]; // [rsp+2970h] [rbp+2860h] BYREF

  hReportHandle = 0;
  pExceptionParam = 0;
  memset_0(v127, 0, 0x158u);
  memset_0(v146, 0, 0x100u);
  memset_0(&v143, 0, 0x100u);
  v97 = 0;
  pSubmitResult = 0;
  memset_0(&pReportInformation, 0, 0x9C8u);
  memset_0(&pDumpCustomOptions, 0, 0x248u);
  v110 = 0;
  memset_0(v111, 0, 0xD0u);
  `eh vector constructor iterator'(
    v173,
    0x20u,
    9u,
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>);
  v108 = 0;
  v103 = 0;
  v100 = v102;
  v102[0] = 0;
  Uuid = 0;
  v105 = v107;
  v106 = v107;
  v107[0] = 0;
  v104 = 0;
  v98 = 0;
  SystemInformation.Data1 = 0;
  memset_0(&SystemInformation.Data2, 0, 0x44u);
  `eh vector constructor iterator'(
    v160,
    0x68u,
    0x31u,
    (void (*)(void *))CRegSetting::CRegSetting,
    (void (*)(void *))CRegSetting::~CRegSetting);
  v167 = 1;
  v168 = 1;
  v169 = 0;
  v170 = 1;
  v171 = 5;
  v172 = 0;
  v99 = 260;
  v101 = v102;
  v102[0] = 0;
  v2 = UuidCreate(&Uuid);
  if ( !v2 || v2 == 1824 )
    UtilGetStringFromGUID(&Uuid, &v100);
  else
    Uuid = 0;
  if ( (*((_DWORD *)this + 3) || *((_DWORD *)this + 1))
    && (*(_BYTE *)(*((_QWORD *)this + 5) + 236LL) & 4) == 0
    && (int)CCrashReport::EnableShutdownPrivilege() >= 0 )
  {
    SystemInformation = Uuid;
    v154 = *((_DWORD *)this + 86);
    v155 = *((_DWORD *)this + 87);
    v156 = *((_QWORD *)this + 52);
    v159 = *((unsigned int *)this + 185);
    v157 = *((unsigned int *)this + 184);
    InformationProcess = NtQueryInformationProcess(
                           *((HANDLE *)this + 6),
                           ProcessLUIDDeviceMapsEnabled|0x40,
                           ProcessInformation,
                           8u,
                           0);
    if ( InformationProcess < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
        (unsigned int)InformationProcess);
    }
    RtlInitUnicodeString(&DestinationString, *((PCWSTR *)this + 38));
    v4 = NtSetSystemInformation(SystemPagedPoolInformation|0x80, &SystemInformation, 0x48u);
    if ( v4 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
        (unsigned int)v4);
    }
  }
  ProcessAppSessionGuid = TelGetProcessAppSessionGuid(
                            *((HANDLE *)this + 6),
                            (struct _GUID *)((char *)this + 10440),
                            (unsigned __int64 *)this + 1304);
  if ( ProcessAppSessionGuid < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
      (unsigned int)ProcessAppSessionGuid);
  }
  ProcessTelemetryTargetAppParams = UtilGetProcessTelemetryTargetAppParams(*((HANDLE *)this + 6));
  if ( ProcessTelemetryTargetAppParams < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
      (unsigned int)ProcessTelemetryTargetAppParams);
  }
  *((_QWORD *)this + 1307) = *((_QWORD *)this + 1309);
  *((_QWORD *)this + 1308) = *((_QWORD *)this + 1313);
  ProcessTimelines = UtilGetProcessTimelines(*((HANDLE *)this + 6), (CCrashReport *)((char *)this + 10152));
  if ( ProcessTimelines < 0 )
  {
    v9 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
        (unsigned int)ProcessTimelines);
  }
  if ( (Application_ErrorEnableBits & 1) != 0 )
    McTemplateU0zzzzzzzzdizzzzz_EventWriteTransfer(
      v9,
      v8,
      *((_QWORD *)this + 15),
      *((_QWORD *)this + 26),
      *((_QWORD *)this + 30),
      *((_QWORD *)this + 38),
      *((_QWORD *)this + 44),
      *((_QWORD *)this + 48),
      *((_QWORD *)this + 59),
      *((_QWORD *)this + 55),
      *((_DWORD *)this + 49),
      *((_QWORD *)this + 25),
      *((_QWORD *)this + 11),
      *((_QWORD *)this + 34),
      (__int64)v100,
      *((_QWORD *)this + 65),
      *((_QWORD *)this + 69));
  CCrashReport::LogCrashEventToAsimov(this, v100);
  if ( (*(_BYTE *)(*((_QWORD *)this + 5) + 236LL) & 4) == 0 )
  {
    v96 = 1;
    NtSetInformationProcess(*((HANDLE *)this + 6), MaxProcessInfoClass|ProcessUserModeIOPL, &v96, 8u);
  }
  pReportInformation.dwSize = 2504;
  v10 = *((_DWORD *)this + 128);
  v11 = 0;
  if ( v10 )
  {
    v12 = 9;
    v94 = 9;
    do
    {
      UtilLoadString(&v173[4 * v11], (unsigned int)dword_180051A30[v11], g_hFaultrepDLLModule);
      v111[3 * v11 - 1] = v173[4 * v11];
      ++v11;
    }
    while ( v11 != 9 );
    if ( !*((_QWORD *)this + 65) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !**((_WORD **)this + 65) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v20 = (_WORD *)*((_QWORD *)this + 69);
    if ( v20
      && *v20
      && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                            &v105,
                            L"praid:") )
    {
      v21 = -1;
      do
        ++v21;
      while ( v20[v21] );
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(&v105, v20);
    }
    v111[0] = *((_QWORD *)this + 65);
    v22 = v105;
    if ( v105 == v106 )
      v22 = (void *)*((_QWORD *)this + 15);
    v112 = v22;
    v113 = *((_QWORD *)this + 26);
    v114 = *((_QWORD *)this + 30);
    v116 = *((_QWORD *)this + 38);
    v117 |= 1u;
    v118 = *((_QWORD *)this + 44);
    v119 |= 2u;
    v120 = *((_QWORD *)this + 48);
    v121 |= 4u;
    v122 = *((_QWORD *)this + 59);
    v123 |= 0x10u;
    v124 = *((_QWORD *)this + 55);
    v125 |= 8u;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             (char *)this + 784,
                             L"MoAppCrash") )
    {
      v14 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
      goto LABEL_41;
    }
  }
  else
  {
    v12 = 8;
    v94 = 8;
    do
    {
      UtilLoadString(&v173[4 * v11], (unsigned int)dword_180051A60[v11], g_hFaultrepDLLModule);
      v111[3 * v11 - 1] = v173[4 * v11];
      ++v11;
    }
    while ( v11 != 8 );
    v111[0] = *((_QWORD *)this + 15);
    v112 = (void *)*((_QWORD *)this + 26);
    v113 = *((_QWORD *)this + 30);
    v114 = *((_QWORD *)this + 38);
    v115 |= 1u;
    v116 = *((_QWORD *)this + 44);
    v117 |= 2u;
    v118 = *((_QWORD *)this + 48);
    v119 |= 4u;
    v120 = *((_QWORD *)this + 59);
    v121 |= 0x10u;
    v122 = *((_QWORD *)this + 55);
    v123 |= 8u;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             (char *)this + 784,
                             L"APPCRASH") )
    {
      v13 = 2147942414LL;
      v14 = -2147024882;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_41;
      v16 = 44;
      goto LABEL_40;
    }
  }
  v23 = 0;
  v24 = 0;
  v25 = 0;
  do
  {
    v26 = v111[v25 - 1];
    v127[v25 + 1] = v26;
    v27 = v111[v25];
    v127[v25 + 2] = v27;
    v28 = v111[v25 + 1];
    LODWORD(v127[v25 + 3]) = v28;
    v146[v25 + 1] = v26;
    v146[v25 + 2] = v27;
    LODWORD(v146[v25 + 3]) = v28;
    ++v24;
    v25 += 3;
  }
  while ( v24 != 9 );
  v29 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
        *((_QWORD *)this + 98));
      v29 = WPP_GLOBAL_Control;
    }
    for ( i = 0; i < v12; ++i )
    {
      if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 8) != 0 )
      {
        WPP_SF_DSSD(v29[2], 47, v25 * 8, i + 1, v111[3 * i - 1], v111[3 * i], v111[3 * i + 1]);
        v29 = WPP_GLOBAL_Control;
      }
    }
  }
  *((_DWORD *)this + 204) = CCrashReport::GetSubmissionFlags(this);
  v31 = (void **)((char *)this + 776);
  v34 = 2147483646;
  if ( (int)WerPluginsCreate(*((_QWORD *)this + 98), (char *)this + 776) >= 0 )
  {
    v127[0] = *((_QWORD *)this + 98);
    v128 = v94;
    v129 = 1;
    v130 = *((_QWORD *)this + 65);
    v131 = *((_QWORD *)this + 11);
    v132 = *((_QWORD *)this + 34);
    v133 = *((_DWORD *)this + 184);
    v134 = *((_DWORD *)this + 185);
    v135 = (char *)this + 824;
    v136 = (char *)this + 976;
    v137 = *((_QWORD *)this + 6);
    v138 = *((_QWORD *)this + 7);
    v139 = v100;
    v140 = *((_DWORD *)this + 7);
    v141 = *(_DWORD *)(*((_QWORD *)this + 5) + 236LL);
    v142 = *((_QWORD *)this + 91);
    v35 = WerPluginsInitialize(*v31, (struct WER_PLUGIN_INIT_IN *)v127, *((_DWORD *)this + 204), g_hFaultrepDLLModule);
    if ( v35 < 0 )
    {
      v32 = (const wchar_t *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
          (unsigned int)v35);
      v49 = (CPluginList *)*v31;
      *v31 = 0;
      goto LABEL_111;
    }
    if ( (int)WerPluginsGetInitData(*v31, v36, &v103) >= 0 )
    {
      v37 = v103;
      if ( v103 )
      {
        v38 = (__int16 *)(v103 + 8);
        if ( *(_WORD *)(v103 + 8) )
        {
          memset_0(v126, 0, sizeof(v126));
          v39 = (_OWORD *)((char *)this + 4280);
          v40 = v126;
          v41 = 4;
          do
          {
            *v39 = *v40;
            v39[1] = v40[1];
            v39[2] = v40[2];
            v39[3] = v40[3];
            v39[4] = v40[4];
            v39[5] = v40[5];
            v39[6] = v40[6];
            v39[7] = v40[7];
            v39 += 8;
            v40 += 8;
            --v41;
          }
          while ( v41 );
          *v39 = *v40;
          v39[1] = v40[1];
          v39[2] = v40[2];
          v39[3] = v40[3];
          v39[4] = v40[4];
          v42 = 2147483646;
          v43 = 293;
          v44 = (_WORD *)((char *)this + 4284);
          do
          {
            if ( !v42 )
              break;
            v45 = *v38;
            if ( !*v38 )
              break;
            ++v38;
            *v44++ = v45;
            --v42;
            --v43;
          }
          while ( v43 );
          v46 = v44 - 1;
          if ( v43 )
            v46 = v44;
          *v46 = 0;
          if ( v43 )
          {
            v47 = *((_DWORD *)this + 1070) | 1;
            *((_DWORD *)this + 1070) = v47;
            *((_DWORD *)this + 1070) = v47 & 0xFFFFFFFD | (*(_DWORD *)(v37 + 528) != 0 ? 2 : 0);
            LODWORD(v96) = 0;
            UtilGetProtectedProcessInfo(*((void **)this + 6), (enum _PS_PROTECTED_TYPE *)&v96, 0);
            *((_DWORD *)this + 1070) = (4 * ((int)v96 > 0)) | *((_DWORD *)this + 1070) & 0xFFFFFFFB;
            *((_DWORD *)this + 204) |= 8u;
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              48,
              &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
              v43 == 0 ? 0x8007007A : 0);
          }
        }
      }
    }
    v146[0] = *((_QWORD *)this + 98);
    v147 = v94;
    updated = WerPluginsUpdateSignatures(
                *((void **)this + 97),
                (struct WER_PLUGIN_SIG_IN *)v146,
                (struct WER_PLUGIN_SIG_OUT *)&v143,
                &v97);
    if ( updated < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
          (unsigned int)updated);
      v49 = (CPluginList *)*((_QWORD *)this + 97);
      *((_QWORD *)this + 97) = 0;
LABEL_111:
      if ( v49 )
        WerPluginsDestroy(v49);
    }
  }
  v50 = (void *)*((_QWORD *)this + 91);
  *((_QWORD *)this + 91) = 0;
  if ( (unsigned __int64)v50 + 1 > 1 )
    CloseHandle(v50);
  v51 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, v143);
      v51 = WPP_GLOBAL_Control;
    }
    v52 = 0;
    for ( j = v145; v52 < j; ++v52 )
    {
      if ( v51 != &WPP_GLOBAL_Control && (*((_BYTE *)v51 + 28) & 8) != 0 )
      {
        WPP_SF_DSSD(v51[2], 52, v33, v52 + 1, v144[3 * v52], v144[3 * v52 + 1], v144[3 * v52 + 2]);
        j = v145;
        v51 = WPP_GLOBAL_Control;
      }
    }
  }
  if ( v10 )
  {
    if ( v51 != &WPP_GLOBAL_Control && (*((_BYTE *)v51 + 28) & 4) != 0 )
      WPP_SF_S(v51[2], 53, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, *((_QWORD *)this + 65));
    matched = CCrashReport::MatchRemoteEnvironmentVariable(*((HANDLE *)this + 6), v32, *((const wchar_t **)this + 65));
    v23 = matched >= 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, matched >= 0);
  }
  if ( (*(_BYTE *)(*((_QWORD *)this + 5) + 236LL) & 2) == 0
    && (*((_BYTE *)this + 4280) & 1) != 0
    && ((*((_BYTE *)this + 4280) & 2) != 0 || v23)
    && *((_WORD *)this + 2142) )
  {
    v55 = WerpLaunchAeDebug(
            *((HANDLE *)this + 6),
            *((HANDLE *)this + 7),
            (__int64)this + 824,
            (_OWORD *)this + 61,
            (__int64)this + 4280);
    v14 = v55;
    if ( v55 >= 0 )
    {
      *(_DWORD *)(*((_QWORD *)this + 5) + 176LL) = 1769472;
      goto LABEL_41;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
        (unsigned int)v55);
  }
  if ( v97 )
  {
    v56 = v143;
    if ( v143 || (MicrosoftTelemetryAssertTriggeredNoArgs(), (v56 = v143) != 0) )
    {
      v57 = -1;
      do
        ++v57;
      while ( *(_WORD *)(v56 + 2 * v57) );
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             (char *)this + 784,
                             v56) )
    {
      v13 = 2147942414LL;
      v14 = -2147024882;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_41;
      v16 = 56;
      goto LABEL_40;
    }
    v58 = (struct WER_PLUGIN_SIG_ELEMENT *)v144;
    v59 = v145;
  }
  else
  {
    v58 = (struct WER_PLUGIN_SIG_ELEMENT *)&v110;
    v59 = v94;
  }
  CLocalDumpGenerator::Initialize((CCrashReport *)((char *)this + 3616), *((HANDLE *)this + 6), *((_DWORD *)this + 8));
  CCrashReport::InitializeReportInformation(this, (struct _WER_REPORT_INFORMATION_V5 *)&pReportInformation);
  pReportInformation.dwSize = 2504;
  pReportInformation.hProcess = (HANDLE)*((_QWORD *)this + 6);
  v60 = hReportHandle;
  hReportHandle = 0;
  if ( v60 )
    WerReportCloseHandle(v60);
  v14 = WerReportCreate(*((PCWSTR *)this + 98), WerReportApplicationCrash, &pReportInformation, &hReportHandle);
  if ( v14 < 0 )
  {
LABEL_310:
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_41;
    v16 = 57;
    v13 = (unsigned int)v14;
LABEL_40:
    WPP_SF_d(v15[2], v16, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, v13);
LABEL_41:
    v17 = 0;
    goto LABEL_42;
  }
  if ( !hReportHandle )
  {
    v14 = -2147418113;
    goto LABEL_310;
  }
  v61 = 40;
  ReportId = WerpGetReportId(hReportHandle, &ReportIdForExceptionLogging, 40);
  if ( ReportId < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
        (unsigned int)ReportId);
    LOWORD(ReportIdForExceptionLogging) = 0;
  }
  if ( v100 != v101 )
  {
    v63 = v100;
    v64 = (wchar_t *)&IntegratorReportIdForExceptionLogging;
    do
    {
      if ( !v34 )
        break;
      v65 = *v63;
      if ( !*v63 )
        break;
      ++v63;
      *v64++ = v65;
      --v34;
      --v61;
    }
    while ( v61 );
    v66 = v64 - 1;
    if ( v61 )
      v66 = v64;
    *v66 = 0;
  }
  WerpSetIntegratorReportId(hReportHandle);
  v14 = CCrashReport::SetReportSignature(this, hReportHandle, v58, v59);
  if ( v14 < 0 )
  {
    v67 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_174;
    v68 = 59;
LABEL_173:
    WPP_SF_d(v67[2], v68, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, (unsigned int)v14);
LABEL_174:
    v17 = 0;
    goto LABEL_42;
  }
  v14 = WerpSetTelemetryAppParams(hReportHandle, (char *)this + 10424);
  if ( v14 < 0 )
  {
    v67 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_174;
    v68 = 60;
    goto LABEL_173;
  }
  v14 = WerpSetProcessTimelines(hReportHandle, (char *)this + 10152, 1);
  if ( v14 < 0 )
  {
    v67 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_174;
    v68 = 61;
    goto LABEL_173;
  }
  v14 = WerpSetTelemetryServiceParams(
          hReportHandle,
          *((_QWORD *)this + 81),
          *((_QWORD *)this + 85),
          *((unsigned int *)this + 178));
  if ( v14 < 0 )
  {
    v67 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_174;
    v68 = 62;
    goto LABEL_173;
  }
  *(_QWORD *)&v108 = (char *)this + 824;
  *((_QWORD *)&v108 + 1) = (char *)this + 976;
  pExceptionParam.bClientPointers = 0;
  pExceptionParam.pExceptionPointers = (PEXCEPTION_POINTERS)&v108;
  v17 = (char *)OpenThread(0x1FFFFFu, 0, *((_DWORD *)this + 185));
  hObject = v17;
  if ( v17 != (char *)-1LL && v17 + 1 != (char *)1 )
  {
    IsFatal = WerpSetReportIsFatal(hReportHandle, (*(_DWORD *)(*((_QWORD *)this + 5) + 236LL) & 4) == 0);
    if ( IsFatal < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
        (unsigned int)IsFatal);
    }
    Settings = CSettings::LoadSettings((CSettings *)v160, v70, v71, v72);
    if ( Settings < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
        (unsigned int)Settings);
    }
    if ( (unsigned int)TelGetWerTelemetryMode() == 3 )
      goto LABEL_207;
    v74 = v162;
    if ( v160[1664] )
      v74 = v161;
    if ( v74 )
    {
LABEL_207:
      v75 = WerDumpTypeMiniDump;
      *((_DWORD *)this + 1236) = 393505;
      v76 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v77 = 66;
        goto LABEL_210;
      }
    }
    else if ( (unsigned __int64)(*((_QWORD *)this + 90) - 1LL) > 0x40000766F41A4LL )
    {
      v75 = WerDumpTypeTriageDump;
      *((_DWORD *)this + 1236) = 1180068;
      v76 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v77 = 67;
        goto LABEL_210;
      }
    }
    else
    {
      v75 = WerDumpTypeMiniDump;
      *((_DWORD *)this + 1236) = 393505;
      v76 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v77 = 68;
LABEL_210:
        WPP_SF_(v76[2], v77, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
        v76 = WPP_GLOBAL_Control;
      }
    }
    pDumpCustomOptions.dwSize = 584;
    v78 = 0x20000000;
    if ( (*((_BYTE *)this + 28) & 0x40) != 0 )
    {
      if ( v76 != &WPP_GLOBAL_Control && (*((_BYTE *)v76 + 28) & 4) != 0 )
      {
        WPP_SF_(v76[2], 69, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
        v76 = WPP_GLOBAL_Control;
      }
      v78 = 536870913;
    }
    if ( v163 )
    {
      if ( !v164 )
      {
        v79 = *(_DWORD *)String;
LABEL_222:
        if ( v79 )
        {
          if ( v76 != &WPP_GLOBAL_Control && (*((_BYTE *)v76 + 28) & 4) != 0 )
            WPP_SF_(v76[2], 70, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
          v78 |= 1u;
        }
        if ( (unsigned int)UtilIsSystemShuttingDown() )
        {
          v80 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
            v80 = WPP_GLOBAL_Control;
          }
          v78 |= 1u;
        }
        else
        {
          v80 = WPP_GLOBAL_Control;
        }
        dwFlags = v78 | (*((int *)this + 7) >> 31) & 0x10000000;
        if ( !*((_DWORD *)this + 2537) && *((_QWORD *)this + 617) )
        {
          if ( v80 != &WPP_GLOBAL_Control && (*((_BYTE *)v80 + 28) & 4) != 0 )
          {
            WPP_SF_(v80[2], 72, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
            v80 = WPP_GLOBAL_Control;
          }
          v149 = *((_QWORD *)this + 617);
        }
        if ( v80 != &WPP_GLOBAL_Control && (*((_BYTE *)v80 + 28) & 4) != 0 )
          WPP_SF_Dd(v80[2], 73, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, (unsigned int)v75, dwFlags);
        v17 = hObject;
        v14 = WerReportAddDump(
                hReportHandle,
                *((HANDLE *)this + 6),
                hObject,
                v75,
                &pExceptionParam,
                &pDumpCustomOptions,
                dwFlags);
        if ( v14 >= 0 )
        {
          WerpSetQuickDumpType(hReportHandle, (unsigned int)v75);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              75,
              &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
              (unsigned int)v75);
          WerpSetCallBack(hReportHandle, CCrashReport::Static_WerCallbackFunction, this);
          CCrashReport::SetUIOptions(this, hReportHandle);
          v82 = WerpAddRegisteredDataToReport(hReportHandle, *((_QWORD *)this + 6));
          if ( v82 < 0
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              76,
              &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
              (unsigned int)v82);
          }
          v83 = WerpAddRegisteredDumpsToReport(hReportHandle, *((_QWORD *)this + 6));
          if ( v83 < 0
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              77,
              &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
              (unsigned int)v83);
          }
          if ( *((_DWORD *)this + 128) )
          {
            v84 = WerpAddIfRegisteredForAppLocalDump(hReportHandle, *((_QWORD *)this + 6), *((_QWORD *)this + 65));
            if ( v84 < 0
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                78,
                &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
                (unsigned int)v84);
            }
          }
          MaxProcessHoldMilliseconds = WerpGetMaxProcessHoldMilliseconds(*((HANDLE *)this + 6));
          *((_DWORD *)this + 2604) = MaxProcessHoldMilliseconds;
          if ( MaxProcessHoldMilliseconds )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                79,
                &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
                MaxProcessHoldMilliseconds);
            v86 = WerpReportSetMaxProcessHoldMilliseconds(hReportHandle, *((unsigned int *)this + 2604));
            if ( v86 < 0
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                80,
                &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
                (unsigned int)v86);
            }
          }
          if ( (int)WerpGetExtendedDiagData(*((_QWORD *)this + 6), &v104, &v98) >= 0 )
          {
            if ( v104 )
            {
              if ( v98 )
              {
                v87 = WerpAddMemoryBlock(hReportHandle, *((unsigned int *)this + 184));
                if ( v87 < 0
                  && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    81,
                    &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
                    (unsigned int)v87);
                }
              }
            }
          }
          v14 = WerReportSubmit(hReportHandle, WerConsentNotAsked, *((_DWORD *)this + 204), &pSubmitResult);
          *(_DWORD *)(*((_QWORD *)this + 5) + 176LL) = CCrashReport::MapReturnToHR(v14, pSubmitResult);
          if ( v14 >= 0 )
          {
            if ( *(_DWORD *)(*((_QWORD *)this + 5) + 176LL) == 1769472
              && (int)WerpLaunchAeDebug(
                        *((HANDLE *)this + 6),
                        *((HANDLE *)this + 7),
                        (__int64)this + 824,
                        (_OWORD *)this + 61,
                        (__int64)this + 4280) < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  83,
                  &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
                  (unsigned int)v14);
              }
              *(_DWORD *)(*((_QWORD *)this + 5) + 176LL) = -2145681408;
            }
            if ( pSubmitResult == WerReportQueued
              && (*(_DWORD *)this
               || *((_DWORD *)this + 2)
               || *((_DWORD *)this + 3)
               || (*((_DWORD *)this + 7) & 0x408) != 0) )
            {
              v174[0] = 0;
              if ( !(unsigned int)WerpGetStoreLocation(hReportHandle, v174, &v99) )
              {
                if ( v174[0] )
                {
                  if ( *((_DWORD *)this + 1) || *((_DWORD *)this + 3) || (*((_DWORD *)this + 7) & 0x400) != 0 )
                  {
                    v90 = UtilFlushFiles(v174, v88);
                    if ( v90 < 0
                      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        84,
                        &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
                        (unsigned int)v90);
                    }
                  }
                  else
                  {
                    CLocalDumpGenerator::GenerateDump(
                      (char *)this + 3616,
                      *((_QWORD *)this + 6),
                      *((unsigned int *)this + 185),
                      (char *)this + 824,
                      (char *)this + 976,
                      0);
                    if ( (*(_BYTE *)(*((_QWORD *)this + 5) + 236LL) & 4) == 0 )
                    {
                      ProcessId = GetProcessId(*((HANDLE *)this + 6));
                      WerpAddTerminationReason(ProcessId, 1, L"WerCrashReportFatal");
                      TerminateProcess(*((HANDLE *)this + 6), *((_DWORD *)this + 2) != 0 ? 1467 : 255);
                      WaitForSingleObject(*((HANDLE *)this + 6), 0x1388u);
                    }
                  }
                }
              }
            }
            v14 = 0;
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              82,
              &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
              (unsigned int)v14);
          }
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            74,
            &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
            (unsigned int)v14);
        }
        goto LABEL_42;
      }
      if ( v164 == 1 )
      {
        v79 = wcstol(String, 0, 10);
        v76 = WPP_GLOBAL_Control;
        goto LABEL_222;
      }
    }
    v79 = v166;
    goto LABEL_222;
  }
  LastError = GetLastError();
  v14 = LastError;
  if ( LastError > 0 )
    v14 = (unsigned __int16)LastError | 0x80070000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      63,
      &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
      *((unsigned int *)this + 185),
      v14);
LABEL_42:
  CLocalDumpGenerator::GenerateDump(
    (char *)this + 3616,
    *((_QWORD *)this + 6),
    *((unsigned int *)this + 185),
    (char *)this + 824,
    (char *)this + 976,
    0);
  if ( *((_DWORD *)this + 901)
    && !*((_DWORD *)this + 1)
    && (*(_BYTE *)(*((_QWORD *)this + 5) + 236LL) & 4) == 0
    && WaitForSingleObject(*((HANDLE *)this + 6), 0) )
  {
    v18 = GetProcessId(*((HANDLE *)this + 6));
    WerpAddTerminationReason(v18, 1, L"WerCrashReportRecovery");
    TerminateProcess(*((HANDLE *)this + 6), 0xFFu);
  }
  `eh vector destructor iterator'(v160, 0x68u, 0x31u, (void (*)(void *))CRegSetting::~CRegSetting);
  if ( v105 != v107 )
    operator delete(v105, (const struct std::nothrow_t *)&std::nothrow);
  if ( v100 != v102 )
    operator delete(v100, (const struct std::nothrow_t *)&std::nothrow);
  `eh vector destructor iterator'(
    v173,
    0x20u,
    9u,
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>);
  if ( (unsigned __int64)(v17 + 1) > 1 )
    CloseHandle(v17);
  if ( hReportHandle )
    WerReportCloseHandle(hReportHandle);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000ff8c  push    rbp
0x18000ff8e  push    rbx
0x18000ff8f  push    rsi
0x18000ff90  push    rdi
0x18000ff91  push    r12
0x18000ff93  push    r13
0x18000ff95  push    r14
0x18000ff97  push    r15
0x18000ff99  lea     rbp, [rsp-2A88h]
0x18000ffa1  mov     eax, 2B98h
0x18000ffa6  call    _alloca_probe
0x18000ffab  sub     rsp, rax
0x18000ffae  mov     rax, cs:__security_cookie
0x18000ffb5  xor     rax, rsp
0x18000ffb8  mov     [rbp+2AC0h+var_50], rax
0x18000ffbf  mov     rdi, rcx
0x18000ffc2  xor     r14d, r14d
0x18000ffc5  mov     [rbp+2AC0h+hReportHandle], r14
0x18000ffc9  xorps   xmm0, xmm0
0x18000ffcc  movups  xmmword ptr [rbp+2AC0h+pExceptionParam.pExceptionPointers], xmm0
0x18000ffd0  xor     edx, edx; Val
0x18000ffd2  mov     r8d, 158h; Size
0x18000ffd8  lea     rcx, [rbp+2AC0h+var_2770]; void *
0x18000ffdf  call    memset_0
0x18000ffe4  mov     ebx, 100h
0x18000ffe9  mov     r8d, ebx; Size
0x18000ffec  xor     edx, edx; Val
0x18000ffee  lea     rcx, [rbp+2AC0h+var_2510]; void *
0x18000fff5  call    memset_0
0x18000fffa  mov     r8d, ebx; Size
0x18000fffd  xor     edx, edx; Val
0x18000ffff  lea     rcx, [rbp+2AC0h+var_2610]; void *
0x180010006  call    memset_0
0x18001000b  mov     [rbp+2AC0h+var_2B20], r14d
0x18001000f  mov     [rbp+2AC0h+pSubmitResult], r14d
0x180010013  xor     edx, edx; Val
0x180010015  mov     r8d, 9C8h; Size
0x18001001b  lea     rcx, [rbp+2AC0h+pReportInformation]; void *
0x180010022  call    memset_0
0x180010027  xor     edx, edx; Val
0x180010029  mov     r8d, 248h; Size
0x18001002f  lea     rcx, [rbp+2AC0h+var_2410]; void *
0x180010036  call    memset_0
0x18001003b  mov     [rbp+2AC0h+hObject], r14
0x18001003f  mov     [rbp+2AC0h+var_2AA0], r14
0x180010043  xor     edx, edx; Val
0x180010045  lea     r8d, [rbx-30h]; Size
0x180010049  lea     rcx, [rbp+2AC0h+var_2A98]; void *
0x18001004d  call    memset_0
0x180010052  lea     rax, ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180010059  mov     [rsp+2BD0h+ReturnLength], rax; void (*)(void *)
0x18001005e  lea     r9, ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; void (*)(void *)
0x180010065  lea     edx, [r14+20h]; unsigned __int64
0x180010069  lea     r8d, [r14+9]; unsigned __int64
0x18001006d  lea     rcx, [rbp+2AC0h+var_380]; void *
0x180010074  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180010079  nop
0x18001007a  xorps   xmm0, xmm0
0x18001007d  movups  [rbp+2AC0h+var_2AC0], xmm0
0x180010081  mov     [rbp+2AC0h+var_2B18], r14d
0x180010085  mov     [rbp+2AC0h+var_2AF0], r14
0x180010089  lea     rax, [rbp+2AC0h+var_2B00]
0x18001008d  mov     [rbp+2AC0h+var_2B10], rax
0x180010091  lea     rax, [rbp+2AC0h+var_2B00]
0x180010095  mov     [rbp+2AC0h+var_2B08], rax
0x180010099  mov     [rbp+2AC0h+var_2B00], r14w
0x18001009e  movups  xmmword ptr [rbp+2AC0h+Uuid.Data1], xmm0
0x1800100a5  lea     rax, [rbp+2AC0h+var_2AD0]
0x1800100a9  mov     [rbp+2AC0h+var_2AE0], rax
0x1800100ad  lea     rax, [rbp+2AC0h+var_2AD0]
0x1800100b1  mov     [rbp+2AC0h+var_2AD8], rax
0x1800100b5  mov     [rbp+2AC0h+var_2AD0], r14w
0x1800100ba  mov     [rbp+2AC0h+var_2AE8], r14
0x1800100be  mov     [rbp+2AC0h+var_2B1C], r14d
0x1800100c2  mov     [rbp+2AC0h+SystemInformation], r14d
0x1800100c9  xor     edx, edx; Val
0x1800100cb  lea     r8d, [r14+44h]; Size
0x1800100cf  lea     rcx, [rbp+2AC0h+var_17DC]; void *
0x1800100d6  call    memset_0
0x1800100db  lea     rax, ??1CRegSetting@@QEAA@XZ; CRegSetting::~CRegSetting(void)
0x1800100e2  mov     [rsp+2BD0h+ReturnLength], rax; void (*)(void *)
0x1800100e7  lea     r9, ??0CRegSetting@@QEAA@XZ; void (*)(void *)
0x1800100ee  lea     edx, [r14+68h]; unsigned __int64
0x1800100f2  lea     r8d, [r14+31h]; unsigned __int64
0x1800100f6  lea     rcx, [rbp+2AC0h+var_1790]; void *
0x1800100fd  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180010102  lea     r15d, [r14+1]
0x180010106  mov     [rbp+2AC0h+var_3A8], r15d
0x18001010d  mov     [rbp+2AC0h+var_3A4], r15
0x180010114  mov     [rbp+2AC0h+var_39C], r14w
0x18001011c  mov     [rbp+2AC0h+var_39A], r15b
0x180010123  mov     [rbp+2AC0h+var_398], 5
0x18001012e  mov     [rbp+2AC0h+var_390], r14d
0x180010135  mov     [rbp+2AC0h+var_2B18], 104h
0x18001013c  mov     rcx, [rbp+2AC0h+var_2B10]
0x180010140  mov     [rbp+2AC0h+var_2B08], rcx
0x180010144  mov     [rcx], r14w
0x180010148  lea     rcx, [rbp+2AC0h+Uuid]; Uuid
0x18001014f  call    cs:__imp_UuidCreate
0x180010155  test    eax, eax
0x180010157  jz      short loc_18001016D
0x180010159  cmp     eax, 720h
0x18001015e  jz      short loc_18001016D
0x180010160  xorps   xmm0, xmm0
0x180010163  movdqa  xmmword ptr [rbp+2AC0h+Uuid.Data1], xmm0
0x18001016b  jmp     short loc_18001017D
0x18001016d  lea     rdx, [rbp+2AC0h+var_2B10]
0x180010171  lea     rcx, [rbp+2AC0h+Uuid]
0x180010178  call    ?UtilGetStringFromGUID@@YAJPEBU_GUID@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetStringFromGUID(_GUID const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001017d  lea     r12, WPP_GLOBAL_Control
0x180010184  lea     r13, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x18001018b  cmp     [rdi+0Ch], r14d
0x18001018f  jnz     short loc_18001019B
0x180010191  cmp     [rdi+4], r14d
0x180010195  jz      loc_1800102C0
0x18001019b  mov     rax, [rdi+28h]
0x18001019f  test    byte ptr [rax+0ECh], 4
0x1800101a6  jnz     loc_1800102C0
0x1800101ac  call    ?EnableShutdownPrivilege@CCrashReport@@CAJXZ; CCrashReport::EnableShutdownPrivilege(void)
0x1800101b1  test    eax, eax
0x1800101b3  js      loc_1800102C0
0x1800101b9  mov     eax, [rbp+2AC0h+Uuid.Data1]
0x1800101bf  mov     [rbp+2AC0h+SystemInformation], eax
0x1800101c5  movsd   xmm0, qword ptr [rbp+2AC0h+Uuid.Data2]
0x1800101cd  movsd   [rbp+2AC0h+var_17DC], xmm0
0x1800101d5  mov     eax, dword ptr [rbp+2AC0h+Uuid.Data4+4]
0x1800101db  mov     [rbp+2AC0h+var_17D4], eax
0x1800101e1  mov     eax, [rdi+158h]
0x1800101e7  mov     [rbp+2AC0h+var_17C0], eax
0x1800101ed  mov     eax, [rdi+15Ch]
0x1800101f3  mov     [rbp+2AC0h+var_17BC], eax
0x1800101f9  mov     rax, [rdi+1A0h]
0x180010200  mov     [rbp+2AC0h+var_17B8], rax
0x180010207  mov     eax, [rdi+2E4h]
0x18001020d  mov     [rbp+2AC0h+var_17A0], rax
0x180010214  mov     eax, [rdi+2E0h]
0x18001021a  mov     [rbp+2AC0h+var_17B0], rax
0x180010221  mov     [rsp+2BD0h+ReturnLength], r14; ReturnLength
0x180010226  mov     r9d, 8; ProcessInformationLength
0x18001022c  lea     r8, [rbp+2AC0h+ProcessInformation]; ProcessInformation
0x180010233  lea     edx, [r9+54h]; ProcessInformationClass
0x180010237  mov     rcx, [rdi+30h]; ProcessHandle
0x18001023b  call    cs:__imp_NtQueryInformationProcess
0x180010241  test    eax, eax
0x180010243  jns     short loc_18001026B
0x180010245  mov     rcx, cs:WPP_GLOBAL_Control
0x18001024c  cmp     rcx, r12
0x18001024f  jz      short loc_18001026B
0x180010251  test    byte ptr [rcx+1Ch], 2
0x180010255  jz      short loc_18001026B
0x180010257  mov     edx, 27h ; '''
0x18001025c  mov     r9d, eax
0x18001025f  mov     r8, r13
0x180010262  mov     rcx, [rcx+10h]
0x180010266  call    WPP_SF_d
0x18001026b  mov     rdx, [rdi+130h]; SourceString
0x180010272  lea     rcx, [rbp+2AC0h+DestinationString]; DestinationString
0x180010279  call    cs:__imp_RtlInitUnicodeString
0x18001027f  mov     r8d, 48h ; 'H'; SystemInformationLength
0x180010285  lea     rdx, [rbp+2AC0h+SystemInformation]; SystemInformation
0x18001028c  lea     ecx, [r8+46h]; SystemInformationClass
0x180010290  call    cs:__imp_NtSetSystemInformation
0x180010296  test    eax, eax
0x180010298  jns     short loc_1800102C0
0x18001029a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102a1  cmp     rcx, r12
0x1800102a4  jz      short loc_1800102C0
0x1800102a6  test    byte ptr [rcx+1Ch], 2
0x1800102aa  jz      short loc_1800102C0
0x1800102ac  mov     edx, 28h ; '('
0x1800102b1  mov     r9d, eax
0x1800102b4  mov     r8, r13
0x1800102b7  mov     rcx, [rcx+10h]
0x1800102bb  call    WPP_SF_d
0x1800102c0  lea     rax, [rdi+28B8h]
0x1800102c7  lea     r8, [rax+8]; unsigned __int64 *
0x1800102cb  lea     rdx, [rax+10h]; struct _GUID *
0x1800102cf  mov     rcx, [rdi+30h]; ProcessHandle
0x1800102d3  call    ?TelGetProcessAppSessionGuid@@YAJPEAXPEAU_GUID@@PEA_K@Z; TelGetProcessAppSessionGuid(void *,_GUID *,unsigned __int64 *)
0x1800102d8  test    eax, eax
0x1800102da  jns     short loc_180010302
0x1800102dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102e3  cmp     rcx, r12
0x1800102e6  jz      short loc_180010302
0x1800102e8  test    byte ptr [rcx+1Ch], 2
0x1800102ec  jz      short loc_180010302
0x1800102ee  mov     edx, 29h ; ')'
0x1800102f3  mov     r9d, eax
0x1800102f6  mov     r8, r13
0x1800102f9  mov     rcx, [rcx+10h]
0x1800102fd  call    WPP_SF_d
0x180010302  lea     rbx, [rdi+2908h]
0x180010309  lea     rsi, [rdi+28E8h]
0x180010310  mov     r8, rbx
0x180010313  mov     rdx, rsi
0x180010316  mov     rcx, [rdi+30h]; ProcessHandle
0x18001031a  call    ?UtilGetProcessTelemetryTargetAppParams@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; UtilGetProcessTelemetryTargetAppParams(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001031f  test    eax, eax
0x180010321  jns     short loc_180010349
0x180010323  mov     rcx, cs:WPP_GLOBAL_Control
0x18001032a  cmp     rcx, r12
0x18001032d  jz      short loc_180010349
0x18001032f  test    byte ptr [rcx+1Ch], 2
0x180010333  jz      short loc_180010349
0x180010335  mov     edx, 2Ah ; '*'
0x18001033a  mov     r9d, eax
0x18001033d  mov     r8, r13
0x180010340  mov     rcx, [rcx+10h]
0x180010344  call    WPP_SF_d
0x180010349  mov     rax, [rsi]
0x18001034c  mov     [rdi+28D8h], rax
0x180010353  mov     rax, [rbx]
0x180010356  mov     [rdi+28E0h], rax
0x18001035d  lea     rdx, [rdi+27A8h]; struct _WER_PROCESS_TIMELINES *
0x180010364  mov     rcx, [rdi+30h]; ProcessHandle
0x180010368  call    ?UtilGetProcessTimelines@@YAJPEAXPEAU_WER_PROCESS_TIMELINES@@@Z; UtilGetProcessTimelines(void *,_WER_PROCESS_TIMELINES *)
0x18001036d  test    eax, eax
0x18001036f  jns     short loc_180010397
0x180010371  mov     rcx, cs:WPP_GLOBAL_Control
0x180010378  cmp     rcx, r12
0x18001037b  jz      short loc_180010397
0x18001037d  test    byte ptr [rcx+1Ch], 2
0x180010381  jz      short loc_180010397
0x180010383  mov     edx, 2Bh ; '+'
0x180010388  mov     r9d, eax
0x18001038b  mov     r8, r13
0x18001038e  mov     rcx, [rcx+10h]
0x180010392  call    WPP_SF_d
0x180010397  test    cs:Application_ErrorEnableBits, r15b
0x18001039e  jz      loc_18001044B
0x1800103a4  mov     rax, [rdi+228h]
0x1800103ab  mov     [rsp+2BD0h+var_2B50], rax
0x1800103b3  mov     rax, [rdi+208h]
0x1800103ba  mov     [rsp+2BD0h+var_2B58], rax
0x1800103bf  mov     rax, [rbp+2AC0h+var_2B10]
0x1800103c3  mov     [rsp+2BD0h+var_2B60], rax
0x1800103c8  mov     rax, [rdi+110h]
0x1800103cf  mov     [rsp+2BD0h+var_2B68], rax
0x1800103d4  mov     rax, [rdi+58h]
0x1800103d8  mov     [rsp+2BD0h+var_2B70], rax
0x1800103dd  mov     rax, [rdi+0C8h]
0x1800103e4  mov     [rsp+2BD0h+var_2B78], rax
0x1800103e9  mov     eax, [rdi+0C4h]
0x1800103ef  mov     [rsp+2BD0h+var_2B80], eax
0x1800103f3  mov     rax, [rdi+1B8h]
0x1800103fa  mov     [rsp+2BD0h+var_2B88], rax
0x1800103ff  mov     rax, [rdi+1D8h]
0x180010406  mov     [rsp+2BD0h+var_2B90], rax
0x18001040b  mov     rax, [rdi+180h]
0x180010412  mov     [rsp+2BD0h+var_2B98], rax
0x180010417  mov     rax, [rdi+160h]
0x18001041e  mov     qword ptr [rsp+2BD0h+dwFlags], rax
0x180010423  mov     rax, [rdi+130h]
0x18001042a  mov     [rsp+2BD0h+pDumpCustomOptions], rax
0x18001042f  mov     rax, [rdi+0F0h]
0x180010436  mov     [rsp+2BD0h+ReturnLength], rax
0x18001043b  mov     r9, [rdi+0D0h]
0x180010442  mov     r8, [rdi+78h]
0x180010446  call    McTemplateU0zzzzzzzzdizzzzz_EventWriteTransfer
0x18001044b  mov     rdx, [rbp+2AC0h+var_2B10]; wchar_t *
0x18001044f  mov     rcx, rdi; this
0x180010452  call    ?LogCrashEventToAsimov@CCrashReport@@AEAAXPEB_W@Z; CCrashReport::LogCrashEventToAsimov(wchar_t const *)
0x180010457  mov     rax, [rdi+28h]
0x18001045b  test    byte ptr [rax+0ECh], 4
0x180010462  jnz     short loc_180010484
0x180010464  mov     [rbp+2AC0h+var_2B28], 1
0x18001046c  mov     r9d, 8; ProcessInformationLength
0x180010472  lea     r8, [rbp+2AC0h+var_2B28]; ProcessInformation
0x180010476  lea     edx, [r9+37h]; ProcessInformationClass
0x18001047a  mov     rcx, [rdi+30h]; ProcessHandle
0x18001047e  call    cs:__imp_NtSetInformationProcess
0x180010484  mov     [rbp+2AC0h+pReportInformation.dwSize], 9C8h
0x18001048e  mov     r13d, [rdi+200h]
0x180010495  mov     rsi, r14
0x180010498  lea     r14, __ImageBase
0x18001049f  test    r13d, r13d
0x1800104a2  jnz     loc_180010705
0x1800104a8  lea     r15d, [r13+8]
0x1800104ac  mov     [rbp+2AC0h+var_2B30], r15d
0x1800104b0  mov     rax, rsi
0x1800104b3  shl     rax, 5
0x1800104b7  lea     rbx, [rbp+2AC0h+var_380]
0x1800104be  add     rbx, rax
0x1800104c1  mov     r8, cs:?g_hFaultrepDLLModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hFaultrepDLLModule
0x1800104c8  mov     edx, ds:rva dword_180051A60[r14+rsi*4]
0x1800104d0  mov     rcx, rbx
0x1800104d3  call    ?UtilLoadString@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ulong,HINSTANCE__ *)
0x1800104d8  lea     rcx, [rsi+rsi*2]
0x1800104dc  mov     rax, [rbx]
0x1800104df  mov     [rbp+rcx*8+2AC0h+var_2AA0], rax
0x1800104e4  inc     rsi
0x1800104e7  cmp     rsi, r15
0x1800104ea  jnz     short loc_1800104B0
0x1800104ec  mov     rax, [rdi+78h]
0x1800104f0  mov     [rbp+2AC0h+var_2A98], rax
0x1800104f4  mov     rax, [rdi+0D0h]
0x1800104fb  mov     [rbp+2AC0h+var_2A80], rax
0x1800104ff  mov     rax, [rdi+0F0h]
0x180010506  mov     [rbp+2AC0h+var_2A68], rax
0x18001050a  mov     rax, [rdi+130h]
  ... truncated ...
```
