# CbsWcpErrorReport(int,HINSTANCE__ *,_CSI_ERROR_REPORT_DATA const *,wchar_t const *,wchar_t const *)

- ea: `0x18011f2e4`
- end: `0x18011fa6a`
- name: `?CbsWcpErrorReport@@YAJHPEAUHINSTANCE__@@PEBU_CSI_ERROR_REPORT_DATA@@PEB_W2@Z`
- size: `1926`
- prototype: `__int64 __fastcall(int, HINSTANCE, const struct _CSI_ERROR_REPORT_DATA *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800f5df8`

## callees

- `0x180013250`
- `0x1800261e0`
- `0x1800406e4`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800eb920`
- `0x1800ec920`
- `0x1801066f4`
- `0x18011f290`
- `0x18011f2e4`
- `0x18012019c`
- `0x180120648`
- `0x180120774`
- `0x180120910`
- `0x180120928`
- `0x180120960`
- `0x180120984`
- `0x1801209ac`
- `0x180121528`
- `0x180121a24`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f4ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f4ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011f92e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011f92e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011f91f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011f91f`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18011f499`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18011f499`

## string_xrefs

- `0x18011f743`: `%windir%\servicing\Sessions\Sessions.xml`
- `0x18011f450`: `WER service not available`
- `0x18011f3db`: `Failed to create Windows Error Report.`
- `0x18011f831`: `Warning: WER service is not available, skip reporting`
- `0x18011f7a3`: `%Windir%\WinSxs\pending.xml.bad`
- `0x18011f792`: `%Windir%\WinSxs\pending.xml`
- `0x18011f768`: `Failed to allocate current session file path name for Windows Error Report.`
- `0x18011f757`: `%%Windir%%\servicing\Sessions\%s.xml`
- `0x18011f820`: `%Windir%\winsxs\Temp\LogFiles\NtfsLog.etl`
- `0x18011f7c5`: `%Windir%\system32\LogFiles\Scm\SCM.EVM`

## pseudocode

