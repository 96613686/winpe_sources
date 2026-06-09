# CSRSTableConstraints::FInit(CDBSession *,ulong,tagVARIANT const * const,CRowsetProperties const &)

- ea: `0x1003b4c0`
- end: `0x1003c972`
- name: `?FInit@CSRSTableConstraints@@QAGJPAVCDBSession@@KQBUtagVARIANT@@ABVCRowsetProperties@@@Z`
- size: `5298`
- prototype: `int __userpurge@<eax>(_DWORD *@<edx>, int@<ecx>, CSRSTableConstraints *this, struct CDBSession *, unsigned int, const struct tagVARIANT *const, const struct CRowsetProperties *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x10034e00`

## callees

- `0x1000d4a0`
- `0x1000d570`
- `0x10013020`
- `0x10013100`
- `0x10017880`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10028340`
- `0x10035e60`
- `0x1003b4c0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d420`
- `0x1004d5a1`
- `0x1004dc8d`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1003b9fa`
- `msvcrt!_wcsicmp` at `0x1003bb07`
- `msvcrt!_wcsicmp` at `0x1003bb90`
- `msvcrt!_wcsicmp` at `0x1003bc81`
- `msvcrt!_wcsicmp` at `0x1003bf39`
- `msvcrt!_wcsicmp` at `0x1003c02b`
- `msvcrt!_wcsicmp` at `0x1003c242`
- `msvcrt!_wcsicmp` at `0x1003b9fa`
- `msvcrt!_wcsicmp` at `0x1003bb07`
- `msvcrt!_wcsicmp` at `0x1003bb90`
- `msvcrt!_wcsicmp` at `0x1003bc81`
- `msvcrt!_wcsicmp` at `0x1003bf39`
- `msvcrt!_wcsicmp` at `0x1003c02b`
- `msvcrt!_wcsicmp` at `0x1003c242`
- `msjet40!__imp__JetCloseTable@8` at `0x1003be28`
- `msjet40!__imp__JetCloseTable@8` at `0x1003c78f`
- `msjet40!__imp__JetCloseTable@8` at `0x1003c85c`
- `msjet40!__imp__JetCloseTable@8` at `0x1003c8dd`
- `msjet40!__imp__JetCloseTable@8` at `0x1003c8ee`
- `msjet40!__imp__JetCloseTable@8` at `0x1003be28`
- `msjet40!__imp__JetCloseTable@8` at `0x1003c78f`
- `msjet40!__imp__JetCloseTable@8` at `0x1003c85c`
- `msjet40!__imp__JetCloseTable@8` at `0x1003c8dd`
- `msjet40!__imp__JetCloseTable@8` at `0x1003c8ee`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003c8be`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003c8be`
- `msjet40!__imp__JetGetIndexInfo@28` at `0x1003ba3a`
- `msjet40!__imp__JetGetIndexInfo@28` at `0x1003ba3a`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x1003b84f`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x1003b84f`
- `msjet40!__imp__JetMove@16` at `0x1003b87a`
- `msjet40!__imp__JetMove@16` at `0x1003b986`
- `msjet40!__imp__JetMove@16` at `0x1003ba13`
- `msjet40!__imp__JetMove@16` at `0x1003bb20`
- `msjet40!__imp__JetMove@16` at `0x1003bd52`
- `msjet40!__imp__JetMove@16` at `0x1003c485`
- `msjet40!__imp__JetMove@16` at `0x1003c767`
- `msjet40!__imp__JetMove@16` at `0x1003b87a`
- `msjet40!__imp__JetMove@16` at `0x1003b986`
- `msjet40!__imp__JetMove@16` at `0x1003ba13`
- `msjet40!__imp__JetMove@16` at `0x1003bb20`
- `msjet40!__imp__JetMove@16` at `0x1003bd52`
- `msjet40!__imp__JetMove@16` at `0x1003c485`
- `msjet40!__imp__JetMove@16` at `0x1003c767`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003bba8`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003bc99`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003bef7`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003c167`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003c387`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003c6ab`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003bba8`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003bc99`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003bef7`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003c167`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003c387`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003c6ab`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003b955`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003b9b6`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003bac3`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003bb4e`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003bd8c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003c566`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003c5b7`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003b955`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003b9b6`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003bac3`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003bb4e`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003bd8c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003c566`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003c5b7`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bbd4`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bbf6`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bc31`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bcc5`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bce7`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bd22`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bf68`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bfb3`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bfd3`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c191`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c1af`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c1cb`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c3ce`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c3f0`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c42b`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c6d7`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c6f9`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c73b`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bbd4`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bbf6`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bc31`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bcc5`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bce7`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bd22`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bf68`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bfb3`
- `msjet40!__imp__JetSetColumn@28` at `0x1003bfd3`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c191`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c1af`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c1cb`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c3ce`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c3f0`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c42b`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c6d7`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c6f9`
- `msjet40!__imp__JetSetColumn@28` at `0x1003c73b`
- `msjet40!__imp__JetUpdate@20` at `0x1003bc42`
- `msjet40!__imp__JetUpdate@20` at `0x1003bd33`
- `msjet40!__imp__JetUpdate@20` at `0x1003bfeb`
- `msjet40!__imp__JetUpdate@20` at `0x1003c1dc`
- `msjet40!__imp__JetUpdate@20` at `0x1003c43c`
- `msjet40!__imp__JetUpdate@20` at `0x1003c74c`
- `msjet40!__imp__JetUpdate@20` at `0x1003bc42`
- `msjet40!__imp__JetUpdate@20` at `0x1003bd33`
- `msjet40!__imp__JetUpdate@20` at `0x1003bfeb`
- `msjet40!__imp__JetUpdate@20` at `0x1003c1dc`
- `msjet40!__imp__JetUpdate@20` at `0x1003c43c`
- `msjet40!__imp__JetUpdate@20` at `0x1003c74c`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1003be69`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1003c121`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1003c2b5`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1003be69`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1003c121`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1003c2b5`
- `msjet40!__imp__JetGetRelationshipInfo@24` at `0x1003c503`
- `msjet40!__imp__JetGetRelationshipInfo@24` at `0x1003c503`

## pseudocode

