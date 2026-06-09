# CFileListener::ProgrammaticMetabaseSaveNotification(void)

- ea: `0x18000e104`
- end: `0x18000e482`
- name: `?ProgrammaticMetabaseSaveNotification@CFileListener@@AEAAHXZ`
- size: `894`
- prototype: `__int64 __fastcall(CFileListener *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d374`

## callees

- `0x18000a638`
- `0x18000b4d0`
- `0x18000e104`
- `0x18002056c`
- `0x1800231ec`
- `0x180025e98`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18000e29c`
- `KERNEL32!CopyFileW` at `0x18000e29c`
- `KERNEL32!Sleep` at `0x18000e279`
- `KERNEL32!Sleep` at `0x18000e279`
- `KERNEL32!LeaveCriticalSection` at `0x18000e1e5`
- `KERNEL32!LeaveCriticalSection` at `0x18000e3e1`
- `KERNEL32!LeaveCriticalSection` at `0x18000e44d`
- `KERNEL32!LeaveCriticalSection` at `0x18000e1e5`
- `KERNEL32!LeaveCriticalSection` at `0x18000e3e1`
- `KERNEL32!LeaveCriticalSection` at `0x18000e44d`
- `KERNEL32!EnterCriticalSection` at `0x18000e176`
- `KERNEL32!EnterCriticalSection` at `0x18000e3bc`
- `KERNEL32!EnterCriticalSection` at `0x18000e439`
- `KERNEL32!EnterCriticalSection` at `0x18000e176`
- `KERNEL32!EnterCriticalSection` at `0x18000e3bc`
- `KERNEL32!EnterCriticalSection` at `0x18000e439`
- `KERNEL32!CompareFileTime` at `0x18000e25c`
- `KERNEL32!CompareFileTime` at `0x18000e25c`
- `KERNEL32!GetLastError` at `0x18000e2aa`
- `KERNEL32!GetLastError` at `0x18000e2aa`
- `IisRTL!PuDbgPrint` at `0x18000e1d8`
- `IisRTL!PuDbgPrint` at `0x18000e246`
- `IisRTL!PuDbgPrint` at `0x18000e427`
- `IisRTL!PuDbgPrint` at `0x18000e1d8`
- `IisRTL!PuDbgPrint` at `0x18000e246`
- `IisRTL!PuDbgPrint` at `0x18000e427`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e28d`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e28d`
- `IisRTL!PuDbgPrintW` at `0x18000e334`
- `IisRTL!PuDbgPrintW` at `0x18000e334`

## string_xrefs

- `0x18000e1cc`: `[ProgrammaticMetabaseSaveNotification] PREVIOUS SAVE TIMESTAMPS:\nMetabaseFileLastWrite low: %d\nMetabaseFileLastWrite high: %d\n`
- `0x18000e23a`: `[ProgrammaticMetabaseSaveNotification] CURRENT TIMESTAMPS:\nMetabaseFileLastWrite low: %d\nMetabaseFileLastWrite high: %d\n`
- `0x18000e328`: `[CFileListener::ProgrammaticMetabaseSaveNotification] CopyFile from %s to %s failed with hr = 0x%x. Hence unable to process edits.\n`
- `0x18000e41b`: `[ProgrammaticMetabaseSaveNotification] CURRENT EWR PROCESSED TIMESTAMPS:\nMetabaseEWRProcessedLastWrite low: %d\nMetabaseEWRProcessedLastWrite high: %d\n`

## pseudocode

```c
__int64 __fastcall CFileListener::ProgrammaticMetabaseSaveNotification(CFileListener *this)
{
  int v2; // r15d
  unsigned int v4; // r14d
  unsigned int v5; // ebx
  int v6; // r12d
  const WCHAR *v7; // rbx
  const WCHAR *Str; // rax
  signed int LastError; // eax
  unsigned int v10; // r9d
  signed int v11; // ebx
  FILETIME *p_ftLastWriteTime; // rbx
  unsigned __int16 *v13; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v14; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v15; // [rsp+48h] [rbp-B8h]
  unsigned int v16; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME FileTime1; // [rsp+58h] [rbp-A8h] BYREF
  struct _WIN32_FIND_DATAW v18; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(&v18, 0, sizeof(v18));
  v2 = 0;
  FileTime1 = 0;
  v16 = 0;
  if ( !g_fcsEditWhileRunningInitialized )
    return 0;
  v4 = 0;
  v5 = 0;
  EnterCriticalSection(&g_csEditWhileRunning);
  v6 = g_bSavingMetabaseFileToDisk;
  if ( g_bSavingMetabaseFileToDisk )
  {
    v5 = g_ulMostRecentMetabaseVersion;
    FileTime1 = g_MostRecentMetabaseFileLastWriteTimeStamp;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\listener.cpp",
      4822,
      "CFileListener::ProgrammaticMetabaseSaveNotification",
      "[ProgrammaticMetabaseSaveNotification] PREVIOUS SAVE TIMESTAMPS:\n"
      "MetabaseFileLastWrite low: %d\n"
      "MetabaseFileLastWrite high: %d\n",
      g_MostRecentMetabaseFileLastWriteTimeStamp.dwLowDateTime,
      g_MostRecentMetabaseFileLastWriteTimeStamp.dwHighDateTime);
  LeaveCriticalSection(&g_csEditWhileRunning);
  if ( !v6 || CFileListener::GetMetabaseAttributes(this, &v18, &v16) < 0 )
    goto LABEL_39;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\listener.cpp",
      4841,
      "CFileListener::ProgrammaticMetabaseSaveNotification",
      "[ProgrammaticMetabaseSaveNotification] CURRENT TIMESTAMPS:\n"
      "MetabaseFileLastWrite low: %d\n"
      "MetabaseFileLastWrite high: %d\n",
      v18.ftLastWriteTime.dwLowDateTime,
      v18.ftLastWriteTime.dwHighDateTime);
  if ( v5 == v16 && !CompareFileTime(&FileTime1, &v18.ftLastWriteTime) )
  {
    v4 = 1;
  }
  else
  {
LABEL_39:
    while ( 1 )
    {
      if ( v2 )
        Sleep(0x7D0u);
      v7 = (const WCHAR *)*((_QWORD *)this + 27);
      Str = STRU::QueryStr((CFileListener *)((char *)this + 264));
      if ( CopyFileW(Str, v7, 0) )
        break;
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( (v11 == -2147024864 || v11 == -2147024894 || v11 == -2147024893) && (unsigned int)++v2 < 0xA )
        continue;
      if ( v11 < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LODWORD(v13) = v11;
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\listener.cpp",
            4914,
            "CFileListener::ProgrammaticMetabaseSaveNotification",
            L"[CFileListener::ProgrammaticMetabaseSaveNotification] CopyFile from %s to %s failed with hr = 0x%x. Hence un"
             "able to process edits.\n",
            *((_QWORD *)this + 5),
            *((_QWORD *)this + 27));
        }
        LogEvent(*((struct ICatalogErrorLogger2 **)this + 70), 0xC002C839, 1u, v10, v11, 0, 0, v13, v14, v15);
        CFileListener::CopyErrorFile(this, v11);
        v4 = 1;
        goto LABEL_34;
      }
      break;
    }
    ResetFileAttributesIfNeeded(*((LPCSTR *)this + 27), 1);
    SetSecurityOnFile(*((unsigned __int16 **)this + 5), *((unsigned __int16 **)this + 27));
    p_ftLastWriteTime = &v18.ftLastWriteTime;
    if ( CFileListener::GetMetabaseAttributes(this, &v18, &v16) < 0 )
      p_ftLastWriteTime = 0;
    EnterCriticalSection(&g_csEditWhileRunning);
    if ( p_ftLastWriteTime )
      g_EWRProcessedMetabaseTimeStamp = *p_ftLastWriteTime;
    else
      g_EWRProcessedMetabaseTimeStamp = 0;
    LeaveCriticalSection(&g_csEditWhileRunning);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        5000,
        "CFileListener::ProgrammaticMetabaseSaveNotification",
        "[ProgrammaticMetabaseSaveNotification] CURRENT EWR PROCESSED TIMESTAMPS:\n"
        "MetabaseEWRProcessedLastWrite low: %d\n"
        "MetabaseEWRProcessedLastWrite high: %d\n",
        v18.ftLastWriteTime.dwLowDateTime,
        v18.ftLastWriteTime.dwHighDateTime);
