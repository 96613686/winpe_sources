# LzmsDoEncoding

- ea: `0x1800182f0`
- end: `0x180019057`
- name: `LzmsDoEncoding`
- size: `3431`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800190e8`

## callees

- `0x18001562a`
- `0x180017ad0`
- `0x180017ba0`
- `0x1800180bc`
- `0x1800181f4`
- `0x180018248`
- `0x1800182f0`
- `0x180019594`
- `0x18001a764`
- `0x18001a94c`
- `0x18001ae0c`
- `0x18001b254`
- `0x18001b2bc`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18001904c`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18001904c`

## pseudocode

```c
__int64 __fastcall LzmsDoEncoding(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, unsigned int a5)
{
  unsigned int v5; // r15d
  unsigned int v6; // r13d
  __int64 v7; // r12
  __int64 v8; // r14
  __int64 v9; // rdi
  __int64 v11; // rcx
  __int64 v12; // rcx
  _DWORD *v13; // rdi
  unsigned int v14; // ebx
  unsigned int v15; // r10d
  unsigned int v16; // r11d
  unsigned int v17; // edi
  __int64 v18; // r15
  int v19; // esi
  __int64 *v20; // r9
  __int64 v21; // rax
  unsigned int v22; // ecx
  unsigned int v23; // edi
  __int64 v24; // rdx
  __int64 v25; // r13
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // r8
  unsigned int v29; // ecx
  __int64 v30; // rcx
  unsigned int v31; // r12d
  __int64 v32; // rax
  int v33; // esi
  int MatchLengthCost; // r8d
  int v35; // r9d
  int v36; // edx
  int i; // edx
  __int64 v38; // rax
  int v39; // r13d
  __int64 v40; // rsi
  int Cost; // eax
  __int64 v42; // rcx
  unsigned int v43; // r13d
  __int64 v44; // rdx
  __int64 v45; // rsi
  __int64 v46; // r10
  unsigned int v47; // r12d
  int v48; // edi
  int RepeatedOffsetMatchCost; // eax
  int v50; // r12d
  __int64 v51; // r13
  int v52; // ecx
  unsigned int v53; // eax
  __int64 v54; // r8
  int v55; // esi
  int v56; // edi
  int v57; // edx
  __int64 v58; // rax
  __int64 v59; // r13
  unsigned __int8 *v60; // r10
  int v61; // r8d
  char v62; // r9
  signed int v63; // r11d
  _BYTE *v64; // rdx
  unsigned __int8 v65; // r9
  unsigned __int8 v66; // dl
  _BYTE *v67; // rax
  unsigned __int8 v68; // al
  unsigned int v69; // r9d
  unsigned int v70; // r12d
  int v71; // esi
  int v72; // r12d
  int v73; // r9d
  int v74; // eax
  int v75; // r8d
  __int64 v76; // rax
  int v77; // edi
  __int64 v78; // r8
  __int64 v79; // rdx
  __int64 j; // rcx
  __int64 k; // rcx
  __int64 m; // rcx
  __int64 v83; // rdi
  __int64 n; // rcx
  unsigned int v85; // edi
  int v86; // eax
  __int64 v87; // r15
  __int64 *v88; // rsi
  unsigned int v89; // r12d
  unsigned int v90; // r10d
  unsigned int v91; // edx
  __int64 v92; // r9
  __int64 v93; // rdi
  int v94; // ecx
  __int64 ii; // rcx
  unsigned int v96; // r8d
  __int64 v97; // rsi
  unsigned int v98; // r9d
  unsigned __int64 v99; // r11
  int v100; // r10d
  signed int v101; // eax
  __int64 v102; // rdi
  _BYTE *v103; // rdx
  unsigned __int8 v104; // r8
  unsigned __int8 v105; // dl
  _BYTE *v106; // rax
  unsigned __int8 v107; // al
  int v108; // ecx
  unsigned int v109; // edx
  unsigned __int64 v110; // r8
  unsigned int v111; // edi
  unsigned __int64 v112; // rax
  int v113; // eax
  unsigned int jj; // ecx
  _WORD *v115; // rdx
  int v116; // r15d
  int v117; // eax
  _WORD *v118; // rdx
  unsigned int v119; // edi
  __int16 v121; // ax
  unsigned int v122; // eax
  unsigned int v123; // [rsp+48h] [rbp-51h]
  int v124; // [rsp+4Ch] [rbp-4Dh]
  int v125; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v126; // [rsp+54h] [rbp-45h]
  unsigned int v127; // [rsp+58h] [rbp-41h]
  unsigned int v128; // [rsp+5Ch] [rbp-3Dh]
  int v129; // [rsp+60h] [rbp-39h]
  unsigned __int64 v130; // [rsp+68h] [rbp-31h] BYREF
  __int64 v131; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int64 v132; // [rsp+78h] [rbp-21h]
  unsigned __int8 *v133; // [rsp+80h] [rbp-19h]
  unsigned __int64 v134; // [rsp+88h] [rbp-11h]
  _DWORD v135[2]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v136; // [rsp+98h] [rbp-1h]
  __int64 v137; // [rsp+F8h] [rbp+5Fh]

  v137 = a1;
  v5 = a3;
  v126 = 0;
  v6 = 511;
  v123 = 0;
  v7 = a2;
  v128 = 0;
  v8 = a1;
  v134 = a2 + a3;
  v9 = a1 + 262192;
  v125 = 511;
  LODWORD(a1) = 1;
  v127 = a3;
  LODWORD(v131) = 0;
  if ( a3 > 2 )
  {
    do
      a1 = (unsigned int)(a1 + 1);
    while ( *((_DWORD *)MatchOffsetDistributionTable + a1) < a3 );
  }
  *(_DWORD *)(v8 + 579192) = a1;
  BuildSuffixArray(v9, a2, a3);
  BuildReverseTrieFromSuffixArray(v9, v5);
  *(_QWORD *)(v8 + 32) = v7;
  *(_DWORD *)(v8 + 326092) = 0;
  *(_QWORD *)(v8 + 326096) = a4;
  *(_QWORD *)(v8 + 326104) = a4;
  v11 = a5 + a4;
  *(_QWORD *)(v8 + 326112) = v11;
  *(_DWORD *)(v8 + 326088) = -1;
  v136 = a5;
  *(_QWORD *)(v8 + 264584) = a4;
  *(_WORD *)(v8 + 264556) = 0;
  *(_QWORD *)(v8 + 264576) = v11;
  *(_QWORD *)(v8 + 264592) = v8 + 326088;
  *(_DWORD *)(v8 + 264552) = 16;
  *(_QWORD *)(v8 + 264568) = v11 - 2;
  memset_0((void *)(v8 + 264600), 0, 0xF030u);
  v12 = 256;
  *(_DWORD *)(v8 + 264608) = 1024;
  *(_DWORD *)(v8 + 264600) = 256;
  v13 = (_DWORD *)(v8 + 321988);
  while ( v12 )
  {
    *v13++ = 1;
    --v12;
  }
  BuildEncodings(v8 + 264600);
  NumberCodecEncoderInit(
    v8 + 333144,
    v8 + 264552,
    (unsigned int)MatchOffsetDistributionTable,
    *(_DWORD *)(v8 + 579192),
    1024);
  NumberCodecEncoderInit(v8 + 394656, v8 + 264552, (unsigned int)MatchLengthDistributionTable, 54, 512);
  NumberCodecEncoderInit(
    v8 + 456168,
    v8 + 264552,
    (unsigned int)MatchOffsetDistributionTable,
    *(_DWORD *)(v8 + 579192),
    1024);
  NumberCodecEncoderInit(v8 + 517680, v8 + 264552, (unsigned int)MatchDeltaOffset1DistributionTable, 8, 512);
  v14 = 0;
  v15 = v5;
  v16 = 0;
  v17 = 0;
  while ( v14 < v5 )
  {
    v18 = v8 + 88LL * v16 + 2947772;
    if ( *(_DWORD *)v18 == 0x40000000 || (v19 = 1, v124 = 1, v6 > 0x400) )
    {
      v19 = 0;
      v124 = 0;
    }
    v20 = (__int64 *)(v8 + 262192);
    v21 = *(_QWORD *)(v8 + 262216);
    LODWORD(v130) = a3;
    v22 = *(_DWORD *)(v21 + 4LL * v14);
    while ( 1 )
    {
      LODWORD(v132) = v22;
      v23 = v22 >> 26;
      if ( v22 >> 26 < 2 )
        break;
      v24 = *v20;
      v25 = v22 & 0x3FFFFFF;
      v129 = v22 & 0x3FFFFFF;
      v22 = *(_DWORD *)(v24 + 4 * v25);
      if ( (v22 & 0xFC000000) > 0xF8000000 )
      {
        while ( 1 )
        {
          v26 = v20[3];
          v27 = v22 & 0x3FFFFFF;
          v28 = (unsigned int)v27;
          v29 = *(_DWORD *)(v26 + 4 * v27);
          LODWORD(v133) = v29;
          if ( v23 > v29 >> 26 )
          {
            v31 = v28;
          }
          else
          {
            do
            {
              v30 = *(_DWORD *)(v24 + 4LL * (v29 & 0x3FFFFFF)) & 0x3FFFFFF;
              v31 = v30;
              v29 = *(_DWORD *)(v26 + 4 * v30);
            }
            while ( v23 <= v29 >> 26 );
            LODWORD(v133) = v29;
          }
          if ( v23 == 62 )
          {
            if ( v31 == v15 )
            {
              v23 = v131;
              LODWORD(v130) = v15 + 1;
              LODWORD(v131) = v131 - 1;
            }
            else
            {
              v130 = a2 + v14 + 62;
              v131 = a2 + v31 + 62;
              if ( v130 < v134 )
              {
                ExtendMatchLength(&v130, &v131, v134);
                v16 = v123;
                v23 = v130 - a2 - v14;
              }
              LODWORD(v130) = v31 + 1;
              LODWORD(v131) = v23 - 1;
            }
          }
          v32 = v23 + v16;
          v33 = 0x40000000;
          if ( (unsigned int)v32 >= 0x1FF || (v33 = *(_DWORD *)(88 * v32 + v8 + 2947772), *(_DWORD *)v18 < v33) )
          {
            if ( v124 )
            {
              MatchLengthCost = GetMatchLengthCost(v8, v23, v28);
              if ( MatchLengthCost + *(_DWORD *)v18 < v33 )
              {
                v35 = 0;
                v36 = v14 - v31;
                while ( v35 < 3 )
                {
                  v36 = v14 - v31;
                  if ( v14 - v31 == *(_DWORD *)(v18 + 4LL * v35 + 20) )
                  {
                    for ( i = 0;
                          i <= v35;
                          MatchLengthCost += *(unsigned __int16 *)(v8
                                                                 + 16 * ((v38 << 6) + *(__int16 *)(v18 + 2 * v38 + 72))
                                                                 + 326404) )
                    {
                      v38 = i++;
                    }
                    if ( v35 + 1 < 3 )
                      MatchLengthCost += *(unsigned __int16 *)(v8
                                                             + 16
                                                             * (((v35 + 1LL) << 6)
                                                              + *(__int16 *)(v18 + 2 * (v35 + 1LL) + 72))
                                                             + 326402);
                    goto LABEL_44;
                  }
                  ++v35;
                }
                if ( v35 == 3 )
                {
                  v39 = MatchLengthCost + *(unsigned __int16 *)(v8 + 16LL * *(__int16 *)(v18 + 72) + 326402);
                  if ( v36 >= 1024 )
                  {
                    Cost = NumberCodecGetCost(v8 + 333144);
                  }
                  else
                  {
                    v40 = v36;
                    Cost = *(_DWORD *)(v8 + 4LL * v36 + 580220);
                    if ( Cost == -1 )
                    {
                      Cost = NumberCodecGetCost(v8 + 333144);
                      *(_DWORD *)(v8 + 4 * v40 + 580220) = Cost;
                    }
                  }
                  MatchLengthCost = Cost + v39;
                  LODWORD(v25) = v129;
                }
LABEL_44:
                TryMatch(
                  v8,
                  MatchLengthCost
                + *(unsigned __int16 *)(v8 + 16LL * *(__int16 *)(v18 + 68) + 326132)
                + *(unsigned __int16 *)(v8 + 16LL * *(__int16 *)(v18 + 70) + 329482),
                  v14,
                  v31,
                  v23,
                  v123,
                  v35,
                  (__int64)&v125);
              }
              v16 = v123;
            }
            v19 = v124;
          }
          else
          {
            v19 = 0;
            v124 = 0;
          }
          v20 = (__int64 *)(v8 + 262192);
          *(_DWORD *)(*(_QWORD *)(v8 + 262216) + 4LL * v31) = v132;
          v42 = (unsigned int)v25;
          v43 = (unsigned int)v133;
          v23 = (unsigned int)v133 >> 26;
          *(_DWORD *)(*(_QWORD *)(v8 + 262192) + 4 * v42) = v14 - 0x4000000;
          v22 = v43;
          LODWORD(v132) = v43;
          if ( v23 < 2 )
            break;
          v24 = *v20;
          v15 = v127;
          LODWORD(v25) = v43 & 0x3FFFFFF;
          v129 = v25;
          v22 = *(_DWORD *)(v24 + 4LL * (unsigned int)v25);
        }
        v7 = a2;
        break;
      }
      *(_DWORD *)(v24 + 4 * v25) = v14 - 0x4000000;
    }
    v44 = v14;
    *(_DWORD *)(v20[3] + 4LL * v14) = v22;
    if ( v19 )
    {
      v45 = 0;
      do
      {
        v46 = a2;
        v47 = v14 - *(_DWORD *)(v18 + 4 * v45 + 20);
        if ( v14 >= *(_DWORD *)(v18 + 4 * v45 + 20) )
        {
          v48 = 0;
          do
          {
            if ( *(_BYTE *)(v48 + v14 + a2) != *(_BYTE *)(v48 + v47 + a2) )
              break;
            ++v48;
          }
          while ( v48 + v14 < a3 );
          if ( v48 > 0 )
          {
            RepeatedOffsetMatchCost = GetRepeatedOffsetMatchCost(v8, (unsigned int)v48, (unsigned int)v45, v18);
            TryMatch(v8, RepeatedOffsetMatchCost, v14, v47, v48, v123, v45, (__int64)&v125);
            v46 = a2;
          }
        }
        v45 = (unsigned int)(v45 + 1);
      }
      while ( (int)v45 < 3 );
      v50 = 0;
      v51 = 0;
      do
      {
        v52 = *(_DWORD *)(v18 + 8 * v51 + 36);
        v53 = *(_DWORD *)(v18 + 8 * v51 + 40) << v52;
        v54 = v14 - v53;
        if ( v14 >= v53 )
        {
          v55 = 0;
          do
          {
            if ( *(unsigned __int8 *)(v55 + v14 + v46) - *(unsigned __int8 *)(v55 - (1 << v52) + v14 + v46) != *(unsigned __int8 *)((unsigned int)(v55 + v54) + v46) - *(unsigned __int8 *)((unsigned int)(v55 - (1 << v52) + v54) + v46) )
              break;
            ++v55;
          }
          while ( v55 + v14 < a3 );
          v8 = v137;
          if ( v55 > 0 )
          {
            v56 = GetMatchLengthCost(v137, (unsigned int)v55, v54);
            v57 = 0;
            do
            {
              v58 = v57++;
              v56 += *(unsigned __int16 *)(v137 + 16 * ((v58 << 6) + *(__int16 *)(v18 + 2 * v58 + 78)) + 330012);
            }
            while ( v57 <= v50 );
            if ( (unsigned int)v50 < 2 )
              v56 += *(unsigned __int16 *)(v137
                                         + 16 * (((v51 + 1) << 6) + *(__int16 *)(v18 + 2 * (v51 + 1) + 78))
                                         + 330010);
            TryDeltaMatch(
              v137,
              v56
            + *(unsigned __int16 *)(v137 + 16LL * *(__int16 *)(v18 + 68) + 326132)
            + *(unsigned __int16 *)(v137 + 16LL * *(__int16 *)(v18 + 70) + 329484),
              v18 + 8 * v51 + 36,
              v55,
              v123,
              v50,
              (__int64)&v125);
          }
        }
        v46 = a2;
        ++v50;
        ++v51;
      }
      while ( v50 < 3 );
      v19 = v124;
      v7 = a2;
      v44 = v14;
    }
    v59 = 0;
    v60 = (unsigned __int8 *)(v7 + v44);
    do
    {
      v61 = 1 << v59;
      if ( 1 << v59 >= (int)v14 )
        break;
      v60 = (unsigned __int8 *)(v44 + v7);
      v62 = *(_BYTE *)(v44 + v7);
      v133 = (unsigned __int8 *)(v44 + v7);
      v63 = v14 - v61;
      v64 = (_BYTE *)(v7 + v14 + 1);
      v65 = v62 - *(_BYTE *)((int)(v14 - v61) + v7);
      if ( (unsigned __int64)v64 >= v134 )
        v66 = -1;
      else
        v66 = *v64 - *(_BYTE *)(v63 + v7 + 1);
      v67 = (_BYTE *)(v7 + v14 + 2);
      if ( (unsigned __int64)v67 >= v134 )
        v68 = -1;
      else
        v68 = *v67 - *(_BYTE *)(v63 + v7 + 2);
      v19 = v124;
      v132 = ((unsigned __int64)(unsigned int)v59 << 16)
           + ((16 * (unsigned int)v68)
            ^ (16 * (unsigned int)v65)
            ^ (v66 + (v65 << 8))
            ^ (unsigned __int64)(v68 + (v66 << 8)));
      v69 = *(_DWORD *)(v8 + 4 * v132 + 588476);
      v70 = v14 - v69;
      if ( ((v61 - 1) & (v14 - v69)) != 0 || (int)v69 <= v61 || !v124 || v69 >= v14 )
        goto LABEL_97;
      v71 = 0;
      do
      {
        if ( *(unsigned __int8 *)(v71 + v14 + a2) - *(unsigned __int8 *)(v71 + v63 + a2) != *(unsigned __int8 *)((int)(v71 + v69) + a2)
                                                                                          - *(unsigned __int8 *)((int)(v71 + v69 - v61) + a2) )
          break;
        ++v71;
      }
      while ( v71 + v14 < a3 );
      v8 = v137;
      if ( v71 > 2 )
      {
        v129 = GetMatchLengthCost(v137, (unsigned int)v71, a2);
        v72 = v70 >> v59;
        if ( v72 >= 1024 )
        {
          v74 = NumberCodecGetCost(v137 + 456168);
LABEL_92:
          v73 = v74;
        }
        else
        {
          v73 = *(_DWORD *)(v137 + 4LL * v72 + 584380);
          if ( v73 == -1 )
          {
            v74 = NumberCodecGetCost(v137 + 456168);
            *(_DWORD *)(v137 + 4LL * v72 + 584380) = v74;
            goto LABEL_92;
          }
        }
        v75 = *(_DWORD *)(v137 + 4 * v59 + 584316);
        if ( v75 == -1 )
        {
          v75 = NumberCodecGetCost(v137 + 517680);
          *(_DWORD *)(v137 + 4 * v59 + 584316) = v75;
        }
        v76 = 2LL * *(__int16 *)(v18 + 68);
        v135[0] = v59;
        v135[1] = v72;
        TryDeltaMatch(
          v137,
          v129
        + v75
        + *(unsigned __int16 *)(v137 + 8 * v76 + 326132)
        + v73
        + *(unsigned __int16 *)(v137 + 16LL * *(__int16 *)(v18 + 78) + 330010)
        + *(unsigned __int16 *)(v137 + 16LL * *(__int16 *)(v18 + 70) + 329484),
          (unsigned int)v135,
          v71,
          v123,
          3,
          (__int64)&v125);
      }
      v19 = v124;
      v60 = v133;
LABEL_97:
      v59 = (unsigned int)(v59 + 1);
      v7 = a2;
      v44 = v14;
      *(_DWORD *)(v8 + 4 * v132 + 588476) = v14;
    }
    while ( (int)v59 < 8 );
    if ( v19
      && (v77 = *(_DWORD *)v18
              + *(unsigned __int16 *)(v8 + 16LL * *(__int16 *)(v18 + 68) + 326130)
              + (*(unsigned __int16 *)(v8 + 4LL * *v60 + 265636) << 6),
          v78 = 88LL * (v123 + 1),
          v79 = v8 + v78 + 2947772,
          v77 < *(_DWORD *)v79) )
    {
      v6 = v125;
      if ( v123 == 510 )
      {
        if ( v77 + ((v125 - 511) << 7) <= *(_DWORD *)v79 )
        {
          v6 = 511;
          v125 = 511;
          goto LABEL_103;
        }
      }
      else
      {
LABEL_103:
        *(_DWORD *)v79 = v77;
        *(_WORD *)(v79 + 84) = 0;
        *(_DWORD *)(v79 + 4) = v123;
        *(_WORD *)(v79 + 68) = (2 * (unsigned __int8)*(_WORD *)(v18 + 68)) & 0xF;
        for ( j = 0; j != 3; ++j )
          *(_WORD *)(v79 + 2 * j + 72) = *(_WORD *)(v18 + 2 * j + 72);
        *(_DWORD *)(v78 + v8 + 2947780) = 0;
        if ( *(_DWORD *)(v18 + 8) )
        {
          do
          {
            *(_DWORD *)(v79 + 4 * j + 20) = *(_DWORD *)(v18 + 4 * j + 16);
            --j;
          }
          while ( j );
          *(_DWORD *)(v78 + v8 + 2947792) = *(_DWORD *)(v18 + 8);
        }
        else
        {
          for ( k = 0; k != 4; ++k )
            *(_DWORD *)(v79 + 4 * k + 20) = *(_DWORD *)(v18 + 4 * k + 20);
        }
        for ( m = 0; m != 3; ++m )
          *(_WORD *)(v79 + 2 * m + 78) = *(_WORD *)(v18 + 2 * m + 78);
        *(_DWORD *)(v78 + v8 + 2947788) = 0;
        if ( *(_DWORD *)(v18 + 16) )
        {
          v83 = 3;
          do
          {
            *(_QWORD *)(v79 + 8 * v83 + 36) = *(_QWORD *)(v18 + 8 * (v83 - 1) + 36);
            --v83;
          }
          while ( v83 );
          *(_QWORD *)(v78 + v8 + 2947808) = *(_QWORD *)(v18 + 12);
        }
        else
        {
          for ( n = 0; n != 4; ++n )
            *(_QWORD *)(v79 + 8 * n + 36) = *(_QWORD *)(v18 + 8 * n + 36);
        }
      }
    }
    else
    {
      v6 = v125;
    }
    v16 = v123 + 1;
    ++v14;
    v123 = v16;
    if ( v16 < 0x1FF )
    {
      v15 = v130;
      v5 = a3;
      v17 = v128;
      v127 = v130;
      continue;
    }
    v85 = v128;
    v86 = OutputCurrentLzResult(v8, v16, v6, v7 + v128);
    *(_DWORD *)(v8 + 2994876) = v86;
    if ( v86 )
      return v126;
    v5 = a3;
    v17 = v6 + v85;
    v16 = 0;
    v128 = v17;
    v123 = 0;
    v6 = 511;
    v125 = 511;
    v15 = a3;
    v127 = a3;
    if ( v14 < v17 )
    {
      v87 = v14;
      v88 = (__int64 *)(v8 + 262192);
      do
      {
        v89 = v14 - 0x4000000;
        v90 = *(_DWORD *)(v88[3] + 4 * v87);
        while ( 1 )
        {
          v91 = v90 >> 26;
          if ( v90 >> 26 < 2 )
            break;
          v92 = *v88;
          v93 = v90 & 0x3FFFFFF;
          v94 = *(_DWORD *)(*v88 + 4 * v93);
          if ( (v94 & 0xFC000000) > 0xF8000000 )
          {
            while ( 1 )
            {
              v97 = v88[3];
              for ( ii = v94 & 0x3FFFFFF; ; ii = *(_DWORD *)(v92 + 4LL * (v96 & 0x3FFFFFF)) & 0x3FFFFFF )
              {
                v96 = *(_DWORD *)(v97 + 4 * ii);
                if ( v91 > v96 >> 26 )
                  break;
              }
              *(_DWORD *)(v97 + 4LL * (unsigned int)ii) = v90;
              v88 = (__int64 *)(v8 + 262192);
              v91 = v96 >> 26;
              v90 = v96;
              *(_DWORD *)(*(_QWORD *)(v8 + 262192) + 4 * v93) = v89;
              if ( v96 >> 26 < 2 )
                break;
              v92 = *v88;
              v93 = v96 & 0x3FFFFFF;
              v94 = *(_DWORD *)(*v88 + 4 * v93);
            }
            break;
          }
          v89 = v14 - 0x4000000;
          v90 = *(_DWORD *)(*v88 + 4 * v93);
          *(_DWORD *)(v92 + 4 * v93) = v14 - 0x4000000;
        }
        v98 = v14 + 1;
        v7 = a2;
        v99 = v134;
        *(_DWORD *)(v88[3] + 4 * v87) = v90;
        v100 = 0;
        do
        {
          if ( 1 << v100 >= (int)v14 )
            break;
          v98 = v14 + 1;
          v101 = v14 - (1 << v100);
          v102 = v101;
          v103 = (_BYTE *)(a2 + v14 + 1);
          v104 = *(_BYTE *)(v87 + a2) - *(_BYTE *)(v101 + a2);
          v105 = (unsigned __int64)v103 >= v99 ? -1 : *v103 - *(_BYTE *)(v101 + a2 + 1);
          v106 = (_BYTE *)(a2 + v14 + 2);
          v107 = (unsigned __int64)v106 >= v99 ? -1 : *v106 - *(_BYTE *)(v102 + a2 + 2);
          v108 = v105;
          v109 = 16 * v104;
          v110 = (v108 + (v104 << 8)) ^ (unsigned __int64)((unsigned int)v107 + (v108 << 8));
          v111 = 16 * v107;
          v112 = (unsigned __int64)(unsigned int)v100++ << 16;
          *(_DWORD *)(v8 + 4 * (v112 + (v111 ^ v109 ^ v110)) + 588476) = v14;
        }
        while ( v100 < 8 );
        v17 = v128;
        ++v87;
        v14 = v98;
      }
      while ( v98 < v128 );
      v15 = v127;
      v16 = 0;
      v5 = a3;
    }
  }
  if ( v16 )
  {
    v113 = OutputCurrentLzResult(v8, v16, v16, v7 + v17);
    *(_DWORD *)(v8 + 2994876) = v113;
    if ( v113 )
      return v126;
  }
  for ( jj = 0; jj < 2; ++jj )
  {
    v115 = *(_WORD **)(v8 + 326096);
    if ( (unsigned __int64)v115 + 1 >= *(_QWORD *)(v8 + 326112) )
    {
      v116 = v126;
      v117 = 111;
      goto LABEL_153;
    }
    *v115 = *(_WORD *)(v8 + 326094);
    *(_QWORD *)(v8 + 326096) += 2LL;
    *(_DWORD *)(v8 + 326092) <<= 16;
  }
  v116 = *(_DWORD *)(v8 + 326096) - *(_DWORD *)(v8 + 326104);
  v126 = v116;
  v117 = 0;
LABEL_153:
  *(_DWORD *)(v8 + 2994876) = v117;
  if ( v117 )
    return v126;
  v118 = *(_WORD **)(v8 + 264568);
  if ( (unsigned __int64)v118 < *(_QWORD *)(v8 + 264584) )
    goto LABEL_155;
  v121 = *(_WORD *)(v8 + 264556) << *(_DWORD *)(v8 + 264552);
  *(_WORD *)(v8 + 264556) = v121;
  *v118 = v121;
  *(_QWORD *)(v8 + 264568) -= 2LL;
  v122 = *(_DWORD *)(v8 + 264576) - *(_DWORD *)(v8 + 264568);
  *(_DWORD *)(v8 + 264552) += 16;
  *(_DWORD *)(v8 + 2994876) = 0;
  v119 = v122 + v116;
  if ( v122 + v116 > a5 )
  {
LABEL_155:
    *(_DWORD *)(v8 + 2994876) = 111;
    return v126;
  }
  memmove_s((void *const)(a4 + v116), a5 - v116, (const void *const)(a4 + v136 - v122), v122);
  return v119;
}