```c
int __userpurge CSRSTableConstraints::FInit@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        CSRSTableConstraints *this,
        struct CDBSession *a4,
        unsigned int a5,
        const struct tagVARIANT *const a6,
        const struct CRowsetProperties *a7)
{
  JET_SESID v8; // esi
  int v9; // edi
  int v10; // edi
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // esi
  int v21; // eax
  int v22; // eax
  JET_COLUMNID *v23; // eax
  int v24; // eax
  _DWORD *v25; // edi
  JET_ERR v26; // eax
  JET_ERR v27; // eax
  signed int IndexInfo; // eax
  unsigned int v29; // ecx
  JET_TABLEID v30; // eax
  unsigned int v31; // edi
  char v32; // cl
  int v33; // eax
  int v34; // eax
  int v35; // esi
  JET_SESID v36; // edi
  signed int v37; // eax
  wchar_t *v38; // edx
  wchar_t *v39; // edi
  unsigned int v40; // esi
  const wchar_t *v41; // eax
  int v42; // eax
  int v43; // ecx
  unsigned int v44; // esi
  const unsigned __int16 *v45; // edx
  ColumnData *v46; // eax
  ColumnData *v47; // edi
  _DWORD *v48; // eax
  _WORD *v49; // edi
  signed int v50; // eax
  bool v51; // zf
  JET_COLUMNID *v52; // edi
  JET_ERR v53; // eax
  ColumnData *v54; // eax
  unsigned int v55; // edi
  _DWORD *v56; // ecx
  const wchar_t *v57; // eax
  int v58; // eax
  int v59; // ecx
  int v60; // esi
  int v61; // eax
  int v62; // eax
  signed int v63; // eax
  signed int RelationshipInfo; // eax
  unsigned int v65; // ecx
  JET_TABLEID v66; // eax
  unsigned int v67; // esi
  JET_SESID v68; // edi
  struct CDBSession *v69; // eax
  int v70; // eax
  int v71; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v72; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v73; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v74; // esi
  int v75; // ecx
  int v76; // eax
  unsigned int v78; // [esp-18h] [ebp-454h]
  int v79; // [esp-4h] [ebp-440h]
  const unsigned __int16 *v80; // [esp+Ch] [ebp-430h]
  const unsigned __int16 *v81; // [esp+Ch] [ebp-430h]
  const unsigned __int16 *v82; // [esp+Ch] [ebp-430h]
  const unsigned __int16 *v83; // [esp+Ch] [ebp-430h]
  const struct _GUID *v84; // [esp+10h] [ebp-42Ch]
  unsigned int v85; // [esp+10h] [ebp-42Ch]
  unsigned int v86; // [esp+10h] [ebp-42Ch]
  unsigned int v87; // [esp+10h] [ebp-42Ch]
  int v88; // [esp+14h] [ebp-428h]
  unsigned int ObjectInfo; // [esp+18h] [ebp-424h] BYREF
  JET_TABLEID v90; // [esp+1Ch] [ebp-420h] BYREF
  JET_SESID sesid; // [esp+20h] [ebp-41Ch]
  JET_COLUMNID *v92; // [esp+24h] [ebp-418h]
  int v93; // [esp+28h] [ebp-414h]
  struct CDBSession *v94; // [esp+2Ch] [ebp-410h]
  _DWORD *v95; // [esp+30h] [ebp-40Ch]
  ColumnData *v96; // [esp+34h] [ebp-408h]
  unsigned int pcbActual; // [esp+38h] [ebp-404h] BYREF
  int v98; // [esp+3Ch] [ebp-400h]
  int v99; // [esp+40h] [ebp-3FCh]
  unsigned int v100; // [esp+44h] [ebp-3F8h] BYREF
  unsigned int cbData; // [esp+48h] [ebp-3F4h] BYREF
  unsigned int v102; // [esp+4Ch] [ebp-3F0h] BYREF
  void *Block; // [esp+50h] [ebp-3ECh]
  int v104; // [esp+54h] [ebp-3E8h]
  wchar_t *v105; // [esp+58h] [ebp-3E4h]
  int v106; // [esp+5Ch] [ebp-3E0h]
  char v107[4]; // [esp+60h] [ebp-3DCh] BYREF
  int v108; // [esp+64h] [ebp-3D8h]
  int v109; // [esp+68h] [ebp-3D4h] BYREF
  unsigned int v110; // [esp+6Ch] [ebp-3D0h]
  int pvData; // [esp+70h] [ebp-3CCh] BYREF
  unsigned int v112; // [esp+74h] [ebp-3C8h] BYREF
  char v113[4]; // [esp+78h] [ebp-3C4h] BYREF
  JET_TABLEID v114; // [esp+7Ch] [ebp-3C0h]
  unsigned int v115; // [esp+80h] [ebp-3BCh]
  JET_COLUMNID v116; // [esp+84h] [ebp-3B8h]
  JET_COLUMNID v117; // [esp+94h] [ebp-3A8h]
  JET_TABLEID v118[12]; // [esp+A4h] [ebp-398h] BYREF
  int v119; // [esp+D4h] [ebp-368h] BYREF
  JET_TABLEID v120; // [esp+D8h] [ebp-364h]
  unsigned int v121; // [esp+DCh] [ebp-360h]
  JET_COLUMNID v122; // [esp+E0h] [ebp-35Ch]
  JET_COLUMNID v123; // [esp+E4h] [ebp-358h]
  wchar_t v124[6]; // [esp+110h] [ebp-32Ch] BYREF
  wchar_t String1[8]; // [esp+11Ch] [ebp-320h] BYREF
  __int128 v126; // [esp+12Ch] [ebp-310h] BYREF
  __int64 v127; // [esp+13Ch] [ebp-300h]
  int v128; // [esp+144h] [ebp-2F8h]
  wchar_t v129; // [esp+148h] [ebp-2F4h]
  wchar_t v130[16]; // [esp+14Ch] [ebp-2F0h] BYREF
  __int128 v131; // [esp+16Ch] [ebp-2D0h] BYREF
  __int64 v132; // [esp+17Ch] [ebp-2C0h]
  wchar_t String2[64]; // [esp+194h] [ebp-2A8h] BYREF
  _OWORD v134[2]; // [esp+21Ch] [ebp-220h] BYREF
  wchar_t v135; // [esp+23Ch] [ebp-200h]
  wchar_t v136[68]; // [esp+254h] [ebp-1E8h] BYREF
  unsigned __int16 v137[104]; // [esp+2DCh] [ebp-160h] BYREF
  unsigned __int16 v138[70]; // [esp+3ACh] [ebp-90h] BYREF

  v94 = a4;
  v110 = a5;
  v95 = a1;
  v109 = a2;
  memset(v118, 0, sizeof(v118));
  v8 = a1[4];
  wcscpy(String1, L"UNIQUE");
  v9 = 0;
  v96 = 0;
  wcscpy(v130, L"PRIMARY KEY");
  wcscpy(v124, L"CHECK");
  v131 = *(_OWORD *)L"FOREIGN KEY";
  ObjectInfo = 0;
  sesid = v8;
  v92 = 0;
  v90 = 0;
  v104 = 0;
  v106 = 0;
  v93 = 0;
  v98 = 1;
  v108 = 0;
  v132 = *(_QWORD *)L"KEY";
  Block = 0;
  v105 = (wchar_t *)operator new(0xFFDEu);
  if ( !v105 )
  {
    v10 = -2147024882;
    v88 = -2147024882;
    goto LABEL_234;
  }
  Block = operator new(0xFFDCu);
  if ( !Block )
  {
    v10 = -2147024882;
    v88 = -2147024882;
    goto LABEL_234;
  }
  if ( !this )
    goto LABEL_45;
  if ( !v94 )
    goto LABEL_39;
  if ( (unsigned int)this > 7 )
    goto LABEL_39;
  v11 = *(unsigned __int16 *)v94;
  if ( (_WORD)v11 )
  {
    if ( v11 != 1 && (v11 != 8 || *((_DWORD *)v94 + 2)) )
      goto LABEL_39;
  }
  if ( (unsigned int)this > 1 )
  {
    v12 = *((unsigned __int16 *)v94 + 8);
    if ( (_WORD)v12 )
    {
      if ( v12 != 1 && (v12 != 8 || *((_DWORD *)v94 + 6)) )
        goto LABEL_39;
    }
  }
  if ( (unsigned int)this > 2 )
  {
    v13 = *((unsigned __int16 *)v94 + 16);
    if ( (_WORD)v13 )
    {
      if ( v13 != 1 && v13 != 8 )
        goto LABEL_39;
    }
  }
  if ( (unsigned int)this > 3 )
  {
    v14 = *((unsigned __int16 *)v94 + 24);
    if ( (_WORD)v14 )
    {
      if ( v14 != 1 && (v14 != 8 || *((_DWORD *)v94 + 14)) )
        goto LABEL_39;
    }
  }
  if ( (unsigned int)this > 4 )
  {
    v15 = *((unsigned __int16 *)v94 + 32);
    if ( (_WORD)v15 )
    {
      if ( v15 != 1 && (v15 != 8 || *((_DWORD *)v94 + 18)) )
        goto LABEL_39;
    }
  }
  if ( (unsigned int)this > 5 )
  {
    v16 = *((unsigned __int16 *)v94 + 40);
    if ( (_WORD)v16 )
    {
      if ( v16 != 1 && v16 != 8 )
        goto LABEL_39;
    }
  }
  if ( (unsigned int)this <= 6 )
  {
    if ( (unsigned int)this < 3 )
    {
LABEL_45:
      v20 = 1;
      goto LABEL_46;
    }
  }
  else
  {
    v17 = *((unsigned __int16 *)v94 + 48);
    if ( (_WORD)v17 && v17 != 1 && v17 != 8 )
    {
LABEL_39:
      v10 = -2147024809;
      v88 = -2147024809;
      goto LABEL_234;
    }
  }
  v18 = *((unsigned __int16 *)v94 + 16);
  if ( !(_WORD)v18 )
    goto LABEL_45;
  if ( v18 == 1 )
    goto LABEL_45;
  v19 = *((_DWORD *)v94 + 10);
  v104 = 1;
  v108 = v19;
  if ( v19 )
    goto LABEL_45;
  v20 = 0;
  v98 = 0;
LABEL_46:
  if ( (unsigned int)this >= 6 )
  {
    v21 = *((unsigned __int16 *)v94 + 40);
    if ( (_WORD)v21 )
    {
      if ( v21 != 1 )
      {
        v9 = *((_DWORD *)v94 + 22);
        v106 = 1;
        if ( !v9 )
          v20 = 0;
        v98 = v20;
      }
    }
  }
  if ( (unsigned int)this < 7 )
    goto LABEL_58;
  v22 = *((unsigned __int16 *)v94 + 48);
  if ( (_WORD)v22 && v22 != 1 )
  {
    v51 = *((_DWORD *)v94 + 26) == 0;
    v93 = 1;
    if ( v51 )
    {
      v98 = 0;
      v93 = 1;
      goto LABEL_59;
    }
LABEL_58:
    if ( (unsigned int)this < 3 )
      goto LABEL_60;
    goto LABEL_59;
  }
  v93 = 0;
LABEL_59:
  if ( *((_WORD *)v94 + 16) == 1 )
  {
LABEL_64:
    v98 = 0;
    goto LABEL_65;
  }
LABEL_60:
  if ( (unsigned int)this >= 6 && *((_WORD *)v94 + 40) == 1 || (unsigned int)this >= 7 && *((_WORD *)v94 + 48) == 1 )
    goto LABEL_64;
LABEL_65:
  v23 = (JET_COLUMNID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          40);
  v92 = v23;
  if ( !v23 )
  {
LABEL_66:
    v10 = -2147024882;
    v88 = -2147024882;
LABEL_67:
    v8 = sesid;
    goto LABEL_234;
  }
  v24 = SRSCreateTempTable(9, v95, &v90, v23, 2u);
  v8 = sesid;
  v88 = v24;
  if ( v24 < 0 )
  {
    v10 = v24;
    goto LABEL_234;
  }
  v79 = v9;
  v25 = v95;
  ObjectInfo = JetGetObjectInfo(sesid, v95[5], 0, L"tables", v79, v118, 48, 1);
  if ( ObjectInfo )
  {
LABEL_70:
    v10 = -2147467259;
    v88 = -2147467259;
    goto LABEL_234;
  }
  v26 = JetMove(v8, v118[1], 0x80000000, 0);
  ObjectInfo = v26;
  if ( v26 != -1603 && v26 )
  {
    v10 = -2147467259;
    v88 = -2147467259;
    goto LABEL_234;
  }
  v100 = 0;
  if ( v118[2] )
  {
    while ( 1 )
    {
      if ( !v98 )
        goto LABEL_187;
      v128 = *(_DWORD *)L"le";
      v129 = aValidationrule[14];
      v135 = aCheckconstrain[16];
      String2[0] = 0;
      v136[0] = 0;
      v126 = *(_OWORD *)L"ValidationRule";
      v127 = *(_QWORD *)L"onRule";
      v134[0] = *(_OWORD *)L"CheckConstraints";
      v134[1] = *(_OWORD *)L"straints";
      ObjectInfo = JetRetrieveColumn(v8, v118[1], v118[5], &pvData, 4u, &pcbActual, 0, 0);
      if ( ObjectInfo )
        goto LABEL_233;
      if ( pvData == 1 || pvData == 4 || pvData == 6 )
      {
        ObjectInfo = JetRetrieveColumn(v8, v118[1], v118[4], String2, 0x81u, &pcbActual, 0, 0);
        if ( ObjectInfo )
          goto LABEL_70;
        if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
LABEL_253:
          __report_rangecheckfailure();
        v51 = v106 == 1;
        *(wchar_t *)((char *)String2 + (pcbActual & 0xFFFFFFFE)) = 0;
        if ( !v51 || !__wcsicmp(*((const wchar_t **)v94 + 22), String2) )
          break;
      }
      v27 = JetMove(v8, v118[1], 1, 0);
LABEL_186:
      ObjectInfo = v27;
      if ( ++v100 >= v118[2] )
        goto LABEL_187;
    }
    IndexInfo = JetGetIndexInfo(v8, v25[5], String2, v108, &v119, 60, 1);
    ObjectInfo = IndexInfo;
    if ( IndexInfo > -1404 )
    {
      if ( IndexInfo )
        goto LABEL_70;
      v29 = v121;
      v30 = v120;
    }
    else
    {
      if ( IndexInfo != -1404 && IndexInfo != -1907 && IndexInfo != -1811 )
        goto LABEL_70;
      v29 = 0;
      ObjectInfo = 0;
      v30 = -1;
      v121 = 0;
      v120 = -1;
    }
    v31 = 0;
    v88 = 0;
    if ( v29 )
    {
      while ( 1 )
      {
        ObjectInfo = JetRetrieveColumn(v8, v30, v122, v136, 0x81u, &cbData, 0, 0);
        if ( ObjectInfo )
          goto LABEL_70;
        if ( (cbData & 0xFFFFFFFE) >= 0x82 )
          goto LABEL_253;
        v51 = v104 == 1;
        *(wchar_t *)((char *)v136 + (cbData & 0xFFFFFFFE)) = 0;
        if ( v51 && __wcsicmp(*((const wchar_t **)v94 + 10), v136) )
        {
          ObjectInfo = JetMove(v8, v120, 1, 0);
          goto LABEL_120;
        }
        ObjectInfo = JetRetrieveColumn(v8, v120, v123, v107, 4u, &v112, 0, 0);
        if ( ObjectInfo )
          goto LABEL_70;
        v32 = v107[0];
        v33 = v93;
        if ( (v107[0] & 3) == 1 )
        {
          if ( !v93 )
            goto LABEL_103;
          if ( v93 == 1 )
            break;
        }
LABEL_106:
        if ( (v32 & 2) != 0 && (!v33 || v33 == 1 && !__wcsicmp(v130, *((const wchar_t **)v94 + 26))) )
        {
          ObjectInfo = JetPrepareUpdate(v8, v90, 0);
          if ( ObjectInfo )
            goto LABEL_70;
          JetSetColumn(v8, v90, v92[2], v136, cbData, 0, 0);
          JetSetColumn(v8, v90, v92[5], String2, pcbActual, 0, 0);
          JetSetColumn(v8, v90, v92[6], v130, 2 * wcslen(v130), 0, 0);
          ObjectInfo = JetUpdate(v8, v90, 0, 0, 0);
          if ( ObjectInfo )
            goto LABEL_70;
        }
        while ( 1 )
        {
          ++v31;
          ObjectInfo = JetMove(v8, v120, 1, 0);
          if ( ObjectInfo == -1603 )
            break;
          ObjectInfo = JetRetrieveColumn(v8, v120, v122, v138, 0x82u, &cbData, 0, 0);
          if ( ObjectInfo )
            goto LABEL_70;
          if ( (cbData & 0xFFFFFFFE) >= 0x82 )
            goto LABEL_253;
          *(unsigned __int16 *)((char *)v138 + (cbData & 0xFFFFFFFE)) = 0;
          v34 = wcscmp(v138, v136);
          if ( v34 )
            v34 = v34 < 0 ? -1 : 1;
          if ( v34 )
            goto LABEL_120;
        }
        ObjectInfo = 0;
LABEL_120:
        v30 = v120;
        if ( v31 >= v121 )
          goto LABEL_121;
      }
      if ( !__wcsicmp(String1, *((const wchar_t **)v94 + 26)) )
      {
LABEL_103:
        ObjectInfo = JetPrepareUpdate(v8, v90, 0);
        if ( ObjectInfo )
          goto LABEL_70;
        JetSetColumn(v8, v90, v92[2], v136, cbData, 0, 0);
        JetSetColumn(v8, v90, v92[5], String2, pcbActual, 0, 0);
        JetSetColumn(v8, v90, v92[6], String1, 2 * wcslen(String1), 0, 0);
        ObjectInfo = JetUpdate(v8, v90, 0, 0, 0);
        if ( ObjectInfo )
          goto LABEL_70;
      }
      v32 = v107[0];
      v33 = v93;
      goto LABEL_106;
    }
LABEL_121:
    v35 = v93;
    v36 = sesid;
    if ( v30 != -1 )
    {
      ObjectInfo = JetCloseTable(sesid, v30);
      if ( ObjectInfo )
        goto LABEL_127;
    }
    v37 = JetRetrieveProperty(v36, v95[5], L"Tables", String2, 0, v134, v105, 65500, &v102, 0, 0, 0);
    ObjectInfo = v37;
    if ( v37 > -1907 )
    {
      if ( v37 )
        goto LABEL_127;
      v38 = v105;
      v39 = v105;
      v93 = v35;
      if ( *v105 )
      {
        v93 = v35;
        v8 = sesid;
        while ( v39 - v38 < v102 >> 1 )
        {
          v99 = 1;
          ObjectInfo = JetPrepareUpdate(v8, v90, 0);
          if ( ObjectInfo )
            goto LABEL_70;
          v40 = wcslen(v39);
          if ( v93 )
          {
            if ( (unsigned int)this > 2 )
            {
              v41 = (const wchar_t *)*((_DWORD *)v94 + 10);
              if ( v41 )
              {
                v42 = __wcsicmp(v41, v39);
                v43 = v99;
                if ( v42 )
                  v43 = 0;
                v99 = v43;
              }
            }
          }
          v44 = v40;
          JetSetColumn(sesid, v90, v92[2], v39, v44 * 2, 0, 0);
          v45 = &v39[v44 + 1];
          v8 = sesid;
          v39 = (wchar_t *)&v45[wcslen(v45) + 1];
          JetSetColumn(sesid, v90, v92[5], String2, pcbActual, 0, 0);
          JetSetColumn(v8, v90, v92[6], v124, 0xCu, 0, 0);
          if ( v99 == 1 )
          {
            ObjectInfo = JetUpdate(v8, v90, 0, 0, 0);
            if ( ObjectInfo )
              goto LABEL_70;
          }
          v38 = v105;
          if ( !*v39 )
            break;
        }
      }
    }
    else if ( v37 != -1907 && v37 != -3602 && v37 != -3600 )
    {
LABEL_127:
      v8 = sesid;
      v10 = -2147467259;
      v88 = -2147467259;
      goto LABEL_234;
    }
    if ( v93 && (v93 != 1 || __wcsicmp(v124, *((const wchar_t **)v94 + 26))) )
    {
LABEL_184:
      v8 = sesid;
LABEL_185:
      v27 = JetMove(v8, v118[1], 1, 0);
      v25 = v95;
      goto LABEL_186;
    }
    if ( v96 )
      (*(void (__thiscall **)(ColumnData *, int))(*(_DWORD *)v96 + 4))(v96, 1);
    v46 = (ColumnData *)operator new(0x10u);
    v8 = sesid;
    v47 = v46;
    v96 = v46;
    v99 = (int)v46;
    if ( !v46 )
    {
      v10 = -2147024882;
      v96 = 0;
      v88 = -2147024882;
      goto LABEL_234;
    }
    *(_DWORD *)v46 = &ColumnData::`vftable';
    *((_DWORD *)v46 + 1) = 0;
    v48 = v95;
    *((_DWORD *)v47 + 2) = 0;
    *((_DWORD *)v47 + 3) = 0;
    v88 = ColumnData::FInit(v47, v8, v48[5], String2, (int *)&ObjectInfo, 0);
    if ( v88 < 0 )
    {
      (*(void (__thiscall **)(ColumnData *, int))(*(_DWORD *)v47 + 4))(v47, 1);
      v8 = sesid;
      v96 = 0;
      if ( ObjectInfo != -1907 )
      {
LABEL_233:
        v10 = v88;
        goto LABEL_234;
      }
      ObjectInfo = 0;
    }
    v49 = Block;
    v50 = JetRetrieveProperty(v8, v95[5], L"tables", String2, 0, &v126, Block, 65500, &v102, 0, 0, 0);
    ObjectInfo = v50;
    if ( v50 > -1907 )
    {
      if ( v50 )
        goto LABEL_70;
      v49[v102 >> 1] = 0;
      ObjectInfo = JetPrepareUpdate(v8, v90, 0);
      if ( ObjectInfo )
        goto LABEL_70;
      v52 = v92;
      JetSetColumn(v8, v90, v92[2], &v126, 0x1Eu, 0, 0);
      JetSetColumn(v8, v90, v52[5], String2, pcbActual, 0, 0);
      JetSetColumn(v8, v90, v52[6], v124, 0xCu, 0, 0);
      v53 = JetUpdate(v8, v90, 0, 0, 0);
      v51 = v53 == 0;
      ObjectInfo = v53;
    }
    else
    {
      if ( v50 == -1907 || v50 == -3602 )
        goto LABEL_159;
      v51 = v50 == -3600;
    }
    if ( !v51 )
      goto LABEL_70;
