# Planar::BDDecompressBitmap15(uchar *,uchar *,uint,uint,ushort)

- ea: `0x18034a518`
- end: `0x18034baf0`
- name: `?BDDecompressBitmap15@Planar@@YAJPEAE0IIG@Z`
- size: `5592`
- prototype: `__int64 __usercall@<rax>(Planar *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned __int16)`
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
- `0x18034a518`

## string_xrefs

- `0x18034a5a8`: `Decompress reads one byte end of buffer`
- `0x18034aa08`: `Decompress reads one byte end of buffer`
- `0x18034aa2f`: `Decompress reads one byte end of buffer`
- `0x18034ab0d`: `Decompress reads one byte end of buffer`
- `0x18034ab32`: `Decompress reads one byte end of buffer`
- `0x18034abfd`: `Decompress reads one byte end of buffer`
- `0x18034ac22`: `Decompress reads one byte end of buffer`
- `0x18034ad26`: `Decompress reads one byte end of buffer`
- `0x18034ad55`: `Decompress reads one byte end of buffer`
- `0x18034ad96`: `Decompress reads one byte end of buffer`
- `0x18034aed8`: `Decompress reads one byte end of buffer`
- `0x18034aeff`: `Decompress reads one byte end of buffer`
- `0x18034af3f`: `Decompress reads one byte end of buffer`
- `0x18034afda`: `Decompress reads one byte end of buffer`
- `0x18034b317`: `Decompress reads one byte end of buffer`
- `0x18034b784`: `Decompress reads one byte end of buffer`
- `0x18034b7ab`: `Decompress reads one byte end of buffer`
- `0x18034a699`: `Decompress write off end of buffer`
- `0x18034a6b9`: `Decompress write off end of buffer`
- `0x18034a725`: `Decompress write off end of buffer`
- `0x18034a7f3`: `Decompress write off end of buffer`
- `0x18034a898`: `Decompress write off end of buffer`
- `0x18034a983`: `Decompress write off end of buffer`
- `0x18034aa80`: `Decompress write off end of buffer`
- `0x18034ab7d`: `Decompress write off end of buffer`
- `0x18034ac76`: `Decompress write off end of buffer`
- `0x18034ae31`: `Decompress write off end of buffer`
- `0x18034b04c`: `Decompress write off end of buffer`
- `0x18034b1f0`: `Decompress write off end of buffer`
- `0x18034b38c`: `Decompress write off end of buffer`
- `0x18034b5cf`: `Decompress write off end of buffer`
- `0x18034b7e0`: `Decompress write off end of buffer`
- `0x18034b865`: `Decompress write off end of buffer`
- `0x18034b8da`: `Decompress write off end of buffer`
- `0x18034b916`: `Decompress write off end of buffer`
- `0x18034a6f2`: `Decompress reads off end of buffer`
- `0x18034a865`: `Decompress reads off end of buffer`
- `0x18034a9dc`: `Decompress reads off end of buffer`
- `0x18034aa54`: `Decompress reads off end of buffer`
- `0x18034aae2`: `Decompress reads off end of buffer`
- `0x18034ab5e`: `Decompress reads off end of buffer`
- `0x18034abd2`: `Decompress reads off end of buffer`
- `0x18034ac45`: `Decompress reads off end of buffer`
- `0x18034adba`: `Decompress reads off end of buffer`
- `0x18034adf0`: `Decompress reads off end of buffer`
- `0x18034ae6d`: `Decompress reads off end of buffer`
- `0x18034af65`: `Decompress reads off end of buffer`
- `0x18034af9b`: `Decompress reads off end of buffer`
- `0x18034b00a`: `Decompress reads off end of buffer`
- `0x18034b34a`: `Decompress reads off end of buffer`
- `0x18034b758`: `Decompress reads off end of buffer`
- `0x18034b816`: `Decompress reads off end of buffer`
- `0x18034b89b`: `Decompress reads off end of buffer`

## pseudocode

