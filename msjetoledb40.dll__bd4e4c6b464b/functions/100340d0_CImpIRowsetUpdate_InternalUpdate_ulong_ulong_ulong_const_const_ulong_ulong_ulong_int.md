# CImpIRowsetUpdate::InternalUpdate(ulong,ulong,ulong const * const,ulong *,ulong * *,ulong * *,int)

- ea: `0x100340d0`
- end: `0x10034d26`
- name: `?InternalUpdate@CImpIRowsetUpdate@@AAEJKKQBKPAKPAPAK2H@Z`
- size: `3158`
- prototype: `int __thiscall(CImpIRowsetUpdate *__hidden this, unsigned int, unsigned int, const unsigned int *const, unsigned int *, unsigned int **, unsigned int **, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x10033f30`

## callees

- `0x1000bb00`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10027a60`
- `0x1002c700`
- `0x100340d0`
- `0x1004ce5d`
- `0x1004cea1`

## import_xrefs

- `msjet40!__imp__JetDelete@8` at `0x100343cf`
- `msjet40!__imp__JetDelete@8` at `0x100343cf`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10034c7e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10034c7e`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x100342c0`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x100342c0`
- `msjet40!__imp__JetUpdate@20` at `0x10034798`
- `msjet40!__imp__JetUpdate@20` at `0x10034798`

## pseudocode

