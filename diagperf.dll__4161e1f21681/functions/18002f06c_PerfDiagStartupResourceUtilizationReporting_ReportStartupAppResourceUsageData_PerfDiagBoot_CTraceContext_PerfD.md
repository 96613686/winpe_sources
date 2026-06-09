# PerfDiagStartupResourceUtilizationReporting::ReportStartupAppResourceUsageData<PerfDiagBoot::CTraceContext,PerfDiagBoot::CUserAnalysisContext>(PerfDiagBoot::CTraceContext const *,PerfDiagBoot::CUserAnalysisContext const *,std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::ProcessInfo,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,XPerfAddIn::IBootAnalysisServices::ProcessInfo>>> &,XPerfCore::TimeStamp const &,XPerfCore::TimeStamp const &,ulong)

- ea: `0x18002f06c`
- end: `0x180030380`
- name: `??$ReportStartupAppResourceUsageData@VCTraceContext@PerfDiagBoot@@UCUserAnalysisContext@2@@PerfDiagStartupResourceUtilizationReporting@@YAJPEBVCTraceContext@PerfDiagBoot@@PEBUCUserAnalysisContext@2@AEAV?$map@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@UProcessInfo@IBootAnalysisServices@3@U?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@UProcessInfo@IBootAnalysisServices@3@@std@@@7@@std@@AEBVTimeStamp@XPerfCore@@3K@Z`
- size: `4884`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD **, struct _EVENT_DESCRIPTOR *, _QWORD *, DWORD)`
- caller_count: `1`
- callee_count: `40`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180030840`

## callees

