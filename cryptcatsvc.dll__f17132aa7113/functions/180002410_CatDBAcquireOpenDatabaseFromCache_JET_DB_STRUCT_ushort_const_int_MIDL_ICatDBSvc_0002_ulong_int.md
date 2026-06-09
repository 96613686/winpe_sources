# _CatDBAcquireOpenDatabaseFromCache(_JET_DB_STRUCT * *,ushort const *,int,__MIDL_ICatDBSvc_0002,ulong,int)

- ea: `0x180002410`
- end: `0x180002b85`
- name: `?_CatDBAcquireOpenDatabaseFromCache@@YAHPEAPEAU_JET_DB_STRUCT@@PEBGHW4__MIDL_ICatDBSvc_0002@@KH@Z`
- size: `1909`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `4`
- callee_count: `19`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180001ce0`
- `0x180017a04`
- `0x180019314`
- `0x18001c03c`

## callees

- `0x180001328`
- `0x180002410`
- `0x180002b90`
- `0x180002fd0`
- `0x180003538`
- `0x1800038f0`
- `0x180003d48`
- `0x180004170`
- `0x18000a59c`
- `0x18000aba4`
- `0x18000acbc`
- `0x18000be40`
- `0x18000c7e8`
- `0x1800187ec`
- `0x180019a7c`
- `0x18001a230`
- `0x18001c6b4`
- `0x18001f6b8`
- `0x18001f968`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800024d7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800024d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800024a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800024a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002552`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002552`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000247c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000247c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002827`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002827`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002b6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002b6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002509`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002509`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000259e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002807`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000259e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002807`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002af5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002712`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002a9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002b7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002712`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002a9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002b7a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800028bc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800028bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000270a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000270a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002919`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002947`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002919`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002947`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180002901`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180002901`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000292b`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000292b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000297f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000297f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800028ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800028ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800025c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800025c0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800026b3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800026eb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800026b3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800026eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800026c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800026c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800026fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000287f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002988`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002b29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002b38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002b41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800026fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000287f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002988`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002b29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002b38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002b41`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatA` at `0x1800025ea`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatA` at `0x1800025ea`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatA` at `0x18000262d`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatA` at `0x18000262d`
- `ESENT!JetBeginSessionW` at `0x1800027bc`
- `ESENT!JetBeginSessionW` at `0x1800027bc`
- `ESENT!JetEndSession` at `0x18000281c`
- `ESENT!JetEndSession` at `0x18000281c`

## pseudocode

```c
__int64 __fastcall _CatDBAcquireOpenDatabaseFromCache(
        WCHAR **a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        DWORD a5,
        int a6)
{
  int v7; // r12d
  unsigned int v11; // edx
  unsigned __int16 *v12; // rcx
  _QWORD *i; // rdi
  __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // ebx
  int v18; // edi
  int LastError; // ebx
  int TimeFormatA; // eax
  const char *v21; // r8
  int v22; // eax
  DWORD v23; // eax
  DWORD v24; // r13d
  WCHAR *v25; // rax
  WCHAR *v26; // r12
  __int64 v27; // r14
  __int64 v28; // r15
  unsigned __int16 *v29; // r15
  WCHAR *v30; // rax
  unsigned int v31; // edx
  unsigned __int16 *v32; // rcx
  WCHAR *v33; // rdi
  __int64 v34; // rax
  unsigned __int16 *v35; // rax
  unsigned int v36; // edx
  unsigned __int16 *v37; // rcx
  const unsigned __int16 *v38; // rax
  unsigned int v39; // edx
  unsigned __int16 *v40; // rcx
  unsigned int v41; // r8d
  WCHAR *v42; // rbx
  unsigned __int16 *v43; // rax
  unsigned int v44; // edx
  unsigned __int16 *v45; // rcx
  HANDLE FileW; // rax
  unsigned int v47; // edx
  unsigned __int16 *v48; // rcx
  unsigned int v49; // r8d
  unsigned int v50; // r8d
  DWORD v51; // eax
  DWORD v52; // eax
  const unsigned __int16 *v53; // rcx
  unsigned int v54; // eax
  void *v55; // rcx
  int cchTime; // [rsp+28h] [rbp-3A0h]
  __int64 cchTimea; // [rsp+28h] [rbp-3A0h]
  int hTemplateFile; // [rsp+30h] [rbp-398h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-388h] BYREF
  unsigned __int16 *v60; // [rsp+48h] [rbp-380h]
  LPCWSTR lpSrc; // [rsp+50h] [rbp-378h]
  _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-370h] BYREF
  CHAR TimeStr[256]; // [rsp+70h] [rbp-358h] BYREF
  CHAR OutputString[512]; // [rsp+170h] [rbp-258h] BYREF

  v7 = 0;
  v60 = 0;
  if ( !a6 )
  {
    if ( a3 )
      AcquireSRWLockShared(&g_CatDirCashSRW);
    else
      AcquireSRWLockExclusive(&g_CatDirCashSRW);
    v7 = _CatDBOpenJet(a3, a5);
    if ( !v7 )
    {
      v18 = 0;
      SystemTime = 0;
      LastError = GetLastError();
      if ( !g_fErrLogInitialized )
        ErrLog_Initialize();
      GetLocalTime(&SystemTime);
      TimeFormatA = GetTimeFormatA(0x400u, 0, &SystemTime, 0, TimeStr, 256);
      if ( (unsigned int)(TimeFormatA - 1) <= 0xFF )
      {
        TimeStr[TimeFormatA - 1] = 32;
        GetDateFormatA(0x400u, 1u, &SystemTime, 0, &TimeStr[TimeFormatA], 256 - TimeFormatA);
        if ( (LastError & 0x1FFF0000) == 0xE5E0000 )
        {
          v21 = "CatalogDB: %s: %s at line #%u encountered JET error %d\r\n";
          v22 = -(unsigned __int16)LastError;
          if ( LastError >= 0 )
            v22 = (unsigned __int16)LastError;
          hTemplateFile = v22;
        }
        else
        {
          hTemplateFile = LastError;
          v21 = "CatalogDB: %s: %s at line #%u encountered error 0x%.8lx\r\n";
        }
        LODWORD(cchTimea) = 4327;
        StringCchPrintfA(OutputString, 0x200u, v21, TimeStr, "catdbsvc.cpp", cchTimea, hTemplateFile);
        NumberOfBytesWritten = 0;
        if ( g_fLogErrorsToDebugger )
          OutputDebugStringA(OutputString);
        if ( g_fLogErrorsToFile )
        {
          lpSrc = ::lpSrc;
          v23 = ExpandEnvironmentStringsW(::lpSrc, 0, 0);
          v24 = v23;
          if ( v23 )
          {
            v25 = (WCHAR *)LocalAlloc(0, 2LL * v23);
            v26 = v25;
            if ( v25 )
            {
              v27 = -1;
              v28 = -1;
              if ( !ExpandEnvironmentStringsW(lpSrc, v25, v24)
                || (FileW = CreateFileW(v26, 0xC0000000, 0, 0, 4u, 0x80u, 0), v28 = (__int64)FileW,
                                                                              FileW == (HANDLE)-1LL)
                || GetFileSize(FileW, 0) >= 0x30D40
                && (SetFilePointer((HANDLE)v28, 0, 0, 0) == -1 || !SetEndOfFile((HANDLE)v28))
                || SetFilePointer((HANDLE)v28, 0, 0, 2u) == -1 )
              {
                LocalFree(v26);
                if ( v28 == -1 )
                  goto LABEL_37;
              }
              else
              {
                do
                  ++v27;
                while ( OutputString[v27] );
                WriteFile((HANDLE)v28, OutputString, v27, &NumberOfBytesWritten, 0);
                LocalFree(v26);
              }
              CloseHandle((HANDLE)v28);
            }
          }
        }
      }
LABEL_37:
      SetLastError(LastError);
LABEL_38:
      NumberOfBytesWritten = GetLastError();
      v29 = 0;
      goto LABEL_55;
    }
  }
  EnterCriticalSection(&g_CatDirCashCS);
  for ( i = (_QWORD *)g_CatalogDBCacheList; ; i = (_QWORD *)*i )
  {
    if ( !i )
      goto LABEL_39;
    v14 = i[1];
    v15 = *(_DWORD *)(v14 + 100);
    if ( v15 == 2 || v15 == a4 )
      break;
LABEL_20:
    if ( !a3 && *(_DWORD *)(v14 + 104) )
      goto LABEL_69;
  }
  if ( a3 || !*(_DWORD *)(v14 + 104) )
  {
    if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)(v14 + 88), a2)
      && !_InterlockedExchange((volatile __int32 *)(v14 + 96), 1) )
    {
      *a1 = (WCHAR *)v14;
      v16 = 1;
      NumberOfBytesWritten = 0;
      goto LABEL_12;
    }
    goto LABEL_20;
  }
