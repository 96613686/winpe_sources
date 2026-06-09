# CompressRdp8<4>::CompressInternal(uchar const *,uint,uint,_CompressHint const *,uint,uchar *,uint,uint *)

- ea: `0x180024304`
- end: `0x180026c7b`
- name: `?CompressInternal@?$CompressRdp8@$03@@AEAAJPEBEIIPEBU_CompressHint@@IPEAEIPEAI@Z`
- size: `10615`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180024100`

## callees

- `0x180024304`
- `0x180027130`
- `0x180027150`
- `0x180028340`

## pseudocode

```c
__int64 __fastcall CompressRdp8<4>::CompressInternal(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        unsigned int *a5,
        int a6,
        char *a7,
        unsigned int a8,
        _DWORD *a9)
{
  _BYTE *v9; // rdi
  unsigned int v10; // r9d
  unsigned int v11; // r11d
  char *v12; // r12
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  __int64 v15; // r14
  __int64 v16; // r10
  char *v17; // r15
  unsigned int v18; // eax
  unsigned int *v19; // r13
  unsigned int v20; // ebx
  int v21; // ecx
  unsigned int v22; // edi
  unsigned int v23; // eax
  unsigned int v24; // r11d
  __int64 v25; // rax
  unsigned __int64 v26; // rdx
  unsigned int v27; // r9d
  _QWORD *v28; // r10
  __int64 v29; // r8
  _QWORD *v30; // r10
  _QWORD *v31; // r10
  _QWORD *v32; // r10
  _QWORD *v33; // r10
  _QWORD *v34; // r10
  _QWORD *v35; // r10
  _QWORD *v36; // r10
  _QWORD *v37; // r10
  _QWORD *v38; // r10
  _QWORD *v39; // r10
  _QWORD *v40; // r10
  unsigned int v41; // eax
  _QWORD *v42; // r10
  _QWORD *v43; // r10
  bool v44; // zf
  _QWORD *v45; // rax
  unsigned __int64 v46; // rdx
  _QWORD *v47; // r10
  __int64 v48; // r8
  _QWORD *v49; // r10
  _QWORD *v50; // r10
  _QWORD *v51; // r10
  _QWORD *v52; // r10
  _QWORD *v53; // r10
  _QWORD *v54; // r10
  _QWORD *v55; // r10
  _QWORD *v56; // r10
  _QWORD *v57; // r10
  _QWORD *v58; // r10
  _QWORD *v59; // r10
  _QWORD *v60; // r10
  _QWORD *v61; // r10
  int v62; // r13d
  unsigned int v63; // eax
  bool v64; // cf
  unsigned __int8 *v65; // rbx
  unsigned __int64 v66; // rsi
  __int64 v67; // r12
  unsigned int v68; // r13d
  int v69; // r14d
  __int64 v70; // rsi
  __int64 v71; // r15
  unsigned int v72; // edi
  __int64 v73; // r10
  _BYTE *v74; // rcx
  _BYTE *v75; // r13
  char v76; // al
  __int64 v77; // rcx
  __int64 v78; // r10
  _WORD *v79; // rdx
  _BYTE *v80; // rdx
  char *v81; // rcx
  unsigned int v82; // ecx
  char *v83; // r10
  __int64 v84; // rcx
  __int64 v85; // r10
  _WORD *v86; // rdx
  _BYTE *v87; // rdx
  char *v88; // rcx
  unsigned int v89; // ecx
  char *v90; // r10
  __int64 v91; // rcx
  __int64 v92; // r10
  _WORD *v93; // rdx
  _BYTE *v94; // rdx
  char *v95; // rcx
  unsigned int v96; // ecx
  char *v97; // r10
  __int64 v98; // rcx
  unsigned __int64 v99; // rdx
  unsigned int v100; // r9d
  _QWORD *v101; // r10
  char *v102; // r11
  __int64 v103; // r8
  _QWORD *v104; // r10
  char *v105; // r11
  _QWORD *v106; // r10
  char *v107; // r11
  _QWORD *v108; // r10
  char *v109; // r11
  _QWORD *v110; // r10
  char *v111; // r11
  _QWORD *v112; // r10
  char *v113; // r11
  _QWORD *v114; // r10
  char *v115; // r11
  _QWORD *v116; // r10
  char *v117; // r11
  _QWORD *v118; // r10
  char *v119; // r11
  _QWORD *v120; // r10
  char *v121; // r11
  _QWORD *v122; // r10
  char *v123; // r11
  _QWORD *v124; // r10
  char *v125; // r11
  _QWORD *v126; // r10
  char *v127; // r11
  _QWORD *v128; // r10
  char *v129; // r11
  _QWORD *v130; // rax
  char *v131; // r11
  unsigned __int64 v132; // rdx
  _QWORD *v133; // r10
  char *v134; // r11
  __int64 v135; // r8
  _QWORD *v136; // r10
  char *v137; // r11
  _QWORD *v138; // r10
  char *v139; // r11
  _QWORD *v140; // r10
  char *v141; // r11
  _QWORD *v142; // r10
  char *v143; // r11
  _QWORD *v144; // r10
  char *v145; // r11
  _QWORD *v146; // r10
  char *v147; // r11
  _QWORD *v148; // r10
  char *v149; // r11
  _QWORD *v150; // r10
  char *v151; // r11
  _QWORD *v152; // r10
  char *v153; // r11
  _QWORD *v154; // r10
  char *v155; // r11
  _QWORD *v156; // r10
  char *v157; // r11
  _QWORD *v158; // r10
  char *v159; // r11
  _QWORD *v160; // r10
  char *v161; // r11
  unsigned int v162; // r10d
  unsigned __int64 v163; // rdx
  _QWORD *v164; // r11
  char *v165; // rbx
  char *v166; // r14
  __int64 v167; // rbx
  __int16 v168; // r11
  char *v169; // rdi
  int v170; // edx
  unsigned __int64 v171; // rcx
  unsigned int v172; // r10d
  __int64 v173; // rdx
  _WORD *v174; // rcx
  _BYTE *v175; // rcx
  unsigned int v176; // edi
  char v177; // al
  unsigned __int64 v178; // rdx
  unsigned int v179; // r9d
  _QWORD *v180; // r10
  unsigned __int64 v181; // r8
  _QWORD *v182; // r10
  _QWORD *v183; // r10
  _QWORD *v184; // r10
  _QWORD *v185; // r10
  _QWORD *v186; // r10
  _QWORD *v187; // r10
  _QWORD *v188; // r10
  _QWORD *v189; // r10
  _QWORD *v190; // r10
  _QWORD *v191; // r10
  _QWORD *v192; // r10
  _QWORD *v193; // r10
  _QWORD *v194; // r10
  _QWORD *v195; // rax
  char *v196; // r15
  unsigned __int64 v197; // rdx
  _QWORD *v198; // r10
  char *v199; // r15
  __int64 v200; // r8
  _QWORD *v201; // r10
  char *v202; // r15
  _QWORD *v203; // r10
  char *v204; // r15
  _QWORD *v205; // r10
  char *v206; // r15
  unsigned __int64 v207; // r10
  int v208; // r9d
  __int64 v209; // r10
  unsigned int v210; // r11d
  int v211; // r9d
  int v212; // r9d
  int v213; // r9d
  int v214; // r9d
  int v215; // r9d
  int v216; // r9d
  int v217; // r9d
  int v218; // r9d
  int v219; // r9d
  __int64 v220; // r10
  unsigned int v221; // r11d
  unsigned __int64 v222; // r10
  int v223; // r9d
  __int64 v224; // r10
  int v225; // r11d
  unsigned int v226; // r13d
  unsigned int v227; // esi
  unsigned __int8 *v228; // r14
  __int64 v229; // rdi
  unsigned __int64 v230; // r10
  int v231; // r9d
  unsigned __int64 v232; // r8
  int v233; // r9d
  __int64 v234; // r10
  __int64 v235; // rax
  unsigned int v236; // r11d
  unsigned __int64 v237; // r10
  int v238; // r9d
  __int64 v239; // r10
  int v240; // r11d
  unsigned __int64 v241; // rbx
  char v242; // bl
  __int64 v243; // rcx
  char *v245; // [rsp+28h] [rbp-61h]
  void *v246; // [rsp+30h] [rbp-59h] BYREF
  void *v247; // [rsp+38h] [rbp-51h]
  char *v248; // [rsp+40h] [rbp-49h]
  int v249; // [rsp+48h] [rbp-41h]
  unsigned __int64 v250; // [rsp+50h] [rbp-39h]
  unsigned __int64 v251; // [rsp+58h] [rbp-31h]
  void *Src; // [rsp+60h] [rbp-29h]
  __int64 v253; // [rsp+70h] [rbp-19h]
  unsigned __int64 v254; // [rsp+78h] [rbp-11h]

  v9 = a7;
  v10 = 64;
  v11 = a3;
  v12 = &a7[a8];
  v246 = a7;
  v13 = 0;
  v245 = a7;
  v247 = a7;
  v14 = 0;
  v251 = (unsigned __int64)v12;
  v15 = a2;
  v248 = v12;
  v16 = a1;
  v249 = 64;
  v17 = a7;
  v250 = 0;
  if ( v11 )
  {
    v18 = v11 - 3;
LABEL_3:
    v19 = a5;
    v20 = v11;
    v21 = a6;
    v22 = v18;
    while ( 1 )
    {
      if ( !v21 )
        goto LABEL_217;
      v23 = *v19;
      if ( v14 < *v19 )
      {
        v20 = *v19;
        v22 = v23 - 2;
        goto LABEL_217;
      }
      if ( v14 == v23 )
        break;
      v19 += 3;
      --v21;
      a5 = v19;
      a6 = v21;
    }
    v24 = v19[1];
    v22 = 0;
    v25 = v19[2];
    v20 = v24 + v14;
    if ( !(_DWORD)v25 )
      goto LABEL_217;
    if ( (unsigned int)v25 < 0x20 )
    {
      v26 = (unsigned int)(v25 + 544);
      if ( v10 > 0xA )
      {
        v27 = v10 - 10;
        goto LABEL_102;
      }
      v28 = v17;
      v17 += 8;
      v245 = v17;
      if ( v17 <= v12 )
        *v28 = _byteswap_uint64(v13 + (v26 >> (10 - (unsigned __int8)v10)));
      v247 = v17;
      v29 = (unsigned int)(v25 + 544);
      if ( v10 != 10 )
      {
        v27 = v10 + 54;
        goto LABEL_108;
      }
LABEL_106:
      v27 = 64;
      v13 = 0;
LABEL_109:
      v250 = v13;
      if ( v24 < 4 )
      {
        v44 = v27 == 1;
        v10 = v27 - 1;
        v249 = v10;
        if ( v44 )
        {
          v45 = v17;
          v17 += 8;
          v245 = v17;
          if ( v17 <= v12 )
            *v45 = _byteswap_uint64(v13);
          v247 = v17;
          goto LABEL_211;
        }
LABEL_215:
        v14 += v19[1];
        v16 = a1;
LABEL_217:
        Src = (void *)(v15 + v14);
        v62 = v15 + v20;
        v63 = 0;
        v253 = v15 + v20;
        v64 = v20 < 3;
        v65 = (unsigned __int8 *)Src;
        if ( !v64 )
          v63 = v22;
        v66 = v15 + v63;
        v44 = *(_BYTE *)(v16 + 157) == 0;
        v254 = v66;
        if ( !v44 )
        {
          if ( (unsigned __int64)Src >= v66 )
            goto LABEL_760;
          while ( 1 )
          {
            v67 = *v65;
            v68 = 0;
            v69 = (_DWORD)v65 - v15 + a4;
            v70 = (unsigned int)v67 ^ (8 * (v65[1] ^ (16 * ((unsigned int)v67 ^ v65[2]))));
            v71 = *(unsigned int *)(v16 + 16 * (v70 + 10));
            v72 = v69 - v71;
            if ( (unsigned int)(v69 - v71) > *(_DWORD *)(v16 + 152) )
              goto LABEL_311;
            v73 = *(_QWORD *)(v16 + 136);
            if ( *(_WORD *)(v73 + v71) == *(_WORD *)v65 )
            {
              v74 = (_BYTE *)(v73 + (unsigned int)v71 + 2LL);
              v75 = v65 + 2;
              if ( (unsigned int)(v253 - (_DWORD)Src) > 6 )
              {
                if ( v65[2] != *v74 )
                {
                  v68 = 0;
LABEL_226:
                  v65 = (unsigned __int8 *)Src;
                  goto LABEL_240;
                }
                if ( v65[3] != v74[1] )
                {
                  v68 = 3;
                  goto LABEL_226;
                }
                if ( v65[4] != v74[2] )
                {
                  v68 = 4;
                  goto LABEL_226;
                }
                if ( v65[5] != v74[3] )
                {
                  v68 = 5;
                  goto LABEL_226;
                }
                v76 = v74[4];
                v75 = v65 + 7;
                v74 += 5;
                if ( v65[6] != v76 )
                {
                  v68 = 6;
                  goto LABEL_226;
                }
              }
              v65 = (unsigned __int8 *)Src;
              while ( v75 < (char *)Src + (unsigned int)(v253 - (_DWORD)Src) && *v75 == *v74 )
              {
                ++v74;
                ++v75;
              }
              v68 = (_DWORD)v75 - (_DWORD)Src;
            }
LABEL_240:
            v16 = a1;
            v77 = *(unsigned int *)(a1 + 16 * v70 + 164);
            if ( (unsigned int)(v69 - v77) > *(_DWORD *)(a1 + 152) )
              goto LABEL_311;
            v78 = (unsigned int)(v253 - (_DWORD)v65);
            if ( v68 + 1 >= (unsigned int)v78
              || (v79 = (_WORD *)(v77 + *(_QWORD *)(a1 + 136)), *(_WORD *)((char *)v79 + v68) != *(_WORD *)&v65[v68])
              || *v79 != *(_WORD *)v65 )
            {
LABEL_260:
              v82 = 0;
              goto LABEL_261;
            }
            v80 = v79 + 1;
            v81 = (char *)(v65 + 2);
            if ( (unsigned int)v78 > 6 )
            {
              if ( *v81 != *v80 )
                goto LABEL_260;
              if ( v65[3] != v80[1] )
              {
                v82 = 3;
                goto LABEL_261;
              }
              if ( v65[4] != v80[2] )
              {
                v82 = 4;
                goto LABEL_261;
              }
              if ( v65[5] != v80[3] )
              {
                v82 = 5;
                goto LABEL_261;
              }
              v81 = (char *)(v65 + 7);
              if ( v65[6] != v80[4] )
              {
                v82 = 6;
                goto LABEL_261;
              }
              v80 += 5;
            }
            v83 = (char *)&v65[v78];
            while ( v81 < v83 && *v81 == *v80 )
            {
              ++v80;
              ++v81;
            }
            v82 = (_DWORD)v81 - (_DWORD)v65;
LABEL_261:
            v16 = a1;
            if ( v68 < v82 )
            {
              v68 = v82;
              v72 = v69 - *(_DWORD *)(16 * v70 + a1 + 164);
            }
            v84 = *(unsigned int *)(a1 + 16 * v70 + 168);
            if ( (unsigned int)(v69 - v84) > *(_DWORD *)(a1 + 152) || v68 >= 0xF )
              goto LABEL_311;
            v85 = (unsigned int)(v253 - (_DWORD)v65);
            if ( v68 + 1 >= (unsigned int)v85
              || (v86 = (_WORD *)(v84 + *(_QWORD *)(a1 + 136)), *(_WORD *)((char *)v86 + v68) != *(_WORD *)&v65[v68])
              || *v86 != *(_WORD *)v65 )
            {
LABEL_284:
              v89 = 0;
              goto LABEL_285;
            }
            v87 = v86 + 1;
            v88 = (char *)(v65 + 2);
            if ( (unsigned int)v85 > 6 )
            {
              if ( *v88 != *v87 )
                goto LABEL_284;
              if ( v65[3] != v87[1] )
              {
                v89 = 3;
                goto LABEL_285;
              }
              if ( v65[4] != v87[2] )
              {
                v89 = 4;
                goto LABEL_285;
              }
              if ( v65[5] != v87[3] )
              {
                v89 = 5;
                goto LABEL_285;
              }
              v88 = (char *)(v65 + 7);
              if ( v65[6] != v87[4] )
              {
                v89 = 6;
                goto LABEL_285;
              }
              v87 += 5;
            }
            v90 = (char *)&v65[v85];
            while ( v88 < v90 && *v88 == *v87 )
            {
              ++v87;
              ++v88;
            }
            v89 = (_DWORD)v88 - (_DWORD)v65;
LABEL_285:
            v16 = a1;
            if ( v68 < v89 )
            {
              v68 = v89;
              v72 = v69 - *(_DWORD *)(16 * v70 + a1 + 168);
            }
            v91 = *(unsigned int *)(a1 + 16 * v70 + 172);
            if ( (unsigned int)(v69 - v91) <= *(_DWORD *)(a1 + 152) && v68 < 0xA )
            {
              v92 = (unsigned int)(v253 - (_DWORD)v65);
              if ( v68 + 1 >= (unsigned int)v92 )
                goto LABEL_308;
              v93 = (_WORD *)(v91 + *(_QWORD *)(a1 + 136));
              if ( *(_WORD *)((char *)v93 + v68) != *(_WORD *)&v65[v68] || *v93 != *(_WORD *)v65 )
                goto LABEL_308;
              v94 = v93 + 1;
              v95 = (char *)(v65 + 2);
              if ( (unsigned int)v92 <= 6 )
                goto LABEL_303;
              if ( *v95 == *v94 )
              {
                if ( v65[3] != v94[1] )
                {
                  v96 = 3;
                  goto LABEL_309;
                }
                if ( v65[4] != v94[2] )
                {
                  v96 = 4;
                  goto LABEL_309;
                }
                if ( v65[5] != v94[3] )
                {
                  v96 = 5;
                  goto LABEL_309;
                }
                v95 = (char *)(v65 + 7);
                if ( v65[6] != v94[4] )
                {
                  v96 = 6;
                  goto LABEL_309;
                }
                v94 += 5;
LABEL_303:
                v97 = (char *)&v65[v92];
                while ( v95 < v97 && *v95 == *v94 )
                {
                  ++v94;
                  ++v95;
                }
                v96 = (_DWORD)v95 - (_DWORD)v65;
              }
              else
              {
LABEL_308:
                v96 = 0;
              }
LABEL_309:
              v16 = a1;
              if ( v68 < v96 )
              {
                v68 = v96;
                v72 = v69 - *(_DWORD *)(16 * v70 + a1 + 172);
              }
            }
LABEL_311:
            v98 = 2 * v70;
            *(_DWORD *)(v16 + 8 * v98 + 172) = *(_DWORD *)(v16 + 16 * v70 + 168);
            *(_DWORD *)(v16 + 8 * v98 + 168) = *(_DWORD *)(v16 + 16 * v70 + 164);
            *(_DWORD *)(v16 + 8 * v98 + 164) = v71;
            *(_DWORD *)(v16 + 16 * (v70 + 10)) = v69;
            if ( !v68 )
              goto LABEL_523;
            if ( v72 >= 0x1000 )
            {
              if ( v68 >= 4 && v72 < 0x10000 )
              {
LABEL_344:
                if ( v72 >= 0x16A0 )
                {
                  if ( v72 >= 0x56A0 )
                  {
                    if ( v72 >= 0xD6A0 )
                    {
                      if ( v72 >= 0x4D6A0 )
                      {
                        if ( v72 >= 0x14D6A0 )
                        {
                          if ( v72 >= 0x24D6A0 )
                          {
                            if ( v72 >= 0x44D6A0 )
                            {
                              if ( v72 >= 0x84D6A0 )
                              {
                                if ( v72 >= 0x104D6A0 )
                                {
                                  v99 = v72 + 0x17CFB2960LL;
                                  if ( v10 > 0x21 )
                                  {
                                    v100 = v10 - 33;
                                    goto LABEL_409;
                                  }
                                  v128 = v245;
                                  v129 = v245 + 8;
                                  v245 = v129;
                                  if ( (unsigned __int64)v129 <= v251 )
                                    *v128 = _byteswap_uint64(v13 + (v99 >> (33 - (unsigned __int8)v10)));
                                  v247 = v129;
                                  if ( v10 == 33 )
                                    goto LABEL_413;
                                  v100 = v10 + 31;
                                  v103 = v72 + 0x17CFB2960LL;
                                }
                                else
                                {
                                  v99 = v72 - 1107613344;
                                  if ( v10 > 0x20 )
                                  {
                                    v100 = v10 - 32;
                                    goto LABEL_409;
                                  }
                                  v126 = v245;
                                  v127 = v245 + 8;
                                  v245 = v127;
                                  if ( (unsigned __int64)v127 <= v251 )
                                    *v126 = _byteswap_uint64(v13 + (v99 >> (32 - (unsigned __int8)v10)));
                                  v247 = v127;
                                  v103 = v72 - 1107613344;
                                  if ( v10 == 32 )
                                    goto LABEL_413;
                                  v100 = v10 + 32;
                                }
                              }
                              else
                              {
                                v99 = v72 + 1589324128;
                                if ( v10 > 0x1F )
                                {
                                  v100 = v10 - 31;
                                  goto LABEL_409;
                                }
                                v124 = v245;
                                v125 = v245 + 8;
                                v245 = v125;
                                if ( (unsigned __int64)v125 <= v251 )
                                  *v124 = _byteswap_uint64(v13 + (v99 >> (31 - (unsigned __int8)v10)));
                                v247 = v125;
                                v103 = v72 + 1589324128;
                                if ( v10 == 31 )
                                  goto LABEL_413;
                                v100 = v10 + 33;
                              }
                            }
                            else
                            {
                              v99 = v72 + 393947488;
                              if ( v10 > 0x1D )
                              {
                                v100 = v10 - 29;
                                goto LABEL_409;
                              }
                              v122 = v245;
                              v123 = v245 + 8;
                              v245 = v123;
                              if ( (unsigned __int64)v123 <= v251 )
                                *v122 = _byteswap_uint64(v13 + (v99 >> (29 - (unsigned __int8)v10)));
                              v247 = v123;
                              v103 = v72 + 393947488;
                              if ( v10 == 29 )
                                goto LABEL_413;
                              v100 = v10 + 35;
                            }
                          }
                          else
                          {
                            v99 = v72 + 195766624;
                            if ( v10 > 0x1C )
                            {
                              v100 = v10 - 28;
                              goto LABEL_409;
                            }
                            v120 = v245;
                            v121 = v245 + 8;
                            v245 = v121;
                            if ( (unsigned __int64)v121 <= v251 )
                              *v120 = _byteswap_uint64(v13 + (v99 >> (28 - (unsigned __int8)v10)));
                            v247 = v121;
                            v103 = v72 + 195766624;
                            if ( v10 == 28 )
                              goto LABEL_413;
                            v100 = v10 + 36;
                          }
                        }
                        else
                        {
                          v99 = v72 + 97200480;
                          if ( v10 > 0x1B )
                          {
                            v100 = v10 - 27;
                            goto LABEL_409;
                          }
                          v118 = v245;
                          v119 = v245 + 8;
                          v245 = v119;
                          if ( (unsigned __int64)v119 <= v251 )
                            *v118 = _byteswap_uint64(v13 + (v99 >> (27 - (unsigned __int8)v10)));
                          v247 = v119;
                          v103 = v72 + 97200480;
                          if ( v10 == 27 )
                            goto LABEL_413;
                          v100 = v10 + 37;
                        }
                      }
                      else
                      {
                        v99 = v72 + 24062304;
                        if ( v10 > 0x19 )
                        {
                          v100 = v10 - 25;
                          goto LABEL_409;
                        }
                        v116 = v245;
                        v117 = v245 + 8;
                        v245 = v117;
                        if ( (unsigned __int64)v117 <= v251 )
                          *v116 = _byteswap_uint64(v13 + (v99 >> (25 - (unsigned __int8)v10)));
                        v247 = v117;
                        v103 = v72 + 24062304;
                        if ( v10 == 25 )
                          goto LABEL_413;
                        v100 = v10 + 39;
                      }
                    }
                    else
                    {
                      v99 = v72 + 1452384;
                      if ( v10 > 0x15 )
                      {
                        v100 = v10 - 21;
                        goto LABEL_409;
                      }
                      v114 = v245;
                      v115 = v245 + 8;
                      v245 = v115;
                      if ( (unsigned __int64)v115 <= v251 )
                        *v114 = _byteswap_uint64(v13 + (v99 >> (21 - (unsigned __int8)v10)));
                      v247 = v115;
                      v103 = v72 + 1452384;
                      if ( v10 == 21 )
                        goto LABEL_413;
                      v100 = v10 + 43;
                    }
                  }
                  else
                  {
                    v99 = v72 + 715104;
                    if ( v10 > 0x14 )
                    {
                      v100 = v10 - 20;
                      goto LABEL_409;
                    }
                    v112 = v245;
                    v113 = v245 + 8;
                    v245 = v113;
                    if ( (unsigned __int64)v113 <= v251 )
                      *v112 = _byteswap_uint64(v13 + (v99 >> (20 - (unsigned __int8)v10)));
                    v247 = v113;
                    v103 = v72 + 715104;
                    if ( v10 == 20 )
                      goto LABEL_413;
                    v100 = v10 + 44;
                  }
                }
                else
                {
                  v99 = v72 + 84320;
                  if ( v10 > 0x11 )
                  {
                    v100 = v10 - 17;
                    goto LABEL_409;
                  }
                  v110 = v245;
                  v111 = v245 + 8;
                  v245 = v111;
                  if ( (unsigned __int64)v111 <= v251 )
                    *v110 = _byteswap_uint64(v13 + (v99 >> (17 - (unsigned __int8)v10)));
                  v247 = v111;
                  v103 = v72 + 84320;
                  if ( v10 == 17 )
                    goto LABEL_413;
                  v100 = v10 + 47;
                }
                goto LABEL_415;
              }
              if ( v68 < 5 )
              {
LABEL_523:
                v162 = HIDWORD(qword_180033700[v67]);
                v163 = LODWORD(qword_180033700[v67]);
                if ( v10 <= v162 )
                {
                  v164 = v245;
                  v165 = v245 + 8;
                  v245 = v165;
                  if ( (unsigned __int64)v165 <= v251 )
                    *v164 = _byteswap_uint64(v13 + (v163 >> ((unsigned __int8)v162 - (unsigned __int8)v10)));
                  v247 = v165;
                  v65 = (unsigned __int8 *)Src;
                  if ( v10 == v162 )
                  {
                    v10 = 64;
                    v13 = 0;
                  }
                  else
                  {
                    v10 += 64 - v162;
                    v13 = v163 << v10;
                  }
                }
                else
                {
                  v10 -= v162;
                  v13 += v163 << v10;
                }
                v250 = v13;
                ++v65;
                v249 = v10;
                goto LABEL_531;
              }
            }
            if ( v72 >= 0x20 )
            {
              if ( v72 >= 0xA0 )
              {
                if ( v72 >= 0x2A0 )
                {
                  if ( v72 >= 0x6A0 )
                    goto LABEL_344;
                  v99 = v72 + 19808;
                  if ( v10 > 0xF )
                  {
                    v100 = v10 - 15;
                    goto LABEL_409;
                  }
                  v108 = v245;
                  v109 = v245 + 8;
                  v245 = v109;
                  if ( (unsigned __int64)v109 <= v251 )
                    *v108 = _byteswap_uint64(v13 + (v99 >> (15 - (unsigned __int8)v10)));
                  v247 = v109;
                  v103 = v72 + 19808;
                  if ( v10 == 15 )
                    goto LABEL_413;
                  v100 = v10 + 49;
                }
                else
                {
                  v99 = v72 + 9568;
                  if ( v10 > 0xE )
                  {
                    v100 = v10 - 14;
                    goto LABEL_409;
                  }
                  v106 = v245;
                  v107 = v245 + 8;
                  v245 = v107;
                  if ( (unsigned __int64)v107 <= v251 )
                    *v106 = _byteswap_uint64(v13 + (v99 >> (14 - (unsigned __int8)v10)));
                  v247 = v107;
                  v103 = v72 + 9568;
                  if ( v10 == 14 )
                    goto LABEL_413;
                  v100 = v10 + 50;
                }
              }
              else
              {
                v99 = v72 + 2272;
                if ( v10 > 0xC )
                {
                  v100 = v10 - 12;
                  goto LABEL_409;
                }
                v104 = v245;
                v105 = v245 + 8;
                v245 = v105;
                if ( (unsigned __int64)v105 <= v251 )
                  *v104 = _byteswap_uint64(v13 + (v99 >> (12 - (unsigned __int8)v10)));
                v247 = v105;
                v103 = v72 + 2272;
                if ( v10 == 12 )
                {
LABEL_413:
                  v100 = 64;
                  v13 = 0;
                  goto LABEL_416;
                }
                v100 = v10 + 52;
              }
            }
            else
            {
              v99 = v72 + 544;
              if ( v10 > 0xA )
              {
                v100 = v10 - 10;
LABEL_409:
                v13 += v99 << v100;
                goto LABEL_416;
              }
              v101 = v245;
              v102 = v245 + 8;
              v245 = v102;
              if ( (unsigned __int64)v102 <= v251 )
                *v101 = _byteswap_uint64(v13 + (v99 >> (10 - (unsigned __int8)v10)));
              v247 = v102;
              v103 = v72 + 544;
              if ( v10 == 10 )
                goto LABEL_413;
              v100 = v10 + 54;
            }
LABEL_415:
            v13 = v103 << v100;
LABEL_416:
            v250 = v13;
            if ( v68 >= 4 )
            {
              if ( v68 < 8 )
              {
                v132 = v68 + 4;
                if ( v100 > 4 )
                {
                  v10 = v100 - 4;
                  goto LABEL_514;
                }
                v133 = v245;
                v134 = v245 + 8;
                v245 = v134;
                if ( (unsigned __int64)v134 <= v251 )
                  *v133 = _byteswap_uint64(v13 + (v132 >> (4 - (unsigned __int8)v100)));
                v247 = v134;
                v135 = v68 + 4;
                if ( v100 != 4 )
                {
                  v10 = v100 + 60;
                  goto LABEL_520;
                }
LABEL_518:
                v10 = 64;
                v13 = 0;
LABEL_521:
                v250 = v13;
                v249 = v10;
                goto LABEL_522;
              }
              if ( v68 >= 0x10 )
              {
                if ( v68 >= 0x20 )
                {
                  if ( v68 >= 0x40 )
                  {
                    if ( v68 >= 0x80 )
                    {
                      if ( v68 >= 0x100 )
                      {
                        if ( v68 >= 0x200 )
                        {
                          if ( v68 >= 0x400 )
                          {
                            if ( v68 >= 0x800 )
                            {
                              if ( v68 >= 0x1000 )
                              {
                                if ( v68 >= 0x2000 )
                                {
                                  if ( v68 >= 0x4000 )
                                  {
                                    if ( v68 >= 0x8000 )
                                    {
                                      v132 = v68 + 1073643520;
                                      if ( v100 > 0x1E )
                                      {
                                        v10 = v100 - 30;
                                        goto LABEL_514;
                                      }
                                      v160 = v245;
                                      v161 = v245 + 8;
                                      v245 = v161;
                                      if ( (unsigned __int64)v161 <= v251 )
                                        *v160 = _byteswap_uint64(v13 + (v132 >> (30 - (unsigned __int8)v100)));
                                      v247 = v161;
                                      v135 = v68 + 1073643520;
                                      if ( v100 == 30 )
                                        goto LABEL_518;
                                      v10 = v100 + 34;
                                    }
                                    else
                                    {
                                      v132 = v68 + 268386304;
                                      if ( v100 > 0x1C )
                                      {
                                        v10 = v100 - 28;
                                        goto LABEL_514;
                                      }
                                      v158 = v245;
                                      v159 = v245 + 8;
                                      v245 = v159;
                                      if ( (unsigned __int64)v159 <= v251 )
                                        *v158 = _byteswap_uint64(v13 + (v132 >> (28 - (unsigned __int8)v100)));
                                      v247 = v159;
                                      v135 = v68 + 268386304;
                                      if ( v100 == 28 )
                                        goto LABEL_518;
                                      v10 = v100 + 36;
                                    }
                                  }
                                  else
                                  {
                                    v132 = v68 + 67084288;
                                    if ( v100 > 0x1A )
                                    {
                                      v10 = v100 - 26;
                                      goto LABEL_514;
                                    }
                                    v156 = v245;
                                    v157 = v245 + 8;
                                    v245 = v157;
                                    if ( (unsigned __int64)v157 <= v251 )
                                      *v156 = _byteswap_uint64(v13 + (v132 >> (26 - (unsigned __int8)v100)));
                                    v247 = v157;
                                    v135 = v68 + 67084288;
                                    if ( v100 == 26 )
                                      goto LABEL_518;
                                    v10 = v100 + 38;
                                  }
                                }
                                else
                                {
                                  v132 = v68 + 16764928;
                                  if ( v100 > 0x18 )
                                  {
                                    v10 = v100 - 24;
                                    goto LABEL_514;
                                  }
                                  v154 = v245;
                                  v155 = v245 + 8;
                                  v245 = v155;
                                  if ( (unsigned __int64)v155 <= v251 )
                                    *v154 = _byteswap_uint64(v13 + (v132 >> (24 - (unsigned __int8)v100)));
                                  v247 = v155;
                                  v135 = v68 + 16764928;
                                  if ( v100 == 24 )
                                    goto LABEL_518;
                                  v10 = v100 + 40;
                                }
                              }
                              else
                              {
                                v132 = v68 + 4188160;
                                if ( v100 > 0x16 )
                                {
                                  v10 = v100 - 22;
                                  goto LABEL_514;
                                }
                                v152 = v245;
                                v153 = v245 + 8;
                                v245 = v153;
                                if ( (unsigned __int64)v153 <= v251 )
                                  *v152 = _byteswap_uint64(v13 + (v132 >> (22 - (unsigned __int8)v100)));
                                v247 = v153;
                                v135 = v68 + 4188160;
                                if ( v100 == 22 )
                                  goto LABEL_518;
                                v10 = v100 + 42;
                              }
                            }
                            else
                            {
                              v132 = v68 + 1045504;
                              if ( v100 > 0x14 )
                              {
                                v10 = v100 - 20;
                                goto LABEL_514;
                              }
                              v150 = v245;
                              v151 = v245 + 8;
                              v245 = v151;
                              if ( (unsigned __int64)v151 <= v251 )
                                *v150 = _byteswap_uint64(v13 + (v132 >> (20 - (unsigned __int8)v100)));
                              v247 = v151;
                              v135 = v68 + 1045504;
                              if ( v100 == 20 )
                                goto LABEL_518;
                              v10 = v100 + 44;
                            }
                          }
                          else
                          {
                            v132 = v68 + 260608;
                            if ( v100 > 0x12 )
                            {
                              v10 = v100 - 18;
                              goto LABEL_514;
                            }
                            v148 = v245;
                            v149 = v245 + 8;
                            v245 = v149;
                            if ( (unsigned __int64)v149 <= v251 )
                              *v148 = _byteswap_uint64(v13 + (v132 >> (18 - (unsigned __int8)v100)));
                            v247 = v149;
                            v135 = v68 + 260608;
                            if ( v100 == 18 )
                              goto LABEL_518;
                            v10 = v100 + 46;
                          }
                        }
                        else
                        {
                          v132 = v68 + 64768;
                          if ( v100 > 0x10 )
                          {
                            v10 = v100 - 16;
                            goto LABEL_514;
                          }
                          v146 = v245;
                          v147 = v245 + 8;
                          v245 = v147;
                          if ( (unsigned __int64)v147 <= v251 )
                            *v146 = _byteswap_uint64(v13 + (v132 >> (16 - (unsigned __int8)v100)));
                          v247 = v147;
                          v135 = v68 + 64768;
                          if ( v100 == 16 )
                            goto LABEL_518;
                          v10 = v100 + 48;
                        }
                      }
                      else
                      {
                        v132 = v68 + 16000;
                        if ( v100 > 0xE )
                        {
                          v10 = v100 - 14;
                          goto LABEL_514;
                        }
                        v144 = v245;
                        v145 = v245 + 8;
                        v245 = v145;
                        if ( (unsigned __int64)v145 <= v251 )
                          *v144 = _byteswap_uint64(v13 + (v132 >> (14 - (unsigned __int8)v100)));
                        v247 = v145;
                        v135 = v68 + 16000;
                        if ( v100 == 14 )
                          goto LABEL_518;
                        v10 = v100 + 50;
                      }
                    }
                    else
                    {
                      v132 = v68 + 3904;
                      if ( v100 > 0xC )
                      {
                        v10 = v100 - 12;
                        goto LABEL_514;
                      }
                      v142 = v245;
                      v143 = v245 + 8;
                      v245 = v143;
                      if ( (unsigned __int64)v143 <= v251 )
                        *v142 = _byteswap_uint64(v13 + (v132 >> (12 - (unsigned __int8)v100)));
                      v247 = v143;
                      v135 = v68 + 3904;
                      if ( v100 == 12 )
                        goto LABEL_518;
                      v10 = v100 + 52;
                    }
                  }
                  else
                  {
                    v132 = v68 + 928;
                    if ( v100 > 0xA )
                    {
                      v10 = v100 - 10;
                      goto LABEL_514;
                    }
                    v140 = v245;
                    v141 = v245 + 8;
                    v245 = v141;
                    if ( (unsigned __int64)v141 <= v251 )
                      *v140 = _byteswap_uint64(v13 + (v132 >> (10 - (unsigned __int8)v100)));
                    v247 = v141;
                    v135 = v68 + 928;
                    if ( v100 == 10 )
                      goto LABEL_518;
                    v10 = v100 + 54;
                  }
                }
                else
                {
                  v132 = v68 + 208;
                  if ( v100 > 8 )
                  {
                    v10 = v100 - 8;
                    goto LABEL_514;
                  }
                  v138 = v245;
                  v139 = v245 + 8;
                  v245 = v139;
                  if ( (unsigned __int64)v139 <= v251 )
                    *v138 = _byteswap_uint64(v13 + (v132 >> (8 - (unsigned __int8)v100)));
                  v247 = v139;
                  v135 = v68 + 208;
                  if ( v100 == 8 )
                    goto LABEL_518;
                  v10 = v100 + 56;
                }
              }
              else
              {
                v132 = v68 + 40;
                if ( v100 > 6 )
                {
                  v10 = v100 - 6;
LABEL_514:
                  v13 += v132 << v10;
                  goto LABEL_521;
                }
                v136 = v245;
                v137 = v245 + 8;
                v245 = v137;
                if ( (unsigned __int64)v137 <= v251 )
                  *v136 = _byteswap_uint64(v13 + (v132 >> (6 - (unsigned __int8)v100)));
                v247 = v137;
                v135 = v68 + 40;
                if ( v100 == 6 )
                  goto LABEL_518;
                v10 = v100 + 58;
              }
LABEL_520:
              v13 = v135 << v10;
              goto LABEL_521;
            }
            v44 = v100 == 1;
            v10 = v100 - 1;
            v249 = v10;
            if ( v44 )
            {
              v130 = v245;
              v131 = v245 + 8;
              v245 = v131;
              if ( (unsigned __int64)v131 <= v251 )
                *v130 = _byteswap_uint64(v13);
              v247 = v131;
              goto LABEL_518;
            }
LABEL_522:
            v65 += v68;
LABEL_531:
            v16 = a1;
            LODWORD(v15) = a2;
            Src = v65;
            if ( (unsigned __int64)v65 >= v254 )
            {
              v62 = v253;
              goto LABEL_759;
            }
          }
        }
        if ( (unsigned __int64)Src >= v66 )
          goto LABEL_760;
        while ( 1 )
        {
          v166 = (char *)Src;
          v167 = *v65;
          v168 = *(_WORD *)Src;
          v169 = (char *)Src + 2;
          v170 = (_DWORD)Src - a2 + a4;
          v171 = v167
               ^ (8
                * (*((unsigned __int8 *)Src + 1)
                 ^ (16 * (*((unsigned __int8 *)Src + 2) ^ (unsigned __int64)(unsigned int)v167))));
          v172 = *(_DWORD *)(v16 + 4 * v171 + 160);
          *(_DWORD *)(a1 + 4 * v171 + 160) = v170;
          v173 = v170 - v172;
          if ( (unsigned int)v173 > *(_DWORD *)(a1 + 152)
            || (v174 = (_WORD *)(*(_QWORD *)(a1 + 136) + v172), *v174 != v168) )
          {
LABEL_750:
            v221 = HIDWORD(qword_180033700[v167]);
            v222 = LODWORD(qword_180033700[v167]);
            if ( v10 <= v221 )
            {
              OutputByteStream::OutputEightBytes(
                (OutputByteStream *)&v246,
                v13 + (v222 >> ((unsigned __int8)v221 - (unsigned __int8)v10)));
              v12 = v248;
              if ( v223 == v225 )
              {
                v10 = 64;
                v13 = 0;
              }
              else
              {
                v10 = 64 - v225 + v223;
                v13 = v224 << v10;
              }
              v245 = (char *)v247;
            }
            else
            {
              v10 -= v221;
              v13 += v222 << v10;
            }
            v65 = (unsigned __int8 *)Src + 1;
            v250 = v13;
            v249 = v10;
            goto LABEL_757;
          }
          *(_QWORD *)(a1 + 144) = v174;
          v175 = v174 + 1;
          if ( (unsigned int)(v62 - (_DWORD)v166) > 6 )
          {
            if ( *v169 != *v175 )
              goto LABEL_750;
            if ( v169[1] != v175[1] )
            {
              v176 = 3;
              goto LABEL_552;
            }
            if ( v169[2] != v175[2] )
            {
              v176 = 4;
              goto LABEL_552;
            }
            if ( v169[3] != v175[3] )
            {
              v176 = 5;
              goto LABEL_552;
            }
            v177 = v169[4];
            v169 += 5;
            if ( v177 != v175[4] )
            {
              v176 = 6;
              goto LABEL_552;
            }
            v175 += 5;
          }
          while ( v169 < &v166[v62 - (_DWORD)v166] && *v169 == *v175 )
          {
            ++v175;
            ++v169;
          }
          v176 = (_DWORD)v169 - (_DWORD)v166;
          if ( !v176 )
            goto LABEL_750;
LABEL_552:
          if ( (unsigned int)v173 >= 0x1000 )
          {
            if ( v176 >= 4 && (unsigned int)v173 < 0x10000 )
            {
LABEL_584:
              if ( (unsigned int)v173 >= 0x16A0 )
              {
                if ( (unsigned int)v173 >= 0x56A0 )
                {
                  if ( (unsigned int)v173 >= 0xD6A0 )
                  {
                    if ( (unsigned int)v173 >= 0x4D6A0 )
                    {
                      if ( (unsigned int)v173 >= 0x14D6A0 )
                      {
                        if ( (unsigned int)v173 >= 0x24D6A0 )
                        {
                          if ( (unsigned int)v173 >= 0x44D6A0 )
                          {
                            if ( (unsigned int)v173 >= 0x84D6A0 )
                            {
                              if ( (unsigned int)v173 >= 0x104D6A0 )
                              {
                                v178 = v173 + 0x17CFB2960LL;
                                if ( v10 > 0x21 )
                                {
                                  v179 = v10 - 33;
                                  goto LABEL_649;
                                }
                                v194 = v17;
                                v17 += 8;
                                v245 = v17;
                                if ( v17 <= v12 )
                                  *v194 = _byteswap_uint64(v13 + (v178 >> (33 - (unsigned __int8)v10)));
                                v247 = v17;
                                if ( v10 == 33 )
                                  goto LABEL_653;
                                v179 = v10 + 31;
                                v181 = v178;
                              }
                              else
                              {
                                v178 = (unsigned int)(v173 - 1107613344);
                                if ( v10 > 0x20 )
                                {
                                  v179 = v10 - 32;
                                  goto LABEL_649;
                                }
                                v193 = v17;
                                v17 += 8;
                                v245 = v17;
                                if ( v17 <= v12 )
                                  *v193 = _byteswap_uint64(v13 + (v178 >> (32 - (unsigned __int8)v10)));
                                v247 = v17;
                                v181 = v178;
                                if ( v10 == 32 )
                                  goto LABEL_653;
                                v179 = v10 + 32;
                              }
                            }
                            else
                            {
                              v178 = (unsigned int)(v173 + 1589324128);
                              if ( v10 > 0x1F )
                              {
                                v179 = v10 - 31;
                                goto LABEL_649;
                              }
                              v192 = v17;
                              v17 += 8;
                              v245 = v17;
                              if ( v17 <= v12 )
                                *v192 = _byteswap_uint64(v13 + (v178 >> (31 - (unsigned __int8)v10)));
                              v247 = v17;
                              v181 = v178;
                              if ( v10 == 31 )
                                goto LABEL_653;
                              v179 = v10 + 33;
                            }
                          }
                          else
                          {
                            v178 = (unsigned int)(v173 + 393947488);
                            if ( v10 > 0x1D )
                            {
                              v179 = v10 - 29;
                              goto LABEL_649;
                            }
                            v191 = v17;
                            v17 += 8;
                            v245 = v17;
                            if ( v17 <= v12 )
                              *v191 = _byteswap_uint64(v13 + (v178 >> (29 - (unsigned __int8)v10)));
                            v247 = v17;
                            v181 = v178;
                            if ( v10 == 29 )
                              goto LABEL_653;
                            v179 = v10 + 35;
                          }
                        }
                        else
                        {
                          v178 = (unsigned int)(v173 + 195766624);
                          if ( v10 > 0x1C )
                          {
                            v179 = v10 - 28;
                            goto LABEL_649;
                          }
                          v190 = v17;
                          v17 += 8;
                          v245 = v17;
                          if ( v17 <= v12 )
                            *v190 = _byteswap_uint64(v13 + (v178 >> (28 - (unsigned __int8)v10)));
                          v247 = v17;
                          v181 = v178;
                          if ( v10 == 28 )
                            goto LABEL_653;
                          v179 = v10 + 36;
                        }
                      }
                      else
                      {
                        v178 = (unsigned int)(v173 + 97200480);
                        if ( v10 > 0x1B )
                        {
                          v179 = v10 - 27;
                          goto LABEL_649;
                        }
                        v189 = v17;
                        v17 += 8;
                        v245 = v17;
                        if ( v17 <= v12 )
                          *v189 = _byteswap_uint64(v13 + (v178 >> (27 - (unsigned __int8)v10)));
                        v247 = v17;
                        v181 = v178;
                        if ( v10 == 27 )
                          goto LABEL_653;
                        v179 = v10 + 37;
                      }
                    }
                    else
                    {
                      v178 = (unsigned int)(v173 + 24062304);
                      if ( v10 > 0x19 )
                      {
                        v179 = v10 - 25;
                        goto LABEL_649;
                      }
                      v188 = v17;
                      v17 += 8;
                      v245 = v17;
                      if ( v17 <= v12 )
                        *v188 = _byteswap_uint64(v13 + (v178 >> (25 - (unsigned __int8)v10)));
                      v247 = v17;
                      v181 = v178;
                      if ( v10 == 25 )
                        goto LABEL_653;
                      v179 = v10 + 39;
                    }
                  }
                  else
                  {
                    v178 = (unsigned int)(v173 + 1452384);
                    if ( v10 > 0x15 )
                    {
                      v179 = v10 - 21;
                      goto LABEL_649;
                    }
                    v187 = v17;
                    v17 += 8;
                    v245 = v17;
                    if ( v17 <= v12 )
                      *v187 = _byteswap_uint64(v13 + (v178 >> (21 - (unsigned __int8)v10)));
                    v247 = v17;
                    v181 = v178;
                    if ( v10 == 21 )
                      goto LABEL_653;
                    v179 = v10 + 43;
                  }
                }
                else
                {
                  v178 = (unsigned int)(v173 + 715104);
                  if ( v10 > 0x14 )
                  {
                    v179 = v10 - 20;
                    goto LABEL_649;
                  }
                  v186 = v17;
                  v17 += 8;
                  v245 = v17;
                  if ( v17 <= v12 )
                    *v186 = _byteswap_uint64(v13 + (v178 >> (20 - (unsigned __int8)v10)));
                  v247 = v17;
                  v181 = v178;
                  if ( v10 == 20 )
                    goto LABEL_653;
                  v179 = v10 + 44;
                }
              }
              else
              {
                v178 = (unsigned int)(v173 + 84320);
                if ( v10 > 0x11 )
                {
                  v179 = v10 - 17;
                  goto LABEL_649;
                }
                v185 = v17;
                v17 += 8;
                v245 = v17;
                if ( v17 <= v12 )
                  *v185 = _byteswap_uint64(v13 + (v178 >> (17 - (unsigned __int8)v10)));
                v247 = v17;
                v181 = v178;
                if ( v10 == 17 )
                  goto LABEL_653;
                v179 = v10 + 47;
              }
              goto LABEL_655;
            }
            if ( v176 < 5 )
              goto LABEL_750;
          }
          if ( (unsigned int)v173 >= 0x20 )
          {
            if ( (unsigned int)v173 >= 0xA0 )
            {
              if ( (unsigned int)v173 >= 0x2A0 )
              {
                if ( (unsigned int)v173 >= 0x6A0 )
                  goto LABEL_584;
                v178 = (unsigned int)(v173 + 19808);
                if ( v10 > 0xF )
                {
                  v179 = v10 - 15;
                  goto LABEL_649;
                }
                v184 = v17;
                v17 += 8;
                v245 = v17;
                if ( v17 <= v12 )
                  *v184 = _byteswap_uint64(v13 + (v178 >> (15 - (unsigned __int8)v10)));
                v247 = v17;
                v181 = v178;
                if ( v10 == 15 )
                  goto LABEL_653;
                v179 = v10 + 49;
              }
              else
              {
                v178 = (unsigned int)(v173 + 9568);
                if ( v10 > 0xE )
                {
                  v179 = v10 - 14;
                  goto LABEL_649;
                }
                v183 = v17;
                v17 += 8;
                v245 = v17;
                if ( v17 <= v12 )
                  *v183 = _byteswap_uint64(v13 + (v178 >> (14 - (unsigned __int8)v10)));
                v247 = v17;
                v181 = v178;
                if ( v10 == 14 )
                  goto LABEL_653;
                v179 = v10 + 50;
              }
            }
            else
            {
              v178 = (unsigned int)(v173 + 2272);
              if ( v10 > 0xC )
              {
                v179 = v10 - 12;
                goto LABEL_649;
              }
              v182 = v17;
              v17 += 8;
              v245 = v17;
              if ( v17 <= v12 )
                *v182 = _byteswap_uint64(v13 + (v178 >> (12 - (unsigned __int8)v10)));
              v247 = v17;
              v181 = v178;
              if ( v10 == 12 )
              {
LABEL_653:
                v179 = 64;
                v13 = 0;
                goto LABEL_656;
              }
              v179 = v10 + 52;
            }
          }
          else
          {
            v178 = (unsigned int)(v173 + 544);
            if ( v10 > 0xA )
            {
              v179 = v10 - 10;
LABEL_649:
              v13 += v178 << v179;
              goto LABEL_656;
            }
            v180 = v17;
            v17 += 8;
            v245 = v17;
            if ( v17 <= v12 )
              *v180 = _byteswap_uint64(v13 + (v178 >> (10 - (unsigned __int8)v10)));
            v247 = v17;
            v181 = v178;
            if ( v10 == 10 )
              goto LABEL_653;
            v179 = v10 + 54;
          }
LABEL_655:
          v13 = v181 << v179;
LABEL_656:
          v249 = v179;
          v250 = v13;
          if ( v176 >= 4 )
          {
            if ( v176 < 8 )
            {
              v197 = v176 + 4;
              if ( v179 > 4 )
              {
                v10 = v179 - 4;
                goto LABEL_664;
              }
              v198 = v17;
              v199 = v17 + 8;
              v245 = v199;
              if ( v199 <= v12 )
                *v198 = _byteswap_uint64(v13 + (v197 >> (4 - (unsigned __int8)v179)));
              v247 = v199;
              v200 = v176 + 4;
              if ( v179 == 4 )
              {
LABEL_668:
                v10 = 64;
                goto LABEL_669;
              }
              v10 = v179 + 60;
LABEL_746:
              v13 = v200 << v10;
LABEL_747:
              v249 = v10;
LABEL_748:
              v250 = v13;
              goto LABEL_749;
            }
            if ( v176 < 0x10 )
            {
              v197 = v176 + 40;
              if ( v179 <= 6 )
              {
                v201 = v17;
                v202 = v17 + 8;
                v245 = v202;
                if ( v202 <= v12 )
                  *v201 = _byteswap_uint64(v13 + (v197 >> (6 - (unsigned __int8)v179)));
                v247 = v202;
                v200 = v176 + 40;
                if ( v179 == 6 )
                  goto LABEL_668;
                v10 = v179 + 58;
                goto LABEL_746;
              }
              v10 = v179 - 6;
              goto LABEL_664;
            }
            if ( v176 < 0x20 )
            {
              v197 = v176 + 208;
              if ( v179 <= 8 )
              {
                v203 = v17;
                v204 = v17 + 8;
                v245 = v204;
                if ( v204 <= v12 )
                  *v203 = _byteswap_uint64(v13 + (v197 >> (8 - (unsigned __int8)v179)));
                v247 = v204;
                v200 = v176 + 208;
                if ( v179 == 8 )
                  goto LABEL_668;
                v10 = v179 + 56;
                goto LABEL_746;
              }
              v10 = v179 - 8;
              goto LABEL_664;
            }
            if ( v176 < 0x40 )
            {
              v197 = v176 + 928;
              if ( v179 <= 0xA )
              {
                v205 = v17;
                v206 = v17 + 8;
                v245 = v206;
                if ( v206 <= v12 )
                  *v205 = _byteswap_uint64(v13 + (v197 >> (10 - (unsigned __int8)v179)));
                v247 = v206;
                v200 = v176 + 928;
                if ( v179 != 10 )
                {
                  v10 = v179 + 54;
                  goto LABEL_746;
                }
                v10 = 64;
LABEL_669:
                v13 = 0;
                goto LABEL_747;
              }
              v10 = v179 - 10;
LABEL_664:
              v13 += v197 << v10;
              goto LABEL_747;
            }
            if ( v176 < 0x80 )
            {
              v207 = v176 + 3904;
              if ( v179 > 0xC )
              {
                v10 = v179 - 12;
LABEL_741:
                v13 += v207 << v10;
                goto LABEL_747;
              }
              OutputByteStream::OutputEightBytes(
                (OutputByteStream *)&v246,
                v13 + (v207 >> (12 - (unsigned __int8)v179)));
              v12 = v248;
              if ( v208 != 12 )
              {
                v10 = v208 + 52;
                goto LABEL_698;
              }
              goto LABEL_743;
            }
            if ( v176 >= 0x100 )
            {
              if ( v176 < 0x200 )
              {
                v207 = v176 + 64768;
                if ( v179 > 0x10 )
                {
                  v10 = v179 - 16;
                  goto LABEL_741;
                }
                OutputByteStream::OutputEightBytes(
                  (OutputByteStream *)&v246,
                  v13 + (v207 >> (16 - (unsigned __int8)v179)));
                v12 = v248;
                if ( v212 == 16 )
                  goto LABEL_743;
                v10 = v212 + 48;
                goto LABEL_698;
              }
              if ( v176 < 0x400 )
              {
                v207 = v176 + 260608;
                if ( v179 > 0x12 )
                {
                  v10 = v179 - 18;
                  goto LABEL_741;
                }
                OutputByteStream::OutputEightBytes(
                  (OutputByteStream *)&v246,
                  v13 + (v207 >> (18 - (unsigned __int8)v179)));
                v12 = v248;
                if ( v213 == 18 )
                  goto LABEL_743;
                v10 = v213 + 46;
                goto LABEL_698;
              }
              if ( v176 < 0x800 )
              {
                v207 = v176 + 1045504;
                if ( v179 > 0x14 )
                {
                  v10 = v179 - 20;
                  goto LABEL_741;
                }
                OutputByteStream::OutputEightBytes(
                  (OutputByteStream *)&v246,
                  v13 + (v207 >> (20 - (unsigned __int8)v179)));
                v12 = v248;
                if ( v214 == 20 )
                  goto LABEL_743;
                v10 = v214 + 44;
                goto LABEL_698;
              }
              if ( v176 < 0x1000 )
              {
                v207 = v176 + 4188160;
                if ( v179 > 0x16 )
                {
                  v10 = v179 - 22;
                  goto LABEL_741;
                }
                OutputByteStream::OutputEightBytes(
                  (OutputByteStream *)&v246,
                  v13 + (v207 >> (22 - (unsigned __int8)v179)));
                v12 = v248;
                if ( v215 == 22 )
                  goto LABEL_743;
                v10 = v215 + 42;
                goto LABEL_698;
              }
              if ( v176 < 0x2000 )
              {
                v207 = v176 + 16764928;
                if ( v179 > 0x18 )
                {
                  v10 = v179 - 24;
                  goto LABEL_741;
                }
                OutputByteStream::OutputEightBytes(
                  (OutputByteStream *)&v246,
                  v13 + (v207 >> (24 - (unsigned __int8)v179)));
                v12 = v248;
                if ( v216 == 24 )
                  goto LABEL_743;
                v10 = v216 + 40;
                goto LABEL_698;
              }
              if ( v176 < 0x4000 )
              {
                v207 = v176 + 67084288;
                if ( v179 > 0x1A )
                {
                  v10 = v179 - 26;
                  goto LABEL_741;
                }
                OutputByteStream::OutputEightBytes(
                  (OutputByteStream *)&v246,
                  v13 + (v207 >> (26 - (unsigned __int8)v179)));
                v12 = v248;
                if ( v217 == 26 )
                  goto LABEL_743;
                v10 = v217 + 38;
                goto LABEL_698;
              }
              if ( v176 >= 0x8000 )
              {
                v207 = v176 + 1073643520;
                if ( v179 > 0x1E )
                {
                  v10 = v179 - 30;
                  goto LABEL_741;
                }
                OutputByteStream::OutputEightBytes(
                  (OutputByteStream *)&v246,
                  v13 + (v207 >> (30 - (unsigned __int8)v179)));
                v12 = v248;
                if ( v219 != 30 )
                {
                  v10 = v219 + 34;
                  v245 = (char *)v247;
                  v200 = v220;
                  goto LABEL_746;
                }
                goto LABEL_743;
              }
              v207 = v176 + 268386304;
              if ( v179 > 0x1C )
              {
                v10 = v179 - 28;
                goto LABEL_741;
              }
              OutputByteStream::OutputEightBytes(
                (OutputByteStream *)&v246,
                v13 + (v207 >> (28 - (unsigned __int8)v179)));
              v12 = v248;
              if ( v218 != 28 )
              {
                v10 = v218 + 36;
                goto LABEL_698;
              }
LABEL_743:
              v13 = 0;
              v10 = v210;
            }
            else
            {
              v207 = v176 + 16000;
              if ( v179 > 0xE )
              {
                v10 = v179 - 14;
                goto LABEL_741;
              }
              OutputByteStream::OutputEightBytes(
                (OutputByteStream *)&v246,
                v13 + (v207 >> (14 - (unsigned __int8)v179)));
              v12 = v248;
              if ( v211 == 14 )
                goto LABEL_743;
              v10 = v211 + 50;
LABEL_698:
              v13 = v209 << v10;
            }
            v245 = (char *)v247;
            goto LABEL_747;
          }
          v44 = v179 == 1;
          v10 = v179 - 1;
          v249 = v10;
          if ( v44 )
          {
            v195 = v17;
            v196 = v17 + 8;
            v245 = v196;
            if ( v196 <= v12 )
              *v195 = _byteswap_uint64(v13);
            v247 = v196;
            v10 = 64;
            v249 = 64;
            v13 = 0;
            goto LABEL_748;
          }
LABEL_749:
          v65 = (unsigned __int8 *)Src + v176;
LABEL_757:
          v17 = v245;
          v16 = a1;
          Src = v65;
          if ( (unsigned __int64)v65 >= v66 )
          {
            v251 = (unsigned __int64)v12;
LABEL_759:
            v15 = a2;
LABEL_760:
            v226 = v62 - (_DWORD)v65;
            if ( v226 < 0x28 )
            {
              if ( v226 )
              {
                do
                {
                  v235 = *v65;
                  --v226;
                  ++v65;
                  v236 = HIDWORD(qword_180033700[v235]);
                  v237 = LODWORD(qword_180033700[v235]);
                  if ( v10 <= v236 )
                  {
                    OutputByteStream::OutputEightBytes(
                      (OutputByteStream *)&v246,
                      v13 + (v237 >> ((unsigned __int8)v236 - (unsigned __int8)v10)));
                    if ( v238 == v240 )
                    {
                      v10 = 64;
                      v13 = 0;
                    }
                    else
                    {
                      v10 = 64 - v240 + v238;
                      v13 = v239 << v10;
                    }
                  }
                  else
                  {
                    v10 -= v236;
                    v13 += v237 << v10;
                  }
                  v250 = v13;
                  v249 = v10;
                }
                while ( v226 );
                v12 = v248;
                v17 = (char *)v247;
                v251 = (unsigned __int64)v248;
                v245 = (char *)v247;
                goto LABEL_773;
              }
              v17 = v245;
              v12 = (char *)v251;
            }
            else
            {
              v227 = v226;
              v228 = v65;
              do
              {
                v229 = 0x7FFF;
                if ( v227 < 0x7FFF )
                  v229 = v227;
                v230 = (unsigned int)(v229 + 17825792);
                if ( v10 <= 0x19 )
                {
                  OutputByteStream::OutputEightBytes(
                    (OutputByteStream *)&v246,
                    v13 + (v230 >> (25 - (unsigned __int8)v10)));
                  if ( v233 == 25 )
                  {
                    v231 = 64;
                    v232 = 0;
                  }
                  else
                  {
                    v231 = v233 + 39;
                    v232 = v234 << v231;
                  }
                }
                else
                {
                  v231 = v10 - 25;
                  v232 = (v230 << v231) + v13;
                }
                v250 = v232;
                v249 = v231;
                OutputBitStream::OutputFlush((OutputBitStream *)&v246);
                v12 = v248;
                v251 = (unsigned __int64)v248;
                v17 = (char *)v247 + v229;
                v245 = (char *)v247 + v229;
                if ( (char *)v247 + v229 <= v248 )
                  memcpy_0(v247, v228, (unsigned int)v229);
                v13 = v250;
                v228 += (unsigned int)v229;
                v10 = v249;
                v247 = v17;
                v227 -= v229;
              }
              while ( v227 );
              LODWORD(v65) = v226 + (_DWORD)Src;
LABEL_773:
              v15 = a2;
            }
            v11 = a3;
            v241 = (unsigned int)((_DWORD)v65 - v15);
            v16 = a1;
            v14 = v241;
            Src = (void *)v241;
            v18 = a3 - 3;
            if ( (unsigned int)v241 >= a3 )
            {
              v9 = a7;
              goto LABEL_785;
            }
            goto LABEL_3;
          }
        }
      }
      if ( v24 >= 8 )
      {
        if ( v24 >= 0x10 )
        {
          if ( v24 >= 0x20 )
          {
            if ( v24 >= 0x40 )
            {
              if ( v24 >= 0x80 )
              {
                if ( v24 >= 0x100 )
                {
                  if ( v24 >= 0x200 )
                  {
                    if ( v24 >= 0x400 )
                    {
                      if ( v24 >= 0x800 )
                      {
                        if ( v24 >= 0x1000 )
                        {
                          if ( v24 >= 0x2000 )
                          {
                            if ( v24 >= 0x4000 )
                            {
                              if ( v24 >= 0x8000 )
                              {
                                v46 = v24 + 1073643520;
                                if ( v27 > 0x1E )
                                {
                                  v10 = v27 - 30;
                                  goto LABEL_207;
                                }
                                v61 = v17;
                                v17 += 8;
                                v245 = v17;
                                if ( v17 <= v12 )
                                  *v61 = _byteswap_uint64(v13 + (v46 >> (30 - (unsigned __int8)v27)));
                                v247 = v17;
                                v48 = v24 + 1073643520;
                                if ( v27 != 30 )
                                {
                                  v10 = v27 + 34;
                                  goto LABEL_213;
                                }
                              }
                              else
                              {
                                v46 = v24 + 268386304;
                                if ( v27 > 0x1C )
                                {
                                  v10 = v27 - 28;
                                  goto LABEL_207;
                                }
                                v60 = v17;
                                v17 += 8;
                                v245 = v17;
                                if ( v17 <= v12 )
                                  *v60 = _byteswap_uint64(v13 + (v46 >> (28 - (unsigned __int8)v27)));
                                v247 = v17;
                                v48 = v24 + 268386304;
                                if ( v27 != 28 )
                                {
                                  v10 = v27 + 36;
                                  goto LABEL_213;
                                }
                              }
                            }
                            else
                            {
                              v46 = v24 + 67084288;
                              if ( v27 > 0x1A )
                              {
                                v10 = v27 - 26;
                                goto LABEL_207;
                              }
                              v59 = v17;
                              v17 += 8;
                              v245 = v17;
                              if ( v17 <= v12 )
                                *v59 = _byteswap_uint64(v13 + (v46 >> (26 - (unsigned __int8)v27)));
                              v247 = v17;
                              v48 = v24 + 67084288;
                              if ( v27 != 26 )
                              {
                                v10 = v27 + 38;
                                goto LABEL_213;
                              }
                            }
                          }
                          else
                          {
                            v46 = v24 + 16764928;
                            if ( v27 > 0x18 )
                            {
                              v10 = v27 - 24;
                              goto LABEL_207;
                            }
                            v58 = v17;
                            v17 += 8;
                            v245 = v17;
                            if ( v17 <= v12 )
                              *v58 = _byteswap_uint64(v13 + (v46 >> (24 - (unsigned __int8)v27)));
                            v247 = v17;
                            v48 = v24 + 16764928;
                            if ( v27 != 24 )
                            {
                              v10 = v27 + 40;
                              goto LABEL_213;
                            }
                          }
                        }
                        else
                        {
                          v46 = v24 + 4188160;
                          if ( v27 > 0x16 )
                          {
                            v10 = v27 - 22;
                            goto LABEL_207;
                          }
                          v57 = v17;
                          v17 += 8;
                          v245 = v17;
                          if ( v17 <= v12 )
                            *v57 = _byteswap_uint64(v13 + (v46 >> (22 - (unsigned __int8)v27)));
                          v247 = v17;
                          v48 = v24 + 4188160;
                          if ( v27 != 22 )
                          {
                            v10 = v27 + 42;
                            goto LABEL_213;
                          }
                        }
                      }
                      else
                      {
                        v46 = v24 + 1045504;
                        if ( v27 > 0x14 )
                        {
                          v10 = v27 - 20;
                          goto LABEL_207;
                        }
                        v56 = v17;
                        v17 += 8;
                        v245 = v17;
                        if ( v17 <= v12 )
                          *v56 = _byteswap_uint64(v13 + (v46 >> (20 - (unsigned __int8)v27)));
                        v247 = v17;
                        v48 = v24 + 1045504;
                        if ( v27 != 20 )
                        {
                          v10 = v27 + 44;
                          goto LABEL_213;
                        }
                      }
                    }
                    else
                    {
                      v46 = v24 + 260608;
                      if ( v27 > 0x12 )
                      {
                        v10 = v27 - 18;
                        goto LABEL_207;
                      }
                      v55 = v17;
                      v17 += 8;
                      v245 = v17;
                      if ( v17 <= v12 )
                        *v55 = _byteswap_uint64(v13 + (v46 >> (18 - (unsigned __int8)v27)));
                      v247 = v17;
                      v48 = v24 + 260608;
                      if ( v27 != 18 )
                      {
                        v10 = v27 + 46;
                        goto LABEL_213;
                      }
                    }
                  }
                  else
                  {
                    v46 = v24 + 64768;
                    if ( v27 > 0x10 )
                    {
                      v10 = v27 - 16;
                      goto LABEL_207;
                    }
                    v54 = v17;
                    v17 += 8;
                    v245 = v17;
                    if ( v17 <= v12 )
                      *v54 = _byteswap_uint64(v13 + (v46 >> (16 - (unsigned __int8)v27)));
                    v247 = v17;
                    v48 = v24 + 64768;
                    if ( v27 != 16 )
                    {
                      v10 = v27 + 48;
                      goto LABEL_213;
                    }
                  }
                }
                else
                {
                  v46 = v24 + 16000;
                  if ( v27 > 0xE )
                  {
                    v10 = v27 - 14;
                    goto LABEL_207;
                  }
                  v53 = v17;
                  v17 += 8;
                  v245 = v17;
                  if ( v17 <= v12 )
                    *v53 = _byteswap_uint64(v13 + (v46 >> (14 - (unsigned __int8)v27)));
                  v247 = v17;
                  v48 = v24 + 16000;
                  if ( v27 != 14 )
                  {
                    v10 = v27 + 50;
                    goto LABEL_213;
                  }
                }
              }
              else
              {
                v46 = v24 + 3904;
                if ( v27 > 0xC )
                {
                  v10 = v27 - 12;
                  goto LABEL_207;
                }
                v52 = v17;
                v17 += 8;
                v245 = v17;
                if ( v17 <= v12 )
                  *v52 = _byteswap_uint64(v13 + (v46 >> (12 - (unsigned __int8)v27)));
                v247 = v17;
                v48 = v24 + 3904;
                if ( v27 != 12 )
                {
                  v10 = v27 + 52;
                  goto LABEL_213;
                }
              }
            }
            else
            {
              v46 = v24 + 928;
              if ( v27 > 0xA )
              {
                v10 = v27 - 10;
                goto LABEL_207;
              }
              v51 = v17;
              v17 += 8;
              v245 = v17;
              if ( v17 <= v12 )
                *v51 = _byteswap_uint64(v13 + (v46 >> (10 - (unsigned __int8)v27)));
              v247 = v17;
              v48 = v24 + 928;
              if ( v27 != 10 )
              {
                v10 = v27 + 54;
                goto LABEL_213;
              }
            }
          }
          else
          {
            v46 = v24 + 208;
            if ( v27 > 8 )
            {
              v10 = v27 - 8;
              goto LABEL_207;
            }
            v50 = v17;
            v17 += 8;
            v245 = v17;
            if ( v17 <= v12 )
              *v50 = _byteswap_uint64(v13 + (v46 >> (8 - (unsigned __int8)v27)));
            v247 = v17;
            v48 = v24 + 208;
            if ( v27 != 8 )
            {
              v10 = v27 + 56;
              goto LABEL_213;
            }
          }
        }
        else
        {
          v46 = v24 + 40;
          if ( v27 > 6 )
          {
            v10 = v27 - 6;
            goto LABEL_207;
          }
          v49 = v17;
          v17 += 8;
          v245 = v17;
          if ( v17 <= v12 )
            *v49 = _byteswap_uint64(v13 + (v46 >> (6 - (unsigned __int8)v27)));
          v247 = v17;
          v48 = v24 + 40;
          if ( v27 != 6 )
          {
            v10 = v27 + 58;
            goto LABEL_213;
          }
        }
      }
      else
      {
        v46 = v24 + 4;
        if ( v27 > 4 )
        {
          v10 = v27 - 4;
LABEL_207:
          v13 += v46 << v10;
LABEL_214:
          v250 = v13;
          v249 = v10;
          goto LABEL_215;
        }
        v47 = v17;
        v17 += 8;
        v245 = v17;
        if ( v17 <= v12 )
          *v47 = _byteswap_uint64(v13 + (v46 >> (4 - (unsigned __int8)v27)));
        v247 = v17;
        v48 = v24 + 4;
        if ( v27 != 4 )
        {
          v10 = v27 + 60;
LABEL_213:
          v13 = v48 << v10;
          goto LABEL_214;
        }
      }
LABEL_211:
      v10 = 64;
      v13 = 0;
      goto LABEL_214;
    }
    if ( (unsigned int)v25 >= 0xA0 )
    {
      if ( (unsigned int)v25 >= 0x2A0 )
      {
        if ( (unsigned int)v25 >= 0x6A0 )
        {
          if ( (unsigned int)v25 >= 0x16A0 )
          {
            if ( (unsigned int)v25 >= 0x56A0 )
            {
              if ( (unsigned int)v25 >= 0xD6A0 )
              {
                if ( (unsigned int)v25 >= 0x4D6A0 )
                {
                  if ( (unsigned int)v25 >= 0x14D6A0 )
                  {
                    if ( (unsigned int)v25 >= 0x24D6A0 )
                    {
                      if ( (unsigned int)v25 >= 0x44D6A0 )
                      {
                        if ( (unsigned int)v25 >= 0x84D6A0 )
                        {
                          if ( (unsigned int)v25 >= 0x104D6A0 )
                          {
                            v26 = v25 + 0x17CFB2960LL;
                            if ( v10 > 0x21 )
                            {
                              v27 = v10 - 33;
                              goto LABEL_102;
                            }
                            v43 = v17;
                            v17 += 8;
                            v245 = v17;
                            if ( v17 <= v12 )
                              *v43 = _byteswap_uint64(v13 + (v26 >> (33 - (unsigned __int8)v10)));
                            v247 = v17;
                            if ( v10 == 33 )
                              goto LABEL_106;
                            v27 = v10 + 31;
                            v29 = v25 + 0x17CFB2960LL;
                          }
                          else
                          {
                            v41 = v25 - 1107613344;
                            v26 = v41;
                            if ( v10 > 0x20 )
                            {
                              v27 = v10 - 32;
                              goto LABEL_102;
                            }
                            v42 = v17;
                            v17 += 8;
                            v245 = v17;
                            if ( v17 <= v12 )
                              *v42 = _byteswap_uint64(v13 + ((unsigned __int64)v41 >> (32 - (unsigned __int8)v10)));
                            v247 = v17;
                            v29 = v41;
                            if ( v10 == 32 )
                              goto LABEL_106;
                            v27 = v10 + 32;
                          }
                        }
                        else
                        {
                          v26 = (unsigned int)(v25 + 1589324128);
                          if ( v10 > 0x1F )
                          {
                            v27 = v10 - 31;
                            goto LABEL_102;
                          }
                          v40 = v17;
                          v17 += 8;
                          v245 = v17;
                          if ( v17 <= v12 )
                            *v40 = _byteswap_uint64(v13 + (v26 >> (31 - (unsigned __int8)v10)));
                          v247 = v17;
                          v29 = (unsigned int)(v25 + 1589324128);
                          if ( v10 == 31 )
                            goto LABEL_106;
                          v27 = v10 + 33;
                        }
                      }
                      else
                      {
                        v26 = (unsigned int)(v25 + 393947488);
                        if ( v10 > 0x1D )
                        {
                          v27 = v10 - 29;
                          goto LABEL_102;
                        }
                        v39 = v17;
                        v17 += 8;
                        v245 = v17;
                        if ( v17 <= v12 )
                          *v39 = _byteswap_uint64(v13 + (v26 >> (29 - (unsigned __int8)v10)));
                        v247 = v17;
                        v29 = (unsigned int)(v25 + 393947488);
                        if ( v10 == 29 )
                          goto LABEL_106;
                        v27 = v10 + 35;
                      }
                    }
                    else
                    {
                      v26 = (unsigned int)(v25 + 195766624);
                      if ( v10 > 0x1C )
                      {
                        v27 = v10 - 28;
                        goto LABEL_102;
                      }
                      v38 = v17;
                      v17 += 8;
                      v245 = v17;
                      if ( v17 <= v12 )
                        *v38 = _byteswap_uint64(v13 + (v26 >> (28 - (unsigned __int8)v10)));
                      v247 = v17;
                      v29 = (unsigned int)(v25 + 195766624);
                      if ( v10 == 28 )
                        goto LABEL_106;
                      v27 = v10 + 36;
                    }
                  }
                  else
                  {
                    v26 = (unsigned int)(v25 + 97200480);
                    if ( v10 > 0x1B )
                    {
                      v27 = v10 - 27;
                      goto LABEL_102;
                    }
                    v37 = v17;
                    v17 += 8;
                    v245 = v17;
                    if ( v17 <= v12 )
                      *v37 = _byteswap_uint64(v13 + (v26 >> (27 - (unsigned __int8)v10)));
                    v247 = v17;
                    v29 = (unsigned int)(v25 + 97200480);
                    if ( v10 == 27 )
                      goto LABEL_106;
                    v27 = v10 + 37;
                  }
                }
                else
                {
                  v26 = (unsigned int)(v25 + 24062304);
                  if ( v10 > 0x19 )
                  {
                    v27 = v10 - 25;
                    goto LABEL_102;
                  }
                  v36 = v17;
                  v17 += 8;
                  v245 = v17;
                  if ( v17 <= v12 )
                    *v36 = _byteswap_uint64(v13 + (v26 >> (25 - (unsigned __int8)v10)));
                  v247 = v17;
                  v29 = (unsigned int)(v25 + 24062304);
                  if ( v10 == 25 )
                    goto LABEL_106;
                  v27 = v10 + 39;
                }
              }
              else
              {
                v26 = (unsigned int)(v25 + 1452384);
                if ( v10 > 0x15 )
                {
                  v27 = v10 - 21;
                  goto LABEL_102;
                }
                v35 = v17;
                v17 += 8;
                v245 = v17;
                if ( v17 <= v12 )
                  *v35 = _byteswap_uint64(v13 + (v26 >> (21 - (unsigned __int8)v10)));
                v247 = v17;
                v29 = (unsigned int)(v25 + 1452384);
                if ( v10 == 21 )
                  goto LABEL_106;
                v27 = v10 + 43;
              }
            }
            else
            {
              v26 = (unsigned int)(v25 + 715104);
              if ( v10 > 0x14 )
              {
                v27 = v10 - 20;
                goto LABEL_102;
              }
              v34 = v17;
              v17 += 8;
              v245 = v17;
              if ( v17 <= v12 )
                *v34 = _byteswap_uint64(v13 + (v26 >> (20 - (unsigned __int8)v10)));
              v247 = v17;
              v29 = (unsigned int)(v25 + 715104);
              if ( v10 == 20 )
                goto LABEL_106;
              v27 = v10 + 44;
            }
          }
          else
          {
            v26 = (unsigned int)(v25 + 84320);
            if ( v10 > 0x11 )
            {
              v27 = v10 - 17;
              goto LABEL_102;
            }
            v33 = v17;
            v17 += 8;
            v245 = v17;
            if ( v17 <= v12 )
              *v33 = _byteswap_uint64(v13 + (v26 >> (17 - (unsigned __int8)v10)));
            v247 = v17;
            v29 = (unsigned int)(v25 + 84320);
            if ( v10 == 17 )
              goto LABEL_106;
            v27 = v10 + 47;
          }
        }
        else
        {
          v26 = (unsigned int)(v25 + 19808);
          if ( v10 > 0xF )
          {
            v27 = v10 - 15;
            goto LABEL_102;
          }
          v32 = v17;
          v17 += 8;
          v245 = v17;
          if ( v17 <= v12 )
            *v32 = _byteswap_uint64(v13 + (v26 >> (15 - (unsigned __int8)v10)));
          v247 = v17;
          v29 = (unsigned int)(v25 + 19808);
          if ( v10 == 15 )
            goto LABEL_106;
          v27 = v10 + 49;
        }
      }
      else
      {
        v26 = (unsigned int)(v25 + 9568);
        if ( v10 > 0xE )
        {
          v27 = v10 - 14;
          goto LABEL_102;
        }
        v31 = v17;
        v17 += 8;
        v245 = v17;
        if ( v17 <= v12 )
          *v31 = _byteswap_uint64(v13 + (v26 >> (14 - (unsigned __int8)v10)));
        v247 = v17;
        v29 = (unsigned int)(v25 + 9568);
        if ( v10 == 14 )
          goto LABEL_106;
        v27 = v10 + 50;
      }
    }
    else
    {
      v26 = (unsigned int)(v25 + 2272);
      if ( v10 > 0xC )
      {
        v27 = v10 - 12;
LABEL_102:
        v13 += v26 << v27;
        goto LABEL_109;
      }
      v30 = v17;
      v17 += 8;
      v245 = v17;
      if ( v17 <= v12 )
        *v30 = _byteswap_uint64(v13 + (v26 >> (12 - (unsigned __int8)v10)));
      v247 = v17;
      v29 = (unsigned int)(v25 + 2272);
      if ( v10 == 12 )
        goto LABEL_106;
      v27 = v10 + 52;
    }
LABEL_108:
    v13 = v29 << v27;
    goto LABEL_109;
  }
LABEL_785:
  v242 = 8 * (_BYTE)v247 - v10;
  if ( OutputBitStream::OutputFlush((OutputBitStream *)&v246)
    && (v243 = (unsigned int)v247 + ((unsigned int)(71 - v249) >> 3) - (_DWORD)v246, (unsigned int)v243 < a8) )
  {
    v9[v243] = (8 - (v242 & 7)) % 8;
    *a9 = v243 + 1;
    return 0;
  }
  else
  {
    *a9 = 0;
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180024304  mov     rax, rsp
0x180024307  mov     [rax+20h], r9d
0x18002430b  mov     [rax+18h], r8d
0x18002430f  mov     [rax+10h], rdx
0x180024313  mov     [rax+8], rcx
0x180024317  push    rbp
0x180024318  push    rbx
0x180024319  push    rsi
0x18002431a  push    rdi
0x18002431b  push    r12
0x18002431d  push    r13
0x18002431f  push    r14
0x180024321  push    r15
0x180024323  lea     rbp, [rax-47h]
0x180024327  sub     rsp, 88h
0x18002432e  mov     rdi, [rbp+3Fh+arg_30]
0x180024332  mov     r9d, 40h ; '@'
0x180024338  mov     r12d, [rbp+3Fh+arg_38]
0x18002433f  mov     r11d, r8d
0x180024342  add     r12, rdi
0x180024345  mov     dword ptr [rbp+3Fh+var_98], edi
0x180024348  xor     r8d, r8d
0x18002434b  mov     [rbp+3Fh+var_A0], rdi
0x18002434f  mov     rax, rdi
0x180024352  mov     [rbp+3Fh+var_90], rdi
0x180024356  sar     rax, 20h
0x18002435a  lea     r13d, [r9-38h]
0x18002435e  xor     esi, esi
0x180024360  mov     dword ptr [rbp+3Fh+var_98+4], eax
0x180024363  mov     [rbp+3Fh+var_70], r12
0x180024367  mov     r14, rdx
0x18002436a  mov     [rbp+3Fh+var_88], r12
0x18002436e  mov     r10, rcx
0x180024371  mov     [rbp+3Fh+var_80], r9d
0x180024375  mov     r15, rdi
0x180024378  mov     [rbp+3Fh+var_78], r8
0x18002437c  test    r11d, r11d
0x18002437f  jz      loc_180026C04
0x180024385  lea     eax, [r11-3]
0x180024389  mov     rdx, 17CFB2960h
0x180024393  mov     r13, [rbp+3Fh+arg_20]
0x180024397  mov     ebx, r11d
0x18002439a  mov     ecx, [rbp+3Fh+arg_28]
0x18002439d  mov     edi, eax
0x18002439f  test    ecx, ecx
0x1800243a1  jz      loc_180024E60
0x1800243a7  mov     eax, [r13+0]
0x1800243ab  cmp     esi, eax
0x1800243ad  jb      loc_180024E5B
0x1800243b3  jz      short loc_1800243C4
0x1800243b5  add     r13, 0Ch
0x1800243b9  dec     ecx
0x1800243bb  mov     [rbp+3Fh+arg_20], r13
0x1800243bf  mov     [rbp+3Fh+arg_28], ecx
0x1800243c2  jmp     short loc_18002439F
0x1800243c4  mov     r11d, [r13+4]
0x1800243c8  xor     edi, edi
0x1800243ca  mov     eax, [r13+8]
0x1800243ce  lea     ebx, [r11+rsi]
0x1800243d2  test    eax, eax
0x1800243d4  jz      loc_180024E60
0x1800243da  cmp     eax, 20h ; ' '
0x1800243dd  jnb     short loc_180024435
0x1800243df  lea     edx, [rax+220h]
0x1800243e5  cmp     r9d, 0Ah
0x1800243e9  jbe     short loc_1800243F4
0x1800243eb  add     r9d, 0FFFFFFF6h
0x1800243ef  jmp     loc_180024895
0x1800243f4  mov     r10, r15
0x1800243f7  add     r15, 8
0x1800243fb  mov     [rbp+3Fh+var_A0], r15
0x1800243ff  cmp     r15, r12
0x180024402  ja      short loc_18002441B
0x180024404  mov     ecx, 0Ah
0x180024409  mov     rax, rdx
0x18002440c  sub     ecx, r9d
0x18002440f  shr     rax, cl
0x180024412  add     rax, r8
0x180024415  bswap   rax
0x180024418  mov     [r10], rax
0x18002441b  mov     [rbp+3Fh+var_90], r15
0x18002441f  mov     r8, rdx
0x180024422  cmp     r9d, 0Ah
0x180024426  jz      loc_1800248D1
0x18002442c  add     r9d, 36h ; '6'
0x180024430  jmp     loc_1800248E3
0x180024435  cmp     eax, 0A0h
0x18002443a  jnb     short loc_180024492
0x18002443c  lea     edx, [rax+8E0h]
0x180024442  cmp     r9d, 0Ch
0x180024446  jbe     short loc_180024451
0x180024448  add     r9d, 0FFFFFFF4h
0x18002444c  jmp     loc_180024895
0x180024451  mov     r10, r15
0x180024454  add     r15, 8
0x180024458  mov     [rbp+3Fh+var_A0], r15
0x18002445c  cmp     r15, r12
0x18002445f  ja      short loc_180024478
0x180024461  mov     ecx, 0Ch
0x180024466  mov     rax, rdx
0x180024469  sub     ecx, r9d
0x18002446c  shr     rax, cl
0x18002446f  add     rax, r8
0x180024472  bswap   rax
0x180024475  mov     [r10], rax
0x180024478  mov     [rbp+3Fh+var_90], r15
0x18002447c  mov     r8, rdx
0x18002447f  cmp     r9d, 0Ch
0x180024483  jz      loc_1800248D1
0x180024489  add     r9d, 34h ; '4'
0x18002448d  jmp     loc_1800248E3
0x180024492  cmp     eax, 2A0h
0x180024497  jnb     short loc_1800244EF
0x180024499  lea     edx, [rax+2560h]
0x18002449f  cmp     r9d, 0Eh
0x1800244a3  jbe     short loc_1800244AE
0x1800244a5  add     r9d, 0FFFFFFF2h
0x1800244a9  jmp     loc_180024895
0x1800244ae  mov     r10, r15
0x1800244b1  add     r15, 8
0x1800244b5  mov     [rbp+3Fh+var_A0], r15
0x1800244b9  cmp     r15, r12
0x1800244bc  ja      short loc_1800244D5
0x1800244be  mov     ecx, 0Eh
0x1800244c3  mov     rax, rdx
0x1800244c6  sub     ecx, r9d
0x1800244c9  shr     rax, cl
0x1800244cc  add     rax, r8
0x1800244cf  bswap   rax
0x1800244d2  mov     [r10], rax
0x1800244d5  mov     [rbp+3Fh+var_90], r15
0x1800244d9  mov     r8, rdx
0x1800244dc  cmp     r9d, 0Eh
0x1800244e0  jz      loc_1800248D1
0x1800244e6  add     r9d, 32h ; '2'
0x1800244ea  jmp     loc_1800248E3
0x1800244ef  cmp     eax, 6A0h
0x1800244f4  jnb     short loc_18002454C
0x1800244f6  lea     edx, [rax+4D60h]
0x1800244fc  cmp     r9d, 0Fh
0x180024500  jbe     short loc_18002450B
0x180024502  add     r9d, 0FFFFFFF1h
0x180024506  jmp     loc_180024895
0x18002450b  mov     r10, r15
0x18002450e  add     r15, 8
0x180024512  mov     [rbp+3Fh+var_A0], r15
0x180024516  cmp     r15, r12
0x180024519  ja      short loc_180024532
0x18002451b  mov     ecx, 0Fh
0x180024520  mov     rax, rdx
0x180024523  sub     ecx, r9d
0x180024526  shr     rax, cl
0x180024529  add     rax, r8
0x18002452c  bswap   rax
0x18002452f  mov     [r10], rax
0x180024532  mov     [rbp+3Fh+var_90], r15
0x180024536  mov     r8, rdx
0x180024539  cmp     r9d, 0Fh
0x18002453d  jz      loc_1800248D1
0x180024543  add     r9d, 31h ; '1'
0x180024547  jmp     loc_1800248E3
0x18002454c  cmp     eax, 16A0h
0x180024551  jnb     short loc_1800245A9
0x180024553  lea     edx, [rax+14960h]
0x180024559  cmp     r9d, 11h
0x18002455d  jbe     short loc_180024568
0x18002455f  add     r9d, 0FFFFFFEFh
0x180024563  jmp     loc_180024895
0x180024568  mov     r10, r15
0x18002456b  add     r15, 8
0x18002456f  mov     [rbp+3Fh+var_A0], r15
0x180024573  cmp     r15, r12
0x180024576  ja      short loc_18002458F
0x180024578  mov     ecx, 11h
0x18002457d  mov     rax, rdx
0x180024580  sub     ecx, r9d
0x180024583  shr     rax, cl
0x180024586  add     rax, r8
0x180024589  bswap   rax
0x18002458c  mov     [r10], rax
0x18002458f  mov     [rbp+3Fh+var_90], r15
0x180024593  mov     r8, rdx
0x180024596  cmp     r9d, 11h
0x18002459a  jz      loc_1800248D1
0x1800245a0  add     r9d, 2Fh ; '/'
0x1800245a4  jmp     loc_1800248E3
0x1800245a9  cmp     eax, 56A0h
0x1800245ae  jnb     short loc_180024606
0x1800245b0  lea     edx, [rax+0AE960h]
0x1800245b6  cmp     r9d, 14h
0x1800245ba  jbe     short loc_1800245C5
0x1800245bc  add     r9d, 0FFFFFFECh
0x1800245c0  jmp     loc_180024895
0x1800245c5  mov     r10, r15
0x1800245c8  add     r15, 8
0x1800245cc  mov     [rbp+3Fh+var_A0], r15
0x1800245d0  cmp     r15, r12
0x1800245d3  ja      short loc_1800245EC
0x1800245d5  mov     ecx, 14h
0x1800245da  mov     rax, rdx
0x1800245dd  sub     ecx, r9d
0x1800245e0  shr     rax, cl
0x1800245e3  add     rax, r8
0x1800245e6  bswap   rax
0x1800245e9  mov     [r10], rax
0x1800245ec  mov     [rbp+3Fh+var_90], r15
0x1800245f0  mov     r8, rdx
0x1800245f3  cmp     r9d, 14h
0x1800245f7  jz      loc_1800248D1
0x1800245fd  add     r9d, 2Ch ; ','
0x180024601  jmp     loc_1800248E3
0x180024606  cmp     eax, 0D6A0h
0x18002460b  jnb     short loc_180024663
0x18002460d  lea     edx, [rax+162960h]
0x180024613  cmp     r9d, 15h
0x180024617  jbe     short loc_180024622
0x180024619  add     r9d, 0FFFFFFEBh
0x18002461d  jmp     loc_180024895
0x180024622  mov     r10, r15
0x180024625  add     r15, 8
0x180024629  mov     [rbp+3Fh+var_A0], r15
0x18002462d  cmp     r15, r12
0x180024630  ja      short loc_180024649
0x180024632  mov     ecx, 15h
0x180024637  mov     rax, rdx
0x18002463a  sub     ecx, r9d
0x18002463d  shr     rax, cl
0x180024640  add     rax, r8
0x180024643  bswap   rax
0x180024646  mov     [r10], rax
0x180024649  mov     [rbp+3Fh+var_90], r15
0x18002464d  mov     r8, rdx
0x180024650  cmp     r9d, 15h
0x180024654  jz      loc_1800248D1
0x18002465a  add     r9d, 2Bh ; '+'
0x18002465e  jmp     loc_1800248E3
0x180024663  cmp     eax, 4D6A0h
0x180024668  jnb     short loc_1800246C0
0x18002466a  lea     edx, [rax+16F2960h]
0x180024670  cmp     r9d, 19h
0x180024674  jbe     short loc_18002467F
0x180024676  add     r9d, 0FFFFFFE7h
0x18002467a  jmp     loc_180024895
0x18002467f  mov     r10, r15
0x180024682  add     r15, 8
0x180024686  mov     [rbp+3Fh+var_A0], r15
0x18002468a  cmp     r15, r12
0x18002468d  ja      short loc_1800246A6
0x18002468f  mov     ecx, 19h
0x180024694  mov     rax, rdx
0x180024697  sub     ecx, r9d
0x18002469a  shr     rax, cl
0x18002469d  add     rax, r8
0x1800246a0  bswap   rax
0x1800246a3  mov     [r10], rax
0x1800246a6  mov     [rbp+3Fh+var_90], r15
0x1800246aa  mov     r8, rdx
0x1800246ad  cmp     r9d, 19h
0x1800246b1  jz      loc_1800248D1
0x1800246b7  add     r9d, 27h ; '''
0x1800246bb  jmp     loc_1800248E3
0x1800246c0  cmp     eax, 14D6A0h
0x1800246c5  jnb     short loc_18002471D
0x1800246c7  lea     edx, [rax+5CB2960h]
0x1800246cd  cmp     r9d, 1Bh
0x1800246d1  jbe     short loc_1800246DC
0x1800246d3  add     r9d, 0FFFFFFE5h
0x1800246d7  jmp     loc_180024895
0x1800246dc  mov     r10, r15
0x1800246df  add     r15, 8
0x1800246e3  mov     [rbp+3Fh+var_A0], r15
0x1800246e7  cmp     r15, r12
0x1800246ea  ja      short loc_180024703
0x1800246ec  mov     ecx, 1Bh
0x1800246f1  mov     rax, rdx
0x1800246f4  sub     ecx, r9d
0x1800246f7  shr     rax, cl
0x1800246fa  add     rax, r8
0x1800246fd  bswap   rax
0x180024700  mov     [r10], rax
0x180024703  mov     [rbp+3Fh+var_90], r15
0x180024707  mov     r8, rdx
0x18002470a  cmp     r9d, 1Bh
0x18002470e  jz      loc_1800248D1
0x180024714  add     r9d, 25h ; '%'
0x180024718  jmp     loc_1800248E3
0x18002471d  cmp     eax, 24D6A0h
0x180024722  jnb     short loc_18002477A
0x180024724  lea     edx, [rax+0BAB2960h]
0x18002472a  cmp     r9d, 1Ch
0x18002472e  jbe     short loc_180024739
0x180024730  add     r9d, 0FFFFFFE4h
0x180024734  jmp     loc_180024895
0x180024739  mov     r10, r15
0x18002473c  add     r15, 8
0x180024740  mov     [rbp+3Fh+var_A0], r15
0x180024744  cmp     r15, r12
0x180024747  ja      short loc_180024760
0x180024749  mov     ecx, 1Ch
0x18002474e  mov     rax, rdx
  ... truncated ...
```
