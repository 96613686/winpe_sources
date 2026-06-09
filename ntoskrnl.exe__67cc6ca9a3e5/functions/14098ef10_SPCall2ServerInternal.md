# SPCall2ServerInternal

- ea: `0x14098ef10`
- end: `0x14099176d`
- name: `SPCall2ServerInternal`
- size: `10333`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `46`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14098edc0`

## callees

- `0x1402289b0`
- `0x1404468d0`
- `0x1404474b0`
- `0x1404a3d04`
- `0x1404e0378`
- `0x1406d9d70`
- `0x1406daf50`
- `0x1406e8590`
- `0x1406f4480`
- `0x1406f4750`
- `0x140729158`
- `0x140729d5c`
- `0x14072f1d0`
- `0x14072f9fc`
- `0x14072fc94`
- `0x140891a80`
- `0x1408a6ca0`
- `0x14098e800`
- `0x14098ece0`
- `0x14098edf8`
- `0x14098ef10`
- `0x140991774`
- `0x140a19f38`
- `0x140a1a34c`
- `0x140a1a884`
- `0x140a546ac`
- `0x140a5c930`
- `0x140a77b14`
- `0x140a8df50`
- `0x140aa48d8`
- `0x140aa6d78`
- `0x140ab5a3c`
- `0x140ab79ac`
- `0x140ac8000`
- `0x140aeab94`
- `0x140aec698`
- `0x140af5b38`
- `0x140af6e34`
- `0x140af73d4`
- `0x140afc940`
- `0x140afd588`
- `0x140afeca8`
- `0x140aff8a4`
- `0x140b00bf4`
- `0x140bae410`
- `0x140bae8e0`

## import_xrefs

- `ext-ms-win-ntos-ksecurity-l1-1-1!QueryUpdateFileEaAllowedExt` at `0x140990710`
- `ext-ms-win-ntos-ksecurity-l1-1-1!QueryUpdateFileEaAllowedExt` at `0x140990710`

## pseudocode

```c
__int64 __fastcall SPCall2ServerInternal(
        unsigned int *a1,
        unsigned int a2,
        unsigned int a3,
        _QWORD *a4,
        unsigned int *a5)
{
  __int64 v5; // rsi
  char *v6; // r15
  unsigned int *v7; // r8
  int v8; // esi
  _QWORD *v9; // r12
  NTSTATUS Acl; // edi
  unsigned int *v11; // r15
  unsigned int *v12; // rbx
  unsigned int *v13; // r14
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  size_t v21; // r14
  char *v22; // r12
  unsigned int v23; // r8d
  unsigned int *v24; // rdi
  unsigned int v25; // ecx
  const void *v26; // r13
  unsigned int v27; // r8d
  size_t v28; // rdi
  unsigned int *Pool2; // rax
  unsigned int *v30; // rbx
  void *v31; // rax
  void *v32; // rax
  unsigned int *v33; // r14
  void *v34; // rcx
  void *v35; // rcx
  void *v36; // rcx
  void *v37; // rcx
  void *v38; // rcx
  void *v39; // rcx
  void *v40; // rax
  size_t v41; // r8
  unsigned __int8 *v42; // rdi
  unsigned __int64 v43; // rcx
  __int64 *v44; // rbx
  unsigned int v45; // eax
  __int64 v46; // r13
  unsigned int v47; // edx
  __int64 v48; // rbx
  unsigned __int64 v49; // rsi
  size_t v50; // rax
  unsigned __int8 *v51; // r11
  unsigned int *v52; // rdx
  unsigned int v53; // r14d
  int v54; // edi
  int v55; // edx
  int v56; // edx
  unsigned int v57; // r8d
  int v58; // r9d
  int v59; // r11d
  int v60; // r10d
  int v61; // ecx
  int v62; // r8d
  int v63; // edx
  int v64; // ecx
  int v65; // r8d
  unsigned int v66; // ebx
  int v67; // esi
  unsigned int v68; // r15d
  unsigned int v69; // r14d
  __int64 v70; // rdi
  int v71; // r14d
  __int64 v72; // rbx
  _BYTE *v73; // r12
  unsigned __int64 v74; // rax
  __m128 v75; // xmm1
  __m128 v76; // xmm2
  __m128 v77; // xmm0
  __m128 v78; // xmm0
  __m128 v79; // xmm1
  __m128 v80; // xmm1
  __m128 v81; // xmm1
  __m128 v82; // xmm1
  unsigned __int8 v83; // cl
  int *v84; // rdx
  const void *v85; // rsi
  size_t v86; // r14
  unsigned __int64 v87; // r8
  unsigned int v88; // ebx
  char *v89; // rcx
  unsigned int v90; // eax
  int v91; // r13d
  void *v92; // r15
  int v93; // r9d
  int v94; // r10d
  int v95; // edx
  unsigned int v96; // r14d
  int v97; // r15d
  int v98; // eax
  char v99; // r8
  __int64 v100; // rsi
  int v101; // r12d
  __int64 v102; // rbx
  unsigned int v103; // edx
  unsigned int v104; // r15d
  unsigned int v105; // eax
  unsigned int v106; // edi
  unsigned int v107; // ecx
  _BYTE *v108; // r10
  size_t v109; // r9
  char v110; // r8
  char *v111; // rdx
  __int64 *v112; // rdx
  unsigned int v113; // eax
  __int64 v114; // r13
  int v115; // ecx
  unsigned __int64 v116; // rsi
  __int64 v117; // rdi
  unsigned __int64 v118; // rax
  __m128 v119; // xmm1
  __m128 v120; // xmm2
  __m128 v121; // xmm0
  __m128 v122; // xmm0
  __m128 v123; // xmm1
  __m128 v124; // xmm1
  __m128 v125; // xmm1
  __m128 v126; // xmm1
  _DWORD *v127; // rbx
  unsigned int v128; // r12d
  char *v129; // r14
  int v130; // r15d
  unsigned __int8 *v131; // rdx
  int v132; // r14d
  __int64 v133; // rbx
  int v134; // esi
  int v135; // ecx
  int v136; // r15d
  int v137; // ecx
  int v138; // r14d
  __int64 v139; // rdi
  unsigned int v140; // edx
  int v141; // r10d
  int v142; // r9d
  int v143; // r8d
  int v144; // edx
  int v145; // r9d
  int v146; // r8d
  unsigned int v147; // edx
  int v148; // r9d
  int v149; // r8d
  int v150; // r15d
  int v151; // edx
  int v152; // ecx
  int v153; // ecx
  _BYTE *v154; // r8
  void *v155; // rax
  void *v156; // rbx
  int v157; // esi
  unsigned int v158; // ecx
  unsigned int v159; // edx
  unsigned int v160; // ecx
  unsigned int v161; // esi
  _DWORD *v162; // rbx
  _DWORD *v163; // rdi
  _DWORD *v164; // rcx
  _DWORD *v165; // rdi
  _DWORD *v166; // rcx
  _DWORD *v167; // rdi
  int *v168; // r8
  unsigned int *v169; // rax
  int v170; // edx
  int v171; // r13d
  size_t v172; // rdi
  unsigned int *v173; // rcx
  const void *v174; // r15
  unsigned int *v175; // rax
  unsigned int i; // edx
  size_t v177; // rbx
  unsigned int *v178; // rcx
  const void *v179; // r14
  __int64 v180; // rax
  __int64 v181; // rcx
  __int64 v182; // r8
  unsigned int *v183; // rsi
  void *v184; // rax
  void *v185; // rax
  unsigned __int64 v186; // r14
  __int64 v187; // rdi
  int LicenseChallenge; // eax
  struct _LIST_ENTRY *v189; // r15
  ULONG v190; // ebx
  ULONG v191; // ebx
  ULONG v192; // ebx
  ACL *v193; // rax
  ACL *v194; // r14
  BOOLEAN v195; // bl
  const void *v196; // rbx
  int updated; // eax
  __int64 v198; // rdx
  __int64 v199; // r8
  const void *v200; // rbx
  __int64 v201; // r8
  struct _LIST_ENTRY *Blink; // r15
  ULONG v203; // ebx
  ULONG v204; // ebx
  ULONG v205; // ebx
  ACL *v206; // rax
  ACL *v207; // r14
  BOOLEAN v208; // bl
  const void *v209; // rbx
  unsigned int *v210; // rax
  unsigned int j; // edx
  __int64 v212; // r9
  unsigned int *v213; // rcx
  __int64 *v214; // r8
  unsigned int *v215; // rax
  unsigned int v216; // edx
  __int64 v217; // r14
  size_t v218; // rbx
  unsigned int *v219; // rcx
  unsigned int *v220; // rsi
  void *v221; // rax
  unsigned int *v222; // rax
  unsigned int k; // edx
  size_t v224; // rbx
  unsigned int *v225; // rcx
  const void *v226; // rdi
  void *v227; // rax
  int v228; // ebx
  _DWORD *v229; // rax
  unsigned __int64 v230; // rdx
  unsigned int v231; // ecx
  unsigned int m; // r8d
  unsigned int v233; // eax
  void *v234; // rcx
  void *v235; // rcx
  void *v236; // rcx
  ACCESS_MASK PreviouslyGrantedAccess[2]; // [rsp+28h] [rbp-E0h]
  PPRIVILEGE_SET *Privileges; // [rsp+30h] [rbp-D8h]
  unsigned int GenericMapping; // [rsp+38h] [rbp-D0h]
  _DWORD *v240; // [rsp+58h] [rbp-B0h]
  _QWORD *v241; // [rsp+68h] [rbp-A0h]
  PVOID v242[2]; // [rsp+70h] [rbp-98h] BYREF
  PVOID Src_8[2]; // [rsp+80h] [rbp-88h] BYREF
  unsigned int *v244; // [rsp+90h] [rbp-78h]
  int v245; // [rsp+98h] [rbp-70h]
  int v246; // [rsp+9Ch] [rbp-6Ch]
  unsigned int v247; // [rsp+A0h] [rbp-68h]
  int v248; // [rsp+A4h] [rbp-64h]
  char *v249; // [rsp+A8h] [rbp-60h]
  size_t Size; // [rsp+B0h] [rbp-58h]
  unsigned __int64 v251; // [rsp+B8h] [rbp-50h]
  int v252; // [rsp+C0h] [rbp-48h]
  int v253; // [rsp+C4h] [rbp-44h]
  PVOID v254; // [rsp+C8h] [rbp-40h]
  size_t v255; // [rsp+D0h] [rbp-38h]
  unsigned __int8 *v256; // [rsp+D8h] [rbp-30h]
  NTSTATUS v257; // [rsp+E0h] [rbp-28h] BYREF
  int v258; // [rsp+E4h] [rbp-24h] BYREF
  NTSTATUS AccessStatus; // [rsp+E8h] [rbp-20h] BYREF
  ACCESS_MASK v260; // [rsp+ECh] [rbp-1Ch] BYREF
  int v261; // [rsp+F0h] [rbp-18h] BYREF
  PVOID v262; // [rsp+F8h] [rbp-10h]
  int v263; // [rsp+100h] [rbp-8h] BYREF
  unsigned __int8 *v264; // [rsp+108h] [rbp+0h]
  ACCESS_MASK GrantedAccess; // [rsp+110h] [rbp+8h] BYREF
  size_t v266; // [rsp+118h] [rbp+10h]
  int v267; // [rsp+120h] [rbp+18h] BYREF
  __int64 v268; // [rsp+128h] [rbp+20h] BYREF
  __int64 v269; // [rsp+130h] [rbp+28h] BYREF
  __int64 v270; // [rsp+138h] [rbp+30h] BYREF
  _QWORD *v271; // [rsp+140h] [rbp+38h]
  unsigned int *v272; // [rsp+148h] [rbp+40h]
  __int128 v273; // [rsp+150h] [rbp+48h] BYREF
  __int128 v274; // [rsp+160h] [rbp+58h]
  ACL *v275; // [rsp+170h] [rbp+68h]
  __int128 SecurityDescriptor; // [rsp+178h] [rbp+70h] BYREF
  __int128 v277; // [rsp+188h] [rbp+80h]
  ACL *v278; // [rsp+198h] [rbp+90h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectSecurityContext; // [rsp+1A0h] [rbp+98h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+1C0h] [rbp+B8h] BYREF
  __int64 v281; // [rsp+1F0h] [rbp+E8h] BYREF
  __int64 v282; // [rsp+1F8h] [rbp+F0h]

  v272 = a5;
  v271 = a4;
  v247 = a3;
  v262 = 0;
  v244 = 0;
  *(_OWORD *)Src_8 = 0;
  *(_OWORD *)v242 = 0;
  if ( a2 < 4 )
  {
    v8 = -1073741762;
    goto LABEL_6;
  }
  v5 = *a1;
  v6 = (char *)(a1 + 1);
  if ( a1 + 1 < a1 )
    goto LABEL_5;
  if ( a2 - 4 < (unsigned int)v5 )
  {
    v8 = -1073741762;
    goto LABEL_6;
  }
  v7 = (unsigned int *)&v6[v5];
  Size = *a1;
  if ( &v6[v5] < v6 || (unsigned int)v5 >= 0xFFFFFFFC )
    goto LABEL_5;
  if ( a2 - ((_DWORD)v5 + 4) < 4 )
  {
    v8 = -1073741762;
    goto LABEL_6;
  }
  v21 = *v7;
  v22 = (char *)(v7 + 1);
  if ( v7 + 1 < v7 )
    goto LABEL_5;
  v23 = v5 + 8;
  if ( (int)v5 + 8 < (unsigned int)(v5 + 4) )
    goto LABEL_5;
  if ( a2 - v23 < (unsigned int)v21 )
  {
    v8 = -1073741762;
    goto LABEL_6;
  }
  v24 = (unsigned int *)&v22[v21];
  if ( &v22[v21] < v22 )
    goto LABEL_5;
  v25 = v23 + v21;
  if ( v23 + (unsigned int)v21 < v23 )
    goto LABEL_5;
  if ( a2 - v25 < 4 )
  {
    v8 = -1073741762;
    goto LABEL_6;
  }
  v26 = v24 + 1;
  if ( v24 + 1 < v24 )
    goto LABEL_5;
  v27 = v25 + 4;
  if ( v25 + 4 < v25 )
    goto LABEL_5;
  v28 = *v24;
  if ( a2 - v27 < (unsigned int)v28 )
  {
    v8 = -1073741762;
    goto LABEL_6;
  }
  if ( v27 + (unsigned int)v28 < v27 )
  {
LABEL_5:
    v8 = -1073741675;
LABEL_6:
    v9 = 0;
    Acl = v8;
    v11 = 0;
    v12 = 0;
    v13 = 0;
    goto LABEL_7;
  }
  if ( a2 != v27 + (_DWORD)v28 )
  {
    v8 = -1073741762;
    goto LABEL_6;
  }
  if ( (unsigned int)(v5 + v28 + v21) + 12LL != a2 )
  {
    v8 = -1073741762;
    goto LABEL_6;
  }
  Pool2 = (unsigned int *)ExAllocatePool2(256, 48, 542329939);
  v30 = Pool2;
  if ( !Pool2 )
  {
    v8 = -1073741801;
    goto LABEL_6;
  }
  *(_OWORD *)Pool2 = 0;
  *((_OWORD *)Pool2 + 1) = 0;
  *((_OWORD *)Pool2 + 2) = 0;
  if ( !v6 )
  {
    v8 = 0;
    goto LABEL_51;
  }
  *Pool2 = v5;
  if ( (_DWORD)v5 )
  {
    v40 = (void *)ExAllocatePool2(256, v5, 542329939);
    if ( !v40 )
    {
      LODWORD(v6) = 0;
      goto LABEL_482;
    }
    v41 = Size;
    *((_QWORD *)v30 + 1) = v40;
    v8 = 0;
    memmove(v40, v6, v41);
    LODWORD(v6) = 0;
LABEL_51:
    if ( v22 )
    {
      v30[4] = v21;
      if ( !(_DWORD)v21 )
      {
        v8 = -1073741762;
        goto LABEL_60;
      }
      v31 = (void *)ExAllocatePool2(256, v21, 542329939);
      if ( !v31 )
        goto LABEL_482;
      *((_QWORD *)v30 + 3) = v31;
      memmove(v31, v22, v21);
    }
    else
    {
      v30[4] = 0;
      *((_QWORD *)v30 + 3) = 0;
    }
    if ( !v26 )
    {
      v30[8] = 0;
      *((_QWORD *)v30 + 5) = 0;
      goto LABEL_59;
    }
    v30[8] = v28;
    if ( !(_DWORD)v28 )
    {
      v8 = -1073741762;
      goto LABEL_60;
    }
    v32 = (void *)ExAllocatePool2(256, v28, 542329939);
    if ( v32 )
    {
      *((_QWORD *)v30 + 5) = v32;
      memmove(v32, v26, v28);
LABEL_59:
      v33 = v30;
      v251 = (unsigned __int64)v30;
      goto LABEL_67;
    }
LABEL_482:
    v8 = -1073741801;
    goto LABEL_60;
  }
  v8 = -1073741762;
  LODWORD(v6) = 0;
LABEL_60:
  v34 = (void *)*((_QWORD *)v30 + 1);
  v33 = 0;
  v251 = 0;
  if ( v34 )
  {
    ExFreePoolWithTag(v34, 0);
    *((_QWORD *)v30 + 1) = 0;
  }
  v35 = (void *)*((_QWORD *)v30 + 3);
  if ( v35 )
  {
    ExFreePoolWithTag(v35, 0);
    *((_QWORD *)v30 + 3) = 0;
  }
  v36 = (void *)*((_QWORD *)v30 + 5);
  if ( v36 )
  {
    ExFreePoolWithTag(v36, 0);
    *((_QWORD *)v30 + 5) = 0;
  }
  ExFreePoolWithTag(v30, 0);
LABEL_67:
  if ( v8 < 0 )
  {
    if ( v33 )
    {
      v37 = (void *)*((_QWORD *)v33 + 1);
      if ( v37 )
      {
        ExFreePoolWithTag(v37, 0);
        *((_QWORD *)v33 + 1) = 0;
      }
      v38 = (void *)*((_QWORD *)v33 + 3);
      if ( v38 )
      {
        ExFreePoolWithTag(v38, 0);
        *((_QWORD *)v33 + 3) = 0;
      }
      v39 = (void *)*((_QWORD *)v33 + 5);
      if ( v39 )
      {
        ExFreePoolWithTag(v39, 0);
        *((_QWORD *)v33 + 5) = 0;
      }
      ExFreePoolWithTag(v33, 0);
    }
    goto LABEL_6;
  }
  if ( !v33 )
  {
    Acl = -1073741811;
    v241 = 0;
    goto LABEL_140;
  }
  v42 = (unsigned __int8 *)*((_QWORD *)v33 + 1);
  v266 = (size_t)v42;
  if ( !v42 )
  {
    Acl = -1073741811;
    v241 = v33;
    goto LABEL_140;
  }
  v43 = *v33;
  if ( !(_DWORD)v43 )
  {
    Acl = -1073741811;
    v241 = v33;
    goto LABEL_140;
  }
  v44 = (__int64 *)*((_QWORD *)v33 + 5);
  if ( !v44 )
  {
    Acl = -1073741811;
    v241 = v33;
    goto LABEL_140;
  }
  v45 = v33[8];
  if ( !v45 )
  {
    Acl = -1073741811;
    v241 = v33;
    goto LABEL_140;
  }
  v46 = *((_QWORD *)v33 + 3);
  if ( !v46 )
  {
    Acl = -1073741811;
    v241 = v33;
    goto LABEL_140;
  }
  v47 = v33[4];
  if ( !v47 )
  {
    Acl = -1073741811;
    v241 = v33;
    goto LABEL_140;
  }
  if ( v45 != 8 )
  {
    v241 = v33;
    goto LABEL_139;
  }
  if ( v47 != 160 )
  {
    v241 = v33;
    goto LABEL_139;
  }
  if ( v43 <= 8 )
  {
    v241 = v33;
    goto LABEL_139;
  }
  v48 = *v44;
  v49 = v43 - 8;
  v254 = (PVOID)(v43 - 8);
  v50 = ExAllocatePool2(256, v43 - 8, 542329939);
  Size = v50;
  if ( !v50 )
  {
    v241 = v33;
    goto LABEL_139;
  }
  v51 = v42;
  v256 = v42;
  LOBYTE(v248) = 0;
  v281 = v48;
  v52 = v33;
  v249 = (char *)(v49 & 7);
  v241 = v33;
  v255 = v50;
  if ( (v49 & 7) != 0 )
  {
    v93 = 0;
    v94 = 0;
    v95 = 0;
    v245 = 0;
    v246 = 0;
    v96 = 0;
    v97 = -1;
    do
    {
      v98 = *v51;
      v99 = 8 * v95;
      ++v51;
      if ( (unsigned int)v95 >= 4 )
        v93 |= v98 << (56 - v99);
      else
        v94 |= v98 << (24 - v99);
      ++v95;
    }
    while ( v95 < (unsigned __int8)(v49 & 7) );
    v246 = v94;
    v245 = v93;
    v256 = v51;
    v100 = 120;
    v101 = 120;
    v102 = 30;
    do
    {
      if ( *(_BYTE *)(v102 + v46 + 129) < 0x1Fu )
      {
        GenericMapping = v96;
        Privileges = (PPRIVILEGE_SET *)&v281;
        *(_QWORD *)PreviouslyGrantedAccess = *(unsigned __int8 *)(v100 + v46 + 7);
        v97 ^= guard_dispatch_icall_no_overrides(v102 + 1);
      }
      if ( *(_BYTE *)(v102 + v46 + 128) < 0x1Fu )
      {
        GenericMapping = v97;
        Privileges = (PPRIVILEGE_SET *)&v281;
        *(_QWORD *)PreviouslyGrantedAccess = *(unsigned __int8 *)(v100 + v46 + 3);
        v96 ^= guard_dispatch_icall_no_overrides(v102);
      }
      v102 -= 2;
      v101 -= 8;
      v100 -= 8;
    }
    while ( v101 != -8 );
    v53 = v246 ^ v96;
    v103 = 0;
    v104 = v245 ^ v97;
    v105 = v53;
    v106 = (unsigned int)v249;
    v107 = v104;
    if ( (_DWORD)v249 )
    {
      v108 = (_BYTE *)v255;
      do
      {
        v109 = (size_t)(v108 + 1);
        if ( v103 >= 4 )
        {
          v107 = __ROR4__(v107, 24);
          v110 = v107;
        }
        else
        {
          v105 = __ROR4__(v105, 24);
          v110 = v105;
        }
        ++v103;
        *v108++ = v110;
      }
      while ( (int)v103 < (int)v106 );
      v255 = v109;
    }
    LODWORD(v48) = v281;
    v49 = (unsigned __int64)v254;
    v51 = v256;
    if ( v106 <= 4 )
    {
      LODWORD(v6) = 0;
      if ( v106 < 4 )
        v53 = v53 >> (8 * (4 - v106)) << (8 * (4 - v106));
    }
    else
    {
      LODWORD(v6) = v104 >> (8 * (8 - v106)) << (8 * (8 - v106));
    }
  }
  else
  {
    v246 = 0;
    v245 = -1;
    v53 = 0;
    v241 = v52;
  }
  v249 = 0;
  v264 = (unsigned __int8 *)(v49 >> 3);
  if ( v49 >> 3 )
  {
    while ( 1 )
    {
      v54 = (unsigned __int16)v48;
      v55 = v51[5] | (v51[4] << 8);
      v252 = v51[3] | ((v51[2] | (((*v51 << 8) | v51[1]) << 8)) << 8);
      v56 = v51[7] | ((v51[6] | (v55 << 8)) << 8);
      v256 = v51 + 8;
      v253 = v56;
      v57 = v48 ^ HIDWORD(v281) ^ (unsigned int)v6 ^ v56 ^ v53 ^ v252;
      v58 = v53 ^ v252 ^ (v57 >> 8) ^ (WORD2(v281) * (v57 ^ WORD1(v281)));
      v59 = v57 ^ (WORD1(v281) * __ROR4__(HIDWORD(v281) - v58, 11) - __ROR4__(v58, 12));
      v60 = v58 ^ ((unsigned __int16)v48 * __ROR4__(HIDWORD(v281) ^ v59, 24) - __ROR4__(v59, 30));
      v61 = v59 ^ __ROR4__(v60, 9) ^ (HIWORD(v281) * __ROR4__(v60 - v48, 4));
      v62 = v60 ^ (__ROR4__(v61, 4) + WORD2(v281) * __ROR4__(v48 - v61, 10));
      v63 = v61 ^ (WORD1(v281) * __ROR4__(v62 ^ HIWORD(v281), 28) - __ROR4__(v62, 16));
      v64 = v62 ^ ((unsigned __int16)v48 * (v63 ^ WORD1(v281)) - __ROR4__(v63, 7));
      v65 = v63 ^ (v64 - HIWORD(v281) - v48);
      v66 = v64 ^ __ROR4__(v65, 11) ^ (WORD2(v281) * __ROR4__(v48 - v65, 9));
      v67 = 120;
      v68 = v65 ^ (WORD1(v281) * (v66 - WORD2(v281)) - (v66 >> 13));
      v69 = v54 * ((8 * (v68 - WORD2(v281))) | ((v68 - WORD2(v281)) >> 29));
      v70 = 120;
      v71 = v66 ^ (v68 >> 15) ^ v69;
      v72 = 30;
      do
      {
        if ( *(_BYTE *)(v72 + v46 + 129) < 0x1Fu )
        {
          GenericMapping = v71;
          Privileges = (PPRIVILEGE_SET *)&v281;
          *(_QWORD *)PreviouslyGrantedAccess = *(unsigned __int8 *)(v70 + v46 + 7);
          v68 ^= guard_dispatch_icall_no_overrides(v72 + 1);
        }
        if ( *(_BYTE *)(v72 + v46 + 128) < 0x1Fu )
        {
          GenericMapping = v68;
          Privileges = (PPRIVILEGE_SET *)&v281;
          *(_QWORD *)PreviouslyGrantedAccess = *(unsigned __int8 *)(v70 + v46 + 3);
          v71 ^= guard_dispatch_icall_no_overrides(v72);
        }
        v72 -= 2;
        v67 -= 8;
        v70 -= 8;
      }
      while ( v67 != -8 );
      v73 = (_BYTE *)v255;
      v53 = v246 ^ v71;
      LODWORD(v6) = v245 ^ v68;
      *(_BYTE *)(v255 + 3) = v53;
      v73[7] = (_BYTE)v6;
      v73[2] = __ROR4__(v53, 8);
      v73[6] = __ROR4__((_DWORD)v6, 8);
      v73[1] = __ROR4__(v53, 16);
      v73[5] = __ROR4__((_DWORD)v6, 16);
      *v73 = __ROR4__(v53, 24);
      v73[4] = __ROR4__((_DWORD)v6, 24);
      v246 = v252;
      v245 = v253;
      v255 = (size_t)(v73 + 8);
      if ( ++v249 >= (char *)v264 )
        break;
      LODWORD(v48) = v281;
      v51 = v256;
    }
    v49 = (unsigned __int64)v254;
  }
  if ( !v49 )
  {
    v83 = v248;
    goto LABEL_110;
  }
  v74 = 0;
  if ( v49 < 0x20 )
  {
    v83 = v248;
    do
    {
LABEL_109:
      v83 ^= *(_BYTE *)(v74 + Size);
      ++v74;
    }
    while ( v74 < v49 );
    goto LABEL_110;
  }
  v75 = 0;
  v76 = 0;
  do
  {
    v75 = _mm_xor_ps(v75, (__m128)_mm_loadu_si128((const __m128i *)(v74 + Size)));
    v77 = (__m128)_mm_loadu_si128((const __m128i *)(v74 + Size + 16));
    v74 += 32LL;
    v78 = _mm_xor_ps(v77, v76);
    v76 = v78;
  }
  while ( v74 < (v49 & 0xFFFFFFFFFFFFFFE0uLL) );
  v79 = _mm_xor_ps(v75, v78);
  v80 = _mm_xor_ps(v79, (__m128)_mm_srli_si128((__m128i)v79, 8));
  v81 = _mm_xor_ps(v80, (__m128)_mm_srli_si128((__m128i)v80, 4));
  v82 = _mm_xor_ps(v81, (__m128)_mm_srli_si128((__m128i)v81, 2));
  v83 = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v82, (__m128)_mm_srli_si128((__m128i)v82, 1)));
  if ( v74 < v49 )
    goto LABEL_109;
