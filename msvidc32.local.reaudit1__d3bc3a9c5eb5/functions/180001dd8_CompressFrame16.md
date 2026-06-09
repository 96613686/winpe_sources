# CompressFrame16

- ea: `0x180001dd8`
- end: `0x180002919`
- name: `CompressFrame16`
- size: `2881`
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
- `0x180001dd8`
- `0x180003640`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall CompressFrame16(
        __int64 a1,
        __int64 a2,
        _WORD *a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        unsigned int (__fastcall *a8)(__int64, __int64, _QWORD),
        __int64 a9,
        _OWORD *a10)
{
  unsigned int v10; // ebx
  __int64 v11; // r12
  __int64 v12; // r11
  _OWORD *v13; // r15
  _WORD *v14; // rdi
  int v15; // eax
  __int64 v16; // r9
  int v17; // ecx
  __int64 v18; // r8
  __int64 v19; // kr08_8
  unsigned int v20; // r10d
  unsigned int v21; // ecx
  int v22; // r14d
  int v23; // r13d
  int v24; // esi
  __int64 v25; // rax
  unsigned int v26; // r11d
  unsigned __int16 v27; // bx
  unsigned __int16 v28; // r9
  unsigned __int16 v29; // r12
  __int64 i; // r10
  int v31; // eax
  int v32; // ecx
  int v33; // r8d
  unsigned int v34; // edx
  __int16 v35; // r9
  __int16 v36; // bx
  unsigned __int16 v37; // r12
  __m128i v38; // xmm0
  unsigned int v39; // eax
  __int16 v40; // ax
  __int16 v41; // ax
  int v42; // ecx
  unsigned int v43; // r8d
  unsigned __int16 v44; // r10
  unsigned __int16 v45; // r9
  unsigned __int16 v46; // r13
  unsigned __int16 v47; // di
  unsigned __int16 v48; // si
  unsigned __int16 v49; // r14
  int v50; // r12d
  unsigned int v51; // edx
  __int64 v52; // rcx
  __int16 v53; // r11
  __int16 v54; // bx
  int v55; // r11d
  __int64 j; // rax
  char v57; // cl
  char v58; // dl
  char v59; // r9
  unsigned int v60; // eax
  __int16 v61; // ax
  __int16 v62; // cx
  unsigned __int16 v63; // ax
  __int16 v64; // cx
  __int16 v65; // cx
  __int16 v66; // ax
  int v67; // r9d
  unsigned int v68; // r8d
  __int64 v69; // rdx
  __int16 v70; // r10
  __int64 v71; // rcx
  __int16 v72; // r11
  __int16 v73; // bx
  __int16 v74; // ax
  unsigned int v75; // r11d
  unsigned __int64 v76; // r8
  unsigned int v77; // eax
  unsigned int v78; // r10d
  unsigned int v79; // r9d
  unsigned int v80; // eax
  unsigned int v81; // eax
  unsigned int v82; // r9d
  unsigned __int16 v83; // r9
  __int16 v84; // r10
  bool v85; // cf
  __int16 v87; // ax
  __int16 v88; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v89; // [rsp+20h] [rbp-E0h]
  __int16 v90; // [rsp+20h] [rbp-E0h]
  int v91; // [rsp+24h] [rbp-DCh]
  int v92; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v93; // [rsp+28h] [rbp-D8h]
  unsigned int v94; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v95; // [rsp+30h] [rbp-D0h]
  __int16 v96; // [rsp+30h] [rbp-D0h]
  int v97; // [rsp+38h] [rbp-C8h]
  int v98; // [rsp+3Ch] [rbp-C4h]
  unsigned int v99; // [rsp+40h] [rbp-C0h]
  int v100; // [rsp+44h] [rbp-BCh]
  unsigned __int16 v101; // [rsp+48h] [rbp-B8h]
  int v102; // [rsp+4Ch] [rbp-B4h]
  int v103; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v104; // [rsp+54h] [rbp-ACh]
  int v105; // [rsp+5Ch] [rbp-A4h]
  unsigned __int16 v106; // [rsp+60h] [rbp-A0h]
  _WORD v107[4]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v108[4]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v109[4]; // [rsp+78h] [rbp-88h]
  _WORD v110[4]; // [rsp+80h] [rbp-80h]
  _WORD v111[4]; // [rsp+88h] [rbp-78h]
  _WORD v112[4]; // [rsp+90h] [rbp-70h]
  unsigned int v113; // [rsp+98h] [rbp-68h]
  unsigned int v114; // [rsp+9Ch] [rbp-64h]
  int v115; // [rsp+A0h] [rbp-60h]
  unsigned int v116; // [rsp+A4h] [rbp-5Ch]
  unsigned int v117; // [rsp+A8h] [rbp-58h]
  unsigned int v118; // [rsp+ACh] [rbp-54h]
  unsigned int v119; // [rsp+B0h] [rbp-50h]
  _WORD v120[4]; // [rsp+B8h] [rbp-48h]
  _WORD *v121; // [rsp+C0h] [rbp-40h]
  _WORD v122[16]; // [rsp+C8h] [rbp-38h]
  unsigned int v123; // [rsp+E8h] [rbp-18h]
  unsigned int v124; // [rsp+ECh] [rbp-14h]
  __int64 v125; // [rsp+F0h] [rbp-10h]
  __int64 v126; // [rsp+F8h] [rbp-8h]
  __int64 v127; // [rsp+100h] [rbp+0h]
  __int64 v128; // [rsp+108h] [rbp+8h]
  unsigned int (__fastcall *v129)(__int64, __int64, _QWORD); // [rsp+110h] [rbp+10h]
  __int64 v130; // [rsp+118h] [rbp+18h]
  __int64 v131; // [rsp+120h] [rbp+20h]
  __int64 v132; // [rsp+128h] [rbp+28h]
  __int64 Cell; // [rsp+130h] [rbp+30h]
  __int64 v134; // [rsp+138h] [rbp+38h]
  __int64 v135; // [rsp+140h] [rbp+40h]
  __int64 v136; // [rsp+148h] [rbp+48h]
  __int64 v137; // [rsp+150h] [rbp+50h]
  __int64 v138; // [rsp+158h] [rbp+58h]
  __int64 v139; // [rsp+160h] [rbp+60h]
  __int64 v140; // [rsp+168h] [rbp+68h]
  __int64 v141; // [rsp+170h] [rbp+70h]

  v10 = 0;
  v11 = a6;
  v12 = a2;
  v13 = a10;
  v14 = a3;
  v128 = a1;
  v129 = a8;
  v15 = *(_DWORD *)(a1 + 4);
  v113 = a4;
  v16 = a1;
  v17 = v15 * *(unsigned __int16 *)(a1 + 14);
  v126 = a2;
  v121 = a3;
  v18 = a7;
  v125 = a6;
  v127 = a7;
  v131 = (__int64)a10;
  v119 = 0;
  HIBYTE(v99) = 0;
  v123 = ((unsigned int)(v17 + 31) >> 3) & 0x1FFFFFFC;
  if ( a6 )
    v119 = ((*(_DWORD *)(a6 + 4) * (unsigned int)*(unsigned __int16 *)(a6 + 14) + 31) >> 3) & 0x1FFFFFFC;
  v19 = *(int *)(v16 + 8);
  v116 = v15 / 4;
  v20 = ((BYTE4(v19) & 3) + (int)v19) >> 2;
  v124 = v20;
  v132 = 1;
  if ( (unsigned int)(v15 / 4) >= 0x64 )
    v21 = ((unsigned int)(v15 / 4) < 0xC8) + 1;
  else
    v21 = 4;
  v118 = v21;
  v100 = 0;
  v22 = 0;
  v98 = 0;
  v23 = 0;
  numberOfSkipCodes = 0;
  v24 = 0;
  v102 = 0;
  numberOfSkips = 0;
  v97 = 0;
  numberOfExtraSkips = 0;
  v105 = 0;
  numberOfEdges = 0;
  numberOfBlocks = 0;
  v104 = 0;
  numberOfSolids = 0;
  numberOfSolid2 = 0;
  v103 = 0;
  numberOfEvilRed = 0;
  v91 = 0;
  v117 = 0;
  if ( !v20 )
    goto LABEL_102;
  while ( 2 )
  {
    if ( v129 && !(v10 % v21) )
    {
      if ( v129(a9, 1, 100 * v10 / v20) )
        return 0xFFFFFFFFLL;
      v23 = numberOfSkipCodes;
      v16 = v128;
      v18 = v127;
      v12 = v126;
      v102 = numberOfSkips;
      v97 = numberOfExtraSkips;
      v105 = numberOfEdges;
      v104 = __PAIR64__(numberOfBlocks, numberOfSolids);
      v98 = numberOfSkipCodes;
      v103 = numberOfEvilRed;
    }
    v25 = v12;
    v130 = v18;
    v115 = 0;
    if ( !v116 )
      goto LABEL_92;
    do
    {
      Cell = GetCell(v16, v25, v13);
      if ( v11 )
      {
        v130 = GetCell(v11, v130, v13 + 8);
        if ( (unsigned int)CmpCell(v13, v13 + 8) <= a5 )
          goto LABEL_52;
      }
      v26 = 0;
      v27 = 0;
      v28 = 0;
      v29 = 0;
      for ( i = 0; i != 16; ++i )
      {
        v31 = *((unsigned __int8 *)v13 + 4 * i);
        v32 = *((unsigned __int8 *)v13 + 4 * i + 1);
        v29 += v31;
        v33 = *((unsigned __int8 *)v13 + 4 * i + 2);
        v28 += v32;
        v27 += v33;
        v34 = (30 * v33 + 59 * v32 + 11 * v31) / 0x64u;
        v122[i] = v34;
        v26 += (unsigned __int16)v34;
      }
      v24 = v91;
      v35 = v28 >> 4;
      BYTE1(v99) = v35;
      v36 = v27 >> 4;
      v37 = v29 >> 4;
      BYTE2(v99) = v36;
      LOBYTE(v99) = v37;
      v38 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v99), 0);
      v13[4] = v38;
      v94 = v26;
      v13[5] = v38;
      v88 = v35;
      v13[6] = v38;
      v13[7] = v38;
      v39 = CmpCell(v13, v13 + 4);
      if ( v39 <= v113 )
      {
        if ( v125 && (unsigned int)CmpCell(v13 + 4, v13 + 8) <= a5 )
          goto LABEL_19;
        if ( (_WORD)v91 )
        {
          do
          {
            if ( (unsigned __int16)v24 >= 0x3FFu )
              v40 = 1023;
            else
              v40 = v24;
            LOWORD(v24) = v24 - v40;
            numberOfSkipCodes = ++v23;
            *v14 = v40 | 0x8400;
            v22 += 2;
            ++v14;
          }
          while ( (_WORD)v24 );
          v98 = v23;
          v91 = v24;
        }
        v41 = v88;
LABEL_27:
        v42 = (unsigned __int16)((v37 >> 3) | (4 * (v41 & 0xFFF8 | (32 * (v36 & 0xFFF8)) | 0xE000)));
        if ( (v42 & 0xFFFFFC00) == 0x8400 )
        {
          numberOfEvilRed = ++v103;
          LOWORD(v42) = v42 ^ 0x400;
        }
        *v14++ = v42;
        LODWORD(v104) = v104 + 1;
        v22 += 2;
        v121 = v14;
        v100 = v22;
        numberOfSolids = v104;
        goto LABEL_90;
      }
      v43 = v94 >> 4;
      v44 = 0;
      v92 = 0;
      v45 = 0;
      v106 = 0;
      v46 = 0;
      v47 = 0;
      v48 = 0;
      v49 = 0;
      LOWORD(v50) = 0;
      v51 = 0;
      v52 = 0;
      do
      {
        v53 = *((unsigned __int8 *)v13 + 4 * v52 + 2);
        v54 = *((unsigned __int8 *)v13 + 4 * v52 + 1);
        if ( v122[v52] >= (unsigned __int16)v43 )
        {
          v46 += v53;
          LOWORD(v55) = v92;
          ++v45;
          v48 += v54;
          v50 = (unsigned __int16)v50 | (1 << v51);
          v49 += *((unsigned __int8 *)v13 + 4 * v52);
        }
        else
        {
          v106 += v53;
          v47 += v54;
          HIWORD(v55) = HIWORD(v92);
          v44 += v132;
          LOWORD(v55) = *((unsigned __int8 *)v13 + 4 * v52) + (_WORD)v92;
          v92 = v55;
        }
        ++v51;
        ++v52;
      }
      while ( v51 < 0x10 );
      v89 = v47;
      v14 = v121;
      v95 = v49;
      v22 = v100;
      v101 = v48;
      v24 = v91;
      v93 = v46;
      v23 = v98;
      if ( v45 )
      {
        v110[0] = v93 / v45;
        v109[0] = v101 / v45;
        v108[0] = v95 / v45;
      }
      else
      {
        v108[0] = 0;
        v109[0] = 0;
        v110[0] = 0;
      }
      if ( v44 )
      {
        v111[0] = v106 / v44;
        v112[0] = v89 / v44;
        v107[0] = (unsigned __int16)v55 / v44;
      }
      else
      {
        v107[0] = 0;
        v112[0] = 0;
        v111[0] = 0;
      }
      for ( j = 0; j != 16; ++j )
      {
        if ( v122[j] >= (unsigned __int16)v43 )
        {
          v57 = v108[0];
          v58 = v109[0];
          v59 = v110[0];
        }
        else
        {
          v57 = v107[0];
          v58 = v112[0];
          v59 = v111[0];
        }
        *((_BYTE *)v13 + 4 * j + 66) = v59;
        *((_BYTE *)v13 + 4 * j + 65) = v58;
        *((_BYTE *)v13 + 4 * j + 64) = v57;
      }
      v60 = CmpCell(v13, v13 + 4);
      if ( v60 <= v113 )
      {
        if ( v125 && (unsigned int)CmpCell(v13 + 4, v13 + 8) <= a5 )
        {
LABEL_19:
          numberOfExtraSkips = ++v97;
LABEL_52:
          LOWORD(v24) = v24 + 1;
          ++v102;
          v91 = v24;
          numberOfSkips = v102;
          goto LABEL_90;
        }
        if ( (_WORD)v91 )
        {
          do
          {
            if ( (unsigned __int16)v24 >= 0x3FFu )
              v61 = 1023;
            else
              v61 = v24;
            LOWORD(v24) = v24 - v61;
            numberOfSkipCodes = ++v23;
            *v14 = v61 | 0x8400;
            v22 += 2;
            ++v14;
          }
          while ( (_WORD)v24 );
          v98 = v23;
          v91 = v24;
        }
        if ( (_WORD)v50 )
        {
          if ( (_WORD)v50 != 0xFFFF )
          {
            if ( (v50 & 0x8000u) == 0 )
            {
              v65 = (v108[0] >> 3) | (4 * (v109[0] & 0xFFF8 | (32 * (v110[0] & 0xFFF8))));
              *v14 = v50;
              v63 = v107[0];
              v14[1] = v65;
              v64 = v112[0] | (32 * (v111[0] & 0xFFF8));
            }
            else
            {
              v62 = (v107[0] >> 3) | (4 * (v112[0] & 0xFFF8 | (32 * (v111[0] & 0xFFF8))));
              *v14 = ~(_WORD)v50;
              v63 = v108[0];
              v14[1] = v62;
              v64 = v109[0] | (32 * (v110[0] & 0xFFF8));
            }
            v22 += 6;
            v100 = v22;
            v14[2] = (v63 >> 3) | (4 * (v64 & 0xFFF8));
            v14 += 3;
            v121 = v14;
            numberOfBlocks = ++HIDWORD(v104);
            goto LABEL_90;
          }
          v36 = v110[0];
          v41 = v109[0];
          v37 = v108[0];
        }
        else
        {
          v36 = v111[0];
          v41 = v112[0];
          v37 = v107[0];
        }
        goto LABEL_27;
      }
      if ( (_WORD)v91 )
      {
        do
        {
          if ( (unsigned __int16)v24 >= 0x3FFu )
            v66 = 1023;
          else
            v66 = v24;
          LOWORD(v24) = v24 - v66;
          numberOfSkipCodes = ++v23;
          *v14 = v66 | 0x8400;
          v22 += 2;
          ++v14;
        }
        while ( (_WORD)v24 );
        v13 = (_OWORD *)v131;
        v98 = v23;
        v91 = v24;
      }
      LOWORD(v67) = 0;
      ++v105;
      v68 = 0;
      numberOfEdges = v105;
      v69 = 0;
      v136 = 0;
      v135 = 0;
      v137 = 0;
      v120[0] = (v122[5] + v122[4] + v122[1] + (unsigned int)v122[0]) >> 2;
      v140 = 0;
      v138 = 0;
      v141 = 0;
      v120[1] = (v122[7] + v122[6] + v122[3] + (unsigned int)v122[2]) >> 2;
      v139 = 0;
      v134 = 0;
      v120[2] = (v122[13] + v122[12] + v122[9] + (unsigned int)v122[8]) >> 2;
      v120[3] = (v122[15] + v122[14] + v122[11] + (unsigned int)v122[10]) >> 2;
      do
      {
        v70 = *((unsigned __int8 *)v13 + 4 * v69 + 2);
        v71 = *((unsigned __int8 *)meanIndex + v69);
        v72 = *((unsigned __int8 *)v13 + 4 * v69 + 1);
        v73 = *((unsigned __int8 *)v13 + 4 * v69);
        if ( v122[v69] >= v120[v71] )
        {
          ++*((_WORD *)&v135 + v71);
          *((_WORD *)&v140 + v71) += v70;
          *((_WORD *)&v141 + v71) += v72;
          v67 = (unsigned __int16)v67 | (1 << v68);
          *((_WORD *)&v134 + v71) += v73;
        }
        else
        {
          ++*((_WORD *)&v136 + v71);
          *((_WORD *)&v137 + v71) += v70;
          *((_WORD *)&v138 + v71) += v72;
          *((_WORD *)&v139 + v71) += v73;
        }
        ++v68;
        ++v69;
      }
      while ( v68 < 0x10 );
      v96 = v67;
      v74 = ~(_WORD)v67;
      v75 = 0;
      if ( (v67 & 0x8000u) == 0 )
        v74 = v67;
      v22 += 2;
      *v14++ = v74;
      do
      {
        v76 = v75;
        v77 = *(unsigned __int16 *)((char *)&v135 + v76 * 2);
        if ( (_WORD)v77 )
        {
          v71 = *((unsigned __int16 *)&v135 + v75);
          v78 = *((unsigned __int16 *)&v140 + v75) / v77;
          v79 = *((unsigned __int16 *)&v141 + v75) / v77;
          v90 = v79;
          v80 = *((unsigned __int16 *)&v134 + v75) / v77;
        }
        else
        {
          if ( v76 >= 4 )
            goto LABEL_103;
          LOWORD(v79) = 0;
          v90 = 0;
          LOWORD(v78) = 0;
          LOWORD(v80) = 0;
        }
        v69 = 0;
        v108[v76] = v80;
        v110[v75] = v78;
        v109[v75] = v79;
        v81 = *((unsigned __int16 *)&v136 + v75);
        if ( (_WORD)v81 )
        {
          v82 = *((unsigned __int16 *)&v137 + v75) / v81;
          v71 = *((unsigned __int16 *)&v138 + v75) / v81;
          v114 = *((unsigned __int16 *)&v139 + v75) / v81;
        }
        else
        {
          if ( v76 >= 4 )
LABEL_103:
            _report_rangecheckfailure(v71, v69);
          v71 = 0;
          LOWORD(v114) = 0;
          LOWORD(v82) = 0;
        }
        v107[v76] = v114;
        v111[v75] = v82;
        v112[v75] = v71;
        v83 = (v107[v76] >> 3) | (4 * (v71 & 0xFFF8 | (32 * (v82 & 0xFFF8))));
        v84 = 4 * (v90 & 0xFFF8 | (32 * (v78 & 0xFFF8)));
        if ( v96 >= 0 )
        {
          v69 = v83;
          LOWORD(v71) = v84 | (v108[v76] >> 3) | (v75 != 0 ? 0 : 0x8000);
        }
        else
        {
          v69 = (unsigned __int16)v108[v76];
          LOWORD(v69) = v84 | ((unsigned __int16)v69 >> 3);
          LOWORD(v71) = v83 | (v75 == 0 ? 0x8000 : 0);
        }
        v13 = (_OWORD *)v131;
        v22 += 4;
        *v14 = v71;
        v14[1] = v69;
        ++v75;
        v14 += 2;
        v100 = v22;
        v121 = v14;
      }
      while ( v75 < 4 );
LABEL_90:
      v11 = v125;
      v85 = v115 + 1 < v116;
      v16 = v128;
      ++v115;
      v25 = Cell;
    }
    while ( v85 );
    v10 = v117;
    v18 = v127;
    v12 = v126;
