# yy_reduce

- ea: `0x1400a40bc`
- end: `0x1400a6f50`
- name: `yy_reduce`
- size: `11924`
- prototype: ``
- caller_count: `1`
- callee_count: `101`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x140065c88`

## callees

- `0x140022838`
- `0x140028058`
- `0x14002b010`
- `0x14002b178`
- `0x14003f14c`
- `0x14003f1bc`
- `0x14004943c`
- `0x14004953c`
- `0x1400495f4`
- `0x140049964`
- `0x140049aa8`
- `0x140049c4c`
- `0x140049cc0`
- `0x140049f6c`
- `0x14004a22c`
- `0x14004a40c`
- `0x14004a928`
- `0x14004acbc`
- `0x14004af6c`
- `0x14004b3f8`
- `0x14004bd88`
- `0x14004c148`
- `0x14004c220`
- `0x1400526c8`
- `0x140052db4`
- `0x140053b3c`
- `0x140053d8c`
- `0x140053fec`
- `0x1400541ec`
- `0x140054474`
- `0x140055090`
- `0x140055158`
- `0x140055194`
- `0x140055380`
- `0x140055620`
- `0x140055854`
- `0x140055f9c`
- `0x1400560c4`
- `0x140056260`
- `0x1400563f0`
- `0x14005659c`
- `0x140056644`
- `0x140056828`
- `0x140059030`
- `0x14005904c`
- `0x140059194`
- `0x140059248`
- `0x140059c88`
- `0x140059de8`
- `0x140059fa0`

## string_xrefs

- `0x1400a63c2`: `the INDEXED BY clause is not allowed on UPDATE or DELETE statements within triggers`
- `0x1400a63a6`: `qualified table names are not allowed on INSERT, UPDATE, and DELETE statements within triggers`
- `0x1400a63cb`: `the NOT INDEXED clause is not allowed on UPDATE or DELETE statements within triggers`

## pseudocode

```c
__int64 __fastcall yy_reduce(__int64 *a1, unsigned int a2, __int64 a3, __int64 *a4, _QWORD *a5)
{
  __int64 v5; // r12
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // r13d
  _QWORD *v9; // rbx
  __int64 v10; // rdx
  const char *v11; // r9
  int v12; // r8d
  __int128 v13; // xmm1
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rbx
  __int64 v34; // rdx
  __int64 v35; // rbx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdi
  __int64 v39; // rdx
  int v40; // eax
  __int64 updated; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rdi
  __int64 v45; // rbx
  __int64 v46; // rax
  __int64 v47; // rbx
  __int64 appended; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // r8
  _QWORD *v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  _QWORD *v59; // rcx
  int *v60; // rdx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  _DWORD *v64; // rdx
  int *v65; // rax
  int *v66; // r8
  __int64 v67; // rdx
  __int64 v68; // r9
  __int64 v69; // rax
  __int64 v70; // rax
  _OWORD *v71; // rsi
  __int64 v72; // rdi
  unsigned __int8 v73; // al
  __int64 v74; // r14
  __int64 v75; // rax
  __int64 v76; // rdi
  unsigned __int8 v77; // al
  __int64 v78; // r15
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rbx
  __int64 v82; // r9
  __int64 v83; // rax
  __int64 v84; // r13
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rax
  __int64 v89; // rdx
  __int64 v90; // r8
  __int64 v91; // r8
  _DWORD *v92; // rdx
  int *v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // r13
  __int64 inserted; // rax
  __int64 v99; // rdx
  __int64 v100; // rbx
  __int64 v101; // rdx
  __int64 v102; // r8
  _QWORD *v103; // rcx
  __int64 v104; // r14
  __int64 v105; // rbx
  _QWORD *v106; // rcx
  __int64 v107; // r8
  __int64 v108; // rdx
  _QWORD *v109; // rcx
  _QWORD *v110; // rbx
  __int64 v111; // rax
  _BYTE *v112; // rax
  __int64 v113; // rax
  unsigned int v114; // ebx
  __int64 v115; // rax
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // r8
  __int64 v119; // rbx
  __int64 v120; // rbx
  __int64 v121; // rbx
  __int64 v122; // rax
  int v123; // ebx
  __int64 v124; // r8
  __int64 v125; // rax
  __int64 v126; // rax
  __int64 v127; // rax
  int v128; // ebx
  __int64 v129; // r8
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // rax
  _QWORD *v133; // rdi
  __int64 v134; // rax
  __int64 v135; // rbx
  _BYTE *v136; // rax
  __int64 v137; // rcx
  __int64 v138; // rdx
  _QWORD *v139; // rdi
  __int64 v140; // rax
  _BYTE *v141; // rax
  __int64 v142; // rax
  __int64 v143; // rax
  _QWORD *v144; // rbx
  __int64 v145; // rax
  __int64 v146; // rdi
  __int64 v147; // rax
  __int64 v148; // rax
  __int64 v149; // rdi
  const char *v150; // r8
  __int64 v151; // rax
  __int64 v152; // rsi
  _QWORD *v153; // rdi
  __int64 v154; // rdx
  __int64 v155; // rax
  __int64 v156; // rax
  __int64 v157; // rdx
  __int64 v158; // rdx
  __int64 v159; // rax
  __int64 v160; // rsi
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // r8
  __int64 v164; // rsi
  __int64 v165; // rax
  __int64 v166; // rdi
  __int64 v167; // rax
  __int64 v168; // rax
  __int64 v169; // rdx
  __int64 v170; // r8
  __int64 v171; // rax
  __int64 v172; // rax
  __int64 v173; // r8
  int v174; // edi
  void *v175; // rsi
  int v176; // r14d
  int *v177; // r15
  __int64 v178; // rax
  _QWORD *v179; // rdx
  __int64 v180; // rdx
  __int64 v181; // r8
  __int64 v182; // r9
  __int64 v183; // rdx
  __int64 v184; // r9
  __int64 v185; // r8
  __int64 v186; // rdx
  __int64 v187; // rdx
  __int64 v188; // rax
  __int64 v189; // rax
  __int64 v190; // r8
  __int64 v191; // rdx
  __int64 v192; // r8
  __int64 v193; // rdx
  __int64 v194; // rdx
  _QWORD *v195; // rbx
  unsigned __int16 v196; // di
  __int64 v197; // rax
  __int64 v198; // rbx
  __int64 result; // rax
  _WORD *v200; // rcx
  __int64 v201; // r9
  __int64 v202; // r8
  __int64 v203; // rcx
  char v204; // al
  __int64 v205; // rax
  __int64 v206; // rdx
  __int64 v207; // rax
  __int64 v208; // rbx
  __int64 v209; // rax
  __int128 v210; // [rsp+68h] [rbp-31h] BYREF
  __int128 v211; // [rsp+78h] [rbp-21h] BYREF
  char v212; // [rsp+88h] [rbp-11h] BYREF
  __int16 v213; // [rsp+89h] [rbp-10h]
  char v214; // [rsp+8Bh] [rbp-Eh]
  __int128 v215; // [rsp+8Ch] [rbp-Dh]
  int v216; // [rsp+9Ch] [rbp+3h]
  __int128 v217; // [rsp+A0h] [rbp+7h]

  v5 = *a1;
  switch ( a2 )
  {
    case 0u:
      if ( !a5[41] )
        *((_BYTE *)a5 + 299) = 1;
      goto LABEL_441;
    case 1u:
      if ( !a5[41] )
        *((_BYTE *)a5 + 299) = 2;
      goto LABEL_441;
    case 2u:
      sqlite3FinishCoding(a5);
      goto LABEL_441;
    case 3u:
      sqlite3BeginTransaction(a5, *(unsigned int *)(v5 - 16));
      goto LABEL_441;
    case 4u:
      *(_DWORD *)(v5 + 32) = 7;
      goto LABEL_441;
    case 5u:
    case 6u:
    case 7u:
    case 0x59u:
    case 0x5Bu:
    case 0x102u:
    case 0x13Fu:
      *(_DWORD *)(v5 + 8) = *(unsigned __int16 *)(v5 + 2);
      goto LABEL_441;
    case 8u:
    case 9u:
      sqlite3EndTransaction(a5, *(unsigned __int16 *)(v5 - 22));
      goto LABEL_441;
    case 0xAu:
      v6 = 0;
      goto LABEL_12;
    case 0xBu:
      v6 = 1;
      goto LABEL_12;
    case 0xCu:
      v6 = 2;
LABEL_12:
      sqlite3Savepoint(a5, v6, v5 + 8);
      goto LABEL_441;
    case 0xDu:
      sqlite3StartTable(a5, (_OWORD *)(v5 - 16), v5 + 8, *(_DWORD *)(v5 - 88), 0, 0, *(_DWORD *)(v5 - 40));
      goto LABEL_441;
    case 0xEu:
      ++*((_BYTE *)a5 + 36);
      v7 = *a5;
      ++*(_DWORD *)(v7 + 416);
      *(_WORD *)(v7 + 420) = 0;
      goto LABEL_441;
    case 0xFu:
    case 0x12u:
    case 0x15u:
    case 0x2Fu:
    case 0x31u:
    case 0x3Eu:
    case 0x48u:
    case 0x51u:
    case 0x62u:
    case 0xEDu:
    case 0xF2u:
      *(_DWORD *)(v5 + 32) = 0;
      goto LABEL_441;
    case 0x10u:
      *(_DWORD *)(v5 - 40) = 1;
      goto LABEL_441;
    case 0x11u:
      v8 = *(_BYTE *)(*a5 + 197LL) == 0;
      goto LABEL_19;
    case 0x13u:
      sqlite3EndTable((_DWORD)a5, v5 - 40, v5 - 16, *(_DWORD *)(v5 + 8), 0);
      goto LABEL_441;
    case 0x14u:
      v9 = a5;
      sqlite3EndTable((_DWORD)a5, 0, 0, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_22;
    case 0x16u:
      *(_DWORD *)(v5 - 40) |= *(_DWORD *)(v5 + 8);
      goto LABEL_441;
    case 0x17u:
      if ( *(_DWORD *)(v5 + 16) != 5 || (unsigned int)sqlite3_strnicmp(*(_QWORD *)(v5 + 8), "rowid", 5) )
      {
        v11 = *(const char **)(v5 + 8);
        v12 = *(_DWORD *)(v5 + 16);
        *(_DWORD *)(v5 - 16) = 0;
        sqlite3ErrorMsg(a5, "unknown table option: %.*s", v12, v11);
      }
      else
      {
        *(_DWORD *)(v5 - 16) = 640;
      }
      goto LABEL_441;
    case 0x18u:
      v8 = 0;
      if ( *(_DWORD *)(v5 + 16) != 6 || (unsigned int)sqlite3_strnicmp(*(_QWORD *)(v5 + 8), "strict", 6) )
        sqlite3ErrorMsg(a5, "unknown table option: %.*s", *(_DWORD *)(v5 + 16), *(const char **)(v5 + 8));
      else
        v8 = 0x10000;
      goto LABEL_19;
    case 0x19u:
      v13 = *(_OWORD *)(v5 - 16);
      v210 = *(_OWORD *)(v5 + 8);
      v211 = v13;
      sqlite3AddColumn(a5, &v211, &v210);
      goto LABEL_441;
    case 0x1Au:
    case 0x41u:
    case 0x68u:
      *(_DWORD *)(v5 + 40) = 0;
      goto LABEL_35;
    case 0x1Bu:
      *(_DWORD *)(v5 - 56) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 64);
      goto LABEL_441;
    case 0x1Cu:
      *(_DWORD *)(v5 - 104) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 112);
      goto LABEL_441;
    case 0x1Du:
      *(_DWORD *)(v5 - 8) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 16);
      goto LABEL_441;
    case 0x1Eu:
      v14 = *a4;
      goto LABEL_40;
    case 0x1Fu:
      *(_OWORD *)(v5 + 32) = *(_OWORD *)a4;
      goto LABEL_441;
    case 0x20u:
    case 0x43u:
      *(_OWORD *)(a5 + 13) = *(_OWORD *)(v5 + 8);
      goto LABEL_441;
    case 0x21u:
      v15 = *(_QWORD *)(v5 - 16);
      v16 = v15 + *(unsigned int *)(v5 - 8);
      goto LABEL_44;
    case 0x22u:
      v16 = *(_QWORD *)(v5 + 8);
      v15 = *(_QWORD *)(v5 - 40) + 1LL;
      v17 = *(_QWORD *)(v5 - 16);
      goto LABEL_45;
    case 0x23u:
      v16 = *(_QWORD *)(v5 - 16) + *(unsigned int *)(v5 - 8);
      v15 = *(_QWORD *)(v5 - 40);
