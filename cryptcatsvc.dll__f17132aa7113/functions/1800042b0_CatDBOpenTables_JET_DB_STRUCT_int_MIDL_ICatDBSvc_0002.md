# _CatDBOpenTables(_JET_DB_STRUCT *,int,__MIDL_ICatDBSvc_0002)

- ea: `0x1800042b0`
- end: `0x18000481b`
- name: `?_CatDBOpenTables@@YAJPEAU_JET_DB_STRUCT@@HW4__MIDL_ICatDBSvc_0002@@@Z`
- size: `1387`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180001328`

## callees

- `0x1800038f0`
- `0x1800042b0`
- `0x18000a59c`
- `0x18000aad4`
- `0x18000acbc`
- `0x18000be40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004478`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004497`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004514`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004565`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004635`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000469f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004718`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000476b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004787`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004478`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004497`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004514`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004565`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004635`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000469f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004718`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000476b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004787`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047ec`
- `ESENT!JetGetTableIndexInfoW` at `0x180004598`
- `ESENT!JetGetTableIndexInfoW` at `0x180004598`
- `ESENT!JetGetColumnInfoW` at `0x1800043a9`
- `ESENT!JetGetColumnInfoW` at `0x180004422`
- `ESENT!JetGetColumnInfoW` at `0x180004619`
- `ESENT!JetGetColumnInfoW` at `0x180004683`
- `ESENT!JetGetColumnInfoW` at `0x1800046fc`
- `ESENT!JetGetColumnInfoW` at `0x1800043a9`
- `ESENT!JetGetColumnInfoW` at `0x180004422`
- `ESENT!JetGetColumnInfoW` at `0x180004619`
- `ESENT!JetGetColumnInfoW` at `0x180004683`
- `ESENT!JetGetColumnInfoW` at `0x1800046fc`
- `ESENT!JetOpenTableW` at `0x180004365`
- `ESENT!JetOpenTableW` at `0x180004549`
- `ESENT!JetOpenTableW` at `0x180004365`
- `ESENT!JetOpenTableW` at `0x180004549`
- `ESENT!JetSetCurrentIndexW` at `0x180004455`
- `ESENT!JetSetCurrentIndexW` at `0x18000474b`
- `ESENT!JetSetCurrentIndexW` at `0x180004455`
- `ESENT!JetSetCurrentIndexW` at `0x18000474b`

## pseudocode

```c
__int64 __fastcall _CatDBOpenTables(__int64 a1, int a2, unsigned int a3)
{
  JET_TABLEID *ptableid; // r15
  unsigned int v4; // r13d
  unsigned int v5; // ebx
  JET_GRBIT v6; // r12d
  JET_SESID v8; // rcx
  unsigned __int64 v9; // r14
  unsigned int ColumnInfoW; // edi
  JET_TABLEID v11; // rdx
  DWORD v12; // eax
  unsigned int v13; // edx
  unsigned __int16 *v14; // rcx
  unsigned int v15; // r8d
  DWORD v16; // eax
  DWORD v17; // eax
  DWORD v18; // eax
  unsigned int v19; // edx
  unsigned __int16 *v20; // rcx
  DWORD v21; // eax
  unsigned int v22; // edx
  unsigned __int16 *v23; // rcx
  DWORD v24; // eax
  unsigned int v25; // edx
  unsigned __int16 *v26; // rcx
  DWORD v27; // eax
  DWORD v28; // eax
  DWORD v29; // eax
  DWORD v30; // eax
  JET_DBID v31; // edx
  JET_SESID v32; // rcx
  DWORD v33; // eax
  JET_DBID v34; // edx
  JET_SESID v35; // rcx
  DWORD v36; // eax
  JET_TABLEID v37; // rdx
  JET_SESID v38; // rcx
  DWORD v39; // eax
  DWORD v40; // eax
  DWORD v41; // eax
  DWORD v42; // eax
  DWORD LastError; // ebx
  JET_GRBIT grbit; // [rsp+28h] [rbp-58h]
  JET_GRBIT grbita; // [rsp+28h] [rbp-58h]
  JET_GRBIT grbitb; // [rsp+28h] [rbp-58h]
  __int64 v48; // [rsp+40h] [rbp-40h]
  __int16 v49; // [rsp+48h] [rbp-38h] BYREF
  _BYTE pvResult[28]; // [rsp+50h] [rbp-30h] BYREF

  ptableid = (JET_TABLEID *)(a1 + 64);
  v4 = 2;
  *(_OWORD *)(a1 + 24) = 0;
  v5 = a3;
  v6 = a2 != 0 ? 4 : 0;
  v49 = 0;
  *(_OWORD *)pvResult = 0;
  *(_OWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_OWORD *)&pvResult[12] = 0;
  if ( a3 != 2 )
    v4 = a3 + 1;
  *(_DWORD *)(a1 + 56) = a3;
  if ( a3 == 2 )
    v5 = 0;
  while ( 1 )
  {
    v8 = *(_QWORD *)(a1 + 8);
    if ( v5 >= v4 )
      break;
    v48 = 16LL * v5;
    v9 = (unsigned __int64)v5 << 6;
    ColumnInfoW = JetOpenTableW(
                    v8,
                    *(_DWORD *)(a1 + 16),
                    *(wchar_t **)((char *)&off_180023000 + v9 + 16),
                    0,
                    0,
                    v6,
                    (JET_TABLEID *)(a1 + v48 + 24));
    if ( (unsigned int)_CatDBJET_errFailure(ColumnInfoW) )
    {
      v24 = _CatDBMapJetError(ColumnInfoW);
      SetLastError(v24);
      ErrLog_LogError(v26, v25, 0x178Eu, 0, 0, grbit);
      goto LABEL_47;
    }
    ColumnInfoW = JetGetColumnInfoW(
                    *(_QWORD *)(a1 + 8),
                    *(_DWORD *)(a1 + 16),
                    *(wchar_t **)((char *)&off_180023000 + v9 + 16),
                    *(wchar_t **)((char *)&off_180023000 + v9 + 24),
                    pvResult,
                    0x1Cu,
                    0);
    if ( (unsigned int)_CatDBJET_errFailure(ColumnInfoW) )
    {
      v21 = _CatDBMapJetError(ColumnInfoW);
      SetLastError(v21);
      ErrLog_LogError(v23, v22, 0x179Bu, 0, 0, grbita);
      goto LABEL_47;
    }
    if ( *(_DWORD *)&pvResult[8] != 9
      || *(_DWORD *)&pvResult[20] != *(_DWORD *)((char *)&off_180023000 + v9 + 8)
      || *(_DWORD *)&pvResult[24] != 5 )
    {
      ColumnInfoW = -1507;
      v18 = _CatDBMapJetError(-1507);
      SetLastError(v18);
      ErrLog_LogError(v20, v19, 0x17A4u, 0, 0, grbita);
      goto LABEL_47;
    }
    *(_DWORD *)(a1 + 16 * (v5 + 2LL)) = *(_DWORD *)&pvResult[4];
    ColumnInfoW = JetGetColumnInfoW(
                    *(_QWORD *)(a1 + 8),
                    *(_DWORD *)(a1 + 16),
                    *(wchar_t **)((char *)&off_180023000 + v9 + 16),
                    *(wchar_t **)((char *)&off_180023000 + v9 + 32),
                    pvResult,
                    0x1Cu,
                    0);
    if ( (unsigned int)_CatDBJET_errFailure(ColumnInfoW) )
    {
      v17 = _CatDBMapJetError(ColumnInfoW);
      SetLastError(v17);
      v15 = 6067;
      goto LABEL_46;
    }
    if ( *(_DWORD *)&pvResult[8] != 11 )
    {
      ColumnInfoW = -1507;
      v16 = _CatDBMapJetError(-1507);
      SetLastError(v16);
      v15 = 6074;
      goto LABEL_46;
    }
    v11 = *(_QWORD *)(v48 + a1 + 24);
    *(_DWORD *)(v48 + a1 + 36) = *(_DWORD *)&pvResult[4];
    ColumnInfoW = JetSetCurrentIndexW(*(_QWORD *)(a1 + 8), v11, 0);
    if ( (unsigned int)_CatDBJET_errFailure(ColumnInfoW) )
    {
      v12 = _CatDBMapJetError(ColumnInfoW);
      SetLastError(v12);
      v15 = 6086;
      goto LABEL_46;
    }
    ++v5;
  }
  ColumnInfoW = JetOpenTableW(v8, *(_DWORD *)(a1 + 16), L"CatNameAttrTable", 0, 0, v6, ptableid);
  if ( (unsigned int)_CatDBJET_errFailure(ColumnInfoW) )
  {
    v27 = _CatDBMapJetError(ColumnInfoW);
    SetLastError(v27);
    v15 = 6104;
  }
  else
  {
    ColumnInfoW = JetGetTableIndexInfoW(*(_QWORD *)(a1 + 8), *ptableid, L"CatNameAttrTable_Index", &v49, 2u, 0xAu);
    if ( (unsigned int)_CatDBJET_errFailure(ColumnInfoW) )
    {
      v28 = _CatDBMapJetError(ColumnInfoW);
      SetLastError(v28);
      v15 = 6116;
    }
    else if ( v49 == 512 )
    {
      ColumnInfoW = JetGetColumnInfoW(
                      *(_QWORD *)(a1 + 8),
                      *(_DWORD *)(a1 + 16),
                      L"CatNameAttrTable",
                      L"CatNameAttrTable_CatNameCol",
                      pvResult,
                      0x1Cu,
                      0);
      if ( (unsigned int)_CatDBJET_errFailure(ColumnInfoW) )
      {
        v30 = _CatDBMapJetError(ColumnInfoW);
        SetLastError(v30);
        v15 = 6135;
      }
      else if ( *(_DWORD *)&pvResult[8] == 11 && *(_DWORD *)&pvResult[20] == 512 )
      {
        v31 = *(_DWORD *)(a1 + 16);
        v32 = *(_QWORD *)(a1 + 8);
        *(_DWORD *)(a1 + 72) = *(_DWORD *)&pvResult[4];
        ColumnInfoW = JetGetColumnInfoW(
                        v32,
                        v31,
                        L"CatNameAttrTable",
                        L"CatNameAttrTable_CatFileNameCol",
                        pvResult,
                        0x1Cu,
                        0);
        if ( (unsigned int)_CatDBJET_errFailure(ColumnInfoW) )
        {
          v33 = _CatDBMapJetError(ColumnInfoW);
          SetLastError(v33);
          v15 = 6157;
        }
        else if ( *(_DWORD *)&pvResult[8] == 12 && *(_WORD *)&pvResult[16] == 1200 && *(_DWORD *)&pvResult[20] == 512 )
        {
          v34 = *(_DWORD *)(a1 + 16);
          v35 = *(_QWORD *)(a1 + 8);
          *(_DWORD *)(a1 + 76) = *(_DWORD *)&pvResult[4];
          ColumnInfoW = JetGetColumnInfoW(
                          v35,
                          v34,
                          L"CatNameAttrTable",
                          L"CatNameAttrTable_AttrCol",
                          pvResult,
                          0x1Cu,
                          0);
          if ( (unsigned int)_CatDBJET_errFailure(ColumnInfoW) )
          {
            v36 = _CatDBMapJetError(ColumnInfoW);
            SetLastError(v36);
            v15 = 6180;
          }
          else if ( *(_DWORD *)&pvResult[8] == 9 && *(_DWORD *)&pvResult[20] == 64 && *(_DWORD *)&pvResult[24] == 5 )
          {
            v37 = *ptableid;
            v38 = *(_QWORD *)(a1 + 8);
            *(_DWORD *)(a1 + 80) = *(_DWORD *)&pvResult[4];
            ColumnInfoW = JetSetCurrentIndexW(v38, v37, 0);
            if ( !(unsigned int)_CatDBJET_errFailure(ColumnInfoW) )
              return ColumnInfoW;
            v39 = _CatDBMapJetError(ColumnInfoW);
            SetLastError(v39);
            v15 = 6201;
          }
          else
          {
            ColumnInfoW = -1507;
            v40 = _CatDBMapJetError(-1507);
            SetLastError(v40);
            v15 = 6189;
          }
        }
        else
        {
          ColumnInfoW = -1507;
          v41 = _CatDBMapJetError(-1507);
          SetLastError(v41);
          v15 = 6165;
        }
      }
      else
      {
        ColumnInfoW = -1507;
        v42 = _CatDBMapJetError(-1507);
        SetLastError(v42);
        v15 = 6142;
      }
    }
    else
    {
      ColumnInfoW = -1409;
      v29 = _CatDBMapJetError(-1409);
      SetLastError(v29);
      v15 = 6122;
    }
  }
LABEL_46:
  ErrLog_LogError(v14, v13, v15, 0, 0, grbitb);
LABEL_47:
  LastError = GetLastError();
  _CatDBCloseDBTables((struct _JET_DB_STRUCT *)a1, 0);
  SetLastError(LastError);
  return ColumnInfoW;
}