LABEL_69:
  if ( a6 )
  {
    v18 = 1;
    ErrLog_LogError(v12, v11, 0x110Cu, 0x8000FFFF, 0, cchTime);
    v29 = v60;
    NumberOfBytesWritten = GetLastError();
    goto LABEL_53;
  }
  LeaveCriticalSection(&g_CatDirCashCS);
  v18 = 0;
  _CatDBCloseJet(0);
  if ( !(unsigned int)CatDBFreezeJet(0) )
  {
    v49 = 4396;
LABEL_77:
    ErrLog_LogError(v48, v47, v49, 0, 0, cchTime);
    goto LABEL_38;
  }
  if ( !(unsigned int)CatDBThawJet(0) )
  {
    v49 = 4402;
    goto LABEL_77;
  }
  v7 = _CatDBOpenJet(0, a5);
  if ( !v7 )
  {
    v49 = 4409;
    goto LABEL_77;
  }
  EnterCriticalSection(&g_CatDirCashCS);
LABEL_39:
  NumberOfBytesWritten = 0;
  v16 = 1;
  v30 = (WCHAR *)_CatDBAlloc(0x70u);
  lpSrc = v30;
  v33 = v30;
  if ( !v30 )
  {
    ErrLog_LogError(v32, v31, 0x1147u, 0, 0, cchTime);
    v18 = 1;
    v29 = v60;
    NumberOfBytesWritten = GetLastError();
    goto LABEL_53;
  }
  memset_0(v30, 0, 0x58u);
  v34 = -1;
  *((_DWORD *)v33 + 24) = 1;
  *((_DWORD *)v33 + 25) = a4;
  *((_DWORD *)v33 + 26) = a3;
  do
    ++v34;
  while ( a2[v34] );
  *(_QWORD *)&SystemTime.wYear = (unsigned int)(v34 + 1);
  v35 = (unsigned __int16 *)_CatDBAlloc(2LL * *(unsigned int *)&SystemTime.wYear);
  *((_QWORD *)v33 + 11) = v35;
  if ( !v35 )
  {
    v50 = 4440;
LABEL_82:
    ErrLog_LogError(v37, v36, v50, 0, 0, cchTime);
    v18 = 1;
    v29 = v60;
    NumberOfBytesWritten = GetLastError();
    goto LABEL_86;
  }
  StringCchCopyW(v35, *(unsigned __int64 *)&SystemTime.wYear, a2);
  *(_DWORD *)&SystemTime.wYear = JetBeginSessionW(g_JetInstance, (JET_SESID *)v33 + 1, 0, 0);
  if ( (unsigned int)_CatDBJET_errFailure(*(int *)&SystemTime.wYear) )
  {
    v51 = _CatDBMapJetError(*(int *)&SystemTime.wYear);
    SetLastError(v51);
    v50 = 4457;
    goto LABEL_82;
  }
  v38 = _CATDBConstructWSTRPath(g_pwszDatabaseFileBaseDirectory, a2);
  v29 = (unsigned __int16 *)v38;
  if ( !v38 )
  {
    v41 = 4463;
    goto LABEL_46;
  }
  v43 = _CATDBConstructWSTRPath(v38, L"catdb");
  *(_QWORD *)v33 = v43;
  if ( !v43 )
  {
    v41 = 4470;
LABEL_46:
    ErrLog_LogError(v40, v39, v41, 0, 0, cchTime);
    v18 = 1;
    v42 = (WCHAR *)lpSrc;
    NumberOfBytesWritten = GetLastError();
    JetEndSession(*((_QWORD *)lpSrc + 1), 0);
    goto LABEL_87;
  }
  if ( !(unsigned int)_CatDBAttachAndOpenDatabase(v33, a3, a4) )
  {
    v41 = 4479;
    goto LABEL_46;
  }
  if ( LIST_AddTail(v40, v33) )
  {
    *a1 = v33;
    v18 = 1;
    goto LABEL_52;
  }
  ErrLog_LogError(v45, v44, 0x1189u, 0, 0, cchTime);
  v52 = GetLastError();
  v53 = (const unsigned __int16 *)*((_QWORD *)v33 + 11);
  NumberOfBytesWritten = v52;
  v54 = _CatDBInstanceCount(v53);
  _CatDBCloseDatabaseFile((struct _JET_DB_STRUCT *)v33, v54 == 0);
  v18 = 1;