LABEL_110:
  if ( v83 != *(_QWORD *)(v49 + v266) )
  {
    ExFreePoolWithTag((PVOID)Size, 0);
LABEL_139:
    Acl = -1073741823;
LABEL_140:
    v11 = v244;
    v9 = v241;
    v12 = v244;
    v13 = v244;
    goto LABEL_7;
  }
  v84 = (int *)Size;
  v262 = (PVOID)Size;
  if ( (unsigned int)v49 < 4 )
    goto LABEL_496;
  if ( Size + 4 < Size )
    goto LABEL_126;
  if ( (unsigned int)(v49 - 4) < 4 )
  {
    Acl = -1073741762;
    goto LABEL_127;
  }
  v85 = (const void *)(Size + 8);
  if ( Size + 8 < Size + 4 )
    goto LABEL_126;
  v86 = *(unsigned int *)(Size + 4);
  if ( (int)v254 - 8 < (unsigned int)v86 )
  {
    Acl = -1073741762;
    goto LABEL_127;
  }
  if ( (unsigned int)v86 >= 0xFFFFFFF8 )
    goto LABEL_126;
  v87 = (unsigned __int64)v85 + v86;
  if ( (unsigned int)v254 + Size < (unsigned __int64)v85 + v86 || (unsigned int)v254 - v86 - 8 >= 8 )
  {
LABEL_496:
    Acl = -1073741762;
    goto LABEL_127;
  }
  v88 = 0;
  if ( Size == -8 )
    goto LABEL_132;
  if ( v87 < (unsigned __int64)v85 )
  {
LABEL_126:
    Acl = -1073741675;
    goto LABEL_127;
  }
  v89 = (char *)(Size + 8);
  while ( (unsigned __int64)v89 < v87 )
  {
    if ( v89 + 4 < v89 )
      goto LABEL_126;
    if ( (unsigned __int64)(v89 + 4) > v87 )
      goto LABEL_500;
    if ( *(_DWORD *)v89 >= 0xFFFFFFFC )
      goto LABEL_126;
    v90 = *(_DWORD *)v89 + 4;
    v111 = &v89[v90];
    if ( v111 < v89 )
      goto LABEL_126;
    if ( (unsigned __int64)v111 > v87 )
    {
      Acl = -1073741811;
      goto LABEL_127;
    }
    v89 += v90;
    ++v88;
  }
  if ( v89 != (char *)v87 )
  {
LABEL_500:
    Acl = -1073741811;
LABEL_127:
    v11 = v244;
    v9 = v241;
    v12 = v244;
    v13 = v244;
    goto LABEL_7;
  }
  v84 = (int *)v262;