```

## disassembly

```asm
0x1800042b0  mov     [rsp-38h+arg_8], rbx
0x1800042b5  push    rbp
0x1800042b6  push    rsi
0x1800042b7  push    rdi
0x1800042b8  push    r12
0x1800042ba  push    r13
0x1800042bc  push    r14
0x1800042be  push    r15
0x1800042c0  mov     rbp, rsp
0x1800042c3  sub     rsp, 80h
0x1800042ca  mov     rax, cs:__security_cookie
0x1800042d1  xor     rax, rsp
0x1800042d4  mov     [rbp+var_10], rax
0x1800042d8  xorps   xmm0, xmm0
0x1800042db  lea     r15, [rcx+40h]
0x1800042df  neg     edx
0x1800042e1  mov     r13d, 2
0x1800042e7  movups  xmmword ptr [rcx+18h], xmm0
0x1800042eb  sbb     r12d, r12d
0x1800042ee  mov     ebx, r8d
0x1800042f1  xor     r14d, r14d
0x1800042f4  and     r12d, 4
0x1800042f8  mov     [rbp+var_38], r14w
0x1800042fd  mov     rsi, rcx
0x180004300  movups  [rbp+pvResult], xmm0
0x180004304  movups  xmmword ptr [rcx+28h], xmm0
0x180004308  mov     [r15], r14
0x18000430b  movups  [rbp+pvResult+0Ch], xmm0
0x18000430f  cmp     r8d, r13d
0x180004312  jz      short loc_180004318
0x180004314  lea     r13d, [r8+1]
0x180004318  mov     [rcx+38h], ebx
0x18000431b  cmovz   ebx, r14d
0x18000431f  mov     rcx, [rsi+8]; sesid
0x180004323  lea     rdx, off_180023000; "SHA1"
0x18000432a  xor     r9d, r9d; pvParameters
0x18000432d  cmp     ebx, r13d
0x180004330  jnb     loc_18000452D
0x180004336  mov     eax, ebx
0x180004338  shl     rax, 4
0x18000433c  mov     [rbp+var_40], rax
0x180004340  add     rax, 18h
0x180004344  add     rax, rsi
0x180004347  mov     r14d, ebx
0x18000434a  mov     [rsp+80h+ptableid], rax; ptableid
0x18000434f  shl     r14, 6
0x180004353  mov     [rsp+80h+grbit], r12d; grbit
0x180004358  mov     [rsp+80h+cbParameters], r9d; cbParameters
0x18000435d  mov     r8, [r14+rdx+10h]; szTableName
0x180004362  mov     edx, [rsi+10h]; dbid
0x180004365  call    cs:__imp_JetOpenTableW
0x18000436b  mov     ecx, eax; int
0x18000436d  mov     edi, eax
0x18000436f  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180004374  test    eax, eax
0x180004376  jnz     loc_18000450B
0x18000437c  mov     edx, [rsi+10h]; dbid
0x18000437f  lea     r8, off_180023000; "SHA1"
0x180004386  mov     r9, [r14+r8+18h]; pwColumnNameOrId
0x18000438b  mov     r8, [r14+r8+10h]; szTableName
0x180004390  mov     rcx, [rsi+8]; sesid
0x180004394  mov     dword ptr [rsp+80h+ptableid], eax; InfoLevel
0x180004398  lea     rax, [rbp+pvResult]
0x18000439c  mov     [rsp+80h+grbit], 1Ch; cbMax
0x1800043a4  mov     qword ptr [rsp+80h+cbParameters], rax; pvResult
0x1800043a9  call    cs:__imp_JetGetColumnInfoW
0x1800043af  mov     ecx, eax; int
0x1800043b1  mov     edi, eax
0x1800043b3  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800043b8  test    eax, eax
0x1800043ba  jnz     loc_1800044E9
0x1800043c0  cmp     dword ptr [rbp+pvResult+8], 9
0x1800043c4  jnz     loc_1800044C2
0x1800043ca  lea     rdx, off_180023000; "SHA1"
0x1800043d1  mov     eax, [r14+rdx+8]
0x1800043d6  cmp     [rbp+var_1C], eax
0x1800043d9  jnz     loc_1800044C2
0x1800043df  cmp     [rbp+var_18], 5
0x1800043e3  jnz     loc_1800044C2
0x1800043e9  mov     eax, dword ptr [rbp+pvResult+4]
0x1800043ec  mov     dword ptr [rsp+80h+ptableid], 0; InfoLevel
0x1800043f4  mov     ecx, ebx
0x1800043f6  add     rcx, 2
0x1800043fa  mov     [rsp+80h+grbit], 1Ch; cbMax
0x180004402  add     rcx, rcx
0x180004405  mov     [rsi+rcx*8], eax
0x180004408  lea     rax, [rbp+pvResult]
0x18000440c  mov     r9, [r14+rdx+20h]; pwColumnNameOrId
0x180004411  mov     r8, [r14+rdx+10h]; szTableName
0x180004416  mov     edx, [rsi+10h]; dbid
0x180004419  mov     rcx, [rsi+8]; sesid
0x18000441d  mov     qword ptr [rsp+80h+cbParameters], rax; pvResult
0x180004422  call    cs:__imp_JetGetColumnInfoW
0x180004428  mov     ecx, eax; int
0x18000442a  mov     edi, eax
0x18000442c  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180004431  xor     r14d, r14d
0x180004434  test    eax, eax
0x180004436  jnz     short loc_1800044A8
0x180004438  cmp     dword ptr [rbp+pvResult+8], 0Bh
0x18000443c  jnz     short loc_180004489
0x18000443e  mov     rcx, [rbp+var_40]
0x180004442  xor     r8d, r8d; szIndexName
0x180004445  mov     eax, dword ptr [rbp+pvResult+4]
0x180004448  mov     rdx, [rcx+rsi+18h]; tableid
0x18000444d  mov     [rcx+rsi+24h], eax
0x180004451  mov     rcx, [rsi+8]; sesid
0x180004455  call    cs:__imp_JetSetCurrentIndexW
0x18000445b  mov     ecx, eax; int
0x18000445d  mov     edi, eax
0x18000445f  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180004464  test    eax, eax
0x180004466  jnz     short loc_18000446F
0x180004468  inc     ebx
0x18000446a  jmp     loc_18000431F
0x18000446f  mov     ecx, edi; int
0x180004471  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180004476  mov     ecx, eax; dwErrCode
0x180004478  call    cs:__imp_SetLastError
0x18000447e  mov     r8d, 17C6h
0x180004484  jmp     loc_1800047CB
0x180004489  mov     ecx, 0FFFFFA1Dh; int
0x18000448e  mov     edi, ecx
0x180004490  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180004495  mov     ecx, eax; dwErrCode
0x180004497  call    cs:__imp_SetLastError
0x18000449d  mov     r8d, 17BAh
0x1800044a3  jmp     loc_1800047CB
0x1800044a8  mov     ecx, edi; int
0x1800044aa  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800044af  mov     ecx, eax; dwErrCode
0x1800044b1  call    cs:__imp_SetLastError
0x1800044b7  mov     r8d, 17B3h
0x1800044bd  jmp     loc_1800047CB
0x1800044c2  mov     ecx, 0FFFFFA1Dh; int
0x1800044c7  mov     edi, ecx
0x1800044c9  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800044ce  mov     ecx, eax; dwErrCode
0x1800044d0  call    cs:__imp_SetLastError
0x1800044d6  mov     r8d, 17A4h
0x1800044dc  mov     [rsp+80h+cbParameters], 0
0x1800044e4  jmp     loc_1800047D0
0x1800044e9  mov     ecx, edi; int
0x1800044eb  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800044f0  mov     ecx, eax; dwErrCode
0x1800044f2  call    cs:__imp_SetLastError
0x1800044f8  mov     r8d, 179Bh
0x1800044fe  mov     [rsp+80h+cbParameters], 0
0x180004506  jmp     loc_1800047D0
0x18000450b  mov     ecx, edi; int
0x18000450d  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180004512  mov     ecx, eax; dwErrCode
0x180004514  call    cs:__imp_SetLastError
0x18000451a  mov     r8d, 178Eh
0x180004520  mov     [rsp+80h+cbParameters], 0
0x180004528  jmp     loc_1800047D0
0x18000452d  mov     edx, [rsi+10h]; dbid
0x180004530  mov     [rsp+80h+ptableid], r15; ptableid
0x180004535  mov     [rsp+80h+grbit], r12d; grbit
0x18000453a  lea     r12, szTableName; "CatNameAttrTable"
0x180004541  mov     r8, r12; szTableName
0x180004544  mov     [rsp+80h+cbParameters], r14d; cbParameters
0x180004549  call    cs:__imp_JetOpenTableW
0x18000454f  mov     ecx, eax; int
0x180004551  mov     edi, eax
0x180004553  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180004558  test    eax, eax
0x18000455a  jz      short loc_180004576
0x18000455c  mov     ecx, edi; int
0x18000455e  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180004563  mov     ecx, eax; dwErrCode
0x180004565  call    cs:__imp_SetLastError
0x18000456b  mov     r8d, 17D8h
0x180004571  jmp     loc_1800047CB
0x180004576  mov     rdx, [r15]; tableid
0x180004579  lea     r9, [rbp+var_38]; pvResult
0x18000457d  mov     rcx, [rsi+8]; sesid
0x180004581  lea     r8, szIndexName; "CatNameAttrTable_Index"
0x180004588  mov     [rsp+80h+grbit], 0Ah; InfoLevel
0x180004590  mov     [rsp+80h+cbParameters], 2; cbResult
0x180004598  call    cs:__imp_JetGetTableIndexInfoW
0x18000459e  mov     ecx, eax; int
0x1800045a0  mov     edi, eax
0x1800045a2  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800045a7  test    eax, eax
0x1800045a9  jz      short loc_1800045C5
0x1800045ab  mov     ecx, edi; int
0x1800045ad  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800045b2  mov     ecx, eax; dwErrCode
0x1800045b4  call    cs:__imp_SetLastError
0x1800045ba  mov     r8d, 17E4h
0x1800045c0  jmp     loc_1800047CB
0x1800045c5  mov     ebx, 200h
0x1800045ca  cmp     [rbp+var_38], bx
0x1800045ce  jz      short loc_1800045EF
0x1800045d0  mov     edi, 0FFFFFA7Fh
0x1800045d5  mov     ecx, edi; int
0x1800045d7  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800045dc  mov     ecx, eax; dwErrCode
0x1800045de  call    cs:__imp_SetLastError
0x1800045e4  mov     r8d, 17EAh
0x1800045ea  jmp     loc_1800047CB
0x1800045ef  mov     edx, [rsi+10h]; dbid
0x1800045f2  lea     rax, [rbp+pvResult]
0x1800045f6  mov     rcx, [rsi+8]; sesid
0x1800045fa  lea     r9, szColumnName; "CatNameAttrTable_CatNameCol"
0x180004601  mov     dword ptr [rsp+80h+ptableid], r14d; InfoLevel
0x180004606  mov     r13d, 1Ch
0x18000460c  mov     [rsp+80h+grbit], r13d; int
0x180004611  mov     r8, r12; szTableName
0x180004614  mov     qword ptr [rsp+80h+cbParameters], rax; pvResult
0x180004619  call    cs:__imp_JetGetColumnInfoW
0x18000461f  mov     ecx, eax; int
0x180004621  mov     edi, eax
0x180004623  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180004628  test    eax, eax
0x18000462a  jz      short loc_180004646
0x18000462c  mov     ecx, edi; int
0x18000462e  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180004633  mov     ecx, eax; dwErrCode
0x180004635  call    cs:__imp_SetLastError
0x18000463b  mov     r8d, 17F7h
0x180004641  jmp     loc_1800047CB
0x180004646  cmp     dword ptr [rbp+pvResult+8], 0Bh
0x18000464a  jnz     loc_1800047B1
0x180004650  cmp     [rbp+var_1C], ebx
0x180004653  jnz     loc_1800047B1
0x180004659  mov     eax, dword ptr [rbp+pvResult+4]
0x18000465c  lea     r9, aCatnameattrtab_1; "CatNameAttrTable_CatFileNameCol"
0x180004663  mov     edx, [rsi+10h]; dbid
0x180004666  mov     r8, r12; szTableName
0x180004669  mov     rcx, [rsi+8]; sesid
0x18000466d  mov     [rsi+48h], eax
0x180004670  lea     rax, [rbp+pvResult]
0x180004674  mov     dword ptr [rsp+80h+ptableid], r14d; InfoLevel
0x180004679  mov     [rsp+80h+grbit], r13d; cbMax
0x18000467e  mov     qword ptr [rsp+80h+cbParameters], rax; pvResult
0x180004683  call    cs:__imp_JetGetColumnInfoW
0x180004689  mov     ecx, eax; int
0x18000468b  mov     edi, eax
0x18000468d  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180004692  test    eax, eax
0x180004694  jz      short loc_1800046B0
0x180004696  mov     ecx, edi; int
0x180004698  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18000469d  mov     ecx, eax; dwErrCode
0x18000469f  call    cs:__imp_SetLastError
0x1800046a5  mov     r8d, 180Dh
0x1800046ab  jmp     loc_1800047CB
0x1800046b0  cmp     dword ptr [rbp+pvResult+8], 0Ch
0x1800046b4  jnz     loc_180004795
0x1800046ba  mov     eax, 4B0h
0x1800046bf  cmp     [rbp+var_20], ax
0x1800046c3  jnz     loc_180004795
0x1800046c9  cmp     [rbp+var_1C], ebx
0x1800046cc  jnz     loc_180004795
0x1800046d2  mov     eax, dword ptr [rbp+pvResult+4]
0x1800046d5  lea     r9, aCatnameattrtab_0; "CatNameAttrTable_AttrCol"
0x1800046dc  mov     edx, [rsi+10h]; dbid
0x1800046df  mov     r8, r12; szTableName
0x1800046e2  mov     rcx, [rsi+8]; sesid
0x1800046e6  mov     [rsi+4Ch], eax
0x1800046e9  lea     rax, [rbp+pvResult]
0x1800046ed  mov     dword ptr [rsp+80h+ptableid], r14d; InfoLevel
0x1800046f2  mov     [rsp+80h+grbit], r13d; cbMax
0x1800046f7  mov     qword ptr [rsp+80h+cbParameters], rax; pvResult
0x1800046fc  call    cs:__imp_JetGetColumnInfoW
0x180004702  mov     ecx, eax; int
0x180004704  mov     edi, eax
0x180004706  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18000470b  test    eax, eax
0x18000470d  jz      short loc_180004729
0x18000470f  mov     ecx, edi; int
0x180004711  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180004716  mov     ecx, eax; dwErrCode
0x180004718  call    cs:__imp_SetLastError
0x18000471e  mov     r8d, 1824h
0x180004724  jmp     loc_1800047CB
0x180004729  cmp     dword ptr [rbp+pvResult+8], 9
0x18000472d  jnz     short loc_180004779
0x18000472f  cmp     [rbp+var_1C], 40h ; '@'
0x180004733  jnz     short loc_180004779
0x180004735  cmp     [rbp+var_18], 5
0x180004739  jnz     short loc_180004779
0x18000473b  mov     eax, dword ptr [rbp+pvResult+4]
0x18000473e  xor     r8d, r8d; szIndexName
0x180004741  mov     rdx, [r15]; tableid
0x180004744  mov     rcx, [rsi+8]; sesid
0x180004748  mov     [rsi+50h], eax
0x18000474b  call    cs:__imp_JetSetCurrentIndexW
0x180004751  mov     ecx, eax; int
0x180004753  mov     edi, eax
0x180004755  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18000475a  test    eax, eax
0x18000475c  jz      loc_1800047F2
0x180004762  mov     ecx, edi; int
0x180004764  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180004769  mov     ecx, eax; dwErrCode
0x18000476b  call    cs:__imp_SetLastError
0x180004771  mov     r8d, 1839h
  ... truncated ...
```
