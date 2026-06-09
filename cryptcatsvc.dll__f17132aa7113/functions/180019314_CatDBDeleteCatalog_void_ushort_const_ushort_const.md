# _CatDBDeleteCatalog(void *,ushort const *,ushort const *)

- ea: `0x180019314`
- end: `0x180019663`
- name: `?_CatDBDeleteCatalog@@YAKPEAXPEBG1@Z`
- size: `847`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001c9e0`

## callees

- `0x1800015b0`
- `0x180001950`
- `0x180002410`
- `0x1800038f0`
- `0x180003d48`
- `0x180008888`
- `0x18000a57c`
- `0x18000a59c`
- `0x18000acbc`
- `0x1800130a0`
- `0x180019314`
- `0x18001b4dc`
- `0x18001c7d4`
- `0x18001cf60`
- `0x18001dcf8`
- `0x18001f748`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800193a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800193a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019643`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019539`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001938c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019443`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800194b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019518`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019576`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001938c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019443`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800194b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019518`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019576`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001952f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001952f`
- `RPCRT4!RpcRevertToSelf` at `0x18001956a`
- `RPCRT4!RpcRevertToSelf` at `0x180019596`
- `RPCRT4!RpcRevertToSelf` at `0x18001956a`
- `RPCRT4!RpcRevertToSelf` at `0x180019596`
- `RPCRT4!RpcImpersonateClient` at `0x18001950c`
- `RPCRT4!RpcImpersonateClient` at `0x18001950c`
- `ESENT!JetBeginTransaction` at `0x180019425`
- `ESENT!JetBeginTransaction` at `0x180019425`
- `ESENT!JetRollback` at `0x1800195fd`
- `ESENT!JetRollback` at `0x1800195fd`
- `ESENT!JetCommitTransaction` at `0x180019498`
- `ESENT!JetCommitTransaction` at `0x180019498`

## string_xrefs

- `0x1800195e1`: `DeleteCatalog(%s):: ERROR_ACCESS_DENIED`

## pseudocode

