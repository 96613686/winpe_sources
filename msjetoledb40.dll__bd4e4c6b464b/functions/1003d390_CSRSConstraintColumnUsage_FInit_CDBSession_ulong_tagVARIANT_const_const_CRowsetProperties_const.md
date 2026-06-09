# CSRSConstraintColumnUsage::FInit(CDBSession *,ulong,tagVARIANT const * const,CRowsetProperties const &)

- ea: `0x1003d390`
- end: `0x1003e17d`
- name: `?FInit@CSRSConstraintColumnUsage@@QAGJPAVCDBSession@@KQBUtagVARIANT@@ABVCRowsetProperties@@@Z`
- size: `3565`
- prototype: `int __userpurge@<eax>(_DWORD *@<edx>, int@<ecx>, CSRSConstraintColumnUsage *this, struct CDBSession *, unsigned int, const struct tagVARIANT *const, const struct CRowsetProperties *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10034e00`

## callees

- `0x10013020`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10028340`
- `0x10035e60`
- `0x1003d390`
- `0x1004ce5d`
- `0x1004d420`
- `0x1004d5a1`
- `0x1004dc8d`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1003d74a`
- `msvcrt!_wcsicmp` at `0x1003d8a9`
- `msvcrt!_wcsicmp` at `0x1003db43`
- `msvcrt!_wcsicmp` at `0x1003de33`
- `msvcrt!_wcsicmp` at `0x1003de54`
- `msvcrt!_wcsicmp` at `0x1003d74a`
- `msvcrt!_wcsicmp` at `0x1003d8a9`
- `msvcrt!_wcsicmp` at `0x1003db43`
- `msvcrt!_wcsicmp` at `0x1003de33`
- `msvcrt!_wcsicmp` at `0x1003de54`
- `msjet40!__imp__JetCloseTable@8` at `0x1003dc74`
- `msjet40!__imp__JetCloseTable@8` at `0x1003df42`
- `msjet40!__imp__JetCloseTable@8` at `0x1003e052`
- `msjet40!__imp__JetCloseTable@8` at `0x1003e0a4`
- `msjet40!__imp__JetCloseTable@8` at `0x1003e136`
- `msjet40!__imp__JetCloseTable@8` at `0x1003dc74`
- `msjet40!__imp__JetCloseTable@8` at `0x1003df42`
- `msjet40!__imp__JetCloseTable@8` at `0x1003e052`
- `msjet40!__imp__JetCloseTable@8` at `0x1003e0a4`
- `msjet40!__imp__JetCloseTable@8` at `0x1003e136`
- `msjet40!__imp__JetCreateIndex@28` at `0x1003d5ea`
- `msjet40!__imp__JetCreateIndex@28` at `0x1003d5ea`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003e10f`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003e10f`
- `msjet40!__imp__JetGetIndexInfo@28` at `0x1003da45`
- `msjet40!__imp__JetGetIndexInfo@28` at `0x1003da45`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x1003d641`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x1003d641`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x1003dfe1`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x1003dfe1`
- `msjet40!__imp__JetMove@16` at `0x1003d665`
- `msjet40!__imp__JetMove@16` at `0x1003d760`
- `msjet40!__imp__JetMove@16` at `0x1003d7c0`
- `msjet40!__imp__JetMove@16` at `0x1003dc4c`
- `msjet40!__imp__JetMove@16` at `0x1003dc87`
- `msjet40!__imp__JetMove@16` at `0x1003df16`
- `msjet40!__imp__JetMove@16` at `0x1003d665`
- `msjet40!__imp__JetMove@16` at `0x1003d760`
- `msjet40!__imp__JetMove@16` at `0x1003d7c0`
- `msjet40!__imp__JetMove@16` at `0x1003dc4c`
- `msjet40!__imp__JetMove@16` at `0x1003dc87`
- `msjet40!__imp__JetMove@16` at `0x1003df16`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003d93a`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003db5b`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003de7f`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003d93a`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003db5b`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003de7f`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003d70a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003d792`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003dab5`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003daf9`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003dbef`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003dd69`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003ddba`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003ddff`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003d70a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003d792`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003dab5`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003daf9`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003dbef`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003dd69`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003ddba`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003ddff`
- `msjet40!__imp__JetSetColumn@28` at `0x1003d981`
- `msjet40!__imp__JetSetColumn@28` at `0x1003d9b7`
- `msjet40!__imp__JetSetColumn@28` at `0x1003d9ee`
- `msjet40!__imp__JetSetColumn@28` at `0x1003dba2`
- `msjet40!__imp__JetSetColumn@28` at `0x1003dbc4`
- `msjet40!__imp__JetSetColumn@28` at `0x1003dc1d`
- `msjet40!__imp__JetSetColumn@28` at `0x1003deab`
- `msjet40!__imp__JetSetColumn@28` at `0x1003dec9`
- `msjet40!__imp__JetSetColumn@28` at `0x1003dee7`
- `msjet40!__imp__JetSetColumn@28` at `0x1003d981`
- `msjet40!__imp__JetSetColumn@28` at `0x1003d9b7`
- `msjet40!__imp__JetSetColumn@28` at `0x1003d9ee`
- `msjet40!__imp__JetSetColumn@28` at `0x1003dba2`
- `msjet40!__imp__JetSetColumn@28` at `0x1003dbc4`
- `msjet40!__imp__JetSetColumn@28` at `0x1003dc1d`
- `msjet40!__imp__JetSetColumn@28` at `0x1003deab`
- `msjet40!__imp__JetSetColumn@28` at `0x1003dec9`
- `msjet40!__imp__JetSetColumn@28` at `0x1003dee7`
- `msjet40!__imp__JetSetCurrentIndex@12` at `0x1003d60f`
- `msjet40!__imp__JetSetCurrentIndex@12` at `0x1003d60f`
- `msjet40!__imp__JetUpdate@20` at `0x1003d9ff`
- `msjet40!__imp__JetUpdate@20` at `0x1003dc2e`
- `msjet40!__imp__JetUpdate@20` at `0x1003def8`
- `msjet40!__imp__JetUpdate@20` at `0x1003d9ff`
- `msjet40!__imp__JetUpdate@20` at `0x1003dc2e`
- `msjet40!__imp__JetUpdate@20` at `0x1003def8`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1003d8f0`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1003d8f0`
- `msjet40!__imp__JetGetRelationshipInfo@24` at `0x1003dcd7`
- `msjet40!__imp__JetGetRelationshipInfo@24` at `0x1003dcd7`

