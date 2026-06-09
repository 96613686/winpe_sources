# CalcNDim_Data8To8_Lut16

- ea: `0x180008480`
- end: `0x18000a9fc`
- name: `CalcNDim_Data8To8_Lut16`
- size: `9596`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800029a4`
- `0x18001c210`

## callees

- `0x180008480`
- `0x18000aa10`
- `0x180013090`
- `0x180014d50`
- `0x18001a958`
- `0x18003cff6`
- `0x18003d00e`
- `0x18003d040`

## pseudocode

```c
__int64 __fastcall CalcNDim_Data8To8_Lut16(__int64 a1, int *a2)
{
  int v2; // r9d
  int *v3; // rdi
  unsigned int v5; // edx
  int v6; // r11d
  __int64 v7; // r12
  int v8; // r10d
  __int64 v9; // rax
  unsigned int v10; // ecx
  __m128i v11; // xmm0
  __m128i v12; // xmm1
  __m128i v13; // xmm2
  unsigned int v14; // edx
  int v15; // r11d
  int v16; // ebx
  __m128i v17; // xmm3
  unsigned int v18; // r14d
  __int64 v19; // rsi
  __int64 v20; // r15
  unsigned int v21; // r10d
  unsigned int v22; // edx
  unsigned int v23; // ecx
  unsigned int v24; // eax
  unsigned int v25; // edx
  unsigned int v26; // r9d
  int v27; // edi
  bool v28; // zf
  int *v29; // rsi
  unsigned int v30; // edx
  bool v31; // al
  bool v32; // r9
  __m128i v33; // xmm9
  int v34; // r13d
  __m128i v35; // xmm8
  __m128i v36; // xmm10
  __m128i v37; // xmm11
  int v38; // esi
  __int64 v39; // rdx
  __int64 v40; // rdx
  _WORD *v41; // rcx
  int v42; // r13d
  _BYTE *v44; // rcx
  unsigned int v45; // edi
  int v46; // r11d
  int k; // ecx
  unsigned int v48; // eax
  unsigned int *v49; // rdi
  unsigned __int64 m; // rcx
  int *v51; // rdi
  unsigned __int64 n; // rcx
  int v53; // ecx
  int v54; // ecx
  int v55; // eax
  int v56; // eax
  int v57; // eax
  int v58; // ecx
  unsigned int v59; // r9d
  __int64 ii; // rdi
  char v61; // r10
  __int64 jj; // r8
  unsigned int v63; // r9d
  char v64; // dl
  __m128i v65; // xmm6
  __m128i v66; // xmm7
  __m128i v67; // xmm9
  __m128i v68; // xmm10
  int v69; // edx
  unsigned int v70; // ecx
  int v71; // eax
  __int64 v72; // rax
  bool v73; // r9
  __int64 v74; // rdi
  int v75; // r10d
  __int64 v76; // r9
  unsigned int v77; // edi
  __int64 v78; // rcx
  unsigned int v79; // ebx
  int v80; // r10d
  __int64 v81; // r9
  unsigned int v82; // eax
  int v83; // edi
  int v84; // edx
  unsigned int v85; // edx
  int v86; // ecx
  __int64 v87; // rcx
  int v88; // r15d
  int v89; // ebx
  unsigned int v90; // r11d
  int v91; // r14d
  unsigned int v92; // edx
  __int64 v93; // r10
  __int64 v94; // r8
  unsigned int v95; // eax
  int v96; // r10d
  int v97; // r8d
  __int64 v98; // r9
  int v99; // r11d
  __int64 v100; // rcx
  int v101; // esi
  __int64 v102; // rdi
  __int64 v103; // rdi
  __int64 v104; // r11
  int v105; // r10d
  int v106; // ebx
  unsigned int v107; // edi
  __int64 v108; // rcx
  __int64 v109; // rdi
  _BYTE *v110; // rax
  unsigned int v111; // edx
  __int64 v112; // rdx
  __m128i v113; // xmm2
  __int64 v114; // rax
  __int64 v115; // rdx
  __m128i v116; // xmm2
  __int64 v117; // rax
  __int64 v118; // rdx
  int v119; // r8d
  __int64 v120; // rdi
  __int64 v121; // rax
  __int64 v122; // r8
  __int64 v123; // rdi
  double v124; // xmm1_8
  unsigned int v125; // r9d
  __int64 v126; // r10
  double v127; // xmm3_8
  double v128; // xmm0_8
  double v129; // xmm0_8
  double v130; // xmm1_8
  int v131; // r10d
  __int64 v132; // r9
  unsigned int v133; // edi
  __int64 v134; // rcx
  int v135; // eax
  int v136; // eax
  int v137; // r8d
  __int64 v138; // rdi
  __int64 v139; // rax
  unsigned int v140; // edx
  unsigned int v141; // ecx
  int v142; // eax
  __int64 v143; // rax
  unsigned int v144; // r15d
  unsigned int v145; // r14d
  int v146; // r12d
  __int64 v147; // rdi
  int v148; // r10d
  __int64 v149; // r9
  unsigned int v150; // edx
  __int64 v151; // rcx
  int *v152; // rdi
  int v153; // r15d
  __int64 v154; // rdi
  __int16 v155; // dx
  _WORD *v156; // rax
  __int64 v157; // rdx
  __m128i v158; // xmm2
  __int64 v159; // rax
  unsigned int v160; // edi
  _BYTE *v161; // rax
  unsigned int v162; // edx
  int v163; // r11d
  __int64 v164; // r10
  unsigned int v165; // edi
  __int64 v166; // rcx
  __int64 v167; // r8
  double v168; // xmm3_8
  double v169; // xmm2_8
  unsigned int v170; // edi
  __int64 v171; // r10
  double v172; // xmm2_8
  __int64 v173; // r11
  __int64 v174; // rdx
  double v175; // xmm1_8
  __int64 v176; // r10
  int v177; // r11d
  unsigned int v178; // edi
  __int64 v179; // rcx
  int v180; // r9d
  int v181; // r10d
  __int64 v182; // r8
  unsigned int v183; // ebx
  unsigned int v184; // ebx
  int v185; // ebx
  __int64 v186; // rcx
  unsigned int v187; // edx
  unsigned int v188; // eax
  int v189; // r14d
  unsigned int v190; // edi
  __int64 v191; // rsi
  __int64 v192; // r10
  unsigned int v193; // eax
  int v194; // r9d
  int v195; // r11d
  __int64 v196; // r10
  int v197; // esi
  __int64 v198; // rcx
  int v199; // r8d
  __int64 v200; // rdi
  __int64 v201; // rdi
  __int64 v202; // rdi
  unsigned int v203; // eax
  int v204; // ecx
  unsigned int v205; // eax
  unsigned int v206; // eax
  __int64 v207; // r8
  int v208; // r10d
  __int64 v209; // rcx
  int v210; // esi
  __int64 v211; // rdi
  __int64 v212; // rdi
  __int64 v213; // rdx
  unsigned int v214; // edi
  __int64 v215; // rcx
  __int64 v216; // r11
  __int64 v217; // r8
  double v218; // xmm2_8
  double v219; // xmm1_8
  unsigned int v220; // edx
  __int64 v221; // rdi
  double v222; // xmm0_8
  int v223; // r8d
  __int64 v224; // rdi
  __int64 v225; // rax
  __int64 i; // rdx
  int v227; // r11d
  int j; // ecx
  int v229; // ecx
  unsigned int v230; // r14d
  bool v231; // cc
  __int64 v232; // rcx
  int v233; // esi
  __int64 v234; // rdi
  __int64 v235; // rdi
  unsigned int v236; // edi
  __int64 v237; // rcx
  int v238; // r11d
  __int64 v239; // r10
  unsigned int v240; // edi
  __int64 v241; // rcx
  unsigned int v242; // r8d
  __int64 v243; // rdi
  double v244; // xmm3_8
  double v245; // xmm2_8
  unsigned int v246; // r10d
  __int64 v247; // r9
  double v248; // xmm4_8
  double v249; // xmm2_8
  _BYTE *v250; // rdx
  _BYTE *v251; // rcx
  __int64 v252; // r8
  int v253; // edi
  __int64 v254; // rax
  __int64 v255; // rax
  int v256; // r8d
  __int64 v257; // rdi
  __int64 v258; // rax
  __int64 v259; // r11
  __int64 v260; // rdx
  double v261; // xmm1_8
  double v262; // xmm1_8
  __int16 v263; // dx
  _WORD *v264; // rax
  __int64 v265; // rdx
  __m128i v266; // xmm2
  __int64 v267; // rax
  __int64 v268; // rdx
  __m128i v269; // xmm1
  __int64 v270; // rax
  __int64 v271; // rdx
  __int64 v272; // rdx
  unsigned int v273; // r8d
  __int64 v274; // rdx
  unsigned int v275; // edi
  __m128i v276; // xmm2
  __int64 v277; // rax
  __m128i v278; // xmm2
  __int64 v279; // rax
  int v280; // ecx
  int v281; // edx
  char v282; // r10
  char v283; // cl
  int v284; // r8d
  __int64 v285; // rdi
  __int64 v286; // rax
  int v287; // r10d
  __int64 v288; // r9
  unsigned int v289; // edx
  __int64 v290; // rcx
  int v291; // r8d
  __int64 v292; // rdi
  __int64 v293; // rax
  __int64 v294; // r8
  int v295; // edi
  __int64 v296; // rax
  __int64 v297; // rax
  _BYTE *v298; // rcx
  _BYTE *v299; // rdx
  __int64 v300; // rdx
  _BYTE *v301; // rcx
  _WORD *v302; // rcx
  __int64 v303; // rdx
  __m128i v304; // xmm2
  __int64 v305; // rax
  unsigned int v306; // r8d
  int v307; // [rsp+28h] [rbp-E0h]
  int v308; // [rsp+28h] [rbp-E0h]
  unsigned int v309; // [rsp+2Ch] [rbp-DCh]
  unsigned int v310; // [rsp+30h] [rbp-D8h]
  char v311; // [rsp+34h] [rbp-D4h]
  unsigned int v312; // [rsp+38h] [rbp-D0h]
  int v313; // [rsp+3Ch] [rbp-CCh]
  int v314; // [rsp+40h] [rbp-C8h]
  int v316; // [rsp+50h] [rbp-B8h]
  char v317; // [rsp+54h] [rbp-B4h]
  unsigned int v318; // [rsp+58h] [rbp-B0h]
  char v319; // [rsp+5Ch] [rbp-ACh]
  unsigned int v320; // [rsp+60h] [rbp-A8h]
  char v321; // [rsp+64h] [rbp-A4h]
  int v322; // [rsp+68h] [rbp-A0h]
  unsigned int v323; // [rsp+6Ch] [rbp-9Ch]
  char v324; // [rsp+70h] [rbp-98h]
  int v325; // [rsp+74h] [rbp-94h]
  int v326; // [rsp+78h] [rbp-90h]
  unsigned int v327; // [rsp+7Ch] [rbp-8Ch]
  int v328; // [rsp+80h] [rbp-88h]
  int v329; // [rsp+84h] [rbp-84h]
  unsigned int v330; // [rsp+88h] [rbp-80h]
  int v331; // [rsp+8Ch] [rbp-7Ch]
  char v332; // [rsp+90h] [rbp-78h]
  char v333; // [rsp+94h] [rbp-74h]
  char v334; // [rsp+98h] [rbp-70h]
  __int64 v335; // [rsp+A0h] [rbp-68h]
  int v336; // [rsp+A8h] [rbp-60h]
  int v337; // [rsp+ACh] [rbp-5Ch]
  int v338; // [rsp+B0h] [rbp-58h]
  unsigned int v339; // [rsp+B4h] [rbp-54h]
  __int64 v340; // [rsp+B8h] [rbp-50h]
  int v341; // [rsp+C0h] [rbp-48h]
  int v342; // [rsp+C8h] [rbp-40h]
  __int64 v343; // [rsp+C8h] [rbp-40h]
  __int64 v344; // [rsp+C8h] [rbp-40h]
  int v345; // [rsp+D0h] [rbp-38h]
  char v346; // [rsp+D4h] [rbp-34h]
  int v347; // [rsp+D8h] [rbp-30h]
  int v348; // [rsp+DCh] [rbp-2Ch]
  bool v349; // [rsp+E0h] [rbp-28h]
  char v350; // [rsp+E4h] [rbp-24h]
  int v351; // [rsp+E8h] [rbp-20h]
  int v352; // [rsp+ECh] [rbp-1Ch]
  int v353; // [rsp+F0h] [rbp-18h]
  int v354; // [rsp+F4h] [rbp-14h]
  int v355; // [rsp+F8h] [rbp-10h]
  unsigned int v356; // [rsp+FCh] [rbp-Ch]
  unsigned int v357; // [rsp+100h] [rbp-8h]
  __int64 v358; // [rsp+108h] [rbp+0h]
  __int64 v359; // [rsp+110h] [rbp+8h]
  _QWORD v360[8]; // [rsp+118h] [rbp+10h] BYREF
  _QWORD v361[8]; // [rsp+158h] [rbp+50h] BYREF
  _DWORD v362[8]; // [rsp+198h] [rbp+90h] BYREF
  _DWORD v363[8]; // [rsp+1B8h] [rbp+B0h] BYREF
  _DWORD v364[8]; // [rsp+1D8h] [rbp+D0h] BYREF
  _QWORD Src[8]; // [rsp+1F8h] [rbp+F0h] BYREF
  _DWORD v366[8]; // [rsp+238h] [rbp+130h] BYREF
  _DWORD v367[16]; // [rsp+258h] [rbp+150h] BYREF
  _DWORD v368[42]; // [rsp+298h] [rbp+190h] BYREF

  v2 = *a2;
  v3 = a2;
  if ( (unsigned int)(*a2 - 1) > 3 )
    return 87;
  if ( (unsigned int)(v2 - 1) <= 1 )
  {
    v55 = a2[12];
    if ( v55 == 3 )
    {
      if ( *(_DWORD *)(a1 + 24) == 6 )
      {
        v135 = a2[13];
        if ( v135 == 3 )
        {
          v136 = *(_DWORD *)(a1 + 28);
          if ( v136 == 3 || v136 == 6 )
            return Calc323Dim_Data8To8_Lut16(a1, a2, a1);
        }
        else if ( v135 == 4 && ((*(_DWORD *)(a1 + 28) - 4) & 0xFFFFFFFB) == 0 )
        {
          return Calc324Dim_Data8To8_Lut16(a1, a2, a1);
        }
      }
    }
    else if ( v55 == 4 && *(_DWORD *)(a1 + 24) == 8 )
    {
      v56 = a2[13];
      if ( v56 == 3 )
      {
        v57 = *(_DWORD *)(a1 + 28);
        if ( v57 == 3 || v57 == 6 )
          return Calc423Dim_Data8To8_Lut16(a1, a2, a1);
      }
      else if ( v56 == 4 && ((*(_DWORD *)(a1 + 28) - 4) & 0xFFFFFFFB) == 0 )
      {
        return Calc424Dim_Data8To8_Lut16(a1, a2, a1);
      }
    }
  }
  v5 = *(_DWORD *)(a1 + 24);
  v6 = *(_DWORD *)(a1 + 8);
  v7 = (unsigned int)v3[12];
  v8 = *(_DWORD *)(a1 + 16);
  v361[0] = *(_QWORD *)(a1 + 32);
  v360[0] = *(_QWORD *)(a1 + 96);
  v361[1] = *(_QWORD *)(a1 + 40);
  v360[1] = *(_QWORD *)(a1 + 104);
  v361[2] = *(_QWORD *)(a1 + 48);
  v360[2] = *(_QWORD *)(a1 + 112);
  v361[3] = *(_QWORD *)(a1 + 56);
  v360[3] = *(_QWORD *)(a1 + 120);
  v361[4] = *(_QWORD *)(a1 + 64);
  v360[4] = *(_QWORD *)(a1 + 128);
  v361[5] = *(_QWORD *)(a1 + 72);
  v360[5] = *(_QWORD *)(a1 + 136);
  v361[6] = *(_QWORD *)(a1 + 80);
  v360[6] = *(_QWORD *)(a1 + 144);
  v361[7] = *(_QWORD *)(a1 + 88);
  v9 = *(_QWORD *)(a1 + 152);
  v10 = *(_DWORD *)(a1 + 28);
  v360[7] = v9;
  v357 = v5;
  v354 = v6;
  v11 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v5), 0);
  v356 = v10;
  v323 = v5 + v8 - v6 * v5;
  v12 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v10), 0);
  v13 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v323), 0);
  v309 = v7;
  v14 = v10 + *(_DWORD *)(a1 + 20) - v6 * v10;
  v339 = v14;
  v15 = (*(_DWORD *)a1 & 0x2800) != 0;
  v16 = (*(_DWORD *)(a1 + 4) & 0x2800) != 0;
  v17 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v14), 0);
  v347 = v16;
  v316 = v15;
  if ( !(_DWORD)v7 )
    return 87;
  v18 = v3[13];
  v310 = v18;
  if ( !v18 )
    return 87;
  if ( (_DWORD)v7 == 2 )
    return 87;
  if ( v18 == 2 )
    return 87;
  if ( (unsigned int)v7 > 8 )
    return 87;
  v19 = *((_QWORD *)v3 + 5);
  v20 = *((_QWORD *)v3 + 8);
  v335 = *((_QWORD *)v3 + 11);
  v322 = *(_DWORD *)(a1 + 12);
  v358 = v19;
  v359 = *((_QWORD *)v3 + 2);
  v340 = v20;
  _mm_lfence();
  if ( v18 > 8 )
    return 87;
  v336 = 0;
  if ( *((_QWORD *)v3 + 2) )
  {
    v53 = 1;
    v325 = v3[1];
    do
    {
      if ( !((unsigned int)v3[1] >> v53) )
        break;
      v336 = v53++;
    }
    while ( v53 < 32 );
    v21 = v3[2];
    if ( !v21 )
      return 87;
    v54 = v336 - 8;
    if ( (*(_DWORD *)a1 & 0x2800) == 0 )
      v54 = 16 - v336;
    v324 = v54;
    if ( v54 < 0 )
      return 87;
    v345 = 1 << v54;
  }
  else
  {
    v325 = 0;
    v324 = 0;
    v21 = 16;
    v345 = 0;
    if ( (*(_DWORD *)a1 & 0x2800) != 0 )
      v21 = 8;
  }
  v350 = 0;
  v22 = 0;
  v351 = 0;
  if ( v2 == 4 && v335 )
  {
    if ( (_DWORD)v7 != 3 )
      return 87;
    v280 = 1;
    v326 = v3[28];
    do
    {
      if ( !((unsigned int)v3[28] >> v280) )
        break;
      v22 = v280++;
    }
    while ( v280 < 32 );
    v23 = v3[29];
    v312 = v23;
    v350 = v22;
    if ( v21 > v22 )
    {
      v317 = v21 - v22;
      v23 = v3[29];
      v351 = 1 << (v21 - v22);
    }
    else
    {
      v317 = v22 - v21;
    }
    v19 = *((_QWORD *)v3 + 5);
    v352 = (v21 > v22) + 1;
  }
  else
  {
    v326 = 0;
    v317 = 0;
    v352 = 0;
    v23 = v21;
    v312 = v21;
  }
  if ( !v20 )
  {
    v24 = v23;
    v25 = v23;
    goto LABEL_16;
  }
  if ( (unsigned int)(v2 - 3) <= 1 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)v7; i = (unsigned int)(i + 1) )
    {
      v227 = *((unsigned __int8 *)v3 + i + 96);
      v368[i] = v227;
      if ( !v227 )
        return 87;
      for ( j = 1; j < 32; ++j )
      {
        if ( !(v227 >> j) )
          break;
        v366[i] = j;
      }
    }
    goto LABEL_53;
  }
  v45 = v3[14];
  if ( !v45 )
    return 87;
  v46 = 0;
  for ( k = 1; k < 32; ++k )
  {
    if ( !(v45 >> k) )
      break;
    v46 = k;
  }
  v48 = v45;
  v49 = v368;
  for ( m = (unsigned __int64)(4 * v7) >> 2; m; --m )
    *v49++ = v48;
  v51 = v366;
  for ( n = (unsigned __int64)(4 * v7) >> 2; n; --n )
    *v51++ = v46;
