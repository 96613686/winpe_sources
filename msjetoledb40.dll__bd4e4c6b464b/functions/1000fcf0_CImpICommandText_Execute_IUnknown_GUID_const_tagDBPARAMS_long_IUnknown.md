# CImpICommandText::Execute(IUnknown *,_GUID const &,tagDBPARAMS *,long *,IUnknown * *)

- ea: `0x1000fcf0`
- end: `0x10010658`
- name: `?Execute@CImpICommandText@@UAGJPAUIUnknown@@ABU_GUID@@PAUtagDBPARAMS@@PAJPAPAU2@@Z`
- size: `2408`
- prototype: `int(CImpICommandText *__hidden this, struct IUnknown *, const struct _GUID *, struct tagDBPARAMS *, int *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000ba90`
- `0x1000fcf0`
- `0x100147f0`
- `0x10016c40`
- `0x10016d50`
- `0x10016e10`
- `0x10016f20`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1001f2d0`
- `0x10021070`
- `0x10027cf0`
- `0x10028340`
- `0x100496d0`
- `0x1004a120`
- `0x1004ce5d`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10010627`
- `KERNEL32!LeaveCriticalSection` at `0x10010632`
- `KERNEL32!LeaveCriticalSection` at `0x10010627`
- `KERNEL32!LeaveCriticalSection` at `0x10010632`
- `KERNEL32!EnterCriticalSection` at `0x1000fd8a`
- `KERNEL32!EnterCriticalSection` at `0x1000fda3`
- `KERNEL32!EnterCriticalSection` at `0x1000fd8a`
- `KERNEL32!EnterCriticalSection` at `0x1000fda3`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000fd74`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000fd74`
- `msjet40!__imp__JetCloseTable@8` at `0x100105bc`
- `msjet40!__imp__JetCloseTable@8` at `0x1001061c`
- `msjet40!__imp__JetCloseTable@8` at `0x100105bc`
- `msjet40!__imp__JetCloseTable@8` at `0x1001061c`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001054d`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001054d`
- `msjet40!__imp__JetGetLastErrorInfo@40` at `0x1001034b`
- `msjet40!__imp__JetGetLastErrorInfo@40` at `0x1001034b`
- `msjet40!__imp__JetOpenTable@28` at `0x100100f4`
- `msjet40!__imp__JetOpenTable@28` at `0x100100f4`
- `msjet40!__imp__JetExecuteTempQuery@28` at `0x10010115`
- `msjet40!__imp__JetExecuteTempQuery@28` at `0x10010115`

## pseudocode

