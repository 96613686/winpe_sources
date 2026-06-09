# LZ4HC_compress_generic

- ea: `0x1800edf40`
- end: `0x1800f088d`
- name: `LZ4HC_compress_generic`
- size: `10573`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180155444`

## callees

- `0x1800e62a8`
- `0x1800e6304`
- `0x1800edf40`
- `0x1800f0894`
- `0x180164280`

## pseudocode

```c
__int64 __fastcall LZ4HC_compress_generic(
        __int64 a1,
        char *a2,
        __int64 a3,
        unsigned int *a4,
        int a5,
        __int64 a6,
        int a7)
{
  __int64 v8; // r8
  unsigned int *v9; // r12
  char *v10; // r13
  __int64 v11; // rbx
  _DWORD *v12; // r14
  __int64 v13; // rdx
  char *v14; // r15
  char *v15; // r9
  unsigned __int64 v16; // rbp
  size_t v17; // r9
  size_t v18; // rdi
  unsigned __int64 v19; // rax
  __int64 result; // rax
  unsigned __int64 v21; // rcx
  __int64 v22; // rcx
  _QWORD *v23; // rbp
  unsigned int v24; // r15d
  __int64 v25; // r13
  unsigned int v26; // edi
  _QWORD *v27; // rdx
  unsigned int v28; // r8d
  int v29; // esi
  unsigned int v30; // r12d
  int v31; // r9d
  unsigned int v32; // r11d
  char *v33; // r8
  char *v34; // r9
  _QWORD *v35; // rdx
  signed int v38; // r10d
  __int64 v39; // r8
  __int64 v40; // rdx
  _QWORD *v41; // r8
  _QWORD *v42; // rdx
  unsigned int v45; // ecx
  int v46; // r9d
  __int16 v47; // r11
  unsigned __int64 v48; // r13
  unsigned __int64 v49; // rcx
  unsigned __int64 v50; // rdx
  unsigned __int64 v51; // rsi
  __int64 v52; // r14
  _DWORD *v53; // r10
  __int16 v54; // r8
  int v55; // r12d
  unsigned __int64 v56; // rdi
  __int64 v57; // r10
  __int16 v58; // bp
  int v59; // r15d
  __int64 v60; // r11
  unsigned __int64 v61; // r10
  int v62; // r10d
  int v63; // r11d
  _BYTE *v64; // rcx
  __int64 v65; // rdi
  unsigned __int64 v66; // r8
  unsigned int v67; // esi
  unsigned __int64 v68; // rax
  __int64 *v69; // rdx
  _WORD *v70; // r9
  __int64 v71; // rax
  __int64 v72; // rcx
  unsigned __int64 v73; // r8
  char v74; // al
  unsigned __int64 n; // rax
  _BYTE *v76; // r8
  unsigned __int64 v77; // r9
  unsigned __int64 v78; // rax
  __int64 *v79; // rdx
  _WORD *v80; // rbx
  __int64 v81; // rax
  __int16 v82; // r9
  unsigned __int64 v83; // r8
  char v84; // al
  unsigned __int64 ii; // rax
  int v86; // ecx
  __int16 v87; // r14
  _BYTE *v88; // rcx
  char *v89; // r9
  char *v90; // rbx
  unsigned __int64 v91; // r8
  unsigned __int64 v92; // rax
  __int64 *v93; // rdx
  _WORD *v94; // rbx
  __int64 v95; // rax
  unsigned __int64 v96; // rcx
  char v97; // al
  _BYTE *v98; // rcx
  unsigned __int64 v99; // r8
  char *v100; // r9
  unsigned __int64 v101; // rax
  __int64 *v102; // rdx
  _WORD *v103; // rbx
  __int64 v104; // rax
  __int16 v105; // r11
  unsigned __int64 v106; // rcx
  char v107; // al
  unsigned __int64 k; // rcx
  char *v109; // rcx
  _QWORD *v110; // rdx
  unsigned int v111; // ecx
  int v112; // ecx
  unsigned int v113; // eax
  unsigned int v114; // r14d
  int v115; // r15d
  _DWORD *v116; // rdi
  char *v117; // rbp
  unsigned __int64 v118; // rsi
  __int64 v119; // r9
  _QWORD *v120; // rdx
  unsigned int v121; // eax
  __int64 v122; // r8
  unsigned int v123; // r11d
  unsigned int v124; // eax
  unsigned int v125; // r11d
  unsigned __int64 v126; // rcx
  unsigned __int64 v127; // rdx
  unsigned int v128; // ecx
  __int64 v129; // rcx
  int v130; // eax
  int v131; // r11d
  char *v132; // rcx
  signed int v133; // ecx
  char *v136; // rcx
  char *v137; // r8
  int v144; // r8d
  int v145; // ecx
  int v146; // ecx
  _BYTE *v147; // rcx
  char *v148; // r9
  unsigned __int64 v149; // r8
  unsigned __int64 v150; // rax
  __int64 *v151; // rdx
  _WORD *v152; // rbx
  __int64 v153; // rax
  unsigned __int64 v154; // rcx
  char v155; // al
  unsigned __int64 kk; // rax
  char *v157; // rax
  _BYTE *v158; // rcx
  _BYTE *v159; // rbx
  unsigned int v160; // edx
  char *v161; // rdi
  _DWORD *v162; // r12
  _QWORD *v163; // r14
  unsigned int v164; // r15d
  unsigned int v165; // ebp
  char *v166; // r9
  unsigned int v167; // r8d
  unsigned int v168; // esi
  unsigned int v169; // r13d
  char *v170; // r10
  int v171; // r8d
  int v172; // ebp
  int v173; // eax
  _DWORD *v174; // r9
  int v175; // edx
  __int64 v176; // rax
  int v177; // r8d
  unsigned int v178; // eax
  char *v179; // r14
  _QWORD *v180; // r10
  _QWORD *v181; // rdx
  char *j; // rcx
  unsigned int v183; // ecx
  int v184; // ecx
  int v185; // ebp
  _DWORD *v186; // r12
  unsigned int v187; // edx
  unsigned int v188; // esi
  _QWORD *v189; // r14
  char *v190; // rdi
  unsigned int v191; // ebp
  char *v192; // r9
  unsigned int v193; // r8d
  unsigned int v194; // r11d
  unsigned int v195; // r13d
  unsigned __int64 v196; // r10
  int v197; // r15d
  int v198; // esi
  int v199; // eax
  int v200; // r8d
  int v201; // edx
  __int64 v202; // rax
  unsigned int v203; // eax
  _QWORD *v204; // rdx
  _QWORD *v205; // r10
  char *m; // rcx
  _BYTE *v207; // rbx
  int v208; // r10d
  unsigned __int64 v209; // r8
  unsigned __int64 v210; // r9
  _BYTE *v211; // rcx
  unsigned __int64 v212; // rax
  _WORD *v213; // rbx
  __int64 v214; // rax
  char v215; // cl
  unsigned __int64 mm; // rax
  _BYTE *v217; // rbx
  char *v218; // rbp
  char *v219; // rcx
  char *v220; // r9
  char *v221; // rdi
  _QWORD *v222; // rdx
  char *i; // rcx
  signed int v224; // esi
  int v225; // r10d
  char *v226; // r9
  unsigned __int64 v227; // r8
  _QWORD *v228; // rdx
  char *v229; // rcx
  char *v231; // rsi
  char *v232; // rcx
  char *v233; // r9
  _QWORD *v234; // rdx
  char *v235; // r11
  signed int v238; // edi
  unsigned __int64 jj; // rax
  _BYTE *v240; // rbx
  bool v241; // cf
  _BYTE *v242; // rbx
  unsigned int v243; // ecx
  int v244; // ecx
  __int64 v245; // r10
  int v246; // ebp
  unsigned int v247; // eax
  unsigned int v248; // r9d
  unsigned int v249; // r15d
  char *v250; // rsi
  __int64 v251; // r9
  unsigned __int64 v252; // r14
  char *v253; // r13
  unsigned int v254; // esi
  char *v255; // rdx
  unsigned int v256; // eax
  __int64 v257; // r8
  unsigned int v258; // r11d
  unsigned __int64 v259; // rcx
  unsigned __int64 v260; // rdx
  unsigned int v261; // ecx
  bool v262; // zf
  __int64 v263; // rcx
  int v264; // eax
  int v265; // r11d
  unsigned int v266; // ecx
  unsigned int v267; // ecx
  int v268; // edx
  int v269; // r8d
  unsigned int v270; // eax
  int v271; // r10d
  __int64 v272; // r9
  unsigned int v273; // r10d
  unsigned int v274; // r15d
  int v275; // r14d
  char *v276; // rsi
  unsigned __int64 v277; // rbp
  __int64 v278; // r9
  char *v279; // rdx
  unsigned int v280; // eax
  char *v281; // r8
  unsigned int v282; // esi
  unsigned __int64 v283; // rcx
  unsigned __int64 v284; // rdx
  unsigned int v285; // ecx
  __int64 v286; // r8
  __int64 v287; // rcx
  char *v293; // rcx
  int v294; // r10d
  unsigned __int64 v295; // r8
  _QWORD *v296; // rdx
  char *v297; // rcx
  unsigned int v298; // ecx
  int v299; // edx
  int v300; // r8d
  unsigned int v301; // eax
  int v302; // r10d
  __int64 v319; // r8
  __int64 v320; // rcx
  __int64 v321; // r8
  __int64 v322; // rcx
  __int64 v323; // r8
  __int64 v324; // rcx
  unsigned __int64 v325; // rdx
  unsigned __int64 v326; // rcx
  unsigned __int64 v327; // rdx
  unsigned __int64 v328; // rcx
  unsigned __int64 v329; // rdx
  unsigned __int64 v330; // rcx
  __int64 v331; // [rsp+28h] [rbp-130h]
  int v332; // [rsp+40h] [rbp-118h]
  int v333; // [rsp+40h] [rbp-118h]
  unsigned int v334; // [rsp+44h] [rbp-114h]
  unsigned int v335; // [rsp+44h] [rbp-114h]
  unsigned int v336; // [rsp+44h] [rbp-114h]
  unsigned int v337; // [rsp+48h] [rbp-110h]
  int v338; // [rsp+4Ch] [rbp-10Ch]
  unsigned int v339; // [rsp+4Ch] [rbp-10Ch]
  unsigned int v340; // [rsp+4Ch] [rbp-10Ch]
  unsigned int v341; // [rsp+50h] [rbp-108h]
  unsigned int v342; // [rsp+50h] [rbp-108h]
  unsigned int v343; // [rsp+54h] [rbp-104h]
  int v344; // [rsp+54h] [rbp-104h]
  char *v345; // [rsp+58h] [rbp-100h]
  int v346; // [rsp+60h] [rbp-F8h]
  __int16 v347; // [rsp+64h] [rbp-F4h]
  int v348; // [rsp+68h] [rbp-F0h]
  int v349; // [rsp+68h] [rbp-F0h]
  __int16 v350; // [rsp+68h] [rbp-F0h]
  _QWORD *v351; // [rsp+70h] [rbp-E8h]
  char *v352; // [rsp+70h] [rbp-E8h]
  char *v353; // [rsp+70h] [rbp-E8h]
  unsigned __int64 v354; // [rsp+78h] [rbp-E0h]
  unsigned int v355; // [rsp+80h] [rbp-D8h]
  int v356; // [rsp+80h] [rbp-D8h]
  __int16 v357; // [rsp+80h] [rbp-D8h]
  int v358; // [rsp+8Ch] [rbp-CCh]
  _DWORD *v359; // [rsp+90h] [rbp-C8h]
  unsigned __int64 v360; // [rsp+98h] [rbp-C0h]
  __int16 v361; // [rsp+98h] [rbp-C0h]
  _QWORD *v362; // [rsp+A0h] [rbp-B8h]
  char *v363; // [rsp+A0h] [rbp-B8h]
  __int64 v364; // [rsp+A8h] [rbp-B0h]
  char *v365; // [rsp+A8h] [rbp-B0h]
  char *v366; // [rsp+A8h] [rbp-B0h]
  char *v367; // [rsp+B0h] [rbp-A8h]
  unsigned __int64 v368; // [rsp+B8h] [rbp-A0h]
  char *v369; // [rsp+C0h] [rbp-98h]
  unsigned __int64 v370; // [rsp+C0h] [rbp-98h]
  unsigned int v371; // [rsp+C0h] [rbp-98h]
  unsigned int v372; // [rsp+C8h] [rbp-90h]
  int v373; // [rsp+C8h] [rbp-90h]
  unsigned __int64 v374; // [rsp+D0h] [rbp-88h]
  unsigned __int64 v375; // [rsp+D8h] [rbp-80h]
  __int64 v376; // [rsp+E0h] [rbp-78h]
  _DWORD *v377; // [rsp+E0h] [rbp-78h]
  int v378; // [rsp+E8h] [rbp-70h]
  char *v379; // [rsp+E8h] [rbp-70h]
  unsigned __int64 v380; // [rsp+F0h] [rbp-68h]
  unsigned __int64 v381; // [rsp+F0h] [rbp-68h]
  _DWORD *v382; // [rsp+F8h] [rbp-60h]
  __int64 v383; // [rsp+F8h] [rbp-60h]
  char *v384; // [rsp+108h] [rbp-50h]
  int v386; // [rsp+168h] [rbp+10h]
  int v387; // [rsp+170h] [rbp+18h]
  int v389; // [rsp+188h] [rbp+30h]

  v387 = a3;
  v386 = (int)a2;
  v8 = a1;
  v9 = a4;
  v10 = a2;
  if ( *(_QWORD *)(a1 + 262184) )
    return LZ4HC_compress_generic_dictCtx(a1, a2, a3, a4, a5, v331, a7);
  if ( a7 == 2 && a5 < 1 || *a4 > 0x7E000000 )
    return 0;
  v11 = a3;
  *(_QWORD *)(a1 + 0x40000) += (int)*a4;
  v12 = a2;
  v13 = (int)*a4;
  v14 = v10;
  v359 = v10;
  v15 = &v10[v13];
  v367 = v10;
  v384 = &v10[v13];
  v16 = a3 + a5 - 5;
  v364 = a3;
  if ( a7 != 2 )
    v16 = a3 + a5;
  v358 = HIDWORD(a3);
  v368 = v16;
  *v9 = 0;
  if ( (int)v13 < 13 )
  {
LABEL_7:
    v17 = v15 - v14;
    v18 = v17;
    if ( a7 == 2 )
      goto LABEL_38;
    if ( a7 )
      goto LABEL_39;
    goto LABEL_9;
  }
  v345 = v15 - 5;
  v21 = (unsigned __int64)(v15 - 12);
  v375 = (unsigned __int64)(v15 - 12);
  v374 = 0;
  v354 = 0;
LABEL_19:
  while ( 2 )
  {
    if ( (unsigned __int64)v12 > v21 )
    {
      v15 = v384;
      v9 = a4;
      LODWORD(v10) = v386;
      goto LABEL_7;
    }
    v22 = *(unsigned int *)(v8 + 262172);
    v23 = *(_QWORD **)(v8 + 262152);
    v24 = v22;
    v25 = *(unsigned int *)(v8 + 262168);
    v26 = v25 + (_DWORD)v12 - (_DWORD)v23;
    v389 = 3;
    v362 = v23;
    v355 = v26;
    v372 = *(_DWORD *)(v8 + 262172);
    if ( (int)v22 + 0x10000 <= v26 )
      v24 = v26 - 0xFFFF;
    v27 = *(_QWORD **)(v8 + 262160);
    v28 = *(_DWORD *)(v8 + 262176);
    v29 = 0;
    v30 = *v12;
    v334 = v24;
    v351 = v27;
    v369 = (char *)v27 + v25 - v22;
    v360 = 0;
    v31 = 256;
    v348 = 256;
    v337 = 0;
    if ( v28 < v26 )
    {
      do
      {
        v325 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v23 + v28 - v25)) >> 17;
        v326 = v28 - *(_DWORD *)(a1 + 4 * v325);
        if ( v326 > 0xFFFF )
          LOWORD(v326) = -1;
        *(_WORD *)(a1 + 2LL * (unsigned __int16)v28 + 0x20000) = v326;
        *(_DWORD *)(a1 + 4 * v325) = v28++;
      }
      while ( v28 < v26 );
      v27 = v351;
      v31 = 256;
    }
    v8 = a1;
    *(_DWORD *)(a1 + 262176) = v26;
    v32 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)(unsigned int)(-1640531535 * *v12) >> 17));
    if ( v32 >= v24 )
    {
      while ( 1 )
      {
        if ( v31 <= 0 )
        {
LABEL_44:
          v11 = v364;
          break;
        }
        if ( v32 >= (unsigned int)v25 )
        {
          v39 = v32 - (unsigned int)v25;
          if ( *(_WORD *)((char *)v12 + v389 - 1) == *(_WORD *)((char *)v23 + v389 + v39 - 1)
            && *(_DWORD *)((char *)v23 + v39) == v30 )
          {
            v40 = v39 + 4;
            v41 = v12 + 1;
            v42 = (_QWORD *)((char *)v23 + v40);
            if ( v12 + 1 >= (_DWORD *)(v345 - 7) )
            {
              v132 = (char *)(v12 + 1);
              while ( v132 < v345 - 7 )
              {
                if ( *(_QWORD *)v132 != *v42 )
                {
                  __asm { tzcnt   rax, rax }
                  v45 = ((unsigned int)_RAX >> 3) - (_DWORD)v41 + (_DWORD)v132;
                  goto LABEL_188;
                }
                v132 += 8;
LABEL_176:
                ++v42;
              }
              if ( v132 < v345 - 3 && *(_DWORD *)v42 == *(_DWORD *)v132 )
              {
                v132 += 4;
                v42 = (_QWORD *)((char *)v42 + 4);
              }
              if ( v132 < v345 - 1 && *(_WORD *)v42 == *(_WORD *)v132 )
              {
                v132 += 2;
                v42 = (_QWORD *)((char *)v42 + 2);
              }
              if ( v132 < v345 && *(_BYTE *)v42 == *v132 )
                LODWORD(v132) = (_DWORD)v132 + 1;
              v45 = (_DWORD)v132 - (_DWORD)v41;
            }
            else
            {
              if ( *v41 == *v42 )
              {
                v132 = (char *)(v12 + 3);
                goto LABEL_176;
              }
              __asm { tzcnt   rcx, rax }
              v45 = (unsigned int)_RCX >> 3;
            }
LABEL_188:
            v8 = a1;
            v133 = v45 + 4;
            if ( v133 > v389 )
            {
              v389 = v133;
              v337 = v26 - v32;
            }
          }
          else
          {
            v8 = a1;
          }
        }
        else if ( v32 <= (int)v25 - 4 && *(_DWORD *)((char *)v27 + v32 - v372) == v30 )
        {
          v33 = (char *)(v12 + 1);
          v34 = (char *)v12 + (unsigned int)v25 - v32;
          if ( v34 > v345 )
            v34 = v345;
          v35 = (_QWORD *)((char *)v27 + v32 - v372 + 4);
          if ( v33 >= v34 - 7 )
          {
            v136 = (char *)(v12 + 1);
            while ( v136 < v34 - 7 )
            {
              if ( *v35 != *(_QWORD *)v136 )
              {
                __asm { tzcnt   r10, rax }
                v38 = (_DWORD)v136 + ((unsigned int)_R10 >> 3) - (_DWORD)v33;
                goto LABEL_206;
              }
              v136 += 8;
LABEL_194:
              ++v35;
            }
            if ( v136 < v34 - 3 && *(_DWORD *)v35 == *(_DWORD *)v136 )
            {
              v136 += 4;
              v35 = (_QWORD *)((char *)v35 + 4);
            }
            if ( v136 < v34 - 1 && *(_WORD *)v35 == *(_WORD *)v136 )
            {
              v136 += 2;
              v35 = (_QWORD *)((char *)v35 + 2);
            }
            if ( v136 < v34 && *(_BYTE *)v35 == *v136 )
              LODWORD(v136) = (_DWORD)v136 + 1;
            v38 = (_DWORD)v136 - (_DWORD)v33;
          }
          else
          {
            if ( *(_QWORD *)v33 == *v35 )
            {
              v136 = (char *)(v12 + 3);
              goto LABEL_194;
            }
            __asm { tzcnt   r10, rax }
            v38 = (unsigned int)_R10 >> 3;
          }
LABEL_206:
          v112 = v38 + 4;
          v137 = (char *)v12 + v38 + 4;
          if ( v137 == v34 && v34 < v345 )
          {
            if ( v137 >= v345 - 7 )
            {
              v110 = v23;
              v109 = (char *)v12 + v38 + 4;
              goto LABEL_210;
            }
            if ( *v23 != *(_QWORD *)v137 )
            {
              __asm { tzcnt   rcx, rax }
              v111 = (unsigned int)_RCX >> 3;
            }
            else
            {
              v109 = v137 + 8;
              v110 = v23 + 1;
LABEL_210:
              while ( v109 < v345 - 7 )
              {
                if ( *v110 != *(_QWORD *)v109 )
                {
                  __asm { tzcnt   rax, rax }
                  v111 = ((unsigned int)_RAX >> 3) - (_DWORD)v137 + (_DWORD)v109;
                  goto LABEL_132;
                }
                v109 += 8;
                ++v110;
              }
              if ( v109 < v345 - 3 && *(_DWORD *)v110 == *(_DWORD *)v109 )
              {
                v109 += 4;
                v110 = (_QWORD *)((char *)v110 + 4);
              }
              if ( v109 < v345 - 1 && *(_WORD *)v110 == *(_WORD *)v109 )
              {
                v109 += 2;
                v110 = (_QWORD *)((char *)v110 + 2);
              }
              if ( v109 < v345 && *(_BYTE *)v110 == *v109 )
                LODWORD(v109) = (_DWORD)v109 + 1;
              v111 = (_DWORD)v109 - (_DWORD)v137;
            }
LABEL_132:
            v112 = v38 + v111 + 4;
          }
          v8 = a1;
          if ( v112 > v389 )
          {
            v389 = v112;
            v337 = v26 - v32;
          }
        }
        if ( *(_WORD *)(v8 + 2LL * (unsigned __int16)v32 + 0x20000) != 1 )
          goto LABEL_42;
        if ( v29 )
        {
          v338 = v29;
          if ( v29 != 2 )
            goto LABEL_42;
        }
        else
        {
          if ( (_BYTE)v30 != HIBYTE(v30) || (unsigned __int16)v30 != HIWORD(v30) )
          {
            v8 = a1;
            v29 = 1;
LABEL_42:
            v32 -= *(unsigned __int16 *)(v8 + 2LL * (unsigned __int16)v32 + 0x20000);
            goto LABEL_43;
          }
          v29 = 2;
          v338 = 2;
          v113 = LZ4HC_countPattern(v12 + 1, v345, v30, 1);
          v8 = a1;
          v360 = v113 + 4LL;
        }
        v114 = v32 - 1;
        if ( v32 - 1 < v24 || (unsigned int)v25 - v32 < 3 )
          goto LABEL_42;
        if ( v114 < (unsigned int)v25 )
        {
          v115 = 1;
          v116 = (_DWORD *)((char *)v351 + v114 - v372);
        }
        else
        {
          v115 = 0;
          v116 = (_DWORD *)((char *)v23 + v114 - (unsigned int)v25);
        }
        if ( *v116 != v30 )
        {
          v24 = v334;
          goto LABEL_42;
        }
        v117 = v345;
        if ( v115 )
          v117 = v369;
        v118 = (unsigned int)LZ4HC_countPattern(v116 + 1, v117, v30, 1) + 4LL;
        if ( v115 )
        {
          if ( (char *)v116 + v118 == v117 )
          {
            v319 = v30;
            v320 = 8 * (v118 & 3);
            if ( v320 )
              v319 = (unsigned int)__ROL4__(v30, v320);
            v23 = v362;
            v118 += (unsigned int)LZ4HC_countPattern(v362, v345, v319, v119);
          }
          else
          {
            v23 = v362;
          }
          v120 = v351;
        }
        else
        {
          v23 = v362;
          v120 = v362;
        }
        v121 = LZ4HC_reverseCountPattern(v116, v120, v30);
        v123 = v121;
        if ( !v115 && (_QWORD *)((char *)v116 - v121) == v23 && v372 < (unsigned int)v25 )
        {
          v129 = 8LL * (-v121 & 3);
          if ( v129 )
            v122 = (unsigned int)__ROL4__(v122, v129);
          v130 = LZ4HC_reverseCountPattern(v369, v351, v122);
          v123 = v130 + v131;
        }
        v24 = v334;
        v124 = v114 - v123;
        v125 = v334;
        if ( v124 > v334 )
          v125 = v124;
        v126 = v118 + v114 - v125;
        if ( v126 >= v360 && v118 <= v360 )
        {
          v32 = v25;
          if ( (unsigned int)v25 - ((_DWORD)v118 - (_DWORD)v360 + v114) - 1 >= 3 )
            v32 = v118 - v360 + v114;
          goto LABEL_155;
        }
        if ( (unsigned int)v25 - v125 - 1 < 3 )
        {
          v32 = v25;
LABEL_155:
          v29 = v338;
          v8 = a1;
          goto LABEL_43;
        }
        v12 = v359;
        v127 = v360;
        if ( v126 < v360 )
          v127 = v126;
        if ( v389 < v127 )
        {
          if ( (unsigned __int64)v359 + v25 - v125 - (_QWORD)v23 > 0xFFFF )
          {
            v8 = a1;
            goto LABEL_44;
          }
          v389 = v127;
          v337 = v355 - v125;
        }
        v8 = a1;
        v128 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v125 + 0x20000);
        if ( v128 > v125 )
          goto LABEL_44;
        v29 = v338;
        v32 = v125 - v128;
LABEL_43:
        v26 = v355;
        v31 = v348 - 1;
        v27 = v351;
        v12 = v359;
        --v348;
        if ( v32 < v24 )
          goto LABEL_44;
      }
    }
    v46 = v389;
    if ( v389 < 4 )
    {
      v14 = v367;
      v12 = (_DWORD *)((char *)v12 + 1);
      v16 = v368;
      v359 = v12;
LABEL_121:
      v21 = v375;
      continue;
    }
    break;
  }
  v47 = v337;
  v48 = (unsigned __int64)v359;
  v49 = __PAIR64__(v389, v337) >> 32;
  v50 = (unsigned __int64)v359;
  while ( 1 )
  {
    v51 = v375;
    v378 = v49;
    v380 = v50;
    while ( 1 )
    {
      v52 = v46;
      v376 = v46;
      v53 = (_DWORD *)(v46 + v48);
      v382 = v53;
      if ( (unsigned __int64)v53 > v51 )
      {
        v54 = 0;
        v55 = 0;
        v347 = 0;
        v346 = 0;
        goto LABEL_50;
      }
      v160 = *(_DWORD *)(v8 + 262172);
      v161 = (char *)*(unsigned int *)(v8 + 262168);
      v162 = (_DWORD *)((char *)v53 - 2);
      v163 = *(_QWORD **)(v8 + 262152);
      v354 = (unsigned __int64)v53 - 2;
      v164 = (_DWORD)v53 - 2 + *(_DWORD *)(v8 + 262168) - (_DWORD)v163;
      v346 = v46;
      v352 = (char *)v163;
      v341 = *(_DWORD *)(v8 + 262168);
      v165 = v160;
      v361 = (_WORD)v53 - 2 + *(_WORD *)(v8 + 262168) - (_WORD)v163;
      v343 = v160;
      if ( v160 + 0x10000 <= v164 )
        v165 = v164 - 0xFFFF;
      v166 = *(char **)(v8 + 262160);
      v167 = *(_DWORD *)(v8 + 262176);
      v168 = *v162;
      v335 = v165;
      v363 = v166;
      v339 = *v162;
      v347 = 0;
      if ( v167 < v164 )
      {
        do
        {
          v327 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v163 + v167 - (_QWORD)v161)) >> 17;
          v328 = v167 - *(_DWORD *)(a1 + 4 * v327);
          if ( v328 > 0xFFFF )
            LOWORD(v328) = -1;
          *(_WORD *)(a1 + 2LL * (unsigned __int16)v167 + 0x20000) = v328;
          *(_DWORD *)(a1 + 4 * v327) = v167++;
        }
        while ( v167 < v164 );
        v168 = v339;
        v160 = v343;
      }
      *(_DWORD *)(a1 + 262176) = v164;
      v169 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)(unsigned int)(-1640531535 * *v162) >> 17));
      if ( v169 >= v165 )
      {
        v170 = (char *)v359;
        v171 = (_DWORD)v162 - (_DWORD)v359;
        v365 = &v161[(_QWORD)v166 - v160];
        v172 = 0;
        v349 = (_DWORD)v162 - (_DWORD)v359;
        v173 = 256;
        v332 = 0;
        v356 = 256;
        v370 = 0;
        do
        {
          if ( v173 <= 0 )
            break;
          if ( v169 < (unsigned int)v161 )
          {
            if ( v169 > (int)v161 - 4 )
              goto LABEL_648;
            v218 = &v166[v169 - v160];
            if ( *(_DWORD *)v218 != v168 )
            {
              v172 = v332;
LABEL_648:
              v179 = v345;
              goto LABEL_485;
            }
            v219 = v345;
            v220 = (char *)(v162 + 1);
            v221 = (char *)v162 + (unsigned int)v161 - v169;
            v222 = v218 + 4;
            if ( v221 > v345 )
              v221 = v345;
            if ( v220 >= v221 - 7 )
            {
              i = (char *)(v162 + 1);
              goto LABEL_346;
            }
            if ( *(_QWORD *)v220 != *v222 )
            {
              __asm { tzcnt   rsi, rax }
              v224 = (unsigned int)_RSI >> 3;
            }
            else
            {
              for ( i = (char *)(v162 + 3); ; i += 8 )
              {
                ++v222;
LABEL_346:
                if ( i >= v221 - 7 )
                  break;
                if ( *v222 != *(_QWORD *)i )
                {
                  __asm { tzcnt   rsi, rax }
                  v224 = (_DWORD)i + ((unsigned int)_RSI >> 3) - (_DWORD)v220;
                  goto LABEL_357;
                }
              }
              if ( i < v221 - 3 && *(_DWORD *)v222 == *(_DWORD *)i )
              {
                i += 4;
                v222 = (_QWORD *)((char *)v222 + 4);
              }
              if ( i < v221 - 1 && *(_WORD *)v222 == *(_WORD *)i )
              {
                i += 2;
                v222 = (_QWORD *)((char *)v222 + 2);
              }
              if ( i < v221 && *(_BYTE *)v222 == *i )
                LODWORD(i) = (_DWORD)i + 1;
              v224 = (_DWORD)i - (_DWORD)v220;
LABEL_357:
              v219 = v345;
            }
            v225 = v224 + 4;
            v226 = (char *)v162 + v224 + 4;
            if ( v226 == v221 && v221 < v219 )
            {
              v227 = (unsigned __int64)(v219 - 7);
              if ( v226 >= v219 - 7 )
              {
                v228 = v163;
                v229 = (char *)v162 + v224 + 4;
                goto LABEL_362;
              }
              if ( *v163 != *(_QWORD *)v226 )
              {
                __asm { tzcnt   rcx, rax }
                v267 = (unsigned int)_RCX >> 3;
              }
              else
              {
                v229 = v226 + 8;
                v228 = v163 + 1;
LABEL_362:
                while ( (unsigned __int64)v229 < v227 )
                {
                  if ( *v228 != *(_QWORD *)v229 )
                  {
                    __asm { tzcnt   rax, rax }
                    v267 = ((unsigned int)_RAX >> 3) - (_DWORD)v226 + (_DWORD)v229;
                    goto LABEL_476;
                  }
                  v229 += 8;
                  ++v228;
                }
                if ( v229 < v345 - 3 && *(_DWORD *)v228 == *(_DWORD *)v229 )
                {
                  v229 += 4;
                  v228 = (_QWORD *)((char *)v228 + 4);
                }
                if ( v229 < v345 - 1 && *(_WORD *)v228 == *(_WORD *)v229 )
                {
                  v229 += 2;
                  v228 = (_QWORD *)((char *)v228 + 2);
                }
                if ( v229 < v345 && *(_BYTE *)v228 == *v229 )
                  LODWORD(v229) = (_DWORD)v229 + 1;
                v267 = (_DWORD)v229 - (_DWORD)v226;
              }
LABEL_476:
              v225 = v224 + v267 + 4;
            }
            v268 = 0;
            if ( v349 )
            {
              v269 = (_DWORD)v359 - (_DWORD)v162;
              if ( (char *)v359 - (char *)v162 <= v363 - v218 )
                v269 = (_DWORD)v363 - (_DWORD)v218;
              while ( v268 - v269 > 3 )
              {
                if ( *(_DWORD *)((char *)v162 + v268 - 4) != *(_DWORD *)&v218[v268 - 4] )
                {
                  _BitScanReverse(&v270, *(_DWORD *)((char *)v162 + v268 - 4) ^ *(_DWORD *)&v218[v268 - 4]);
                  v268 -= (31 - v270) >> 3;
                  goto LABEL_483;
                }
                v268 -= 4;
              }
              if ( v268 > v269 )
              {
                do
                {
                  if ( *((_BYTE *)v162 + v268 - 1) != v218[v268 - 1] )
                    break;
                  --v268;
                }
                while ( v268 > v269 );
                LOWORD(v164) = v361;
              }
            }
LABEL_483:
            LODWORD(v161) = v341;
            v271 = v225 - v268;
            v168 = v339;
            v172 = v332;
            v179 = v345;
            if ( v271 > v346 )
            {
              v346 = v271;
              v347 = v164 - v169;
              v354 = (unsigned __int64)v162 + v268;
            }
          }
          else
          {
            v174 = (_DWORD *)((char *)v163 + v169 - (unsigned int)v161);
            if ( *(_WORD *)&v170[v346 - 1] == *(_WORD *)((char *)v174 + v346 - (__int64)v171 - 1) && *v174 == v168 )
            {
              if ( v171 )
              {
                v175 = (_DWORD)v170 - (_DWORD)v162;
                v176 = -(__int64)(v169 - (unsigned int)v161);
                v177 = 0;
                if ( v170 - (char *)v162 <= v176 )
                  v175 = v176;
                while ( v177 - v175 > 3 )
                {
                  if ( *(_DWORD *)((char *)v174 + v177 - 4) != *(_DWORD *)((char *)v162 + v177 - 4) )
                  {
                    _BitScanReverse(&v178, *(_DWORD *)((char *)v174 + v177 - 4) ^ *(_DWORD *)((char *)v162 + v177 - 4));
                    v177 -= (31 - v178) >> 3;
                    goto LABEL_271;
                  }
                  v177 -= 4;
                }
                if ( v177 > v175 )
                {
                  do
                  {
                    if ( *((_BYTE *)v162 + v177 - 1) != *((_BYTE *)v174 + v177 - 1) )
                      break;
                    --v177;
                  }
                  while ( v177 > v175 );
                  LOWORD(v164) = v361;
                }
              }
              else
              {
                v177 = 0;
              }
LABEL_271:
              v179 = v345;
              v180 = v162 + 1;
              v181 = v174 + 1;
              if ( v162 + 1 >= (_DWORD *)(v345 - 7) )
              {
                j = (char *)(v162 + 1);
                goto LABEL_273;
              }
              if ( *v180 != *v181 )
              {
                __asm { tzcnt   rcx, rax }
                v183 = (unsigned int)_RCX >> 3;
              }
              else
              {
                for ( j = (char *)(v162 + 3); ; j += 8 )
                {
                  ++v181;
LABEL_273:
                  if ( j >= v345 - 7 )
                    break;
                  if ( *v181 != *(_QWORD *)j )
                  {
                    __asm { tzcnt   rax, rax }
                    v183 = ((unsigned int)_RAX >> 3) - (_DWORD)v180 + (_DWORD)j;
                    goto LABEL_284;
                  }
                }
                if ( j < v345 - 3 && *(_DWORD *)v181 == *(_DWORD *)j )
                {
                  j += 4;
                  v181 = (_QWORD *)((char *)v181 + 4);
                }
                if ( j < v345 - 1 && *(_WORD *)v181 == *(_WORD *)j )
                {
                  j += 2;
                  v181 = (_QWORD *)((char *)v181 + 2);
                }
                if ( j < v345 && *(_BYTE *)v181 == *j )
                  LODWORD(j) = (_DWORD)j + 1;
                v183 = (_DWORD)j - (_DWORD)v180;
              }
LABEL_284:
              v184 = v183 - v177 + 4;
              if ( v184 > v346 )
              {
                v346 = v184;
                v347 = v164 - v169;
                v354 = (unsigned __int64)v162 + v177;
              }
            }
            else
            {
              v179 = v345;
            }
          }
LABEL_485:
          v272 = a1;
          if ( *(_WORD *)(a1 + 2LL * (unsigned __int16)v169 + 0x20000) != 1 )
            goto LABEL_489;
          if ( v172 )
          {
            v332 = v172;
            if ( v172 != 2 )
              goto LABEL_489;
          }
          else
          {
            if ( (_BYTE)v168 != HIBYTE(v168) || (unsigned __int16)v168 != HIWORD(v168) )
            {
              v172 = 1;
              v332 = 1;
LABEL_489:
              v273 = v335;
LABEL_490:
              LODWORD(v161) = v341;
              v169 -= *(unsigned __int16 *)(v272 + 2LL * (unsigned __int16)v169 + 0x20000);
              goto LABEL_389;
            }
            v172 = 2;
            v332 = 2;
            v370 = (unsigned int)LZ4HC_countPattern(v162 + 1, v179, v168, a1) + 4LL;
            v272 = a1;
          }
          v273 = v335;
          v274 = v169 - 1;
          if ( v169 - 1 < v335 || (unsigned int)v161 - v169 < 3 )
            goto LABEL_490;
          if ( v274 < (unsigned int)v161 )
          {
            v275 = 1;
            v161 = &v363[v274 - v343];
          }
          else
          {
            v275 = 0;
            v161 = &v352[v274 - (unsigned int)v161];
          }
          if ( *(_DWORD *)v161 != v168 )
            goto LABEL_490;
          v276 = v345;
          if ( v275 )
            v276 = v365;
          v277 = (unsigned int)LZ4HC_countPattern(v161 + 4, v276, v339, v272) + 4LL;
          if ( v275 )
          {
            if ( &v161[v277] == v276 )
            {
              v321 = v339;
              v322 = 8 * (v277 & 3);
              if ( v322 )
                v321 = (unsigned int)__ROL4__(v339, v322);
              v277 += (unsigned int)LZ4HC_countPattern(v352, v345, v321, v278);
            }
            v279 = v363;
          }
          else
          {
            v279 = v352;
          }
          v280 = LZ4HC_reverseCountPattern(v161, v279, v339);
          v281 = v352;
          v282 = v280;
          if ( v275 )
          {
            LODWORD(v161) = v341;
          }
          else
          {
            v262 = &v161[-v280] == v352;
            LODWORD(v161) = v341;
            if ( v262 && v343 < v341 )
            {
              v286 = v339;
              v287 = 8LL * (-v280 & 3);
              if ( v287 )
                v286 = (unsigned int)__ROL4__(v339, v287);
              v282 = LZ4HC_reverseCountPattern(v365, v363, v286) + v280;
              v281 = v352;
            }
          }
          v273 = v335;
          v169 = v335;
          if ( v274 - v282 > v335 )
            v169 = v274 - v282;
          v283 = v277 + v274 - v169;
          if ( v283 < v370 || v277 > v370 )
          {
            if ( (unsigned int)v161 - v169 - 1 < 3 )
            {
              v169 = (unsigned int)v161;
            }
            else if ( !v349 )
            {
              v284 = v370;
              if ( v283 < v370 )
                v284 = v277 + v274 - v169;
              if ( v346 < v284 )
              {
                if ( (unsigned __int64)v162 + (unsigned int)v161 - (unsigned __int64)v169 - (_QWORD)v281 > 0xFFFF )
                  break;
                v346 = v284;
                v347 = v361 - v169;
                v354 = (unsigned __int64)v162;
              }
              v285 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v169 + 0x20000);
              if ( v285 > v169 )
                break;
              v169 -= v285;
            }
          }
          else
          {
            v169 = (unsigned int)v161;
            if ( (unsigned int)v161 - (v274 + (_DWORD)v277 - (_DWORD)v370) - 1 >= 3 )
              v169 = v274 + v277 - v370;
          }
          v172 = v332;
LABEL_389:
          v168 = v339;
          v173 = v356 - 1;
          v163 = v352;
          v241 = v169 < v273;
          v170 = (char *)v359;
          LOWORD(v164) = v361;
          v171 = (_DWORD)v162 - (_DWORD)v359;
          v160 = v343;
          v166 = v363;
          --v356;
        }
        while ( !v241 );
      }
      LODWORD(v49) = v378;
      v50 = v380;
      v53 = v382;
      v52 = v376;
      v55 = v346;
      v48 = (unsigned __int64)v359;
      v46 = v389;
      v54 = v347;
      v51 = v375;
