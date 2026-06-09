# CRowset::FInit(ulong,CDBSession *,CCommand *,ushort *,ushort *,ulong,CRowsetProperties const &,eJetCursorType,void *,ulong *,ColumnData *,int,ulong,tagDBPROPSET * const,_GUID const &)

- ea: `0x10028340`
- end: `0x100294a3`
- name: `?FInit@CRowset@@QAGJKPAVCDBSession@@PAVCCommand@@PAG2KABVCRowsetProperties@@W4eJetCursorType@@PAXPAKPAVColumnData@@HKQAUtagDBPROPSET@@ABU_GUID@@@Z`
- size: `4451`
- prototype: `int __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `26`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1000e140`
- `0x1000fcf0`
- `0x1001b4a0`
- `0x10025180`
- `0x1002e3e0`
- `0x10035f80`
- `0x10036ad0`
- `0x100372f0`
- `0x10037c60`
- `0x10038310`
- `0x10038f10`
- `0x100395b0`
- `0x10039cc0`
- `0x1003a1a0`
- `0x1003a8b0`
- `0x1003b4c0`
- `0x1003c980`
- `0x1003d390`
- `0x1003e190`
- `0x1003e7d0`
- `0x1003e990`
- `0x1003eb30`
- `0x1003eda0`
- `0x1003fcd0`
- `0x1003fea0`
- `0x10044ee0`

## callees

- `0x1000bca0`
- `0x1000bcf0`
- `0x1000be60`
- `0x1000bea0`
- `0x1000e8e0`
- `0x10013100`
- `0x10013c50`
- `0x1001a140`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1001f2d0`
- `0x1001fb90`
- `0x1001fbe0`
- `0x1001fcb0`
- `0x100201c0`
- `0x100204c0`
- `0x100205d0`
- `0x10020c40`
- `0x10020e30`
- `0x10021070`
- `0x10028340`
- `0x1002c8f0`
- `0x1002d600`
- `0x1002d9b0`
- `0x10049580`
- `0x1004cc50`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004dc8d`

## import_xrefs

- `msvcrt!malloc` at `0x100284a4`
- `msvcrt!malloc` at `0x10028fb5`
- `msvcrt!malloc` at `0x100284a4`
- `msvcrt!malloc` at `0x10028fb5`
- `msvcrt!free` at `0x10028fa4`
- `msvcrt!free` at `0x10028fa4`
- `KERNEL32!InitializeCriticalSection` at `0x10028eda`
- `KERNEL32!InitializeCriticalSection` at `0x10028f41`
- `KERNEL32!InitializeCriticalSection` at `0x10028eda`
- `KERNEL32!InitializeCriticalSection` at `0x10028f41`
- `KERNEL32!LeaveCriticalSection` at `0x100283fd`
- `KERNEL32!LeaveCriticalSection` at `0x1002905e`
- `KERNEL32!LeaveCriticalSection` at `0x10029258`
- `KERNEL32!LeaveCriticalSection` at `0x100283fd`
- `KERNEL32!LeaveCriticalSection` at `0x1002905e`
- `KERNEL32!LeaveCriticalSection` at `0x10029258`
- `KERNEL32!EnterCriticalSection` at `0x100283ee`
- `KERNEL32!EnterCriticalSection` at `0x1002903f`
- `KERNEL32!EnterCriticalSection` at `0x10029245`
- `KERNEL32!EnterCriticalSection` at `0x100283ee`
- `KERNEL32!EnterCriticalSection` at `0x1002903f`
- `KERNEL32!EnterCriticalSection` at `0x10029245`
- `msjet40!__imp__JetCloseTable@8` at `0x100286f7`
- `msjet40!__imp__JetCloseTable@8` at `0x100292cd`
- `msjet40!__imp__JetCloseTable@8` at `0x100292eb`
- `msjet40!__imp__JetCloseTable@8` at `0x100286f7`
- `msjet40!__imp__JetCloseTable@8` at `0x100292cd`
- `msjet40!__imp__JetCloseTable@8` at `0x100292eb`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100291f1`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100291f1`
- `msjet40!__imp__JetGetTableInfo@20` at `0x1002871c`
- `msjet40!__imp__JetGetTableInfo@20` at `0x10028754`
- `msjet40!__imp__JetGetTableInfo@20` at `0x1002871c`
- `msjet40!__imp__JetGetTableInfo@20` at `0x10028754`
- `msjet40!__imp__JetOpenTable@28` at `0x10028574`
- `msjet40!__imp__JetOpenTable@28` at `0x100285a3`
- `msjet40!__imp__JetOpenTable@28` at `0x10028574`
- `msjet40!__imp__JetOpenTable@28` at `0x100285a3`
- `msjet40!__imp__JetSetCurrentIndex@12` at `0x100286a4`
- `msjet40!__imp__JetSetCurrentIndex@12` at `0x100286a4`

## pseudocode

