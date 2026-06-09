# SyncWorkThread

- ea: `0x18000c2a0`
- end: `0x18000dfd2`
- name: `SyncWorkThread`
- size: `7474`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, int *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001aa0`
- `0x18000231e`
- `0x18000b8a4`
- `0x18000bb10`
- `0x18000c024`
- `0x18000c2a0`

## import_xrefs

- `ntdll!RtlExtendCorrelationVector` at `0x18000cdb3`
- `ntdll!RtlExtendCorrelationVector` at `0x18000cdb3`
- `ntdll!RtlComputeCrc32` at `0x18000c39a`
- `ntdll!RtlComputeCrc32` at `0x18000c39a`
- `ntdll!RtlNtStatusToDosError` at `0x18000c548`
- `ntdll!RtlNtStatusToDosError` at `0x18000c655`
- `ntdll!RtlNtStatusToDosError` at `0x18000c75c`
- `ntdll!RtlNtStatusToDosError` at `0x18000c7ed`
- `ntdll!RtlNtStatusToDosError` at `0x18000c883`
- `ntdll!RtlNtStatusToDosError` at `0x18000c910`
- `ntdll!RtlNtStatusToDosError` at `0x18000ce31`
- `ntdll!RtlNtStatusToDosError` at `0x18000cec8`
- `ntdll!RtlNtStatusToDosError` at `0x18000cf58`
- `ntdll!RtlNtStatusToDosError` at `0x18000d074`
- `ntdll!RtlNtStatusToDosError` at `0x18000d107`
- `ntdll!RtlNtStatusToDosError` at `0x18000d1c7`
- `ntdll!RtlNtStatusToDosError` at `0x18000d334`
- `ntdll!RtlNtStatusToDosError` at `0x18000d3dd`
- `ntdll!RtlNtStatusToDosError` at `0x18000d5f8`
- `ntdll!RtlNtStatusToDosError` at `0x18000d694`
- `ntdll!RtlNtStatusToDosError` at `0x18000d79c`
- `ntdll!RtlNtStatusToDosError` at `0x18000d82d`
- `ntdll!RtlNtStatusToDosError` at `0x18000d9e8`
- `ntdll!RtlNtStatusToDosError` at `0x18000da94`
- `ntdll!RtlNtStatusToDosError` at `0x18000db27`
- `ntdll!RtlNtStatusToDosError` at `0x18000dc1b`
- `ntdll!RtlNtStatusToDosError` at `0x18000dcbd`
- `ntdll!RtlNtStatusToDosError` at `0x18000dd50`
- `ntdll!RtlNtStatusToDosError` at `0x18000dde8`
- `ntdll!RtlNtStatusToDosError` at `0x18000de88`
- `ntdll!RtlNtStatusToDosError` at `0x18000df26`
- `ntdll!RtlNtStatusToDosError` at `0x18000c548`
- `ntdll!RtlNtStatusToDosError` at `0x18000c655`
- `ntdll!RtlNtStatusToDosError` at `0x18000c75c`
- `ntdll!RtlNtStatusToDosError` at `0x18000c7ed`
- `ntdll!RtlNtStatusToDosError` at `0x18000c883`
- `ntdll!RtlNtStatusToDosError` at `0x18000c910`
- `ntdll!RtlNtStatusToDosError` at `0x18000ce31`
- `ntdll!RtlNtStatusToDosError` at `0x18000cec8`
- `ntdll!RtlNtStatusToDosError` at `0x18000cf58`
- `ntdll!RtlNtStatusToDosError` at `0x18000d074`
- `ntdll!RtlNtStatusToDosError` at `0x18000d107`
- `ntdll!RtlNtStatusToDosError` at `0x18000d1c7`
- `ntdll!RtlNtStatusToDosError` at `0x18000d334`
- `ntdll!RtlNtStatusToDosError` at `0x18000d3dd`
- `ntdll!RtlNtStatusToDosError` at `0x18000d5f8`
- `ntdll!RtlNtStatusToDosError` at `0x18000d694`
- `ntdll!RtlNtStatusToDosError` at `0x18000d79c`
- `ntdll!RtlNtStatusToDosError` at `0x18000d82d`
- `ntdll!RtlNtStatusToDosError` at `0x18000d9e8`
- `ntdll!RtlNtStatusToDosError` at `0x18000da94`
- `ntdll!RtlNtStatusToDosError` at `0x18000db27`
- `ntdll!RtlNtStatusToDosError` at `0x18000dc1b`
- `ntdll!RtlNtStatusToDosError` at `0x18000dcbd`
- `ntdll!RtlNtStatusToDosError` at `0x18000dd50`
- `ntdll!RtlNtStatusToDosError` at `0x18000dde8`
- `ntdll!RtlNtStatusToDosError` at `0x18000de88`
- `ntdll!RtlNtStatusToDosError` at `0x18000df26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dfa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dfa2`

## pseudocode

```c
void __fastcall SyncWorkThread(PTP_CALLBACK_INSTANCE Instance, int *Context, PTP_WORK Work)
{
  int v3; // r14d
  unsigned int v4; // r14d
  __int64 v5; // rbx
  __int64 v6; // r13
  int v7; // r15d
  signed int v8; // ecx
  char *v9; // rdi
  unsigned int *v10; // r12
  unsigned int v11; // esi
  signed int v12; // ecx
  __int64 v13; // rdx
  unsigned __int64 v14; // r10
  unsigned int i; // r8d
  unsigned int v16; // eax
  unsigned __int64 v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned __int64 v20; // rcx
  unsigned int v21; // eax
  NTSTATUS v22; // esi
  unsigned __int64 v23; // rcx
  unsigned int v24; // eax
  unsigned __int16 v25; // r14
  NTSTATUS v26; // ecx
  signed int v27; // eax
  bool v28; // sf
  unsigned __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  unsigned __int64 v32; // rdx
  unsigned int v33; // eax
  NTSTATUS v34; // ecx
  signed int v35; // eax
  bool v36; // sf
  __int64 v37; // rax
  unsigned __int64 v38; // rdx
  unsigned int v39; // r8d
  NTSTATUS v40; // ecx
  signed int v41; // eax
  bool v42; // sf
  unsigned __int64 v43; // rdx
  unsigned int v44; // eax
  NTSTATUS v45; // ecx
  signed int v46; // eax
  bool v47; // sf
  unsigned __int64 v48; // rdx
  unsigned int v49; // eax
  NTSTATUS v50; // ecx
  signed int v51; // eax
  bool v52; // sf
  unsigned __int64 v53; // rdx
  unsigned int v54; // eax
  NTSTATUS v55; // ecx
  signed int v56; // eax
  bool v57; // sf
  __int64 v58; // r15
  unsigned int v59; // r14d
  char *v60; // rbx
  unsigned __int64 v61; // rdx
  unsigned int v62; // eax
  unsigned __int64 v63; // rdx
  unsigned int v64; // eax
  unsigned int *v65; // r10
  unsigned __int64 v66; // rdx
  unsigned __int64 v67; // rdx
  unsigned __int64 v68; // rdx
  unsigned int v69; // ecx
  char *v70; // rax
  unsigned __int64 v71; // rdx
  unsigned __int64 v72; // rdx
  unsigned __int64 v73; // rdx
  unsigned __int64 v74; // rdx
  unsigned int v75; // eax
  __int128 v76; // xmm0
  unsigned int v77; // eax
  char *v78; // rcx
  unsigned __int64 v79; // rdx
  unsigned int v80; // eax
  NTSTATUS v81; // ecx
  signed int v82; // eax
  bool v83; // sf
  unsigned __int64 v84; // rdx
  unsigned int v85; // eax
  NTSTATUS v86; // ecx
  signed int v87; // eax
  bool v88; // sf
  unsigned __int64 v89; // rdx
  unsigned int v90; // eax
  int v91; // r14d
  NTSTATUS v92; // ecx
  signed int v93; // eax
  bool v94; // sf
  char *v95; // r15
  unsigned __int64 v96; // rdx
  unsigned int v97; // eax
  NTSTATUS v98; // ecx
  signed int v99; // eax
  bool v100; // sf
  unsigned __int64 v101; // rdx
  unsigned int v102; // eax
  signed int v103; // eax
  bool v104; // sf
  int v105; // eax
  int v106; // eax
  __int64 v107; // rbx
  unsigned __int64 v108; // rdx
  unsigned int v109; // eax
  NTSTATUS v110; // ecx
  signed int v111; // eax
  bool v112; // sf
  unsigned __int16 v113; // r9
  unsigned __int64 v114; // rdx
  unsigned int v115; // r8d
  char *v116; // rdx
  unsigned int v117; // r9d
  unsigned __int64 v118; // r8
  unsigned int v119; // eax
  signed int v120; // eax
  bool v121; // sf
  unsigned __int64 v122; // rdx
  unsigned int v123; // eax
  NTSTATUS v124; // ecx
  signed int v125; // eax
  bool v126; // sf
  unsigned __int16 v127; // r9
  unsigned __int64 v128; // rdx
  unsigned int v129; // r8d
  char *v130; // rdx
  unsigned int v131; // r9d
  bool v132; // cf
  unsigned __int64 v133; // r8
  unsigned int v134; // eax
  unsigned __int64 v135; // rdx
  unsigned int v136; // eax
  int v137; // r13d
  NTSTATUS v138; // ecx
  signed int v139; // eax
  bool v140; // sf
  unsigned __int64 v141; // rdx
  unsigned int v142; // eax
  NTSTATUS v143; // ecx
  signed int v144; // eax
  bool v145; // sf
  char *v146; // rbx
  int v147; // eax
  unsigned int v148; // r14d
  unsigned __int16 v149; // r8
  unsigned __int64 v150; // rdx
  unsigned int v151; // eax
  NTSTATUS v152; // ecx
  signed int v153; // eax
  bool v154; // sf
  unsigned int v155; // r8d
  unsigned __int64 v156; // rdx
  unsigned int v157; // eax
  signed int v158; // eax
  bool v159; // sf
  int v160; // eax
  unsigned __int16 v161; // r9
  unsigned __int64 v162; // rdx
  unsigned int v163; // r8d
  unsigned __int64 v164; // rdx
  unsigned int v165; // eax
  signed int v166; // eax
  bool v167; // sf
  unsigned __int64 v168; // rdx
  unsigned int v169; // eax
  NTSTATUS v170; // ecx
  signed int v171; // eax
  bool v172; // sf
  unsigned __int64 v173; // rdx
  unsigned int v174; // eax
  signed int v175; // eax
  bool v176; // sf
  int v177; // eax
  unsigned __int16 v178; // r8
  unsigned __int64 v179; // rdx
  unsigned int v180; // eax
  NTSTATUS v181; // ecx
  signed int v182; // eax
  bool v183; // sf
  unsigned __int16 v184; // r8
  unsigned __int64 v185; // rdx
  unsigned int v186; // eax
  NTSTATUS v187; // ecx
  signed int v188; // eax
  bool v189; // sf
  unsigned __int64 v190; // rdx
  unsigned int v191; // eax
  NTSTATUS v192; // ecx
  signed int v193; // eax
  bool v194; // sf
  unsigned __int64 v195; // rdx
  unsigned int v196; // eax
  NTSTATUS v197; // ecx
  signed int v198; // eax
  bool v199; // sf
  unsigned __int16 v200; // r8
  unsigned __int64 v201; // rdx
  unsigned int v202; // eax
  NTSTATUS v203; // ecx
  signed int v204; // eax
  bool v205; // sf
  unsigned __int16 v206; // r8
  unsigned __int64 v207; // rdx
  unsigned int v208; // eax
  signed int v209; // eax
  bool v210; // sf
  HANDLE ProcessHeap; // rax
  __int64 v212; // [rsp+30h] [rbp-D0h]
  int v213; // [rsp+38h] [rbp-C8h]
  unsigned __int16 v214; // [rsp+3Ch] [rbp-C4h]
  __int128 v215; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v216; // [rsp+60h] [rbp-A0h]
  _BYTE v217[28]; // [rsp+70h] [rbp-90h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  int v219; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v220; // [rsp+A8h] [rbp-58h]
  __int64 v221; // [rsp+B0h] [rbp-50h]
  __int64 v222; // [rsp+B8h] [rbp-48h]
  __int64 v223; // [rsp+C0h] [rbp-40h]
  int v224; // [rsp+C8h] [rbp-38h]
  __int64 v225; // [rsp+D0h] [rbp-30h]
  __int64 v226; // [rsp+D8h] [rbp-28h]
  int v227; // [rsp+E0h] [rbp-20h]
  __int64 v228; // [rsp+E8h] [rbp-18h]
  __int64 v229; // [rsp+F0h] [rbp-10h]
  char *v230; // [rsp+F8h] [rbp-8h]
  unsigned int v231; // [rsp+100h] [rbp+0h]
  char *v232; // [rsp+108h] [rbp+8h]
  __int64 v233; // [rsp+110h] [rbp+10h]
  char v234; // [rsp+118h] [rbp+18h]
  char *v235; // [rsp+120h] [rbp+20h]
  _DWORD *v236; // [rsp+128h] [rbp+28h]
  __int64 v237; // [rsp+130h] [rbp+30h]
  _DWORD v238[2]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v239; // [rsp+148h] [rbp+48h]
  unsigned __int64 v240; // [rsp+150h] [rbp+50h]
  unsigned __int64 v241; // [rsp+158h] [rbp+58h]
  char *v242; // [rsp+160h] [rbp+60h]
  int v243; // [rsp+168h] [rbp+68h]
  __int128 v244; // [rsp+16Ch] [rbp+6Ch]

  v3 = *Context;
  lpMem = Context;
  v214 = 0;
  v4 = v3 - 16;
  v213 = 0;
  v5 = 0;
  memset_0(v238, 0, 0x40u);
  v6 = 0;
  memset_0(&v219, 0, 0x98u);
  v7 = 87;
  v8 = v4 < 0x18 ? 0x57 : 0;
  *(_OWORD *)v217 = 0;
  if ( v4 < 0x18 )
    v8 = (v4 < 0x18 ? 0x57 : 0) | 0x80070000;
  v215 = 0;
  v216 = 0;
  *(_OWORD *)&v217[12] = 0;
  if ( v8 < 0 )
    goto LABEL_745;
  v9 = (char *)lpMem + 16;
  v10 = (unsigned int *)((char *)lpMem + 24);
  v11 = *((_DWORD *)lpMem + 6);
  v12 = v4 < v11 ? 0x57 : 0;
  if ( v4 < v11 )
    v12 = (v4 < v11 ? 0x57 : 0) | 0x80070000;
  if ( v12 < 0
    || v11 < 0x18
    || *(_DWORD *)v9 != 1886219331
    || (*((_BYTE *)lpMem + 28) & 2) != 0 && *((_DWORD *)lpMem + 5) != RtlComputeCrc32(0, (PUCHAR)lpMem + 24, v11 - 8) )
  {
    goto LABEL_745;
  }
  if ( v11 < *v10 )
    goto LABEL_745;
  v13 = *((unsigned __int16 *)lpMem + 15);
  if ( !(_WORD)v13 )
    goto LABEL_745;
  v14 = 8 * v13 + 16;
  if ( v14 >= *v10 )
    goto LABEL_745;
  for ( i = 0; ; ++i )
  {
    v16 = *((unsigned __int16 *)lpMem + 15);
    if ( (unsigned __int16)v13 >= 0x12u )
      v16 = 18;
    if ( i >= v16 )
      break;
    if ( *(_WORD *)&v9[8 * i + 16] >= 0x12u )
      goto LABEL_745;
    v17 = *(unsigned int *)&v9[8 * i + 20];
    if ( (_DWORD)v17 )
    {
      if ( v17 < v14 )
        goto LABEL_745;
    }
    if ( (unsigned int)v17 > *v10 )
      goto LABEL_745;
    v18 = *(unsigned __int16 *)&v9[8 * i + 18];
    if ( v18 > *v10 )
      goto LABEL_745;
    v19 = v17 + v18;
    if ( v19 < (unsigned int)v17 || v19 > *v10 )
      goto LABEL_745;
  }
  if ( *v10 < 0x18 )
    goto LABEL_745;
  if ( *((_WORD *)lpMem + 16) >= 0x12u )
    goto LABEL_745;
  v20 = *((unsigned int *)lpMem + 9);
  if ( (_DWORD)v20 )
  {
    if ( v20 < v14 || (unsigned int)v20 > *v10 )
      goto LABEL_745;
  }
  v21 = *((unsigned __int16 *)lpMem + 17);
  if ( v21 > *v10
    || v21 + (unsigned int)v20 < (unsigned int)v20
    || v21 + (unsigned int)v20 > *v10
    || *((_WORD *)lpMem + 16) != 7
    || (_WORD)v21 != 1
    || (unsigned __int8)v9[v20] > 1u )
  {
    goto LABEL_745;
  }
  v22 = -1073741275;
  if ( (unsigned __int16)v13 > 1u
    && *v10 >= 0x20
    && *((_WORD *)lpMem + 20) < 0x12u
    && ((v23 = *((unsigned int *)lpMem + 11), !(_DWORD)v23) || v23 >= v14 && (unsigned int)v23 <= *v10)
    && (v24 = *((unsigned __int16 *)lpMem + 21), v24 <= *v10)
    && (unsigned int)v23 + v24 >= (unsigned int)v23
    && (unsigned int)v23 + v24 <= *v10
    && *((_WORD *)lpMem + 20) == 8
    && (_WORD)v24 == 2 )
  {
    v25 = *(_WORD *)&v9[v23];
    v26 = 0;
    v214 = v25;
  }
  else
  {
    v25 = 0;
    v26 = -1073741275;
  }
  v27 = RtlNtStatusToDosError(v26);
  v28 = v27 < 0;
  if ( v27 > 0 )
    v28 = 1;
  if ( v28 )
    goto LABEL_745;
  v29 = 4;
  if ( (unsigned __int16)(v25 + 0x7FFF) <= 4u
    || (unsigned __int16)(v25 + 32511) <= 2u
    || (unsigned __int16)(v25 + 0x3FFF) <= 4u )
  {
    v7 = 0;
  }
  if ( v7 )
    v7 |= 0x80070000;
  if ( v7 < 0 )
    goto LABEL_745;
  v30 = 6;
  v219 = 152;
  v31 = 17;
  if ( v25 <= 0xC000u || (v212 = 0, v25 >= 0xC006u) )
  {
    if ( *((_WORD *)lpMem + 15) > 2u
      && *v10 >= 0x28
      && *((_WORD *)lpMem + 24) < 0x12u
      && ((v32 = *((unsigned int *)lpMem + 13), !(_DWORD)v32)
       || v32 >= 8 * (unsigned __int64)*((unsigned __int16 *)lpMem + 15) + 16 && (unsigned int)v32 <= *v10)
      && (v33 = *((unsigned __int16 *)lpMem + 25), v33 <= *v10)
      && v33 + (unsigned int)v32 >= (unsigned int)v32
      && v33 + (unsigned int)v32 <= *v10
      && *((_WORD *)lpMem + 24) == 6
      && (_WORD)v33 == 8 )
    {
      v5 = *(_QWORD *)&v9[v32];
      v34 = 0;
    }
    else
    {
      v34 = -1073741275;
    }
    v35 = RtlNtStatusToDosError(v34);
    v36 = v35 < 0;
    if ( v35 > 0 )
      v36 = 1;
    if ( v36 )
      goto LABEL_745;
    v37 = CfpReferenceSyncRoot(v5);
    v212 = v37;
    if ( !v37 )
      goto LABEL_745;
    v220 = v5;
    v221 = *(_QWORD *)(v37 + 280);
    v222 = v37 + 40;
    v223 = *(_QWORD *)(v37 + 32);
    v224 = *(_DWORD *)(v37 + 24);
    v225 = **(_QWORD **)(v37 + 16);
    v226 = *(_QWORD *)(v37 + 16) + 1056LL;
    v227 = *(_DWORD *)(*(_QWORD *)(v37 + 16) + 1052LL);
    if ( *((_WORD *)lpMem + 15) <= 6u
      || *v10 < 0x48
      || *((_WORD *)lpMem + 40) >= 0x12u
      || (v38 = *((unsigned int *)lpMem + 21), (_DWORD)v38)
      && (v38 < 8 * (unsigned __int64)*((unsigned __int16 *)lpMem + 15) + 16 || (unsigned int)v38 > *v10)
      || (v39 = *((unsigned __int16 *)lpMem + 41), v39 > *v10)
      || v39 + (unsigned int)v38 < (unsigned int)v38
      || v39 + (unsigned int)v38 > *v10
      || *((_WORD *)lpMem + 40) != 17 )
    {
      v40 = -1073741275;
    }
    else
    {
      if ( (_DWORD)v38 && (_WORD)v39 )
        v230 = &v9[v38];
      else
        v230 = 0;
      v40 = 0;
      v231 = v39;
    }
    v41 = RtlNtStatusToDosError(v40);
    v42 = v41 < 0;
    if ( v41 > 0 )
      v42 = 1;
    if ( v42 )
      goto LABEL_743;
    if ( *((_WORD *)lpMem + 15) > 4u
      && *v10 >= 0x38
      && *((_WORD *)lpMem + 32) < 0x12u
      && ((v43 = *((unsigned int *)lpMem + 17), !(_DWORD)v43)
       || v43 >= 8 * (unsigned __int64)*((unsigned __int16 *)lpMem + 15) + 16 && (unsigned int)v43 <= *v10)
      && (v44 = *((unsigned __int16 *)lpMem + 33), v44 <= *v10)
      && v44 + (unsigned int)v43 >= (unsigned int)v43
      && v44 + (unsigned int)v43 <= *v10
      && *((_WORD *)lpMem + 32) == 6
      && (_WORD)v44 == 8 )
    {
      v228 = *(_QWORD *)&v9[v43];
      v45 = 0;
    }
    else
    {
      v45 = -1073741275;
    }
    v46 = RtlNtStatusToDosError(v45);
    v47 = v46 < 0;
    if ( v46 > 0 )
      v47 = 1;
    if ( v47 )
      goto LABEL_743;
    if ( *((_WORD *)lpMem + 15) <= 7u
      || *v10 < 0x50
      || *((_WORD *)lpMem + 44) >= 0x12u
      || (v48 = *((unsigned int *)lpMem + 23), (_DWORD)v48)
      && (v48 < 8 * (unsigned __int64)*((unsigned __int16 *)lpMem + 15) + 16 || (unsigned int)v48 > *v10)
      || (v49 = *((unsigned __int16 *)lpMem + 45), v49 > *v10)
      || v49 + (unsigned int)v48 < (unsigned int)v48
      || v49 + (unsigned int)v48 > *v10
      || *((_WORD *)lpMem + 44) != 17 )
    {
      v50 = -1073741275;
    }
    else
    {
      if ( (_DWORD)v48 && (_WORD)v49 )
        v232 = &v9[v48];
      else
        v232 = 0;
      v50 = 0;
    }
    v51 = RtlNtStatusToDosError(v50);
    v52 = v51 < 0;
    if ( v51 > 0 )
      v52 = 1;
    if ( v52 )
      goto LABEL_743;
    if ( *((_WORD *)lpMem + 15) > 5u
      && *v10 >= 0x40
      && *((_WORD *)lpMem + 36) < 0x12u
      && ((v53 = *((unsigned int *)lpMem + 19), !(_DWORD)v53)
       || v53 >= 8 * (unsigned __int64)*((unsigned __int16 *)lpMem + 15) + 16 && (unsigned int)v53 <= *v10)
      && (v54 = *((unsigned __int16 *)lpMem + 37), v54 <= *v10)
      && v54 + (unsigned int)v53 >= (unsigned int)v53
      && v54 + (unsigned int)v53 <= *v10
      && *((_WORD *)lpMem + 36) == 6
      && (_WORD)v54 == 8 )
    {
      v233 = *(_QWORD *)&v9[v53];
      v55 = 0;
    }
    else
    {
      v55 = -1073741275;
    }
    v56 = RtlNtStatusToDosError(v55);
    v57 = v56 < 0;
    if ( v56 > 0 )
      v57 = 1;
    if ( v57 )
    {
LABEL_743:
      v107 = v212;
LABEL_744:
      CfpReleaseSyncRoot(v107);
      goto LABEL_745;
    }
    v31 = 17;
  }
  v58 = *((unsigned __int16 *)lpMem + 15);
  if ( (unsigned __int16)v58 <= 0xAu )
    goto LABEL_285;
  if ( *v10 >= 0x68 && *((_WORD *)lpMem + 56) < 0x12u )
  {
    v29 = *((unsigned int *)lpMem + 29);
    if ( !(_DWORD)v29 || v29 >= 8 * v58 + 16 && (unsigned int)v29 <= *v10 )
    {
      v59 = *((unsigned __int16 *)lpMem + 57);
      if ( v59 <= *v10
        && v59 + (unsigned int)v29 >= (unsigned int)v29
        && v59 + (unsigned int)v29 <= *v10
        && *((_WORD *)lpMem + 56) == 17 )
      {
        if ( !(_DWORD)v29 || (v60 = &v9[v29], !(_WORD)v59) )
          v60 = 0;
        memset_0(v238, 0, 0x40u);
        if ( v59 < 0x18 )
          goto LABEL_269;
        if ( *((_WORD *)v60 + 7) )
        {
          v30 = *((unsigned int *)v60 + 2);
          if ( (unsigned int)v30 >= 0x18 && *((_WORD *)v60 + 8) < 0x12u )
          {
            v61 = *((unsigned int *)v60 + 5);
            if ( !(_DWORD)v61
              || v61 >= 8 * (unsigned __int64)*((unsigned __int16 *)v60 + 7) + 16
              && (unsigned int)v61 <= (unsigned int)v30 )
            {
              v62 = *((unsigned __int16 *)v60 + 9);
              if ( v62 <= (unsigned int)v30
                && v62 + (unsigned int)v61 >= (unsigned int)v61
                && v62 + (unsigned int)v61 <= (unsigned int)v30
                && *((_WORD *)v60 + 8) == 10
                && (_WORD)v62 == 4 )
              {
                v238[1] = *(_DWORD *)&v60[v61];
              }
            }
          }
        }
        if ( *((_WORD *)v60 + 7) > 4u )
        {
          v30 = *((unsigned int *)v60 + 2);
          if ( (unsigned int)v30 >= 0x38 && *((_WORD *)v60 + 24) < 0x12u )
          {
            v63 = *((unsigned int *)v60 + 13);
            if ( !(_DWORD)v63
              || v63 >= 8 * (unsigned __int64)*((unsigned __int16 *)v60 + 7) + 16
              && (unsigned int)v63 <= (unsigned int)v30 )
            {
              v64 = *((unsigned __int16 *)v60 + 25);
              if ( v64 <= (unsigned int)v30
                && v64 + (unsigned int)v63 >= (unsigned int)v63
                && v64 + (unsigned int)v63 <= (unsigned int)v30
                && *((_WORD *)v60 + 24) == 10
                && (_WORD)v64 == 4 )
              {
                v243 = *(_DWORD *)&v60[v63];
              }
            }
          }
        }
        v31 = (__int64)(v60 + 14);
        v65 = (unsigned int *)(v60 + 8);
        if ( *((_WORD *)v60 + 7) > 1u && *v65 >= 0x20 && *((_WORD *)v60 + 12) < 0x12u )
        {
          v66 = *((unsigned int *)v60 + 7);
          if ( !(_DWORD)v66 || v66 >= 8 * (unsigned __int64)*(unsigned __int16 *)v31 + 16 && (unsigned int)v66 <= *v65 )
          {
            v30 = *((unsigned __int16 *)v60 + 13);
            if ( (unsigned int)v30 <= *v65
              && (int)v30 + (int)v66 >= (unsigned int)v66
              && (int)v30 + (int)v66 <= *v65
              && *((_WORD *)v60 + 12) == 17 )
            {
              v67 = (_DWORD)v66 && (_WORD)v30 ? (unsigned __int64)&v60[v66] : 0LL;
              if ( v67 && *((_WORD *)v60 + 13) )
                v239 = v67;
            }
          }
        }
        if ( *(_WORD *)v31 > 5u )
        {
          v30 = *((unsigned int *)v60 + 2);
          if ( (unsigned int)v30 >= 0x40 && *((_WORD *)v60 + 28) < 0x12u )
          {
            v68 = *((unsigned int *)v60 + 15);
            if ( !(_DWORD)v68
              || v68 >= 8 * (unsigned __int64)*(unsigned __int16 *)v31 + 16 && (unsigned int)v68 <= (unsigned int)v30 )
            {
              v69 = *((unsigned __int16 *)v60 + 29);
              if ( v69 <= (unsigned int)v30
                && v69 + (unsigned int)v68 >= (unsigned int)v68
                && v69 + (unsigned int)v68 <= (unsigned int)v30
                && *((_WORD *)v60 + 28) == 17 )
              {
                if ( !(_DWORD)v68 || (v70 = &v60[v68], !(_WORD)v69) )
                  v70 = 0;
                if ( v70 && *((_WORD *)v60 + 29) )
                  v242 = v70;
              }
            }
          }
        }
        if ( *(_WORD *)v31 > 2u && *v65 >= 0x28 && *((_WORD *)v60 + 16) < 0x12u )
        {
          v71 = *((unsigned int *)v60 + 9);
          if ( !(_DWORD)v71 || v71 >= 8 * (unsigned __int64)*(unsigned __int16 *)v31 + 16 && (unsigned int)v71 <= *v65 )
          {
            v30 = *((unsigned __int16 *)v60 + 17);
            if ( (unsigned int)v30 <= *v65
              && (int)v30 + (int)v71 >= (unsigned int)v71
              && (int)v30 + (int)v71 <= *v65
              && *((_WORD *)v60 + 16) == 17 )
            {
              v72 = (_DWORD)v71 && (_WORD)v30 ? (unsigned __int64)&v60[v71] : 0LL;
              if ( v72 && *((_WORD *)v60 + 17) )
                v240 = v72;
            }
          }
        }
        v29 = 18;
        if ( *(_WORD *)v31 > 3u && *v65 >= 0x30 && *((_WORD *)v60 + 20) < 0x12u )
        {
          v73 = *((unsigned int *)v60 + 11);
          if ( !(_DWORD)v73 || v73 >= 8 * (unsigned __int64)*(unsigned __int16 *)v31 + 16 && (unsigned int)v73 <= *v65 )
          {
            v30 = *((unsigned __int16 *)v60 + 21);
            if ( (unsigned int)v30 <= *v65
              && (int)v30 + (int)v73 >= (unsigned int)v73
              && (int)v30 + (int)v73 <= *v65
              && *((_WORD *)v60 + 20) == 17 )
            {
              v74 = (_DWORD)v73 && (_WORD)v30 ? (unsigned __int64)&v60[v73] : 0LL;
              if ( v74 && *((_WORD *)v60 + 21) )
                v241 = v74;
            }
          }
          v29 = 18;
        }
        if ( *(_WORD *)v31 > 6u
          && *v65 >= 0x48
          && *((_WORD *)v60 + 32) < 0x12u
          && ((v29 = *((unsigned int *)v60 + 17), !(_DWORD)v29)
           || v29 >= 8 * (unsigned __int64)*(unsigned __int16 *)v31 + 16 && (unsigned int)v29 <= *v65)
          && (v75 = *((unsigned __int16 *)v60 + 33), v75 <= *v65)
          && v75 + (unsigned int)v29 >= (unsigned int)v29
          && v75 + (unsigned int)v29 <= *v65
          && (v30 = 16, *((_WORD *)v60 + 32) == 16)
          && (_WORD)v75 == 16 )
        {
          v76 = *(_OWORD *)&v60[v29];
          v238[0] = 64;
          v244 = v76;
        }
        else
        {
LABEL_269:
          v238[0] = 48;
        }
        v236 = v238;
      }
    }
  }
  if ( (unsigned __int16)v58 <= 0xBu
    || *v10 < 0x70
    || *((_WORD *)lpMem + 60) >= 0x12u
    || (v29 = *((unsigned int *)lpMem + 31), (_DWORD)v29) && (v29 < 8 * v58 + 16 || (unsigned int)v29 > *v10)
    || (v77 = *((unsigned __int16 *)lpMem + 61), v77 > *v10)
    || v77 + (unsigned int)v29 < (unsigned int)v29
    || v77 + (unsigned int)v29 > *v10
    || *((_WORD *)lpMem + 60) != 17 )
  {
LABEL_285:
    v78 = v235;
  }
  else
  {
    if ( (_DWORD)v29 && (_WORD)v77 )
      v78 = &v9[v29];
    else
      v78 = 0;
    v235 = v78;
  }
  if ( v78 )
    RtlExtendCorrelationVector(v78, v29, v30, v31);
  if ( *((_WORD *)lpMem + 15) > 8u
    && *v10 >= 0x58
    && *((_WORD *)lpMem + 48) < 0x12u
    && ((v79 = *((unsigned int *)lpMem + 25), !(_DWORD)v79)
     || v79 >= 8 * (unsigned __int64)*((unsigned __int16 *)lpMem + 15) + 16 && (unsigned int)v79 <= *v10)
    && (v80 = *((unsigned __int16 *)lpMem + 49), v80 <= *v10)
    && v80 + (unsigned int)v79 >= (unsigned int)v79
    && v80 + (unsigned int)v79 <= *v10
    && *((_WORD *)lpMem + 48) == 6
    && (_WORD)v80 == 8 )
  {
    v229 = *(_QWORD *)&v9[v79];
    v81 = 0;
  }
  else
  {
    v81 = -1073741275;
  }
  v82 = RtlNtStatusToDosError(v81);
  v83 = v82 < 0;
  if ( v82 > 0 )
    v83 = 1;
  if ( v83 )
    goto LABEL_740;
  if ( *((_WORD *)lpMem + 15) > 3u
    && *v10 >= 0x30
    && *((_WORD *)lpMem + 28) < 0x12u
    && ((v84 = *((unsigned int *)lpMem + 15), !(_DWORD)v84)
     || v84 >= 8 * (unsigned __int64)*((unsigned __int16 *)lpMem + 15) + 16 && (unsigned int)v84 <= *v10)
    && (v85 = *((unsigned __int16 *)lpMem + 29), v85 <= *v10)
    && v85 + (unsigned int)v84 >= (unsigned int)v84
    && v85 + (unsigned int)v84 <= *v10
    && *((_WORD *)lpMem + 28) == 7
    && (_WORD)v85 == 1 )
  {
    v234 = v9[v84];
    v86 = 0;
  }
  else
  {
    v86 = -1073741275;
  }
  v87 = RtlNtStatusToDosError(v86);
  v88 = v87 < 0;
  if ( v87 > 0 )
    v88 = 1;
  if ( v88 )
    goto LABEL_740;
  if ( *((_WORD *)lpMem + 15) > 9u
    && *v10 >= 0x60
    && *((_WORD *)lpMem + 52) < 0x12u
    && ((v89 = *((unsigned int *)lpMem + 27), !(_DWORD)v89)
     || v89 >= 8 * (unsigned __int64)*((unsigned __int16 *)lpMem + 15) + 16 && (unsigned int)v89 <= *v10)
    && (v90 = *((unsigned __int16 *)lpMem + 53), v90 <= *v10)
    && v90 + (unsigned int)v89 >= (unsigned int)v89
    && v90 + (unsigned int)v89 <= *v10
    && *((_WORD *)lpMem + 52) == 10
    && (_WORD)v90 == 4 )
  {
    v91 = *(_DWORD *)&v9[v89];
    v92 = 0;
  }
  else
  {
    LOBYTE(v91) = 0;
    v92 = -1073741275;
  }
  v93 = RtlNtStatusToDosError(v92);
  v94 = v93 < 0;
  if ( v93 > 0 )
    v94 = 1;
  if ( v94 )
    goto LABEL_740;
  v95 = 0;
  memset_0(&v215, 0, 0x40u);
  switch ( v214 )
  {
    case 0x8001u:
      LODWORD(v215) = 64;
      if ( *((_WORD *)v9 + 7) > 0x11u
        && *v10 >= 0xA0
        && (v178 = *((_WORD *)v9 + 76), v178 < 0x12u)
        && ((v179 = *((unsigned int *)v9 + 39), !(_DWORD)v179)
         || v179 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v179 <= *v10)
        && (v180 = *((unsigned __int16 *)v9 + 77), v180 <= *v10)
        && v180 + (unsigned int)v179 >= (unsigned int)v179
        && v180 + (unsigned int)v179 <= *v10
        && v178 == 10
        && (_WORD)v180 == 4 )
      {
        *(_DWORD *)&v217[24] = *(_DWORD *)&v9[v179];
        v181 = 0;
      }
      else
      {
        v181 = -1073741275;
      }
      v182 = RtlNtStatusToDosError(v181);
      v183 = v182 < 0;
      if ( v182 > 0 )
        v183 = 1;
      if ( v183 )
        goto LABEL_740;
      if ( *((_WORD *)v9 + 7) > 0x10u
        && *v10 >= 0x98
        && (v184 = *((_WORD *)v9 + 72), v184 < 0x12u)
        && ((v185 = *((unsigned int *)v9 + 37), !(_DWORD)v185)
         || v185 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v185 <= *v10)
        && (v186 = *((unsigned __int16 *)v9 + 73), v186 <= *v10)
        && v186 + (unsigned int)v185 >= (unsigned int)v185
        && v186 + (unsigned int)v185 <= *v10
        && v184 == 6
        && (_WORD)v186 == 8 )
      {
        *(_QWORD *)&v217[16] = *(_QWORD *)&v9[v185];
        v187 = 0;
      }
      else
      {
        v187 = -1073741275;
      }
      v188 = RtlNtStatusToDosError(v187);
      v189 = v188 < 0;
      if ( v188 > 0 )
        v189 = 1;
      if ( v189 )
        goto LABEL_740;
      if ( *((_WORD *)v9 + 7) > 0xCu
        && *v10 >= 0x78
        && *((_WORD *)v9 + 56) < 0x12u
        && ((v190 = *((unsigned int *)v9 + 29), !(_DWORD)v190)
         || v190 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v190 <= *v10)
        && (v191 = *((unsigned __int16 *)v9 + 57), v191 <= *v10)
        && v191 + (unsigned int)v190 >= (unsigned int)v190
        && v191 + (unsigned int)v190 <= *v10
        && *((_WORD *)v9 + 56) == 6
        && (_WORD)v191 == 8 )
      {
        *(_QWORD *)&v216 = *(_QWORD *)&v9[v190];
        v192 = 0;
      }
      else
      {
        v192 = -1073741275;
      }
      v193 = RtlNtStatusToDosError(v192);
      v194 = v193 < 0;
      if ( v193 > 0 )
        v194 = 1;
      if ( v194 )
        goto LABEL_740;
      if ( *((_WORD *)v9 + 7) > 0xDu
        && *v10 >= 0x80
        && *((_WORD *)v9 + 60) < 0x12u
        && ((v195 = *((unsigned int *)v9 + 31), !(_DWORD)v195)
         || v195 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v195 <= *v10)
        && (v196 = *((unsigned __int16 *)v9 + 61), v196 <= *v10)
        && v196 + (unsigned int)v195 >= (unsigned int)v195
        && v196 + (unsigned int)v195 <= *v10
        && *((_WORD *)v9 + 60) == 6
        && (_WORD)v196 == 8 )
      {
        *((_QWORD *)&v216 + 1) = *(_QWORD *)&v9[v195];
        v197 = 0;
      }
      else
      {
        v197 = -1073741275;
      }
      v198 = RtlNtStatusToDosError(v197);
      v199 = v198 < 0;
      if ( v198 > 0 )
        v199 = 1;
      if ( v199 )
        goto LABEL_740;
      if ( *((_WORD *)v9 + 7) > 0xEu
        && *v10 >= 0x88
        && (v200 = *((_WORD *)v9 + 64), v200 < 0x12u)
        && ((v201 = *((unsigned int *)v9 + 33), !(_DWORD)v201)
         || v201 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v201 <= *v10)
        && (v202 = *((unsigned __int16 *)v9 + 65), v202 <= *v10)
        && v202 + (unsigned int)v201 >= (unsigned int)v201
        && v202 + (unsigned int)v201 <= *v10
        && v200 == 6
        && (_WORD)v202 == 8 )
      {
        *(_QWORD *)v217 = *(_QWORD *)&v9[v201];
        v203 = 0;
      }
      else
      {
        v203 = -1073741275;
      }
      v204 = RtlNtStatusToDosError(v203);
      v205 = v204 < 0;
      if ( v204 > 0 )
        v205 = 1;
      if ( v205 )
        goto LABEL_740;
      if ( *((_WORD *)v9 + 7) > 0xFu && *v10 >= 0x90 )
      {
        v206 = *((_WORD *)v9 + 68);
        if ( v206 < 0x12u )
        {
          v207 = *((unsigned int *)v9 + 35);
          if ( !(_DWORD)v207
            || v207 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v207 <= *v10 )
          {
            v208 = *((unsigned __int16 *)v9 + 69);
            if ( v208 <= *v10
              && v208 + (unsigned int)v207 >= (unsigned int)v207
              && v208 + (unsigned int)v207 <= *v10
              && v206 == 6
              && (_WORD)v208 == 8 )
            {
              v22 = 0;
              *(_QWORD *)&v217[8] = *(_QWORD *)&v9[v207];
            }
          }
        }
      }
      v209 = RtlNtStatusToDosError(v22);
      v210 = v209 < 0;
      if ( v209 > 0 )
        v210 = 1;
      if ( v210 )
        goto LABEL_740;
      v105 = 2;
      if ( (v91 & 2) != 0 )
      {
LABEL_737:
        DWORD2(v215) |= v105;
        goto LABEL_738;
      }
      goto LABEL_738;
    case 0x8002u:
      LODWORD(v215) = 32;
      if ( *((_WORD *)v9 + 7) > 0xCu
        && *v10 >= 0x78
        && *((_WORD *)v9 + 56) < 0x12u
        && ((v168 = *((unsigned int *)v9 + 29), !(_DWORD)v168)
         || v168 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v168 <= *v10)
        && (v169 = *((unsigned __int16 *)v9 + 57), v169 <= *v10)
        && v169 + (unsigned int)v168 >= (unsigned int)v168
        && v169 + (unsigned int)v168 <= *v10
        && *((_WORD *)v9 + 56) == 6
        && (_WORD)v169 == 8 )
      {
        *(_QWORD *)&v216 = *(_QWORD *)&v9[v168];
        v170 = 0;
      }
      else
      {
        v170 = -1073741275;
      }
      v171 = RtlNtStatusToDosError(v170);
      v172 = v171 < 0;
      if ( v171 > 0 )
        v172 = 1;
      if ( !v172 )
      {
        if ( *((_WORD *)v9 + 7) > 0xDu && *v10 >= 0x80 && *((_WORD *)v9 + 60) < 0x12u )
        {
          v173 = *((unsigned int *)v9 + 31);
          if ( !(_DWORD)v173
            || v173 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v173 <= *v10 )
          {
            v174 = *((unsigned __int16 *)v9 + 61);
            if ( v174 <= *v10
              && v174 + (unsigned int)v173 >= (unsigned int)v173
              && v174 + (unsigned int)v173 <= *v10
              && *((_WORD *)v9 + 60) == 6
              && (_WORD)v174 == 8 )
            {
              v22 = 0;
              *((_QWORD *)&v216 + 1) = *(_QWORD *)&v9[v173];
            }
          }
        }
        v175 = RtlNtStatusToDosError(v22);
        v176 = v175 < 0;
        if ( v175 > 0 )
          v176 = 1;
        if ( !v176 )
        {
          v177 = DWORD2(v215);
          if ( (v91 & 2) != 0 )
          {
            v177 = DWORD2(v215) | 2;
            DWORD2(v215) |= 2u;
          }
          v107 = v212;
          if ( !*(_QWORD *)(v212 + 184) && (v91 & 1) != 0 )
          {
            DWORD2(v215) = v177 | 1;
            CfpProcessCallback(v212, 0x8001u, 0, (__int64)&v219, (__int64)&v215);
            goto LABEL_741;
          }
          goto LABEL_739;
        }
      }
      goto LABEL_740;
    case 0x8003u:
      LODWORD(v215) = 24;
      if ( *((_WORD *)v9 + 7) > 0xCu && *v10 >= 0x78 && *((_WORD *)v9 + 56) < 0x12u )
      {
        v164 = *((unsigned int *)v9 + 29);
        if ( !(_DWORD)v164
          || v164 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v164 <= *v10 )
        {
          v165 = *((unsigned __int16 *)v9 + 57);
          if ( v165 <= *v10
            && v165 + (unsigned int)v164 >= (unsigned int)v164
            && v165 + (unsigned int)v164 <= *v10
            && *((_WORD *)v9 + 56) == 17 )
          {
            if ( (_DWORD)v164 && (_WORD)v165 )
              *(_QWORD *)&v216 = &v9[v164];
            else
              *(_QWORD *)&v216 = 0;
            v22 = 0;
          }
        }
      }
LABEL_601:
      v166 = RtlNtStatusToDosError(v22);
      v167 = v166 < 0;
      if ( v166 > 0 )
        v167 = 1;
      v107 = v212;
      if ( !v167 )
        goto LABEL_739;
      goto LABEL_741;
  }
  if ( v214 != 32772 )
  {
    if ( v214 != 32773 )
    {
      if ( v214 != 33025 )
      {
        if ( (unsigned int)v214 - 33026 <= 1 )
        {
          LODWORD(v215) = 12;
          if ( (v91 & 1) != 0 )
            DWORD2(v215) = 1;
          goto LABEL_738;
        }
        goto LABEL_740;
      }
      LODWORD(v215) = 32;
      if ( *((_WORD *)v9 + 7) > 0xCu
        && *v10 >= 0x78
        && *((_WORD *)v9 + 56) < 0x12u
        && ((v96 = *((unsigned int *)v9 + 29), !(_DWORD)v96)
         || v96 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v96 <= *v10)
        && (v97 = *((unsigned __int16 *)v9 + 57), v97 <= *v10)
        && v97 + (unsigned int)v96 >= (unsigned int)v96
        && v97 + (unsigned int)v96 <= *v10
        && *((_WORD *)v9 + 56) == 6
        && (_WORD)v97 == 8 )
      {
        *(_QWORD *)&v216 = *(_QWORD *)&v9[v96];
        v98 = 0;
      }
      else
      {
        v98 = -1073741275;
      }
      v99 = RtlNtStatusToDosError(v98);
      v100 = v99 < 0;
      if ( v99 > 0 )
        v100 = 1;
      if ( !v100 )
      {
        if ( *((_WORD *)v9 + 7) > 0xDu && *v10 >= 0x80 && *((_WORD *)v9 + 60) < 0x12u )
        {
          v101 = *((unsigned int *)v9 + 31);
          if ( !(_DWORD)v101
            || v101 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v101 <= *v10 )
          {
            v102 = *((unsigned __int16 *)v9 + 61);
            if ( v102 <= *v10
              && v102 + (unsigned int)v101 >= (unsigned int)v101
              && v102 + (unsigned int)v101 <= *v10
              && *((_WORD *)v9 + 60) == 6
              && (_WORD)v102 == 8 )
            {
              v22 = 0;
              *((_QWORD *)&v216 + 1) = *(_QWORD *)&v9[v101];
            }
          }
        }
        v103 = RtlNtStatusToDosError(v22);
        v104 = v103 < 0;
        if ( v103 > 0 )
          v104 = 1;
        if ( !v104 )
        {
          v105 = 1;
          if ( (v91 & 1) == 0 )
          {
            v106 = 2;
            goto LABEL_378;
          }
          goto LABEL_737;
        }
      }
LABEL_740:
      v107 = v212;
      goto LABEL_741;
    }
    if ( *((_WORD *)v9 + 7) > 0xCu
      && *v10 >= 0x78
      && *((_WORD *)v9 + 56) < 0x12u
      && ((v108 = *((unsigned int *)v9 + 29), !(_DWORD)v108)
       || v108 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v108 <= *v10)
      && (v109 = *((unsigned __int16 *)v9 + 57), v109 <= *v10)
      && v109 + (unsigned int)v108 >= (unsigned int)v108
      && v109 + (unsigned int)v108 <= *v10
      && *((_WORD *)v9 + 56) == 10
      && (_WORD)v109 == 4 )
    {
      v110 = 0;
      v213 = *(_DWORD *)&v9[v108];
    }
    else
    {
      v110 = -1073741275;
    }
    v111 = RtlNtStatusToDosError(v110);
    v112 = v111 < 0;
    if ( v111 > 0 )
      v112 = 1;
    if ( v112 )
      goto LABEL_740;
    if ( v213 == 1 )
    {
      LODWORD(v215) = 12;
      v106 = 1;
LABEL_378:
      v107 = v212;
      if ( ((unsigned __int8)v91 & (unsigned __int8)v106) != 0 )
        DWORD2(v215) |= v106;
      goto LABEL_739;
    }
    if ( v213 == 2 )
    {
      LODWORD(v215) = 12;
      v107 = v212;
      if ( (v91 & 4) != 0 )
        DWORD2(v215) |= 1u;
      goto LABEL_739;
    }
    if ( v213 != 3 )
    {
      if ( v213 != 4 )
      {
        if ( v213 != 5 )
          goto LABEL_740;
        LODWORD(v215) = 24;
        if ( *((_WORD *)v9 + 7) > 0xEu && *v10 >= 0x88 )
        {
          v113 = *((_WORD *)v9 + 64);
          if ( v113 < 0x12u )
          {
            v114 = *((unsigned int *)v9 + 33);
            if ( !(_DWORD)v114
              || v114 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v114 <= *v10 )
            {
              v115 = *((unsigned __int16 *)v9 + 65);
              if ( v115 <= *v10
                && v115 + (unsigned int)v114 >= (unsigned int)v114
                && v115 + (unsigned int)v114 <= *v10
                && v113 == 17 )
              {
                if ( (_DWORD)v114 && (_WORD)v115 )
                  v116 = &v9[v114];
                else
                  v116 = 0;
                if ( v115 >= 0x18 )
                {
                  if ( *((_WORD *)v116 + 7) )
                  {
                    v117 = *((_DWORD *)v116 + 2);
                    if ( v117 >= 0x18 && *((_WORD *)v116 + 8) < 0x12u )
                    {
                      v118 = *((unsigned int *)v116 + 5);
                      if ( !(_DWORD)v118
                        || v118 >= 8 * (unsigned __int64)*((unsigned __int16 *)v116 + 7) + 16
                        && (unsigned int)v118 <= v117 )
                      {
                        v119 = *((unsigned __int16 *)v116 + 9);
                        if ( v119 <= v117
                          && v119 + (unsigned int)v118 >= (unsigned int)v118
                          && v119 + (unsigned int)v118 <= v117
                          && *((_WORD *)v116 + 8) == 17 )
                        {
                          if ( (_DWORD)v118 && (_WORD)v119 )
                            v95 = &v116[v118];
                          v22 = 0;
                        }
                      }
                    }
                  }
                }
                v120 = RtlNtStatusToDosError(v22);
                v121 = v120 < 0;
                if ( v120 > 0 )
                  v121 = 1;
                if ( v121 )
                  goto LABEL_740;
              }
            }
          }
        }
        *(_QWORD *)&v216 = v95;
LABEL_738:
        v107 = v212;
        goto LABEL_739;
      }
LABEL_567:
      LODWORD(v215) = 12;
      goto LABEL_738;
    }
    LODWORD(v215) = 16;
    if ( *((_WORD *)v9 + 7) > 0xDu
      && *v10 >= 0x80
      && *((_WORD *)v9 + 60) < 0x12u
      && ((v122 = *((unsigned int *)v9 + 31), !(_DWORD)v122)
       || v122 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v122 <= *v10)
      && (v123 = *((unsigned __int16 *)v9 + 61), v123 <= *v10)
      && v123 + (unsigned int)v122 >= (unsigned int)v122
      && v123 + (unsigned int)v122 <= *v10
      && *((_WORD *)v9 + 60) == 6
      && (_WORD)v123 == 8 )
    {
      v6 = *(_QWORD *)&v9[v122];
      v124 = 0;
    }
    else
    {
      v124 = -1073741275;
    }
    v125 = RtlNtStatusToDosError(v124);
    v126 = v125 < 0;
    if ( v125 > 0 )
      v126 = 1;
    if ( v126 )
      goto LABEL_740;
    if ( v6 )
      DWORD2(v215) |= 2u;
    if ( *((_WORD *)v9 + 7) <= 0xEu )
      goto LABEL_738;
    if ( *v10 < 0x88 )
      goto LABEL_738;
    v127 = *((_WORD *)v9 + 64);
    if ( v127 >= 0x12u )
      goto LABEL_738;
    v128 = *((unsigned int *)v9 + 33);
    if ( (_DWORD)v128 )
    {
      if ( v128 < 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 || (unsigned int)v128 > *v10 )
        goto LABEL_738;
    }
    v129 = *((unsigned __int16 *)v9 + 65);
    if ( v129 > *v10 || v129 + (unsigned int)v128 < (unsigned int)v128 || v129 + (unsigned int)v128 > *v10 || v127 != 17 )
      goto LABEL_738;
    if ( (_DWORD)v128 && (_WORD)v129 )
      v130 = &v9[v128];
    else
      v130 = 0;
    if ( v129 < 0x18 )
      goto LABEL_601;
    if ( !*((_WORD *)v130 + 7) )
      goto LABEL_601;
    v131 = *((_DWORD *)v130 + 2);
    if ( v131 < 0x18 )
      goto LABEL_601;
    v132 = *((_WORD *)v130 + 8) < 0x12u;
LABEL_470:
    if ( v132 )
    {
      v133 = *((unsigned int *)v130 + 5);
      if ( !(_DWORD)v133
        || v133 >= 8 * (unsigned __int64)*((unsigned __int16 *)v130 + 7) + 16 && (unsigned int)v133 <= v131 )
      {
        v134 = *((unsigned __int16 *)v130 + 9);
        if ( v134 <= v131
          && v134 + (unsigned int)v133 >= (unsigned int)v133
          && v134 + (unsigned int)v133 <= v131
          && *((_WORD *)v130 + 8) == 10
          && (_WORD)v134 == 4 )
        {
          v22 = 0;
          HIDWORD(v215) = *(_DWORD *)&v130[v133];
        }
      }
    }
    goto LABEL_601;
  }
  if ( *((_WORD *)v9 + 7) > 0xCu
    && *v10 >= 0x78
    && *((_WORD *)v9 + 56) < 0x12u
    && ((v135 = *((unsigned int *)v9 + 29), !(_DWORD)v135)
     || v135 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v135 <= *v10)
    && (v136 = *((unsigned __int16 *)v9 + 57), v136 <= *v10)
    && v136 + (unsigned int)v135 >= (unsigned int)v135
    && v136 + (unsigned int)v135 <= *v10
    && *((_WORD *)v9 + 56) == 10
    && (_WORD)v136 == 4 )
  {
    v137 = *(_DWORD *)&v9[v135];
    v138 = 0;
    v213 = v137;
  }
  else
  {
    v137 = 0;
    v138 = -1073741275;
  }
  v139 = RtlNtStatusToDosError(v138);
  v140 = v139 < 0;
  if ( v139 > 0 )
    v140 = 1;
  if ( v140 )
    goto LABEL_740;
  if ( *((_WORD *)v9 + 7) > 0xDu
    && *v10 >= 0x80
    && *((_WORD *)v9 + 60) < 0x12u
    && ((v141 = *((unsigned int *)v9 + 31), !(_DWORD)v141)
     || v141 >= 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 && (unsigned int)v141 <= *v10)
    && (v142 = *((unsigned __int16 *)v9 + 61), v142 <= *v10)
    && v142 + (unsigned int)v141 >= (unsigned int)v141
    && v142 + (unsigned int)v141 <= *v10
    && *((_WORD *)v9 + 60) == 6
    && (_WORD)v142 == 8 )
  {
    v237 = *(_QWORD *)&v9[v141];
    v143 = 0;
  }
  else
  {
    v143 = -1073741275;
  }
  v144 = RtlNtStatusToDosError(v143);
  v145 = v144 < 0;
  if ( v144 > 0 )
    v145 = 1;
  if ( v145 )
    goto LABEL_740;
  if ( v137 == 3 )
  {
    LODWORD(v215) = 16;
    if ( *((_WORD *)v9 + 7) <= 0xEu )
      goto LABEL_738;
    if ( *v10 < 0x88 )
      goto LABEL_738;
    v161 = *((_WORD *)v9 + 64);
    if ( v161 >= 0x12u )
      goto LABEL_738;
    v162 = *((unsigned int *)v9 + 33);
    if ( (_DWORD)v162 )
    {
      if ( v162 < 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 || (unsigned int)v162 > *v10 )
        goto LABEL_738;
    }
    v163 = *((unsigned __int16 *)v9 + 65);
    if ( v163 > *v10 || v163 + (unsigned int)v162 < (unsigned int)v162 || v163 + (unsigned int)v162 > *v10 || v161 != 17 )
      goto LABEL_738;
    if ( (_DWORD)v162 && (_WORD)v163 )
      v130 = &v9[v162];
    else
      v130 = 0;
    if ( v163 < 0x18 )
      goto LABEL_601;
    if ( !*((_WORD *)v130 + 7) )
      goto LABEL_601;
    v131 = *((_DWORD *)v130 + 2);
    if ( v131 < 0x18 )
      goto LABEL_601;
    v132 = *((_WORD *)v130 + 8) < 0x12u;
    goto LABEL_470;
  }
  if ( v137 == 4 )
  {
    v160 = DWORD2(v215);
    if ( (v91 & 0x10) != 0 )
    {
      v160 = DWORD2(v215) | 1;
      DWORD2(v215) |= 1u;
    }
    if ( (v91 & 0x80u) != 0 )
      DWORD2(v215) = v160 | 2;
    goto LABEL_567;
  }
  if ( v137 != 5 )
    goto LABEL_740;
  LODWORD(v215) = 24;
  v146 = 0;
  v147 = DWORD2(v215);
  if ( (v91 & 0x10) != 0 )
  {
    v147 = DWORD2(v215) | 1;
    DWORD2(v215) |= 1u;
  }
  if ( (v91 & 0x20) != 0 )
  {
    v147 |= 2u;
    DWORD2(v215) = v147;
  }
  if ( (v91 & 0x40) != 0 )
    DWORD2(v215) = v147 | 4;
  if ( (v148 = 0, *((_WORD *)v9 + 7) <= 0xEu)
    || *v10 < 0x88
    || (v149 = *((_WORD *)v9 + 64), v149 >= 0x12u)
    || (v150 = *((unsigned int *)v9 + 33), (_DWORD)v150)
    && (v150 < 8 * (unsigned __int64)*((unsigned __int16 *)v9 + 7) + 16 || (unsigned int)v150 > *v10)
    || (v151 = *((unsigned __int16 *)v9 + 65), v151 > *v10)
    || v151 + (unsigned int)v150 < (unsigned int)v150
    || v151 + (unsigned int)v150 > *v10
    || v149 != 17 )
  {
    v152 = -1073741275;
  }
  else
  {
    if ( (_DWORD)v150 && (_WORD)v151 )
      v146 = &v9[v150];
    v148 = *((unsigned __int16 *)v9 + 65);
    v152 = 0;
  }
  if ( v152 < 0 )
    v148 = 0;
  v153 = RtlNtStatusToDosError(v152);
  v154 = v153 < 0;
  if ( v153 > 0 )
    v154 = 1;
  if ( v154 )
    goto LABEL_740;
  if ( v148 >= 0x18 )
  {
    if ( *((_WORD *)v146 + 7) )
    {
      v155 = *((_DWORD *)v146 + 2);
      if ( v155 >= 0x18 && *((_WORD *)v146 + 8) < 0x12u )
      {
        v156 = *((unsigned int *)v146 + 5);
        if ( !(_DWORD)v156
          || v156 >= 8 * (unsigned __int64)*((unsigned __int16 *)v146 + 7) + 16 && (unsigned int)v156 <= v155 )
        {
          v157 = *((unsigned __int16 *)v146 + 9);
          if ( v157 <= v155
            && v157 + (unsigned int)v156 >= (unsigned int)v156
            && v157 + (unsigned int)v156 <= v155
            && *((_WORD *)v146 + 8) == 17 )
          {
            if ( (_DWORD)v156 && (_WORD)v157 )
              v95 = &v146[v156];
            v22 = 0;
          }
        }
      }
    }
  }
  v158 = RtlNtStatusToDosError(v22);
  v159 = v158 < 0;
  if ( v158 > 0 )
    v159 = 1;
  v107 = v212;
  if ( !v159 )
  {
    *(_QWORD *)&v216 = v95;
LABEL_739:
    CfpProcessCallback(v107, v214, v213, (__int64)&v219, (__int64)&v215);
  }
LABEL_741:
  if ( v107 )
    goto LABEL_744;
LABEL_745:
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, lpMem);
}

