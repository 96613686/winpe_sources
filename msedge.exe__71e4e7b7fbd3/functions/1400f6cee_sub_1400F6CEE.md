# sub_1400F6CEE

- ea: `0x1400f6cee`
- end: `0x1400f761d`
- name: `sub_1400F6CEE`
- size: `2351`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `29`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400f5602`
- `0x1403160b8`

## callees

- `0x1400f5e05`
- `0x1400f6cee`
- `0x1400f761d`
- `0x1400f7634`
- `0x1400f76a2`
- `0x1400f7723`
- `0x1400f779e`
- `0x1400f77e8`
- `0x1400f7851`
- `0x1400f79ce`
- `0x1400f7e7c`
- `0x1400f81f0`
- `0x1400f8275`
- `0x1400f8304`
- `0x1400f8515`
- `0x1400f89ce`
- `0x14011fa70`
- `0x140152400`
- `0x140152ce0`
- `0x1402fcaec`
- `0x14030c437`
- `0x14030c59a`
- `0x14030c9a2`
- `0x14030d4bd`
- `0x140314c8e`
- `0x140315621`
- `0x140318d44`
- `0x140318f91`
- `0x1403297fe`

## string_xrefs

- `0x1401b09c6`: `http://www.w3.org/2000/xmlns/`
- `0x1401b0a1b`: `http://www.w3.org/2000/xmlns/`
- `0x1401b04c5`: `Malformed value for xml:lang : %s\n`
- `0x1401b066e`: `Invalid value "%s" for xml:space : "default" or "preserve" expected\n`
- `0x1401b0b20`: `xmlns: '%s' is not a valid URI\n`
- `0x1401b0ac2`: `xmlns: URI %s is not absolute\n`
- `0x1401b090c`: `xml namespace URI cannot be the default namespace\n`
- `0x1401b0a47`: `reuse of the xmlns namespace name is forbidden\n`
- `0x1401b08e5`: `xml namespace prefix mapped to wrong URI\n`
- `0x1401b09f4`: `xml namespace URI mapped to wrong prefix\n`
- `0x1401b0a12`: `redefinition of the xmlns prefix is forbidden\n`
- `0x1401b0a99`: `xmlns:%s: Empty XML namespace is not allowed\n`
- `0x1401b0caa`: `xmlns:%s: '%s' is not a valid URI\n`
- `0x1401b0c34`: `xmlns:%s: URI %s is not absolute\n`

## pseudocode