```

## disassembly

```asm
0x1800182f0  mov     rax, rsp
0x1800182f3  mov     [rax+20h], r9
0x1800182f7  mov     [rax+18h], r8d
0x1800182fb  mov     [rax+10h], rdx
0x1800182ff  mov     [rax+8], rcx
0x180018303  push    rbp
0x180018304  push    rbx
0x180018305  push    rsi
0x180018306  push    rdi
0x180018307  push    r12
0x180018309  push    r13
0x18001830b  push    r14
0x18001830d  push    r15
0x18001830f  lea     rbp, [rax-57h]
0x180018313  sub     rsp, 0A8h
0x18001831a  xor     esi, esi
0x18001831c  mov     eax, r8d
0x18001831f  add     rax, rdx
0x180018322  mov     r15d, r8d
0x180018325  mov     [rbp+4Fh+var_94], esi
0x180018328  mov     r13d, 1FFh
0x18001832e  mov     [rbp+4Fh+var_A0], esi
0x180018331  mov     r12, rdx
0x180018334  mov     [rbp+4Fh+var_8C], esi
0x180018337  mov     r14, rcx
0x18001833a  mov     [rbp+4Fh+var_60], rax
0x18001833e  lea     rdi, [rcx+40030h]
0x180018345  mov     [rbp+4Fh+var_98], r13d
0x180018349  lea     ecx, [rsi+1]
0x18001834c  mov     [rbp+4Fh+var_90], r15d
0x180018350  mov     rbx, r9
0x180018353  mov     dword ptr [rbp+4Fh+var_78], esi
0x180018356  lea     rdx, MatchOffsetDistributionTable
0x18001835d  cmp     r8d, 2
0x180018361  jbe     short loc_18001836B
0x180018363  inc     ecx
0x180018365  cmp     [rdx+rcx*4], r15d
0x180018369  jb      short loc_180018363
0x18001836b  mov     [r14+8D678h], ecx
0x180018372  mov     r8d, r15d
0x180018375  mov     rcx, rdi
0x180018378  mov     rdx, r12
0x18001837b  call    BuildSuffixArray
0x180018380  mov     edx, r15d
0x180018383  mov     rcx, rdi
0x180018386  call    BuildReverseTrieFromSuffixArray
0x18001838b  mov     eax, [rbp+4Fh+arg_20]
0x18001838e  lea     rdx, [r14+4F9C8h]
0x180018395  mov     [r14+20h], r12
0x180018399  mov     r8d, 0F030h; Size
0x18001839f  mov     [rdx+4], esi
0x1800183a2  lea     rsi, [r14+40968h]
0x1800183a9  mov     [rdx+8], rbx
0x1800183ad  mov     [rdx+10h], rbx
0x1800183b1  lea     rcx, [rax+rbx]
0x1800183b5  mov     [rdx+18h], rcx
0x1800183b9  mov     dword ptr [rdx], 0FFFFFFFFh
0x1800183bf  mov     [rbp+4Fh+var_50], rax
0x1800183c3  xor     eax, eax
0x1800183c5  mov     [rsi+20h], rbx
0x1800183c9  lea     rbx, [r14+40998h]
0x1800183d0  mov     [rsi+4], ax
0x1800183d4  lea     rax, [rcx-2]
0x1800183d8  mov     [rsi+18h], rcx
0x1800183dc  mov     rcx, rbx; void *
0x1800183df  mov     [rsi+28h], rdx
0x1800183e3  xor     edx, edx; Val
0x1800183e5  mov     dword ptr [rsi], 10h
0x1800183eb  mov     [rsi+10h], rax
0x1800183ef  call    memset_0
0x1800183f4  mov     ecx, 100h
0x1800183f9  mov     dword ptr [r14+409A0h], 400h
0x180018404  mov     [rbx], ecx
0x180018406  lea     rdi, [r14+4E9C4h]
0x18001840d  mov     eax, 1
0x180018412  rep stosd
0x180018414  mov     rcx, rbx
0x180018417  call    BuildEncodings
0x18001841c  mov     r9d, [r14+8D678h]
0x180018423  lea     rcx, [r14+51558h]
0x18001842a  mov     ebx, 400h
0x18001842f  lea     r8, MatchOffsetDistributionTable
0x180018436  mov     rdx, rsi
0x180018439  mov     [rsp+0E0h+var_C0], ebx
0x18001843d  call    NumberCodecEncoderInit
0x180018442  mov     edi, 200h
0x180018447  lea     rcx, [r14+605A0h]
0x18001844e  mov     r9d, 36h ; '6'
0x180018454  mov     [rsp+0E0h+var_C0], edi
0x180018458  lea     r8, MatchLengthDistributionTable
0x18001845f  mov     rdx, rsi
0x180018462  call    NumberCodecEncoderInit
0x180018467  mov     r9d, [r14+8D678h]
0x18001846e  lea     rcx, [r14+6F5E8h]
0x180018475  lea     r8, MatchOffsetDistributionTable
0x18001847c  mov     [rsp+0E0h+var_C0], ebx
0x180018480  mov     rdx, rsi
0x180018483  call    NumberCodecEncoderInit
0x180018488  lea     rcx, [r14+7E630h]
0x18001848f  mov     [rsp+0E0h+var_C0], edi
0x180018493  mov     r9d, 8
0x180018499  lea     r8, MatchDeltaOffset1DistributionTable
0x1800184a0  mov     rdx, rsi
0x1800184a3  call    NumberCodecEncoderInit
0x1800184a8  xor     ebx, ebx
0x1800184aa  mov     r10d, r15d
0x1800184ad  mov     r11d, ebx
0x1800184b0  mov     edi, ebx
0x1800184b2  cmp     ebx, r15d
0x1800184b5  jnb     loc_180018F25
0x1800184bb  mov     eax, r11d
0x1800184be  imul    r15, rax, 58h ; 'X'
0x1800184c2  add     r15, 2CFABCh
0x1800184c9  add     r15, r14
0x1800184cc  cmp     dword ptr [r15], 40000000h
0x1800184d3  jz      short loc_1800184E6
0x1800184d5  mov     esi, 1
0x1800184da  mov     [rbp+4Fh+var_9C], esi
0x1800184dd  cmp     r13d, 400h
0x1800184e4  jbe     short loc_1800184EB
0x1800184e6  xor     esi, esi
0x1800184e8  mov     [rbp+4Fh+var_9C], esi
0x1800184eb  mov     r8d, [rbp+4Fh+arg_10]
0x1800184ef  lea     r9, [r14+40030h]
0x1800184f6  mov     rax, [r9+18h]
0x1800184fa  mov     edx, ebx
0x1800184fc  mov     dword ptr [rbp+4Fh+var_80], r8d
0x180018500  mov     ecx, [rax+rdx*4]
0x180018503  mov     edi, ecx
0x180018505  mov     dword ptr [rbp+4Fh+var_70], ecx
0x180018508  shr     edi, 1Ah
0x18001850b  cmp     edi, 2
0x18001850e  jb      loc_1800187B9
0x180018514  mov     rdx, [r9]
0x180018517  mov     r13d, ecx
0x18001851a  and     r13d, 3FFFFFFh
0x180018521  mov     [rbp+4Fh+var_88], r13d
0x180018525  mov     ecx, [rdx+r13*4]
0x180018529  mov     eax, ecx
0x18001852b  and     eax, 0FC000000h
0x180018530  cmp     eax, 0F8000000h
0x180018535  ja      short loc_180018543
0x180018537  lea     eax, [rbx-4000000h]
0x18001853d  mov     [rdx+r13*4], eax
0x180018541  jmp     short loc_180018503
0x180018543  mov     esi, 3FFFFFFh
0x180018548  mov     r9, [r9+18h]
0x18001854c  and     ecx, esi
0x18001854e  mov     r8d, ecx
0x180018551  mov     ecx, [r9+rcx*4]
0x180018555  mov     eax, ecx
0x180018557  shr     eax, 1Ah
0x18001855a  mov     dword ptr [rbp+4Fh+var_68], ecx
0x18001855d  cmp     edi, eax
0x18001855f  ja      short loc_18001857E
0x180018561  and     rcx, rsi
0x180018564  mov     ecx, [rdx+rcx*4]
0x180018567  and     ecx, esi
0x180018569  mov     r12d, ecx
0x18001856c  mov     ecx, [r9+rcx*4]
0x180018570  mov     eax, ecx
0x180018572  shr     eax, 1Ah
0x180018575  cmp     edi, eax
0x180018577  jbe     short loc_180018561
0x180018579  mov     dword ptr [rbp+4Fh+var_68], ecx
0x18001857c  jmp     short loc_180018581
0x18001857e  mov     r12d, r8d
0x180018581  cmp     edi, 3Eh ; '>'
0x180018584  jnz     short loc_1800185EA
0x180018586  cmp     r12d, r10d
0x180018589  jnz     short loc_18001859E
0x18001858b  mov     edx, dword ptr [rbp+4Fh+var_78]
0x18001858e  lea     ecx, [r10+1]
0x180018592  mov     edi, edx
0x180018594  mov     dword ptr [rbp+4Fh+var_80], ecx
0x180018597  dec     edx
0x180018599  mov     dword ptr [rbp+4Fh+var_78], edx
0x18001859c  jmp     short loc_1800185EA
0x18001859e  mov     rsi, [rbp+4Fh+arg_8]
0x1800185a2  lea     edx, [rbx+3Eh]
0x1800185a5  mov     rax, [rbp+4Fh+var_60]
0x1800185a9  lea     ecx, [r12+3Eh]
0x1800185ae  add     rdx, rsi
0x1800185b1  add     rcx, rsi
0x1800185b4  mov     [rbp+4Fh+var_80], rdx
0x1800185b8  mov     [rbp+4Fh+var_78], rcx
0x1800185bc  cmp     rdx, rax
0x1800185bf  jnb     short loc_1800185DC
0x1800185c1  mov     r8, rax
0x1800185c4  lea     rdx, [rbp+4Fh+var_78]
0x1800185c8  lea     rcx, [rbp+4Fh+var_80]
0x1800185cc  call    ExtendMatchLength
0x1800185d1  mov     edi, dword ptr [rbp+4Fh+var_80]
0x1800185d4  mov     r11d, [rbp+4Fh+var_A0]
0x1800185d8  sub     edi, esi
0x1800185da  sub     edi, ebx
0x1800185dc  lea     eax, [r12+1]
0x1800185e1  mov     dword ptr [rbp+4Fh+var_80], eax
0x1800185e4  lea     eax, [rdi-1]
0x1800185e7  mov     dword ptr [rbp+4Fh+var_78], eax
0x1800185ea  lea     eax, [rdi+r11]
0x1800185ee  mov     esi, 40000000h
0x1800185f3  cmp     eax, 1FFh
0x1800185f8  jnb     short loc_180018615
0x1800185fa  imul    rcx, rax, 58h ; 'X'
0x1800185fe  mov     esi, [rcx+r14+2CFABCh]
0x180018606  cmp     [r15], esi
0x180018609  jl      short loc_180018615
0x18001860b  xor     esi, esi
0x18001860d  mov     [rbp+4Fh+var_9C], esi
0x180018610  jmp     loc_180018761
0x180018615  cmp     [rbp+4Fh+var_9C], 0
0x180018619  jz      loc_18001875E
0x18001861f  mov     edx, edi
0x180018621  mov     rcx, r14
0x180018624  call    GetMatchLengthCost
0x180018629  mov     ecx, [r15]
0x18001862c  mov     r8d, eax
0x18001862f  add     ecx, eax
0x180018631  cmp     ecx, esi
0x180018633  jge     loc_18001875A
0x180018639  xor     r9d, r9d
0x18001863c  mov     edx, ebx
0x18001863e  sub     edx, r12d
0x180018641  cmp     r9d, 3
0x180018645  jge     short loc_1800186B3
0x180018647  movsxd  r10, r9d
0x18001864a  mov     edx, ebx
0x18001864c  sub     edx, r12d
0x18001864f  cmp     edx, [r15+r10*4+14h]
0x180018654  jz      short loc_18001865B
0x180018656  inc     r9d
0x180018659  jmp     short loc_180018641
0x18001865b  xor     edx, edx
0x18001865d  test    r9d, r9d
0x180018660  js      short loc_180018688
0x180018662  movsxd  rax, edx
0x180018665  inc     edx
0x180018667  movsx   rcx, word ptr [r15+rax*2+48h]
0x18001866d  shl     rax, 6
0x180018671  add     rcx, rax
0x180018674  add     rcx, rcx
0x180018677  movzx   eax, word ptr [r14+rcx*8+4FB04h]
0x180018680  add     r8d, eax
0x180018683  cmp     edx, r9d
0x180018686  jle     short loc_180018662
0x180018688  lea     eax, [r9+1]
0x18001868c  cmp     eax, 3
0x18001868f  jge     short loc_18001870B
0x180018691  lea     rax, [r10+1]
0x180018695  movsx   rcx, word ptr [r15+rax*2+48h]
0x18001869b  shl     rax, 6
0x18001869f  add     rcx, rax
0x1800186a2  add     rcx, rcx
0x1800186a5  movzx   eax, word ptr [r14+rcx*8+4FB02h]
0x1800186ae  add     r8d, eax
0x1800186b1  jmp     short loc_18001870B
0x1800186b3  jnz     short loc_18001870B
0x1800186b5  movsx   rax, word ptr [r15+48h]
0x1800186ba  add     rax, rax
0x1800186bd  movzx   r13d, word ptr [r14+rax*8+4FB02h]
0x1800186c6  add     r13d, r8d
0x1800186c9  cmp     edx, 400h
0x1800186cf  jge     short loc_1800186F7
0x1800186d1  movsxd  rsi, edx
0x1800186d4  mov     eax, [r14+rsi*4+8DA7Ch]
0x1800186dc  cmp     eax, 0FFFFFFFFh
0x1800186df  jnz     short loc_180018703
0x1800186e1  lea     rcx, [r14+51558h]
0x1800186e8  call    NumberCodecGetCost
0x1800186ed  mov     [r14+rsi*4+8DA7Ch], eax
0x1800186f5  jmp     short loc_180018703
0x1800186f7  lea     rcx, [r14+51558h]
0x1800186fe  call    NumberCodecGetCost
0x180018703  lea     r8d, [rax+r13]
0x180018707  mov     r13d, [rbp+4Fh+var_88]
0x18001870b  movsx   rax, word ptr [r15+44h]
0x180018710  add     rax, rax
0x180018713  movzx   ecx, word ptr [r14+rax*8+4F9F4h]
0x18001871c  movsx   rax, word ptr [r15+46h]
0x180018721  add     rax, rax
0x180018724  movzx   edx, word ptr [r14+rax*8+5070Ah]
0x18001872d  lea     eax, [r8+rcx]
0x180018731  add     edx, eax
0x180018733  mov     r8d, ebx
0x180018736  lea     rax, [rbp+4Fh+var_98]
0x18001873a  mov     rcx, r14
0x18001873d  mov     [rsp+38h], rax
0x180018742  mov     eax, [rbp+4Fh+var_A0]
0x180018745  mov     dword ptr [rsp+0E0h+var_B0], r9d
0x18001874a  mov     r9d, r12d
0x18001874d  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180018751  mov     [rsp+0E0h+var_C0], edi
0x180018755  call    TryMatch
0x18001875a  mov     r11d, [rbp+4Fh+var_A0]
0x18001875e  mov     esi, [rbp+4Fh+var_9C]
0x180018761  mov     edx, dword ptr [rbp+4Fh+var_70]
0x180018764  lea     r9, [r14+40030h]
0x18001876b  mov     rax, [r9+18h]
0x18001876f  mov     ecx, r12d
  ... truncated ...
```