LABEL_159:
    v54 = v96;
    v55 = 0;
    if ( v96 )
    {
      while ( 1 )
      {
        if ( v55 >= *((_DWORD *)v54 + 1) )
        {
          (*(void (__thiscall **)(ColumnData *, int))(*(_DWORD *)v54 + 4))(v96, 1);
          v96 = 0;
          goto LABEL_184;
        }
        if ( v104 == 1 )
        {
          v56 = (_DWORD *)(*((_DWORD *)v54 + 3) + 104 * v55);
          v57 = (const wchar_t *)v56[1];
          if ( !v57 )
          {
            v58 = v56[6];
            if ( v58 && (unsigned int)(v58 - 2) >= 2 )
              v57 = 0;
            else
              v57 = (const wchar_t *)v56[7];
          }
          if ( __wcsicmp(v57, *((const wchar_t **)v94 + 10)) )
            goto LABEL_182;
          v54 = v96;
        }
        v59 = *((_DWORD *)v54 + 3);
        v60 = 104 * v55;
        v61 = *(_DWORD *)(v59 + 104 * v55 + 4);
        if ( !v61 )
        {
          v62 = *(_DWORD *)(v59 + v60 + 24);
          if ( v62 && (unsigned int)(v62 - 2) >= 2 )
            v61 = 0;
          else
            v61 = *(_DWORD *)(v59 + v60 + 28);
        }
        v63 = JetRetrieveProperty(sesid, v95[5], L"tables", String2, v61, &v126, Block, 65500, &v102, 0, 0, 0);
        ObjectInfo = v63;
        if ( v63 > -1907 )
        {
          if ( v63 )
            goto LABEL_127;
          *((_WORD *)Block + (v102 >> 1)) = 0;
          v137[0] = 0;
          WCSCPY((unsigned __int16 *)0x68, v80, (unsigned int)v84);
          WCSCAT((unsigned __int16 *)0x68, v81, v85);
          WCSCAT((unsigned __int16 *)0x68, v82, v86);
          WCSCAT((unsigned __int16 *)0x68, v83, v87);
          v8 = sesid;
          ObjectInfo = JetPrepareUpdate(sesid, v90, 0);
          if ( ObjectInfo )
            goto LABEL_70;
          JetSetColumn(v8, v90, v92[2], v137, 2 * wcslen(v137), 0, 0);
          JetSetColumn(v8, v90, v92[5], String2, pcbActual, 0, 0);
          JetSetColumn(v8, v90, v92[6], v124, 2 * wcslen(v124), 0, 0);
          ObjectInfo = JetUpdate(v8, v90, 0, 0, 0);
          if ( ObjectInfo )
            goto LABEL_70;
LABEL_182:
          v54 = v96;
          ++v55;
        }
        else
        {
          if ( v63 == -1907 || v63 == -3602 )
            goto LABEL_182;
          if ( v63 != -3600 )
            goto LABEL_127;
          v54 = v96;
          ++v55;
        }
      }
    }
    goto LABEL_185;
  }