```c
int __stdcall CImpICommandText::Execute(
        CImpICommandText *this,
        struct IUnknown *a2,
        struct _GUID *a3,
        struct tagDBPARAMS *a4,
        int *a5,
        struct IUnknown **a6)
{
  int v6; // ebx
  int v7; // eax
  int v8; // eax
  JET_SESID v9; // ecx
  int v10; // eax
  struct _RTL_CRITICAL_SECTION *v11; // esi
  struct _RTL_CRITICAL_SECTION *v12; // edi
  int v13; // eax
  CImpICommandText *v14; // ecx
  DB_UPARAMS cParamSets; // eax
  int v16; // eax
  int v17; // ebx
  int v18; // eax
  int v19; // ecx
  int v20; // eax
  struct _GUID *v21; // edx
  GUID *v22; // ecx
  bool v23; // cf
  struct _GUID *v24; // edx
  GUID *v25; // ecx
  int v26; // ecx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  CImpICommandText *v30; // ecx
  int v31; // edx
  int v32; // ecx
  int v33; // eax
  CImpICommandText *v34; // ecx
  _DWORD *v35; // ebx
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  unsigned int v40; // eax
  int v41; // eax
  int v42; // eax
  CDBSession *v43; // ecx
  int v44; // eax
  int v45; // eax
  struct _GUID *v46; // edx
  GUID *v47; // ecx
  int v48; // eax
  int v49; // eax
  CDBSession *v50; // eax
  CImpICommandText *v51; // edx
  CRowset *v52; // ecx
  int v53; // eax
  int v54; // eax
  int v55; // edx
  CImpICommandText *v56; // eax
  int v57; // eax
  JET_SESID *v58; // ecx
  unsigned int v59; // eax
  int v61; // [esp-24h] [ebp-C4h]
  unsigned int v62; // [esp-20h] [ebp-C0h]
  unsigned int v63; // [esp-8h] [ebp-A8h]
  struct _GUID *v64; // [esp-4h] [ebp-A4h]
  CCommand *v65; // [esp+0h] [ebp-A0h]
  const struct _GUID *v66; // [esp+0h] [ebp-A0h]
  const struct _GUID *v67; // [esp+4h] [ebp-9Ch]
  unsigned int v68; // [esp+18h] [ebp-88h] BYREF
  unsigned int v69; // [esp+1Ch] [ebp-84h] BYREF
  unsigned int v70; // [esp+20h] [ebp-80h] BYREF
  int v71; // [esp+24h] [ebp-7Ch]
  unsigned int v72; // [esp+28h] [ebp-78h] BYREF
  struct IUnknown *v73; // [esp+2Ch] [ebp-74h]
  int v74; // [esp+30h] [ebp-70h]
  JoltProperties *v75; // [esp+34h] [ebp-6Ch]
  struct tagDBPARAMS *v76; // [esp+38h] [ebp-68h]
  unsigned int v77; // [esp+3Ch] [ebp-64h] BYREF
  CDBSession *v78; // [esp+40h] [ebp-60h] BYREF
  JET_SESID sesid; // [esp+44h] [ebp-5Ch]
  int v80; // [esp+48h] [ebp-58h]
  unsigned int v81; // [esp+4Ch] [ebp-54h]
  JoltProperties *v82; // [esp+50h] [ebp-50h]
  int v83; // [esp+54h] [ebp-4Ch]
  struct IUnknown **v84; // [esp+58h] [ebp-48h]
  struct _GUID *v85; // [esp+5Ch] [ebp-44h]
  DB_UPARAMS v86; // [esp+60h] [ebp-40h]
  unsigned int v87; // [esp+64h] [ebp-3Ch]
  unsigned int v88; // [esp+68h] [ebp-38h]
  JET_TABLEID tableid; // [esp+6Ch] [ebp-34h] BYREF
  CRowset *v90; // [esp+70h] [ebp-30h]
  CImpICommandText *v91; // [esp+74h] [ebp-2Ch]
  int v92; // [esp+78h] [ebp-28h]
  _BYTE v93[4]; // [esp+7Ch] [ebp-24h] BYREF
  int v94; // [esp+80h] [ebp-20h]
  int v95; // [esp+8Ch] [ebp-14h]
  int v96; // [esp+9Ch] [ebp-4h]

  v6 = 0;
  v73 = a2;
  v85 = a3;
  v81 = (unsigned int)a5;
  v84 = a6;
  v7 = *((_DWORD *)this + 2);
  tableid = -1;
  v8 = *(_DWORD *)(v7 + 52);
  v91 = this;
  v76 = a4;
  v88 = 0;
  v9 = *(_DWORD *)(v8 + 16);
  v10 = *(_DWORD *)(v8 + 20);
  v90 = 0;
  v80 = 1;
  sesid = v9;
  v74 = v10;
  v71 = 0;
  v83 = 0;
  SetErrorInfo(0, 0);
  v11 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 248);
  EnterCriticalSection(v11);
  v96 = 0;
  v12 = (struct _RTL_CRITICAL_SECTION *)(*(_DWORD *)(*((_DWORD *)this + 2) + 52) + 104);
  EnterCriticalSection(v12);
  LOBYTE(v96) = 1;
  v13 = CCommand::CheckForZombieCommandAndFix(v65);
  v92 = v13;
  if ( v13 < 0 )
  {
    v17 = v13;
    goto LABEL_153;
  }
  v14 = v91;
  v92 = *((_DWORD *)v91 + 2);
  v71 = (*(_DWORD *)(v92 + 60) >> 4) & 1;
  if ( v81 )
  {
    *(_DWORD *)v81 = 0;
    v92 = *((_DWORD *)v14 + 2);
  }
  if ( v84 )
  {
    *v84 = 0;
    v92 = *((_DWORD *)v14 + 2);
  }
  if ( v76 )
  {
    cParamSets = v76->cParamSets;
    if ( cParamSets && !v76->pData )
      goto LABEL_11;
    if ( cParamSets > 1 )
    {
      if ( v84 )
      {
LABEL_11:
        v16 = *((_DWORD *)v14 + 2);
        v17 = -2147024809;
        v92 = -2147024809;
        v18 = *(_DWORD *)(v16 + 52);
        v19 = *(_DWORD *)(v18 + 20);
        v20 = *(_DWORD *)(v18 + 16);
        goto LABEL_154;
      }
      goto LABEL_13;
    }
  }
  if ( !v84 )
  {
LABEL_13:
    v21 = v85;
    v22 = &GUID_NULL;
    v87 = 12;
    while ( v22->Data1 == v21->Data1 )
    {
      v22 = (GUID *)((char *)v22 + 4);
      v21 = (struct _GUID *)((char *)v21 + 4);
      v23 = v87 < 4;
      v87 -= 4;
      if ( v23 )
        goto LABEL_16;
    }
    v17 = -2147024809;
LABEL_26:
    v92 = v17;
    v28 = *(_DWORD *)(*((_DWORD *)v91 + 2) + 52);
    v19 = *(_DWORD *)(v28 + 20);
    v20 = *(_DWORD *)(v28 + 16);
    goto LABEL_154;
  }
LABEL_16:
  if ( v73 )
  {
    v24 = v85;
    v25 = &IID_IUnknown;
    v87 = 12;
    while ( v25->Data1 == v24->Data1 )
    {
      v25 = (GUID *)((char *)v25 + 4);
      v24 = (struct _GUID *)((char *)v24 + 4);
      v23 = v87 < 4;
      v87 -= 4;
      if ( v23 )
        goto LABEL_20;
    }
    v17 = -2147217886;
    goto LABEL_26;
  }
LABEL_20:
  if ( !v76 || (v86 = v76->cParamSets) == 0 )
    v86 = 1;
  v26 = v92;
  v27 = *(_DWORD *)(v92 + 60);
  if ( (v27 & 0x20) == 0 )
  {
    v17 = -2147217908;
    goto LABEL_26;
  }
  if ( (v27 & 0x10) == 0 )
  {
    *(_DWORD *)(v92 + 60) = v27 | 0x100;
    v29 = (*(int (__thiscall **)(_DWORD, _DWORD, _DWORD))(**(_DWORD **)(*((_DWORD *)v91 + 2) + 24) + 12))(
            *(_DWORD *)(**(_DWORD **)(*((_DWORD *)v91 + 2) + 24) + 12),
            *(_DWORD *)(*((_DWORD *)v91 + 2) + 24),
            0);
    v30 = v91;
    v17 = v29;
    v92 = v29;
    *(_DWORD *)(*((_DWORD *)v91 + 2) + 60) &= ~0x100u;
    if ( v29 < 0 )
      goto LABEL_160;
    v26 = *((_DWORD *)v30 + 2);
    v6 = 0;
  }
  v92 = CRowsetProperties::ValidateStateForJetOpenTable(
          (CRowsetProperties *)(*(_DWORD *)(v26 + 20) + 12),
          &v72,
          v85,
          (enum eJetCursorType *)&v77,
          0);
  if ( v92 < 0 )
  {
    v17 = v92;
    goto LABEL_153;
  }
  v87 = 0;
  if ( !v86 )
  {
LABEL_91:
    v46 = v85;
    v47 = &GUID_NULL;
    v81 = 12;
    while ( v47->Data1 == v46->Data1 )
    {
      v47 = (GUID *)((char *)v47 + 4);
      v46 = (struct _GUID *)((char *)v46 + 4);
      v23 = v81 < 4;
      v81 -= 4;
      if ( v23 )
      {
        v48 = 0;
        goto LABEL_133;
      }
    }
    if ( tableid == -1 )
      v48 = 0;
    else
      v48 = v80;
LABEL_133:
    if ( v84 && v48 )
    {
      v50 = (CDBSession *)operator new(0xF0u);
      v78 = v50;
      if ( v50 )
      {
        v90 = CRowset::CRowset(v50, v73);
        if ( v90 )
        {
          v64 = v85;
          v51 = v91;
          v62 = v77;
          v61 = *(_DWORD *)(*((_DWORD *)v91 + 2) + 20) + 12;
          v52 = v90;
          *((_DWORD *)v90 + 30) = v72;
          v53 = CRowset::FInit(
                  v52,
                  0,
                  *(_DWORD *)(*((_DWORD *)v51 + 2) + 52),
                  *((_DWORD *)v51 + 2),
                  0,
                  0,
                  tableid,
                  v61,
                  v62,
                  0,
                  0,
                  0,
                  0,
                  0,
                  0,
                  v64);
          v6 = v88;
          v92 = v53;
          if ( v53 >= 0 )
          {
            if ( v53 == 265946 )
              v83 = 1;
            else
              tableid = -1;
            v49 = (**(int (__thiscall ***)(_DWORD, CRowset *, struct _GUID *, struct IUnknown **))v90)(
                    **(_DWORD **)v90,
                    v90,
                    v85,
                    v84);
            v6 = v88;
            v92 = v49;
            goto LABEL_147;
          }
LABEL_146:
          v49 = v92;
          goto LABEL_147;
        }
      }
      else
      {
        v90 = 0;
      }
      v49 = -2147024882;
      v92 = -2147024882;
      goto LABEL_147;
    }
    if ( tableid != -1 )
    {
      CDBSession::CloseTableid(*(CDBSession **)(*((_DWORD *)v91 + 2) + 52), tableid);
      tableid = -1;
    }
    goto LABEL_146;
  }
  while ( 1 )
  {
    v31 = 0;
    v32 = *((_DWORD *)v91 + 2);
    v82 = (JoltProperties *)(v32 + 84);
    v33 = *(_DWORD *)(v32 + 84);
    if ( v33 )
    {
      do
      {
        v33 = *(_DWORD *)(v33 + 40);
        ++v31;
      }
      while ( v33 );
      if ( v31 )
      {
        if ( !v76 )
        {
          v49 = -2147217904;
          v92 = -2147217904;
          goto LABEL_147;
        }
        v92 = CJetParameterList::BuildJetParameterBuffer(v82, (struct CCommand *)v32, v76, v87);
        if ( v92 < 0 )
          goto LABEL_146;
      }
    }
    v34 = v91;
    *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v91 + 2) + 52) + 8) = 0;
    v35 = (_DWORD *)*((_DWORD *)v34 + 2);
    v88 = v72 | 0x1000100;
    v82 = *(JoltProperties **)(v35[5] + 24);
    if ( JoltProperties::BinarySearch(v82, 0xEFu, &v70) < 0
      || (v36 = *((_DWORD *)v82 + 4), *(_WORD *)(v36 + 48 * v70 + 16) != 3)
      || (v37 = *(_DWORD *)(v36 + 48 * v70 + 24)) == 0 )
    {
      v75 = *(JoltProperties **)(*(_DWORD *)(v35[13] + 84) + 164);
      if ( JoltProperties::BinarySearch(v75, 0x109u, &v69) < 0 )
        goto LABEL_46;
      v38 = *((_DWORD *)v75 + 4);
      if ( *(_WORD *)(v38 + 48 * v69 + 16) != 3 )
        goto LABEL_46;
      v37 = *(_DWORD *)(v38 + 48 * v69 + 24);
    }
    if ( v37 == 2 )
      v88 |= 0x4000u;
LABEL_46:
    if ( JoltProperties::BinarySearch(v82, 0x10Cu, &v68) < 0
      || (v39 = *((_DWORD *)v82 + 4), *(_WORD *)(v39 + 48 * v68 + 16) != 3)
      || (v40 = *(_DWORD *)(v39 + 48 * v68 + 24)) == 0 )
    {
      v75 = *(JoltProperties **)(*(_DWORD *)(v35[13] + 84) + 164);
      if ( JoltProperties::BinarySearch(v75, 0x10Bu, (unsigned int *)&v78) < 0 )
        goto LABEL_53;
      v41 = *((_DWORD *)v75 + 4);
      if ( *(_WORD *)(v41 + 48 * (_DWORD)v78 + 16) != 3 )
        goto LABEL_53;
      v40 = *(_DWORD *)(v41 + 48 * (_DWORD)v78 + 24);
    }
    if ( v40 > 1 )
    {
      v42 = v88;
      goto LABEL_55;
    }
LABEL_53:
    v42 = v88 | 0x200000;
LABEL_55:
    if ( v35[18] == 1 && v35[25] == -1 )
    {
      v6 = JetOpenTable(sesid, v74, v35[19], v35[23], v35[22], v42, &tableid);
      v88 = v6;
    }
    else
    {
      v6 = JetExecuteTempQuery(sesid, v74, v35[25], v35[23], v35[22], v42, &tableid);
      v88 = v6;
    }
    if ( v6 <= -1513 )
      break;
    if ( v6 <= -1016 )
    {
      if ( v6 == -1016 )
        goto LABEL_127;
      if ( v6 <= -1305 )
      {
        if ( v6 != -1305 )
        {
          switch ( v6 )
          {
            case -1508:
            case -1506:
            case -1404:
              goto LABEL_127;
            case -1507:
            case -1314:
              goto LABEL_105;
            default:
              goto LABEL_113;
          }
        }
        goto LABEL_100;
      }
      if ( v6 > -1048 )
      {
        if ( v6 != -1047 )
          goto LABEL_113;
        v92 = -2147217833;
        goto LABEL_148;
      }
      if ( v6 == -1048 )
      {
LABEL_127:
        v49 = -2147217887;
        v92 = -2147217887;
        goto LABEL_147;
      }
      if ( v6 == -1304 || v6 == -1303 )
        goto LABEL_105;
LABEL_113:
      v49 = -2147467259;
      v92 = -2147467259;
      goto LABEL_147;
    }
    if ( v6 > 1409 )
    {
      if ( v6 > 3061 )
      {
        if ( v6 == 5011 )
          goto LABEL_90;
        goto LABEL_89;
      }
      if ( v6 == 3061 )
        goto LABEL_73;
      if ( v6 == 3026 || v6 == 3032 )
        goto LABEL_74;
    }
    else
    {
      if ( v6 == 1409 )
        goto LABEL_90;
      if ( v6 <= 1111 )
      {
        switch ( v6 )
        {
          case 1111:
            goto LABEL_69;
          case 0:
            goto LABEL_75;
          case 1110:
            goto LABEL_69;
        }
LABEL_89:
        if ( v6 <= 0 )
          goto LABEL_113;
        goto LABEL_90;
      }
      if ( v6 == 1112 )
      {
LABEL_69:
        v43 = *(CDBSession **)(*((_DWORD *)v91 + 2) + 52);
        if ( v6 == 1110 )
          v44 = CDBSession::pushTransactionState(v43);
        else
          v44 = CDBSession::popTransactionState(v43, v6 == 1111);
        v92 = v44;
        if ( v44 < 0 )
          goto LABEL_146;
LABEL_73:
        v80 = 0;
        tableid = -1;
LABEL_74:
        v6 = 0;
        v88 = 0;
LABEL_75:
        if ( tableid == -1 )
        {
          v80 = 0;
        }
        else if ( v80 == 1 )
        {
          v45 = v86;
          if ( v86 > 1 )
            v45 = 1;
          v86 = v45;
        }
        if ( v81 )
          *(_DWORD *)v81 += *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v91 + 2) + 52) + 8);
      }
    }
LABEL_90:
    if ( ++v87 >= v86 )
      goto LABEL_91;
  }
  if ( v6 == -1513 )
    goto LABEL_105;
  if ( v6 > -3103 )
  {
    if ( v6 > -1907 )
    {
      if ( v6 != -1809 )
        goto LABEL_113;
    }
    else if ( v6 != -1907 )
    {
      switch ( v6 )
      {
        case -3102:
        case -3072:
        case -3064:
        case -3037:
        case -3019:
        case -3018:
        case -3013:
        case -3012:
        case -3008:
          goto LABEL_105;
        case -3101:
        case -3011:
          goto LABEL_127;
        case -3100:
        case -3030:
          if ( (int)JetGetLastErrorInfo(sesid, v93, 20, 0, 0, 0, 0, 0, 0, 0) < 0 )
            goto LABEL_105;
          if ( v6 != -3100 )
          {
            if ( v6 != -3030 )
              goto LABEL_105;
            if ( v95 == 6 )
            {
              v92 = -2147217833;
              goto LABEL_148;
            }
            if ( v94 == -8239 )
            {
              v92 = -2147217913;
              goto LABEL_148;
            }
            goto LABEL_105;
          }
          if ( v95 != 10001 )
            goto LABEL_105;
          v92 = -2147217913;
          break;
        case -3084:
        case -3010:
          v92 = -2147217904;
          goto LABEL_148;
        default:
          goto LABEL_113;
      }
      goto LABEL_148;
    }
    v92 = -2147217911;
    goto LABEL_148;
  }
  if ( v6 == -3103 )
    goto LABEL_105;
  if ( v6 == -3817 )
  {
LABEL_100:
    v92 = -2147217865;
    goto LABEL_148;
  }
  if ( v6 != -3500 )
    goto LABEL_113;
LABEL_105:
  v49 = -2147217900;
  v92 = -2147217900;
LABEL_147:
  if ( v6 )
  {
LABEL_148:
    v63 = v6;
    v17 = v92;
    CExtError::SendJetErrortoOLEAuto(v63, (int)&IID_ICommand, (int)v66, v67);
    goto LABEL_156;
  }
  v17 = v49;
  v92 = v49;
  if ( v49 >= 0 )
    goto LABEL_156;
  v92 = v49;
LABEL_153:
  v54 = *(_DWORD *)(*((_DWORD *)v91 + 2) + 52);
  v19 = *(_DWORD *)(v54 + 20);
  v20 = *(_DWORD *)(v54 + 16);
  if ( v17 == -2147024882 )
    goto LABEL_156;
LABEL_154:
  if ( !JetGetDatabaseInfo(v20, v19, &v77, 4, 3) )
    CExtError::SendHRtoOLEAuto((int)&IID_ICommand, 0, v66, (int)v67);
LABEL_156:
  if ( !v17 )
  {
    if ( v83 == 1 )
      v17 = 265946;
    v92 = v17;
  }
LABEL_160:
  v55 = *((_DWORD *)v91 + 2);
  if ( v71 != ((*(_DWORD *)(v55 + 60) >> 4) & 1) )
  {
    v56 = v91;
    *(_DWORD *)(v55 + 60) &= ~0x10u;
    CJetParameterList::PurgeParameters((CJetParameterList *)(*((_DWORD *)v56 + 2) + 84));
    v57 = *((_DWORD *)v91 + 2);
    v58 = *(JET_SESID **)(v57 + 52);
    v59 = *(_DWORD *)(v57 + 100);
    v78 = (CDBSession *)v58;
    v77 = v59;
    if ( v59 != -1 && JetCloseTable(v58[4], v59) == -1108 )
      CDBSession::AddJetTableId(v78, v77);
    *(_DWORD *)(*((_DWORD *)v91 + 2) + 100) = -1;
  }
  if ( v17 < 0 )
  {
    if ( v84 )
      *v84 = 0;
    if ( v90 )
    {
      (*(void (__thiscall **)(CRowset *, int))(*(_DWORD *)v90 + 12))(v90, 1);
      v17 = v92;
    }
    if ( tableid != -1 )
      JetCloseTable(sesid, tableid);
  }
  if ( v12 )
    LeaveCriticalSection(v12);
  if ( v11 )
    LeaveCriticalSection(v11);
  return v17;
}

```

