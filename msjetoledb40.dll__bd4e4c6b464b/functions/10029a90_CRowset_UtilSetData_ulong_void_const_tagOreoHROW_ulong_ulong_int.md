# CRowset::UtilSetData(ulong,void const *,tagOreoHROW *,ulong,ulong,int)

- ea: `0x10029a90`
- end: `0x1002b526`
- name: `?UtilSetData@CRowset@@IAGJKPBXPAUtagOreoHROW@@KKH@Z`
- size: `6806`
- prototype: `int(CRowset *__hidden this, unsigned int, const void *, struct tagOreoHROW *, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x10032ba0`
- `0x10032e50`

## callees

- `0x1000bb00`
- `0x1001bdc0`
- `0x1001c6d0`
- `0x10027a40`
- `0x10027a60`
- `0x10027b80`
- `0x10027c40`
- `0x10029a90`
- `0x1002c700`
- `0x1002d9b0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d420`
- `0x1004dc50`
- `0x1004dc81`
- `0x1004dc8d`

## import_xrefs

- `OLEAUT32!__imp__SysAllocString@4` at `0x1002a238`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1002a238`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1002af44`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1002b0dd`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1002af44`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1002b0dd`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10029d36`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1002b02e`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1002b414`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10029d36`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1002b02e`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1002b414`
- `msjet40!__imp__JetSetColumn@28` at `0x1002aa01`
- `msjet40!__imp__JetSetColumn@28` at `0x1002ac6a`
- `msjet40!__imp__JetSetColumn@28` at `0x1002ad39`
- `msjet40!__imp__JetSetColumn@28` at `0x1002adc6`
- `msjet40!__imp__JetSetColumn@28` at `0x1002aa01`
- `msjet40!__imp__JetSetColumn@28` at `0x1002ac6a`
- `msjet40!__imp__JetSetColumn@28` at `0x1002ad39`
- `msjet40!__imp__JetSetColumn@28` at `0x1002adc6`
- `msjet40!__imp__JetUpdate@20` at `0x1002afba`
- `msjet40!__imp__JetUpdate@20` at `0x1002afba`
- `msjet40!__imp__JetOpenILockBytes@20` at `0x1002a673`
- `msjet40!__imp__JetOpenILockBytes@20` at `0x1002a673`

## pseudocode

```c
int __userpurge CRowset::UtilSetData@<eax>(
        unsigned int a1@<edx>,
        _DWORD *a2@<ecx>,
        CRowset *this,
        JET_ERR *a4,
        unsigned int prep,
        struct tagOreoHROW *a6,
        unsigned int a7,
        unsigned int a8,
        int a9)
{
  int v9; // ebx
  size_t *v10; // esi
  int v11; // ebx
  size_t v12; // eax
  size_t v13; // ecx
  int v14; // ecx
  int EditCursor; // ebx
  CRowset *v16; // edi
  unsigned int v17; // esi
  int v18; // edx
  JET_TABLEID v19; // eax
  bool v20; // zf
  JET_TABLEID v21; // ebx
  int v22; // esi
  unsigned int v23; // eax
  JET_ERR v24; // eax
  JET_ERR v25; // edi
  int v26; // ecx
  JET_ERR *v27; // edx
  CRowset *v28; // eax
  JET_ERR v29; // eax
  int v30; // eax
  BOOL v31; // ecx
  JET_TABLEID v32; // esi
  char *v33; // ebx
  JET_GRBIT v34; // eax
  _DWORD *v35; // ecx
  int v36; // eax
  int v37; // eax
  int *v38; // eax
  int v39; // ecx
  int v40; // ecx
  int v41; // eax
  int v42; // eax
  JET_COLUMNID v43; // ecx
  int v44; // eax
  int v45; // ebx
  JET_TABLEID v46; // edx
  int v47; // esi
  int *v48; // ecx
  int v49; // edx
  __int16 v50; // ax
  int v51; // edx
  _DWORD *v52; // edx
  GUID *v53; // ecx
  unsigned int v54; // esi
  bool v55; // cf
  int v56; // ecx
  unsigned int v57; // ecx
  _DWORD *v58; // edx
  _WORD *v59; // ebx
  unsigned __int16 *v60; // esi
  int v61; // eax
  unsigned int *v62; // ecx
  char *v63; // ebx
  OLECHAR *v64; // eax
  unsigned int v65; // eax
  unsigned int v66; // eax
  _WORD *v67; // edx
  _WORD *v68; // ecx
  int v70; // eax
  int v71; // eax
  CRowset *v72; // edx
  bool v73; // sf
  int v74; // eax
  unsigned int v75; // eax
  int v76; // eax
  CRowset *v77; // edx
  int v78; // edx
  __int16 v79; // cx
  char v80; // al
  int v81; // eax
  int v82; // eax
  __int16 v83; // bx
  const char *v84; // eax
  JET_TABLEID v85; // edx
  JET_TABLEID v86; // esi
  JET_GRBIT v87; // ecx
  JET_ERR v88; // eax
  JET_ERR v89; // ebx
  JET_TABLEID v90; // ebx
  int v91; // eax
  int v92; // eax
  int v93; // eax
  int v94; // eax
  int v95; // ebx
  JET_GRBIT v96; // ecx
  int v97; // ebx
  const char *v98; // eax
  CRowset *v99; // ebx
  int v100; // eax
  const char *v101; // eax
  _DWORD **v102; // ecx
  int v103; // ebx
  int v104; // eax
  _DWORD *v105; // ecx
  JET_GRBIT v106; // ebx
  void *v107; // edx
  int v108; // esi
  unsigned int v109; // eax
  JET_ERR v110; // eax
  int v111; // eax
  JET_ERR v112; // eax
  CRowset *v113; // eax
  JET_ERR v114; // eax
  unsigned int v115; // eax
  CRowset *v116; // ecx
  JET_ERR v117; // ecx
  int v118; // eax
  CRowset *v120; // eax
  CRowset *v121; // ebx
  unsigned int v122; // esi
  JET_COLUMNID v123; // ecx
  int v124; // eax
  int v125; // eax
  int v126; // edx
  int v127; // eax
  int v128; // edx
  unsigned int v129; // ecx
  int v130; // esi
  _DWORD *v131; // ecx
  int v132; // ecx
  _DWORD *v133; // ecx
  int v134; // eax
  JET_ERR *v135; // edx
  unsigned int v136; // eax
  CRowset *v137; // ecx
  unsigned int v138; // [esp-8h] [ebp-1104h]
  unsigned int *v139; // [esp+0h] [ebp-10FCh]
  enum DBREASONENUM v140; // [esp+0h] [ebp-10FCh]
  enum DBREASONENUM v141; // [esp+0h] [ebp-10FCh]
  const struct _GUID *v142; // [esp+4h] [ebp-10F8h]
  enum DBEVENTPHASEENUM v143; // [esp+4h] [ebp-10F8h]
  enum DBEVENTPHASEENUM v144; // [esp+4h] [ebp-10F8h]
  int v145; // [esp+Ch] [ebp-10F0h]
  unsigned int pcbActual; // [esp+10h] [ebp-10ECh] BYREF
  JET_ERR v147; // [esp+14h] [ebp-10E8h]
  int v148; // [esp+18h] [ebp-10E4h]
  int v149; // [esp+1Ch] [ebp-10E0h]
  int v150; // [esp+20h] [ebp-10DCh]
  int v151; // [esp+24h] [ebp-10D8h]
  JET_ERR pvBookmark; // [esp+28h] [ebp-10D4h] BYREF
  int v153; // [esp+2Ch] [ebp-10D0h]
  CRowset *v154; // [esp+30h] [ebp-10CCh]
  int v155; // [esp+34h] [ebp-10C8h]
  int v156; // [esp+38h] [ebp-10C4h]
  CPendingChange *v157; // [esp+3Ch] [ebp-10C0h]
  int v158; // [esp+40h] [ebp-10BCh]
  _DWORD *v159; // [esp+44h] [ebp-10B8h]
  int v160; // [esp+48h] [ebp-10B4h] BYREF
  int v161; // [esp+4Ch] [ebp-10B0h]
  int v162; // [esp+50h] [ebp-10ACh]
  BSTR bstrString; // [esp+54h] [ebp-10A8h]
  int v164; // [esp+58h] [ebp-10A4h]
  unsigned int v165; // [esp+5Ch] [ebp-10A0h]
  JET_SESID sesid; // [esp+60h] [ebp-109Ch]
  JET_ERR *v167; // [esp+64h] [ebp-1098h]
  void *pvData; // [esp+68h] [ebp-1094h] BYREF
  int v169; // [esp+6Ch] [ebp-1090h] BYREF
  int v170; // [esp+70h] [ebp-108Ch]
  unsigned int cbData; // [esp+74h] [ebp-1088h] BYREF
  int v172; // [esp+78h] [ebp-1084h]
  int v173; // [esp+7Ch] [ebp-1080h]
  int v174; // [esp+80h] [ebp-107Ch] BYREF
  int v175; // [esp+84h] [ebp-1078h]
  const char *v176; // [esp+88h] [ebp-1074h]
  JET_COLUMNID columnid; // [esp+8Ch] [ebp-1070h]
  _DWORD *v178; // [esp+90h] [ebp-106Ch] BYREF
  int v179; // [esp+94h] [ebp-1068h]
  int *v180; // [esp+98h] [ebp-1064h]
  CRowset *v181; // [esp+9Ch] [ebp-1060h]
  int v182; // [esp+A0h] [ebp-105Ch]
  int v183; // [esp+A4h] [ebp-1058h] BYREF
  JET_GRBIT grbit; // [esp+A8h] [ebp-1054h] BYREF
  JET_TABLEID tableid; // [esp+ACh] [ebp-1050h]
  _DWORD v186[18]; // [esp+B0h] [ebp-104Ch] BYREF
  _BYTE v187[4096]; // [esp+F8h] [ebp-1004h] BYREF

  v181 = (CRowset *)a2;
  v154 = this;
  v9 = a2[55];
  v10 = (size_t *)a2[25];
  sesid = *(_DWORD *)(a2[14] + 16);
  v157 = (CPendingChange *)(a2 + 55);
  v149 = v9;
  v150 = a2[56];
  v11 = a2[58];
  v148 = a2[59];
  v147 = a4[1];
  v162 = 0;
  v165 = 0;
  bstrString = 0;
  v12 = v10[5];
  v13 = v10[6];
  v167 = a4;
  tableid = 0;
  v169 = 0;
  v145 = v11;
  v153 = 0;
  v161 = 0;
  if ( a1 > v13 + 8 * v12 - 1
    || (*(_BYTE *)(((a1 - v13) >> 3) + v10[4]) & *((_BYTE *)&Bitmap::ThisBit + ((a1 - v13) & 7))) != 0 )
  {
    v16 = v181;
    v14 = 0;
    v17 = 0;
    EditCursor = -2147217920;
    v18 = 0;
    goto LABEL_326;
  }
  memcpy(&v169, (const void *)(v10[2] + a1 * *v10), *v10);
  v14 = v169;
  EditCursor = 0;
  v170 = v169;
  if ( v154 )
  {
    if ( *(_DWORD *)(v169 + 36) )
      goto LABEL_9;
  }
  else if ( !v169 || *(_DWORD *)(v169 + 36) )
  {
    v16 = v181;
    v17 = 0;
    EditCursor = -2147024809;
    v18 = 0;
LABEL_326:
    if ( a7 == 1 && v18 == 1 )
    {
      v20 = *((_DWORD *)v16 + 13) == 0;
      v115 = *(_DWORD *)(v14 + 32);
      v116 = *(CRowset **)(v14 + 36);
      v160 = (int)a6;
      if ( !v20 )
      {
        CRowset::ColumnNotify(
          v116,
          v115,
          (unsigned int)v116,
          (const unsigned int *const)3,
          (enum DBREASONENUM)v139,
          (enum DBEVENTPHASEENUM)v142);
        if ( v17 )
          CRowset::RowNotify((CRowset *)&v160, 7u, (const unsigned int *const)3, v140, v143);
      }
    }
    goto LABEL_331;
  }
  if ( prep )
    goto LABEL_385;
LABEL_9:
  if ( !*(_DWORD *)(v169 + 8) )
  {
    v16 = v181;
    v17 = 0;
    EditCursor = -2147217845;
    v18 = 0;
    goto LABEL_326;
  }
  if ( *(_DWORD *)v157 == -1 )
  {
    if ( !v150 )
      goto LABEL_15;
    if ( !*((_DWORD *)v181 + 56) )
      goto LABEL_399;
  }
  if ( *(_DWORD *)v157 != *v167 || !prep )
  {
LABEL_399:
    v16 = v181;
    EditCursor = -2147217836;
    goto LABEL_400;
  }
LABEL_15:
  v16 = v181;
  EditCursor = 0;
  v179 = 0;
  if ( (*((_BYTE *)v181 + 96) & 0x10) != 0 )
  {
    v19 = *((_DWORD *)v181 + 27);
  }
  else
  {
    EditCursor = CRowset::GetEditCursor(v181);
    v179 = EditCursor;
    if ( EditCursor < 0 )
      goto LABEL_400;
    v19 = *((_DWORD *)v16 + 28);
  }
  v20 = *(_DWORD *)v157 == -1;
  tableid = v19;
  if ( !v20
    || *((_DWORD *)v157 + 1)
    || !prep
    || !*((_DWORD *)v16 + 33)
    || (EditCursor = CRowset::GotoBookmark(v19, v139, (unsigned int)v142), v179 = EditCursor, EditCursor != 265926) )
  {
    if ( EditCursor >= 0 )
    {
      v21 = tableid;
      v22 = v179;
      goto LABEL_27;
    }
LABEL_400:
    v17 = 0;
    v18 = 0;
    goto LABEL_325;
  }
  v21 = tableid;
  v22 = 0;
  v179 = 0;
LABEL_27:
  if ( a7 == 1 )
  {
    v20 = (*((_BYTE *)v16 + 96) & 0x10) == 0;
    v162 = 1;
    v23 = v20 && !CPendingChange::IsPending(v157);
    v165 = v23;
    if ( CRowset::SetDataEventNotify(
           a6,
           *(enum DBEVENTPHASEENUM *)(v170 + 36),
           *(_DWORD *)(v170 + 32),
           v23,
           v139,
           (int)v142) )
    {
      EditCursor = -2147217842;
LABEL_331:
      v117 = v147;
      *((_DWORD *)v16 + 55) = v149;
      v118 = v150;
      *((_DWORD *)v16 + 57) = v150;
      *((_DWORD *)v16 + 56) = v118;
      *((_DWORD *)v16 + 58) = v145;
      *((_DWORD *)v16 + 59) = v148;
      v167[1] = v117;
      goto LABEL_332;
    }
  }
  if ( CPendingChange::IsPending(v157) )
  {
    v25 = 0;
    if ( !prep )
    {
      v167[1] = 1;
      goto LABEL_53;
    }
    v27 = v167;
  }
  else
  {
    v24 = JetPrepareUpdate(sesid, v21, prep);
    v25 = v24;
    if ( v24 <= -1017 )
    {
      if ( v24 == -1017 )
      {
        EditCursor = -2147217885;
        goto LABEL_384;
      }
      if ( v24 == -1907 || v24 == -1809 )
      {
LABEL_39:
        EditCursor = -2147217911;
LABEL_384:
        v138 = v25;
        v16 = v181;
        CExtError::SendJetErrortoOLEAuto(v138, (int)&IID_IRowset, (int)v139, v142);
        goto LABEL_386;
      }
      goto LABEL_42;
    }
    if ( v24 )
    {
LABEL_42:
      EditCursor = -2147467259;
      v26 = 0;
      goto LABEL_382;
    }
    if ( !prep )
    {
      *(_DWORD *)v157 = -2;
      v167[1] = 1;
      goto LABEL_53;
    }
    v27 = v167;
    *(_DWORD *)v157 = *v167;
    v28 = v181;
    *((_DWORD *)v181 + 57) = a6;
    *((_DWORD *)v28 + 56) = a6;
    ++v27[2];
  }
  v29 = v27[1];
  if ( (v29 & 4) != 0 )
  {
    EditCursor = -2147217885;
    v26 = 0;
    goto LABEL_382;
  }
  if ( (v29 & 1) == 0 )
    v27[1] = 2;
LABEL_53:
  v156 = 0;
  v30 = *(_DWORD *)(v170 + 36);
  v31 = v30 == 0;
  v161 = v31;
  if ( v30 )
  {
    v161 = 0;
    v160 = 13;
    while ( 1 )
    {
      v183 = 0;
      cbData = 0;
      v174 = 0;
      v32 = v21;
      v180 = 0;
      v33 = 0;
      v176 = 0;
      v34 = 16;
      v158 = 0;
      v169 = 0;
      v164 = 0;
      v182 = 0;
      pvBookmark = v25;
      pvData = 0;
      if ( *((_DWORD *)v181 + 17) != 1 )
        v34 = 0;
      grbit = v34;
      v35 = (_DWORD *)(52 * v156 + 40 + v170);
      v178 = v35;
      v36 = v35[7];
      if ( (v36 & 1) != 0 )
      {
        v176 = (char *)v154 + v35[1];
        v36 = v35[7];
      }
      if ( (v36 & 2) != 0 )
      {
        v33 = (char *)v154 + v35[2];
        pvData = v33;
      }
      if ( (v36 & 4) != 0 )
      {
        v37 = v35[3];
        v20 = (CRowset *)((char *)v154 + v37) == 0;
        v38 = (int *)((char *)v154 + v37);
        v180 = v38;
        if ( !v20 )
          v183 = *v38;
      }
      v39 = *v35;
      if ( !v39
        || (v40 = 104 * v39,
            v41 = *(_DWORD *)(*((_DWORD *)v181 + 37) + 12) - 104,
            v20 = v40 + v41 == 0,
            v42 = v40 + v41,
            v173 = v42,
            v20) )
      {
        v183 = 10;
        goto LABEL_302;
      }
      v43 = *(_DWORD *)(v42 + 32);
      v44 = *(unsigned __int16 *)(v42 + 40);
      columnid = v43;
      tableid = v32;
      v172 = 0;
      if ( (_WORD)v44 == 131 )
        v44 = 14;
      v155 = v44;
      if ( v176 )
      {
        v45 = 0;
      }
      else
      {
        v172 = 0;
        if ( v180 )
        {
          v20 = *v180 == 3;
          v172 = 0;
          if ( !v20 )
          {
            v183 = 8;
            v172 = 1;
          }
        }
        if ( !v33 || v180 )
        {
          v45 = v172;
        }
        else
        {
          v45 = 1;
          v183 = 8;
          v172 = 1;
        }
      }
      if ( *(_DWORD *)v157 != -1 || *((_DWORD *)v157 + 1) )
      {
        v47 = v173;
        v45 = v172;
        if ( *(_DWORD *)v157 == *v167 )
        {
          v46 = tableid;
          v45 = v172;
          if ( columnid == *((_DWORD *)v181 + 58) )
          {
            v21 = tableid;
            v183 = 8;
LABEL_303:
            v48 = v180;
            goto LABEL_304;
          }
        }
        else
        {
          v46 = tableid;
        }
      }
      else
      {
        v46 = v32;
        v47 = v173;
        tableid = v46;
      }
      v48 = v180;
      if ( !v45 )
        break;
      v21 = tableid;
LABEL_304:
      switch ( v183 )
      {
        case 0:
        case 3:
        case 4:
        case 13:
        case 15:
          v161 = 1;
          break;
        default:
          v153 = 1;
          break;
      }
      if ( v48 )
        *v48 = v183;
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( (unsigned int)++v156 >= *(_DWORD *)(v170 + 36) )
      {
        v22 = v179;
        v31 = v161;
        goto LABEL_313;
      }
    }
    if ( v180 )
    {
      switch ( *v180 )
      {
        case 0:
        case 3:
          goto LABEL_89;
        case 13:
        case 15:
          break;
        default:
          v183 = 12;
          break;
      }
      v21 = tableid;
      goto LABEL_304;
    }
LABEL_89:
    v21 = v46;
    v49 = v47;
    v175 = v47;
    v50 = *((_WORD *)v178 + 24);
    if ( (_WORD)v160 == v50 )
    {
      v51 = v178[5];
      v169 = 1;
      if ( v51 )
      {
        v52 = (_DWORD *)(v51 + 4);
        v53 = &IID_ISequentialStream;
        v54 = 12;
        while ( v53->Data1 == *v52 )
        {
          v53 = (GUID *)((char *)v53 + 4);
          ++v52;
          v55 = v54 < 4;
          v54 -= 4;
          if ( v55 )
            goto LABEL_94;
        }
      }
      else
      {
LABEL_94:
        v164 = 1;
      }
      v49 = v175;
    }
    else
    {
      v56 = v158;
      if ( v50 != (_WORD)v155 )
        v56 = 1;
      v158 = v56;
    }
    if ( v180 && *v180 == 3 )
    {
      v20 = *(_DWORD *)(v49 + 36) == 1;
      v182 = 1;
      v173 = v49;
      tableid = v21;
      if ( v20 )
      {
        v183 = 10;
        tableid = v21;
        goto LABEL_303;
      }
      v57 = 0;
      v58 = v178;
      v59 = v178 + 12;
      v174 = 0;
      v155 = (unsigned __int16)v155;
LABEL_138:
      if ( v57 > v58[10] && *v59 != 8 )
      {
        if ( *v59 != 13 || (v70 = *(_DWORD *)(v173 + 36), v70 != 11) && v70 != 12 )
          v183 = 2;
      }
      if ( v158 != 1 || v182 )
      {
        v84 = v176;
        cbData = v57;
        goto LABEL_167;
      }
      v71 = (*(int (__thiscall **)(_DWORD, LPVOID, _DWORD, int, int *, unsigned int *, const char *))(*(_DWORD *)g_pIDataConvert + 20))(
              *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 20),
              g_pIDataConvert,
              (unsigned __int16)*v59,
              v155,
              &v174,
              &cbData,
              v176);
      v72 = v181;
      v73 = v71 < 0;
      v74 = v172;
      if ( v73 )
        v74 = 1;
      v172 = v74;
      if ( *((_DWORD *)v181 + 36) <= cbData )
      {
        v75 = ((cbData + 1) & 0xFFFFFFC0) + 64;
        *((_DWORD *)v181 + 36) = v75;
        v76 = (*(int (__thiscall **)(_DWORD, int, _DWORD, unsigned int))(*(_DWORD *)Sys + 16))(
                *(_DWORD *)(*(_DWORD *)Sys + 16),
                Sys,
                *((_DWORD *)v72 + 35),
                v75);
        v77 = v181;
        *((_DWORD *)v181 + 35) = v76;
        if ( !v76 )
        {
          *((_DWORD *)v77 + 36) = 0;
          v183 = 2;
        }
      }
      v78 = 131;
      v175 = *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 12);
      v79 = *(_WORD *)(v173 + 40);
      if ( v79 == 131 )
      {
        LOBYTE(v78) = *(_BYTE *)(v173 + 49);
        v80 = *(_BYTE *)(v173 + 48);
      }
      else
      {
        LOBYTE(v78) = -1;
        v81 = 0;
        while ( word_10004700[2 * v81] != v79 )
        {
          if ( (unsigned int)++v81 >= 8 )
          {
            v80 = -1;
            goto LABEL_158;
          }
        }
        v80 = byte_10004702[4 * v81];
      }
LABEL_158:
      LOBYTE(v159) = v80;
      v82 = (unsigned __int16)*v59;
      v83 = v155;
      if ( ((int (__thiscall *)(int, LPVOID, int, int, int, unsigned int *, const char *, _DWORD, unsigned int, int, int *, _DWORD *, int, _DWORD))v175)(
             v175,
             g_pIDataConvert,
             v82,
             v155,
             v174,
             &cbData,
             v176,
             *((_DWORD *)v181 + 35),
             cbData,
             v183,
             &v183,
             v159,
             v78,
             0) >= 0 )
      {
        if ( v83 == 130 && !v174 && !v183 )
          grbit |= 0x20u;
      }
      else
      {
        v183 = 2;
      }
      v179 = 0;
      v84 = (const char *)*((_DWORD *)v181 + 35);
      if ( v172 )
        goto LABEL_302;
      v57 = cbData;
LABEL_167:
      v85 = tableid;
      v86 = tableid;
      v175 = v182;
      pvData = (void *)tableid;
      if ( (_WORD)v155 == 11 && !v182 && v183 != 2 && v84 )
      {
        v57 = 1;
        cbData = 1;
      }
      if ( v169 == 1 )
      {
        if ( !v164 )
        {
          memset(v186, 0, sizeof(v186));
          v87 = 0;
          pvData = 0;
          grbit = 0;
          v169 = 0;
          v151 = 0;
          if ( v182 == 1 )
            goto LABEL_215;
          if ( !v182 )
          {
            if ( *(_DWORD *)v176 )
              goto LABEL_177;
LABEL_215:
            v25 = JetSetColumn(sesid, tableid, columnid, 0, 0, v182 != 1 ? 0x20 : 0, 0);
            if ( v25 < 0 )
              v183 = 7;
LABEL_217:
            v87 = grbit;
            goto LABEL_218;
          }
          if ( !v176 )
          {
            v183 = 7;
            goto LABEL_219;
          }
LABEL_177:
          v88 = JetOpenILockBytes(sesid, tableid, columnid, &grbit, 0);
          v87 = grbit;
          v25 = v88;
          v89 = v88;
          if ( !grbit || v88 )
          {
            v97 = v175;
            v183 = 7;
            v186[3] = 0;
            v186[2] = 0;
            tableid = v86;
            goto LABEL_220;
          }
          v179 = (***(int (__thiscall ****)(_DWORD, _DWORD, GUID *, int *))v176)(
                   ***(_DWORD ***)v176,
                   *(_DWORD *)v176,
                   &IID_ILockBytes,
                   &v169);
          if ( v179 < 0 || !v169 )
          {
            v87 = grbit;
            v183 = 7;
            if ( grbit )
            {
              if ( !(*(int (__thiscall **)(_DWORD, JET_GRBIT))(*(_DWORD *)grbit + 8))(
                      *(_DWORD *)(*(_DWORD *)grbit + 8),
                      grbit) )
              {
                v87 = 0;
                v25 = v89;
                grbit = 0;
                goto LABEL_218;
              }
              v87 = grbit;
            }
            v25 = v89;
            goto LABEL_218;
          }
          v90 = tableid;
          v164 = v182;
          v91 = *(_DWORD *)v169;
          v175 = 0;
          v92 = (*(int (__thiscall **)(_DWORD, int, _DWORD *, int))(v91 + 36))(*(_DWORD *)(v91 + 36), v169, v186, 1);
          v87 = grbit;
          v179 = v92;
          if ( v92 < 0 )
          {
            v183 = 7;
            if ( grbit )
            {
              if ( (*(int (__thiscall **)(_DWORD, JET_GRBIT))(*(_DWORD *)grbit + 8))(
                     *(_DWORD *)(*(_DWORD *)grbit + 8),
                     grbit) )
              {
                goto LABEL_217;
              }
              v87 = 0;
              grbit = 0;
            }
LABEL_218:
            v186[2] = 0;
            v186[3] = 0;
LABEL_219:
            v97 = v182;
LABEL_220:
            if ( v87
              && !(*(int (__thiscall **)(_DWORD, JET_GRBIT))(*(_DWORD *)v87 + 8))(*(_DWORD *)(*(_DWORD *)v87 + 8), v87) )
            {
              grbit = 0;
            }
            v98 = v176;
            if ( v176 && !v97 )
            {
              if ( v169 )
              {
                (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v169 + 8))(*(_DWORD *)(*(_DWORD *)v169 + 8), v169);
                v98 = v176;
              }
              if ( *(_DWORD *)v98 )
                (*(void (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)v98 + 8))(
                  *(_DWORD *)(**(_DWORD **)v98 + 8),
                  *(_DWORD *)v98);
            }
LABEL_302:
            v21 = tableid;
            goto LABEL_303;
          }
          v25 = v175;
          v182 = v164;
          v93 = *(_DWORD *)grbit;
          tableid = v90;
          v94 = (*(int (__thiscall **)(_DWORD, JET_GRBIT, _DWORD, _DWORD))(v93 + 24))(
                  *(_DWORD *)(v93 + 24),
                  grbit,
                  v186[2],
                  v186[3]);
          v179 = v94;
          if ( v94 < 0 )
          {
            v87 = grbit;
            v183 = 6;
            if ( grbit )
            {
              if ( !(*(int (__thiscall **)(_DWORD, JET_GRBIT))(*(_DWORD *)grbit + 8))(
                      *(_DWORD *)(*(_DWORD *)grbit + 8),
                      grbit) )
              {
                v87 = 0;
                grbit = 0;
                v182 = v164;
                tableid = v90;
                goto LABEL_218;
              }
              v87 = grbit;
            }
            v25 = v175;
            v182 = v164;
            tableid = v90;
            goto LABEL_218;
          }
          v186[3] = 0;
          v186[2] = 0;
          if ( v180 )
          {
            v20 = *v180 == 3;
            v179 = v94;
            if ( v20 )
            {
              v87 = grbit;
              goto LABEL_219;
            }
          }
          v95 = 0;
          pvBookmark = v25;
          while ( 1 )
          {
            if ( (*(int (__thiscall **)(_DWORD, int, int, _DWORD, _BYTE *, int, void **))(*(_DWORD *)v169 + 12))(
                   *(_DWORD *)(*(_DWORD *)v169 + 12),
                   v169,
                   v95,
                   0,
                   v187,
                   4096,
                   &pvData) >= 0 )
              goto LABEL_201;
            v96 = grbit;
            if ( !grbit )
              goto LABEL_202;
            if ( (*(int (__thiscall **)(_DWORD, JET_GRBIT))(*(_DWORD *)grbit + 8))(
                   *(_DWORD *)(*(_DWORD *)grbit + 8),
                   grbit) )
            {
LABEL_201:
              v96 = grbit;
            }
            else
            {
              v96 = 0;
              grbit = 0;
            }
LABEL_202:
            v179 = (*(int (__thiscall **)(_DWORD, JET_GRBIT, int, _DWORD, _BYTE *, void *, unsigned int *))(*(_DWORD *)v96 + 16))(
                     *(_DWORD *)(*(_DWORD *)v96 + 16),
                     v96,
                     v95,
                     0,
                     v187,
                     pvData,
                     &pcbActual);
            if ( v179 >= 0 )
              goto LABEL_206;
            v87 = grbit;
            if ( grbit )
            {
              if ( (*(int (__thiscall **)(_DWORD, JET_GRBIT))(*(_DWORD *)grbit + 8))(
                     *(_DWORD *)(*(_DWORD *)grbit + 8),
                     grbit) )
              {
LABEL_206:
                v87 = grbit;
                goto LABEL_207;
              }
              v87 = 0;
              grbit = 0;
            }
LABEL_207:
            v95 += (int)pvData;
            if ( pvData != (void *)4096 )
            {
              v25 = pvBookmark;
              goto LABEL_219;
            }
          }
        }
        if ( v164 == 1 )
        {
          v99 = v181;
          v178 = 0;
          if ( *((_DWORD *)v181 + 36) <= 0x800u )
          {
            *((_DWORD *)v181 + 36) = 2112;
            v100 = (*(int (__thiscall **)(_DWORD, int, _DWORD, int))(*(_DWORD *)Sys + 16))(
                     *(_DWORD *)(*(_DWORD *)Sys + 16),
                     Sys,
                     *((_DWORD *)v99 + 35),
                     2112);
            *((_DWORD *)v99 + 35) = v100;
            if ( !v100 )
            {
              *((_DWORD *)v99 + 36) = 0;
              v179 = -2147024882;
LABEL_233:
              v21 = tableid;
              v183 = 8;
              goto LABEL_268;
            }
            v85 = (JET_TABLEID)pvData;
          }
          v179 = 0;
          if ( v182 != 1 )
          {
            if ( v182 )
            {
              v101 = v176;
              if ( !v176 )
              {
                v183 = 7;
                goto LABEL_302;
              }
              goto LABEL_239;
            }
            if ( *(_DWORD *)v176 )
            {
              v101 = v176;
LABEL_239:
              v102 = *(_DWORD ***)v101;
              v103 = v182;
              v25 = pvBookmark;
              tableid = v85;
              v104 = ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, _DWORD **))**v102)(
                       **v102,
                       v102,
                       &IID_ISequentialStream,
                       &v178);
              v105 = v178;
              v179 = v104;
              if ( v104 < 0 || !v178 )
              {
                v25 = pvBookmark;
                v111 = v103;
                v21 = (JET_TABLEID)pvData;
                v183 = 7;
                tableid = (JET_TABLEID)pvData;
LABEL_270:
                if ( !v111 )
                {
                  if ( v105 )
                    (*(void (__thiscall **)(_DWORD, _DWORD *))(*v105 + 8))(*(_DWORD *)(*v105 + 8), v105);
                  if ( *(_DWORD *)v176 )
                    (*(void (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)v176 + 8))(
                      *(_DWORD *)(**(_DWORD **)v176 + 8),
                      *(_DWORD *)v176);
                }
                goto LABEL_303;
              }
              v106 = 0;
              v175 = 1;
              v107 = (void *)*((_DWORD *)v181 + 35);
              for ( pvData = v107; ; v107 = pvData )
              {
                v108 = (*(int (__thiscall **)(_DWORD, _DWORD *, void *, int, unsigned int *))(*v105 + 12))(
                         *(_DWORD *)(*v105 + 12),
                         v105,
                         v107,
                         2048,
                         &cbData);
                v109 = cbData;
                v179 = v108;
                if ( v108 < 0 && !cbData )
                  goto LABEL_233;
                v179 = 0;
                if ( v175 == 1 )
                  break;
                if ( v175 || cbData )
                  goto LABEL_251;
LABEL_262:
                v105 = v178;
                v106 = 1;
                v175 = 0;
                if ( v109 != 2048 )
                {
                  v21 = tableid;
                  goto LABEL_269;
                }
              }
              if ( !cbData )
                v106 |= 0x20u;
LABEL_251:
              v110 = JetSetColumn(sesid, tableid, columnid, pvData, cbData, v106, 0);
              v25 = v110;
              if ( v110 > -1048 )
              {
                if ( v110 == -1047 )
                {
                  v183 = 11;
                  goto LABEL_261;
                }
                if ( !v110 )
                {
LABEL_261:
                  v109 = cbData;
                  goto LABEL_262;
                }
              }
              else if ( v110 == -1048 || v110 == -1907 || v110 == -1809 || v110 == -1504 )
              {
                v183 = 9;
                goto LABEL_261;
              }
              v183 = 8;
              goto LABEL_261;
            }
          }
          v21 = tableid;
          v25 = JetSetColumn(sesid, tableid, columnid, 0, 0, v182 != 1 ? 0x20 : 0, 0);
          if ( v25 < 0 )
            v183 = 7;
