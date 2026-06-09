# LZ4_compress_fast_extState

- ea: `0x180106dc8`
- end: `0x180107cb5`
- name: `LZ4_compress_fast_extState`
- size: `3821`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180151e10`

## callees

- `0x180106dc8`
- `0x18011e870`
- `0x18011f948`
- `0x180163a80`

## pseudocode

```c
__int64 __fastcall LZ4_compress_fast_extState(__int64 a1, char *a2, char *a3, int a4, int a5)
{
  __int64 v5; // rdi
  char *v6; // r13
  int v8; // eax
  unsigned int v9; // r8d
  __int64 v10; // rdx
  char *v11; // rbp
  char *v12; // rbx
  char *v13; // r12
  char *v14; // r10
  unsigned int v15; // ecx
  char *v16; // r11
  int v17; // eax
  int v18; // edi
  char *v19; // r13
  __int64 v20; // rcx
  char *v21; // r10
  __int16 v22; // r15
  char *v23; // rdx
  int v24; // r12d
  int v25; // eax
  int v26; // r12d
  char *v27; // rdi
  _BYTE *v28; // rbx
  int v29; // eax
  _WORD *v30; // r11
  _QWORD *v31; // rcx
  _WORD *v32; // rbx
  __int64 v33; // rax
  unsigned __int64 v34; // r14
  unsigned __int64 v35; // r15
  _QWORD *v36; // r11
  _QWORD *v37; // rcx
  __int16 v38; // ax
  _QWORD *v39; // rdx
  unsigned int v43; // ecx
  char v45; // al
  unsigned int v46; // r11d
  char *v47; // rax
  unsigned __int64 v48; // rcx
  __int64 v49; // rdx
  size_t v50; // rbp
  unsigned __int64 v51; // rax
  void *v52; // rbx
  __int64 v53; // rcx
  char *v54; // r10
  char *v55; // r11
  char *v56; // rbx
  char *v57; // r13
  char *v58; // r15
  unsigned __int64 v59; // rdx
  char *v60; // rdi
  int v61; // eax
  int m; // r12d
  int v63; // ebp
  char *v64; // r10
  unsigned __int64 v65; // rdx
  unsigned int v66; // ebp
  unsigned int *v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rcx
  char *v70; // r11
  int v71; // r12d
  char *v72; // rdi
  _BYTE *v73; // rbx
  int v74; // eax
  _WORD *v75; // rdx
  _QWORD *v76; // rcx
  _WORD *v77; // rbx
  __int64 v78; // rax
  unsigned __int64 v79; // r15
  unsigned __int64 v80; // rbp
  __int16 v81; // ax
  _QWORD *v82; // rdx
  _QWORD *v83; // r11
  _QWORD *v84; // rcx
  unsigned int v88; // ecx
  char v90; // al
  unsigned int v91; // r11d
  __int64 v92; // rdx
  unsigned __int64 v93; // rcx
  __int64 v94; // rax
  size_t v95; // r13
  unsigned __int64 v96; // rax
  void *v97; // rbx
  int v98; // r8d
  __int64 v99; // r10
  char *v100; // r12
  char *v101; // rbp
  char *v102; // r11
  char *v103; // r10
  unsigned int v104; // ecx
  char *v105; // rdx
  int v106; // eax
  int i; // edi
  char *v108; // r13
  __int64 v109; // rcx
  char *v110; // r10
  __int16 v111; // r15
  int v112; // r12d
  char *v113; // r11
  __int64 v114; // rcx
  char *v115; // rdi
  _BYTE *v116; // rbx
  int v117; // r13d
  int v118; // eax
  _WORD *v119; // rcx
  _QWORD *v120; // rdx
  _WORD *v121; // rbx
  __int64 v122; // rax
  unsigned __int64 v123; // r14
  unsigned __int64 v124; // r15
  __int16 v125; // ax
  _QWORD *v126; // rdx
  _QWORD *v127; // r11
  _QWORD *v128; // rcx
  unsigned int v132; // r11d
  char v134; // al
  unsigned int j; // r11d
  char *v136; // rax
  unsigned __int64 v137; // rcx
  __int64 v138; // rcx
  char *v139; // r11
  char *v140; // rbp
  char *v141; // r10
  char *v142; // rbx
  char *v143; // r15
  unsigned __int64 v144; // rdx
  char *v145; // rdi
  int v146; // eax
  int k; // r13d
  int v148; // r12d
  char *v149; // r11
  unsigned __int64 v150; // rdx
  unsigned int v151; // r12d
  unsigned int *v152; // rax
  __int64 v153; // rdx
  __int64 v154; // rcx
  char *v155; // r10
  __int64 v156; // rcx
  char *v157; // rdi
  _BYTE *v158; // rbx
  int v159; // r13d
  int v160; // eax
  _WORD *v161; // rcx
  _QWORD *v162; // rdx
  _WORD *v163; // rbx
  __int64 v164; // rax
  unsigned __int64 v165; // r15
  unsigned __int64 v166; // r12
  __int16 v167; // ax
  _QWORD *v168; // rdx
  _QWORD *v169; // r10
  _QWORD *v170; // rcx
  unsigned int v174; // r10d
  char v176; // al
  unsigned int v177; // r10d
  __int64 v178; // rdx
  unsigned __int64 v179; // rcx
  __int64 v180; // rax
  size_t v181; // rbp
  unsigned __int64 v182; // rax
  void *v183; // rbx
  unsigned int *inited; // [rsp+20h] [rbp-78h]
  char *v186; // [rsp+28h] [rbp-70h]
  char *v187; // [rsp+28h] [rbp-70h]
  char *v188; // [rsp+28h] [rbp-70h]
  char *v189; // [rsp+28h] [rbp-70h]
  char *v190; // [rsp+30h] [rbp-68h]
  char *v191; // [rsp+30h] [rbp-68h]
  char *v192; // [rsp+30h] [rbp-68h]
  char *v193; // [rsp+38h] [rbp-60h]
  int v194; // [rsp+B0h] [rbp+18h]
  int v195; // [rsp+C0h] [rbp+28h]
  int v196; // [rsp+C0h] [rbp+28h]
  int v197; // [rsp+C0h] [rbp+28h]
  int v198; // [rsp+C0h] [rbp+28h]

  v194 = (int)a3;
  v5 = a4;
  v6 = a3;
  inited = (unsigned int *)LZ4_initStream();
  v8 = LZ4_compressBound((unsigned int)v5);
  v9 = 0;
  if ( a5 < v8 )
  {
    if ( (int)v5 < 65547 )
    {
      if ( (unsigned int)v5 > 0x7E000000 )
        return v9;
      if ( !(_DWORD)v5 )
      {
        if ( a5 <= 0 )
          return v9;
        goto LABEL_5;
      }
      v99 = inited[4100];
      v100 = &v6[a5];
      inited[4102] += v5;
      v101 = &a2[v5];
      v191 = v100;
      v12 = v6;
      inited[4101] = 3;
      inited[4100] = v99 + v5;
      if ( (int)v5 >= 13 )
      {
        v102 = &a2[-v99];
        v197 = 0;
        v188 = &a2[-v99];
        v193 = a2;
        *((_WORD *)inited + ((unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)a2) >> 19)) = v99;
        v103 = a2 + 1;
LABEL_126:
        v104 = -1640531535 * *(_DWORD *)v103;
        v105 = v103;
        v106 = 1;
        for ( i = 64; ; ++i )
        {
          v108 = v105;
          v109 = v104 >> 19;
          v110 = v105;
          v111 = (_WORD)v105 - (_WORD)v102;
          v105 += v106;
          if ( v105 > v101 - 11 )
            break;
          v112 = *(_DWORD *)v105;
          v113 = &v102[*((unsigned __int16 *)inited + v109)];
          *((_WORD *)inited + v109) = v111;
          if ( *(_DWORD *)v113 == *(_DWORD *)v110 )
          {
            if ( v113 > v193 && *(v108 - 1) == *(v113 - 1) )
            {
              do
              {
                --v110;
                --v113;
              }
              while ( v110 > a2 && v113 > v193 && *(v110 - 1) == *(v113 - 1) );
            }
            v100 = v191;
            v114 = (unsigned int)((_DWORD)v110 - (_DWORD)a2);
            v115 = v12;
            v116 = v12 + 1;
            if ( &v116[v114 + 8 + (unsigned int)v114 / 0xFF] > v191 )
              return v9;
            v117 = v197;
            if ( (unsigned int)v114 < 0xF )
            {
              *v115 = 16 * ((_BYTE)v110 - (_BYTE)a2);
            }
            else
            {
              v118 = v114 - 15;
              *v115 = -16;
              while ( v118 >= 255 )
              {
                *v116++ = -1;
                v118 -= 255;
              }
              *v116++ = v118;
            }
            v119 = &v116[v114];
            v120 = v116;
            v121 = v119;
            do
            {
              v122 = *(_QWORD *)a2;
              a2 += 8;
              *v120++ = v122;
            }
            while ( v120 < (_QWORD *)v119 );
            v123 = (unsigned __int64)(v101 - 5);
            v124 = (unsigned __int64)(v101 - 12);
            while ( 2 )
            {
              v197 = v117;
              v125 = (_WORD)v110 - (_WORD)v113;
              v126 = v113 + 4;
              v127 = v110 + 4;
              *v121 = v125;
              v12 = (char *)(v121 + 1);
              v128 = v110 + 4;
              if ( (unsigned __int64)(v110 + 4) >= v124 )
              {
LABEL_147:
                v197 = v117;
                while ( (unsigned __int64)v128 < v124 )
                {
                  if ( *v126 != *v128 )
                  {
                    __asm { tzcnt   rax, rax }
                    v132 = (_DWORD)v128 + ((unsigned int)_RAX >> 3) - (_DWORD)v127;
                    goto LABEL_163;
                  }
                  ++v128;
                  ++v126;
                }
                if ( (unsigned __int64)v128 < v123 - 3 && *(_DWORD *)v126 == *(_DWORD *)v128 )
                {
                  v128 = (_QWORD *)((char *)v128 + 4);
                  v126 = (_QWORD *)((char *)v126 + 4);
                }
                if ( (unsigned __int64)v128 < v123 - 1 && *(_WORD *)v126 == *(_WORD *)v128 )
                {
                  v128 = (_QWORD *)((char *)v128 + 2);
                  v126 = (_QWORD *)((char *)v126 + 2);
                }
                if ( (unsigned __int64)v128 < v123 && *(_BYTE *)v126 == *(_BYTE *)v128 )
                  LODWORD(v128) = (_DWORD)v128 + 1;
                v132 = (_DWORD)v128 - (_DWORD)v127;
              }
              else
              {
                if ( *v126 == *v127 )
                {
                  v128 = v110 + 12;
                  ++v126;
                  goto LABEL_147;
                }
                __asm { tzcnt   r11, rax }
                v132 = (unsigned int)_R11 >> 3;
              }
LABEL_163:
              v110 += v132 + 4;
              if ( &v12[(v132 + 240) / 0xFF + 6] > v191 )
                return v9;
              v134 = *v115;
              if ( v132 < 0xF )
              {
                *v115 = v134 + v132;
              }
              else
              {
                *v115 = v134 + 15;
                for ( j = v132 - 15; ; j -= 1020 )
                {
                  *(_DWORD *)v12 = -1;
                  if ( j < 0x3FC )
                    break;
                  v12 += 4;
                }
                v136 = &v12[j / 0xFF];
                *v136 = j + j / 0xFF;
                v12 = v136 + 1;
              }
              a2 = v110;
              if ( v110 >= v101 - 11 )
                goto LABEL_175;
              *((_WORD *)inited + ((unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)(v110 - 2)) >> 19)) = (_WORD)v110 - (_WORD)v188 - 2;
              v137 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)v110) >> 19;
              v113 = &v188[*((unsigned __int16 *)inited + v137)];
              *((_WORD *)inited + v137) = (_WORD)v110 - (_WORD)v188;
              if ( *(_DWORD *)v113 != *(_DWORD *)v110 )
              {
                v102 = v188;
                v103 = v110 + 1;
                goto LABEL_126;
              }
              v115 = v12;
              v123 = (unsigned __int64)(v101 - 5);
              v121 = v12 + 1;
              *v115 = 0;
              continue;
            }
          }
          v102 = v188;
          v106 = i >> 6;
          v104 = -1640531535 * v112;
        }
        v100 = v191;