## pseudocode

```c
int __userpurge CSRSConstraintColumnUsage::FInit@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        CSRSConstraintColumnUsage *this,
        struct CDBSession *a4,
        unsigned int a5,
        const struct tagVARIANT *const a6,
        const struct CRowsetProperties *a7)
{
  JET_SESID v7; // edi
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // eax
  int v13; // esi
  JET_SESID v14; // ecx
  int v15; // ecx
  wchar_t *v16; // edx
  unsigned int v17; // ecx
  int v18; // eax
  wchar_t *v19; // eax
  JET_COLUMNID *v20; // eax
  JET_ERR v21; // eax
  _DWORD *v22; // eax
  _DWORD *v23; // ecx
  _DWORD *v24; // esi
  unsigned int v25; // eax
  _DWORD *v26; // ecx
  const unsigned __int16 *v27; // esi
  int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  JET_COLUMNID *v31; // esi
  signed int IndexInfo; // eax
  _DWORD *v33; // esi
  unsigned int RelationshipInfo; // eax
  BOOL v35; // esi
  BOOL v36; // eax
  JET_COLUMNID *v37; // esi
  wchar_t *v38; // eax
  int v39; // ecx
  signed int TableColumnInfo; // eax
  int v41; // ecx
  unsigned int v43; // [esp-Ch] [ebp-4F4h]
  wchar_t *v44; // [esp+4h] [ebp-4E4h]
  const unsigned __int16 *v45; // [esp+8h] [ebp-4E0h]
  JET_TABLEID v46; // [esp+10h] [ebp-4D8h]
  const struct _GUID *v47; // [esp+18h] [ebp-4D0h]
  const struct _GUID *v48; // [esp+1Ch] [ebp-4CCh]
  int v49; // [esp+2Ch] [ebp-4BCh]
  int v50; // [esp+2Ch] [ebp-4BCh]
  unsigned int Index; // [esp+30h] [ebp-4B8h] BYREF
  JET_TABLEID v52; // [esp+34h] [ebp-4B4h] BYREF
  _DWORD *v53; // [esp+38h] [ebp-4B0h]
  JET_COLUMNID *v54; // [esp+3Ch] [ebp-4ACh]
  _DWORD *v55; // [esp+40h] [ebp-4A8h]
  wchar_t *String1; // [esp+44h] [ebp-4A4h]
  unsigned int v57; // [esp+48h] [ebp-4A0h] BYREF
  unsigned int cbData; // [esp+4Ch] [ebp-49Ch] BYREF
  unsigned int pcbActual; // [esp+50h] [ebp-498h] BYREF
  unsigned int v60; // [esp+54h] [ebp-494h] BYREF
  JET_TABLEID v61; // [esp+58h] [ebp-490h] BYREF
  int v62; // [esp+5Ch] [ebp-48Ch]
  int v63; // [esp+60h] [ebp-488h]
  wchar_t *String2; // [esp+64h] [ebp-484h]
  int v65; // [esp+68h] [ebp-480h]
  int v66; // [esp+6Ch] [ebp-47Ch] BYREF
  int v67; // [esp+70h] [ebp-478h] BYREF
  int v68; // [esp+74h] [ebp-474h] BYREF
  unsigned int v69; // [esp+78h] [ebp-470h]
  JET_TABLEID v70[12]; // [esp+7Ch] [ebp-46Ch] BYREF
  int v71; // [esp+ACh] [ebp-43Ch] BYREF
  JET_TABLEID v72; // [esp+B0h] [ebp-438h]
  unsigned int v73; // [esp+B4h] [ebp-434h]
  JET_COLUMNID v74; // [esp+B8h] [ebp-430h]
  JET_COLUMNID v75; // [esp+C8h] [ebp-420h]
  JET_COLUMNID v76; // [esp+CCh] [ebp-41Ch]
  JET_TABLEID v77[4]; // [esp+D8h] [ebp-410h] BYREF
  __int64 v78; // [esp+E8h] [ebp-400h]
  int v79; // [esp+F0h] [ebp-3F8h]
  wchar_t v80; // [esp+F4h] [ebp-3F4h]
  int v81; // [esp+11Ch] [ebp-3CCh] BYREF
  JET_TABLEID v82; // [esp+120h] [ebp-3C8h]
  unsigned int v83; // [esp+124h] [ebp-3C4h]
  JET_COLUMNID v84; // [esp+128h] [ebp-3C0h]
  JET_COLUMNID v85; // [esp+12Ch] [ebp-3BCh]
  JET_COLUMNID v86; // [esp+154h] [ebp-394h]
  _OWORD v87[3]; // [esp+158h] [ebp-390h] BYREF
  int v88; // [esp+188h] [ebp-360h]
  wchar_t v89; // [esp+18Ch] [ebp-35Ch]
  _OWORD v90[2]; // [esp+198h] [ebp-350h] BYREF
  __int64 v91; // [esp+1B8h] [ebp-330h]
  __int16 v92; // [esp+1C0h] [ebp-328h]
  unsigned __int16 pvData[68]; // [esp+1D0h] [ebp-318h] BYREF
  wchar_t v94[68]; // [esp+258h] [ebp-290h] BYREF
  _WORD v95[258]; // [esp+2E0h] [ebp-208h] BYREF

  v69 = a5;
  v53 = a1;
  v67 = a2;
  memset(v70, 0, sizeof(v70));
  v87[0] = *(_OWORD *)L"ConstraintColumnUsageIndex";
  v88 = *(_DWORD *)L"ex";
  v7 = v53[4];
  v87[1] = *(_OWORD *)L"ntColumnUsageIndex";
  v89 = aConstraintcolu[26];
  v92 = 0;
  Index = 0;
  v54 = 0;
  v62 = 1;
  v65 = 0;
  v63 = 0;
  String1 = 0;
  String2 = 0;
  v87[2] = *(_OWORD *)L"UsageIndex";
  v90[0] = *(_OWORD *)L"+002";
  v90[1] = xmmword_1000751C;
  v91 = 0x3800300030LL;
  if ( this )
  {
    if ( !a4 )
      goto LABEL_21;
    if ( (unsigned int)this > 7 )
      goto LABEL_21;
    v8 = *(unsigned __int16 *)a4;
    if ( (_WORD)v8 )
    {
      if ( v8 != 1 && (v8 != 8 || *((_DWORD *)a4 + 2)) )
        goto LABEL_21;
    }
    if ( (unsigned int)this > 1 )
    {
      v9 = *((unsigned __int16 *)a4 + 8);
      if ( (_WORD)v9 )
      {
        if ( v9 != 1 && (v9 != 8 || *((_DWORD *)a4 + 6)) )
          goto LABEL_21;
      }
    }
    if ( (unsigned int)this > 2 )
    {
      v10 = *((unsigned __int16 *)a4 + 16);
      if ( (_WORD)v10 )
      {
        if ( v10 != 1 && v10 != 8 )
          goto LABEL_21;
      }
    }
    if ( (unsigned int)this > 3 )
    {
      v11 = *((unsigned __int16 *)a4 + 24);
      if ( (_WORD)v11 && v11 != 1 && v11 != 8 )
      {
LABEL_21:
        v12 = v53[5];
        v13 = -2147024809;
        v49 = -2147024809;
        v14 = v7;
LABEL_141:
        if ( !JetGetDatabaseInfo(v14, v12, &v67, 4, 3) )
        {
          CExtError::SendHRtoOLEAuto((int)&IID_IDBSchemaRowset, 0, v47, (int)v48);
          goto LABEL_143;
        }
LABEL_145:
        JetCloseTable(v7, v70[1]);
        goto LABEL_146;
      }
      goto LABEL_23;
    }
    if ( (unsigned int)this > 2 )
    {
LABEL_23:
      v15 = *((unsigned __int16 *)a4 + 16);
      if ( (_WORD)v15 && v15 != 1 )
      {
        v16 = (wchar_t *)*((_DWORD *)a4 + 10);
        v17 = 1;
        v57 = 0;
        v65 = 1;
        if ( !v16 )
          v17 = v57;
        String1 = v16;
        v62 = v17;
      }
      if ( (unsigned int)this > 3 )
      {
        v18 = *((unsigned __int16 *)a4 + 24);
        if ( (_WORD)v18 )
        {
          if ( v18 != 1 )
          {
            v19 = (wchar_t *)*((_DWORD *)a4 + 14);
            v63 = 1;
            String2 = v19;
            if ( !v19 )
              v62 = 0;
          }
        }
      }
    }
  }
  v20 = (JET_COLUMNID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          36);
  v54 = v20;
  if ( !v20 )
    goto LABEL_135;
  v13 = SRSCreateTempTable(11, v53, &v52, v20, 0);
  v49 = v13;
  if ( v13 < 0 )
    goto LABEL_137;
  Index = JetCreateIndex(v7, v52, v87, 0, v90, 21, 100);
  if ( (Index & 0x80000000) != 0 )
    goto LABEL_36;
  Index = JetSetCurrentIndex(v7, v52, v87);
  if ( (Index & 0x80000000) != 0 )
  {
    v13 = -2147467259;
    goto LABEL_136;
  }
  Index = JetGetObjectInfo(v7, v53[5], 0, L"tables", 0, v70, 48, 1);
  if ( Index )
  {
    v13 = -2147467259;
    goto LABEL_136;
  }
  v21 = JetMove(v7, v70[1], 0x80000000, 0);
  Index = v21;
  if ( v21 != -1603 && v21 )
  {
    v13 = -2147467259;
    goto LABEL_136;
  }
  v57 = 0;
  if ( v70[2] )
  {
    while ( v62 )
    {
      v79 = *(_DWORD *)L"le";
      v80 = aValidationrule[14];
      *(_OWORD *)v77 = *(_OWORD *)L"ValidationRule";
      v78 = *(_QWORD *)L"onRule";
      Index = JetRetrieveColumn(v7, v70[1], v70[4], pvData, 0x81u, &pcbActual, 0, 0);
      if ( Index )
        goto LABEL_36;
      if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
LABEL_150:
        __report_rangecheckfailure();
      *(unsigned __int16 *)((char *)pvData + (pcbActual & 0xFFFFFFFE)) = 0;
      if ( v65 && __wcsicmp(String1, pvData) )
      {
        Index = JetMove(v7, v70[1], 1, 0);
        v49 = v13;
        goto LABEL_102;
      }
      Index = JetRetrieveColumn(v7, v70[1], v70[5], &v68, 4u, &pcbActual, 0, 0);
      if ( Index )
        goto LABEL_137;
      if ( v68 != 1 && v68 != 4 && v68 != 6 )
        goto LABEL_55;
      v22 = operator new(0x10u);
      v55 = v22;
      if ( !v22 )
        goto LABEL_135;
      *v22 = &ColumnData::`vftable';
      v22[1] = 0;
      v23 = v53;
      v22[2] = 0;
      v22[3] = 0;
      v13 = ColumnData::FInit((ColumnData *)v22, v7, v23[5], pvData, (int *)&Index, 0);
      v49 = v13;
      if ( (int)Index > -1811 )
      {
        if ( Index )
          goto LABEL_106;
        if ( v13 < 0 )
          goto LABEL_137;
      }
      else
      {
        if ( Index != -1811 && Index != -2001 && Index != -1907 )
        {
LABEL_106:
          (*(void (__thiscall **)(_DWORD *, int))(*v55 + 4))(v55, 1);
          goto LABEL_137;
        }
        Index = 0;
      }
      v24 = v55;
      v25 = 0;
      v50 = 0;
      if ( v55[1] )
      {
        while ( 1 )
        {
          v26 = (_DWORD *)(v24[3] + 104 * v25);
          v27 = (const unsigned __int16 *)v26[1];
          if ( !v27 )
          {
            v28 = v26[6];
            if ( !v28 || (unsigned int)(v28 - 2) <= 1 )
              v27 = (const unsigned __int16 *)v26[7];
            v25 = v50;
          }
          if ( !v63 )
            goto LABEL_73;
          if ( v27 )
            break;
LABEL_83:
          v24 = v55;
          v50 = ++v25;
          if ( v25 >= v55[1] )
            goto LABEL_84;
        }
        if ( !__wcsicmp(v27, String2) )
        {
LABEL_73:
          v29 = JetRetrieveProperty(v7, v53[5], L"tables", pvData, v27, v77, v95, 255, &v66, 0, 0, 0);
          Index = v29;
          if ( v29 != -3600 && v29 != -1907 )
          {
            if ( v29 )
              goto LABEL_36;
            if ( (v66 & 0xFFFFFFFE) >= 0x200 )
              goto LABEL_150;
            v46 = v52;
            *(_WORD *)((char *)v95 + (v66 & 0xFFFFFFFE)) = 0;
            Index = JetPrepareUpdate(v7, v46, 0);
            if ( Index )
              goto LABEL_36;
            JetSetColumn(v7, v52, v54[2], pvData, 2 * wcslen(pvData), 0, 0);
            v30 = v27 ? 2 * wcslen(v27) : 0;
            v45 = v27;
            v31 = v54;
            JetSetColumn(v7, v52, v54[3], v45, v30, 0, 0);
            JetSetColumn(v7, v52, v31[8], v77, 2 * wcslen((const unsigned __int16 *)v77), 0, 0);
            Index = JetUpdate(v7, v52, 0, 0, 0);
            if ( Index )
              goto LABEL_36;
          }
        }
        v25 = v50;
        goto LABEL_83;
      }
