# _CatDBSyncDB(int,ushort const *,ushort const *,int,int,int *)

- ea: `0x18001c03c`
- end: `0x18001c617`
- name: `?_CatDBSyncDB@@YAHHPEBG0HHPEAH@Z`
- size: `1499`
- prototype: `int(int, const unsigned __int16 *, const unsigned __int16 *, int, int, int *)`
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001b6d8`
- `0x18001cca0`

## callees

- `0x1800015b0`
- `0x180001950`
- `0x180002410`
- `0x1800038f0`
- `0x180003d48`
- `0x180008a6c`
- `0x18000a57c`
- `0x18000a59c`
- `0x18000a710`
- `0x18000acbc`
- `0x18000be40`
- `0x18000c7e8`
- `0x180013584`
- `0x18001966c`
- `0x18001b8f4`
- `0x18001c03c`
- `0x18001c7d4`
- `0x18001da60`
- `0x18001f748`
- `0x18001f81c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c425`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c43c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c46a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c4b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c4cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c5a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c425`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c43c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c46a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c4b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c4cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c5a1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001c29f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001c29f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001c3e1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001c3e1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001c579`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001c579`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18001c1dd`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18001c1dd`
- `ESENT!JetBeginTransaction` at `0x18001c343`
- `ESENT!JetBeginTransaction` at `0x18001c343`
- `ESENT!JetRollback` at `0x18001c5fb`
- `ESENT!JetRollback` at `0x18001c5fb`
- `ESENT!JetCommitTransaction` at `0x18001c31f`
- `ESENT!JetCommitTransaction` at `0x18001c405`
- `ESENT!JetCommitTransaction` at `0x18001c498`
- `ESENT!JetCommitTransaction` at `0x18001c31f`
- `ESENT!JetCommitTransaction` at `0x18001c405`
- `ESENT!JetCommitTransaction` at `0x18001c498`

## string_xrefs

- `0x18001c261`: `SyncDB:: DeleteInvalidCatalogFilesFromDatabase failed, will continue`
- `0x18001c508`: `SyncDB:: Error while updating the directory change time`
- `0x18001c532`: `SyncDB:: %u catalogs synced (%u added, %u attributes changed, %u deleted) for database %s`

## pseudocode

