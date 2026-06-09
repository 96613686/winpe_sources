# _CatDBCreateDBTables(_JET_DB_STRUCT *,ulong)

- ea: `0x180018b38`
- end: `0x1800190f1`
- name: `?_CatDBCreateDBTables@@YAHPEAU_JET_DB_STRUCT@@K@Z`
- size: `1465`
- prototype: `int(struct _JET_DB_STRUCT *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800188dc`

## callees

- `0x1800038f0`
- `0x18000a59c`
- `0x18000acbc`
- `0x18000be40`
- `0x18000c7e8`
- `0x180018b38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018d61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018d7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018d9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018db8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018dd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018df4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018e42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018e7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018eca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018f42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018fb8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001902d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800190ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018d61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018d7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018d9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018db8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018dd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018df4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018e42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018e7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018eca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018f42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018fb8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001902d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800190ac`
- `ESENT!JetAddColumnW` at `0x180018c98`
- `ESENT!JetAddColumnW` at `0x180018cf2`
- `ESENT!JetAddColumnW` at `0x180018f24`
- `ESENT!JetAddColumnW` at `0x180018f9a`
- `ESENT!JetAddColumnW` at `0x18001900f`
- `ESENT!JetAddColumnW` at `0x180018c98`
- `ESENT!JetAddColumnW` at `0x180018cf2`
- `ESENT!JetAddColumnW` at `0x180018f24`
- `ESENT!JetAddColumnW` at `0x180018f9a`
- `ESENT!JetAddColumnW` at `0x18001900f`
- `ESENT!JetCloseTable` at `0x180018bf1`
- `ESENT!JetCloseTable` at `0x180018e5a`
- `ESENT!JetCloseTable` at `0x180018bf1`
- `ESENT!JetCloseTable` at `0x180018e5a`
- `ESENT!JetCreateIndexW` at `0x180018d3a`
- `ESENT!JetCreateIndexW` at `0x180018d3a`
- `ESENT!JetCreateTableW` at `0x180018bd2`
- `ESENT!JetCreateTableW` at `0x180018e24`
- `ESENT!JetCreateTableW` at `0x180018bd2`
- `ESENT!JetCreateTableW` at `0x180018e24`
- `ESENT!JetCreateIndex3W` at `0x180019090`
- `ESENT!JetCreateIndex3W` at `0x180019090`
- `ESENT!JetOpenTableW` at `0x180018c33`
- `ESENT!JetOpenTableW` at `0x180018eac`
- `ESENT!JetOpenTableW` at `0x180018c33`
- `ESENT!JetOpenTableW` at `0x180018eac`

## pseudocode