LABEL_84:
      IndexInfo = JetGetIndexInfo(v7, v53[5], pvData, 0, &v81, 60, 1);
      Index = IndexInfo;
      if ( IndexInfo <= -1404 )
      {
        if ( IndexInfo != -1404 && IndexInfo != -1907 && IndexInfo != -1811 )
          goto LABEL_36;
        v13 = 0;
        v49 = 0;
        Index = 0;
LABEL_55:
        Index = JetMove(v7, v70[1], 1, 0);
        goto LABEL_102;
      }
      if ( IndexInfo )
        goto LABEL_36;
      v60 = 0;
      v49 = 0;
      if ( v83 )
      {
        while ( 1 )
        {
          Index = JetRetrieveColumn(v7, v82, v85, &v61, 4u, &cbData, 0, 0);
          if ( Index )
            break;
          v49 = 0;
          if ( (v61 & 3) != 0 )
          {
            Index = JetRetrieveColumn(v7, v82, v86, v94, 0x82u, &cbData, 0, 0);
            if ( (Index & 0x80000000) != 0 )
              break;
            if ( (cbData & 0xFFFFFFFE) >= 0x82 )
              goto LABEL_150;
            v13 = 0;
            *(wchar_t *)((char *)v94 + (cbData & 0xFFFFFFFE)) = 0;
            v49 = 0;
            if ( !v63 || (v49 = 0, !__wcsicmp(v94, String2)) )
            {
              Index = JetPrepareUpdate(v7, v52, 0);
              if ( Index )
                break;
              JetSetColumn(v7, v52, v54[2], pvData, 2 * wcslen(pvData), 0, 0);
              JetSetColumn(v7, v52, v54[3], v94, cbData, 0, 0);
              Index = JetRetrieveColumn(v7, v82, v84, v94, 0x80u, &cbData, 0, 0);
              if ( (Index & 0x80000000) != 0 )
                goto LABEL_137;
              JetSetColumn(v7, v52, v54[8], v94, cbData, 0, 0);
              Index = JetUpdate(v7, v52, 0, 0, 0);
              if ( Index )
                break;
            }
          }
          Index = JetMove(v7, v82, 1, 0);
          if ( ++v60 >= v83 )
            goto LABEL_101;
        }
LABEL_36:
        v13 = -2147467259;
LABEL_136:
        v49 = v13;
        goto LABEL_137;
      }
