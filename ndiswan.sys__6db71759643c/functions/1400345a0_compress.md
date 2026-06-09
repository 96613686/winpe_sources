# compress

- ea: `0x1400345a0`
- end: `0x140035235`
- name: `compress`
- size: `3221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140032340`

## callees

- `0x140016700`
- `0x1400345a0`

## pseudocode

```c
char __fastcall compress(unsigned __int8 *a1, _BYTE *a2, unsigned int *a3, unsigned int *a4)
{
  __int16 *v6; // r10
  __int64 v7; // rsi
  int v8; // r12d
  unsigned int v9; // eax
  unsigned int v10; // ecx
  _BYTE *v11; // r14
  int v12; // r8d
  _BYTE *v13; // r11
  unsigned __int8 *v14; // rdx
  int v15; // ebp
  _BYTE *v16; // r9
  int v17; // edi
  __int64 v18; // rdi
  _BYTE *v19; // rbp
  __int64 v20; // r12
  _BYTE *v21; // r8
  __int64 v22; // r13
  _BYTE *v23; // r9
  int v24; // r10d
  __int64 v25; // rsi
  int v26; // edx
  int v27; // r11d
  _BYTE *v28; // rdx
  unsigned __int64 v29; // rcx
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // ebp
  unsigned __int8 *v34; // rcx
  unsigned int v35; // r11d
  int v36; // ecx
  __int16 v37; // dx
  char result; // al
  int v39; // edx
  int v40; // edx
  __int16 v41; // dx
  unsigned int v42; // eax
  _BYTE *v43; // rdx
  int i; // esi
  char v45; // cl
  unsigned int v46; // edx
  int v47; // ecx
  _BYTE *v48; // r10
  int v49; // ebp
  char v50; // ah
  int v51; // eax
  unsigned int v52; // ebp
  char v53; // cl
  int v54; // r8d
  int v55; // eax
  int v56; // ebp
  int v57; // eax
  _BYTE *v58; // r8
  int v59; // ecx
  int v60; // edx
  int v61; // ecx
  int v62; // edx
  int v63; // edx
  int v64; // edi
  int v65; // edx
  int v66; // ebp
  char v67; // cl
  int v68; // ebp
  __int16 v69; // bp
  _BYTE *v70; // r10
  int v71; // r11d
  int v72; // ebp
  char v73; // ah
  int v74; // r11d
  int v75; // ebp
  int v76; // edx
  int v77; // edx
  int v78; // r11d
  int v79; // ebp
  char v80; // ah
  int v81; // r11d
  _BYTE *v82; // r8
  _BYTE *v83; // r10
  __int16 v84; // bp
  int v85; // edx
  __int16 v86; // bp
  int v87; // ebp
  int v88; // edx
  int v89; // edi
  int v90; // edx
  int v91; // r11d
  int v92; // ebp
  int v93; // eax
  _BYTE *v94; // r11
  int v95; // edx
  int v96; // ebp
  int v97; // ebp
  int v98; // r10d
  char v99; // ah
  int v100; // edx
  int v101; // r10d
  _BYTE *v102; // r11
  __int16 v103; // bp
  int v104; // ebp
  _BYTE *v105; // r11
  int v106; // ebp
  int v107; // edx
  char v108; // ah
  int v109; // edx
  int v110; // edi
  int v111; // edx
  int v112; // r11d
  int v113; // ebp
  int v114; // eax
  int v115; // edx
  int v116; // r10d
  int v117; // edx
  char v118; // cl
  int v119; // edx
  __int16 v120; // dx
  int v121; // [rsp+20h] [rbp-78h]
  int v122; // [rsp+24h] [rbp-74h]
  int v123; // [rsp+28h] [rbp-70h]
  _BYTE *v124; // [rsp+30h] [rbp-68h]
  unsigned __int64 v125; // [rsp+38h] [rbp-60h]
  char v126; // [rsp+A0h] [rbp+8h]
  int v127; // [rsp+A8h] [rbp+10h]
  int v129; // [rsp+B8h] [rbp+20h]

  v127 = (int)a2;
  v6 = (__int16 *)a3;
  v7 = *a3;
  v8 = (int)a2;
  v9 = *a4;
  v123 = v7;
  v10 = *a4 + v7;
  if ( v10 >= *a4 && v10 < 0x1FFE && v9 )
  {
    v126 = 32;
  }
  else
  {
    *a4 = 0;
    v9 = 0;
    v126 = 96;
  }
  v11 = a4 + 2054;
  v12 = a4[5] & 0x800;
  v122 = v12;
  if ( v12 )
    v11 = a1;
  v13 = a2;
  v124 = a2;
  v14 = &a1[v7 - 1];
  v15 = 0;
  v16 = &v11[v9];
  v129 = 0;
  v17 = 16;
  v125 = (unsigned __int64)v14;
  v121 = 16;
  if ( a1 < v14 - 2 )
  {
    while ( 1 )
    {
      v18 = *a1++;
      v19 = v16;
      if ( !v12 )
        *v16 = v18;
      v20 = a1[1];
      v21 = v16 + 1;
      v22 = *a1;
      v23 = v16 + 1;
      v24 = *((unsigned __int16 *)a4 + 8);
      v25 = (__int64)a4
          + 2 * (((unsigned int)(lookup_array1[v18] + lookup_array2[v22] + lookup_array3[v20]) >> 12) & 0xFFF);
      v26 = *(unsigned __int16 *)(v25 + 24);
      if ( (unsigned __int16)v26 < (unsigned __int16)v24 )
        v27 = 0;
      else
        v27 = v26 - v24;
      v28 = &v11[v27];
      if ( v28 != v19 )
        *(_WORD *)(v25 + 24) = v24 + (_WORD)v23 - (_WORD)v11;
      v29 = *((_QWORD *)a4 + 1);
      if ( v29 < (unsigned __int64)v21 )
      {
        *((_QWORD *)a4 + 1) = v21;
        v29 = (unsigned __int64)(v19 + 1);
      }
      if ( v28 == v11
        || v28 == v19
        || v28 == v21
        || (unsigned __int64)(v28 + 1) > v29
        || *(v28 - 1) != (_BYTE)v18
        || *v28 != (_BYTE)v22
        || v28[1] != (_BYTE)v20 )
      {
        v13 = v124;
        v16 = v19 + 1;
        v30 = v18;
        if ( (v18 & 0x80u) != 0LL )
        {
          v39 = v18 + 128;
          if ( v121 <= 9 )
          {
            v41 = v129 | v39;
            v17 = 16;
            *v124 = HIBYTE(v41);
            v13 = v124 + 1;
            v15 = 0;
            v124[1] = v41;
          }
          else
          {
            v17 = v121 - 1;
            v40 = v129 | (v39 << (v121 - 9));
            *v124 = BYTE1(v40);
            v15 = v40 << 8;
          }
          v121 = v17;
          ++v13;
          goto LABEL_19;
        }
        v17 = v121;
        v31 = v129 | (v30 << (v121 - 8));
        v15 = v31;
        goto LABEL_17;
      }
      v42 = ((_WORD)v23 - (_WORD)v11 - (_WORD)v27) & 0x1FFF;
      if ( v122 )
      {
        v16 = v23 + 2;
      }
      else
      {
        *v21 = v22;
        v16 = v19 + 3;
        v19[2] = v20;
      }
      a1 += 2;
      v43 = v28 + 2;
      for ( i = 3; (unsigned __int64)a1 < v125; ++v16 )
      {
        if ( (unsigned __int64)v43 > *((_QWORD *)a4 + 1) )
          break;
        v45 = *a1;
        if ( *v43 != *a1 )
          break;
        ++v43;
        ++a1;
        if ( !v122 )
          *v16 = v45;
        ++i;
      }
      v17 = v121;
      if ( v42 >= 0x140 )
      {
        v52 = v42 - 320;
        v53 = v121 - 8;
        *v124 = (unsigned __int16)(v129 | ((int)(v42 - 320 + 49152) >> 8 << (v121 - 8))) >> 8;
        v48 = v124 + 1;
        v54 = (v129 | ((int)(v42 - 320 + 49152) >> 8 << (v121 - 8))) << 8;
LABEL_66:
        v49 = v54 | (v52 << v53);
        v50 = BYTE1(v49);
        goto LABEL_59;
      }
      if ( v42 < 0x40 )
      {
        v46 = v42 + 960;
        if ( v121 <= 10 )
        {
          v48 = v124;
          v17 = v121 - 2;
          v121 = v17;
          v54 = v129 | (v46 >> 8 << v17);
          if ( v17 >= 9 )
          {
LABEL_74:
            v53 = v17 - 8;
            v52 = (unsigned __int8)v46;
            goto LABEL_66;
          }
LABEL_73:
          v17 += 8;
          *v48++ = BYTE1(v54);
          v54 <<= 8;
          v121 = v17;
          goto LABEL_74;
        }
        v47 = v121 - 10;
      }
      else
      {
        v46 = v42 + 3520;
        if ( v121 <= 12 )
        {
          v48 = v124;
          v17 = v121 - 4;
          v121 = v17;
          v54 = v129 | (v46 >> 8 << v17);
          if ( v17 >= 9 )
            goto LABEL_74;
          goto LABEL_73;
        }
        v47 = v121 - 12;
      }
      v48 = v124;
      v17 = v47 + 8;
      v49 = v129 | (v46 << v47);
      v121 = v47 + 8;
      v50 = (unsigned __int16)(v129 | ((_WORD)v46 << v47)) >> 8;
LABEL_59:
      v15 = v49 << 8;
      v129 = v15;
      *v48 = v50;
      if ( i == 16 )
      {
        v51 = 224;
LABEL_61:
        v13 = v48 + 2;
        v15 |= v51 << (v17 - 8);
        v48[1] = BYTE1(v15);
        goto LABEL_18;
      }
      switch ( i )
      {
        case 3:
          if ( v17 < 10 )
          {
            v13 = v48 + 2;
            v17 = 16;
            v48[1] = BYTE1(v15);
            v121 = 16;
            goto LABEL_18;
          }
          --v17;
          v13 = v48 + 1;
          v121 = v17;
          goto LABEL_20;
        case 4:
          v17 -= 4;
          v13 = v48 + 1;
          v121 = v17;
          v124 = v48 + 1;
          v55 = v15 | (8 << v17);
          v15 = v55;
          if ( v17 < 9 )
            goto LABEL_80;
          goto LABEL_88;
        case 5:
          v57 = 9;
          goto LABEL_85;
        case 6:
          v57 = 10;
          goto LABEL_85;
        case 7:
          v57 = 11;
LABEL_85:
          v17 -= 4;
          goto LABEL_87;
        case 8:
          v17 -= 6;
          v57 = 48;
          goto LABEL_87;
        case 9:
          v17 -= 6;
          v57 = 49;
          goto LABEL_87;
        case 10:
          v17 -= 6;
          v57 = 50;
          goto LABEL_87;
        case 11:
          v17 -= 6;
          v57 = 51;
          goto LABEL_87;
        case 12:
          v17 -= 6;
          v57 = 52;
          goto LABEL_87;
        case 13:
          v17 -= 6;
          v57 = 53;
          goto LABEL_87;
        case 14:
          v17 -= 6;
          v57 = 54;
          goto LABEL_87;
        case 15:
          v17 -= 6;
          v57 = 55;
LABEL_87:
          v121 = v17;
          v13 = v48 + 1;
          v55 = v15 | (v57 << v17);
          v124 = v48 + 1;
          v15 = v55;
          if ( v17 >= 9 )
            goto LABEL_88;
LABEL_80:
          *v13 = BYTE1(v55);
          v17 += 8;
          v13 = v48 + 2;
          goto LABEL_82;
        case 17:
          v51 = 225;
          goto LABEL_61;
        case 18:
          v51 = 226;
          goto LABEL_61;
        case 19:
          v51 = 227;
          goto LABEL_61;
        case 20:
          v51 = 228;
          goto LABEL_61;
        case 21:
          v51 = 229;
          goto LABEL_61;
        case 22:
          v51 = 230;
          goto LABEL_61;
        case 23:
          v51 = 231;
          goto LABEL_61;
        case 24:
          v51 = 232;
          goto LABEL_61;
        case 25:
          v51 = 233;
          goto LABEL_61;
        case 26:
          v51 = 234;
          goto LABEL_61;
        case 27:
          v51 = 235;
          goto LABEL_61;
        case 28:
          v51 = 236;
          goto LABEL_61;
        case 29:
          v51 = 237;
          goto LABEL_61;
        case 30:
          v51 = 238;
          goto LABEL_61;
        case 31:
          v51 = 239;
          goto LABEL_61;
        default:
          v58 = v48 + 1;
          if ( i >= 64 )
          {
            if ( i >= 128 )
            {
              if ( i >= 256 )
              {
                if ( i < 512 )
                {
                  v64 = v17 - 7;
                  v65 = v15 | (127 << v64);
                  if ( v64 < 9 )
                  {
                    v64 += 8;
                    *v58 = BYTE1(v65);
                    v58 = v48 + 2;
                    v65 <<= 8;
                  }
                  v66 = i - 256;
                  if ( v64 <= 9 )
                  {
                    v69 = v65 | v66;
                    v17 = 16;
                    *v58++ = HIBYTE(v69);
                    *v58 = v69;
                    v15 = 0;
                  }
                  else
                  {
                    v67 = v64 - 9;
                    v17 = v64 - 1;
                    v68 = v65 | (v66 << v67);
                    *v58 = BYTE1(v68);
                    v15 = v68 << 8;
                  }
                  v121 = v17;
                  v13 = v58 + 1;
                  goto LABEL_19;
                }
                if ( i < 1024 )
                {
                  v70 = v48 + 2;
                  v71 = v15 | (255 << (v17 - 8));
                  v72 = i - 512;
                  v73 = BYTE1(v71);
                  v74 = v71 << 8;
                  *v58 = v73;
                  if ( v17 <= 10 )
                  {
                    v17 -= 2;
                    v76 = v74 | (v72 >> 8 << v17);
                    v121 = v17;
                    if ( v17 < 9 )
                    {
                      v17 += 8;
                      *v70++ = BYTE1(v76);
                      v76 <<= 8;
                      v121 = v17;
                    }
                    v15 = v76 | ((unsigned __int8)i << (v17 - 8));
                  }
                  else
                  {
                    v75 = v72 << (v17 - 10);
                    v17 = v17 - 10 + 8;
                    v15 = v74 | v75;
                    v121 = v17;
                  }
                  v13 = v70 + 1;
                  *v70 = BYTE1(v15);
                  goto LABEL_18;
                }
                if ( i < 2048 )
                {
                  if ( v17 <= 9 )
                  {
                    v86 = v15 | 0x1FF;
                    v77 = 16;
                    *v58 = HIBYTE(v86);
                    v81 = 0;
                    v48[2] = v86;
                    v82 = v48 + 3;
                    v79 = i - 1024;
                  }
                  else
                  {
                    v77 = v17 - 1;
                    v78 = v15 | (511 << (v17 - 9));
                    v79 = i - 1024;
                    v80 = BYTE1(v78);
                    v81 = v78 << 8;
                    *v58 = v80;
                    v82 = v48 + 2;
                    if ( v17 - 1 <= 11 )
                    {
                      v83 = v48 + 3;
                      v17 = 16;
                      if ( v77 == 11 )
                      {
                        v84 = v81 | v79;
                        *v82 = HIBYTE(v84);
                        *v83 = v84;
                        v15 = 0;
                      }
                      else
                      {
                        v17 = 16 - (11 - v77);
                        v85 = v81 | (v79 >> (11 - v77));
                        *v82 = BYTE1(v85);
                        *v83 = v85;
                        v15 = v79 << v17;
                      }
                      goto LABEL_148;
                    }
                  }
                  v83 = v82;
                  v17 = v77 - 11 + 8;
                  v87 = v81 | (v79 << (v77 - 11));
                  *v82 = BYTE1(v87);
                  v15 = v87 << 8;
LABEL_148:
                  v121 = v17;
                  v13 = v83 + 1;
                  goto LABEL_19;
                }
                if ( i < 4096 )
                {
                  if ( v17 <= 10 )
                  {
                    v89 = v17 - 2;
                    v91 = v15 | (3 << v89);
                    if ( v89 < 9 )
                    {
                      v89 += 8;
                      *v58 = BYTE1(v91);
                      v58 = v48 + 2;
                      v91 <<= 8;
                    }
                    v90 = v91 | (255 << (v89 - 8));
                  }
                  else
                  {
                    v88 = 1023 << (v17 - 10);
                    v89 = v17 - 10 + 8;
                    v90 = v15 | v88;
                  }
                  v92 = i - 2048;
                  v93 = v90 >> 8;
                  v94 = v58 + 1;
                  v95 = v90 << 8;
                  *v58 = v93;
                  if ( v89 <= 12 )
                  {
                    v17 = v89 - 4;
                    v98 = v95 | (v92 >> 8 << v17);
                    v121 = v17;
                    if ( v17 < 9 )
                    {
                      v17 += 8;
                      *v94 = BYTE1(v98);
                      v94 = v58 + 2;
                      v121 = v17;
                      v98 <<= 8;
                    }
                    v97 = v98 | ((unsigned __int8)i << (v17 - 8));
                  }
                  else
                  {
                    v96 = v92 << (v89 - 12);
                    v17 = v89 - 12 + 8;
                    v97 = v95 | v96;
                    v121 = v17;
                  }
                  v99 = BYTE1(v97);
                  v15 = v97 << 8;
                  *v94 = v99;
                  v13 = v94 + 1;
                  goto LABEL_19;
                }
                if ( i < 0x2000 )
                {
                  if ( v17 > 11 )
                  {
                    v100 = v17 - 11 + 8;
                    *v58 = (unsigned __int16)(v15 | (2047 << (v17 - 11))) >> 8;
                    v101 = (v15 | (2047 << (v17 - 11))) << 8;
                    goto LABEL_168;
                  }
                  v102 = v48 + 2;
                  if ( v17 == 11 )
                  {
                    v103 = v15 | 0x7FF;
                    v101 = 0;
                    v100 = 16;
                    *v58 = HIBYTE(v103);
                    *v102 = v103;
                    v104 = i - 4096;
                    v105 = v102 + 1;
                    goto LABEL_166;
                  }
                  *v58 = (unsigned __int16)(v15 | (2047 >> (11 - v17))) >> 8;
                  v58 = v48 + 2;
                  *v102 = v15 | (2047 >> (11 - v17));
                  v100 = 16 - (11 - v17);
                  v101 = 2047 << (16 - (11 - v17));
LABEL_168:
                  v104 = i - 4096;
                  v105 = v58 + 1;
                  if ( v100 > 13 )
                  {
LABEL_166:
                    v17 = v100 - 13 + 8;
                    v106 = v101 | (v104 << (v100 - 13));
                    v121 = v17;
                  }
                  else
                  {
                    v17 = v100 - 5;
                    v107 = v101 | (v104 >> 8 << (v100 - 5));
                    v121 = v17;
                    if ( v17 < 9 )
                    {
                      v17 += 8;
                      *v105 = BYTE1(v107);
                      v105 = v58 + 2;
                      v121 = v17;
                      v107 <<= 8;
                    }
                    v106 = v107 | ((unsigned __int8)i << (v17 - 8));
                  }
                  v108 = BYTE1(v106);
                  v15 = v106 << 8;
                  *v105 = v108;
                  v13 = v105 + 1;
                  goto LABEL_19;
                }
                if ( v17 <= 12 )
                {
                  v110 = v17 - 4;
                  v112 = v15 | (15 << v110);
                  if ( v110 < 9 )
                  {
                    v110 += 8;
                    *v58 = BYTE1(v112);
                    v58 = v48 + 2;
                    v112 <<= 8;
                  }
                  v111 = v112 | (255 << (v110 - 8));
                }
                else
                {
                  v109 = 4095 << (v17 - 12);
                  v110 = v17 - 12 + 8;
                  v111 = v15 | v109;
                }
                v113 = i - 0x2000;
                v114 = v111 >> 8;
                v13 = v58 + 1;
                v115 = v111 << 8;
                *v58 = v114;
                if ( v110 > 14 )
                {
                  v56 = v113 << (v110 - 14);
                  v17 = v110 - 14 + 8;
                  v15 = v115 | v56;
                  *v13 = BYTE1(v15);
                  v13 = v58 + 2;
LABEL_82:
                  v121 = v17;
                  goto LABEL_18;
                }
                v17 = v110 - 6;
                v116 = v115 | (v113 >> 8 << v17);
                v121 = v17;
                if ( v17 < 9 )
                {
                  v17 += 8;
                  *v13 = BYTE1(v116);
                  v13 = v58 + 2;
                  v121 = v17;
                  v116 <<= 8;
                }
                v15 = v116 | ((unsigned __int8)i << (v17 - 8));
                BYTE1(v31) = (unsigned __int16)(v116 | ((unsigned __int8)i << (v17 - 8))) >> 8;
              }
              else
              {
                v17 -= 6;
                v121 = v17;
                v13 = v48 + 1;
                v63 = v15 | (63 << v17);
                if ( v17 < 9 )
                {
                  v13 = v48 + 2;
                  v17 += 8;
                  *v58 = BYTE1(v63);
                  v63 <<= 8;
                  v121 = v17;
                }
                v15 = v63 | ((i - 128) << (v17 - 8));
                BYTE1(v31) = BYTE1(v15);
              }
            }
            else
            {
              v61 = v17 - 5;
              v124 = v48 + 1;
              v13 = v48 + 1;
              v62 = v15 | (31 << (v17 - 5));
              if ( v17 - 5 < 9 )
              {
                v13 = v48 + 2;
                v61 += 8;
                *v58 = BYTE1(v62);
                v62 <<= 8;
                v124 = v48 + 2;
              }
              v17 = v61 - 7;
              v121 = v61 - 7;
              v15 = v62 | ((i - 64) << (v61 - 7));
              if ( v61 - 7 >= 9 )
              {
LABEL_88:
                v129 = v15;
                goto LABEL_21;
              }
              v17 += 8;
              BYTE1(v31) = (unsigned __int16)(v62 | (((_WORD)i - 64) << (v61 - 7))) >> 8;
              v121 = v17;
            }
          }
          else
          {
            v59 = v17 - 4;
            v124 = v48 + 1;
            v13 = v48 + 1;
            v60 = v15 | (15 << (v17 - 4));
            if ( v17 - 4 < 9 )
            {
              v13 = v48 + 2;
              v59 += 8;
              *v58 = BYTE1(v60);
              v60 <<= 8;
              v124 = v48 + 2;
            }
            v17 = v59 - 6;
            v121 = v59 - 6;
            v15 = v60 | ((i - 32) << (v59 - 6));
            if ( v59 - 6 >= 9 )
              goto LABEL_88;
            v17 += 8;
            BYTE1(v31) = (unsigned __int16)(v60 | (((_WORD)i - 32) << (v59 - 6))) >> 8;
            v121 = v17;
          }
          break;
      }
LABEL_17:
      *v13++ = BYTE1(v31);
LABEL_18:
      v15 <<= 8;
LABEL_19:
      v129 = v15;
LABEL_20:
      v124 = v13;
LABEL_21:
      v14 = (unsigned __int8 *)v125;
      v12 = v122;
      if ( (unsigned __int64)a1 >= v125 - 2 )
      {
        v6 = (__int16 *)a3;
        LODWORD(v7) = v123;
        v8 = v127;
        break;
      }
    }
  }
  if ( a1 <= v14 )
  {
    do
    {
      v32 = *a1;
      if ( (v32 & 0x80u) != 0 )
      {
        v117 = v32 + 128;
        if ( v17 <= 9 )
        {
          v120 = v15 | v117;
          v17 = 16;
          *v13++ = HIBYTE(v120);
          v15 = 0;
          *v13 = v120;
        }
        else
        {
          v118 = v17-- - 9;
          v119 = v15 | (v117 << v118);
          *v13 = BYTE1(v119);
          v15 = v119 << 8;
        }
        v14 = (unsigned __int8 *)v125;
      }
      else
      {
        v33 = v15 | (v32 << (v17 - 8));
        *v13 = BYTE1(v33);
        v15 = v33 << 8;
      }
      ++v13;
      v34 = a1 + 1;
      if ( !v12 )
        *v16 = *a1;
      ++v16;
      ++a1;
    }
    while ( v34 <= v14 );
  }
  if ( v17 != 16 )
  {
    *v13 = BYTE1(v15);
    LODWORD(v13) = (_DWORD)v13 + 1;
  }
  v35 = (_DWORD)v13 - v8;
  v36 = a4[5] & 0x800;
  if ( v35 > (unsigned int)v7 )
  {
    *((_WORD *)a4 + 8) = 0;
    if ( !v36 )
      memset(a4 + 2054, 0, 0x2001u);
    memset(a4 + 6, 0, 0x2000u);
    result = 0x80;
    *a4 = 8193;
  }
  else
  {
    v37 = *v6;
    result = v126;
    *(_DWORD *)v6 = v35;
    *a4 = (_DWORD)v16 - (_DWORD)v11;
    if ( v36 )
      *((_WORD *)a4 + 8) += v37;
  }
  return result;
}

```

