# AccessSpecRead

- ea: `0x10018b90`
- end: `0x100197c5`
- name: `AccessSpecRead`
- size: `3125`
- prototype: `int __stdcall(int, JET_SESID sesid, int, JET_TABLEID tableid, JET_TABLEID, int, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation`

## callers

- `0x1001c250`

## callees

- `0x1000a1f0`
- `0x1000a260`
- `0x1000ad60`
- `0x1000b070`
- `0x1000b200`
- `0x1000f030`
- `0x10018b90`
- `0x1001b5d0`
- `0x1001baf0`
- `0x10029810`
- `0x1002b61a`
- `0x1002b620`
- `0x1002b62c`
- `0x1002b632`
- `0x1002b638`
- `0x1002b63e`
- `0x1002b644`
- `0x1002b81a`
- `0x1002c253`
- `0x1002c490`

## pseudocode

```c
JET_ERR __stdcall AccessSpecRead(
        int a1,
        JET_SESID sesid,
        int a3,
        JET_TABLEID tableid,
        JET_TABLEID a5,
        void *a6,
        int a7)
{
  wchar_t v7; // bp
  int v8; // edi
  JET_SESID v9; // esi
  JET_ERR result; // eax
  int v11; // ebx
  int *v12; // eax
  unsigned int v13; // ecx
  int v14; // ecx
  _BYTE *v15; // ecx
  int v16; // edx
  __int16 v17; // ax
  __int16 v18; // ax
  wchar_t *v19; // ecx
  int v20; // edx
  wchar_t v21; // ax
  int v22; // edx
  __int16 v23; // ax
  wchar_t v24; // ax
  int v25; // edx
  __int16 v26; // ax
  __int16 v27; // si
  wchar_t v28; // dx
  wchar_t v29; // ax
  int v30; // eax
  _DWORD *v31; // esi
  unsigned int v32; // ecx
  int v33; // esi
  wchar_t *v34; // edi
  const wchar_t *v35; // ecx
  int v36; // edx
  bool v37; // zf
  wchar_t *v38; // esi
  int v39; // eax
  wchar_t *v40; // edi
  int v41; // edx
  wchar_t *v42; // ecx
  int v43; // ebx
  wchar_t *v44; // esi
  int v45; // esi
  const __m128i *v46; // ebx
  int v47; // eax
  JET_TABLEID v48; // ebp
  int v49; // edi
  JET_COLUMNID *v50; // esi
  JET_COLUMNID v51; // eax
  _DWORD *v52; // edi
  int v53; // esi
  unsigned int v54; // edx
  JET_ERR v55; // edx
  unsigned int v56; // eax
  __int16 v57; // ax
  unsigned int v58; // eax
  int v59; // ecx
  _DWORD *v60; // ebx
  const wchar_t *v61; // edi
  const wchar_t *v62; // ebp
  int *v63; // eax
  _DWORD *v64; // edx
  unsigned __int16 v65; // si
  int v66; // eax
  int v67; // ecx
  char *v68; // eax
  char *v69; // esi
  int v70; // ecx
  __int16 v71; // ax
  __int16 v72; // ax
  int v73; // ebx
  int v74; // eax
  int v75; // esi
  int v76; // esi
  int v77; // ecx
  int v78; // edx
  __int16 v79; // dx
  __int16 v80; // ax
  __int16 v81; // si
  __int16 v82; // cx
  int v83; // esi
  int v84; // esi
  const wchar_t *v85; // eax
  int v86; // esi
  int v87; // esi
  unsigned __int8 v88; // [esp+13h] [ebp-11Dh] BYREF
  int v89; // [esp+14h] [ebp-11Ch]
  int v90; // [esp+18h] [ebp-118h]
  void *v91; // [esp+1Ch] [ebp-114h]
  int v92; // [esp+20h] [ebp-110h]
  char v93; // [esp+27h] [ebp-109h] BYREF
  int v94; // [esp+28h] [ebp-108h]
  int v95; // [esp+2Ch] [ebp-104h] BYREF
  int v96; // [esp+30h] [ebp-100h] BYREF
  int v97; // [esp+34h] [ebp-FCh]
  void *pvData; // [esp+38h] [ebp-F8h]
  unsigned int pcbActual; // [esp+3Ch] [ebp-F4h] BYREF
  int v100; // [esp+40h] [ebp-F0h]
  int v101; // [esp+44h] [ebp-ECh]
  int v102; // [esp+48h] [ebp-E8h]
  int v103; // [esp+4Ch] [ebp-E4h] BYREF
  wchar_t v104[2]; // [esp+50h] [ebp-E0h] BYREF
  int v105; // [esp+54h] [ebp-DCh]
  int v106; // [esp+58h] [ebp-D8h]
  _DWORD *v107; // [esp+5Ch] [ebp-D4h]
  char v108[4]; // [esp+60h] [ebp-D0h] BYREF
  JET_COLUMNID columnid; // [esp+64h] [ebp-CCh]
  int v110; // [esp+68h] [ebp-C8h]
  wchar_t v111[8]; // [esp+78h] [ebp-B8h] BYREF
  _BYTE v112[16]; // [esp+88h] [ebp-A8h] BYREF
  _BYTE v113[16]; // [esp+98h] [ebp-98h] BYREF
  wchar_t pszSrc[66]; // [esp+A8h] [ebp-88h] BYREF

  v94 = a1;
  v7 = 0;
  v8 = a7;
  pvData = a6;
  v97 = a7;
  v88 = 0;
  v93 = 0;
  v96 = 0;
  v95 = 0;
  v91 = 0;
  v90 = 0;
  pcbActual = 0;
  v103 = 0;
  v89 = 0;
  v92 = 0;
  v105 = 0;
  v106 = 0;
  v101 = 0;
  v107 = 0;
  v102 = 0;
  v100 = 0;
  InitializeSpec(a7);
  v9 = sesid;
  result = JetSetCurrentIndex(sesid, tableid, L"PrimaryKey");
  if ( !result )
  {
    result = JetMakeKey(sesid, tableid, pvData, 2 * wcslen((const unsigned __int16 *)pvData), 1u);
    if ( !result )
    {
      result = JetSeek(sesid, tableid, 1u);
      if ( !result )
      {
        v11 = 0;
        while ( 1 )
        {
          result = JetGetTableColumnInfo(v9, tableid, (&off_1003E680)[3 * v11], v108, 24, 0);
          if ( result )
          {
            if ( v11 != 12 )
              return result;
            *(_DWORD *)(v8 + 32) = 0;
          }
          else
          {
            switch ( v110 )
            {
              case 1:
                v12 = (int *)&v88;
                v88 = 0;
                v13 = 1;
                v91 = &v88;
                v90 = 1;
                break;
              case 2:
                v12 = (int *)&v93;
                v93 = 0;
                v13 = 1;
                v91 = &v93;
                v90 = 1;
                break;
              case 3:
                v12 = &v95;
                v95 = 0;
                v13 = 2;
                v91 = &v95;
                v90 = 2;
                break;
              case 4:
                v12 = &v96;
                v96 = 0;
                v13 = 4;
                v91 = &v96;
                v90 = 4;
                break;
              case 10:
                v12 = (int *)pszSrc;
                v13 = 130;
                v91 = pszSrc;
                v90 = 130;
                pszSrc[0] = 0;
                break;
              default:
                v13 = v90;
                v12 = (int *)v91;
                break;
            }
            result = JetRetrieveColumn(v9, tableid, columnid, v12, v13, &pcbActual, 0, 0);
            if ( result < 0 )
              return result;
            v14 = pcbActual;
            if ( result == 1004 )
              v14 = 0;
            pcbActual = v14;
            switch ( v11 )
            {
              case 0:
                if ( v14 <= 0 )
                  v104[0] = 0;
                else
                  v104[0] = pszSrc[0];
                v104[1] = 0;
                goto LABEL_84;
              case 1:
                v15 = v113;
                v16 = 8;
                if ( v88 )
                {
                  while ( v16 != -2147483638 )
                  {
                    v18 = *(_WORD *)&v15[(char *)L"yyyy" - v113];
                    if ( !v18 )
                      break;
                    *(_WORD *)v15 = v18;
                    v15 += 2;
                    if ( !--v16 )
                    {
                      *((_WORD *)v15 - 1) = 0;
                      goto LABEL_84;
                    }
                  }
                }
                else
                {
                  while ( v16 != -2147483638 )
                  {
                    v17 = *(_WORD *)&v15[(char *)L"yy" - v113];
                    if ( !v17 )
                      break;
                    *(_WORD *)v15 = v17;
                    v15 += 2;
                    if ( !--v16 )
                    {
                      *((_WORD *)v15 - 1) = 0;
                      goto LABEL_84;
                    }
                  }
                }
                goto LABEL_28;
              case 2:
                v19 = v111;
                v20 = 8;
                if ( !v88 )
                {
                  do
                  {
                    if ( v20 == -2147483638 )
                      goto LABEL_38;
                    v21 = *(wchar_t *)((char *)v19 + (char *)L"d" - (char *)v111);
                    if ( !v21 )
                      goto LABEL_38;
                    *v19++ = v21;
                    --v20;
                  }
                  while ( v20 );
                  --v19;
LABEL_38:
                  *v19 = 0;
                  v15 = v112;
                  v22 = 8;
                  do
                  {
                    if ( v22 == -2147483638 )
                      goto LABEL_28;
                    v23 = *(_WORD *)&v15[(char *)L"m" - v112];
                    if ( !v23 )
                      goto LABEL_28;
                    *(_WORD *)v15 = v23;
                    v15 += 2;
                    --v22;
                  }
                  while ( v22 );
                  *((_WORD *)v15 - 1) = 0;
                  goto LABEL_84;
                }
                while ( v20 != -2147483638 )
                {
                  v24 = *(wchar_t *)((char *)v19 + (char *)L"dd" - (char *)v111);
                  if ( !v24 )
                    break;
                  *v19++ = v24;
                  if ( !--v20 )
                  {
                    --v19;
                    break;
                  }
                }
                *v19 = 0;
                v15 = v112;
                v25 = 8;
                do
                {
                  if ( v25 == -2147483638 || (v26 = *(_WORD *)&v15[(char *)L"mm" - v112]) == 0 )
                  {
LABEL_28:
                    *(_WORD *)v15 = 0;
                    goto LABEL_84;
                  }
                  *(_WORD *)v15 = v26;
                  v15 += 2;
                  --v25;
                }
                while ( v25 );
                *((_WORD *)v15 - 1) = 0;
                goto LABEL_84;
              case 3:
                v27 = v95;
                v89 = (unsigned __int16)v95;
                goto LABEL_85;
              case 4:
                v28 = pszSrc[0];
                if ( v14 <= 0 )
                  v29 = 0;
                else
                  v29 = pszSrc[0];
                *(_WORD *)(v8 + 730) = v29;
                if ( v14 <= 0 )
                  *(_WORD *)(v8 + 724) = 0;
                else
                  *(_WORD *)(v8 + 724) = v28;
                goto LABEL_84;
              case 5:
                if ( v14 <= 0 )
                  *(_WORD *)(v8 + 56) = 0;
                else
                  *(_WORD *)(v8 + 56) = pszSrc[0];
                goto LABEL_84;
              case 6:
                v30 = (unsigned __int16)v95;
                v31 = (_DWORD *)(v8 + 36);
                *(_DWORD *)(v8 + 36) = (unsigned __int16)v95;
                if ( v30 )
                {
                  if ( v30 == 1 )
                    *v31 = 0;
                }
                else
                {
                  *v31 = 1;
                }
                if ( TextDefaultDetectCP(0, v8 + 36) )
                  *v31 = *(_DWORD *)(v94 + 864);
                else
                  *(_DWORD *)(v94 + 864) = *v31;
                goto LABEL_84;
              case 7:
                v103 = v96;
                goto LABEL_84;
              case 10:
                if ( v14 <= 0 )
                  *(_WORD *)(v8 + 72) = 0;
                else
                  *(_WORD *)(v8 + 72) = pszSrc[0];
                goto LABEL_84;
              case 11:
                v32 = v14 & 0xFFFFFFFE;
                if ( v32 >= 0x82 )
                  goto LABEL_192;
                v33 = v97;
                *(wchar_t *)((char *)pszSrc + v32) = 0;
                v34 = (wchar_t *)(v8 + 340);
                v35 = L"h";
                v36 = 65;
                v37 = *(_DWORD *)(v33 + 76) == 0;
                v38 = v34;
                if ( !v37 )
                  v35 = L"hh";
                break;
              case 12:
                v39 = 0;
                if ( v14 )
                  v39 = v96;
                *(_DWORD *)(v8 + 32) = v39;
                goto LABEL_84;
              default:
                goto LABEL_84;
            }
            while ( v36 != -2147483581 && *v35 )
            {
              *v38++ = *v35++;
              if ( !--v36 )
              {
                --v38;
                break;
              }
            }
            *v38 = 0;
            StringCchCatW(v34, 0x41u, pszSrc);
            StringCchCatW(v34, 0x41u, L"nn");
            StringCchCatW(v34, 0x41u, pszSrc);
            StringCchCatW(v34, 0x41u, L"ss");
            v7 = pszSrc[0];
            v8 = v97;
          }
LABEL_84:
          v27 = v89;
LABEL_85:
          if ( ++v11 > 12 )
            break;
          v9 = sesid;
        }
        v40 = (wchar_t *)(v8 + 210);
        v41 = 65;
        v42 = v40;
        v43 = 3 * v27;
        v44 = &v111[8 * (unsigned __int8)byte_1003E774[v43]];
        while ( v41 != -2147483581 && *v44 )
        {
          *v42++ = *v44++;
          if ( !--v41 )
          {
            --v42;
            break;
          }
        }
        *v42 = 0;
        StringCchCatW(v40, 0x41u, v104);
        StringCchCatW(v40, 0x41u, &v111[8 * (unsigned __int8)byte_1003E775[v43]]);
        StringCchCatW(v40, 0x41u, v104);
        StringCchCatW(v40, 0x41u, &v111[8 * (unsigned __int8)byte_1003E776[v43]]);
        v45 = v97;
        v46 = (const __m128i *)(v97 + 748);
        ParseDateTimePicture(v40, v97 + 748);
        v47 = v94;
        *(_WORD *)(v45 + 752) = v7;
        v48 = a5;
        *(_DWORD *)(v45 + 820) = 1;
        *(_DWORD *)(v45 + 52) = *(unsigned __int8 *)(v47 + 856);
        result = JetSetCurrentIndex(sesid, a5, L"PrimaryKey");
        if ( !result )
        {
          result = JetMakeKey(sesid, a5, &v103, 4u, 1u);
          if ( !result )
          {
            if ( JetSeek(sesid, a5, 8u) >= 0 )
            {
              v49 = 0;
              v50 = &::columnid;
              while ( 1 )
              {
                result = JetGetTableColumnInfo(sesid, a5, *(v50 - 2), v108, 24, 0);
                if ( result )
                {
                  if ( (unsigned int)(v49 - 5) > 1 )
                    return result;
                  v51 = 0;
                  columnid = 0;
                }
                else
                {
                  v51 = columnid;
                }
                *v50 = v51;
                ++v49;
                v50 += 3;
                if ( (int)v50 > (int)&dword_1003E770 )
                {
                  v52 = 0;
                  while ( 1 )
                  {
                    v53 = 0;
                    while ( 2 )
                    {
                      switch ( dword_1003E724[3 * v53] )
                      {
                        case 1:
                          v88 = 0;
                          v54 = 1;
                          v91 = &v88;
                          v90 = 1;
                          break;
                        case 3:
                          v95 = 0;
                          v54 = 2;
                          v91 = &v95;
                          v90 = 2;
                          break;
                        case 4:
                          v96 = 0;
                          v54 = 4;
                          v91 = &v96;
                          v90 = 4;
                          break;
                        case 10:
                          v54 = 130;
                          pszSrc[0] = 0;
                          v48 = a5;
                          v91 = pszSrc;
                          v90 = 130;
                          break;
                        default:
                          v54 = v90;
                          break;
                      }
                      result = JetRetrieveColumn(sesid, v48, *(&::columnid + 3 * v53), v91, v54, &pcbActual, 0, 0);
                      v55 = result;
                      if ( result < 0 )
                      {
                        if ( v53 == 5 )
                        {
                          v101 = 0;
                        }
                        else
                        {
                          if ( v53 != 6 )
                            return result;
                          v102 = 0;
                        }
                      }
                      v56 = pcbActual;
                      if ( v55 == 1004 )
                        v56 = 0;
                      pcbActual = v56;
                      switch ( v53 )
                      {
                        case 0:
                          v57 = v95;
                          v92 = (unsigned __int16)v95;
                          goto LABEL_139;
                        case 1:
                          if ( v56 <= 0x80 )
                          {
                            v58 = v56 & 0xFFFFFFFE;
                            if ( v58 >= 0x82 )
LABEL_192:
                              __report_rangecheckfailure();
                            *(wchar_t *)((char *)pszSrc + v58) = 0;
                          }
                          else
                          {
                            pszSrc[64] = 0;
                          }
LABEL_138:
                          v57 = v92;
LABEL_139:
                          if ( ++v53 <= 6 )
                            continue;
                          if ( v57 >= 18 )
                            return -1003;
                          v68 = (char *)MemAllocate(0xF8u);
                          v69 = v68;
                          if ( !v68 )
                            return -1011;
                          memset(v68, 0, 0xF8u);
                          v70 = (__int16)v92;
                          *((_DWORD *)v69 + 3) = (__int16)v105;
                          *((_DWORD *)v69 + 4) = (unsigned __int16)v106;
                          *((_DWORD *)v69 + 2) = v70;
                          *((_DWORD *)v69 + 5) = v101 != 0;
                          v71 = v102;
                          *((_DWORD *)v69 + 6) = v102;
                          if ( v71 < 0 )
                            *((_DWORD *)v69 + 7) = 1;
                          MakeValidFieldName(v94, pszSrc, (wchar_t *)v69 + 18, 0x41u, 0x4B0u);
                          v72 = v92;
                          if ( (_WORD)v92 == 8 )
                          {
                            *(__m128i *)(v69 + 172) = _mm_loadu_si128(v46);
                            *(__m128i *)(v69 + 188) = _mm_loadu_si128(v46 + 1);
                            *(__m128i *)(v69 + 204) = _mm_loadu_si128(v46 + 2);
                            *(__m128i *)(v69 + 220) = _mm_loadu_si128(v46 + 3);
                            *(_QWORD *)(v69 + 236) = v46[4].m128i_i64[0];
                          }
                          else if ( (_WORD)v92 == 16 )
                          {
                            *((_WORD *)v69 + 122) = 7170;
                          }
                          if ( *(_BYTE *)(v94 + 856) != 1 && v72 == 10 )
                            *((_DWORD *)v69 + 3) = 255;
                          if ( *((_DWORD *)v69 + 5) && *(_DWORD *)(v97 + 52) == 1 )
                          {
                            MemFree(v69);
                          }
                          else
                          {
                            if ( v52 )
                              *v52 = v69;
                            else
                              *(_DWORD *)(v97 + 8) = v69;
                            ++v100;
                            v52 = v69;
                          }
                          if ( JetMove(sesid, v48, 1, 0) < 0 )
                            goto LABEL_123;
                          break;
                        case 2:
                          if ( v96 != v103 )
                            goto LABEL_123;
                          goto LABEL_138;
                        case 3:
                          v106 = (unsigned __int16)v95;
                          goto LABEL_138;
                        case 4:
                          v105 = (unsigned __int16)v95;
                          goto LABEL_138;
                        case 5:
                          v101 = v88;
                          goto LABEL_138;
                        case 6:
                          v67 = v96;
                          if ( !v56 )
                            v67 = 0;
                          v102 = v67;
                          goto LABEL_138;
                        default:
                          goto LABEL_138;
                      }
                      break;
                    }
                  }
                }
              }
            }
LABEL_123:
            v59 = v97;
            v60 = 0;
            v61 = 0;
            if ( *(_DWORD *)(v97 + 8) )
            {
              v62 = 0;
              do
              {
                v63 = *(int **)(v59 + 8);
                v64 = 0;
                v65 = -538;
                if ( v63 )
                {
                  do
                  {
                    if ( v63[4] < (unsigned int)v65 )
                    {
                      v65 = *((_WORD *)v63 + 8);
                      v62 = (const wchar_t *)v63;
                      v107 = v64;
                    }
                    v64 = v63;
                    v63 = (int *)*v63;
                  }
                  while ( v63 );
                  v59 = v97;
                }
                v66 = *(_DWORD *)v62;
                if ( v107 )
                  *v107 = v66;
                else
                  *(_DWORD *)(v59 + 8) = v66;
                *(_DWORD *)v62 = 0;
                if ( v60 )
                  *v60 = v62;
                else
                  v61 = v62;
                v60 = v62;
              }
              while ( *(_DWORD *)(v59 + 8) );
              v48 = a5;
            }
            v73 = *(_DWORD *)(v59 + 52);
            v74 = v100;
            *(_DWORD *)(v59 + 8) = v61;
            *(_DWORD *)(v59 + 12) = v74;
            if ( v73 == 1 )
            {
              *(_WORD *)(v59 + 56) = 44;
              if ( v61 )
              {
                v76 = 0;
                while ( 1 )
                {
                  v77 = *((_DWORD *)v61 + 3);
                  if ( !v77 )
                    break;
                  v76 += v77;
                  if ( v76 > 64998 )
                  {
                    v86 = *(_DWORD *)(v94 + 4);
                    JetCloseTable(*(_DWORD *)(v86 + 40), tableid);
                    JetCloseTable(*(_DWORD *)(v86 + 40), v48);
                    v85 = v61 + 18;
                    goto LABEL_188;
                  }
                  v78 = *(_DWORD *)v61;
                  if ( *(_DWORD *)v61 && *(_DWORD *)(v78 + 16) - *((_DWORD *)v61 + 4) - v77 < 0 )
                  {
                    v84 = *(_DWORD *)(v94 + 4);
                    JetCloseTable(*(_DWORD *)(v84 + 40), tableid);
                    JetCloseTable(*(_DWORD *)(v84 + 40), v48);
                    v85 = (const wchar_t *)(*(_DWORD *)v61 + 36);
LABEL_188:
                    ErrorSetExtendedInfoSz1Sz2(-8236, (STRSAFE_LPCWSTR)pvData, v85, 2);
                    return -5402;
                  }
                  v61 = *(const wchar_t **)v61;
                  if ( !v78 )
                  {
                    v59 = v97;
                    goto LABEL_179;
                  }
                }
                v87 = *(_DWORD *)(v94 + 4);
                JetCloseTable(*(_DWORD *)(v87 + 40), tableid);
                JetCloseTable(*(_DWORD *)(v87 + 40), v48);
                ErrorSetExtendedInfoSz1Sz2(-8238, (STRSAFE_LPCWSTR)pvData, v61 + 18, 2);
                return -5401;
              }
              else
              {
                v75 = *(_DWORD *)(v94 + 4);
                JetCloseTable(*(_DWORD *)(v75 + 40), tableid);
                JetCloseTable(*(_DWORD *)(v75 + 40), v48);
                ErrorSetExtendedInfoSz1(-8237, (STRSAFE_LPCWSTR)pvData, 0);
                return -5400;
              }
            }
            else
            {
LABEL_179:
              if ( !v73
                && ((v79 = *(_WORD *)(v59 + 730), v80 = *(_WORD *)(v59 + 56), v79 == v80)
                 || (v81 = *(_WORD *)(v59 + 724), v81 == v80)
                 || (v82 = *(_WORD *)(v59 + 72), v82 == v79)
                 || v82 == v81
                 || v82 == v80) )
              {
                v83 = *(_DWORD *)(v94 + 4);
                JetCloseTable(*(_DWORD *)(v83 + 40), tableid);
                JetCloseTable(*(_DWORD *)(v83 + 40), v48);
                return -5406;
              }
              else
              {
                return 0;
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x10018b90  sub     esp, 120h
0x10018b96  mov     eax, ___security_cookie
0x10018b9b  xor     eax, esp
0x10018b9d  mov     [esp+120h+var_4], eax
0x10018ba4  mov     eax, [esp+120h+arg_0]
0x10018bab  xor     ecx, ecx
0x10018bad  push    ebx
0x10018bae  push    ebp
0x10018baf  push    esi
0x10018bb0  mov     [esp+12Ch+var_108], eax
0x10018bb4  xor     esi, esi
0x10018bb6  mov     eax, [esp+12Ch+arg_14]
0x10018bbd  xor     ebp, ebp
0x10018bbf  push    edi
0x10018bc0  mov     edi, [esp+130h+arg_18]
0x10018bc7  mov     [esp+130h+pvData], eax
0x10018bcb  xor     eax, eax
0x10018bcd  push    edi
0x10018bce  mov     [esp+134h+var_FC], edi
0x10018bd2  mov     [esp+134h+var_11D], 0
0x10018bd7  mov     [esp+134h+var_109], 0
0x10018bdc  mov     [esp+134h+var_100], 0
0x10018be4  mov     [esp+134h+var_104], 0
0x10018bec  mov     [esp+134h+var_114], 0
0x10018bf4  mov     [esp+134h+var_118], 0
0x10018bfc  mov     [esp+134h+pcbActual], 0
0x10018c04  mov     [esp+134h+var_E4], 0
0x10018c0c  mov     [esp+134h+var_11C], esi
0x10018c10  mov     [esp+134h+var_110], eax
0x10018c14  mov     [esp+134h+var_DC], eax
0x10018c18  mov     [esp+134h+var_D8], eax
0x10018c1c  mov     [esp+134h+var_EC], ecx
0x10018c20  mov     [esp+134h+var_D4], eax
0x10018c24  mov     [esp+134h+var_E8], eax
0x10018c28  mov     [esp+134h+var_F0], eax
0x10018c2c  call    _InitializeSpec@4; InitializeSpec(x)
0x10018c31  mov     ebx, [esp+130h+tableid]
0x10018c38  mov     esi, [esp+130h+sesid]
0x10018c3f  push    offset aPrimarykey; "PrimaryKey"
0x10018c44  push    ebx
0x10018c45  push    esi
0x10018c46  call    _JetSetCurrentIndex@12; JetSetCurrentIndex(x,x,x)
0x10018c4b  test    eax, eax
0x10018c4d  jnz     loc_100197A5
0x10018c53  mov     ecx, [esp+130h+pvData]
0x10018c57  lea     edx, [ecx+2]
0x10018c5a  lea     ebx, [ebx+0]
0x10018c60  mov     ax, [ecx]
0x10018c63  add     ecx, 2
0x10018c66  test    ax, ax
0x10018c69  jnz     short loc_10018C60
0x10018c6b  sub     ecx, edx
0x10018c6d  sar     ecx, 1
0x10018c6f  push    1; grbit
0x10018c71  lea     eax, [ecx+ecx]
0x10018c74  push    eax; cbData
0x10018c75  push    [esp+138h+pvData]; pvData
0x10018c79  push    ebx; tableid
0x10018c7a  push    esi; sesid
0x10018c7b  call    _JetMakeKey@20; JetMakeKey(x,x,x,x,x)
0x10018c80  test    eax, eax
0x10018c82  jnz     loc_100197A5
0x10018c88  push    1; grbit
0x10018c8a  push    ebx; tableid
0x10018c8b  push    esi; sesid
0x10018c8c  call    _JetSeek@12; JetSeek(x,x,x)
0x10018c91  test    eax, eax
0x10018c93  jnz     loc_100197A5
0x10018c99  xor     ebx, ebx
0x10018c9b  jmp     short loc_10018CA0
0x10018ca0  push    0
0x10018ca2  push    18h
0x10018ca4  lea     eax, [esp+138h+var_D0]
0x10018ca8  push    eax
0x10018ca9  lea     eax, [ebx+ebx*2]
0x10018cac  push    off_1003E680[eax*4]; "DateDelim"
0x10018cb3  push    [esp+140h+tableid]
0x10018cba  push    esi
0x10018cbb  call    _JetGetTableColumnInfo@24; JetGetTableColumnInfo(x,x,x,x,x,x)
0x10018cc0  test    eax, eax
0x10018cc2  jz      short loc_10018CD9
0x10018cc4  cmp     ebx, 0Ch
0x10018cc7  jnz     loc_100197A5
0x10018ccd  mov     dword ptr [edi+20h], 0
0x10018cd4  jmp     def_10018DBB; jumptable 10018DBB default case, cases 8,9
0x10018cd9  mov     eax, [esp+130h+var_C8]
0x10018cdd  dec     eax; switch 10 cases
0x10018cde  cmp     eax, 9
0x10018ce1  ja      def_10018CE7; jumptable 10018CE7 default case, cases 5-9
0x10018ce7  jmp     ds:jpt_10018CE7[eax*4]; switch jump
0x10018cee  lea     eax, [esp+130h+var_11D]; jumptable 10018CE7 case 1
0x10018cf2  mov     [esp+130h+var_11D], 0
0x10018cf7  mov     ecx, 1
0x10018cfc  mov     [esp+130h+var_114], eax
0x10018d00  mov     [esp+130h+var_118], ecx
0x10018d04  jmp     short loc_10018D7C
0x10018d06  lea     eax, [esp+130h+var_109]; jumptable 10018CE7 case 2
0x10018d0a  mov     [esp+130h+var_109], 0
0x10018d0f  mov     ecx, 1
0x10018d14  mov     [esp+130h+var_114], eax
0x10018d18  mov     [esp+130h+var_118], ecx
0x10018d1c  jmp     short loc_10018D7C
0x10018d1e  lea     eax, [esp+130h+var_104]; jumptable 10018CE7 case 3
0x10018d22  mov     [esp+130h+var_104], 0
0x10018d2a  mov     ecx, 2
0x10018d2f  mov     [esp+130h+var_114], eax
0x10018d33  mov     [esp+130h+var_118], ecx
0x10018d37  jmp     short loc_10018D7C
0x10018d39  lea     eax, [esp+130h+var_100]; jumptable 10018CE7 case 4
0x10018d3d  mov     [esp+130h+var_100], 0
0x10018d45  mov     ecx, 4
0x10018d4a  mov     [esp+130h+var_114], eax
0x10018d4e  mov     [esp+130h+var_118], ecx
0x10018d52  jmp     short loc_10018D7C
0x10018d54  lea     eax, [esp+130h+pszSrc]; jumptable 10018CE7 case 10
0x10018d5b  mov     ecx, 82h
0x10018d60  xor     edx, edx
0x10018d62  mov     [esp+130h+var_114], eax
0x10018d66  mov     [esp+130h+var_118], ecx
0x10018d6a  mov     [esp+130h+pszSrc], dx
0x10018d72  jmp     short loc_10018D7C
0x10018d74  mov     ecx, [esp+130h+var_118]; jumptable 10018CE7 default case, cases 5-9
0x10018d78  mov     eax, [esp+130h+var_114]
0x10018d7c  push    0; pretinfo
0x10018d7e  push    0; grbit
0x10018d80  lea     edx, [esp+138h+pcbActual]
0x10018d84  push    edx; pcbActual
0x10018d85  push    ecx; cbData
0x10018d86  push    eax; pvData
0x10018d87  push    [esp+144h+columnid]; columnid
0x10018d8b  push    [esp+148h+tableid]; tableid
0x10018d92  push    esi; sesid
0x10018d93  call    _JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10018d98  test    eax, eax
0x10018d9a  js      loc_100197A5
0x10018da0  mov     ecx, [esp+130h+pcbActual]
0x10018da4  xor     edx, edx
0x10018da6  cmp     eax, 3ECh
0x10018dab  cmovz   ecx, edx
0x10018dae  mov     [esp+130h+pcbActual], ecx
0x10018db2  cmp     ebx, 0Ch; switch 13 cases
0x10018db5  ja      def_10018DBB; jumptable 10018DBB default case, cases 8,9
0x10018dbb  jmp     ds:jpt_10018DBB[ebx*4]; switch jump
0x10018dc2  test    ecx, ecx; jumptable 10018DBB case 0
0x10018dc4  jle     short loc_10018DDF
0x10018dc6  movzx   eax, [esp+130h+pszSrc]
0x10018dce  mov     [esp+130h+var_E0], ax
0x10018dd3  xor     eax, eax
0x10018dd5  mov     [esp+130h+var_DE], ax
0x10018dda  jmp     def_10018DBB; jumptable 10018DBB default case, cases 8,9
0x10018ddf  xor     eax, eax
0x10018de1  mov     [esp+130h+var_E0], ax
0x10018de6  mov     [esp+130h+var_DE], ax
0x10018deb  jmp     def_10018DBB; jumptable 10018DBB default case, cases 8,9
0x10018df0  cmp     [esp+130h+var_11D], dl; jumptable 10018DBB case 1
0x10018df4  lea     ecx, [esp+130h+var_98]
0x10018dfb  mov     eax, ecx
0x10018dfd  mov     edx, 8
0x10018e02  jnz     short loc_10018E4A
0x10018e04  mov     esi, offset aYy; "yy"
0x10018e09  sub     esi, eax
0x10018e0b  jmp     short loc_10018E10
0x10018e10  lea     eax, [edx+7FFFFFF6h]
0x10018e16  test    eax, eax
0x10018e18  jz      short loc_10018E39
0x10018e1a  movzx   eax, word ptr [esi+ecx]
0x10018e1e  test    ax, ax
0x10018e21  jz      short loc_10018E39
0x10018e23  mov     [ecx], ax
0x10018e26  add     ecx, 2
0x10018e29  dec     edx
0x10018e2a  jnz     short loc_10018E10
0x10018e2c  sub     ecx, 2
0x10018e2f  xor     eax, eax
0x10018e31  mov     [ecx], ax
0x10018e34  jmp     def_10018DBB; jumptable 10018DBB default case, cases 8,9
0x10018e39  test    edx, edx
0x10018e3b  jnz     short loc_10018E40
0x10018e3d  sub     ecx, 2
0x10018e40  xor     eax, eax
0x10018e42  mov     [ecx], ax
0x10018e45  jmp     def_10018DBB; jumptable 10018DBB default case, cases 8,9
0x10018e4a  mov     esi, offset aYyyy; "yyyy"
0x10018e4f  sub     esi, eax
0x10018e51  lea     eax, [edx+7FFFFFF6h]
0x10018e57  test    eax, eax
0x10018e59  jz      short loc_10018E39
0x10018e5b  movzx   eax, word ptr [esi+ecx]
0x10018e5f  test    ax, ax
0x10018e62  jz      short loc_10018E39
0x10018e64  mov     [ecx], ax
0x10018e67  add     ecx, 2
0x10018e6a  dec     edx
0x10018e6b  jnz     short loc_10018E51
0x10018e6d  sub     ecx, 2
0x10018e70  xor     eax, eax
0x10018e72  mov     [ecx], ax
0x10018e75  jmp     def_10018DBB; jumptable 10018DBB default case, cases 8,9
0x10018e7a  cmp     [esp+130h+var_11D], dl; jumptable 10018DBB case 2
0x10018e7e  lea     ecx, [esp+130h+var_B8]
0x10018e82  mov     eax, ecx
0x10018e84  mov     edx, 8
0x10018e89  jnz     short loc_10018F01
0x10018e8b  mov     esi, offset aD_0; "d"
0x10018e90  sub     esi, eax
0x10018e92  lea     eax, [edx+7FFFFFF6h]
0x10018e98  test    eax, eax
0x10018e9a  jz      short loc_10018EB0
0x10018e9c  movzx   eax, word ptr [esi+ecx]
0x10018ea0  test    ax, ax
0x10018ea3  jz      short loc_10018EB0
0x10018ea5  mov     [ecx], ax
0x10018ea8  add     ecx, 2
0x10018eab  dec     edx
0x10018eac  jnz     short loc_10018E92
0x10018eae  jmp     short loc_10018EB4
0x10018eb0  test    edx, edx
0x10018eb2  jnz     short loc_10018EB7
0x10018eb4  sub     ecx, 2
0x10018eb7  xor     eax, eax
0x10018eb9  mov     esi, offset aM; "m"
0x10018ebe  mov     [ecx], ax
0x10018ec1  lea     ecx, [esp+130h+var_A8]
0x10018ec8  lea     edx, [eax+8]
0x10018ecb  mov     eax, ecx
0x10018ecd  sub     esi, eax
0x10018ecf  nop
0x10018ed0  lea     eax, [edx+7FFFFFF6h]
0x10018ed6  test    eax, eax
0x10018ed8  jz      loc_10018E39
0x10018ede  movzx   eax, word ptr [esi+ecx]
0x10018ee2  test    ax, ax
0x10018ee5  jz      loc_10018E39
0x10018eeb  mov     [ecx], ax
0x10018eee  add     ecx, 2
0x10018ef1  dec     edx
0x10018ef2  jnz     short loc_10018ED0
0x10018ef4  sub     ecx, 2
0x10018ef7  xor     eax, eax
0x10018ef9  mov     [ecx], ax
0x10018efc  jmp     def_10018DBB; jumptable 10018DBB default case, cases 8,9
0x10018f01  mov     esi, offset aDd_0; "dd"
0x10018f06  sub     esi, eax
0x10018f08  jmp     short loc_10018F10
0x10018f10  lea     eax, [edx+7FFFFFF6h]
0x10018f16  test    eax, eax
0x10018f18  jz      short loc_10018F2E
0x10018f1a  movzx   eax, word ptr [esi+ecx]
0x10018f1e  test    ax, ax
0x10018f21  jz      short loc_10018F2E
0x10018f23  mov     [ecx], ax
0x10018f26  add     ecx, 2
0x10018f29  dec     edx
0x10018f2a  jnz     short loc_10018F10
0x10018f2c  jmp     short loc_10018F32
0x10018f2e  test    edx, edx
0x10018f30  jnz     short loc_10018F35
0x10018f32  sub     ecx, 2
0x10018f35  xor     eax, eax
0x10018f37  mov     esi, offset aMm; "mm"
0x10018f3c  mov     [ecx], ax
0x10018f3f  lea     ecx, [esp+130h+var_A8]
0x10018f46  lea     edx, [eax+8]
0x10018f49  mov     eax, ecx
0x10018f4b  sub     esi, eax
0x10018f4d  lea     ecx, [ecx+0]
0x10018f50  lea     eax, [edx+7FFFFFF6h]
0x10018f56  test    eax, eax
0x10018f58  jz      loc_10018E39
0x10018f5e  movzx   eax, word ptr [esi+ecx]
0x10018f62  test    ax, ax
0x10018f65  jz      loc_10018E39
0x10018f6b  mov     [ecx], ax
0x10018f6e  add     ecx, 2
0x10018f71  dec     edx
0x10018f72  jnz     short loc_10018F50
0x10018f74  sub     ecx, 2
0x10018f77  xor     eax, eax
0x10018f79  mov     [ecx], ax
0x10018f7c  jmp     def_10018DBB; jumptable 10018DBB default case, cases 8,9
0x10018f81  movzx   esi, word ptr [esp+130h+var_104]; jumptable 10018DBB case 3
0x10018f86  mov     [esp+130h+var_11C], esi
0x10018f8a  jmp     loc_10019124
0x10018f8f  mov     dx, [esp+130h+pszSrc]; jumptable 10018DBB case 4
0x10018f97  test    ecx, ecx
0x10018f99  jle     short loc_10018FA0
0x10018f9b  movzx   eax, dx
0x10018f9e  jmp     short loc_10018FA2
0x10018fa0  xor     eax, eax
0x10018fa2  mov     [edi+2DAh], ax
0x10018fa9  test    ecx, ecx
0x10018fab  jle     short loc_10018FBC
0x10018fad  movzx   eax, dx
0x10018fb0  mov     [edi+2D4h], ax
0x10018fb7  jmp     def_10018DBB; jumptable 10018DBB default case, cases 8,9
0x10018fbc  xor     eax, eax
0x10018fbe  mov     [edi+2D4h], ax
0x10018fc5  jmp     def_10018DBB; jumptable 10018DBB default case, cases 8,9
0x10018fca  test    ecx, ecx; jumptable 10018DBB case 5
0x10018fcc  jle     short loc_10018FDF
  ... truncated ...
```