```c
int __thiscall CImpIRowsetUpdate::InternalUpdate(
        CImpIRowsetUpdate *this,
        unsigned int a2,
        unsigned int a3,
        const unsigned int *a4,
        unsigned int *a5,
        unsigned int **a6,
        unsigned int **a7,
        int a8)
{
  int v8; // eax
  JET_ERR v9; // ebx
  unsigned int **v10; // edi
  int v11; // eax
  unsigned int v12; // edx
  unsigned int *v13; // eax
  unsigned int **v14; // ecx
  unsigned int *v15; // eax
  int v16; // edx
  unsigned int v17; // ecx
  unsigned int *v18; // eax
  int v19; // esi
  _DWORD *v20; // esi
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  int v23; // edx
  unsigned __int8 v24; // al
  int v25; // ecx
  unsigned int v26; // eax
  bool v27; // zf
  _DWORD *v28; // eax
  int v29; // esi
  int v30; // eax
  JET_TABLEID *v31; // ecx
  JET_TABLEID v32; // edx
  CRowset *v33; // esi
  int v34; // edx
  int v35; // eax
  int v36; // ecx
  CRowset *v37; // esi
  int v38; // edx
  CImpIRowsetUpdate *v39; // esi
  _DWORD *v40; // eax
  unsigned int v41; // ecx
  int v42; // eax
  CRowset *v43; // esi
  int v44; // eax
  int v45; // eax
  unsigned int v46; // edx
  int v47; // eax
  unsigned int v48; // edx
  _DWORD *v49; // ecx
  int v50; // ecx
  _DWORD *v51; // ecx
  int v52; // eax
  CRowset *v53; // esi
  JET_ERR v54; // eax
  _DWORD *v55; // eax
  unsigned int v56; // ecx
  CRowset *v57; // esi
  unsigned int v58; // eax
  int v59; // eax
  int v60; // edx
  int v61; // eax
  unsigned int v62; // edx
  _DWORD *v63; // ecx
  int v64; // ecx
  _DWORD *v65; // ecx
  int v66; // eax
  CExtBuffer *v68; // [esp+0h] [ebp-58h]
  enum DBREASONENUM v69; // [esp+0h] [ebp-58h]
  int v70; // [esp+0h] [ebp-58h]
  const struct _GUID *v71; // [esp+4h] [ebp-54h]
  enum DBEVENTPHASEENUM v72; // [esp+4h] [ebp-54h]
  const struct _GUID *v73; // [esp+4h] [ebp-54h]
  unsigned int pcbActual[2]; // [esp+Ch] [ebp-4Ch] BYREF
  int pvBookmark; // [esp+14h] [ebp-44h] BYREF
  unsigned int v76; // [esp+18h] [ebp-40h]
  CRowset *v77; // [esp+1Ch] [ebp-3Ch]
  int v78; // [esp+20h] [ebp-38h]
  unsigned int v79; // [esp+24h] [ebp-34h]
  CRowset *v80; // [esp+28h] [ebp-30h]
  JET_SESID sesid; // [esp+2Ch] [ebp-2Ch]
  int v82; // [esp+30h] [ebp-28h]
  _DWORD *v83; // [esp+34h] [ebp-24h]
  CRowset *v84; // [esp+38h] [ebp-20h]
  int v85; // [esp+3Ch] [ebp-1Ch]
  unsigned int v86; // [esp+40h] [ebp-18h]
  int v87; // [esp+44h] [ebp-14h]
  int v88; // [esp+48h] [ebp-10h]
  int v89; // [esp+4Ch] [ebp-Ch]
  CImpIRowsetUpdate *v90; // [esp+50h] [ebp-8h]
  int v91; // [esp+54h] [ebp-4h]

  v90 = this;
  v8 = *((_DWORD *)this + 2);
  v9 = 0;
  v10 = a7;
  v87 = 0;
  v11 = *(_DWORD *)(v8 + 56);
  v82 = 0;
  v85 = 0;
  sesid = *(_DWORD *)(v11 + 16);
  v89 = 0;
  v88 = 0;
  v12 = 4 * a3;
  v76 = 4 * a3;
  if ( a5 )
  {
    v13 = (unsigned int *)(*(int (__thiscall **)(_DWORD, int, unsigned int))(*(_DWORD *)Sys + 12))(
                            *(_DWORD *)(*(_DWORD *)Sys + 12),
                            Sys,
                            4 * a3);
    v14 = a6;
    *a6 = v13;
    if ( !v13 )
    {
      v15 = a5;
      v16 = -2147024882;
      v87 = -2147024882;
LABEL_201:
      if ( *v15 || !v82 )
        return v16;
      if ( v14 && *v14 )
      {
        if ( Sys )
        {
          (*(void (__thiscall **)(_DWORD, int, unsigned int *))(*(_DWORD *)Sys + 20))(
            *(_DWORD *)(*(_DWORD *)Sys + 20),
            Sys,
            *v14);
          v14 = a6;
        }
        *v14 = 0;
      }
      if ( v10 && *v10 )
      {
        if ( Sys )
          (*(void (__thiscall **)(_DWORD, int, unsigned int *))(*(_DWORD *)Sys + 20))(
            *(_DWORD *)(*(_DWORD *)Sys + 20),
            Sys,
            *v10);
        *v10 = 0;
      }
      return v87;
    }
    v12 = v76;
    v17 = 1;
    v82 = 1;
  }
  else
  {
    v17 = 0;
  }
  if ( a7 )
  {
    v18 = (unsigned int *)(*(int (__thiscall **)(_DWORD, int, unsigned int))(*(_DWORD *)Sys + 12))(
                            *(_DWORD *)(*(_DWORD *)Sys + 12),
                            Sys,
                            v12);
    *a7 = v18;
    if ( !v18 )
    {
      v16 = -2147024882;
      v87 = -2147024882;
      goto LABEL_199;
    }
    v17 = 1;
    v82 = 1;
  }
  v19 = 0;
  pcbActual[1] = v17;
  v91 = 0;
  if ( !a3 )
  {
    v16 = 0;
    goto LABEL_199;
  }
  while ( 1 )
  {
    if ( v10 && *v10 )
      (*v10)[v19] = 0;
    if ( a5 )
      ++*a5;
    if ( a6 && *a6 )
      (*a6)[v19] = a4[v19];
    v20 = *(_DWORD **)(*((_DWORD *)v90 + 2) + 104);
    v21 = a4[v91];
    v84 = (CRowset *)&a4[v91];
    if ( v21 > v20[6] + 8 * v20[5] - 1 )
    {
      v25 = v91;
LABEL_186:
      v35 = 1;
      v89 = 1;
      if ( !v10 )
        goto LABEL_155;
      v34 = v91;
      if ( !*v10 )
        goto LABEL_179;
      (*v10)[v25] = 12;
      v35 = v89;
      v36 = v88;
      goto LABEL_157;
    }
    v22 = v21 - v20[6];
    v23 = v22 & 7;
    v24 = *(_BYTE *)((v22 >> 3) + v20[4]);
    v25 = v91;
    if ( (v24 & *((_BYTE *)&Bitmap::ThisBit + v23)) != 0 )
      goto LABEL_186;
    v26 = a4[v91] * *v20;
    v27 = v20[2] + v26 == 0;
    v28 = (_DWORD *)(v20[2] + v26);
    v83 = v28;
    if ( v27 )
      goto LABEL_186;
    v29 = *v28;
    if ( *v28 == -1 )
      goto LABEL_186;
    if ( ((v30 = v28[1], v31 = (JET_TABLEID *)*((_DWORD *)v90 + 2), v32 = v31[55], v32 != -1) || v31[56]) && v32 == v29 )
    {
      if ( v32 == -2 && (v30 & 4) != 0 )
      {
        v33 = v84;
        if ( CRowset::RowNotify(v84, 0xDu, 0, (enum DBREASONENUM)v68, (enum DBEVENTPHASEENUM)v71) )
          goto LABEL_31;
        v9 = JetPrepareUpdate(sesid, *(_DWORD *)(*((_DWORD *)v90 + 2) + 112), 3u);
        if ( v9 )
        {
          v89 = 1;
          CExtError::SendJetErrortoOLEAuto(v9, (int)&IID_IRowsetUpdate, (int)v68, v71);
          v85 = 1;
          CRowset::RowNotify(v33, 0xDu, (const unsigned int *const)3, v69, v72);
          v34 = v91;
          v36 = v88;
          if ( v10 )
          {
            if ( *v10 )
              (*v10)[v91] = 12;
LABEL_39:
            v35 = v89;
            goto LABEL_157;
          }
          v35 = 1;
        }
        else
        {
          CRowset::RowNotify(
            v33,
            0xDu,
            (const unsigned int *const)4,
            (enum DBREASONENUM)v68,
            (enum DBEVENTPHASEENUM)v71);
          v36 = 1;
          v35 = v89;
          v88 = 1;
          v83[1] = 16;
          v34 = v91;
        }
        goto LABEL_157;
      }
      if ( v30 != 4 )
      {
        v53 = v84;
        if ( CRowset::RowNotify(v84, 0xDu, 0, (enum DBREASONENUM)v68, (enum DBEVENTPHASEENUM)v71) )
        {
LABEL_31:
          v34 = v91;
          if ( v10 && *v10 )
            (*v10)[v91] = 4;
          goto LABEL_34;
        }
        v54 = JetUpdate(sesid, *(_DWORD *)(*((_DWORD *)v90 + 2) + 112), &pvBookmark, 4u, pcbActual);
        v9 = v54;
        if ( v54 < 0 )
        {
          CExtError::SendJetErrortoOLEAuto(v54, (int)&IID_IRowsetUpdate, (int)v68, v71);
          v85 = 1;
LABEL_109:
          CRowset::RowNotify(
            v53,
            0xDu,
            (const unsigned int *const)3,
            (enum DBREASONENUM)v68,
            (enum DBEVENTPHASEENUM)v71);
          if ( v9 > -1053 )
          {
            switch ( v9 )
            {
              case 1614:
              case 1617:
              case 1624:
              case 1625:
              case 1626:
                if ( v10 && *v10 )
                  (*v10)[v91] = 2;
                v35 = v89;
                v36 = 1;
                v88 = 1;
                if ( v9 >= 0 )
                  goto LABEL_129;
                goto LABEL_174;
              default:
                if ( v9 < 0 )
                  goto LABEL_151;
                goto LABEL_129;
            }
          }
          if ( v9 != -1053 )
          {
            if ( v9 > -1613 )
            {
              if ( v9 != -1612 && v9 != -1605 )
                goto LABEL_151;
            }
            else if ( v9 != -1613 )
            {
              if ( v9 == -3703 || v9 == -3702 || v9 == -3701 )
              {
                v34 = v91;
                if ( v10 && *v10 )
                {
                  (*v10)[v91] = 18;
                  v35 = 1;
                  v89 = 1;
                  goto LABEL_156;
                }
LABEL_34:
                v35 = 1;
                v89 = 1;
LABEL_156:
                v36 = v88;
                goto LABEL_157;
              }
LABEL_151:
              if ( v10 && *v10 )
                (*v10)[v91] = 12;
              v35 = 1;
              v89 = 1;
LABEL_155:
              v34 = v91;
              goto LABEL_156;
            }
          }
          v34 = v91;
          if ( v10 && *v10 )
          {
            (*v10)[v91] = 11;
            v35 = 1;
            v89 = 1;
            goto LABEL_156;
          }
          goto LABEL_34;
        }
        if ( v54 )
          goto LABEL_109;
LABEL_129:
        CRowset::RowNotify(v53, 0xDu, (const unsigned int *const)4, (enum DBREASONENUM)v68, (enum DBEVENTPHASEENUM)v71);
        if ( !v9 && *(_DWORD *)(*((_DWORD *)v90 + 2) + 220) == -2 )
          *v83 = pvBookmark;
        v55 = (_DWORD *)*((_DWORD *)v90 + 2);
        v56 = v55[56];
        v79 = v56;
        v55[55] = -1;
        v55[57] = 0;
        v55[56] = 0;
        v55[58] = -1;
        v55[59] = 1;
        if ( !a8 )
        {
          v57 = 0;
          v77 = 0;
          v76 = 0;
          v86 = *(_DWORD *)(*((_DWORD *)v90 + 2) + 16);
          if ( *(_DWORD *)(*(_DWORD *)(v86 + 8) + 52) )
          {
            v57 = (CRowset *)operator new(4u);
            v77 = v57;
            if ( v57 )
            {
              v56 = v79;
              goto LABEL_136;
            }
          }
          else
          {
LABEL_136:
            v58 = v86;
            _mm_lfence();
            v80 = *(CRowset **)(v58 + 8);
            v59 = *((_DWORD *)v80 + 26);
            v60 = *(_DWORD *)(v59 + 24);
            v61 = *(_DWORD *)(v59 + 20);
            v78 = v60;
            if ( v56 <= v60 + 8 * v61 - 1 )
            {
              v10 = a7;
              if ( (*(_BYTE *)(((v56 - v78) >> 3) + *(_DWORD *)(*((_DWORD *)v80 + 26) + 16))
                  & *((_BYTE *)&Bitmap::ThisBit + ((v56 - v78) & 7))) == 0 )
              {
                v62 = v79;
                v63 = (_DWORD *)(*(_DWORD *)(*((_DWORD *)v80 + 26) + 8) + v79 * **((_DWORD **)v80 + 26));
                if ( v63 )
                {
                  if ( *v63 != -1 )
                  {
                    if ( v79 == *((_DWORD *)v80 + 56) && v63[2] == 1 )
                      v63[2] = 2;
                    v27 = v63[2]-- == 1;
                    if ( v27 )
                    {
                      if ( v57 )
                      {
                        *(_DWORD *)v57 = v62;
                        v76 = 1;
                      }
                      v64 = *(_DWORD *)(v86 + 8);
                      if ( *(_DWORD *)(v64 + 228) == v62 )
                      {
                        v65 = *(_DWORD **)(v64 + 216);
                        v78 = (int)v65;
                        if ( v65 )
                        {
                          v66 = v65[3];
                          v65[1] = 1;
                          *(_DWORD *)(v66 + 216) = 0;
                          (*(void (__thiscall **)(int))(*v65 + 4))(v78);
                          v57 = v77;
                          *(_DWORD *)(v78 + 12) = 0;
                        }
                      }
                      CExtBuffer::DeleteFromExtBuffer(v68, (unsigned int)v71);
                      *(_DWORD *)(*(_DWORD *)(v86 + 8) + 136) = 0;
                    }
                  }
                }
              }
            }
            if ( v57 )
            {
              if ( v76 )
                CRowset::RowNotify(
                  v57,
                  5u,
                  (const unsigned int *const)4,
                  (enum DBREASONENUM)v68,
                  (enum DBEVENTPHASEENUM)v71);
              operator delete(v57);
            }
          }
          v53 = v84;
        }
        v34 = v91;
        v83[1] = 8;
        if ( a6 && *a6 )
          (*a6)[v34] = *(_DWORD *)v53;
        v35 = v89;
        if ( !v9 )
        {
          v36 = 1;
          v88 = 1;
          goto LABEL_157;
        }
        goto LABEL_180;
      }
      if ( CRowset::GotoBookmark(v31[28], (unsigned int *)v68, (unsigned int)v71) < 0 )
      {
        v34 = v91;
        v35 = 1;
        v36 = v88;
        v89 = 1;
        if ( v10 )
        {
          if ( !*v10 )
            goto LABEL_39;
          (*v10)[v91] = 12;
          v35 = v89;
        }
        goto LABEL_157;
      }
      v37 = v84;
      if ( CRowset::RowNotify(v84, 6u, 0, (enum DBREASONENUM)v68, (enum DBEVENTPHASEENUM)v71) )
        goto LABEL_31;
      v9 = JetDelete(sesid, *(_DWORD *)(*((_DWORD *)v90 + 2) + 112));
      if ( v9 < 0 )
      {
        CRowset::RowNotify(v37, 6u, (const unsigned int *const)3, (enum DBREASONENUM)v68, (enum DBEVENTPHASEENUM)v71);
        CExtError::SendJetErrortoOLEAuto(v9, (int)&IID_IRowsetUpdate, v70, v73);
        v85 = 1;
      }
      if ( v9 > -1102 )
      {
        if ( v9 > 1624 )
        {
          if ( v9 == 1625 || v9 == 1626 )
          {
LABEL_97:
            if ( v10 )
            {
              v38 = v91;
              if ( *v10 )
                (*v10)[v91] = 2;
LABEL_72:
              if ( a6 )
                (*a6)[v38] = *(_DWORD *)v37;
              v39 = v90;
              v40 = (_DWORD *)*((_DWORD *)v90 + 2);
              v41 = v40[56];
              v86 = v41;
              v40[55] = -1;
              v40[57] = 0;
              v40[56] = 0;
              v40[58] = -1;
              v40[59] = 1;
              if ( !a8 )
              {
                v42 = *((_DWORD *)v39 + 2);
                v43 = 0;
                v80 = 0;
                v78 = 0;
                v88 = *(_DWORD *)(v42 + 16);
                if ( *(_DWORD *)(*(_DWORD *)(v88 + 8) + 52) )
                {
                  v43 = (CRowset *)operator new(4u);
                  v80 = v43;
                  if ( v43 )
                  {
                    v41 = v86;
                    goto LABEL_78;
                  }
                }
                else
                {
LABEL_78:
                  v44 = v88;
                  _mm_lfence();
                  v84 = *(CRowset **)(v44 + 8);
                  v45 = *((_DWORD *)v84 + 26);
                  v46 = *(_DWORD *)(v45 + 24);
                  v47 = *(_DWORD *)(v45 + 20);
                  v76 = v46;
                  if ( v41 <= v46 + 8 * v47 - 1 )
                  {
                    v10 = a7;
                    if ( (*(_BYTE *)(((v41 - v76) >> 3) + *(_DWORD *)(*((_DWORD *)v84 + 26) + 16))
                        & *((_BYTE *)&Bitmap::ThisBit + ((v41 - v76) & 7))) == 0 )
                    {
                      v48 = v86;
                      v49 = (_DWORD *)(*(_DWORD *)(*((_DWORD *)v84 + 26) + 8) + v86 * **((_DWORD **)v84 + 26));
                      if ( v49 )
                      {
                        if ( *v49 != -1 )
                        {
                          if ( v86 == *((_DWORD *)v84 + 56) && v49[2] == 1 )
                            v49[2] = 2;
                          v27 = v49[2]-- == 1;
                          if ( v27 )
                          {
                            if ( v43 )
                            {
                              *(_DWORD *)v43 = v48;
                              v78 = 1;
                            }
                            v50 = *(_DWORD *)(v88 + 8);
                            if ( *(_DWORD *)(v50 + 228) == v48 )
                            {
                              v51 = *(_DWORD **)(v50 + 216);
                              v79 = (unsigned int)v51;
                              if ( v51 )
                              {
                                v52 = v51[3];
                                v51[1] = 1;
                                *(_DWORD *)(v52 + 216) = 0;
                                (*(void (__thiscall **)(unsigned int))(*v51 + 4))(v79);
                                v43 = v80;
                                *(_DWORD *)(v79 + 12) = 0;
                              }
                            }
                            CExtBuffer::DeleteFromExtBuffer(v68, (unsigned int)v71);
                            *(_DWORD *)(*(_DWORD *)(v88 + 8) + 136) = 0;
                          }
                        }
                      }
                    }
                  }
                  if ( v43 )
                  {
                    if ( v78 )
                      CRowset::RowNotify(
                        v43,
                        5u,
                        (const unsigned int *const)4,
                        (enum DBREASONENUM)v68,
                        (enum DBEVENTPHASEENUM)v71);
                    operator delete(v43);
                  }
                }
              }
              v36 = 1;
              v34 = v91;
              v88 = 1;
              v83[1] = 16;
              v35 = v89;
              goto LABEL_157;
            }
LABEL_71:
            v38 = v91;
            goto LABEL_72;
          }
        }
        else
        {
          switch ( v9 )
          {
            case 1624:
              goto LABEL_97;
            case -1053:
LABEL_60:
              v34 = v91;
              v35 = 1;
              v36 = v88;
              v89 = 1;
              if ( v10 )
              {
                if ( !*v10 )
                  goto LABEL_39;
                (*v10)[v91] = 11;
                v35 = v89;
              }
              goto LABEL_157;
            case 0:
              CRowset::RowNotify(
                v37,
                6u,
                (const unsigned int *const)4,
                (enum DBREASONENUM)v68,
                (enum DBEVENTPHASEENUM)v71);
              goto LABEL_71;
          }
        }
      }
      else
      {
        if ( v9 == -1102 )
        {
          v34 = v91;
          v35 = 1;
          v36 = v88;
          v89 = 1;
          if ( v10 )
          {
            if ( !*v10 )
              goto LABEL_39;
            (*v10)[v91] = 7;
            v35 = v89;
          }
          goto LABEL_157;
        }
        if ( v9 > -1613 )
        {
          if ( v9 == -1612 || v9 == -1605 )
            goto LABEL_60;
        }
        else
        {
          if ( v9 == -1613 )
            goto LABEL_60;
          if ( v9 == -1907 || v9 == -1809 )
          {
            v34 = v91;
            v35 = 1;
            v36 = v88;
            v89 = 1;
            if ( v10 )
            {
              if ( !*v10 )
                goto LABEL_39;
              (*v10)[v91] = 16;
              v35 = v89;
            }
            goto LABEL_157;
          }
        }
      }
      v34 = v91;
      v35 = 1;
      v36 = v88;
      v89 = 1;
      if ( v10 )
      {
        if ( !*v10 )
          goto LABEL_39;
        (*v10)[v91] = 19;
        v35 = v89;
      }
    }
    else
    {
      switch ( v30 )
      {
        case 8:
          v35 = v89;
          v36 = 1;
          v88 = 1;
LABEL_174:
          v34 = v91;
          break;
        case 16:
          v35 = 1;
          v89 = 1;
          if ( !v10 )
            goto LABEL_155;
          v34 = v91;
          if ( *v10 )
            (*v10)[v91] = 8;
LABEL_179:
          v35 = v89;
LABEL_180:
          v36 = v88;
          break;
        case 4:
          v35 = v89;
          goto LABEL_155;
        default:
          v35 = 1;
          v89 = 1;
          if ( !v10 )
            goto LABEL_155;
          v34 = v91;
          if ( !*v10 )
            goto LABEL_179;
          (*v10)[v91] = 12;
          v35 = v89;
          v36 = v88;
          break;
      }
    }
LABEL_157:
    v91 = v34 + 1;
    if ( v34 + 1 >= a3 )
      break;
    v19 = v91;
  }
  if ( v36 == 1 )
  {
    v76 = 0;
    v16 = 265946;
    if ( v35 != 1 )
      v16 = v76;
    v87 = v16;
  }
  else if ( v35 == 1 )
  {
    v16 = -2147217887;
    v87 = -2147217887;
  }
  else
  {
    v16 = 0;
  }
  if ( !v85 )
  {
    if ( v9 )
    {
      CExtError::SendJetErrortoOLEAuto(v9, (int)&IID_IRowsetUpdate, (int)v68, v71);
      v16 = v87;
    }
    else
    {
      v87 = v16;
      if ( v16 < 0 )
        v87 = v16;
    }
  }
LABEL_199:
  v15 = a5;
  if ( a5 )
  {
    v14 = a6;
    goto LABEL_201;
  }
  return v16;
}

```

