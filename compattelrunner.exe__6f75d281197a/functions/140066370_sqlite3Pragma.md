# sqlite3Pragma

- ea: `0x140066370`
- end: `0x140069ce5`
- name: `sqlite3Pragma`
- size: `14709`
- prototype: ``
- caller_count: `1`
- callee_count: `91`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400a40bc`

## callees

- `0x140001ba0`
- `0x140020730`
- `0x140024bec`
- `0x14002b178`
- `0x14002fbf8`
- `0x140031430`
- `0x1400314a8`
- `0x14003c92c`
- `0x140040520`
- `0x1400405f8`
- `0x140046bdc`
- `0x140046c34`
- `0x140048db0`
- `0x140048f88`
- `0x14004bdbc`
- `0x14004c754`
- `0x14004de08`
- `0x14004fa1c`
- `0x14004fa9c`
- `0x14004fb1c`
- `0x14004fb9c`
- `0x14004fce4`
- `0x140051668`
- `0x1400516cc`
- `0x1400518c4`
- `0x140051aa8`
- `0x140053e3c`
- `0x140053ef0`
- `0x140054248`
- `0x140056018`
- `0x1400560c4`
- `0x140056d98`
- `0x140057598`
- `0x1400592c0`
- `0x140059680`
- `0x140059fbc`
- `0x14005ae08`
- `0x14005ae90`
- `0x14005c130`
- `0x14005e31c`
- `0x14005eabc`
- `0x14005ebd0`
- `0x14005f5fc`
- `0x1400626b8`
- `0x140062858`
- `0x140062bfc`
- `0x14006345c`
- `0x1400636dc`
- `0x140063770`
- `0x140063830`

## string_xrefs

- `0x140069997`: `sqlite_temp_schema`
- `0x140069c2f`: `Safety level may not be changed inside a transaction`
- `0x140069674`: `not a writable directory`

## pseudocode

```c
__int64 __fastcall sqlite3Pragma(_QWORD **a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  _QWORD *v5; // r15
  _QWORD **v9; // r13
  __int64 result; // rax
  __int64 v11; // rsi
  int v12; // r14d
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  char *v16; // r12
  __int64 v17; // rax
  const char **v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // r10
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // rcx
  unsigned __int64 v32; // rbx
  char v33; // al
  int v34; // r11d
  __int64 v35; // rbx
  int AutoVacuum; // eax
  unsigned int v37; // r11d
  unsigned int v38; // r13d
  unsigned int v39; // r11d
  unsigned __int8 v40; // cl
  int v41; // ebx
  _DWORD *v42; // rax
  int v43; // r13d
  __int64 v44; // rcx
  __int64 v45; // r10
  unsigned int v46; // r11d
  __int64 v47; // rbx
  _DWORD *v48; // rax
  int v49; // r9d
  __int64 v50; // r8
  unsigned int v51; // edx
  int Int32; // eax
  __int64 v53; // r8
  int v54; // edi
  char SafetyLevel; // al
  __int64 v56; // rcx
  __int64 v57; // rdx
  unsigned __int64 v58; // rcx
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rcx
  unsigned int j; // ebx
  char *v66; // r8
  int v67; // r8d
  __int64 v68; // r9
  unsigned int v69; // edx
  __int64 **v70; // rbx
  unsigned int v71; // edi
  char v72; // al
  unsigned int i; // ebx
  __int64 v74; // r8
  __int64 v75; // rcx
  __int64 v76; // rax
  __int64 *v77; // rax
  __int64 v78; // rdx
  int *v79; // rax
  unsigned int v80; // ecx
  unsigned int v81; // ecx
  unsigned int v82; // ecx
  unsigned int v83; // ecx
  unsigned int v84; // ecx
  unsigned int v85; // ecx
  unsigned int v86; // ecx
  unsigned int v87; // ecx
  __int64 v88; // rbx
  __int64 v89; // rcx
  int v90; // edi
  __int64 v91; // rdx
  __int64 v92; // rbx
  unsigned int v93; // edi
  bool v94; // zf
  const char **v95; // rbx
  __int64 v96; // rdx
  __int64 v97; // rax
  __int64 v98; // r8
  int v99; // ecx
  __int64 v100; // r9
  __int64 v101; // rax
  unsigned __int16 *v102; // r8
  unsigned int v103; // ebx
  unsigned int v104; // edi
  __int64 v105; // rbx
  __int64 v106; // r12
  __int64 v107; // rdx
  __int64 v108; // rcx
  int v109; // ebx
  unsigned int v110; // ebx
  __int64 v111; // rax
  __int64 v112; // rax
  unsigned int v113; // ebx
  __int64 m; // r13
  __int64 n; // rdi
  _QWORD *v116; // rdi
  __int64 v117; // rax
  __int64 v118; // rbx
  __int64 v119; // rcx
  int v120; // edi
  __int64 v121; // rdx
  int v122; // eax
  int v123; // r13d
  unsigned int v124; // r12d
  const char *v125; // r10
  const char *v126; // r9
  int v127; // eax
  unsigned int v128; // ecx
  const char **v129; // rcx
  __int64 Table; // rax
  __int64 v131; // rcx
  __int64 v132; // rdx
  __int64 v133; // r8
  const char **v134; // rbx
  int v135; // ecx
  int v136; // r8d
  int v137; // ecx
  __int64 k; // rax
  __int64 v139; // rax
  int v140; // r8d
  __int64 v141; // r12
  const char **v142; // r8
  __int64 v143; // rbx
  __int64 v144; // rax
  int v145; // ecx
  int v146; // eax
  int v147; // edx
  int v148; // edi
  __int64 v149; // r15
  int v150; // r13d
  int v151; // r9d
  unsigned int v152; // ebx
  int v153; // edi
  unsigned int v154; // eax
  int v155; // edi
  __int64 v156; // rbx
  unsigned int v157; // ebx
  char *v158; // rdx
  const char *v159; // rax
  char **v160; // rbx
  __int64 v161; // rdx
  char v162; // r11
  __int64 v163; // rcx
  int v164; // r11d
  _DWORD *v165; // rax
  int v166; // r14d
  __int64 v167; // rcx
  int v168; // eax
  __int64 v169; // r9
  __int64 v170; // r11
  unsigned int v171; // eax
  int v172; // ebx
  __int64 v173; // rdx
  int v174; // ecx
  __int64 v175; // rax
  _QWORD *v176; // rax
  __int64 v177; // rdx
  __int64 v178; // rdx
  int v179; // r8d
  int v180; // eax
  int *v181; // rax
  int *v182; // rdi
  __int64 v183; // r10
  int v184; // r9d
  _QWORD *ii; // r8
  __int64 v186; // rdx
  __int64 v187; // rcx
  __int64 jj; // rdx
  int v189; // ebx
  unsigned int v190; // eax
  __int64 v191; // rax
  unsigned int v192; // edi
  __int64 v193; // rbx
  unsigned int v194; // eax
  __int64 v195; // rdi
  const char **v196; // rdi
  __int64 v197; // r10
  int TempRange; // eax
  __int64 v199; // r10
  int v200; // edx
  int v201; // r13d
  const char *v202; // r15
  int v203; // eax
  int v204; // r9d
  int v205; // edx
  __int64 v206; // r8
  int v207; // eax
  int v208; // r9d
  const char *kk; // rcx
  __int64 LastOp; // rax
  int v211; // ebx
  unsigned int v212; // edi
  __int64 v213; // rbx
  unsigned int v214; // eax
  unsigned int v215; // r10d
  int v216; // ebx
  int v217; // esi
  __int64 v218; // r15
  int v219; // edi
  __int64 v220; // rdx
  int v221; // r9d
  const char *v222; // rax
  char *v223; // rcx
  BOOL v224; // r9d
  bool v225; // cc
  int v226; // r11d
  int v227; // ecx
  __int64 v228; // rax
  _BYTE *v229; // r8
  int v230; // r9d
  const char *mm; // rcx
  __int16 v232; // ax
  unsigned int v233; // edx
  const char **v234; // rax
  unsigned int v235; // eax
  int v236; // edx
  __int64 v237; // rcx
  const char *v238; // r8
  __int64 v239; // rbx
  unsigned int v240; // eax
  unsigned int v241; // ebx
  __int64 v242; // rcx
  __int64 v243; // rax
  __int64 v244; // rax
  int v245; // ebx
  __int64 v246; // rax
  bool v247; // sf
  const char **v248; // rbx
  unsigned int v249; // eax
  __int64 v250; // rax
  __int64 v251; // rbx
  unsigned int v252; // eax
  int v253; // eax
  const char *v254; // rdx
  __int64 v255; // rax
  __int64 v256; // rcx
  unsigned int v257; // eax
  int v258; // ebx
  unsigned int v259; // r15d
  __int64 v260; // rdi
  __int64 v261; // rbx
  unsigned int v262; // eax
  __int64 v263; // rbx
  __int64 v264; // rdx
  int v265; // ecx
  const char **v266; // r15
  int v267; // edi
  unsigned int v268; // ebx
  unsigned int v269; // ebx
  unsigned int v270; // edx
  int v271; // r15d
  unsigned int v272; // ebx
  int v273; // edx
  int v274; // r13d
  __int64 v275; // rax
  unsigned int v276; // ebx
  int v277; // ebx
  const char *v278; // rbx
  int v279; // r13d
  int v280; // r15d
  const char *v281; // rax
  unsigned int v282; // eax
  __int64 v283; // rcx
  unsigned int v284; // edi
  __int64 v285; // rax
  char v286; // r9
  __int64 v287; // rax
  __int64 v288; // r8
  __int64 *v289; // rax
  unsigned int v290; // ecx
  unsigned int v291; // ecx
  unsigned int v292; // ecx
  unsigned int v293; // ecx
  __int64 v294; // rdx
  int v295; // r12d
  __int64 v296; // rax
  __int64 v297; // rcx
  int v298; // r12d
  __int64 v299; // rax
  __int64 v300; // rcx
  unsigned __int8 *v301; // rax
  int v302; // ebx
  int v303; // eax
  int v304; // r9d
  int v305; // r8d
  int v306; // r11d
  const char *v307; // rdi
  int v308; // r8d
  int v309; // eax
  char v310; // al
  int i3; // r9d
  __int64 *v312; // rax
  __int64 v313; // rcx
  __int64 v314; // rax
  __int64 v315; // rax
  __int64 v316; // rcx
  __int64 *v317; // rcx
  __int64 v318; // rax
  __int64 v319; // rdi
  __int64 v320; // rcx
  int v321; // r13d
  __int64 v322; // rcx
  unsigned int v323; // ecx
  char *v324; // rdx
  int v325; // ebx
  __int64 v326; // r12
  int v327; // ecx
  _QWORD *i2; // rbx
  unsigned int v329; // ecx
  unsigned int v330; // ecx
  unsigned int v331; // ecx
  __int64 v332; // r13
  int v333; // ebx
  int v334; // r11d
  int i4; // edi
  __int64 i5; // rbx
  __int64 v337; // rbx
  int v338; // ecx
  __int64 v339; // rdx
  int v340; // eax
  _QWORD *i6; // r12
  __int64 v342; // rbx
  __int64 v343; // rax
  __int16 v344; // cx
  __int64 v345; // rbx
  char v346; // cl
  int v347; // ebx
  unsigned __int8 v348; // cl
  unsigned int v349; // eax
  unsigned int v350; // eax
  unsigned int v351; // ecx
  unsigned int v352; // ecx
  unsigned int v353; // ecx
  unsigned int v354; // ecx
  unsigned int v355; // ecx
  unsigned int v356; // ecx
  unsigned int v357; // ecx
  unsigned int v358; // ecx
  int v359; // r9d
  int v360; // edi
  int v361; // r11d
  int v362; // r8d
  __int64 v363; // rax
  __int64 v364; // rax
  int v365; // eax
  int v366; // r11d
  unsigned __int8 *v367; // rbx
  const char **v368; // rbx
  const char **v369; // rdx
  int nn; // r13d
  __int64 v371; // r11
  __int64 v372; // rdx
  __int64 v373; // rcx
  int v374; // edi
  _QWORD *i1; // rax
  __int64 v376; // r8
  __int64 v377; // rax
  __int64 v378; // r8
  _QWORD *v379; // r11
  _QWORD *v380; // rdi
  const char *v381; // rax
  unsigned int v382; // ecx
  const char *v383; // rax
  __int64 v384; // r11
  const char *v385; // r11
  __int64 v386; // rax
  __int64 v387; // rdi
  __int64 v388; // rdx
  int v389; // ecx
  __int64 v390; // r15
  int v391; // r9d
  __int64 v392; // r12
  signed int v393; // r8d
  __int16 v394; // ax
  int v395; // r13d
  __int64 v396; // rax
  __int64 v397; // r9
  unsigned int v398; // r11d
  __int64 v399; // rax
  int v400; // r10d
  int v401; // r11d
  int v402; // r8d
  __int64 v403; // r9
  const char *v404; // r8
  char v405; // al
  __int64 v406; // rcx
  int v407; // eax
  __int64 v408; // [rsp+20h] [rbp-E0h]
  int v409; // [rsp+20h] [rbp-E0h]
  __int64 v410; // [rsp+20h] [rbp-E0h]
  __int64 v411; // [rsp+28h] [rbp-D8h]
  __int64 v412; // [rsp+28h] [rbp-D8h]
  int v413; // [rsp+28h] [rbp-D8h]
  int v414; // [rsp+28h] [rbp-D8h]
  int v415; // [rsp+30h] [rbp-D0h]
  __int64 v416; // [rsp+38h] [rbp-C8h]
  int v417; // [rsp+40h] [rbp-C0h]
  int v418; // [rsp+48h] [rbp-B8h]
  int String; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v420; // [rsp+64h] [rbp-9Ch] BYREF
  int v421; // [rsp+68h] [rbp-98h] BYREF
  __int64 v422; // [rsp+70h] [rbp-90h] BYREF
  __int64 v423; // [rsp+78h] [rbp-88h] BYREF
  __int64 v424; // [rsp+80h] [rbp-80h] BYREF
  __int64 v425; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v426; // [rsp+90h] [rbp-70h] BYREF
  unsigned int IndexKey; // [rsp+94h] [rbp-6Ch]
  int v428; // [rsp+98h] [rbp-68h]
  unsigned int v429; // [rsp+9Ch] [rbp-64h]
  __int64 v430; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v431; // [rsp+A8h] [rbp-58h]
  __int64 v432; // [rsp+B0h] [rbp-50h]
  const char **v433; // [rsp+B8h] [rbp-48h]
  int v434; // [rsp+C0h] [rbp-40h]
  int v435; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned int v436; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v437; // [rsp+CCh] [rbp-34h]
  int v438; // [rsp+D0h] [rbp-30h] BYREF
  int v439; // [rsp+D4h] [rbp-2Ch]
  char *v440; // [rsp+D8h] [rbp-28h]
  __int64 v441; // [rsp+E0h] [rbp-20h]
  int v442; // [rsp+E8h] [rbp-18h]
  __int64 v443; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD *v444; // [rsp+F8h] [rbp-8h]
  __int64 Index; // [rsp+100h] [rbp+0h]
  const char **v446; // [rsp+108h] [rbp+8h]
  unsigned __int8 *v447; // [rsp+110h] [rbp+10h]
  __int64 v448; // [rsp+118h] [rbp+18h]
  _QWORD v449[3]; // [rsp+120h] [rbp+20h]
  __int128 v450; // [rsp+138h] [rbp+38h] BYREF
  __int128 v451; // [rsp+148h] [rbp+48h]

  v5 = *a1;
  v444 = *a1;
  v430 = a3;
  v423 = 0;
  v450 = 0;
  v9 = a1;
  v451 = 0;
  Index = (__int64)a1;
  result = sqlite3GetVdbe(a1);
  v443 = result;
  v11 = result;
  if ( result )
  {
    v12 = 1;
    sqlite3VdbeAddOp3(result, 166, 1, 1, 0);
    *((_DWORD *)v9 + 14) = 2;
    result = sqlite3TwoPartName(v9, a2, a3, &v423);
    v13 = (int)result;
    if ( (int)result >= 0 )
    {
      v424 = v5[4];
      if ( (_DWORD)result != 1 || (result = sqlite3OpenTempDatabase(v9), !(_DWORD)result) )
      {
        result = sqlite3NameFromToken(v5, v423);
        v447 = (unsigned __int8 *)result;
        if ( result )
        {
          v14 = 32 * v13;
          if ( a5 )
            v15 = sqlite3MPrintf(v5, "-%T", a4);
          else
            v15 = sqlite3NameFromToken(v5, a4);
          v16 = (char *)v15;
          v440 = (char *)v15;
          if ( *(_DWORD *)(v430 + 8) )
            v17 = *(_QWORD *)(v14 + v424);
          else
            v17 = 0;
          v433 = (const char **)v17;
          if ( (unsigned int)sqlite3AuthCheck((_DWORD)v9, 19, (_DWORD)v447, (_DWORD)v16, v17) )
            goto LABEL_806;
          v18 = v433;
          *(_QWORD *)&v450 = 0;
          *((_QWORD *)&v450 + 1) = v447;
          v451 = (unsigned __int64)v16;
          *((_DWORD *)v5 + 166) = 0;
          v19 = sqlite3_file_control(v5, v18, 14, &v450);
          v420 = v19;
          if ( !v19 )
          {
            sqlite3VdbeSetNumCols(v11, 1);
            sqlite3VdbeSetColName(v11, 0, 0, v450, -1);
            returnSingleText(v11, v450);
            sqlite3_free(v450);
            goto LABEL_806;
          }
          if ( v19 != 12 )
          {
            if ( (_QWORD)v450 )
            {
              sqlite3ErrorMsg(v9, "%s", (const char *)v450);
              sqlite3_free(v450);
              v19 = v420;
            }
            goto LABEL_18;
          }
          v20 = pragmaLocate(v447);
          v425 = v20;
          v22 = v20;
          if ( !v20 )
            goto LABEL_806;
          if ( (*(_BYTE *)(v20 + 9) & 1) != 0 )
          {
            if ( (unsigned int)sqlite3ReadSchema(v9) )
              goto LABEL_806;
            v22 = v425;
          }
          if ( (*(_BYTE *)(v22 + 9) & 2) == 0 && ((*(_BYTE *)(v22 + 9) & 4) == 0 || !v16) )
          {
            setPragmaResultColumnNames(v11, v22);
            v22 = v425;
          }
          v23 = *(unsigned __int8 *)(v22 + 8);
          if ( v23 <= 0x16 )
          {
            if ( v23 != 22 )
            {
              if ( v23 <= 0xC )
              {
                if ( v23 == 12 )
                {
                  *((_DWORD *)v9 + 14) = 3;
                  for ( i = 0; (signed int)i < *((_DWORD *)v5 + 10); ++i )
                  {
                    v74 = v5[4];
                    v75 = 32LL * (int)i;
                    v76 = *(_QWORD *)(v75 + v74 + 8);
                    if ( v76 )
                    {
                      v77 = *(__int64 **)(v76 + 8);
                      v78 = *v77;
                      if ( *(_BYTE *)(*v77 + 19) || *(char **)v78 == byte_1400C5000 )
                        v79 = &dword_1400B1D54;
                      else
                        v79 = *(int **)(v78 + 216);
                      sqlite3VdbeMultiLoad(v11, 1, "iss", i, *(_QWORD *)(v75 + v74), v79, v415, v416, v417, v418);
                    }
                  }
                  goto LABEL_806;
                }
                if ( v23 <= 7 )
                {
                  if ( v23 == 7 )
                  {
                    AutoVacuum = 0;
                    if ( v16 )
                    {
                      String = 1;
                      Int32 = sqlite3GetInt32(v16, &String);
                      v54 = String;
                      if ( Int32 )
                        sqlite3BtreeSetSpillSize(*(_QWORD *)(v14 + v424 + 8), (unsigned int)String);
                      LOBYTE(v53) = v54 != 0;
                      SafetyLevel = getSafetyLevel(v16, 1, v53);
                      v56 = v5[6];
                      v57 = v56 | 0x20;
                      v58 = v56 & 0xFFFFFFFFFFFFFFDFuLL;
                      if ( !SafetyLevel )
                        v57 = v58;
                      v5[6] = v57;
                      goto LABEL_92;
                    }
                    if ( (v5[6] & 0x20) != 0 )
                      AutoVacuum = sqlite3BtreeSetSpillSize(*(_QWORD *)(v14 + v424 + 8), 0);
                  }
                  else
                  {
                    v24 = v23 - 1;
                    if ( !v24 )
                    {
                      v423 = 0;
                      if ( v16 && !(unsigned int)sqlite3DecOrHexToI64(v16) && v423 >= 0 )
                        *((_DWORD *)v5 + 186) = v423 & 0x7FFFFFFF;
                      v28 = *((int *)v5 + 186);
                      goto LABEL_805;
                    }
                    v25 = v24 - 1;
                    if ( !v25 )
                    {
                      v43 = *(_DWORD *)(v22 + 16);
                      sqlite3VdbeUsesBtree(v11, (unsigned int)v13);
                      if ( !v16 || (*(_BYTE *)(v45 + 9) & 8) != 0 )
                      {
                        v48 = (_DWORD *)sqlite3VdbeAddOpList(v44, 3, qword_1400B5930);
                        v48[1] = v13;
                        v48[7] = v13;
                        v48[9] = v43;
                        v49 = *(_DWORD *)(v11 + 144);
                        if ( v49 > 1 )
                        {
                          v50 = *(_QWORD *)(v11 + 136);
                          v51 = 1;
                          while ( *(_BYTE *)(v50 + 24LL * v51) != 0xA6 )
                          {
                            if ( (int)++v51 >= v49 )
                              goto LABEL_806;
                          }
                          *(_BYTE *)(v50 + 24) = -72;
                        }
                      }
                      else
                      {
                        String = 0;
                        v47 = sqlite3VdbeAddOpList(v44, v46, qword_1400B18C0);
                        *(_DWORD *)(v47 + 4) = v13;
                        *(_DWORD *)(v47 + 28) = v13;
                        *(_DWORD *)(v47 + 32) = v43;
                        sqlite3GetInt32(v16, &String);
                        *(_DWORD *)(v47 + 36) = String;
                        *(_WORD *)(v47 + 26) = 1;
                        if ( v43 == 1 && (v5[6] & 0x10000000) != 0 )
                          *(_BYTE *)(v47 + 24) = -72;
                      }
                      goto LABEL_806;
                    }
                    v26 = v25 - 1;
                    if ( v26 )
                    {
                      v27 = v26 - 1;
                      if ( v27 )
                      {
                        if ( v27 == 2 )
                        {
                          if ( !v16 )
                          {
                            v28 = *(int *)(*(_QWORD *)(v14 + v424 + 24) + 116LL);
LABEL_805:
                            returnSingleInt(v11, v28);
                            goto LABEL_806;
                          }
                          String = 0;
                          sqlite3GetInt32(v16, &String);
                          v29 = v424;
                          *(_DWORD *)(*(_QWORD *)(v14 + v424 + 24) + 116LL) = String;
                          v30 = *(_QWORD *)(v14 + v29 + 24);
                          v31 = *(_QWORD *)(v14 + v29 + 8);
LABEL_293:
                          sqlite3BtreeSetCacheSize(v31, *(unsigned int *)(v30 + 116));
                          goto LABEL_806;
                        }
LABEL_677:
                        if ( v16 )
                        {
                          v420 = 0;
                          sqlite3GetInt32(v16, &v420);
                          sqlite3_busy_timeout(v5, v420);
                        }
                        v28 = *((int *)v5 + 187);
                        goto LABEL_805;
                      }
                      if ( !v16 )
                      {
                        setPragmaResultColumnNames(v11, v22);
                        v28 = (*(_QWORD *)(v425 + 16) & v5[6]) != 0;
                        goto LABEL_805;
                      }
                      v32 = *(_QWORD *)(v22 + 16) & 0xFFFFFFFFFFFFBFFFuLL;
                      if ( *((_BYTE *)v5 + 101) )
                        v32 = *(_QWORD *)(v22 + 16);
                      v33 = getSafetyLevel(v16, 1, 0);
                      v34 = 0;
                      if ( v33 )
                      {
                        v5[6] |= v32;
                      }
                      else
                      {
                        v5[6] &= ~v32;
                        if ( v32 == 0x80000 )
                        {
                          v5[96] = 0;
                        }
                        else if ( (v32 & 1) != 0 && !(unsigned int)sqlite3StrICmp(v16, "reset") )
                        {
                          sqlite3ResetAllSchemasOfConnection(v5);
                          v34 = 0;
                        }
                      }
                      sqlite3VdbeAddOp3(v11, 166, 0, 0, v34);
LABEL_92:
                      setAllPagerFlags(v5);
                      goto LABEL_806;
                    }
                    v35 = *(_QWORD *)(v14 + v424 + 8);
                    if ( v16 )
                    {
                      if ( (unsigned int)sqlite3StrICmp(v16, "none") )
                      {
                        if ( (unsigned int)sqlite3StrICmp(v16, "full") )
                        {
                          if ( (unsigned int)sqlite3StrICmp(v16, "incremental") )
                          {
                            v426 = v39;
                            sqlite3GetInt32(v16, &v426);
                            v40 = v426;
                            if ( v426 > 2 )
                              v40 = 0;
                            v38 = v40;
                          }
                          else
                          {
                            v38 = 2;
                          }
                        }
                        else
                        {
                          v38 = 1;
                        }
                      }
                      else
                      {
                        v38 = v37;
                      }
                      *((_BYTE *)v5 + 106) = v38;
                      if ( !(unsigned int)sqlite3BtreeSetAutoVacuum(v35, v38) && v38 - 1 <= 1 )
                      {
                        v41 = *(_DWORD *)(v11 + 144);
                        v42 = (_DWORD *)sqlite3VdbeAddOpList(v11, 5, qword_1400B2770);
                        v42[14] = v41 + 4;
                        v42[27] = v38 - 1;
                        v42[1] = v13;
                        v42[7] = v13;
                        v42[25] = v13;
                        sqlite3VdbeUsesBtree(v11, (unsigned int)v13);
                      }
                      goto LABEL_806;
                    }
                    AutoVacuum = sqlite3BtreeGetAutoVacuum(v35);
                  }
LABEL_55:
                  v28 = AutoVacuum;
                  goto LABEL_805;
                }
                v59 = v23 - 8;
                if ( !v59 )
                {
                  if ( v16 )
                  {
                    v72 = getSafetyLevel(v16, 1, 0);
                    sqlite3RegisterLikeFunctions(v5, v72 != 0);
                  }
                  goto LABEL_806;
                }
                v60 = v59 - 1;
                if ( v60 )
                {
                  v61 = v60 - 1;
                  if ( !v61 )
                  {
                    *((_DWORD *)v9 + 14) = 1;
                    for ( j = 0; j <= 0x25; ++j )
                    {
                      v66 = off_1400AACF0[j];
                      if ( !v66 )
                        break;
                      sqlite3VdbeLoadString(v11, 1, v66);
                      sqlite3VdbeAddOp3(v11, 84, 1, 1, 0);
                    }
                    v67 = *(_DWORD *)(v11 + 144);
                    v5 = v444;
                    v16 = v440;
                    if ( v67 > 1 )
                    {
                      v68 = *(_QWORD *)(v11 + 136);
                      v69 = 1;
                      while ( *(_BYTE *)(v68 + 24LL * v69) != 0xA6 )
                      {
                        if ( (int)++v69 >= v67 )
                          goto LABEL_806;
                      }
                      *(_BYTE *)(v68 + 24) = -72;
                    }
                    goto LABEL_806;
                  }
                  if ( v61 != 1 )
                    goto LABEL_677;
                  if ( (_BYTE)word_1400C84B4 )
                  {
                    v62 = ((__int64 (__fastcall *)(__int64))xmmword_1400C8520)(11);
                    if ( v62 )
                      ((void (__fastcall *)(__int64))xmmword_1400C8530)(v62);
                  }
                  if ( !v16 )
                  {
                    v63 = sqlite3_data_directory;
LABEL_102:
                    returnSingleText(v11, v63);
                    goto LABEL_708;
                  }
                  if ( !*v16
                    || (v64 = *v5,
                        String = 0,
                        !(*(unsigned int (__fastcall **)(__int64, char *, __int64, int *))(v64 + 56))(
                           v64,
                           v16,
                           1,
                           &String))
                    && String )
                  {
                    sqlite3_free(sqlite3_data_directory);
                    if ( *v16 )
                      sqlite3_data_directory = sqlite3_mprintf("%s", v16);
                    else
                      sqlite3_data_directory = 0;
LABEL_708:
                    if ( (_BYTE)word_1400C84B4 )
                    {
                      v364 = ((__int64 (__fastcall *)(__int64))xmmword_1400C8520)(11);
                      if ( v364 )
                        ((void (__fastcall *)(__int64))xmmword_1400C8540)(v364);
                    }
                    goto LABEL_806;
                  }
                  goto LABEL_707;
                }
                *((_DWORD *)v9 + 14) = 2;
                v70 = (__int64 **)v5[79];
                v71 = 0;
                if ( !v70 )
                  goto LABEL_806;
                do
                {
                  sqlite3VdbeMultiLoad(v11, 1, "is", v71, *v70[2], v411, v415, v416, v417, v418);
                  v70 = (__int64 **)*v70;
                  ++v71;
                }
                while ( v70 );
LABEL_791:
                v16 = v440;
                goto LABEL_806;
              }
              v80 = v23 - 13;
              if ( !v80 )
              {
                sqlite3VdbeUsesBtree(v11, (unsigned int)v13);
                if ( !v16 )
                {
                  *((_DWORD *)v9 + 14) += v164;
                  v165 = (_DWORD *)sqlite3VdbeAddOpList(v163, 9, qword_1400B1770);
                  v165[1] = v13;
                  v165[7] = v13;
                  v165[37] = -2000;
                  goto LABEL_806;
                }
                String = 0;
                sqlite3GetInt32(v16, &String);
                v166 = String;
                if ( String < 0 )
                {
                  if ( String == 0x80000000 )
                    v166 = 0x7FFFFFFF;
                  else
                    v166 = -String;
                }
                sqlite3BeginWriteOperation(v9, 0, (unsigned int)v13);
                sqlite3VdbeAddOp3(v11, 100, v13, 3, v166);
                v167 = v424;
                *(_DWORD *)(*(_QWORD *)(v14 + v424 + 24) + 116LL) = v166;
                v30 = *(_QWORD *)(v14 + v167 + 24);
                v31 = *(_QWORD *)(v14 + v167 + 8);
                goto LABEL_293;
              }
              v81 = v80 - 1;
              if ( v81 )
              {
                v82 = v81 - 1;
                if ( !v82 )
                {
                  _mm_lfence();
                  v127 = *((_DWORD *)v9 + 14);
                  v128 = v127 + 1;
                  v127 += 5;
                  *((_DWORD *)v9 + 14) = v127;
                  v426 = v128;
                  v435 = v127;
                  v129 = *(const char ***)(*(_QWORD *)(v14 + v5[4] + 24) + 16LL);
                  while ( v129 )
                  {
                    if ( v16 )
                    {
                      Table = sqlite3LocateTable(v9, 0, v16, v433);
                      v129 = 0;
                    }
                    else
                    {
                      Table = (__int64)v129[2];
                      v129 = (const char **)*v129;
                    }
                    v446 = v129;
                    v425 = Table;
                    if ( Table && !*(_BYTE *)(Table + 63) && *(_QWORD *)(Table + 72) )
                    {
                      v131 = *(_QWORD *)(Table + 96);
                      v132 = 4294934528LL;
                      v421 = -32768;
                      if ( v131 )
                      {
                        v132 = 0;
                        v133 = v5[4];
                        v421 = 0;
                        if ( *(_QWORD *)(v133 + 24) != v131 )
                        {
                          do
                            v132 = (unsigned int)(v132 + 1);
                          while ( *(_QWORD *)(32LL * (int)v132 + v133 + 24) != v131 );
                          v421 = v132;
                        }
                      }
                      v134 = *(const char ***)(32LL * (int)v132 + v5[4]);
                      v433 = v134;
                      sqlite3CodeVerifySchema(v9, v132);
                      sqlite3TableLock((_DWORD)v9, v421, *(_DWORD *)(v425 + 40), 0, *(_QWORD *)v425);
                      v135 = v425;
                      v136 = v435 + *(__int16 *)(v425 + 54);
                      if ( *((_DWORD *)v9 + 14) < v136 )
                        *((_DWORD *)v9 + 14) = v136;
                      sqlite3OpenTable((_DWORD)v9, 0, v421, v135, 112);
                      sqlite3VdbeLoadString(v11, v426, *(_QWORD *)v425);
                      v137 = 1;
                      for ( k = *(_QWORD *)(v425 + 72); ; k = *(_QWORD *)(v443 + 8) )
                      {
                        v443 = k;
                        LODWORD(v432) = v137;
                        if ( !k )
                          break;
                        v139 = sqlite3FindTable(v5, *(_QWORD *)(k + 16), v134);
                        v423 = v139;
                        if ( v139 )
                        {
                          v140 = *(_DWORD *)(v139 + 40);
                          v424 = 0;
                          sqlite3TableLock((_DWORD)v9, v421, v140, 0, *(_QWORD *)v139);
                          if ( (unsigned int)sqlite3FkLocateIndex((_DWORD)v9, v423, v443, (unsigned int)&v424, 0) )
                            goto LABEL_806;
                          if ( v424 )
                          {
                            sqlite3VdbeAddOp3(v11, 112, v432, *(_DWORD *)(v424 + 88), v421);
                            sqlite3VdbeSetP4KeyInfo(v9, v424);
                          }
                          else
                          {
                            sqlite3OpenTable((_DWORD)v9, v432, v421, v423, 112);
                          }
                        }
                        v137 = v432 + 1;
                      }
                      if ( *((_DWORD *)v9 + 13) < v137 )
                        *((_DWORD *)v9 + 13) = v137;
                      v437 = sqlite3VdbeAddOp3(v11, 36, 0, 0, 0);
                      v434 = 1;
                      v430 = *(_QWORD *)(v425 + 72);
                      if ( v430 )
                      {
                        v141 = v425;
                        v436 = v426 + 2;
                        v420 = v426 + 1;
                        do
                        {
                          v142 = v134;
                          v143 = v430;
                          v144 = sqlite3FindTable(v5, *(_QWORD *)(v430 + 16), v142);
                          v422 = v144;
                          v424 = 0;
                          v443 = 0;
                          if ( v144 )
                            sqlite3FkLocateIndex((_DWORD)v9, v144, v143, (unsigned int)&v424, (__int64)&v443);
                          v145 = v435;
                          v146 = *((_DWORD *)v9 + 17) - 1;
                          *((_DWORD *)v9 + 17) = v146;
                          v147 = v145 + *(_DWORD *)(v143 + 40);
                          LODWORD(v432) = v146;
                          if ( *((_DWORD *)v9 + 14) < v147 )
                            *((_DWORD *)v9 + 14) = v147;
                          v148 = 0;
                          if ( *(int *)(v143 + 40) > 0 )
                          {
                            v149 = v443;
                            v150 = v145;
                            do
                            {
                              if ( v149 )
                                v151 = *(_DWORD *)(v149 + 4LL * v148);
                              else
                                v151 = *(_DWORD *)(v143 + 16 * (v148 + 4LL));
                              sqlite3ExprCodeGetColumnOfTable(v11, v141, 0, v151, v148 + v150);
                              sqlite3VdbeAddOp3(v11, 50, v148 + v150, v432, 0);
                              v143 = v430;
                              ++v148;
                            }
                            while ( v148 < *(_DWORD *)(v430 + 40) );
                            v5 = v444;
                            v9 = (_QWORD **)Index;
                            v145 = v435;
                          }
                          if ( v424 )
                          {
                            v423 = *(_QWORD *)(v424 + 32);
                            if ( !v423 )
                              v423 = computeIndexAffStr(v5, v424);
                            v152 = *(_DWORD *)(v143 + 40);
                            v153 = v435;
                            v154 = sqlite3VdbeAddOp3(v11, 96, v435, v152, 0);
                            sqlite3VdbeChangeP4(v11, v154, v423, v152);
                            v143 = v430;
                            v409 = v153;
                            v155 = v434;
                            sqlite3VdbeAddOp4Int(v11, 29, v434, v432, v409, *(_DWORD *)(v430 + 40));
                          }
                          else
                          {
                            v155 = v434;
                            if ( v422 )
                            {
                              sqlite3VdbeAddOp3(v11, 30, v434, *(_DWORD *)(v11 + 144) + 2, v145);
                              sqlite3VdbeAddOp3(v11, 9, 0, v432, 0);
                            }
                          }
                          sqlite3VdbeAddOp3(v11, (*(_DWORD *)(v141 + 48) & 0x80u) != 0 ? 75 : 135, 0, v420, 0);
                          LODWORD(v410) = v155 - 1;
                          sqlite3VdbeMultiLoad(
                            v11,
                            v436,
                            "siX",
                            *(_QWORD *)(v143 + 16),
                            v410,
                            v411,
                            v415,
                            v416,
                            v417,
                            v418);
                          sqlite3VdbeAddOp3(v11, 84, v426, 4, 0);
                          sqlite3VdbeResolveLabel(v11, (unsigned int)v432);
                          if ( v443 )
                            sqlite3DbFreeNN(v5);
                          v156 = *(_QWORD *)(v143 + 8);
                          ++v434;
                          v430 = v156;
                          v94 = v156 == 0;
                          v134 = v433;
                        }
                        while ( !v94 );
                        v16 = v440;
                      }
                      v157 = v437;
                      sqlite3VdbeAddOp3(v11, 39, 0, v437 + 1, 0);
                      sqlite3VdbeJumpHere(v11, v157);
                      v129 = v446;
                    }
                  }
                  goto LABEL_806;
                }
                v83 = v82 - 1;
                if ( !v83 )
                {
                  if ( !v16 )
                    goto LABEL_806;
                  v117 = sqlite3FindTable(v5, v16, v433);
                  v422 = v117;
                  if ( !v117 )
                    goto LABEL_806;
                  if ( *(_BYTE *)(v117 + 63) )
                    goto LABEL_806;
                  v118 = *(_QWORD *)(v117 + 72);
                  if ( !v118 )
                    goto LABEL_806;
                  v119 = *(_QWORD *)(v117 + 96);
                  v120 = -32768;
                  if ( v119 )
                  {
                    v121 = v5[4];
                    v120 = 0;
                    if ( *(_QWORD *)(v121 + 24) != v119 )
                    {
                      do
                        ++v120;
                      while ( *(_QWORD *)(32LL * v120 + v121 + 24) != v119 );
                    }
                  }
                  LODWORD(v432) = 0;
                  *((_DWORD *)v9 + 14) = 8;
                  sqlite3CodeVerifySchema(v9, (unsigned int)v120);
                  v122 = v432;
                  do
                  {
                    v123 = 0;
                    if ( *(int *)(v118 + 40) > 0 )
                    {
                      v124 = v432;
                      do
                      {
                        switch ( *(_BYTE *)(v118 + 45) )
                        {
                          case 7:
                            v125 = "RESTRICT";
                            break;
                          case 8:
                            v125 = "SET NULL";
                            break;
                          case 9:
                            v125 = "SET DEFAULT";
                            break;
                          case 0xA:
                            v125 = "CASCADE";
                            break;
                          default:
                            v125 = "NO ACTION";
                            break;
                        }
                        switch ( *(_BYTE *)(v118 + 46) )
                        {
                          case 7:
                            v126 = "RESTRICT";
                            break;
                          case 8:
                            v126 = "SET NULL";
                            break;
                          case 9:
                            v126 = "SET DEFAULT";
                            break;
                          case 0xA:
                            v126 = "CASCADE";
                            break;
                          default:
                            v126 = "NO ACTION";
                            break;
                        }
                        LODWORD(v408) = v123;
                        sqlite3VdbeMultiLoad(
                          v11,
                          1,
                          "iissssss",
                          v124,
                          v408,
                          *(_QWORD *)(v118 + 16),
                          *(_QWORD *)(*(_QWORD *)(v422 + 8) + 24LL * *(int *)(v118 + 16 * (v123 + 4LL))),
                          *(_QWORD *)(v118 + 16LL * v123 + 72),
                          (_DWORD)v126,
                          (_DWORD)v125);
                        ++v123;
                      }
                      while ( v123 < *(_DWORD *)(v118 + 40) );
                      v122 = v124;
                    }
                    v118 = *(_QWORD *)(v118 + 8);
                    LODWORD(v432) = ++v122;
                  }
                  while ( v118 );
                  goto LABEL_791;
                }
                v84 = v83 - 1;
                if ( !v84 )
                {
                  v113 = (*((_DWORD *)v5 + 11) >> 5) & 1;
                  *((_DWORD *)v9 + 14) = 6;
                  for ( m = 0; m != 23; ++m )
                  {
                    for ( n = qword_1400C8EF0[m]; n; n = *(_QWORD *)(n + 64) )
                      pragmaFunclistLine(v11, n, 1, v113);
                  }
                  v116 = (_QWORD *)v5[76];
                  v16 = v440;
                  while ( v116 )
                  {
                    pragmaFunclistLine(v11, v116[2], 0, v113);
                    v116 = (_QWORD *)*v116;
                  }
                  goto LABEL_806;
                }
                v85 = v84 - 1;
                if ( v85 )
                {
                  v86 = v85 - 1;
                  if ( !v86 )
                  {
                    String = 0;
                    if ( !v16 || !(unsigned int)sqlite3GetInt32(v16, &String) || (v109 = String, String <= 0) )
                      v109 = 0x7FFFFFFF;
                    sqlite3BeginWriteOperation(v9, 0, (unsigned int)v13);
                    sqlite3VdbeAddOp3(v11, 71, v109, 1, 0);
                    v110 = sqlite3VdbeAddOp3(v11, 62, v13, 0, 0);
                    sqlite3VdbeAddOp3(v11, 84, 1, 0, 0);
                    sqlite3VdbeAddOp3(v11, 86, 1, -1, 0);
                    sqlite3VdbeAddOp3(v11, 59, 1, v110, 0);
                    sqlite3VdbeJumpHere(v11, v110);
                    goto LABEL_806;
                  }
                  v87 = v86 - 1;
                  if ( v87 )
                  {
                    if ( v87 != 1 )
                      goto LABEL_677;
                    if ( !v16 )
                      goto LABEL_806;
                    v88 = sqlite3FindTable(v5, v16, v433);
                    if ( !v88 )
                      goto LABEL_806;
                    v89 = *(_QWORD *)(v88 + 96);
                    v90 = -32768;
                    if ( v89 )
                    {
                      v91 = v5[4];
                      v90 = 0;
                      if ( *(_QWORD *)(v91 + 24) != v89 )
                      {
                        do
                          ++v90;
                        while ( *(_QWORD *)(32LL * v90 + v91 + 24) != v89 );
                      }
                    }
                    *((_DWORD *)v9 + 14) = 5;
                    sqlite3CodeVerifySchema(v9, (unsigned int)v90);
                    v92 = *(_QWORD *)(v88 + 16);
                    v93 = 0;
                    if ( !v92 )
                      goto LABEL_806;
                    do
                    {
                      v94 = *(_QWORD *)(v92 + 72) == 0;
                      v449[0] = "c";
                      v449[1] = "u";
                      LODWORD(v416) = !v94;
                      v449[2] = "pk";
                      LODWORD(v411) = *(_BYTE *)(v92 + 98) != 0;
                      sqlite3VdbeMultiLoad(
                        v11,
                        1,
                        "isisi",
                        v93,
                        *(_QWORD *)v92,
                        v411,
                        v449[*(_DWORD *)(v92 + 100) & 3],
                        v416,
                        v417,
                        v418);
                      v92 = *(_QWORD *)(v92 + 40);
                      ++v93;
                    }
                    while ( v92 );
                    goto LABEL_791;
                  }
                  if ( !v16 )
                    goto LABEL_806;
                  v95 = v433;
                  Index = sqlite3FindIndex(v5, v16, v433);
                  v96 = Index;
                  if ( !Index )
                  {
                    v97 = sqlite3LocateTable(v9, 2, v16, v95);
                    if ( !v97 )
                      goto LABEL_806;
                    if ( *(char *)(v97 + 48) >= 0 )
                      goto LABEL_806;
                    v96 = *(_QWORD *)(v97 + 16);
                    Index = v96;
                    if ( !v96 )
                      goto LABEL_806;
                    do
                    {
                      if ( (*(_DWORD *)(v96 + 100) & 3) == 2 )
                        break;
                      v96 = *(_QWORD *)(v96 + 40);
                    }
                    while ( v96 );
                    Index = v96;
                    if ( !v96 )
                      goto LABEL_806;
                  }
                  v98 = *(_QWORD *)(v96 + 48);
                  v99 = -32768;
                  if ( v98 )
                  {
                    v100 = v5[4];
                    v99 = 0;
                    if ( *(_QWORD *)(v100 + 24) != v98 )
                    {
                      do
                        ++v99;
                      while ( *(_QWORD *)(32LL * v99 + v100 + 24) != v98 );
                    }
                  }
                  v101 = *(_QWORD *)(v425 + 16);
                  v102 = (unsigned __int16 *)(v96 + 96);
                  if ( !v101 )
                    v102 = (unsigned __int16 *)(v96 + 94);
                  v103 = *v102;
                  v420 = v103;
                  *((_DWORD *)v9 + 14) = v101 != 0 ? 6 : 3;
                  v422 = *(_QWORD *)(v96 + 24);
                  sqlite3CodeVerifySchema(v9, (unsigned int)v99);
                  v104 = 0;
                  if ( !v103 )
                    goto LABEL_806;
                  v105 = Index;
                  v106 = v425;
                  do
                  {
                    v107 = *(__int16 *)(*(_QWORD *)(v105 + 8) + 2LL * v104);
                    if ( (v107 & 0x8000u) == 0LL )
                      v108 = *(_QWORD *)(*(_QWORD *)(v422 + 8) + 24 * v107);
                    else
                      v108 = 0;
                    LODWORD(v408) = *(__int16 *)(*(_QWORD *)(v105 + 8) + 2LL * v104);
                    sqlite3VdbeMultiLoad(v11, 1, "iisX", v104, v408, v108, v415, v416, v417, v418);
                    if ( *(_QWORD *)(v106 + 16) )
                    {
                      LODWORD(v412) = v104 < *(unsigned __int16 *)(v105 + 94);
                      sqlite3VdbeMultiLoad(
                        v11,
                        4,
                        "isiX",
                        *(unsigned __int8 *)(*(_QWORD *)(v105 + 56) + v104),
                        *(_QWORD *)(*(_QWORD *)(v105 + 64) + 8LL * v104),
                        v412,
                        v415,
                        v416,
                        v417,
                        v418);
                    }
                    sqlite3VdbeAddOp3(v11, 84, 1, *((_DWORD *)v9 + 14), 0);
                    ++v104;
                  }
                  while ( (int)v104 < (int)v420 );
LABEL_790:
                  v5 = v444;
                  goto LABEL_791;
                }
                v423 = 0;
                if ( v16 )
                {
                  if ( !(unsigned int)sqlite3DecOrHexToI64(v16) )
                  {
                    v111 = sqlite3_hard_heap_limit64(-1);
                    if ( v423 > 0 && (!v111 || v111 > v423) )
                      sqlite3_hard_heap_limit64(v423);
                  }
                }
                v112 = sqlite3_hard_heap_limit64(-1);
LABEL_804:
                v28 = v112;
                goto LABEL_805;
              }
              if ( v16 )
              {
                if ( (*((_BYTE *)v5 + 44) & 0x40) == 0 )
                {
                  v159 = "UTF8";
                  if ( !"UTF8" )
                    goto LABEL_285;
                  v160 = &off_1400AAEB0;
                  while ( (unsigned int)sqlite3StrICmp(v16, v159) )
                  {
                    v160 += 2;
                    v159 = *v160;
                    if ( !*v160 )
                      goto LABEL_285;
                  }
                  if ( *((_BYTE *)v160 + 8) )
                    v162 = *((_BYTE *)v160 + 8);
                  LOBYTE(v161) = v162;
                  *(_BYTE *)(*(_QWORD *)(v5[4] + 24LL) + 113LL) = v162;
                  sqlite3SetTextEncoding(v5, v161);
                  if ( !*v160 )
LABEL_285:
                    sqlite3ErrorMsg(v9, "unsupported encoding: %s", v16);
                }
                goto LABEL_806;
              }
              if ( !(unsigned int)sqlite3ReadSchema(v9) )
              {
                v158 = (&off_1400AAEB0)[2 * *((unsigned __int8 *)*v9 + 100)];
LABEL_579:
                returnSingleText(v11, v158);
              }
LABEL_806:
              result = sqlite3DbFreeNN(v5);
              if ( v16 )
                return sqlite3DbFreeNN(v5);
              return result;
            }
            v448 = 0;
            LOBYTE(v431) = *((_BYTE *)qword_1400B2890 + *v447);
            v94 = *(_QWORD *)v430 == 0;
            v168 = 100;
            *((_DWORD *)v9 + 14) = 6;
            if ( v94 )
              LODWORD(v13) = -1;
            v426 = 100;
            v420 = v13;
            v438 = 100;
            if ( v16 )
            {
              if ( (unsigned int)sqlite3GetInt32(v16, &v438) )
              {
                v168 = v438;
                v426 = v438;
                if ( v438 > 0 )
                  goto LABEL_305;
                v168 = 100;
              }
              else
              {
                if ( (int)v13 < 0 )
                  v169 = 0;
                else
                  v169 = *(_QWORD *)(32LL * (int)v13 + v5[4]);
                v448 = sqlite3LocateTable(v9, 0, v16, v169);
                v168 = v438;
              }
              v426 = v168;
            }
LABEL_305:
            sqlite3VdbeAddOp3(v11, 71, v168 - 1, 1, 0);
            LODWORD(v170) = 0;
            v171 = 0;
            v439 = 0;
            if ( *((int *)v5 + 10) <= 0 )
              goto LABEL_495;
            while ( 1 )
            {
              if ( (int)v13 < 0 || v171 == (_DWORD)v13 )
              {
                v172 = v170;
                sqlite3CodeVerifySchema(v9, v171);
                v173 = v439;
                LODWORD(v170) = 0;
                *((_BYTE *)v9 + 35) = 0;
                v174 = 0;
                v175 = v5[4];
                v422 = 32 * v173;
                v423 = *(_QWORD *)(v175 + 32 * v173 + 24);
                v176 = *(_QWORD **)(v423 + 16);
                if ( v176 )
                {
                  do
                  {
                    v177 = v176[2];
                    if ( !v448 || v448 == v177 )
                    {
                      if ( *(char *)(v177 + 48) >= 0 )
                        ++v174;
                      v178 = *(_QWORD *)(v177 + 16);
                      v179 = 0;
                      while ( v178 )
                      {
                        v178 = *(_QWORD *)(v178 + 40);
                        ++v174;
                        ++v179;
                      }
                      if ( v179 > v172 )
                        v172 = v179;
                    }
                    v176 = (_QWORD *)*v176;
                  }
                  while ( v176 );
                  v11 = v443;
                  if ( v174 )
                  {
                    v180 = v174 + 1;
                    if ( !v448 )
                      v180 = v174;
                    v181 = (int *)sqlite3DbMallocRawNN(v5, 4LL * v180 + 4);
                    v182 = v181;
                    if ( v181 )
                    {
                      v183 = v448;
                      v184 = 0;
                      if ( v448 )
                      {
                        v184 = 1;
                        v181[1] = 0;
                      }
                      for ( ii = *(_QWORD **)(v423 + 16); ii; ii = (_QWORD *)*ii )
                      {
                        v186 = ii[2];
                        if ( !v183 || v183 == v186 )
                        {
                          if ( *(char *)(v186 + 48) >= 0 )
                          {
                            v187 = v184++;
                            v181[v187 + 1] = *(_DWORD *)(v186 + 40);
                          }
                          for ( jj = *(_QWORD *)(v186 + 16); jj; jj = *(_QWORD *)(jj + 40) )
                            v181[++v184] = *(_DWORD *)(jj + 88);
                        }
                      }
                      v189 = v172 + 8;
                      *v181 = v184;
                      if ( *((_DWORD *)v9 + 14) < v189 )
                        *((_DWORD *)v9 + 14) = v189;
                      *((_BYTE *)v9 + 31) = 0;
                      *((_DWORD *)v9 + 10) = 0;
                      v190 = sqlite3VdbeAddOp3(v11, 155, 2, v184, 1);
                      sqlite3VdbeChangeP4(v11, v190, v182, 4294967282LL);
                      v191 = *(int *)(v11 + 144);
                      if ( (int)v191 > 0 )
                        *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v191 - 22) = (unsigned __int8)v439;
                      v192 = sqlite3VdbeAddOp3(v11, 50, 2, 0, 0);
                      v193 = sqlite3MPrintf(v5, "*** in database %s ***\n", *(const char **)(v5[4] + v422));
                      v194 = sqlite3VdbeAddOp3(v11, 117, 0, 3, 0);
                      sqlite3VdbeChangeP4(v11, v194, v193, 4294967290LL);
                      sqlite3VdbeAddOp3(v11, 111, 2, 3, 3);
                      integrityCheckResultRow(v11);
                      sqlite3VdbeJumpHere(v11, v192);
                      v170 = 0;
                      v195 = *(_QWORD *)(v423 + 16);
                      while ( 2 )
                      {
                        v422 = v195;
                        if ( !v195 )
                        {
                          LODWORD(v13) = v420;
                          goto LABEL_492;
                        }
                        v196 = *(const char ***)(v195 + 16);
                        v433 = v196;
                        v421 = v170;
                        v435 = v170;
                        if ( *((_BYTE *)v196 + 63) == (_BYTE)v170 && (!v448 || (const char **)v448 == v196) )
                        {
                          if ( (_BYTE)v431 == 113 || *((char *)v196 + 48) >= 0 )
                          {
                            v425 = v170;
                            v438 = v170;
                          }
                          else
                          {
                            v197 = (__int64)v196[2];
                            v425 = v197;
                            if ( v197 )
                            {
                              do
                              {
                                if ( (*(_DWORD *)(v197 + 100) & 3) == 2 )
                                  break;
                                v197 = *(_QWORD *)(v197 + 40);
                              }
                              while ( v197 );
                              v425 = v197;
                            }
                            TempRange = sqlite3GetTempRange(v9, *(unsigned __int16 *)(v197 + 94));
                            v200 = *(unsigned __int16 *)(v199 + 94) - 1;
                            v438 = TempRange;
                            sqlite3VdbeAddOp3(v11, 75, 1, TempRange, TempRange + v200);
                            v170 = 0;
                          }
                          sqlite3OpenTableAndIndices(
                            (_DWORD)v9,
                            (_DWORD)v196,
                            112,
                            0,
                            1,
                            v170,
                            (__int64)&v421,
                            (__int64)&v435);
                          sqlite3VdbeAddOp3(v11, 71, 0, 7, 0);
                          if ( v196[2] )
                          {
                            v201 = 8;
                            v202 = v196[2];
                            do
                            {
                              sqlite3VdbeAddOp3(v11, 71, 0, v201, 0);
                              v202 = (const char *)*((_QWORD *)v202 + 5);
                              ++v201;
                            }
                            while ( v202 );
                            v5 = v444;
                            v9 = (_QWORD **)Index;
                            v196 = v433;
                          }
                          sqlite3VdbeAddOp3(v11, 36, v421, 0, 0);
                          v203 = sqlite3VdbeAddOp3(v11, 86, 7, 1, 0);
                          v94 = *((_BYTE *)v196 + 48) >= 0;
                          LODWORD(v424) = v203;
                          if ( v94 )
                          {
                            v204 = *((__int16 *)v196 + 27);
                            v205 = -1;
                            if ( v204 > 0 )
                            {
                              v206 = 0;
                              do
                              {
                                v207 = v205 + 1;
                                if ( (v196[1][24 * v206 + 18] & 0x20) != 0 )
                                  v207 = v205;
                                v206 = (unsigned int)(v206 + 1);
                                v205 = v207;
                              }
                              while ( (int)v206 < v204 );
                            }
                            v208 = v205 - 1;
                            if ( v205 != *((__int16 *)v196 + 26) )
                              v208 = v205;
                          }
                          else
                          {
                            for ( kk = v196[2];
                                  kk && (*((_DWORD *)kk + 25) & 3) != 2;
                                  kk = (const char *)*((_QWORD *)kk + 5) )
                            {
                              ;
                            }
                            v208 = *((unsigned __int16 *)kk + 48) - 1;
                          }
                          if ( v208 >= 0 )
                          {
                            sqlite3VdbeAddOp3(v11, 94, v421, v208, 3);
                            LastOp = sqlite3VdbeGetLastOp(v11);
                            if ( *(_DWORD *)(LastOp + 12) == 3 && *(_BYTE *)LastOp == 94 )
                              *(_WORD *)(LastOp + 2) |= 0x80u;
                          }
                          if ( (_BYTE)v431 == 113 || !v425 )
                          {
LABEL_380:
                            v215 = 0;
                          }
                          else
                          {
                            v211 = v438;
                            v212 = sqlite3VdbeAddOp4Int(v11, 41, v421, 0, v438, *(unsigned __int16 *)(v425 + 94));
                            sqlite3VdbeAddOp3(v11, 50, v211, 0, 0);
                            v213 = sqlite3MPrintf(v5, "row not in PRIMARY KEY order for %s", *v433);
                            v214 = sqlite3VdbeAddOp3(v11, 117, 0, 3, 0);
                            sqlite3VdbeChangeP4(v11, v214, v213, 4294967290LL);
                            integrityCheckResultRow(v11);
                            sqlite3VdbeJumpHere(v11, v212);
                            sqlite3VdbeJumpHere(v11, v212 + 1);
                            v215 = 0;
                            v216 = 0;
                            if ( *(_WORD *)(v425 + 94) )
                            {
                              v217 = v421;
                              v218 = v425;
                              v219 = v438;
                              do
                              {
                                sqlite3ExprCodeLoadIndexColumn((_DWORD)v9, v218, v217, v216, v219 + v216);
                                ++v216;
                              }
                              while ( v216 < *(unsigned __int16 *)(v218 + 94) );
                              v11 = v443;
                              v5 = v444;
                              v196 = v433;
                              goto LABEL_380;
                            }
                            v196 = v433;
                          }
                          v220 = 0;
                          v221 = (_DWORD)v196[6] & 0x10000;
                          IndexKey = 0;
                          String = v221;
                          if ( *((__int16 *)v196 + 27) > 0 )
                          {
                            while ( (_DWORD)v220 == *((__int16 *)v196 + 26) )
                            {
LABEL_438:
                              v253 = *((__int16 *)v196 + 27);
                              v220 = (unsigned int)(v220 + 1);
                              IndexKey = v220;
                              if ( (int)v220 >= v253 )
                                goto LABEL_439;
                            }
                            v222 = v196[1];
                            v441 = 3LL * (int)v220;
                            v223 = (char *)&v222[24 * (int)v220];
                            v446 = (const char **)v223;
                            v423 = (__int64)(v223 + 12);
                            if ( v221 )
                            {
                              v224 = (*((_DWORD *)v223 + 2) & 0xF0u) > 0x10;
                              v429 = v224;
                            }
                            else
                            {
                              v225 = v223[12] <= 65;
                              v423 = (__int64)(v223 + 12);
                              if ( v225 )
                              {
                                v224 = 0;
                                v429 = 0;
                              }
                              else
                              {
                                v224 = 1;
                                v429 = 1;
                              }
                            }
                            if ( (v223[8] & 0xF) != 0 || v224 )
                            {
                              v94 = (v223[18] & 0x20) == 0;
                              v434 = 5;
                              if ( v94 )
                              {
                                if ( *((_WORD *)v223 + 8) )
                                {
                                  v430 = 0;
                                  v228 = sqlite3ColumnExpr(v196, v223);
                                  if ( v228 )
                                  {
                                    LOBYTE(v230) = *v229;
                                    LOBYTE(v229) = *((_BYTE *)v5 + 100);
                                    valueFromExpr((_DWORD)v5, v228, (_DWORD)v229, v230, (__int64)&v430, v413);
                                    if ( v430 )
                                    {
                                      v434 = *((unsigned __int8 *)qword_1400B5170 + (*(_WORD *)(v430 + 20) & 0x3F));
                                      sqlite3ValueFree();
                                    }
                                  }
                                  v220 = IndexKey;
                                }
                                v94 = *((_BYTE *)v196 + 48) >= 0;
                                v442 = v421;
                                if ( v94 )
                                {
                                  v232 = sqlite3TableColumnToStorage(v196, v220);
                                  v226 = v442;
                                }
                                else
                                {
                                  for ( mm = v196[2];
                                        mm && (*((_DWORD *)mm + 25) & 3) != 2;
                                        mm = (const char *)*((_QWORD *)mm + 5) )
                                  {
                                    ;
                                  }
                                  v232 = sqlite3TableColumnToIndex(mm, v220);
                                }
                                v227 = v232;
                                v428 = v232;
                              }
                              else
                              {
                                sqlite3ExprCodeGetColumnOfTable(v11, (_DWORD)v196, v421, v220, 3);
                                v226 = -1;
                                v442 = -1;
                                v227 = 3;
                                v428 = 3;
                              }
                              v436 = *((_DWORD *)v9 + 17) - 1;
                              v233 = v436 - 1;
                              v234 = v446;
                              *((_DWORD *)v9 + 17) = v436 - 1;
                              LODWORD(v432) = v233;
                              if ( ((_BYTE)v234[1] & 0xF) != 0 )
                              {
                                v235 = sqlite3VdbeAddOp4Int(v11, 18, v226, v233, v227, v434);
                                v236 = v442;
                                v237 = *(int *)(v11 + 144);
                                LODWORD(v430) = v235;
                                if ( v442 >= 0 )
                                {
                                  if ( (int)v237 > 0 )
                                    *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v237 - 22) = 13;
                                  sqlite3VdbeAddOp3(v11, 94, v236, v428, 3);
                                  v235 = sqlite3VdbeAddOp3(v11, 51, 3, v432, 0);
                                }
                                else if ( (int)v237 > 0 )
                                {
                                  *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v237 - 22) = 15;
                                }
                                v238 = *v196;
                                v437 = v235;
                                v239 = sqlite3MPrintf(v5, "NULL value in %s.%s", v238, *v446);
                                v240 = sqlite3VdbeAddOp3(v11, 117, 0, 3, 0);
                                sqlite3VdbeChangeP4(v11, v240, v239, 4294967290LL);
                                v241 = v429;
                                if ( v429 )
                                {
                                  sqlite3VdbeAddOp3(v11, 9, 0, v436, 0);
                                  sqlite3VdbeJumpHere(v11, (unsigned int)v430);
                                  sqlite3VdbeJumpHere(v11, v437);
                                }
                                v233 = v432;
                              }
                              else
                              {
                                v241 = v429;
                              }
                              if ( String )
                              {
                                if ( v241 )
                                {
                                  sqlite3VdbeAddOp4Int(v11, 18, v442, v233, v428, v434);
                                  v242 = *(int *)(v11 + 144);
                                  if ( (int)v242 > 0 )
                                    *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v242 - 22) = *((unsigned __int8 *)&qword_1400B13B0[1]
                                                                                          + ((*((_DWORD *)v446 + 2) >> 4)
                                                                                           & 0xFu)
                                                                                          + 3);
                                  v243 = sqlite3MPrintf(
                                           v5,
                                           "non-%s value in %s.%s",
                                           off_1400C8180[((*((_DWORD *)v446 + 2) >> 4) & 0xFu) - 1],
                                           *v433,
                                           *(const char **)&v433[1][8 * v441]);
                                  goto LABEL_435;
                                }
                              }
                              else
                              {
                                if ( *(_BYTE *)v423 == 66 )
                                {
                                  sqlite3VdbeAddOp4Int(v11, 18, v442, v233, v428, v434);
                                  v244 = *(int *)(v11 + 144);
                                  if ( (int)v244 > 0 )
                                    *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v244 - 22) = 28;
                                  v243 = sqlite3MPrintf(
                                           v5,
                                           "NUMERIC value in %s.%s",
                                           *v433,
                                           *(_QWORD *)&v433[1][8 * v441]);
                                }
                                else
                                {
                                  if ( *(char *)v423 < 67 )
                                    goto LABEL_436;
                                  v245 = v442;
                                  sqlite3VdbeAddOp4Int(v11, 18, v442, v233, v428, v434);
                                  v246 = *(int *)(v11 + 144);
                                  if ( (int)v246 > 0 )
                                    *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v246 - 22) = 27;
                                  v247 = v245 < 0;
                                  v248 = v433;
                                  if ( !v247 )
                                    sqlite3ExprCodeGetColumnOfTable(v11, (_DWORD)v433, v421, IndexKey, 3);
                                  v249 = sqlite3VdbeAddOp3(v11, 96, 3, 1, 0);
                                  sqlite3VdbeChangeP4(v11, v249, "C", 0xFFFFFFFFLL);
                                  sqlite3VdbeAddOp4Int(v11, 18, -1, v432, 3, v434);
                                  v250 = *(int *)(v11 + 144);
                                  if ( (int)v250 > 0 )
                                    *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v250 - 22) = 28;
                                  v243 = sqlite3MPrintf(
                                           v5,
                                           "TEXT value in %s.%s",
                                           *v248,
                                           *(_QWORD *)&v248[1][24 * IndexKey]);
                                }
LABEL_435:
                                v251 = v243;
                                v252 = sqlite3VdbeAddOp3(v11, 117, 0, 3, 0);
                                sqlite3VdbeChangeP4(v11, v252, v251, 4294967290LL);
                              }
LABEL_436:
                              sqlite3VdbeResolveLabel(v11, v436);
                              integrityCheckResultRow(v11);
                              sqlite3VdbeResolveLabel(v11, (unsigned int)v432);
                              LODWORD(v220) = IndexKey;
                              v215 = 0;
                              v196 = v433;
                            }
                            v221 = String;
                            goto LABEL_438;
                          }
LABEL_439:
                          v254 = v196[4];
                          if ( v254 && (v5[6] & 0x200LL) == 0 )
                          {
                            v255 = sqlite3ExprListDup(v5, v254, 0);
                            v215 = 0;
                            v423 = v255;
                            v256 = v255;
                            if ( !*((_BYTE *)v5 + 103) )
                            {
                              v436 = *((_DWORD *)v9 + 17) - 1;
                              v257 = v436 - 1;
                              *((_DWORD *)v9 + 17) = v436 - 1;
                              v437 = v257;
                              *((_DWORD *)v9 + 16) = v421 + 1;
                              v258 = *(_DWORD *)v256 - 1;
                              if ( v258 > 0 )
                              {
                                v259 = v436;
                                v260 = v256;
                                do
                                  sqlite3ExprIfFalse(v9, *(_QWORD *)(32LL * (unsigned int)v258-- + v260 + 8), v259, 0);
                                while ( v258 > 0 );
                                v11 = v443;
                                v5 = v444;
                                v196 = v433;
                                v256 = v423;
                              }
                              sqlite3ExprIfTrue(v9, *(_QWORD *)(v256 + 8), v437, 16);
                              sqlite3VdbeResolveLabel(v11, v436);
                              *((_DWORD *)v9 + 16) = 0;
                              v261 = sqlite3MPrintf(v5, "CHECK constraint failed in %s", *v196);
                              v262 = sqlite3VdbeAddOp3(v11, 117, 0, 3, 0);
                              sqlite3VdbeChangeP4(v11, v262, v261, 4294967290LL);
                              integrityCheckResultRow(v11);
                              sqlite3VdbeResolveLabel(v11, v437);
                              v256 = v423;
                              v215 = 0;
                            }
                            if ( v256 )
                            {
                              exprListDeleteNN(v5, v256);
                              v215 = 0;
                            }
                          }
                          if ( (_BYTE)v431 != 113 )
                          {
                            v263 = (__int64)v196[2];
                            v264 = 0;
                            v428 = 0;
                            v265 = -1;
                            v432 = v263;
                            if ( v263 )
                            {
                              v266 = v433;
                              do
                              {
                                v267 = *((_DWORD *)v9 + 17) - 1;
                                v436 = v215;
                                *((_DWORD *)v9 + 17) = v267;
                                if ( v425 != v263 )
                                {
                                  IndexKey = sqlite3GenerateIndexKey(
                                               (_DWORD)v9,
                                               v263,
                                               v421,
                                               0,
                                               v215,
                                               (__int64)&v436,
                                               v264,
                                               v265);
                                  v441 = v263;
                                  sqlite3VdbeAddOp3(v11, 86, v428 + 8, 1, 0);
                                  v414 = *(unsigned __int16 *)(v263 + 96);
                                  LODWORD(v430) = v435 + v428;
                                  v268 = sqlite3VdbeAddOp4Int(v11, 29, v435 + v428, v267, IndexKey, v414);
                                  sqlite3VdbeLoadString(v11, 3, "row ");
                                  sqlite3VdbeAddOp3(v11, 111, 7, 3, 3);
                                  sqlite3VdbeLoadString(v11, 4, " missing from index ");
                                  sqlite3VdbeAddOp3(v11, 111, 4, 3, 3);
                                  String = sqlite3VdbeLoadString(v11, 4, *(_QWORD *)v432);
                                  sqlite3VdbeAddOp3(v11, 111, 4, 3, 3);
                                  v437 = integrityCheckResultRow(v11);
                                  sqlite3VdbeJumpHere(v11, v268);
                                  if ( *((char *)v266 + 48) >= 0 )
                                  {
                                    sqlite3VdbeAddOp3(v11, 142, v430, 3, 0);
                                    v269 = sqlite3VdbeAddOp3(
                                             v11,
                                             53,
                                             3,
                                             0,
                                             *(unsigned __int16 *)(v432 + 96) + IndexKey - 1);
                                    sqlite3VdbeLoadString(v11, 3, "rowid not at end-of-record for row ");
                                    sqlite3VdbeAddOp3(v11, 111, 7, 3, 3);
                                    sqlite3VdbeLoadString(v11, 4, " of index ");
                                    sqlite3VdbeAddOp3(v11, 9, 0, String - 1, 0);
                                    sqlite3VdbeJumpHere(v11, v269);
                                  }
                                  v263 = v432;
                                  v270 = 0;
                                  v429 = 0;
                                  if ( *(_WORD *)(v432 + 94) )
                                  {
                                    v271 = 0;
                                    do
                                    {
                                      if ( *(char **)(*(_QWORD *)(v263 + 64) + 8LL * v271) != "BINARY" )
                                      {
                                        if ( !v270 )
                                        {
                                          v429 = *((_DWORD *)v9 + 17) - 1;
                                          *((_DWORD *)v9 + 17) = v429;
                                        }
                                        sqlite3VdbeAddOp3(v11, 94, v428 + v435, v271, 3);
                                        sqlite3VdbeAddOp3(v11, 52, 3, v429, v271 + IndexKey);
                                        v270 = v429;
                                      }
                                      ++v271;
                                    }
                                    while ( v271 < *(unsigned __int16 *)(v263 + 94) );
                                    v266 = v433;
                                    if ( v270 )
                                    {
                                      v272 = sqlite3VdbeAddOp3(v11, 9, 0, 0, 0);
                                      sqlite3VdbeResolveLabel(v11, v429);
                                      sqlite3VdbeLoadString(v11, 3, "row ");
                                      sqlite3VdbeAddOp3(v11, 111, 7, 3, 3);
                                      sqlite3VdbeLoadString(v11, 4, " values differ from index ");
                                      sqlite3VdbeAddOp3(v11, 9, 0, String - 1, 0);
                                      sqlite3VdbeJumpHere(v11, v272);
                                      v263 = v432;
                                    }
                                  }
                                  if ( *(_BYTE *)(v263 + 98) )
                                  {
                                    v273 = *((_DWORD *)v9 + 17) - 1;
                                    *((_DWORD *)v9 + 17) = v273;
                                    v429 = v273;
                                    if ( *(_WORD *)(v263 + 94) )
                                    {
                                      v274 = 0;
                                      do
                                      {
                                        v275 = *(_QWORD *)(v263 + 8);
                                        if ( *(__int16 *)(v275 + 2LL * v274) < 0
                                          || (v266[1][24 * *(__int16 *)(v275 + 2LL * v274) + 8] & 0xF) == 0 )
                                        {
                                          sqlite3VdbeAddOp3(v11, 50, v274 + IndexKey, v273, 0);
                                          v273 = v429;
                                        }
                                        ++v274;
                                      }
                                      while ( v274 < *(unsigned __int16 *)(v263 + 94) );
                                      v9 = (_QWORD **)Index;
                                    }
                                    v276 = sqlite3VdbeAddOp3(v11, 39, v428 + v435, 0, 0);
                                    sqlite3VdbeAddOp3(v11, 9, 0, v429, 0);
                                    sqlite3VdbeJumpHere(v11, v276);
                                    v263 = v432;
                                    sqlite3VdbeAddOp4Int(
                                      v11,
                                      41,
                                      v428 + v435,
                                      v429,
                                      IndexKey,
                                      *(unsigned __int16 *)(v432 + 94));
                                    sqlite3VdbeLoadString(v11, 3, "non-unique entry in index ");
                                    sqlite3VdbeAddOp3(v11, 9, 0, String, 0);
                                    sqlite3VdbeResolveLabel(v11, v429);
                                  }
                                  sqlite3VdbeJumpHere(v11, v437);
                                  if ( v436 )
                                  {
                                    sqlite3VdbeResolveLabel(v9[2], v436);
                                    v215 = 0;
                                  }
                                  v264 = v441;
                                  v265 = IndexKey;
                                }
                                v263 = *(_QWORD *)(v263 + 40);
                                ++v428;
                                v432 = v263;
                              }
                              while ( v263 );
                              v5 = v444;
                              v196 = v433;
                            }
                          }
                          v277 = v424;
                          sqlite3VdbeAddOp3(v11, 39, v421, v424, v215);
                          sqlite3VdbeJumpHere(v11, (unsigned int)(v277 - 1));
                          if ( (_BYTE)v431 == 113 )
                          {
                            v170 = 0;
                          }
                          else
                          {
                            sqlite3VdbeLoadString(v11, 2, "wrong # of entries in index ");
                            v278 = v196[2];
                            v170 = 0;
                            if ( v278 )
                            {
                              v279 = v435;
                              v280 = 0;
                              v281 = (const char *)v425;
                              do
                              {
                                if ( v281 != v278 )
                                {
                                  sqlite3VdbeAddOp3(v11, 98, v280 + v279, 3, 0);
                                  v282 = sqlite3VdbeAddOp3(v11, 53, v280 + 8, 0, 3);
                                  v283 = *(int *)(v11 + 144);
                                  v284 = v282;
                                  if ( (int)v283 > 0 )
                                    *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v283 - 22) = 144;
                                  sqlite3VdbeLoadString(v11, 4, *(_QWORD *)v278);
                                  sqlite3VdbeAddOp3(v11, 111, 4, 2, 3);
                                  integrityCheckResultRow(v11);
                                  sqlite3VdbeJumpHere(v11, v284);
                                  v281 = (const char *)v425;
                                  v170 = 0;
                                }
                                v278 = (const char *)*((_QWORD *)v278 + 5);
                                ++v280;
                              }
                              while ( v278 );
                              v5 = v444;
                              v9 = (_QWORD **)Index;
                            }
                            if ( v425 )
                              sqlite3ReleaseTempRange(v9, (unsigned int)v438, *(unsigned __int16 *)(v425 + 94));
                          }
                        }
                        v195 = *(_QWORD *)v422;
                        continue;
                      }
                    }
LABEL_494:
                    v16 = v440;
LABEL_495:
                    v285 = sqlite3VdbeAddOpList(v11, 7, qword_1400B5150);
                    v286 = 0;
                    if ( v285 )
                    {
                      *(_DWORD *)(v285 + 8) = 1 - v426;
                      *(_BYTE *)(v285 + 49) = -1;
                      *(_QWORD *)(v285 + 64) = "ok";
                      *(_BYTE *)(v285 + 121) = -1;
                      v287 = sqlite3ErrStr(11);
                      *(_QWORD *)(v288 + 136) = v287;
                    }
                    v289 = qword_1400C8EC0;
                    if ( *(_BYTE *)(*(_QWORD *)v11 + 103LL) == v286 )
                      v289 = *(__int64 **)(v11 + 136);
                    *((_DWORD *)v289 + 3) = *(_DWORD *)(v11 + 144) - 2;
                    goto LABEL_806;
                  }
                }
