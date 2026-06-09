# Planar::BDDecompressBitmap24(uchar *,uchar *,uint,uint,ushort)

- ea: `0x18034baf8`
- end: `0x18034d512`
- name: `?BDDecompressBitmap24@Planar@@YAJPEAE0IIG@Z`
- size: `6682`
- prototype: `__int64 __fastcall(Planar *this, unsigned __int8 *, unsigned __int8 *, int, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180350350`

## callees

- `0x18003f834`
- `0x1800415dc`
- `0x180045338`
- `0x180051830`
- `0x18034baf8`

## string_xrefs

- `0x18034bb7d`: `Decompress reads one byte end of buffer`
- `0x18034c1eb`: `Decompress reads one byte end of buffer`
- `0x18034c212`: `Decompress reads one byte end of buffer`
- `0x18034c319`: `Decompress reads one byte end of buffer`
- `0x18034c33e`: `Decompress reads one byte end of buffer`
- `0x18034c404`: `Decompress reads one byte end of buffer`
- `0x18034c42b`: `Decompress reads one byte end of buffer`
- `0x18034c569`: `Decompress reads one byte end of buffer`
- `0x18034c598`: `Decompress reads one byte end of buffer`
- `0x18034c5d9`: `Decompress reads one byte end of buffer`
- `0x18034c73a`: `Decompress reads one byte end of buffer`
- `0x18034c764`: `Decompress reads one byte end of buffer`
- `0x18034c7aa`: `Decompress reads one byte end of buffer`
- `0x18034c856`: `Decompress reads one byte end of buffer`
- `0x18034cc46`: `Decompress reads one byte end of buffer`
- `0x18034d159`: `Decompress reads one byte end of buffer`
- `0x18034d180`: `Decompress reads one byte end of buffer`
- `0x18034bc69`: `Decompress write off end of buffer`
- `0x18034bca3`: `Decompress write off end of buffer`
- `0x18034bd18`: `Decompress write off end of buffer`
- `0x18034bea3`: `Decompress write off end of buffer`
- `0x18034bf89`: `Decompress write off end of buffer`
- `0x18034c12f`: `Decompress write off end of buffer`
- `0x18034c262`: `Decompress write off end of buffer`
- `0x18034c385`: `Decompress write off end of buffer`
- `0x18034c472`: `Decompress write off end of buffer`
- `0x18034c678`: `Decompress write off end of buffer`
- `0x18034c8bd`: `Decompress write off end of buffer`
- `0x18034cace`: `Decompress write off end of buffer`
- `0x18034ccb5`: `Decompress write off end of buffer`
- `0x18034cf59`: `Decompress write off end of buffer`
- `0x18034d1b8`: `Decompress write off end of buffer`
- `0x18034d24a`: `Decompress write off end of buffer`
- `0x18034d2e0`: `Decompress write off end of buffer`
- `0x18034d321`: `Decompress write off end of buffer`
- `0x18034bce5`: `Decompress reads off end of buffer`
- `0x18034bf56`: `Decompress reads off end of buffer`
- `0x18034c1bf`: `Decompress reads off end of buffer`
- `0x18034c237`: `Decompress reads off end of buffer`
- `0x18034c2ee`: `Decompress reads off end of buffer`
- `0x18034c36b`: `Decompress reads off end of buffer`
- `0x18034c3d8`: `Decompress reads off end of buffer`
- `0x18034c450`: `Decompress reads off end of buffer`
- `0x18034c5fd`: `Decompress reads off end of buffer`
- `0x18034c633`: `Decompress reads off end of buffer`
- `0x18034c6b8`: `Decompress reads off end of buffer`
- `0x18034c7d3`: `Decompress reads off end of buffer`
- `0x18034c810`: `Decompress reads off end of buffer`
- `0x18034c899`: `Decompress reads off end of buffer`
- `0x18034cc8c`: `Decompress reads off end of buffer`
- `0x18034d12d`: `Decompress reads off end of buffer`
- `0x18034d1ec`: `Decompress reads off end of buffer`
- `0x18034d283`: `Decompress reads off end of buffer`

## pseudocode

