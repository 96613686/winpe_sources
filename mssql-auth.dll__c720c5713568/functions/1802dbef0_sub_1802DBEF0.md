# sub_1802DBEF0

- ea: `0x1802dbef0`
- end: `0x1802ddc9c`
- name: `sub_1802DBEF0`
- size: `7596`
- prototype: ``
- caller_count: `1`
- callee_count: `59`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1802ec090`

## callees

- `0x180003e60`
- `0x1800050e0`
- `0x180005740`
- `0x180005ba0`
- `0x180007de0`
- `0x180009780`
- `0x18000a650`
- `0x180020bc0`
- `0x180020e60`
- `0x180021240`
- `0x180023780`
- `0x180060840`
- `0x1800608c0`
- `0x180060dd0`
- `0x180069df0`
- `0x1800a2a00`
- `0x180144880`
- `0x180196300`
- `0x1801ad7d0`
- `0x1801adc90`
- `0x1801ae334`
- `0x1801ae380`
- `0x180201310`
- `0x1802041e0`
- `0x180205d70`
- `0x18020af20`
- `0x18020ba40`
- `0x1802145c0`
- `0x18022cc50`
- `0x180237650`
- `0x180239290`
- `0x1802548d0`
- `0x180254dc0`
- `0x18026a700`
- `0x1802a0650`
- `0x1802a31b0`
- `0x1802ade10`
- `0x1802c8690`
- `0x1802c9290`
- `0x1802cf6d0`
- `0x1802d5630`
- `0x1802d5fa0`
- `0x1802d8180`
- `0x1802d8240`
- `0x1802d8f40`
- `0x1802d9a70`
- `0x1802d9c50`
- `0x1802daf00`
- `0x1802db4b0`
- `0x1802db5a0`

## string_xrefs

- `0x1802dd020`: `broker_error_location`
- `0x1802dd2ad`: `Attempt to acquire a token via refresh token failed`
- `0x1802dcdb8`: `Invalid readAllAccounts response`
- `0x1802dda3a`: `AuthorizationType %d failed in a non-critical way, and we didn't attempt to read from cache.`
- `0x1802ddaea`: `No Home Account ID available for us to read the cache`

## pseudocode

