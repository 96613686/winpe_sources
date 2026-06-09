# Planar::BDDecompressBitmap16(uchar *,uchar *,uint,uint,ushort)

- ea: `0x18003f894`
- end: `0x180040eeb`
- name: `?BDDecompressBitmap16@Planar@@YAJPEAE0IIG@Z`
- size: `5719`
- prototype: `__int64 __usercall@<rax>(Planar *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180350350`

## callees

- `0x18003f834`
- `0x18003f894`
- `0x1800415dc`
- `0x180045338`
- `0x180051830`
- `0x180373e00`

## string_xrefs

- `0x18003f924`: `Decompress reads one byte end of buffer`
- `0x18003fd84`: `Decompress reads one byte end of buffer`
- `0x18003fdab`: `Decompress reads one byte end of buffer`
- `0x18003fe93`: `Decompress reads one byte end of buffer`
- `0x18003feb8`: `Decompress reads one byte end of buffer`
- `0x18003ff83`: `Decompress reads one byte end of buffer`
- `0x18003ffa8`: `Decompress reads one byte end of buffer`
- `0x1800400ac`: `Decompress reads one byte end of buffer`
- `0x1800400db`: `Decompress reads one byte end of buffer`
- `0x18004011c`: `Decompress reads one byte end of buffer`
- `0x18004025e`: `Decompress reads one byte end of buffer`
- `0x180040285`: `Decompress reads one byte end of buffer`
- `0x1800402c5`: `Decompress reads one byte end of buffer`
- `0x180040360`: `Decompress reads one byte end of buffer`
- `0x18004069d`: `Decompress reads one byte end of buffer`
- `0x180040b0a`: `Decompress reads one byte end of buffer`
- `0x180040b31`: `Decompress reads one byte end of buffer`
- `0x18003fa15`: `Decompress write off end of buffer`
- `0x18003fa35`: `Decompress write off end of buffer`
- `0x18003faa1`: `Decompress write off end of buffer`
- `0x18003fb6f`: `Decompress write off end of buffer`
- `0x18003fc14`: `Decompress write off end of buffer`
- `0x18003fcff`: `Decompress write off end of buffer`
- `0x18003fdfc`: `Decompress write off end of buffer`
- `0x18003ff03`: `Decompress write off end of buffer`
- `0x18003fffc`: `Decompress write off end of buffer`
- `0x1800401b7`: `Decompress write off end of buffer`
- `0x1800403d2`: `Decompress write off end of buffer`
- `0x180040576`: `Decompress write off end of buffer`
- `0x180040712`: `Decompress write off end of buffer`
- `0x180040955`: `Decompress write off end of buffer`
- `0x180040b66`: `Decompress write off end of buffer`
- `0x180040beb`: `Decompress write off end of buffer`
- `0x180040c5d`: `Decompress write off end of buffer`
- `0x180040c99`: `Decompress write off end of buffer`
- `0x18003fa6e`: `Decompress reads off end of buffer`
- `0x18003fbe1`: `Decompress reads off end of buffer`
- `0x18003fd58`: `Decompress reads off end of buffer`
- `0x18003fdd0`: `Decompress reads off end of buffer`
- `0x18003fe68`: `Decompress reads off end of buffer`
- `0x18003fee4`: `Decompress reads off end of buffer`
- `0x18003ff58`: `Decompress reads off end of buffer`
- `0x18003ffcb`: `Decompress reads off end of buffer`
- `0x180040140`: `Decompress reads off end of buffer`
- `0x180040176`: `Decompress reads off end of buffer`
- `0x1800401f3`: `Decompress reads off end of buffer`
- `0x1800402eb`: `Decompress reads off end of buffer`
- `0x180040321`: `Decompress reads off end of buffer`
- `0x180040390`: `Decompress reads off end of buffer`
- `0x1800406d0`: `Decompress reads off end of buffer`
- `0x180040ade`: `Decompress reads off end of buffer`
- `0x180040b9c`: `Decompress reads off end of buffer`
- `0x180040e87`: `Decompress reads off end of buffer`

## pseudocode

