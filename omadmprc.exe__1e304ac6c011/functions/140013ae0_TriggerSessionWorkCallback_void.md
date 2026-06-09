# TriggerSessionWorkCallback(void *)

- ea: `0x140013ae0`
- end: `0x140014014`
- name: `?TriggerSessionWorkCallback@@YAXPEAX@Z`
- size: `1332`
- prototype: `void __fastcall(TriggerSessionContext *this)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140001090`
- `0x14000271f`
- `0x14000812c`
- `0x140008ea0`
- `0x14000b708`
- `0x14000c1a4`
- `0x14000f0d0`
- `0x14000f250`
- `0x14000f964`
- `0x140010f44`
- `0x140012604`
- `0x140013ae0`
- `0x1400141a0`
- `0x140015690`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140013fc0`
- `msvcrt!??3@YAXPEAX@Z` at `0x140013fc0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140013e47`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140013e47`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140013d0f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140013d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013b79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013b79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013e57`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140013dc0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140013dc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013fda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013fda`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140013e8e`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140013e8e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140013b63`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140013b63`

## string_xrefs

- `0x140013c06`: `/serverid "%s" /lookuptype 1 /initiator %d /initiationid "%s" /usersid "%s" /sessionid %d`
- `0x140013b5c`: `%windir%\system32\omadmclient.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TriggerSessionWorkCallback(TriggerSessionContext *this)
{
  char *hProcess; // rbx
  signed int LastError; // eax
  signed int refreshed; // edi
  signed int v5; // eax
  __int64 v6; // r9
  int v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // r8d
  signed int v10; // eax
  __int64 v11; // rcx
  unsigned int v12; // r8d
  __int64 v13; // rcx
  unsigned int v14; // r8d
  signed int v15; // eax
  bool v16; // sf
  unsigned int v17; // ecx
  const WCHAR *v18; // rcx
  const unsigned __int16 **v19; // r14
  const WCHAR *v20; // rcx
  COmaDmPrcLogger *Logger; // r10
  int v22; // edx
  unsigned int v23; // eax
  struct _PROCESS_INFORMATION *v24; // rdx
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v26; // [rsp+54h] [rbp-ACh]
  DWORD ExitCode; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  int v29; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  HANDLE v31; // [rsp+78h] [rbp-88h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v34[32]; // [rsp+110h] [rbp+10h] BYREF
  __int64 *v35; // [rsp+130h] [rbp+30h]
  __int64 v36; // [rsp+138h] [rbp+38h]
  WCHAR Dst[264]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR CommandLine[1024]; // [rsp+350h] [rbp+250h] BYREF

  v29 = 0;
  ExitCode = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  hProcess = 0;
  v31 = 0;
  memset_0(Dst, 0, 0x208u);
  if ( !ExpandEnvironmentStringsW(Src, Dst, 0x104u) )
  {
    LastError = GetLastError();
    refreshed = LastError;
    if ( LastError > 0 )
      refreshed = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_4;
  }
  memset_0(CommandLine, 0, sizeof(CommandLine));
  v6 = *((_QWORD *)this + 1);
  if ( *((_BYTE *)this + 32) )
  {
    v7 = StringCchPrintfW(CommandLine, 0x400u, aServeridSLooku_1, v6, *((unsigned __int8 *)this + 32));
  }
  else if ( *(_QWORD *)this )
  {
    v7 = StringCchPrintfW(
           CommandLine,
           0x400u,
           aServeridSLooku,
           v6,
           0,
           *((_QWORD *)this + 2),
           *(_QWORD *)this,
           *((_DWORD *)this + 10));
  }
  else
  {
    v7 = StringCchPrintfW(CommandLine, 0x400u, aServeridSLooku_0, v6, 0, *((_QWORD *)this + 2), *((_DWORD *)this + 10));
  }
  refreshed = v7;
  if ( v7 < 0 )
    goto LABEL_4;
  hObject = 0;
  v9 = *(_DWORD *)Feature_ConfigRefresh__descriptor;
  if ( (*(_DWORD *)Feature_ConfigRefresh__descriptor & 4) == 0 )
  {
    v28 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(
                       v8,
                       &v28);
    v9 = v28;
  }
  v25 = 0;
  v26 = 3;
  wil::details::ReportUsageToService(&qword_140024350, 43467477, (v9 >> 10) & 1, (v9 >> 11) & 1, &v25, 1);
  refreshed = SignalConfigRefreshSemaphore(&hObject);
  if ( refreshed < 0 )
    goto LABEL_4;
  StartupInfo.cb = 104;
  if ( !CreateProcessW(Dst, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation)
    || (hProcess = (char *)ProcessInformation.hProcess,
        v31 = ProcessInformation.hProcess,
        ProcessInformation.hProcess = 0,
        WaitForSingleObject(v31, 0x5265C0u)) )
  {
    v10 = GetLastError();
    refreshed = v10;
    if ( v10 > 0 )
      refreshed = (unsigned __int16)v10 | 0x80070000;
    v12 = *(_DWORD *)Feature_ConfigRefresh__descriptor;
    if ( (*(_DWORD *)Feature_ConfigRefresh__descriptor & 4) == 0 )
    {
      v28 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(
                         v11,
                         &v28);
      v12 = v28;
    }
    v25 = 0;
    v26 = 3;
    wil::details::ReportUsageToService(&qword_140024350, 43467477, (v12 >> 10) & 1, (v12 >> 11) & 1, &v25, 1);
    WaitForConfigRefreshSemaphore(hObject);
    goto LABEL_4;
  }
  v14 = *(_DWORD *)Feature_ConfigRefresh__descriptor;
  if ( (*(_DWORD *)Feature_ConfigRefresh__descriptor & 4) == 0 )
  {
    v28 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(
                       v13,
                       &v28);
    v14 = v28;
  }
  v25 = 0;
  v26 = 3;
  wil::details::ReportUsageToService(&qword_140024350, 43467477, (v14 >> 10) & 1, (v14 >> 11) & 1, &v25, 1);
  WaitForConfigRefreshSemaphore(hObject);
  if ( !GetExitCodeProcess(hProcess, &ExitCode) )
  {
    v15 = GetLastError();
    refreshed = v15;
    if ( v15 > 0 )
      refreshed = (unsigned __int16)v15 | 0x80070000;
    if ( refreshed < 0 )
    {
LABEL_4:
      v5 = ExitCode;
      goto LABEL_5;
    }
  }
  v16 = (int)OmaDmRegistryGetDWORD(
               HKEY_LOCAL_MACHINE,
               *((const unsigned __int16 **)this + 2),
               L"SessionHRESULT",
               (unsigned int *)&v29) < 0;
  v5 = ExitCode;
  if ( !v16 && v29 >= 0 )
  {
    if ( (int)ExitCode > 0 )
      v17 = (unsigned __int16)ExitCode | 0x80070000;
    else
      v17 = ExitCode;
    v29 = v17;
  }
LABEL_5:
  if ( v5 || refreshed < 0 )
  {
    if ( refreshed >= 0 )
    {
      if ( v5 > 0 )
        refreshed = (unsigned __int16)v5 | 0x80070000;
      else
        refreshed = v5;
    }
    if ( (unsigned int)dword_140023000 > 5 )
    {
      v28 = refreshed;
      v35 = &v28;
      v36 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_140023000, byte_14001E235, 0, 0, 3, v34);
    }
  }
  v18 = (const WCHAR *)*((_QWORD *)this + 2);
  if ( v18 )
  {
    NotifySessionResultRecovery(v18, refreshed);
    v19 = (const unsigned __int16 **)((char *)this + 24);
    v20 = (const WCHAR *)*((_QWORD *)this + 3);
    if ( v20 )
      NotifySessionResultRecovery(v20, refreshed);
  }
  else
  {
    v19 = (const unsigned __int16 **)((char *)this + 24);
  }
  *((_DWORD *)this + 11) = v29;
  Logger = COmaDmPrcLogger::GetLogger();
  v22 = *((_DWORD *)this + 11);
  if ( qword_140024308 )
    v23 = _InterlockedCompareExchange(&ThreadpoolManager::m_numberOfWorkQueued, 0, 0);
  else
    v23 = 0;
  COmaDmPrcLogger::LogOmaDmPrcSessionComplete(
    Logger,
    *(const unsigned __int16 **)this,
    *((const unsigned __int16 **)this + 1),
    *((const unsigned __int16 **)this + 2),
    *v19,
    *((_DWORD *)this + 9),
    *((_DWORD *)this + 10),
    v23,
    v22,
    refreshed);
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *v19 = 0;
  TriggerSessionContext::~TriggerSessionContext(this);
  operator delete(this);
  if ( (unsigned __int64)(hProcess - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hProcess);
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v24);
}

