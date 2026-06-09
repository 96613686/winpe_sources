# CRowset::UtilGetData(ulong,void const *,tagOreoHROW *,ushort,ulong,int &)

- ea: `0x1002b570`
- end: `0x1002c62f`
- name: `?UtilGetData@CRowset@@IAGJKPBXPAUtagOreoHROW@@GKAAH@Z`
- size: `4287`
- prototype: `int(CRowset *__hidden this, unsigned int, const void *, struct tagOreoHROW *, unsigned __int16, unsigned int, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10030340`
- `0x10032ff0`

## callees

- `0x1001bdc0`
- `0x1001c6d0`
- `0x1002b570`
- `0x1002c700`
- `0x1002d9b0`
- `0x1004ce5d`
- `0x1004dc81`

## import_xrefs

- `msjet40!__imp__JetPrepareUpdate@12` at `0x1002bc5e`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1002c027`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1002bc5e`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1002c027`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002b9fb`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002bb41`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002be9a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002c1d6`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002c45f`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002b9fb`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002bb41`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002be9a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002c1d6`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002c45f`
- `msjet40!__imp__JetOpenILockBytes@20` at `0x1002bd47`
- `msjet40!__imp__JetOpenILockBytes@20` at `0x1002bd47`

## pseudocode

```c
int __userpurge CRowset::UtilGetData@<eax>(
        unsigned int a1@<edx>,
        CRowset *a2@<ecx>,
        CRowset *this,
        _DWORD *pvData,
        const void *a5,
        struct tagOreoHROW *a6,
        _DWORD *a7,
        unsigned int a8,
        int *a9)
{
  JET_ERR EditCursor; // edi
  CRowset *v10; // ebx
  int v11; // eax
  size_t *v12; // esi
  size_t v13; // ecx
  int result; // eax
  int v15; // ecx
  int v16; // eax
  int v17; // edx
  JET_TABLEID v18; // ecx
  JET_GRBIT v19; // ecx
  _DWORD *v20; // edx
  unsigned int v21; // ecx
  int v22; // eax
  int *v23; // edi
  int v24; // ecx
  int v25; // esi
  int v26; // ecx
  int v27; // eax
  int v28; // eax
  int v29; // edx
  unsigned int v30; // ecx
  int v31; // ecx
  unsigned int v32; // edx
  __int16 v33; // ax
  _DWORD *v34; // ecx
  unsigned __int16 v35; // di
  _DWORD *v36; // ecx
  int v37; // esi
  JET_COLUMNID v38; // eax
  int v39; // esi
  int *v40; // edi
  unsigned __int16 v41; // ax
  unsigned __int16 *v42; // ecx
  int *v43; // edx
  int v44; // edi
  _DWORD *v45; // edi
  GUID *v46; // ecx
  _DWORD *v47; // esi
  unsigned int v48; // ebx
  bool v49; // cf
  GUID *v50; // ecx
  unsigned int v51; // esi
  int v52; // ecx
  __int16 v53; // dx
  unsigned int v54; // eax
  int v55; // eax
  _DWORD *v56; // esi
  JET_ERR v57; // eax
  int v58; // edx
  int v59; // esi
  _DWORD *v60; // eax
  JET_TABLEID v61; // ecx
  JET_COLUMNID v62; // eax
  JET_TABLEID v63; // edx
  JET_ERR v64; // eax
  _DWORD *v65; // ebx
  int v66; // edx
  CRowset *v67; // eax
  int v68; // esi
  _DWORD *v69; // ecx
  int v70; // edx
  JET_TABLEID v71; // ecx
  int v72; // esi
  JET_TABLEID v73; // ecx
  _DWORD *v74; // eax
  JET_TABLEID v75; // edx
  _DWORD *v76; // edx
  _DWORD *v77; // eax
  BOOL v78; // eax
  JET_COLUMNID v79; // esi
  JET_SESID v80; // esi
  JET_GRBIT v81; // ebx
  int v82; // eax
  int v83; // eax
  _DWORD *v84; // eax
  int v85; // eax
  JET_ERR v86; // eax
  _WORD *v87; // edx
  int v88; // eax
  JET_TABLEID v89; // ecx
  JET_GRBIT v90; // edx
  unsigned int v91; // ecx
  unsigned int v92; // eax
  JET_ERR v93; // eax
  bool v94; // zf
  int v95; // edx
  int v96; // eax
  unsigned int *v97; // [esp+0h] [ebp-CCh]
  const struct _GUID *v98; // [esp+4h] [ebp-C8h]
  unsigned int v99; // [esp+Ch] [ebp-C0h] BYREF
  int v100; // [esp+10h] [ebp-BCh]
  int v101; // [esp+14h] [ebp-B8h]
  int v102; // [esp+18h] [ebp-B4h] BYREF
  int v103; // [esp+1Ch] [ebp-B0h]
  int v104; // [esp+20h] [ebp-ACh]
  int *v105; // [esp+24h] [ebp-A8h]
  unsigned int *v106; // [esp+28h] [ebp-A4h]
  int v107; // [esp+2Ch] [ebp-A0h]
  JET_TABLEID v108; // [esp+30h] [ebp-9Ch]
  int v109; // [esp+34h] [ebp-98h]
  unsigned __int16 *v110; // [esp+38h] [ebp-94h]
  JET_GRBIT v111; // [esp+3Ch] [ebp-90h]
  int v112; // [esp+40h] [ebp-8Ch]
  unsigned __int16 *v113; // [esp+44h] [ebp-88h]
  int v114; // [esp+48h] [ebp-84h]
  BOOL v115; // [esp+4Ch] [ebp-80h]
  int v116; // [esp+50h] [ebp-7Ch]
  _DWORD *v117; // [esp+54h] [ebp-78h]
  int v118; // [esp+58h] [ebp-74h]
  _DWORD *v119; // [esp+5Ch] [ebp-70h] BYREF
  BOOL v120; // [esp+60h] [ebp-6Ch]
  int v121; // [esp+64h] [ebp-68h]
  unsigned int v122; // [esp+68h] [ebp-64h]
  int v123; // [esp+6Ch] [ebp-60h]
  JET_GRBIT v124; // [esp+70h] [ebp-5Ch]
  int v125; // [esp+74h] [ebp-58h]
  JET_TABLEID v126; // [esp+78h] [ebp-54h]
  int v127; // [esp+7Ch] [ebp-50h] BYREF
  unsigned int pcbActual; // [esp+80h] [ebp-4Ch] BYREF
  int v129; // [esp+84h] [ebp-48h]
  CRowset *v130; // [esp+88h] [ebp-44h]
  JET_SESID sesid; // [esp+8Ch] [ebp-40h]
  _WORD *v132; // [esp+90h] [ebp-3Ch] BYREF
  _DWORD *v133; // [esp+94h] [ebp-38h]
  int *v134; // [esp+98h] [ebp-34h]
  unsigned int v135; // [esp+9Ch] [ebp-30h] BYREF
  int v136; // [esp+A0h] [ebp-2Ch]
  _DWORD *v137; // [esp+A4h] [ebp-28h]
  int v138; // [esp+A8h] [ebp-24h]
  unsigned __int16 *v139; // [esp+ACh] [ebp-20h]
  int v140; // [esp+B0h] [ebp-1Ch]
  JET_TABLEID tableid; // [esp+B4h] [ebp-18h]
  BOOL v142; // [esp+B8h] [ebp-14h]
  JET_COLUMNID v143; // [esp+BCh] [ebp-10h]
  JET_GRBIT grbit; // [esp+C0h] [ebp-Ch]
  int v145; // [esp+C4h] [ebp-8h]
  int v146; // [esp+C8h] [ebp-4h] BYREF

  v122 = a1;
  EditCursor = 0;
  v10 = a2;
  v130 = a2;
  v119 = 0;
  grbit = (_WORD)a5 != 1;
  v11 = *((_DWORD *)a2 + 14);
  v109 = 0;
  v104 = 0;
  sesid = *(_DWORD *)(v11 + 16);
  *a7 = 0;
  v12 = (size_t *)*((_DWORD *)a2 + 25);
  v13 = v12[6];
  if ( a1 > v13 + 8 * v12[5] - 1 )
    return -2147217920;
  if ( (*(_BYTE *)(((a1 - v13) >> 3) + v12[4]) & *((_BYTE *)&Bitmap::ThisBit + ((a1 - v13) & 7))) != 0 )
    return -2147217920;
  memcpy(&v119, (const void *)(v12[2] + v122 * *v12), *v12);
  if ( !v119 )
    return -2147217920;
  if ( !this && v119[9] )
    return -2147024809;
  v15 = pvData[1];
  if ( v15 == 16 )
    return -2147217885;
  if ( !*v119 || (unsigned int)(*v119 - 3) > 1 )
    return -2147217891;
  v16 = (int)(*((_DWORD *)v10 + 43) << 30) >> 31;
  v101 = (int)(*((_DWORD *)v10 + 43) << 31) >> 31;
  v17 = *((_DWORD *)v10 + 33);
  v100 = v16;
  result = 0;
  if ( v17 == 1 )
  {
    if ( *((_DWORD *)v10 + 55) == *pvData )
    {
      result = 0;
      if ( (v15 & 4) == 0 )
      {
        v18 = *((_DWORD *)v10 + 28);
        goto LABEL_21;
      }
    }
    else
    {
      result = 0;
    }
  }
  v19 = grbit;
  if ( (_WORD)a5 != 1 )
    v19 = 0;
  grbit = v19;
  if ( v17 )
  {
    result = CRowset::GotoBookmark(0xFFFFFFFF, v97, (unsigned int)v98);
    if ( result < 0 )
      return result;
  }
  v18 = *((_DWORD *)v10 + 27);
LABEL_21:
  v20 = v119;
  tableid = v18;
  v21 = 0;
  v138 = result;
  v122 = 0;
  if ( v119[9] )
  {
    v103 = 131;
    v107 = 136;
    while ( 1 )
    {
      v22 = 13 * v21;
      v146 = 0;
      v23 = 0;
      v135 = 0;
      v102 = 1;
      v24 = v20[13 * v21 + 10];
      v25 = (int)&v20[v22 + 10];
      v106 = 0;
      v105 = 0;
      v134 = 0;
      v143 = 1;
      v140 = v25;
      if ( v24 )
      {
        v26 = 104 * v24;
        v27 = *(_DWORD *)(*((_DWORD *)v10 + 37) + 12) - 104;
        v94 = v26 + v27 == 0;
        v28 = v26 + v27;
        v29 = v28;
        v145 = v28;
        if ( !v94 )
        {
          v30 = *(_DWORD *)(v28 + 44);
          v145 = v28;
          goto LABEL_28;
        }
      }
      else
      {
        v29 = 0;
        v28 = 0;
        v145 = 0;
      }
      v30 = 4;
LABEL_28:
      v135 = v30;
      v31 = *(_DWORD *)(v25 + 28);
      if ( (v31 & 1) != 0 )
      {
        v23 = (int *)((char *)this + *(_DWORD *)(v25 + 4));
        v134 = v23;
      }
      if ( (v31 & 2) != 0 )
      {
        v106 = (unsigned int *)((char *)this + *(_DWORD *)(v25 + 8));
        v10 = v130;
      }
      if ( (v31 & 4) != 0 )
        v105 = (int *)((char *)this + *(_DWORD *)(v25 + 12));
      if ( v23 )
      {
        v127 = 0;
        v32 = 0;
        v123 = 0;
        v125 = 0;
        pcbActual = 0;
        if ( !*(_DWORD *)v25 )
        {
          v127 = 1;
          v137 = (_DWORD *)(v28 + 36);
          v32 = 4;
          v139 = (unsigned __int16 *)(v25 + 48);
          v33 = *(_WORD *)(v25 + 48);
          pcbActual = 4;
          if ( v33 == 128 || v33 == 19 )
          {
            v143 = (JET_COLUMNID)v23;
            EditCursor = 0;
            v136 = 3;
            v34 = (_DWORD *)v143;
            v142 = 0;
          }
          else
          {
            EditCursor = 0;
            v136 = 3;
            v34 = pvData;
            v142 = 1;
            v143 = (JET_COLUMNID)pvData;
          }
          goto LABEL_83;
        }
        v35 = *(_WORD *)(v145 + 40);
        v36 = (_DWORD *)(v145 + 36);
        v37 = v35;
        switch ( *(_DWORD *)(v145 + 36) )
        {
          case 9:
          case 0xA:
          case 0xB:
          case 0xC:
            v38 = 0;
            v143 = 0;
            break;
          default:
            v38 = v143;
            break;
        }
        if ( (_WORD)v103 != v35 )
        {
          v143 = v38;
          v139 = (unsigned __int16 *)(v140 + 48);
          v41 = *(_WORD *)(v140 + 48);
          if ( (_WORD)v107 != v35 )
          {
            v137 = (_DWORD *)(v145 + 36);
            v136 = v35;
            v40 = (int *)(v145 + 36);
            v42 = v139;
            v39 = v140;
            v127 = 0;
            goto LABEL_52;
          }
          v43 = &v102;
          if ( v41 == 136 )
            v43 = v134;
          EditCursor = 0;
          v143 = (JET_COLUMNID)v43;
          v142 = (_WORD)v107 != v41;
          if ( (_WORD)v107 == v41 )
            *v43 = 1;
          v137 = v36;
          v136 = v37;
          goto LABEL_126;
        }
        v39 = v140;
        v40 = (int *)(v145 + 36);
        v41 = *(_WORD *)(v140 + 48);
        v42 = (unsigned __int16 *)(v140 + 48);
        v136 = 14;
        v137 = (_DWORD *)(v145 + 36);
LABEL_52:
        v139 = v42;
        if ( v41 == 13 )
        {
          v44 = *(_DWORD *)(v39 + 20);
          v123 = 1;
          if ( v44 )
          {
            v45 = (_DWORD *)(v44 + 4);
            v46 = &IID_ISequentialStream;
            v47 = v45;
            v48 = 12;
            while ( v46->Data1 == *v47 )
            {
              v46 = (GUID *)((char *)v46 + 4);
              ++v47;
              v49 = v48 < 4;
              v48 -= 4;
              if ( v49 )
              {
                v34 = v134;
                EditCursor = 0;
                v125 = 1;
                v142 = 0;
                goto LABEL_82;
              }
            }
            v50 = &IID_IUnknown;
            v51 = 12;
            while ( v50->Data1 == *v45 )
            {
              v50 = (GUID *)((char *)v50 + 4);
              ++v45;
              v49 = v51 < 4;
              v51 -= 4;
              if ( v49 )
                goto LABEL_61;
            }
          }
          else
          {
LABEL_61:
            v125 = 1;
          }
          v34 = v134;
          EditCursor = 0;
          v142 = 0;
        }
        else
        {
          v52 = *v40;
          v53 = word_100510F0[4 * *v40];
          if ( v41 != v53 || v53 == 131 )
          {
            v142 = 1;
            v32 = *(_DWORD *)(v145 + 44);
            if ( !v32 )
              v32 = *(_DWORD *)(v39 + 40);
            pcbActual = v32;
            if ( v52 == 11 || (EditCursor = 0, v52 == 12) )
            {
              EditCursor = JetRetrieveColumn(sesid, tableid, *(_DWORD *)(v145 + 32), 0, 0, &pcbActual, grbit, 0);
              if ( EditCursor == 1006 )
              {
                v32 = pcbActual;
              }
              else
              {
                v32 = 0;
                pcbActual = 0;
              }
            }
            if ( *((_DWORD *)v10 + 36) <= v32 + 2 )
            {
              *((_DWORD *)v10 + 36) = ((v32 + 3) & 0xFFFFFFC0) + 64;
              v55 = (*(int (__thiscall **)(_DWORD, int, _DWORD, unsigned int))(*(_DWORD *)Sys + 16))(
                      *(_DWORD *)(*(_DWORD *)Sys + 16),
                      Sys,
                      *((_DWORD *)v10 + 35),
                      ((v32 + 3) & 0xFFFFFFC0) + 64);
              *((_DWORD *)v10 + 35) = v55;
              if ( !v55 )
              {
                *((_DWORD *)v10 + 36) = 0;
                result = -2147024882;
                goto LABEL_227;
              }
              v32 = pcbActual;
            }
            v34 = (_DWORD *)*((_DWORD *)v10 + 35);
            v138 = 0;
          }
          else
          {
            v142 = 0;
            v32 = *(_DWORD *)(v145 + 44);
            if ( !v143 )
            {
              v54 = *(_DWORD *)(v39 + 40);
              if ( v32 && v32 < v54 )
                v54 = *(_DWORD *)(v145 + 44);
              v32 = v54;
            }
            v34 = v134;
            EditCursor = 0;
            pcbActual = v32;
          }
        }
LABEL_82:
        v143 = (JET_COLUMNID)v34;
LABEL_83:
        v118 = (unsigned __int16)v136;
        v108 = tableid;
        v111 = grbit;
        v117 = v137;
        v116 = (unsigned __int16)v136;
        v120 = v142;
        v126 = tableid;
        v124 = grbit;
        v110 = v139;
        v113 = v139;
        v114 = (unsigned __int16)v136;
        v112 = v145;
        v121 = v145;
        v56 = v137;
        v129 = v138;
        v10 = v130;
        v133 = v34;
        v115 = v142;
        v132 = v34;
        if ( v127 == 1 )
        {
          if ( !v142 )
            *v34 = *pvData;
          if ( *pvData == -2 )
          {
            v146 = 8;
LABEL_127:
            if ( v142 )
            {
              if ( v145 )
                v70 = (unsigned __int16)word_100510F0[4 * *v137];
              else
                v70 = (unsigned __int16)v136;
              if ( (_WORD)v70 == 131 )
                v70 = 14;
              (*(void (__thiscall **)(_DWORD, LPVOID, int, _DWORD, unsigned int, unsigned int *, JET_COLUMNID, int *, _DWORD, int, int *, _DWORD, _DWORD, _DWORD))(*(_DWORD *)g_pIDataConvert + 12))(
                *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 12),
                g_pIDataConvert,
                v70,
                *v139,
                v135,
                &v99,
                v143,
                v134,
                *(_DWORD *)(v140 + 40),
                v146,
                &v146,
                *(unsigned __int8 *)(v140 + 50),
                *(unsigned __int8 *)(v140 + 51),
                0);
              v92 = v99;
LABEL_213:
              v135 = v92;
              goto LABEL_214;
            }
            goto LABEL_215;
          }
LABEL_126:
          if ( v146 == 3 )
            goto LABEL_215;
          goto LABEL_127;
        }
        if ( v123 != 1 )
          goto LABEL_166;
        if ( !v125 )
        {
          v133 = *(_DWORD **)(v145 + 32);
          v57 = JetRetrieveColumn(sesid, tableid, (JET_COLUMNID)v133, 0, 0, &v135, grbit, 0);
          v58 = v140;
          EditCursor = v57;
          if ( v57 == 1004 && !**(_DWORD **)(v140 + 20) )
          {
            v146 = 3;
            v135 = 0;
            goto LABEL_215;
          }
          v59 = 0;
          v123 = *((_DWORD *)v10 + 55);
          v126 = *((_DWORD *)v10 + 56);
          v124 = *((_DWORD *)v10 + 58);
          v121 = *((_DWORD *)v10 + 59);
          v60 = *(_DWORD **)(v140 + 20);
          v127 = 0;
          v132 = (_WORD *)(3 - (*v60 != 0));
          if ( !*((_DWORD *)v10 + 59) || !v101 )
          {
            v59 = 1;
            v146 = 7;
            v109 = 1;
          }
          if ( *pvData != -2 && *pvData != -3 && !v59 && *((_DWORD *)v10 + 29) )
          {
            EditCursor = CRowset::GetEditCursor(v10);
            v138 = CRowset::GotoBookmark(*((_DWORD *)v10 + 28), v97, (unsigned int)v98);
            if ( v138 < 0 || EditCursor )
            {
              v146 = 7;
              v59 = 1;
            }
            v58 = v140;
          }
          v94 = *((_DWORD *)v10 + 55) == -1;
          v61 = *((_DWORD *)v10 + (*((_DWORD *)v10 + 29) != 0) + 27);
          v125 = v61;
          if ( !v94 || *((_DWORD *)v10 + 56) )
          {
            v62 = (JET_COLUMNID)v133;
          }
          else if ( !**(_DWORD **)(v58 + 20) || v59 )
          {
            v62 = (JET_COLUMNID)v133;
            *((_DWORD *)v10 + 57) = a6;
            v136 = (unsigned __int16)v118;
            v63 = tableid;
            *((_DWORD *)v10 + 59) = 0;
            *((_DWORD *)v10 + 58) = v62;
            tableid = v63;
          }
          else
          {
            EditCursor = JetPrepareUpdate(sesid, v61, 2u);
            if ( EditCursor )
            {
              v62 = (JET_COLUMNID)v133;
              v59 = 1;
              v146 = 7;
            }
            else
            {
              *((_DWORD *)v10 + 55) = *pvData;
              *((_DWORD *)v10 + 57) = a6;
              *((_DWORD *)v10 + 56) = a6;
              v62 = (JET_COLUMNID)v133;
              *((_DWORD *)v10 + 59) = 0;
              *((_DWORD *)v10 + 58) = v62;
              ++pvData[2];
            }
            v136 = (unsigned __int16)v118;
            v61 = v125;
          }
          if ( !v59 )
          {
            v64 = JetOpenILockBytes(sesid, v61, v62, &v127, v132);
            EditCursor = v64;
            if ( v127 && !v64 )
            {
              v65 = operator new(0x20u);
              v132 = v65;
              if ( v65 )
              {
                v66 = v127;
                v67 = v130;
                v68 = **(_DWORD **)(v140 + 20);
                v65[4] = v130;
                v65[2] = 0;
                v65[3] = 1;
                *((_DWORD *)v67 + 54) = v65 + 1;
                v65[6] = v125;
                *v65 = &LongBinaryILockBytes::`vftable'{for `ILockBytes'};
                v65[5] = v66;
                v65[1] = &LongBinaryILockBytes::`vftable'{for `CStorageObject'};
                v65[7] = v68 == 0;
                *v134 = (int)v65;
              }
              else
              {
                *v134 = 0;
              }
              v10 = v130;
              if ( **(_DWORD **)(v140 + 20) == 2 )
              {
                v69 = pvData;
LABEL_125:
                ++v69[2];
              }
              goto LABEL_126;
            }
            v146 = 7;
          }
          *((_DWORD *)v10 + 55) = v123;
          v71 = v126;
          *((_DWORD *)v10 + 57) = v126;
          *((_DWORD *)v10 + 56) = v71;
          *((_DWORD *)v10 + 58) = v124;
          v134 = 0;
          *((_DWORD *)v10 + 59) = v121;
          goto LABEL_126;
        }
        if ( v125 != 1 )
        {
LABEL_166:
          v86 = JetRetrieveColumn(sesid, tableid, *(_DWORD *)(v145 + 32), v34, v32, &v135, grbit, 0);
          EditCursor = v86;
          if ( v86 > -1017 )
          {
            if ( v86 )
            {
              if ( v86 == 1004 )
              {
                v146 = 3;
              }
              else if ( v86 == 1006 )
              {
                v146 = 4;
              }
              else if ( v86 < 0 )
              {
                goto LABEL_179;
              }
            }
          }
          else
          {
            if ( v86 == -1017 )
            {
              v138 = -2147217885;
              goto LABEL_229;
            }
            if ( v86 > -1603 )
            {
              if ( v86 != -1038 )
                goto LABEL_179;
              v146 = 6;
            }
            else if ( v86 == -1603 )
            {
              v146 = 8;
              *((_DWORD *)v10 + 55) = -1;
              *((_DWORD *)v10 + 57) = 0;
              *((_DWORD *)v10 + 56) = 0;
              *((_DWORD *)v10 + 58) = -1;
              *((_DWORD *)v10 + 59) = 1;
            }
            else
            {
              if ( v86 == -1809 )
              {
                v146 = 9;
                goto LABEL_182;
              }
LABEL_179:
              v146 = 8;
            }
          }
LABEL_182:
          switch ( v146 )
          {
            case 0:
            case 3:
            case 4:
            case 13:
              v87 = v132;
              if ( *v56 == 1 )
              {
                v135 = 2;
                *v132 = -(*(_BYTE *)v132 != 0);
              }
              v88 = *v56;
              if ( *v56 == 10 )
              {
                v89 = v126;
              }
              else
              {
                v138 = v129;
                v142 = v115;
                v136 = (unsigned __int16)v114;
                v139 = v113;
                v145 = v121;
                grbit = v124;
                v89 = v126;
                v143 = (JET_COLUMNID)v87;
                v137 = v56;
                tableid = v126;
                if ( v88 != 12 )
                  goto LABEL_126;
              }
              v136 = (unsigned __int16)v114;
              v139 = v113;
              v145 = v121;
              v138 = v129;
              grbit = v124;
              v10 = v130;
              v143 = (JET_COLUMNID)v87;
              v142 = v115;
              v137 = v56;
              tableid = v89;
              if ( v115 )
                goto LABEL_126;
              v143 = (JET_COLUMNID)v87;
              v90 = v124;
              v137 = v56;
              v91 = *(_DWORD *)(v140 + 40) - 2;
              grbit = v124;
              if ( v135 < v91 )
                v91 = v135;
              *((_WORD *)v134 + (v91 >> 1)) = 0;
              v138 = v129;
              v10 = v130;
              v142 = v115;
              v136 = (unsigned __int16)v114;
              v139 = v113;
              v145 = v121;
              tableid = v126;
              if ( (*(_DWORD *)(v140 + 40) & 0xFFFFFFFE) - 2 >= v135 )
                goto LABEL_126;
              v146 = 4;
              v138 = v129;
              grbit = v90;
              tableid = v126;
              break;
            default:
              goto LABEL_126;
          }
          goto LABEL_215;
        }
        v118 = *((_DWORD *)v130 + 55);
        v72 = 0;
        v125 = *((_DWORD *)v130 + 56);
        v123 = *((_DWORD *)v130 + 58);
        v126 = *((_DWORD *)v130 + 59);
        v129 = *(_DWORD *)(v145 + 32);
        EditCursor = JetRetrieveColumn(sesid, tableid, v129, 0, 0, &v135, grbit, 0);
        if ( EditCursor == 1004 && !**(_DWORD **)(v140 + 20) )
        {
          v146 = 3;
          v135 = 0;
          goto LABEL_215;
        }
        if ( !*((_DWORD *)v10 + 59) || !v100 )
        {
          v146 = 7;
          v72 = 1;
        }
        if ( *pvData != -2 && *pvData != -3 && !v72 )
        {
          if ( *((_DWORD *)v10 + 29) )
          {
            EditCursor = CRowset::GetEditCursor(v10);
            v138 = CRowset::GotoBookmark(*((_DWORD *)v10 + 28), v97, (unsigned int)v98);
            if ( v138 < 0 || EditCursor )
            {
              v146 = 7;
              v72 = 1;
            }
          }
        }
        v94 = *((_DWORD *)v10 + 55) == -1;
        v73 = *((_DWORD *)v10 + (*((_DWORD *)v10 + 29) != 0) + 27);
        v132 = (_WORD *)v73;
        if ( v94 && !*((_DWORD *)v10 + 56) )
        {
          v74 = *(_DWORD **)(v140 + 20);
          if ( v74 )
          {
            v94 = *v74 == 0;
            v143 = (JET_COLUMNID)v133;
            v142 = v120;
            v136 = (unsigned __int16)v116;
            v137 = v117;
            v139 = v110;
            v145 = v112;
            grbit = v111;
            v75 = v108;
            tableid = v108;
            if ( v94 )
              goto LABEL_148;
          }
          else
          {
            v75 = v108;
          }
          v143 = (JET_COLUMNID)v133;
          v142 = v120;
          v136 = (unsigned __int16)v116;
          v137 = v117;
          v139 = v110;
          v145 = v112;
          grbit = v111;
          tableid = v75;
          if ( v72 )
          {
LABEL_157:
            v79 = v129;
          }
          else
          {
            EditCursor = JetPrepareUpdate(sesid, v73, 2u);
            v143 = (JET_COLUMNID)v133;
            v142 = v120;
            v136 = (unsigned __int16)v116;
            v137 = v117;
            v139 = v110;
            v145 = v112;
            grbit = v111;
            tableid = v108;
            if ( EditCursor )
            {
              v143 = (JET_COLUMNID)v133;
              v142 = v120;
              v136 = (unsigned __int16)v116;
              v137 = v117;
              v10 = v130;
              v146 = 7;
              v139 = v110;
              v145 = v112;
              grbit = v111;
              tableid = v108;
              goto LABEL_157;
            }
LABEL_149:
            v76 = operator new(0x30u);
            v124 = (JET_GRBIT)v76;
            if ( v76 )
            {
              v77 = *(_DWORD **)(v140 + 20);
              v78 = !v77 || !*v77;
              v80 = sesid;
              v76[4] = v10;
              v76[2] = 0;
              v76[3] = 1;
              *((_DWORD *)v10 + 54) = v76 + 1;
              v81 = grbit;
              v76[11] = v78;
              v82 = v76[4];
              v76[5] = v80;
              v76[6] = v132;
              v79 = v129;
              v76[9] = v81;
              v10 = v130;
              *v76 = &CImpISequentialStream::`vftable'{for `ISequentialStream'};
              v76[1] = &CImpISequentialStream::`vftable'{for `CStorageObject'};
              v76[7] = v79;
              v76[8] = 1;
              v76[10] = 0;
              *(_DWORD *)(v82 + 216) = v76 + 1;
              *v134 = (int)v76;
            }
            else
            {
              v79 = v129;
              *v134 = 0;
              v146 = 7;
            }
          }
          switch ( v146 )
          {
            case 0:
            case 3:
            case 4:
            case 13:
              v83 = v140;
              *((_DWORD *)v10 + 59) = 0;
              *((_DWORD *)v10 + 58) = v79;
              *((_DWORD *)v10 + 57) = a6;
              v84 = *(_DWORD **)(v83 + 20);
              if ( v84 && *v84 )
              {
                v69 = pvData;
                *((_DWORD *)v10 + 55) = *pvData;
                *((_DWORD *)v10 + 56) = a6;
                goto LABEL_125;
              }
              break;
            default:
              *((_DWORD *)v10 + 55) = v118;
              v85 = v125;
              *((_DWORD *)v10 + 57) = v125;
              *((_DWORD *)v10 + 56) = v85;
              *((_DWORD *)v10 + 58) = v123;
              *((_DWORD *)v10 + 59) = v126;
              break;
          }
          goto LABEL_126;
        }
LABEL_148:
        if ( v72 )
          goto LABEL_157;
        goto LABEL_149;
      }
      EditCursor = 0;
      if ( v29 )
      {
        v93 = JetRetrieveColumn(sesid, tableid, *(_DWORD *)(v29 + 32), 0, 0, &v135, grbit, 0);
        EditCursor = v93;
        if ( v93 > 1004 )
        {
          v94 = v93 == 1006;
        }
        else
        {
          if ( v93 == 1004 )
          {
            v146 = 3;
            goto LABEL_215;
          }
          if ( v93 == -1038 )
          {
            EditCursor = 0;
            if ( *(_WORD *)(v25 + 48) == 131 )
              v135 = 19;
            else
              v135 = *(_DWORD *)(v145 + 44);
            goto LABEL_215;
          }
          v94 = v93 == 0;
        }
        if ( v94 )
        {
          v132 = 0;
          v95 = (unsigned __int16)word_100510F0[4 * *(_DWORD *)(v145 + 36)];
          if ( (_WORD)v95 != *(_WORD *)(v25 + 48) )
          {
            v96 = (*(int (__thiscall **)(_DWORD, LPVOID, int, _DWORD, unsigned int *, _WORD **, _DWORD))(*(_DWORD *)g_pIDataConvert + 20))(
                    *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 20),
                    g_pIDataConvert,
                    v95,
                    *(unsigned __int16 *)(v140 + 48),
                    &v135,
                    &v132,
                    0);
            v10 = v130;
            if ( v96 >= 0 )
            {
              v92 = (unsigned int)v132;
              goto LABEL_213;
            }
LABEL_214:
            v138 = 0;
          }
        }
        else
        {
          v146 = 8;
        }
      }
LABEL_215:
      if ( v106 )
        *v106 = v135;
      if ( v105 )
        *v105 = v146;
      switch ( v146 )
      {
        case 0:
        case 3:
        case 4:
        case 13:
          v104 = 1;
          break;
        default:
          v109 = 1;
          if ( EditCursor < 0 )
            CExtError::SendJetErrortoOLEAuto(EditCursor, (int)&IID_IRowset, (int)v97, v98);
          break;
      }
      EditCursor = 0;
      v20 = v119;
      v21 = v122 + 1;
      v122 = v21;
      if ( v21 >= v119[9] )
      {
        result = v138;
        break;
      }
    }
  }
  if ( !result )
  {
    if ( v109 )
    {
      result = 265946;
      if ( !v104 )
        result = -2147217887;
LABEL_227:
      v138 = result;
    }
    if ( EditCursor )
    {
LABEL_229:
      CExtError::SendJetErrortoOLEAuto(EditCursor, (int)&IID_IRowset, (int)v97, v98);
      *a7 = 1;
      return v138;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1002b570  mov     edi, edi
0x1002b572  push    ebp
0x1002b573  mov     ebp, esp
0x1002b575  sub     esp, 0C0h
0x1002b57b  xor     eax, eax
0x1002b57d  mov     [ebp+var_64], edx
0x1002b580  push    ebx
0x1002b581  push    esi; struct _GUID *
0x1002b582  push    edi; int
0x1002b583  xor     edi, edi
0x1002b585  mov     ebx, ecx
0x1002b587  cmp     word ptr [ebp+arg_8], 1
0x1002b58c  mov     [ebp+var_44], ebx
0x1002b58f  setnz   al
0x1002b592  mov     [ebp+var_70], edi
0x1002b595  mov     [ebp+grbit], eax
0x1002b598  mov     eax, [ebx+38h]
0x1002b59b  mov     [ebp+var_98], edi
0x1002b5a1  mov     [ebp+var_AC], edi
0x1002b5a7  mov     eax, [eax+10h]
0x1002b5aa  mov     [ebp+sesid], eax
0x1002b5ad  mov     eax, dword ptr [ebp+arg_10]
0x1002b5b0  mov     [eax], edi
0x1002b5b2  mov     esi, [ebx+64h]
0x1002b5b5  mov     eax, [esi+14h]
0x1002b5b8  mov     ecx, [esi+18h]
0x1002b5bb  lea     eax, ds:0FFFFFFFFh[eax*8]
0x1002b5c2  add     eax, ecx
0x1002b5c4  cmp     edx, eax
0x1002b5c6  ja      loc_1002C621
0x1002b5cc  mov     eax, [esi+10h]
0x1002b5cf  sub     edx, ecx
0x1002b5d1  mov     ecx, edx
0x1002b5d3  and     edx, 7
0x1002b5d6  shr     ecx, 3
0x1002b5d9  mov     al, [ecx+eax]
0x1002b5dc  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1002b5e2  jnz     loc_1002C621
0x1002b5e8  mov     eax, [esi]
0x1002b5ea  push    eax; Size
0x1002b5eb  imul    eax, [ebp+var_64]
0x1002b5ef  add     eax, [esi+8]
0x1002b5f2  push    eax; Src
0x1002b5f3  lea     eax, [ebp+var_70]
0x1002b5f6  push    eax; void *
0x1002b5f7  call    _memcpy
0x1002b5fc  mov     eax, [ebp+var_70]
0x1002b5ff  add     esp, 0Ch
0x1002b602  test    eax, eax
0x1002b604  jz      loc_1002C621
0x1002b60a  cmp     [ebp+this], edi
0x1002b60d  jnz     short loc_1002B622
0x1002b60f  cmp     [eax+24h], edi
0x1002b612  jz      short loc_1002B622
0x1002b614  pop     edi
0x1002b615  pop     esi
0x1002b616  mov     eax, 80070057h
0x1002b61b  pop     ebx
0x1002b61c  mov     esp, ebp
0x1002b61e  pop     ebp
0x1002b61f  retn    14h
0x1002b622  mov     esi, [ebp+pvData]
0x1002b625  mov     ecx, [esi+4]
0x1002b628  cmp     ecx, 10h
0x1002b62b  jnz     short loc_1002B63B
0x1002b62d  pop     edi
0x1002b62e  pop     esi
0x1002b62f  mov     eax, 80040E23h
0x1002b634  pop     ebx
0x1002b635  mov     esp, ebp
0x1002b637  pop     ebp
0x1002b638  retn    14h
0x1002b63b  mov     eax, [eax]
0x1002b63d  sub     eax, 0
0x1002b640  jz      loc_1002C613
0x1002b646  sub     eax, 3
0x1002b649  jz      short loc_1002B654
0x1002b64b  sub     eax, 1
0x1002b64e  jnz     loc_1002C613
0x1002b654  mov     eax, [ebx+0ACh]
0x1002b65a  mov     edx, eax
0x1002b65c  shl     edx, 1Fh
0x1002b65f  shl     eax, 1Eh
0x1002b662  sar     edx, 1Fh
0x1002b665  sar     eax, 1Fh
0x1002b668  mov     [ebp+var_B8], edx
0x1002b66e  mov     edx, [ebx+84h]
0x1002b674  mov     [ebp+var_BC], eax
0x1002b67a  xor     eax, eax
0x1002b67c  cmp     edx, 1
0x1002b67f  jnz     short loc_1002B699
0x1002b681  mov     eax, [ebx+0DCh]
0x1002b687  cmp     eax, [esi]
0x1002b689  jnz     short loc_1002B697
0x1002b68b  xor     eax, eax
0x1002b68d  test    cl, 4
0x1002b690  jnz     short loc_1002B699
0x1002b692  mov     ecx, [ebx+70h]
0x1002b695  jmp     short loc_1002B6C1
0x1002b697  xor     eax, eax
0x1002b699  cmp     word ptr [ebp+arg_8], 1
0x1002b69e  mov     ecx, [ebp+grbit]
0x1002b6a1  cmovnz  ecx, edi
0x1002b6a4  mov     [ebp+grbit], ecx
0x1002b6a7  test    edx, edx
0x1002b6a9  jz      short loc_1002B6BE
0x1002b6ab  push    0FFFFFFFFh; tableid
0x1002b6ad  mov     edx, esi
0x1002b6af  mov     ecx, ebx
0x1002b6b1  call    ?GotoBookmark@CRowset@@IAGJPAKK@Z; CRowset::GotoBookmark(ulong *,ulong)
0x1002b6b6  test    eax, eax
0x1002b6b8  js      loc_1002C626
0x1002b6be  mov     ecx, [ebx+6Ch]
0x1002b6c1  mov     edx, [ebp+var_70]
0x1002b6c4  mov     esi, 80040E21h
0x1002b6c9  mov     [ebp+tableid], ecx
0x1002b6cc  xor     ecx, ecx
0x1002b6ce  mov     [ebp+var_24], eax
0x1002b6d1  mov     [ebp+var_64], ecx
0x1002b6d4  cmp     [edx+24h], ecx
0x1002b6d7  jbe     loc_1002C57B
0x1002b6dd  mov     [ebp+var_B0], 83h
0x1002b6e7  mov     [ebp+var_A0], 88h
0x1002b6f1  imul    eax, ecx, 34h ; '4'
0x1002b6f4  lea     esi, [edx+28h]
0x1002b6f7  mov     [ebp+var_4], 0
0x1002b6fe  xor     edi, edi
0x1002b700  mov     [ebp+var_30], 0
0x1002b707  mov     [ebp+var_B4], 1
0x1002b711  mov     ecx, [esi+eax]
0x1002b714  add     esi, eax
0x1002b716  mov     [ebp+var_A4], 0
0x1002b720  mov     [ebp+var_A8], 0
0x1002b72a  mov     [ebp+var_34], edi
0x1002b72d  mov     [ebp+var_10], 1
0x1002b734  mov     [ebp+var_1C], esi
0x1002b737  test    ecx, ecx
0x1002b739  jz      short loc_1002B75B
0x1002b73b  mov     eax, [ebx+94h]
0x1002b741  imul    ecx, 68h ; 'h'
0x1002b744  mov     eax, [eax+0Ch]
0x1002b747  add     eax, 0FFFFFF98h
0x1002b74a  add     eax, ecx
0x1002b74c  mov     edx, eax
0x1002b74e  mov     [ebp+var_8], edx
0x1002b751  jz      short loc_1002B762
0x1002b753  mov     ecx, [eax+2Ch]
0x1002b756  mov     [ebp+var_8], edx
0x1002b759  jmp     short loc_1002B767
0x1002b75b  xor     edx, edx
0x1002b75d  xor     eax, eax
0x1002b75f  mov     [ebp+var_8], edx
0x1002b762  mov     ecx, 4
0x1002b767  mov     [ebp+var_30], ecx
0x1002b76a  mov     ecx, [esi+1Ch]
0x1002b76d  test    cl, 1
0x1002b770  jz      short loc_1002B77B
0x1002b772  mov     edi, [esi+4]
0x1002b775  add     edi, [ebp+this]
0x1002b778  mov     [ebp+var_34], edi
0x1002b77b  test    cl, 2
0x1002b77e  jz      short loc_1002B78F
0x1002b780  mov     ebx, [esi+8]
0x1002b783  add     ebx, [ebp+this]
0x1002b786  mov     [ebp+var_A4], ebx
0x1002b78c  mov     ebx, [ebp+var_44]
0x1002b78f  test    cl, 4
0x1002b792  jz      short loc_1002B7A0
0x1002b794  mov     ecx, [esi+0Ch]
0x1002b797  add     ecx, [ebp+this]
0x1002b79a  mov     [ebp+var_A8], ecx
0x1002b7a0  test    edi, edi
0x1002b7a2  jz      loc_1002C442
0x1002b7a8  xor     ecx, ecx
0x1002b7aa  mov     [ebp+var_50], 0
0x1002b7b1  xor     edx, edx
0x1002b7b3  mov     [ebp+var_60], 0
0x1002b7ba  mov     [ebp+var_58], ecx
0x1002b7bd  mov     [ebp+pcbActual], edx
0x1002b7c0  cmp     [esi], ecx
0x1002b7c2  jnz     short loc_1002B829
0x1002b7c4  add     eax, 24h ; '$'
0x1002b7c7  mov     [ebp+var_50], 1
0x1002b7ce  mov     [ebp+var_28], eax
0x1002b7d1  lea     ecx, [edx+3]
0x1002b7d4  lea     eax, [esi+30h]
0x1002b7d7  mov     edx, 4
0x1002b7dc  mov     [ebp+var_20], eax
0x1002b7df  mov     esi, 80h
0x1002b7e4  movzx   eax, word ptr [eax]
0x1002b7e7  mov     [ebp+pcbActual], edx
0x1002b7ea  cmp     si, ax
0x1002b7ed  jz      short loc_1002B812
0x1002b7ef  mov     esi, 13h
0x1002b7f4  cmp     si, ax
0x1002b7f7  jz      short loc_1002B812
0x1002b7f9  mov     eax, [ebp+pvData]
0x1002b7fc  xor     edi, edi
0x1002b7fe  mov     [ebp+var_2C], ecx
0x1002b801  mov     ecx, eax
0x1002b803  mov     [ebp+var_14], 1
0x1002b80a  mov     [ebp+var_10], eax
0x1002b80d  jmp     loc_1002BA6B
0x1002b812  mov     [ebp+var_10], edi
0x1002b815  xor     edi, edi
0x1002b817  mov     [ebp+var_2C], ecx
0x1002b81a  mov     ecx, [ebp+var_10]
0x1002b81d  mov     [ebp+var_14], 0
0x1002b824  jmp     loc_1002BA6B
0x1002b829  mov     eax, [ebp+var_8]
0x1002b82c  movzx   edi, word ptr [eax+28h]
0x1002b830  lea     ecx, [eax+24h]
0x1002b833  mov     eax, [ecx]
0x1002b835  mov     esi, edi
0x1002b837  add     eax, 0FFFFFFF7h; switch 4 cases
0x1002b83a  cmp     eax, 3
0x1002b83d  ja      short def_1002B83F; jumptable 1002B83F default case
0x1002b83f  jmp     ds:jpt_1002B83F[eax*4]; switch jump
0x1002b846  xor     eax, eax; jumptable 1002B83F cases 9-12
0x1002b848  mov     [ebp+var_10], eax
0x1002b84b  jmp     short loc_1002B850
0x1002b84d  mov     eax, [ebp+var_10]; jumptable 1002B83F default case
0x1002b850  cmp     word ptr [ebp+var_B0], di
0x1002b857  jnz     short loc_1002B874
0x1002b859  mov     esi, [ebp+var_1C]
0x1002b85c  mov     edi, ecx
0x1002b85e  movzx   eax, word ptr [esi+30h]
0x1002b862  lea     ecx, [esi+30h]
0x1002b865  mov     [ebp+var_2C], 0Eh
0x1002b86c  mov     [ebp+var_28], edi
0x1002b86f  jmp     loc_1002B8FD
0x1002b874  mov     edi, [ebp+var_1C]
0x1002b877  add     edi, 30h ; '0'
0x1002b87a  mov     [ebp+var_10], eax
0x1002b87d  mov     [ebp+var_20], edi
0x1002b880  mov     edi, esi
0x1002b882  mov     eax, [ebp+var_20]
0x1002b885  movzx   eax, word ptr [eax]
0x1002b888  cmp     word ptr [ebp+var_A0], si
0x1002b88f  jnz     short loc_1002B8EA
0x1002b891  mov     edi, 88h
0x1002b896  lea     edx, [ebp+var_B4]
0x1002b89c  cmp     di, ax
0x1002b89f  cmovz   edx, [ebp+var_34]
0x1002b8a3  xor     edi, edi
0x1002b8a5  cmp     word ptr [ebp+var_A0], ax
0x1002b8ac  mov     eax, edi
0x1002b8ae  mov     [ebp+var_14], edi
0x1002b8b1  setnz   al
0x1002b8b4  mov     [ebp+var_10], edx
0x1002b8b7  mov     [ebp+var_14], eax
0x1002b8ba  mov     eax, esi
0x1002b8bc  cmp     [ebp+var_14], edi
0x1002b8bf  jnz     short loc_1002B8C7
0x1002b8c1  mov     dword ptr [edx], 1
0x1002b8c7  mov     edx, [ebp+var_24]
0x1002b8ca  mov     [ebp+var_28], ecx
0x1002b8cd  mov     ecx, [ebp+grbit]
0x1002b8d0  mov     [ebp+var_24], edx
0x1002b8d3  mov     edx, [ebp+var_8]
0x1002b8d6  mov     [ebp+grbit], ecx
0x1002b8d9  mov     ecx, [ebp+tableid]
0x1002b8dc  mov     [ebp+var_2C], eax
0x1002b8df  mov     [ebp+var_8], edx
0x1002b8e2  mov     [ebp+tableid], ecx
0x1002b8e5  jmp     def_1002C2A1; jumptable 1002C2A1 default case, cases 1,2,5-12
0x1002b8ea  mov     esi, edi
0x1002b8ec  mov     [ebp+var_28], ecx
0x1002b8ef  mov     [ebp+var_2C], esi
0x1002b8f2  mov     edi, ecx
0x1002b8f4  mov     ecx, [ebp+var_20]
0x1002b8f7  mov     esi, [ebp+var_1C]
0x1002b8fa  mov     [ebp+var_50], edx
0x1002b8fd  mov     [ebp+var_20], ecx
0x1002b900  mov     ecx, 0Dh
0x1002b905  cmp     cx, ax
0x1002b908  jnz     short loc_1002B97B
0x1002b90a  mov     edi, [esi+14h]
0x1002b90d  mov     [ebp+var_60], 1
0x1002b914  test    edi, edi
0x1002b916  jz      short loc_1002B967
0x1002b918  add     edi, 4
0x1002b91b  mov     ecx, offset _IID_ISequentialStream
0x1002b920  mov     esi, edi
0x1002b922  mov     ebx, 0Ch
0x1002b927  mov     eax, [ecx]
0x1002b929  cmp     eax, [esi]
0x1002b92b  jnz     short loc_1002B94C
0x1002b92d  add     ecx, 4
0x1002b930  add     esi, 4
0x1002b933  sub     ebx, 4
0x1002b936  jnb     short loc_1002B927
0x1002b938  mov     ecx, [ebp+var_34]
0x1002b93b  xor     edi, edi
0x1002b93d  mov     [ebp+var_58], 1
0x1002b944  mov     [ebp+var_14], edx
0x1002b947  jmp     loc_1002BA68
0x1002b94c  mov     ecx, offset _IID_IUnknown
0x1002b951  mov     esi, 0Ch
0x1002b956  mov     eax, [ecx]
  ... truncated ...
```