LABEL_44:
      v17 = *(_QWORD *)(v5 + 8);
      goto LABEL_45;
    case 0x24u:
      v17 = sqlite3PExpr(a5, 173, *(_QWORD *)(v5 + 8));
      v16 = *(_QWORD *)(v5 - 16) + *(unsigned int *)(v5 - 8);
      v15 = *(_QWORD *)(v5 - 40);
      goto LABEL_45;
    case 0x25u:
      v211 = *(_OWORD *)(v5 + 8);
      v18 = tokenExpr(a5, 117, &v211);
      v19 = v18;
      if ( v18 )
        sqlite3ExprIdToTrueFalse(v18);
      v15 = *(_QWORD *)(v5 + 8);
      v17 = v19;
      v16 = v15 + *(unsigned int *)(v5 + 16);
LABEL_45:
      sqlite3AddDefaultValue(a5, v17, v15, v16);
      goto LABEL_441;
    case 0x26u:
      sqlite3AddNotNull(a5, *(unsigned int *)(v5 + 8));
      goto LABEL_441;
    case 0x27u:
      sqlite3AddPrimaryKey((_DWORD)a5, 0, *(_DWORD *)(v5 - 16), *(_DWORD *)(v5 + 8), *(_DWORD *)(v5 - 40));
      goto LABEL_441;
    case 0x28u:
      sqlite3CreateIndex(a5, 0, 0, 0, 0, *(_DWORD *)(v5 + 8), 0, 0, 0, 0, 1u);
      goto LABEL_441;
    case 0x29u:
      v20 = *(_QWORD *)(v5 + 8);
      v21 = *(_QWORD *)(v5 - 40);
      v22 = *(_QWORD *)(v5 - 16);
      goto LABEL_58;
    case 0x2Au:
      sqlite3CreateForeignKey((_DWORD)a5, 0, v5 - 40, *(_QWORD *)(v5 - 16), *(_DWORD *)(v5 + 8));
      goto LABEL_441;
    case 0x2Bu:
      v23 = a5[43];
      if ( v23 )
      {
        if ( !*(_BYTE *)(v23 + 63) )
        {
          v24 = *(_QWORD *)(v23 + 72);
          if ( v24 )
            *(_BYTE *)(v24 + 44) = *(_BYTE *)(v5 + 8);
        }
      }
      goto LABEL_441;
    case 0x2Cu:
      sqlite3AddCollateType(a5, v5 + 8);
      goto LABEL_441;
    case 0x2Du:
      v25 = *(_QWORD *)(v5 - 16);
      v26 = 0;
      goto LABEL_66;
    case 0x2Eu:
      v25 = *(_QWORD *)(v5 - 40);
      v26 = v5 + 8;
LABEL_66:
      sqlite3AddGenerated(a5, v25, v26);
      goto LABEL_441;
    case 0x30u:
    case 0x60u:
    case 0x7Au:
    case 0x89u:
    case 0x115u:
      *(_DWORD *)(v5 + 8) = 1;
      goto LABEL_441;
    case 0x32u:
      v27 = *(_DWORD *)(v5 + 8) | *(_DWORD *)(v5 - 16) & ~*(_DWORD *)(v5 + 12);
      goto LABEL_71;
    case 0x33u:
      goto LABEL_220;
    case 0x34u:
      *(_QWORD *)(v5 - 40) = 0;
      goto LABEL_441;
    case 0x35u:
      *(_DWORD *)(v5 - 40) = *(_DWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 36) = 255;
      goto LABEL_441;
    case 0x36u:
      *(_DWORD *)(v5 - 40) = *(_DWORD *)(v5 + 8) << 8;
      *(_DWORD *)(v5 - 36) = 65280;
      goto LABEL_441;
    case 0x37u:
      *(_DWORD *)(v5 - 16) = 8;
      goto LABEL_441;
    case 0x38u:
      *(_DWORD *)(v5 - 16) = 9;
      goto LABEL_441;
    case 0x39u:
      *(_DWORD *)(v5 + 8) = 10;
      goto LABEL_441;
    case 0x3Au:
      *(_DWORD *)(v5 + 8) = 7;
      goto LABEL_441;
    case 0x3Bu:
    case 0x40u:
    case 0x8Bu:
      *(_DWORD *)(v5 - 16) = 0;
      goto LABEL_441;
    case 0x3Cu:
      *(_DWORD *)(v5 - 40) = 0;
      goto LABEL_441;
    case 0x3Du:
    case 0x4Cu:
    case 0xABu:
      v27 = *(_DWORD *)(v5 + 8);
      goto LABEL_71;
    case 0x3Fu:
    case 0x50u:
    case 0x8Cu:
    case 0xD7u:
    case 0xDAu:
    case 0xF3u:
      *(_DWORD *)(v5 - 16) = 1;
      goto LABEL_441;
    case 0x42u:
      *((_DWORD *)a5 + 28) = 0;
      goto LABEL_441;
    case 0x44u:
      sqlite3AddPrimaryKey((_DWORD)a5, *(_QWORD *)(v5 - 64), *(_DWORD *)(v5 + 8), *(_DWORD *)(v5 - 40), 0);
      goto LABEL_441;
    case 0x45u:
      sqlite3CreateIndex(a5, 0, 0, 0, *(int **)(v5 - 40), *(_DWORD *)(v5 + 8), 0, 0, 0, 0, 1u);
      goto LABEL_441;
    case 0x46u:
      v20 = *(_QWORD *)(v5 - 16);
      v21 = *(_QWORD *)(v5 - 64);
      v22 = *(_QWORD *)(v5 - 40);
LABEL_58:
      sqlite3AddCheckConstraint(a5, v22, v21, v20);
      goto LABEL_441;
    case 0x47u:
      sqlite3CreateForeignKey((_DWORD)a5, *(_QWORD *)(v5 - 136), v5 - 64, *(_QWORD *)(v5 - 40), *(_DWORD *)(v5 - 16));
      v28 = a5[43];
      if ( v28 )
      {
        if ( !*(_BYTE *)(v28 + 63) )
        {
          v29 = *(_QWORD *)(v28 + 72);
          if ( v29 )
            *(_BYTE *)(v29 + 44) = *(_BYTE *)(v5 + 8);
        }
      }
      goto LABEL_441;
    case 0x49u:
    case 0x4Bu:
      *(_DWORD *)(v5 + 32) = 11;
      goto LABEL_441;
    case 0x4Au:
      v30 = *(_DWORD *)(v5 + 8);
      goto LABEL_93;
    case 0x4Du:
      *(_DWORD *)(v5 + 8) = 4;
      goto LABEL_441;
    case 0x4Eu:
    case 0xACu:
      *(_DWORD *)(v5 + 8) = 5;
      goto LABEL_441;
    case 0x4Fu:
      v31 = 0;
      goto LABEL_97;
    case 0x52u:
      sqlite3CreateView(
        (_DWORD)a5,
        v5 - 184,
        v5 - 88,
        v5 - 64,
        *(_QWORD *)(v5 - 40),
        *(_QWORD *)(v5 + 8),
        *(_DWORD *)(v5 - 160),
        *(_DWORD *)(v5 - 112));
      goto LABEL_441;
    case 0x53u:
      v31 = 1;
LABEL_97:
      sqlite3DropTable(a5, *(_QWORD *)(v5 + 8), v31, *(unsigned int *)(v5 - 16));
      goto LABEL_441;
    case 0x54u:
      v9 = a5;
      v32 = *(_QWORD *)(v5 + 8);
      v212 = 9;
      v213 = 0;
      v214 = 0;
      v215 = 0;
      v216 = 0;
      v217 = 0;
      sqlite3Select(a5, v32, &v212);
LABEL_22:
      v10 = *(_QWORD *)(v5 + 8);
      if ( v10 )
        clearSelect(*v9, v10, 1);
      goto LABEL_441;
    case 0x55u:
      v33 = *(_QWORD *)(v5 + 8);
      v34 = *(_QWORD *)(v5 - 16);
      if ( v33 )
      {
        *(_QWORD *)(v33 + 104) = v34;
        parserDoubleLinkSelect(a5, v33);
      }
      else
      {
        sqlite3WithDelete(*a5, v34);
      }
      goto LABEL_104;
    case 0x56u:
      v35 = *(_QWORD *)(v5 + 8);
      v36 = *(_QWORD *)(v5 - 16);
      if ( v35 )
      {
        *(_QWORD *)(v35 + 104) = v36;
        parserDoubleLinkSelect(a5, v35);
      }
      else
      {
        sqlite3WithDelete(*a5, v36);
      }
      *(_QWORD *)(v5 - 64) = v35;
      goto LABEL_441;
    case 0x57u:
      v37 = *(_QWORD *)(v5 + 8);
      if ( v37 )
        parserDoubleLinkSelect(a5, v37);
      goto LABEL_441;
    case 0x58u:
      v33 = *(_QWORD *)(v5 + 8);
      v38 = *(_QWORD *)(v5 - 40);
      if ( v33
        && (!*(_QWORD *)(v33 + 80)
         || (v39 = *(_QWORD *)(v5 + 8),
             v211 = 0,
             parserDoubleLinkSelect(a5, v39),
             v40 = sqlite3SrcListAppendFromTerm((_DWORD)a5, 0, 0, 0, (__int64)&v211, v33, 0),
             (v33 = sqlite3SelectNew((_DWORD)a5, 0, v40, 0, 0, 0, 0, 0, 0)) != 0)) )
      {
        *(_BYTE *)v33 = *(_BYTE *)(v5 - 16);
        *(_QWORD *)(v33 + 80) = v38;
        if ( v38 )
          *(_DWORD *)(v38 + 4) &= ~0x400u;
        *(_DWORD *)(v33 + 4) &= ~0x400u;
        if ( *(_DWORD *)(v5 - 16) != 135 )
          *((_BYTE *)a5 + 34) = 1;
      }
      else if ( v38 )
      {
        clearSelect(*a5, v38, 1);
      }
      goto LABEL_104;
    case 0x5Au:
      *(_DWORD *)(v5 - 16) = 135;
      goto LABEL_441;
    case 0x5Cu:
      updated = sqlite3SelectNew(
                  (_DWORD)a5,
                  *(_QWORD *)(v5 - 136),
                  *(_QWORD *)(v5 - 112),
                  *(_QWORD *)(v5 - 88),
                  *(_QWORD *)(v5 - 64),
                  *(_QWORD *)(v5 - 40),
                  *(_QWORD *)(v5 - 16),
                  *(_DWORD *)(v5 - 160),
                  *(_QWORD *)(v5 + 8));
      goto LABEL_122;
    case 0x5Du:
      v42 = sqlite3SelectNew(
              (_DWORD)a5,
              *(_QWORD *)(v5 - 160),
              *(_QWORD *)(v5 - 136),
              *(_QWORD *)(v5 - 112),
              *(_QWORD *)(v5 - 88),
              *(_QWORD *)(v5 - 64),
              *(_QWORD *)(v5 - 16),
              *(_DWORD *)(v5 - 184),
              *(_QWORD *)(v5 + 8));
      v43 = *(_QWORD *)(v5 - 40);
      *(_QWORD *)(v5 - 208) = v42;
      if ( v42 )
      {
        *(_QWORD *)(v42 + 120) = v43;
      }
      else
      {
        v44 = *a5;
        if ( v43 )
        {
          do
          {
            v45 = *(_QWORD *)(v43 + 64);
            sqlite3WindowDelete(v44);
            v43 = v45;
          }
          while ( v45 );
        }
      }
      goto LABEL_441;
    case 0x5Eu:
      v46 = sqlite3SelectNew((_DWORD)a5, *(_QWORD *)(v5 - 16), 0, 0, 0, 0, 0, 512, 0);
      goto LABEL_129;
    case 0x5Fu:
      v47 = *(_QWORD *)(v5 - 88);
      appended = sqlite3SelectNew((_DWORD)a5, *(_QWORD *)(v5 - 16), 0, 0, 0, 0, 0, 1536, 0);
      if ( v47 )
        *(_DWORD *)(v47 + 4) &= ~0x400u;
      if ( appended )
      {
        *(_BYTE *)appended = -121;
        *(_QWORD *)(appended + 80) = v47;
      }
      else
      {
        appended = v47;
      }
      goto LABEL_440;
    case 0x61u:
    case 0xECu:
    case 0x116u:
      *(_DWORD *)(v5 + 8) = 2;
      goto LABEL_441;
    case 0x63u:
    case 0x69u:
    case 0x6Cu:
    case 0x84u:
    case 0x8Eu:
    case 0x90u:
    case 0x92u:
    case 0x97u:
    case 0x99u:
    case 0xA4u:
    case 0xADu:
    case 0xE4u:
    case 0xE5u:
    case 0xE6u:
    case 0xE9u:
    case 0xEEu:
    case 0xF8u:
    case 0x108u:
    case 0x11Bu:
