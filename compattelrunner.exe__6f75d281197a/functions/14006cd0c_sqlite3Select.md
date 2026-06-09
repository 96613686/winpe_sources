# sqlite3Select

- ea: `0x14006cd0c`
- end: `0x14006ebf5`
- name: `sqlite3Select`
- size: `7913`
- prototype: ``
- caller_count: `12`
- callee_count: `63`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140024174`
- `0x14002f17c`
- `0x14003a3c4`
- `0x14003ac30`
- `0x140050c68`
- `0x1400513e0`
- `0x140055854`
- `0x140060400`
- `0x140062f5c`
- `0x14006cd0c`
- `0x140093160`
- `0x1400a40bc`

## callees

- `0x140001ba0`
- `0x14001c22c`
- `0x140024e2c`
- `0x14002631c`
- `0x1400280e8`
- `0x14002aa98`
- `0x14002b178`
- `0x14002bebc`
- `0x14002c490`
- `0x14002d73c`
- `0x14002eb84`
- `0x140030568`
- `0x140032024`
- `0x14003a3c4`
- `0x140040f90`
- `0x140041324`
- `0x140044fe4`
- `0x140047180`
- `0x1400480a0`
- `0x14004bdbc`
- `0x1400516cc`
- `0x140053e3c`
- `0x140053fec`
- `0x1400560c4`
- `0x140056508`
- `0x14005654c`
- `0x1400568bc`
- `0x1400569d4`
- `0x140056aa8`
- `0x14005904c`
- `0x1400592c0`
- `0x140059a68`
- `0x140059c88`
- `0x140059f20`
- `0x140059fbc`
- `0x14005cb30`
- `0x14005ebd0`
- `0x14005f5fc`
- `0x140061d5c`
- `0x140061df4`
- `0x140065e48`
- `0x14006b460`
- `0x14006cd0c`
- `0x14006f02c`
- `0x1400702ec`
- `0x140070918`
- `0x1400738a0`
- `0x14007399c`
- `0x140073ca8`
- `0x140073d38`

## string_xrefs

- `0x14006e0bc`: `USE TEMP B-TREE FOR %s`
- `0x14006e9a1`: `USE TEMP B-TREE FOR %s`

## pseudocode

```c
__int64 __fastcall sqlite3Select(_QWORD *a1, __int64 a2, __int128 *a3)
{
  __int64 v4; // r13
  int v6; // esi
  __int64 v7; // rdi
  BOOL v8; // r12d
  __int64 v9; // r8
  int v10; // ebx
  __int64 v11; // rsi
  const char *v12; // r8
  signed int *v14; // r14
  bool v15; // zf
  __int64 v16; // r10
  __int64 v17; // rbx
  char v18; // al
  int *v19; // rcx
  const char **v20; // r9
  int v21; // eax
  char v22; // al
  int ii; // ecx
  __int64 v24; // rdx
  char v25; // al
  char v26; // al
  int jj; // edx
  __int64 v28; // rcx
  int v29; // r8d
  int v30; // edx
  __int64 v31; // r8
  unsigned int v32; // r9d
  _BYTE *v33; // rax
  __int64 v34; // rsi
  signed int v35; // r11d
  __int64 v36; // rsi
  unsigned int *v37; // rbx
  __int64 v38; // r8
  int v39; // r11d
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rax
  unsigned int v43; // edi
  unsigned int v44; // r8d
  int v45; // ecx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // rdx
  unsigned int v49; // ecx
  unsigned int *v50; // rax
  _DWORD *v51; // rax
  int v52; // r9d
  _DWORD *v53; // rbx
  unsigned int v54; // r8d
  int v55; // r9d
  _DWORD *v56; // rax
  int v57; // r9d
  unsigned int v58; // eax
  _BYTE *v59; // rax
  int *v60; // rbx
  int v61; // r10d
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rax
  int *v65; // rbx
  int *v66; // rcx
  _DWORD *v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  int v70; // r8d
  __int64 v71; // rdi
  unsigned int v72; // eax
  __int64 v73; // r8
  unsigned int v74; // ebx
  int v75; // eax
  int i; // esi
  int *v77; // rcx
  __int64 v78; // rbx
  __int64 v79; // rdx
  signed int v80; // ecx
  __int64 v81; // rax
  unsigned int v82; // eax
  __int64 *v83; // rax
  __int64 v84; // rdi
  unsigned int v85; // eax
  __int64 v86; // r8
  unsigned int v87; // ebx
  __int64 v88; // rax
  int *v89; // rbx
  __int16 v90; // ax
  __int64 v91; // rsi
  __int16 v92; // bx
  __int64 v93; // rax
  __int64 v94; // rdx
  __int16 v95; // ax
  char v96; // al
  __int64 v97; // rcx
  int v98; // r8d
  __int64 v99; // rax
  int v100; // eax
  unsigned int v101; // ebx
  int v102; // esi
  unsigned int v103; // edi
  unsigned int v104; // r14d
  __int64 v105; // r12
  __int128 *v106; // rbx
  __int64 v107; // rdx
  __int64 v108; // rcx
  __int64 v109; // r14
  int *v110; // rax
  int v111; // ecx
  _DWORD *v112; // rdx
  int v113; // ecx
  _DWORD *v114; // rdx
  int j; // r8d
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // rax
  __int64 v119; // rsi
  int v120; // eax
  int *v121; // rdx
  _DWORD *v122; // rcx
  __int64 v123; // r8
  __int64 v124; // rdx
  __int64 *v125; // rax
  __int64 v126; // rcx
  _DWORD *v127; // r11
  __int64 v128; // r11
  __int64 v129; // r11
  __int64 v130; // r10
  int *v131; // rax
  __int64 v132; // rax
  __int64 v133; // rcx
  __int64 v134; // rdx
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // rax
  __int16 v138; // cx
  _DWORD *v139; // rax
  int v140; // r9d
  int v141; // r8d
  int v142; // r8d
  unsigned int v143; // edx
  unsigned int v144; // ecx
  int v145; // eax
  unsigned int v146; // ecx
  __int16 v147; // dx
  __int64 v148; // r8
  __int64 v149; // r14
  int v150; // r9d
  int v151; // edx
  int k; // r8d
  int v153; // eax
  int v154; // ecx
  bool v155; // sf
  const char *v156; // r9
  int v157; // r14d
  unsigned int v158; // r8d
  unsigned int v159; // r10d
  int v160; // r9d
  int v161; // edx
  unsigned int v162; // eax
  int v163; // eax
  unsigned int v164; // r13d
  int v165; // edi
  __int64 v166; // rcx
  char v167; // al
  int v168; // r14d
  unsigned __int8 v169; // al
  unsigned int v170; // r14d
  unsigned int v171; // ecx
  char v172; // al
  int v173; // eax
  unsigned __int8 v174; // al
  int v175; // r14d
  __int64 v176; // rdx
  unsigned int v177; // eax
  int v178; // r14d
  unsigned int v179; // r13d
  __int64 v180; // r8
  _DWORD *v181; // r14
  unsigned int v182; // eax
  unsigned int v183; // ebx
  unsigned int v184; // r14d
  int v185; // edi
  unsigned int v186; // r12d
  int v187; // ebx
  __int64 v188; // rdx
  __int64 v189; // rdi
  _QWORD *v190; // rdi
  __int64 v191; // rdx
  __int64 v192; // rcx
  int v193; // r14d
  __int64 v194; // rdx
  __int64 m; // rbx
  __int64 n; // rax
  __int16 v197; // cx
  unsigned int v198; // r8d
  const unsigned __int16 *v199; // rcx
  const char *v200; // rax
  unsigned int v201; // edi
  int v202; // ecx
  __int16 v203; // bx
  unsigned int v204; // edx
  __int64 v205; // r9
  int *v206; // rax
  __int64 v207; // rax
  __int64 v208; // rbx
  unsigned int v209; // r14d
  __int64 v210; // r8
  unsigned int v211; // ecx
  __int64 v212; // r9
  int v213; // r9d
  int v214; // [rsp+20h] [rbp-E0h]
  int v215; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v216; // [rsp+40h] [rbp-C0h]
  unsigned int v217; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v218; // [rsp+48h] [rbp-B8h]
  unsigned int v219; // [rsp+4Ch] [rbp-B4h]
  __int64 v220; // [rsp+50h] [rbp-B0h]
  char v221; // [rsp+58h] [rbp-A8h]
  int *v222; // [rsp+60h] [rbp-A0h]
  unsigned int v223; // [rsp+68h] [rbp-98h]
  unsigned int TempRange; // [rsp+6Ch] [rbp-94h]
  __int64 Vdbe; // [rsp+70h] [rbp-90h]
  _DWORD *v226; // [rsp+78h] [rbp-88h]
  unsigned int v227; // [rsp+80h] [rbp-80h]
  unsigned int v228; // [rsp+84h] [rbp-7Ch]
  unsigned int v229; // [rsp+88h] [rbp-78h]
  _DWORD *v230; // [rsp+90h] [rbp-70h]
  int v231; // [rsp+98h] [rbp-68h]
  unsigned int v232; // [rsp+9Ch] [rbp-64h]
  __int64 v233; // [rsp+A0h] [rbp-60h]
  int v234; // [rsp+A8h] [rbp-58h]
  __int64 v235; // [rsp+B0h] [rbp-50h]
  __int64 v236; // [rsp+B8h] [rbp-48h]
  int v237; // [rsp+C0h] [rbp-40h]
  __int128 *v238; // [rsp+C8h] [rbp-38h]
  __int128 v239; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v240; // [rsp+E0h] [rbp-20h]
  __int128 v241; // [rsp+F0h] [rbp-10h]
  __int128 v242; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v243[2]; // [rsp+110h] [rbp+10h] BYREF
  int *v244; // [rsp+130h] [rbp+30h]
  __int64 v245; // [rsp+138h] [rbp+38h]
  unsigned int v246; // [rsp+140h] [rbp+40h]
  unsigned int v247; // [rsp+144h] [rbp+44h]
  __int64 v248; // [rsp+148h] [rbp+48h]
  _BYTE v249[56]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v250; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v251; // [rsp+190h] [rbp+90h]

  v238 = a3;
  v250 = 0;
  v251 = 0;
  v4 = a2;
  v220 = *a1;
  v248 = a2;
  v239 = 0;
  v240 = 0;
  v241 = 0;
  v6 = 0;
  Vdbe = sqlite3GetVdbe(a1);
  v7 = Vdbe;
  if ( !v4 || *((_DWORD *)a1 + 12) || (unsigned int)sqlite3AuthCheck((_DWORD)a1, 21, 0, 0, 0) )
    return 1;
  v8 = 1;
  if ( *(_BYTE *)a3 <= 6u )
  {
    v9 = *(_QWORD *)(v4 + 72);
    if ( v9 )
    {
      sqlite3ParserAddCleanup(a1, sqlite3ExprListDelete, v9);
      *(_QWORD *)(v4 + 72) = 0;
    }
    *(_DWORD *)(v4 + 4) &= ~1u;
    *(_DWORD *)(v4 + 4) |= 0x400000u;
  }
  sqlite3SelectPrep(a1, v4, 0);
  if ( *((_DWORD *)a1 + 12) )
    goto LABEL_14;
  v10 = *(_DWORD *)(v4 + 4);
  if ( (v10 & 0x800000) != 0 )
  {
    v11 = *(_QWORD *)(v4 + 40) + 8LL;
    if ( (unsigned int)sameSrcAlias(v11) )
    {
      v12 = *(const char **)(v11 + 24);
      if ( !v12 )
        v12 = **(const char ***)(v11 + 32);
      sqlite3ErrorMsg(a1, "target object/alias may not appear in FROM clause: %s", v12);
      goto LABEL_14;
    }
    *(_DWORD *)(v4 + 4) = v10 & 0xFF7FFFFF;
    v6 = 0;
  }
  if ( *(_BYTE *)a3 == 9 )
    sqlite3GenerateColumnNames(a1, v4);
  if ( (unsigned int)sqlite3WindowRewrite(a1, v4) )
  {
LABEL_14:
    sqlite3VdbeExplainPop(a1);
    return v8;
  }
  else
  {
    v14 = *(signed int **)(v4 + 40);
    v15 = (*(_DWORD *)(v4 + 4) & 8) == 0;
    v231 = *(_DWORD *)(v4 + 4) & 8;
    v219 = !v15;
    v239 = *(unsigned __int64 *)(v4 + 72);
    v240 = 0;
    v241 = 0;
    if ( !*(_QWORD *)(v4 + 80) )
    {
      v16 = v220;
      do
      {
        if ( v6 >= *v14 )
        {
          v33 = *(_BYTE **)(v4 + 48);
          if ( v33 && *v33 == 44 && (*(_DWORD *)(v16 + 96) & 0x8000) == 0 )
            propagateConstants(a1, v4);
          v34 = v220;
          if ( (*(_DWORD *)(v220 + 96) & 0x201) == 0 && (unsigned int)countOfViewOptimization(a1, v4) )
          {
            if ( !*(_BYTE *)(v220 + 103) )
            {
              v14 = *(signed int **)(v4 + 40);
              goto LABEL_81;
            }
            goto LABEL_14;
          }
LABEL_81:
          v35 = 0;
          v218 = 0;
          if ( *v14 > 0 )
          {
            while ( 2 )
            {
              v36 = 26LL * v35;
              memset(v243, 0, 21);
              v242 = 0;
              v37 = (unsigned int *)&v14[v36 + 2];
              if ( !*(_QWORD *)&v14[v36 + 22] )
              {
                v38 = *((_QWORD *)v37 + 2);
                if ( v38 )
                {
                  sqlite3AuthCheck((_DWORD)a1, 20, v38, (unsigned int)&dword_1400ACDEC, *((_QWORD *)v37 + 1));
                  v35 = v218;
                }
              }
              v222 = (int *)*((_QWORD *)v37 + 5);
              if ( v222 )
              {
                v217 = 0;
                heightOfSelect(v4, &v217);
                v40 = v220;
                *((_DWORD *)a1 + 77) += v217;
                if ( (*(_DWORD *)(v40 + 96) & 0x1000) == 0 )
                {
                  if ( (v37[16] & 0x100) == 0 || (v41 = *((_QWORD *)v37 + 12), *(_BYTE *)(v41 + 18)) && *(int *)v41 < 2 )
                  {
                    pushDownWhereTerms((_DWORD)a1, (_DWORD)v222, *(_QWORD *)(v4 + 48), (_DWORD)v14, v39);
                    v40 = v220;
                  }
                }
                if ( (*(_DWORD *)(v40 + 96) & 0x4000000) == 0 )
                  disableUnusedSubqueryResultColumns(&v14[v36 + 2]);
                v233 = a1[46];
                a1[46] = *((_QWORD *)v37 + 2);
                v230 = v37 + 16;
                v219 = v37[16] & 0x100;
                if ( v219 )
                {
                  v42 = *((_QWORD *)v37 + 12);
                  if ( !*(_BYTE *)(v42 + 18) || *(int *)v42 >= 2 && *(_BYTE *)(v42 + 18) != 2 )
                    goto LABEL_111;
                }
                if ( (v14[17] & 0x40) != 0
                  || (*(_DWORD *)(*a1 + 96LL) & 0x2000000) != 0
                  || isSelfJoinView(v14, &v14[v36 + 2], v218 + 1, (unsigned int)*v14) )
                {
                  goto LABEL_110;
                }
                if ( v218 )
                {
                  if ( (*(_DWORD *)(v4 + 4) & 0x10000000) != 0 )
                    goto LABEL_110;
                  v49 = v218;
                  v50 = (unsigned int *)&v14[v36 + 2];
                  if ( (v37[15] & 0x22) != 0 )
                    goto LABEL_110;
                  while ( v49 )
                  {
                    v50 -= 26;
                    if ( !*((_QWORD *)v50 + 5) )
                    {
                      --v49;
                      if ( (v50[15] & 0x22) == 0 )
                        continue;
                    }
                    goto LABEL_110;
                  }
LABEL_104:
                  v43 = *(_DWORD *)(v7 + 144);
                  v44 = ++*((_DWORD *)a1 + 14);
                  v45 = Vdbe;
                  v14[v36 + 15] = v44;
                  sqlite3VdbeAddOp3(v45, 11, v44, 0, v43 + 1);
                  DWORD1(v242) = v14[v36 + 15];
                  v14[v36 + 14] = v43 + 1;
                  *((_QWORD *)&v242 + 1) = 0;
                  *((_QWORD *)&v243[0] + 1) = 0;
                  LODWORD(v243[0]) = 0;
                  LOBYTE(v242) = 13;
                  sqlite3VdbeExplain(a1, 1, "CO-ROUTINE %!S", &v14[v36 + 2]);
                  sqlite3Select(a1, v222, &v242);
                  *(_WORD *)(*(_QWORD *)&v14[v36 + 10] + 58LL) = *((_WORD *)v222 + 1);
                  v46 = (unsigned int)v14[v36 + 15];
                  v47 = Vdbe;
                  *v230 |= 0x20u;
                  v14[v36 + 16] = HIDWORD(v242);
                  sqlite3VdbeEndCoroutine(v47, v46);
                  v48 = v43;
                  v7 = Vdbe;
                  sqlite3VdbeJumpHere(Vdbe, v48);
                  *((_BYTE *)a1 + 31) = 0;
                  *((_DWORD *)a1 + 10) = 0;
                }
                else
                {
                  if ( *v14 == 1 || (v14[43] & 2) != 0 || (*(_DWORD *)(v4 + 4) & 0x10000000) == 0 )
                    goto LABEL_104;
LABEL_110:
                  if ( v219 )
                  {
LABEL_111:
                    v51 = *(_DWORD **)&v14[v36 + 26];
                    v226 = v51;
                    v52 = v51[1];
                    if ( v52 > 0 )
                    {
                      sqlite3VdbeAddOp3(v7, 10, v51[2], v52, 0);
                      v53 = v226;
                      v54 = v14[v36 + 19];
                      v55 = v226[3];
                      if ( v54 != v55 )
                        sqlite3VdbeAddOp3(v7, 115, v54, v55, 0);
                      *((_WORD *)v222 + 1) = *((_WORD *)v53 + 8);
                      goto LABEL_125;
                    }
                  }
                  v56 = (_DWORD *)isSelfJoinView(v14, &v14[v36 + 2], 0, v218);
                  v235 = (__int64)v56;
                  if ( v56 )
                  {
                    v57 = v56[12];
                    if ( v57 )
                    {
                      sqlite3VdbeAddOp3(v7, 10, v56[13], v57, 0);
                      v56 = (_DWORD *)v235;
                    }
                    sqlite3VdbeAddOp3(v7, 115, v14[v36 + 19], v56[17], 0);
                    *((_WORD *)v222 + 1) = *(_WORD *)(*(_QWORD *)(v235 + 40) + 2LL);
                  }
                  else
                  {
                    v58 = ++*((_DWORD *)a1 + 14);
                    v217 = 0;
                    v14[v36 + 15] = v58;
                    v232 = sqlite3VdbeAddOp3(v7, 9, 0, 0, 0);
                    v219 = v232 + 1;
                    v14[v36 + 14] = v232 + 1;
                    v59 = v230;
                    *v230 |= 0x10u;
                    if ( (*v59 & 8) == 0 )
                      v217 = sqlite3VdbeAddOp3(v7, 15, 0, 0, 0);
                    DWORD1(v242) = v14[v36 + 19];
                    LOBYTE(v242) = 12;
                    *((_QWORD *)&v242 + 1) = 0;
                    *((_QWORD *)&v243[0] + 1) = 0;
                    LODWORD(v243[0]) = 0;
                    sqlite3VdbeExplain(a1, 1, "MATERIALIZE %!S", &v14[v36 + 2]);
                    v60 = v222;
                    sqlite3Select(a1, v222, &v242);
                    v61 = 0;
                    *(_WORD *)(*(_QWORD *)&v14[v36 + 10] + 58LL) = *((_WORD *)v60 + 1);
                    if ( v217 )
                      sqlite3VdbeJumpHere(v7, v217);
                    sqlite3VdbeAddOp3(v7, 67, v14[v36 + 15], v219, v61);
                    sqlite3VdbeJumpHere(v7, v232);
                    *((_BYTE *)a1 + 31) = 0;
                    *((_DWORD *)a1 + 10) = 0;
                    if ( (*v230 & 0x108) == 0x100 )
                    {
                      v62 = *(_QWORD *)&v14[v36 + 26];
                      *(_DWORD *)(v62 + 4) = v14[v36 + 14];
                      *(_DWORD *)(v62 + 8) = v14[v36 + 15];
                      *(_DWORD *)(v62 + 12) = v14[v36 + 19];
                      *(_WORD *)(v62 + 16) = *((_WORD *)v60 + 1);
                    }
                  }
                }
LABEL_125:
                v34 = v220;
                if ( *(_BYTE *)(v220 + 103) )
                  goto LABEL_14;
                v217 = 0;
                heightOfSelect(v4, &v217);
                v63 = v233;
                v35 = v218;
                *((_DWORD *)a1 + 77) -= v217;
                a1[46] = v63;
              }
              else
              {
                v34 = v220;
              }
              v218 = ++v35;
              if ( v35 >= *v14 )
                break;
              continue;
            }
          }
          v64 = *(_QWORD *)(v4 + 48);
          v65 = *(int **)(v4 + 32);
          v235 = 0;
          v66 = *(int **)(v4 + 56);
          v236 = v64;
          v67 = *(_DWORD **)(v4 + 64);
          v244 = v66;
          LODWORD(v66) = *(_DWORD *)(v4 + 4);
          v230 = v67;
          v222 = v65;
          LOBYTE(v250) = (unsigned __int8)v66 & 1;
          if ( ((unsigned __int8)v66 & 9) == 1
            && !(unsigned int)sqlite3ExprListCompare(v239, v65, 0xFFFFFFFFLL)
            && !*(_QWORD *)(v4 + 112) )
          {
            *(_DWORD *)(v4 + 4) &= ~1u;
            v68 = sqlite3ExprListDup(v34, v65, 0);
            *(_DWORD *)(v4 + 4) |= 8u;
            v244 = (int *)v68;
            *(_QWORD *)(v4 + 56) = v68;
            LOBYTE(v250) = 2;
          }
          if ( (_QWORD)v239 )
          {
            v69 = sqlite3KeyInfoFromExprList(a1, v239, 0, (unsigned int)*v65);
            HIDWORD(v239) = *((_DWORD *)a1 + 13);
            v70 = HIDWORD(v239);
            v71 = v69;
            *((_DWORD *)a1 + 13) = HIDWORD(v239) + 1;
            v72 = sqlite3VdbeAddOp3(Vdbe, 118, v70, *v65 + *(_DWORD *)v239 + 1, 0);
            v73 = v71;
            v7 = Vdbe;
            v74 = v72;
            sqlite3VdbeChangeP4(Vdbe, v72, v73, 4294967288LL);
            DWORD2(v240) = v74;
            v65 = v222;
          }
          else
          {
            DWORD2(v240) = -1;
          }
          if ( *(_BYTE *)v238 == 12 )
          {
            sqlite3VdbeAddOp3(v7, 118, *((_DWORD *)v238 + 1), *v65, 0);
            if ( (*(_DWORD *)(v4 + 4) & 0x800) != 0 )
            {
              v75 = *v65;
              for ( i = *v65 - 1; i > 0; --i )
              {
                v77 = v222;
                v78 = 8LL * (unsigned int)i;
                if ( (v222[v78 + 7] & 0x40) != 0 )
                {
                  v65 = v222;
                  break;
                }
                v79 = *(_QWORD *)&v222[v78 + 2];
                if ( v79 )
                {
                  sqlite3ExprDeleteNN(v220, v79);
                  v77 = v222;
                }
                if ( *(_QWORD *)&v77[v78 + 4] )
                  sqlite3DbFreeNN(v220);
                v65 = v222;
                --*v222;
                v75 = *v65;
              }
              v80 = 0;
              if ( v75 > 0 )
              {
                do
                {
                  v81 = 8LL * v80;
                  if ( (v65[v81 + 7] & 0x40) == 0 )
                    **(_BYTE **)&v65[v81 + 2] = 121;
                  ++v80;
                }
                while ( v80 < *v65 );
              }
            }
          }
          v82 = *((_DWORD *)a1 + 17) - 1;
          *((_DWORD *)a1 + 17) = v82;
          v15 = (*(_DWORD *)(v4 + 4) & 0x4000) == 0;
          v247 = v82;
          if ( v15 )
            *(_WORD *)(v4 + 2) = 320;
          if ( *(_QWORD *)(v4 + 96) )
            computeLimitRegisters(a1, v4, v82);
          if ( !*(_DWORD *)(v4 + 8) && (SDWORD2(v240) & 0x80000000) == 0 )
          {
            if ( *(_BYTE *)(*(_QWORD *)v7 + 103LL) )
              v83 = qword_1400C8EC0;
            else
              v83 = (__int64 *)(*(_QWORD *)(v7 + 136) + 24LL * SDWORD2(v240));
            *(_BYTE *)v83 = 119;
            BYTE4(v241) |= 1u;
          }
          if ( (*(_BYTE *)(v4 + 4) & 1) != 0 )
          {
            HIDWORD(v250) = *((_DWORD *)a1 + 13);
            *((_DWORD *)a1 + 13) = HIDWORD(v250) + 1;
            v84 = sqlite3KeyInfoFromExprList(a1, *(_QWORD *)(v4 + 32), 0, 0);
            v85 = sqlite3VdbeAddOp3(Vdbe, 118, HIDWORD(v250), 0, 0);
            v86 = v84;
            v7 = Vdbe;
            v87 = v85;
            sqlite3VdbeChangeP4(Vdbe, v85, v86, 4294967288LL);
            v251 = v87;
            v88 = *(int *)(v7 + 144);
            if ( (int)v88 > 0 )
              *(_WORD *)(*(_QWORD *)(v7 + 136) + 24 * v88 - 22) = 8;
            BYTE1(v250) = 3;
          }
          else
          {
            BYTE1(v250) = 0;
          }
          v89 = v244;
          if ( !v231 && !v244 )
          {
            v90 = 256;
            if ( !(_BYTE)v250 )
              v90 = 0;
            v91 = *(_QWORD *)(v4 + 112);
            v92 = v90 | *(_WORD *)(v4 + 4) & 0x4000;
            if ( v91 )
              sqlite3WindowCodeInit(a1, v4);
            v93 = sqlite3WhereBegin(
                    (_DWORD)a1,
                    (_DWORD)v14,
                    v236,
                    v239,
                    *(_QWORD *)(v4 + 32),
                    v4,
                    v92,
                    *(__int16 *)(v4 + 2));
            v233 = v93;
            v94 = v93;
            if ( !v93 )
              goto LABEL_14;
            v95 = *(_WORD *)(v93 + 72);
            if ( v95 < *(__int16 *)(v4 + 2) )
              *(_WORD *)(v4 + 2) = v95;
            if ( (_BYTE)v250 )
            {
              v96 = BYTE1(v250);
              if ( *(_BYTE *)(v94 + 67) )
                v96 = *(_BYTE *)(v94 + 67);
              BYTE1(v250) = v96;
            }
            v97 = v239;
            if ( (_QWORD)v239 )
            {
              v98 = 0;
              if ( *(char *)(v94 + 65) >= 0 )
                v98 = *(char *)(v94 + 65);
              DWORD2(v239) = v98;
              if ( (*(_BYTE *)(v94 + 68) & 4) != 0
                && (v99 = 112LL * *(unsigned __int8 *)(v94 + 64), !*(_QWORD *)(v99 + v94 + 808)) )
              {
                v100 = *(_DWORD *)(v99 + v94 + 768);
              }
              else
              {
                v100 = *(_DWORD *)(v94 + 48);
              }
              LODWORD(v241) = v100;
              if ( v98 == *(_DWORD *)v239 )
                v97 = 0;
              *(_QWORD *)&v239 = v97;
            }
            if ( (SDWORD2(v240) & 0x80000000) == 0 && !v97 )
            {
              sqlite3VdbeChangeToNoop(v7, DWORD2(v240));
              v94 = v233;
            }
            if ( v91 )
            {
              v101 = *((_DWORD *)a1 + 17);
              ++*((_DWORD *)a1 + 14);
              --v101;
              v102 = *((_DWORD *)a1 + 14);
              v103 = v101 - 1;
              v104 = v101 - 2;
              *((_DWORD *)a1 + 17) = v101 - 2;
              sqlite3WindowCodeStep((_DWORD)a1, v4, v94, v102, v101);
              v105 = Vdbe;
              sqlite3VdbeAddOp3(Vdbe, 9, 0, v101 - 2, 0);
              sqlite3VdbeResolveLabel(v105, v101);
              v106 = v238;
              LODWORD(v241) = 0;
              selectInnerLoop((_DWORD)a1, v4, -1, (unsigned int)&v239, (__int64)&v250, (__int64)v238, v103, v104);
              sqlite3VdbeResolveLabel(v105, v103);
              sqlite3VdbeAddOp3(v105, 67, v102, 0, 0);
              v107 = v104;
              v108 = v105;
              v109 = v105;
              goto LABEL_373;
            }
            v106 = v238;
            selectInnerLoop(
              (_DWORD)a1,
              v4,
              -1,
              (unsigned int)&v239,
              (__int64)&v250,
              (__int64)v238,
              *(_DWORD *)(v94 + 48),
              *(_DWORD *)(v94 + 52));
            sqlite3WhereEnd(v233);
            v109 = Vdbe;
LABEL_374:
            if ( BYTE1(v250) == 3 )
              sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s", "DISTINCT");
            if ( (_QWORD)v239 )
              generateSortTail((_DWORD)a1, v4, (unsigned int)&v239, *v222, (__int64)v106);
            sqlite3VdbeResolveLabel(v109, v247);
            v8 = *((_DWORD *)a1 + 12) > 0;
LABEL_379:
            v130 = v220;
            goto LABEL_380;
          }
          v237 = 0;
          memset(v249, 0, sizeof(v249));
          if ( v244 )
          {
            v110 = *(int **)(v4 + 32);
            v111 = *v110;
            v112 = v110 + 2;
            while ( v111 > 0 )
            {
              *((_WORD *)v112 + 13) = 0;
              v112 += 8;
              --v111;
            }
            v113 = *v89;
            v114 = v89 + 2;
            while ( v113 > 0 )
            {
              *((_WORD *)v114 + 13) = 0;
              v114 += 8;
              --v113;
            }
            if ( *(__int16 *)(v4 + 2) > 66 )
              *(_WORD *)(v4 + 2) = 66;
            if ( (_QWORD)v239 && *v89 == *(_DWORD *)v239 )
            {
              for ( j = 0; j < *v89; LOBYTE(v89[8 * v116 + 6]) = *(_BYTE *)(32 * v116 + v239 + 24) & 1 )
                v116 = j++;
              if ( !(unsigned int)sqlite3ExprListCompare(v89, v239, 0xFFFFFFFFLL) )
                v237 = 1;
            }
          }
          else
          {
            *(_WORD *)(v4 + 2) = 0;
          }
          v117 = v220;
          v229 = *((_DWORD *)a1 + 17) - 1;
          *((_DWORD *)a1 + 17) = v229;
          v118 = sqlite3DbMallocZero(v117, 56);
          v119 = v118;
          if ( v118 )
            sqlite3ParserAddCleanup(a1, agginfoFree, v118);
          if ( *(_BYTE *)(v220 + 103) )
            goto LABEL_14;
          *(_DWORD *)(v119 + 52) = *(_DWORD *)(v4 + 16);
          *(_QWORD *)v249 = a1;
          *(_QWORD *)&v249[8] = v14;
          *(_QWORD *)&v249[16] = v119;
          memset(&v249[24], 0, 32);
          if ( v89 )
            v120 = *v89;
          else
            LOWORD(v120) = 0;
          v121 = v222;
          *(_WORD *)(v119 + 2) = v120;
          *(_QWORD *)(v119 + 16) = v89;
          sqlite3ExprAnalyzeAggList(v249, v121);
          sqlite3ExprAnalyzeAggList(v249, v239);
          v122 = v230;
          v123 = 0;
          if ( v230 )
          {
            if ( v89 )
            {
              v124 = *(_QWORD *)(v4 + 64);
              *(_QWORD *)&v242 = a1;
              *((_QWORD *)&v242 + 1) = havingToWhereExprCb;
              *((_QWORD *)&v243[1] + 1) = v4;
              memset(v243, 0, 24);
              if ( v124 )
              {
                sqlite3WalkExprNN(&v242, v124, 0);
                v122 = v230;
              }
              v236 = *(_QWORD *)(v4 + 48);
            }
            sqlite3ExprAnalyzeAggregates(v249, v122, v123);
          }
          *(_DWORD *)(v119 + 36) = *(_DWORD *)(v119 + 32);
          if ( *(_QWORD *)(v4 + 56)
            || *(_QWORD *)(v4 + 64)
            || *(_DWORD *)(v119 + 48) != 1
            || (v125 = *(__int64 **)(v119 + 40), v126 = *v125, (v127 = *(_DWORD **)(*v125 + 32)) == 0)
            || *v127 != 1
            || (*(_DWORD *)(v126 + 4) & 0x1000000) != 0
            || (*(_DWORD *)(v220 + 96) & 0x10000) != 0 )
          {
            v216 = 0;
          }
          else
          {
            v226 = *(_DWORD **)(v126 + 8);
            if ( (unsigned int)sqlite3StrICmp(v226, "min") )
            {
              if ( !(unsigned int)sqlite3StrICmp(v226, "max") )
              {
                v221 = 1;
                v216 = 2;
                goto LABEL_235;
              }
              v216 = 0;
            }
            else
            {
              v216 = 1;
              v221 = (unsigned int)sqlite3ExprCanBeNull(*(_QWORD *)(v128 + 8)) != 0 ? 2 : 0;
LABEL_235:
              v235 = sqlite3ExprListDup(v220, v129, 0);
              if ( v235 )
                *(_BYTE *)(v235 + 24) = v221;
            }
          }
          analyzeAggFuncArgs(v119, v249);
          v130 = v220;
          if ( !*(_BYTE *)(v220 + 103) )
          {
            if ( v89 )
            {
              v245 = 0;
              v234 = 0;
              if ( *(_DWORD *)(v119 + 48) == 1 )
              {
                v131 = *(int **)(v119 + 40);
                if ( v131[4] >= 0 )
                {
                  v132 = *(_QWORD *)v131;
                  if ( v132 )
                  {
                    if ( (*(_DWORD *)(v132 + 4) & 0x1000) == 0 )
                    {
                      v133 = *(_QWORD *)(v132 + 32);
                      if ( v133 )
                      {
                        v134 = *(_QWORD *)(v133 + 8);
                        if ( v134 )
                        {
                          v135 = exprDup(v220, v134, 0);
                          v130 = v220;
                          v233 = v135;
                        }
                        else
                        {
                          v233 = 0;
                        }
                        v136 = sqlite3ExprListDup(v130, v89, 0);
                        v137 = sqlite3ExprListAppend(a1, v136, v233);
                        v138 = 0;
                        v245 = v137;
                        if ( v137 )
                          v138 = 1280;
                        LOWORD(v234) = v138;
                      }
                    }
                  }
                }
              }
              *(_DWORD *)(v119 + 4) = (*((_DWORD *)a1 + 13))++;
              v139 = (_DWORD *)sqlite3KeyInfoFromExprList(a1, v89, 0, *(unsigned int *)(v119 + 32));
              v140 = *(unsigned __int16 *)(v119 + 2);
              v141 = *(_DWORD *)(v119 + 4);
              v226 = v139;
              v246 = sqlite3VdbeAddOp3(v7, 119, v141, v140, 0);
              sqlite3VdbeChangeP4(v7, v246, v226, 4294967288LL);
              v142 = *((_DWORD *)a1 + 17) - 1;
              v217 = *((_DWORD *)a1 + 14) + 1;
              v228 = v142;
              v143 = v217 + 1;
              v144 = v217 + 3;
              v227 = v217 + 1;
              *((_DWORD *)a1 + 14) = v217 + 3;
              *((_DWORD *)a1 + 17) = v142 - 1;
              v145 = v144 + 1;
              v146 = *v89 + v144;
              *((_DWORD *)a1 + 14) = v146;
              v219 = v146;
              *((_DWORD *)a1 + 14) = *v89 + v146;
              v231 = v145;
              sqlite3VdbeAddOp3(v7, 71, 0, v143, 0);
              sqlite3VdbeAddOp3(v7, 75, 0, v231, *v89 + v227 + 2);
              sqlite3VdbeAddOp3(v7, 10, v227 + 2, v228 - 1, 0);
              v147 = 128;
              if ( (_BYTE)v250 != 2 )
                v147 = 64;
              v233 = sqlite3WhereBegin(
                       (_DWORD)a1,
                       (_DWORD)v14,
                       v236,
                       (_DWORD)v89,
                       v245,
                       v4,
                       (unsigned __int16)v234 | (unsigned __int16)(v147 | ((_WORD)v237 << 9)),
                       0);
              v149 = v233;
              if ( !v233 )
              {
                if ( v245 )
                  exprListDeleteNN(v220, v245);
                goto LABEL_379;
              }
              v232 = v219 + 1;
              if ( a1[12] )
              {
                v150 = *(_DWORD *)(v119 + 36);
                *(_DWORD *)(v119 + 32) = v150;
                if ( *(_WORD *)(v119 + 2) )
                {
                  v151 = **(_DWORD **)(v4 + 56) - 1;
                  if ( v150 > 0 )
                  {
                    for ( k = 0; k < v150; ++k )
                    {
                      v153 = *(__int16 *)(*(_QWORD *)(v119 + 24) + 24LL * (unsigned int)k + 22);
                      if ( v153 <= v151 )
                        v153 = v151;
                      v151 = v153;
                    }
                  }
                  *(_WORD *)(v119 + 2) = v151 + 1;
                }
                analyzeAggFuncArgs(v119, v249);
              }
              v154 = 0;
              *(_DWORD *)(v119 + 12) = *((_DWORD *)a1 + 14) + 1;
              *((_DWORD *)a1 + 14) += *(_DWORD *)(v119 + 32) + *(_DWORD *)(v119 + 48);
              v155 = *(char *)(v149 + 65) < 0;
              v219 = *(unsigned __int8 *)(v149 + 67);
              if ( !v155 )
                v154 = *(char *)(v149 + 65);
              if ( v154 == *v89 )
              {
                v223 = 0;
                TempRange = 0;
                v218 = 0;
              }
              else
              {
                if ( !(_BYTE)v250 || (v156 = "DISTINCT", (*(_BYTE *)(v4 + 4) & 1) != 0) )
                  v156 = "GROUP BY";
                sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s", v156);
                v157 = *v89;
                v158 = v157;
                v218 = 1;
                v223 = v157;
                if ( *(int *)(v119 + 32) > 0 )
                {
                  v159 = 0;
                  v160 = v157;
                  do
                  {
                    v161 = *(__int16 *)(*(_QWORD *)(v119 + 24) + 24LL * v159 + 22);
                    v162 = v158 + 1;
                    if ( v161 < v160 )
                      v162 = v158;
                    ++v159;
                    v158 = v162;
                    v163 = v160 + 1;
                    if ( v161 < v160 )
                      v163 = v160;
                    v160 = v163;
                  }
                  while ( (signed int)v159 < *(_DWORD *)(v119 + 32) );
                  v223 = v158;
                }
                TempRange = sqlite3GetTempRange(a1, v158);
                sqlite3ExprCodeExprList((_DWORD)a1, (_DWORD)v89, TempRange, 0, 0);
                *(_BYTE *)v119 = 1;
                if ( *(int *)(v119 + 32) > 0 )
                {
                  v164 = TempRange;
                  v165 = 0;
                  do
                  {
                    v166 = *(_QWORD *)(v119 + 24);
                    if ( *(__int16 *)(v166 + 24LL * v165 + 22) >= v157 )
                    {
                      sqlite3ExprCode(a1, *(_QWORD *)(v166 + 24LL * v165 + 8), v157 + v164);
                      ++v157;
                    }
                    ++v165;
                  }
                  while ( v165 < *(_DWORD *)(v119 + 32) );
                  LODWORD(v4) = v248;
                  v7 = Vdbe;
                }
                *(_BYTE *)v119 = 0;
                v167 = *((_BYTE *)a1 + 31);
                if ( v167 )
                {
                  v169 = v167 - 1;
                  *((_BYTE *)a1 + 31) = v169;
                  v168 = *((_DWORD *)a1 + v169 + 56);
                }
                else
                {
                  v168 = *((_DWORD *)a1 + 14) + 1;
                  *((_DWORD *)a1 + 14) = v168;
                }
                sqlite3VdbeAddOp3(v7, 97, TempRange, v223, v168);
                sqlite3VdbeAddOp3(v7, 139, *(_DWORD *)(v119 + 4), v168, 0);
                if ( v168 && *((_BYTE *)a1 + 31) < 8u )
                  *((_DWORD *)a1 + (unsigned __int8)(*((_BYTE *)a1 + 31))++ + 56) = v168;
                v170 = v223;
                sqlite3ReleaseTempRange(a1, TempRange, v223);
                sqlite3WhereEnd(v233);
                v171 = *((_DWORD *)a1 + 13);
                *(_DWORD *)(v119 + 8) = v171;
                ++*((_DWORD *)a1 + 13);
                v172 = *((_BYTE *)a1 + 31);
                v223 = v171;
                if ( v172 )
                {
                  v174 = v172 - 1;
                  *((_BYTE *)a1 + 31) = v174;
                  v173 = *((_DWORD *)a1 + v174 + 56);
                }
                else
                {
                  v173 = *((_DWORD *)a1 + 14) + 1;
                  *((_DWORD *)a1 + 14) = v173;
                }
                TempRange = v173;
                sqlite3VdbeAddOp3(v7, 121, v171, v173, v170);
                sqlite3VdbeAddOp3(v7, 34, *(_DWORD *)(v119 + 4), v229, 0);
                *(_BYTE *)(v119 + 1) = 1;
              }
              if ( a1[12] )
              {
                v175 = 0;
                *(_QWORD *)&v242 = 0;
                *((_QWORD *)&v242 + 1) = aggregateIdxEprRefToColCallback;
                memset(v243, 0, sizeof(v243));
                if ( *(int *)(v119 + 48) > 0 )
                {
                  do
                  {
                    v176 = *(_QWORD *)(*(_QWORD *)(v119 + 40) + 24LL * v175);
                    if ( v176 )
                      sqlite3WalkExprNN(&v242, v176, v148);
                    ++v175;
                  }
                  while ( v175 < *(_DWORD *)(v119 + 48) );
                }
              }
              if ( v237 && (*(_BYTE *)(v220 + 96) & 4) == 0 && (v218 || (*(_BYTE *)(v233 + 68) & 8) != 0) )
              {
                *(_QWORD *)&v239 = 0;
                sqlite3VdbeChangeToNoop(v7, DWORD2(v240));
              }
              LODWORD(v236) = *(_DWORD *)(v7 + 144);
              v177 = v218;
              if ( v218 )
              {
                sqlite3VdbeAddOp3(v7, 133, *(_DWORD *)(v119 + 4), TempRange, v223);
                v177 = v218;
              }
              v178 = 0;
              if ( *v89 > 0 )
              {
                v179 = v223;
                do
                {
                  v180 = v178 + v232;
                  if ( v177 )
                  {
                    sqlite3VdbeAddOp3(v7, 94, v179, v178, v180);
                  }
                  else
                  {
                    *(_BYTE *)v119 = 1;
                    sqlite3ExprCode(a1, *(_QWORD *)&v89[8 * v178 + 2], v180);
                  }
                  v177 = v218;
                  ++v178;
                }
                while ( v178 < *v89 );
                LODWORD(v4) = v248;
              }
              v181 = v226;
              if ( v226 )
                ++*v226;
              v182 = sqlite3VdbeAddOp3(v7, 90, v231, v232, *v89);
              sqlite3VdbeChangeP4(v7, v182, v181, 4294967288LL);
              v183 = *(_DWORD *)(v7 + 144);
              sqlite3VdbeAddOp3(v7, 14, v183 + 1, 0, v183 + 1);
              sqlite3VdbeAddOp3(a1[2], 79, v232, v231, *v244);
              v184 = v227;
              sqlite3VdbeAddOp3(v7, 10, v227 + 1, v228, 0);
              sqlite3VdbeAddOp3(v7, 59, v184, v229, 0);
              sqlite3VdbeAddOp3(v7, 10, v184 + 2, v228 - 1, 0);
              sqlite3VdbeJumpHere(v7, v183);
              updateAccumulator(a1, v217, v119, v219);
              sqlite3VdbeAddOp3(v7, 71, 1, v217, 0);
              if ( v218 )
              {
                sqlite3VdbeAddOp3(v7, 37, *(_DWORD *)(v119 + 4), v236, 0);
              }
              else
              {
                sqlite3WhereEnd(v233);
                sqlite3VdbeChangeToNoop(v7, v246);
              }
              if ( v245 )
                exprListDeleteNN(v220, v245);
              sqlite3VdbeAddOp3(v7, 10, v184 + 1, v228, 0);
              sqlite3VdbeAddOp3(v7, 9, 0, v229, 0);
              v185 = *(_DWORD *)(v7 + 144);
              v109 = Vdbe;
              sqlite3VdbeAddOp3(Vdbe, 71, 1, v227, 0);
              v186 = v227 + 1;
              sqlite3VdbeAddOp3(v109, 67, v227 + 1, 0, 0);
              sqlite3VdbeResolveLabel(v109, v228);
              v187 = *(_DWORD *)(v109 + 144);
              sqlite3VdbeAddOp3(v109, 59, v217, v187 + 2, 0);
              sqlite3VdbeAddOp3(v109, 67, v186, 0, 0);
              finalizeAggFunctions(a1, v119);
              sqlite3ExprIfFalse(a1, v230, (unsigned int)++v187, 16);
              v215 = v187;
              v106 = v238;
              selectInnerLoop((_DWORD)a1, v4, -1, (unsigned int)&v239, (__int64)&v250, (__int64)v238, v215, v185);
              sqlite3VdbeAddOp3(v109, 67, v186, 0, 0);
              sqlite3VdbeResolveLabel(v109, v228 - 1);
              resetAccumulator(a1, v119);
              sqlite3VdbeAddOp3(v109, 71, 0, v217, 0);
              sqlite3VdbeAddOp3(v109, 67, v186 + 1, 0, 0);
              if ( (_WORD)v234 && v219 )
                fixDistinctOpenEph(
                  a1,
                  v219,
                  *(unsigned int *)(*(_QWORD *)(v119 + 40) + 16LL),
                  *(unsigned int *)(*(_QWORD *)(v119 + 40) + 20LL));
            }
            else
            {
              if ( !*(_QWORD *)(v4 + 48)
                && (v188 = *(_QWORD *)(v4 + 32), *(_DWORD *)v188 == 1)
                && (v189 = *(_QWORD *)(v4 + 40), *(_DWORD *)v189 == 1)
                && !*(_QWORD *)(v189 + 48)
                && *(_DWORD *)(v119 + 48) == 1
                && !*(_QWORD *)(v4 + 64)
                && (v190 = *(_QWORD **)(v189 + 40), !*((_BYTE *)v190 + 63))
                && (v191 = *(_QWORD *)(v188 + 8), *(_BYTE *)v191 == 0xA8)
                && *(_QWORD *)(v191 + 56) == v119
                && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v119 + 40) + 8LL) + 4LL) & 0x100) != 0
                && (*(_DWORD *)(v191 + 4) & 0x1000004) == 0
                && v190 )
              {
                v192 = v190[12];
                if ( v192 )
                {
                  v193 = 0;
                  v194 = *(_QWORD *)(*a1 + 32LL);
                  if ( *(_QWORD *)(v194 + 24) != v192 )
                  {
                    do
                      ++v193;
                    while ( *(_QWORD *)(32LL * v193 + v194 + 24) != v192 );
                  }
                }
                else
                {
                  v193 = -32768;
                }
                v217 = *((_DWORD *)a1 + 13);
                v226 = 0;
                *((_DWORD *)a1 + 13) = v217 + 1;
                m = 0;
                v219 = *((_DWORD *)v190 + 10);
                sqlite3CodeVerifySchema(a1, (unsigned int)v193);
                sqlite3TableLock((_DWORD)a1, v193, *((_DWORD *)v190 + 10), 0, *v190);
                if ( *((char *)v190 + 48) < 0 )
                {
                  for ( m = v190[2]; m && (*(_DWORD *)(m + 100) & 3) != 2; m = *(_QWORD *)(m + 40) )
                    ;
                }
                if ( (*(_BYTE *)(*(_QWORD *)(v4 + 40) + 72LL) & 1) == 0 )
                {
                  for ( n = v190[2]; n; n = *(_QWORD *)(n + 40) )
                  {
                    if ( (*(_BYTE *)(n + 100) & 4) == 0 )
                    {
                      v197 = *(_WORD *)(n + 92);
                      if ( v197 < *((__int16 *)v190 + 30) && !*(_QWORD *)(n + 72) && (!m || v197 < *(__int16 *)(m + 92)) )
                        m = n;
                    }
                  }
                }
                if ( m )
                {
                  v219 = *(_DWORD *)(m + 88);
                  v226 = (_DWORD *)sqlite3KeyInfoOfIndex(a1, m);
                }
                v214 = v193;
                v109 = Vdbe;
                sqlite3VdbeAddOp4Int(Vdbe, 112, v217, v219, v214, 1);
                if ( v226 )
                  sqlite3VdbeChangeP4(v109, 0xFFFFFFFFLL, v226, 4294967288LL);
                v198 = v217;
                *(_DWORD *)(v119 + 12) = *((_DWORD *)a1 + 14) + 1;
                *((_DWORD *)a1 + 14) += *(_DWORD *)(v119 + 32) + *(_DWORD *)(v119 + 48);
                sqlite3VdbeAddOp3(v109, 98, v198, *(_DWORD *)(v119 + 12) + *(_DWORD *)(v119 + 32), 0);
                sqlite3VdbeAddOp3(v109, 122, v217, 0, 0);
                if ( *((_BYTE *)a1 + 299) == 2 )
                {
                  if ( !m || *((char *)v190 + 48) < 0 && (*(_DWORD *)(m + 100) & 3) == 2 )
                  {
                    v8 = 0;
                    v199 = &dword_1400ACDEC;
                  }
                  else
                  {
                    v199 = *(const unsigned __int16 **)m;
                  }
                  v200 = " USING COVERING INDEX ";
                  if ( !v8 )
                    v200 = (const char *)&dword_1400ACDEC;
                  sqlite3VdbeExplain(a1, 0, "SCAN %s%s%s", *v190, v200, v199);
                }
              }
              else
              {
                v201 = 0;
                v202 = *(_DWORD *)(v119 + 48);
                v203 = 0;
                v226 = 0;
                if ( *(_DWORD *)(v119 + 36) )
                {
                  v204 = 0;
                  if ( v202 <= 0 )
                  {
LABEL_388:
                    if ( v204 == v202 )
                    {
                      v201 = ++*((_DWORD *)a1 + 14);
                      sqlite3VdbeAddOp3(Vdbe, 71, 0, v201, 0);
                    }
                  }
                  else
                  {
                    v205 = *(_QWORD *)(v119 + 40);
                    while ( (*(_DWORD *)(*(_QWORD *)(v205 + 24LL * v204) + 4LL) & 0x1000000) != 0
                         || (*(_BYTE *)(*(_QWORD *)(v205 + 24LL * v204 + 8) + 4LL) & 0x20) == 0 )
                    {
                      if ( (int)++v204 >= v202 )
                        goto LABEL_388;
                    }
                  }
                }
                else if ( v202 == 1 )
                {
                  v206 = *(int **)(v119 + 40);
                  if ( v206[4] >= 0 )
                  {
                    v226 = *(_DWORD **)(*(_QWORD *)v206 + 32LL);
                    if ( v226 )
                      v203 = 1280;
                  }
                }
                *(_DWORD *)(v119 + 12) = *((_DWORD *)a1 + 14) + 1;
                *((_DWORD *)a1 + 14) += *(_DWORD *)(v119 + 32) + *(_DWORD *)(v119 + 48);
                resetAccumulator(a1, v119);
                v207 = sqlite3WhereBegin((_DWORD)a1, (_DWORD)v14, v236, v235, (__int64)v226, v4, v203 | v216, 0);
                v208 = v207;
                if ( !v207 )
                  goto LABEL_379;
                v209 = *(unsigned __int8 *)(v207 + 67);
                updateAccumulator(a1, v201, v119, *(unsigned __int8 *)(v207 + 67));
                if ( v209 )
                {
                  v210 = *(_QWORD *)(v119 + 40);
                  if ( v210 )
                    fixDistinctOpenEph(a1, v209, *(unsigned int *)(v210 + 16), *(unsigned int *)(v210 + 20));
                }
                v109 = Vdbe;
                if ( v201 )
                  sqlite3VdbeAddOp3(Vdbe, 71, 1, v201, 0);
                if ( v216 && (*(_BYTE *)(v208 + 68) & 4) != 0 && *(_BYTE *)(v208 + 65) )
                {
                  v211 = *(unsigned __int8 *)(v208 + 64);
                  do
                  {
                    if ( (--v211 & 0x80000000) != 0 )
                    {
                      v213 = *(_DWORD *)(v208 + 52);
                      goto LABEL_407;
                    }
                    v212 = 112LL * v211;
                  }
                  while ( (*(_BYTE *)(*(_QWORD *)(v212 + v208 + 960) + 56LL) & 4) == 0 );
                  v213 = *(_DWORD *)(v212 + v208 + 880);
LABEL_407:
                  sqlite3VdbeAddOp3(v109, 9, 0, v213, 0);
                }
                sqlite3WhereEnd(v208);
                finalizeAggFunctions(a1, v119);
              }
              *(_QWORD *)&v239 = 0;
              sqlite3ExprIfFalse(a1, v230, v229, 16);
              v106 = v238;
              selectInnerLoop((_DWORD)a1, v4, -1, 0, 0, (__int64)v238, v229, v229);
            }
            v107 = v229;
            v108 = v109;
LABEL_373:
            sqlite3VdbeResolveLabel(v108, v107);
            goto LABEL_374;
          }
LABEL_380:
          if ( v235 )
            exprListDeleteNN(v130, v235);
          goto LABEL_14;
        }
        v17 = 26LL * v6;
        v18 = v14[v17 + 17];
        v19 = *(int **)&v14[v17 + 12];
        v20 = *(const char ***)&v14[v17 + 10];
        v222 = v19;
        v230 = v20;
        if ( (v18 & 0x48) != 0 )
        {
          v21 = sqlite3ExprImpliesNonNullRow(*(_QWORD *)(v4 + 48), (unsigned int)v14[v17 + 19], v18 & 0x40);
          v16 = v220;
          if ( v21 && (*(_DWORD *)(v220 + 96) & 0x2000) == 0 )
          {
            v22 = v14[v17 + 17];
            if ( (v22 & 8) != 0 )
            {
              if ( (v22 & 0x10) != 0 )
                v22 &= ~8u;
              else
                v22 &= 0xD7u;
              LOBYTE(v14[v17 + 17]) = v22;
            }
            if ( (v22 & 0x40) != 0 )
            {
              for ( ii = v6 + 1; ii < *v14; ++ii )
              {
                v24 = 26LL * ii;
                v25 = v14[v24 + 17];
                if ( (v25 & 0x10) != 0 )
                {
                  if ( (v25 & 8) != 0 )
                    v26 = v25 & 0xEF;
                  else
                    v26 = v25 & 0xCF;
                  LOBYTE(v14[v24 + 17]) = v26;
                }
              }
              for ( jj = *v14 - 1; jj >= v6; --jj )
              {
                v28 = 26LL * jj;
                LOBYTE(v14[v28 + 17]) &= ~0x40u;
                if ( (v14[v28 + 17] & 0x10) != 0 )
                  break;
              }
            }
            unsetJoinExpr(*(_QWORD *)(v4 + 48), (unsigned int)v14[v17 + 19], v14[17] & 0x40);
          }
          v19 = v222;
          v20 = (const char **)v230;
        }
        if ( v19 )
        {
          v29 = *((__int16 *)v20 + 27);
          v30 = **((_DWORD **)v19 + 4);
          if ( v29 != v30 )
          {
            sqlite3ErrorMsg(a1, "expected %d columns for '%s' but got %d", v29, *v20, v30);
            goto LABEL_14;
          }
          if ( ((v14[v17 + 18] & 0x100) == 0 || *(_BYTE *)(*(_QWORD *)&v14[v17 + 26] + 18LL)) && (v19[1] & 8) == 0 )
          {
            v31 = *((_QWORD *)v19 + 9);
            if ( v31 )
            {
              if ( !*(_QWORD *)(v4 + 72) && *v14 <= 1
                || *((_QWORD *)v19 + 12)
                || (v19[1] & 0x8000000) != 0
                || (*(_DWORD *)(v4 + 4) & 0x8000000) != 0
                || (*(_DWORD *)(v16 + 96) & 0x40000) != 0 )
              {
                if ( !v6 && (*(_DWORD *)(v4 + 4) & 0x40000) != 0 && (*v14 == 1 || (v14[43] & 0x22) != 0) )
                  goto LABEL_68;
              }
              else
              {
                sqlite3ParserAddCleanup(a1, sqlite3ExprListDelete, v31);
                *((_QWORD *)v222 + 9) = 0;
              }
            }
            if ( (unsigned int)flattenSubquery(a1, v4, (unsigned int)v6, v219) )
            {
              if ( *((_DWORD *)a1 + 12) )
                goto LABEL_14;
              v6 = -1;
            }
            v16 = v220;
            if ( *(_BYTE *)(v220 + 103) )
              goto LABEL_14;
            v14 = *(signed int **)(v4 + 40);
            if ( *(_BYTE *)v238 > 8u )
              *(_QWORD *)&v239 = *(_QWORD *)(v4 + 72);
          }
        }
