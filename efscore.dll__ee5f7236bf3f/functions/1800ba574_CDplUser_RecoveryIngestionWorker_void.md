# CDplUser::RecoveryIngestionWorker(void)

- ea: `0x1800ba574`
- end: `0x1800baae9`
- name: `?RecoveryIngestionWorker@CDplUser@@AEAAXXZ`
- size: `1397`
- prototype: `void __fastcall(CDplUser *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800bd980`

## callees

- `0x180005045`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800857a8`
- `0x1800963f0`
- `0x1800964ac`
- `0x18009652c`
- `0x180097238`
- `0x1800b6470`
- `0x1800b7880`
- `0x1800b9ea4`
- `0x1800ba574`
- `0x1800bcfd8`
- `0x1800bd7a8`
- `0x1800bd810`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba70d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba850`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba9b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba70d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba850`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba9b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800baa73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800baa73`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800ba9a5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800ba9a5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800baa0a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800baa0a`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800baa1c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800baa1c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800ba841`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800ba841`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800baa63`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800baa63`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ba703`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ba703`

## string_xrefs

- `0x1800ba972`: `Failed to move processed recovery file`

## pseudocode

```c
void __fastcall CDplUser::RecoveryIngestionWorker(CDplUser *this)
{
  int v2; // ecx
  int v3; // ecx
  unsigned int SessionUserTokenBySid; // ebx
  int v5; // ecx
  int v6; // ecx
  signed int LastError; // eax
  unsigned int v8; // r8d
  int v9; // ecx
  HANDLE FirstFile; // rsi
  signed int v11; // eax
  int v12; // r15d
  int v13; // r14d
  int v14; // ebx
  signed int v15; // eax
  unsigned int lpSearchFilter; // [rsp+20h] [rbp-E0h]
  int dwAdditionalFlags; // [rsp+28h] [rbp-D8h]
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE hToken[2]; // [rsp+48h] [rbp-B8h] BYREF
  void *v21; // [rsp+58h] [rbp-A8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v23[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR PathName[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR FileName[264]; // [rsp+6D0h] [rbp+5D0h] BYREF

  v19 = 0;
  v21 = 0;
  hToken[0] = 0;
  memset_0(v23, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  memset_0(PathName, 0, 0x208u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v18 = 0;
  if ( g_DplDbgBreakEnabled )
    __int2c();
  fnEfsLogTrace1Strings(v2, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 40, 181);
  fnEfsLogTrace1Strings(v3, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 187);
  SessionUserTokenBySid = CDplServiceImpl::RevertToSelf(*((CDplServiceImpl **)this + 6), &v21);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              SessionUserTokenBySid,
              40,
              187) < 0 )
    goto LABEL_34;
  fnEfsLogTrace1Strings(v5, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 193);
  SessionUserTokenBySid = EdpCredSvcQuerySessionUserTokenBySid(*((const unsigned __int16 **)this + 13), hToken);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              SessionUserTokenBySid,
              40,
              193) < 0 )
    goto LABEL_34;
  if ( !ImpersonateLoggedOnUser(hToken[0]) )
  {
    LastError = GetLastError();
    SessionUserTokenBySid = LastError;
    if ( LastError > 0 )
      SessionUserTokenBySid = (unsigned __int16)LastError | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, SessionUserTokenBySid, 40, 199);
    goto LABEL_34;
  }
  fnEfsLogTrace1Strings(v6, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 211);
  SessionUserTokenBySid = CDplUser::MakeRecoveryIngestionFolderPath(
                            *((const unsigned __int16 **)this + 13),
                            v23,
                            v8,
                            PathName,
                            lpSearchFilter,
                            dwAdditionalFlags);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              SessionUserTokenBySid,
              40,
              211) < 0 )
    goto LABEL_33;
  fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 216);
  SessionUserTokenBySid = CDplService::StringCchConcat(FileName, 0x104u, v23, L"\\*", 0);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              SessionUserTokenBySid,
              40,
              216) < 0 )
    goto LABEL_33;
  FirstFile = FindFirstFileExW(FileName, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
  if ( FirstFile == (HANDLE)-1LL )
  {
    v11 = GetLastError();
    SessionUserTokenBySid = v11;
    if ( v11 > 0 )
      SessionUserTokenBySid = (unsigned __int16)v11 | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, SessionUserTokenBySid, 40, 231);
    goto LABEL_33;
  }
  v12 = 0;
  v13 = 0;
  do
  {
    hToken[1] = (HANDLE)__PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
    v14 = CDplUser::RecoveryIngestionProcessFile(
            this,
            v23,
            PathName,
            FindFileData.cFileName,
            FindFileData.dwFileAttributes,
            __PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow),
            &v18,
            &v19);
    if ( v18 )
    {
      v12 = 1;
      if ( v14 >= 0 )
      {
        v13 = 1;
        goto LABEL_21;
      }
    }
    else if ( v14 >= 0 )
    {
      goto LABEL_21;
    }
    fnEfsLogTrace1String1Dword(
      g_hPublisher,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)L"Recovery file ingestion failed at stage",
      v18,
      40,
      3);
    fnEfsLogTrace1String1Dword(
      g_hPublisher,
      (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
      (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
      (unsigned int)L"Recovery file ingestion failure",
      v14,
      40,
      4);
LABEL_21:
    if ( v19 < 0 )
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
        (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
        (unsigned int)L"Failed to move processed recovery file",
        v19,
        40,
        9);
  }
  while ( FindNextFileW(FirstFile, &FindFileData) );
  v15 = GetLastError();
  SessionUserTokenBySid = v15;
  if ( v15 > 0 )
    SessionUserTokenBySid = (unsigned __int16)v15 | 0x80070000;
  if ( SessionUserTokenBySid == -2147024878 )
  {
    SessionUserTokenBySid = 0;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 40, 24);
  }
  else
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, SessionUserTokenBySid, 40, 28);
  }
  FindClose(FirstFile);
  if ( v12 )
    RemoveDirectoryW(PathName);
  if ( v13 )
  {
    CDplServiceImpl::ReloadSvcConfig(*((CDplServiceImpl **)this + 6));
    CDplUser::ProcessRecoveryPolicy(this, 0);
    CDplUser::UserSvcLock(this);
    CDplUser::ScheduleRecoveryBackup(this, 0, 0);
    CDplUser::UserSvcUnlock(this, 1);
  }
