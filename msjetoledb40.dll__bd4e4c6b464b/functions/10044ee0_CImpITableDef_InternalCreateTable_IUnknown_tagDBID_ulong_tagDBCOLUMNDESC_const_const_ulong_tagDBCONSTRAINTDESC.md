# CImpITableDef::InternalCreateTable(IUnknown *,tagDBID *,ulong,tagDBCOLUMNDESC const * const,ulong,tagDBCONSTRAINTDESC * const,_GUID const &,ulong,tagDBPROPSET * const,tagDBID * *,IUnknown * *)

- ea: `0x10044ee0`
- end: `0x10045d0b`
- name: `?InternalCreateTable@CImpITableDef@@QAEJPAUIUnknown@@PAUtagDBID@@KQBUtagDBCOLUMNDESC@@KQAUtagDBCONSTRAINTDESC@@ABU_GUID@@KQAUtagDBPROPSET@@PAPAU3@PAPAU2@@Z`
- size: `3627`
- prototype: `int __thiscall(CImpITableDef *__hidden this, struct IUnknown *, struct tagDBID *, unsigned int, const struct tagDBCOLUMNDESC *const, unsigned int, struct tagDBCONSTRAINTDESC *const, const struct _GUID *, unsigned int, struct tagDBPROPSET *const, struct tagDBID **, struct IUnknown **)`
- caller_count: `2`
- callee_count: `28`
- tags: ``

## callers

- `0x10044290`
- `0x10044a20`

## callees

- `0x1000d4a0`
- `0x1000e8d0`
- `0x10016e10`
- `0x10016f20`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1001e960`
- `0x1001fb20`
- `0x1001fd10`
- `0x10020410`
- `0x100204c0`
- `0x100207d0`
- `0x10021070`
- `0x100215b0`
- `0x10022870`
- `0x10022990`
- `0x10022a90`
- `0x10025750`
- `0x10027cf0`
- `0x10028340`
- `0x10044ee0`
- `0x10045d20`
- `0x10046330`
- `0x1004b910`
- `0x1004ce5d`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `msjet40!__imp__JetCloseDatabase@12` at `0x10045af6`
- `msjet40!__imp__JetCloseDatabase@12` at `0x10045af6`
- `msjet40!__imp__JetCloseTable@8` at `0x100458c6`
- `msjet40!__imp__JetCloseTable@8` at `0x10045b4f`
- `msjet40!__imp__JetCloseTable@8` at `0x100458c6`
- `msjet40!__imp__JetCloseTable@8` at `0x10045b4f`
- `msjet40!__imp__JetCreateLink@24` at `0x1004576d`
- `msjet40!__imp__JetCreateLink@24` at `0x1004576d`
- `msjet40!__imp__JetCreateTable@24` at `0x1004549f`
- `msjet40!__imp__JetCreateTable@24` at `0x1004549f`
- `msjet40!__imp__JetDeleteTable@12` at `0x10045c4d`
- `msjet40!__imp__JetDeleteTable@12` at `0x10045c4d`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10045ac7`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10045ac7`
- `msjet40!__imp__JetDeleteRelationship@12` at `0x10045bdd`
- `msjet40!__imp__JetDeleteRelationship@12` at `0x10045bdd`

## pseudocode

```c
int __thiscall CImpITableDef::InternalCreateTable(
        CImpITableDef *this,
        struct IUnknown *a2,
        struct tagDBID *a3,
        unsigned int a4,
        const struct tagDBCOLUMNDESC *const a5,
        unsigned int a6,
        struct tagDBCONSTRAINTDESC *const a7,
        struct _GUID *a8,
        unsigned int a9,
        struct tagDBPROPSET *const a10,
        struct tagDBID **a11,
        struct IUnknown **a12)
{
  CImpITableDef *v12; // edx
  struct tagDBID *v13; // ebx
  int v14; // eax
  CDBSession **v15; // esi
  int v16; // edi
  int v17; // ecx
  int v18; // eax
  int v19; // ecx
  int v20; // ecx
  struct _GUID *v21; // edx
  GUID *v22; // ecx
  unsigned int v23; // esi
  bool v24; // cf
  int v25; // eax
  CDBSession **v26; // ebx
  int v27; // eax
  _DWORD *v28; // edi
  int v29; // edx
  LPOLESTR pwszName; // ecx
  _WORD *v31; // esi
  unsigned __int16 *v33; // edi
  int v34; // eax
  struct tagDBID **v35; // edx
  unsigned __int16 *v36; // edx
  CDBSession **v37; // edi
  unsigned int v38; // edi
  GUID *p_guidPropertySet; // esi
  struct tagDBPROPSET *v40; // ebx
  int *v41; // ecx
  GUID *v42; // edx
  const GUID *v43; // ecx
  GUID *v44; // edx
  unsigned int v45; // edi
  int v46; // eax
  const GUID *v47; // ecx
  GUID *v48; // edx
  unsigned int v49; // edi
  int *v50; // ecx
  unsigned int v51; // edx
  int v52; // eax
  int v53; // ecx
  bool v54; // zf
  int v55; // ecx
  JoltProperties *v56; // esi
  unsigned int v57; // ebx
  CDBSession *v58; // eax
  signed int v59; // eax
  unsigned int v60; // ecx
  unsigned int v61; // esi
  int v62; // eax
  unsigned __int16 *v63; // ecx
  int v64; // eax
  int v65; // edi
  unsigned int *v66; // edx
  int v67; // esi
  unsigned int *v68; // eax
  CDBSession **v69; // esi
  JoltProperties *v70; // edi
  unsigned __int16 *v71; // esi
  int v72; // eax
  int v73; // ecx
  signed int Link; // eax
  int v75; // esi
  int v76; // eax
  struct tagDBID *v77; // esi
  JET_ERR v78; // eax
  struct IUnknown **v79; // esi
  CRowset *v80; // eax
  int v81; // eax
  JET_TABLEID v82; // esi
  CDBSession *v83; // ebx
  struct tagDBID *v84; // ecx
  struct tagDBCONSTRAINTDESC *v85; // edx
  CDBSession **v86; // ebx
  unsigned int i; // esi
  DBID *pConstraintID; // eax
  LPOLESTR v89; // ecx
  int v90; // eax
  int v91; // eax
  struct tagDBID **v92; // ebx
  LPOLESTR v93; // edx
  struct _GUID *v95; // [esp+0h] [ebp-4B8h]
  struct _GUID *v96; // [esp+4h] [ebp-4B4h]
  _BYTE v97[16]; // [esp+10h] [ebp-4A8h] BYREF
  int v98; // [esp+20h] [ebp-498h]
  _DWORD v100[4]; // [esp+28h] [ebp-490h] BYREF
  int v101; // [esp+38h] [ebp-480h]
  _DWORD v102[3]; // [esp+3Ch] [ebp-47Ch] BYREF
  JoltProperties *v103; // [esp+48h] [ebp-470h]
  int v104; // [esp+4Ch] [ebp-46Ch]
  struct tagDBID **v105; // [esp+50h] [ebp-468h]
  struct _GUID *v106; // [esp+54h] [ebp-464h]
  struct tagDBPROPSET *v107; // [esp+58h] [ebp-460h]
  unsigned __int16 *v108; // [esp+5Ch] [ebp-45Ch] BYREF
  unsigned int v109; // [esp+60h] [ebp-458h] BYREF
  int v110; // [esp+64h] [ebp-454h] BYREF
  unsigned __int16 *v111; // [esp+68h] [ebp-450h] BYREF
  struct IUnknown **v112; // [esp+6Ch] [ebp-44Ch]
  JET_DBID dbid; // [esp+70h] [ebp-448h] BYREF
  struct IUnknown *v114; // [esp+74h] [ebp-444h] BYREF
  unsigned __int16 *v115; // [esp+78h] [ebp-440h] BYREF
  CRowset *v116; // [esp+7Ch] [ebp-43Ch]
  int v117; // [esp+80h] [ebp-438h]
  int v118; // [esp+84h] [ebp-434h]
  struct tagDBCONSTRAINTDESC *v119; // [esp+88h] [ebp-430h]
  int v120; // [esp+8Ch] [ebp-42Ch]
  unsigned int v121; // [esp+90h] [ebp-428h] BYREF
  JET_TABLEID tableid; // [esp+94h] [ebp-424h] BYREF
  CImpITableDef *v123; // [esp+98h] [ebp-420h]
  struct tagDBID *v124; // [esp+9Ch] [ebp-41Ch]
  CDBSession **v125; // [esp+A0h] [ebp-418h]
  unsigned int v126[261]; // [esp+A4h] [ebp-414h] BYREF