LABEL_35:
      *(_QWORD *)(v5 + 32) = 0;
      goto LABEL_441;
    case 0x64u:
      v49 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 88) = v49;
      if ( *(_DWORD *)(v5 + 16) )
        sqlite3ExprListSetName(a5, v49, v5 + 8, 1);
      sqlite3ExprListSetSpan(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16));
      goto LABEL_441;
    case 0x65u:
      v50 = sqlite3Expr(*a5, 180, 0);
      if ( v50 && (*(_BYTE *)(v50 + 4) & 3) == 0 )
        *(_DWORD *)(v50 + 52) = *(_DWORD *)(v5 + 8) - *((_DWORD *)a5 + 84);
      v51 = v50;
      v52 = a5;
      goto LABEL_142;
    case 0x66u:
      v54 = sqlite3PExpr(a5, 180, 0);
      if ( v54 && (*(_BYTE *)(v54 + 4) & 3) == 0 )
        *(_DWORD *)(v54 + 52) = *(_DWORD *)(v5 + 8) - *((_DWORD *)a5 + 84);
      v211 = *(_OWORD *)(v5 - 40);
      v55 = tokenExpr(a5, 59, &v211);
      v56 = sqlite3PExpr(a5, 141, v55);
      v57 = *(_QWORD *)(v5 - 88);
      v58 = v56;
      v59 = a5;
      goto LABEL_148;
    case 0x67u:
    case 0x73u:
    case 0xFEu:
    case 0xFFu:
      *(_OWORD *)(v5 - 16) = *(_OWORD *)(v5 + 8);
      goto LABEL_441;
    case 0x6Au:
      *(_QWORD *)(v5 - 16) = *(_QWORD *)(v5 + 8);
      sqlite3SrcListShiftJoinType(a5);
      goto LABEL_441;
    case 0x6Bu:
      v60 = *(int **)(v5 - 16);
      if ( v60 && *v60 > 0 )
        LOBYTE(v60[26 * *v60 - 9]) = *(_BYTE *)(v5 + 8);
      goto LABEL_441;
    case 0x6Du:
      appended = sqlite3SrcListAppendFromTerm(
                   (_DWORD)a5,
                   *(_QWORD *)(v5 - 88),
                   (int)v5 - 64,
                   (int)v5 - 40,
                   v5 - 16,
                   0,
                   v5 + 8);
      goto LABEL_440;
    case 0x6Eu:
      v61 = sqlite3SrcListAppendFromTerm(
              (_DWORD)a5,
              *(_QWORD *)(v5 - 112),
              (int)v5 - 88,
              (int)v5 - 64,
              v5 - 40,
              0,
              v5 + 8);
      *(_QWORD *)(v5 - 112) = v61;
      sqlite3SrcListIndexedBy(a5, v61, v5 - 16);
      goto LABEL_441;
    case 0x6Fu:
      v62 = sqlite3SrcListAppendFromTerm(
              (_DWORD)a5,
              *(_QWORD *)(v5 - 160),
              (int)v5 - 136,
              (int)v5 - 112,
              v5 - 16,
              0,
              v5 + 8);
      *(_QWORD *)(v5 - 160) = v62;
      sqlite3SrcListFuncArgs(a5, v62);
      goto LABEL_441;
    case 0x70u:
      v63 = sqlite3SrcListAppendFromTerm((_DWORD)a5, *(_QWORD *)(v5 - 112), 0, 0, v5 - 16, *(_QWORD *)(v5 - 64), v5 + 8);
      goto LABEL_158;
    case 0x71u:
      if ( !*(_QWORD *)(v5 - 112) && !*(_DWORD *)(v5 - 8) && !*(_QWORD *)(v5 + 8) && !*(_QWORD *)(v5 + 16) )
      {
        v63 = *(_QWORD *)(v5 - 64);
LABEL_158:
        *(_QWORD *)(v5 - 112) = v63;
        goto LABEL_441;
      }
      v64 = *(_DWORD **)(v5 - 64);
      if ( !v64 || *v64 != 1 )
      {
        sqlite3SrcListShiftJoinType(a5);
        v70 = sqlite3SelectNew((_DWORD)a5, 0, *(_QWORD *)(v5 - 64), 0, 0, 0, 0, 2048, 0);
        v63 = sqlite3SrcListAppendFromTerm((_DWORD)a5, *(_QWORD *)(v5 - 112), 0, 0, v5 - 16, v70, v5 + 8);
        goto LABEL_158;
      }
      v65 = (int *)sqlite3SrcListAppendFromTerm((_DWORD)a5, *(_QWORD *)(v5 - 112), 0, 0, v5 - 16, 0, v5 + 8);
      *(_QWORD *)(v5 - 112) = v65;
      v66 = v65;
      if ( v65 )
      {
        v67 = *(_QWORD *)(v5 - 64);
        v68 = 26LL * *v65;
        *(_QWORD *)&v65[v68 - 20] = *(_QWORD *)(v67 + 24);
        *(_QWORD *)&v65[v68 - 22] = *(_QWORD *)(v67 + 16);
        v69 = *(_QWORD *)(v67 + 48);
        *(_QWORD *)&v66[v68 - 14] = v69;
        if ( v69 && (*(_DWORD *)(v69 + 4) & 0x800) != 0 )
          v66[v68 - 8] |= 0x2000u;
        if ( (*(_BYTE *)(v67 + 72) & 4) != 0 )
        {
          *(_QWORD *)&v66[v68 - 2] = *(_QWORD *)(v67 + 96);
          *(_DWORD *)(v67 + 72) &= ~4u;
          *(_QWORD *)(v67 + 96) = 0;
          v66[v68 - 8] |= 4u;
        }
        *(_QWORD *)(v67 + 16) = 0;
        *(_QWORD *)(v67 + 24) = 0;
        *(_QWORD *)(v67 + 48) = 0;
      }
      sqlite3SrcListDelete(*a5, *(_QWORD *)(v5 - 64));
      goto LABEL_441;
    case 0x72u:
    case 0x81u:
      *(_QWORD *)(v5 + 32) = 0;
      *(_DWORD *)(v5 + 40) = 0;
      goto LABEL_441;
    case 0x74u:
      v71 = (_OWORD *)(v5 + 8);
      v72 = sqlite3SrcListAppend(a5, 0, v5 + 8, 0);
      v73 = *((_BYTE *)a5 + 300);
      if ( v73 >= 2u )
      {
        if ( v72 )
        {
          if ( v73 != 3 )
          {
            v74 = *(_QWORD *)(v72 + 24);
            v75 = sqlite3DbMallocZero(*a5, 32);
            if ( v75 )
            {
              *(_QWORD *)v75 = v74;
              *(_OWORD *)(v75 + 8) = *v71;
              *(_QWORD *)(v75 + 24) = a5[51];
              a5[51] = v75;
            }
          }
        }
      }
      *(_QWORD *)v71 = v72;
      goto LABEL_441;
    case 0x75u:
      v76 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 + 8);
      v77 = *((_BYTE *)a5 + 300);
      if ( v77 >= 2u )
      {
        if ( v76 )
        {
          if ( v77 != 3 )
          {
            v78 = *(_QWORD *)(v76 + 24);
            v79 = sqlite3DbMallocZero(*a5, 32);
            if ( v79 )
            {
              *(_QWORD *)v79 = v78;
              *(_OWORD *)(v79 + 8) = *(_OWORD *)(v5 + 8);
              *(_QWORD *)(v79 + 24) = a5[51];
              a5[51] = v79;
            }
          }
        }
      }
      goto LABEL_187;
    case 0x76u:
      v80 = sqlite3SrcListAppend(a5, 0, v5 + 8, 0);
      goto LABEL_189;
    case 0x77u:
      v53 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 + 8);
      goto LABEL_143;
    case 0x78u:
      v81 = v5 - 88;
      v82 = v5 - 40;
      goto LABEL_192;
    case 0x79u:
      v81 = v5 - 40;
      v82 = 0;
LABEL_192:
      v83 = sqlite3SrcListAppend(a5, 0, v81, v82);
      v84 = 0;
      *(_QWORD *)v81 = v83;
      if ( v83 )
      {
        if ( v5 != -8 )
        {
          v84 = sqlite3DbStrNDup(*a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 + 16));
          sqlite3Dequote(v84);
        }
        *(_QWORD *)(*(_QWORD *)v81 + 32LL) = v84;
      }
      goto LABEL_441;
    case 0x7Bu:
      v27 = sqlite3JoinType(a5, v5 - 16, 0, 0);
LABEL_71:
      *(_DWORD *)(v5 - 16) = v27;
      goto LABEL_441;
    case 0x7Cu:
      v30 = sqlite3JoinType(a5, v5 - 40, v5 - 16, 0);