LABEL_492:
                v171 = v439;
              }
              v439 = ++v171;
              if ( (signed int)v171 >= *((_DWORD *)v5 + 10) )
                goto LABEL_494;
            }
          }
          if ( (unsigned __int8)v23 > 0x22u )
          {
            v351 = v23 - 35;
            if ( !v351 )
            {
              v422 = 0;
              if ( v16 && !(unsigned int)sqlite3DecOrHexToI64(v16) )
                sqlite3_soft_heap_limit64(v422);
              v112 = sqlite3_soft_heap_limit64(-1);
              goto LABEL_804;
            }
            v352 = v351 - 1;
            if ( !v352 )
            {
              if ( !v16 )
              {
                v28 = *(unsigned __int8 *)(v14 + v424 + 16) - 1LL;
                goto LABEL_805;
              }
              if ( !*((_BYTE *)v5 + 101) )
              {
                sqlite3ErrorMsg(v9, "Safety level may not be changed inside a transaction");
                goto LABEL_806;
              }
              if ( (_DWORD)v13 != 1 )
              {
                LOBYTE(v21) = 1;
                v405 = getSafetyLevel(v16, 0, v21);
                v406 = v424;
                v407 = (v405 + 1) & 7;
                if ( !v407 )
                  LOBYTE(v407) = 1;
                *(_BYTE *)(v14 + v424 + 16) = v407;
                *(_BYTE *)(v14 + v406 + 17) = 1;
                goto LABEL_92;
              }
              goto LABEL_806;
            }
            v353 = v352 - 1;
            if ( !v353 )
            {
              if ( !v16 )
                goto LABEL_806;
              sqlite3CodeVerifyNamedSchema(v9, v433);
              v386 = sqlite3LocateTable(v9, 2, v16, v433);
              v387 = v386;
              if ( !v386 )
                goto LABEL_806;
              v388 = *(_QWORD *)(v386 + 16);
              v423 = v388;
              if ( v388 )
              {
                do
                {
                  if ( (*(_DWORD *)(v388 + 100) & 3) == 2 )
                    break;
                  v388 = *(_QWORD *)(v388 + 40);
                }
                while ( v388 );
                v423 = v388;
              }
              *((_DWORD *)v9 + 14) = 7;
              if ( *(_BYTE *)(v386 + 63) == 1 || *(__int16 *)(v386 + 54) <= 0 )
              {
                viewGetColumnNames(v9, v386);
                v388 = v423;
              }
              LOWORD(v389) = *(_WORD *)(v387 + 54);
              if ( (__int16)v389 <= 0 )
                goto LABEL_806;
              v390 = *(_QWORD *)(v387 + 8);
              v391 = 0;
              v392 = v425;
              v393 = 0;
              String = 0;
              v420 = 0;
              do
              {
                v394 = *(_WORD *)(v390 + 18);
                if ( (v394 & 0x62) == 0 || *(_QWORD *)(v392 + 16) )
                {
                  if ( (v394 & 1) != 0 )
                  {
                    v395 = 1;
                    if ( v388 && (__int16)v389 >= 1 )
                    {
                      do
                      {
                        if ( *(__int16 *)(*(_QWORD *)(v388 + 8) + 2LL * v395 - 2) == v393 )
                          break;
                        ++v395;
                      }
                      while ( v395 <= (__int16)v389 );
                    }
                  }
                  else
                  {
                    v395 = 0;
                  }
                  v396 = sqlite3ColumnExpr(v387, v390);
                  if ( v398 < 2 && v396 )
                    v422 = *(_QWORD *)(v396 + 8);
                  else
                    v422 = v397;
                  v399 = sqlite3ColumnType(v390, &dword_1400ACDEC);
                  v403 = (unsigned int)(v402 - String);
                  v404 = "issisii";
                  if ( !*(_QWORD *)(v392 + 16) )
                    v404 = "issisi";
                  sqlite3VdbeMultiLoad(v11, 1, v404, v403, *(_QWORD *)v390, v399, v400, v422, v395, v401);
                  v393 = v420;
                  v391 = String;
                }
                else
                {
                  String = ++v391;
                }
                v389 = *(__int16 *)(v387 + 54);
                ++v393;
                v388 = v423;
                v390 += 24;
                v420 = v393;
              }
              while ( v393 < v389 );
              goto LABEL_790;
            }
            v354 = v353 - 1;
            if ( !v354 )
            {
              v368 = v433;
              v369 = v433;
              *((_DWORD *)v9 + 14) = 6;
              sqlite3CodeVerifyNamedSchema(v9, v369);
              for ( nn = 0; nn < *((_DWORD *)v5 + 10); ++nn )
              {
                v371 = nn;
                if ( v368 )
                {
                  v372 = *(_QWORD *)(32LL * nn + v5[4]);
                  if ( !v372 || (unsigned int)sqlite3StrICmp(v368, v372) )
                    continue;
                }
                v373 = *(_QWORD *)(32 * v371 + v5[4] + 24) + 8LL;
                v374 = *(_DWORD *)(*(_QWORD *)(32 * v371 + v5[4] + 24) + 12LL);
LABEL_740:
                if ( v374 )
                {
                  for ( i1 = *(_QWORD **)(v373 + 8); i1; i1 = (_QWORD *)*i1 )
                  {
                    v376 = i1[2];
                    if ( !*(_WORD *)(v376 + 54) )
                    {
                      --v374;
                      v377 = sqlite3MPrintf(v5, "SELECT*FROM\"%w\"", *(_QWORD *)v376);
                      v441 = v377;
                      if ( v377 )
                      {
                        v422 = 0;
                        sqlite3LockAndPrepare((_DWORD)v5, v377, -1, 0, 0, (__int64)&v422, 0);
                        sqlite3_finalize(v422);
                        sqlite3DbFreeNN(v5);
                      }
                      if ( *((_BYTE *)v5 + 103) )
                      {
                        sqlite3ErrorMsg(v5[44], "out of memory", v378, 0);
                        *(_DWORD *)(v5[44] + 24LL) = 7;
                      }
                      v373 = *(_QWORD *)(32LL * nn + v5[4] + 24) + 8LL;
                      goto LABEL_740;
                    }
                  }
                }
                v379 = *(_QWORD **)(v373 + 8);
                v422 = (__int64)v379;
                if ( v379 )
                {
                  do
                  {
                    v380 = (_QWORD *)v379[2];
                    if ( !v16 || *v380 && !(unsigned int)sqlite3StrICmp(v16, *v380) )
                    {
                      if ( *((_BYTE *)v380 + 63) == 2 )
                      {
                        v381 = "view";
                      }
                      else if ( *((_BYTE *)v380 + 63) == 1 )
                      {
                        v381 = "virtual";
                      }
                      else
                      {
                        v381 = "shadow";
                        if ( (v380[6] & 0x1000) == 0 )
                          v381 = "table";
                      }
                      v423 = (__int64)v381;
                      v382 = *((_DWORD *)v380 + 12);
                      LODWORD(v430) = (v382 >> 7) & 1;
                      v383 = (const char *)*v380;
                      LODWORD(v424) = HIWORD(v382) & 1;
                      v441 = (__int64)v383;
                      if ( (unsigned int)sqlite3_strnicmp(v383, "sqlite_", 7) )
                      {
                        v385 = (const char *)*v380;
                      }
                      else if ( (unsigned int)sqlite3StrICmp(v441 + 7, "master") )
                      {
                        if ( !(unsigned int)sqlite3StrICmp(v384 + 7, "temp_master") )
                          v385 = "sqlite_temp_schema";
                      }
                      else
                      {
                        v385 = "sqlite_schema";
                      }
                      LODWORD(v416) = v430;
                      sqlite3VdbeMultiLoad(
                        v11,
                        1,
                        "sssiii",
                        *(_QWORD *)(32LL * nn + v5[4]),
                        v385,
                        v423,
                        *((__int16 *)v380 + 27),
                        v416,
                        v424,
                        v418);
                      v379 = (_QWORD *)v422;
                    }
                    v379 = (_QWORD *)*v379;
                    v422 = (__int64)v379;
                  }
                  while ( v379 );
                  v368 = v433;
                }
              }
              goto LABEL_806;
            }
            v355 = v354 - 1;
            if ( !v355 )
            {
              if ( v16 )
              {
                if ( (unsigned __int8)(*v16 - 48) > 2u )
                {
                  if ( (unsigned int)sqlite3StrICmp(v16, "file") )
                  {
                    v365 = sqlite3StrICmp(v16, "memory");
                    v12 = v365 == 0 ? v366 : 0;
                  }
                }
                else
                {
                  v12 = *v16 - 48;
                }
                v367 = (unsigned __int8 *)*v9;
                if ( *((unsigned __int8 *)*v9 + 102) != v12 && !(unsigned int)invalidateTempStorage(v9) )
                  v367[102] = v12;
                goto LABEL_806;
              }
              v28 = *((unsigned __int8 *)v5 + 102);
              goto LABEL_805;
            }
            v356 = v355 - 1;
            if ( !v356 )
            {
              if ( (_BYTE)word_1400C84B4 )
              {
                v363 = ((__int64 (__fastcall *)(__int64))xmmword_1400C8520)(11);
                if ( v363 )
                  ((void (__fastcall *)(__int64))xmmword_1400C8530)(v363);
              }
              if ( !v16 )
              {
                v63 = sqlite3_temp_directory;
                goto LABEL_102;
              }
              if ( !*v16
                || (v420 = 0,
                    !(*(unsigned int (__fastcall **)(_QWORD, char *, __int64, unsigned int *))(*v5 + 56LL))(
                       *v5,
                       v16,
                       1,
                       &v420))
                && v420 )
              {
                if ( *((_BYTE *)v5 + 102) <= 1u )
                  invalidateTempStorage(v9);
                sqlite3_free(sqlite3_temp_directory);
                if ( *v16 )
                  sqlite3_temp_directory = sqlite3_mprintf("%s", v16);
                else
                  sqlite3_temp_directory = 0;
                goto LABEL_708;
              }
LABEL_707:
              sqlite3ErrorMsg(v9, "not a writable directory");
              goto LABEL_708;
            }
            v357 = v356 - 1;
            if ( !v357 )
            {
              v422 = 0;
              if ( v16 && !(unsigned int)sqlite3DecOrHexToI64(v16) )
                sqlite3_limit(v5, 11, v422 & 0x7FFFFFFF);
              AutoVacuum = sqlite3_limit(v5, 11, 0xFFFFFFFFLL);
              goto LABEL_55;
            }
            v358 = v357 - 1;
            if ( !v358 )
            {
              if ( v16 )
              {
                v420 = 0;
                sqlite3GetInt32(v16, &v420);
                sqlite3_wal_autocheckpoint(v5, v420);
              }
              if ( (__int64 (__fastcall *)())v5[45] == sqlite3WalDefaultHook )
                AutoVacuum = *((_DWORD *)v5 + 92);
              else
                AutoVacuum = 0;
              goto LABEL_55;
            }
            if ( v358 != 1 )
              goto LABEL_677;
            v359 = 12;
            if ( *(_QWORD *)v430 )
              v359 = v13;
            v360 = 0;
            LODWORD(v424) = v359;
            if ( v16 )
            {
              if ( (unsigned int)sqlite3StrICmp(v16, "full") )
              {
                if ( (unsigned int)sqlite3StrICmp(v16, "restart") )
                {
                  if ( !(unsigned int)sqlite3StrICmp(v16, "truncate") )
                    v360 = 3;
                }
                else
                {
                  v360 = v361;
                }
              }
              else
              {
                v360 = 1;
              }
            }
            v362 = v424;
            *((_DWORD *)v9 + 14) = 3;
            sqlite3VdbeAddOp3(v11, 3, v362, v360, 1);
            v304 = 3;
            goto LABEL_609;
          }
          if ( (_BYTE)v23 == 34 )
          {
            sqlite3_db_release_memory(v5);
            goto LABEL_806;
          }
          if ( (unsigned __int8)v23 <= 0x1Du )
          {
            if ( (_BYTE)v23 == 29 )
            {
              *((_DWORD *)v9 + 14) = 1;
              for ( i2 = (_QWORD *)v5[70]; i2; i2 = (_QWORD *)*i2 )
                sqlite3VdbeMultiLoad(v11, 1, "s", *(_QWORD *)(i2[2] + 8LL), v408, v411, v415, v416, v417, v418);
              goto LABEL_806;
            }
            v290 = v23 - 23;
            if ( v290 )
            {
              v291 = v290 - 1;
              if ( !v291 )
              {
                v317 = *(__int64 **)(*(_QWORD *)(v14 + v424 + 8) + 8LL);
                v318 = -2;
                v422 = -2;
                v319 = *v317;
                if ( v16 )
                {
                  sqlite3DecOrHexToI64(v16);
                  v318 = -1;
                }
                if ( v318 >= -1 )
                {
                  v320 = *(_QWORD *)(v319 + 296);
                  *(_QWORD *)(v319 + 208) = v318;
                  if ( v320 )
                    *(_QWORD *)(v320 + 32) = v318;
                }
                v28 = *(_QWORD *)(v319 + 208);
                goto LABEL_805;
              }
              v292 = v291 - 2;
              if ( v292 )
              {
                v293 = v292 - 1;
                if ( v293 )
                {
                  if ( v293 != 1 )
                    goto LABEL_677;
                  v425 = 0;
                  if ( !v16 )
                    goto LABEL_539;
                  sqlite3DecOrHexToI64(v16);
                  if ( v425 < 0 )
                    v425 = qword_1400C85D8;
                  v294 = v430;
                  if ( *(_DWORD *)(v430 + 8) )
                  {
                    if ( *((_DWORD *)v5 + 10) - 1 >= 0 )
                    {
                      v298 = *((_DWORD *)v5 + 10) - 1;
                      do
                      {
                        v299 = *(_QWORD *)(32LL * (unsigned int)v298 + v5[4] + 8);
                        v423 = v299;
                        if ( v299 && v298 == (_DWORD)v13 )
                        {
                          v441 = v425;
                          v300 = *(_QWORD *)(v299 + 8);
                          v422 = v300;
                          if ( *(_BYTE *)(v299 + 17) )
                          {
                            ++*(_DWORD *)(v299 + 20);
                            if ( !*(_BYTE *)(v299 + 18) )
                            {
                              btreeLockCarefully(v299);
                              v300 = v422;
                            }
                          }
                          *(_QWORD *)(*(_QWORD *)v300 + 160LL) = v441;
                          pagerFixMaplimit();
                          if ( *(_BYTE *)(v423 + 17) )
                          {
                            v94 = (*(_DWORD *)(v423 + 20))-- == 1;
                            if ( v94 )
                              unlockBtreeMutex();
                          }
                        }
                        --v298;
                      }
                      while ( v298 >= 0 );
                      goto LABEL_538;
                    }
                  }
                  else
                  {
                    v5[8] = v425;
                    if ( *((_DWORD *)v5 + 10) - 1 >= 0 )
                    {
                      v295 = *((_DWORD *)v5 + 10) - 1;
                      do
                      {
                        v296 = *(_QWORD *)(32LL * (unsigned int)v295 + v5[4] + 8);
                        v423 = v296;
                        if ( v296 && (v295 == (_DWORD)v13 || !*(_DWORD *)(v294 + 8)) )
                        {
                          v441 = v425;
                          v297 = *(_QWORD *)(v296 + 8);
                          v422 = v297;
                          if ( *(_BYTE *)(v296 + 17) )
                          {
                            ++*(_DWORD *)(v296 + 20);
                            if ( !*(_BYTE *)(v296 + 18) )
                            {
                              btreeLockCarefully(v296);
                              v297 = v422;
                            }
                          }
                          *(_QWORD *)(*(_QWORD *)v297 + 160LL) = v441;
                          pagerFixMaplimit();
                          if ( *(_BYTE *)(v423 + 17) )
                          {
                            v94 = (*(_DWORD *)(v423 + 20))-- == 1;
                            if ( v94 )
                              unlockBtreeMutex();
                          }
                          v294 = v430;
                        }
                        --v295;
                      }
                      while ( v295 >= 0 );
LABEL_538:
                      v16 = v440;
                    }
                  }
LABEL_539:
                  v425 = -1;
                  v19 = sqlite3_file_control(v5, v433, 18, &v425);
                  if ( !v19 )
                  {
                    v28 = v425;
                    goto LABEL_805;
                  }
                  if ( v19 != 12 )
                  {
LABEL_18:
                    ++*((_DWORD *)v9 + 12);
                    *((_DWORD *)v9 + 6) = v19;
                    goto LABEL_806;
                  }
                  goto LABEL_806;
                }
                v422 = 0;
                sqlite3CodeVerifySchema(v9, (unsigned int)v13);
                v301 = v447;
                v302 = *((_DWORD *)v9 + 14) + 1;
                *((_DWORD *)v9 + 14) = v302;
                if ( *((_BYTE *)qword_1400B2890 + *v301) == 112 )
                {
                  sqlite3VdbeAddOp3(v11, 177, v13, v302, 0);
                }
                else
                {
                  if ( !v16 || (unsigned int)sqlite3DecOrHexToI64(v16) || (v303 = v422, v422 < 0) )
                  {
                    v303 = 0;
                  }
                  else if ( v422 > 4294967294LL )
                  {
                    v303 = -2;
                  }
                  sqlite3VdbeAddOp3(v11, 178, v13, v302, v303);
                }
                v304 = 1;
                v305 = v302;
LABEL_553:
                sqlite3VdbeAddOp3(v11, 84, v305, v304, 0);
                goto LABEL_806;
              }
              v306 = -1;
              v307 = "exclusive";
              if ( !v16 )
                goto LABEL_558;
              if ( !(unsigned int)sqlite3StrICmp(v16, "exclusive") )
              {
                v308 = 1;
                goto LABEL_559;
              }
              v309 = sqlite3StrICmp(v16, "normal");
              v308 = 0;
              if ( v309 )
LABEL_558:
                v308 = v306;
LABEL_559:
              if ( !*(_DWORD *)(v430 + 8) )
              {
                if ( v308 == v306 )
                {
                  v310 = *((_BYTE *)v5 + 105);
LABEL_576:
                  if ( v310 != 1 )
                    v307 = "normal";
                  v158 = (char *)v307;
                  goto LABEL_579;
                }
                if ( v308 >= 0 )
                {
                  for ( i3 = 2; i3 < *((_DWORD *)v5 + 10); ++i3 )
                  {
                    v312 = *(__int64 **)(*(_QWORD *)(32LL * i3 + v5[4] + 8) + 8LL);
                    v313 = *v312;
                    if ( !*(_BYTE *)(*v312 + 16) )
                    {
                      v314 = *(_QWORD *)(v313 + 296);
                      if ( !v314 || *(_BYTE *)(v314 + 63) != 2 )
                        *(_BYTE *)(v313 + 8) = v308;
                    }
                  }
                }
                *((_BYTE *)v5 + 105) = v308;
              }
              v315 = **(_QWORD **)(*(_QWORD *)(v14 + v424 + 8) + 8LL);
              if ( v308 >= 0 && !*(_BYTE *)(v315 + 16) )
              {
                v316 = *(_QWORD *)(v315 + 296);
                if ( !v316 || *(_BYTE *)(v316 + 63) != 2 )
                  *(_BYTE *)(v315 + 8) = v308;
              }
              v310 = *(_BYTE *)(v315 + 8);
              goto LABEL_576;
            }
            if ( v16 )
            {
              v322 = -1;
              do
                ++v322;
              while ( v16[v322] );
              v323 = v322 & 0x3FFFFFFF;
              v321 = 0;
              v422 = v323;
              while ( 1 )
              {
                if ( v321 == 6 )
                  goto LABEL_597;
                v324 = off_1400AA2D8[v321];
                if ( !v324 )
                  goto LABEL_597;
                if ( !(unsigned int)sqlite3_strnicmp(v16, v324, v323) )
                  break;
                v323 = v422;
                ++v321;
              }
              if ( v321 == 2 )
              {
                if ( (v5[6] & 0x10000000) == 0 )
                  goto LABEL_600;
LABEL_597:
                v321 = -1;
                goto LABEL_598;
              }
              if ( v321 != -1 )
                goto LABEL_600;
            }
            else
            {
              v321 = -1;
            }
LABEL_598:
            if ( !*(_DWORD *)(v430 + 8) )
            {
              LODWORD(v13) = 0;
              *(_DWORD *)(v430 + 8) = 1;
            }
LABEL_600:
            v325 = *((_DWORD *)v5 + 10) - 1;
            if ( v325 >= 0 )
            {
              v326 = v430;
              do
              {
                if ( *(_QWORD *)(32LL * (unsigned int)v325 + v5[4] + 8)
                  && (v325 == (_DWORD)v13 || !*(_DWORD *)(v326 + 8)) )
                {
                  sqlite3VdbeUsesBtree(v11, (unsigned int)v325);
                  sqlite3VdbeAddOp3(v327, 4, v325, 1, v321);
                }
                --v325;
              }
              while ( v325 >= 0 );
              v16 = v440;
            }
            v304 = 1;
LABEL_609:
            v305 = 1;
            goto LABEL_553;
          }
          v329 = v23 - 30;
          if ( v329 )
          {
            v330 = v329 - 1;
            if ( !v330 )
            {
              v337 = *(_QWORD *)(v14 + v424 + 8);
              if ( v16 )
              {
                v420 = 0;
                sqlite3GetInt32(v16, &v420);
                v339 = v420;
                *((_DWORD *)v5 + 29) = v420;
                if ( (unsigned int)sqlite3BtreeSetPageSize(v337, v339, 0, 0) == 7 )
                  sqlite3OomFault(v5);
                goto LABEL_806;
              }
              if ( v337 )
                v338 = *(_DWORD *)(*(_QWORD *)(v337 + 8) + 52LL);
              else
                v338 = 0;
              v28 = v338;
              goto LABEL_805;
            }
            v331 = v330 - 1;
            if ( v331 )
            {
              if ( v331 != 1 )
                goto LABEL_677;
              v332 = *(_QWORD *)(v14 + v424 + 8);
              v333 = -1;
              if ( v16 )
              {
                if ( (unsigned int)sqlite3StrICmp(v16, "fast") )
                  v333 = (unsigned __int8)getSafetyLevel(v16, 1, 0) != 0;
                else
                  v333 = v334;
              }
              if ( !*(_DWORD *)(v430 + 8) && v333 >= 0 )
              {
                for ( i4 = 0; i4 < *((_DWORD *)v5 + 10); ++i4 )
                  sqlite3BtreeSecureDelete(*(_QWORD *)(32LL * i4 + v5[4] + 8), (unsigned int)v333);
              }
              AutoVacuum = sqlite3BtreeSecureDelete(v332, (unsigned int)v333);
              goto LABEL_55;
            }
            for ( i5 = 0; i5 != 67; ++i5 )
              sqlite3VdbeMultiLoad(v11, 1, "s", (&off_1400AA6A0)[3 * i5], v408, v411, v415, v416, v417, v418);
            goto LABEL_791;
          }
          if ( v16 )
          {
            v420 = 0;
            sqlite3GetInt32(v16, &v420);
            String = v420;
            if ( (v420 & 2) == 0 )
              goto LABEL_806;
          }
          else
          {
            String = 65534;
          }
          v420 = *((_DWORD *)v9 + 13);
          *((_DWORD *)v9 + 13) = v420 + 1;
          if ( v433 )
          {
            v340 = v13;
            v426 = v13;
          }
          else
          {
            v340 = *((_DWORD *)v5 + 10) - 1;
            v426 = v340;
            if ( (int)v13 > v340 )
            {
LABEL_666:
              sqlite3VdbeAddOp3(v11, 166, 0, 0, 0);
              goto LABEL_806;
            }
          }
          do
          {
            if ( (_DWORD)v13 != 1 )
            {
              sqlite3CodeVerifySchema(v9, (unsigned int)v13);
              for ( i6 = *(_QWORD **)(*(_QWORD *)(32LL * (int)v13 + v5[4] + 24) + 16LL); i6; i6 = (_QWORD *)*i6 )
              {
                v342 = i6[2];
                if ( (*(_DWORD *)(v342 + 48) & 0x100) != 0 )
                {
                  v343 = *(_QWORD *)(v342 + 16);
                  v344 = *(_WORD *)(v342 + 58) + 46;
                  v431 = v344;
                  while ( v343 )
                  {
                    if ( *(char *)(v343 + 100) >= 0 )
                      goto LABEL_656;
                    v343 = *(_QWORD *)(v343 + 40);
                  }
                  if ( v344 )
                  {
                    sqlite3OpenTable((_DWORD)v9, v420, v13, v342, 112);
                    sqlite3VdbeAddOp3(v11, 33, v420, (String & 1) + 2 + *(_DWORD *)(v11 + 144), v431);
                  }
LABEL_656:
                  v345 = sqlite3MPrintf(
                           v5,
                           "ANALYZE \"%w\".\"%w\"",
                           *(_QWORD *)(32LL * (int)v13 + v5[4]),
                           *(_QWORD *)v342);
                  v422 = v345;
                  if ( (String & 1) != 0 )
                  {
                    v346 = *((_BYTE *)v9 + 31);
                    if ( v346 )
                    {
                      v348 = v346 - 1;
                      *((_BYTE *)v9 + 31) = v348;
                      v347 = *((_DWORD *)v9 + v348 + 56);
                    }
                    else
                    {
                      v347 = *((_DWORD *)v9 + 14) + 1;
                      *((_DWORD *)v9 + 14) = v347;
                    }
                    v349 = sqlite3VdbeAddOp3(v11, 117, 0, v347, 0);
                    sqlite3VdbeChangeP4(v11, v349, v422, 4294967290LL);
                    sqlite3VdbeAddOp3(v11, 84, v347, 1, 0);
                  }
                  else
                  {
                    v350 = sqlite3VdbeAddOp3(v11, 148, 0, 0, 0);
                    sqlite3VdbeChangeP4(v11, v350, v345, 4294967290LL);
                  }
                }
              }
              v340 = v426;
            }
            LODWORD(v13) = v13 + 1;
          }
          while ( (int)v13 <= v340 );
          v16 = v440;
          goto LABEL_666;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140066370  push    rbp