LABEL_50:
      if ( v55 <= v46 )
      {
        v14 = v367;
        v98 = (_BYTE *)(v11 + 1);
        v16 = v368;
        v65 = v11 >> 32;
        v99 = v48 - (_QWORD)v367;
        v67 = v11;
        v100 = (char *)v11;
        if ( a7 && (unsigned __int64)&v98[v99 / 0xFF + 8 + v99] > v368 )
          goto LABEL_315;
        if ( v99 < 0xF )
        {
          *(_BYTE *)v11 = 16 * v99;
        }
        else
        {
          v101 = v99 - 15;
          *(_BYTE *)v11 = -16;
          while ( v101 >= 0xFF )
          {
            *v98++ = -1;
            v101 -= 255LL;
          }
          *v98++ = v101;
        }
        v102 = (__int64 *)v367;
        v103 = &v98[v99];
        do
        {
          v104 = *v102++;
          *(_QWORD *)v98 = v104;
          v98 += 8;
        }
        while ( v98 < (_BYTE *)v103 );
        v105 = v337;
        v106 = v52 - 4;
        *v103 = v337;
        v11 = (__int64)(v103 + 1);
        v364 = v11;
        v358 = HIDWORD(v11);
        if ( a7 && v11 + v106 / 0xFF + 6 > v368 )
          goto LABEL_316;
        v107 = *v100;
        if ( v106 < 0xF )
        {
          *v100 = v107 + v106;
        }
        else
        {
          *v100 = v107 + 15;
          for ( k = v52 - 19; k >= 0x1FE; k -= 510LL )
          {
            *(_BYTE *)v11 = -1;
            v217 = (_BYTE *)(v11 + 1);
            *v217 = -1;
            v11 = (__int64)(v217 + 1);
          }
          if ( k >= 0xFF )
          {
            LOBYTE(k) = k + 1;
            *(_BYTE *)v11++ = -1;
          }
          *(_BYTE *)v11++ = k;
          v364 = v11;
          v358 = HIDWORD(v11);
        }
        v8 = a1;
        v12 = v53;
        v359 = v53;
        v14 = (char *)v53;
        v367 = (char *)v53;
        goto LABEL_121;
      }
      v56 = v354;
      if ( v50 < v48 && v354 < v48 + (int)v49 )
      {
        v48 = v50;
        v359 = (_DWORD *)v50;
        LOWORD(v337) = v47;
        v46 = v49;
        v389 = v49;
      }
      if ( (__int64)(v354 - v48) >= 3 )
        break;
      LOWORD(v337) = v54;
      v48 = v354;
      v8 = a1;
      v46 = v55;
      v359 = (_DWORD *)v354;
      v389 = v55;
    }