LABEL_86:
  v42 = (WCHAR *)lpSrc;
LABEL_87:
  if ( *(_QWORD *)v42 )
    LocalFree(*(HLOCAL *)v42);
  v55 = (void *)*((_QWORD *)v42 + 11);
  if ( v55 )
    LocalFree(v55);
  LocalFree(v42);
LABEL_53:
  if ( v7 )
  {
    LeaveCriticalSection(&g_CatDirCashCS);
    v18 = 0;
    _CatDBCloseJet(a3);
  }
LABEL_55:
  v16 = 0;
  if ( v29 )
LABEL_52:
    LocalFree(v29);
  if ( v18 )
LABEL_12:
    LeaveCriticalSection(&g_CatDirCashCS);
  if ( !a6 )
  {
    if ( a3 )
      ReleaseSRWLockShared(&g_CatDirCashSRW);
    else
      ReleaseSRWLockExclusive(&g_CatDirCashSRW);
  }
  if ( !v16 )
    SetLastError(NumberOfBytesWritten);
  return v16;
}

```

## disassembly

```asm
0x180002410  mov     r11, rsp
0x180002413  push    rbx
0x180002414  sub     rsp, 3C0h
0x18000241b  mov     rax, cs:__security_cookie
0x180002422  xor     rax, rsp
0x180002425  mov     [rsp+3C8h+var_58], rax
0x18000242d  mov     [r11-10h], rbp
0x180002431  mov     ebp, [rsp+3C8h+arg_28]
0x180002438  mov     [r11-18h], rsi
0x18000243c  mov     esi, r8d
0x18000243f  mov     [r11-20h], rdi
0x180002443  mov     [r11-28h], r12
0x180002447  xor     r12d, r12d
0x18000244a  mov     [r11-30h], r13
0x18000244e  mov     r13, rcx
0x180002451  mov     [r11-38h], r14
0x180002455  mov     r14d, r9d
0x180002458  mov     [r11-40h], r15
0x18000245c  mov     r15, rdx
0x18000245f  mov     [rsp+3C8h+var_380], 0
0x180002468  test    ebp, ebp
0x18000246a  jnz     short loc_18000249B
0x18000246c  lea     rcx, ?g_CatDirCashSRW@@3U_RTL_SRWLOCK@@A; SRWLock
0x180002473  test    r8d, r8d
0x180002476  jz      loc_180002827
0x18000247c  call    cs:__imp_AcquireSRWLockShared
0x180002482  mov     edx, [rsp+3C8h+arg_20]; unsigned int
0x180002489  mov     ecx, esi; int
0x18000248b  call    ?_CatDBOpenJet@@YAHHK@Z; _CatDBOpenJet(int,ulong)
0x180002490  mov     r12d, eax
0x180002493  test    eax, eax
0x180002495  jz      loc_18000259C
0x18000249b  lea     rcx, ?g_CatDirCashCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800024a2  call    cs:__imp_EnterCriticalSection
0x1800024a8  mov     rdi, qword ptr cs:?g_CatalogDBCacheList@@3ULIST_@@A; LIST_ g_CatalogDBCacheList
0x1800024af  test    rdi, rdi
0x1800024b2  jz      loc_18000272A
0x1800024b8  mov     rbx, [rdi+8]
0x1800024bc  mov     eax, [rbx+64h]
0x1800024bf  cmp     eax, 2
0x1800024c2  jnz     loc_180002583
0x1800024c8  test    esi, esi
0x1800024ca  jz      loc_180002993
0x1800024d0  mov     rcx, [rbx+58h]
0x1800024d4  mov     rdx, r15
0x1800024d7  call    cs:__imp__o__wcsicmp
0x1800024dd  test    eax, eax
0x1800024df  jnz     loc_18000258C
0x1800024e5  mov     eax, 1
0x1800024ea  xchg    eax, [rbx+60h]
0x1800024ed  test    eax, eax
0x1800024ef  jnz     loc_18000258C
0x1800024f5  mov     [r13+0], rbx
0x1800024f9  mov     ebx, 1
0x1800024fe  mov     [rsp+3C8h+NumberOfBytesWritten], eax
0x180002502  lea     rcx, ?g_CatDirCashCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002509  call    cs:__imp_LeaveCriticalSection
0x18000250f  mov     r15, [rsp+3C8h+var_40]
0x180002517  test    ebp, ebp
0x180002519  mov     rbp, [rsp+3C8h+var_10]
0x180002521  mov     r14, [rsp+3C8h+var_38]
0x180002529  mov     r13, [rsp+3C8h+var_30]
0x180002531  mov     r12, [rsp+3C8h+var_28]
0x180002539  mov     rdi, [rsp+3C8h+var_20]
0x180002541  jnz     short loc_180002558
0x180002543  lea     rcx, ?g_CatDirCashSRW@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000254a  test    esi, esi
0x18000254c  jz      loc_180002B6B
0x180002552  call    cs:__imp_ReleaseSRWLockShared
0x180002558  mov     rsi, [rsp+3C8h+var_18]
0x180002560  test    ebx, ebx
0x180002562  jz      loc_180002B76
0x180002568  mov     eax, ebx
0x18000256a  mov     rcx, [rsp+3C8h+var_58]
0x180002572  xor     rcx, rsp; StackCookie
0x180002575  call    __security_check_cookie
0x18000257a  add     rsp, 3C0h
0x180002581  pop     rbx
0x180002582  retn
0x180002583  cmp     eax, r14d
0x180002586  jz      loc_1800024C8
0x18000258c  test    esi, esi
0x18000258e  jz      loc_18000299E
0x180002594  mov     rdi, [rdi]
0x180002597  jmp     loc_1800024AF
0x18000259c  xor     edi, edi
0x18000259e  call    cs:__imp_GetLastError
0x1800025a4  cmp     cs:?g_fErrLogInitialized@@3HA, edi; int g_fErrLogInitialized
0x1800025aa  xorps   xmm0, xmm0
0x1800025ad  movups  xmmword ptr [rsp+3C8h+SystemTime.wYear], xmm0
0x1800025b2  mov     ebx, eax
0x1800025b4  jnz     short loc_1800025BB
0x1800025b6  call    ?ErrLog_Initialize@@YAXXZ; ErrLog_Initialize(void)
0x1800025bb  lea     rcx, [rsp+3C8h+SystemTime]; lpSystemTime
0x1800025c0  call    cs:__imp_GetLocalTime
0x1800025c6  lea     rax, [rsp+3C8h+TimeStr]
0x1800025cb  mov     r14d, 100h
0x1800025d1  mov     dword ptr [rsp+3C8h+cchTime], r14d; cchTime
0x1800025d6  lea     r8, [rsp+3C8h+SystemTime]; lpTime
0x1800025db  xor     r9d, r9d; lpFormat
0x1800025de  mov     [rsp+3C8h+lpTimeStr], rax; lpTimeStr
0x1800025e3  xor     edx, edx; dwFlags
0x1800025e5  mov     ecx, 400h; Locale
0x1800025ea  call    cs:__imp_GetTimeFormatA
0x1800025f0  movsxd  r8, eax
0x1800025f3  lea     eax, [r8-1]
0x1800025f7  cmp     eax, 0FFh
0x1800025fc  ja      loc_180002710
0x180002602  sub     r14d, r8d
0x180002605  lea     rdx, [rsp+3C8h+TimeStr]
0x18000260a  add     rdx, r8
0x18000260d  mov     dword ptr [rsp+3C8h+cchTime], r14d; cchDate
0x180002612  mov     [rsp+3C8h+lpTimeStr], rdx; lpDateStr
0x180002617  lea     r8, [rsp+3C8h+SystemTime]; lpDate
0x18000261c  xor     r9d, r9d; lpFormat
0x18000261f  mov     ecx, 400h; Locale
0x180002624  mov     byte ptr [rdx-1], 20h ; ' '
0x180002628  mov     edx, 1; dwFlags
0x18000262d  call    cs:__imp_GetDateFormatA
0x180002633  mov     eax, ebx
0x180002635  lea     r9, [rsp+3C8h+TimeStr]
0x18000263a  and     eax, 1FFF0000h
0x18000263f  mov     edx, 200h; unsigned __int64
0x180002644  cmp     eax, 0E5E0000h
0x180002649  jnz     loc_1800028A4
0x18000264f  movzx   ecx, bx
0x180002652  lea     r8, aCatalogdbSSAtL; "CatalogDB: %s: %s at line #%u encounter"...
0x180002659  mov     eax, ecx
0x18000265b  neg     eax
0x18000265d  test    ebx, ebx
0x18000265f  cmovns  eax, ecx
0x180002662  mov     [rsp+3C8h+hTemplateFile], eax
0x180002666  lea     rax, aCatdbsvcCpp; "catdbsvc.cpp"
0x18000266d  mov     dword ptr [rsp+3C8h+cchTime], 10E7h
0x180002675  lea     rcx, [rsp+3C8h+OutputString]; char *
0x18000267d  mov     [rsp+3C8h+lpTimeStr], rax
0x180002682  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180002687  cmp     cs:?g_fLogErrorsToDebugger@@3HA, edi; int g_fLogErrorsToDebugger
0x18000268d  mov     [rsp+3C8h+NumberOfBytesWritten], edi
0x180002691  jnz     loc_1800028B4
0x180002697  cmp     cs:?g_fLogErrorsToFile@@3HA, edi; int g_fLogErrorsToFile
0x18000269d  jz      short loc_180002710
0x18000269f  mov     rax, cs:lpSrc
0x1800026a6  xor     r8d, r8d; nSize
0x1800026a9  mov     rcx, rax; lpSrc
0x1800026ac  mov     [rsp+3C8h+lpSrc], rax
0x1800026b1  xor     edx, edx; lpDst
0x1800026b3  call    cs:__imp_ExpandEnvironmentStringsW
0x1800026b9  mov     r13d, eax
0x1800026bc  test    eax, eax
0x1800026be  jz      short loc_180002710
0x1800026c0  mov     edx, r13d
0x1800026c3  xor     ecx, ecx; uFlags
0x1800026c5  add     rdx, rdx; uBytes
0x1800026c8  call    cs:__imp_LocalAlloc
0x1800026ce  mov     r12, rax
0x1800026d1  test    rax, rax
0x1800026d4  jz      short loc_180002710
0x1800026d6  mov     rcx, [rsp+3C8h+lpSrc]; lpSrc
0x1800026db  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800026e2  mov     r8d, r13d; nSize
0x1800026e5  mov     rdx, rax; lpDst
0x1800026e8  mov     r15, r14
0x1800026eb  call    cs:__imp_ExpandEnvironmentStringsW
0x1800026f1  test    eax, eax
0x1800026f3  jnz     loc_1800028C7
0x1800026f9  mov     rcx, r12; hMem
0x1800026fc  call    cs:__imp_LocalFree
0x180002702  cmp     r15, r14
0x180002705  jz      short loc_180002710
0x180002707  mov     rcx, r15; hObject
0x18000270a  call    cs:__imp_CloseHandle
0x180002710  mov     ecx, ebx; dwErrCode
0x180002712  call    cs:__imp_SetLastError
0x180002718  call    cs:__imp_GetLastError
0x18000271e  mov     [rsp+3C8h+NumberOfBytesWritten], eax
0x180002722  mov     r15, rdi
0x180002725  jmp     loc_180002890
0x18000272a  mov     ecx, 70h ; 'p'; uBytes
0x18000272f  mov     [rsp+3C8h+NumberOfBytesWritten], 0
0x180002737  mov     ebx, 1
0x18000273c  call    ?_CatDBAlloc@@YAPEAX_K@Z; _CatDBAlloc(unsigned __int64)
0x180002741  mov     [rsp+3C8h+lpSrc], rax
0x180002746  mov     rdi, rax
0x180002749  test    rax, rax
0x18000274c  jz      loc_180002A58
0x180002752  xor     edx, edx; Val
0x180002754  mov     r8d, 58h ; 'X'; Size
0x18000275a  mov     rcx, rax; void *
0x18000275d  call    memset_0
0x180002762  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002769  mov     [rdi+60h], ebx
0x18000276c  mov     [rdi+64h], r14d
0x180002770  mov     [rdi+68h], esi
0x180002773  inc     rax
0x180002776  cmp     word ptr [r15+rax*2], 0
0x18000277c  jnz     short loc_180002773
0x18000277e  inc     eax
0x180002780  mov     qword ptr [rsp+3C8h+SystemTime.wYear], rax
0x180002785  lea     rcx, [rax+rax]; uBytes
0x180002789  call    ?_CatDBAlloc@@YAPEAX_K@Z; _CatDBAlloc(unsigned __int64)
0x18000278e  mov     [rdi+58h], rax
0x180002792  test    rax, rax
0x180002795  jz      loc_180002A87
0x18000279b  mov     rdx, qword ptr [rsp+3C8h+SystemTime.wYear]; unsigned __int64
0x1800027a0  mov     r8, r15; unsigned __int16 *
0x1800027a3  mov     rcx, rax; unsigned __int16 *
0x1800027a6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800027ab  mov     rcx, cs:?g_JetInstance@@3_KA; instance
0x1800027b2  lea     rdx, [rdi+8]; psesid
0x1800027b6  xor     r9d, r9d; szPassword
0x1800027b9  xor     r8d, r8d; szUserName
0x1800027bc  call    cs:__imp_JetBeginSessionW
0x1800027c2  mov     ecx, eax; int
0x1800027c4  mov     dword ptr [rsp+3C8h+SystemTime.wYear], eax
0x1800027c8  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800027cd  test    eax, eax
0x1800027cf  jnz     loc_180002A8F
0x1800027d5  mov     rcx, cs:?g_pwszDatabaseFileBaseDirectory@@3PEAGEA; unsigned __int16 *
0x1800027dc  mov     rdx, r15; unsigned __int16 *
0x1800027df  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x1800027e4  mov     r15, rax
0x1800027e7  test    rax, rax
0x1800027ea  jnz     short loc_180002832
0x1800027ec  mov     r8d, 116Fh; unsigned int
0x1800027f2  xor     r9d, r9d; unsigned int
0x1800027f5  mov     dword ptr [rsp+3C8h+lpTimeStr], 0; int
0x1800027fd  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180002802  mov     edi, 1
0x180002807  call    cs:__imp_GetLastError
0x18000280d  mov     rbx, [rsp+3C8h+lpSrc]
0x180002812  xor     edx, edx; grbit
0x180002814  mov     [rsp+3C8h+NumberOfBytesWritten], eax
0x180002818  mov     rcx, [rbx+8]; sesid
0x18000281c  call    cs:__imp_JetEndSession
0x180002822  jmp     loc_180002B21
0x180002827  call    cs:__imp_AcquireSRWLockExclusive
0x18000282d  jmp     loc_180002482
0x180002832  lea     rdx, aCatdb_0; "catdb"
0x180002839  mov     rcx, rax; unsigned __int16 *
0x18000283c  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x180002841  mov     [rdi], rax
0x180002844  test    rax, rax
0x180002847  jz      loc_180002AC9
0x18000284d  mov     r8d, r14d
0x180002850  mov     edx, esi
0x180002852  mov     rcx, rdi
0x180002855  call    ?_CatDBAttachAndOpenDatabase@@YAHPEAU_JET_DB_STRUCT@@HW4__MIDL_ICatDBSvc_0002@@@Z; _CatDBAttachAndOpenDatabase(_JET_DB_STRUCT *,int,__MIDL_ICatDBSvc_0002)
0x18000285a  test    eax, eax
0x18000285c  jz      loc_180002AD4
0x180002862  mov     rdx, rdi
0x180002865  call    LIST_AddTail
0x18000286a  test    rax, rax
0x18000286d  jz      loc_180002ADF
0x180002873  mov     [r13+0], rdi
0x180002877  mov     edi, 1
0x18000287c  mov     rcx, r15; hMem
0x18000287f  call    cs:__imp_LocalFree
0x180002885  jmp     short loc_180002897
0x180002887  test    r12d, r12d
0x18000288a  jnz     loc_180002B4C
0x180002890  xor     ebx, ebx
0x180002892  test    r15, r15
0x180002895  jnz     short loc_18000287C
0x180002897  test    edi, edi
0x180002899  jnz     loc_180002502
0x18000289f  jmp     loc_18000250F
0x1800028a4  mov     [rsp+3C8h+hTemplateFile], ebx
0x1800028a8  lea     r8, aCatalogdbSSAtL_0; "CatalogDB: %s: %s at line #%u encounter"...
0x1800028af  jmp     loc_180002666
0x1800028b4  lea     rcx, [rsp+3C8h+OutputString]; lpOutputString
0x1800028bc  call    cs:__imp_OutputDebugStringA
0x1800028c2  jmp     loc_180002697
0x1800028c7  mov     qword ptr [rsp+3C8h+hTemplateFile], rdi; hTemplateFile
0x1800028cc  xor     r9d, r9d; lpSecurityAttributes
0x1800028cf  mov     dword ptr [rsp+3C8h+cchTime], 80h; dwFlagsAndAttributes
0x1800028d7  xor     r8d, r8d; dwShareMode
0x1800028da  mov     edx, 0C0000000h; dwDesiredAccess
0x1800028df  mov     dword ptr [rsp+3C8h+lpTimeStr], 4; dwCreationDisposition
0x1800028e7  mov     rcx, r12; lpFileName
0x1800028ea  call    cs:__imp_CreateFileW
0x1800028f0  mov     r15, rax
0x1800028f3  cmp     rax, r14
0x1800028f6  jz      loc_1800026F9
0x1800028fc  xor     edx, edx; lpFileSizeHigh
0x1800028fe  mov     rcx, rax; hFile
0x180002901  call    cs:__imp_GetFileSize
0x180002907  cmp     eax, 30D40h
0x18000290c  jb      short loc_180002939
0x18000290e  xor     r9d, r9d; dwMoveMethod
0x180002911  xor     r8d, r8d; lpDistanceToMoveHigh
0x180002914  xor     edx, edx; lDistanceToMove
0x180002916  mov     rcx, r15; hFile
0x180002919  call    cs:__imp_SetFilePointer
0x18000291f  cmp     eax, 0FFFFFFFFh
0x180002922  jz      loc_1800026F9
0x180002928  mov     rcx, r15; hFile
0x18000292b  call    cs:__imp_SetEndOfFile
0x180002931  test    eax, eax
0x180002933  jz      loc_1800026F9
  ... truncated ...
```
