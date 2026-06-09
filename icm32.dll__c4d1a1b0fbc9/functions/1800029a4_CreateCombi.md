# CreateCombi

- ea: `0x1800029a4`
- end: `0x1800042da`
- name: `CreateCombi`
- size: `6454`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *, char)`
- caller_count: `1`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x1800023c8`

## callees

- `0x18000190c`
- `0x1800019e8`
- `0x1800029a4`
- `0x1800042e0`
- `0x1800049d4`
- `0x180004a40`
- `0x1800053d0`
- `0x180008480`
- `0x180012af0`
- `0x180012c90`
- `0x180017504`
- `0x1800176b0`
- `0x180018808`
- `0x180018a54`
- `0x180018b68`
- `0x180018b9c`
- `0x18001927c`
- `0x1800192e8`
- `0x18001d15d`
- `0x180020758`
- `0x1800207d0`
- `0x18003c9b4`
- `0x18003cb08`
- `0x18003ce9c`
- `0x18003d002`
- `0x18003d00e`
- `0x18003d040`

## import_xrefs

- `mscms!GetColorProfileHeader` at `0x180002ab6`
- `mscms!GetColorProfileHeader` at `0x180002d1f`
- `mscms!GetColorProfileHeader` at `0x180002e74`
- `mscms!GetColorProfileHeader` at `0x180002ab6`
- `mscms!GetColorProfileHeader` at `0x180002d1f`
- `mscms!GetColorProfileHeader` at `0x180002e74`

## pseudocode