LABEL_68:
        ++v6;
      }
      while ( !*(_QWORD *)(v4 + 80) );
    }
    v32 = multiSelect(a1, (unsigned __int8 *)v4, v238);
    if ( !*(_QWORD *)(v4 + 88) )
      sqlite3VdbeExplainPop(a1);
    return v32;
  }
}

```

## disassembly

```asm
0x14006cd0c  mov     [rsp-8+arg_18], rbx
0x14006cd11  push    rbp
0x14006cd12  push    rsi
0x14006cd13  push    rdi
0x14006cd14  push    r12
0x14006cd16  push    r13
0x14006cd18  push    r14
0x14006cd1a  push    r15
0x14006cd1c  lea     rbp, [rsp-0A0h]
0x14006cd24  sub     rsp, 1A0h
0x14006cd2b  mov     rax, cs:__security_cookie
0x14006cd32  xor     rax, rsp
0x14006cd35  mov     [rbp+0D0h+var_38], rax
0x14006cd3c  xor     eax, eax
0x14006cd3e  mov     [rbp+0D0h+var_108], r8
0x14006cd42  xorps   xmm0, xmm0
0x14006cd45  mov     [rbp+0D0h+var_48], rax
0x14006cd4c  mov     [rbp+0D0h+var_40], eax
0x14006cd52  mov     r14, r8
0x14006cd55  mov     rax, [rcx]
0x14006cd58  mov     r13, rdx
0x14006cd5b  mov     [rsp+1D0h+var_180], rax
0x14006cd60  mov     r15, rcx
0x14006cd63  mov     [rbp+0D0h+var_88], rdx
0x14006cd67  movups  [rbp+0D0h+var_100], xmm0
0x14006cd6b  movups  [rbp+0D0h+var_F0], xmm0
0x14006cd6f  movups  [rbp+0D0h+var_E0], xmm0
0x14006cd73  call    sqlite3GetVdbe
0x14006cd78  xor     esi, esi
0x14006cd7a  mov     [rsp+1D0h+var_160], rax
0x14006cd7f  mov     rdi, rax
0x14006cd82  test    r13, r13
0x14006cd85  jz      loc_14006EBC6
0x14006cd8b  cmp     [r15+30h], esi
0x14006cd8f  jnz     loc_14006EBC6
0x14006cd95  xor     r9d, r9d
0x14006cd98  mov     [rsp+1D0h+var_1B0], rsi
0x14006cd9d  xor     r8d, r8d
0x14006cda0  lea     edx, [rsi+15h]
0x14006cda3  mov     rcx, r15
0x14006cda6  call    sqlite3AuthCheck
0x14006cdab  test    eax, eax
0x14006cdad  jnz     loc_14006EBC6
0x14006cdb3  cmp     byte ptr [r14], 6
0x14006cdb7  lea     r12d, [rsi+1]
0x14006cdbb  ja      short loc_14006CDE4
0x14006cdbd  mov     r8, [r13+48h]
0x14006cdc1  test    r8, r8
0x14006cdc4  jz      short loc_14006CDD9
0x14006cdc6  lea     rdx, sqlite3ExprListDelete
0x14006cdcd  mov     rcx, r15
0x14006cdd0  call    sqlite3ParserAddCleanup
0x14006cdd5  mov     [r13+48h], rsi
0x14006cdd9  and     dword ptr [r13+4], 0FFFFFFFEh
0x14006cdde  bts     dword ptr [r13+4], 16h
0x14006cde4  xor     r8d, r8d
0x14006cde7  mov     rdx, r13
0x14006cdea  mov     rcx, r15
0x14006cded  call    sqlite3SelectPrep
0x14006cdf2  cmp     [r15+30h], esi
0x14006cdf6  jnz     short loc_14006CE35
0x14006cdf8  mov     ebx, [r13+4]
0x14006cdfc  bt      ebx, 17h
0x14006ce00  jnb     short loc_14006CE4F
0x14006ce02  mov     rdx, [r13+28h]
0x14006ce06  lea     rsi, [rdx+8]
0x14006ce0a  mov     rcx, rsi
0x14006ce0d  call    sameSrcAlias
0x14006ce12  test    eax, eax
0x14006ce14  jz      short loc_14006CE45
0x14006ce16  mov     r8, [rsi+18h]
0x14006ce1a  test    r8, r8
0x14006ce1d  jnz     short loc_14006CE26
0x14006ce1f  mov     rax, [rsi+20h]
0x14006ce23  mov     r8, [rax]
0x14006ce26  lea     rdx, aTargetObjectAl; "target object/alias may not appear in F"...
0x14006ce2d  mov     rcx, r15
0x14006ce30  call    sqlite3ErrorMsg
0x14006ce35  mov     rcx, r15
0x14006ce38  call    sqlite3VdbeExplainPop
0x14006ce3d  mov     eax, r12d
0x14006ce40  jmp     loc_14006EBCB
0x14006ce45  btr     ebx, 17h
0x14006ce49  mov     [r13+4], ebx
0x14006ce4d  xor     esi, esi
0x14006ce4f  cmp     byte ptr [r14], 9
0x14006ce53  jnz     short loc_14006CE60
0x14006ce55  mov     rdx, r13
0x14006ce58  mov     rcx, r15
0x14006ce5b  call    sqlite3GenerateColumnNames
0x14006ce60  mov     rdx, r13
0x14006ce63  mov     rcx, r15
0x14006ce66  call    sqlite3WindowRewrite
0x14006ce6b  test    eax, eax
0x14006ce6d  jnz     short loc_14006CE35
0x14006ce6f  mov     eax, [r13+4]
0x14006ce73  xorps   xmm0, xmm0
0x14006ce76  mov     r14, [r13+28h]
0x14006ce7a  and     eax, 8
0x14006ce7d  mov     [rbp+0D0h+var_138], eax
0x14006ce80  mov     eax, esi
0x14006ce82  setnz   al
0x14006ce85  xor     ecx, ecx
0x14006ce87  mov     [rsp+1D0h+var_184], eax
0x14006ce8b  mov     rax, [r13+48h]
0x14006ce8f  movups  [rbp+0D0h+var_100], xmm0
0x14006ce93  mov     qword ptr [rbp+0D0h+var_100], rax
0x14006ce97  movups  [rbp+0D0h+var_F0], xmm0
0x14006ce9b  movups  [rbp+0D0h+var_E0], xmm0
0x14006ce9f  cmp     [r13+50h], rcx
0x14006cea3  jnz     loc_14006D0BB
0x14006cea9  mov     r10, [rsp+1D0h+var_180]
0x14006ceae  mov     r11d, 100h
0x14006ceb4  mov     edx, 40h ; '@'
0x14006ceb9  cmp     esi, [r14]
0x14006cebc  jge     loc_14006D0FF
0x14006cec2  movsxd  rax, esi
0x14006cec5  imul    rbx, rax, 68h ; 'h'
0x14006cec9  movzx   eax, byte ptr [rbx+r14+44h]
0x14006cecf  mov     rcx, [rbx+r14+30h]
0x14006ced4  mov     r9, [rbx+r14+28h]
0x14006ced9  mov     [rsp+1D0h+var_170], rcx
0x14006cede  mov     [rbp+0D0h+var_140], r9
0x14006cee2  test    al, 48h
0x14006cee4  jz      loc_14006CFB7
0x14006ceea  mov     rcx, [r13+30h]
0x14006ceee  mov     r8d, eax
0x14006cef1  and     r8d, edx
0x14006cef4  mov     edx, [rbx+r14+4Ch]
0x14006cef9  call    sqlite3ExprImpliesNonNullRow
0x14006cefe  mov     r10, [rsp+1D0h+var_180]
0x14006cf03  test    eax, eax
0x14006cf05  jz      loc_14006CFA8
0x14006cf0b  test    dword ptr [r10+60h], 2000h
0x14006cf13  jnz     loc_14006CFA8
0x14006cf19  mov     al, [rbx+r14+44h]
0x14006cf1e  mov     r8d, 8
0x14006cf24  test    r8b, al
0x14006cf27  jz      short loc_14006CF38
0x14006cf29  test    al, 10h
0x14006cf2b  jz      short loc_14006CF31
0x14006cf2d  and     al, 0F7h
0x14006cf2f  jmp     short loc_14006CF33
0x14006cf31  and     al, 0D7h
0x14006cf33  mov     [rbx+r14+44h], al
0x14006cf38  mov     r9d, 40h ; '@'
0x14006cf3e  test    r9b, al
0x14006cf41  jz      short loc_14006CF92
0x14006cf43  lea     ecx, [rsi+1]
0x14006cf46  jmp     short loc_14006CF6B
0x14006cf48  movsxd  rax, ecx
0x14006cf4b  imul    rdx, rax, 68h ; 'h'
0x14006cf4f  mov     al, [rdx+r14+44h]
0x14006cf54  test    al, 10h
0x14006cf56  jz      short loc_14006CF68
0x14006cf58  test    r8b, al
0x14006cf5b  jz      short loc_14006CF61
0x14006cf5d  and     al, 0EFh
0x14006cf5f  jmp     short loc_14006CF63
0x14006cf61  and     al, 0CFh
0x14006cf63  mov     [rdx+r14+44h], al
0x14006cf68  add     ecx, r12d
0x14006cf6b  mov     edx, [r14]
0x14006cf6e  cmp     ecx, edx
0x14006cf70  jl      short loc_14006CF48
0x14006cf72  dec     edx
0x14006cf74  jmp     short loc_14006CF8E
0x14006cf76  movsxd  rax, edx
0x14006cf79  imul    rcx, rax, 68h ; 'h'
0x14006cf7d  and     byte ptr [rcx+r14+44h], 0BFh
0x14006cf83  test    byte ptr [rcx+r14+44h], 10h
0x14006cf89  jnz     short loc_14006CF92
0x14006cf8b  sub     edx, r12d
0x14006cf8e  cmp     edx, esi
0x14006cf90  jge     short loc_14006CF76
0x14006cf92  movzx   r8d, byte ptr [r14+44h]
0x14006cf97  mov     edx, [rbx+r14+4Ch]
0x14006cf9c  and     r8d, r9d
0x14006cf9f  mov     rcx, [r13+30h]
0x14006cfa3  call    unsetJoinExpr
0x14006cfa8  mov     rcx, [rsp+1D0h+var_170]
0x14006cfad  mov     r11d, 100h
0x14006cfb3  mov     r9, [rbp+0D0h+var_140]
0x14006cfb7  test    rcx, rcx
0x14006cfba  jz      loc_14006D0AC
0x14006cfc0  mov     rax, [rcx+20h]
0x14006cfc4  movsx   r8d, word ptr [r9+36h]
0x14006cfc9  mov     edx, [rax]
0x14006cfcb  cmp     r8d, edx
0x14006cfce  jnz     loc_14006D0E4
0x14006cfd4  test    [rbx+r14+48h], r11d
0x14006cfd9  jz      short loc_14006CFED
0x14006cfdb  mov     rax, [rbx+r14+68h]
0x14006cfe0  xor     ebx, ebx
0x14006cfe2  cmp     [rax+12h], bl
0x14006cfe5  jz      loc_14006D0AC
0x14006cfeb  jmp     short loc_14006CFEF
0x14006cfed  xor     ebx, ebx
0x14006cfef  test    byte ptr [rcx+4], 8
0x14006cff3  jnz     loc_14006D0AC
0x14006cff9  mov     r8, [rcx+48h]
0x14006cffd  test    r8, r8
0x14006d000  jz      short loc_14006D064
0x14006d002  cmp     [r13+48h], rbx
0x14006d006  jnz     short loc_14006D00D
0x14006d008  cmp     [r14], r12d
0x14006d00b  jle     short loc_14006D047
0x14006d00d  cmp     [rcx+60h], rbx
0x14006d011  jnz     short loc_14006D047
0x14006d013  mov     eax, 8000000h
0x14006d018  test    [rcx+4], eax
0x14006d01b  jnz     short loc_14006D047
0x14006d01d  test    [r13+4], eax
0x14006d021  jnz     short loc_14006D047
0x14006d023  test    dword ptr [r10+60h], 40000h
0x14006d02b  jnz     short loc_14006D047
0x14006d02d  lea     rdx, sqlite3ExprListDelete
0x14006d034  mov     rcx, r15
0x14006d037  call    sqlite3ParserAddCleanup
0x14006d03c  mov     rax, [rsp+1D0h+var_170]
0x14006d041  mov     [rax+48h], rbx
0x14006d045  jmp     short loc_14006D064
0x14006d047  test    esi, esi
0x14006d049  jnz     short loc_14006D064
0x14006d04b  test    dword ptr [r13+4], 40000h
0x14006d053  jz      short loc_14006D064
0x14006d055  cmp     [r14], r12d
0x14006d058  jz      short loc_14006D0AC
0x14006d05a  test    byte ptr [r14+0ACh], 22h
0x14006d062  jnz     short loc_14006D0AC
0x14006d064  mov     r9d, [rsp+1D0h+var_184]
0x14006d069  mov     r8d, esi
0x14006d06c  mov     rdx, r13
0x14006d06f  mov     rcx, r15
0x14006d072  call    flattenSubquery
0x14006d077  test    eax, eax
0x14006d079  jz      short loc_14006D088
0x14006d07b  cmp     [r15+30h], ebx
0x14006d07f  jnz     loc_14006CE35
0x14006d085  or      esi, 0FFFFFFFFh
0x14006d088  mov     r10, [rsp+1D0h+var_180]
0x14006d08d  cmp     [r10+67h], bl
0x14006d091  jnz     loc_14006CE35
0x14006d097  mov     rax, [rbp+0D0h+var_108]
0x14006d09b  mov     r14, [r13+28h]
0x14006d09f  cmp     byte ptr [rax], 8
0x14006d0a2  jbe     short loc_14006D0AC
0x14006d0a4  mov     rax, [r13+48h]
0x14006d0a8  mov     qword ptr [rbp+0D0h+var_100], rax
0x14006d0ac  add     esi, r12d
0x14006d0af  xor     ecx, ecx
0x14006d0b1  cmp     [r13+50h], rcx
0x14006d0b5  jz      loc_14006CEAE
0x14006d0bb  mov     r8, [rbp+0D0h+var_108]
0x14006d0bf  mov     rdx, r13
0x14006d0c2  mov     rcx, r15
0x14006d0c5  call    multiSelect
0x14006d0ca  cmp     qword ptr [r13+58h], 0
0x14006d0cf  mov     r9d, eax
0x14006d0d2  jnz     short loc_14006D0DC
0x14006d0d4  mov     rcx, r15
0x14006d0d7  call    sqlite3VdbeExplainPop
0x14006d0dc  mov     eax, r9d
0x14006d0df  jmp     loc_14006EBCB
0x14006d0e4  mov     r9, [r9]
0x14006d0e7  mov     rcx, r15
0x14006d0ea  mov     dword ptr [rsp+1D0h+var_1B0], edx
0x14006d0ee  lea     rdx, aExpectedDColum; "expected %d columns for '%s' but got %d"
0x14006d0f5  call    sqlite3ErrorMsg
0x14006d0fa  jmp     loc_14006CE35
0x14006d0ff  mov     rax, [r13+30h]
0x14006d103  test    rax, rax
0x14006d106  jz      short loc_14006D124
0x14006d108  cmp     byte ptr [rax], 2Ch ; ','
0x14006d10b  jnz     short loc_14006D124
0x14006d10d  test    dword ptr [r10+60h], 8000h
0x14006d115  jnz     short loc_14006D124
0x14006d117  mov     rdx, r13
0x14006d11a  mov     rcx, r15
0x14006d11d  call    propagateConstants
0x14006d122  xor     ecx, ecx
0x14006d124  mov     rsi, [rsp+1D0h+var_180]
0x14006d129  test    dword ptr [rsi+60h], 201h
0x14006d130  jnz     short loc_14006D150
0x14006d132  mov     rdx, r13
0x14006d135  mov     rcx, r15
0x14006d138  call    countOfViewOptimization
0x14006d13d  xor     ecx, ecx
0x14006d13f  test    eax, eax
0x14006d141  jz      short loc_14006D150
0x14006d143  cmp     [rsi+67h], cl
0x14006d146  jnz     loc_14006CE35
0x14006d14c  mov     r14, [r13+28h]
0x14006d150  lea     rdx, dword_1400ACDEC
0x14006d157  mov     r11d, ecx
0x14006d15a  mov     [rsp+1D0h+var_188], ecx
0x14006d15e  cmp     [r14], ecx
0x14006d161  jle     loc_14006D64D
0x14006d167  movsxd  rax, r11d
0x14006d16a  xorps   xmm0, xmm0
  ... truncated ...
```