LABEL_187:
  if ( v98 != 1 )
    goto LABEL_227;
  if ( v104 == 1 && *((_WORD *)v94 + 16) )
    RelationshipInfo = JetGetRelationshipInfo(v8, v25[5], 0, *((_DWORD *)v94 + 10), v113, 44);
  else
    RelationshipInfo = JetGetRelationshipInfo(v8, v25[5], 0, 0, v113, 44);
  ObjectInfo = RelationshipInfo;
  if ( RelationshipInfo > -1002 )
  {
    if ( RelationshipInfo != -1001 )
    {
      if ( RelationshipInfo )
      {
        v10 = -2147467259;
        v88 = -2147467259;
        goto LABEL_234;
      }
      v65 = v115;
      v66 = v114;
      goto LABEL_199;
    }
  }
  else if ( RelationshipInfo != -1002 && RelationshipInfo != -1907 && RelationshipInfo != -1305 )
  {
    goto LABEL_70;
  }
  v65 = 0;
  v66 = -1;
  v115 = 0;
  v114 = -1;
LABEL_199:
  v67 = 0;
  if ( v65 )
  {
    v68 = sesid;
    while ( 1 )
    {
      ObjectInfo = JetRetrieveColumn(v68, v66, v116, v137, 0x81u, &v100, 0, 0);
      if ( ObjectInfo )
        goto LABEL_127;
      if ( (v100 & 0xFFFFFFFE) >= 0x82 )
        goto LABEL_253;
      *(unsigned __int16 *)((char *)v137 + (v100 & 0xFFFFFFFE)) = 0;
      ObjectInfo = JetRetrieveColumn(v68, v114, v117, String2, 0x82u, &pcbActual, 0, 0);
      if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
        goto LABEL_253;
      *(wchar_t *)((char *)String2 + (pcbActual & 0xFFFFFFFE)) = 0;
      v69 = v94;
      if ( !v106 || !*((_WORD *)v94 + 40) )
        goto LABEL_215;
      v70 = wcscmp(String2, *((const unsigned __int16 **)v94 + 22));
      if ( v70 )
        v70 = v70 < 0 ? -1 : 1;
      if ( !v70 )
        break;
LABEL_222:
      ++v67;
      ObjectInfo = JetMove(v68, v114, 1, 0);
      v66 = v114;
      if ( v67 >= v115 )
      {
        v25 = v95;
        goto LABEL_224;
      }
    }
    v69 = v94;
LABEL_215:
    if ( !v93 || !*((_WORD *)v69 + 48) )
      goto LABEL_256;
    v71 = wcscmp((const unsigned __int16 *)&v131, *((const unsigned __int16 **)v69 + 26));
    if ( v71 )
      v71 = v71 < 0 ? -1 : 1;
    if ( !v71 )
    {
LABEL_256:
      ObjectInfo = JetPrepareUpdate(v68, v90, 0);
      if ( ObjectInfo )
        goto LABEL_127;
      JetSetColumn(v68, v90, v92[2], v137, v100, 0, 0);
      JetSetColumn(v68, v90, v92[5], String2, pcbActual, 0, 0);
      JetSetColumn(v68, v90, v92[6], &v131, 2 * wcslen((const unsigned __int16 *)&v131), 0, 0);
      ObjectInfo = JetUpdate(v68, v90, 0, 0, 0);
      if ( ObjectInfo )
        goto LABEL_127;
    }
    goto LABEL_222;
  }