- `0x180007fe4`
- `0x180013870`
- `0x1800141e0`
- `0x180015d80`
- `0x18001640c`
- `0x180016a1c`
- `0x18001769c`
- `0x1800179b0`
- `0x180018044`
- `0x180018350`
- `0x180018438`
- `0x180021328`
- `0x180022e3c`
- `0x180026800`
- `0x1800282a4`
- `0x18002b098`
- `0x18002b1b0`
- `0x18002be58`
- `0x18002c2f8`
- `0x18002dc88`
- `0x18002f06c`
- `0x180037cb0`
- `0x180037f98`
- `0x18003866c`
- `0x18003c3ec`
- `0x18003cc3c`
- `0x18003df28`
- `0x18003ecf8`
- `0x18003fb50`
- `0x180042990`
- `0x180043030`
- `0x1800440ac`
- `0x180082b74`
- `0x1800c6594`
- `0x1800c7a28`
- `0x1800c7a84`
- `0x1800c87d4`
- `0x1800cf080`
- `0x1800cf140`
- `0x1800d6010`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x18002f399`
- `ntdll!NtSetInformationFile` at `0x18002f3f9`
- `ntdll!NtSetInformationFile` at `0x18002f399`
- `ntdll!NtSetInformationFile` at `0x18002f3f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f34e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fdd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f34e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fdd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301cc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002f63e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002f738`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002f8a4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002f948`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002fdc6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002fe8f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800301c2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002f63e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002f738`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002f8a4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002f948`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002fdc6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002fe8f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800301c2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f2c8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f52f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f2c8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f52f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f3a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f402`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f3a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f402`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f770`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f7cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f770`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f7cb`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002f1fe`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002f340`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002f1fe`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002f340`
- `KERNEL32!DeleteFileW` at `0x18002f29d`
- `KERNEL32!DeleteFileW` at `0x18002f504`
- `KERNEL32!DeleteFileW` at `0x18002f29d`
- `KERNEL32!DeleteFileW` at `0x18002f504`
- `KERNEL32!CreateDirectoryW` at `0x18002f233`
- `KERNEL32!CreateDirectoryW` at `0x18002f49a`
- `KERNEL32!CreateDirectoryW` at `0x18002f233`
- `KERNEL32!CreateDirectoryW` at `0x18002f49a`

## string_xrefs

- `0x18002f1f7`: `%WINDIR%\system32\wdi\LogFiles\StartupInfo\`
- `0x18002f339`: `%WINDIR%\system32\wdi\LogFiles\StartupInfo\`
- `0x18002f25b`: `_StartupInfo?.xml`
- `0x18002f46e`: `JsonSummary\`
- `0x18002f4c2`: `_StartupInfo?.json`
- `0x18002fd50`: `	<Process Name="%ws" PID="%d" StartedInTraceSec="%.3I64f">\n		<StartTime>%ws</StartTime>\n		<CommandLine><![CDATA[%ws]]></CommandLine>\n		<DiskUsage Units="bytes">%I64lu</DiskUsage>\n		<CpuUsage Units="us">%I64d</CpuUsage>\n		<ParentPID>%d</ParentPID>\n		<ParentStartTime>%ws</ParentStartTime>\n		<ParentName>%ws</ParentName>\n	</Process>\n`
- `0x18002f6cd`: `    "intervalStartMs": %I64lu,\n    "intervalEndMs": %I64lu,\n    "version": "1.0",\n    "userSid": "%ws",\n    "processes": [\n`
- `0x1800300ef`: `        "memoryMetrics": {\n          "peakCommitSizeBytes": %I64lu,\n          "averageCommitSizeBytes": %I64lu,\n          "peakWorkingSetBytes": %I64lu,\n          "averageWorkingSetBytes": %I64lu\n        }\n      }`
- `0x18002f833`: `	<ReadAheadAnalysisTime>%u</ReadAheadAnalysisTime>\n	<RurLegacyResourceAttribution>%u</RurLegacyResourceAttribution>\n</StartupData>\n`
- `0x180030087`: `        "commandLine": "%ws",\n        "diskUsageBytes": %I64lu,\n        "cpuUsageUs": %I64d,\n        "parentPID": %d,\n        "parentStartTime": "%ws",\n        "parentName": "%ws",\n`
- `0x18002f8cd`: `\n    ],\n    "analysisMetadata": {\n      "readAheadAnalysisTimeMs": %u,\n      "rurLegacyResourceAttributionMs": %u\n    }\n  }\n}\n`

## pseudocode

```c
__int64 __fastcall PerfDiagStartupResourceUtilizationReporting::ReportStartupAppResourceUsageData<PerfDiagBoot::CTraceContext,PerfDiagBoot::CUserAnalysisContext>(
        __int64 a1,
        _QWORD *a2,
        _QWORD **a3,
        struct _EVENT_DESCRIPTOR *a4,
        _QWORD *a5,
        DWORD a6)
{
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rbx
  struct _EVENT_DESCRIPTOR *v12; // r15
  signed int v13; // eax
  unsigned __int16 *v14; // rdx
  HANDLE FileW; // rax
  void *v16; // r8
  HANDLE v17; // rsi
  void *v18; // rdx
  signed int LastError; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  unsigned __int16 *v23; // rdx
  HANDLE v24; // rax
  void *v25; // r8
  void *v26; // rdx
  unsigned __int16 *v27; // rcx
  LPCVOID *v28; // rax
  __int64 v29; // r8
  DWORD v30; // r8d
  LPCVOID *v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  LPCVOID *v34; // rdx
  const struct _EVENT_DESCRIPTOR *v35; // rdx
  DWORD TickCount; // edi
  const unsigned __int16 *v37; // r9
  DWORD v38; // r13d
  _QWORD *v39; // rax
  __int64 v40; // r14
  unsigned __int16 *v41; // rcx
  LPCVOID *v42; // rax
  __int64 v43; // r8
  DWORD v44; // r8d
  LPCVOID *v45; // rdx
  __int64 v46; // rax
  LPCVOID *v47; // rdx
  __int64 v48; // r13
  _QWORD *v49; // rax
  __int64 v50; // rdi
  __int64 i; // rax
  char FileName; // al
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // rbx
  unsigned __int64 DataForProcess; // rbx
  __int64 v57; // rdi
  __int64 v58; // rsi
  __int64 v59; // rbx
  unsigned __int16 *v60; // rcx
  LPCVOID *v61; // rax
  __int64 v62; // r8
  DWORD v63; // r8d
  LPCVOID *v64; // rdx
  signed int v65; // eax
  __int64 v66; // rax
  LPCVOID *v67; // rdx
  __int64 v68; // rdx
  const unsigned __int16 *v69; // rcx
  LPCVOID *v70; // rax
  _QWORD *v71; // r9
  _QWORD *v72; // rcx
  _QWORD *v73; // r9
  __int64 v74; // rdx
  __int64 v75; // rdx
  LPCVOID *v76; // rdx
  __int64 v77; // rdx
  signed int v78; // eax
  __int64 v79; // rdx
  __int64 v80; // rdx
  __int64 v81; // rdx
  __int64 v82; // rdx
  __int64 v83; // rdx
  __int64 v84; // rdx
  __int64 v85; // rdx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-16F8h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-16F8h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-16E8h]
  __int64 v89; // [rsp+50h] [rbp-16C8h]
  _BYTE FileInformation[4]; // [rsp+70h] [rbp-16A8h] BYREF
  int v91; // [rsp+74h] [rbp-16A4h]
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp-16A0h] BYREF
  HANDLE hFile; // [rsp+80h] [rbp-1698h]
  __int64 v94; // [rsp+88h] [rbp-1690h] BYREF
  HANDLE v95; // [rsp+90h] [rbp-1688h]
  __int64 v96; // [rsp+98h] [rbp-1680h] BYREF
  _QWORD **v97; // [rsp+A0h] [rbp-1678h]
  unsigned __int16 *p_Id; // [rsp+A8h] [rbp-1670h] BYREF
  __int64 v99; // [rsp+B0h] [rbp-1668h] BYREF
  _QWORD *v100; // [rsp+B8h] [rbp-1660h]
  __int64 v101; // [rsp+C0h] [rbp-1658h] BYREF
  __int64 v102; // [rsp+C8h] [rbp-1650h] BYREF
  struct _EVENT_DESCRIPTOR *v103; // [rsp+D0h] [rbp-1648h]
  _QWORD v104[3]; // [rsp+D8h] [rbp-1640h] BYREF
  __int128 v105; // [rsp+F0h] [rbp-1628h] BYREF
  __int64 v106; // [rsp+100h] [rbp-1618h]
  int v107; // [rsp+108h] [rbp-1610h]
  __int64 v108; // [rsp+110h] [rbp-1608h]
  unsigned __int64 v109; // [rsp+118h] [rbp-1600h]
  _QWORD v110[2]; // [rsp+120h] [rbp-15F8h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+130h] [rbp-15E8h] BYREF
  int v112[4]; // [rsp+140h] [rbp-15D8h] BYREF
  __int64 v113; // [rsp+150h] [rbp-15C8h]
  _QWORD *v114; // [rsp+158h] [rbp-15C0h]
  ATL::CAtlException *v115; // [rsp+160h] [rbp-15B8h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+168h] [rbp-15B0h] BYREF
  unsigned __int64 v117; // [rsp+178h] [rbp-15A0h]
  unsigned __int64 v118; // [rsp+180h] [rbp-1598h]
  LPCVOID v119[2]; // [rsp+188h] [rbp-1590h] BYREF
  __int64 v120; // [rsp+198h] [rbp-1580h]
  unsigned __int64 v121; // [rsp+1A0h] [rbp-1578h]
  _QWORD v122[3]; // [rsp+1A8h] [rbp-1570h] BYREF
  unsigned __int64 v123; // [rsp+1C0h] [rbp-1558h]
  _QWORD v124[3]; // [rsp+1C8h] [rbp-1550h] BYREF
  unsigned __int64 v125; // [rsp+1E0h] [rbp-1538h]
  _QWORD v126[3]; // [rsp+1E8h] [rbp-1530h] BYREF
  unsigned __int64 v127; // [rsp+200h] [rbp-1518h]
  __int64 v128; // [rsp+208h] [rbp-1510h] BYREF
  __int64 v129; // [rsp+210h] [rbp-1508h]
  __int64 v130; // [rsp+218h] [rbp-1500h]
  __int64 v131; // [rsp+220h] [rbp-14F8h]
  _OWORD v132[3]; // [rsp+230h] [rbp-14E8h] BYREF
  __int16 v133; // [rsp+260h] [rbp-14B8h]
  __int64 v134; // [rsp+270h] [rbp-14A8h]
  __int64 v135; // [rsp+278h] [rbp-14A0h]
  __int16 v136; // [rsp+280h] [rbp-1498h]
  __int64 v137; // [rsp+290h] [rbp-1488h]
  __int64 v138; // [rsp+298h] [rbp-1480h]
  char v139; // [rsp+2A0h] [rbp-1478h]
  WCHAR PathName[264]; // [rsp+2B0h] [rbp-1468h] BYREF
  WCHAR Dst[264]; // [rsp+4C0h] [rbp-1258h] BYREF
  unsigned __int16 v142[2048]; // [rsp+6D0h] [rbp-1048h] BYREF

  v103 = a4;
  v97 = a3;
  v114 = a2;
  v113 = a1;
  v100 = a5;
  v118 = 7;
  v117 = 0;
  LOWORD(lpBuffer[0]) = 0;
  v121 = 7;
  v120 = 0;
  LOWORD(v119[0]) = 0;
  NumberOfBytesWritten = 0;
  std::_Tree_comp<0,std::_Tset_traits<XPerfCore::PathNode const *,std::less<XPerfCore::PathNode const *>,std::allocator<XPerfCore::PathNode const *>,0>>::_Tree_comp<0,std::_Tset_traits<XPerfCore::PathNode const *,std::less<XPerfCore::PathNode const *>,std::allocator<XPerfCore::PathNode const *>,0>>(v110);
  std::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>(v112);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v102 = 0;
    v9 = std::wstring::wstring(&v128, 0x10000);
    std::wstring::operator=(lpBuffer, v9);
    LOBYTE(v10) = 1;
    std::wstring::_Tidy(&v128, v10, 0);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180030309);
      PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData((PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v102);
      std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(v112);
      std::_Tree<std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>::~_Tree<std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>(v110);
      LOBYTE(v84) = 1;
      std::wstring::_Tidy(v119, v84, 0);
      LOBYTE(v85) = 1;
      std::wstring::_Tidy(lpBuffer, v85, 0);
      return 2147942414LL;
    }
  }
  memset(v132, 0, sizeof(v132));
  v11 = -1;
  v95 = (HANDLE)-1LL;
  v135 = 7;
  v134 = 0;
  v133 = 0;
  v138 = 7;
  v137 = 0;
  v136 = 0;
  v139 = 0;
  if ( !*(_DWORD *)(a2[119] - 16LL) )
  {
    LODWORD(v12) = -2058022908;
    goto LABEL_21;
  }
  if ( !ExpandEnvironmentStringsW(L"%WINDIR%\\system32\\wdi\\LogFiles\\StartupInfo\\", Dst, 0x104u) )
    goto LABEL_5;
  CreateDirectoryW(Dst, 0);
  LODWORD(v12) = ((int (__stdcall *)(unsigned __int16 *, unsigned __int64, const unsigned __int16 *))StringCchCatW)(
                   Dst,
                   0x104u,
                   (const unsigned __int16 *)a2[119]);
  if ( (int)v12 < 0 )
    goto LABEL_21;
  LODWORD(v12) = ((int (__stdcall *)(unsigned __int16 *, unsigned __int64, const unsigned __int16 *))StringCchCatW)(
                   Dst,
                   0x104u,
                   L"_StartupInfo?.xml");
  if ( (int)v12 < 0 )
    goto LABEL_21;
  LODWORD(v12) = PerfDiagStartupResourceUtilizationReporting::FindSuccessorFileName(Dst, v14);
  if ( (int)v12 < 0 )
    goto LABEL_21;
  DeleteFileW(Dst);
  FileW = CreateFileW(Dst, 0x40050000u, 0, 0, 2u, 0, 0);
  v17 = FileW;
  hFile = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_5:
    v13 = GetLastError();
    LODWORD(v12) = v13;
    if ( v13 > 0 )
      LODWORD(v12) = (unsigned __int16)v13 | 0x80070000;
    goto LABEL_21;
  }
  v18 = (void *)a2[118];
  if ( !v18 )
  {
LABEL_33:
    LODWORD(v12) = -2058022908;
    goto LABEL_19;
  }
  LODWORD(v12) = PerfDiagStartupResourceUtilizationReporting::SetAccessPermissions(FileW, v18, v16);
  if ( (int)v12 < 0 )
    goto LABEL_18;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl) )
  {
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      std::wstring::reserve(v119, 0x10000);
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v91 = -2147024882;
        LODWORD(v12) = -2147024882;
        __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_1800302F7);
