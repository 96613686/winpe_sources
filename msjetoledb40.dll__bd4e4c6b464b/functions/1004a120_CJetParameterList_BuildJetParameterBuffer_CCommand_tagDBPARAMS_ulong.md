# CJetParameterList::BuildJetParameterBuffer(CCommand *,tagDBPARAMS *,ulong)

- ea: `0x1004a120`
- end: `0x1004ab3c`
- name: `?BuildJetParameterBuffer@CJetParameterList@@QAEJPAVCCommand@@PAUtagDBPARAMS@@K@Z`
- size: `2588`
- prototype: `int __thiscall(CJetParameterList *__hidden this, struct CCommand *, struct tagDBPARAMS *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1000fcf0`

## callees

- `0x10015b10`
- `0x10017690`
- `0x1001c6d0`
- `0x10049c60`
- `0x1004a070`
- `0x1004a120`
- `0x1004ae80`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004dc81`

## pseudocode

```c
int __thiscall CJetParameterList::BuildJetParameterBuffer(
        void **this,
        struct CCommand *a2,
        struct tagDBPARAMS *a3,
        unsigned int a4)
{
  int v5; // ebx
  _DWORD *v7; // eax
  unsigned int v8; // ecx
  unsigned int *v9; // esi
  struct tagREDACCESSOR *v10; // eax
  CJetParameterList *v11; // edx
  unsigned int v12; // esi
  int v13; // edi
  unsigned int *v14; // eax
  void *v15; // ebx
  int v16; // eax
  unsigned int v17; // edi
  unsigned int *v18; // esi
  unsigned int v19; // ecx
  unsigned int *v20; // eax
  DBLENGTH v21; // ecx
  unsigned int v22; // edi
  unsigned int *v23; // esi
  char *v24; // eax
  bool v25; // zf
  unsigned __int16 *v26; // edx
  struct tagREDACCESSOR *v27; // eax
  unsigned int v28; // edi
  struct tagREDACCESSOR *v29; // eax
  unsigned int v30; // edi
  unsigned int *p_cbMaxLen; // eax
  unsigned int v32; // ecx
  unsigned int *v33; // edx
  unsigned int *v34; // eax
  const unsigned __int16 *v35; // edi
  int v36; // ebx
  unsigned int v37; // ecx
  unsigned int *v38; // eax
  _WORD *v39; // edx
  _WORD *v40; // ecx
  unsigned int *v42; // esi
  int v43; // eax
  unsigned int *v44; // eax
  int v45; // eax
  struct tagREDACCESSOR *v46; // esi
  unsigned int v47; // ecx
  struct tagREDACCESSOR **v48; // eax
  struct tagREDACCESSOR *v49; // eax
  unsigned int *v50; // ecx
  int v51; // ecx
  struct tagREDACCESSOR *v52; // esi
  struct tagREDACCESSOR *v53; // ecx
  struct tagREDACCESSOR *v54; // eax
  struct tagREDACCESSOR *v55; // ecx
  unsigned int *v56; // ecx
  size_t cbMaxLen; // ecx
  struct tagREDACCESSOR *v58; // eax
  struct tagREDACCESSOR **v59; // eax
  struct tagREDACCESSOR *v60; // eax
  int v61; // eax
  unsigned int *v62; // edx
  struct tagREDACCESSOR *v63; // esi
  size_t v64; // eax
  struct tagREDACCESSOR **v65; // ecx
  unsigned int *v66; // eax
  struct tagREDACCESSOR *v67; // eax
  struct tagREDACCESSOR *v68; // edx
  unsigned int *v69; // ecx
  struct tagDBBINDING *v70; // esi
  void *v71; // ebx
  int v72; // edx
  unsigned int *v73; // eax
  const char *v74; // edi
  size_t v75; // edx
  _DWORD *v76; // esi
  unsigned int v77; // ecx
  unsigned int *v78; // eax
  __int16 v79; // bx
  BOOL v80; // edx
  struct tagREDACCESSOR *v81; // esi
  unsigned int v82; // [esp+28h] [ebp-60h]
  void *v83; // [esp+2Ch] [ebp-5Ch]
  size_t Size; // [esp+34h] [ebp-54h] BYREF
  const char *v85; // [esp+38h] [ebp-50h]
  unsigned int *v86; // [esp+3Ch] [ebp-4Ch]
  unsigned int v87; // [esp+40h] [ebp-48h]
  struct tagREDACCESSOR **v88; // [esp+44h] [ebp-44h]
  struct tagREDACCESSOR *v89; // [esp+48h] [ebp-40h]
  struct tagDBBINDING *v90; // [esp+4Ch] [ebp-3Ch]
  size_t v91; // [esp+50h] [ebp-38h] BYREF
  unsigned int *v92; // [esp+54h] [ebp-34h]
  unsigned int *v93; // [esp+58h] [ebp-30h]
  CJetParameterList *v94; // [esp+5Ch] [ebp-2Ch]
  _DWORD *v95; // [esp+60h] [ebp-28h]
  struct tagREDACCESSOR *v96; // [esp+64h] [ebp-24h]
  int v97; // [esp+68h] [ebp-20h] BYREF
  void *Src; // [esp+6Ch] [ebp-1Ch] BYREF
  unsigned int v99; // [esp+70h] [ebp-18h]
  unsigned int v100; // [esp+74h] [ebp-14h]
  struct tagREDACCESSOR *wType; // [esp+78h] [ebp-10h] BYREF
  int v102; // [esp+7Ch] [ebp-Ch]
  struct tagREDACCESSOR *v103; // [esp+80h] [ebp-8h]
  size_t v104; // [esp+84h] [ebp-4h] BYREF

  wType = 0;
  v94 = (CJetParameterList *)this;
  if ( this[2] )
  {
    operator delete(this[2]);
    this[2] = 0;
    this[1] = 0;
  }
  v5 = CLVParamArray::Clear((CLVParamArray *)(*((_DWORD *)a2 + 13) + 92));
  if ( v5 >= 0 && a3 && a3->cParamSets )
  {
    if ( !a3->pData )
      return -2147024809;
    if ( CExtBuffer::GetItemOfExtBuffer((CExtBuffer *)&wType, v82, v83) >= 0 && (v96 = wType) != 0 )
    {
      if ( *((_DWORD *)wType + 3) != 3 )
        return -2147217845;
      v7 = *this;
      v8 = 0;
      if ( *this )
      {
        do
        {
          v7 = (_DWORD *)v7[10];
          ++v8;
        }
        while ( v7 );
      }
      if ( *((_DWORD *)wType + 9) < v8 )
        return -2147217904;
      v9 = (unsigned int *)(this + 1);
      v100 = a4 * *((_DWORD *)wType + 7);
      v5 = CJetParameterList::DetermineSizeOfJetBuffer(v94, wType, a3, v9);
      if ( v5 >= 0 )
      {
        v10 = (struct tagREDACCESSOR *)operator new(*v9);
        v11 = v94;
        v89 = v10;
        *((_DWORD *)v94 + 2) = v10;
        if ( !v10 )
        {
          *v9 = 0;
          return -2147024882;
        }
        v12 = 0;
        v13 = *((_DWORD *)a2 + 13);
        v14 = *(unsigned int **)v11;
        if ( *(_DWORD *)v11 )
        {
          do
          {
            v14 = (unsigned int *)v14[10];
            ++v12;
          }
          while ( v14 );
        }
        if ( v12 > *(_DWORD *)(v13 + 96) )
        {
          v15 = operator new(saturated_mul(0x10u, v12));
          if ( !v15 )
            return -2147024882;
          v16 = *(_DWORD *)(v13 + 100);
          if ( v16 )
          {
            memcpy(v15, *(const void **)(v13 + 92), 16 * v16);
            operator delete(*(void **)(v13 + 92));
          }
          v11 = v94;
          *(_DWORD *)(v13 + 96) = v12;
          *(_DWORD *)(v13 + 92) = v15;
        }
        v5 = 0;
        v102 = 13;
        v17 = 1;
        while ( 1 )
        {
          while ( 1 )
          {
            v18 = *(unsigned int **)v11;
            v19 = 0;
            v99 = v17;
            v92 = v18;
            if ( v18 )
            {
              v20 = v18;
              do
              {
                v20 = (unsigned int *)v20[10];
                ++v19;
              }
              while ( v20 );
            }
            if ( v17 > v19 )
              return v5;
            v93 = 0;
            v21 = 0;
            v95 = 0;
            v85 = 0;
            Src = 0;
            v97 = 0;
            Size = 0;
            v91 = 0;
            v103 = 0;
            if ( !v18 )
              return -2147467259;
            while ( *v18 != v17 )
            {
              v18 = (unsigned int *)v18[10];
              v92 = v18;
              if ( !v18 )
                return -2147467259;
            }
            if ( v18[2] == 1 )
              return -2147467259;
            v22 = 0;
            wType = (struct tagREDACCESSOR *)*((_DWORD *)v96 + 9);
            if ( !wType )
              return -2147467259;
            while ( 1 )
            {
              v23 = v92;
              if ( v99 == *((_DWORD *)v96 + 13 * v22 + 10) )
                break;
              if ( ++v22 >= (unsigned int)wType )
                return -2147467259;
            }
            v5 = 0;
            v24 = (char *)v96 + 52 * v22 + 40;
            v90 = (struct tagDBBINDING *)v24;
            v25 = (*((_DWORD *)v24 + 7) & 1) == 0;
            wType = (struct tagREDACCESSOR *)*((_DWORD *)v24 + 7);
            v26 = (unsigned __int16 *)v85;
            if ( !v25 )
            {
              v26 = (unsigned __int16 *)((char *)a3->pData + *((_DWORD *)v24 + 1) + v100);
              v23 = v92;
              v85 = (const char *)v26;
              Src = v26;
            }
            if ( (v24[28] & 2) != 0 )
            {
              v23 = v92;
              v93 = (unsigned int *)((char *)a3->pData + *((_DWORD *)v24 + 2) + v100);
            }
            if ( ((unsigned __int8)wType & 4) != 0 )
            {
              v23 = v92;
              v95 = (char *)a3->pData + v90->obStatus + v100;
            }
            if ( !v26 )
            {
              v5 = -2147217887;
              if ( !v95 )
                return v5;
              *v95 = 1;
              return -2147217887;
            }
            if ( v95 )
              break;
LABEL_53:
            v25 = (_WORD)v102 == v90->wType;
            wType = (struct tagREDACCESSOR *)v90->wType;
            p_cbMaxLen = v93;
            if ( v25 )
            {
              v5 = CJetParameterList::ReadStorageParameter((CJetParameterList *)&Size, v90, &Src, v93, &Size);
              if ( v5 < 0 )
              {
                CJetParameterList::ReleaseStorageParameters(v94, v22, a3, v32, v96);
                return v5;
              }
              v21 = Size;
              v33 = v23;
              v87 = v22;
              v34 = v23;
              v35 = (const unsigned __int16 *)Src;
              v86 = v23;
              v88 = (struct tagREDACCESSOR **)v23;
              v85 = (const char *)Src;
              goto LABEL_87;
            }
            v36 = (unsigned __int16)wType & 0x8FFF;
            if ( v36 == 128 )
            {
              if ( !v93 )
                p_cbMaxLen = &v90->cbMaxLen;
LABEL_59:
              v21 = *p_cbMaxLen;
              goto LABEL_60;
            }
            if ( v36 != 129 && v36 != 130 )
            {
              if ( v36 == 8 )
              {
                v21 = 4;
              }
              else if ( v36 == 131 )
              {
                v21 = 19;
              }
              else
              {
                v37 = v23[6];
                if ( v37 )
                  v21 = dword_10051944[2 * v37];
                else
                  v21 = v23[9];
              }
              goto LABEL_60;
            }
            if ( v93 )
              goto LABEL_59;
            v38 = (unsigned int *)v90->wType;
            v93 = v38;
            if ( (unsigned int)v38 > 0x4081 )
            {
              v5 = 0;
              v87 = v22;
              v33 = v23;
              v34 = v23;
              v86 = v23;
              v88 = (struct tagREDACCESSOR **)v23;
              if ( v93 != (unsigned int *)16514 )
                goto LABEL_86;
              v87 = v22;
              v86 = v23;
              v88 = (struct tagREDACCESSOR **)v23;
              v39 = *(_WORD **)v85;
              if ( !*(_DWORD *)v85 )
              {
                v33 = v86;
                goto LABEL_86;
              }
              v40 = v39 + 1;
              while ( *v39++ )
                ;
              v21 = 2 * (v39 - v40);
            }
            else if ( v38 == (unsigned int *)16513 )
            {
              if ( !*(_DWORD *)v26 )
                goto LABEL_61;
              v21 = strlen(*(const char **)v26);
            }
            else
            {
              v5 = 0;
              v87 = v22;
              v25 = v93 == (unsigned int *)129;
              v93 = (unsigned int *)((char *)v93 - 129);
              v33 = v23;
              v34 = v23;
              v86 = v23;
              v88 = (struct tagREDACCESSOR **)v23;
              if ( v25 )
              {
                v21 = strlen(v85);
              }
              else
              {
                v93 = (unsigned int *)((char *)v93 - 1);
                if ( v93 )
                  goto LABEL_86;
                v21 = 2 * wcslen((const unsigned __int16 *)v85);
              }
            }
LABEL_60:
            Size = v21;
LABEL_61:
            v33 = v23;
            v87 = v22;
            v34 = v23;
            v86 = v23;
            v5 = 0;
            v88 = (struct tagREDACCESSOR **)v23;
LABEL_86:
            v35 = (const unsigned __int16 *)v85;
LABEL_87:
            v25 = v33[6] == 0;
            Src = v33 + 6;
            if ( v25 )
            {
              v42 = v33;
            }
            else
            {
              v42 = v34;
              v34 = v33;
            }
            v25 = v33[6] == 0;
            v92 = (unsigned int *)((char *)v34 + 22);
            v93 = v42 + 7;
            wType = (struct tagREDACCESSOR *)v90->wType;
            v43 = 28;
            if ( !v25 )
              v43 = 22;
            if ( (_WORD)wType == *(_WORD *)((char *)v33 + v43) )
            {
              v91 = v21;
              if ( v21 > v90->cbMaxLen && (v90->wType & 0x4000) == 0 )
                goto LABEL_99;
            }
            else
            {
              if ( (_WORD)wType == 13 )
              {
                v91 = v21;
              }
              else
              {
                v44 = v92;
                if ( !*(_DWORD *)Src )
                  v44 = v93;
                v45 = (*(int (__thiscall **)(_DWORD, LPVOID, struct tagREDACCESSOR *, _DWORD, size_t *, size_t *, const unsigned __int16 *))(*(_DWORD *)g_pIDataConvert + 20))(
                        *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 20),
                        g_pIDataConvert,
                        wType,
                        *(unsigned __int16 *)v44,
                        &Size,
                        &v91,
                        v35);
                v33 = v86;
                v5 = v45;
              }
              if ( v5 < 0 )
              {
LABEL_99:
                if ( v95 )
                  *v95 = 2;
LABEL_101:
                CJetParameterList::ReleaseStorageParameters(v94, v87 + 1, a3, v21, v96);
                return -2147217887;
              }
            }
            v46 = (struct tagREDACCESSOR *)v33[6];
            if ( v46 )
            {
              v47 = v33[6];
              v48 = v88 + 8;
            }
            else
            {
              v47 = v33[8];
              v48 = (struct tagREDACCESSOR **)(v33 + 8);
            }
            v88 = v48;
            if ( v47 != 10 )
            {
              v49 = v46 ? v46 : *v48;
              if ( v49 != (struct tagREDACCESSOR *)9 )
                goto LABEL_118;
            }
            v50 = v92;
            if ( !v46 )
              v50 = v93;
            if ( v90->wType == *(_WORD *)v50 )
            {
              if ( !v46 )
                v46 = *v88;
              v51 = (v46 == (struct tagREDACCESSOR *)10) + 11;
            }
            else
            {
LABEL_118:
              if ( v46 )
                v51 = (int)v46;
              else
                v51 = (int)*v88;
            }
            wType = (struct tagREDACCESSOR *)((char *)v89 + 4);
            *(_DWORD *)v89 = v51;
            v52 = (struct tagREDACCESSOR *)v33[6];
            if ( v52 )
              v53 = (struct tagREDACCESSOR *)v33[6];
            else
              v53 = *v88;
            if ( v53 == (struct tagREDACCESSOR *)10
              || (v52 ? (v54 = (struct tagREDACCESSOR *)v33[6]) : (v54 = *v88), v54 == (struct tagREDACCESSOR *)9) )
            {
              v56 = v92;
              if ( !v52 )
                v56 = v93;
              if ( v90->wType != *(_WORD *)v56 )
              {
                v103 = wType;
                v55 = (struct tagREDACCESSOR *)((char *)wType + 4);
                goto LABEL_137;
              }
              v11 = v94;
              cbMaxLen = v90->cbMaxLen;
              v58 = wType;
              if ( v91 < cbMaxLen )
                cbMaxLen = v91;
              *(_DWORD *)wType = cbMaxLen;
              *((_DWORD *)v58 + 1) = v35;
              v89 = (struct tagREDACCESSOR *)((char *)v58 + 8);
              v17 = v99 + 1;
            }
            else
            {
              v55 = wType;
LABEL_137:
              v89 = v55;
              v59 = (struct tagREDACCESSOR **)(v33 + 6);
              if ( !v52 )
                v59 = v88;
              if ( *v59 == (struct tagREDACCESSOR *)11
                || (v52 ? (wType = v52) : (struct tagREDACCESSOR *)(wType = *v88, v33 = v86),
                    wType == (struct tagREDACCESSOR *)17
                 || (v52 ? (v60 = v52) : (v60 = *v88), v60 == (struct tagREDACCESSOR *)12)) )
              {
                v69 = v92;
                v25 = v52 == 0;
                v70 = v90;
                if ( v25 )
                  v69 = v93;
                if ( v90->wType == *(_WORD *)v69 )
                {
                  v74 = v85;
                }
                else
                {
                  v71 = operator new(v91);
                  if ( !v71 )
                    return -2147024882;
                  v72 = v70->wType;
                  if ( (_WORD)v72 == 13 )
                  {
                    memcpy(v71, v35, Size);
                    (*(void (__thiscall **)(_DWORD, int, const unsigned __int16 *))(*(_DWORD *)Sys + 20))(
                      *(_DWORD *)(*(_DWORD *)Sys + 20),
                      Sys,
                      v35);
                    v74 = (const char *)v71;
                  }
                  else
                  {
                    v73 = v92;
                    if ( !*(_DWORD *)Src )
                      v73 = v93;
                    if ( (*(int (__thiscall **)(_DWORD, LPVOID, int, _DWORD, size_t, size_t *, const unsigned __int16 *, void *, size_t, int, int *, _DWORD, _DWORD, _DWORD))(*(_DWORD *)g_pIDataConvert + 12))(
                           *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 12),
                           g_pIDataConvert,
                           v72,
                           *(unsigned __int16 *)v73,
                           Size,
                           &v104,
                           v35,
                           v71,
                           v91,
                           v97,
                           &v97,
                           0,
                           0,
                           0) < 0 )
                      goto LABEL_101;
                    v74 = (const char *)v71;
                    Size = v104;
                  }
                }
                v75 = Size;
                v76 = (_DWORD *)*((_DWORD *)a2 + 13);
                v77 = v76[25];
                v103 = (struct tagREDACCESSOR *)v90->wType;
                v78 = v92;
                if ( !*(_DWORD *)Src )
                  v78 = v93;
                wType = (struct tagREDACCESSOR *)*(unsigned __int16 *)v78;
                if ( v77 >= v76[24] )
                  return -2147467259;
                *(_DWORD *)(v76[23] + 16 * v77) = v99;
                v79 = (__int16)v103;
                *(_DWORD *)(v76[23] + 16 * v76[25] + 8) = v74;
                *(_DWORD *)(v76[23] + 16 * v76[25] + 4) = v75;
                v80 = v79 != (__int16)wType;
                v5 = 0;
                *(_DWORD *)(v76[23] + 16 * v76[25]++ + 12) = v80;
                v81 = v89;
                v11 = v94;
                *(_DWORD *)v89 = Size;
                *((_DWORD *)v81 + 1) = v74;
                v89 = (struct tagREDACCESSOR *)((char *)v81 + 8);
                v17 = v99 + 1;
              }
              else
              {
                wType = (struct tagREDACCESSOR *)v90->wType;
                if ( (_WORD)v102 == (_WORD)wType )
                {
                  if ( v52 )
                    v64 = dword_10051944[2 * (_DWORD)v52];
                  else
                    v64 = v33[9];
                  if ( Size > v64 )
                    return -2147467259;
                  memcpy(v55, v35, Size);
                  (*(void (__thiscall **)(_DWORD, int, const unsigned __int16 *))(*(_DWORD *)Sys + 20))(
                    *(_DWORD *)(*(_DWORD *)Sys + 20),
                    Sys,
                    v35);
                  v63 = v89;
                }
                else
                {
                  v90 = *(struct tagDBBINDING **)(*(_DWORD *)g_pIDataConvert + 12);
                  if ( v52 )
                  {
                    v61 = dword_10051944[2 * (_DWORD)v52];
                    v62 = v92;
                  }
                  else
                  {
                    v61 = v33[9];
                    v62 = v93;
                  }
                  v63 = v89;
                  v5 = ((int (__thiscall *)(struct tagDBBINDING *, LPVOID, struct tagREDACCESSOR *, _DWORD, size_t, size_t *, const unsigned __int16 *, struct tagREDACCESSOR *, int, int, int *, _DWORD, _DWORD, _DWORD))v90)(
                         v90,
                         g_pIDataConvert,
                         wType,
                         *(unsigned __int16 *)v62,
                         Size,
                         &v91,
                         v35,
                         v89,
                         v61,
                         v97,
                         &v97,
                         0,
                         0,
                         0);
                  if ( v5 < 0 )
                    return -2147467259;
                  Size = v91;
                }
                if ( v95 )
                  *v95 = v97;
                v65 = (struct tagREDACCESSOR **)Src;
                v66 = v92;
                if ( !*(_DWORD *)Src )
                  v66 = v93;
                if ( *(_WORD *)v66 == 11 )
                  *(_BYTE *)v63 = -(*(_BYTE *)v63 != 0);
                v67 = *v65;
                if ( *v65 )
                  v68 = *v65;
                else
                  v68 = *v88;
                if ( v68 == (struct tagREDACCESSOR *)10 )
                  goto LABEL_172;
                if ( !v67 )
                  v67 = *v88;
                if ( v67 == (struct tagREDACCESSOR *)9 )
LABEL_172:
                  *(_DWORD *)v103 = v91;
                v11 = v94;
                v17 = v99 + 1;
                v89 = (struct tagREDACCESSOR *)((char *)v63 + 4 * ((Size + 3) >> 2));
              }
            }
          }
          if ( *v95 == 3 )
          {
            v27 = v89;
            v28 = v99;
            v11 = v94;
            *(_DWORD *)v89 = 0;
            v89 = (struct tagREDACCESSOR *)((char *)v27 + 4);
            v17 = v28 + 1;
          }
          else
          {
            if ( *v95 != 13 )
              goto LABEL_53;
            v29 = v89;
            v30 = v99;
            v11 = v94;
            *(_DWORD *)v89 = 253;
            v89 = (struct tagREDACCESSOR *)((char *)v29 + 4);
            v17 = v30 + 1;
          }
        }
      }
    }
    else
    {
      return -2147217920;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1004a120  mov     edi, edi
0x1004a122  push    ebp
0x1004a123  mov     ebp, esp
0x1004a125  and     esp, 0FFFFFFF8h
0x1004a128  sub     esp, 54h
0x1004a12b  push    ebx
0x1004a12c  push    esi; void *
0x1004a12d  mov     esi, ecx
0x1004a12f  mov     [esp+5Ch+var_10], 0
0x1004a137  push    edi; unsigned int
0x1004a138  mov     [esp+60h+var_2C], esi
0x1004a13c  mov     eax, [esi+8]
0x1004a13f  test    eax, eax
0x1004a141  jz      short loc_1004A15A
0x1004a143  push    eax; Block
0x1004a144  call    ??3@YAXPAX@Z; operator delete(void *)
0x1004a149  add     esp, 4
0x1004a14c  mov     dword ptr [esi+8], 0
0x1004a153  mov     dword ptr [esi+4], 0
0x1004a15a  mov     ecx, [ebp+arg_0]
0x1004a15d  mov     ecx, [ecx+34h]
0x1004a160  add     ecx, 5Ch ; '\'; this
0x1004a163  call    ?Clear@CLVParamArray@@QAEJXZ; CLVParamArray::Clear(void)
0x1004a168  mov     ebx, eax
0x1004a16a  test    ebx, ebx
0x1004a16c  js      loc_1004AB31
0x1004a172  mov     edi, [ebp+arg_4]
0x1004a175  test    edi, edi
0x1004a177  jz      loc_1004AB31
0x1004a17d  cmp     dword ptr [edi+4], 0
0x1004a181  jz      loc_1004AB31
0x1004a187  cmp     dword ptr [edi], 0
0x1004a18a  jnz     short loc_1004A19C
0x1004a18c  mov     ebx, 80070057h
0x1004a191  mov     eax, ebx
0x1004a193  pop     edi
0x1004a194  pop     esi
0x1004a195  pop     ebx
0x1004a196  mov     esp, ebp
0x1004a198  pop     ebp
0x1004a199  retn    0Ch
0x1004a19c  mov     edx, [edi+8]
0x1004a19f  lea     eax, [esp+60h+var_10]
0x1004a1a3  push    eax; this
0x1004a1a4  mov     eax, [ebp+arg_0]
0x1004a1a7  mov     ecx, [eax+30h]
0x1004a1aa  call    ?GetItemOfExtBuffer@CExtBuffer@@QAGJKPAX@Z; CExtBuffer::GetItemOfExtBuffer(ulong,void *)
0x1004a1af  test    eax, eax
0x1004a1b1  js      loc_1004AB2C
0x1004a1b7  mov     edx, [esp+60h+var_10]
0x1004a1bb  mov     [esp+60h+var_24], edx
0x1004a1bf  test    edx, edx
0x1004a1c1  jz      loc_1004AB2C
0x1004a1c7  cmp     dword ptr [edx+0Ch], 3
0x1004a1cb  jz      short loc_1004A1DD
0x1004a1cd  mov     ebx, 80040E4Bh
0x1004a1d2  mov     eax, ebx
0x1004a1d4  pop     edi
0x1004a1d5  pop     esi
0x1004a1d6  pop     ebx
0x1004a1d7  mov     esp, ebp
0x1004a1d9  pop     ebp
0x1004a1da  retn    0Ch
0x1004a1dd  mov     eax, [esi]
0x1004a1df  xor     ecx, ecx
0x1004a1e1  test    eax, eax
0x1004a1e3  jz      short loc_1004A1ED
0x1004a1e5  mov     eax, [eax+28h]
0x1004a1e8  inc     ecx
0x1004a1e9  test    eax, eax
0x1004a1eb  jnz     short loc_1004A1E5
0x1004a1ed  cmp     [edx+24h], ecx
0x1004a1f0  jnb     short loc_1004A202
0x1004a1f2  mov     ebx, 80040E10h
0x1004a1f7  mov     eax, ebx
0x1004a1f9  pop     edi
0x1004a1fa  pop     esi
0x1004a1fb  pop     ebx
0x1004a1fc  mov     esp, ebp
0x1004a1fe  pop     ebp
0x1004a1ff  retn    0Ch
0x1004a202  mov     eax, [edx+1Ch]
0x1004a205  add     esi, 4
0x1004a208  imul    eax, [ebp+arg_8]
0x1004a20c  mov     ecx, [esp+60h+var_2C]; this
0x1004a210  push    esi; unsigned int *
0x1004a211  push    edi; struct tagDBPARAMS *
0x1004a212  push    edx; struct tagREDACCESSOR *
0x1004a213  mov     [esp+6Ch+var_14], eax
0x1004a217  call    ?DetermineSizeOfJetBuffer@CJetParameterList@@AAEJPAUtagREDACCESSOR@@PAUtagDBPARAMS@@AAK@Z; CJetParameterList::DetermineSizeOfJetBuffer(tagREDACCESSOR *,tagDBPARAMS *,ulong &)
0x1004a21c  mov     ebx, eax
0x1004a21e  test    ebx, ebx
0x1004a220  js      loc_1004AB31
0x1004a226  push    dword ptr [esi]; Size
0x1004a228  call    ??2@YAPAXI@Z; operator new(uint)
0x1004a22d  mov     edx, [esp+64h+var_2C]
0x1004a231  add     esp, 4
0x1004a234  mov     [esp+60h+var_40], eax
0x1004a238  mov     [edx+8], eax
0x1004a23b  test    eax, eax
0x1004a23d  jnz     short loc_1004A251
0x1004a23f  mov     [esi], eax
0x1004a241  mov     ebx, 8007000Eh
0x1004a246  mov     eax, ebx
0x1004a248  pop     edi
0x1004a249  pop     esi
0x1004a24a  pop     ebx
0x1004a24b  mov     esp, ebp
0x1004a24d  pop     ebp
0x1004a24e  retn    0Ch
0x1004a251  mov     eax, [ebp+arg_0]
0x1004a254  xor     esi, esi
0x1004a256  mov     edi, [eax+34h]
0x1004a259  mov     eax, [edx]
0x1004a25b  test    eax, eax
0x1004a25d  jz      short loc_1004A268
0x1004a25f  nop
0x1004a260  mov     eax, [eax+28h]
0x1004a263  inc     esi
0x1004a264  test    eax, eax
0x1004a266  jnz     short loc_1004A260
0x1004a268  cmp     esi, [edi+60h]
0x1004a26b  jbe     short loc_1004A2B9
0x1004a26d  mov     ecx, 10h
0x1004a272  mov     eax, esi
0x1004a274  mul     ecx
0x1004a276  mov     ecx, 0FFFFFFFFh
0x1004a27b  cmovb   eax, ecx
0x1004a27e  push    eax; Size
0x1004a27f  call    ??2@YAPAXI@Z; operator new(uint)
0x1004a284  mov     ebx, eax
0x1004a286  add     esp, 4
0x1004a289  test    ebx, ebx
0x1004a28b  jz      short loc_1004A241
0x1004a28d  mov     eax, [edi+64h]
0x1004a290  test    eax, eax
0x1004a292  jz      short loc_1004A2AF
0x1004a294  shl     eax, 4
0x1004a297  push    eax; Size
0x1004a298  push    dword ptr [edi+5Ch]; Src
0x1004a29b  push    ebx; void *
0x1004a29c  call    _memcpy
0x1004a2a1  add     esp, 0Ch
0x1004a2a4  push    dword ptr [edi+5Ch]; Block
0x1004a2a7  call    ??3@YAXPAX@Z; operator delete(void *)
0x1004a2ac  add     esp, 4
0x1004a2af  mov     edx, [esp+60h+var_2C]
0x1004a2b3  mov     [edi+60h], esi
0x1004a2b6  mov     [edi+5Ch], ebx
0x1004a2b9  xor     ebx, ebx
0x1004a2bb  mov     [esp+60h+var_C], 0Dh
0x1004a2c3  mov     edi, 1
0x1004a2c8  mov     esi, [edx]
0x1004a2ca  xor     ecx, ecx
0x1004a2cc  mov     [esp+60h+var_18], edi
0x1004a2d0  mov     [esp+60h+var_34], esi
0x1004a2d4  test    esi, esi
0x1004a2d6  jz      short loc_1004A2E8
0x1004a2d8  mov     eax, esi
0x1004a2da  nop     word ptr [eax+eax+00h]
0x1004a2e0  mov     eax, [eax+28h]
0x1004a2e3  inc     ecx
0x1004a2e4  test    eax, eax
0x1004a2e6  jnz     short loc_1004A2E0
0x1004a2e8  cmp     edi, ecx
0x1004a2ea  ja      loc_1004AB31
0x1004a2f0  xor     edx, edx
0x1004a2f2  mov     [esp+60h+var_30], 0
0x1004a2fa  xor     ecx, ecx
0x1004a2fc  mov     [esp+60h+var_28], 0
0x1004a304  mov     [esp+60h+var_50], edx
0x1004a308  mov     [esp+60h+Src], edx
0x1004a30c  mov     [esp+60h+var_20], edx
0x1004a310  mov     [esp+60h+Size], ecx
0x1004a314  mov     [esp+60h+var_38], ecx
0x1004a318  mov     [esp+60h+var_8], ecx
0x1004a31c  test    esi, esi
0x1004a31e  jz      short loc_1004A32F
0x1004a320  cmp     [esi], edi
0x1004a322  jz      short loc_1004A33F
0x1004a324  mov     esi, [esi+28h]
0x1004a327  mov     [esp+60h+var_34], esi
0x1004a32b  test    esi, esi
0x1004a32d  jnz     short loc_1004A320
0x1004a32f  mov     ebx, 80004005h
0x1004a334  mov     eax, ebx
0x1004a336  pop     edi
0x1004a337  pop     esi
0x1004a338  pop     ebx
0x1004a339  mov     esp, ebp
0x1004a33b  pop     ebp
0x1004a33c  retn    0Ch
0x1004a33f  cmp     dword ptr [esi+8], 1
0x1004a343  jz      short loc_1004A32F
0x1004a345  mov     eax, [esp+60h+var_24]
0x1004a349  xor     edi, edi
0x1004a34b  mov     ebx, [eax+24h]
0x1004a34e  mov     [esp+60h+var_10], ebx
0x1004a352  test    ebx, ebx
0x1004a354  jz      short loc_1004A32F
0x1004a356  nop     word ptr [eax+eax+00000000h]
0x1004a360  mov     esi, [esp+60h+var_24]
0x1004a364  mov     ebx, [esp+60h+var_18]
0x1004a368  imul    eax, edi, 34h ; '4'
0x1004a36b  cmp     ebx, [eax+esi+28h]
0x1004a36f  mov     esi, [esp+60h+var_34]
0x1004a373  mov     ebx, [esp+60h+var_10]
0x1004a377  jz      short loc_1004A38E
0x1004a379  inc     edi
0x1004a37a  cmp     edi, ebx
0x1004a37c  jb      short loc_1004A360
0x1004a37e  mov     ebx, 80004005h
0x1004a383  mov     eax, ebx
0x1004a385  pop     edi
0x1004a386  pop     esi
0x1004a387  pop     ebx
0x1004a388  mov     esp, ebp
0x1004a38a  pop     ebp
0x1004a38b  retn    0Ch
0x1004a38e  mov     edx, [esp+60h+var_24]
0x1004a392  xor     ebx, ebx
0x1004a394  imul    eax, edi, 34h ; '4'
0x1004a397  add     edx, 28h ; '('
0x1004a39a  add     eax, edx
0x1004a39c  mov     [esp+60h+var_3C], eax
0x1004a3a0  mov     edx, [eax+1Ch]
0x1004a3a3  test    dl, 1
0x1004a3a6  mov     [esp+60h+var_10], edx
0x1004a3aa  mov     edx, [esp+60h+var_50]
0x1004a3ae  jz      short loc_1004A3C8
0x1004a3b0  mov     esi, [ebp+arg_4]
0x1004a3b3  mov     edx, [eax+4]
0x1004a3b6  add     edx, [esi]
0x1004a3b8  add     edx, [esp+60h+var_14]
0x1004a3bc  mov     esi, [esp+60h+var_34]
0x1004a3c0  mov     [esp+60h+var_50], edx
0x1004a3c4  mov     [esp+60h+Src], edx
0x1004a3c8  test    byte ptr [eax+1Ch], 2
0x1004a3cc  jz      short loc_1004A3E2
0x1004a3ce  mov     esi, [ebp+arg_4]
0x1004a3d1  mov     eax, [eax+8]
0x1004a3d4  add     eax, [esi]
0x1004a3d6  add     eax, [esp+60h+var_14]
0x1004a3da  mov     esi, [esp+60h+var_34]
0x1004a3de  mov     [esp+60h+var_30], eax
0x1004a3e2  test    byte ptr [esp+60h+var_10], 4
0x1004a3e7  jz      short loc_1004A401
0x1004a3e9  mov     eax, [esp+60h+var_3C]
0x1004a3ed  mov     esi, [ebp+arg_4]
0x1004a3f0  mov     eax, [eax+0Ch]
0x1004a3f3  add     eax, [esi]
0x1004a3f5  add     eax, [esp+60h+var_14]
0x1004a3f9  mov     esi, [esp+60h+var_34]
0x1004a3fd  mov     [esp+60h+var_28], eax
0x1004a401  test    edx, edx
0x1004a403  jz      loc_1004AB0E
0x1004a409  cmp     [esp+60h+var_28], ecx
0x1004a40d  jz      short loc_1004A45B
0x1004a40f  mov     eax, [esp+60h+var_28]
0x1004a413  cmp     dword ptr [eax], 3
0x1004a416  jnz     short loc_1004A433
0x1004a418  mov     eax, [esp+60h+var_40]
0x1004a41c  mov     edi, [esp+60h+var_18]
0x1004a420  mov     edx, [esp+60h+var_2C]
0x1004a424  mov     [eax], ecx
0x1004a426  add     eax, 4
0x1004a429  mov     [esp+60h+var_40], eax
0x1004a42d  inc     edi
0x1004a42e  jmp     loc_1004A2C8
0x1004a433  mov     eax, [esp+60h+var_28]
0x1004a437  cmp     dword ptr [eax], 0Dh
0x1004a43a  jnz     short loc_1004A45B
0x1004a43c  mov     eax, [esp+60h+var_40]
0x1004a440  mov     edi, [esp+60h+var_18]
0x1004a444  mov     edx, [esp+60h+var_2C]
0x1004a448  mov     dword ptr [eax], 0FDh
0x1004a44e  add     eax, 4
0x1004a451  mov     [esp+60h+var_40], eax
0x1004a455  inc     edi
0x1004a456  jmp     loc_1004A2C8
0x1004a45b  mov     ebx, [esp+60h+var_3C]
0x1004a45f  movzx   eax, word ptr [ebx+30h]
0x1004a463  cmp     word ptr [esp+60h+var_C], ax
0x1004a468  mov     [esp+60h+var_10], eax
0x1004a46c  mov     eax, [esp+60h+var_30]
0x1004a470  jnz     short loc_1004A4AE
0x1004a472  lea     ecx, [esp+60h+Size]; this
0x1004a476  push    ecx; unsigned int *
0x1004a477  push    eax; unsigned int *
0x1004a478  lea     eax, [esp+68h+Src]
0x1004a47c  push    eax; void **
0x1004a47d  push    ebx; struct tagDBBINDING *
0x1004a47e  call    ?ReadStorageParameter@CJetParameterList@@QAEJPAUtagDBBINDING@@PAPAXPAK2@Z; CJetParameterList::ReadStorageParameter(tagDBBINDING *,void * *,ulong *,ulong *)
0x1004a483  mov     ebx, eax
0x1004a485  test    ebx, ebx
0x1004a487  js      loc_1004AAF1
0x1004a48d  mov     ecx, [esp+60h+Size]
0x1004a491  mov     edx, esi
0x1004a493  mov     [esp+60h+var_48], edi
0x1004a497  mov     eax, esi
  ... truncated ...
```
