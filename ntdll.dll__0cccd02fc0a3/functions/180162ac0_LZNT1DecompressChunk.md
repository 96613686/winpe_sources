# LZNT1DecompressChunk

- ea: `0x180162ac0`
- end: `0x180163626`
- name: `LZNT1DecompressChunk`
- size: `2918`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18010afe0`
- `0x180150270`

## callees

- `0x180162ac0`

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
                    v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
                  }
                  v13 = a3 + 1;
                  v14 = *(_WORD *)(a3 + 1);
                  v15 = v14;
                  v17 = dword_180183F44[v11] & v14;
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
                  v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
                }
                v20 = a3 + 1;
                v21 = *((_WORD *)a3 + 1);
                v22 = v21;
                v24 = dword_180183F44[v11] & v21;
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
                v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
              }
              v27 = a3 + 1;
              v28 = *(_WORD *)(a3 + 3);
              v29 = v28;
              v31 = dword_180183F44[v11] & v28;
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
              v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
            }
            v34 = a3 + 1;
            v35 = *((_WORD *)a3 + 2);
            v36 = v35;
            v38 = dword_180183F44[v11] & v35;
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
            v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
          }
          v41 = a3 + 1;
          v42 = *(_WORD *)(a3 + 5);
          v43 = v42;
          v45 = dword_180183F44[v11] & v42;
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
          v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
        }
        v48 = a3 + 1;
        v49 = *((_WORD *)a3 + 3);
        v50 = v49;
        v52 = dword_180183F44[v11] & v49;
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
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
      }
      v55 = a3 + 1;
      v56 = *(_WORD *)(a3 + 7);
      v57 = v56;
      v59 = dword_180183F44[v11] & v56;
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
      v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
    }
    v62 = a3 + 1;
    v63 = *((_WORD *)a3 + 4);
    v64 = v63;
    v66 = dword_180183F44[v11] & v63;
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
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
      }
      v119 = a3 + 1;
      v120 = *((_WORD *)a3 + 4);
      v121 = v120;
      v123 = dword_180183F44[v11] & v120;
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
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
      }
      v70 = a3 + 1;
      v71 = *(_WORD *)(a3 + 1);
      v72 = v71;
      v74 = dword_180183F44[v11] & v71;
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
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
      }
      v77 = a3 + 1;
      v78 = *((_WORD *)a3 + 1);
      v79 = v78;
      v81 = dword_180183F44[v11] & v78;
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
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
      }
      v84 = a3 + 1;
      v85 = *(_WORD *)(a3 + 3);
      v86 = v85;
      v88 = dword_180183F44[v11] & v85;
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
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
      }
      v91 = a3 + 1;
      v92 = *((_WORD *)a3 + 2);
      v93 = v92;
      v95 = dword_180183F44[v11] & v92;
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
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
      }
      v98 = a3 + 1;
      v99 = *(_WORD *)(a3 + 5);
      v100 = v99;
      v102 = dword_180183F44[v11] & v99;
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
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
      }
      v105 = a3 + 1;
      v106 = *((_WORD *)a3 + 3);
      v107 = v106;
      v109 = dword_180183F44[v11] & v106;
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
        v10 = (unsigned __int64)&a1[*((unsigned int *)qword_180183F00 + v11)];
      }
      v112 = a3 + 1;
      v113 = *(_WORD *)(a3 + 7);
      v114 = v113;
      v116 = dword_180183F44[v11] & v113;
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
0x180162ac0  push    r12
0x180162ac2  push    rbp
0x180162ac3  push    rbx
0x180162ac4  push    rdi
0x180162ac5  push    rsi
0x180162ac6  mov     rdi, rcx
0x180162ac9  mov     r10, rcx
0x180162acc  mov     rsi, r8
0x180162acf  mov     r8, rdx
0x180162ad2  sub     r9, 11h
0x180162ad6  sub     rdx, 8
0x180162ada  mov     r11, rdx
0x180162add  mov     rbp, rdi
0x180162ae0  mov     ebx, 0Dh
0x180162ae5  cmp     rsi, r9
0x180162ae8  jnb     loc_1801630AF
0x180162aee  cmp     rdi, r11
0x180162af1  jnb     loc_1801630AF
0x180162af7  mov     al, [rsi]
0x180162af9  test    al, 1
0x180162afb  jnz     short loc_180162B71
0x180162afd  mov     dl, [rsi+1]
0x180162b00  mov     [rdi], dl
0x180162b02  test    al, 2
0x180162b04  jnz     loc_180162C4C
0x180162b0a  mov     dl, [rsi+2]
0x180162b0d  mov     [rdi+1], dl
0x180162b10  test    al, 4
0x180162b12  jnz     loc_180162D19
0x180162b18  mov     dl, [rsi+3]
0x180162b1b  mov     [rdi+2], dl
0x180162b1e  test    al, 8
0x180162b20  jnz     loc_180162DD8
0x180162b26  mov     dl, [rsi+4]
0x180162b29  mov     [rdi+3], dl
0x180162b2c  test    al, 10h
0x180162b2e  jnz     loc_180162E89
0x180162b34  mov     dl, [rsi+5]
0x180162b37  mov     [rdi+4], dl
0x180162b3a  test    al, 20h
0x180162b3c  jnz     loc_180162F28
0x180162b42  mov     dl, [rsi+6]
0x180162b45  mov     [rdi+5], dl
0x180162b48  test    al, 40h
0x180162b4a  jnz     loc_180162FB9
0x180162b50  mov     dl, [rsi+7]
0x180162b53  mov     [rdi+6], dl
0x180162b56  test    al, 80h
0x180162b58  jnz     loc_180163039
0x180162b5e  mov     dl, [rsi+8]
0x180162b61  mov     [rdi+7], dl
0x180162b64  add     rsi, 9
0x180162b68  add     rdi, 8
0x180162b6c  jmp     loc_180162AE5
0x180162b71  cmp     rdi, rbp
0x180162b74  ja      loc_180162C32
0x180162b7a  lea     rdx, [rsi+1]
0x180162b7e  mov     r12, rdx
0x180162b81  xor     ecx, ecx
0x180162b83  mov     cx, [rsi+1]
0x180162b87  mov     esi, ecx
0x180162b89  lea     rdx, dword_180183F44
0x180162b90  and     ecx, [rdx+rbx*4]
0x180162b93  xchg    ebx, ecx
0x180162b95  shr     esi, cl
0x180162b97  xchg    ebx, ecx
0x180162b99  neg     rsi
0x180162b9c  lea     rsi, [rsi+rdi-1]
0x180162ba1  cmp     rsi, r10
0x180162ba4  jb      loc_180163609
0x180162baa  add     ecx, 3
0x180162bad  lea     rdx, [rdi+rcx]
0x180162bb1  cmp     rdx, r11
0x180162bb4  jnb     loc_1801630C0
0x180162bba  rep movsb
0x180162bbc  mov     rsi, r12
0x180162bbf  sub     rdi, 1
0x180162bc3  test    al, 2
0x180162bc5  jnz     loc_180162C4C
0x180162bcb  mov     dl, [rsi+2]
0x180162bce  mov     [rdi+1], dl
0x180162bd1  test    al, 4
0x180162bd3  jnz     loc_180162D19
0x180162bd9  mov     dl, [rsi+3]
0x180162bdc  mov     [rdi+2], dl
0x180162bdf  test    al, 8
0x180162be1  jnz     loc_180162DD8
0x180162be7  mov     dl, [rsi+4]
0x180162bea  mov     [rdi+3], dl
0x180162bed  test    al, 10h
0x180162bef  jnz     loc_180162E89
0x180162bf5  mov     dl, [rsi+5]
0x180162bf8  mov     [rdi+4], dl
0x180162bfb  test    al, 20h
0x180162bfd  jnz     loc_180162F28
0x180162c03  mov     dl, [rsi+6]
0x180162c06  mov     [rdi+5], dl
0x180162c09  test    al, 40h
0x180162c0b  jnz     loc_180162FB9
0x180162c11  mov     dl, [rsi+7]
0x180162c14  mov     [rdi+6], dl
0x180162c17  test    al, 80h
0x180162c19  jnz     loc_180163039
0x180162c1f  mov     dl, [rsi+8]
0x180162c22  mov     [rdi+7], dl
0x180162c25  add     rsi, 9
0x180162c29  add     rdi, 8
0x180162c2d  jmp     loc_180162AE5
0x180162c32  dec     ebx
0x180162c34  mov     rdx, r10
0x180162c37  lea     rcx, qword_180183F00
0x180162c3e  mov     ecx, [rcx+rbx*4]
0x180162c41  add     rdx, rcx
0x180162c44  mov     rbp, rdx
0x180162c47  jmp     loc_180162B71
0x180162c4c  add     rdi, 1
0x180162c50  cmp     rdi, rbp
0x180162c53  ja      loc_180162CFF
0x180162c59  lea     rdx, [rsi+1]
0x180162c5d  mov     r12, rdx
0x180162c60  xor     ecx, ecx
0x180162c62  mov     cx, [rsi+2]
0x180162c66  mov     esi, ecx
0x180162c68  lea     rdx, dword_180183F44
0x180162c6f  and     ecx, [rdx+rbx*4]
0x180162c72  xchg    ebx, ecx
0x180162c74  shr     esi, cl
0x180162c76  xchg    ebx, ecx
0x180162c78  neg     rsi
0x180162c7b  lea     rsi, [rsi+rdi-1]
0x180162c80  cmp     rsi, r10
0x180162c83  jb      loc_180163609
0x180162c89  add     ecx, 3
0x180162c8c  lea     rdx, [rdi+rcx]
0x180162c90  cmp     rdx, r11
0x180162c93  jnb     loc_18016316A
0x180162c99  rep movsb
0x180162c9b  mov     rsi, r12
0x180162c9e  sub     rdi, 2
0x180162ca2  test    al, 4
0x180162ca4  jnz     short loc_180162D19
0x180162ca6  mov     dl, [rsi+3]
0x180162ca9  mov     [rdi+2], dl
0x180162cac  test    al, 8
0x180162cae  jnz     loc_180162DD8
0x180162cb4  mov     dl, [rsi+4]
0x180162cb7  mov     [rdi+3], dl
0x180162cba  test    al, 10h
0x180162cbc  jnz     loc_180162E89
0x180162cc2  mov     dl, [rsi+5]
0x180162cc5  mov     [rdi+4], dl
0x180162cc8  test    al, 20h
0x180162cca  jnz     loc_180162F28
0x180162cd0  mov     dl, [rsi+6]
0x180162cd3  mov     [rdi+5], dl
0x180162cd6  test    al, 40h
0x180162cd8  jnz     loc_180162FB9
0x180162cde  mov     dl, [rsi+7]
0x180162ce1  mov     [rdi+6], dl
0x180162ce4  test    al, 80h
0x180162ce6  jnz     loc_180163039
0x180162cec  mov     dl, [rsi+8]
0x180162cef  mov     [rdi+7], dl
0x180162cf2  add     rsi, 9
0x180162cf6  add     rdi, 8
0x180162cfa  jmp     loc_180162AE5
0x180162cff  dec     ebx
0x180162d01  mov     rdx, r10
0x180162d04  lea     rcx, qword_180183F00
0x180162d0b  mov     ecx, [rcx+rbx*4]
0x180162d0e  add     rdx, rcx
0x180162d11  mov     rbp, rdx
0x180162d14  jmp     loc_180162C50
0x180162d19  add     rdi, 2
0x180162d1d  cmp     rdi, rbp
0x180162d20  ja      loc_180162DBE
0x180162d26  lea     rdx, [rsi+1]
0x180162d2a  mov     r12, rdx
0x180162d2d  xor     ecx, ecx
0x180162d2f  mov     cx, [rsi+3]
0x180162d33  mov     esi, ecx
0x180162d35  lea     rdx, dword_180183F44
0x180162d3c  and     ecx, [rdx+rbx*4]
0x180162d3f  xchg    ebx, ecx
0x180162d41  shr     esi, cl
0x180162d43  xchg    ebx, ecx
0x180162d45  neg     rsi
0x180162d48  lea     rsi, [rsi+rdi-1]
0x180162d4d  cmp     rsi, r10
0x180162d50  jb      loc_180163609
0x180162d56  add     ecx, 3
0x180162d59  lea     rdx, [rdi+rcx]
0x180162d5d  cmp     rdx, r11
0x180162d60  jnb     loc_180163214
0x180162d66  rep movsb
0x180162d68  mov     rsi, r12
0x180162d6b  sub     rdi, 3
0x180162d6f  test    al, 8
0x180162d71  jnz     short loc_180162DD8
0x180162d73  mov     dl, [rsi+4]
0x180162d76  mov     [rdi+3], dl
0x180162d79  test    al, 10h
0x180162d7b  jnz     loc_180162E89
0x180162d81  mov     dl, [rsi+5]
0x180162d84  mov     [rdi+4], dl
0x180162d87  test    al, 20h
0x180162d89  jnz     loc_180162F28
0x180162d8f  mov     dl, [rsi+6]
0x180162d92  mov     [rdi+5], dl
0x180162d95  test    al, 40h
0x180162d97  jnz     loc_180162FB9
0x180162d9d  mov     dl, [rsi+7]
0x180162da0  mov     [rdi+6], dl
0x180162da3  test    al, 80h
0x180162da5  jnz     loc_180163039
0x180162dab  mov     dl, [rsi+8]
0x180162dae  mov     [rdi+7], dl
0x180162db1  add     rsi, 9
0x180162db5  add     rdi, 8
0x180162db9  jmp     loc_180162AE5
0x180162dbe  dec     ebx
0x180162dc0  mov     rdx, r10
0x180162dc3  lea     rcx, qword_180183F00
0x180162dca  mov     ecx, [rcx+rbx*4]
0x180162dcd  add     rdx, rcx
0x180162dd0  mov     rbp, rdx
0x180162dd3  jmp     loc_180162D1D
0x180162dd8  add     rdi, 3
0x180162ddc  cmp     rdi, rbp
0x180162ddf  ja      loc_180162E6F
0x180162de5  lea     rdx, [rsi+1]
0x180162de9  mov     r12, rdx
0x180162dec  xor     ecx, ecx
0x180162dee  mov     cx, [rsi+4]
0x180162df2  mov     esi, ecx
0x180162df4  lea     rdx, dword_180183F44
0x180162dfb  and     ecx, [rdx+rbx*4]
0x180162dfe  xchg    ebx, ecx
0x180162e00  shr     esi, cl
0x180162e02  xchg    ebx, ecx
0x180162e04  neg     rsi
0x180162e07  lea     rsi, [rsi+rdi-1]
0x180162e0c  cmp     rsi, r10
0x180162e0f  jb      loc_180163609
0x180162e15  add     ecx, 3
0x180162e18  lea     rdx, [rdi+rcx]
0x180162e1c  cmp     rdx, r11
0x180162e1f  jnb     loc_1801632BE
0x180162e25  rep movsb
0x180162e27  mov     rsi, r12
0x180162e2a  sub     rdi, 4
0x180162e2e  test    al, 10h
0x180162e30  jnz     short loc_180162E89
0x180162e32  mov     dl, [rsi+5]
0x180162e35  mov     [rdi+4], dl
0x180162e38  test    al, 20h
0x180162e3a  jnz     loc_180162F28
0x180162e40  mov     dl, [rsi+6]
0x180162e43  mov     [rdi+5], dl
0x180162e46  test    al, 40h
0x180162e48  jnz     loc_180162FB9
0x180162e4e  mov     dl, [rsi+7]
0x180162e51  mov     [rdi+6], dl
0x180162e54  test    al, 80h
0x180162e56  jnz     loc_180163039
0x180162e5c  mov     dl, [rsi+8]
0x180162e5f  mov     [rdi+7], dl
0x180162e62  add     rsi, 9
0x180162e66  add     rdi, 8
0x180162e6a  jmp     loc_180162AE5
0x180162e6f  dec     ebx
0x180162e71  mov     rdx, r10
0x180162e74  lea     rcx, qword_180183F00
0x180162e7b  mov     ecx, [rcx+rbx*4]
0x180162e7e  add     rdx, rcx
0x180162e81  mov     rbp, rdx
0x180162e84  jmp     loc_180162DDC
0x180162e89  add     rdi, 4
0x180162e8d  cmp     rdi, rbp
0x180162e90  ja      short loc_180162F0E
0x180162e92  lea     rdx, [rsi+1]
0x180162e96  mov     r12, rdx
0x180162e99  xor     ecx, ecx
0x180162e9b  mov     cx, [rsi+5]
0x180162e9f  mov     esi, ecx
0x180162ea1  lea     rdx, dword_180183F44
0x180162ea8  and     ecx, [rdx+rbx*4]
0x180162eab  xchg    ebx, ecx
0x180162ead  shr     esi, cl
0x180162eaf  xchg    ebx, ecx
0x180162eb1  neg     rsi
0x180162eb4  lea     rsi, [rsi+rdi-1]
0x180162eb9  cmp     rsi, r10
0x180162ebc  jb      loc_180163609
0x180162ec2  add     ecx, 3
0x180162ec5  lea     rdx, [rdi+rcx]
0x180162ec9  cmp     rdx, r11
0x180162ecc  jnb     loc_180163368
0x180162ed2  rep movsb
0x180162ed4  mov     rsi, r12
  ... truncated ...
```