LABEL_53:
    if ( (__int64)(v56 - v48) < 18 )
    {
      v144 = v46;
      if ( v46 > 18 )
        v144 = 18;
      if ( v48 + v144 > v56 + v55 - 4LL )
        v144 = v55 + v56 - v48 - 4;
      v145 = v144 + v48 - v56;
      if ( v145 > 0 )
      {
        v56 += v145;
        v55 -= v145;
        v354 = v56;
        v346 = v55;
      }
    }
    v57 = v55;
    v383 = v55;
    v12 = (_DWORD *)(v55 + v56);
    v377 = v12;
    if ( (unsigned __int64)v12 > v51 )
    {
      v58 = 0;
      v59 = 0;
      goto LABEL_56;
    }
    v185 = (_DWORD)v12 - 3;
    v333 = v55;
    v59 = v55;
    v374 = (unsigned __int64)v12 - 3;
    v186 = (_DWORD *)((char *)v12 - 3);
    v187 = *(_DWORD *)(a1 + 262172);
    v188 = v187;
    v189 = *(_QWORD **)(a1 + 262152);
    v190 = (char *)*(unsigned int *)(a1 + 262168);
    v191 = (_DWORD)v190 + v185 - (_DWORD)v189;
    v353 = (char *)v189;
    v336 = *(_DWORD *)(a1 + 262168);
    v357 = v191;
    v371 = v187;
    if ( v187 + 0x10000 <= v191 )
      v188 = v191 - 0xFFFF;
    v192 = *(char **)(a1 + 262160);
    v193 = *(_DWORD *)(a1 + 262176);
    v194 = *v186;
    v340 = v188;
    v366 = v192;
    v342 = *v186;
    v350 = 0;
    if ( v193 < v191 )
    {
      do
      {
        v329 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v189 + v193 - (_QWORD)v190)) >> 17;
        v330 = v193 - *(_DWORD *)(a1 + 4 * v329);
        if ( v330 > 0xFFFF )
          LOWORD(v330) = -1;
        *(_WORD *)(a1 + 2LL * (unsigned __int16)v193 + 0x20000) = v330;
        *(_DWORD *)(a1 + 4 * v329) = v193++;
      }
      while ( v193 < v191 );
      v194 = v342;
      v187 = v371;
    }
    *(_DWORD *)(a1 + 262176) = v191;
    v195 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)(unsigned int)(-1640531535 * *v186) >> 17));
    if ( v195 < v188 )
    {
      v374 = (unsigned __int64)v186;
      goto LABEL_396;
    }
    v196 = v354;
    v197 = (_DWORD)v186 - v354;
    v379 = &v190[(_QWORD)v192 - v187];
    v198 = 0;
    v199 = 256;
    v344 = 0;
    v381 = 0;
    v373 = 256;
    while ( v199 > 0 )
    {
      if ( v195 < (unsigned int)v190 )
      {
        if ( v195 <= (int)v190 - 4 )
        {
          v231 = &v192[v195 - v187];
          if ( *(_DWORD *)v231 == v194 )
          {
            v232 = v345;
            v233 = (char *)(v186 + 1);
            v234 = v231 + 4;
            v235 = (char *)v186 + (unsigned int)v190 - v195;
            if ( v235 > v345 )
              v235 = v345;
            if ( v233 >= v235 - 7 )
            {
              v293 = (char *)(v186 + 1);
              while ( v293 < v235 - 7 )
              {
                if ( *v234 != *(_QWORD *)v293 )
                {
                  __asm { tzcnt   rdi, rax }
                  v238 = (_DWORD)v293 + ((unsigned int)_RDI >> 3) - (_DWORD)v233;
                  goto LABEL_554;
                }
                v293 += 8;
LABEL_542:
                ++v234;
              }
              if ( v293 < v235 - 3 && *(_DWORD *)v234 == *(_DWORD *)v293 )
              {
                v293 += 4;
                v234 = (_QWORD *)((char *)v234 + 4);
              }
              if ( v293 < v235 - 1 && *(_WORD *)v234 == *(_WORD *)v293 )
              {
                v293 += 2;
                v234 = (_QWORD *)((char *)v234 + 2);
              }
              if ( v293 < v235 && *(_BYTE *)v234 == *v293 )
                LODWORD(v293) = (_DWORD)v293 + 1;
              v238 = (_DWORD)v293 - (_DWORD)v233;
LABEL_554:
              v232 = v345;
            }
            else
            {
              if ( *v234 == *(_QWORD *)v233 )
              {
                v293 = (char *)(v186 + 3);
                goto LABEL_542;
              }
              __asm { tzcnt   rdi, rax }
              v238 = (unsigned int)_RDI >> 3;
            }
            v294 = v238 + 4;
            v192 = (char *)v186 + v238 + 4;
            if ( v192 == v235 && v235 < v232 )
            {
              v295 = (unsigned __int64)(v232 - 7);
              if ( v192 >= v232 - 7 )
              {
                v296 = v189;
                v297 = (char *)v186 + v238 + 4;
                goto LABEL_559;
              }
              if ( *(_QWORD *)v192 != *v189 )
              {
                __asm { tzcnt   rcx, rax }
                v298 = (unsigned int)_RCX >> 3;
              }
              else
              {
                v297 = v192 + 8;
                v296 = v189 + 1;
LABEL_559:
                while ( (unsigned __int64)v297 < v295 )
                {
                  if ( *v296 != *(_QWORD *)v297 )
                  {
                    __asm { tzcnt   rax, rax }
                    v298 = ((unsigned int)_RAX >> 3) - (_DWORD)v192 + (_DWORD)v297;
                    goto LABEL_570;
                  }
                  v297 += 8;
                  ++v296;
                }
                if ( v297 < v345 - 3 && *(_DWORD *)v296 == *(_DWORD *)v297 )
                {
                  v297 += 4;
                  v296 = (_QWORD *)((char *)v296 + 4);
                }
                if ( v297 < v345 - 1 && *(_WORD *)v296 == *(_WORD *)v297 )
                {
                  v297 += 2;
                  v296 = (_QWORD *)((char *)v296 + 2);
                }
                if ( v297 < v345 && *(_BYTE *)v296 == *v297 )
                  LODWORD(v297) = (_DWORD)v297 + 1;
                v298 = (_DWORD)v297 - (_DWORD)v192;
              }
LABEL_570:
              v294 = v238 + v298 + 4;
            }
            v299 = 0;
            if ( v197 )
            {
              v300 = v354 - (_DWORD)v186;
              if ( (__int64)(v354 - (_QWORD)v186) <= v366 - v231 )
                v300 = (_DWORD)v366 - (_DWORD)v231;
              while ( v299 - v300 > 3 )
              {
                if ( *(_DWORD *)&v231[v299 - 4] != *(_DWORD *)((char *)v186 + v299 - 4) )
                {
                  _BitScanReverse(&v301, *(_DWORD *)&v231[v299 - 4] ^ *(_DWORD *)((char *)v186 + v299 - 4));
                  v299 -= (31 - v301) >> 3;
                  goto LABEL_577;
                }
                v299 -= 4;
              }
              if ( v299 > v300 )
              {
                do
                {
                  if ( *((_BYTE *)v186 + v299 - 1) != v231[v299 - 1] )
                    break;
                  --v299;
                }
                while ( v299 > v300 );
                LOWORD(v191) = v357;
              }
            }
LABEL_577:
            LODWORD(v190) = v336;
            v302 = v294 - v299;
            v194 = v342;
            v198 = v344;
            if ( v302 > v333 )
            {
              v333 = v302;
              v350 = v191 - v195;
              v374 = (unsigned __int64)v186 + v299;
            }
          }
          else
          {
            v198 = v344;
          }
        }
      }
      else
      {
        v192 = (char *)v189 + v195 - (unsigned int)v190;
        if ( *(_WORD *)(v333 + v196 - 1) == *(_WORD *)&v192[v333 - (__int64)v197 - 1] && *(_DWORD *)v192 == v194 )
        {
          v200 = 0;
          if ( v197 )
          {
            v201 = v196 - (_DWORD)v186;
            v202 = -(__int64)(v195 - (unsigned int)v190);
            if ( (__int64)(v196 - (_QWORD)v186) <= v202 )
              v201 = v202;
            while ( v200 - v201 > 3 )
            {
              if ( *(_DWORD *)((char *)v186 + v200 - 4) != *(_DWORD *)&v192[v200 - 4] )
              {
                _BitScanReverse(&v203, *(_DWORD *)((char *)v186 + v200 - 4) ^ *(_DWORD *)&v192[v200 - 4]);
                v200 -= (31 - v203) >> 3;
                goto LABEL_302;
              }
              v200 -= 4;
            }
            if ( v200 > v201 )
            {
              do
              {
                if ( *((_BYTE *)v186 + v200 - 1) != v192[v200 - 1] )
                  break;
                --v200;
              }
              while ( v200 > v201 );
              v197 = (_DWORD)v186 - v354;
            }
          }
LABEL_302:
          v204 = v192 + 4;
          v205 = v186 + 1;
          v192 = v345 - 7;
          if ( v186 + 1 >= (_DWORD *)(v345 - 7) )
          {
            m = (char *)(v186 + 1);
            goto LABEL_537;
          }
          if ( *v204 != *v205 )
          {
            __asm { tzcnt   rcx, rax }
            v243 = (unsigned int)_RCX >> 3;
          }
          else
          {
            for ( m = (char *)(v186 + 3); ; m += 8 )
            {
              ++v204;
LABEL_537:
              if ( m >= v192 )
                break;
              if ( *v204 != *(_QWORD *)m )
              {
                __asm { tzcnt   rax, rax }
                v243 = ((unsigned int)_RAX >> 3) - (_DWORD)v205 + (_DWORD)m;
                goto LABEL_421;
              }
            }
            v192 = v345;
            if ( m < v345 - 3 && *(_DWORD *)v204 == *(_DWORD *)m )
            {
              m += 4;
              v204 = (_QWORD *)((char *)v204 + 4);
            }
            if ( m < v345 - 1 && *(_WORD *)v204 == *(_WORD *)m )
            {
              m += 2;
              v204 = (_QWORD *)((char *)v204 + 2);
            }
            if ( m < v345 && *(_BYTE *)v204 == *m )
              LODWORD(m) = (_DWORD)m + 1;
            v243 = (_DWORD)m - (_DWORD)v205;
          }
LABEL_421:
          v244 = v243 - v200 + 4;
          if ( v244 > v333 )
          {
            v333 = v244;
            v350 = v191 - v195;
            v374 = (unsigned __int64)v186 + v200;
          }
        }
      }
      v245 = a1;
      v246 = 1;
      if ( *(_WORD *)(a1 + 2LL * (unsigned __int16)v195 + 0x20000) != 1 )
        goto LABEL_465;
      if ( v198 )
      {
        v344 = v198;
        if ( v198 != 2 )
          goto LABEL_465;
      }
      else
      {
        if ( (_BYTE)v194 != HIBYTE(v194) || (unsigned __int16)v194 != HIWORD(v194) )
        {
          v198 = 1;
          v344 = 1;
LABEL_465:
          v248 = v340;
          goto LABEL_393;
        }
        v198 = 2;
        v344 = 2;
        v247 = LZ4HC_countPattern(v186 + 1, v345, v194, v192);
        v245 = a1;
        v381 = v247 + 4LL;
      }
      v248 = v340;
      v249 = v195 - 1;
      if ( v195 - 1 >= v340 && (unsigned int)v190 - v195 >= 3 )
      {
        if ( v249 < (unsigned int)v190 )
        {
          v190 = &v366[v249 - v371];
        }
        else
        {
          v246 = 0;
          v190 = (char *)v189 + v249 - (unsigned int)v190;
        }
        if ( *(_DWORD *)v190 == v194 )
        {
          v250 = v345;
          if ( v246 )
            v250 = v379;
          v252 = (unsigned int)LZ4HC_countPattern(v190 + 4, v250, v194, v340) + 4LL;
          if ( v246 )
          {
            v262 = &v190[v252] == v250;
            v254 = v342;
            if ( v262 )
            {
              v323 = v342;
              v324 = 8 * (v252 & 3);
              if ( v324 )
                v323 = (unsigned int)__ROL4__(v342, v324);
              v253 = v353;
              v252 += (unsigned int)LZ4HC_countPattern(v353, v345, v323, v251);
            }
            else
            {
              v253 = v353;
            }
            v255 = v366;
          }
          else
          {
            v253 = v353;
            v254 = v342;
            v255 = v353;
          }
          v256 = LZ4HC_reverseCountPattern(v190, v255, v254);
          v258 = v256;
          if ( v246 )
          {
            LODWORD(v190) = v336;
          }
          else
          {
            v262 = &v190[-v256] == v253;
            LODWORD(v190) = v336;
            if ( v262 && v371 < v336 )
            {
              v263 = 8LL * (-v256 & 3);
              if ( v263 )
                v257 = (unsigned int)__ROL4__(v257, v263);
              v264 = LZ4HC_reverseCountPattern(v379, v366, v257);
              v258 = v264 + v265;
            }
          }
          v248 = v340;
          v195 = v340;
          if ( v249 - v258 > v340 )
            v195 = v249 - v258;
          v259 = v252 + v249 - v195;
          if ( v259 >= v381 && v252 <= v381 )
          {
            v198 = v344;
            v195 = (unsigned int)v190;
            v266 = v252 - v381 + v249;
            v189 = v353;
            v197 = (_DWORD)v186 - v354;
            if ( (unsigned int)v190 - v266 - 1 >= 3 )
              v195 = v266;
            goto LABEL_394;
          }
          v197 = (_DWORD)v186 - v354;
          if ( (unsigned int)v190 - v195 - 1 < 3 )
          {
            v195 = (unsigned int)v190;
            goto LABEL_444;
          }
          if ( (_DWORD)v186 == (_DWORD)v354 )
          {
            v189 = v353;
            v260 = v381;
            if ( v259 < v381 )
              v260 = v259;
            if ( v333 < v260 )
            {
              if ( (unsigned __int64)v186 + (unsigned int)v190 - (unsigned __int64)v195 - (_QWORD)v353 > 0xFFFF )
                break;
              v333 = v260;
              v350 = v357 - v195;
              v374 = (unsigned __int64)v186;
            }
            v261 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v195 + 0x20000);
            if ( v261 > v195 )
              break;
            v195 -= v261;
          }
          else
          {
LABEL_444:
            v189 = v353;
          }
          v198 = v344;
          goto LABEL_394;
        }
      }
      v197 = (_DWORD)v186 - v354;
