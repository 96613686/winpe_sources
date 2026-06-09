# LZNT1DecompressChunk

- ea: `0x1801632d0`
- end: `0x180163e36`
- name: `LZNT1DecompressChunk`
- size: `2918`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18010c580`
- `0x180150bd0`

## callees

- `0x1801632d0`

## pseudocode

```c
__int64 __fastcall LZNT1DecompressChunk(_BYTE *a1, _BYTE *a2, _BYTE *a3, __int64 a4, _DWORD *a5)
{
  _BYTE *v5; // rdi
  unsigned __int64 v8; // r9
  _BYTE *v9; // r11
  unsigned __int64 v10; // rbp
  __int64 v11; // rbx
  char v12; // al
  _BYTE *v13; // r12
  unsigned __int16 v14; // cx
  unsigned int v15; // esi
  int v16; // ecx
  int v17; // et1
  _BYTE *v18; // rsi
  unsigned __int64 v19; // rcx
  _BYTE *v20; // r12
  unsigned __int16 v21; // cx
  unsigned int v22; // esi
  int v23; // ecx
  int v24; // ett
  _BYTE *v25; // rsi
  unsigned __int64 v26; // rcx
  _BYTE *v27; // r12
  unsigned __int16 v28; // cx
  unsigned int v29; // esi
  int v30; // ecx
  int v31; // et1
  _BYTE *v32; // rsi
  unsigned __int64 v33; // rcx
  _BYTE *v34; // r12
  unsigned __int16 v35; // cx
  unsigned int v36; // esi
  int v37; // ecx
  int v38; // ett
  _BYTE *v39; // rsi
  unsigned __int64 v40; // rcx
  _BYTE *v41; // r12
  unsigned __int16 v42; // cx
  unsigned int v43; // esi
  int v44; // ecx
  int v45; // et1
  _BYTE *v46; // rsi
  unsigned __int64 v47; // rcx
  _BYTE *v48; // r12
  unsigned __int16 v49; // cx
  unsigned int v50; // esi
  int v51; // ecx
  int v52; // ett
  _BYTE *v53; // rsi
  unsigned __int64 v54; // rcx
  _BYTE *v55; // r12
  unsigned __int16 v56; // cx
  unsigned int v57; // esi
  int v58; // ecx
  int v59; // et1
  _BYTE *v60; // rsi
  unsigned __int64 v61; // rcx
  _BYTE *v62; // r12
  unsigned __int16 v63; // cx
  unsigned int v64; // esi
  int v65; // ecx
  int v66; // ett
  _BYTE *v67; // rsi
  unsigned __int64 v68; // rcx
  unsigned __int64 v69; // r9
  _BYTE *v70; // r12
  unsigned __int16 v71; // cx
  unsigned int v72; // esi
  int v73; // ecx
  int v74; // et1
  _BYTE *v75; // rsi
  unsigned __int64 v76; // rcx
  _BYTE *v77; // r12
  unsigned __int16 v78; // cx
  unsigned int v79; // esi
  int v80; // ecx
  int v81; // ett
  _BYTE *v82; // rsi
  unsigned __int64 v83; // rcx
  _BYTE *v84; // r12
  unsigned __int16 v85; // cx
  unsigned int v86; // esi
  int v87; // ecx
  int v88; // et1
  _BYTE *v89; // rsi
  unsigned __int64 v90; // rcx
  _BYTE *v91; // r12
  unsigned __int16 v92; // cx
  unsigned int v93; // esi
  int v94; // ecx
  int v95; // ett
  _BYTE *v96; // rsi
  unsigned __int64 v97; // rcx
  _BYTE *v98; // r12
  unsigned __int16 v99; // cx
  unsigned int v100; // esi
  int v101; // ecx
  int v102; // et1
  _BYTE *v103; // rsi
  unsigned __int64 v104; // rcx
  _BYTE *v105; // r12
  unsigned __int16 v106; // cx
  unsigned int v107; // esi
  int v108; // ecx
  int v109; // ett
  _BYTE *v110; // rsi
  unsigned __int64 v111; // rcx
  _BYTE *v112; // r12
  unsigned __int16 v113; // cx
  unsigned int v114; // esi
  int v115; // ecx
  int v116; // et1
  _BYTE *v117; // rsi
  unsigned __int64 v118; // rcx
  _BYTE *v119; // r12
  unsigned __int16 v120; // cx
  unsigned int v121; // esi
  int v122; // ecx
  int v123; // ett
  _BYTE *v124; // rsi
  unsigned __int64 v125; // rcx

  v5 = a1;
  v8 = a4 - 17;
  v9 = a2 - 8;
  v10 = (unsigned __int64)a1;
  v11 = 13;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              while ( 1 )
              {
                while ( 1 )
                {
                  while ( 1 )
                  {
                    if ( (unsigned __int64)a3 >= v8 || v5 >= v9 )
                    {
                      v69 = v8 + 17;
                      goto LABEL_89;
                    }
                    v12 = *a3;
                    if ( (*a3 & 1) != 0 )
                      break;
                    *v5 = a3[1];
                    if ( (v12 & 2) != 0 )
                      goto LABEL_25;
                    v5[1] = a3[2];
                    if ( (v12 & 4) != 0 )
                      goto LABEL_37;
                    v5[2] = a3[3];
                    if ( (v12 & 8) != 0 )
                      goto LABEL_48;
                    v5[3] = a3[4];
                    if ( (v12 & 0x10) != 0 )
                      goto LABEL_58;
                    v5[4] = a3[5];
                    if ( (v12 & 0x20) != 0 )
                      goto LABEL_67;
                    v5[5] = a3[6];
                    if ( (v12 & 0x40) != 0 )
                      goto LABEL_75;
                    v5[6] = a3[7];
                    if ( v12 < 0 )
                      goto LABEL_82;
                    v5[7] = a3[8];
                    a3 += 9;
                    v5 += 8;
                  }
                  while ( (unsigned __int64)v5 > v10 )
                  {
                    v11 = (unsigned int)(v11 - 1);
                    v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
                  }
                  v13 = a3 + 1;
                  v14 = *(_WORD *)(a3 + 1);
                  v15 = v14;
                  v17 = dword_180184444[v11] & v14;
                  v11 = (unsigned int)v11;
                  v16 = v17;
                  v18 = &v5[-(v15 >> v11) - 1];
                  if ( v18 < a1 )
                    return 3221226050LL;
                  v19 = (unsigned int)(v16 + 3);
                  if ( &v5[v19] >= v9 )
                  {
                    v69 = v8 + 17;
                    a3 = v13 - 1;
                    goto LABEL_92;
                  }
                  qmemcpy(v5, v18, v19);
                  a3 = v13;
                  v5 = &v5[v19 - 1];
                  if ( (v12 & 2) != 0 )
                    break;
                  v5[1] = v13[2];
                  if ( (v12 & 4) != 0 )
                    goto LABEL_37;
                  v5[2] = v13[3];
                  if ( (v12 & 8) != 0 )
                    goto LABEL_48;
                  v5[3] = v13[4];
                  if ( (v12 & 0x10) != 0 )
                    goto LABEL_58;
                  v5[4] = v13[5];
                  if ( (v12 & 0x20) != 0 )
                    goto LABEL_67;
                  v5[5] = v13[6];
                  if ( (v12 & 0x40) != 0 )
                    goto LABEL_75;
                  v5[6] = v13[7];
                  if ( v12 < 0 )
                    goto LABEL_82;
                  v5[7] = v13[8];
                  a3 = v13 + 9;
                  v5 += 8;
                }
LABEL_25:
                ++v5;
                while ( (unsigned __int64)v5 > v10 )
                {
                  v11 = (unsigned int)(v11 - 1);
                  v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
                }
                v20 = a3 + 1;
                v21 = *((_WORD *)a3 + 1);
                v22 = v21;
                v24 = dword_180184444[v11] & v21;
                v11 = (unsigned int)v11;
                v23 = v24;
                v25 = &v5[-(v22 >> v11) - 1];
                if ( v25 < a1 )
                  return 3221226050LL;
                v26 = (unsigned int)(v23 + 3);
                if ( &v5[v26] >= v9 )
                {
                  v69 = v8 + 17;
                  a3 = v20 - 1;
                  goto LABEL_105;
                }
                qmemcpy(v5, v25, v26);
                a3 = v20;
                v5 = &v5[v26 - 2];
                if ( (v12 & 4) != 0 )
                  break;
                v5[2] = v20[3];
                if ( (v12 & 8) != 0 )
                  goto LABEL_48;
                v5[3] = v20[4];
                if ( (v12 & 0x10) != 0 )
                  goto LABEL_58;
                v5[4] = v20[5];
                if ( (v12 & 0x20) != 0 )
                  goto LABEL_67;
                v5[5] = v20[6];
                if ( (v12 & 0x40) != 0 )
                  goto LABEL_75;
                v5[6] = v20[7];
                if ( v12 < 0 )
                  goto LABEL_82;
                v5[7] = v20[8];
                a3 = v20 + 9;
                v5 += 8;
              }
LABEL_37:
              v5 += 2;
              while ( (unsigned __int64)v5 > v10 )
              {
                v11 = (unsigned int)(v11 - 1);
                v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
              }
              v27 = a3 + 1;
              v28 = *(_WORD *)(a3 + 3);
              v29 = v28;
              v31 = dword_180184444[v11] & v28;
              v11 = (unsigned int)v11;
              v30 = v31;
              v32 = &v5[-(v29 >> v11) - 1];
              if ( v32 < a1 )
                return 3221226050LL;
              v33 = (unsigned int)(v30 + 3);
              if ( &v5[v33] >= v9 )
              {
                v69 = v8 + 17;
                a3 = v27 - 1;
                goto LABEL_118;
              }
              qmemcpy(v5, v32, v33);
              a3 = v27;
              v5 = &v5[v33 - 3];
              if ( (v12 & 8) != 0 )
                break;
              v5[3] = v27[4];
              if ( (v12 & 0x10) != 0 )
                goto LABEL_58;
              v5[4] = v27[5];
              if ( (v12 & 0x20) != 0 )
                goto LABEL_67;
              v5[5] = v27[6];
              if ( (v12 & 0x40) != 0 )
                goto LABEL_75;
              v5[6] = v27[7];
              if ( v12 < 0 )
                goto LABEL_82;
              v5[7] = v27[8];
              a3 = v27 + 9;
              v5 += 8;
            }