## disassembly

```asm
0x100340d0  mov     edi, edi
0x100340d2  push    ebp
0x100340d3  mov     ebp, esp
0x100340d5  sub     esp, 4Ch
0x100340d8  mov     eax, ecx
0x100340da  xor     ecx, ecx
0x100340dc  mov     [ebp+var_8], eax
0x100340df  push    ebx
0x100340e0  push    esi
0x100340e1  mov     eax, [eax+8]
0x100340e4  xor     ebx, ebx
0x100340e6  push    edi
0x100340e7  mov     edi, [ebp+arg_14]
0x100340ea  mov     [ebp+var_14], ecx
0x100340ed  mov     eax, [eax+38h]
0x100340f0  mov     [ebp+var_28], ecx
0x100340f3  mov     [ebp+var_1C], ecx
0x100340f6  mov     eax, [eax+10h]
0x100340f9  mov     [ebp+sesid], eax
0x100340fc  xor     eax, eax
0x100340fe  mov     [ebp+var_C], eax
0x10034101  mov     [ebp+var_10], eax
0x10034104  mov     eax, [ebp+arg_4]
0x10034107  lea     edx, ds:0[eax*4]
0x1003410e  mov     [ebp+var_40], edx
0x10034111  cmp     [ebp+arg_C], ecx
0x10034114  jz      short loc_10034153
0x10034116  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1003411c  push    edx
0x1003411d  push    ecx
0x1003411e  mov     eax, [ecx]
0x10034120  mov     esi, [eax+0Ch]
0x10034123  mov     ecx, esi
0x10034125  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1003412b  call    esi
0x1003412d  mov     ecx, [ebp+arg_10]
0x10034130  mov     [ecx], eax
0x10034132  test    eax, eax
0x10034134  jnz     short loc_10034146
0x10034136  mov     eax, [ebp+arg_C]
0x10034139  mov     edx, 8007000Eh
0x1003413e  mov     [ebp+var_14], edx
0x10034141  jmp     loc_10034CAC
0x10034146  mov     edx, [ebp+var_40]
0x10034149  mov     ecx, 1
0x1003414e  mov     [ebp+var_28], ecx
0x10034151  jmp     short loc_10034155
0x10034153  xor     ecx, ecx
0x10034155  test    edi, edi
0x10034157  jz      short loc_1003418B
0x10034159  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1003415f  push    edx
0x10034160  push    ecx
0x10034161  mov     eax, [ecx]
0x10034163  mov     esi, [eax+0Ch]
0x10034166  mov     ecx, esi
0x10034168  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1003416e  call    esi
0x10034170  mov     [edi], eax
0x10034172  test    eax, eax
0x10034174  jnz     short loc_10034183
0x10034176  mov     edx, 8007000Eh
0x1003417b  mov     [ebp+var_14], edx
0x1003417e  jmp     loc_10034CA2
0x10034183  mov     ecx, 1
0x10034188  mov     [ebp+var_28], ecx
0x1003418b  xor     esi, esi
0x1003418d  mov     [ebp+var_48], ecx
0x10034190  mov     [ebp+var_4], esi
0x10034193  cmp     [ebp+arg_4], ebx
0x10034196  ja      short loc_100341A3
0x10034198  xor     edx, edx
0x1003419a  jmp     loc_10034CA2
0x100341a0  mov     esi, [ebp+var_4]
0x100341a3  test    edi, edi
0x100341a5  jz      short loc_100341B4
0x100341a7  mov     eax, [edi]
0x100341a9  test    eax, eax
0x100341ab  jz      short loc_100341B4
0x100341ad  mov     dword ptr [eax+esi*4], 0
0x100341b4  mov     eax, [ebp+arg_C]
0x100341b7  test    eax, eax
0x100341b9  jz      short loc_100341BD
0x100341bb  inc     dword ptr [eax]
0x100341bd  mov     eax, [ebp+arg_10]
0x100341c0  test    eax, eax
0x100341c2  jz      short loc_100341D3
0x100341c4  mov     ecx, [eax]
0x100341c6  test    ecx, ecx
0x100341c8  jz      short loc_100341D3
0x100341ca  mov     eax, [ebp+arg_8]
0x100341cd  mov     eax, [eax+esi*4]
0x100341d0  mov     [ecx+esi*4], eax
0x100341d3  mov     eax, [ebp+var_8]
0x100341d6  mov     ecx, [ebp+arg_8]
0x100341d9  mov     esi, [eax+8]
0x100341dc  mov     eax, [ebp+var_4]
0x100341df  mov     esi, [esi+68h]
0x100341e2  lea     eax, [ecx+eax*4]
0x100341e5  mov     ecx, [eax]
0x100341e7  mov     [ebp+var_20], eax
0x100341ea  mov     eax, [esi+14h]
0x100341ed  lea     eax, ds:0FFFFFFFFh[eax*8]
0x100341f4  add     eax, [esi+18h]
0x100341f7  cmp     ecx, eax
0x100341f9  ja      loc_10034BCC
0x100341ff  mov     eax, [esi+10h]
0x10034202  mov     edx, ecx
0x10034204  sub     edx, [esi+18h]
0x10034207  mov     ecx, edx
0x10034209  and     edx, 7
0x1003420c  shr     ecx, 3
0x1003420f  mov     al, [ecx+eax]
0x10034212  mov     ecx, [ebp+var_4]
0x10034215  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1003421b  jnz     loc_10034BCF
0x10034221  mov     edx, [ebp+arg_8]
0x10034224  mov     eax, [esi]
0x10034226  imul    eax, [edx+ecx*4]
0x1003422a  add     eax, [esi+8]
0x1003422d  mov     [ebp+var_24], eax
0x10034230  jz      loc_10034BCF
0x10034236  mov     esi, [eax]
0x10034238  cmp     esi, 0FFFFFFFFh
0x1003423b  jz      loc_10034BCF
0x10034241  mov     edx, [ebp+var_8]
0x10034244  mov     eax, [eax+4]
0x10034247  mov     ecx, [edx+8]
0x1003424a  mov     edx, [ecx+0DCh]
0x10034250  cmp     edx, 0FFFFFFFFh
0x10034253  jnz     short loc_10034262
0x10034255  cmp     dword ptr [ecx+0E0h], 0
0x1003425c  jz      loc_10034B4A
0x10034262  cmp     edx, esi
0x10034264  jnz     loc_10034B4A
0x1003426a  cmp     edx, 0FFFFFFFEh
0x1003426d  jnz     loc_1003435D
0x10034273  test    al, 4
0x10034275  jz      loc_1003435D
0x1003427b  mov     esi, [ebp+var_20]
0x1003427e  mov     edx, 1
0x10034283  push    0; unsigned int *
0x10034285  push    0Dh; unsigned int
0x10034287  push    esi; this
0x10034288  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x1003428d  test    eax, eax
0x1003428f  jz      short loc_100342B2
0x10034291  mov     edx, [ebp+var_4]
0x10034294  test    edi, edi
0x10034296  jz      short loc_100342A5
0x10034298  mov     eax, [edi]
0x1003429a  test    eax, eax
0x1003429c  jz      short loc_100342A5
0x1003429e  mov     dword ptr [eax+edx*4], 4
0x100342a5  mov     eax, 1
0x100342aa  mov     [ebp+var_C], eax
0x100342ad  jmp     loc_10034AB5
0x100342b2  mov     eax, [ebp+var_8]
0x100342b5  push    3; prep
0x100342b7  mov     eax, [eax+8]
0x100342ba  push    dword ptr [eax+70h]; tableid
0x100342bd  push    [ebp+sesid]; sesid
0x100342c0  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x100342c6  mov     ebx, eax
0x100342c8  test    ebx, ebx
0x100342ca  jz      short loc_1003432B
0x100342cc  mov     eax, [ebp+var_8]
0x100342cf  xor     edx, edx
0x100342d1  push    offset _IID_IRowsetUpdate; int
0x100342d6  push    ebx; unsigned int
0x100342d7  mov     [ebp+var_C], 1
0x100342de  mov     ecx, [eax+8]
0x100342e1  mov     ecx, [ecx+38h]
0x100342e4  mov     ecx, [ecx+10h]
0x100342e7  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x100342ec  push    3; unsigned int *
0x100342ee  push    0Dh; unsigned int
0x100342f0  push    esi; this
0x100342f1  mov     esi, [ebp+var_8]
0x100342f4  mov     edx, 1
0x100342f9  mov     [ebp+var_1C], 1
0x10034300  mov     ecx, [esi+8]
0x10034303  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x10034308  mov     edx, [ebp+var_4]
0x1003430b  mov     ecx, [ebp+var_10]
0x1003430e  test    edi, edi
0x10034310  jz      loc_10034C05
0x10034316  mov     eax, [edi]
0x10034318  test    eax, eax
0x1003431a  jz      short loc_10034323
0x1003431c  mov     dword ptr [eax+edx*4], 0Ch
0x10034323  mov     eax, [ebp+var_C]
0x10034326  jmp     loc_10034ABB
0x1003432b  push    4; unsigned int *
0x1003432d  push    0Dh; unsigned int
0x1003432f  push    esi; this
0x10034330  mov     esi, [ebp+var_8]
0x10034333  mov     edx, 1
0x10034338  mov     ecx, [esi+8]
0x1003433b  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x10034340  mov     edx, [ebp+var_24]
0x10034343  mov     ecx, 1
0x10034348  mov     eax, [ebp+var_C]
0x1003434b  mov     [ebp+var_10], ecx
0x1003434e  mov     dword ptr [edx+4], 10h
0x10034355  mov     edx, [ebp+var_4]
0x10034358  jmp     loc_10034ABB
0x1003435d  cmp     eax, 4
0x10034360  jnz     loc_10034768
0x10034366  push    dword ptr [ecx+70h]; tableid
0x10034369  mov     edx, [ebp+var_24]
0x1003436c  call    ?GotoBookmark@CRowset@@IAGJPAKK@Z; CRowset::GotoBookmark(ulong *,ulong)
0x10034371  test    eax, eax
0x10034373  jns     short loc_100343A3
0x10034375  mov     edx, [ebp+var_4]
0x10034378  mov     eax, 1
0x1003437d  mov     esi, [ebp+var_8]
0x10034380  mov     ecx, [ebp+var_10]
0x10034383  mov     [ebp+var_C], eax
0x10034386  test    edi, edi
0x10034388  jz      loc_10034ABB
0x1003438e  mov     eax, [edi]
0x10034390  test    eax, eax
0x10034392  jz      short loc_10034323
0x10034394  mov     dword ptr [eax+edx*4], 0Ch
0x1003439b  mov     eax, [ebp+var_C]
0x1003439e  jmp     loc_10034ABB
0x100343a3  mov     eax, [ebp+var_8]
0x100343a6  mov     edx, 1
0x100343ab  mov     esi, [ebp+var_20]
0x100343ae  push    0; unsigned int *
0x100343b0  push    6; unsigned int
0x100343b2  mov     ecx, [eax+8]
0x100343b5  push    esi; this
0x100343b6  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x100343bb  test    eax, eax
0x100343bd  jnz     loc_10034291
0x100343c3  mov     eax, [ebp+var_8]
0x100343c6  mov     eax, [eax+8]
0x100343c9  push    dword ptr [eax+70h]; tableid
0x100343cc  push    [ebp+sesid]; sesid
0x100343cf  call    ds:__imp__JetDelete@8; JetDelete(x,x)
0x100343d5  mov     ebx, eax
0x100343d7  test    ebx, ebx
0x100343d9  jns     short loc_10034413
0x100343db  mov     eax, [ebp+var_8]
0x100343de  mov     edx, 1
0x100343e3  push    3; unsigned int *
0x100343e5  push    6; unsigned int
0x100343e7  push    esi; this
0x100343e8  mov     ecx, [eax+8]
0x100343eb  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x100343f0  mov     eax, [ebp+var_8]
0x100343f3  mov     edx, 80040E21h
0x100343f8  push    offset _IID_IRowsetUpdate; int
0x100343fd  push    ebx; unsigned int
0x100343fe  mov     eax, [eax+8]
0x10034401  mov     ecx, [eax+38h]
0x10034404  mov     ecx, [ecx+10h]
0x10034407  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1003440c  mov     [ebp+var_1C], 1
0x10034413  cmp     ebx, 0FFFFFBB2h
0x10034419  jg      loc_100344ED
0x1003441f  jz      loc_100344BB
0x10034425  cmp     ebx, 0FFFFF9B3h
0x1003442b  jg      short loc_10034475
0x1003442d  jz      short loc_10034489
0x1003442f  cmp     ebx, 0FFFFF88Dh
0x10034435  jz      short loc_10034443
0x10034437  cmp     ebx, 0FFFFF8EFh
0x1003443d  jnz     loc_100346CF
0x10034443  mov     edx, [ebp+var_4]
0x10034446  mov     eax, 1
0x1003444b  mov     esi, [ebp+var_8]
0x1003444e  mov     ecx, [ebp+var_10]
0x10034451  mov     [ebp+var_C], eax
0x10034454  test    edi, edi
0x10034456  jz      loc_10034ABB
0x1003445c  mov     eax, [edi]
0x1003445e  test    eax, eax
0x10034460  jz      loc_10034323
0x10034466  mov     dword ptr [eax+edx*4], 10h
0x1003446d  mov     eax, [ebp+var_C]
0x10034470  jmp     loc_10034ABB
0x10034475  cmp     ebx, 0FFFFF9B4h
0x1003447b  jz      short loc_10034489
0x1003447d  cmp     ebx, 0FFFFF9BBh
0x10034483  jnz     loc_100346CF
0x10034489  mov     edx, [ebp+var_4]
0x1003448c  mov     eax, 1
0x10034491  mov     esi, [ebp+var_8]
0x10034494  mov     ecx, [ebp+var_10]
0x10034497  mov     [ebp+var_C], eax
0x1003449a  test    edi, edi
0x1003449c  jz      loc_10034ABB
0x100344a2  mov     eax, [edi]
0x100344a4  test    eax, eax
0x100344a6  jz      loc_10034323
0x100344ac  mov     dword ptr [eax+edx*4], 0Bh
0x100344b3  mov     eax, [ebp+var_C]
  ... truncated ...
```
