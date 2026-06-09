# SaveAllData(int,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,ushort *,ushort *,ulong,int,int)

- ea: `0x180023548`
- end: `0x180023a6d`
- name: `?SaveAllData@@YAJHPEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@PEAG2KHH@Z`
- size: `1317`
- prototype: `__int64 __fastcall(__int64, struct IIS_CRYPTO_STORAGE *, struct _IIS_CRYPTO_BLOB *, unsigned __int16 *, unsigned __int16 *, unsigned int, int, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180015e30`
- `0x180019b60`
- `0x180026cb8`

## callees

- `0x18000f0f4`
- `0x18000f128`
- `0x18000f2d0`
- `0x18001d314`
- `0x18002056c`
- `0x180023548`
- `0x180023df4`
- `0x180024bc4`
- `0x1800274d0`
- `0x180027930`
- `0x1800309d0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002365d`
- `KERNEL32!CreateFileW` at `0x18002365d`
- `KERNEL32!CloseHandle` at `0x1800237b2`
- `KERNEL32!CloseHandle` at `0x1800237b2`
- `KERNEL32!WaitForSingleObject` at `0x18002360c`
- `KERNEL32!WaitForSingleObject` at `0x18002360c`
- `KERNEL32!ReleaseSemaphore` at `0x1800239d3`
- `KERNEL32!ReleaseSemaphore` at `0x1800239d3`
- `KERNEL32!DeleteFileW` at `0x1800239b9`
- `KERNEL32!DeleteFileW` at `0x1800239b9`
- `KERNEL32!LeaveCriticalSection` at `0x1800238b8`
- `KERNEL32!LeaveCriticalSection` at `0x18002392f`
- `KERNEL32!LeaveCriticalSection` at `0x1800238b8`
- `KERNEL32!LeaveCriticalSection` at `0x18002392f`
- `KERNEL32!EnterCriticalSection` at `0x180023879`
- `KERNEL32!EnterCriticalSection` at `0x180023914`
- `KERNEL32!EnterCriticalSection` at `0x180023879`
- `KERNEL32!EnterCriticalSection` at `0x180023914`
- `KERNEL32!GetLastError` at `0x18002366d`
- `KERNEL32!GetLastError` at `0x1800237c9`
- `KERNEL32!GetLastError` at `0x180023822`
- `KERNEL32!GetLastError` at `0x18002366d`
- `KERNEL32!GetLastError` at `0x1800237c9`
- `KERNEL32!GetLastError` at `0x180023822`
- `KERNEL32!GetFileAttributesExW` at `0x180023818`
- `KERNEL32!GetFileAttributesExW` at `0x180023818`
- `IisRTL!?ReadOrWriteLock@CReaderWriterLock3@@QEAA_NXZ` at `0x180023695`
- `IisRTL!?ReadOrWriteLock@CReaderWriterLock3@@QEAA_NXZ` at `0x180023695`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x18002378a`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x18002378a`
- `IisRTL!PuDbgPrint` at `0x180023a3e`
- `IisRTL!PuDbgPrint` at `0x180023a3e`
- `IisRTL!PuDbgPrintW` at `0x18002386a`
- `IisRTL!PuDbgPrintW` at `0x180023993`
- `IisRTL!PuDbgPrintW` at `0x18002386a`
- `IisRTL!PuDbgPrintW` at `0x180023993`

## string_xrefs

