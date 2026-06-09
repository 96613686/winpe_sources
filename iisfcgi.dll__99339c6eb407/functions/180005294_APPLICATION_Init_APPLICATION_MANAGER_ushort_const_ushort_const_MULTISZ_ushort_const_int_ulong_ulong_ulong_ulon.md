# APPLICATION::Init(APPLICATION_MANAGER *,ushort const *,ushort const *,MULTISZ *,ushort const *,int,ulong,ulong,ulong,ulong,ulong,int,int,ulong,ulong,uint *,FastCgiApplicationStdErrMode)

- ea: `0x180005294`
- end: `0x180005f46`
- name: `?Init@APPLICATION@@QEAAJPEAVAPPLICATION_MANAGER@@PEBG1PEAVMULTISZ@@1HKKKKKHHKKPEAIW4FastCgiApplicationStdErrMode@@@Z`
- size: `3250`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, const unsigned __int16 *, MULTISZ *, const WCHAR *, int, int, int, int, int, int, int, int, int, int, _DWORD *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007180`

## callees

- `0x180001008`
- `0x180001f84`
- `0x180002250`
- `0x1800022c8`
- `0x180003480`
- `0x180004ab8`
- `0x180005030`
- `0x180005294`
- `0x18000edde`
- `0x18000ee10`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005da3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005da3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005e4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005e4a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005991`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005991`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800054dc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800057f9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800054dc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800057f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ea3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ec0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ed0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ea3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ec0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ed0`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x180005ce3`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x180005ce3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005e7f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005e7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800058cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800058cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800058e2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800058e2`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180005b43`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180005b9d`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180005b43`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180005b9d`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180005c1c`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180005c1c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180005c9b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180005c9b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180005d41`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180005d41`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180005e57`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180005e57`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180005eb5`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180005eb5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800058ec`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800058ec`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x180005b02`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x180005b02`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180005dd6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180005dd6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180005e28`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180005e28`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x180005d02`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x180005d02`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000539b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000596d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005a61`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000539b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000596d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005a61`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800059bc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005a0d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005ac8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005efd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800059bc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005a0d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005ac8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005efd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005460`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000547a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005460`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000547a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800054a0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800054ba`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800054a0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800054ba`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005664`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005664`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180005f07`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180005f07`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005b72`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005b72`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180005309`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180005309`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180005f14`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180005f14`
- `iisutil!SAFE_snwprintf` at `0x180005445`
- `iisutil!SAFE_snwprintf` at `0x1800059d5`
- `iisutil!SAFE_snwprintf` at `0x180005a84`
- `iisutil!SAFE_snwprintf` at `0x180005445`
- `iisutil!SAFE_snwprintf` at `0x1800059d5`
- `iisutil!SAFE_snwprintf` at `0x180005a84`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800059e7`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180005a9a`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800059e7`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180005a9a`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180005ad5`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180005ae3`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180005c56`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180005ad5`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180005ae3`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180005c56`

## pseudocode