LABEL_132:
  v91 = *v84;
  v92 = 0;
  if ( (_DWORD)v86 )
  {
    v92 = (void *)ExAllocatePool2(256, v86, 542329939);
    if ( !v92 )
    {
      Acl = -1073741801;
      goto LABEL_127;
    }
  }
  if ( Size != -8 )
    memmove(v92, v85, v86);
  Src_8[1] = v92;
  Src_8[0] = (PVOID)__PAIR64__(v86, v88);
  if ( v91 != v88 )
  {
    Acl = -1073741762;
    v11 = v244;
    v9 = v241;
    v12 = v244;
    v13 = v244;
    goto LABEL_7;
  }
  v9 = v241;
  if ( !Src_8[1] )
  {
    v11 = v244;
    Acl = -1073741811;
    v12 = v244;
    v13 = v244;
    goto LABEL_7;
  }
  if ( !v88 )
  {
    v11 = v244;
    Acl = -1073741811;
    v12 = v244;
    v13 = v244;
    goto LABEL_7;
  }
  if ( (char *)Src_8[1] + 4 < Src_8[1] )
    goto LABEL_214;
  v168 = 0;
  if ( *(_DWORD *)Src_8[1] )
    v168 = (int *)((char *)Src_8[1] + 4);
  if ( *(_DWORD *)Src_8[1] != 4 )
  {
    Acl = -1073741789;
    goto LABEL_215;
  }
  if ( v88 <= 1 )
  {
    Acl = -1073741811;
    goto LABEL_215;
  }
  v169 = (unsigned int *)Src_8[1];
  v170 = 0;
  v171 = *v168;
  while ( 1 )
  {
    v172 = *v169;
    v173 = v169 + 1;
    if ( v170 )
      break;
    if ( v173 < v169 )
      goto LABEL_214;
    v169 = (unsigned int *)((char *)v173 + v172);
    if ( (unsigned int *)((char *)v173 + v172) < v173 )
      goto LABEL_214;
    v170 = 1;
  }
  if ( v173 < v169 )
    goto LABEL_214;
  v174 = 0;
  if ( (_DWORD)v172 )
    v174 = v169 + 1;
  if ( v88 <= 2 )
  {
    Acl = -1073741811;
    goto LABEL_215;
  }
  v175 = (unsigned int *)Src_8[1];
  for ( i = 0; ; ++i )
  {
    v177 = *v175;
    v178 = v175 + 1;
    if ( i >= 2 )
      break;
    if ( v178 < v175 )
      goto LABEL_214;
    v175 = (unsigned int *)((char *)v178 + v177);
    if ( (unsigned int *)((char *)v178 + v177) < v178 )
      goto LABEL_214;
  }
  if ( v178 < v175 )
  {
LABEL_214:
    Acl = -1073741675;
LABEL_215:
    v11 = v244;
    v12 = v244;
    v13 = v244;
    goto LABEL_7;
  }
  v179 = 0;
  if ( (_DWORD)v177 )
    v179 = v175 + 1;
  v180 = ExAllocatePool2(256, 48, 542329939);
  v183 = (unsigned int *)v180;
  if ( !v180 )
  {
    Acl = -1073741801;
    goto LABEL_215;
  }
  *(_QWORD *)v180 = 0;
  *(_QWORD *)(v180 + 20) = 0;
  *(_QWORD *)(v180 + 28) = 0;
  *(_QWORD *)(v180 + 36) = 0;
  *(_DWORD *)(v180 + 44) = 0;
  *(_QWORD *)(v180 + 8) = 0;
  if ( v174 )
  {
    *(_DWORD *)(v180 + 16) = v172;
    if ( !(_DWORD)v172 )
    {
      Acl = -1073741762;
      goto LABEL_434;
    }
    v184 = (void *)ExAllocatePool2(256, v172, 542329939);
    if ( !v184 )
    {
LABEL_509:
      Acl = -1073741801;
      goto LABEL_434;
    }
    *((_QWORD *)v183 + 3) = v184;
    memmove(v184, v174, v172);
  }
  else
  {
    *(_DWORD *)(v180 + 16) = 0;
  }
  if ( v179 )
  {
    v183[8] = v177;
    if ( (_DWORD)v177 )
    {
      v185 = (void *)ExAllocatePool2(256, v177, 542329939);
      if ( v185 )
      {
        *((_QWORD *)v183 + 5) = v185;
        memmove(v185, v179, v177);
        goto LABEL_246;
      }
      goto LABEL_509;
    }
    Acl = -1073741762;
LABEL_434:
    v234 = (void *)*((_QWORD *)v183 + 1);
    if ( v234 )
    {
      ExFreePoolWithTag(v234, 0);
      *((_QWORD *)v183 + 1) = 0;
    }
    v235 = (void *)*((_QWORD *)v183 + 3);
    if ( v235 )
    {
      ExFreePoolWithTag(v235, 0);
      *((_QWORD *)v183 + 3) = 0;
    }
    v236 = (void *)*((_QWORD *)v183 + 5);
    if ( v236 )
    {
      ExFreePoolWithTag(v236, 0);
      *((_QWORD *)v183 + 5) = 0;
    }
    ExFreePoolWithTag(v183, 0);
    v11 = v244;
    v12 = v244;
    v13 = v244;
    goto LABEL_7;
  }
  v183[8] = 0;
  *((_QWORD *)v183 + 5) = 0;