LABEL_268:
          v105 = v178;
LABEL_269:
          v111 = v182;
          goto LABEL_270;
        }
      }
      v21 = tableid;
      if ( v183 == 2 )
        goto LABEL_303;
      v112 = JetSetColumn(sesid, tableid, columnid, v84, v57, grbit, 0);
      v25 = v112;
      if ( v112 > -1530 )
      {
        if ( v112 > -1048 )
        {
          if ( v112 == -1047 )
          {
LABEL_283:
            v183 = 11;
LABEL_284:
            CExtError::SendJetErrortoOLEAuto(v112, (int)&IID_IRowset, (int)v139, v142);
            v25 = 0;
            goto LABEL_303;
          }
          if ( v112 >= 0 )
            goto LABEL_303;
LABEL_299:
          v183 = 8;
          goto LABEL_284;
        }
        if ( v112 == -1048 )
        {
LABEL_296:
          v183 = 9;
          goto LABEL_284;
        }
        if ( v112 != -1529 )
        {
          if ( v112 != -1504 && v112 != -1053 )
            goto LABEL_299;
          goto LABEL_294;
        }
      }
      else if ( v112 != -1530 )
      {
        if ( v112 <= -1907 )
        {
          if ( v112 != -1907 )
          {
            if ( v112 == -3703 || v112 == -3702 || v112 == -3701 )
              goto LABEL_283;
            goto LABEL_299;
          }
          goto LABEL_296;
        }
        if ( v112 == -1809 )
          goto LABEL_296;
        if ( v112 != -1605 )
        {
          if ( v112 == -1531 )
          {
            v183 = 2;
            goto LABEL_284;
          }
          goto LABEL_299;
        }
LABEL_294:
        v183 = 10;
        goto LABEL_284;
      }
      v183 = 6;
      goto LABEL_284;
    }
    v60 = (unsigned __int16 *)(v178 + 12);
    v61 = v178[12] & 0x8FFF;
    if ( v61 == 128 )
    {
      v62 = (unsigned int *)pvData;
      if ( !pvData )
        v62 = v178 + 10;
      v57 = *v62;
      v174 = v57;
      goto LABEL_136;
    }
    if ( v61 != 129 && v61 != 130 )
    {
      if ( v61 != 8 )
      {
        v58 = v178;
        if ( v61 == 131 )
        {
          v57 = 19;
          v174 = 19;
          v59 = v178 + 12;
        }
        else
        {
          v59 = v178 + 12;
          v57 = *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v181 + 37) + 12) + 104 * *v178 - 60);
          v174 = v57;
        }
        goto LABEL_138;
      }
      v63 = (char *)v176;
      v57 = 4;
      v174 = 4;
      if ( !*(_DWORD *)v176 )
      {
        v64 = SysAllocString(&word_100046A0);
        *(_DWORD *)v63 = v64;
        v57 = v174;
        bstrString = v64;
      }
      goto LABEL_136;
    }
    if ( pvData )
    {
      v57 = *(_DWORD *)pvData;
LABEL_133:
      v174 = v57;
      goto LABEL_134;
    }
    v57 = 0;
    v174 = 0;
    if ( v176 )
    {
      v65 = *v60;
      if ( v65 > 0x4081 )
      {
        if ( v65 != 16514 )
          goto LABEL_134;
        v67 = *(_WORD **)v176;
        if ( !*(_DWORD *)v176 )
          goto LABEL_134;
        v68 = v67 + 1;
        while ( *v67++ )
          ;
        v57 = 2 * (v67 - v68);
        goto LABEL_133;
      }
      if ( v65 == 16513 )
      {
        if ( *(_DWORD *)v176 )
        {
          v57 = strlen(*(const char **)v176);
          goto LABEL_133;
        }
      }
      else
      {
        v66 = v65 - 129;
        if ( !v66 )
        {
          v57 = strlen(v176);
          goto LABEL_133;
        }
        if ( v66 == 1 )
        {
          v57 = 2 * wcslen((const unsigned __int16 *)v176);
          goto LABEL_133;
        }
      }
    }