LABEL_34:
    if ( !v6 )
      return v4;
  }
  EnterCriticalSection(&g_csEditWhileRunning);
  g_bSavingMetabaseFileToDisk = 0;
  LeaveCriticalSection(&g_csEditWhileRunning);
  return v4;
}

```

## disassembly

```asm
0x18000e104  mov     [rsp-8+arg_8], rbx
0x18000e109  mov     [rsp-8+arg_10], rdi
0x18000e10e  push    rbp
0x18000e10f  push    r12
0x18000e111  push    r13
0x18000e113  push    r14
0x18000e115  push    r15
0x18000e117  lea     rbp, [rsp-1C0h]
0x18000e11f  sub     rsp, 2C0h
0x18000e126  mov     rax, cs:__security_cookie
0x18000e12d  xor     rax, rsp
0x18000e130  mov     [rbp+1E0h+var_30], rax
0x18000e137  mov     rdi, rcx
0x18000e13a  xor     edx, edx; Val
0x18000e13c  lea     rcx, [rsp+2E0h+var_280]; void *
0x18000e141  mov     r8d, 250h; Size
0x18000e147  call    memset_0
0x18000e14c  xor     r15d, r15d
0x18000e14f  cmp     cs:?g_fcsEditWhileRunningInitialized@@3HA, r15d; int g_fcsEditWhileRunningInitialized
0x18000e156  mov     qword ptr [rsp+2E0h+FileTime1.dwLowDateTime], r15
0x18000e15b  mov     [rsp+2E0h+var_290], r15d
0x18000e160  jnz     short loc_18000E169
0x18000e162  xor     eax, eax
0x18000e164  jmp     loc_18000E456
0x18000e169  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e170  mov     r14d, r15d
0x18000e173  mov     ebx, r15d
0x18000e176  call    cs:__imp_EnterCriticalSection
0x18000e17c  mov     r12d, cs:?g_bSavingMetabaseFileToDisk@@3HA; int g_bSavingMetabaseFileToDisk
0x18000e183  mov     rax, cs:?g_MostRecentMetabaseFileLastWriteTimeStamp@@3U_FILETIME@@A; _FILETIME g_MostRecentMetabaseFileLastWriteTimeStamp
0x18000e18a  test    r12d, r12d
0x18000e18d  jz      short loc_18000E19A
0x18000e18f  mov     ebx, cs:?g_ulMostRecentMetabaseVersion@@3KA; ulong g_ulMostRecentMetabaseVersion
0x18000e195  mov     qword ptr [rsp+2E0h+FileTime1.dwLowDateTime], rax
0x18000e19a  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e1a1  jz      short loc_18000E1DE
0x18000e1a3  mov     ecx, dword ptr cs:?g_MostRecentMetabaseFileLastWriteTimeStamp@@3U_FILETIME@@A+4; _FILETIME g_MostRecentMetabaseFileLastWriteTimeStamp
0x18000e1a9  lea     r9, aCfilelistenerP; "CFileListener::ProgrammaticMetabaseSave"...
0x18000e1b0  mov     dword ptr [rsp+2E0h+var_2B0], ecx
0x18000e1b4  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000e1bb  mov     rcx, cs:g_pDebug
0x18000e1c2  mov     r8d, 12D6h
0x18000e1c8  mov     dword ptr [rsp+2E0h+var_2B8], eax
0x18000e1cc  lea     rax, aProgrammaticme_1; "[ProgrammaticMetabaseSaveNotification] "...
0x18000e1d3  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18000e1d8  call    cs:__imp_PuDbgPrint
0x18000e1de  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e1e5  call    cs:__imp_LeaveCriticalSection
0x18000e1eb  test    r12d, r12d
0x18000e1ee  jz      short loc_18000E26F
0x18000e1f0  lea     r8, [rsp+2E0h+var_290]; unsigned int *
0x18000e1f5  mov     rcx, rdi; this
0x18000e1f8  lea     rdx, [rsp+2E0h+var_280]; struct _WIN32_FIND_DATAW *
0x18000e1fd  call    ?GetMetabaseAttributes@CFileListener@@AEAAJPEAU_WIN32_FIND_DATAW@@PEAK@Z; CFileListener::GetMetabaseAttributes(_WIN32_FIND_DATAW *,ulong *)
0x18000e202  test    eax, eax
0x18000e204  js      short loc_18000E26F
0x18000e206  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e20d  jz      short loc_18000E24C
0x18000e20f  mov     eax, [rsp+2E0h+var_280.ftLastWriteTime.dwHighDateTime]
0x18000e213  lea     r9, aCfilelistenerP; "CFileListener::ProgrammaticMetabaseSave"...
0x18000e21a  mov     rcx, cs:g_pDebug
0x18000e221  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000e228  mov     dword ptr [rsp+2E0h+var_2B0], eax
0x18000e22c  mov     r8d, 12E9h
0x18000e232  mov     eax, [rsp+2E0h+var_280.ftLastWriteTime.dwLowDateTime]
0x18000e236  mov     dword ptr [rsp+2E0h+var_2B8], eax
0x18000e23a  lea     rax, aProgrammaticme; "[ProgrammaticMetabaseSaveNotification] "...
0x18000e241  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18000e246  call    cs:__imp_PuDbgPrint
0x18000e24c  cmp     ebx, [rsp+2E0h+var_290]
0x18000e250  jnz     short loc_18000E26F
0x18000e252  lea     rdx, [rsp+2E0h+var_280.ftLastWriteTime]; lpFileTime2
0x18000e257  lea     rcx, [rsp+2E0h+FileTime1]; lpFileTime1
0x18000e25c  call    cs:__imp_CompareFileTime
0x18000e262  test    eax, eax
0x18000e264  jnz     short loc_18000E26F
0x18000e266  lea     r14d, [rax+1]
0x18000e26a  jmp     loc_18000E432
0x18000e26f  test    r15d, r15d
0x18000e272  jz      short loc_18000E27F
0x18000e274  mov     ecx, 7D0h; dwMilliseconds
0x18000e279  call    cs:__imp_Sleep
0x18000e27f  mov     rbx, [rdi+0D8h]
0x18000e286  lea     rcx, [rdi+108h]
0x18000e28d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e293  xor     r8d, r8d; bFailIfExists
0x18000e296  mov     rdx, rbx; lpNewFileName
0x18000e299  mov     rcx, rax; lpExistingFileName
0x18000e29c  call    cs:__imp_CopyFileW
0x18000e2a2  test    eax, eax
0x18000e2a4  jnz     loc_18000E374
0x18000e2aa  call    cs:__imp_GetLastError
0x18000e2b0  mov     ebx, eax
0x18000e2b2  test    eax, eax
0x18000e2b4  jle     short loc_18000E2BF
0x18000e2b6  movzx   ebx, ax
0x18000e2b9  or      ebx, 80070000h
0x18000e2bf  cmp     ebx, 80070020h
0x18000e2c5  jz      short loc_18000E2D7
0x18000e2c7  cmp     ebx, 80070002h
0x18000e2cd  jz      short loc_18000E2D7
0x18000e2cf  cmp     ebx, 80070003h
0x18000e2d5  jnz     short loc_18000E2E0
0x18000e2d7  inc     r15d
0x18000e2da  cmp     r15d, 0Ah
0x18000e2de  jb      short loc_18000E26F
0x18000e2e0  xor     r15d, r15d
0x18000e2e3  test    ebx, ebx
0x18000e2e5  jns     loc_18000E377
0x18000e2eb  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e2f2  jz      short loc_18000E33A
0x18000e2f4  mov     rax, [rdi+0D8h]
0x18000e2fb  lea     r9, aCfilelistenerP; "CFileListener::ProgrammaticMetabaseSave"...
0x18000e302  mov     rcx, cs:g_pDebug
0x18000e309  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000e310  mov     dword ptr [rsp+2E0h+var_2A8], ebx; unsigned __int16 *
0x18000e314  mov     r8d, 1332h
0x18000e31a  mov     [rsp+2E0h+var_2B0], rax
0x18000e31f  mov     rax, [rdi+28h]
0x18000e323  mov     [rsp+2E0h+var_2B8], rax
0x18000e328  lea     rax, aCfilelistenerP_5; "[CFileListener::ProgrammaticMetabaseSav"...
0x18000e32f  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18000e334  call    cs:__imp_PuDbgPrintW
0x18000e33a  mov     rcx, [rdi+230h]; struct ICatalogErrorLogger2 *
0x18000e341  mov     edx, 0C002C839h; unsigned int
0x18000e346  mov     [rsp+2E0h+var_2B0], r15; unsigned __int16 *
0x18000e34b  mov     r8d, 1; unsigned int
0x18000e351  mov     [rsp+2E0h+var_2B8], r15; unsigned __int16 *
0x18000e356  mov     dword ptr [rsp+2E0h+var_2C0], ebx; char
0x18000e35a  call    ?LogEvent@@YAJPEAUICatalogErrorLogger2@@KKKKPEAG1111@Z; LogEvent(ICatalogErrorLogger2 *,ulong,ulong,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18000e35f  mov     edx, ebx; int
0x18000e361  mov     rcx, rdi; this
0x18000e364  call    ?CopyErrorFile@CFileListener@@AEAAJJ@Z; CFileListener::CopyErrorFile(long)
0x18000e369  mov     r14d, 1
0x18000e36f  jmp     loc_18000E42D
0x18000e374  xor     r15d, r15d
0x18000e377  mov     rcx, [rdi+0D8h]; lpFileName
0x18000e37e  mov     edx, 1; int
0x18000e383  call    ?ResetFileAttributesIfNeeded@@YAXPEADH@Z; ResetFileAttributesIfNeeded(char *,int)
0x18000e388  mov     rdx, [rdi+0D8h]; unsigned __int16 *
0x18000e38f  mov     rcx, [rdi+28h]; unsigned __int16 *
0x18000e393  call    ?SetSecurityOnFile@@YAJPEAG0@Z; SetSecurityOnFile(ushort *,ushort *)
0x18000e398  lea     r8, [rsp+2E0h+var_290]; unsigned int *
0x18000e39d  mov     rcx, rdi; this
0x18000e3a0  lea     rdx, [rsp+2E0h+var_280]; struct _WIN32_FIND_DATAW *
0x18000e3a5  call    ?GetMetabaseAttributes@CFileListener@@AEAAJPEAU_WIN32_FIND_DATAW@@PEAK@Z; CFileListener::GetMetabaseAttributes(_WIN32_FIND_DATAW *,ulong *)
0x18000e3aa  test    eax, eax
0x18000e3ac  lea     rbx, [rsp+2E0h+var_280.ftLastWriteTime]
0x18000e3b1  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e3b8  cmovs   rbx, r15
0x18000e3bc  call    cs:__imp_EnterCriticalSection
0x18000e3c2  test    rbx, rbx
0x18000e3c5  jz      short loc_18000E3D3
0x18000e3c7  mov     rax, [rbx]
0x18000e3ca  mov     cs:?g_EWRProcessedMetabaseTimeStamp@@3U_FILETIME@@A, rax; _FILETIME g_EWRProcessedMetabaseTimeStamp
0x18000e3d1  jmp     short loc_18000E3DA
0x18000e3d3  mov     cs:?g_EWRProcessedMetabaseTimeStamp@@3U_FILETIME@@A, r15; _FILETIME g_EWRProcessedMetabaseTimeStamp
0x18000e3da  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e3e1  call    cs:__imp_LeaveCriticalSection
0x18000e3e7  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e3ee  jz      short loc_18000E42D
0x18000e3f0  mov     eax, [rsp+2E0h+var_280.ftLastWriteTime.dwHighDateTime]
0x18000e3f4  lea     r9, aCfilelistenerP; "CFileListener::ProgrammaticMetabaseSave"...
0x18000e3fb  mov     rcx, cs:g_pDebug
0x18000e402  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000e409  mov     dword ptr [rsp+2E0h+var_2B0], eax
0x18000e40d  mov     r8d, 1388h
0x18000e413  mov     eax, [rsp+2E0h+var_280.ftLastWriteTime.dwLowDateTime]
0x18000e417  mov     dword ptr [rsp+2E0h+var_2B8], eax
0x18000e41b  lea     rax, aProgrammaticme_0; "[ProgrammaticMetabaseSaveNotification] "...
0x18000e422  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18000e427  call    cs:__imp_PuDbgPrint
0x18000e42d  test    r12d, r12d
0x18000e430  jz      short loc_18000E453
0x18000e432  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e439  call    cs:__imp_EnterCriticalSection
0x18000e43f  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e446  mov     cs:?g_bSavingMetabaseFileToDisk@@3HA, r15d; int g_bSavingMetabaseFileToDisk
0x18000e44d  call    cs:__imp_LeaveCriticalSection
0x18000e453  mov     eax, r14d
0x18000e456  mov     rcx, [rbp+1E0h+var_30]
0x18000e45d  xor     rcx, rsp; StackCookie
0x18000e460  call    __security_check_cookie
0x18000e465  lea     r11, [rsp+2E0h+var_20]
0x18000e46d  mov     rbx, [r11+38h]
0x18000e471  mov     rdi, [r11+40h]
0x18000e475  mov     rsp, r11
0x18000e478  pop     r15
0x18000e47a  pop     r14
0x18000e47c  pop     r13
0x18000e47e  pop     r12
0x18000e480  pop     rbp
0x18000e481  retn
```