```c
__int64 __fastcall Planar::BDDecompressBitmap24(
        Planar *this,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        int a4,
        unsigned __int16 a5)
{
  unsigned __int8 *v5; // r15
  unsigned __int8 *v6; // r12
  int v7; // eax
  int v8; // r13d
  unsigned __int8 *v9; // rdi
  unsigned int v10; // esi
  unsigned int v11; // ebp
  unsigned __int8 *v12; // rbx
  int v13; // r14d
  char v14; // al
  char v15; // r13
  unsigned __int8 *v16; // r14
  int v17; // ecx
  __int64 v18; // rcx
  unsigned __int16 v19; // dx
  int v20; // edx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  unsigned __int8 *v24; // rbx
  unsigned __int8 *v25; // rdx
  unsigned __int8 *v26; // rcx
  unsigned int v27; // r8d
  unsigned int v28; // eax
  unsigned __int8 *v29; // r14
  int v30; // ecx
  int v31; // edx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  _BYTE *v36; // r10
  __int64 v37; // rcx
  __int64 v38; // rcx
  unsigned __int8 *v39; // rax
  int v40; // r14d
  unsigned __int8 *v41; // rdi
  unsigned __int8 v42; // r14
  int v43; // r13d
  int v44; // ecx
  int v45; // ecx
  int v46; // eax
  char v47; // al
  int v48; // r14d
  unsigned int v49; // r13d
  int v50; // r14d
  unsigned __int8 *v51; // rdi
  unsigned __int8 v52; // r14
  int v53; // r13d
  int v54; // ecx
  int v55; // ecx
  char v56; // r12
  int v57; // r12d
  char v58; // r12
  unsigned __int8 *v59; // r13
  __int16 v60; // cx
  unsigned __int8 v61; // ah
  char v62; // r13
  int v63; // r13d
  unsigned int v64; // r13d
  char v65; // r13
  char v66; // r14
  int v67; // ecx
  _BYTE *v68; // rbx
  int v69; // edx
  int v70; // edx
  int v71; // edx
  int v72; // edx
  _BYTE *v73; // r8
  int v74; // edx
  _BYTE *v75; // rbx
  int v76; // edx
  _BYTE *v77; // r8
  unsigned int v78; // edx
  unsigned int v79; // ecx
  unsigned __int8 v80; // al
  unsigned __int8 v81; // r8
  _BYTE *v82; // r8
  _BYTE *v83; // rax
  char v84; // r10
  char v85; // r11
  char v86; // bl
  char v87; // r8
  char v88; // r9
  char v89; // r8
  char v90; // r9
  char v91; // r8
  char v92; // r9
  char v93; // r8
  char v94; // r9
  char v95; // al
  char v96; // r8
  char v97; // r14
  int v98; // eax
  unsigned __int8 *v99; // rdx
  int v100; // ecx
  unsigned int v101; // r13d
  unsigned __int8 *v102; // rcx
  unsigned __int8 *v103; // r9
  int v104; // edx
  int v105; // eax
  unsigned __int8 *v106; // rcx
  int v107; // edx
  unsigned int v108; // r10d
  int v109; // edx
  unsigned int v110; // r10d
  int v111; // edx
  unsigned int v112; // r10d
  int v113; // edx
  unsigned int v114; // r10d
  int v115; // edx
  unsigned int v116; // r10d
  int v117; // edx
  int v118; // edx
  int v119; // eax
  int v120; // eax
  unsigned __int8 v121; // r11
  unsigned int v122; // ecx
  unsigned __int8 *v123; // r9
  unsigned __int8 v124; // al
  unsigned __int8 v125; // r8
  unsigned int v126; // r13d
  unsigned __int8 *v127; // r8
  unsigned __int8 *v128; // rax
  unsigned __int8 v129; // r9
  unsigned __int8 v130; // r10
  unsigned int v131; // r10d
  unsigned __int8 v132; // r8
  unsigned __int8 v133; // r9
  unsigned int v134; // r10d
  unsigned __int8 v135; // r8
  unsigned __int8 v136; // r9
  unsigned int v137; // r10d
  unsigned __int8 v138; // r8
  unsigned __int8 v139; // r9
  unsigned int v140; // r10d
  unsigned __int8 v141; // r8
  unsigned __int8 v142; // r9
  unsigned __int8 *v143; // r8
  unsigned int v144; // r10d
  unsigned __int8 v145; // al
  unsigned __int8 v146; // r9
  unsigned __int8 v147; // al
  int v148; // r14d
  char v149; // r14
  unsigned __int8 *v150; // r13
  int v151; // ecx
  unsigned __int8 *v152; // r13
  unsigned __int16 v153; // cx
  unsigned __int8 v155; // [rsp+30h] [rbp-68h]
  unsigned __int8 v156; // [rsp+31h] [rbp-67h]
  int v157; // [rsp+34h] [rbp-64h]
  int v158; // [rsp+38h] [rbp-60h]
  unsigned __int8 *v159; // [rsp+40h] [rbp-58h]
  unsigned __int8 v160; // [rsp+A0h] [rbp+8h]
  unsigned __int8 *v161; // [rsp+A0h] [rbp+8h]
  unsigned __int8 *v162; // [rsp+A0h] [rbp+8h]
  unsigned __int8 v164; // [rsp+B0h] [rbp+18h]
  unsigned __int8 v165; // [rsp+B0h] [rbp+18h]
  unsigned __int8 v166; // [rsp+B8h] [rbp+20h]
  unsigned __int8 v167; // [rsp+B8h] [rbp+20h]

  v5 = (unsigned __int8 *)this + (unsigned int)a3;
  v6 = &a2[a4];
  v158 = 0;
  v7 = (int)a2;
  v159 = v6;
  v8 = 1;
  v9 = (unsigned __int8 *)this;
  v157 = 1;
  v10 = 0;
  v11 = 0xFFFFFF;
  v12 = a2;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v9 >= v5 )
          return v10;
        if ( v8 && (int)v12 - v7 >= (unsigned int)a5 )
        {
          v8 = 0;
          v157 = 0;
          v158 = 0;
        }
        if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586815;
        v13 = *v9;
        v14 = *v9 & 0xE0;
        if ( !v14 )
        {
          if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586802;
          v149 = *v9++;
          v148 = v149 & 0x1F;
          if ( !v148 )
          {
            if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586802;
            v148 = *v9++ + 32;
          }
          goto LABEL_249;
        }
        if ( (_BYTE)v13 != 0xF0 )
          break;
        if ( !(unsigned int)CheckReadNBytes(v9 + 1, v5, 2u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586798;
        v148 = *(unsigned __int16 *)(v9 + 1);
        v9 += 3;
LABEL_249:
        if ( v8 )
        {
          if ( v158 )
          {
            if ( !(unsigned int)CheckWriteNBytes(v12, v6, 3u, L"Decompress write off end of buffer") )
              return (unsigned int)-1626586766;
            v12[2] = v11;
            v12[1] = BYTE1(v11);
            *v12 = BYTE2(v11);
            v12 += 3;
            --v148;
          }
          if ( !(unsigned int)CheckWriteNBytes(v12, v6, (unsigned int)(3 * v148), L"Decompress write off end of buffer") )
            return (unsigned int)-1626586761;
          for ( ; v148; --v148 )
          {
            *(_WORD *)(v12 + 1) = 0;
            *v12 = 0;
            v12 += 3;
          }
        }
        else
        {
          if ( v158 )
          {
            if ( !(unsigned int)CheckWriteNBytes(v12, v6, 3u, L"Decompress write off end of buffer") )
              return (unsigned int)-1626586788;
            v150 = &v12[-a5];
            if ( !(unsigned int)CheckReadNBytes2Ended(v150, a2, v6, 3u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586787;
            v151 = v11 ^ ((*v150 << 16) | v150[2] | (v150[1] << 8));
            v12[2] = v11 ^ v150[2];
            v12[1] = BYTE1(v151);
            *v12 = BYTE2(v151);
            v12 += 3;
            --v148;
          }
          if ( !(unsigned int)CheckWriteNBytes(v12, v6, (unsigned int)(3 * v148), L"Decompress write off end of buffer") )
            return (unsigned int)-1626586779;
          while ( v148 )
          {
            v152 = &v12[-a5];
            if ( !(unsigned int)CheckReadNBytes2Ended(v152, a2, v6, 3u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586775;
            --v148;
            v153 = _byteswap_ushort(*(_WORD *)(v152 + 1));
            *v12 = *v152;
            v12[2] = v153;
            v12[1] = HIBYTE(v153);
            v12 += 3;
          }
          v8 = v157;
        }
        v158 = 1;
LABEL_267:
        v7 = (int)a2;
      }
      v158 = 0;
      v15 = v13 & 0xF0;
      if ( v14 != 64 && v15 != -48 )
        break;
      if ( (_BYTE)v13 == 0xF2 || (_BYTE)v13 == 0xF7 )
      {
LABEL_123:
        if ( !(unsigned int)CheckReadNBytes(v9 + 1, v5, 2u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586727;
        v64 = *(unsigned __int16 *)(v9 + 1);
        v9 += 3;
        goto LABEL_125;
      }
      if ( v14 == 64 )
      {
        if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586719;
        v62 = *v9++;
        v63 = v62 & 0x1F;
        if ( v63 )
          goto LABEL_118;
        if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586719;
      }
      else
      {
        if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586715;
        v65 = *v9++;
        v63 = v65 & 0xF;
        if ( v63 )
        {
LABEL_118:
          v64 = 8 * v63;
          goto LABEL_125;
        }
        if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586715;
      }
      v64 = *v9++ + 1;
LABEL_125:
      if ( (v13 & 0xF0) == 0xD0 || (_BYTE)v13 == 0xF7 )
      {
        if ( !(unsigned int)CheckReadNBytes(v9, v5, 3u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586708;
        v11 = v9[2] | (*v9 << 16) | (v9[1] << 8);
        v9 += 3;
      }
      while ( v64 > 8 )
      {
        if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586691;
        v66 = *v9;
        if ( v157 )
        {
          if ( !(unsigned int)CheckWriteNBytes(v12, v6, 0x18u, L"Decompress write off end of buffer") )
            return (unsigned int)-1626586679;
          v79 = v11 >> 8;
          if ( (v66 & 1) != 0 )
          {
            *v12 = BYTE2(v11);
            v80 = BYTE1(v11);
            v81 = v11;
          }
          else
          {
            v80 = 0;
            *v12 = 0;
            v81 = 0;
          }
          v12[2] = v81;
          v82 = v12 + 3;
          v12[1] = v80;
          v83 = v12 + 3;
          if ( (v66 & 2) != 0 )
          {
            v84 = BYTE1(v11);
            v85 = v11;
            v86 = BYTE2(v11);
          }
          else
          {
            v84 = 0;
            v85 = 0;
            v86 = 0;
          }
          *v82 = v86;
          v82[2] = v85;
          v82[1] = v84;
          if ( (v66 & 4) != 0 )
          {
            v82[3] = BYTE2(v11);
            v87 = BYTE1(v11);
            v88 = v11;
          }
          else
          {
            v82[3] = 0;
            v87 = 0;
            v88 = 0;
          }
          v83[5] = v88;
          v83[4] = v87;
          if ( (v66 & 8) != 0 )
          {
            v83[6] = BYTE2(v11);
            v89 = BYTE1(v11);
            v90 = v11;
          }
          else
          {
            v83[6] = 0;
            v89 = 0;
            v90 = 0;
          }
          v83[8] = v90;
          v83[7] = v89;
          if ( (v66 & 0x10) != 0 )
          {
            v83[9] = BYTE2(v11);
            v91 = BYTE1(v11);
            v92 = v11;
          }
          else
          {
            v83[9] = 0;
            v91 = 0;
            v92 = 0;
          }
          v83[11] = v92;
          v83[10] = v91;
          if ( (v66 & 0x20) != 0 )
          {
            v83[12] = BYTE2(v11);
            v93 = BYTE1(v11);
            v94 = v11;
          }
          else
          {
            v83[12] = 0;
            v93 = 0;
            v94 = 0;
          }
          v83[14] = v94;
          v75 = v83 + 15;
          v83[13] = v93;
          if ( (v66 & 0x40) != 0 )
          {
            *v75 = BYTE2(v11);
            v95 = BYTE1(v11);
            v96 = v11;
          }
          else
          {
            *v75 = 0;
            v95 = 0;
            v96 = 0;
          }
          v75[2] = v96;
          v77 = v75 + 3;
          v75[1] = v95;
          if ( v66 >= 0 )
          {
            *v77 = 0;
            LOBYTE(v79) = 0;
            LOBYTE(v78) = 0;
          }
          else
          {
            *v77 = BYTE2(v11);
            LOBYTE(v78) = v11;
          }
        }
        else
        {
          v161 = &v12[-a5];
          if ( !(unsigned int)CheckReadNBytes2Ended(v161, a2, v6, 3u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586687;
          if ( !(unsigned int)CheckWriteNBytes(v12, v6, 0x18u, L"Decompress write off end of buffer") )
            return (unsigned int)-1626586683;
          v67 = (*v161 << 16) | v161[2] | (v161[1] << 8);
          if ( (v66 & 1) != 0 )
            v67 ^= v11;
          *v12 = BYTE2(v67);
          v12[2] = v67;
          v12[1] = BYTE1(v67);
          v68 = v12 + 3;
          v69 = ((unsigned __int8)v68[-a5] << 16) | (unsigned __int8)v68[-a5 + 2] | ((unsigned __int8)v68[-a5 + 1] << 8);
          if ( (v66 & 2) != 0 )
            v69 ^= v11;
          *v68 = BYTE2(v69);
          v68[2] = v69;
          v68[1] = BYTE1(v69);
          v70 = (unsigned __int8)v68[-a5 + 5]
              | ((unsigned __int8)v68[-a5 + 3] << 16)
              | ((unsigned __int8)v68[-a5 + 4] << 8);
          if ( (v66 & 4) != 0 )
            v70 ^= v11;
          v68[3] = BYTE2(v70);
          v68[5] = v70;
          v68[4] = BYTE1(v70);
          v71 = (unsigned __int8)v68[-a5 + 8]
              | ((unsigned __int8)v68[-a5 + 6] << 16)
              | ((unsigned __int8)v68[-a5 + 7] << 8);
          if ( (v66 & 8) != 0 )
            v71 ^= v11;
          v68[6] = BYTE2(v71);
          v68[8] = v71;
          v68[7] = BYTE1(v71);
          v72 = (unsigned __int8)v68[-a5 + 11]
              | ((unsigned __int8)v68[-a5 + 9] << 16)
              | ((unsigned __int8)v68[-a5 + 10] << 8);
          if ( (v66 & 0x10) != 0 )
            v72 ^= v11;
          v68[9] = BYTE2(v72);
          v68[11] = v72;
          v68[10] = BYTE1(v72);
          v73 = v68 + 12;
          v74 = ((unsigned __int8)v68[-a5 + 12] << 16)
              | (unsigned __int8)v68[-a5 + 14]
              | ((unsigned __int8)v68[-a5 + 13] << 8);
          if ( (v66 & 0x20) != 0 )
            v74 ^= v11;
          v75 = v68 + 15;
          *v73 = BYTE2(v74);
          v73[2] = v74;
          v73[1] = BYTE1(v74);
          v76 = (unsigned __int8)v75[-a5 + 2] | ((unsigned __int8)v75[-a5] << 16) | ((unsigned __int8)v75[-a5 + 1] << 8);
          if ( (v66 & 0x40) != 0 )
            v76 ^= v11;
          v77 = v75 + 3;
          *v75 = BYTE2(v76);
          v75[2] = v76;
          v75[1] = BYTE1(v76);
          v78 = ((unsigned __int8)v75[-a5 + 3] << 16)
              | (unsigned __int8)v75[-a5 + 5]
              | ((unsigned __int8)v75[-a5 + 4] << 8);
          if ( v66 < 0 )
            v78 ^= v11;
          v79 = v78 >> 8;
          *v77 = BYTE2(v78);
        }
        ++v9;
        v64 -= 8;
        v12 = v75 + 6;
        v77[2] = v78;
        v77[1] = v79;
      }
      if ( !v64 )
      {
LABEL_3:
        v7 = (int)a2;
        goto LABEL_4;
      }
      if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
        return (unsigned int)-1626586673;
      v97 = *v9++;
      if ( v157 )
      {
        v119 = 8;
        if ( v64 < 8 )
          v119 = v64;
        v120 = CheckWriteNBytes(v12, v6, (unsigned int)(3 * v119), L"Decompress write off end of buffer");
        v121 = 0;
        if ( !v120 )
          return (unsigned int)-1626586661;
        v122 = v11 >> 8;
        v123 = v12;
        if ( (v97 & 1) != 0 )
        {
          *v12 = BYTE2(v11);
          v124 = BYTE1(v11);
          v125 = v11;
        }
        else
        {
          *v12 = 0;
          v124 = 0;
          v125 = 0;
        }
        v12[2] = v125;
        v12[1] = v124;
        v12 += 3;
        v7 = (int)a2;
        v126 = v64 - 1;
        if ( !v126 )
          goto LABEL_4;
        v127 = v123 + 3;
        v128 = v123 + 3;
        if ( (v97 & 2) != 0 )
        {
          v129 = BYTE1(v11);
          v130 = v11;
          v121 = BYTE2(v11);
        }
        else
        {
          v129 = 0;
          v130 = 0;
        }
        *v12 = v121;
        v12[2] = v130;
        v12 += 3;
        v131 = v126 - 1;
        v127[1] = v129;
        v8 = v157;
        if ( !v131 )
          goto LABEL_267;
        if ( (v97 & 4) != 0 )
        {
          *v12 = BYTE2(v11);
          v132 = BYTE1(v11);
          v133 = v11;
        }
        else
        {
          *v12 = 0;
          v132 = 0;
          v133 = 0;
        }
        v128[5] = v133;
        v128[4] = v132;
        v12 = v128 + 6;
        v134 = v131 - 1;
        if ( !v134 )
          goto LABEL_267;
        if ( (v97 & 8) != 0 )
        {
          *v12 = BYTE2(v11);
          v135 = BYTE1(v11);
          v136 = v11;
        }
        else
        {
          *v12 = 0;
          v135 = 0;
          v136 = 0;
        }
        v128[8] = v136;
        v128[7] = v135;
        v12 = v128 + 9;
        v137 = v134 - 1;
        if ( !v137 )
          goto LABEL_267;
        if ( (v97 & 0x10) != 0 )
        {
          *v12 = BYTE2(v11);
          v138 = BYTE1(v11);
          v139 = v11;
        }
        else
        {
          *v12 = 0;
          v138 = 0;
          v139 = 0;
        }
        v128[11] = v139;
        v128[10] = v138;
        v12 = v128 + 12;
        v140 = v137 - 1;
        if ( !v140 )
          goto LABEL_267;
        if ( (v97 & 0x20) != 0 )
        {
          *v12 = BYTE2(v11);
          v141 = BYTE1(v11);
          v142 = v11;
        }
        else
        {
          *v12 = 0;
          v141 = 0;
          v142 = 0;
        }
        v128[14] = v142;
        v128[13] = v141;
        v143 = v128 + 15;
        v7 = (int)a2;
        v12 = v143;
        v144 = v140 - 1;
        if ( v144 )
        {
          if ( (v97 & 0x40) != 0 )
          {
            *v143 = BYTE2(v11);
            v145 = BYTE1(v11);
            v146 = v11;
          }
          else
          {
            *v143 = 0;
            v145 = 0;
            v146 = 0;
          }
          v143[2] = v146;
          v12 = v143 + 3;
          v143[1] = v145;
          v7 = (int)a2;
          if ( v144 != 1 )
          {
            if ( v97 >= 0 )
            {
              *v12 = 0;
              LOBYTE(v122) = 0;
              v147 = 0;
            }
            else
            {
              *v12 = BYTE2(v11);
              v147 = v11;
            }
            v143[5] = v147;
            v143[4] = v122;
            v12 = v143 + 6;
            goto LABEL_267;
          }
        }
      }
      else
      {
        v162 = &v12[-a5];
        if ( !(unsigned int)CheckReadNBytes2Ended(v162, a2, v6, 3u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586669;
        v98 = 8;
        if ( v64 < 8 )
          v98 = v64;
        if ( !(unsigned int)CheckWriteNBytes(v12, v6, (unsigned int)(3 * v98), L"Decompress write off end of buffer") )
          return (unsigned int)-1626586665;
        v99 = v12;
        v100 = (*v162 << 16) | v162[2] | (v162[1] << 8);
        if ( (v97 & 1) != 0 )
          v100 ^= v11;
        *v12 = BYTE2(v100);
        v12[2] = v100;
        v12[1] = BYTE1(v100);
        v12 += 3;
        v7 = (int)a2;
        v101 = v64 - 1;
        if ( v101 )
        {
          v102 = &v12[-a5];
          v103 = v99 + 3;
          v104 = v102[2] | (v102[1] << 8);
          v105 = *v102 << 16;
          v106 = v12;
          v107 = v105 | v104;
          if ( (v97 & 2) != 0 )
            v107 ^= v11;
          *v12 = BYTE2(v107);
          v12 += 3;
          v106[2] = v107;
          v108 = v101 - 1;
          v8 = 0;
          v106[1] = BYTE1(v107);
          v7 = (int)a2;
          if ( v108 )
          {
            v109 = v12[-a5 + 2] | (v12[-a5] << 16) | (v12[-a5 + 1] << 8);
            if ( (v97 & 4) != 0 )
              v109 ^= v11;
            *v12 = BYTE2(v109);
            v103[5] = v109;
            v103[4] = BYTE1(v109);
            v12 = v103 + 6;
            v7 = (int)a2;
            v110 = v108 - 1;
            if ( v110 )
            {
              v111 = (v12[-a5] << 16) | v12[-a5 + 2] | (v12[-a5 + 1] << 8);
              if ( (v97 & 8) != 0 )
                v111 ^= v11;
              *v12 = BYTE2(v111);
              v103[8] = v111;
              v103[7] = BYTE1(v111);
              v12 = v103 + 9;
              v7 = (int)a2;
              v112 = v110 - 1;
              if ( v112 )
              {
                v113 = (v12[-a5] << 16) | v12[-a5 + 2] | (v12[-a5 + 1] << 8);
                if ( (v97 & 0x10) != 0 )
                  v113 ^= v11;
                *v12 = BYTE2(v113);
                v103[11] = v113;
                v103[10] = BYTE1(v113);
                v12 = v103 + 12;
                v7 = (int)a2;
                v114 = v112 - 1;
                if ( v114 )
                {
                  v115 = (v12[-a5] << 16) | v12[-a5 + 2] | (v12[-a5 + 1] << 8);
                  if ( (v97 & 0x20) != 0 )
                    v115 ^= v11;
                  *v12 = BYTE2(v115);
                  v103[14] = v115;
                  v103[13] = BYTE1(v115);
                  v12 = v103 + 15;
                  v7 = (int)a2;
                  v116 = v114 - 1;
                  if ( v116 )
                  {
                    v117 = (v103[-a5 + 15] << 16) | v103[-a5 + 17] | (v103[-a5 + 16] << 8);
                    if ( (v97 & 0x40) != 0 )
                      v117 ^= v11;
                    v12 = v103 + 18;
                    v103[15] = BYTE2(v117);
                    v103[17] = v117;
                    v103[16] = BYTE1(v117);
                    v7 = (int)a2;
                    if ( v116 != 1 )
                    {
                      v118 = (v12[-a5] << 16) | v12[-a5 + 2] | (v12[-a5 + 1] << 8);
                      if ( v97 < 0 )
                        v118 ^= v11;
                      *v12 = BYTE2(v118);
                      v103[20] = v118;
                      v103[19] = BYTE1(v118);
                      v12 = v103 + 21;
                      goto LABEL_267;
                    }
                  }
                }
              }
            }
          }
        }
        else
        {
LABEL_4:
          v8 = v157;
        }
      }
    }
    if ( (_BYTE)v13 == 0xF2 || (_BYTE)v13 == 0xF7 )
      goto LABEL_123;
    if ( v14 == 32 || v15 == -64 )
      break;
    if ( (_BYTE)v13 == 0xF1 || (_BYTE)v13 == 0xF6 )
      goto LABEL_98;
    if ( v15 == -32 )
    {
      if ( (_BYTE)v13 == 0xF8 )
      {
LABEL_75:
        if ( !(unsigned int)CheckReadNBytes(v9 + 1, v5, 2u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586584;
        v50 = *(unsigned __int16 *)(v9 + 1);
        v51 = v9 + 3;
        goto LABEL_81;
      }
      if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
        return (unsigned int)-1626586578;
      v52 = *v9;
      v51 = v9 + 1;
      v50 = v52 & 0xF;
      if ( !v50 )
      {
        if ( !(unsigned int)CheckReadOneByte(v51, v5, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586578;
        v50 = *v51++ + 16;
      }
LABEL_81:
      if ( !(unsigned int)CheckReadNBytes(v51, v5, 6u, L"Decompress reads off end of buffer") )
        return (unsigned int)-1626586574;
      v53 = v51[1];
      v165 = *v51;
      v167 = v51[2];
      v160 = v51[4];
      v155 = v51[3];
      v156 = v51[5];
      if ( !(unsigned int)CheckWriteNBytes(v12, v6, (unsigned int)(6 * v50), L"Decompress write off end of buffer") )
        return (unsigned int)-1626586568;
      v54 = v53;
      v9 = v51 + 6;
      v8 = v157;
      v55 = v167 | (v165 << 16) | (v54 << 8);
      v7 = (int)a2;
      if ( v50 )
      {
        do
        {
          v12[2] = v55;
          v12[1] = BYTE1(v55);
          *v12 = BYTE2(v55);
          v12[5] = v156;
          v12[4] = v160;
          v12[3] = (unsigned int)(v156 | (v155 << 16) | (v160 << 8)) >> 16;
          v12 += 6;
          --v50;
        }
        while ( v50 );
        goto LABEL_267;
      }
    }
    else
    {
      if ( (_BYTE)v13 == 0xF8 )
        goto LABEL_75;
      if ( v14 == (char)0x80 )
      {
        if ( (_BYTE)v13 == 0xF4 )
        {
LABEL_63:
          if ( !(unsigned int)CheckReadNBytes(v9 + 1, v5, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586548;
          v46 = *(unsigned __int16 *)(v9 + 1);
          v9 += 3;
          goto LABEL_69;
        }
        if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586542;
        v47 = *v9++;
        v46 = v47 & 0x1F;
        if ( !v46 )
        {
          if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586542;
          v46 = *v9++ + 32;
        }
LABEL_69:
        v48 = 3 * v46;
        v49 = 3 * v46;
        if ( !(unsigned int)CheckReadNBytes(v9, v5, (unsigned int)(3 * v46), L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586534;
        if ( !(unsigned int)CheckWriteNBytes(v12, v6, v49, L"Decompress write off end of buffer") )
          return (unsigned int)-1626586533;
        v7 = (int)a2;
        v8 = v157;
        if ( v48 )
        {
          do
          {
            --v48;
            *v12++ = *v9++;
          }
          while ( v48 > 0 );
          goto LABEL_267;
        }
      }
      else
      {
        if ( (_BYTE)v13 == 0xF4 )
          goto LABEL_63;
        if ( v14 != 96 )
        {
          if ( (_BYTE)v13 != 0xF3 )
          {
            switch ( v13 )
            {
              case 249:
                v8 = v157;
                if ( v157 )
                {
                  if ( !(unsigned int)CheckWriteNBytes(v12, v6, 0x18u, L"Decompress write off end of buffer") )
                    return (unsigned int)-1626586458;
                  v12[2] = v11;
                  v12[1] = BYTE1(v11);
                  *v12 = BYTE2(v11);
                  v12[3] = BYTE2(v11);
                  v39 = v12 + 18;
                  v12[5] = v11;
                  v12[4] = BYTE1(v11);
                  *(_WORD *)(v12 + 7) = 0;
                  v12[6] = 0;
                  *((_WORD *)v12 + 5) = 0;
                  v12[9] = 0;
                  *(_WORD *)(v12 + 13) = 0;
                  v12[12] = 0;
                  *((_WORD *)v12 + 8) = 0;
                  v12[15] = 0;
                  v12 += 24;
                  *(_WORD *)(v39 + 1) = 0;
                  *v39 = 0;
                  *((_WORD *)v39 + 2) = 0;
                  v39[3] = 0;
                  goto LABEL_34;
                }
                v29 = &v12[-a5];
                if ( !(unsigned int)CheckReadNBytes2Ended(v29, a2, v6, 3u, L"Decompress reads off end of buffer") )
                  return (unsigned int)-1626586466;
                if ( !(unsigned int)CheckWriteNBytes(v12, v6, 0x18u, L"Decompress write off end of buffer") )
                  return (unsigned int)-1626586462;
                v30 = v11 ^ ((*v29 << 16) | v29[2] | (v29[1] << 8));
                v12[2] = v11 ^ v29[2];
                v12[1] = BYTE1(v30);
                *v12 = BYTE2(v30);
                v31 = v11 ^ ((v12[-a5 + 3] << 16) | v12[-a5 + 5] | (v12[-a5 + 4] << 8));
                v12[5] = v11 ^ v12[-a5 + 5];
                v12[4] = BYTE1(v31);
                v32 = (__int64)&v12[-a5 + 6];
                v12[3] = BYTE2(v31);
                LOWORD(v30) = _byteswap_ushort(*(_WORD *)(v32 + 1));
                v12[6] = *(_BYTE *)v32;
                v12[8] = v30;
                v33 = (__int64)&v12[-a5 + 9];
                v12[7] = BYTE1(v30);
                LOWORD(v30) = _byteswap_ushort(*(_WORD *)(v33 + 1));
                v12[9] = *(_BYTE *)v33;
                v12[11] = v30;
                v34 = (__int64)&v12[-a5 + 12];
                v12[10] = BYTE1(v30);
                LOWORD(v30) = _byteswap_ushort(*(_WORD *)(v34 + 1));
                v12[12] = *(_BYTE *)v34;
                v12[14] = v30;
                v35 = (__int64)&v12[-a5 + 15];
                v12[13] = BYTE1(v30);
                LOWORD(v30) = _byteswap_ushort(*(_WORD *)(v35 + 1));
                v12[15] = *(_BYTE *)v35;
                v12[17] = v30;
                v12[16] = BYTE1(v30);
                v36 = v12 + 18;
                v37 = (__int64)&v12[-a5 + 18];
                v12 += 24;
                LOWORD(v31) = _byteswap_ushort(*(_WORD *)(v37 + 1));
                *v36 = *(_BYTE *)v37;
                v36[2] = v31;
                v38 = (__int64)&v36[-a5 + 3];
                v36[1] = BYTE1(v31);
                LOWORD(v31) = _byteswap_ushort(*(_WORD *)(v38 + 1));
                v36[3] = *(_BYTE *)v38;
                v36[5] = v31;
                v36[4] = BYTE1(v31);
                break;
              case 250:
                if ( v157 )
                {
                  if ( !(unsigned int)CheckWriteNBytes(v12, v6, 0x18u, L"Decompress write off end of buffer") )
                    return (unsigned int)-1626586443;
                  v12[2] = v11;
                  *v12 = BYTE2(v11);
                  LOBYTE(v27) = 0;
                  v12[1] = BYTE1(v11);
                  *((_WORD *)v12 + 2) = 0;
                  v12[3] = 0;
                  v12[6] = BYTE2(v11);
                  v12[8] = v11;
                  v12[7] = BYTE1(v11);
                  *((_WORD *)v12 + 5) = 0;
                  v12[9] = 0;
                  *(_WORD *)(v12 + 13) = 0;
                  v12[12] = 0;
                  *((_WORD *)v12 + 8) = 0;
                  v12[15] = 0;
                  v24 = v12 + 18;
                  *(_WORD *)(v24 + 1) = 0;
                  v25 = v24 + 3;
                  *v24 = 0;
                  LOBYTE(v28) = 0;
                  v24[3] = 0;
                }
                else
                {
                  v16 = &v12[-a5];
                  if ( !(unsigned int)CheckReadNBytes2Ended(v16, a2, v6, 3u, L"Decompress reads off end of buffer") )
                    return (unsigned int)-1626586451;
                  if ( !(unsigned int)CheckWriteNBytes(v12, v6, 0x18u, L"Decompress write off end of buffer") )
                    return (unsigned int)-1626586447;
                  v17 = v11 ^ ((*v16 << 16) | v16[2] | (v16[1] << 8));
                  v12[2] = v11 ^ v16[2];
                  v12[1] = BYTE1(v17);
                  *v12 = BYTE2(v17);
                  v18 = (__int64)&v12[-a5 + 3];
                  v19 = _byteswap_ushort(*(_WORD *)(v18 + 1));
                  v12[3] = *(_BYTE *)v18;
                  v12[5] = v19;
                  v12[4] = HIBYTE(v19);
                  v20 = v11 ^ ((v12[-a5 + 6] << 16) | v12[-a5 + 8] | (v12[-a5 + 7] << 8));
                  v12[8] = v11 ^ v12[-a5 + 8];
                  v12[7] = BYTE1(v20);
                  v21 = (__int64)&v12[-a5 + 9];
                  v12[6] = BYTE2(v20);
                  LOWORD(v18) = _byteswap_ushort(*(_WORD *)(v21 + 1));
                  v12[9] = *(_BYTE *)v21;
                  v12[11] = v18;
                  v22 = (__int64)&v12[-a5 + 12];
                  v12[10] = BYTE1(v18);
                  LOWORD(v18) = _byteswap_ushort(*(_WORD *)(v22 + 1));
                  v12[12] = *(_BYTE *)v22;
                  v12[14] = v18;
                  v23 = (__int64)&v12[-a5 + 15];
                  v12[13] = BYTE1(v18);
                  LOWORD(v18) = _byteswap_ushort(*(_WORD *)(v23 + 1));
                  v12[15] = *(_BYTE *)v23;
                  v12[17] = v18;
                  v12[16] = BYTE1(v18);
                  v24 = v12 + 18;
                  LOWORD(v20) = _byteswap_ushort(*(_WORD *)&v24[-a5 + 1]);
                  *v24 = v24[-a5];
                  v24[2] = v20;
                  v24[1] = BYTE1(v20);
                  v25 = v24 + 3;
                  v26 = &v24[-a5 + 3];
                  v27 = v26[2] | (v26[1] << 8);
                  v24[3] = *v26;
                  v28 = v27 >> 8;
                }
                v25[2] = v27;
                v25[1] = v28;
                v12 = v24 + 6;
                break;
              case 253:
                if ( !(unsigned int)CheckWriteNBytes(v12, v6, 3u, L"Decompress write off end of buffer") )
                  return (unsigned int)-1626586479;
                *(_WORD *)(v12 + 1) = -1;
                *v12 = -1;
LABEL_32:
                v12 += 3;
                break;
              case 254:
                if ( !(unsigned int)CheckWriteNBytes(v12, v6, 3u, L"Decompress write off end of buffer") )
                  return (unsigned int)-1626586485;
                *(_WORD *)(v12 + 1) = 0;
                *v12 = 0;
                goto LABEL_32;
            }
            v8 = v157;
LABEL_34:
            ++v9;
            goto LABEL_267;
          }
LABEL_51:
          if ( !(unsigned int)CheckReadNBytes(v9 + 1, v5, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586516;
          v40 = *(unsigned __int16 *)(v9 + 1);
          v41 = v9 + 3;
          goto LABEL_57;
        }
        if ( (_BYTE)v13 == 0xF3 )
          goto LABEL_51;
        if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586510;
        v42 = *v9;
        v41 = v9 + 1;
        v40 = v42 & 0x1F;
        if ( !v40 )
        {
          if ( !(unsigned int)CheckReadOneByte(v41, v5, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586510;
          v40 = *v41++ + 32;
        }
LABEL_57:
        if ( !(unsigned int)CheckReadNBytes(v41, v5, 3u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586506;
        v43 = v41[1];
        v164 = *v41;
        v166 = v41[2];
        if ( !(unsigned int)CheckWriteNBytes(v12, v6, (unsigned int)(3 * v40), L"Decompress write off end of buffer") )
          return (unsigned int)-1626586502;
        v44 = v43;
        v8 = v157;
        v9 = v41 + 3;
        v45 = v166 | (v164 << 16) | (v44 << 8);
        v7 = (int)a2;
        if ( v40 )
        {
          do
          {
            v12[2] = v45;
            v12[1] = BYTE1(v45);
            *v12 = BYTE2(v45);
            v12 += 3;
            --v40;
          }
          while ( v40 );
          goto LABEL_267;
        }
      }
    }
  }
  if ( (_BYTE)v13 == 0xF1 || (_BYTE)v13 == 0xF6 )
  {
LABEL_98:
    if ( !(unsigned int)CheckReadNBytes(v9 + 1, v5, 2u, L"Decompress reads off end of buffer") )
      return (unsigned int)-1626586643;
    v57 = *(unsigned __int16 *)(v9 + 1);
    v9 += 3;
    goto LABEL_100;
  }
  if ( v14 != 32 )
  {
    if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
      return (unsigned int)-1626586631;
    v58 = *v9++;
    v57 = v58 & 0xF;
    if ( v57 )
      goto LABEL_100;
    if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
      return (unsigned int)-1626586631;
    v57 = *v9 + 16;
LABEL_93:
    ++v9;
LABEL_100:
    if ( v15 == -64 || (_BYTE)v13 == 0xF6 )
    {
      if ( !(unsigned int)CheckReadNBytes(v9, v5, 3u, L"Decompress reads off end of buffer") )
        return (unsigned int)-1626586621;
      v11 = v9[2] | (*v9 << 16) | (v9[1] << 8);
      v9 += 3;
    }
    if ( !(unsigned int)CheckWriteNBytes(v12, v159, (unsigned int)(3 * v57), L"Decompress write off end of buffer") )
      return (unsigned int)-1626586611;
    while ( 1 )
    {
      if ( !v57 )
      {
        v6 = v159;
        goto LABEL_3;
      }
      if ( v157 )
      {
        LOBYTE(v60) = v11;
        *v12 = BYTE2(v11);
        v61 = BYTE1(v11);
      }
      else
      {
        v59 = &v12[-a5];
        if ( !(unsigned int)CheckReadNBytes2Ended(v59, a2, v159, 3u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586606;
        v60 = v11 ^ _byteswap_ushort(*(_WORD *)(v59 + 1));
        *v12 = (v11 ^ ((*v59 << 16) | v59[2] | (v59[1] << 8))) >> 16;
        v61 = HIBYTE(v60);
      }
      --v57;
      v12[2] = v60;
      v12[1] = v61;
      v12 += 3;
    }
  }
  if ( !(unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
    return (unsigned int)-1626586635;
  v56 = *v9++;
  v57 = v56 & 0x1F;
  if ( v57 )
    goto LABEL_100;
  if ( (unsigned int)CheckReadOneByte(v9, v5, L"Decompress reads one byte end of buffer") )
  {
    v57 = *v9 + 32;
    goto LABEL_93;
  }
  return (unsigned int)-1626586635;
}

```