```c
__int64 __fastcall CreateCombi(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4, char a5)
{
  char *v9; // r15
  char v10; // al
  void *v11; // rcx
  BOOL ColorProfileHeader; // eax
  unsigned int v13; // r12d
  __int16 v14; // ax
  int v15; // ebx
  int v16; // r13d
  unsigned __int16 v17; // di
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // edi
  unsigned __int8 v33; // si
  unsigned __int8 v34; // dl
  BOOL v35; // eax
  int v36; // r14d
  unsigned int v37; // ebx
  unsigned __int16 i; // dx
  char v39; // dl
  int v40; // edi
  unsigned __int8 v41; // cl
  unsigned __int8 v42; // al
  __int64 v43; // rsi
  char v44; // al
  unsigned int v45; // edx
  int v46; // eax
  int v47; // eax
  __int64 v48; // rdi
  void *v49; // rcx
  BOOL v50; // eax
  __int64 v51; // rax
  __int64 v52; // r8
  int v53; // eax
  __int16 SpecialCube16; // ax
  void *v55; // rcx
  unsigned __int8 v56; // al
  int v57; // esi
  int v58; // r14d
  int v59; // eax
  char v60; // si
  char v61; // di
  bool v62; // r14
  unsigned int v63; // eax
  int v64; // r8d
  char v65; // dl
  bool v66; // cl
  int v67; // ecx
  int v68; // eax
  __int16 Cube16; // ax
  int v70; // edi
  __int64 v71; // rcx
  __int64 v72; // rax
  _DWORD *v73; // rsi
  int v74; // r14d
  __int64 v75; // rcx
  int v76; // eax
  size_t v77; // rdi
  int v78; // ecx
  size_t v79; // rdi
  int v80; // r12d
  _DWORD *v81; // r15
  _DWORD *v82; // rax
  _DWORD *v83; // rdi
  void **v84; // rdx
  void *v85; // r8
  unsigned __int16 v86; // dx
  size_t v87; // r14
  int v88; // edi
  int v89; // r12d
  size_t v90; // r14
  int v91; // eax
  unsigned __int16 *v92; // r8
  int v93; // r9d
  int v94; // r10d
  unsigned int v95; // eax
  unsigned int v96; // edx
  unsigned __int16 v97; // r11
  unsigned __int16 v98; // r14
  int j; // ecx
  unsigned int v100; // eax
  int v101; // edi
  unsigned int v102; // eax
  __int64 v103; // rcx
  int v104; // r11d
  __int64 v105; // r8
  char v106; // si
  void *v107; // rax
  int v108; // edi
  void *v109; // rax
  int v110; // edi
  _DWORD *v111; // r9
  int v112; // r8d
  int k; // edx
  __int64 v114; // rcx
  int m; // edx
  __int64 v116; // rcx
  int v117; // eax
  int v118; // eax
  _DWORD *v119; // rdi
  __int64 n; // rcx
  int v121; // ebx
  int v122; // edi
  int ii; // ecx
  int v124; // r8d
  int v125; // ebx
  __int64 v126; // rcx
  unsigned int v127; // esi
  char *v128; // rax
  unsigned __int8 *v129; // r9
  int jj; // r8d
  __int64 v131; // rdx
  char *v132; // rax
  int v133; // edi
  int v134; // eax
  int v135; // r13d
  __int64 v136; // r8
  __int64 v137; // r8
  char *v138; // rdi
  unsigned __int16 v139; // cx
  int v140; // edx
  __int64 v141; // rcx
  __int64 mm; // rdx
  __int64 v143; // rax
  char *v144; // rcx
  int v145; // r14d
  __int64 v146; // rsi
  bool v147; // zf
  void *v148; // rax
  __int64 v149; // r8
  __int64 v150; // rsi
  _DWORD *v151; // rsi
  unsigned int v152; // eax
  unsigned int v153; // eax
  __int64 v154; // r8
  int v155; // eax
  int v156; // eax
  DWORD v157; // eax
  _DWORD *v158; // rcx
  char *v159; // rax
  int v160; // eax
  char *v161; // rcx
  bool v163; // [rsp+30h] [rbp-D0h]
  char v164; // [rsp+30h] [rbp-D0h]
  _WORD v165[2]; // [rsp+34h] [rbp-CCh] BYREF
  char v166; // [rsp+38h] [rbp-C8h]
  int v167; // [rsp+3Ch] [rbp-C4h]
  int v168; // [rsp+40h] [rbp-C0h] BYREF
  int v169; // [rsp+44h] [rbp-BCh] BYREF
  bool v170; // [rsp+48h] [rbp-B8h]
  char v171; // [rsp+49h] [rbp-B7h]
  char v172; // [rsp+4Ah] [rbp-B6h]
  int v173; // [rsp+4Ch] [rbp-B4h]
  int v174; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v175; // [rsp+54h] [rbp-ACh]
  int v176; // [rsp+58h] [rbp-A8h]
  int v177; // [rsp+5Ch] [rbp-A4h] BYREF
  int v178; // [rsp+60h] [rbp-A0h]
  unsigned int v179; // [rsp+64h] [rbp-9Ch]
  int v180; // [rsp+68h] [rbp-98h]
  int v181; // [rsp+6Ch] [rbp-94h]
  int v182; // [rsp+70h] [rbp-90h]
  _DWORD *v183; // [rsp+78h] [rbp-88h]
  int v184; // [rsp+80h] [rbp-80h]
  __int64 v185; // [rsp+88h] [rbp-78h]
  HPROFILE hProfile; // [rsp+90h] [rbp-70h] BYREF
  DWORD phVersion; // [rsp+98h] [rbp-68h]
  DWORD phClass; // [rsp+9Ch] [rbp-64h]
  DWORD phDataColorSpace; // [rsp+A0h] [rbp-60h]
  int phConnectionSpace; // [rsp+A4h] [rbp-5Ch]
  int v191; // [rsp+A8h] [rbp-58h] BYREF
  int v192; // [rsp+ACh] [rbp-54h]
  int v193; // [rsp+B0h] [rbp-50h]
  int v194; // [rsp+B4h] [rbp-4Ch]
  int v195; // [rsp+B8h] [rbp-48h]
  int v196; // [rsp+BCh] [rbp-44h]
  __int16 v197; // [rsp+C0h] [rbp-40h]
  bool v198; // [rsp+C2h] [rbp-3Eh]
  char v199; // [rsp+C3h] [rbp-3Dh]
  char v200; // [rsp+C4h] [rbp-3Ch]
  char v201; // [rsp+C5h] [rbp-3Bh]
  char v202; // [rsp+C6h] [rbp-3Ah]
  char v203; // [rsp+C7h] [rbp-39h]
  char v204; // [rsp+C8h] [rbp-38h]
  char v205; // [rsp+C9h] [rbp-37h]
  __int64 v206; // [rsp+D0h] [rbp-30h]
  __int64 v207; // [rsp+D8h] [rbp-28h]
  int v208; // [rsp+E0h] [rbp-20h]
  int v209; // [rsp+E4h] [rbp-1Ch]
  char *v210; // [rsp+E8h] [rbp-18h] BYREF
  char *v211; // [rsp+F0h] [rbp-10h]
  size_t Size; // [rsp+F8h] [rbp-8h]
  void *v213; // [rsp+100h] [rbp+0h]
  __int64 v214; // [rsp+108h] [rbp+8h]
  size_t v215; // [rsp+110h] [rbp+10h]
  int v216; // [rsp+118h] [rbp+18h]
  void *v217; // [rsp+120h] [rbp+20h]
  __int64 v218; // [rsp+128h] [rbp+28h]
  _DWORD v219[3]; // [rsp+130h] [rbp+30h] BYREF
  char v220; // [rsp+13Ch] [rbp+3Ch]
  void *v221; // [rsp+140h] [rbp+40h]
  int v222; // [rsp+148h] [rbp+48h]
  int v223; // [rsp+14Ch] [rbp+4Ch]
  int v224; // [rsp+150h] [rbp+50h]
  char v225; // [rsp+154h] [rbp+54h]
  void *v226; // [rsp+158h] [rbp+58h]
  void *v227; // [rsp+160h] [rbp+60h]
  unsigned int v228; // [rsp+168h] [rbp+68h]
  unsigned int v229; // [rsp+16Ch] [rbp+6Ch]
  char *v230; // [rsp+170h] [rbp+70h]
  int v231; // [rsp+180h] [rbp+80h] BYREF
  int v232; // [rsp+184h] [rbp+84h]
  unsigned int v233; // [rsp+188h] [rbp+88h]
  int v234; // [rsp+18Ch] [rbp+8Ch]
  int v235; // [rsp+190h] [rbp+90h]
  int kk; // [rsp+194h] [rbp+94h]
  int v237; // [rsp+198h] [rbp+98h]
  int v238; // [rsp+19Ch] [rbp+9Ch]
  _QWORD v239[16]; // [rsp+1A0h] [rbp+A0h]
  __int16 v240; // [rsp+220h] [rbp+120h]
  __int128 v241; // [rsp+230h] [rbp+130h] BYREF
  void *Src[2]; // [rsp+240h] [rbp+140h]
  void *v243[2]; // [rsp+250h] [rbp+150h]
  __int128 v244; // [rsp+260h] [rbp+160h]
  void *v245[2]; // [rsp+270h] [rbp+170h] BYREF
  __int128 v246; // [rsp+280h] [rbp+180h]
  __int128 v247; // [rsp+290h] [rbp+190h]
  __int128 v248; // [rsp+2A0h] [rbp+1A0h]
  __int128 v249; // [rsp+2B0h] [rbp+1B0h]
  PROFILEHEADER pHeader; // [rsp+2C0h] [rbp+1C0h] BYREF
  _OWORD v251[9]; // [rsp+340h] [rbp+240h] BYREF
  _DWORD v252[16]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v214 = a1;
  v185 = a3;
  v183 = a4;
  memset_0(&pHeader, 0, sizeof(pHeader));
  memset_0(v251, 0, sizeof(v251));
  memset_0(v219, 0, 0x48u);
  memset_0(&v231, 0, 0xA8u);
  v165[0] = 0;
  v211 = 0;
  v9 = 0;
  v210 = 0;
  v168 = 0;
  v208 = 1;
  v177 = 1;
  v167 = 0;
  v169 = 0;
  *a4 = 0;
  memset_0(&hProfile, 0, 0x50u);
  memset_0(&v241, 0, 0x90u);
  v10 = v202;
  if ( *(_DWORD *)(a1 + 328) == 2 )
    v10 = 1;
  v11 = *(void **)(a2 + 8);
  v163 = *(_WORD *)(a3 + 2) == 1;
  v202 = v10;
  ColorProfileHeader = GetColorProfileHeader(v11, &pHeader);
  if ( pHeader.phSignature == 1633907568 && ColorProfileHeader )
  {
    v13 = 0;
    v14 = BYTE2(pHeader.phProfileFlags) & 3;
    v173 = 0;
    v147 = *(_DWORD *)(a1 + 364) == -1;
    *(_WORD *)(a1 + 288) = v14;
    if ( !v147 )
    {
      v14 = *(_WORD *)(a1 + 364);
      *(_WORD *)(a1 + 288) = v14;
    }
    if ( v14 < 2 )
    {
      v200 = 0;
    }
    else
    {
      v200 = 1;
      v14 = 2;
      *(_WORD *)(a1 + 288) = 2;
    }
    if ( v14 )
    {
      if ( v14 == 1 )
      {
        v13 = 5462;
        goto LABEL_14;
      }
      if ( v14 != 2 )
        goto LABEL_15;
    }
    v13 = 87382;
LABEL_14:
    v173 = v13;
LABEL_15:
    v15 = *(unsigned __int16 *)(a3 + 2);
    v16 = 3 * v13;
    v180 = 3 * v13;
    v174 = 3 * v13;
    v195 = v15 - 1;
    v17 = 0;
    v205 = *(_BYTE *)(a1 + 384);
    v194 = v14;
    v206 = a1 + 392;
    v207 = a1 + 464;
    v18 = *(_DWORD *)(a1 + 292);
    v199 = 0;
    if ( v18 > 0x47524159 )
    {
      if ( v18 != 1852662636
        && v18 != 1212961568
        && v18 != 1213421088
        && v18 != 1281450528
        && v18 != 1282766368
        && v18 != 1380401696
        && v18 != 1482250784
        && v18 != 1497588338
        && v18 != 1501067552 )
      {
        goto LABEL_51;
      }
    }
    else
    {
      if ( v18 == 1196573017 )
      {
        v16 = 255;
        v180 = 255;
        v174 = 255;
        v27 = 1;
        v28 = 255;
        goto LABEL_35;
      }
      v19 = v18 - 843271250;
      if ( !v19 )
      {
        v27 = 2;
        goto LABEL_29;
      }
      v20 = v19 - 0x1000000;
      if ( v20 )
      {
        v21 = v20 - 0x1000000;
        if ( !v21 )
        {
LABEL_26:
          v27 = 4;
LABEL_29:
          v28 = (unsigned int)v16;
LABEL_35:
          CalcGridPoints4Cube(v28, v27, &v191, &v168);
LABEL_51:
          v33 = 0;
          if ( pHeader.phConnectionSpace == 1482250784 && (_WORD)v15 )
          {
            do
            {
              v34 = v33 | 1;
              if ( *(_QWORD *)(v185 + 24LL * v17 + 8) )
                v34 = v33;
              ++v17;
              v33 = v34;
            }
            while ( v17 < (unsigned __int16)v15 );
          }
          v35 = GetColorProfileHeader(*(HPROFILE *)(a2 + 8LL * *(unsigned __int16 *)(a2 + 2)), &pHeader);
          if ( pHeader.phSignature == 1633907568 && v35 )
          {
            v172 = 1;
            v175 = 2;
            v36 = 0;
            v178 = 0;
            v37 = 0;
            v209 = 0;
            v184 = 0;
            v171 = 0;
            v170 = 0;
            v217 = 0;
            v213 = 0;
            v181 = 0;
            if ( pHeader.phConnectionSpace == 1482250784 )
            {
              for ( i = 0; i < *(_WORD *)(v185 + 2); ++i )
              {
                if ( !*(_QWORD *)(v185 + 24LL * i + 8) && !a5 )
                  v33 |= 2u;
              }
            }
            v39 = v200;
            v40 = *(_DWORD *)(v214 + 328);
            if ( v40 == 2 )
              v39 = 1;
            v41 = v33 | 1;
            v42 = v33;
            v43 = v185;
            if ( v40 != 2 )
              v41 = v42;
            v44 = v39;
            v45 = 0;
            if ( v40 == 3 )
              v44 = 1;
            v200 = v44;
            v46 = v41 | 2;
            if ( v40 != 3 )
              v46 = v41;
            v176 = v46;
            while ( 1 )
            {
              v179 = v45;
              if ( (unsigned __int16)v45 >= *(_WORD *)(v43 + 2) )
              {
                DisposeIfPtr(v245[0]);
                v158 = v183;
                v147 = v175 == 1;
                v159 = v9;
                v245[0] = 0;
                v9 = 0;
                *((_QWORD *)v183 + 8) = v159;
                v158[14] = v209;
                v160 = 8;
                if ( !v147 )
                  v160 = 16;
                v138 = 0;
                v158[15] = v160;
                if ( !*v158 )
                  *v158 = 2;
                goto LABEL_350;
              }
              v196 = (unsigned __int16)v45;
              if ( v199 )
              {
                v197 = 257;
                v198 = 1;
              }
              else
              {
                HIBYTE(v197) = v200;
                v47 = *(unsigned __int16 *)(v43 + 2);
                LOBYTE(v197) = (_WORD)v45 != 0;
                v198 = (unsigned __int16)v45 != v47 - 1;
              }
              v48 = 3LL * (unsigned __int16)v45;
              v49 = *(void **)(v43 + 24LL * (unsigned __int16)v45 + 8);
              v218 = v48;
              if ( v49 )
              {
                hProfile = v49;
                v37 = 2011;
                v50 = GetColorProfileHeader(v49, &pHeader);
                if ( pHeader.phSignature != 1633907568 || !v50 )
                {
LABEL_336:
                  v138 = 0;
                  goto LABEL_350;
                }
                v37 = 0;
                phVersion = pHeader.phVersion;
                phClass = pHeader.phClass;
                phDataColorSpace = pHeader.phDataColorSpace;
                phConnectionSpace = pHeader.phConnectionSpace;
                v192 = *(_DWORD *)(v43 + 8 * v48 + 20);
                v204 = *(_BYTE *)(v43 + 8 * v48 + 28);
                v166 = 0;
              }
              else
              {
                v166 = 1;
              }
              Src[0] = (void *)DisposeIfPtr(Src[0]);
              v243[1] = (void *)DisposeIfPtr(v243[1]);
              v245[0] = (void *)DisposeIfPtr(v245[0]);
              *(_QWORD *)&v246 = DisposeIfPtr(v246);
              v245[1] = (void *)DisposeIfPtr(v245[1]);
              *((_QWORD *)&v246 + 1) = DisposeIfPtr(*((_QWORD *)&v246 + 1));
              v51 = DisposeIfPtr(*((_QWORD *)&v248 + 1));
              v52 = 0;
              *((_QWORD *)&v248 + 1) = v51;
              if ( v166 )
              {
                if ( v9 )
                {
                  if ( v36 != 3 )
                  {
                    v138 = 0;
                    goto LABEL_349;
                  }
                  v55 = v9;
                  v211 = 0;
                  v245[0] = v9;
                  v9 = 0;
                  v210 = 0;
                }
                else
                {
                  LODWORD(v244) = 3;
                  v53 = *(_DWORD *)(v214 + 292);
                  if ( v53 == 1281450528 || v53 == 1282766368 )
                    SpecialCube16 = MakeSpecialCube16(
                                      3,
                                      (unsigned int)&v174,
                                      (unsigned int)v245,
                                      (unsigned int)&v168,
                                      (__int64)&v177);
                  else
                    SpecialCube16 = MakeCube16(
                                      3,
                                      (unsigned int)&v174,
                                      (unsigned int)v245,
                                      (unsigned int)&v168,
                                      (__int64)&v177);
                  v52 = 0;
                  if ( SpecialCube16 )
                  {
                    v37 = SpecialCube16;
                    goto LABEL_351;
                  }
                  v16 = v174;
                  v180 = v174;
                  v13 = v174 / (int)v244;
                  v173 = v174 / (int)v244;
                  v209 = 1 << v168;
                  v184 = 1 << v168;
                  if ( !(_WORD)v179 )
                  {
                    DWORD1(v241) = 256;
                    DWORD2(v244) = 1 << v168;
                    DWORD2(v241) = (_BYTE)v197 != 0 ? 16 : 10;
                  }
                  v55 = v245[0];
                  v181 = 3;
                  v37 = 0;
                  v208 = v177;
                }
                if ( *(_WORD *)(v43 + 8 * v48 + 16) == 2 )
                {
                  if ( v167 == 2 )
                  {
                    LabNewEncodingToLegacyEncoding(v55, v13, 0);
                    v55 = v245[0];
                  }
                  Lab2XYZ_forCube16(v55, v13, v52);
                  v167 = 0;
                  v169 = 0;
                }
                else if ( *(_WORD *)(v43 + 8 * v48 + 16) == 1 )
                {
                  XYZ2Lab_forCube16(v55, v13, 0);
                  v167 = 1;
                  v169 = 1;
                }
                v56 = 1;
                v57 = 3;
                *(_QWORD *)&v244 = 0x300000003LL;
                v58 = 3;
              }
              else
              {
                if ( !a5 || (v59 = *(unsigned __int16 *)(v43 + 2) - 1, v201 = 1, (unsigned __int16)v179 != v59) )
                  v201 = 0;
                v203 = *(_BYTE *)(v43 + 8 * v48 + 18);
                v60 = v176 & 1;
                if ( (v176 & 1) != 0 && v195 > 0 )
                {
                  v171 = HIBYTE(v197);
                  v195 = 0;
                  HIBYTE(v197) = 1;
                }
                v61 = v176 & 2;
                if ( (v176 & 2) != 0 )
                {
                  v62 = v198;
                  v170 = v198;
                  v198 = 1;
                }
                else
                {
                  v62 = v170;
                }
                v63 = ExtractAllLuts(&v241, &hProfile, 0, 1);
                v64 = v184;
                v37 = v63;
                if ( *(_WORD *)(v185 + 2) == 1 )
                  v64 = DWORD2(v244);
                v184 = v64;
                if ( v60 )
                {
                  v65 = HIBYTE(v197);
                  v195 = *(unsigned __int16 *)(v185 + 2) - 1;
                  if ( v195 > 0 )
                    v65 = v171;
                  HIBYTE(v197) = v65;
                }
                v66 = v198;
                if ( v61 )
                  v66 = v62;
                v198 = v66;
                if ( v63 )
                {
LABEL_342:
                  v138 = 0;
                  goto LABEL_350;
                }
                v57 = v244;
                if ( !(_DWORD)v244 )
                  goto LABEL_340;
                v58 = DWORD1(v244);
                if ( !DWORD1(v244) )
                  goto LABEL_340;
                v56 = v163;
              }
              v67 = v56;
              if ( (_QWORD)v246 )
                v67 = 0;
              v216 = v67;
              if ( v172 )
              {
                if ( (_BYTE)v67 )
                {
                  v209 = DWORD2(v244);
                }
                else
                {
                  if ( v57 == 1 )
                    v16 = 255;
                  v174 = v16;
                  v68 = *(_DWORD *)(v214 + 292);
                  if ( v68 == 1281450528 || v68 == 1282766368 )
                    Cube16 = MakeSpecialCube16(
                               v57,
                               (unsigned int)&v174,
                               (unsigned int)&v210,
                               (unsigned int)&v168,
                               (__int64)&v177);
                  else
                    Cube16 = MakeCube16(
                               v57,
                               (unsigned int)&v174,
                               (unsigned int)&v210,
                               (unsigned int)&v168,
                               (__int64)&v177);
                  v9 = v210;
                  v37 = Cube16;
                  if ( Cube16 )
                    goto LABEL_342;
                  v16 = v174;
                  v57 = v244;
                  v180 = v174;
                  v13 = v174 / (int)v244;
                  v173 = v174 / (int)v244;
                  v208 = v177;
                  v209 = 1 << v168;
                  v184 = 1 << v168;
                  v181 = v244;
                  v211 = v210;
                }
                v70 = v57 * DWORD1(v241);
                if ( SDWORD2(v241) > 8 )
                  v70 *= 2;
                v71 = (unsigned int)(v70 + 2);
                if ( (v176 & 1) != 0 )
                {
                  v72 = SmartNewPtr(v71, v165);
                  v73 = v183;
                  v74 = 0;
                  v37 = v165[0];
                  v75 = v72;
                  *((_QWORD *)v183 + 2) = v72;
                  if ( v37 )
                    goto LABEL_339;
                  v76 = v70 / (int)v244;
                  v182 = v70 / (int)v244;
                  if ( (_BYTE)v197 || v200 )
                  {
                    Size = v76;
                    v77 = (unsigned __int64)v76 >> 1;
                    CreateLinearElut16(v75, (unsigned int)v77);
                    v78 = 16;
                    v215 = v77;
                  }
                  else
                  {
                    Size = v76;
                    v77 = (unsigned __int64)v76 >> 1;
                    v215 = v77;
                    CreateLinearElut(v75, (unsigned int)v77);
                    v78 = 10;
                  }
                  v73[2] = v78;
                  v57 = v244;
                  if ( (int)v244 > 0 )
                  {
                    v79 = Size;
                    v80 = v182;
                    v81 = v183;
                    do
                    {
                      memmove_0((void *)(*((_QWORD *)v81 + 2) + v80 * v74), *((const void **)v81 + 2), v79);
                      v57 = v244;
                      ++v74;
                    }
                    while ( v74 < (int)v244 );
                    v9 = v211;
                    v13 = v173;
                    v16 = v180;
                    LODWORD(v77) = v215;
                  }
                  v82 = v183;
                  LOBYTE(v176) = v176 & 0xFE;
                  v183[1] = v77;
                  v83 = v82;
                  v82[12] = v57;
                }
                else
                {
                  v84 = (void **)v183;
                  v183[2] = DWORD2(v241);
                  v84[2] = Src[0];
                  v84[3] = Src[1];
                  *((_DWORD *)v84 + 1) = DWORD1(v241);
                  *((_DWORD *)v84 + 12) = v57;
                  v85 = malloc_0((int)v71);
                  Src[0] = v85;
                  v86 = v85 == 0 ? 8 : 0;
                  v37 = v86;
                  v165[0] = v86;
                  if ( v86 )
                  {
                    v138 = 0;
                    goto LABEL_350;
                  }
                  v182 = v70 / v57;
                  v215 = v70 / v57;
                  v87 = v215 >> 1;
                  Size = v215 >> 1;
                  CreateLinearElut16(v85, (unsigned int)(v215 >> 1));
                  v57 = v244;
                  v88 = 0;
                  if ( (int)v244 > 0 )
                  {
                    v89 = v182;
                    v90 = v215;
                    do
                    {
                      memmove_0((char *)Src[0] + v89 * v88, Src[0], v90);
                      v57 = v244;
                      ++v88;
                    }
                    while ( v88 < (int)v244 );
                    v9 = v211;
                    v13 = v173;
                    LODWORD(v87) = Size;
                  }
                  v83 = v183;
                  *(_QWORD *)((char *)&v241 + 4) = (unsigned int)v87 | 0x1000000000LL;
                }
                v172 = 0;
                v91 = *(_DWORD *)(v214 + 292);
                if ( v91 != 1281450528 && v91 != 1282766368 )
                  goto LABEL_169;
                if ( (unsigned int)v184 <= 1 )
                  goto LABEL_340;
                v92 = (unsigned __int16 *)*((_QWORD *)v83 + 2);
                v93 = v83[1] / 2;
                LODWORD(Size) = v93;
                v94 = v93 - 1;
                v95 = (unsigned int)(v93 + v184 * ((v83[1] << 15) - 0x8000)) / v83[1] + v184 / 2;
                v83 = v183;
                v96 = v95 / (v184 - 1);
                v97 = (1 << v183[2]) - 1;
                v182 = v96;
                v98 = 0;
                if ( *((_WORD *)v183 + 24) )
                {
                  do
                  {
                    for ( j = 0; j <= v93; ++j )
                    {
                      v100 = (v96 * *v92 + 0x4000) >> 15;
                      *v92 = v100;
                      if ( (unsigned __int16)v100 > v97 )
                        *v92 = v97;
                      ++v92;
                    }
                    v101 = 1;
                    if ( v94 >= 1 )
                    {
                      do
                      {
                        v102 = (*v92 * ((((unsigned int)v94 >> 1) + v96 * (v94 - v101) + (v101 << 15)) / v94) + 0x4000) >> 15;
                        *v92 = v102;
                        if ( (unsigned __int16)v102 > v97 )
                          *v92 = v97;
                        v96 = v182;
                        ++v92;
                        ++v101;
                      }
                      while ( v101 <= v94 );
                      v93 = Size;
                    }
                    v83 = v183;
                    ++v98;
                  }
                  while ( v98 < *((_WORD *)v183 + 24) );
                  v13 = v173;
                  v58 = DWORD1(v244);
                  v57 = v244;
                }
                else
                {
LABEL_169:
                  v58 = DWORD1(v244);
                }
              }
              else
              {
                v83 = v183;
              }
              v103 = v185;
              v104 = 1;
              v105 = v179;
              if ( (unsigned __int16)v179 == *(unsigned __int16 *)(v185 + 2) - 1 )
              {
                v106 = v176 & 2;
                if ( (v176 & 2) != 0 )
                {
                  v217 = v243[1];
                  v213 = v243[0];
                }
                else
                {
                  *((void **)v83 + 5) = v243[1];
                  *((void **)v83 + 4) = v243[0];
                }
                v83[13] = v58;
                if ( v198 || v200 )
                {
                  v109 = malloc_0((v58 << 11) + 2);
                  v243[1] = v109;
                  v37 = v109 == 0 ? 8 : 0;
                  v165[0] = v109 == 0 ? 8 : 0;
                  if ( (v109 == 0 ? 8 : 0) != 0 )
                    goto LABEL_336;
                  CreateLinearAlut16(v109);
                  v58 = DWORD1(v244);
                  v104 = 1;
                  v110 = 1;
                  if ( SDWORD1(v244) > 1 )
                  {
                    do
                    {
                      memmove_0((char *)v243[1] + 2048 * v110, v243[1], 0x800u);
                      v58 = DWORD1(v244);
                      ++v110;
                    }
                    while ( v110 < SDWORD1(v244) );
                    v13 = v173;
                    v104 = 1;
                  }
                  HIDWORD(v243[0]) = 16;
                }
                else
                {
                  v107 = (void *)SmartNewPtr((unsigned int)((v58 << 10) + 1), v165);
                  v37 = v165[0];
                  v243[1] = v107;
                  if ( v165[0] )
                    goto LABEL_336;
                  CreateLinearAlut(v107);
                  v58 = DWORD1(v244);
                  v104 = v37 + 1;
                  v108 = v37 + 1;
                  if ( SDWORD1(v244) > (int)(v37 + 1) )
                  {
                    do
                    {
                      memmove_0((char *)v243[1] + 1024 * v108, v243[1], 0x400u);
                      v58 = DWORD1(v244);
                      ++v108;
                    }
                    while ( v108 < SDWORD1(v244) );
                    v13 = v173;
                    v104 = 1;
                  }
                  HIDWORD(v243[0]) = 8;
                  v175 = v104;
                }
                v111 = v183;
                v103 = v185;
                v147 = v106 == 0;
                v57 = v244;
                LODWORD(v243[0]) = 1024;
                if ( !v147 )
                {
                  LOBYTE(v176) = v176 & 0xFD;
                  *((void **)v183 + 5) = v243[1];
                  v111[9] = HIDWORD(v243[0]);
                  v243[1] = v217;
                  v243[0] = v213;
                  v111[8] = 1024;
                }
              }
              else
              {
                v111 = v183;
              }
              if ( !(_BYTE)v216 )
                break;
              if ( (_WORD)v104 == *(_WORD *)(v103 + 2) )
              {
                v112 = v241;
                if ( (_DWORD)v241 == 3 )
                {
                  for ( k = 0; k < v57; v252[v114] = *((unsigned __int8 *)&v247 + v114) )
                  {
                    v114 = k;
                    k += v104;
                  }
                  for ( m = 0; m < v57; *((_BYTE *)v111 + v116 + 96) = v252[v116] )
                  {
                    v116 = m;
                    m += v104;
                  }
                  *((_QWORD *)v111 + 14) = v248;
                  *((_QWORD *)v111 + 11) = *((_QWORD *)&v246 + 1);
                  *((_QWORD *)v111 + 15) = *((_QWORD *)&v248 + 1);
                  *((_QWORD *)&v246 + 1) = 0;
                  *((_QWORD *)&v248 + 1) = 0;
                }
                else
                {
                  if ( (_DWORD)v241 != 2 )
                    goto LABEL_340;
                  v117 = 0;
                  if ( v57 > 0 )
                  {
                    do
                      v117 += v104;
                    while ( v117 < v57 );
                    v118 = DWORD2(v244);
                    v119 = v252;
                    for ( n = v57; n; --n )
                      *v119++ = v118;
                  }
                }
                *v111 = v112;
                v121 = v104;
                v122 = v58;
                for ( ii = 0; ii < v57; ii += v104 )
                {
                  v124 = v252[ii];
                  if ( !v124 || v122 > 0x7FFFFFFF / v124 )
                    goto LABEL_340;
                  v122 *= v124;
                  if ( ii < v57 - 1 )
                  {
                    if ( v121 > 0x7FFFFFFF - v122 )
                      goto LABEL_340;
                    v121 += v122;
                  }
                }
                if ( v121 > 0x7FFFFFFF / v58 )
                {
LABEL_340:
                  v138 = 0;
                  goto LABEL_349;
                }
                v125 = v58 * v121;
                v208 = v125;
                v177 = v125;
                DisposeIfPtr(v9);
                v126 = (unsigned int)(v125 + v122);
                if ( v200 )
                {
                  v127 = 2 * v126;
                  v128 = (char *)SmartNewPtr((unsigned int)(2 * v126), v165);
                  v37 = v165[0];
                  v9 = v128;
                  if ( v165[0] )
                    goto LABEL_339;
                  memset_0(v128, 0, v127);
                  v129 = (unsigned __int8 *)v245[0];
                  if ( HIDWORD(v244) == 8 )
                  {
                    for ( jj = 0; jj < v122; *(_WORD *)&v9[2 * v131] = v129[v131] | (v129[v131] << 8) )
                      v131 = jj++;
                  }
                  else
                  {
                    memmove_0(v9, v245[0], 2 * v122);
                  }
                  HIDWORD(v244) = 16;
                }
                else
                {
                  v132 = (char *)SmartNewPtr(v126, v165);
                  v37 = v165[0];
                  v9 = v132;
                  if ( v165[0] )
                  {
LABEL_339:
                    v138 = 0;
                    goto LABEL_350;
                  }
                  memmove_0(v132, v245[0], v122);
                  DisposeIfPtr(v245[0]);
                  HIDWORD(v244) = 8;
                }
                v245[0] = v9;
                v9 = 0;
              }
              DisposeIfPtr(v9);
              v9 = (char *)v245[0];
              v211 = (char *)v245[0];
              v210 = (char *)v245[0];
              if ( v245[0] )
              {
                v16 = v13 * v244 * DWORD1(v244);
                v180 = v16;
                v174 = v16;
              }
              v43 = v185;
              v45 = v179;
              v245[0] = 0;
              if ( (unsigned __int16)v179 == *(unsigned __int16 *)(v185 + 2) - 1 && !v198 && !v200 )
                v175 = 1;
LABEL_326:
              v163 = 0;
              if ( pHeader.phClass == 1818848875 )
              {
                v157 = pHeader.phConnectionSpace;
                phDataColorSpace = pHeader.phConnectionSpace;
                v202 = 1;
              }
              else
              {
                v157 = phDataColorSpace;
              }
              if ( !v202 || v166 || v203 || v157 == 1281450528 || (v202 = 0, v157 == 1482250784) )
                v202 = 1;
              v36 = v181;
              LOWORD(v45) = v45 + 1;
            }
            if ( v181 != v57 )
              goto LABEL_340;
            if ( v202 )
            {
              if ( v181 != 3 )
                goto LABEL_340;
              v133 = v193;
              v134 = v178;
              if ( v193 != v178 )
              {
                if ( phConnectionSpace == 1281450528 )
                {
                  Lab2XYZ_forCube16(v9, v13, v105);
                  v134 = v178;
                }
                if ( v133 == 2 && v134 == 1 )
                  AdjustBlackPointFromLegacyToV4Perceptual(v9, v13, v105, v111);
                else
                  AdjustBlackPointFromV4PerceptualToLegacy(v9, v13, v105, v111);
                if ( phConnectionSpace == 1281450528 )
                  XYZ2Lab_forCube16(v9, v13, v105);
                v58 = DWORD1(v244);
                v57 = v244;
              }
            }
            if ( (_DWORD)v241 == 1 )
            {
              v219[2] = DWORD2(v241);
              v219[0] = DWORD1(v241);
              v221 = Src[0];
              v224 = HIDWORD(v243[0]);
              v222 = (int)v243[0];
              v226 = v243[1];
              v227 = v245[1];
              v220 = 1;
              v225 = 1;
              v229 = v175;
              v219[1] = 0;
              v223 = 0;
              v228 = v13;
              v230 = v9;
              DoMatrixForCube16(v219);
              v156 = v178;
              v167 = 0;
              if ( !v202 )
                v156 = v193;
              v178 = v156;
              v155 = DWORD1(v244);
              v169 = 0;
              goto LABEL_325;
            }
            if ( (_DWORD)v241 != 2 && (unsigned int)(v241 - 3) > 1 )
              goto LABEL_340;
            v135 = 0;
            if ( v202 )
            {
              if ( phConnectionSpace == 1281450528 )
              {
                LOBYTE(v135) = (_DWORD)v241 != 2;
                ++v135;
              }
              if ( v204 && v205 && v192 )
              {
                if ( phConnectionSpace == 1281450528 )
                {
                  if ( v167 == 2 )
                    LabNewEncodingToLegacyEncoding(v9, v13, v105);
                  Lab2XYZ_forCube16(v9, v13, v105);
                }
                ApplyChromaticAdaptationCorrection(v9, v13, v207);
                if ( phConnectionSpace == 1281450528 )
                {
                  XYZ2Lab_forCube16(v9, v13, v136);
                  v167 = 1;
                  v169 = 1;
                }
                v57 = v244;
                v58 = DWORD1(v244);
              }
              if ( v202 && *(_DWORD *)(v185 + 8 * v218 + 20) == 3 && !*(_WORD *)(v185 + 8 * v218 + 18) )
              {
                v37 = DoAbsoluteShiftForPCS_Cube16((int)v9, v13, phConnectionSpace, (int)&v169, hProfile, 0);
                if ( v37 )
                  goto LABEL_342;
                v58 = DWORD1(v244);
                v57 = v244;
                v167 = v169;
              }
            }
            if ( (_QWORD)v246 )
            {
              DoOnlyMatrixForCube16(v246, v9, v13);
              v58 = DWORD1(v244);
              v57 = v244;
            }
            v137 = v175;
            if ( v57 >= v58 && v175 == 2 )
            {
              v138 = v9;
              v164 = 0;
              v231 = 0x4000;
            }
            else
            {
              v138 = (char *)malloc_0((int)(v175 * v58 * (v13 + v208)));
              v139 = v138 != 0 ? 0 : 8;
              v37 = v139;
              v165[0] = v139;
              if ( v139 )
                goto LABEL_350;
              v137 = v175;
              v231 = 0x4000;
              v164 = 1;
              v232 = 0x2000;
              if ( v175 == 1 )
              {
LABEL_272:
                v233 = v13;
                v237 = 2 * v57;
                v140 = 0;
                v234 = 1;
                v238 = v137 * v58;
                v235 = v13 * 2 * v57;
                for ( kk = v13 * v137 * v58; v140 < v57; v239[v141] = &v9[2 * v141] )
                  v141 = v140++;
                for ( mm = 0; (int)mm < v58; v239[v143 + 8] = v144 )
                {
                  v143 = (int)mm;
                  v144 = &v138[(int)mm * (int)v137];
                  mm = (unsigned int)(mm + 1);
                }
                v240 = 0;
                if ( (unsigned int)(v241 - 3) > 1 )
                {
                  v37 = FillDescaledInputLut(&v241, mm);
                  if ( v37 )
                    goto LABEL_350;
                }
                v145 = v167;
                v251[0] = v241;
                v251[2] = *(_OWORD *)v243;
                v251[1] = *(_OWORD *)Src;
                v251[4] = *(_OWORD *)v245;
                v251[3] = v244;
                v251[6] = v247;
                v251[5] = v246;
                v251[8] = v249;
                v251[7] = v248;
                if ( v167 == 1 )
                {
                  if ( v135 == 2 )
                    LabLegacyEncodingToNewEncoding(v9, v13);
                }
                else if ( v167 == 2 && v135 == 1 )
                {
                  LabNewEncodingToLegacyEncoding(v9, v13, v137);
                }
                v146 = v185;
                if ( (unsigned __int16)v179 >= *(unsigned __int16 *)(v185 + 2) - 1 )
                {
LABEL_297:
                  v37 = CalcNDim_Data8To8_Lut16(&v231, v251);
                  v148 = (void *)DisposeIfPtr(Src[1]);
                  v149 = 0;
                  Src[1] = v148;
                  if ( v37 )
                    goto LABEL_350;
                  v147 = *(_WORD *)(v146 + 8 * v218 + 18) == 0;
                  v150 = v146 + 8 * v218;
                  if ( v147 )
                  {
                    v151 = (_DWORD *)(v150 + 20);
                  }
                  else
                  {
                    v151 = (_DWORD *)(v150 + 20);
                    if ( *v151 == 3 )
                    {
                      v152 = DoAbsoluteShiftForPCS_Cube16((int)v138, v13, phConnectionSpace, (int)&v169, hProfile, 1);
                      v149 = 0;
                      v37 = v152;
                      if ( v152 )
                        goto LABEL_350;
                      v145 = v169;
                      v167 = v169;
LABEL_304:
                      if ( !v202 )
                      {
                        if ( *v151 != 3 )
                        {
LABEL_309:
                          if ( v204 && v205 && v192 )
                          {
                            if ( phConnectionSpace == 1281450528 )
                            {
                              if ( v145 == 2 )
                                LabNewEncodingToLegacyEncoding(v138, v13, 0);
                              Lab2XYZ_forCube16(v138, v13, v149);
                            }
                            v37 = ApplyChromaticAdaptationCorrection(v138, v13, v206);
                            if ( phConnectionSpace == 1281450528 )
                            {
                              XYZ2Lab_forCube16(v138, v13, v154);
                              v167 = 1;
                              v169 = 1;
                            }
                          }
                          goto LABEL_318;
                        }
                        v153 = DoAbsoluteShiftForPCS_Cube16((int)v138, v13, phConnectionSpace, (int)&v169, hProfile, 1);
                        v149 = 0;
                        v37 = v153;
                        if ( v153 )
                          goto LABEL_350;
                        if ( !v202 )
                        {
                          v145 = v169;
                          v167 = v169;
                          goto LABEL_309;
                        }
                        v167 = v169;
                      }
LABEL_318:
                      if ( v164 )
                      {
                        DisposeIfPtr(v9);
                        v211 = v138;
                        v9 = v138;
                        v210 = v138;
                      }
                      v155 = DWORD1(v244);
                      v16 = v13 * v175 * DWORD1(v244);
                      v180 = v16;
                      v174 = v16;
LABEL_325:
                      v43 = v185;
                      v45 = v179;
                      v181 = v155;
                      goto LABEL_326;
                    }
                  }
                  v37 = 0;
                  goto LABEL_304;
                }
                if ( v202 )
                {
                  if ( v203 != 1 )
                  {
                    if ( phDataColorSpace == 1281450528 )
                      goto LABEL_293;
                    if ( phDataColorSpace != 1482250784 )
                    {
                      v178 = 0;
                      v145 = 0;
                      v167 = 0;
LABEL_296:
                      v169 = v145;
                      goto LABEL_297;
                    }
                  }
                  v147 = phDataColorSpace == 1281450528;
                }
                else
                {
                  v147 = phConnectionSpace == 1281450528;
                }
                if ( !v147 )
                {
                  v145 = 0;
                  v167 = 0;
                  goto LABEL_295;
                }
LABEL_293:
                v145 = ((_DWORD)v241 != 2) + 1;
                v167 = v145;
LABEL_295:
                v178 = v193;
                goto LABEL_296;
              }
            }
            v232 = 0x4000;
            goto LABEL_272;
          }
          v37 = 2011;
          goto LABEL_351;
        }
        v22 = v21 - 0x1000000;
        if ( !v22 )
        {
          v27 = 5;
          goto LABEL_29;
        }
        v23 = v22 - 0x1000000;
        if ( !v23 )
        {
          v27 = 6;
          goto LABEL_29;
        }
        v24 = v23 - 0x1000000;
        if ( !v24 )
        {
          v27 = 7;
          goto LABEL_29;
        }
        v25 = v24 - 0x1000000;
        if ( !v25 )
        {
          v27 = 8;
          goto LABEL_29;
        }
        v26 = v25 - 185208014;
        if ( v26 )
        {
          if ( v26 != 43 )
            goto LABEL_51;
          goto LABEL_26;
        }
      }
    }
    v29 = 0;
    do
    {
      v30 = v29++;
      v31 = 2;
      v32 = 1 << v29;
      do
      {
        v32 *= 1 << v29;
        --v31;
      }
      while ( v31 );
    }
    while ( v16 / 3 >= v32 );
    v17 = 0;
    if ( v30 > 0 )
    {
      v168 = v30;
      v191 = 1 << v30;
    }
    goto LABEL_51;
  }
  v138 = 0;
LABEL_349:
  v37 = 2011;
LABEL_350:
  if ( v9 != v138 )
  {
    DisposeIfPtr(v9);
    v161 = v138;
    goto LABEL_353;
  }
LABEL_351:
  v161 = v9;
LABEL_353:
  DisposeIfPtr(v161);
  Src[0] = (void *)DisposeIfPtr(Src[0]);
  Src[1] = (void *)DisposeIfPtr(Src[1]);
  v243[1] = (void *)DisposeIfPtr(v243[1]);
  v245[0] = (void *)DisposeIfPtr(v245[0]);
  *(_QWORD *)&v246 = DisposeIfPtr(v246);
  v245[1] = (void *)DisposeIfPtr(v245[1]);
  *((_QWORD *)&v246 + 1) = DisposeIfPtr(*((_QWORD *)&v246 + 1));
  DisposeIfPtr(*((_QWORD *)&v248 + 1));
  return v37;
}

```