LABEL_393:
      LODWORD(v190) = v336;
      v195 -= *(unsigned __int16 *)(v245 + 2LL * (unsigned __int16)v195 + 0x20000);
LABEL_394:
      v194 = v342;
      v199 = v373 - 1;
      LOWORD(v191) = v357;
      v241 = v195 < v248;
      v192 = v366;
      v187 = v371;
      v196 = v354;
      --v373;
      if ( v241 )
        break;
    }
    v59 = v333;
LABEL_396:
    v58 = v350;
    v12 = v377;
    v57 = v383;
    v55 = v346;
    v48 = (unsigned __int64)v359;
    v46 = v389;
    v56 = v354;
    v51 = v375;
LABEL_56:
    v60 = v46;
    if ( v59 <= v55 )
    {
      if ( v56 >= v46 + v48 )
      {
        v63 = v389;
      }
      else
      {
        v63 = v56 - v48;
        v389 = v56 - v48;
      }
      v14 = v367;
      v64 = (_BYTE *)(v11 + 1);
      v16 = v368;
      v65 = v11 >> 32;
      v66 = v48 - (_QWORD)v367;
      v67 = v11;
      if ( a7 && (unsigned __int64)&v64[v66 / 0xFF + 8 + v66] > v368 )
      {
        v208 = v389;
        v105 = v337;
        goto LABEL_317;
      }
      if ( v66 < 0xF )
      {
        *(_BYTE *)v11 = 16 * v66;
      }
      else
      {
        v68 = v66 - 15;
        *(_BYTE *)v11 = -16;
        while ( v68 >= 0xFF )
        {
          *v64++ = -1;
          v68 -= 255LL;
        }
        *v64++ = v68;
      }
      v69 = (__int64 *)v367;
      v70 = &v64[v66];
      do
      {
        v71 = *v69++;
        *(_QWORD *)v64 = v71;
        v64 += 8;
      }
      while ( v64 < (_BYTE *)v70 );
      v72 = (__int64)(v70 + 1);
      *v70 = v337;
      v73 = v63 - 4LL;
      if ( a7 && v72 + v73 / 0xFF + 6 > v368 )
      {
LABEL_315:
        v105 = v337;
        goto LABEL_316;
      }
      v74 = *(_BYTE *)v11;
      if ( v73 < 0xF )
      {
        *(_BYTE *)v11 = v74 + v73;
      }
      else
      {
        *(_BYTE *)v11 = v74 + 15;
        for ( n = v63 - 19LL; n >= 0x1FE; n -= 510LL )
        {
          *(_BYTE *)v72 = -1;
          v158 = (_BYTE *)(v72 + 1);
          *v158 = -1;
          v72 = (__int64)(v158 + 1);
        }
        if ( n >= 0xFF )
        {
          LOBYTE(n) = n + 1;
          *(_BYTE *)v72++ = -1;
        }
        *(_BYTE *)v72++ = n;
      }
      v14 = (char *)(v63 + v48);
      v48 = v354;
      v76 = (_BYTE *)(v72 + 1);
      v65 = v72 >> 32;
      v77 = v354 - (_QWORD)v14;
      v67 = v72;
      if ( a7 && (unsigned __int64)&v76[v77 + 8 + v77 / 0xFF] > v368 )
      {
        v82 = v347;
LABEL_332:
        v105 = v82;
        v208 = v55;
        goto LABEL_317;
      }
      if ( v77 < 0xF )
      {
        *(_BYTE *)v72 = 16 * v77;
      }
      else
      {
        v78 = v77 - 15;
        *(_BYTE *)v72 = -16;
        while ( v78 >= 0xFF )
        {
          *v76++ = -1;
          v78 -= 255LL;
        }
        *v76++ = v78;
      }
      v79 = (__int64 *)v14;
      v80 = &v76[v77];
      do
      {
        v81 = *v79++;
        *(_QWORD *)v76 = v81;
        v76 += 8;
      }
      while ( v76 < (_BYTE *)v80 );
      v82 = v347;
      v83 = v57 - 4;
      *v80 = v347;
      v11 = (__int64)(v80 + 1);
      v364 = v11;
      v358 = HIDWORD(v11);
      if ( a7 && v11 + v83 / 0xFF + 6 > v368 )
        goto LABEL_332;
      v84 = *(_BYTE *)v72;
      if ( v83 < 0xF )
      {
        *(_BYTE *)v72 = v84 + v83;
      }
      else
      {
        *(_BYTE *)v72 = v84 + 15;
        for ( ii = v57 - 19; ii >= 0x1FE; ii -= 510LL )
        {
          *(_BYTE *)v11 = -1;
          v159 = (_BYTE *)(v11 + 1);
          *v159 = -1;
          v11 = (__int64)(v159 + 1);
        }
        if ( ii >= 0xFF )
        {
          LOBYTE(ii) = ii + 1;
          *(_BYTE *)v11++ = -1;
        }
        *(_BYTE *)v11++ = ii;
        v364 = v11;
        v358 = HIDWORD(v11);
      }
      v8 = a1;
      v14 = (char *)v12;
      v21 = v375;
      v359 = v12;
      v367 = (char *)v12;
      goto LABEL_19;
    }
    v61 = v46 + v48;
    if ( v374 >= v61 + 3 )
      break;
    if ( v374 < v61 )
    {
      v56 = v374;
      v354 = v374;
      v347 = v58;
      v55 = v59;
      v346 = v59;
      goto LABEL_53;
    }
    if ( v56 >= v61 )
      goto LABEL_660;
    v86 = v46 + v48 - v56;
    v55 -= v86;
    if ( v55 >= 4 )
    {
      v354 = v86 + v56;
LABEL_660:
      v87 = v347;
      goto LABEL_96;
    }
    v354 = v374;
    v87 = v58;
    v55 = v59;
