# mp3ScaleFactorRead(CBitStream &,MP3SI_GRCH &,MP3SCF &,MPEG_INFO const &,int const *,int,int)

- ea: `0x1800078d0`
- end: `0x18000a580`
- name: `?mp3ScaleFactorRead@@YAXAEAVCBitStream@@AEAUMP3SI_GRCH@@AEAUMP3SCF@@AEBUMPEG_INFO@@PEBHHH@Z`
- size: `11440`
- prototype: `void __usercall(struct CBitStream *this@<rcx>, struct MP3SI_GRCH *@<rdx>, struct MP3SCF *@<r8>, const struct MPEG_INFO *@<r9>, const int *, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004910`

## callees

- `0x180005630`
- `0x1800078d0`

## pseudocode

```c
void __fastcall mp3ScaleFactorRead(
        struct CBitStream *this,
        struct MP3SI_GRCH *a2,
        struct MP3SCF *a3,
        const struct MPEG_INFO *a4,
        const int *a5,
        int a6,
        int a7)
{
  int v10; // r15d
  __int64 v11; // r14
  unsigned int v12; // r11d
  unsigned __int16 v13; // r10
  unsigned int v14; // ecx
  __int64 v15; // r14
  unsigned int v16; // r11d
  __int64 v17; // rax
  unsigned __int16 v18; // r10
  unsigned int v19; // ecx
  __int64 v20; // r14
  unsigned int v21; // r11d
  __int64 v22; // rax
  unsigned __int16 v23; // r10
  unsigned int v24; // ecx
  int v25; // r15d
  __int64 v26; // r14
  unsigned int v27; // r11d
  unsigned __int16 v28; // r10
  unsigned int v29; // ecx
  __int64 v30; // r14
  unsigned int v31; // r11d
  __int64 v32; // rax
  unsigned __int16 v33; // r10
  unsigned int v34; // ecx
  __int64 v35; // r14
  unsigned int v36; // r11d
  __int64 v37; // rax
  unsigned __int16 v38; // r10
  unsigned int v39; // ecx
  int v40; // r15d
  __int64 v41; // r14
  unsigned int v42; // r11d
  unsigned __int16 v43; // r10
  unsigned int v44; // ecx
  __int64 v45; // r14
  unsigned int v46; // r11d
  __int64 v47; // rax
  unsigned __int16 v48; // r10
  unsigned int v49; // ecx
  __int64 v50; // r14
  unsigned int v51; // r11d
  __int64 v52; // rax
  unsigned __int16 v53; // r10
  unsigned int v54; // ecx
  int v55; // r15d
  __int64 v56; // r14
  unsigned int v57; // r11d
  unsigned __int16 v58; // r10
  unsigned int v59; // ecx
  __int64 v60; // r14
  unsigned int v61; // r11d
  __int64 v62; // rax
  unsigned __int16 v63; // r10
  unsigned int v64; // ecx
  __int64 v65; // r14
  unsigned int v66; // r11d
  __int64 v67; // rax
  unsigned __int16 v68; // r10
  unsigned int v69; // ecx
  int v70; // r15d
  __int64 v71; // r14
  unsigned int v72; // r11d
  unsigned __int16 v73; // r10
  unsigned int v74; // ecx
  __int64 v75; // r14
  unsigned int v76; // r11d
  __int64 v77; // rax
  unsigned __int16 v78; // r10
  unsigned int v79; // ecx
  __int64 v80; // r14
  unsigned int v81; // r11d
  __int64 v82; // rax
  unsigned __int16 v83; // r10
  unsigned int v84; // ecx
  int v85; // r15d
  __int64 v86; // r14
  unsigned int v87; // r11d
  unsigned __int16 v88; // r10
  unsigned int v89; // ecx
  __int64 v90; // r14
  unsigned int v91; // r11d
  __int64 v92; // rax
  unsigned __int16 v93; // r10
  unsigned int v94; // ecx
  __int64 v95; // r14
  unsigned int v96; // r11d
  __int64 v97; // rax
  unsigned __int16 v98; // r10
  unsigned int v99; // ecx
  int v100; // r15d
  __int64 v101; // r14
  unsigned int v102; // r11d
  unsigned __int16 v103; // r10
  unsigned int v104; // ecx
  __int64 v105; // r14
  unsigned int v106; // r11d
  __int64 v107; // rax
  unsigned __int16 v108; // r10
  unsigned int v109; // ecx
  __int64 v110; // r14
  unsigned int v111; // r11d
  __int64 v112; // rax
  unsigned __int16 v113; // r10
  unsigned int v114; // ecx
  int v115; // r15d
  __int64 v116; // r14
  unsigned int v117; // r11d
  unsigned __int16 v118; // r10
  unsigned int v119; // ecx
  __int64 v120; // r14
  unsigned int v121; // r11d
  __int64 v122; // rax
  unsigned __int16 v123; // r10
  unsigned int v124; // ecx
  __int64 v125; // r14
  unsigned int v126; // r11d
  __int64 v127; // rax
  unsigned __int16 v128; // r10
  unsigned int v129; // ecx
  int v130; // r15d
  __int64 v131; // r14
  unsigned int v132; // r11d
  unsigned __int16 v133; // r10
  unsigned int v134; // ecx
  __int64 v135; // r14
  unsigned int v136; // r11d
  __int64 v137; // rax
  unsigned __int16 v138; // r10
  unsigned int v139; // ecx
  int v140; // r14d
  __int64 v141; // r11
  unsigned int v142; // edi
  __int64 v143; // rax
  unsigned int v144; // ecx
  unsigned __int16 v145; // r8
  int v146; // edx
  __int64 i; // r14
  int v148; // r12d
  __int64 v149; // rdi
  unsigned int v150; // r15d
  unsigned __int16 v151; // r11
  unsigned int v152; // ecx
  __int64 v153; // rdi
  unsigned int v154; // r15d
  __int64 v155; // rax
  unsigned __int16 v156; // r11
  unsigned int v157; // ecx
  __int64 v158; // r15
  unsigned int v159; // edi
  __int64 v160; // rax
  unsigned __int16 v161; // r11
  unsigned int v162; // ecx
  __int64 j; // r12
  int v164; // r15d
  __int64 v165; // rdi
  unsigned int v166; // r14d
  unsigned __int16 v167; // r11
  unsigned int v168; // ecx
  __int64 v169; // rdi
  unsigned int v170; // r14d
  __int64 v171; // rax
  unsigned __int16 v172; // r11
  unsigned int v173; // ecx
  __int64 v174; // r14
  unsigned int v175; // edi
  __int64 v176; // rax
  unsigned __int16 v177; // r11
  unsigned int v178; // ecx
  int v179; // eax
  int v180; // r10d
  int v181; // r12d
  int v182; // r15d
  __int64 v183; // r14
  unsigned int v184; // edi
  __int64 v185; // rax
  unsigned int v186; // ecx
  unsigned __int16 v187; // r8
  int v188; // eax
  __int64 v189; // rdx
  int v190; // r15d
  __int64 v191; // r14
  unsigned int v192; // edi
  __int64 v193; // rax
  unsigned int v194; // ecx
  unsigned __int16 v195; // r8
  int v196; // eax
  __int64 v197; // rdx
  int v198; // eax
  int v199; // ecx
  char v200; // al
  int v201; // ecx
  __int64 v202; // r12
  unsigned int v203; // r14d
  int v204; // ecx
  unsigned int v205; // r15d
  __int64 v206; // rax
  unsigned int v207; // r10d
  __int64 v208; // rcx
  int v209; // r15d
  unsigned int v210; // edx
  char v211; // r10
  int v212; // r15d
  int v213; // r15d
  unsigned int v214; // edx
  int v215; // r11d
  int v216; // r13d
  __int64 v217; // r12
  __int64 v218; // rax
  unsigned __int16 v219; // di
  unsigned int v220; // ecx
  int v221; // eax
  unsigned int v222; // ecx
  __int64 v223; // rdx
  __int64 v224; // rax
  int v225; // r10d
  int v226; // r12d
  __int64 v227; // r14
  unsigned __int16 v228; // di
  unsigned int v229; // ecx
  int v230; // eax
  __int64 v231; // rdx
  int v232; // r12d
  int v233; // r15d
  __int64 v234; // r14
  unsigned __int16 v235; // di
  unsigned int v236; // ecx
  int v237; // eax
  __int64 v238; // rdx
  unsigned int v239; // edi
  int v240; // r12d
  int v241; // r15d
  __int64 v242; // r14
  unsigned int v243; // ecx
  unsigned __int16 v244; // r8
  int v245; // eax
  __int64 v246; // rdx
  __int64 *v247; // rcx
  int v248; // r15d
  int *v249; // r8
  int v250; // ecx
  __int64 v251; // r10
  int v252; // r12d
  int v253; // r13d
  int v254; // r14d
  __int64 v255; // rdi
  unsigned __int16 v256; // r11
  unsigned int v257; // ecx
  __int64 v258; // rdi
  int v259; // r15d
  __int64 v260; // r14
  unsigned __int16 v261; // r11
  unsigned int v262; // ecx
  int v263; // r15d
  __int64 v264; // r14
  unsigned __int16 v265; // r11
  unsigned int v266; // ecx
  int v267; // ecx
  int v268; // edi
  int v269; // edi
  int v270; // r15d
  int v271; // r13d
  int v272; // r12d
  __int64 v273; // r11
  unsigned __int16 v274; // r10
  unsigned int v275; // ecx
  unsigned int v276; // ecx
  __int64 v277; // r12
  __int64 v278; // r11
  __int64 v279; // rax
  unsigned __int16 v280; // r10
  unsigned int v281; // ecx
  __int64 v282; // r11
  __int64 v283; // rax
  unsigned __int16 v284; // r10
  unsigned int v285; // ecx
  __int64 v286; // kr00_8
  int v287; // r14d
  __int64 v288; // r11
  unsigned __int16 v289; // r10
  unsigned int v290; // ecx
  unsigned int v291; // ecx
  __int64 v292; // r14
  __int64 v293; // r11
  __int64 v294; // rax
  unsigned __int16 v295; // r10
  unsigned int v296; // ecx
  int v297; // r12d
  __int64 v298; // r11
  unsigned __int16 v299; // r10
  unsigned int v300; // ecx
  unsigned int v301; // r10d
  int v302; // r13d
  int v303; // r15d
  __int64 v304; // r14
  unsigned __int16 v305; // r11
  unsigned int v306; // ecx
  unsigned int v307; // ecx
  __int64 v308; // r15
  __int64 v309; // r14
  __int64 v310; // rax
  unsigned __int16 v311; // r11
  unsigned int v312; // ecx
  int v313; // r12d
  __int64 v314; // r14
  unsigned __int16 v315; // r11
  unsigned int v316; // ecx
  int v317; // r15d
  __int64 v318; // r14
  unsigned int v319; // r10d
  unsigned __int16 v320; // r11
  unsigned int v321; // ecx
  __int64 v322; // r14
  char v323; // r13
  int v324; // r12d
  __int64 v325; // r15
  unsigned __int16 v326; // r11
  unsigned int v327; // ecx
  int v328; // r12d
  __int64 v329; // r15
  unsigned __int16 v330; // r11
  unsigned int v331; // ecx
  __int64 v332; // [rsp+20h] [rbp-71h]
  int v333; // [rsp+20h] [rbp-71h]
  int v334; // [rsp+20h] [rbp-71h]
  int v335; // [rsp+28h] [rbp-69h]
  int v336; // [rsp+28h] [rbp-69h]
  int v337; // [rsp+28h] [rbp-69h]
  int v338; // [rsp+28h] [rbp-69h]
  char v339; // [rsp+28h] [rbp-69h]
  int v340; // [rsp+28h] [rbp-69h]
  int v341; // [rsp+28h] [rbp-69h]
  int v342; // [rsp+28h] [rbp-69h]
  int v343; // [rsp+30h] [rbp-61h]
  int v344; // [rsp+30h] [rbp-61h]
  int v345; // [rsp+30h] [rbp-61h]
  int v346; // [rsp+30h] [rbp-61h]
  int v347; // [rsp+30h] [rbp-61h]
  int v348; // [rsp+30h] [rbp-61h]
  int v349; // [rsp+38h] [rbp-59h]
  unsigned int v350; // [rsp+38h] [rbp-59h]
  int v351; // [rsp+38h] [rbp-59h]
  __int128 v352; // [rsp+40h] [rbp-51h]
  struct MP3SCF *v353; // [rsp+50h] [rbp-41h]
  struct MP3SCF *v354; // [rsp+58h] [rbp-39h]
  struct MP3SCF *v355; // [rsp+60h] [rbp-31h]
  __int64 v356; // [rsp+68h] [rbp-29h]
  __int64 v357; // [rsp+70h] [rbp-21h]
  __int64 v358; // [rsp+78h] [rbp-19h]
  __int64 v359; // [rsp+80h] [rbp-11h]
  __int64 v360; // [rsp+88h] [rbp-9h]
  int *v361; // [rsp+90h] [rbp-1h]
  __int64 *v362; // [rsp+98h] [rbp+7h]

  *((_DWORD *)this + 8) = 0;
  if ( *((_BYTE *)a4 + 32) )
  {
    if ( *((_DWORD *)a2 + 4) && *((_DWORD *)a2 + 5) == 2 )
    {
      if ( *((_DWORD *)a2 + 6) )
      {
        *(_DWORD *)a3 = CBitStream::GetBits(this, dword_180014150[*((int *)a2 + 3)]);
        *((_DWORD *)a3 + 1) = CBitStream::GetBits(this, dword_180014150[*((int *)a2 + 3)]);
        *((_DWORD *)a3 + 2) = CBitStream::GetBits(this, dword_180014150[*((int *)a2 + 3)]);
        *((_DWORD *)a3 + 3) = CBitStream::GetBits(this, dword_180014150[*((int *)a2 + 3)]);
        *((_DWORD *)a3 + 4) = CBitStream::GetBits(this, dword_180014150[*((int *)a2 + 3)]);
        *((_DWORD *)a3 + 5) = CBitStream::GetBits(this, dword_180014150[*((int *)a2 + 3)]);
        *((_DWORD *)a3 + 6) = CBitStream::GetBits(this, dword_180014150[*((int *)a2 + 3)]);
        *((_DWORD *)a3 + 7) = CBitStream::GetBits(this, dword_180014150[*((int *)a2 + 3)]);
        v10 = *((_DWORD *)this + 9);
        v11 = *((_QWORD *)this + 6);
        v12 = dword_180014150[*((int *)a2 + 3)];
        v13 = (*(unsigned __int8 *)(((v10 >> 3) & 0xFFFFFFFE) + 1 + v11)
             | (unsigned __int16)(*(unsigned __int8 *)(((v10 >> 3) & 0xFFFFFFFE) + v11) << 8)) << (*((_BYTE *)this + 36)
                                                                                                 & 0xF);
        v14 = 16 - (v10 & 0xF);
        if ( v12 > v14 )
          v13 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v11)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v11) << 8)) >> v14;
        *((_DWORD *)this + 8) += v12;
        *((_DWORD *)this + 6) -= v12;
        *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v10 + v12);
        *((_DWORD *)a3 + 26) = v13 >> (16 - v12);
        v15 = *((_QWORD *)this + 6);
        v16 = dword_180014150[*((int *)a2 + 3)];
        v17 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v18 = (*(unsigned __int8 *)((unsigned int)(v17 + 1) + v15)
             | (unsigned __int16)(*(unsigned __int8 *)(v17 + v15) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v19 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v16 > v19 )
          v18 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v15)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v15) << 8)) >> v19;
        *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (*((_DWORD *)this + 9) + v16);
        *((_DWORD *)this + 8) += v16;
        *((_DWORD *)this + 6) -= v16;
        *((_DWORD *)a3 + 39) = v18 >> (16 - v16);
        v20 = *((_QWORD *)this + 6);
        v21 = dword_180014150[*((int *)a2 + 3)];
        v22 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v23 = (*(unsigned __int8 *)((unsigned int)(v22 + 1) + v20)
             | (unsigned __int16)(*(unsigned __int8 *)(v22 + v20) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v24 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v21 > v24 )
          v23 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v20)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v20) << 8)) >> v24;
        *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (*((_DWORD *)this + 9) + v21);
        *((_DWORD *)this + 8) += v21;
        *((_DWORD *)this + 6) -= v21;
        *((_DWORD *)a3 + 52) = v23 >> (16 - v21);
        v25 = *((_DWORD *)this + 9);
        v26 = *((_QWORD *)this + 6);
        v27 = dword_180014150[*((int *)a2 + 3)];
        v28 = (*(unsigned __int8 *)(((v25 >> 3) & 0xFFFFFFFE) + 1 + v26)
             | (unsigned __int16)(*(unsigned __int8 *)(((v25 >> 3) & 0xFFFFFFFE) + v26) << 8)) << (*((_BYTE *)this + 36)
                                                                                                 & 0xF);
        v29 = 16 - (v25 & 0xF);
        if ( v27 > v29 )
          v28 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v26)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v26) << 8)) >> v29;
        *((_DWORD *)this + 8) += v27;
        *((_DWORD *)this + 6) -= v27;
        *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v25 + v27);
        *((_DWORD *)a3 + 27) = v28 >> (16 - v27);
        v30 = *((_QWORD *)this + 6);
        v31 = dword_180014150[*((int *)a2 + 3)];
        v32 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v33 = (*(unsigned __int8 *)((unsigned int)(v32 + 1) + v30)
             | (unsigned __int16)(*(unsigned __int8 *)(v32 + v30) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v34 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v31 > v34 )
          v33 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v30)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v30) << 8)) >> v34;
        *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (*((_DWORD *)this + 9) + v31);
        *((_DWORD *)this + 8) += v31;
        *((_DWORD *)this + 6) -= v31;
        *((_DWORD *)a3 + 40) = v33 >> (16 - v31);
        v35 = *((_QWORD *)this + 6);
        v36 = dword_180014150[*((int *)a2 + 3)];
        v37 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v38 = (*(unsigned __int8 *)((unsigned int)(v37 + 1) + v35)
             | (unsigned __int16)(*(unsigned __int8 *)(v37 + v35) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v39 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v36 > v39 )
          v38 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v35)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v35) << 8)) >> v39;
        *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (*((_DWORD *)this + 9) + v36);
        *((_DWORD *)this + 8) += v36;
        *((_DWORD *)this + 6) -= v36;
        *((_DWORD *)a3 + 53) = v38 >> (16 - v36);
        v40 = *((_DWORD *)this + 9);
        v41 = *((_QWORD *)this + 6);
        v42 = dword_180014150[*((int *)a2 + 3)];
        v43 = (*(unsigned __int8 *)(((v40 >> 3) & 0xFFFFFFFE) + 1 + v41)
             | (unsigned __int16)(*(unsigned __int8 *)(((v40 >> 3) & 0xFFFFFFFE) + v41) << 8)) << (*((_BYTE *)this + 36)
                                                                                                 & 0xF);
        v44 = 16 - (v40 & 0xF);
        if ( v42 > v44 )
          v43 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v41)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v41) << 8)) >> v44;
        *((_DWORD *)this + 8) += v42;
        *((_DWORD *)this + 6) -= v42;
        *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v40 + v42);
        *((_DWORD *)a3 + 28) = v43 >> (16 - v42);
        v45 = *((_QWORD *)this + 6);
        v46 = dword_180014150[*((int *)a2 + 3)];
        v47 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v48 = (*(unsigned __int8 *)((unsigned int)(v47 + 1) + v45)
             | (unsigned __int16)(*(unsigned __int8 *)(v47 + v45) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v49 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v46 > v49 )
          v48 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v45)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v45) << 8)) >> v49;
        *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (*((_DWORD *)this + 9) + v46);
        *((_DWORD *)this + 8) += v46;
        *((_DWORD *)this + 6) -= v46;
        *((_DWORD *)a3 + 41) = v48 >> (16 - v46);
        v50 = *((_QWORD *)this + 6);
        v51 = dword_180014150[*((int *)a2 + 3)];
        v52 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v53 = (*(unsigned __int8 *)((unsigned int)(v52 + 1) + v50)
             | (unsigned __int16)(*(unsigned __int8 *)(v52 + v50) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v54 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v51 > v54 )
          v53 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v50)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v50) << 8)) >> v54;
        *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (*((_DWORD *)this + 9) + v51);
        *((_DWORD *)this + 8) += v51;
        *((_DWORD *)this + 6) -= v51;
        *((_DWORD *)a3 + 54) = v53 >> (16 - v51);
        v55 = *((_DWORD *)this + 9);
        v56 = *((_QWORD *)this + 6);
        v57 = dword_180014190[*((int *)a2 + 3)];
        v58 = (*(unsigned __int8 *)(((v55 >> 3) & 0xFFFFFFFE) + 1 + v56)
             | (unsigned __int16)(*(unsigned __int8 *)(((v55 >> 3) & 0xFFFFFFFE) + v56) << 8)) << (*((_BYTE *)this + 36)
                                                                                                 & 0xF);
        v59 = 16 - (v55 & 0xF);
        if ( v57 > v59 )
          v58 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v56)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v56) << 8)) >> v59;
        *((_DWORD *)this + 8) += v57;
        *((_DWORD *)this + 6) -= v57;
        *((_DWORD *)this + 9) = (v55 + v57) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)a3 + 29) = v58 >> (16 - v57);
        v60 = *((_QWORD *)this + 6);
        v61 = dword_180014190[*((int *)a2 + 3)];
        v62 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v63 = (*(unsigned __int8 *)((unsigned int)(v62 + 1) + v60)
             | (unsigned __int16)(*(unsigned __int8 *)(v62 + v60) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v64 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v61 > v64 )
          v63 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v60)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v60) << 8)) >> v64;
        *((_DWORD *)this + 9) = (v61 + *((_DWORD *)this + 9)) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)this + 8) += v61;
        *((_DWORD *)this + 6) -= v61;
        *((_DWORD *)a3 + 42) = v63 >> (16 - v61);
        v65 = *((_QWORD *)this + 6);
        v66 = dword_180014190[*((int *)a2 + 3)];
        v67 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v68 = (*(unsigned __int8 *)((unsigned int)(v67 + 1) + v65)
             | (unsigned __int16)(*(unsigned __int8 *)(v67 + v65) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v69 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v66 > v69 )
          v68 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v65)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v65) << 8)) >> v69;
        *((_DWORD *)this + 9) = (v66 + *((_DWORD *)this + 9)) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)this + 8) += v66;
        *((_DWORD *)this + 6) -= v66;
        *((_DWORD *)a3 + 55) = v68 >> (16 - v66);
        v70 = *((_DWORD *)this + 9);
        v71 = *((_QWORD *)this + 6);
        v72 = dword_180014190[*((int *)a2 + 3)];
        v73 = (*(unsigned __int8 *)(((v70 >> 3) & 0xFFFFFFFE) + 1 + v71)
             | (unsigned __int16)(*(unsigned __int8 *)(((v70 >> 3) & 0xFFFFFFFE) + v71) << 8)) << (*((_BYTE *)this + 36)
                                                                                                 & 0xF);
        v74 = 16 - (v70 & 0xF);
        if ( v72 > v74 )
          v73 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v71)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v71) << 8)) >> v74;
        *((_DWORD *)this + 8) += v72;
        *((_DWORD *)this + 6) -= v72;
        *((_DWORD *)this + 9) = (v70 + v72) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)a3 + 30) = v73 >> (16 - v72);
        v75 = *((_QWORD *)this + 6);
        v76 = dword_180014190[*((int *)a2 + 3)];
        v77 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v78 = (*(unsigned __int8 *)((unsigned int)(v77 + 1) + v75)
             | (unsigned __int16)(*(unsigned __int8 *)(v77 + v75) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v79 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v76 > v79 )
          v78 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v75)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v75) << 8)) >> v79;
        *((_DWORD *)this + 9) = (v76 + *((_DWORD *)this + 9)) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)this + 8) += v76;
        *((_DWORD *)this + 6) -= v76;
        *((_DWORD *)a3 + 43) = v78 >> (16 - v76);
        v80 = *((_QWORD *)this + 6);
        v81 = dword_180014190[*((int *)a2 + 3)];
        v82 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v83 = (*(unsigned __int8 *)((unsigned int)(v82 + 1) + v80)
             | (unsigned __int16)(*(unsigned __int8 *)(v82 + v80) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v84 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v81 > v84 )
          v83 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v80)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v80) << 8)) >> v84;
        *((_DWORD *)this + 9) = (v81 + *((_DWORD *)this + 9)) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)this + 8) += v81;
        *((_DWORD *)this + 6) -= v81;
        *((_DWORD *)a3 + 56) = v83 >> (16 - v81);
        v85 = *((_DWORD *)this + 9);
        v86 = *((_QWORD *)this + 6);
        v87 = dword_180014190[*((int *)a2 + 3)];
        v88 = (*(unsigned __int8 *)(((v85 >> 3) & 0xFFFFFFFE) + 1 + v86)
             | (unsigned __int16)(*(unsigned __int8 *)(((v85 >> 3) & 0xFFFFFFFE) + v86) << 8)) << (*((_BYTE *)this + 36)
                                                                                                 & 0xF);
        v89 = 16 - (v85 & 0xF);
        if ( v87 > v89 )
          v88 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v86)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v86) << 8)) >> v89;
        *((_DWORD *)this + 8) += v87;
        *((_DWORD *)this + 6) -= v87;
        *((_DWORD *)this + 9) = (v85 + v87) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)a3 + 31) = v88 >> (16 - v87);
        v90 = *((_QWORD *)this + 6);
        v91 = dword_180014190[*((int *)a2 + 3)];
        v92 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v93 = (*(unsigned __int8 *)((unsigned int)(v92 + 1) + v90)
             | (unsigned __int16)(*(unsigned __int8 *)(v92 + v90) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v94 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v91 > v94 )
          v93 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v90)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v90) << 8)) >> v94;
        *((_DWORD *)this + 9) = (v91 + *((_DWORD *)this + 9)) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)this + 8) += v91;
        *((_DWORD *)this + 6) -= v91;
        *((_DWORD *)a3 + 44) = v93 >> (16 - v91);
        v95 = *((_QWORD *)this + 6);
        v96 = dword_180014190[*((int *)a2 + 3)];
        v97 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v98 = (*(unsigned __int8 *)((unsigned int)(v97 + 1) + v95)
             | (unsigned __int16)(*(unsigned __int8 *)(v97 + v95) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v99 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v96 > v99 )
          v98 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                        & (*((_DWORD *)this + 4) - 1))
                                                       + 1
                                                       + v95)
                                  | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + v95) << 8)) >> v99;
        *((_DWORD *)this + 9) = (v96 + *((_DWORD *)this + 9)) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)this + 8) += v96;
        *((_DWORD *)this + 6) -= v96;
        *((_DWORD *)a3 + 57) = v98 >> (16 - v96);
        v100 = *((_DWORD *)this + 9);
        v101 = *((_QWORD *)this + 6);
        v102 = dword_180014190[*((int *)a2 + 3)];
        v103 = (*(unsigned __int8 *)(((v100 >> 3) & 0xFFFFFFFE) + 1 + v101)
              | (unsigned __int16)(*(unsigned __int8 *)(((v100 >> 3) & 0xFFFFFFFE) + v101) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v104 = 16 - (v100 & 0xF);
        if ( v102 > v104 )
          v103 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + 1
                                                        + v101)
                                   | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                          & (*((_DWORD *)this + 4) - 1))
                                                         + v101) << 8)) >> v104;
        *((_DWORD *)this + 8) += v102;
        *((_DWORD *)this + 6) -= v102;
        *((_DWORD *)this + 9) = (v100 + v102) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)a3 + 32) = v103 >> (16 - v102);
        v105 = *((_QWORD *)this + 6);
        v106 = dword_180014190[*((int *)a2 + 3)];
        v107 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v108 = (*(unsigned __int8 *)((unsigned int)(v107 + 1) + v105)
              | (unsigned __int16)(*(unsigned __int8 *)(v107 + v105) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v109 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v106 > v109 )
          v108 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + 1
                                                        + v105)
                                   | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                          & (*((_DWORD *)this + 4) - 1))
                                                         + v105) << 8)) >> v109;
        *((_DWORD *)this + 9) = (v106 + *((_DWORD *)this + 9)) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)this + 8) += v106;
        *((_DWORD *)this + 6) -= v106;
        *((_DWORD *)a3 + 45) = v108 >> (16 - v106);
        v110 = *((_QWORD *)this + 6);
        v111 = dword_180014190[*((int *)a2 + 3)];
        v112 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v113 = (*(unsigned __int8 *)((unsigned int)(v112 + 1) + v110)
              | (unsigned __int16)(*(unsigned __int8 *)(v112 + v110) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v114 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v111 > v114 )
          v113 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + 1
                                                        + v110)
                                   | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                          & (*((_DWORD *)this + 4) - 1))
                                                         + v110) << 8)) >> v114;
        *((_DWORD *)this + 9) = (v111 + *((_DWORD *)this + 9)) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)this + 8) += v111;
        *((_DWORD *)this + 6) -= v111;
        *((_DWORD *)a3 + 58) = v113 >> (16 - v111);
        v115 = *((_DWORD *)this + 9);
        v116 = *((_QWORD *)this + 6);
        v117 = dword_180014190[*((int *)a2 + 3)];
        v118 = (*(unsigned __int8 *)(((v115 >> 3) & 0xFFFFFFFE) + 1 + v116)
              | (unsigned __int16)(*(unsigned __int8 *)(((v115 >> 3) & 0xFFFFFFFE) + v116) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v119 = 16 - (v115 & 0xF);
        if ( v117 > v119 )
          v118 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + 1
                                                        + v116)
                                   | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                          & (*((_DWORD *)this + 4) - 1))
                                                         + v116) << 8)) >> v119;
        *((_DWORD *)this + 8) += v117;
        *((_DWORD *)this + 6) -= v117;
        *((_DWORD *)this + 9) = (v115 + v117) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)a3 + 33) = v118 >> (16 - v117);
        v120 = *((_QWORD *)this + 6);
        v121 = dword_180014190[*((int *)a2 + 3)];
        v122 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v123 = (*(unsigned __int8 *)((unsigned int)(v122 + 1) + v120)
              | (unsigned __int16)(*(unsigned __int8 *)(v122 + v120) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v124 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v121 > v124 )
          v123 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + 1
                                                        + v120)
                                   | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                          & (*((_DWORD *)this + 4) - 1))
                                                         + v120) << 8)) >> v124;
        *((_DWORD *)this + 9) = (v121 + *((_DWORD *)this + 9)) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)this + 8) += v121;
        *((_DWORD *)this + 6) -= v121;
        *((_DWORD *)a3 + 46) = v123 >> (16 - v121);
        v125 = *((_QWORD *)this + 6);
        v126 = dword_180014190[*((int *)a2 + 3)];
        v127 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v128 = (*(unsigned __int8 *)((unsigned int)(v127 + 1) + v125)
              | (unsigned __int16)(*(unsigned __int8 *)(v127 + v125) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v129 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v126 > v129 )
          v128 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + 1
                                                        + v125)
                                   | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                          & (*((_DWORD *)this + 4) - 1))
                                                         + v125) << 8)) >> v129;
        *((_DWORD *)this + 9) = (v126 + *((_DWORD *)this + 9)) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)this + 8) += v126;
        *((_DWORD *)this + 6) -= v126;
        *((_DWORD *)a3 + 59) = v128 >> (16 - v126);
        v130 = *((_DWORD *)this + 9);
        v131 = *((_QWORD *)this + 6);
        v132 = dword_180014190[*((int *)a2 + 3)];
        v133 = (*(unsigned __int8 *)(((v130 >> 3) & 0xFFFFFFFE) + 1 + v131)
              | (unsigned __int16)(*(unsigned __int8 *)(((v130 >> 3) & 0xFFFFFFFE) + v131) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v134 = 16 - (v130 & 0xF);
        if ( v132 > v134 )
          v133 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + 1
                                                        + v131)
                                   | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                          & (*((_DWORD *)this + 4) - 1))
                                                         + v131) << 8)) >> v134;
        *((_DWORD *)this + 8) += v132;
        *((_DWORD *)this + 6) -= v132;
        *((_DWORD *)this + 9) = (v130 + v132) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)a3 + 34) = v133 >> (16 - v132);
        v135 = *((_QWORD *)this + 6);
        v136 = dword_180014190[*((int *)a2 + 3)];
        v137 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v138 = (*(unsigned __int8 *)((unsigned int)(v137 + 1) + v135)
              | (unsigned __int16)(*(unsigned __int8 *)(v137 + v135) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v139 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v136 > v139 )
          v138 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + 1
                                                        + v135)
                                   | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                          & (*((_DWORD *)this + 4) - 1))
                                                         + v135) << 8)) >> v139;
        *((_DWORD *)this + 9) = (v136 + *((_DWORD *)this + 9)) & (*((_DWORD *)this + 5) - 1);
        *((_DWORD *)this + 8) += v136;
        *((_DWORD *)this + 6) -= v136;
        *((_DWORD *)a3 + 47) = v138 >> (16 - v136);
        v140 = *((_DWORD *)this + 9);
        v141 = *((_QWORD *)this + 6);
        v142 = dword_180014190[*((int *)a2 + 3)];
        v143 = (v140 >> 3) & 0xFFFFFFFE;
        v144 = 16 - (v140 & 0xF);
        if ( v142 <= v144 )
          v145 = (*(unsigned __int8 *)((unsigned int)(v143 + 1) + v141)
                | (unsigned __int16)(*(unsigned __int8 *)(v143 + v141) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        else
          v145 = ((*(unsigned __int8 *)((unsigned int)(v143 + 1) + v141)
                 | (unsigned __int16)(*(unsigned __int8 *)(v143 + v141) << 8)) << (*((_BYTE *)this + 36) & 0xF))
               | ((unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + 1
                                                        + v141)
                                   | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                          & (*((_DWORD *)this + 4) - 1))
                                                         + v141) << 8)) >> v144);
        v146 = *((_DWORD *)this + 5) - 1;
        v360 = 340;
        *((_DWORD *)this + 9) = (v142 + v140) & v146;
        *((_DWORD *)this + 8) += v142;
        *((_DWORD *)this + 6) -= v142;
        *((_DWORD *)a3 + 60) = v145 >> (16 - v142);
        *((_DWORD *)a3 + 35) = 0;
        *((_DWORD *)a3 + 48) = 0;
        *((_DWORD *)a3 + 61) = 0;
        *((_DWORD *)a3 + 62) = 7;
        *((_DWORD *)a3 + 63) = 7;
        *((_DWORD *)a3 + 64) = 7;
        *((_DWORD *)a3 + 65) = 7;
        *((_DWORD *)a3 + 66) = 7;
        *((_DWORD *)a3 + 67) = 7;
        *((_DWORD *)a3 + 68) = 7;
        *((_DWORD *)a3 + 69) = 7;
        *((_DWORD *)a3 + 70) = 7;
        *((_DWORD *)a3 + 71) = 7;
        *((_DWORD *)a3 + 72) = 7;
        *((_DWORD *)a3 + 73) = 7;
        *((_DWORD *)a3 + 74) = 7;
        *((_DWORD *)a3 + 75) = 7;
        *((_DWORD *)a3 + 76) = 7;
        *((_DWORD *)a3 + 77) = 7;
        *((_DWORD *)a3 + 78) = 7;
        *((_DWORD *)a3 + 79) = 7;
        *((_DWORD *)a3 + 80) = 7;
        *((_DWORD *)a3 + 81) = 7;
        *((_DWORD *)a3 + 82) = 7;
        *((_DWORD *)a3 + 83) = 7;
        *((_DWORD *)a3 + 84) = 7;
        *(_QWORD *)&v352 = 388;
      }
      else
      {
        for ( i = 0; i != 6; ++i )
        {
          v148 = *((_DWORD *)this + 9);
          v149 = *((_QWORD *)this + 6);
          v150 = dword_180014150[*((int *)a2 + 3)];
          v151 = (*(unsigned __int8 *)(((v148 >> 3) & 0xFFFFFFFE) + 1 + v149)
                | (unsigned __int16)(*(unsigned __int8 *)(((v148 >> 3) & 0xFFFFFFFE) + v149) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v152 = 16 - (v148 & 0xF);
          if ( v150 > v152 )
            v151 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v149)
                                     | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v149) << 8)) >> v152;
          *((_DWORD *)this + 8) += v150;
          *((_DWORD *)this + 6) -= v150;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v150 + v148);
          *((_DWORD *)a3 + i + 23) = v151 >> (16 - v150);
          v153 = *((_QWORD *)this + 6);
          v154 = dword_180014150[*((int *)a2 + 3)];
          v155 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
          v156 = (*(unsigned __int8 *)((unsigned int)(v155 + 1) + v153)
                | (unsigned __int16)(*(unsigned __int8 *)(v155 + v153) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v157 = 16 - (*((_DWORD *)this + 9) & 0xF);
          if ( v154 > v157 )
            v156 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v153)
                                     | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v153) << 8)) >> v157;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (*((_DWORD *)this + 9) + v154);
          *((_DWORD *)this + 8) += v154;
          *((_DWORD *)this + 6) -= v154;
          *((_DWORD *)a3 + i + 36) = v156 >> (16 - v154);
          v158 = *((_QWORD *)this + 6);
          v159 = dword_180014150[*((int *)a2 + 3)];
          v160 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
          v161 = (*(unsigned __int8 *)((unsigned int)(v160 + 1) + v158)
                | (unsigned __int16)(*(unsigned __int8 *)(v160 + v158) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v162 = 16 - (*((_DWORD *)this + 9) & 0xF);
          if ( v159 > v162 )
            v161 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v158)
                                     | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v158) << 8)) >> v162;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (*((_DWORD *)this + 9) + v159);
          *((_DWORD *)this + 8) += v159;
          *((_DWORD *)this + 6) -= v159;
          *((_DWORD *)a3 + i + 49) = v161 >> (16 - v159);
        }
        for ( j = 6; j != 12; ++j )
        {
          v164 = *((_DWORD *)this + 9);
          v165 = *((_QWORD *)this + 6);
          v166 = dword_180014190[*((int *)a2 + 3)];
          v167 = (*(unsigned __int8 *)(((v164 >> 3) & 0xFFFFFFFE) + 1 + v165)
                | (unsigned __int16)(*(unsigned __int8 *)(((v164 >> 3) & 0xFFFFFFFE) + v165) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v168 = 16 - (v164 & 0xF);
          if ( v166 > v168 )
            v167 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v165)
                                     | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v165) << 8)) >> v168;
          *((_DWORD *)this + 8) += v166;
          *((_DWORD *)this + 6) -= v166;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v164 + v166);
          *((_DWORD *)a3 + j + 23) = v167 >> (16 - v166);
          v169 = *((_QWORD *)this + 6);
          v170 = dword_180014190[*((int *)a2 + 3)];
          v171 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
          v172 = (*(unsigned __int8 *)((unsigned int)(v171 + 1) + v169)
                | (unsigned __int16)(*(unsigned __int8 *)(v171 + v169) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v173 = 16 - (*((_DWORD *)this + 9) & 0xF);
          if ( v170 > v173 )
            v172 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v169)
                                     | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v169) << 8)) >> v173;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (*((_DWORD *)this + 9) + v170);
          *((_DWORD *)this + 8) += v170;
          *((_DWORD *)this + 6) -= v170;
          *((_DWORD *)a3 + j + 36) = v172 >> (16 - v170);
          v174 = *((_QWORD *)this + 6);
          v175 = dword_180014190[*((int *)a2 + 3)];
          v176 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
          v177 = (*(unsigned __int8 *)((unsigned int)(v176 + 1) + v174)
                | (unsigned __int16)(*(unsigned __int8 *)(v176 + v174) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v178 = 16 - (*((_DWORD *)this + 9) & 0xF);
          if ( v175 > v178 )
            v177 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v174)
                                     | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v174) << 8)) >> v178;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (*((_DWORD *)this + 9) + v175);
          *((_DWORD *)this + 8) += v175;
          *((_DWORD *)this + 6) -= v175;
          *((_DWORD *)a3 + j + 49) = v177 >> (16 - v175);
        }
        *((_DWORD *)a3 + 35) = 0;
        *((_DWORD *)a3 + 48) = 0;
        *(_QWORD *)&v352 = 388;
        *((_DWORD *)a3 + 61) = 0;
        v360 = 340;
      }
      v355 = a3;
      v359 = (__int64)a3;
      *(_DWORD *)((char *)a3 + v360) = 7;
      v358 = (__int64)a3;
      v357 = (__int64)a3;
      v356 = (__int64)a3;
      *((_DWORD *)a3 + 86) = 7;
      *((_DWORD *)a3 + 87) = 7;
      *((_DWORD *)a3 + 88) = 7;
      *((_DWORD *)a3 + 89) = 7;
      *((_DWORD *)a3 + 90) = 7;
      *((_DWORD *)a3 + 91) = 7;
      *((_DWORD *)a3 + 92) = 7;
      *((_DWORD *)a3 + 93) = 7;
      *((_DWORD *)a3 + 94) = 7;
      v354 = a3;
      *((_DWORD *)a3 + 95) = 7;
      v353 = a3;
      v361 = (int *)a3;
      *((_DWORD *)v355 + 96) = 7;
      *(_DWORD *)((char *)a3 + v352) = 7;
    }
    else
    {
      v179 = 0;
      v349 = 0;
      do
      {
        if ( !a6 || !a5[v179] )
        {
          v180 = dword_180014110[v179];
          v181 = dword_180014114[v179];
          if ( v180 < v181 )
          {
            if ( (unsigned int)v179 >= 2 )
            {
              do
              {
                v190 = *((_DWORD *)this + 9);
                v191 = *((_QWORD *)this + 6);
                v192 = dword_180014190[*((int *)a2 + 3)];
                v193 = (v190 >> 3) & 0xFFFFFFFE;
                v194 = 16 - (v190 & 0xF);
                if ( v192 <= v194 )
                  v195 = (*(unsigned __int8 *)((unsigned int)(v193 + 1) + v191)
                        | (unsigned __int16)(*(unsigned __int8 *)(v193 + v191) << 8)) << (*((_BYTE *)this + 36) & 0xF);
                else
                  v195 = ((*(unsigned __int8 *)((unsigned int)(v193 + 1) + v191)
                         | (unsigned __int16)(*(unsigned __int8 *)(v193 + v191) << 8)) << (*((_BYTE *)this + 36) & 0xF))
                       | ((unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                                 & (*((_DWORD *)this + 4) - 1))
                                                                + 1
                                                                + v191)
                                           | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                                  & (*((_DWORD *)this + 4) - 1))
                                                                 + v191) << 8)) >> v194);
                v196 = *((_DWORD *)this + 5);
                *((_DWORD *)this + 8) += v192;
                *((_DWORD *)this + 6) -= v192;
                *((_DWORD *)this + 9) = (v196 - 1) & (v192 + v190);
                v197 = v180++;
                *((_DWORD *)a3 + v197) = v195 >> (16 - v192);
              }
              while ( v180 < v181 );
            }
            else
            {
              do
              {
                v182 = *((_DWORD *)this + 9);
                v183 = *((_QWORD *)this + 6);
                v184 = dword_180014150[*((int *)a2 + 3)];
                v185 = (v182 >> 3) & 0xFFFFFFFE;
                v186 = 16 - (v182 & 0xF);
                if ( v184 <= v186 )
                  v187 = (*(unsigned __int8 *)((unsigned int)(v185 + 1) + v183)
                        | (unsigned __int16)(*(unsigned __int8 *)(v185 + v183) << 8)) << (*((_BYTE *)this + 36) & 0xF);
                else
                  v187 = ((*(unsigned __int8 *)((unsigned int)(v185 + 1) + v183)
                         | (unsigned __int16)(*(unsigned __int8 *)(v185 + v183) << 8)) << (*((_BYTE *)this + 36) & 0xF))
                       | ((unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                                 & (*((_DWORD *)this + 4) - 1))
                                                                + 1
                                                                + v183)
                                           | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                                  & (*((_DWORD *)this + 4) - 1))
                                                                 + v183) << 8)) >> v186);
                v188 = *((_DWORD *)this + 5);
                *((_DWORD *)this + 8) += v184;
                *((_DWORD *)this + 6) -= v184;
                *((_DWORD *)this + 9) = (v188 - 1) & (v184 + v182);
                v189 = v180++;
                *((_DWORD *)a3 + v189) = v187 >> (16 - v184);
              }
              while ( v180 < v181 );
            }
            v179 = v349;
          }
        }
        v349 = ++v179;
      }
      while ( v179 < 4 );
      *(_QWORD *)((char *)a3 + 84) = 0;
      *((_DWORD *)a3 + 62) = 7;
      *((_DWORD *)a3 + 63) = 7;
      *((_DWORD *)a3 + 64) = 7;
      *((_DWORD *)a3 + 65) = 7;
      *((_DWORD *)a3 + 66) = 7;
      *((_DWORD *)a3 + 67) = 7;
      *((_DWORD *)a3 + 68) = 7;
      *((_DWORD *)a3 + 69) = 7;
      *((_DWORD *)a3 + 70) = 7;
      *((_DWORD *)a3 + 71) = 7;
      *((_DWORD *)a3 + 72) = 7;
      *((_DWORD *)a3 + 73) = 7;
      *((_DWORD *)a3 + 74) = 7;
      *((_DWORD *)a3 + 75) = 7;
      *((_DWORD *)a3 + 76) = 7;
      *((_DWORD *)a3 + 77) = 7;
      *((_DWORD *)a3 + 78) = 7;
      *((_DWORD *)a3 + 79) = 7;
      *((_DWORD *)a3 + 80) = 7;
      *((_DWORD *)a3 + 81) = 7;
      *((_DWORD *)a3 + 82) = 7;
      *((_DWORD *)a3 + 83) = 7;
      *((_DWORD *)a3 + 84) = 7;
    }
    return;
  }
  v198 = *((_DWORD *)a4 + 4);
  v199 = *((_DWORD *)a2 + 3);
  *((_DWORD *)a2 + 15) = 0;
  v352 = 0;
  if ( (v198 & 1) == 0 || a7 != 1 )
  {
    *((_DWORD *)a2 + 18) = 0;
    if ( v199 >= 400 )
    {
      if ( v199 < 500 )
      {
        v211 = v199 + 112;
        v358 = 3;
        v359 = 3;
        v212 = (v199 - 400) >> 2;
        v202 = 3;
        v360 = 3;
        v332 = 3;
        v208 = 3;
        v356 = 3;
        v203 = v212 / 5;
        v357 = 48;
        LODWORD(v352) = v212 / 5;
        v205 = v212 % 5;
        v206 = 3;
        v207 = v211 & 3;
        *(_QWORD *)((char *)&v352 + 4) = __PAIR64__(v207, v205);
        goto LABEL_113;
      }
      v207 = DWORD2(v352);
      if ( v199 < 512 )
      {
        v202 = 6;
        *((_DWORD *)a2 + 15) = 1;
        v213 = v199 - 500;
        v358 = 6;
        v359 = 6;
        v214 = (unsigned __int64)(1431655766LL * (v199 - 500)) >> 32;
        v360 = 6;
        v208 = 6;
        v332 = 6;
        v203 = v214 + (v214 >> 31);
        v356 = 6;
        LODWORD(v352) = v203;
        v357 = 96;
        v205 = v213 - 3 * v203;
        v206 = 6;
        DWORD1(v352) = v205;
        goto LABEL_113;
      }
      v205 = DWORD1(v352);
      v203 = v352;
    }
    else
    {
      v207 = (v199 >> 2) & 3;
      v203 = (v199 >> 4) / 5;
      LODWORD(v352) = v203;
      v205 = (v199 >> 4) % 5;
      *(_QWORD *)((char *)&v352 + 4) = __PAIR64__(v207, v205);
      HIDWORD(v352) = v199 & 3;
    }
    v357 = 0;
    v206 = 0;
    v356 = 0;
    v208 = 0;
    v332 = 0;
    v202 = 0;
    v360 = 0;
    v359 = 0;
    v358 = 0;
    goto LABEL_113;
  }
  v200 = v199;
  v201 = v199 >> 1;
  *((_DWORD *)a2 + 18) = v200 & 1;
  if ( v201 < 180 )
  {
    v202 = 9;
    v357 = 144;
    v358 = 9;
    v359 = 9;
    v360 = 9;
    v332 = 9;
    v203 = v201 / 36;
    v356 = 9;
    LODWORD(v352) = v201 / 36;
    v204 = v201 % 36;
    v205 = v204 / 6;
    DWORD1(v352) = v204 / 6;
    v206 = 9;
    v207 = v204 % 6;
    LODWORD(v355) = v204 % 6;
    DWORD2(v352) = v204 % 6;
    v208 = 9;
    goto LABEL_114;
  }
  if ( v201 < 244 )
  {
    v202 = 12;
    v357 = 192;
    v358 = 12;
    v359 = 12;
    v203 = ((v201 - 180) >> 4) & 3;
    v205 = ((v201 - 180) >> 2) & 3;
    *(_QWORD *)&v352 = __PAIR64__(v205, v203);
    v207 = (v201 - 180) & 3;
    DWORD2(v352) = v207;
    v208 = 12;
    v360 = 12;
    v206 = 12;
    v332 = 12;
    v356 = 12;
LABEL_113:
    LODWORD(v355) = v207;
    goto LABEL_114;
  }
  v207 = DWORD2(v352);
  LODWORD(v355) = DWORD2(v352);
  if ( v201 > 255 )
  {
    v205 = DWORD1(v352);
    v202 = 0;
    v203 = v352;
    v208 = 0;
    v358 = 0;
    v206 = 0;
    v359 = 0;
    v360 = 0;
    v332 = 0;
    v356 = 0;
    v357 = 0;
  }
  else
  {
    v202 = 15;
    v357 = 240;
    v209 = v201 - 244;
    v358 = 15;
    v359 = 15;
    v210 = (unsigned __int64)(1431655766LL * (v201 - 244)) >> 32;
    v360 = 15;
    v208 = 15;
    v332 = 15;
    v203 = v210 + (v210 >> 31);
    v356 = 15;
    LODWORD(v352) = v203;
    v205 = v209 - 3 * v203;
    v206 = 15;
    DWORD1(v352) = v205;
  }
LABEL_114:
  v350 = v205;
  if ( *((_DWORD *)a2 + 5) == 2 )
  {
    if ( *((_DWORD *)a2 + 6) )
    {
      LODWORD(v353) = 2;
      v268 = dword_180014130[v203];
      *(_DWORD *)a3 = CBitStream::GetBits(this, v203);
      *((_DWORD *)a3 + 62) = v268;
      *((_DWORD *)a3 + 1) = CBitStream::GetBits(this, v203);
      *((_DWORD *)a3 + 63) = v268;
      *((_DWORD *)a3 + 2) = CBitStream::GetBits(this, v203);
      *((_DWORD *)a3 + 64) = v268;
      *((_DWORD *)a3 + 3) = CBitStream::GetBits(this, v203);
      *((_DWORD *)a3 + 65) = v268;
      *((_DWORD *)a3 + 4) = CBitStream::GetBits(this, v203);
      *((_DWORD *)a3 + 66) = v268;
      *((_DWORD *)a3 + 5) = CBitStream::GetBits(this, v203);
      *((_DWORD *)a3 + 67) = v268;
      v269 = 3;
      if ( (dword_1800141F0[4 * v202] - 6) / 3 <= 0 )
      {
        LODWORD(v353) = 2;
      }
      else
      {
        v270 = (dword_1800141F0[4 * v202] - 6) / 3;
        v271 = 0;
        v333 = dword_180014130[v203];
        do
        {
          v272 = *((_DWORD *)this + 9);
          v273 = *((_QWORD *)this + 6);
          v274 = (*(unsigned __int8 *)(((v272 >> 3) & 0xFFFFFFFE) + 1 + v273)
                | (unsigned __int16)(*(unsigned __int8 *)(((v272 >> 3) & 0xFFFFFFFE) + v273) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v275 = 16 - (v272 & 0xF);
          if ( v203 > v275 )
            v274 |= (unsigned __int16)(*(unsigned __int8 *)(((((v272 >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v273)
                                     | (*(unsigned __int8 *)(((((v272 >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v273) << 8)) >> v275;
          *((_DWORD *)this + 8) += v203;
          v276 = v203 + v272;
          *((_DWORD *)this + 6) -= v203;
          v277 = v269;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & v276;
          v339 = 16 - v203;
          *((_DWORD *)a3 + v269 + 23) = v274 >> (16 - v203);
          v278 = *((_QWORD *)this + 6);
          v279 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
          v280 = (*(unsigned __int8 *)((unsigned int)(v279 + 1) + v278)
                | (unsigned __int16)(*(unsigned __int8 *)(v279 + v278) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v281 = 16 - (*((_DWORD *)this + 9) & 0xF);
          if ( v203 > v281 )
            v280 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v278)
                                     | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v278) << 8)) >> v281;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v203 + *((_DWORD *)this + 9));
          *((_DWORD *)this + 8) += v203;
          *((_DWORD *)this + 6) -= v203;
          *((_DWORD *)a3 + v269 + 36) = v280 >> v339;
          v282 = *((_QWORD *)this + 6);
          v283 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
          v284 = (*(unsigned __int8 *)((unsigned int)(v283 + 1) + v282)
                | (unsigned __int16)(*(unsigned __int8 *)(v283 + v282) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v285 = 16 - (*((_DWORD *)this + 9) & 0xF);
          if ( v203 > v285 )
            v284 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v282)
                                     | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v282) << 8)) >> v285;
          ++v269;
          ++v271;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v203 + *((_DWORD *)this + 9));
          *((_DWORD *)this + 8) += v203;
          *((_DWORD *)this + 6) -= v203;
          *((_DWORD *)a3 + v277 + 49) = v284 >> v339;
          *((_DWORD *)a3 + v277 + 85) = v333;
        }
        while ( v271 < v270 );
        v205 = v350;
      }
      v286 = 1431655766LL * dword_1800141D4[4 * v358 + 8];
      if ( (signed int)(HIDWORD(v286) + (HIDWORD(v286) >> 31)) > 0 )
      {
        v340 = 0;
        v346 = dword_180014130[v205];
        do
        {
          v287 = *((_DWORD *)this + 9);
          v288 = *((_QWORD *)this + 6);
          v289 = (*(unsigned __int8 *)(((v287 >> 3) & 0xFFFFFFFE) + 1 + v288)
                | (unsigned __int16)(*(unsigned __int8 *)(((v287 >> 3) & 0xFFFFFFFE) + v288) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v290 = 16 - (v287 & 0xF);
          if ( v205 > v290 )
            v289 |= (unsigned __int16)(*(unsigned __int8 *)(((((v287 >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v288)
                                     | (*(unsigned __int8 *)(((((v287 >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v288) << 8)) >> v290;
          *((_DWORD *)this + 8) += v205;
          v291 = v287 + v205;
          *((_DWORD *)this + 6) -= v205;
          v292 = v269;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & v291;
          *((_DWORD *)a3 + v269 + 23) = v289 >> (16 - v205);
          v293 = *((_QWORD *)this + 6);
          v294 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
          v295 = (*(unsigned __int8 *)((unsigned int)(v294 + 1) + v293)
                | (unsigned __int16)(*(unsigned __int8 *)(v294 + v293) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v296 = 16 - (*((_DWORD *)this + 9) & 0xF);
          if ( v205 > v296 )
            v295 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v293)
                                     | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v293) << 8)) >> v296;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v205 + *((_DWORD *)this + 9));
          *((_DWORD *)this + 8) += v205;
          *((_DWORD *)this + 6) -= v205;
          *((_DWORD *)a3 + v269 + 36) = v295 >> (16 - v205);
          v297 = *((_DWORD *)this + 9);
          v298 = *((_QWORD *)this + 6);
          v299 = (*(unsigned __int8 *)(((v297 >> 3) & 0xFFFFFFFE) + 1 + v298)
                | (unsigned __int16)(*(unsigned __int8 *)(((v297 >> 3) & 0xFFFFFFFE) + v298) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v300 = 16 - (v297 & 0xF);
          if ( v205 > v300 )
            v299 |= (unsigned __int16)(*(unsigned __int8 *)(((((v297 >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v298)
                                     | (*(unsigned __int8 *)(((((v297 >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v298) << 8)) >> v300;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v297 + v205);
          *((_DWORD *)this + 8) += v205;
          ++v269;
          *((_DWORD *)this + 6) -= v205;
          *((_DWORD *)a3 + v292 + 49) = v299 >> (16 - v205);
          *((_DWORD *)a3 + v292 + 85) = v346;
          ++v340;
        }
        while ( v340 < (signed int)(HIDWORD(v286) + (HIDWORD(v286) >> 31)) );
      }
      if ( dword_1800141D8[4 * v359 + 4 * (unsigned int)v353] / 3 > 0 )
      {
        v301 = (unsigned int)v355;
        v341 = 0;
        v302 = dword_1800141D8[4 * v359 + 4 * (unsigned int)v353] / 3;
        v347 = dword_180014130[(int)v355];
        do
        {
          v303 = *((_DWORD *)this + 9);
          v304 = *((_QWORD *)this + 6);
          v305 = (*(unsigned __int8 *)(((v303 >> 3) & 0xFFFFFFFE) + 1 + v304)
                | (unsigned __int16)(*(unsigned __int8 *)(((v303 >> 3) & 0xFFFFFFFE) + v304) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v306 = 16 - (v303 & 0xF);
          if ( v301 > v306 )
            v305 |= (unsigned __int16)(*(unsigned __int8 *)(((((v303 >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v304)
                                     | (*(unsigned __int8 *)(((((v303 >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v304) << 8)) >> v306;
          *((_DWORD *)this + 8) += v301;
          v307 = v303 + v301;
          *((_DWORD *)this + 6) -= v301;
          v308 = v269;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & v307;
          *((_DWORD *)a3 + v269 + 23) = v305 >> (16 - v301);
          v309 = *((_QWORD *)this + 6);
          v310 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
          v311 = (*(unsigned __int8 *)((unsigned int)(v310 + 1) + v309)
                | (unsigned __int16)(*(unsigned __int8 *)(v310 + v309) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v312 = 16 - (*((_DWORD *)this + 9) & 0xF);
          if ( v301 > v312 )
            v311 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v309)
                                     | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v309) << 8)) >> v312;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v301 + *((_DWORD *)this + 9));
          *((_DWORD *)this + 8) += v301;
          *((_DWORD *)this + 6) -= v301;
          *((_DWORD *)a3 + v269 + 36) = v311 >> (16 - v301);
          v313 = *((_DWORD *)this + 9);
          v314 = *((_QWORD *)this + 6);
          v315 = (*(unsigned __int8 *)(((v313 >> 3) & 0xFFFFFFFE) + 1 + v314)
                | (unsigned __int16)(*(unsigned __int8 *)(((v313 >> 3) & 0xFFFFFFFE) + v314) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v316 = 16 - (v313 & 0xF);
          if ( v301 > v316 )
            v315 |= (unsigned __int16)(*(unsigned __int8 *)(((((v313 >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v314)
                                     | (*(unsigned __int8 *)(((((v313 >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v314) << 8)) >> v316;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v313 + v301);
          *((_DWORD *)this + 8) += v301;
          ++v269;
          *((_DWORD *)this + 6) -= v301;
          *((_DWORD *)a3 + v308 + 49) = v315 >> (16 - v301);
          *((_DWORD *)a3 + v308 + 85) = v347;
          ++v341;
        }
        while ( v341 < v302 );
      }
      v348 = dword_1800141DC[4 * v360 + 4 * (unsigned int)v353] / 3;
      if ( v348 > 0 )
      {
        v342 = 0;
        v334 = dword_180014130[SHIDWORD(v352)];
        do
        {
          v317 = *((_DWORD *)this + 9);
          v318 = *((_QWORD *)this + 6);
          v319 = HIDWORD(v352);
          v320 = (*(unsigned __int8 *)(((v317 >> 3) & 0xFFFFFFFE) + 1 + v318)
                | (unsigned __int16)(*(unsigned __int8 *)(((v317 >> 3) & 0xFFFFFFFE) + v318) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v321 = 16 - (v317 & 0xF);
          if ( HIDWORD(v352) > v321 )
            v320 |= (unsigned __int16)(*(unsigned __int8 *)(((((v317 >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v318)
                                     | (*(unsigned __int8 *)(((((v317 >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v318) << 8)) >> v321;
          *((_DWORD *)this + 8) += HIDWORD(v352);
          *((_DWORD *)this + 6) -= v319;
          v322 = v269;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v317 + v319);
          v323 = 16 - v319;
          *((_DWORD *)a3 + v269 + 23) = v320 >> (16 - v319);
          v324 = *((_DWORD *)this + 9);
          v325 = *((_QWORD *)this + 6);
          v326 = (*(unsigned __int8 *)(((v324 >> 3) & 0xFFFFFFFE) + 1 + v325)
                | (unsigned __int16)(*(unsigned __int8 *)(((v324 >> 3) & 0xFFFFFFFE) + v325) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v327 = 16 - (v324 & 0xF);
          if ( v319 > v327 )
            v326 |= (unsigned __int16)(*(unsigned __int8 *)(((((v324 >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v325)
                                     | (*(unsigned __int8 *)(((((v324 >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v325) << 8)) >> v327;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v324 + v319);
          *((_DWORD *)this + 8) += v319;
          *((_DWORD *)this + 6) -= v319;
          *((_DWORD *)a3 + v269 + 36) = v326 >> v323;
          v328 = *((_DWORD *)this + 9);
          v329 = *((_QWORD *)this + 6);
          v330 = (*(unsigned __int8 *)(((v328 >> 3) & 0xFFFFFFFE) + 1 + v329)
                | (unsigned __int16)(*(unsigned __int8 *)(((v328 >> 3) & 0xFFFFFFFE) + v329) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v331 = 16 - (v328 & 0xF);
          if ( v319 > v331 )
            v330 |= (unsigned __int16)(*(unsigned __int8 *)(((((v328 >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + 1
                                                          + v329)
                                     | (*(unsigned __int8 *)(((((v328 >> 3) & 0xFFFFFFFE) + 2)
                                                            & (*((_DWORD *)this + 4) - 1))
                                                           + v329) << 8)) >> v331;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v328 + v319);
          *((_DWORD *)this + 8) += v319;
          ++v269;
          *((_DWORD *)this + 6) -= v319;
          *((_DWORD *)a3 + v322 + 49) = v330 >> v323;
          *((_DWORD *)a3 + v322 + 85) = v334;
          ++v342;
        }
        while ( v342 < v348 );
      }
    }
    else
    {
      v247 = &qword_1800141E0[2 * v208];
      v351 = 0;
      v362 = v247;
      v248 = 0;
      v249 = 0;
      v361 = 0;
      do
      {
        v250 = *((_DWORD *)v247 + (_QWORD)v249) / 3;
        if ( v250 > 0 )
        {
          v251 = *((int *)&v352 + (_QWORD)v249);
          v252 = 0;
          v253 = v250;
          LODWORD(v354) = dword_180014130[v251];
          LODWORD(v353) = (unsigned __int16)(16 - v251);
          do
          {
            v254 = *((_DWORD *)this + 9);
            v255 = *((_QWORD *)this + 6);
            v256 = (*(unsigned __int8 *)(((v254 >> 3) & 0xFFFFFFFE) + 1 + v255)
                  | (unsigned __int16)(*(unsigned __int8 *)(((v254 >> 3) & 0xFFFFFFFE) + v255) << 8)) << (*((_BYTE *)this + 36) & 0xF);
            v257 = 16 - (v254 & 0xF);
            if ( (unsigned int)v251 > v257 )
              v256 |= (unsigned __int16)(*(unsigned __int8 *)(((((v254 >> 3) & 0xFFFFFFFE) + 2)
                                                             & (*((_DWORD *)this + 4) - 1))
                                                            + 1
                                                            + v255)
                                       | (*(unsigned __int8 *)(((((v254 >> 3) & 0xFFFFFFFE) + 2)
                                                              & (*((_DWORD *)this + 4) - 1))
                                                             + v255) << 8)) >> v257;
            *((_DWORD *)this + 8) += v251;
            *((_DWORD *)this + 6) -= v251;
            v258 = v248;
            *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v251 + v254);
            *((_DWORD *)a3 + v248 + 23) = v256 >> (char)v353;
            v259 = *((_DWORD *)this + 9);
            v260 = *((_QWORD *)this + 6);
            v261 = (*(unsigned __int8 *)(((v259 >> 3) & 0xFFFFFFFE) + 1 + v260)
                  | (unsigned __int16)(*(unsigned __int8 *)(((v259 >> 3) & 0xFFFFFFFE) + v260) << 8)) << (*((_BYTE *)this + 36) & 0xF);
            v262 = 16 - (v259 & 0xF);
            if ( (unsigned int)v251 > v262 )
              v261 |= (unsigned __int16)(*(unsigned __int8 *)(((((v259 >> 3) & 0xFFFFFFFE) + 2)
                                                             & (*((_DWORD *)this + 4) - 1))
                                                            + 1
                                                            + v260)
                                       | (*(unsigned __int8 *)(((((v259 >> 3) & 0xFFFFFFFE) + 2)
                                                              & (*((_DWORD *)this + 4) - 1))
                                                             + v260) << 8)) >> v262;
            *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v259 + v251);
            *((_DWORD *)this + 8) += v251;
            *((_DWORD *)this + 6) -= v251;
            *((_DWORD *)a3 + v258 + 36) = v261 >> (char)v353;
            v263 = *((_DWORD *)this + 9);
            v264 = *((_QWORD *)this + 6);
            v265 = (*(unsigned __int8 *)(((v263 >> 3) & 0xFFFFFFFE) + 1 + v264)
                  | (unsigned __int16)(*(unsigned __int8 *)(((v263 >> 3) & 0xFFFFFFFE) + v264) << 8)) << (*((_BYTE *)this + 36) & 0xF);
            v266 = 16 - (v263 & 0xF);
            if ( (unsigned int)v251 > v266 )
              v265 |= (unsigned __int16)(*(unsigned __int8 *)(((((v263 >> 3) & 0xFFFFFFFE) + 2)
                                                             & (*((_DWORD *)this + 4) - 1))
                                                            + 1
                                                            + v264)
                                       | (*(unsigned __int8 *)(((((v263 >> 3) & 0xFFFFFFFE) + 2)
                                                              & (*((_DWORD *)this + 4) - 1))
                                                             + v264) << 8)) >> v266;
            v267 = v263 + v251;
            v248 = v351 + 1;
            *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & v267;
            ++v252;
            *((_DWORD *)this + 8) += v251;
            *((_DWORD *)this + 6) -= v251;
            *((_DWORD *)a3 + v258 + 49) = v265 >> (char)v353;
            *((_DWORD *)a3 + v258 + 85) = (_DWORD)v354;
            ++v351;
          }
          while ( v252 < v253 );
          v249 = v361;
        }
        v247 = v362;
        v249 = (int *)((char *)v249 + 1);
        v361 = v249;
      }
      while ( v249 != (int *)4 );
    }
    *((_DWORD *)a3 + 35) = 0;
    *((_DWORD *)a3 + 48) = 0;
    *((_DWORD *)a3 + 61) = 0;
    *((_DWORD *)a3 + 97) = 1;
  }
  else
  {
    v215 = 0;
    v361 = dword_1800141DC;
    v335 = dword_1800141D0[4 * v206];
    if ( v335 <= 0 )
    {
      v224 = 0;
      LODWORD(v353) = 0;
      v361 = dword_1800141DC;
    }
    else
    {
      LODWORD(v353) = 0;
      LODWORD(v354) = dword_180014130[v203];
      v216 = (int)v354;
      do
      {
        v217 = *((_QWORD *)this + 6);
        v218 = (*((int *)this + 9) >> 3) & 0xFFFFFFFE;
        v219 = (*(unsigned __int8 *)((unsigned int)(v218 + 1) + v217)
              | (unsigned __int16)(*(unsigned __int8 *)(v218 + v217) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v220 = 16 - (*((_DWORD *)this + 9) & 0xF);
        if ( v203 > v220 )
          v219 |= (unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                         & (*((_DWORD *)this + 4) - 1))
                                                        + 1
                                                        + v217)
                                   | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                          & (*((_DWORD *)this + 4) - 1))
                                                         + v217) << 8)) >> v220;
        v221 = *((_DWORD *)this + 5);
        v222 = v203 + *((_DWORD *)this + 9);
        *((_DWORD *)this + 8) += v203;
        *((_DWORD *)this + 6) -= v203;
        *((_DWORD *)this + 9) = (v221 - 1) & v222;
        v223 = (unsigned int)v215++;
        *((_DWORD *)a3 + v223) = v219 >> (16 - v203);
        *((_DWORD *)a3 + v223 + 62) = v216;
      }
      while ( v215 < v335 );
      v207 = (unsigned int)v355;
      v224 = (unsigned int)v353;
    }
    v343 = dword_1800141D4[4 * v332 + 4 * v224];
    if ( v343 > 0 )
    {
      v225 = 0;
      v336 = dword_180014130[v205];
      LODWORD(v354) = (unsigned __int16)(16 - v205);
      do
      {
        v226 = *((_DWORD *)this + 9);
        v227 = *((_QWORD *)this + 6);
        v228 = (*(unsigned __int8 *)(((v226 >> 3) & 0xFFFFFFFE) + 1 + v227)
              | (unsigned __int16)(*(unsigned __int8 *)(((v226 >> 3) & 0xFFFFFFFE) + v227) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v229 = 16 - (v226 & 0xF);
        if ( v205 > v229 )
          v228 |= (unsigned __int16)(*(unsigned __int8 *)(((((v226 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)this + 4) - 1))
                                                        + 1
                                                        + v227)
                                   | (*(unsigned __int8 *)(((((v226 >> 3) & 0xFFFFFFFE) + 2)
                                                          & (*((_DWORD *)this + 4) - 1))
                                                         + v227) << 8)) >> v229;
        v230 = *((_DWORD *)this + 5);
        *((_DWORD *)this + 8) += v205;
        *((_DWORD *)this + 6) -= v205;
        *((_DWORD *)this + 9) = (v230 - 1) & (v205 + v226);
        ++v225;
        v231 = v215++;
        *((_DWORD *)a3 + v231) = v228 >> (char)v354;
        *((_DWORD *)a3 + v231 + 62) = v336;
      }
      while ( v225 < v343 );
      v207 = (unsigned int)v355;
    }
    v344 = dword_1800141D8[4 * v356 + 4 * (unsigned int)v353];
    if ( v344 > 0 )
    {
      v232 = 0;
      v337 = dword_180014130[v207];
      LODWORD(v354) = (unsigned __int16)(16 - v207);
      do
      {
        v233 = *((_DWORD *)this + 9);
        v234 = *((_QWORD *)this + 6);
        v235 = (*(unsigned __int8 *)(((v233 >> 3) & 0xFFFFFFFE) + 1 + v234)
              | (unsigned __int16)(*(unsigned __int8 *)(((v233 >> 3) & 0xFFFFFFFE) + v234) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        v236 = 16 - (v233 & 0xF);
        if ( v207 > v236 )
          v235 |= (unsigned __int16)(*(unsigned __int8 *)(((((v233 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)this + 4) - 1))
                                                        + 1
                                                        + v234)
                                   | (*(unsigned __int8 *)(((((v233 >> 3) & 0xFFFFFFFE) + 2)
                                                          & (*((_DWORD *)this + 4) - 1))
                                                         + v234) << 8)) >> v236;
        v237 = *((_DWORD *)this + 5);
        *((_DWORD *)this + 8) += v207;
        *((_DWORD *)this + 6) -= v207;
        *((_DWORD *)this + 9) = (v237 - 1) & (v207 + v233);
        ++v232;
        v238 = v215++;
        *((_DWORD *)a3 + v238) = v235 >> (char)v354;
        *((_DWORD *)a3 + v238 + 62) = v337;
      }
      while ( v232 < v344 );
    }
    v345 = *(int *)((char *)v361 + v357);
    if ( v345 > 0 )
    {
      v239 = HIDWORD(v352);
      v240 = 0;
      v338 = dword_180014130[SHIDWORD(v352)];
      LODWORD(v354) = (unsigned __int16)(16 - WORD6(v352));
      do
      {
        v241 = *((_DWORD *)this + 9);
        v242 = *((_QWORD *)this + 6);
        v243 = 16 - (v241 & 0xF);
        if ( v239 <= v243 )
          v244 = (*(unsigned __int8 *)(((v241 >> 3) & 0xFFFFFFFE) + 1 + v242)
                | (unsigned __int16)(*(unsigned __int8 *)(((v241 >> 3) & 0xFFFFFFFE) + v242) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        else
          v244 = ((*(unsigned __int8 *)(((v241 >> 3) & 0xFFFFFFFE) + 1 + v242)
                 | (unsigned __int16)(*(unsigned __int8 *)(((v241 >> 3) & 0xFFFFFFFE) + v242) << 8)) << (*((_BYTE *)this + 36) & 0xF))
               | ((unsigned __int16)(*(unsigned __int8 *)(((((v241 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)this + 4) - 1))
                                                        + 1
                                                        + v242)
                                   | (*(unsigned __int8 *)(((((v241 >> 3) & 0xFFFFFFFE) + 2)
                                                          & (*((_DWORD *)this + 4) - 1))
                                                         + v242) << 8)) >> v243);
        v245 = *((_DWORD *)this + 5);
        *((_DWORD *)this + 8) += v239;
        *((_DWORD *)this + 6) -= v239;
        *((_DWORD *)this + 9) = (v245 - 1) & (v239 + v241);
        ++v240;
        v246 = v215++;
        *((_DWORD *)a3 + v246) = v244 >> (char)v354;
        *((_DWORD *)a3 + v246 + 62) = v338;
      }
      while ( v240 < v345 );
    }
    *((_DWORD *)a3 + 83) = 1;
    *(_QWORD *)((char *)a3 + 84) = 0;
    *((_DWORD *)a3 + 84) = 1;
  }
}

```