```

## disassembly

```asm
0x140013ae0  push    rbp
0x140013ae2  push    rbx
0x140013ae3  push    rsi
0x140013ae4  push    rdi
0x140013ae5  push    r12
0x140013ae7  push    r13
0x140013ae9  push    r14
0x140013aeb  push    r15
0x140013aed  lea     rbp, [rsp-0A68h]
0x140013af5  sub     rsp, 0B68h
0x140013afc  mov     rax, cs:__security_cookie
0x140013b03  xor     rax, rsp
0x140013b06  mov     [rbp+0AA0h+var_50], rax
0x140013b0d  mov     rsi, rcx
0x140013b10  xor     r15d, r15d
0x140013b13  mov     [rsp+0BA0h+var_B38], r15d
0x140013b18  mov     [rsp+0BA0h+ExitCode], r15d
0x140013b1d  xor     edx, edx; Val
0x140013b1f  lea     r8d, [r15+68h]; Size
0x140013b23  lea     rcx, [rbp+0AA0h+StartupInfo]; void *
0x140013b27  call    memset_0
0x140013b2c  xorps   xmm0, xmm0
0x140013b2f  xor     eax, eax
0x140013b31  movups  xmmword ptr [rbp+0AA0h+ProcessInformation.hProcess], xmm0
0x140013b35  mov     qword ptr [rbp+0AA0h+ProcessInformation.dwProcessId], rax
0x140013b39  mov     ebx, r15d
0x140013b3c  mov     [rsp+0BA0h+var_B28], rbx
0x140013b41  xor     edx, edx; Val
0x140013b43  mov     r8d, 208h; Size
0x140013b49  lea     rcx, [rbp+0AA0h+Dst]; void *
0x140013b4d  call    memset_0
0x140013b52  mov     r8d, 104h; nSize
0x140013b58  lea     rdx, [rbp+0AA0h+Dst]; lpDst
0x140013b5c  lea     rcx, Src; "%windir%\\system32\\omadmclient.exe"
0x140013b63  call    cs:__imp_ExpandEnvironmentStringsW
0x140013b6a  nop     dword ptr [rax+rax+00h]
0x140013b6f  mov     r12d, 80070000h
0x140013b75  test    eax, eax
0x140013b77  jnz     short loc_140013BB8
0x140013b79  call    cs:__imp_GetLastError
0x140013b80  nop     dword ptr [rax+rax+00h]
0x140013b85  mov     edi, eax
0x140013b87  test    eax, eax
0x140013b89  jle     short loc_140013B91
0x140013b8b  movzx   edi, ax
0x140013b8e  or      edi, r12d
0x140013b91  mov     eax, [rsp+0BA0h+ExitCode]
0x140013b95  test    eax, eax
0x140013b97  jnz     short loc_140013BA1
0x140013b99  test    edi, edi
0x140013b9b  jns     loc_140013F1C
0x140013ba1  test    edi, edi
0x140013ba3  js      loc_140013ECE
0x140013ba9  test    eax, eax
0x140013bab  jg      loc_140013EC8
0x140013bb1  mov     edi, eax
0x140013bb3  jmp     loc_140013ECE
0x140013bb8  xor     edx, edx; Val
0x140013bba  mov     r8d, 800h; Size
0x140013bc0  lea     rcx, [rbp+0AA0h+CommandLine]; void *
0x140013bc7  call    memset_0
0x140013bcc  movzx   eax, byte ptr [rsi+20h]
0x140013bd0  mov     r9, [rsi+8]
0x140013bd4  mov     edx, 400h; unsigned __int64
0x140013bd9  lea     rcx, [rbp+0AA0h+CommandLine]; unsigned __int16 *
0x140013be0  test    al, al
0x140013be2  jnz     short loc_140013C34
0x140013be4  mov     eax, [rsi+28h]
0x140013be7  cmp     [rsi], r15
0x140013bea  jz      short loc_140013C14
0x140013bec  mov     dword ptr [rsp+0BA0h+lpCurrentDirectory], eax
0x140013bf0  mov     rax, [rsi]
0x140013bf3  mov     [rsp+0BA0h+lpEnvironment], rax
0x140013bf8  mov     rax, [rsi+10h]
0x140013bfc  mov     qword ptr [rsp+0BA0h+dwCreationFlags], rax
0x140013c01  mov     [rsp+0BA0h+bInheritHandles], r15d
0x140013c06  lea     r8, aServeridSLooku; "/serverid \"%s\" /lookuptype 1 /initiat"...
0x140013c0d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140013c12  jmp     short loc_140013C44
0x140013c14  mov     dword ptr [rsp+0BA0h+lpEnvironment], eax
0x140013c18  mov     rax, [rsi+10h]
0x140013c1c  mov     qword ptr [rsp+0BA0h+dwCreationFlags], rax
0x140013c21  mov     [rsp+0BA0h+bInheritHandles], r15d
0x140013c26  lea     r8, aServeridSLooku_0; "/serverid \"%s\" /lookuptype 1 /initiat"...
0x140013c2d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140013c32  jmp     short loc_140013C44
0x140013c34  mov     [rsp+0BA0h+bInheritHandles], eax
0x140013c38  lea     r8, aServeridSLooku_1; "/serverid \"%s\" /lookuptype 1 /initiat"...
0x140013c3f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140013c44  mov     edi, eax
0x140013c46  test    eax, eax
0x140013c48  js      loc_140013B91
0x140013c4e  mov     [rsp+0BA0h+hObject], r15
0x140013c53  mov     rax, cs:Feature_ConfigRefresh__descriptor
0x140013c5a  mov     r8d, [rax]
0x140013c5d  mov     r14b, 4
0x140013c60  test    r14b, r8b
0x140013c63  jnz     short loc_140013C7A
0x140013c65  lea     rdx, [rsp+0BA0h+var_B40]
0x140013c6a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ConfigRefresh@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(void)
0x140013c6f  mov     rcx, [rax]
0x140013c72  mov     [rsp+0BA0h+var_B40], rcx
0x140013c77  mov     r8d, ecx
0x140013c7a  mov     [rsp+0BA0h+var_B50], r15d
0x140013c7f  mov     [rsp+0BA0h+var_B4C], 3
0x140013c86  mov     r9d, r8d
0x140013c89  shr     r9d, 0Bh
0x140013c8d  mov     r13d, 1
0x140013c93  and     r9d, r13d
0x140013c96  shr     r8d, 0Ah
0x140013c9a  and     r8d, r13d
0x140013c9d  mov     [rsp+0BA0h+dwCreationFlags], r13d
0x140013ca2  lea     rax, [rsp+0BA0h+var_B50]
0x140013ca7  mov     qword ptr [rsp+0BA0h+bInheritHandles], rax
0x140013cac  mov     edx, 29742D5h
0x140013cb1  lea     rcx, qword_140024350
0x140013cb8  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140013cbd  lea     rcx, [rsp+0BA0h+hObject]; void **
0x140013cc2  call    ?SignalConfigRefreshSemaphore@@YAJPEAPEAX@Z; SignalConfigRefreshSemaphore(void * *)
0x140013cc7  mov     edi, eax
0x140013cc9  test    eax, eax
0x140013ccb  js      loc_140013B91
0x140013cd1  mov     [rbp+0AA0h+StartupInfo.cb], 68h ; 'h'
0x140013cd8  lea     rax, [rbp+0AA0h+ProcessInformation]
0x140013cdc  mov     [rsp+0BA0h+lpProcessInformation], rax; lpProcessInformation
0x140013ce1  lea     rax, [rbp+0AA0h+StartupInfo]
0x140013ce5  mov     [rsp+0BA0h+lpStartupInfo], rax; lpStartupInfo
0x140013cea  mov     [rsp+0BA0h+lpCurrentDirectory], r15; lpCurrentDirectory
0x140013cef  mov     [rsp+0BA0h+lpEnvironment], r15; lpEnvironment
0x140013cf4  mov     [rsp+0BA0h+dwCreationFlags], r15d; dwCreationFlags
0x140013cf9  mov     [rsp+0BA0h+bInheritHandles], r15d; bInheritHandles
0x140013cfe  xor     r9d, r9d; lpThreadAttributes
0x140013d01  xor     r8d, r8d; lpProcessAttributes
0x140013d04  lea     rdx, [rbp+0AA0h+CommandLine]; lpCommandLine
0x140013d0b  lea     rcx, [rbp+0AA0h+Dst]; lpApplicationName
0x140013d0f  call    cs:__imp_CreateProcessW
0x140013d16  nop     dword ptr [rax+rax+00h]
0x140013d1b  test    eax, eax
0x140013d1d  jnz     loc_140013DAB
0x140013d23  call    cs:__imp_GetLastError
0x140013d2a  nop     dword ptr [rax+rax+00h]
0x140013d2f  test    eax, eax
0x140013d31  mov     edi, eax
0x140013d33  jle     short loc_140013D3B
0x140013d35  movzx   edi, ax
0x140013d38  or      edi, r12d
0x140013d3b  mov     rax, cs:Feature_ConfigRefresh__descriptor
0x140013d42  mov     r8d, [rax]
0x140013d45  test    r14b, r8b
0x140013d48  jnz     short loc_140013D5F
0x140013d4a  lea     rdx, [rsp+0BA0h+var_B40]
0x140013d4f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ConfigRefresh@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(void)
0x140013d54  mov     rcx, [rax]
0x140013d57  mov     [rsp+0BA0h+var_B40], rcx
0x140013d5c  mov     r8d, ecx
0x140013d5f  mov     [rsp+0BA0h+var_B50], r15d
0x140013d64  mov     [rsp+0BA0h+var_B4C], 3
0x140013d6b  mov     r9d, r8d
0x140013d6e  shr     r9d, 0Bh
0x140013d72  and     r9d, r13d
0x140013d75  shr     r8d, 0Ah
0x140013d79  and     r8d, r13d
0x140013d7c  mov     [rsp+0BA0h+dwCreationFlags], r13d
0x140013d81  lea     rax, [rsp+0BA0h+var_B50]
0x140013d86  mov     qword ptr [rsp+0BA0h+bInheritHandles], rax
0x140013d8b  mov     edx, 29742D5h
0x140013d90  lea     rcx, qword_140024350
0x140013d97  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140013d9c  mov     rcx, [rsp+0BA0h+hObject]; hObject
0x140013da1  call    ?WaitForConfigRefreshSemaphore@@YAXPEAX@Z; WaitForConfigRefreshSemaphore(void *)
0x140013da6  jmp     loc_140013B91
0x140013dab  mov     rbx, [rbp+0AA0h+ProcessInformation.hProcess]
0x140013daf  mov     [rsp+0BA0h+var_B28], rbx
0x140013db4  mov     [rbp+0AA0h+ProcessInformation.hProcess], r15
0x140013db8  mov     edx, 5265C0h; dwMilliseconds
0x140013dbd  mov     rcx, rbx; hHandle
0x140013dc0  call    cs:__imp_WaitForSingleObject
0x140013dc7  nop     dword ptr [rax+rax+00h]
0x140013dcc  test    eax, eax
0x140013dce  jnz     loc_140013D23
0x140013dd4  mov     rax, cs:Feature_ConfigRefresh__descriptor
0x140013ddb  mov     r8d, [rax]
0x140013dde  test    r14b, r8b
0x140013de1  jnz     short loc_140013DF8
0x140013de3  lea     rdx, [rsp+0BA0h+var_B40]
0x140013de8  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ConfigRefresh@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(void)
0x140013ded  mov     rcx, [rax]
0x140013df0  mov     [rsp+0BA0h+var_B40], rcx
0x140013df5  mov     r8d, ecx
0x140013df8  mov     [rsp+0BA0h+var_B50], r15d
0x140013dfd  mov     [rsp+0BA0h+var_B4C], 3
0x140013e04  mov     r9d, r8d
0x140013e07  shr     r9d, 0Bh
0x140013e0b  and     r9d, r13d
0x140013e0e  shr     r8d, 0Ah
0x140013e12  and     r8d, r13d
0x140013e15  mov     [rsp+0BA0h+dwCreationFlags], r13d
0x140013e1a  lea     rax, [rsp+0BA0h+var_B50]
0x140013e1f  mov     qword ptr [rsp+0BA0h+bInheritHandles], rax
0x140013e24  mov     edx, 29742D5h
0x140013e29  lea     rcx, qword_140024350
0x140013e30  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140013e35  mov     rcx, [rsp+0BA0h+hObject]; hObject
0x140013e3a  call    ?WaitForConfigRefreshSemaphore@@YAXPEAX@Z; WaitForConfigRefreshSemaphore(void *)
0x140013e3f  lea     rdx, [rsp+0BA0h+ExitCode]; lpExitCode
0x140013e44  mov     rcx, rbx; hProcess
0x140013e47  call    cs:__imp_GetExitCodeProcess
0x140013e4e  nop     dword ptr [rax+rax+00h]
0x140013e53  test    eax, eax
0x140013e55  jnz     short loc_140013E77
0x140013e57  call    cs:__imp_GetLastError
0x140013e5e  nop     dword ptr [rax+rax+00h]
0x140013e63  mov     edi, eax
0x140013e65  test    eax, eax
0x140013e67  jle     short loc_140013E6F
0x140013e69  movzx   edi, ax
0x140013e6c  or      edi, r12d
0x140013e6f  test    edi, edi
0x140013e71  js      loc_140013B91
0x140013e77  lea     r9, [rsp+0BA0h+var_B38]
0x140013e7c  lea     r8, aSessionhresult; "SessionHRESULT"
0x140013e83  mov     rdx, [rsi+10h]
0x140013e87  mov     rcx, 0FFFFFFFF80000002h
0x140013e8e  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140013e95  nop     dword ptr [rax+rax+00h]
0x140013e9a  test    eax, eax
0x140013e9c  mov     eax, [rsp+0BA0h+ExitCode]
0x140013ea0  js      loc_140013B95
0x140013ea6  cmp     [rsp+0BA0h+var_B38], r15d
0x140013eab  jl      loc_140013B95
0x140013eb1  test    eax, eax
0x140013eb3  jg      short loc_140013EB9
0x140013eb5  mov     ecx, eax
0x140013eb7  jmp     short loc_140013EBF
0x140013eb9  movzx   ecx, ax
0x140013ebc  or      ecx, r12d
0x140013ebf  mov     [rsp+0BA0h+var_B38], ecx
0x140013ec3  jmp     loc_140013B95
0x140013ec8  movzx   edi, ax
0x140013ecb  or      edi, r12d
0x140013ece  mov     eax, cs:dword_140023000
0x140013ed4  cmp     eax, 5
0x140013ed7  jbe     short loc_140013F1C
0x140013ed9  movsxd  rax, edi
0x140013edc  mov     [rsp+0BA0h+var_B40], rax
0x140013ee1  lea     rax, [rsp+0BA0h+var_B40]
0x140013ee6  mov     [rbp+0AA0h+var_A70], rax
0x140013eea  mov     [rbp+0AA0h+var_A68], 8
0x140013ef2  lea     rax, [rbp+0AA0h+var_A90]
0x140013ef6  mov     qword ptr [rsp+0BA0h+dwCreationFlags], rax
0x140013efb  mov     [rsp+0BA0h+bInheritHandles], 3
0x140013f03  xor     r9d, r9d
0x140013f06  xor     r8d, r8d
0x140013f09  lea     rdx, byte_14001E235
0x140013f10  lea     rcx, dword_140023000
0x140013f17  call    _tlgWriteTransfer_EventWriteTransfer
0x140013f1c  mov     rcx, [rsi+10h]; lpSubKey
0x140013f20  test    rcx, rcx
0x140013f23  jnz     short loc_140013F2B
0x140013f25  lea     r14, [rsi+18h]
0x140013f29  jmp     short loc_140013F45
0x140013f2b  mov     edx, edi
0x140013f2d  call    NotifySessionResultRecovery
0x140013f32  lea     r14, [rsi+18h]
0x140013f36  mov     rcx, [r14]; lpSubKey
0x140013f39  test    rcx, rcx
0x140013f3c  jz      short loc_140013F45
0x140013f3e  mov     edx, edi
0x140013f40  call    NotifySessionResultRecovery
0x140013f45  mov     eax, [rsp+0BA0h+var_B38]
0x140013f49  mov     [rsi+2Ch], eax
0x140013f4c  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140013f51  mov     r10, rax
0x140013f54  mov     edx, [rsi+2Ch]
0x140013f57  cmp     cs:qword_140024308, r15
0x140013f5e  jz      short loc_140013F6F
0x140013f60  mov     ecx, r15d
0x140013f63  xor     eax, eax
0x140013f65  lock cmpxchg cs:?m_numberOfWorkQueued@ThreadpoolManager@@0JC, ecx; long volatile ThreadpoolManager::m_numberOfWorkQueued
0x140013f6d  jmp     short loc_140013F72
0x140013f6f  mov     eax, r15d
0x140013f72  mov     dword ptr [rsp+0BA0h+lpProcessInformation], edi; int
0x140013f76  mov     dword ptr [rsp+0BA0h+lpStartupInfo], edx; int
0x140013f7a  mov     dword ptr [rsp+0BA0h+lpCurrentDirectory], eax; unsigned int
0x140013f7e  mov     eax, [rsi+28h]
0x140013f81  mov     dword ptr [rsp+0BA0h+lpEnvironment], eax; unsigned int
0x140013f85  mov     eax, [rsi+24h]
0x140013f88  mov     [rsp+0BA0h+dwCreationFlags], eax; unsigned int
0x140013f8c  mov     rax, [r14]
0x140013f8f  mov     qword ptr [rsp+0BA0h+bInheritHandles], rax; unsigned __int16 *
0x140013f94  mov     r9, [rsi+10h]; unsigned __int16 *
0x140013f98  mov     r8, [rsi+8]; unsigned __int16 *
0x140013f9c  mov     rdx, [rsi]; unsigned __int16 *
0x140013f9f  mov     rcx, r10; this
0x140013fa2  call    ?LogOmaDmPrcSessionComplete@COmaDmPrcLogger@@QEAAXPEBG000KKKJJ@Z; COmaDmPrcLogger::LogOmaDmPrcSessionComplete(ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,ulong,long,long)
0x140013fa7  mov     [rsi], r15
0x140013faa  mov     [rsi+8], r15
0x140013fae  mov     [rsi+10h], r15
0x140013fb2  mov     [r14], r15
0x140013fb5  mov     rcx, rsi; this
  ... truncated ...
```