LABEL_134:
    v59 = v178 + 12;
    if ( v57 )
    {
LABEL_137:
      v58 = v178;
      goto LABEL_138;
    }
    grbit = 32;
LABEL_136:
    v59 = v60;
    goto LABEL_137;
  }
LABEL_313:
  v113 = v181;
  if ( (*((_BYTE *)v181 + 96) & 0x10) == 0 || !v31 )
  {
    v135 = v167;
    goto LABEL_378;
  }
  pvBookmark = *v167;
  v114 = JetUpdate(sesid, v21, &pvBookmark, 4u, &pcbActual);
  v25 = v114;
  if ( v114 <= -1053 )
  {
    if ( v114 != -1053 )
    {
      if ( v114 <= -1907 )
      {
        if ( v114 == -1907 )
          goto LABEL_39;
        if ( v114 == -3703 || v114 == -3702 || v114 == -3701 )
        {
          EditCursor = -2147217917;
LABEL_323:
          v16 = v181;
          CExtError::SendJetErrortoOLEAuto(v114, (int)&IID_IRowset, (int)v139, v142);
          JetPrepareUpdate(sesid, tableid, 3u);
LABEL_324:
          v17 = v165;
          v18 = v162;
LABEL_325:
          v14 = v170;
          goto LABEL_326;
        }
LABEL_346:
        EditCursor = -2147467259;
        goto LABEL_323;
      }
      if ( v114 == -1809 )
        goto LABEL_39;
      if ( v114 != -1605 )
      {
        if ( v114 == -1312 )
        {
          EditCursor = -2147217915;
          goto LABEL_384;
        }
        goto LABEL_346;
      }
    }
    EditCursor = -2147217873;
    goto LABEL_323;
  }
  if ( v114 > 1624 )
  {
    if ( v114 != 1625 && v114 != 1626 )
    {
LABEL_349:
      v25 = 0;
LABEL_350:
      if ( v22 < 0 )
        goto LABEL_355;
      goto LABEL_353;
    }
  }
  else if ( v114 != 1624 )
  {
    if ( !v114 )
      goto LABEL_350;
    if ( v114 != 1614 && v114 != 1617 )
    {
      if ( v114 < 0 )
        goto LABEL_346;
      goto LABEL_349;
    }
  }
  v179 = 265948;