LABEL_224:
  if ( v66 != -1 )
  {
    v8 = sesid;
    ObjectInfo = JetCloseTable(sesid, v66);
    if ( ObjectInfo )
    {
      v10 = -2147467259;
      v88 = -2147467259;
      goto LABEL_234;
    }
  }
LABEL_227:
  v72 = (ColumnDataWithFakeNamesAndDBTYPES *)operator new(0x20u);
  v100 = (unsigned int)v72;
  if ( !v72 )
    goto LABEL_66;
  v73 = ColumnDataWithFakeNamesAndDBTYPES::ColumnDataWithFakeNamesAndDBTYPES(v72);
  v74 = v73;
  if ( !v73 )
    goto LABEL_66;
  *((_DWORD *)v73 + 4) = 0;
  *((_DWORD *)v73 + 5) = &SRSTableConstraintsNames;
  *((_DWORD *)v73 + 7) = 0;
  v10 = ColumnData::FInit(v73, sesid, v25[5], v90, (int *)&ObjectInfo, 0, (int)&SRSTableConstraintsNames);
  v88 = v10;
  if ( v10 < 0 )
    goto LABEL_67;
  v75 = v109;
  v78 = v110;
  *((_DWORD *)v74 + 1) = 10;
  v76 = CRowset::FInit(v75, 0, v95, 0, 0, 0, v90, v78, 1, 0, 0, v74, 1, 0, 0, &GUID_NULL);
  v8 = sesid;
  v10 = v76;
  v88 = v76;
  ObjectInfo = JetCloseTable(sesid, v118[1]);
  if ( ObjectInfo )
  {
    v10 = -2147467259;
    v88 = -2147467259;
  }
