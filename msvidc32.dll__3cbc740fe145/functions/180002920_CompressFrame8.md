# CompressFrame8

- ea: `0x180002920`
- end: `0x180003450`
- name: `CompressFrame8`
- size: `2864`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800064e8`

## callees

- `0x180001400`
- `0x180001440`
- `0x180001d44`
- `0x180002920`
- `0x180003640`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall CompressFrame8(
        __int64 a1,
        __int64 a2,
        _WORD *a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        unsigned int (__fastcall *a8)(__int64, __int64, _QWORD),
        __int64 a9,
        _OWORD *a10,
        __int64 a11,
        __int64 a12)
{
  __int64 v12; // rbx
  int v13; // edi
  __int64 v14; // r11
  _WORD *v15; // rsi
  __int64 v16; // r10
  unsigned int v17; // r12d
  unsigned int v18; // eax
  unsigned int v19; // r8d
  unsigned int v20; // ecx
  __int64 result; // rax
  int v22; // r15d
  int v23; // r14d
  unsigned int v24; // r9d
  __int64 v25; // rax
  unsigned __int16 v26; // r10
  unsigned __int16 v27; // r11
  unsigned __int16 v28; // bx
  __int64 v29; // r9
  unsigned int v30; // r12d
  int v31; // eax
  int v32; // ecx
  int v33; // r8d
  unsigned int v34; // edx
  __m128i v35; // xmm0
  __int16 v36; // ax
  unsigned __int8 v37; // al
  unsigned int v38; // r11d
  unsigned __int16 v39; // r9
  unsigned __int16 v40; // r8
  unsigned __int16 v41; // r15
  unsigned __int16 v42; // di
  unsigned __int16 v43; // r14
  int v44; // ebx
  unsigned int v45; // edx
  __int64 v46; // rcx
  unsigned __int16 v47; // si
  __int16 v48; // r10
  int v49; // r10d
  unsigned int v50; // ecx
  __int16 v51; // r8
  __int16 v52; // r9
  unsigned int v53; // r10d
  int v54; // eax
  int v55; // edx
  __int64 i; // r8
  int v57; // ecx
  __int16 v58; // ax
  unsigned __int8 v59; // cl
  __int64 v60; // rdx
  __int16 v61; // ax
  int v62; // r10d
  unsigned int v63; // r8d
  __int16 v64; // r9
  __int64 v65; // rcx
  __int16 v66; // r11
  __int16 v67; // bx
  unsigned __int64 v68; // r9
  __int16 v69; // cx
  unsigned __int64 v70; // rdx
  __int16 v71; // ax
  unsigned __int64 v72; // r8
  unsigned int v73; // ecx
  unsigned int v74; // eax
  unsigned int v75; // eax
  unsigned int v76; // eax
  unsigned __int8 v77; // al
  bool v78; // cf
  __int16 v79; // ax
  unsigned int v80; // [rsp+20h] [rbp-E0h]
  int v81; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v82; // [rsp+20h] [rbp-E0h]
  __int16 v83; // [rsp+20h] [rbp-E0h]
  int v84; // [rsp+24h] [rbp-DCh]
  int v85; // [rsp+28h] [rbp-D8h]
  int v86; // [rsp+2Ch] [rbp-D4h]
  unsigned __int16 v87; // [rsp+30h] [rbp-D0h]
  __int16 v88; // [rsp+30h] [rbp-D0h]
  __int64 v89; // [rsp+38h] [rbp-C8h]
  unsigned __int16 v90; // [rsp+38h] [rbp-C8h]
  __int16 v91; // [rsp+38h] [rbp-C8h]
  __int64 v92; // [rsp+38h] [rbp-C8h]
  unsigned int v93; // [rsp+40h] [rbp-C0h]
  int v94; // [rsp+44h] [rbp-BCh]
  unsigned __int16 v95; // [rsp+48h] [rbp-B8h]
  int v96; // [rsp+4Ch] [rbp-B4h]
  unsigned __int64 v97; // [rsp+50h] [rbp-B0h]
  int v98; // [rsp+58h] [rbp-A8h]
  int v99; // [rsp+5Ch] [rbp-A4h]
  unsigned __int16 v100; // [rsp+60h] [rbp-A0h]
  __int64 v101; // [rsp+60h] [rbp-A0h]
  unsigned int v103; // [rsp+6Ch] [rbp-94h]
  unsigned int v104; // [rsp+70h] [rbp-90h]
  unsigned int v105; // [rsp+74h] [rbp-8Ch]
  unsigned int v106; // [rsp+78h] [rbp-88h]
  int v107; // [rsp+7Ch] [rbp-84h]
  unsigned int v108; // [rsp+80h] [rbp-80h]
  unsigned int v109; // [rsp+84h] [rbp-7Ch]
  unsigned int v110; // [rsp+88h] [rbp-78h]
  _WORD v111[4]; // [rsp+90h] [rbp-70h]
  _WORD *v112; // [rsp+98h] [rbp-68h]
  __int64 v113; // [rsp+A0h] [rbp-60h]
  _WORD v114[16]; // [rsp+A8h] [rbp-58h]
  unsigned int v115; // [rsp+C8h] [rbp-38h]
  unsigned int v116; // [rsp+CCh] [rbp-34h]
  _WORD v117[4]; // [rsp+D0h] [rbp-30h] BYREF
  _WORD v118[4]; // [rsp+D8h] [rbp-28h]
  _WORD v119[4]; // [rsp+E0h] [rbp-20h]
  _WORD v120[4]; // [rsp+E8h] [rbp-18h]
  _WORD v121[4]; // [rsp+F0h] [rbp-10h]
  _WORD v122[4]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v123; // [rsp+100h] [rbp+0h]
  __int64 v124; // [rsp+108h] [rbp+8h]
  __int64 v125; // [rsp+110h] [rbp+10h]
  unsigned int (__fastcall *v126)(__int64, __int64, _QWORD); // [rsp+118h] [rbp+18h]
  __int64 v127; // [rsp+120h] [rbp+20h]
  __int64 Cell; // [rsp+128h] [rbp+28h]
  __int64 v129; // [rsp+130h] [rbp+30h]
  __int64 v130; // [rsp+138h] [rbp+38h]
  __int64 v131; // [rsp+140h] [rbp+40h]
  __int64 v132; // [rsp+148h] [rbp+48h]
  __int64 v133; // [rsp+150h] [rbp+50h]
  __int64 v134; // [rsp+158h] [rbp+58h]
  __int64 v135; // [rsp+160h] [rbp+60h]
  __int64 v136; // [rsp+168h] [rbp+68h]

  v12 = a6;
  v13 = 0;
  v14 = a7;
  v15 = a3;
  v16 = a1;
  v17 = 0;
  v112 = a3;
  v125 = a2;
  v124 = a1;
  v113 = a6;
  v123 = a7;
  v126 = a8;
  v93 = 0;
  if ( a6 )
  {
    v17 = ((*(_DWORD *)(a6 + 4) * (unsigned int)*(unsigned __int16 *)(a6 + 14) + 31) >> 3) & 0x1FFFFFFC;
    v93 = v17;
  }
  v18 = *(_DWORD *)(a1 + 4) / 4;
  v108 = v18;
  if ( v18 >= 0x64 )
    v19 = (v18 < 0xC8) + 1;
  else
    v19 = 4;
  v20 = 0;
  result = 0;
  v22 = 0;
  v85 = 0;
  numberOfExtraSkips = 0;
  v98 = 0;
  numberOfEdges = 0;
  v97 = 0;
  numberOfSolids = 0;
  v99 = 0;
  numberOfSolid2 = 0;
  v110 = v19;
  v86 = 0;
  numberOfSkipCodes = 0;
  v96 = 0;
  numberOfSkips = 0;
  numberOfBlocks = 0;
  numberOfEvilRed = 0;
  if ( a11 )
  {
    v94 = 0;
    v84 = 0;
    v23 = 0;
    v115 = ((*(_DWORD *)(v16 + 4) * (unsigned int)*(unsigned __int16 *)(v16 + 14) + 31) >> 3) & 0x1FFFFFFC;
    v116 = *(_DWORD *)(v16 + 8) / 4;
    v24 = v116;
    v109 = 0;
    if ( !v116 )
    {
LABEL_104:
      *v15 = 0;
      return (unsigned int)(v23 + 2);
    }
    while ( 1 )
    {
      if ( v126 && !(v20 % v19) )
      {
        if ( v126(a9, 1, 100 * v20 / v24) )
          return 0xFFFFFFFFLL;
        v22 = numberOfSkipCodes;
        v16 = v124;
        v14 = v123;
        v96 = numberOfSkips;
        v85 = numberOfExtraSkips;
        v98 = numberOfEdges;
        v97 = __PAIR64__(numberOfBlocks, numberOfSolids);
        v86 = numberOfSkipCodes;
        v99 = numberOfSolid2;
      }
      v25 = v125;
      v127 = v14;
      v107 = 0;
      if ( v108 )
        break;
LABEL_94:
      v125 += 4 * v115;
      if ( v14 )
      {
        v14 += 4 * v17;
        v123 = v14;
      }
      v24 = v116;
      v20 = v109 + 1;
      v109 = v20;
      if ( v20 >= v116 )
      {
        if ( (_WORD)v13 )
        {
          do
          {
            v79 = 1023;
            if ( (unsigned __int16)v13 < 0x3FFu )
              v79 = v13;
            LOWORD(v13) = v13 - v79;
            ++v22;
            v23 += 2;
            *v15++ = v79 | 0x8400;
          }
          while ( (_WORD)v13 );
          numberOfSkipCodes = v22;
        }
        goto LABEL_104;
      }
      v19 = v110;
      v16 = v124;
    }
    while ( 1 )
    {
      Cell = GetCell(v16, v25, a10);
      if ( v12 )
      {
        v127 = GetCell(v113, v127, a10 + 8);
        if ( (unsigned int)CmpCell(a10, a10 + 8) <= a5 )
          goto LABEL_47;
      }
      v26 = 0;
      v27 = 0;
      v28 = 0;
      v29 = 0;
      v30 = 0;
      do
      {
        v31 = *((unsigned __int8 *)a10 + 4 * v29);
        v32 = *((unsigned __int8 *)a10 + 4 * v29 + 1);
        v28 += v31;
        v33 = *((unsigned __int8 *)a10 + 4 * v29 + 2);
        v27 += v32;
        v26 += v33;
        v34 = (30 * v33 + 59 * v32 + 11 * v31) / 0x64u;
        v114[v29] = v34;
        v30 += (unsigned __int16)v34;
        ++v29;
      }
      while ( v29 != 16 );
      v13 = v84;
      v80 = v30;
      v17 = v93;
      v89 = *(unsigned __int8 *)((((unsigned __int64)(unsigned __int8)(v28 >> 4) >> 3)
                                | (4
                                 * ((unsigned __int8)(v27 >> 4) & 0xF8 | (32LL * ((unsigned __int8)(v26 >> 4) & 0xF8)))))
                               + a11);
      v35 = _mm_shuffle_epi32(_mm_cvtsi32_si128(*(_DWORD *)(a12 + 4 * v89)), 0);
      a10[4] = v35;
      a10[5] = v35;
      a10[6] = v35;
      a10[7] = v35;
      if ( (unsigned int)CmpCell(a10, a10 + 4) <= a4 )
      {
        if ( v113 && (unsigned int)CmpCell(a10 + 4, a10 + 8) <= a5 )
          goto LABEL_46;
        if ( (_WORD)v84 )
        {
          do
          {
            if ( (unsigned __int16)v13 >= 0x3FFu )
              v36 = 1023;
            else
              v36 = v13;
            LOWORD(v13) = v13 - v36;
            numberOfSkipCodes = ++v22;
            *v15 = v36 | 0x8400;
            v23 += 2;
            ++v15;
          }
          while ( (_WORD)v13 );
          v86 = v22;
          v84 = v13;
        }
        v37 = v89;
        goto LABEL_27;
      }
      v38 = v80 >> 4;
      v39 = 0;
      v81 = 0;
      v40 = 0;
      v41 = 0;
      v42 = 0;
      v100 = 0;
      v43 = 0;
      LOWORD(v44) = 0;
      v45 = 0;
      v46 = 0;
      v47 = 0;
      do
      {
        v48 = *((unsigned __int8 *)a10 + 4 * v46 + 2);
        if ( v114[v46] >= (unsigned __int16)v38 )
        {
          v41 += v48;
          LOWORD(v49) = v81;
          v42 += *((unsigned __int8 *)a10 + 4 * v46 + 1);
          ++v40;
          v44 = (unsigned __int16)v44 | (1 << v45);
          v43 += *((unsigned __int8 *)a10 + 4 * v46);
        }
        else
        {
          v47 += v48;
          ++v39;
          HIWORD(v49) = HIWORD(v81);
          LOWORD(v49) = *((unsigned __int8 *)a10 + 4 * v46 + 1) + (_WORD)v81;
          v100 += *((unsigned __int8 *)a10 + 4 * v46);
          v81 = v49;
        }
        ++v45;
        ++v46;
      }
      while ( v45 < 0x10 );
      v95 = v47;
      v15 = v112;
      v90 = v43;
      v23 = v94;
      v87 = v42;
      v13 = v84;
      v82 = v41;
      v22 = v86;
      if ( v40 )
      {
        v83 = v82 / v40;
        v120[0] = v83;
        v88 = v87 / v40;
        v121[0] = v88;
        v91 = v90 / v40;
        v122[0] = v91;
      }
      else
      {
        LOBYTE(v91) = 0;
        v122[0] = 0;
        LOBYTE(v88) = 0;
        v121[0] = 0;
        LOBYTE(v83) = 0;
        v120[0] = 0;
      }
      if ( v39 )
      {
        v50 = v39;
        v51 = v95 / v39;
        v118[0] = v95 / v39;
        v52 = (unsigned __int16)v49 / v39;
        v119[0] = v52;
        v53 = v100 / v50;
        v117[0] = v53;
      }
      else
      {
        LOBYTE(v53) = 0;
        v117[0] = 0;
        LOBYTE(v52) = 0;
        v119[0] = 0;
        LOBYTE(v51) = 0;
        v118[0] = 0;
      }
      v101 = *(unsigned __int8 *)((((unsigned __int64)(unsigned __int8)v53 >> 3)
                                 | (4 * ((unsigned __int8)v52 & 0xF8 | (32LL * ((unsigned __int8)v51 & 0xF8)))))
                                + a11);
      v54 = *(_DWORD *)(a12 + 4 * v101);
      v92 = *(unsigned __int8 *)((((unsigned __int64)(unsigned __int8)v91 >> 3)
                                | (4 * ((unsigned __int8)v88 & 0xF8 | (32LL * ((unsigned __int8)v83 & 0xF8)))))
                               + a11);
      v55 = *(_DWORD *)(a12 + 4 * v92);
      for ( i = 0; i != 16; ++i )
      {
        v57 = v55;
        if ( v114[i] < (unsigned __int16)v38 )
          v57 = v54;
        *((_DWORD *)a10 + i + 16) = v57;
      }
      if ( (unsigned int)CmpCell(a10, a10 + 4) > a4 )
        break;
      if ( v113 && (unsigned int)CmpCell(a10 + 4, a10 + 8) <= a5 )
      {
LABEL_46:
        numberOfExtraSkips = ++v85;
LABEL_47:
        LOWORD(v13) = v13 + 1;
        ++v96;
        v84 = v13;
        numberOfSkips = v96;
        goto LABEL_92;
      }
      if ( (_WORD)v84 )
      {
        do
        {
          if ( (unsigned __int16)v13 >= 0x3FFu )
            v58 = 1023;
          else
            v58 = v13;
          LOWORD(v13) = v13 - v58;
          numberOfSkipCodes = ++v22;
          *v15 = v58 | 0x8400;
          v23 += 2;
          ++v15;
        }
        while ( (_WORD)v13 );
        v86 = v22;
        v84 = v13;
      }
      if ( (_WORD)v44 )
      {
        v37 = v92;
        if ( (_WORD)v44 != 0xFFFF )
        {
          v59 = v101;
          if ( (_BYTE)v101 != (_BYTE)v92 )
          {
            if ( (v44 & 0x8000u) != 0 )
            {
              v37 = v101;
              LOWORD(v44) = ~(_WORD)v44;
              v59 = v92;
            }
            v23 += 4;
            *v15 = v44;
            v15[1] = v37 | (v59 << 8);
            v15 += 2;
            v112 = v15;
            numberOfBlocks = ++HIDWORD(v97);
            v94 = v23;
            goto LABEL_92;
          }
        }
      }
      else
      {
        v37 = v101;
      }
LABEL_27:
      *v15++ = v37 | 0x8000;
      v112 = v15;
      v23 += 2;
      LODWORD(v97) = v97 + 1;
      v94 = v23;
      numberOfSolids = v97;
LABEL_92:
      v12 = v113;
      v78 = v107 + 1 < v108;
      v16 = v124;
      ++v107;
      v25 = Cell;
      if ( !v78 )
      {
        v14 = v123;
        goto LABEL_94;
      }
    }
    v60 = 0;
    if ( (_WORD)v84 )
    {
      do
      {
        if ( (unsigned __int16)v13 >= 0x3FFu )
          v61 = 1023;
        else
          v61 = v13;
        LOWORD(v13) = v13 - v61;
        numberOfSkipCodes = ++v22;
        *v15 = v61 | 0x8400;
        v23 += 2;
        ++v15;
      }
      while ( (_WORD)v13 );
      v86 = v22;
      v84 = v13;
    }
    ++v98;
    LOWORD(v62) = 0;
    numberOfEdges = v98;
    v63 = 0;
    v136 = 0;
    v132 = 0;
    v130 = 0;
    v111[0] = (v114[5] + v114[4] + v114[1] + (unsigned int)v114[0]) >> 2;
    v134 = 0;
    v129 = 0;
    v133 = 0;
    v111[1] = (v114[7] + v114[6] + v114[3] + (unsigned int)v114[2]) >> 2;
    v131 = 0;
    v135 = 0;
    v111[2] = (v114[13] + v114[12] + v114[9] + (unsigned int)v114[8]) >> 2;
    v111[3] = (v114[15] + v114[14] + v114[11] + (unsigned int)v114[10]) >> 2;
    do
    {
      v64 = *((unsigned __int8 *)a10 + 4 * v60 + 2);
      v65 = *((unsigned __int8 *)meanIndex + v60);
      v66 = *((unsigned __int8 *)a10 + 4 * v60 + 1);
      v67 = *((unsigned __int8 *)a10 + 4 * v60);
      if ( v114[v60] >= v111[v65] )
      {
        ++*((_WORD *)&v132 + v65);
        *((_WORD *)&v134 + v65) += v64;
        *((_WORD *)&v133 + v65) += v66;
        v62 = (unsigned __int16)v62 | (1 << v63);
        *((_WORD *)&v135 + v65) += v67;
      }
      else
      {
        ++*((_WORD *)&v136 + v65);
        *((_WORD *)&v130 + v65) += v64;
        *((_WORD *)&v129 + v65) += v66;
        *((_WORD *)&v131 + v65) += v67;
      }
      ++v63;
      ++v60;
    }
    while ( v63 < 0x10 );
    v17 = v93;
    v68 = 0;
    v69 = v62 ^ 0xCC00;
    v70 = (unsigned __int16)v62;
    if ( (v62 & 0x8000u) != 0 )
      v69 = v62;
    LOWORD(v70) = v62 & 0x2000;
    v71 = v69 ^ 0x3300;
    if ( (v62 & 0x2000) != 0 )
      v71 = v69;
    *v15++ = v71;
    v23 += 2;
    while ( 1 )
    {
      v72 = v68;
      LOWORD(v73) = 0;
      v74 = *((unsigned __int16 *)&v132 + v68);
      if ( (_WORD)v74 )
      {
        v104 = *((unsigned __int16 *)&v133 + v68) / v74;
        v103 = *((unsigned __int16 *)&v134 + v68) / v74;
        v70 = *((unsigned __int16 *)&v135 + v68) % v74;
        v75 = *((unsigned __int16 *)&v135 + v68) / v74;
        LOWORD(v73) = 0;
      }
      else
      {
        if ( v72 >= 4 )
          goto LABEL_106;
        LOWORD(v104) = 0;
        LOWORD(v75) = 0;
        LOWORD(v103) = 0;
      }
      v122[v72] = v75;
      v120[v68] = v103;
      v121[v68] = v104;
      v76 = *((unsigned __int16 *)&v136 + v68);
      if ( (_WORD)v76 )
      {
        v106 = *((unsigned __int16 *)&v129 + v68) / v76;
        v105 = *((unsigned __int16 *)&v130 + v68) / v76;
        v73 = *((unsigned __int16 *)&v131 + v68) / v76;
      }
      else
      {
        if ( v72 >= 4 )
LABEL_106:
          _report_rangecheckfailure(0, v70);
        LOWORD(v106) = 0;
        LOWORD(v105) = 0;
      }
      v70 = (unsigned __int64)v117;
      v117[v68] = v73;
      v118[v68] = v105;
      v119[v68] = v106;
      LOBYTE(v70) = *(_BYTE *)((((unsigned __int64)LOBYTE(v117[v68]) >> 3)
                              | (4 * ((unsigned __int8)v106 & 0xF8 | (32LL * (v118[v68] & 0xF8)))))
                             + a11);
      if ( (_DWORD)v68 != 3 )
        break;
      v77 = *(_BYTE *)((((unsigned __int64)LOBYTE(v122[v68]) >> 3)
                      | (4 * (v121[v68] & 0xF8 | (32LL * (v120[v68] & 0xF8)))))
                     + a11);
      if ( (v62 & 0x8000u) == 0 )
        goto LABEL_87;
LABEL_91:
      v23 += 2;
      ++v99;
      v68 = (unsigned int)(v68 + 1);
      numberOfSolid2 = v99;
      v94 = v23;
      *v15++ = v77 | ((unsigned __int8)v70 << 8);
      v112 = v15;
      if ( (unsigned int)v68 >= 4 )
        goto LABEL_92;
    }
    if ( (_DWORD)v68 != 2 || (v62 & 0x2000) != 0 )
    {
      v77 = *(_BYTE *)((((unsigned __int64)LOBYTE(v122[v68]) >> 3)
                      | (4 * (v121[v68] & 0xF8 | (32LL * (v120[v68] & 0xF8)))))
                     + a11);
      goto LABEL_91;
    }
LABEL_87:
    v77 = *(_BYTE *)((((unsigned __int64)LOBYTE(v117[v68]) >> 3)
                    | (4 * ((unsigned __int8)v106 & 0xF8 | (32LL * (v118[v68] & 0xF8)))))
                   + a11);
    LOBYTE(v70) = *(_BYTE *)((((unsigned __int64)LOBYTE(v122[v68]) >> 3)
                            | (4 * (v121[v68] & 0xF8 | (32LL * (v120[v68] & 0xF8)))))
                           + a11);
    goto LABEL_91;
  }
  return result;
}

```