```

## disassembly

```asm
0x18000c2a0  push    rbp
0x18000c2a2  push    rbx
0x18000c2a3  push    rsi
0x18000c2a4  push    rdi
0x18000c2a5  push    r12
0x18000c2a7  push    r13
0x18000c2a9  push    r14
0x18000c2ab  push    r15
0x18000c2ad  lea     rbp, [rsp-98h]
0x18000c2b5  sub     rsp, 198h
0x18000c2bc  mov     rax, cs:__security_cookie
0x18000c2c3  xor     rax, rsp
0x18000c2c6  mov     [rbp+0D0h+var_50], rax
0x18000c2cd  mov     r14d, [rdx]
0x18000c2d0  lea     rcx, [rbp+0D0h+var_90]; void *
0x18000c2d4  xor     edi, edi
0x18000c2d6  mov     [rbp+0D0h+lpMem], rdx
0x18000c2da  xor     edx, edx; Val
0x18000c2dc  mov     dword ptr [rsp+1D0h+var_194], edi
0x18000c2e0  add     r14d, 0FFFFFFF0h
0x18000c2e4  mov     [rsp+1D0h+var_198], edi
0x18000c2e8  mov     ebx, edi
0x18000c2ea  lea     r8d, [rdi+40h]; Size
0x18000c2ee  call    memset_0
0x18000c2f3  xor     edx, edx; Val
0x18000c2f5  mov     [rsp+1D0h+var_18C], edi
0x18000c2f9  mov     r8d, 98h; Size
0x18000c2ff  lea     rcx, [rbp+0D0h+var_130]; void *
0x18000c303  mov     r13d, edi
0x18000c306  call    memset_0
0x18000c30b  xor     eax, eax
0x18000c30d  lea     r15d, [rdi+57h]
0x18000c311  xorps   xmm0, xmm0
0x18000c314  cmp     r14d, 18h
0x18000c318  mov     edx, 80070000h
0x18000c31d  sbb     ecx, ecx
0x18000c31f  and     ecx, r15d
0x18000c322  mov     eax, ecx
0x18000c324  or      eax, edx
0x18000c326  cmp     r14d, 18h
0x18000c32a  movups  [rsp+1D0h+var_160], xmm0
0x18000c32f  cmovb   ecx, eax
0x18000c332  xor     r11d, r11d
0x18000c335  movups  [rsp+1D0h+var_180], xmm0
0x18000c33a  movups  [rsp+1D0h+var_170], xmm0
0x18000c33f  movups  [rsp+1D0h+var_160+0Ch], xmm0
0x18000c344  test    ecx, ecx
0x18000c346  js      loc_18000DF8D
0x18000c34c  mov     rdi, [rbp+0D0h+lpMem]
0x18000c350  add     rdi, 10h
0x18000c354  lea     r12, [rdi+8]
0x18000c358  mov     esi, [r12]
0x18000c35c  cmp     r14d, esi
0x18000c35f  sbb     ecx, ecx
0x18000c361  and     ecx, r15d
0x18000c364  mov     eax, ecx
0x18000c366  or      eax, edx
0x18000c368  cmp     r14d, esi
0x18000c36b  cmovb   ecx, eax
0x18000c36e  test    ecx, ecx
0x18000c370  js      loc_18000DF8D
0x18000c376  cmp     esi, 18h
0x18000c379  jb      loc_18000DF8D
0x18000c37f  cmp     dword ptr [rdi], 706D6C43h
0x18000c385  jnz     loc_18000DF8D
0x18000c38b  test    byte ptr [rdi+0Ch], 2
0x18000c38f  jz      short loc_18000C3B2
0x18000c391  lea     r8d, [rsi-8]; Length
0x18000c395  mov     rdx, r12; Buffer
0x18000c398  xor     ecx, ecx; InitialCrc
0x18000c39a  call    cs:__imp_RtlComputeCrc32
0x18000c3a1  nop     dword ptr [rax+rax+00h]
0x18000c3a6  cmp     [rdi+4], eax
0x18000c3a9  jnz     loc_18000DF8D
0x18000c3af  xor     r11d, r11d
0x18000c3b2  cmp     esi, [r12]
0x18000c3b6  jb      loc_18000DF8D
0x18000c3bc  movzx   edx, word ptr [rdi+0Eh]
0x18000c3c0  test    dx, dx
0x18000c3c3  jz      loc_18000DF8D
0x18000c3c9  mov     eax, [r12]
0x18000c3cd  lea     r10, ds:10h[rdx*8]
0x18000c3d5  cmp     r10, rax
0x18000c3d8  jnb     loc_18000DF8D
0x18000c3de  mov     r14d, 12h
0x18000c3e4  mov     r8d, r11d
0x18000c3e7  lea     r9d, [r14-11h]
0x18000c3eb  mov     eax, edx
0x18000c3ed  cmp     dx, r14w
0x18000c3f1  jb      short loc_18000C3F6
0x18000c3f3  mov     eax, r14d
0x18000c3f6  cmp     r8d, eax
0x18000c3f9  jnb     short loc_18000C455
0x18000c3fb  mov     r9d, r8d
0x18000c3fe  cmp     [rdi+r9*8+10h], r14w
0x18000c404  jnb     loc_18000DF8D
0x18000c40a  mov     ecx, [rdi+r9*8+14h]
0x18000c40f  test    ecx, ecx
0x18000c411  jz      short loc_18000C41C
0x18000c413  cmp     rcx, r10
0x18000c416  jb      loc_18000DF8D
0x18000c41c  cmp     ecx, [r12]
0x18000c420  ja      loc_18000DF8D
0x18000c426  movzx   eax, word ptr [rdi+r9*8+12h]
0x18000c42c  cmp     eax, [r12]
0x18000c430  ja      loc_18000DF8D
0x18000c436  add     eax, ecx
0x18000c438  cmp     eax, ecx
0x18000c43a  jb      loc_18000DF8D
0x18000c440  cmp     eax, [r12]
0x18000c444  ja      loc_18000DF8D
0x18000c44a  mov     r9d, 1
0x18000c450  add     r8d, r9d
0x18000c453  jmp     short loc_18000C3EB
0x18000c455  cmp     dword ptr [r12], 18h
0x18000c45a  jb      loc_18000DF8D
0x18000c460  cmp     r11w, dx
0x18000c464  jnb     loc_18000DF8D
0x18000c46a  cmp     [rdi+10h], r14w
0x18000c46f  jnb     loc_18000DF8D
0x18000c475  mov     ecx, [rdi+14h]
0x18000c478  test    ecx, ecx
0x18000c47a  jz      short loc_18000C48F
0x18000c47c  cmp     rcx, r10
0x18000c47f  jb      loc_18000DF8D
0x18000c485  cmp     ecx, [r12]
0x18000c489  ja      loc_18000DF8D
0x18000c48f  movzx   eax, word ptr [rdi+12h]
0x18000c493  cmp     eax, [r12]
0x18000c497  ja      loc_18000DF8D
0x18000c49d  lea     r8d, [rax+rcx]
0x18000c4a1  cmp     r8d, ecx
0x18000c4a4  jb      loc_18000DF8D
0x18000c4aa  cmp     r8d, [r12]
0x18000c4ae  ja      loc_18000DF8D
0x18000c4b4  mov     r8d, 7
0x18000c4ba  cmp     [rdi+10h], r8w
0x18000c4bf  jnz     loc_18000DF8D
0x18000c4c5  cmp     ax, r9w
0x18000c4c9  jnz     loc_18000DF8D
0x18000c4cf  cmp     [rcx+rdi], r9b
0x18000c4d3  ja      loc_18000DF8D
0x18000c4d9  mov     esi, 0C0000225h
0x18000c4de  mov     r8d, 8
0x18000c4e4  cmp     r9w, dx
0x18000c4e8  jnb     short loc_18000C541
0x18000c4ea  cmp     dword ptr [r12], 20h ; ' '
0x18000c4ef  jb      short loc_18000C541
0x18000c4f1  cmp     [rdi+18h], r14w
0x18000c4f6  jnb     short loc_18000C541
0x18000c4f8  mov     ecx, [rdi+1Ch]
0x18000c4fb  test    ecx, ecx
0x18000c4fd  jz      short loc_18000C50A
0x18000c4ff  cmp     rcx, r10
0x18000c502  jb      short loc_18000C541
0x18000c504  cmp     ecx, [r12]
0x18000c508  ja      short loc_18000C541
0x18000c50a  movzx   eax, word ptr [rdi+1Ah]
0x18000c50e  cmp     eax, [r12]
0x18000c512  ja      short loc_18000C541
0x18000c514  lea     edx, [rcx+rax]
0x18000c517  cmp     edx, ecx
0x18000c519  jb      short loc_18000C541
0x18000c51b  cmp     edx, [r12]
0x18000c51f  ja      short loc_18000C541
0x18000c521  cmp     [rdi+18h], r8w
0x18000c526  jnz     short loc_18000C541
0x18000c528  mov     edx, 2
0x18000c52d  cmp     ax, dx
0x18000c530  jnz     short loc_18000C541
0x18000c532  movzx   r14d, word ptr [rcx+rdi]
0x18000c537  mov     ecx, r11d
0x18000c53a  mov     dword ptr [rsp+1D0h+var_194], r14d
0x18000c53f  jmp     short loc_18000C548
0x18000c541  mov     r14d, dword ptr [rsp+1D0h+var_194]
0x18000c546  mov     ecx, esi; Status
0x18000c548  call    cs:__imp_RtlNtStatusToDosError
0x18000c54f  nop     dword ptr [rax+rax+00h]
0x18000c554  xor     r11d, r11d
0x18000c557  test    eax, eax
0x18000c559  jle     short loc_18000C565
0x18000c55b  movzx   eax, ax
0x18000c55e  or      eax, 80070000h
0x18000c563  test    eax, eax
0x18000c565  js      loc_18000DF8D
0x18000c56b  mov     edx, 4
0x18000c570  mov     eax, 7FFFh
0x18000c575  add     eax, r14d
0x18000c578  lea     r10d, [rdx-2]
0x18000c57c  cmp     ax, dx
0x18000c57f  jbe     short loc_18000C59C
0x18000c581  mov     eax, 7EFFh
0x18000c586  add     eax, r14d
0x18000c589  cmp     ax, r10w
0x18000c58d  jbe     short loc_18000C59C
0x18000c58f  mov     eax, 3FFFh
0x18000c594  add     eax, r14d
0x18000c597  cmp     ax, dx
0x18000c59a  ja      short loc_18000C59F
0x18000c59c  mov     r15d, r11d
0x18000c59f  mov     eax, r15d
0x18000c5a2  or      eax, 80070000h
0x18000c5a7  test    r15d, r15d
0x18000c5aa  cmovnz  r15d, eax
0x18000c5ae  test    r15d, r15d
0x18000c5b1  js      loc_18000DF8D
0x18000c5b7  mov     r8d, 6
0x18000c5bd  mov     [rbp+0D0h+var_130], 98h
0x18000c5c4  mov     eax, 0C000h
0x18000c5c9  lea     r9d, [r8+0Bh]
0x18000c5cd  lea     r15d, [r8-1]
0x18000c5d1  cmp     r14w, ax
0x18000c5d5  jbe     short loc_18000C5EB
0x18000c5d7  mov     eax, 0C006h
0x18000c5dc  mov     [rsp+1D0h+var_1A0], r11
0x18000c5e1  cmp     r14w, ax
0x18000c5e5  jb      loc_18000C939
0x18000c5eb  cmp     r10w, [rdi+0Eh]
0x18000c5f0  jnb     short loc_18000C653
0x18000c5f2  cmp     dword ptr [r12], 28h ; '('
0x18000c5f7  jb      short loc_18000C653
0x18000c5f9  mov     eax, 12h
0x18000c5fe  cmp     [rdi+20h], ax
0x18000c602  jnb     short loc_18000C653
0x18000c604  mov     edx, [rdi+24h]
0x18000c607  test    edx, edx
0x18000c609  jz      short loc_18000C622
0x18000c60b  movzx   eax, word ptr [rdi+0Eh]
0x18000c60f  lea     rcx, ds:10h[rax*8]
0x18000c617  cmp     rdx, rcx
0x18000c61a  jb      short loc_18000C653
0x18000c61c  cmp     edx, [r12]
0x18000c620  ja      short loc_18000C653
0x18000c622  movzx   eax, word ptr [rdi+22h]
0x18000c626  cmp     eax, [r12]
0x18000c62a  ja      short loc_18000C653
0x18000c62c  lea     ecx, [rax+rdx]
0x18000c62f  cmp     ecx, edx
0x18000c631  jb      short loc_18000C653
0x18000c633  cmp     ecx, [r12]
0x18000c637  ja      short loc_18000C653
0x18000c639  cmp     [rdi+20h], r8w
0x18000c63e  jnz     short loc_18000C653
0x18000c640  mov     ecx, 8
0x18000c645  cmp     ax, cx
0x18000c648  jnz     short loc_18000C653
0x18000c64a  mov     rbx, [rdx+rdi]
0x18000c64e  mov     ecx, r11d
0x18000c651  jmp     short loc_18000C655
0x18000c653  mov     ecx, esi; Status
0x18000c655  call    cs:__imp_RtlNtStatusToDosError
0x18000c65c  nop     dword ptr [rax+rax+00h]
0x18000c661  xor     r14d, r14d
0x18000c664  test    eax, eax
0x18000c666  jle     short loc_18000C672
0x18000c668  movzx   eax, ax
0x18000c66b  or      eax, 80070000h
0x18000c670  test    eax, eax
0x18000c672  js      loc_18000DF8D
0x18000c678  mov     rcx, rbx
0x18000c67b  call    CfpReferenceSyncRoot
0x18000c680  mov     [rsp+1D0h+var_1A0], rax
0x18000c685  mov     rdx, rax
0x18000c688  test    rax, rax
0x18000c68b  jz      loc_18000DF8D
0x18000c691  mov     [rbp+0D0h+var_128], rbx
0x18000c695  mov     rcx, [rax+118h]
0x18000c69c  mov     [rbp+0D0h+var_120], rcx
0x18000c6a0  lea     rcx, [rax+28h]
0x18000c6a4  mov     [rbp+0D0h+var_118], rcx
0x18000c6a8  mov     rcx, [rax+20h]
0x18000c6ac  mov     [rbp+0D0h+var_110], rcx
0x18000c6b0  mov     ecx, [rax+18h]
0x18000c6b3  mov     [rbp+0D0h+var_108], ecx
0x18000c6b6  mov     rcx, [rax+10h]
0x18000c6ba  mov     rax, [rcx]
0x18000c6bd  mov     [rbp+0D0h+var_100], rax
0x18000c6c1  mov     rax, [rdx+10h]
0x18000c6c5  add     rax, 420h
0x18000c6cb  mov     [rbp+0D0h+var_F8], rax
0x18000c6cf  mov     rax, [rdx+10h]
0x18000c6d3  mov     ecx, [rax+41Ch]
0x18000c6d9  mov     eax, 6
0x18000c6de  mov     [rbp+0D0h+var_F0], ecx
0x18000c6e1  lea     ebx, [rax+0Ch]
0x18000c6e4  cmp     ax, [rdi+0Eh]
0x18000c6e8  jnb     short loc_18000C75A
0x18000c6ea  cmp     dword ptr [r12], 48h ; 'H'
0x18000c6ef  jb      short loc_18000C75A
0x18000c6f1  cmp     [rdi+40h], bx
0x18000c6f5  jnb     short loc_18000C75A
0x18000c6f7  mov     edx, [rdi+44h]
0x18000c6fa  test    edx, edx
0x18000c6fc  jz      short loc_18000C715
0x18000c6fe  movzx   eax, word ptr [rdi+0Eh]
0x18000c702  lea     rcx, ds:10h[rax*8]
0x18000c70a  cmp     rdx, rcx
0x18000c70d  jb      short loc_18000C75A
0x18000c70f  cmp     edx, [r12]
0x18000c713  ja      short loc_18000C75A
  ... truncated ...
```
