# PerfDiagStartupResourceUtilizationReporting::ReportStartupAppResourceUsageData<PerfDiagSecondaryLogons::CTraceContext,PerfDiagSecondaryLogons::CAnalysisContext>(PerfDiagSecondaryLogons::CTraceContext const *,PerfDiagSecondaryLogons::CAnalysisContext const *,std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::ProcessInfo,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,XPerfAddIn::IBootAnalysisServices::ProcessInfo>>> &,XPerfCore::TimeStamp const &,XPerfCore::TimeStamp const &,ulong)

- ea: `0x1800c49c4`
- end: `0x1800c5cc1`
- name: `??$ReportStartupAppResourceUsageData@VCTraceContext@PerfDiagSecondaryLogons@@UCAnalysisContext@2@@PerfDiagStartupResourceUtilizationReporting@@YAJPEBVCTraceContext@PerfDiagSecondaryLogons@@PEBUCAnalysisContext@2@AEAV?$map@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@UProcessInfo@IBootAnalysisServices@3@U?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@UProcessInfo@IBootAnalysisServices@3@@std@@@7@@std@@AEBVTimeStamp@XPerfCore@@3K@Z`
- size: `4861`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c6c24`

## callees

- `0x180007fe4`
- `0x180013870`
- `0x180015d80`
- `0x18001640c`
- `0x180016a1c`
- `0x18001769c`
- `0x180018044`
- `0x180018350`
- `0x180018438`
- `0x180022e3c`
- `0x180026800`
- `0x1800282a4`
- `0x18002b098`
- `0x18002b1b0`
- `0x18002be58`
- `0x18002c2f8`
- `0x18002dc88`
- `0x180037cb0`
- `0x180037f98`
- `0x18003866c`
- `0x18003c3ec`
- `0x18003cc3c`
- `0x18003df28`
- `0x18003e6a8`
- `0x18003ecf8`
- `0x18003fb50`
- `0x180042990`
- `0x180043030`
- `0x1800440ac`
- `0x180082b74`
- `0x1800c4648`
- `0x1800c46fc`
- `0x1800c4830`
- `0x1800c49c4`
- `0x1800c6594`
- `0x1800c7a28`
- `0x1800c87d4`
- `0x1800cf080`
- `0x1800cf140`
- `0x1800d6010`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x1800c4ce8`
- `ntdll!NtSetInformationFile` at `0x1800c4d48`
- `ntdll!NtSetInformationFile` at `0x1800c4ce8`
- `ntdll!NtSetInformationFile` at `0x1800c4d48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4b5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4c9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4b5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4c9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5b0d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c4f87`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c507e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c51e4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c5289`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c5707`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c57d0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c5b03`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c4f87`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c507e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c51e4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c5289`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c5707`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c57d0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c5b03`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c4c1a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c4e7b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c4c1a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c4e7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4cf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4d51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4cf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4d51`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c50b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c5111`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c50b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c5111`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800c4b53`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800c4c8f`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800c4b53`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800c4c8f`
- `KERNEL32!DeleteFileW` at `0x1800c4bef`
- `KERNEL32!DeleteFileW` at `0x1800c4e50`
- `KERNEL32!DeleteFileW` at `0x1800c4bef`
- `KERNEL32!DeleteFileW` at `0x1800c4e50`
- `KERNEL32!CreateDirectoryW` at `0x1800c4b88`
- `KERNEL32!CreateDirectoryW` at `0x1800c4de9`
- `KERNEL32!CreateDirectoryW` at `0x1800c4b88`
- `KERNEL32!CreateDirectoryW` at `0x1800c4de9`

## string_xrefs