```c
__int64 __fastcall sub_1802DBEF0(__int64 a1)
{
  int v2; // r15d
  _QWORD *v3; // r14
  _QWORD *v4; // r12
  char v5; // al
  __int64 v6; // r8
  __int64 v7; // rsi
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 result; // rax
  __int64 v11; // rcx
  char v12; // si
  _QWORD *v13; // rax
  __m128i si128; // xmm6
  int v15; // edx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rbx
  _QWORD *v21; // rax
  __int64 v22; // rdi
  __int64 v23; // rbx
  __int64 v24; // rax
  char v25; // bl
  __int64 v26; // rbx
  int v27; // r9d
  int v28; // r8d
  __int64 v29; // rax
  __int64 *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int128 *, __int64, __int64); // rbx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 *v38; // rax
  __int64 v39; // rbx
  __int64 v40; // rcx
  __int64 v41; // rax
  _QWORD *v42; // rax
  _QWORD *v43; // rax
  _QWORD *v44; // rax
  int v45; // r15d
  __int64 v46; // rax
  char v47; // bl
  int v48; // r8d
  __int64 v49; // rax
  bool v50; // bl
  _QWORD *v51; // rax
  _QWORD *v52; // rax
  bool v53; // bl
  __int64 *v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // rdi
  void (__fastcall *v59)(__int64, __int64); // rbx
  __int64 v60; // rax
  __int64 *v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // rcx
  __int64 *v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // rcx
  bool v69; // bl
  __int64 v70; // r14
  void (__fastcall *v71)(__int64, __int128 *, __int64, __int64, _DWORD, __int64); // rsi
  char v72; // di
  __int64 v73; // rbx
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rcx
  void (__fastcall *v77)(__int64, __int64); // rax
  int v78; // r8d
  __int64 v79; // rax
  __int64 v80; // rsi
  void (__fastcall *v81)(__int64, _BYTE *, __int64); // rdi
  _QWORD *v82; // rax
  unsigned int v83; // eax
  __int64 v84; // rbx
  __int64 *v85; // rax
  __int64 v86; // rcx
  __int64 v87; // rdx
  __int64 v88; // rax
  bool v89; // bl
  __int64 v90; // rdi
  void (__fastcall *v91)(__int64, __int64); // rbx
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rcx
  __int64 v95; // rcx
  __int64 v96; // rdx
  __int64 *v97; // rax
  __int64 *v98; // rax
  __int64 v99; // rcx
  __int64 v100; // rdx
  __int64 v101; // rcx
  __int64 v102; // rcx
  __int64 v103; // rdx
  __int64 v104; // rcx
  bool v105; // bl
  __int64 v106; // r9
  __int64 v107; // rcx
  char v108; // al
  bool v109; // si
  __int64 *v110; // rax
  __int64 v111; // rcx
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // rcx
  __int64 v115; // rax
  __int64 v116; // rbx
  __int64 v117; // rbx
  __int64 v118; // rax
  __int64 v119; // rbx
  __int64 v120; // rax
  __int64 v121; // rsi
  __int64 v122; // rax
  __int64 v123; // rbx
  bool v124; // bl
  bool v125; // bl
  __int64 v126; // r9
  __int64 v127; // rax
  __int64 v128; // rcx
  __int64 *v129; // rax
  __int64 v130; // rcx
  __int64 v131; // rdx
  __int64 v132; // rcx
  __int64 *v133; // rax
  __int64 v134; // rcx
  __int64 v135; // rdx
  __int64 v136; // rcx
  __int64 v137; // rax
  __int64 v138; // rbx
  int v139; // r9d
  int v140; // r8d
  __int64 v141; // rax
  int v142; // r8d
  __int64 v143; // rax
  unsigned __int8 v144; // al
  __int64 v145; // rax
  __int64 v146; // rax
  __int64 v147; // [rsp+20h] [rbp-E0h]
  __int64 v148; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v149; // [rsp+48h] [rbp-B8h]
  bool v150; // [rsp+50h] [rbp-B0h]
  __int128 v151; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v152; // [rsp+70h] [rbp-90h] BYREF
  __m128i v153; // [rsp+80h] [rbp-80h]
  int v154; // [rsp+90h] [rbp-70h] BYREF
  __int128 v155; // [rsp+98h] [rbp-68h] BYREF
  __int128 v156; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v157; // [rsp+B8h] [rbp-48h]
  __int64 v158; // [rsp+C0h] [rbp-40h]
  __int64 v159; // [rsp+C8h] [rbp-38h]
  _BYTE v160[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v161; // [rsp+D8h] [rbp-28h]
  _BYTE v162[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v163[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v164[208]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v165; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v166; // [rsp+200h] [rbp+100h] BYREF
  __int128 v167; // [rsp+210h] [rbp+110h] BYREF
  __int128 v168; // [rsp+220h] [rbp+120h] BYREF
  __int128 v169; // [rsp+230h] [rbp+130h] BYREF
  __int128 v170; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v171[32]; // [rsp+250h] [rbp+150h] BYREF
  __int128 v172; // [rsp+270h] [rbp+170h] BYREF
  __int128 v173; // [rsp+280h] [rbp+180h] BYREF
  __int128 v174; // [rsp+290h] [rbp+190h]
  __int64 v175; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v176; // [rsp+2A8h] [rbp+1A8h]
  _BYTE v177[8]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v178[32]; // [rsp+2B8h] [rbp+1B8h] BYREF
  _BYTE v179[72]; // [rsp+2D8h] [rbp+1D8h] BYREF
  _BYTE v180[8]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v181[8]; // [rsp+328h] [rbp+228h] BYREF
  __int64 v182; // [rsp+330h] [rbp+230h] BYREF
  __int128 v183; // [rsp+340h] [rbp+240h]
  __int64 v184; // [rsp+350h] [rbp+250h]
  int v185; // [rsp+368h] [rbp+268h]
  char v186; // [rsp+370h] [rbp+270h]

  v2 = 0;
  LODWORD(v167) = 0;
  sub_1801AE334(&word_18064BE06);
  v3 = (_QWORD *)(a1 + 112);
  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 112) + 136LL))(*(_QWORD *)(a1 + 112), 570803725);
  v4 = (_QWORD *)(a1 + 176);
  v5 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 176) + 96LL))(*(_QWORD *)(a1 + 176));
  v6 = **(_QWORD **)(a1 + 176);
  if ( v5 != 13 )
  {
    if ( (*(unsigned __int8 (**)(void))(v6 + 96))() == 2 )
    {
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v3 + 136LL))(*v3, 571277974);
      return sub_1802DDCB0(a1);
    }
    v170 = 0;
    v12 = sub_1802E0240(a1 + 240, a1 + 176, a1 + 112);
    v155 = 0;
    v13 = (_QWORD *)sub_1801AD7D0(80);
    *v13 = v13;
    v13[1] = v13;
    *(_QWORD *)&v155 = v13;
    v156 = 0;
    v157 = 0;
    v158 = 7;
    v159 = 8;
    v154 = 1065353216;
    sub_18000A650(&v156, 16, v13);
    v152 = 0;
    si128 = _mm_load_si128((const __m128i *)&xmmword_18041F110);
    v153 = si128;
    LOBYTE(v152) = 0;
    LOBYTE(v15) = 1;
    sub_1802F0360((unsigned int)v177, v15, (unsigned int)&v152, (unsigned int)&v154, 0);
    if ( v153.m128i_i64[1] > 0xFuLL )
    {
      _mm_lfence();
      sub_180020E60(v152, v153.m128i_i64[1] + 1);
    }
    v153 = si128;
    LOBYTE(v152) = 0;
    if ( (_QWORD)v156 )
    {
      sub_180020E60(v156, (v157 - v156) & 0xFFFFFFFFFFFFFFF8uLL);
      v156 = 0;
      v157 = 0;
    }
    sub_1800608C0(&v155, v155);
    sub_180020E60(v155, 80);
    v172 = 0;
    sub_18020AF20(&v175);
    if ( v12 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 200LL))(*(_QWORD *)(a1 + 24)) )
      {
        v16 = v175;
        if ( v175 )
        {
          v17 = *(__int64 (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)v175 + 32LL);
          v18 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v4 + 320LL))(*v4, &v148);
          v19 = sub_180205D70(v18, &v152);
          v20 = v17(v16, v164, v19, a1 + 112);
          v177[0] = *(_BYTE *)v20;
          sub_180005BA0(v178, v20 + 8);
          sub_180069DF0(v179, v20 + 40);
          v179[64] = *(_BYTE *)(v20 + 104);
          if ( *(_BYTE *)(v20 + 192) )
          {
            if ( v186 )
            {
              v180[0] = *(_BYTE *)(v20 + 112);
              v180[1] = *(_BYTE *)(v20 + 113);
              sub_180069DF0(v181, v20 + 120);
              v185 = *(_DWORD *)(v20 + 184);
            }
            else
            {
              sub_180196300(v180, v20 + 112);
              v186 = 1;
            }
          }
          else if ( v186 )
          {
            if ( (_QWORD)v183 )
            {
              sub_180020E60(v183, (v184 - v183) & 0xFFFFFFFFFFFFFFF8uLL);
              v183 = 0;
              v184 = 0;
            }
            sub_1800608C0(&v182, v182);
            sub_180020E60(v182, 80);
            v186 = 0;
          }
          sub_18022CC50(v164);
          if ( v153.m128i_i64[1] > 0xFuLL )
          {
            _mm_lfence();
            sub_180020E60(v152, v153.m128i_i64[1] + 1);
          }
          v153 = _mm_load_si128((const __m128i *)&xmmword_18041F110);
          LOBYTE(v152) = 0;
        }
      }
    }
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 96LL))(*v4) == 1
      || (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 96LL))(*v4) == 4
      || (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 96LL))(*v4) == 3 )
    {
      if ( !v12 )
        goto LABEL_37;
      v21 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v4 + 120LL))(*v4, &v166);
      v2 = 1;
      LODWORD(v167) = 1;
      if ( !*v21 )
        goto LABEL_37;
      v22 = *(_QWORD *)(a1 + 128);
      v23 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v4 + 120LL))(*v4, &v151);
      LODWORD(v167) = 3;
      v24 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v4 + 48LL))(*v4, &v152);
      v2 = 7;
      LODWORD(v167) = 7;
      if ( (unsigned __int8)sub_180239290(v22, v24, v23) )
        v25 = 1;
      else
LABEL_37:
        v25 = 0;
      if ( (v2 & 4) != 0 )
      {
        v2 &= ~4u;
        LODWORD(v167) = v2;
        if ( v153.m128i_i64[1] > 0xFuLL )
        {
          _mm_lfence();
          sub_180020E60(v152, v153.m128i_i64[1] + 1);
        }
        v153 = _mm_load_si128((const __m128i *)&xmmword_18041F110);
        LOBYTE(v152) = 0;
      }
      if ( (v2 & 2) != 0 )
      {
        v2 &= ~2u;
        LODWORD(v167) = v2;
        if ( *((_QWORD *)&v151 + 1) )
          sub_180020BC0(*((_QWORD *)&v151 + 1));
      }
      if ( (v2 & 1) != 0 )
      {
        v2 &= ~1u;
        LODWORD(v167) = v2;
        if ( *((_QWORD *)&v166 + 1) )
          sub_180020BC0(*((_QWORD *)&v166 + 1));
      }
      if ( v25 )
      {
        v173 = 0;
        v174 = 0;
        v26 = sub_180021240(51, 15, 0x7FFFFFFFFFFFFFFFLL);
        *(_QWORD *)&v173 = sub_180003E60(v26 + 1);
        *(_QWORD *)&v174 = 51;
        *((_QWORD *)&v174 + 1) = v26;
        strcpy((char *)v173, "Interaction required due to Broker account deleted.");
        LOBYTE(v27) = 25;
        LOBYTE(v28) = 2;
        v29 = sub_180254DC0((unsigned int)&v168, 541066629, v28, v27, 0, (__int64)&v173);
        sub_1802DEF10(a1, v29);
        if ( *((_QWORD *)&v168 + 1) )
          sub_180020BC0(*((_QWORD *)&v168 + 1));
        if ( *((_QWORD *)&v174 + 1) > 0xFu )
        {
          _mm_lfence();
          sub_180020E60(v173, *((_QWORD *)&v174 + 1) + 1LL);
        }
        goto LABEL_303;
      }
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v3 + 136LL))(*v3, 571277975);
      v30 = sub_18034DF40(*(_QWORD **)(a1 + 88), &v151, v12 ^ 1u, v12);
      v31 = *v30;
      v32 = v30[1];
      *v30 = 0;
      v30[1] = 0;
      *(_QWORD *)&v170 = v31;
      v33 = *((_QWORD *)&v170 + 1);
      *((_QWORD *)&v170 + 1) = v32;
      if ( v33 )
        sub_180020BC0(v33);
      if ( *((_QWORD *)&v151 + 1) )
        sub_180020BC0(*((_QWORD *)&v151 + 1));
      if ( !v186 && v177[0] == 2 )
      {
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v3 + 136LL))(*v3, 529131079);
        v34 = v175;
        v35 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64, __int64))(*(_QWORD *)v175 + 40LL);
        v36 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v4 + 320LL))(*v4, &v148);
        v37 = sub_180205D70(v36, &v152);
        v38 = (__int64 *)v35(v34, &v151, v37, a1 + 112);
        v39 = *v38;
        v40 = v38[1];
        *v38 = 0;
        v38[1] = 0;
        *(_QWORD *)&v172 = v39;
        *((_QWORD *)&v172 + 1) = v40;
        if ( *((_QWORD *)&v151 + 1) )
          sub_180020BC0(*((_QWORD *)&v151 + 1));
        if ( v153.m128i_i64[1] > 0xFuLL )
        {
          _mm_lfence();
          sub_180020E60(v152, v153.m128i_i64[1] + 1);
        }
        if ( v39 )
        {
          v41 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v39 + 48LL))(v39, v163);
          v2 |= 8u;
        }
        else
        {
          v41 = sub_180023780(v162, byte_18041F140);
          v2 |= 0x10u;
        }
        LODWORD(v167) = v2;
        sub_1800050E0(v171, v41);
        if ( (v2 & 0x10) != 0 )
        {
          v2 &= ~0x10u;
          sub_180005740(v162);
        }
        if ( (v2 & 8) != 0 )
        {
          v2 &= ~8u;
          sub_180005740(v163);
        }
        if ( !(_QWORD)v170 )
          goto LABEL_75;
        v42 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v170 + 16LL))(v170, &v148);
        v2 |= 0x20u;
        LODWORD(v167) = v2;
        if ( *v42 )
          goto LABEL_75;
        v43 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)v170 + 24LL))(v170, v160);
        v2 |= 0x40u;
        LODWORD(v167) = v2;
        if ( !*v43
          || (v44 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v170 + 24LL))(v170, &v168),
              v45 = v2 | 0x80,
              LODWORD(v167) = v45,
              v46 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v44 + 48LL))(*v44, &v154),
              v2 = v45 | 0x100,
              v151 = *(_OWORD *)sub_180060DD0(v46, &v173),
              v166 = *(_OWORD *)sub_180060DD0(v171, &v152),
              (unsigned __int8)sub_180201310(&v166, &v151)) )
        {
LABEL_75:
          v47 = 0;
        }
        else
        {
          v47 = 1;
        }
        if ( (v2 & 0x100) != 0 )
        {
          v2 &= ~0x100u;
          sub_180005740(&v154);
        }
        if ( (v2 & 0x80u) != 0 )
        {
          v2 &= ~0x80u;
          if ( *((_QWORD *)&v168 + 1) )
            sub_180020BC0(*((_QWORD *)&v168 + 1));
        }
        if ( (v2 & 0x40) != 0 )
        {
          v2 &= ~0x40u;
          if ( v161 )
            sub_180020BC0(v161);
        }
        if ( (v2 & 0x20) != 0 )
        {
          v2 &= ~0x20u;
          if ( v149 )
            sub_180020BC0(v149);
        }
        if ( v47 )
        {
          sub_180023780(&v152, "Account is not a shared account. User data removal required.");
          LOBYTE(v48) = 14;
          v49 = sub_1802548D0((unsigned int)&v148, 537187219, v48, 0, (__int64)&v152);
          sub_1802DEF10(a1, v49);
          if ( v149 )
            sub_180020BC0(v149);
          sub_180005740(&v152);
          sub_180005740(v171);
          goto LABEL_303;
        }
        sub_180005740(v171);
      }
    }
    v50 = 0;
    if ( (_QWORD)v170 )
    {
      v2 |= 0x200u;
      if ( !*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v170 + 16LL))(v170, &v148) )
        v50 = 1;
    }
    if ( (v2 & 0x200) != 0 )
    {
      v2 &= ~0x200u;
      if ( v149 )
        sub_180020BC0(v149);
    }
    if ( v50 )
      goto LABEL_302;
    v53 = 0;
    if ( (_QWORD)v170 )
    {
      v51 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)v170 + 16LL))(v170, v160);
      v2 |= 0x400u;
      LODWORD(v167) = v2;
      if ( *v51 )
      {
        v52 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v170 + 16LL))(v170, &v148);
        v2 |= 0x800u;
        LODWORD(v167) = v2;
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v52 + 16LL))(*v52) == 13 )
          v53 = 1;
      }
    }
    if ( (v2 & 0x800) != 0 )
    {
      v2 &= ~0x800u;
      if ( v149 )
        sub_180020BC0(v149);
    }
    if ( (v2 & 0x400) != 0 )
    {
      v2 &= ~0x400u;
      if ( v161 )
        sub_180020BC0(v161);
    }
    if ( v53 )
    {
LABEL_302:
      sub_1802DEBD0(a1, &v170);
LABEL_303:
      if ( v176 )
        sub_180020BC0(v176);
      if ( *((_QWORD *)&v172 + 1) )
        sub_180020BC0(*((_QWORD *)&v172 + 1));
      result = sub_18022CC50(v177);
      v11 = *((_QWORD *)&v170 + 1);
      goto LABEL_308;
    }
    v165 = 0;
    v150 = 1;
    v169 = 0;
    if ( v12 )
    {
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v3 + 136LL))(*v3, 520495430);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 232LL))(*v3);
      v54 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v4 + 120LL))(*v4, &v148);
      v55 = *v54;
      v56 = v54[1];
      *v54 = 0;
      v54[1] = 0;
      *(_QWORD *)&v169 = v55;
      v57 = *((_QWORD *)&v169 + 1);
      *((_QWORD *)&v169 + 1) = v56;
      if ( v57 )
        sub_180020BC0(v57);
      if ( v149 )
        sub_180020BC0(v149);
      if ( (_QWORD)v169 )
      {
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v3 + 136LL))(*v3, 571277978);
        v58 = v169;
        v59 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v169 + 248LL);
        v60 = sub_180237650(*(_QWORD *)(a1 + 128), &v154, &v169, a1 + 112);
        v59(v58, v60);
        sub_180009780(&v154);
      }
      else if ( !v186 && v177[0] == 2 )
      {
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v3 + 136LL))(*v3, 541406169);
        v166 = 0;
        v70 = *(_QWORD *)(a1 + 240);
        v71 = *(void (__fastcall **)(__int64, __int128 *, __int64, __int64, _DWORD, __int64))(*(_QWORD *)v70 + 48LL);
        v72 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 200LL))(*(_QWORD *)(a1 + 24));
        v73 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v4 + 320LL))(*v4, &v152);
        v74 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v4 + 48LL))(*v4, &v154);
        LOBYTE(v147) = v72;
        v71(v70, &v166, v74, v73, v147, a1 + 112);
        sub_180005740(&v154);
        if ( !(_QWORD)v166 )
        {
          (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 112) + 136LL))(*(_QWORD *)(a1 + 112), 541173316);
          sub_180023780(v171, "Invalid readAllAccounts response");
          v75 = sub_1802548D0((unsigned int)&v148, 541173317, 0, 0, (__int64)v171);
          sub_1802DEF10(a1, v75);
          if ( v149 )
            sub_180020BC0(v149);
          sub_180005740(v171);
          goto LABEL_295;
        }
        (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v166 + 16LL))(v166, &v167);
        if ( (_QWORD)v167 )
        {
          (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 112) + 136LL))(*(_QWORD *)(a1 + 112), 541173318);
          sub_1802DEF10(a1, &v167);
          if ( *((_QWORD *)&v167 + 1) )
            sub_180020BC0(*((_QWORD *)&v167 + 1));
          goto LABEL_295;
        }
        if ( *((_QWORD *)&v167 + 1) )
          sub_180020BC0(*((_QWORD *)&v167 + 1));
        v3 = (_QWORD *)(a1 + 112);
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 112) + 136LL))(*(_QWORD *)(a1 + 112), 541173319);
        v173 = 0;
        *(_QWORD *)&v174 = 0;
        (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v166 + 8LL))(v166, &v173);
        v76 = *(_QWORD *)(a1 + 112);
        v77 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v76 + 136LL);
        if ( ((*((_QWORD *)&v173 + 1) - (_QWORD)v173) & 0xFFFFFFFFFFFFFFF0uLL) != 0x10 )
        {
          v77(v76, 541173321);
          sub_180023780(v171, "SignInSilently in shared device mode failed due to missing account");
          LOBYTE(v78) = 2;
          v79 = sub_1802548D0((unsigned int)&v148, 541173322, v78, 0, (__int64)v171);
          sub_1802DEF10(a1, v79);
          if ( v149 )
            sub_180020BC0(v149);
          sub_180005740(v171);
          sub_1800A2A00(&v173);
          goto LABEL_295;
        }
        v77(v76, 541173320);
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 112LL))(*v4, v173);
        sub_1800A2A00(&v173);
        if ( *((_QWORD *)&v166 + 1) )
          sub_180020BC0(*((_QWORD *)&v166 + 1));
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v3 + 160LL))(*v3, 546169673, 10);
      v168 = 0;
      (*(void (__fastcall **)(_QWORD, __int128 *, __int64, _QWORD *))(**(_QWORD **)(a1 + 240) + 16LL))(
        *(_QWORD *)(a1 + 240),
        &v168,
        a1 + 176,
        v3);
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v3 + 168LL))(*v3, 546169674, 10);
      if ( (_QWORD)v168 )
      {
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v3 + 136LL))(*v3, 571277979);
        v150 = (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v168 + 152LL))(v168) == 0;
        v61 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v168 + 96LL))(v168, &v148);
        v62 = *v61;
        v63 = v61[1];
        *v61 = 0;
        v61[1] = 0;
        *(_QWORD *)&v169 = v62;
        v64 = *((_QWORD *)&v169 + 1);
        *((_QWORD *)&v169 + 1) = v63;
        if ( v64 )
          sub_180020BC0(v64);
        if ( v149 )
          sub_180020BC0(v149);
        v65 = (__int64 *)sub_1802D8180(&v148, a1 + 176, v3, &v168);
        v66 = *v65;
        v67 = v65[1];
        *v65 = 0;
        v65[1] = 0;
        *(_QWORD *)&v165 = v66;
        v68 = *((_QWORD *)&v165 + 1);
        *((_QWORD *)&v165 + 1) = v67;
        if ( v68 )
          sub_180020BC0(v68);
        if ( v149 )
          sub_180020BC0(v149);
      }
      v69 = 0;
      if ( (_QWORD)v165 )
      {
        v2 |= 0x1000u;
        if ( *(_QWORD *)sub_1802ADE10(v165, &v148) )
          v69 = 1;
      }
      if ( (v2 & 0x1000) != 0 )
      {
        v2 &= ~0x1000u;
        if ( v149 )
          sub_180020BC0(v149);
      }
      if ( v69 )
      {
        v80 = *v3;
        v81 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)*v3 + 112LL);
        v82 = (_QWORD *)sub_1802ADE10(v165, &v148);
        v83 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v82 + 32LL))(*v82);
        v84 = sub_1802041E0(&v154, v83);
        sub_180023780(v171, "broker_error_location");
        v81(v80, v171, v84);
        sub_180005740(v171);
        sub_180005740(&v154);
        if ( v149 )
          sub_180020BC0(v149);
        sub_18020BA40(141);
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v4 + 424LL))(*v4, 211) )
          goto LABEL_172;
        sub_1802A31B0(520484298, v3);
        v85 = sub_18034DF40(*(_QWORD **)(a1 + 88), &v148, 1, 1);
        v86 = *v85;
        v87 = v85[1];
        *v85 = 0;
        v85[1] = 0;
        *(_QWORD *)&v170 = v86;
        v88 = *((_QWORD *)&v170 + 1);
        *((_QWORD *)&v170 + 1) = v87;
        if ( v88 )
        {
          sub_180020BC0(v88);
          v86 = v170;
        }
        if ( v149 )
        {
          sub_180020BC0(v149);
          v86 = v170;
        }
        v89 = 0;
        if ( v86 )
        {
          LOWORD(v2) = v2 | 0x2000;
          if ( !*(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v86 + 16LL))(v86, &v148) )
            v89 = 1;
        }
        if ( (v2 & 0x2000) != 0 && v149 )
          sub_180020BC0(v149);
        if ( v89 )
        {
          v90 = *v3;
          v91 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)*v3 + 8LL);
          v92 = sub_1802ADE10(v165, &v148);
          v91(v90, v92);
          if ( v149 )
            sub_180020BC0(v149);
          sub_1802A31B0(520484299, v3);
          sub_1802DEBD0(a1, &v170);
        }
        else
        {
LABEL_172:
          v93 = sub_1802ADE10(v165, &v148);
          sub_1802DEF10(a1, v93);
          if ( v149 )
            sub_180020BC0(v149);
        }
        v94 = *((_QWORD *)&v168 + 1);
        goto LABEL_296;
      }
      v95 = *((_QWORD *)&v168 + 1);
    }
    else
    {
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 96LL))(*v4) == 4 )
        sub_1802CF6D0((_QWORD *)(a1 + 112), (_QWORD *)(a1 + 176), (_QWORD *)(a1 + 72));
      v166 = 0;
      sub_1802A0650(*(_QWORD *)(a1 + 160), &v166, a1 + 176);
      if ( (_QWORD)v166 )
        goto LABEL_217;
      switch ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 96LL))(*v4) )
      {
        case 1u:
          (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v3 + 136LL))(*v3, 571277980);
          sub_1802145C0(
            4,
            607,
            (unsigned int)"Execute",
            (unsigned int)"Attempt to acquire a token via refresh token failed");
          goto LABEL_196;
        case 3u:
          v97 = (__int64 *)sub_1802D5630((unsigned int)&v148, (int)a1 + 112, (int)a1 + 176, (int)a1 + 208, a1 + 56);
          goto LABEL_192;
        case 4u:
          v97 = (__int64 *)sub_1802D5FA0(&v148, a1 + 112, a1 + 176, a1 + 56);
          goto LABEL_192;
        case 5u:
          v97 = (__int64 *)sub_1802D8F40(a1, &v148);
          goto LABEL_192;
        case 7u:
          v97 = (__int64 *)sub_1802D9A70(a1, &v148);
          goto LABEL_192;
        case 9u:
          if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 256) + 152LL))(*(_QWORD *)(a1 + 256)) )
          {
            v150 = 0;
            v98 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 256) + 96LL))(
                               *(_QWORD *)(a1 + 256),
                               &v148);
            v99 = *v98;
            v100 = v98[1];
            *v98 = 0;
            v98[1] = 0;
            *(_QWORD *)&v169 = v99;
            v101 = *((_QWORD *)&v169 + 1);
            *((_QWORD *)&v169 + 1) = v100;
            if ( v101 )
              sub_180020BC0(v101);
            if ( v149 )
              sub_180020BC0(v149);
          }
          v97 = (__int64 *)sub_1802D8180(&v148, a1 + 176, a1 + 112, a1 + 256);
LABEL_192:
          v102 = *v97;
          v103 = v97[1];
          *v97 = 0;
          v97[1] = 0;
          *(_QWORD *)&v165 = v102;
          v104 = *((_QWORD *)&v165 + 1);
          *((_QWORD *)&v165 + 1) = v103;
          if ( v104 )
            sub_180020BC0(v104);
          if ( v149 )
            sub_180020BC0(v149);
LABEL_196:
          v95 = *((_QWORD *)&v166 + 1);
          break;
        default:
          v144 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v4 + 96LL))(*v4, v96);
          v145 = sub_180144880(&v154, "Background request called with invalid type: %d", v144);
          v146 = sub_1802548D0((unsigned int)&v148, 593819476, 0, 0, v145);
          sub_1802DEF10(a1, v146);
          if ( v149 )
            sub_180020BC0(v149);
          sub_180005740(&v154);
          goto LABEL_295;
      }
    }
    if ( v95 )
      sub_180020BC0(v95);
    v105 = 0;
    if ( (_QWORD)v165 )
    {
      v2 |= 0x4000u;
      if ( !*(_QWORD *)sub_1802ADE10(v165, &v148) )
        v105 = 1;
    }
    if ( (v2 & 0x4000) != 0 )
    {
      v2 &= ~0x4000u;
      if ( v149 )
        sub_180020BC0(v149);
    }
    if ( v105 )
    {
      v167 = 0;
      sub_1802DAF00(a1, &v167, &v165);
      if ( (_QWORD)v167 )
      {
        sub_1802DEF10(a1, &v167);
        v94 = *((_QWORD *)&v167 + 1);
        goto LABEL_296;
      }
      if ( *((_QWORD *)&v167 + 1) )
        sub_180020BC0(*((_QWORD *)&v167 + 1));
      v166 = 0;
      sub_1802D9C50(a1, &v166, &v165);
      v107 = v166;
      v109 = 0;
      if ( (_QWORD)v166 )
      {
        v108 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v166 + 16LL))(v166);
        v107 = v166;
        if ( v108 == 18 )
          v109 = 1;
      }
      if ( !v107 || v109 )
      {
        v168 = 0;
        if ( v150 )
        {
          LOBYTE(v106) = 1;
          v110 = (__int64 *)sub_18034A060(*(_QWORD *)(a1 + 88), &v148, &v165, v106);
          v111 = *v110;
          v112 = v110[1];
          *v110 = 0;
          v110[1] = 0;
          *(_QWORD *)&v168 = v111;
          v113 = *((_QWORD *)&v168 + 1);
          *((_QWORD *)&v168 + 1) = v112;
          if ( v113 )
            sub_180020BC0(v113);
          v114 = v149;
        }
        else
        {
          v115 = sub_1801AD7D0(496);
          v116 = v115;
          *(_QWORD *)&v167 = v115;
          if ( v115 )
          {
            *(_OWORD *)v115 = 0;
            *(_DWORD *)(v115 + 8) = 1;
            *(_DWORD *)(v115 + 12) = 1;
            *(_QWORD *)v115 = &std::_Ref_count_obj2<Msai::AuthenticationResultInternalImpl>::`vftable';
            sub_1802C8690(v115 + 16, (unsigned int)&v165, (unsigned int)&v169, a1 + 176, (__int64)v3);
          }
          else
          {
            v116 = 0;
          }
          *(_QWORD *)&v168 = v116 + 16;
          v114 = *((_QWORD *)&v168 + 1);
          *((_QWORD *)&v168 + 1) = v116;
        }
        if ( v114 )
          sub_180020BC0(v114);
        v117 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v4 + 400LL))(*v4, &v154);
        sub_180023780(v171, "IgnoreSignOut");
        v118 = sub_180060840(v117, v171);
        v119 = *(_QWORD *)(sub_180007DE0(v117, &v152, v171, v118) + 8);
        sub_180005740(v171);
        sub_180009780(&v154);
        if ( !v119 )
        {
          v120 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v168 + 24LL))(v168, &v148);
          sub_1802DB4B0(a1, v120);
          if ( v149 )
            sub_180020BC0(v149);
        }
        if ( v109 )
        {
          v121 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v168 + 24LL))(v168, &v148);
          v122 = sub_1801AD7D0(496);
          v123 = v122;
          *(_QWORD *)&v167 = v122;
          if ( v122 )
          {
            *(_OWORD *)v122 = 0;
            *(_DWORD *)(v122 + 8) = 1;
            *(_DWORD *)(v122 + 12) = 1;
            *(_QWORD *)v122 = &std::_Ref_count_obj2<Msai::AuthenticationResultInternalImpl>::`vftable';
            sub_1802C9290(v122 + 16, &v166, v121);
          }
          else
          {
            v123 = 0;
          }
          *(_QWORD *)&v167 = v123 + 16;
          *((_QWORD *)&v167 + 1) = v123;
          sub_18026A700(&v151, &v167);
          sub_1802DEBD0(a1, &v151);
          if ( *((_QWORD *)&v151 + 1) )
            sub_180020BC0(*((_QWORD *)&v151 + 1));
          if ( *((_QWORD *)&v167 + 1) )
            sub_180020BC0(*((_QWORD *)&v167 + 1));
          if ( v149 )
            sub_180020BC0(v149);
        }
        else
        {
          sub_1802DEBD0(a1, &v168);
        }
        if ( *((_QWORD *)&v168 + 1) )
          sub_180020BC0(*((_QWORD *)&v168 + 1));
        goto LABEL_295;
      }
LABEL_217:
      sub_1802DEF10(a1, &v166);
LABEL_295:
      v94 = *((_QWORD *)&v166 + 1);
LABEL_296:
      if ( v94 )
        sub_180020BC0(v94);
      goto LABEL_298;
    }
    v124 = 0;
    if ( (_QWORD)v170 )
    {
      v2 |= 0x8000u;
      if ( *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v170 + 16LL))(v170, &v148) )
        v124 = 1;
    }
    if ( (v2 & 0x8000) != 0 )
    {
      v2 &= ~0x8000u;
      if ( v149 )
        sub_180020BC0(v149);
    }
    if ( v124 )
    {
      sub_1802DEBD0(a1, &v170);
LABEL_298:
      if ( *((_QWORD *)&v169 + 1) )
        sub_180020BC0(*((_QWORD *)&v169 + 1));
      if ( *((_QWORD *)&v165 + 1) )
        sub_180020BC0(*((_QWORD *)&v165 + 1));
      goto LABEL_303;
    }
    v125 = 0;
    if ( (_QWORD)v165 )
    {
      v2 |= 0x10000u;
      if ( *(_QWORD *)sub_1802ADE10(v165, &v148) )
        v125 = 1;
    }
    if ( (v2 & 0x10000) != 0 && v149 )
      sub_180020BC0(v149);
    if ( !v125 )
    {
      LODWORD(v147) = (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 96LL))(*v4);
      sub_1802145C0(
        1,
        748,
        (unsigned int)"Execute",
        (unsigned int)"AuthorizationType %d failed in a non-critical way, and we didn't attempt to read from cache.",
        v147);
      v138 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v4 + 120LL))(*v4, &v148);
      if ( v149 )
        sub_180020BC0(v149);
      if ( v138 )
      {
        sub_180023780(v171, "No Home Account ID available for us to read the cache");
        LOBYTE(v142) = 2;
        v143 = sub_1802548D0((unsigned int)&v148, 591716636, v142, 0, (__int64)v171);
        sub_1802DEF10(a1, v143);
        if ( v149 )
          sub_180020BC0(v149);
      }
      else
      {
        sub_180023780(v171, "Default account could not be found");
        LOBYTE(v139) = 30;
        LOBYTE(v140) = 2;
        v141 = sub_180254DC0((unsigned int)&v148, 527512645, v140, v139, 0, (__int64)v171);
        sub_1802DEF10(a1, v141);
        if ( v149 )
          sub_180020BC0(v149);
      }
      sub_180005740(v171);
      goto LABEL_298;
    }
    v166 = 0;
    sub_1802ADE10(v165, &v166);
    if ( (unsigned __int8)sub_18020BA40(104)
      && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v166 + 16LL))(v166) == 12 )
    {
      v168 = 0;
      LOBYTE(v126) = 1;
      sub_18034A060(*(_QWORD *)(a1 + 88), &v168, &v165, v126);
      v127 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v168 + 24LL))(v168, &v148);
      sub_1802DB4B0(a1, v127);
      if ( v149 )
        sub_180020BC0(v149);
      sub_1802DEBD0(a1, &v168);
      v128 = *((_QWORD *)&v168 + 1);
    }
    else
    {
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v166 + 80LL))(v166) != 18 )
        goto LABEL_217;
      v129 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v4 + 120LL))(*v4, &v148);
      v130 = *v129;
      v131 = v129[1];
      *v129 = 0;
      v129[1] = 0;
      *(_QWORD *)&v169 = v130;
      v132 = *((_QWORD *)&v169 + 1);
      *((_QWORD *)&v169 + 1) = v131;
      if ( v132 )
        sub_180020BC0(v132);
      if ( v149 )
        sub_180020BC0(v149);
      if ( !(_QWORD)v169 )
      {
        v133 = (__int64 *)sub_1802DB5A0(a1, &v148, &v165);
        v134 = *v133;
        v135 = v133[1];
        *v133 = 0;
        v133[1] = 0;
        *(_QWORD *)&v169 = v134;
        v136 = *((_QWORD *)&v169 + 1);
        *((_QWORD *)&v169 + 1) = v135;
        if ( v136 )
          sub_180020BC0(v136);
        if ( v149 )
          sub_180020BC0(v149);
      }
      sub_1802DB4B0(a1, &v169);
      v137 = sub_1802D8240(&v148, &v166, &v169);
      sub_18026A700(&v151, v137);
      sub_1802DEBD0(a1, &v151);
      if ( *((_QWORD *)&v151 + 1) )
        sub_180020BC0(*((_QWORD *)&v151 + 1));
      v128 = v149;
    }
    if ( v128 )
      sub_180020BC0(v128);
    goto LABEL_295;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(v6 + 120))(*(_QWORD *)(a1 + 176), &v151);
  v8 = sub_1801AD7D0(496);
  v9 = v8;
  *(_QWORD *)&v167 = v8;
  if ( v8 )
  {
    *(_OWORD *)v8 = 0;
    *(_DWORD *)(v8 + 8) = 1;
    *(_DWORD *)(v8 + 12) = 1;
    *(_QWORD *)v8 = &std::_Ref_count_obj2<Msai::AuthenticationResultInternalImpl>::`vftable';
    v166 = 0;
    sub_1802C9290(v8 + 16, &v166, v7);
    if ( *((_QWORD *)&v166 + 1) )
      sub_180020BC0(*((_QWORD *)&v166 + 1));
  }
  else
  {
    v9 = 0;
  }
  *(_QWORD *)&v172 = v9 + 16;
  *((_QWORD *)&v172 + 1) = v9;
  if ( *((_QWORD *)&v151 + 1) )
    sub_180020BC0(*((_QWORD *)&v151 + 1));
  result = sub_1802DEBD0(a1, &v172);
  v11 = *((_QWORD *)&v172 + 1);