```c
__int64 __fastcall Planar::BDDecompressBitmap15(
        Planar *this,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        int a4,
        unsigned __int16 a5)
{
  unsigned int v5; // esi
  unsigned __int8 *v6; // r12
  unsigned __int8 *v7; // r13
  int v8; // eax
  int v9; // r14d
  unsigned __int8 *v10; // rdi
  unsigned __int16 v11; // r15
  unsigned __int8 *v12; // rbx
  int v13; // ebp
  char v14; // al
  char v15; // r13
  unsigned __int8 *v16; // rax
  __int16 v17; // cx
  unsigned __int8 *v18; // rax
  __int16 v19; // cx
  unsigned __int8 *v20; // rax
  unsigned __int8 *v21; // rax
  unsigned __int8 *v22; // rbx
  unsigned __int8 *v23; // rcx
  unsigned __int8 *v24; // rax
  unsigned __int8 v25; // dl
  __int16 v26; // cx
  unsigned __int8 *v27; // rax
  __int16 v28; // cx
  unsigned __int8 *v29; // rax
  unsigned __int8 *v30; // rax
  unsigned __int8 *v31; // rax
  _BYTE *v32; // r8
  unsigned __int8 *v33; // rax
  _BYTE *v34; // rax
  _DWORD *v35; // rax
  int v36; // r14d
  unsigned __int8 *v37; // rdi
  unsigned __int8 v38; // r14
  __int16 v39; // bp
  __int16 v40; // r13
  __int16 v41; // cx
  int v42; // eax
  char v43; // al
  int v44; // ebp
  unsigned int v45; // r14d
  int v46; // ebp
  unsigned __int8 *v47; // rdi
  unsigned __int8 v48; // bp
  __int16 v49; // r14
  __int16 v50; // r14
  char v51; // r14
  int v52; // r14d
  char v53; // r14
  __int16 v54; // cx
  unsigned __int8 v55; // ah
  char v56; // r14
  int v57; // r14d
  unsigned int v58; // r14d
  char v59; // r14
  char v60; // bp
  unsigned __int16 v61; // cx
  _BYTE *v62; // rdx
  _BYTE *v63; // r8
  _BYTE *v64; // rbx
  unsigned __int16 v65; // cx
  _BYTE *v66; // rdx
  unsigned __int16 v67; // cx
  unsigned __int16 v68; // cx
  unsigned __int16 v69; // cx
  _BYTE *v70; // rdx
  unsigned __int16 v71; // cx
  _BYTE *v72; // rbx
  unsigned __int16 v73; // cx
  _BYTE *v74; // r8
  unsigned __int16 v75; // cx
  char v76; // dl
  unsigned __int8 v77; // al
  unsigned __int16 v78; // kr00_2
  unsigned __int8 v79; // r8
  unsigned __int8 v80; // r8
  unsigned __int8 v81; // r8
  unsigned __int8 v82; // r8
  char v83; // al
  char v84; // bp
  int v85; // eax
  unsigned __int16 v86; // cx
  unsigned int v87; // r14d
  unsigned __int8 *v88; // r8
  unsigned __int8 *v89; // rdx
  unsigned __int16 v90; // cx
  unsigned int v91; // r8d
  unsigned __int16 v92; // cx
  unsigned int v93; // r8d
  unsigned __int16 v94; // cx
  unsigned int v95; // r8d
  unsigned __int16 v96; // cx
  unsigned int v97; // r8d
  unsigned __int16 v98; // cx
  unsigned int v99; // r8d
  unsigned __int16 v100; // cx
  unsigned __int16 v101; // cx
  int v102; // eax
  unsigned __int8 v103; // dl
  unsigned __int8 *v104; // r8
  unsigned __int8 v105; // al
  unsigned int v106; // r14d
  unsigned __int8 *v107; // rax
  unsigned __int16 v108; // kr02_2
  unsigned int v109; // r9d
  unsigned __int8 v110; // r8
  unsigned int v111; // r9d
  unsigned __int8 v112; // r8
  unsigned int v113; // r9d
  unsigned __int8 v114; // r8
  unsigned int v115; // r9d
  unsigned __int8 v116; // r8
  unsigned __int8 *v117; // r8
  unsigned int v118; // r9d
  unsigned __int8 v119; // al
  int v120; // r14d
  char v121; // r14
  __int16 v122; // cx
  unsigned __int8 *v123; // rbp
  unsigned __int8 v124; // cl
  int v126; // [rsp+30h] [rbp-58h]
  int v127; // [rsp+34h] [rbp-54h]
  unsigned __int8 *v128; // [rsp+38h] [rbp-50h]
  __int16 v129; // [rsp+90h] [rbp+8h]
  unsigned __int8 v131; // [rsp+A0h] [rbp+18h]
  unsigned __int8 v132; // [rsp+A8h] [rbp+20h]

  v5 = 0;
  v6 = (unsigned __int8 *)this + (unsigned int)a3;
  v7 = &a2[a4];
  v127 = 0;
  v8 = (int)a2;
  v128 = v7;
  v9 = 1;
  v10 = (unsigned __int8 *)this;
  v126 = 1;
  v11 = -129;
  v12 = a2;
  while ( v10 < v6 )
  {
    if ( v9 && (int)v12 - v8 >= (unsigned int)a5 )
    {
      v9 = 0;
      v127 = 0;
      v126 = 0;
    }
    if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
      return (unsigned int)-1626586815;
    v13 = *v10;
    v14 = *v10 & 0xE0;
    if ( !v14 )
    {
      if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
        return (unsigned int)-1626586802;
      v121 = *v10++;
      v120 = v121 & 0x1F;
      if ( !v120 )
      {
        if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586802;
        v120 = *v10++ + 32;
      }
LABEL_251:
      if ( v126 )
      {
        if ( v127 )
        {
          if ( !(unsigned int)CheckWriteNBytes(v12, v7, 2u, L"Decompress write off end of buffer") )
            return (unsigned int)-1626586766;
          v12[1] = v11;
          *v12 = HIBYTE(v11);
          v12 += 2;
          --v120;
        }
        if ( !(unsigned int)CheckWriteNBytes(v12, v7, (unsigned int)(2 * v120), L"Decompress write off end of buffer") )
          return (unsigned int)-1626586761;
        for ( ; v120; --v120 )
        {
          *(_WORD *)v12 = 0;
          v12 += 2;
        }
      }
      else
      {
        if ( v127 )
        {
          if ( !(unsigned int)CheckWriteNBytes(v12, v7, 2u, L"Decompress write off end of buffer") )
            return (unsigned int)-1626586788;
          if ( !(unsigned int)CheckReadNBytes2Ended(&v12[-a5], a2, v7, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586787;
          v122 = v11 ^ _byteswap_ushort(*(_WORD *)&v12[-a5]);
          v12[1] = v122;
          *v12 = HIBYTE(v122);
          v12 += 2;
          --v120;
        }
        if ( !(unsigned int)CheckWriteNBytes(v12, v7, (unsigned int)(2 * v120), L"Decompress write off end of buffer") )
          return (unsigned int)-1626586779;
        while ( v120 )
        {
          v123 = &v12[-a5];
          if ( !(unsigned int)CheckReadNBytes2Ended(v123, a2, v7, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586775;
          v124 = *v123;
          --v120;
          v12[1] = v123[1];
          *v12 = v124;
          v12 += 2;
        }
      }
      v127 = 1;
LABEL_5:
      v8 = (int)a2;
      goto LABEL_6;
    }
    if ( (_BYTE)v13 == 0xF0 )
    {
      if ( !(unsigned int)CheckReadNBytes(v10 + 1, v6, 2u, L"Decompress reads off end of buffer") )
        return (unsigned int)-1626586798;
      v120 = *(unsigned __int16 *)(v10 + 1);
      v10 += 3;
      goto LABEL_251;
    }
    v127 = 0;
    v15 = v13 & 0xF0;
    if ( v14 == 64 || v15 == -48 )
    {
      if ( (_BYTE)v13 == 0xF2 || (_BYTE)v13 == 0xF7 )
      {
LABEL_124:
        if ( !(unsigned int)CheckReadNBytes(v10 + 1, v6, 2u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586727;
        v58 = *(unsigned __int16 *)(v10 + 1);
        v10 += 3;
        goto LABEL_126;
      }
      if ( v14 == 64 )
      {
        if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586719;
        v56 = *v10++;
        v57 = v56 & 0x1F;
        if ( !v57 )
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586719;
LABEL_123:
          v58 = *v10++ + 1;
          goto LABEL_126;
        }
      }
      else
      {
        if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586715;
        v59 = *v10++;
        v57 = v59 & 0xF;
        if ( !v57 )
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586715;
          goto LABEL_123;
        }
      }
      v58 = 8 * v57;
LABEL_126:
      if ( v15 == -48 || (_BYTE)v13 == 0xF7 )
      {
        if ( (unsigned int)CheckReadNBytes(v10, v6, 2u, L"Decompress reads off end of buffer") )
        {
          v11 = _byteswap_ushort(*(_WORD *)v10);
          v10 += 2;
          goto LABEL_130;
        }
        return (unsigned int)-1626586708;
      }
LABEL_130:
      while ( v58 > 8 )
      {
        if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586691;
        v60 = *v10;
        if ( v126 )
        {
          if ( !(unsigned int)CheckWriteNBytes(v12, v128, 0x10u, L"Decompress write off end of buffer") )
            return (unsigned int)-1626586679;
          v76 = v11;
          if ( (v60 & 1) != 0 )
          {
            *v12 = HIBYTE(v11);
            v77 = v11;
          }
          else
          {
            *v12 = 0;
            v77 = 0;
          }
          v12[1] = v77;
          if ( (v60 & 2) != 0 )
            v78 = v11;
          else
            v78 = 0;
          v12[2] = HIBYTE(v78);
          v12[3] = v78;
          if ( (v60 & 4) != 0 )
          {
            v12[4] = HIBYTE(v11);
            v79 = v11;
          }
          else
          {
            v12[4] = 0;
            v79 = 0;
          }
          v12[5] = v79;
          if ( (v60 & 8) != 0 )
          {
            v12[6] = HIBYTE(v11);
            v80 = v11;
          }
          else
          {
            v12[6] = 0;
            v80 = 0;
          }
          v12[7] = v80;
          if ( (v60 & 0x10) != 0 )
          {
            v12[8] = HIBYTE(v11);
            v81 = v11;
          }
          else
          {
            v12[8] = 0;
            v81 = 0;
          }
          v12[9] = v81;
          if ( (v60 & 0x20) != 0 )
          {
            v12[10] = HIBYTE(v11);
            v82 = v11;
          }
          else
          {
            v12[10] = 0;
            v82 = 0;
          }
          v12[11] = v82;
          v72 = v12 + 12;
          if ( (v60 & 0x40) != 0 )
          {
            *v72 = HIBYTE(v11);
            v83 = v11;
          }
          else
          {
            *v72 = 0;
            v83 = 0;
          }
          v72[1] = v83;
          v74 = v72 + 2;
          if ( v60 >= 0 )
          {
            *v74 = 0;
            v76 = 0;
          }
          else
          {
            *v74 = HIBYTE(v11);
          }
          LOBYTE(v75) = v76;
        }
        else
        {
          if ( !(unsigned int)CheckReadNBytes2Ended(&v12[-a5], a2, v128, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586687;
          if ( !(unsigned int)CheckWriteNBytes(v12, v128, 0x10u, L"Decompress write off end of buffer") )
            return (unsigned int)-1626586683;
          v61 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
          if ( (v60 & 1) != 0 )
            v61 ^= v11;
          v62 = v12 + 2;
          v63 = v62;
          *v12 = HIBYTE(v61);
          v12[1] = v61;
          v64 = v12 + 2;
          v65 = _byteswap_ushort(*(_WORD *)&v62[-a5]);
          if ( (v60 & 2) != 0 )
            v65 ^= v11;
          *v62 = HIBYTE(v65);
          v66 = v62 + 2;
          v63[1] = v65;
          v67 = _byteswap_ushort(*(_WORD *)&v64[-a5 + 2]);
          if ( (v60 & 4) != 0 )
            v67 ^= v11;
          *v66 = HIBYTE(v67);
          v64[3] = v67;
          v68 = _byteswap_ushort(*(_WORD *)&v64[-a5 + 4]);
          if ( (v60 & 8) != 0 )
            v68 ^= v11;
          v64[4] = HIBYTE(v68);
          v64[5] = v68;
          v69 = _byteswap_ushort(*(_WORD *)&v64[-a5 + 6]);
          if ( (v60 & 0x10) != 0 )
            v69 ^= v11;
          v64[6] = HIBYTE(v69);
          v64[7] = v69;
          v70 = v64 + 8;
          v71 = _byteswap_ushort(*(_WORD *)&v64[-a5 + 8]);
          if ( (v60 & 0x20) != 0 )
            v71 ^= v11;
          v72 = v64 + 10;
          *v70 = HIBYTE(v71);
          v70[1] = v71;
          v73 = _byteswap_ushort(*(_WORD *)&v72[-a5]);
          if ( (v60 & 0x40) != 0 )
            v73 ^= v11;
          v74 = v72 + 2;
          *v72 = HIBYTE(v73);
          v72[1] = v73;
          v75 = _byteswap_ushort(*(_WORD *)&v72[-a5 + 2]);
          if ( v60 < 0 )
            v75 ^= v11;
          *v74 = HIBYTE(v75);
        }
        v74[1] = v75;
        ++v10;
        v58 -= 8;
        v12 = v72 + 4;
      }
      if ( !v58 )
      {
        v7 = v128;
        goto LABEL_5;
      }
      if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
        return (unsigned int)-1626586673;
      v84 = *v10++;
      if ( !v126 )
      {
        if ( !(unsigned int)CheckReadNBytes2Ended(&v12[-a5], a2, v128, 2u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586669;
        v85 = 8;
        if ( v58 < 8 )
          v85 = v58;
        if ( !(unsigned int)CheckWriteNBytes(v12, v128, (unsigned int)(2 * v85), L"Decompress write off end of buffer") )
          return (unsigned int)-1626586665;
        v86 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
        if ( (v84 & 1) != 0 )
          v86 ^= v11;
        *v12 = HIBYTE(v86);
        v12[1] = v86;
        v12 += 2;
        v8 = (int)a2;
        v87 = v58 - 1;
        if ( !v87 )
        {
          v7 = v128;
          goto LABEL_6;
        }
        v88 = v12;
        v89 = v12;
        v90 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
        if ( (v84 & 2) != 0 )
          v90 ^= v11;
        *v12 = HIBYTE(v90);
        v12 += 2;
        v88[1] = v90;
        v91 = v87 - 1;
        v8 = (int)a2;
        v9 = 0;
        if ( !v91 )
          goto LABEL_3;
        v92 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
        if ( (v84 & 4) != 0 )
          v92 ^= v11;
        *v12 = HIBYTE(v92);
        v89[3] = v92;
        v12 = v89 + 4;
        v8 = (int)a2;
        v93 = v91 - 1;
        if ( !v93 )
          goto LABEL_3;
        v94 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
        if ( (v84 & 8) != 0 )
          v94 ^= v11;
        *v12 = HIBYTE(v94);
        v89[5] = v94;
        v12 = v89 + 6;
        v8 = (int)a2;
        v95 = v93 - 1;
        if ( !v95 )
          goto LABEL_3;
        v96 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
        if ( (v84 & 0x10) != 0 )
          v96 ^= v11;
        *v12 = HIBYTE(v96);
        v89[7] = v96;
        v12 = v89 + 8;
        v8 = (int)a2;
        v97 = v95 - 1;
        if ( !v97 )
          goto LABEL_3;
        v98 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
        if ( (v84 & 0x20) != 0 )
          v98 ^= v11;
        *v12 = HIBYTE(v98);
        v89[9] = v98;
        v12 = v89 + 10;
        v8 = (int)a2;
        v99 = v97 - 1;
        if ( !v99 )
          goto LABEL_3;
        v100 = _byteswap_ushort(*(_WORD *)&v89[-a5 + 10]);
        if ( (v84 & 0x40) != 0 )
          v100 ^= v11;
        v12 = v89 + 12;
        v89[10] = HIBYTE(v100);
        v89[11] = v100;
        v8 = (int)a2;
        if ( v99 == 1 )
        {
LABEL_3:
          v7 = v128;
          continue;
        }
        v101 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
        if ( v84 < 0 )
          v101 ^= v11;
        v7 = v128;
        *v12 = HIBYTE(v101);
        v89[13] = v101;
        v12 = v89 + 14;
        goto LABEL_74;
      }
      v7 = v128;
      v102 = 8;
      if ( v58 < 8 )
        v102 = v58;
      if ( !(unsigned int)CheckWriteNBytes(v12, v128, (unsigned int)(2 * v102), L"Decompress write off end of buffer") )
        return (unsigned int)-1626586661;
      v103 = v11;
      v104 = v12;
      if ( (v84 & 1) != 0 )
      {
        *v12 = HIBYTE(v11);
        v105 = v11;
      }
      else
      {
        *v12 = 0;
        v105 = 0;
      }
      v12[1] = v105;
      v12 += 2;
      v8 = (int)a2;
      v106 = v58 - 1;
      if ( !v106 )
        goto LABEL_6;
      v107 = v104 + 2;
      if ( (v84 & 2) != 0 )
        v108 = v11;
      else
        v108 = 0;
      *v12 = HIBYTE(v108);
      v12 += 2;
      v104[3] = v108;
      v109 = v106 - 1;
      v9 = v126;
      if ( !v109 )
        goto LABEL_74;
      if ( (v84 & 4) != 0 )
      {
        *v12 = HIBYTE(v11);
        v110 = v11;
      }
      else
      {
        *v12 = 0;
        v110 = 0;
      }
      v107[3] = v110;
      v12 = v107 + 4;
      v111 = v109 - 1;
      if ( !v111 )
        goto LABEL_74;
      if ( (v84 & 8) != 0 )
      {
        *v12 = HIBYTE(v11);
        v112 = v11;
      }
      else
      {
        *v12 = 0;
        v112 = 0;
      }
      v107[5] = v112;
      v12 = v107 + 6;
      v113 = v111 - 1;
      if ( !v113 )
        goto LABEL_74;
      if ( (v84 & 0x10) != 0 )
      {
        *v12 = HIBYTE(v11);
        v114 = v11;
      }
      else
      {
        *v12 = 0;
        v114 = 0;
      }
      v107[7] = v114;
      v12 = v107 + 8;
      v115 = v113 - 1;
      if ( v115 )
      {
        if ( (v84 & 0x20) != 0 )
        {
          *v12 = HIBYTE(v11);
          v116 = v11;
        }
        else
        {
          *v12 = 0;
          v116 = 0;
        }
        v107[9] = v116;
        v117 = v107 + 10;
        v8 = (int)a2;
        v12 = v117;
        v118 = v115 - 1;
        if ( v118 )
        {
          if ( (v84 & 0x40) != 0 )
          {
            *v117 = HIBYTE(v11);
            v119 = v11;
          }
          else
          {
            *v117 = 0;
            v119 = 0;
          }
          v117[1] = v119;
          v12 = v117 + 2;
          v8 = (int)a2;
          if ( v118 != 1 )
          {
            if ( v84 >= 0 )
            {
              *v12 = 0;
              v103 = 0;
            }
            else
            {
              *v12 = HIBYTE(v11);
            }
            v117[3] = v103;
            v12 = v117 + 4;
            goto LABEL_74;
          }
        }
      }
      else
      {
LABEL_74:
        v8 = (int)a2;
      }
    }
    else
    {
      if ( (_BYTE)v13 == 0xF2 || (_BYTE)v13 == 0xF7 )
        goto LABEL_124;
      if ( v14 == 32 || v15 == -64 )
      {
        if ( (_BYTE)v13 == 0xF1 || (_BYTE)v13 == 0xF6 )
        {
LABEL_99:
          if ( !(unsigned int)CheckReadNBytes(v10 + 1, v6, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586643;
          v52 = *(unsigned __int16 *)(v10 + 1);
          v10 += 3;
        }
        else if ( v14 == 32 )
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586635;
          v51 = *v10++;
          v52 = v51 & 0x1F;
          if ( !v52 )
          {
            if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586635;
            v52 = *v10 + 32;
            goto LABEL_94;
          }
        }
        else
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586631;
          v53 = *v10++;
          v52 = v53 & 0xF;
          if ( !v52 )
          {
            if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586631;
            v52 = *v10 + 16;
LABEL_94:
            ++v10;
          }
        }
        if ( v15 == -64 || (_BYTE)v13 == 0xF6 )
        {
          if ( !(unsigned int)CheckReadNBytes(v10, v6, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586621;
          v11 = _byteswap_ushort(*(_WORD *)v10);
          v10 += 2;
        }
        v7 = v128;
        if ( !(unsigned int)CheckWriteNBytes(v12, v128, (unsigned int)(2 * v52), L"Decompress write off end of buffer") )
          return (unsigned int)-1626586611;
        while ( v52 )
        {
          if ( v126 )
          {
            v55 = HIBYTE(v11);
            LOBYTE(v54) = v11;
          }
          else
          {
            if ( !(unsigned int)CheckReadNBytes2Ended(&v12[-a5], a2, v128, 2u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586606;
            v54 = v11 ^ _byteswap_ushort(*(_WORD *)&v12[-a5]);
            v55 = HIBYTE(v54);
          }
          --v52;
          *v12 = v55;
          v12[1] = v54;
          v12 += 2;
        }
        goto LABEL_5;
      }
      if ( (_BYTE)v13 == 0xF1 || (_BYTE)v13 == 0xF6 )
        goto LABEL_99;
      if ( v15 == -32 )
      {
        if ( (_BYTE)v13 == 0xF8 )
        {
LABEL_76:
          if ( !(unsigned int)CheckReadNBytes(v10 + 1, v6, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586584;
          v46 = *(unsigned __int16 *)(v10 + 1);
          v47 = v10 + 3;
        }
        else
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586578;
          v48 = *v10;
          v47 = v10 + 1;
          v46 = v48 & 0xF;
          if ( !v46 )
          {
            if ( !(unsigned int)CheckReadOneByte(v47, v6, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586578;
            v46 = *v47++ + 16;
          }
        }
        if ( !(unsigned int)CheckReadNBytes(v47, v6, 4u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586574;
        v7 = v128;
        v49 = *v47;
        v129 = v47[1];
        v131 = v47[2];
        v132 = v47[3];
        if ( !(unsigned int)CheckWriteNBytes(v12, v128, (unsigned int)(4 * v46), L"Decompress write off end of buffer") )
          return (unsigned int)-1626586568;
        v10 = v47 + 4;
        v50 = v129 | (v49 << 8);
        v8 = (int)a2;
        if ( v46 )
        {
          do
          {
            v12[1] = v50;
            *v12 = HIBYTE(v50);
            v12[3] = v132;
            v12[2] = v131;
            v12 += 4;
            --v46;
          }
          while ( v46 );
          goto LABEL_5;
        }
        goto LABEL_6;
      }
      if ( (_BYTE)v13 == 0xF8 )
        goto LABEL_76;
      if ( v14 == (char)0x80 )
      {
        if ( (_BYTE)v13 != 0xF4 )
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586542;
          v43 = *v10++;
          v42 = v43 & 0x1F;
          if ( !v42 )
          {
            if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586542;
            v42 = *v10++ + 32;
          }
          goto LABEL_70;
        }
LABEL_64:
        if ( !(unsigned int)CheckReadNBytes(v10 + 1, v6, 2u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586548;
        v42 = *(unsigned __int16 *)(v10 + 1);
        v10 += 3;
LABEL_70:
        v44 = 2 * v42;
        v45 = 2 * v42;
        if ( !(unsigned int)CheckReadNBytes(v10, v6, (unsigned int)(2 * v42), L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586534;
        v7 = v128;
        if ( !(unsigned int)CheckWriteNBytes(v12, v128, v45, L"Decompress write off end of buffer") )
          return (unsigned int)-1626586533;
        v8 = (int)a2;
        v9 = v126;
        if ( v44 )
        {
          do
          {
            --v44;
            *v12++ = *v10++;
          }
          while ( v44 > 0 );
          goto LABEL_74;
        }
      }
      else
      {
        if ( (_BYTE)v13 == 0xF4 )
          goto LABEL_64;
        if ( v14 != 96 )
        {
          if ( (_BYTE)v13 != 0xF3 )
          {
            v7 = v128;
            switch ( v13 )
            {
              case 249:
                if ( v9 )
                {
                  if ( !(unsigned int)CheckWriteNBytes(v12, v128, 0x10u, L"Decompress write off end of buffer") )
                    return (unsigned int)-1626586458;
                  v12[1] = v11;
                  *v12 = HIBYTE(v11);
                  v12[2] = HIBYTE(v11);
                  v35 = v12 + 12;
                  v12[3] = v11;
                  *(_QWORD *)(v12 + 4) = 0;
                  v12 += 16;
                  *v35 = 0;
                }
                else
                {
                  if ( !(unsigned int)CheckReadNBytes2Ended(
                                        &v12[-a5],
                                        a2,
                                        v128,
                                        2u,
                                        L"Decompress reads off end of buffer") )
                    return (unsigned int)-1626586466;
                  if ( !(unsigned int)CheckWriteNBytes(v12, v128, 0x10u, L"Decompress write off end of buffer") )
                    return (unsigned int)-1626586462;
                  v26 = v11 ^ _byteswap_ushort(*(_WORD *)&v12[-a5]);
                  v12[1] = v26;
                  *v12 = HIBYTE(v26);
                  v27 = &v12[-a5 + 4];
                  v28 = v11 ^ _byteswap_ushort(*(_WORD *)&v12[-a5 + 2]);
                  v12[3] = v28;
                  v12[2] = HIBYTE(v28);
                  LOBYTE(v28) = *v27;
                  v12[5] = v27[1];
                  v12[4] = v28;
                  v29 = &v12[-a5 + 6];
                  LOBYTE(v28) = *v29;
                  v12[7] = v29[1];
                  v12[6] = v28;
                  v30 = &v12[-a5 + 8];
                  LOBYTE(v28) = *v30;
                  v12[9] = v30[1];
                  v12[8] = v28;
                  v31 = &v12[-a5 + 10];
                  LOBYTE(v28) = *v31;
                  v12[11] = v31[1];
                  v12[10] = v28;
                  v32 = v12 + 12;
                  v33 = &v12[-a5 + 12];
                  v12 += 16;
                  LOBYTE(v28) = *v33;
                  v32[1] = v33[1];
                  *v32 = v28;
                  v34 = &v32[-a5 + 2];
                  LOBYTE(v28) = *v34;
                  v32[3] = v34[1];
                  v32[2] = v28;
                }
                break;
              case 250:
                if ( v9 )
                {
                  if ( !(unsigned int)CheckWriteNBytes(v12, v128, 0x10u, L"Decompress write off end of buffer") )
                    return (unsigned int)-1626586443;
                  v12[1] = v11;
                  *v12 = HIBYTE(v11);
                  *((_WORD *)v12 + 1) = 0;
                  v12[5] = v11;
                  v12[4] = HIBYTE(v11);
                  *(_DWORD *)(v12 + 6) = 0;
                  *((_WORD *)v12 + 5) = 0;
                  v22 = v12 + 12;
                  v25 = 0;
                  v23 = v22 + 2;
                  *(_WORD *)v22 = 0;
                  v22[2] = 0;
                }
                else
                {
                  if ( !(unsigned int)CheckReadNBytes2Ended(
                                        &v12[-a5],
                                        a2,
                                        v128,
                                        2u,
                                        L"Decompress reads off end of buffer") )
                    return (unsigned int)-1626586451;
                  if ( !(unsigned int)CheckWriteNBytes(v12, v128, 0x10u, L"Decompress write off end of buffer") )
                    return (unsigned int)-1626586447;
                  v16 = &v12[-a5 + 2];
                  v17 = v11 ^ _byteswap_ushort(*(_WORD *)&v12[-a5]);
                  v12[1] = v17;
                  *v12 = HIBYTE(v17);
                  LOBYTE(v17) = *v16;
                  v12[3] = v16[1];
                  v12[2] = v17;
                  v18 = &v12[-a5 + 6];
                  v19 = v11 ^ _byteswap_ushort(*(_WORD *)&v12[-a5 + 4]);
                  v12[5] = v19;
                  v12[4] = HIBYTE(v19);
                  LOBYTE(v19) = *v18;
                  v12[7] = v18[1];
                  v12[6] = v19;
                  v20 = &v12[-a5 + 8];
                  LOBYTE(v19) = *v20;
                  v12[9] = v20[1];
                  v12[8] = v19;
                  v21 = &v12[-a5 + 10];
                  LOBYTE(v19) = *v21;
                  v12[11] = v21[1];
                  v12[10] = v19;
                  v22 = v12 + 12;
                  LOBYTE(v19) = v22[-a5];
                  v22[1] = v22[-a5 + 1];
                  *v22 = v19;
                  v23 = v22 + 2;
                  v24 = &v22[-a5 + 2];
                  v25 = v24[1];
                  v22[2] = *v24;
                }
                v23[1] = v25;
                v12 = v22 + 4;
                break;
              case 253:
                if ( !(unsigned int)CheckWriteNBytes(v12, v128, 2u, L"Decompress write off end of buffer") )
                  return (unsigned int)-1626586479;
                *(_WORD *)v12 = 0x7FFF;
LABEL_34:
                v12 += 2;
                break;
              case 254:
                if ( !(unsigned int)CheckWriteNBytes(v12, v128, 2u, L"Decompress write off end of buffer") )
                  return (unsigned int)-1626586485;
                *(_WORD *)v12 = 0;
                goto LABEL_34;
            }
            ++v10;
            goto LABEL_5;
          }
LABEL_52:
          if ( !(unsigned int)CheckReadNBytes(v10 + 1, v6, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586516;
          v36 = *(unsigned __int16 *)(v10 + 1);
          v37 = v10 + 3;
          goto LABEL_58;
        }
        if ( (_BYTE)v13 == 0xF3 )
          goto LABEL_52;
        if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586510;
        v38 = *v10;
        v37 = v10 + 1;
        v36 = v38 & 0x1F;
        if ( !v36 )
        {
          if ( !(unsigned int)CheckReadOneByte(v37, v6, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586510;
          v36 = *v37++ + 32;
        }
LABEL_58:
        if ( !(unsigned int)CheckReadNBytes(v37, v6, 2u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586506;
        v39 = *v37;
        v40 = v37[1];
        if ( !(unsigned int)CheckWriteNBytes(v12, v128, (unsigned int)(2 * v36), L"Decompress write off end of buffer") )
          return (unsigned int)-1626586502;
        v8 = (int)a2;
        v10 = v37 + 2;
        v41 = v40 | (v39 << 8);
        v7 = v128;
        if ( v36 )
        {
          do
          {
            v12[1] = v41;
            *v12 = HIBYTE(v41);
            v12 += 2;
            --v36;
          }
          while ( v36 );
          goto LABEL_5;
        }
LABEL_6:
        v9 = v126;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18034a518  mov     [rsp+arg_8], rdx
0x18034a51d  push    rbx
0x18034a51e  push    rbp
0x18034a51f  push    rsi
0x18034a520  push    rdi
0x18034a521  push    r12
0x18034a523  push    r13
0x18034a525  push    r14
0x18034a527  push    r15
0x18034a529  sub     rsp, 48h
0x18034a52d  xor     esi, esi
0x18034a52f  mov     r12d, r8d
0x18034a532  add     r12, rcx
0x18034a535  mov     r13d, r9d
0x18034a538  add     r13, rdx
0x18034a53b  mov     [rsp+88h+var_54], esi
0x18034a53f  mov     rax, rdx
0x18034a542  mov     [rsp+88h+var_50], r13
0x18034a547  lea     r14d, [rsi+1]
0x18034a54b  mov     rdi, rcx
0x18034a54e  mov     [rsp+88h+var_58], r14d
0x18034a553  mov     r15d, 0FF7Fh
0x18034a559  mov     rbx, rdx
0x18034a55c  jmp     short loc_18034A57E
0x18034a55e  mov     r13, [rsp+88h+var_50]
0x18034a563  jmp     short loc_18034A579
0x18034a565  mov     r13, [rsp+88h+var_50]
0x18034a56a  jmp     short loc_18034A57E
0x18034a56c  mov     r13, [rsp+88h+var_50]
0x18034a571  mov     rax, [rsp+88h+arg_8]
0x18034a579  mov     r14d, [rsp+88h+var_58]
0x18034a57e  cmp     rdi, r12
0x18034a581  jnb     loc_18034BADD
0x18034a587  test    r14d, r14d
0x18034a58a  jz      short loc_18034A5A8
0x18034a58c  mov     ecx, ebx
0x18034a58e  sub     ecx, eax
0x18034a590  movzx   eax, word ptr [rsp+88h+arg_20]
0x18034a598  cmp     ecx, eax
0x18034a59a  jb      short loc_18034A5A8
0x18034a59c  xor     r14d, r14d
0x18034a59f  mov     [rsp+88h+var_54], esi
0x18034a5a3  mov     [rsp+88h+var_58], r14d
0x18034a5a8  lea     r8, aDecompressRead_1; "Decompress reads one byte end of buffer"
0x18034a5af  mov     rdx, r12; unsigned __int8 *
0x18034a5b2  mov     rcx, rdi; unsigned __int8 *
0x18034a5b5  call    ?CheckReadOneByte@@YAHPEAE0PEBG@Z; CheckReadOneByte(uchar *,uchar *,ushort const *)
0x18034a5ba  test    eax, eax
0x18034a5bc  jz      loc_18034BAD8
0x18034a5c2  movzx   ebp, byte ptr [rdi]
0x18034a5c5  mov     al, bpl
0x18034a5c8  and     al, 0E0h
0x18034a5ca  jz      loc_18034B784
0x18034a5d0  cmp     bpl, 0F0h
0x18034a5d4  jz      loc_18034B758
0x18034a5da  mov     r13b, bpl
0x18034a5dd  mov     [rsp+88h+var_54], esi
0x18034a5e1  and     r13b, 0F0h
0x18034a5e5  cmp     al, 40h ; '@'
0x18034a5e7  jz      loc_18034AEC4
0x18034a5ed  cmp     r13b, 0D0h
0x18034a5f1  jz      loc_18034AEC4
0x18034a5f7  cmp     bpl, 0F2h
0x18034a5fb  jz      loc_18034AF65
0x18034a601  cmp     bpl, 0F7h
0x18034a605  jz      loc_18034AF65
0x18034a60b  cmp     al, 20h ; ' '
0x18034a60d  jz      loc_18034AD12
0x18034a613  cmp     r13b, 0C0h
0x18034a617  jz      loc_18034AD12
0x18034a61d  cmp     bpl, 0F1h
0x18034a621  jz      loc_18034ADBA
0x18034a627  cmp     bpl, 0F6h
0x18034a62b  jz      loc_18034ADBA
0x18034a631  cmp     r13b, 0E0h
0x18034a635  jz      loc_18034ABCC
0x18034a63b  cmp     bpl, 0F8h
0x18034a63f  jz      loc_18034ABD2
0x18034a645  cmp     al, 80h
0x18034a647  jz      loc_18034AADC
0x18034a64d  cmp     bpl, 0F4h
0x18034a651  jz      loc_18034AAE2
0x18034a657  cmp     al, 60h ; '`'
0x18034a659  jz      loc_18034A9D6
0x18034a65f  cmp     bpl, 0F3h
0x18034a663  jz      loc_18034A9DC
0x18034a669  mov     r13, [rsp+88h+var_50]
0x18034a66e  mov     ecx, ebp
0x18034a670  sub     ecx, 0F9h
0x18034a676  jz      loc_18034A853
0x18034a67c  sub     ecx, 1
0x18034a67f  jz      short loc_18034A6E0
0x18034a681  sub     ecx, 3
0x18034a684  jz      short loc_18034A6B9
0x18034a686  cmp     ecx, 1
0x18034a689  jnz     loc_18034A9CE
0x18034a68f  lea     r8d, [rcx+1]; unsigned __int64
0x18034a693  mov     rdx, r13; unsigned __int8 *
0x18034a696  mov     rcx, rbx; unsigned __int8 *
0x18034a699  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034a6a0  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034a6a5  test    eax, eax
0x18034a6a7  jz      loc_18034B94C
0x18034a6ad  mov     [rbx], si
0x18034a6b0  add     rbx, 2
0x18034a6b4  jmp     loc_18034A9CE
0x18034a6b9  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034a6c0  mov     r8d, 2; unsigned __int64
0x18034a6c6  mov     rdx, r13; unsigned __int8 *
0x18034a6c9  mov     rcx, rbx; unsigned __int8 *
0x18034a6cc  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034a6d1  test    eax, eax
0x18034a6d3  jz      loc_18034B956
0x18034a6d9  mov     word ptr [rbx], 7FFFh
0x18034a6de  jmp     short loc_18034A6B0
0x18034a6e0  test    r14d, r14d
0x18034a6e3  jnz     loc_18034A7F3
0x18034a6e9  movzx   r14d, word ptr [rsp+88h+arg_20]
0x18034a6f2  lea     rax, aDecompressRead; "Decompress reads off end of buffer"
0x18034a6f9  mov     rdx, [rsp+88h+arg_8]; unsigned __int8 *
0x18034a701  mov     rbp, rbx
0x18034a704  sub     rbp, r14
0x18034a707  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x18034a70c  mov     rcx, rbp; unsigned __int8 *
0x18034a70f  mov     r9d, 2; unsigned __int64
0x18034a715  mov     r8, r13; unsigned __int8 *
0x18034a718  call    ?CheckReadNBytes2Ended@@YAHPEAE00_KPEBG@Z; CheckReadNBytes2Ended(uchar *,uchar *,uchar *,unsigned __int64,ushort const *)
0x18034a71d  test    eax, eax
0x18034a71f  jz      loc_18034B96A
0x18034a725  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034a72c  mov     r8d, 10h; unsigned __int64
0x18034a732  mov     rdx, r13; unsigned __int8 *
0x18034a735  mov     rcx, rbx; unsigned __int8 *
0x18034a738  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034a73d  test    eax, eax
0x18034a73f  jz      loc_18034B960
0x18034a745  movzx   ecx, byte ptr [rbp+1]
0x18034a749  movzx   eax, byte ptr [rbp+0]
0x18034a74d  shl     ax, 8
0x18034a751  or      cx, ax
0x18034a754  lea     rax, [rbx+2]
0x18034a758  sub     rax, r14
0x18034a75b  xor     cx, r15w
0x18034a75f  mov     [rbx+1], cl
0x18034a762  shr     cx, 8
0x18034a766  mov     [rbx], cl
0x18034a768  mov     cl, [rax]
0x18034a76a  mov     al, [rax+1]
0x18034a76d  mov     [rbx+3], al
0x18034a770  lea     rax, [rbx+4]
0x18034a774  mov     [rbx+2], cl
0x18034a777  sub     rax, r14
0x18034a77a  movzx   ecx, byte ptr [rax]
0x18034a77d  movzx   eax, byte ptr [rax+1]
0x18034a781  shl     cx, 8
0x18034a785  or      cx, ax
0x18034a788  lea     rax, [rbx+6]
0x18034a78c  sub     rax, r14
0x18034a78f  xor     cx, r15w
0x18034a793  mov     [rbx+5], cl
0x18034a796  shr     cx, 8
0x18034a79a  mov     [rbx+4], cl
0x18034a79d  mov     cl, [rax]
0x18034a79f  mov     al, [rax+1]
0x18034a7a2  mov     [rbx+7], al
0x18034a7a5  lea     rax, [rbx+8]
0x18034a7a9  mov     [rbx+6], cl
0x18034a7ac  sub     rax, r14
0x18034a7af  mov     cl, [rax]
0x18034a7b1  mov     al, [rax+1]
0x18034a7b4  mov     [rbx+9], al
0x18034a7b7  lea     rax, [rbx+0Ah]
0x18034a7bb  mov     [rbx+8], cl
0x18034a7be  sub     rax, r14
0x18034a7c1  mov     cl, [rax]
0x18034a7c3  mov     al, [rax+1]
0x18034a7c6  mov     [rbx+0Bh], al
0x18034a7c9  mov     [rbx+0Ah], cl
0x18034a7cc  add     rbx, 0Ch
0x18034a7d0  mov     rax, rbx
0x18034a7d3  sub     rax, r14
0x18034a7d6  mov     cl, [rax]
0x18034a7d8  mov     al, [rax+1]
0x18034a7db  mov     [rbx+1], al
0x18034a7de  mov     [rbx], cl
0x18034a7e0  lea     rcx, [rbx+2]
0x18034a7e4  mov     rax, rcx
0x18034a7e7  sub     rax, r14
0x18034a7ea  mov     dl, [rax+1]
0x18034a7ed  mov     al, [rax]
0x18034a7ef  mov     [rcx], al
0x18034a7f1  jmp     short loc_18034A843
0x18034a7f3  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034a7fa  mov     r8d, 10h; unsigned __int64
0x18034a800  mov     rdx, r13; unsigned __int8 *
0x18034a803  mov     rcx, rbx; unsigned __int8 *
0x18034a806  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034a80b  test    eax, eax
0x18034a80d  jz      loc_18034B974
0x18034a813  mov     [rbx+1], r15b
0x18034a817  movzx   eax, r15w
0x18034a81b  shr     ax, 8
0x18034a81f  mov     [rbx], al
0x18034a821  mov     [rbx+2], si
0x18034a825  mov     [rbx+5], r15b
0x18034a829  mov     [rbx+4], al
0x18034a82c  mov     [rbx+6], esi
0x18034a82f  mov     [rbx+0Ah], si
0x18034a833  add     rbx, 0Ch
0x18034a837  xor     dl, dl
0x18034a839  lea     rcx, [rbx+2]
0x18034a83d  mov     [rbx], si
0x18034a840  mov     [rcx], sil
0x18034a843  lea     rax, [rbx+4]
0x18034a847  mov     [rcx+1], dl
0x18034a84a  add     rbx, 4
0x18034a84e  jmp     loc_18034A9C6
0x18034a853  test    r14d, r14d
0x18034a856  jnz     loc_18034A983
0x18034a85c  movzx   r14d, word ptr [rsp+88h+arg_20]
0x18034a865  lea     rax, aDecompressRead; "Decompress reads off end of buffer"
0x18034a86c  mov     rdx, [rsp+88h+arg_8]; unsigned __int8 *
0x18034a874  mov     rbp, rbx
0x18034a877  sub     rbp, r14
0x18034a87a  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x18034a87f  mov     rcx, rbp; unsigned __int8 *
0x18034a882  mov     r9d, 2; unsigned __int64
0x18034a888  mov     r8, r13; unsigned __int8 *
0x18034a88b  call    ?CheckReadNBytes2Ended@@YAHPEAE00_KPEBG@Z; CheckReadNBytes2Ended(uchar *,uchar *,uchar *,unsigned __int64,ushort const *)
0x18034a890  test    eax, eax
0x18034a892  jz      loc_18034B988
0x18034a898  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034a89f  mov     r8d, 10h; unsigned __int64
0x18034a8a5  mov     rdx, r13; unsigned __int8 *
0x18034a8a8  mov     rcx, rbx; unsigned __int8 *
0x18034a8ab  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034a8b0  test    eax, eax
0x18034a8b2  jz      loc_18034B97E
0x18034a8b8  movzx   eax, byte ptr [rbp+0]
0x18034a8bc  lea     r8, [rbx+2]
0x18034a8c0  movzx   ecx, byte ptr [rbp+1]
0x18034a8c4  shl     ax, 8
0x18034a8c8  or      cx, ax
0x18034a8cb  mov     rax, r8
0x18034a8ce  sub     rax, r14
0x18034a8d1  xor     cx, r15w
0x18034a8d5  mov     [rbx+1], cl
0x18034a8d8  shr     cx, 8
0x18034a8dc  mov     [rbx], cl
0x18034a8de  movzx   ecx, byte ptr [rax+1]
0x18034a8e2  movzx   eax, byte ptr [rax]
0x18034a8e5  shl     ax, 8
0x18034a8e9  or      cx, ax
0x18034a8ec  lea     rax, [r8+2]
0x18034a8f0  sub     rax, r14
0x18034a8f3  xor     cx, r15w
0x18034a8f7  mov     [r8+1], cl
0x18034a8fb  shr     cx, 8
0x18034a8ff  mov     [r8], cl
0x18034a902  mov     cl, [rax]
0x18034a904  mov     al, [rax+1]
0x18034a907  mov     [r8+3], al
0x18034a90b  lea     rax, [r8+4]
0x18034a90f  mov     [r8+2], cl
0x18034a913  sub     rax, r14
0x18034a916  mov     cl, [rax]
0x18034a918  mov     al, [rax+1]
0x18034a91b  mov     [r8+5], al
0x18034a91f  lea     rax, [r8+6]
0x18034a923  mov     [r8+4], cl
0x18034a927  sub     rax, r14
0x18034a92a  mov     cl, [rax]
0x18034a92c  mov     al, [rax+1]
0x18034a92f  mov     [r8+7], al
0x18034a933  lea     rax, [r8+8]
0x18034a937  mov     [r8+6], cl
0x18034a93b  sub     rax, r14
0x18034a93e  mov     cl, [rax]
0x18034a940  mov     al, [rax+1]
0x18034a943  mov     [r8+9], al
0x18034a947  mov     [r8+8], cl
0x18034a94b  add     r8, 0Ah
0x18034a94f  mov     rax, r8
0x18034a952  mov     [rsp+88h+arg_0], r8
0x18034a95a  sub     rax, r14
0x18034a95d  lea     rbx, [r8+4]
0x18034a961  mov     cl, [rax]
0x18034a963  mov     al, [rax+1]
0x18034a966  mov     [r8+1], al
0x18034a96a  lea     rax, [r8+2]
0x18034a96e  mov     [r8], cl
0x18034a971  sub     rax, r14
0x18034a974  mov     cl, [rax]
0x18034a976  mov     al, [rax+1]
0x18034a979  mov     [r8+3], al
0x18034a97d  mov     [r8+2], cl
0x18034a981  jmp     short loc_18034A9CE
0x18034a983  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034a98a  mov     r8d, 10h; unsigned __int64
0x18034a990  mov     rdx, r13; unsigned __int8 *
  ... truncated ...
```
