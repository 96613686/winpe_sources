# LZ4_compress_fast_extState

- ea: `0x180002270`
- end: `0x18000332f`
- name: `LZ4_compress_fast_extState`
- size: `4287`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002210`

## callees

- `0x1800021f4`
- `0x180002270`
- `0x180003424`

## pseudocode

```c
__int64 __fastcall LZ4_compress_fast_extState(_DWORD *a1, char *a2, char *a3, int a4, int a5, int a6)
{
  __int64 v6; // rsi
  char *v7; // r15
  unsigned int *v9; // r14
  int v10; // r11d
  int v11; // eax
  __int64 v13; // rdx
  char *v14; // rcx
  char *v15; // rbx
  unsigned __int64 v16; // r13
  unsigned __int64 v17; // r15
  char *v18; // r12
  char *v19; // r9
  __int64 v20; // r11
  int v21; // eax
  int v22; // esi
  _DWORD *v23; // r8
  int v24; // ebp
  int v25; // r10d
  _DWORD *v26; // r9
  __int16 v27; // r14
  int v28; // esi
  __int64 v29; // rdx
  _WORD *v30; // rcx
  unsigned int v31; // r11d
  char *v32; // rdx
  char *v33; // r11
  unsigned int v34; // r10d
  _BYTE *v35; // rbx
  unsigned int v36; // eax
  _QWORD *v37; // rcx
  _WORD *v38; // rbx
  __int64 v39; // rax
  unsigned __int64 v40; // r10
  _QWORD *v41; // r8
  _DWORD *v42; // rcx
  _QWORD *v43; // rdx
  unsigned int v46; // ecx
  char v47; // al
  unsigned int v48; // ecx
  char *v49; // rbx
  unsigned __int64 v52; // rcx
  __int64 v53; // rdx
  unsigned int v54; // r11d
  unsigned __int64 v55; // rcx
  size_t v56; // rbp
  unsigned __int64 v57; // rax
  __int64 v58; // rcx
  char *v59; // r13
  char *v60; // r9
  unsigned __int64 v61; // r12
  int v62; // r11d
  char *v63; // rbx
  unsigned __int64 v64; // r14
  char *v65; // r15
  unsigned __int64 v66; // rdx
  _QWORD *v67; // r10
  int v68; // eax
  int i; // esi
  _QWORD *v70; // rbp
  unsigned __int64 v71; // rdx
  _QWORD *v72; // r9
  unsigned int v73; // r11d
  __int64 v74; // rcx
  unsigned int *v75; // rax
  __int64 v76; // rdx
  char *v77; // r8
  char *v78; // r10
  int v79; // edx
  _BYTE *v80; // rbx
  unsigned int v81; // eax
  _QWORD *v82; // rcx
  _WORD *v83; // rbx
  __int64 v84; // rax
  unsigned __int64 v85; // r11
  _QWORD *v86; // rdx
  __int16 v87; // ax
  _QWORD *v88; // r8
  _DWORD *v89; // rcx
  unsigned int v92; // ecx
  char v93; // al
  unsigned int v94; // ecx
  char *v95; // rbx
  unsigned __int64 v98; // rax
  __int64 v99; // rcx
  __int64 v100; // rdx
  size_t v101; // r13
  unsigned __int64 v102; // rax
  _DWORD *v103; // r9
  char *v104; // rbp
  __int64 v105; // r8
  unsigned __int64 v106; // r14
  char *v107; // r12
  unsigned __int64 v108; // r13
  unsigned __int64 v109; // r15
  _DWORD *v110; // rdx
  __int64 v111; // rsi
  int v112; // r14d
  int v113; // r11d
  int v114; // ebp
  _DWORD *v115; // r10
  __int16 v116; // r8
  _WORD *v117; // rcx
  int v118; // r11d
  unsigned int v119; // esi
  __int64 v120; // r9
  char *v121; // r9
  unsigned int v122; // ebp
  char *v123; // r11
  _BYTE *v124; // rbx
  unsigned int v125; // eax
  _QWORD *v126; // rcx
  _WORD *v127; // rbx
  __int64 v128; // rax
  unsigned __int64 v129; // rsi
  _QWORD *v130; // r8
  _QWORD *v131; // rdx
  _DWORD *v132; // rcx
  unsigned int v135; // r8d
  char v136; // al
  unsigned int v137; // ecx
  __int64 v138; // rax
  char *v139; // rbx
  unsigned __int64 v142; // rcx
  __int64 v143; // r9
  __int64 v144; // rcx
  char *v145; // r13
  char *v146; // r9
  unsigned __int64 v147; // r12
  unsigned __int64 v148; // r14
  int v149; // r11d
  char *v150; // r15
  unsigned __int64 v151; // rdx
  _QWORD *v152; // r10
  int v153; // eax
  int j; // esi
  _QWORD *v155; // rbp
  unsigned __int64 v156; // rdx
  _QWORD *v157; // r9
  unsigned int v158; // r11d
  __int64 v159; // rcx
  unsigned int *v160; // rax
  __int64 v161; // rdx
  char *v162; // r8
  char *v163; // rbp
  __int64 v164; // r10
  char *v165; // r11
  _BYTE *v166; // rbx
  unsigned int v167; // eax
  _QWORD *v168; // rcx
  _WORD *v169; // rbx
  __int64 v170; // rax
  unsigned __int64 v171; // r10
  _DWORD *v172; // rdx
  __int16 v173; // ax
  _QWORD *v174; // r8
  _DWORD *v175; // rcx
  unsigned int v178; // r8d
  char v179; // al
  unsigned int v180; // ecx
  __int64 v181; // rax
  char *v182; // rbx
  unsigned __int64 v185; // rax
  __int64 v186; // rcx
  __int64 v187; // rdx
  char *v189; // [rsp+28h] [rbp-70h]
  char *v190; // [rsp+28h] [rbp-70h]
  unsigned __int64 v191; // [rsp+28h] [rbp-70h]
  char *v192; // [rsp+30h] [rbp-68h]
  char *v193; // [rsp+30h] [rbp-68h]
  char *v194; // [rsp+30h] [rbp-68h]
  char *v195; // [rsp+30h] [rbp-68h]
  char *v196; // [rsp+38h] [rbp-60h]
  char *v197; // [rsp+40h] [rbp-58h]
  char *v198; // [rsp+40h] [rbp-58h]
  char *v199; // [rsp+48h] [rbp-50h]
  char *v200; // [rsp+48h] [rbp-50h]
  _DWORD *v201; // [rsp+A0h] [rbp+8h]
  int v202; // [rsp+B0h] [rbp+18h]
  int v203; // [rsp+C8h] [rbp+30h]
  int v204; // [rsp+C8h] [rbp+30h]
  int v205; // [rsp+C8h] [rbp+30h]
  int v206; // [rsp+C8h] [rbp+30h]
  int v207; // [rsp+C8h] [rbp+30h]

  v202 = (int)a3;
  v201 = a1;
  v6 = a4;
  v7 = a3;
  v9 = a1;
  if ( a1 )
  {
    if ( ((unsigned __int8)a1 & 7) != 0 )
    {
      v9 = 0;
      v201 = 0;
    }
    else
    {
      memset_0(a1, 0, 0x4020u);
    }
  }
  else
  {
    v201 = 0;
  }
  v10 = 1;
  if ( a6 >= 1 )
    v10 = a6;
  if ( v10 > 65537 )
    v10 = 65537;
  v203 = v10;
  if ( (unsigned int)v6 <= 0x7E000000 )
    v11 = v6
        + ((int)((unsigned __int64)(2155905153LL * (int)v6) >> 32) >> 7)
        + ((unsigned int)((unsigned __int64)(2155905153LL * (int)v6) >> 32) >> 31)
        + 16;
  else
    v11 = 0;
  if ( a5 >= v11 )
  {
    if ( (int)v6 < 65547 )
    {
      if ( (unsigned int)v6 > 0x7E000000 )
        return 0;
      if ( !(_DWORD)v6 )
        goto LABEL_18;
      v13 = v9[4100];
      v14 = &a2[v6];
      v9[4102] += v6;
      v15 = v7;
      v189 = &a2[v6];
      v9[4101] = 3;
      v9[4100] = v13 + v6;
      if ( (int)v6 >= 13 )
      {
        v16 = (unsigned __int64)(v14 - 11);
        v17 = (unsigned __int64)(v14 - 5);
        v192 = a2;
        v18 = &a2[-v13];
        v19 = a2 + 1;
        *((_WORD *)v9 + ((unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)a2) >> 19)) = v13;
        v20 = (unsigned int)(-1640531535 * *(_DWORD *)(a2 + 1)) >> 19;
        v21 = v203 << 6;
        v204 = v203 << 6;
LABEL_21:
        v22 = 1;
        v23 = v19;
        v24 = v21;
        while ( 1 )
        {
          v25 = (int)v23;
          v26 = v23;
          v27 = (_WORD)v23 - (_WORD)v18;
          v23 = (_DWORD *)((char *)v23 + v22);
          if ( (unsigned __int64)v23 > v16 )
            break;
          v28 = v24;
          v29 = *((unsigned __int16 *)v201 + v20);
          v30 = (_WORD *)v201 + v20;
          v31 = -1640531535 * *v23;
          v32 = &v18[v29];
          *v30 = v27;
          ++v24;
          v22 = v28 >> 6;
          v20 = v31 >> 19;
          if ( *(_DWORD *)v32 == *v26 )
          {
            if ( v32 > v192 && *((_BYTE *)v26 - 1) == *(v32 - 1) )
            {
              do
              {
                v26 = (_DWORD *)((char *)v26 - 1);
                --v32;
              }
              while ( v32 > v192 && v26 > (_DWORD *)a2 && *((_BYTE *)v26 - 1) == *(v32 - 1) );
              v25 = (int)v26;
            }
            v33 = v15;
            v34 = v25 - (_DWORD)a2;
            v35 = v15 + 1;
            if ( v34 < 0xF )
            {
              *v33 = 16 * v34;
            }
            else
            {
              v36 = v34 - 15;
              for ( *v33 = -16; v36 >= 0xFF; ++v35 )
              {
                *v35 = -1;
                v36 -= 255;
              }
              *v35++ = v36;
            }
            v37 = v35;
            v38 = &v35[v34];
            do
            {
              v39 = *(_QWORD *)a2;
              a2 += 8;
              *v37++ = v39;
            }
            while ( v37 < (_QWORD *)v38 );
            v40 = v17 - 7;
            while ( 1 )
            {
              v41 = v26 + 1;
              v42 = v26 + 1;
              *v38 = (_WORD)v26 - (_WORD)v32;
              v43 = v32 + 4;
              v15 = (char *)(v38 + 1);
              if ( (unsigned __int64)(v26 + 1) < v40 )
              {
                if ( *v43 != *v41 )
                {
                  __asm { tzcnt   rcx, rax }
                  v46 = (unsigned int)_RCX >> 3;
                  goto LABEL_53;
                }
                v42 = v26 + 3;
                ++v43;
              }
              if ( (unsigned __int64)v42 >= v40 )
              {
LABEL_43:
                if ( (unsigned __int64)v42 < v17 - 3 && *(_DWORD *)v43 == *v42 )
                {
                  ++v42;
                  v43 = (_QWORD *)((char *)v43 + 4);
                }
                if ( (unsigned __int64)v42 < v17 - 1 && *(_WORD *)v43 == *(_WORD *)v42 )
                {
                  v42 = (_DWORD *)((char *)v42 + 2);
                  v43 = (_QWORD *)((char *)v43 + 2);
                }
                if ( (unsigned __int64)v42 < v17 && *(_BYTE *)v43 == *(_BYTE *)v42 )
                  LODWORD(v42) = (_DWORD)v42 + 1;
                v46 = (_DWORD)v42 - (_DWORD)v41;
              }
              else
              {
                while ( *v43 == *(_QWORD *)v42 )
                {
                  v42 += 2;
                  ++v43;
                  if ( (unsigned __int64)v42 >= v40 )
                    goto LABEL_43;
                }
                __asm { tzcnt   rax, rax }
                v46 = ((unsigned int)_RAX >> 3) - (_DWORD)v41 + (_DWORD)v42;
              }
LABEL_53:
              v26 = (_DWORD *)((char *)v26 + v46 + 4);
              v47 = *v33;
              if ( v46 < 0xF )
              {
                *v33 = v47 + v46;
              }
              else
              {
                v48 = v46 - 15;
                *v33 = v47 + 15;
                for ( *(_DWORD *)v15 = -1; v48 >= 0x3FC; *(_DWORD *)v15 = -1 )
                {
                  v15 += 4;
                  v48 -= 1020;
                }
                v49 = &v15[v48 / 0xFF];
                *v49 = v48 / 0xFF + v48;
                v15 = v49 + 1;
              }
              a2 = (char *)v26;
              if ( (unsigned __int64)v26 >= v16 )
                goto LABEL_64;
              *((_WORD *)v201 + ((unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v26 - 2)) >> 19)) = (_WORD)v26 - (_WORD)v18 - 2;
              v52 = (unsigned __int64)(unsigned int)(-1640531535 * *v26) >> 19;
              v53 = *((unsigned __int16 *)v201 + v52);
              *((_WORD *)v201 + v52) = (_WORD)v26 - (_WORD)v18;
              v32 = &v18[v53];
              if ( *(_DWORD *)v32 != *v26 )
              {
                v54 = -1640531535 * *(_DWORD *)((char *)v26 + 1);
                v19 = (char *)v26 + 1;
                v21 = v204;
                v20 = v54 >> 19;
                goto LABEL_21;
              }
              v33 = v15;
              v38 = v15 + 1;
              *v33 = 0;
            }
          }
        }
LABEL_64:
        v14 = v189;
        LODWORD(v7) = v202;
      }
      v55 = v14 - a2;
      v56 = v55;
      if ( v55 >= 0xF )
      {
        *v15 = -16;
        v57 = v55 - 15;
        ++v15;
        if ( v55 - 15 >= 0xFF )
        {
          do
          {
            *v15 = -1;
            v57 -= 255LL;
            ++v15;
          }
          while ( v57 >= 0xFF );
        }
        goto LABEL_70;
      }
LABEL_69:
      LOBYTE(v57) = 16 * v56;
LABEL_70:
      *v15 = v57;
      memcpy_0(v15 + 1, a2, v56);
      return (unsigned int)((_DWORD)v15 + 1 + v56 - (_DWORD)v7);
    }
    if ( (unsigned int)v6 <= 0x7E000000 )
    {
      v58 = v9[4100];
      v59 = &a2[v6];
      v9[4102] += v6;
      v60 = a2 + 1;
      v61 = (unsigned __int64)&a2[v6 - 11];
      v9[4101] = 2;
      v62 = v10 << 6;
      v9[4100] = v58 + v6;
      v63 = v7;
      v64 = (unsigned __int64)&a2[v6 - 5];
      v193 = a2;
      v65 = &a2[-v58];
      v190 = a2;
      v205 = v62;
      v201[(0xCF1BBCDCBB000000uLL * *(_QWORD *)a2) >> 52] = v58;
      v66 = 0xCF1BBCDCBB000000uLL * *(_QWORD *)(a2 + 1);
LABEL_73:
      v67 = v60;
      v68 = 1;
      for ( i = v62; ; ++i )
      {
        v70 = v67;
        v71 = v66 >> 52;
        v72 = v67;
        v73 = (_DWORD)v67 - (_DWORD)v65;
        v67 = (_QWORD *)((char *)v67 + v68);
        if ( (unsigned __int64)v67 > v61 )
          break;
        v74 = (unsigned int)v201[v71];
        v75 = &v201[v71];
        v76 = *v67;
        *v75 = v73;
        v77 = &v65[v74];
        if ( (int)v74 + 0xFFFF >= v73 && *(_DWORD *)v77 == *(_DWORD *)v72 )
        {
          if ( v77 > v193 && *((_BYTE *)v70 - 1) == *(v77 - 1) )
          {
            do
            {
              v72 = (_QWORD *)((char *)v72 - 1);
              --v77;
            }
            while ( v77 > v190 && v72 > (_QWORD *)a2 && *((_BYTE *)v72 - 1) == *(v77 - 1) );
            v61 = (unsigned __int64)(v59 - 11);
          }
          v78 = v63;
          v79 = (_DWORD)v72 - (_DWORD)a2;
          v80 = v63 + 1;
          if ( (unsigned int)((_DWORD)v72 - (_DWORD)a2) < 0xF )
          {
            *v78 = 16 * v79;
          }
          else
          {
            v81 = v79 - 15;
            for ( *v78 = -16; v81 >= 0xFF; ++v80 )
            {
              *v80 = -1;
              v81 -= 255;
            }
            *v80++ = v81;
          }
          v82 = v80;
          v83 = &v80[v79];
          do
          {
            v84 = *(_QWORD *)a2;
            a2 += 8;
            *v82++ = v84;
          }
          while ( v82 < (_QWORD *)v83 );
          v85 = v64 - 7;
          while ( 1 )
          {
            v86 = v77 + 4;
            v87 = (_WORD)v72 - (_WORD)v77;
            v88 = (_QWORD *)((char *)v72 + 4);
            *v83 = v87;
            v89 = (_DWORD *)v72 + 1;
            v63 = (char *)(v83 + 1);
            if ( (unsigned __int64)v72 + 4 < v85 )
            {
              if ( *v86 != *v88 )
              {
                __asm { tzcnt   rcx, rax }
                v92 = (unsigned int)_RCX >> 3;
                goto LABEL_107;
              }
              v89 = (_DWORD *)v72 + 3;
              ++v86;
            }
            if ( (unsigned __int64)v89 >= v85 )
            {
LABEL_97:
              if ( (unsigned __int64)v89 < v64 - 3 && *(_DWORD *)v86 == *v89 )
              {
                ++v89;
                v86 = (_QWORD *)((char *)v86 + 4);
              }
              if ( (unsigned __int64)v89 < v64 - 1 && *(_WORD *)v86 == *(_WORD *)v89 )
              {
                v89 = (_DWORD *)((char *)v89 + 2);
                v86 = (_QWORD *)((char *)v86 + 2);
              }
              if ( (unsigned __int64)v89 < v64 && *(_BYTE *)v86 == *(_BYTE *)v89 )
                LODWORD(v89) = (_DWORD)v89 + 1;
              v92 = (_DWORD)v89 - (_DWORD)v88;
            }
            else
            {
              while ( *v86 == *(_QWORD *)v89 )
              {
                v89 += 2;
                ++v86;
                if ( (unsigned __int64)v89 >= v85 )
                  goto LABEL_97;
              }
              __asm { tzcnt   rax, rax }
              v92 = ((unsigned int)_RAX >> 3) - (_DWORD)v88 + (_DWORD)v89;
            }
LABEL_107:
            v72 = (_QWORD *)((char *)v72 + v92 + 4);
            v93 = *v78;
            if ( v92 < 0xF )
            {
              *v78 = v93 + v92;
            }
            else
            {
              v94 = v92 - 15;
              *v78 = v93 + 15;
              for ( *(_DWORD *)v63 = -1; v94 >= 0x3FC; *(_DWORD *)v63 = -1 )
              {
                v63 += 4;
                v94 -= 1020;
              }
              v95 = &v63[v94 / 0xFF];
              *v95 = v94 / 0xFF + v94;
              v63 = v95 + 1;
            }
            a2 = (char *)v72;
            if ( (unsigned __int64)v72 >= v61 )
              goto LABEL_119;
            v201[(0xCF1BBCDCBB000000uLL * *(_QWORD *)((char *)v72 - 2)) >> 52] = (_DWORD)v72 - (_DWORD)v65 - 2;
            v98 = (0xCF1BBCDCBB000000uLL * *v72) >> 52;
            v99 = (unsigned int)v201[v98];
            v201[v98] = (_DWORD)v72 - (_DWORD)v65;
            v77 = &v65[v99];
            if ( (int)v99 + 0xFFFF < (unsigned int)((_DWORD)v72 - (_DWORD)v65) || *(_DWORD *)v77 != *(_DWORD *)v72 )
            {
              v100 = *(_QWORD *)((char *)v72 + 1);
              v60 = (char *)v72 + 1;
              v62 = v205;
              v66 = 0xCF1BBCDCBB000000uLL * v100;
              goto LABEL_73;
            }
            v78 = v63;
            v83 = v63 + 1;
            *v78 = 0;
          }
        }
        v68 = i >> 6;
        v66 = 0xCF1BBCDCBB000000uLL * v76;
      }
LABEL_119:
      v101 = v59 - a2;
      if ( v101 >= 0xF )
      {
        *v63 = -16;
        v102 = v101 - 15;
        ++v63;
        if ( v101 - 15 >= 0xFF )
        {
          do
          {
            *v63 = -1;
            v102 -= 255LL;
            ++v63;
          }
          while ( v102 >= 0xFF );
        }
        goto LABEL_240;
      }
LABEL_239:
      LOBYTE(v102) = 16 * v101;
LABEL_240:
      *v63 = v102;
      memcpy_0(v63 + 1, a2, v101);
      return (unsigned int)((_DWORD)v63 + 1 + v101 - v202);
    }
    return 0;
  }
  if ( (int)v6 >= 65547 )
  {
    if ( (unsigned int)v6 <= 0x7E000000 )
    {
      v144 = v9[4100];
      v9[4102] += v6;
      v145 = &a2[v6];
      v146 = a2 + 1;
      v195 = &v7[a5];
      v147 = (unsigned __int64)&a2[v6 - 11];
      v9[4101] = 2;
      v9[4100] = v144 + v6;
      v148 = (unsigned __int64)&a2[v6 - 5];
      v63 = v7;
      v149 = v10 << 6;
      v150 = &a2[-v144];
      v200 = a2;
      v198 = a2;
      v207 = v149;
      v201[(0xCF1BBCDCBB000000uLL * *(_QWORD *)a2) >> 52] = v144;
      v151 = 0xCF1BBCDCBB000000uLL * *(_QWORD *)(a2 + 1);
LABEL_184:
      v152 = v146;
      v153 = 1;
      for ( j = v149; ; ++j )
      {
        v155 = v152;
        v156 = v151 >> 52;
        v157 = v152;
        v158 = (_DWORD)v152 - (_DWORD)v150;
        v152 = (_QWORD *)((char *)v152 + v153);
        if ( (unsigned __int64)v152 > v147 )
          break;
        v159 = (unsigned int)v201[v156];
        v160 = &v201[v156];
        v161 = *v152;
        *v160 = v158;
        v162 = &v150[v159];
        if ( (int)v159 + 0xFFFF >= v158 && *(_DWORD *)v162 == *(_DWORD *)v157 )
        {
          if ( v162 > v200 && *((_BYTE *)v155 - 1) == *(v162 - 1) )
          {
            do
            {
              v157 = (_QWORD *)((char *)v157 - 1);
              --v162;
            }
            while ( v162 > v198 && v157 > (_QWORD *)a2 && *((_BYTE *)v157 - 1) == *(v162 - 1) );
            v147 = (unsigned __int64)(v145 - 11);
          }
          v163 = v195;
          v164 = (unsigned int)((_DWORD)v157 - (_DWORD)a2);
          v165 = v63;
          v166 = v63 + 1;
          if ( &v166[v164 + 8 + (unsigned int)v164 / 0xFF] > v195 )
            return 0;
          if ( (unsigned int)v164 < 0xF )
          {
            *v165 = 16 * ((_BYTE)v157 - (_BYTE)a2);
          }
          else
          {
            v167 = v164 - 15;
            for ( *v165 = -16; v167 >= 0xFF; ++v166 )
            {
              *v166 = -1;
              v167 -= 255;
            }
            *v166++ = v167;
          }
          v168 = v166;
          v169 = &v166[v164];
          do
          {
            v170 = *(_QWORD *)a2;
            a2 += 8;
            *v168++ = v170;
          }
          while ( v168 < (_QWORD *)v169 );
          v171 = v148 - 7;
          while ( 2 )
          {
            v172 = v162 + 4;
            v173 = (_WORD)v157 - (_WORD)v162;
            v174 = (_QWORD *)((char *)v157 + 4);
            *v169 = v173;
            v175 = (_DWORD *)v157 + 1;
            v63 = (char *)(v169 + 1);
            if ( (unsigned __int64)v157 + 4 >= v171 )
            {
LABEL_206:
              if ( (unsigned __int64)v175 >= v171 )
              {
LABEL_209:
                if ( (unsigned __int64)v175 < v148 - 3 && *v172 == *v175 )
                {
                  ++v175;
                  ++v172;
                }
                if ( (unsigned __int64)v175 < v148 - 1 && *(_WORD *)v172 == *(_WORD *)v175 )
                {
                  v175 = (_DWORD *)((char *)v175 + 2);
                  v172 = (_DWORD *)((char *)v172 + 2);
                }
                if ( (unsigned __int64)v175 < v148 && *(_BYTE *)v172 == *(_BYTE *)v175 )
                  LODWORD(v175) = (_DWORD)v175 + 1;
                v178 = (_DWORD)v175 - (_DWORD)v174;
              }
              else
              {
                while ( *(_QWORD *)v175 == *(_QWORD *)v172 )
                {
                  v175 += 2;
                  v172 += 2;
                  if ( (unsigned __int64)v175 >= v171 )
                    goto LABEL_209;
                }
                __asm { tzcnt   rax, rax }
                v178 = (_DWORD)v175 + ((unsigned int)_RAX >> 3) - (_DWORD)v174;
              }
            }
            else
            {
              if ( *(_QWORD *)v172 == *v174 )
              {
                v175 = (_DWORD *)v157 + 3;
                v172 += 2;
                goto LABEL_206;
              }
              __asm { tzcnt   r8, rax }
              v178 = (unsigned int)_R8 >> 3;
            }
            v157 = (_QWORD *)((char *)v157 + v178 + 4);
            if ( &v63[(v178 + 240) / 0xFF + 6] > v195 )
              return 0;
            v179 = *v165;
            if ( v178 < 0xF )
            {
              *v165 = v179 + v178;
            }
            else
            {
              v180 = v178 - 15;
              *v165 = v179 + 15;
              for ( *(_DWORD *)v63 = -1; v180 >= 0x3FC; *(_DWORD *)v63 = -1 )
              {
                v63 += 4;
                v180 -= 1020;
              }
              v181 = v180 / 0xFF;
              v182 = &v63[v181];
              *v182 = v180 + v181;
              v63 = v182 + 1;
            }
            a2 = (char *)v157;
            if ( (unsigned __int64)v157 >= v147 )
              goto LABEL_234;
            v201[(0xCF1BBCDCBB000000uLL * *(_QWORD *)((char *)v157 - 2)) >> 52] = (_DWORD)v157 - (_DWORD)v150 - 2;
            v185 = (0xCF1BBCDCBB000000uLL * *v157) >> 52;
            v186 = (unsigned int)v201[v185];
            v201[v185] = (_DWORD)v157 - (_DWORD)v150;
            v162 = &v150[v186];
            if ( (int)v186 + 0xFFFF < (unsigned int)((_DWORD)v157 - (_DWORD)v150) || *(_DWORD *)v162 != *(_DWORD *)v157 )
            {
              v187 = *(_QWORD *)((char *)v157 + 1);
              v146 = (char *)v157 + 1;
              v151 = 0xCF1BBCDCBB000000uLL * v187;
              v149 = v207;
              goto LABEL_184;
            }
            v165 = v63;
            v169 = v63 + 1;
            *v165 = 0;
            continue;
          }
        }
        v153 = j >> 6;
        v151 = 0xCF1BBCDCBB000000uLL * v161;
      }
      v163 = v195;
LABEL_234:
      v101 = v145 - a2;
      if ( &v63[v101 + 1 + (v101 + 240) / 0xFF] <= v163 )
      {
        if ( v101 >= 0xF )
        {
          *v63 = -16;
          v102 = v101 - 15;
          ++v63;
          if ( v101 - 15 >= 0xFF )
          {
            do
            {
              *v63 = -1;
              v102 -= 255LL;
              ++v63;
            }
            while ( v102 >= 0xFF );
          }
          goto LABEL_240;
        }
        goto LABEL_239;
      }
    }
    return 0;
  }
  if ( (unsigned int)v6 > 0x7E000000 )
    return 0;
  if ( (_DWORD)v6 )
  {
    v103 = v201;
    v104 = &a2[v6];
    v105 = v9[4100];
    v15 = v7;
    v106 = (unsigned __int64)&v7[a5];
    v194 = &a2[v6];
    v191 = v106;
    v201[4102] += v6;
    v201[4101] = 3;
    v201[4100] = v105 + v6;
    if ( (int)v6 < 13 )
      goto LABEL_177;
    v197 = a2;
    v107 = &a2[-v105];
    v196 = a2;
    v199 = &a2[-v105];
    v108 = (unsigned __int64)(v104 - 11);
    v109 = (unsigned __int64)(v104 - 5);
    v110 = a2 + 1;
    *((_WORD *)v201 + ((unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)a2) >> 19)) = v105;
    v111 = (unsigned int)(-1640531535 * *(_DWORD *)(a2 + 1)) >> 19;
    v206 = v10 << 6;
    v112 = v10 << 6;
    v113 = 1;