LABEL_92:
    v12 += 4 * v123;
    v126 = v12;
    if ( v18 )
    {
      v18 += 4 * v119;
      v127 = v18;
    }
    ++v10;
    v20 = v124;
    v117 = v10;
    if ( v10 < v124 )
    {
      v21 = v118;
      v16 = v128;
      continue;
    }
    break;
  }
  if ( (_WORD)v24 )
  {
    do
    {
      v87 = 1023;
      if ( (unsigned __int16)v24 < 0x3FFu )
        v87 = v24;
      LOWORD(v24) = v24 - v87;
      ++v23;
      v22 += 2;
      *v14++ = v87 | 0x8400;
    }
    while ( (_WORD)v24 );
    numberOfSkipCodes = v23;
  }
LABEL_102:
  *v14 = 0;
  return (unsigned int)(v22 + 2);
}

```

## disassembly

```asm
0x180001dd8  mov     [rsp-8+arg_18], rbx
0x180001ddd  push    rbp
0x180001dde  push    rsi
0x180001ddf  push    rdi
0x180001de0  push    r12
0x180001de2  push    r13
0x180001de4  push    r14
0x180001de6  push    r15
0x180001de8  lea     rbp, [rsp-80h]
0x180001ded  sub     rsp, 180h
0x180001df4  mov     rax, cs:__security_cookie
0x180001dfb  xor     rax, rsp
0x180001dfe  mov     [rbp+0B0h+var_38], rax
0x180001e02  mov     rax, [rbp+0B0h+arg_38]
0x180001e09  xor     ebx, ebx
0x180001e0b  mov     r12, [rbp+0B0h+arg_28]
0x180001e12  mov     r11, rdx
0x180001e15  mov     r15, [rbp+0B0h+arg_48]
0x180001e1c  mov     rdi, r8
0x180001e1f  mov     [rbp+0B0h+var_A8], rcx
0x180001e23  mov     [rbp+0B0h+var_A0], rax
0x180001e27  mov     eax, [rcx+4]
0x180001e2a  mov     [rbp+0B0h+var_118], r9d
0x180001e2e  mov     r9, rcx
0x180001e31  movzx   ecx, word ptr [rcx+0Eh]
0x180001e35  imul    ecx, eax
0x180001e38  mov     [rbp+0B0h+var_B8], rdx
0x180001e3c  mov     edx, 1FFFFFFCh
0x180001e41  mov     [rbp+0B0h+var_F0], r8
0x180001e45  mov     r8, [rbp+0B0h+arg_30]
0x180001e4c  mov     [rbp+0B0h+var_C0], r12
0x180001e50  add     ecx, 1Fh
0x180001e53  mov     [rbp+0B0h+var_B0], r8
0x180001e57  shr     ecx, 3
0x180001e5a  and     ecx, edx
0x180001e5c  mov     [rbp+0B0h+var_90], r15
0x180001e60  mov     [rbp+0B0h+var_100], ebx
0x180001e63  mov     [rsp+1B0h+var_170], ebx
0x180001e67  mov     [rbp+0B0h+var_C8], ecx
0x180001e6a  test    r12, r12
0x180001e6d  jz      short loc_180001E86
0x180001e6f  movzx   ecx, word ptr [r12+0Eh]
0x180001e75  imul    ecx, [r12+4]
0x180001e7b  add     ecx, 1Fh
0x180001e7e  shr     ecx, 3
0x180001e81  and     ecx, edx
0x180001e83  mov     [rbp+0B0h+var_100], ecx
0x180001e86  cdq
0x180001e87  and     edx, 3
0x180001e8a  lea     ecx, [rdx+rax]
0x180001e8d  mov     eax, [r9+8]
0x180001e91  cdq
0x180001e92  sar     ecx, 2
0x180001e95  and     edx, 3
0x180001e98  mov     [rbp+0B0h+var_10C], ecx
0x180001e9b  lea     r10d, [rdx+rax]
0x180001e9f  mov     eax, 1
0x180001ea4  sar     r10d, 2
0x180001ea8  mov     [rbp+0B0h+var_C4], r10d
0x180001eac  mov     [rbp+0B0h+var_88], rax
0x180001eb0  cmp     ecx, 64h ; 'd'
0x180001eb3  jnb     short loc_180001EBA
0x180001eb5  lea     ecx, [rax+3]
0x180001eb8  jmp     short loc_180001EC6
0x180001eba  cmp     ecx, 0C8h
0x180001ec0  sbb     ecx, ecx
0x180001ec2  neg     ecx
0x180001ec4  add     ecx, eax
0x180001ec6  xor     edx, edx
0x180001ec8  mov     [rbp+0B0h+var_104], ecx
0x180001ecb  mov     [rsp+1B0h+var_16C], ebx
0x180001ecf  mov     r14d, ebx
0x180001ed2  mov     [rsp+1B0h+var_174], ebx
0x180001ed6  mov     r13d, ebx
0x180001ed9  mov     cs:numberOfSkipCodes, ebx
0x180001edf  mov     esi, ebx
0x180001ee1  mov     [rsp+1B0h+var_164], ebx
0x180001ee5  mov     cs:numberOfSkips, ebx
0x180001eeb  mov     [rsp+1B0h+var_178], ebx
0x180001eef  mov     cs:numberOfExtraSkips, ebx
0x180001ef5  mov     [rsp+1B0h+var_154], ebx
0x180001ef9  mov     cs:numberOfEdges, ebx
0x180001eff  mov     dword ptr [rsp+1B0h+var_15C+4], ebx
0x180001f03  mov     cs:numberOfBlocks, ebx
0x180001f09  mov     dword ptr [rsp+1B0h+var_15C], ebx
0x180001f0d  mov     cs:numberOfSolids, ebx
0x180001f13  mov     cs:numberOfSolid2, ebx
0x180001f19  mov     [rsp+1B0h+var_160], ebx
0x180001f1d  mov     cs:numberOfEvilRed, ebx
0x180001f23  mov     [rsp+1B0h+var_18C], ebx
0x180001f27  mov     [rbp+0B0h+var_108], ebx
0x180001f2a  test    r10d, r10d
0x180001f2d  jz      loc_1800028E5
0x180001f33  cmp     [rbp+0B0h+var_A0], rdx
0x180001f37  jz      loc_180001FCD
0x180001f3d  xor     edx, edx
0x180001f3f  mov     eax, ebx
0x180001f41  div     ecx
0x180001f43  test    edx, edx
0x180001f45  jnz     loc_180001FCB
0x180001f4b  mov     rcx, [rbp+0B0h+arg_40]
0x180001f52  xor     edx, edx
0x180001f54  imul    eax, ebx, 64h ; 'd'
0x180001f57  div     r10d
0x180001f5a  mov     edx, 1
0x180001f5f  mov     r8d, eax
0x180001f62  mov     rax, [rbp+0B0h+var_A0]
0x180001f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f6b  xor     edx, edx
0x180001f6d  test    eax, eax
0x180001f6f  jnz     loc_1800028AD
0x180001f75  mov     eax, cs:numberOfSkips
0x180001f7b  mov     ecx, cs:numberOfEdges
0x180001f81  mov     r13d, cs:numberOfSkipCodes
0x180001f88  mov     r9, [rbp+0B0h+var_A8]
0x180001f8c  mov     r8, [rbp+0B0h+var_B0]
0x180001f90  mov     r11, [rbp+0B0h+var_B8]
0x180001f94  mov     [rsp+1B0h+var_164], eax
0x180001f98  mov     eax, cs:numberOfExtraSkips
0x180001f9e  mov     [rsp+1B0h+var_178], eax
0x180001fa2  mov     eax, cs:numberOfBlocks
0x180001fa8  mov     dword ptr [rsp+1B0h+var_15C+4], eax
0x180001fac  mov     eax, cs:numberOfSolids
0x180001fb2  mov     [rsp+1B0h+var_154], ecx
0x180001fb6  mov     ecx, cs:numberOfEvilRed
0x180001fbc  mov     dword ptr [rsp+1B0h+var_15C], eax
0x180001fc0  mov     [rsp+1B0h+var_174], r13d
0x180001fc5  mov     [rsp+1B0h+var_160], ecx
0x180001fc9  jmp     short loc_180001FCD
0x180001fcb  xor     edx, edx
0x180001fcd  mov     rax, r11
0x180001fd0  mov     [rbp+0B0h+var_98], r8
0x180001fd4  mov     [rbp+0B0h+var_110], edx
0x180001fd7  cmp     [rbp+0B0h+var_10C], edx
0x180001fda  jbe     loc_18000286D
0x180001fe0  mov     r8, r15
0x180001fe3  mov     rdx, rax
0x180001fe6  mov     rcx, r9
0x180001fe9  call    GetCell
0x180001fee  mov     [rbp+0B0h+var_80], rax
0x180001ff2  xor     eax, eax
0x180001ff4  test    r12, r12
0x180001ff7  jz      short loc_18000202C
0x180001ff9  mov     rdx, [rbp+0B0h+var_98]
0x180001ffd  lea     rbx, [r15+80h]
0x180002004  mov     r8, rbx
0x180002007  mov     rcx, r12
0x18000200a  call    GetCell
0x18000200f  mov     rdx, rbx
0x180002012  mov     [rbp+0B0h+var_98], rax
0x180002016  mov     rcx, r15
0x180002019  call    CmpCell
0x18000201e  cmp     eax, [rbp+0B0h+arg_20]
0x180002024  jbe     loc_1800023B9
0x18000202a  xor     eax, eax
0x18000202c  mov     r11d, eax
0x18000202f  mov     ebx, eax
0x180002031  mov     r9d, eax
0x180002034  mov     r12d, eax
0x180002037  mov     r10, rax
0x18000203a  movzx   eax, byte ptr [r15+r10*4]
0x18000203f  movzx   ecx, byte ptr [r15+r10*4+1]
0x180002045  add     r12w, ax
0x180002049  movzx   r8d, byte ptr [r15+r10*4+2]
0x18000204f  add     r9w, cx
0x180002053  imul    edx, eax, 0Bh
0x180002056  add     bx, r8w
0x18000205a  imul    eax, ecx, 3Bh ; ';'
0x18000205d  add     edx, eax
0x18000205f  imul    eax, r8d, 1Eh
0x180002063  add     edx, eax
0x180002065  mov     eax, 51EB851Fh
0x18000206a  mul     edx
0x18000206c  shr     edx, 5
0x18000206f  movzx   eax, dx
0x180002072  mov     [rbp+r10*2+0B0h+var_E8], ax
0x180002078  add     r11d, eax
0x18000207b  inc     r10
0x18000207e  cmp     r10, 10h
0x180002082  jnz     short loc_18000203A
0x180002084  mov     esi, [rsp+1B0h+var_18C]
0x180002088  lea     rdx, [r15+40h]
0x18000208c  shr     r9w, 4
0x180002091  mov     rcx, r15
0x180002094  mov     byte ptr [rsp+1B0h+var_170+1], r9b
0x180002099  shr     bx, 4
0x18000209d  shr     r12w, 4
0x1800020a2  mov     byte ptr [rsp+1B0h+var_170+2], bl
0x1800020a6  mov     byte ptr [rsp+1B0h+var_170], r12b
0x1800020ab  movd    xmm0, [rsp+1B0h+var_170]
0x1800020b1  pshufd  xmm0, xmm0, 0
0x1800020b6  movups  xmmword ptr [r15+40h], xmm0
0x1800020bb  mov     [rsp+1B0h+var_180], r11d
0x1800020c0  movups  xmmword ptr [r15+50h], xmm0
0x1800020c5  mov     [rsp+1B0h+var_190], r9d
0x1800020ca  movups  xmmword ptr [r15+60h], xmm0
0x1800020cf  movups  xmmword ptr [r15+70h], xmm0
0x1800020d4  call    CmpCell
0x1800020d9  cmp     eax, [rbp+0B0h+var_118]
0x1800020dc  ja      loc_1800021E0
0x1800020e2  xor     ecx, ecx
0x1800020e4  cmp     [rbp+0B0h+var_C0], rcx
0x1800020e8  jz      short loc_18000211E
0x1800020ea  lea     rdx, [r15+80h]
0x1800020f1  lea     rcx, [r15+40h]
0x1800020f5  call    CmpCell
0x1800020fa  cmp     eax, [rbp+0B0h+arg_20]
0x180002100  ja      short loc_18000211E
0x180002102  mov     eax, [rsp+1B0h+var_178]
0x180002106  mov     r10d, 1
0x18000210c  add     eax, r10d
0x18000210f  mov     [rsp+1B0h+var_178], eax
0x180002113  mov     cs:numberOfExtraSkips, eax
0x180002119  jmp     loc_1800023BF
0x18000211e  mov     r10d, 1
0x180002124  test    si, si
0x180002127  jz      short loc_180002164
0x180002129  mov     edx, 3FFh
0x18000212e  cmp     si, dx
0x180002131  jnb     short loc_180002138
0x180002133  movzx   eax, si
0x180002136  jmp     short loc_18000213A
0x180002138  mov     eax, edx
0x18000213a  sub     si, ax
0x18000213d  add     r13d, r10d
0x180002140  or      ax, 8400h
0x180002144  mov     cs:numberOfSkipCodes, r13d
0x18000214b  mov     [rdi], ax
0x18000214e  add     r14d, 2
0x180002152  add     rdi, 2
0x180002156  test    si, si
0x180002159  jnz     short loc_18000212E
0x18000215b  mov     [rsp+1B0h+var_174], r13d
0x180002160  mov     [rsp+1B0h+var_18C], esi
0x180002164  mov     eax, [rsp+1B0h+var_190]
0x180002168  mov     ecx, 0FFF8h
0x18000216d  shr     r12w, 3
0x180002172  and     bx, cx
0x180002175  shl     bx, 5
0x180002179  or      bx, ax
0x18000217c  and     bx, cx
0x18000217f  or      bx, 0E000h
0x180002184  shl     bx, 2
0x180002188  or      bx, r12w
0x18000218c  movzx   ecx, bx
0x18000218f  mov     eax, ecx
0x180002191  and     eax, 0FFFFFC00h
0x180002196  cmp     eax, 8400h
0x18000219b  jnz     short loc_1800021B6
0x18000219d  mov     eax, [rsp+1B0h+var_160]
0x1800021a1  add     eax, r10d
0x1800021a4  mov     [rsp+1B0h+var_160], eax
0x1800021a8  mov     cs:numberOfEvilRed, eax
0x1800021ae  mov     eax, 400h
0x1800021b3  xor     cx, ax
0x1800021b6  mov     ebx, dword ptr [rsp+1B0h+var_15C]
0x1800021ba  add     ebx, r10d
0x1800021bd  mov     [rdi], cx
0x1800021c0  add     rdi, 2
0x1800021c4  mov     dword ptr [rsp+1B0h+var_15C], ebx
0x1800021c8  add     r14d, 2
0x1800021cc  mov     [rbp+0B0h+var_F0], rdi
0x1800021d0  mov     [rsp+1B0h+var_16C], r14d
0x1800021d5  mov     cs:numberOfSolids, ebx
0x1800021db  jmp     loc_180002840
0x1800021e0  mov     r8d, [rsp+1B0h+var_180]
0x1800021e5  shr     r8d, 4
0x1800021e9  xor     eax, eax
0x1800021eb  mov     [rsp+1B0h+var_188], eax
0x1800021ef  mov     r10d, eax
0x1800021f2  mov     [rsp+1B0h+var_188], eax
0x1800021f6  mov     r9d, eax
0x1800021f9  mov     dword ptr [rsp+1B0h+var_150], eax
0x1800021fd  mov     r13d, eax
0x180002200  mov     edi, eax
0x180002202  mov     [rsp+1B0h+var_190], eax
0x180002206  mov     esi, eax
0x180002208  mov     [rsp+1B0h+var_168], eax
0x18000220c  mov     r14d, eax
0x18000220f  mov     [rsp+1B0h+var_180], eax
0x180002213  mov     r12d, eax
0x180002216  mov     edx, eax
0x180002218  mov     ecx, eax
0x18000221a  movzx   r11d, byte ptr [r15+rcx*4+2]
0x180002220  movzx   ebx, byte ptr [r15+rcx*4+1]
0x180002226  movzx   eax, byte ptr [r15+rcx*4]
0x18000222b  cmp     [rbp+rcx*2+0B0h+var_E8], r8w
0x180002231  jnb     short loc_180002251
0x180002233  add     [rsp+1B0h+var_150], r11w
0x180002239  add     di, bx
0x18000223c  mov     r11d, [rsp+1B0h+var_188]
0x180002241  add     r10w, word ptr [rbp+0B0h+var_88]
0x180002246  add     r11w, ax
0x18000224a  mov     [rsp+1B0h+var_188], r11d
0x18000224f  jmp     short loc_180002272
0x180002251  movzx   eax, byte ptr [r15+rcx*4]
0x180002256  add     r13w, r11w
0x18000225a  mov     r11d, [rsp+1B0h+var_188]
0x18000225f  inc     r9w
0x180002263  movzx   r12d, r12w
  ... truncated ...
```
