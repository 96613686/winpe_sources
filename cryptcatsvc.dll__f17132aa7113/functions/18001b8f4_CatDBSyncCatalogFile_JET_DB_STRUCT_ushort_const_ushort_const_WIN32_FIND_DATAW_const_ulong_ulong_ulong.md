# _CatDBSyncCatalogFile(_JET_DB_STRUCT *,ushort const *,ushort const *,_WIN32_FIND_DATAW const *,ulong *,ulong *,ulong *)

- ea: `0x18001b8f4`
- end: `0x18001c034`
- name: `?_CatDBSyncCatalogFile@@YAHPEAU_JET_DB_STRUCT@@PEBG1PEBU_WIN32_FIND_DATAW@@PEAK33@Z`
- size: `1856`
- prototype: `__int64 __usercall@<rax>(struct _JET_DB_STRUCT *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const struct _WIN32_FIND_DATAW *@<r9>, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001c03c`

## callees

- `0x1800015b0`
- `0x1800038f0`
- `0x180003d48`
- `0x180004094`
- `0x180008b8c`
- `0x180009084`
- `0x18000938c`
- `0x180009440`
- `0x18000a57c`
- `0x18000a59c`
- `0x18000a710`
- `0x18000aa00`
- `0x18000acbc`
- `0x18000be40`
- `0x18000c7e8`
- `0x1800181f4`
- `0x18001825c`
- `0x18001aeb0`
- `0x18001b4dc`
- `0x18001b8f4`
- `0x18001f748`
- `0x18001f81c`
- `0x1800215c8`

## import_xrefs

- `CRYPT32!CertCreateContext` at `0x18001be34`
- `CRYPT32!CertCreateContext` at `0x18001be34`
- `CRYPT32!CryptHashCertificate2` at `0x18001bb6b`
- `CRYPT32!CryptHashCertificate2` at `0x18001bb6b`
- `CRYPT32!CertFreeCTLContext` at `0x18001be6b`
- `CRYPT32!CertFreeCTLContext` at `0x18001be6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b9bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ba9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bcbe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bd14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bd49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bd81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bdfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001be7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bec6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bef8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bf85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c00c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b9bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ba9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bcbe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bd14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bd49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bd81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bdfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001be7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bec6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bef8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bf85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c00c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001ba2d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001ba3f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001ba2d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001ba3f`
- `ESENT!JetBeginTransaction` at `0x18001b99b`
- `ESENT!JetBeginTransaction` at `0x18001bd61`
- `ESENT!JetBeginTransaction` at `0x18001bde1`
- `ESENT!JetBeginTransaction` at `0x18001b99b`
- `ESENT!JetBeginTransaction` at `0x18001bd61`
- `ESENT!JetBeginTransaction` at `0x18001bde1`
- `ESENT!JetRollback` at `0x18001beaa`
- `ESENT!JetRollback` at `0x18001bfbe`
- `ESENT!JetRollback` at `0x18001beaa`
- `ESENT!JetRollback` at `0x18001bfbe`
- `ESENT!JetDelete` at `0x18001bcf6`
- `ESENT!JetDelete` at `0x18001bcf6`
- `ESENT!JetCommitTransaction` at `0x18001bd2b`
- `ESENT!JetCommitTransaction` at `0x18001bed7`
- `ESENT!JetCommitTransaction` at `0x18001bf69`
- `ESENT!JetCommitTransaction` at `0x18001bd2b`
- `ESENT!JetCommitTransaction` at `0x18001bed7`
- `ESENT!JetCommitTransaction` at `0x18001bf69`

## string_xrefs

- `0x18001bbb8`: `SyncDB:: Failed to open `
- `0x18001bc98`: `SyncDB:: Catalog modified (%u) and being removed: %s`
- `0x18001bc10`: `SyncDB:: ChangedFileAttributesForCatalog: %s CreationTime: %I64u/%I64u LastWriteTime: %I64u/%I64u Size: %u/%u`

## pseudocode