```c
void *__fastcall sub_1400F6CEE(__int64 a1, __int64 a2, unsigned __int64 *a3, _QWORD *a4)
{
  unsigned __int64 v4; // rdi
  void *v5; // r13
  __int64 v6; // r15
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // ecx
  __int64 v11; // rax
  __int64 v12; // rdi
  unsigned __int64 v13; // rbp
  __int64 v14; // rcx
  unsigned __int8 *v15; // rax
  _QWORD *v16; // rdx
  unsigned __int64 v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // r14
  __int64 v20; // rcx
  __int64 v21; // rax
  _BYTE *v22; // r9
  int v23; // edx
  __int64 v24; // r13
  unsigned int v25; // r14d
  __int64 v26; // rax
  int v27; // r12d
  int v28; // eax
  __int64 v29; // rax
  unsigned __int8 *v30; // rax
  int v31; // ecx
  __int64 v32; // rax
  __int64 v33; // rdx
  void *v34; // r14
  int v35; // ecx
  void *v36; // rcx
  size_t v37; // rbx
  __int64 v38; // rcx
  int v39; // r12d
  int v40; // ebx
  void *v41; // r14
  int v42; // eax
  __int64 v43; // r12
  unsigned int v44; // eax
  unsigned int v45; // ecx
  __int64 v46; // rax
  __int64 v47; // r12
  __int64 v48; // r13
  int v49; // ebp
  void *v50; // rbx
  __int64 v51; // r14
  __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // r15
  int v55; // eax
  unsigned int v56; // eax
  __int64 v57; // rcx
  int v58; // r10d
  int v59; // eax
  int v60; // ecx
  __int64 v61; // rdx
  int v62; // r8d
  __int64 v63; // r8
  int v64; // eax
  void *v65; // r8
  _BYTE *v66; // rax
  void (__fastcall *v67)(__int64, void *, void *, unsigned __int64, int, _QWORD, _DWORD, _DWORD, _QWORD); // rax
  __int64 v68; // rcx
  __int64 v70; // r10
  int v71; // eax
  __int64 v72; // rdx
  _BYTE *v73; // r12
  void *v74; // rax
  __int64 v75; // rbp
  signed int v76; // r12d
  void *v77; // rbx
  __int64 v78; // r13
  unsigned int v79; // r14d
  unsigned int v80; // eax
  __int64 v81; // rax
  unsigned int *v82; // rcx
  unsigned int v83; // r9d
  __int64 v84; // r8
  int *v85; // rbx
  unsigned __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rcx
  unsigned __int64 v89; // r14
  int *v90; // rax
  int *v91; // rdi
  int v92; // ebx
  _QWORD *v93; // r14
  int v94; // eax
  int v95; // eax
  __int64 *v96; // rcx
  __int64 v97; // r15
  int v98; // eax
  unsigned int v99; // eax
  unsigned __int64 v100; // r14
  unsigned int *v101; // rbx
  unsigned __int64 v102; // rax
  unsigned __int64 v103; // rdx
  unsigned __int64 v104; // rax
  int *v105; // rax
  int *v106; // r12
  _BYTE *v107; // r14
  int v108; // r12d
  unsigned int v109; // eax
  void *v110; // r13
  int v111; // r12d
  void *v112; // r14
  __int64 v113; // rax
  __int64 v114; // rax
  __int128 v115; // xmm0
  const char *v116; // rcx
  __int128 v117; // xmm0
  const char *v118; // rcx
  __int64 v119; // rcx
  __int64 v120; // [rsp+0h] [rbp-1A8h] BYREF
  int v121[2]; // [rsp+20h] [rbp-188h]
  _BYTE v122[24]; // [rsp+28h] [rbp-180h]
  int v123[2]; // [rsp+40h] [rbp-168h]
  __int64 v124; // [rsp+48h] [rbp-160h]
  __int64 v125[3]; // [rsp+50h] [rbp-158h] BYREF
  void *v126; // [rsp+70h] [rbp-138h]
  __int64 v127; // [rsp+78h] [rbp-130h]
  int v128; // [rsp+84h] [rbp-124h]
  void *v129; // [rsp+88h] [rbp-120h]
  void *v130; // [rsp+90h] [rbp-118h]
  _BYTE *v131; // [rsp+98h] [rbp-110h]
  __int64 v132; // [rsp+A0h] [rbp-108h]
  unsigned int v133; // [rsp+ACh] [rbp-FCh]
  __int64 v134; // [rsp+B0h] [rbp-F8h]
  void *v135; // [rsp+B8h] [rbp-F0h]
  __int64 v136; // [rsp+C0h] [rbp-E8h]
  int v137; // [rsp+CCh] [rbp-DCh]
  __int64 v138; // [rsp+D0h] [rbp-D8h]
  _QWORD *v139; // [rsp+D8h] [rbp-D0h]
  unsigned __int64 *v140; // [rsp+E0h] [rbp-C8h]
  int *v141; // [rsp+E8h] [rbp-C0h]
  _QWORD *v142; // [rsp+F0h] [rbp-B8h] BYREF
  _DWORD MaxCount[5]; // [rsp+FCh] [rbp-ACh] BYREF
  __int128 v144; // [rsp+110h] [rbp-98h]
  __int128 v145; // [rsp+120h] [rbp-88h] BYREF
  unsigned __int64 v146; // [rsp+138h] [rbp-70h] BYREF
  void *v147; // [rsp+140h] [rbp-68h]
  __int64 v148; // [rsp+148h] [rbp-60h]

  v140 = a3;
  v139 = (_QWORD *)a2;
  v144 = 0;
  *(_OWORD *)&MaxCount[1] = 0;
  v8 = *(_QWORD *)(a1 + 56);
  if ( **(_BYTE **)(v8 + 32) != 60 )
    goto LABEL_144;
  v4 = (unsigned __int64)a4;
  v5 = *(void **)(a1 + 448);
  LODWORD(v136) = *(_DWORD *)(a1 + 456);
  ++*(_DWORD *)(v8 + 56);
  if ( !*(_BYTE *)++*(_QWORD *)(*(_QWORD *)(a1 + 56) + 32LL) )
    sub_1400F779E(a1);
  v141 = (int *)v4;
  v9 = *(_QWORD *)(a1 + 736);
  v10 = *(_DWORD *)(v9 + 24);
  if ( v10 == -1 )
  {
    sub_14030C437(a1);
LABEL_144:
    v129 = 0;
    goto LABEL_100;
  }
  v145 = 0;
  *(_DWORD *)(v9 + 24) = v10 + 1;
  v4 = (unsigned __int64)&v146;
  sub_1400F76A2(&v146, a1);
  v129 = v147;
  if ( !v147 )
  {
    v129 = 0;
    sub_14030C59A(a1, 0, 1, 68, 3, 0, 0, 0, 0, (__int64)"%s", (__int64)"StartTag: invalid element name\n");
    goto LABEL_100;
  }
  v135 = (void *)*((_QWORD *)&v145 + 1);
  sub_1400F7634(a1);
  v11 = *(_QWORD *)(a1 + 56);
  if ( (*(_BYTE *)(v11 + 88) & 0x40) == 0 && (__int64)(*(_QWORD *)(v11 + 40) - *(_QWORD *)(v11 + 32)) <= 249 )
    sub_1400F779E(a1);
  v12 = 0;
  v13 = 0;
  v128 = 0;
  v137 = 0;
  while ( 1 )
  {
    v14 = *(_QWORD *)(a1 + 56);
    v15 = *(unsigned __int8 **)(v14 + 32);
    LODWORD(v16) = *v15;
    if ( (_DWORD)v16 == 62 )
      break;
    if ( (_DWORD)v16 == 47 )
    {
      if ( v15[1] == 62 )
        break;
    }
    else if ( (unsigned __int8)((_BYTE)v16 - 9) >= 2u && (unsigned __int8)v16 < 0x20u && (_BYTE)v16 != 13 )
    {
      break;
    }
    if ( *(int *)(a1 + 316) > 1 )
      break;
    v127 = v12;
    MaxCount[0] = -1;
    LODWORD(v142) = 0;
    if ( (*(_BYTE *)(v14 + 88) & 0x40) == 0 && (__int64)(*(_QWORD *)(v14 + 40) - (_QWORD)v15) <= 249 )
      sub_1400F779E(a1);
    sub_1400F76A2(&v146, a1);
    v17 = v146;
    v18 = (__int64)v147;
    if ( !v147 )
    {
      sub_14030C59A(a1, 0, 1, 68, 3, 0, 0, 0, 0, (__int64)"%s", (__int64)"error parsing attribute name\n");
      v144 = v17;
      v12 = v127;
      break;
    }
    v19 = *(_QWORD *)&MaxCount[3];
    v20 = *(_QWORD *)(a1 + 536);
    if ( v20 )
      sub_140318F91(v20, (_DWORD)v135, (_DWORD)v129, MaxCount[3], (__int64)v147);
    sub_1400F7634(a1);
    if ( **(_BYTE **)(*(_QWORD *)(a1 + 56) + 32LL) != 61 )
    {
      sub_14030C59A(
        a1,
        0,
        1,
        41,
        3,
        (void *)v18,
        0,
        0,
        0,
        (__int64)"Specification mandates value for attribute %s\n",
        v18);
LABEL_198:
      *(_QWORD *)&v144 = v17;
      *((_QWORD *)&v144 + 1) = v18;
      v12 = v127;
      goto LABEL_29;
    }
    sub_1400F7723(a1);
    sub_1400F7634(a1);
    LODWORD(v142) = 0;
    v21 = sub_1400F7E7C(
            a1,
            ((v19 | *(_QWORD *)(a1 + 472) ^ v18) == 0) | (unsigned __int8)(v19 == *(_QWORD *)(a1 + 472)));
    if ( !v21 )
      goto LABEL_198;
    v22 = (_BYTE *)v21;
    v126 = v5;
    v23 = (int)v142;
    LODWORD(v6) = (unsigned __int8)v142 & 1;
    if ( v19 == *(_QWORD *)(a1 + 464) )
    {
      v111 = (int)v142;
      v112 = (void *)v21;
      if ( *(_DWORD *)(a1 + 404) && (unsigned int)sub_1400F5E05(v18, "lang") )
      {
        v113 = sub_1400F8515(v112, MaxCount[0]);
        if ( !v113 )
          goto LABEL_202;
        v110 = (void *)v113;
        if ( !(unsigned int)sub_14030D4BD(v113) )
        {
          v125[1] = 0;
          sub_14030C59A(a1, 0, 1, 98, 1, v110, 0, 0, 0, (__int64)"Malformed value for xml:lang : %s\n", (__int64)v110);
        }
      }
      else
      {
        v110 = 0;
      }
      if ( (unsigned int)sub_1400F5E05(v18, "space") )
      {
        v114 = sub_1400F8515(v112, MaxCount[0]);
        if ( !v114 )
        {
LABEL_202:
          sub_14030C437(a1);
          v5 = v126;
          if ( (_DWORD)v6 )
            ((void (__fastcall *)(void *))off_14042A808[0])(v112);
          goto LABEL_198;
        }
        v110 = (void *)v114;
        if ( (unsigned int)sub_1400F5E05(v114, "default") )
        {
          **(_DWORD **)(a1 + 352) = 0;
        }
        else if ( (unsigned int)sub_1400F5E05(v110, "preserve") )
        {
          **(_DWORD **)(a1 + 352) = 1;
        }
        else
        {
          v125[1] = 0;
          sub_14030C59A(
            a1,
            0,
            1,
            102,
            1,
            v110,
            0,
            0,
            0,
            (__int64)"Invalid value \"%s\" for xml:space : \"default\" or \"preserve\" expected\n",
            (__int64)v110);
        }
LABEL_209:
        ((void (__fastcall *)(void *))off_14042A808[0])(v110);
        v23 = v111;
        v22 = v112;
        goto LABEL_20;
      }
      v22 = v112;
      v23 = v111;
      if ( v110 )
        goto LABEL_209;
    }
LABEL_20:
    *(_QWORD *)&v144 = v17;
    *((_QWORD *)&v144 + 1) = v18;
    v24 = *(_QWORD *)&MaxCount[3];
    v25 = MaxCount[0];
    if ( MaxCount[0] < 0 )
    {
      v107 = v22;
      v108 = v23;
      v109 = sub_1402FCAEC(v22);
      v23 = v108;
      v22 = v107;
      v25 = v109;
      MaxCount[0] = v109;
    }
    v26 = *(_QWORD *)(a1 + 472);
    if ( !(v24 | v26 ^ v18) )
    {
      LODWORD(v6) = v23;
      v142 = 0;
      v33 = *(_QWORD *)(a1 + 440);
      v131 = v22;
      sub_1400F79CE(&v146, v33, v22, v25);
      v34 = v147;
      if ( v147 )
      {
        v5 = v126;
        v12 = v127;
        if ( !*(_BYTE *)v147 )
          goto LABEL_44;
        if ( (int)sub_1400F81F0(v147, &v142) >= 0 )
        {
          if ( v142 )
          {
            if ( !*v142 )
            {
              *(_OWORD *)&v125[1] = 0;
              sub_14030C59A(a1, 0, 3, 100, 1, v34, 0, 0, 0, (__int64)"xmlns: URI %s is not absolute\n", (__int64)v34);
            }
            sub_1400F8304();
          }
          else
          {
            *(_DWORD *)(a1 + 544) = 0;
            *(_OWORD *)&v125[1] = 0;
            sub_14030C59A(a1, 0, 3, 99, 2, v34, 0, 0, 0, (__int64)"xmlns: '%s' is not a valid URI\n", (__int64)v34);
          }
          if ( v34 != *(void **)(a1 + 480) )
          {
            if ( MaxCount[0] == 29 && (unsigned int)sub_1400F5E05(v34, "http://www.w3.org/2000/xmlns/") )
            {
LABEL_237:
              *(_DWORD *)(a1 + 544) = 0;
              v117 = 0;
              memset(v125, 0, sizeof(v125));
              v118 = "reuse of the xmlns namespace name is forbidden\n";
LABEL_238:
              v124 = (__int64)v118;
              v123[0] = 0;
              *(_QWORD *)&v122[16] = 0;
              *(_OWORD *)v122 = v117;
LABEL_239:
              sub_14030C59A(
                a1,
                0,
                3,
                200,
                2,
                *(void **)v122,
                *(int *)&v122[8],
                *(void **)&v122[16],
                v123[0],
                v124,
                v125[0]);
LABEL_46:
              LODWORD(v16) = v6;
              goto LABEL_47;
            }
LABEL_44:
            v35 = a1;
LABEL_45:
            v128 += (int)sub_1400F89CE(v35) > 0;
            goto LABEL_46;
          }
          if ( v18 != *(_QWORD *)(a1 + 464) )
          {
            *(_DWORD *)(a1 + 544) = 0;
            v115 = 0;
            memset(v125, 0, sizeof(v125));
            v116 = "xml namespace URI cannot be the default namespace\n";
LABEL_229:
            sub_14030C59A(a1, 0, 3, 200, 2, (void *)v115, SDWORD2(v115), 0, 0, (__int64)v116, v125[0]);
          }
LABEL_231:
          v5 = v126;
          v12 = v127;
          goto LABEL_46;
        }
LABEL_223:
        sub_14030C437(a1);
        goto LABEL_46;
      }
LABEL_230:
      sub_14030C437(a1);
      goto LABEL_231;
    }
    if ( v24 == v26 )
    {
      LODWORD(v6) = v23;
      v142 = 0;
      v72 = *(_QWORD *)(a1 + 440);
      v131 = v22;
      sub_1400F79CE(&v146, v72, v22, v25);
      v73 = v147;
      if ( v147 )
      {
        v74 = *(void **)(a1 + 480);
        v5 = v126;
        v12 = v127;
        if ( v18 == *(_QWORD *)(a1 + 464) )
        {
          if ( v147 != v74 )
          {
            *(_DWORD *)(a1 + 544) = 0;
            v115 = 0;
            memset(v125, 0, sizeof(v125));
            v116 = "xml namespace prefix mapped to wrong URI\n";
            goto LABEL_229;
          }
          goto LABEL_231;
        }
        if ( v147 == v74 )
        {
          *(_DWORD *)(a1 + 544) = 0;
          v117 = 0;
          memset(v125, 0, sizeof(v125));
          v118 = "xml namespace URI mapped to wrong prefix\n";
          goto LABEL_238;
        }
        if ( v18 == *(_QWORD *)(a1 + 472) )
        {
          *(_DWORD *)(a1 + 544) = 0;
          v117 = 0;
          memset(v125, 0, sizeof(v125));
          v118 = "redefinition of the xmlns prefix is forbidden\n";
          goto LABEL_238;
        }
        if ( v25 == 29 && (unsigned int)sub_1400F5E05(v147, "http://www.w3.org/2000/xmlns/") )
          goto LABEL_237;
        if ( !*v73 )
        {
          *(_DWORD *)(a1 + 544) = 0;
          *(_OWORD *)&v125[1] = 0;
          v125[0] = v18;
          v124 = (__int64)"xmlns:%s: Empty XML namespace is not allowed\n";
          v123[0] = 0;
          *(_OWORD *)&v122[8] = 0;
          *(_QWORD *)v122 = v18;
          goto LABEL_239;
        }
        if ( (int)sub_1400F81F0(v73, &v142) >= 0 )
        {
          if ( v142 )
          {
            if ( *(_DWORD *)(a1 + 404) && !*v142 )
            {
              v125[2] = 0;
              v125[1] = (__int64)v73;
              sub_14030C59A(
                a1,
                0,
                3,
                100,
                1,
                (void *)v18,
                (int)v73,
                0,
                0,
                (__int64)"xmlns:%s: URI %s is not absolute\n",
                v18);
            }
            sub_1400F8304();
          }
          else
          {
            *(_DWORD *)(a1 + 544) = 0;
            v125[2] = 0;
            v125[1] = (__int64)v73;
            sub_14030C59A(
              a1,
              0,
              3,
              99,
              2,
              (void *)v18,
              (int)v73,
              0,
              0,
              (__int64)"xmlns:%s: '%s' is not a valid URI\n",
              v18);
          }
          v35 = a1;
          goto LABEL_45;
        }
        goto LABEL_223;
      }
      goto LABEL_230;
    }
    v27 = v13 + 5;
    if ( v126 && v27 <= (int)v136
      || (v131 = v22,
          LODWORD(v130) = v23,
          v71 = sub_1400F8275(a1),
          LODWORD(v16) = (_DWORD)v130,
          v22 = v131,
          LODWORD(v136) = *(_DWORD *)(a1 + 456),
          v126 = *(void **)(a1 + 448),
          v71 >= 0) )
    {
      v28 = v17 & 0x7FFFFFFF | ((_DWORD)v6 << 31);
      v12 = (unsigned int)(v127 + 1);
      *(_DWORD *)(*(_QWORD *)(a1 + 512) + 4LL * (int)v127) = v28;
      v16 = v126;
      *((_QWORD *)v126 + (int)v13) = v18;
      v16[(int)v13 + 1] = v24;
      v5 = v16;
      LODWORD(v16) = v13 + 3;
      *((_QWORD *)v5 + (int)v13 + 2) = MaxCount[1];
      if ( (_DWORD)v6 )
      {
        *((_QWORD *)v5 + (int)v16) = v22;
        *((_QWORD *)v5 + (int)v13 + 4) = &v22[v25];
        v137 = 1;
      }
      else
      {
        v16 = *(_QWORD **)(*(_QWORD *)(a1 + 56) + 24LL);
        *((_QWORD *)v5 + (int)v13 + 3) = v22 - (_BYTE *)v16;
        *((_QWORD *)v5 + (int)v13 + 4) = &v22[(int)v25 - *(_QWORD *)(*(_QWORD *)(a1 + 56) + 24LL)];
      }
      v13 = (unsigned int)v27;
      goto LABEL_29;
    }
    v5 = v126;
    v12 = v127;
LABEL_47:
    if ( ((unsigned __int8)v16 & 1) != 0 )
      ((void (__fastcall *)(_BYTE *))off_14042A808[0])(v131);
LABEL_29:
    v29 = *(_QWORD *)(a1 + 56);
    if ( (*(_BYTE *)(v29 + 88) & 0x40) == 0 && (__int64)(*(_QWORD *)(v29 + 40) - *(_QWORD *)(v29 + 32)) <= 249 )
    {
      sub_1400F779E(a1);
      v29 = *(_QWORD *)(a1 + 56);
    }
    v30 = *(unsigned __int8 **)(v29 + 32);
    v31 = *v30;
    if ( v31 == 47 )
    {
      if ( v30[1] == 62 )
        break;
    }
    else if ( v31 == 62 )
    {
      break;
    }
    if ( !(unsigned int)sub_1400F7634(a1) )
    {
      sub_14030C59A(a1, 0, 1, 65, 3, 0, 0, 0, 0, (__int64)"%s", (__int64)"attributes construct error\n");
      break;
    }
    v32 = *(_QWORD *)(a1 + 56);
    if ( (*(_BYTE *)(v32 + 88) & 0x40) == 0 && (__int64)(*(_QWORD *)(v32 + 40) - *(_QWORD *)(v32 + 32)) <= 249 )
      sub_1400F779E(a1);
  }
  v127 = v12;
  v38 = *(_QWORD *)(a1 + 528);
  v126 = v5;
  if ( v38 )
  {
    v39 = 0;
    v89 = v13;
    v90 = (int *)sub_140318D44(v38, v129, v135);
    if ( v90 )
    {
      v91 = v90;
      if ( *v90 > 0 )
      {
        v85 = v90 + 10;
        v39 = 0;
        v6 = 0;
        while ( 1 )
        {
          v86 = (unsigned int)v91[1];
          if ( (int)v86 <= 0 || v6 > v86 )
LABEL_251:
            __asm { ud1     eax, dword ptr [eax+12h] }
          v87 = *((_QWORD *)v85 - 3);
          v88 = *(_QWORD *)(a1 + 472);
          v16 = (_QWORD *)(v87 | v88 ^ *((_QWORD *)v85 - 1));
          if ( !v16 || v87 == v88 )
          {
            sub_140314C8E(a1, (unsigned int)v85[7]);
            v128 += (int)sub_1400F89CE(a1) > 0;
          }
          else
          {
            if ( v39 + (int)v127 > 99999999 )
            {
              sub_14030C9A2(a1, 114);
              break;
            }
            ++v39;
          }
          ++v6;
          v85 += 16;
          v5 = v126;
          v13 = v89;
          if ( v6 >= *v91 )
            goto LABEL_55;
        }
      }
    }
    v5 = v126;
    v13 = v89;
  }
  else
  {
    v39 = 0;
  }
LABEL_55:
  if ( (int)v13 > 0 )
  {
    v40 = 0;
    do
    {
      v41 = (void *)*((_QWORD *)v5 + v40 + 1);
      v42 = 0x7FFFFFFF;
      if ( v41 )
      {
        if ( v41 == *(void **)(a1 + 464) )
        {
          v42 = 2147483646;
        }
        else
        {
          v6 = *((_QWORD *)v5 + v40);
          *(_QWORD *)&MaxCount[3] = *((_QWORD *)v5 + v40 + 1);
          MaxCount[1] = *((_DWORD *)v5 + 2 * v40 + 4);
          v42 = sub_1400F7851(a1, &MaxCount[1], 0);
          if ( v42 == 0x7FFFFFFF || v42 < *(_DWORD *)(*(_QWORD *)(a1 + 736) + 32LL) )
          {
            *(_DWORD *)(a1 + 544) = 0;
            v125[2] = (__int64)v129;
            v125[1] = v6;
            sub_14030C59A(
              a1,
              0,
              3,
              201,
              2,
              v41,
              v6,
              v129,
              0,
              (__int64)"Namespace prefix %s for %s on %s is not defined\n",
              (__int64)v41);
            v42 = 0x7FFFFFFF;
          }
        }
      }
      *((_QWORD *)v5 + v40 + 2) = v42;
      v40 += 5;
    }
    while ( v40 < (int)v13 );
  }
  v43 = (unsigned int)(v127 + v39);
  LODWORD(v131) = 0;
  v138 = v43;
  if ( (int)v43 < 2 )
  {
    LODWORD(v4) = 0;
LABEL_50:
    a2 = 0;
    goto LABEL_73;
  }
  v44 = 4;
  do
  {
    LODWORD(v4) = v44;
    v45 = v44 >> 1;
    v44 *= 2;
  }
  while ( v45 < (unsigned int)v43 );
  if ( (unsigned int)v4 <= *(_DWORD *)(a1 + 744) )
  {
    v36 = *(void **)(a1 + 752);
    v37 = 4LL * (unsigned int)v4;
  }
  else
  {
    v37 = 4LL * (unsigned int)v4;
    v46 = ((__int64 (__fastcall *)(_QWORD, size_t))off_14042A818[0])(*(_QWORD *)(a1 + 752), v37);
    if ( !v46 )
    {
      sub_14030C437(a1);
      goto LABEL_98;
    }
    v36 = (void *)v46;
    *(_QWORD *)(a1 + 752) = v46;
    *(_DWORD *)(a1 + 744) = v4;
  }
  v130 = (void *)v13;
  LOBYTE(v16) = -1;
  memset(v36, (int)v16, v37);
  v132 = 0;
  if ( (int)v127 <= 0 )
  {
    LODWORD(v13) = (_DWORD)v130;
    goto LABEL_50;
  }
  v47 = (unsigned int)v127;
  v48 = 0;
  LODWORD(v134) = 0;
  v49 = 0;
  do
  {
    v50 = (void *)*((_QWORD *)v126 + v49);
    v51 = *((_QWORD *)v126 + v49 + 1);
    v52 = *((_QWORD *)v126 + v49 + 2);
    a2 = 0x80000000LL;
    if ( (_DWORD)v52 == 0x7FFFFFFF )
    {
      if ( v51 )
        goto LABEL_71;
      v53 = 3645087822LL;
      v54 = 0;
    }
    else if ( (_DWORD)v52 == 2147483646 )
    {
      v54 = *(_QWORD *)(a1 + 480);
      v53 = 4031061762LL;
    }
    else
    {
      v54 = *(_QWORD *)(*(_QWORD *)(a1 + 504) + 16LL * (_DWORD)v52 + 8);
      v53 = *(unsigned int *)(**(_QWORD **)(a1 + 736) + 24LL * (int)v52 + 12);
    }
    v55 = sub_1400F761D(*(_DWORD *)(*(_QWORD *)(a1 + 512) + 4 * v48) | 0x80000000, v53);
    v56 = sub_1400F77E8(a1, v4, (_DWORD)v50, v54, v55, v49);
    if ( v56 != 0x7FFFFFFF )
    {
      if ( v51 == *((_QWORD *)v126 + v56 + 1) )
      {
        sub_140315621(a1, v51, v50);
        v132 = (unsigned int)(v132 + 1);
      }
      else
      {
        *(_DWORD *)(a1 + 544) = 0;
        v125[2] = 0;
        v125[1] = v54;
        sub_14030C59A(
          a1,
          0,
          3,
          203,
          2,
          v50,
          v54,
          0,
          0,
          (__int64)"Namespaced Attribute %s in '%s' redefined\n",
          (__int64)v50);
        LODWORD(v134) = v134 + 1;
      }
    }
LABEL_71:
    v49 += 5;
    ++v48;
  }
  while ( v47 != v48 );
  LOBYTE(a2) = (_DWORD)v132 == 0 && (int)v134 >= 2;
  LODWORD(v13) = (_DWORD)v130;
LABEL_73:
  v57 = *(_QWORD *)(a1 + 528);
  if ( !v57 )
  {
    LODWORD(v6) = v13;
    v5 = v126;
    goto LABEL_75;
  }
  v132 = a2;
  v105 = (int *)sub_140318D44(v57, v129, v135);
  if ( v105 )
  {
    v106 = v105;
    if ( *v105 > 0 )
    {
      v101 = (unsigned int *)(v105 + 17);
      v100 = 0;
      LODWORD(v131) = 0;
      v5 = v126;
      while ( 2 )
      {
        v102 = (unsigned int)v106[1];
        if ( (int)v102 <= 0 || v100 > v102 )
          goto LABEL_251;
        v103 = *(_QWORD *)(v101 - 13);
        v104 = *(_QWORD *)(a1 + 472);
        v130 = *(void **)(v101 - 9);
        v126 = (void *)v103;
        if ( (v103 | v104 ^ (unsigned __int64)v130) == 0 || v103 == v104 )
          goto LABEL_181;
        v133 = -649879474;
        v134 = 0x7FFFFFFF;
        if ( v126 )
        {
          if ( v126 == *(void **)(a1 + 464) )
          {
            v97 = *(_QWORD *)(a1 + 480);
            v133 = -263905534;
            v134 = 2147483646;
            goto LABEL_175;
          }
          v95 = sub_1400F7851(a1, v101 - 15, 0);
          if ( v95 != 0x7FFFFFFF )
          {
            v96 = *(__int64 **)(a1 + 736);
            if ( v95 >= *((_DWORD *)v96 + 8) )
            {
              v97 = *(_QWORD *)(*(_QWORD *)(a1 + 504) + 16LL * v95 + 8);
              v119 = *v96;
              v134 = v95;
              v133 = *(_DWORD *)(v119 + 24LL * v95 + 12);
LABEL_175:
              if ( (int)v138 < 2 )
                goto LABEL_176;
              v98 = sub_1400F761D(*(v101 - 11), v133);
              v99 = sub_1400F77E8(a1, v4, (_DWORD)v130, v97, v98, v13);
              if ( v99 == 0x7FFFFFFF )
                goto LABEL_176;
              if ( v126 != *((void **)v5 + v99 + 1) )
              {
                *(_DWORD *)(a1 + 544) = 0;
                v125[2] = 0;
                v125[1] = v97;
                sub_14030C59A(
                  a1,
                  0,
                  3,
                  203,
                  2,
                  v130,
                  v97,
                  0,
                  0,
                  (__int64)"Namespaced Attribute %s in '%s' redefined\n",
                  (__int64)v130);
LABEL_176:
                sub_140314C8E(a1, *v101);
                LODWORD(v6) = v13 + 5;
                if ( !v5 || (int)v6 > (int)v136 )
                {
                  v94 = sub_1400F8275(a1);
                  v5 = *(void **)(a1 + 448);
                  if ( v94 < 0 )
                  {
                    v129 = 0;
                    goto LABEL_98;
                  }
                  LODWORD(v136) = *(_DWORD *)(a1 + 456);
                }
                *((_QWORD *)v5 + (int)v13) = v130;
                *((_QWORD *)v5 + (int)v13 + 1) = v126;
                *((_QWORD *)v5 + (int)v13 + 2) = v134;
                *((_QWORD *)v5 + (int)v13 + 3) = *(_QWORD *)(v101 - 5);
                *((_QWORD *)v5 + (int)v13 + 4) = *(_QWORD *)(v101 - 3);
                LODWORD(v131) = (_DWORD)v131 + 1;
                goto LABEL_182;
              }
LABEL_181:
              LODWORD(v6) = v13;
LABEL_182:
              ++v100;
              v101 += 16;
              LODWORD(v13) = v6;
              LODWORD(a2) = v132;
              if ( (__int64)v100 >= *v106 )
                goto LABEL_75;
              continue;
            }
          }
          *(_DWORD *)(a1 + 544) = 0;
          v125[2] = (__int64)v129;
          v125[1] = (__int64)v130;
          sub_14030C59A(
            a1,
            0,
            3,
            201,
            2,
            v126,
            (int)v130,
            v129,
            0,
            (__int64)"Namespace prefix %s for %s on %s is not defined\n",
            (__int64)v126);
        }
        break;
      }
      v97 = 0;
      goto LABEL_175;
    }
  }
  LODWORD(v6) = v13;
  v5 = v126;
  LODWORD(a2) = v132;
LABEL_75:
  if ( (_BYTE)a2 )
    goto LABEL_127;
  while ( 1 )
  {
    v58 = v127;
    if ( (int)v6 > 0 )
    {
      v59 = 0;
      v60 = 0;
      do
      {
        v61 = v60 + 2;
        v62 = *((_DWORD *)v5 + 2 * v61);
        if ( v62 == 0x7FFFFFFF )
        {
          v63 = 0;
        }
        else if ( v62 == 2147483646 )
        {
          v63 = *(_QWORD *)(a1 + 480);
        }
        else
        {
          v63 = *(_QWORD *)(*(_QWORD *)(a1 + 504) + 16LL * v62 + 8);
        }
        *((_QWORD *)v5 + v61) = v63;
        if ( v59 < v58 && *(int *)(*(_QWORD *)(a1 + 512) + 4LL * v59) >= 0 )
        {
          *((_QWORD *)v5 + v60 + 3) += *(_QWORD *)(*(_QWORD *)(a1 + 56) + 24LL);
          *((_QWORD *)v5 + v60 + 4) += *(_QWORD *)(*(_QWORD *)(a1 + 56) + 24LL);
        }
        v60 += 5;
        ++v59;
      }
      while ( v60 < (int)v6 );
    }
    if ( *((_QWORD *)&v145 + 1) == *(_QWORD *)(a1 + 464) )
    {
      v4 = *(_QWORD *)(a1 + 480);
      v65 = v135;
    }
    else
    {
      v4 = 0;
      v64 = sub_1400F7851(a1, &v145, 0);
      v65 = v135;
      if ( v64 != 0x7FFFFFFF )
      {
        if ( v64 < *(_DWORD *)(*(_QWORD *)(a1 + 736) + 32LL) )
        {
          v4 = 0;
        }
        else
        {
          v66 = *(_BYTE **)(*(_QWORD *)(a1 + 504) + 16LL * v64 + 8);
          v4 = 0;
          if ( *v66 )
            v4 = (unsigned __int64)v66;
        }
      }
    }
    if ( v65 && !v4 )
    {
      *(_DWORD *)(a1 + 544) = 0;
      v125[2] = 0;
      v125[1] = (__int64)v129;
      sub_14030C59A(
        a1,
        0,
        3,
        201,
        2,
        v65,
        (int)v129,
        0,
        0,
        (__int64)"Namespace prefix %s on %s is not defined\n",
        (__int64)v65);
      v65 = v135;
    }
    *v139 = v65;
    *v140 = v4;
    if ( *(_QWORD *)a1 )
    {
      v67 = *(void (__fastcall **)(__int64, void *, void *, unsigned __int64, int, _QWORD, _DWORD, _DWORD, _QWORD))(*(_QWORD *)a1 + 232LL);
      if ( v67 )
      {
        if ( !*(_DWORD *)(a1 + 316) )
        {
          if ( v128 > 0 )
          {
            v70 = *(_QWORD *)(a1 + 504) + 16LL * (*(_DWORD *)(a1 + 492) - v128);
            v68 = *(_QWORD *)(a1 + 8);
            *(_QWORD *)v123 = v5;
            *(_DWORD *)&v122[16] = (_DWORD)v131;
            *(_DWORD *)&v122[8] = (int)v6 / 5;
            *(_QWORD *)v122 = v70;
            v121[0] = v128;
          }
          else
          {
            v68 = *(_QWORD *)(a1 + 8);
            *(_QWORD *)v123 = v5;
            *(_DWORD *)&v122[16] = (_DWORD)v131;
            *(_DWORD *)&v122[8] = (int)v6 / 5;
            *(_QWORD *)v122 = 0;
            v121[0] = 0;
          }
          v67(v68, v129, v65, v4, v121[0], *(_QWORD *)v122, *(_DWORD *)&v122[8], *(_DWORD *)&v122[16], *(_QWORD *)v123);
        }
      }
    }
LABEL_98:
    LODWORD(a2) = v127;
    if ( v137 != 0 && (int)v127 > 0 )
    {
      v4 = (unsigned int)v127;
      v92 = 3;
      v93 = 0;
      do
      {
        if ( *(int *)(*(_QWORD *)(a1 + 512) + 4LL * (_QWORD)v93) < 0 )
          ((void (__fastcall *)(_QWORD))off_14042A808[0])(*((_QWORD *)v5 + v92));
        v93 = (_QWORD *)((char *)v93 + 1);
        v92 += 5;
      }
      while ( (_QWORD *)v4 != v93 );
    }
    *v141 = v128;
LABEL_100:
    if ( _security_cookie == ((unsigned __int64)&v120 ^ v148) )
      return v129;
LABEL_127:
    LOBYTE(a2) = -1;
    memset(*(void **)(a1 + 752), a2, 4LL * (unsigned int)v4);
    if ( (int)v127 > 0 )
    {
      LODWORD(v130) = v4 - 1;
      v136 = (unsigned int)v127;
      v75 = 0;
      v76 = 0;
      v126 = v5;
      do
      {
        v77 = (void *)*((_QWORD *)v5 + v76 + 1);
        if ( v77 )
        {
          v78 = *((_QWORD *)v126 + v76);
          v79 = *(_DWORD *)(*(_QWORD *)(a1 + 512) + 4 * v75) | 0x80000000;
          v80 = sub_1403297FE(*(_QWORD *)(a1 + 440), v77);
          v81 = (unsigned int)v130 & (unsigned int)sub_1400F761D(v79, v80);
          v82 = (unsigned int *)(*(_QWORD *)(a1 + 752) + 4 * v81);
          v83 = *v82;
          if ( (*v82 & 0x80000000) != 0 )
          {
LABEL_129:
            *v82 = v76;
          }
          else
          {
            v84 = *(_QWORD *)(a1 + 448);
            while ( v78 != *(_QWORD *)(v84 + 8LL * v83) || v77 != *(void **)(v84 + 8LL * v83 + 8) )
            {
              LODWORD(v81) = v81 + 1;
              ++v82;
              if ( (unsigned int)v81 >= (unsigned int)v4 )
              {
                v82 = *(unsigned int **)(a1 + 752);
                LODWORD(v81) = 0;
              }
              v83 = *v82;
              if ( (*v82 & 0x80000000) != 0 )
                goto LABEL_129;
            }
            if ( v83 != 0x7FFFFFFF )
            {
              v125[1] = v78;
              sub_14030C59A(a1, 0, 1, 42, 3, v77, v78, 0, 0, (__int64)"Attribute %s:%s redefined\n", (__int64)v77);
            }
          }
        }
        v76 += 5;
        ++v75;
        v5 = v126;
      }
      while ( v75 != v136 );
    }
  }
}

```

