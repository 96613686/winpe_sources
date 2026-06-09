# CSRSForeignKeys::FInit(CDBSession *,ulong,tagVARIANT const * const,CRowsetProperties const &)

- ea: `0x1003eda0`
- end: `0x1003f723`
- name: `?FInit@CSRSForeignKeys@@QAGJPAVCDBSession@@KQBUtagVARIANT@@ABVCRowsetProperties@@@Z`
- size: `2435`
- prototype: `int(CSRSForeignKeys *__hidden this, struct CDBSession *, unsigned int, const struct tagVARIANT *const, const struct CRowsetProperties *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10034e00`

## callees

- `0x1000d570`
- `0x10013100`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10028340`
- `0x10035e60`
- `0x1003eda0`
- `0x1003f730`
- `0x1004ce5d`
- `0x1004d420`
- `0x1004d5a1`
- `0x1004dc8d`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1003f115`
- `msvcrt!_wcsicmp` at `0x1003f13c`
- `msvcrt!_wcsicmp` at `0x1003f115`
- `msvcrt!_wcsicmp` at `0x1003f13c`
- `msjet40!__imp__JetCloseTable@8` at `0x1003f5ab`
- `msjet40!__imp__JetCloseTable@8` at `0x1003f6de`
- `msjet40!__imp__JetCloseTable@8` at `0x1003f5ab`
- `msjet40!__imp__JetCloseTable@8` at `0x1003f6de`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003f6bc`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003f6bc`
- `msjet40!__imp__JetMove@16` at `0x1003f57a`
- `msjet40!__imp__JetMove@16` at `0x1003f57a`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003f156`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003f156`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f079`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f0cd`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f220`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f2a0`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f320`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f39d`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f410`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f079`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f0cd`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f220`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f2a0`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f320`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f39d`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003f410`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f1a1`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f1e8`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f268`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f2e8`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f368`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f3db`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f477`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f4d2`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f548`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f1a1`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f1e8`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f268`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f2e8`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f368`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f3db`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f477`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f4d2`
- `msjet40!__imp__JetSetColumn@28` at `0x1003f548`
- `msjet40!__imp__JetUpdate@20` at `0x1003f55b`
- `msjet40!__imp__JetUpdate@20` at `0x1003f55b`
- `msjet40!__imp__JetGetRelationshipInfo@24` at `0x1003f02b`
- `msjet40!__imp__JetGetRelationshipInfo@24` at `0x1003f02b`

## pseudocode

```c
int __userpurge CSRSForeignKeys::FInit@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        CSRSForeignKeys *this,
        struct CDBSession *a4,
        unsigned int a5,
        const struct tagVARIANT *const a6,
        const struct CRowsetProperties *a7)
{
  JET_SESID v7; // edi
  CSRSForeignKeys *v8; // eax
  bool v9; // bl
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  wchar_t *v17; // edx
  int v18; // eax
  wchar_t *v19; // eax
  JET_COLUMNID *v20; // eax
  int v21; // ebx
  int v22; // eax
  bool v23; // zf
  JET_COLUMNID *v24; // ebx
  __int128 *v25; // edx
  __int128 *v26; // edx
  unsigned __int16 *v27; // ecx
  JET_ERR v28; // eax
  wchar_t *v29; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v30; // esi
  _DWORD *v31; // ebx
  int v32; // ecx
  unsigned int v34; // [esp-Ch] [ebp-3ECh]
  unsigned int v35; // [esp-Ch] [ebp-3ECh]
  unsigned int v36; // [esp-Ch] [ebp-3ECh]
  unsigned __int16 *v37; // [esp+0h] [ebp-3E0h]
  const struct _GUID *v38; // [esp+4h] [ebp-3DCh]
  int v39; // [esp+10h] [ebp-3D0h] BYREF
  int v40; // [esp+14h] [ebp-3CCh] BYREF
  int v41; // [esp+18h] [ebp-3C8h] BYREF
  wchar_t *String2; // [esp+1Ch] [ebp-3C4h]
  wchar_t *v43; // [esp+20h] [ebp-3C0h]
  JET_COLUMNID *v44; // [esp+24h] [ebp-3BCh]
  CSRSForeignKeys *v45; // [esp+28h] [ebp-3B8h]
  int v46; // [esp+2Ch] [ebp-3B4h] BYREF
  unsigned int pcbActual; // [esp+30h] [ebp-3B0h] BYREF
  char v48; // [esp+36h] [ebp-3AAh]
  char v49; // [esp+37h] [ebp-3A9h]
  JET_TABLEID v50; // [esp+38h] [ebp-3A8h] BYREF
  unsigned int RelationshipInfo; // [esp+3Ch] [ebp-3A4h] BYREF
  int PKName; // [esp+40h] [ebp-3A0h]
  _DWORD *v53; // [esp+44h] [ebp-39Ch]
  unsigned int v54[11]; // [esp+48h] [ebp-398h] BYREF
  unsigned __int16 v55[66]; // [esp+74h] [ebp-36Ch] BYREF
  _WORD v56[66]; // [esp+F8h] [ebp-2E8h] BYREF
  _WORD v57[66]; // [esp+17Ch] [ebp-264h] BYREF
  wchar_t v58[66]; // [esp+200h] [ebp-1E0h] BYREF
  wchar_t String1[66]; // [esp+284h] [ebp-15Ch] BYREF
  unsigned __int16 pvData[66]; // [esp+308h] [ebp-D8h] BYREF
  __int128 v61; // [esp+38Ch] [ebp-54h] BYREF
  __int64 v62; // [esp+39Ch] [ebp-44h]
  __int128 v63; // [esp+3A4h] [ebp-3Ch] BYREF
  __int128 v64; // [esp+3B4h] [ebp-2Ch] BYREF
  int v65; // [esp+3C4h] [ebp-1Ch]
  __int128 v66; // [esp+3C8h] [ebp-18h] BYREF
  wchar_t v67; // [esp+3D8h] [ebp-8h]

  v53 = a1;
  v40 = a2;
  v63 = *(_OWORD *)L"CASCADE";
  v66 = *(_OWORD *)L"SET NULL";
  v67 = aSetNull[8];
  v7 = a1[4];
  v61 = *(_OWORD *)L"SET DEFAULT";
  v65 = *(_DWORD *)L"N";
  v8 = (CSRSForeignKeys *)a1[5];
  v62 = *(_QWORD *)L"ULT";
  v45 = v8;
  v64 = *(_OWORD *)L"NO ACTION";
  RelationshipInfo = 0;
  v44 = 0;
  memset(v54, 0, sizeof(v54));
  String2 = 0;
  v9 = 1;
  v43 = 0;
  v49 = 0;
  v48 = 0;
  if ( !this )
    goto LABEL_40;
  if ( !a4 )
    goto LABEL_42;
  if ( (unsigned int)this > 6 )
    goto LABEL_42;
  v10 = *(unsigned __int16 *)a4;
  if ( (_WORD)v10 )
  {
    if ( v10 != 1 && (v10 != 8 || *((_DWORD *)a4 + 2)) )
      goto LABEL_42;
  }
  if ( (unsigned int)this > 1 )
  {
    v11 = *((unsigned __int16 *)a4 + 8);
    if ( (_WORD)v11 )
    {
      if ( v11 != 1 && (v11 != 8 || *((_DWORD *)a4 + 6)) )
        goto LABEL_42;
    }
  }
  if ( (unsigned int)this > 2 )
  {
    v12 = *((unsigned __int16 *)a4 + 16);
    if ( (_WORD)v12 )
    {
      if ( v12 != 1 && v12 != 8 )
        goto LABEL_42;
    }
  }
  if ( (unsigned int)this > 3 )
  {
    v13 = *((unsigned __int16 *)a4 + 24);
    if ( (_WORD)v13 )
    {
      if ( v13 != 1 && (v13 != 8 || *((_DWORD *)a4 + 14)) )
        goto LABEL_42;
    }
  }
  if ( (unsigned int)this > 4 )
  {
    v14 = *((unsigned __int16 *)a4 + 32);
    if ( (_WORD)v14 )
    {
      if ( v14 != 1 && (v14 != 8 || *((_DWORD *)a4 + 18)) )
        goto LABEL_42;
    }
  }
  if ( (unsigned int)this > 5 )
  {
    v15 = *((unsigned __int16 *)a4 + 40);
    if ( !(_WORD)v15 || v15 == 1 )
    {
LABEL_32:
      v16 = *((unsigned __int16 *)a4 + 16);
      if ( (_WORD)v16 && v16 != 1 )
      {
        v17 = (wchar_t *)*((_DWORD *)a4 + 10);
        v49 = 1;
        String2 = v17;
        v9 = v17 != 0;
      }
      goto LABEL_35;
    }
    if ( v15 != 8 )
    {
LABEL_42:
      v21 = -2147024809;
      goto LABEL_104;
    }
  }
  if ( (unsigned int)this > 2 )
    goto LABEL_32;
LABEL_35:
  if ( (unsigned int)this > 5 )
  {
    v18 = *((unsigned __int16 *)a4 + 40);
    if ( (_WORD)v18 )
    {
      if ( v18 != 1 )
      {
        v19 = (wchar_t *)*((_DWORD *)a4 + 22);
        v48 = 1;
        v43 = v19;
        if ( !v19 )
          v9 = 0;
      }
    }
  }
LABEL_40:
  v20 = (JET_COLUMNID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          72);
  v44 = v20;
  if ( !v20 )
  {
    v21 = -2147024882;
    goto LABEL_98;
  }
  v22 = SRSCreateTempTable(18, v53, &v50, v20, 0);
  PKName = v22;
  if ( v22 < 0 )
  {
    v21 = v22;
  }
  else
  {
    v54[1] = 0;
    RelationshipInfo = JetGetRelationshipInfo(v7, v45, 0, 0, v54, 44);
    if ( (RelationshipInfo & 0x80000000) != 0 )
    {
      v21 = PKName;
    }
    else
    {
      if ( v54[2] && v9 )
      {
        while ( 1 )
        {
          RelationshipInfo = JetRetrieveColumn(v7, v54[1], v54[9], pvData, 0x80u, &pcbActual, 0, 0);
          if ( (RelationshipInfo & 0x80000000) != 0 )
            break;
          if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
            goto LABEL_112;
          *(unsigned __int16 *)((char *)pvData + (pcbActual & 0xFFFFFFFE)) = 0;
          RelationshipInfo = JetRetrieveColumn(v7, v54[1], v54[7], String1, 0x80u, &pcbActual, 0, 0);
          if ( (RelationshipInfo & 0x80000000) != 0 )
            break;
          if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
            goto LABEL_112;
          v23 = v49 == 1;
          *(wchar_t *)((char *)String1 + (pcbActual & 0xFFFFFFFE)) = 0;
          if ( (!v23 || !__wcsicmp(pvData, String2)) && (v48 != 1 || !__wcsicmp(String1, v43)) )
          {
            RelationshipInfo = JetPrepareUpdate(v7, v50, 0);
            if ( (RelationshipInfo & 0x80000000) != 0 )
              break;
            v24 = v44;
            RelationshipInfo = JetSetColumn(v7, v50, v44[2], pvData, 2 * wcslen(pvData), 0, 0);
            if ( (RelationshipInfo & 0x80000000) != 0 )
              break;
            RelationshipInfo = JetSetColumn(v7, v50, v24[8], String1, 2 * wcslen(String1), 0, 0);
            if ( (RelationshipInfo & 0x80000000) != 0 )
              break;
            RelationshipInfo = JetRetrieveColumn(v7, v54[1], v54[10], v58, 0x80u, &pcbActual, 0, 0);
            if ( (RelationshipInfo & 0x80000000) != 0 )
              break;
            if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
              goto LABEL_112;
            v34 = pcbActual;
            *(wchar_t *)((char *)v58 + (pcbActual & 0xFFFFFFFE)) = 0;
            RelationshipInfo = JetSetColumn(v7, v50, v24[3], v58, v34, 0, 0);
            if ( (RelationshipInfo & 0x80000000) != 0 )
              break;
            RelationshipInfo = JetRetrieveColumn(v7, v54[1], v54[3], v57, 0x80u, &pcbActual, 0, 0);
            if ( (RelationshipInfo & 0x80000000) != 0 )
              break;
            if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
              goto LABEL_112;
            v35 = pcbActual;
            *(_WORD *)((char *)v57 + (pcbActual & 0xFFFFFFFE)) = 0;
            RelationshipInfo = JetSetColumn(v7, v50, v24[16], v57, v35, 0, 0);
            if ( (RelationshipInfo & 0x80000000) != 0 )
              break;
            RelationshipInfo = JetRetrieveColumn(v7, v54[1], v54[8], v56, 0x80u, &pcbActual, 0, 0);
            if ( (RelationshipInfo & 0x80000000) != 0 )
              break;
            if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
LABEL_112:
              __report_rangecheckfailure();
            v36 = pcbActual;
            *(_WORD *)((char *)v56 + (pcbActual & 0xFFFFFFFE)) = 0;
            RelationshipInfo = JetSetColumn(v7, v50, v24[9], v56, v36, 0, 0);
            if ( (RelationshipInfo & 0x80000000) != 0 )
              break;
            RelationshipInfo = JetRetrieveColumn(v7, v54[1], v54[6], &v46, 4u, &pcbActual, 0, 0);
            if ( (RelationshipInfo & 0x80000000) != 0 )
              break;
            v39 = ++v46;
            RelationshipInfo = JetSetColumn(v7, v50, v24[12], &v39, 4u, 0, 0);
            if ( (RelationshipInfo & 0x80000000) != 0 )
              break;
            RelationshipInfo = JetRetrieveColumn(v7, v54[1], v54[4], &v41, 4u, &pcbActual, 0, 0);
            if ( (RelationshipInfo & 0x80000000) != 0 )
              break;
            if ( (v41 & 0x100) != 0 )
            {
              v25 = &v63;
            }
            else if ( (v41 & 0x200) != 0 )
            {
              v25 = &v66;
            }
            else
            {
              v25 = &v61;
              if ( (v41 & 0x300) == 0 )
                v25 = &v64;
            }
            JetSetColumn(v7, v50, v24[13], v25, 2 * wcslen((const unsigned __int16 *)v25), 0, 0);
            if ( (v41 & 0x1000) != 0 )
            {
              v26 = &v63;
            }
            else if ( (v41 & 0x2000) != 0 )
            {
              v26 = &v66;
            }
            else
            {
              v26 = &v61;
              if ( (v41 & 0x3000) == 0 )
                v26 = &v64;
            }
            JetSetColumn(v7, v50, v24[14], v26, 2 * wcslen((const unsigned __int16 *)v26), 0, 0);
            if ( v46 == 1 )
            {
              PKName = CSRSForeignKeys::GetPKName(
                         v7,
                         v45,
                         v54,
                         (unsigned int)pvData,
                         (struct JET_RELATIONSHIPLIST *)v55,
                         v27,
                         v37,
                         (unsigned int)v38);
              if ( PKName < 0 )
                break;
            }
            JetSetColumn(v7, v50, v24[15], v55, 2 * wcslen(v55), 0, 0);
            RelationshipInfo = JetUpdate(v7, v50, 0, 0, 0);
            if ( (RelationshipInfo & 0x80000000) != 0 )
              break;
          }
          v28 = JetMove(v7, v54[1], 1, 0);
          RelationshipInfo = v28;
          if ( v28 < 0 )
          {
            if ( v28 == -1603 )
              RelationshipInfo = 0;
            goto LABEL_88;
          }
        }
      }
      else
      {
LABEL_88:
        if ( v54[1] )
          JetCloseTable(v7, v54[1]);
        v29 = (wchar_t *)operator new(0x20u);
        v43 = v29;
        if ( !v29
          || (v30 = ColumnDataWithFakeNamesAndDBTYPES::ColumnDataWithFakeNamesAndDBTYPES((ColumnDataWithFakeNamesAndDBTYPES *)v29)) == 0 )
        {
          v21 = -2147024882;
          goto LABEL_98;
        }
        v31 = v53;
        *((_DWORD *)v30 + 4) = dword_10007E44;
        *((_DWORD *)v30 + 5) = &SRSForeignKeysNames;
        *((_DWORD *)v30 + 7) = 0;
        PKName = ColumnData::FInit(v30, v7, v31[5], v50, (int *)&RelationshipInfo, 0, (int)&SRSForeignKeysNames);
        if ( PKName >= 0 )
        {
          v32 = v40;
          *((_DWORD *)v30 + 1) = 18;
          v21 = CRowset::FInit(v32, 0, v31, 0, 0, 0, v50, a5, 1, 0, 0, v30, 1, 0, 0, &GUID_NULL);
          goto LABEL_98;
        }
      }
      v21 = PKName;
    }
  }
LABEL_98:
  if ( (RelationshipInfo & 0x80000000) != 0 )
    v21 = -2147467259;
  if ( RelationshipInfo )
  {
    CExtError::SendJetErrortoOLEAuto(RelationshipInfo, (int)&IID_IDBSchemaRowset, (int)v37, v38);
    goto LABEL_106;
  }
  if ( v21 >= 0 )
    goto LABEL_108;
  if ( v21 == -2147024882 )
  {
LABEL_107:
    JetCloseTable(v7, v54[1]);
    goto LABEL_108;
  }
LABEL_104:
  if ( JetGetDatabaseInfo(v7, v45, &v40, 4, 3) )
    goto LABEL_107;
  CExtError::SendHRtoOLEAuto((int)&IID_IDBSchemaRowset, 0, (const struct _GUID *)v37, (int)v38);
LABEL_106:
  if ( v21 < 0 )
    goto LABEL_107;
LABEL_108:
  if ( v44 && Sys )
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNID *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v44);
  return v21;
}