```c
__int64 __fastcall _CatDBSyncCatalogFile(
        struct _JET_DB_STRUCT *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        const struct _WIN32_FIND_DATAW *a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned int *a7)
{
  WCHAR *cFileName; // r15
  wchar_t *v8; // r12
  int v11; // r13d
  JET_ERR v13; // r14d
  int v14; // ebx
  DWORD v15; // eax
  unsigned int v16; // edx
  unsigned __int16 *v17; // rcx
  int v18; // r14d
  int v19; // r15d
  unsigned int v20; // edx
  unsigned __int16 *v21; // rcx
  int v22; // eax
  DWORD v23; // eax
  unsigned int v24; // edx
  unsigned __int16 *v25; // rcx
  unsigned __int16 *v26; // rax
  unsigned int v27; // edx
  unsigned __int16 *v28; // rcx
  unsigned int v29; // r8d
  unsigned int v30; // esi
  DWORD Error; // r15d
  unsigned int v32; // edx
  unsigned __int16 *v33; // rcx
  unsigned int v34; // edx
  unsigned __int16 *v35; // rcx
  unsigned int v36; // r13d
  unsigned int *v37; // rax
  JET_ERR v38; // r14d
  DWORD v39; // eax
  JET_ERR v40; // r14d
  DWORD v41; // eax
  JET_ERR v42; // r13d
  DWORD v43; // eax
  unsigned int v44; // edx
  unsigned __int16 *v45; // rcx
  JET_ERR v46; // esi
  DWORD v47; // eax
  const struct _CTL_CONTEXT *Context; // rax
  unsigned int v49; // edx
  unsigned __int16 *v50; // rcx
  const CTL_CONTEXT *v51; // r14
  int v52; // esi
  unsigned int v53; // edx
  unsigned __int16 *v54; // rcx
  JET_SESID v55; // rcx
  JET_ERR v56; // esi
  DWORD v57; // eax
  JET_ERR v58; // esi
  DWORD v59; // eax
  int v60; // eax
  unsigned __int16 *v61; // rdx
  int v62; // eax
  JET_ERR v63; // esi
  DWORD v64; // eax
  DWORD v65; // ebx
  int pbComputedHash; // [rsp+28h] [rbp-D8h]
  int v68; // [rsp+50h] [rbp-B0h]
  unsigned int v69; // [rsp+54h] [rbp-ACh]
  DWORD cbEncoded; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwErrCode; // [rsp+5Ch] [rbp-A4h]
  BYTE *pbEncoded; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v73; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v74; // [rsp+70h] [rbp-90h]
  int v75[2]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v76[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v77; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v78; // [rsp+98h] [rbp-68h]
  unsigned int *v79; // [rsp+A0h] [rbp-60h]
  DWORD pcbComputedHash[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v81; // [rsp+B0h] [rbp-50h] BYREF
  FILETIME ftCreationTime; // [rsp+B8h] [rbp-48h] BYREF
  FILETIME FileTime2; // [rsp+C0h] [rbp-40h] BYREF
  DWORD nFileSizeHigh; // [rsp+C8h] [rbp-38h]
  DWORD nFileSizeLow; // [rsp+CCh] [rbp-34h]
  _OWORD Buf2[2]; // [rsp+D0h] [rbp-30h] BYREF
  BYTE Buf1[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v88; // [rsp+100h] [rbp+0h]

  cFileName = a4->cFileName;
  v77 = a5;
  v8 = 0;
  v79 = a6;
  v73 = a7;
  v11 = 0;
  v74 = a3;
  *(_QWORD *)v75 = -1;
  v76[0] = -1;
  v78 = a4->cFileName;
  v69 = 0;
  pbEncoded = 0;
  cbEncoded = 0;
  memset_0(&v81, 0, 0x40u);
  I_CatDBEventSubsystemAndCatalogTemplate(a2, cFileName, CAPI2_CATDB_SYNC_CATALOG_START_EVENT);
  v13 = JetBeginTransaction(*((_QWORD *)a1 + 1));
  if ( (unsigned int)_CatDBJET_errFailure(v13) )
  {
    v14 = 0;
    v15 = _CatDBMapJetError(v13);
    SetLastError(v15);
    ErrLog_LogError(v17, v16, 0x69Du, 0, 0, pbComputedHash);
    goto LABEL_72;
  }
  v68 = 0;
  v18 = 0;
  v14 = 1;
  v19 = _CatDBSeekInCatNameAttrTable(a1, cFileName);
  if ( (unsigned int)_CatDBJET_errFailure(v19) )
    goto LABEL_15;
  if ( !_CatDBRetrieveCatNameAttrTableAttrColumn(a1, (struct _CATALOG_ATTR_STRUCT *)&v81) )
  {
    ErrLog_LogError(v21, v20, 0x6ABu, 0, 0, pbComputedHash);
    goto LABEL_72;
  }
  if ( a4->nFileSizeLow != nFileSizeLow || a4->nFileSizeHigh != nFileSizeHigh )
    goto LABEL_14;
  if ( CompareFileTime(&a4->ftLastWriteTime, &FileTime2) || CompareFileTime(&a4->ftCreationTime, &ftCreationTime) )
  {
    v11 = dword_180032718;
LABEL_14:
    v18 = 1;
LABEL_15:
    v22 = 0;
    goto LABEL_16;
  }
  if ( !(_DWORD)v81 || HIDWORD(v81) >= 3 )
    goto LABEL_15;
  v22 = HIDWORD(v81) + 1;
  v68 = HIDWORD(v81) + 1;
LABEL_16:
  dwErrCode = 0;
  if ( v19 != -1601 && !v18 && !v22 )
  {
    if ( (unsigned int)_CatDBJET_errFailure(v19) )
    {
      v23 = _CatDBMapJetError(v19);
      SetLastError(v23);
      ErrLog_LogError(v25, v24, 0x7D5u, 0, 0, pbComputedHash);
      goto LABEL_72;
    }
    goto LABEL_69;
  }
  if ( v11 )
  {
    ftCreationTime = a4->ftCreationTime;
    FileTime2 = a4->ftLastWriteTime;
    if ( !v18 )
      goto LABEL_63;
    goto LABEL_65;
  }
  v26 = _CATDBConstructWSTRPath(v74, a4->cFileName);
  v8 = v26;
  if ( !v26 )
  {
    v29 = 1743;
    goto LABEL_71;
  }
  v69 = CatUtil_Open(v28, v26, v76, &pbEncoded, &cbEncoded);
  if ( v69 )
  {
    pcbComputedHash[0] = 32;
    if ( CryptHashCertificate2(L"SHA256", 0, 0, pbEncoded, cbEncoded, Buf1, pcbComputedHash) )
    {
      Error = 0;
      if ( pcbComputedHash[0] == 32 )
      {
LABEL_32:
        v36 = v69;
        if ( v18 )
        {
          if ( v69 && !memcmp_0(Buf1, Buf2, 0x20u) )
          {
            *(FILETIME *)pcbComputedHash = a4->ftLastWriteTime;
            v76[1] = FileTime2;
            v73 = (unsigned int *)a4->ftCreationTime;
            v74 = (unsigned __int16 *)ftCreationTime;
            pbComputedHash = (int)v73;
            ErrLog_LogPrintfW(
              0,
              1,
              L"SyncDB:: ChangedFileAttributesForCatalog: %s CreationTime: %I64u/%I64u LastWriteTime: %I64u/%I64u Size: %u/%u",
              a4->cFileName,
              ftCreationTime);
          }
          else
          {
            ErrLog_LogPrintfW(0, 1, L"SyncDB:: Catalog modified (%u) and being removed: %s", v69, a4->cFileName);
            v37 = v73;
            ++*v73;
            if ( *v37 > 3 )
            {
              SetLastError(0x12Fu);
              v29 = 1812;
              goto LABEL_71;
            }
            CatDBSetWriteJetDatabaseParams();
            if ( !(unsigned int)_CatDBRemoveCatNameFromCatNameTable(a1, a4->cFileName) )
            {
              v29 = 1821;
              goto LABEL_71;
            }
            v38 = JetDelete(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 8));
            if ( (unsigned int)_CatDBJET_errFailure(v38) )
            {
              v39 = _CatDBMapJetError(v38);
              SetLastError(v39);
              v29 = 1831;
              goto LABEL_71;
            }
            v40 = JetCommitTransaction(*((_QWORD *)a1 + 1), 0);
            if ( (unsigned int)_CatDBJET_errFailure(v40) )
            {
              v41 = _CatDBMapJetError(v40);
              SetLastError(v41);
              v29 = 1843;
              goto LABEL_71;
            }
            v18 = 0;
            v42 = JetBeginTransaction(*((_QWORD *)a1 + 1));
            if ( (unsigned int)_CatDBJET_errFailure(v42) )
            {
              v14 = 0;
              v43 = _CatDBMapJetError(v42);
              SetLastError(v43);
              ErrLog_LogError(v45, v44, 0x73Fu, 0, 0, pbComputedHash);
              goto LABEL_72;
            }
            v36 = v69;
          }
        }
        ftCreationTime = a4->ftCreationTime;
        FileTime2 = a4->ftLastWriteTime;
        nFileSizeHigh = a4->nFileSizeHigh;
        nFileSizeLow = a4->nFileSizeLow;
        v81 = 0;
        Buf2[0] = *(_OWORD *)Buf1;
        Buf2[1] = v88;
        if ( !v18 )
        {
          CatDBSetWriteJetDatabaseParams();
          v46 = JetBeginTransaction(*((_QWORD *)a1 + 1));
          if ( (unsigned int)_CatDBJET_errFailure(v46) )
          {
            v47 = _CatDBMapJetError(v46);
            SetLastError(v47);
            v29 = 1905;
            goto LABEL_71;
          }
          if ( v36 )
          {
            Context = (const struct _CTL_CONTEXT *)CertCreateContext(3u, 0x10001u, pbEncoded, cbEncoded, 1u, 0);
            v51 = Context;
            if ( Context )
            {
              v52 = _CatDBAddCatalogEntriesToDatabase(a1, Context, v8);
              CertFreeCTLContext(v51);
              if ( v52 )
                goto LABEL_57;
            }
            else
            {
              ErrLog_LogError(v50, v49, 0x784u, 0, 0, pbComputedHash);
              v52 = 0;
            }
          }
          else
          {
            v52 = 0;
            SetLastError(Error);
          }
          LODWORD(v81) = _CatDBGetNonzeroLastError();
          ErrLog_LogError(v54, v53, 0x79Bu, v81, 0, pbComputedHash);
LABEL_57:
          v55 = *((_QWORD *)a1 + 1);
          if ( v52 )
          {
            v58 = JetCommitTransaction(v55, 0);
            if ( (unsigned int)_CatDBJET_errFailure(v58) )
            {
              v14 = 2;
              v59 = _CatDBMapJetError(v58);
              SetLastError(v59);
              v29 = 1966;
              goto LABEL_71;
            }
          }
          else
          {
            v56 = JetRollback(v55, 0);
            if ( (unsigned int)_CatDBJET_errFailure(v56) )
            {
              v57 = _CatDBMapJetError(v56);
              SetLastError(v57);
              v29 = 1957;
              goto LABEL_71;
            }
          }
LABEL_63:
          v60 = v68;
          if ( !v68 )
          {
            v61 = v78;
            ++*v77;
            v62 = _CatDBAddNewRowToCatNameAttrTable(a1, v61, (struct _CATALOG_ATTR_STRUCT *)&v81);
LABEL_67:
            if ( v62 )
            {
LABEL_69:
              v63 = JetCommitTransaction(*((_QWORD *)a1 + 1), 0);
              if ( !(unsigned int)_CatDBJET_errFailure(v63) )
              {
                v30 = 1;
                goto LABEL_76;
              }
              v64 = _CatDBMapJetError(v63);
              SetLastError(v64);
              v29 = 2018;
              goto LABEL_71;
            }
            v29 = 1996;
LABEL_71:
            ErrLog_LogError(v28, v27, v29, 0, 0, pbComputedHash);
LABEL_72:
            dwErrCode = _CatDBGetNonzeroLastError();
            v30 = 0;
            if ( !v14 )
              goto LABEL_76;
            goto LABEL_73;
          }
LABEL_66:
          HIDWORD(v81) = v60;
          ++*v79;
          v62 = _CatDBUpdateCatNameAttrTableAttrColumn(a1, (struct _CATALOG_ATTR_STRUCT *)&v81);
          goto LABEL_67;
        }
LABEL_65:
        v60 = v68;
        goto LABEL_66;
      }
    }
    Error = _CatDBGetNonzeroLastError();
    ErrLog_LogError(v35, v34, 0x6F5u, Error, 0, pbComputedHash);
    CatUtil_Close(v76, &pbEncoded, v75);
    v69 = 0;
LABEL_31:
    ErrLog_LogString(0, L"SyncDB:: Failed to open ", v8, 1);
    *(_OWORD *)Buf1 = 0;
    v88 = 0;
    goto LABEL_32;
  }
  if ( !g_fFilterNonePresentCatalogs )
  {
    Error = _CatDBGetNonzeroLastError();
    ErrLog_LogError(v33, v32, 0x6E4u, Error, 0, (int)v75);
    goto LABEL_31;
  }
  v30 = 1;
  do
  {
LABEL_73:
    JetRollback(*((_QWORD *)a1 + 1), 0);
    --v14;
  }
  while ( v14 );
LABEL_76:
  if ( v69 )
    CatUtil_Close(v76, &pbEncoded, v75);
  if ( v8 )
    _CatDBFree(v8);
  v65 = dwErrCode;
  I_CatDBEventStatusTemplate(dwErrCode, CAPI2_CATDB_SYNC_CATALOG_STOP_EVENT);
  if ( !v30 )
    SetLastError(v65);
  return v30;
}

```