```c
__int64 __fastcall _CatDBCreateDBTables(struct _JET_DB_STRUCT *a1, JET_DBID a2)
{
  unsigned int v4; // r15d
  unsigned int v5; // esi
  unsigned __int64 v6; // r14
  char *v7; // rdi
  JET_ERR TableW; // r12d
  JET_ERR v9; // eax
  int v10; // r12d
  JET_ERR v11; // r12d
  const WCHAR *v12; // r8
  JET_TABLEID v13; // rdx
  JET_SESID v14; // rcx
  JET_ERR v15; // r12d
  JET_TABLEID v16; // rdx
  const WCHAR *v17; // r8
  JET_SESID v18; // rcx
  JET_ERR v19; // r12d
  JET_ERR IndexW; // edi
  DWORD v21; // eax
  unsigned int v22; // edx
  unsigned __int16 *v23; // rcx
  unsigned int v24; // r8d
  DWORD v25; // eax
  DWORD v26; // eax
  DWORD v27; // eax
  DWORD v28; // eax
  DWORD v29; // eax
  JET_TABLEID *v30; // rdi
  JET_ERR v31; // r14d
  DWORD v32; // eax
  JET_ERR v33; // eax
  int v34; // r14d
  DWORD v35; // eax
  JET_ERR v36; // r14d
  DWORD v37; // eax
  JET_TABLEID v38; // rdx
  JET_SESID v39; // rcx
  JET_ERR v40; // r14d
  DWORD v41; // eax
  JET_TABLEID v42; // rdx
  JET_SESID v43; // rcx
  JET_ERR v44; // r14d
  DWORD v45; // eax
  JET_TABLEID v46; // rdx
  JET_SESID v47; // rcx
  JET_ERR v48; // r14d
  DWORD v49; // eax
  JET_TABLEID v50; // rdx
  JET_SESID v51; // rcx
  JET_ERR v52; // ebx
  DWORD v53; // eax
  int ptableid; // [rsp+28h] [rbp-81h]
  JET_INDEXCREATE2_W pindexcreate; // [rsp+40h] [rbp-69h] BYREF
  JET_COLUMNDEF pcolumndef; // [rsp+A0h] [rbp-9h] BYREF

  memset(&pcolumndef, 0, sizeof(pcolumndef));
  memset_0(&pindexcreate, 0, sizeof(pindexcreate));
  v4 = 0;
  v5 = 1;
  while ( v4 < 2 )
  {
    v6 = (unsigned __int64)v4 << 6;
    v7 = (char *)a1 + 16 * v4 + 24;
    TableW = JetCreateTableW(
               *((_QWORD *)a1 + 1),
               a2,
               *(wchar_t **)((char *)&off_180023000 + v6 + 16),
               4u,
               0x64u,
               (JET_TABLEID *)v7);
    if ( (unsigned int)_CatDBJET_errFailure(TableW) )
    {
      v29 = _CatDBMapJetError(TableW);
      SetLastError(v29);
      v24 = 6285;
      goto LABEL_30;
    }
    v9 = JetCloseTable(*((_QWORD *)a1 + 1), *(_QWORD *)v7);
    *(_QWORD *)v7 = 0;
    v10 = v9;
    if ( (unsigned int)_CatDBJET_errFailure(v9) )
    {
      v28 = _CatDBMapJetError(v10);
      SetLastError(v28);
      v24 = 6293;
      goto LABEL_30;
    }
    v11 = JetOpenTableW(
            *((_QWORD *)a1 + 1),
            a2,
            *(wchar_t **)((char *)&off_180023000 + v6 + 16),
            0,
            0,
            0,
            (JET_TABLEID *)v7);
    if ( (unsigned int)_CatDBJET_errFailure(v11) )
    {
      v27 = _CatDBMapJetError(v11);
      SetLastError(v27);
      v24 = 6306;
      goto LABEL_30;
    }
    *(_QWORD *)&pcolumndef.wCountry = 0;
    v12 = *(wchar_t **)((char *)&off_180023000 + v6 + 24);
    v13 = *(_QWORD *)v7;
    pcolumndef.cbMax = *(_DWORD *)((char *)&off_180023000 + v6 + 8);
    v14 = *((_QWORD *)a1 + 1);
    *(_QWORD *)&pcolumndef.cbStruct = 28;
    pcolumndef.coltyp = 9;
    pcolumndef.grbit = 5;
    v15 = JetAddColumnW(v14, v13, v12, &pcolumndef, 0, 0, (JET_COLUMNID *)v7 + 2);
    if ( (unsigned int)_CatDBJET_errFailure(v15) )
    {
      v26 = _CatDBMapJetError(v15);
      SetLastError(v26);
      v24 = 6326;
      goto LABEL_30;
    }
    v16 = *(_QWORD *)v7;
    v17 = *(wchar_t **)((char *)&off_180023000 + v6 + 32);
    v18 = *((_QWORD *)a1 + 1);
    *(_QWORD *)&pcolumndef.cbStruct = 28;
    *(_OWORD *)&pcolumndef.wCountry = 0;
    pcolumndef.coltyp = 11;
    v19 = JetAddColumnW(v18, v16, v17, &pcolumndef, 0, 0, (JET_COLUMNID *)v7 + 3);
    if ( (unsigned int)_CatDBJET_errFailure(v19) )
    {
      v25 = _CatDBMapJetError(v19);
      SetLastError(v25);
      v24 = 6344;
      goto LABEL_30;
    }
    IndexW = JetCreateIndexW(
               *((_QWORD *)a1 + 1),
               *(_QWORD *)v7,
               *(wchar_t **)((char *)&off_180023000 + v6 + 40),
               3u,
               *(wchar_t **)((char *)&off_180023000 + v6 + 48),
               *(_DWORD *)((char *)&off_180023000 + v6 + 56),
               0x50u);
    if ( (unsigned int)_CatDBJET_errFailure(IndexW) )
    {
      v21 = _CatDBMapJetError(IndexW);
      SetLastError(v21);
      v24 = 6358;
      goto LABEL_30;
    }
    ++v4;
  }
  v30 = (JET_TABLEID *)((char *)a1 + 64);
  v31 = JetCreateTableW(*((_QWORD *)a1 + 1), a2, L"CatNameAttrTable", 4u, 0x64u, (JET_TABLEID *)a1 + 8);
  if ( (unsigned int)_CatDBJET_errFailure(v31) )
  {
    v32 = _CatDBMapJetError(v31);
    SetLastError(v32);
    v24 = 6374;
  }
  else
  {
    v33 = JetCloseTable(*((_QWORD *)a1 + 1), *v30);
    *v30 = 0;
    v34 = v33;
    if ( (unsigned int)_CatDBJET_errFailure(v33) )
    {
      v35 = _CatDBMapJetError(v34);
      SetLastError(v35);
      v24 = 6382;
    }
    else
    {
      v36 = JetOpenTableW(*((_QWORD *)a1 + 1), a2, L"CatNameAttrTable", 0, 0, 0, (JET_TABLEID *)a1 + 8);
      if ( (unsigned int)_CatDBJET_errFailure(v36) )
      {
        v37 = _CatDBMapJetError(v36);
        SetLastError(v37);
        v24 = 6395;
      }
      else
      {
        v38 = *v30;
        v39 = *((_QWORD *)a1 + 1);
        *(_QWORD *)&pcolumndef.cbStruct = 28;
        *(_QWORD *)&pcolumndef.wCountry = 0;
        pcolumndef.coltyp = 11;
        pcolumndef.cbMax = 512;
        pcolumndef.grbit = 4;
        v40 = JetAddColumnW(v39, v38, L"CatNameAttrTable_CatNameCol", &pcolumndef, 0, 0, (JET_COLUMNID *)a1 + 18);
        if ( (unsigned int)_CatDBJET_errFailure(v40) )
        {
          v41 = _CatDBMapJetError(v40);
          SetLastError(v41);
          v24 = 6416;
        }
        else
        {
          v42 = *v30;
          v43 = *((_QWORD *)a1 + 1);
          *(_QWORD *)&pcolumndef.cbStruct = 28;
          *(_QWORD *)&pcolumndef.coltyp = 12;
          *(_DWORD *)&pcolumndef.cp = 1200;
          pcolumndef.cbMax = 512;
          pcolumndef.grbit = 4;
          v44 = JetAddColumnW(v43, v42, L"CatNameAttrTable_CatFileNameCol", &pcolumndef, 0, 0, (JET_COLUMNID *)a1 + 19);
          if ( (unsigned int)_CatDBJET_errFailure(v44) )
          {
            v45 = _CatDBMapJetError(v44);
            SetLastError(v45);
            v24 = 6438;
          }
          else
          {
            v46 = *v30;
            v47 = *((_QWORD *)a1 + 1);
            *(_QWORD *)&pcolumndef.cbStruct = 28;
            *(_QWORD *)&pcolumndef.wCountry = 0;
            pcolumndef.coltyp = 9;
            pcolumndef.cbMax = 64;
            pcolumndef.grbit = 5;
            v48 = JetAddColumnW(v47, v46, L"CatNameAttrTable_AttrCol", &pcolumndef, 0, 0, (JET_COLUMNID *)a1 + 20);
            if ( (unsigned int)_CatDBJET_errFailure(v48) )
            {
              v49 = _CatDBMapJetError(v48);
              SetLastError(v49);
              v24 = 6458;
            }
            else
            {
              memset_0(&pindexcreate, 0, sizeof(pindexcreate));
              v50 = *v30;
              v51 = *((_QWORD *)a1 + 1);
              pindexcreate.szIndexName = (WCHAR *)L"CatNameAttrTable_Index";
              pindexcreate.cbStruct = 88;
              pindexcreate.szKey = L"+CatNameAttrTable_CatNameCol";
              pindexcreate.cbKey = 60;
              pindexcreate.grbit = 98307;
              pindexcreate.ulDensity = 80;
              pindexcreate.cbKeyMost = 512;
              v52 = JetCreateIndex3W(v51, v50, &pindexcreate, 1u);
              if ( !(unsigned int)_CatDBJET_errFailure(v52) )
                return v5;
              v53 = _CatDBMapJetError(v52);
              SetLastError(v53);
              v24 = 6478;
            }
          }
        }
      }
    }
  }
LABEL_30:
  ErrLog_LogError(v23, v22, v24, 0, 0, ptableid);
  return 0;
}

```