LABEL_93:
      *(_DWORD *)(v5 - 40) = v30;
      goto LABEL_441;
    case 0x7Du:
      *(_DWORD *)(v5 - 64) = sqlite3JoinType(a5, v5 - 64, v5 - 40, v5 - 16);
      goto LABEL_441;
    case 0x7Eu:
      v85 = *(_QWORD *)(v5 + 8);
      goto LABEL_201;
    case 0x7Fu:
      v86 = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(v5 - 64) = 0;
      *(_QWORD *)(v5 - 56) = v86;
      goto LABEL_441;
    case 0x80u:
      *(_QWORD *)(v5 + 32) = 0;
      *(_QWORD *)(v5 + 40) = 0;
      goto LABEL_441;
    case 0x82u:
      *(_OWORD *)(v5 - 40) = *(_OWORD *)(v5 + 8);
      goto LABEL_441;
    case 0x83u:
      *(_DWORD *)(v5 - 8) = 1;
      *(_QWORD *)(v5 - 16) = 0;
      goto LABEL_441;
    case 0x85u:
    case 0x8Fu:
      goto LABEL_436;
    case 0x86u:
      v87 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 88) = v87;
      goto LABEL_207;
    case 0x87u:
      v87 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 40) = v87;
LABEL_207:
      sqlite3ExprListSetSortOrder(v87, *(unsigned int *)(v5 - 16), *(unsigned int *)(v5 + 8));
      goto LABEL_441;
    case 0x88u:
    case 0xD6u:
    case 0xD9u:
      v8 = 0;
LABEL_19:
      *(_DWORD *)(v5 + 8) = v8;
      goto LABEL_441;
    case 0x8Au:
    case 0x8Du:
      *(_DWORD *)(v5 + 32) = -1;
      goto LABEL_441;
    case 0x91u:
    case 0x98u:
    case 0x9Au:
    case 0xE3u:
    case 0xF7u:
    case 0x109u:
    case 0x11Cu:
    case 0x14Bu:
      goto LABEL_210;
    case 0x93u:
      v89 = 148;
      goto LABEL_213;
    case 0x94u:
      v91 = *(_QWORD *)(v5 - 40);
      goto LABEL_216;
    case 0x95u:
      v91 = *(_QWORD *)(v5 + 8);
LABEL_216:
      v46 = sqlite3PExpr(a5, 148, v91);
      goto LABEL_129;
    case 0x96u:
      sqlite3SrcListIndexedBy(a5, *(_QWORD *)(v5 - 40), v5 - 16);
      sqlite3DeleteFrom((_DWORD)a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8), 0, 0);
      goto LABEL_441;
    case 0x9Bu:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
LABEL_220:
      *(_QWORD *)(v5 - 16) = 0;
      goto LABEL_441;
    case 0x9Cu:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
      v46 = *(_QWORD *)(v5 - 40);
      goto LABEL_129;
    case 0x9Du:
      sqlite3SrcListIndexedBy(a5, *(_QWORD *)(v5 - 112), v5 - 88);
      v92 = *(_DWORD **)(v5 - 40);
      if ( v92 && *v92 > *(_DWORD *)(*a5 + 144LL) )
        sqlite3ErrorMsg(a5, "too many columns in %s", "set list");
      v93 = *(int **)(v5 - 16);
      if ( v93 )
      {
        if ( *v93 > 1 )
        {
          v210 = 0;
          v94 = sqlite3SelectNew((_DWORD)a5, 0, (_DWORD)v93, 0, 0, 0, 0, 2048, 0);
          DWORD2(v210) = 0;
          *(_QWORD *)&v210 = 0;
          v93 = (int *)sqlite3SrcListAppendFromTerm((_DWORD)a5, 0, 0, 0, (__int64)&v210, v94, 0);
        }
        *(_QWORD *)(v5 - 112) = sqlite3SrcListAppendList(a5, *(_QWORD *)(v5 - 112), v93);
      }
      sqlite3Update(
        (_DWORD)a5,
        *(_QWORD *)(v5 - 112),
        *(_QWORD *)(v5 - 40),
        *(_QWORD *)(v5 + 8),
        *(_DWORD *)(v5 - 136),
        0,
        0,
        0);
      goto LABEL_441;
    case 0x9Eu:
      v95 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 88) = v95;
      sqlite3ExprListSetName(a5, v95, v5 - 40, 1);
      goto LABEL_441;
    case 0x9Fu:
      *(_QWORD *)(v5 - 136) = sqlite3ExprListAppendVector(
                                a5,
                                *(_QWORD *)(v5 - 136),
                                *(_QWORD *)(v5 - 64),
                                *(_QWORD *)(v5 + 8));
      goto LABEL_441;
    case 0xA0u:
      v76 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 + 8));
      sqlite3ExprListSetName(a5, v76, v5 - 40, 1);
LABEL_187:
      *(_QWORD *)(v5 - 40) = v76;
      goto LABEL_441;
    case 0xA1u:
      appended = sqlite3ExprListAppendVector(a5, 0, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 + 8));
      goto LABEL_440;
    case 0xA2u:
      sqlite3Insert(
        (_DWORD)a5,
        *(_QWORD *)(v5 - 64),
        *(_QWORD *)(v5 - 16),
        *(_QWORD *)(v5 - 40),
        *(_DWORD *)(v5 - 112),
        *(_QWORD *)(v5 + 8));
      goto LABEL_441;
    case 0xA3u:
      sqlite3Insert((_DWORD)a5, *(_QWORD *)(v5 - 88), 0, *(_QWORD *)(v5 - 64), *(_DWORD *)(v5 - 136), 0);
      goto LABEL_441;
    case 0xA5u:
      *(_QWORD *)(v5 - 16) = 0;
      goto LABEL_238;
    case 0xA6u:
      *(_QWORD *)(v5 - 256) = sqlite3UpsertNew(
                                *a5,
                                *(_QWORD *)(v5 - 184),
                                *(_QWORD *)(v5 - 136),
                                *(_QWORD *)(v5 - 40),
                                *(_QWORD *)(v5 - 16),
                                *(_QWORD *)(v5 + 8));
      goto LABEL_441;
    case 0xA7u:
      updated = sqlite3UpsertNew(*a5, *(_QWORD *)(v5 - 112), *(_QWORD *)(v5 - 64), 0, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_122;
    case 0xA8u:
      v96 = sqlite3DbMallocZero(*a5, 88);
      v97 = 0;
      if ( v96 )
      {
        *(_QWORD *)v96 = 0;
        *(_QWORD *)(v96 + 8) = 0;
        *(_QWORD *)(v96 + 16) = 0;
        *(_QWORD *)(v96 + 24) = 0;
        *(_BYTE *)(v96 + 40) = 0;
        *(_QWORD *)(v96 + 32) = 0;
        v97 = v96;
      }
      *(_QWORD *)(v5 - 88) = v97;
      goto LABEL_441;
    case 0xA9u:
      inserted = sqlite3UpsertNew(*a5, 0, 0, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 - 16), 0);
      goto LABEL_245;
    case 0xAAu:
LABEL_238:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_441;
    case 0xAEu:
    case 0xB1u:
    case 0xEAu:
    case 0xEFu:
      v53 = *(_QWORD *)(v5 - 16);
      goto LABEL_143;
    case 0xAFu:
      v53 = sqlite3IdListAppend(a5, *(_QWORD *)(v5 - 40), v5 + 8);
      goto LABEL_143;
    case 0xB0u:
      v80 = sqlite3IdListAppend(a5, 0, v5 + 8);
      goto LABEL_189;
    case 0xB2u:
      v99 = 59;
      goto LABEL_250;
    case 0xB3u:
      v211 = *(_OWORD *)(v5 - 40);
      v100 = tokenExpr(a5, 59, &v211);
      v211 = *(_OWORD *)(v5 + 8);
      tokenExpr(a5, 59, &v211);
      v101 = 141;
      v102 = v100;
      v103 = a5;
      goto LABEL_252;
    case 0xB4u:
      v211 = *(_OWORD *)(v5 - 88);
      v104 = tokenExpr(a5, 59, &v211);
      v211 = *(_OWORD *)(v5 - 40);
      v105 = tokenExpr(a5, 59, &v211);
      v211 = *(_OWORD *)(v5 + 8);
      tokenExpr(a5, 59, &v211);
      sqlite3PExpr(a5, 141, v105);
      if ( *((_BYTE *)a5 + 300) < 2u )
        goto LABEL_260;
      v106 = (_QWORD *)a5[51];
      while ( 2 )
      {
        if ( v106 )
        {
          if ( *v106 != v104 )
          {
            v106 = (_QWORD *)v106[3];
            continue;
          }
          *v106 = 0;
        }
        break;
      }
LABEL_260:
      v107 = v104;
      v108 = 141;
      v109 = a5;
LABEL_261:
      appended = sqlite3PExpr(v109, v108, v107);
LABEL_440:
      *(_QWORD *)(v5 - 88) = appended;
      goto LABEL_441;
    case 0xB5u:
    case 0xB6u:
      v99 = *(unsigned __int16 *)(v5 + 2);
LABEL_250:
      v211 = *(_OWORD *)(v5 + 8);
      v80 = tokenExpr(a5, v99, &v211);
      goto LABEL_189;
    case 0xB7u:
      v110 = (_QWORD *)(v5 + 8);
      v111 = sqlite3ExprAlloc(*a5, 155, v5 + 8);
      if ( v111 )
        *(_DWORD *)(v111 + 52) = *(_DWORD *)v110 - *((_DWORD *)a5 + 84);
      goto LABEL_265;
    case 0xB8u:
      v112 = *(_BYTE **)(v5 + 8);
      if ( *v112 == 35 && (byte_1400B2300[(unsigned __int8)v112[1]] & 4) != 0 )
      {
        v210 = *(_OWORD *)(v5 + 8);
        if ( *((_BYTE *)a5 + 30) )
        {
          v113 = sqlite3PExpr(a5, 176, 0);
          *(_QWORD *)(v5 + 8) = v113;
          if ( v113 )
            sqlite3GetInt32(v210 + 1, v113 + 44);
        }
        else
        {
          sqlite3ErrorMsg(a5, "near \"%T\": syntax error", &v210);
          *(_QWORD *)(v5 + 8) = 0;
        }
      }
      else
      {
        v114 = *(_DWORD *)(v5 + 16);
        v211 = *(_OWORD *)(v5 + 8);
        v115 = tokenExpr(a5, 156, &v211);
        *(_QWORD *)(v5 + 8) = v115;
        sqlite3ExprAssignVarNumber(a5, v115, v114);
      }
      goto LABEL_441;
    case 0xB9u:
      v33 = *(_QWORD *)(v5 - 40);
      if ( *(_DWORD *)(v5 + 16) )
      {
        v116 = sqlite3ExprAlloc(*a5, 113, v5 + 8);
        if ( v116 )
        {
          *(_DWORD *)(v116 + 4) |= 0x2200u;
          *(_QWORD *)(v116 + 16) = v33;
          v33 = v116;
        }
      }
