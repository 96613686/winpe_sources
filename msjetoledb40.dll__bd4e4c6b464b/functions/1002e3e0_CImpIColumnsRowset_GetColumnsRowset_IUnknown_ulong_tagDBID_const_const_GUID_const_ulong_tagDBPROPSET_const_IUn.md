# CImpIColumnsRowset::GetColumnsRowset(IUnknown *,ulong,tagDBID const * const,_GUID const &,ulong,tagDBPROPSET * const,IUnknown * *)

- ea: `0x1002e3e0`
- end: `0x1002ef73`
- name: `?GetColumnsRowset@CImpIColumnsRowset@@UAGJPAUIUnknown@@KQBUtagDBID@@ABU_GUID@@KQAUtagDBPROPSET@@PAPAU2@@Z`
- size: `2963`
- prototype: `int(CImpIColumnsRowset *__hidden this, struct IUnknown *, unsigned int, const struct tagDBID *const, const struct _GUID *, unsigned int, struct tagDBPROPSET *const, struct IUnknown **)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1000ba90`
- `0x1000d570`
- `0x1000e8d0`
- `0x100123d0`
- `0x10013100`
- `0x100146e0`
- `0x100147f0`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1001f2d0`
- `0x10020410`
- `0x100204c0`
- `0x100207d0`
- `0x100257a0`
- `0x10027cf0`
- `0x10028340`
- `0x1002e0b0`
- `0x1002e3e0`
- `0x100495b0`
- `0x1004ce5d`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1002ef43`
- `KERNEL32!LeaveCriticalSection` at `0x1002ef43`
- `KERNEL32!EnterCriticalSection` at `0x1002e49d`
- `KERNEL32!EnterCriticalSection` at `0x1002e49d`
- `msjet40!__imp__JetCloseTable@8` at `0x1002ef31`
- `msjet40!__imp__JetCloseTable@8` at `0x1002ef31`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1002eee8`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1002eee8`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1002e68b`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1002e78c`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1002e68b`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1002e78c`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e6b3`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e6d2`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e6f3`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e712`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e731`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e7f1`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e828`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e852`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e8b2`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e8cd`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e8fb`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e937`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e99e`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e9d2`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e9ff`
- `msjet40!__imp__JetSetColumn@28` at `0x1002ea59`
- `msjet40!__imp__JetSetColumn@28` at `0x1002eaa4`
- `msjet40!__imp__JetSetColumn@28` at `0x1002ead5`
- `msjet40!__imp__JetSetColumn@28` at `0x1002eaf9`
- `msjet40!__imp__JetSetColumn@28` at `0x1002eb50`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e6b3`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e6d2`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e6f3`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e712`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e731`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e7f1`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e828`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e852`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e8b2`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e8cd`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e8fb`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e937`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e99e`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e9d2`
- `msjet40!__imp__JetSetColumn@28` at `0x1002e9ff`
- `msjet40!__imp__JetSetColumn@28` at `0x1002ea59`
- `msjet40!__imp__JetSetColumn@28` at `0x1002eaa4`
- `msjet40!__imp__JetSetColumn@28` at `0x1002ead5`
- `msjet40!__imp__JetSetColumn@28` at `0x1002eaf9`
- `msjet40!__imp__JetSetColumn@28` at `0x1002eb50`
- `msjet40!__imp__JetUpdate@20` at `0x1002e746`
- `msjet40!__imp__JetUpdate@20` at `0x1002eb62`
- `msjet40!__imp__JetUpdate@20` at `0x1002e746`
- `msjet40!__imp__JetUpdate@20` at `0x1002eb62`

## pseudocode

```c
int __stdcall CImpIColumnsRowset::GetColumnsRowset(
        CImpIColumnsRowset *this,
        struct IUnknown *a2,
        unsigned int a3,
        const struct tagDBID *const a4,
        const struct _GUID *a5,
        unsigned int a6,
        struct tagDBPROPSET *const a7,
        struct IUnknown **a8)
{
  int v8; // edi
  BOOL v9; // eax
  struct _RTL_CRITICAL_SECTION *v10; // esi
  unsigned int v11; // edx
  int v12; // ecx
  const struct _GUID *v13; // edx
  GUID *v14; // ecx
  unsigned int v15; // edi
  bool v16; // cf
  int v17; // ecx
  bool v18; // zf
  CCommand *v19; // edi
  _DWORD *v20; // eax
  CTransactionState *v21; // ecx
  int isZombie; // eax
  int ColumnData; // edi
  int v24; // eax
  JoltProperties *v25; // edi
  unsigned int v26; // ecx
  int v27; // ecx
  unsigned int i; // eax
  _DWORD *v29; // edi
  int v30; // eax
  char *v31; // edx
  _WORD *v32; // ecx
  const void *v34; // eax
  int v35; // edi
  _DWORD *v36; // ecx
  const unsigned __int16 *v37; // edx
  int v38; // eax
  unsigned int v39; // ecx
  int v40; // ecx
  int v41; // edx
  int v42; // eax
  __int16 v43; // cx
  unsigned __int8 v44; // al
  int v45; // eax
  int v46; // eax
  int v47; // eax
  JET_COLUMNID v48; // edi
  int v49; // edx
  int v50; // ecx
  int v51; // eax
  _WORD *v52; // eax
  _WORD *v53; // ecx
  _WORD *v54; // edx
  char *v56; // eax
  char *v57; // edx
  char *v58; // ecx
  __int16 v59; // ax
  int v60; // edx
  JET_COLUMNID v61; // ecx
  JoltProperties *v62; // edi
  int v63; // eax
  BOOL v64; // eax
  CRowset *v65; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v66; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v67; // eax
  int v68; // ecx
  struct CDBSession *v69; // ecx
  _DWORD *v70; // eax
  int v71; // ecx
  unsigned int v72; // edi
  unsigned int v73; // esi
  int v74; // edi
  unsigned int v75; // edx
  int v76; // edx
  unsigned int v77; // ecx
  int v78; // eax
  int v80; // [esp-4h] [ebp-98h]
  struct CDBSession *v81; // [esp+0h] [ebp-94h]
  struct tagDBID *v82; // [esp+4h] [ebp-90h]
  void **v83; // [esp+Ch] [ebp-88h] BYREF
  __int128 v84; // [esp+10h] [ebp-84h]
  const struct _GUID *v85; // [esp+20h] [ebp-74h]
  BOOL v86; // [esp+24h] [ebp-70h] BYREF
  struct IUnknown **v87; // [esp+28h] [ebp-6Ch]
  __int16 v88; // [esp+2Ch] [ebp-68h] BYREF
  unsigned int v89; // [esp+30h] [ebp-64h] BYREF
  struct _RTL_CRITICAL_SECTION *v90; // [esp+34h] [ebp-60h]
  struct IUnknown *v91; // [esp+38h] [ebp-5Ch]
  struct tagDBPROPSET *v92; // [esp+3Ch] [ebp-58h]
  unsigned int v93; // [esp+40h] [ebp-54h] BYREF
  struct tagDBPROPSET *v94; // [esp+44h] [ebp-50h]
  unsigned int v95; // [esp+48h] [ebp-4Ch] BYREF
  struct CDBSession *v96; // [esp+4Ch] [ebp-48h]
  __int16 v97; // [esp+50h] [ebp-44h] BYREF
  int v98; // [esp+54h] [ebp-40h] BYREF
  int v99; // [esp+58h] [ebp-3Ch]
  int v100; // [esp+5Ch] [ebp-38h] BYREF
  int pvData; // [esp+60h] [ebp-34h] BYREF
  JET_SESID sesid; // [esp+64h] [ebp-30h]
  struct tagDBID tableid; // [esp+68h] [ebp-2Ch] BYREF
  int v104; // [esp+90h] [ebp-4h]

