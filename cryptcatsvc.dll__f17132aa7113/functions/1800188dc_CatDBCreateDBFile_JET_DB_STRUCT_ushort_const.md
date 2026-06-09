# _CatDBCreateDBFile(_JET_DB_STRUCT *,ushort const *)

- ea: `0x1800188dc`
- end: `0x180018b2f`
- name: `?_CatDBCreateDBFile@@YAHPEAU_JET_DB_STRUCT@@PEBG@Z`
- size: `595`
- prototype: `__int64 __fastcall(struct _JET_DB_STRUCT *, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180001328`

## callees

- `0x1800038f0`
- `0x18000a59c`
- `0x18000aad4`
- `0x18000acbc`
- `0x18000be40`
- `0x1800188dc`
- `0x180018b38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ab7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018942`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001897d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800189bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800189f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018a55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018a9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018aff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018942`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001897d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800189bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800189f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018a55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018a9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018aff`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180018af7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180018af7`
- `ESENT!JetBeginTransaction` at `0x1800189d5`
- `ESENT!JetBeginTransaction` at `0x1800189d5`
- `ESENT!JetRollback` at `0x180018ac9`
- `ESENT!JetRollback` at `0x180018ac9`
- `ESENT!JetCreateDatabaseW` at `0x180018920`
- `ESENT!JetCreateDatabaseW` at `0x180018920`
- `ESENT!JetCloseDatabase` at `0x180018961`
- `ESENT!JetCloseDatabase` at `0x180018a80`
- `ESENT!JetCloseDatabase` at `0x180018ae9`
- `ESENT!JetCloseDatabase` at `0x180018961`
- `ESENT!JetCloseDatabase` at `0x180018a80`
- `ESENT!JetCloseDatabase` at `0x180018ae9`
- `ESENT!JetCommitTransaction` at `0x180018a37`
- `ESENT!JetCommitTransaction` at `0x180018a37`
- `ESENT!JetOpenDatabaseW` at `0x1800189a1`
- `ESENT!JetOpenDatabaseW` at `0x1800189a1`

## pseudocode

```c
__int64 __fastcall _CatDBCreateDBFile(struct _JET_DB_STRUCT *a1, LPCWSTR lpFileName)
{
  JET_SESID v3; // rcx
  int v4; // ebp
  int v6; // r14d
  JET_ERR v7; // esi
  unsigned int v8; // edi
  int v9; // r15d
  DWORD v10; // eax
  unsigned int v11; // edx
  unsigned __int16 *v12; // rcx
  unsigned int v13; // r8d
  JET_ERR v14; // esi
  DWORD v15; // eax
  JET_ERR v16; // esi
  DWORD v17; // eax
  JET_ERR v18; // esi
  DWORD v19; // eax
  unsigned int v20; // edx
  unsigned __int16 *v21; // rcx
  DWORD LastError; // esi
  JET_ERR v23; // esi
  DWORD v24; // eax
  unsigned int v25; // edx
  unsigned __int16 *v26; // rcx
  JET_ERR v27; // esi
  DWORD v28; // eax
  int v30; // [rsp+28h] [rbp-40h]
  JET_DBID pdbid; // [rsp+30h] [rbp-38h] BYREF

  v3 = *((_QWORD *)a1 + 1);
  v4 = 0;
  pdbid = 0;
  v6 = 0;
  v7 = JetCreateDatabaseW(v3, lpFileName, 0, &pdbid, 0);
  v8 = 1;
  if ( (unsigned int)_CatDBJET_errFailure(v7) )
  {
    v9 = 0;
    v10 = _CatDBMapJetError(v7);
    SetLastError(v10);
    v13 = 6520;
  }
  else
  {
    v9 = 1;
    v14 = JetCloseDatabase(*((_QWORD *)a1 + 1), pdbid, 0);
    if ( (unsigned int)_CatDBJET_errFailure(v14) )
    {
      v15 = _CatDBMapJetError(v14);
      SetLastError(v15);
      v13 = 6530;
    }
    else
    {
      v16 = JetOpenDatabaseW(*((_QWORD *)a1 + 1), lpFileName, 0, &pdbid, 0);
      if ( (unsigned int)_CatDBJET_errFailure(v16) )
      {
        v17 = _CatDBMapJetError(v16);
        SetLastError(v17);
        v13 = 6541;
      }
      else
      {
        v6 = 1;
        v18 = JetBeginTransaction(*((_QWORD *)a1 + 1));
        if ( (unsigned int)_CatDBJET_errFailure(v18) )
        {
          v19 = _CatDBMapJetError(v18);
          SetLastError(v19);
          v13 = 6552;
        }
        else
        {
          if ( !(unsigned int)_CatDBCreateDBTables(a1, pdbid) )
          {
            ErrLog_LogError(v21, v20, 0x199Eu, 0, 0, v30);
            LastError = GetLastError();
LABEL_17:
            JetRollback(*((_QWORD *)a1 + 1), 0);
            _CatDBCloseDBTables(a1, 1);
            goto LABEL_18;
          }
          v23 = JetCommitTransaction(*((_QWORD *)a1 + 1), 0);
          if ( (unsigned int)_CatDBJET_errFailure(v23) )
          {
            v4 = 1;
            v24 = _CatDBMapJetError(v23);
            SetLastError(v24);
            ErrLog_LogError(v26, v25, 0x19AAu, 0, 0, v30);
            goto LABEL_16;
          }
          _CatDBCloseDBTables(a1, 0);
          v27 = JetCloseDatabase(*((_QWORD *)a1 + 1), pdbid, 0);
          if ( !(unsigned int)_CatDBJET_errFailure(v27) )
            return v8;
          v6 = 0;
          v28 = _CatDBMapJetError(v27);
          SetLastError(v28);
          v13 = 6586;
        }
      }
    }
  }
  ErrLog_LogError(v12, v11, v13, 0, 0, v30);
LABEL_16:
  LastError = GetLastError();
  if ( v4 )
    goto LABEL_17;
LABEL_18:
  if ( v6 )
    JetCloseDatabase(*((_QWORD *)a1 + 1), pdbid, 0);
  if ( v9 )
    DeleteFileW(lpFileName);
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x1800188dc  mov     [rsp+arg_10], rbx
0x1800188e1  mov     [rsp+arg_18], rbp
0x1800188e6  push    rsi
0x1800188e7  push    rdi
0x1800188e8  push    r12
0x1800188ea  push    r14
0x1800188ec  push    r15
0x1800188ee  sub     rsp, 40h
0x1800188f2  mov     rax, cs:__security_cookie
0x1800188f9  xor     rax, rsp
0x1800188fc  mov     [rsp+68h+var_30], rax
0x180018901  mov     rbx, rcx
0x180018904  lea     r9, [rsp+68h+pdbid]; pdbid
0x180018909  mov     rcx, [rcx+8]; sesid
0x18001890d  xor     ebp, ebp
0x18001890f  xor     r8d, r8d; szConnect
0x180018912  mov     [rsp+68h+pdbid], ebp
0x180018916  mov     [rsp+68h+grbit], ebp; grbit
0x18001891a  mov     r12, rdx
0x18001891d  xor     r14d, r14d
0x180018920  call    cs:__imp_JetCreateDatabaseW
0x180018926  mov     ecx, eax; int
0x180018928  mov     esi, eax
0x18001892a  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001892f  lea     edi, [rbp+1]
0x180018932  test    eax, eax
0x180018934  jz      short loc_180018953
0x180018936  mov     ecx, esi; int
0x180018938  xor     r15d, r15d
0x18001893b  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018940  mov     ecx, eax; dwErrCode
0x180018942  call    cs:__imp_SetLastError
0x180018948  mov     r8d, 1978h
0x18001894e  jmp     loc_180018AAB
0x180018953  mov     edx, [rsp+68h+pdbid]; dbid
0x180018957  xor     r8d, r8d; grbit
0x18001895a  mov     rcx, [rbx+8]; sesid
0x18001895e  mov     r15d, edi
0x180018961  call    cs:__imp_JetCloseDatabase
0x180018967  mov     ecx, eax; int
0x180018969  mov     esi, eax
0x18001896b  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018970  test    eax, eax
0x180018972  jz      short loc_18001898E
0x180018974  mov     ecx, esi; int
0x180018976  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001897b  mov     ecx, eax; dwErrCode
0x18001897d  call    cs:__imp_SetLastError
0x180018983  mov     r8d, 1982h
0x180018989  jmp     loc_180018AAB
0x18001898e  mov     rcx, [rbx+8]; sesid
0x180018992  lea     r9, [rsp+68h+pdbid]; pdbid
0x180018997  xor     r8d, r8d; szConnect
0x18001899a  mov     [rsp+68h+grbit], ebp; grbit
0x18001899e  mov     rdx, r12; szFilename
0x1800189a1  call    cs:__imp_JetOpenDatabaseW
0x1800189a7  mov     ecx, eax; int
0x1800189a9  mov     esi, eax
0x1800189ab  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800189b0  test    eax, eax
0x1800189b2  jz      short loc_1800189CE
0x1800189b4  mov     ecx, esi; int
0x1800189b6  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800189bb  mov     ecx, eax; dwErrCode
0x1800189bd  call    cs:__imp_SetLastError
0x1800189c3  mov     r8d, 198Dh
0x1800189c9  jmp     loc_180018AAB
0x1800189ce  mov     rcx, [rbx+8]; sesid
0x1800189d2  mov     r14d, edi
0x1800189d5  call    cs:__imp_JetBeginTransaction
0x1800189db  mov     ecx, eax; int
0x1800189dd  mov     esi, eax
0x1800189df  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800189e4  test    eax, eax
0x1800189e6  jz      short loc_180018A02
0x1800189e8  mov     ecx, esi; int
0x1800189ea  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800189ef  mov     ecx, eax; dwErrCode
0x1800189f1  call    cs:__imp_SetLastError
0x1800189f7  mov     r8d, 1998h
0x1800189fd  jmp     loc_180018AAB
0x180018a02  mov     edx, [rsp+68h+pdbid]; unsigned int
0x180018a06  mov     rcx, rbx; struct _JET_DB_STRUCT *
0x180018a09  call    ?_CatDBCreateDBTables@@YAHPEAU_JET_DB_STRUCT@@K@Z; _CatDBCreateDBTables(_JET_DB_STRUCT *,ulong)
0x180018a0e  test    eax, eax
0x180018a10  jnz     short loc_180018A31
0x180018a12  xor     r9d, r9d; unsigned int
0x180018a15  mov     [rsp+68h+grbit], ebp; int
0x180018a19  mov     r8d, 199Eh; unsigned int
0x180018a1f  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180018a24  call    cs:__imp_GetLastError
0x180018a2a  mov     esi, eax
0x180018a2c  jmp     loc_180018AC3
0x180018a31  mov     rcx, [rbx+8]; sesid
0x180018a35  xor     edx, edx; grbit
0x180018a37  call    cs:__imp_JetCommitTransaction
0x180018a3d  mov     ecx, eax; int
0x180018a3f  mov     esi, eax
0x180018a41  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018a46  test    eax, eax
0x180018a48  jz      short loc_180018A6B
0x180018a4a  mov     ecx, esi; int
0x180018a4c  mov     ebp, edi
0x180018a4e  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018a53  mov     ecx, eax; dwErrCode
0x180018a55  call    cs:__imp_SetLastError
0x180018a5b  mov     r8d, 19AAh
0x180018a61  mov     [rsp+68h+grbit], 0
0x180018a69  jmp     short loc_180018AAF
0x180018a6b  xor     edx, edx; int
0x180018a6d  mov     rcx, rbx; struct _JET_DB_STRUCT *
0x180018a70  call    ?_CatDBCloseDBTables@@YAXPEAU_JET_DB_STRUCT@@H@Z; _CatDBCloseDBTables(_JET_DB_STRUCT *,int)
0x180018a75  mov     edx, [rsp+68h+pdbid]; dbid
0x180018a79  xor     r8d, r8d; grbit
0x180018a7c  mov     rcx, [rbx+8]; sesid
0x180018a80  call    cs:__imp_JetCloseDatabase
0x180018a86  mov     ecx, eax; int
0x180018a88  mov     esi, eax
0x180018a8a  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018a8f  test    eax, eax
0x180018a91  jz      short loc_180018B07
0x180018a93  mov     ecx, esi; int
0x180018a95  xor     r14d, r14d
0x180018a98  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018a9d  mov     ecx, eax; dwErrCode
0x180018a9f  call    cs:__imp_SetLastError
0x180018aa5  mov     r8d, 19BAh; unsigned int
0x180018aab  mov     [rsp+68h+grbit], ebp; int
0x180018aaf  xor     r9d, r9d; unsigned int
0x180018ab2  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180018ab7  call    cs:__imp_GetLastError
0x180018abd  mov     esi, eax
0x180018abf  test    ebp, ebp
0x180018ac1  jz      short loc_180018AD9
0x180018ac3  mov     rcx, [rbx+8]; sesid
0x180018ac7  xor     edx, edx; grbit
0x180018ac9  call    cs:__imp_JetRollback
0x180018acf  mov     edx, edi; int
0x180018ad1  mov     rcx, rbx; struct _JET_DB_STRUCT *
0x180018ad4  call    ?_CatDBCloseDBTables@@YAXPEAU_JET_DB_STRUCT@@H@Z; _CatDBCloseDBTables(_JET_DB_STRUCT *,int)
0x180018ad9  test    r14d, r14d
0x180018adc  jz      short loc_180018AEF
0x180018ade  mov     edx, [rsp+68h+pdbid]; dbid
0x180018ae2  xor     r8d, r8d; grbit
0x180018ae5  mov     rcx, [rbx+8]; sesid
0x180018ae9  call    cs:__imp_JetCloseDatabase
0x180018aef  test    r15d, r15d
0x180018af2  jz      short loc_180018AFD
0x180018af4  mov     rcx, r12; lpFileName
0x180018af7  call    cs:__imp_DeleteFileW
0x180018afd  mov     ecx, esi; dwErrCode
0x180018aff  call    cs:__imp_SetLastError
0x180018b05  xor     edi, edi
0x180018b07  mov     eax, edi
0x180018b09  mov     rcx, [rsp+68h+var_30]
0x180018b0e  xor     rcx, rsp; StackCookie
0x180018b11  call    __security_check_cookie
0x180018b16  lea     r11, [rsp+68h+var_28]
0x180018b1b  mov     rbx, [r11+40h]
0x180018b1f  mov     rbp, [r11+48h]
0x180018b23  mov     rsp, r11
0x180018b26  pop     r15
0x180018b28  pop     r14
0x180018b2a  pop     r12
0x180018b2c  pop     rdi
0x180018b2d  pop     rsi
0x180018b2e  retn
```