LABEL_101:
      Index = JetCloseTable(v7, v82);
      Index = JetMove(v7, v70[1], 1, 0);
      (*(void (__thiscall **)(_DWORD *, int))(*v55 + 4))(v55, 1);
      v13 = 0;
LABEL_102:
      if ( ++v57 >= v70[2] )
        break;
    }
  }
  v33 = v53;
  RelationshipInfo = JetGetRelationshipInfo(v7, v53[5], 0, 0, &v71, 44);
  Index = RelationshipInfo;
  if ( RelationshipInfo != -1907 && RelationshipInfo )
  {
    v13 = -2147467259;
    goto LABEL_136;
  }
  v55 = 0;
  if ( v73 )
  {
    while ( v62 )
    {
      v35 = 1;
      v61 = 1;
      Index = JetRetrieveColumn(v7, v72, v74, v95, 0x81u, &pcbActual, 0, 0);
      if ( Index )
        goto LABEL_36;
      if ( (pcbActual & 0xFFFFFFFE) >= 0x200 )
        goto LABEL_150;
      *(_WORD *)((char *)v95 + (pcbActual & 0xFFFFFFFE)) = 0;
      JetRetrieveColumn(v7, v72, v75, pvData, 0x82u, &v57, 0, 0);
      if ( (v57 & 0xFFFFFFFE) >= 0x82 )
        goto LABEL_150;
      *(unsigned __int16 *)((char *)pvData + (v57 & 0xFFFFFFFE)) = 0;
      JetRetrieveColumn(v7, v72, v76, v94, 0x82u, &v60, 0, 0);
      if ( (v60 & 0xFFFFFFFE) >= 0x82 )
        goto LABEL_150;
      *(wchar_t *)((char *)v94 + (v60 & 0xFFFFFFFE)) = 0;
      if ( v65 )
        v35 = __wcsicmp(pvData, String1) == 0;
      if ( v63 )
        v36 = __wcsicmp(v94, String2) == 0;
      else
        v36 = v61;
      if ( v35 )
      {
        if ( v36 )
        {
          Index = JetPrepareUpdate(v7, v52, 0);
          if ( Index )
            goto LABEL_36;
          v37 = v54;
          JetSetColumn(v7, v52, v54[2], pvData, v57, 0, 0);
          JetSetColumn(v7, v52, v37[3], v94, v60, 0, 0);
          JetSetColumn(v7, v52, v37[8], v95, pcbActual, 0, 0);
          Index = JetUpdate(v7, v52, 0, 0, 0);
          if ( Index )
            goto LABEL_36;
        }
      }
      Index = JetMove(v7, v72, 1, 0);
      v55 = (_DWORD *)((char *)v55 + 1);
      if ( (unsigned int)v55 >= v73 )
        break;
    }
    v33 = v53;
  }
  Index = JetCloseTable(v7, v72);
  v38 = (wchar_t *)operator new(0x20u);
  String1 = v38;
  if ( !v38 )
  {
LABEL_135:
    v13 = -2147024882;
    goto LABEL_136;
  }
  *((_DWORD *)v38 + 1) = 0;
  *((_DWORD *)v38 + 2) = 0;
  *((_DWORD *)v38 + 3) = 0;
  *(_DWORD *)v38 = &ColumnDataWithFakeNamesAndDBTYPES::`vftable';
  *((_DWORD *)v38 + 4) = 0;
  *((_DWORD *)v38 + 5) = 0;
  *((_DWORD *)v38 + 6) = 0;
  *((_DWORD *)v38 + 7) = 0;
  *((_DWORD *)v38 + 4) = dword_10007BE0;
  *((_DWORD *)v38 + 7) = 0;
  *((_DWORD *)v38 + 5) = &SRSConstraintColumnUsageNames;
  v39 = v33[5];
  v13 = 0;
  v66 = v39;
  v61 = v52;
  v49 = 0;
  v77[1] = -1;
  TableColumnInfo = JetGetTableColumnInfo(v7, v52, 0, v77, 56, 1);
  Index = TableColumnInfo;
  if ( TableColumnInfo != -3031 )
  {
    if ( TableColumnInfo >= 0 )
    {
      if ( v77[2] )
      {
        v13 = (**(int (__thiscall ***)(wchar_t *, JET_SESID, int, JET_TABLEID *, JET_TABLEID, _DWORD, _DWORD, _DWORD, unsigned int *))String1)(
                String1,
                v7,
                v66,
                v77,
                v61,
                0,
                0,
                0,
                &Index);
        v49 = v13;
      }
    }
    else
    {
      v13 = -2147467259;
      v49 = -2147467259;
    }
  }
  if ( v77[1] != -1 )
    JetCloseTable(v7, v77[1]);
  if ( v13 >= 0 )
  {
    v41 = v67;
    v44 = String1;
    v43 = v69;
    *((_DWORD *)String1 + 1) = 9;
    v13 = CRowset::FInit(v41, 0, v53, 0, 0, 0, v52, v43, 1, 0, 0, v44, 1, 0, 0, &GUID_NULL);
    v49 = v13;
    Index = JetCloseTable(v7, v70[1]);
    if ( Index )
    {
      v13 = -2147467259;
      goto LABEL_136;
    }
  }
LABEL_137:
  if ( !Index )
  {
    if ( v13 >= 0 )
      goto LABEL_146;
    v49 = v13;
    v12 = v53[5];
    v14 = v53[4];
    if ( v13 == -2147024882 )
      goto LABEL_145;
    goto LABEL_141;
  }
  CExtError::SendJetErrortoOLEAuto(Index, (int)&IID_IDBSchemaRowset, (int)v47, v48);
LABEL_143:
  if ( v13 < 0 || Index )
    goto LABEL_145;
LABEL_146:
  if ( v54 && Sys )
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNID *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v54);
  return v49;
}

```