  v91 = a2;
  v85 = a5;
  v94 = a7;
  v95 = (unsigned int)this;
  v87 = a8;
  v93 = 0;
  tableid.uGuid.guid.Data1 = -1;
  v84 = 0;
  v83 = &CSchemaRowsetProperties::`vftable';
  v104 = 0;
  v8 = *((_DWORD *)this + 2);
  v9 = *((_DWORD *)this + 3) != 0;
  pvData = 0;
  v92 = 0;
  sesid = 0;
  v96 = *(struct CDBSession **)(4 * v9 + 52 + v8);
  v97 = 0;
  v10 = (struct _RTL_CRITICAL_SECTION *)(*(int (__thiscall **)(int))(*(_DWORD *)v8 + 16))(v8);
  v90 = v10;
  EnterCriticalSection(v10);
  LOBYTE(v104) = 1;
  if ( !a8 || (v11 = a3, *v87 = 0, a3) && !a4 || a6 && !v94 )
  {
LABEL_135:
    ColumnData = -2147024809;
    goto LABEL_136;
  }
  v12 = 0;
  if ( a6 )
  {
    do
    {
      v10 = v90;
      if ( v94[v12].cProperties )
      {
        v10 = v90;
        if ( !v94[v12].rgProperties )
          goto LABEL_135;
      }
    }
    while ( ++v12 < a6 );
  }
  if ( !v91 )
    goto LABEL_15;
  v13 = v85;
  v14 = &IID_IUnknown;
  v15 = 12;
  do
  {
    if ( v14->Data1 != v13->Data1 )
    {
      ColumnData = -2147217886;
      goto LABEL_136;
    }
    v14 = (GUID *)((char *)v14 + 4);
    v13 = (const struct _GUID *)((char *)v13 + 4);
    v16 = v15 < 4;
    v15 -= 4;
  }
  while ( !v16 );
  v11 = a3;
LABEL_15:
  v17 = 0;
  if ( v11 )
  {
    while ( a4[v17].eKind == 1 )
    {
      if ( ++v17 >= v11 )
        goto LABEL_18;
    }
    ColumnData = -2147217903;
    goto LABEL_136;
  }
LABEL_18:
  v18 = *(_DWORD *)(v95 + 12) == 0;
  v19 = *(CCommand **)(v95 + 8);
  v95 = (unsigned int)v19;
  if ( !v18 )
  {
    v99 = *((_DWORD *)v19 + 37);
    v98 = (*((_DWORD *)v19 + 24) >> 3) & 1;
    v20 = (_DWORD *)*((_DWORD *)v19 + 16);
    if ( v20
      && (v20[4] != 1 || (v21 = (CTransactionState *)v20[2]) == 0
        ? (isZombie = v20[3])
        : (isZombie = CTransactionState::isZombie(v21)),
          isZombie == 1)
      || !*((_DWORD *)v19 + 29) && !*((_DWORD *)v19 + 59) )
    {
      ColumnData = -2147418113;
LABEL_136:
      *((_DWORD *)&tableid.uGuid.pguid + 1) = ColumnData;
      goto LABEL_137;
    }
LABEL_42:
    sesid = *((_DWORD *)v96 + 4);
    ColumnData = ICRCreateTempTable((unsigned int)v96, (unsigned int)v96, &tableid, v81, &v82->uGuid.guid.Data1);
    *((_DWORD *)&tableid.uGuid.pguid + 1) = ColumnData;
    if ( ColumnData < 0 )
      goto LABEL_137;
    if ( v98 == 1 )
    {
      v93 = JetPrepareUpdate(*((_DWORD *)v96 + 4), tableid.uGuid.guid.Data1, 0);
      if ( v93 )
        goto LABEL_137;
      pvData = 2;
      JetSetColumn(sesid, tableid.uGuid.guid.Data1, 2u, &pvData, 4u, 0, 0);
      pvData = 0;
      JetSetColumn(sesid, tableid.uGuid.guid.Data1, 4u, &pvData, 4u, 0, 0);
      LOWORD(v98) = 3;
      JetSetColumn(sesid, tableid.uGuid.guid.Data1, 5u, &v98, 2u, 0, 0);
      pvData = 4;
      JetSetColumn(sesid, tableid.uGuid.guid.Data1, 7u, &pvData, 4u, 0, 0);
      pvData = 19;
      JetSetColumn(sesid, tableid.uGuid.guid.Data1, 0xAu, &pvData, 4u, 0, 0);
      v93 = JetUpdate(*((_DWORD *)v96 + 4), tableid.uGuid.guid.Data1, 0, 0, 0);
      if ( v93 )
        goto LABEL_137;
    }
    v27 = v99;
    v100 = 0;
    if ( v99 )
    {
      for ( i = 0; ; i = ++v100 )
      {
        *((_DWORD *)&tableid.uGuid.pguid + 1) = ColumnData;
        if ( i >= *(_DWORD *)(v27 + 4) )
          break;
        v97 = 0;
        v93 = JetPrepareUpdate(*((_DWORD *)v96 + 4), tableid.uGuid.guid.Data1, 0);
        if ( v93 )
        {
          v64 = 0;
          v92 = 0;
          goto LABEL_130;
        }
        v29 = (_DWORD *)(*(_DWORD *)(v99 + 12) + 104 * v100);
        v30 = v29[6];
        if ( !v30 || (unsigned int)(v30 - 2) <= 1 )
        {
          v31 = (char *)v29[7];
          if ( v31 )
          {
            v32 = (_WORD *)v29[7];
            *((_DWORD *)&tableid.uGuid.pguid + 1) = v31 + 2;
            while ( *v32++ )
              ;
            JetSetColumn(
              sesid,
              tableid.uGuid.guid.Data1,
              0,
              v31,
              2 * (((int)v32 - *((_DWORD *)&tableid.uGuid.pguid + 1)) >> 1),
              0,
              0);
          }
        }
        switch ( v29[6] )
        {
          case 0:
          case 1:
          case 6:
            v34 = v29 + 2;
            goto LABEL_59;
          case 3:
          case 4:
            v34 = (const void *)v29[2];
LABEL_59:
            if ( v34 )
              JetSetColumn(sesid, tableid.uGuid.guid.Data1, 1u, v34, 0x10u, 0, 0);
            break;
          default:
            break;
        }
        if ( v29[6] == 1 || (unsigned int)(v29[6] - 4) <= 1 )
          JetSetColumn(sesid, tableid.uGuid.guid.Data1, 2u, v29 + 7, 4u, 0, 0);
        v35 = v99;
        v36 = (_DWORD *)(*(_DWORD *)(v99 + 12) + 104 * v100);
        v37 = (const unsigned __int16 *)v36[1];
        if ( v37 )
          goto LABEL_70;
        v38 = v36[6];
        if ( v38 && (unsigned int)(v38 - 2) >= 2 )
        {
          v39 = 0;
          goto LABEL_71;
        }
        v37 = (const unsigned __int16 *)v36[7];
        if ( v37 )
        {
LABEL_70:
          v35 = v99;
          v39 = 2 * wcslen(v37);
        }
        else
        {
          v39 = 0;
        }
LABEL_71:
        JetSetColumn(sesid, tableid.uGuid.guid.Data1, 3u, v37, v39, 0, 0);
        ++v100;
        JetSetColumn(sesid, tableid.uGuid.guid.Data1, 4u, &v100, 4u, 0, 0);
        v40 = 104 * --v100;
        v88 = *(_WORD *)(v40 + *(_DWORD *)(v35 + 12) + 40);
        JetSetColumn(sesid, tableid.uGuid.guid.Data1, 5u, &v88, 2u, 0, 0);
        pvData = *(_DWORD *)(104 * v100 + *(_DWORD *)(v35 + 12) + 60);
        if ( *(_WORD *)(104 * v100 + *(_DWORD *)(v35 + 12) + 40) == 131 )
          pvData = 19;
        JetSetColumn(sesid, tableid.uGuid.guid.Data1, 7u, &pvData, 4u, 0, 0);
        v41 = v100;
        v42 = *(_DWORD *)(v35 + 12) + 104 * v100;
        v43 = *(_WORD *)(v42 + 40);
        if ( v43 == 131 )
        {
          v44 = *(_BYTE *)(v42 + 48);
        }
        else
        {
          v45 = 0;
          while ( word_10004700[2 * v45] != v43 )
          {
            if ( (unsigned int)++v45 >= 8 )
            {
              v44 = -1;
              goto LABEL_80;
            }
          }
          v44 = byte_10004702[4 * v45];
        }
LABEL_80:
        v97 = v44;
        if ( v44 != 255 )
        {
          JetSetColumn(sesid, tableid.uGuid.guid.Data1, 8u, &v97, 2u, 0, 0);
          v41 = v100;
        }
        v46 = *(_DWORD *)(v35 + 12);
        v10 = v90;
        if ( *(_WORD *)(104 * v41 + v46 + 40) == 131 )
        {
          v97 = *(unsigned __int8 *)(104 * v41 + v46 + 49);
          JetSetColumn(sesid, tableid.uGuid.guid.Data1, 9u, &v97, 2u, 0, 0);
          v41 = v100;
        }
        v47 = *(_DWORD *)(v35 + 12);
        v48 = 11;
        pvData = *(_DWORD *)(104 * v41 + v47 + 56);
        JetSetColumn(sesid, tableid.uGuid.guid.Data1, 0xAu, &pvData, 4u, 0, 0);
        v49 = v100;
        v50 = *(_DWORD *)(v99 + 12) + 104 * v100;
        v51 = *(_DWORD *)(v50 + 92);
        if ( !v51 || (unsigned int)(v51 - 2) <= 1 )
        {
          v52 = *(_WORD **)(v50 + 96);
          *((_DWORD *)&tableid.uGuid.pguid + 1) = v52;
          if ( v52 )
          {
            v53 = v52;
            v54 = v52 + 1;
            while ( *v53++ )
              ;
            v48 = 12;
            JetSetColumn(
              sesid,
              tableid.uGuid.guid.Data1,
              0xBu,
              *((const void **)&tableid.uGuid.pguid + 1),
              2 * (v53 - v54),
              0,
              0);
            v49 = v100;
          }
        }
        v56 = *(char **)(104 * v49 + *(_DWORD *)(v99 + 12) + 100);
        *((_DWORD *)&tableid.uGuid.pguid + 1) = v56;
        if ( v56 )
        {
          v57 = v56;
          v58 = v56 + 2;
          do
          {
            v59 = *(_WORD *)v57;
            v57 += 2;
          }
          while ( v59 );
          v60 = v57 - v58;
          v61 = v48++;
          JetSetColumn(
            sesid,
            tableid.uGuid.guid.Data1,
            v61,
            *((const void **)&tableid.uGuid.pguid + 1),
            2 * (v60 >> 1),
            0,
            0);
          v49 = v100;
        }
        HIBYTE(v98) = (*(_DWORD *)(104 * v49 + *(_DWORD *)(v99 + 12) + 52) & 0x10) != 0;
        JetSetColumn(sesid, tableid.uGuid.guid.Data1, v48, (char *)&v98 + 3, 1u, 0, 0);
        HIBYTE(v98) = 0;
        *((_DWORD *)&tableid.uGuid.pguid + 1) = v48 + 2;
        JetSetColumn(sesid, tableid.uGuid.guid.Data1, v48 + 1, (char *)&v98 + 3, 1u, 0, 0);
        v62 = *(JoltProperties **)(*((_DWORD *)v96 + 21) + 160);
        if ( JoltProperties::BinarySearch(v62, 0xBAu, &v89) < 0
          || (v63 = *((_DWORD *)v62 + 4), *(_WORD *)(v63 + 48 * v89 + 16) != 3) )
        {
          v95 = 0;
          ColumnData = -2147467259;
          goto LABEL_136;
        }
        ColumnData = 0;
        v95 = *(_DWORD *)(v63 + 48 * v89 + 24);
        JetSetColumn(sesid, tableid.uGuid.guid.Data1, *((JET_COLUMNID *)&tableid.uGuid.pguid + 1), &v95, 4u, 0, 0);
        v93 = JetUpdate(*((_DWORD *)v96 + 4), tableid.uGuid.guid.Data1, 0, 0, 0);
        if ( v93 )
          goto LABEL_136;
        v27 = v99;
      }
    }
    v65 = (CRowset *)operator new(0xF0u);
    v86 = (BOOL)v65;
    if ( v65 )
    {
      v92 = (struct tagDBPROPSET *)CRowset::CRowset(v65, v91);
      if ( v92 )
      {
        ColumnData = CSettableProperties::FInit((CSettableProperties *)&v83);
        *((_DWORD *)&tableid.uGuid.pguid + 1) = ColumnData;
        if ( ColumnData < 0 )
          goto LABEL_137;
        ColumnData = (*(int (__thiscall **)(_DWORD, const struct DBInfoProps *const *, int, int, unsigned int, _DWORD, _DWORD, _DWORD))(*(_DWORD *)DWORD1(v84) + 4))(
                       DWORD1(v84),
                       &rgDBInfoProps,
                       79,
                       74,
                       DBPROPSET_ROWSET.Data1,
                       *(_DWORD *)&DBPROPSET_ROWSET.Data2,
                       *(_DWORD *)DBPROPSET_ROWSET.Data4,
                       *(_DWORD *)&DBPROPSET_ROWSET.Data4[4]);
        *((_DWORD *)&tableid.uGuid.pguid + 1) = ColumnData;
        if ( ColumnData < 0 )
          goto LABEL_137;
        ColumnData = (*(int (__thiscall **)(_DWORD, const struct DBInfoProps *const *, int, int, int, int, int, int))(*(_DWORD *)DWORD2(v84) + 4))(
                       DWORD2(v84),
                       &rgDBInfoProps,
                       155,
                       13,
                       -1499601888,
                       298844197,
                       -1073701700,
                       -1039804593);
        *((_DWORD *)&tableid.uGuid.pguid + 1) = ColumnData;
        if ( ColumnData < 0 )
          goto LABEL_137;
        HIDWORD(v84) = *((_DWORD *)v96 + 21) + 152;
        ColumnData = CSettableProperties::SetProperties((CSettableProperties *)&v83, a6, v94, v96);
        *((_DWORD *)&tableid.uGuid.pguid + 1) = ColumnData;
        if ( ColumnData < 0 )
          goto LABEL_137;
        v86 = ColumnData == 265946;
        v66 = (ColumnDataWithFakeNamesAndDBTYPES *)operator new(0x20u);
        v89 = (unsigned int)v66;
        if ( v66 )
        {
          v67 = ColumnDataWithFakeNamesAndDBTYPES::ColumnDataWithFakeNamesAndDBTYPES(v66);
          pvData = (int)v67;
          if ( v67 )
          {
            v80 = v68;
            *((_DWORD *)v67 + 4) = dword_10006280;
            v69 = v96;
            *((_DWORD *)v67 + 6) = &ColumnsDefNames;
            *((_DWORD *)v67 + 7) = 1;
            *((_DWORD *)v67 + 5) = &rgwszColumnsDefNames;
            ColumnData = ColumnData::FInit(
                           v67,
                           sesid,
                           *((_DWORD *)v69 + 5),
                           tableid.uGuid.guid.Data1,
                           (int *)&v93,
                           0,
                           v80);
            *((_DWORD *)&tableid.uGuid.pguid + 1) = ColumnData;
            if ( ColumnData >= 0 )
            {
              v70 = (_DWORD *)pvData;
              v71 = 0;
              v98 = 0;
              v99 = 0;
              v95 = pvData + 4;
              v72 = *(_DWORD *)(pvData + 4);
              *((_DWORD *)&tableid.uGuid.pguid + 1) = v72;
              *(_DWORD *)(pvData + 4) = 11;
              v94 = v92;
              v10 = v90;
              if ( a3 )
              {
                pvData = (int)v70;
                if ( v72 <= 0xB )
                {
                  v77 = 11;
                  v94 = v92;
                }
                else
                {
                  v89 = (unsigned int)(v70 + 3);
                  v73 = 11;
                  v94 = v92;
                  do
                  {
                    v74 = 0;
                    v91 = (struct IUnknown *)(*(_DWORD *)v89 + 8 + 104 * v73);
                    while ( CompareDBIDs((const struct tagDBID *)v81, v82) < 0 )
                    {
                      if ( ++v74 >= a3 )
                      {
                        v75 = v99;
                        goto LABEL_118;
                      }
                    }
                    v76 = v99;
                    *((_DWORD *)&tableid.uGuid.pguid + v99 + 2) = v73;
                    v75 = v76 + 1;
                    v99 = v75;
LABEL_118:
                    ++v73;
                  }
                  while ( v73 < *((_DWORD *)&tableid.uGuid.pguid + 1) );
                  v10 = v90;
                  v77 = 11;
                  v89 = v75 + 11;
                  v91 = (struct IUnknown *)11;
                  if ( v75 < 0xFFFFFFF5 && v75 != 0 )
                  {
                    do
                    {
                      v78 = (int)*(&v94 + v77);
                      if ( v77 != v78 )
                      {
                        v98 = ColumnInfo::Copy(
                                (ColumnInfo *)(*(_DWORD *)(pvData + 12) + 104 * v77),
                                (struct ColumnInfo *)(*(_DWORD *)(pvData + 12) + 104 * v78));
                        ColumnData = v98;
                        *((_DWORD *)&tableid.uGuid.pguid + 1) = v98;
                        if ( v98 < 0 )
                          goto LABEL_137;
                        v77 = (unsigned int)v91;
                      }
                      v91 = (struct IUnknown *)++v77;
                    }
                    while ( v77 < v89 );
                  }
                  v70 = (_DWORD *)pvData;
                }
                *(_DWORD *)v95 = v77 - 11 + v70[1];
                v70 = (_DWORD *)pvData;
                v71 = v98;
              }
              ColumnData = v71;
              *((_DWORD *)&tableid.uGuid.pguid + 1) = v71;
              if ( v71 >= 0 )
              {
                ColumnData = CRowset::FInit(
                               v94,
                               0,
                               v96,
                               0,
                               0,
                               0,
                               tableid.uGuid.guid.Data1,
                               &v83,
                               1,
                               0,
                               0,
                               v70,
                               1,
                               0,
                               0,
                               &GUID_NULL);
                *((_DWORD *)&tableid.uGuid.pguid + 1) = ColumnData;
                if ( ColumnData >= 0 )
                {
                  ColumnData = ((int (__thiscall *)(DBPROPID, struct tagDBPROPSET *, const struct _GUID *, struct IUnknown **))v94->rgProperties->dwPropertyID)(
                                 v94->rgProperties->dwPropertyID,
                                 v94,
                                 v85,
                                 v87);
                  *((_DWORD *)&tableid.uGuid.pguid + 1) = ColumnData;
                  if ( ColumnData >= 0 )
                  {
                    v64 = v86;
LABEL_130:
                    if ( v64 )
                    {
                      ColumnData = 265946;
                      goto LABEL_136;
                    }
                  }
                }
              }
            }
            goto LABEL_137;
          }
        }
      }
    }
    else
    {
      v92 = 0;
    }
    ColumnData = -2147024882;
    goto LABEL_136;
  }
  if ( !*((_DWORD *)v19 + 24) )
    CCommand::CheckForZombieCommandAndFix(v81);
  v24 = *((_DWORD *)v19 + 15);
  if ( (v24 & 0x20) == 0 )
  {
    ColumnData = -2147217908;
    goto LABEL_136;
  }
  if ( (v24 & 0x10) == 0 )
  {
    ColumnData = -2147217846;
    goto LABEL_136;
  }
  ColumnData = CCommand::GetColumnData(v19, (struct ColumnData **)&pvData, (int *)&v93);
  *((_DWORD *)&tableid.uGuid.pguid + 1) = ColumnData;
  if ( ColumnData >= 0 || v93 != -1302 )
  {
    v25 = *(JoltProperties **)(*(_DWORD *)(v95 + 20) + 20);
    if ( JoltProperties::BinarySearch(v25, 0xEu, &v95) < 0 )
      v26 = 0;
    else
      v26 = *((_DWORD *)v25 + 4) + 48 * v95;
    v98 = *(_WORD *)(v26 + 24) == 0xFFFF;
    v99 = pvData;
    goto LABEL_42;
  }
LABEL_137:
  if ( v93 )
  {
    CExtError::SendJetErrortoOLEAuto(v93, (int)&IID_IColumnsRowset, (int)v81, &v82->uGuid.guid);
    if ( ColumnData >= 0 )
      goto LABEL_150;
  }
  else
  {
    if ( ColumnData >= 0 )
      goto LABEL_150;
    if ( ColumnData != -2147024882 && !JetGetDatabaseInfo(*((_DWORD *)v96 + 4), *((_DWORD *)v96 + 5), &v86, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_IColumnsRowset, 0, (const struct _GUID *)v81, (int)v82);
  }
  if ( v87 && !*v87 && v92 )
  {
    ((void (__thiscall *)(DBPROPSTATUS, struct tagDBPROPSET *))v92->rgProperties->dwStatus)(
      v92->rgProperties->dwStatus,
      v92);
    ColumnData = *((_DWORD *)&tableid.uGuid.pguid + 1);
  }
  if ( tableid.uGuid.guid.Data1 != -1 )
  {
    JetCloseTable(sesid, tableid.uGuid.guid.Data1);
    tableid.uGuid.guid.Data1 = -1;
  }
LABEL_150:
  if ( v10 )
    LeaveCriticalSection(v10);
  CSettableProperties::~CSettableProperties((CSettableProperties *)&v83);
  return ColumnData;
}

```

## disassembly

```asm
0x1002e3e0  mov     edi, edi
0x1002e3e2  push    ebp
0x1002e3e3  mov     ebp, esp
0x1002e3e5  push    0FFFFFFFFh
0x1002e3e7  push    offset ?GetColumnsRowset@CImpIColumnsRowset@@UAGJPAUIUnknown@@KQBUtagDBID@@ABU_GUID@@KQAUtagDBPROPSET@@PAPAU2@@Z_SEH
0x1002e3ec  mov     eax, large fs:0
0x1002e3f2  push    eax
0x1002e3f3  sub     esp, 7Ch
0x1002e3f6  mov     eax, ___security_cookie
0x1002e3fb  xor     eax, ebp
0x1002e3fd  mov     [ebp+var_10], eax
0x1002e400  push    esi
0x1002e401  push    edi; int
0x1002e402  push    eax; struct _GUID *
0x1002e403  lea     eax, [ebp+var_C]
0x1002e406  mov     large fs:0, eax
0x1002e40c  mov     eax, [ebp+arg_4]
0x1002e40f  xorps   xmm0, xmm0
0x1002e412  mov     ecx, [ebp+this]
0x1002e415  mov     [ebp+var_5C], eax
0x1002e418  mov     eax, [ebp+arg_10]
0x1002e41b  mov     [ebp+var_74], eax
0x1002e41e  mov     eax, [ebp+arg_18]
0x1002e421  mov     [ebp+var_50], eax
0x1002e424  mov     eax, [ebp+arg_1C]
0x1002e427  mov     [ebp+var_4C], ecx
0x1002e42a  mov     [ebp+var_6C], eax
0x1002e42d  mov     [ebp+var_54], 0
0x1002e434  mov     [ebp+tableid], 0FFFFFFFFh
0x1002e43b  movups  [ebp+var_84], xmm0
0x1002e442  mov     [ebp+var_88], offset ??_7CSchemaRowsetProperties@@6B@; const CSchemaRowsetProperties::`vftable'
0x1002e44c  mov     [ebp+var_4], 0
0x1002e453  xor     eax, eax
0x1002e455  cmp     [ecx+0Ch], eax
0x1002e458  mov     edi, [ecx+8]
0x1002e45b  setnz   al
0x1002e45e  mov     [ebp+pvData], 0
0x1002e465  mov     [ebp+var_58], 0
0x1002e46c  mov     [ebp+sesid], 0
0x1002e473  lea     eax, ds:34h[eax*4]
0x1002e47a  mov     eax, [eax+edi]
0x1002e47d  mov     [ebp+var_48], eax
0x1002e480  xor     eax, eax
0x1002e482  mov     [ebp+var_44], ax
0x1002e486  mov     eax, [edi]
0x1002e488  mov     esi, [eax+10h]
0x1002e48b  mov     ecx, esi
0x1002e48d  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002e493  mov     ecx, edi
0x1002e495  call    esi
0x1002e497  mov     esi, eax
0x1002e499  push    esi; lpCriticalSection
0x1002e49a  mov     [ebp+var_60], esi
0x1002e49d  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1002e4a3  mov     eax, [ebp+var_6C]
0x1002e4a6  mov     byte ptr [ebp+var_4], 1
0x1002e4aa  test    eax, eax
0x1002e4ac  jz      loc_1002EEA3
0x1002e4b2  mov     edx, [ebp+arg_8]
0x1002e4b5  mov     dword ptr [eax], 0
0x1002e4bb  test    edx, edx
0x1002e4bd  jz      short loc_1002E4C9
0x1002e4bf  cmp     [ebp+arg_C], 0
0x1002e4c3  jz      loc_1002EEA3
0x1002e4c9  mov     edi, [ebp+arg_14]
0x1002e4cc  test    edi, edi
0x1002e4ce  jz      short loc_1002E4DA
0x1002e4d0  cmp     [ebp+var_50], 0
0x1002e4d4  jz      loc_1002EEA3
0x1002e4da  xor     ecx, ecx
0x1002e4dc  test    edi, edi
0x1002e4de  jz      short loc_1002E505
0x1002e4e0  mov     esi, [ebp+var_50]
0x1002e4e3  lea     eax, [ecx+ecx*2]
0x1002e4e6  cmp     dword ptr [esi+eax*8+4], 0
0x1002e4eb  mov     esi, [ebp+var_60]
0x1002e4ee  jz      short loc_1002E500
0x1002e4f0  mov     esi, [ebp+var_50]
0x1002e4f3  cmp     dword ptr [esi+eax*8], 0
0x1002e4f7  mov     esi, [ebp+var_60]
0x1002e4fa  jz      loc_1002EEA3
0x1002e500  inc     ecx
0x1002e501  cmp     ecx, edi
0x1002e503  jb      short loc_1002E4E0
0x1002e505  cmp     [ebp+var_5C], 0
0x1002e509  jz      short loc_1002E52C
0x1002e50b  mov     edx, [ebp+var_74]
0x1002e50e  mov     ecx, offset _IID_IUnknown
0x1002e513  mov     edi, 0Ch
0x1002e518  mov     eax, [ecx]
0x1002e51a  cmp     eax, [edx]
0x1002e51c  jnz     short loc_1002E583
0x1002e51e  add     ecx, 4
0x1002e521  add     edx, 4
0x1002e524  sub     edi, 4
0x1002e527  jnb     short loc_1002E518
0x1002e529  mov     edx, [ebp+arg_8]
0x1002e52c  xor     ecx, ecx
0x1002e52e  test    edx, edx
0x1002e530  jz      short loc_1002E544
0x1002e532  mov     edi, [ebp+arg_C]
0x1002e535  lea     eax, [ecx+ecx*2]
0x1002e538  cmp     dword ptr [edi+eax*8+10h], 1
0x1002e53d  jnz     short loc_1002E58D
0x1002e53f  inc     ecx
0x1002e540  cmp     ecx, edx
0x1002e542  jb      short loc_1002E535
0x1002e544  mov     eax, [ebp+var_4C]
0x1002e547  cmp     dword ptr [eax+0Ch], 0
0x1002e54b  mov     edi, [eax+8]
0x1002e54e  mov     [ebp+var_4C], edi
0x1002e551  jz      short loc_1002E5C0
0x1002e553  mov     eax, [edi+94h]
0x1002e559  mov     [ebp+var_3C], eax
0x1002e55c  mov     eax, [edi+60h]
0x1002e55f  shr     eax, 3
0x1002e562  and     eax, 1
0x1002e565  mov     [ebp+var_40], eax
0x1002e568  mov     eax, [edi+40h]
0x1002e56b  test    eax, eax
0x1002e56d  jz      short loc_1002E59F
0x1002e56f  cmp     dword ptr [eax+10h], 1
0x1002e573  jnz     short loc_1002E597
0x1002e575  mov     ecx, [eax+8]; this
0x1002e578  test    ecx, ecx
0x1002e57a  jz      short loc_1002E597
0x1002e57c  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x1002e581  jmp     short loc_1002E59A
0x1002e583  mov     edi, 80040E22h
0x1002e588  jmp     loc_1002EEA8
0x1002e58d  mov     edi, 80040E11h
0x1002e592  jmp     loc_1002EEA8
0x1002e597  mov     eax, [eax+0Ch]
0x1002e59a  cmp     eax, 1
0x1002e59d  jz      short loc_1002E5B6
0x1002e59f  cmp     dword ptr [edi+74h], 0
0x1002e5a3  jnz     loc_1002E655
0x1002e5a9  cmp     dword ptr [edi+0ECh], 0
0x1002e5b0  jnz     loc_1002E655
0x1002e5b6  mov     edi, 8000FFFFh
0x1002e5bb  jmp     loc_1002EEA8
0x1002e5c0  cmp     dword ptr [edi+60h], 0
0x1002e5c4  jnz     short loc_1002E5CD
0x1002e5c6  mov     ecx, edi
0x1002e5c8  call    ?CheckForZombieCommandAndFix@CCommand@@QAGJXZ; CCommand::CheckForZombieCommandAndFix(void)
0x1002e5cd  mov     eax, [edi+3Ch]
0x1002e5d0  test    al, 20h
0x1002e5d2  jnz     short loc_1002E5DE
0x1002e5d4  mov     edi, 80040E0Ch
0x1002e5d9  jmp     loc_1002EEA8
0x1002e5de  test    al, 10h
0x1002e5e0  jnz     short loc_1002E5EC
0x1002e5e2  mov     edi, 80040E4Ah
0x1002e5e7  jmp     loc_1002EEA8
0x1002e5ec  lea     eax, [ebp+var_54]
0x1002e5ef  mov     ecx, edi; this
0x1002e5f1  push    eax; int *
0x1002e5f2  lea     eax, [ebp+pvData]
0x1002e5f5  push    eax; struct ColumnData **
0x1002e5f6  call    ?GetColumnData@CCommand@@IAEJPAPAVColumnData@@AAJ@Z; CCommand::GetColumnData(ColumnData * *,long &)
0x1002e5fb  mov     edi, eax
0x1002e5fd  mov     [ebp+columnid], edi
0x1002e600  test    edi, edi
0x1002e602  jns     short loc_1002E611
0x1002e604  cmp     [ebp+var_54], 0FFFFFAEAh
0x1002e60b  jz      loc_1002EEAB
0x1002e611  mov     eax, [ebp+var_4C]
0x1002e614  mov     eax, [eax+14h]
0x1002e617  mov     edi, [eax+14h]
0x1002e61a  lea     eax, [ebp+var_4C]
0x1002e61d  push    eax; unsigned int *
0x1002e61e  push    0Eh; unsigned int
0x1002e620  mov     ecx, edi; this
0x1002e622  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1002e627  test    eax, eax
0x1002e629  js      short loc_1002E639
0x1002e62b  mov     eax, [ebp+var_4C]
0x1002e62e  lea     ecx, [eax+eax*2]
0x1002e631  shl     ecx, 4
0x1002e634  add     ecx, [edi+10h]
0x1002e637  jmp     short loc_1002E63B
0x1002e639  xor     ecx, ecx
0x1002e63b  xor     eax, eax
0x1002e63d  or      edi, 0FFFFFFFFh
0x1002e640  cmp     di, [ecx+18h]
0x1002e644  mov     edx, 1
0x1002e649  cmovz   eax, edx
0x1002e64c  mov     [ebp+var_40], eax
0x1002e64f  mov     eax, [ebp+pvData]
0x1002e652  mov     [ebp+var_3C], eax
0x1002e655  mov     ecx, [ebp+var_48]
0x1002e658  mov     eax, [ecx+10h]
0x1002e65b  mov     [ebp+sesid], eax
0x1002e65e  lea     eax, [ebp+tableid]
0x1002e661  push    eax; struct tagDBID *
0x1002e662  push    ecx; unsigned int
0x1002e663  push    ecx; unsigned int
0x1002e664  call    ?ICRCreateTempTable@@YGJKKQBUtagDBID@@PAVCDBSession@@PAK@Z; ICRCreateTempTable(ulong,ulong,tagDBID const * const,CDBSession *,ulong *)
0x1002e669  mov     edi, eax
0x1002e66b  mov     [ebp+columnid], edi
0x1002e66e  test    edi, edi
0x1002e670  js      loc_1002EEAB
0x1002e676  cmp     [ebp+var_40], 1
0x1002e67a  jnz     loc_1002E757
0x1002e680  mov     ecx, [ebp+var_48]
0x1002e683  push    0; prep
0x1002e685  push    [ebp+tableid]; tableid
0x1002e688  push    dword ptr [ecx+10h]; sesid
0x1002e68b  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x1002e691  mov     [ebp+var_54], eax
0x1002e694  test    eax, eax
0x1002e696  jnz     loc_1002EEAB
0x1002e69c  push    eax; psetinfo
0x1002e69d  push    eax; grbit
0x1002e69e  push    4; cbData
0x1002e6a0  lea     eax, [ebp+pvData]
0x1002e6a3  mov     [ebp+pvData], 2
0x1002e6aa  push    eax; pvData
0x1002e6ab  push    2; columnid
0x1002e6ad  push    [ebp+tableid]; tableid
0x1002e6b0  push    [ebp+sesid]; sesid
0x1002e6b3  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1002e6b9  push    0; psetinfo
0x1002e6bb  push    0; grbit
0x1002e6bd  push    4; cbData
0x1002e6bf  lea     eax, [ebp+pvData]
0x1002e6c2  mov     [ebp+pvData], 0
0x1002e6c9  push    eax; pvData
0x1002e6ca  push    4; columnid
0x1002e6cc  push    [ebp+tableid]; tableid
0x1002e6cf  push    [ebp+sesid]; sesid
0x1002e6d2  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1002e6d8  push    0; psetinfo
0x1002e6da  push    0; grbit
0x1002e6dc  mov     eax, 3
0x1002e6e1  push    2; cbData
0x1002e6e3  mov     word ptr [ebp+var_40], ax
0x1002e6e7  lea     eax, [ebp+var_40]
0x1002e6ea  push    eax; pvData
0x1002e6eb  push    5; columnid
0x1002e6ed  push    [ebp+tableid]; tableid
0x1002e6f0  push    [ebp+sesid]; sesid
0x1002e6f3  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1002e6f9  push    0; psetinfo
0x1002e6fb  push    0; grbit
0x1002e6fd  push    4; cbData
0x1002e6ff  lea     eax, [ebp+pvData]
0x1002e702  mov     [ebp+pvData], 4
0x1002e709  push    eax; pvData
0x1002e70a  push    7; columnid
0x1002e70c  push    [ebp+tableid]; tableid
0x1002e70f  push    [ebp+sesid]; sesid
0x1002e712  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1002e718  push    0; psetinfo
0x1002e71a  push    0; grbit
0x1002e71c  push    4; cbData
0x1002e71e  lea     eax, [ebp+pvData]
0x1002e721  mov     [ebp+pvData], 13h
0x1002e728  push    eax; pvData
0x1002e729  push    0Ah; columnid
0x1002e72b  push    [ebp+tableid]; tableid
0x1002e72e  push    [ebp+sesid]; sesid
0x1002e731  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1002e737  mov     eax, [ebp+var_48]
0x1002e73a  push    0; pcbActual
0x1002e73c  push    0; cbBookmark
0x1002e73e  push    0; pvBookmark
0x1002e740  push    [ebp+tableid]; tableid
0x1002e743  push    dword ptr [eax+10h]; sesid
0x1002e746  call    ds:__imp__JetUpdate@20; JetUpdate(x,x,x,x,x)
0x1002e74c  mov     [ebp+var_54], eax
0x1002e74f  test    eax, eax
0x1002e751  jnz     loc_1002EEAB
0x1002e757  mov     ecx, [ebp+var_3C]
0x1002e75a  mov     [ebp+var_38], 0
0x1002e761  test    ecx, ecx
0x1002e763  jz      loc_1002EBAF
0x1002e769  xor     eax, eax
0x1002e76b  nop     dword ptr [eax+eax+00h]
0x1002e770  mov     [ebp+columnid], edi
0x1002e773  cmp     eax, [ecx+4]
0x1002e776  jnb     loc_1002EBAF
0x1002e77c  xor     eax, eax
0x1002e77e  push    eax; prep
0x1002e77f  push    [ebp+tableid]; tableid
0x1002e782  mov     [ebp+var_44], ax
0x1002e786  mov     eax, [ebp+var_48]
0x1002e789  push    dword ptr [eax+10h]; sesid
0x1002e78c  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x1002e792  mov     [ebp+var_54], eax
0x1002e795  test    eax, eax
0x1002e797  jnz     loc_1002EB93
0x1002e79d  imul    edi, [ebp+var_38], 68h ; 'h'
0x1002e7a1  mov     eax, [ebp+var_3C]
0x1002e7a4  add     edi, [eax+0Ch]
0x1002e7a7  mov     eax, [edi+18h]
0x1002e7aa  sub     eax, 0
0x1002e7ad  jz      short loc_1002E7B9
0x1002e7af  sub     eax, 2
0x1002e7b2  jz      short loc_1002E7B9
  ... truncated ...
```
