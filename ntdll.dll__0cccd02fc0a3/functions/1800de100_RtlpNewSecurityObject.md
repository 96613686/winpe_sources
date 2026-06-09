# RtlpNewSecurityObject

- ea: `0x1800de100`
- end: `0x1800df80e`
- name: `RtlpNewSecurityObject`
- size: `5902`
- prototype: ``
- caller_count: `6`
- callee_count: `24`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800ddfe0`
- `0x1800de030`
- `0x1800de090`
- `0x1800de100`
- `0x1801392e0`
- `0x180139380`

## callees

- `0x180015af0`
- `0x180015b30`
- `0x18001861c`
- `0x18001b984`
- `0x1800aeaa0`
- `0x1800b0c30`
- `0x1800b2970`
- `0x1800b2b40`
- `0x1800b2e90`
- `0x1800b3670`
- `0x1800b37fc`
- `0x1800b38d8`
- `0x1800b3b70`
- `0x1800c7fe0`
- `0x1800d3a90`
- `0x1800de100`
- `0x18015e2d0`
- `0x18015e4b0`
- `0x18015e6f0`
- `0x18015eb10`
- `0x180160b00`
- `0x180162000`
- `0x180163a80`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall RtlpNewSecurityObject(
        __int64 a1,
        __int128 *a2,
        __int64 *a3,
        __int64 a4,
        int a5,
        unsigned __int8 a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9)
{
  char *v11; // r13
  void *v12; // rdi
  __int64 v13; // rcx
  __int64 result; // rax
  int v15; // eax
  __int16 v16; // dx
  _QWORD *v17; // rcx
  __int64 v18; // r14
  void *v19; // r9
  _QWORD *v20; // r10
  __int64 v21; // rsi
  unsigned int v22; // ebx
  __int16 v23; // r8
  __int64 v24; // rax
  char *v25; // rax
  __int16 v26; // cx
  __int64 v27; // rax
  char *v28; // rdx
  int valid; // ebx
  __int64 v30; // rax
  void *v31; // rax
  _QWORD *v32; // rax
  __int64 v33; // rax
  void *v34; // rdx
  unsigned int v35; // r13d
  char v36; // si
  __int16 v37; // cx
  int v38; // r9d
  unsigned int v39; // ebx
  int v40; // r11d
  int v41; // ebx
  int v42; // r10d
  __int64 v43; // rdx
  int v44; // eax
  __int16 v45; // ax
  int v46; // eax
  __int64 v47; // rcx
  int v48; // eax
  __int16 v49; // r11
  int v50; // ecx
  __int64 v51; // rax
  unsigned int v52; // edx
  int v53; // r9d
  int v54; // r8d
  int v55; // r10d
  __int64 v56; // rdx
  int v57; // eax
  __int16 v58; // ax
  int v59; // eax
  __int64 v60; // rcx
  void *v61; // rdi
  int v62; // eax
  unsigned __int64 v63; // r8
  __int64 v64; // rax
  __int16 v65; // r11
  unsigned int v66; // r10d
  __int64 v67; // rax
  char *v68; // rdx
  __int16 v69; // cx
  __int64 v70; // rax
  char *v71; // rcx
  unsigned int v72; // r10d
  __int64 v73; // rax
  char *v74; // rdx
  bool v75; // zf
  unsigned int v76; // ecx
  unsigned int v77; // eax
  char *v78; // rdx
  unsigned int v79; // ecx
  char *v80; // rcx
  __int64 v81; // rax
  char *v82; // r13
  char v83; // r15
  int v84; // edx
  int v85; // esi
  __int16 v86; // ax
  __int64 v87; // rax
  char *v88; // rdx
  char *v89; // rbx
  unsigned int v90; // ecx
  char *v91; // rax
  char v92; // di
  char *v93; // rdx
  unsigned int v94; // r8d
  __int64 v95; // r8
  __int64 *v96; // r14
  unsigned int v97; // r8d
  __int16 v98; // ax
  int v99; // eax
  __int64 v100; // rcx
  int v101; // eax
  __int16 v102; // si
  __int64 *v103; // rdi
  int v104; // eax
  int v105; // r15d
  __int64 *v106; // r8
  void *v107; // rdi
  char *v108; // rax
  bool v109; // r14
  char *v110; // r8
  char *v111; // rcx
  unsigned int v112; // edx
  unsigned int v113; // r8d
  __int16 v114; // r8
  __int64 v115; // rdx
  int v116; // eax
  __int64 v117; // r13
  __int16 v118; // ax
  int v119; // eax
  __int64 v120; // rcx
  int v121; // eax
  char *v122; // r12
  __int64 v123; // rcx
  __int64 v124; // rdx
  __int16 v125; // cx
  __int64 v126; // rax
  __int64 v127; // r13
  __int64 v128; // rdx
  bool v129; // al
  unsigned __int8 *v130; // rdi
  void *v131; // rbx
  unsigned __int16 *v132; // rdx
  void *v133; // r15
  unsigned int v134; // r13d
  unsigned int v135; // r12d
  int v136; // r14d
  unsigned int v137; // edi
  int v138; // r15d
  unsigned int v139; // esi
  __int64 Heap_0; // rax
  __int64 v141; // r10
  __int16 v142; // cx
  unsigned __int16 *v143; // rbx
  __int64 v144; // r14
  __int64 v145; // r8
  __int64 v146; // rcx
  unsigned __int16 *v147; // rdi
  __int64 v148; // r8
  __int64 v149; // rcx
  char *v150; // rbx
  __int64 v151; // r14
  void *v152; // r15
  char v153; // [rsp+90h] [rbp-80h] BYREF
  char v154; // [rsp+91h] [rbp-7Fh]
  char v155; // [rsp+92h] [rbp-7Eh]
  void *Src; // [rsp+98h] [rbp-78h] BYREF
  void *v157; // [rsp+A0h] [rbp-70h]
  __int64 v158; // [rsp+A8h] [rbp-68h]
  char v159[8]; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v160; // [rsp+B8h] [rbp-58h] BYREF
  void *v161; // [rsp+C0h] [rbp-50h]
  char v162; // [rsp+C8h] [rbp-48h]
  char v163; // [rsp+C9h] [rbp-47h] BYREF
  char v164; // [rsp+CAh] [rbp-46h]
  char v165; // [rsp+CBh] [rbp-45h]
  char v166; // [rsp+CCh] [rbp-44h] BYREF
  char v167; // [rsp+CDh] [rbp-43h]
  char v168; // [rsp+CEh] [rbp-42h]
  int v169; // [rsp+D0h] [rbp-40h]
  __int64 v170; // [rsp+D8h] [rbp-38h] BYREF
  __int16 v171; // [rsp+E0h] [rbp-30h]
  int v172; // [rsp+E4h] [rbp-2Ch] BYREF
  char v173; // [rsp+E8h] [rbp-28h] BYREF
  char v174; // [rsp+E9h] [rbp-27h] BYREF
  bool v175; // [rsp+EAh] [rbp-26h]
  void *v176; // [rsp+F0h] [rbp-20h] BYREF
  int v177; // [rsp+F8h] [rbp-18h] BYREF
  __int16 v178; // [rsp+FCh] [rbp-14h]
  void *v179; // [rsp+100h] [rbp-10h] BYREF
  __int64 v180; // [rsp+108h] [rbp-8h]
  _QWORD *v181; // [rsp+110h] [rbp+0h] BYREF
  __int64 v182; // [rsp+118h] [rbp+8h]
  void *Buf1; // [rsp+120h] [rbp+10h] BYREF
  int v184; // [rsp+128h] [rbp+18h] BYREF
  int v185; // [rsp+12Ch] [rbp+1Ch] BYREF
  void *ProcessHeap; // [rsp+130h] [rbp+20h]
  _QWORD *v187; // [rsp+138h] [rbp+28h] BYREF
  _QWORD *v188; // [rsp+140h] [rbp+30h] BYREF
  HANDLE Handle; // [rsp+148h] [rbp+38h] BYREF
  int v190; // [rsp+150h] [rbp+40h] BYREF
  __int64 v191; // [rsp+158h] [rbp+48h]
  __int64 v192; // [rsp+160h] [rbp+50h] BYREF
  char *v193; // [rsp+168h] [rbp+58h] BYREF
  int v194; // [rsp+170h] [rbp+60h]
  unsigned __int16 *v195; // [rsp+178h] [rbp+68h] BYREF
  __int64 *v196; // [rsp+180h] [rbp+70h] BYREF
  __int64 v197; // [rsp+188h] [rbp+78h]
  _QWORD *v198; // [rsp+190h] [rbp+80h]
  void *v199; // [rsp+198h] [rbp+88h]
  void *v200; // [rsp+1A0h] [rbp+90h]
  void *v201; // [rsp+1A8h] [rbp+98h]
  _QWORD *v202; // [rsp+1B0h] [rbp+A0h]
  __int64 v203; // [rsp+1B8h] [rbp+A8h]
  _QWORD *v204; // [rsp+1C0h] [rbp+B0h]
  __int64 *v205; // [rsp+1C8h] [rbp+B8h]
  __int128 v206; // [rsp+1D0h] [rbp+C0h] BYREF
  __int128 v207; // [rsp+1E0h] [rbp+D0h]
  __int64 v208; // [rsp+1F0h] [rbp+E0h]
  __int64 v209; // [rsp+1F8h] [rbp+E8h] BYREF
  int v210; // [rsp+200h] [rbp+F0h]
  __int128 v211; // [rsp+208h] [rbp+F8h] BYREF
  int v212; // [rsp+218h] [rbp+108h]
  __int128 v213; // [rsp+220h] [rbp+110h] BYREF
  __int128 v214; // [rsp+230h] [rbp+120h]
  __int128 v215; // [rsp+240h] [rbp+130h]
  __int64 v216; // [rsp+250h] [rbp+140h]
  __int64 v217; // [rsp+260h] [rbp+150h] BYREF
  char v218; // [rsp+268h] [rbp+158h] BYREF

  v182 = a9;
  v184 = 0;
  v208 = 0;
  v153 = 0;
  v173 = 0;
  v11 = 0;
  v174 = 0;
  v12 = 0;
  v163 = 0;
  v166 = 0;
  v159[0] = 0;
  v212 = 0;
  v206 = 0;
  v193 = 0;
  v207 = 0;
  v192 = 0;
  v211 = 0;
  v197 = a1;
  v13 = a8;
  v191 = a4;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  v205 = a3;
  v180 = a8;
  Src = 0;
  v158 = 0;
  v170 = 0;
  v157 = 0;
  Handle = 0;
  v161 = 0;
  v195 = 0;
  v172 = 0;
  v177 = 0;
  v196 = 0;
  v164 = 1;
  v190 = 0;
  LOBYTE(v185) = 1;
  v198 = 0;
  v187 = 0;
  v201 = 0;
  Buf1 = 0;
  v202 = 0;
  v181 = 0;
  v199 = 0;
  v179 = 0;
  v200 = 0;
  v176 = 0;
  v203 = 0;
  v160 = 0;
  v204 = 0;
  v188 = 0;
  if ( a8 )
  {
    v185 = 0;
    v216 = 0;
    v213 = 0;
    v214 = 0;
    v215 = 0;
    result = NtQueryInformationToken(a8, 10, &v213, 56, &v185);
    if ( (int)result < 0 )
      return result;
    v185 = DWORD2(v214);
    if ( DWORD2(v214) == 2 && SHIDWORD(v214) < 1 )
      return 3221225637LL;
    v13 = v180;
  }
  if ( a2 )
  {
    v165 = 1;
  }
  else
  {
    v165 = 0;
    a2 = &v206;
    v206 = 0;
    LOBYTE(v206) = 1;
    v207 = 0;
    v208 = 0;
  }
  v15 = *((unsigned __int16 *)a2 + 1);
  v16 = *((_WORD *)a2 + 1) & 0x80;
  v171 = v16;
  LOBYTE(v15) = (v15 & 0x40) != 0;
  v175 = v16 != 0;
  v194 = v15;
  if ( !v13 && !v16 )
  {
    v17 = 0;
    Buf1 = 0;
    v18 = 0;
    v181 = 0;
    v209 = 0;
    v19 = 0;
LABEL_13:
    v187 = 0;
    v20 = 0;
    goto LABEL_14;
  }
  result = RtlpGetDefaultsSubjectContext(
             v13,
             v16 != 0,
             (unsigned int)&v187,
             (unsigned int)&Buf1,
             (__int64)&v181,
             (__int64)&v160,
             (__int64)&v179,
             (__int64)&v176,
             (__int64)&v188);
  if ( (int)result < 0 )
    return result;
  v198 = v187;
  v17 = (_QWORD *)*v187;
  v201 = Buf1;
  v19 = *(void **)Buf1;
  v202 = v181;
  v209 = *v181;
  v199 = v179;
  Buf1 = *(void **)v179;
  v200 = v176;
  v18 = *(_QWORD *)v176;
  v203 = v160;
  if ( v160 )
    v181 = *(_QWORD **)v160;
  else
    v181 = 0;
  v204 = v188;
  if ( !v188 )
    goto LABEL_13;
  v20 = (_QWORD *)*v188;
  v187 = (_QWORD *)*v188;
LABEL_14:
  v21 = 0;
  v154 = 0;
  v168 = 0;
  v167 = 0;
  v155 = 0;
  v160 = 0;
  v22 = *((unsigned __int16 *)a2 + 1);
  v23 = v22 & 0x8000;
  if ( (v22 & 0x8000) != 0 )
  {
    v24 = *((unsigned int *)a2 + 1);
    if ( !(_DWORD)v24 )
      goto LABEL_29;
    v25 = (char *)a2 + v24;
  }
  else
  {
    v25 = (char *)*((_QWORD *)a2 + 1);
  }
  v176 = v25;
  if ( v25 )
  {
LABEL_25:
    v26 = v171;
    v162 = 1;
    goto LABEL_26;
  }
LABEL_29:
  if ( (a7 & 0x20) != 0 )
  {
    if ( !a1 )
    {
      valid = -1073741734;
LABEL_400:
      v133 = v161;
      goto LABEL_401;
    }
    if ( *(__int16 *)(a1 + 2) >= 0 )
    {
      v31 = *(void **)(a1 + 8);
    }
    else
    {
      v30 = *(unsigned int *)(a1 + 4);
      if ( !(_DWORD)v30 )
      {
LABEL_37:
        valid = -1073741734;
        goto LABEL_400;
      }
      v31 = (void *)(a1 + v30);
    }
    v176 = v31;
    if ( v31 )
      goto LABEL_25;
    goto LABEL_37;
  }
  v32 = v17;
  v162 = 0;
  v26 = v171;
  if ( v171 )
    v32 = v181;
  v176 = v32;
  if ( !v32 )
  {
    valid = -1073741700;
    goto LABEL_400;
  }
LABEL_26:
  if ( (v22 & 0x8000) == 0 )
  {
    v28 = (char *)*((_QWORD *)a2 + 2);
LABEL_43:
    v179 = v28;
    if ( v28 )
      goto LABEL_55;
    goto LABEL_44;
  }
  v27 = *((unsigned int *)a2 + 2);
  if ( (_DWORD)v27 )
  {
    v28 = (char *)a2 + v27;
    goto LABEL_43;
  }
LABEL_44:
  if ( (a7 & 0x40) != 0 )
  {
    if ( !a1 )
    {
      valid = -1073741733;
      goto LABEL_400;
    }
    if ( *(__int16 *)(a1 + 2) >= 0 )
    {
      v34 = *(void **)(a1 + 16);
    }
    else
    {
      v33 = *(unsigned int *)(a1 + 8);
      if ( !(_DWORD)v33 )
      {
LABEL_54:
        valid = -1073741733;
        goto LABEL_400;
      }
      v34 = (void *)(a1 + v33);
    }
  }
  else
  {
    v34 = v19;
    if ( v26 )
      v34 = v20;
  }
  v179 = v34;
  if ( !v34 )
    goto LABEL_54;
LABEL_55:
  v35 = a7 >> 2;
  LOBYTE(v35) = (a7 & 4) != 0;
  LODWORD(v188) = v35;
  v36 = (a7 & 2) != 0;
  v37 = v22 & 0x10;
  v38 = (v22 >> 2) & 8;
  v39 = v22 >> 1;
  v40 = v39 & 0x400;
  v41 = v39 & 0x1000;
  v42 = v37 != 0 ? 4 : 0;
  if ( v37 )
  {
    if ( v23 )
    {
      v44 = *((_DWORD *)a2 + 3);
      if ( v44 )
        LODWORD(v43) = (_DWORD)a2 + v44;
      else
        LODWORD(v43) = 0;
    }
    else
    {
      v43 = *((_QWORD *)a2 + 3);
    }
  }
  else
  {
    LODWORD(v43) = 0;
  }
  if ( a1 )
  {
    v45 = *(_WORD *)(a1 + 2);
    if ( (v45 & 0x10) != 0 )
    {
      if ( v45 >= 0 )
      {
        v47 = *(_QWORD *)(a1 + 24);
        goto LABEL_69;
      }
      v46 = *(_DWORD *)(a1 + 12);
      if ( v46 )
      {
        LODWORD(v47) = a1 + v46;
        goto LABEL_69;
      }
    }
  }
  LODWORD(v47) = 0;
LABEL_69:
  v48 = RtlpInheritAcl(
          v47,
          v43,
          v38 | v40 | v41 | (unsigned int)v42,
          a6,
          v36,
          v35,
          (__int64)v176,
          (__int64)v179,
          (__int64)v181,
          (__int64)v187,
          v182,
          2,
          v191,
          a5,
          (__int64)&Src,
          (__int64)&v153,
          (__int64)&v172);
  valid = v48;
  if ( v48 >= 0 )
  {
    v154 = 1;
    v169 = 2 * (v172 & 0x1400 | (2 * (v172 & 8 | 0x2004)));
LABEL_84:
    v11 = (char *)Src;
    goto LABEL_85;
  }
  if ( v48 != -2147483637 )
  {
LABEL_397:
    v11 = (char *)Src;
    goto LABEL_398;
  }
  v49 = *((_WORD *)a2 + 1);
  v50 = 34816;
  if ( (a7 & 2) == 0 )
    v50 = 0x8000;
  if ( (v49 & 0x30) != 0x30 )
  {
    v169 = v50;
    goto LABEL_84;
  }
  if ( (v49 & 0x10) != 0 )
  {
    if ( v49 >= 0 )
    {
      v11 = (char *)*((_QWORD *)a2 + 3);
    }
    else
    {
      v51 = *((unsigned int *)a2 + 3);
      if ( (_DWORD)v51 )
        v11 = (char *)a2 + v51;
      else
        v11 = 0;
    }
  }
  else
  {
    v11 = 0;
  }
  v153 = 1;
  v169 = v50 | v49 & 0x2000 | 0x10;
LABEL_85:
  v52 = *((unsigned __int16 *)a2 + 1);
  Src = v11;
  v53 = (v52 >> 2) & 8;
  v54 = (v52 >> 1) & 0x400;
  v55 = (v52 & 0x10) != 0 ? 4 : 0;
  if ( (v52 & 0x10) != 0 )
  {
    if ( (v52 & 0x8000u) == 0 )
    {
      v56 = *((_QWORD *)a2 + 3);
    }
    else
    {
      v57 = *((_DWORD *)a2 + 3);
      if ( v57 )
        LODWORD(v56) = (_DWORD)a2 + v57;
      else
        LODWORD(v56) = 0;
    }
  }
  else
  {
    LODWORD(v56) = 0;
  }
  if ( a1 )
  {
    v58 = *(_WORD *)(a1 + 2);
    if ( (v58 & 0x10) != 0 )
    {
      if ( v58 >= 0 )
      {
        v60 = *(_QWORD *)(a1 + 24);
        goto LABEL_99;
      }
      v59 = *(_DWORD *)(a1 + 12);
      if ( v59 )
      {
        LODWORD(v60) = a1 + v59;
        goto LABEL_99;
      }
    }
  }
  LODWORD(v60) = 0;
LABEL_99:
  v61 = v179;
  v62 = RtlpInheritAcl(
          v60,
          v56,
          v55 | v53 | (unsigned int)v54,
          a6,
          v36,
          (char)v188,
          (__int64)v176,
          (__int64)v179,
          (__int64)v181,
          (__int64)v187,
          v182,
          2,
          v191,
          a5,
          (__int64)&v170,
          (__int64)&v173,
          (__int64)&v177);
  valid = v62;
  if ( v62 >= 0 )
  {
    v168 = 1;
    goto LABEL_101;
  }
  if ( v62 == -2147483637 )
  {
    v69 = *((_WORD *)a2 + 1);
    if ( (v69 & 0x30) == 0x30 )
    {
      if ( (v69 & 0x10) == 0 )
      {
        v158 = 0;
LABEL_103:
        v65 = *((_WORD *)a2 + 1);
        v66 = 0;
        if ( (v65 & 0x10) != 0 )
        {
          while ( 1 )
          {
            if ( v65 >= 0 )
            {
              v68 = (char *)*((_QWORD *)a2 + 3);
            }
            else
            {
              v67 = *((unsigned int *)a2 + 3);
              if ( !(_DWORD)v67 )
                break;
              v68 = (char *)a2 + v67;
            }
            if ( !v68 )
              break;
            v71 = v68 + 8;
            v63 = 0;
            if ( !*((_WORD *)v68 + 2) )
              break;
            while ( (unsigned int)v63 < v66 || *v71 != 20 )
            {
              v63 = (unsigned int)(v63 + 1);
              v71 += *((unsigned __int16 *)v71 + 1);
              if ( (unsigned int)v63 >= *((unsigned __int16 *)v68 + 2) )
                goto LABEL_122;
            }
            v74 = v71 + 8;
            if ( !v71 )
              v74 = 0;
            if ( v74 )
            {
              if ( !v18 )
                goto LABEL_146;
              v75 = *(_BYTE *)(v18 + 1) == 2;
              v177 = 0;
              v178 = 4864;
              if ( !v75 )
                goto LABEL_146;
              if ( *(_BYTE *)v18 != 1 )
                goto LABEL_146;
              if ( *(_DWORD *)(v18 + 2) != v177 )
                goto LABEL_146;
              if ( *(_WORD *)(v18 + 6) != v178 )
                goto LABEL_146;
              v76 = *(_DWORD *)(v18 + 8);
              if ( !v76 )
              {
                if ( *(_DWORD *)(v18 + 12) )
                  goto LABEL_146;
              }
              if ( (v75 = v74[1] == 2, LODWORD(v170) = 0, WORD2(v170) = 4864, !v75)
                || *v74 != 1
                || *(_DWORD *)(v74 + 2) != (_DWORD)v170
                || *((_WORD *)v74 + 3) != WORD2(v170)
                || (v77 = *((_DWORD *)v74 + 2)) == 0 && *((_DWORD *)v74 + 3)
                || v76 < v77
                || *(_DWORD *)(v18 + 12) < *((_DWORD *)v74 + 3) )
              {
LABEL_146:
                valid = -1073741790;
                goto LABEL_398;
              }
            }
            v66 = v63 + 1;
          }
        }
LABEL_122:
        if ( (a7 & 0x800) != 0 )
        {
          v72 = 0;
          if ( (v65 & 0x10) != 0 )
          {
            while ( 1 )
            {
              if ( v65 >= 0 )
              {
                v63 = *((_QWORD *)a2 + 3);
              }
              else
              {
                v73 = *((unsigned int *)a2 + 3);
                if ( !(_DWORD)v73 )
                  break;
                v63 = (unsigned __int64)a2 + v73;
              }
              if ( !v63 )
                break;
              v78 = (char *)(v63 + 8);
              v79 = 0;
              if ( !*(_WORD *)(v63 + 4) )
                break;
              while ( v79 < v72 || *v78 != 20 )
              {
                if ( ++v79 >= *(unsigned __int16 *)(v63 + 4) )
                  goto LABEL_156;
                v78 += *((unsigned __int16 *)v78 + 1);
              }
              if ( (v78[1] & 8) == 0 )
                goto LABEL_157;
              v72 = v79 + 1;
            }
          }
LABEL_156:
          if ( v18 )
          {
LABEL_157:
            valid = -1073741811;
LABEL_398:
            v21 = v160;
LABEL_399:
            v12 = v157;
            goto LABEL_400;
          }
        }
        if ( (v65 & 0x10) != 0 )
        {
          if ( v65 >= 0 )
          {
            v80 = (char *)*((_QWORD *)a2 + 3);
          }
          else
          {
            v81 = *((unsigned int *)a2 + 3);
            if ( (_DWORD)v81 )
              v80 = (char *)a2 + v81;
            else
              v80 = 0;
          }
        }
        else
        {
          v80 = 0;
        }
        valid = RtlpValidFilterAclSubjectContext(v80, v18, v63);
        if ( valid < 0 )
          goto LABEL_398;
        v82 = 0;
        v83 = 0;
        v84 = (a7 >> 8) & 1 | 2;
        if ( (a7 & 0x200) == 0 )
          v84 = (a7 >> 8) & 1;
        v85 = v84 | 4;
        if ( (a7 & 0x400) == 0 )
          v85 = v84;
        if ( v85 )
          goto LABEL_180;
        v86 = *((_WORD *)a2 + 1);
        if ( (v86 & 0x10) == 0 )
          goto LABEL_180;
        if ( v86 >= 0 )
        {
          v88 = (char *)*((_QWORD *)a2 + 3);
        }
        else
        {
          v87 = *((unsigned int *)a2 + 3);
          if ( !(_DWORD)v87 )
            goto LABEL_180;
          v88 = (char *)a2 + v87;
        }
        if ( v88 )
        {
          v89 = v88 + 8;
          v90 = 0;
          if ( *((_WORD *)v88 + 2) )
          {
            while ( *v89 != 17 )
            {
              ++v90;
              v89 += *((unsigned __int16 *)v89 + 1);
              if ( v90 >= *((unsigned __int16 *)v88 + 2) )
                goto LABEL_180;
            }
            if ( v89 )
            {
              v83 = v89[1];
              if ( v83 != 8 && (v83 & 0x10) == 0 )
              {
                v85 = *((_DWORD *)v89 + 1);
                v82 = v89 + 8;
                v91 = (char *)Buf1;
                if ( (v83 & 8) != 0 && *((_DWORD *)Buf1 + 2) < 0x2000u )
                {
                  valid = -1073740730;
                  goto LABEL_397;
                }
LABEL_182:
                if ( !v85 )
                {
                  if ( !v91 || *((_DWORD *)v91 + 2) >= 0x2000u )
                    goto LABEL_189;
                  v85 = 1;
                }
                if ( !v89 )
                {
                  if ( !v180 )
                    goto LABEL_396;
                  v82 = v91;
                  v83 = 0;
                }
LABEL_189:
                if ( v82 )
                {
                  v217 = 8388610;
                  LODWORD(v170) = 0;
                  WORD2(v170) = 4096;
                  if ( !(unsigned __int8)RtlValidSid(v82) )
                  {
                    valid = -1073741704;
                    goto LABEL_397;
                  }
                  if ( *(_DWORD *)(v82 + 2) != (_DWORD)v170 || *((_WORD *)v82 + 3) != WORD2(v170) )
                    goto LABEL_218;
                  if ( (unsigned __int8)v217 > 4u )
                  {
                    valid = -1073741735;
                    goto LABEL_397;
                  }
                  v92 = 2;
                  if ( (unsigned __int8)v217 > 2u )
                    v92 = v217;
                  if ( (v83 & 0xE0) != 0 || (v85 & 0xFFFFFFF8) != 0 )
                  {
LABEL_218:
                    valid = -1073741811;
                    goto LABEL_397;
                  }
                  if ( !(unsigned __int8)RtlValidAcl(&v217) )
                  {
LABEL_207:
                    valid = -1073741705;
                    goto LABEL_397;
                  }
                  v93 = &v218;
                  v94 = 0;
                  if ( WORD2(v217) )
                  {
                    while ( v93 < (char *)&v217 + WORD1(v217) )
                    {
                      ++v94;
                      v93 += *((unsigned __int16 *)v93 + 1);
                      if ( v94 >= WORD2(v217) )
                        goto LABEL_211;
                    }
                    goto LABEL_207;
                  }
LABEL_211:
                  if ( v93 > (char *)&v217 + WORD1(v217) )
                    v93 = 0;
                  if ( !v93
                    || (v95 = (unsigned __int16)(4 * ((unsigned __int8)v82[1] + 4)),
                        &v93[v95] > (char *)&v217 + WORD1(v217)) )
                  {
                    valid = -1073741671;
                    goto LABEL_397;
                  }
                  *((_WORD *)v93 + 1) = v95;
                  v96 = &v217;
                  v93[1] = v83;
                  *v93 = 17;
                  *((_DWORD *)v93 + 1) = v85;
                  RtlCopySid(4 * (unsigned int)(unsigned __int8)v82[1] + 8, v93 + 8, v82);
                  ++WORD2(v217);
                  LOBYTE(v217) = v92;
                  v61 = v179;
                }
                else
                {
                  v96 = 0;
                }
                if ( (a7 & 0x700) != 0 )
                {
                  v97 = 4;
                }
                else if ( v89 || !v96 )
                {
                  v97 = (*((_WORD *)a2 + 1) & 0x2800 | (*((unsigned __int16 *)a2 + 1) >> 1) & 0x18u) >> 1;
                }
                else
                {
                  v97 = 0;
                }
                if ( v197 )
                {
                  v98 = *(_WORD *)(v197 + 2);
                  if ( (v98 & 0x10) != 0 )
                  {
                    if ( v98 >= 0 )
                    {
                      v100 = *(_QWORD *)(v197 + 24);
                      goto LABEL_233;
                    }
                    v99 = *(_DWORD *)(v197 + 12);
                    if ( v99 )
                    {
                      LODWORD(v100) = v197 + v99;
                      goto LABEL_233;
                    }
                  }
                }
                LODWORD(v100) = 0;
LABEL_233:
                v101 = RtlpInheritAcl(
                         v100,
                         (_DWORD)v96,
                         v97,
                         a6,
                         1,
                         0,
                         (__int64)v176,
                         (__int64)v61,
                         (__int64)v181,
                         (__int64)v187,
                         v182,
                         3,
                         v191,
                         a5,
                         (__int64)&v196,
                         (__int64)&v174,
                         (__int64)&v172);
                valid = v101;
                if ( v101 == -2147483637 )
                {
                  v102 = 0;
                  v103 = v96;
                  v172 = 0;
                }
                else
                {
                  if ( v101 < 0 )
                    goto LABEL_397;
                  v102 = v172;
                  v103 = v196;
                }
                v104 = RtlpCombineAcls(
                         (_DWORD)Src,
                         (_DWORD)v103,
                         v158,
                         v158,
                         v158,
                         v158,
                         (__int64)&v193,
                         (__int64)&v184);
                v105 = v169;
                valid = v104;
                v184 |= (v169 & 0x2000) << 17;
                if ( !v103 || v103 == v96 )
                {
                  v107 = ProcessHeap;
                }
                else
                {
                  v106 = v103;
                  v107 = ProcessHeap;
                  RtlFreeHeap_0(ProcessHeap, 0, v106);
                }
                if ( valid < 0 )
                  goto LABEL_397;
                v108 = v193;
                v109 = 0;
                if ( v193 )
                {
                  if ( v154 && Src )
                  {
                    RtlFreeHeap_0(v107, 0, Src);
                    v108 = v193;
                  }
                  v110 = v108;
                  Src = v108;
                  v193 = 0;
                  v167 = 1;
                  v105 |= 2 * (v102 & 0x1400 | (2 * (v102 & 8 | 4)));
                  v169 = v105;
                }
                else
                {
                  v110 = (char *)Src;
                }
                if ( (a7 & 8) == 0 )
                {
                  if ( v110 )
                  {
                    v111 = v110 + 8;
                    v112 = 0;
                    v113 = *((unsigned __int16 *)v110 + 2);
                    if ( v113 )
                    {
                      while ( *v111 != 17 )
                      {
                        ++v112;
                        v111 += *((unsigned __int16 *)v111 + 1);
                        if ( v112 >= v113 )
                          goto LABEL_255;
                      }
                      v82 = v111 + 8;
                    }
                  }
LABEL_255:
                  if ( v82 )
                  {
                    if ( !v180 )
                      goto LABEL_396;
                    valid = RtlSidDominates(Buf1, v82);
                    if ( valid < 0 )
                      goto LABEL_397;
                    v109 = v164 == 0;
                  }
                }
                v114 = *((_WORD *)a2 + 1);
                if ( (v114 & 4) != 0 )
                {
                  if ( v114 >= 0 )
                  {
                    v115 = *((_QWORD *)a2 + 4);
                  }
                  else
                  {
                    v116 = *((_DWORD *)a2 + 4);
                    if ( v116 )
                      LODWORD(v115) = (_DWORD)a2 + v116;
                    else
                      LODWORD(v115) = 0;
                  }
                }
                else
                {
                  LODWORD(v115) = 0;
                }
                v117 = v197;
                if ( v197 )
                {
                  v118 = *(_WORD *)(v197 + 2);
                  if ( (v118 & 4) != 0 )
                  {
                    if ( v118 >= 0 )
                    {
                      v120 = *(_QWORD *)(v197 + 32);
                      goto LABEL_273;
                    }
                    v119 = *(_DWORD *)(v197 + 16);
                    if ( v119 )
                    {
                      LODWORD(v120) = v119 + v197;
                      goto LABEL_273;
                    }
                  }
                }
                LODWORD(v120) = 0;
LABEL_273:
                v121 = RtlpInheritAcl(
                         v120,
                         v115,
                         v114 & 0x140C,
                         a6,
                         a7 & 1,
                         (char)v188,
                         (__int64)v176,
                         (__int64)v179,
                         (__int64)v181,
                         (__int64)v187,
                         v182,
                         1,
                         v191,
                         a5,
                         (__int64)&Handle,
                         (__int64)&v163,
                         (__int64)&v172);
                valid = v121;
                if ( v121 >= 0 )
                {
                  v155 = 1;
                  v105 |= v172 & 0x1408 | 4;
                  v169 = v105;
LABEL_275:
                  v122 = (char *)Handle;
                  v157 = Handle;
LABEL_276:
                  if ( (a7 & 0x1000) == 0 && v165 )
                  {
                    if ( !v180 || !v117 )
                    {
                      v127 = v180;
                      goto LABEL_315;
                    }
                    v177 = 0;
                    LODWORD(v188) = 0;
                    valid = RtlpNewSecurityObject(v117, 0, (unsigned int)&v192, v191, a5, a6, a7 | 1, v180, v182);
                    if ( valid < 0 )
                      goto LABEL_397;
                    v123 = *(unsigned __int16 *)(v192 + 2);
                    if ( (v123 & 4) != 0 )
                    {
                      if ( (v123 & 0x8000u) == 0LL )
                      {
                        v124 = *(_QWORD *)(v192 + 32);
                      }
                      else
                      {
                        v123 = *(unsigned int *)(v192 + 16);
                        if ( (_DWORD)v123 )
                          v124 = v192 + v123;
                        else
                          v124 = 0;
                      }
                    }
                    else
                    {
                      v124 = 0;
                    }
                    LOBYTE(v123) = 16;
                    if ( (unsigned __int8)RtlpOwnerAcesPresent(v123, v124) )
                    {
                      v127 = v180;
                      Handle = 0;
                      v172 = 20;
                      if ( (_BYTE)v185 != 1 )
                        goto LABEL_307;
                      v213 = 0x30u;
                      v210 = 1;
                      *((_QWORD *)&v215 + 1) = &v209;
                      v209 = 0x20000000CLL;
                      v214 = 0u;
                      *(_QWORD *)&v215 = 0;
                      valid = NtDuplicateToken(v180, 8, &v213, 0, 2, &Handle);
                      if ( valid < 0 )
                        goto LABEL_397;
                      v128 = (__int64)Handle;
                      if ( !Handle )
LABEL_307:
                        v128 = v127;
                      valid = ZwAccessCheck(v192, v128, 0x40000, v182, &v211, &v172, &v177, &v188);
                      if ( Handle )
                        NtClose(Handle);
                      if ( valid < 0 )
                        goto LABEL_397;
                      valid = (int)v188;
                      if ( (int)v188 < 0 )
                        goto LABEL_397;
                      goto LABEL_315;
                    }
                  }
                  v127 = v180;
LABEL_315:
                  if ( (a7 & 1) != 0 && !v122 )
                  {
                    v105 |= 0x1000u;
                    v169 = v105;
                  }
                  v129 = !v184 || (v184 & 0x1B0) != v184;
                  if ( v153 && (a7 & 8) == 0 && v129 )
                  {
                    if ( !v127 )
                      goto LABEL_396;
                    *(_QWORD *)&v211 = 0x100000001LL;
                    v212 = 0;
                    *((_QWORD *)&v211 + 1) = 8;
                    valid = ZwPrivilegeCheck(v127, &v211, v159);
                    if ( valid < 0 )
                      goto LABEL_397;
                    if ( !v159[0] )
                    {
                      valid = -1073741727;
                      goto LABEL_397;
                    }
                  }
                  if ( v109 && (a7 & 8) == 0 )
                  {
                    if ( !v127 )
                      goto LABEL_396;
                    *(_QWORD *)&v211 = 0x100000001LL;
                    *((_QWORD *)&v211 + 1) = 32;
                    v212 = 0;
                    valid = ZwPrivilegeCheck(v127, &v211, v159);
                    if ( valid < 0 )
                      goto LABEL_397;
                    if ( !v159[0] )
                    {
                      valid = -1073741727;
                      goto LABEL_397;
                    }
                  }
                  if ( !v162 || (a7 & 0x10) != 0 )
                  {
                    v130 = (unsigned __int8 *)v176;
                    goto LABEL_341;
                  }
                  if ( v127 )
                  {
                    v130 = (unsigned __int8 *)v176;
                    if ( !(unsigned __int8)RtlpValidOwnerSubjectContext(v127, v176, v175, &v190) )
                    {
                      valid = v190;
                      goto LABEL_397;
                    }
LABEL_341:
                    if ( v163 && v171 )
                    {
                      valid = RtlpCreateServerAcl(
                                (_DWORD)v122,
                                (unsigned __int8)v194,
                                (_DWORD)v181,
                                (unsigned int)&v195,
                                (__int64)&v166);
                      if ( valid < 0 )
                      {
                        v133 = v195;
                        v12 = v157;
                        v11 = (char *)Src;
                        v21 = v160;
LABEL_401:
                        v151 = v158;
                        goto LABEL_402;
                      }
                      v131 = ProcessHeap;
                      if ( v155 && v122 )
                        RtlFreeHeap_0(ProcessHeap, 0, v122);
                      v132 = v195;
                      v157 = v195;
                      v161 = 0;
                    }
                    else
                    {
                      v131 = ProcessHeap;
                      v132 = (unsigned __int16 *)v157;
                    }
                    v134 = 4 * v130[1] + 8;
                    if ( v179 )
                      v135 = 4 * *((unsigned __int8 *)v179 + 1) + 8;
                    else
                      v135 = 0;
                    v136 = v105 & 0x10;
                    if ( (v105 & 0x10) != 0 && Src )
                      v137 = (*((unsigned __int16 *)Src + 1) + 3) & 0xFFFFFFFC;
                    else
                      v137 = 0;
                    v138 = v105 & 4;
                    if ( v138 && v132 )
                      v139 = (v132[1] + 3) & 0xFFFFFFFC;
                    else
                      v139 = 0;
                    Heap_0 = RtlAllocateHeap_0(
                               v131,
                               (unsigned int)(NtdllBaseTag + 1310720),
                               v135 + v137 + v134 + v139 + 20);
                    v160 = Heap_0;
                    v141 = Heap_0;
                    if ( Heap_0 )
                    {
                      v142 = v169;
                      v143 = (unsigned __int16 *)(Heap_0 + 20);
                      *(_OWORD *)Heap_0 = 0;
                      *(_DWORD *)(Heap_0 + 16) = 0;
                      *(_WORD *)(Heap_0 + 2) |= v142;
                      *(_BYTE *)Heap_0 = 1;
                      if ( v136 )
                      {
                        if ( Src )
                        {
                          v144 = Heap_0 + 20;
                          if ( (a7 & 0x4000) != 0 )
                          {
                            v145 = v182;
                            if ( v154 )
                              v145 = 0;
                            RtlpNormalizeAcl(Heap_0 + 20, Src, v145);
                            if ( v143[2] )
                            {
                              v137 = v143[1];
                            }
                            else
                            {
                              v144 = 0;
                              v137 = 0;
                            }
                          }
                          else
                          {
                            memmove((void *)(Heap_0 + 20), Src, *((unsigned __int16 *)Src + 1));
                            if ( !v154 )
                              RtlpApplyAclToObject(v143, v182);
                            v146 = *((unsigned __int16 *)Src + 1);
                            if ( v137 > (unsigned int)v146 )
                              memset_thunk_772440563353939046((char *)v143 + v146, 0, v137 - (unsigned int)v146);
                          }
                          v141 = v160;
                          if ( v144 )
                          {
                            v143 = (unsigned __int16 *)((char *)v143 + v137);
                            *(_DWORD *)(v160 + 12) = v144 - v160;
                          }
                          else
                          {
                            *(_DWORD *)(v160 + 12) = 0;
                          }
                        }
                        else
                        {
                          *(_DWORD *)(Heap_0 + 12) = 0;
                        }
                      }
                      if ( v138 )
                      {
                        v147 = (unsigned __int16 *)v157;
                        if ( v157 )
                        {
                          if ( (a7 & 0x4000) != 0 )
                          {
                            v148 = v182;
                            if ( v155 )
                              v148 = 0;
                            RtlpNormalizeAcl(v143, v157, v148);
                            v139 = v143[1];
                          }
                          else
                          {
                            memmove(v143, v157, *((unsigned __int16 *)v157 + 1));
                            if ( !v155 )
                              RtlpApplyAclToObject(v143, v182);
                            v149 = v147[1];
                            if ( v139 > (unsigned int)v149 )
                              memset_thunk_772440563353939046((char *)v143 + v149, 0, v139 - (unsigned int)v149);
                          }
                          *(_DWORD *)(v160 + 16) = (_DWORD)v143 - v160;
                          v143 = (unsigned __int16 *)((char *)v143 + v139);
                        }
                        else
                        {
                          *(_DWORD *)(v141 + 16) = 0;
                        }
                      }
                      memmove(v143, v176, v134);
                      v21 = v160;
                      *(_DWORD *)(v160 + 4) = (_DWORD)v143 - v160;
                      if ( v179 )
                      {
                        v150 = (char *)v143 + v134;
                        memmove(v150, v179, v135);
                        *(_DWORD *)(v21 + 8) = (_DWORD)v150 - v21;
                      }
                      v11 = (char *)Src;
                      valid = 0;
                      goto LABEL_399;
                    }
                    valid = -1073741801;
                    goto LABEL_397;
                  }
LABEL_396:
                  valid = -1073741700;
                  goto LABEL_397;
                }
                if ( v121 != -2147483637 )
                {
                  v12 = Handle;
                  v11 = (char *)Src;
                  v21 = v160;
                  goto LABEL_400;
                }
                if ( (a7 & 1) != 0 )
                {
                  v105 |= 0x400u;
                  v169 = v105;
                }
                v125 = *((_WORD *)a2 + 1);
                if ( (v125 & 0xC) != 0xC )
                {
                  if ( v209 )
                  {
                    v105 |= 4u;
                    v157 = (void *)v209;
                    v169 = v105;
                    v122 = (char *)v209;
                    goto LABEL_276;
                  }
                  goto LABEL_275;
                }
                if ( (v125 & 4) != 0 )
                {
                  if ( v125 >= 0 )
                  {
                    v122 = (char *)*((_QWORD *)a2 + 4);
                  }
                  else
                  {
                    v126 = *((unsigned int *)a2 + 4);
                    if ( (_DWORD)v126 )
                    {
                      v157 = (char *)a2 + v126;
                      v122 = (char *)a2 + v126;
LABEL_295:
                      v163 = 1;
                      v105 |= v125 & 0x1000 | 4;
                      v169 = v105;
                      goto LABEL_276;
                    }
                    v122 = 0;
                  }
                }
                else
                {
                  v122 = 0;
                }
                v157 = v122;
                goto LABEL_295;
              }
              v89 = 0;
              v85 = 0;
              v83 = 0;
            }
LABEL_181:
            v91 = (char *)Buf1;
            goto LABEL_182;
          }
        }
LABEL_180:
        v89 = 0;
        goto LABEL_181;
      }
      if ( v69 >= 0 )
      {
        v64 = *((_QWORD *)a2 + 3);
      }
      else
      {
        v70 = *((unsigned int *)a2 + 3);
        if ( (_DWORD)v70 )
          v64 = (__int64)a2 + v70;
        else
          v64 = 0;
      }
LABEL_102:
      v158 = v64;
      goto LABEL_103;
    }
LABEL_101:
    v64 = v170;
    goto LABEL_102;
  }
  v151 = v170;
  v12 = v157;
  v21 = v160;
  v133 = v161;
LABEL_402:
  if ( v192 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v192);
  if ( v166 && v133 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v133);
  v152 = ProcessHeap;
  RtlFreeHeap_0(ProcessHeap, 0, v198);
  RtlFreeHeap_0(v152, 0, v199);
  RtlFreeHeap_0(v152, 0, v200);
  RtlFreeHeap_0(v152, 0, v201);
  RtlFreeHeap_0(v152, 0, v202);
  if ( v203 )
    RtlFreeHeap_0(v152, 0, v203);
  if ( v204 )
    RtlFreeHeap_0(v152, 0, v204);
  if ( (v154 || v167) && v11 )
    RtlFreeHeap_0(v152, 0, v11);
  if ( v168 && v151 )
    RtlFreeHeap_0(v152, 0, v151);
  if ( v155 )
  {
    if ( v12 )
      RtlFreeHeap_0(v152, 0, v12);
  }
  *v205 = v21;
  return (unsigned int)valid;
}

```