- `0x1800c4b4c`: `%WINDIR%\system32\wdi\LogFiles\StartupInfo\`
- `0x1800c4c88`: `%WINDIR%\system32\wdi\LogFiles\StartupInfo\`
- `0x1800c4bad`: `_StartupInfo?.xml`
- `0x1800c4dbd`: `JsonSummary\`
- `0x1800c4e0e`: `_StartupInfo?.json`
- `0x1800c5691`: `	<Process Name="%ws" PID="%d" StartedInTraceSec="%.3I64f">\n		<StartTime>%ws</StartTime>\n		<CommandLine><![CDATA[%ws]]></CommandLine>\n		<DiskUsage Units="bytes">%I64lu</DiskUsage>\n		<CpuUsage Units="us">%I64d</CpuUsage>\n		<ParentPID>%d</ParentPID>\n		<ParentStartTime>%ws</ParentStartTime>\n		<ParentName>%ws</ParentName>\n	</Process>\n`
- `0x1800c5013`: `    "intervalStartMs": %I64lu,\n    "intervalEndMs": %I64lu,\n    "version": "1.0",\n    "userSid": "%ws",\n    "processes": [\n`
- `0x1800c5a30`: `        "memoryMetrics": {\n          "peakCommitSizeBytes": %I64lu,\n          "averageCommitSizeBytes": %I64lu,\n          "peakWorkingSetBytes": %I64lu,\n          "averageWorkingSetBytes": %I64lu\n        }\n      }`
- `0x1800c5173`: `	<ReadAheadAnalysisTime>%u</ReadAheadAnalysisTime>\n	<RurLegacyResourceAttribution>%u</RurLegacyResourceAttribution>\n</StartupData>\n`
- `0x1800c59c8`: `        "commandLine": "%ws",\n        "diskUsageBytes": %I64lu,\n        "cpuUsageUs": %I64d,\n        "parentPID": %d,\n        "parentStartTime": "%ws",\n        "parentName": "%ws",\n`
- `0x1800c520e`: `\n    ],\n    "analysisMetadata": {\n      "readAheadAnalysisTimeMs": %u,\n      "rurLegacyResourceAttributionMs": %u\n    }\n  }\n}\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall PerfDiagStartupResourceUtilizationReporting::ReportStartupAppResourceUsageData<PerfDiagSecondaryLogons::CTraceContext,PerfDiagSecondaryLogons::CAnalysisContext>(
        __int64 a1,
        __int64 a2,
        _QWORD **a3,
        _QWORD *a4,
        _QWORD *a5)
{
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rbx
  int SuccessorFileName; // r15d
  signed int v12; // eax
  size_t v13; // r9
  size_t v14; // r9
  unsigned __int16 *v15; // rdx
  HANDLE FileW; // rax
  void *v17; // r8
  HANDLE v18; // rdi
  void *v19; // rdx
  size_t v20; // r9
  signed int LastError; // eax
  __int64 v22; // rdx
  __int64 v23; // rdx
  size_t v25; // r9
  size_t v26; // r9
  unsigned __int16 *v27; // rdx
  HANDLE v28; // rax
  void *v29; // r8
  void *v30; // rdx
  _QWORD *v31; // r15
  unsigned __int16 *v32; // rcx
  LPCVOID *v33; // rax
  __int64 v34; // r8
  DWORD v35; // r8d
  LPCVOID *v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rcx
  LPCVOID *v39; // rdx
  const struct _EVENT_DESCRIPTOR *v40; // rdx
  DWORD TickCount; // esi
  const unsigned __int16 *v42; // r9
  DWORD v43; // r13d
  _QWORD *v44; // rax
  __int64 v45; // r14
  unsigned __int16 *v46; // rcx
  LPCVOID *v47; // rax
  __int64 v48; // r8
  DWORD v49; // r8d
  LPCVOID *v50; // rdx
  __int64 v51; // rax
  LPCVOID *v52; // rdx
  __int64 v53; // r13
  _QWORD *v54; // rax
  __int64 v55; // rsi
  __int64 i; // rax
  char FileName; // al
  __int64 v58; // rdx
  __int64 v59; // rax
  __int64 v60; // rbx
  unsigned __int16 *v61; // r15
  unsigned __int64 DataForProcess; // rbx
  __int64 v63; // rdi
  __int64 v64; // rsi
  __int64 v65; // rbx
  unsigned __int16 *v66; // rcx
  LPCVOID *v67; // rax
  __int64 v68; // r8
  DWORD v69; // r8d
  LPCVOID *v70; // rdx
  signed int v71; // eax
  __int64 v72; // rax
  LPCVOID *v73; // rdx
  __int64 v74; // rdx
  const unsigned __int16 *v75; // rcx
  LPCVOID *v76; // rax
  _QWORD *v77; // r9
  _QWORD *v78; // rcx
  _QWORD *v79; // r9
  __int64 v80; // rdx
  __int64 v81; // rdx
  LPCVOID *v82; // rdx
  __int64 v83; // rdx
  signed int v84; // eax
  __int64 v85; // rdx
  __int64 v86; // rdx
  __int64 v87; // rdx
  __int64 v88; // rdx
  __int64 v89; // rdx
  __int64 v90; // rdx
  __int64 v91; // rdx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-16F8h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-16F8h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-16E8h]
  __int64 v95; // [rsp+50h] [rbp-16C8h]
  _BYTE FileInformation[4]; // [rsp+70h] [rbp-16A8h] BYREF
  int v97; // [rsp+74h] [rbp-16A4h]
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp-16A0h] BYREF
  HANDLE hFile; // [rsp+80h] [rbp-1698h]
  __int64 v100; // [rsp+88h] [rbp-1690h] BYREF
  HANDLE v101; // [rsp+90h] [rbp-1688h]
  __int64 v102; // [rsp+98h] [rbp-1680h] BYREF
  _QWORD **v103; // [rsp+A0h] [rbp-1678h]
  unsigned __int16 *v104; // [rsp+A8h] [rbp-1670h] BYREF
  __int64 v105; // [rsp+B0h] [rbp-1668h] BYREF
  _QWORD *v106; // [rsp+B8h] [rbp-1660h]
  __int64 v107; // [rsp+C0h] [rbp-1658h] BYREF
  __int64 v108; // [rsp+C8h] [rbp-1650h] BYREF
  _QWORD *v109; // [rsp+D0h] [rbp-1648h]
  _QWORD v110[3]; // [rsp+D8h] [rbp-1640h] BYREF
  __int128 v111; // [rsp+F0h] [rbp-1628h] BYREF
  __int64 v112; // [rsp+100h] [rbp-1618h]
  int v113; // [rsp+108h] [rbp-1610h]
  __int64 v114; // [rsp+110h] [rbp-1608h]
  unsigned __int64 v115; // [rsp+118h] [rbp-1600h]
  _QWORD v116[2]; // [rsp+120h] [rbp-15F8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+130h] [rbp-15E8h] BYREF
  int v118[4]; // [rsp+140h] [rbp-15D8h] BYREF
  __int64 v119; // [rsp+150h] [rbp-15C8h]
  _QWORD *v120; // [rsp+158h] [rbp-15C0h]
  ATL::CAtlException *v121; // [rsp+160h] [rbp-15B8h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+168h] [rbp-15B0h] BYREF
  unsigned __int64 v123; // [rsp+178h] [rbp-15A0h]
  unsigned __int64 v124; // [rsp+180h] [rbp-1598h]
  LPCVOID v125[2]; // [rsp+188h] [rbp-1590h] BYREF
  __int64 v126; // [rsp+198h] [rbp-1580h]
  unsigned __int64 v127; // [rsp+1A0h] [rbp-1578h]
  _QWORD v128[3]; // [rsp+1A8h] [rbp-1570h] BYREF
  unsigned __int64 v129; // [rsp+1C0h] [rbp-1558h]
  _QWORD v130[3]; // [rsp+1C8h] [rbp-1550h] BYREF
  unsigned __int64 v131; // [rsp+1E0h] [rbp-1538h]
  _QWORD v132[3]; // [rsp+1E8h] [rbp-1530h] BYREF
  unsigned __int64 v133; // [rsp+200h] [rbp-1518h]
  __int64 v134; // [rsp+208h] [rbp-1510h] BYREF
  __int64 v135; // [rsp+210h] [rbp-1508h]
  __int64 v136; // [rsp+218h] [rbp-1500h]
  __int64 v137; // [rsp+220h] [rbp-14F8h]
  _OWORD v138[3]; // [rsp+230h] [rbp-14E8h] BYREF
  __int16 v139; // [rsp+260h] [rbp-14B8h]
  __int64 v140; // [rsp+270h] [rbp-14A8h]
  __int64 v141; // [rsp+278h] [rbp-14A0h]
  __int16 v142; // [rsp+280h] [rbp-1498h]
  __int64 v143; // [rsp+290h] [rbp-1488h]
  __int64 v144; // [rsp+298h] [rbp-1480h]
  char v145; // [rsp+2A0h] [rbp-1478h]
  WCHAR PathName[264]; // [rsp+2B0h] [rbp-1468h] BYREF
  WCHAR Dst[264]; // [rsp+4C0h] [rbp-1258h] BYREF
  unsigned __int16 v148[2048]; // [rsp+6D0h] [rbp-1048h] BYREF

  v109 = a4;
  v103 = a3;
  v120 = (_QWORD *)a2;
  v119 = a1;
  v106 = a5;
  v124 = 7;
  v123 = 0;
  LOWORD(lpBuffer[0]) = 0;
  v127 = 7;
  v126 = 0;
  LOWORD(v125[0]) = 0;
  NumberOfBytesWritten = 0;
  std::_Tree_comp<0,std::_Tset_traits<XPerfCore::PathNode const *,std::less<XPerfCore::PathNode const *>,std::allocator<XPerfCore::PathNode const *>,0>>::_Tree_comp<0,std::_Tset_traits<XPerfCore::PathNode const *,std::less<XPerfCore::PathNode const *>,std::allocator<XPerfCore::PathNode const *>,0>>(v116);
  std::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>(v118);
  try
  {
    v108 = 0;
    v8 = std::wstring::wstring(&v134, 0x10000);
    std::wstring::operator=(lpBuffer, v8);
    LOBYTE(v9) = 1;
    std::wstring::_Tidy(&v134, v9, 0);
  }
  catch ( std::bad_alloc )
  {
    PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData((PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v108);
    std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(v118);
    std::_Tree<std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>::~_Tree<std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>(v116);
    LOBYTE(v90) = 1;
    std::wstring::_Tidy(v125, v90, 0);
    LOBYTE(v91) = 1;
    std::wstring::_Tidy(lpBuffer, v91, 0);
    return 2147942414LL;
  }
  memset(v138, 0, sizeof(v138));
  v10 = -1;
  v101 = (HANDLE)-1LL;
  v141 = 7;
  v140 = 0;
  v139 = 0;
  v144 = 7;
  v143 = 0;
  v142 = 0;
  v145 = 0;
  if ( !*(_DWORD *)(*(_QWORD *)(a2 + 24) - 16LL) )
  {
    SuccessorFileName = -2058022908;
    goto LABEL_21;
  }
  if ( ExpandEnvironmentStringsW(L"%WINDIR%\\system32\\wdi\\LogFiles\\StartupInfo\\", Dst, 0x104u) )
  {
    CreateDirectoryW(Dst, 0);
    SuccessorFileName = StringCchCatW(Dst, 0x104u, *(const unsigned __int16 **)(a2 + 24), v13);
    if ( SuccessorFileName < 0 )
      goto LABEL_21;
    SuccessorFileName = StringCchCatW(Dst, 0x104u, L"_StartupInfo?.xml", v14);
    if ( SuccessorFileName < 0 )
      goto LABEL_21;
    SuccessorFileName = PerfDiagStartupResourceUtilizationReporting::FindSuccessorFileName(Dst, v15);
    if ( SuccessorFileName < 0 )
      goto LABEL_21;
    DeleteFileW(Dst);
    FileW = CreateFileW(Dst, 0x40050000u, 0, 0, 2u, 0, 0);
    v18 = FileW;
    hFile = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      v19 = *(void **)(a2 + 16);
      if ( !v19 )
      {
LABEL_33:
        SuccessorFileName = -2058022908;
        goto LABEL_19;
      }
      SuccessorFileName = PerfDiagStartupResourceUtilizationReporting::SetAccessPermissions(FileW, v19, v17);
      if ( SuccessorFileName < 0 )
        goto LABEL_18;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl) )
      {
        try
        {
          std::wstring::reserve(v125, 0x10000);
        }
        catch ( std::bad_alloc )
        {
          v97 = -2147024882;
          SuccessorFileName = -2147024882;
          goto LABEL_143;
        }
        if ( !ExpandEnvironmentStringsW(L"%WINDIR%\\system32\\wdi\\LogFiles\\StartupInfo\\", PathName, 0x104u) )
          goto LABEL_16;
        SuccessorFileName = StringCchCatW(PathName, 0x104u, L"JsonSummary\\", v20);
        if ( SuccessorFileName < 0 )
          goto LABEL_18;
        CreateDirectoryW(PathName, 0);
        SuccessorFileName = StringCchCatW(PathName, 0x104u, *(const unsigned __int16 **)(a2 + 24), v25);
        if ( SuccessorFileName < 0 )
          goto LABEL_18;
        SuccessorFileName = StringCchCatW(PathName, 0x104u, L"_StartupInfo?.json", v26);
        if ( SuccessorFileName < 0 )
          goto LABEL_18;
        SuccessorFileName = PerfDiagStartupResourceUtilizationReporting::FindSuccessorFileName(PathName, v27);
        if ( SuccessorFileName < 0 )
          goto LABEL_18;
        DeleteFileW(PathName);
        v28 = CreateFileW(PathName, 0x40050000u, 0, 0, 2u, 0, 0);
        v10 = (__int64)v28;
        v101 = v28;
        if ( v28 == (HANDLE)-1LL )
          goto LABEL_16;
        v30 = *(void **)(a2 + 16);
        if ( !v30 )
          goto LABEL_33;
        SuccessorFileName = PerfDiagStartupResourceUtilizationReporting::SetAccessPermissions(v28, v30, v29);
        if ( SuccessorFileName < 0 )
          goto LABEL_19;
      }
      v31 = v109;
      v32 = (unsigned __int16 *)lpBuffer;
      if ( v124 >= 8 )
        v32 = (unsigned __int16 *)lpBuffer[0];
      StringCchPrintfW(v32, v123, &qword_1800E8EC0, *v109 / 1000000LL, *v106 / 1000000LL);
      v33 = lpBuffer;
      if ( v124 >= 8 )
        v33 = (LPCVOID *)lpBuffer[0];
      v34 = -1;
      do
        ++v34;
      while ( *((_WORD *)v33 + v34) );
      v35 = 2 * v34;
      v36 = lpBuffer;
      if ( v124 >= 8 )
        v36 = (LPCVOID *)lpBuffer[0];
      if ( !WriteFile(v18, v36, v35, &NumberOfBytesWritten, 0) )
        goto LABEL_16;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl) )
      {
        v37 = std::char_traits<unsigned short>::length(qword_1800E8F98);
        std::wstring::assign(v125, v38, v37);
        SuccessorFileName = StringCchPrintfW(
                              v148,
                              0x800u,
                              L"    \"intervalStartMs\": %I64lu,\r\n"
                               "    \"intervalEndMs\": %I64lu,\r\n"
                               "    \"version\": \"1.0\",\r\n"
                               "    \"userSid\": \"%ws\",\r\n"
                               "    \"processes\": [\r\n",
                              *v31 / 1000000LL,
                              *v106 / 1000000LL,
                              *(_QWORD *)(a2 + 24));
        if ( SuccessorFileName < 0 )
          goto LABEL_18;
        std::wstring::append(v125, v148);
        v39 = v125;
        if ( v127 >= 8 )
          v39 = (LPCVOID *)v125[0];
        if ( !WriteFile((HANDLE)v10, v39, 2 * v126, &NumberOfBytesWritten, 0) )
          goto LABEL_16;
      }
      SuccessorFileName = PerfDiagStartupResourceUtilizationReporting::GetStartupProcesses<PerfDiagSecondaryLogons::CTraceContext>(
                            a1,
                            a3,
                            v116);
      if ( SuccessorFileName >= 0 )
      {
        try
        {
          PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Boot_RurReadAhead_Start, v40);
          TickCount = GetTickCount();
          SuccessorFileName = PerfDiagStartupResourceUtilizationReporting::GetReadAheadAmounts<PerfDiagSecondaryLogons::CTraceContext,PerfDiagSecondaryLogons::CAnalysisContext,std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::ProcessInfo>>(
                                a1,
                                a2,
                                (_DWORD)v103,
                                (_DWORD)v109,
                                (__int64)v106,
                                (__int64)v118);
          PerfDiagOutput::StatusLog::Write(
            (PerfDiagOutput::StatusLog *)PDEvt_Boot_RurReadAhead_Stop,
            (const struct _EVENT_DESCRIPTOR *)(unsigned int)SuccessorFileName,
            0,
            v42);
        }
        catch ( std::bad_alloc )
        {
          v97 = -2147024882;
          SuccessorFileName = -2147024882;
          goto LABEL_143;
        }
        if ( SuccessorFileName < 0 )
          goto LABEL_19;
        v43 = GetTickCount() - TickCount;
        v97 = v43;
        SuccessorFileName = PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::QueryBootPrefetcher((PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v108);
        if ( SuccessorFileName < 0 )
          goto LABEL_18;
        v44 = v103;
        v45 = **v103;
        while ( 1 )
        {
          if ( v45 == *v44 )
          {
            v46 = (unsigned __int16 *)lpBuffer;
            if ( v124 >= 8 )
              v46 = (unsigned __int16 *)lpBuffer[0];
            dwCreationDispositiona[0] = 0;
            SuccessorFileName = StringCchPrintfW(
                                  v46,
                                  v123,
                                  L"\t<ReadAheadAnalysisTime>%u</ReadAheadAnalysisTime>\r\n"
                                   "\t<RurLegacyResourceAttribution>%u</RurLegacyResourceAttribution>\r\n"
                                   "</StartupData>\r\n",
                                  v43,
                                  *(_QWORD *)dwCreationDispositiona);
            if ( SuccessorFileName < 0 )
              break;
            v47 = lpBuffer;
            if ( v124 >= 8 )
              v47 = (LPCVOID *)lpBuffer[0];
            v48 = -1;
            do
              ++v48;
            while ( *((_WORD *)v47 + v48) );
            v49 = 2 * v48;
            v50 = lpBuffer;
            if ( v124 >= 8 )
              v50 = (LPCVOID *)lpBuffer[0];
            if ( WriteFile(v18, v50, v49, &NumberOfBytesWritten, 0) )
            {
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl) )
                goto LABEL_70;
              dwCreationDisposition[0] = 0;
              SuccessorFileName = StringCchPrintfW(
                                    v148,
                                    0x800u,
                                    L"\r\n"
                                     "    ],\r\n"
                                     "    \"analysisMetadata\": {\r\n"
                                     "      \"readAheadAnalysisTimeMs\": %u,\r\n"
                                     "      \"rurLegacyResourceAttributionMs\": %u\r\n"
                                     "    }\r\n"
                                     "  }\r\n"
                                     "}\r\n",
                                    v43,
                                    *(_QWORD *)dwCreationDisposition);
              if ( SuccessorFileName < 0 )
                break;
              v51 = std::char_traits<unsigned short>::length(v148);
              std::wstring::assign(v125, v148, v51);
              v52 = v125;
              if ( v127 >= 8 )
                v52 = (LPCVOID *)v125[0];
              if ( WriteFile((HANDLE)v10, v52, 2 * v126, &NumberOfBytesWritten, 0) )
              {
LABEL_70:
                SuccessorFileName = 0;
                goto LABEL_20;
              }
            }
LABEL_16:
            LastError = GetLastError();
            SuccessorFileName = LastError;
            if ( LastError > 0 )
              SuccessorFileName = (unsigned __int16)LastError | 0x80070000;
            break;
          }
          v53 = *(_QWORD *)(v45 + 40);
          v105 = v53;
          v54 = (_QWORD *)std::_Tree<std::_Tset_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<XPerfAddIn::IProcessInfoSource::ProcessData const *>,0>>::find(
                            v116,
                            &IoStatusBlock,
                            &v105);
          if ( *v54 != v116[0] )
          {
            v55 = v119;
            v114 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v119 + 80) + 24LL))(
                     *(_QWORD *)(v119 + 80),
                     v53);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v100);
            if ( !(unsigned int)PerfDiagStartupResourceUtilizationReporting::GetProcessStartTime<PerfDiagSecondaryLogons::CTraceContext>(
                                  v55,
                                  v53,
                                  &v100) )
              goto LABEL_73;
            v104 = 0;
            v110[0] = *(_QWORD *)(v55 + 24);
            v110[1] = *(_QWORD *)(v55 + 16);
            v110[2] = *v120;
            v111 = 0;
            v112 = 0;
            v113 = 0;
            if ( (int)PerfDiagShared::CProcessImageNameLocator::GetProcessImageName(
                        (PerfDiagShared::CProcessImageNameLocator *)v110,
                        (const unsigned __int16 **)&v104,
                        (const struct XPerfAddIn::IProcessInfoSource::ProcessData *)v53) < 0 )
              goto LABEL_79;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v102);
            try
            {
              FileName = PerfDiagShared::CLocalNtImagePathDecoder::GetFileName(v138, v104, &v102);
            }
            catch ( ATL::CAtlException *v121 )
            {
              v97 = *(_DWORD *)v121;
              ATL::CStringData::Release((ATL::CStringData *)(v102 - 24));
              ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v111);
              ATL::CStringData::Release((ATL::CStringData *)(v100 - 24));
              SuccessorFileName = v97;
              goto LABEL_137;
            }
            if ( !FileName )
            {
              ATL::CStringData::Release((ATL::CStringData *)(v102 - 24));
              ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v111);
              ATL::CStringData::Release((ATL::CStringData *)(v100 - 24));
              goto LABEL_74;
            }
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v107);
            v58 = v53 + 8;
            if ( *(_QWORD *)v53 != XPerfCore::TimeStamp::Min )
              v58 = v53;
            v59 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(v55 + 24) + 32LL))(
                    *(_QWORD *)(v55 + 24),
                    v58,
                    *(unsigned int *)(v53 + 36),
                    1);
            v60 = v59;
            if ( v59 )
            {
              if ( !(unsigned int)PerfDiagStartupResourceUtilizationReporting::GetProcessStartTime<PerfDiagSecondaryLogons::CTraceContext>(
                                    v55,
                                    v59,
                                    &v107) )
              {
                ATL::CStringData::Release((ATL::CStringData *)(v107 - 24));
                ATL::CStringData::Release((ATL::CStringData *)(v102 - 24));
LABEL_79:
                ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v111);
LABEL_73:
                ATL::CStringData::Release((ATL::CStringData *)(v100 - 24));
                goto LABEL_74;
              }
              v61 = *(unsigned __int16 **)(v60 + 24);
              v104 = v61;
            }
            else
            {
              v61 = L"n/a";
              v104 = L"n/a";
              ATL::CSimpleStringT<unsigned short,0>::SetString(&v107, L"n/a");
            }
            DataForProcess = PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::GetDataForProcess(
                               (PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v108,
                               (const struct XPerfAddIn::IProcessInfoSource::ProcessData *)v53);
            v115 = *(_QWORD *)std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64>::operator[]((int)v118)
                 + *(unsigned int *)(v45 + 64)
                 + DataForProcess;
            v105 = *(_QWORD *)(v45 + 48) / 1000LL;
            v134 = 0;
            v135 = 0;
            v136 = 0;
            v137 = 0;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl)
              && (int)PerfDiagStartupResourceUtilizationReporting::CollectProcessMemoryMetrics<PerfDiagSecondaryLogons::CTraceContext>(
                        v55,
                        v53,
                        (_DWORD)v109,
                        (_DWORD)v106,
                        (__int64)&v134) < 0 )
            {
              v134 = 0;
              v135 = 0;
              v136 = 0;
              v137 = 0;
            }
            v63 = v107;
            v64 = v100;
            v65 = v102;
            v66 = (unsigned __int16 *)lpBuffer;
            if ( v124 >= 8 )
              v66 = (unsigned __int16 *)lpBuffer[0];
            LODWORD(v95) = *(_DWORD *)(v53 + 36);
            dwCreationDispositiona[0] = *(_DWORD *)(v53 + 32);
            SuccessorFileName = StringCchPrintfW(
                                  v66,
                                  v123,
                                  L"\t<Process Name=\"%ws\" PID=\"%d\" StartedInTraceSec=\"%.3I64f\">\r\n"
                                   "\t\t<StartTime>%ws</StartTime>\r\n"
                                   "\t\t<CommandLine><![CDATA[%ws]]></CommandLine>\r\n"
                                   "\t\t<DiskUsage Units=\"bytes\">%I64lu</DiskUsage>\r\n"
                                   "\t\t<CpuUsage Units=\"us\">%I64d</CpuUsage>\r\n"
                                   "\t\t<ParentPID>%d</ParentPID>\r\n"
                                   "\t\t<ParentStartTime>%ws</ParentStartTime>\r\n"
                                   "\t\t<ParentName>%ws</ParentName>\r\n"
                                   "\t</Process>\r\n",
                                  v102,
                                  *(_QWORD *)dwCreationDispositiona,
                                  (double)((int)*(_QWORD *)v53 / 1000) / 1000000.0,
                                  v100,
                                  v114,
                                  v115,
                                  v105,
                                  v95,
                                  v107,
                                  v61);
            if ( SuccessorFileName < 0 )
              goto LABEL_128;
            v67 = lpBuffer;
            if ( v124 >= 8 )
              v67 = (LPCVOID *)lpBuffer[0];
            v68 = -1;
            do
              ++v68;
            while ( *((_WORD *)v67 + v68) );
            v69 = 2 * v68;
            v70 = lpBuffer;
            if ( v124 >= 8 )
              v70 = (LPCVOID *)lpBuffer[0];
            if ( !WriteFile(hFile, v70, v69, &NumberOfBytesWritten, 0) )
            {
LABEL_103:
              v71 = GetLastError();
              SuccessorFileName = v71;
              if ( v71 > 0 )
                SuccessorFileName = (unsigned __int16)v71 | 0x80070000;
LABEL_105:
              ATL::CStringData::Release((ATL::CStringData *)(v63 - 24));
              ATL::CStringData::Release((ATL::CStringData *)(v65 - 24));
              ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v111);
              ATL::CStringData::Release((ATL::CStringData *)(v64 - 24));