```c
__int64 __fastcall APPLICATION::Init(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        const unsigned __int16 *a4,
        MULTISZ *a5,
        const WCHAR *a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        int a14,
        int a15,
        int a16,
        _DWORD *a17,
        int a18)
{
  TRANSPORT *v22; // rsi
  BOOL v23; // eax
  signed int v24; // ebx
  signed int v25; // eax
  _QWORD *v26; // rax
  _QWORD *v27; // rcx
  _QWORD *v28; // rax
  _QWORD *v29; // rax
  _QWORD *v30; // rcx
  _QWORD *v31; // rax
  TRANSPORT *v32; // rax
  TRANSPORT *v33; // rax
  char *v34; // rax
  char *v35; // rdx
  __int64 v36; // rbx
  __int64 v37; // rax
  signed int LastError; // eax
  HANDLE CurrentThread; // rax
  HANDLE v40; // rax
  signed int v41; // eax
  APPLICATION *v42; // rcx
  __int64 v43; // rax
  APPLICATION *v44; // rcx
  MULTISZ *v45; // r14
  const unsigned __int16 *v46; // rax
  APPLICATION *v47; // rcx
  const unsigned __int16 *EnvironmentStringsW; // rax
  APPLICATION *v49; // rcx
  signed int v50; // eax
  signed int v51; // eax
  __int64 v52; // rax
  signed int v53; // eax
  unsigned __int16 *v54; // rax
  signed int v55; // eax
  signed int v56; // eax
  HANDLE hThread; // rcx
  __int64 v58; // rdx
  unsigned int v59; // eax
  void *v60; // rdx
  signed int v61; // eax
  signed int v62; // eax
  int v64; // [rsp+50h] [rbp-B0h]
  ULONG_PTR Size; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpApplicationName; // [rsp+88h] [rbp-78h]
  _DWORD *v70; // [rsp+90h] [rbp-70h]
  MULTISZ *v71; // [rsp+98h] [rbp-68h]
  LPCWSTR lpCurrentDirectory; // [rsp+A0h] [rbp-60h]
  HANDLE Value; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v74; // [rsp+B0h] [rbp-50h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+D0h] [rbp-30h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST v77; // [rsp+138h] [rbp+38h]
  _BYTE v78[32]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 *v79; // [rsp+160h] [rbp+60h]
  _BYTE v80[32]; // [rsp+178h] [rbp+78h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+198h] [rbp+98h]
  unsigned int v82; // [rsp+1A0h] [rbp+A0h]
  __int16 v83; // [rsp+1A4h] [rbp+A4h]
  _BYTE v84[56]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v85[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  LPWSTR lpCommandLine; // [rsp+200h] [rbp+100h]
  char v87; // [rsp+220h] [rbp+120h] BYREF
  char v88[255]; // [rsp+221h] [rbp+121h] BYREF
  unsigned __int16 v89[128]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v90[128]; // [rsp+420h] [rbp+320h] BYREF

  v71 = a5;
  lpCurrentDirectory = a6;
  lpApplicationName = a3;
  v70 = a17;
  hObject = 0;
  TokenHandle = 0;
  MULTISZ::MULTISZ((MULTISZ *)v84);
  *(_QWORD *)&StartupInfo.cb = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  memset_0(v88, 0, sizeof(v88));
  v87 = 0;
  v82 = 256;
  lpAttributeList = (LPPROC_THREAD_ATTRIBUTE_LIST)&v87;
  v83 = 256;
  v64 = 1;
  v22 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(v90, 0, sizeof(v90));
  STRU::STRU((STRU *)v85, v90, 0x80u);
  *a17 = 0;
  *(_DWORD *)(a1 + 288) = a8;
  *(_DWORD *)(a1 + 292) = a9;
  *(_DWORD *)(a1 + 296) = a10;
  *(_DWORD *)(a1 + 300) = a11;
  *(_DWORD *)(a1 + 304) = a12;
  v23 = a7 && a13;
  *(_DWORD *)(a1 + 268) = v23;
  *(_DWORD *)(a1 + 308) = a18;
  *(_DWORD *)(a1 + 272) = a14;
  *(_DWORD *)(a1 + 280) = a15;
  *(_DWORD *)(a1 + 284) = a16;
  v24 = SAFE_snwprintf((struct STRU *)v85, L"\"%s\"", a3);
  if ( v24 < 0 )
    goto LABEL_114;
  v24 = STRU::Copy((STRU *)(a1 + 312), lpApplicationName);
  if ( v24 < 0 )
    goto LABEL_114;
  v24 = STRU::Copy((STRU *)(a1 + 368), a4);
  if ( v24 < 0 )
    goto LABEL_114;
  if ( *a4 )
  {
    v24 = STRU::Append((STRU *)v85, L" ");
    if ( v24 < 0 )
      goto LABEL_114;
    v24 = STRU::Append((STRU *)v85, a4);
    if ( v24 < 0 )
      goto LABEL_114;
  }
  *(_QWORD *)(a1 + 96) = a2;
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(a1 + 112), 0x3E8u) )
    goto LABEL_12;
  *(_QWORD *)(a1 + 176) = a1 + 168;
  *(_QWORD *)(a1 + 168) = a1 + 168;
  *(_QWORD *)(a1 + 192) = a1 + 184;
  *(_QWORD *)(a1 + 184) = a1 + 184;
  *(_DWORD *)(a1 + 152) = 1;
  v26 = operator new(0x88u);
  v27 = v26;
  if ( v26 )
  {
    v26[2] = 0x1000000;
    *v26 = 0;
    v26[1] = 0;
    v26[10] = 0;
    v26[11] = 1;
    v26[12] = 0;
    v26[13] = 0;
    v26[14] = 0;
    *((_DWORD *)v26 + 30) = 0;
    v26[16] = 0;
    v28 = v26 + 3;
    v28[1] = v28;
    *v28 = v28;
    if ( *((_DWORD *)v27 + 4) >= 0x11800u )
    {
      if ( *((_DWORD *)v27 + 4) > 0x1000000u )
        *((_DWORD *)v27 + 4) = 16848896;
    }
    else
    {
      *((_DWORD *)v27 + 4) = 71680;
    }
  }
  else
  {
    v27 = 0;
  }
  *(_QWORD *)(a1 + 72) = v27;
  if ( !v27 )
    goto LABEL_113;
  *(_DWORD *)(a1 + 212) = 1;
  v29 = operator new(0x88u);
  v30 = v29;
  if ( v29 )
  {
    v29[2] = 0x80000;
    *v29 = 0;
    v29[1] = 0;
    v29[10] = 0;
    v29[11] = 1;
    v29[12] = 0;
    v29[13] = 0;
    v29[14] = 0;
    *((_DWORD *)v29 + 30) = 0;
    v29[16] = 0;
    v31 = v29 + 3;
    v31[1] = v31;
    *v31 = v31;
    if ( *((_DWORD *)v30 + 4) >= 0x11800u )
    {
      if ( *((_DWORD *)v30 + 4) > 0x1000000u )
        *((_DWORD *)v30 + 4) = 16848896;
    }
    else
    {
      *((_DWORD *)v30 + 4) = 71680;
    }
  }
  else
  {
    v30 = 0;
  }
  *(_QWORD *)(a1 + 64) = v30;
  if ( !v30 )
    goto LABEL_113;
  if ( a7 )
  {
    v32 = (TRANSPORT *)operator new(0xF8u);
    v22 = v32;
    if ( v32 )
    {
      TRANSPORT::TRANSPORT(v32, (struct DEBUG_LOG *)(a1 + 424));
      *(_QWORD *)v22 = &TRANSPORT_NAMEDPIPE::`vftable';
      STRU::STRU((TRANSPORT *)((char *)v22 + 160));
      *((_QWORD *)v22 + 27) = -1;
      *((_QWORD *)v22 + 28) = -1;
      *((_QWORD *)v22 + 29) = 0;
      *((_QWORD *)v22 + 30) = 0;
    }
    else
    {
      v22 = 0;
    }
    if ( !v22 )
      goto LABEL_113;
  }
  else
  {
    v33 = (TRANSPORT *)operator new(0xD0u);
    v22 = v33;
    if ( !v33 )
    {
      v22 = 0;
      goto LABEL_113;
    }
    TRANSPORT::TRANSPORT(v33, (struct DEBUG_LOG *)(a1 + 424));
    *((_QWORD *)v22 + 24) = 0;
    *((_QWORD *)v22 + 20) = -1;
    *(_QWORD *)v22 = &TRANSPORT_TCP::`vftable';
    *((_QWORD *)v22 + 21) = -1;
    *((_QWORD *)v22 + 25) = 0;
    *((_OWORD *)v22 + 11) = 0;
  }
  v34 = (char *)operator new(0xC8u);
  v35 = v34;
  if ( v34 )
  {
    *((_DWORD *)v34 + 6) = 1346847558;
    *(_QWORD *)v34 = &PROTOCOL::`vftable'{for `ITRANSPORT_CALLBACK'};
    *((_QWORD *)v34 + 1) = &PROTOCOL::`vftable'{for `ISEND_QUEUE_CONSUMER'};
    *((_QWORD *)v34 + 2) = &PROTOCOL::`vftable'{for `ISEND_QUEUE_PRODUCER'};
    *((_QWORD *)v34 + 4) = v22;
    *((_WORD *)v34 + 20) = 0;
    *(_QWORD *)(v34 + 44) = 0;
    *(_QWORD *)(v34 + 52) = 0;
    *((_DWORD *)v34 + 15) = 0;
    *((_QWORD *)v34 + 13) = 0;
    *((_DWORD *)v34 + 28) = 1;
    *((_QWORD *)v34 + 15) = 0;
    *((_QWORD *)v34 + 16) = 0;
    *((_QWORD *)v34 + 17) = 0x2000;
    *((_QWORD *)v34 + 18) = 0;
    *((_QWORD *)v34 + 19) = 0;
    *((_QWORD *)v34 + 20) = 0;
    *((_QWORD *)v34 + 21) = a1;
    *((_QWORD *)v34 + 22) = 0;
    *((_QWORD *)v34 + 23) = 0;
    *((_DWORD *)v34 + 48) = 0;
  }
  else
  {
    v35 = 0;
  }
  *(_QWORD *)(a1 + 80) = v35;
  if ( !v35 )
    goto LABEL_113;
  v64 = 0;
  v24 = (**(__int64 (__fastcall ***)(TRANSPORT *, char *, HANDLE *))v22)(v22, v35, &hObject);
  if ( v24 < 0 )
    goto LABEL_114;
  v36 = *(_QWORD *)(a1 + 80);
  v37 = *(_QWORD *)(a1 + 64);
  *(_QWORD *)(v36 + 184) = *(_QWORD *)(a1 + 72);
  *(_QWORD *)(v36 + 32) = v22;
  *(_QWORD *)(v36 + 176) = v37;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v36 + 64), 0x3E8u) )
  {
    *(_DWORD *)(v36 + 104) = 1;
    PROTOCOL::EndOfRequestCleanup((PROTOCOL *)v36);
  }
  else
  {
    LastError = GetLastError();
    v24 = LastError;
    if ( LastError > 0 )
      v24 = (unsigned __int16)LastError | 0x80070000;
    if ( v24 < 0 )
      goto LABEL_114;
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 156));
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 80) + 112LL));
  v24 = SEND_QUEUE::Init(
          *(SEND_QUEUE **)(a1 + 64),
          (struct ISEND_QUEUE_PRODUCER *)a1,
          (struct ISEND_QUEUE_CONSUMER *)((*(_QWORD *)(a1 + 80) + 8LL) & -(__int64)(*(_QWORD *)(a1 + 80) != 0)),
          0,
          0);
  if ( v24 < 0 )
    goto LABEL_114;
  SEND_QUEUE::StartSends(*(SEND_QUEUE **)(a1 + 64));
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 156));
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 80) + 112LL));
  v24 = SEND_QUEUE::Init(
          *(SEND_QUEUE **)(a1 + 72),
          (struct ISEND_QUEUE_PRODUCER *)((*(_QWORD *)(a1 + 80) + 16LL) & -(__int64)(*(_QWORD *)(a1 + 80) != 0)),
          (struct ISEND_QUEUE_CONSUMER *)((a1 + 8) & -(__int64)(a1 != 0)),
          1,
          0x100000u);
  if ( v24 < 0 )
    goto LABEL_114;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
  {
    if ( !RevertToSelf() )
    {
LABEL_12:
      v25 = GetLastError();
      v24 = v25;
      if ( v25 <= 0 )
        goto LABEL_114;
      goto LABEL_13;
    }
LABEL_54:
    StartupInfo.dwFlags = 256;
    StartupInfo.hStdInput = hObject;
    StartupInfo.cb = 112;
    StartupInfo.hStdOutput = (HANDLE)-1LL;
    StartupInfo.hStdError = (HANDLE)-1LL;
    if ( a12 )
    {
      memset(&EventAttributes, 0, sizeof(EventAttributes));
      memset_0(v89, 0, sizeof(v89));
      STRU::STRU((STRU *)v78, v89, 0x80u);
      EventAttributes.nLength = 24;
      EventAttributes.bInheritHandle = 1;
      v40 = CreateEventW(&EventAttributes, 1, 0, 0);
      *(_QWORD *)(a1 + 240) = v40;
      if ( !v40 )
      {
        v41 = GetLastError();
        v24 = v41;
        if ( v41 > 0 )
          v24 = (unsigned __int16)v41 | 0x80070000;
        goto LABEL_58;
      }
      v24 = SAFE_snwprintf((struct STRU *)v78, L"_FCGI_SHUTDOWN_EVENT_=%u", v40);
      if ( v24 < 0 )
        goto LABEL_58;
      v24 = STRU::Append((STRU *)v78, 0);
      if ( v24 < 0 )
        goto LABEL_58;
      v24 = APPLICATION::AddEnvironmentStrings(v42, (struct MULTISZ *)v84, v79);
      if ( v24 < 0 )
        goto LABEL_58;
      STRU::~STRU((STRU *)v78);
    }
    if ( !a7 || !(*(__int64 (__fastcall **)(TRANSPORT *))(*(_QWORD *)v22 + 32LL))(v22) )
    {
LABEL_69:
      v45 = v71;
      if ( MULTISZ::First(v71) )
      {
        v46 = MULTISZ::First(v45);
        v24 = APPLICATION::AddEnvironmentStrings(v47, (struct MULTISZ *)v84, v46);
        if ( v24 < 0 )
          goto LABEL_114;
      }
      EnvironmentStringsW = GetEnvironmentStringsW();
      if ( EnvironmentStringsW )
      {
        v24 = APPLICATION::AddEnvironmentStrings(v49, (struct MULTISZ *)v84, EnvironmentStringsW);
        if ( v24 < 0 )
          goto LABEL_114;
      }
      Size = v82;
      if ( InitializeProcThreadAttributeList(lpAttributeList, 1u, 0, &Size) )
        goto LABEL_81;
      v50 = GetLastError();
      v24 = v50;
      if ( v50 > 0 )
        v24 = (unsigned __int16)v50 | 0x80070000;
      if ( v24 != -2147024774 )
        goto LABEL_81;
      if ( BUFFER::Resize((BUFFER *)v80, Size) )
      {
        Size = v82;
        if ( InitializeProcThreadAttributeList(lpAttributeList, 1u, 0, &Size) )
        {
LABEL_82:
          Value = hObject;
          v52 = *(_QWORD *)(a1 + 240);
          v74 = 0;
          if ( v52 )
            v74 = v52;
          if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20002u, &Value, v52 != 0 ? 16LL : 8LL, 0, 0) )
            goto LABEL_85;
          v77 = lpAttributeList;
          v54 = (unsigned __int16 *)MULTISZ::First((MULTISZ *)v84);
          if ( !CreateProcessW(
                  lpApplicationName,
                  lpCommandLine,
                  0,
                  0,
                  1,
                  0x8040Cu,
                  v54,
                  lpCurrentDirectory,
                  &StartupInfo,
                  &ProcessInformation) )
          {
            v55 = GetLastError();
            v24 = v55;
            if ( v55 > 0 )
              v24 = (unsigned __int16)v55 | 0x80070000;
            if ( (unsigned int)(v24 + 2147024894) <= 1 )
              *v70 = 200000;
            goto LABEL_109;
          }
          if ( !SetHandleInformation(hObject, 1u, 0) )
            goto LABEL_85;
          if ( APPLICATION::sm_hJobObject
            && !AssignProcessToJobObject(APPLICATION::sm_hJobObject, ProcessInformation.hProcess) )
          {
            v56 = GetLastError();
            v24 = v56;
            if ( v56 > 0 )
              v24 = (unsigned __int16)v56 | 0x80070000;
            if ( v24 == -2147024891 )
              *v70 = 200002;
            goto LABEL_109;
          }
          if ( ResumeThread(ProcessInformation.hThread) == -1 )
          {
LABEL_85:
            v53 = GetLastError();
            v24 = v53;
            if ( v53 > 0 )
              v24 = (unsigned __int16)v53 | 0x80070000;
            goto LABEL_109;
          }
          hThread = ProcessInformation.hThread;
          *(_QWORD *)(a1 + 232) = ProcessInformation.hProcess;
          *(_DWORD *)(a1 + 252) = ProcessInformation.dwProcessId;
          CloseHandle(hThread);
          memset(&ProcessInformation, 0, sizeof(ProcessInformation));
          v24 = (*(__int64 (__fastcall **)(TRANSPORT *))(*(_QWORD *)v22 + 8LL))(v22);
          if ( v24 < 0 )
          {
LABEL_109:
            DeleteProcThreadAttributeList(lpAttributeList);
            goto LABEL_114;
          }
          v22 = 0;
          *(_DWORD *)(a1 + 44) = 0;
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
          _InterlockedAdd((volatile signed __int32 *)(a1 + 156), 1u);
          if ( RegisterWaitForSingleObject(
                 (PHANDLE)(a1 + 216),
                 *(HANDLE *)(a1 + 232),
                 APPLICATION::WaitOrTimerCallbackProcess,
                 (PVOID)a1,
                 0xFFFFFFFF,
                 8u) )
          {
            v58 = *(_QWORD *)(a1 + 96);
            v24 = 0;
            v59 = *(_DWORD *)(v58 + 456);
            v60 = *(void **)(v58 + 152);
            if ( v59 < 0xA )
              v59 = 10;
            if ( CreateTimerQueueTimer(
                   (PHANDLE)(a1 + 224),
                   v60,
                   APPLICATION::WaitOrTimerCallbackTimeout,
                   (PVOID)a1,
                   500 * v59,
                   500 * v59,
                   0) )
            {
              goto LABEL_108;
            }
          }
          else
          {
            APPLICATION::DereferenceApplication((APPLICATION *)a1);
          }
          v61 = GetLastError();
          v24 = v61;
          if ( v61 > 0 )
            v24 = (unsigned __int16)v61 | 0x80070000;
LABEL_108:
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
          goto LABEL_109;
        }
        v51 = GetLastError();
        v24 = v51;
        if ( v51 > 0 )
          v24 = (unsigned __int16)v51 | 0x80070000;
LABEL_81:
        if ( v24 < 0 )
          goto LABEL_114;
        goto LABEL_82;
      }