LABEL_143:
        v17 = hFile;
        goto LABEL_19;
      }
    }
    if ( !ExpandEnvironmentStringsW(L"%WINDIR%\\system32\\wdi\\LogFiles\\StartupInfo\\", PathName, 0x104u) )
      goto LABEL_16;
    LODWORD(v12) = ((int (__stdcall *)(unsigned __int16 *, unsigned __int64, const unsigned __int16 *))StringCchCatW)(
                     PathName,
                     0x104u,
                     L"JsonSummary\\");
    if ( (int)v12 < 0 )
      goto LABEL_18;
    CreateDirectoryW(PathName, 0);
    LODWORD(v12) = ((int (__stdcall *)(unsigned __int16 *, unsigned __int64, const unsigned __int16 *))StringCchCatW)(
                     PathName,
                     0x104u,
                     (const unsigned __int16 *)a2[119]);
    if ( (int)v12 < 0 )
      goto LABEL_18;
    LODWORD(v12) = ((int (__stdcall *)(unsigned __int16 *, unsigned __int64, const unsigned __int16 *))StringCchCatW)(
                     PathName,
                     0x104u,
                     L"_StartupInfo?.json");
    if ( (int)v12 < 0 )
      goto LABEL_18;
    LODWORD(v12) = PerfDiagStartupResourceUtilizationReporting::FindSuccessorFileName(PathName, v23);
    if ( (int)v12 < 0 )
      goto LABEL_18;
    DeleteFileW(PathName);
    v24 = CreateFileW(PathName, 0x40050000u, 0, 0, 2u, 0, 0);
    v11 = (__int64)v24;
    v95 = v24;
    if ( v24 == (HANDLE)-1LL )
      goto LABEL_16;
    v26 = (void *)a2[118];
    if ( !v26 )
      goto LABEL_33;
    LODWORD(v12) = PerfDiagStartupResourceUtilizationReporting::SetAccessPermissions(v24, v26, v25);
    if ( (int)v12 < 0 )
      goto LABEL_19;
  }
  v12 = v103;
  v27 = (unsigned __int16 *)lpBuffer;
  if ( v118 >= 8 )
    v27 = (unsigned __int16 *)lpBuffer[0];
  StringCchPrintfW(v27, v117, &qword_1800E8EC0, *(_QWORD *)&v103->Id / 1000000LL, *v100 / 1000000LL);
  v28 = lpBuffer;
  if ( v118 >= 8 )
    v28 = (LPCVOID *)lpBuffer[0];
  v29 = -1;
  do
    ++v29;
  while ( *((_WORD *)v28 + v29) );
  v30 = 2 * v29;
  v31 = lpBuffer;
  if ( v118 >= 8 )
    v31 = (LPCVOID *)lpBuffer[0];
  if ( !WriteFile(v17, v31, v30, &NumberOfBytesWritten, 0) )
    goto LABEL_16;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl) )
  {
    v32 = std::char_traits<unsigned short>::length(qword_1800E8F98);
    std::wstring::assign(v119, v33, v32);
    LODWORD(v12) = StringCchPrintfW(
                     v142,
                     0x800u,
                     L"    \"intervalStartMs\": %I64lu,\r\n"
                      "    \"intervalEndMs\": %I64lu,\r\n"
                      "    \"version\": \"1.0\",\r\n"
                      "    \"userSid\": \"%ws\",\r\n"
                      "    \"processes\": [\r\n",
                     *(_QWORD *)&v12->Id / 1000000LL,
                     *v100 / 1000000LL,
                     a2[119]);
    if ( (int)v12 < 0 )
      goto LABEL_18;
    std::wstring::append(v119, v142);
    v34 = v119;
    if ( v121 >= 8 )
      v34 = (LPCVOID *)v119[0];
    if ( !WriteFile((HANDLE)v11, v34, 2 * v120, &NumberOfBytesWritten, 0) )
      goto LABEL_16;
  }
  LODWORD(v12) = PerfDiagStartupResourceUtilizationReporting::GetStartupProcesses<PerfDiagBoot::CTraceContext>(
                   a1,
                   a3,
                   v110);
  if ( (int)v12 >= 0 )
  {
    if ( __eh34_try(-1, 4) )
    {
      __eh34_scope_strut(4);
      PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Boot_RurReadAhead_Start, v35);
      TickCount = GetTickCount();
      v12 = (struct _EVENT_DESCRIPTOR *)(unsigned int)PerfDiagStartupResourceUtilizationReporting::GetReadAheadAmounts<PerfDiagBoot::CTraceContext,PerfDiagBoot::CUserAnalysisContext,std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::ProcessInfo>>(
                                                        a1,
                                                        (int)a2,
                                                        (int)v97,
                                                        (int)v103,
                                                        (__int64)v100,
                                                        (int)v112);
      PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Boot_RurReadAhead_Stop, v12, 0, v37);
    }
    if ( __eh34_catch(4) )
    {
      if ( __eh34_catch_type(4, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v91 = -2147024882;
        LODWORD(v12) = -2147024882;
        __eh34_try_continuation(4, &std::bad_alloc `RTTI Type Descriptor', &loc_1800302F7);
        goto LABEL_143;
      }
    }
    if ( (int)v12 >= 0 )
    {
      v38 = GetTickCount() - TickCount;
      v91 = v38;
      LODWORD(v12) = PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::QueryBootPrefetcher((PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v102);
      if ( (int)v12 < 0 )
        goto LABEL_18;
      v39 = v97;
      v40 = **v97;
      while ( 1 )
      {
        if ( v40 == *v39 )
        {
          v41 = (unsigned __int16 *)lpBuffer;
          if ( v118 >= 8 )
            v41 = (unsigned __int16 *)lpBuffer[0];
          dwCreationDispositiona[0] = a6;
          LODWORD(v12) = StringCchPrintfW(
                           v41,
                           v117,
                           L"\t<ReadAheadAnalysisTime>%u</ReadAheadAnalysisTime>\r\n"
                            "\t<RurLegacyResourceAttribution>%u</RurLegacyResourceAttribution>\r\n"
                            "</StartupData>\r\n",
                           v38,
                           *(_QWORD *)dwCreationDispositiona);
          if ( (int)v12 >= 0 )
          {
            v42 = lpBuffer;
            if ( v118 >= 8 )
              v42 = (LPCVOID *)lpBuffer[0];
            v43 = -1;
            do
              ++v43;
            while ( *((_WORD *)v42 + v43) );
            v44 = 2 * v43;
            v45 = lpBuffer;
            if ( v118 >= 8 )
              v45 = (LPCVOID *)lpBuffer[0];
            if ( WriteFile(v17, v45, v44, &NumberOfBytesWritten, 0) )
            {
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl) )
                goto LABEL_70;
              dwCreationDisposition[0] = a6;
              LODWORD(v12) = StringCchPrintfW(
                               v142,
                               0x800u,
                               L"\r\n"
                                "    ],\r\n"
                                "    \"analysisMetadata\": {\r\n"
                                "      \"readAheadAnalysisTimeMs\": %u,\r\n"
                                "      \"rurLegacyResourceAttributionMs\": %u\r\n"
                                "    }\r\n"
                                "  }\r\n"
                                "}\r\n",
                               v38,
                               *(_QWORD *)dwCreationDisposition);
              if ( (int)v12 < 0 )
                goto LABEL_18;
              v46 = std::char_traits<unsigned short>::length(v142);
              std::wstring::assign(v119, v142, v46);
              v47 = v119;
              if ( v121 >= 8 )
                v47 = (LPCVOID *)v119[0];
              if ( WriteFile((HANDLE)v11, v47, 2 * v120, &NumberOfBytesWritten, 0) )
              {
LABEL_70:
                LODWORD(v12) = 0;
                goto LABEL_20;
              }
            }
LABEL_16:
            LastError = GetLastError();
            LODWORD(v12) = LastError;
            if ( LastError > 0 )
              LODWORD(v12) = (unsigned __int16)LastError | 0x80070000;
          }
          goto LABEL_18;
        }
        v48 = *(_QWORD *)(v40 + 40);
        v99 = v48;
        v49 = (_QWORD *)std::_Tree<std::_Tset_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<XPerfAddIn::IProcessInfoSource::ProcessData const *>,0>>::find(
                          v110,
                          &IoStatusBlock,
                          &v99);
        if ( *v49 != v110[0] )
        {
          v50 = v113;
          v108 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v113 + 104) + 24LL))(
                   *(_QWORD *)(v113 + 104),
                   v48);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v94);
          if ( !(unsigned int)PerfDiagStartupResourceUtilizationReporting::GetProcessStartTime<PerfDiagBoot::CTraceContext>(
                                v50,
                                v48,
                                &v94) )
            goto LABEL_73;
          p_Id = 0;
          v104[0] = *(_QWORD *)(v50 + 24);
          v104[1] = *(_QWORD *)(v50 + 8);
          v104[2] = *v114;
          v105 = 0;
          v106 = 0;
          v107 = 0;
          if ( (int)PerfDiagShared::CProcessImageNameLocator::GetProcessImageName(
                      (PerfDiagShared::CProcessImageNameLocator *)v104,
                      (const unsigned __int16 **)&p_Id,
                      (const struct XPerfAddIn::IProcessInfoSource::ProcessData *)v48) < 0 )
            goto LABEL_79;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v96);
          if ( __eh34_try(-1, 6) )
          {
            __eh34_scope_strut(6);
            FileName = PerfDiagShared::CLocalNtImagePathDecoder::GetFileName(v132, p_Id, &v96);
          }
          if ( __eh34_catch(6) )
          {
            if ( __eh34_catch_type(6, &ATL::CAtlException `RTTI Type Descriptor', &v115) )
            {
              v91 = *(_DWORD *)v115;
              __eh34_try_continuation(6, &ATL::CAtlException `RTTI Type Descriptor', &loc_180030292);
              ATL::CStringData::Release((ATL::CStringData *)(v96 - 24));
              ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v105);
              ATL::CStringData::Release((ATL::CStringData *)(v94 - 24));
              LODWORD(v12) = v91;
              goto LABEL_137;
            }
          }
          if ( !FileName )
          {
            ATL::CStringData::Release((ATL::CStringData *)(v96 - 24));
            ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v105);
            ATL::CStringData::Release((ATL::CStringData *)(v94 - 24));
            goto LABEL_74;
          }
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v101);
          v53 = v48 + 8;
          if ( *(_QWORD *)v48 != XPerfCore::TimeStamp::Min )
            v53 = v48;
          v54 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(v50 + 24) + 32LL))(
                  *(_QWORD *)(v50 + 24),
                  v53,
                  *(unsigned int *)(v48 + 36),
                  1);
          v55 = v54;
          if ( v54 )
          {
            if ( !(unsigned int)PerfDiagStartupResourceUtilizationReporting::GetProcessStartTime<PerfDiagBoot::CTraceContext>(
                                  v50,
                                  v54,
                                  &v101) )
            {
              ATL::CStringData::Release((ATL::CStringData *)(v101 - 24));
              ATL::CStringData::Release((ATL::CStringData *)(v96 - 24));
LABEL_79:
              ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v105);
LABEL_73:
              ATL::CStringData::Release((ATL::CStringData *)(v94 - 24));
              goto LABEL_74;
            }
            v12 = *(struct _EVENT_DESCRIPTOR **)(v55 + 24);
            p_Id = &v12->Id;
          }
          else
          {
            v12 = (struct _EVENT_DESCRIPTOR *)L"n/a";
            p_Id = L"n/a";
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v101, L"n/a");
          }
          DataForProcess = PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::GetDataForProcess(
                             (PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v102,
                             (const struct XPerfAddIn::IProcessInfoSource::ProcessData *)v48);
          v109 = *(_QWORD *)std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64>::operator[]((int)v112)
               + *(unsigned int *)(v40 + 64)
               + DataForProcess;
          v99 = *(_QWORD *)(v40 + 48) / 1000LL;
          v128 = 0;
          v129 = 0;
          v130 = 0;
          v131 = 0;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl)
            && (int)PerfDiagStartupResourceUtilizationReporting::CollectProcessMemoryMetrics<PerfDiagBoot::CTraceContext>(
                      v50,
                      v48,
                      (int)v103,
                      (int)v100,
                      (__int64)&v128) < 0 )
          {
            v128 = 0;
            v129 = 0;
            v130 = 0;
            v131 = 0;
          }
          v57 = v101;
          v58 = v94;
          v59 = v96;
          v60 = (unsigned __int16 *)lpBuffer;
          if ( v118 >= 8 )
            v60 = (unsigned __int16 *)lpBuffer[0];
          LODWORD(v89) = *(_DWORD *)(v48 + 36);
          dwCreationDispositiona[0] = *(_DWORD *)(v48 + 32);
          LODWORD(v12) = StringCchPrintfW(
                           v60,
                           v117,
                           L"\t<Process Name=\"%ws\" PID=\"%d\" StartedInTraceSec=\"%.3I64f\">\r\n"
                            "\t\t<StartTime>%ws</StartTime>\r\n"
                            "\t\t<CommandLine><![CDATA[%ws]]></CommandLine>\r\n"
                            "\t\t<DiskUsage Units=\"bytes\">%I64lu</DiskUsage>\r\n"
                            "\t\t<CpuUsage Units=\"us\">%I64d</CpuUsage>\r\n"
                            "\t\t<ParentPID>%d</ParentPID>\r\n"
                            "\t\t<ParentStartTime>%ws</ParentStartTime>\r\n"
                            "\t\t<ParentName>%ws</ParentName>\r\n"
                            "\t</Process>\r\n",
                           v96,
                           *(_QWORD *)dwCreationDispositiona,
                           (double)((int)*(_QWORD *)v48 / 1000) / 1000000.0,
                           v94,
                           v108,
                           v109,
                           v99,
                           v89,
                           v101,
                           v12);
          if ( (int)v12 < 0 )
            goto LABEL_128;
          v61 = lpBuffer;
          if ( v118 >= 8 )
            v61 = (LPCVOID *)lpBuffer[0];
          v62 = -1;
          do
            ++v62;
          while ( *((_WORD *)v61 + v62) );
          v63 = 2 * v62;
          v64 = lpBuffer;
          if ( v118 >= 8 )
            v64 = (LPCVOID *)lpBuffer[0];
          if ( !WriteFile(hFile, v64, v63, &NumberOfBytesWritten, 0) )
          {
LABEL_103:
            v65 = GetLastError();
            LODWORD(v12) = v65;
            if ( v65 > 0 )
              LODWORD(v12) = (unsigned __int16)v65 | 0x80070000;
            goto LABEL_105;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl) )
          {
            if ( !`PerfDiagStartupResourceUtilizationReporting::ReportStartupAppResourceUsageData<PerfDiagBoot::CTraceContext,PerfDiagBoot::CUserAnalysisContext>'[::C]::firstJsonProcess )
            {
              v66 = std::char_traits<unsigned short>::length(L",\r\n");
              std::wstring::assign(v119, L",\r\n", v66);
              v67 = v119;
              if ( v121 >= 8 )
                v67 = (LPCVOID *)v119[0];
              if ( !WriteFile(v95, v67, 2 * v120, &NumberOfBytesWritten, 0) )
                goto LABEL_103;
            }
            `PerfDiagStartupResourceUtilizationReporting::ReportStartupAppResourceUsageData<PerfDiagBoot::CTraceContext,PerfDiagBoot::CUserAnalysisContext>'[::C]::firstJsonProcess = 0;
            v127 = 7;
            v126[2] = 0;
            LOWORD(v126[0]) = 0;
            v125 = 7;
            v124[2] = 0;
            LOWORD(v124[0]) = 0;
            v123 = 7;
            v122[2] = 0;
            LOWORD(v122[0]) = 0;
            LODWORD(v12) = PerfDiagStartupResourceUtilizationReporting::EscapeJsonString(v59, v126);
            if ( (int)v12 < 0 )
              goto LABEL_127;
            v69 = &qword_1800E1280;
            if ( v108 )
              v69 = (const unsigned __int16 *)v108;
            LODWORD(v12) = PerfDiagStartupResourceUtilizationReporting::EscapeJsonString(v69, v124);
            if ( (int)v12 < 0 )
              goto LABEL_127;
            LODWORD(v12) = PerfDiagStartupResourceUtilizationReporting::EscapeJsonString(p_Id, v122);
            if ( (int)v12 < 0 )
              goto LABEL_127;
            v70 = v119;
            if ( v121 >= 8 )
              v70 = (LPCVOID *)v119[0];
            v120 = 0;
            *(_WORD *)v70 = 0;
            std::wstring::reserve(v119, 3072);
            v71 = v126;
            if ( v127 >= 8 )
              v71 = (_QWORD *)v126[0];
            dwCreationDispositiona[0] = *(_DWORD *)(v48 + 32);
            LODWORD(v12) = StringCchPrintfW(
                             v142,
                             0x800u,
                             L"      {\r\n"
                              "        \"name\": \"%ws\",\r\n"
                              "        \"pid\": %d,\r\n"
                              "        \"startedInTraceSec\": %.3f,\r\n"
                              "        \"startTime\": \"%ws\",\r\n",
                             v71,
                             *(_QWORD *)dwCreationDispositiona,
                             (double)(int)(*(_QWORD *)v48 / 1000LL) / 1000000.0,
                             v58);
            if ( (int)v12 < 0 )
              goto LABEL_127;
            std::wstring::append(v119, v142);
            v72 = v122;
            if ( v123 >= 8 )
              v72 = (_QWORD *)v122[0];
            v73 = v124;
            if ( v125 >= 8 )
              v73 = (_QWORD *)v124[0];
            LODWORD(hTemplateFile) = *(_DWORD *)(v48 + 36);
            LODWORD(v12) = StringCchPrintfW(
                             v142,
                             0x800u,
                             L"        \"commandLine\": \"%ws\",\r\n"
                              "        \"diskUsageBytes\": %I64lu,\r\n"
                              "        \"cpuUsageUs\": %I64d,\r\n"
                              "        \"parentPID\": %d,\r\n"
                              "        \"parentStartTime\": \"%ws\",\r\n"
                              "        \"parentName\": \"%ws\",\r\n",
                             v73,
                             v109,
                             v99,
                             hTemplateFile,
                             v57,
                             v72);
            if ( (int)v12 < 0
              || (std::wstring::append(v119, v142),
                  LODWORD(v12) = StringCchPrintfW(
                                   v142,
                                   0x800u,
                                   L"        \"memoryMetrics\": {\r\n"
                                    "          \"peakCommitSizeBytes\": %I64lu,\r\n"
                                    "          \"averageCommitSizeBytes\": %I64lu,\r\n"
                                    "          \"peakWorkingSetBytes\": %I64lu,\r\n"
                                    "          \"averageWorkingSetBytes\": %I64lu\r\n"
                                    "        }\r\n"
                                    "      }",
                                   v128,
                                   v129,
                                   v130,
                                   v131),
                  (int)v12 < 0) )
            {
LABEL_127:
              LOBYTE(v68) = 1;
              std::wstring::_Tidy(v122, v68, 0);
              LOBYTE(v74) = 1;
              std::wstring::_Tidy(v124, v74, 0);
              LOBYTE(v75) = 1;
              std::wstring::_Tidy(v126, v75, 0);
LABEL_128:
              ATL::CStringData::Release((ATL::CStringData *)(v57 - 24));
              ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
              ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v105);
              ATL::CStringData::Release((ATL::CStringData *)(v58 - 24));
              goto LABEL_143;
            }
            std::wstring::append(v119, v142);
            v76 = v119;
            if ( v121 >= 8 )
              v76 = (LPCVOID *)v119[0];
            if ( !WriteFile(v95, v76, 2 * v120, &NumberOfBytesWritten, 0) )
            {
              v78 = GetLastError();
              LODWORD(v12) = v78;
              if ( v78 > 0 )
                LODWORD(v12) = (unsigned __int16)v78 | 0x80070000;
              LOBYTE(v79) = 1;
              std::wstring::_Tidy(v122, v79, 0);
              LOBYTE(v80) = 1;
              std::wstring::_Tidy(v124, v80, 0);
              LOBYTE(v81) = 1;
              std::wstring::_Tidy(v126, v81, 0);
LABEL_105:
              ATL::CStringData::Release((ATL::CStringData *)(v57 - 24));
              ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
              ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v105);
              ATL::CStringData::Release((ATL::CStringData *)(v58 - 24));
LABEL_137:
              v17 = hFile;
              goto LABEL_18;
            }
            LOBYTE(v77) = 1;
            std::wstring::_Tidy(v122, v77, 0);
            LOBYTE(v82) = 1;
            std::wstring::_Tidy(v124, v82, 0);
            LOBYTE(v83) = 1;
            std::wstring::_Tidy(v126, v83, 0);
          }
          ATL::CStringData::Release((ATL::CStringData *)(v57 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
          ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v105);
          ATL::CStringData::Release((ATL::CStringData *)(v58 - 24));
          v17 = hFile;
        }
LABEL_74:
        v11 = (__int64)v95;
        v38 = v91;
        v39 = v97;
        if ( !*(_BYTE *)(v40 + 25) )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v40 + 16) + 25LL) )
          {
            for ( i = *(_QWORD *)(v40 + 8); !*(_BYTE *)(i + 25) && v40 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
              v40 = i;
          }
          else
          {
            i = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::set<XPerfAddIn::IProcessInfoSource::VARange *>>>>::_Min();
          }
          v40 = i;
          v39 = v97;
        }
      }
    }
LABEL_19:
    IoStatusBlock = 0;
    FileInformation[0] = 1;
    NtSetInformationFile(v17, &IoStatusBlock, FileInformation, 1u, FileDispositionInformation);
    goto LABEL_20;
  }
LABEL_18:
  if ( (int)v12 < 0 )
    goto LABEL_19;
LABEL_20:
  CloseHandle(v17);
  v11 = (__int64)v95;
LABEL_21:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl)
    && v11 != -1 )
  {
    if ( (int)v12 < 0 )
    {
      IoStatusBlock = 0;
      FileInformation[0] = 1;
      NtSetInformationFile((HANDLE)v11, &IoStatusBlock, FileInformation, 1u, FileDispositionInformation);
    }
    CloseHandle((HANDLE)v11);
  }
  PerfDiagShared::CNtImagePathDecoderBase::~CNtImagePathDecoderBase((PerfDiagShared::CNtImagePathDecoderBase *)v132);
  PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData((PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v102);
  std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(v112);
  std::_Tree<std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>::~_Tree<std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>(v110);
  LOBYTE(v20) = 1;
  std::wstring::_Tidy(v119, v20, 0);
  LOBYTE(v21) = 1;
  std::wstring::_Tidy(lpBuffer, v21, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002f06c  push    rbx
0x18002f06e  push    rsi
0x18002f06f  push    rdi
0x18002f070  push    r12
0x18002f072  push    r13
0x18002f074  push    r14
0x18002f076  push    r15
0x18002f078  mov     eax, 16E0h
0x18002f07d  call    _alloca_probe
0x18002f082  sub     rsp, rax
0x18002f085  mov     rax, cs:__security_cookie
0x18002f08c  xor     rax, rsp
0x18002f08f  mov     [rsp+1718h+var_48], rax
0x18002f097  mov     [rsp+1718h+var_1648], r9
0x18002f09f  mov     rdi, r8
0x18002f0a2  mov     [rsp+1718h+var_1678], r8
0x18002f0aa  mov     r14, rdx
0x18002f0ad  mov     [rsp+1718h+var_15C0], rdx
0x18002f0b5  mov     r13, rcx
0x18002f0b8  mov     [rsp+1718h+var_15C8], rcx
0x18002f0c0  mov     rax, [rsp+1718h+arg_20]
0x18002f0c8  mov     [rsp+1718h+var_1660], rax
0x18002f0d0  mov     esi, 7
0x18002f0d5  mov     [rsp+1718h+var_1598], rsi
0x18002f0dd  xor     r12d, r12d
0x18002f0e0  mov     [rsp+1718h+var_15A0], r12
0x18002f0e8  mov     word ptr [rsp+1718h+lpBuffer], r12w
0x18002f0f1  mov     [rsp+1718h+var_1578], rsi
0x18002f0f9  mov     [rsp+1718h+var_1580], r12
0x18002f101  mov     word ptr [rsp+1718h+var_1590], r12w
0x18002f10a  mov     [rsp+1718h+NumberOfBytesWritten], r12d
0x18002f10f  lea     rcx, [rsp+1718h+var_15F8]
0x18002f117  call    ??0?$_Tree_comp@$0A@V?$_Tset_traits@PEBUPathNode@XPerfCore@@U?$less@PEBUPathNode@XPerfCore@@@std@@V?$allocator@PEBUPathNode@XPerfCore@@@4@$0A@@std@@@std@@QEAA@AEBU?$less@PEBUPathNode@XPerfCore@@@1@AEBV?$allocator@PEBUPathNode@XPerfCore@@@1@@Z; std::_Tree_comp<0,std::_Tset_traits<XPerfCore::PathNode const *,std::less<XPerfCore::PathNode const *>,std::allocator<XPerfCore::PathNode const *>,0>>::_Tree_comp<0,std::_Tset_traits<XPerfCore::PathNode const *,std::less<XPerfCore::PathNode const *>,std::allocator<XPerfCore::PathNode const *>,0>>(std::less<XPerfCore::PathNode const *> const &,std::allocator<XPerfCore::PathNode const *> const &)
0x18002f11c  nop
0x18002f11d  lea     rcx, [rsp+1718h+var_15D8]
0x18002f125  call    ??0?$map@PEBUThreadData@IProcessInfoSource@XPerfAddIn@@VTimeStampDelta@XPerfCore@@U?$less@PEBUThreadData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUThreadData@IProcessInfoSource@XPerfAddIn@@VTimeStampDelta@XPerfCore@@@std@@@7@@std@@QEAA@XZ; std::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>(void)
0x18002f12a  nop
0x18002f12b  mov     [rsp+1718h+var_1650], r12
0x18002f133  mov     edx, 10000h
0x18002f138  lea     rcx, [rsp+1718h+var_1510]
0x18002f140  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18002f145  mov     rdx, rax
0x18002f148  lea     rcx, [rsp+1718h+lpBuffer]
0x18002f150  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002f155  xor     r8d, r8d
0x18002f158  mov     dl, 1
0x18002f15a  lea     rcx, [rsp+1718h+var_1510]
0x18002f162  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002f167  nop
0x18002f168  xorps   xmm0, xmm0
0x18002f16b  movdqa  [rsp+1718h+var_14E8], xmm0
0x18002f174  xorps   xmm1, xmm1
0x18002f177  movdqa  [rsp+1718h+var_14D8], xmm1
0x18002f180  movdqa  [rsp+1718h+var_14C8], xmm0
0x18002f189  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002f18d  mov     [rsp+1718h+var_1688], rbx
0x18002f195  mov     [rsp+1718h+var_14A0], rsi
0x18002f19d  mov     [rsp+1718h+var_14A8], r12
0x18002f1a5  mov     [rsp+1718h+var_14B8], r12w
0x18002f1ae  mov     [rsp+1718h+var_1480], rsi
0x18002f1b6  mov     [rsp+1718h+var_1488], r12
0x18002f1be  mov     [rsp+1718h+var_1498], r12w
0x18002f1c7  mov     [rsp+1718h+var_1478], r12b
0x18002f1cf  mov     rax, [r14+3B8h]
0x18002f1d6  cmp     [rax-10h], r12d
0x18002f1da  jnz     short loc_18002F1E7
0x18002f1dc  mov     r15d, 85551004h
0x18002f1e2  jmp     loc_18002F3B0
0x18002f1e7  mov     esi, 104h
0x18002f1ec  mov     r8d, esi; nSize
0x18002f1ef  lea     rdx, [rsp+1718h+Dst]; lpDst
0x18002f1f7  lea     rcx, Src; "%WINDIR%\\system32\\wdi\\LogFiles\\Star"...
0x18002f1fe  call    cs:__imp_ExpandEnvironmentStringsW
0x18002f204  test    eax, eax
0x18002f206  jnz     short loc_18002F229
0x18002f208  call    cs:__imp_GetLastError
0x18002f20e  mov     r15d, eax
0x18002f211  test    eax, eax
0x18002f213  jle     loc_18002F3B0
0x18002f219  movzx   r15d, ax
0x18002f21d  or      r15d, 80070000h
0x18002f224  jmp     loc_18002F3B0
0x18002f229  xor     edx, edx; lpSecurityAttributes
0x18002f22b  lea     rcx, [rsp+1718h+Dst]; lpPathName
0x18002f233  call    cs:__imp_CreateDirectoryW
0x18002f239  mov     r8, [r14+3B8h]; unsigned __int16 *
0x18002f240  mov     rdx, rsi; unsigned __int64
0x18002f243  lea     rcx, [rsp+1718h+Dst]; unsigned __int16 *
0x18002f24b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002f250  mov     r15d, eax
0x18002f253  test    eax, eax
0x18002f255  js      loc_18002F3B0
0x18002f25b  lea     r8, aStartupinfoXml; "_StartupInfo?.xml"
0x18002f262  mov     rdx, rsi; unsigned __int64
0x18002f265  lea     rcx, [rsp+1718h+Dst]; unsigned __int16 *
0x18002f26d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002f272  mov     r15d, eax
0x18002f275  test    eax, eax
0x18002f277  js      loc_18002F3B0
0x18002f27d  lea     rcx, [rsp+1718h+Dst]; lpFileName
0x18002f285  call    ?FindSuccessorFileName@PerfDiagStartupResourceUtilizationReporting@@YAJPEAG@Z; PerfDiagStartupResourceUtilizationReporting::FindSuccessorFileName(ushort *)
0x18002f28a  mov     r15d, eax
0x18002f28d  test    eax, eax
0x18002f28f  js      loc_18002F3B0
0x18002f295  lea     rcx, [rsp+1718h+Dst]; lpFileName
0x18002f29d  call    cs:__imp_DeleteFileW
0x18002f2a3  mov     [rsp+1718h+hTemplateFile], r12; hTemplateFile
0x18002f2a8  mov     [rsp+1718h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18002f2ad  mov     [rsp+1718h+dwCreationDisposition], 2; dwCreationDisposition
0x18002f2b5  xor     r9d, r9d; lpSecurityAttributes
0x18002f2b8  xor     r8d, r8d; dwShareMode
0x18002f2bb  mov     edx, 40050000h; dwDesiredAccess
0x18002f2c0  lea     rcx, [rsp+1718h+Dst]; lpFileName
0x18002f2c8  call    cs:__imp_CreateFileW
0x18002f2ce  mov     rsi, rax
0x18002f2d1  mov     [rsp+1718h+hFile], rax
0x18002f2d9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002f2dd  jz      loc_18002F208
0x18002f2e3  mov     rdx, [r14+3B0h]; pSid
0x18002f2ea  test    rdx, rdx
0x18002f2ed  jz      loc_18002F556
0x18002f2f3  mov     rcx, rax; handle
0x18002f2f6  call    ?SetAccessPermissions@PerfDiagStartupResourceUtilizationReporting@@YAJQEAX0@Z; PerfDiagStartupResourceUtilizationReporting::SetAccessPermissions(void * const,void * const)
0x18002f2fb  mov     r15d, eax
0x18002f2fe  test    eax, eax
0x18002f300  js      short loc_18002F366
0x18002f302  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace> `wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl(void)'::`2'::impl
0x18002f309  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(void)
0x18002f30e  test    al, al
0x18002f310  jz      loc_18002F574
0x18002f316  mov     edx, 10000h
0x18002f31b  lea     rcx, [rsp+1718h+var_1590]
0x18002f323  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x18002f328  nop
0x18002f329  mov     ebx, 104h
0x18002f32e  mov     r8d, ebx; nSize
0x18002f331  lea     rdx, [rsp+1718h+PathName]; lpDst
0x18002f339  lea     rcx, Src; "%WINDIR%\\system32\\wdi\\LogFiles\\Star"...
0x18002f340  call    cs:__imp_ExpandEnvironmentStringsW
0x18002f346  test    eax, eax
0x18002f348  jnz     loc_18002F46E
0x18002f34e  call    cs:__imp_GetLastError
0x18002f354  mov     r15d, eax
0x18002f357  test    eax, eax
0x18002f359  jle     short loc_18002F366
0x18002f35b  movzx   r15d, ax
0x18002f35f  or      r15d, 80070000h
0x18002f366  test    r15d, r15d
0x18002f369  jns     short loc_18002F39F
0x18002f36b  xorps   xmm0, xmm0
0x18002f36e  movups  xmmword ptr [rsp+1718h+IoStatusBlock], xmm0
0x18002f376  mov     [rsp+1718h+FileInformation], 1
0x18002f37b  mov     [rsp+1718h+dwCreationDisposition], 0Dh; FileInformationClass
0x18002f383  mov     r9d, 1; Length
0x18002f389  lea     r8, [rsp+1718h+FileInformation]; FileInformation
0x18002f38e  lea     rdx, [rsp+1718h+IoStatusBlock]; IoStatusBlock
0x18002f396  mov     rcx, rsi; FileHandle
0x18002f399  call    cs:__imp_NtSetInformationFile
0x18002f39f  mov     rcx, rsi; hObject
0x18002f3a2  call    cs:__imp_CloseHandle
0x18002f3a8  mov     rbx, [rsp+1718h+var_1688]
0x18002f3b0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace> `wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl(void)'::`2'::impl
0x18002f3b7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(void)
0x18002f3bc  test    al, al
0x18002f3be  jz      short loc_18002F409
0x18002f3c0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002f3c4  jz      short loc_18002F409
0x18002f3c6  test    r15d, r15d
0x18002f3c9  jns     short loc_18002F3FF
0x18002f3cb  xorps   xmm0, xmm0
0x18002f3ce  movups  xmmword ptr [rsp+1718h+IoStatusBlock], xmm0
0x18002f3d6  mov     [rsp+1718h+FileInformation], 1
0x18002f3db  mov     [rsp+1718h+dwCreationDisposition], 0Dh; FileInformationClass
0x18002f3e3  mov     r9d, 1; Length
0x18002f3e9  lea     r8, [rsp+1718h+FileInformation]; FileInformation
0x18002f3ee  lea     rdx, [rsp+1718h+IoStatusBlock]; IoStatusBlock
0x18002f3f6  mov     rcx, rbx; FileHandle
0x18002f3f9  call    cs:__imp_NtSetInformationFile
0x18002f3ff  mov     rcx, rbx; hObject
0x18002f402  call    cs:__imp_CloseHandle
0x18002f408  nop
0x18002f409  lea     rcx, [rsp+1718h+var_14E8]; this
0x18002f411  call    ??1CNtImagePathDecoderBase@PerfDiagShared@@QEAA@XZ; PerfDiagShared::CNtImagePathDecoderBase::~CNtImagePathDecoderBase(void)
0x18002f416  nop
0x18002f417  lea     rcx, [rsp+1718h+var_1650]; this
0x18002f41f  call    ??1BootPrefetcherData@PerfDiagStartupResourceUtilizationReporting@@QEAA@XZ; PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData(void)
0x18002f424  nop
0x18002f425  lea     rcx, [rsp+1718h+var_15D8]
0x18002f42d  call    ??1?$_Tree@V?$_Tmap_traits@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@_KU?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(void)
0x18002f432  nop
0x18002f433  lea     rcx, [rsp+1718h+var_15F8]
0x18002f43b  call    ??1?$_Tree@V?$_Tset_traits@UClassicEventStats@ITraceStatsInfoSource@XPerfAddIn@@UlessEventStats@?$CTraceStatsSource@UCClassicEtwEventPolicy@XPerfAddIn@@@3@V?$allocator@UClassicEventStats@ITraceStatsInfoSource@XPerfAddIn@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>::~_Tree<std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>(void)
0x18002f440  nop
0x18002f441  xor     r8d, r8d
0x18002f444  mov     dl, 1
0x18002f446  lea     rcx, [rsp+1718h+var_1590]
0x18002f44e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002f453  nop
0x18002f454  xor     r8d, r8d
0x18002f457  mov     dl, 1
0x18002f459  lea     rcx, [rsp+1718h+lpBuffer]
0x18002f461  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002f466  mov     eax, r15d
0x18002f469  jmp     loc_18003035D
0x18002f46e  lea     r8, aJsonsummary; "JsonSummary\\"
0x18002f475  mov     rdx, rbx; unsigned __int64
0x18002f478  lea     rcx, [rsp+1718h+PathName]; unsigned __int16 *
0x18002f480  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002f485  mov     r15d, eax
0x18002f488  test    eax, eax
0x18002f48a  js      loc_18002F366
0x18002f490  xor     edx, edx; lpSecurityAttributes
0x18002f492  lea     rcx, [rsp+1718h+PathName]; lpPathName
0x18002f49a  call    cs:__imp_CreateDirectoryW
0x18002f4a0  mov     r8, [r14+3B8h]; unsigned __int16 *
0x18002f4a7  mov     rdx, rbx; unsigned __int64
0x18002f4aa  lea     rcx, [rsp+1718h+PathName]; unsigned __int16 *
0x18002f4b2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002f4b7  mov     r15d, eax
0x18002f4ba  test    eax, eax
0x18002f4bc  js      loc_18002F366
0x18002f4c2  lea     r8, aStartupinfoJso; "_StartupInfo?.json"
0x18002f4c9  mov     rdx, rbx; unsigned __int64
0x18002f4cc  lea     rcx, [rsp+1718h+PathName]; unsigned __int16 *
0x18002f4d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002f4d9  mov     r15d, eax
0x18002f4dc  test    eax, eax
0x18002f4de  js      loc_18002F366
0x18002f4e4  lea     rcx, [rsp+1718h+PathName]; lpFileName
0x18002f4ec  call    ?FindSuccessorFileName@PerfDiagStartupResourceUtilizationReporting@@YAJPEAG@Z; PerfDiagStartupResourceUtilizationReporting::FindSuccessorFileName(ushort *)
0x18002f4f1  mov     r15d, eax
0x18002f4f4  test    eax, eax
0x18002f4f6  js      loc_18002F366
0x18002f4fc  lea     rcx, [rsp+1718h+PathName]; lpFileName
0x18002f504  call    cs:__imp_DeleteFileW
0x18002f50a  mov     [rsp+1718h+hTemplateFile], r12; hTemplateFile
0x18002f50f  mov     [rsp+1718h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18002f514  mov     [rsp+1718h+dwCreationDisposition], 2; dwCreationDisposition
0x18002f51c  xor     r9d, r9d; lpSecurityAttributes
0x18002f51f  xor     r8d, r8d; dwShareMode
0x18002f522  mov     edx, 40050000h; dwDesiredAccess
0x18002f527  lea     rcx, [rsp+1718h+PathName]; lpFileName
0x18002f52f  call    cs:__imp_CreateFileW
0x18002f535  mov     rbx, rax
0x18002f538  mov     [rsp+1718h+var_1688], rax
0x18002f540  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002f544  jz      loc_18002F34E
0x18002f54a  mov     rdx, [r14+3B0h]; pSid
0x18002f551  test    rdx, rdx
0x18002f554  jnz     short loc_18002F561
0x18002f556  mov     r15d, 85551004h
0x18002f55c  jmp     loc_18002F36B
0x18002f561  mov     rcx, rax; handle
0x18002f564  call    ?SetAccessPermissions@PerfDiagStartupResourceUtilizationReporting@@YAJQEAX0@Z; PerfDiagStartupResourceUtilizationReporting::SetAccessPermissions(void * const,void * const)
0x18002f569  mov     r15d, eax
0x18002f56c  test    eax, eax
0x18002f56e  js      loc_18002F36B
0x18002f574  mov     r9, 431BDE82D7B634DBh
0x18002f57e  mov     rax, r9
0x18002f581  mov     rcx, [rsp+1718h+var_1660]
0x18002f589  imul    qword ptr [rcx]
0x18002f58c  mov     r8, rdx
0x18002f58f  sar     r8, 12h
0x18002f593  mov     rax, r8
0x18002f596  shr     rax, 3Fh
0x18002f59a  add     r8, rax
0x18002f59d  mov     rax, r9
0x18002f5a0  mov     r15, [rsp+1718h+var_1648]
0x18002f5a8  imul    qword ptr [r15]
0x18002f5ab  sar     rdx, 12h
0x18002f5af  mov     r9, rdx
0x18002f5b2  shr     r9, 3Fh
0x18002f5b6  add     r9, rdx
0x18002f5b9  lea     rcx, [rsp+1718h+lpBuffer]
0x18002f5c1  cmp     [rsp+1718h+var_1598], 8
0x18002f5ca  cmovnb  rcx, [rsp+1718h+lpBuffer]; unsigned __int16 *
0x18002f5d3  mov     qword ptr [rsp+1718h+dwCreationDisposition], r8
0x18002f5d8  lea     r8, qword_1800E8EC0; unsigned __int16 *
0x18002f5df  mov     rdx, [rsp+1718h+var_15A0]; unsigned __int64
0x18002f5e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f5ec  lea     rax, [rsp+1718h+lpBuffer]
0x18002f5f4  cmp     [rsp+1718h+var_1598], 8
0x18002f5fd  cmovnb  rax, [rsp+1718h+lpBuffer]
0x18002f606  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002f60a  inc     r8
0x18002f60d  cmp     [rax+r8*2], r12w
0x18002f612  jnz     short loc_18002F60A
0x18002f614  add     r8d, r8d; nNumberOfBytesToWrite
0x18002f617  lea     rdx, [rsp+1718h+lpBuffer]
0x18002f61f  cmp     [rsp+1718h+var_1598], 8
0x18002f628  cmovnb  rdx, [rsp+1718h+lpBuffer]; lpBuffer
0x18002f631  mov     qword ptr [rsp+1718h+dwCreationDisposition], r12; lpOverlapped
0x18002f636  lea     r9, [rsp+1718h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002f63b  mov     rcx, rsi; hFile
0x18002f63e  call    cs:__imp_WriteFile
0x18002f644  test    eax, eax
0x18002f646  jz      loc_18002F34E
0x18002f64c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace> `wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl(void)'::`2'::impl
0x18002f653  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(void)
0x18002f658  test    al, al
  ... truncated ...
```