LABEL_234:
  if ( ObjectInfo )
  {
    CExtError::SendJetErrortoOLEAuto(ObjectInfo, (int)&IID_IDBSchemaRowset, (int)v80, v84);
    if ( v10 >= 0 )
      goto LABEL_243;
  }
  else
  {
    if ( v10 >= 0 )
      goto LABEL_243;
    if ( v10 != -2147024882 && !JetGetDatabaseInfo(v95[4], v95[5], &v109, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_IDBSchemaRowset, 0, (const struct _GUID *)v80, (int)v84);
  }
  JetCloseTable(v8, v118[1]);
  if ( v90 != -1 )
    JetCloseTable(v8, v90);
LABEL_243:
  if ( v96 )
    (*(void (__thiscall **)(ColumnData *, int))(*(_DWORD *)v96 + 4))(v96, 1);
  if ( v105 )
    operator delete(v105);
  if ( Block )
    operator delete(Block);
  if ( v92 && Sys )
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNID *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v92);
  return v88;
}

```

## disassembly

```asm
0x1003b4c0  mov     edi, edi
0x1003b4c2  push    ebp
0x1003b4c3  mov     ebp, esp
0x1003b4c5  and     esp, 0FFFFFFF0h
0x1003b4c8  sub     esp, 428h
0x1003b4ce  mov     eax, ___security_cookie
0x1003b4d3  xor     eax, esp
0x1003b4d5  mov     [esp+428h+var_4], eax
0x1003b4dc  mov     eax, [ebp+arg_4]
0x1003b4df  push    esi; int
0x1003b4e0  push    edi; struct _GUID *
0x1003b4e1  mov     [esp+430h+var_410], eax
0x1003b4e5  mov     esi, edx
0x1003b4e7  mov     eax, [ebp+arg_8]
0x1003b4ea  push    30h ; '0'; Size
0x1003b4ec  mov     [esp+434h+var_3D0], eax
0x1003b4f0  lea     eax, [esp+434h+var_398]
0x1003b4f7  push    0; Val
0x1003b4f9  push    eax; void *
0x1003b4fa  mov     [esp+43Ch+var_40C], esi
0x1003b4fe  mov     [esp+43Ch+var_3D4], ecx
0x1003b502  call    _memset
0x1003b507  movq    xmm0, qword ptr ds:aUnique; "UNIQUE"
0x1003b50f  xor     eax, eax
0x1003b511  mov     esi, [esi+10h]
0x1003b514  add     esp, 0Ch
0x1003b517  movq    qword ptr [esp+430h+String1], xmm0
0x1003b520  xor     edi, edi
0x1003b522  movups  xmm0, xmmword ptr ds:aPrimaryKey_1; "PRIMARY KEY"
0x1003b529  mov     [esp+430h+var_408], eax
0x1003b52d  mov     eax, dword ptr ds:aUnique+8; "UE"
0x1003b532  movups  xmmword ptr [esp+430h+var_2F0], xmm0
0x1003b53a  mov     dword ptr [esp+430h+var_318], eax
0x1003b541  movq    xmm0, qword ptr ds:aPrimaryKey_1+10h; "KEY"
0x1003b549  mov     ax, word ptr ds:aUnique+0Ch; ""
0x1003b54f  movq    [esp+430h+var_2E0], xmm0
0x1003b558  movq    xmm0, qword ptr ds:aCheck; "CHECK"
0x1003b560  movq    qword ptr [esp+430h+var_32C], xmm0
0x1003b569  movups  xmm0, xmmword ptr ds:aForeignKey; "FOREIGN KEY"
0x1003b570  mov     word ptr [esp+430h+var_318+4], ax
0x1003b578  mov     eax, dword ptr ds:aCheck+8; "K"
0x1003b57d  movups  [esp+430h+var_2D0], xmm0
0x1003b585  push    0FFDEh; Size
0x1003b58a  movq    xmm0, qword ptr ds:aForeignKey+10h; "KEY"
0x1003b592  mov     [esp+434h+var_424], 0
0x1003b59a  mov     [esp+434h+sesid], esi
0x1003b59e  mov     [esp+434h+var_418], 0
0x1003b5a6  mov     [esp+434h+var_420], 0
0x1003b5ae  mov     [esp+434h+var_3E8], 0
0x1003b5b6  mov     [esp+434h+var_3E0], 0
0x1003b5be  mov     [esp+434h+var_414], 0
0x1003b5c6  mov     [esp+434h+var_400], 1
0x1003b5ce  mov     [esp+434h+var_3D8], edi
0x1003b5d2  mov     [esp+434h+var_324], eax
0x1003b5d9  movq    [esp+434h+var_2C0], xmm0
0x1003b5e2  mov     [esp+434h+Block], edi
0x1003b5e6  call    ??2@YAPAXI@Z; operator new(uint)
0x1003b5eb  add     esp, 4
0x1003b5ee  mov     [esp+430h+var_3E4], eax
0x1003b5f2  test    eax, eax
0x1003b5f4  jnz     short loc_1003B604
0x1003b5f6  mov     edi, 8007000Eh
0x1003b5fb  mov     [esp+430h+var_428], edi
0x1003b5ff  jmp     loc_1003C87D
0x1003b604  push    0FFDCh; Size
0x1003b609  call    ??2@YAPAXI@Z; operator new(uint)
0x1003b60e  add     esp, 4
0x1003b611  mov     [esp+430h+Block], eax
0x1003b615  test    eax, eax
0x1003b617  jnz     short loc_1003B627
0x1003b619  mov     edi, 8007000Eh
0x1003b61e  mov     [esp+430h+var_428], edi
0x1003b622  jmp     loc_1003C87D
0x1003b627  mov     edx, [ebp+this]
0x1003b62a  mov     ecx, [esp+430h+var_410]
0x1003b62e  test    edx, edx
0x1003b630  jz      loc_1003B749
0x1003b636  test    ecx, ecx
0x1003b638  jz      loc_1003B70D
0x1003b63e  cmp     edx, 7
0x1003b641  ja      loc_1003B70D
0x1003b647  movzx   eax, word ptr [ecx]
0x1003b64a  test    ax, ax
0x1003b64d  jz      short loc_1003B666
0x1003b64f  cmp     eax, 1
0x1003b652  jz      short loc_1003B666
0x1003b654  cmp     eax, 8
0x1003b657  jnz     loc_1003B70D
0x1003b65d  cmp     [ecx+8], edi
0x1003b660  jnz     loc_1003B70D
0x1003b666  cmp     edx, 1
0x1003b669  jbe     short loc_1003B68B
0x1003b66b  movzx   eax, word ptr [ecx+10h]
0x1003b66f  test    ax, ax
0x1003b672  jz      short loc_1003B68B
0x1003b674  cmp     eax, 1
0x1003b677  jz      short loc_1003B68B
0x1003b679  cmp     eax, 8
0x1003b67c  jnz     loc_1003B70D
0x1003b682  cmp     [ecx+18h], edi
0x1003b685  jnz     loc_1003B70D
0x1003b68b  cmp     edx, 2
0x1003b68e  jbe     short loc_1003B6A3
0x1003b690  movzx   eax, word ptr [ecx+20h]
0x1003b694  test    ax, ax
0x1003b697  jz      short loc_1003B6A3
0x1003b699  cmp     eax, 1
0x1003b69c  jz      short loc_1003B6A3
0x1003b69e  cmp     eax, 8
0x1003b6a1  jnz     short loc_1003B70D
0x1003b6a3  cmp     edx, 3
0x1003b6a6  jbe     short loc_1003B6C0
0x1003b6a8  movzx   eax, word ptr [ecx+30h]
0x1003b6ac  test    ax, ax
0x1003b6af  jz      short loc_1003B6C0
0x1003b6b1  cmp     eax, 1
0x1003b6b4  jz      short loc_1003B6C0
0x1003b6b6  cmp     eax, 8
0x1003b6b9  jnz     short loc_1003B70D
0x1003b6bb  cmp     [ecx+38h], edi
0x1003b6be  jnz     short loc_1003B70D
0x1003b6c0  cmp     edx, 4
0x1003b6c3  jbe     short loc_1003B6DD
0x1003b6c5  movzx   eax, word ptr [ecx+40h]
0x1003b6c9  test    ax, ax
0x1003b6cc  jz      short loc_1003B6DD
0x1003b6ce  cmp     eax, 1
0x1003b6d1  jz      short loc_1003B6DD
0x1003b6d3  cmp     eax, 8
0x1003b6d6  jnz     short loc_1003B70D
0x1003b6d8  cmp     [ecx+48h], edi
0x1003b6db  jnz     short loc_1003B70D
0x1003b6dd  cmp     edx, 5
0x1003b6e0  jbe     short loc_1003B6F5
0x1003b6e2  movzx   eax, word ptr [ecx+50h]
0x1003b6e6  test    ax, ax
0x1003b6e9  jz      short loc_1003B6F5
0x1003b6eb  cmp     eax, 1
0x1003b6ee  jz      short loc_1003B6F5
0x1003b6f0  cmp     eax, 8
0x1003b6f3  jnz     short loc_1003B70D
0x1003b6f5  cmp     edx, 6
0x1003b6f8  jbe     short loc_1003B71B
0x1003b6fa  movzx   eax, word ptr [ecx+60h]
0x1003b6fe  test    ax, ax
0x1003b701  jz      short loc_1003B720
0x1003b703  cmp     eax, 1
0x1003b706  jz      short loc_1003B720
0x1003b708  cmp     eax, 8
0x1003b70b  jz      short loc_1003B720
0x1003b70d  mov     edi, 80070057h
0x1003b712  mov     [esp+430h+var_428], edi
0x1003b716  jmp     loc_1003C87D
0x1003b71b  cmp     edx, 3
0x1003b71e  jb      short loc_1003B749
0x1003b720  movzx   eax, word ptr [ecx+20h]
0x1003b724  test    ax, ax
0x1003b727  jz      short loc_1003B749
0x1003b729  cmp     eax, 1
0x1003b72c  jz      short loc_1003B749
0x1003b72e  mov     eax, [ecx+28h]
0x1003b731  mov     [esp+430h+var_3E8], 1
0x1003b739  mov     [esp+430h+var_3D8], eax
0x1003b73d  test    eax, eax
0x1003b73f  jnz     short loc_1003B749
0x1003b741  xor     esi, esi
0x1003b743  mov     [esp+430h+var_400], esi
0x1003b747  jmp     short loc_1003B74E
0x1003b749  mov     esi, 1
0x1003b74e  cmp     edx, 6
0x1003b751  jb      short loc_1003B777
0x1003b753  movzx   eax, word ptr [ecx+50h]
0x1003b757  test    ax, ax
0x1003b75a  jz      short loc_1003B777
0x1003b75c  cmp     eax, 1
0x1003b75f  jz      short loc_1003B777
0x1003b761  mov     edi, [ecx+58h]
0x1003b764  xor     eax, eax
0x1003b766  test    edi, edi
0x1003b768  mov     [esp+430h+var_3E0], 1
0x1003b770  cmovz   esi, eax
0x1003b773  mov     [esp+430h+var_400], esi
0x1003b777  mov     esi, 1
0x1003b77c  cmp     edx, 7
0x1003b77f  jb      short loc_1003B7B0
0x1003b781  movzx   eax, word ptr [ecx+60h]
0x1003b785  test    ax, ax
0x1003b788  jz      short loc_1003B7A6
0x1003b78a  cmp     eax, esi
0x1003b78c  jz      short loc_1003B7A6
0x1003b78e  cmp     dword ptr [ecx+68h], 0
0x1003b792  mov     [esp+430h+var_414], esi
0x1003b796  jnz     short loc_1003B7B0
0x1003b798  mov     [esp+430h+var_400], 0
0x1003b7a0  mov     [esp+430h+var_414], esi
0x1003b7a4  jmp     short loc_1003B7B5
0x1003b7a6  mov     [esp+430h+var_414], 0
0x1003b7ae  jmp     short loc_1003B7B5
0x1003b7b0  cmp     edx, 3
0x1003b7b3  jb      short loc_1003B7BB
0x1003b7b5  cmp     si, [ecx+20h]
0x1003b7b9  jz      short loc_1003B7D1
0x1003b7bb  cmp     edx, 6
0x1003b7be  jb      short loc_1003B7C6
0x1003b7c0  cmp     si, [ecx+50h]
0x1003b7c4  jz      short loc_1003B7D1
0x1003b7c6  cmp     edx, 7
0x1003b7c9  jb      short loc_1003B7D9
0x1003b7cb  cmp     si, [ecx+60h]
0x1003b7cf  jnz     short loc_1003B7D9
0x1003b7d1  mov     [esp+430h+var_400], 0
0x1003b7d9  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1003b7df  push    28h ; '('
0x1003b7e1  push    ecx
0x1003b7e2  mov     eax, [ecx]
0x1003b7e4  mov     esi, [eax+0Ch]
0x1003b7e7  mov     ecx, esi
0x1003b7e9  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1003b7ef  call    esi
0x1003b7f1  mov     [esp+430h+var_418], eax
0x1003b7f5  test    eax, eax
0x1003b7f7  jnz     short loc_1003B80B
0x1003b7f9  mov     edi, 8007000Eh
0x1003b7fe  mov     [esp+430h+var_428], edi
0x1003b802  mov     esi, [esp+430h+sesid]
0x1003b806  jmp     loc_1003C87D
0x1003b80b  mov     edx, [esp+430h+var_40C]
0x1003b80f  mov     ecx, 9
0x1003b814  push    2
0x1003b816  push    eax
0x1003b817  lea     eax, [esp+438h+var_420]
0x1003b81b  push    eax
0x1003b81c  call    SRSCreateTempTable
0x1003b821  mov     esi, [esp+430h+sesid]
0x1003b825  mov     ecx, eax
0x1003b827  mov     [esp+430h+var_428], ecx
0x1003b82b  test    ecx, ecx
0x1003b82d  js      loc_1003C875
0x1003b833  push    1
0x1003b835  push    30h ; '0'
0x1003b837  lea     eax, [esp+438h+var_398]
0x1003b83e  push    eax
0x1003b83f  push    edi
0x1003b840  mov     edi, [esp+440h+var_40C]
0x1003b844  push    offset aTables_0; "tables"
0x1003b849  push    0
0x1003b84b  push    dword ptr [edi+14h]
0x1003b84e  push    esi
0x1003b84f  call    ds:__imp__JetGetObjectInfo@32; JetGetObjectInfo(x,x,x,x,x,x,x,x)
0x1003b855  mov     [esp+430h+var_424], eax
0x1003b859  test    eax, eax
0x1003b85b  jz      short loc_1003B86B
0x1003b85d  mov     edi, 80004005h
0x1003b862  mov     [esp+430h+var_428], edi
0x1003b866  jmp     loc_1003C87D
0x1003b86b  push    0; grbit
0x1003b86d  push    80000000h; cRow
0x1003b872  push    [esp+438h+tableid]; tableid
0x1003b879  push    esi; sesid
0x1003b87a  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1003b880  mov     [esp+430h+var_424], eax
0x1003b884  cmp     eax, 0FFFFF9BDh
0x1003b889  jz      short loc_1003B89D
0x1003b88b  test    eax, eax
0x1003b88d  jz      short loc_1003B89D
0x1003b88f  mov     edi, 80004005h
0x1003b894  mov     [esp+430h+var_428], edi
0x1003b898  jmp     loc_1003C87D
0x1003b89d  cmp     [esp+430h+var_390], 0
0x1003b8a5  mov     [esp+430h+var_3F8], 0
0x1003b8ad  jbe     loc_1003C4A9
0x1003b8b3  cmp     [esp+430h+var_400], 0
0x1003b8b8  jz      loc_1003C4A9
0x1003b8be  mov     eax, dword ptr ds:aValidationrule+18h; "le"
0x1003b8c3  movups  xmm0, xmmword ptr ds:aValidationrule; "ValidationRule"
0x1003b8ca  mov     [esp+430h+var_2F8], eax
0x1003b8d1  movzx   eax, word ptr ds:aValidationrule+1Ch; ""
0x1003b8d8  mov     [esp+430h+var_2F4], ax
0x1003b8e0  movzx   eax, word ptr ds:aCheckconstrain+20h; ""
0x1003b8e7  mov     [esp+430h+var_200], ax
0x1003b8ef  xor     eax, eax
0x1003b8f1  push    eax; pretinfo
0x1003b8f2  push    eax; grbit
0x1003b8f3  mov     [esp+438h+String2], ax
0x1003b8fb  mov     [esp+438h+var_1E8], ax
0x1003b903  lea     eax, [esp+438h+pcbActual]
0x1003b907  push    eax; pcbActual
0x1003b908  movups  xmmword ptr [esp+43Ch+var_318+8], xmm0
0x1003b910  lea     eax, [esp+43Ch+pvData]
0x1003b914  movq    xmm0, qword ptr ds:aValidationrule+10h; "onRule"
0x1003b91c  push    4; cbData
0x1003b91e  movq    [esp+440h+var_300], xmm0
0x1003b927  movups  xmm0, xmmword ptr ds:aCheckconstrain; "CheckConstraints"
0x1003b92e  push    eax; pvData
0x1003b92f  push    [esp+444h+columnid]; columnid
0x1003b936  movups  [esp+448h+var_228+8], xmm0
0x1003b93e  movups  xmm0, xmmword ptr ds:aCheckconstrain+10h; "straints"
0x1003b945  push    [esp+448h+tableid]; tableid
0x1003b94c  movups  [esp+44Ch+var_218+8], xmm0
0x1003b954  push    esi; sesid
  ... truncated ...
```