```c
__int64 __fastcall Planar::BDDecompressBitmap16(
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
  unsigned __int8 v39; // bp
  int v40; // eax
  char v41; // al
  int v42; // ebp
  unsigned int v43; // r14d
  int v44; // ebp
  unsigned __int8 *v45; // rdi
  unsigned __int8 v46; // bp
  __int16 v47; // r14
  __int16 v48; // r14
  char v49; // r14
  int v50; // r14d
  char v51; // r14
  __int16 v52; // cx
  unsigned __int8 v53; // ah
  char v54; // r14
  int v55; // r14d
  unsigned int v56; // r14d
  char v57; // r14
  char v58; // bp
  unsigned __int16 v59; // cx
  _BYTE *v60; // rdx
  _BYTE *v61; // r8
  _BYTE *v62; // rbx
  unsigned __int16 v63; // cx
  _BYTE *v64; // rdx
  unsigned __int16 v65; // cx
  unsigned __int16 v66; // cx
  unsigned __int16 v67; // cx
  _BYTE *v68; // rdx
  unsigned __int16 v69; // cx
  _BYTE *v70; // rbx
  unsigned __int16 v71; // cx
  _BYTE *v72; // r8
  unsigned __int16 v73; // cx
  char v74; // dl
  unsigned __int8 v75; // al
  unsigned __int16 v76; // kr00_2
  unsigned __int8 v77; // r8
  unsigned __int8 v78; // r8
  unsigned __int8 v79; // r8
  unsigned __int8 v80; // r8
  char v81; // al
  char v82; // bp
  int v83; // eax
  unsigned __int16 v84; // cx
  unsigned int v85; // r14d
  unsigned __int8 *v86; // r8
  unsigned __int8 *v87; // rdx
  unsigned __int16 v88; // cx
  unsigned int v89; // r8d
  unsigned __int16 v90; // cx
  unsigned int v91; // r8d
  unsigned __int16 v92; // cx
  unsigned int v93; // r8d
  unsigned __int16 v94; // cx
  unsigned int v95; // r8d
  unsigned __int16 v96; // cx
  unsigned int v97; // r8d
  unsigned __int16 v98; // cx
  unsigned __int16 v99; // cx
  int v100; // eax
  unsigned __int8 v101; // dl
  unsigned __int8 *v102; // r8
  unsigned __int8 v103; // al
  unsigned int v104; // r14d
  unsigned __int8 *v105; // rax
  unsigned __int16 v106; // kr02_2
  unsigned int v107; // r9d
  unsigned __int8 v108; // r8
  unsigned int v109; // r9d
  unsigned __int8 v110; // r8
  unsigned int v111; // r9d
  unsigned __int8 v112; // r8
  unsigned int v113; // r9d
  unsigned __int8 v114; // r8
  unsigned __int8 *v115; // r8
  unsigned int v116; // r9d
  unsigned __int8 v117; // al
  int v118; // r14d
  char v119; // r14
  __int16 v120; // cx
  unsigned __int8 *v121; // r8
  char v122; // al
  unsigned __int8 v123; // cl
  int v125; // [rsp+40h] [rbp-58h]
  int v126; // [rsp+44h] [rbp-54h]
  unsigned __int8 *v127; // [rsp+48h] [rbp-50h]
  __int16 v128; // [rsp+A0h] [rbp+8h]
  unsigned __int8 v130; // [rsp+B0h] [rbp+18h]
  unsigned __int8 v131; // [rsp+B0h] [rbp+18h]
  unsigned __int8 v132; // [rsp+B8h] [rbp+20h]

  v5 = 0;
  v6 = (unsigned __int8 *)this + (unsigned int)a3;
  v7 = &a2[a4];
  v126 = 0;
  v8 = (int)a2;
  v127 = v7;
  v9 = 1;
  v10 = (unsigned __int8 *)this;
  v125 = 1;
  v11 = -1;
  v12 = a2;
  while ( v10 < v6 )
  {
    if ( v9 && (int)v12 - v8 >= (unsigned int)a5 )
    {
      v9 = 0;
      v126 = 0;
      v125 = 0;
    }
    if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
      return (unsigned int)-1626586815;
    v13 = *v10;
    v14 = *v10 & 0xE0;
    if ( !v14 )
    {
      if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
        return (unsigned int)-1626586802;
      v119 = *v10++;
      v118 = v119 & 0x1F;
      if ( !v118 )
      {
        if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586802;
        v118 = *v10++ + 32;
      }
LABEL_251:
      if ( v125 )
      {
        if ( v126 )
        {
          if ( !(unsigned int)CheckWriteNBytes(v12, v7, 2u, L"Decompress write off end of buffer") )
            return (unsigned int)-1626586766;
          v12[1] = v11;
          *v12 = HIBYTE(v11);
          v12 += 2;
          --v118;
        }
        if ( !(unsigned int)CheckWriteNBytes(v12, v7, (unsigned int)(2 * v118), L"Decompress write off end of buffer") )
          return (unsigned int)-1626586761;
        for ( ; v118; --v118 )
        {
          *(_WORD *)v12 = 0;
          v12 += 2;
        }
      }
      else
      {
        if ( v126 )
        {
          if ( !(unsigned int)CheckWriteNBytes(v12, v7, 2u, L"Decompress write off end of buffer") )
            return (unsigned int)-1626586788;
          if ( !(unsigned int)CheckReadNBytes2Ended(&v12[-a5], a2, v7, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586787;
          v120 = v11 ^ _byteswap_ushort(*(_WORD *)&v12[-a5]);
          v12[1] = v120;
          *v12 = HIBYTE(v120);
          v12 += 2;
          --v118;
        }
        if ( !(unsigned int)CheckWriteNBytes(v12, v7, (unsigned int)(2 * v118), L"Decompress write off end of buffer") )
          return (unsigned int)-1626586779;
        while ( v118 )
        {
          v121 = &v12[-a5];
          if ( v121 > v7 )
          {
            v122 = (char)a2;
LABEL_310:
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              WPP_SF_SqqqI(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                14,
                (_DWORD)v121,
                (unsigned int)L"Decompress reads off end of buffer",
                (_BYTE)v12 - a5,
                v122,
                (char)v7,
                2);
            }
            return (unsigned int)-1626586775;
          }
          v122 = (char)a2;
          if ( (unsigned int)((_DWORD)v7 - (_DWORD)v121) < 2 || v121 < a2 )
            goto LABEL_310;
          v123 = *v121;
          --v118;
          v12[1] = v121[1];
          *v12 = v123;
          v12 += 2;
        }
      }
      v126 = 1;
LABEL_5:
      v8 = (int)a2;
      goto LABEL_6;
    }
    if ( (_BYTE)v13 == 0xF0 )
    {
      if ( !(unsigned int)CheckReadNBytes(v10 + 1, v6, 2u, L"Decompress reads off end of buffer") )
        return (unsigned int)-1626586798;
      v118 = *(unsigned __int16 *)(v10 + 1);
      v10 += 3;
      goto LABEL_251;
    }
    v126 = 0;
    v15 = v13 & 0xF0;
    if ( v14 == 64 || v15 == -48 )
    {
      if ( (_BYTE)v13 == 0xF2 || (_BYTE)v13 == 0xF7 )
      {
LABEL_124:
        if ( !(unsigned int)CheckReadNBytes(v10 + 1, v6, 2u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586727;
        v56 = *(unsigned __int16 *)(v10 + 1);
        v10 += 3;
        goto LABEL_126;
      }
      if ( v14 == 64 )
      {
        if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586719;
        v54 = *v10++;
        v55 = v54 & 0x1F;
        if ( !v55 )
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586719;
LABEL_123:
          v56 = *v10++ + 1;
          goto LABEL_126;
        }
      }
      else
      {
        if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586715;
        v57 = *v10++;
        v55 = v57 & 0xF;
        if ( !v55 )
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586715;
          goto LABEL_123;
        }
      }
      v56 = 8 * v55;
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
      while ( v56 > 8 )
      {
        if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586691;
        v58 = *v10;
        if ( v125 )
        {
          if ( !(unsigned int)CheckWriteNBytes(v12, v127, 0x10u, L"Decompress write off end of buffer") )
            return (unsigned int)-1626586679;
          v74 = v11;
          if ( (v58 & 1) != 0 )
          {
            *v12 = HIBYTE(v11);
            v75 = v11;
          }
          else
          {
            *v12 = 0;
            v75 = 0;
          }
          v12[1] = v75;
          if ( (v58 & 2) != 0 )
            v76 = v11;
          else
            v76 = 0;
          v12[2] = HIBYTE(v76);
          v12[3] = v76;
          if ( (v58 & 4) != 0 )
          {
            v12[4] = HIBYTE(v11);
            v77 = v11;
          }
          else
          {
            v12[4] = 0;
            v77 = 0;
          }
          v12[5] = v77;
          if ( (v58 & 8) != 0 )
          {
            v12[6] = HIBYTE(v11);
            v78 = v11;
          }
          else
          {
            v12[6] = 0;
            v78 = 0;
          }
          v12[7] = v78;
          if ( (v58 & 0x10) != 0 )
          {
            v12[8] = HIBYTE(v11);
            v79 = v11;
          }
          else
          {
            v12[8] = 0;
            v79 = 0;
          }
          v12[9] = v79;
          if ( (v58 & 0x20) != 0 )
          {
            v12[10] = HIBYTE(v11);
            v80 = v11;
          }
          else
          {
            v12[10] = 0;
            v80 = 0;
          }
          v12[11] = v80;
          v70 = v12 + 12;
          if ( (v58 & 0x40) != 0 )
          {
            *v70 = HIBYTE(v11);
            v81 = v11;
          }
          else
          {
            *v70 = 0;
            v81 = 0;
          }
          v70[1] = v81;
          v72 = v70 + 2;
          if ( v58 >= 0 )
          {
            *v72 = 0;
            v74 = 0;
          }
          else
          {
            *v72 = HIBYTE(v11);
          }
          LOBYTE(v73) = v74;
        }
        else
        {
          if ( !(unsigned int)CheckReadNBytes2Ended(&v12[-a5], a2, v127, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586687;
          if ( !(unsigned int)CheckWriteNBytes(v12, v127, 0x10u, L"Decompress write off end of buffer") )
            return (unsigned int)-1626586683;
          v59 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
          if ( (v58 & 1) != 0 )
            v59 ^= v11;
          v60 = v12 + 2;
          v61 = v60;
          *v12 = HIBYTE(v59);
          v12[1] = v59;
          v62 = v12 + 2;
          v63 = _byteswap_ushort(*(_WORD *)&v60[-a5]);
          if ( (v58 & 2) != 0 )
            v63 ^= v11;
          *v60 = HIBYTE(v63);
          v64 = v60 + 2;
          v61[1] = v63;
          v65 = _byteswap_ushort(*(_WORD *)&v62[-a5 + 2]);
          if ( (v58 & 4) != 0 )
            v65 ^= v11;
          *v64 = HIBYTE(v65);
          v62[3] = v65;
          v66 = _byteswap_ushort(*(_WORD *)&v62[-a5 + 4]);
          if ( (v58 & 8) != 0 )
            v66 ^= v11;
          v62[4] = HIBYTE(v66);
          v62[5] = v66;
          v67 = _byteswap_ushort(*(_WORD *)&v62[-a5 + 6]);
          if ( (v58 & 0x10) != 0 )
            v67 ^= v11;
          v62[6] = HIBYTE(v67);
          v62[7] = v67;
          v68 = v62 + 8;
          v69 = _byteswap_ushort(*(_WORD *)&v62[-a5 + 8]);
          if ( (v58 & 0x20) != 0 )
            v69 ^= v11;
          v70 = v62 + 10;
          *v68 = HIBYTE(v69);
          v68[1] = v69;
          v71 = _byteswap_ushort(*(_WORD *)&v70[-a5]);
          if ( (v58 & 0x40) != 0 )
            v71 ^= v11;
          v72 = v70 + 2;
          *v70 = HIBYTE(v71);
          v70[1] = v71;
          v73 = _byteswap_ushort(*(_WORD *)&v70[-a5 + 2]);
          if ( v58 < 0 )
            v73 ^= v11;
          *v72 = HIBYTE(v73);
        }
        v72[1] = v73;
        ++v10;
        v56 -= 8;
        v12 = v70 + 4;
      }
      if ( !v56 )
      {
        v7 = v127;
        goto LABEL_5;
      }
      if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
        return (unsigned int)-1626586673;
      v82 = *v10++;
      if ( !v125 )
      {
        if ( !(unsigned int)CheckReadNBytes2Ended(&v12[-a5], a2, v127, 2u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586669;
        v83 = 8;
        if ( v56 < 8 )
          v83 = v56;
        if ( !(unsigned int)CheckWriteNBytes(v12, v127, (unsigned int)(2 * v83), L"Decompress write off end of buffer") )
          return (unsigned int)-1626586665;
        v84 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
        if ( (v82 & 1) != 0 )
          v84 ^= v11;
        *v12 = HIBYTE(v84);
        v12[1] = v84;
        v12 += 2;
        v8 = (int)a2;
        v85 = v56 - 1;
        if ( !v85 )
        {
          v7 = v127;
          goto LABEL_6;
        }
        v86 = v12;
        v87 = v12;
        v88 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
        if ( (v82 & 2) != 0 )
          v88 ^= v11;
        *v12 = HIBYTE(v88);
        v12 += 2;
        v86[1] = v88;
        v89 = v85 - 1;
        v8 = (int)a2;
        v9 = 0;
        if ( !v89 )
          goto LABEL_3;
        v90 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
        if ( (v82 & 4) != 0 )
          v90 ^= v11;
        *v12 = HIBYTE(v90);
        v87[3] = v90;
        v12 = v87 + 4;
        v8 = (int)a2;
        v91 = v89 - 1;
        if ( !v91 )
          goto LABEL_3;
        v92 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
        if ( (v82 & 8) != 0 )
          v92 ^= v11;
        *v12 = HIBYTE(v92);
        v87[5] = v92;
        v12 = v87 + 6;
        v8 = (int)a2;
        v93 = v91 - 1;
        if ( !v93 )
          goto LABEL_3;
        v94 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
        if ( (v82 & 0x10) != 0 )
          v94 ^= v11;
        *v12 = HIBYTE(v94);
        v87[7] = v94;
        v12 = v87 + 8;
        v8 = (int)a2;
        v95 = v93 - 1;
        if ( !v95 )
          goto LABEL_3;
        v96 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
        if ( (v82 & 0x20) != 0 )
          v96 ^= v11;
        *v12 = HIBYTE(v96);
        v87[9] = v96;
        v12 = v87 + 10;
        v8 = (int)a2;
        v97 = v95 - 1;
        if ( !v97 )
          goto LABEL_3;
        v98 = _byteswap_ushort(*(_WORD *)&v87[-a5 + 10]);
        if ( (v82 & 0x40) != 0 )
          v98 ^= v11;
        v12 = v87 + 12;
        v87[10] = HIBYTE(v98);
        v87[11] = v98;
        v8 = (int)a2;
        if ( v97 == 1 )
        {
LABEL_3:
          v7 = v127;
          continue;
        }
        v99 = _byteswap_ushort(*(_WORD *)&v12[-a5]);
        if ( v82 < 0 )
          v99 ^= v11;
        v7 = v127;
        *v12 = HIBYTE(v99);
        v87[13] = v99;
        v12 = v87 + 14;
        goto LABEL_74;
      }
      v7 = v127;
      v100 = 8;
      if ( v56 < 8 )
        v100 = v56;
      if ( !(unsigned int)CheckWriteNBytes(v12, v127, (unsigned int)(2 * v100), L"Decompress write off end of buffer") )
        return (unsigned int)-1626586661;
      v101 = v11;
      v102 = v12;
      if ( (v82 & 1) != 0 )
      {
        *v12 = HIBYTE(v11);
        v103 = v11;
      }
      else
      {
        *v12 = 0;
        v103 = 0;
      }
      v12[1] = v103;
      v12 += 2;
      v8 = (int)a2;
      v104 = v56 - 1;
      if ( !v104 )
        goto LABEL_6;
      v105 = v102 + 2;
      if ( (v82 & 2) != 0 )
        v106 = v11;
      else
        v106 = 0;
      *v12 = HIBYTE(v106);
      v12 += 2;
      v102[3] = v106;
      v107 = v104 - 1;
      v9 = v125;
      if ( !v107 )
        goto LABEL_74;
      if ( (v82 & 4) != 0 )
      {
        *v12 = HIBYTE(v11);
        v108 = v11;
      }
      else
      {
        *v12 = 0;
        v108 = 0;
      }
      v105[3] = v108;
      v12 = v105 + 4;
      v109 = v107 - 1;
      if ( !v109 )
        goto LABEL_74;
      if ( (v82 & 8) != 0 )
      {
        *v12 = HIBYTE(v11);
        v110 = v11;
      }
      else
      {
        *v12 = 0;
        v110 = 0;
      }
      v105[5] = v110;
      v12 = v105 + 6;
      v111 = v109 - 1;
      if ( !v111 )
        goto LABEL_74;
      if ( (v82 & 0x10) != 0 )
      {
        *v12 = HIBYTE(v11);
        v112 = v11;
      }
      else
      {
        *v12 = 0;
        v112 = 0;
      }
      v105[7] = v112;
      v12 = v105 + 8;
      v113 = v111 - 1;
      if ( v113 )
      {
        if ( (v82 & 0x20) != 0 )
        {
          *v12 = HIBYTE(v11);
          v114 = v11;
        }
        else
        {
          *v12 = 0;
          v114 = 0;
        }
        v105[9] = v114;
        v115 = v105 + 10;
        v8 = (int)a2;
        v12 = v115;
        v116 = v113 - 1;
        if ( v116 )
        {
          if ( (v82 & 0x40) != 0 )
          {
            *v115 = HIBYTE(v11);
            v117 = v11;
          }
          else
          {
            *v115 = 0;
            v117 = 0;
          }
          v115[1] = v117;
          v12 = v115 + 2;
          v8 = (int)a2;
          if ( v116 != 1 )
          {
            if ( v82 >= 0 )
            {
              *v12 = 0;
              v101 = 0;
            }
            else
            {
              *v12 = HIBYTE(v11);
            }
            v115[3] = v101;
            v12 = v115 + 4;
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
          v50 = *(unsigned __int16 *)(v10 + 1);
          v10 += 3;
        }
        else if ( v14 == 32 )
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586635;
          v49 = *v10++;
          v50 = v49 & 0x1F;
          if ( !v50 )
          {
            if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586635;
            v50 = *v10 + 32;
            goto LABEL_94;
          }
        }
        else
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586631;
          v51 = *v10++;
          v50 = v51 & 0xF;
          if ( !v50 )
          {
            if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586631;
            v50 = *v10 + 16;
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
        v7 = v127;
        if ( !(unsigned int)CheckWriteNBytes(v12, v127, (unsigned int)(2 * v50), L"Decompress write off end of buffer") )
          return (unsigned int)-1626586611;
        while ( v50 )
        {
          if ( v125 )
          {
            v53 = HIBYTE(v11);
            LOBYTE(v52) = v11;
          }
          else
          {
            if ( !(unsigned int)CheckReadNBytes2Ended(&v12[-a5], a2, v127, 2u, L"Decompress reads off end of buffer") )
              return (unsigned int)-1626586606;
            v52 = v11 ^ _byteswap_ushort(*(_WORD *)&v12[-a5]);
            v53 = HIBYTE(v52);
          }
          --v50;
          *v12 = v53;
          v12[1] = v52;
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
          v44 = *(unsigned __int16 *)(v10 + 1);
          v45 = v10 + 3;
        }
        else
        {
          if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586578;
          v46 = *v10;
          v45 = v10 + 1;
          v44 = v46 & 0xF;
          if ( !v44 )
          {
            if ( !(unsigned int)CheckReadOneByte(v45, v6, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586578;
            v44 = *v45++ + 16;
          }
        }
        if ( !(unsigned int)CheckReadNBytes(v45, v6, 4u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586574;
        v7 = v127;
        v47 = *v45;
        v128 = v45[1];
        v131 = v45[2];
        v132 = v45[3];
        if ( !(unsigned int)CheckWriteNBytes(v12, v127, (unsigned int)(4 * v44), L"Decompress write off end of buffer") )
          return (unsigned int)-1626586568;
        v10 = v45 + 4;
        v48 = v128 | (v47 << 8);
        v8 = (int)a2;
        if ( v44 )
        {
          do
          {
            v12[1] = v48;
            *v12 = HIBYTE(v48);
            v12[3] = v132;
            v12[2] = v131;
            v12 += 4;
            --v44;
          }
          while ( v44 );
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
          v41 = *v10++;
          v40 = v41 & 0x1F;
          if ( !v40 )
          {
            if ( !(unsigned int)CheckReadOneByte(v10, v6, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586542;
            v40 = *v10++ + 32;
          }
          goto LABEL_70;
        }
LABEL_64:
        if ( !(unsigned int)CheckReadNBytes(v10 + 1, v6, 2u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586548;
        v40 = *(unsigned __int16 *)(v10 + 1);
        v10 += 3;
LABEL_70:
        v42 = 2 * v40;
        v43 = 2 * v40;
        if ( !(unsigned int)CheckReadNBytes(v10, v6, (unsigned int)(2 * v40), L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586534;
        v7 = v127;
        if ( !(unsigned int)CheckWriteNBytes(v12, v127, v43, L"Decompress write off end of buffer") )
          return (unsigned int)-1626586533;
        v8 = (int)a2;
        v9 = v125;
        if ( v42 )
        {
          do
          {
            --v42;
            *v12++ = *v10++;
          }
          while ( v42 > 0 );
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
            v7 = v127;
            switch ( v13 )
            {
              case 249:
                if ( v9 )
                {
                  if ( !(unsigned int)CheckWriteNBytes(v12, v127, 0x10u, L"Decompress write off end of buffer") )
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
                                        v127,
                                        2u,
                                        L"Decompress reads off end of buffer") )
                    return (unsigned int)-1626586466;
                  if ( !(unsigned int)CheckWriteNBytes(v12, v127, 0x10u, L"Decompress write off end of buffer") )
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
                  if ( !(unsigned int)CheckWriteNBytes(v12, v127, 0x10u, L"Decompress write off end of buffer") )
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
                                        v127,
                                        2u,
                                        L"Decompress reads off end of buffer") )
                    return (unsigned int)-1626586451;
                  if ( !(unsigned int)CheckWriteNBytes(v12, v127, 0x10u, L"Decompress write off end of buffer") )
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
                if ( !(unsigned int)CheckWriteNBytes(v12, v127, 2u, L"Decompress write off end of buffer") )
                  return (unsigned int)-1626586479;
                *(_WORD *)v12 = -1;
LABEL_34:
                v12 += 2;
                break;
              case 254:
                if ( !(unsigned int)CheckWriteNBytes(v12, v127, 2u, L"Decompress write off end of buffer") )
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
        v7 = v127;
        v39 = *v37;
        v130 = v37[1];
        if ( !(unsigned int)CheckWriteNBytes(v12, v127, (unsigned int)(2 * v36), L"Decompress write off end of buffer") )
          return (unsigned int)-1626586502;
        v10 = v37 + 2;
        v8 = (int)a2;
        if ( v36 )
        {
          do
          {
            v12[1] = v130;
            *v12 = v39;
            v12 += 2;
            --v36;
          }
          while ( v36 );
          goto LABEL_5;
        }
LABEL_6:
        v9 = v125;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18003f894  mov     [rsp+arg_8], rdx
0x18003f899  push    rbx
0x18003f89a  push    rbp
0x18003f89b  push    rsi
0x18003f89c  push    rdi
0x18003f89d  push    r12
0x18003f89f  push    r13
0x18003f8a1  push    r14
0x18003f8a3  push    r15
0x18003f8a5  sub     rsp, 58h
0x18003f8a9  xor     esi, esi
0x18003f8ab  mov     r12d, r8d
0x18003f8ae  add     r12, rcx
0x18003f8b1  mov     r13d, r9d
0x18003f8b4  add     r13, rdx
0x18003f8b7  mov     [rsp+98h+var_54], esi
0x18003f8bb  mov     rax, rdx
0x18003f8be  mov     [rsp+98h+var_50], r13
0x18003f8c3  lea     r14d, [rsi+1]
0x18003f8c7  mov     rdi, rcx
0x18003f8ca  mov     [rsp+98h+var_58], r14d
0x18003f8cf  mov     r15d, 0FFFFh
0x18003f8d5  mov     rbx, rdx
0x18003f8d8  jmp     short loc_18003F8FA
0x18003f8da  mov     r13, [rsp+98h+var_50]
0x18003f8df  jmp     short loc_18003F8F5
0x18003f8e1  mov     r13, [rsp+98h+var_50]
0x18003f8e6  jmp     short loc_18003F8FA
0x18003f8e8  mov     r13, [rsp+98h+var_50]
0x18003f8ed  mov     rax, [rsp+98h+arg_8]
0x18003f8f5  mov     r14d, [rsp+98h+var_58]
0x18003f8fa  cmp     rdi, r12
0x18003f8fd  jnb     loc_180040ED8
0x18003f903  test    r14d, r14d
0x18003f906  jz      short loc_18003F924
0x18003f908  mov     ecx, ebx
0x18003f90a  sub     ecx, eax
0x18003f90c  movzx   eax, word ptr [rsp+98h+arg_20]
0x18003f914  cmp     ecx, eax
0x18003f916  jb      short loc_18003F924
0x18003f918  xor     r14d, r14d
0x18003f91b  mov     [rsp+98h+var_54], esi
0x18003f91f  mov     [rsp+98h+var_58], r14d
0x18003f924  lea     r8, aDecompressRead_1; "Decompress reads one byte end of buffer"
0x18003f92b  mov     rdx, r12; unsigned __int8 *
0x18003f92e  mov     rcx, rdi; unsigned __int8 *
0x18003f931  call    ?CheckReadOneByte@@YAHPEAE0PEBG@Z; CheckReadOneByte(uchar *,uchar *,ushort const *)
0x18003f936  test    eax, eax
0x18003f938  jz      loc_180040ED3
0x18003f93e  movzx   ebp, byte ptr [rdi]
0x18003f941  mov     al, bpl
0x18003f944  and     al, 0E0h
0x18003f946  jz      loc_180040B0A
0x18003f94c  cmp     bpl, 0F0h
0x18003f950  jz      loc_180040ADE
0x18003f956  mov     r13b, bpl
0x18003f959  mov     [rsp+98h+var_54], esi
0x18003f95d  and     r13b, 0F0h
0x18003f961  cmp     al, 40h ; '@'
0x18003f963  jz      loc_18004024A
0x18003f969  cmp     r13b, 0D0h
0x18003f96d  jz      loc_18004024A
0x18003f973  cmp     bpl, 0F2h
0x18003f977  jz      loc_1800402EB
0x18003f97d  cmp     bpl, 0F7h
0x18003f981  jz      loc_1800402EB
0x18003f987  cmp     al, 20h ; ' '
0x18003f989  jz      loc_180040098
0x18003f98f  cmp     r13b, 0C0h
0x18003f993  jz      loc_180040098
0x18003f999  cmp     bpl, 0F1h
0x18003f99d  jz      loc_180040140
0x18003f9a3  cmp     bpl, 0F6h
0x18003f9a7  jz      loc_180040140
0x18003f9ad  cmp     r13b, 0E0h
0x18003f9b1  jz      loc_18003FF52
0x18003f9b7  cmp     bpl, 0F8h
0x18003f9bb  jz      loc_18003FF58
0x18003f9c1  cmp     al, 80h
0x18003f9c3  jz      loc_18003FE62
0x18003f9c9  cmp     bpl, 0F4h
0x18003f9cd  jz      loc_18003FE68
0x18003f9d3  cmp     al, 60h ; '`'
0x18003f9d5  jz      loc_18003FD52
0x18003f9db  cmp     bpl, 0F3h
0x18003f9df  jz      loc_18003FD58
0x18003f9e5  mov     r13, [rsp+98h+var_50]
0x18003f9ea  mov     ecx, ebp
0x18003f9ec  sub     ecx, 0F9h
0x18003f9f2  jz      loc_18003FBCF
0x18003f9f8  sub     ecx, 1
0x18003f9fb  jz      short loc_18003FA5C
0x18003f9fd  sub     ecx, 3
0x18003fa00  jz      short loc_18003FA35
0x18003fa02  cmp     ecx, 1
0x18003fa05  jnz     loc_18003FD4A
0x18003fa0b  lea     r8d, [rcx+1]; unsigned __int64
0x18003fa0f  mov     rdx, r13; unsigned __int8 *
0x18003fa12  mov     rcx, rbx; unsigned __int8 *
0x18003fa15  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18003fa1c  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18003fa21  test    eax, eax
0x18003fa23  jz      loc_180040CCF
0x18003fa29  mov     [rbx], si
0x18003fa2c  add     rbx, 2
0x18003fa30  jmp     loc_18003FD4A
0x18003fa35  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18003fa3c  mov     r8d, 2; unsigned __int64
0x18003fa42  mov     rdx, r13; unsigned __int8 *
0x18003fa45  mov     rcx, rbx; unsigned __int8 *
0x18003fa48  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18003fa4d  test    eax, eax
0x18003fa4f  jz      loc_180040CD9
0x18003fa55  mov     word ptr [rbx], 0FFFFh
0x18003fa5a  jmp     short loc_18003FA2C
0x18003fa5c  test    r14d, r14d
0x18003fa5f  jnz     loc_18003FB6F
0x18003fa65  movzx   r14d, word ptr [rsp+98h+arg_20]
0x18003fa6e  lea     rax, aDecompressRead; "Decompress reads off end of buffer"
0x18003fa75  mov     rdx, [rsp+98h+arg_8]; unsigned __int8 *
0x18003fa7d  mov     rbp, rbx
0x18003fa80  sub     rbp, r14
0x18003fa83  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x18003fa88  mov     rcx, rbp; unsigned __int8 *
0x18003fa8b  mov     r9d, 2; unsigned __int64
0x18003fa91  mov     r8, r13; unsigned __int8 *
0x18003fa94  call    ?CheckReadNBytes2Ended@@YAHPEAE00_KPEBG@Z; CheckReadNBytes2Ended(uchar *,uchar *,uchar *,unsigned __int64,ushort const *)
0x18003fa99  test    eax, eax
0x18003fa9b  jz      loc_180040CED
0x18003faa1  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18003faa8  mov     r8d, 10h; unsigned __int64
0x18003faae  mov     rdx, r13; unsigned __int8 *
0x18003fab1  mov     rcx, rbx; unsigned __int8 *
0x18003fab4  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18003fab9  test    eax, eax
0x18003fabb  jz      loc_180040CE3
0x18003fac1  movzx   ecx, byte ptr [rbp+1]
0x18003fac5  movzx   eax, byte ptr [rbp+0]
0x18003fac9  shl     ax, 8
0x18003facd  or      cx, ax
0x18003fad0  lea     rax, [rbx+2]
0x18003fad4  sub     rax, r14
0x18003fad7  xor     cx, r15w
0x18003fadb  mov     [rbx+1], cl
0x18003fade  shr     cx, 8
0x18003fae2  mov     [rbx], cl
0x18003fae4  mov     cl, [rax]
0x18003fae6  mov     al, [rax+1]
0x18003fae9  mov     [rbx+3], al
0x18003faec  lea     rax, [rbx+4]
0x18003faf0  mov     [rbx+2], cl
0x18003faf3  sub     rax, r14
0x18003faf6  movzx   ecx, byte ptr [rax]
0x18003faf9  movzx   eax, byte ptr [rax+1]
0x18003fafd  shl     cx, 8
0x18003fb01  or      cx, ax
0x18003fb04  lea     rax, [rbx+6]
0x18003fb08  sub     rax, r14
0x18003fb0b  xor     cx, r15w
0x18003fb0f  mov     [rbx+5], cl
0x18003fb12  shr     cx, 8
0x18003fb16  mov     [rbx+4], cl
0x18003fb19  mov     cl, [rax]
0x18003fb1b  mov     al, [rax+1]
0x18003fb1e  mov     [rbx+7], al
0x18003fb21  lea     rax, [rbx+8]
0x18003fb25  mov     [rbx+6], cl
0x18003fb28  sub     rax, r14
0x18003fb2b  mov     cl, [rax]
0x18003fb2d  mov     al, [rax+1]
0x18003fb30  mov     [rbx+9], al
0x18003fb33  lea     rax, [rbx+0Ah]
0x18003fb37  mov     [rbx+8], cl
0x18003fb3a  sub     rax, r14
0x18003fb3d  mov     cl, [rax]
0x18003fb3f  mov     al, [rax+1]
0x18003fb42  mov     [rbx+0Bh], al
0x18003fb45  mov     [rbx+0Ah], cl
0x18003fb48  add     rbx, 0Ch
0x18003fb4c  mov     rax, rbx
0x18003fb4f  sub     rax, r14
0x18003fb52  mov     cl, [rax]
0x18003fb54  mov     al, [rax+1]
0x18003fb57  mov     [rbx+1], al
0x18003fb5a  mov     [rbx], cl
0x18003fb5c  lea     rcx, [rbx+2]
0x18003fb60  mov     rax, rcx
0x18003fb63  sub     rax, r14
0x18003fb66  mov     dl, [rax+1]
0x18003fb69  mov     al, [rax]
0x18003fb6b  mov     [rcx], al
0x18003fb6d  jmp     short loc_18003FBBF
0x18003fb6f  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18003fb76  mov     r8d, 10h; unsigned __int64
0x18003fb7c  mov     rdx, r13; unsigned __int8 *
0x18003fb7f  mov     rcx, rbx; unsigned __int8 *
0x18003fb82  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18003fb87  test    eax, eax
0x18003fb89  jz      loc_180040CF7
0x18003fb8f  mov     [rbx+1], r15b
0x18003fb93  movzx   eax, r15w
0x18003fb97  shr     ax, 8
0x18003fb9b  mov     [rbx], al
0x18003fb9d  mov     [rbx+2], si
0x18003fba1  mov     [rbx+5], r15b
0x18003fba5  mov     [rbx+4], al
0x18003fba8  mov     [rbx+6], esi
0x18003fbab  mov     [rbx+0Ah], si
0x18003fbaf  add     rbx, 0Ch
0x18003fbb3  xor     dl, dl
0x18003fbb5  lea     rcx, [rbx+2]
0x18003fbb9  mov     [rbx], si
0x18003fbbc  mov     [rcx], sil
0x18003fbbf  lea     rax, [rbx+4]
0x18003fbc3  mov     [rcx+1], dl
0x18003fbc6  add     rbx, 4
0x18003fbca  jmp     loc_18003FD42
0x18003fbcf  test    r14d, r14d
0x18003fbd2  jnz     loc_18003FCFF
0x18003fbd8  movzx   r14d, word ptr [rsp+98h+arg_20]
0x18003fbe1  lea     rax, aDecompressRead; "Decompress reads off end of buffer"
0x18003fbe8  mov     rdx, [rsp+98h+arg_8]; unsigned __int8 *
0x18003fbf0  mov     rbp, rbx
0x18003fbf3  sub     rbp, r14
0x18003fbf6  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x18003fbfb  mov     rcx, rbp; unsigned __int8 *
0x18003fbfe  mov     r9d, 2; unsigned __int64
0x18003fc04  mov     r8, r13; unsigned __int8 *
0x18003fc07  call    ?CheckReadNBytes2Ended@@YAHPEAE00_KPEBG@Z; CheckReadNBytes2Ended(uchar *,uchar *,uchar *,unsigned __int64,ushort const *)
0x18003fc0c  test    eax, eax
0x18003fc0e  jz      loc_180040D0B
0x18003fc14  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18003fc1b  mov     r8d, 10h; unsigned __int64
0x18003fc21  mov     rdx, r13; unsigned __int8 *
0x18003fc24  mov     rcx, rbx; unsigned __int8 *
0x18003fc27  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18003fc2c  test    eax, eax
0x18003fc2e  jz      loc_180040D01
0x18003fc34  movzx   eax, byte ptr [rbp+0]
0x18003fc38  lea     r8, [rbx+2]
0x18003fc3c  movzx   ecx, byte ptr [rbp+1]
0x18003fc40  shl     ax, 8
0x18003fc44  or      cx, ax
0x18003fc47  mov     rax, r8
0x18003fc4a  sub     rax, r14
0x18003fc4d  xor     cx, r15w
0x18003fc51  mov     [rbx+1], cl
0x18003fc54  shr     cx, 8
0x18003fc58  mov     [rbx], cl
0x18003fc5a  movzx   ecx, byte ptr [rax+1]
0x18003fc5e  movzx   eax, byte ptr [rax]
0x18003fc61  shl     ax, 8
0x18003fc65  or      cx, ax
0x18003fc68  lea     rax, [r8+2]
0x18003fc6c  sub     rax, r14
0x18003fc6f  xor     cx, r15w
0x18003fc73  mov     [r8+1], cl
0x18003fc77  shr     cx, 8
0x18003fc7b  mov     [r8], cl
0x18003fc7e  mov     cl, [rax]
0x18003fc80  mov     al, [rax+1]
0x18003fc83  mov     [r8+3], al
0x18003fc87  lea     rax, [r8+4]
0x18003fc8b  mov     [r8+2], cl
0x18003fc8f  sub     rax, r14
0x18003fc92  mov     cl, [rax]
0x18003fc94  mov     al, [rax+1]
0x18003fc97  mov     [r8+5], al
0x18003fc9b  lea     rax, [r8+6]
0x18003fc9f  mov     [r8+4], cl
0x18003fca3  sub     rax, r14
0x18003fca6  mov     cl, [rax]
0x18003fca8  mov     al, [rax+1]
0x18003fcab  mov     [r8+7], al
0x18003fcaf  lea     rax, [r8+8]
0x18003fcb3  mov     [r8+6], cl
0x18003fcb7  sub     rax, r14
0x18003fcba  mov     cl, [rax]
0x18003fcbc  mov     al, [rax+1]
0x18003fcbf  mov     [r8+9], al
0x18003fcc3  mov     [r8+8], cl
0x18003fcc7  add     r8, 0Ah
0x18003fccb  mov     rax, r8
0x18003fcce  mov     [rsp+98h+arg_0], r8
0x18003fcd6  sub     rax, r14
0x18003fcd9  lea     rbx, [r8+4]
0x18003fcdd  mov     cl, [rax]
0x18003fcdf  mov     al, [rax+1]
0x18003fce2  mov     [r8+1], al
0x18003fce6  lea     rax, [r8+2]
0x18003fcea  mov     [r8], cl
0x18003fced  sub     rax, r14
0x18003fcf0  mov     cl, [rax]
0x18003fcf2  mov     al, [rax+1]
0x18003fcf5  mov     [r8+3], al
0x18003fcf9  mov     [r8+2], cl
0x18003fcfd  jmp     short loc_18003FD4A
0x18003fcff  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18003fd06  mov     r8d, 10h; unsigned __int64
0x18003fd0c  mov     rdx, r13; unsigned __int8 *
  ... truncated ...
```