LABEL_308:
  if ( v11 )
    return sub_180020BC0(v11);
  return result;
}

```

## disassembly

```asm
0x1802dbef0  mov     [rsp-8+arg_8], rbx
0x1802dbef5  mov     [rsp-8+arg_10], rsi
0x1802dbefa  mov     [rsp-8+arg_18], rdi
0x1802dbeff  push    rbp
0x1802dbf00  push    r12
0x1802dbf02  push    r13
0x1802dbf04  push    r14
0x1802dbf06  push    r15
0x1802dbf08  lea     rbp, [rsp-2A0h]
0x1802dbf10  mov     eax, 3A0h
0x1802dbf15  call    __alloca_probe
0x1802dbf1a  sub     rsp, rax
0x1802dbf1d  movaps  [rsp+3C0h+var_30], xmm6
0x1802dbf25  mov     rax, cs:__security_cookie
0x1802dbf2c  xor     rax, rsp
0x1802dbf2f  mov     [rbp+2C0h+var_40], rax
0x1802dbf36  mov     r13, rcx
0x1802dbf39  xor     edi, edi
0x1802dbf3b  mov     r15d, edi
0x1802dbf3e  mov     dword ptr [rbp+2C0h+var_1B0], edi
0x1802dbf44  lea     rcx, word_18064BE06
0x1802dbf4b  call    sub_1801AE334
0x1802dbf50  lea     r14, [r13+70h]
0x1802dbf54  mov     rcx, [r14]
0x1802dbf57  mov     rax, [rcx]
0x1802dbf5a  mov     edx, 2205C60Dh
0x1802dbf5f  mov     rax, [rax+88h]
0x1802dbf66  call    cs:__guard_dispatch_icall_fptr
0x1802dbf6c  lea     r12, [r13+0B0h]
0x1802dbf73  mov     rcx, [r12]
0x1802dbf77  mov     rax, [rcx]
0x1802dbf7a  mov     rax, [rax+60h]
0x1802dbf7e  call    cs:__guard_dispatch_icall_fptr
0x1802dbf84  mov     rcx, [r12]
0x1802dbf88  mov     r8, [rcx]
0x1802dbf8b  cmp     al, 0Dh
0x1802dbf8d  jnz     loc_1802DC04B
0x1802dbf93  lea     rdx, [rsp+3C0h+var_360]
0x1802dbf98  mov     rax, [r8+78h]
0x1802dbf9c  call    cs:__guard_dispatch_icall_fptr
0x1802dbfa2  mov     rsi, rax
0x1802dbfa5  mov     ecx, 1F0h
0x1802dbfaa  call    sub_1801AD7D0
0x1802dbfaf  mov     rbx, rax
0x1802dbfb2  mov     qword ptr [rbp+2C0h+var_1B0], rax
0x1802dbfb9  test    rax, rax
0x1802dbfbc  jz      short loc_1802DC00C
0x1802dbfbe  xorps   xmm0, xmm0
0x1802dbfc1  movups  xmmword ptr [rax], xmm0
0x1802dbfc4  mov     dword ptr [rax+8], 1
0x1802dbfcb  mov     dword ptr [rax+0Ch], 1
0x1802dbfd2  lea     rdi, ??_7?$_Ref_count_obj2@VAuthenticationResultInternalImpl@Msai@@@std@@6B@; const std::_Ref_count_obj2<Msai::AuthenticationResultInternalImpl>::`vftable'
0x1802dbfd9  mov     [rax], rdi
0x1802dbfdc  lea     rcx, [rax+10h]
0x1802dbfe0  movdqu  [rbp+2C0h+var_1C0], xmm0
0x1802dbfe8  mov     r8, rsi
0x1802dbfeb  lea     rdx, [rbp+2C0h+var_1C0]
0x1802dbff2  call    sub_1802C9290
0x1802dbff7  nop
0x1802dbff8  mov     rcx, qword ptr [rbp+2C0h+var_1C0+8]
0x1802dbfff  test    rcx, rcx
0x1802dc002  jz      short loc_1802DC00A
0x1802dc004  call    sub_180020BC0
0x1802dc009  nop
0x1802dc00a  jmp     short loc_1802DC00F
0x1802dc00c  mov     rbx, rdi
0x1802dc00f  lea     rax, [rbx+10h]
0x1802dc013  mov     qword ptr [rbp+2C0h+var_150], rax
0x1802dc01a  mov     qword ptr [rbp+2C0h+var_150+8], rbx
0x1802dc021  mov     rcx, qword ptr [rsp+3C0h+var_360+8]
0x1802dc026  test    rcx, rcx
0x1802dc029  jz      short loc_1802DC030
0x1802dc02b  call    sub_180020BC0
0x1802dc030  lea     rdx, [rbp+2C0h+var_150]
0x1802dc037  mov     rcx, r13
0x1802dc03a  call    sub_1802DEBD0
0x1802dc03f  mov     rcx, qword ptr [rbp+2C0h+var_150+8]
0x1802dc046  jmp     loc_1802DDC25
0x1802dc04b  mov     rax, [r8+60h]
0x1802dc04f  call    cs:__guard_dispatch_icall_fptr
0x1802dc055  cmp     al, 2
0x1802dc057  jnz     short loc_1802DC07E
0x1802dc059  mov     rcx, [r14]
0x1802dc05c  mov     rax, [rcx]
0x1802dc05f  mov     edx, 220D0296h
0x1802dc064  mov     rax, [rax+88h]
0x1802dc06b  call    cs:__guard_dispatch_icall_fptr
0x1802dc071  mov     rcx, r13
0x1802dc074  call    sub_1802DDCB0
0x1802dc079  jmp     loc_1802DDC2F
0x1802dc07e  xorps   xmm1, xmm1
0x1802dc081  movdqu  [rbp+2C0h+var_180], xmm1
0x1802dc089  lea     rcx, [r13+0F0h]
0x1802dc090  mov     r8, r14
0x1802dc093  mov     rdx, r12
0x1802dc096  call    sub_1802E0240
0x1802dc09b  movzx   esi, al
0x1802dc09e  mov     [rbp+2C0h+var_330], 0
0x1802dc0a5  xorps   xmm1, xmm1
0x1802dc0a8  movdqu  [rbp+2C0h+var_328], xmm1
0x1802dc0ad  mov     ecx, 50h ; 'P'
0x1802dc0b2  call    sub_1801AD7D0
0x1802dc0b7  mov     [rax], rax
0x1802dc0ba  mov     [rax+8], rax
0x1802dc0be  mov     qword ptr [rbp+2C0h+var_328], rax
0x1802dc0c2  xorps   xmm0, xmm0
0x1802dc0c5  movdqu  [rbp+2C0h+var_318], xmm0
0x1802dc0ca  mov     [rbp+2C0h+var_308], rdi
0x1802dc0ce  mov     [rbp+2C0h+var_300], 7
0x1802dc0d6  mov     [rbp+2C0h+var_2F8], 8
0x1802dc0de  mov     [rbp+2C0h+var_330], 3F800000h
0x1802dc0e5  mov     r8, rax
0x1802dc0e8  mov     edx, 10h
0x1802dc0ed  lea     rcx, [rbp+2C0h+var_318]
0x1802dc0f1  call    sub_18000A650
0x1802dc0f6  nop
0x1802dc0f7  xorps   xmm0, xmm0
0x1802dc0fa  movups  [rsp+3C0h+var_350], xmm0
0x1802dc0ff  movdqa  xmm6, cs:xmmword_18041F110
0x1802dc107  movdqu  [rbp+2C0h+var_340], xmm6
0x1802dc10c  mov     byte ptr [rsp+3C0h+var_350], 0
0x1802dc111  mov     byte ptr [rsp+3C0h+var_3A0], 0
0x1802dc116  lea     r9, [rbp+2C0h+var_330]
0x1802dc11a  lea     r8, [rsp+3C0h+var_350]
0x1802dc11f  mov     dl, 1
0x1802dc121  lea     rcx, [rbp+2C0h+var_110]
0x1802dc128  call    sub_1802F0360
0x1802dc12d  nop
0x1802dc12e  cmp     qword ptr [rbp+2C0h+var_340+8], 0Fh
0x1802dc133  jbe     short loc_1802DC149
0x1802dc135  lfence
0x1802dc138  mov     rdx, qword ptr [rbp+2C0h+var_340+8]
0x1802dc13c  inc     rdx
0x1802dc13f  mov     rcx, qword ptr [rsp+3C0h+var_350]
0x1802dc144  call    sub_180020E60
0x1802dc149  movdqu  [rbp+2C0h+var_340], xmm6
0x1802dc14e  mov     byte ptr [rsp+3C0h+var_350], 0
0x1802dc153  mov     rcx, qword ptr [rbp+2C0h+var_318]
0x1802dc157  test    rcx, rcx
0x1802dc15a  jz      short loc_1802DC178
0x1802dc15c  mov     rdx, [rbp+2C0h+var_308]
0x1802dc160  sub     rdx, rcx
0x1802dc163  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1802dc167  call    sub_180020E60
0x1802dc16c  xorps   xmm0, xmm0
0x1802dc16f  movdqu  [rbp+2C0h+var_318], xmm0
0x1802dc174  mov     [rbp+2C0h+var_308], rdi
0x1802dc178  mov     rdx, qword ptr [rbp+2C0h+var_328]
0x1802dc17c  lea     rcx, [rbp+2C0h+var_328]
0x1802dc180  call    sub_1800608C0
0x1802dc185  mov     edx, 50h ; 'P'
0x1802dc18a  mov     rcx, qword ptr [rbp+2C0h+var_328]
0x1802dc18e  call    sub_180020E60
0x1802dc193  xorps   xmm1, xmm1
0x1802dc196  movdqu  [rbp+2C0h+var_150], xmm1
0x1802dc19e  lea     rcx, [rbp+2C0h+var_120]
0x1802dc1a5  call    sub_18020AF20
0x1802dc1aa  nop
0x1802dc1ab  test    sil, sil
0x1802dc1ae  jz      loc_1802DC35A
0x1802dc1b4  mov     rcx, [r13+18h]
0x1802dc1b8  mov     rax, [rcx]
0x1802dc1bb  mov     rax, [rax+0C8h]
0x1802dc1c2  call    cs:__guard_dispatch_icall_fptr
0x1802dc1c8  test    al, al
0x1802dc1ca  jz      loc_1802DC35A
0x1802dc1d0  mov     rdi, [rbp+2C0h+var_120]
0x1802dc1d7  test    rdi, rdi
0x1802dc1da  jz      loc_1802DC35A
0x1802dc1e0  mov     rax, [rdi]
0x1802dc1e3  mov     rbx, [rax+20h]
0x1802dc1e7  mov     rcx, [r12]
0x1802dc1eb  mov     rax, [rcx]
0x1802dc1ee  lea     rdx, [rsp+3C0h+var_380]
0x1802dc1f3  mov     rax, [rax+140h]
0x1802dc1fa  call    cs:__guard_dispatch_icall_fptr
0x1802dc200  lea     rdx, [rsp+3C0h+var_350]
0x1802dc205  mov     rcx, rax
0x1802dc208  call    sub_180205D70
0x1802dc20d  nop
0x1802dc20e  mov     r9, r14
0x1802dc211  mov     r8, rax
0x1802dc214  lea     rdx, [rbp+2C0h+var_2A0]
0x1802dc218  mov     rcx, rdi
0x1802dc21b  mov     rax, rbx
0x1802dc21e  call    cs:__guard_dispatch_icall_fptr
0x1802dc224  mov     rbx, rax
0x1802dc227  movzx   ecx, byte ptr [rax]
0x1802dc22a  mov     [rbp+2C0h+var_110], cl
0x1802dc230  lea     rdx, [rax+8]
0x1802dc234  lea     rcx, [rbp+2C0h+var_108]
0x1802dc23b  call    sub_180005BA0
0x1802dc240  lea     rdx, [rbx+28h]
0x1802dc244  lea     rcx, [rbp+2C0h+var_E8]
0x1802dc24b  call    sub_180069DF0
0x1802dc250  movzx   ecx, byte ptr [rbx+68h]
0x1802dc254  mov     [rbp+2C0h+var_A8], cl
0x1802dc25a  cmp     byte ptr [rbx+0C0h], 0
0x1802dc261  jz      short loc_1802DC2BA
0x1802dc263  cmp     [rbp+2C0h+var_50], 0
0x1802dc26a  jz      short loc_1802DC2A1
0x1802dc26c  movzx   eax, byte ptr [rbx+70h]
0x1802dc270  mov     [rbp+2C0h+var_A0], al
0x1802dc276  movzx   eax, byte ptr [rbx+71h]
0x1802dc27a  mov     [rbp+2C0h+var_9F], al
0x1802dc280  lea     rdx, [rbx+78h]
0x1802dc284  lea     rcx, [rbp+2C0h+var_98]
0x1802dc28b  call    sub_180069DF0
0x1802dc290  mov     eax, [rbx+0B8h]
0x1802dc296  mov     [rbp+2C0h+var_58], eax
0x1802dc29c  jmp     loc_1802DC323
0x1802dc2a1  lea     rdx, [rbx+70h]
0x1802dc2a5  lea     rcx, [rbp+2C0h+var_A0]
0x1802dc2ac  call    sub_180196300
0x1802dc2b1  mov     [rbp+2C0h+var_50], 1
0x1802dc2b8  jmp     short loc_1802DC323
0x1802dc2ba  cmp     [rbp+2C0h+var_50], 0
0x1802dc2c1  jz      short loc_1802DC323
0x1802dc2c3  mov     rcx, qword ptr [rbp+2C0h+var_80]
0x1802dc2ca  test    rcx, rcx
0x1802dc2cd  jz      short loc_1802DC2F8
0x1802dc2cf  mov     rdx, [rbp+2C0h+var_70]
0x1802dc2d6  sub     rdx, rcx
0x1802dc2d9  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1802dc2dd  call    sub_180020E60
0x1802dc2e2  xorps   xmm0, xmm0
0x1802dc2e5  movdqa  [rbp+2C0h+var_80], xmm0
0x1802dc2ed  mov     [rbp+2C0h+var_70], 0
0x1802dc2f8  mov     rdx, [rbp+2C0h+var_90]
0x1802dc2ff  lea     rcx, [rbp+2C0h+var_90]
0x1802dc306  call    sub_1800608C0
0x1802dc30b  mov     edx, 50h ; 'P'
0x1802dc310  mov     rcx, [rbp+2C0h+var_90]
0x1802dc317  call    sub_180020E60
0x1802dc31c  mov     [rbp+2C0h+var_50], 0
0x1802dc323  lea     rcx, [rbp+2C0h+var_2A0]
0x1802dc327  call    sub_18022CC50
0x1802dc32c  nop
0x1802dc32d  cmp     qword ptr [rbp+2C0h+var_340+8], 0Fh
0x1802dc332  jbe     short loc_1802DC348
0x1802dc334  lfence
0x1802dc337  mov     rdx, qword ptr [rbp+2C0h+var_340+8]
0x1802dc33b  inc     rdx
0x1802dc33e  mov     rcx, qword ptr [rsp+3C0h+var_350]
0x1802dc343  call    sub_180020E60
0x1802dc348  movdqa  xmm0, cs:xmmword_18041F110
0x1802dc350  movdqu  [rbp+2C0h+var_340], xmm0
0x1802dc355  mov     byte ptr [rsp+3C0h+var_350], 0
0x1802dc35a  mov     rcx, [r12]
0x1802dc35e  mov     rax, [rcx]
0x1802dc361  mov     rax, [rax+60h]
0x1802dc365  call    cs:__guard_dispatch_icall_fptr
0x1802dc36b  cmp     al, 1
0x1802dc36d  jz      short loc_1802DC39D
0x1802dc36f  mov     rcx, [r12]
0x1802dc373  mov     rax, [rcx]
0x1802dc376  mov     rax, [rax+60h]
0x1802dc37a  call    cs:__guard_dispatch_icall_fptr
0x1802dc380  cmp     al, 4
0x1802dc382  jz      short loc_1802DC39D
0x1802dc384  mov     rcx, [r12]
0x1802dc388  mov     rax, [rcx]
0x1802dc38b  mov     rax, [rax+60h]
0x1802dc38f  call    cs:__guard_dispatch_icall_fptr
0x1802dc395  cmp     al, 3
0x1802dc397  jnz     loc_1802DC93E
0x1802dc39d  test    sil, sil
0x1802dc3a0  jz      loc_1802DC433
0x1802dc3a6  mov     rcx, [r12]
0x1802dc3aa  mov     rax, [rcx]
0x1802dc3ad  lea     rdx, [rbp+2C0h+var_1C0]
0x1802dc3b4  mov     rax, [rax+78h]
0x1802dc3b8  call    cs:__guard_dispatch_icall_fptr
0x1802dc3be  nop
0x1802dc3bf  or      r15d, 1
0x1802dc3c3  mov     dword ptr [rbp+2C0h+var_1B0], r15d
0x1802dc3ca  cmp     qword ptr [rax], 0
0x1802dc3ce  jz      short loc_1802DC433
0x1802dc3d0  mov     rdi, [r13+80h]
0x1802dc3d7  mov     rcx, [r12]
0x1802dc3db  mov     rax, [rcx]
0x1802dc3de  lea     rdx, [rsp+3C0h+var_360]
0x1802dc3e3  mov     rax, [rax+78h]
0x1802dc3e7  call    cs:__guard_dispatch_icall_fptr
0x1802dc3ed  mov     rbx, rax
0x1802dc3f0  or      r15d, 2
0x1802dc3f4  mov     dword ptr [rbp+2C0h+var_1B0], r15d
0x1802dc3fb  mov     rcx, [r12]
0x1802dc3ff  mov     rdx, [rcx]
0x1802dc402  mov     rax, [rdx+30h]
0x1802dc406  lea     rdx, [rsp+3C0h+var_350]
0x1802dc40b  call    cs:__guard_dispatch_icall_fptr
0x1802dc411  nop
0x1802dc412  or      r15d, 4
0x1802dc416  mov     dword ptr [rbp+2C0h+var_1B0], r15d
0x1802dc41d  mov     r8, rbx
0x1802dc420  mov     rdx, rax
0x1802dc423  mov     rcx, rdi
0x1802dc426  call    sub_180239290
0x1802dc42b  test    al, al
  ... truncated ...
```