```c
__int64 __fastcall _CatDBSyncDB(unsigned int a1, WCHAR *a2, unsigned __int16 *a3, int a4, int a5, int *a6)
{
  WCHAR *v8; // r13
  __int64 v9; // rsi
  struct _JET_DB_STRUCT *v10; // r14
  const WCHAR *v11; // rcx
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  unsigned int v14; // ebx
  unsigned int v15; // r15d
  unsigned int v16; // edx
  unsigned __int16 *v17; // rcx
  unsigned int Error; // eax
  int v19; // eax
  int v20; // ecx
  unsigned __int16 *v21; // rdi
  unsigned __int16 *v22; // rdx
  DWORD LastError; // ebx
  unsigned int v24; // edx
  unsigned __int16 *v25; // rcx
  unsigned __int16 *v26; // r8
  const WCHAR *v27; // rax
  unsigned int v28; // edx
  unsigned __int16 *v29; // rcx
  DWORD v30; // eax
  unsigned int v31; // edx
  unsigned __int16 *v32; // rcx
  int v33; // esi
  __int64 v34; // rbx
  unsigned __int64 v35; // rdi
  JET_ERR v36; // ebx
  JET_ERR v37; // edi
  DWORD v38; // edi
  unsigned int v39; // edx
  unsigned __int16 *v40; // rcx
  unsigned int v41; // edx
  unsigned __int16 *v42; // rcx
  JET_ERR v43; // edi
  DWORD v44; // eax
  unsigned int v45; // edx
  unsigned __int16 *v46; // rcx
  unsigned int v47; // r8d
  DWORD v48; // eax
  DWORD v49; // eax
  unsigned int v50; // edx
  unsigned __int16 *v51; // rcx
  JET_ERR v52; // ebx
  DWORD v53; // eax
  unsigned int v54; // r9d
  unsigned int v55; // r8d
  int v57; // [rsp+28h] [rbp-D8h]
  int v58; // [rsp+28h] [rbp-D8h]
  HANDLE hFindFile; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v60; // [rsp+48h] [rbp-B8h]
  int v61; // [rsp+4Ch] [rbp-B4h]
  struct _JET_DB_STRUCT *v62; // [rsp+50h] [rbp-B0h] BYREF
  int v63; // [rsp+58h] [rbp-A8h]
  int v64; // [rsp+5Ch] [rbp-A4h]
  unsigned __int16 *v65; // [rsp+60h] [rbp-A0h]
  unsigned int v66; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v67; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v68[4]; // [rsp+70h] [rbp-90h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF

  v60 = a1;
  v65 = a3;
  v64 = a4;
  v8 = 0;
  v9 = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v10 = 0;
  v63 = 0;
  v62 = 0;
  v68[0] = 0;
  v67 = 0;
  v66 = 0;
  LODWORD(hFindFile) = 0;
  v61 = 0;
  I_CatDBEventSubsystemTemplate(a3, CAPI2_CATDB_SYNC_SUBSYSTEM_START_EVENT);
  v11 = g_pwszDatabaseFileBaseDirectory;
  *a6 = 0;
  if ( !_CatDBEnsureDirExists(v11, a3) )
  {
    ErrLog_LogError(v13, v12, 0x833u, 0, 0, v57);
    goto LABEL_3;
  }
  v14 = 0;
  v58 = v64;
  v15 = 1;
  if ( !(unsigned int)_CatDBAcquireOpenDatabaseFromCache(&v62, v65, v60, 2, -1) )
  {
    if ( !v60 )
    {
      ErrLog_LogError(v17, v16, 0x849u, 0, 0, v58);
      Error = _CatDBGetNonzeroLastError();
      v10 = v62;
      v14 = Error;
      goto LABEL_78;
    }
    *a6 = 1;
    goto LABEL_70;
  }
  v10 = v62;
  v63 = 1;
  if ( !a5 )
  {
    v19 = _CatDBIsCatalogPathChanged(v62, a2, (int *)&hFindFile);
    v20 = (int)hFindFile;
    if ( !v19 )
      v20 = 1;
    if ( v60 || !v20 )
    {
      *a6 = v20;
      goto LABEL_61;
    }
  }
  v21 = v65;
  ErrLog_LogString(0, L"SyncDB:: Sync started for database ", v65, 1);
  if ( (int)RtlRunOnceExecuteOnce(&qword_180032A58, _CatDBRunOnceShouldOnlySyncPresentCatalogs, 0, 0) >= 0
    && g_fFilterNonePresentCatalogs )
  {
    v22 = L"SyncDB:: Sync only present catalogs";
    goto LABEL_22;
  }
  if ( !(unsigned int)_CatDBDeleteInvalidCatalogFilesFromDatabase(v10, dword_180032714, a2, &v66) )
  {
    LastError = GetLastError();
    ErrLog_LogError(v25, v24, 0x874u, LastError, 0, v58);
    if ( LastError == 303 )
    {
      if ( !dword_180032714 )
        goto LABEL_3;
      v22 = L"SyncDB:: Enabling enum filtering for ";
      g_fFilterNonePresentCatalogs = 1;
      v26 = v21;
      goto LABEL_23;
    }
    v22 = L"SyncDB:: DeleteInvalidCatalogFilesFromDatabase failed, will continue";
LABEL_22:
    v26 = 0;
LABEL_23:
    ErrLog_LogString(0, v22, v26, 1);
  }
  v27 = _CATDBConstructWSTRPath(a2, L"*.cat");
  v8 = (WCHAR *)v27;
  if ( !v27 )
  {
    ErrLog_LogError(v29, v28, 0x899u, 0, 0, v58);
    goto LABEL_3;
  }
  hFindFile = FindFirstFileW(v27, &FindFileData);
  v9 = (__int64)hFindFile;
  if ( hFindFile == (HANDLE)-1LL )
  {
    v30 = GetLastError();
    v14 = v30;
    v32 = (unsigned __int16 *)(v30 - 2);
    if ( ((unsigned int)v32 & 0xFFFFFFEE) == 0 && v30 != 19 )
    {
LABEL_58:
      if ( !g_fFilterNonePresentCatalogs && !(unsigned int)_CatDBUpdateCatalogPathChangedTime(v10, a2, 0) )
        ErrLog_LogString(0, L"SyncDB:: Error while updating the directory change time", 0, 1);
      goto LABEL_61;
    }
    ErrLog_LogError(v32, v31, 0x8B2u, 0, 0, v58);
LABEL_3:
    v14 = _CatDBGetNonzeroLastError();
    goto LABEL_78;
  }
  v33 = 0;
  v34 = 0;
  while ( (FindFileData.dwFileAttributes & 0x10) != 0 )
  {
LABEL_45:
    if ( !FindNextFileW(hFindFile, &FindFileData) )
    {
      v14 = GetLastError();
      if ( v33 )
      {
        v43 = JetCommitTransaction(*((_QWORD *)v10 + 1), 0);
        if ( (unsigned int)_CatDBJET_errFailure(v43) )
        {
          v44 = _CatDBMapJetError(v43);
          SetLastError(v44);
          v47 = 2340;
LABEL_50:
          ErrLog_LogError(v46, v45, v47, 0, 0, v58);
          v14 = _CatDBGetNonzeroLastError();
          goto LABEL_76;
        }
        --v33;
      }
      if ( v14 == 18 )
      {
        v9 = (__int64)hFindFile;
        goto LABEL_58;
      }
      v54 = v14;
      v55 = 2352;
      goto LABEL_74;
    }
  }
  v62 = (struct _JET_DB_STRUCT *)__PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
  v35 = __PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
  v34 += __PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
  if ( v34 > 0x200000 || v34 < __SPAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow) )
  {
    if ( v33 )
    {
      v36 = JetCommitTransaction(*((_QWORD *)v10 + 1), 1u);
      if ( (unsigned int)_CatDBJET_errFailure(v36) )
      {
        v48 = _CatDBMapJetError(v36);
        SetLastError(v48);
        v47 = 2263;
        goto LABEL_50;
      }
      --v33;
    }
    v34 = v35;
  }
  if ( !v33 )
  {
    v37 = JetBeginTransaction(*((_QWORD *)v10 + 1));
    if ( (unsigned int)_CatDBJET_errFailure(v37) )
    {
      v49 = _CatDBMapJetError(v37);
      SetLastError(v49);
      ErrLog_LogError(v51, v50, 0x8E6u, 0, 0, v58);
      v14 = _CatDBGetNonzeroLastError();
      goto LABEL_77;
    }
    v33 = 1;
  }
  if ( (unsigned int)_CatDBSyncCatalogFile(v10, v65, a2, &FindFileData, v68, &v67, &v66) )
  {
    ++v61;
    goto LABEL_45;
  }
  v38 = GetLastError();
  ErrLog_LogError(v40, v39, 0x8F7u, v38, 0, v58);
  if ( v38 != 303 )
  {
    ErrLog_LogString(0, L"SyncDB:: SyncCatalogFile failed, will continue ", FindFileData.cFileName, 1);
    goto LABEL_45;
  }
  v52 = JetCommitTransaction(*((_QWORD *)v10 + 1), 0);
  if ( !(unsigned int)_CatDBJET_errFailure(v52) )
  {
    SetLastError(0x12Fu);
    --v33;
    goto LABEL_75;
  }
  v53 = _CatDBMapJetError(v52);
  SetLastError(v53);
  v54 = 0;
  v55 = 2305;
LABEL_74:
  ErrLog_LogError(v42, v41, v55, v54, 0, v58);
LABEL_75:
  v14 = _CatDBGetNonzeroLastError();
  if ( !v33 )
    goto LABEL_77;
  do
  {
LABEL_76:
    JetRollback(*((_QWORD *)v10 + 1), 0);
    --v33;
  }
  while ( v33 );
LABEL_77:
  v9 = (__int64)hFindFile;
LABEL_78:
  v15 = 0;
LABEL_61:
  if ( !v60 && v61 )
    ErrLog_LogPrintfW(
      0,
      1,
      L"SyncDB:: %u catalogs synced (%u added, %u attributes changed, %u deleted) for database %s");
  if ( v63 )
    _CatDBReleaseDatabaseToCache(v10, v64);
  if ( v9 != -1 )
    FindClose((HANDLE)v9);
  if ( v8 )
    _CatDBFree(v8);
LABEL_70:
  I_CatDBEventStatusTemplate(v14, CAPI2_CATDB_SYNC_SUBSYSTEM_STOP_EVENT);
  if ( !v15 )
    SetLastError(v14);
  return v15;
}

```