## disassembly

```asm
0x1800de100  push    rbp
0x1800de102  push    rbx
0x1800de103  push    rdi
0x1800de104  push    r12
0x1800de106  push    r13
0x1800de108  push    r15
0x1800de10a  lea     rbp, [rsp-1F8h]
0x1800de112  sub     rsp, 308h
0x1800de119  mov     rax, cs:__security_cookie
0x1800de120  xor     rax, rsp
0x1800de123  mov     [rbp+220h+var_50], rax
0x1800de12a  mov     rax, [rbp+220h+arg_40]
0x1800de131  xor     ebx, ebx
0x1800de133  mov     [rbp+220h+var_218], rax
0x1800de137  xorps   xmm0, xmm0
0x1800de13a  xor     eax, eax
0x1800de13c  mov     [rbp+220h+var_208], ebx
0x1800de13f  mov     [rbp+220h+var_140], rax
0x1800de146  mov     r15, rcx
0x1800de149  mov     [rbp+220h+var_2A0], al
0x1800de14c  mov     r12, rdx
0x1800de14f  mov     [rbp+220h+var_248], al
0x1800de152  mov     r13d, ebx
0x1800de155  mov     [rbp+220h+var_247], al
0x1800de158  mov     edi, ebx
0x1800de15a  mov     [rbp+220h+var_267], al
0x1800de15d  mov     [rbp+220h+var_264], al
0x1800de160  mov     [rbp+220h+var_280], al
0x1800de163  mov     [rbp+220h+var_118], eax
0x1800de169  movups  [rbp+220h+var_160], xmm0
0x1800de170  mov     [rbp+220h+var_1C8], rbx
0x1800de174  movups  [rbp+220h+var_150], xmm0
0x1800de17b  mov     [rbp+220h+var_1D0], rbx
0x1800de17f  movups  [rbp+220h+var_128], xmm0
0x1800de186  mov     rax, gs:60h
0x1800de18f  mov     [rbp+220h+var_1A8], rcx
0x1800de193  mov     rcx, [rbp+220h+arg_38]
0x1800de19a  mov     [rbp+220h+var_1D8], r9
0x1800de19e  mov     rax, [rax+30h]
0x1800de1a2  mov     [rbp+220h+var_200], rax
0x1800de1a6  mov     [rbp+220h+var_168], r8
0x1800de1ad  mov     [rbp+220h+var_228], rcx
0x1800de1b1  mov     [rbp+220h+Src], rbx
0x1800de1b5  mov     [rbp+220h+var_288], rbx
0x1800de1b9  mov     [rbp+220h+var_258], rbx
0x1800de1bd  mov     [rbp+220h+var_290], rbx
0x1800de1c1  mov     [rbp+220h+Handle], rbx
0x1800de1c5  mov     [rbp+220h+var_270], rbx
0x1800de1c9  mov     [rbp+220h+var_1B8], rbx
0x1800de1cd  mov     [rbp+220h+var_24C], ebx
0x1800de1d0  mov     [rbp+220h+var_238], ebx
0x1800de1d3  mov     [rbp+220h+var_1B0], rbx
0x1800de1d7  mov     [rbp+220h+var_266], 1
0x1800de1db  mov     [rbp+220h+var_1E0], ebx
0x1800de1de  mov     byte ptr [rbp+220h+var_204], 1
0x1800de1e2  mov     [rbp+220h+var_1A0], rbx
0x1800de1e9  mov     [rbp+220h+var_1F8], rbx
0x1800de1ed  mov     [rbp+220h+var_188], rbx
0x1800de1f4  mov     [rbp+220h+Buf1], rbx
0x1800de1f8  mov     [rbp+220h+var_180], rbx
0x1800de1ff  mov     [rbp+220h+var_220], rbx
0x1800de203  mov     [rbp+220h+var_198], rbx
0x1800de20a  mov     [rbp+220h+var_230], rbx
0x1800de20e  mov     [rbp+220h+var_190], rbx
0x1800de215  mov     [rbp+220h+var_240], rbx
0x1800de219  mov     [rbp+220h+var_178], rbx
0x1800de220  mov     [rbp+220h+var_278], rbx
0x1800de224  mov     [rbp+220h+var_170], rbx
0x1800de22b  mov     [rbp+220h+var_1F0], rbx
0x1800de22f  test    rcx, rcx
0x1800de232  jz      short loc_1800DE2A2
0x1800de234  xor     eax, eax
0x1800de236  mov     [rbp+220h+var_204], ebx
0x1800de239  mov     [rbp+220h+var_E0], rax
0x1800de240  lea     r8, [rbp+220h+var_110]
0x1800de247  lea     rax, [rbp+220h+var_204]
0x1800de24b  mov     r9d, 38h ; '8'
0x1800de251  mov     edx, 0Ah
0x1800de256  mov     [rsp+330h+var_310], rax
0x1800de25b  movups  [rbp+220h+var_110], xmm0
0x1800de262  movups  [rbp+220h+var_100], xmm0
0x1800de269  movups  [rbp+220h+var_F0], xmm0
0x1800de270  call    NtQueryInformationToken
0x1800de275  test    eax, eax
0x1800de277  js      loc_1800DF7ED
0x1800de27d  mov     edx, dword ptr [rbp+220h+var_100+8]
0x1800de283  mov     [rbp+220h+var_204], edx
0x1800de286  cmp     edx, 2
0x1800de289  jnz     short loc_1800DE29E
0x1800de28b  cmp     dword ptr [rbp+220h+var_100+0Ch], 1
0x1800de292  jge     short loc_1800DE29E
0x1800de294  mov     eax, 0C00000A5h
0x1800de299  jmp     loc_1800DF7ED
0x1800de29e  mov     rcx, [rbp+220h+var_228]
0x1800de2a2  test    r12, r12
0x1800de2a5  jz      short loc_1800DE2AD
0x1800de2a7  mov     [rbp+220h+var_265], 1
0x1800de2ab  jmp     short loc_1800DE2D8
0x1800de2ad  xorps   xmm0, xmm0
0x1800de2b0  mov     [rbp+220h+var_265], bl
0x1800de2b3  xor     eax, eax
0x1800de2b5  lea     r12, [rbp+220h+var_160]
0x1800de2bc  movups  [rbp+220h+var_160], xmm0
0x1800de2c3  mov     byte ptr [rbp+220h+var_160], 1
0x1800de2ca  movups  [rbp+220h+var_150], xmm0
0x1800de2d1  mov     [rbp+220h+var_140], rax
0x1800de2d8  movzx   eax, word ptr [r12+2]
0x1800de2de  mov     r8d, 80h
0x1800de2e4  movzx   edx, ax
0x1800de2e7  mov     [rsp+330h+var_38], r14
0x1800de2ef  and     dx, r8w
0x1800de2f3  mov     [rbp+220h+var_250], dx
0x1800de2f7  setnz   r10b
0x1800de2fb  shr     al, 6
0x1800de2fe  and     al, 1
0x1800de300  mov     [rbp+220h+var_246], r10b
0x1800de304  mov     [rbp+220h+var_1C0], eax
0x1800de307  test    rcx, rcx
0x1800de30a  jnz     short loc_1800DE384
0x1800de30c  test    dx, dx
0x1800de30f  jnz     short loc_1800DE384
0x1800de311  mov     rcx, rbx
0x1800de314  mov     [rbp+220h+Buf1], rbx
0x1800de318  mov     r14, rbx
0x1800de31b  mov     [rbp+220h+var_220], rbx
0x1800de31f  mov     [rbp+220h+var_138], rbx
0x1800de326  mov     r9, rbx
0x1800de329  mov     [rbp+220h+var_1F8], rbx
0x1800de32d  mov     r10, rbx
0x1800de330  mov     r11d, [rbp+220h+arg_30]
0x1800de337  mov     eax, 8000h
0x1800de33c  mov     [rsp+330h+var_30], rsi
0x1800de344  mov     rsi, rbx
0x1800de347  mov     [rbp+220h+var_29F], bl
0x1800de34a  mov     [rbp+220h+var_262], bl
0x1800de34d  mov     [rbp+220h+var_263], bl
0x1800de350  mov     [rbp+220h+var_29E], bl
0x1800de353  mov     [rbp+220h+var_278], rbx
0x1800de357  movzx   ebx, word ptr [r12+2]
0x1800de35d  movzx   r8d, bx
0x1800de361  and     r8w, ax
0x1800de365  movzx   edx, r8w
0x1800de369  jz      loc_1800DE458
0x1800de36f  mov     eax, [r12+4]
0x1800de374  test    eax, eax
0x1800de376  jz      loc_1800DE482
0x1800de37c  add     rax, r12
0x1800de37f  jmp     loc_1800DE45D
0x1800de384  lea     rax, [rbp+220h+var_1F0]
0x1800de388  movzx   edx, r10b
0x1800de38c  mov     [rsp+330h+var_2F0], rax
0x1800de391  lea     r9, [rbp+220h+Buf1]
0x1800de395  lea     rax, [rbp+220h+var_240]
0x1800de399  mov     [rsp+330h+var_2F8], rax
0x1800de39e  lea     r8, [rbp+220h+var_1F8]
0x1800de3a2  lea     rax, [rbp+220h+var_230]
0x1800de3a6  mov     [rsp+330h+var_300], rax
0x1800de3ab  lea     rax, [rbp+220h+var_278]
0x1800de3af  mov     [rsp+330h+var_308], rax
0x1800de3b4  lea     rax, [rbp+220h+var_220]
0x1800de3b8  mov     [rsp+330h+var_310], rax
0x1800de3bd  call    RtlpGetDefaultsSubjectContext
0x1800de3c2  test    eax, eax
0x1800de3c4  js      loc_1800DF7E5
0x1800de3ca  mov     rax, [rbp+220h+var_1F8]
0x1800de3ce  mov     [rbp+220h+var_1A0], rax
0x1800de3d5  mov     rcx, [rax]
0x1800de3d8  mov     rax, [rbp+220h+Buf1]
0x1800de3dc  mov     [rbp+220h+var_188], rax
0x1800de3e3  mov     r9, [rax]
0x1800de3e6  mov     rax, [rbp+220h+var_220]
0x1800de3ea  mov     [rbp+220h+var_180], rax
0x1800de3f1  mov     rax, [rax]
0x1800de3f4  mov     [rbp+220h+var_138], rax
0x1800de3fb  mov     rax, [rbp+220h+var_230]
0x1800de3ff  mov     [rbp+220h+var_198], rax
0x1800de406  mov     rax, [rax]
0x1800de409  mov     [rbp+220h+Buf1], rax
0x1800de40d  mov     rax, [rbp+220h+var_240]
0x1800de411  mov     [rbp+220h+var_190], rax
0x1800de418  mov     r14, [rax]
0x1800de41b  mov     rax, [rbp+220h+var_278]
0x1800de41f  mov     [rbp+220h+var_178], rax
0x1800de426  test    rax, rax
0x1800de429  jz      short loc_1800DE434
0x1800de42b  mov     rax, [rax]
0x1800de42e  mov     [rbp+220h+var_220], rax
0x1800de432  jmp     short loc_1800DE438
0x1800de434  mov     [rbp+220h+var_220], rbx
0x1800de438  mov     rax, [rbp+220h+var_1F0]
0x1800de43c  mov     [rbp+220h+var_170], rax
0x1800de443  test    rax, rax
0x1800de446  jz      loc_1800DE329
0x1800de44c  mov     r10, [rax]
0x1800de44f  mov     [rbp+220h+var_1F8], r10
0x1800de453  jmp     loc_1800DE330
0x1800de458  mov     rax, [r12+8]
0x1800de45d  mov     [rbp+220h+var_240], rax
0x1800de461  test    rax, rax
0x1800de464  jz      short loc_1800DE482
0x1800de466  movzx   ecx, [rbp+220h+var_250]
0x1800de46a  mov     [rbp+220h+var_268], 1
0x1800de46e  test    dx, dx
0x1800de471  jz      short loc_1800DE4E8
0x1800de473  mov     eax, [r12+8]
0x1800de478  test    eax, eax
0x1800de47a  jz      short loc_1800DE4F6
0x1800de47c  lea     rdx, [r12+rax]
0x1800de480  jmp     short loc_1800DE4ED
0x1800de482  test    r11b, 20h
0x1800de486  jz      short loc_1800DE4C2
0x1800de488  test    r15, r15
0x1800de48b  jnz     short loc_1800DE497
0x1800de48d  mov     ebx, 0C000005Ah
0x1800de492  jmp     loc_1800DF6B5
0x1800de497  cmp     [r15+2], si
0x1800de49c  jge     short loc_1800DE4AB
0x1800de49e  mov     eax, [r15+4]
0x1800de4a2  test    eax, eax
0x1800de4a4  jz      short loc_1800DE4B8
0x1800de4a6  add     rax, r15
0x1800de4a9  jmp     short loc_1800DE4AF
0x1800de4ab  mov     rax, [r15+8]
0x1800de4af  mov     [rbp+220h+var_240], rax
0x1800de4b3  test    rax, rax
0x1800de4b6  jnz     short loc_1800DE466
0x1800de4b8  mov     ebx, 0C000005Ah
0x1800de4bd  jmp     loc_1800DF6B5
0x1800de4c2  mov     rax, rcx
0x1800de4c5  mov     [rbp+220h+var_268], sil
0x1800de4c9  movzx   ecx, [rbp+220h+var_250]
0x1800de4cd  test    cx, cx
0x1800de4d0  cmovnz  rax, [rbp+220h+var_220]
0x1800de4d5  mov     [rbp+220h+var_240], rax
0x1800de4d9  test    rax, rax
0x1800de4dc  jnz     short loc_1800DE46E
0x1800de4de  mov     ebx, 0C000007Ch
0x1800de4e3  jmp     loc_1800DF6B5
0x1800de4e8  mov     rdx, [r12+10h]
0x1800de4ed  mov     [rbp+220h+var_230], rdx
0x1800de4f1  test    rdx, rdx
0x1800de4f4  jnz     short loc_1800DE543
0x1800de4f6  test    r11b, 40h
0x1800de4fa  jz      short loc_1800DE526
0x1800de4fc  test    r15, r15
0x1800de4ff  jnz     short loc_1800DE50B
0x1800de501  mov     ebx, 0C000005Bh
0x1800de506  jmp     loc_1800DF6B5
0x1800de50b  cmp     [r15+2], si
0x1800de510  jge     short loc_1800DE520
0x1800de512  mov     eax, [r15+8]
0x1800de516  test    eax, eax
0x1800de518  jz      short loc_1800DE539
0x1800de51a  lea     rdx, [r15+rax]
0x1800de51e  jmp     short loc_1800DE530
0x1800de520  mov     rdx, [r15+10h]
0x1800de524  jmp     short loc_1800DE530
0x1800de526  test    cx, cx
0x1800de529  mov     rdx, r9
0x1800de52c  cmovnz  rdx, r10
0x1800de530  mov     [rbp+220h+var_230], rdx
0x1800de534  test    rdx, rdx
0x1800de537  jnz     short loc_1800DE543
0x1800de539  mov     ebx, 0C000005Bh
0x1800de53e  jmp     loc_1800DF6B5
0x1800de543  mov     r13d, r11d
0x1800de546  mov     edi, r11d
0x1800de549  shr     r13d, 2
0x1800de54d  movzx   ecx, bx
0x1800de550  and     r13b, 1
0x1800de554  mov     r9d, ebx
0x1800de557  and     edi, 2
0x1800de55a  mov     dword ptr [rbp+220h+var_1F0], r13d
0x1800de55e  mov     r11d, ebx
0x1800de561  setnz   sil
0x1800de565  and     cx, 10h
0x1800de569  movzx   eax, cx
0x1800de56c  neg     ax
0x1800de56f  sbb     r10d, r10d
0x1800de572  shr     r9d, 2
0x1800de576  shr     r11d, 1
0x1800de579  and     r9d, 8
0x1800de57d  shr     ebx, 1
0x1800de57f  and     r11d, 400h
0x1800de586  and     ebx, 1000h
0x1800de58c  and     r10d, 4
0x1800de590  test    cx, cx
0x1800de593  jnz     short loc_1800DE599
0x1800de595  xor     edx, edx
0x1800de597  jmp     short loc_1800DE5B7
0x1800de599  test    r8w, r8w
0x1800de59d  jz      short loc_1800DE5B2
0x1800de59f  mov     eax, [r12+0Ch]
0x1800de5a4  test    eax, eax
0x1800de5a6  jnz     short loc_1800DE5AC
0x1800de5a8  xor     edx, edx
0x1800de5aa  jmp     short loc_1800DE5B7
0x1800de5ac  lea     rdx, [r12+rax]
0x1800de5b0  jmp     short loc_1800DE5B7
0x1800de5b2  mov     rdx, [r12+18h]
  ... truncated ...
```