## disassembly

```asm
0x18001b8f4  push    rbp
0x18001b8f6  push    rbx
0x18001b8f7  push    rsi
0x18001b8f8  push    rdi
0x18001b8f9  push    r12
0x18001b8fb  push    r13
0x18001b8fd  push    r14
0x18001b8ff  push    r15
0x18001b901  lea     rbp, [rsp-28h]
0x18001b906  sub     rsp, 128h
0x18001b90d  mov     rax, cs:__security_cookie
0x18001b914  xor     rax, rsp
0x18001b917  mov     [rbp+60h+var_50], rax
0x18001b91b  mov     rax, [rbp+60h+arg_20]
0x18001b922  lea     r15, [r9+2Ch]
0x18001b926  mov     [rbp+60h+var_D0], rax
0x18001b92a  xor     r12d, r12d
0x18001b92d  mov     rax, [rbp+60h+arg_28]
0x18001b934  mov     rbx, rdx
0x18001b937  mov     [rbp+60h+var_C0], rax
0x18001b93b  mov     rdi, rcx
0x18001b93e  mov     rax, [rbp+60h+arg_30]
0x18001b945  lea     rcx, [rbp+60h+var_B0]; void *
0x18001b949  mov     [rsp+160h+var_F8], rax
0x18001b94e  xor     r13d, r13d
0x18001b951  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b955  mov     [rsp+160h+var_F0], r8
0x18001b95a  xor     edx, edx; Val
0x18001b95c  mov     qword ptr [rsp+160h+var_E8], rax
0x18001b961  lea     r8d, [r12+40h]; Size
0x18001b966  mov     [rbp+60h+var_E0], rax
0x18001b96a  mov     rsi, r9
0x18001b96d  mov     [rbp+60h+var_C8], r15
0x18001b971  mov     [rsp+160h+var_10C], r13d
0x18001b976  mov     [rsp+160h+pbEncoded], r12
0x18001b97b  mov     [rsp+160h+var_108], r12d
0x18001b980  call    memset_0
0x18001b985  lea     r8, CAPI2_CATDB_SYNC_CATALOG_START_EVENT
0x18001b98c  mov     rdx, r15
0x18001b98f  mov     rcx, rbx
0x18001b992  call    I_CatDBEventSubsystemAndCatalogTemplate
0x18001b997  mov     rcx, [rdi+8]; sesid
0x18001b99b  call    cs:__imp_JetBeginTransaction
0x18001b9a1  mov     ecx, eax; int
0x18001b9a3  mov     r14d, eax
0x18001b9a6  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001b9ab  test    eax, eax
0x18001b9ad  jz      short loc_18001B9D0
0x18001b9af  mov     ecx, r14d; int
0x18001b9b2  xor     ebx, ebx
0x18001b9b4  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001b9b9  mov     ecx, eax; dwErrCode
0x18001b9bb  call    cs:__imp_SetLastError
0x18001b9c1  mov     r8d, 69Dh
0x18001b9c7  mov     [rsp+160h+cbEncoded], ebx
0x18001b9cb  jmp     loc_18001BF99
0x18001b9d0  xor     eax, eax
0x18001b9d2  mov     rdx, r15; unsigned __int16 *
0x18001b9d5  mov     rcx, rdi; struct _JET_DB_STRUCT *
0x18001b9d8  mov     [rsp+160h+var_110], eax
0x18001b9dc  xor     r14d, r14d
0x18001b9df  lea     ebx, [rax+1]
0x18001b9e2  call    ?_CatDBSeekInCatNameAttrTable@@YAJPEAU_JET_DB_STRUCT@@PEBG@Z; _CatDBSeekInCatNameAttrTable(_JET_DB_STRUCT *,ushort const *)
0x18001b9e7  mov     ecx, eax; int
0x18001b9e9  mov     r15d, eax
0x18001b9ec  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001b9f1  test    eax, eax
0x18001b9f3  jnz     short loc_18001BA69
0x18001b9f5  lea     rdx, [rbp+60h+var_B0]; struct _CATALOG_ATTR_STRUCT *
0x18001b9f9  mov     rcx, rdi; struct _JET_DB_STRUCT *
0x18001b9fc  call    ?_CatDBRetrieveCatNameAttrTableAttrColumn@@YAHPEAU_JET_DB_STRUCT@@PEAU_CATALOG_ATTR_STRUCT@@@Z; _CatDBRetrieveCatNameAttrTableAttrColumn(_JET_DB_STRUCT *,_CATALOG_ATTR_STRUCT *)
0x18001ba01  test    eax, eax
0x18001ba03  jnz     short loc_18001BA15
0x18001ba05  mov     [rsp+160h+cbEncoded], r12d
0x18001ba0a  mov     r8d, 6ABh
0x18001ba10  jmp     loc_18001BF99
0x18001ba15  mov     eax, [rbp+60h+var_94]
0x18001ba18  cmp     [rsi+20h], eax
0x18001ba1b  jnz     short loc_18001BA66
0x18001ba1d  mov     eax, [rbp+60h+var_98]
0x18001ba20  cmp     [rsi+1Ch], eax
0x18001ba23  jnz     short loc_18001BA66
0x18001ba25  lea     rcx, [rsi+14h]; lpFileTime1
0x18001ba29  lea     rdx, [rbp+60h+FileTime2]; lpFileTime2
0x18001ba2d  call    cs:__imp_CompareFileTime
0x18001ba33  test    eax, eax
0x18001ba35  jnz     short loc_18001BA5F
0x18001ba37  lea     rcx, [rsi+4]; lpFileTime1
0x18001ba3b  lea     rdx, [rbp+60h+var_A8]; lpFileTime2
0x18001ba3f  call    cs:__imp_CompareFileTime
0x18001ba45  test    eax, eax
0x18001ba47  jnz     short loc_18001BA5F
0x18001ba49  cmp     dword ptr [rbp+60h+var_B0], r12d
0x18001ba4d  jz      short loc_18001BA69
0x18001ba4f  mov     eax, dword ptr [rbp+60h+var_B0+4]
0x18001ba52  cmp     eax, 3
0x18001ba55  jnb     short loc_18001BA69
0x18001ba57  inc     eax
0x18001ba59  mov     [rsp+160h+var_110], eax
0x18001ba5d  jmp     short loc_18001BA6C
0x18001ba5f  mov     r13d, cs:dword_180032718
0x18001ba66  mov     r14d, ebx
0x18001ba69  mov     eax, r12d
0x18001ba6c  mov     [rsp+160h+dwErrCode], r12d
0x18001ba71  cmp     r15d, 0FFFFF9BFh
0x18001ba78  jz      short loc_18001BAB3
0x18001ba7a  test    r14d, r14d
0x18001ba7d  jnz     short loc_18001BAB3
0x18001ba7f  test    eax, eax
0x18001ba81  jnz     short loc_18001BAB3
0x18001ba83  mov     ecx, r15d; int
0x18001ba86  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001ba8b  test    eax, eax
0x18001ba8d  jz      loc_18001BF63
0x18001ba93  mov     ecx, r15d; int
0x18001ba96  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001ba9b  mov     ecx, eax; dwErrCode
0x18001ba9d  call    cs:__imp_SetLastError
0x18001baa3  mov     r8d, 7D5h
0x18001baa9  mov     [rsp+160h+cbEncoded], r12d
0x18001baae  jmp     loc_18001BF99
0x18001bab3  test    r13d, r13d
0x18001bab6  jnz     loc_18001BF09
0x18001babc  mov     rcx, [rsp+160h+var_F0]; unsigned __int16 *
0x18001bac1  lea     rdx, [rsi+2Ch]; unsigned __int16 *
0x18001bac5  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001baca  mov     r12, rax
0x18001bacd  test    rax, rax
0x18001bad0  jnz     short loc_18001BADD
0x18001bad2  mov     r8d, 6CFh
0x18001bad8  jmp     loc_18001BF91
0x18001badd  lea     rax, [rsp+160h+var_E8]
0x18001bae2  mov     rdx, r12
0x18001bae5  mov     [rsp+160h+pbComputedHash], rax; int
0x18001baea  lea     r9, [rsp+160h+pbEncoded]
0x18001baef  lea     rax, [rsp+160h+var_108]
0x18001baf4  lea     r8, [rbp+60h+var_E0]
0x18001baf8  mov     qword ptr [rsp+160h+cbEncoded], rax
0x18001bafd  call    CatUtil_Open
0x18001bb02  mov     [rsp+160h+var_10C], eax
0x18001bb06  test    eax, eax
0x18001bb08  jnz     short loc_18001BB39
0x18001bb0a  cmp     cs:?g_fFilterNonePresentCatalogs@@3HA, eax; int g_fFilterNonePresentCatalogs
0x18001bb10  jz      short loc_18001BB19
0x18001bb12  mov     esi, ebx
0x18001bb14  jmp     loc_18001BFB8
0x18001bb19  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001bb1e  mov     r9d, eax; unsigned int
0x18001bb21  mov     [rsp+160h+cbEncoded], 0; int
0x18001bb29  mov     r8d, 6E4h; unsigned int
0x18001bb2f  mov     r15d, eax
0x18001bb32  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001bb37  jmp     short loc_18001BBB5
0x18001bb39  mov     r9, [rsp+160h+pbEncoded]; pbEncoded
0x18001bb3e  lea     rax, [rbp+60h+var_B8]
0x18001bb42  mov     [rsp+160h+pcbComputedHash], rax; pcbComputedHash
0x18001bb47  lea     rcx, pwszCNGHashAlgid; "SHA256"
0x18001bb4e  lea     rax, [rbp+60h+Buf1]
0x18001bb52  mov     [rbp+60h+var_B8], 20h ; ' '
0x18001bb59  mov     [rsp+160h+pbComputedHash], rax; int
0x18001bb5e  xor     r8d, r8d; pvReserved
0x18001bb61  mov     eax, [rsp+160h+var_108]
0x18001bb65  xor     edx, edx; dwFlags
0x18001bb67  mov     [rsp+160h+cbEncoded], eax; cbEncoded
0x18001bb6b  call    cs:__imp_CryptHashCertificate2
0x18001bb71  test    eax, eax
0x18001bb73  jz      short loc_18001BB7E
0x18001bb75  xor     r15d, r15d
0x18001bb78  cmp     [rbp+60h+var_B8], 20h ; ' '
0x18001bb7c  jz      short loc_18001BBD4
0x18001bb7e  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001bb83  mov     r9d, eax; unsigned int
0x18001bb86  mov     [rsp+160h+cbEncoded], 0; int
0x18001bb8e  mov     r8d, 6F5h; unsigned int
0x18001bb94  mov     r15d, eax
0x18001bb97  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001bb9c  lea     r8, [rsp+160h+var_E8]
0x18001bba1  lea     rdx, [rsp+160h+pbEncoded]
0x18001bba6  lea     rcx, [rbp+60h+var_E0]
0x18001bbaa  call    CatUtil_Close
0x18001bbaf  xor     eax, eax
0x18001bbb1  mov     [rsp+160h+var_10C], eax
0x18001bbb5  mov     r9d, ebx; int
0x18001bbb8  lea     rdx, aSyncdbFailedTo; "SyncDB:: Failed to open "
0x18001bbbf  mov     r8, r12; unsigned __int16 *
0x18001bbc2  xor     ecx, ecx; unsigned __int16 *
0x18001bbc4  call    ?ErrLog_LogString@@YAXPEAG00H@Z; ErrLog_LogString(ushort *,ushort *,ushort *,int)
0x18001bbc9  xorps   xmm0, xmm0
0x18001bbcc  movups  xmmword ptr [rbp+60h+Buf1], xmm0
0x18001bbd0  movups  [rbp+60h+var_60], xmm0
0x18001bbd4  mov     r13d, [rsp+160h+var_10C]
0x18001bbd9  test    r14d, r14d
0x18001bbdc  jz      loc_18001BD9B
0x18001bbe2  test    r13d, r13d
0x18001bbe5  jz      loc_18001BC91
0x18001bbeb  mov     r8d, 20h ; ' '; Size
0x18001bbf1  lea     rdx, [rbp+60h+Buf2]; Buf2
0x18001bbf5  lea     rcx, [rbp+60h+Buf1]; Buf1
0x18001bbf9  call    memcmp_0
0x18001bbfe  test    eax, eax
0x18001bc00  jnz     loc_18001BC91
0x18001bc06  mov     eax, [rsi+14h]
0x18001bc09  lea     r9, [rsi+2Ch]
0x18001bc0d  mov     [rbp+60h+var_B8], eax
0x18001bc10  lea     r8, aSyncdbChangedf; "SyncDB:: ChangedFileAttributesForCatalo"...
0x18001bc17  mov     eax, [rsi+18h]
0x18001bc1a  mov     edx, ebx; int
0x18001bc1c  mov     [rbp+60h+var_B8+4], eax
0x18001bc1f  xor     ecx, ecx; unsigned __int16 *
0x18001bc21  mov     eax, [rbp+60h+FileTime2.dwLowDateTime]
0x18001bc24  mov     dword ptr [rbp+60h+var_D8], eax
0x18001bc27  mov     rax, qword ptr [rbp+60h+FileTime2.dwLowDateTime]
0x18001bc2b  shr     rax, 20h
0x18001bc2f  mov     dword ptr [rbp+60h+var_D8+4], eax
0x18001bc32  mov     eax, [rsi+4]
0x18001bc35  mov     dword ptr [rsp+160h+var_F8], eax
0x18001bc39  mov     eax, [rsi+8]
0x18001bc3c  mov     dword ptr [rsp+160h+var_F8+4], eax
0x18001bc40  mov     eax, [rbp+60h+var_A8.dwLowDateTime]
0x18001bc43  mov     dword ptr [rsp+160h+var_F0], eax
0x18001bc47  mov     rax, qword ptr [rbp+60h+var_A8.dwLowDateTime]
0x18001bc4b  shr     rax, 20h
0x18001bc4f  mov     dword ptr [rsp+160h+var_F0+4], eax
0x18001bc53  mov     eax, [rsi+20h]
0x18001bc56  mov     [rsp+160h+var_118], eax
0x18001bc5a  mov     eax, [rbp+60h+var_94]
0x18001bc5d  mov     [rsp+160h+var_120], eax
0x18001bc61  mov     rax, qword ptr [rbp+60h+var_B8]
0x18001bc65  mov     [rsp+160h+var_128], rax
0x18001bc6a  mov     rax, [rbp+60h+var_D8]
0x18001bc6e  mov     [rsp+160h+pcbComputedHash], rax
0x18001bc73  mov     rax, [rsp+160h+var_F8]
0x18001bc78  mov     [rsp+160h+pbComputedHash], rax
0x18001bc7d  mov     rax, [rsp+160h+var_F0]
0x18001bc82  mov     qword ptr [rsp+160h+cbEncoded], rax
0x18001bc87  call    ?ErrLog_LogPrintfW@@YAXPEAGHPEBGZZ; ErrLog_LogPrintfW(ushort *,int,ushort const *,...)
0x18001bc8c  jmp     loc_18001BD9B
0x18001bc91  lea     r14, [rsi+2Ch]
0x18001bc95  mov     r9d, r13d
0x18001bc98  lea     r8, aSyncdbCatalogM; "SyncDB:: Catalog modified (%u) and bein"...
0x18001bc9f  mov     qword ptr [rsp+160h+cbEncoded], r14
0x18001bca4  mov     edx, ebx; int
0x18001bca6  xor     ecx, ecx; unsigned __int16 *
0x18001bca8  call    ?ErrLog_LogPrintfW@@YAXPEAGHPEBGZZ; ErrLog_LogPrintfW(ushort *,int,ushort const *,...)
0x18001bcad  mov     rax, [rsp+160h+var_F8]
0x18001bcb2  add     [rax], ebx
0x18001bcb4  cmp     dword ptr [rax], 3
0x18001bcb7  jbe     short loc_18001BCCF
0x18001bcb9  mov     ecx, 12Fh; dwErrCode
0x18001bcbe  call    cs:__imp_SetLastError
0x18001bcc4  mov     r8d, 714h
0x18001bcca  jmp     loc_18001BF91
0x18001bccf  call    _CatDBSetWriteJetDatabaseParams
0x18001bcd4  mov     rdx, r14; unsigned __int16 *
0x18001bcd7  mov     rcx, rdi; struct _JET_DB_STRUCT *
0x18001bcda  call    ?_CatDBRemoveCatNameFromCatNameTable@@YAHPEAU_JET_DB_STRUCT@@PEBG@Z; _CatDBRemoveCatNameFromCatNameTable(_JET_DB_STRUCT *,ushort const *)
0x18001bcdf  test    eax, eax
0x18001bce1  jnz     short loc_18001BCEE
0x18001bce3  mov     r8d, 71Dh
0x18001bce9  jmp     loc_18001BF91
0x18001bcee  mov     rdx, [rdi+40h]; tableid
0x18001bcf2  mov     rcx, [rdi+8]; sesid
0x18001bcf6  call    cs:__imp_JetDelete
0x18001bcfc  mov     ecx, eax; int
0x18001bcfe  mov     r14d, eax
0x18001bd01  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001bd06  test    eax, eax
0x18001bd08  jz      short loc_18001BD25
0x18001bd0a  mov     ecx, r14d; int
0x18001bd0d  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001bd12  mov     ecx, eax; dwErrCode
0x18001bd14  call    cs:__imp_SetLastError
0x18001bd1a  mov     r8d, 727h
0x18001bd20  jmp     loc_18001BF91
0x18001bd25  mov     rcx, [rdi+8]; sesid
0x18001bd29  xor     edx, edx; grbit
0x18001bd2b  call    cs:__imp_JetCommitTransaction
0x18001bd31  mov     ecx, eax; int
0x18001bd33  mov     r14d, eax
0x18001bd36  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001bd3b  test    eax, eax
0x18001bd3d  jz      short loc_18001BD5A
0x18001bd3f  mov     ecx, r14d; int
0x18001bd42  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001bd47  mov     ecx, eax; dwErrCode
0x18001bd49  call    cs:__imp_SetLastError
0x18001bd4f  mov     r8d, 733h
0x18001bd55  jmp     loc_18001BF91
0x18001bd5a  mov     rcx, [rdi+8]; sesid
0x18001bd5e  xor     r14d, r14d
0x18001bd61  call    cs:__imp_JetBeginTransaction
0x18001bd67  mov     ecx, eax; int
0x18001bd69  mov     r13d, eax
0x18001bd6c  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001bd71  test    eax, eax
0x18001bd73  jz      short loc_18001BD96
0x18001bd75  mov     ecx, r13d; int
0x18001bd78  xor     ebx, ebx
0x18001bd7a  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001bd7f  mov     ecx, eax; dwErrCode
  ... truncated ...
```