## disassembly

```asm
0x1400345a0  mov     rax, rsp
0x1400345a3  mov     [rax+18h], r8
0x1400345a7  mov     [rax+10h], rdx
0x1400345ab  push    r14
0x1400345ad  push    r15
0x1400345af  sub     rsp, 88h
0x1400345b6  mov     [rax-18h], rbx
0x1400345ba  mov     r15, r9
0x1400345bd  mov     [rax-20h], rbp
0x1400345c1  mov     rbx, rcx
0x1400345c4  mov     [rax-28h], rsi
0x1400345c8  mov     r10, r8
0x1400345cb  mov     esi, [r8]
0x1400345ce  mov     [rax-30h], rdi
0x1400345d2  mov     [rax-38h], r12
0x1400345d6  mov     r12, rdx
0x1400345d9  mov     eax, [r9]
0x1400345dc  mov     [rsp+98h+var_70], esi
0x1400345e0  lea     ecx, [rax+rsi]
0x1400345e3  cmp     ecx, eax
0x1400345e5  jnb     loc_1400349DA
0x1400345eb  mov     dword ptr [r9], 0
0x1400345f2  xor     eax, eax
0x1400345f4  mov     [rsp+98h+arg_0], 60h ; '`'
0x1400345fc  mov     r8d, [r9+14h]
0x140034600  lea     r14, [r9+2018h]
0x140034607  and     r8d, 800h
0x14003460e  mov     [rsp+98h+var_74], r8d
0x140034613  jz      short loc_140034618
0x140034615  mov     r14, rbx
0x140034618  mov     r11, rdx
0x14003461b  mov     [rsp+98h+var_68], rdx
0x140034620  movsxd  r9, eax
0x140034623  lea     rdx, [rbx-1]
0x140034627  add     rdx, rsi
0x14003462a  xor     ebp, ebp
0x14003462c  add     r9, r14
0x14003462f  mov     [rsp+98h+arg_18], ebp
0x140034636  mov     edi, 10h
0x14003463b  mov     [rsp+98h+var_60], rdx
0x140034640  mov     [rsp+98h+var_78], edi
0x140034644  lea     rax, [rdx-2]
0x140034648  cmp     rbx, rax
0x14003464b  jnb     loc_14003476A
0x140034651  mov     [rsp+98h+var_40], r13
0x140034656  nop     word ptr [rax+rax+00000000h]
0x140034660  movzx   edi, byte ptr [rbx]
0x140034663  lea     r11, cs:140000000h
0x14003466a  inc     rbx
0x14003466d  mov     rbp, r9
0x140034670  test    r8d, r8d
0x140034673  jz      loc_1400349FB
0x140034679  movzx   r12d, byte ptr [rbx+1]
0x14003467e  lea     r8, [rbp+1]
0x140034682  movzx   r13d, byte ptr [rbx]
0x140034686  inc     r9
0x140034689  movzx   r10d, word ptr [r15+10h]
0x14003468e  mov     rax, r9
0x140034691  mov     edx, ds:rva lookup_array3[r11+r12*4]
0x140034699  add     edx, ds:rva lookup_array2[r11+r13*4]
0x1400346a1  add     edx, ds:rva lookup_array1[r11+rdi*4]
0x1400346a9  shr     rdx, 0Ch
0x1400346ad  and     edx, 0FFFh
0x1400346b3  lea     rsi, [r15+rdx*2]
0x1400346b7  movzx   edx, word ptr [r15+rdx*2+18h]
0x1400346bd  cmp     dx, r10w
0x1400346c1  jb      loc_140034861
0x1400346c7  mov     r11d, edx
0x1400346ca  sub     r11d, r10d
0x1400346cd  movsxd  rdx, r11d
0x1400346d0  add     rdx, r14
0x1400346d3  cmp     rdx, rbp
0x1400346d6  jz      short loc_1400346E4
0x1400346d8  sub     ax, r14w
0x1400346dc  add     ax, r10w
0x1400346e0  mov     [rsi+18h], ax
0x1400346e4  mov     rcx, [r15+8]
0x1400346e8  cmp     rcx, r8
0x1400346eb  jnb     short loc_1400346F4
0x1400346ed  mov     [r15+8], r8
0x1400346f1  mov     rcx, r8
0x1400346f4  cmp     rdx, r14
0x1400346f7  jnz     loc_140034869
0x1400346fd  mov     r11, [rsp+98h+var_68]
0x140034702  mov     r9, r8
0x140034705  mov     eax, edi
0x140034707  test    dil, dil
0x14003470a  js      loc_14003480D
0x140034710  mov     edi, [rsp+98h+var_78]
0x140034714  lea     ecx, [rdi-8]
0x140034717  shl     eax, cl
0x140034719  or      eax, [rsp+98h+arg_18]
0x140034720  mov     ebp, eax
0x140034722  sar     eax, 8
0x140034725  mov     [r11], al
0x140034728  inc     r11
0x14003472b  shl     ebp, 8
0x14003472e  mov     [rsp+98h+arg_18], ebp
0x140034735  mov     [rsp+98h+var_68], r11
0x14003473a  mov     rdx, [rsp+98h+var_60]
0x14003473f  mov     r8d, [rsp+98h+var_74]
0x140034744  lea     rax, [rdx-2]
0x140034748  cmp     rbx, rax
0x14003474b  jb      loc_140034660
0x140034751  mov     r13, [rsp+98h+var_40]
0x140034756  mov     r10, [rsp+98h+arg_10]
0x14003475e  mov     esi, [rsp+98h+var_70]
0x140034762  mov     r12, [rsp+98h+arg_8]
0x14003476a  cmp     rbx, rdx
0x14003476d  ja      short loc_1400347A8
0x14003476f  nop
0x140034770  movzx   eax, byte ptr [rbx]
0x140034773  test    al, al
0x140034775  js      loc_140035190
0x14003477b  lea     ecx, [rdi-8]
0x14003477e  shl     eax, cl
0x140034780  or      eax, ebp
0x140034782  mov     ebp, eax
0x140034784  sar     eax, 8
0x140034787  mov     [r11], al
0x14003478a  shl     ebp, 8
0x14003478d  inc     r11
0x140034790  lea     rcx, [rbx+1]
0x140034794  test    r8d, r8d
0x140034797  jz      loc_1400351D4
0x14003479d  inc     r9
0x1400347a0  mov     rbx, rcx
0x1400347a3  cmp     rcx, rdx
0x1400347a6  jbe     short loc_140034770
0x1400347a8  mov     rbx, [rsp+98h+var_18]
0x1400347b0  cmp     edi, 10h
0x1400347b3  mov     rdi, [rsp+98h+var_30]
0x1400347b8  jnz     loc_1400351DF
0x1400347be  mov     ecx, [r15+14h]
0x1400347c2  sub     r11d, r12d
0x1400347c5  mov     r12, [rsp+98h+var_38]
0x1400347ca  and     ecx, 800h
0x1400347d0  mov     rbp, [rsp+98h+var_20]
0x1400347d5  cmp     r11d, esi
0x1400347d8  mov     rsi, [rsp+98h+var_28]
0x1400347dd  ja      loc_1400351ED
0x1400347e3  movzx   edx, word ptr [r10]
0x1400347e7  sub     r9d, r14d
0x1400347ea  movzx   eax, [rsp+98h+arg_0]
0x1400347f2  mov     [r10], r11d
0x1400347f5  mov     [r15], r9d
0x1400347f8  test    ecx, ecx
0x1400347fa  jnz     loc_14003522B
0x140034800  add     rsp, 88h
0x140034807  pop     r15
0x140034809  pop     r14
0x14003480b  retn
0x14003480d  lea     edx, [rdi+80h]
0x140034813  mov     edi, [rsp+98h+var_78]
0x140034817  cmp     edi, 9
0x14003481a  jle     short loc_140034843
0x14003481c  lea     ecx, [rdi-9]
0x14003481f  dec     edi
0x140034821  shl     edx, cl
0x140034823  or      edx, [rsp+98h+arg_18]
0x14003482a  mov     eax, edx
0x14003482c  mov     ebp, edx
0x14003482e  sar     eax, 8
0x140034831  mov     [r11], al
0x140034834  shl     ebp, 8
0x140034837  mov     [rsp+98h+var_78], edi
0x14003483b  inc     r11
0x14003483e  jmp     loc_14003472E
0x140034843  or      edx, [rsp+98h+arg_18]
0x14003484a  mov     edi, 10h
0x14003484f  mov     eax, edx
0x140034851  sar     eax, 8
0x140034854  mov     [r11], al
0x140034857  inc     r11
0x14003485a  xor     ebp, ebp
0x14003485c  mov     [r11], dl
0x14003485f  jmp     short loc_140034837
0x140034861  xor     r11d, r11d
0x140034864  jmp     loc_1400346CD
0x140034869  cmp     rdx, rbp
0x14003486c  jz      loc_1400346FD
0x140034872  cmp     rdx, r8
0x140034875  jz      loc_1400346FD
0x14003487b  lea     rax, [rdx+1]
0x14003487f  cmp     rax, rcx
0x140034882  ja      loc_1400346FD
0x140034888  cmp     [rdx-1], dil
0x14003488c  jnz     loc_1400346FD
0x140034892  cmp     [rdx], r13b
0x140034895  jnz     loc_1400346FD
0x14003489b  cmp     [rdx+1], r12b
0x14003489f  jnz     loc_1400346FD
0x1400348a5  mov     r10d, [rsp+98h+var_74]
0x1400348aa  mov     eax, r9d
0x1400348ad  sub     eax, r14d
0x1400348b0  sub     eax, r11d
0x1400348b3  and     eax, 1FFFh
0x1400348b8  test    r10d, r10d
0x1400348bb  jz      loc_140034978
0x1400348c1  add     r9, 2
0x1400348c5  mov     r8, [rsp+98h+var_60]
0x1400348ca  add     rbx, 2
0x1400348ce  add     rdx, 2
0x1400348d2  mov     esi, 3
0x1400348d7  cmp     rbx, r8
0x1400348da  jnb     short loc_140034902
0x1400348dc  cmp     rdx, [r15+8]
0x1400348e0  ja      short loc_140034902
0x1400348e2  movzx   ecx, byte ptr [rbx]
0x1400348e5  cmp     [rdx], cl
0x1400348e7  jnz     short loc_140034902
0x1400348e9  inc     rdx
0x1400348ec  inc     rbx
0x1400348ef  test    r10d, r10d
0x1400348f2  jz      loc_140034A03
0x1400348f8  inc     esi
0x1400348fa  inc     r9
0x1400348fd  cmp     rbx, r8
0x140034900  jb      short loc_1400348DC
0x140034902  mov     edi, [rsp+98h+var_78]
0x140034906  cmp     eax, 140h
0x14003490b  jnb     loc_140034998
0x140034911  cmp     eax, 40h ; '@'
0x140034914  jb      short loc_140034988
0x140034916  lea     edx, [rax+0DC0h]
0x14003491c  cmp     edi, 0Ch
0x14003491f  jle     loc_140034A32
0x140034925  lea     ecx, [rdi-0Ch]
0x140034928  mov     r10, [rsp+98h+var_68]
0x14003492d  lea     edi, [rcx+8]
0x140034930  shl     edx, cl
0x140034932  or      edx, [rsp+98h+arg_18]
0x140034939  mov     ebp, edx
0x14003493b  mov     [rsp+98h+var_78], edi
0x14003493f  mov     eax, edx
0x140034941  sar     eax, 8
0x140034944  shl     ebp, 8
0x140034947  mov     [rsp+98h+arg_18], ebp
0x14003494e  mov     [r10], al
0x140034951  cmp     esi, 10h
0x140034954  jnz     loc_140034A79
0x14003495a  mov     eax, 0E0h
0x14003495f  lea     ecx, [rdi-8]
0x140034962  shl     eax, cl
0x140034964  lea     r11, [r10+2]
0x140034968  or      eax, ebp
0x14003496a  mov     ebp, eax
0x14003496c  sar     eax, 8
0x14003496f  mov     [r10+1], al
0x140034973  jmp     loc_14003472B
0x140034978  mov     [r8], r13b
0x14003497b  lea     r9, [rbp+3]
0x14003497f  mov     [rbp+2], r12b
0x140034983  jmp     loc_1400348C5
0x140034988  lea     edx, [rax+3C0h]
0x14003498e  cmp     edi, 0Ah
0x140034991  jle     short loc_140034A0B
0x140034993  lea     ecx, [rdi-0Ah]
0x140034996  jmp     short loc_140034928
0x140034998  mov     r10, [rsp+98h+var_68]
0x14003499d  lea     edx, [rax-140h]
0x1400349a3  lea     r8d, [rdx+0C000h]
0x1400349aa  mov     ebp, edx
0x1400349ac  sar     r8d, 8
0x1400349b0  lea     ecx, [rdi-8]
0x1400349b3  shl     r8d, cl
0x1400349b6  or      r8d, [rsp+98h+arg_18]
0x1400349be  mov     eax, r8d
0x1400349c1  sar     eax, 8
0x1400349c4  mov     [r10], al
0x1400349c7  inc     r10
0x1400349ca  shl     r8d, 8
0x1400349ce  shl     ebp, cl
0x1400349d0  or      ebp, r8d
0x1400349d3  mov     eax, ebp
0x1400349d5  jmp     loc_140034941
0x1400349da  cmp     ecx, 1FFEh
0x1400349e0  jnb     loc_1400345EB
0x1400349e6  test    eax, eax
0x1400349e8  jz      loc_1400345EB
0x1400349ee  mov     [rsp+98h+arg_0], 20h ; ' '
0x1400349f6  jmp     loc_1400345FC
0x1400349fb  mov     [r9], dil
0x1400349fe  jmp     loc_140034679
0x140034a03  mov     [r9], cl
0x140034a06  jmp     loc_1400348F8
0x140034a0b  mov     r10, [rsp+98h+var_68]
0x140034a10  add     edi, 0FFFFFFFEh
0x140034a13  mov     r8d, edx
0x140034a16  mov     [rsp+98h+var_78], edi
0x140034a1a  shr     r8d, 8
0x140034a1e  mov     ecx, edi
0x140034a20  shl     r8d, cl
0x140034a23  or      r8d, [rsp+98h+arg_18]
0x140034a2b  cmp     edi, 9
0x140034a2e  jl      short loc_140034A57
0x140034a30  jmp     short loc_140034A6E
0x140034a32  mov     r10, [rsp+98h+var_68]
0x140034a37  add     edi, 0FFFFFFFCh
0x140034a3a  mov     r8d, edx
  ... truncated ...
```