LABEL_137:
              v18 = hFile;
              break;
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl) )
            {
              if ( !`PerfDiagStartupResourceUtilizationReporting::ReportStartupAppResourceUsageData<PerfDiagSecondaryLogons::CTraceContext,PerfDiagSecondaryLogons::CAnalysisContext>'[::C]::firstJsonProcess )
              {
                v72 = std::char_traits<unsigned short>::length(L",\r\n");
                std::wstring::assign(v125, L",\r\n", v72);
                v73 = v125;
                if ( v127 >= 8 )
                  v73 = (LPCVOID *)v125[0];
                if ( !WriteFile(v101, v73, 2 * v126, &NumberOfBytesWritten, 0) )
                  goto LABEL_103;
              }
              `PerfDiagStartupResourceUtilizationReporting::ReportStartupAppResourceUsageData<PerfDiagSecondaryLogons::CTraceContext,PerfDiagSecondaryLogons::CAnalysisContext>'[::C]::firstJsonProcess = 0;
              v133 = 7;
              v132[2] = 0;
              LOWORD(v132[0]) = 0;
              v131 = 7;
              v130[2] = 0;
              LOWORD(v130[0]) = 0;
              v129 = 7;
              v128[2] = 0;
              LOWORD(v128[0]) = 0;
              SuccessorFileName = PerfDiagStartupResourceUtilizationReporting::EscapeJsonString(v65, v132);
              if ( SuccessorFileName < 0 )
                goto LABEL_127;
              v75 = &qword_1800E1280;
              if ( v114 )
                v75 = (const unsigned __int16 *)v114;
              SuccessorFileName = PerfDiagStartupResourceUtilizationReporting::EscapeJsonString(v75, v130);
              if ( SuccessorFileName < 0 )
                goto LABEL_127;
              SuccessorFileName = PerfDiagStartupResourceUtilizationReporting::EscapeJsonString(v104, v128);
              if ( SuccessorFileName < 0 )
                goto LABEL_127;
              v76 = v125;
              if ( v127 >= 8 )
                v76 = (LPCVOID *)v125[0];
              v126 = 0;
              *(_WORD *)v76 = 0;
              std::wstring::reserve(v125, 3072);
              v77 = v132;
              if ( v133 >= 8 )
                v77 = (_QWORD *)v132[0];
              dwCreationDispositiona[0] = *(_DWORD *)(v53 + 32);
              SuccessorFileName = StringCchPrintfW(
                                    v148,
                                    0x800u,
                                    L"      {\r\n"
                                     "        \"name\": \"%ws\",\r\n"
                                     "        \"pid\": %d,\r\n"
                                     "        \"startedInTraceSec\": %.3f,\r\n"
                                     "        \"startTime\": \"%ws\",\r\n",
                                    v77,
                                    *(_QWORD *)dwCreationDispositiona,
                                    (double)(int)(*(_QWORD *)v53 / 1000LL) / 1000000.0,
                                    v64);
              if ( SuccessorFileName < 0 )
                goto LABEL_127;
              std::wstring::append(v125, v148);
              v78 = v128;
              if ( v129 >= 8 )
                v78 = (_QWORD *)v128[0];
              v79 = v130;
              if ( v131 >= 8 )
                v79 = (_QWORD *)v130[0];
              LODWORD(hTemplateFile) = *(_DWORD *)(v53 + 36);
              SuccessorFileName = StringCchPrintfW(
                                    v148,
                                    0x800u,
                                    L"        \"commandLine\": \"%ws\",\r\n"
                                     "        \"diskUsageBytes\": %I64lu,\r\n"
                                     "        \"cpuUsageUs\": %I64d,\r\n"
                                     "        \"parentPID\": %d,\r\n"
                                     "        \"parentStartTime\": \"%ws\",\r\n"
                                     "        \"parentName\": \"%ws\",\r\n",
                                    v79,
                                    v115,
                                    v105,
                                    hTemplateFile,
                                    v63,
                                    v78);
              if ( SuccessorFileName < 0
                || (std::wstring::append(v125, v148),
                    SuccessorFileName = StringCchPrintfW(
                                          v148,
                                          0x800u,
                                          L"        \"memoryMetrics\": {\r\n"
                                           "          \"peakCommitSizeBytes\": %I64lu,\r\n"
                                           "          \"averageCommitSizeBytes\": %I64lu,\r\n"
                                           "          \"peakWorkingSetBytes\": %I64lu,\r\n"
                                           "          \"averageWorkingSetBytes\": %I64lu\r\n"
                                           "        }\r\n"
                                           "      }",
                                          v134,
                                          v135,
                                          v136,
                                          v137),
                    SuccessorFileName < 0) )
              {
LABEL_127:
                LOBYTE(v74) = 1;
                std::wstring::_Tidy(v128, v74, 0);
                LOBYTE(v80) = 1;
                std::wstring::_Tidy(v130, v80, 0);
                LOBYTE(v81) = 1;
                std::wstring::_Tidy(v132, v81, 0);
LABEL_128:
                ATL::CStringData::Release((ATL::CStringData *)(v63 - 24));
                ATL::CStringData::Release((ATL::CStringData *)(v65 - 24));
                ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v111);
                ATL::CStringData::Release((ATL::CStringData *)(v64 - 24));
LABEL_143:
                v18 = hFile;
                goto LABEL_19;
              }
              std::wstring::append(v125, v148);
              v82 = v125;
              if ( v127 >= 8 )
                v82 = (LPCVOID *)v125[0];
              if ( !WriteFile(v101, v82, 2 * v126, &NumberOfBytesWritten, 0) )
              {
                v84 = GetLastError();
                SuccessorFileName = v84;
                if ( v84 > 0 )
                  SuccessorFileName = (unsigned __int16)v84 | 0x80070000;
                LOBYTE(v85) = 1;
                std::wstring::_Tidy(v128, v85, 0);
                LOBYTE(v86) = 1;
                std::wstring::_Tidy(v130, v86, 0);
                LOBYTE(v87) = 1;
                std::wstring::_Tidy(v132, v87, 0);
                goto LABEL_105;
              }
              LOBYTE(v83) = 1;
              std::wstring::_Tidy(v128, v83, 0);
              LOBYTE(v88) = 1;
              std::wstring::_Tidy(v130, v88, 0);
              LOBYTE(v89) = 1;
              std::wstring::_Tidy(v132, v89, 0);
            }
            ATL::CStringData::Release((ATL::CStringData *)(v63 - 24));
            ATL::CStringData::Release((ATL::CStringData *)(v65 - 24));
            ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v111);
            ATL::CStringData::Release((ATL::CStringData *)(v64 - 24));
            v18 = hFile;
          }
