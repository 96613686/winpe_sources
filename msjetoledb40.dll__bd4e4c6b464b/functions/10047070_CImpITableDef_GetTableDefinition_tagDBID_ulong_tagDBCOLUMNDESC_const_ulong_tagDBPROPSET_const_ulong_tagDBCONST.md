# CImpITableDef::GetTableDefinition(tagDBID *,ulong *,tagDBCOLUMNDESC * * const,ulong *,tagDBPROPSET * * const,ulong *,tagDBCONSTRAINTDESC * * const,ushort * *)

- ea: `0x10047070`
- end: `0x10048dbc`
- name: `?GetTableDefinition@CImpITableDef@@UAGJPAUtagDBID@@PAKQAPAUtagDBCOLUMNDESC@@1QAPAUtagDBPROPSET@@1QAPAUtagDBCONSTRAINTDESC@@PAPAG@Z`
- size: `7500`
- prototype: `int(CImpITableDef *__hidden this, struct tagDBID *, unsigned int *, struct tagDBCOLUMNDESC **const, unsigned int *, struct tagDBPROPSET **const, unsigned int *, struct tagDBCONSTRAINTDESC **const, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x1000ba90`
- `0x1000d4a0`
- `0x1000e8d0`
- `0x10013020`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1001eae0`
- `0x1001f2d0`
- `0x1001fbe0`
- `0x10020410`
- `0x100204c0`
- `0x10022870`
- `0x10022c40`
- `0x10023390`
- `0x10023ab0`
- `0x10047070`
- `0x10048dd0`
- `0x10048e80`
- `0x1004b560`
- `0x1004b5c0`
- `0x1004c660`
- `0x1004ce5d`
- `0x1004d406`
- `0x1004d420`
- `0x1004d5a1`
- `0x1004dc50`
- `0x1004dc8d`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1004816e`
- `msvcrt!_wcsicmp` at `0x1004816e`
- `KERNEL32!LeaveCriticalSection` at `0x10048d83`
- `KERNEL32!LeaveCriticalSection` at `0x10048d83`
- `KERNEL32!EnterCriticalSection` at `0x1004722c`
- `KERNEL32!EnterCriticalSection` at `0x1004722c`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100471a3`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100471a3`
- `msjet40!__imp__JetCloseTable@8` at `0x10047f67`
- `msjet40!__imp__JetCloseTable@8` at `0x10048c44`
- `msjet40!__imp__JetCloseTable@8` at `0x10048c5c`
- `msjet40!__imp__JetCloseTable@8` at `0x10047f67`
- `msjet40!__imp__JetCloseTable@8` at `0x10048c44`
- `msjet40!__imp__JetCloseTable@8` at `0x10048c5c`
- `msjet40!__imp__JetGetColumnInfo@28` at `0x100477d0`
- `msjet40!__imp__JetGetColumnInfo@28` at `0x10047973`
- `msjet40!__imp__JetGetColumnInfo@28` at `0x100477d0`
- `msjet40!__imp__JetGetColumnInfo@28` at `0x10047973`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10048bf4`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10048bf4`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10047e9c`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10047e9c`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x10047ed8`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x10047ed8`
- `msjet40!__imp__JetMove@16` at `0x100480c3`
- `msjet40!__imp__JetMove@16` at `0x1004818f`
- `msjet40!__imp__JetMove@16` at `0x10048443`
- `msjet40!__imp__JetMove@16` at `0x10048977`
- `msjet40!__imp__JetMove@16` at `0x100489d7`
- `msjet40!__imp__JetMove@16` at `0x100489fb`
- `msjet40!__imp__JetMove@16` at `0x100480c3`
- `msjet40!__imp__JetMove@16` at `0x1004818f`
- `msjet40!__imp__JetMove@16` at `0x10048443`
- `msjet40!__imp__JetMove@16` at `0x10048977`
- `msjet40!__imp__JetMove@16` at `0x100489d7`
- `msjet40!__imp__JetMove@16` at `0x100489fb`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10047f1b`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10048091`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10048125`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10048223`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10048385`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100484d0`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1004856d`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10048716`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100487ef`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100488c0`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10047f1b`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10048091`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10048125`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10048223`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10048385`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100484d0`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1004856d`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10048716`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100487ef`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100488c0`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x10047458`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x10047458`
- `msjet40!__imp__JetGetRelationshipInfo@24` at `0x100473ed`
- `msjet40!__imp__JetGetRelationshipInfo@24` at `0x100473ed`

## pseudocode