LABEL_104:
      *(_QWORD *)(v5 - 40) = v33;
      goto LABEL_441;
    case 0xBAu:
      v117 = sqlite3ExprAlloc(*a5, 36, v5 - 16);
      v118 = *(_QWORD *)(v5 - 64);
      *(_QWORD *)(v5 - 112) = v117;
      sqlite3ExprAttachSubtrees(*a5, v117, v118, 0);
      goto LABEL_441;
    case 0xBBu:
      appended = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 16), v5 - 88, *(unsigned int *)(v5 - 40));
      goto LABEL_440;
    case 0xBCu:
      v46 = sqlite3ExprFunction(a5, 0, v5 - 64, 0);
      goto LABEL_129;
    case 0xBDu:
      v119 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 40), v5 - 112, *(unsigned int *)(v5 - 64));
      sqlite3WindowAttach(a5, v119, *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 112) = v119;
      goto LABEL_441;
    case 0xBEu:
      v120 = sqlite3ExprFunction(a5, 0, v5 - 88, 0);
      sqlite3WindowAttach(a5, v120, *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 88) = v120;
      goto LABEL_441;
    case 0xBFu:
      v80 = sqlite3ExprFunction(a5, 0, v5 + 8, 0);
      goto LABEL_189;
    case 0xC0u:
      v121 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16));
      v122 = sqlite3PExpr(a5, 177, 0);
      *(_QWORD *)(v5 - 88) = v122;
      if ( v122 )
      {
        *(_QWORD *)(v122 + 32) = v121;
        if ( *(_DWORD *)v121 )
          *(_DWORD *)(*(_QWORD *)(v5 - 88) + 4LL) |= *(_DWORD *)(*(_QWORD *)(v121 + 8) + 4LL) & 0x400208;
      }
      else if ( v121 )
      {
        exprListDeleteNN(*a5, v121);
      }
      goto LABEL_441;
    case 0xC1u:
      v53 = sqlite3ExprAnd(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_143;
    case 0xC2u:
    case 0xC3u:
    case 0xC4u:
    case 0xC5u:
    case 0xC6u:
    case 0xC7u:
    case 0xC8u:
      v101 = *(unsigned __int16 *)(v5 - 22);
      goto LABEL_289;
    case 0xC9u:
      *(_OWORD *)(v5 - 16) = *(_OWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 8) |= 0x80000000;
      goto LABEL_441;
    case 0xCAu:
      v123 = *(_DWORD *)(v5 - 8);
      v124 = *(_QWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 8) = v123 & 0x7FFFFFFF;
      v125 = sqlite3ExprListAppend(a5, 0, v124);
      v126 = sqlite3ExprListAppend(a5, v125, *(_QWORD *)(v5 - 40));
      v127 = sqlite3ExprFunction(a5, v126, v5 - 16, 0);
      *(_QWORD *)(v5 - 40) = v127;
      if ( v123 < 0 )
      {
        v127 = sqlite3PExpr(a5, 19, v127);
        *(_QWORD *)(v5 - 40) = v127;
      }
      goto LABEL_293;
    case 0xCBu:
      v128 = *(_DWORD *)(v5 - 56);
      v129 = *(_QWORD *)(v5 - 40);
      *(_DWORD *)(v5 - 56) = v128 & 0x7FFFFFFF;
      v130 = sqlite3ExprListAppend(a5, 0, v129);
      v131 = sqlite3ExprListAppend(a5, v130, *(_QWORD *)(v5 - 88));
      v132 = sqlite3ExprListAppend(a5, v131, *(_QWORD *)(v5 + 8));
      v127 = sqlite3ExprFunction(a5, v132, v5 - 64, 0);
      *(_QWORD *)(v5 - 88) = v127;
      if ( v128 < 0 )
      {
        v127 = sqlite3PExpr(a5, 19, v127);
        *(_QWORD *)(v5 - 88) = v127;
      }
LABEL_293:
      if ( v127 )
        *(_DWORD *)(v127 + 4) |= 0x100u;
      goto LABEL_441;
    case 0xCCu:
      v89 = *(unsigned __int16 *)(v5 + 2);
      v90 = *(_QWORD *)(v5 - 16);
      goto LABEL_214;
    case 0xCDu:
      v101 = 51;
LABEL_289:
      v102 = *(_QWORD *)(v5 - 40);
      v103 = a5;
LABEL_252:
      v53 = sqlite3PExpr(v103, v101, v102);
      goto LABEL_143;
    case 0xCEu:
      v133 = a5;
      v134 = sqlite3PExpr(a5, 45, *(_QWORD *)(v5 - 40));
      v135 = v134;
      *(_QWORD *)(v5 - 40) = v134;
      goto LABEL_300;
    case 0xCFu:
      v139 = a5;
      v140 = sqlite3PExpr(a5, 171, *(_QWORD *)(v5 - 64));
      v135 = v140;
      *(_QWORD *)(v5 - 64) = v140;
      goto LABEL_309;
    case 0xD0u:
      v133 = a5;
      v134 = sqlite3PExpr(a5, 45, *(_QWORD *)(v5 - 112));
      v135 = v134;
      *(_QWORD *)(v5 - 112) = v134;
LABEL_300:
      if ( !v134 )
        goto LABEL_441;
      v136 = *(_BYTE **)(v5 + 8);
      if ( !v136 || *v136 != 121 || *((_BYTE *)v133 + 300) >= 2u )
        goto LABEL_441;
      v137 = *v133;
      *(_BYTE *)v135 = 50;
      goto LABEL_305;
    case 0xD1u:
      v139 = a5;
      v140 = sqlite3PExpr(a5, 171, *(_QWORD *)(v5 - 88));
      v135 = v140;
      *(_QWORD *)(v5 - 88) = v140;
LABEL_309:
      if ( !v140 )
        goto LABEL_441;
      v141 = *(_BYTE **)(v5 + 8);
      if ( !v141 || *v141 != 121 || *((_BYTE *)v139 + 300) >= 2u )
        goto LABEL_441;
      v137 = *v139;
      *(_BYTE *)v135 = 51;
LABEL_305:
      v138 = *(_QWORD *)(v135 + 24);
      if ( v138 )
        sqlite3ExprDeleteNN(v137, v138);
      *(_QWORD *)(v135 + 24) = 0;
      goto LABEL_441;
    case 0xD2u:
    case 0xD3u:
      v89 = *(unsigned __int16 *)(v5 - 22);
      goto LABEL_213;
    case 0xD4u:
      v89 = 174 - (unsigned int)(*(_WORD *)(v5 - 22) != 106);
LABEL_213:
      v90 = *(_QWORD *)(v5 + 8);
LABEL_214:
      v88 = sqlite3PExpr(a5, v89, v90);
      goto LABEL_211;
    case 0xD5u:
      v142 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      v143 = sqlite3ExprListAppend(a5, v142, *(_QWORD *)(v5 + 8));
      v53 = sqlite3ExprFunction(a5, v143, v5 - 16, 0);
      goto LABEL_143;
    case 0xD8u:
      v144 = a5;
      v145 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      v146 = sqlite3ExprListAppend(a5, v145, *(_QWORD *)(v5 + 8));
      v147 = sqlite3PExpr(a5, 48, *(_QWORD *)(v5 - 88));
      *(_QWORD *)(v5 - 88) = v147;
      if ( v147 )
      {
        *(_QWORD *)(v147 + 32) = v146;
      }
      else if ( v146 )
      {
        exprListDeleteNN(*a5, v146);
      }
      goto LABEL_324;
    case 0xDBu:
      v148 = *(_QWORD *)(v5 - 16);
      if ( !v148 )
      {
        v149 = *(_QWORD *)(v5 - 88);
        if ( v149 )
        {
          if ( *((_BYTE *)a5 + 300) >= 2u )
            sqlite3RenameExprUnmap(a5, *(_QWORD *)(v5 - 88));
          sqlite3ExprDeleteNN(*a5, v149);
        }
        v150 = "true";
        if ( !*(_DWORD *)(v5 - 64) )
          v150 = "false";
        v151 = sqlite3Expr(*a5, 117, v150);
        *(_QWORD *)(v5 - 88) = v151;
        if ( v151 )
          sqlite3ExprIdToTrueFalse(v151);
        goto LABEL_441;
      }
      v152 = *(_QWORD *)(v148 + 8);
      if ( *(_DWORD *)v148 == 1 )
      {
        if ( (unsigned int)exprIsConst(*(_QWORD *)(v148 + 8), 1) )
        {
          v110 = (_QWORD *)(v5 - 88);
          if ( **(_BYTE **)(v5 - 88) != 0xB1 )
          {
            v153 = a5;
            *(_QWORD *)(*(_QWORD *)(v5 - 16) + 8LL) = 0;
            v154 = *(_QWORD *)(v5 - 16);
            if ( v154 )
              exprListDeleteNN(*a5, v154);
            sqlite3PExpr(a5, 174, v152);
            *v110 = sqlite3PExpr(a5, 53, *v110);
            goto LABEL_351;
          }
        }
      }
      if ( **(_DWORD **)(v5 - 16) == 1 && *(_BYTE *)v152 == 0x8A )
      {
        v153 = a5;
        v110 = (_QWORD *)(v5 - 88);
        v155 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88));
        *(_QWORD *)(v5 - 88) = v155;
        sqlite3PExprAddSelect(a5, v155, *(_QWORD *)(v152 + 32));
        *(_QWORD *)(v152 + 32) = 0;
        goto LABEL_345;
      }
      v153 = a5;
      v110 = (_QWORD *)(v5 - 88);
      v156 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88));
      *(_QWORD *)(v5 - 88) = v156;
      if ( !v156 )
      {
LABEL_345:
        v157 = *(_QWORD *)(v5 - 16);
        if ( v157 )
          exprListDeleteNN(*v153, v157);
        goto LABEL_351;
      }
      v158 = *(_QWORD *)(v156 + 16);
      if ( *(_BYTE *)v158 == 0xB1 )
      {
        v159 = sqlite3ExprListToValues(a5, **(unsigned int **)(v158 + 32), *(_QWORD *)(v5 - 16));
        v160 = v159;
        if ( v159 )
        {
          parserDoubleLinkSelect(a5, v159);
          sqlite3PExprAddSelect(a5, *v110, v160);
        }
      }
      else
      {
        *(_QWORD *)(v156 + 32) = *(_QWORD *)(v5 - 16);
        sqlite3ExprSetHeightAndFlags(a5, *v110);
      }
LABEL_351:
      if ( *(_DWORD *)(v5 - 64) )
      {
        v111 = sqlite3PExpr(v153, 19, *v110);
LABEL_265:
        *v110 = v111;
      }
LABEL_441:
      v196 = word_1400B29C0[a2];
      v197 = *((char *)qword_1400B1F20 + a2);
      v198 = 3 * v197;
      result = yy_find_reduce_action(*(unsigned __int16 *)(v5 + 24 * v197), v196);
      v200 = (_WORD *)(v5 + 8 * (v198 + 3));
      *a1 = (__int64)v200;
      *v200 = result;
      v200[1] = v196;
      return result;
    case 0xDCu:
      v161 = sqlite3PExpr(a5, 138, 0);
      *(_QWORD *)(v5 - 40) = v161;
      goto LABEL_354;
    case 0xDDu:
      v144 = a5;
      v162 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88));
      v163 = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(v5 - 88) = v162;
      sqlite3PExprAddSelect(a5, v162, v163);
      goto LABEL_324;
    case 0xDEu:
      v144 = a5;
      v164 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 - 16);
      v165 = sqlite3SelectNew((_DWORD)a5, 0, v164, 0, 0, 0, 0, 0, 0);
      v166 = v165;
      if ( *(_QWORD *)(v5 + 8) )
        sqlite3SrcListFuncArgs(a5, v164 & -(__int64)(v165 != 0));
      v167 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88));
      *(_QWORD *)(v5 - 88) = v167;
      sqlite3PExprAddSelect(a5, v167, v166);
LABEL_324:
      if ( !*(_DWORD *)(v5 - 64) )
        goto LABEL_441;
      v107 = *(_QWORD *)(v5 - 88);
      v109 = v144;
      v108 = 19;
      goto LABEL_261;
    case 0xDFu:
      v161 = sqlite3PExpr(a5, 20, 0);
      *(_QWORD *)(v5 - 64) = v161;