## disassembly

```asm
0x1800078d0  mov     [rsp-8+arg_18], rbx
0x1800078d5  push    rbp
0x1800078d6  push    rsi
0x1800078d7  push    rdi
0x1800078d8  push    r12
0x1800078da  push    r13
0x1800078dc  push    r14
0x1800078de  push    r15
0x1800078e0  lea     rbp, [rsp-0Fh]
0x1800078e5  sub     rsp, 0A0h
0x1800078ec  xor     edi, edi
0x1800078ee  mov     rsi, r8
0x1800078f1  mov     [rcx+20h], edi
0x1800078f4  mov     r13, rdx
0x1800078f7  mov     rbx, rcx
0x1800078fa  cmp     [r9+20h], dil
0x1800078fe  jz      loc_180009264
0x180007904  cmp     [rdx+10h], edi
0x180007907  jz      loc_180008FE4
0x18000790d  cmp     dword ptr [rdx+14h], 2
0x180007911  jnz     loc_180008FE4
0x180007917  cmp     [rdx+18h], edi
0x18000791a  jz      loc_180008B12
0x180007920  movsxd  rdx, dword ptr [rdx+0Ch]
0x180007924  lea     rdi, __ImageBase
0x18000792b  mov     edx, ds:rva dword_180014150[rdi+rdx*4]; unsigned int
0x180007932  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x180007937  mov     [rsi], eax
0x180007939  mov     rcx, rbx; this
0x18000793c  movsxd  rdx, dword ptr [r13+0Ch]
0x180007940  mov     edx, ds:rva dword_180014150[rdi+rdx*4]; unsigned int
0x180007947  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000794c  mov     [rsi+4], eax
0x18000794f  mov     rcx, rbx; this
0x180007952  movsxd  rdx, dword ptr [r13+0Ch]
0x180007956  mov     edx, ds:rva dword_180014150[rdi+rdx*4]; unsigned int
0x18000795d  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x180007962  mov     [rsi+8], eax
0x180007965  mov     rcx, rbx; this
0x180007968  movsxd  rdx, dword ptr [r13+0Ch]
0x18000796c  mov     edx, ds:rva dword_180014150[rdi+rdx*4]; unsigned int
0x180007973  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x180007978  mov     [rsi+0Ch], eax
0x18000797b  mov     rcx, rbx; this
0x18000797e  movsxd  rdx, dword ptr [r13+0Ch]
0x180007982  mov     edx, ds:rva dword_180014150[rdi+rdx*4]; unsigned int
0x180007989  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000798e  mov     [rsi+10h], eax
0x180007991  mov     rcx, rbx; this
0x180007994  movsxd  rdx, dword ptr [r13+0Ch]
0x180007998  mov     edx, ds:rva dword_180014150[rdi+rdx*4]; unsigned int
0x18000799f  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x1800079a4  mov     [rsi+14h], eax
0x1800079a7  mov     rcx, rbx; this
0x1800079aa  movsxd  rdx, dword ptr [r13+0Ch]
0x1800079ae  mov     edx, ds:rva dword_180014150[rdi+rdx*4]; unsigned int
0x1800079b5  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x1800079ba  mov     [rsi+18h], eax
0x1800079bd  mov     rcx, rbx; this
0x1800079c0  movsxd  rdx, dword ptr [r13+0Ch]
0x1800079c4  mov     edx, ds:rva dword_180014150[rdi+rdx*4]; unsigned int
0x1800079cb  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x1800079d0  mov     [rsi+1Ch], eax
0x1800079d3  mov     r9d, 10h
0x1800079d9  movsxd  rax, dword ptr [r13+0Ch]
0x1800079dd  mov     r15d, [rbx+24h]
0x1800079e1  mov     edx, r15d
0x1800079e4  mov     r14, [rbx+30h]
0x1800079e8  and     edx, 0Fh
0x1800079eb  mov     ecx, edx
0x1800079ed  mov     r11d, ds:rva dword_180014150[rdi+rax*4]
0x1800079f5  mov     eax, r15d
0x1800079f8  sar     eax, 3
0x1800079fb  and     eax, 0FFFFFFFEh
0x1800079fe  mov     r8d, eax
0x180007a01  movzx   r10d, byte ptr [rax+r14]
0x180007a06  inc     eax
0x180007a08  shl     r10w, 8
0x180007a0d  movzx   eax, byte ptr [rax+r14]
0x180007a12  or      r10w, ax
0x180007a16  shl     r10w, cl
0x180007a1a  mov     ecx, r9d
0x180007a1d  sub     ecx, edx
0x180007a1f  cmp     r11d, ecx
0x180007a22  jbe     short loc_180007A4E
0x180007a24  mov     edx, [rbx+10h]
0x180007a27  lea     eax, [r8+2]
0x180007a2b  dec     edx
0x180007a2d  and     edx, eax
0x180007a2f  mov     eax, edx
0x180007a31  movzx   r8d, byte ptr [rdx+r14]
0x180007a36  shl     r8w, 8
0x180007a3b  inc     eax
0x180007a3d  movzx   eax, byte ptr [rax+r14]
0x180007a42  or      r8w, ax
0x180007a46  shr     r8w, cl
0x180007a4a  or      r10w, r8w
0x180007a4e  add     [rbx+20h], r11d
0x180007a52  lea     ecx, [r15+r11]
0x180007a56  sub     [rbx+18h], r11d
0x180007a5a  mov     eax, [rbx+14h]
0x180007a5d  dec     eax
0x180007a5f  and     ecx, eax
0x180007a61  movzx   eax, r10w
0x180007a65  mov     [rbx+24h], ecx
0x180007a68  mov     ecx, r9d
0x180007a6b  sub     cl, r11b
0x180007a6e  shr     eax, cl
0x180007a70  mov     [rsi+68h], eax
0x180007a73  movsxd  rax, dword ptr [r13+0Ch]
0x180007a77  mov     r15d, [rbx+24h]
0x180007a7b  mov     edx, r15d
0x180007a7e  mov     r14, [rbx+30h]
0x180007a82  and     edx, 0Fh
0x180007a85  mov     ecx, edx
0x180007a87  mov     r11d, ds:rva dword_180014150[rdi+rax*4]
0x180007a8f  mov     eax, r15d
0x180007a92  sar     eax, 3
0x180007a95  and     eax, 0FFFFFFFEh
0x180007a98  mov     r8d, eax
0x180007a9b  movzx   r10d, byte ptr [rax+r14]
0x180007aa0  inc     eax
0x180007aa2  shl     r10w, 8
0x180007aa7  movzx   eax, byte ptr [rax+r14]
0x180007aac  or      r10w, ax
0x180007ab0  shl     r10w, cl
0x180007ab4  mov     ecx, r9d
0x180007ab7  sub     ecx, edx
0x180007ab9  cmp     r11d, ecx
0x180007abc  jbe     short loc_180007AE8
0x180007abe  mov     edx, [rbx+10h]
0x180007ac1  lea     eax, [r8+2]
0x180007ac5  dec     edx
0x180007ac7  and     edx, eax
0x180007ac9  mov     eax, edx
0x180007acb  movzx   r8d, byte ptr [rdx+r14]
0x180007ad0  shl     r8w, 8
0x180007ad5  inc     eax
0x180007ad7  movzx   eax, byte ptr [rax+r14]
0x180007adc  or      r8w, ax
0x180007ae0  shr     r8w, cl
0x180007ae4  or      r10w, r8w
0x180007ae8  mov     eax, [rbx+14h]
0x180007aeb  lea     ecx, [r15+r11]
0x180007aef  dec     eax
0x180007af1  and     ecx, eax
0x180007af3  movzx   eax, r10w
0x180007af7  mov     [rbx+24h], ecx
0x180007afa  mov     ecx, r9d
0x180007afd  add     [rbx+20h], r11d
0x180007b01  sub     cl, r11b
0x180007b04  sub     [rbx+18h], r11d
0x180007b08  shr     eax, cl
0x180007b0a  mov     [rsi+9Ch], eax
0x180007b10  movsxd  rax, dword ptr [r13+0Ch]
0x180007b14  mov     r15d, [rbx+24h]
0x180007b18  mov     edx, r15d
0x180007b1b  mov     r14, [rbx+30h]
0x180007b1f  and     edx, 0Fh
0x180007b22  mov     ecx, edx
0x180007b24  mov     r11d, ds:rva dword_180014150[rdi+rax*4]
0x180007b2c  mov     eax, r15d
0x180007b2f  sar     eax, 3
0x180007b32  and     eax, 0FFFFFFFEh
0x180007b35  mov     r8d, eax
0x180007b38  movzx   r10d, byte ptr [rax+r14]
0x180007b3d  inc     eax
0x180007b3f  shl     r10w, 8
0x180007b44  movzx   eax, byte ptr [rax+r14]
0x180007b49  or      r10w, ax
0x180007b4d  shl     r10w, cl
0x180007b51  mov     ecx, r9d
0x180007b54  sub     ecx, edx
0x180007b56  cmp     r11d, ecx
0x180007b59  jbe     short loc_180007B85
0x180007b5b  mov     edx, [rbx+10h]
0x180007b5e  lea     eax, [r8+2]
0x180007b62  dec     edx
0x180007b64  and     edx, eax
0x180007b66  mov     eax, edx
0x180007b68  movzx   r8d, byte ptr [rdx+r14]
0x180007b6d  shl     r8w, 8
0x180007b72  inc     eax
0x180007b74  movzx   eax, byte ptr [rax+r14]
0x180007b79  or      r8w, ax
0x180007b7d  shr     r8w, cl
0x180007b81  or      r10w, r8w
0x180007b85  mov     eax, [rbx+14h]
0x180007b88  lea     ecx, [r15+r11]
0x180007b8c  dec     eax
0x180007b8e  and     ecx, eax
0x180007b90  movzx   eax, r10w
0x180007b94  mov     [rbx+24h], ecx
0x180007b97  mov     ecx, r9d
0x180007b9a  add     [rbx+20h], r11d
0x180007b9e  sub     cl, r11b
0x180007ba1  sub     [rbx+18h], r11d
0x180007ba5  shr     eax, cl
0x180007ba7  mov     [rsi+0D0h], eax
0x180007bad  movsxd  rax, dword ptr [r13+0Ch]
0x180007bb1  mov     r15d, [rbx+24h]
0x180007bb5  mov     edx, r15d
0x180007bb8  mov     r14, [rbx+30h]
0x180007bbc  and     edx, 0Fh
0x180007bbf  mov     ecx, edx
0x180007bc1  mov     r11d, ds:rva dword_180014150[rdi+rax*4]
0x180007bc9  mov     eax, r15d
0x180007bcc  sar     eax, 3
0x180007bcf  and     eax, 0FFFFFFFEh
0x180007bd2  mov     r8d, eax
0x180007bd5  movzx   r10d, byte ptr [rax+r14]
0x180007bda  inc     eax
0x180007bdc  shl     r10w, 8
0x180007be1  movzx   eax, byte ptr [rax+r14]
0x180007be6  or      r10w, ax
0x180007bea  shl     r10w, cl
0x180007bee  mov     ecx, r9d
0x180007bf1  sub     ecx, edx
0x180007bf3  cmp     r11d, ecx
0x180007bf6  jbe     short loc_180007C22
0x180007bf8  mov     edx, [rbx+10h]
0x180007bfb  lea     eax, [r8+2]
0x180007bff  dec     edx
0x180007c01  and     edx, eax
0x180007c03  mov     eax, edx
0x180007c05  movzx   r8d, byte ptr [rdx+r14]
0x180007c0a  shl     r8w, 8
0x180007c0f  inc     eax
0x180007c11  movzx   eax, byte ptr [rax+r14]
0x180007c16  or      r8w, ax
0x180007c1a  shr     r8w, cl
0x180007c1e  or      r10w, r8w
0x180007c22  add     [rbx+20h], r11d
0x180007c26  lea     ecx, [r15+r11]
0x180007c2a  sub     [rbx+18h], r11d
0x180007c2e  mov     eax, [rbx+14h]
0x180007c31  dec     eax
0x180007c33  and     ecx, eax
0x180007c35  movzx   eax, r10w
0x180007c39  mov     [rbx+24h], ecx
0x180007c3c  mov     ecx, r9d
0x180007c3f  sub     cl, r11b
0x180007c42  shr     eax, cl
0x180007c44  mov     [rsi+6Ch], eax
0x180007c47  movsxd  rax, dword ptr [r13+0Ch]
0x180007c4b  mov     r15d, [rbx+24h]
0x180007c4f  mov     edx, r15d
0x180007c52  mov     r14, [rbx+30h]
0x180007c56  and     edx, 0Fh
0x180007c59  mov     ecx, edx
0x180007c5b  mov     r11d, ds:rva dword_180014150[rdi+rax*4]
0x180007c63  mov     eax, r15d
0x180007c66  sar     eax, 3
0x180007c69  and     eax, 0FFFFFFFEh
0x180007c6c  mov     r8d, eax
0x180007c6f  movzx   r10d, byte ptr [rax+r14]
0x180007c74  inc     eax
0x180007c76  shl     r10w, 8
0x180007c7b  movzx   eax, byte ptr [rax+r14]
0x180007c80  or      r10w, ax
0x180007c84  shl     r10w, cl
0x180007c88  mov     ecx, r9d
0x180007c8b  sub     ecx, edx
0x180007c8d  cmp     r11d, ecx
0x180007c90  jbe     short loc_180007CBC
0x180007c92  mov     edx, [rbx+10h]
0x180007c95  lea     eax, [r8+2]
0x180007c99  dec     edx
0x180007c9b  and     edx, eax
0x180007c9d  mov     eax, edx
0x180007c9f  movzx   r8d, byte ptr [rdx+r14]
0x180007ca4  shl     r8w, 8
0x180007ca9  inc     eax
0x180007cab  movzx   eax, byte ptr [rax+r14]
0x180007cb0  or      r8w, ax
0x180007cb4  shr     r8w, cl
0x180007cb8  or      r10w, r8w
0x180007cbc  mov     eax, [rbx+14h]
0x180007cbf  lea     ecx, [r15+r11]
0x180007cc3  dec     eax
0x180007cc5  and     ecx, eax
0x180007cc7  movzx   eax, r10w
0x180007ccb  mov     [rbx+24h], ecx
0x180007cce  mov     ecx, r9d
0x180007cd1  add     [rbx+20h], r11d
0x180007cd5  sub     cl, r11b
0x180007cd8  sub     [rbx+18h], r11d
0x180007cdc  shr     eax, cl
0x180007cde  mov     [rsi+0A0h], eax
0x180007ce4  movsxd  rax, dword ptr [r13+0Ch]
0x180007ce8  mov     r15d, [rbx+24h]
0x180007cec  mov     edx, r15d
0x180007cef  mov     r14, [rbx+30h]
0x180007cf3  and     edx, 0Fh
0x180007cf6  mov     ecx, edx
0x180007cf8  mov     r11d, ds:rva dword_180014150[rdi+rax*4]
0x180007d00  mov     eax, r15d
0x180007d03  sar     eax, 3
0x180007d06  and     eax, 0FFFFFFFEh
0x180007d09  mov     r8d, eax
  ... truncated ...
```