```c
int __stdcall CImpITableDef::GetTableDefinition(
        CImpITableDef *this,
        struct tagDBID *a2,
        unsigned int *a3,
        struct tagDBCOLUMNDESC **const a4,
        unsigned int *a5,
        struct tagDBPROPSET **const a6,
        unsigned int *a7,
        struct tagDBCONSTRAINTDESC **const a8,
        unsigned __int16 **a9)
{
  int v9; // eax
  size_t v10; // edi
  struct _RTL_CRITICAL_SECTION *v11; // esi
  unsigned int v12; // eax
  unsigned int *v13; // ecx
  ColumnData *v14; // eax
  ColumnData *v15; // ecx
  unsigned int v16; // eax
  int IndexInfo; // edi
  signed int RelationshipInfo; // eax
  signed int v19; // eax
  const unsigned __int16 *v20; // edx
  unsigned int v21; // esi
  unsigned int v22; // ecx
  bool v23; // zf
  int v24; // edx
  int v25; // eax
  ColumnData *v26; // eax
  size_t v27; // edx
  int (__thiscall *v28)(_DWORD, int, size_t); // edi
  struct tagDBCOLUMNDESC *v29; // eax
  JET_TABLEID v30; // ecx
  _DWORD *v31; // eax
  int v32; // eax
  int v33; // edi
  _WORD *v34; // ecx
  _WORD *v35; // edx
  _DWORD *v37; // ecx
  int v38; // edx
  int v39; // eax
  unsigned int ColumnInfo; // eax
  unsigned int v41; // esi
  JET_SESID v42; // ecx
  int v43; // edi
  unsigned int v44; // edx
  unsigned int v45; // eax
  int v46; // ecx
  int v47; // eax
  JoltProperties *v48; // edi
  unsigned int v49; // eax
  _DWORD *v50; // ecx
  int v51; // edx
  int v52; // eax
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  _DWORD *v55; // ecx
  unsigned __int16 *v56; // edx
  int v57; // eax
  int v58; // edi
  unsigned int v59; // eax
  _DWORD *v60; // edi
  unsigned int v61; // eax
  int v62; // eax
  int v63; // eax
  unsigned int v64; // edx
  unsigned int v65; // edi
  _DWORD *v66; // edx
  _WORD *v67; // ecx
  int v68; // eax
  int v69; // eax
  _WORD *v70; // edx
  int v72; // eax
  struct tagDBCOLUMNDESC **v73; // edx
  unsigned int v74; // edi
  unsigned __int16 *v75; // edi
  _DWORD *v76; // ecx
  unsigned __int16 *v77; // edx
  int v78; // eax
  unsigned int v79; // eax
  __int16 v80; // cx
  char v81; // al
  int v82; // eax
  unsigned int v83; // eax
  char v84; // cl
  int v85; // eax
  unsigned __int16 *v86; // ecx
  int v87; // edx
  int v88; // eax
  size_t v89; // ecx
  JET_TABLEID v90; // edx
  int (__thiscall *v91)(_DWORD, int, JET_TABLEID); // edi
  struct tagDBCONSTRAINTDESC *v92; // eax
  char *v93; // edx
  JET_TABLEID v94; // edi
  JET_ERR v95; // eax
  _DWORD *v96; // edi
  unsigned int v97; // edx
  CImpITableDef *v98; // ecx
  size_t v99; // edx
  int (__thiscall *v100)(_DWORD, int, size_t); // edi
  int v101; // eax
  struct tagDBCONSTRAINTDESC **v102; // edi
  unsigned int v103; // edx
  void *v104; // eax
  JET_TABLEID v105; // edi
  unsigned int v106; // edi
  unsigned __int16 *v107; // edx
  JET_SESID v108; // ecx
  int v109; // eax
  unsigned __int16 *v110; // eax
  JET_ERR v111; // eax
  unsigned int v112; // edx
  _DWORD *v113; // edi
  unsigned int v114; // ecx
  struct tagDBCONSTRAINTDESC **v115; // edx
  CImpITableDef *v116; // ecx
  unsigned int v117; // edx
  int (__thiscall *v118)(_DWORD, int, unsigned int); // edi
  int v119; // eax
  struct tagDBCONSTRAINTDESC **v120; // edx
  JET_SESID v121; // edi
  void *v122; // eax
  int v123; // eax
  struct tagDBCONSTRAINTDESC **v124; // edx
  JET_SESID v125; // edi
  void *v126; // eax
  size_t v127; // eax
  unsigned int v128; // ecx
  struct tagDBCONSTRAINTDESC **v129; // edx
  size_t v130; // eax
  unsigned int v131; // ecx
  size_t v132; // edi
  unsigned int v133; // edx
  struct tagDBCONSTRAINTDESC *v134; // eax
  unsigned __int16 *v135; // eax
  unsigned __int16 *v136; // edx
  unsigned __int16 *v137; // eax
  JET_TABLEID v138; // eax
  unsigned int v139; // edi
  size_t v140; // ecx
  struct tagDBCONSTRAINTDESC **v141; // edx
  struct tagDBCONSTRAINTDESC *v142; // eax
  unsigned __int16 *v143; // edx
  int v144; // edi
  unsigned int v145; // ecx
  unsigned __int16 *v146; // eax
  struct tagDBCOLUMNDESC **v147; // edx
  unsigned int v148; // esi
  int v149; // edx
  const unsigned __int16 *v151; // [esp-14h] [ebp-101D0h]
  void *v152; // [esp-10h] [ebp-101CCh]
  JET_TABLEID v153; // [esp-Ch] [ebp-101C8h]
  unsigned __int16 *v154; // [esp-8h] [ebp-101C4h]
  size_t v155; // [esp-4h] [ebp-101C0h]
  struct CSettableProperties *v156; // [esp+0h] [ebp-101BCh]
  unsigned int *v157; // [esp+0h] [ebp-101BCh]
  struct _GUID *v158; // [esp+4h] [ebp-101B8h]
  struct tagDBCONSTRAINTDESC **v159; // [esp+4h] [ebp-101B8h]
  unsigned int v160; // [esp+10h] [ebp-101ACh] BYREF
  unsigned int v161; // [esp+14h] [ebp-101A8h] BYREF
  unsigned int v162; // [esp+18h] [ebp-101A4h] BYREF
  unsigned int v163; // [esp+1Ch] [ebp-101A0h] BYREF
  unsigned int v164; // [esp+20h] [ebp-1019Ch] BYREF
  struct tagDBPROPSET *v165[3]; // [esp+24h] [ebp-10198h] BYREF
  JoltProperties *v166; // [esp+30h] [ebp-1018Ch]
  unsigned int pcbActual; // [esp+34h] [ebp-10188h] BYREF
  struct _RTL_CRITICAL_SECTION *v168; // [esp+38h] [ebp-10184h]
  struct tagDBPROPIDSET *v169; // [esp+3Ch] [ebp-10180h]
  unsigned int v170; // [esp+40h] [ebp-1017Ch]
  unsigned __int16 *v171; // [esp+44h] [ebp-10178h]
  size_t v172; // [esp+48h] [ebp-10174h]
  unsigned int v173; // [esp+4Ch] [ebp-10170h]
  size_t pvData; // [esp+50h] [ebp-1016Ch] BYREF
  int v175; // [esp+54h] [ebp-10168h]
  ColumnData *v176; // [esp+58h] [ebp-10164h]
  unsigned int *v177; // [esp+5Ch] [ebp-10160h]
  CImpITableDef *v178; // [esp+60h] [ebp-1015Ch]
  unsigned int *v179; // [esp+64h] [ebp-10158h]
  unsigned __int16 **v180; // [esp+68h] [ebp-10154h]
  unsigned int v181; // [esp+6Ch] [ebp-10150h]
  unsigned __int16 *v182; // [esp+70h] [ebp-1014Ch] BYREF
  size_t Size; // [esp+74h] [ebp-10148h] BYREF
  unsigned int v184; // [esp+78h] [ebp-10144h] BYREF
  size_t v185; // [esp+7Ch] [ebp-10140h] BYREF
  struct tagDBCOLUMNDESC **v186; // [esp+80h] [ebp-1013Ch]
  size_t v187; // [esp+84h] [ebp-10138h] BYREF
  JET_TABLEID tableid; // [esp+88h] [ebp-10134h] BYREF
  struct tagDBCONSTRAINTDESC **v189; // [esp+8Ch] [ebp-10130h]
  JET_SESID sesid; // [esp+90h] [ebp-1012Ch]
  JET_SESID v191; // [esp+94h] [ebp-10128h]
  _DWORD *v192; // [esp+98h] [ebp-10124h]
  unsigned int ObjectInfo; // [esp+9Ch] [ebp-10120h] BYREF
  unsigned int v194; // [esp+A0h] [ebp-1011Ch] BYREF
  int v195; // [esp+A4h] [ebp-10118h]
  char v196[20]; // [esp+A8h] [ebp-10114h] BYREF
  size_t v197; // [esp+BCh] [ebp-10100h]
  char v198[4]; // [esp+C0h] [ebp-100FCh] BYREF
  int v199; // [esp+C4h] [ebp-100F8h]
  int v200; // [esp+C8h] [ebp-100F4h]
  unsigned __int16 v201[30]; // [esp+CCh] [ebp-100F0h] BYREF
  JET_TABLEID v202[11]; // [esp+108h] [ebp-100B4h] BYREF
  _DWORD v203[2]; // [esp+134h] [ebp-10088h] BYREF
  struct tagDBPROPSET *v204[2]; // [esp+13Ch] [ebp-10080h] BYREF
  __int64 v205; // [esp+144h] [ebp-10078h]
  _WORD v206[32750]; // [esp+14Ch] [ebp-10070h] BYREF
  wchar_t String2[66]; // [esp+10128h] [ebp-94h] BYREF
  int v208; // [esp+101B8h] [ebp-4h]

  v181 = (unsigned int)a2;
  v177 = a3;
  v186 = a4;
  v173 = (unsigned int)a5;
  v169 = (struct tagDBPROPIDSET *)a6;
  v179 = a7;
  v180 = a9;
  v178 = this;
  v189 = a8;
  v195 = 0;
  v170 = 0;
  v175 = 0;
  ObjectInfo = 0;
  v165[1] = 0;
  v165[2] = 0;
  v166 = 0;
  v165[0] = (struct tagDBPROPSET *)&CAlterTableTableProperties::`vftable';
  v208 = 0;
  v176 = 0;
  v9 = *((_DWORD *)this + 2);
  v10 = *(_DWORD *)(v9 + 20);
  v191 = *(_DWORD *)(v9 + 16);
  v185 = v10;
  memset(v201, 0, sizeof(v201));
  memset(v202, 0, sizeof(v202));
  v172 = 0;
  v184 = 0;
  v171 = v206;
  *(_DWORD *)&v201[2] = -1;
  v202[1] = -1;
  SetErrorInfo(0, 0);
  if ( a3 )
    *v177 = 0;
  if ( v186 )
    *v186 = 0;
  if ( v173 )
    *(_DWORD *)v173 = 0;
  if ( v169 )
    v169->rgPropertyIDs = 0;
  if ( v179 )
    *v179 = 0;
  if ( a8 )
    *a8 = 0;
  if ( v180 )
    *v180 = 0;
  v11 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)v178 + 2) + 104);
  v168 = v11;
  EnterCriticalSection(v11);
  v12 = v181;
  LOBYTE(v208) = 1;
  if ( !v181 || v177 && !v186 || v173 && !v169 || (v13 = v179) != 0 && !v189 || !v177 && !v173 && !v179 )
  {
    IndexInfo = -2147024809;
    v195 = -2147024809;
    goto LABEL_276;
  }
  if ( *(_DWORD *)(v181 + 16) != 2 || !*(_DWORD *)(v181 + 20) )
  {
    IndexInfo = -2147217860;
    v195 = -2147217860;
    goto LABEL_276;
  }
  if ( v177 )
  {
    v14 = (ColumnData *)operator new(0x10u);
    v15 = v14;
    v176 = v14;
    v187 = (size_t)v14;
    if ( !v14 )
    {
      v176 = 0;
      goto LABEL_36;
    }
    *(_DWORD *)v14 = &ColumnData::`vftable';
    v16 = v181;
    *((_DWORD *)v15 + 1) = 0;
    *((_DWORD *)v15 + 2) = 0;
    *((_DWORD *)v15 + 3) = 0;
    IndexInfo = ColumnData::FInit(v15, v191, v10, *(const unsigned __int16 **)(v16 + 20), (int *)&ObjectInfo, 0);
    v195 = IndexInfo;
    if ( IndexInfo < 0 )
    {
      if ( ObjectInfo == -1907 || ObjectInfo == -1809 )
      {
        IndexInfo = -2147217911;
        v195 = -2147217911;
      }
      else if ( ObjectInfo == -1305 )
      {
        IndexInfo = -2147217865;
        v195 = -2147217865;
      }
      goto LABEL_276;
    }
    v12 = v181;
    v13 = v179;
  }
  if ( v13 )
  {
    IndexInfo = CJOLT::JOLTJetGetIndexInfo(
                  *(_DWORD *)(v12 + 20),
                  0,
                  v201,
                  v151,
                  v152,
                  (unsigned int)&ObjectInfo,
                  0,
                  (int *)&v187,
                  (int)v156,
                  (int *)v158);
    v195 = IndexInfo;
    if ( IndexInfo < 0 )
      goto LABEL_276;
    RelationshipInfo = JetGetRelationshipInfo(v191, v185, *(_DWORD *)(v181 + 20), 0, v202, 44);
    ObjectInfo = RelationshipInfo;
    if ( RelationshipInfo == -1001 )
    {
      v202[2] = 0;
    }
    else if ( RelationshipInfo < 0 )
    {
LABEL_42:
      IndexInfo = -2147467259;
      v195 = -2147467259;
      goto LABEL_276;
    }
    v19 = JetRetrieveProperty(
            v191,
            v185,
            L"Tables",
            *(_DWORD *)(v181 + 20),
            0,
            L"CheckConstraints",
            v206,
            65500,
            &pvData,
            &v182,
            0,
            0);
    ObjectInfo = v19;
    if ( v19 == -3602 || v19 == -3600 )
    {
      v206[0] = 0;
      ObjectInfo = 0;
    }
    else
    {
      if ( v19 < 0 )
      {
        IndexInfo = -2147467259;
        v195 = -2147467259;
        goto LABEL_276;
      }
      if ( v206[0] )
      {
        v20 = v206;
        v21 = 0;
        do
        {
          v22 = wcslen(v20);
          v20 += v22 + 1;
          if ( (v172 & 1) != 0 )
            v21 += 2 * v22 + 2;
          v23 = *v20 == 0;
          ++v172;
        }
        while ( !v23 );
        v184 = v21;
        v11 = v168;
      }
    }
    v13 = v179;
  }
  if ( v180 )
  {
    if ( v177 )
    {
      v24 = 24 * *((_DWORD *)v176 + 1);
      v170 = v24;
    }
    else
    {
      v24 = 0;
    }
    if ( v13 )
    {
      v24 += v184;
      v170 = v24;
    }
    if ( v24 )
    {
      v25 = (*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(*(_DWORD *)(*(_DWORD *)Sys + 12), Sys, v24);
      *v180 = (unsigned __int16 *)v25;
      if ( !v25 )
      {
        IndexInfo = -2147024882;
        v195 = -2147024882;
        goto LABEL_276;
      }
    }
  }
  if ( !v177 )
    goto LABEL_170;
  v26 = v176;
  v27 = *((_DWORD *)v176 + 1);
  v185 = v27;
  *v177 = v27;
  if ( v27 )
  {
    v28 = *(int (__thiscall **)(_DWORD, int, size_t))(*(_DWORD *)Sys + 12);
    Size = 52 * v27;
    v29 = (struct tagDBCOLUMNDESC *)v28(v28, Sys, 52 * v27);
    *v186 = v29;
    if ( !v29 )
    {
      IndexInfo = -2147024882;
      v195 = -2147024882;
      goto LABEL_276;
    }
    memset(v29, 0, Size);
    v27 = v185;
    v26 = v176;
  }
  v30 = 0;
  tableid = 0;
  if ( !v27 )
  {
LABEL_170:
    if ( v173 )
    {
      IndexInfo = CSettableProperties::FInit((CSettableProperties *)v165);
      v195 = IndexInfo;
      if ( IndexInfo < 0 )
        goto LABEL_276;
      IndexInfo = CTableProperties::CopyPropertiesFromStaticTable(
                    (CTableProperties *)v165,
                    (const struct DBInfoProps *)&rgDBInfoProps);
      v195 = IndexInfo;
      if ( IndexInfo < 0 )
        goto LABEL_276;
      IndexInfo = CTableProperties::SetJetPropertiesToJoltProperties(
                    (CTableProperties *)v165,
                    *(_DWORD *)(*((_DWORD *)v178 + 2) + 16),
                    v181,
                    *(_DWORD *)(*((_DWORD *)v178 + 2) + 20),
                    *(unsigned __int16 **)(v181 + 20));
      v195 = IndexInfo;
      if ( IndexInfo < 0 )
        goto LABEL_276;
      IndexInfo = 0;
      v195 = 0;
      tableid = -1;
      v203[0] = 24;
      v85 = *((_DWORD *)v178 + 2);
      v86 = *(unsigned __int16 **)(v85 + 20);
      sesid = *(_DWORD *)(v85 + 16);
      v182 = v86;
      ObjectInfo = 0;
      if ( JoltProperties::BinarySearch(v166, 0x10Au, &v187) >= 0 )
      {
        if ( (*(_BYTE *)(*((_DWORD *)v166 + 4) + 48 * v187 + 40) & 1) != 0 )
        {
          ObjectInfo = JetGetObjectInfo(sesid, v182, 1, L"Tables", *(_DWORD *)(v181 + 20), &tableid, 4, 3);
          if ( ObjectInfo )
          {
            IndexInfo = -2147467259;
            v195 = -2147467259;
          }
          else
          {
            ObjectInfo = JetGetTableColumnInfo(sesid, tableid, L"Flags", v203, 24, 0);
            if ( (ObjectInfo & 0x80000000) == 0 )
            {
              ObjectInfo = JetRetrieveColumn(sesid, tableid, v203[1], &pvData, 4u, &pcbActual, 0, 0);
              if ( (ObjectInfo & 0x80000000) == 0 )
              {
                JoltProperties::SetbProperty(v166, 0x10Au, (pvData >> 3) & 1);
              }
              else
              {
                IndexInfo = -2147467259;
                v195 = -2147467259;
              }
            }
            else
            {
              IndexInfo = -2147467259;
              v195 = -2147467259;
            }
          }
          if ( tableid != -1 )
            JetCloseTable(sesid, tableid);
        }
        if ( IndexInfo < 0 )
          goto LABEL_276;
      }
      IndexInfo = GenericGetProperties(
                    v173,
                    v169,
                    *(unsigned int **)(*((_DWORD *)v178 + 2) + 84),
                    v165,
                    (struct CDataSource *)4,
                    v156,
                    (unsigned int)v158);
      v195 = IndexInfo;
      if ( IndexInfo < 0 )
        goto LABEL_276;
    }
    else
    {
      IndexInfo = v195;
    }
    if ( !v179 )
      goto LABEL_276;
    v87 = 32;
    v88 = *(_DWORD *)&v201[4];
    v89 = v172 >> 1;
    v194 = 0;
    if ( *(_DWORD *)&v201[4] < 0x20u )
      v87 = *(_DWORD *)&v201[4];
    v172 >>= 1;
    v90 = v202[2] + v89 + v87;
    if ( v90 )
    {
      v91 = *(int (__thiscall **)(_DWORD, int, JET_TABLEID))(*(_DWORD *)Sys + 12);
      v187 = 56 * v90;
      v92 = (struct tagDBCONSTRAINTDESC *)v91(v91, Sys, 56 * v90);
      *v189 = v92;
      if ( !v92 )
      {
        IndexInfo = -2147024882;
        v195 = -2147024882;
        goto LABEL_276;
      }
      memset(v92, 0, v187);
      v88 = *(_DWORD *)&v201[4];
    }
    v93 = 0;
    tableid = v88 == 0;
    v192 = 0;
    if ( v88 )
    {
      do
      {
        while ( 1 )
        {
          ObjectInfo = JetRetrieveColumn(v191, *(JET_TABLEID *)&v201[2], *(JET_COLUMNID *)&v201[8], &v194, 4u, 0, 0, 0);
          if ( (ObjectInfo & 0x80000000) != 0 )
            goto LABEL_42;
          if ( (v194 & 3) == 0 )
            break;
          v96 = v192;
          if ( (v194 & 2) != 0 )
          {
            (*v189)[(_DWORD)v192].ConstraintType = 2;
          }
          else if ( (v194 & 1) != 0 )
          {
            (*v189)[(_DWORD)v192].ConstraintType = 0;
          }
          ObjectInfo = JetRetrieveColumn(
                         v191,
                         *(JET_TABLEID *)&v201[2],
                         *(JET_COLUMNID *)&v201[6],
                         String2,
                         0x82u,
                         &v194,
                         0,
                         0);
          if ( (ObjectInfo & 0x80000000) != 0 )
            goto LABEL_42;
          v97 = v194;
          if ( (v194 & 0xFFFFFFFE) >= 0x82 )
LABEL_311:
            __report_rangecheckfailure();
          *(wchar_t *)((char *)String2 + (v194 & 0xFFFFFFFE)) = 0;
          v184 = 56 * (_DWORD)v96;
          IndexInfo = CImpITableDef::FillpDBIDWithName(
                        (CImpITableDef *)(56 * (_DWORD)v96),
                        &(*v189)[(_DWORD)v96].pConstraintID,
                        String2,
                        v97);
          v195 = IndexInfo;
          if ( IndexInfo < 0 )
            goto LABEL_276;
          IndexInfo = CImpITableDef::DetermineNumberofColumnsInGroup(
                        v98,
                        v191,
                        *(JET_TABLEID *)&v201[2],
                        *(JET_COLUMNID *)&v201[6],
                        String2,
                        &v185,
                        (int *)&ObjectInfo);
          v195 = IndexInfo;
          if ( IndexInfo < 0 )
            goto LABEL_276;
          v99 = v185;
          *(DBORDINAL *)((char *)&(*v189)->cColumns + v184) = v185;
          v100 = *(int (__thiscall **)(_DWORD, int, size_t))(*(_DWORD *)Sys + 12);
          v187 = 24 * v99;
          v101 = v100(v100, Sys, 24 * v99);
          v102 = v189;
          v103 = v184;
          *(DBID **)((char *)&(*v189)->rgColumnList + v184) = (DBID *)v101;
          v104 = *(DBID **)((char *)&(*v102)->rgColumnList + v103);
          if ( !v104 )
            goto LABEL_36;
          memset(v104, 0, v187);
          v105 = tableid;
          for ( sesid = 0; sesid < v185; ++sesid )
          {
            if ( v105 )
              break;
            ObjectInfo = JetRetrieveColumn(
                           v191,
                           *(JET_TABLEID *)&v201[2],
                           *(JET_COLUMNID *)&v201[28],
                           String2,
                           0x82u,
                           &v194,
                           0,
                           0);
            if ( (ObjectInfo & 0x80000000) != 0 )
              goto LABEL_42;
            if ( (v194 & 0xFFFFFFFE) >= 0x82 )
              goto LABEL_311;
            v106 = v184;
            v107 = (unsigned __int16 *)(2 * v194 + 2);
            v182 = v107;
            *(wchar_t *)((char *)String2 + (v194 & 0xFFFFFFFE)) = 0;
            v108 = 3 * sesid;
            v109 = *(int *)((char *)&(*v189)->rgColumnList + v106);
            *(_DWORD *)(v109 + 8 * v108 + 16) = 2;
            v187 = v109 + 8 * v108;
            v110 = (unsigned __int16 *)(*(int (__thiscall **)(_DWORD, int, unsigned __int16 *))(*(_DWORD *)Sys + 12))(
                                         *(_DWORD *)(*(_DWORD *)Sys + 12),
                                         Sys,
                                         v107);
            *(_DWORD *)(v187 + 20) = v110;
            if ( !v110 )
              goto LABEL_36;
            WCSCPY(String2, v110, v182, (const unsigned __int16 *)v156, (unsigned int)v158);
            v195 = 0;
            v111 = JetMove(v191, *(JET_TABLEID *)&v201[2], 1, 0);
            v105 = tableid;
            ObjectInfo = v111;
            if ( v111 == -1603 )
              v105 = 1;
            tableid = v105;
          }
          v93 = (char *)v192 + 1;
          v192 = (_DWORD *)((char *)v192 + 1);
          ++*v179;
          if ( v105 )
            goto LABEL_201;
        }
        ObjectInfo = JetMove(v191, *(JET_TABLEID *)&v201[2], 1, 0);
      }
      while ( ObjectInfo != -1603 );
      v93 = (char *)v192;
    }
LABEL_201:
    v94 = v202[2] == 0;
    if ( !v202[2] )
    {
LABEL_270:
      for ( Size = 0; Size < v172; ++Size )
      {
        v139 = wcslen(v171);
        v140 = 7 * (_DWORD)v93;
        v141 = v189;
        v140 *= 8;
        v154 = v171;
        v142 = *v189;
        v187 = v140;
        *(DBCONSTRAINTTYPE *)((char *)&v142->ConstraintType + v140) = 3;
        v195 = CImpITableDef::FillpDBIDWithName(
                 (CImpITableDef *)v140,
                 (struct tagDBID **)((char *)&(*v141)->pConstraintID + v140),
                 v154,
                 v139);
        if ( v195 < 0 )
          break;
        v143 = &v171[v139 + 1];
        v182 = v143;
        if ( v180 )
        {
          v144 = v175;
          WCSCPY(
            v143,
            &(*v180)[v175],
            (unsigned __int16 *)((v170 >> 1) - v175),
            (const unsigned __int16 *)v156,
            (unsigned int)v158);
          *(OLECHAR **)((char *)&(*v189)->pwszConstraintText + v187) = &(*v180)[v144];
          v143 = v182;
          v175 += wcslen(v182) + 1;
        }
        v145 = wcslen(v143);
        v146 = v143 + 1;
        v93 = (char *)v192 + 1;
        v192 = (_DWORD *)((char *)v192 + 1);
        v171 = &v146[v145];
        ++*v179;
      }
      IndexInfo = v195;
      goto LABEL_276;
    }
    while ( 1 )
    {
      do
      {
        v95 = JetRetrieveColumn(v191, v202[1], v202[7], String2, 0x82u, &v194, 0, 0);
        ObjectInfo = v95;
        if ( v95 < 0 )
          goto LABEL_42;
      }
      while ( v95 == 1004 );
      if ( (v194 & 0xFFFFFFFE) >= 0x82 )
        goto LABEL_311;
      *(wchar_t *)((char *)String2 + (v194 & 0xFFFFFFFE)) = 0;
      if ( !__wcsicmp(*(const wchar_t **)(v181 + 20), String2) )
        break;
      ObjectInfo = JetMove(v191, v202[1], 1, 0);
      if ( ObjectInfo == -1603 )
      {
        v94 = 1;
LABEL_269:
        v93 = (char *)v192 + 1;
        v192 = (_DWORD *)((char *)v192 + 1);
        if ( v94 )
          goto LABEL_270;
      }
    }
    tableid = v94;
    ObjectInfo = JetRetrieveColumn(v191, v202[1], v202[3], String2, 0x82u, &v194, 0, 0);
    if ( (ObjectInfo & 0x80000000) != 0 )
      goto LABEL_42;
    v112 = v194;
    if ( (v194 & 0xFFFFFFFE) >= 0x82 )
      goto LABEL_311;
    v113 = v192;
    *(wchar_t *)((char *)String2 + (v194 & 0xFFFFFFFE)) = 0;
    sesid = 56 * (_DWORD)v113;
    IndexInfo = CImpITableDef::FillpDBIDWithName(
                  (CImpITableDef *)(56 * (_DWORD)v113),
                  &(*v189)[(_DWORD)v113].pConstraintID,
                  String2,
                  v112);
    v195 = IndexInfo;
    if ( IndexInfo < 0 )
      goto LABEL_276;
    ObjectInfo = JetRetrieveColumn(v191, v202[1], v202[9], String2, 0x82u, &v194, 0, 0);
    if ( (ObjectInfo & 0x80000000) != 0 )
      goto LABEL_42;
    v114 = v194;
    if ( (v194 & 0xFFFFFFFE) >= 0x82 )
      goto LABEL_311;
    *(wchar_t *)((char *)String2 + (v194 & 0xFFFFFFFE)) = 0;
    IndexInfo = CImpITableDef::FillpDBIDWithName(
                  (CImpITableDef *)(sesid + 16),
                  (struct tagDBID **)((char *)&(*v189)->pReferencedTableID + sesid),
                  String2,
                  v114);
    v195 = IndexInfo;
    if ( IndexInfo < 0 )
      goto LABEL_276;
    v115 = v189;
    v116 = (CImpITableDef *)sesid;
    *(DBCONSTRAINTTYPE *)((char *)&(*v189)->ConstraintType + sesid) = 1;
    IndexInfo = CImpITableDef::DetermineNumberofColumnsInGroup(
                  v116,
                  v191,
                  v202[1],
                  v202[3],
                  *(unsigned __int16 **)(*(_DWORD *)((char *)v116 + (_DWORD)*v115) + 20),
                  &v184,
                  (int *)&ObjectInfo);
    v195 = IndexInfo;
    if ( IndexInfo < 0 )
      goto LABEL_276;
    v117 = v184;
    *(DBORDINAL *)((char *)&(*v189)->cForeignKeyColumns + sesid) = v184;
    v118 = *(int (__thiscall **)(_DWORD, int, unsigned int))(*(_DWORD *)Sys + 12);
    v185 = 24 * v117;
    v119 = v118(v118, Sys, 24 * v117);
    v120 = v189;
    v121 = sesid;
    *(DBID **)((char *)&(*v189)->rgForeignKeyColumnList + sesid) = (DBID *)v119;
    v122 = *(DBID **)((char *)&(*v120)->rgForeignKeyColumnList + v121);
    if ( !v122 )
      goto LABEL_36;
    memset(v122, 0, v185);
    v155 = v185;
    *(DBORDINAL *)((char *)&(*v189)->cColumns + v121) = v184;
    v123 = (*(int (__thiscall **)(_DWORD, int, size_t))(*(_DWORD *)Sys + 12))(
             *(_DWORD *)(*(_DWORD *)Sys + 12),
             Sys,
             v155);
    v124 = v189;
    v125 = sesid;
    *(DBID **)((char *)&(*v189)->rgColumnList + sesid) = (DBID *)v123;
    v126 = *(DBID **)((char *)&(*v124)->rgColumnList + v125);
    if ( !v126 )
      goto LABEL_36;
    memset(v126, 0, v185);
    ObjectInfo = JetRetrieveColumn(v191, v202[1], v202[4], &Size, 4u, &v194, 0, 0);
    v127 = Size & 0xF00;
    if ( (Size & 0xF00) != 0 )
    {
      if ( v127 == 256 )
      {
        v128 = 1;
      }
      else
      {
        if ( v127 != 512 )
        {
          v128 = v194;
          goto LABEL_244;
        }
        v128 = 2;
      }
    }
    else
    {
      v128 = 0;
    }
    v194 = v128;
LABEL_244:
    v129 = v189;
    *(DBUPDELRULE *)((char *)&(*v189)->UpdateRule + v125) = v128;
    v130 = Size & 0xF000;
    if ( (Size & 0xF000) != 0 )
    {
      if ( v130 == 4096 )
      {
        v131 = 1;
      }
      else
      {
        if ( v130 != 0x2000 )
        {
          v131 = v194;
LABEL_252:
          *(DBUPDELRULE *)((char *)&(*v129)->DeleteRule + v125) = v131;
          v132 = 0;
          v185 = 0;
          if ( v184 )
          {
            do
            {
              ObjectInfo = JetRetrieveColumn(v191, v202[1], v202[8], String2, 0x82u, &v194, 0, 0);
              if ( (ObjectInfo & 0x80000000) != 0 )
                goto LABEL_42;
              v133 = v194;
              if ( (v194 & 0xFFFFFFFE) >= 0x82 )
                goto LABEL_311;
              *(wchar_t *)((char *)String2 + (v194 & 0xFFFFFFFE)) = 0;
              v134 = *v189;
              pvData = 24 * v132;
              v182 = (unsigned __int16 *)(2 * v133 + 2);
              v187 = (size_t)&(*(DBID **)((char *)&v134->rgForeignKeyColumnList + sesid))[v132];
              *(_DWORD *)(v187 + 16) = 2;
              v135 = (unsigned __int16 *)(*(int (__thiscall **)(_DWORD, int, unsigned int))(*(_DWORD *)Sys + 12))(
                                           *(_DWORD *)(*(_DWORD *)Sys + 12),
                                           Sys,
                                           2 * v133 + 2);
              *(_DWORD *)(v187 + 20) = v135;
              if ( !v135 )
                goto LABEL_36;
              WCSCPY(String2, v135, v182, (const unsigned __int16 *)v156, (unsigned int)v158);
              ObjectInfo = JetRetrieveColumn(v191, v202[1], v202[10], String2, 0x82u, &v194, 0, 0);
              if ( (ObjectInfo & 0x80000000) != 0 )
                goto LABEL_42;
              if ( (v194 & 0xFFFFFFFE) >= 0x82 )
                goto LABEL_311;
              v136 = (unsigned __int16 *)(2 * v194 + 2);
              *(wchar_t *)((char *)String2 + (v194 & 0xFFFFFFFE)) = 0;
              v182 = v136;
              v187 = *(size_t *)((char *)&(*v189)->rgColumnList + sesid) + pvData;
              *(_DWORD *)(v187 + 16) = 2;
              v137 = (unsigned __int16 *)(*(int (__thiscall **)(_DWORD, int, unsigned __int16 *))(*(_DWORD *)Sys + 12))(
                                           *(_DWORD *)(*(_DWORD *)Sys + 12),
                                           Sys,
                                           v136);
              *(_DWORD *)(v187 + 20) = v137;
              if ( !v137 )
                goto LABEL_36;
              WCSCPY(String2, v137, v182, (const unsigned __int16 *)v156, (unsigned int)v158);
              v195 = 0;
              ObjectInfo = JetMove(v191, v202[1], 1, 0);
              if ( ObjectInfo == -1603 )
              {
                v138 = 1;
                ObjectInfo = 0;
                tableid = 1;
              }
              else
              {
                v138 = tableid;
              }
              v132 = v185 + 1;
              v185 = v132;
            }
            while ( v132 < v184 );
            if ( !v138 && v132 )
              ObjectInfo = JetMove(v191, v202[1], -1, 0);
          }
          v153 = v202[1];
          ++*v179;
          ObjectInfo = JetMove(v191, v153, 1, 0);
          if ( ObjectInfo == -1603 )
          {
            ObjectInfo = 0;
            v94 = 1;
          }
          else
          {
            v94 = tableid;
          }
          goto LABEL_269;
        }
        v131 = 2;
      }
    }
    else
    {
      v131 = 0;
    }
    v194 = v131;
    goto LABEL_252;
  }
  v31 = (_DWORD *)((char *)v26 + 12);
  v187 = 131;
  while ( 2 )
  {
    v192 = v31;
    if ( v180 )
    {
      v32 = *v31;
      Size = 104 * v30;
      v33 = v175;
      WCSCPY(
        (unsigned __int16 *)dword_10051564[2 * *(_DWORD *)(v32 + 104 * v30 + 36)],
        &(*v180)[v175],
        (unsigned __int16 *)((v170 >> 1) - v175),
        (const unsigned __int16 *)v156,
        (unsigned int)v158);
      (*v186)[tableid].pwszTypeName = &(*v180)[v33];
      v34 = (_WORD *)dword_10051564[2 * *(_DWORD *)(*v192 + Size + 36)];
      v35 = v34 + 1;
      while ( *v34++ )
        ;
      v175 += v34 - v35 + 1;
    }
    v204[1] = 0;
    v205 = 0;
    v204[0] = (struct tagDBPROPSET *)&CAlterColumnProperties::`vftable';
    LOBYTE(v208) = 2;
    IndexInfo = CColumnProperties::FInit((CColumnProperties *)v204);
    v195 = IndexInfo;
    if ( IndexInfo < 0 )
      goto LABEL_169;
    IndexInfo = (*(int (__thiscall **)(_DWORD, const struct DBInfoProps *const *, _DWORD, int, unsigned int, _DWORD, _DWORD, _DWORD))(*(_DWORD *)v205 + 4))(
                  v205,
                  &rgDBInfoProps,
                  0,
                  7,
                  DBPROPSET_COLUMN.Data1,
                  *(_DWORD *)&DBPROPSET_COLUMN.Data2,
                  *(_DWORD *)DBPROPSET_COLUMN.Data4,
                  *(_DWORD *)&DBPROPSET_COLUMN.Data4[4]);
    v195 = IndexInfo;
    if ( IndexInfo < 0 )
      goto LABEL_169;
    IndexInfo = (*(int (__thiscall **)(_DWORD, const struct DBInfoProps *const *, int, int, int, int, int, int))(*(_DWORD *)HIDWORD(v205) + 4))(
                  HIDWORD(v205),
                  &rgDBInfoProps,
                  209,
                  8,
                  -2113144542,
                  298937032,
                  -1073741153,
                  -524107185);
    v195 = IndexInfo;
    if ( IndexInfo < 0 )
      goto LABEL_169;
    v37 = (_DWORD *)(104 * tableid + *v192);
    v194 = 104 * tableid;
    v38 = v37[1];
    if ( !v38 )
    {
      v39 = v37[6];
      if ( !v39 || (unsigned int)(v39 - 2) <= 1 )
        v38 = v37[7];
    }
    ColumnInfo = JetGetColumnInfo(
                   *(_DWORD *)(*((_DWORD *)v178 + 2) + 16),
                   *(_DWORD *)(*((_DWORD *)v178 + 2) + 20),
                   *(_DWORD *)(v181 + 20),
                   v38,
                   v196,
                   24,
                   0);
    ObjectInfo = ColumnInfo;
    if ( ColumnInfo == -1507 )
    {
      IndexInfo = -2147217819;
      v195 = -2147217819;
LABEL_169:
      LOBYTE(v208) = 1;
      CSettableProperties::~CSettableProperties((CSettableProperties *)v204);
      goto LABEL_276;
    }
    if ( ColumnInfo == -1305 )
    {
      IndexInfo = -2147217865;
      LOBYTE(v208) = 1;
      v195 = -2147217865;
      CSettableProperties::~CSettableProperties((CSettableProperties *)v204);
      goto LABEL_276;
    }
    if ( ColumnInfo )
    {
      IndexInfo = -2147467259;
      LOBYTE(v208) = 1;
      v195 = -2147467259;
      CSettableProperties::~CSettableProperties((CSettableProperties *)v204);
      goto LABEL_276;
    }
    v41 = 0;
    Size = v197;
    do
    {
      sesid = 0;
      if ( dword_100053A0[4 * v41] )
      {
        if ( dword_100053A0[4 * v41] != 1 )
          goto LABEL_92;
        v42 = HIDWORD(v205);
      }
      else
      {
        v42 = v205;
      }
      sesid = v42;
LABEL_92:
      v23 = (Size & dword_100053A8[4 * v41]) == 0;
      v43 = dword_100053AC[4 * v41];
      v44 = dword_100053A4[4 * v41];
      v195 = -2147467259;
      if ( v23 )
      {
        if ( JoltProperties::BinarySearch((JoltProperties *)sesid, v44, &v163) < 0 )
          goto LABEL_100;
        v45 = v163;
      }
      else
      {
        v43 ^= 1u;
        if ( JoltProperties::BinarySearch((JoltProperties *)sesid, v44, &v164) < 0 )
          goto LABEL_100;
        v45 = v164;
      }
      v46 = 6 * v45;
      v47 = *(_DWORD *)(sesid + 16);
      if ( *(_WORD *)(v47 + 8 * v46 + 16) == 11 && (*(_DWORD *)(v47 + 8 * v46 + 32) & 0x400) != 0 )
      {
        *(_WORD *)(v47 + 8 * v46 + 24) = (v43 != 1) - 1;
        v195 = 0;
      }
LABEL_100:
      ++v41;
    }
    while ( v41 < 8 );
    IndexInfo = v195;
    v11 = v168;
    if ( v195 < 0 )
      goto LABEL_169;
    v48 = (JoltProperties *)v205;
    if ( JoltProperties::BinarySearch((JoltProperties *)v205, 0x1Au, &v162) < 0 )
      v49 = 0;
    else
      v49 = *((_DWORD *)v48 + 4) + 48 * v162;
    if ( *(_WORD *)(v49 + 24) == 0xFFFF )
    {
      v50 = (_DWORD *)(v194 + *v192);
      v51 = v50[1];
      if ( !v51 )
      {
        v52 = v50[6];
        if ( !v52 || (unsigned int)(v52 - 2) <= 1 )
          v51 = v50[7];
      }
      ObjectInfo = JetGetColumnInfo(
                     *(_DWORD *)(*((_DWORD *)v178 + 2) + 16),
                     *(_DWORD *)(*((_DWORD *)v178 + 2) + 20),
                     *(_DWORD *)(v181 + 20),
                     v51,
                     v198,
                     12,
                     11);
      if ( (ObjectInfo & 0x80000000) == 0 )
      {
        if ( JoltProperties::BinarySearch(v48, 0x11Au, &v161) < 0 )
          v53 = 0;
        else
          v53 = *((_DWORD *)v48 + 4) + 48 * v161;
        *(_DWORD *)(v53 + 24) = v199;
        if ( JoltProperties::BinarySearch(v48, 0x11Bu, &v160) < 0 )
          v54 = 0;
        else
          v54 = *((_DWORD *)v48 + 4) + 48 * v160;
        *(_DWORD *)(v54 + 24) = v200;
      }
    }
    v55 = (_DWORD *)(v194 + *v192);
    v56 = (unsigned __int16 *)v55[1];
    if ( !v56 )
    {
      v57 = v55[6];
      if ( !v57 || (unsigned int)(v57 - 2) <= 1 )
        v56 = (unsigned __int16 *)v55[7];
    }
    IndexInfo = CColumnProperties::SetJetPropertyManagerToJoltProperties(
                  (CColumnProperties *)v204,
                  *(_DWORD *)(*((_DWORD *)v178 + 2) + 16),
                  v181,
                  *(_DWORD *)(*((_DWORD *)v178 + 2) + 20),
                  *(unsigned __int16 **)(v181 + 20),
                  v56,
                  v194 + *v192);
    v195 = IndexInfo;
    if ( IndexInfo < 0 )
      goto LABEL_169;
    v58 = v205;
    if ( JoltProperties::BinarySearch((JoltProperties *)v205, 0xA7u, &pcbActual) < 0 )
      v59 = 0;
    else
      v59 = *(_DWORD *)(v58 + 16) + 48 * pcbActual;
    if ( *(_WORD *)(v59 + 24) == 0xFFFF )
    {
      v60 = (_DWORD *)(HIDWORD(v205) + 16);
      v61 = JoltProperties::BinarySearch((JoltProperties *)HIDWORD(v205), 0xE0u, &pvData) < 0 ? 0 : *v60 + 48 * pvData;
      if ( *(_WORD *)(v61 + 24) == 0xFFFF )
      {
        if ( JoltProperties::BinarySearch((JoltProperties *)HIDWORD(v205), 0xE0u, (unsigned int *)&v182) < 0 )
          v62 = 0;
        else
          v62 = *v60 + 48 * (_DWORD)v182;
        *(_WORD *)(v62 + 24) = 0;
      }
    }
    v63 = *((_DWORD *)v178 + 2);
    v184 = 52 * tableid;
    IndexInfo = GenericGetProperties(
                  (unsigned int)&(*v186)[tableid].cPropertySets,
                  (const struct tagDBPROPIDSET *const)&(*v186)[tableid].rgPropertySets,
                  *(unsigned int **)(v63 + 84),
                  v204,
                  (struct CDataSource *)1,
                  v156,
                  (unsigned int)v158);
    LOBYTE(v208) = 1;
    v195 = IndexInfo;
    CSettableProperties::~CSettableProperties((CSettableProperties *)v204);
    if ( IndexInfo < 0 )
      goto LABEL_276;
    v64 = v194;
    v65 = v184;
    *(DBLENGTH *)((char *)&(*v186)->ulColumnSize + v184) = *(_DWORD *)(*v192 + v194 + 60);
    *(DBKIND *)((char *)&(*v186)->dbcid.eKind + v65) = 2;
    v66 = (_DWORD *)(*v192 + v64);
    v67 = (_WORD *)v66[1];
    if ( v67 )
      goto LABEL_144;
    v68 = v66[6];
    if ( v68 && (unsigned int)(v68 - 2) > 1 || !v66[7] )
    {
LABEL_152:
      *(DBTYPE *)((char *)&(*v186)->wType + v65) = *(_WORD *)(*v192 + v194 + 40);
      if ( *(DBTYPE *)((char *)&(*v186)->wType + v65) == 131 )
      {
        v79 = v194 + *v192;
        v80 = *(_WORD *)(v79 + 40);
        if ( v80 == (_WORD)v187 )
        {
          v81 = *(_BYTE *)(v79 + 48);
        }
        else
        {
          v82 = 0;
          while ( word_10004700[2 * v82] != v80 )
          {
            if ( (unsigned int)++v82 >= 8 )
            {
              v81 = -1;
              goto LABEL_160;
            }
          }
          v81 = byte_10004702[4 * v82];
        }
LABEL_160:
        *(&(*v186)->bPrecision + v65) = v81;
        v83 = v194 + *v192;
        if ( *(_WORD *)(v83 + 40) == 131 )
          v84 = *(_BYTE *)(v83 + 49);
        else
          v84 = -1;
        *(&(*v186)->bScale + v65) = v84;
      }
      v30 = tableid + 1;
      tableid = v30;
      if ( v30 >= v185 )
        goto LABEL_170;
      v31 = v192;
      continue;
    }
    break;
  }
  v69 = v66[6];
  if ( v69 && (unsigned int)(v69 - 2) >= 2 )
    v67 = 0;
  else
    v67 = (_WORD *)v66[7];