## disassembly

```asm
0x18001c03c  mov     [rsp-8+arg_18], rbx
0x18001c041  push    rbp
0x18001c042  push    rsi
0x18001c043  push    rdi
0x18001c044  push    r12
0x18001c046  push    r13
0x18001c048  push    r14
0x18001c04a  push    r15
0x18001c04c  lea     rbp, [rsp-1E0h]
0x18001c054  sub     rsp, 2E0h
0x18001c05b  mov     rax, cs:__security_cookie
0x18001c062  xor     rax, rsp
0x18001c065  mov     [rbp+210h+var_40], rax
0x18001c06c  mov     rdi, [rbp+210h+arg_28]
0x18001c073  mov     rbx, r8
0x18001c076  mov     r12, rdx
0x18001c079  mov     [rsp+310h+var_2C8], ecx
0x18001c07d  xor     edx, edx; Val
0x18001c07f  mov     [rsp+310h+var_2B0], rbx
0x18001c084  mov     r8d, 250h; Size
0x18001c08a  mov     [rsp+310h+var_2B4], r9d
0x18001c08f  lea     rcx, [rbp+210h+FindFileData]; void *
0x18001c093  xor     r13d, r13d
0x18001c096  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001c09a  call    memset_0
0x18001c09f  xor     r14d, r14d
0x18001c0a2  mov     [rsp+310h+var_2B8], r13d
0x18001c0a7  lea     rdx, CAPI2_CATDB_SYNC_SUBSYSTEM_START_EVENT
0x18001c0ae  mov     [rsp+310h+var_2C0], r14
0x18001c0b3  mov     rcx, rbx
0x18001c0b6  mov     [rsp+310h+var_2A0], r13d
0x18001c0bb  mov     [rsp+310h+var_2A4], r13d
0x18001c0c0  mov     [rsp+310h+var_2A8], r13d
0x18001c0c5  mov     dword ptr [rsp+310h+hFindFile], r13d
0x18001c0ca  mov     [rsp+310h+var_2C4], r13d
0x18001c0cf  call    I_CatDBEventSubsystemTemplate
0x18001c0d4  mov     rcx, cs:?g_pwszDatabaseFileBaseDirectory@@3PEAGEA; lpFileName
0x18001c0db  mov     rdx, rbx; unsigned __int16 *
0x18001c0de  mov     [rdi], r13d
0x18001c0e1  call    ?_CatDBEnsureDirExists@@YAHPEBG0@Z; _CatDBEnsureDirExists(ushort const *,ushort const *)
0x18001c0e6  test    eax, eax
0x18001c0e8  jnz     short loc_18001C109
0x18001c0ea  mov     dword ptr [rsp+310h+var_2F0], r13d; int
0x18001c0ef  mov     r8d, 833h; unsigned int
0x18001c0f5  xor     r9d, r9d; unsigned int
0x18001c0f8  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001c0fd  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001c102  mov     ebx, eax
0x18001c104  jmp     loc_18001C60B
0x18001c109  mov     eax, [rsp+310h+var_2B4]
0x18001c10d  lea     rcx, [rsp+310h+var_2C0]
0x18001c112  mov     r14d, [rsp+310h+var_2C8]
0x18001c117  xor     ebx, ebx
0x18001c119  mov     rdx, [rsp+310h+var_2B0]
0x18001c11e  mov     r8d, r14d
0x18001c121  mov     dword ptr [rsp+310h+var_2E8], eax; int
0x18001c125  mov     dword ptr [rsp+310h+var_2F0], 0FFFFFFFFh
0x18001c12d  lea     r9d, [rbx+2]
0x18001c131  lea     r15d, [rbx+1]
0x18001c135  call    ?_CatDBAcquireOpenDatabaseFromCache@@YAHPEAPEAU_JET_DB_STRUCT@@PEBGHW4__MIDL_ICatDBSvc_0002@@KH@Z; _CatDBAcquireOpenDatabaseFromCache(_JET_DB_STRUCT * *,ushort const *,int,__MIDL_ICatDBSvc_0002,ulong,int)
0x18001c13a  test    eax, eax
0x18001c13c  jnz     short loc_18001C16E
0x18001c13e  test    r14d, r14d
0x18001c141  jz      short loc_18001C14B
0x18001c143  mov     [rdi], r15d
0x18001c146  jmp     loc_18001C58C
0x18001c14b  xor     r9d, r9d; unsigned int
0x18001c14e  mov     dword ptr [rsp+310h+var_2F0], ebx; int
0x18001c152  mov     r8d, 849h; unsigned int
0x18001c158  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001c15d  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001c162  mov     r14, [rsp+310h+var_2C0]
0x18001c167  mov     ebx, eax
0x18001c169  jmp     loc_18001C60B
0x18001c16e  mov     r14, [rsp+310h+var_2C0]
0x18001c173  mov     [rsp+310h+var_2B8], r15d
0x18001c178  cmp     [rbp+210h+arg_20], ebx
0x18001c17e  jnz     short loc_18001C1AD
0x18001c180  lea     r8, [rsp+310h+hFindFile]; int *
0x18001c185  mov     rdx, r12; lpFileName
0x18001c188  mov     rcx, r14; struct _JET_DB_STRUCT *
0x18001c18b  call    ?_CatDBIsCatalogPathChanged@@YAHPEAU_JET_DB_STRUCT@@PEBGPEAH@Z; _CatDBIsCatalogPathChanged(_JET_DB_STRUCT *,ushort const *,int *)
0x18001c190  mov     ecx, dword ptr [rsp+310h+hFindFile]
0x18001c194  test    eax, eax
0x18001c196  mov     edx, r15d
0x18001c199  cmovz   ecx, edx
0x18001c19c  cmp     [rsp+310h+var_2C8], ebx
0x18001c1a0  jnz     short loc_18001C1A6
0x18001c1a2  test    ecx, ecx
0x18001c1a4  jnz     short loc_18001C1AD
0x18001c1a6  mov     [rdi], ecx
0x18001c1a8  jmp     loc_18001C51C
0x18001c1ad  mov     rdi, [rsp+310h+var_2B0]
0x18001c1b2  lea     rdx, aSyncdbSyncStar; "SyncDB:: Sync started for database "
0x18001c1b9  mov     ebx, r15d
0x18001c1bc  mov     r8, rdi; unsigned __int16 *
0x18001c1bf  mov     r9d, ebx; int
0x18001c1c2  xor     ecx, ecx; unsigned __int16 *
0x18001c1c4  call    ?ErrLog_LogString@@YAXPEAG00H@Z; ErrLog_LogString(ushort *,ushort *,ushort *,int)
0x18001c1c9  xor     r9d, r9d
0x18001c1cc  lea     rdx, ?_CatDBRunOnceShouldOnlySyncPresentCatalogs@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; _CatDBRunOnceShouldOnlySyncPresentCatalogs(_RTL_RUN_ONCE *,void *,void * *)
0x18001c1d3  xor     r8d, r8d
0x18001c1d6  lea     rcx, qword_180032A58
0x18001c1dd  call    cs:__imp_RtlRunOnceExecuteOnce
0x18001c1e3  test    eax, eax
0x18001c1e5  js      short loc_18001C1FC
0x18001c1e7  cmp     cs:?g_fFilterNonePresentCatalogs@@3HA, r13d; int g_fFilterNonePresentCatalogs
0x18001c1ee  jz      short loc_18001C1FC
0x18001c1f0  mov     r9d, ebx
0x18001c1f3  lea     rdx, aSyncdbSyncOnly; "SyncDB:: Sync only present catalogs"
0x18001c1fa  jmp     short loc_18001C268
0x18001c1fc  mov     edx, cs:dword_180032714; int
0x18001c202  lea     r9, [rsp+310h+var_2A8]; unsigned int *
0x18001c207  mov     r8, r12; unsigned __int16 *
0x18001c20a  mov     rcx, r14; struct _JET_DB_STRUCT *
0x18001c20d  call    ?_CatDBDeleteInvalidCatalogFilesFromDatabase@@YAHPEAU_JET_DB_STRUCT@@HPEBGPEAK@Z; _CatDBDeleteInvalidCatalogFilesFromDatabase(_JET_DB_STRUCT *,int,ushort const *,ulong *)
0x18001c212  test    eax, eax
0x18001c214  jnz     short loc_18001C272
0x18001c216  call    cs:__imp_GetLastError
0x18001c21c  mov     r8d, 874h; unsigned int
0x18001c222  mov     dword ptr [rsp+310h+var_2F0], r13d; int
0x18001c227  mov     r9d, eax; unsigned int
0x18001c22a  mov     ebx, eax
0x18001c22c  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001c231  cmp     ebx, 12Fh
0x18001c237  jnz     short loc_18001C25E
0x18001c239  cmp     cs:dword_180032714, r13d
0x18001c240  jz      loc_18001C0FD
0x18001c246  mov     ebx, r15d
0x18001c249  lea     rdx, aSyncdbEnabling; "SyncDB:: Enabling enum filtering for "
0x18001c250  mov     cs:?g_fFilterNonePresentCatalogs@@3HA, ebx; int g_fFilterNonePresentCatalogs
0x18001c256  mov     r9d, ebx
0x18001c259  mov     r8, rdi
0x18001c25c  jmp     short loc_18001C26B
0x18001c25e  mov     r9d, r15d; int
0x18001c261  lea     rdx, aSyncdbDeletein; "SyncDB:: DeleteInvalidCatalogFilesFromD"...
0x18001c268  xor     r8d, r8d; unsigned __int16 *
0x18001c26b  xor     ecx, ecx; unsigned __int16 *
0x18001c26d  call    ?ErrLog_LogString@@YAXPEAG00H@Z; ErrLog_LogString(ushort *,ushort *,ushort *,int)
0x18001c272  lea     rdx, aCat; "*.cat"
0x18001c279  mov     rcx, r12; unsigned __int16 *
0x18001c27c  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001c281  mov     r13, rax
0x18001c284  test    rax, rax
0x18001c287  jnz     short loc_18001C298
0x18001c289  mov     dword ptr [rsp+310h+var_2F0], eax
0x18001c28d  mov     r8d, 899h
0x18001c293  jmp     loc_18001C0F5
0x18001c298  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x18001c29c  mov     rcx, rax; lpFileName
0x18001c29f  call    cs:__imp_FindFirstFileW
0x18001c2a5  mov     [rsp+310h+hFindFile], rax
0x18001c2aa  mov     rsi, rax
0x18001c2ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c2b1  jnz     short loc_18001C2E2
0x18001c2b3  call    cs:__imp_GetLastError
0x18001c2b9  mov     ebx, eax
0x18001c2bb  lea     ecx, [rax-2]
0x18001c2be  test    ecx, 0FFFFFFEEh
0x18001c2c4  jnz     short loc_18001C2CF
0x18001c2c6  cmp     eax, 13h
0x18001c2c9  jnz     loc_18001C4EA
0x18001c2cf  mov     dword ptr [rsp+310h+var_2F0], 0
0x18001c2d7  mov     r8d, 8B2h
0x18001c2dd  jmp     loc_18001C0F5
0x18001c2e2  xor     esi, esi
0x18001c2e4  xor     ebx, ebx
0x18001c2e6  test    byte ptr [rbp+210h+FindFileData.dwFileAttributes], 10h
0x18001c2ea  jnz     loc_18001C3D8
0x18001c2f0  mov     eax, [rbp+210h+FindFileData.nFileSizeLow]
0x18001c2f3  mov     dword ptr [rsp+310h+var_2C0], eax
0x18001c2f7  mov     eax, [rbp+210h+FindFileData.nFileSizeHigh]
0x18001c2fa  mov     dword ptr [rsp+310h+var_2C0+4], eax
0x18001c2fe  mov     rdi, [rsp+310h+var_2C0]
0x18001c303  add     rbx, rdi
0x18001c306  cmp     rbx, 200000h
0x18001c30d  jg      short loc_18001C314
0x18001c30f  cmp     rbx, rdi
0x18001c312  jge     short loc_18001C33B
0x18001c314  test    esi, esi
0x18001c316  jz      short loc_18001C338
0x18001c318  mov     rcx, [r14+8]; sesid
0x18001c31c  mov     edx, r15d; grbit
0x18001c31f  call    cs:__imp_JetCommitTransaction
0x18001c325  mov     ecx, eax; int
0x18001c327  mov     ebx, eax
0x18001c329  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001c32e  test    eax, eax
0x18001c330  jnz     loc_18001C433
0x18001c336  dec     esi
0x18001c338  mov     rbx, rdi
0x18001c33b  test    esi, esi
0x18001c33d  jnz     short loc_18001C35D
0x18001c33f  mov     rcx, [r14+8]; sesid
0x18001c343  call    cs:__imp_JetBeginTransaction
0x18001c349  mov     ecx, eax; int
0x18001c34b  mov     edi, eax
0x18001c34d  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001c352  test    eax, eax
0x18001c354  jnz     loc_18001C461
0x18001c35a  mov     esi, r15d
0x18001c35d  mov     rdx, [rsp+310h+var_2B0]; unsigned __int16 *
0x18001c362  lea     rax, [rsp+310h+var_2A8]
0x18001c367  mov     [rsp+310h+var_2E0], rax; unsigned int *
0x18001c36c  lea     r9, [rbp+210h+FindFileData]; struct _WIN32_FIND_DATAW *
0x18001c370  lea     rax, [rsp+310h+var_2A4]
0x18001c375  mov     r8, r12; unsigned __int16 *
0x18001c378  mov     [rsp+310h+var_2E8], rax; int
0x18001c37d  mov     rcx, r14; struct _JET_DB_STRUCT *
0x18001c380  lea     rax, [rsp+310h+var_2A0]
0x18001c385  mov     [rsp+310h+var_2F0], rax; unsigned int *
0x18001c38a  call    ?_CatDBSyncCatalogFile@@YAHPEAU_JET_DB_STRUCT@@PEBG1PEBU_WIN32_FIND_DATAW@@PEAK33@Z; _CatDBSyncCatalogFile(_JET_DB_STRUCT *,ushort const *,ushort const *,_WIN32_FIND_DATAW const *,ulong *,ulong *,ulong *)
0x18001c38f  test    eax, eax
0x18001c391  jnz     short loc_18001C3D4
0x18001c393  call    cs:__imp_GetLastError
0x18001c399  mov     r8d, 8F7h; unsigned int
0x18001c39f  mov     dword ptr [rsp+310h+var_2F0], 0; int
0x18001c3a7  mov     r9d, eax; unsigned int
0x18001c3aa  mov     edi, eax
0x18001c3ac  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001c3b1  cmp     edi, 12Fh
0x18001c3b7  jz      loc_18001C492
0x18001c3bd  mov     r9d, r15d; int
0x18001c3c0  lea     r8, [rbp+210h+FindFileData.cFileName]; unsigned __int16 *
0x18001c3c4  lea     rdx, aSyncdbSynccata; "SyncDB:: SyncCatalogFile failed, will c"...
0x18001c3cb  xor     ecx, ecx; unsigned __int16 *
0x18001c3cd  call    ?ErrLog_LogString@@YAXPEAG00H@Z; ErrLog_LogString(ushort *,ushort *,ushort *,int)
0x18001c3d2  jmp     short loc_18001C3D8
0x18001c3d4  inc     [rsp+310h+var_2C4]
0x18001c3d8  mov     rcx, [rsp+310h+hFindFile]; hFindFile
0x18001c3dd  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x18001c3e1  call    cs:__imp_FindNextFileW
0x18001c3e7  test    eax, eax
0x18001c3e9  jnz     loc_18001C2E6
0x18001c3ef  call    cs:__imp_GetLastError
0x18001c3f5  mov     ebx, eax
0x18001c3f7  test    esi, esi
0x18001c3f9  jz      loc_18001C4DC
0x18001c3ff  mov     rcx, [r14+8]; sesid
0x18001c403  xor     edx, edx; grbit
0x18001c405  call    cs:__imp_JetCommitTransaction
0x18001c40b  mov     ecx, eax; int
0x18001c40d  mov     edi, eax
0x18001c40f  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001c414  test    eax, eax
0x18001c416  jz      loc_18001C4DA
0x18001c41c  mov     ecx, edi; int
0x18001c41e  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001c423  mov     ecx, eax; dwErrCode
0x18001c425  call    cs:__imp_SetLastError
0x18001c42b  mov     r8d, 924h
0x18001c431  jmp     short loc_18001C448
0x18001c433  mov     ecx, ebx; int
0x18001c435  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001c43a  mov     ecx, eax; dwErrCode
0x18001c43c  call    cs:__imp_SetLastError
0x18001c442  mov     r8d, 8D7h; unsigned int
0x18001c448  xor     r9d, r9d; unsigned int
0x18001c44b  mov     dword ptr [rsp+310h+var_2F0], r9d; int
0x18001c450  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001c455  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001c45a  mov     ebx, eax
0x18001c45c  jmp     loc_18001C5F5
0x18001c461  mov     ecx, edi; int
0x18001c463  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001c468  mov     ecx, eax; dwErrCode
0x18001c46a  call    cs:__imp_SetLastError
0x18001c470  xor     r9d, r9d; unsigned int
0x18001c473  mov     dword ptr [rsp+310h+var_2F0], 0; int
0x18001c47b  mov     r8d, 8E6h; unsigned int
0x18001c481  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001c486  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001c48b  mov     ebx, eax
0x18001c48d  jmp     loc_18001C606
0x18001c492  mov     rcx, [r14+8]; sesid
0x18001c496  xor     edx, edx; grbit
0x18001c498  call    cs:__imp_JetCommitTransaction
0x18001c49e  mov     ecx, eax; int
0x18001c4a0  mov     ebx, eax
0x18001c4a2  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001c4a7  test    eax, eax
0x18001c4a9  jz      short loc_18001C4C8
0x18001c4ab  mov     ecx, ebx; int
0x18001c4ad  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001c4b2  mov     ecx, eax; dwErrCode
0x18001c4b4  call    cs:__imp_SetLastError
0x18001c4ba  xor     r9d, r9d
0x18001c4bd  mov     r8d, 901h
0x18001c4c3  jmp     loc_18001C5DD
0x18001c4c8  mov     ecx, 12Fh; dwErrCode
0x18001c4cd  call    cs:__imp_SetLastError
0x18001c4d3  dec     esi
0x18001c4d5  jmp     loc_18001C5EA
0x18001c4da  dec     esi
0x18001c4dc  cmp     ebx, 12h
0x18001c4df  jnz     loc_18001C5D4
0x18001c4e5  mov     rsi, [rsp+310h+hFindFile]
0x18001c4ea  cmp     cs:?g_fFilterNonePresentCatalogs@@3HA, 0; int g_fFilterNonePresentCatalogs
0x18001c4f1  jnz     short loc_18001C519
0x18001c4f3  xor     r8d, r8d; int
  ... truncated ...
```