LABEL_74:
          v10 = (__int64)v101;
          v43 = v97;
          v44 = v103;
          if ( !*(_BYTE *)(v45 + 25) )
          {
            if ( *(_BYTE *)(*(_QWORD *)(v45 + 16) + 25LL) )
            {
              for ( i = *(_QWORD *)(v45 + 8); !*(_BYTE *)(i + 25) && v45 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
                v45 = i;
            }
            else
            {
              i = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::set<XPerfAddIn::IProcessInfoSource::VARange *>>>>::_Min();
            }
            v45 = i;
            v44 = v103;
          }
        }
      }
LABEL_18:
      if ( SuccessorFileName >= 0 )
      {
LABEL_20:
        CloseHandle(v18);
        v10 = (__int64)v101;
        goto LABEL_21;
      }
LABEL_19:
      IoStatusBlock = 0;
      FileInformation[0] = 1;
      NtSetInformationFile(v18, &IoStatusBlock, FileInformation, 1u, FileDispositionInformation);
      goto LABEL_20;
    }
  }
  v12 = GetLastError();
  SuccessorFileName = v12;
  if ( v12 > 0 )
    SuccessorFileName = (unsigned __int16)v12 | 0x80070000;
LABEL_21:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl)
    && v10 != -1 )
  {
    if ( SuccessorFileName < 0 )
    {
      IoStatusBlock = 0;
      FileInformation[0] = 1;
      NtSetInformationFile((HANDLE)v10, &IoStatusBlock, FileInformation, 1u, FileDispositionInformation);
    }
    CloseHandle((HANDLE)v10);
  }
  PerfDiagShared::CNtImagePathDecoderBase::~CNtImagePathDecoderBase((PerfDiagShared::CNtImagePathDecoderBase *)v138);
  PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData((PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v108);
  std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(v118);
  std::_Tree<std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>::~_Tree<std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>(v116);
  LOBYTE(v22) = 1;
  std::wstring::_Tidy(v125, v22, 0);
  LOBYTE(v23) = 1;
  std::wstring::_Tidy(lpBuffer, v23, 0);
  return (unsigned int)SuccessorFileName;
}