LABEL_144:
  v70 = v67 + 1;
  while ( *v67++ )
    ;
  Size = 2 * (v67 - v70) + 2;
  v72 = (*(int (__thiscall **)(_DWORD, int, size_t))(*(_DWORD *)Sys + 12))(*(_DWORD *)(*(_DWORD *)Sys + 12), Sys, Size);
  v73 = v186;
  v74 = v184;
  *(ULONG *)((char *)&(*v186)->dbcid.uName.ulPropid + v184) = v72;
  v75 = *(LPOLESTR *)((char *)&(*v73)->dbcid.uName.pwszName + v74);
  if ( v75 )
  {
    v76 = (_DWORD *)(v194 + *v192);
    v77 = (unsigned __int16 *)v76[1];
    if ( !v77 )
    {
      v78 = v76[6];
      if ( !v78 || (unsigned int)(v78 - 2) <= 1 )
        v77 = (unsigned __int16 *)v76[7];
    }
    WCSCPY(v77, v75, (unsigned __int16 *)Size, (const unsigned __int16 *)v156, (unsigned int)v158);
    v65 = v184;
    goto LABEL_152;
  }
LABEL_36:
  IndexInfo = -2147024882;
  v195 = -2147024882;
LABEL_276:
  if ( ObjectInfo )
  {
    CExtError::SendJetErrortoOLEAuto(ObjectInfo, (int)&IID_ITableCreation, (int)v156, v158);
  }
  else if ( IndexInfo < 0
         && IndexInfo != -2147024882
         && !JetGetDatabaseInfo(
               *(_DWORD *)(*((_DWORD *)v178 + 2) + 16),
               *(_DWORD *)(*((_DWORD *)v178 + 2) + 20),
               &v187,
               4,
               3) )
  {
    CExtError::SendHRtoOLEAuto((int)&IID_ITableCreation, 0, (const struct _GUID *)v156, (int)v158);
  }
  if ( v176 )
  {
    (*(void (__thiscall **)(ColumnData *, int))(*(_DWORD *)v176 + 4))(v176, 1);
    IndexInfo = v195;
  }
  if ( v202[1] != -1 )
    JetCloseTable(v191, v202[1]);
  if ( *(_DWORD *)&v201[2] != -1 )
    JetCloseTable(v191, *(JET_TABLEID *)&v201[2]);
  if ( IndexInfo < 0 )
  {
    if ( v177 )
    {
      v147 = v186;
      if ( v186 )
      {
        if ( *v177 )
        {
          v148 = 0;
          do
          {
            v149 = (int)&(*v147)[v148];
            v187 = 52 * v148;
            if ( *(_DWORD *)(v149 + 40) == 2 && Sys )
              (*(void (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)Sys + 20))(
                *(_DWORD *)(*(_DWORD *)Sys + 20),
                Sys,
                *(_DWORD *)(v149 + 44));
            FreeMemory((const unsigned int *)v156, (struct tagDBPROPSET **)v158);
            ++v148;
            v147 = v186;
          }
          while ( v148 < *v177 );
          v11 = v168;
        }
        if ( Sys )
          (*(void (__thiscall **)(_DWORD, int, struct tagDBCOLUMNDESC *))(*(_DWORD *)Sys + 20))(
            *(_DWORD *)(*(_DWORD *)Sys + 20),
            Sys,
            *v147);
        *v177 = 0;
        *v186 = 0;
      }
    }
    FreeMemory((const unsigned int *)v156, (struct tagDBPROPSET **)v158);
    FreeMemory(v157, v159);
    if ( v180 && *v180 )
    {
      if ( Sys )
        (*(void (__thiscall **)(_DWORD, int, unsigned __int16 *))(*(_DWORD *)Sys + 20))(
          *(_DWORD *)(*(_DWORD *)Sys + 20),
          Sys,
          *v180);
      *v180 = 0;
    }
  }
  if ( v11 )
    LeaveCriticalSection(v11);
  CSettableProperties::~CSettableProperties((CSettableProperties *)v165);
  return v195;
}