## disassembly

```asm
0x1800029a4  push    rbp
0x1800029a6  push    rbx
0x1800029a7  push    rsi
0x1800029a8  push    rdi
0x1800029a9  push    r12
0x1800029ab  push    r13
0x1800029ad  push    r14
0x1800029af  push    r15
0x1800029b1  lea     rbp, [rsp-328h]
0x1800029b9  sub     rsp, 428h
0x1800029c0  mov     rax, cs:__security_cookie
0x1800029c7  xor     rax, rsp
0x1800029ca  mov     [rbp+360h+var_50], rax
0x1800029d1  mov     rbx, r8
0x1800029d4  mov     [rbp+360h+var_358], rcx
0x1800029d8  mov     r14, rdx
0x1800029db  mov     [rbp+360h+var_3D8], rbx
0x1800029df  mov     rsi, rcx
0x1800029e2  mov     [rsp+460h+var_3E8], r9
0x1800029e7  xor     edx, edx; Val
0x1800029e9  lea     rcx, [rbp+360h+pHeader]; void *
0x1800029f0  mov     r8d, 80h; Size
0x1800029f6  mov     rdi, r9
0x1800029f9  call    memset_0
0x1800029fe  mov     r12d, 90h
0x180002a04  lea     rcx, [rbp+360h+var_120]; void *
0x180002a0b  mov     r8d, r12d; Size
0x180002a0e  xor     edx, edx; Val
0x180002a10  call    memset_0
0x180002a15  xor     edx, edx; Val
0x180002a17  lea     r8d, [r12-48h]; Size
0x180002a1c  lea     rcx, [rbp+360h+var_330]; void *
0x180002a20  call    memset_0
0x180002a25  xor     edx, edx; Val
0x180002a27  lea     r8d, [r12+18h]; Size
0x180002a2c  lea     rcx, [rbp+360h+var_2E0]; void *
0x180002a33  call    memset_0
0x180002a38  xor     r13d, r13d
0x180002a3b  lea     r8d, [r12-40h]; Size
0x180002a40  xor     edx, edx; Val
0x180002a42  mov     [rsp+460h+var_42C], r13w
0x180002a48  lea     rcx, [rbp+360h+var_3D0]; void *
0x180002a4c  mov     [rbp+360h+var_370], r13
0x180002a50  mov     r15d, r13d
0x180002a53  mov     [rbp+360h+var_378], r13
0x180002a57  lea     eax, [r13+1]
0x180002a5b  mov     [rsp+460h+var_420], r13d
0x180002a60  mov     [rbp+360h+var_380], eax
0x180002a63  mov     [rsp+460h+var_404], eax
0x180002a67  mov     eax, r13d
0x180002a6a  mov     [rsp+460h+var_424], eax
0x180002a6e  mov     [rsp+460h+var_41C], eax
0x180002a72  mov     [rdi], r13d
0x180002a75  call    memset_0
0x180002a7a  mov     r8d, r12d; Size
0x180002a7d  lea     rcx, [rbp+360h+var_230]; void *
0x180002a84  xor     edx, edx; Val
0x180002a86  call    memset_0
0x180002a8b  movzx   eax, [rbp+360h+var_39A]
0x180002a8f  lea     edi, [r13+2]
0x180002a93  cmp     [rsi+148h], edi
0x180002a99  lea     ecx, [rdi-1]
0x180002a9c  lea     rdx, [rbp+360h+pHeader]; pHeader
0x180002aa3  cmovz   eax, ecx
0x180002aa6  cmp     cx, [rbx+2]
0x180002aaa  mov     rcx, [r14+8]; hProfile
0x180002aae  setz    [rsp+460h+var_430]
0x180002ab3  mov     [rbp+360h+var_39A], al
0x180002ab6  call    cs:__imp_GetColorProfileHeader
0x180002abc  cmp     [rbp+360h+pHeader.phSignature], 61637370h
0x180002ac6  jnz     loc_180004202
0x180002acc  test    eax, eax
0x180002ace  jz      loc_180004202
0x180002ad4  mov     eax, [rbp+360h+pHeader.phProfileFlags]
0x180002ada  mov     r12d, r13d
0x180002add  shr     eax, 10h
0x180002ae0  and     ax, 3
0x180002ae4  mov     [rsp+460h+var_414], r13d
0x180002ae9  cmp     dword ptr [rsi+16Ch], 0FFFFFFFFh
0x180002af0  mov     [rsi+120h], ax
0x180002af7  jz      short loc_180002B07
0x180002af9  movzx   eax, word ptr [rsi+16Ch]
0x180002b00  mov     [rsi+120h], ax
0x180002b07  mov     r10d, 1
0x180002b0d  cmp     ax, di
0x180002b10  jl      short loc_180002B22
0x180002b12  mov     [rbp+360h+var_39C], r10b
0x180002b16  movzx   eax, di
0x180002b19  mov     [rsi+120h], di
0x180002b20  jmp     short loc_180002B26
0x180002b22  mov     [rbp+360h+var_39C], r13b
0x180002b26  movsx   edx, ax
0x180002b29  mov     ecx, edx
0x180002b2b  test    edx, edx
0x180002b2d  jz      short loc_180002B3D
0x180002b2f  sub     ecx, 1
0x180002b32  jz      loc_180002BE8
0x180002b38  cmp     ecx, 1
0x180002b3b  jnz     short loc_180002B48
0x180002b3d  mov     r12d, 15556h
0x180002b43  mov     [rsp+460h+var_414], r12d
0x180002b48  movzx   ebx, word ptr [rbx+2]
0x180002b4c  lea     r13d, [r12+r12*2]
0x180002b50  mov     eax, ebx
0x180002b52  mov     [rsp+460h+var_3F8], r13d
0x180002b57  sub     eax, r10d
0x180002b5a  mov     [rsp+460h+var_410], r13d
0x180002b5f  mov     [rbp+360h+var_3A8], eax
0x180002b62  xor     edi, edi
0x180002b64  mov     al, [rsi+180h]
0x180002b6a  mov     ecx, 47524159h
0x180002b6f  mov     [rbp+360h+var_397], al
0x180002b72  mov     r11d, 0FFh
0x180002b78  lea     rax, [rsi+188h]
0x180002b7f  mov     [rbp+360h+var_3AC], edx
0x180002b82  mov     [rbp+360h+var_390], rax
0x180002b86  lea     rax, [rsi+1D0h]
0x180002b8d  mov     [rbp+360h+var_388], rax
0x180002b91  mov     eax, [rsi+124h]
0x180002b97  mov     [rbp+360h+var_39D], dil
0x180002b9b  cmp     eax, ecx
0x180002b9d  ja      loc_180002C45
0x180002ba3  jz      short loc_180002C19
0x180002ba5  sub     eax, 32434C52h
0x180002baa  jz      short loc_180002C12
0x180002bac  mov     ecx, 1000000h
0x180002bb1  sub     eax, ecx
0x180002bb3  jz      loc_180002C84
0x180002bb9  sub     eax, ecx
0x180002bbb  jz      short loc_180002BE1
0x180002bbd  sub     eax, ecx
0x180002bbf  jz      short loc_180002C0B
0x180002bc1  sub     eax, ecx
0x180002bc3  jz      short loc_180002C04
0x180002bc5  sub     eax, ecx
0x180002bc7  jz      short loc_180002BFD
0x180002bc9  sub     eax, ecx
0x180002bcb  jz      short loc_180002BF3
0x180002bcd  sub     eax, 0B0A0CCEh
0x180002bd2  jz      loc_180002C84
0x180002bd8  cmp     eax, 2Bh ; '+'
0x180002bdb  jnz     loc_180002CCB
0x180002be1  mov     edx, 4
0x180002be6  jmp     short loc_180002BF8
0x180002be8  mov     r12d, 1556h
0x180002bee  jmp     loc_180002B43
0x180002bf3  mov     edx, 8
0x180002bf8  mov     ecx, r13d
0x180002bfb  jmp     short loc_180002C2C
0x180002bfd  mov     edx, 7
0x180002c02  jmp     short loc_180002BF8
0x180002c04  mov     edx, 6
0x180002c09  jmp     short loc_180002BF8
0x180002c0b  mov     edx, 5
0x180002c10  jmp     short loc_180002BF8
0x180002c12  mov     edx, 2
0x180002c17  jmp     short loc_180002BF8
0x180002c19  mov     r13d, r11d
0x180002c1c  mov     [rsp+460h+var_3F8], r11d
0x180002c21  mov     [rsp+460h+var_410], r11d
0x180002c26  mov     edx, r10d
0x180002c29  mov     ecx, r11d
0x180002c2c  lea     r9, [rsp+460h+var_420]
0x180002c31  lea     r8, [rbp+360h+var_3B8]
0x180002c35  call    CalcGridPoints4Cube
0x180002c3a  mov     r10d, 1
0x180002c40  jmp     loc_180002CCB
0x180002c45  cmp     eax, 6E6D636Ch
0x180002c4a  jz      short loc_180002C84
0x180002c4c  cmp     eax, 484C5320h
0x180002c51  jz      short loc_180002C84
0x180002c53  cmp     eax, 48535620h
0x180002c58  jz      short loc_180002C84
0x180002c5a  cmp     eax, 4C616220h
0x180002c5f  jz      short loc_180002C84
0x180002c61  cmp     eax, 4C757620h
0x180002c66  jz      short loc_180002C84
0x180002c68  cmp     eax, 52474220h
0x180002c6d  jz      short loc_180002C84
0x180002c6f  cmp     eax, 58595A20h
0x180002c74  jz      short loc_180002C84
0x180002c76  cmp     eax, 59436272h
0x180002c7b  jz      short loc_180002C84
0x180002c7d  cmp     eax, 59787920h
0x180002c82  jnz     short loc_180002CCB
0x180002c84  mov     eax, 55555556h
0x180002c89  mov     ecx, edi
0x180002c8b  imul    r13d
0x180002c8e  mov     eax, edx
0x180002c90  shr     eax, 1Fh
0x180002c93  add     edx, eax
0x180002c95  mov     r8d, ecx
0x180002c98  mov     eax, r10d
0x180002c9b  add     ecx, r10d
0x180002c9e  mov     r9d, 2
0x180002ca4  shl     eax, cl
0x180002ca6  mov     edi, eax
0x180002ca8  imul    edi, eax
0x180002cab  sub     r9d, r10d
0x180002cae  jnz     short loc_180002CA8
0x180002cb0  cmp     edx, edi
0x180002cb2  jge     short loc_180002C95
0x180002cb4  xor     edi, edi
0x180002cb6  test    r8d, r8d
0x180002cb9  jle     short loc_180002CCB
0x180002cbb  mov     ecx, r8d
0x180002cbe  mov     [rsp+460h+var_420], r8d
0x180002cc3  mov     eax, r10d
0x180002cc6  shl     eax, cl
0x180002cc8  mov     [rbp+360h+var_3B8], eax
0x180002ccb  cmp     [rbp+360h+pHeader.phConnectionSpace], 58595A20h
0x180002cd5  mov     sil, dil
0x180002cd8  jnz     short loc_180002D0F
0x180002cda  xor     r9d, r9d
0x180002cdd  cmp     r9w, bx
0x180002ce1  jnb     short loc_180002D0F
0x180002ce3  mov     r8, [rbp+360h+var_3D8]
0x180002ce7  movzx   eax, di
0x180002cea  lea     rcx, [rax+rax*2]
0x180002cee  mov     al, sil
0x180002cf1  or      al, r10b
0x180002cf4  cmp     [r8+rcx*8+8], r9
0x180002cf9  movzx   edx, al
0x180002cfc  movzx   eax, sil
0x180002d00  cmovnz  edx, eax
0x180002d03  add     di, r10w
0x180002d07  mov     sil, dl
0x180002d0a  cmp     di, bx
0x180002d0d  jb      short loc_180002CE7
0x180002d0f  movzx   ecx, word ptr [r14+2]
0x180002d14  lea     rdx, [rbp+360h+pHeader]; pHeader
0x180002d1b  mov     rcx, [r14+rcx*8]; hProfile
0x180002d1f  call    cs:__imp_GetColorProfileHeader
0x180002d25  cmp     [rbp+360h+pHeader.phSignature], 61637370h
0x180002d2f  jnz     loc_1800041FB
0x180002d35  xor     r8d, r8d
0x180002d38  test    eax, eax
0x180002d3a  jz      loc_1800041FB
0x180002d40  cmp     [rbp+360h+pHeader.phConnectionSpace], 58595A20h
0x180002d4a  lea     r9d, [r8+1]
0x180002d4e  lea     r10d, [r8+2]
0x180002d52  mov     [rsp+460h+var_416], r9b
0x180002d57  mov     [rsp+460h+var_40C], r10d
0x180002d5c  mov     r14d, r8d
0x180002d5f  mov     [rsp+460h+var_400], r8d
0x180002d64  mov     ebx, r8d
0x180002d67  mov     [rbp+360h+var_37C], r8d
0x180002d6b  mov     [rbp+360h+var_3E0], r8d
0x180002d6f  mov     [rsp+460h+var_417], r8b
0x180002d74  mov     [rsp+460h+var_418], r8b
0x180002d79  mov     [rbp+360h+var_340], r8
0x180002d7d  mov     dword ptr [rbp+360h+var_360], r8d
0x180002d81  mov     dword ptr [rbp+360h+var_360+4], r8d
0x180002d85  mov     [rsp+460h+var_3F4], r8d
0x180002d8a  jnz     short loc_180002DBE
0x180002d8c  mov     rdi, [rbp+360h+var_3D8]
0x180002d90  mov     edx, r8d
0x180002d93  cmp     r8w, [rdi+2]
0x180002d98  jnb     short loc_180002DBE
0x180002d9a  movzx   eax, dx
0x180002d9d  lea     rcx, [rax+rax*2]
0x180002da1  cmp     [rdi+rcx*8+8], r8
0x180002da6  jnz     short loc_180002DB4
0x180002da8  cmp     [rbp+360h+arg_20], r8b
0x180002daf  jnz     short loc_180002DB4
0x180002db1  or      sil, r10b
0x180002db4  add     dx, r9w
0x180002db8  cmp     dx, [rdi+2]
0x180002dbc  jb      short loc_180002D9A
0x180002dbe  movzx   edx, [rbp+360h+var_39C]
0x180002dc2  mov     al, sil
0x180002dc5  mov     rdi, [rbp+360h+var_358]
0x180002dc9  mov     edi, [rdi+148h]
0x180002dcf  cmp     edi, r10d
0x180002dd2  cmovz   edx, r9d
0x180002dd6  or      al, r9b
0x180002dd9  movzx   ecx, al
0x180002ddc  cmp     edi, r10d
0x180002ddf  movzx   eax, sil
0x180002de3  mov     rsi, [rbp+360h+var_3D8]
0x180002de7  cmovnz  ecx, eax
0x180002dea  cmp     edi, 3
0x180002ded  movzx   eax, dl
0x180002df0  movzx   ecx, cl
0x180002df3  mov     edx, r8d
0x180002df6  cmovz   eax, r9d
0x180002dfa  mov     [rbp+360h+var_39C], al
0x180002dfd  mov     al, cl
0x180002dff  or      al, r10b
0x180002e02  cmp     edi, 3
0x180002e05  movzx   eax, al
0x180002e08  cmovnz  eax, ecx
0x180002e0b  mov     [rsp+460h+var_408], eax
0x180002e0f  mov     [rsp+460h+var_3FC], edx
0x180002e13  cmp     dx, [rsi+2]
0x180002e17  jnb     loc_1800041B2
0x180002e1d  movzx   ecx, dx
0x180002e20  mov     [rbp+360h+var_3A4], ecx
0x180002e23  cmp     [rbp+360h+var_39D], r8b
0x180002e27  jz      short loc_180002E35
  ... truncated ...
```