## disassembly

```asm
0x1000fcf0  mov     edi, edi
0x1000fcf2  push    ebp
0x1000fcf3  mov     ebp, esp
0x1000fcf5  push    0FFFFFFFFh
0x1000fcf7  push    offset ?Execute@CImpICommandText@@UAGJPAUIUnknown@@ABU_GUID@@PAUtagDBPARAMS@@PAJPAPAU2@@Z_SEH
0x1000fcfc  mov     eax, large fs:0
0x1000fd02  push    eax
0x1000fd03  sub     esp, 84h
0x1000fd09  mov     eax, ___security_cookie
0x1000fd0e  xor     eax, ebp
0x1000fd10  mov     [ebp+var_10], eax
0x1000fd13  push    ebx
0x1000fd14  push    esi
0x1000fd15  push    edi; int
0x1000fd16  push    eax; struct _GUID *
0x1000fd17  lea     eax, [ebp+var_C]
0x1000fd1a  mov     large fs:0, eax
0x1000fd20  mov     eax, [ebp+arg_4]
0x1000fd23  xor     ebx, ebx
0x1000fd25  mov     edi, [ebp+this]
0x1000fd28  mov     edx, [ebp+arg_C]
0x1000fd2b  mov     [ebp+var_74], eax
0x1000fd2e  mov     eax, [ebp+arg_8]
0x1000fd31  mov     [ebp+var_44], eax
0x1000fd34  mov     eax, [ebp+arg_10]
0x1000fd37  mov     [ebp+var_54], eax
0x1000fd3a  mov     eax, [ebp+arg_14]
0x1000fd3d  mov     [ebp+var_48], eax
0x1000fd40  mov     eax, [edi+8]
0x1000fd43  mov     [ebp+tableid], 0FFFFFFFFh
0x1000fd4a  push    ebx; perrinfo
0x1000fd4b  push    ebx; dwReserved
0x1000fd4c  mov     eax, [eax+34h]
0x1000fd4f  mov     [ebp+var_2C], edi
0x1000fd52  mov     [ebp+var_68], edx
0x1000fd55  mov     [ebp+var_38], ebx
0x1000fd58  mov     ecx, [eax+10h]
0x1000fd5b  mov     eax, [eax+14h]
0x1000fd5e  mov     [ebp+var_30], ebx
0x1000fd61  mov     [ebp+var_58], 1
0x1000fd68  mov     [ebp+sesid], ecx
0x1000fd6b  mov     [ebp+var_70], eax
0x1000fd6e  mov     [ebp+var_7C], ebx
0x1000fd71  mov     [ebp+var_4C], ebx
0x1000fd74  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1000fd7a  mov     esi, [edi+8]
0x1000fd7d  add     esi, 0F8h
0x1000fd83  push    esi; lpCriticalSection
0x1000fd84  mov     [ebp+var_8C], esi
0x1000fd8a  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000fd90  mov     [ebp+var_4], ebx
0x1000fd93  mov     edi, [edi+8]
0x1000fd96  mov     edi, [edi+34h]
0x1000fd99  add     edi, 68h ; 'h'
0x1000fd9c  push    edi; lpCriticalSection
0x1000fd9d  mov     [ebp+var_90], edi
0x1000fda3  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000fda9  mov     ecx, [ebp+var_2C]
0x1000fdac  mov     byte ptr [ebp+var_4], 1
0x1000fdb0  mov     ecx, [ecx+8]
0x1000fdb3  call    ?CheckForZombieCommandAndFix@CCommand@@QAGJXZ; CCommand::CheckForZombieCommandAndFix(void)
0x1000fdb8  mov     [ebp+var_28], eax
0x1000fdbb  test    eax, eax
0x1000fdbd  js      loc_10010525
0x1000fdc3  mov     ecx, [ebp+var_2C]
0x1000fdc6  mov     eax, [ecx+8]
0x1000fdc9  mov     [ebp+var_28], eax
0x1000fdcc  mov     eax, [eax+3Ch]
0x1000fdcf  shr     eax, 4
0x1000fdd2  and     eax, 1
0x1000fdd5  mov     [ebp+var_7C], eax
0x1000fdd8  mov     eax, [ebp+var_54]
0x1000fddb  test    eax, eax
0x1000fddd  jz      short loc_1000FDE7
0x1000fddf  mov     [eax], ebx
0x1000fde1  mov     eax, [ecx+8]
0x1000fde4  mov     [ebp+var_28], eax
0x1000fde7  mov     eax, [ebp+var_48]
0x1000fdea  test    eax, eax
0x1000fdec  jz      short loc_1000FDFA
0x1000fdee  mov     dword ptr [eax], 0
0x1000fdf4  mov     eax, [ecx+8]
0x1000fdf7  mov     [ebp+var_28], eax
0x1000fdfa  mov     edx, [ebp+var_68]
0x1000fdfd  test    edx, edx
0x1000fdff  jz      short loc_1000FE31
0x1000fe01  mov     eax, [edx+4]
0x1000fe04  test    eax, eax
0x1000fe06  jz      short loc_1000FE0D
0x1000fe08  cmp     dword ptr [edx], 0
0x1000fe0b  jz      short loc_1000FE18
0x1000fe0d  cmp     eax, 1
0x1000fe10  jbe     short loc_1000FE31
0x1000fe12  cmp     [ebp+var_48], 0
0x1000fe16  jz      short loc_1000FE37
0x1000fe18  mov     eax, [ecx+8]
0x1000fe1b  mov     ebx, 80070057h
0x1000fe20  mov     [ebp+var_28], ebx
0x1000fe23  mov     eax, [eax+34h]
0x1000fe26  mov     ecx, [eax+14h]
0x1000fe29  mov     eax, [eax+10h]
0x1000fe2c  jmp     loc_10010543
0x1000fe31  cmp     [ebp+var_48], 0
0x1000fe35  jnz     short loc_1000FE58
0x1000fe37  mov     edx, [ebp+var_44]
0x1000fe3a  mov     ecx, offset _GUID_NULL
0x1000fe3f  mov     [ebp+var_3C], 0Ch
0x1000fe46  mov     eax, [ecx]
0x1000fe48  cmp     eax, [edx]
0x1000fe4a  jnz     short loc_1000FEAB
0x1000fe4c  add     ecx, 4
0x1000fe4f  add     edx, 4
0x1000fe52  sub     [ebp+var_3C], 4
0x1000fe56  jnb     short loc_1000FE46
0x1000fe58  cmp     [ebp+var_74], 0
0x1000fe5c  jz      short loc_1000FE82
0x1000fe5e  mov     edx, [ebp+var_44]
0x1000fe61  mov     ecx, offset _IID_IUnknown
0x1000fe66  mov     [ebp+var_3C], 0Ch
0x1000fe6d  nop     dword ptr [eax]
0x1000fe70  mov     eax, [ecx]
0x1000fe72  cmp     eax, [edx]
0x1000fe74  jnz     short loc_1000FEC7
0x1000fe76  add     ecx, 4
0x1000fe79  add     edx, 4
0x1000fe7c  sub     [ebp+var_3C], 4
0x1000fe80  jnb     short loc_1000FE70
0x1000fe82  mov     edx, [ebp+var_68]
0x1000fe85  test    edx, edx
0x1000fe87  jz      short loc_1000FE93
0x1000fe89  mov     edx, [edx+4]
0x1000fe8c  mov     [ebp+var_40], edx
0x1000fe8f  test    edx, edx
0x1000fe91  jnz     short loc_1000FE9A
0x1000fe93  mov     [ebp+var_40], 1
0x1000fe9a  mov     ecx, [ebp+var_28]
0x1000fe9d  mov     eax, [ecx+3Ch]
0x1000fea0  test    al, 20h
0x1000fea2  jnz     short loc_1000FECE
0x1000fea4  mov     ebx, 80040E0Ch
0x1000fea9  jmp     short loc_1000FEB0
0x1000feab  mov     ebx, 80070057h
0x1000feb0  mov     ecx, [ebp+var_2C]
0x1000feb3  mov     [ebp+var_28], ebx
0x1000feb6  mov     eax, [ecx+8]
0x1000feb9  mov     eax, [eax+34h]
0x1000febc  mov     ecx, [eax+14h]
0x1000febf  mov     eax, [eax+10h]
0x1000fec2  jmp     loc_10010543
0x1000fec7  mov     ebx, 80040E22h
0x1000fecc  jmp     short loc_1000FEB0
0x1000fece  test    al, 10h
0x1000fed0  jnz     short loc_1000FF14
0x1000fed2  or      eax, 100h
0x1000fed7  mov     [ecx+3Ch], eax
0x1000feda  mov     ecx, [ebp+var_2C]
0x1000fedd  push    0
0x1000fedf  mov     eax, [ecx+8]
0x1000fee2  mov     ecx, [eax+18h]
0x1000fee5  push    ecx
0x1000fee6  mov     eax, [ecx]
0x1000fee8  mov     ebx, [eax+0Ch]
0x1000feeb  mov     ecx, ebx
0x1000feed  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000fef3  call    ebx
0x1000fef5  mov     ecx, [ebp+var_2C]
0x1000fef8  mov     ebx, eax
0x1000fefa  mov     [ebp+var_28], ebx
0x1000fefd  mov     eax, [ecx+8]
0x1000ff00  and     dword ptr [eax+3Ch], 0FFFFFEFFh
0x1000ff07  test    ebx, ebx
0x1000ff09  js      loc_10010577
0x1000ff0f  mov     ecx, [ecx+8]
0x1000ff12  xor     ebx, ebx
0x1000ff14  mov     ecx, [ecx+14h]
0x1000ff17  lea     eax, [ebp+var_64]
0x1000ff1a  push    0; int
0x1000ff1c  push    eax; enum eJetCursorType *
0x1000ff1d  push    [ebp+var_44]; struct _GUID *
0x1000ff20  lea     eax, [ebp+var_78]
0x1000ff23  add     ecx, 0Ch; this
0x1000ff26  push    eax; unsigned int *
0x1000ff27  call    ?ValidateStateForJetOpenTable@CRowsetProperties@@QAEJAAKABU_GUID@@AAW4eJetCursorType@@H@Z; CRowsetProperties::ValidateStateForJetOpenTable(ulong &,_GUID const &,eJetCursorType &,int)
0x1000ff2c  mov     [ebp+var_28], eax
0x1000ff2f  test    eax, eax
0x1000ff31  js      loc_10010529
0x1000ff37  cmp     [ebp+var_40], 0
0x1000ff3b  mov     [ebp+var_3C], 0
0x1000ff42  jbe     loc_1001022F
0x1000ff48  mov     ecx, [ebp+var_2C]
0x1000ff4b  xor     edx, edx
0x1000ff4d  mov     ecx, [ecx+8]
0x1000ff50  lea     eax, [ecx+54h]
0x1000ff53  mov     [ebp+var_50], eax
0x1000ff56  mov     eax, [eax]
0x1000ff58  test    eax, eax
0x1000ff5a  jz      short loc_1000FF8F
0x1000ff5c  nop     dword ptr [eax+00h]
0x1000ff60  mov     eax, [eax+28h]
0x1000ff63  inc     edx
0x1000ff64  test    eax, eax
0x1000ff66  jnz     short loc_1000FF60
0x1000ff68  test    edx, edx
0x1000ff6a  jz      short loc_1000FF8F
0x1000ff6c  mov     eax, [ebp+var_68]
0x1000ff6f  test    eax, eax
0x1000ff71  jz      loc_1001025D
0x1000ff77  push    [ebp+var_3C]; unsigned int
0x1000ff7a  push    eax; struct tagDBPARAMS *
0x1000ff7b  push    ecx; struct CCommand *
0x1000ff7c  mov     ecx, [ebp+var_50]; this
0x1000ff7f  call    ?BuildJetParameterBuffer@CJetParameterList@@QAEJPAVCCommand@@PAUtagDBPARAMS@@K@Z; CJetParameterList::BuildJetParameterBuffer(CCommand *,tagDBPARAMS *,ulong)
0x1000ff84  mov     [ebp+var_28], eax
0x1000ff87  test    eax, eax
0x1000ff89  js      loc_100104E0
0x1000ff8f  mov     ecx, [ebp+var_2C]
0x1000ff92  mov     eax, [ecx+8]
0x1000ff95  mov     eax, [eax+34h]
0x1000ff98  mov     dword ptr [eax+8], 0
0x1000ff9f  mov     ebx, [ecx+8]
0x1000ffa2  lea     ecx, [ebp+var_80]
0x1000ffa5  mov     eax, [ebp+var_78]
0x1000ffa8  or      eax, 1000100h
0x1000ffad  mov     [ebp+var_38], eax
0x1000ffb0  mov     eax, [ebx+14h]
0x1000ffb3  push    ecx; unsigned int *
0x1000ffb4  push    0EFh; unsigned int
0x1000ffb9  mov     eax, [eax+18h]
0x1000ffbc  mov     ecx, eax; this
0x1000ffbe  mov     [ebp+var_50], eax
0x1000ffc1  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1000ffc6  test    eax, eax
0x1000ffc8  js      short loc_1000FFEC
0x1000ffca  mov     eax, [ebp+var_80]
0x1000ffcd  mov     edx, 3
0x1000ffd2  lea     ecx, [eax+eax*2]
0x1000ffd5  mov     eax, [ebp+var_50]
0x1000ffd8  add     ecx, ecx
0x1000ffda  mov     eax, [eax+10h]
0x1000ffdd  cmp     dx, [eax+ecx*8+10h]
0x1000ffe2  jnz     short loc_1000FFEC
0x1000ffe4  mov     eax, [eax+ecx*8+18h]
0x1000ffe8  test    eax, eax
0x1000ffea  jnz     short loc_10010033
0x1000ffec  mov     eax, [ebx+34h]
0x1000ffef  lea     ecx, [ebp+var_84]
0x1000fff5  push    ecx; unsigned int *
0x1000fff6  push    109h; unsigned int
0x1000fffb  mov     eax, [eax+54h]
0x1000fffe  mov     eax, [eax+0A4h]
0x10010004  mov     ecx, eax; this
0x10010006  mov     [ebp+var_6C], eax
0x10010009  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1001000e  test    eax, eax
0x10010010  js      short loc_1001003F
0x10010012  mov     eax, [ebp+var_84]
0x10010018  mov     edx, 3
0x1001001d  lea     ecx, [eax+eax*2]
0x10010020  mov     eax, [ebp+var_6C]
0x10010023  add     ecx, ecx
0x10010025  mov     eax, [eax+10h]
0x10010028  cmp     dx, [eax+ecx*8+10h]
0x1001002d  jnz     short loc_1001003F
0x1001002f  mov     eax, [eax+ecx*8+18h]
0x10010033  sub     eax, 2
0x10010036  jnz     short loc_1001003F
0x10010038  or      [ebp+var_38], 4000h
0x1001003f  mov     ecx, [ebp+var_50]; this
0x10010042  lea     eax, [ebp+var_88]
0x10010048  push    eax; unsigned int *
0x10010049  push    10Ch; unsigned int
0x1001004e  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10010053  test    eax, eax
0x10010055  js      short loc_1001007C
0x10010057  mov     eax, [ebp+var_88]
0x1001005d  mov     edx, 3
0x10010062  lea     ecx, [eax+eax*2]
0x10010065  mov     eax, [ebp+var_50]
0x10010068  add     ecx, ecx
0x1001006a  mov     eax, [eax+10h]
0x1001006d  cmp     dx, [eax+ecx*8+10h]
0x10010072  jnz     short loc_1001007C
0x10010074  mov     eax, [eax+ecx*8+18h]
0x10010078  test    eax, eax
0x1001007a  jnz     short loc_100100BD
0x1001007c  mov     eax, [ebx+34h]
0x1001007f  lea     ecx, [ebp+var_60]
0x10010082  push    ecx; unsigned int *
0x10010083  push    10Bh; unsigned int
0x10010088  mov     eax, [eax+54h]
0x1001008b  mov     eax, [eax+0A4h]
0x10010091  mov     ecx, eax; this
0x10010093  mov     [ebp+var_6C], eax
0x10010096  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1001009b  test    eax, eax
0x1001009d  js      short loc_100100C7
0x1001009f  mov     eax, [ebp+var_60]
0x100100a2  mov     edx, 3
0x100100a7  lea     ecx, [eax+eax*2]
0x100100aa  mov     eax, [ebp+var_6C]
  ... truncated ...
```