LABEL_246:
  v244 = v183;
  v11 = v183;
  if ( v171 )
  {
    switch ( v171 )
    {
      case 1:
        Blink = ExpPlatformBinaryLock.GlobalForegroundListEntry.Blink;
        v260 = 0;
        v273 = 0;
        v275 = 0;
        v274 = 0;
        v257 = 0;
        memset(&SubjectSecurityContext, 0, sizeof(SubjectSecurityContext));
        v203 = RtlLengthSid(*(PSID *)(ExpPlatformBinaryLock.InGlobalForegroundList + 384));
        v204 = RtlLengthSid(Blink[17].Flink) + v203;
        v205 = RtlLengthSid(Blink[24].Blink) + 32 + v204;
        v206 = (ACL *)ExAllocatePool2(256, v205, 542329939);
        v207 = v206;
        if ( !v206 )
        {
          Acl = -1073741801;
          goto LABEL_292;
        }
        Acl = RtlCreateAcl(v206, v205, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlpAddKnownAce((int)v207, 2, 0, 32, Blink[24].Flink, 0);
          if ( Acl >= 0 )
          {
            Acl = RtlpAddKnownAce((int)v207, 2, 0, 32, Blink[24].Blink, 0);
            if ( Acl >= 0 )
            {
              Acl = RtlpAddKnownAce((int)v207, 2, 0, 32, Blink[17].Flink, 0);
              if ( Acl >= 0 )
              {
                v275 = v207;
                v273 = 0;
                LOBYTE(v273) = 1;
                WORD1(v273) = 4;
                v274 = 0;
                Acl = 0;
                SeCaptureSubjectContext(&SubjectSecurityContext);
                v208 = SeAccessCheck(
                         &v273,
                         &SubjectSecurityContext,
                         0,
                         0x20u,
                         0,
                         0,
                         (PGENERIC_MAPPING)&IopFileMapping,
                         1,
                         &v260,
                         &v257);
                SeReleaseSubjectContext(&SubjectSecurityContext);
                if ( !v208 )
                  Acl = v257;
              }
            }
          }
        }
        ExFreePoolWithTag(v207, 0);
        if ( Acl < 0 )
          goto LABEL_292;
        v267 = 0;
        v268 = 8;
        ZwQuerySystemInformation(103, &v268, 8, &v267, *(_QWORD *)PreviouslyGrantedAccess, Privileges, GenericMapping);
        if ( *(_DWORD *)(v251 + 16) != 160 )
          goto LABEL_291;
        v209 = *(const void **)(v251 + 24);
        if ( (memcmp(qword_140B7D8C0, v209, 0xA0u)
           || v183[4] != 160
           || memcmp(qword_140B7D960, *((const void **)v183 + 3), 0xA0u)
           || *(_DWORD *)(v251 + 32) != 8
           || **(_QWORD **)(v251 + 40) != 0xA564595855B292C4uLL
           || v183[8] != 8
           || **((_QWORD **)v183 + 5) != 0x1B732BD76B4D09FCLL)
          && (memcmp(qword_140B7DBE0, v209, 0xA0u)
           || v183[4] != 160
           || memcmp(qword_140B7D640, *((const void **)v183 + 3), 0xA0u)
           || *(_DWORD *)(v251 + 32) != 8
           || **(_QWORD **)(v251 + 40) != 0x93278D843BBDC445uLL
           || v183[8] != 8
           || **((_QWORD **)v183 + 5) != 0x6223E824AB21D998LL) )
        {
          goto LABEL_291;
        }
        if ( (KeGetCurrentThread()->ApcState.Process[3].ActiveGroupsMask.Masks[1] & 0x70000) != 0 )
          Acl = 0;
        else
          Acl = -2147024891;
        if ( Acl < 0 )
          goto LABEL_292;
        Acl = SPCallServerHandleUpdatePolicies(Src_8, v183, v247, v242);
        v11 = v183;
        if ( Acl >= 0 )
          goto LABEL_248;
        v12 = 0;
        v13 = 0;
        goto LABEL_7;
      case 2:
        LicenseChallenge = sub_140AEC698(
                             v181,
                             v183,
                             v247,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 4:
        LicenseChallenge = sub_140AB5A3C(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 5:
        LicenseChallenge = SPCallServerHandleWaitForDisplayWindow(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 6:
        LicenseChallenge = sub_14072FC94(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 7:
        LicenseChallenge = sub_14072F9FC(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 22:
        LicenseChallenge = sub_140A19F38(
                             Src_8,
                             0x140000000uLL,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 23:
        v189 = ExpPlatformBinaryLock.GlobalForegroundListEntry.Blink;
        GrantedAccess = 0;
        SecurityDescriptor = 0;
        v278 = 0;
        v277 = 0;
        AccessStatus = 0;
        memset(&SubjectContext, 0, sizeof(SubjectContext));
        v190 = RtlLengthSid(*(PSID *)(ExpPlatformBinaryLock.InGlobalForegroundList + 384));
        v191 = RtlLengthSid(v189[17].Flink) + v190;
        v192 = RtlLengthSid(v189[24].Blink) + 32 + v191;
        v193 = (ACL *)ExAllocatePool2(256, v192, 542329939);
        v194 = v193;
        if ( v193 )
        {
          Acl = RtlCreateAcl(v193, v192, 2u);
          if ( Acl >= 0 )
          {
            Acl = RtlpAddKnownAce((int)v194, 2, 0, 32, v189[24].Flink, 0);
            if ( Acl >= 0 )
            {
              Acl = RtlpAddKnownAce((int)v194, 2, 0, 32, v189[24].Blink, 0);
              if ( Acl >= 0 )
              {
                Acl = RtlpAddKnownAce((int)v194, 2, 0, 32, v189[17].Flink, 0);
                if ( Acl >= 0 )
                {
                  v278 = v194;
                  SecurityDescriptor = 0;
                  LOBYTE(SecurityDescriptor) = 1;
                  WORD1(SecurityDescriptor) = 4;
                  v277 = 0;
                  Acl = 0;
                  SeCaptureSubjectContext(&SubjectContext);
                  v195 = SeAccessCheck(
                           &SecurityDescriptor,
                           &SubjectContext,
                           0,
                           0x20u,
                           0,
                           0,
                           (PGENERIC_MAPPING)&IopFileMapping,
                           1,
                           &GrantedAccess,
                           &AccessStatus);
                  SeReleaseSubjectContext(&SubjectContext);
                  if ( !v195 )
                    Acl = AccessStatus;
                }
              }
            }
          }
          ExFreePoolWithTag(v194, 0);
          if ( Acl >= 0 )
          {
            v263 = 0;
            v269 = 8;
            ZwQuerySystemInformation(
              103,
              &v269,
              8,
              &v263,
              *(_QWORD *)PreviouslyGrantedAccess,
              Privileges,
              GenericMapping);
            if ( *(_DWORD *)(v251 + 16) == 160
              && ((v196 = *(const void **)(v251 + 24), !memcmp(qword_140B7D820, v196, 0xA0u))
               && v183[4] == 160
               && !memcmp(qword_140B7D780, *((const void **)v183 + 3), 0xA0u)
               && *(_DWORD *)(v251 + 32) == 8
               && **(_QWORD **)(v251 + 40) == 0x35DCEB18766AABAALL
               && v183[8] == 8
               && **((_QWORD **)v183 + 5) == 0x14CEA8BAE086077CLL
               || !memcmp(qword_140B7DAA0, v196, 0xA0u)
               && v183[4] == 160
               && !memcmp(qword_140B7DF00, *((const void **)v183 + 3), 0xA0u)
               && *(_DWORD *)(v251 + 32) == 8
               && **(_QWORD **)(v251 + 40) == 0xF10D668DB2BB8BB9uLL
               && v183[8] == 8
               && **((_QWORD **)v183 + 5) == 0x768DFD321621EA95LL
               || !memcmp(qword_140B7DFA0, v196, 0xA0u)
               && v183[4] == 160
               && !memcmp(sub_140B7D5A0, *((const void **)v183 + 3), 0xA0u)
               && *(_DWORD *)(v251 + 32) == 8
               && **(_QWORD **)(v251 + 40) == 0xA10B922F1A2F2A8AuLL
               && v183[8] == 8
               && **((_QWORD **)v183 + 5) == 0xC349B50B0A716A96uLL
               || !memcmp(qword_140B7DC80, v196, 0xA0u)
               && v183[4] == 160
               && !memcmp(qword_140B7DB40, *((const void **)v183 + 3), 0xA0u)
               && *(_DWORD *)(v251 + 32) == 8
               && **(_QWORD **)(v251 + 40) == 0xA6723CF736811074uLL
               && v183[8] == 8
               && **((_QWORD **)v183 + 5) == 0x7511056E178DA076LL) )
            {
              Acl = 0;
              v258 = 0;
              updated = QueryUpdateFileEaAllowedExt(&v258);
              if ( updated == -1073741637 || (Acl = updated, updated >= 0) && v258 != 1 )
              {
                if ( (KeGetCurrentThread()->ApcState.Process[3].ActiveGroupsMask.Masks[1] & 0x70000) == 0 )
                  Acl = -2147024891;
              }
              if ( Acl >= 0 )
              {
                LicenseChallenge = sub_140A1A884(Src_8, v198, v199, v242);
                v11 = v183;
                goto LABEL_259;
              }
            }
            else
            {
LABEL_291:
              Acl = -2147024891;
            }
          }
        }
        else
        {
          Acl = -1073741801;
        }
LABEL_292:
        v12 = 0;
        v11 = v183;
        v13 = 0;
        goto LABEL_7;
      case 24:
        LicenseChallenge = sub_140A1A34C(
                             Src_8,
                             0x140000000uLL,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 100:
        LicenseChallenge = sub_140AA6D78(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 101:
        LicenseChallenge = sub_14072F1D0(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 102:
        v12 = 0;
        Acl = -1073741822;
        v13 = 0;
        goto LABEL_7;
      case 103:
        LicenseChallenge = sub_140AF6E34(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 104:
        LicenseChallenge = sub_140AFD588(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 105:
        LicenseChallenge = SPCallServerHandleGetLicenseChallenge(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 106:
        LicenseChallenge = sub_140AF5B38(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 107:
        LicenseChallenge = sub_1404E0378(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 109:
        LicenseChallenge = sub_140A546AC(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 110:
        LicenseChallenge = sub_140AFF8A4(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 111:
        LicenseChallenge = sub_140729D5C(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 112:
        LicenseChallenge = sub_140AEAB94(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 113:
        LicenseChallenge = sub_140A5C930(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 204:
        LicenseChallenge = sub_140AFECA8(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 205:
        LicenseChallenge = sub_140A8DF50(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 206:
        v261 = 0;
        v270 = 8;
        ZwQuerySystemInformation(103, &v270, 8, &v261, *(_QWORD *)PreviouslyGrantedAccess, Privileges, GenericMapping);
        if ( *(_DWORD *)(v251 + 16) != 160
          || ((v200 = *(const void **)(v251 + 24), memcmp(qword_140B7DD20, v200, 0xA0u))
           || v183[4] != 160
           || memcmp(qword_140B7DDC0, *((const void **)v183 + 3), 0xA0u)
           || *(_DWORD *)(v251 + 32) != 8
           || **(_QWORD **)(v251 + 40) != 0x5638EBB72F3355A5LL
           || v183[8] != 8
           || **((_QWORD **)v183 + 5) != 0x9F2DD8784FE939B7uLL)
          && (memcmp(qword_140B7DA00, v200, 0xA0u)
           || v183[4] != 160
           || memcmp(qword_140B7DE60, *((const void **)v183 + 3), 0xA0u)
           || *(_DWORD *)(v251 + 32) != 8
           || **(_QWORD **)(v251 + 40) != 0x5638EBB72F3355A5LL
           || v183[8] != 8
           || **((_QWORD **)v183 + 5) != 0x9F2DD8784FE939B7uLL)
          && (memcmp(qword_140B7D460, v200, 0xA0u)
           || v183[4] != 160
           || memcmp(qword_140B7D6E0, *((const void **)v183 + 3), 0xA0u)
           || *(_DWORD *)(v251 + 32) != 8
           || **(_QWORD **)(v251 + 40) != 0xF10D668DB2BB8BB9uLL
           || v183[8] != 8
           || **((_QWORD **)v183 + 5) != 0x768DFD321621EA95LL)
          && (memcmp(qword_140B7D3C0, v200, 0xA0u)
           || v183[4] != 160
           || memcmp(qword_140B7D500, *((const void **)v183 + 3), 0xA0u)
           || *(_DWORD *)(v251 + 32) != 8
           || **(_QWORD **)(v251 + 40) != 0xF10D668DB2BB8BB9uLL
           || v183[8] != 8
           || **((_QWORD **)v183 + 5) != 0x768DFD321621EA95LL) )
        {
          v12 = 0;
          Acl = -2147024891;
          v13 = 0;
          goto LABEL_7;
        }
        LicenseChallenge = SPCallServerHandleGetCurrentHardwareID(Src_8, v183, v201, v242);
LABEL_259:
        Acl = LicenseChallenge;
        if ( LicenseChallenge < 0 )
          goto LABEL_260;
        goto LABEL_248;
      case 207:
        LicenseChallenge = sub_140AF73D4(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 208:
        LicenseChallenge = sub_140A77B14(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 209:
        LicenseChallenge = sub_140AFC940(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 210:
        LicenseChallenge = sub_140729158(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 211:
        LicenseChallenge = sub_140B00BF4(
                             Src_8,
                             v183,
                             v182,
                             v242,
                             *(_QWORD *)PreviouslyGrantedAccess,
                             Privileges,
                             GenericMapping);
        goto LABEL_259;
      case 212:
        v210 = (unsigned int *)Src_8[1];
        if ( !Src_8[1] )
        {
          v12 = 0;
          Acl = -1073741811;
          v13 = 0;
          goto LABEL_7;
        }
        if ( LODWORD(Src_8[0]) <= 3 )
        {
          v12 = 0;
          Acl = -1073741811;
          v13 = 0;
          goto LABEL_7;
        }
        for ( j = 0; ; ++j )
        {
          v212 = *v210;
          v213 = v210 + 1;
          if ( j >= 3 )
            break;
          if ( v213 < v210 )
            goto LABEL_360;
          v210 = (unsigned int *)((char *)v213 + v212);
          if ( (unsigned int *)((char *)v213 + v212) < v213 )
            goto LABEL_360;
        }
        if ( v213 < v210 )
          goto LABEL_360;
        v214 = 0;
        if ( (_DWORD)v212 )
          v214 = (__int64 *)(v210 + 1);
        if ( (_DWORD)v212 != 8 )
        {
          Acl = -1073741789;
          goto LABEL_361;
        }
        if ( LODWORD(Src_8[0]) <= 4 )
        {
          v12 = 0;
          Acl = -1073741811;
          v13 = 0;
          goto LABEL_7;
        }
        v215 = (unsigned int *)Src_8[1];
        v216 = 0;
        v217 = *v214;
        while ( 1 )
        {
          v218 = *v215;
          v219 = v215 + 1;
          if ( v216 >= 4 )
            break;
          if ( v219 < v215 )
            goto LABEL_360;
          v215 = (unsigned int *)((char *)v219 + v218);
          if ( (unsigned int *)((char *)v219 + v218) < v219 )
            goto LABEL_360;
          ++v216;
        }
        if ( v219 < v215 )
          goto LABEL_360;
        if ( !(_DWORD)v218 )
        {
          Acl = -1073741762;
          goto LABEL_361;
        }
        v220 = v215 + 1;
        v221 = (void *)ExAllocatePool2(256, *v215, 542329939);
        if ( !v221 )
        {
          Acl = -1073741801;
          goto LABEL_361;
        }
        memmove(v221, v220, v218);
        if ( (_DWORD)v218 != 4 )
        {
          Acl = -1073741306;
          goto LABEL_361;
        }
        v222 = (unsigned int *)Src_8[1];
        if ( LODWORD(Src_8[0]) <= 5 )
        {
          v12 = 0;
          Acl = -1073741811;
          v13 = 0;
          goto LABEL_7;
        }
        for ( k = 0; ; ++k )
        {
          v224 = *v222;
          v225 = v222 + 1;
          if ( k >= 5 )
            break;
          if ( v225 < v222 )
            goto LABEL_360;
          v222 = (unsigned int *)((char *)v225 + v224);
          if ( (unsigned int *)((char *)v225 + v224) < v225 )
            goto LABEL_360;
        }
        if ( v225 < v222 )
        {
LABEL_360:
          Acl = -1073741675;
          goto LABEL_361;
        }
        if ( !(_DWORD)v224 )
        {
          Acl = -1073741762;
          goto LABEL_361;
        }
        v226 = v222 + 1;
        v227 = (void *)ExAllocatePool2(256, *v222, 542329939);
        if ( !v227 )
        {
          Acl = -1073741801;
          goto LABEL_361;
        }
        memmove(v227, v226, v224);
        if ( (_DWORD)v224 != 8 )
        {
          Acl = -1073741306;
          goto LABEL_361;
        }
        v228 = guard_dispatch_icall_no_overrides(*v220);
        HIDWORD(v242[0]) = 20;
        v229 = (_DWORD *)ExAllocatePool2(256, 20, 542329939);
        if ( !v229 )
        {
          Acl = -1073741801;
          goto LABEL_361;
        }
        v242[1] = v229;
        LODWORD(v242[0]) = 0;
        if ( v229 + 1 < v229 )
          goto LABEL_406;
        if ( v229 + 2 > (_DWORD *)((char *)v242[1] + HIDWORD(v242[0])) )
        {
          Acl = -1073741789;
        }
        else
        {
          *v229 = 4;
          v229[1] = v228 | 0x10000000;
          v230 = (unsigned __int64)v242[1];
          v231 = ++LODWORD(v242[0]);
          if ( v242[1] )
          {
            for ( m = 0; m < v231; ++m )
            {
              v233 = *(_DWORD *)v230 + 4;
              if ( *(_DWORD *)v230 >= 0xFFFFFFFC || v230 + v233 < v230 )
                goto LABEL_406;
              v230 += v233;
            }
            if ( v230 + 4 < v230 )
            {
LABEL_406:
              Acl = -1073741675;
            }
            else if ( (PVOID)(v230 + 12) > (char *)v242[1] + HIDWORD(v242[0]) )
            {
              Acl = -1073741789;
            }
            else
            {
              *(_DWORD *)v230 = 8;
              Acl = 0;
              *(_QWORD *)(v230 + 4) = v217;
              ++LODWORD(v242[0]);
            }
          }
          else
          {
            Acl = RtlUIntAdd(HIDWORD(v242[0]), 0xCu, (UINT *)v242 + 1);
            if ( Acl >= 0 )
            {
              ++LODWORD(v242[0]);
              Acl = 0;
            }
          }
        }
        if ( Acl >= 0 )
          goto LABEL_248;
LABEL_361:
        v12 = 0;
        v13 = 0;
        goto LABEL_7;
      default:
        LicenseChallenge = sub_14098EDF8(v181, v242);
        goto LABEL_259;
    }
  }
  Acl = SPCallServerHandleQueryPolicy(
          Src_8,
          v183,
          v247,
          v242,
          *(_QWORD *)PreviouslyGrantedAccess,
          Privileges,
          GenericMapping);
  if ( Acl >= 0 )
  {
LABEL_248:
    v186 = __rdtsc();
    if ( HIDWORD(v242[0]) >= 0xFFFFFFF8
      || (v187 = (HIDWORD(v242[0]) + 15) & 0xFFFFFFF8, (unsigned int)v187 < HIDWORD(v242[0]) + 8) )
    {
      Acl = -1073741675;
      goto LABEL_255;
    }
    if ( !(_DWORD)v187 )
    {
      Acl = -1073741762;
      goto LABEL_255;
    }
    v127 = (_DWORD *)ExAllocatePool2(256, (unsigned int)v187, 542329939);
    if ( !v127 )
    {
      Acl = -1073741801;
      goto LABEL_255;
    }
    *v127 = v242[0];
    if ( v127 + 1 < v127 || (v127[1] = HIDWORD(v242[0]), v127 + 2 < v127 + 1) )
    {
      Acl = -1073741675;
      ExFreePoolWithTag(v127, 0);
LABEL_255:
      v12 = 0;
      v13 = 0;
      goto LABEL_7;
    }
    *(_QWORD *)((char *)v127 + v187 - 8) = v186;
    memmove(v127 + 2, v242[1], HIDWORD(v242[0]));
    v112 = (__int64 *)*((_QWORD *)v11 + 5);
    v240 = v127;
    if ( v112 )
    {
      v113 = v11[8];
      if ( !v113 )
      {
        Acl = -1073741811;
        goto LABEL_195;
      }
      v114 = *((_QWORD *)v11 + 3);
      if ( !v114 )
      {
        Acl = -1073741811;
        goto LABEL_195;
      }
      v115 = v11[4];
      if ( !v115 )
      {
        Acl = -1073741811;
        goto LABEL_195;
      }
      v116 = (unsigned int)v187;
      v251 = (unsigned int)v187;
      if ( v113 == 8 && v115 == 160 )
      {
        v117 = *v112;
        LOBYTE(v115) = 0;
        v247 = v115;
        v118 = 0;
        if ( v116 < 0x20 )
          goto LABEL_536;
        v240 = v127;
        v119 = 0;
        v120 = 0;
        do
        {
          v119 = _mm_xor_ps(v119, (__m128)_mm_loadu_si128((const __m128i *)((char *)v127 + v118)));
          v121 = (__m128)_mm_loadu_si128((const __m128i *)((char *)v127 + v118 + 16));
          v118 += 32LL;
          v122 = _mm_xor_ps(v121, v120);
          v120 = v122;
        }
        while ( v118 < (v116 & 0xFFFFFFE0) );
        v123 = _mm_xor_ps(v119, v122);
        v124 = _mm_xor_ps(v123, (__m128)_mm_srli_si128((__m128i)v123, 8));
        v125 = _mm_xor_ps(v124, (__m128)_mm_srli_si128((__m128i)v124, 4));
        v126 = _mm_xor_ps(v125, (__m128)_mm_srli_si128((__m128i)v125, 2));
        v115 = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v126, (__m128)_mm_srli_si128((__m128i)v126, 1)));
        v247 = v115;
        if ( v118 < v116 )
        {
LABEL_536:
          do
            LOBYTE(v115) = *((_BYTE *)v127 + v118++) ^ v115;
          while ( v118 < v116 );
          v127 = v240;
          v247 = v115;
        }
        v128 = v116 + 8;
        v255 = v116 + 8;
        v254 = (PVOID)ExAllocatePool2(256, v116 + 8, 542329939);
        v129 = (char *)v254;
        if ( v254 )
        {
          v130 = 0;
          v282 = v117;
          v248 = 0;
          v245 = 0;
          v266 = v116 >> 3;
          Size = 0;
          v240 = v127;
          if ( v116 >> 3 )
          {
            v249 = (char *)v254;
            v131 = (unsigned __int8 *)v127;
            v132 = -1;
            do
            {
              v133 = 0;
              v134 = 0;
              v135 = v131[5] | (v131[4] << 8);
              v252 = v131[3] | ((v131[2] | ((v131[1] | (*v131 << 8)) << 8)) << 8);
              v136 = v252 ^ v130;
              v137 = v131[7] | ((v131[6] | (v135 << 8)) << 8);
              v264 = v131 + 8;
              v138 = v137 ^ v132;
              v246 = v137;
              v139 = 0;
              do
              {
                if ( *(_BYTE *)(v133 + v114 + 128) < 0x1Fu )
                  v136 ^= guard_dispatch_icall_no_overrides(v133);
                if ( *(_BYTE *)(v133 + v114 + 129) < 0x1Fu )
                  v138 ^= guard_dispatch_icall_no_overrides(v133 + 1);
                v133 += 2;
                v134 += 8;
                v139 += 8;
              }
              while ( v134 != 128 );
              v140 = v136 ^ (HIWORD(v282) * ((unsigned __int16)v282 + __ROR4__(~v138, 5)));
              v141 = v138 ^ (v140 >> 10) ^ (WORD1(v282) * (v140 ^ HIWORD(v282)));
              v142 = v140 ^ __ROR4__(v141, 10) ^ (WORD2(v282) * __ROR4__(v141 ^ v282, 12));
              v143 = v141 ^ (HIWORD(v282) * __ROR4__(v142 - v282, 14) - __ROR4__(v142, 24));
              v144 = v142 ^ (__ROR4__(v143, 30) + (unsigned __int16)v282 * __ROR4__(HIDWORD(v282) + v143, 15));
              v145 = v143 ^ (WORD1(v282) * (v144 ^ WORD2(v282))) ^ __ROR4__(v144, 6);
              v146 = v144 ^ (HIDWORD(v282) - (v282 ^ v145));
              v147 = v145 ^ (HIWORD(v282) * __ROR4__(v146 ^ WORD1(v282), 26) - __ROR4__(v146, 30));
              v148 = v146 ^ ((unsigned __int16)v282 * (v147 - WORD2(v282)) - (v147 >> 13));
              v149 = v147 ^ (WORD1(v282) * __ROR4__(v148 + HIDWORD(v282), 9) - __ROR4__(v148, 30));
              v150 = v248;
              v248 = v252;
              v151 = v148 ^ (__ROR4__(v149, 22) + WORD2(v282) * __ROR4__(v149 - v282, 27));
              v130 = v151 ^ v150;
              v152 = v151 ^ v245;
              v245 = v246;
              v131 = v264;
              v153 = v149 ^ v152;
              v154 = v249;
              v253 = HIDWORD(v282) ^ v153;
              v132 = v282 ^ HIDWORD(v282) ^ v153;
              v249[3] = v130;
              v154[7] = v132;
              v154[2] = __ROR4__(v130, 8);
              v154[6] = __ROR4__(v132, 8);
              v154[1] = __ROR4__(v130, 16);
              v154[5] = __ROR4__(v132, 16);
              *v154 = __ROR4__(v130, 24);
              v154[4] = __ROR4__(v132, 24);
              v249 = v154 + 8;
              ++Size;
            }
            while ( Size < v266 );
            v116 = v251;
            v129 = (char *)v254;
            v128 = v255;
          }
          *(_QWORD *)&v129[v116] = (unsigned __int8)v247;
          if ( v128 )
          {
            v155 = (void *)ExAllocatePool2(256, v128, 542329939);
            v156 = v155;
            if ( v155 )
            {
              v157 = 0;
              memmove(v155, v129, v128);
              v11 = v244;
              Acl = 0;
              *((_QWORD *)v244 + 1) = v156;
              *v11 = v128;
            }
            else
            {
              v11 = v244;
              v157 = -1073741801;
              Acl = -1073741801;
            }
          }
          else
          {
            v11 = v244;
            v157 = -1073741762;
            Acl = -1073741762;
          }
          ExFreePoolWithTag(v129, 0);
          if ( v157 >= 0 )
          {
            if ( *v11 >= 0xFFFFFFFC
              || (v158 = *v11 + 8, v158 < *v11 + 4)
              || (v159 = v158 + v11[4], v159 < v158)
              || (v160 = v159 + 4, v159 + 4 < v159)
              || (v161 = v160 + v11[8], v161 < v160) )
            {
              v12 = v240;
              Acl = -1073741675;
              v9 = v241;
              v13 = 0;
              goto LABEL_7;
            }
            if ( v161 )
            {
              v162 = (_DWORD *)ExAllocatePool2(256, v161, 542329939);
              if ( v162 )
              {
                v163 = v162 + 1;
                *v162 = *v11;
                if ( v162 + 1 >= v162 )
                {
                  memmove(v162 + 1, *((const void **)v11 + 1), *v11);
                  v164 = (_DWORD *)((char *)v163 + *v11);
                  if ( v164 >= v163 )
                  {
                    v165 = v164 + 1;
                    *v164 = v11[4];
                    if ( v164 + 1 >= v164 )
                    {
                      memmove(v164 + 1, *((const void **)v11 + 3), v11[4]);
                      v166 = (_DWORD *)((char *)v165 + v11[4]);
                      if ( v166 >= v165 )
                      {
                        v167 = v166 + 1;
                        *v166 = v11[8];
                        if ( v166 + 1 >= v166 )
                        {
                          memmove(v166 + 1, *((const void **)v11 + 5), v11[8]);
                          if ( (_DWORD *)((char *)v167 + v11[8]) >= v167 )
                          {
                            v13 = 0;
                            v9 = v241;
                            Acl = 0;
                            *v271 = v162;
                            v12 = v240;
                            *v272 = v161;
                            goto LABEL_7;
                          }
                        }
                      }
                    }
                  }
                }
                Acl = -1073741675;
                ExFreePoolWithTag(v162, 0);
              }
              else
              {
                Acl = -1073741801;
              }
            }
            else
            {
              Acl = -1073741762;
            }
            v12 = v240;
            v9 = v241;
            v13 = 0;
            goto LABEL_7;
          }
          v9 = v241;
LABEL_195:
          v12 = v240;
          v13 = 0;
          goto LABEL_7;
        }
        v9 = v241;
      }
      Acl = -1073741823;
      goto LABEL_195;
    }
    Acl = -1073741811;
    goto LABEL_195;
  }
LABEL_260:
  v12 = 0;
  v13 = 0;
LABEL_7:
  Src_8[0] = 0;
  if ( Src_8[1] )
  {
    ExFreePoolWithTag(Src_8[1], 0);
    Src_8[1] = 0;
  }
  v242[0] = 0;
  if ( v242[1] )
  {
    ExFreePoolWithTag(v242[1], 0);
    v242[1] = 0;
  }
  if ( v262 )
    ExFreePoolWithTag(v262, 0);
  if ( v9 )
  {
    v14 = (void *)v9[1];
    if ( v14 )
    {
      ExFreePoolWithTag(v14, 0);
      v9[1] = 0;
    }
    v15 = (void *)v9[3];
    if ( v15 )
    {
      ExFreePoolWithTag(v15, 0);
      v9[3] = 0;
    }
    v16 = (void *)v9[5];
    if ( v16 )
    {
      ExFreePoolWithTag(v16, 0);
      v9[5] = 0;
    }
    ExFreePoolWithTag(v9, 0);
  }
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  if ( v11 )
  {
    v17 = (void *)*((_QWORD *)v11 + 1);
    if ( v17 )
    {
      ExFreePoolWithTag(v17, 0);
      *((_QWORD *)v11 + 1) = 0;
    }
    v18 = (void *)*((_QWORD *)v11 + 3);
    if ( v18 )
    {
      ExFreePoolWithTag(v18, 0);
      *((_QWORD *)v11 + 3) = 0;
    }
    v19 = (void *)*((_QWORD *)v11 + 5);
    if ( v19 )
    {
      ExFreePoolWithTag(v19, 0);
      *((_QWORD *)v11 + 5) = 0;
    }
    ExFreePoolWithTag(v11, 0);
  }
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x14098ef10  mov     r11, rsp
0x14098ef13  push    rbp
0x14098ef14  push    rbx
0x14098ef15  push    rdi
0x14098ef16  lea     rbp, [r11-138h]
0x14098ef1d  sub     rsp, 220h
0x14098ef24  mov     rax, cs:__security_cookie
0x14098ef2b  xor     rax, rsp
0x14098ef2e  mov     [rbp+130h+var_38], rax
0x14098ef35  mov     rax, [rbp+130h+arg_20]
0x14098ef3c  xorps   xmm0, xmm0
0x14098ef3f  mov     [r11+10h], rsi
0x14098ef43  xorps   xmm1, xmm1
0x14098ef46  mov     [r11-20h], r12
0x14098ef4a  mov     [r11-28h], r13
0x14098ef4e  mov     [rbp+130h+var_F0], rax
0x14098ef52  xor     eax, eax
0x14098ef54  mov     [r11-30h], r14
0x14098ef58  mov     [r11-38h], r15
0x14098ef5c  mov     [rbp+130h+var_F8], r9
0x14098ef60  mov     [rbp+130h+var_198], r8d
0x14098ef64  mov     [rsp+230h+var_1D0], rax
0x14098ef69  mov     [rbp+130h+var_140], rax
0x14098ef6d  mov     [rsp+230h+var_1E0], rax
0x14098ef72  mov     [rbp+130h+var_1A8], rax
0x14098ef76  mov     [rsp+230h+var_1D8], rax
0x14098ef7b  movups  xmmword ptr [rsp+230h+Src+8], xmm0
0x14098ef80  movups  xmmword ptr [rsp+230h+var_1D0+8], xmm1
0x14098ef85  cmp     edx, 4
0x14098ef88  jb      loc_14099149E
0x14098ef8e  mov     esi, [rcx]
0x14098ef90  lea     r15, [rcx+4]
0x14098ef94  cmp     r15, rcx
0x14098ef97  jb      short loc_14098EFB5
0x14098ef99  lea     eax, [rdx-4]
0x14098ef9c  cmp     eax, esi
0x14098ef9e  jb      loc_1409914A8
0x14098efa4  lea     r8, [rsi+r15]
0x14098efa8  mov     [rbp+130h+Size], rsi
0x14098efac  cmp     r8, r15
0x14098efaf  jnb     loc_14098F101
0x14098efb5  mov     esi, 0C0000095h
0x14098efba  mov     r12, [rsp+230h+var_1D0]
0x14098efbf  mov     edi, esi
0x14098efc1  mov     r15, r12
0x14098efc4  mov     rbx, r12
0x14098efc7  mov     r14, r12
0x14098efca  mov     rcx, [rbp+130h+P]; P
0x14098efce  xor     r13d, r13d
0x14098efd1  mov     rsi, [rsp+230h+arg_8]
0x14098efd9  mov     [rsp+230h+Src+8], r13
0x14098efde  test    rcx, rcx
0x14098efe1  jz      short loc_14098EFEE
0x14098efe3  xor     edx, edx; Tag
0x14098efe5  call    ExFreePoolWithTag
0x14098efea  mov     [rbp+130h+P], r13
0x14098efee  mov     r8, [rsp+230h+Src]
0x14098eff3  mov     [rsp+230h+var_1D0+8], r13
0x14098eff8  test    r8, r8
0x14098effb  jz      short loc_14098F00C
0x14098effd  xor     edx, edx; Tag
0x14098efff  mov     rcx, r8; P
0x14098f002  call    ExFreePoolWithTag
0x14098f007  mov     [rsp+230h+Src], r13
0x14098f00c  mov     rax, [rbp+130h+var_140]
0x14098f010  test    rax, rax
0x14098f013  jz      short loc_14098F01F
0x14098f015  xor     edx, edx; Tag
0x14098f017  mov     rcx, rax; P
0x14098f01a  call    ExFreePoolWithTag
0x14098f01f  test    r12, r12
0x14098f022  jz      short loc_14098F070
0x14098f024  mov     rcx, [r12+8]; P
0x14098f029  test    rcx, rcx
0x14098f02c  jz      short loc_14098F03A
0x14098f02e  xor     edx, edx; Tag
0x14098f030  call    ExFreePoolWithTag
0x14098f035  mov     [r12+8], r13
0x14098f03a  mov     rcx, [r12+18h]; P
0x14098f03f  test    rcx, rcx
0x14098f042  jz      short loc_14098F050
0x14098f044  xor     edx, edx; Tag
0x14098f046  call    ExFreePoolWithTag
0x14098f04b  mov     [r12+18h], r13
0x14098f050  mov     rcx, [r12+28h]; P
0x14098f055  test    rcx, rcx
0x14098f058  jz      short loc_14098F066
0x14098f05a  xor     edx, edx; Tag
0x14098f05c  call    ExFreePoolWithTag
0x14098f061  mov     [r12+28h], r13
0x14098f066  xor     edx, edx; Tag
0x14098f068  mov     rcx, r12; P
0x14098f06b  call    ExFreePoolWithTag
0x14098f070  mov     r12, [rsp+218h]
0x14098f078  test    r14, r14
0x14098f07b  jz      short loc_14098F087
0x14098f07d  xor     edx, edx; Tag
0x14098f07f  mov     rcx, r14; P
0x14098f082  call    ExFreePoolWithTag
0x14098f087  mov     r14, [rsp+230h+var_28]
0x14098f08f  test    r15, r15
0x14098f092  jz      short loc_14098F0DA
0x14098f094  mov     rcx, [r15+8]; P
0x14098f098  test    rcx, rcx
0x14098f09b  jz      short loc_14098F0A8
0x14098f09d  xor     edx, edx; Tag
0x14098f09f  call    ExFreePoolWithTag
0x14098f0a4  mov     [r15+8], r13
0x14098f0a8  mov     rcx, [r15+18h]; P
0x14098f0ac  test    rcx, rcx
0x14098f0af  jz      short loc_14098F0BC
0x14098f0b1  xor     edx, edx; Tag
0x14098f0b3  call    ExFreePoolWithTag
0x14098f0b8  mov     [r15+18h], r13
0x14098f0bc  mov     rcx, [r15+28h]; P
0x14098f0c0  test    rcx, rcx
0x14098f0c3  jz      short loc_14098F0D0
0x14098f0c5  xor     edx, edx; Tag
0x14098f0c7  call    ExFreePoolWithTag
0x14098f0cc  mov     [r15+28h], r13
0x14098f0d0  xor     edx, edx; Tag
0x14098f0d2  mov     rcx, r15; P
0x14098f0d5  call    ExFreePoolWithTag
0x14098f0da  mov     r15, [rsp+230h+var_30]
0x14098f0e2  mov     r13, [rsp+230h+var_20]
0x14098f0ea  test    rbx, rbx
0x14098f0ed  jz      short loc_14098F0F9
0x14098f0ef  xor     edx, edx; Tag
0x14098f0f1  mov     rcx, rbx; P
0x14098f0f4  call    ExFreePoolWithTag
0x14098f0f9  mov     eax, edi
0x14098f0fb  jmp     loc_140991753
0x14098f101  lea     ecx, [rsi+4]
0x14098f104  cmp     ecx, 4
0x14098f107  jb      loc_14098EFB5
0x14098f10d  mov     eax, edx
0x14098f10f  sub     eax, ecx
0x14098f111  cmp     eax, 4
0x14098f114  jb      loc_1409914B2
0x14098f11a  mov     r14d, [r8]
0x14098f11d  lea     r12, [r8+4]
0x14098f121  cmp     r12, r8
0x14098f124  jb      loc_14098EFB5
0x14098f12a  lea     r8d, [rcx+4]
0x14098f12e  cmp     r8d, ecx
0x14098f131  jb      loc_14098EFB5
0x14098f137  mov     eax, edx
0x14098f139  sub     eax, r8d
0x14098f13c  cmp     eax, r14d
0x14098f13f  jb      loc_1409914BC
0x14098f145  lea     rdi, [r14+r12]
0x14098f149  cmp     rdi, r12
0x14098f14c  jb      loc_14098EFB5
0x14098f152  lea     ecx, [r8+r14]
0x14098f156  cmp     ecx, r8d
0x14098f159  jb      loc_14098EFB5
0x14098f15f  mov     eax, edx
0x14098f161  sub     eax, ecx
0x14098f163  cmp     eax, 4
0x14098f166  jb      loc_1409914C6
0x14098f16c  lea     r13, [rdi+4]
0x14098f170  cmp     r13, rdi
0x14098f173  jb      loc_14098EFB5
0x14098f179  lea     r8d, [rcx+4]
0x14098f17d  cmp     r8d, ecx
0x14098f180  jb      loc_14098EFB5
0x14098f186  mov     edi, [rdi]
0x14098f188  mov     eax, edx
0x14098f18a  sub     eax, r8d
0x14098f18d  cmp     eax, edi
0x14098f18f  jb      loc_1409914D0
0x14098f195  lea     ecx, [r8+rdi]
0x14098f199  cmp     ecx, r8d
0x14098f19c  jb      loc_14098EFB5
0x14098f1a2  cmp     edx, ecx
0x14098f1a4  jnz     loc_1409914DA
0x14098f1aa  lea     ecx, [rdi+r14]
0x14098f1ae  mov     eax, edx
0x14098f1b0  add     ecx, esi
0x14098f1b2  add     rcx, 0Ch
0x14098f1b6  cmp     rcx, rax
0x14098f1b9  jnz     loc_1409914E4
0x14098f1bf  mov     edx, 30h ; '0'
0x14098f1c4  mov     ecx, 100h
0x14098f1c9  mov     r8d, 20534C53h
0x14098f1cf  call    ExAllocatePool2
0x14098f1d4  mov     rbx, rax
0x14098f1d7  test    rax, rax
0x14098f1da  jz      loc_1409914EE
0x14098f1e0  xorps   xmm0, xmm0
0x14098f1e3  movups  xmmword ptr [rax], xmm0
0x14098f1e6  movups  xmmword ptr [rax+10h], xmm0
0x14098f1ea  movups  xmmword ptr [rax+20h], xmm0
0x14098f1ee  mov     eax, 0C000003Eh
0x14098f1f3  test    r15, r15
0x14098f1f6  jnz     loc_14098F337
0x14098f1fc  mov     esi, r15d
0x14098f1ff  test    r12, r12
0x14098f202  jz      loc_14098F37F
0x14098f208  mov     [rbx+10h], r14d
0x14098f20c  test    r14d, r14d
0x14098f20f  jz      loc_14099150F
0x14098f215  mov     r8d, 20534C53h
0x14098f21b  mov     rdx, r14
0x14098f21e  mov     ecx, 100h
0x14098f223  call    ExAllocatePool2
0x14098f228  test    rax, rax
0x14098f22b  jz      loc_140991505
0x14098f231  mov     r8, r14; Size
0x14098f234  mov     [rbx+18h], rax
0x14098f238  mov     rdx, r12; Src
0x14098f23b  mov     rcx, rax; void *
0x14098f23e  call    memmove
0x14098f243  test    r13, r13
0x14098f246  jz      loc_14098F38C
0x14098f24c  mov     [rbx+20h], edi
0x14098f24f  test    edi, edi
0x14098f251  jz      loc_140991516
0x14098f257  mov     r8d, 20534C53h
0x14098f25d  mov     rdx, rdi
0x14098f260  mov     ecx, 100h
0x14098f265  call    ExAllocatePool2
0x14098f26a  test    rax, rax
0x14098f26d  jz      loc_140991505
0x14098f273  mov     r8, rdi; Size
0x14098f276  mov     [rbx+28h], rax
0x14098f27a  mov     rdx, r13; Src
0x14098f27d  mov     rcx, rax; void *
0x14098f280  call    memmove
0x14098f285  mov     r14, rbx
0x14098f288  mov     [rbp+130h+var_180], rbx
0x14098f28c  jmp     short loc_14098F2DB
0x14098f28e  mov     rcx, [rbx+8]; P
0x14098f292  mov     r14, r15
0x14098f295  mov     [rbp+130h+var_180], r15
0x14098f299  test    rcx, rcx
0x14098f29c  jz      short loc_14098F2A9
0x14098f29e  xor     edx, edx; Tag
0x14098f2a0  call    ExFreePoolWithTag
0x14098f2a5  mov     [rbx+8], r15
0x14098f2a9  mov     rcx, [rbx+18h]; P
0x14098f2ad  test    rcx, rcx
0x14098f2b0  jz      short loc_14098F2BD
0x14098f2b2  xor     edx, edx; Tag
0x14098f2b4  call    ExFreePoolWithTag
0x14098f2b9  mov     [rbx+18h], r15
0x14098f2bd  mov     rcx, [rbx+28h]; P
0x14098f2c1  test    rcx, rcx
0x14098f2c4  jz      short loc_14098F2D1
0x14098f2c6  xor     edx, edx; Tag
0x14098f2c8  call    ExFreePoolWithTag
0x14098f2cd  mov     [rbx+28h], r15
0x14098f2d1  xor     edx, edx; Tag
0x14098f2d3  mov     rcx, rbx; P
0x14098f2d6  call    ExFreePoolWithTag
0x14098f2db  test    esi, esi
0x14098f2dd  jns     loc_14098F399
0x14098f2e3  test    r14, r14
0x14098f2e6  jz      loc_14098EFBA
0x14098f2ec  mov     rcx, [r14+8]; P
0x14098f2f0  test    rcx, rcx
0x14098f2f3  jz      short loc_14098F300
0x14098f2f5  xor     edx, edx; Tag
0x14098f2f7  call    ExFreePoolWithTag
0x14098f2fc  mov     [r14+8], r15
0x14098f300  mov     rcx, [r14+18h]; P
0x14098f304  test    rcx, rcx
0x14098f307  jz      short loc_14098F314
0x14098f309  xor     edx, edx; Tag
0x14098f30b  call    ExFreePoolWithTag
0x14098f310  mov     [r14+18h], r15
0x14098f314  mov     rcx, [r14+28h]; P
0x14098f318  test    rcx, rcx
0x14098f31b  jz      short loc_14098F328
0x14098f31d  xor     edx, edx; Tag
0x14098f31f  call    ExFreePoolWithTag
0x14098f324  mov     [r14+28h], r15
0x14098f328  xor     edx, edx; Tag
0x14098f32a  mov     rcx, r14; P
0x14098f32d  call    ExFreePoolWithTag
0x14098f332  jmp     loc_14098EFBA
0x14098f337  mov     [rbx], esi
0x14098f339  test    esi, esi
0x14098f33b  jz      loc_1409914F8
0x14098f341  mov     r8d, 20534C53h
0x14098f347  mov     rdx, rsi
0x14098f34a  mov     ecx, 100h
0x14098f34f  call    ExAllocatePool2
0x14098f354  test    rax, rax
0x14098f357  jz      loc_140991502
0x14098f35d  mov     r8, [rbp+130h+Size]; Size
0x14098f361  mov     rdx, r15; Src
0x14098f364  mov     rcx, rax; void *
0x14098f367  mov     [rbx+8], rax
0x14098f36b  xor     esi, esi
0x14098f36d  call    memmove
0x14098f372  mov     eax, 0C000003Eh
0x14098f377  xor     r15d, r15d
0x14098f37a  jmp     loc_14098F1FF
0x14098f37f  mov     [rbx+10h], r15d
  ... truncated ...
```