```

## disassembly

```asm
0x1800c49c4  push    rbx
0x1800c49c6  push    rsi
0x1800c49c7  push    rdi
0x1800c49c8  push    r12
0x1800c49ca  push    r13
0x1800c49cc  push    r14
0x1800c49ce  push    r15
0x1800c49d0  mov     eax, 16E0h
0x1800c49d5  call    _alloca_probe
0x1800c49da  sub     rsp, rax
0x1800c49dd  mov     rax, cs:__security_cookie
0x1800c49e4  xor     rax, rsp
0x1800c49e7  mov     [rsp+1718h+var_48], rax
0x1800c49ef  mov     [rsp+1718h+var_1648], r9
0x1800c49f7  mov     rsi, r8
0x1800c49fa  mov     [rsp+1718h+var_1678], r8
0x1800c4a02  mov     r14, rdx
0x1800c4a05  mov     [rsp+1718h+var_15C0], rdx
0x1800c4a0d  mov     r13, rcx
0x1800c4a10  mov     [rsp+1718h+var_15C8], rcx
0x1800c4a18  mov     rax, [rsp+1718h+arg_20]
0x1800c4a20  mov     [rsp+1718h+var_1660], rax
0x1800c4a28  mov     edi, 7
0x1800c4a2d  mov     [rsp+1718h+var_1598], rdi
0x1800c4a35  xor     r12d, r12d
0x1800c4a38  mov     [rsp+1718h+var_15A0], r12
0x1800c4a40  mov     word ptr [rsp+1718h+lpBuffer], r12w
0x1800c4a49  mov     [rsp+1718h+var_1578], rdi
0x1800c4a51  mov     [rsp+1718h+var_1580], r12
0x1800c4a59  mov     word ptr [rsp+1718h+var_1590], r12w
0x1800c4a62  mov     [rsp+1718h+NumberOfBytesWritten], r12d
0x1800c4a67  lea     rcx, [rsp+1718h+var_15F8]
0x1800c4a6f  call    ??0?$_Tree_comp@$0A@V?$_Tset_traits@PEBUPathNode@XPerfCore@@U?$less@PEBUPathNode@XPerfCore@@@std@@V?$allocator@PEBUPathNode@XPerfCore@@@4@$0A@@std@@@std@@QEAA@AEBU?$less@PEBUPathNode@XPerfCore@@@1@AEBV?$allocator@PEBUPathNode@XPerfCore@@@1@@Z; std::_Tree_comp<0,std::_Tset_traits<XPerfCore::PathNode const *,std::less<XPerfCore::PathNode const *>,std::allocator<XPerfCore::PathNode const *>,0>>::_Tree_comp<0,std::_Tset_traits<XPerfCore::PathNode const *,std::less<XPerfCore::PathNode const *>,std::allocator<XPerfCore::PathNode const *>,0>>(std::less<XPerfCore::PathNode const *> const &,std::allocator<XPerfCore::PathNode const *> const &)
0x1800c4a74  nop
0x1800c4a75  lea     rcx, [rsp+1718h+var_15D8]
0x1800c4a7d  call    ??0?$map@PEBUThreadData@IProcessInfoSource@XPerfAddIn@@VTimeStampDelta@XPerfCore@@U?$less@PEBUThreadData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUThreadData@IProcessInfoSource@XPerfAddIn@@VTimeStampDelta@XPerfCore@@@std@@@7@@std@@QEAA@XZ; std::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>(void)
0x1800c4a82  nop
0x1800c4a83  mov     [rsp+1718h+var_1650], r12
0x1800c4a8b  mov     edx, 10000h
0x1800c4a90  lea     rcx, [rsp+1718h+var_1510]
0x1800c4a98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1800c4a9d  mov     rdx, rax
0x1800c4aa0  lea     rcx, [rsp+1718h+lpBuffer]
0x1800c4aa8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800c4aad  xor     r8d, r8d
0x1800c4ab0  mov     dl, 1
0x1800c4ab2  lea     rcx, [rsp+1718h+var_1510]
0x1800c4aba  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c4abf  nop
0x1800c4ac0  xorps   xmm0, xmm0
0x1800c4ac3  movdqa  [rsp+1718h+var_14E8], xmm0
0x1800c4acc  xorps   xmm1, xmm1
0x1800c4acf  movdqa  [rsp+1718h+var_14D8], xmm1
0x1800c4ad8  movdqa  [rsp+1718h+var_14C8], xmm0
0x1800c4ae1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800c4ae5  mov     [rsp+1718h+var_1688], rbx
0x1800c4aed  mov     [rsp+1718h+var_14A0], rdi
0x1800c4af5  mov     [rsp+1718h+var_14A8], r12
0x1800c4afd  mov     [rsp+1718h+var_14B8], r12w
0x1800c4b06  mov     [rsp+1718h+var_1480], rdi
0x1800c4b0e  mov     [rsp+1718h+var_1488], r12
0x1800c4b16  mov     [rsp+1718h+var_1498], r12w
0x1800c4b1f  mov     [rsp+1718h+var_1478], r12b
0x1800c4b27  mov     rax, [r14+18h]
0x1800c4b2b  cmp     [rax-10h], r12d
0x1800c4b2f  jnz     short loc_1800C4B3C
0x1800c4b31  mov     r15d, 85551004h
0x1800c4b37  jmp     loc_1800C4CFF
0x1800c4b3c  mov     edi, 104h
0x1800c4b41  mov     r8d, edi; nSize
0x1800c4b44  lea     rdx, [rsp+1718h+Dst]; lpDst
0x1800c4b4c  lea     rcx, Src; "%WINDIR%\\system32\\wdi\\LogFiles\\Star"...
0x1800c4b53  call    cs:__imp_ExpandEnvironmentStringsW
0x1800c4b59  test    eax, eax
0x1800c4b5b  jnz     short loc_1800C4B7E
0x1800c4b5d  call    cs:__imp_GetLastError
0x1800c4b63  mov     r15d, eax
0x1800c4b66  test    eax, eax
0x1800c4b68  jle     loc_1800C4CFF
0x1800c4b6e  movzx   r15d, ax
0x1800c4b72  or      r15d, 80070000h
0x1800c4b79  jmp     loc_1800C4CFF
0x1800c4b7e  xor     edx, edx; lpSecurityAttributes
0x1800c4b80  lea     rcx, [rsp+1718h+Dst]; lpPathName
0x1800c4b88  call    cs:__imp_CreateDirectoryW
0x1800c4b8e  mov     r8, [r14+18h]; unsigned __int16 *
0x1800c4b92  mov     rdx, rdi; unsigned __int64
0x1800c4b95  lea     rcx, [rsp+1718h+Dst]; unsigned __int16 *
0x1800c4b9d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800c4ba2  mov     r15d, eax
0x1800c4ba5  test    eax, eax
0x1800c4ba7  js      loc_1800C4CFF
0x1800c4bad  lea     r8, aStartupinfoXml; "_StartupInfo?.xml"
0x1800c4bb4  mov     rdx, rdi; unsigned __int64
0x1800c4bb7  lea     rcx, [rsp+1718h+Dst]; unsigned __int16 *
0x1800c4bbf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800c4bc4  mov     r15d, eax
0x1800c4bc7  test    eax, eax
0x1800c4bc9  js      loc_1800C4CFF
0x1800c4bcf  lea     rcx, [rsp+1718h+Dst]; lpFileName
0x1800c4bd7  call    ?FindSuccessorFileName@PerfDiagStartupResourceUtilizationReporting@@YAJPEAG@Z; PerfDiagStartupResourceUtilizationReporting::FindSuccessorFileName(ushort *)
0x1800c4bdc  mov     r15d, eax
0x1800c4bdf  test    eax, eax
0x1800c4be1  js      loc_1800C4CFF
0x1800c4be7  lea     rcx, [rsp+1718h+Dst]; lpFileName
0x1800c4bef  call    cs:__imp_DeleteFileW
0x1800c4bf5  mov     [rsp+1718h+hTemplateFile], r12; hTemplateFile
0x1800c4bfa  mov     [rsp+1718h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1800c4bff  mov     [rsp+1718h+dwCreationDisposition], 2; dwCreationDisposition
0x1800c4c07  xor     r9d, r9d; lpSecurityAttributes
0x1800c4c0a  xor     r8d, r8d; dwShareMode
0x1800c4c0d  mov     edx, 40050000h; dwDesiredAccess
0x1800c4c12  lea     rcx, [rsp+1718h+Dst]; lpFileName
0x1800c4c1a  call    cs:__imp_CreateFileW
0x1800c4c20  mov     rdi, rax
0x1800c4c23  mov     [rsp+1718h+hFile], rax
0x1800c4c2b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c4c2f  jz      loc_1800C4B5D
0x1800c4c35  mov     rdx, [r14+10h]; pSid
0x1800c4c39  test    rdx, rdx
0x1800c4c3c  jz      loc_1800C4E9F
0x1800c4c42  mov     rcx, rax; handle
0x1800c4c45  call    ?SetAccessPermissions@PerfDiagStartupResourceUtilizationReporting@@YAJQEAX0@Z; PerfDiagStartupResourceUtilizationReporting::SetAccessPermissions(void * const,void * const)
0x1800c4c4a  mov     r15d, eax
0x1800c4c4d  test    eax, eax
0x1800c4c4f  js      short loc_1800C4CB5
0x1800c4c51  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace> `wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl(void)'::`2'::impl
0x1800c4c58  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(void)
0x1800c4c5d  test    al, al
0x1800c4c5f  jz      loc_1800C4EBD
0x1800c4c65  mov     edx, 10000h
0x1800c4c6a  lea     rcx, [rsp+1718h+var_1590]
0x1800c4c72  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x1800c4c77  nop
0x1800c4c78  mov     ebx, 104h
0x1800c4c7d  mov     r8d, ebx; nSize
0x1800c4c80  lea     rdx, [rsp+1718h+PathName]; lpDst
0x1800c4c88  lea     rcx, Src; "%WINDIR%\\system32\\wdi\\LogFiles\\Star"...
0x1800c4c8f  call    cs:__imp_ExpandEnvironmentStringsW
0x1800c4c95  test    eax, eax
0x1800c4c97  jnz     loc_1800C4DBD
0x1800c4c9d  call    cs:__imp_GetLastError
0x1800c4ca3  mov     r15d, eax
0x1800c4ca6  test    eax, eax
0x1800c4ca8  jle     short loc_1800C4CB5
0x1800c4caa  movzx   r15d, ax
0x1800c4cae  or      r15d, 80070000h
0x1800c4cb5  test    r15d, r15d
0x1800c4cb8  jns     short loc_1800C4CEE
0x1800c4cba  xorps   xmm0, xmm0
0x1800c4cbd  movups  xmmword ptr [rsp+1718h+IoStatusBlock], xmm0
0x1800c4cc5  mov     [rsp+1718h+FileInformation], 1
0x1800c4cca  mov     [rsp+1718h+dwCreationDisposition], 0Dh; FileInformationClass
0x1800c4cd2  mov     r9d, 1; Length
0x1800c4cd8  lea     r8, [rsp+1718h+FileInformation]; FileInformation
0x1800c4cdd  lea     rdx, [rsp+1718h+IoStatusBlock]; IoStatusBlock
0x1800c4ce5  mov     rcx, rdi; FileHandle
0x1800c4ce8  call    cs:__imp_NtSetInformationFile
0x1800c4cee  mov     rcx, rdi; hObject
0x1800c4cf1  call    cs:__imp_CloseHandle
0x1800c4cf7  mov     rbx, [rsp+1718h+var_1688]
0x1800c4cff  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace> `wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl(void)'::`2'::impl
0x1800c4d06  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(void)
0x1800c4d0b  test    al, al
0x1800c4d0d  jz      short loc_1800C4D58
0x1800c4d0f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800c4d13  jz      short loc_1800C4D58
0x1800c4d15  test    r15d, r15d
0x1800c4d18  jns     short loc_1800C4D4E
0x1800c4d1a  xorps   xmm0, xmm0
0x1800c4d1d  movups  xmmword ptr [rsp+1718h+IoStatusBlock], xmm0
0x1800c4d25  mov     [rsp+1718h+FileInformation], 1
0x1800c4d2a  mov     [rsp+1718h+dwCreationDisposition], 0Dh; FileInformationClass
0x1800c4d32  mov     r9d, 1; Length
0x1800c4d38  lea     r8, [rsp+1718h+FileInformation]; FileInformation
0x1800c4d3d  lea     rdx, [rsp+1718h+IoStatusBlock]; IoStatusBlock
0x1800c4d45  mov     rcx, rbx; FileHandle
0x1800c4d48  call    cs:__imp_NtSetInformationFile
0x1800c4d4e  mov     rcx, rbx; hObject
0x1800c4d51  call    cs:__imp_CloseHandle
0x1800c4d57  nop
0x1800c4d58  lea     rcx, [rsp+1718h+var_14E8]; this
0x1800c4d60  call    ??1CNtImagePathDecoderBase@PerfDiagShared@@QEAA@XZ; PerfDiagShared::CNtImagePathDecoderBase::~CNtImagePathDecoderBase(void)
0x1800c4d65  nop
0x1800c4d66  lea     rcx, [rsp+1718h+var_1650]; this
0x1800c4d6e  call    ??1BootPrefetcherData@PerfDiagStartupResourceUtilizationReporting@@QEAA@XZ; PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData(void)
0x1800c4d73  nop
0x1800c4d74  lea     rcx, [rsp+1718h+var_15D8]
0x1800c4d7c  call    ??1?$_Tree@V?$_Tmap_traits@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@_KU?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(void)
0x1800c4d81  nop
0x1800c4d82  lea     rcx, [rsp+1718h+var_15F8]
0x1800c4d8a  call    ??1?$_Tree@V?$_Tset_traits@UClassicEventStats@ITraceStatsInfoSource@XPerfAddIn@@UlessEventStats@?$CTraceStatsSource@UCClassicEtwEventPolicy@XPerfAddIn@@@3@V?$allocator@UClassicEventStats@ITraceStatsInfoSource@XPerfAddIn@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>::~_Tree<std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>(void)
0x1800c4d8f  nop
0x1800c4d90  xor     r8d, r8d
0x1800c4d93  mov     dl, 1
0x1800c4d95  lea     rcx, [rsp+1718h+var_1590]
0x1800c4d9d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c4da2  nop
0x1800c4da3  xor     r8d, r8d
0x1800c4da6  mov     dl, 1
0x1800c4da8  lea     rcx, [rsp+1718h+lpBuffer]
0x1800c4db0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c4db5  mov     eax, r15d
0x1800c4db8  jmp     loc_1800C5C9E
0x1800c4dbd  lea     r8, aJsonsummary; "JsonSummary\\"
0x1800c4dc4  mov     rdx, rbx; unsigned __int64
0x1800c4dc7  lea     rcx, [rsp+1718h+PathName]; unsigned __int16 *
0x1800c4dcf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800c4dd4  mov     r15d, eax
0x1800c4dd7  test    eax, eax
0x1800c4dd9  js      loc_1800C4CB5
0x1800c4ddf  xor     edx, edx; lpSecurityAttributes
0x1800c4de1  lea     rcx, [rsp+1718h+PathName]; lpPathName
0x1800c4de9  call    cs:__imp_CreateDirectoryW
0x1800c4def  mov     r8, [r14+18h]; unsigned __int16 *
0x1800c4df3  mov     rdx, rbx; unsigned __int64
0x1800c4df6  lea     rcx, [rsp+1718h+PathName]; unsigned __int16 *
0x1800c4dfe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800c4e03  mov     r15d, eax
0x1800c4e06  test    eax, eax
0x1800c4e08  js      loc_1800C4CB5
0x1800c4e0e  lea     r8, aStartupinfoJso; "_StartupInfo?.json"
0x1800c4e15  mov     rdx, rbx; unsigned __int64
0x1800c4e18  lea     rcx, [rsp+1718h+PathName]; unsigned __int16 *
0x1800c4e20  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800c4e25  mov     r15d, eax
0x1800c4e28  test    eax, eax
0x1800c4e2a  js      loc_1800C4CB5
0x1800c4e30  lea     rcx, [rsp+1718h+PathName]; lpFileName
0x1800c4e38  call    ?FindSuccessorFileName@PerfDiagStartupResourceUtilizationReporting@@YAJPEAG@Z; PerfDiagStartupResourceUtilizationReporting::FindSuccessorFileName(ushort *)
0x1800c4e3d  mov     r15d, eax
0x1800c4e40  test    eax, eax
0x1800c4e42  js      loc_1800C4CB5
0x1800c4e48  lea     rcx, [rsp+1718h+PathName]; lpFileName
0x1800c4e50  call    cs:__imp_DeleteFileW
0x1800c4e56  mov     [rsp+1718h+hTemplateFile], r12; hTemplateFile
0x1800c4e5b  mov     [rsp+1718h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1800c4e60  mov     [rsp+1718h+dwCreationDisposition], 2; dwCreationDisposition
0x1800c4e68  xor     r9d, r9d; lpSecurityAttributes
0x1800c4e6b  xor     r8d, r8d; dwShareMode
0x1800c4e6e  mov     edx, 40050000h; dwDesiredAccess
0x1800c4e73  lea     rcx, [rsp+1718h+PathName]; lpFileName
0x1800c4e7b  call    cs:__imp_CreateFileW
0x1800c4e81  mov     rbx, rax
0x1800c4e84  mov     [rsp+1718h+var_1688], rax
0x1800c4e8c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c4e90  jz      loc_1800C4C9D
0x1800c4e96  mov     rdx, [r14+10h]; pSid
0x1800c4e9a  test    rdx, rdx
0x1800c4e9d  jnz     short loc_1800C4EAA
0x1800c4e9f  mov     r15d, 85551004h
0x1800c4ea5  jmp     loc_1800C4CBA
0x1800c4eaa  mov     rcx, rax; handle
0x1800c4ead  call    ?SetAccessPermissions@PerfDiagStartupResourceUtilizationReporting@@YAJQEAX0@Z; PerfDiagStartupResourceUtilizationReporting::SetAccessPermissions(void * const,void * const)
0x1800c4eb2  mov     r15d, eax
0x1800c4eb5  test    eax, eax
0x1800c4eb7  js      loc_1800C4CBA
0x1800c4ebd  mov     r9, 431BDE82D7B634DBh
0x1800c4ec7  mov     rax, r9
0x1800c4eca  mov     rcx, [rsp+1718h+var_1660]
0x1800c4ed2  imul    qword ptr [rcx]
0x1800c4ed5  mov     r8, rdx
0x1800c4ed8  sar     r8, 12h
0x1800c4edc  mov     rax, r8
0x1800c4edf  shr     rax, 3Fh
0x1800c4ee3  add     r8, rax
0x1800c4ee6  mov     rax, r9
0x1800c4ee9  mov     r15, [rsp+1718h+var_1648]
0x1800c4ef1  imul    qword ptr [r15]
0x1800c4ef4  sar     rdx, 12h
0x1800c4ef8  mov     r9, rdx
0x1800c4efb  shr     r9, 3Fh
0x1800c4eff  add     r9, rdx
0x1800c4f02  lea     rcx, [rsp+1718h+lpBuffer]
0x1800c4f0a  cmp     [rsp+1718h+var_1598], 8
0x1800c4f13  cmovnb  rcx, [rsp+1718h+lpBuffer]; unsigned __int16 *
0x1800c4f1c  mov     qword ptr [rsp+1718h+dwCreationDisposition], r8
0x1800c4f21  lea     r8, qword_1800E8EC0; unsigned __int16 *
0x1800c4f28  mov     rdx, [rsp+1718h+var_15A0]; unsigned __int64
0x1800c4f30  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c4f35  lea     rax, [rsp+1718h+lpBuffer]
0x1800c4f3d  cmp     [rsp+1718h+var_1598], 8
0x1800c4f46  cmovnb  rax, [rsp+1718h+lpBuffer]
0x1800c4f4f  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800c4f53  inc     r8
0x1800c4f56  cmp     [rax+r8*2], r12w
0x1800c4f5b  jnz     short loc_1800C4F53
0x1800c4f5d  add     r8d, r8d; nNumberOfBytesToWrite
0x1800c4f60  lea     rdx, [rsp+1718h+lpBuffer]
0x1800c4f68  cmp     [rsp+1718h+var_1598], 8
0x1800c4f71  cmovnb  rdx, [rsp+1718h+lpBuffer]; lpBuffer
0x1800c4f7a  mov     qword ptr [rsp+1718h+dwCreationDisposition], r12; lpOverlapped
0x1800c4f7f  lea     r9, [rsp+1718h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c4f84  mov     rcx, rdi; hFile
0x1800c4f87  call    cs:__imp_WriteFile
0x1800c4f8d  test    eax, eax
0x1800c4f8f  jz      loc_1800C4C9D
0x1800c4f95  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace> `wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl(void)'::`2'::impl
0x1800c4f9c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(void)
0x1800c4fa1  test    al, al
  ... truncated ...
```