LABEL_48:
            v5 += 3;
            while ( (unsigned __int64)v5 > v10 )
            {
              v11 = (unsigned int)(v11 - 1);
              v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
            }
            v34 = a3 + 1;
            v35 = *((_WORD *)a3 + 2);
            v36 = v35;
            v38 = dword_180184444[v11] & v35;
            v11 = (unsigned int)v11;
            v37 = v38;
            v39 = &v5[-(v36 >> v11) - 1];
            if ( v39 < a1 )
              return 3221226050LL;
            v40 = (unsigned int)(v37 + 3);
            if ( &v5[v40] >= v9 )
            {
              v69 = v8 + 17;
              a3 = v34 - 1;
              goto LABEL_131;
            }
            qmemcpy(v5, v39, v40);
            a3 = v34;
            v5 = &v5[v40 - 4];
            if ( (v12 & 0x10) != 0 )
              break;
            v5[4] = v34[5];
            if ( (v12 & 0x20) != 0 )
              goto LABEL_67;
            v5[5] = v34[6];
            if ( (v12 & 0x40) != 0 )
              goto LABEL_75;
            v5[6] = v34[7];
            if ( v12 < 0 )
              goto LABEL_82;
            v5[7] = v34[8];
            a3 = v34 + 9;
            v5 += 8;
          }