LABEL_96:
    v88 = (_BYTE *)(v11 + 1);
    v67 = v11;
    v65 = v11 >> 32;
    v89 = (char *)v11;
    v90 = v367;
    v91 = v48 - (_QWORD)v367;
    if ( a7 && (unsigned __int64)&v88[v91 / 0xFF + 8 + v91] > v368 )
    {
      v16 = v368;
LABEL_399:
      v14 = v90;
      goto LABEL_315;
    }
    if ( v91 < 0xF )
    {
      *v89 = 16 * v91;
    }
    else
    {
      v92 = v91 - 15;
      *v89 = -16;
      while ( v92 >= 0xFF )
      {
        *v88++ = -1;
        v92 -= 255LL;
      }
      *v88++ = v92;
    }
    v93 = (__int64 *)v367;
    v94 = &v88[v91];
    do
    {
      v95 = *v93++;
      *(_QWORD *)v88 = v95;
      v88 += 8;
    }
    while ( v88 < (_BYTE *)v94 );
    v96 = v60 - 4;
    *v94 = v337;
    v11 = (__int64)(v94 + 1);
    v358 = HIDWORD(v11);
    if ( a7 && v11 + v96 / 0xFF + 6 > v368 )
    {
      v14 = v367;
      v16 = v368;
      goto LABEL_315;
    }
    v97 = *v89;
    if ( v96 >= 0xF )
    {
      *v89 = v97 + 15;
      for ( jj = v60 - 19; jj >= 0x1FE; jj -= 510LL )
      {
        *(_BYTE *)v11 = -1;
        v240 = (_BYTE *)(v11 + 1);
        *v240 = -1;
        v11 = (__int64)(v240 + 1);
      }
      if ( jj >= 0xFF )
      {
        LOBYTE(jj) = jj + 1;
        *(_BYTE *)v11++ = -1;
      }
      *(_BYTE *)v11++ = jj;
      v358 = HIDWORD(v11);
    }
    else
    {
      *v89 = v97 + v96;
    }
    v46 = v59;
    v50 = v354;
    v48 = v374;
    v8 = a1;
    v47 = v87;
    v359 = (_DWORD *)v374;
    LODWORD(v49) = v55;
    v367 = (char *)v61;
    LOWORD(v337) = v58;
    v389 = v59;
  }
  if ( v56 >= v61 )
  {
    v62 = v389;
  }
  else if ( (__int64)(v56 - v48) < 18 )
  {
    if ( v46 > 18 )
      v46 = 18;
    v389 = v46;
    if ( v48 + v46 > (unsigned __int64)(v12 - 1) )
    {
      v46 = v55 + v56 - v48 - 4;
      v389 = v46;
    }
    v62 = v389;
    v146 = v46 + v48 - v56;
    if ( v146 > 0 )
    {
      v354 = v146 + v56;
      v55 -= v146;
    }
  }
  else
  {
    v62 = v56 - v48;
    v389 = v56 - v48;
  }
  LODWORD(v65) = v358;
  v147 = (_BYTE *)(v11 + 1);
  v67 = v11;
  v148 = (char *)v11;
  v90 = v367;
  v149 = v48 - (_QWORD)v367;
  if ( a7 && (unsigned __int64)&v147[v149 + 8 + v149 / 0xFF] > v368 )
  {
    v16 = v368;
    goto LABEL_399;
  }
  if ( v149 < 0xF )
  {
    *v148 = 16 * v149;
  }
  else
  {
    v150 = v149 - 15;
    *v148 = -16;
    while ( v150 >= 0xFF )
    {
      *v147++ = -1;
      v150 -= 255LL;
    }
    *v147++ = v150;
  }
  v151 = (__int64 *)v367;
  v152 = &v147[v149];
  do
  {
    v153 = *v151++;
    *(_QWORD *)v147 = v153;
    v147 += 8;
  }
  while ( v147 < (_BYTE *)v152 );
  v105 = v337;
  *v152 = v337;
  v11 = (__int64)(v152 + 1);
  v358 = HIDWORD(v11);
  v154 = v62 - 4LL;
  if ( !a7 || v11 + v154 / 0xFF + 6 <= v368 )
  {
    v155 = *v148;
    if ( v154 < 0xF )
    {
      *v148 = v155 + v154;
    }
    else
    {
      *v148 = v155 + 15;
      for ( kk = v62 - 19LL; kk >= 0x1FE; kk -= 510LL )
      {
        *(_BYTE *)v11 = -1;
        v207 = (_BYTE *)(v11 + 1);
        *v207 = -1;
        v11 = (__int64)(v207 + 1);
      }
      if ( kk >= 0xFF )
      {
        LOBYTE(kk) = kk + 1;
        *(_BYTE *)v11++ = -1;
      }
      *(_BYTE *)v11++ = kk;
      v358 = HIDWORD(v11);
    }
    v157 = (char *)(v62 + v48);
    v51 = v375;
    v48 = v354;
    v367 = v157;
    LOWORD(v337) = v347;
    v56 = v374;
    v46 = v55;
    v389 = v55;
    v354 = v374;
    v55 = v59;
    v359 = (_DWORD *)v48;
    v347 = v58;
    v346 = v59;
    goto LABEL_53;
  }
  v14 = v367;
  v16 = v368;