## disassembly

```asm
0x1400f6cee  push    r15
0x1400f6cf0  push    r14
0x1400f6cf2  push    r13
0x1400f6cf4  push    r12
0x1400f6cf6  push    rsi
0x1400f6cf7  push    rdi
0x1400f6cf8  push    rbp
0x1400f6cf9  push    rbx
0x1400f6cfa  sub     rsp, 168h
0x1400f6d01  movaps  [rsp+1A8h+var_58], xmm6
0x1400f6d09  mov     [rsp+1A8h+var_C8], r8
0x1400f6d11  mov     [rsp+1A8h+var_D0], rdx
0x1400f6d19  mov     rsi, rcx
0x1400f6d1c  mov     rax, cs:__security_cookie
0x1400f6d23  xor     rax, rsp
0x1400f6d26  mov     [rsp+1A8h+var_60], rax
0x1400f6d2e  xorps   xmm0, xmm0
0x1400f6d31  movaps  [rsp+1A8h+var_98], xmm0
0x1400f6d39  movaps  xmmword ptr [rsp+1A8h+MaxCount+4], xmm0
0x1400f6d41  mov     rax, [rcx+38h]
0x1400f6d45  mov     rcx, [rax+20h]
0x1400f6d49  cmp     byte ptr [rcx], 3Ch ; '<'
0x1400f6d4c  jnz     loc_1401AFFCF
0x1400f6d52  mov     rdi, r9
0x1400f6d55  mov     r13, [rsi+1C0h]
0x1400f6d5c  mov     ecx, [rsi+1C8h]
0x1400f6d62  mov     dword ptr [rsp+1A8h+var_E8], ecx
0x1400f6d69  inc     dword ptr [rax+38h]
0x1400f6d6c  mov     rax, [rsi+38h]
0x1400f6d70  inc     qword ptr [rax+20h]
0x1400f6d74  mov     rax, [rsi+38h]
0x1400f6d78  mov     rax, [rax+20h]
0x1400f6d7c  cmp     byte ptr [rax], 0
0x1400f6d7f  jz      loc_1401B048C
0x1400f6d85  mov     [rsp+1A8h+var_C0], rdi
0x1400f6d8d  mov     rax, [rsi+2E0h]
0x1400f6d94  mov     ecx, [rax+18h]
0x1400f6d97  cmp     ecx, 0FFFFFFFFh
0x1400f6d9a  jz      loc_1401AFFC7
0x1400f6da0  xorps   xmm6, xmm6
0x1400f6da3  lea     r8, [rsp+1A8h+var_88]
0x1400f6dab  movaps  xmmword ptr [r8], xmm6
0x1400f6daf  inc     ecx
0x1400f6db1  mov     [rax+18h], ecx
0x1400f6db4  lea     rdi, [rsp+1A8h+var_70]
0x1400f6dbc  mov     rcx, rdi
0x1400f6dbf  mov     rdx, rsi
0x1400f6dc2  call    sub_1400F76A2
0x1400f6dc7  mov     rcx, [rdi+8]
0x1400f6dcb  mov     [rsp+1A8h+var_120], rcx
0x1400f6dd3  test    rcx, rcx
0x1400f6dd6  jz      loc_1401B086E
0x1400f6ddc  mov     rax, [rsp+1A8h+var_80]
0x1400f6de4  mov     [rsp+1A8h+var_F0], rax
0x1400f6dec  mov     rcx, rsi; int
0x1400f6def  call    sub_1400F7634
0x1400f6df4  mov     rax, [rsi+38h]
0x1400f6df8  test    byte ptr [rax+58h], 40h
0x1400f6dfc  jz      loc_1401B074E
0x1400f6e02  xor     edi, edi
0x1400f6e04  xor     ebp, ebp
0x1400f6e06  mov     [rsp+1A8h+var_124], 0
0x1400f6e11  mov     [rsp+1A8h+var_DC], 0
0x1400f6e1c  mov     rcx, [rsi+38h]
0x1400f6e20  mov     rax, [rcx+20h]
0x1400f6e24  movzx   edx, byte ptr [rax]
0x1400f6e27  cmp     edx, 3Eh ; '>'
0x1400f6e2a  jz      loc_1400F71AC
0x1400f6e30  cmp     edx, 2Fh ; '/'
0x1400f6e33  jz      loc_140155826
0x1400f6e39  lea     r8d, [rdx-9]
0x1400f6e3d  cmp     r8b, 2
0x1400f6e41  jb      short loc_1400F6E59
0x1400f6e43  cmp     dl, 0Dh
0x1400f6e46  setnz   r8b
0x1400f6e4a  cmp     dl, 20h ; ' '
0x1400f6e4d  setb    dl
0x1400f6e50  test    r8b, dl
0x1400f6e53  jnz     loc_1400F71AC
0x1400f6e59  cmp     dword ptr [rsi+13Ch], 1
0x1400f6e60  jg      loc_1400F71AC
0x1400f6e66  mov     [rsp+1A8h+var_130], rdi
0x1400f6e6b  mov     dword ptr [rsp+1A8h+MaxCount], 0FFFFFFFFh
0x1400f6e76  mov     dword ptr [rsp+1A8h+var_B8], 0
0x1400f6e81  test    byte ptr [rcx+58h], 40h
0x1400f6e85  jz      loc_1401AFFA6
0x1400f6e8b  lea     rcx, [rsp+1A8h+var_70]
0x1400f6e93  mov     rdx, rsi
0x1400f6e96  lea     r8, [rsp+1A8h+MaxCount+4]
0x1400f6e9e  call    sub_1400F76A2
0x1400f6ea3  mov     rdi, [rsp+1A8h+var_70]
0x1400f6eab  mov     rbx, [rsp+1A8h+var_68]
0x1400f6eb3  test    rbx, rbx
0x1400f6eb6  jz      loc_1401B077D
0x1400f6ebc  mov     r14, qword ptr [rsp+1A8h+MaxCount+0Ch]
0x1400f6ec4  mov     rcx, [rsi+218h]
0x1400f6ecb  xor     r12d, r12d
0x1400f6ece  test    rcx, rcx
0x1400f6ed1  jnz     loc_1401B0126
0x1400f6ed7  mov     rcx, rsi; int
0x1400f6eda  call    sub_1400F7634
0x1400f6edf  mov     rax, [rsi+38h]
0x1400f6ee3  mov     rax, [rax+20h]
0x1400f6ee7  cmp     byte ptr [rax], 3Dh ; '='
0x1400f6eea  jnz     loc_1401B0512
0x1400f6ef0  mov     rcx, rsi; int
0x1400f6ef3  call    sub_1400F7723
0x1400f6ef8  mov     rcx, rsi; int
0x1400f6efb  call    sub_1400F7634
0x1400f6f00  mov     dword ptr [rsp+1A8h+var_B8], 0
0x1400f6f0b  mov     rax, [rsi+1D8h]
0x1400f6f12  mov     rcx, rbx
0x1400f6f15  xor     rcx, rax
0x1400f6f18  or      rcx, r14
0x1400f6f1b  setz    cl
0x1400f6f1e  cmp     r14, rax
0x1400f6f21  setz    al
0x1400f6f24  or      al, cl
0x1400f6f26  movzx   eax, al
0x1400f6f29  mov     [rsp+1A8h+var_188], eax; int
0x1400f6f2d  mov     rcx, rsi; int
0x1400f6f30  lea     rdx, [rsp+1A8h+MaxCount]
0x1400f6f38  lea     r8, [rsp+1A8h+var_B8]
0x1400f6f40  mov     r9d, r12d
0x1400f6f43  call    sub_1400F7E7C
0x1400f6f48  test    rax, rax
0x1400f6f4b  jz      loc_1401B0556
0x1400f6f51  mov     r9, rax
0x1400f6f54  mov     [rsp+1A8h+var_138], r13
0x1400f6f59  mov     edx, dword ptr [rsp+1A8h+var_B8]
0x1400f6f60  mov     r15d, edx
0x1400f6f63  and     r15d, 1
0x1400f6f67  cmp     r14, [rsi+1D0h]
0x1400f6f6e  jz      loc_1401B0570
0x1400f6f74  mov     qword ptr [rsp+1A8h+var_98], rdi
0x1400f6f7c  mov     qword ptr [rsp+1A8h+var_98+8], rbx
0x1400f6f84  mov     r13, qword ptr [rsp+1A8h+MaxCount+0Ch]
0x1400f6f8c  mov     r14d, dword ptr [rsp+1A8h+MaxCount]
0x1400f6f94  test    r14d, r14d
0x1400f6f97  js      loc_1401B0469
0x1400f6f9d  mov     rax, [rsi+1D8h]
0x1400f6fa4  mov     rcx, rbx
0x1400f6fa7  xor     rcx, rax
0x1400f6faa  or      rcx, r13
0x1400f6fad  jz      loc_1400F70AE
0x1400f6fb3  cmp     r13, rax
0x1400f6fb6  jz      loc_140155835
0x1400f6fbc  lea     r12d, [rbp+5]
0x1400f6fc0  cmp     [rsp+1A8h+var_138], 0
0x1400f6fc6  jz      loc_1401557DA
0x1400f6fcc  cmp     r12d, dword ptr [rsp+1A8h+var_E8]
0x1400f6fd4  jg      loc_1401557DA
0x1400f6fda  and     edi, 7FFFFFFFh
0x1400f6fe0  mov     eax, r15d
0x1400f6fe3  shl     eax, 1Fh
0x1400f6fe6  or      eax, edi
0x1400f6fe8  mov     rcx, [rsi+200h]
0x1400f6fef  mov     rdi, [rsp+1A8h+var_130]
0x1400f6ff4  movsxd  rdx, edi
0x1400f6ff7  inc     edi
0x1400f6ff9  mov     [rcx+rdx*4], eax
0x1400f6ffc  lea     eax, [rbp+1]
0x1400f6fff  movsxd  rcx, ebp
0x1400f7002  mov     rdx, [rsp+1A8h+var_138]
0x1400f7007  mov     [rdx+rcx*8], rbx
0x1400f700b  lea     ecx, [rbp+2]
0x1400f700e  cdqe
0x1400f7010  mov     [rdx+rax*8], r13
0x1400f7014  mov     r13, rdx
0x1400f7017  mov     eax, dword ptr [rsp+1A8h+MaxCount+4]
0x1400f701e  lea     edx, [rbp+3]
0x1400f7021  movsxd  rcx, ecx
0x1400f7024  mov     [r13+rcx*8+0], rax
0x1400f7029  movsxd  rcx, edx
0x1400f702c  movsxd  rax, r14d
0x1400f702f  test    r15d, r15d
0x1400f7032  jnz     loc_1401B0188
0x1400f7038  mov     rdx, [rsi+38h]
0x1400f703c  mov     rdx, [rdx+18h]
0x1400f7040  mov     r8, r9
0x1400f7043  sub     r8, rdx
0x1400f7046  mov     [r13+rcx*8+0], r8
0x1400f704b  add     r9, rax
0x1400f704e  mov     rax, [rsi+38h]
0x1400f7052  sub     r9, [rax+18h]
0x1400f7056  add     ebp, 4
0x1400f7059  movsxd  rax, ebp
0x1400f705c  mov     [r13+rax*8+0], r9
0x1400f7061  mov     ebp, r12d
0x1400f7064  mov     rax, [rsi+38h]
0x1400f7068  test    byte ptr [rax+58h], 40h
0x1400f706c  jz      loc_1401B00DE
0x1400f7072  mov     rax, [rax+20h]
0x1400f7076  movzx   ecx, byte ptr [rax]
0x1400f7079  cmp     ecx, 2Fh ; '/'
0x1400f707c  jz      loc_1400F71A2
0x1400f7082  cmp     ecx, 3Eh ; '>'
0x1400f7085  jz      loc_1400F71AC
0x1400f708b  mov     rcx, rsi; int
0x1400f708e  call    sub_1400F7634
0x1400f7093  test    eax, eax
0x1400f7095  jz      loc_1401B07E4
0x1400f709b  mov     rax, [rsi+38h]
0x1400f709f  test    byte ptr [rax+58h], 40h
0x1400f70a3  jnz     loc_1400F6E1C
0x1400f70a9  jmp     loc_1401B0104
0x1400f70ae  mov     r15d, edx
0x1400f70b1  mov     [rsp+1A8h+var_B8], 0
0x1400f70bd  mov     rdx, [rsi+1B8h]
0x1400f70c4  lea     rcx, [rsp+1A8h+var_70]
0x1400f70cc  mov     [rsp+1A8h+var_110], r9
0x1400f70d4  mov     r8, r9
0x1400f70d7  mov     r9d, r14d
0x1400f70da  call    sub_1400F79CE
0x1400f70df  mov     r14, [rsp+1A8h+var_68]
0x1400f70e7  test    r14, r14
0x1400f70ea  jz      loc_1401B0946
0x1400f70f0  cmp     byte ptr [r14], 0
0x1400f70f4  mov     r13, [rsp+1A8h+var_138]
0x1400f70f9  mov     rdi, [rsp+1A8h+var_130]
0x1400f70fe  jz      short loc_1400F7153
0x1400f7100  mov     rcx, r14
0x1400f7103  lea     rdx, [rsp+1A8h+var_B8]
0x1400f710b  call    sub_1400F81F0
0x1400f7110  test    eax, eax
0x1400f7112  js      loc_1401B0838
0x1400f7118  mov     rcx, [rsp+1A8h+var_B8]
0x1400f7120  test    rcx, rcx
0x1400f7123  jz      loc_1401B0B0B
0x1400f7129  cmp     qword ptr [rcx], 0
0x1400f712d  jz      loc_1401B0AB5
0x1400f7133  call    sub_1400F8304
0x1400f7138  cmp     r14, [rsi+1E0h]
0x1400f713f  jz      loc_1401B08EE
0x1400f7145  cmp     dword ptr [rsp+1A8h+MaxCount], 1Dh
0x1400f714d  jz      loc_1401B0A1B
0x1400f7153  mov     rcx, rsi; int
0x1400f7156  xor     edx, edx
0x1400f7158  lea     r8, [rsp+1A8h+var_70]
0x1400f7160  xor     r9d, r9d
0x1400f7163  call    sub_1400F89CE
0x1400f7168  xor     ecx, ecx
0x1400f716a  test    eax, eax
0x1400f716c  setnle  cl
0x1400f716f  add     [rsp+1A8h+var_124], ecx
0x1400f7176  mov     edx, r15d
0x1400f7179  test    dl, 1
0x1400f717c  jz      loc_1400F7064
0x1400f7182  jmp     loc_1401B0854
0x1400f7187  xor     edi, edi
0x1400f7189  xor     edx, edx
0x1400f718b  jmp     loc_1400F7352
0x1400f7190  mov     rcx, [rsi+2F0h]
0x1400f7197  mov     ebx, edi
0x1400f7199  shl     rbx, 2
0x1400f719d  jmp     loc_1400F7278
0x1400f71a2  cmp     byte ptr [rax+1], 3Eh ; '>'
0x1400f71a6  jnz     loc_1400F708B
0x1400f71ac  mov     [rsp+1A8h+var_130], rdi
0x1400f71b1  mov     rcx, [rsi+210h]
0x1400f71b8  test    rcx, rcx
0x1400f71bb  mov     [rsp+1A8h+var_138], r13
0x1400f71c0  jnz     loc_1401B0086
0x1400f71c6  xor     r12d, r12d
0x1400f71c9  test    ebp, ebp
0x1400f71cb  jle     short loc_1400F7201
0x1400f71cd  xor     ebx, ebx
0x1400f71cf  lea     rdi, [rsp+1A8h+MaxCount+4]
0x1400f71d7  movsxd  rcx, ebx
0x1400f71da  mov     r14, [r13+rcx*8+8]
0x1400f71df  mov     eax, 7FFFFFFFh
0x1400f71e4  test    r14, r14
0x1400f71e7  jnz     loc_1401558FA
0x1400f71ed  cdqe
0x1400f71ef  lea     ecx, [rbx+2]
0x1400f71f2  movsxd  rcx, ecx
0x1400f71f5  mov     [r13+rcx*8+0], rax
0x1400f71fa  add     ebx, 5
0x1400f71fd  cmp     ebx, ebp
0x1400f71ff  jl      short loc_1400F71D7
0x1400f7201  add     r12d, dword ptr [rsp+1A8h+var_130]
0x1400f7206  mov     dword ptr [rsp+1A8h+var_110], 0
0x1400f7211  cmp     r12d, 2
0x1400f7215  mov     [rsp+1A8h+var_D8], r12
0x1400f721d  jl      loc_1400F7187
0x1400f7223  mov     eax, 4
0x1400f7228  mov     edi, eax
0x1400f722a  mov     ecx, eax
0x1400f722c  shr     ecx, 1
0x1400f722e  lea     eax, [rdi+rdi]
0x1400f7231  cmp     ecx, r12d
0x1400f7234  jb      short loc_1400F7228
0x1400f7236  cmp     edi, [rsi+2E8h]
0x1400f723c  jbe     loc_1400F7190
0x1400f7242  mov     rax, cs:off_14042A818
0x1400f7249  mov     ebx, edi
0x1400f724b  shl     rbx, 2
0x1400f724f  mov     rcx, [rsi+2F0h]
0x1400f7256  mov     rdx, rbx
0x1400f7259  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