```c
__int64 __fastcall CbsWcpErrorReport(
        int a1,
        HINSTANCE a2,
        const struct _CSI_ERROR_REPORT_DATA *a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  void *v6; // rcx
  unsigned int v9; // ebx
  int v10; // edx
  __int64 v11; // rdx
  const wchar_t *v12; // rax
  enum _WER_REPORT_TYPE v13; // edx
  struct _WER_REPORT_INFORMATION *v14; // r8
  int v15; // eax
  int v16; // edx
  const char *v17; // rdx
  signed int LastError; // ebx
  int v19; // edx
  unsigned int v20; // eax
  int v21; // eax
  int v22; // edx
  int v23; // eax
  enum _WER_FILE_TYPE v24; // r8d
  unsigned int v25; // r9d
  int v26; // edx
  unsigned int i; // esi
  __int64 v28; // r8
  const wchar_t *v29; // r9
  __int64 v30; // rax
  const wchar_t *v31; // r8
  int v32; // eax
  __int64 j; // rbx
  unsigned int v34; // eax
  enum _WER_FILE_TYPE v35; // r8d
  unsigned int v36; // r9d
  enum _WER_FILE_TYPE v37; // r8d
  unsigned int v38; // r9d
  unsigned int v39; // ebx
  enum _WER_FILE_TYPE v40; // r8d
  unsigned int v41; // r9d
  enum _WER_FILE_TYPE v42; // r8d
  unsigned int v43; // r9d
  enum _WER_FILE_TYPE v44; // r8d
  unsigned int v45; // r9d
  wchar_t *v46; // rdx
  wchar_t *v47; // rcx
  enum _WER_FILE_TYPE v48; // r8d
  unsigned int v49; // r9d
  enum _WER_FILE_TYPE v50; // r8d
  unsigned int v51; // r9d
  int v53; // edx
  unsigned int v54; // eax
  struct _EXCEPTION_POINTERS *v55; // rax
  HANDLE CurrentThread; // rbx
  HANDLE CurrentProcess; // rdx
  unsigned int v58; // eax
  int v59; // eax
  unsigned int v60; // r8d
  enum _WER_SUBMIT_RESULT *v61; // r9
  int v62; // edx
  enum _WER_CONSENT v63; // edx
  int v64; // eax
  int v65; // edx
  unsigned int v66; // [rsp+20h] [rbp-E0h]
  bool v67; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v68[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v69; // [rsp+50h] [rbp-B0h] BYREF
  int v70; // [rsp+54h] [rbp-ACh] BYREF
  wchar_t *v71; // [rsp+58h] [rbp-A8h] BYREF
  void *v72; // [rsp+60h] [rbp-A0h] BYREF
  struct _WER_EXCEPTION_INFORMATION v73; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v74; // [rsp+78h] [rbp-88h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+80h] [rbp-80h] BYREF
  wchar_t v76[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v77; // [rsp+1B0h] [rbp+B0h]
  _BYTE v78[22]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v6 = 0;
  v71 = 0;
  v72 = 0;
  if ( !a2 )
  {
LABEL_56:
    v9 = 0;
    goto LABEL_57;
  }
  if ( !a3 )
  {
LABEL_54:
    if ( v6 )
      CbsWerReportCloseHandle(v6);
    goto LABEL_56;
  }
  if ( *(_DWORD *)a3 != 56 )
  {
    v9 = -2147024809;
    v74 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Unexpected CSI error report data size.");
      *(_QWORD *)v68 = &v74;
      LOBYTE(v10) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v10,
        3,
        (unsigned int)": {}",
        (__int64)v68);
    }
    v11 = 766;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\cbs\\werlib\\cbswer.cpp",
      (const char *)v9,
      v66);
    goto LABEL_12;
  }
  v12 = CbsCsiErrorTypeToWerEventName(*((_DWORD *)a3 + 2));
  v15 = CbsWerReportCreate(v12, v13, v14, &v72);
  v9 = v15;
  if ( v15 < 0 )
  {
    v74 = v15;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create Windows Error Report.");
      *(_QWORD *)v68 = &v74;
      LOBYTE(v16) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        3,
        (unsigned int)": {}",
        (__int64)v68);
    }
    v11 = 769;
    goto LABEL_11;
  }
  if ( v15 == 1 )
  {
    v17 = "WER service not available";
LABEL_52:
    LogAdapter::TraceAtLevel<>(1, v17);
    goto LABEL_53;
  }
  memset(v78, 0, sizeof(v78));
  *(_OWORD *)v76 = 0;
  v77 = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
  {
    v74 = 0;
    v68[0] = 0;
    v70 = 0;
    v69 = 0;
    GetSelfFileVersion(&v74, v68, &v70, &v69);
    v66 = v68[0];
    v21 = StringCchPrintfW(v76, 0x1Bu, L"%hu.%hu.%hu.%hu:%x", v74);
    v9 = v21;
    if ( v21 < 0 )
    {
      v74 = v21;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "StringCchPrintf failed.");
        *(_QWORD *)v68 = &v74;
        LOBYTE(v22) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v22,
          3,
          (unsigned int)": {}",
          (__int64)v68);
      }
      v11 = 794;
      goto LABEL_11;
    }
    v23 = CbsWerReportSetParameter(v72, 0, L"OsVersion", v76);
    v9 = v23;
    if ( v23 < 0 )
    {
      v74 = v23;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to set Windows Error Report parameters.");
        *(_QWORD *)v68 = &v74;
        LOBYTE(v26) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v26,
          3,
          (unsigned int)": {}",
          (__int64)v68);
      }
      v11 = 797;
      goto LABEL_11;
    }
    for ( i = 1; i <= 9; ++i )
    {
      if ( i >= *((_DWORD *)a3 + 3) + 1 )
        break;
      v28 = i - 1;
      v29 = *(const wchar_t **)(*((_QWORD *)a3 + 3) + 8 * v28);
      v30 = *((_QWORD *)a3 + 2);
      if ( v30 )
        v31 = *(const wchar_t **)(v30 + 8 * v28);
      else
        v31 = 0;
      v32 = CbsWerReportSetParameter(v72, i, v31, v29);
      v9 = v32;
      if ( v32 < 0 )
      {
        v74 = v32;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to set Windows Error Report parameters.");
          *(_QWORD *)v68 = &v74;
          LOBYTE(v53) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v53,
            3,
            (unsigned int)": {}",
            (__int64)v68);
        }
        v11 = 805;
        goto LABEL_11;
      }
      if ( v32 == 1 )
      {
        v17 = "Warning: WER service is not available, skip reporting";
        goto LABEL_52;
      }
    }
    for ( j = 0; (unsigned int)j < *((_DWORD *)a3 + 8); j = (unsigned int)(j + 1) )
      CbsWerReportAddFile(v72, *(const wchar_t **)(*((_QWORD *)a3 + 5) + 8 * j), v24, v25);
    v34 = CbsWerReportAddCbsLogFiles(v72, a1);
    LogAdapter::TraceAtLevelIfFailed<long,>(3, v34, "Not able to add CBS log files to Windows Error Report.");
    if ( a1 )
    {
      if ( a4 )
      {
        v54 = CbsWerReportAddOfflineFiles(v72, a4, a5);
        LogAdapter::TraceAtLevelIfFailed<long,>(3, v54, "Not able to add files to offline WER report.");
      }
    }
    else
    {
      CbsWerReportAddFile(v72, L"%windir%\\servicing\\Sessions\\Sessions.xml", v35, v36);
      if ( a5 )
      {
        v39 = SczAllocFormatted(&v71, L"%%Windir%%\\servicing\\Sessions\\%s.xml", a5);
        LogAdapter::TraceAtLevelIfFailed<long,>(
          3,
          v39,
          "Failed to allocate current session file path name for Windows Error Report.");
        if ( !v39 )
          CbsWerReportAddFile(v72, v71, v37, v38);
      }
      CbsWerReportAddFile(v72, L"%Windir%\\WinSxs\\pending.xml", v37, v38);
      CbsWerReportAddFile(v72, L"%Windir%\\WinSxs\\pending.xml.bad", v40, v41);
      CbsWerReportAddFile(v72, L"%Windir%\\WinSxs\\poqexec.log", v42, v43);
      CbsWerReportAddFile(v72, L"%Windir%\\system32\\LogFiles\\Scm\\SCM.EVM", v44, v45);
      if ( CreateFilterDriverList((wchar_t *)L"Logs\\Cbs\\FilterList.log") >= 0 )
        CbsWerReportAddFile(v72, L"%Windir%\\Logs\\Cbs\\FilterList.log", v48, v49);
      if ( (*((_BYTE *)a3 + 4) & 1) != 0 && (int)FlushNtfsETWLog(v47, v46) >= 0 )
      {
        LogAdapter::TraceAtLevel<>(1, "Succesfully flushed NtfsLog.etl");
        CbsWerReportAddFile(v72, L"%Windir%\\winsxs\\Temp\\LogFiles\\NtfsLog.etl", v50, v51);
      }
    }
    v55 = (struct _EXCEPTION_POINTERS *)*((_QWORD *)a3 + 6);
    v73 = 0;
    if ( v55 )
    {
      v73.pExceptionPointers = v55;
      CurrentThread = GetCurrentThread();
      CurrentProcess = GetCurrentProcess();
      v58 = (unsigned int)vpfnWerReportAddDump;
      if ( vpfnWerReportAddDump )
        v58 = vpfnWerReportAddDump(v72, CurrentProcess, CurrentThread, WerDumpTypeMiniDump, &v73, 0, 0);
      LogAdapter::TraceAtLevelIfFailed<long,>(3, v58, "Not able to add mini dump to Windows Error Report.");
    }
    v67 = 0;
    v59 = QueryConsentKey(&v67);
    v9 = v59;
    if ( v59 < 0 )
    {
      v74 = v59;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to query Consent Key.");
        *(_QWORD *)v68 = &v74;
        LOBYTE(v62) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v62,
          3,
          (unsigned int)": {}",
          (__int64)v68);
      }
      v11 = 891;
      goto LABEL_11;
    }
    v63 = WerConsentApproved;
    if ( !v67 )
      v63 = WerConsentNotAsked;
    v64 = CbsWerReportSubmit(v72, v63, v60, v61);
    v9 = v64;
    if ( v64 < 0 )
    {
      v74 = v64;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to submit the Windows Error Report.");
        *(_QWORD *)v68 = &v74;
        LOBYTE(v65) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v65,
          3,
          (unsigned int)": {}",
          (__int64)v68);
      }
      v11 = 902;
      goto LABEL_11;
    }
    goto LABEL_53;
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "GetVersionEx failed.");
    if ( LastError > 0 )
      v20 = (unsigned __int16)LastError | 0x80070000;
    else
      v20 = LastError;
    v74 = v20;
    LOBYTE(v19) = 1;
    *(_QWORD *)v68 = &v74;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v19,
      3,
      (unsigned int)": {0}",
      (__int64)v68);
  }
  if ( !LastError )
  {
LABEL_53:
    v6 = v72;
    goto LABEL_54;
  }
  v9 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x30E,
         (unsigned int)"onecore\\base\\cbs\\werlib\\cbswer.cpp",
         (const char *)(unsigned int)LastError,
         v66);
LABEL_12:
  if ( v72 )
    CbsWerReportCloseHandle(v72);
LABEL_57:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v71);
  return v9;
}

```