```c
int __thiscall CRowset::FInit(
        int this,
        int a2,
        _DWORD *a3,
        int a4,
        _WORD *a5,
        int a6,
        struct CSettableProperties *a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        unsigned int a13,
        unsigned int a14,
        struct _GUID *a15)
{
  int v16; // ecx
  void (__thiscall *v17)(_DWORD, int *); // ecx
  int v18; // eax
  int v19; // edi
  int v20; // esi
  CTransactionState *v21; // ecx
  volatile signed __int32 *v22; // eax
  _DWORD *v23; // eax
  _DWORD *v24; // esi
  void *v25; // eax
  int v26; // edi
  CSettableProperties *v27; // ecx
  JET_TABLEID *v28; // esi
  signed int v29; // eax
  signed int v30; // eax
  JET_SESID v31; // edi
  unsigned int v32; // eax
  char v33; // cl
  unsigned int v34; // edi
  _DWORD *v35; // ecx
  void (__thiscall ***v36)(unsigned int, int); // eax
  JoltProperties *v37; // ecx
  CBitArray *v38; // ecx
  int v39; // eax
  ColumnData *v40; // eax
  ColumnData *v41; // ecx
  int v42; // eax
  int v43; // eax
  struct JoltProperty *RowbyProp; // esi
  int v45; // eax
  struct _GUID *v46; // ecx
  GUID *v47; // edx
  unsigned int v48; // esi
  bool v49; // cf
  int v50; // eax
  struct JoltProperty *v51; // esi
  int v52; // eax
  struct _GUID *v53; // ecx
  GUID *v54; // edx
  unsigned int v55; // esi
  int v56; // eax
  JoltProperties *v57; // esi
  int v58; // eax
  unsigned int v59; // edi
  int v60; // eax
  _DWORD *v61; // eax
  _DWORD *v62; // edx
  int v63; // ecx
  struct IUnknown **v64; // esi
  int v65; // eax
  CImpIColumnsRowset *v66; // eax
  CImpIColumnsRowset *v67; // eax
  _DWORD *v68; // edx
  struct IUnknown *v69; // ecx
  struct IUnknown *v70; // eax
  _DWORD *v71; // eax
  _DWORD *v72; // esi
  JoltProperties *v73; // edi
  _DWORD *v74; // eax
  int v75; // ecx
  _DWORD *v76; // eax
  _DWORD *v77; // eax
  unsigned int i; // esi
  JoltProperties *v79; // edi
  unsigned int v80; // eax
  char *v81; // eax
  _DWORD *v82; // edi
  int v83; // esi
  unsigned int v84; // eax
  _DWORD *v85; // esi
  char *v86; // eax
  char *v87; // edi
  int v88; // esi
  int v89; // esi
  _DWORD *v90; // ecx
  int v91; // eax
  _DWORD *v92; // esi
  _DWORD *v93; // eax
  CBitArray *v94; // ecx
  CBitArray *v95; // edi
  bool v96; // cc
  int v97; // edi
  struct _RTL_CRITICAL_SECTION *v98; // esi
  JoltProperties *v99; // esi
  _DWORD *v100; // eax
  CImpIAccessor *v101; // eax
  CImpIAccessor *v102; // eax
  int v103; // eax
  bool v104; // zf
  int v106; // eax
  int v107; // eax
  struct _RTL_CRITICAL_SECTION *v108; // esi
  int v109; // eax
  int v110; // esi
  CTransactionState *v111; // ecx
  JET_SESID v112; // esi
  CImpIAccessor *v113; // esi
  _DWORD *v114; // eax
  _DWORD *v115; // eax
  _DWORD *v116; // eax
  _DWORD *v117; // eax
  _DWORD *v118; // eax
  _DWORD *v119; // eax
  _DWORD *v120; // eax
  _DWORD *v121; // eax
  int v122; // eax
  CBitArray *v123; // eax
  unsigned int v124; // [esp-10h] [ebp-68h]
  struct _GUID v125; // [esp-10h] [ebp-68h]
  struct _GUID v126; // [esp-10h] [ebp-68h]
  struct _GUID v127; // [esp-10h] [ebp-68h]
  int *v128; // [esp-4h] [ebp-5Ch]
  size_t v129; // [esp-4h] [ebp-5Ch]
  int v130; // [esp-4h] [ebp-5Ch]
  void *v131; // [esp-4h] [ebp-5Ch]
  void *v132; // [esp-4h] [ebp-5Ch]
  void *v133; // [esp-4h] [ebp-5Ch]
  void *v134; // [esp-4h] [ebp-5Ch]
  void *v135; // [esp-4h] [ebp-5Ch]
  void *v136; // [esp-4h] [ebp-5Ch]
  void *v137; // [esp-4h] [ebp-5Ch]
  void *v138; // [esp-4h] [ebp-5Ch]
  struct CSettableProperties *v139; // [esp+0h] [ebp-58h]
  struct CCommand *v140; // [esp+4h] [ebp-54h]
  unsigned int v141; // [esp+8h] [ebp-50h]
  struct tagDBPROPSET *v142; // [esp+Ch] [ebp-4Ch]
  int v143; // [esp+10h] [ebp-48h]
  unsigned int v144; // [esp+10h] [ebp-48h]
  unsigned int TableInfo; // [esp+14h] [ebp-44h] BYREF
  unsigned int v146; // [esp+18h] [ebp-40h] BYREF
  int v147; // [esp+1Ch] [ebp-3Ch]
  CBitArray *v148; // [esp+20h] [ebp-38h]
  JET_SESID sesid; // [esp+24h] [ebp-34h]
  CBitArray *v150; // [esp+28h] [ebp-30h]
  int v151; // [esp+2Ch] [ebp-2Ch]
  _DWORD *v152; // [esp+30h] [ebp-28h]
  int v153; // [esp+34h] [ebp-24h] BYREF
  unsigned int v154; // [esp+38h] [ebp-20h] BYREF
  unsigned int v155; // [esp+3Ch] [ebp-1Ch] BYREF
  unsigned int v156; // [esp+40h] [ebp-18h] BYREF
  int v157; // [esp+44h] [ebp-14h] BYREF
  int v158; // [esp+48h] [ebp-10h]
  int v159; // [esp+4Ch] [ebp-Ch]
  unsigned int v160[2]; // [esp+50h] [ebp-8h]

  TableInfo = 0;
  v146 = 0;
  v153 = 0;
  *(_DWORD *)(this + 56) = a2;
  v128 = *(int **)(a2 + 28);
  v158 = 0;
  v16 = *v128;
  v159 = 0;
  v157 = 0;
  v151 = 0;
  v17 = *(void (__thiscall **)(_DWORD, int *))(v16 + 4);
  v154 = 0;
  v160[0] = 127;
  v160[1] = 134;
  v17(v17, v128);
  if ( a3 )
  {
    *(_DWORD *)(this + 60) = a3;
    v18 = (*(int (__thiscall **)(_DWORD *))(*a3 + 24))(a3);
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v18 + 4))(*(_DWORD *)(*(_DWORD *)v18 + 4), v18);
    v19 = *(_DWORD *)(this + 60);
    EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 248));
    _InterlockedIncrement((volatile signed __int32 *)(v19 + 80));
    if ( v19 != -248 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 248));
  }
  v20 = *(_DWORD *)(this + 64);
  if ( v20 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v20);
    if ( !*(_DWORD *)v20 )
    {
      v21 = *(CTransactionState **)(v20 + 8);
      if ( v21 )
        CTransactionState::Release(v21);
      operator delete((void *)v20);
    }
  }
  v22 = *(volatile signed __int32 **)(*(_DWORD *)(this + 56) + 88);
  *(_DWORD *)(this + 64) = v22;
  if ( v22 )
    _InterlockedIncrement(v22);
  sesid = *(_DWORD *)(*(_DWORD *)(this + 56) + 16);
  v23 = operator new(0x28u);
  v24 = v23;
  v156 = (unsigned int)v23;
  if ( !v23 )
  {
    *(_DWORD *)(this + 104) = 0;
    v148 = (CBitArray *)(this + 104);
    goto LABEL_191;
  }
  v23[5] = 1;
  *((_BYTE *)v23 + 32) = -1;
  v23[4] = v23 + 8;
  v23[6] = 0;
  v23[9] = 1;
  v23[7] = 1;
  v23[1] = 0;
  v23[2] = 0;
  *(_DWORD *)(this + 104) = v23;
  v148 = (CBitArray *)(this + 104);
  v150 = (CBitArray *)(this + 104);
  *v23 = 12;
  v25 = _malloc(0x300u);
  v24[2] = v25;
  if ( !v25 )
    goto LABEL_191;
  v129 = v24[5];
  v24[1] = 64;
  memset((void *)v24[4], -1, v129);
  v147 = a8;
  *(_DWORD *)(this + 116) = a8;
  v26 = CSettableProperties::FInit((CSettableProperties *)(this + 152));
  v143 = v26;
  if ( v26 < 0 )
    goto LABEL_193;
  v27 = (CSettableProperties *)(this + 152);
  if ( a7 != (struct CSettableProperties *)(this + 152) )
  {
    v26 = CSettableProperties::CopyFrom(v27, a7);
    v27 = (CSettableProperties *)(this + 152);
    v143 = v26;
    if ( v26 < 0 )
      goto LABEL_193;
    *(_DWORD *)(this + 168) = *((_DWORD *)a7 + 4);
  }
  if ( a4 )
  {
    v26 = CRowsetProperties::ValidateStateForJetOpenTable(v27, &v146, a15, (enum eJetCursorType *)&a8, 1);
    v143 = v26;
    if ( v26 < 0 )
      goto LABEL_193;
    v28 = (JET_TABLEID *)(this + 108);
    v29 = JetOpenTable(sesid, *(_DWORD *)(*(_DWORD *)(this + 56) + 20), a4, 0, 0, v146, this + 108);
    TableInfo = v29;
    if ( v29 == -1003 )
    {
      v146 |= 0x40u;
      v29 = JetOpenTable(sesid, *(_DWORD *)(*(_DWORD *)(this + 56) + 20), a4, 0, 0, v146, this + 108);
      TableInfo = v29;
    }
    if ( v29 <= -1907 )
    {
      if ( v29 == -1907 )
      {
        v26 = -2147217911;
        *v28 = -1;
        goto LABEL_192;
      }
      if ( v29 > -3020 )
      {
        if ( v29 == -3010 )
        {
          *v28 = -1;
          v26 = -2147217904;
          goto LABEL_192;
        }
        if ( v29 != -2001 )
          goto LABEL_40;
        goto LABEL_30;
      }
      if ( v29 != -3020 )
      {
        if ( v29 != -3504 && v29 != -3100 )
        {
LABEL_40:
          if ( (int)TableInfo <= 0 )
          {
            v26 = -2147467259;
            *v28 = -1;
            goto LABEL_192;
          }
          goto LABEL_42;
        }
LABEL_30:
        *v28 = -1;
        v26 = -2147217865;
        goto LABEL_192;
      }
LABEL_38:
      v26 = -2147217865;
      *v28 = -1;
      goto LABEL_192;
    }
    if ( v29 > 0 )
    {
      if ( v29 != 3032 )
        goto LABEL_40;
    }
    else if ( v29 )
    {
      if ( v29 != -1305 )
      {
        if ( v29 != -1302 )
          goto LABEL_40;
        v26 = -2147467259;
        *v28 = -1;
LABEL_192:
        v143 = v26;
        goto LABEL_193;
      }
      goto LABEL_38;
    }
LABEL_42:
    *(_DWORD *)(this + 120) = v146;
    v158 = 1;
    v147 = a8;
    goto LABEL_45;
  }
  v26 = CRowsetProperties::SetInterfacesFromREFIID(v27, a15);
  v143 = v26;
  if ( v26 < 0 )
    goto LABEL_193;
  v28 = (JET_TABLEID *)(this + 108);
  *(_DWORD *)(this + 108) = a6;
LABEL_45:
  if ( !a5 )
    goto LABEL_56;
  v30 = JetSetCurrentIndex(sesid, *v28, a5);
  TableInfo = v30;
  if ( v30 == -1404 || v30 == -1312 )
  {
    v26 = -2147217867;
    goto LABEL_52;
  }
  if ( v30 )
  {
    v26 = -2147467259;
LABEL_52:
    v143 = v26;
    goto LABEL_53;
  }
  v26 = v143;
  *(_DWORD *)(this + 208) = *a5 != 0;
LABEL_53:
  if ( v30 < 0 )
  {
    JetCloseTable(sesid, *v28);
    *v28 = -1;
    goto LABEL_193;
  }
  *(_DWORD *)(this + 96) |= 0x20u;
LABEL_56:
  v31 = sesid;
  TableInfo = JetGetTableInfo(sesid, *v28, &v153, 4, 10);
  if ( (TableInfo & 0x80000000) != 0 )
  {
    v26 = -2147467259;
    goto LABEL_192;
  }
  v104 = a12 == 0;
  *(_DWORD *)(this + 212) = v153;
  if ( !v104 )
  {
    v34 = v147;
LABEL_69:
    v33 = v146;
    goto LABEL_71;
  }
  v32 = JetGetTableInfo(v31, *v28, &v146, 4, 6);
  TableInfo = v32;
  if ( v32 == -1312 )
  {
    v33 = 0;
    TableInfo = 0;
    v34 = 0;
    v146 = 0;
    v147 = 0;
    goto LABEL_71;
  }
  if ( v32 == -1003 )
  {
    v34 = v147;
    TableInfo = 0;
    if ( v147 != 4 )
    {
      v33 = 48;
      v157 = 1;
      v34 = 3;
      v146 = 48;
      v147 = 3;
      goto LABEL_71;
    }
    goto LABEL_69;
  }
  if ( v32 )
  {
    v26 = -2147467259;
    goto LABEL_192;
  }
  v33 = v146;
  if ( v146 )
  {
    v34 = v147;
  }
  else
  {
    v34 = 0;
    v147 = 0;
  }
LABEL_71:
  switch ( *(_DWORD *)(this + 212) )
  {
    case 0xF:
    case 0x10:
    case 0x11:
    case 0x37:
    case 0x38:
    case 0x39:
      if ( (v33 & 0x30) == 0 )
        goto LABEL_74;
      v34 = 5;
      v147 = 5;
      break;
    default:
LABEL_74:
      if ( v34 <= 1 )
        JoltProperties::SetbProperty(*(JoltProperties **)(this + 160), 0x86u, 0);
      break;
  }
  v35 = a3;
  if ( a3 )
  {
    v36 = (void (__thiscall ***)(unsigned int, int))a3[68];
    v156 = (unsigned int)v36;
    if ( v36 )
    {
      (**v36)(v156, 1);
      v35 = a3;
      v28 = (JET_TABLEID *)(this + 108);
      a3[68] = 0;
    }
  }
  v26 = CRowset::SetPropertiestoCursorType(v34, this + 152, v35, a13, a14);
  v143 = v26;
  if ( v26 < 0 )
    goto LABEL_193;
  v37 = *(JoltProperties **)(this + 164);
  v156 = *(_DWORD *)(this + 120);
  JoltProperties::SetIntValue(v37, 0xFEu, &v156);
  CSettableProperties::SetPropertiesReadOnly((CSettableProperties *)(this + 152));
  if ( (v146 & 0x30) != 0 )
  {
    v39 = v147;
  }
  else
  {
    if ( a12 != 1 )
      goto LABEL_83;
    v39 = v147;
    if ( !v147 )
      goto LABEL_83;
  }
  if ( v39 == 5 )
  {
LABEL_83:
    *(_DWORD *)(this + 132) = 0;
    v152 = (_DWORD *)(this + 132);
    goto LABEL_84;
  }
  v38 = v150;
  v152 = (_DWORD *)(this + 132);
  *(_DWORD *)(this + 132) = 1;
  v148 = v38;
  v43 = v39 - 2;
  if ( !v43 || (unsigned int)(v43 - 1) <= 1 )
  {
    TableInfo = CRowset::GetEditCursor((CRowset *)this);
    v148 = v150;
    if ( (TableInfo & 0x80000000) != 0 )
    {
      v26 = -2147467259;
      goto LABEL_192;
    }
    v159 = 1;
    v152 = (_DWORD *)(this + 132);
  }
LABEL_84:
  if ( a11 )
  {
    *(_DWORD *)(this + 148) = a11;
  }
  else
  {
    v40 = (ColumnData *)operator new(0x10u);
    v41 = v40;
    v156 = (unsigned int)v40;
    if ( !v40 )
    {
      *(_DWORD *)(this + 148) = 0;
      goto LABEL_191;
    }
    v130 = (int)v40;
    *(_DWORD *)v40 = &ColumnData::`vftable';
    *((_DWORD *)v40 + 1) = 0;
    *((_DWORD *)v40 + 2) = 0;
    *((_DWORD *)v40 + 3) = 0;
    v42 = *(_DWORD *)(this + 56);
    v124 = *v28;
    *(_DWORD *)(this + 148) = v41;
    v26 = ColumnData::FInit(v41, sesid, *(_DWORD *)(v42 + 20), v124, (int *)&TableInfo, 0, v130);
    v143 = v26;
    if ( v26 < 0 )
      goto LABEL_193;
  }
  if ( *v152 == 1 || v147 == 5 )
  {
    v143 = CRowset::Move(v38, (int)&TableInfo, 0, (int *)v38, (int)v139, (int)v140);
    if ( v143 == 265926 || TableInfo == -1603 )
    {
      v143 = 0;
      TableInfo = 0;
    }
  }
  if ( *(_DWORD *)(this + 212) == 4 )
    goto LABEL_123;
  RowbyProp = JoltProperties::GetRowbyProp(*(JoltProperties **)(this + 160), 0x9Fu);
  if ( *((_WORD *)RowbyProp + 12) == 0xFFFF )
  {
    *(_DWORD *)&v125.Data4[4] = (a3 != 0) + 7;
    *(_DWORD *)v125.Data4 = a14;
    *(_QWORD *)&v125.Data1 = __PAIR64__(a13, (unsigned int)a3);
    v45 = HandleInvalidPropertyValue(*(_OWORD *)&DBPROPSET_ROWSET, v125, v139, v140, v141, v142, v143);
    v26 = v45;
    v143 = v45;
    if ( v45 < 0 )
    {
      if ( v45 == -2147467259 )
      {
        v46 = a15;
        v47 = &IID_IRowsetIndex;
        v48 = 12;
        while ( v47->Data1 == v46->Data1 )
        {
          v47 = (GUID *)((char *)v47 + 4);
          v46 = (struct _GUID *)((char *)v46 + 4);
          v49 = v48 < 4;
          v48 -= 4;
          if ( v49 )
          {
            v26 = -2147467262;
            goto LABEL_192;
          }
        }
      }
      goto LABEL_193;
    }
    v50 = *((_DWORD *)RowbyProp + 10);
    if ( (v50 & 2) != 0 )
    {
LABEL_111:
      v26 = -2147217887;
      goto LABEL_192;
    }
    v151 = 1;
    *((_WORD *)RowbyProp + 12) = 0;
    *((_DWORD *)RowbyProp + 8) &= ~0x400u;
    *((_DWORD *)RowbyProp + 10) = v50 | 2;
  }
  v51 = JoltProperties::GetRowbyProp(*(JoltProperties **)(this + 160), 0x117u);
  if ( *((_WORD *)v51 + 12) != 0xFFFF )
  {
LABEL_123:
    v57 = *(JoltProperties **)(this + 160);
    v58 = JoltProperties::IsbPropertySet(v57, 0x88u);
    v59 = v58 ^ (v58 ^ *(_DWORD *)(this + 172)) & 0xFFFFFFFE;
    *(_DWORD *)(this + 172) = v59;
    v60 = JoltProperties::IsbPropertySet(v57, 0x89u);
    *(_DWORD *)(this + 172) = (2 * v60) ^ ((2 * v60) ^ v59) & 0xFFFFFFFD;
    v61 = operator new(0x14u);
    v62 = v61;
    v156 = (unsigned int)v61;
    if ( !v61 )
    {
      *(_DWORD *)(this + 40) = 0;
      goto LABEL_191;
    }
    v63 = *(_DWORD *)(this + 8);
    v64 = (struct IUnknown **)(this + 8);
    *v61 = &CImpIColumnsInfo::`vftable';
    v65 = this;
    v62[1] = 0;
    if ( v63 )
      v65 = v63;
    v62[2] = this;
    v62[4] = 1;
    v62[3] = v65;
    v150 = (CBitArray *)(this + 8);
    *(_DWORD *)(this + 40) = v62;
    if ( !v62 )
      goto LABEL_191;
    if ( JoltProperties::IsbPropertySet(*(JoltProperties **)(this + 160), 0x7Bu) )
    {
      v66 = (CImpIColumnsRowset *)operator new(0x14u);
      v156 = (unsigned int)v66;
      if ( !v66 )
      {
        *(_DWORD *)(this + 44) = 0;
        goto LABEL_191;
      }
      v67 = CImpIColumnsRowset::CImpIColumnsRowset(v66, (struct CBaseObj *)this, 1, *v64);
      *(_DWORD *)(this + 44) = v67;
      if ( !v67 )
      {
LABEL_191:
        v26 = -2147024882;
        goto LABEL_192;
      }
    }
    v68 = operator new(0x14u);
    v156 = (unsigned int)v68;
    if ( !v68 )
    {
      *(_DWORD *)(this + 48) = 0;
      goto LABEL_191;
    }
    v69 = *v64;
    v70 = (struct IUnknown *)this;
    v104 = *v64 == 0;
    *v68 = &CImpIConvertType::`vftable';
    v68[1] = 0;
    if ( !v104 )
      v70 = v69;
    v68[2] = this;
    v68[3] = 1;
    v68[4] = v70;
    *(_DWORD *)(this + 48) = v68;
    v71 = operator new(0xCu);
    v72 = v71;
    v156 = (unsigned int)v71;
    if ( !v71 )
    {
      *(_DWORD *)(this + 16) = 0;
      goto LABEL_191;
    }
    *v71 = &CImpIRowsetLocate::`vftable';
    v71[1] = 0;
    v71[2] = this;
    v73 = *(JoltProperties **)(this + 160);
    *(_DWORD *)(this + 16) = v71;
    if ( JoltProperties::IsbPropertySet(v73, 0xEu) )
    {
      *(_DWORD *)(this + 96) |= 8u;
      if ( JoltProperties::IsbPropertySet(v73, 0x82u) || JoltProperties::IsbPropertySet(v73, 0x85u) )
        *(_DWORD *)(this + 20) = v72;
    }
    v74 = operator new(0xCu);
    v156 = (unsigned int)v74;
    if ( !v74 )
    {
      *(_DWORD *)(this + 32) = 0;
      goto LABEL_191;
    }
    *v74 = &CImpIRowsetInfo::`vftable';
    v74[1] = 0;
    v74[2] = this;
    v75 = *(_DWORD *)(this + 56);
    *(_DWORD *)(this + 32) = v74;
    CDataSource::ValidateStateForJetOpenDatabase(*(CDataSource **)(v75 + 84), &v154);
    if ( JoltProperties::IsbPropertySet(*(JoltProperties **)(this + 160), 0x7Fu) )
    {
      v76 = operator new(0xCu);
      v156 = (unsigned int)v76;
      if ( !v76 )
        goto LABEL_148;
      *v76 = &CImpIRowsetUpdate::`vftable';
      v76[1] = 0;
      v76[2] = this;
      *(_DWORD *)(this + 36) = v76;
    }
    if ( !JoltProperties::IsbPropertySet(*(JoltProperties **)(this + 160), 0x86u) )
    {
      *(_DWORD *)(this + 96) |= 0x10u;
      goto LABEL_150;
    }
    if ( *(_DWORD *)(this + 36) )
    {
LABEL_150:
      if ( (v154 & 1) != 0 )
      {
        for ( i = 0; i < 2; ++i )
        {
          if ( JoltProperties::BinarySearch(*(JoltProperties **)(this + 160), v160[i], &v156) >= 0
            && *(_WORD *)(*(_DWORD *)(*(_DWORD *)(this + 160) + 16) + 48 * v156 + 24) == 0xFFFF )
          {
            *(_QWORD *)v127.Data4 = a14 | 0x800000000LL;
            *(_QWORD *)&v127.Data1 = __PAIR64__(a13, (unsigned int)a3);
            v26 = HandleInvalidPropertyValue(*(_OWORD *)&DBPROPSET_ROWSET, v127, v139, v140, v141, v142, v143);
            v143 = v26;
            if ( v26 < 0 )
              goto LABEL_193;
            v79 = *(JoltProperties **)(this + 160);
            if ( JoltProperties::BinarySearch(v79, v160[i], &v155) < 0 )
              v80 = 0;
            else
              v80 = *((_DWORD *)v79 + 4) + 48 * v155;
            if ( (*(_BYTE *)(v80 + 40) & 2) != 0 )
              goto LABEL_111;
            v151 = 1;
            v143 = 265946;
          }
        }
      }
      if ( JoltProperties::IsbPropertySet(*(JoltProperties **)(this + 160), 0x7Cu) )
      {
        v81 = (char *)operator new(0x2Cu);
        v82 = v81;
        v144 = (unsigned int)v81;
        if ( !v81 )
        {
          *(_DWORD *)(this + 52) = 0;
          goto LABEL_191;
        }
        v83 = *(_DWORD *)(this + 8);
        *(_DWORD *)v81 = &CRowsetConnectionPointContainer::`vftable';
        InitializeCriticalSection((LPCRITICAL_SECTION)(v81 + 4));
        v82[9] = 0;
        v84 = this + 52;
        v82[8] = 0;
        v82[7] = v83;
        *(_DWORD *)(this + 52) = v82;
        v147 = 0;
        v85 = v82;
        v152 = v82;
        do
        {
          v154 = v84;
          v86 = (char *)operator new(0x4Cu);
          v87 = v86;
          v156 = (unsigned int)v86;
          if ( !v86 )
          {
            v85[v147 + 9] = 0;
            goto LABEL_191;
          }
          v88 = v147;
          *(_DWORD *)v86 = &CRowsetConnectionPoint::`vftable';
          v89 = (int)*(&off_10003080 + v88);
          InitializeCriticalSection((LPCRITICAL_SECTION)(v86 + 12));
          v90 = v152;
          v91 = v147;
          *((_DWORD *)v87 + 12) = 0;
          *((_DWORD *)v87 + 15) = 0;
          *((_DWORD *)v87 + 9) = v89;
          *((_DWORD *)v87 + 1) = v90;
          *((_DWORD *)v87 + 10) = 0;
          *((_DWORD *)v87 + 16) = 0;
          *((_DWORD *)v87 + 11) = 0;
          *((_DWORD *)v87 + 2) = 0;
          *((_DWORD *)v87 + 18) = 0;
          *((_DWORD *)v87 + 17) = 0;
          v90[v91 + 9] = v87;
          v92 = v87 + 48;
          if ( *((_DWORD *)v87 + 15) )
            _free(*((void **)v87 + 15));
          *v92 = 96;
          v93 = _malloc(0xCu);
          *((_DWORD *)v87 + 15) = v93;
          if ( !v93 )
          {
            *v92 = 0;
            goto LABEL_191;
          }
          v94 = v148;
          *(_QWORD *)v93 = 0;
          v93[2] = 0;
          *((_DWORD *)v87 + 13) = 134480385;
          *((_DWORD *)v87 + 14) = -2143281136;
          v95 = v150;
          v156 = (unsigned int)v94;
          v155 = (unsigned int)v150;
          CBitArray::SetSlots(v94, (unsigned int)v139, (unsigned int)v140);
          v85 = (_DWORD *)v144;
          v96 = ++v147 < 1;
          v84 = v154;
          v150 = v95;
        }
        while ( v96 );
        v143 = 0;
        v97 = *(_DWORD *)v154;
        v98 = (struct _RTL_CRITICAL_SECTION *)(*(_DWORD *)v154 + 4);
        EnterCriticalSection(v98);
        _InterlockedIncrement((volatile signed __int32 *)(v97 + 32));
        v150 = (CBitArray *)v155;
        v148 = (CBitArray *)v156;
        if ( !v98 )
          goto LABEL_174;
        LeaveCriticalSection(v98);
        v26 = 0;
        v150 = (CBitArray *)v155;
        v148 = (CBitArray *)v156;
      }
      else
      {
LABEL_174:
        v26 = v143;
      }
      v99 = *(JoltProperties **)(this + 160);
      if ( !JoltProperties::IsbPropertySet(v99, 0x9Fu) && !JoltProperties::IsbPropertySet(v99, 0x117u) || v157 != 1 )
      {
LABEL_180:
        v101 = (CImpIAccessor *)operator new(0x30u);
        v157 = (int)v101;
        if ( v101 )
        {
          v102 = CImpIAccessor::CImpIAccessor(v101, (struct CBaseObj *)this, *(struct IUnknown **)v150);
          *(_DWORD *)(this + 12) = v102;
          if ( v102 && CImpIAccessor::FInit(v139, (int)v140) >= 0 )
          {
            v103 = JoltProperties::IsbPropertySet(*(JoltProperties **)(this + 164), 0xECu);
            *(_DWORD *)(this + 96) |= 0x203u;
            *(_DWORD *)(this + 68) = v103;
            goto LABEL_193;
          }
        }
        else
        {
          *(_DWORD *)(this + 12) = 0;
        }
        goto LABEL_191;
      }
      v100 = operator new(0xCu);
      v157 = (int)v100;
      if ( v100 )
      {
        *v100 = &CImpIRowsetIndex::`vftable';
        v100[1] = 0;
        v100[2] = this;
        *(_DWORD *)(this + 28) = v100;
        goto LABEL_180;
      }
      *(_DWORD *)(this + 28) = 0;
      goto LABEL_191;
    }
    v77 = operator new(0xCu);
    v156 = (unsigned int)v77;
    if ( v77 )
    {
      *v77 = &CImpIRowsetUpdate::`vftable';
      v77[1] = 0;
      v77[2] = this;
      *(_DWORD *)(this + 36) = v77;
      goto LABEL_150;
    }
LABEL_148:
    *(_DWORD *)(this + 36) = 0;
    goto LABEL_191;
  }
  *(_DWORD *)&v126.Data4[4] = (a3 != 0) + 7;
  *(_DWORD *)v126.Data4 = a14;
  *(_QWORD *)&v126.Data1 = __PAIR64__(a13, (unsigned int)a3);
  v52 = HandleInvalidPropertyValue(*(_OWORD *)&DBPROPSET_ROWSET, v126, v139, v140, v141, v142, v143);
  v26 = v52;
  v143 = v52;
  if ( v52 >= 0 )
  {
    v56 = *((_DWORD *)v51 + 10);
    if ( (v56 & 2) != 0 )
    {
      v26 = -2147217887;
      goto LABEL_192;
    }
    v151 = 1;
    *((_WORD *)v51 + 12) = 0;
    *((_DWORD *)v51 + 8) &= ~0x400u;
    *((_DWORD *)v51 + 10) = v56 | 2;
    goto LABEL_123;
  }
  if ( v52 == -2147467259 )
  {
    v53 = a15;
    v54 = &IID_IRowsetCurrentIndex;
    v55 = 12;
    while ( v54->Data1 == v53->Data1 )
    {
      v54 = (GUID *)((char *)v54 + 4);
      v53 = (struct _GUID *)((char *)v53 + 4);
      v49 = v55 < 4;
      v55 -= 4;
      if ( v49 )
      {
        v26 = -2147467262;
        goto LABEL_192;
      }
    }
  }
LABEL_193:
  if ( TableInfo )
  {
    CExtError::SendJetErrortoOLEAuto(TableInfo, (int)&IID_IRowset, (int)v139, (const struct _GUID *)v140);
    v104 = v26 == 0;
  }
  else
  {
    v104 = v26 == 0;
    if ( v26 < 0 )
    {
      if ( v26 != -2147024882
        && !JetGetDatabaseInfo(
              *(_DWORD *)(*(_DWORD *)(this + 56) + 16),
              *(_DWORD *)(*(_DWORD *)(this + 56) + 20),
              &v157,
              4,
              3) )
      {
        CExtError::SendHRtoOLEAuto((int)&IID_IRowset, 0, (const struct _GUID *)v139, (int)v140);
      }
      goto LABEL_203;
    }
  }
  if ( !v104 )
  {
    if ( v26 >= 0 )
      return v26;
LABEL_203:
    v106 = *(_DWORD *)(this + 56);
    if ( v106 )
    {
      (*(void (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)(v106 + 28) + 8))(
        *(_DWORD *)(**(_DWORD **)(v106 + 28) + 8),
        *(_DWORD *)(v106 + 28));
      *(_DWORD *)(this + 56) = 0;
    }
    v107 = *(_DWORD *)(this + 60);
    v157 = v107;
    if ( v107 )
    {
      v108 = (struct _RTL_CRITICAL_SECTION *)(v107 + 248);
      EnterCriticalSection((LPCRITICAL_SECTION)(v107 + 248));
      _InterlockedDecrement((volatile signed __int32 *)(v157 + 80));
      if ( v108 )
        LeaveCriticalSection(v108);
      v109 = (*(int (__thiscall **)(_DWORD))(**(_DWORD **)(this + 60) + 24))(*(_DWORD *)(this + 60));
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v109 + 8))(*(_DWORD *)(*(_DWORD *)v109 + 8), v109);
      v26 = v143;
      *(_DWORD *)(this + 60) = 0;
    }
    v110 = *(_DWORD *)(this + 64);
    if ( v110 )
    {
      _InterlockedDecrement((volatile signed __int32 *)v110);
      if ( !*(_DWORD *)v110 )
      {
        v111 = *(CTransactionState **)(v110 + 8);
        if ( v111 )
          CTransactionState::Release(v111);
        operator delete((void *)v110);
      }
      *(_DWORD *)(this + 64) = 0;
    }
    v112 = sesid;
    if ( v158 == 1 && *(_DWORD *)(this + 108) != -1 )
      JetCloseTable(sesid, *(_DWORD *)(this + 108));
    v104 = v159 == 1;
    *(_DWORD *)(this + 108) = -1;
    if ( v104 && *(_DWORD *)(this + 112) != -1 )
      JetCloseTable(v112, *(_DWORD *)(this + 112));
    v113 = *(CImpIAccessor **)(this + 12);
    *(_DWORD *)(this + 112) = -1;
    if ( v113 )
    {
      CImpIAccessor::~CImpIAccessor(v113);
      operator delete(v113);
    }
    v114 = *(_DWORD **)(this + 24);
    if ( v114 )
    {
      v131 = *(void **)(this + 24);
      *v114 = &CImpIRowsetIdentity::`vftable';
      operator delete(v131);
    }
    v115 = *(_DWORD **)(this + 28);
    if ( v115 )
    {
      v132 = *(void **)(this + 28);
      *v115 = &CImpIRowsetIndex::`vftable';
      operator delete(v132);
    }
    v116 = *(_DWORD **)(this + 32);
    if ( v116 )
    {
      v133 = *(void **)(this + 32);
      *v116 = &CImpIRowsetInfo::`vftable';
      operator delete(v133);
    }
    v117 = *(_DWORD **)(this + 16);
    if ( v117 )
    {
      v134 = *(void **)(this + 16);
      *v117 = &CImpIRowsetLocate::`vftable';
      operator delete(v134);
    }
    v118 = *(_DWORD **)(this + 36);
    if ( v118 )
    {
      v135 = *(void **)(this + 36);
      *v118 = &CImpIRowsetUpdate::`vftable';
      operator delete(v135);
    }
    v119 = *(_DWORD **)(this + 40);
    if ( v119 )
    {
      v136 = *(void **)(this + 40);
      *v119 = &CImpIColumnsInfo::`vftable';
      operator delete(v136);
    }
    v120 = *(_DWORD **)(this + 44);
    if ( v120 )
    {
      v137 = *(void **)(this + 44);
      *v120 = &CImpIColumnsRowset::`vftable';
      operator delete(v137);
    }
    v121 = *(_DWORD **)(this + 48);
    if ( v121 )
    {
      v138 = *(void **)(this + 48);
      *v121 = &CImpIConvertType::`vftable';
      operator delete(v138);
    }
    if ( *(_DWORD *)v148 )
      CExtBuffer::`scalar deleting destructor'(*(CExtBuffer **)v148, *(_DWORD *)v148);
    if ( *(_DWORD *)(this + 140) && Sys )
      (*(void (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)Sys + 20))(
        *(_DWORD *)(*(_DWORD *)Sys + 20),
        Sys,
        *(_DWORD *)(this + 140));
    v122 = *(_DWORD *)(this + 148);
    v159 = v122;
    if ( v122 )
      (*(void (__thiscall **)(int, int))(*(_DWORD *)v122 + 4))(v159, 1);
    v123 = v148;
    *(_DWORD *)(this + 176) = 0;
    *(_DWORD *)(this + 180) = 0;
    *(_DWORD *)(this + 12) = 0;
    *(_DWORD *)(this + 24) = 0;
    *(_DWORD *)(this + 28) = 0;
    *(_DWORD *)(this + 32) = 0;
    *(_DWORD *)(this + 20) = 0;
    *(_DWORD *)(this + 16) = 0;
    *(_DWORD *)(this + 36) = 0;
    *(_DWORD *)(this + 40) = 0;
    *(_DWORD *)(this + 44) = 0;
    *(_DWORD *)(this + 48) = 0;
    *(_DWORD *)v123 = 0;
    *(_DWORD *)(this + 140) = 0;
    *(_DWORD *)(this + 144) = 0;
    *(_DWORD *)(this + 148) = 0;
    return v26;
  }
  if ( v151 == 1 )
    return 265946;
  return v26;
}

