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
  unsigned __int16 *v9; // r15
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
  int v45; // edx
  int v46; // eax
  int v47; // eax
  __int64 v48; // rdi
  void *v49; // rcx
  BOOL v50; // eax
  int v51; // eax
  __int16 SpecialCube16; // ax
  unsigned __int16 *v53; // rcx
  unsigned __int8 v54; // al
  int v55; // esi
  int v56; // r14d
  int v57; // eax
  char v58; // si
  char v59; // di
  bool v60; // r14
  unsigned int v61; // eax
  int v62; // r8d
  char v63; // dl
  bool v64; // cl
  int v65; // ecx
  int v66; // eax
  __int16 Cube16; // ax
  int v68; // edi
  __int64 v69; // rcx
  __int64 v70; // rax
  _DWORD *v71; // rsi
  int v72; // r14d
  __int64 v73; // rcx
  int v74; // eax
  size_t v75; // rdi
  int v76; // ecx
  size_t v77; // rdi
  int v78; // r12d
  _DWORD *v79; // r15
  _DWORD *v80; // rax
  _DWORD *v81; // rdi
  void **v82; // rdx
  void *v83; // r8
  unsigned __int16 v84; // dx
  size_t v85; // r14
  int v86; // edi
  int v87; // r12d
  size_t v88; // r14
  int v89; // eax
  unsigned __int16 *v90; // r8
  int v91; // r9d
  int v92; // r10d
  unsigned int v93; // eax
  unsigned int v94; // edx
  unsigned __int16 v95; // r11
  unsigned __int16 v96; // r14
  int j; // ecx
  unsigned int v98; // eax
  int v99; // edi
  unsigned int v100; // eax
  __int64 v101; // rcx
  int v102; // r11d
  char v103; // si
  void *v104; // rax
  int v105; // edi
  void *v106; // rax
  int v107; // edi
  _DWORD *v108; // r9
  int v109; // r8d
  int k; // edx
  __int64 v111; // rcx
  int m; // edx
  __int64 v113; // rcx
  int v114; // eax
  int v115; // eax
  _DWORD *v116; // rdi
  __int64 n; // rcx
  int v118; // ebx
  int v119; // edi
  int ii; // ecx
  int v121; // r8d
  int v122; // ebx
  __int64 v123; // rcx
  unsigned int v124; // esi
  unsigned __int16 *v125; // rax
  unsigned __int8 *v126; // r9
  int jj; // r8d
  __int64 v128; // rdx
  unsigned __int16 *v129; // rax
  int v130; // edi
  int v131; // eax
  int v132; // r13d
  int v133; // r8d
  unsigned __int16 *v134; // rdi
  unsigned __int16 v135; // cx
  int v136; // edx
  __int64 v137; // rcx
  int mm; // edx
  __int64 v139; // rax
  char *v140; // rcx
  int v141; // r14d
  __int64 v142; // rsi
  bool v143; // zf
  __int64 v144; // rsi
  _DWORD *v145; // rsi
  int v146; // eax
  int v147; // eax
  DWORD v148; // eax
  _DWORD *v149; // rcx
  unsigned __int16 *v150; // rax
  int v151; // eax
  unsigned __int16 *v152; // rcx
  bool v154; // [rsp+30h] [rbp-D0h]
  char v155; // [rsp+30h] [rbp-D0h]
  _WORD v156[2]; // [rsp+34h] [rbp-CCh] BYREF
  char v157; // [rsp+38h] [rbp-C8h]
  int v158; // [rsp+3Ch] [rbp-C4h]
  int v159; // [rsp+40h] [rbp-C0h] BYREF
  int v160; // [rsp+44h] [rbp-BCh] BYREF
  bool v161; // [rsp+48h] [rbp-B8h]
  char v162; // [rsp+49h] [rbp-B7h]
  char v163; // [rsp+4Ah] [rbp-B6h]
  int v164; // [rsp+4Ch] [rbp-B4h]
  int v165; // [rsp+50h] [rbp-B0h] BYREF
  int v166; // [rsp+54h] [rbp-ACh]
  int v167; // [rsp+58h] [rbp-A8h]
  int v168; // [rsp+5Ch] [rbp-A4h] BYREF
  int v169; // [rsp+60h] [rbp-A0h]
  int v170; // [rsp+64h] [rbp-9Ch]
  int v171; // [rsp+68h] [rbp-98h]
  int v172; // [rsp+6Ch] [rbp-94h]
  int v173; // [rsp+70h] [rbp-90h]
  _DWORD *v174; // [rsp+78h] [rbp-88h]
  int v175; // [rsp+80h] [rbp-80h]
  __int64 v176; // [rsp+88h] [rbp-78h]
  HPROFILE hProfile; // [rsp+90h] [rbp-70h] BYREF
  DWORD phVersion; // [rsp+98h] [rbp-68h]
  DWORD phClass; // [rsp+9Ch] [rbp-64h]
  DWORD phDataColorSpace; // [rsp+A0h] [rbp-60h]
  int phConnectionSpace; // [rsp+A4h] [rbp-5Ch]
  int v182; // [rsp+A8h] [rbp-58h] BYREF
  int v183; // [rsp+ACh] [rbp-54h]
  int v184; // [rsp+B0h] [rbp-50h]
  int v185; // [rsp+B4h] [rbp-4Ch]
  int v186; // [rsp+B8h] [rbp-48h]
  int v187; // [rsp+BCh] [rbp-44h]
  __int16 v188; // [rsp+C0h] [rbp-40h]
  bool v189; // [rsp+C2h] [rbp-3Eh]
  char v190; // [rsp+C3h] [rbp-3Dh]
  char v191; // [rsp+C4h] [rbp-3Ch]
  char v192; // [rsp+C5h] [rbp-3Bh]
  char v193; // [rsp+C6h] [rbp-3Ah]
  char v194; // [rsp+C7h] [rbp-39h]
  char v195; // [rsp+C8h] [rbp-38h]
  char v196; // [rsp+C9h] [rbp-37h]
  __int64 v197; // [rsp+D0h] [rbp-30h]
  __int64 v198; // [rsp+D8h] [rbp-28h]
  int v199; // [rsp+E0h] [rbp-20h]
  int v200; // [rsp+E4h] [rbp-1Ch]
  unsigned __int16 *v201; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v202; // [rsp+F0h] [rbp-10h]
  size_t Size; // [rsp+F8h] [rbp-8h]
  void *v204; // [rsp+100h] [rbp+0h]
  __int64 v205; // [rsp+108h] [rbp+8h]
  size_t v206; // [rsp+110h] [rbp+10h]
  int v207; // [rsp+118h] [rbp+18h]
  void *v208; // [rsp+120h] [rbp+20h]
  __int64 v209; // [rsp+128h] [rbp+28h]
  _DWORD v210[3]; // [rsp+130h] [rbp+30h] BYREF
  char v211; // [rsp+13Ch] [rbp+3Ch]
  void *v212; // [rsp+140h] [rbp+40h]
  int v213; // [rsp+148h] [rbp+48h]
  int v214; // [rsp+14Ch] [rbp+4Ch]
  int v215; // [rsp+150h] [rbp+50h]
  char v216; // [rsp+154h] [rbp+54h]
  void *v217; // [rsp+158h] [rbp+58h]
  void *v218; // [rsp+160h] [rbp+60h]
  unsigned int v219; // [rsp+168h] [rbp+68h]
  int v220; // [rsp+16Ch] [rbp+6Ch]
  unsigned __int16 *v221; // [rsp+170h] [rbp+70h]
  int v222; // [rsp+180h] [rbp+80h] BYREF
  int v223; // [rsp+184h] [rbp+84h]
  unsigned int v224; // [rsp+188h] [rbp+88h]
  int v225; // [rsp+18Ch] [rbp+8Ch]
  int v226; // [rsp+190h] [rbp+90h]
  int kk; // [rsp+194h] [rbp+94h]
  int v228; // [rsp+198h] [rbp+98h]
  int v229; // [rsp+19Ch] [rbp+9Ch]
  _QWORD v230[16]; // [rsp+1A0h] [rbp+A0h]
  __int16 v231; // [rsp+220h] [rbp+120h]
  __int128 v232; // [rsp+230h] [rbp+130h] BYREF
  void *Src[2]; // [rsp+240h] [rbp+140h]
  void *v234[2]; // [rsp+250h] [rbp+150h]
  __int128 v235; // [rsp+260h] [rbp+160h]
  void *v236[2]; // [rsp+270h] [rbp+170h] BYREF
  __int128 v237; // [rsp+280h] [rbp+180h]
  __int128 v238; // [rsp+290h] [rbp+190h]
  __int128 v239; // [rsp+2A0h] [rbp+1A0h]
  __int128 v240; // [rsp+2B0h] [rbp+1B0h]
  PROFILEHEADER pHeader; // [rsp+2C0h] [rbp+1C0h] BYREF
  _OWORD v242[9]; // [rsp+340h] [rbp+240h] BYREF
  _DWORD v243[16]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v205 = a1;
  v176 = a3;
  v174 = a4;
  memset_0(&pHeader, 0, sizeof(pHeader));
  memset_0(v242, 0, sizeof(v242));
  memset_0(v210, 0, 0x48u);
  memset_0(&v222, 0, 0xA8u);
  v156[0] = 0;
  v202 = 0;
  v9 = 0;
  v201 = 0;
  v159 = 0;
  v199 = 1;
  v168 = 1;
  v158 = 0;
  v160 = 0;
  *a4 = 0;
  memset_0(&hProfile, 0, 0x50u);
  memset_0(&v232, 0, 0x90u);
  v10 = v193;
  if ( *(_DWORD *)(a1 + 328) == 2 )
    v10 = 1;
  v11 = *(void **)(a2 + 8);
  v154 = *(_WORD *)(a3 + 2) == 1;
  v193 = v10;
  ColorProfileHeader = GetColorProfileHeader(v11, &pHeader);
  if ( pHeader.phSignature == 1633907568 && ColorProfileHeader )
  {
    v13 = 0;
    v14 = BYTE2(pHeader.phProfileFlags) & 3;
    v164 = 0;
    v143 = *(_DWORD *)(a1 + 364) == -1;
    *(_WORD *)(a1 + 288) = v14;
    if ( !v143 )
    {
      v14 = *(_WORD *)(a1 + 364);
      *(_WORD *)(a1 + 288) = v14;
    }
    if ( v14 < 2 )
    {
      v191 = 0;
    }
    else
    {
      v191 = 1;
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
    v164 = v13;
LABEL_15:
    v15 = *(unsigned __int16 *)(a3 + 2);
    v16 = 3 * v13;
    v171 = 3 * v13;
    v165 = 3 * v13;
    v186 = v15 - 1;
    v17 = 0;
    v196 = *(_BYTE *)(a1 + 384);
    v185 = v14;
    v197 = a1 + 392;
    v198 = a1 + 464;
    v18 = *(_DWORD *)(a1 + 292);
    v190 = 0;
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
        v171 = 255;
        v165 = 255;
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
          CalcGridPoints4Cube(v28, v27, &v182, &v159);
LABEL_51:
          v33 = 0;
          if ( pHeader.phConnectionSpace == 1482250784 && (_WORD)v15 )
          {
            do
            {
              v34 = v33 | 1;
              if ( *(_QWORD *)(v176 + 24LL * v17 + 8) )
                v34 = v33;
              ++v17;
              v33 = v34;
            }
            while ( v17 < (unsigned __int16)v15 );
          }
          v35 = GetColorProfileHeader(*(HPROFILE *)(a2 + 8LL * *(unsigned __int16 *)(a2 + 2)), &pHeader);
          if ( pHeader.phSignature == 1633907568 && v35 )
          {
            v163 = 1;
            v166 = 2;
            v36 = 0;
            v169 = 0;
            v37 = 0;
            v200 = 0;
            v175 = 0;
            v162 = 0;
            v161 = 0;
            v208 = 0;
            v204 = 0;
            v172 = 0;
            if ( pHeader.phConnectionSpace == 1482250784 )
            {
              for ( i = 0; i < *(_WORD *)(v176 + 2); ++i )
              {
                if ( !*(_QWORD *)(v176 + 24LL * i + 8) && !a5 )
                  v33 |= 2u;
              }
            }
            v39 = v191;
            v40 = *(_DWORD *)(v205 + 328);
            if ( v40 == 2 )
              v39 = 1;
            v41 = v33 | 1;
            v42 = v33;
            v43 = v176;
            if ( v40 != 2 )
              v41 = v42;
            v44 = v39;
            v45 = 0;
            if ( v40 == 3 )
              v44 = 1;
            v191 = v44;
            v46 = v41 | 2;
            if ( v40 != 3 )
              v46 = v41;
            v167 = v46;
            while ( 1 )
            {
              v170 = v45;
              if ( (unsigned __int16)v45 >= *(_WORD *)(v43 + 2) )
              {
                DisposeIfPtr(v236[0]);
                v149 = v174;
                v143 = v166 == 1;
                v150 = v9;
                v236[0] = 0;
                v9 = 0;
                *((_QWORD *)v174 + 8) = v150;
                v149[14] = v200;
                v151 = 8;
                if ( !v143 )
                  v151 = 16;
                v134 = 0;
                v149[15] = v151;
                if ( !*v149 )
                  *v149 = 2;
                goto LABEL_350;
              }
              v187 = (unsigned __int16)v45;
              if ( v190 )
              {
                v188 = 257;
                v189 = 1;
              }
              else
              {
                HIBYTE(v188) = v191;
                v47 = *(unsigned __int16 *)(v43 + 2);
                LOBYTE(v188) = (_WORD)v45 != 0;
                v189 = (unsigned __int16)v45 != v47 - 1;
              }
              v48 = 3LL * (unsigned __int16)v45;
              v49 = *(void **)(v43 + 24LL * (unsigned __int16)v45 + 8);
              v209 = v48;
              if ( v49 )
              {
                hProfile = v49;
                v37 = 2011;
                v50 = GetColorProfileHeader(v49, &pHeader);
                if ( pHeader.phSignature != 1633907568 || !v50 )
                {
LABEL_336:
                  v134 = 0;
                  goto LABEL_350;
                }
                v37 = 0;
                phVersion = pHeader.phVersion;
                phClass = pHeader.phClass;
                phDataColorSpace = pHeader.phDataColorSpace;
                phConnectionSpace = pHeader.phConnectionSpace;
                v183 = *(_DWORD *)(v43 + 8 * v48 + 20);
                v195 = *(_BYTE *)(v43 + 8 * v48 + 28);
                v157 = 0;
              }
              else
              {
                v157 = 1;
              }
              Src[0] = (void *)DisposeIfPtr(Src[0]);
              v234[1] = (void *)DisposeIfPtr(v234[1]);
              v236[0] = (void *)DisposeIfPtr(v236[0]);
              *(_QWORD *)&v237 = DisposeIfPtr(v237);
              v236[1] = (void *)DisposeIfPtr(v236[1]);
              *((_QWORD *)&v237 + 1) = DisposeIfPtr(*((_QWORD *)&v237 + 1));
              *((_QWORD *)&v239 + 1) = DisposeIfPtr(*((_QWORD *)&v239 + 1));
              if ( v157 )
              {
                if ( v9 )
                {
                  if ( v36 != 3 )
                  {
                    v134 = 0;
                    goto LABEL_349;
                  }
                  v53 = v9;
                  v202 = 0;
                  v236[0] = v9;
                  v9 = 0;
                  v201 = 0;
                }
                else
                {
                  LODWORD(v235) = 3;
                  v51 = *(_DWORD *)(v205 + 292);
                  if ( v51 == 1281450528 || v51 == 1282766368 )
                    SpecialCube16 = MakeSpecialCube16(
                                      3,
                                      (unsigned int)&v165,
                                      (unsigned int)v236,
                                      (unsigned int)&v159,
                                      (__int64)&v168);
                  else
                    SpecialCube16 = MakeCube16(
                                      3,
                                      (unsigned int)&v165,
                                      (unsigned int)v236,
                                      (unsigned int)&v159,
                                      (__int64)&v168);
                  if ( SpecialCube16 )
                  {
                    v37 = SpecialCube16;
                    goto LABEL_351;
                  }
                  v16 = v165;
                  v171 = v165;
                  v13 = v165 / (int)v235;
                  v164 = v165 / (int)v235;
                  v200 = 1 << v159;
                  v175 = 1 << v159;
                  if ( !(_WORD)v170 )
                  {
                    DWORD1(v232) = 256;
                    DWORD2(v235) = 1 << v159;
                    DWORD2(v232) = (_BYTE)v188 != 0 ? 16 : 10;
                  }
                  v53 = (unsigned __int16 *)v236[0];
                  v172 = 3;
                  v37 = 0;
                  v199 = v168;
                }
                if ( *(_WORD *)(v43 + 8 * v48 + 16) == 2 )
                {
                  if ( v158 == 2 )
                  {
                    LabNewEncodingToLegacyEncoding(v53, v13);
                    v53 = (unsigned __int16 *)v236[0];
                  }
                  Lab2XYZ_forCube16(v53, v13);
                  v158 = 0;
                  v160 = 0;
                }
                else if ( *(_WORD *)(v43 + 8 * v48 + 16) == 1 )
                {
                  XYZ2Lab_forCube16(v53, v13);
                  v158 = 1;
                  v160 = 1;
                }
                v54 = 1;
                v55 = 3;
                *(_QWORD *)&v235 = 0x300000003LL;
                v56 = 3;
              }
              else
              {
                if ( !a5 || (v57 = *(unsigned __int16 *)(v43 + 2) - 1, v192 = 1, (unsigned __int16)v170 != v57) )
                  v192 = 0;
                v194 = *(_BYTE *)(v43 + 8 * v48 + 18);
                v58 = v167 & 1;
                if ( (v167 & 1) != 0 && v186 > 0 )
                {
                  v162 = HIBYTE(v188);
                  v186 = 0;
                  HIBYTE(v188) = 1;
                }
                v59 = v167 & 2;
                if ( (v167 & 2) != 0 )
                {
                  v60 = v189;
                  v161 = v189;
                  v189 = 1;
                }
                else
                {
                  v60 = v161;
                }
                v61 = ExtractAllLuts(&v232, (__int64)&hProfile);
                v62 = v175;
                v37 = v61;
                if ( *(_WORD *)(v176 + 2) == 1 )
                  v62 = DWORD2(v235);
                v175 = v62;
                if ( v58 )
                {
                  v63 = HIBYTE(v188);
                  v186 = *(unsigned __int16 *)(v176 + 2) - 1;
                  if ( v186 > 0 )
                    v63 = v162;
                  HIBYTE(v188) = v63;
                }
                v64 = v189;
                if ( v59 )
                  v64 = v60;
                v189 = v64;
                if ( v61 )
                {
LABEL_342:
                  v134 = 0;
                  goto LABEL_350;
                }
                v55 = v235;
                if ( !(_DWORD)v235 )
                  goto LABEL_340;
                v56 = DWORD1(v235);
                if ( !DWORD1(v235) )
                  goto LABEL_340;
                v54 = v154;
              }
              v65 = v54;
              if ( (_QWORD)v237 )
                v65 = 0;
              v207 = v65;
              if ( v163 )
              {
                if ( (_BYTE)v65 )
                {
                  v200 = DWORD2(v235);
                }
                else
                {
                  if ( v55 == 1 )
                    v16 = 255;
                  v165 = v16;
                  v66 = *(_DWORD *)(v205 + 292);
                  if ( v66 == 1281450528 || v66 == 1282766368 )
                    Cube16 = MakeSpecialCube16(
                               v55,
                               (unsigned int)&v165,
                               (unsigned int)&v201,
                               (unsigned int)&v159,
                               (__int64)&v168);
                  else
                    Cube16 = MakeCube16(
                               v55,
                               (unsigned int)&v165,
                               (unsigned int)&v201,
                               (unsigned int)&v159,
                               (__int64)&v168);
                  v9 = v201;
                  v37 = Cube16;
                  if ( Cube16 )
                    goto LABEL_342;
                  v16 = v165;
                  v55 = v235;
                  v171 = v165;
                  v13 = v165 / (int)v235;
                  v164 = v165 / (int)v235;
                  v199 = v168;
                  v200 = 1 << v159;
                  v175 = 1 << v159;
                  v172 = v235;
                  v202 = v201;
                }
                v68 = v55 * DWORD1(v232);
                if ( SDWORD2(v232) > 8 )
                  v68 *= 2;
                v69 = (unsigned int)(v68 + 2);
                if ( (v167 & 1) != 0 )
                {
                  v70 = SmartNewPtr(v69, v156);
                  v71 = v174;
                  v72 = 0;
                  v37 = v156[0];
                  v73 = v70;
                  *((_QWORD *)v174 + 2) = v70;
                  if ( v37 )
                    goto LABEL_339;
                  v74 = v68 / (int)v235;
                  v173 = v68 / (int)v235;
                  if ( (_BYTE)v188 || v191 )
                  {
                    Size = v74;
                    v75 = (unsigned __int64)v74 >> 1;
                    CreateLinearElut16(v73, (unsigned int)v75);
                    v76 = 16;
                    v206 = v75;
                  }
                  else
                  {
                    Size = v74;
                    v75 = (unsigned __int64)v74 >> 1;
                    v206 = v75;
                    CreateLinearElut(v73, (unsigned int)v75);
                    v76 = 10;
                  }
                  v71[2] = v76;
                  v55 = v235;
                  if ( (int)v235 > 0 )
                  {
                    v77 = Size;
                    v78 = v173;
                    v79 = v174;
                    do
                    {
                      memmove_0((void *)(*((_QWORD *)v79 + 2) + v78 * v72), *((const void **)v79 + 2), v77);
                      v55 = v235;
                      ++v72;
                    }
                    while ( v72 < (int)v235 );
                    v9 = v202;
                    v13 = v164;
                    v16 = v171;
                    LODWORD(v75) = v206;
                  }
                  v80 = v174;
                  LOBYTE(v167) = v167 & 0xFE;
                  v174[1] = v75;
                  v81 = v80;
                  v80[12] = v55;
                }
                else
                {
                  v82 = (void **)v174;
                  v174[2] = DWORD2(v232);
                  v82[2] = Src[0];
                  v82[3] = Src[1];
                  *((_DWORD *)v82 + 1) = DWORD1(v232);
                  *((_DWORD *)v82 + 12) = v55;
                  v83 = malloc_0((int)v69);
                  Src[0] = v83;
                  v84 = v83 == 0 ? 8 : 0;
                  v37 = v84;
                  v156[0] = v84;
                  if ( v84 )
                  {
                    v134 = 0;
                    goto LABEL_350;
                  }
                  v173 = v68 / v55;
                  v206 = v68 / v55;
                  v85 = v206 >> 1;
                  Size = v206 >> 1;
                  CreateLinearElut16(v83, (unsigned int)(v206 >> 1));
                  v55 = v235;
                  v86 = 0;
                  if ( (int)v235 > 0 )
                  {
                    v87 = v173;
                    v88 = v206;
                    do
                    {
                      memmove_0((char *)Src[0] + v87 * v86, Src[0], v88);
                      v55 = v235;
                      ++v86;
                    }
                    while ( v86 < (int)v235 );
                    v9 = v202;
                    v13 = v164;
                    LODWORD(v85) = Size;
                  }
                  v81 = v174;
                  *(_QWORD *)((char *)&v232 + 4) = (unsigned int)v85 | 0x1000000000LL;
                }
                v163 = 0;
                v89 = *(_DWORD *)(v205 + 292);
                if ( v89 != 1281450528 && v89 != 1282766368 )
                  goto LABEL_169;
                if ( (unsigned int)v175 <= 1 )
                  goto LABEL_340;
                v90 = (unsigned __int16 *)*((_QWORD *)v81 + 2);
                v91 = v81[1] / 2;
                LODWORD(Size) = v91;
                v92 = v91 - 1;
                v93 = (unsigned int)(v91 + v175 * ((v81[1] << 15) - 0x8000)) / v81[1] + v175 / 2;
                v81 = v174;
                v94 = v93 / (v175 - 1);
                v95 = (1 << v174[2]) - 1;
                v173 = v94;
                v96 = 0;
                if ( *((_WORD *)v174 + 24) )
                {
                  do
                  {
                    for ( j = 0; j <= v91; ++j )
                    {
                      v98 = (v94 * *v90 + 0x4000) >> 15;
                      *v90 = v98;
                      if ( (unsigned __int16)v98 > v95 )
                        *v90 = v95;
                      ++v90;
                    }
                    v99 = 1;
                    if ( v92 >= 1 )
                    {
                      do
                      {
                        v100 = (*v90 * ((((unsigned int)v92 >> 1) + v94 * (v92 - v99) + (v99 << 15)) / v92) + 0x4000) >> 15;
                        *v90 = v100;
                        if ( (unsigned __int16)v100 > v95 )
                          *v90 = v95;
                        v94 = v173;
                        ++v90;
                        ++v99;
                      }
                      while ( v99 <= v92 );
                      v91 = Size;
                    }
                    v81 = v174;
                    ++v96;
                  }
                  while ( v96 < *((_WORD *)v174 + 24) );
                  v13 = v164;
                  v56 = DWORD1(v235);
                  v55 = v235;
                }
                else
                {
LABEL_169:
                  v56 = DWORD1(v235);
                }
              }
              else
              {
                v81 = v174;
              }
              v101 = v176;
              v102 = 1;
              if ( (unsigned __int16)v170 == *(unsigned __int16 *)(v176 + 2) - 1 )
              {
                v103 = v167 & 2;
                if ( (v167 & 2) != 0 )
                {
                  v208 = v234[1];
                  v204 = v234[0];
                }
                else
                {
                  *((void **)v81 + 5) = v234[1];
                  *((void **)v81 + 4) = v234[0];
                }
                v81[13] = v56;
                if ( v189 || v191 )
                {
                  v106 = malloc_0((v56 << 11) + 2);
                  v234[1] = v106;
                  v37 = v106 == 0 ? 8 : 0;
                  v156[0] = v106 == 0 ? 8 : 0;
                  if ( (v106 == 0 ? 8 : 0) != 0 )
                    goto LABEL_336;
                  CreateLinearAlut16(v106);
                  v56 = DWORD1(v235);
                  v102 = 1;
                  v107 = 1;
                  if ( SDWORD1(v235) > 1 )
                  {
                    do
                    {
                      memmove_0((char *)v234[1] + 2048 * v107, v234[1], 0x800u);
                      v56 = DWORD1(v235);
                      ++v107;
                    }
                    while ( v107 < SDWORD1(v235) );
                    v13 = v164;
                    v102 = 1;
                  }
                  HIDWORD(v234[0]) = 16;
                }
                else
                {
                  v104 = (void *)SmartNewPtr((unsigned int)((v56 << 10) + 1), v156);
                  v37 = v156[0];
                  v234[1] = v104;
                  if ( v156[0] )
                    goto LABEL_336;
                  CreateLinearAlut(v104);
                  v56 = DWORD1(v235);
                  v102 = v37 + 1;
                  v105 = v37 + 1;
                  if ( SDWORD1(v235) > (int)(v37 + 1) )
                  {
                    do
                    {
                      memmove_0((char *)v234[1] + 1024 * v105, v234[1], 0x400u);
                      v56 = DWORD1(v235);
                      ++v105;
                    }
                    while ( v105 < SDWORD1(v235) );
                    v13 = v164;
                    v102 = 1;
                  }
                  HIDWORD(v234[0]) = 8;
                  v166 = v102;
                }
                v108 = v174;
                v101 = v176;
                v143 = v103 == 0;
                v55 = v235;
                LODWORD(v234[0]) = 1024;
                if ( !v143 )
                {
                  LOBYTE(v167) = v167 & 0xFD;
                  *((void **)v174 + 5) = v234[1];
                  v108[9] = HIDWORD(v234[0]);
                  v234[1] = v208;
                  v234[0] = v204;
                  v108[8] = 1024;
                }
              }
              else
              {
                v108 = v174;
              }
              if ( !(_BYTE)v207 )
                break;
              if ( (_WORD)v102 == *(_WORD *)(v101 + 2) )
              {
                v109 = v232;
                if ( (_DWORD)v232 == 3 )
                {
                  for ( k = 0; k < v55; v243[v111] = *((unsigned __int8 *)&v238 + v111) )
                  {
                    v111 = k;
                    k += v102;
                  }
                  for ( m = 0; m < v55; *((_BYTE *)v108 + v113 + 96) = v243[v113] )
                  {
                    v113 = m;
                    m += v102;
                  }
                  *((_QWORD *)v108 + 14) = v239;
                  *((_QWORD *)v108 + 11) = *((_QWORD *)&v237 + 1);
                  *((_QWORD *)v108 + 15) = *((_QWORD *)&v239 + 1);
                  *((_QWORD *)&v237 + 1) = 0;
                  *((_QWORD *)&v239 + 1) = 0;
                }
                else
                {
                  if ( (_DWORD)v232 != 2 )
                    goto LABEL_340;
                  v114 = 0;
                  if ( v55 > 0 )
                  {
                    do
                      v114 += v102;
                    while ( v114 < v55 );
                    v115 = DWORD2(v235);
                    v116 = v243;
                    for ( n = v55; n; --n )
                      *v116++ = v115;
                  }
                }
                *v108 = v109;
                v118 = v102;
                v119 = v56;
                for ( ii = 0; ii < v55; ii += v102 )
                {
                  v121 = v243[ii];
                  if ( !v121 || v119 > 0x7FFFFFFF / v121 )
                    goto LABEL_340;
                  v119 *= v121;
                  if ( ii < v55 - 1 )
                  {
                    if ( v118 > 0x7FFFFFFF - v119 )
                      goto LABEL_340;
                    v118 += v119;
                  }
                }
                if ( v118 > 0x7FFFFFFF / v56 )
                {
LABEL_340:
                  v134 = 0;
                  goto LABEL_349;
                }
                v122 = v56 * v118;
                v199 = v122;
                v168 = v122;
                DisposeIfPtr(v9);
                v123 = (unsigned int)(v122 + v119);
                if ( v191 )
                {
                  v124 = 2 * v123;
                  v125 = (unsigned __int16 *)SmartNewPtr((unsigned int)(2 * v123), v156);
                  v37 = v156[0];
                  v9 = v125;
                  if ( v156[0] )
                    goto LABEL_339;
                  memset_0(v125, 0, v124);
                  v126 = (unsigned __int8 *)v236[0];
                  if ( HIDWORD(v235) == 8 )
                  {
                    for ( jj = 0; jj < v119; v9[v128] = v126[v128] | (v126[v128] << 8) )
                      v128 = jj++;
                  }
                  else
                  {
                    memmove_0(v9, v236[0], 2 * v119);
                  }
                  HIDWORD(v235) = 16;
                }
                else
                {
                  v129 = (unsigned __int16 *)SmartNewPtr(v123, v156);
                  v37 = v156[0];
                  v9 = v129;
                  if ( v156[0] )
                  {
LABEL_339:
                    v134 = 0;
                    goto LABEL_350;
                  }
                  memmove_0(v129, v236[0], v119);
                  DisposeIfPtr(v236[0]);
                  HIDWORD(v235) = 8;
                }
                v236[0] = v9;
                v9 = 0;
              }
              DisposeIfPtr(v9);
              v9 = (unsigned __int16 *)v236[0];
              v202 = (unsigned __int16 *)v236[0];
              v201 = (unsigned __int16 *)v236[0];
              if ( v236[0] )
              {
                v16 = v13 * v235 * DWORD1(v235);
                v171 = v16;
                v165 = v16;
              }
              v43 = v176;
              v45 = v170;
              v236[0] = 0;
              if ( (unsigned __int16)v170 == *(unsigned __int16 *)(v176 + 2) - 1 && !v189 && !v191 )
                v166 = 1;
LABEL_326:
              v154 = 0;
              if ( pHeader.phClass == 1818848875 )
              {
                v148 = pHeader.phConnectionSpace;
                phDataColorSpace = pHeader.phConnectionSpace;
                v193 = 1;
              }
              else
              {
                v148 = phDataColorSpace;
              }
              if ( !v193 || v157 || v194 || v148 == 1281450528 || (v193 = 0, v148 == 1482250784) )
                v193 = 1;
              v36 = v172;
              LOWORD(v45) = v45 + 1;
            }
            if ( v172 != v55 )
              goto LABEL_340;
            if ( v193 )
            {
              if ( v172 != 3 )
                goto LABEL_340;
              v130 = v184;
              v131 = v169;
              if ( v184 != v169 )
              {
                if ( phConnectionSpace == 1281450528 )
                {
                  Lab2XYZ_forCube16(v9, v13);
                  v131 = v169;
                }
                if ( v130 == 2 && v131 == 1 )
                  AdjustBlackPointFromLegacyToV4Perceptual(v9, v13);
                else
                  AdjustBlackPointFromV4PerceptualToLegacy(v9, v13);
                if ( phConnectionSpace == 1281450528 )
                  XYZ2Lab_forCube16(v9, v13);
                v56 = DWORD1(v235);
                v55 = v235;
              }
            }
            if ( (_DWORD)v232 == 1 )
            {
              v210[2] = DWORD2(v232);
              v210[0] = DWORD1(v232);
              v212 = Src[0];
              v215 = HIDWORD(v234[0]);
              v213 = (int)v234[0];
              v217 = v234[1];
              v218 = v236[1];
              v211 = 1;
              v216 = 1;
              v220 = v166;
              v210[1] = 0;
              v214 = 0;
              v219 = v13;
              v221 = v9;
              DoMatrixForCube16(v210);
              v147 = v169;
              v158 = 0;
              if ( !v193 )
                v147 = v184;
              v169 = v147;
              v146 = DWORD1(v235);
              v160 = 0;
              goto LABEL_325;
            }
            if ( (_DWORD)v232 != 2 && (unsigned int)(v232 - 3) > 1 )
              goto LABEL_340;
            v132 = 0;
            if ( v193 )
            {
              if ( phConnectionSpace == 1281450528 )
              {
                LOBYTE(v132) = (_DWORD)v232 != 2;
                ++v132;
              }
              if ( v195 && v196 && v183 )
              {
                if ( phConnectionSpace == 1281450528 )
                {
                  if ( v158 == 2 )
                    LabNewEncodingToLegacyEncoding(v9, v13);
                  Lab2XYZ_forCube16(v9, v13);
                }
                ApplyChromaticAdaptationCorrection(v9, v13, v198);
                if ( phConnectionSpace == 1281450528 )
                {
                  XYZ2Lab_forCube16(v9, v13);
                  v158 = 1;
                  v160 = 1;
                }
                v55 = v235;
                v56 = DWORD1(v235);
              }
              if ( v193 && *(_DWORD *)(v176 + 8 * v209 + 20) == 3 && !*(_WORD *)(v176 + 8 * v209 + 18) )
              {
                v37 = DoAbsoluteShiftForPCS_Cube16((int)v9, v13, phConnectionSpace, (int)&v160, hProfile, 0);
                if ( v37 )
                  goto LABEL_342;
                v56 = DWORD1(v235);
                v55 = v235;
                v158 = v160;
              }
            }
            if ( (_QWORD)v237 )
            {
              DoOnlyMatrixForCube16(v237, v9, v13);
              v56 = DWORD1(v235);
              v55 = v235;
            }
            v133 = v166;
            if ( v55 >= v56 && v166 == 2 )
            {
              v134 = v9;
              v155 = 0;
              v222 = 0x4000;
            }
            else
            {
              v134 = (unsigned __int16 *)malloc_0((int)(v166 * v56 * (v13 + v199)));
              v135 = v134 != 0 ? 0 : 8;
              v37 = v135;
              v156[0] = v135;
              if ( v135 )
                goto LABEL_350;
              v133 = v166;
              v222 = 0x4000;
              v155 = 1;
              v223 = 0x2000;
              if ( v166 == 1 )
              {
LABEL_272:
                v224 = v13;
                v228 = 2 * v55;
                v136 = 0;
                v225 = 1;
                v229 = v133 * v56;
                v226 = v13 * 2 * v55;
                for ( kk = v13 * v133 * v56; v136 < v55; v230[v137] = &v9[v137] )
                  v137 = v136++;
                for ( mm = 0; mm < v56; v230[v139 + 8] = v140 )
                {
                  v139 = mm;
                  v140 = (char *)v134 + mm * v133;
                  ++mm;
                }
                v231 = 0;
                if ( (unsigned int)(v232 - 3) > 1 )
                {
                  v37 = FillDescaledInputLut(&v232);
                  if ( v37 )
                    goto LABEL_350;
                }
                v141 = v158;
                v242[0] = v232;
                v242[2] = *(_OWORD *)v234;
                v242[1] = *(_OWORD *)Src;
                v242[4] = *(_OWORD *)v236;
                v242[3] = v235;
                v242[6] = v238;
                v242[5] = v237;
                v242[8] = v240;
                v242[7] = v239;
                if ( v158 == 1 )
                {
                  if ( v132 == 2 )
                    LabLegacyEncodingToNewEncoding(v9, v13);
                }
                else if ( v158 == 2 && v132 == 1 )
                {
                  LabNewEncodingToLegacyEncoding(v9, v13);
                }
                v142 = v176;
                if ( (unsigned __int16)v170 >= *(unsigned __int16 *)(v176 + 2) - 1 )
                {
LABEL_297:
                  v37 = CalcNDim_Data8To8_Lut16(&v222, v242);
                  Src[1] = (void *)DisposeIfPtr(Src[1]);
                  if ( v37 )
                    goto LABEL_350;
                  v143 = *(_WORD *)(v142 + 8 * v209 + 18) == 0;
                  v144 = v142 + 8 * v209;
                  if ( v143 )
                  {
                    v145 = (_DWORD *)(v144 + 20);
                  }
                  else
                  {
                    v145 = (_DWORD *)(v144 + 20);
                    if ( *v145 == 3 )
                    {
                      v37 = DoAbsoluteShiftForPCS_Cube16((int)v134, v13, phConnectionSpace, (int)&v160, hProfile, 1);
                      if ( v37 )
                        goto LABEL_350;
                      v141 = v160;
                      v158 = v160;
LABEL_304:
                      if ( !v193 )
                      {
                        if ( *v145 != 3 )
                        {
LABEL_309:
                          if ( v195 && v196 && v183 )
                          {
                            if ( phConnectionSpace == 1281450528 )
                            {
                              if ( v141 == 2 )
                                LabNewEncodingToLegacyEncoding(v134, v13);
                              Lab2XYZ_forCube16(v134, v13);
                            }
                            v37 = ApplyChromaticAdaptationCorrection(v134, v13, v197);
                            if ( phConnectionSpace == 1281450528 )
                            {
                              XYZ2Lab_forCube16(v134, v13);
                              v158 = 1;
                              v160 = 1;
                            }
                          }
                          goto LABEL_318;
                        }
                        v37 = DoAbsoluteShiftForPCS_Cube16((int)v134, v13, phConnectionSpace, (int)&v160, hProfile, 1);
                        if ( v37 )
                          goto LABEL_350;
                        if ( !v193 )
                        {
                          v141 = v160;
                          v158 = v160;
                          goto LABEL_309;
                        }
                        v158 = v160;
                      }
LABEL_318:
                      if ( v155 )
                      {
                        DisposeIfPtr(v9);
                        v202 = v134;
                        v9 = v134;
                        v201 = v134;
                      }
                      v146 = DWORD1(v235);
                      v16 = v13 * v166 * DWORD1(v235);
                      v171 = v16;
                      v165 = v16;
LABEL_325:
                      v43 = v176;
                      v45 = v170;
                      v172 = v146;
                      goto LABEL_326;
                    }
                  }
                  v37 = 0;
                  goto LABEL_304;
                }
                if ( v193 )
                {
                  if ( v194 != 1 )
                  {
                    if ( phDataColorSpace == 1281450528 )
                      goto LABEL_293;
                    if ( phDataColorSpace != 1482250784 )
                    {
                      v169 = 0;
                      v141 = 0;
                      v158 = 0;
LABEL_296:
                      v160 = v141;
                      goto LABEL_297;
                    }
                  }
                  v143 = phDataColorSpace == 1281450528;
                }
                else
                {
                  v143 = phConnectionSpace == 1281450528;
                }
                if ( !v143 )
                {
                  v141 = 0;
                  v158 = 0;
                  goto LABEL_295;
                }
LABEL_293:
                v141 = ((_DWORD)v232 != 2) + 1;
                v158 = v141;
LABEL_295:
                v169 = v184;
                goto LABEL_296;
              }
            }
            v223 = 0x4000;
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
      v159 = v30;
      v182 = 1 << v30;
    }
    goto LABEL_51;
  }
  v134 = 0;
LABEL_349:
  v37 = 2011;
LABEL_350:
  if ( v9 != v134 )
  {
    DisposeIfPtr(v9);
    v152 = v134;
    goto LABEL_353;
  }
LABEL_351:
  v152 = v9;
LABEL_353:
  DisposeIfPtr(v152);
  Src[0] = (void *)DisposeIfPtr(Src[0]);
  Src[1] = (void *)DisposeIfPtr(Src[1]);
  v234[1] = (void *)DisposeIfPtr(v234[1]);
  v236[0] = (void *)DisposeIfPtr(v236[0]);
  *(_QWORD *)&v237 = DisposeIfPtr(v237);
  v236[1] = (void *)DisposeIfPtr(v236[1]);
  *((_QWORD *)&v237 + 1) = DisposeIfPtr(*((_QWORD *)&v237 + 1));
  DisposeIfPtr(*((_QWORD *)&v239 + 1));
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