LABEL_131:
    while ( 2 )
    {
      v114 = (int)v110;
      v115 = v110;
      v116 = (_WORD)v110 - (_WORD)v107;
      v110 = (_DWORD *)((char *)v110 + v113);
      if ( (unsigned __int64)v110 > v108 )
      {
        v106 = v191;
LABEL_176:
        LODWORD(v7) = v202;
        v104 = v194;
LABEL_177:
        v56 = v104 - a2;
        if ( (unsigned __int64)&v15[v56 + 1 + (v56 + 240) / 0xFF] > v106 )
          return 0;
        if ( v56 >= 0xF )
        {
          *v15 = -16;
          v57 = v56 - 15;
          ++v15;
          if ( v56 - 15 >= 0xFF )
          {
            do
            {
              *v15 = -1;
              v57 -= 255LL;
              ++v15;
            }
            while ( v57 >= 0xFF );
          }
          goto LABEL_70;
        }
        goto LABEL_69;
      }
      v117 = (_WORD *)v103 + v111;
      v118 = v112;
      v119 = -1640531535 * *v110;
      ++v112;
      v120 = (unsigned __int16)*v117;
      *v117 = v116;
      v121 = &v107[v120];
      v113 = v118 >> 6;
      v111 = v119 >> 19;
      if ( *(_DWORD *)v121 != *v115 )
      {
        v103 = v201;
        continue;
      }
      break;
    }
    if ( v121 > v196 && *((_BYTE *)v115 - 1) == *(v121 - 1) )
    {
      do
      {
        v115 = (_DWORD *)((char *)v115 - 1);
        --v121;
      }
      while ( v121 > v197 && v115 > (_DWORD *)a2 && *((_BYTE *)v115 - 1) == *(v121 - 1) );
      v107 = v199;
      v114 = (int)v115;
    }
    v106 = v191;
    v122 = v114 - (_DWORD)a2;
    v123 = v15;
    v124 = v15 + 1;
    if ( (unsigned __int64)&v124[v122 / 0xFF + 8 + v122] > v191 )
      return 0;
    if ( v122 < 0xF )
    {
      *v123 = 16 * v122;
    }
    else
    {
      v125 = v122 - 15;
      for ( *v123 = -16; v125 >= 0xFF; ++v124 )
      {
        *v124 = -1;
        v125 -= 255;
      }
      *v124++ = v125;
    }
    v126 = v124;
    v127 = &v124[v122];
    do
    {
      v128 = *(_QWORD *)a2;
      a2 += 8;
      *v126++ = v128;
    }
    while ( v126 < (_QWORD *)v127 );
    v129 = v109 - 7;
    while ( 1 )
    {
      v130 = v115 + 1;
      v131 = v121 + 4;
      *v127 = (_WORD)v115 - (_WORD)v121;
      v132 = v115 + 1;
      v15 = (char *)(v127 + 1);
      if ( (unsigned __int64)(v115 + 1) < v129 )
      {
        if ( *v130 != *v131 )
        {
          __asm { tzcnt   r8, rax }
          v135 = (unsigned int)_R8 >> 3;
          goto LABEL_163;
        }
        v132 = v115 + 3;
        v131 = v121 + 12;
      }
      if ( (unsigned __int64)v132 >= v129 )
      {
LABEL_153:
        if ( (unsigned __int64)v132 < v109 - 3 && *(_DWORD *)v131 == *v132 )
        {
          ++v132;
          v131 = (_QWORD *)((char *)v131 + 4);
        }
        if ( (unsigned __int64)v132 < v109 - 1 && *(_WORD *)v131 == *(_WORD *)v132 )
        {
          v132 = (_DWORD *)((char *)v132 + 2);
          v131 = (_QWORD *)((char *)v131 + 2);
        }
        if ( (unsigned __int64)v132 < v109 && *(_BYTE *)v131 == *(_BYTE *)v132 )
          LODWORD(v132) = (_DWORD)v132 + 1;
        v135 = (_DWORD)v132 - (_DWORD)v130;
      }
      else
      {
        while ( *v131 == *(_QWORD *)v132 )
        {
          v132 += 2;
          ++v131;
          if ( (unsigned __int64)v132 >= v129 )
            goto LABEL_153;
        }
        __asm { tzcnt   rax, rax }
        v135 = (_DWORD)v132 + ((unsigned int)_RAX >> 3) - (_DWORD)v130;
      }
LABEL_163:
      v115 = (_DWORD *)((char *)v115 + v135 + 4);
      if ( (unsigned __int64)&v15[(v135 + 240) / 0xFF + 6] > v191 )
        return 0;
      v136 = *v123;
      if ( v135 < 0xF )
      {
        *v123 = v136 + v135;
      }
      else
      {
        v137 = v135 - 15;
        *v123 = v136 + 15;
        for ( *(_DWORD *)v15 = -1; v137 >= 0x3FC; *(_DWORD *)v15 = -1 )
        {
          v15 += 4;
          v137 -= 1020;
        }
        v138 = v137 / 0xFF;
        v139 = &v15[v138];
        *v139 = v137 + v138;
        v15 = v139 + 1;
      }
      a2 = (char *)v115;
      if ( (unsigned __int64)v115 >= v108 )
        goto LABEL_176;
      *((_WORD *)v201 + ((unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v115 - 2)) >> 19)) = (_WORD)v115 - (_WORD)v107 - 2;
      v142 = (unsigned __int64)(unsigned int)(-1640531535 * *v115) >> 19;
      v143 = *((unsigned __int16 *)v201 + v142);
      *((_WORD *)v201 + v142) = (_WORD)v115 - (_WORD)v107;
      v121 = &v107[v143];
      if ( *(_DWORD *)v121 != *v115 )
      {
        v103 = v201;
        v110 = (_DWORD *)((char *)v115 + 1);
        v113 = 1;
        v112 = v206;
        v111 = (unsigned int)(-1640531535 * *(_DWORD *)((char *)v115 + 1)) >> 19;
        goto LABEL_131;
      }
      v123 = v15;
      v127 = v15 + 1;
      *v123 = 0;
    }
  }
  if ( a5 > 0 )
  {
LABEL_18:
    *v7 = 0;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180002270  mov     [rsp+arg_10], r8
0x180002275  mov     [rsp+arg_0], rcx
0x18000227a  push    rbp
0x18000227b  push    rsi
0x18000227c  push    rdi
0x18000227d  push    r14
0x18000227f  push    r15
0x180002281  sub     rsp, 70h
0x180002285  movsxd  rsi, r9d
0x180002288  mov     r15, r8
0x18000228b  mov     rdi, rdx
0x18000228e  mov     r14, rcx
0x180002291  test    rcx, rcx
0x180002294  jnz     short loc_1800022A0
0x180002296  mov     [rsp+98h+arg_0], rcx
0x18000229e  jmp     short loc_1800022BF
0x1800022a0  test    cl, 7
0x1800022a3  jz      short loc_1800022B2
0x1800022a5  xor     r14d, r14d
0x1800022a8  mov     [rsp+98h+arg_0], r14
0x1800022b0  jmp     short loc_1800022BF
0x1800022b2  xor     edx, edx; Val
0x1800022b4  mov     r8d, 4020h; Size
0x1800022ba  call    memset_0
0x1800022bf  mov     ebp, 1
0x1800022c4  mov     eax, 10001h
0x1800022c9  cmp     [rsp+98h+arg_28], ebp
0x1800022d0  mov     r11d, ebp
0x1800022d3  mov     [rsp+98h+var_78], rbp
0x1800022d8  cmovge  r11d, [rsp+98h+arg_28]
0x1800022e1  cmp     r11d, eax
0x1800022e4  cmovg   r11d, eax
0x1800022e8  mov     [rsp+98h+arg_28], r11d
0x1800022f0  cmp     esi, 7E000000h
0x1800022f6  jbe     short loc_1800022FC
0x1800022f8  xor     eax, eax
0x1800022fa  jmp     short loc_180002314
0x1800022fc  mov     eax, 80808081h
0x180002301  imul    esi
0x180002303  add     edx, esi
0x180002305  sar     edx, 7
0x180002308  mov     eax, edx
0x18000230a  shr     eax, 1Fh
0x18000230d  add     eax, 10h
0x180002310  add     eax, edx
0x180002312  add     eax, esi
0x180002314  movsxd  rdx, [rsp+98h+arg_20]
0x18000231c  mov     [rsp+98h+arg_8], rbx
0x180002324  mov     [rsp+98h+var_30], r12
0x180002329  mov     [rsp+98h+var_38], r13
0x18000232e  cmp     edx, eax
0x180002330  jl      loc_180002A89
0x180002336  cmp     esi, 1000Bh
0x18000233c  jge     loc_1800026EF
0x180002342  cmp     esi, 7E000000h
0x180002348  jbe     short loc_180002353
0x18000234a  xor     ebp, ebp
0x18000234c  mov     eax, ebp
0x18000234e  jmp     loc_180003311
0x180002353  test    esi, esi
0x180002355  jnz     short loc_180002362
0x180002357  mov     byte ptr [r15], 0
0x18000235b  mov     eax, ebp
0x18000235d  jmp     loc_180003311
0x180002362  mov     edx, [r14+4010h]
0x180002369  lea     rcx, [rdi+rsi]
0x18000236d  add     [r14+4018h], esi
0x180002374  mov     rbx, r15
0x180002377  mov     [rsp+98h+var_70], rcx
0x18000237c  mov     dword ptr [r14+4014h], 3
0x180002387  lea     eax, [rdx+rsi]
0x18000238a  mov     [r14+4010h], eax
0x180002391  cmp     esi, 0Dh
0x180002394  jl      loc_18000268D
0x18000239a  mov     eax, [rsp+98h+arg_28]
0x1800023a1  lea     r13, [rcx-0Bh]
0x1800023a5  lea     r15, [rcx-5]
0x1800023a9  mov     [rsp+98h+var_68], rdi
0x1800023ae  imul    ecx, [rdi], 9E3779B1h
0x1800023b4  mov     r12, rdi
0x1800023b7  sub     r12, rdx
0x1800023ba  mov     r9, rdi
0x1800023bd  shr     rcx, 13h
0x1800023c1  inc     r9
0x1800023c4  mov     [r14+rcx*2], dx
0x1800023c9  imul    r11d, [r9], 9E3779B1h
0x1800023d0  shr     r11d, 13h
0x1800023d4  shl     eax, 6
0x1800023d7  mov     [rsp+98h+arg_28], eax
0x1800023de  xchg    ax, ax
0x1800023e0  mov     esi, ebp
0x1800023e2  mov     r8, r9
0x1800023e5  mov     ebp, eax
0x1800023e7  nop     word ptr [rax+rax+00000000h]
0x1800023f0  mov     r14d, r8d
0x1800023f3  movsxd  rax, esi
0x1800023f6  mov     r10, r8
0x1800023f9  mov     r9, r8
0x1800023fc  sub     r14d, r12d
0x1800023ff  add     r8, rax
0x180002402  cmp     r8, r13
0x180002405  ja      loc_180002680
0x18000240b  mov     rcx, [rsp+98h+arg_0]
0x180002413  mov     esi, ebp
0x180002415  movzx   edx, word ptr [rcx+r11*2]
0x18000241a  lea     rcx, [rcx+r11*2]
0x18000241e  imul    r11d, [r8], 9E3779B1h
0x180002425  add     rdx, r12
0x180002428  mov     [rcx], r14w
0x18000242c  inc     ebp
0x18000242e  mov     eax, [r9]
0x180002431  sar     esi, 6
0x180002434  shr     r11d, 13h
0x180002438  cmp     [rdx], eax
0x18000243a  jnz     short loc_1800023F0
0x18000243c  mov     r14, [rsp+98h+var_68]
0x180002441  cmp     rdx, r14
0x180002444  jbe     short loc_180002477
0x180002446  movzx   eax, byte ptr [rdx-1]
0x18000244a  cmp     [r9-1], al
0x18000244e  jnz     short loc_180002477
0x180002450  xor     ecx, ecx
0x180002452  dec     r9
0x180002455  dec     rdx
0x180002458  cmp     rdx, r14
0x18000245b  setnbe  cl
0x18000245e  xor     eax, eax
0x180002460  cmp     r9, rdi
0x180002463  setnbe  al
0x180002466  test    eax, ecx
0x180002468  jz      short loc_180002474
0x18000246a  movzx   eax, byte ptr [rdx-1]
0x18000246e  cmp     [r9-1], al
0x180002472  jz      short loc_180002450
0x180002474  mov     r10d, r9d
0x180002477  mov     r11, rbx
0x18000247a  sub     r10d, edi
0x18000247d  inc     rbx
0x180002480  cmp     r10d, 0Fh
0x180002484  jb      short loc_1800024B9
0x180002486  lea     eax, [r10-0Fh]
0x18000248a  mov     byte ptr [r11], 0F0h
0x18000248e  cmp     eax, 0FFh
0x180002493  jb      short loc_1800024B2
0x180002495  nop     word ptr [rax+rax+00000000h]
0x1800024a0  mov     byte ptr [rbx], 0FFh
0x1800024a3  add     eax, 0FFFFFF01h
0x1800024a8  inc     rbx
0x1800024ab  cmp     eax, 0FFh
0x1800024b0  jnb     short loc_1800024A0
0x1800024b2  mov     [rbx], al
0x1800024b4  inc     rbx
0x1800024b7  jmp     short loc_1800024C3
0x1800024b9  movzx   eax, r10b
0x1800024bd  shl     al, 4
0x1800024c0  mov     [r11], al
0x1800024c3  mov     eax, r10d
0x1800024c6  mov     rcx, rbx
0x1800024c9  add     rbx, rax
0x1800024cc  nop     dword ptr [rax+00h]
0x1800024d0  mov     rax, [rdi]
0x1800024d3  lea     rdi, [rdi+8]
0x1800024d7  mov     [rcx], rax
0x1800024da  add     rcx, 8
0x1800024de  cmp     rcx, rbx
0x1800024e1  jb      short loc_1800024D0
0x1800024e3  mov     r14, [rsp+98h+arg_0]
0x1800024eb  lea     r10, [r15-7]
0x1800024ef  nop
0x1800024f0  lea     r8, [r9+4]
0x1800024f4  movzx   eax, r9w
0x1800024f8  sub     ax, dx
0x1800024fb  mov     rcx, r8
0x1800024fe  mov     [rbx], ax
0x180002501  add     rdx, 4
0x180002505  add     rbx, 2
0x180002509  cmp     r8, r10
0x18000250c  jnb     short loc_180002522
0x18000250e  mov     rax, [r8]
0x180002511  xor     rax, [rdx]
0x180002514  jnz     loc_1800025F0
0x18000251a  lea     rcx, [r8+8]
0x18000251e  add     rdx, 8
0x180002522  cmp     rcx, r10
0x180002525  jnb     short loc_180002549
0x180002527  nop     word ptr [rax+rax+00000000h]
0x180002530  mov     rax, [rcx]
0x180002533  xor     rax, [rdx]
0x180002536  jnz     loc_1800025FA
0x18000253c  add     rcx, 8
0x180002540  add     rdx, 8
0x180002544  cmp     rcx, r10
0x180002547  jb      short loc_180002530
0x180002549  lea     rax, [r15-3]
0x18000254d  cmp     rcx, rax
0x180002550  jnb     short loc_180002560
0x180002552  mov     eax, [rcx]
0x180002554  cmp     [rdx], eax
0x180002556  jnz     short loc_180002560
0x180002558  add     rcx, 4
0x18000255c  add     rdx, 4
0x180002560  lea     rax, [r15-1]
0x180002564  cmp     rcx, rax
0x180002567  jnb     short loc_180002579
0x180002569  movzx   eax, word ptr [rcx]
0x18000256c  cmp     [rdx], ax
0x18000256f  jnz     short loc_180002579
0x180002571  add     rcx, 2
0x180002575  add     rdx, 2
0x180002579  cmp     rcx, r15
0x18000257c  jnb     short loc_180002588
0x18000257e  movzx   eax, byte ptr [rcx]
0x180002581  cmp     [rdx], al
0x180002583  jnz     short loc_180002588
0x180002585  inc     rcx
0x180002588  sub     ecx, r8d
0x18000258b  mov     eax, ecx
0x18000258d  add     r9, 4
0x180002591  add     r9, rax
0x180002594  movzx   eax, byte ptr [r11]
0x180002598  cmp     ecx, 0Fh
0x18000259b  jb      short loc_180002609
0x18000259d  add     al, 0Fh
0x18000259f  add     ecx, 0FFFFFFF1h
0x1800025a2  mov     [r11], al
0x1800025a5  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800025ab  cmp     ecx, 3FCh
0x1800025b1  jb      short loc_1800025D8
0x1800025b3  nop     dword ptr [rax+00h]
0x1800025b7  nop     word ptr [rax+rax+00000000h]
0x1800025c0  add     rbx, 4
0x1800025c4  add     ecx, 0FFFFFC04h
0x1800025ca  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800025d0  cmp     ecx, 3FCh
0x1800025d6  jnb     short loc_1800025C0
0x1800025d8  mov     eax, 80808081h
0x1800025dd  mul     ecx
0x1800025df  shr     edx, 7
0x1800025e2  add     cl, dl
0x1800025e4  mov     eax, edx
0x1800025e6  add     rbx, rax
0x1800025e9  mov     [rbx], cl
0x1800025eb  inc     rbx
0x1800025ee  jmp     short loc_18000260E
0x1800025f0  tzcnt   rcx, rax
0x1800025f5  shr     ecx, 3
0x1800025f8  jmp     short loc_18000258B
0x1800025fa  tzcnt   rax, rax
0x1800025ff  shr     eax, 3
0x180002602  sub     eax, r8d
0x180002605  add     ecx, eax
0x180002607  jmp     short loc_18000258B
0x180002609  add     cl, al
0x18000260b  mov     [r11], cl
0x18000260e  mov     rdi, r9
0x180002611  cmp     r9, r13
0x180002614  jnb     short loc_180002680
0x180002616  imul    ecx, [r9-2], 9E3779B1h
0x18000261e  mov     r8d, r9d
0x180002621  sub     r8w, r12w
0x180002625  shr     rcx, 13h
0x180002629  lea     edx, [r8-2]
0x18000262d  mov     [r14+rcx*2], dx
0x180002632  imul    ecx, [r9], 9E3779B1h
0x180002639  shr     rcx, 13h
0x18000263d  movzx   edx, word ptr [r14+rcx*2]
0x180002642  mov     [r14+rcx*2], r8w
0x180002647  add     rdx, r12
0x18000264a  mov     eax, [r9]
0x18000264d  cmp     [rdx], eax
0x18000264f  jnz     short loc_180002660
0x180002651  mov     r11, rbx
0x180002654  inc     rbx
0x180002657  mov     byte ptr [r11], 0
0x18000265b  jmp     loc_1800024F0
0x180002660  imul    r11d, [r9+1], 9E3779B1h
0x180002668  inc     r9
0x18000266b  mov     rbp, [rsp+98h+var_78]
0x180002670  mov     eax, [rsp+98h+arg_28]
0x180002677  shr     r11d, 13h
0x18000267b  jmp     loc_1800023E0
0x180002680  mov     rcx, [rsp+98h+var_70]
0x180002685  mov     r15, [rsp+98h+arg_10]
0x18000268d  sub     rcx, rdi
0x180002690  mov     rbp, rcx
0x180002693  cmp     rcx, 0Fh
0x180002697  jb      short loc_1800026C6
0x180002699  mov     byte ptr [rbx], 0F0h
0x18000269c  lea     rax, [rcx-0Fh]
0x1800026a0  inc     rbx
0x1800026a3  cmp     rax, 0FFh
0x1800026a9  jb      short loc_1800026CD
0x1800026ab  nop     dword ptr [rax+rax+00h]
0x1800026b0  mov     byte ptr [rbx], 0FFh
0x1800026b3  sub     rax, 0FFh
0x1800026b9  inc     rbx
0x1800026bc  cmp     rax, 0FFh
0x1800026c2  jnb     short loc_1800026B0
0x1800026c4  jmp     short loc_1800026CD
0x1800026c6  movzx   eax, bpl
  ... truncated ...
```