LABEL_354:
      sqlite3PExprAddSelect(a5, v161, *(_QWORD *)(v5 - 16));
      goto LABEL_441;
    case 0xE0u:
      v168 = sqlite3PExpr(a5, 157, *(_QWORD *)(v5 - 64));
      v169 = *(_QWORD *)(v5 - 40);
      *(_QWORD *)(v5 - 88) = v168;
      if ( v168 )
      {
        v170 = *(_QWORD *)(v5 - 16);
        if ( v170 )
          v169 = sqlite3ExprListAppend(a5, v169, v170);
        *(_QWORD *)(*(_QWORD *)(v5 - 88) + 32LL) = v169;
        sqlite3ExprSetHeightAndFlags(a5, *(_QWORD *)(v5 - 88));
      }
      else
      {
        sqlite3ExprListDelete(*a5, v169);
        sqlite3ExprDelete(*a5, *(_QWORD *)(v5 - 16));
      }
      goto LABEL_441;
    case 0xE1u:
      v171 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
      v58 = *(_QWORD *)(v5 + 8);
      v57 = v171;
      v59 = a5;
      *(_QWORD *)(v5 - 88) = v171;
LABEL_148:
      appended = sqlite3ExprListAppend(v59, v57, v58);
      goto LABEL_440;
    case 0xE2u:
      v172 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      v173 = *(_QWORD *)(v5 + 8);
      *(_QWORD *)(v5 - 64) = v172;
      v46 = sqlite3ExprListAppend(a5, v172, v173);
      goto LABEL_129;
    case 0xE7u:
      v51 = *(_QWORD *)(v5 + 8);
      v52 = a5;
LABEL_142:
      v53 = sqlite3ExprListAppend(v52, *(_QWORD *)(v5 - 40), v51);
      goto LABEL_143;
    case 0xE8u:
      v80 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_189;
    case 0xEBu:
      v174 = *(_DWORD *)(v5 - 184);
      v175 = *(void **)(v5 + 8);
      v176 = *(_DWORD *)(v5 - 232);
      v177 = *(int **)(v5 - 40);
      v178 = sqlite3SrcListAppend(a5, 0, v5 - 88, 0);
      sqlite3CreateIndex(a5, v5 - 160, v5 - 136, v178, v177, v176, v5 - 256, v175, 0, v174, 0);
      if ( *((_BYTE *)a5 + 300) >= 2u )
      {
        v179 = (_QWORD *)a5[44];
        if ( v179 )
          sqlite3RenameTokenMap(a5, *v179, v5 - 88);
      }
      goto LABEL_441;
    case 0xF0u:
      appended = parserAddExprIdListTerm(
                   (_DWORD)a5,
                   *(_QWORD *)(v5 - 88),
                   (int)v5 - 40,
                   *(_DWORD *)(v5 - 16),
                   *(_DWORD *)(v5 + 8));
      goto LABEL_440;
    case 0xF1u:
      v53 = parserAddExprIdListTerm((_DWORD)a5, 0, (int)v5 - 40, *(_DWORD *)(v5 - 16), *(_DWORD *)(v5 + 8));
      goto LABEL_143;
    case 0xF4u:
      sqlite3DropIndex(a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 - 16));
      goto LABEL_441;
    case 0xF5u:
      v180 = 0;
      goto LABEL_377;
    case 0xF6u:
      v180 = v5 - 16;
LABEL_377:
      sqlite3Vacuum(a5, v180, *(_QWORD *)(v5 + 8));
      goto LABEL_441;
    case 0xF9u:
      v181 = v5 + 8;
      v182 = 0;
      v183 = v5 - 16;
      goto LABEL_380;
    case 0xFAu:
      v182 = v5 + 8;
      v181 = v5 - 40;
      v183 = v5 - 64;
      goto LABEL_380;
    case 0xFBu:
      v182 = v5 - 16;
      v181 = v5 - 64;
      v183 = v5 - 88;
LABEL_380:
      sqlite3Pragma((_QWORD **)a5, v183, v181, v182, 0);
      goto LABEL_441;
    case 0xFCu:
      v184 = v5 + 8;
      v185 = v5 - 40;
      v186 = v5 - 64;
      goto LABEL_385;
    case 0xFDu:
      v184 = v5 - 16;
      v185 = v5 - 64;
      v186 = v5 - 88;
LABEL_385:
      sqlite3Pragma((_QWORD **)a5, v186, v185, v184, 1);
      goto LABEL_441;
    case 0x100u:
      v187 = *(_QWORD *)(v5 - 16);
      *(_QWORD *)&v210 = *(_QWORD *)(v5 - 64);
      *((_QWORD *)&v210 + 1) = (unsigned int)(*(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 64));
      sqlite3FinishTrigger(a5, v187, &v210);
      goto LABEL_441;
    case 0x101u:
      sqlite3BeginTrigger(
        a5,
        v5 - 160,
        v5 - 136,
        *(_DWORD *)(v5 - 112),
        *(_DWORD *)(v5 - 88),
        *(_QWORD *)(v5 - 80),
        *(_QWORD *)(v5 - 40),
        *(_QWORD *)(v5 + 8),
        *(_DWORD *)(v5 - 232),
        *(_DWORD *)(v5 - 184));
      *(_OWORD *)(v5 - 232) = *(_OWORD *)(v5 - ((-(__int64)(*(_DWORD *)(v5 - 128) != 0) & 0xFFFFFFFFFFFFFFE8uLL) + 160));
      goto LABEL_441;
    case 0x103u:
      *(_DWORD *)(v5 - 16) = 65;
      goto LABEL_441;
    case 0x104u:
      *(_DWORD *)(v5 + 32) = 33;
      goto LABEL_441;
    case 0x105u:
    case 0x106u:
      *(_DWORD *)(v5 + 8) = *(unsigned __int16 *)(v5 + 2);
      *(_QWORD *)(v5 + 16) = 0;
      goto LABEL_441;
    case 0x107u:
      *(_QWORD *)(v5 - 32) = *(_QWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 40) = 129;
      goto LABEL_441;
    case 0x10Au:
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 - 40) + 88LL) + 80LL) = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(*(_QWORD *)(v5 - 40) + 88LL) = *(_QWORD *)(v5 - 16);
      goto LABEL_441;
    case 0x10Bu:
      *(_QWORD *)(*(_QWORD *)(v5 - 16) + 88LL) = *(_QWORD *)(v5 - 16);
      goto LABEL_441;
    case 0x10Cu:
      *(_OWORD *)(v5 - 40) = *(_OWORD *)(v5 + 8);
      sqlite3ErrorMsg(
        a5,
        "qualified table names are not allowed on INSERT, UPDATE, and DELETE statements within triggers");
      goto LABEL_441;
    case 0x10Du:
      sqlite3ErrorMsg(a5, "the INDEXED BY clause is not allowed on UPDATE or DELETE statements within triggers");
      goto LABEL_441;
    case 0x10Eu:
      sqlite3ErrorMsg(a5, "the NOT INDEXED clause is not allowed on UPDATE or DELETE statements within triggers");
      goto LABEL_441;
    case 0x10Fu:
      updated = sqlite3TriggerUpdateStep(
                  (_DWORD)a5,
                  (int)v5 - 136,
                  *(_QWORD *)(v5 - 40),
                  *(_QWORD *)(v5 - 64),
                  *(_QWORD *)(v5 - 16),
                  *(_BYTE *)(v5 - 160),
                  *(_QWORD *)(v5 - 184),
                  *(_QWORD *)(v5 + 8));
LABEL_122:
      *(_QWORD *)(v5 - 184) = updated;
      goto LABEL_441;
    case 0x110u:
      inserted = sqlite3TriggerInsertStep(
                   (_DWORD)a5,
                   (int)v5 - 88,
                   *(_QWORD *)(v5 - 64),
                   *(_QWORD *)(v5 - 40),
                   *(_BYTE *)(v5 - 136),
                   *(_QWORD *)(v5 - 16),
                   *(_QWORD *)(v5 - 160),
                   *(_QWORD *)(v5 + 8));
LABEL_245:
      *(_QWORD *)(v5 - 160) = inserted;
      goto LABEL_441;
    case 0x111u:
      v63 = sqlite3TriggerDeleteStep(
              (_DWORD)a5,
              (int)v5 - 64,
              *(_QWORD *)(v5 - 16),
              *(_QWORD *)(v5 - 112),
              *(_QWORD *)(v5 + 8));
      goto LABEL_158;
    case 0x112u:
      v53 = sqlite3TriggerSelectStep(*a5, *(_QWORD *)(v5 - 16), *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_143;
    case 0x113u:
      v188 = sqlite3PExpr(a5, 71, 0);
      *(_QWORD *)(v5 - 64) = v188;
      if ( v188 )
        *(_BYTE *)(v188 + 1) = 4;
      goto LABEL_441;
    case 0x114u:
      v189 = sqlite3ExprAlloc(*a5, 71, v5 - 16);
      *(_QWORD *)(v5 - 112) = v189;
      if ( v189 )
        *(_BYTE *)(v189 + 1) = *(_BYTE *)(v5 - 64);
      goto LABEL_441;
    case 0x117u:
      *(_DWORD *)(v5 + 8) = 3;
      goto LABEL_441;
    case 0x118u:
      sqlite3DropTrigger(a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 - 16));
      goto LABEL_441;
    case 0x119u:
      sqlite3Attach(a5, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16), *(_QWORD *)(v5 + 8));
      goto LABEL_441;
    case 0x11Au:
      sqlite3Detach(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_441;
    case 0x11Du:
      v190 = 0;
      v191 = 0;
      goto LABEL_412;
    case 0x11Eu:
      v190 = v5 + 8;
      v191 = v5 - 16;
LABEL_412:
      sqlite3Reindex(a5, v191, v190);
      goto LABEL_441;
    case 0x11Fu:
      v192 = 0;
      v193 = 0;
      goto LABEL_415;
    case 0x120u:
      v192 = v5 + 8;
      v193 = v5 - 16;
LABEL_415:
      sqlite3Analyze(a5, v193, v192);
      goto LABEL_441;
    case 0x121u:
      sqlite3AlterRenameTable(a5, *(_QWORD *)(v5 - 64), v5 + 8);
      goto LABEL_441;
    case 0x122u:
      *(_DWORD *)(v5 - 8) = *((_DWORD *)a5 + 70) + *((_DWORD *)a5 + 72) - *(_DWORD *)(v5 - 16);
      sqlite3AlterFinishAddColumn();
      goto LABEL_441;
    case 0x123u:
      sqlite3AlterDropColumn(a5, *(_QWORD *)(v5 - 64), v5 + 8);
      goto LABEL_441;
    case 0x124u:
      disableLookaside(a5);
      sqlite3AlterBeginAddColumn(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_441;
    case 0x125u:
      sqlite3AlterRenameColumn(a5, *(_QWORD *)(v5 - 112), v5 - 40, (unsigned __int8 **)(v5 + 8));
      goto LABEL_441;
    case 0x126u:
      v194 = 0;
      goto LABEL_423;
    case 0x127u:
      v194 = v5 + 8;
LABEL_423:
      sqlite3VtabFinishParse(a5, v194);
      goto LABEL_441;
    case 0x128u:
      sqlite3VtabBeginParse((_DWORD)a5, v5 - 64, v5 - 40, v5 + 8, *(_DWORD *)(v5 - 88));
      goto LABEL_441;
    case 0x129u:
      sqlite3VtabArgInit(a5);
      goto LABEL_441;
    case 0x12Au:
    case 0x12Bu:
    case 0x12Cu:
      sqlite3VtabArgExtend(a5, v5 + 8);
      goto LABEL_441;
    case 0x12Du:
    case 0x12Eu:
      LOBYTE(a3) = 1;
      sqlite3WithPush(a5, *(_QWORD *)(v5 + 8), a3);
      goto LABEL_441;
    case 0x12Fu:
      *(_BYTE *)(v5 + 8) = 1;
      goto LABEL_441;
    case 0x130u:
      *(_BYTE *)(v5 - 16) = 0;
      goto LABEL_441;
    case 0x131u:
      *(_BYTE *)(v5 - 40) = 2;
      goto LABEL_441;
    case 0x132u:
      v63 = sqlite3CteNew((_DWORD)a5, (int)v5 - 112, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 16), *(_BYTE *)(v5 - 64));
      goto LABEL_158;
    case 0x133u:
      v80 = sqlite3WithAdd(a5, 0, *(_QWORD *)(v5 + 8));
LABEL_189:
      *(_QWORD *)(v5 + 8) = v80;
      goto LABEL_441;
    case 0x134u:
      v53 = sqlite3WithAdd(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_143;
    case 0x135u:
      sqlite3WindowChain(a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 40));
      *(_QWORD *)(*(_QWORD *)(v5 + 8) + 64LL) = *(_QWORD *)(v5 - 40);
LABEL_436:
      v53 = *(_QWORD *)(v5 + 8);
      goto LABEL_143;
    case 0x136u:
      v195 = *(_QWORD **)(v5 - 16);
      if ( v195 )
        *v195 = sqlite3DbStrNDup(*a5, *(_QWORD *)(v5 - 88), *(unsigned int *)(v5 - 80));
      goto LABEL_439;
    case 0x137u:
      appended = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 - 16), 0);
      goto LABEL_440;
    case 0x138u:
      v201 = *(_QWORD *)(v5 - 16);
      v110 = (_QWORD *)(v5 - 112);
      v202 = *(_QWORD *)(v5 - 40);
      goto LABEL_444;
    case 0x139u:
      v46 = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), 0, *(_QWORD *)(v5 - 16), 0);
      goto LABEL_129;
    case 0x13Au:
      v201 = *(_QWORD *)(v5 - 16);
      v110 = (_QWORD *)(v5 - 88);
      goto LABEL_447;
    case 0x13Bu:
      v110 = (_QWORD *)(v5 - 16);
      LODWORD(v201) = 0;