LABEL_58:
          v5 += 4;
          while ( (unsigned __int64)v5 > v10 )
          {
            v11 = (unsigned int)(v11 - 1);
            v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
          }
          v41 = a3 + 1;
          v42 = *(_WORD *)(a3 + 5);
          v43 = v42;
          v45 = dword_180184444[v11] & v42;
          v11 = (unsigned int)v11;
          v44 = v45;
          v46 = &v5[-(v43 >> v11) - 1];
          if ( v46 < a1 )
            return 3221226050LL;
          v47 = (unsigned int)(v44 + 3);
          if ( &v5[v47] >= v9 )
          {
            v69 = v8 + 17;
            a3 = v41 - 1;
            goto LABEL_144;
          }
          qmemcpy(v5, v46, v47);
          a3 = v41;
          v5 = &v5[v47 - 5];
          if ( (v12 & 0x20) != 0 )
            break;
          v5[5] = v41[6];
          if ( (v12 & 0x40) != 0 )
            goto LABEL_75;
          v5[6] = v41[7];
          if ( v12 < 0 )
            goto LABEL_82;
          v5[7] = v41[8];
          a3 = v41 + 9;
          v5 += 8;
        }
LABEL_67:
        v5 += 5;
        while ( (unsigned __int64)v5 > v10 )
        {
          v11 = (unsigned int)(v11 - 1);
          v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
        }
        v48 = a3 + 1;
        v49 = *((_WORD *)a3 + 3);
        v50 = v49;
        v52 = dword_180184444[v11] & v49;
        v11 = (unsigned int)v11;
        v51 = v52;
        v53 = &v5[-(v50 >> v11) - 1];
        if ( v53 < a1 )
          return 3221226050LL;
        v54 = (unsigned int)(v51 + 3);
        if ( &v5[v54] >= v9 )
        {
          v69 = v8 + 17;
          a3 = v48 - 1;
          goto LABEL_157;
        }
        qmemcpy(v5, v53, v54);
        a3 = v48;
        v5 = &v5[v54 - 6];
        if ( (v12 & 0x40) != 0 )
          break;
        v5[6] = v48[7];
        if ( v12 < 0 )
          goto LABEL_82;
        v5[7] = v48[8];
        a3 = v48 + 9;
        v5 += 8;
      }
LABEL_75:
      v5 += 6;
      while ( (unsigned __int64)v5 > v10 )
      {
        v11 = (unsigned int)(v11 - 1);
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
      }
      v55 = a3 + 1;
      v56 = *(_WORD *)(a3 + 7);
      v57 = v56;
      v59 = dword_180184444[v11] & v56;
      v11 = (unsigned int)v11;
      v58 = v59;
      v60 = &v5[-(v57 >> v11) - 1];
      if ( v60 < a1 )
        return 3221226050LL;
      v61 = (unsigned int)(v58 + 3);
      if ( &v5[v61] >= v9 )
      {
        v69 = v8 + 17;
        a3 = v55 - 1;
        goto LABEL_170;
      }
      qmemcpy(v5, v60, v61);
      a3 = v55;
      v5 = &v5[v61 - 7];
      if ( v12 < 0 )
        break;
      v5[7] = v55[8];
      a3 = v55 + 9;
      v5 += 8;
    }