LABEL_33:
  RevertToSelf();
LABEL_34:
  if ( hToken[0] )
  {
    CloseHandle(hToken[0]);
    hToken[0] = 0;
  }
  CDplServiceImpl::RestoreImpersonation(*((CDplServiceImpl **)this + 6), &v21);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    SessionUserTokenBySid,
    40,
    78);
}

```

## disassembly

```asm
0x1800ba574  mov     [rsp-8+arg_8], rbx
0x1800ba579  mov     [rsp-8+arg_10], rsi
0x1800ba57e  push    rbp
0x1800ba57f  push    rdi
0x1800ba580  push    r13
0x1800ba582  push    r14
0x1800ba584  push    r15
0x1800ba586  lea     rbp, [rsp-7F0h]
0x1800ba58e  sub     rsp, 8F0h
0x1800ba595  mov     rax, cs:__security_cookie
0x1800ba59c  xor     rax, rsp
0x1800ba59f  mov     [rbp+810h+var_30], rax
0x1800ba5a6  mov     rdi, rcx
0x1800ba5a9  mov     [rsp+910h+var_8CC], 0
0x1800ba5b1  mov     ebx, 208h
0x1800ba5b6  mov     [rsp+910h+var_8B8], 0
0x1800ba5bf  mov     r8d, ebx; Size
0x1800ba5c2  mov     [rsp+910h+hToken], 0
0x1800ba5cb  xor     edx, edx; Val
0x1800ba5cd  lea     rcx, [rbp+810h+var_660]; void *
0x1800ba5d4  call    memset_0
0x1800ba5d9  mov     r8d, ebx; Size
0x1800ba5dc  lea     rcx, [rbp+810h+FileName]; void *
0x1800ba5e3  xor     edx, edx; Val
0x1800ba5e5  call    memset_0
0x1800ba5ea  mov     r8d, ebx; Size
0x1800ba5ed  lea     rcx, [rbp+810h+PathName]; void *
0x1800ba5f4  xor     edx, edx; Val
0x1800ba5f6  call    memset_0
0x1800ba5fb  xor     edx, edx; Val
0x1800ba5fd  lea     r8d, [rbx+48h]; Size
0x1800ba601  lea     rcx, [rsp+910h+FindFileData]; void *
0x1800ba606  call    memset_0
0x1800ba60b  cmp     cs:?g_DplDbgBreakEnabled@@3IA, 0; uint g_DplDbgBreakEnabled
0x1800ba612  mov     [rsp+910h+var_8D0], 0
0x1800ba61a  jz      short loc_1800BA61E
0x1800ba61c  int     2Ch; Windows NT - assertion failure
0x1800ba61e  mov     r13d, 28h ; '('
0x1800ba624  mov     dword ptr [rsp+910h+lpSearchFilter], 29B5h
0x1800ba62c  lea     r14, sourceString
0x1800ba633  mov     r9d, r13d
0x1800ba636  mov     r8, r14
0x1800ba639  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800ba640  call    fnEfsLogTrace1Strings
0x1800ba645  lea     r15, EFS_TRACE_START_EVENT
0x1800ba64c  mov     esi, 29BBh
0x1800ba651  mov     rdx, r15
0x1800ba654  mov     dword ptr [rsp+910h+lpSearchFilter], esi
0x1800ba658  mov     r9d, r13d
0x1800ba65b  mov     r8, r14
0x1800ba65e  call    fnEfsLogTrace1Strings
0x1800ba663  mov     rcx, [rdi+30h]; this
0x1800ba667  lea     rdx, [rsp+910h+var_8B8]; void **
0x1800ba66c  call    ?RevertToSelf@CDplServiceImpl@@AEAAJPEAPEAX@Z; CDplServiceImpl::RevertToSelf(void * *)
0x1800ba671  mov     rcx, cs:g_hPublisher
0x1800ba678  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ba67f  mov     dword ptr [rsp+910h+var_8E0], esi
0x1800ba683  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ba68a  mov     [rsp+910h+dwAdditionalFlags], r13d
0x1800ba68f  mov     r9, r14
0x1800ba692  mov     dword ptr [rsp+910h+lpSearchFilter], eax
0x1800ba696  mov     ebx, eax
0x1800ba698  call    fnEfsLogTrace1String1Dword
0x1800ba69d  test    eax, eax
0x1800ba69f  js      loc_1800BAA69
0x1800ba6a5  mov     esi, 29C1h
0x1800ba6aa  mov     r9d, r13d
0x1800ba6ad  mov     r8, r14
0x1800ba6b0  mov     dword ptr [rsp+910h+lpSearchFilter], esi
0x1800ba6b4  mov     rdx, r15
0x1800ba6b7  call    fnEfsLogTrace1Strings
0x1800ba6bc  mov     rcx, [rdi+68h]; unsigned __int16 *
0x1800ba6c0  lea     rdx, [rsp+910h+hToken]; void **
0x1800ba6c5  call    ?EdpCredSvcQuerySessionUserTokenBySid@@YAJPEBGPEAPEAX@Z; EdpCredSvcQuerySessionUserTokenBySid(ushort const *,void * *)
0x1800ba6ca  mov     rcx, cs:g_hPublisher
0x1800ba6d1  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ba6d8  mov     dword ptr [rsp+910h+var_8E0], esi
0x1800ba6dc  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ba6e3  mov     [rsp+910h+dwAdditionalFlags], r13d; int
0x1800ba6e8  mov     r9, r14
0x1800ba6eb  mov     dword ptr [rsp+910h+lpSearchFilter], eax
0x1800ba6ef  mov     ebx, eax
0x1800ba6f1  call    fnEfsLogTrace1String1Dword
0x1800ba6f6  test    eax, eax
0x1800ba6f8  js      loc_1800BAA69
0x1800ba6fe  mov     rcx, [rsp+910h+hToken]; hToken
0x1800ba703  call    cs:__imp_ImpersonateLoggedOnUser
0x1800ba709  test    eax, eax
0x1800ba70b  jnz     short loc_1800BA748
0x1800ba70d  call    cs:__imp_GetLastError
0x1800ba713  mov     ebx, eax
0x1800ba715  test    eax, eax
0x1800ba717  jle     short loc_1800BA722
0x1800ba719  movzx   ebx, ax
0x1800ba71c  or      ebx, 80070000h
0x1800ba722  mov     rcx, cs:g_hPublisher
0x1800ba729  lea     rdx, EFS_TRACE_ERROR
0x1800ba730  mov     r9d, r13d
0x1800ba733  mov     dword ptr [rsp+910h+lpSearchFilter], 29C7h
0x1800ba73b  mov     r8d, ebx
0x1800ba73e  call    fnEfsLogTrace1
0x1800ba743  jmp     loc_1800BAA69
0x1800ba748  mov     esi, 29D3h
0x1800ba74d  mov     r9d, r13d
0x1800ba750  mov     r8, r14
0x1800ba753  mov     dword ptr [rsp+910h+lpSearchFilter], esi; unsigned int
0x1800ba757  mov     rdx, r15
0x1800ba75a  call    fnEfsLogTrace1Strings
0x1800ba75f  mov     rcx, [rdi+68h]; unsigned __int16 *
0x1800ba763  lea     r9, [rbp+810h+PathName]; unsigned __int16 *
0x1800ba76a  lea     rdx, [rbp+810h+var_660]; unsigned __int16 *
0x1800ba771  call    ?MakeRecoveryIngestionFolderPath@CDplUser@@CAJPEBGPEAGK1KH@Z; CDplUser::MakeRecoveryIngestionFolderPath(ushort const *,ushort *,ulong,ushort *,ulong,int)
0x1800ba776  mov     rcx, cs:g_hPublisher
0x1800ba77d  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ba784  mov     dword ptr [rsp+910h+var_8E0], esi
0x1800ba788  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ba78f  mov     [rsp+910h+dwAdditionalFlags], r13d
0x1800ba794  mov     r9, r14
0x1800ba797  mov     dword ptr [rsp+910h+lpSearchFilter], eax
0x1800ba79b  mov     ebx, eax
0x1800ba79d  call    fnEfsLogTrace1String1Dword
0x1800ba7a2  test    eax, eax
0x1800ba7a4  js      loc_1800BAA63
0x1800ba7aa  mov     esi, 29D8h
0x1800ba7af  mov     r9d, r13d
0x1800ba7b2  mov     r8, r14
0x1800ba7b5  mov     dword ptr [rsp+910h+lpSearchFilter], esi
0x1800ba7b9  mov     rdx, r15
0x1800ba7bc  call    fnEfsLogTrace1Strings
0x1800ba7c1  lea     r9, asc_1800F2660; "\\*"
0x1800ba7c8  mov     [rsp+910h+lpSearchFilter], 0
0x1800ba7d1  lea     r8, [rbp+810h+var_660]
0x1800ba7d8  mov     edx, 104h; unsigned int
0x1800ba7dd  lea     rcx, [rbp+810h+FileName]; unsigned __int16 *
0x1800ba7e4  call    ?StringCchConcat@CDplService@@SAJPEAGKZZ; CDplService::StringCchConcat(ushort *,ulong,...)
0x1800ba7e9  mov     rcx, cs:g_hPublisher
0x1800ba7f0  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ba7f7  mov     dword ptr [rsp+910h+var_8E0], esi
0x1800ba7fb  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ba802  mov     [rsp+910h+dwAdditionalFlags], r13d
0x1800ba807  mov     r9, r14
0x1800ba80a  mov     dword ptr [rsp+910h+lpSearchFilter], eax
0x1800ba80e  mov     ebx, eax
0x1800ba810  call    fnEfsLogTrace1String1Dword
0x1800ba815  test    eax, eax
0x1800ba817  js      loc_1800BAA63
0x1800ba81d  xor     r9d, r9d; fSearchOp
0x1800ba820  mov     [rsp+910h+dwAdditionalFlags], 0; dwAdditionalFlags
0x1800ba828  lea     r8, [rsp+910h+FindFileData]; lpFindFileData
0x1800ba82d  mov     [rsp+910h+lpSearchFilter], 0; lpSearchFilter
0x1800ba836  lea     rcx, [rbp+810h+FileName]; lpFileName
0x1800ba83d  lea     edx, [r9+1]; fInfoLevelId
0x1800ba841  call    cs:__imp_FindFirstFileExW
0x1800ba847  mov     rsi, rax
0x1800ba84a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ba84e  jnz     short loc_1800BA88B
0x1800ba850  call    cs:__imp_GetLastError
0x1800ba856  mov     ebx, eax
0x1800ba858  test    eax, eax
0x1800ba85a  jle     short loc_1800BA865
0x1800ba85c  movzx   ebx, ax
0x1800ba85f  or      ebx, 80070000h
0x1800ba865  mov     rcx, cs:g_hPublisher
0x1800ba86c  lea     rdx, EFS_TRACE_ERROR
0x1800ba873  mov     r9d, r13d
0x1800ba876  mov     dword ptr [rsp+910h+lpSearchFilter], 29E7h
0x1800ba87e  mov     r8d, ebx
0x1800ba881  call    fnEfsLogTrace1
0x1800ba886  jmp     loc_1800BAA63
0x1800ba88b  xor     r15d, r15d
0x1800ba88e  xor     r14d, r14d
0x1800ba891  mov     eax, [rbp+810h+var_890]
0x1800ba894  lea     r9, [rbp+810h+var_884]; unsigned __int16 *
0x1800ba898  mov     dword ptr [rsp+910h+var_8C0], eax
0x1800ba89c  lea     r8, [rbp+810h+PathName]; unsigned __int16 *
0x1800ba8a3  mov     eax, [rsp+910h+var_894]
0x1800ba8a7  lea     rdx, [rbp+810h+var_660]; unsigned __int16 *
0x1800ba8ae  mov     dword ptr [rsp+910h+var_8C0+4], eax
0x1800ba8b2  mov     rcx, rdi; this
0x1800ba8b5  lea     rax, [rsp+910h+var_8CC]
0x1800ba8ba  mov     [rsp+910h+var_8D8], rax; int *
0x1800ba8bf  lea     rax, [rsp+910h+var_8D0]
0x1800ba8c4  mov     [rsp+910h+var_8E0], rax; unsigned int *
0x1800ba8c9  mov     rax, [rsp+910h+var_8C0]
0x1800ba8ce  mov     qword ptr [rsp+910h+dwAdditionalFlags], rax; unsigned __int64
0x1800ba8d3  mov     eax, [rsp+910h+FindFileData]
0x1800ba8d7  mov     dword ptr [rsp+910h+lpSearchFilter], eax; unsigned int
0x1800ba8db  call    ?RecoveryIngestionProcessFile@CDplUser@@AEAAJPEBG00K_KPEAKPEAJ@Z; CDplUser::RecoveryIngestionProcessFile(ushort const *,ushort const *,ushort const *,ulong,unsigned __int64,ulong *,long *)
0x1800ba8e0  mov     ebx, eax
0x1800ba8e2  mov     eax, [rsp+910h+var_8D0]
0x1800ba8e6  test    eax, eax
0x1800ba8e8  jz      short loc_1800BA8FB
0x1800ba8ea  mov     ecx, 1
0x1800ba8ef  mov     r15d, ecx
0x1800ba8f2  test    ebx, ebx
0x1800ba8f4  js      short loc_1800BA8FF
0x1800ba8f6  mov     r14d, ecx
0x1800ba8f9  jmp     short loc_1800BA963
0x1800ba8fb  test    ebx, ebx
0x1800ba8fd  jns     short loc_1800BA963
0x1800ba8ff  mov     rcx, cs:g_hPublisher
0x1800ba906  lea     r9, aRecoveryFileIn; "Recovery file ingestion failed at stage"
0x1800ba90d  mov     dword ptr [rsp+910h+var_8E0], 2A03h
0x1800ba915  lea     r8, EFS_TRACE_MSG_DWORD_EVENT
0x1800ba91c  mov     [rsp+910h+dwAdditionalFlags], r13d
0x1800ba921  lea     rdx, EFS_TRACE_MSG_DWORD_EVENT
0x1800ba928  mov     dword ptr [rsp+910h+lpSearchFilter], eax
0x1800ba92c  call    fnEfsLogTrace1String1Dword
0x1800ba931  mov     rcx, cs:g_hPublisher
0x1800ba938  lea     r9, aRecoveryFileIn_0; "Recovery file ingestion failure"
0x1800ba93f  mov     dword ptr [rsp+910h+var_8E0], 2A04h
0x1800ba947  lea     r8, EFS_TRACE_MSG_ERROR_EVENT
0x1800ba94e  mov     [rsp+910h+dwAdditionalFlags], r13d
0x1800ba953  lea     rdx, EFS_TRACE_MSG_ERROR_EVENT
0x1800ba95a  mov     dword ptr [rsp+910h+lpSearchFilter], ebx
0x1800ba95e  call    fnEfsLogTrace1String1Dword
0x1800ba963  mov     eax, [rsp+910h+var_8CC]
0x1800ba967  test    eax, eax
0x1800ba969  jns     short loc_1800BA99D
0x1800ba96b  mov     rcx, cs:g_hPublisher
0x1800ba972  lea     r9, aFailedToMovePr; "Failed to move processed recovery file"
0x1800ba979  mov     dword ptr [rsp+910h+var_8E0], 2A09h
0x1800ba981  lea     r8, EFS_TRACE_MSG_ERROR_EVENT
0x1800ba988  mov     [rsp+910h+dwAdditionalFlags], r13d
0x1800ba98d  lea     rdx, EFS_TRACE_MSG_ERROR_EVENT
0x1800ba994  mov     dword ptr [rsp+910h+lpSearchFilter], eax
0x1800ba998  call    fnEfsLogTrace1String1Dword
0x1800ba99d  lea     rdx, [rsp+910h+FindFileData]; lpFindFileData
0x1800ba9a2  mov     rcx, rsi; hFindFile
0x1800ba9a5  call    cs:__imp_FindNextFileW
0x1800ba9ab  test    eax, eax
0x1800ba9ad  jnz     loc_1800BA891
0x1800ba9b3  call    cs:__imp_GetLastError
0x1800ba9b9  mov     ebx, eax
0x1800ba9bb  test    eax, eax
0x1800ba9bd  jle     short loc_1800BA9C8
0x1800ba9bf  movzx   ebx, ax
0x1800ba9c2  or      ebx, 80070000h
0x1800ba9c8  mov     rcx, cs:g_hPublisher
0x1800ba9cf  mov     r9d, r13d
0x1800ba9d2  cmp     ebx, 80070012h
0x1800ba9d8  jnz     short loc_1800BA9F0
0x1800ba9da  xor     ebx, ebx
0x1800ba9dc  mov     dword ptr [rsp+910h+lpSearchFilter], 2A18h
0x1800ba9e4  xor     r8d, r8d
0x1800ba9e7  lea     rdx, EFS_TRACE_STATUS
0x1800ba9ee  jmp     short loc_1800BAA02
0x1800ba9f0  mov     dword ptr [rsp+910h+lpSearchFilter], 2A1Ch
0x1800ba9f8  lea     rdx, EFS_TRACE_ERROR
0x1800ba9ff  mov     r8d, ebx
0x1800baa02  call    fnEfsLogTrace1
0x1800baa07  mov     rcx, rsi; hFindFile
0x1800baa0a  call    cs:__imp_FindClose
0x1800baa10  test    r15d, r15d
0x1800baa13  jz      short loc_1800BAA22
0x1800baa15  lea     rcx, [rbp+810h+PathName]; lpPathName
0x1800baa1c  call    cs:__imp_RemoveDirectoryW
0x1800baa22  test    r14d, r14d
0x1800baa25  jz      short loc_1800BAA5C
0x1800baa27  mov     rcx, [rdi+30h]; this
0x1800baa2b  call    ?ReloadSvcConfig@CDplServiceImpl@@AEAAXXZ; CDplServiceImpl::ReloadSvcConfig(void)
0x1800baa30  xor     edx, edx; int
0x1800baa32  mov     rcx, rdi; this
0x1800baa35  call    ?ProcessRecoveryPolicy@CDplUser@@AEAAJH@Z; CDplUser::ProcessRecoveryPolicy(int)
0x1800baa3a  mov     rcx, rdi; this
0x1800baa3d  call    ?UserSvcLock@CDplUser@@AEAAHXZ; CDplUser::UserSvcLock(void)
0x1800baa42  xor     r8d, r8d; unsigned int
0x1800baa45  xor     edx, edx; struct _GUID *
0x1800baa47  mov     rcx, rdi; this
0x1800baa4a  call    ?ScheduleRecoveryBackup@CDplUser@@AEAAXPEBU_GUID@@K@Z; CDplUser::ScheduleRecoveryBackup(_GUID const *,ulong)
0x1800baa4f  mov     edx, 1; int
0x1800baa54  mov     rcx, rdi; this
0x1800baa57  call    ?UserSvcUnlock@CDplUser@@AEAAHH@Z; CDplUser::UserSvcUnlock(int)
0x1800baa5c  lea     r14, sourceString
0x1800baa63  call    cs:__imp_RevertToSelf
0x1800baa69  mov     rcx, [rsp+910h+hToken]; hObject
0x1800baa6e  test    rcx, rcx
0x1800baa71  jz      short loc_1800BAA82
0x1800baa73  call    cs:__imp_CloseHandle
0x1800baa79  mov     [rsp+910h+hToken], 0
0x1800baa82  mov     rcx, [rdi+30h]; this
0x1800baa86  lea     rdx, [rsp+910h+var_8B8]; void **
0x1800baa8b  call    ?RestoreImpersonation@CDplServiceImpl@@AEAAXPEAPEAX@Z; CDplServiceImpl::RestoreImpersonation(void * *)
0x1800baa90  mov     rcx, cs:g_hPublisher
0x1800baa97  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x1800baa9e  mov     dword ptr [rsp+910h+var_8E0], 2A4Eh
0x1800baaa6  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x1800baaad  mov     [rsp+910h+dwAdditionalFlags], r13d
0x1800baab2  mov     r9, r14
0x1800baab5  mov     dword ptr [rsp+910h+lpSearchFilter], ebx
0x1800baab9  call    fnEfsLogTrace1String1Dword
0x1800baabe  mov     rcx, [rbp+810h+var_30]
0x1800baac5  xor     rcx, rsp; StackCookie
0x1800baac8  call    __security_check_cookie
0x1800baacd  lea     r11, [rsp+910h+var_20]
0x1800baad5  mov     rbx, [r11+38h]
0x1800baad9  mov     rsi, [r11+40h]
0x1800baadd  mov     rsp, r11
0x1800baae0  pop     r15
0x1800baae2  pop     r14
  ... truncated ...
```