```c
__int64 __fastcall _CatDBDeleteCatalog(
        RPC_BINDING_HANDLE BindingHandle,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  struct _JET_DB_STRUCT *v4; // rsi
  int v5; // r15d
  WCHAR *v7; // rdi
  int v8; // r13d
  const WCHAR *v9; // rax
  unsigned int v10; // edx
  unsigned __int16 *v11; // rcx
  unsigned __int16 *v12; // r14
  unsigned int v13; // r8d
  unsigned int Error; // eax
  int v15; // ebp
  DWORD v16; // eax
  unsigned int v17; // ebx
  unsigned int v18; // edx
  unsigned __int16 *v19; // rcx
  JET_ERR v20; // r15d
  DWORD v21; // eax
  unsigned int v22; // edx
  unsigned __int16 *v23; // rcx
  unsigned int v24; // edx
  unsigned __int16 *v25; // rcx
  JET_ERR v26; // r15d
  DWORD v27; // eax
  unsigned int v28; // edx
  unsigned __int16 *v29; // rcx
  unsigned int v30; // edx
  unsigned __int16 *v31; // rcx
  RPC_STATUS v32; // eax
  unsigned int v33; // edx
  unsigned __int16 *v34; // rcx
  unsigned int v35; // r8d
  int v36; // ebp
  DWORD LastError; // eax
  unsigned int v38; // edx
  unsigned __int16 *v39; // rcx
  RPC_STATUS v40; // eax
  unsigned int v41; // edx
  unsigned __int16 *v42; // rcx
  int v44; // [rsp+28h] [rbp-50h]
  int v45; // [rsp+28h] [rbp-50h]
  struct _JET_DB_STRUCT *v46; // [rsp+38h] [rbp-40h] BYREF

  v4 = 0;
  v5 = 0;
  v46 = 0;
  v7 = 0;
  v8 = 0;
  v9 = _CATDBConstructWSTRPath(g_pwszCatalogFileBaseDirectory, a2);
  v12 = (unsigned __int16 *)v9;
  if ( v9 )
  {
    v16 = _CatDBCanWriteToPathWithImpersonation(BindingHandle, v9);
    v17 = v16;
    if ( v16 )
    {
      SetLastError(v16);
      v13 = 3183;
      goto LABEL_3;
    }
    EnterCriticalSection(&g_CatDBAddDeleteCS);
    v8 = 1;
    v7 = _CATDBConstructWSTRPath(v12, a3);
    if ( !v7 )
    {
      v13 = 3198;
      goto LABEL_3;
    }
    v45 = 0;
    if ( !(unsigned int)_CatDBAcquireOpenDatabaseFromCache(&v46, a2, 0, 2, -1) )
    {
      ErrLog_LogError(v19, v18, 0xC8Au, 0, 0, 0);
      Error = _CatDBGetNonzeroLastError();
      v4 = v46;
      v15 = 0;
      goto LABEL_33;
    }
    CatDBSetWriteJetDatabaseParams();
    v4 = v46;
    v20 = JetBeginTransaction(*((_QWORD *)v46 + 1));
    if ( (unsigned int)_CatDBJET_errFailure(v20) )
    {
      v21 = _CatDBMapJetError(v20);
      SetLastError(v21);
      ErrLog_LogError(v23, v22, 0xC97u, 0, 0, 0);
      Error = _CatDBGetNonzeroLastError();
      v5 = 0;
LABEL_32:
      v15 = 1;
      goto LABEL_33;
    }
    v5 = 1;
    if ( (unsigned int)_CatDBDeleteCatalogEntriesFromDatabase(v4, v7, 0) )
    {
      v26 = JetCommitTransaction(*((_QWORD *)v4 + 1), 0);
      if ( (unsigned int)_CatDBJET_errFailure(v26) )
      {
        v27 = _CatDBMapJetError(v26);
        SetLastError(v27);
        ErrLog_LogError(v29, v28, 0xCB0u, 0, 0, 0);
        Error = _CatDBGetNonzeroLastError();
        v5 = 1;
        goto LABEL_32;
      }
      v5 = 0;
      if ( !(unsigned int)_CatDBIgnoreChangesForFile(a2, a3) )
        ErrLog_LogError(v31, v30, 0xCBBu, 0, 0, 0);
      v32 = RpcImpersonateClient(BindingHandle);
      if ( v32 )
      {
        SetLastError(v32);
        v35 = 3267;
      }
      else
      {
        v36 = 1;
        if ( !DeleteFileW(v7) )
        {
          LastError = GetLastError();
          if ( LastError != 123 && LastError != 2 && !(unsigned int)_CatDBMoveInUseFileToTempLocation(v7) )
          {
            ErrLog_LogError(v39, v38, 0xCD8u, 0, 0, v45);
            v36 = 0;
          }
        }
        v40 = RpcRevertToSelf();
        if ( v40 )
        {
          SetLastError(v40);
          ErrLog_LogError(v42, v41, 0xCE9u, 0, 0, v45);
          v17 = _CatDBGetNonzeroLastError();
          RpcRevertToSelf();
          v15 = 1;
          goto LABEL_34;
        }
        if ( !v36 || (unsigned int)_CatDBUpdateCatalogPathChangedTime(v4, v12, 0) )
        {
          _CatDBReleaseDatabaseToCache(v4, 0);
LABEL_43:
          _CatDBFree(v7);
          goto LABEL_44;
        }
        v35 = 3316;
      }
      ErrLog_LogError(v34, v33, v35, 0, 0, v45);
    }
    else
    {
      ErrLog_LogError(v25, v24, 0xCA4u, 0, 0, 0);
    }
    Error = _CatDBGetNonzeroLastError();
    goto LABEL_32;
  }
  v13 = 3175;
LABEL_3:
  ErrLog_LogError(v11, v10, v13, 0, 0, v44);
  Error = _CatDBGetNonzeroLastError();
  v15 = 0;
LABEL_33:
  v17 = Error;
LABEL_34:
  if ( v17 == 5 )
    ErrLog_LogPrintfW(0, 1, L"DeleteCatalog(%s):: ERROR_ACCESS_DENIED", a3);
  if ( v5 )
    JetRollback(*((_QWORD *)v4 + 1), 0);
  if ( v15 )
    _CatDBReleaseDatabaseToCache(v4, 0);
  if ( v7 )
    goto LABEL_43;
LABEL_44:
  if ( v12 )
    _CatDBFree(v12);
  if ( v8 )
    LeaveCriticalSection(&g_CatDBAddDeleteCS);
  return v17;
}

```

## disassembly