## disassembly

```asm
0x18034baf8  mov     [rsp+arg_8], rdx
0x18034bafd  push    rbx
0x18034bafe  push    rbp
0x18034baff  push    rsi
0x18034bb00  push    rdi
0x18034bb01  push    r12
0x18034bb03  push    r13
0x18034bb05  push    r14
0x18034bb07  push    r15
0x18034bb09  sub     rsp, 58h
0x18034bb0d  xor     r11d, r11d
0x18034bb10  mov     r15d, r8d
0x18034bb13  add     r15, rcx
0x18034bb16  mov     r12d, r9d
0x18034bb19  add     r12, rdx
0x18034bb1c  mov     [rsp+98h+var_60], r11d
0x18034bb21  mov     rax, rdx
0x18034bb24  mov     [rsp+98h+var_58], r12
0x18034bb29  lea     r13d, [r11+1]
0x18034bb2d  mov     rdi, rcx
0x18034bb30  mov     [rsp+98h+var_64], r13d
0x18034bb35  mov     esi, r11d
0x18034bb38  mov     ebp, 0FFFFFFh
0x18034bb3d  mov     rbx, rdx
0x18034bb40  jmp     short loc_18034BB52
0x18034bb42  mov     r12, r14
0x18034bb45  mov     rax, [rsp+98h+arg_8]
0x18034bb4d  mov     r13d, [rsp+98h+var_64]
0x18034bb52  cmp     rdi, r15
0x18034bb55  jnb     loc_18034D4FF
0x18034bb5b  test    r13d, r13d
0x18034bb5e  jz      short loc_18034BB7D
0x18034bb60  mov     ecx, ebx
0x18034bb62  sub     ecx, eax
0x18034bb64  movzx   eax, word ptr [rsp+98h+arg_20]
0x18034bb6c  cmp     ecx, eax
0x18034bb6e  jb      short loc_18034BB7D
0x18034bb70  mov     r13d, r11d
0x18034bb73  mov     [rsp+98h+var_64], r11d
0x18034bb78  mov     [rsp+98h+var_60], r11d
0x18034bb7d  lea     r8, aDecompressRead_1; "Decompress reads one byte end of buffer"
0x18034bb84  mov     rdx, r15; unsigned __int8 *
0x18034bb87  mov     rcx, rdi; unsigned __int8 *
0x18034bb8a  call    ?CheckReadOneByte@@YAHPEAE0PEBG@Z; CheckReadOneByte(uchar *,uchar *,ushort const *)
0x18034bb8f  xor     r11d, r11d
0x18034bb92  test    eax, eax
0x18034bb94  jz      loc_18034D4FA
0x18034bb9a  movzx   r14d, byte ptr [rdi]
0x18034bb9e  mov     al, r14b
0x18034bba1  and     al, 0E0h
0x18034bba3  jz      loc_18034D159
0x18034bba9  cmp     r14b, 0F0h
0x18034bbad  jz      loc_18034D12D
0x18034bbb3  mov     r13b, r14b
0x18034bbb6  mov     [rsp+98h+var_60], r11d
0x18034bbbb  and     r13b, 0F0h
0x18034bbbf  mov     [rsp+98h+arg_10], r13b
0x18034bbc7  cmp     al, 40h ; '@'
0x18034bbc9  jz      loc_18034C726
0x18034bbcf  cmp     r13b, 0D0h
0x18034bbd3  jz      loc_18034C726
0x18034bbd9  cmp     r14b, 0F2h
0x18034bbdd  jz      loc_18034C7D3
0x18034bbe3  cmp     r14b, 0F7h
0x18034bbe7  jz      loc_18034C7D3
0x18034bbed  cmp     al, 20h ; ' '
0x18034bbef  jz      loc_18034C555
0x18034bbf5  cmp     r13b, 0C0h
0x18034bbf9  jz      loc_18034C555
0x18034bbff  cmp     r14b, 0F1h
0x18034bc03  jz      loc_18034C5FD
0x18034bc09  cmp     r14b, 0F6h
0x18034bc0d  jz      loc_18034C5FD
0x18034bc13  cmp     r13b, 0E0h
0x18034bc17  jz      loc_18034C3D2
0x18034bc1d  cmp     r14b, 0F8h
0x18034bc21  jz      loc_18034C3D8
0x18034bc27  cmp     al, 80h
0x18034bc29  jz      loc_18034C2E8
0x18034bc2f  cmp     r14b, 0F4h
0x18034bc33  jz      loc_18034C2EE
0x18034bc39  cmp     al, 60h ; '`'
0x18034bc3b  jz      loc_18034C1B9
0x18034bc41  cmp     r14b, 0F3h
0x18034bc45  jz      loc_18034C1BF
0x18034bc4b  mov     ecx, r14d
0x18034bc4e  sub     ecx, 0F9h
0x18034bc54  jz      loc_18034BF3F
0x18034bc5a  sub     ecx, 1
0x18034bc5d  jz      short loc_18034BCD1
0x18034bc5f  sub     ecx, 3
0x18034bc62  jz      short loc_18034BCA3
0x18034bc64  cmp     ecx, 1
0x18034bc67  jnz     short loc_18034BC96
0x18034bc69  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034bc70  mov     rdx, r12; unsigned __int8 *
0x18034bc73  lea     r8d, [r11+3]; unsigned __int64
0x18034bc77  mov     rcx, rbx; unsigned __int8 *
0x18034bc7a  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034bc7f  xor     r11d, r11d
0x18034bc82  test    eax, eax
0x18034bc84  jz      loc_18034D36E
0x18034bc8a  mov     [rbx+1], r11w
0x18034bc8f  mov     [rbx], r11b
0x18034bc92  add     rbx, 3
0x18034bc96  mov     r13d, [rsp+98h+var_64]
0x18034bc9b  inc     rdi
0x18034bc9e  jmp     loc_18034D361
0x18034bca3  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034bcaa  mov     r8d, 3; unsigned __int64
0x18034bcb0  mov     rdx, r12; unsigned __int8 *
0x18034bcb3  mov     rcx, rbx; unsigned __int8 *
0x18034bcb6  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034bcbb  xor     r11d, r11d
0x18034bcbe  test    eax, eax
0x18034bcc0  jz      loc_18034D378
0x18034bcc6  mov     word ptr [rbx+1], 0FFFFh
0x18034bccc  mov     byte ptr [rbx], 0FFh
0x18034bccf  jmp     short loc_18034BC92
0x18034bcd1  cmp     [rsp+98h+var_64], r11d
0x18034bcd6  jnz     loc_18034BEA3
0x18034bcdc  movzx   r13d, word ptr [rsp+98h+arg_20]
0x18034bce5  lea     rax, aDecompressRead; "Decompress reads off end of buffer"
0x18034bcec  mov     rdx, [rsp+98h+arg_8]; unsigned __int8 *
0x18034bcf4  mov     r14, rbx
0x18034bcf7  sub     r14, r13
0x18034bcfa  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x18034bcff  mov     rcx, r14; unsigned __int8 *
0x18034bd02  mov     r9d, 3; unsigned __int64
0x18034bd08  mov     r8, r12; unsigned __int8 *
0x18034bd0b  call    ?CheckReadNBytes2Ended@@YAHPEAE00_KPEBG@Z; CheckReadNBytes2Ended(uchar *,uchar *,uchar *,unsigned __int64,ushort const *)
0x18034bd10  test    eax, eax
0x18034bd12  jz      loc_18034D38C
0x18034bd18  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034bd1f  mov     r8d, 18h; unsigned __int64
0x18034bd25  mov     rdx, r12; unsigned __int8 *
0x18034bd28  mov     rcx, rbx; unsigned __int8 *
0x18034bd2b  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034bd30  xor     r11d, r11d
0x18034bd33  test    eax, eax
0x18034bd35  jz      loc_18034D382
0x18034bd3b  movzx   eax, byte ptr [r14+2]
0x18034bd40  movzx   ecx, byte ptr [r14+1]
0x18034bd45  shl     ecx, 8
0x18034bd48  or      ecx, eax
0x18034bd4a  movzx   eax, byte ptr [r14]
0x18034bd4e  shl     eax, 10h
0x18034bd51  or      ecx, eax
0x18034bd53  xor     ecx, ebp
0x18034bd55  mov     [rbx+2], cl
0x18034bd58  mov     eax, ecx
0x18034bd5a  shr     eax, 8
0x18034bd5d  mov     [rbx+1], al
0x18034bd60  shr     ecx, 10h
0x18034bd63  mov     [rbx], cl
0x18034bd65  lea     rcx, [rbx+3]
0x18034bd69  sub     rcx, r13
0x18034bd6c  movzx   r8d, byte ptr [rcx]
0x18034bd70  movzx   edx, byte ptr [rcx+1]
0x18034bd74  mov     eax, r8d
0x18034bd77  shl     eax, 10h
0x18034bd7a  shl     edx, 8
0x18034bd7d  or      edx, eax
0x18034bd7f  movzx   eax, byte ptr [rcx+2]
0x18034bd83  or      edx, eax
0x18034bd85  mov     [rbx+3], r8b
0x18034bd89  mov     [rbx+5], dl
0x18034bd8c  lea     rcx, [rbx+6]
0x18034bd90  sub     rcx, r13
0x18034bd93  shr     edx, 8
0x18034bd96  mov     [rbx+4], dl
0x18034bd99  movzx   eax, byte ptr [rcx+2]
0x18034bd9d  movzx   edx, byte ptr [rcx+1]
0x18034bda1  shl     edx, 8
0x18034bda4  or      edx, eax
0x18034bda6  movzx   eax, byte ptr [rcx]
0x18034bda9  shl     eax, 10h
0x18034bdac  or      edx, eax
0x18034bdae  xor     edx, ebp
0x18034bdb0  mov     [rbx+8], dl
0x18034bdb3  mov     eax, edx
0x18034bdb5  shr     eax, 8
0x18034bdb8  mov     [rbx+7], al
0x18034bdbb  lea     rax, [rbx+9]
0x18034bdbf  sub     rax, r13
0x18034bdc2  shr     edx, 10h
0x18034bdc5  mov     [rbx+6], dl
0x18034bdc8  movzx   ecx, byte ptr [rax+1]
0x18034bdcc  movzx   edx, byte ptr [rax]
0x18034bdcf  movzx   eax, byte ptr [rax+2]
0x18034bdd3  shl     ecx, 8
0x18034bdd6  or      ecx, eax
0x18034bdd8  mov     [rbx+9], dl
0x18034bddb  mov     eax, edx
0x18034bddd  shl     eax, 10h
0x18034bde0  or      ecx, eax
0x18034bde2  lea     rax, [rbx+0Ch]
0x18034bde6  mov     [rbx+0Bh], cl
0x18034bde9  sub     rax, r13
0x18034bdec  shr     ecx, 8
0x18034bdef  mov     [rbx+0Ah], cl
0x18034bdf2  movzx   ecx, byte ptr [rax+1]
0x18034bdf6  movzx   edx, byte ptr [rax]
0x18034bdf9  movzx   eax, byte ptr [rax+2]
0x18034bdfd  shl     ecx, 8
0x18034be00  or      ecx, eax
0x18034be02  mov     [rbx+0Ch], dl
0x18034be05  mov     eax, edx
0x18034be07  shl     eax, 10h
0x18034be0a  or      ecx, eax
0x18034be0c  lea     rax, [rbx+0Fh]
0x18034be10  mov     [rbx+0Eh], cl
0x18034be13  sub     rax, r13
0x18034be16  shr     ecx, 8
0x18034be19  mov     [rbx+0Dh], cl
0x18034be1c  movzx   ecx, byte ptr [rax+1]
0x18034be20  movzx   edx, byte ptr [rax]
0x18034be23  movzx   eax, byte ptr [rax+2]
0x18034be27  shl     ecx, 8
0x18034be2a  or      ecx, eax
0x18034be2c  mov     eax, edx
0x18034be2e  shl     eax, 10h
0x18034be31  mov     [rbx+0Fh], dl
0x18034be34  or      ecx, eax
0x18034be36  mov     [rbx+11h], cl
0x18034be39  shr     ecx, 8
0x18034be3c  mov     [rbx+10h], cl
0x18034be3f  add     rbx, 12h
0x18034be43  mov     rcx, rbx
0x18034be46  sub     rcx, r13
0x18034be49  movzx   r8d, byte ptr [rcx]
0x18034be4d  movzx   edx, byte ptr [rcx+1]
0x18034be51  mov     eax, r8d
0x18034be54  shl     eax, 10h
0x18034be57  shl     edx, 8
0x18034be5a  or      edx, eax
0x18034be5c  movzx   eax, byte ptr [rcx+2]
0x18034be60  or      edx, eax
0x18034be62  mov     [rbx], r8b
0x18034be65  mov     [rbx+2], dl
0x18034be68  shr     edx, 8
0x18034be6b  mov     [rbx+1], dl
0x18034be6e  lea     rdx, [rbx+3]
0x18034be72  mov     rcx, rdx
0x18034be75  sub     rcx, r13
0x18034be78  movzx   eax, byte ptr [rcx+2]
0x18034be7c  movzx   r8d, byte ptr [rcx+1]
0x18034be81  shl     r8d, 8
0x18034be85  or      r8d, eax
0x18034be88  mov     al, [rcx]
0x18034be8a  mov     [rdx], al
0x18034be8c  lea     rax, [rbx+6]
0x18034be90  mov     [rsp+98h+arg_0], rax
0x18034be98  mov     eax, r8d
0x18034be9b  shr     eax, 8
0x18034be9e  jmp     loc_18034BF2C
0x18034bea3  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034beaa  mov     r8d, 18h; unsigned __int64
0x18034beb0  mov     rdx, r12; unsigned __int8 *
0x18034beb3  mov     rcx, rbx; unsigned __int8 *
0x18034beb6  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034bebb  xor     r11d, r11d
0x18034bebe  test    eax, eax
0x18034bec0  jz      loc_18034D396
0x18034bec6  mov     [rbx+2], bpl
0x18034beca  mov     eax, ebp
0x18034becc  shr     eax, 10h
0x18034becf  mov     ecx, ebp
0x18034bed1  mov     [rbx], al
0x18034bed3  mov     r8b, r11b
0x18034bed6  shr     ecx, 8
0x18034bed9  mov     [rbx+1], cl
0x18034bedc  mov     [rbx+4], r11w
0x18034bee1  mov     [rbx+3], r11b
0x18034bee5  mov     [rbx+6], al
0x18034bee8  mov     [rbx+8], bpl
0x18034beec  mov     [rbx+7], cl
0x18034beef  mov     [rbx+0Ah], r11w
0x18034bef4  mov     [rbx+9], r11b
0x18034bef8  mov     [rbx+0Dh], r11w
0x18034befd  mov     [rbx+0Ch], r11b
0x18034bf01  mov     [rbx+10h], r11w
0x18034bf06  mov     [rbx+0Fh], r11b
0x18034bf0a  add     rbx, 12h
0x18034bf0e  lea     rax, [rbx+6]
0x18034bf12  mov     [rbx+1], r11w
0x18034bf17  lea     rdx, [rbx+3]
0x18034bf1b  mov     [rsp+98h+arg_0], rax
0x18034bf23  mov     [rbx], r11b
0x18034bf26  mov     al, r11b
0x18034bf29  mov     [rdx], r11b
0x18034bf2c  mov     [rdx+2], r8b
0x18034bf30  mov     rcx, rdx
0x18034bf33  mov     [rdx+1], al
0x18034bf36  add     rbx, 6
0x18034bf3a  jmp     loc_18034BC96
0x18034bf3f  mov     r13d, [rsp+98h+var_64]
0x18034bf44  test    r13d, r13d
0x18034bf47  jnz     loc_18034C12F
0x18034bf4d  movzx   r13d, word ptr [rsp+98h+arg_20]
  ... truncated ...
```
