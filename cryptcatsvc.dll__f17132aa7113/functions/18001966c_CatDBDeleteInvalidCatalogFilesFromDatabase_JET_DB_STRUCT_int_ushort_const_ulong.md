# _CatDBDeleteInvalidCatalogFilesFromDatabase(_JET_DB_STRUCT *,int,ushort const *,ulong *)

- ea: `0x18001966c`
- end: `0x180019984`
- name: `?_CatDBDeleteInvalidCatalogFilesFromDatabase@@YAHPEAU_JET_DB_STRUCT@@HPEBGPEAK@Z`
- size: `792`
- prototype: `__int64 __fastcall(struct _JET_DB_STRUCT *, int, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001c03c`

## callees

- `0x1800015b0`
- `0x1800038f0`
- `0x180003d48`
- `0x180004094`
- `0x18000a57c`
- `0x18000a59c`
- `0x18000acbc`
- `0x18000be40`
- `0x18000c7e8`
- `0x18001966c`
- `0x18001aeb0`
- `0x18001b030`
- `0x18001b4dc`
- `0x18001f81c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800196c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019848`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019862`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001988c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019918`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001994d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800196c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019848`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019862`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001988c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019918`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001994d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180019749`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180019749`
- `ESENT!JetMove` at `0x1800196e6`
- `ESENT!JetMove` at `0x18001982d`
- `ESENT!JetMove` at `0x1800196e6`
- `ESENT!JetMove` at `0x18001982d`
- `ESENT!JetBeginTransaction` at `0x1800196a5`
- `ESENT!JetBeginTransaction` at `0x18001980c`
- `ESENT!JetBeginTransaction` at `0x1800196a5`
- `ESENT!JetBeginTransaction` at `0x18001980c`
- `ESENT!JetRollback` at `0x180019945`
- `ESENT!JetRollback` at `0x180019945`
- `ESENT!JetDelete` at `0x1800197d8`
- `ESENT!JetDelete` at `0x1800197d8`
- `ESENT!JetCommitTransaction` at `0x1800197f5`
- `ESENT!JetCommitTransaction` at `0x1800198fc`
- `ESENT!JetCommitTransaction` at `0x1800197f5`
- `ESENT!JetCommitTransaction` at `0x1800198fc`

## string_xrefs

- `0x18001977a`: `SyncDB:: DeleteCatalog: `

## pseudocode

```c
__int64 __fastcall _CatDBDeleteInvalidCatalogFilesFromDatabase(
        struct _JET_DB_STRUCT *a1,
        int a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  JET_ERR v8; // ebx
  DWORD v9; // eax
  unsigned int v10; // edx
  unsigned __int16 *v11; // rcx
  unsigned int v12; // r8d
  JET_ERR v13; // eax
  int v14; // edi
  int v15; // ebx
  unsigned int v16; // edx
  unsigned __int16 *v17; // rcx
  int v18; // edx
  const WCHAR *v19; // rax
  WCHAR *v20; // rbp
  DWORD FileAttributesW; // ebx
  JET_ERR v22; // ebx
  JET_ERR v23; // ebx
  JET_ERR v24; // ebx
  unsigned int v25; // r8d
  DWORD v26; // eax
  DWORD v27; // eax
  DWORD v28; // eax
  DWORD v29; // eax
  JET_ERR v30; // ebx
  DWORD v31; // eax
  unsigned int v32; // ebx
  DWORD Error; // ebp
  int v35; // [rsp+28h] [rbp-2A0h]
  _DWORD v36[16]; // [rsp+30h] [rbp-298h] BYREF
  unsigned __int16 v37[264]; // [rsp+70h] [rbp-258h] BYREF

  v8 = JetBeginTransaction(*((_QWORD *)a1 + 1));
  if ( (unsigned int)_CatDBJET_errFailure(v8) )
  {
    v9 = _CatDBMapJetError(v8);
    SetLastError(v9);
    v12 = 1476;
LABEL_23:
    ErrLog_LogError(v11, v10, v12, 0, 0, v35);
    v14 = 0;
LABEL_35:
    v32 = 0;
    Error = _CatDBGetNonzeroLastError();
    if ( v14 )
      JetRollback(*((_QWORD *)a1 + 1), 0);
    SetLastError(Error);
  }
  else
  {
    v13 = JetMove(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 8), 0x80000000, 0);
    v14 = 1;
    while ( 1 )
    {
      v15 = v13;
      if ( v13 )
        break;
      if ( !_CatDBRetrieveCatNameAttrTableCatNameColumn(a1, v37) )
      {
        v25 = 1497;
        goto LABEL_34;
      }
      v18 = v37[0] - 124;
      if ( v37[0] == 124 )
        v18 = v37[1];
      if ( v18 )
      {
        v19 = _CATDBConstructWSTRPath(a3, v37);
        v20 = (WCHAR *)v19;
        if ( !v19 )
        {
          v25 = 1507;
          goto LABEL_34;
        }
        FileAttributesW = GetFileAttributesW(v19);
        _CatDBFree(v20);
        if ( FileAttributesW == -1 )
        {
          memset_0(v36, 0, sizeof(v36));
          ErrLog_LogString(0, L"SyncDB:: DeleteCatalog: ", v37, 1);
          CatDBSetWriteJetDatabaseParams();
          if ( !_CatDBRetrieveCatNameAttrTableAttrColumn(a1, (struct _CATALOG_ATTR_STRUCT *)v36) )
          {
            v25 = 1529;
            goto LABEL_34;
          }
          if ( !v36[0] )
          {
            if ( ++*a4 > 3 || a2 )
            {
              SetLastError(0x12Fu);
              v25 = 1545;
              goto LABEL_34;
            }
            if ( !(unsigned int)_CatDBRemoveCatNameFromCatNameTable(a1, v37) )
            {
              v25 = 1552;
LABEL_34:
              ErrLog_LogError(v17, v16, v25, 0, 0, v35);
              goto LABEL_35;
            }
          }
          v22 = JetDelete(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 8));
          if ( (unsigned int)_CatDBJET_errFailure(v22) )
          {
            v28 = _CatDBMapJetError(v22);
            SetLastError(v28);
            v25 = 1565;
            goto LABEL_34;
          }
          v23 = JetCommitTransaction(*((_QWORD *)a1 + 1), 0);
          if ( (unsigned int)_CatDBJET_errFailure(v23) )
          {
            v27 = _CatDBMapJetError(v23);
            SetLastError(v27);
            v25 = 1577;
            goto LABEL_34;
          }
          v24 = JetBeginTransaction(*((_QWORD *)a1 + 1));
          if ( (unsigned int)_CatDBJET_errFailure(v24) )
          {
            v26 = _CatDBMapJetError(v24);
            SetLastError(v26);
            v12 = 1589;
            goto LABEL_23;
          }
        }
      }
      v13 = JetMove(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 8), 1, 0);
    }
    if ( v13 != -1603 && (unsigned int)_CatDBJET_errFailure(v13) )
    {
      v29 = _CatDBMapJetError(v15);
      SetLastError(v29);
      v25 = 1610;
      goto LABEL_34;
    }
    v30 = JetCommitTransaction(*((_QWORD *)a1 + 1), 0);
    if ( (unsigned int)_CatDBJET_errFailure(v30) )
    {
      v31 = _CatDBMapJetError(v30);
      SetLastError(v31);
      v25 = 1623;
      goto LABEL_34;
    }
    return 1;
  }
  return v32;
}