LABEL_353:
  if ( !prep )
    *v167 = pvBookmark;
LABEL_355:
  v120 = v181;
  v121 = 0;
  v122 = *((_DWORD *)v181 + 56);
  v123 = *((_DWORD *)v181 + 4);
  *((_DWORD *)v181 + 55) = -1;
  *((_DWORD *)v120 + 57) = 0;
  *((_DWORD *)v120 + 56) = 0;
  *((_DWORD *)v120 + 58) = -1;
  *((_DWORD *)v120 + 59) = 1;
  v156 = 0;
  v124 = *(_DWORD *)(v123 + 8);
  v175 = v122;
  columnid = v123;
  if ( !*(_DWORD *)(v124 + 52) )
    goto LABEL_358;
  v121 = (CRowset *)operator new(4u);
  if ( v121 )
  {
    v123 = columnid;
LABEL_358:
    _mm_lfence();
    v159 = *(_DWORD **)(v123 + 8);
    v125 = v159[26];
    v126 = *(_DWORD *)(v125 + 24);
    v127 = *(_DWORD *)(v125 + 20);
    v160 = v126;
    if ( v122 <= v126 + 8 * v127 - 1 )
    {
      v128 = (v122 - v160) & 7;
      v129 = (v122 - v160) >> 3;
      v130 = v175;
      if ( (*(_BYTE *)(v129 + *(_DWORD *)(v159[26] + 16)) & *((_BYTE *)&Bitmap::ThisBit + v128)) == 0 )
      {
        v131 = (_DWORD *)(*(_DWORD *)(v159[26] + 8) + v175 * *(_DWORD *)v159[26]);
        if ( v131 )
        {
          if ( *v131 != -1 )
          {
            if ( v175 == v159[56] && v131[2] == 1 )
              v131[2] = 2;
            v20 = v131[2]-- == 1;
            if ( v20 )
            {
              if ( v121 )
              {
                *(_DWORD *)v121 = v130;
                v156 = 1;
              }
              v132 = *(_DWORD *)(columnid + 8);
              if ( *(_DWORD *)(v132 + 228) == v130 )
              {
                v133 = *(_DWORD **)(v132 + 216);
                v159 = v133;
                if ( v133 )
                {
                  v134 = v133[3];
                  v133[1] = 1;
                  *(_DWORD *)(v134 + 216) = 0;
                  (*(void (__thiscall **)(_DWORD *))(*v133 + 4))(v159);
                  v159[3] = 0;
                }
              }
              CExtBuffer::DeleteFromExtBuffer((CExtBuffer *)v139, (unsigned int)v142);
              *(_DWORD *)(*(_DWORD *)(columnid + 8) + 136) = 0;
            }
          }
        }
      }
    }
    if ( v121 )
    {
      if ( v156 )
        CRowset::RowNotify(v121, 5u, (const unsigned int *const)4, (enum DBREASONENUM)v139, (enum DBEVENTPHASEENUM)v142);
      operator delete(v121);
    }
  }
  v135 = v167;
  v113 = v181;
  v167[1] = 8;