- `0x180023853`: `[SaveAllData] Could not fetch the current file attributes for the temporary metabase file. GetFileAttributesEx on %s failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SaveAllData(
        __int64 a1,
        struct IIS_CRYPTO_STORAGE *a2,
        struct _IIS_CRYPTO_BLOB *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        int a7,
        int a8)
{
  const WCHAR *v8; // r14
  int v10; // r15d
  signed int v12; // esi
  struct _FILETIME v13; // rbx
  const WCHAR *v14; // rcx
  unsigned __int16 *v15; // rax
  signed int LastError; // eax
  CListenerController *v17; // r14
  unsigned __int16 *v18; // r12
  int v19; // r13d
  signed int v20; // ecx
  signed int v21; // edi
  signed int v22; // eax
  unsigned int v23; // r14d
  int v24; // esi
  unsigned int v25; // edi
  unsigned int i; // ebx
  int v27; // eax
  int v28; // edi
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-D9h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D1h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-C9h]
  unsigned __int16 *lpNewFileName; // [rsp+38h] [rbp-C1h]
  unsigned __int16 *v34; // [rsp+40h] [rbp-B9h]
  unsigned __int16 *v35; // [rsp+48h] [rbp-B1h]
  bool v36; // [rsp+60h] [rbp-99h]
  const WCHAR *lpFileName; // [rsp+68h] [rbp-91h]
  unsigned int v38; // [rsp+70h] [rbp-89h]
  int v39; // [rsp+74h] [rbp-85h] BYREF
  unsigned int v40; // [rsp+78h] [rbp-81h]
  unsigned int v41; // [rsp+7Ch] [rbp-7Dh]
  unsigned int v42; // [rsp+80h] [rbp-79h]
  int v43; // [rsp+84h] [rbp-75h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-71h]
  int v45; // [rsp+90h] [rbp-69h]
  unsigned __int16 *v46; // [rsp+98h] [rbp-61h]
  LPCWSTR v47; // [rsp+A0h] [rbp-59h]
  unsigned __int16 *v48; // [rsp+A8h] [rbp-51h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+B0h] [rbp-49h] BYREF
  LPCWSTR v50; // [rsp+C8h] [rbp-31h]
  __int128 FileInformation; // [rsp+D0h] [rbp-29h] BYREF
  __int128 v52; // [rsp+E0h] [rbp-19h]
  int v53; // [rsp+F0h] [rbp-9h]

  v8 = g_wszTempFileName;
  v43 = 1;
  v39 = 1;
  v10 = 1;
  v46 = a4;
  hObject = (HANDLE)-1LL;
  lpFileName = g_wszTempFileName;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !g_fcsEditWhileRunningInitialized )
  {
    v12 = -2147418113;
    goto LABEL_45;
  }
  v12 = 0;
  v13 = g_MostRecentMetabaseFileLastWriteTimeStamp;
  v50 = g_wszBackupFileName;
  v14 = a4;
  if ( !a4 )
    v14 = g_wszRealFileName;
  v15 = a5;
  v47 = v14;
  if ( !a5 )
    v15 = g_wszSchemaFileName;
  v48 = v15;
  if ( !a7 )
    WaitForSingleObject(g_hReadSaveSemaphore, 0xFFFFFFFF);
  if ( !g_bSaveDisallowed )
  {
    SecurityAttributes.lpSecurityDescriptor = qword_180048AE8;
    g_bSaveDisallowed = 0;
    SecurityAttributes.nLength = 24;
    SecurityAttributes.bInheritHandle = 0;
    hObject = CreateFileW(v8, 0xC0000000, 0, &SecurityAttributes, 4u, 0x8000080u, 0);
    if ( hObject == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_45;
    }
    v17 = 0;
    v36 = CReaderWriterLock3::ReadOrWriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
    if ( v46 || g_dwLastSaveChangeNumber != *(_DWORD *)&g_dwSystemChangeNumber )
    {
      v45 = 1;
      v12 = SaveEntireTree(a2, a3, a6, a5, v48, &SecurityAttributes, hObject);
      v42 = *(_DWORD *)&g_dwSystemChangeNumber;
      v38 = g_ulHistoryMajorVersionNumber;
      v41 = g_dwEnableHistory;
      ValidateMaxHistoryFiles();
      v18 = v46;
      v40 = g_dwMaxHistoryFiles;
      DetermineIfMetabaseCanBeRenamed(v46, (unsigned __int16 *)v47, a8, &v39);
      v10 = v39;
      v19 = v45;
    }
    else
    {
      v18 = v46;
      v19 = 0;
      v38 = 0;
      v41 = 0;
      v40 = 0;
      v42 = 0;
    }
    if ( g_pListenerController )
    {
      if ( g_dwEnableEditWhileRunning )
      {
        v20 = CListenerController::Start(g_pListenerController);
      }
      else
      {
        v20 = 0;
        v17 = g_pListenerController;
        _InterlockedIncrement((volatile signed __int32 *)g_pListenerController + 17);
      }
      if ( v12 >= 0 )
        v12 = v20;
    }
    CReaderWriterLock3::ReadOrWriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource, v36);
    if ( v17 )
    {
      v21 = CListenerController::Stop(v17, 0);
      CListenerController::Release(v17);
      if ( v12 >= 0 )
        v12 = v21;
    }
    if ( !CloseHandle(hObject) )
    {
      if ( v12 < 0 )
      {
LABEL_44:
        v8 = lpFileName;
        goto LABEL_45;
      }
      v22 = GetLastError();
      v12 = v22;
      if ( v22 > 0 )
        v12 = (unsigned __int16)v22 | 0x80070000;
    }
    if ( v12 >= 0 && v19 )
    {
      v23 = 0;
      if ( v10 )
      {
        v53 = 0;
        FileInformation = 0;
        v24 = 1;
        v52 = 0;
        if ( !GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
        {
          GetLastError();
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
              8171,
              "SaveAllData",
              L"[SaveAllData] Could not fetch the current file attributes for the temporary metabase file. GetFileAttribut"
               "esEx on %s failed with hr = 0x%x.\n");
          v24 = 0;
        }
        EnterCriticalSection(&g_csEditWhileRunning);
        v13 = g_MostRecentMetabaseFileLastWriteTimeStamp;
        v23 = g_ulMostRecentMetabaseVersion;
        v25 = v38;
        g_ulMostRecentMetabaseVersion = v38;
        g_MostRecentMetabaseFileLastWriteTimeStamp = (struct _FILETIME)(*(_QWORD *)((_BYTE *)&v52 + 4)
                                                                      & -(__int64)(v24 != 0));
        g_bSavingMetabaseFileToDisk = 1;
        LeaveCriticalSection(&g_csEditWhileRunning);
      }
      else
      {
        v25 = v38;
      }
      v12 = SaveMetabaseFile(v48, v25, v41, v40, dwCreationDisposition, v10, lpFileName, v47, v50, v18, &v43);
      if ( v12 >= 0 )
      {
        if ( v10 )
          g_dwLastSaveChangeNumber = v42;
      }
      else if ( v10 )
      {
        EnterCriticalSection(&g_csEditWhileRunning);
        g_MostRecentMetabaseFileLastWriteTimeStamp = v13;
        g_ulMostRecentMetabaseVersion = v23;
        LeaveCriticalSection(&g_csEditWhileRunning);
      }
    }
    goto LABEL_44;
  }
LABEL_45:
  if ( a8 )
  {
    for ( i = 0; i < 3; ++i )
    {
      v27 = UnlockMetabaseFile(i);
      v28 = v27;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(hTemplateFile) = v27;
        dwFlagsAndAttributes[0] = i;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          8269,
          "SaveAllData",
          L"[SaveAllData] Unlocking metabase file %d returned 0x%x.\n",
          *(_QWORD *)dwFlagsAndAttributes,
          hTemplateFile);
      }
      if ( v12 >= 0 && v28 < 0 )
        v12 = v28;
    }
  }
  if ( v43 && hObject != (HANDLE)-1LL )
    DeleteFileW(v8);
  if ( !a7 )
    ReleaseSemaphore(g_hReadSaveSemaphore, 1, 0);
  if ( v12 < 0 )
  {
    LogEvent(g_pEventLog, 0xC002C81C, 1u, (unsigned int)a4, v12, 0, 0, lpNewFileName, v34, v35);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        8297,
        "SaveAllData",
        "Failed to flush metabase - error 0x%08lx\n",
        v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180023548  mov     [rsp-8+arg_0], rbx
0x18002354d  push    rbp
0x18002354e  push    rsi
0x18002354f  push    rdi
0x180023550  push    r12
0x180023552  push    r13
0x180023554  push    r14
0x180023556  push    r15
0x180023558  lea     rbp, [rsp-7]
0x18002355d  sub     rsp, 100h
0x180023564  mov     rax, cs:__security_cookie
0x18002356b  xor     rax, rsp
0x18002356e  mov     [rbp+37h+var_38], rax
0x180023572  mov     r14, cs:?g_wszTempFileName@@3PEAGEA; ushort * g_wszTempFileName
0x180023579  xor     ecx, ecx
0x18002357b  cmp     cs:?g_fcsEditWhileRunningInitialized@@3HA, ecx; int g_fcsEditWhileRunningInitialized
0x180023581  mov     r12, rdx
0x180023584  mov     rdi, [rbp+37h+arg_20]
0x180023588  mov     edx, 1
0x18002358d  mov     rax, r9
0x180023590  mov     [rbp+37h+var_AC], edx
0x180023593  xorps   xmm0, xmm0
0x180023596  mov     [rsp+130h+var_BC], edx
0x18002359a  mov     r15d, edx
0x18002359d  mov     [rbp+37h+var_98], rax
0x1800235a1  mov     r13, r8
0x1800235a4  mov     [rbp+37h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800235ac  mov     [rsp+130h+lpFileName], r14
0x1800235b1  movups  xmmword ptr [rbp+37h+SecurityAttributes.nLength], xmm0
0x1800235b5  mov     qword ptr [rbp+37h+SecurityAttributes.bInheritHandle], rcx
0x1800235b9  jnz     short loc_1800235C5
0x1800235bb  mov     esi, 8000FFFFh
0x1800235c0  jmp     loc_18002394A
0x1800235c5  mov     rcx, cs:?g_wszBackupFileName@@3PEAGEA; ushort * g_wszBackupFileName
0x1800235cc  xor     esi, esi
0x1800235ce  mov     rbx, cs:?g_MostRecentMetabaseFileLastWriteTimeStamp@@3U_FILETIME@@A; _FILETIME g_MostRecentMetabaseFileLastWriteTimeStamp
0x1800235d5  test    rax, rax
0x1800235d8  mov     [rbp+37h+var_68], rcx
0x1800235dc  mov     rcx, rax
0x1800235df  cmovz   rcx, cs:?g_wszRealFileName@@3PEAGEA; ushort * g_wszRealFileName
0x1800235e7  mov     rax, rdi
0x1800235ea  test    rdi, rdi
0x1800235ed  mov     [rbp+37h+var_90], rcx
0x1800235f1  cmovz   rax, cs:?g_wszSchemaFileName@@3PEAGEA; ushort * g_wszSchemaFileName
0x1800235f9  mov     [rbp+37h+var_88], rax
0x1800235fd  cmp     [rbp+37h+arg_30], esi
0x180023600  jnz     short loc_180023612
0x180023602  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hHandle
0x180023609  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002360c  call    cs:__imp_WaitForSingleObject
0x180023612  cmp     cs:?g_bSaveDisallowed@@3HA, esi; int g_bSaveDisallowed
0x180023618  jnz     loc_18002394A
0x18002361e  lea     rax, qword_180048AE8
0x180023625  mov     [rsp+130h+hTemplateFile], rsi; hTemplateFile
0x18002362a  mov     [rsp+130h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x180023632  lea     r9, [rbp+37h+SecurityAttributes]; lpSecurityAttributes
0x180023636  xor     r8d, r8d; dwShareMode
0x180023639  mov     [rbp+37h+SecurityAttributes.lpSecurityDescriptor], rax
0x18002363d  mov     edx, 0C0000000h; dwDesiredAccess
0x180023642  mov     [rsp+130h+dwCreationDisposition], 4; dwCreationDisposition
0x18002364a  mov     rcx, r14; lpFileName
0x18002364d  mov     cs:?g_bSaveDisallowed@@3HA, esi; int g_bSaveDisallowed
0x180023653  mov     [rbp+37h+SecurityAttributes.nLength], 18h
0x18002365a  mov     [rbp+37h+SecurityAttributes.bInheritHandle], esi
0x18002365d  call    cs:__imp_CreateFileW
0x180023663  mov     [rbp+37h+hObject], rax
0x180023667  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002366b  jnz     short loc_18002368B
0x18002366d  call    cs:__imp_GetLastError
0x180023673  mov     esi, eax
0x180023675  test    eax, eax
0x180023677  jle     loc_18002394A
0x18002367d  movzx   esi, ax
0x180023680  or      esi, 80070000h
0x180023686  jmp     loc_18002394A
0x18002368b  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180023692  xor     r14d, r14d
0x180023695  call    cs:__imp_?ReadOrWriteLock@CReaderWriterLock3@@QEAA_NXZ; CReaderWriterLock3::ReadOrWriteLock(void)
0x18002369b  mov     [rsp+130h+var_D0], al
0x18002369f  cmp     [rbp+37h+var_98], rsi
0x1800236a3  jnz     short loc_1800236CF
0x1800236a5  mov     ecx, cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x1800236ab  cmp     cs:?g_dwLastSaveChangeNumber@@3KA, ecx; ulong g_dwLastSaveChangeNumber
0x1800236b1  jnz     short loc_1800236CF
0x1800236b3  mov     r12, [rbp+37h+var_98]
0x1800236b7  xor     edi, edi
0x1800236b9  mov     r13d, edi
0x1800236bc  mov     [rsp+130h+var_C0], edi
0x1800236c0  mov     [rbp+37h+var_B4], edi
0x1800236c3  mov     [rsp+130h+var_B8], edi
0x1800236c7  mov     [rbp+37h+var_B0], edi
0x1800236ca  jmp     loc_180023751
0x1800236cf  mov     rax, [rbp+37h+hObject]
0x1800236d3  mov     r9, rdi; unsigned __int16 *
0x1800236d6  mov     r8d, [rbp+37h+arg_28]; unsigned int
0x1800236da  mov     rdx, r13; struct _IIS_CRYPTO_BLOB *
0x1800236dd  mov     [rsp+130h+hTemplateFile], rax; void *
0x1800236e2  mov     rcx, r12; struct IIS_CRYPTO_STORAGE *
0x1800236e5  lea     rax, [rbp+37h+SecurityAttributes]
0x1800236e9  mov     [rbp+37h+var_A0], r15d
0x1800236ed  mov     qword ptr [rsp+130h+dwFlagsAndAttributes], rax; struct _SECURITY_ATTRIBUTES *
0x1800236f2  mov     rax, [rbp+37h+var_88]
0x1800236f6  mov     qword ptr [rsp+130h+dwCreationDisposition], rax; unsigned int
0x1800236fb  call    ?SaveEntireTree@@YAJPEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@KPEAG2PEAU_SECURITY_ATTRIBUTES@@PEAX@Z; SaveEntireTree(IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,ulong,ushort *,ushort *,_SECURITY_ATTRIBUTES *,void *)
0x180023700  mov     esi, eax
0x180023702  mov     eax, cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x180023708  mov     [rbp+37h+var_B0], eax
0x18002370b  mov     eax, cs:?g_ulHistoryMajorVersionNumber@@3KA; ulong g_ulHistoryMajorVersionNumber
0x180023711  mov     [rsp+130h+var_C0], eax
0x180023715  mov     eax, cs:?g_dwEnableHistory@@3KA; ulong g_dwEnableHistory
0x18002371b  mov     [rbp+37h+var_B4], eax
0x18002371e  call    ?ValidateMaxHistoryFiles@@YAXXZ; ValidateMaxHistoryFiles(void)
0x180023723  mov     eax, cs:?g_dwMaxHistoryFiles@@3KA; ulong g_dwMaxHistoryFiles
0x180023729  lea     r9, [rsp+130h+var_BC]; int *
0x18002372e  mov     r12, [rbp+37h+var_98]
0x180023732  mov     r8d, [rbp+37h+arg_38]; int
0x180023736  mov     rcx, r12; unsigned __int16 *
0x180023739  mov     rdx, [rbp+37h+var_90]; unsigned __int16 *
0x18002373d  mov     [rsp+130h+var_B8], eax
0x180023741  call    ?DetermineIfMetabaseCanBeRenamed@@YAXPEAG0HPEAH@Z; DetermineIfMetabaseCanBeRenamed(ushort *,ushort *,int,int *)
0x180023746  mov     r15d, [rsp+130h+var_BC]
0x18002374b  xor     edi, edi
0x18002374d  mov     r13d, [rbp+37h+var_A0]
0x180023751  mov     rax, cs:?g_pListenerController@@3PEAVCListenerController@@EA; CListenerController * g_pListenerController
0x180023758  test    rax, rax
0x18002375b  jz      short loc_18002377F
0x18002375d  cmp     cs:?g_dwEnableEditWhileRunning@@3KA, edi; ulong g_dwEnableEditWhileRunning
0x180023763  jz      short loc_180023771
0x180023765  mov     rcx, rax; this
0x180023768  call    ?Start@CListenerController@@QEAAJXZ; CListenerController::Start(void)
0x18002376d  mov     ecx, eax
0x18002376f  jmp     short loc_18002377A
0x180023771  mov     ecx, edi
0x180023773  mov     r14, rax
0x180023776  lock inc dword ptr [rax+44h]
0x18002377a  test    esi, esi
0x18002377c  cmovns  esi, ecx
0x18002377f  mov     dl, [rsp+130h+var_D0]
0x180023783  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18002378a  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z; CReaderWriterLock3::ReadOrWriteUnlock(bool)
0x180023790  test    r14, r14
0x180023793  jz      short loc_1800237AE
0x180023795  xor     edx, edx
0x180023797  mov     rcx, r14
0x18002379a  call    ?Stop@CListenerController@@QEAAJW4eSTATE@@@Z; CListenerController::Stop(eSTATE)
0x18002379f  mov     rcx, r14; this
0x1800237a2  mov     edi, eax
0x1800237a4  call    ?Release@CListenerController@@QEAAKXZ; CListenerController::Release(void)
0x1800237a9  test    esi, esi
0x1800237ab  cmovns  esi, edi
0x1800237ae  mov     rcx, [rbp+37h+hObject]; hObject
0x1800237b2  call    cs:__imp_CloseHandle
0x1800237b8  mov     edi, 80070000h
0x1800237bd  test    eax, eax
0x1800237bf  jnz     short loc_1800237DA
0x1800237c1  test    esi, esi
0x1800237c3  js      loc_180023945
0x1800237c9  call    cs:__imp_GetLastError
0x1800237cf  mov     esi, eax
0x1800237d1  test    eax, eax
0x1800237d3  jle     short loc_1800237DA
0x1800237d5  movzx   esi, ax
0x1800237d8  or      esi, edi
0x1800237da  test    esi, esi
0x1800237dc  js      loc_180023945
0x1800237e2  test    r13d, r13d
0x1800237e5  jz      loc_180023945
0x1800237eb  mov     r13, [rsp+130h+lpFileName]
0x1800237f0  xor     r14d, r14d
0x1800237f3  test    r15d, r15d
0x1800237f6  jz      loc_1800238C0
0x1800237fc  xor     eax, eax
0x1800237fe  lea     r8, [rbp+37h+FileInformation]; lpFileInformation
0x180023802  xorps   xmm0, xmm0
0x180023805  mov     [rbp+37h+var_40], eax
0x180023808  xor     edx, edx; fInfoLevelId
0x18002380a  mov     rcx, r13; lpFileName
0x18002380d  movups  [rbp+37h+FileInformation], xmm0
0x180023811  lea     esi, [rax+1]
0x180023814  movups  [rbp+37h+var_50], xmm0
0x180023818  call    cs:__imp_GetFileAttributesExW
0x18002381e  test    eax, eax
0x180023820  jnz     short loc_180023872
0x180023822  call    cs:__imp_GetLastError
0x180023828  test    eax, eax
0x18002382a  jle     short loc_180023831
0x18002382c  movzx   eax, ax
0x18002382f  or      eax, edi
0x180023831  test    byte ptr cs:g_dwDebugFlags, 3
0x180023838  jz      short loc_180023870
0x18002383a  mov     rcx, cs:g_pDebug
0x180023841  lea     r9, aSavealldata; "SaveAllData"
0x180023848  mov     dword ptr [rsp+130h+hTemplateFile], eax
0x18002384c  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180023853  lea     rax, aSavealldataCou; "[SaveAllData] Could not fetch the curre"...
0x18002385a  mov     qword ptr [rsp+130h+dwFlagsAndAttributes], r13
0x18002385f  mov     r8d, 1FEBh
0x180023865  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x18002386a  call    cs:__imp_PuDbgPrintW
0x180023870  xor     esi, esi
0x180023872  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180023879  call    cs:__imp_EnterCriticalSection
0x18002387f  mov     rbx, cs:?g_MostRecentMetabaseFileLastWriteTimeStamp@@3U_FILETIME@@A; _FILETIME g_MostRecentMetabaseFileLastWriteTimeStamp
0x180023886  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002388d  mov     r14d, cs:?g_ulMostRecentMetabaseVersion@@3KA; ulong g_ulMostRecentMetabaseVersion
0x180023894  neg     esi
0x180023896  mov     edi, [rsp+130h+var_C0]
0x18002389a  sbb     rax, rax
0x18002389d  mov     cs:?g_ulMostRecentMetabaseVersion@@3KA, edi; ulong g_ulMostRecentMetabaseVersion
0x1800238a3  and     rax, qword ptr [rbp+37h+var_50+4]
0x1800238a7  mov     cs:?g_MostRecentMetabaseFileLastWriteTimeStamp@@3U_FILETIME@@A, rax; _FILETIME g_MostRecentMetabaseFileLastWriteTimeStamp
0x1800238ae  mov     cs:?g_bSavingMetabaseFileToDisk@@3HA, 1; int g_bSavingMetabaseFileToDisk
0x1800238b8  call    cs:__imp_LeaveCriticalSection
0x1800238be  jmp     short loc_1800238C4
0x1800238c0  mov     edi, [rsp+130h+var_C0]
0x1800238c4  mov     r9d, [rsp+130h+var_B8]; unsigned int
0x1800238c9  lea     rax, [rbp+37h+var_AC]
0x1800238cd  mov     r8d, [rbp+37h+var_B4]; unsigned int
0x1800238d1  mov     edx, edi; unsigned int
0x1800238d3  mov     rcx, [rbp+37h+var_88]; unsigned __int16 *
0x1800238d7  mov     [rsp+130h+var_E0], rax; int *
0x1800238dc  mov     rax, [rbp+37h+var_68]
0x1800238e0  mov     [rsp+130h+var_E8], r12; unsigned __int16 *
0x1800238e5  mov     [rsp+130h+var_F0], rax; unsigned __int16 *
0x1800238ea  mov     rax, [rbp+37h+var_90]
0x1800238ee  mov     [rsp+130h+lpNewFileName], rax; unsigned __int16 *
0x1800238f3  mov     [rsp+130h+hTemplateFile], r13; lpExistingFileName
0x1800238f8  mov     [rsp+130h+dwFlagsAndAttributes], r15d; int
0x1800238fd  call    ?SaveMetabaseFile@@YAJPEAGKKKKH0000PEAH@Z; SaveMetabaseFile(ushort *,ulong,ulong,ulong,ulong,int,ushort *,ushort *,ushort *,ushort *,int *)
0x180023902  mov     esi, eax
0x180023904  test    eax, eax
0x180023906  jns     short loc_180023937
0x180023908  test    r15d, r15d
0x18002390b  jz      short loc_180023945
0x18002390d  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180023914  call    cs:__imp_EnterCriticalSection
0x18002391a  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180023921  mov     cs:?g_MostRecentMetabaseFileLastWriteTimeStamp@@3U_FILETIME@@A, rbx; _FILETIME g_MostRecentMetabaseFileLastWriteTimeStamp
0x180023928  mov     cs:?g_ulMostRecentMetabaseVersion@@3KA, r14d; ulong g_ulMostRecentMetabaseVersion
0x18002392f  call    cs:__imp_LeaveCriticalSection
0x180023935  jmp     short loc_180023945
0x180023937  test    r15d, r15d
0x18002393a  jz      short loc_180023945
0x18002393c  mov     eax, [rbp+37h+var_B0]
0x18002393f  mov     cs:?g_dwLastSaveChangeNumber@@3KA, eax; ulong g_dwLastSaveChangeNumber
0x180023945  mov     r14, [rsp+130h+lpFileName]
0x18002394a  cmp     [rbp+37h+arg_38], 0
0x18002394e  jz      short loc_1800239A9
0x180023950  xor     ebx, ebx
0x180023952  mov     ecx, ebx
0x180023954  call    ?UnlockMetabaseFile@@YAJW4_eMetabaseFile@@H@Z; UnlockMetabaseFile(_eMetabaseFile,int)
0x180023959  test    byte ptr cs:g_dwDebugFlags, 3
0x180023960  mov     edi, eax
0x180023962  jz      short loc_180023999
0x180023964  mov     rcx, cs:g_pDebug
0x18002396b  lea     r9, aSavealldata; "SaveAllData"
0x180023972  mov     dword ptr [rsp+130h+hTemplateFile], eax
0x180023976  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18002397d  lea     rax, aSavealldataUnl_0; "[SaveAllData] Unlocking metabase file %"...
0x180023984  mov     [rsp+130h+dwFlagsAndAttributes], ebx
0x180023988  mov     r8d, 204Dh
0x18002398e  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x180023993  call    cs:__imp_PuDbgPrintW
0x180023999  test    esi, esi
0x18002399b  js      short loc_1800239A2
0x18002399d  test    edi, edi
0x18002399f  cmovs   esi, edi
0x1800239a2  inc     ebx
0x1800239a4  cmp     ebx, 3
0x1800239a7  jb      short loc_180023952
0x1800239a9  cmp     [rbp+37h+var_AC], 0
0x1800239ad  jz      short loc_1800239BF
0x1800239af  cmp     [rbp+37h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800239b4  jz      short loc_1800239BF
0x1800239b6  mov     rcx, r14; lpFileName
0x1800239b9  call    cs:__imp_DeleteFileW
0x1800239bf  cmp     [rbp+37h+arg_30], 0
0x1800239c3  jnz     short loc_1800239D9
0x1800239c5  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hSemaphore
0x1800239cc  xor     r8d, r8d; lpPreviousCount
0x1800239cf  lea     edx, [r8+1]; lReleaseCount
0x1800239d3  call    cs:__imp_ReleaseSemaphore
0x1800239d9  test    esi, esi
0x1800239db  jns     short loc_180023A44
0x1800239dd  mov     rcx, cs:?g_pEventLog@@3PEAUICatalogErrorLogger2@@EA; struct ICatalogErrorLogger2 *
0x1800239e4  mov     edx, 0C002C81Ch; unsigned int
0x1800239e9  mov     [rsp+130h+hTemplateFile], 0; unsigned __int16 *
0x1800239f2  mov     r8d, 1; unsigned int
0x1800239f8  mov     qword ptr [rsp+130h+dwFlagsAndAttributes], 0; unsigned __int16 *
0x180023a01  mov     [rsp+130h+dwCreationDisposition], esi; char
0x180023a05  call    ?LogEvent@@YAJPEAUICatalogErrorLogger2@@KKKKPEAG1111@Z; LogEvent(ICatalogErrorLogger2 *,ulong,ulong,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ushort *)
0x180023a0a  test    byte ptr cs:g_dwDebugFlags, 3
0x180023a11  jz      short loc_180023A44
0x180023a13  mov     rcx, cs:g_pDebug
0x180023a1a  lea     rax, aFailedToFlushM; "Failed to flush metabase - error 0x%08l"...
0x180023a21  mov     [rsp+130h+dwFlagsAndAttributes], esi
0x180023a25  lea     r9, aSavealldata; "SaveAllData"
0x180023a2c  mov     r8d, 2069h
0x180023a32  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x180023a37  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
  ... truncated ...
```