LABEL_113:
      v24 = -2147024882;
      goto LABEL_114;
    }
    memset_0(v89, 0, sizeof(v89));
    STRU::STRU((STRU *)v78, v89, 0x80u);
    v43 = (*(__int64 (__fastcall **)(TRANSPORT *))(*(_QWORD *)v22 + 32LL))(v22);
    v24 = SAFE_snwprintf((struct STRU *)v78, L"_FCGI_X_PIPE_=%s", v43);
    if ( v24 >= 0 )
    {
      v24 = STRU::Append((STRU *)v78, 0);
      if ( v24 >= 0 )
      {
        v24 = APPLICATION::AddEnvironmentStrings(v44, (struct MULTISZ *)v84, v79);
        if ( v24 >= 0 )
        {
          STRU::~STRU((STRU *)v78);
          goto LABEL_69;
        }
      }
    }
LABEL_58:
    STRU::~STRU((STRU *)v78);
    goto LABEL_114;
  }
  v25 = GetLastError();
  if ( v25 == 1008 )
  {
    TokenHandle = 0;
    goto LABEL_54;
  }
  if ( v25 > 0 )
  {
LABEL_13:
    v24 = (unsigned __int16)v25 | 0x80070000;
    goto LABEL_114;
  }
  v24 = v25;