LABEL_378:
  v26 = v161;
  EditCursor = v179;
  if ( (*((_BYTE *)v113 + 96) & 0x10) == 0 && v161 == 1 && !prep )
    *v135 = *((_DWORD *)v113 + 55);
LABEL_382:
  if ( v25 )
  {
    v161 = v26;
    goto LABEL_384;
  }
LABEL_385:
  v16 = v181;
LABEL_386:
  if ( EditCursor )
  {
    v18 = v162;
    v17 = v165;
    if ( EditCursor < 0 )
      goto LABEL_325;
  }
  else
  {
    if ( v153 )
    {
      if ( !v161 )
      {
        JetPrepareUpdate(sesid, tableid, 3u);
        *((_DWORD *)v16 + 57) = 0;
        *((_DWORD *)v16 + 56) = 0;
        EditCursor = -2147217887;
        *((_DWORD *)v16 + 55) = -1;
        *((_DWORD *)v16 + 58) = -1;
        *((_DWORD *)v16 + 59) = 1;
        goto LABEL_324;
      }
      EditCursor = 265946;
    }
    v18 = v162;
    v17 = v165;
  }
  if ( a7 == 1 && v18 == 1 )
  {
    v20 = *((_DWORD *)v16 + 13) == 0;
    v136 = *(_DWORD *)(v170 + 32);
    v137 = *(CRowset **)(v170 + 36);
    v160 = (int)a6;
    if ( !v20 )
    {
      CRowset::ColumnNotify(
        v137,
        v136,
        (unsigned int)v137,
        (const unsigned int *const)4,
        (enum DBREASONENUM)v139,
        (enum DBEVENTPHASEENUM)v142);
      if ( v17 )
        CRowset::RowNotify((CRowset *)&v160, 7u, (const unsigned int *const)4, v141, v144);
    }
  }