## disassembly

```asm
0x18011f2e4  push    rbp
0x18011f2e6  push    rbx
0x18011f2e7  push    rsi
0x18011f2e8  push    r12
0x18011f2ea  push    r13
0x18011f2ec  push    r14
0x18011f2ee  push    r15
0x18011f2f0  lea     rbp, [rsp-0E0h]
0x18011f2f8  sub     rsp, 1E0h
0x18011f2ff  mov     rax, cs:__security_cookie
0x18011f306  xor     rax, rsp
0x18011f309  mov     [rbp+110h+var_38], rax
0x18011f310  mov     r15, [rbp+110h+arg_20]
0x18011f317  mov     r13d, ecx
0x18011f31a  xor     ecx, ecx
0x18011f31c  mov     [rsp+210h+var_1B8], 0
0x18011f325  mov     [rsp+210h+var_1B0], rcx
0x18011f32a  mov     r12, r9
0x18011f32d  mov     r14, r8
0x18011f330  test    rdx, rdx
0x18011f333  jz      loc_18011F851
0x18011f339  test    r8, r8
0x18011f33c  jz      loc_18011F847
0x18011f342  cmp     dword ptr [r8], 38h ; '8'
0x18011f346  jz      short loc_18011F3A6
0x18011f348  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18011f34f  mov     ebx, 80070057h
0x18011f354  mov     [rsp+210h+var_198], ebx
0x18011f358  test    rcx, rcx
0x18011f35b  jz      short loc_18011F39F
0x18011f35d  mov     esi, 3
0x18011f362  lea     r9, aUnexpectedCsiE; "Unexpected CSI error report data size."
0x18011f369  mov     r8d, esi
0x18011f36c  xor     edx, edx
0x18011f36e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18011f373  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18011f37a  lea     rax, [rsp+210h+var_198]
0x18011f37f  mov     qword ptr [rsp+210h+var_1C8], rax
0x18011f384  lea     r9, asc_1802EE7AC; ": {}"
0x18011f38b  lea     rax, [rsp+210h+var_1C8]
0x18011f390  mov     r8d, esi
0x18011f393  mov     dl, 1
0x18011f395  mov     qword ptr [rsp+210h+var_1F0], rax
0x18011f39a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18011f39f  mov     edx, 2FEh
0x18011f3a4  jmp     short loc_18011F41D
0x18011f3a6  mov     ecx, [r8+8]; unsigned int
0x18011f3aa  call    ?CbsCsiErrorTypeToWerEventName@@YAPEB_WK@Z; CbsCsiErrorTypeToWerEventName(ulong)
0x18011f3af  mov     rcx, rax; wchar_t *
0x18011f3b2  lea     r9, [rsp+210h+var_1B0]; void **
0x18011f3b7  call    ?CbsWerReportCreate@@YAJPEB_WW4_WER_REPORT_TYPE@@PEAU_WER_REPORT_INFORMATION@@PEAPEAX@Z; CbsWerReportCreate(wchar_t const *,_WER_REPORT_TYPE,_WER_REPORT_INFORMATION *,void * *)
0x18011f3bc  mov     ebx, eax
0x18011f3be  test    eax, eax
0x18011f3c0  jns     loc_18011F44B
0x18011f3c6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18011f3cd  mov     [rsp+210h+var_198], eax
0x18011f3d1  test    rcx, rcx
0x18011f3d4  jz      short loc_18011F418
0x18011f3d6  mov     esi, 3
0x18011f3db  lea     r9, aFailedToCreate_57; "Failed to create Windows Error Report."
0x18011f3e2  mov     r8d, esi
0x18011f3e5  xor     edx, edx
0x18011f3e7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18011f3ec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18011f3f3  lea     rax, [rsp+210h+var_198]
0x18011f3f8  mov     qword ptr [rsp+210h+var_1C8], rax
0x18011f3fd  lea     r9, asc_1802EE7AC; ": {}"
0x18011f404  lea     rax, [rsp+210h+var_1C8]
0x18011f409  mov     r8d, esi
0x18011f40c  mov     dl, 1
0x18011f40e  mov     qword ptr [rsp+210h+var_1F0], rax; int
0x18011f413  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18011f418  mov     edx, 301h; void *
0x18011f41d  mov     rcx, [rbp+118h]; this
0x18011f424  lea     r8, aOnecoreBaseCbs_72; "onecore\\base\\cbs\\werlib\\cbswer.cpp"
0x18011f42b  mov     r9d, ebx; char *
0x18011f42e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011f433  mov     rcx, [rsp+210h+var_1B0]; void *
0x18011f438  test    rcx, rcx
0x18011f43b  jz      loc_18011F853
0x18011f441  call    ?CbsWerReportCloseHandle@@YAJPEAX@Z; CbsWerReportCloseHandle(void *)
0x18011f446  jmp     loc_18011F853
0x18011f44b  cmp     ebx, 1
0x18011f44e  jnz     short loc_18011F45C
0x18011f450  lea     rdx, aWerServiceNotA; "WER service not available"
0x18011f457  jmp     loc_18011F838
0x18011f45c  xorps   xmm0, xmm0
0x18011f45f  lea     rcx, [rbp+110h+VersionInformation.dwMajorVersion]; void *
0x18011f463  xor     eax, eax
0x18011f465  xor     edx, edx; Val
0x18011f467  movups  xmmword ptr [rbp+110h+var_50], xmm0
0x18011f46e  mov     r8d, 118h; Size
0x18011f474  mov     qword ptr [rbp+110h+var_50+0Eh], rax
0x18011f47b  movups  xmmword ptr [rbp+110h+var_70], xmm0
0x18011f482  movups  [rbp+110h+var_60], xmm0
0x18011f489  call    memset_0
0x18011f48e  lea     rcx, [rbp+110h+VersionInformation]; lpVersionInformation
0x18011f492  mov     [rbp+110h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18011f499  call    cs:__imp_GetVersionExW
0x18011f4a0  nop     dword ptr [rax+rax+00h]
0x18011f4a5  test    eax, eax
0x18011f4a7  jnz     loc_18011F547
0x18011f4ad  call    cs:__imp_GetLastError
0x18011f4b4  nop     dword ptr [rax+rax+00h]
0x18011f4b9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18011f4c0  mov     ebx, eax
0x18011f4c2  test    rcx, rcx
0x18011f4c5  jz      short loc_18011F51D
0x18011f4c7  mov     esi, 3
0x18011f4cc  lea     r9, aGetversionexFa; "GetVersionEx failed."
0x18011f4d3  mov     r8d, esi
0x18011f4d6  xor     edx, edx
0x18011f4d8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18011f4dd  test    ebx, ebx
0x18011f4df  jg      short loc_18011F4E5
0x18011f4e1  mov     eax, ebx
0x18011f4e3  jmp     short loc_18011F4ED
0x18011f4e5  movzx   eax, bx
0x18011f4e8  or      eax, 80070000h
0x18011f4ed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18011f4f4  lea     r9, a0; ": {0}"
0x18011f4fb  mov     [rsp+210h+var_198], eax
0x18011f4ff  mov     r8d, esi
0x18011f502  lea     rax, [rsp+210h+var_198]
0x18011f507  mov     dl, 1
0x18011f509  mov     qword ptr [rsp+210h+var_1C8], rax
0x18011f50e  lea     rax, [rsp+210h+var_1C8]
0x18011f513  mov     qword ptr [rsp+210h+var_1F0], rax; unsigned int
0x18011f518  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18011f51d  test    ebx, ebx
0x18011f51f  jz      loc_18011F842
0x18011f525  mov     rcx, [rbp+118h]; this
0x18011f52c  lea     r8, aOnecoreBaseCbs_72; "onecore\\base\\cbs\\werlib\\cbswer.cpp"
0x18011f533  mov     r9d, ebx; char *
0x18011f536  mov     edx, 30Eh; void *
0x18011f53b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18011f540  mov     ebx, eax
0x18011f542  jmp     loc_18011F433
0x18011f547  movzx   ebx, [rbp+110h+var_76]
0x18011f54e  lea     r9, [rsp+210h+var_1C0]
0x18011f553  lea     r8, [rsp+210h+var_1BC]
0x18011f558  mov     [rsp+210h+var_198], 0
0x18011f560  lea     rdx, [rsp+210h+var_1C8]
0x18011f565  mov     [rsp+210h+var_1C8], 0
0x18011f56d  lea     rcx, [rsp+210h+var_198]
0x18011f572  mov     [rsp+210h+var_1BC], 0
0x18011f57a  mov     [rsp+210h+var_1C0], 0
0x18011f582  call    GetSelfFileVersion
0x18011f587  mov     eax, [rsp+210h+var_1C0]
0x18011f58b  lea     r8, aHuHuHuHuX; "%hu.%hu.%hu.%hu:%x"
0x18011f592  mov     r9d, [rsp+210h+var_198]
0x18011f597  lea     rcx, [rbp+110h+var_70]; wchar_t *
0x18011f59e  mov     [rsp+210h+var_1D8], ebx
0x18011f5a2  mov     edx, 1Bh; unsigned __int64
0x18011f5a7  mov     [rsp+210h+var_1E0], eax
0x18011f5ab  mov     eax, [rsp+210h+var_1BC]
0x18011f5af  mov     dword ptr [rsp+210h+var_1E8], eax
0x18011f5b3  mov     eax, [rsp+210h+var_1C8]
0x18011f5b7  mov     [rsp+210h+var_1F0], eax
0x18011f5bb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18011f5c0  mov     ebx, eax
0x18011f5c2  test    eax, eax
0x18011f5c4  jns     short loc_18011F622
0x18011f5c6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18011f5cd  mov     [rsp+210h+var_198], eax
0x18011f5d1  test    rcx, rcx
0x18011f5d4  jz      short loc_18011F618
0x18011f5d6  mov     esi, 3
0x18011f5db  lea     r9, aStringcchprint; "StringCchPrintf failed."
0x18011f5e2  mov     r8d, esi
0x18011f5e5  xor     edx, edx
0x18011f5e7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18011f5ec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18011f5f3  lea     rax, [rsp+210h+var_198]
0x18011f5f8  mov     qword ptr [rsp+210h+var_1C8], rax
0x18011f5fd  lea     r9, asc_1802EE7AC; ": {}"
0x18011f604  lea     rax, [rsp+210h+var_1C8]
0x18011f609  mov     r8d, esi
0x18011f60c  mov     dl, 1
0x18011f60e  mov     qword ptr [rsp+210h+var_1F0], rax
0x18011f613  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18011f618  mov     edx, 31Ah
0x18011f61d  jmp     loc_18011F41D
0x18011f622  mov     rcx, [rsp+210h+var_1B0]; void *
0x18011f627  lea     r9, [rbp+110h+var_70]; wchar_t *
0x18011f62e  lea     r8, aOsversion; "OsVersion"
0x18011f635  xor     edx, edx; unsigned int
0x18011f637  call    ?CbsWerReportSetParameter@@YAJPEAXKPEB_W1@Z; CbsWerReportSetParameter(void *,ulong,wchar_t const *,wchar_t const *)
0x18011f63c  mov     ebx, eax
0x18011f63e  test    eax, eax
0x18011f640  jns     short loc_18011F69E
0x18011f642  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18011f649  mov     [rsp+210h+var_198], eax
0x18011f64d  test    rcx, rcx
0x18011f650  jz      short loc_18011F694
0x18011f652  mov     esi, 3
0x18011f657  lea     r9, aFailedToSetWin; "Failed to set Windows Error Report para"...
0x18011f65e  mov     r8d, esi
0x18011f661  xor     edx, edx
0x18011f663  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18011f668  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18011f66f  lea     rax, [rsp+210h+var_198]
0x18011f674  mov     qword ptr [rsp+210h+var_1C8], rax
0x18011f679  lea     r9, asc_1802EE7AC; ": {}"
0x18011f680  lea     rax, [rsp+210h+var_1C8]
0x18011f685  mov     r8d, esi
0x18011f688  mov     dl, 1
0x18011f68a  mov     qword ptr [rsp+210h+var_1F0], rax
0x18011f68f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18011f694  mov     edx, 31Dh
0x18011f699  jmp     loc_18011F41D
0x18011f69e  mov     esi, 1
0x18011f6a3  mov     eax, [r14+0Ch]
0x18011f6a7  inc     eax
0x18011f6a9  cmp     esi, eax
0x18011f6ab  jnb     short loc_18011F6F1
0x18011f6ad  mov     rax, [r14+18h]
0x18011f6b1  lea     r8d, [rsi-1]
0x18011f6b5  mov     r9, [rax+r8*8]; wchar_t *
0x18011f6b9  mov     rax, [r14+10h]
0x18011f6bd  test    rax, rax
0x18011f6c0  jz      short loc_18011F6C8
0x18011f6c2  mov     r8, [rax+r8*8]
0x18011f6c6  jmp     short loc_18011F6CB
0x18011f6c8  xor     r8d, r8d; wchar_t *
0x18011f6cb  mov     rcx, [rsp+210h+var_1B0]; void *
0x18011f6d0  mov     edx, esi; unsigned int
0x18011f6d2  call    ?CbsWerReportSetParameter@@YAJPEAXKPEB_W1@Z; CbsWerReportSetParameter(void *,ulong,wchar_t const *,wchar_t const *)
0x18011f6d7  mov     ebx, eax
0x18011f6d9  test    eax, eax
0x18011f6db  js      loc_18011F882
0x18011f6e1  cmp     eax, 1
0x18011f6e4  jz      loc_18011F831
0x18011f6ea  inc     esi
0x18011f6ec  cmp     esi, 9
0x18011f6ef  jbe     short loc_18011F6A3
0x18011f6f1  xor     ebx, ebx
0x18011f6f3  cmp     [r14+20h], ebx
0x18011f6f7  jbe     short loc_18011F713
0x18011f6f9  mov     rdx, [r14+28h]
0x18011f6fd  mov     rcx, [rsp+210h+var_1B0]; void *
0x18011f702  mov     rdx, [rdx+rbx*8]; wchar_t *
0x18011f706  call    ?CbsWerReportAddFile@@YAJPEAXPEB_WW4_WER_FILE_TYPE@@K@Z; CbsWerReportAddFile(void *,wchar_t const *,_WER_FILE_TYPE,ulong)
0x18011f70b  inc     ebx
0x18011f70d  cmp     ebx, [r14+20h]
0x18011f711  jb      short loc_18011F6F9
0x18011f713  mov     rcx, [rsp+210h+var_1B0]; void *
0x18011f718  mov     edx, r13d; int
0x18011f71b  call    ?CbsWerReportAddCbsLogFiles@@YAJPEAXH@Z; CbsWerReportAddCbsLogFiles(void *,int)
0x18011f720  mov     esi, 3
0x18011f725  lea     r8, aNotAbleToAddCb_0; "Not able to add CBS log files to Window"...
0x18011f72c  mov     ecx, esi
0x18011f72e  mov     edx, eax
0x18011f730  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18011f735  test    r13d, r13d
0x18011f738  jnz     loc_18011F8DE
0x18011f73e  mov     rcx, [rsp+210h+var_1B0]; void *
0x18011f743  lea     rdx, aWindirServicin_0; "%windir%\\servicing\\Sessions\\Sessions"...
0x18011f74a  call    ?CbsWerReportAddFile@@YAJPEAXPEB_WW4_WER_FILE_TYPE@@K@Z; CbsWerReportAddFile(void *,wchar_t const *,_WER_FILE_TYPE,ulong)
0x18011f74f  test    r15, r15
0x18011f752  jz      short loc_18011F78D
0x18011f754  mov     r8, r15
0x18011f757  lea     rdx, aWindirServicin; "%%Windir%%\\servicing\\Sessions\\%s.xml"
0x18011f75e  lea     rcx, [rsp+210h+var_1B8]
0x18011f763  call    SczAllocFormatted
0x18011f768  lea     r8, aFailedToAlloca_24; "Failed to allocate current session file"...
0x18011f76f  mov     edx, eax
0x18011f771  mov     ecx, esi
0x18011f773  mov     ebx, eax
0x18011f775  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18011f77a  test    ebx, ebx
0x18011f77c  jnz     short loc_18011F78D
0x18011f77e  mov     rdx, [rsp+210h+var_1B8]; wchar_t *
0x18011f783  mov     rcx, [rsp+210h+var_1B0]; void *
0x18011f788  call    ?CbsWerReportAddFile@@YAJPEAXPEB_WW4_WER_FILE_TYPE@@K@Z; CbsWerReportAddFile(void *,wchar_t const *,_WER_FILE_TYPE,ulong)
0x18011f78d  mov     rcx, [rsp+210h+var_1B0]; void *
0x18011f792  lea     rdx, aWindirWinsxsPe_1; "%Windir%\\WinSxs\\pending.xml"
0x18011f799  call    ?CbsWerReportAddFile@@YAJPEAXPEB_WW4_WER_FILE_TYPE@@K@Z; CbsWerReportAddFile(void *,wchar_t const *,_WER_FILE_TYPE,ulong)
0x18011f79e  mov     rcx, [rsp+210h+var_1B0]; void *
0x18011f7a3  lea     rdx, aWindirWinsxsPe_0; "%Windir%\\WinSxs\\pending.xml.bad"
0x18011f7aa  call    ?CbsWerReportAddFile@@YAJPEAXPEB_WW4_WER_FILE_TYPE@@K@Z; CbsWerReportAddFile(void *,wchar_t const *,_WER_FILE_TYPE,ulong)
0x18011f7af  mov     rcx, [rsp+210h+var_1B0]; void *
0x18011f7b4  lea     rdx, aWindirWinsxsPo; "%Windir%\\WinSxs\\poqexec.log"
0x18011f7bb  call    ?CbsWerReportAddFile@@YAJPEAXPEB_WW4_WER_FILE_TYPE@@K@Z; CbsWerReportAddFile(void *,wchar_t const *,_WER_FILE_TYPE,ulong)
0x18011f7c0  mov     rcx, [rsp+210h+var_1B0]; void *
0x18011f7c5  lea     rdx, aWindirSystem32; "%Windir%\\system32\\LogFiles\\Scm\\SCM."...
0x18011f7cc  call    ?CbsWerReportAddFile@@YAJPEAXPEB_WW4_WER_FILE_TYPE@@K@Z; CbsWerReportAddFile(void *,wchar_t const *,_WER_FILE_TYPE,ulong)
0x18011f7d1  lea     rcx, aLogsCbsFilterl; "Logs\\Cbs\\FilterList.log"
0x18011f7d8  call    ?CreateFilterDriverList@@YAJPEA_W@Z; CreateFilterDriverList(wchar_t *)
0x18011f7dd  test    eax, eax
0x18011f7df  js      short loc_18011F7F2
0x18011f7e1  mov     rcx, [rsp+210h+var_1B0]; void *
0x18011f7e6  lea     rdx, aWindirLogsCbsF; "%Windir%\\Logs\\Cbs\\FilterList.log"
0x18011f7ed  call    ?CbsWerReportAddFile@@YAJPEAXPEB_WW4_WER_FILE_TYPE@@K@Z; CbsWerReportAddFile(void *,wchar_t const *,_WER_FILE_TYPE,ulong)
0x18011f7f2  test    byte ptr [r14+4], 1
0x18011f7f7  jz      loc_18011F903
0x18011f7fd  call    ?FlushNtfsETWLog@@YAJPEA_W0@Z; FlushNtfsETWLog(wchar_t *,wchar_t *)
0x18011f802  test    eax, eax
0x18011f804  js      loc_18011F903
0x18011f80a  lea     rdx, aSuccesfullyFlu_0; "Succesfully flushed NtfsLog.etl"
  ... truncated ...
```