```

## disassembly

```asm
0x10028340  mov     edi, edi
0x10028342  push    ebp
0x10028343  mov     ebp, esp
0x10028345  and     esp, 0FFFFFFF8h
0x10028348  sub     esp, 4Ch
0x1002834b  mov     eax, [ebp+arg_0]
0x1002834e  push    ebx; unsigned int
0x1002834f  mov     ebx, ecx
0x10028351  mov     [esp+50h+var_44], 0
0x10028359  mov     [esp+50h+var_40], 0
0x10028361  mov     [esp+50h+var_24], 0
0x10028369  push    esi; int
0x1002836a  mov     [ebx+38h], eax
0x1002836d  mov     eax, [eax+1Ch]
0x10028370  push    edi; struct _GUID *
0x10028371  push    eax
0x10028372  mov     [esp+5Ch+var_10], 0
0x1002837a  mov     ecx, [eax]
0x1002837c  mov     [esp+5Ch+var_C], 0
0x10028384  mov     [esp+5Ch+var_14], 0
0x1002838c  mov     [esp+5Ch+var_2C], 0
0x10028394  mov     esi, [ecx+4]
0x10028397  mov     ecx, esi
0x10028399  mov     [esp+5Ch+var_20], 0
0x100283a1  mov     [esp+5Ch+var_8], 7Fh
0x100283a9  mov     [esp+5Ch+var_4], 86h
0x100283b1  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100283b7  call    esi
0x100283b9  mov     edi, [ebp+arg_4.Data1]
0x100283bc  test    edi, edi
0x100283be  jz      short loc_10028403
0x100283c0  mov     [ebx+3Ch], edi
0x100283c3  mov     eax, [edi]
0x100283c5  mov     esi, [eax+18h]
0x100283c8  mov     ecx, esi
0x100283ca  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100283d0  mov     ecx, edi
0x100283d2  call    esi
0x100283d4  push    eax
0x100283d5  mov     ecx, [eax]
0x100283d7  mov     esi, [ecx+4]
0x100283da  mov     ecx, esi
0x100283dc  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100283e2  call    esi
0x100283e4  mov     edi, [ebx+3Ch]
0x100283e7  lea     esi, [edi+0F8h]
0x100283ed  push    esi; lpCriticalSection
0x100283ee  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100283f4  lock inc dword ptr [edi+50h]
0x100283f8  test    esi, esi
0x100283fa  jz      short loc_10028403
0x100283fc  push    esi; lpCriticalSection
0x100283fd  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10028403  mov     esi, [ebx+40h]
0x10028406  test    esi, esi
0x10028408  jz      short loc_10028427
0x1002840a  lock dec dword ptr [esi]
0x1002840d  cmp     dword ptr [esi], 0
0x10028410  ja      short loc_10028427
0x10028412  mov     ecx, [esi+8]; this
0x10028415  test    ecx, ecx
0x10028417  jz      short loc_1002841E
0x10028419  call    ?Release@CTransactionState@@QAEKXZ; CTransactionState::Release(void)
0x1002841e  push    esi; Block
0x1002841f  call    ??3@YAXPAX@Z; operator delete(void *)
0x10028424  add     esp, 4
0x10028427  mov     eax, [ebx+38h]
0x1002842a  mov     eax, [eax+58h]
0x1002842d  mov     [ebx+40h], eax
0x10028430  test    eax, eax
0x10028432  jz      short loc_10028437
0x10028434  lock inc dword ptr [eax]
0x10028437  mov     eax, [ebx+38h]
0x1002843a  push    28h ; '('; Size
0x1002843c  mov     eax, [eax+10h]
0x1002843f  mov     [esp+5Ch+sesid], eax
0x10028443  call    ??2@YAPAXI@Z; operator new(uint)
0x10028448  mov     esi, eax
0x1002844a  add     esp, 4
0x1002844d  mov     [esp+58h+var_18], esi
0x10028451  test    esi, esi
0x10028453  jz      loc_10029185
0x10028459  lea     ecx, [esi+20h]
0x1002845c  mov     dword ptr [esi+14h], 1
0x10028463  mov     byte ptr [ecx], 0FFh
0x10028466  lea     eax, [ebx+68h]
0x10028469  mov     [esi+10h], ecx
0x1002846c  mov     dword ptr [esi+18h], 0
0x10028473  mov     dword ptr [esi+24h], 1
0x1002847a  mov     dword ptr [esi+1Ch], 1
0x10028481  mov     dword ptr [esi+4], 0
0x10028488  mov     dword ptr [esi+8], 0
0x1002848f  mov     [eax], esi
0x10028491  push    300h; Size
0x10028496  mov     [esp+5Ch+var_38], eax
0x1002849a  mov     [esp+5Ch+var_30], eax
0x1002849e  mov     dword ptr [esi], 0Ch
0x100284a4  call    ds:__imp__malloc
0x100284aa  add     esp, 4
0x100284ad  mov     [esi+8], eax
0x100284b0  test    eax, eax
0x100284b2  jz      loc_10029192
0x100284b8  push    dword ptr [esi+14h]; Size
0x100284bb  mov     dword ptr [esi+4], 40h ; '@'
0x100284c2  push    0FFFFFFFFh; Val
0x100284c4  push    dword ptr [esi+10h]; void *
0x100284c7  call    _memset
0x100284cc  mov     eax, [ebp+arg_18]
0x100284cf  lea     ecx, [ebx+98h]; this
0x100284d5  add     esp, 0Ch
0x100284d8  mov     [esp+58h+var_3C], eax
0x100284dc  mov     [ebx+74h], eax
0x100284df  call    ?FInit@CSettableProperties@@QAEJXZ; CSettableProperties::FInit(void)
0x100284e4  mov     edi, eax
0x100284e6  mov     [esp+58h+var_48], edi
0x100284ea  test    edi, edi
0x100284ec  js      loc_1002919B
0x100284f2  mov     esi, [ebp+arg_14]
0x100284f5  lea     ecx, [ebx+98h]; this
0x100284fb  xor     edi, edi
0x100284fd  mov     [esp+58h+var_48], edi
0x10028501  cmp     esi, ecx
0x10028503  jz      short loc_10028527
0x10028505  push    esi; struct CSettableProperties *
0x10028506  call    ?CopyFrom@CSettableProperties@@QAEJABV1@@Z; CSettableProperties::CopyFrom(CSettableProperties const &)
0x1002850b  mov     edi, eax
0x1002850d  lea     ecx, [ebx+98h]
0x10028513  mov     [esp+58h+var_48], edi
0x10028517  test    edi, edi
0x10028519  js      loc_1002919B
0x1002851f  mov     eax, [esi+10h]
0x10028522  mov     [ecx+10h], eax
0x10028525  jmp     short loc_1002852F
0x10028527  test    edi, edi
0x10028529  js      loc_1002919B
0x1002852f  cmp     dword ptr [ebp+arg_4.Data2], 0
0x10028533  jz      loc_10028677
0x10028539  push    1; int
0x1002853b  lea     eax, [ebp+arg_18]
0x1002853e  push    eax; enum eJetCursorType *
0x1002853f  mov     eax, [ebp+arg_34]
0x10028542  push    eax; struct _GUID *
0x10028543  lea     eax, [esp+64h+var_40]
0x10028547  push    eax; unsigned int *
0x10028548  call    ?ValidateStateForJetOpenTable@CRowsetProperties@@QAEJAAKABU_GUID@@AAW4eJetCursorType@@H@Z; CRowsetProperties::ValidateStateForJetOpenTable(ulong &,_GUID const &,eJetCursorType &,int)
0x1002854d  mov     edi, eax
0x1002854f  mov     [esp+58h+var_48], edi
0x10028553  test    edi, edi
0x10028555  js      loc_1002919B
0x1002855b  mov     eax, [ebx+38h]
0x1002855e  lea     esi, [ebx+6Ch]
0x10028561  push    esi
0x10028562  push    [esp+5Ch+var_40]
0x10028566  push    0
0x10028568  push    0
0x1002856a  push    dword ptr [ebp+arg_4.Data2]
0x1002856d  push    dword ptr [eax+14h]
0x10028570  push    [esp+70h+sesid]
0x10028574  call    ds:__imp__JetOpenTable@28; JetOpenTable(x,x,x,x,x,x,x)
0x1002857a  mov     [esp+58h+var_44], eax
0x1002857e  cmp     eax, 0FFFFFC15h
0x10028583  jnz     short loc_100285AD
0x10028585  mov     eax, [esp+58h+var_40]
0x10028589  push    esi
0x1002858a  or      eax, 40h
0x1002858d  push    eax
0x1002858e  push    0
0x10028590  mov     [esp+64h+var_40], eax
0x10028594  mov     eax, [ebx+38h]
0x10028597  push    0
0x10028599  push    dword ptr [ebp+arg_4.Data2]
0x1002859c  push    dword ptr [eax+14h]
0x1002859f  push    [esp+70h+sesid]
0x100285a3  call    ds:__imp__JetOpenTable@28; JetOpenTable(x,x,x,x,x,x,x)
0x100285a9  mov     [esp+58h+var_44], eax
0x100285ad  cmp     eax, 0FFFFF88Dh
0x100285b2  jg      short loc_1002860D
0x100285b4  jz      short loc_100285FD
0x100285b6  cmp     eax, 0FFFFF434h
0x100285bb  jg      short loc_100285CF
0x100285bd  jz      short loc_10028631
0x100285bf  cmp     eax, 0FFFFF250h
0x100285c4  jz      short loc_100285DD
0x100285c6  cmp     eax, 0FFFFF3E4h
0x100285cb  jz      short loc_100285DD
0x100285cd  jmp     short loc_10028648
0x100285cf  cmp     eax, 0FFFFF43Eh
0x100285d4  jz      short loc_100285ED
0x100285d6  cmp     eax, 0FFFFF82Fh
0x100285db  jnz     short loc_10028648
0x100285dd  mov     dword ptr [esi], 0FFFFFFFFh
0x100285e3  mov     edi, 80040E37h
0x100285e8  jmp     loc_10029197
0x100285ed  mov     dword ptr [esi], 0FFFFFFFFh
0x100285f3  mov     edi, 80040E10h
0x100285f8  jmp     loc_10029197
0x100285fd  mov     edi, 80040E09h
0x10028602  mov     dword ptr [esi], 0FFFFFFFFh
0x10028608  jmp     loc_10029197
0x1002860d  test    eax, eax
0x1002860f  jg      short loc_10028641
0x10028611  jz      short loc_1002865F
0x10028613  cmp     eax, 0FFFFFAE7h
0x10028618  jz      short loc_10028631
0x1002861a  cmp     eax, 0FFFFFAEAh
0x1002861f  jnz     short loc_10028648
0x10028621  mov     edi, 80004005h
0x10028626  mov     dword ptr [esi], 0FFFFFFFFh
0x1002862c  jmp     loc_10029197
0x10028631  mov     edi, 80040E37h
0x10028636  mov     dword ptr [esi], 0FFFFFFFFh
0x1002863c  jmp     loc_10029197
0x10028641  cmp     eax, 0BD8h
0x10028646  jz      short loc_1002865F
0x10028648  cmp     [esp+58h+var_44], 0
0x1002864d  jg      short loc_1002865F
0x1002864f  mov     edi, 80004005h
0x10028654  mov     dword ptr [esi], 0FFFFFFFFh
0x1002865a  jmp     loc_10029197
0x1002865f  mov     eax, [esp+58h+var_40]
0x10028663  mov     [ebx+78h], eax
0x10028666  mov     eax, [ebp+arg_18]
0x10028669  mov     [esp+58h+var_10], 1
0x10028671  mov     [esp+58h+var_3C], eax
0x10028675  jmp     short loc_10028696
0x10028677  mov     eax, [ebp+arg_34]
0x1002867a  push    eax; struct _GUID *
0x1002867b  call    ?SetInterfacesFromREFIID@CRowsetProperties@@QAEJABU_GUID@@@Z; CRowsetProperties::SetInterfacesFromREFIID(_GUID const &)
0x10028680  mov     edi, eax
0x10028682  mov     [esp+58h+var_48], edi
0x10028686  test    edi, edi
0x10028688  js      loc_1002919B
0x1002868e  mov     eax, dword ptr [ebp+arg_4.Data4+4]
0x10028691  lea     esi, [ebx+6Ch]
0x10028694  mov     [esi], eax
0x10028696  mov     eax, dword ptr [ebp+arg_4.Data4]
0x10028699  test    eax, eax
0x1002869b  jz      short loc_1002870C
0x1002869d  push    eax
0x1002869e  push    dword ptr [esi]
0x100286a0  push    [esp+60h+sesid]
0x100286a4  call    ds:__imp__JetSetCurrentIndex@12; JetSetCurrentIndex(x,x,x)
0x100286aa  mov     ecx, eax
0x100286ac  mov     [esp+58h+var_44], ecx
0x100286b0  cmp     ecx, 0FFFFFA84h
0x100286b6  jz      short loc_100286E4
0x100286b8  cmp     ecx, 0FFFFFAE0h
0x100286be  jz      short loc_100286E4
0x100286c0  test    ecx, ecx
0x100286c2  jz      short loc_100286CB
0x100286c4  mov     edi, 80004005h
0x100286c9  jmp     short loc_100286E9
0x100286cb  mov     edx, dword ptr [ebp+arg_4.Data4]
0x100286ce  xor     eax, eax
0x100286d0  xor     edi, edi
0x100286d2  cmp     di, [edx]
0x100286d5  mov     edi, [esp+58h+var_48]
0x100286d9  setnz   al
0x100286dc  mov     [ebx+0D0h], eax
0x100286e2  jmp     short loc_100286ED
0x100286e4  mov     edi, 80040E35h
0x100286e9  mov     [esp+58h+var_48], edi
0x100286ed  test    ecx, ecx
0x100286ef  jns     short loc_10028708
0x100286f1  push    dword ptr [esi]; tableid
0x100286f3  push    [esp+5Ch+sesid]; sesid
0x100286f7  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x100286fd  mov     dword ptr [esi], 0FFFFFFFFh
0x10028703  jmp     loc_1002919B
0x10028708  or      dword ptr [ebx+60h], 20h
0x1002870c  mov     edi, [esp+58h+sesid]
0x10028710  lea     eax, [esp+58h+var_24]
0x10028714  push    0Ah
0x10028716  push    4
0x10028718  push    eax
0x10028719  push    dword ptr [esi]
0x1002871b  push    edi
0x1002871c  call    ds:__imp__JetGetTableInfo@20; JetGetTableInfo(x,x,x,x,x)
0x10028722  mov     [esp+58h+var_44], eax
0x10028726  test    eax, eax
0x10028728  jns     short loc_10028734
0x1002872a  mov     edi, 80004005h
0x1002872f  jmp     loc_10029197
0x10028734  cmp     [ebp+arg_28], 0
0x10028738  mov     eax, [esp+58h+var_24]
0x1002873c  mov     [ebx+0D4h], eax
0x10028742  jnz     loc_100287CD
0x10028748  push    6
0x1002874a  push    4
0x1002874c  lea     eax, [esp+60h+var_40]
0x10028750  push    eax
0x10028751  push    dword ptr [esi]
0x10028753  push    edi
0x10028754  call    ds:__imp__JetGetTableInfo@20; JetGetTableInfo(x,x,x,x,x)
0x1002875a  mov     [esp+58h+var_44], eax
0x1002875e  cmp     eax, 0FFFFFAE0h
0x10028763  jz      short loc_100287B7
0x10028765  cmp     eax, 0FFFFFC15h
0x1002876a  jz      short loc_1002878A
0x1002876c  test    eax, eax
  ... truncated ...
```