LABEL_175:
        LODWORD(v6) = v194;
      }
      v50 = v101 - a2;
      if ( &v12[v50 + 1 + (v50 + 240) / 0xFF] > v100 )
        return v9;
      if ( v50 >= 0xF )
      {
        *v12 = -16;
        v51 = v50 - 15;
        ++v12;
        while ( v51 >= 0xFF )
        {
          *v12++ = -1;
          v51 -= 255LL;
        }
        goto LABEL_61;
      }
      goto LABEL_60;
    }
    if ( (unsigned int)v5 > 0x7E000000 )
      return v9;
    v138 = inited[4100];
    inited[4102] += v5;
    v139 = a2 + 1;
    v192 = &v6[a5];
    v140 = &a2[v5];
    inited[4101] = 2;
    v198 = 0;
    inited[4100] = v138 + v5;
    v141 = &a2[-v138];
    v142 = v6;
    v189 = &a2[-v138];
    inited[(0xCF1BBCDCBB000000uLL * *(_QWORD *)a2) >> 52] = v138;
    v143 = a2;
    v144 = 0xCF1BBCDCBB000000uLL * *(_QWORD *)(a2 + 1);
LABEL_184:
    v145 = v139;
    v146 = 1;
    for ( k = 64; ; ++k )
    {
      v148 = (int)v145;
      v149 = v145;
      v150 = v144 >> 52;
      v145 += v146;
      v151 = v148 - (_DWORD)v141;
      if ( v145 > v140 - 11 )
        break;
      v152 = &inited[v150];
      v153 = *(_QWORD *)v145;
      v154 = *v152;
      *v152 = v151;
      v155 = &v141[v154];
      if ( (int)v154 + 0xFFFF >= v151 && *(_DWORD *)v155 == *(_DWORD *)v149 )
      {
        if ( v155 > a2 )
        {
          do
          {
            if ( *(v149 - 1) != *(v155 - 1) )
              break;
            --v149;
            --v155;
          }
          while ( v149 > v143 && v155 > a2 );
        }
        v156 = (unsigned int)((_DWORD)v149 - (_DWORD)v143);
        v157 = v142;
        v158 = v142 + 1;
        if ( &v158[v156 + 8 + (unsigned int)v156 / 0xFF] > v192 )
          return v9;
        v159 = v198;
        if ( (unsigned int)v156 < 0xF )
        {
          *v157 = 16 * ((_BYTE)v149 - (_BYTE)v143);
        }
        else
        {
          v160 = v156 - 15;
          *v157 = -16;
          while ( v160 >= 255 )
          {
            *v158++ = -1;
            v160 -= 255;
          }
          *v158++ = v160;
        }
        v161 = &v158[v156];
        v162 = v158;
        v163 = v161;
        do
        {
          v164 = *(_QWORD *)v143;
          v143 += 8;
          *v162++ = v164;
        }
        while ( v162 < (_QWORD *)v161 );
        v165 = (unsigned __int64)(v140 - 5);
        v166 = (unsigned __int64)(v140 - 12);
LABEL_203:
        v198 = v159;
        v167 = (_WORD)v149 - (_WORD)v155;
        v168 = v155 + 4;
        v169 = v149 + 4;
        *v163 = v167;
        v142 = (char *)(v163 + 1);
        v170 = v149 + 4;
        if ( (unsigned __int64)(v149 + 4) >= v166 )
        {
LABEL_206:
          v198 = v159;
          while ( (unsigned __int64)v170 < v166 )
          {
            if ( *v168 != *v170 )
            {
              __asm { tzcnt   rax, rax }
              v174 = (_DWORD)v170 + ((unsigned int)_RAX >> 3) - (_DWORD)v169;
              goto LABEL_222;
            }
            ++v170;
            ++v168;
          }
          if ( (unsigned __int64)v170 < v165 - 3 && *(_DWORD *)v168 == *(_DWORD *)v170 )
          {
            v170 = (_QWORD *)((char *)v170 + 4);
            v168 = (_QWORD *)((char *)v168 + 4);
          }
          if ( (unsigned __int64)v170 < v165 - 1 && *(_WORD *)v168 == *(_WORD *)v170 )
          {
            v170 = (_QWORD *)((char *)v170 + 2);
            v168 = (_QWORD *)((char *)v168 + 2);
          }
          if ( (unsigned __int64)v170 < v165 && *(_BYTE *)v168 == *(_BYTE *)v170 )
            LODWORD(v170) = (_DWORD)v170 + 1;
          v174 = (_DWORD)v170 - (_DWORD)v169;
        }
        else
        {
          if ( *v169 == *v168 )
          {
            v170 = v149 + 12;
            ++v168;
            goto LABEL_206;
          }
          __asm { tzcnt   r10, rax }
          v174 = (unsigned int)_R10 >> 3;
        }
LABEL_222:
        v149 += v174 + 4;
        if ( &v142[(v174 + 240) / 0xFF + 6] > v192 )
          return v9;
        v176 = *v157;
        if ( v174 < 0xF )
        {
          *v157 = v176 + v174;
        }
        else
        {
          v177 = v174 - 15;
          *v157 = v176 + 15;
          while ( 1 )
          {
            *(_DWORD *)v142 = -1;
            if ( v177 < 0x3FC )
              break;
            v142 += 4;
            v177 -= 1020;
          }
          v178 = v177 / 0xFF;
          v142[v178] = v178 + v177;
          v142 += v178 + 1;
        }
        v143 = v149;
        if ( v149 >= v140 - 11 )
          break;
        inited[(0xCF1BBCDCBB000000uLL * *(_QWORD *)(v149 - 2)) >> 52] = (_DWORD)v149 - (_DWORD)v189 - 2;
        v179 = (0xCF1BBCDCBB000000uLL * *(_QWORD *)v149) >> 52;
        v180 = inited[v179];
        v155 = &v189[v180];
        inited[v179] = (_DWORD)v149 - (_DWORD)v189;
        if ( (int)v180 + 0xFFFF < (unsigned int)((_DWORD)v149 - (_DWORD)v189) || *(_DWORD *)v155 != *(_DWORD *)v149 )
        {
          v141 = v189;
          v139 = v149 + 1;
          v144 = 0xCF1BBCDCBB000000uLL * *(_QWORD *)v139;
          goto LABEL_184;
        }
        v157 = v142;
        v165 = (unsigned __int64)(v140 - 5);
        v163 = v142 + 1;
        *v157 = 0;
        goto LABEL_203;
      }
      v141 = v189;
      v146 = k >> 6;
      v144 = 0xCF1BBCDCBB000000uLL * v153;
    }
    v181 = v140 - v143;
    if ( &v142[(v181 + 240) / 0xFF + 1 + v181] > v192 )
      return v9;
    if ( v181 < 0xF )
    {
      LOBYTE(v182) = 16 * v181;
    }
    else
    {
      *v142 = -16;
      v182 = v181 - 15;
      ++v142;
      while ( v182 >= 0xFF )
      {
        *v142++ = -1;
        v182 -= 255LL;
      }
    }
    *v142 = v182;
    v183 = v142 + 1;
    memmove(v183, v143, v181);
    v98 = (_DWORD)v183 + v181;
    return (unsigned int)(v98 - v194);
  }
  if ( (int)v5 >= 65547 )
  {
    if ( (unsigned int)v5 > 0x7E000000 )
      return v9;
    v53 = inited[4100];
    v54 = a2 + 1;
    inited[4102] += v5;
    inited[4101] = 2;
    v55 = &a2[-v53];
    v196 = 0;
    v187 = &a2[-v53];
    inited[4100] = v53 + v5;
    v56 = v6;
    v57 = &a2[v5];
    inited[(0xCF1BBCDCBB000000uLL * *(_QWORD *)a2) >> 52] = v53;
    v58 = a2;
    v59 = 0xCF1BBCDCBB000000uLL * *(_QWORD *)(a2 + 1);
LABEL_64:
    v60 = v54;
    v61 = 1;
    for ( m = 64; ; ++m )
    {
      v63 = (int)v60;
      v64 = v60;
      v65 = v59 >> 52;
      v60 += v61;
      v66 = v63 - (_DWORD)v55;
      if ( v60 > v57 - 11 )
        break;
      v67 = &inited[v65];
      v68 = *(_QWORD *)v60;
      v69 = *v67;
      *v67 = v66;
      v70 = &v55[v69];
      if ( (int)v69 + 0xFFFF >= v66 && *(_DWORD *)v70 == *(_DWORD *)v64 )
      {
        v71 = v196;
        if ( v70 > a2 )
        {
          do
          {
            if ( *(v64 - 1) != *(v70 - 1) )
              break;
            --v64;
            --v70;
          }
          while ( v70 > a2 && v64 > v58 );
        }
        v72 = v56;
        v73 = v56 + 1;
        if ( (unsigned int)((_DWORD)v64 - (_DWORD)v58) < 0xF )
        {
          *v72 = 16 * ((_BYTE)v64 - (_BYTE)v58);
        }
        else
        {
          v74 = (_DWORD)v64 - (_DWORD)v58 - 15;
          *v72 = -16;
          while ( v74 >= 255 )
          {
            *v73++ = -1;
            v74 -= 255;
          }
          *v73++ = v74;
        }
        v75 = &v73[(_DWORD)v64 - (_DWORD)v58];
        v76 = v73;
        v77 = v75;
        do
        {
          v78 = *(_QWORD *)v58;
          v58 += 8;
          *v76++ = v78;
        }
        while ( v76 < (_QWORD *)v75 );
        v79 = (unsigned __int64)(v57 - 5);
        v80 = (unsigned __int64)(v57 - 12);
        while ( 1 )
        {
          v196 = v71;
          v81 = (_WORD)v64 - (_WORD)v70;
          v82 = v70 + 4;
          v83 = v64 + 4;
          *v77 = v81;
          v56 = (char *)(v77 + 1);
          v84 = v64 + 4;
          if ( (unsigned __int64)(v64 + 4) < v80 )
          {
            if ( *v83 != *v82 )
            {
              __asm { tzcnt   rcx, rax }
              v88 = (unsigned int)_RCX >> 3;
              goto LABEL_101;
            }
            v84 = v64 + 12;
            ++v82;
          }
          v196 = v71;
          while ( (unsigned __int64)v84 < v80 )
          {
            if ( *v82 != *v84 )
            {
              __asm { tzcnt   rax, rax }
              v88 = ((unsigned int)_RAX >> 3) - (_DWORD)v83 + (_DWORD)v84;
              goto LABEL_101;
            }
            ++v84;
            ++v82;
          }
          if ( (unsigned __int64)v84 < v79 - 3 && *(_DWORD *)v82 == *(_DWORD *)v84 )
          {
            v84 = (_QWORD *)((char *)v84 + 4);
            v82 = (_QWORD *)((char *)v82 + 4);
          }
          if ( (unsigned __int64)v84 < v79 - 1 && *(_WORD *)v82 == *(_WORD *)v84 )
          {
            v84 = (_QWORD *)((char *)v84 + 2);
            v82 = (_QWORD *)((char *)v82 + 2);
          }
          if ( (unsigned __int64)v84 < v79 && *(_BYTE *)v82 == *(_BYTE *)v84 )
            LODWORD(v84) = (_DWORD)v84 + 1;
          v88 = (_DWORD)v84 - (_DWORD)v83;
LABEL_101:
          v64 += v88 + 4;
          v90 = *v72;
          if ( v88 < 0xF )
          {
            *v72 = v90 + v88;
          }
          else
          {
            v91 = v88 - 15;
            *v72 = v90 + 15;
            while ( 1 )
            {
              *(_DWORD *)v56 = -1;
              if ( v91 < 0x3FC )
                break;
              v56 += 4;
              v91 -= 1020;
            }
            v92 = v91 / 0xFF;
            v56[v92] = v92 + v91;
            v56 += v92 + 1;
          }
          v58 = v64;
          if ( v64 >= v57 - 11 )
            goto LABEL_112;
          inited[(0xCF1BBCDCBB000000uLL * *(_QWORD *)(v64 - 2)) >> 52] = (_DWORD)v64 - (_DWORD)v187 - 2;
          v93 = (0xCF1BBCDCBB000000uLL * *(_QWORD *)v64) >> 52;
          v94 = inited[v93];
          v70 = &v187[v94];
          inited[v93] = (_DWORD)v64 - (_DWORD)v187;
          if ( (int)v94 + 0xFFFF < (unsigned int)((_DWORD)v64 - (_DWORD)v187) || *(_DWORD *)v70 != *(_DWORD *)v64 )
          {
            v55 = v187;
            v54 = v64 + 1;
            v59 = 0xCF1BBCDCBB000000uLL * *(_QWORD *)v54;
            goto LABEL_64;
          }
          v72 = v56;
          v79 = (unsigned __int64)(v57 - 5);
          v77 = v56 + 1;
          *v72 = 0;
        }
      }
      v55 = v187;
      v61 = m >> 6;
      v59 = 0xCF1BBCDCBB000000uLL * v68;
    }
LABEL_112:
    v95 = v57 - v58;
    if ( v95 < 0xF )
    {
      LOBYTE(v96) = 16 * v95;
    }
    else
    {
      *v56 = -16;
      v96 = v95 - 15;
      ++v56;
      while ( v96 >= 0xFF )
      {
        *v56++ = -1;
        v96 -= 255LL;
      }
    }
    *v56 = v96;
    v97 = v56 + 1;
    memmove(v97, v58, v95);
    v98 = (_DWORD)v97 + v95;
    return (unsigned int)(v98 - v194);
  }
  if ( (unsigned int)v5 <= 0x7E000000 )
  {
    if ( !(_DWORD)v5 )
    {
LABEL_5:
      *v6 = 0;
      return 1;
    }
    v10 = inited[4100];
    v11 = &a2[v5];
    inited[4102] += v5;
    v12 = v6;
    inited[4101] = 3;
    inited[4100] = v10 + v5;
    if ( (int)v5 >= 13 )
    {
      v13 = &a2[-v10];
      v195 = 0;
      v186 = &a2[-v10];
      v190 = a2;
      v14 = a2 + 1;
      *((_WORD *)inited + ((unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)a2) >> 19)) = v10;
LABEL_8:
      v15 = -1640531535 * *(_DWORD *)v14;
      v16 = v14;
      v17 = 1;
      v18 = 64;
      while ( 1 )
      {
        v19 = v16;
        v20 = v15 >> 19;
        v21 = v16;
        v22 = (_WORD)v16 - (_WORD)v13;
        v16 += v17;
        if ( v16 > v11 - 11 )
          break;
        v23 = &v13[*((unsigned __int16 *)inited + v20)];
        v24 = *(_DWORD *)v16;
        *((_WORD *)inited + v20) = v22;
        if ( *(_DWORD *)v23 == *(_DWORD *)v21 )
        {
          v26 = v195;
          if ( v23 > v190 && *(v19 - 1) == *(v23 - 1) )
          {
            do
            {
              --v21;
              --v23;
            }
            while ( v21 > a2 && v23 > v190 && *(v21 - 1) == *(v23 - 1) );
          }
          v27 = v12;
          v28 = v12 + 1;
          if ( (unsigned int)((_DWORD)v21 - (_DWORD)a2) < 0xF )
          {
            *v27 = 16 * ((_BYTE)v21 - (_BYTE)a2);
          }
          else
          {
            v29 = (_DWORD)v21 - (_DWORD)a2 - 15;
            *v27 = -16;
            while ( v29 >= 255 )
            {
              *v28++ = -1;
              v29 -= 255;
            }
            *v28++ = v29;
          }
          v30 = &v28[(_DWORD)v21 - (_DWORD)a2];
          v31 = v28;
          v32 = v30;
          do
          {
            v33 = *(_QWORD *)a2;
            a2 += 8;
            *v31++ = v33;
          }
          while ( v31 < (_QWORD *)v30 );
          v34 = (unsigned __int64)(v11 - 5);
          v35 = (unsigned __int64)(v11 - 12);
          while ( 1 )
          {
            v36 = v21 + 4;
            v195 = v26;
            v37 = v21 + 4;
            v38 = (_WORD)v21 - (_WORD)v23;
            v39 = v23 + 4;
            *v32 = v38;
            v12 = (char *)(v32 + 1);
            if ( (unsigned __int64)(v21 + 4) < v35 )
            {
              if ( *v39 != *v36 )
              {
                __asm { tzcnt   rcx, rax }
                v43 = (unsigned int)_RCX >> 3;
                goto LABEL_44;
              }
              v37 = v21 + 12;
              ++v39;
            }
            v195 = v26;
            while ( (unsigned __int64)v37 < v35 )
            {
              if ( *v39 != *v37 )
              {
                __asm { tzcnt   rax, rax }
                v43 = ((unsigned int)_RAX >> 3) - (_DWORD)v36 + (_DWORD)v37;
                goto LABEL_44;
              }
              ++v37;
              ++v39;
            }
            if ( (unsigned __int64)v37 < v34 - 3 && *(_DWORD *)v39 == *(_DWORD *)v37 )
            {
              v37 = (_QWORD *)((char *)v37 + 4);
              v39 = (_QWORD *)((char *)v39 + 4);
            }
            if ( (unsigned __int64)v37 < v34 - 1 && *(_WORD *)v39 == *(_WORD *)v37 )
            {
              v37 = (_QWORD *)((char *)v37 + 2);
              v39 = (_QWORD *)((char *)v39 + 2);
            }
            if ( (unsigned __int64)v37 < v34 && *(_BYTE *)v39 == *(_BYTE *)v37 )
              LODWORD(v37) = (_DWORD)v37 + 1;
            v43 = (_DWORD)v37 - (_DWORD)v36;
LABEL_44:
            v21 += v43 + 4;
            v45 = *v27;
            if ( v43 < 0xF )
            {
              *v27 = v45 + v43;
            }
            else
            {
              v46 = v43 - 15;
              *v27 = v45 + 15;
              while ( 1 )
              {
                *(_DWORD *)v12 = -1;
                if ( v46 < 0x3FC )
                  break;
                v12 += 4;
                v46 -= 1020;
              }
              v47 = &v12[v46 / 0xFF];
              *v47 = v46 + v46 / 0xFF;
              v12 = v47 + 1;
            }
            a2 = v21;
            if ( v21 >= v11 - 11 )
              goto LABEL_54;
            *((_WORD *)inited + ((unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)(v21 - 2)) >> 19)) = (_WORD)v21 - (_WORD)v186 - 2;
            v48 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)v21) >> 19;
            v49 = *((unsigned __int16 *)inited + v48);
            *((_WORD *)inited + v48) = (_WORD)v21 - (_WORD)v186;
            v23 = &v186[v49];
            if ( *(_DWORD *)v23 != *(_DWORD *)v21 )
            {
              v13 = v186;
              v14 = v21 + 1;
              goto LABEL_8;
            }
            v27 = v12;
            v34 = (unsigned __int64)(v11 - 5);
            v32 = v12 + 1;
            *v27 = 0;
          }
        }
        v25 = v18++;
        v17 = v25 >> 6;
        v15 = -1640531535 * v24;
        v13 = v186;
      }