```

## disassembly

```asm
0x18001966c  mov     [rsp+arg_8], rbx
0x180019671  push    rbp
0x180019672  push    rsi
0x180019673  push    rdi
0x180019674  push    r12
0x180019676  push    r13
0x180019678  push    r14
0x18001967a  push    r15
0x18001967c  sub     rsp, 290h
0x180019683  mov     rax, cs:__security_cookie
0x18001968a  xor     rax, rsp
0x18001968d  mov     [rsp+2C8h+var_48], rax
0x180019695  mov     rsi, rcx
0x180019698  mov     r14, r9
0x18001969b  mov     rcx, [rcx+8]; sesid
0x18001969f  mov     r12, r8
0x1800196a2  mov     r15d, edx
0x1800196a5  call    cs:__imp_JetBeginTransaction
0x1800196ab  mov     ecx, eax; int
0x1800196ad  mov     ebx, eax
0x1800196af  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800196b4  xor     r13d, r13d
0x1800196b7  test    eax, eax
0x1800196b9  jz      short loc_1800196D5
0x1800196bb  mov     ecx, ebx; int
0x1800196bd  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800196c2  mov     ecx, eax; dwErrCode
0x1800196c4  call    cs:__imp_SetLastError
0x1800196ca  mov     r8d, 5C4h
0x1800196d0  jmp     loc_18001986E
0x1800196d5  mov     rdx, [rsi+40h]; tableid
0x1800196d9  xor     r9d, r9d; grbit
0x1800196dc  mov     rcx, [rsi+8]; sesid
0x1800196e0  mov     r8d, 80000000h; cRow
0x1800196e6  call    cs:__imp_JetMove
0x1800196ec  mov     edi, 1
0x1800196f1  mov     ebx, eax
0x1800196f3  test    eax, eax
0x1800196f5  jnz     loc_1800198CC
0x1800196fb  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x180019700  mov     rcx, rsi; struct _JET_DB_STRUCT *
0x180019703  call    ?_CatDBRetrieveCatNameAttrTableCatNameColumn@@YAHPEAU_JET_DB_STRUCT@@PEAG@Z; _CatDBRetrieveCatNameAttrTableCatNameColumn(_JET_DB_STRUCT *,ushort *)
0x180019708  test    eax, eax
0x18001970a  jz      loc_1800198C4
0x180019710  movzx   edx, [rsp+2C8h+var_258]
0x180019715  sub     edx, 7Ch ; '|'
0x180019718  jnz     short loc_180019725
0x18001971a  movzx   edx, [rsp+2C8h+var_256]
0x18001971f  movzx   ecx, r13w
0x180019723  sub     edx, ecx
0x180019725  test    edx, edx
0x180019727  jz      loc_18001981F
0x18001972d  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x180019732  mov     rcx, r12; unsigned __int16 *
0x180019735  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001973a  mov     rbp, rax
0x18001973d  test    rax, rax
0x180019740  jz      loc_1800198BC
0x180019746  mov     rcx, rax; lpFileName
0x180019749  call    cs:__imp_GetFileAttributesW
0x18001974f  mov     rcx, rbp; void *
0x180019752  mov     ebx, eax
0x180019754  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x180019759  cmp     ebx, 0FFFFFFFFh
0x18001975c  jnz     loc_18001981F
0x180019762  xor     edx, edx; Val
0x180019764  lea     rcx, [rsp+2C8h+var_298]; void *
0x180019769  lea     r8d, [rdx+40h]; Size
0x18001976d  call    memset_0
0x180019772  mov     r9d, edi; int
0x180019775  lea     r8, [rsp+2C8h+var_258]; unsigned __int16 *
0x18001977a  lea     rdx, aSyncdbDeleteca; "SyncDB:: DeleteCatalog: "
0x180019781  xor     ecx, ecx; unsigned __int16 *
0x180019783  call    ?ErrLog_LogString@@YAXPEAG00H@Z; ErrLog_LogString(ushort *,ushort *,ushort *,int)
0x180019788  call    _CatDBSetWriteJetDatabaseParams
0x18001978d  lea     rdx, [rsp+2C8h+var_298]; struct _CATALOG_ATTR_STRUCT *
0x180019792  mov     rcx, rsi; struct _JET_DB_STRUCT *
0x180019795  call    ?_CatDBRetrieveCatNameAttrTableAttrColumn@@YAHPEAU_JET_DB_STRUCT@@PEAU_CATALOG_ATTR_STRUCT@@@Z; _CatDBRetrieveCatNameAttrTableAttrColumn(_JET_DB_STRUCT *,_CATALOG_ATTR_STRUCT *)
0x18001979a  test    eax, eax
0x18001979c  jz      loc_1800198B4
0x1800197a2  cmp     [rsp+2C8h+var_298], r13d
0x1800197a7  jnz     short loc_1800197D0
0x1800197a9  add     [r14], edi
0x1800197ac  cmp     dword ptr [r14], 3
0x1800197b0  ja      loc_180019843
0x1800197b6  test    r15d, r15d
0x1800197b9  jnz     loc_180019843
0x1800197bf  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x1800197c4  mov     rcx, rsi; struct _JET_DB_STRUCT *
0x1800197c7  call    ?_CatDBRemoveCatNameFromCatNameTable@@YAHPEAU_JET_DB_STRUCT@@PEBG@Z; _CatDBRemoveCatNameFromCatNameTable(_JET_DB_STRUCT *,ushort const *)
0x1800197cc  test    eax, eax
0x1800197ce  jz      short loc_180019838
0x1800197d0  mov     rdx, [rsi+40h]; tableid
0x1800197d4  mov     rcx, [rsi+8]; sesid
0x1800197d8  call    cs:__imp_JetDelete
0x1800197de  mov     ecx, eax; int
0x1800197e0  mov     ebx, eax
0x1800197e2  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800197e7  test    eax, eax
0x1800197e9  jnz     loc_18001989D
0x1800197ef  mov     rcx, [rsi+8]; sesid
0x1800197f3  xor     edx, edx; grbit
0x1800197f5  call    cs:__imp_JetCommitTransaction
0x1800197fb  mov     ecx, eax; int
0x1800197fd  mov     ebx, eax
0x1800197ff  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180019804  test    eax, eax
0x180019806  jnz     short loc_180019883
0x180019808  mov     rcx, [rsi+8]; sesid
0x18001980c  call    cs:__imp_JetBeginTransaction
0x180019812  mov     ecx, eax; int
0x180019814  mov     ebx, eax
0x180019816  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001981b  test    eax, eax
0x18001981d  jnz     short loc_180019859
0x18001981f  mov     rdx, [rsi+40h]; tableid
0x180019823  xor     r9d, r9d; grbit
0x180019826  mov     rcx, [rsi+8]; sesid
0x18001982a  mov     r8d, edi; cRow
0x18001982d  call    cs:__imp_JetMove
0x180019833  jmp     loc_1800196F1
0x180019838  mov     r8d, 610h
0x18001983e  jmp     loc_180019924
0x180019843  mov     ecx, 12Fh; dwErrCode
0x180019848  call    cs:__imp_SetLastError
0x18001984e  mov     r8d, 609h
0x180019854  jmp     loc_180019924
0x180019859  mov     ecx, ebx; int
0x18001985b  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180019860  mov     ecx, eax; dwErrCode
0x180019862  call    cs:__imp_SetLastError
0x180019868  mov     r8d, 635h; unsigned int
0x18001986e  xor     r9d, r9d; unsigned int
0x180019871  mov     [rsp+2C8h+var_2A8], r13d; int
0x180019876  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001987b  mov     edi, r13d
0x18001987e  jmp     loc_180019931
0x180019883  mov     ecx, ebx; int
0x180019885  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001988a  mov     ecx, eax; dwErrCode
0x18001988c  call    cs:__imp_SetLastError
0x180019892  mov     r8d, 629h
0x180019898  jmp     loc_180019924
0x18001989d  mov     ecx, ebx; int
0x18001989f  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800198a4  mov     ecx, eax; dwErrCode
0x1800198a6  call    cs:__imp_SetLastError
0x1800198ac  mov     r8d, 61Dh
0x1800198b2  jmp     short loc_180019924
0x1800198b4  mov     r8d, 5F9h
0x1800198ba  jmp     short loc_180019924
0x1800198bc  mov     r8d, 5E3h
0x1800198c2  jmp     short loc_180019924
0x1800198c4  mov     r8d, 5D9h
0x1800198ca  jmp     short loc_180019924
0x1800198cc  cmp     ebx, 0FFFFF9BDh
0x1800198d2  jz      short loc_1800198F6
0x1800198d4  mov     ecx, ebx; int
0x1800198d6  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800198db  test    eax, eax
0x1800198dd  jz      short loc_1800198F6
0x1800198df  mov     ecx, ebx; int
0x1800198e1  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800198e6  mov     ecx, eax; dwErrCode
0x1800198e8  call    cs:__imp_SetLastError
0x1800198ee  mov     r8d, 64Ah
0x1800198f4  jmp     short loc_180019924
0x1800198f6  mov     rcx, [rsi+8]; sesid
0x1800198fa  xor     edx, edx; grbit
0x1800198fc  call    cs:__imp_JetCommitTransaction
0x180019902  mov     ecx, eax; int
0x180019904  mov     ebx, eax
0x180019906  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001990b  test    eax, eax
0x18001990d  jz      short loc_180019955
0x18001990f  mov     ecx, ebx; int
0x180019911  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180019916  mov     ecx, eax; dwErrCode
0x180019918  call    cs:__imp_SetLastError
0x18001991e  mov     r8d, 657h; unsigned int
0x180019924  xor     r9d, r9d; unsigned int
0x180019927  mov     [rsp+2C8h+var_2A8], r13d; int
0x18001992c  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180019931  mov     ebx, r13d
0x180019934  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x180019939  mov     ebp, eax
0x18001993b  test    edi, edi
0x18001993d  jz      short loc_18001994B
0x18001993f  mov     rcx, [rsi+8]; sesid
0x180019943  xor     edx, edx; grbit
0x180019945  call    cs:__imp_JetRollback
0x18001994b  mov     ecx, ebp; dwErrCode
0x18001994d  call    cs:__imp_SetLastError
0x180019953  jmp     short loc_180019957
0x180019955  mov     ebx, edi
0x180019957  mov     eax, ebx
0x180019959  mov     rcx, [rsp+2C8h+var_48]
0x180019961  xor     rcx, rsp; StackCookie
0x180019964  call    __security_check_cookie
0x180019969  mov     rbx, [rsp+2C8h+arg_8]
0x180019971  add     rsp, 290h
0x180019978  pop     r15
0x18001997a  pop     r14
0x18001997c  pop     r13
0x18001997e  pop     r12
0x180019980  pop     rdi
0x180019981  pop     rsi
0x180019982  pop     rbp
0x180019983  retn
```