```

## disassembly

```asm
0x10047070  mov     edi, edi
0x10047072  push    ebp
0x10047073  mov     ebp, esp
0x10047075  push    0FFFFFFFFh
0x10047077  push    offset ?GetTableDefinition@CImpITableDef@@UAGJPAUtagDBID@@PAKQAPAUtagDBCOLUMNDESC@@1QAPAUtagDBPROPSET@@1QAPAUtagDBCONSTRAINTDESC@@PAPAG@Z_SEH
0x1004707c  mov     eax, large fs:0
0x10047082  push    eax
0x10047083  mov     eax, 101A4h
0x10047088  call    __chkstk
0x1004708d  mov     eax, ___security_cookie
0x10047092  xor     eax, ebp
0x10047094  mov     [ebp+var_10], eax
0x10047097  push    esi
0x10047098  push    edi; struct tagDBCONSTRAINTDESC **
0x10047099  push    eax; unsigned int *
0x1004709a  lea     eax, [ebp+var_C]
0x1004709d  mov     large fs:0, eax
0x100470a3  mov     eax, [ebp+arg_4]
0x100470a6  mov     ecx, [ebp+this]
0x100470a9  mov     esi, [ebp+arg_1C]
0x100470ac  mov     [ebp+var_10150], eax
0x100470b2  mov     eax, [ebp+arg_8]
0x100470b5  mov     [ebp+var_10160], eax
0x100470bb  mov     eax, [ebp+arg_C]
0x100470be  mov     [ebp+var_1013C], eax
0x100470c4  mov     eax, [ebp+arg_10]
0x100470c7  mov     [ebp+var_10170], eax
0x100470cd  mov     eax, [ebp+arg_14]
0x100470d0  mov     [ebp+var_10180], eax
0x100470d6  mov     eax, [ebp+arg_18]
0x100470d9  mov     [ebp+var_10158], eax
0x100470df  mov     eax, [ebp+arg_20]
0x100470e2  mov     [ebp+var_10154], eax
0x100470e8  xor     eax, eax
0x100470ea  mov     [ebp+var_1015C], ecx
0x100470f0  mov     [ebp+var_10130], esi
0x100470f6  mov     [ebp+var_10118], eax
0x100470fc  mov     [ebp+var_1017C], eax
0x10047102  mov     [ebp+var_10168], eax
0x10047108  mov     [ebp+var_10120], eax
0x1004710e  mov     [ebp+var_10194], eax
0x10047114  mov     [ebp+var_10190], eax
0x1004711a  mov     [ebp+var_1018C], eax
0x10047120  mov     [ebp+var_10198], offset ??_7CAlterTableTableProperties@@6B@; const CAlterTableTableProperties::`vftable'
0x1004712a  mov     [ebp+var_4], eax
0x1004712d  mov     [ebp+var_10164], eax
0x10047133  mov     eax, [ecx+8]
0x10047136  push    3Ch ; '<'; Size
0x10047138  push    0; Val
0x1004713a  mov     ecx, [eax+10h]
0x1004713d  mov     edi, [eax+14h]
0x10047140  lea     eax, [ebp+var_100F0]
0x10047146  push    eax; void *
0x10047147  mov     [ebp+var_10128], ecx
0x1004714d  mov     [ebp+var_10140], edi
0x10047153  call    _memset
0x10047158  push    2Ch ; ','; Size
0x1004715a  lea     eax, [ebp+var_100B4]
0x10047160  push    0; Val
0x10047162  push    eax; void *
0x10047163  call    _memset
0x10047168  add     esp, 18h
0x1004716b  mov     [ebp+var_10174], 0
0x10047175  lea     eax, [ebp+var_10070]
0x1004717b  mov     [ebp+var_10144], 0
0x10047185  mov     [ebp+var_10178], eax
0x1004718b  mov     [ebp+var_100EC], 0FFFFFFFFh
0x10047195  push    0; perrinfo
0x10047197  push    0; dwReserved
0x10047199  mov     [ebp+var_100B0], 0FFFFFFFFh
0x100471a3  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100471a9  mov     eax, [ebp+var_10160]
0x100471af  test    eax, eax
0x100471b1  jz      short loc_100471B9
0x100471b3  mov     dword ptr [eax], 0
0x100471b9  mov     eax, [ebp+var_1013C]
0x100471bf  test    eax, eax
0x100471c1  jz      short loc_100471C9
0x100471c3  mov     dword ptr [eax], 0
0x100471c9  mov     eax, [ebp+var_10170]
0x100471cf  test    eax, eax
0x100471d1  jz      short loc_100471D9
0x100471d3  mov     dword ptr [eax], 0
0x100471d9  mov     eax, [ebp+var_10180]
0x100471df  test    eax, eax
0x100471e1  jz      short loc_100471E9
0x100471e3  mov     dword ptr [eax], 0
0x100471e9  mov     eax, [ebp+var_10158]
0x100471ef  test    eax, eax
0x100471f1  jz      short loc_100471F9
0x100471f3  mov     dword ptr [eax], 0
0x100471f9  test    esi, esi
0x100471fb  jz      short loc_10047203
0x100471fd  mov     dword ptr [esi], 0
0x10047203  mov     eax, [ebp+var_10154]
0x10047209  test    eax, eax
0x1004720b  jz      short loc_10047213
0x1004720d  mov     dword ptr [eax], 0
0x10047213  mov     esi, [ebp+var_1015C]
0x10047219  mov     esi, [esi+8]
0x1004721c  add     esi, 68h ; 'h'
0x1004721f  push    esi; lpCriticalSection
0x10047220  mov     [ebp+var_10184], esi
0x10047226  mov     [ebp+var_101B0], esi
0x1004722c  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10047232  mov     eax, [ebp+var_10150]
0x10047238  mov     byte ptr [ebp+var_4], 1
0x1004723c  test    eax, eax
0x1004723e  jz      loc_10048BC1
0x10047244  mov     edx, [ebp+var_10160]
0x1004724a  test    edx, edx
0x1004724c  jz      short loc_1004725B
0x1004724e  cmp     [ebp+var_1013C], 0
0x10047255  jz      loc_10048BC1
0x1004725b  cmp     [ebp+var_10170], 0
0x10047262  jz      short loc_10047271
0x10047264  cmp     [ebp+var_10180], 0
0x1004726b  jz      loc_10048BC1
0x10047271  mov     ecx, [ebp+var_10158]
0x10047277  test    ecx, ecx
0x10047279  jz      short loc_10047288
0x1004727b  cmp     [ebp+var_10130], 0
0x10047282  jz      loc_10048BC1
0x10047288  test    edx, edx
0x1004728a  jnz     short loc_1004729C
0x1004728c  cmp     [ebp+var_10170], edx
0x10047292  jnz     short loc_1004729C
0x10047294  test    ecx, ecx
0x10047296  jz      loc_10048BC1
0x1004729c  cmp     dword ptr [eax+10h], 2
0x100472a0  jnz     loc_10048BB4
0x100472a6  cmp     dword ptr [eax+14h], 0
0x100472aa  jz      loc_10048BB4
0x100472b0  test    edx, edx
0x100472b2  jz      loc_10047388
0x100472b8  push    10h; Size
0x100472ba  call    ??2@YAPAXI@Z; operator new(uint)
0x100472bf  mov     ecx, eax; this
0x100472c1  add     esp, 4
0x100472c4  mov     [ebp+var_10164], ecx
0x100472ca  mov     [ebp+var_10138], ecx
0x100472d0  test    ecx, ecx
0x100472d2  jz      loc_1004735C
0x100472d8  push    0; int
0x100472da  lea     eax, [ebp+var_10120]
0x100472e0  mov     dword ptr [ecx], offset ??_7ColumnData@@6B@; const ColumnData::`vftable'
0x100472e6  push    eax; int *
0x100472e7  mov     eax, [ebp+var_10150]
0x100472ed  mov     dword ptr [ecx+4], 0
0x100472f4  mov     dword ptr [ecx+8], 0
0x100472fb  mov     dword ptr [ecx+0Ch], 0
0x10047302  push    dword ptr [eax+14h]; unsigned __int16 *
0x10047305  push    edi; void *
0x10047306  push    [ebp+var_10128]; unsigned __int16 *
0x1004730c  call    ?FInit@ColumnData@@QAEJKKPBGAAJH@Z; ColumnData::FInit(ulong,ulong,ushort const *,long &,int)
0x10047311  mov     edi, eax
0x10047313  mov     [ebp+var_10118], edi
0x10047319  test    edi, edi
0x1004731b  jns     short loc_10047376
0x1004731d  mov     eax, [ebp+var_10120]
0x10047323  cmp     eax, 0FFFFF88Dh
0x10047328  jz      short loc_1004734C
0x1004732a  cmp     eax, 0FFFFF8EFh
0x1004732f  jz      short loc_1004734C
0x10047331  cmp     eax, 0FFFFFAE7h
0x10047336  jnz     loc_10048B8F
0x1004733c  mov     edi, 80040E37h
0x10047341  mov     [ebp+var_10118], edi
0x10047347  jmp     loc_10048B8F
0x1004734c  mov     edi, 80040E09h
0x10047351  mov     [ebp+var_10118], edi
0x10047357  jmp     loc_10048B8F
0x1004735c  mov     [ebp+var_10164], 0
0x10047366  mov     edi, 8007000Eh
0x1004736b  mov     [ebp+var_10118], edi
0x10047371  jmp     loc_10048B8F
0x10047376  mov     edi, [ebp+var_10140]
0x1004737c  mov     eax, [ebp+var_10150]
0x10047382  mov     ecx, [ebp+var_10158]
0x10047388  test    ecx, ecx
0x1004738a  jz      loc_100474FA
0x10047390  lea     ecx, [ebp+var_10138]
0x10047396  mov     edx, edi
0x10047398  push    ecx; int *
0x10047399  push    0; unsigned int
0x1004739b  lea     ecx, [ebp+var_10120]
0x100473a1  push    ecx; unsigned int
0x100473a2  sub     esp, 8
0x100473a5  lea     ecx, [ebp+var_100F0]
0x100473ab  push    ecx; unsigned __int16 *
0x100473ac  mov     ecx, [ebp+var_10128]
0x100473b2  push    0; unsigned int
0x100473b4  push    dword ptr [eax+14h]; unsigned int
0x100473b7  call    ?JOLTJetGetIndexInfo@CJOLT@@SGJKKPBG0PAXKKAAJHAAH@Z; CJOLT::JOLTJetGetIndexInfo(ulong,ulong,ushort const *,ushort const *,void *,ulong,ulong,long &,int,int &)
0x100473bc  mov     edi, eax
0x100473be  mov     [ebp+var_10118], edi
0x100473c4  test    edi, edi
0x100473c6  js      loc_10048B8F
0x100473cc  mov     edi, [ebp+var_10140]
0x100473d2  lea     eax, [ebp+var_100B4]
0x100473d8  push    2Ch ; ','
0x100473da  push    eax
0x100473db  mov     eax, [ebp+var_10150]
0x100473e1  push    0
0x100473e3  push    dword ptr [eax+14h]
0x100473e6  push    edi
0x100473e7  push    [ebp+var_10128]
0x100473ed  call    ds:__imp__JetGetRelationshipInfo@24; JetGetRelationshipInfo(x,x,x,x,x,x)
0x100473f3  mov     [ebp+var_10120], eax
0x100473f9  cmp     eax, 0FFFFFC17h
0x100473fe  jz      short loc_10047414
0x10047400  test    eax, eax
0x10047402  jns     short loc_1004741E
0x10047404  mov     edi, 80004005h
0x10047409  mov     [ebp+var_10118], edi
0x1004740f  jmp     loc_10048B8F
0x10047414  mov     [ebp+var_100AC], 0
0x1004741e  push    0
0x10047420  push    0
0x10047422  lea     eax, [ebp+var_1014C]
0x10047428  push    eax
0x10047429  lea     eax, [ebp+pvData]
0x1004742f  push    eax
0x10047430  push    0FFDCh
0x10047435  lea     eax, [ebp+var_10070]
0x1004743b  push    eax
0x1004743c  mov     eax, [ebp+var_10150]
0x10047442  push    offset aCheckconstrain; "CheckConstraints"
0x10047447  push    0
0x10047449  push    dword ptr [eax+14h]
0x1004744c  push    offset aTables; "Tables"
0x10047451  push    edi
0x10047452  push    [ebp+var_10128]
0x10047458  call    ds:__imp__JetRetrieveProperty@48; JetRetrieveProperty(x,x,x,x,x,x,x,x,x,x,x,x)
0x1004745e  mov     [ebp+var_10120], eax
0x10047464  cmp     eax, 0FFFFF1EEh
0x10047469  jz      short loc_100474E5
0x1004746b  cmp     eax, 0FFFFF1F0h
0x10047470  jz      short loc_100474E5
0x10047472  test    eax, eax
0x10047474  jz      short loc_10047488
0x10047476  jns     short loc_10047488
0x10047478  mov     edi, 80004005h
0x1004747d  mov     [ebp+var_10118], edi
0x10047483  jmp     loc_10048B8F
0x10047488  cmp     [ebp+var_10070], 0
0x10047490  jz      short loc_100474F4
0x10047492  lea     edx, [ebp+var_10070]
0x10047498  xor     esi, esi
0x1004749a  nop     word ptr [eax+eax+00h]
0x100474a0  mov     ecx, edx
0x100474a2  lea     edi, [ecx+2]
0x100474a5  mov     ax, [ecx]
0x100474a8  add     ecx, 2
0x100474ab  test    ax, ax
0x100474ae  jnz     short loc_100474A5
0x100474b0  mov     eax, [ebp+var_10174]
0x100474b6  sub     ecx, edi
0x100474b8  sar     ecx, 1
0x100474ba  lea     edx, [edx+ecx*2]
0x100474bd  add     edx, 2
0x100474c0  test    al, 1
0x100474c2  jz      short loc_100474CA
0x100474c4  lea     esi, [esi+ecx*2]
0x100474c7  add     esi, 2
0x100474ca  inc     eax
0x100474cb  cmp     word ptr [edx], 0
0x100474cf  mov     [ebp+var_10174], eax
0x100474d5  jnz     short loc_100474A0
0x100474d7  mov     [ebp+var_10144], esi
0x100474dd  mov     esi, [ebp+var_10184]
0x100474e3  jmp     short loc_100474F4
0x100474e5  xor     eax, eax
0x100474e7  mov     [ebp+var_10070], ax
0x100474ee  mov     [ebp+var_10120], eax
0x100474f4  mov     ecx, [ebp+var_10158]
0x100474fa  cmp     [ebp+var_10154], 0
0x10047501  jz      short loc_1004756C
0x10047503  cmp     [ebp+var_10160], 0
0x1004750a  jz      short loc_10047523
0x1004750c  mov     eax, [ebp+var_10164]
0x10047512  mov     eax, [eax+4]
0x10047515  lea     edx, [eax+eax*2]
0x10047518  shl     edx, 3
0x1004751b  mov     [ebp+var_1017C], edx
0x10047521  jmp     short loc_10047525
0x10047523  xor     edx, edx
0x10047525  test    ecx, ecx
0x10047527  jz      short loc_10047535
0x10047529  add     edx, [ebp+var_10144]
0x1004752f  mov     [ebp+var_1017C], edx
0x10047535  test    edx, edx
0x10047537  jz      short loc_1004756C
0x10047539  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1004753f  push    edx
0x10047540  push    ecx
0x10047541  mov     eax, [ecx]
0x10047543  mov     edi, [eax+0Ch]
0x10047546  mov     ecx, edi
0x10047548  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
  ... truncated ...
```
