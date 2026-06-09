# Planar::BDDecompressBitmap32(uchar *,uchar *,uint,uint,ushort)

- ea: `0x18034d518`
- end: `0x18034f2e6`
- name: `?BDDecompressBitmap32@Planar@@YAJPEAE0IIG@Z`
- size: `7630`
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
- `0x18034d518`

## string_xrefs

- `0x18034d592`: `Decompress reads one byte end of buffer`
- `0x18034dcec`: `Decompress reads one byte end of buffer`
- `0x18034dd13`: `Decompress reads one byte end of buffer`
- `0x18034de3d`: `Decompress reads one byte end of buffer`
- `0x18034de62`: `Decompress reads one byte end of buffer`
- `0x18034df29`: `Decompress reads one byte end of buffer`
- `0x18034df50`: `Decompress reads one byte end of buffer`
- `0x18034e0c3`: `Decompress reads one byte end of buffer`
- `0x18034e0f2`: `Decompress reads one byte end of buffer`
- `0x18034e133`: `Decompress reads one byte end of buffer`
- `0x18034e2ad`: `Decompress reads one byte end of buffer`
- `0x18034e2d4`: `Decompress reads one byte end of buffer`
- `0x18034e314`: `Decompress reads one byte end of buffer`
- `0x18034e3c0`: `Decompress reads one byte end of buffer`
- `0x18034e8c5`: `Decompress reads one byte end of buffer`
- `0x18034eef9`: `Decompress reads one byte end of buffer`
- `0x18034ef20`: `Decompress reads one byte end of buffer`
- `0x18034d687`: `Decompress write off end of buffer`
- `0x18034d6aa`: `Decompress write off end of buffer`
- `0x18034d717`: `Decompress write off end of buffer`
- `0x18034d929`: `Decompress write off end of buffer`
- `0x18034da0b`: `Decompress write off end of buffer`
- `0x18034dc43`: `Decompress write off end of buffer`
- `0x18034dd67`: `Decompress write off end of buffer`
- `0x18034dead`: `Decompress write off end of buffer`
- `0x18034dfa4`: `Decompress write off end of buffer`
- `0x18034e1de`: `Decompress write off end of buffer`
- `0x18034e42b`: `Decompress write off end of buffer`
- `0x18034e6c6`: `Decompress write off end of buffer`
- `0x18034e939`: `Decompress write off end of buffer`
- `0x18034ec67`: `Decompress write off end of buffer`
- `0x18034ef59`: `Decompress write off end of buffer`
- `0x18034f005`: `Decompress write off end of buffer`
- `0x18034f0ad`: `Decompress write off end of buffer`
- `0x18034f0fa`: `Decompress write off end of buffer`
- `0x18034d6e4`: `Decompress reads off end of buffer`
- `0x18034d9d8`: `Decompress reads off end of buffer`
- `0x18034dcc0`: `Decompress reads off end of buffer`
- `0x18034dd38`: `Decompress reads off end of buffer`
- `0x18034de12`: `Decompress reads off end of buffer`
- `0x18034de93`: `Decompress reads off end of buffer`
- `0x18034defd`: `Decompress reads off end of buffer`
- `0x18034df75`: `Decompress reads off end of buffer`
- `0x18034e157`: `Decompress reads off end of buffer`
- `0x18034e191`: `Decompress reads off end of buffer`
- `0x18034e21b`: `Decompress reads off end of buffer`
- `0x18034e33a`: `Decompress reads off end of buffer`
- `0x18034e374`: `Decompress reads off end of buffer`
- `0x18034e3fe`: `Decompress reads off end of buffer`
- `0x18034e906`: `Decompress reads off end of buffer`
- `0x18034eecd`: `Decompress reads off end of buffer`
- `0x18034ef8e`: `Decompress reads off end of buffer`
- `0x18034f03b`: `Decompress reads off end of buffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall Planar::BDDecompressBitmap32(
        Planar *this,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        int a4,
        unsigned __int16 a5)
{
  unsigned int v5; // esi
  unsigned int v6; // ebp
  unsigned __int8 *v7; // r14
  int v8; // eax
  int v9; // r12d
  unsigned __int8 *v10; // rdi
  unsigned __int8 *v11; // rbx
  unsigned __int8 *v12; // r13
  int v13; // r15d
  char v14; // al
  char v15; // cl
  unsigned __int8 *v16; // r15
  int v17; // ecx
  __int64 v18; // rcx
  unsigned __int8 v19; // r9
  unsigned __int16 v20; // dx
  int v21; // edx
  __int64 v22; // rcx
  unsigned __int8 v23; // r9
  __int16 v24; // ax
  __int64 v25; // rcx
  unsigned __int8 v26; // r9
  __int16 v27; // ax
  __int64 v28; // rcx
  unsigned __int8 v29; // r9
  unsigned __int8 *v30; // rbx
  _BYTE *v31; // rdx
  unsigned __int8 *v32; // rcx
  unsigned __int8 v33; // r9
  unsigned int v34; // r8d
  unsigned int v35; // eax
  unsigned __int8 *v36; // r15
  int v37; // ecx
  int v38; // edx
  __int64 v39; // rcx
  unsigned __int8 v40; // r9
  __int16 v41; // ax
  __int64 v42; // rcx
  unsigned __int8 v43; // r9
  __int64 v44; // rcx
  unsigned __int8 v45; // r9
  __int16 v46; // ax
  __int64 v47; // rcx
  unsigned __int8 v48; // r9
  unsigned __int8 *v49; // r11
  __int64 v50; // rcx
  unsigned __int8 v51; // r9
  unsigned __int8 *v52; // rcx
  _QWORD *v53; // rax
  int v54; // r15d
  unsigned __int8 *v55; // rdi
  unsigned __int8 v56; // r15
  int v57; // r12d
  int v58; // ecx
  int v59; // ecx
  int v60; // eax
  char v61; // al
  int v62; // r15d
  unsigned int v63; // r12d
  int v64; // r15d
  unsigned __int8 *v65; // rdi
  unsigned __int8 v66; // r15
  int v67; // r12d
  int v68; // ecx
  int v69; // ecx
  int v70; // edx
  char v71; // r12
  int v72; // r12d
  char v73; // r12
  unsigned __int8 *v74; // r15
  int v75; // ecx
  __int16 v76; // dx
  unsigned __int8 v77; // eax^2
  char v78; // r12
  int v79; // r12d
  unsigned int v80; // r12d
  char v81; // r12
  char v82; // r15
  int v83; // ecx
  _BYTE *v84; // r10
  _BYTE *v85; // rbx
  int v86; // edx
  int v87; // edx
  int v88; // edx
  int v89; // edx
  _BYTE *v90; // r8
  int v91; // edx
  _BYTE *v92; // rbx
  int v93; // edx
  _BYTE *v94; // r8
  unsigned int v95; // edx
  unsigned int v96; // r9d
  unsigned int v97; // ecx
  unsigned __int8 v98; // al
  unsigned __int8 v99; // r8
  unsigned __int8 v100; // r10
  unsigned __int8 *v101; // rax
  unsigned __int8 v102; // r11
  __int16 v103; // kr00_2
  unsigned __int8 v104; // r8
  unsigned __int8 v105; // r10
  unsigned __int8 v106; // r11
  unsigned __int8 v107; // r8
  unsigned __int8 v108; // r10
  unsigned __int8 v109; // r11
  unsigned __int8 v110; // r8
  unsigned __int8 v111; // r10
  unsigned __int8 v112; // r11
  unsigned __int8 v113; // r8
  unsigned __int8 v114; // r10
  unsigned __int8 v115; // r11
  char v116; // al
  char v117; // r8
  char v118; // r10
  char v119; // r10
  char v120; // r15
  int v121; // r8d
  unsigned __int8 *v122; // r8
  int v123; // ecx
  unsigned int v124; // r12d
  _BYTE *v125; // r10
  unsigned __int8 *v126; // r8
  int v127; // edx
  unsigned int v128; // r10d
  int v129; // edx
  unsigned int v130; // r10d
  int v131; // edx
  unsigned int v132; // r10d
  int v133; // edx
  unsigned int v134; // r10d
  int v135; // edx
  unsigned int v136; // r10d
  int v137; // edx
  int v138; // edx
  int v139; // r8d
  unsigned int v140; // ecx
  unsigned int v141; // edx
  unsigned __int8 *v142; // r11
  unsigned __int8 v143; // al
  unsigned __int8 v144; // r9
  unsigned __int8 v145; // r10
  unsigned int v146; // eax
  bool v147; // zf
  _BYTE *v148; // rax
  unsigned __int8 *v149; // r9
  char v150; // r10
  char v151; // r11
  char v152; // r12
  unsigned __int8 v153; // al
  unsigned __int8 v154; // r10
  unsigned __int8 v155; // r11
  unsigned __int8 v156; // al
  unsigned __int8 v157; // r10
  unsigned __int8 v158; // r11
  unsigned __int8 v159; // al
  unsigned __int8 v160; // r10
  unsigned __int8 v161; // r11
  unsigned __int8 v162; // al
  unsigned __int8 v163; // r10
  unsigned __int8 v164; // r11
  unsigned __int8 v165; // al
  unsigned __int8 v166; // r10
  unsigned __int8 v167; // r11
  unsigned __int8 v168; // al
  int v169; // r15d
  char v170; // r15
  unsigned __int8 *v171; // r12
  int v172; // ecx
  unsigned __int8 *v173; // r12
  unsigned __int16 v174; // cx
  unsigned __int8 v176; // [rsp+30h] [rbp-58h]
  unsigned __int8 v177; // [rsp+31h] [rbp-57h]
  unsigned __int8 v178; // [rsp+32h] [rbp-56h]
  unsigned __int8 v179; // [rsp+33h] [rbp-55h]
  int v180; // [rsp+34h] [rbp-54h]
  int v181; // [rsp+38h] [rbp-50h]
  unsigned __int8 v182; // [rsp+90h] [rbp+8h]
  unsigned __int8 v183; // [rsp+90h] [rbp+8h]
  char v185; // [rsp+A0h] [rbp+18h]
  unsigned __int8 v186; // [rsp+A0h] [rbp+18h]
  unsigned __int8 v187; // [rsp+A0h] [rbp+18h]
  unsigned __int8 v188; // [rsp+A0h] [rbp+18h]
  unsigned __int8 v189; // [rsp+A0h] [rbp+18h]
  unsigned __int8 v190; // [rsp+A8h] [rbp+20h]
  unsigned __int8 v191; // [rsp+A8h] [rbp+20h]
  unsigned int v192; // [rsp+A8h] [rbp+20h]

  v5 = 0;
  v6 = -1;
  v7 = (unsigned __int8 *)this + (unsigned int)a3;
  v8 = (int)a2;
  v181 = 0;
  v9 = 1;
  v10 = (unsigned __int8 *)this;
  v180 = 1;
  v11 = a2;
  v12 = &a2[a4];
  while ( v10 < v7 )
  {
    if ( v9 && (int)v11 - v8 >= (unsigned int)a5 )
    {
      v9 = 0;
      v180 = 0;
      v181 = 0;
    }
    if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
      return (unsigned int)-1626586815;
    v13 = *v10;
    v14 = *v10 & 0xE0;
    if ( !v14 )
    {
      if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
        return (unsigned int)-1626586802;
      v170 = *v10++;
      v169 = v170 & 0x1F;
      if ( !v169 )
      {
        if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586802;
        v169 = *v10++ + 32;
      }
      goto LABEL_248;
    }
    if ( (_BYTE)v13 == 0xF0 )
    {
      if ( !(unsigned int)CheckReadNBytes(v10 + 1, v7, 2u, L"Decompress reads off end of buffer") )
        return (unsigned int)-1626586798;
      v169 = *(unsigned __int16 *)(v10 + 1);
      v10 += 3;
LABEL_248:
      if ( !v9 )
      {
        if ( v181 )
        {
          if ( !(unsigned int)CheckWriteNBytes(v11, v12, 4u, L"Decompress write off end of buffer") )
            return (unsigned int)-1626586788;
          v171 = &v11[-a5];
          if ( !(unsigned int)CheckReadNBytes2Ended(v171, a2, v12, 4u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586787;
          v172 = v6 ^ (v171[3] | (v171[2] << 8) | ((v171[1] | (*v171 << 8)) << 16));
          v11[3] = v6 ^ v171[3];
          v11[2] = BYTE1(v172);
          v11[1] = BYTE2(v172);
          *v11 = HIBYTE(v172);
          v11 += 4;
          --v169;
        }
        if ( (unsigned int)CheckWriteNBytes(v11, v12, (unsigned int)(4 * v169), L"Decompress write off end of buffer") )
        {
          while ( 1 )
          {
            if ( !v169 )
            {
              v9 = v180;
              goto LABEL_265;
            }
            v173 = &v11[-a5];
            if ( !(unsigned int)CheckReadNBytes2Ended(v173, a2, v12, 4u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586775;
            --v169;
            v174 = _byteswap_ushort(*((_WORD *)v173 + 1));
            *(_WORD *)v11 = *(_WORD *)v173;
            v11[3] = v174;
            v11[2] = HIBYTE(v174);
            v11 += 4;
          }
        }
        else
        {
          return (unsigned int)-1626586779;
        }
      }
      if ( v181 )
      {
        if ( !(unsigned int)CheckWriteNBytes(v11, v12, 4u, L"Decompress write off end of buffer") )
          return (unsigned int)-1626586766;
        v11[3] = v6;
        v11[2] = BYTE1(v6);
        v11[1] = BYTE2(v6);
        *v11 = HIBYTE(v6);
        v11 += 4;
        --v169;
      }
      if ( !(unsigned int)CheckWriteNBytes(v11, v12, (unsigned int)(4 * v169), L"Decompress write off end of buffer") )
        return (unsigned int)-1626586761;
      for ( ; v169; --v169 )
      {
        *(_DWORD *)v11 = 0;
        v11 += 4;
      }
LABEL_265:
      v181 = 1;
LABEL_266:
      v8 = (int)a2;
    }
    else
    {
      v181 = 0;
      v15 = v13 & 0xF0;
      v185 = v13 & 0xF0;
      if ( v14 == 64 || v15 == -48 )
      {
        if ( (_BYTE)v13 == 0xF2 || (_BYTE)v13 == 0xF7 )
        {
LABEL_121:
          if ( !(unsigned int)CheckReadNBytes(v10 + 1, v7, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586727;
          v80 = *(unsigned __int16 *)(v10 + 1);
          v10 += 3;
          goto LABEL_123;
        }
        if ( v14 == 64 )
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586719;
          v78 = *v10++;
          v79 = v78 & 0x1F;
          if ( v79 )
            goto LABEL_116;
          if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586719;
        }
        else
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586715;
          v81 = *v10++;
          v79 = v81 & 0xF;
          if ( v79 )
          {
LABEL_116:
            v80 = 8 * v79;
            goto LABEL_123;
          }
          if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586715;
        }
        v80 = *v10++ + 1;
LABEL_123:
        if ( v185 == -48 || (_BYTE)v13 == 0xF7 )
        {
          if ( (unsigned int)CheckReadNBytes(v10, v7, 4u, L"Decompress reads off end of buffer") )
          {
            v6 = v10[3] | (v10[2] << 8) | ((v10[1] | (*v10 << 8)) << 16);
            v10 += 4;
            goto LABEL_127;
          }
          return (unsigned int)-1626586708;
        }
LABEL_127:
        while ( v80 > 8 )
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586691;
          v82 = *v10;
          if ( v180 )
          {
            if ( !(unsigned int)CheckWriteNBytes(v11, v12, 0x20u, L"Decompress write off end of buffer") )
              return (unsigned int)-1626586679;
            v97 = v6 >> 8;
            v95 = HIWORD(v6);
            if ( (v82 & 1) != 0 )
            {
              *v11 = HIBYTE(v6);
              v98 = BYTE2(v6);
              v99 = BYTE1(v6);
              v100 = v6;
            }
            else
            {
              v98 = 0;
              *v11 = 0;
              v99 = 0;
              v100 = 0;
            }
            v11[3] = v100;
            v11[2] = v99;
            v11[1] = v98;
            v101 = v11 + 4;
            if ( (v82 & 2) != 0 )
            {
              v102 = BYTE2(v6);
              v103 = v6;
              v188 = HIBYTE(v6);
            }
            else
            {
              v102 = 0;
              v188 = 0;
              v103 = 0;
            }
            v11[4] = v188;
            v11[7] = v103;
            v11[6] = HIBYTE(v103);
            v11[5] = v102;
            if ( (v82 & 4) != 0 )
            {
              v11[8] = HIBYTE(v6);
              v104 = BYTE2(v6);
              v105 = BYTE1(v6);
              v106 = v6;
            }
            else
            {
              v104 = 0;
              v11[8] = 0;
              v105 = 0;
              v106 = 0;
            }
            v11[11] = v106;
            v11[10] = v105;
            v11[9] = v104;
            if ( (v82 & 8) != 0 )
            {
              v11[12] = HIBYTE(v6);
              v107 = BYTE2(v6);
              v108 = BYTE1(v6);
              v109 = v6;
            }
            else
            {
              v107 = 0;
              v11[12] = 0;
              v108 = 0;
              v109 = 0;
            }
            v11[15] = v109;
            v11[14] = v108;
            v11[13] = v107;
            if ( (v82 & 0x10) != 0 )
            {
              v11[16] = HIBYTE(v6);
              v110 = BYTE2(v6);
              v111 = BYTE1(v6);
              v112 = v6;
            }
            else
            {
              v110 = 0;
              v11[16] = 0;
              v111 = 0;
              v112 = 0;
            }
            v11[19] = v112;
            v11[18] = v111;
            v11[17] = v110;
            if ( (v82 & 0x20) != 0 )
            {
              v11[20] = HIBYTE(v6);
              v113 = BYTE2(v6);
              v114 = BYTE1(v6);
              v115 = v6;
            }
            else
            {
              v113 = 0;
              v11[20] = 0;
              v114 = 0;
              v115 = 0;
            }
            v11[23] = v115;
            v92 = v11 + 24;
            v101[18] = v114;
            v101[17] = v113;
            if ( (v82 & 0x40) != 0 )
            {
              *v92 = HIBYTE(v6);
              v116 = BYTE2(v6);
              v117 = BYTE1(v6);
              v118 = v6;
            }
            else
            {
              v116 = 0;
              *v92 = 0;
              v117 = 0;
              v118 = 0;
            }
            v92[3] = v118;
            v92[2] = v117;
            v94 = v92 + 4;
            v92[1] = v116;
            if ( v82 >= 0 )
            {
              LOBYTE(v95) = 0;
              *v94 = 0;
              LOBYTE(v97) = 0;
              v119 = 0;
            }
            else
            {
              *v94 = HIBYTE(v6);
              v119 = v6;
            }
            v5 = 0;
            LOBYTE(v96) = v95;
            LOBYTE(v95) = v119;
          }
          else
          {
            if ( !(unsigned int)CheckReadNBytes2Ended(&v11[-a5], a2, v12, 4u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586687;
            if ( !(unsigned int)CheckWriteNBytes(v11, v12, 0x20u, L"Decompress write off end of buffer") )
              return (unsigned int)-1626586683;
            v83 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | ((v11[-a5 + 1] | (v11[-a5] << 8)) << 16);
            if ( (v82 & 1) != 0 )
              v83 ^= v6;
            *v11 = HIBYTE(v83);
            v84 = v11 + 4;
            v11[3] = v83;
            v11[2] = BYTE1(v83);
            v11[1] = BYTE2(v83);
            v85 = v11 + 4;
            v86 = (unsigned __int8)v85[-a5 + 3]
                | ((unsigned __int8)v85[-a5 + 2] << 8)
                | (((unsigned __int8)v85[-a5 + 1] | ((unsigned __int8)v85[-a5] << 8)) << 16);
            if ( (v82 & 2) != 0 )
              v86 ^= v6;
            *v85 = HIBYTE(v86);
            v84[3] = v86;
            v84[2] = BYTE1(v86);
            v84[1] = BYTE2(v86);
            v87 = (unsigned __int8)v85[-a5 + 7]
                | ((unsigned __int8)v85[-a5 + 6] << 8)
                | ((((unsigned __int8)v85[-a5 + 4] << 8) | (unsigned __int8)v85[-a5 + 5]) << 16);
            if ( (v82 & 4) != 0 )
              v87 ^= v6;
            v85[4] = HIBYTE(v87);
            v85[7] = v87;
            v85[6] = BYTE1(v87);
            v85[5] = BYTE2(v87);
            v88 = (unsigned __int8)v85[-a5 + 11]
                | ((unsigned __int8)v85[-a5 + 10] << 8)
                | (((unsigned __int8)v85[-a5 + 9] | ((unsigned __int8)v85[-a5 + 8] << 8)) << 16);
            if ( (v82 & 8) != 0 )
              v88 ^= v6;
            v85[8] = HIBYTE(v88);
            v85[11] = v88;
            v85[10] = BYTE1(v88);
            v85[9] = BYTE2(v88);
            v89 = (unsigned __int8)v85[-a5 + 15]
                | ((unsigned __int8)v85[-a5 + 14] << 8)
                | ((((unsigned __int8)v85[-a5 + 12] << 8) | (unsigned __int8)v85[-a5 + 13]) << 16);
            if ( (v82 & 0x10) != 0 )
              v89 ^= v6;
            v85[12] = HIBYTE(v89);
            v85[15] = v89;
            v85[14] = BYTE1(v89);
            v85[13] = BYTE2(v89);
            v90 = v85 + 16;
            v91 = (unsigned __int8)v85[-a5 + 19]
                | ((unsigned __int8)v85[-a5 + 18] << 8)
                | (((unsigned __int8)v85[-a5 + 17] | ((unsigned __int8)v85[-a5 + 16] << 8)) << 16);
            if ( (v82 & 0x20) != 0 )
              v91 ^= v6;
            v92 = v85 + 20;
            *v90 = HIBYTE(v91);
            v90[3] = v91;
            v90[2] = BYTE1(v91);
            v90[1] = BYTE2(v91);
            v93 = (unsigned __int8)v92[-a5 + 3]
                | ((unsigned __int8)v92[-a5 + 2] << 8)
                | (((unsigned __int8)v92[-a5 + 1] | ((unsigned __int8)v92[-a5] << 8)) << 16);
            if ( (v82 & 0x40) != 0 )
              v93 ^= v6;
            v94 = v92 + 4;
            *v92 = HIBYTE(v93);
            v92[3] = v93;
            v92[2] = BYTE1(v93);
            v92[1] = BYTE2(v93);
            v95 = (unsigned __int8)v92[-a5 + 7]
                | ((unsigned __int8)v92[-a5 + 6] << 8)
                | ((((unsigned __int8)v92[-a5 + 4] << 8) | (unsigned __int8)v92[-a5 + 5]) << 16);
            if ( v82 < 0 )
              v95 ^= v6;
            v96 = HIWORD(v95);
            v97 = v95 >> 8;
            *v94 = HIBYTE(v95);
          }
          v94[3] = v95;
          ++v10;
          v80 -= 8;
          v11 = v92 + 8;
          v94[2] = v97;
          v94[1] = v96;
        }
        if ( !v80 )
          goto LABEL_2;
        if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586673;
        v120 = *v10++;
        if ( v180 )
        {
          v139 = 8;
          if ( v80 < 8 )
            v139 = v80;
          if ( !(unsigned int)CheckWriteNBytes(
                                v11,
                                v12,
                                (unsigned int)(4 * v139),
                                L"Decompress write off end of buffer") )
            return (unsigned int)-1626586661;
          v140 = v6 >> 8;
          v141 = HIWORD(v6);
          v142 = v11;
          if ( (v120 & 1) != 0 )
          {
            *v11 = HIBYTE(v6);
            v143 = BYTE2(v6);
            v144 = BYTE1(v6);
            v145 = v6;
          }
          else
          {
            v143 = 0;
            *v11 = 0;
            v144 = 0;
            v145 = 0;
          }
          v11[3] = v145;
          v11[2] = v144;
          v11[1] = v143;
          v146 = v80 - 1;
          v9 = v180;
          v11 += 4;
          v192 = v146;
          v147 = v146 == 0;
          v8 = (int)a2;
          if ( !v147 )
          {
            v148 = v142 + 4;
            v149 = v142 + 4;
            if ( (v120 & 2) != 0 )
            {
              v150 = BYTE2(v6);
              v189 = HIBYTE(v6);
              v151 = BYTE1(v6);
              v152 = v6;
            }
            else
            {
              v150 = 0;
              v151 = 0;
              v152 = 0;
              v189 = 0;
            }
            *v11 = v189;
            v11 += 4;
            v5 = 0;
            v148[3] = v152;
            v148[2] = v151;
            v148[1] = v150;
            v8 = (int)a2;
            if ( v192 == 1 )
              goto LABEL_3;
            if ( (v120 & 4) != 0 )
            {
              *v11 = HIBYTE(v6);
              v153 = BYTE2(v6);
              v154 = BYTE1(v6);
              v155 = v6;
            }
            else
            {
              v153 = 0;
              *v11 = 0;
              v154 = 0;
              v155 = 0;
            }
            v149[7] = v155;
            v149[6] = v154;
            v149[5] = v153;
            v11 = v149 + 8;
            v8 = (int)a2;
            if ( v192 == 2 )
              goto LABEL_3;
            if ( (v120 & 8) != 0 )
            {
              *v11 = HIBYTE(v6);
              v156 = BYTE2(v6);
              v157 = BYTE1(v6);
              v158 = v6;
            }
            else
            {
              v156 = 0;
              *v11 = 0;
              v157 = 0;
              v158 = 0;
            }
            v149[11] = v158;
            v149[10] = v157;
            v149[9] = v156;
            v11 = v149 + 12;
            v8 = (int)a2;
            if ( v192 == 3 )
              goto LABEL_3;
            if ( (v120 & 0x10) != 0 )
            {
              *v11 = HIBYTE(v6);
              v159 = BYTE2(v6);
              v160 = BYTE1(v6);
              v161 = v6;
            }
            else
            {
              v159 = 0;
              *v11 = 0;
              v160 = 0;
              v161 = 0;
            }
            v149[15] = v161;
            v149[14] = v160;
            v149[13] = v159;
            v11 = v149 + 16;
            v8 = (int)a2;
            if ( v192 == 4 )
              goto LABEL_3;
            if ( (v120 & 0x20) != 0 )
            {
              *v11 = HIBYTE(v6);
              v162 = BYTE2(v6);
              v163 = BYTE1(v6);
              v164 = v6;
            }
            else
            {
              v162 = 0;
              *v11 = 0;
              v163 = 0;
              v164 = 0;
            }
            v149[19] = v164;
            v149[18] = v163;
            v149[17] = v162;
            v11 = v149 + 20;
            v8 = (int)a2;
            if ( v192 == 5 )
              goto LABEL_3;
            if ( (v120 & 0x40) != 0 )
            {
              v149[20] = HIBYTE(v6);
              v165 = BYTE2(v6);
              v166 = BYTE1(v6);
              v167 = v6;
            }
            else
            {
              v165 = 0;
              v149[20] = 0;
              v166 = 0;
              v167 = 0;
            }
            v149[23] = v167;
            v11 = v149 + 24;
            v149[22] = v166;
            v149[21] = v165;
            v9 = v180;
            v8 = (int)a2;
            if ( v192 != 6 )
            {
              if ( v120 >= 0 )
              {
                LOBYTE(v141) = 0;
                *v11 = 0;
                LOBYTE(v140) = 0;
                v168 = 0;
              }
              else
              {
                *v11 = HIBYTE(v6);
                v168 = v6;
              }
              v149[27] = v168;
              v149[26] = v140;
              v149[25] = v141;
              v11 = v149 + 28;
              goto LABEL_266;
            }
          }
        }
        else
        {
          if ( !(unsigned int)CheckReadNBytes2Ended(&v11[-a5], a2, v12, 4u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586669;
          v121 = 8;
          if ( v80 < 8 )
            v121 = v80;
          if ( !(unsigned int)CheckWriteNBytes(
                                v11,
                                v12,
                                (unsigned int)(4 * v121),
                                L"Decompress write off end of buffer") )
            return (unsigned int)-1626586665;
          v122 = v11;
          v123 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | ((v11[-a5 + 1] | (v11[-a5] << 8)) << 16);
          if ( (v120 & 1) != 0 )
            v123 ^= v6;
          *v11 = HIBYTE(v123);
          v11[3] = v123;
          v11[2] = BYTE1(v123);
          v11[1] = BYTE2(v123);
          v11 += 4;
          v8 = (int)a2;
          v124 = v80 - 1;
          if ( v124 )
          {
            v125 = v122 + 4;
            v126 = v122 + 4;
            v127 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | ((v11[-a5 + 1] | (v11[-a5] << 8)) << 16);
            if ( (v120 & 2) != 0 )
              v127 ^= v6;
            *v11 = HIBYTE(v127);
            v11 += 4;
            v125[3] = v127;
            v125[2] = BYTE1(v127);
            v125[1] = BYTE2(v127);
            v128 = v124 - 1;
            v8 = (int)a2;
            v9 = 0;
            if ( v128 )
            {
              v129 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | (((v11[-a5] << 8) | v11[-a5 + 1]) << 16);
              if ( (v120 & 4) != 0 )
                v129 ^= v6;
              *v11 = HIBYTE(v129);
              v126[7] = v129;
              v126[6] = BYTE1(v129);
              v126[5] = BYTE2(v129);
              v11 = v126 + 8;
              v8 = (int)a2;
              v130 = v128 - 1;
              if ( v130 )
              {
                v131 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | ((v11[-a5 + 1] | (v11[-a5] << 8)) << 16);
                if ( (v120 & 8) != 0 )
                  v131 ^= v6;
                *v11 = HIBYTE(v131);
                v126[11] = v131;
                v126[10] = BYTE1(v131);
                v126[9] = BYTE2(v131);
                v11 = v126 + 12;
                v8 = (int)a2;
                v132 = v130 - 1;
                if ( v132 )
                {
                  v133 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | (((v11[-a5] << 8) | v11[-a5 + 1]) << 16);
                  if ( (v120 & 0x10) != 0 )
                    v133 ^= v6;
                  *v11 = HIBYTE(v133);
                  v126[15] = v133;
                  v126[14] = BYTE1(v133);
                  v126[13] = BYTE2(v133);
                  v11 = v126 + 16;
                  v8 = (int)a2;
                  v134 = v132 - 1;
                  if ( v134 )
                  {
                    v135 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | ((v11[-a5 + 1] | (v11[-a5] << 8)) << 16);
                    if ( (v120 & 0x20) != 0 )
                      v135 ^= v6;
                    *v11 = HIBYTE(v135);
                    v126[19] = v135;
                    v126[18] = BYTE1(v135);
                    v126[17] = BYTE2(v135);
                    v11 = v126 + 20;
                    v8 = (int)a2;
                    v136 = v134 - 1;
                    if ( v136 )
                    {
                      v137 = v126[-a5 + 23] | (v126[-a5 + 22] << 8) | ((v126[-a5 + 21] | (v126[-a5 + 20] << 8)) << 16);
                      if ( (v120 & 0x40) != 0 )
                        v137 ^= v6;
                      v11 = v126 + 24;
                      v126[20] = HIBYTE(v137);
                      v126[23] = v137;
                      v126[22] = BYTE1(v137);
                      v126[21] = BYTE2(v137);
                      v8 = (int)a2;
                      if ( v136 != 1 )
                      {
                        v138 = v11[-a5 + 3] | (v11[-a5 + 2] << 8) | ((v11[-a5 + 1] | (v11[-a5] << 8)) << 16);
                        if ( v120 < 0 )
                          v138 ^= v6;
                        *v11 = HIBYTE(v138);
                        v126[27] = v138;
                        v126[26] = BYTE1(v138);
                        v126[25] = BYTE2(v138);
                        v11 = v126 + 28;
                        goto LABEL_266;
                      }
                    }
                  }
                }
              }
            }
          }
          else
          {
LABEL_3:
            v9 = v180;
          }
        }
      }
      else
      {
        if ( (_BYTE)v13 == 0xF2 || (_BYTE)v13 == 0xF7 )
          goto LABEL_121;
        if ( v14 == 32 || v15 == -64 )
        {
          if ( (_BYTE)v13 == 0xF1 || (_BYTE)v13 == 0xF6 )
          {
LABEL_96:
            if ( !(unsigned int)CheckReadNBytes(v10 + 1, v7, 2u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586643;
            v72 = *(unsigned __int16 *)(v10 + 1);
            v10 += 3;
          }
          else if ( v14 == 32 )
          {
            if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586635;
            v71 = *v10++;
            v72 = v71 & 0x1F;
            if ( !v72 )
            {
              if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
                return (unsigned int)-1626586635;
              v72 = *v10 + 32;
              goto LABEL_91;
            }
          }
          else
          {
            if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586631;
            v73 = *v10++;
            v72 = v73 & 0xF;
            if ( !v72 )
            {
              if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
                return (unsigned int)-1626586631;
              v72 = *v10 + 16;
LABEL_91:
              ++v10;
            }
          }
          if ( v185 == -64 || (_BYTE)v13 == 0xF6 )
          {
            if ( !(unsigned int)CheckReadNBytes(v10, v7, 4u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586621;
            v6 = v10[3] | (v10[2] << 8) | ((v10[1] | (*v10 << 8)) << 16);
            v10 += 4;
          }
          if ( !(unsigned int)CheckWriteNBytes(v11, v12, (unsigned int)(4 * v72), L"Decompress write off end of buffer") )
            return (unsigned int)-1626586611;
          while ( v72 )
          {
            if ( v180 )
            {
              HIBYTE(v76) = BYTE1(v6);
              LOBYTE(v75) = v6;
              *v11 = HIBYTE(v6);
              v77 = BYTE2(v6);
            }
            else
            {
              v74 = &v11[-a5];
              if ( !(unsigned int)CheckReadNBytes2Ended(v74, a2, v12, 4u, L"Decompress reads off end of buffer") )
                return (unsigned int)-1626586606;
              v75 = v6 ^ (v74[3] | (v74[2] << 8) | ((v74[1] | (*v74 << 8)) << 16));
              v76 = v6 ^ _byteswap_ushort(*((_WORD *)v74 + 1));
              *v11 = HIBYTE(v75);
              v77 = BYTE2(v75);
            }
            v11[3] = v75;
            --v72;
            v11[2] = HIBYTE(v76);
            v11[1] = v77;
            v11 += 4;
          }
          goto LABEL_2;
        }
        if ( (_BYTE)v13 == 0xF1 || (_BYTE)v13 == 0xF6 )
          goto LABEL_96;
        if ( v15 == -32 )
        {
          if ( (_BYTE)v13 != 0xF8 )
          {
            if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586578;
            v66 = *v10;
            v65 = v10 + 1;
            v64 = v66 & 0xF;
            if ( !v64 )
            {
              if ( !(unsigned int)CheckReadOneByte(v65, v7, L"Decompress reads one byte end of buffer") )
                return (unsigned int)-1626586578;
              v64 = *v65++ + 16;
            }
            goto LABEL_79;
          }
LABEL_73:
          if ( !(unsigned int)CheckReadNBytes(v10 + 1, v7, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586584;
          v64 = *(unsigned __int16 *)(v10 + 1);
          v65 = v10 + 3;
LABEL_79:
          if ( !(unsigned int)CheckReadNBytes(v65, v7, 8u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586574;
          v67 = *v65;
          v187 = v65[1];
          v191 = v65[2];
          v183 = v65[3];
          v176 = v65[4];
          v177 = v65[5];
          v178 = v65[6];
          v179 = v65[7];
          if ( !(unsigned int)CheckWriteNBytes(v11, v12, (unsigned int)(8 * v64), L"Decompress write off end of buffer") )
            return (unsigned int)-1626586568;
          v68 = v67;
          v10 = v65 + 8;
          v9 = v180;
          v69 = v183 | (v191 << 8) | ((v187 | (v68 << 8)) << 16);
          v70 = v179 | (v178 << 8) | ((v177 | (v176 << 8)) << 16);
          v8 = (int)a2;
          if ( v64 )
          {
            do
            {
              v11[3] = v69;
              v11[2] = BYTE1(v69);
              v11[1] = BYTE2(v69);
              *v11 = HIBYTE(v69);
              v11[7] = v179;
              v11[6] = v178;
              v11[5] = BYTE2(v70);
              v11[4] = HIBYTE(v70);
              v11 += 8;
              --v64;
            }
            while ( v64 );
            goto LABEL_2;
          }
        }
        else
        {
          if ( (_BYTE)v13 == 0xF8 )
            goto LABEL_73;
          if ( v14 == (char)0x80 )
          {
            if ( (_BYTE)v13 != 0xF4 )
            {
              if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
                return (unsigned int)-1626586542;
              v61 = *v10++;
              v60 = v61 & 0x1F;
              if ( !v60 )
              {
                if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
                  return (unsigned int)-1626586542;
                v60 = *v10++ + 32;
              }
              goto LABEL_67;
            }
LABEL_61:
            if ( !(unsigned int)CheckReadNBytes(v10 + 1, v7, 2u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586548;
            v60 = *(unsigned __int16 *)(v10 + 1);
            v10 += 3;
LABEL_67:
            v62 = 4 * v60;
            v63 = 4 * v60;
            if ( !(unsigned int)CheckReadNBytes(v10, v7, (unsigned int)(4 * v60), L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586534;
            if ( !(unsigned int)CheckWriteNBytes(v11, v12, v63, L"Decompress write off end of buffer") )
              return (unsigned int)-1626586533;
            v8 = (int)a2;
            v9 = v180;
            if ( v62 )
            {
              do
              {
                --v62;
                *v11++ = *v10++;
              }
              while ( v62 > 0 );
              goto LABEL_266;
            }
          }
          else
          {
            if ( (_BYTE)v13 == 0xF4 )
              goto LABEL_61;
            if ( v14 == 96 )
            {
              if ( (_BYTE)v13 != 0xF3 )
              {
                if ( !(unsigned int)CheckReadOneByte(v10, v7, L"Decompress reads one byte end of buffer") )
                  return (unsigned int)-1626586510;
                v56 = *v10;
                v55 = v10 + 1;
                v54 = v56 & 0x1F;
                if ( !v54 )
                {
                  if ( !(unsigned int)CheckReadOneByte(v55, v7, L"Decompress reads one byte end of buffer") )
                    return (unsigned int)-1626586510;
                  v54 = *v55++ + 32;
                }
                goto LABEL_55;
              }
            }
            else if ( (_BYTE)v13 != 0xF3 )
            {
              switch ( v13 )
              {
                case 249:
                  if ( v9 )
                  {
                    if ( !(unsigned int)CheckWriteNBytes(v11, v12, 0x20u, L"Decompress write off end of buffer") )
                      return (unsigned int)-1626586458;
                    v11[3] = v6;
                    v11[2] = BYTE1(v6);
                    v11[1] = BYTE2(v6);
                    *v11 = HIBYTE(v6);
                    v11[4] = HIBYTE(v6);
                    v53 = v11 + 24;
                    v11[7] = v6;
                    v11[6] = BYTE1(v6);
                    v11[5] = BYTE2(v6);
                    *((_QWORD *)v11 + 1) = 0;
                    *((_QWORD *)v11 + 2) = 0;
                    v11 += 32;
                    *v53 = 0;
                  }
                  else
                  {
                    v36 = &v11[-a5];
                    if ( !(unsigned int)CheckReadNBytes2Ended(v36, a2, v12, 4u, L"Decompress reads off end of buffer") )
                      return (unsigned int)-1626586466;
                    if ( !(unsigned int)CheckWriteNBytes(v11, v12, 0x20u, L"Decompress write off end of buffer") )
                      return (unsigned int)-1626586462;
                    v37 = v6 ^ (v36[3] | (v36[2] << 8) | ((v36[1] | (*v36 << 8)) << 16));
                    v11[3] = v6 ^ v36[3];
                    v11[2] = BYTE1(v37);
                    v11[1] = BYTE2(v37);
                    *v11 = HIBYTE(v37);
                    v38 = v6 ^ (v11[-a5 + 7] | (v11[-a5 + 6] << 8) | ((v11[-a5 + 5] | (v11[-a5 + 4] << 8)) << 16));
                    v39 = (__int64)&v11[-a5 + 8];
                    v11[7] = v6 ^ v11[-a5 + 7];
                    v11[6] = BYTE1(v38);
                    v11[5] = BYTE2(v38);
                    v11[4] = HIBYTE(v38);
                    v40 = *(_BYTE *)v39;
                    LOWORD(v38) = *(unsigned __int8 *)(v39 + 2) << 8;
                    v41 = *(unsigned __int8 *)(v39 + 3);
                    v11[9] = _byteswap_ushort(*(_WORD *)v39);
                    v11[8] = v40;
                    v42 = (__int64)&v11[-a5 + 12];
                    LOWORD(v38) = v41 | v38;
                    v11[11] = v38;
                    v11[10] = BYTE1(v38);
                    v43 = *(_BYTE *)v42;
                    LOWORD(v38) = _byteswap_ushort(*(_WORD *)(v42 + 2));
                    v11[13] = *(_BYTE *)(v42 + 1);
                    v11[12] = v43;
                    v11[15] = v38;
                    v11[14] = BYTE1(v38);
                    v44 = (__int64)&v11[-a5 + 16];
                    v45 = *(_BYTE *)v44;
                    LOWORD(v38) = *(unsigned __int8 *)(v44 + 2) << 8;
                    v46 = *(unsigned __int8 *)(v44 + 3);
                    v11[17] = _byteswap_ushort(*(_WORD *)v44);
                    v11[16] = v45;
                    v47 = (__int64)&v11[-a5 + 20];
                    LOWORD(v38) = v46 | v38;
                    v11[19] = v38;
                    v11[18] = BYTE1(v38);
                    v48 = *(_BYTE *)v47;
                    LOWORD(v38) = _byteswap_ushort(*(_WORD *)(v47 + 2));
                    v11[21] = *(_BYTE *)(v47 + 1);
                    v11[20] = v48;
                    v11[23] = v38;
                    v11[22] = BYTE1(v38);
                    v49 = v11 + 24;
                    v50 = (__int64)&v11[-a5 + 24];
                    v11 += 32;
                    v51 = *(_BYTE *)v50;
                    LOWORD(v38) = _byteswap_ushort(*(_WORD *)(v50 + 2));
                    v49[1] = *(_BYTE *)(v50 + 1);
                    *v49 = v51;
                    v52 = &v49[-a5 + 4];
                    v49[3] = v38;
                    v49[2] = BYTE1(v38);
                    LOWORD(v38) = _byteswap_ushort(*((_WORD *)v52 + 1));
                    *((_WORD *)v49 + 2) = *(_WORD *)v52;
                    v49[7] = v38;
                    v49[6] = BYTE1(v38);
                  }
                  break;
                case 250:
                  if ( v9 )
                  {
                    if ( !(unsigned int)CheckWriteNBytes(v11, v12, 0x20u, L"Decompress write off end of buffer") )
                      return (unsigned int)-1626586443;
                    v11[3] = v6;
                    v11[2] = BYTE1(v6);
                    v33 = 0;
                    *v11 = HIBYTE(v6);
                    v11[1] = BYTE2(v6);
                    *((_DWORD *)v11 + 1) = 0;
                    v11[8] = HIBYTE(v6);
                    v11[10] = BYTE1(v6);
                    v11[11] = v6;
                    v11[9] = BYTE2(v6);
                    *(_QWORD *)(v11 + 12) = 0;
                    *((_DWORD *)v11 + 5) = 0;
                    v30 = v11 + 24;
                    *(_DWORD *)v30 = 0;
                    v31 = v30 + 4;
                    LOBYTE(v35) = 0;
                    v30[4] = 0;
                    LOBYTE(v34) = 0;
                  }
                  else
                  {
                    v16 = &v11[-a5];
                    if ( !(unsigned int)CheckReadNBytes2Ended(v16, a2, v12, 4u, L"Decompress reads off end of buffer") )
                      return (unsigned int)-1626586451;
                    if ( !(unsigned int)CheckWriteNBytes(v11, v12, 0x20u, L"Decompress write off end of buffer") )
                      return (unsigned int)-1626586447;
                    v17 = v6 ^ (v16[3] | (v16[2] << 8) | ((v16[1] | (*v16 << 8)) << 16));
                    v11[3] = v6 ^ v16[3];
                    v11[2] = BYTE1(v17);
                    v11[1] = BYTE2(v17);
                    *v11 = HIBYTE(v17);
                    v18 = (__int64)&v11[-a5 + 4];
                    v19 = *(_BYTE *)v18;
                    v20 = _byteswap_ushort(*(_WORD *)(v18 + 2));
                    v11[5] = *(_BYTE *)(v18 + 1);
                    v11[4] = v19;
                    v11[7] = v20;
                    v11[6] = HIBYTE(v20);
                    v21 = v6 ^ (v11[-a5 + 11] | (v11[-a5 + 10] << 8) | ((v11[-a5 + 9] | (v11[-a5 + 8] << 8)) << 16));
                    v22 = (__int64)&v11[-a5 + 12];
                    v11[11] = v6 ^ v11[-a5 + 11];
                    v11[10] = BYTE1(v21);
                    v11[9] = BYTE2(v21);
                    v11[8] = HIBYTE(v21);
                    v23 = *(_BYTE *)v22;
                    LOWORD(v21) = *(unsigned __int8 *)(v22 + 2) << 8;
                    v24 = *(unsigned __int8 *)(v22 + 3);
                    v11[13] = _byteswap_ushort(*(_WORD *)v22);
                    v11[12] = v23;
                    LOWORD(v21) = v24 | v21;
                    v11[15] = v21;
                    v11[14] = BYTE1(v21);
                    v25 = (__int64)&v11[-a5 + 16];
                    v26 = *(_BYTE *)v25;
                    LOWORD(v21) = *(unsigned __int8 *)(v25 + 2) << 8;
                    v27 = *(unsigned __int8 *)(v25 + 3);
                    v11[17] = _byteswap_ushort(*(_WORD *)v25);
                    v11[16] = v26;
                    v28 = (__int64)&v11[-a5 + 20];
                    LOWORD(v21) = v27 | v21;
                    v11[19] = v21;
                    v11[18] = BYTE1(v21);
                    v29 = *(_BYTE *)v28;
                    LOWORD(v21) = _byteswap_ushort(*(_WORD *)(v28 + 2));
                    v11[21] = *(_BYTE *)(v28 + 1);
                    v11[20] = v29;
                    v11[23] = v21;
                    v11[22] = BYTE1(v21);
                    v30 = v11 + 24;
                    LOWORD(v21) = _byteswap_ushort(*(_WORD *)&v30[-a5 + 2]);
                    *(_WORD *)v30 = *(_WORD *)&v30[-a5];
                    v30[3] = v21;
                    v30[2] = BYTE1(v21);
                    v31 = v30 + 4;
                    v32 = &v30[-a5 + 4];
                    v33 = v32[1];
                    v34 = v32[3] | (v32[2] << 8);
                    v30[4] = *v32;
                    v35 = v34 >> 8;
                  }
                  v31[3] = v34;
                  v31[2] = v35;
                  v31[1] = v33;
                  v11 = v30 + 8;
                  break;
                case 253:
                  if ( !(unsigned int)CheckWriteNBytes(v11, v12, 4u, L"Decompress write off end of buffer") )
                    return (unsigned int)-1626586479;
                  *(_DWORD *)v11 = -1;
LABEL_31:
                  v11 += 4;
                  break;
                case 254:
                  if ( !(unsigned int)CheckWriteNBytes(v11, v12, 4u, L"Decompress write off end of buffer") )
                    return (unsigned int)-1626586485;
                  *(_DWORD *)v11 = 0;
                  goto LABEL_31;
              }
              ++v10;
LABEL_2:
              v8 = (int)a2;
              goto LABEL_3;
            }
            if ( !(unsigned int)CheckReadNBytes(v10 + 1, v7, 2u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586516;
            v54 = *(unsigned __int16 *)(v10 + 1);
            v55 = v10 + 3;
LABEL_55:
            if ( !(unsigned int)CheckReadNBytes(v55, v7, 4u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586506;
            v57 = *v55;
            v186 = v55[1];
            v190 = v55[2];
            v182 = v55[3];
            if ( !(unsigned int)CheckWriteNBytes(
                                  v11,
                                  v12,
                                  (unsigned int)(4 * v54),
                                  L"Decompress write off end of buffer") )
              return (unsigned int)-1626586502;
            v58 = v57;
            v9 = v180;
            v10 = v55 + 4;
            v59 = v182 | (v190 << 8) | ((v186 | (v58 << 8)) << 16);
            v8 = (int)a2;
            if ( v54 )
            {
              do
              {
                v11[3] = v59;
                v11[2] = BYTE1(v59);
                v11[1] = BYTE2(v59);
                *v11 = HIBYTE(v59);
                v11 += 4;
                --v54;
              }
              while ( v54 );
              goto LABEL_266;
            }
          }
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18034d518  mov     [rsp+arg_8], rdx
0x18034d51d  push    rbx
0x18034d51e  push    rbp
0x18034d51f  push    rsi
0x18034d520  push    rdi
0x18034d521  push    r12
0x18034d523  push    r13
0x18034d525  push    r14
0x18034d527  push    r15
0x18034d529  sub     rsp, 48h
0x18034d52d  xor     esi, esi
0x18034d52f  mov     r14d, r8d
0x18034d532  or      ebp, 0FFFFFFFFh
0x18034d535  mov     r13d, r9d
0x18034d538  add     r14, rcx
0x18034d53b  mov     [rsp+88h+var_4C], esi
0x18034d53f  mov     rax, rdx
0x18034d542  mov     [rsp+88h+var_50], esi
0x18034d546  lea     r12d, [rsi+1]
0x18034d54a  mov     rdi, rcx
0x18034d54d  mov     [rsp+88h+var_54], r12d
0x18034d552  mov     rbx, rdx
0x18034d555  add     r13, rdx
0x18034d558  jmp     short loc_18034D567
0x18034d55a  mov     rax, [rsp+88h+arg_8]
0x18034d562  mov     r12d, [rsp+88h+var_54]
0x18034d567  cmp     rdi, r14
0x18034d56a  jnb     loc_18034F2D3
0x18034d570  test    r12d, r12d
0x18034d573  jz      short loc_18034D592
0x18034d575  mov     ecx, ebx
0x18034d577  sub     ecx, eax
0x18034d579  movzx   eax, word ptr [rsp+88h+arg_20]
0x18034d581  cmp     ecx, eax
0x18034d583  jb      short loc_18034D592
0x18034d585  xor     r12d, r12d
0x18034d588  mov     [rsp+88h+var_54], r12d
0x18034d58d  mov     [rsp+88h+var_50], r12d
0x18034d592  lea     r8, aDecompressRead_1; "Decompress reads one byte end of buffer"
0x18034d599  mov     rdx, r14; unsigned __int8 *
0x18034d59c  mov     rcx, rdi; unsigned __int8 *
0x18034d59f  call    ?CheckReadOneByte@@YAHPEAE0PEBG@Z; CheckReadOneByte(uchar *,uchar *,ushort const *)
0x18034d5a4  test    eax, eax
0x18034d5a6  jz      loc_18034F2CE
0x18034d5ac  movzx   r15d, byte ptr [rdi]
0x18034d5b0  mov     al, r15b
0x18034d5b3  and     al, 0E0h
0x18034d5b5  jz      loc_18034EEF9
0x18034d5bb  cmp     r15b, 0F0h
0x18034d5bf  jz      loc_18034EECD
0x18034d5c5  mov     cl, r15b
0x18034d5c8  mov     [rsp+88h+var_50], 0
0x18034d5d0  and     cl, 0F0h
0x18034d5d3  mov     [rsp+88h+arg_10], cl
0x18034d5da  cmp     al, 40h ; '@'
0x18034d5dc  jz      loc_18034E299
0x18034d5e2  cmp     cl, 0D0h
0x18034d5e5  jz      loc_18034E299
0x18034d5eb  cmp     r15b, 0F2h
0x18034d5ef  jz      loc_18034E33A
0x18034d5f5  cmp     r15b, 0F7h
0x18034d5f9  jz      loc_18034E33A
0x18034d5ff  cmp     al, 20h ; ' '
0x18034d601  jz      loc_18034E0AF
0x18034d607  cmp     cl, 0C0h
0x18034d60a  jz      loc_18034E0AF
0x18034d610  cmp     r15b, 0F1h
0x18034d614  jz      loc_18034E157
0x18034d61a  cmp     r15b, 0F6h
0x18034d61e  jz      loc_18034E157
0x18034d624  cmp     cl, 0E0h
0x18034d627  jz      loc_18034DEF7
0x18034d62d  cmp     r15b, 0F8h
0x18034d631  jz      loc_18034DEFD
0x18034d637  cmp     al, 80h
0x18034d639  jz      loc_18034DE0C
0x18034d63f  cmp     r15b, 0F4h
0x18034d643  jz      loc_18034DE12
0x18034d649  cmp     al, 60h ; '`'
0x18034d64b  jz      loc_18034DCBA
0x18034d651  cmp     r15b, 0F3h
0x18034d655  jz      loc_18034DCC0
0x18034d65b  mov     ecx, r15d
0x18034d65e  sub     ecx, 0F9h
0x18034d664  jz      loc_18034D9C6
0x18034d66a  sub     ecx, 1
0x18034d66d  jz      short loc_18034D6D2
0x18034d66f  sub     ecx, 3
0x18034d672  jz      short loc_18034D6AA
0x18034d674  cmp     ecx, 1
0x18034d677  jnz     loc_18034DCB2
0x18034d67d  lea     r8d, [rcx+3]; unsigned __int64
0x18034d681  mov     rdx, r13; unsigned __int8 *
0x18034d684  mov     rcx, rbx; unsigned __int8 *
0x18034d687  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034d68e  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034d693  test    eax, eax
0x18034d695  jz      loc_18034F142
0x18034d69b  mov     dword ptr [rbx], 0
0x18034d6a1  add     rbx, 4
0x18034d6a5  jmp     loc_18034DCB2
0x18034d6aa  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034d6b1  mov     r8d, 4; unsigned __int64
0x18034d6b7  mov     rdx, r13; unsigned __int8 *
0x18034d6ba  mov     rcx, rbx; unsigned __int8 *
0x18034d6bd  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034d6c2  test    eax, eax
0x18034d6c4  jz      loc_18034F14C
0x18034d6ca  mov     dword ptr [rbx], 0FFFFFFFFh
0x18034d6d0  jmp     short loc_18034D6A1
0x18034d6d2  test    r12d, r12d
0x18034d6d5  jnz     loc_18034D929
0x18034d6db  movzx   r12d, word ptr [rsp+88h+arg_20]
0x18034d6e4  lea     rax, aDecompressRead; "Decompress reads off end of buffer"
0x18034d6eb  mov     rdx, [rsp+88h+arg_8]; unsigned __int8 *
0x18034d6f3  mov     r15, rbx
0x18034d6f6  sub     r15, r12
0x18034d6f9  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x18034d6fe  mov     rcx, r15; unsigned __int8 *
0x18034d701  mov     r9d, 4; unsigned __int64
0x18034d707  mov     r8, r13; unsigned __int8 *
0x18034d70a  call    ?CheckReadNBytes2Ended@@YAHPEAE00_KPEBG@Z; CheckReadNBytes2Ended(uchar *,uchar *,uchar *,unsigned __int64,ushort const *)
0x18034d70f  test    eax, eax
0x18034d711  jz      loc_18034F160
0x18034d717  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034d71e  mov     r8d, 20h ; ' '; unsigned __int64
0x18034d724  mov     rdx, r13; unsigned __int8 *
0x18034d727  mov     rcx, rbx; unsigned __int8 *
0x18034d72a  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034d72f  test    eax, eax
0x18034d731  jz      loc_18034F156
0x18034d737  movzx   ecx, byte ptr [r15]
0x18034d73b  movzx   eax, byte ptr [r15+1]
0x18034d740  shl     ecx, 8
0x18034d743  or      ecx, eax
0x18034d745  movzx   eax, byte ptr [r15+2]
0x18034d74a  shl     eax, 8
0x18034d74d  shl     ecx, 10h
0x18034d750  or      ecx, eax
0x18034d752  movzx   eax, byte ptr [r15+3]
0x18034d757  or      ecx, eax
0x18034d759  xor     ecx, ebp
0x18034d75b  mov     [rbx+3], cl
0x18034d75e  mov     eax, ecx
0x18034d760  shr     eax, 8
0x18034d763  mov     [rbx+2], al
0x18034d766  mov     eax, ecx
0x18034d768  shr     eax, 10h
0x18034d76b  mov     [rbx+1], al
0x18034d76e  shr     ecx, 18h
0x18034d771  mov     [rbx], cl
0x18034d773  lea     rcx, [rbx+4]
0x18034d777  sub     rcx, r12
0x18034d77a  movzx   r9d, byte ptr [rcx]
0x18034d77e  movzx   eax, byte ptr [rcx+1]
0x18034d782  mov     r8d, r9d
0x18034d785  movzx   edx, byte ptr [rcx+2]
0x18034d789  shl     edx, 8
0x18034d78c  shl     r8d, 8
0x18034d790  or      r8d, eax
0x18034d793  movzx   eax, byte ptr [rcx+3]
0x18034d797  or      edx, eax
0x18034d799  mov     [rbx+5], r8b
0x18034d79d  mov     [rbx+4], r9b
0x18034d7a1  lea     rcx, [rbx+8]
0x18034d7a5  sub     rcx, r12
0x18034d7a8  mov     eax, r8d
0x18034d7ab  shl     eax, 10h
0x18034d7ae  or      edx, eax
0x18034d7b0  mov     [rbx+7], dl
0x18034d7b3  shr     edx, 8
0x18034d7b6  mov     [rbx+6], dl
0x18034d7b9  movzx   eax, byte ptr [rcx+1]
0x18034d7bd  movzx   edx, byte ptr [rcx]
0x18034d7c0  shl     edx, 8
0x18034d7c3  or      edx, eax
0x18034d7c5  movzx   eax, byte ptr [rcx+2]
0x18034d7c9  shl     eax, 8
0x18034d7cc  shl     edx, 10h
0x18034d7cf  or      edx, eax
0x18034d7d1  movzx   eax, byte ptr [rcx+3]
0x18034d7d5  or      edx, eax
0x18034d7d7  lea     rcx, [rbx+0Ch]
0x18034d7db  xor     edx, ebp
0x18034d7dd  sub     rcx, r12
0x18034d7e0  mov     [rbx+0Bh], dl
0x18034d7e3  mov     eax, edx
0x18034d7e5  shr     eax, 8
0x18034d7e8  mov     [rbx+0Ah], al
0x18034d7eb  mov     eax, edx
0x18034d7ed  shr     eax, 10h
0x18034d7f0  mov     [rbx+9], al
0x18034d7f3  shr     edx, 18h
0x18034d7f6  mov     [rbx+8], dl
0x18034d7f9  movzx   r9d, byte ptr [rcx]
0x18034d7fd  movzx   r8d, byte ptr [rcx+1]
0x18034d802  mov     eax, r9d
0x18034d805  movzx   edx, byte ptr [rcx+2]
0x18034d809  shl     eax, 8
0x18034d80c  or      r8d, eax
0x18034d80f  shl     edx, 8
0x18034d812  movzx   eax, byte ptr [rcx+3]
0x18034d816  lea     rcx, [rbx+10h]
0x18034d81a  or      edx, eax
0x18034d81c  mov     [rbx+0Dh], r8b
0x18034d820  mov     eax, r8d
0x18034d823  mov     [rbx+0Ch], r9b
0x18034d827  shl     eax, 10h
0x18034d82a  or      edx, eax
0x18034d82c  mov     [rbx+0Fh], dl
0x18034d82f  shr     edx, 8
0x18034d832  mov     [rbx+0Eh], dl
0x18034d835  sub     rcx, r12
0x18034d838  movzx   r9d, byte ptr [rcx]
0x18034d83c  movzx   edx, byte ptr [rcx+2]
0x18034d840  mov     eax, r9d
0x18034d843  movzx   r8d, byte ptr [rcx+1]
0x18034d848  shl     eax, 8
0x18034d84b  or      r8d, eax
0x18034d84e  shl     edx, 8
0x18034d851  movzx   eax, byte ptr [rcx+3]
0x18034d855  lea     rcx, [rbx+14h]
0x18034d859  or      edx, eax
0x18034d85b  mov     [rbx+11h], r8b
0x18034d85f  mov     [rbx+10h], r9b
0x18034d863  mov     eax, r8d
0x18034d866  shl     eax, 10h
0x18034d869  sub     rcx, r12
0x18034d86c  or      edx, eax
0x18034d86e  mov     [rbx+13h], dl
0x18034d871  shr     edx, 8
0x18034d874  mov     [rbx+12h], dl
0x18034d877  movzx   r9d, byte ptr [rcx]
0x18034d87b  movzx   edx, byte ptr [rcx+2]
0x18034d87f  mov     eax, r9d
0x18034d882  movzx   r8d, byte ptr [rcx+1]
0x18034d887  shl     eax, 8
0x18034d88a  or      r8d, eax
0x18034d88d  shl     edx, 8
0x18034d890  movzx   eax, byte ptr [rcx+3]
0x18034d894  or      edx, eax
0x18034d896  mov     [rbx+15h], r8b
0x18034d89a  mov     [rbx+14h], r9b
0x18034d89e  mov     eax, r8d
0x18034d8a1  shl     eax, 10h
0x18034d8a4  or      edx, eax
0x18034d8a6  mov     [rbx+17h], dl
0x18034d8a9  shr     edx, 8
0x18034d8ac  mov     [rbx+16h], dl
0x18034d8af  add     rbx, 18h
0x18034d8b3  mov     rcx, rbx
0x18034d8b6  sub     rcx, r12
0x18034d8b9  movzx   eax, byte ptr [rcx+1]
0x18034d8bd  movzx   r9d, byte ptr [rcx]
0x18034d8c1  movzx   edx, byte ptr [rcx+2]
0x18034d8c5  mov     r8d, r9d
0x18034d8c8  shl     r8d, 8
0x18034d8cc  or      r8d, eax
0x18034d8cf  shl     edx, 8
0x18034d8d2  movzx   eax, byte ptr [rcx+3]
0x18034d8d6  or      edx, eax
0x18034d8d8  mov     [rbx+1], r8b
0x18034d8dc  mov     eax, r8d
0x18034d8df  mov     [rbx], r9b
0x18034d8e2  shl     eax, 10h
0x18034d8e5  or      edx, eax
0x18034d8e7  mov     [rbx+3], dl
0x18034d8ea  shr     edx, 8
0x18034d8ed  mov     [rbx+2], dl
0x18034d8f0  lea     rdx, [rbx+4]
0x18034d8f4  mov     rcx, rdx
0x18034d8f7  sub     rcx, r12
0x18034d8fa  movzx   eax, byte ptr [rcx+3]
0x18034d8fe  movzx   r8d, byte ptr [rcx+2]
0x18034d903  mov     r9b, [rcx+1]
0x18034d907  shl     r8d, 8
0x18034d90b  or      r8d, eax
0x18034d90e  mov     al, [rcx]
0x18034d910  mov     [rdx], al
0x18034d912  lea     rax, [rbx+8]
0x18034d916  mov     [rsp+88h+arg_0], rax
0x18034d91e  mov     eax, r8d
0x18034d921  shr     eax, 8
0x18034d924  jmp     loc_18034D9AC
0x18034d929  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034d930  mov     r8d, 20h ; ' '; unsigned __int64
0x18034d936  mov     rdx, r13; unsigned __int8 *
0x18034d939  mov     rcx, rbx; unsigned __int8 *
0x18034d93c  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034d941  test    eax, eax
0x18034d943  jz      loc_18034F16A
0x18034d949  mov     [rbx+3], bpl
0x18034d94d  mov     edx, ebp
0x18034d94f  shr     edx, 8
0x18034d952  mov     eax, ebp
0x18034d954  mov     [rbx+2], dl
0x18034d957  mov     ecx, ebp
0x18034d959  shr     eax, 18h
0x18034d95c  xor     r9b, r9b
0x18034d95f  mov     [rbx], al
  ... truncated ...
```