LABEL_54:
      LODWORD(v6) = v194;
    }
    v50 = v11 - a2;
    if ( v50 >= 0xF )
    {
      *v12 = -16;
      v51 = v50 - 15;
      ++v12;
      while ( v51 >= 0xFF )
      {
        *v12++ = -1;
        v51 -= 255LL;
      }
      goto LABEL_61;
    }
LABEL_60:
    LOBYTE(v51) = 16 * v50;
LABEL_61:
    *v12 = v51;
    v52 = v12 + 1;
    memmove(v52, a2, v50);
    return (unsigned int)((_DWORD)v52 + v50 - (_DWORD)v6);
  }
  return v9;
}

```

## disassembly

```asm
0x180106dc8  mov     [rsp+arg_10], r8
0x180106dcd  push    rbx
0x180106dce  push    rbp
0x180106dcf  push    rsi
0x180106dd0  push    rdi
0x180106dd1  push    r12
0x180106dd3  push    r13
0x180106dd5  push    r14
0x180106dd7  push    r15
0x180106dd9  sub     rsp, 58h
0x180106ddd  movsxd  rdi, r9d
0x180106de0  mov     r13, r8
0x180106de3  mov     r14, rdx
0x180106de6  call    LZ4_initStream
0x180106deb  mov     ecx, edi
0x180106ded  mov     [rsp+98h+var_78], rax
0x180106df2  mov     r15, rax
0x180106df5  call    LZ4_compressBound
0x180106dfa  movsxd  rdx, [rsp+98h+arg_20]
0x180106e02  xor     r8d, r8d
0x180106e05  cmp     edx, eax
0x180106e07  jl      loc_1801074DB
0x180106e0d  cmp     edi, 1000Bh
0x180106e13  jge     loc_180107175
0x180106e19  cmp     edi, 7E000000h
0x180106e1f  ja      loc_180107CA0
0x180106e25  test    edi, edi
0x180106e27  jnz     short loc_180106E38
0x180106e29  mov     [r13+0], r8b
0x180106e2d  mov     r8d, 1
0x180106e33  jmp     loc_180107CA0
0x180106e38  mov     edx, [r15+4010h]
0x180106e3f  lea     rbp, [r14+rdi]
0x180106e43  add     [r15+4018h], edi
0x180106e4a  mov     rbx, r13
0x180106e4d  mov     dword ptr [r15+4014h], 3
0x180106e58  mov     esi, 0FFh
0x180106e5d  mov     r9d, 1
0x180106e63  lea     eax, [rdx+rdi]
0x180106e66  mov     [r15+4010h], eax
0x180106e6d  cmp     edi, 0Dh
0x180106e70  jl      loc_18010712B
0x180106e76  imul    ecx, [r14], 9E3779B1h
0x180106e7d  mov     r12, r14
0x180106e80  sub     r12, rdx
0x180106e83  mov     [rsp+98h+arg_20], r8d
0x180106e8b  mov     r10, r14
0x180106e8e  mov     [rsp+98h+var_70], r12
0x180106e93  mov     [rsp+98h+var_68], r14
0x180106e98  shr     rcx, 13h
0x180106e9c  inc     r10
0x180106e9f  mov     [r15+rcx*2], dx
0x180106ea4  imul    ecx, [r10], 9E3779B1h
0x180106eab  mov     r11, r10
0x180106eae  mov     eax, r9d
0x180106eb1  mov     edi, 40h ; '@'
0x180106eb6  cdqe
0x180106eb8  mov     r15d, r11d
0x180106ebb  mov     r13, r11
0x180106ebe  shr     ecx, 13h
0x180106ec1  mov     r10, r11
0x180106ec4  sub     r15d, r12d
0x180106ec7  add     r11, rax
0x180106eca  lea     rax, [rbp-0Bh]
0x180106ece  cmp     r11, rax
0x180106ed1  ja      loc_180107123
0x180106ed7  mov     rax, [rsp+98h+var_78]
0x180106edc  movzx   edx, word ptr [rax+rcx*2]
0x180106ee0  add     rdx, r12
0x180106ee3  mov     r12d, [r11]
0x180106ee6  mov     [rax+rcx*2], r15w
0x180106eeb  mov     eax, [r10]
0x180106eee  cmp     [rdx], eax
0x180106ef0  jz      short loc_180106F08
0x180106ef2  mov     eax, edi
0x180106ef4  add     edi, r9d
0x180106ef7  sar     eax, 6
0x180106efa  imul    ecx, r12d, 9E3779B1h
0x180106f01  mov     r12, [rsp+98h+var_70]
0x180106f06  jmp     short loc_180106EB6
0x180106f08  mov     r11, [rsp+98h+var_68]
0x180106f0d  mov     r12d, [rsp+98h+arg_20]
0x180106f15  cmp     rdx, r11
0x180106f18  jbe     short loc_180106F48
0x180106f1a  mov     al, [rdx-1]
0x180106f1d  cmp     [r13-1], al
0x180106f21  jnz     short loc_180106F48
0x180106f23  sub     r10, r9
0x180106f26  sub     rdx, r9
0x180106f29  cmp     r10, r14
0x180106f2c  mov     ecx, r8d
0x180106f2f  mov     eax, r8d
0x180106f32  setnbe  cl
0x180106f35  cmp     rdx, r11
0x180106f38  setnbe  al
0x180106f3b  test    eax, ecx
0x180106f3d  jz      short loc_180106F48
0x180106f3f  mov     al, [rdx-1]
0x180106f42  cmp     [r10-1], al
0x180106f46  jz      short loc_180106F23
0x180106f48  mov     eax, r10d
0x180106f4b  mov     rdi, rbx
0x180106f4e  sub     eax, r14d
0x180106f51  add     rbx, r9
0x180106f54  mov     r11d, eax
0x180106f57  cmp     eax, 0Fh
0x180106f5a  jb      short loc_180106F77
0x180106f5c  add     eax, 0FFFFFFF1h
0x180106f5f  mov     byte ptr [rdi], 0F0h
0x180106f62  jmp     short loc_180106F6C
0x180106f64  mov     [rbx], sil
0x180106f67  add     rbx, r9
0x180106f6a  sub     eax, esi
0x180106f6c  cmp     eax, esi
0x180106f6e  jge     short loc_180106F64
0x180106f70  mov     [rbx], al
0x180106f72  add     rbx, r9
0x180106f75  jmp     short loc_180106F7F
0x180106f77  mov     al, r11b
0x180106f7a  shl     al, 4
0x180106f7d  mov     [rdi], al
0x180106f7f  add     r11, rbx
0x180106f82  mov     rcx, rbx
0x180106f85  mov     rbx, r11
0x180106f88  mov     rax, [r14]
0x180106f8b  lea     r14, [r14+8]
0x180106f8f  mov     [rcx], rax
0x180106f92  add     rcx, 8
0x180106f96  cmp     rcx, r11
0x180106f99  jb      short loc_180106F88
0x180106f9b  lea     r14, [rbp-5]
0x180106f9f  lea     r15, [r14-7]
0x180106fa3  mov     r13, [rsp+98h+var_70]
0x180106fa8  lea     r11, [r10+4]
0x180106fac  mov     [rsp+98h+arg_20], r12d
0x180106fb4  movzx   eax, r10w
0x180106fb8  mov     rcx, r11
0x180106fbb  sub     ax, dx
0x180106fbe  add     rdx, 4
0x180106fc2  mov     [rbx], ax
0x180106fc5  add     rbx, 2
0x180106fc9  cmp     r11, r15
0x180106fcc  jnb     short loc_180106FDE
0x180106fce  mov     rax, [r11]
0x180106fd1  xor     rax, [rdx]
0x180106fd4  jnz     short loc_180106FFD
0x180106fd6  lea     rcx, [r11+8]
0x180106fda  add     rdx, 8
0x180106fde  mov     [rsp+98h+arg_20], r12d
0x180106fe6  cmp     rcx, r15
0x180106fe9  jnb     short loc_180107016
0x180106feb  mov     rax, [rcx]
0x180106fee  xor     rax, [rdx]
0x180106ff1  jnz     short loc_180107007
0x180106ff3  add     rcx, 8
0x180106ff7  add     rdx, 8
0x180106ffb  jmp     short loc_180106FE6
0x180106ffd  tzcnt   rcx, rax
0x180107002  shr     ecx, 3
0x180107005  jmp     short loc_18010705A
0x180107007  tzcnt   rax, rax
0x18010700c  shr     eax, 3
0x18010700f  sub     eax, r11d
0x180107012  add     ecx, eax
0x180107014  jmp     short loc_18010705A
0x180107016  lea     rax, [r14-3]
0x18010701a  cmp     rcx, rax
0x18010701d  jnb     short loc_18010702D
0x18010701f  mov     eax, [rcx]
0x180107021  cmp     [rdx], eax
0x180107023  jnz     short loc_18010702D
0x180107025  add     rcx, 4
0x180107029  add     rdx, 4
0x18010702d  lea     rax, [r14-1]
0x180107031  cmp     rcx, rax
0x180107034  jnb     short loc_180107049
0x180107036  movzx   eax, word ptr [rcx]
0x180107039  cmp     [rdx], ax
0x18010703c  jnz     short loc_180107049
0x18010703e  mov     eax, 2
0x180107043  add     rcx, rax
0x180107046  add     rdx, rax
0x180107049  cmp     rcx, r14
0x18010704c  jnb     short loc_180107057
0x18010704e  mov     al, [rcx]
0x180107050  cmp     [rdx], al
0x180107052  jnz     short loc_180107057
0x180107054  add     rcx, r9
0x180107057  sub     ecx, r11d
0x18010705a  mov     eax, ecx
0x18010705c  add     r10, 4
0x180107060  add     r10, rax
0x180107063  mov     al, [rdi]
0x180107065  cmp     ecx, 0Fh
0x180107068  jb      short loc_1801070AB
0x18010706a  add     al, 0Fh
0x18010706c  lea     r11d, [rcx-0Fh]
0x180107070  mov     [rdi], al
0x180107072  mov     eax, 3FCh
0x180107077  jmp     short loc_180107084
0x180107079  add     rbx, 4
0x18010707d  add     r11d, 0FFFFFC04h
0x180107084  mov     dword ptr [rbx], 0FFFFFFFFh
0x18010708a  cmp     r11d, eax
0x18010708d  jnb     short loc_180107079
0x18010708f  mov     eax, 80808081h
0x180107094  mul     r11d
0x180107097  shr     edx, 7
0x18010709a  mov     ecx, edx
0x18010709c  add     cl, r11b
0x18010709f  lea     rax, [rdx+rbx]
0x1801070a3  mov     [rax], cl
0x1801070a5  lea     rbx, [rax+1]
0x1801070a9  jmp     short loc_1801070AF
0x1801070ab  add     cl, al
0x1801070ad  mov     [rdi], cl
0x1801070af  lea     rax, [rbp-0Bh]
0x1801070b3  mov     r14, r10
0x1801070b6  cmp     r10, rax
0x1801070b9  jnb     short loc_180107123
0x1801070bb  imul    ecx, [r10-2], 9E3779B1h
0x1801070c3  movzx   edx, r10w
0x1801070c7  mov     r11, [rsp+98h+var_78]
0x1801070cc  sub     dx, r13w
0x1801070d0  sub     dx, 2
0x1801070d4  movzx   eax, r10w
0x1801070d8  sub     ax, r13w
0x1801070dc  shr     rcx, 13h
0x1801070e0  mov     [r11+rcx*2], dx
0x1801070e5  imul    ecx, [r10], 9E3779B1h
0x1801070ec  shr     rcx, 13h
0x1801070f0  movzx   edx, word ptr [r11+rcx*2]
0x1801070f5  mov     [r11+rcx*2], ax
0x1801070fa  add     rdx, r13
0x1801070fd  mov     eax, [r10]
0x180107100  cmp     [rdx], eax
0x180107102  jnz     short loc_180107116
0x180107104  mov     rdi, rbx
0x180107107  lea     r14, [rbp-5]
0x18010710b  add     rbx, r9
0x18010710e  mov     [rdi], r8b
0x180107111  jmp     loc_180106FA8
0x180107116  mov     r12, [rsp+98h+var_70]
0x18010711b  add     r10, r9
0x18010711e  jmp     loc_180106EA4
0x180107123  mov     r13, [rsp+98h+arg_10]
0x18010712b  sub     rbp, r14
0x18010712e  cmp     rbp, 0Fh
0x180107132  jb      short loc_180107150
0x180107134  mov     byte ptr [rbx], 0F0h
0x180107137  lea     rax, [rbp-0Fh]
0x18010713b  add     rbx, r9
0x18010713e  jmp     short loc_180107149
0x180107140  mov     [rbx], sil
0x180107143  add     rbx, r9
0x180107146  sub     rax, rsi
0x180107149  cmp     rax, rsi
0x18010714c  jnb     short loc_180107140
0x18010714e  jmp     short loc_180107156
0x180107150  mov     al, bpl
0x180107153  shl     al, 4
0x180107156  mov     [rbx], al
0x180107158  mov     r8, rbp; Size
0x18010715b  inc     rbx
0x18010715e  mov     rdx, r14; Src
0x180107161  mov     rcx, rbx; void *
0x180107164  call    memmove
0x180107169  lea     r8, [rbx+rbp]
0x18010716d  sub     r8d, r13d
0x180107170  jmp     loc_180107CA0
0x180107175  cmp     edi, 7E000000h
0x18010717b  ja      loc_180107CA0
0x180107181  mov     ecx, [r15+4010h]
0x180107188  lea     r10, [r14+1]
0x18010718c  add     [r15+4018h], edi
0x180107193  mov     r9, 0CF1BBCDCBB000000h
0x18010719d  mov     dword ptr [r15+4014h], 2
0x1801071a8  mov     r11, r14
0x1801071ab  sub     r11, rcx
0x1801071ae  mov     [rsp+98h+arg_20], r8d
0x1801071b6  lea     eax, [rcx+rdi]
0x1801071b9  mov     [rsp+98h+var_70], r11
0x1801071be  mov     [r15+4010h], eax
0x1801071c5  mov     rbx, r13
0x1801071c8  mov     rax, [r14]
0x1801071cb  lea     r13, [r14+rdi]
0x1801071cf  imul    rax, r9
0x1801071d3  mov     esi, 0FFh
0x1801071d8  shr     rax, 34h
0x1801071dc  mov     [r15+rax*4], ecx
0x1801071e0  mov     r15, r14
0x1801071e3  mov     rdx, [r10]
0x1801071e6  imul    rdx, r9
0x1801071ea  mov     r9d, 1
0x1801071f0  mov     rdi, r10
0x1801071f3  mov     eax, r9d
0x1801071f6  mov     r12d, 40h ; '@'
0x1801071fc  cdqe
0x1801071fe  mov     ebp, edi
0x180107200  mov     r10, rdi
  ... truncated ...
```