LABEL_53:
  v3 = a2;
  v15 = v316;
  v24 = a2[15];
  v25 = v24 + v312;
LABEL_16:
  v327 = v24;
  LOBYTE(v320) = 0;
  v329 = 0;
  v346 = 0;
  v321 = 0;
  v333 = 0;
  v348 = 0;
  v353 = 1 << v21;
  v338 = 2;
  v318 = (1 << v21) - 1;
  if ( v2 == 3 && v335 )
  {
    v229 = 1;
    v230 = 0;
    v328 = v3[28];
    do
    {
      if ( !((unsigned int)v3[28] >> v229) )
        break;
      v230 = v229++;
    }
    while ( v229 < 32 );
    v26 = v3[29];
    v231 = v25 <= v230;
    v27 = v26;
    v320 = v230;
    v18 = v310;
    v332 = v26;
    if ( v231 )
    {
      v337 = 1;
      v319 = v320 - v25;
    }
    else
    {
      v281 = v25 - v320;
      v337 = 2;
      v282 = v281;
      if ( v281 > 16 )
        v282 = 16;
      v319 = v282;
      v329 = 1 << v282;
      v283 = v281 - 16;
      if ( v281 <= 16 )
        v283 = 0;
      v346 = v283;
    }
  }
  else
  {
    v332 = v24;
    v328 = 0;
    v26 = v24;
    v319 = 0;
    v27 = v25;
    v337 = 0;
  }
  v28 = v19 == 0;
  v355 = (1 << v26) - 1;
  v29 = a2;
  if ( v28 )
  {
    v30 = v26;
    v313 = 0;
    v330 = v26;
    v311 = 0;
    v331 = 0;
    v338 = 0;
  }
  else
  {
    v58 = 1;
    v59 = 0;
    v313 = a2[8];
    do
    {
      if ( !((unsigned int)a2[8] >> v58) )
        break;
      v59 = v58++;
    }
    while ( v58 < 32 );
    v30 = a2[9];
    v330 = v30;
    v321 = v59;
    if ( v27 <= v59 )
    {
      v338 = 1;
      v311 = v59 - v27;
      LOBYTE(v27) = v59 - v27;
    }
    else
    {
      v27 -= v59;
      v311 = v27;
      if ( v27 > 16 )
      {
        v311 = 16;
        v333 = v27 - 16;
        LOBYTE(v27) = 16;
      }
    }
    v331 = 1 << v27;
  }
  if ( v16 )
  {
    v334 = v30 - 8;
    if ( (int)(v30 - 8) > 0 )
      v348 = 1 << (v30 - 9);
  }
  else
  {
    v334 = 16 - v30;
  }
  v31 = *(_BYTE *)(a1 + 160) != 0;
  if ( (_DWORD)v7 == 8 || v18 == 8 )
    v31 = 0;
  v32 = 0;
  if ( v15 == v16 )
    v32 = v31;
  v349 = v32;
  if ( v20 )
  {
    for ( ii = 0; (unsigned int)ii < (unsigned int)v7; ii = (unsigned int)(ii + 1) )
    {
      if ( v368[ii] != 1 << v366[ii] )
        goto LABEL_27;
    }
    v61 = v312;
    for ( jj = 0; (unsigned int)jj < (unsigned int)v7; jj = (unsigned int)(jj + 1) )
    {
      v63 = v366[jj];
      v64 = v312 - v63;
      v368[jj + 16] = v312 - v63;
      if ( v312 < v63 )
        return 87;
      *((_DWORD *)&Src[4] + jj) = v63;
      v368[jj + 24] = (1 << v64) - 1;
      v367[jj + 8] = ((1 << v63) - 1) << v64;
    }
    v65 = _mm_move_epi64(v11);
    v66 = _mm_move_epi64(v12);
    v67 = _mm_move_epi64(v13);
    v68 = _mm_move_epi64(v17);
    v69 = 0;
    _mm_lfence();
    v70 = 0;
    do
    {
      v71 = v7 - v70++;
      v72 = (unsigned int)(v71 - 1);
      v368[v72 + 8] = v69;
      v69 += *((_DWORD *)&Src[4] + v72);
    }
    while ( v70 < (unsigned int)v7 );
    if ( v322 )
    {
      v73 = v349;
      while ( 1 )
      {
        v42 = v354;
        v308 = v354;
        if ( v354 )
        {
          v341 = 1 << v61;
          while ( 1 )
          {
            v74 = 0;
            if ( v15 )
            {
              do
              {
                *((_BYTE *)&v368[32] + v74) = *(_BYTE *)v361[v74];
                v74 = (unsigned int)(v74 + 1);
              }
              while ( (unsigned int)v74 < (unsigned int)v7 );
            }
            else
            {
              do
              {
                *((_WORD *)&v368[34] + v74) = *(_WORD *)v361[v74];
                v74 = (unsigned int)(v74 + 1);
              }
              while ( (unsigned int)v74 < (unsigned int)v7 );
            }
            if ( v359 )
            {
              if ( v15 )
              {
                v119 = 0;
                v120 = 0;
                do
                {
                  v121 = v119 + (*((unsigned __int8 *)&v368[32] + v120) << v324);
                  v119 += v325;
                  *((_DWORD *)Src + v120) = *(unsigned __int16 *)(v359 + 2 * v121);
                  v120 = (unsigned int)(v120 + 1);
                }
                while ( (unsigned int)v120 < (unsigned int)v7 );
                v29 = a2;
              }
              else
              {
                v75 = 0;
                v76 = 0;
                do
                {
                  v77 = *((unsigned __int16 *)&v368[34] + v76) - (*((unsigned __int16 *)&v368[34] + v76) >> v336);
                  v78 = (v77 >> v324) + v75;
                  v75 += v325;
                  *((_DWORD *)Src + v76) = (((v345 - 1) & v77)
                                          * *(unsigned __int16 *)(v359 + 2LL * (unsigned int)(v78 + 1))
                                          + (v345 - ((v345 - 1) & v77)) * *(unsigned __int16 *)(v359 + 2 * v78)) >> v324;
                  v76 = (unsigned int)(v76 + 1);
                }
                while ( (unsigned int)v76 < (unsigned int)v7 );
                v42 = v308;
                v29 = a2;
              }
            }
            else
            {
              v118 = 0;
              if ( v15 )
              {
                if ( (unsigned int)v7 < 2 )
                  goto LABEL_466;
                do
                {
                  *(_QWORD *)((char *)Src + 4 * v118) = _mm_unpacklo_epi16(
                                                          _mm_unpacklo_epi8(
                                                            _mm_cvtsi32_si128(*(unsigned __int16 *)((char *)&v368[32]
                                                                                                  + v118)),
                                                            (__m128i)0LL),
                                                          (__m128i)0LL).m128i_u64[0];
                  v118 = (unsigned int)(v118 + 2);
                }
                while ( (unsigned int)v118 < ((unsigned int)v7 & 0xFFFFFFFE) );
                if ( (unsigned int)v118 < (unsigned int)v7 )
                {
LABEL_466:
                  do
                  {
                    *((_DWORD *)Src + v118) = *((unsigned __int8 *)&v368[32] + v118);
                    v118 = (unsigned int)(v118 + 1);
                  }
                  while ( (unsigned int)v118 < (unsigned int)v7 );
                }
              }
              else
              {
                if ( (unsigned int)v7 < 2 )
                  goto LABEL_467;
                do
                {
                  *(_QWORD *)((char *)Src + 4 * v118) = _mm_unpacklo_epi16(
                                                          _mm_cvtsi32_si128(*(_DWORD *)((char *)&v368[34] + 2 * v118)),
                                                          (__m128i)0LL).m128i_u64[0];
                  v118 = (unsigned int)(v118 + 2);
                }
                while ( (unsigned int)v118 < ((unsigned int)v7 & 0xFFFFFFFE) );
                if ( (unsigned int)v118 < (unsigned int)v7 )
                {
LABEL_467:
                  do
                  {
                    *((_DWORD *)Src + v118) = *((unsigned __int16 *)&v368[34] + v118);
                    v118 = (unsigned int)(v118 + 1);
                  }
                  while ( (unsigned int)v118 < (unsigned int)v7 );
                }
              }
            }
            if ( *v29 == 4 && v335 )
            {
              v79 = v318;
              v122 = *((_QWORD *)v29 + 15);
              v123 = 0;
              do
              {
                v124 = *(double *)(v122 + 8 * v123 + 72);
                v125 = 0;
                v126 = 0;
                v127 = (double)(int)v318;
                do
                {
                  v128 = (double)*((int *)Src + v126) * *(double *)(v122 + 24 * v123 + 8 * v126);
                  v126 = (unsigned int)(v126 + 1);
                  v129 = v128 / v127;
                  v127 = (double)(int)v318;
                  v124 = v124 + v129;
                }
                while ( (unsigned int)v126 < (unsigned int)v7 );
                v130 = v124 * (double)(int)v318;
                if ( v130 > 0.0 )
                {
                  v125 = (int)(v130 + 0.5);
                  if ( v125 > v318 )
                    v125 = v318;
                }
                v364[v123] = v125;
                v123 = (unsigned int)(v123 + 1);
              }
              while ( (unsigned int)v123 < (unsigned int)v7 );
              if ( v352 == 1 )
              {
                v137 = 0;
                v138 = 0;
                do
                {
                  v139 = (unsigned int)(v137 + (v364[v138] << v317));
                  v137 += v326;
                  v363[v138] = *(unsigned __int16 *)(v335 + 2 * v139);
                  v138 = (unsigned int)(v138 + 1);
                }
                while ( (unsigned int)v138 < (unsigned int)v7 );
                v29 = a2;
              }
              else
              {
                v131 = 0;
                v132 = 0;
                do
                {
                  v133 = v364[v132] - (v364[v132] >> v350);
                  v134 = (v133 >> v317) + v131;
                  v131 += v326;
                  v363[v132] = (((v351 - 1) & v133) * *(unsigned __int16 *)(v335 + 2LL * (unsigned int)(v134 + 1))
                              + (v351 - ((v351 - 1) & v133)) * *(unsigned __int16 *)(v335 + 2 * v134)) >> v317;
                  v132 = (unsigned int)(v132 + 1);
                }
                while ( (unsigned int)v132 < (unsigned int)v7 );
                v42 = v308;
                v79 = v318;
                v29 = a2;
              }
            }
            else
            {
              memcpy_0(v363, Src, 4LL * (unsigned int)v7);
              v79 = v318;
            }
            v80 = 0;
            v81 = 0;
            do
            {
              v82 = (v368[v81] - 1) * (v363[v81] * v353 / v79) / v368[v81];
              v83 = v368[v81 + 16];
              v84 = v82 & v368[v81 + 24];
              *((_WORD *)&v368[38] + v81) = v82;
              v366[v81] = v84 << (v312 - v83);
              v85 = (v82 & v367[v81 + 8]) >> v83;
              v86 = v368[v81 + 8];
              v81 = (unsigned int)(v81 + 1);
              v80 |= v85 << v86;
            }
            while ( (unsigned int)v81 < (unsigned int)v7 );
            v87 = 0;
            v88 = *v29;
            v89 = v80 * v310;
            do
            {
              *((_DWORD *)&Src[4] + v87) = v87;
              v87 = (unsigned int)(v87 + 1);
            }
            while ( (unsigned int)v87 < (unsigned int)v7 );
            v90 = v7;
            while ( 1 )
            {
              v90 = (12 * v90) >> 4;
              if ( !v90 )
                v90 = 1;
              v91 = 0;
              v92 = 0;
              if ( (_DWORD)v7 == v90 )
                goto LABEL_110;
              do
              {
                v93 = *((int *)&Src[4] + v90 + v92);
                v94 = *((int *)&Src[4] + v92);
                if ( v366[v94] < v366[v93] )
                {
                  *((_DWORD *)&Src[4] + v92) = v93;
                  v91 = 1;
                  *((_DWORD *)&Src[4] + v90 + v92) = v94;
                }
                ++v92;
              }
              while ( v92 < (unsigned int)v7 - v90 );
              LODWORD(v7) = v309;
              if ( !v91 )
              {
LABEL_110:
                if ( v90 <= 1 )
                  break;
              }
            }
            v18 = v310;
            v95 = 0;
            do
              ++v95;
            while ( v95 < v310 );
            memset_0(v362, 0, 4LL * v310);
            v96 = v341;
            v97 = 0;
            v98 = 0;
            v99 = v89;
            if ( v327 == 16 )
            {
              do
              {
                v100 = *((unsigned int *)&Src[4] + v98);
                v101 = v96 - v366[v100];
                v96 = v366[v100];
                if ( (unsigned int)*((unsigned __int16 *)&v368[38] + v100) < v367[v100 + 8] )
                  v97 |= 1 << v368[v100 + 8];
                v102 = 0;
                do
                {
                  v362[v102] += v101 * *(unsigned __int16 *)(v340 + 2LL * (unsigned int)(v89 + v102));
                  v102 = (unsigned int)(v102 + 1);
                }
                while ( (unsigned int)v102 < v310 );
                v98 = (unsigned int)(v98 + 1);
                v89 = v99 + v310 * v97;
              }
              while ( (unsigned int)v98 < v309 );
              v103 = 0;
              do
              {
                v362[v103] += v96 * *(unsigned __int16 *)(v340 + 2LL * (unsigned int)(v89 + v103));
                v103 = (unsigned int)(v103 + 1);
              }
              while ( (unsigned int)v103 < v310 );
            }
            else
            {
              do
              {
                v232 = *((unsigned int *)&Src[4] + v98);
                v233 = v96 - v366[v232];
                v96 = v366[v232];
                if ( (unsigned int)*((unsigned __int16 *)&v368[38] + v232) < v367[v232 + 8] )
                  v97 |= 1 << v368[v232 + 8];
                v234 = 0;
                do
                {
                  v362[v234] += v233 * *(unsigned __int8 *)((unsigned int)(v89 + v234) + v340);
                  v234 = (unsigned int)(v234 + 1);
                }
                while ( (unsigned int)v234 < v310 );
                v98 = (unsigned int)(v98 + 1);
                v89 = v99 + v310 * v97;
              }
              while ( (unsigned int)v98 < v309 );
              v235 = 0;
              do
              {
                v362[v235] += v96 * *(unsigned __int8 *)((unsigned int)(v89 + v235) + v340);
                v235 = (unsigned int)(v235 + 1);
              }
              while ( (unsigned int)v235 < v310 );
            }
            LODWORD(v7) = v309;
            if ( v88 == 3 && *((_QWORD *)a2 + 11) )
            {
              v344 = *((_QWORD *)a2 + 15);
              if ( v337 == 1 )
              {
                v256 = 0;
                v257 = 0;
                do
                {
                  v258 = (unsigned int)(v256 + (v362[v257] << v319));
                  v256 += v328;
                  v363[v257] = *(unsigned __int16 *)(v335 + 2 * v258);
                  v257 = (unsigned int)(v257 + 1);
                }
                while ( (unsigned int)v257 < v310 );
              }
              else
              {
                v238 = 0;
                v239 = 0;
                do
                {
                  v240 = (v362[v239] + (v362[v239] >> v327) - ((unsigned int)(v362[v239] + (v362[v239] >> v327)) >> v320)) >> v346;
                  v241 = (v240 >> v319) + v238;
                  v238 += v328;
                  v363[v239] = (((v329 - 1) & v240) * *(unsigned __int16 *)(v335 + 2LL * (unsigned int)(v241 + 1))
                              + (v329 - ((v329 - 1) & v240)) * *(unsigned __int16 *)(v335 + 2 * v241)) >> v319;
                  v239 = (unsigned int)(v239 + 1);
                }
                while ( (unsigned int)v239 < v310 );
              }
              v242 = 0;
              v42 = v308;
              LODWORD(v7) = v309;
              v243 = 0;
              v244 = (double)v355;
              do
              {
                v245 = *(double *)(v344 + 8 * v243 + 72);
                v246 = 0;
                v247 = 0;
                v248 = (double)v355;
                if ( v310 < 2 )
                  goto LABEL_341;
                v259 = v344 + 24 * v243;
                do
                {
                  v260 = (unsigned int)(v247 + 1);
                  v261 = (double)(int)v363[v247] * *(double *)(v259 + 8 * v247);
                  v247 = (unsigned int)(v247 + 2);
                  v262 = v261 / v248;
                  v248 = (double)v355;
                  v245 = v245 + v262 + (double)(int)v363[v260] * *(double *)(v259 + 8 * v260) / v244;
                }
                while ( (unsigned int)v247 < v310 - 1 );
                if ( (unsigned int)v247 < v310 )
LABEL_341:
                  v245 = v245 + (double)(int)v363[v247] * *(double *)(v344 + 8 * ((unsigned int)v247 + 3 * v243)) / v248;
                v249 = v245 * v244;
                if ( v249 > 0.0 )
                {
                  v246 = (int)(v249 + 0.5);
                  if ( v246 > v355 )
                    v246 = v355;
                }
                ++v242;
                v364[v243++] = v246;
              }
              while ( v242 < v310 );
            }
            else
            {
              memcpy_0(v364, v362, 4LL * v310);
            }
            if ( v358 )
            {
              if ( v338 == 1 )
              {
                v252 = 0;
                v253 = 0;
                if ( v330 <= 8 )
                {
                  do
                  {
                    v255 = (unsigned int)(v253 + (v364[v252] << v311));
                    v253 += v313;
                    v367[v252] = *(unsigned __int8 *)(v255 + v358);
                    v252 = (unsigned int)(v252 + 1);
                  }
                  while ( (unsigned int)v252 < v310 );
                  LODWORD(v7) = v309;
                  v42 = v308;
                }
                else
                {
                  do
                  {
                    v254 = (unsigned int)(v253 + (v364[v252] << v311));
                    v253 += v313;
                    v367[v252] = *(unsigned __int16 *)(v358 + 2 * v254);
                    v252 = (unsigned int)(v252 + 1);
                  }
                  while ( (unsigned int)v252 < v310 );
                  LODWORD(v7) = v309;
                  v42 = v308;
                }
              }
              else
              {
                v104 = 0;
                v105 = 0;
                v106 = v331 - 1;
                if ( v330 <= 8 )
                {
                  do
                  {
                    v236 = (v364[v104]
                          + (v364[v104] >> v332)
                          - ((unsigned int)(v364[v104] + (v364[v104] >> v332)) >> v321)) >> v333;
                    v237 = (v236 >> v311) + v105;
                    v105 += v313;
                    v367[v104] = ((v106 & v236) * *(unsigned __int8 *)((unsigned int)(v237 + 1) + v358)
                                + (v331 - (v106 & v236)) * *(unsigned __int8 *)(v237 + v358)) >> v311;
                    v104 = (unsigned int)(v104 + 1);
                  }
                  while ( (unsigned int)v104 < v310 );
                  LODWORD(v7) = v309;
                  v42 = v308;
                }
                else
                {
                  do
                  {
                    v107 = (v364[v104]
                          + (v364[v104] >> v332)
                          - ((unsigned int)(v364[v104] + (v364[v104] >> v332)) >> v321)) >> v333;
                    v108 = (v107 >> v311) + v105;
                    v105 += v313;
                    v367[v104] = ((v106 & v107) * *(unsigned __int16 *)(v358 + 2LL * (unsigned int)(v108 + 1))
                                + (v331 - (v106 & v107)) * *(unsigned __int16 *)(v358 + 2 * v108)) >> v311;
                    v104 = (unsigned int)(v104 + 1);
                  }
                  while ( (unsigned int)v104 < v310 );
                  LODWORD(v7) = v309;
                  v42 = v308;
                }
              }
            }
            else
            {
              memcpy_0(v367, v364, 4LL * v310);
            }
            v109 = 0;
            if ( v347 )
            {
              do
              {
                v110 = (_BYTE *)v360[v109];
                v111 = (unsigned int)(v348 + v367[v109]) >> v334;
                if ( v111 > 0xFF )
                  LOBYTE(v111) = -1;
                v109 = (unsigned int)(v109 + 1);
                *v110 = v111;
              }
              while ( (unsigned int)v109 < v310 );
            }
            else
            {
              do
              {
                v263 = v367[v109];
                v264 = (_WORD *)v360[v109];
                v109 = (unsigned int)(v109 + 1);
                *v264 = v263 << v334;
              }
              while ( (unsigned int)v109 < v310 );
            }
            v73 = v349;
            if ( v349 )
            {
              v250 = (_BYTE *)v360[v310];
              v251 = (_BYTE *)v361[(unsigned int)v7];
              if ( v347 )
                *v250 = *v251;
              else
                *(_WORD *)v250 = *(_WORD *)v251;
            }
            v308 = --v42;
            if ( !v42 )
              break;
LABEL_134:
            v112 = 0;
            if ( (unsigned int)v7 < 8 )
              goto LABEL_468;
            v113 = _mm_unpacklo_epi32(_mm_move_epi64(v65), (__m128i)0LL);
            do
            {
              *(__m128i *)&v361[v112] = _mm_add_epi64(_mm_loadu_si128((const __m128i *)&v361[v112]), v113);
              *(__m128i *)&v361[(unsigned int)(v112 + 2)] = _mm_add_epi64(
                                                              v113,
                                                              _mm_loadu_si128((const __m128i *)&v361[(unsigned int)(v112 + 2)]));
              *(__m128i *)&v361[(unsigned int)(v112 + 4)] = _mm_add_epi64(
                                                              _mm_loadu_si128((const __m128i *)&v361[(unsigned int)(v112 + 4)]),
                                                              v113);
              v114 = (unsigned int)(v112 + 6);
              v112 = (unsigned int)(v112 + 8);
              *(__m128i *)&v361[v114] = _mm_add_epi64(v113, _mm_loadu_si128((const __m128i *)&v361[v114]));
            }
            while ( (unsigned int)v112 < ((unsigned int)v7 & 0xFFFFFFF8) );
            if ( (unsigned int)v112 >= (unsigned int)v7 )
            {
              v308 = v42;
            }
            else
            {
LABEL_468:
              do
              {
                v361[v112] += v357;
                v112 = (unsigned int)(v112 + 1);
              }
              while ( (unsigned int)v112 < (unsigned int)v7 );
            }
            v115 = 0;
            if ( v310 < 8 )
              goto LABEL_469;
            v116 = _mm_unpacklo_epi32(_mm_move_epi64(v66), (__m128i)0LL);
            do
            {
              *(__m128i *)&v360[v115] = _mm_add_epi64(v116, _mm_loadu_si128((const __m128i *)&v360[v115]));
              *(__m128i *)&v360[(unsigned int)(v115 + 2)] = _mm_add_epi64(
                                                              v116,
                                                              _mm_loadu_si128((const __m128i *)&v360[(unsigned int)(v115 + 2)]));
              *(__m128i *)&v360[(unsigned int)(v115 + 4)] = _mm_add_epi64(
                                                              v116,
                                                              _mm_loadu_si128((const __m128i *)&v360[(unsigned int)(v115 + 4)]));
              v117 = (unsigned int)(v115 + 6);
              v115 = (unsigned int)(v115 + 8);
              *(__m128i *)&v360[v117] = _mm_add_epi64(v116, _mm_loadu_si128((const __m128i *)&v360[v117]));
            }
            while ( (unsigned int)v115 < (v310 & 0xFFFFFFF8) );
            if ( (unsigned int)v115 < v310 )
            {
LABEL_469:
              do
              {
                v360[v115] += v356;
                v115 = (unsigned int)(v115 + 1);
              }
              while ( (unsigned int)v115 < v310 );
            }
            if ( v349 )
            {
              v361[(unsigned int)v7] += v357;
              v360[v310] += v356;
            }
            v39 = 0;
            if ( v316 )
            {
              while ( *(_BYTE *)v361[v39] == *((_BYTE *)&v368[32] + v39) )
              {
                v39 = (unsigned int)(v39 + 1);
                if ( (unsigned int)v39 >= (unsigned int)v7 )
                  goto LABEL_31;
              }
            }
            else
            {
              while ( *(_WORD *)v361[v39] == *((_WORD *)&v368[34] + v39) )
              {
                v39 = (unsigned int)(v39 + 1);
                if ( (unsigned int)v39 >= (unsigned int)v7 )
                {
LABEL_31:
                  v40 = 0;
                  if ( v347 )
                  {
                    do
                    {
                      v44 = (_BYTE *)v360[v40];
                      v40 = (unsigned int)(v40 + 1);
                      *v44 = v44[-v356];
                    }
                    while ( (unsigned int)v40 < v310 );
                    if ( v349 )
                    {
                      _mm_lfence();
                      *(_BYTE *)v360[v310] = *(_BYTE *)v361[(unsigned int)v7];
                    }
                  }
                  else
                  {
                    do
                    {
                      v41 = (_WORD *)v360[v40];
                      v40 = (unsigned int)(v40 + 1);
                      *v41 = *(_WORD *)((char *)v41 - (int)v356);
                    }
                    while ( (unsigned int)v40 < v310 );
                    if ( v349 )
                    {
                      _mm_lfence();
                      *(_WORD *)v360[v310] = *(_WORD *)v361[(unsigned int)v7];
                    }
                  }
                  v28 = v42-- == 1;
                  v308 = v42;
                  if ( !v28 )
                    goto LABEL_134;
                  goto LABEL_36;
                }
              }
            }
            v29 = a2;
            v15 = v316;
          }
LABEL_36:
          v15 = v316;
        }
        if ( !--v322 )
          break;
        v272 = 0;
        if ( (unsigned int)v7 < 8 )
          goto LABEL_382;
        v276 = _mm_unpacklo_epi32(_mm_move_epi64(v67), (__m128i)0LL);
        do
        {
          *(__m128i *)&v361[v272] = _mm_add_epi64(v276, _mm_loadu_si128((const __m128i *)&v361[v272]));
          *(__m128i *)&v361[(unsigned int)(v272 + 2)] = _mm_add_epi64(
                                                          v276,
                                                          _mm_loadu_si128((const __m128i *)&v361[(unsigned int)(v272 + 2)]));
          *(__m128i *)&v361[(unsigned int)(v272 + 4)] = _mm_add_epi64(
                                                          v276,
                                                          _mm_loadu_si128((const __m128i *)&v361[(unsigned int)(v272 + 4)]));
          v277 = (unsigned int)(v272 + 6);
          v272 = (unsigned int)(v272 + 8);
          *(__m128i *)&v361[v277] = _mm_add_epi64(v276, _mm_loadu_si128((const __m128i *)&v361[v277]));
        }
        while ( (unsigned int)v272 < ((unsigned int)v7 & 0xFFFFFFF8) );
        if ( (unsigned int)v272 < (unsigned int)v7 )
        {
LABEL_382:
          v273 = v323;
          do
          {
            v361[v272] += v323;
            v272 = (unsigned int)(v272 + 1);
          }
          while ( (unsigned int)v272 < (unsigned int)v7 );
        }
        else
        {
          v273 = v323;
        }
        v274 = 0;
        if ( v18 < 8 )
          goto LABEL_385;
        v274 = 0;
        v278 = _mm_unpacklo_epi32(_mm_move_epi64(v68), (__m128i)0LL);
        do
        {
          *(__m128i *)&v360[v274] = _mm_add_epi64(v278, _mm_loadu_si128((const __m128i *)&v360[v274]));
          *(__m128i *)&v360[(unsigned int)(v274 + 2)] = _mm_add_epi64(
                                                          v278,
                                                          _mm_loadu_si128((const __m128i *)&v360[(unsigned int)(v274 + 2)]));
          *(__m128i *)&v360[(unsigned int)(v274 + 4)] = _mm_add_epi64(
                                                          v278,
                                                          _mm_loadu_si128((const __m128i *)&v360[(unsigned int)(v274 + 4)]));
          v279 = (unsigned int)(v274 + 6);
          v274 = (unsigned int)(v274 + 8);
          *(__m128i *)&v360[v279] = _mm_add_epi64(v278, _mm_loadu_si128((const __m128i *)&v360[v279]));
        }
        while ( (unsigned int)v274 < (v18 & 0xFFFFFFF8) );
        if ( (unsigned int)v274 < v18 )
        {
LABEL_385:
          v275 = v339;
          do
          {
            v360[v274] += v339;
            v274 = (unsigned int)(v274 + 1);
          }
          while ( (unsigned int)v274 < v18 );
        }
        else
        {
          v275 = v339;
        }
        v29 = a2;
        v61 = v312;
        if ( v73 )
        {
          v361[(unsigned int)v7] += v273;
          v360[v18] += v275;
        }
      }
    }
  }
  else
  {
LABEL_27:
    v33 = _mm_move_epi64(v11);
    v34 = 1 << v312;
    v35 = _mm_move_epi64(v12);
    v36 = _mm_move_epi64(v13);
    v307 = 1 << v312;
    v37 = _mm_move_epi64(v17);
    v38 = (1 << v312) - 1;
    if ( v20 )
    {
      v140 = v18;
      v141 = 0;
      do
      {
        v142 = v7 - v141++;
        v143 = (unsigned int)(v142 - 1);
        v366[v143] = v140;
        v140 *= v368[v143];
      }
      while ( v141 < (unsigned int)v7 );
    }
    if ( v322 )
    {
      v144 = v310;
      v145 = v7;
      while ( 1 )
      {
        v146 = v354;
        v314 = v354;
        if ( v354 )
        {
          while ( 1 )
          {
            v147 = 0;
            if ( v15 )
            {
              do
              {
                *((_BYTE *)&v368[32] + v147) = *(_BYTE *)v361[v147];
                v147 = (unsigned int)(v147 + 1);
              }
              while ( (unsigned int)v147 < v145 );
            }
            else
            {
              do
              {
                *((_WORD *)&v368[34] + v147) = *(_WORD *)v361[v147];
                v147 = (unsigned int)(v147 + 1);
              }
              while ( (unsigned int)v147 < v145 );
            }
            if ( v359 )
            {
              if ( v15 )
              {
                v284 = 0;
                v285 = 0;
                do
                {
                  v286 = v284 + (*((unsigned __int8 *)&v368[32] + v285) << v324);
                  v284 += v325;
                  *((_DWORD *)Src + v285) = *(unsigned __int16 *)(v359 + 2 * v286);
                  v285 = (unsigned int)(v285 + 1);
                }
                while ( (unsigned int)v285 < v145 );
                v34 = 1 << v312;
                v38 = v307 - 1;
              }
              else
              {
                v148 = 0;
                v149 = 0;
                do
                {
                  v150 = *((unsigned __int16 *)&v368[34] + v149) - (*((unsigned __int16 *)&v368[34] + v149) >> v336);
                  v151 = (v150 >> v324) + v148;
                  v148 += v325;
                  *((_DWORD *)Src + v149) = ((v150 & (v345 - 1))
                                           * *(unsigned __int16 *)(v359 + 2LL * (unsigned int)(v151 + 1))
                                           + (v345 - (v150 & (v345 - 1))) * *(unsigned __int16 *)(v359 + 2 * v151)) >> v324;
                  v149 = (unsigned int)(v149 + 1);
                }
                while ( (unsigned int)v149 < v145 );
                v34 = 1 << v312;
                v146 = v314;
                v38 = (1 << v312) - 1;
              }
            }
            else
            {
              v213 = 0;
              if ( v15 )
              {
                if ( v145 < 2 )
                  goto LABEL_470;
                do
                {
                  *(_QWORD *)((char *)Src + 4 * v213) = _mm_unpacklo_epi16(
                                                          _mm_unpacklo_epi8(
                                                            _mm_cvtsi32_si128(*(unsigned __int16 *)((char *)&v368[32]
                                                                                                  + v213)),
                                                            (__m128i)0LL),
                                                          (__m128i)0LL).m128i_u64[0];
                  v213 = (unsigned int)(v213 + 2);
                }
                while ( (unsigned int)v213 < (v145 & 0xFFFFFFFE) );
                if ( (unsigned int)v213 < v145 )
                {
LABEL_470:
                  do
                  {
                    *((_DWORD *)Src + v213) = *((unsigned __int8 *)&v368[32] + v213);
                    v213 = (unsigned int)(v213 + 1);
                  }
                  while ( (unsigned int)v213 < v145 );
                }
              }
              else
              {
                if ( v145 < 2 )
                  goto LABEL_471;
                do
                {
                  *(_QWORD *)((char *)Src + 4 * v213) = _mm_unpacklo_epi16(
                                                          _mm_cvtsi32_si128(*(_DWORD *)((char *)&v368[34] + 2 * v213)),
                                                          (__m128i)0LL).m128i_u64[0];
                  v213 = (unsigned int)(v213 + 2);
                }
                while ( (unsigned int)v213 < (v145 & 0xFFFFFFFE) );
                if ( (unsigned int)v213 < v145 )
                {
LABEL_471:
                  do
                  {
                    *((_DWORD *)Src + v213) = *((unsigned __int16 *)&v368[34] + v213);
                    v213 = (unsigned int)(v213 + 1);
                  }
                  while ( (unsigned int)v213 < v145 );
                }
              }
            }
            v152 = a2;
            v153 = *a2;
            v342 = *a2;
            if ( *a2 == 4 && v335 )
            {
              v216 = *((_QWORD *)a2 + 15);
              v217 = 0;
              v218 = (double)(int)v318;
              do
              {
                v219 = *(double *)(v216 + 8 * v217 + 72);
                v220 = 0;
                v221 = 0;
                do
                {
                  v222 = (double)*((int *)Src + v221) * *(double *)(v216 + 24 * v217 + 8 * v221);
                  v221 = (unsigned int)(v221 + 1);
                  v219 = v219 + v222 / v218;
                }
                while ( (unsigned int)v221 < v145 );
                if ( v218 * v219 > 0.0 )
                {
                  v220 = (int)(v218 * v219 + 0.5);
                  if ( v220 > v318 )
                    v220 = v318;
                }
                v364[v217] = v220;
                v217 = (unsigned int)(v217 + 1);
              }
              while ( (unsigned int)v217 < v145 );
              if ( v352 == 1 )
              {
                v223 = 0;
                v224 = 0;
                do
                {
                  v225 = (unsigned int)(v223 + (v364[v224] << v317));
                  v223 += v326;
                  v363[v224] = *(unsigned __int16 *)(v335 + 2 * v225);
                  v224 = (unsigned int)(v224 + 1);
                }
                while ( (unsigned int)v224 < v145 );
                v34 = 1 << v312;
                v38 = (1 << v312) - 1;
                v152 = a2;
              }
              else
              {
                v287 = 0;
                v288 = 0;
                do
                {
                  v289 = v364[v288] - (v364[v288] >> v350);
                  v290 = (v289 >> v317) + v287;
                  v287 += v326;
                  v363[v288] = ((v289 & (v351 - 1)) * *(unsigned __int16 *)(v335 + 2LL * (unsigned int)(v290 + 1))
                              + (v351 - (v289 & (v351 - 1))) * *(unsigned __int16 *)(v335 + 2 * v290)) >> v317;
                  v288 = (unsigned int)(v288 + 1);
                }
                while ( (unsigned int)v288 < v145 );
                v34 = 1 << v312;
                v153 = 4;
                v146 = v314;
                v152 = a2;
                v38 = v307 - 1;
              }
            }
            else
            {
              memcpy_0(v363, Src, 4LL * v145);
            }
            if ( v340 )
            {
              v180 = 0;
              v181 = 0;
              v182 = 0;
              if ( v145 < 2 )
                goto LABEL_254;
              do
              {
                v202 = (unsigned int)(v182 + 1);
                v203 = (v368[v182] - 1) * (v363[v182] * v353 / v318);
                v367[v182 + 8] = v38 & v203;
                *((_WORD *)&v368[38] + v182) = v203 >> v312;
                v204 = v366[v182] * (v203 >> v312);
                v182 = (unsigned int)(v182 + 2);
                v180 += v204;
                v205 = (v368[v202] - 1) * (v363[v202] * v353 / v318);
                v367[v202 + 8] = v38 & v205;
                v206 = v205 >> v312;
                *((_WORD *)&v368[38] + v202) = v206;
                v181 += v366[v202] * v206;
              }
              while ( (unsigned int)v182 < v145 - 1 );
              v153 = v342;
              v34 = 1 << v312;
              if ( (unsigned int)v182 < v145 )
              {
LABEL_254:
                v183 = (v368[v182] - 1) * (v363[v182] * v353 / v318);
                v367[v182 + 8] = v38 & v183;
                v184 = v183 >> v312;
                *((_WORD *)&v368[38] + v182) = v184;
                v185 = v180 + v181 + v366[v182] * v184;
              }
              else
              {
                v185 = v181 + v180;
              }
              v186 = 0;
              v187 = v145;
              do
              {
                *((_DWORD *)&Src[4] + v186) = v186;
                v186 = (unsigned int)(v186 + 1);
              }
              while ( (unsigned int)v186 < v145 );
              v188 = v309;
              while ( 1 )
              {
                v187 = (12 * v187) >> 4;
                if ( !v187 )
                  v187 = 1;
                v189 = 0;
                v190 = 0;
                if ( v188 == v187 )
                  goto LABEL_265;
                do
                {
                  v191 = *((int *)&Src[4] + v187 + v190);
                  v192 = *((int *)&Src[4] + v190);
                  if ( v367[v192 + 8] < v367[v191 + 8] )
                  {
                    *((_DWORD *)&Src[4] + v190) = v191;
                    v189 = 1;
                    *((_DWORD *)&Src[4] + v187 + v190) = v192;
                  }
                  ++v190;
                }
                while ( v190 < v188 - v187 );
                v153 = v342;
                v188 = v309;
                if ( !v189 )
                {
LABEL_265:
                  if ( v187 <= 1 )
                    break;
                }
              }
              v193 = 0;
              do
                ++v193;
              while ( v193 < v310 );
              memset_0(v362, 0, 4LL * v310);
              v194 = 0;
              v195 = v34;
              if ( v327 == 16 )
              {
                v196 = 0;
                v197 = v185;
                do
                {
                  v198 = *((unsigned int *)&Src[4] + v196);
                  v199 = v195 - v367[v198 + 8];
                  v195 = v367[v198 + 8];
                  if ( *((_WORD *)&v368[38] + v198) < (unsigned __int16)(LOWORD(v368[v198]) - 1) )
                    v194 += v366[v198];
                  v200 = 0;
                  do
                  {
                    v362[v200] += v199 * *(unsigned __int16 *)(v340 + 2LL * (unsigned int)(v185 + v200));
                    v200 = (unsigned int)(v200 + 1);
                  }
                  while ( (unsigned int)v200 < v310 );
                  v196 = (unsigned int)(v196 + 1);
                  v185 = v194 + v197;
                }
                while ( (unsigned int)v196 < v309 );
                v201 = 0;
                do
                {
                  v362[v201] += v195 * *(unsigned __int16 *)(v340 + 2LL * (unsigned int)(v185 + v201));
                  v201 = (unsigned int)(v201 + 1);
                }
                while ( (unsigned int)v201 < v310 );
                v34 = 1 << v312;
                v145 = v309;
                v152 = a2;
              }
              else
              {
                v207 = 0;
                v208 = v185;
                do
                {
                  v209 = *((unsigned int *)&Src[4] + v207);
                  v210 = v195 - v367[v209 + 8];
                  v195 = v367[v209 + 8];
                  if ( *((_WORD *)&v368[38] + v209) < (unsigned __int16)(LOWORD(v368[v209]) - 1) )
                    v194 += v366[v209];
                  v211 = 0;
                  do
                  {
                    v362[v211] += v210 * *(unsigned __int8 *)((unsigned int)(v185 + v211) + v340);
                    v211 = (unsigned int)(v211 + 1);
                  }
                  while ( (unsigned int)v211 < v310 );
                  v207 = (unsigned int)(v207 + 1);
                  v185 = v194 + v208;
                }
                while ( (unsigned int)v207 < v309 );
                v212 = 0;
                do
                {
                  v362[v212] += v195 * *(unsigned __int8 *)((unsigned int)(v185 + v212) + v340);
                  v212 = (unsigned int)(v212 + 1);
                }
                while ( (unsigned int)v212 < v310 );
                v34 = 1 << v312;
                v145 = v309;
                v152 = a2;
              }
            }
            else
            {
              memcpy_0(v362, v363, 4LL * v310);
            }
            if ( v153 == 3 && *((_QWORD *)v152 + 11) )
            {
              v144 = v310;
              v343 = *((_QWORD *)v152 + 15);
              if ( v337 == 1 )
              {
                v291 = 0;
                v292 = 0;
                do
                {
                  v293 = (unsigned int)(v291 + (v362[v292] << v319));
                  v291 += v328;
                  v363[v292] = *(unsigned __int16 *)(v335 + 2 * v293);
                  v292 = (unsigned int)(v292 + 1);
                }
                while ( (unsigned int)v292 < v310 );
              }
              else
              {
                v163 = 0;
                v164 = 0;
                do
                {
                  v165 = (v362[v164] + (v362[v164] >> v327) - ((unsigned int)(v362[v164] + (v362[v164] >> v327)) >> v320)) >> v346;
                  v166 = (v165 >> v319) + v163;
                  v163 += v328;
                  v363[v164] = (((v329 - 1) & v165) * *(unsigned __int16 *)(v335 + 2LL * (unsigned int)(v166 + 1))
                              + (v329 - ((v329 - 1) & v165)) * *(unsigned __int16 *)(v335 + 2 * v166)) >> v319;
                  v164 = (unsigned int)(v164 + 1);
                }
                while ( (unsigned int)v164 < v310 );
              }
              v145 = v309;
              v167 = 0;
              v146 = v314;
              v168 = (double)v355;
              do
              {
                v169 = *(double *)(v343 + 8 * v167 + 72);
                v170 = 0;
                v171 = 0;
                if ( v310 < 2 )
                  goto LABEL_239;
                v173 = v343 + 24 * v167;
                do
                {
                  v174 = (unsigned int)(v171 + 1);
                  v175 = (double)(int)v363[v171] * *(double *)(v173 + 8 * v171);
                  v171 = (unsigned int)(v171 + 2);
                  v169 = v169 + v175 / v168 + (double)(int)v363[v174] * *(double *)(v173 + 8 * v174) / v168;
                }
                while ( (unsigned int)v171 < v310 - 1 );
                if ( (unsigned int)v171 < v310 )
LABEL_239:
                  v169 = v169
                       + (double)(int)v363[v171]
                       * *(double *)(v343 + 8 * ((unsigned int)v171 + 3LL * (unsigned int)v167))
                       / v168;
                v172 = v169 * v168;
                if ( v172 > 0.0 )
                {
                  v170 = (int)(v172 + 0.5);
                  if ( v170 > v355 )
                    v170 = v355;
                }
                v364[v167] = v170;
                v167 = (unsigned int)(v167 + 1);
              }
              while ( (unsigned int)v167 < v310 );
              v34 = 1 << v312;
            }
            else
            {
              v144 = v310;
              memcpy_0(v364, v362, 4LL * v310);
            }
            if ( v358 )
            {
              if ( v338 == 1 )
              {
                v294 = 0;
                v295 = 0;
                if ( v330 > 8 )
                {
                  do
                  {
                    v297 = (unsigned int)(v295 + (v364[v294] << v311));
                    v295 += v313;
                    v367[v294] = *(unsigned __int16 *)(v358 + 2 * v297);
                    v294 = (unsigned int)(v294 + 1);
                  }
                  while ( (unsigned int)v294 < v144 );
                  v34 = 1 << v312;
                  v145 = v309;
                }
                else
                {
                  do
                  {
                    v296 = (unsigned int)(v295 + (v364[v294] << v311));
                    v295 += v313;
                    v367[v294] = *(unsigned __int8 *)(v296 + v358);
                    v294 = (unsigned int)(v294 + 1);
                  }
                  while ( (unsigned int)v294 < v144 );
                  v34 = 1 << v312;
                  v145 = v309;
                }
              }
              else
              {
                v176 = 0;
                v177 = 0;
                if ( v330 <= 8 )
                {
                  do
                  {
                    v214 = (v364[v176]
                          + (v364[v176] >> v332)
                          - ((unsigned int)(v364[v176] + (v364[v176] >> v332)) >> v321)) >> v333;
                    v215 = (v214 >> v311) + v177;
                    v177 += v313;
                    v367[v176] = (((v331 - 1) & v214) * *(unsigned __int8 *)((unsigned int)(v215 + 1) + v358)
                                + (v331 - ((v331 - 1) & v214)) * *(unsigned __int8 *)(v215 + v358)) >> v311;
                    v176 = (unsigned int)(v176 + 1);
                  }
                  while ( (unsigned int)v176 < v144 );
                  v34 = 1 << v312;
                  v146 = v314;
                  v145 = v309;
                }
                else
                {
                  do
                  {
                    v178 = (v364[v176]
                          + (v364[v176] >> v332)
                          - ((unsigned int)(v364[v176] + (v364[v176] >> v332)) >> v321)) >> v333;
                    v179 = (v178 >> v311) + v177;
                    v177 += v313;
                    v367[v176] = (((v331 - 1) & v178) * *(unsigned __int16 *)(v358 + 2LL * (unsigned int)(v179 + 1))
                                + (v331 - ((v331 - 1) & v178)) * *(unsigned __int16 *)(v358 + 2 * v179)) >> v311;
                    v176 = (unsigned int)(v176 + 1);
                  }
                  while ( (unsigned int)v176 < v144 );
                  v34 = 1 << v312;
                  v146 = v314;
                  v145 = v309;
                }
              }
            }
            else
            {
              memcpy_0(v367, v364, 4LL * v144);
            }
            v154 = 0;
            if ( v347 )
            {
              do
              {
                v161 = (_BYTE *)v360[v154];
                v162 = (unsigned int)(v348 + v367[v154]) >> v334;
                if ( v162 > 0xFF )
                  LOBYTE(v162) = -1;
                v154 = (unsigned int)(v154 + 1);
                *v161 = v162;
              }
              while ( (unsigned int)v154 < v144 );
            }
            else
            {
              do
              {
                v155 = v367[v154];
                v156 = (_WORD *)v360[v154];
                v154 = (unsigned int)(v154 + 1);
                *v156 = v155 << v334;
              }
              while ( (unsigned int)v154 < v144 );
            }
            v32 = v349;
            if ( v349 )
            {
              v298 = (_BYTE *)v361[v145];
              v299 = (_BYTE *)v360[v144];
              if ( v347 )
                *v299 = *v298;
              else
                *(_WORD *)v299 = *(_WORD *)v298;
            }
            v314 = --v146;
            if ( !v146 )
              break;
LABEL_364:
            v265 = 0;
            if ( v145 < 8 )
              goto LABEL_472;
            v266 = _mm_unpacklo_epi32(_mm_move_epi64(v33), (__m128i)0LL);
            do
            {
              *(__m128i *)&v361[v265] = _mm_add_epi64(v266, _mm_loadu_si128((const __m128i *)&v361[v265]));
              *(__m128i *)&v361[(unsigned int)(v265 + 2)] = _mm_add_epi64(
                                                              _mm_loadu_si128((const __m128i *)&v361[(unsigned int)(v265 + 2)]),
                                                              v266);
              *(__m128i *)&v361[(unsigned int)(v265 + 4)] = _mm_add_epi64(
                                                              v266,
                                                              _mm_loadu_si128((const __m128i *)&v361[(unsigned int)(v265 + 4)]));
              v267 = (unsigned int)(v265 + 6);
              v265 = (unsigned int)(v265 + 8);
              *(__m128i *)&v361[v267] = _mm_add_epi64(_mm_loadu_si128((const __m128i *)&v361[v267]), v266);
            }
            while ( (unsigned int)v265 < (v145 & 0xFFFFFFF8) );
            if ( (unsigned int)v265 >= v145 )
            {
              v314 = v146;
            }
            else
            {
LABEL_472:
              do
              {
                v361[v265] += v357;
                v265 = (unsigned int)(v265 + 1);
              }
              while ( (unsigned int)v265 < v145 );
            }
            v268 = 0;
            if ( v144 < 8 )
              goto LABEL_473;
            v269 = _mm_unpacklo_epi32(_mm_move_epi64(v35), (__m128i)0LL);
            do
            {
              *(__m128i *)&v360[v268] = _mm_add_epi64(_mm_loadu_si128((const __m128i *)&v360[v268]), v269);
              *(__m128i *)&v360[(unsigned int)(v268 + 2)] = _mm_add_epi64(
                                                              _mm_loadu_si128((const __m128i *)&v360[(unsigned int)(v268 + 2)]),
                                                              v269);
              *(__m128i *)&v360[(unsigned int)(v268 + 4)] = _mm_add_epi64(
                                                              _mm_loadu_si128((const __m128i *)&v360[(unsigned int)(v268 + 4)]),
                                                              v269);
              v270 = (unsigned int)(v268 + 6);
              v268 = (unsigned int)(v268 + 8);
              *(__m128i *)&v360[v270] = _mm_add_epi64(_mm_loadu_si128((const __m128i *)&v360[v270]), v269);
            }
            while ( (unsigned int)v268 < (v144 & 0xFFFFFFF8) );
            if ( (unsigned int)v268 < v144 )
            {
LABEL_473:
              do
              {
                v360[v268] += v356;
                v268 = (unsigned int)(v268 + 1);
              }
              while ( (unsigned int)v268 < v144 );
            }
            if ( v349 )
            {
              v361[v145] += v357;
              v360[v144] += v356;
            }
            v271 = 0;
            if ( v316 )
            {
              while ( *(_BYTE *)v361[v271] == *((_BYTE *)&v368[32] + v271) )
              {
                v271 = (unsigned int)(v271 + 1);
                if ( (unsigned int)v271 >= v145 )
                {
LABEL_444:
                  v300 = 0;
                  if ( v347 )
                  {
                    do
                    {
                      v301 = (_BYTE *)v360[v300];
                      v300 = (unsigned int)(v300 + 1);
                      *v301 = v301[-v356];
                    }
                    while ( (unsigned int)v300 < v144 );
                    if ( v349 )
                    {
                      _mm_lfence();
                      *(_BYTE *)v360[v144] = *(_BYTE *)v361[v145];
                    }
                  }
                  else
                  {
                    do
                    {
                      v302 = (_WORD *)v360[v300];
                      v300 = (unsigned int)(v300 + 1);
                      *v302 = *(_WORD *)((char *)v302 - (int)v356);
                    }
                    while ( (unsigned int)v300 < v144 );
                    if ( v349 )
                    {
                      _mm_lfence();
                      *(_WORD *)v360[v144] = *(_WORD *)v361[v145];
                    }
                  }
                  v28 = v146-- == 1;
                  v314 = v146;
                  if ( !v28 )
                    goto LABEL_364;
                  goto LABEL_222;
                }
              }
            }
            else
            {
              while ( *(_WORD *)v361[v271] == *((_WORD *)&v368[34] + v271) )
              {
                v271 = (unsigned int)(v271 + 1);
                if ( (unsigned int)v271 >= v145 )
                  goto LABEL_444;
              }
            }
            v38 = v34 - 1;
            v15 = v316;
          }
LABEL_222:
          v15 = v316;
          v38 = v34 - 1;
        }
        if ( !--v322 )
          break;
        v157 = 0;
        if ( v145 < 8 )
          goto LABEL_453;
        v158 = _mm_unpacklo_epi32(_mm_move_epi64(v36), (__m128i)0LL);
        do
        {
          *(__m128i *)&v361[v157] = _mm_add_epi64(_mm_loadu_si128((const __m128i *)&v361[v157]), v158);
          *(__m128i *)&v361[(unsigned int)(v157 + 2)] = _mm_add_epi64(
                                                          v158,
                                                          _mm_loadu_si128((const __m128i *)&v361[(unsigned int)(v157 + 2)]));
          *(__m128i *)&v361[(unsigned int)(v157 + 4)] = _mm_add_epi64(
                                                          _mm_loadu_si128((const __m128i *)&v361[(unsigned int)(v157 + 4)]),
                                                          v158);
          v159 = (unsigned int)(v157 + 6);
          v157 = (unsigned int)(v157 + 8);
          *(__m128i *)&v361[v159] = _mm_add_epi64(_mm_loadu_si128((const __m128i *)&v361[v159]), v158);
        }
        while ( (unsigned int)v157 < (v145 & 0xFFFFFFF8) );
        if ( (unsigned int)v157 < v145 )
        {
LABEL_453:
          v160 = v323;
          do
          {
            v361[v157] += v323;
            v157 = (unsigned int)(v157 + 1);
          }
          while ( (unsigned int)v157 < v145 );
        }
        else
        {
          v160 = v323;
        }
        v303 = 0;
        if ( v144 < 8 )
          goto LABEL_460;
        v304 = _mm_unpacklo_epi32(_mm_move_epi64(v37), (__m128i)0LL);
        do
        {
          *(__m128i *)&v360[v303] = _mm_add_epi64(v304, _mm_loadu_si128((const __m128i *)&v360[v303]));
          *(__m128i *)&v360[(unsigned int)(v303 + 2)] = _mm_add_epi64(
                                                          _mm_loadu_si128((const __m128i *)&v360[(unsigned int)(v303 + 2)]),
                                                          v304);
          *(__m128i *)&v360[(unsigned int)(v303 + 4)] = _mm_add_epi64(
                                                          _mm_loadu_si128((const __m128i *)&v360[(unsigned int)(v303 + 4)]),
                                                          v304);
          v305 = (unsigned int)(v303 + 6);
          v303 = (unsigned int)(v303 + 8);
          *(__m128i *)&v360[v305] = _mm_add_epi64(_mm_loadu_si128((const __m128i *)&v360[v305]), v304);
        }
        while ( (unsigned int)v303 < (v144 & 0xFFFFFFF8) );
        v160 = v323;
        if ( (unsigned int)v303 < v144 )
        {
LABEL_460:
          v306 = v339;
          do
          {
            v360[v303] += v339;
            v303 = (unsigned int)(v303 + 1);
          }
          while ( (unsigned int)v303 < v144 );
        }
        else
        {
          v306 = v339;
        }
        if ( v32 )
        {
          v361[v145] += v160;
          v360[v144] += v306;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008480  mov     rax, rsp
0x180008483  mov     [rax+18h], rbx
0x180008487  push    rbp
0x180008488  push    rsi
0x180008489  push    rdi
0x18000848a  push    r12
0x18000848c  push    r13
0x18000848e  push    r14
0x180008490  push    r15
0x180008492  lea     rbp, [rax-2D8h]
0x180008499  sub     rsp, 3A0h
0x1800084a0  movaps  xmmword ptr [rax-48h], xmm6
0x1800084a4  movaps  xmmword ptr [rax-58h], xmm7
0x1800084a8  movaps  xmmword ptr [rax-68h], xmm8
0x1800084ad  movaps  xmmword ptr [rax-78h], xmm9
0x1800084b2  movaps  xmmword ptr [rax-88h], xmm10
0x1800084ba  mov     rax, cs:__security_cookie
0x1800084c1  xor     rax, rsp
0x1800084c4  mov     qword ptr [rbp+2D0h+var_98], rax
0x1800084cb  mov     r9d, [rdx]
0x1800084ce  mov     rdi, rdx
0x1800084d1  mov     qword ptr [rsp+3D0h+var_390], rdx
0x1800084d6  mov     r8, rcx
0x1800084d9  lea     eax, [r9-1]
0x1800084dd  cmp     eax, 3
0x1800084e0  ja      loc_180009334
0x1800084e6  lea     eax, [r9-1]
0x1800084ea  cmp     eax, 1
0x1800084ed  jbe     loc_1800089D3
0x1800084f3  mov     edx, [rcx+18h]
0x1800084f6  mov     rax, [rcx+20h]
0x1800084fa  mov     r11d, [r8+8]
0x1800084fe  mov     r12d, [rdi+30h]
0x180008502  mov     r10d, [r8+10h]
0x180008506  mov     qword ptr [rbp+2D0h+var_280], rax
0x18000850a  mov     rax, [rcx+60h]
0x18000850e  mov     qword ptr [rbp+2D0h+var_2C0], rax
0x180008512  mov     rax, [rcx+28h]
0x180008516  mov     qword ptr [rbp+2D0h+var_280+8], rax
0x18000851a  mov     rax, [rcx+68h]
0x18000851e  mov     qword ptr [rbp+2D0h+var_2C0+8], rax
0x180008522  mov     rax, [rcx+30h]
0x180008526  mov     [rbp+2D0h+var_270], rax
0x18000852a  mov     rax, [rcx+70h]
0x18000852e  mov     [rbp+2D0h+var_2B0], rax
0x180008532  mov     rax, [rcx+38h]
0x180008536  mov     [rbp+2D0h+var_268], rax
0x18000853a  mov     rax, [rcx+78h]
0x18000853e  mov     [rbp+2D0h+var_2A8], rax
0x180008542  mov     rax, [rcx+40h]
0x180008546  mov     [rbp+2D0h+var_260], rax
0x18000854a  mov     rax, [rcx+80h]
0x180008551  mov     [rbp+2D0h+var_2A0], rax
0x180008555  mov     rax, [rcx+48h]
0x180008559  mov     [rbp+2D0h+var_258], rax
0x18000855d  mov     rax, [rcx+88h]
0x180008564  mov     [rbp+2D0h+var_298], rax
0x180008568  mov     rax, [rcx+50h]
0x18000856c  mov     [rbp+2D0h+var_250], rax
0x180008573  mov     rax, [rcx+90h]
0x18000857a  mov     [rbp+2D0h+var_290], rax
0x18000857e  mov     rax, [rcx+58h]
0x180008582  mov     [rbp+2D0h+var_248], rax
0x180008589  mov     rax, [rcx+98h]
0x180008590  mov     ecx, [rcx+1Ch]
0x180008593  mov     [rbp+2D0h+var_288], rax
0x180008597  mov     eax, edx
0x180008599  imul    eax, r11d
0x18000859d  movd    xmm0, edx
0x1800085a1  mov     [rbp+2D0h+var_2D8], edx
0x1800085a4  mov     [rbp+2D0h+var_2E4], r11d
0x1800085a8  movd    xmm1, ecx
0x1800085ac  sub     r10d, eax
0x1800085af  pshufd  xmm0, xmm0, 0
0x1800085b4  add     r10d, edx
0x1800085b7  mov     [rbp+2D0h+var_2DC], ecx
0x1800085ba  mov     edx, [r8+14h]
0x1800085be  mov     eax, ecx
0x1800085c0  imul    eax, r11d
0x1800085c4  mov     [rsp+3D0h+var_36C], r10d
0x1800085c9  movd    xmm2, r10d
0x1800085ce  mov     r10d, 1
0x1800085d4  mov     r11d, r10d
0x1800085d7  pshufd  xmm1, xmm1, 0
0x1800085dc  mov     ebx, r10d
0x1800085df  pshufd  xmm2, xmm2, 0
0x1800085e4  sub     edx, eax
0x1800085e6  mov     [rsp+3D0h+var_3AC], r12d
0x1800085eb  add     edx, ecx
0x1800085ed  xor     eax, eax
0x1800085ef  test    dword ptr [r8], 2800h
0x1800085f6  mov     [rbp+2D0h+var_324], edx
0x1800085f9  cmovz   r11d, eax
0x1800085fd  test    dword ptr [r8+4], 2800h
0x180008605  movd    xmm3, edx
0x180008609  cmovz   ebx, eax
0x18000860c  pshufd  xmm3, xmm3, 0
0x180008611  mov     [rbp+2D0h+var_300], ebx
0x180008614  mov     [rsp+3D0h+var_388], r11d
0x180008619  test    r12d, r12d
0x18000861c  jz      loc_180009334
0x180008622  mov     r14d, [rdi+34h]
0x180008626  mov     [rsp+3D0h+var_3A8], r14d
0x18000862b  test    r14d, r14d
0x18000862e  jz      loc_180009334
0x180008634  cmp     r12d, 2
0x180008638  jz      loc_180009334
0x18000863e  cmp     r14d, 2
0x180008642  jz      loc_180009334
0x180008648  cmp     r12d, 8
0x18000864c  ja      loc_180009334
0x180008652  mov     rcx, [rdi+58h]
0x180008656  mov     rsi, [rdi+28h]
0x18000865a  mov     rax, [rdi+10h]
0x18000865e  mov     r15, [rdi+40h]
0x180008662  mov     [rbp+2D0h+var_338], rcx
0x180008666  mov     ecx, [r8+0Ch]
0x18000866a  mov     [rsp+3D0h+var_370], ecx
0x18000866e  mov     [rbp+2D0h+var_2D0], rsi
0x180008672  mov     [rbp+2D0h+var_2C8], rax
0x180008676  mov     [rbp+2D0h+var_320], r15
0x18000867a  lfence
0x18000867d  cmp     r14d, 8
0x180008681  ja      loc_180009334
0x180008687  xor     ecx, ecx
0x180008689  mov     [rbp+2D0h+var_330], ecx
0x18000868c  test    rax, rax
0x18000868f  jnz     loc_180008975
0x180008695  mov     r13d, 10h
0x18000869b  mov     [rsp+3D0h+var_364], ecx
0x18000869f  test    r11d, r11d
0x1800086a2  mov     [rsp+3D0h+var_368], ecx
0x1800086a6  mov     r10d, r13d
0x1800086a9  mov     [rbp+2D0h+var_308], ecx
0x1800086ac  mov     eax, 8
0x1800086b1  cmovnz  r10d, eax
0x1800086b5  mov     [rbp+2D0h+var_2F4], ecx
0x1800086b8  mov     edx, ecx
0x1800086ba  mov     [rbp+2D0h+var_2F0], ecx
0x1800086bd  cmp     r9d, 4
0x1800086c1  jz      loc_18000A53E
0x1800086c7  mov     [rsp+3D0h+var_360], ecx
0x1800086cb  mov     [rsp+3D0h+var_384], ecx
0x1800086cf  mov     [rbp+2D0h+var_2EC], ecx
0x1800086d2  mov     ecx, r10d
0x1800086d5  mov     [rsp+3D0h+var_3A0], ecx
0x1800086d9  test    r15, r15
0x1800086dc  jnz     loc_1800088FA
0x1800086e2  mov     eax, ecx
0x1800086e4  mov     edx, ecx
0x1800086e6  xor     ecx, ecx
0x1800086e8  mov     [rsp+3D0h+var_35C], eax
0x1800086ec  mov     [rsp+3D0h+var_378], ecx
0x1800086f0  mov     [rsp+3D0h+var_354], ecx
0x1800086f4  mov     [rbp+2D0h+var_304], ecx
0x1800086f7  mov     [rsp+3D0h+var_374], ecx
0x1800086fb  mov     [rbp+2D0h+var_344], ecx
0x1800086fe  mov     [rbp+2D0h+var_2FC], ecx
0x180008701  mov     ecx, r10d
0x180008704  mov     r10d, 1
0x18000870a  shl     r10d, cl
0x18000870d  mov     [rbp+2D0h+var_2E8], r10d
0x180008711  lea     ecx, [r10-1]
0x180008715  mov     r10d, 2
0x18000871b  mov     [rbp+2D0h+var_328], r10d
0x18000871f  mov     [rsp+3D0h+var_380], ecx
0x180008723  cmp     r9d, 3
0x180008727  jz      loc_180009E09
0x18000872d  xor     r10d, r10d
0x180008730  mov     [rbp+2D0h+var_348], eax
0x180008733  mov     [rsp+3D0h+var_358], r10d
0x180008738  mov     r9d, eax
0x18000873b  mov     [rsp+3D0h+var_37C], r10d
0x180008740  mov     edi, edx
0x180008742  mov     [rbp+2D0h+var_32C], r10d
0x180008746  mov     edx, 1
0x18000874b  mov     ecx, r9d
0x18000874e  mov     eax, edx
0x180008750  shl     eax, cl
0x180008752  dec     eax
0x180008754  test    rsi, rsi
0x180008757  mov     [rbp+2D0h+var_2E0], eax
0x18000875a  mov     rsi, qword ptr [rsp+3D0h+var_390]
0x18000875f  jnz     loc_180008A14
0x180008765  mov     edx, r9d
0x180008768  mov     [rsp+3D0h+var_39C], r10d
0x18000876d  mov     [rbp+2D0h+var_350], edx
0x180008770  mov     [rsp+3D0h+var_3A4], 0
0x180008778  mov     [rbp+2D0h+var_34C], 0
0x18000877f  mov     [rbp+2D0h+var_328], 0
0x180008786  test    ebx, ebx
0x180008788  jnz     loc_18000930C
0x18000878e  sub     r13d, edx
0x180008791  mov     dword ptr [rbp+2D0h+var_340], r13d
0x180008795  mov     r13d, 1
0x18000879b  cmp     byte ptr [r8+0A0h], 0
0x1800087a3  setnz   al
0x1800087a6  cmp     r12d, 8
0x1800087aa  jz      loc_18000A621
0x1800087b0  cmp     r14d, 8
0x1800087b4  jz      loc_18000A621
0x1800087ba  xor     r9d, r9d
0x1800087bd  movzx   eax, al
0x1800087c0  cmp     r11d, ebx
0x1800087c3  cmovz   r9d, eax
0x1800087c7  mov     [rbp+2D0h+var_2F8], r9d
0x1800087cb  test    r15, r15
0x1800087ce  jnz     loc_180008A76
0x1800087d4  mov     ecx, [rsp+3D0h+var_3A0]
0x1800087d8  movq    xmm9, xmm0
0x1800087dd  shl     r13d, cl
0x1800087e0  movq    xmm8, xmm1
0x1800087e5  movaps  [rsp+3D0h+var_98+8], xmm11
0x1800087ee  movq    xmm10, xmm2
0x1800087f3  mov     [rsp+3D0h+var_3B0], r13d
0x1800087f8  movq    xmm11, xmm3
0x1800087fd  lea     esi, [r13-1]
0x180008801  mov     [rbp+2D0h+var_318], esi
0x180008804  test    r15, r15
0x180008807  jnz     loc_180009376
0x18000880d  cmp     [rsp+3D0h+var_370], 0
0x180008812  jnz     loc_1800093F3
0x180008818  movaps  xmm11, [rsp+3D0h+var_98+8]
0x180008821  jmp     short loc_180008878
0x180008823  inc     edx
0x180008825  cmp     edx, r12d
0x180008828  jb      loc_180009E80
0x18000882e  xor     edx, edx
0x180008830  test    ebx, ebx
0x180008832  jnz     loc_1800088C0
0x180008838  mov     rcx, qword ptr [rbp+rdx*8+2D0h+var_2C0]
0x18000883d  inc     edx
0x18000883f  mov     rax, rcx
0x180008842  sub     rax, r11
0x180008845  movzx   eax, word ptr [rax]
0x180008848  mov     [rcx], ax
0x18000884b  cmp     edx, r14d
0x18000884e  jb      short loc_180008838
0x180008850  test    r9b, r9b
0x180008853  jnz     loc_18000A632
0x180008859  add     r13d, 0FFFFFFFFh
0x18000885d  mov     [rsp+3D0h+var_3B0], r13d
0x180008862  jnz     loc_180008F67
0x180008868  mov     r11d, [rsp+3D0h+var_388]
0x18000886d  add     [rsp+3D0h+var_370], 0FFFFFFFFh
0x180008872  jnz     loc_18000A3D3
0x180008878  xor     eax, eax
0x18000887a  mov     rcx, qword ptr [rbp+2D0h+var_98]
0x180008881  xor     rcx, rsp; StackCookie
0x180008884  call    __security_check_cookie
0x180008889  lea     r11, [rsp+3D0h+var_30]
0x180008891  mov     rbx, [r11+50h]
0x180008895  movaps  xmm6, xmmword ptr [r11-10h]
0x18000889a  movaps  xmm7, xmmword ptr [r11-20h]
0x18000889f  movaps  xmm8, xmmword ptr [r11-30h]
0x1800088a4  movaps  xmm9, xmmword ptr [r11-40h]
0x1800088a9  movaps  xmm10, xmmword ptr [r11-50h]
0x1800088ae  mov     rsp, r11
0x1800088b1  pop     r15
0x1800088b3  pop     r14
0x1800088b5  pop     r13
0x1800088b7  pop     r12
0x1800088b9  pop     rdi
0x1800088ba  pop     rsi
0x1800088bb  pop     rbp
0x1800088bc  retn
0x1800088c0  mov     rcx, qword ptr [rbp+rdx*8+2D0h+var_2C0]
0x1800088c5  inc     edx
0x1800088c7  mov     rax, rcx
0x1800088ca  sub     rax, r11
0x1800088cd  movzx   eax, byte ptr [rax]
0x1800088d0  mov     [rcx], al
0x1800088d2  cmp     edx, r14d
0x1800088d5  jb      short loc_1800088C0
0x1800088d7  test    r9b, r9b
0x1800088da  jz      loc_180008859
0x1800088e0  lfence
0x1800088e3  mov     rcx, qword ptr [rbp+r14*8+2D0h+var_2C0]
0x1800088e8  mov     eax, r12d
0x1800088eb  mov     rdx, qword ptr [rbp+rax*8+2D0h+var_280]
0x1800088f0  movzx   eax, byte ptr [rdx]
0x1800088f3  mov     [rcx], al
0x1800088f5  jmp     loc_180008859
0x1800088fa  lea     eax, [r9-3]
0x1800088fe  cmp     eax, 1
0x180008901  jbe     loc_180009DCD
0x180008907  movsxd  rdi, dword ptr [rdi+38h]
0x18000890b  test    edi, edi
0x18000890d  jz      loc_180009334
0x180008913  xor     r11d, r11d
0x180008916  mov     ecx, 1
0x18000891b  mov     eax, edi
0x18000891d  shr     eax, cl
0x18000891f  test    eax, eax
0x180008921  jz      short loc_180008930
0x180008923  mov     r11d, ecx
0x180008926  inc     ecx
0x180008928  cmp     ecx, 20h ; ' '
0x18000892b  jl      short loc_18000891B
0x18000892d  nop     dword ptr [rax]
  ... truncated ...
```