LABEL_447:
      LODWORD(v202) = 0;
LABEL_444:
      v111 = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), v202, v201, (__int64)v110);
      goto LABEL_265;
    case 0x13Cu:
      v14 = sqlite3WindowAlloc((_DWORD)a5, 0, 90, 0, 85, 0, 0);
LABEL_40:
      *(_QWORD *)(v5 + 32) = v14;
      goto LABEL_441;
    case 0x13Du:
      v53 = sqlite3WindowAlloc(
              (_DWORD)a5,
              *(_DWORD *)(v5 - 40),
              *(_DWORD *)(v5 - 16),
              *(_QWORD *)(v5 - 8),
              85,
              0,
              *(_BYTE *)(v5 + 8));
LABEL_143:
      *(_QWORD *)(v5 - 40) = v53;
      goto LABEL_441;
    case 0x13Eu:
      v63 = sqlite3WindowAlloc(
              (_DWORD)a5,
              *(_DWORD *)(v5 - 112),
              *(_DWORD *)(v5 - 64),
              *(_QWORD *)(v5 - 56),
              *(_DWORD *)(v5 - 16),
              *(_QWORD *)(v5 - 8),
              *(_BYTE *)(v5 + 8));
      goto LABEL_158;
    case 0x141u:
    case 0x143u:
    case 0x145u:
      LODWORD(v210) = *(unsigned __int16 *)(v5 - 22);
      v85 = v210;
LABEL_201:
      *(_QWORD *)(v5 - 16) = v85;
      *(_QWORD *)(v5 - 8) = 0;
      goto LABEL_441;
    case 0x144u:
      v203 = *(_QWORD *)(v5 - 16);
      LODWORD(v210) = *(unsigned __int16 *)(v5 + 2);
      *(_QWORD *)(v5 - 16) = v210;
      *(_QWORD *)(v5 - 8) = v203;
      goto LABEL_441;
    case 0x146u:
      *(_BYTE *)(v5 + 32) = 0;
      goto LABEL_441;
    case 0x147u:
      v204 = *(_BYTE *)(v5 + 8);
      goto LABEL_456;
    case 0x148u:
    case 0x149u:
      v204 = *(_BYTE *)(v5 - 22);
LABEL_456:
      *(_BYTE *)(v5 - 16) = v204;
      goto LABEL_441;
    case 0x14Au:
      *(_BYTE *)(v5 + 8) = *(_BYTE *)(v5 + 2);
      goto LABEL_441;
    case 0x14Cu:
      v205 = *(_QWORD *)(v5 + 8);
      v206 = *(_QWORD *)(v5 - 16);
      if ( v205 )
        *(_QWORD *)(v205 + 72) = v206;
      else
        sqlite3ExprDelete(*a5, v206);
LABEL_210:
      v88 = *(_QWORD *)(v5 + 8);
LABEL_211:
      *(_QWORD *)(v5 - 16) = v88;
      goto LABEL_441;
    case 0x14Eu:
      v207 = sqlite3DbMallocZero(*a5, 144);
      v208 = v207;
      if ( v207 )
      {
        *(_BYTE *)(v207 + 32) = -90;
        *(_QWORD *)(v207 + 72) = *(_QWORD *)(v5 + 8);
      }
      else
      {
        sqlite3ExprDelete(*a5, *(_QWORD *)(v5 + 8));
      }
      *(_QWORD *)(v5 + 8) = v208;
      goto LABEL_441;
    case 0x14Fu:
      v46 = *(_QWORD *)(v5 - 16);
LABEL_129:
      *(_QWORD *)(v5 - 64) = v46;
      goto LABEL_441;
    case 0x150u:
      v209 = sqlite3DbMallocZero(*a5, 144);
      *(_QWORD *)(v5 - 16) = v209;
      v110 = (_QWORD *)v209;
      if ( !v209 )
        goto LABEL_441;
      v111 = sqlite3DbStrNDup(*a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 + 16));
      goto LABEL_265;
    case 0x151u:
LABEL_439:
      appended = *(_QWORD *)(v5 - 16);
      goto LABEL_440;
    default:
      goto LABEL_441;
  }
}