  v12 = this;
  v123 = this;
  v13 = a3;
  v119 = a7;
  v114 = a2;
  v106 = a8;
  v124 = a3;
  v110 = (int)a5;
  v107 = a10;
  v105 = a11;
  v112 = a12;
  v121 = 0;
  v116 = 0;
  tableid = -1;
  memset(&v100[1], 0, 12);
  v100[0] = &CRowsetProperties::`vftable';
  v101 = 0;
  v126[260] = 1;
  v102[1] = 0;
  v102[2] = 0;
  v103 = 0;
  v102[0] = &CAlterTableTableProperties::`vftable';
  v108 = 0;
  v111 = 0;
  dbid = 0;
  v120 = 0;
  v118 = 0;
  v104 = 0;
  v117 = 0;
  if ( a12 )
    *a12 = 0;
  if ( a11 )
    *a11 = 0;
  if ( !a3 && !a11 || a4 && !a5 || a9 && !a10 || a6 && !v119 )
  {
LABEL_13:
    v14 = *((_DWORD *)v12 + 2);
    v15 = (CDBSession **)((char *)v12 + 8);
    v16 = -2147024809;
    v17 = *(_DWORD *)(v14 + 20);
    v18 = *(_DWORD *)(v14 + 16);
LABEL_167:
    v26 = v15;
    v125 = v15;
    if ( JetGetDatabaseInfo(v18, v17, &v114, 4, 3) )
      goto LABEL_170;
    CExtError::SendHRtoOLEAuto((int)&IID_ITableDefinition, 0, v95, (int)v96);
    goto LABEL_169;
  }
  v19 = 0;
  if ( a6 )
  {
    do
    {
      v12 = v123;
      if ( v119[v19].cColumns )
      {
        v13 = v124;
        if ( !v119[v19].rgColumnList )
          goto LABEL_13;
      }
      v12 = v123;
      if ( v119[v19].cForeignKeyColumns )
      {
        v13 = v124;
        if ( !v119[v19].rgForeignKeyColumnList )
          goto LABEL_13;
      }
    }
    while ( ++v19 < a6 );
  }
  v20 = 0;
  if ( a9 )
  {
    while ( v107[v20].rgProperties || !v107[v20].cProperties )
    {
      if ( ++v20 >= a9 )
        goto LABEL_24;
    }
    goto LABEL_13;
  }
LABEL_24:
  if ( v114 )
  {
    v21 = v106;
    v22 = &IID_IUnknown;
    v23 = 12;
    while ( v22->Data1 == v21->Data1 )
    {
      v22 = (GUID *)((char *)v22 + 4);
      v21 = (struct _GUID *)((char *)v21 + 4);
      v24 = v23 < 4;
      v23 -= 4;
      if ( v24 )
        goto LABEL_28;
    }
    v16 = -2147217886;
    v15 = (CDBSession **)((char *)v123 + 8);
    v27 = *((_DWORD *)v123 + 2);
    v17 = *(_DWORD *)(v27 + 20);
    v18 = *(_DWORD *)(v27 + 16);
    goto LABEL_167;
  }
LABEL_28:
  v16 = CSettableProperties::FInit((CSettableProperties *)v100);
  if ( v16 < 0 )
    goto LABEL_166;
  v16 = CSettableProperties::FInit((CSettableProperties *)v102);
  if ( v16 < 0 )
    goto LABEL_166;
  if ( !v13 )
  {
    v13 = (struct tagDBID *)v97;
    v124 = (struct tagDBID *)v97;
    v25 = *(_DWORD *)Sys;
    v98 = 2;
    if ( !(*(int (__thiscall **)(_DWORD, int, int))(v25 + 12))(*(_DWORD *)(v25 + 12), Sys, 128) )
    {
      v16 = -2147024882;
      v26 = (CDBSession **)((char *)v123 + 8);
LABEL_169:
      v125 = v26;
      goto LABEL_170;
    }
    v104 = 1;
    GenerateRandomName((unsigned __int16 *)v95, (unsigned int)v96);
  }
  if ( v13->eKind != 2 || !v13->uName.ulPropid )
  {
    v16 = -2147217860;
    v15 = (CDBSession **)((char *)v123 + 8);
    v91 = *((_DWORD *)v123 + 2);
    v17 = *(_DWORD *)(v91 + 20);
    v18 = *(_DWORD *)(v91 + 16);
    goto LABEL_167;
  }
  v28 = v105;
  if ( v105 )
  {
    v29 = (*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(*(_DWORD *)(*(_DWORD *)Sys + 12), Sys, 24);
    *v28 = v29;
    if ( !v29 )
    {
      v16 = -2147024882;
      v26 = (CDBSession **)((char *)v123 + 8);
      goto LABEL_169;
    }
    pwszName = v13->uName.pwszName;
    v31 = pwszName + 1;
    while ( *pwszName++ )
      ;
    *(_DWORD *)(v29 + 16) = 2;
    v33 = (unsigned __int16 *)(2 * (pwszName - v31) + 2);
    v34 = (*(int (__thiscall **)(_DWORD, int, unsigned __int16 *))(*(_DWORD *)Sys + 12))(
            *(_DWORD *)(*(_DWORD *)Sys + 12),
            Sys,
            v33);
    v35 = v105;
    (*v105)->uName.ulPropid = v34;
    if ( !(*v35)->uName.ulPropid )
    {
      v16 = -2147024882;
      v26 = (CDBSession **)((char *)v123 + 8);
      goto LABEL_169;
    }
    WCSCPY(v33, (const unsigned __int16 *)v95, (unsigned int)v96);
  }
  v16 = CTableProperties::CopyPropertiesFromStaticTable(
          (CTableProperties *)v102,
          (const struct DBInfoProps *)&rgDBInfoProps);
  if ( v16 < 0
    || (v16 = CRowsetProperties::CopyPropertiesFromStaticTable(
                (CRowsetProperties *)v100,
                (const struct DBInfoProps *)&rgDBInfoProps),
        v16 < 0) )
  {
LABEL_166:
    v15 = (CDBSession **)((char *)v123 + 8);
    v26 = (CDBSession **)((char *)v123 + 8);
    v125 = (CDBSession **)((char *)v123 + 8);
    v81 = *((_DWORD *)v123 + 2);
    v17 = *(_DWORD *)(v81 + 20);
    v18 = *(_DWORD *)(v81 + 16);
    if ( v16 == -2147024882 )
      goto LABEL_170;
    goto LABEL_167;
  }
  v36 = 0;
  v37 = (CDBSession **)((char *)v123 + 8);
  v115 = 0;
  v125 = (CDBSession **)((char *)v123 + 8);
  v101 = *(_DWORD *)(*((_DWORD *)v123 + 2) + 84) + 152;
  if ( a9 )
  {
    do
    {
      v38 = 12;
      p_guidPropertySet = &v107[(_DWORD)v36].guidPropertySet;
      v40 = &v107[(_DWORD)v36];
      v41 = dword_10008D40;
      v42 = p_guidPropertySet;
      while ( *v41 == v42->Data1 )
      {
        ++v41;
        v42 = (GUID *)((char *)v42 + 4);
        v24 = v38 < 4;
        v38 -= 4;
        if ( v24 )
        {
LABEL_55:
          v46 = CSettableProperties::SetProperties((CSettableProperties *)v102, 1u, v40, 0);
          goto LABEL_65;
        }
      }
      v43 = &DBPROPSET_TABLE;
      v44 = p_guidPropertySet;
      v45 = 12;
      while ( v43->Data1 == v44->Data1 )
      {
        v43 = (const GUID *)((char *)v43 + 4);
        v44 = (GUID *)((char *)v44 + 4);
        v24 = v45 < 4;
        v45 -= 4;
        if ( v24 )
          goto LABEL_55;
      }
      v47 = &DBPROPSET_ROWSET;
      v48 = p_guidPropertySet;
      v49 = 12;
      while ( v47->Data1 == v48->Data1 )
      {
        v47 = (const GUID *)((char *)v47 + 4);
        v48 = (GUID *)((char *)v48 + 4);
        v24 = v49 < 4;
        v49 -= 4;
        if ( v24 )
        {
LABEL_63:
          v46 = CSettableProperties::SetProperties((CSettableProperties *)v100, 1u, v40, 0);
          goto LABEL_65;
        }
      }
      v50 = dword_10008D50;
      v51 = 12;
      while ( *v50 == p_guidPropertySet->Data1 )
      {
        ++v50;
        p_guidPropertySet = (GUID *)((char *)p_guidPropertySet + 4);
        v24 = v51 < 4;
        v51 -= 4;
        if ( v24 )
          goto LABEL_63;
      }
      v46 = SetPropSetNotSupported(0, (unsigned int)v95, (int *)v96);
LABEL_65:
      if ( v46 >= 0 )
      {
        v53 = v120;
        v54 = v46 == 265946;
        v52 = 1;
        if ( v54 )
          v53 = 1;
        v118 = 1;
      }
      else
      {
        v52 = v118;
        v53 = 1;
      }
      v36 = (unsigned __int16 *)((char *)v115 + 1);
      v120 = v53;
      v115 = v36;
    }
    while ( (unsigned int)v36 < a9 );
    v120 = v53;
    v118 = v52;
    if ( v53 == 1 )
    {
      v120 = 1;
      v55 = v52;
      v118 = v52;
      if ( !v52 )
      {
LABEL_157:
        v16 = -2147217887;
        if ( v55 == 1 )
          v16 = 265946;
        goto LABEL_159;
      }
    }
    v37 = v125;
  }
  v56 = v103;
  JoltProperties::IsbPropertySet(v103, 0xF7u, (int *)&v109);
  v57 = v109;
  if ( !v109 )
  {
    v58 = *v37;
    v16 = 0;
    v59 = JetCreateTable(*((_DWORD *)v58 + 4), *((_DWORD *)v58 + 5), v124->uName.ulPropid, 0, 0, &tableid);
    v121 = v59;
    if ( v59 > -1011 )
    {
      if ( v59 == -1002 )
      {
        v16 = -2147217860;
        goto LABEL_88;
      }
      if ( !v59 || v59 == 5011 )
      {
LABEL_89:
        if ( v16 >= 0 )
        {
          v61 = 0;
          v117 = 1;
          if ( a4 )
          {
            while ( 1 )
            {
              v62 = CImpITableDef::InternalAddColumn(
                      v123,
                      tableid,
                      (const struct tagDBCOLUMNDESC *)(v110 + 52 * v61),
                      v124->uName.pwszName,
                      (int *)&v121);
              v16 = v62;
              v117 = 1;
              if ( v62 < 0 )
                goto LABEL_159;
              if ( v62 == 265946 )
              {
                v118 = 1;
                v120 = 1;
              }
              ++v61;
              v117 = 1;
              if ( v61 >= a4 )
                goto LABEL_131;
            }
          }
          goto LABEL_131;
        }
LABEL_159:
        v26 = v125;
        goto LABEL_163;
      }
    }
    else
    {
      switch ( v59 )
      {
        case -1011:
          v16 = -2147024882;
          goto LABEL_88;
        case -1907:
        case -1809:
          v16 = -2147217911;
          goto LABEL_88;
        case -1303:
          v16 = -2147217857;
LABEL_88:
          tableid = -1;
          goto LABEL_89;
      }
    }
    v16 = -2147467259;
    goto LABEL_88;
  }
  v110 = 0;
  v115 = 0;
  if ( a4 || v112 )
  {
    v16 = -2147024809;
    v15 = (CDBSession **)((char *)v123 + 8);
    v90 = *((_DWORD *)v123 + 2);
    v17 = *(_DWORD *)(v90 + 20);
    v18 = *(_DWORD *)(v90 + 16);
    goto LABEL_167;
  }
  JoltProperties::GetStrValue(v56, 0xF4u, &v115);
  JoltProperties::GetStrValue(v56, 0xF5u, &v108);
  v63 = v115;
  if ( !v108 && !v115 )
  {
    v16 = -2147217887;
    v15 = (CDBSession **)((char *)v123 + 8);
    v64 = *((_DWORD *)v123 + 2);
    v17 = *(_DWORD *)(v64 + 20);
    v18 = *(_DWORD *)(v64 + 16);
    goto LABEL_167;
  }
  LOWORD(v126[0]) = 0;
  if ( v115 )
  {
    v65 = 2147483646;
    v66 = v126;
    v67 = 513;
    do
    {
      if ( !v65 )
        break;
      if ( !*v63 )
        break;
      *(_WORD *)v66 = *v63++;
      v66 = (unsigned int *)((char *)v66 + 2);
      --v65;
      --v67;
    }
    while ( v67 );
    v68 = (unsigned int *)((char *)v66 - 2);
    if ( v67 )
      v68 = v66;
    *(_WORD *)v68 = 0;
  }
  v69 = v125;
  v16 = CJOLT::JOLTJetOpenDatabase(
          (unsigned int)v126,
          (const unsigned __int16 *)&dbid,
          0,
          &v121,
          (unsigned int)v95,
          (int *)v96);
  if ( v16 < 0 )
  {
    if ( v121 != -1031 && v121 != -1024 )
    {
      v26 = v69;
      goto LABEL_163;
    }
    v16 = CJOLT::JOLTJetOpenDatabase(
            (unsigned int)v126,
            (const unsigned __int16 *)&dbid,
            (const unsigned __int16 *)3,
            &v121,
            (unsigned int)v95,
            (int *)v96);
    if ( v16 < 0 )
      goto LABEL_159;
  }
  v70 = v103;
  JoltProperties::GetStrValue(v103, 0xF3u, &v111);
  v71 = v111;
  if ( !v111 || !*v111 )
  {
    v26 = v125;
    v16 = -2147217887;
    goto LABEL_163;
  }
  JoltProperties::IsbPropertySet(v70, 0xF6u, (int *)&v111);
  v72 = JoltProperties::IsbPropertySet(v70, 0xF0u, &v110);
  v73 = 0;
  v16 = v72;
  if ( v111 == (unsigned __int16 *)1 )
    v73 = 0x40000000;
  if ( v110 == 1 )
    v73 |= 0x20000000u;
  v26 = v125;
  Link = JetCreateLink(*((_DWORD *)*v125 + 4), *((_DWORD *)*v125 + 5), v124->uName.ulPropid, dbid, v71, v73);
  v121 = Link;
  if ( Link <= -1314 )
  {
    if ( Link == -1314 )
    {
      v16 = -2147217857;
      goto LABEL_163;
    }
    if ( Link != -2001 && (Link == -1907 || Link == -1809) )
    {
      v16 = -2147217911;
      goto LABEL_163;
    }
    goto LABEL_129;
  }
  if ( Link == -1305 || Link == -1002 )
  {
    v16 = -2147217860;
    goto LABEL_163;
  }
  if ( Link )
  {
LABEL_129:
    v16 = -2147467259;
    goto LABEL_163;
  }
  v57 = v109;
  v117 = 1;
LABEL_131:
  v75 = 0;
  if ( a6 )
  {
    do
    {
      v76 = CImpITableDef::InternalAddConstraint(v123, &tableid, v124->uName.pwszName, &v119[v75], (int *)&v121);
      v16 = v76;
      if ( v76 < 0 )
        goto LABEL_159;
      if ( v76 == 265946 )
      {
        v118 = 1;
        v120 = 1;
      }
    }
    while ( ++v75 < a6 );
  }
  v54 = v57 == 0;
  v26 = v125;
  if ( !v54
    || (v77 = v124,
        v16 = CTableProperties::SetPropertiesToJetPropertyManager(
                (CTableProperties *)v102,
                *((_DWORD *)*v125 + 4),
                v60,
                *((_DWORD *)*v125 + 5),
                v124->uName.pwszName),
        v16 >= 0)
    && (v16 = CTableProperties::SetPropertiesInMSysObjects(
                (CTableProperties *)v102,
                *((_DWORD *)*v26 + 4),
                *((_DWORD *)*v26 + 5),
                v77->uName.pwszName,
                (int *)&v121),
        v16 >= 0) )
  {
    if ( tableid != -1 )
    {
      v78 = JetCloseTable(*((_DWORD *)*v26 + 4), tableid);
      v121 = v78;
      if ( v78 < 0 )
      {
        if ( v78 == -1108 )
        {
          v16 = CDBSession::AddJetTableId(*v26, tableid);
          if ( v16 >= 0 )
          {
            tableid = -1;
            v16 = -2147217856;
          }
          goto LABEL_163;
        }
        goto LABEL_129;
      }
      tableid = -1;
    }
    v79 = v112;
    if ( v112 )
    {
      v80 = (CRowset *)operator new(0xF0u);
      v109 = (unsigned int)v80;
      if ( v80 )
      {
        v116 = CRowset::CRowset(v80, v114);
        if ( v116 )
        {
          CRowsetProperties::ValidateStateForJetOpenTable(
            (CRowsetProperties *)v100,
            &v109,
            v106,
            (enum eJetCursorType *)&v114,
            1);
          v16 = CRowset::FInit(
                  v116,
                  0,
                  *v26,
                  0,
                  v124->uName.ulPropid,
                  0,
                  tableid,
                  v100,
                  v114,
                  0,
                  0,
                  0,
                  0,
                  a9,
                  v107,
                  &GUID_NULL);
          if ( v16 < 0 )
          {
            *v79 = 0;
            goto LABEL_163;
          }
          v16 = (**(int (__thiscall ***)(_DWORD, CRowset *, struct _GUID *, struct IUnknown **))v116)(
                  **(_DWORD **)v116,
                  v116,
                  v106,
                  v112);
          if ( v16 < 0 )
            goto LABEL_163;
          goto LABEL_155;
        }
      }
      else
      {
        v116 = 0;
      }
      v16 = -2147024882;
      goto LABEL_163;
    }
    if ( v16 < 0 )
      goto LABEL_163;
LABEL_155:
    if ( v120 != 1 )
      goto LABEL_163;
    v55 = v118;
    goto LABEL_157;
  }
LABEL_163:
  if ( v121 )
  {
    CExtError::SendJetErrortoOLEAuto(v121, (int)&IID_ITableDefinition, (int)v95, v96);
    goto LABEL_170;
  }
  v125 = v26;
  if ( v16 < 0 )
    goto LABEL_166;
LABEL_170:
  if ( dbid )
    JetCloseDatabase(*((_DWORD *)*v26 + 4), dbid, 0);
  if ( v16 >= 0 )
    goto LABEL_208;
  if ( v116 )
    (*(void (__thiscall **)(CRowset *, int))(*(_DWORD *)v116 + 12))(v116, 1);
  if ( v112 && *v112 )
    *v112 = 0;
  v82 = tableid;
  if ( tableid == -1 )
  {
    v84 = v124;
LABEL_197:
    v86 = v125;
    goto LABEL_198;
  }
  v83 = *v26;
  if ( JetCloseTable(*((_DWORD *)v83 + 4), tableid) == -1108 )
    CDBSession::AddJetTableId(v83, v82);
  v84 = v124;
  if ( !a6 )
    goto LABEL_197;
  v85 = v119;
  if ( !v119 || !v124 || v124->eKind != 2 )
    goto LABEL_197;
  v86 = v125;
  if ( v124->uName.ulPropid )
  {
    for ( i = 0; i < a6; ++i )
    {
      if ( v85[i].ConstraintType == 1 )
      {
        pConstraintID = v85[i].pConstraintID;
        if ( pConstraintID )
        {
          if ( pConstraintID->eKind == 2 )
          {
            v89 = pConstraintID->uName.pwszName;
            if ( v89 )
            {
              JetDeleteRelationship(*((_DWORD *)*v86 + 4), *((_DWORD *)*v86 + 5), v89);
              v85 = v119;
            }
          }
        }
      }
    }
    v84 = v124;
  }
LABEL_198:
  if ( v117 == 1 )
    JetDeleteTable(*((_DWORD *)*v86 + 4), *((_DWORD *)*v86 + 5), v84->uName.ulPropid);
  v92 = v105;
  if ( v105 && *v105 )
  {
    v93 = (*v105)->uName.pwszName;
    if ( v93 )
    {
      if ( !Sys )
      {
LABEL_207:
        *v92 = 0;
        goto LABEL_208;
      }
      (*(void (__thiscall **)(_DWORD, int, LPOLESTR))(*(_DWORD *)Sys + 20))(*(_DWORD *)(*(_DWORD *)Sys + 20), Sys, v93);
    }
    if ( Sys )
      (*(void (__thiscall **)(_DWORD, int, struct tagDBID *))(*(_DWORD *)Sys + 20))(
        *(_DWORD *)(*(_DWORD *)Sys + 20),
        Sys,
        *v92);
    goto LABEL_207;
  }
LABEL_208:
  if ( v104 == 1 && v124->uName.ulPropid && Sys )
    (*(void (__thiscall **)(_DWORD, int, ULONG))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v124->uName.ulPropid);
  CSettableProperties::~CSettableProperties((CSettableProperties *)v102);
  CSettableProperties::~CSettableProperties((CSettableProperties *)v100);
  return v16;
}

```

## disassembly

```asm
0x10044ee0  mov     edi, edi
0x10044ee2  push    ebp
0x10044ee3  mov     ebp, esp
0x10044ee5  push    0FFFFFFFFh
0x10044ee7  push    offset ?InternalCreateTable@CImpITableDef@@QAEJPAUIUnknown@@PAUtagDBID@@KQBUtagDBCOLUMNDESC@@KQAUtagDBCONSTRAINTDESC@@ABU_GUID@@KQAUtagDBPROPSET@@PAPAU3@PAPAU2@@Z_SEH
0x10044eec  mov     eax, large fs:0
0x10044ef2  push    eax
0x10044ef3  sub     esp, 49Ch
0x10044ef9  mov     eax, ___security_cookie
0x10044efe  xor     eax, ebp
0x10044f00  mov     [ebp+var_10], eax
0x10044f03  push    ebx
0x10044f04  push    esi
0x10044f05  push    edi; int
0x10044f06  push    eax; struct _GUID *
0x10044f07  lea     eax, [ebp+var_C]
0x10044f0a  mov     large fs:0, eax
0x10044f10  mov     edx, ecx
0x10044f12  mov     [ebp+var_420], edx
0x10044f18  mov     ecx, [ebp+arg_14]
0x10044f1b  mov     eax, [ebp+arg_0]
0x10044f1e  mov     ebx, [ebp+arg_4]
0x10044f21  mov     edi, [ebp+arg_24]
0x10044f24  mov     esi, [ebp+arg_28]
0x10044f27  mov     [ebp+var_430], ecx
0x10044f2d  mov     ecx, [ebp+arg_18]
0x10044f30  mov     [ebp+var_444], eax
0x10044f36  mov     eax, [ebp+arg_C]
0x10044f39  mov     [ebp+var_464], ecx
0x10044f3f  mov     ecx, [ebp+arg_20]
0x10044f42  mov     [ebp+var_41C], ebx
0x10044f48  mov     [ebp+var_454], eax
0x10044f4e  mov     [ebp+var_460], ecx
0x10044f54  mov     [ebp+var_468], edi
0x10044f5a  mov     [ebp+var_44C], esi
0x10044f60  mov     [ebp+var_428], 0
0x10044f6a  mov     [ebp+var_43C], 0
0x10044f74  mov     [ebp+tableid], 0FFFFFFFFh
0x10044f7e  mov     [ebp+var_48C], 0
0x10044f88  mov     [ebp+var_488], 0
0x10044f92  mov     [ebp+var_484], 0
0x10044f9c  mov     [ebp+var_490], offset ??_7CRowsetProperties@@6B@; const CRowsetProperties::`vftable'
0x10044fa6  mov     [ebp+var_480], 0
0x10044fb0  mov     [ebp+var_4], 0
0x10044fb7  mov     [ebp+var_478], 0
0x10044fc1  mov     [ebp+var_474], 0
0x10044fcb  mov     [ebp+var_470], 0
0x10044fd5  mov     [ebp+var_47C], offset ??_7CAlterTableTableProperties@@6B@; const CAlterTableTableProperties::`vftable'
0x10044fdf  mov     byte ptr [ebp+var_4], 1
0x10044fe3  mov     [ebp+var_45C], 0
0x10044fed  mov     [ebp+var_450], 0
0x10044ff7  mov     [ebp+dbid], 0
0x10045001  mov     [ebp+var_42C], 0
0x1004500b  mov     [ebp+var_434], 0
0x10045015  mov     [ebp+var_46C], 0
0x1004501f  mov     [ebp+var_438], 0
0x10045029  test    esi, esi
0x1004502b  jz      short loc_10045033
0x1004502d  mov     dword ptr [esi], 0
0x10045033  test    edi, edi
0x10045035  jz      short loc_1004503D
0x10045037  mov     dword ptr [edi], 0
0x1004503d  mov     esi, [ebp+arg_10]
0x10045040  test    ebx, ebx
0x10045042  jnz     short loc_10045048
0x10045044  test    edi, edi
0x10045046  jz      short loc_1004506A
0x10045048  cmp     [ebp+arg_8], 0
0x1004504c  jz      short loc_10045052
0x1004504e  test    eax, eax
0x10045050  jz      short loc_1004506A
0x10045052  mov     edi, [ebp+arg_1C]
0x10045055  test    edi, edi
0x10045057  jz      short loc_1004505D
0x10045059  test    ecx, ecx
0x1004505b  jz      short loc_1004506A
0x1004505d  test    esi, esi
0x1004505f  jz      short loc_10045080
0x10045061  cmp     [ebp+var_430], 0
0x10045068  jnz     short loc_10045080
0x1004506a  mov     eax, [edx+8]
0x1004506d  lea     esi, [edx+8]
0x10045070  mov     edi, 80070057h
0x10045075  mov     ecx, [eax+14h]
0x10045078  mov     eax, [eax+10h]
0x1004507b  jmp     loc_10045AB2
0x10045080  xor     ecx, ecx
0x10045082  test    esi, esi
0x10045084  jz      short loc_100450EA
0x10045086  nop     word ptr [eax+eax+00000000h]
0x10045090  mov     edx, [ebp+var_430]
0x10045096  lea     eax, ds:0[ecx*8]
0x1004509d  sub     eax, ecx
0x1004509f  cmp     dword ptr [edx+eax*8+8], 0
0x100450a4  mov     edx, [ebp+var_420]
0x100450aa  jz      short loc_100450BF
0x100450ac  mov     ebx, [ebp+var_430]
0x100450b2  cmp     dword ptr [ebx+eax*8+0Ch], 0
0x100450b7  mov     ebx, [ebp+var_41C]
0x100450bd  jz      short loc_1004506A
0x100450bf  mov     edx, [ebp+var_430]
0x100450c5  cmp     dword ptr [edx+eax*8+14h], 0
0x100450ca  mov     edx, [ebp+var_420]
0x100450d0  jz      short loc_100450E5
0x100450d2  mov     ebx, [ebp+var_430]
0x100450d8  cmp     dword ptr [ebx+eax*8+18h], 0
0x100450dd  mov     ebx, [ebp+var_41C]
0x100450e3  jz      short loc_1004506A
0x100450e5  inc     ecx
0x100450e6  cmp     ecx, esi
0x100450e8  jb      short loc_10045090
0x100450ea  xor     ecx, ecx
0x100450ec  test    edi, edi
0x100450ee  jz      short loc_1004510F
0x100450f0  mov     esi, [ebp+var_460]
0x100450f6  lea     eax, [ecx+ecx*2]
0x100450f9  cmp     dword ptr [esi+eax*8], 0
0x100450fd  jnz     short loc_1004510A
0x100450ff  cmp     dword ptr [esi+eax*8+4], 0
0x10045104  jnz     loc_1004506A
0x1004510a  inc     ecx
0x1004510b  cmp     ecx, edi
0x1004510d  jb      short loc_100450F6
0x1004510f  cmp     [ebp+var_444], 0
0x10045116  jz      short loc_10045145
0x10045118  mov     edx, [ebp+var_464]
0x1004511e  mov     ecx, offset _IID_IUnknown
0x10045123  mov     esi, 0Ch
0x10045128  nop     dword ptr [eax+eax+00000000h]
0x10045130  mov     eax, [ecx]
0x10045132  cmp     eax, [edx]
0x10045134  jnz     loc_100451C1
0x1004513a  add     ecx, 4
0x1004513d  add     edx, 4
0x10045140  sub     esi, 4
0x10045143  jnb     short loc_10045130
0x10045145  lea     ecx, [ebp+var_490]; this
0x1004514b  call    ?FInit@CSettableProperties@@QAEJXZ; CSettableProperties::FInit(void)
0x10045150  mov     edi, eax
0x10045152  test    edi, edi
0x10045154  js      loc_10045A91
0x1004515a  lea     ecx, [ebp+var_47C]; this
0x10045160  call    ?FInit@CSettableProperties@@QAEJXZ; CSettableProperties::FInit(void)
0x10045165  mov     edi, eax
0x10045167  test    edi, edi
0x10045169  js      loc_10045A91
0x1004516f  test    ebx, ebx
0x10045171  jnz     short loc_100451ED
0x10045173  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10045179  lea     ebx, [ebp+var_4A8]
0x1004517f  push    80h
0x10045184  push    ecx
0x10045185  mov     [ebp+var_41C], ebx
0x1004518b  mov     eax, [ecx]
0x1004518d  mov     [ebp+var_498], 2
0x10045197  mov     esi, [eax+0Ch]
0x1004519a  mov     ecx, esi
0x1004519c  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100451a2  call    esi
0x100451a4  mov     [ebp+var_494], eax
0x100451aa  test    eax, eax
0x100451ac  jnz     short loc_100451DC
0x100451ae  mov     ebx, [ebp+var_420]
0x100451b4  mov     edi, 8007000Eh
0x100451b9  add     ebx, 8
0x100451bc  jmp     loc_10045ADE
0x100451c1  mov     esi, [ebp+var_420]
0x100451c7  mov     edi, 80040E22h
0x100451cc  add     esi, 8
0x100451cf  mov     eax, [esi]
0x100451d1  mov     ecx, [eax+14h]
0x100451d4  mov     eax, [eax+10h]
0x100451d7  jmp     loc_10045AB2
0x100451dc  mov     ecx, eax
0x100451de  mov     [ebp+var_46C], 1
0x100451e8  call    ?GenerateRandomName@@YGJPAGK@Z; GenerateRandomName(ushort *,ulong)
0x100451ed  cmp     dword ptr [ebx+10h], 2
0x100451f1  jnz     loc_10045C12
0x100451f7  cmp     dword ptr [ebx+14h], 0
0x100451fb  jz      loc_10045C12
0x10045201  mov     edi, [ebp+var_468]
0x10045207  test    edi, edi
0x10045209  jz      loc_100452B4
0x1004520f  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10045215  push    18h
0x10045217  push    ecx
0x10045218  mov     eax, [ecx]
0x1004521a  mov     esi, [eax+0Ch]
0x1004521d  mov     ecx, esi
0x1004521f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10045225  call    esi
0x10045227  mov     edx, eax
0x10045229  mov     [edi], edx
0x1004522b  test    edx, edx
0x1004522d  jnz     short loc_10045242
0x1004522f  mov     ebx, [ebp+var_420]
0x10045235  mov     edi, 8007000Eh
0x1004523a  add     ebx, 8
0x1004523d  jmp     loc_10045ADE
0x10045242  mov     ecx, [ebx+14h]
0x10045245  lea     esi, [ecx+2]
0x10045248  nop     dword ptr [eax+eax+00000000h]
0x10045250  mov     ax, [ecx]
0x10045253  add     ecx, 2
0x10045256  test    ax, ax
0x10045259  jnz     short loc_10045250
0x1004525b  sub     ecx, esi
0x1004525d  mov     dword ptr [edx+10h], 2
0x10045264  sar     ecx, 1
0x10045266  lea     edi, ds:2[ecx*2]
0x1004526d  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10045273  push    edi
0x10045274  push    ecx
0x10045275  mov     eax, [ecx]
0x10045277  mov     esi, [eax+0Ch]
0x1004527a  mov     ecx, esi
0x1004527c  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10045282  call    esi
0x10045284  mov     edx, [ebp+var_468]
0x1004528a  mov     ecx, [edx]
0x1004528c  mov     [ecx+14h], eax
0x1004528f  mov     eax, [edx]
0x10045291  mov     ecx, [eax+14h]
0x10045294  test    ecx, ecx
0x10045296  jnz     short loc_100452AB
0x10045298  mov     ebx, [ebp+var_420]
0x1004529e  mov     edi, 8007000Eh
0x100452a3  add     ebx, 8
0x100452a6  jmp     loc_10045ADE
0x100452ab  mov     edx, [ebx+14h]
0x100452ae  push    edi; unsigned __int16 *
0x100452af  call    ?WCSCPY@@YGPAGPAGPBGI@Z; WCSCPY(ushort *,ushort const *,uint)
0x100452b4  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; struct DBInfoProps *
0x100452b9  lea     ecx, [ebp+var_47C]; this
0x100452bf  call    ?CopyPropertiesFromStaticTable@CTableProperties@@QAEJPBUDBInfoProps@@@Z; CTableProperties::CopyPropertiesFromStaticTable(DBInfoProps const *)
0x100452c4  mov     edi, eax
0x100452c6  test    edi, edi
0x100452c8  js      loc_10045A91
0x100452ce  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; struct DBInfoProps *
0x100452d3  lea     ecx, [ebp+var_490]; this
0x100452d9  call    ?CopyPropertiesFromStaticTable@CRowsetProperties@@QAEJPBUDBInfoProps@@@Z; CRowsetProperties::CopyPropertiesFromStaticTable(DBInfoProps const *)
0x100452de  mov     edi, eax
0x100452e0  test    edi, edi
0x100452e2  js      loc_10045A91
0x100452e8  mov     edi, [ebp+var_420]
0x100452ee  xor     edx, edx
0x100452f0  add     edi, 8
0x100452f3  mov     [ebp+var_440], edx
0x100452f9  mov     [ebp+var_418], edi
0x100452ff  mov     eax, [edi]
0x10045301  mov     eax, [eax+54h]
0x10045304  add     eax, 98h
0x10045309  mov     [ebp+var_480], eax
0x1004530f  cmp     [ebp+arg_1C], edx
0x10045312  jbe     loc_1004545C
0x10045318  nop     dword ptr [eax+eax+00000000h]
0x10045320  mov     ecx, [ebp+var_460]
0x10045326  lea     eax, [edx+edx*2]
0x10045329  shl     eax, 3
0x1004532c  mov     edi, 0Ch
0x10045331  lea     esi, [ecx+8]
0x10045334  add     esi, eax
0x10045336  lea     ebx, [eax+ecx]
0x10045339  mov     ecx, offset dword_10008D40
0x1004533e  mov     edx, esi
0x10045340  mov     eax, [ecx]
0x10045342  cmp     eax, [edx]
0x10045344  jnz     short loc_10045353
0x10045346  add     ecx, 4
0x10045349  add     edx, 4
0x1004534c  sub     edi, 4
0x1004534f  jnb     short loc_10045340
0x10045351  jmp     short loc_10045371
0x10045353  mov     ecx, offset _DBPROPSET_TABLE
0x10045358  mov     edx, esi
0x1004535a  mov     edi, 0Ch
0x1004535f  nop
0x10045360  mov     eax, [ecx]
0x10045362  cmp     eax, [edx]
0x10045364  jnz     short loc_10045388
0x10045366  add     ecx, 4
0x10045369  add     edx, 4
0x1004536c  sub     edi, 4
0x1004536f  jnb     short loc_10045360
0x10045371  push    0; struct CDBSession *
0x10045373  push    ebx; struct tagDBPROPSET *
0x10045374  push    1; unsigned int
0x10045376  lea     ecx, [ebp+var_47C]; this
0x1004537c  call    ?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z; CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)
0x10045381  mov     esi, 1
0x10045386  jmp     short loc_100453E9
0x10045388  mov     ecx, offset _DBPROPSET_ROWSET
0x1004538d  mov     edx, esi
0x1004538f  mov     edi, 0Ch
0x10045394  mov     eax, [ecx]
0x10045396  cmp     eax, [edx]
0x10045398  jnz     short loc_100453A7
0x1004539a  add     ecx, 4
0x1004539d  add     edx, 4
0x100453a0  sub     edi, 4
  ... truncated ...
```