LABEL_114:
  if ( TokenHandle )
  {
    if ( !SetThreadToken(0, TokenHandle) )
    {
      v62 = GetLastError();
      v24 = v62;
      if ( v62 > 0 )
        v24 = (unsigned __int16)v62 | 0x80070000;
    }
    CloseHandle(TokenHandle);
  }
  if ( ProcessInformation.hProcess )
  {
    TerminateProcess(ProcessInformation.hProcess, 0);
    CloseHandle(ProcessInformation.hProcess);
  }
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( v64 && v22 )
    (*(void (__fastcall **)(TRANSPORT *, __int64))(*(_QWORD *)v22 + 40LL))(v22, 1);
  STRU::~STRU((STRU *)v85);
  BUFFER::~BUFFER((BUFFER *)v80);
  MULTISZ::~MULTISZ((MULTISZ *)v84);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x180005294  mov     [rsp-8+arg_8], rbx
0x180005299  push    rbp
0x18000529a  push    rsi
0x18000529b  push    rdi
0x18000529c  push    r12
0x18000529e  push    r13
0x1800052a0  push    r14
0x1800052a2  push    r15
0x1800052a4  lea     rbp, [rsp-430h]
0x1800052ac  sub     rsp, 530h
0x1800052b3  mov     rax, cs:__security_cookie
0x1800052ba  xor     rax, rsp
0x1800052bd  mov     [rbp+460h+var_40], rax
0x1800052c4  mov     rax, [rbp+460h+arg_20]
0x1800052cb  mov     rbx, r8
0x1800052ce  mov     r12, [rbp+460h+arg_80]
0x1800052d5  mov     rdi, rcx
0x1800052d8  mov     [rbp+460h+var_4C8], rax
0x1800052dc  lea     rcx, [rbp+460h+var_3B8]
0x1800052e3  mov     rax, [rbp+460h+arg_28]
0x1800052ea  xor     r13d, r13d
0x1800052ed  mov     [rbp+460h+var_4C0], rax
0x1800052f1  mov     r14, r9
0x1800052f4  mov     [rbp+460h+lpApplicationName], rbx
0x1800052f8  mov     r15, rdx
0x1800052fb  mov     [rbp+460h+var_4D0], r12
0x1800052ff  mov     [rsp+560h+hObject], r13
0x180005304  mov     [rsp+560h+TokenHandle], r13
0x180005309  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18000530f  xor     edx, edx; Val
0x180005311  mov     qword ptr [rbp+460h+StartupInfo.cb], r13
0x180005315  lea     r8d, [r13+68h]; Size
0x180005319  lea     rcx, [rbp+460h+StartupInfo.lpReserved]; void *
0x18000531d  call    memset_0
0x180005322  xor     edx, edx; Val
0x180005324  lea     rcx, [rbp+460h+var_33F]; void *
0x18000532b  mov     r8d, 0FFh; Size
0x180005331  call    memset_0
0x180005336  mov     ecx, 100h
0x18000533b  mov     [rbp+460h+var_340], r13b
0x180005342  lea     rax, [rbp+460h+var_340]
0x180005349  mov     [rbp+460h+var_3C0], ecx
0x18000534f  mov     [rbp+460h+lpAttributeList], rax
0x180005356  xorps   xmm0, xmm0
0x180005359  xor     eax, eax
0x18000535b  mov     [rbp+460h+var_3BC], cx
0x180005362  mov     r8d, ecx; Size
0x180005365  mov     qword ptr [rbp+460h+ProcessInformation.dwProcessId], rax
0x180005369  xor     edx, edx; Val
0x18000536b  mov     [rsp+560h+var_510], 1
0x180005373  lea     rcx, [rbp+460h+var_140]; void *
0x18000537a  mov     esi, r13d
0x18000537d  movups  xmmword ptr [rsp+560h+ProcessInformation.hProcess], xmm0
0x180005382  call    memset_0
0x180005387  mov     r8d, 80h
0x18000538d  lea     rdx, [rbp+460h+var_140]
0x180005394  lea     rcx, [rbp+460h+var_380]
0x18000539b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800053a1  mov     eax, [rbp+460h+arg_38]
0x1800053a7  mov     [r12], r13d
0x1800053ab  mov     r12d, [rbp+460h+arg_30]
0x1800053b2  mov     r13d, [rbp+460h+arg_58]
0x1800053b9  mov     [rdi+120h], eax
0x1800053bf  mov     eax, [rbp+460h+arg_40]
0x1800053c5  mov     [rdi+124h], eax
0x1800053cb  mov     eax, [rbp+460h+arg_48]
0x1800053d1  mov     [rdi+128h], eax
0x1800053d7  mov     eax, [rbp+460h+arg_50]
0x1800053dd  mov     [rdi+12Ch], eax
0x1800053e3  mov     [rdi+130h], r13d
0x1800053ea  test    r12d, r12d
0x1800053ed  jz      short loc_1800053FC
0x1800053ef  cmp     [rbp+460h+arg_60], esi
0x1800053f5  jz      short loc_1800053FC
0x1800053f7  lea     eax, [rsi+1]
0x1800053fa  jmp     short loc_1800053FE
0x1800053fc  xor     eax, eax
0x1800053fe  mov     [rdi+10Ch], eax
0x180005404  lea     rdx, aS; "\"%s\""
0x18000540b  mov     eax, [rbp+460h+arg_88]
0x180005411  lea     rcx, [rbp+460h+var_380]
0x180005418  mov     [rdi+134h], eax
0x18000541e  mov     r8, rbx
0x180005421  mov     eax, [rbp+460h+arg_68]
0x180005427  mov     [rdi+110h], eax
0x18000542d  mov     eax, [rbp+460h+arg_70]
0x180005433  mov     [rdi+118h], eax
0x180005439  mov     eax, [rbp+460h+arg_78]
0x18000543f  mov     [rdi+11Ch], eax
0x180005445  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x18000544b  mov     ebx, eax
0x18000544d  test    eax, eax
0x18000544f  js      loc_180005E73
0x180005455  mov     rdx, [rbp+460h+lpApplicationName]
0x180005459  lea     rcx, [rdi+138h]
0x180005460  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180005466  mov     ebx, eax
0x180005468  test    eax, eax
0x18000546a  js      loc_180005E73
0x180005470  lea     rcx, [rdi+170h]
0x180005477  mov     rdx, r14
0x18000547a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180005480  mov     ebx, eax
0x180005482  test    eax, eax
0x180005484  js      loc_180005E73
0x18000548a  xor     ebx, ebx
0x18000548c  cmp     bx, [r14]
0x180005490  jz      short loc_1800054CC
0x180005492  lea     rdx, asc_180011F64; " "
0x180005499  lea     rcx, [rbp+460h+var_380]
0x1800054a0  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800054a6  mov     ebx, eax
0x1800054a8  test    eax, eax
0x1800054aa  js      loc_180005E73
0x1800054b0  mov     rdx, r14
0x1800054b3  lea     rcx, [rbp+460h+var_380]
0x1800054ba  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800054c0  mov     ebx, eax
0x1800054c2  test    eax, eax
0x1800054c4  js      loc_180005E73
0x1800054ca  xor     ebx, ebx
0x1800054cc  mov     [rdi+60h], r15
0x1800054d0  mov     edx, 3E8h; dwSpinCount
0x1800054d5  lea     r15, [rdi+70h]
0x1800054d9  mov     rcx, r15; lpCriticalSection
0x1800054dc  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800054e2  test    eax, eax
0x1800054e4  jnz     short loc_180005504
0x1800054e6  call    cs:__imp_GetLastError
0x1800054ec  mov     ebx, eax
0x1800054ee  test    eax, eax
0x1800054f0  jle     loc_180005E73
0x1800054f6  movzx   ebx, ax
0x1800054f9  or      ebx, 80070000h
0x1800054ff  jmp     loc_180005E73
0x180005504  lea     rax, [rdi+0A8h]
0x18000550b  mov     r14d, 1
0x180005511  mov     [rax+8], rax
0x180005515  mov     ecx, 88h; Size
0x18000551a  mov     [rax], rax
0x18000551d  lea     rax, [rdi+0B8h]
0x180005524  mov     [rax+8], rax
0x180005528  mov     [rax], rax
0x18000552b  mov     [rdi+98h], r14d
0x180005532  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005537  mov     rcx, rax
0x18000553a  mov     edx, 11800h
0x18000553f  mov     r8d, 1000000h
0x180005545  test    rax, rax
0x180005548  jz      short loc_180005597
0x18000554a  mov     [rax+10h], r8
0x18000554e  mov     [rax], rbx
0x180005551  mov     [rax+8], rbx
0x180005555  mov     [rax+50h], rsi
0x180005559  mov     [rax+58h], r14
0x18000555d  mov     [rax+60h], rsi
0x180005561  mov     [rax+68h], rsi
0x180005565  mov     [rax+70h], rsi
0x180005569  mov     [rax+78h], ebx
0x18000556c  mov     [rax+80h], rbx
0x180005573  add     rax, 18h
0x180005577  mov     [rax+8], rax
0x18000557b  mov     [rax], rax
0x18000557e  cmp     [rcx+10h], edx
0x180005581  jnb     short loc_180005588
0x180005583  mov     [rcx+10h], edx
0x180005586  jmp     short loc_18000559A
0x180005588  cmp     [rcx+10h], r8d
0x18000558c  jbe     short loc_18000559A
0x18000558e  mov     dword ptr [rcx+10h], 1011800h
0x180005595  jmp     short loc_18000559A
0x180005597  mov     rcx, rbx
0x18000559a  mov     [rdi+48h], rcx
0x18000559e  test    rcx, rcx
0x1800055a1  jz      loc_180005E6E
0x1800055a7  mov     ecx, 88h; Size
0x1800055ac  mov     [rdi+0D4h], r14d
0x1800055b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800055b8  mov     rcx, rax
0x1800055bb  test    rax, rax
0x1800055be  jz      short loc_180005619
0x1800055c0  mov     qword ptr [rax+10h], 80000h
0x1800055c8  mov     [rax], rbx
0x1800055cb  mov     [rax+8], rbx
0x1800055cf  mov     [rax+50h], rsi
0x1800055d3  mov     [rax+58h], r14
0x1800055d7  mov     [rax+60h], rsi
0x1800055db  mov     [rax+68h], rsi
0x1800055df  mov     [rax+70h], rsi
0x1800055e3  mov     [rax+78h], ebx
0x1800055e6  mov     [rax+80h], rbx
0x1800055ed  add     rax, 18h
0x1800055f1  mov     [rax+8], rax
0x1800055f5  mov     [rax], rax
0x1800055f8  mov     eax, 11800h
0x1800055fd  cmp     [rcx+10h], eax
0x180005600  jnb     short loc_180005607
0x180005602  mov     [rcx+10h], eax
0x180005605  jmp     short loc_18000561C
0x180005607  cmp     dword ptr [rcx+10h], 1000000h
0x18000560e  jbe     short loc_18000561C
0x180005610  mov     dword ptr [rcx+10h], 1011800h
0x180005617  jmp     short loc_18000561C
0x180005619  mov     rcx, rbx
0x18000561c  mov     [rdi+40h], rcx
0x180005620  test    rcx, rcx
0x180005623  jz      loc_180005E6E
0x180005629  test    r12d, r12d
0x18000562c  jz      short loc_180005695
0x18000562e  mov     ecx, 0F8h; Size
0x180005633  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005638  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000563c  mov     rsi, rax
0x18000563f  test    rax, rax
0x180005642  jz      short loc_180005688
0x180005644  lea     rdx, [rdi+1A8h]; struct DEBUG_LOG *
0x18000564b  mov     rcx, rax; this
0x18000564e  call    ??0TRANSPORT@@QEAA@PEAVDEBUG_LOG@@@Z; TRANSPORT::TRANSPORT(DEBUG_LOG *)
0x180005653  lea     rax, ??_7TRANSPORT_NAMEDPIPE@@6B@; const TRANSPORT_NAMEDPIPE::`vftable'
0x18000565a  lea     rcx, [rsi+0A0h]
0x180005661  mov     [rsi], rax
0x180005664  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000566a  mov     [rsi+0D8h], r14
0x180005671  mov     [rsi+0E0h], r14
0x180005678  mov     [rsi+0E8h], rbx
0x18000567f  mov     [rsi+0F0h], rbx
0x180005686  jmp     short loc_18000568B
0x180005688  mov     rsi, rbx
0x18000568b  test    rsi, rsi
0x18000568e  jnz     short loc_1800056EE
0x180005690  jmp     loc_180005E6E
0x180005695  mov     ecx, 0D0h; Size
0x18000569a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000569f  mov     rsi, rax
0x1800056a2  test    rax, rax
0x1800056a5  jz      loc_180005E6B
0x1800056ab  lea     rdx, [rdi+1A8h]; struct DEBUG_LOG *
0x1800056b2  mov     rcx, rax; this
0x1800056b5  call    ??0TRANSPORT@@QEAA@PEAVDEBUG_LOG@@@Z; TRANSPORT::TRANSPORT(DEBUG_LOG *)
0x1800056ba  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800056be  mov     [rsi+0C0h], rbx
0x1800056c5  lea     rax, ??_7TRANSPORT_TCP@@6B@; const TRANSPORT_TCP::`vftable'
0x1800056cc  mov     [rsi+0A0h], r14
0x1800056d3  xorps   xmm0, xmm0
0x1800056d6  mov     [rsi], rax
0x1800056d9  mov     [rsi+0A8h], r14
0x1800056e0  mov     [rsi+0C8h], rbx
0x1800056e7  movups  xmmword ptr [rsi+0B0h], xmm0
0x1800056ee  mov     ecx, 0C8h; Size
0x1800056f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800056f8  mov     rdx, rax
0x1800056fb  test    rax, rax
0x1800056fe  jz      loc_1800057A1
0x180005704  lea     rax, ??_7PROTOCOL@@6BITRANSPORT_CALLBACK@@@; const PROTOCOL::`vftable'{for `ITRANSPORT_CALLBACK'}
0x18000570b  mov     dword ptr [rdx+18h], 50474346h
0x180005712  mov     [rdx], rax
0x180005715  lea     rax, ??_7PROTOCOL@@6BISEND_QUEUE_CONSUMER@@@; const PROTOCOL::`vftable'{for `ISEND_QUEUE_CONSUMER'}
0x18000571c  mov     [rdx+8], rax
0x180005720  lea     rax, ??_7PROTOCOL@@6BISEND_QUEUE_PRODUCER@@@; const PROTOCOL::`vftable'{for `ISEND_QUEUE_PRODUCER'}
0x180005727  mov     [rdx+10h], rax
0x18000572b  mov     [rdx+20h], rsi
0x18000572f  mov     [rdx+28h], bx
0x180005733  mov     qword ptr [rdx+2Ch], 0
0x18000573b  mov     qword ptr [rdx+34h], 0
0x180005743  mov     [rdx+3Ch], ebx
0x180005746  mov     qword ptr [rdx+68h], 0
0x18000574e  mov     dword ptr [rdx+70h], 1
0x180005755  mov     [rdx+78h], rbx
0x180005759  mov     [rdx+80h], rbx
0x180005760  mov     qword ptr [rdx+88h], 2000h
0x18000576b  mov     [rdx+90h], rbx
0x180005772  mov     [rdx+98h], rbx
0x180005779  mov     qword ptr [rdx+0A0h], 0
0x180005784  mov     [rdx+0A8h], rdi
0x18000578b  mov     [rdx+0B0h], rbx
0x180005792  mov     [rdx+0B8h], rbx
0x180005799  mov     [rdx+0C0h], ebx
0x18000579f  jmp     short loc_1800057A4
0x1800057a1  mov     rdx, rbx
0x1800057a4  mov     [rdi+50h], rdx
0x1800057a8  test    rdx, rdx
0x1800057ab  jz      loc_180005E6E
0x1800057b1  mov     rax, [rsi]
0x1800057b4  lea     r8, [rsp+560h+hObject]
0x1800057b9  mov     rcx, rsi
0x1800057bc  mov     [rsp+560h+var_510], ebx
0x1800057c0  mov     rax, [rax]
0x1800057c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057c8  mov     ebx, eax
0x1800057ca  test    eax, eax
0x1800057cc  js      loc_180005E73
0x1800057d2  mov     rbx, [rdi+50h]
0x1800057d6  mov     edx, 3E8h; dwSpinCount
0x1800057db  mov     rcx, [rdi+48h]
0x1800057df  mov     rax, [rdi+40h]
0x1800057e3  mov     [rbx+0B8h], rcx
0x1800057ea  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800057ee  mov     [rbx+20h], rsi
0x1800057f2  mov     [rbx+0B0h], rax
0x1800057f9  call    cs:__imp_InitializeCriticalSectionAndSpinCount
  ... truncated ...
```