```

## disassembly

```asm
0x1003eda0  mov     edi, edi
0x1003eda2  push    ebp
0x1003eda3  mov     ebp, esp
0x1003eda5  sub     esp, 3D4h
0x1003edab  mov     eax, ___security_cookie
0x1003edb0  xor     eax, ebp
0x1003edb2  mov     [ebp+var_4], eax
0x1003edb5  push    ebx
0x1003edb6  push    esi; int
0x1003edb7  push    edi; struct _GUID *
0x1003edb8  mov     [ebp+var_39C], edx
0x1003edbe  mov     [ebp+var_3CC], ecx
0x1003edc4  movups  xmm0, xmmword ptr ds:aCascade; "CASCADE"
0x1003edcb  mov     eax, [ebp+arg_8]
0x1003edce  movups  [ebp+var_3C], xmm0
0x1003edd2  mov     [ebp+var_3D4], eax
0x1003edd8  movups  xmm0, xmmword ptr ds:aSetNull; "SET NULL"
0x1003eddf  mov     ax, word ptr ds:aSetNull+10h; ""
0x1003ede5  mov     esi, [ebp+arg_4]
0x1003ede8  movups  [ebp+var_18], xmm0
0x1003edec  mov     [ebp+var_8], ax
0x1003edf0  movups  xmm0, xmmword ptr ds:aSetDefault; "SET DEFAULT"
0x1003edf7  mov     eax, dword ptr ds:aNoAction+10h; "N"
0x1003edfc  mov     edi, [edx+10h]
0x1003edff  movups  [ebp+var_54], xmm0
0x1003ee03  mov     [ebp+var_1C], eax
0x1003ee06  movq    xmm0, qword ptr ds:aSetDefault+10h; "ULT"
0x1003ee0e  mov     eax, [edx+14h]
0x1003ee11  movq    [ebp+var_44], xmm0
0x1003ee16  movups  xmm0, xmmword ptr ds:aNoAction; "NO ACTION"
0x1003ee1d  push    2Ch ; ','; Size
0x1003ee1f  mov     [ebp+var_3B8], eax
0x1003ee25  lea     eax, [ebp+var_398]
0x1003ee2b  push    0; Val
0x1003ee2d  push    eax; void *
0x1003ee2e  movups  [ebp+var_2C], xmm0
0x1003ee32  mov     [ebp+var_3A4], 0
0x1003ee3c  mov     [ebp+var_3BC], 0
0x1003ee46  call    _memset
0x1003ee4b  mov     eax, [ebp+this]
0x1003ee4e  add     esp, 0Ch
0x1003ee51  mov     [ebp+String2], 0
0x1003ee5b  mov     bl, 1
0x1003ee5d  mov     [ebp+var_3C0], 0
0x1003ee67  mov     [ebp+var_3A9], 0
0x1003ee6e  mov     [ebp+var_3AA], 0
0x1003ee75  test    eax, eax
0x1003ee77  jz      loc_1003EFAD
0x1003ee7d  test    esi, esi
0x1003ee7f  jz      loc_1003EFDF
0x1003ee85  cmp     eax, 6
0x1003ee88  ja      loc_1003EFDF
0x1003ee8e  movzx   ecx, word ptr [esi]
0x1003ee91  test    cx, cx
0x1003ee94  jz      short loc_1003EEAE
0x1003ee96  cmp     ecx, 1
0x1003ee99  jz      short loc_1003EEAE
0x1003ee9b  cmp     ecx, 8
0x1003ee9e  jnz     loc_1003EFDF
0x1003eea4  cmp     dword ptr [esi+8], 0
0x1003eea8  jnz     loc_1003EFDF
0x1003eeae  cmp     eax, 1
0x1003eeb1  jbe     short loc_1003EED4
0x1003eeb3  movzx   ecx, word ptr [esi+10h]
0x1003eeb7  test    cx, cx
0x1003eeba  jz      short loc_1003EED4
0x1003eebc  cmp     ecx, 1
0x1003eebf  jz      short loc_1003EED4
0x1003eec1  cmp     ecx, 8
0x1003eec4  jnz     loc_1003EFDF
0x1003eeca  cmp     dword ptr [esi+18h], 0
0x1003eece  jnz     loc_1003EFDF
0x1003eed4  cmp     eax, 2
0x1003eed7  jbe     short loc_1003EEF0
0x1003eed9  movzx   ecx, word ptr [esi+20h]
0x1003eedd  test    cx, cx
0x1003eee0  jz      short loc_1003EEF0
0x1003eee2  cmp     ecx, 1
0x1003eee5  jz      short loc_1003EEF0
0x1003eee7  cmp     ecx, 8
0x1003eeea  jnz     loc_1003EFDF
0x1003eef0  cmp     eax, 3
0x1003eef3  jbe     short loc_1003EF16
0x1003eef5  movzx   ecx, word ptr [esi+30h]
0x1003eef9  test    cx, cx
0x1003eefc  jz      short loc_1003EF16
0x1003eefe  cmp     ecx, 1
0x1003ef01  jz      short loc_1003EF16
0x1003ef03  cmp     ecx, 8
0x1003ef06  jnz     loc_1003EFDF
0x1003ef0c  cmp     dword ptr [esi+38h], 0
0x1003ef10  jnz     loc_1003EFDF
0x1003ef16  cmp     eax, 4
0x1003ef19  jbe     short loc_1003EF3C
0x1003ef1b  movzx   ecx, word ptr [esi+40h]
0x1003ef1f  test    cx, cx
0x1003ef22  jz      short loc_1003EF3C
0x1003ef24  cmp     ecx, 1
0x1003ef27  jz      short loc_1003EF3C
0x1003ef29  cmp     ecx, 8
0x1003ef2c  jnz     loc_1003EFDF
0x1003ef32  cmp     dword ptr [esi+48h], 0
0x1003ef36  jnz     loc_1003EFDF
0x1003ef3c  cmp     eax, 5
0x1003ef3f  jbe     short loc_1003EF58
0x1003ef41  movzx   ecx, word ptr [esi+50h]
0x1003ef45  test    cx, cx
0x1003ef48  jz      short loc_1003EF5D
0x1003ef4a  cmp     ecx, 1
0x1003ef4d  jz      short loc_1003EF5D
0x1003ef4f  cmp     ecx, 8
0x1003ef52  jnz     loc_1003EFDF
0x1003ef58  cmp     eax, 2
0x1003ef5b  jbe     short loc_1003EF84
0x1003ef5d  movzx   ecx, word ptr [esi+20h]
0x1003ef61  test    cx, cx
0x1003ef64  jz      short loc_1003EF84
0x1003ef66  cmp     ecx, 1
0x1003ef69  jz      short loc_1003EF84
0x1003ef6b  mov     edx, [esi+28h]
0x1003ef6e  xor     ecx, ecx
0x1003ef70  mov     [ebp+var_3A9], bl
0x1003ef76  test    edx, edx
0x1003ef78  movzx   ebx, bl
0x1003ef7b  mov     [ebp+String2], edx
0x1003ef81  cmovz   ebx, ecx
0x1003ef84  cmp     eax, 5
0x1003ef87  jbe     short loc_1003EFAD
0x1003ef89  movzx   eax, word ptr [esi+50h]
0x1003ef8d  test    ax, ax
0x1003ef90  jz      short loc_1003EFAD
0x1003ef92  cmp     eax, 1
0x1003ef95  jz      short loc_1003EFAD
0x1003ef97  mov     eax, [esi+58h]
0x1003ef9a  mov     [ebp+var_3AA], 1
0x1003efa1  mov     [ebp+var_3C0], eax
0x1003efa7  test    eax, eax
0x1003efa9  jnz     short loc_1003EFAD
0x1003efab  xor     bl, bl
0x1003efad  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1003efb3  push    48h ; 'H'
0x1003efb5  push    ecx
0x1003efb6  mov     eax, [ecx]
0x1003efb8  mov     esi, [eax+0Ch]
0x1003efbb  mov     ecx, esi
0x1003efbd  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1003efc3  call    esi
0x1003efc5  mov     esi, [ebp+var_39C]
0x1003efcb  mov     [ebp+var_3BC], eax
0x1003efd1  test    eax, eax
0x1003efd3  jnz     short loc_1003EFE9
0x1003efd5  mov     ebx, 8007000Eh
0x1003efda  jmp     loc_1003F67A
0x1003efdf  mov     ebx, 80070057h
0x1003efe4  jmp     loc_1003F6AA
0x1003efe9  push    0
0x1003efeb  push    eax
0x1003efec  lea     eax, [ebp+var_3A8]
0x1003eff2  mov     edx, esi
0x1003eff4  push    eax
0x1003eff5  mov     ecx, 12h
0x1003effa  call    SRSCreateTempTable
0x1003efff  mov     [ebp+var_3A0], eax
0x1003f005  test    eax, eax
0x1003f007  js      loc_1003F66A
0x1003f00d  push    2Ch ; ','
0x1003f00f  lea     eax, [ebp+var_398]
0x1003f015  mov     [ebp+tableid], 0
0x1003f01f  push    eax
0x1003f020  push    0
0x1003f022  push    0
0x1003f024  push    [ebp+var_3B8]
0x1003f02a  push    edi
0x1003f02b  call    ds:__imp__JetGetRelationshipInfo@24; JetGetRelationshipInfo(x,x,x,x,x,x)
0x1003f031  mov     [ebp+var_3A4], eax
0x1003f037  test    eax, eax
0x1003f039  js      loc_1003F662
0x1003f03f  cmp     [ebp+var_390], 0
0x1003f046  jbe     loc_1003F59F
0x1003f04c  cmp     bl, 1
0x1003f04f  jnz     loc_1003F59F
0x1003f055  push    0; pretinfo
0x1003f057  push    0; grbit
0x1003f059  lea     eax, [ebp+pcbActual]
0x1003f05f  push    eax; pcbActual
0x1003f060  push    80h; cbData
0x1003f065  lea     eax, [ebp+pvData]
0x1003f06b  push    eax; pvData
0x1003f06c  push    [ebp+columnid]; columnid
0x1003f072  push    [ebp+tableid]; tableid
0x1003f078  push    edi; sesid
0x1003f079  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003f07f  mov     [ebp+var_3A4], eax
0x1003f085  test    eax, eax
0x1003f087  js      loc_1003F66E
0x1003f08d  mov     eax, [ebp+pcbActual]
0x1003f093  and     eax, 0FFFFFFFEh
0x1003f096  cmp     eax, 82h
0x1003f09b  jnb     loc_1003F71E
0x1003f0a1  xor     ecx, ecx
0x1003f0a3  push    ecx; pretinfo
0x1003f0a4  push    ecx; grbit
0x1003f0a5  mov     [ebp+eax+pvData], cx
0x1003f0ad  lea     eax, [ebp+pcbActual]
0x1003f0b3  push    eax; pcbActual
0x1003f0b4  push    80h; cbData
0x1003f0b9  lea     eax, [ebp+String1]
0x1003f0bf  push    eax; pvData
0x1003f0c0  push    [ebp+var_37C]; columnid
0x1003f0c6  push    [ebp+tableid]; tableid
0x1003f0cc  push    edi; sesid
0x1003f0cd  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003f0d3  mov     [ebp+var_3A4], eax
0x1003f0d9  test    eax, eax
0x1003f0db  js      loc_1003F66E
0x1003f0e1  mov     eax, [ebp+pcbActual]
0x1003f0e7  and     eax, 0FFFFFFFEh
0x1003f0ea  cmp     eax, 82h
0x1003f0ef  jnb     loc_1003F71E
0x1003f0f5  xor     ecx, ecx
0x1003f0f7  cmp     [ebp+var_3A9], 1
0x1003f0fe  mov     [ebp+eax+String1], cx
0x1003f106  jnz     short loc_1003F126
0x1003f108  push    [ebp+String2]; String2
0x1003f10e  lea     eax, [ebp+pvData]
0x1003f114  push    eax; String1
0x1003f115  call    ds:__imp___wcsicmp
0x1003f11b  add     esp, 8
0x1003f11e  test    eax, eax
0x1003f120  jnz     loc_1003F56F
0x1003f126  cmp     [ebp+var_3AA], 1
0x1003f12d  jnz     short loc_1003F14D
0x1003f12f  push    [ebp+var_3C0]; String2
0x1003f135  lea     eax, [ebp+String1]
0x1003f13b  push    eax; String1
0x1003f13c  call    ds:__imp___wcsicmp
0x1003f142  add     esp, 8
0x1003f145  test    eax, eax
0x1003f147  jnz     loc_1003F56F
0x1003f14d  push    0; prep
0x1003f14f  push    [ebp+var_3A8]; tableid
0x1003f155  push    edi; sesid
0x1003f156  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x1003f15c  mov     [ebp+var_3A4], eax
0x1003f162  test    eax, eax
0x1003f164  js      loc_1003F66E
0x1003f16a  lea     ecx, [ebp+pvData]
0x1003f170  lea     edx, [ecx+2]
0x1003f173  mov     ax, [ecx]
0x1003f176  add     ecx, 2
0x1003f179  test    ax, ax
0x1003f17c  jnz     short loc_1003F173
0x1003f17e  mov     ebx, [ebp+var_3BC]
0x1003f184  sub     ecx, edx
0x1003f186  push    0; psetinfo
0x1003f188  sar     ecx, 1
0x1003f18a  push    0; grbit
0x1003f18c  lea     eax, [ecx+ecx]
0x1003f18f  push    eax; cbData
0x1003f190  lea     eax, [ebp+pvData]
0x1003f196  push    eax; pvData
0x1003f197  push    dword ptr [ebx+8]; columnid
0x1003f19a  push    [ebp+var_3A8]; tableid
0x1003f1a0  push    edi; sesid
0x1003f1a1  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1003f1a7  mov     [ebp+var_3A4], eax
0x1003f1ad  test    eax, eax
0x1003f1af  js      loc_1003F66E
0x1003f1b5  lea     ecx, [ebp+String1]
0x1003f1bb  lea     edx, [ecx+2]
0x1003f1be  mov     edi, edi
0x1003f1c0  mov     ax, [ecx]
0x1003f1c3  add     ecx, 2
0x1003f1c6  test    ax, ax
0x1003f1c9  jnz     short loc_1003F1C0
0x1003f1cb  sub     ecx, edx
0x1003f1cd  push    0; psetinfo
0x1003f1cf  sar     ecx, 1
0x1003f1d1  push    0; grbit
0x1003f1d3  lea     eax, [ecx+ecx]
0x1003f1d6  push    eax; cbData
0x1003f1d7  lea     eax, [ebp+String1]
0x1003f1dd  push    eax; pvData
0x1003f1de  push    dword ptr [ebx+20h]; columnid
0x1003f1e1  push    [ebp+var_3A8]; tableid
0x1003f1e7  push    edi; sesid
0x1003f1e8  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1003f1ee  mov     [ebp+var_3A4], eax
0x1003f1f4  test    eax, eax
0x1003f1f6  js      loc_1003F66E
0x1003f1fc  push    0; pretinfo
0x1003f1fe  push    0; grbit
0x1003f200  lea     eax, [ebp+pcbActual]
0x1003f206  push    eax; pcbActual
0x1003f207  push    80h; cbData
0x1003f20c  lea     eax, [ebp+var_1E0]
0x1003f212  push    eax; pvData
0x1003f213  push    [ebp+var_370]; columnid
0x1003f219  push    [ebp+tableid]; tableid
0x1003f21f  push    edi; sesid
  ... truncated ...
```