0x140066372  push    rbx
0x140066373  push    rsi
0x140066374  push    rdi
0x140066375  push    r12
0x140066377  push    r13
0x140066379  push    r14
0x14006637b  push    r15
0x14006637d  lea     rbp, [rsp-68h]
0x140066382  sub     rsp, 168h
0x140066389  mov     rax, cs:__security_cookie
0x140066390  xor     rax, rsp
0x140066393  mov     [rbp+0A0h+var_48], rax
0x140066397  mov     r15, [rcx]
0x14006639a  xorps   xmm0, xmm0
0x14006639d  mov     rbx, r8
0x1400663a0  mov     [rbp+0A0h+var_A8], r15
0x1400663a4  xor     r14d, r14d
0x1400663a7  mov     [rbp+0A0h+var_100], rbx
0x1400663ab  mov     [rsp+1A0h+var_128], r14
0x1400663b0  mov     r12, r9
0x1400663b3  movups  [rbp+0A0h+var_68], xmm0
0x1400663b7  mov     rdi, rdx
0x1400663ba  mov     r13, rcx
0x1400663bd  movups  [rbp+0A0h+var_58], xmm0
0x1400663c1  mov     [rbp+0A0h+var_A0], rcx
0x1400663c5  call    sqlite3GetVdbe
0x1400663ca  mov     [rbp+0A0h+var_B0], rax
0x1400663ce  mov     rsi, rax
0x1400663d1  test    rax, rax
0x1400663d4  jz      loc_140069CC5
0x1400663da  mov     dword ptr [rsp+1A0h+var_180], r14d
0x1400663df  mov     edx, 0A6h
0x1400663e4  mov     r14d, 1
0x1400663ea  mov     rcx, rax
0x1400663ed  mov     r9d, r14d
0x1400663f0  mov     r8d, r14d
0x1400663f3  call    sqlite3VdbeAddOp3
0x1400663f8  lea     r9, [rsp+1A0h+var_128]
0x1400663fd  mov     dword ptr [r13+38h], 2
0x140066405  mov     r8, rbx
0x140066408  mov     rdx, rdi
0x14006640b  mov     rcx, r13
0x14006640e  call    sqlite3TwoPartName
0x140066413  movsxd  rdi, eax
0x140066416  test    eax, eax
0x140066418  js      loc_140069CC5
0x14006641e  mov     rax, [r15+20h]
0x140066422  mov     [rbp+0A0h+var_120], rax
0x140066426  cmp     edi, r14d
0x140066429  jnz     short loc_14006643B
0x14006642b  mov     rcx, r13
0x14006642e  call    sqlite3OpenTempDatabase
0x140066433  test    eax, eax
0x140066435  jnz     loc_140069CC5
0x14006643b  mov     rdx, [rsp+1A0h+var_128]
0x140066440  mov     rcx, r15
0x140066443  call    sqlite3NameFromToken
0x140066448  mov     [rbp+0A0h+var_90], rax
0x14006644c  test    rax, rax
0x14006644f  jz      loc_140069CC5
0x140066455  mov     rbx, rdi
0x140066458  mov     rcx, r15
0x14006645b  shl     rbx, 5
0x14006645f  cmp     [rbp+0A0h+arg_20], 0
0x140066466  jz      short loc_140066479
0x140066468  mov     r8, r12
0x14006646b  lea     rdx, aT; "-%T"
0x140066472  call    sqlite3MPrintf
0x140066477  jmp     short loc_140066481
0x140066479  mov     rdx, r12
0x14006647c  call    sqlite3NameFromToken
0x140066481  mov     r12, rax
0x140066484  mov     [rbp+0A0h+var_C8], rax
0x140066488  mov     rax, [rbp+0A0h+var_100]
0x14006648c  xor     ecx, ecx
0x14006648e  cmp     [rax+8], ecx
0x140066491  jbe     short loc_14006649D
0x140066493  mov     rax, [rbp+0A0h+var_120]
0x140066497  mov     rax, [rbx+rax]
0x14006649b  jmp     short loc_1400664A0
0x14006649d  mov     rax, rcx
0x1400664a0  mov     r8, [rbp+0A0h+var_90]
0x1400664a4  mov     r9, r12
0x1400664a7  mov     edx, 13h
0x1400664ac  mov     [rbp+0A0h+var_E8], rax
0x1400664b0  mov     rcx, r13
0x1400664b3  mov     [rsp+1A0h+var_180], rax
0x1400664b8  call    sqlite3AuthCheck
0x1400664bd  xor     ecx, ecx
0x1400664bf  test    eax, eax
0x1400664c1  jnz     loc_140069CA9
0x1400664c7  mov     rax, [rbp+0A0h+var_90]
0x1400664cb  lea     r8d, [rcx+0Eh]
0x1400664cf  mov     rdx, [rbp+0A0h+var_E8]
0x1400664d3  lea     r9, [rbp+0A0h+var_68]
0x1400664d7  mov     qword ptr [rbp+0A0h+var_68], rcx
0x1400664db  mov     qword ptr [rbp+0A0h+var_58+8], rcx
0x1400664df  mov     qword ptr [rbp+0A0h+var_68+8], rax
0x1400664e3  mov     qword ptr [rbp+0A0h+var_58], r12
0x1400664e7  mov     [r15+298h], ecx
0x1400664ee  mov     rcx, r15
0x1400664f1  call    sqlite3_file_control
0x1400664f6  mov     [rsp+1A0h+var_13C], eax
0x1400664fa  test    eax, eax
0x1400664fc  jnz     short loc_14006653D
0x1400664fe  mov     edx, r14d
0x140066501  mov     rcx, rsi
0x140066504  call    sqlite3VdbeSetNumCols
0x140066509  mov     r9, qword ptr [rbp+0A0h+var_68]
0x14006650d  xor     r8d, r8d
0x140066510  xor     edx, edx
0x140066512  mov     [rsp+1A0h+var_180], 0FFFFFFFFFFFFFFFFh
0x14006651b  mov     rcx, rsi
0x14006651e  call    sqlite3VdbeSetColName
0x140066523  mov     rdx, qword ptr [rbp+0A0h+var_68]
0x140066527  mov     rcx, rsi
0x14006652a  call    returnSingleText
0x14006652f  mov     rcx, qword ptr [rbp+0A0h+var_68]
0x140066533  call    sqlite3_free
0x140066538  jmp     loc_140069CA9
0x14006653d  cmp     eax, 0Ch
0x140066540  jz      short loc_140066574
0x140066542  mov     r8, qword ptr [rbp+0A0h+var_68]
0x140066546  test    r8, r8
0x140066549  jz      short loc_140066567
0x14006654b  lea     rdx, aS_6; "%s"
0x140066552  mov     rcx, r13
0x140066555  call    sqlite3ErrorMsg
0x14006655a  mov     rcx, qword ptr [rbp+0A0h+var_68]
0x14006655e  call    sqlite3_free
0x140066563  mov     eax, [rsp+1A0h+var_13C]
0x140066567  add     [r13+30h], r14d
0x14006656b  mov     [r13+18h], eax
0x14006656f  jmp     loc_140069CA9
0x140066574  mov     rcx, [rbp+0A0h+var_90]
0x140066578  call    pragmaLocate
0x14006657d  mov     [rbp+0A0h+var_118], rax
0x140066581  mov     r10, rax
0x140066584  test    rax, rax
0x140066587  jz      loc_140069CA9
0x14006658d  test    [rax+9], r14b
0x140066591  jz      short loc_1400665A7
0x140066593  mov     rcx, r13
0x140066596  call    sqlite3ReadSchema
0x14006659b  test    eax, eax
0x14006659d  jnz     loc_140069CA9
0x1400665a3  mov     r10, [rbp+0A0h+var_118]
0x1400665a7  mov     r11d, 2
0x1400665ad  test    [r10+9], r11b
0x1400665b1  jnz     short loc_1400665D4
0x1400665b3  test    byte ptr [r10+9], 4
0x1400665b8  jz      short loc_1400665BF
0x1400665ba  test    r12, r12
0x1400665bd  jnz     short loc_1400665D4
0x1400665bf  mov     rdx, r10
0x1400665c2  mov     rcx, rsi
0x1400665c5  call    setPragmaResultColumnNames
0x1400665ca  mov     r10, [rbp+0A0h+var_118]
0x1400665ce  mov     r11d, 2
0x1400665d4  movzx   ecx, byte ptr [r10+8]
0x1400665d9  cmp     ecx, 16h
0x1400665dc  ja      loc_140068BB5
0x1400665e2  jz      loc_1400678BC
0x1400665e8  mov     eax, 0Ch
0x1400665ed  cmp     ecx, eax
0x1400665ef  ja      loc_140066C2A
0x1400665f5  jz      loc_140066BA0
0x1400665fb  cmp     ecx, 7
0x1400665fe  ja      loc_1400669B6
0x140066604  jz      loc_14006692E
0x14006660a  sub     ecx, r14d
0x14006660d  jz      loc_1400668ED
0x140066613  sub     ecx, r14d
0x140066616  jz      loc_14006681C
0x14006661c  sub     ecx, r14d
0x14006661f  jz      loc_14006672E
0x140066625  sub     ecx, r14d
0x140066628  jz      short loc_14006667C
0x14006662a  cmp     ecx, r11d
0x14006662d  jnz     loc_1400694AC
0x140066633  xor     eax, eax
0x140066635  test    r12, r12
0x140066638  jnz     short loc_14006664C
0x14006663a  mov     rax, [rbp+0A0h+var_120]
0x14006663e  mov     rax, [rbx+rax+18h]
0x140066643  movsxd  rdx, dword ptr [rax+74h]
0x140066647  jmp     loc_140069CA1
0x14006664c  lea     rdx, [rsp+1A0h+var_140]
0x140066651  mov     [rsp+1A0h+var_140], eax
0x140066655  mov     rcx, r12
0x140066658  call    sqlite3GetInt32
0x14006665d  mov     r8, [rbp+0A0h+var_120]
0x140066661  mov     eax, [rsp+1A0h+var_140]
0x140066665  mov     rcx, [rbx+r8+18h]
0x14006666a  mov     [rcx+74h], eax
0x14006666d  mov     rdx, [rbx+r8+18h]
0x140066672  mov     rcx, [rbx+r8+8]
0x140066677  jmp     loc_1400678AF
0x14006667c  xor     eax, eax
0x14006667e  test    r12, r12
0x140066681  jnz     short loc_1400666A5
0x140066683  mov     rdx, r10
0x140066686  mov     rcx, rsi
0x140066689  call    setPragmaResultColumnNames
0x14006668e  mov     r8, [rbp+0A0h+var_118]
0x140066692  mov     rdx, r12
0x140066695  mov     rax, [r8+10h]
0x140066699  test    [r15+30h], rax
0x14006669d  setnz   dl
0x1400666a0  jmp     loc_140069CA1
0x1400666a5  mov     rbx, [r10+10h]
0x1400666a9  mov     edx, r14d
0x1400666ac  btr     rbx, 0Eh
0x1400666b1  mov     rcx, r12
0x1400666b4  cmp     [r15+65h], al
0x1400666b8  cmovnz  rbx, [r10+10h]
0x1400666bd  xor     r8d, r8d
0x1400666c0  call    getSafetyLevel
0x1400666c5  xor     r11d, r11d
0x1400666c8  test    al, al
0x1400666ca  jz      short loc_1400666D2
0x1400666cc  or      [r15+30h], rbx
0x1400666d0  jmp     short loc_140066711
0x1400666d2  mov     rax, rbx
0x1400666d5  not     rax
0x1400666d8  and     [r15+30h], rax
0x1400666dc  cmp     rbx, 80000h
0x1400666e3  jnz     short loc_1400666EE
0x1400666e5  mov     [r15+300h], r11
0x1400666ec  jmp     short loc_140066711
0x1400666ee  test    r14b, bl
0x1400666f1  jz      short loc_140066711
0x1400666f3  lea     rdx, aReset; "reset"
0x1400666fa  mov     rcx, r12
0x1400666fd  call    sqlite3StrICmp
0x140066702  test    eax, eax
0x140066704  jnz     short loc_140066711
0x140066706  mov     rcx, r15
0x140066709  call    sqlite3ResetAllSchemasOfConnection
0x14006670e  xor     r11d, r11d
0x140066711  xor     r9d, r9d
0x140066714  mov     dword ptr [rsp+1A0h+var_180], r11d
0x140066719  xor     r8d, r8d
0x14006671c  mov     edx, 0A6h
0x140066721  mov     rcx, rsi
0x140066724  call    sqlite3VdbeAddOp3
0x140066729  jmp     loc_1400669A9
0x14006672e  mov     rax, [rbp+0A0h+var_120]
0x140066732  xor     r11d, r11d
0x140066735  mov     rbx, [rbx+rax+8]
0x14006673a  test    r12, r12
0x14006673d  jnz     short loc_14006674F
0x14006673f  mov     rcx, rbx
0x140066742  call    sqlite3BtreeGetAutoVacuum
0x140066747  movsxd  rdx, eax
0x14006674a  jmp     loc_140069CA1
0x14006674f  lea     rdx, aNone; "none"
0x140066756  mov     rcx, r12
0x140066759  call    sqlite3StrICmp
0x14006675e  test    eax, eax
0x140066760  jnz     short loc_140066767
0x140066762  mov     r13d, r11d
0x140066765  jmp     short loc_1400667B9
0x140066767  lea     rdx, aFull; "full"
0x14006676e  mov     rcx, r12
0x140066771  call    sqlite3StrICmp
0x140066776  test    eax, eax
0x140066778  jnz     short loc_14006677F
0x14006677a  mov     r13d, r14d
0x14006677d  jmp     short loc_1400667B9
0x14006677f  lea     rdx, aIncremental; "incremental"
0x140066786  mov     rcx, r12
0x140066789  call    sqlite3StrICmp
0x14006678e  test    eax, eax
0x140066790  jnz     short loc_140066798
0x140066792  lea     r13d, [rax+2]
0x140066796  jmp     short loc_1400667B9
0x140066798  lea     rdx, [rbp+0A0h+var_110]
0x14006679c  mov     [rbp+0A0h+var_110], r11d
0x1400667a0  mov     rcx, r12
0x1400667a3  call    sqlite3GetInt32
0x1400667a8  movzx   ecx, byte ptr [rbp+0A0h+var_110]
0x1400667ac  xor     eax, eax
0x1400667ae  cmp     [rbp+0A0h+var_110], 2
0x1400667b2  cmova   ecx, eax
0x1400667b5  movzx   r13d, cl
0x1400667b9  mov     edx, r13d
0x1400667bc  mov     [r15+6Ah], r13b
0x1400667c0  mov     rcx, rbx
0x1400667c3  call    sqlite3BtreeSetAutoVacuum
0x1400667c8  test    eax, eax
0x1400667ca  jnz     loc_140069CA9
0x1400667d0  lea     eax, [r13-1]
0x1400667d4  cmp     eax, r14d
0x1400667d7  ja      loc_140069CA9
0x1400667dd  mov     ebx, [rsi+90h]
0x1400667e3  lea     r8, qword_1400B2770
0x1400667ea  mov     edx, 5
0x1400667ef  mov     rcx, rsi
  ... truncated ...
```