LABEL_316:
  v208 = v389;
LABEL_317:
  if ( a7 != 2 )
  {
LABEL_41:
    result = 0;
    goto LABEL_13;
  }
  v11 = __PAIR64__(v65, v67);
  v209 = v48 - (_QWORD)v14;
  v210 = (v48 - (unsigned __int64)v14 + 240) / 0xFF + v48 - (_QWORD)v14 + 1;
  if ( v210 + __PAIR64__(v65, v67) <= v16 - 3 )
  {
    if ( v208 > 255 * (v16 - 3 - v210 - __PAIR64__(v65, v67)) + 18 )
      v208 = 255 * (v16 - 3 - v210 - v67) + 18;
    if ( (__int64)(v208 + v16 - v210 - __PAIR64__(v65, v67) + 2) >= 12 )
    {
      v211 = (_BYTE *)(__PAIR64__(v65, v67) + 1);
      if ( v209 < 0xF )
      {
        *(_BYTE *)__PAIR64__(v65, v67) = 16 * v209;
      }
      else
      {
        v212 = v209 - 15;
        *(_BYTE *)__PAIR64__(v65, v67) = -16;
        while ( v212 >= 0xFF )
        {
          *v211++ = -1;
          v212 -= 255LL;
        }
        *v211++ = v212;
      }
      v213 = &v211[v209];
      do
      {
        v214 = *(_QWORD *)v14;
        v14 += 8;
        *(_QWORD *)v211 = v214;
        v211 += 8;
      }
      while ( v211 < (_BYTE *)v213 );
      *v213 = v105;
      v215 = *(_BYTE *)__PAIR64__(v65, v67);
      v11 = (__int64)(v213 + 1);
      if ( (unsigned __int64)(v208 - 4LL) < 0xF )
      {
        *(_BYTE *)__PAIR64__(v65, v67) = v215 + v208 - 4;
      }
      else
      {
        *(_BYTE *)__PAIR64__(v65, v67) = v215 + 15;
        for ( mm = v208 - 19LL; mm >= 0x1FE; mm -= 510LL )
        {
          *(_BYTE *)v11 = -1;
          v242 = (_BYTE *)(v11 + 1);
          *v242 = -1;
          v11 = (__int64)(v242 + 1);
        }
        if ( mm >= 0xFF )
        {
          LOBYTE(mm) = mm + 1;
          *(_BYTE *)v11++ = -1;
        }
        *(_BYTE *)v11++ = mm;
      }
      v14 = (char *)(v208 + v48);
    }
  }
  v9 = a4;
  v17 = v384 - v14;
  LODWORD(v10) = v386;
  v18 = v384 - v14;