```

## disassembly

```asm
0x1400a40bc  mov     rax, rsp
0x1400a40bf  mov     [rax+18h], rbx
0x1400a40c3  mov     [rax+10h], edx
0x1400a40c6  mov     [rax+8], rcx
0x1400a40ca  push    rbp
0x1400a40cb  push    rsi
0x1400a40cc  push    rdi
0x1400a40cd  push    r12
0x1400a40cf  push    r13
0x1400a40d1  push    r14
0x1400a40d3  push    r15
0x1400a40d5  lea     rbp, [rax-57h]
0x1400a40d9  sub     rsp, 0B0h
0x1400a40e0  mov     r12, [rcx]
0x1400a40e3  lea     rcx, __ImageBase
0x1400a40ea  cmp     edx, 151h; switch 338 cases
0x1400a40f0  ja      def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a40f6  mov     eax, edx
0x1400a40f8  mov     r8d, ds:(jpt_1400A4103 - 140000000h)[rcx+rax*4]
0x1400a4100  add     r8, rcx
0x1400a4103  jmp     r8; switch jump
0x1400a4106  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001400A4103 case 0
0x1400a410a  xor     r13d, r13d
0x1400a410d  cmp     [rax+148h], r13
0x1400a4114  jnz     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a411a  mov     byte ptr [rax+12Bh], 1
0x1400a4121  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a4126  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001400A4103 case 1
0x1400a412a  xor     r13d, r13d
0x1400a412d  cmp     [rax+148h], r13
0x1400a4134  jnz     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a413a  mov     byte ptr [rax+12Bh], 2
0x1400a4141  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a4146  mov     rcx, [rbp+4Fh+arg_20]; jumptable 00000001400A4103 case 2
0x1400a414a  call    sqlite3FinishCoding
0x1400a414f  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a4154  mov     edx, [r12-10h]; jumptable 00000001400A4103 case 3
0x1400a4159  mov     rcx, [rbp+4Fh+arg_20]
0x1400a415d  call    sqlite3BeginTransaction
0x1400a4162  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a4167  mov     dword ptr [r12+20h], 7; jumptable 00000001400A4103 case 4
0x1400a4170  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a4175  movzx   eax, word ptr [r12+2]; jumptable 00000001400A4103 cases 5-7,89,91,258,319
0x1400a417b  mov     [r12+8], eax
0x1400a4180  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a4185  movzx   edx, word ptr [r12-16h]; jumptable 00000001400A4103 cases 8,9
0x1400a418b  mov     rcx, [rbp+4Fh+arg_20]
0x1400a418f  call    sqlite3EndTransaction
0x1400a4194  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a4199  xor     edx, edx; jumptable 00000001400A4103 case 10
0x1400a419b  mov     rcx, [rbp+4Fh+arg_20]
0x1400a419f  lea     r8, [r12+8]
0x1400a41a4  call    sqlite3Savepoint
0x1400a41a9  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a41ae  mov     edx, 1; jumptable 00000001400A4103 case 11
0x1400a41b3  jmp     short loc_1400A419B
0x1400a41b5  mov     edx, 2; jumptable 00000001400A4103 case 12
0x1400a41ba  jmp     short loc_1400A419B
0x1400a41bc  mov     eax, [r12-28h]; jumptable 00000001400A4103 case 13
0x1400a41c1  lea     r8, [r12+8]
0x1400a41c6  mov     r9d, [r12-58h]
0x1400a41cb  lea     rdx, [r12-10h]
0x1400a41d0  mov     rcx, [rbp+4Fh+arg_20]
0x1400a41d4  xor     r13d, r13d
0x1400a41d7  mov     dword ptr [rsp+0E0h+var_B0], eax
0x1400a41db  mov     dword ptr [rsp+0E0h+var_B8], r13d
0x1400a41e0  mov     dword ptr [rsp+0E0h+var_C0], r13d
0x1400a41e5  call    sqlite3StartTable
0x1400a41ea  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a41ef  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001400A4103 case 14
0x1400a41f3  inc     byte ptr [rax+24h]
0x1400a41f6  mov     rcx, [rax]
0x1400a41f9  inc     dword ptr [rcx+1A0h]
0x1400a41ff  xor     r13d, r13d
0x1400a4202  mov     [rcx+1A4h], r13w
0x1400a420a  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a420f  mov     dword ptr [r12-28h], 1; jumptable 00000001400A4103 case 16
0x1400a4218  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a421d  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001400A4103 case 17
0x1400a4221  xor     r13d, r13d
0x1400a4224  mov     rcx, [rax]
0x1400a4227  cmp     [rcx+0C5h], r13b
0x1400a422e  setz    r13b
0x1400a4232  mov     [r12+8], r13d
0x1400a4237  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a423c  mov     r9d, [r12+8]; jumptable 00000001400A4103 case 19
0x1400a4241  lea     r8, [r12-10h]
0x1400a4246  mov     rcx, [rbp+4Fh+arg_20]
0x1400a424a  lea     rdx, [r12-28h]
0x1400a424f  xor     r13d, r13d
0x1400a4252  mov     [rsp+0E0h+var_C0], r13
0x1400a4257  call    sqlite3EndTable
0x1400a425c  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a4261  mov     rax, [r12+8]; jumptable 00000001400A4103 case 20
0x1400a4266  xor     r9d, r9d
0x1400a4269  mov     rbx, [rbp+4Fh+arg_20]
0x1400a426d  xor     r8d, r8d
0x1400a4270  mov     rcx, rbx
0x1400a4273  mov     [rsp+0E0h+var_C0], rax
0x1400a4278  xor     edx, edx
0x1400a427a  call    sqlite3EndTable
0x1400a427f  mov     rdx, [r12+8]
0x1400a4284  test    rdx, rdx
0x1400a4287  jz      def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a428d  mov     rcx, [rbx]
0x1400a4290  mov     r8d, 1
0x1400a4296  call    clearSelect
0x1400a429b  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a42a0  mov     eax, [r12+8]; jumptable 00000001400A4103 case 22
0x1400a42a5  or      [r12-28h], eax
0x1400a42aa  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a42af  xor     r13d, r13d; jumptable 00000001400A4103 case 23
0x1400a42b2  cmp     dword ptr [r12+10h], 5
0x1400a42b8  jnz     short loc_1400A42E1
0x1400a42ba  mov     rcx, [r12+8]
0x1400a42bf  lea     r8d, [r13+5]
0x1400a42c3  lea     rdx, aRowid_1; "rowid"
0x1400a42ca  call    sqlite3_strnicmp
0x1400a42cf  test    eax, eax
0x1400a42d1  jnz     short loc_1400A42E1
0x1400a42d3  mov     dword ptr [r12-10h], 280h
0x1400a42dc  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a42e1  mov     r9, [r12+8]
0x1400a42e6  lea     rdx, aUnknownTableOp; "unknown table option: %.*s"
0x1400a42ed  mov     r8d, [r12+10h]
0x1400a42f2  mov     rcx, [rbp+4Fh+arg_20]
0x1400a42f6  mov     [r12-10h], r13d
0x1400a42fb  call    sqlite3ErrorMsg
0x1400a4300  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a4305  xor     r13d, r13d; jumptable 00000001400A4103 case 24
0x1400a4308  lea     r8d, [r13+6]
0x1400a430c  cmp     [r12+10h], r8d
0x1400a4311  jnz     short loc_1400A4333
0x1400a4313  mov     rcx, [r12+8]
0x1400a4318  lea     rdx, aStrict; "strict"
0x1400a431f  call    sqlite3_strnicmp
0x1400a4324  test    eax, eax
0x1400a4326  jnz     short loc_1400A4333
0x1400a4328  mov     r13d, 10000h
0x1400a432e  jmp     loc_1400A4232
0x1400a4333  mov     r9, [r12+8]
0x1400a4338  lea     rdx, aUnknownTableOp; "unknown table option: %.*s"
0x1400a433f  mov     r8d, [r12+10h]
0x1400a4344  mov     rcx, [rbp+4Fh+arg_20]
0x1400a4348  call    sqlite3ErrorMsg
0x1400a434d  jmp     loc_1400A4232
0x1400a4352  movups  xmm0, xmmword ptr [r12+8]; jumptable 00000001400A4103 case 25
0x1400a4358  mov     rcx, [rbp+4Fh+arg_20]
0x1400a435c  lea     r8, [rbp+4Fh+var_80]
0x1400a4360  movups  xmm1, xmmword ptr [r12-10h]
0x1400a4366  lea     rdx, [rbp+4Fh+var_70]
0x1400a436a  movdqu  [rbp+4Fh+var_80], xmm0
0x1400a436f  movdqu  [rbp+4Fh+var_70], xmm1
0x1400a4374  call    sqlite3AddColumn
0x1400a4379  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a437e  xor     r13d, r13d; jumptable 00000001400A4103 cases 26,65,104
0x1400a4381  mov     [r12+28h], r13d
0x1400a4386  mov     [r12+20h], r13
0x1400a438b  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a4390  mov     eax, [r12+10h]; jumptable 00000001400A4103 case 27
0x1400a4395  sub     eax, [r12-40h]
0x1400a439a  add     eax, [r12+8]
0x1400a439f  mov     [r12-38h], eax
0x1400a43a4  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a43a9  mov     eax, [r12+10h]; jumptable 00000001400A4103 case 28
0x1400a43ae  sub     eax, [r12-70h]
0x1400a43b3  add     eax, [r12+8]
0x1400a43b8  mov     [r12-68h], eax
0x1400a43bd  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a43c2  mov     eax, [r12+10h]; jumptable 00000001400A4103 case 29
0x1400a43c7  sub     eax, [r12-10h]
0x1400a43cc  add     eax, [r12+8]
0x1400a43d1  mov     [r12-8], eax
0x1400a43d6  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a43db  mov     rax, [r9]; jumptable 00000001400A4103 case 30
0x1400a43de  mov     [r12+20h], rax
0x1400a43e3  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a43e8  movups  xmm0, xmmword ptr [r9]; jumptable 00000001400A4103 case 31
0x1400a43ec  movdqu  xmmword ptr [r12+20h], xmm0
0x1400a43f3  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a43f8  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001400A4103 cases 32,67
0x1400a43fc  movups  xmm0, xmmword ptr [r12+8]
0x1400a4402  movdqu  xmmword ptr [rax+68h], xmm0
0x1400a4407  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a440c  mov     r8, [r12-10h]; jumptable 00000001400A4103 case 33
0x1400a4411  mov     r9d, [r12-8]
0x1400a4416  add     r9, r8
0x1400a4419  mov     rdx, [r12+8]
0x1400a441e  mov     rcx, [rbp+4Fh+arg_20]
0x1400a4422  call    sqlite3AddDefaultValue
0x1400a4427  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a442c  mov     r8, [r12-28h]; jumptable 00000001400A4103 case 34
0x1400a4431  mov     r9, [r12+8]
0x1400a4436  inc     r8
0x1400a4439  mov     rdx, [r12-10h]
0x1400a443e  jmp     short loc_1400A441E
0x1400a4440  mov     r9d, [r12-8]; jumptable 00000001400A4103 case 35
0x1400a4445  add     r9, [r12-10h]
0x1400a444a  mov     r8, [r12-28h]
0x1400a444f  jmp     short loc_1400A4419
0x1400a4451  mov     r8, [r12+8]; jumptable 00000001400A4103 case 36
0x1400a4456  xor     r9d, r9d
0x1400a4459  mov     rcx, [rbp+4Fh+arg_20]
0x1400a445d  mov     edx, 0ADh
0x1400a4462  call    sqlite3PExpr
0x1400a4467  mov     r9d, [r12-8]
0x1400a446c  mov     rdx, rax
0x1400a446f  add     r9, [r12-10h]
0x1400a4474  mov     r8, [r12-28h]
0x1400a4479  jmp     short loc_1400A441E
0x1400a447b  movups  xmm0, xmmword ptr [r12+8]; jumptable 00000001400A4103 case 37
0x1400a4481  mov     rcx, [rbp+4Fh+arg_20]
0x1400a4485  lea     r8, [rbp+4Fh+var_70]
0x1400a4489  mov     edx, 75h ; 'u'
0x1400a448e  movdqu  [rbp+4Fh+var_70], xmm0
0x1400a4493  call    tokenExpr
0x1400a4498  mov     rbx, rax
0x1400a449b  test    rax, rax
0x1400a449e  jz      short loc_1400A44A8
0x1400a44a0  mov     rcx, rax
0x1400a44a3  call    sqlite3ExprIdToTrueFalse
0x1400a44a8  mov     r8, [r12+8]
0x1400a44ad  mov     rdx, rbx
0x1400a44b0  mov     r9d, [r12+10h]
0x1400a44b5  add     r9, r8
0x1400a44b8  jmp     loc_1400A441E
0x1400a44bd  mov     edx, [r12+8]; jumptable 00000001400A4103 case 38
0x1400a44c2  mov     rcx, [rbp+4Fh+arg_20]
0x1400a44c6  call    sqlite3AddNotNull
0x1400a44cb  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a44d0  mov     eax, [r12-28h]; jumptable 00000001400A4103 case 39
0x1400a44d5  xor     edx, edx
0x1400a44d7  mov     r9d, [r12+8]
0x1400a44dc  mov     r8d, [r12-10h]
0x1400a44e1  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1400a44e5  mov     rcx, [rbp+4Fh+arg_20]
0x1400a44e9  call    sqlite3AddPrimaryKey
0x1400a44ee  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a44f3  mov     eax, [r12+8]; jumptable 00000001400A4103 case 40
0x1400a44f8  xor     r13d, r13d
0x1400a44fb  mov     byte ptr [rsp+50h], 1
0x1400a4500  mov     dword ptr [rsp+0E0h+var_98], r13d
0x1400a4505  mov     [rsp+0E0h+var_A0], r13d
0x1400a450a  mov     [rsp+0E0h+var_A8], r13
0x1400a450f  mov     [rsp+0E0h+var_B0], r13
0x1400a4514  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1400a4518  mov     [rsp+0E0h+var_C0], r13
0x1400a451d  mov     rcx, [rbp+4Fh+arg_20]
0x1400a4521  xor     r9d, r9d
0x1400a4524  xor     r8d, r8d
0x1400a4527  xor     edx, edx
0x1400a4529  call    sqlite3CreateIndex
0x1400a452e  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a4533  mov     r9, [r12+8]; jumptable 00000001400A4103 case 41
0x1400a4538  mov     r8, [r12-28h]
0x1400a453d  mov     rdx, [r12-10h]
0x1400a4542  mov     rcx, [rbp+4Fh+arg_20]
0x1400a4546  call    sqlite3AddCheckConstraint
0x1400a454b  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a4550  mov     eax, [r12+8]; jumptable 00000001400A4103 case 42
0x1400a4555  lea     r8, [r12-28h]
0x1400a455a  mov     r9, [r12-10h]
0x1400a455f  xor     edx, edx
0x1400a4561  mov     rcx, [rbp+4Fh+arg_20]
0x1400a4565  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1400a4569  call    sqlite3CreateForeignKey
0x1400a456e  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a4573  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001400A4103 case 43
0x1400a4577  xor     r13d, r13d
0x1400a457a  mov     rcx, [rax+158h]
0x1400a4581  test    rcx, rcx
0x1400a4584  jz      def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a458a  cmp     [rcx+3Fh], r13b
0x1400a458e  jnz     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a4594  mov     rdx, [rcx+48h]
0x1400a4598  test    rdx, rdx
0x1400a459b  jz      def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a45a1  mov     al, [r12+8]
0x1400a45a6  mov     [rdx+2Ch], al
0x1400a45a9  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a45ae  mov     rcx, [rbp+4Fh+arg_20]; jumptable 00000001400A4103 case 44
0x1400a45b2  lea     rdx, [r12+8]
0x1400a45b7  call    sqlite3AddCollateType
0x1400a45bc  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a45c1  mov     rdx, [r12-10h]; jumptable 00000001400A4103 case 45
0x1400a45c6  xor     r8d, r8d
0x1400a45c9  mov     rcx, [rbp+4Fh+arg_20]
0x1400a45cd  call    sqlite3AddGenerated
0x1400a45d2  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a45d7  mov     rdx, [r12-28h]; jumptable 00000001400A4103 case 46
0x1400a45dc  lea     r8, [r12+8]
0x1400a45e1  jmp     short loc_1400A45C9
0x1400a45e3  mov     dword ptr [r12+8], 1; jumptable 00000001400A4103 cases 48,96,122,137,277
0x1400a45ec  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a45f1  xor     r13d, r13d; jumptable 00000001400A4103 cases 15,18,21,47,49,62,72,81,98,237,242
0x1400a45f4  mov     [r12+20h], r13d
0x1400a45f9  jmp     def_1400A4103; jumptable 00000001400A4103 default case, cases 320,322,333
0x1400a45fe  mov     eax, [r12+0Ch]; jumptable 00000001400A4103 case 50
0x1400a4603  not     eax
0x1400a4605  and     eax, [r12-10h]
  ... truncated ...
```