LABEL_82:
    v5 += 7;
    while ( (unsigned __int64)v5 > v10 )
    {
      v11 = (unsigned int)(v11 - 1);
      v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
    }
    v62 = a3 + 1;
    v63 = *((_WORD *)a3 + 4);
    v64 = v63;
    v66 = dword_180184444[v11] & v63;
    v11 = (unsigned int)v11;
    v65 = v66;
    v67 = &v5[-(v64 >> v11) - 1];
    if ( v67 < a1 )
      return 3221226050LL;
    v68 = (unsigned int)(v65 + 3);
    if ( &v5[v68] >= v9 )
      break;
    qmemcpy(v5, v67, v68);
    v5 += v68;
    a3 = v62 + 9;
  }
  v69 = v8 + 17;
  a3 = v62 - 1;
  while ( a3 + 8 != (_BYTE *)v69 )
  {
    if ( (unsigned __int64)(a3 + 8) > v69 )
      return 3221226050LL;
    if ( v5 == a2 )
      break;
    if ( v5 > a2 )
      return 3221226050LL;
    if ( v12 < 0 )
    {
      if ( (unsigned __int64)(a3 + 10) > v69 )
        return 3221226050LL;
      while ( (unsigned __int64)v5 > v10 )
      {
        v11 = (unsigned int)(v11 - 1);
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
      }
      v119 = a3 + 1;
      v120 = *((_WORD *)a3 + 4);
      v121 = v120;
      v123 = dword_180184444[v11] & v120;
      v11 = (unsigned int)v11;
      v122 = v123;
      v124 = &v5[-(v121 >> v11) - 1];
      if ( v124 < a1 )
        return 3221226050LL;
      v125 = (unsigned int)(v122 + 3);
      if ( &v5[v125] > a2 )
        return 3221226050LL;
      qmemcpy(v5, v124, v125);
      v5 += v125;
      a3 = v119;
    }
    else
    {
      *v5++ = a3[8];
    }
    a3 += 9;
LABEL_89:
    if ( a3 == (_BYTE *)v69 )
      break;
    v12 = *a3;
LABEL_92:
    if ( a3 + 1 == (_BYTE *)v69 )
      break;
    if ( (unsigned __int64)(a3 + 1) > v69 )
      return 3221226050LL;
    if ( v5 == a2 )
      break;
    if ( v5 > a2 )
      return 3221226050LL;
    if ( (v12 & 1) != 0 )
    {
      if ( (unsigned __int64)(a3 + 3) > v69 )
        return 3221226050LL;
      while ( (unsigned __int64)v5 > v10 )
      {
        v11 = (unsigned int)(v11 - 1);
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
      }
      v70 = a3 + 1;
      v71 = *(_WORD *)(a3 + 1);
      v72 = v71;
      v74 = dword_180184444[v11] & v71;
      v11 = (unsigned int)v11;
      v73 = v74;
      v75 = &v5[-(v72 >> v11) - 1];
      if ( v75 < a1 )
        return 3221226050LL;
      v76 = (unsigned int)(v73 + 3);
      if ( &v5[v76] > a2 )
        return 3221226050LL;
      qmemcpy(v5, v75, v76);
      v5 += v76;
      a3 = v70;
    }
    else
    {
      *v5++ = a3[1];
    }
LABEL_105:
    if ( a3 + 2 == (_BYTE *)v69 )
      break;
    if ( (unsigned __int64)(a3 + 2) > v69 )
      return 3221226050LL;
    if ( v5 == a2 )
      break;
    if ( v5 > a2 )
      return 3221226050LL;
    if ( (v12 & 2) != 0 )
    {
      if ( (unsigned __int64)(a3 + 4) > v69 )
        return 3221226050LL;
      while ( (unsigned __int64)v5 > v10 )
      {
        v11 = (unsigned int)(v11 - 1);
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
      }
      v77 = a3 + 1;
      v78 = *((_WORD *)a3 + 1);
      v79 = v78;
      v81 = dword_180184444[v11] & v78;
      v11 = (unsigned int)v11;
      v80 = v81;
      v82 = &v5[-(v79 >> v11) - 1];
      if ( v82 < a1 )
        return 3221226050LL;
      v83 = (unsigned int)(v80 + 3);
      if ( &v5[v83] > a2 )
        return 3221226050LL;
      qmemcpy(v5, v82, v83);
      v5 += v83;
      a3 = v77;
    }
    else
    {
      *v5++ = a3[2];
    }
LABEL_118:
    if ( a3 + 3 == (_BYTE *)v69 )
      break;
    if ( (unsigned __int64)(a3 + 3) > v69 )
      return 3221226050LL;
    if ( v5 == a2 )
      break;
    if ( v5 > a2 )
      return 3221226050LL;
    if ( (v12 & 4) != 0 )
    {
      if ( (unsigned __int64)(a3 + 5) > v69 )
        return 3221226050LL;
      while ( (unsigned __int64)v5 > v10 )
      {
        v11 = (unsigned int)(v11 - 1);
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
      }
      v84 = a3 + 1;
      v85 = *(_WORD *)(a3 + 3);
      v86 = v85;
      v88 = dword_180184444[v11] & v85;
      v11 = (unsigned int)v11;
      v87 = v88;
      v89 = &v5[-(v86 >> v11) - 1];
      if ( v89 < a1 )
        return 3221226050LL;
      v90 = (unsigned int)(v87 + 3);
      if ( &v5[v90] > a2 )
        return 3221226050LL;
      qmemcpy(v5, v89, v90);
      v5 += v90;
      a3 = v84;
    }
    else
    {
      *v5++ = a3[3];
    }
LABEL_131:
    if ( a3 + 4 == (_BYTE *)v69 )
      break;
    if ( (unsigned __int64)(a3 + 4) > v69 )
      return 3221226050LL;
    if ( v5 == a2 )
      break;
    if ( v5 > a2 )
      return 3221226050LL;
    if ( (v12 & 8) != 0 )
    {
      if ( (unsigned __int64)(a3 + 6) > v69 )
        return 3221226050LL;
      while ( (unsigned __int64)v5 > v10 )
      {
        v11 = (unsigned int)(v11 - 1);
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
      }
      v91 = a3 + 1;
      v92 = *((_WORD *)a3 + 2);
      v93 = v92;
      v95 = dword_180184444[v11] & v92;
      v11 = (unsigned int)v11;
      v94 = v95;
      v96 = &v5[-(v93 >> v11) - 1];
      if ( v96 < a1 )
        return 3221226050LL;
      v97 = (unsigned int)(v94 + 3);
      if ( &v5[v97] > a2 )
        return 3221226050LL;
      qmemcpy(v5, v96, v97);
      v5 += v97;
      a3 = v91;
    }
    else
    {
      *v5++ = a3[4];
    }
LABEL_144:
    if ( a3 + 5 == (_BYTE *)v69 )
      break;
    if ( (unsigned __int64)(a3 + 5) > v69 )
      return 3221226050LL;
    if ( v5 == a2 )
      break;
    if ( v5 > a2 )
      return 3221226050LL;
    if ( (v12 & 0x10) != 0 )
    {
      if ( (unsigned __int64)(a3 + 7) > v69 )
        return 3221226050LL;
      while ( (unsigned __int64)v5 > v10 )
      {
        v11 = (unsigned int)(v11 - 1);
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
      }
      v98 = a3 + 1;
      v99 = *(_WORD *)(a3 + 5);
      v100 = v99;
      v102 = dword_180184444[v11] & v99;
      v11 = (unsigned int)v11;
      v101 = v102;
      v103 = &v5[-(v100 >> v11) - 1];
      if ( v103 < a1 )
        return 3221226050LL;
      v104 = (unsigned int)(v101 + 3);
      if ( &v5[v104] > a2 )
        return 3221226050LL;
      qmemcpy(v5, v103, v104);
      v5 += v104;
      a3 = v98;
    }
    else
    {
      *v5++ = a3[5];
    }
LABEL_157:
    if ( a3 + 6 == (_BYTE *)v69 )
      break;
    if ( (unsigned __int64)(a3 + 6) > v69 )
      return 3221226050LL;
    if ( v5 == a2 )
      break;
    if ( v5 > a2 )
      return 3221226050LL;
    if ( (v12 & 0x20) != 0 )
    {
      if ( (unsigned __int64)(a3 + 8) > v69 )
        return 3221226050LL;
      while ( (unsigned __int64)v5 > v10 )
      {
        v11 = (unsigned int)(v11 - 1);
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
      }
      v105 = a3 + 1;
      v106 = *((_WORD *)a3 + 3);
      v107 = v106;
      v109 = dword_180184444[v11] & v106;
      v11 = (unsigned int)v11;
      v108 = v109;
      v110 = &v5[-(v107 >> v11) - 1];
      if ( v110 < a1 )
        return 3221226050LL;
      v111 = (unsigned int)(v108 + 3);
      if ( &v5[v111] > a2 )
        return 3221226050LL;
      qmemcpy(v5, v110, v111);
      v5 += v111;
      a3 = v105;
    }
    else
    {
      *v5++ = a3[6];
    }
LABEL_170:
    if ( a3 + 7 == (_BYTE *)v69 )
      break;
    if ( (unsigned __int64)(a3 + 7) > v69 )
      return 3221226050LL;
    if ( v5 == a2 )
      break;
    if ( v5 > a2 )
      return 3221226050LL;
    if ( (v12 & 0x40) != 0 )
    {
      if ( (unsigned __int64)(a3 + 9) > v69 )
        return 3221226050LL;
      while ( (unsigned __int64)v5 > v10 )
      {
        v11 = (unsigned int)(v11 - 1);
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180184400 + v11)];
      }
      v112 = a3 + 1;
      v113 = *(_WORD *)(a3 + 7);
      v114 = v113;
      v116 = dword_180184444[v11] & v113;
      v11 = (unsigned int)v11;
      v115 = v116;
      v117 = &v5[-(v114 >> v11) - 1];
      if ( v117 < a1 )
        return 3221226050LL;
      v118 = (unsigned int)(v115 + 3);
      if ( &v5[v118] > a2 )
        return 3221226050LL;
      qmemcpy(v5, v117, v118);
      v5 += v118;
      a3 = v112;
    }
    else
    {
      *v5++ = a3[7];
    }
  }
  *a5 = (_DWORD)v5 - (_DWORD)a1;
  return 0;
}