## disassembly

```asm
0x180018b38  mov     [rsp-8+arg_10], rbx
0x180018b3d  push    rbp
0x180018b3e  push    rsi
0x180018b3f  push    rdi
0x180018b40  push    r12
0x180018b42  push    r13
0x180018b44  push    r14
0x180018b46  push    r15
0x180018b48  lea     rbp, [rsp-27h]
0x180018b4d  sub     rsp, 0D0h
0x180018b54  mov     rax, cs:__security_cookie
0x180018b5b  xor     rax, rsp
0x180018b5e  mov     [rbp+57h+var_40], rax
0x180018b62  xorps   xmm0, xmm0
0x180018b65  mov     r13d, edx
0x180018b68  xor     edx, edx; Val
0x180018b6a  mov     rbx, rcx
0x180018b6d  movups  xmmword ptr [rbp+57h+pcolumndef.cbStruct], xmm0
0x180018b71  lea     rcx, [rbp+57h+pindexcreate]; void *
0x180018b75  movups  xmmword ptr [rbp+57h+pcolumndef.wCountry], xmm0
0x180018b79  lea     r8d, [rdx+58h]; Size
0x180018b7d  call    memset_0
0x180018b82  xor     r12d, r12d
0x180018b85  mov     r15d, r12d
0x180018b88  lea     esi, [r12+1]
0x180018b8d  lea     rcx, off_180023000; "SHA1"
0x180018b94  mov     r9d, 4; lPages
0x180018b9a  mov     edx, r13d; dbid
0x180018b9d  cmp     r15d, 2
0x180018ba1  jnb     loc_180018E08
0x180018ba7  mov     r14d, r15d
0x180018baa  mov     edi, r15d
0x180018bad  shl     rdi, 4
0x180018bb1  shl     r14, 6
0x180018bb5  add     rdi, 18h
0x180018bb9  add     rdi, rbx
0x180018bbc  mov     [rsp+100h+ptableid], rdi; ptableid
0x180018bc1  mov     [rsp+100h+lDensity], 64h ; 'd'; lDensity
0x180018bc9  mov     r8, [r14+rcx+10h]; szTableName
0x180018bce  mov     rcx, [rbx+8]; sesid
0x180018bd2  call    cs:__imp_JetCreateTableW
0x180018bd8  mov     ecx, eax; int
0x180018bda  mov     r12d, eax
0x180018bdd  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018be2  test    eax, eax
0x180018be4  jnz     loc_180018DEA
0x180018bea  mov     rdx, [rdi]; tableid
0x180018bed  mov     rcx, [rbx+8]; sesid
0x180018bf1  call    cs:__imp_JetCloseTable
0x180018bf7  mov     ecx, eax; int
0x180018bf9  mov     qword ptr [rdi], 0
0x180018c00  mov     r12d, eax
0x180018c03  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018c08  test    eax, eax
0x180018c0a  jnz     loc_180018DCC
0x180018c10  mov     rcx, [rbx+8]; sesid
0x180018c14  lea     r8, off_180023000; "SHA1"
0x180018c1b  mov     r8, [r14+r8+10h]; szTableName
0x180018c20  xor     r9d, r9d; pvParameters
0x180018c23  mov     [rsp+100h+pcolumnid], rdi; ptableid
0x180018c28  mov     edx, r13d; dbid
0x180018c2b  mov     dword ptr [rsp+100h+ptableid], eax; grbit
0x180018c2f  mov     [rsp+100h+lDensity], eax; cbParameters
0x180018c33  call    cs:__imp_JetOpenTableW
0x180018c39  mov     ecx, eax; int
0x180018c3b  mov     r12d, eax
0x180018c3e  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018c43  xor     ecx, ecx
0x180018c45  test    eax, eax
0x180018c47  jnz     loc_180018DAE
0x180018c4d  lea     rdx, off_180023000; "SHA1"
0x180018c54  mov     qword ptr [rbp+57h+pcolumndef.wCountry], rcx
0x180018c58  mov     eax, [r14+rdx+8]
0x180018c5d  lea     r9, [rbp+57h+pcolumndef]; pcolumndef
0x180018c61  mov     r8, [r14+rdx+18h]; szColumnName
0x180018c66  mov     rdx, [rdi]; tableid
0x180018c69  mov     [rbp+57h+pcolumndef.cbMax], eax
0x180018c6c  lea     rax, [rdi+8]
0x180018c70  mov     [rsp+100h+pcolumnid], rax; pcolumnid
0x180018c75  mov     dword ptr [rsp+100h+ptableid], ecx; cbDefault
0x180018c79  mov     qword ptr [rsp+100h+lDensity], rcx; pvDefault
0x180018c7e  mov     rcx, [rbx+8]; sesid
0x180018c82  mov     qword ptr [rbp+57h+pcolumndef.cbStruct], 1Ch
0x180018c8a  mov     [rbp+57h+pcolumndef.coltyp], 9
0x180018c91  mov     [rbp+57h+pcolumndef.grbit], 5
0x180018c98  call    cs:__imp_JetAddColumnW
0x180018c9e  mov     ecx, eax; int
0x180018ca0  mov     r12d, eax
0x180018ca3  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018ca8  xor     ecx, ecx
0x180018caa  test    eax, eax
0x180018cac  jnz     loc_180018D90
0x180018cb2  mov     rdx, [rdi]; tableid
0x180018cb5  lea     rax, [rdi+0Ch]
0x180018cb9  mov     [rsp+100h+pcolumnid], rax; pcolumnid
0x180018cbe  lea     r8, off_180023000; "SHA1"
0x180018cc5  mov     r8, [r14+r8+20h]; szColumnName
0x180018cca  lea     r9, [rbp+57h+pcolumndef]; pcolumndef
0x180018cce  mov     dword ptr [rsp+100h+ptableid], ecx; cbDefault
0x180018cd2  xorps   xmm0, xmm0
0x180018cd5  mov     qword ptr [rsp+100h+lDensity], rcx; pvDefault
0x180018cda  mov     rcx, [rbx+8]; sesid
0x180018cde  mov     qword ptr [rbp+57h+pcolumndef.cbStruct], 1Ch
0x180018ce6  movdqu  xmmword ptr [rbp+57h+pcolumndef.wCountry], xmm0
0x180018ceb  mov     [rbp+57h+pcolumndef.coltyp], 0Bh
0x180018cf2  call    cs:__imp_JetAddColumnW
0x180018cf8  mov     ecx, eax; int
0x180018cfa  mov     r12d, eax
0x180018cfd  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018d02  test    eax, eax
0x180018d04  jnz     short loc_180018D72
0x180018d06  mov     rdx, [rdi]; tableid
0x180018d09  lea     rcx, off_180023000; "SHA1"
0x180018d10  mov     eax, [r14+rcx+38h]
0x180018d15  mov     r9d, 3; grbit
0x180018d1b  mov     r8, [r14+rcx+28h]; szIndexName
0x180018d20  mov     dword ptr [rsp+100h+pcolumnid], 50h ; 'P'; lDensity
0x180018d28  mov     dword ptr [rsp+100h+ptableid], eax; cbKey
0x180018d2c  mov     rax, [r14+rcx+30h]
0x180018d31  mov     rcx, [rbx+8]; sesid
0x180018d35  mov     qword ptr [rsp+100h+lDensity], rax; szKey
0x180018d3a  call    cs:__imp_JetCreateIndexW
0x180018d40  mov     ecx, eax; int
0x180018d42  mov     edi, eax
0x180018d44  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018d49  xor     r12d, r12d
0x180018d4c  test    eax, eax
0x180018d4e  jnz     short loc_180018D58
0x180018d50  add     r15d, esi
0x180018d53  jmp     loc_180018B8D
0x180018d58  mov     ecx, edi; int
0x180018d5a  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018d5f  mov     ecx, eax; dwErrCode
0x180018d61  call    cs:__imp_SetLastError
0x180018d67  mov     r8d, 18D6h
0x180018d6d  jmp     loc_1800190B8
0x180018d72  mov     ecx, r12d; int
0x180018d75  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018d7a  mov     ecx, eax; dwErrCode
0x180018d7c  call    cs:__imp_SetLastError
0x180018d82  xor     r12d, r12d
0x180018d85  mov     r8d, 18C8h
0x180018d8b  jmp     loc_1800190B8
0x180018d90  mov     ecx, r12d; int
0x180018d93  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018d98  mov     ecx, eax; dwErrCode
0x180018d9a  call    cs:__imp_SetLastError
0x180018da0  xor     r12d, r12d
0x180018da3  mov     r8d, 18B6h
0x180018da9  jmp     loc_1800190B8
0x180018dae  mov     ecx, r12d; int
0x180018db1  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018db6  mov     ecx, eax; dwErrCode
0x180018db8  call    cs:__imp_SetLastError
0x180018dbe  xor     r12d, r12d
0x180018dc1  mov     r8d, 18A2h
0x180018dc7  jmp     loc_1800190B8
0x180018dcc  mov     ecx, r12d; int
0x180018dcf  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018dd4  mov     ecx, eax; dwErrCode
0x180018dd6  call    cs:__imp_SetLastError
0x180018ddc  xor     r12d, r12d
0x180018ddf  mov     r8d, 1895h
0x180018de5  jmp     loc_1800190B8
0x180018dea  mov     ecx, r12d; int
0x180018ded  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018df2  mov     ecx, eax; dwErrCode
0x180018df4  call    cs:__imp_SetLastError
0x180018dfa  xor     r12d, r12d
0x180018dfd  mov     r8d, 188Dh
0x180018e03  jmp     loc_1800190B8
0x180018e08  mov     rcx, [rbx+8]; sesid
0x180018e0c  lea     rdi, [rbx+40h]
0x180018e10  mov     [rsp+100h+ptableid], rdi; ptableid
0x180018e15  lea     r8, szTableName; "CatNameAttrTable"
0x180018e1c  mov     [rsp+100h+lDensity], 64h ; 'd'; lDensity
0x180018e24  call    cs:__imp_JetCreateTableW
0x180018e2a  mov     ecx, eax; int
0x180018e2c  mov     r14d, eax
0x180018e2f  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018e34  test    eax, eax
0x180018e36  jz      short loc_180018E53
0x180018e38  mov     ecx, r14d; int
0x180018e3b  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018e40  mov     ecx, eax; dwErrCode
0x180018e42  call    cs:__imp_SetLastError
0x180018e48  mov     r8d, 18E6h
0x180018e4e  jmp     loc_1800190B8
0x180018e53  mov     rdx, [rdi]; tableid
0x180018e56  mov     rcx, [rbx+8]; sesid
0x180018e5a  call    cs:__imp_JetCloseTable
0x180018e60  mov     ecx, eax; int
0x180018e62  mov     [rdi], r12
0x180018e65  mov     r14d, eax
0x180018e68  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018e6d  test    eax, eax
0x180018e6f  jz      short loc_180018E8C
0x180018e71  mov     ecx, r14d; int
0x180018e74  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018e79  mov     ecx, eax; dwErrCode
0x180018e7b  call    cs:__imp_SetLastError
0x180018e81  mov     r8d, 18EEh
0x180018e87  jmp     loc_1800190B8
0x180018e8c  mov     rcx, [rbx+8]; sesid
0x180018e90  lea     r8, szTableName; "CatNameAttrTable"
0x180018e97  mov     [rsp+100h+pcolumnid], rdi; ptableid
0x180018e9c  xor     r9d, r9d; pvParameters
0x180018e9f  mov     dword ptr [rsp+100h+ptableid], r12d; grbit
0x180018ea4  mov     edx, r13d; dbid
0x180018ea7  mov     [rsp+100h+lDensity], r12d; cbParameters
0x180018eac  call    cs:__imp_JetOpenTableW
0x180018eb2  mov     ecx, eax; int
0x180018eb4  mov     r14d, eax
0x180018eb7  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018ebc  test    eax, eax
0x180018ebe  jz      short loc_180018EDB
0x180018ec0  mov     ecx, r14d; int
0x180018ec3  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018ec8  mov     ecx, eax; dwErrCode
0x180018eca  call    cs:__imp_SetLastError
0x180018ed0  mov     r8d, 18FBh
0x180018ed6  jmp     loc_1800190B8
0x180018edb  mov     rdx, [rdi]; tableid
0x180018ede  lea     rax, [rbx+48h]
0x180018ee2  mov     rcx, [rbx+8]; sesid
0x180018ee6  lea     r9, [rbp+57h+pcolumndef]; pcolumndef
0x180018eea  mov     [rsp+100h+pcolumnid], rax; pcolumnid
0x180018eef  lea     r8, szColumnName; "CatNameAttrTable_CatNameCol"
0x180018ef6  mov     r15d, 200h
0x180018efc  mov     dword ptr [rsp+100h+ptableid], r12d; cbDefault
0x180018f01  mov     qword ptr [rsp+100h+lDensity], r12; pvDefault
0x180018f06  mov     qword ptr [rbp+57h+pcolumndef.cbStruct], 1Ch
0x180018f0e  mov     qword ptr [rbp+57h+pcolumndef.wCountry], r12
0x180018f12  mov     [rbp+57h+pcolumndef.coltyp], 0Bh
0x180018f19  mov     [rbp+57h+pcolumndef.cbMax], r15d
0x180018f1d  mov     [rbp+57h+pcolumndef.grbit], 4
0x180018f24  call    cs:__imp_JetAddColumnW
0x180018f2a  mov     ecx, eax; int
0x180018f2c  mov     r14d, eax
0x180018f2f  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018f34  test    eax, eax
0x180018f36  jz      short loc_180018F53
0x180018f38  mov     ecx, r14d; int
0x180018f3b  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018f40  mov     ecx, eax; dwErrCode
0x180018f42  call    cs:__imp_SetLastError
0x180018f48  mov     r8d, 1910h
0x180018f4e  jmp     loc_1800190B8
0x180018f53  mov     rdx, [rdi]; tableid
0x180018f56  lea     rax, [rbx+4Ch]
0x180018f5a  mov     rcx, [rbx+8]; sesid
0x180018f5e  lea     r9, [rbp+57h+pcolumndef]; pcolumndef
0x180018f62  mov     [rsp+100h+pcolumnid], rax; pcolumnid
0x180018f67  lea     r8, aCatnameattrtab_1; "CatNameAttrTable_CatFileNameCol"
0x180018f6e  mov     dword ptr [rsp+100h+ptableid], r12d; cbDefault
0x180018f73  mov     qword ptr [rsp+100h+lDensity], r12; pvDefault
0x180018f78  mov     qword ptr [rbp+57h+pcolumndef.cbStruct], 1Ch
0x180018f80  mov     qword ptr [rbp+57h+pcolumndef.coltyp], 0Ch
0x180018f88  mov     dword ptr [rbp+57h+pcolumndef.cp], 4B0h
0x180018f8f  mov     [rbp+57h+pcolumndef.cbMax], r15d
0x180018f93  mov     [rbp+57h+pcolumndef.grbit], 4
0x180018f9a  call    cs:__imp_JetAddColumnW
0x180018fa0  mov     ecx, eax; int
0x180018fa2  mov     r14d, eax
0x180018fa5  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018faa  test    eax, eax
0x180018fac  jz      short loc_180018FC9
0x180018fae  mov     ecx, r14d; int
0x180018fb1  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018fb6  mov     ecx, eax; dwErrCode
0x180018fb8  call    cs:__imp_SetLastError
0x180018fbe  mov     r8d, 1926h
0x180018fc4  jmp     loc_1800190B8
0x180018fc9  mov     rdx, [rdi]; tableid
0x180018fcc  lea     rax, [rbx+50h]
0x180018fd0  mov     rcx, [rbx+8]; sesid
0x180018fd4  lea     r9, [rbp+57h+pcolumndef]; pcolumndef
0x180018fd8  mov     [rsp+100h+pcolumnid], rax; pcolumnid
0x180018fdd  lea     r8, aCatnameattrtab_0; "CatNameAttrTable_AttrCol"
0x180018fe4  mov     dword ptr [rsp+100h+ptableid], r12d; int
0x180018fe9  mov     qword ptr [rsp+100h+lDensity], r12; pvDefault
0x180018fee  mov     qword ptr [rbp+57h+pcolumndef.cbStruct], 1Ch
0x180018ff6  mov     qword ptr [rbp+57h+pcolumndef.wCountry], r12
0x180018ffa  mov     [rbp+57h+pcolumndef.coltyp], 9
0x180019001  mov     [rbp+57h+pcolumndef.cbMax], 40h ; '@'
0x180019008  mov     [rbp+57h+pcolumndef.grbit], 5
0x18001900f  call    cs:__imp_JetAddColumnW
0x180019015  mov     ecx, eax; int
0x180019017  mov     r14d, eax
0x18001901a  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001901f  test    eax, eax
0x180019021  jz      short loc_18001903B
0x180019023  mov     ecx, r14d; int
0x180019026  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001902b  mov     ecx, eax; dwErrCode
0x18001902d  call    cs:__imp_SetLastError
0x180019033  mov     r8d, 193Ah
0x180019039  jmp     short loc_1800190B8
0x18001903b  mov     r14d, 58h ; 'X'
0x180019041  lea     rcx, [rbp+57h+pindexcreate]; void *
  ... truncated ...
```