## disassembly

```asm
0x1003d390  mov     edi, edi
0x1003d392  push    ebp
0x1003d393  mov     ebp, esp
0x1003d395  and     esp, 0FFFFFFF0h
0x1003d398  sub     esp, 4C8h
0x1003d39e  mov     eax, ___security_cookie
0x1003d3a3  xor     eax, esp
0x1003d3a5  mov     [esp+4C8h+var_4], eax
0x1003d3ac  mov     eax, [ebp+arg_8]
0x1003d3af  push    esi; int
0x1003d3b0  mov     esi, [ebp+arg_4]
0x1003d3b3  push    edi; struct _GUID *
0x1003d3b4  push    30h ; '0'; Size
0x1003d3b6  mov     [esp+4D4h+var_470], eax
0x1003d3ba  lea     eax, [esp+4D4h+var_46C]
0x1003d3be  push    0; Val
0x1003d3c0  push    eax; void *
0x1003d3c1  mov     [esp+4DCh+var_4B0], edx
0x1003d3c5  mov     [esp+4DCh+var_478], ecx
0x1003d3c9  call    _memset
0x1003d3ce  movups  xmm0, xmmword ptr ds:aConstraintcolu; "ConstraintColumnUsageIndex"
0x1003d3d5  mov     eax, dword ptr ds:aConstraintcolu+30h; "ex"
0x1003d3da  add     esp, 0Ch
0x1003d3dd  mov     edx, [esp+4D0h+var_4B0]
0x1003d3e1  movups  [esp+4D0h+var_390], xmm0
0x1003d3e9  mov     [esp+4D0h+var_360], eax
0x1003d3f0  movups  xmm0, xmmword ptr ds:aConstraintcolu+10h; "ntColumnUsageIndex"
0x1003d3f7  movzx   eax, word ptr ds:aConstraintcolu+34h; ""
0x1003d3fe  mov     edi, [edx+10h]
0x1003d401  movups  [esp+4D0h+var_380], xmm0
0x1003d409  mov     [esp+4D0h+var_35C], ax
0x1003d411  movups  xmm0, xmmword ptr ds:aConstraintcolu+20h; "UsageIndex"
0x1003d418  movzx   eax, ds:word_10007534
0x1003d41f  mov     [esp+4D0h+var_328], ax
0x1003d427  mov     eax, [ebp+this]
0x1003d42a  mov     [esp+4D0h+var_4B8], 0
0x1003d432  mov     [esp+4D0h+var_4AC], 0
0x1003d43a  mov     [esp+4D0h+var_48C], 1
0x1003d442  mov     [esp+4D0h+var_480], 0
0x1003d44a  mov     [esp+4D0h+var_488], 0
0x1003d452  mov     [esp+4D0h+String1], 0
0x1003d45a  mov     [esp+4D0h+String2], 0
0x1003d462  movups  [esp+4D0h+var_370], xmm0
0x1003d46a  movups  xmm0, xmmword ptr ds:a002; "+002"
0x1003d471  movups  [esp+4D0h+var_350], xmm0
0x1003d479  movups  xmm0, ds:xmmword_1000751C
0x1003d480  movups  [esp+4D0h+var_340], xmm0
0x1003d488  movq    xmm0, ds:qword_1000752C
0x1003d490  movq    [esp+4D0h+var_330], xmm0
0x1003d499  test    eax, eax
0x1003d49b  jz      loc_1003D587
0x1003d4a1  test    esi, esi
0x1003d4a3  jz      short loc_1003D510
0x1003d4a5  cmp     eax, 7
0x1003d4a8  ja      short loc_1003D510
0x1003d4aa  movzx   ecx, word ptr [esi]
0x1003d4ad  test    cx, cx
0x1003d4b0  jz      short loc_1003D4C2
0x1003d4b2  cmp     ecx, 1
0x1003d4b5  jz      short loc_1003D4C2
0x1003d4b7  cmp     ecx, 8
0x1003d4ba  jnz     short loc_1003D510
0x1003d4bc  cmp     dword ptr [esi+8], 0
0x1003d4c0  jnz     short loc_1003D510
0x1003d4c2  cmp     eax, 1
0x1003d4c5  jbe     short loc_1003D4E0
0x1003d4c7  movzx   ecx, word ptr [esi+10h]
0x1003d4cb  test    cx, cx
0x1003d4ce  jz      short loc_1003D4E0
0x1003d4d0  cmp     ecx, 1
0x1003d4d3  jz      short loc_1003D4E0
0x1003d4d5  cmp     ecx, 8
0x1003d4d8  jnz     short loc_1003D510
0x1003d4da  cmp     dword ptr [esi+18h], 0
0x1003d4de  jnz     short loc_1003D510
0x1003d4e0  cmp     eax, 2
0x1003d4e3  jbe     short loc_1003D4F8
0x1003d4e5  movzx   ecx, word ptr [esi+20h]
0x1003d4e9  test    cx, cx
0x1003d4ec  jz      short loc_1003D4F8
0x1003d4ee  cmp     ecx, 1
0x1003d4f1  jz      short loc_1003D4F8
0x1003d4f3  cmp     ecx, 8
0x1003d4f6  jnz     short loc_1003D510
0x1003d4f8  cmp     eax, 3
0x1003d4fb  jbe     short loc_1003D523
0x1003d4fd  movzx   ecx, word ptr [esi+30h]
0x1003d501  test    cx, cx
0x1003d504  jz      short loc_1003D528
0x1003d506  cmp     ecx, 1
0x1003d509  jz      short loc_1003D528
0x1003d50b  cmp     ecx, 8
0x1003d50e  jz      short loc_1003D528
0x1003d510  mov     eax, [edx+14h]
0x1003d513  mov     esi, 80070057h
0x1003d518  mov     [esp+4D0h+var_4BC], esi
0x1003d51c  mov     ecx, edi
0x1003d51e  jmp     loc_1003E104
0x1003d523  cmp     eax, 2
0x1003d526  jbe     short loc_1003D587
0x1003d528  movzx   ecx, word ptr [esi+20h]
0x1003d52c  test    cx, cx
0x1003d52f  jz      short loc_1003D55D
0x1003d531  cmp     ecx, 1
0x1003d534  jz      short loc_1003D55D
0x1003d536  mov     edx, [esi+28h]
0x1003d539  mov     ecx, 1
0x1003d53e  test    edx, edx
0x1003d540  mov     [esp+4D0h+var_4A0], 0
0x1003d548  mov     [esp+4D0h+var_480], 1
0x1003d550  cmovz   ecx, [esp+4D0h+var_4A0]
0x1003d555  mov     [esp+4D0h+String1], edx
0x1003d559  mov     [esp+4D0h+var_48C], ecx
0x1003d55d  cmp     eax, 3
0x1003d560  jbe     short loc_1003D587
0x1003d562  movzx   eax, word ptr [esi+30h]
0x1003d566  test    ax, ax
0x1003d569  jz      short loc_1003D587
0x1003d56b  cmp     eax, 1
0x1003d56e  jz      short loc_1003D587
0x1003d570  mov     eax, [esi+38h]
0x1003d573  mov     [esp+4D0h+var_488], 1
0x1003d57b  mov     [esp+4D0h+String2], eax
0x1003d57f  test    eax, eax
0x1003d581  jnz     short loc_1003D587
0x1003d583  mov     [esp+4D0h+var_48C], eax
0x1003d587  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1003d58d  push    24h ; '$'
0x1003d58f  push    ecx
0x1003d590  mov     eax, [ecx]
0x1003d592  mov     esi, [eax+0Ch]
0x1003d595  mov     ecx, esi
0x1003d597  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1003d59d  call    esi
0x1003d59f  mov     [esp+4D0h+var_4AC], eax
0x1003d5a3  test    eax, eax
0x1003d5a5  jz      loc_1003E0B9
0x1003d5ab  mov     edx, [esp+4D0h+var_4B0]
0x1003d5af  mov     ecx, 0Bh
0x1003d5b4  push    0
0x1003d5b6  push    eax
0x1003d5b7  lea     eax, [esp+4D8h+var_4B4]
0x1003d5bb  push    eax
0x1003d5bc  call    SRSCreateTempTable
0x1003d5c1  mov     esi, eax
0x1003d5c3  mov     [esp+4D0h+var_4BC], esi
0x1003d5c7  test    esi, esi
0x1003d5c9  js      loc_1003E0C2
0x1003d5cf  push    64h ; 'd'
0x1003d5d1  push    15h
0x1003d5d3  lea     eax, [esp+4D8h+var_350]
0x1003d5da  push    eax
0x1003d5db  push    0
0x1003d5dd  lea     eax, [esp+4E0h+var_390]
0x1003d5e4  push    eax
0x1003d5e5  push    [esp+4E4h+var_4B4]
0x1003d5e9  push    edi
0x1003d5ea  call    ds:__imp__JetCreateIndex@28; JetCreateIndex(x,x,x,x,x,x,x)
0x1003d5f0  mov     [esp+4D0h+var_4B8], eax
0x1003d5f4  test    eax, eax
0x1003d5f6  jns     short loc_1003D602
0x1003d5f8  mov     esi, 80004005h
0x1003d5fd  jmp     loc_1003E0BE
0x1003d602  lea     eax, [esp+4D0h+var_390]
0x1003d609  push    eax
0x1003d60a  push    [esp+4D4h+var_4B4]
0x1003d60e  push    edi
0x1003d60f  call    ds:__imp__JetSetCurrentIndex@12; JetSetCurrentIndex(x,x,x)
0x1003d615  mov     [esp+4D0h+var_4B8], eax
0x1003d619  test    eax, eax
0x1003d61b  jns     short loc_1003D627
0x1003d61d  mov     esi, 80004005h
0x1003d622  jmp     loc_1003E0BE
0x1003d627  push    1
0x1003d629  push    30h ; '0'
0x1003d62b  lea     eax, [esp+4D8h+var_46C]
0x1003d62f  push    eax
0x1003d630  mov     eax, [esp+4DCh+var_4B0]
0x1003d634  push    0
0x1003d636  push    offset aTables_0; "tables"
0x1003d63b  push    0
0x1003d63d  push    dword ptr [eax+14h]
0x1003d640  push    edi
0x1003d641  call    ds:__imp__JetGetObjectInfo@32; JetGetObjectInfo(x,x,x,x,x,x,x,x)
0x1003d647  mov     [esp+4D0h+var_4B8], eax
0x1003d64b  test    eax, eax
0x1003d64d  jz      short loc_1003D659
0x1003d64f  mov     esi, 80004005h
0x1003d654  jmp     loc_1003E0BE
0x1003d659  push    0; grbit
0x1003d65b  push    80000000h; cRow
0x1003d660  push    [esp+4D8h+tableid]; tableid
0x1003d664  push    edi; sesid
0x1003d665  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1003d66b  mov     [esp+4D0h+var_4B8], eax
0x1003d66f  cmp     eax, 0FFFFF9BDh
0x1003d674  jz      short loc_1003D684
0x1003d676  test    eax, eax
0x1003d678  jz      short loc_1003D684
0x1003d67a  mov     esi, 80004005h
0x1003d67f  jmp     loc_1003E0BE
0x1003d684  cmp     [esp+4D0h+var_464], 0
0x1003d689  mov     [esp+4D0h+var_4A0], 0
0x1003d691  jbe     loc_1003DCC1
0x1003d697  nop     word ptr [eax+eax+00000000h]
0x1003d6a0  cmp     [esp+4D0h+var_48C], 0
0x1003d6a5  jz      loc_1003DCC1
0x1003d6ab  mov     eax, dword ptr ds:aValidationrule+18h; "le"
0x1003d6b0  movups  xmm0, xmmword ptr ds:aValidationrule; "ValidationRule"
0x1003d6b7  push    0; pretinfo
0x1003d6b9  mov     [esp+4D4h+var_3F8], eax
0x1003d6c0  mov     ax, word ptr ds:aValidationrule+1Ch; ""
0x1003d6c6  push    0; grbit
0x1003d6c8  mov     [esp+4D8h+var_3F4], ax
0x1003d6d0  lea     eax, [esp+4D8h+pcbActual]
0x1003d6d4  push    eax; pcbActual
0x1003d6d5  push    81h; cbData
0x1003d6da  lea     eax, [esp+4E0h+pvData]
0x1003d6e1  push    eax; pvData
0x1003d6e2  push    [esp+4E4h+columnid]; columnid
0x1003d6e9  movups  xmmword ptr [esp+4E8h+var_418+8], xmm0
0x1003d6f1  push    [esp+4E8h+tableid]; tableid
0x1003d6f8  movq    xmm0, qword ptr ds:aValidationrule+10h; "onRule"
0x1003d700  push    edi; sesid
0x1003d701  movq    [esp+4F0h+var_400], xmm0
0x1003d70a  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003d710  mov     [esp+4D0h+var_4B8], eax
0x1003d714  test    eax, eax
0x1003d716  jnz     loc_1003D5F8
0x1003d71c  mov     eax, [esp+4D0h+pcbActual]
0x1003d720  and     eax, 0FFFFFFFEh
0x1003d723  cmp     eax, 82h
0x1003d728  jnb     loc_1003E178
0x1003d72e  xor     ecx, ecx
0x1003d730  mov     [esp+eax+4D0h+pvData], cx
0x1003d738  cmp     [esp+4D0h+var_480], ecx
0x1003d73c  jz      short loc_1003D773
0x1003d73e  lea     eax, [esp+4D0h+pvData]
0x1003d745  push    eax; String2
0x1003d746  push    [esp+4D4h+String1]; String1
0x1003d74a  call    ds:__imp___wcsicmp
0x1003d750  add     esp, 8
0x1003d753  test    eax, eax
0x1003d755  jz      short loc_1003D773
0x1003d757  push    0; grbit
0x1003d759  push    1; cRow
0x1003d75b  push    [esp+4D8h+tableid]; tableid
0x1003d75f  push    edi; sesid
0x1003d760  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1003d766  mov     [esp+4D0h+var_4B8], eax
0x1003d76a  mov     [esp+4D0h+var_4BC], esi
0x1003d76e  jmp     loc_1003DCAE
0x1003d773  push    0; pretinfo
0x1003d775  push    0; grbit
0x1003d777  lea     eax, [esp+4D8h+pcbActual]
0x1003d77b  push    eax; pcbActual
0x1003d77c  push    4; cbData
0x1003d77e  lea     eax, [esp+4E0h+var_474]
0x1003d782  push    eax; pvData
0x1003d783  push    [esp+4E4h+var_458]; columnid
0x1003d78a  push    [esp+4E8h+tableid]; tableid
0x1003d791  push    edi; sesid
0x1003d792  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003d798  mov     [esp+4D0h+var_4B8], eax
0x1003d79c  test    eax, eax
0x1003d79e  jnz     loc_1003E0C2
0x1003d7a4  mov     eax, [esp+4D0h+var_474]
0x1003d7a8  sub     eax, 1
0x1003d7ab  jz      short loc_1003D7CF
0x1003d7ad  sub     eax, 3
0x1003d7b0  jz      short loc_1003D7CF
0x1003d7b2  sub     eax, 2
0x1003d7b5  jz      short loc_1003D7CF
0x1003d7b7  push    0; grbit
0x1003d7b9  push    1; cRow
0x1003d7bb  push    [esp+4D8h+tableid]; tableid
0x1003d7bf  push    edi; sesid
0x1003d7c0  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1003d7c6  mov     [esp+4D0h+var_4B8], eax
0x1003d7ca  jmp     loc_1003DCAE
0x1003d7cf  push    10h; Size
0x1003d7d1  call    ??2@YAPAXI@Z; operator new(uint)
0x1003d7d6  add     esp, 4
0x1003d7d9  mov     [esp+4D0h+var_4A8], eax
0x1003d7dd  test    eax, eax
0x1003d7df  jz      loc_1003E0B9
0x1003d7e5  push    0; int
0x1003d7e7  lea     ecx, [esp+4D4h+var_4B8]
0x1003d7eb  mov     dword ptr [eax], offset ??_7ColumnData@@6B@; const ColumnData::`vftable'
0x1003d7f1  push    ecx; int *
0x1003d7f2  lea     ecx, [esp+4D8h+pvData]
0x1003d7f9  mov     dword ptr [eax+4], 0
0x1003d800  push    ecx; unsigned __int16 *
0x1003d801  mov     ecx, [esp+4DCh+var_4B0]
0x1003d805  mov     dword ptr [eax+8], 0
0x1003d80c  mov     dword ptr [eax+0Ch], 0
0x1003d813  push    dword ptr [ecx+14h]; unsigned int
0x1003d816  mov     ecx, eax; this
0x1003d818  push    edi; sesid
0x1003d819  call    ?FInit@ColumnData@@QAEJKKPBGAAJH@Z; ColumnData::FInit(ulong,ulong,ushort const *,long &,int)
  ... truncated ...
```