```

## disassembly

```asm
0x1801632d0  push    r12
0x1801632d2  push    rbp
0x1801632d3  push    rbx
0x1801632d4  push    rdi
0x1801632d5  push    rsi
0x1801632d6  mov     rdi, rcx
0x1801632d9  mov     r10, rcx
0x1801632dc  mov     rsi, r8
0x1801632df  mov     r8, rdx
0x1801632e2  sub     r9, 11h
0x1801632e6  sub     rdx, 8
0x1801632ea  mov     r11, rdx
0x1801632ed  mov     rbp, rdi
0x1801632f0  mov     ebx, 0Dh
0x1801632f5  cmp     rsi, r9
0x1801632f8  jnb     loc_1801638BF
0x1801632fe  cmp     rdi, r11
0x180163301  jnb     loc_1801638BF
0x180163307  mov     al, [rsi]
0x180163309  test    al, 1
0x18016330b  jnz     short loc_180163381
0x18016330d  mov     dl, [rsi+1]
0x180163310  mov     [rdi], dl
0x180163312  test    al, 2
0x180163314  jnz     loc_18016345C
0x18016331a  mov     dl, [rsi+2]
0x18016331d  mov     [rdi+1], dl
0x180163320  test    al, 4
0x180163322  jnz     loc_180163529
0x180163328  mov     dl, [rsi+3]
0x18016332b  mov     [rdi+2], dl
0x18016332e  test    al, 8
0x180163330  jnz     loc_1801635E8
0x180163336  mov     dl, [rsi+4]
0x180163339  mov     [rdi+3], dl
0x18016333c  test    al, 10h
0x18016333e  jnz     loc_180163699
0x180163344  mov     dl, [rsi+5]
0x180163347  mov     [rdi+4], dl
0x18016334a  test    al, 20h
0x18016334c  jnz     loc_180163738
0x180163352  mov     dl, [rsi+6]
0x180163355  mov     [rdi+5], dl
0x180163358  test    al, 40h
0x18016335a  jnz     loc_1801637C9
0x180163360  mov     dl, [rsi+7]
0x180163363  mov     [rdi+6], dl
0x180163366  test    al, 80h
0x180163368  jnz     loc_180163849
0x18016336e  mov     dl, [rsi+8]
0x180163371  mov     [rdi+7], dl
0x180163374  add     rsi, 9
0x180163378  add     rdi, 8
0x18016337c  jmp     loc_1801632F5
0x180163381  cmp     rdi, rbp
0x180163384  ja      loc_180163442
0x18016338a  lea     rdx, [rsi+1]
0x18016338e  mov     r12, rdx
0x180163391  xor     ecx, ecx
0x180163393  mov     cx, [rsi+1]
0x180163397  mov     esi, ecx
0x180163399  lea     rdx, dword_180184444
0x1801633a0  and     ecx, [rdx+rbx*4]
0x1801633a3  xchg    ebx, ecx
0x1801633a5  shr     esi, cl
0x1801633a7  xchg    ebx, ecx
0x1801633a9  neg     rsi
0x1801633ac  lea     rsi, [rsi+rdi-1]
0x1801633b1  cmp     rsi, r10
0x1801633b4  jb      loc_180163E19
0x1801633ba  add     ecx, 3
0x1801633bd  lea     rdx, [rdi+rcx]
0x1801633c1  cmp     rdx, r11
0x1801633c4  jnb     loc_1801638D0
0x1801633ca  rep movsb
0x1801633cc  mov     rsi, r12
0x1801633cf  sub     rdi, 1
0x1801633d3  test    al, 2
0x1801633d5  jnz     loc_18016345C
0x1801633db  mov     dl, [rsi+2]
0x1801633de  mov     [rdi+1], dl
0x1801633e1  test    al, 4
0x1801633e3  jnz     loc_180163529
0x1801633e9  mov     dl, [rsi+3]
0x1801633ec  mov     [rdi+2], dl
0x1801633ef  test    al, 8
0x1801633f1  jnz     loc_1801635E8
0x1801633f7  mov     dl, [rsi+4]
0x1801633fa  mov     [rdi+3], dl
0x1801633fd  test    al, 10h
0x1801633ff  jnz     loc_180163699
0x180163405  mov     dl, [rsi+5]
0x180163408  mov     [rdi+4], dl
0x18016340b  test    al, 20h
0x18016340d  jnz     loc_180163738
0x180163413  mov     dl, [rsi+6]
0x180163416  mov     [rdi+5], dl
0x180163419  test    al, 40h
0x18016341b  jnz     loc_1801637C9
0x180163421  mov     dl, [rsi+7]
0x180163424  mov     [rdi+6], dl
0x180163427  test    al, 80h
0x180163429  jnz     loc_180163849
0x18016342f  mov     dl, [rsi+8]
0x180163432  mov     [rdi+7], dl
0x180163435  add     rsi, 9
0x180163439  add     rdi, 8
0x18016343d  jmp     loc_1801632F5
0x180163442  dec     ebx
0x180163444  mov     rdx, r10
0x180163447  lea     rcx, qword_180184400
0x18016344e  mov     ecx, [rcx+rbx*4]
0x180163451  add     rdx, rcx
0x180163454  mov     rbp, rdx
0x180163457  jmp     loc_180163381
0x18016345c  add     rdi, 1
0x180163460  cmp     rdi, rbp
0x180163463  ja      loc_18016350F
0x180163469  lea     rdx, [rsi+1]
0x18016346d  mov     r12, rdx
0x180163470  xor     ecx, ecx
0x180163472  mov     cx, [rsi+2]
0x180163476  mov     esi, ecx
0x180163478  lea     rdx, dword_180184444
0x18016347f  and     ecx, [rdx+rbx*4]
0x180163482  xchg    ebx, ecx
0x180163484  shr     esi, cl
0x180163486  xchg    ebx, ecx
0x180163488  neg     rsi
0x18016348b  lea     rsi, [rsi+rdi-1]
0x180163490  cmp     rsi, r10
0x180163493  jb      loc_180163E19
0x180163499  add     ecx, 3
0x18016349c  lea     rdx, [rdi+rcx]
0x1801634a0  cmp     rdx, r11
0x1801634a3  jnb     loc_18016397A
0x1801634a9  rep movsb
0x1801634ab  mov     rsi, r12
0x1801634ae  sub     rdi, 2
0x1801634b2  test    al, 4
0x1801634b4  jnz     short loc_180163529
0x1801634b6  mov     dl, [rsi+3]
0x1801634b9  mov     [rdi+2], dl
0x1801634bc  test    al, 8
0x1801634be  jnz     loc_1801635E8
0x1801634c4  mov     dl, [rsi+4]
0x1801634c7  mov     [rdi+3], dl
0x1801634ca  test    al, 10h
0x1801634cc  jnz     loc_180163699
0x1801634d2  mov     dl, [rsi+5]
0x1801634d5  mov     [rdi+4], dl
0x1801634d8  test    al, 20h
0x1801634da  jnz     loc_180163738
0x1801634e0  mov     dl, [rsi+6]
0x1801634e3  mov     [rdi+5], dl
0x1801634e6  test    al, 40h
0x1801634e8  jnz     loc_1801637C9
0x1801634ee  mov     dl, [rsi+7]
0x1801634f1  mov     [rdi+6], dl
0x1801634f4  test    al, 80h
0x1801634f6  jnz     loc_180163849
0x1801634fc  mov     dl, [rsi+8]
0x1801634ff  mov     [rdi+7], dl
0x180163502  add     rsi, 9
0x180163506  add     rdi, 8
0x18016350a  jmp     loc_1801632F5
0x18016350f  dec     ebx
0x180163511  mov     rdx, r10
0x180163514  lea     rcx, qword_180184400
0x18016351b  mov     ecx, [rcx+rbx*4]
0x18016351e  add     rdx, rcx
0x180163521  mov     rbp, rdx
0x180163524  jmp     loc_180163460
0x180163529  add     rdi, 2
0x18016352d  cmp     rdi, rbp
0x180163530  ja      loc_1801635CE
0x180163536  lea     rdx, [rsi+1]
0x18016353a  mov     r12, rdx
0x18016353d  xor     ecx, ecx
0x18016353f  mov     cx, [rsi+3]
0x180163543  mov     esi, ecx
0x180163545  lea     rdx, dword_180184444
0x18016354c  and     ecx, [rdx+rbx*4]
0x18016354f  xchg    ebx, ecx
0x180163551  shr     esi, cl
0x180163553  xchg    ebx, ecx
0x180163555  neg     rsi
0x180163558  lea     rsi, [rsi+rdi-1]
0x18016355d  cmp     rsi, r10
0x180163560  jb      loc_180163E19
0x180163566  add     ecx, 3
0x180163569  lea     rdx, [rdi+rcx]
0x18016356d  cmp     rdx, r11
0x180163570  jnb     loc_180163A24
0x180163576  rep movsb
0x180163578  mov     rsi, r12
0x18016357b  sub     rdi, 3
0x18016357f  test    al, 8
0x180163581  jnz     short loc_1801635E8
0x180163583  mov     dl, [rsi+4]
0x180163586  mov     [rdi+3], dl
0x180163589  test    al, 10h
0x18016358b  jnz     loc_180163699
0x180163591  mov     dl, [rsi+5]
0x180163594  mov     [rdi+4], dl
0x180163597  test    al, 20h
0x180163599  jnz     loc_180163738
0x18016359f  mov     dl, [rsi+6]
0x1801635a2  mov     [rdi+5], dl
0x1801635a5  test    al, 40h
0x1801635a7  jnz     loc_1801637C9
0x1801635ad  mov     dl, [rsi+7]
0x1801635b0  mov     [rdi+6], dl
0x1801635b3  test    al, 80h
0x1801635b5  jnz     loc_180163849
0x1801635bb  mov     dl, [rsi+8]
0x1801635be  mov     [rdi+7], dl
0x1801635c1  add     rsi, 9
0x1801635c5  add     rdi, 8
0x1801635c9  jmp     loc_1801632F5
0x1801635ce  dec     ebx
0x1801635d0  mov     rdx, r10
0x1801635d3  lea     rcx, qword_180184400
0x1801635da  mov     ecx, [rcx+rbx*4]
0x1801635dd  add     rdx, rcx
0x1801635e0  mov     rbp, rdx
0x1801635e3  jmp     loc_18016352D
0x1801635e8  add     rdi, 3
0x1801635ec  cmp     rdi, rbp
0x1801635ef  ja      loc_18016367F
0x1801635f5  lea     rdx, [rsi+1]
0x1801635f9  mov     r12, rdx
0x1801635fc  xor     ecx, ecx
0x1801635fe  mov     cx, [rsi+4]
0x180163602  mov     esi, ecx
0x180163604  lea     rdx, dword_180184444
0x18016360b  and     ecx, [rdx+rbx*4]
0x18016360e  xchg    ebx, ecx
0x180163610  shr     esi, cl
0x180163612  xchg    ebx, ecx
0x180163614  neg     rsi
0x180163617  lea     rsi, [rsi+rdi-1]
0x18016361c  cmp     rsi, r10
0x18016361f  jb      loc_180163E19
0x180163625  add     ecx, 3
0x180163628  lea     rdx, [rdi+rcx]
0x18016362c  cmp     rdx, r11
0x18016362f  jnb     loc_180163ACE
0x180163635  rep movsb
0x180163637  mov     rsi, r12
0x18016363a  sub     rdi, 4
0x18016363e  test    al, 10h
0x180163640  jnz     short loc_180163699
0x180163642  mov     dl, [rsi+5]
0x180163645  mov     [rdi+4], dl
0x180163648  test    al, 20h
0x18016364a  jnz     loc_180163738
0x180163650  mov     dl, [rsi+6]
0x180163653  mov     [rdi+5], dl
0x180163656  test    al, 40h
0x180163658  jnz     loc_1801637C9
0x18016365e  mov     dl, [rsi+7]
0x180163661  mov     [rdi+6], dl
0x180163664  test    al, 80h
0x180163666  jnz     loc_180163849
0x18016366c  mov     dl, [rsi+8]
0x18016366f  mov     [rdi+7], dl
0x180163672  add     rsi, 9
0x180163676  add     rdi, 8
0x18016367a  jmp     loc_1801632F5
0x18016367f  dec     ebx
0x180163681  mov     rdx, r10
0x180163684  lea     rcx, qword_180184400
0x18016368b  mov     ecx, [rcx+rbx*4]
0x18016368e  add     rdx, rcx
0x180163691  mov     rbp, rdx
0x180163694  jmp     loc_1801635EC
0x180163699  add     rdi, 4
0x18016369d  cmp     rdi, rbp
0x1801636a0  ja      short loc_18016371E
0x1801636a2  lea     rdx, [rsi+1]
0x1801636a6  mov     r12, rdx
0x1801636a9  xor     ecx, ecx
0x1801636ab  mov     cx, [rsi+5]
0x1801636af  mov     esi, ecx
0x1801636b1  lea     rdx, dword_180184444
0x1801636b8  and     ecx, [rdx+rbx*4]
0x1801636bb  xchg    ebx, ecx
0x1801636bd  shr     esi, cl
0x1801636bf  xchg    ebx, ecx
0x1801636c1  neg     rsi
0x1801636c4  lea     rsi, [rsi+rdi-1]
0x1801636c9  cmp     rsi, r10
0x1801636cc  jb      loc_180163E19
0x1801636d2  add     ecx, 3
0x1801636d5  lea     rdx, [rdi+rcx]
0x1801636d9  cmp     rdx, r11
0x1801636dc  jnb     loc_180163B78
0x1801636e2  rep movsb
0x1801636e4  mov     rsi, r12
  ... truncated ...
```
