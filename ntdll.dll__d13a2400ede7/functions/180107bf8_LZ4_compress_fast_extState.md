# LZ4_compress_fast_extState

- ea: `0x180107bf8`
- end: `0x180108ae5`
- name: `LZ4_compress_fast_extState`
- size: `3821`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180152770`

## callees

- `0x180107bf8`
- `0x18011f360`
- `0x180120438`
- `0x180164280`

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
0x180107bf8  mov     [rsp+arg_10], r8
0x180107bfd  push    rbx
0x180107bfe  push    rbp
0x180107bff  push    rsi
0x180107c00  push    rdi
0x180107c01  push    r12
0x180107c03  push    r13
0x180107c05  push    r14
0x180107c07  push    r15
0x180107c09  sub     rsp, 58h
0x180107c0d  movsxd  rdi, r9d
0x180107c10  mov     r13, r8
0x180107c13  mov     r14, rdx
0x180107c16  call    LZ4_initStream
0x180107c1b  mov     ecx, edi
0x180107c1d  mov     [rsp+98h+var_78], rax
0x180107c22  mov     r15, rax
0x180107c25  call    LZ4_compressBound
0x180107c2a  movsxd  rdx, [rsp+98h+arg_20]
0x180107c32  xor     r8d, r8d
0x180107c35  cmp     edx, eax
0x180107c37  jl      loc_18010830B
0x180107c3d  cmp     edi, 1000Bh
0x180107c43  jge     loc_180107FA5
0x180107c49  cmp     edi, 7E000000h
0x180107c4f  ja      loc_180108AD0
0x180107c55  test    edi, edi
0x180107c57  jnz     short loc_180107C68
0x180107c59  mov     [r13+0], r8b
0x180107c5d  mov     r8d, 1
0x180107c63  jmp     loc_180108AD0
0x180107c68  mov     edx, [r15+4010h]
0x180107c6f  lea     rbp, [r14+rdi]
0x180107c73  add     [r15+4018h], edi
0x180107c7a  mov     rbx, r13
0x180107c7d  mov     dword ptr [r15+4014h], 3
0x180107c88  mov     esi, 0FFh
0x180107c8d  mov     r9d, 1
0x180107c93  lea     eax, [rdx+rdi]
0x180107c96  mov     [r15+4010h], eax
0x180107c9d  cmp     edi, 0Dh
0x180107ca0  jl      loc_180107F5B
0x180107ca6  imul    ecx, [r14], 9E3779B1h
0x180107cad  mov     r12, r14
0x180107cb0  sub     r12, rdx
0x180107cb3  mov     [rsp+98h+arg_20], r8d
0x180107cbb  mov     r10, r14
0x180107cbe  mov     [rsp+98h+var_70], r12
0x180107cc3  mov     [rsp+98h+var_68], r14
0x180107cc8  shr     rcx, 13h
0x180107ccc  inc     r10
0x180107ccf  mov     [r15+rcx*2], dx
0x180107cd4  imul    ecx, [r10], 9E3779B1h
0x180107cdb  mov     r11, r10
0x180107cde  mov     eax, r9d
0x180107ce1  mov     edi, 40h ; '@'
0x180107ce6  cdqe
0x180107ce8  mov     r15d, r11d
0x180107ceb  mov     r13, r11
0x180107cee  shr     ecx, 13h
0x180107cf1  mov     r10, r11
0x180107cf4  sub     r15d, r12d
0x180107cf7  add     r11, rax
0x180107cfa  lea     rax, [rbp-0Bh]
0x180107cfe  cmp     r11, rax
0x180107d01  ja      loc_180107F53
0x180107d07  mov     rax, [rsp+98h+var_78]
0x180107d0c  movzx   edx, word ptr [rax+rcx*2]
0x180107d10  add     rdx, r12
0x180107d13  mov     r12d, [r11]
0x180107d16  mov     [rax+rcx*2], r15w
0x180107d1b  mov     eax, [r10]
0x180107d1e  cmp     [rdx], eax
0x180107d20  jz      short loc_180107D38
0x180107d22  mov     eax, edi
0x180107d24  add     edi, r9d
0x180107d27  sar     eax, 6
0x180107d2a  imul    ecx, r12d, 9E3779B1h
0x180107d31  mov     r12, [rsp+98h+var_70]
0x180107d36  jmp     short loc_180107CE6
0x180107d38  mov     r11, [rsp+98h+var_68]
0x180107d3d  mov     r12d, [rsp+98h+arg_20]
0x180107d45  cmp     rdx, r11
0x180107d48  jbe     short loc_180107D78
0x180107d4a  mov     al, [rdx-1]
0x180107d4d  cmp     [r13-1], al
0x180107d51  jnz     short loc_180107D78
0x180107d53  sub     r10, r9
0x180107d56  sub     rdx, r9
0x180107d59  cmp     r10, r14
0x180107d5c  mov     ecx, r8d
0x180107d5f  mov     eax, r8d
0x180107d62  setnbe  cl
0x180107d65  cmp     rdx, r11
0x180107d68  setnbe  al
0x180107d6b  test    eax, ecx
0x180107d6d  jz      short loc_180107D78
0x180107d6f  mov     al, [rdx-1]
0x180107d72  cmp     [r10-1], al
0x180107d76  jz      short loc_180107D53
0x180107d78  mov     eax, r10d
0x180107d7b  mov     rdi, rbx
0x180107d7e  sub     eax, r14d
0x180107d81  add     rbx, r9
0x180107d84  mov     r11d, eax
0x180107d87  cmp     eax, 0Fh
0x180107d8a  jb      short loc_180107DA7
0x180107d8c  add     eax, 0FFFFFFF1h
0x180107d8f  mov     byte ptr [rdi], 0F0h
0x180107d92  jmp     short loc_180107D9C
0x180107d94  mov     [rbx], sil
0x180107d97  add     rbx, r9
0x180107d9a  sub     eax, esi
0x180107d9c  cmp     eax, esi
0x180107d9e  jge     short loc_180107D94
0x180107da0  mov     [rbx], al
0x180107da2  add     rbx, r9
0x180107da5  jmp     short loc_180107DAF
0x180107da7  mov     al, r11b
0x180107daa  shl     al, 4
0x180107dad  mov     [rdi], al
0x180107daf  add     r11, rbx
0x180107db2  mov     rcx, rbx
0x180107db5  mov     rbx, r11
0x180107db8  mov     rax, [r14]
0x180107dbb  lea     r14, [r14+8]
0x180107dbf  mov     [rcx], rax
0x180107dc2  add     rcx, 8
0x180107dc6  cmp     rcx, r11
0x180107dc9  jb      short loc_180107DB8
0x180107dcb  lea     r14, [rbp-5]
0x180107dcf  lea     r15, [r14-7]
0x180107dd3  mov     r13, [rsp+98h+var_70]
0x180107dd8  lea     r11, [r10+4]
0x180107ddc  mov     [rsp+98h+arg_20], r12d
0x180107de4  movzx   eax, r10w
0x180107de8  mov     rcx, r11
0x180107deb  sub     ax, dx
0x180107dee  add     rdx, 4
0x180107df2  mov     [rbx], ax
0x180107df5  add     rbx, 2
0x180107df9  cmp     r11, r15
0x180107dfc  jnb     short loc_180107E0E
0x180107dfe  mov     rax, [r11]
0x180107e01  xor     rax, [rdx]
0x180107e04  jnz     short loc_180107E2D
0x180107e06  lea     rcx, [r11+8]
0x180107e0a  add     rdx, 8
0x180107e0e  mov     [rsp+98h+arg_20], r12d
0x180107e16  cmp     rcx, r15
0x180107e19  jnb     short loc_180107E46
0x180107e1b  mov     rax, [rcx]
0x180107e1e  xor     rax, [rdx]
0x180107e21  jnz     short loc_180107E37
0x180107e23  add     rcx, 8
0x180107e27  add     rdx, 8
0x180107e2b  jmp     short loc_180107E16
0x180107e2d  tzcnt   rcx, rax
0x180107e32  shr     ecx, 3
0x180107e35  jmp     short loc_180107E8A
0x180107e37  tzcnt   rax, rax
0x180107e3c  shr     eax, 3
0x180107e3f  sub     eax, r11d
0x180107e42  add     ecx, eax
0x180107e44  jmp     short loc_180107E8A
0x180107e46  lea     rax, [r14-3]
0x180107e4a  cmp     rcx, rax
0x180107e4d  jnb     short loc_180107E5D
0x180107e4f  mov     eax, [rcx]
0x180107e51  cmp     [rdx], eax
0x180107e53  jnz     short loc_180107E5D
0x180107e55  add     rcx, 4
0x180107e59  add     rdx, 4
0x180107e5d  lea     rax, [r14-1]
0x180107e61  cmp     rcx, rax
0x180107e64  jnb     short loc_180107E79
0x180107e66  movzx   eax, word ptr [rcx]
0x180107e69  cmp     [rdx], ax
0x180107e6c  jnz     short loc_180107E79
0x180107e6e  mov     eax, 2
0x180107e73  add     rcx, rax
0x180107e76  add     rdx, rax
0x180107e79  cmp     rcx, r14
0x180107e7c  jnb     short loc_180107E87
0x180107e7e  mov     al, [rcx]
0x180107e80  cmp     [rdx], al
0x180107e82  jnz     short loc_180107E87
0x180107e84  add     rcx, r9
0x180107e87  sub     ecx, r11d
0x180107e8a  mov     eax, ecx
0x180107e8c  add     r10, 4
0x180107e90  add     r10, rax
0x180107e93  mov     al, [rdi]
0x180107e95  cmp     ecx, 0Fh
0x180107e98  jb      short loc_180107EDB
0x180107e9a  add     al, 0Fh
0x180107e9c  lea     r11d, [rcx-0Fh]
0x180107ea0  mov     [rdi], al
0x180107ea2  mov     eax, 3FCh
0x180107ea7  jmp     short loc_180107EB4
0x180107ea9  add     rbx, 4
0x180107ead  add     r11d, 0FFFFFC04h
0x180107eb4  mov     dword ptr [rbx], 0FFFFFFFFh
0x180107eba  cmp     r11d, eax
0x180107ebd  jnb     short loc_180107EA9
0x180107ebf  mov     eax, 80808081h
0x180107ec4  mul     r11d
0x180107ec7  shr     edx, 7
0x180107eca  mov     ecx, edx
0x180107ecc  add     cl, r11b
0x180107ecf  lea     rax, [rdx+rbx]
0x180107ed3  mov     [rax], cl
0x180107ed5  lea     rbx, [rax+1]
0x180107ed9  jmp     short loc_180107EDF
0x180107edb  add     cl, al
0x180107edd  mov     [rdi], cl
0x180107edf  lea     rax, [rbp-0Bh]
0x180107ee3  mov     r14, r10
0x180107ee6  cmp     r10, rax
0x180107ee9  jnb     short loc_180107F53
0x180107eeb  imul    ecx, [r10-2], 9E3779B1h
0x180107ef3  movzx   edx, r10w
0x180107ef7  mov     r11, [rsp+98h+var_78]
0x180107efc  sub     dx, r13w
0x180107f00  sub     dx, 2
0x180107f04  movzx   eax, r10w
0x180107f08  sub     ax, r13w
0x180107f0c  shr     rcx, 13h
0x180107f10  mov     [r11+rcx*2], dx
0x180107f15  imul    ecx, [r10], 9E3779B1h
0x180107f1c  shr     rcx, 13h
0x180107f20  movzx   edx, word ptr [r11+rcx*2]
0x180107f25  mov     [r11+rcx*2], ax
0x180107f2a  add     rdx, r13
0x180107f2d  mov     eax, [r10]
0x180107f30  cmp     [rdx], eax
0x180107f32  jnz     short loc_180107F46
0x180107f34  mov     rdi, rbx
0x180107f37  lea     r14, [rbp-5]
0x180107f3b  add     rbx, r9
0x180107f3e  mov     [rdi], r8b
0x180107f41  jmp     loc_180107DD8
0x180107f46  mov     r12, [rsp+98h+var_70]
0x180107f4b  add     r10, r9
0x180107f4e  jmp     loc_180107CD4
0x180107f53  mov     r13, [rsp+98h+arg_10]
0x180107f5b  sub     rbp, r14
0x180107f5e  cmp     rbp, 0Fh
0x180107f62  jb      short loc_180107F80
0x180107f64  mov     byte ptr [rbx], 0F0h
0x180107f67  lea     rax, [rbp-0Fh]
0x180107f6b  add     rbx, r9
0x180107f6e  jmp     short loc_180107F79
0x180107f70  mov     [rbx], sil
0x180107f73  add     rbx, r9
0x180107f76  sub     rax, rsi
0x180107f79  cmp     rax, rsi
0x180107f7c  jnb     short loc_180107F70
0x180107f7e  jmp     short loc_180107F86
0x180107f80  mov     al, bpl
0x180107f83  shl     al, 4
0x180107f86  mov     [rbx], al
0x180107f88  mov     r8, rbp; Size
0x180107f8b  inc     rbx
0x180107f8e  mov     rdx, r14; Src
0x180107f91  mov     rcx, rbx; void *
0x180107f94  call    memmove
0x180107f99  lea     r8, [rbx+rbp]
0x180107f9d  sub     r8d, r13d
0x180107fa0  jmp     loc_180108AD0
0x180107fa5  cmp     edi, 7E000000h
0x180107fab  ja      loc_180108AD0
0x180107fb1  mov     ecx, [r15+4010h]
0x180107fb8  lea     r10, [r14+1]
0x180107fbc  add     [r15+4018h], edi
0x180107fc3  mov     r9, 0CF1BBCDCBB000000h
0x180107fcd  mov     dword ptr [r15+4014h], 2
0x180107fd8  mov     r11, r14
0x180107fdb  sub     r11, rcx
0x180107fde  mov     [rsp+98h+arg_20], r8d
0x180107fe6  lea     eax, [rcx+rdi]
0x180107fe9  mov     [rsp+98h+var_70], r11
0x180107fee  mov     [r15+4010h], eax
0x180107ff5  mov     rbx, r13
0x180107ff8  mov     rax, [r14]
0x180107ffb  lea     r13, [r14+rdi]
0x180107fff  imul    rax, r9
0x180108003  mov     esi, 0FFh
0x180108008  shr     rax, 34h
0x18010800c  mov     [r15+rax*4], ecx
0x180108010  mov     r15, r14
0x180108013  mov     rdx, [r10]
0x180108016  imul    rdx, r9
0x18010801a  mov     r9d, 1
0x180108020  mov     rdi, r10
0x180108023  mov     eax, r9d
0x180108026  mov     r12d, 40h ; '@'
0x18010802c  cdqe
0x18010802e  mov     ebp, edi
0x180108030  mov     r10, rdi
  ... truncated ...
```