```asm
0x180019314  mov     [rsp+arg_0], rbx
0x180019319  mov     [rsp+arg_10], r8
0x18001931e  push    rbp
0x18001931f  push    rsi
0x180019320  push    rdi
0x180019321  push    r12
0x180019323  push    r13
0x180019325  push    r14
0x180019327  push    r15
0x180019329  sub     rsp, 40h
0x18001932d  mov     r12, rcx
0x180019330  xor     esi, esi
0x180019332  mov     rcx, cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA; unsigned __int16 *
0x180019339  xor     r15d, r15d
0x18001933c  mov     [rsp+78h+var_40], rsi
0x180019341  mov     rbp, rdx
0x180019344  mov     [rsp+78h+var_48], r15d
0x180019349  xor     edi, edi
0x18001934b  xor     r13d, r13d
0x18001934e  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x180019353  mov     r14, rax
0x180019356  test    rax, rax
0x180019359  jnz     short loc_180019379
0x18001935b  mov     r8d, 0C67h; unsigned int
0x180019361  xor     r9d, r9d; unsigned int
0x180019364  mov     [rsp+78h+var_58], esi; int
0x180019368  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001936d  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x180019372  mov     ebp, esi
0x180019374  jmp     loc_1800195D2
0x180019379  mov     rdx, r14; lpFileName
0x18001937c  mov     rcx, r12; BindingHandle
0x18001937f  call    ?_CatDBCanWriteToPathWithImpersonation@@YAKPEAXPEBG@Z; _CatDBCanWriteToPathWithImpersonation(void *,ushort const *)
0x180019384  mov     ebx, eax
0x180019386  test    eax, eax
0x180019388  jz      short loc_18001939A
0x18001938a  mov     ecx, eax; dwErrCode
0x18001938c  call    cs:__imp_SetLastError
0x180019392  mov     r8d, 0C6Fh
0x180019398  jmp     short loc_180019361
0x18001939a  lea     rcx, ?g_CatDBAddDeleteCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800193a1  call    cs:__imp_EnterCriticalSection
0x1800193a7  mov     rdx, [rsp+78h+arg_10]; unsigned __int16 *
0x1800193af  mov     rcx, r14; unsigned __int16 *
0x1800193b2  mov     r13d, 1
0x1800193b8  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x1800193bd  mov     rdi, rax
0x1800193c0  test    rax, rax
0x1800193c3  jnz     short loc_1800193CD
0x1800193c5  mov     r8d, 0C7Eh
0x1800193cb  jmp     short loc_180019361
0x1800193cd  mov     [rsp+78h+var_50], esi; int
0x1800193d1  lea     rcx, [rsp+78h+var_40]
0x1800193d6  mov     r9d, 2
0x1800193dc  mov     [rsp+78h+var_58], 0FFFFFFFFh
0x1800193e4  xor     r8d, r8d
0x1800193e7  mov     rdx, rbp
0x1800193ea  call    ?_CatDBAcquireOpenDatabaseFromCache@@YAHPEAPEAU_JET_DB_STRUCT@@PEBGHW4__MIDL_ICatDBSvc_0002@@KH@Z; _CatDBAcquireOpenDatabaseFromCache(_JET_DB_STRUCT * *,ushort const *,int,__MIDL_ICatDBSvc_0002,ulong,int)
0x1800193ef  test    eax, eax
0x1800193f1  jnz     short loc_180019417
0x1800193f3  xor     r9d, r9d; unsigned int
0x1800193f6  mov     [rsp+78h+var_58], esi; int
0x1800193fa  mov     r8d, 0C8Ah; unsigned int
0x180019400  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180019405  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001940a  mov     rsi, [rsp+78h+var_40]
0x18001940f  mov     ebp, r15d
0x180019412  jmp     loc_1800195D2
0x180019417  call    _CatDBSetWriteJetDatabaseParams
0x18001941c  mov     rsi, [rsp+78h+var_40]
0x180019421  mov     rcx, [rsi+8]; sesid
0x180019425  call    cs:__imp_JetBeginTransaction
0x18001942b  mov     ecx, eax; int
0x18001942d  mov     r15d, eax
0x180019430  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180019435  test    eax, eax
0x180019437  jz      short loc_18001946E
0x180019439  mov     ecx, r15d; int
0x18001943c  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180019441  mov     ecx, eax; dwErrCode
0x180019443  call    cs:__imp_SetLastError
0x180019449  xor     r9d, r9d; unsigned int
0x18001944c  mov     [rsp+78h+var_58], 0; int
0x180019454  mov     r8d, 0C97h; unsigned int
0x18001945a  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001945f  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x180019464  mov     r15d, [rsp+78h+var_48]
0x180019469  jmp     loc_1800195CF
0x18001946e  xor     r8d, r8d; int
0x180019471  mov     rdx, rdi; Str
0x180019474  mov     rcx, rsi; struct _JET_DB_STRUCT *
0x180019477  mov     r15d, r13d
0x18001947a  call    ?_CatDBDeleteCatalogEntriesFromDatabase@@YAHPEAU_JET_DB_STRUCT@@PEBGH@Z; _CatDBDeleteCatalogEntriesFromDatabase(_JET_DB_STRUCT *,ushort const *,int)
0x18001947f  test    eax, eax
0x180019481  jnz     short loc_180019492
0x180019483  mov     [rsp+78h+var_58], eax
0x180019487  mov     r8d, 0CA4h
0x18001948d  jmp     loc_1800195C2
0x180019492  mov     rcx, [rsi+8]; sesid
0x180019496  xor     edx, edx; grbit
0x180019498  call    cs:__imp_JetCommitTransaction
0x18001949e  mov     ecx, eax; int
0x1800194a0  mov     r15d, eax
0x1800194a3  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800194a8  test    eax, eax
0x1800194aa  jz      short loc_1800194DF
0x1800194ac  mov     ecx, r15d; int
0x1800194af  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800194b4  mov     ecx, eax; dwErrCode
0x1800194b6  call    cs:__imp_SetLastError
0x1800194bc  xor     r9d, r9d; unsigned int
0x1800194bf  mov     [rsp+78h+var_58], 0; int
0x1800194c7  mov     r8d, 0CB0h; unsigned int
0x1800194cd  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800194d2  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x1800194d7  mov     r15d, r13d
0x1800194da  jmp     loc_1800195CF
0x1800194df  mov     rdx, [rsp+78h+arg_10]; unsigned __int16 *
0x1800194e7  mov     rcx, rbp; unsigned __int16 *
0x1800194ea  xor     r15d, r15d
0x1800194ed  call    ?_CatDBIgnoreChangesForFile@@YAHPEBG0@Z; _CatDBIgnoreChangesForFile(ushort const *,ushort const *)
0x1800194f2  test    eax, eax
0x1800194f4  jnz     short loc_180019509
0x1800194f6  xor     r9d, r9d; unsigned int
0x1800194f9  mov     [rsp+78h+var_58], r15d; int
0x1800194fe  mov     r8d, 0CBBh; unsigned int
0x180019504  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180019509  mov     rcx, r12; BindingHandle
0x18001950c  call    cs:__imp_RpcImpersonateClient
0x180019512  test    eax, eax
0x180019514  jz      short loc_180019529
0x180019516  mov     ecx, eax; dwErrCode
0x180019518  call    cs:__imp_SetLastError
0x18001951e  mov     r8d, 0CC3h
0x180019524  jmp     loc_1800195BD
0x180019529  mov     rcx, rdi; lpFileName
0x18001952c  mov     ebp, r13d
0x18001952f  call    cs:__imp_DeleteFileW
0x180019535  test    eax, eax
0x180019537  jnz     short loc_18001956A
0x180019539  call    cs:__imp_GetLastError
0x18001953f  cmp     eax, 7Bh ; '{'
0x180019542  jz      short loc_18001956A
0x180019544  cmp     eax, 2
0x180019547  jz      short loc_18001956A
0x180019549  mov     rcx, rdi; lpExistingFileName
0x18001954c  call    ?_CatDBMoveInUseFileToTempLocation@@YAHPEBG@Z; _CatDBMoveInUseFileToTempLocation(ushort const *)
0x180019551  test    eax, eax
0x180019553  jnz     short loc_18001956A
0x180019555  xor     r9d, r9d; unsigned int
0x180019558  mov     [rsp+78h+var_58], r15d; int
0x18001955d  mov     r8d, 0CD8h; unsigned int
0x180019563  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180019568  xor     ebp, ebp
0x18001956a  call    cs:__imp_RpcRevertToSelf
0x180019570  test    eax, eax
0x180019572  jz      short loc_1800195A1
0x180019574  mov     ecx, eax; dwErrCode
0x180019576  call    cs:__imp_SetLastError
0x18001957c  xor     r9d, r9d; unsigned int
0x18001957f  mov     [rsp+78h+var_58], r15d; int
0x180019584  mov     r8d, 0CE9h; unsigned int
0x18001958a  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001958f  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x180019594  mov     ebx, eax
0x180019596  call    cs:__imp_RpcRevertToSelf
0x18001959c  mov     ebp, r13d
0x18001959f  jmp     short loc_1800195D4
0x1800195a1  test    ebp, ebp
0x1800195a3  jz      short loc_180019618
0x1800195a5  xor     r8d, r8d; int
0x1800195a8  mov     rdx, r14; lpFileName
0x1800195ab  mov     rcx, rsi; struct _JET_DB_STRUCT *
0x1800195ae  call    ?_CatDBUpdateCatalogPathChangedTime@@YAHPEAU_JET_DB_STRUCT@@PEBGH@Z; _CatDBUpdateCatalogPathChangedTime(_JET_DB_STRUCT *,ushort const *,int)
0x1800195b3  test    eax, eax
0x1800195b5  jnz     short loc_180019618
0x1800195b7  mov     r8d, 0CF4h; unsigned int
0x1800195bd  mov     [rsp+78h+var_58], r15d; int
0x1800195c2  xor     r9d, r9d; unsigned int
0x1800195c5  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800195ca  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x1800195cf  mov     ebp, r13d
0x1800195d2  mov     ebx, eax
0x1800195d4  cmp     ebx, 5
0x1800195d7  jnz     short loc_1800195F2
0x1800195d9  mov     r9, [rsp+78h+arg_10]
0x1800195e1  lea     r8, aDeletecatalogS; "DeleteCatalog(%s):: ERROR_ACCESS_DENIED"
0x1800195e8  lea     edx, [rbx-4]; int
0x1800195eb  xor     ecx, ecx; unsigned __int16 *
0x1800195ed  call    ?ErrLog_LogPrintfW@@YAXPEAGHPEBGZZ; ErrLog_LogPrintfW(ushort *,int,ushort const *,...)
0x1800195f2  test    r15d, r15d
0x1800195f5  jz      short loc_180019603
0x1800195f7  mov     rcx, [rsi+8]; sesid
0x1800195fb  xor     edx, edx; grbit
0x1800195fd  call    cs:__imp_JetRollback
0x180019603  test    ebp, ebp
0x180019605  jz      short loc_180019611
0x180019607  xor     edx, edx; int
0x180019609  mov     rcx, rsi; struct _JET_DB_STRUCT *
0x18001960c  call    ?_CatDBReleaseDatabaseToCache@@YAHPEAU_JET_DB_STRUCT@@H@Z; _CatDBReleaseDatabaseToCache(_JET_DB_STRUCT *,int)
0x180019611  test    rdi, rdi
0x180019614  jz      short loc_18001962A
0x180019616  jmp     short loc_180019622
0x180019618  xor     edx, edx; int
0x18001961a  mov     rcx, rsi; struct _JET_DB_STRUCT *
0x18001961d  call    ?_CatDBReleaseDatabaseToCache@@YAHPEAU_JET_DB_STRUCT@@H@Z; _CatDBReleaseDatabaseToCache(_JET_DB_STRUCT *,int)
0x180019622  mov     rcx, rdi; void *
0x180019625  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001962a  test    r14, r14
0x18001962d  jz      short loc_180019637
0x18001962f  mov     rcx, r14; void *
0x180019632  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x180019637  test    r13d, r13d
0x18001963a  jz      short loc_180019649
0x18001963c  lea     rcx, ?g_CatDBAddDeleteCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019643  call    cs:__imp_LeaveCriticalSection
0x180019649  mov     eax, ebx
0x18001964b  mov     rbx, [rsp+78h+arg_0]
0x180019653  add     rsp, 40h
0x180019657  pop     r15
0x180019659  pop     r14
0x18001965b  pop     r13
0x18001965d  pop     r12
0x18001965f  pop     rdi
0x180019660  pop     rsi
0x180019661  pop     rbp
0x180019662  retn
```