LABEL_332:
  if ( bstrString )
    SysFreeString(bstrString);
  return EditCursor;
}

```

## disassembly

```asm
0x10029a90  mov     edi, edi
0x10029a92  push    ebp
0x10029a93  mov     ebp, esp
0x10029a95  mov     eax, 10F0h
0x10029a9a  call    __chkstk
0x10029a9f  mov     eax, ___security_cookie
0x10029aa4  xor     eax, ebp
0x10029aa6  mov     [ebp+var_4], eax
0x10029aa9  push    ebx
0x10029aaa  push    esi; enum DBEVENTPHASEENUM
0x10029aab  push    edi; enum DBREASONENUM
0x10029aac  mov     edi, edx
0x10029aae  mov     [ebp+var_1060], ecx
0x10029ab4  mov     eax, [ebp+this]
0x10029ab7  mov     [ebp+var_10CC], eax
0x10029abd  mov     eax, [ecx+38h]
0x10029ac0  mov     ebx, [ecx+0DCh]
0x10029ac6  mov     eax, [eax+10h]
0x10029ac9  mov     esi, [ecx+64h]
0x10029acc  mov     [ebp+sesid], eax
0x10029ad2  lea     eax, [ecx+0DCh]
0x10029ad8  mov     [ebp+var_10C0], eax
0x10029ade  mov     [ebp+var_10E0], ebx
0x10029ae4  mov     ebx, [eax+4]
0x10029ae7  mov     edx, [ebp+arg_4]
0x10029aea  mov     [ebp+var_10DC], ebx
0x10029af0  mov     ebx, [eax+0Ch]
0x10029af3  mov     eax, [eax+10h]
0x10029af6  mov     [ebp+var_10E4], eax
0x10029afc  mov     eax, [edx+4]
0x10029aff  mov     [ebp+var_10E8], eax
0x10029b05  xor     eax, eax
0x10029b07  mov     [ebp+var_10AC], eax
0x10029b0d  mov     [ebp+var_10A0], eax
0x10029b13  mov     [ebp+bstrString], eax
0x10029b19  mov     eax, [esi+14h]
0x10029b1c  mov     ecx, [esi+18h]
0x10029b1f  mov     [ebp+var_1098], edx
0x10029b25  lea     eax, ds:0FFFFFFFFh[eax*8]
0x10029b2c  mov     [ebp+tableid], 0
0x10029b36  add     eax, ecx
0x10029b38  mov     [ebp+var_1090], 0
0x10029b42  mov     [ebp+var_10F0], ebx
0x10029b48  mov     [ebp+var_10D0], 0
0x10029b52  mov     [ebp+var_10B0], 0
0x10029b5c  cmp     edi, eax
0x10029b5e  ja      loc_1002B510
0x10029b64  mov     eax, [esi+10h]
0x10029b67  mov     edx, edi
0x10029b69  sub     edx, ecx
0x10029b6b  mov     ecx, edx
0x10029b6d  and     edx, 7
0x10029b70  shr     ecx, 3
0x10029b73  mov     al, [ecx+eax]
0x10029b76  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x10029b7c  jnz     loc_1002B510
0x10029b82  mov     eax, [esi]
0x10029b84  push    eax; Size
0x10029b85  imul    eax, edi
0x10029b88  add     eax, [esi+8]
0x10029b8b  push    eax; Src
0x10029b8c  lea     eax, [ebp+var_1090]
0x10029b92  push    eax; void *
0x10029b93  call    _memcpy
0x10029b98  mov     ecx, [ebp+var_1090]
0x10029b9e  xor     ebx, ebx
0x10029ba0  add     esp, 0Ch
0x10029ba3  mov     [ebp+var_108C], ecx
0x10029ba9  cmp     [ebp+var_10CC], ebx
0x10029baf  jnz     short loc_10029BCE
0x10029bb1  test    ecx, ecx
0x10029bb3  jz      short loc_10029BBA
0x10029bb5  cmp     [ecx+24h], ebx
0x10029bb8  jz      short loc_10029BD3
0x10029bba  mov     edi, [ebp+var_1060]
0x10029bc0  xor     esi, esi
0x10029bc2  mov     ebx, 80070057h
0x10029bc7  xor     edx, edx
0x10029bc9  jmp     loc_1002B046
0x10029bce  cmp     [ecx+24h], ebx
0x10029bd1  jnz     short loc_10029BDC
0x10029bd3  cmp     [ebp+prep], ebx
0x10029bd6  jnz     loc_1002B3E6
0x10029bdc  cmp     [ecx+8], ebx
0x10029bdf  jz      loc_1002B4FC
0x10029be5  mov     esi, [ebp+var_10C0]
0x10029beb  mov     eax, [esi]
0x10029bed  cmp     eax, 0FFFFFFFFh
0x10029bf0  jnz     short loc_10029C0C
0x10029bf2  cmp     [ebp+var_10DC], ebx
0x10029bf8  jz      short loc_10029C23
0x10029bfa  mov     ecx, [ebp+var_1060]
0x10029c00  cmp     [ecx+0E0h], ebx
0x10029c06  jz      loc_1002B4E8
0x10029c0c  mov     ecx, [ebp+var_1098]
0x10029c12  cmp     eax, [ecx]
0x10029c14  jnz     loc_1002B4E8
0x10029c1a  cmp     [ebp+prep], ebx
0x10029c1d  jz      loc_1002B4E8
0x10029c23  mov     edi, [ebp+var_1060]
0x10029c29  xor     ebx, ebx
0x10029c2b  mov     [ebp+var_1068], ebx
0x10029c31  test    byte ptr [edi+60h], 10h
0x10029c35  jz      short loc_10029C3C
0x10029c37  mov     eax, [edi+6Ch]
0x10029c3a  jmp     short loc_10029C56
0x10029c3c  mov     ecx, edi; this
0x10029c3e  call    ?GetEditCursor@CRowset@@IAEJXZ; CRowset::GetEditCursor(void)
0x10029c43  mov     ebx, eax
0x10029c45  mov     [ebp+var_1068], ebx
0x10029c4b  test    ebx, ebx
0x10029c4d  js      loc_1002B4F3
0x10029c53  mov     eax, [edi+70h]
0x10029c56  cmp     dword ptr [esi], 0FFFFFFFFh
0x10029c59  mov     [ebp+tableid], eax
0x10029c5f  jnz     short loc_10029CA4
0x10029c61  cmp     dword ptr [esi+4], 0
0x10029c65  jnz     short loc_10029CA4
0x10029c67  cmp     [ebp+prep], 0
0x10029c6b  jz      short loc_10029CA4
0x10029c6d  cmp     dword ptr [edi+84h], 0
0x10029c74  jz      short loc_10029CA4
0x10029c76  mov     edx, [ebp+var_1098]
0x10029c7c  mov     ecx, edi
0x10029c7e  push    eax; tableid
0x10029c7f  call    ?GotoBookmark@CRowset@@IAGJPAKK@Z; CRowset::GotoBookmark(ulong *,ulong)
0x10029c84  mov     ebx, eax
0x10029c86  mov     [ebp+var_1068], ebx
0x10029c8c  cmp     ebx, 40EC6h
0x10029c92  jnz     short loc_10029CA4
0x10029c94  mov     ebx, [ebp+tableid]
0x10029c9a  xor     esi, esi
0x10029c9c  mov     [ebp+var_1068], esi
0x10029ca2  jmp     short loc_10029CBE
0x10029ca4  test    ebx, ebx
0x10029ca6  js      loc_1002B4F3
0x10029cac  mov     ebx, [ebp+tableid]
0x10029cb2  mov     esi, [ebp+var_1068]
0x10029cb8  mov     [ebp+tableid], ebx
0x10029cbe  cmp     [ebp+arg_10], 1
0x10029cc2  jnz     short loc_10029D19
0x10029cc4  test    byte ptr [edi+60h], 10h
0x10029cc8  mov     [ebp+var_10AC], 1
0x10029cd2  jnz     short loc_10029CEA
0x10029cd4  mov     ecx, [ebp+var_10C0]; this
0x10029cda  call    ?IsPending@CPendingChange@@QBEHXZ; CPendingChange::IsPending(void)
0x10029cdf  test    eax, eax
0x10029ce1  jnz     short loc_10029CEA
0x10029ce3  mov     eax, 1
0x10029ce8  jmp     short loc_10029CEC
0x10029cea  xor     eax, eax
0x10029cec  push    eax; unsigned int
0x10029ced  mov     [ebp+var_10A0], eax
0x10029cf3  xor     edx, edx
0x10029cf5  mov     eax, [ebp+var_108C]
0x10029cfb  mov     ecx, edi
0x10029cfd  push    dword ptr [eax+20h]; unsigned int
0x10029d00  push    dword ptr [eax+24h]; enum DBEVENTPHASEENUM
0x10029d03  push    [ebp+arg_C]; this
0x10029d06  call    ?SetDataEventNotify@CRowset@@QAGJW4DBEVENTPHASEENUM@@KKQAKH@Z; CRowset::SetDataEventNotify(DBEVENTPHASEENUM,ulong,ulong,ulong * const,int)
0x10029d0b  test    eax, eax
0x10029d0d  jz      short loc_10029D19
0x10029d0f  mov     ebx, 80040E4Eh
0x10029d14  jmp     loc_1002B08D
0x10029d19  mov     ecx, [ebp+var_10C0]; this
0x10029d1f  call    ?IsPending@CPendingChange@@QBEHXZ; CPendingChange::IsPending(void)
0x10029d24  test    eax, eax
0x10029d26  jnz     loc_10029DC7
0x10029d2c  push    [ebp+prep]; prep
0x10029d2f  push    ebx; tableid
0x10029d30  push    [ebp+sesid]; sesid
0x10029d36  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x10029d3c  mov     edi, eax
0x10029d3e  cmp     edi, 0FFFFFC07h
0x10029d44  jg      short loc_10029D6C
0x10029d46  jz      short loc_10029D62
0x10029d48  cmp     edi, 0FFFFF88Dh
0x10029d4e  jz      short loc_10029D58
0x10029d50  cmp     edi, 0FFFFF8EFh
0x10029d56  jnz     short loc_10029D70
0x10029d58  mov     ebx, 80040E09h
0x10029d5d  jmp     loc_1002B3CB
0x10029d62  mov     ebx, 80040E23h
0x10029d67  jmp     loc_1002B3CB
0x10029d6c  test    edi, edi
0x10029d6e  jz      short loc_10029D7C
0x10029d70  mov     ebx, 80004005h
0x10029d75  xor     ecx, ecx
0x10029d77  jmp     loc_1002B39D
0x10029d7c  cmp     [ebp+prep], 0
0x10029d80  jnz     short loc_10029D9D
0x10029d82  mov     eax, [ebp+var_10C0]
0x10029d88  mov     dword ptr [eax], 0FFFFFFFEh
0x10029d8e  mov     eax, [ebp+var_1098]
0x10029d94  mov     dword ptr [eax+4], 1
0x10029d9b  jmp     short loc_10029E01
0x10029d9d  mov     edx, [ebp+var_1098]
0x10029da3  mov     ecx, [ebp+var_10C0]
0x10029da9  mov     eax, [edx]
0x10029dab  mov     [ecx], eax
0x10029dad  mov     eax, [ebp+var_1060]
0x10029db3  mov     ecx, [ebp+arg_C]
0x10029db6  mov     [eax+0E4h], ecx
0x10029dbc  mov     [eax+0E0h], ecx
0x10029dc2  inc     dword ptr [edx+8]
0x10029dc5  jmp     short loc_10029DE3
0x10029dc7  xor     edi, edi
0x10029dc9  cmp     [ebp+prep], edi
0x10029dcc  jnz     short loc_10029DDD
0x10029dce  mov     eax, [ebp+var_1098]
0x10029dd4  mov     dword ptr [eax+4], 1
0x10029ddb  jmp     short loc_10029E01
0x10029ddd  mov     edx, [ebp+var_1098]
0x10029de3  mov     eax, [edx+4]
0x10029de6  test    al, 4
0x10029de8  jz      short loc_10029DF6
0x10029dea  mov     ebx, 80040E23h
0x10029def  xor     ecx, ecx
0x10029df1  jmp     loc_1002B39D
0x10029df6  test    al, 1
0x10029df8  jnz     short loc_10029E01
0x10029dfa  mov     dword ptr [edx+4], 2
0x10029e01  mov     eax, [ebp+var_108C]
0x10029e07  xor     ecx, ecx
0x10029e09  mov     [ebp+var_10C4], 0
0x10029e13  mov     eax, [eax+24h]
0x10029e16  test    eax, eax
0x10029e18  setz    cl
0x10029e1b  mov     [ebp+var_10B0], ecx
0x10029e21  test    eax, eax
0x10029e23  jz      loc_1002AF7C
0x10029e29  mov     [ebp+var_10B0], ecx
0x10029e2f  mov     [ebp+var_10B4], 0Dh
0x10029e39  nop     dword ptr [eax+00000000h]
0x10029e40  xor     ecx, ecx
0x10029e42  mov     [ebp+var_1058], 0
0x10029e4c  mov     [ebp+cbData], ecx
0x10029e52  xor     edx, edx
0x10029e54  mov     [ebp+var_107C], ecx
0x10029e5a  mov     esi, ebx
0x10029e5c  mov     [ebp+var_1064], ecx
0x10029e62  xor     ebx, ebx
0x10029e64  mov     [ebp+var_1074], ecx
0x10029e6a  mov     eax, 10h
0x10029e6f  mov     [ebp+var_10BC], ecx
0x10029e75  mov     [ebp+var_1090], ecx
0x10029e7b  mov     [ebp+var_10A4], ecx
0x10029e81  mov     [ebp+var_105C], ecx
0x10029e87  mov     ecx, [ebp+var_1060]
0x10029e8d  mov     [ebp+pvBookmark], edi
0x10029e93  mov     [ebp+pvData], ebx
0x10029e99  cmp     dword ptr [ecx+44h], 1
0x10029e9d  mov     ecx, edx
0x10029e9f  cmovnz  eax, ecx
0x10029ea2  mov     ecx, [ebp+var_108C]
0x10029ea8  mov     [ebp+grbit], eax
0x10029eae  imul    eax, [ebp+var_10C4], 34h ; '4'
0x10029eb5  add     eax, 28h ; '('
0x10029eb8  add     ecx, eax
0x10029eba  mov     [ebp+var_106C], ecx
0x10029ec0  mov     eax, [ecx+1Ch]
0x10029ec3  test    al, 1
0x10029ec5  jz      short loc_10029ED9
0x10029ec7  mov     eax, [ecx+4]
0x10029eca  add     eax, [ebp+var_10CC]
0x10029ed0  mov     [ebp+var_1074], eax
0x10029ed6  mov     eax, [ecx+1Ch]
0x10029ed9  test    al, 2
0x10029edb  jz      short loc_10029EEC
0x10029edd  mov     ebx, [ecx+8]
0x10029ee0  add     ebx, [ebp+var_10CC]
0x10029ee6  mov     [ebp+pvData], ebx
0x10029eec  test    al, 4
0x10029eee  jz      short loc_10029F09
0x10029ef0  mov     eax, [ecx+0Ch]
0x10029ef3  add     eax, [ebp+var_10CC]
0x10029ef9  mov     [ebp+var_1064], eax
0x10029eff  jz      short loc_10029F09
0x10029f01  mov     eax, [eax]
0x10029f03  mov     [ebp+var_1058], eax
0x10029f09  mov     ecx, [ecx]
0x10029f0b  test    ecx, ecx
0x10029f0d  jz      loc_1002AEE8
0x10029f13  mov     eax, [ebp+var_1060]
0x10029f19  imul    ecx, 68h ; 'h'
0x10029f1c  mov     eax, [eax+94h]
0x10029f22  mov     eax, [eax+0Ch]
0x10029f25  add     eax, 0FFFFFF98h
0x10029f28  add     eax, ecx
0x10029f2a  mov     [ebp+var_1080], eax
0x10029f30  jz      loc_1002AEE8
0x10029f36  mov     ecx, [eax+20h]
0x10029f39  movzx   eax, word ptr [eax+28h]
0x10029f3d  mov     [ebp+columnid], ecx
0x10029f43  mov     ecx, 83h
0x10029f48  cmp     cx, ax
0x10029f4b  mov     [ebp+tableid], esi
0x10029f51  mov     ecx, 0Eh
0x10029f56  mov     [ebp+var_1084], edx
0x10029f5c  cmovz   eax, ecx
  ... truncated ...
```