## disassembly

```asm
0x180002920  mov     [rsp-8+arg_18], rbx
0x180002925  push    rbp
0x180002926  push    rsi
0x180002927  push    rdi
0x180002928  push    r12
0x18000292a  push    r13
0x18000292c  push    r14
0x18000292e  push    r15
0x180002930  lea     rbp, [rsp-80h]
0x180002935  sub     rsp, 180h
0x18000293c  mov     rax, cs:__security_cookie
0x180002943  xor     rax, rsp
0x180002946  mov     [rbp+0B0h+var_40], rax
0x18000294a  mov     rbx, [rbp+0B0h+arg_28]
0x180002951  xor     edi, edi
0x180002953  mov     r11, [rbp+0B0h+arg_30]
0x18000295a  mov     rsi, r8
0x18000295d  mov     rax, [rbp+0B0h+arg_38]
0x180002964  mov     r10, rcx
0x180002967  mov     r13, [rbp+0B0h+arg_48]
0x18000296e  mov     r12d, edi
0x180002971  mov     [rsp+1B0h+var_148], r9d
0x180002976  mov     r14d, 1FFFFFFCh
0x18000297c  mov     [rbp+0B0h+var_118], r8
0x180002980  mov     [rbp+0B0h+var_A0], rdx
0x180002984  mov     [rbp+0B0h+var_A8], rcx
0x180002988  mov     [rbp+0B0h+var_110], rbx
0x18000298c  mov     [rbp+0B0h+var_B0], r11
0x180002990  mov     [rbp+0B0h+var_98], rax
0x180002994  mov     [rsp+1B0h+var_170], edi
0x180002998  test    rbx, rbx
0x18000299b  jz      short loc_1800029B7
0x18000299d  movzx   r12d, word ptr [rbx+0Eh]
0x1800029a2  imul    r12d, [rbx+4]
0x1800029a7  add     r12d, 1Fh
0x1800029ab  shr     r12d, 3
0x1800029af  and     r12d, r14d
0x1800029b2  mov     [rsp+1B0h+var_170], r12d
0x1800029b7  mov     eax, [rcx+4]
0x1800029ba  cdq
0x1800029bb  and     edx, 3
0x1800029be  add     eax, edx
0x1800029c0  sar     eax, 2
0x1800029c3  mov     [rbp+0B0h+var_130], eax
0x1800029c6  cmp     eax, 64h ; 'd'
0x1800029c9  jnb     short loc_1800029D3
0x1800029cb  mov     r8d, 4
0x1800029d1  jmp     short loc_1800029E1
0x1800029d3  cmp     eax, 0C8h
0x1800029d8  sbb     r8d, r8d
0x1800029db  neg     r8d
0x1800029de  inc     r8d
0x1800029e1  mov     ecx, edi
0x1800029e3  mov     eax, edi
0x1800029e5  mov     r15d, edi
0x1800029e8  mov     [rsp+1B0h+var_188], ecx
0x1800029ec  mov     cs:numberOfExtraSkips, ecx
0x1800029f2  mov     [rsp+1B0h+var_158], eax
0x1800029f6  mov     cs:numberOfEdges, eax
0x1800029fc  mov     dword ptr [rsp+1B0h+var_160], ecx
0x180002a00  mov     cs:numberOfSolids, ecx
0x180002a06  mov     [rsp+1B0h+var_154], ecx
0x180002a0a  mov     cs:numberOfSolid2, ecx
0x180002a10  mov     [rbp+0B0h+var_128], r8d
0x180002a14  mov     [rsp+1B0h+var_184], edi
0x180002a18  mov     cs:numberOfSkipCodes, edi
0x180002a1e  mov     [rsp+1B0h+var_164], edi
0x180002a22  mov     cs:numberOfSkips, edi
0x180002a28  mov     dword ptr [rsp+1B0h+var_160+4], edi
0x180002a2c  mov     cs:numberOfBlocks, edi
0x180002a32  mov     cs:numberOfEvilRed, edi
0x180002a38  cmp     [rbp+0B0h+arg_50], rdi
0x180002a3f  jz      loc_180003423
0x180002a45  movzx   eax, word ptr [r10+0Eh]
0x180002a4a  imul    eax, [r10+4]
0x180002a4f  mov     [rsp+1B0h+var_16C], edi
0x180002a53  mov     [rsp+1B0h+var_18C], edi
0x180002a57  add     eax, 1Fh
0x180002a5a  shr     eax, 3
0x180002a5d  and     eax, r14d
0x180002a60  mov     r14d, edi
0x180002a63  mov     [rbp+0B0h+var_E8], eax
0x180002a66  mov     eax, [r10+8]
0x180002a6a  cdq
0x180002a6b  and     edx, 3
0x180002a6e  add     eax, edx
0x180002a70  xor     edx, edx
0x180002a72  sar     eax, 2
0x180002a75  mov     [rbp+0B0h+var_E4], eax
0x180002a78  mov     r9d, eax
0x180002a7b  mov     [rbp+0B0h+var_12C], edx
0x180002a7e  test    eax, eax
0x180002a80  jz      loc_18000341C
0x180002a86  cmp     [rbp+0B0h+var_98], rdx
0x180002a8a  jz      loc_180002B19
0x180002a90  xor     edx, edx
0x180002a92  mov     eax, ecx
0x180002a94  div     r8d
0x180002a97  test    edx, edx
0x180002a99  jnz     short loc_180002B17
0x180002a9b  imul    eax, ecx, 64h ; 'd'
0x180002a9e  xor     edx, edx
0x180002aa0  mov     rcx, [rbp+0B0h+arg_40]
0x180002aa7  div     r9d
0x180002aaa  mov     edx, 1
0x180002aaf  mov     r8d, eax
0x180002ab2  mov     rax, [rbp+0B0h+var_98]
0x180002ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002abb  xor     edx, edx
0x180002abd  test    eax, eax
0x180002abf  jnz     loc_1800033E4
0x180002ac5  mov     eax, cs:numberOfSkips
0x180002acb  mov     r15d, cs:numberOfSkipCodes
0x180002ad2  mov     ecx, cs:numberOfSolid2
0x180002ad8  mov     r10, [rbp+0B0h+var_A8]
0x180002adc  mov     r11, [rbp+0B0h+var_B0]
0x180002ae0  mov     [rsp+1B0h+var_164], eax
0x180002ae4  mov     eax, cs:numberOfExtraSkips
0x180002aea  mov     [rsp+1B0h+var_188], eax
0x180002aee  mov     eax, cs:numberOfEdges
0x180002af4  mov     [rsp+1B0h+var_158], eax
0x180002af8  mov     eax, cs:numberOfBlocks
0x180002afe  mov     dword ptr [rsp+1B0h+var_160+4], eax
0x180002b02  mov     eax, cs:numberOfSolids
0x180002b08  mov     dword ptr [rsp+1B0h+var_160], eax
0x180002b0c  mov     [rsp+1B0h+var_184], r15d
0x180002b11  mov     [rsp+1B0h+var_154], ecx
0x180002b15  jmp     short loc_180002B19
0x180002b17  xor     edx, edx
0x180002b19  mov     rax, [rbp+0B0h+var_A0]
0x180002b1d  mov     [rbp+0B0h+var_90], r11
0x180002b21  mov     [rsp+1B0h+var_134], edx
0x180002b25  cmp     [rbp+0B0h+var_130], edx
0x180002b28  jbe     loc_1800033A1
0x180002b2e  mov     r8, r13
0x180002b31  mov     rdx, rax
0x180002b34  mov     rcx, r10
0x180002b37  call    GetCell
0x180002b3c  mov     [rbp+0B0h+var_88], rax
0x180002b40  xor     eax, eax
0x180002b42  test    rbx, rbx
0x180002b45  jz      short loc_180002B7B
0x180002b47  mov     rdx, [rbp+0B0h+var_90]
0x180002b4b  lea     rbx, [r13+80h]
0x180002b52  mov     rcx, [rbp+0B0h+var_110]
0x180002b56  mov     r8, rbx
0x180002b59  call    GetCell
0x180002b5e  mov     rdx, rbx
0x180002b61  mov     [rbp+0B0h+var_90], rax
0x180002b65  mov     rcx, r13
0x180002b68  call    CmpCell
0x180002b6d  cmp     eax, [rbp+0B0h+arg_20]
0x180002b73  jbe     loc_180002F4E
0x180002b79  xor     eax, eax
0x180002b7b  mov     [rsp+1B0h+var_190], eax
0x180002b7f  mov     r10d, eax
0x180002b82  mov     r11d, eax
0x180002b85  mov     ebx, eax
0x180002b87  mov     r9, rax
0x180002b8a  mov     r12d, eax
0x180002b8d  movzx   eax, byte ptr [r13+r9*4+0]
0x180002b93  movzx   ecx, byte ptr [r13+r9*4+1]
0x180002b99  add     bx, ax
0x180002b9c  movzx   r8d, byte ptr [r13+r9*4+2]
0x180002ba2  add     r11w, cx
0x180002ba6  imul    edx, eax, 0Bh
0x180002ba9  add     r10w, r8w
0x180002bad  imul    eax, ecx, 3Bh ; ';'
0x180002bb0  add     edx, eax
0x180002bb2  imul    eax, r8d, 1Eh
0x180002bb6  add     edx, eax
0x180002bb8  mov     eax, 51EB851Fh
0x180002bbd  mul     edx
0x180002bbf  shr     edx, 5
0x180002bc2  movzx   eax, dx
0x180002bc5  mov     [rbp+r9*2+0B0h+var_108], ax
0x180002bcb  add     r12d, eax
0x180002bce  inc     r9
0x180002bd1  cmp     r9, 10h
0x180002bd5  jnz     short loc_180002B8D
0x180002bd7  mov     edi, [rsp+1B0h+var_18C]
0x180002bdb  shr     r10w, 4
0x180002be0  movzx   ecx, r10b
0x180002be4  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180002be8  shr     r11w, 4
0x180002bed  shl     rcx, 5
0x180002bf1  movzx   eax, r11b
0x180002bf5  and     rax, 0FFFFFFFFFFFFFFF8h
0x180002bf9  shr     bx, 4
0x180002bfd  or      rcx, rax
0x180002c00  mov     [rsp+1B0h+var_190], r12d
0x180002c05  mov     r12d, [rsp+1B0h+var_170]
0x180002c0a  shl     rcx, 2
0x180002c0e  movzx   eax, bl
0x180002c11  lea     rbx, [r13+40h]
0x180002c15  shr     rax, 3
0x180002c19  mov     rdx, rbx
0x180002c1c  or      rcx, rax
0x180002c1f  mov     rax, [rbp+0B0h+arg_50]
0x180002c26  movzx   eax, byte ptr [rcx+rax]
0x180002c2a  mov     rcx, [rbp+0B0h+arg_58]
0x180002c31  mov     [rsp+1B0h+var_178], rax
0x180002c36  movd    xmm0, dword ptr [rcx+rax*4]
0x180002c3b  mov     rcx, r13
0x180002c3e  pshufd  xmm0, xmm0, 0
0x180002c43  movups  xmmword ptr [rbx], xmm0
0x180002c46  movups  xmmword ptr [rbx+10h], xmm0
0x180002c4a  movups  xmmword ptr [rbx+20h], xmm0
0x180002c4e  movups  xmmword ptr [rbx+30h], xmm0
0x180002c52  call    CmpCell
0x180002c57  cmp     eax, [rsp+1B0h+var_148]
0x180002c5b  ja      loc_180002CF9
0x180002c61  xor     ecx, ecx
0x180002c63  cmp     [rbp+0B0h+var_110], rcx
0x180002c67  jz      short loc_180002C84
0x180002c69  lea     rdx, [r13+80h]
0x180002c70  mov     rcx, rbx
0x180002c73  call    CmpCell
0x180002c78  cmp     eax, [rbp+0B0h+arg_20]
0x180002c7e  jbe     loc_180002F3E
0x180002c84  test    di, di
0x180002c87  jz      short loc_180002CC4
0x180002c89  mov     edx, 3FFh
0x180002c8e  cmp     di, dx
0x180002c91  jnb     short loc_180002C98
0x180002c93  movzx   eax, di
0x180002c96  jmp     short loc_180002C9A
0x180002c98  mov     eax, edx
0x180002c9a  sub     di, ax
0x180002c9d  inc     r15d
0x180002ca0  or      ax, 8400h
0x180002ca4  mov     cs:numberOfSkipCodes, r15d
0x180002cab  mov     [rsi], ax
0x180002cae  add     r14d, 2
0x180002cb2  add     rsi, 2
0x180002cb6  test    di, di
0x180002cb9  jnz     short loc_180002C8E
0x180002cbb  mov     [rsp+1B0h+var_184], r15d
0x180002cc0  mov     [rsp+1B0h+var_18C], edi
0x180002cc4  mov     rax, [rsp+1B0h+var_178]
0x180002cc9  movzx   eax, al
0x180002ccc  or      ax, 8000h
0x180002cd0  mov     [rsi], ax
0x180002cd3  add     rsi, 2
0x180002cd7  mov     eax, dword ptr [rsp+1B0h+var_160]
0x180002cdb  inc     eax
0x180002cdd  mov     [rbp+0B0h+var_118], rsi
0x180002ce1  add     r14d, 2
0x180002ce5  mov     dword ptr [rsp+1B0h+var_160], eax
0x180002ce9  mov     [rsp+1B0h+var_16C], r14d
0x180002cee  mov     cs:numberOfSolids, eax
0x180002cf4  jmp     loc_18000337C
0x180002cf9  mov     r11d, [rsp+1B0h+var_190]
0x180002cfe  shr     r11d, 4
0x180002d02  xor     eax, eax
0x180002d04  mov     [rsp+1B0h+var_190], eax
0x180002d08  mov     r9d, eax
0x180002d0b  mov     [rsp+1B0h+var_190], eax
0x180002d0f  mov     r8d, eax
0x180002d12  mov     [rsp+1B0h+var_168], eax
0x180002d16  mov     r15d, eax
0x180002d19  mov     edi, eax
0x180002d1b  mov     dword ptr [rsp+1B0h+var_180], eax
0x180002d1f  mov     dword ptr [rsp+1B0h+var_150], eax
0x180002d23  mov     r14d, eax
0x180002d26  mov     dword ptr [rsp+1B0h+var_178], eax
0x180002d2a  mov     ebx, eax
0x180002d2c  mov     edx, eax
0x180002d2e  mov     ecx, eax
0x180002d30  mov     esi, eax
0x180002d32  movzx   r10d, byte ptr [r13+rcx*4+2]
0x180002d38  movzx   eax, byte ptr [r13+rcx*4+1]
0x180002d3e  cmp     [rbp+rcx*2+0B0h+var_108], r11w
0x180002d44  jnb     short loc_180002D69
0x180002d46  add     si, r10w
0x180002d4a  inc     r9w
0x180002d4e  mov     r10d, [rsp+1B0h+var_190]
0x180002d53  add     r10w, ax
0x180002d57  movzx   eax, byte ptr [r13+rcx*4+0]
0x180002d5d  add     word ptr [rsp+1B0h+var_150], ax
0x180002d62  mov     [rsp+1B0h+var_190], r10d
0x180002d67  jmp     short loc_180002D8F
0x180002d69  movzx   eax, byte ptr [r13+rcx*4+1]
0x180002d6f  add     r15w, r10w
0x180002d73  mov     r10d, [rsp+1B0h+var_190]
0x180002d78  add     di, ax
0x180002d7b  movzx   eax, byte ptr [r13+rcx*4+0]
0x180002d81  inc     r8w
0x180002d85  movzx   ebx, bx
0x180002d88  bts     ebx, edx
0x180002d8b  add     r14w, ax
0x180002d8f  mov     eax, 1
0x180002d94  add     edx, eax
0x180002d96  add     rcx, rax
0x180002d99  cmp     edx, 10h
0x180002d9c  jb      short loc_180002D32
0x180002d9e  xor     ecx, ecx
0x180002da0  mov     [rsp+1B0h+var_168], esi
0x180002da4  mov     rsi, [rbp+0B0h+var_118]
0x180002da8  mov     dword ptr [rsp+1B0h+var_178], r14d
  ... truncated ...
```