LABEL_38:
  v16 += 5LL;
LABEL_39:
  if ( v11 + (v17 + 240) / 0xFF + v17 + 1 > v16 )
  {
    if ( a7 == 1 )
      goto LABEL_41;
    v18 = v16 - v11 - 1 - ((v16 - v11 - 1 + 241) >> 8);
  }
LABEL_9:
  if ( v18 < 0xF )
  {
    LOBYTE(v19) = 16 * v18;
  }
  else
  {
    *(_BYTE *)v11 = -16;
    v19 = v18 - 15;
    ++v11;
    while ( v19 >= 0xFF )
    {
      *(_BYTE *)v11++ = -1;
      v19 -= 255LL;
    }
  }
  *(_BYTE *)v11 = v19;
  memmove((void *)(v11 + 1), v14, v18);
  *v9 = v18 + (_DWORD)v14 - (_DWORD)v10;
  result = (unsigned int)(v18 - v387 + v11 + 1);
  if ( (int)result <= 0 )
LABEL_13:
    *(_BYTE *)(a1 + 262183) = 1;
  return result;
}

```

## disassembly

```asm
0x1800edf40  mov     rax, rsp
0x1800edf43  mov     [rax+20h], r9
0x1800edf47  mov     [rax+18h], r8
0x1800edf4b  mov     [rax+10h], rdx
0x1800edf4f  mov     [rax+8], rcx
0x1800edf53  push    rbx
0x1800edf54  push    rbp
0x1800edf55  push    rsi
0x1800edf56  push    rdi
0x1800edf57  push    r12
0x1800edf59  push    r13
0x1800edf5b  push    r14
0x1800edf5d  push    r15
0x1800edf5f  sub     rsp, 118h
0x1800edf66  cmp     qword ptr [rcx+40028h], 0
0x1800edf6e  mov     r10, r8
0x1800edf71  mov     r8, rcx
0x1800edf74  mov     r12, r9
0x1800edf77  mov     r13, rdx
0x1800edf7a  jnz     loc_1800EE0B5
0x1800edf80  cmp     [rsp+158h+arg_30], 2
0x1800edf88  mov     r11d, 1
0x1800edf8e  jz      loc_1800EE0DD
0x1800edf94  cmp     dword ptr [r9], 7E000000h
0x1800edf9b  ja      loc_1800EE0EB
0x1800edfa1  movsxd  rax, dword ptr [r9]
0x1800edfa4  mov     rbx, r10
0x1800edfa7  add     [rcx+40000h], rax
0x1800edfae  mov     r14, r13
0x1800edfb1  movsxd  rdx, dword ptr [r9]
0x1800edfb4  mov     r15, r13
0x1800edfb7  movsxd  rcx, [rsp+158h+arg_20]
0x1800edfbf  add     rcx, r10
0x1800edfc2  mov     [rsp+158h+var_C8], r13
0x1800edfca  cmp     [rsp+158h+arg_30], 2
0x1800edfd2  mov     r10, 8080808080808081h
0x1800edfdc  lea     r9, [rdx+r13]
0x1800edfe0  mov     [rsp+158h+var_A8], r13
0x1800edfe8  mov     [rsp+158h+var_50], r9
0x1800edff0  lea     rbp, [rcx-5]
0x1800edff4  mov     [rsp+158h+var_B0], rbx
0x1800edffc  cmovnz  rbp, rcx
0x1800ee000  mov     [rsp+158h+var_D0], rbx
0x1800ee008  mov     [rsp+158h+var_A0], rbp
0x1800ee010  mov     dword ptr [r12], 0
0x1800ee018  cmp     edx, 0Dh
0x1800ee01b  jge     loc_1800EE0EF
0x1800ee021  sub     r9, r15
0x1800ee024  cmp     [rsp+158h+arg_30], 2
0x1800ee02c  mov     rdi, r9
0x1800ee02f  jz      loc_1800EE2E2
0x1800ee035  cmp     [rsp+158h+arg_30], 0
0x1800ee03d  jnz     loc_1800EE2E6
0x1800ee043  lea     rsi, [rdi+r15]
0x1800ee047  cmp     rdi, 0Fh
0x1800ee04b  jb      loc_1800EED86
0x1800ee051  mov     byte ptr [rbx], 0F0h
0x1800ee054  lea     rax, [rdi-0Fh]
0x1800ee058  inc     rbx
0x1800ee05b  cmp     rax, 0FFh
0x1800ee061  jnb     loc_1800F087C
0x1800ee067  lea     rcx, [rbx+1]; void *
0x1800ee06b  mov     [rbx], al
0x1800ee06d  mov     r8, rdi; Size
0x1800ee070  lea     rbp, [rbx+1]
0x1800ee074  mov     rdx, r15; Src
0x1800ee077  call    memmove
0x1800ee07c  sub     edi, [rsp+158h+arg_10]
0x1800ee083  sub     esi, r13d
0x1800ee086  mov     [r12], esi
0x1800ee08a  lea     eax, [rdi+rbp]
0x1800ee08d  test    eax, eax
0x1800ee08f  jg      short loc_1800EE0A0
0x1800ee091  mov     rcx, [rsp+158h+arg_0]
0x1800ee099  mov     byte ptr [rcx+40027h], 1
0x1800ee0a0  add     rsp, 118h
0x1800ee0a7  pop     r15
0x1800ee0a9  pop     r14
0x1800ee0ab  pop     r13
0x1800ee0ad  pop     r12
0x1800ee0af  pop     rdi
0x1800ee0b0  pop     rsi
0x1800ee0b1  pop     rbp
0x1800ee0b2  pop     rbx
0x1800ee0b3  retn
0x1800ee0b5  mov     eax, [rsp+158h+arg_30]
0x1800ee0bc  mov     r8, r10
0x1800ee0bf  mov     rcx, [rsp+158h+arg_0]
0x1800ee0c7  mov     [rsp+158h+var_128], eax
0x1800ee0cb  mov     eax, [rsp+158h+arg_20]
0x1800ee0d2  mov     [rsp+158h+var_138], eax
0x1800ee0d6  call    LZ4HC_compress_generic_dictCtx
0x1800ee0db  jmp     short loc_1800EE0A0
0x1800ee0dd  cmp     [rsp+158h+arg_20], r11d
0x1800ee0e5  jge     loc_1800EDF94
0x1800ee0eb  xor     eax, eax
0x1800ee0ed  jmp     short loc_1800EE0A0
0x1800ee0ef  lea     rax, [r9-5]
0x1800ee0f3  xor     r11d, r11d
0x1800ee0f6  mov     [rsp+158h+var_100], rax
0x1800ee0fb  lea     rcx, [r9-0Ch]
0x1800ee0ff  xor     eax, eax
0x1800ee101  mov     [rsp+158h+var_80], rcx
0x1800ee109  mov     [rsp+158h+var_88], rax
0x1800ee111  mov     [rsp+158h+var_E0], r11
0x1800ee116  cmp     r14, rcx
0x1800ee119  ja      loc_1800F085F
0x1800ee11f  mov     ecx, [r8+4001Ch]
0x1800ee126  mov     edi, r14d
0x1800ee129  mov     rbp, [r8+40008h]
0x1800ee130  mov     r15d, ecx
0x1800ee133  mov     r13d, [r8+40018h]
0x1800ee13a  sub     edi, ebp
0x1800ee13c  add     edi, r13d
0x1800ee13f  mov     [rsp+158h+arg_28], 3
0x1800ee14a  lea     eax, [rcx+10000h]
0x1800ee150  mov     [rsp+158h+var_B8], rbp
0x1800ee158  mov     [rsp+158h+var_D8], edi
0x1800ee15f  mov     dword ptr [rsp+158h+var_90], ecx
0x1800ee166  cmp     eax, edi
0x1800ee168  jbe     loc_1800EE2D6
0x1800ee16e  mov     rdx, [r8+40010h]
0x1800ee175  mov     rax, rcx
0x1800ee178  mov     r8d, [r8+40020h]
0x1800ee17f  xor     esi, esi
0x1800ee181  mov     r12d, [r14]
0x1800ee184  mov     rcx, r13
0x1800ee187  sub     rcx, rax
0x1800ee18a  mov     [rsp+158h+var_114], r15d
0x1800ee18f  add     rcx, rdx
0x1800ee192  mov     [rsp+158h+var_E8], rdx
0x1800ee197  xor     eax, eax
0x1800ee199  mov     [rsp+158h+var_98], rcx
0x1800ee1a1  mov     [rsp+158h+var_C0], rsi
0x1800ee1a9  mov     r9d, 100h
0x1800ee1af  mov     [rsp+158h+var_F0], r9d
0x1800ee1b4  mov     [rsp+158h+var_110], eax
0x1800ee1b8  cmp     r8d, edi
0x1800ee1bb  jb      loc_1800F0679
0x1800ee1c1  mov     r8, [rsp+158h+arg_0]
0x1800ee1c9  mov     [r8+40020h], edi
0x1800ee1d0  imul    ecx, [r14], 9E3779B1h
0x1800ee1d7  shr     rcx, 11h
0x1800ee1db  mov     r11d, [r8+rcx*4]
0x1800ee1df  cmp     r11d, r15d
0x1800ee1e2  jb      loc_1800EE361
0x1800ee1e8  mov     ebx, dword ptr [rsp+158h+var_90]
0x1800ee1ef  test    r9d, r9d
0x1800ee1f2  jle     loc_1800EE359
0x1800ee1f8  cmp     r11d, r13d
0x1800ee1fb  jnb     short loc_1800EE269
0x1800ee1fd  lea     eax, [r13-4]
0x1800ee201  cmp     r11d, eax
0x1800ee204  ja      loc_1800EE931
0x1800ee20a  mov     eax, r11d
0x1800ee20d  sub     eax, ebx
0x1800ee20f  mov     ecx, eax
0x1800ee211  cmp     [rax+rdx], r12d
0x1800ee215  jnz     loc_1800EE931
0x1800ee21b  mov     r9d, r13d
0x1800ee21e  lea     r8, [r14+4]
0x1800ee222  sub     r9d, r11d
0x1800ee225  mov     [rsp+158h+var_78], r8
0x1800ee22d  add     r9, r14
0x1800ee230  cmp     r9, [rsp+158h+var_100]
0x1800ee235  cmova   r9, [rsp+158h+var_100]
0x1800ee23b  add     rdx, 4
0x1800ee23f  add     rdx, rcx
0x1800ee242  lea     r10, [r9-7]
0x1800ee246  cmp     r8, r10
0x1800ee249  jnb     loc_1800EEC3E
0x1800ee24f  mov     rax, [rdx]
0x1800ee252  xor     rax, [r8]
0x1800ee255  jz      loc_1800EF456
0x1800ee25b  tzcnt   r10, rax
0x1800ee260  shr     r10d, 3
0x1800ee264  jmp     loc_1800EEC98
0x1800ee269  movsxd  r10, [rsp+158h+arg_28]
0x1800ee271  mov     eax, r11d
0x1800ee274  sub     eax, r13d
0x1800ee277  mov     r8d, eax
0x1800ee27a  add     rax, r10
0x1800ee27d  movzx   ecx, word ptr [rax+rbp-1]
0x1800ee282  cmp     [r10+r14-1], cx
0x1800ee288  jnz     loc_1800F06D3
0x1800ee28e  cmp     [r8+rbp], r12d
0x1800ee292  jnz     loc_1800F06D3
0x1800ee298  mov     r9, [rsp+158h+var_100]
0x1800ee29d  lea     rdx, [r8+4]
0x1800ee2a1  lea     r8, [r14+4]
0x1800ee2a5  add     rdx, rbp
0x1800ee2a8  add     r9, 0FFFFFFFFFFFFFFF9h
0x1800ee2ac  mov     [rsp+158h+var_78], r8
0x1800ee2b4  cmp     r8, r9
0x1800ee2b7  jnb     loc_1800EEBA2
0x1800ee2bd  mov     rax, [rdx]
0x1800ee2c0  xor     rax, [r8]
0x1800ee2c3  jz      loc_1800EF44D
0x1800ee2c9  tzcnt   rcx, rax
0x1800ee2ce  shr     ecx, 3
0x1800ee2d1  jmp     loc_1800EEBFA
0x1800ee2d6  lea     r15d, [rdi-0FFFFh]
0x1800ee2dd  jmp     loc_1800EE16E
0x1800ee2e2  add     rbp, 5
0x1800ee2e6  lea     rcx, [r9+0F0h]
0x1800ee2ed  mov     rax, r10
0x1800ee2f0  mul     rcx
0x1800ee2f3  lea     rax, [r9+1]
0x1800ee2f7  shr     rdx, 7
0x1800ee2fb  add     rdx, rbx
0x1800ee2fe  add     rax, rdx
0x1800ee301  cmp     rax, rbp
0x1800ee304  jbe     loc_1800EE043
0x1800ee30a  cmp     [rsp+158h+arg_30], 1
0x1800ee312  jnz     loc_1800EEF48
0x1800ee318  xor     eax, eax
0x1800ee31a  jmp     loc_1800EE091
0x1800ee31f  movzx   ecx, r11w
0x1800ee323  movzx   eax, word ptr [r8+rcx*2+20000h]
0x1800ee32c  sub     r11d, eax
0x1800ee32f  mov     r9d, [rsp+158h+var_F0]
0x1800ee334  mov     edi, [rsp+158h+var_D8]
0x1800ee33b  dec     r9d
0x1800ee33e  mov     rdx, [rsp+158h+var_E8]
0x1800ee343  mov     r14, [rsp+158h+var_C8]
0x1800ee34b  mov     [rsp+158h+var_F0], r9d
0x1800ee350  cmp     r11d, r15d
0x1800ee353  jnb     loc_1800EE1EF
0x1800ee359  mov     rbx, [rsp+158h+var_B0]
0x1800ee361  mov     r9d, [rsp+158h+arg_28]
0x1800ee369  mov     esi, [rsp+158h+var_110]
0x1800ee36d  mov     dword ptr [rsp+158h+var_58+4], r9d
0x1800ee375  mov     dword ptr [rsp+158h+var_58], esi
0x1800ee37c  cmp     r9d, 4
0x1800ee380  jl      loc_1800EF40F
0x1800ee386  mov     r11, [rsp+158h+var_58]
0x1800ee38e  mov     r13, [rsp+158h+var_C8]
0x1800ee396  mov     rcx, r11
0x1800ee399  shr     rcx, 20h
0x1800ee39d  mov     rdx, r13
0x1800ee3a0  mov     rsi, [rsp+158h+var_80]
0x1800ee3a8  mov     [rsp+158h+var_70], rcx
0x1800ee3b0  mov     [rsp+158h+var_68], rdx
0x1800ee3b8  movsxd  r14, r9d
0x1800ee3bb  mov     [rsp+158h+var_78], r14
0x1800ee3c3  lea     r10, [r14+r13]
0x1800ee3c7  mov     [rsp+158h+var_60], r10
0x1800ee3cf  cmp     r10, rsi
0x1800ee3d2  jbe     loc_1800EF013
0x1800ee3d8  xor     r8d, r8d
0x1800ee3db  xor     r12d, r12d
0x1800ee3de  mov     [rsp+158h+var_F4], r8d
0x1800ee3e3  mov     [rsp+158h+var_F8], r12d
0x1800ee3e8  cmp     r12d, r9d
0x1800ee3eb  jle     loc_1800EE793
0x1800ee3f1  mov     rdi, [rsp+158h+var_E0]
0x1800ee3f6  cmp     rdx, r13
0x1800ee3f9  jb      loc_1800EEF62
0x1800ee3ff  mov     rax, rdi
0x1800ee402  sub     rax, r13
0x1800ee405  cmp     rax, 3
0x1800ee409  jl      loc_1800EEF90
0x1800ee40f  mov     rax, rdi
0x1800ee412  mov     ecx, 12h
0x1800ee417  sub     rax, r13
0x1800ee41a  cmp     rax, rcx
0x1800ee41d  jl      loc_1800EED32
0x1800ee423  movsxd  r10, r12d
0x1800ee426  mov     [rsp+158h+var_60], r10
0x1800ee42e  lea     r14, [r10+rdi]
0x1800ee432  mov     [rsp+158h+var_78], r14
0x1800ee43a  cmp     r14, rsi
0x1800ee43d  jbe     loc_1800EF246
0x1800ee443  xor     ebp, ebp
0x1800ee445  xor     r15d, r15d
0x1800ee448  movsxd  r11, r9d
0x1800ee44b  cmp     r15d, r12d
0x1800ee44e  jle     short loc_1800EE499
0x1800ee450  mov     rdx, [rsp+158h+var_88]
0x1800ee458  lea     r10, [r11+r13]
0x1800ee45c  lea     rax, [r10+3]
0x1800ee460  cmp     rdx, rax
0x1800ee463  jb      loc_1800EE6B1
0x1800ee469  cmp     rdi, r10
0x1800ee46c  jnb     loc_1800F07E0
0x1800ee472  mov     rax, rdi
0x1800ee475  mov     ecx, 12h
0x1800ee47a  sub     rax, r13
0x1800ee47d  cmp     rax, rcx
0x1800ee480  jl      loc_1800EED91
0x1800ee486  mov     r10d, edi
0x1800ee489  sub     r10d, r13d
0x1800ee48c  mov     [rsp+158h+arg_28], r10d
0x1800ee494  jmp     loc_1800EEDE6
0x1800ee499  lea     rax, [r11+r13]
0x1800ee49d  cmp     rdi, rax
0x1800ee4a0  jnb     loc_1800F081C
0x1800ee4a6  mov     r11d, edi
0x1800ee4a9  sub     r11d, r13d
0x1800ee4ac  mov     [rsp+158h+arg_28], r11d
  ... truncated ...
```
