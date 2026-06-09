# LHCalc3toX_Di16_Do16_Lut16_G16

- ea: `0x18002c300`
- end: `0x18002ccd1`
- name: `LHCalc3toX_Di16_Do16_Lut16_G16`
- size: `2513`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800268d0`
- `0x180028b60`

## callees

- `0x18002c300`

## pseudocode

```c
__int64 __fastcall LHCalc3toX_Di16_Do16_Lut16_G16(_QWORD *a1, _QWORD *a2, char a3)
{
  __int64 v3; // r10
  char v4; // bp
  _QWORD *v5; // r9
  _WORD *v7; // rsi
  _WORD *v8; // rbx
  _WORD *v9; // rdi
  _WORD *v10; // r14
  _WORD *v11; // r12
  _WORD *v12; // r13
  _WORD *v13; // r11
  int v14; // ecx
  int v15; // eax
  int v16; // r8d
  int v17; // edx
  int v18; // r15d
  unsigned int v19; // r9d
  unsigned int v20; // ebp
  unsigned int v21; // r8d
  unsigned int v22; // r10d
  __int64 v23; // rdx
  unsigned int v24; // ebp
  unsigned int v25; // r8d
  unsigned int v26; // r10d
  unsigned int v27; // ebx
  __int64 v28; // rax
  unsigned int v29; // edi
  unsigned int v30; // esi
  unsigned int v31; // ecx
  unsigned int v32; // esi
  unsigned int v33; // esi
  __int64 v34; // rbp
  unsigned int v35; // ecx
  unsigned int v36; // r8d
  unsigned int v37; // r8d
  unsigned int v38; // ecx
  unsigned int v39; // r8d
  __int64 v40; // rcx
  int v41; // r8d
  int v42; // edx
  int v43; // eax
  _WORD *v44; // rcx
  __int64 v45; // rdx
  unsigned int v46; // ecx
  unsigned int v47; // r8d
  __int64 v48; // rcx
  int v49; // r8d
  int v50; // eax
  __int64 v51; // r8
  __int64 v52; // rdx
  _WORD *v53; // rax
  _WORD *v54; // r10
  __int16 v55; // ax
  __int64 v56; // r8
  __int64 v57; // rdx
  _WORD *v58; // rax
  _WORD *v59; // r10
  __int16 v60; // ax
  __int16 v61; // ax
  _WORD *v62; // rdx
  __int16 v63; // ax
  __int64 v64; // r10
  __int64 v65; // r8
  _WORD *v66; // rdx
  _WORD *v67; // rax
  bool v68; // zf
  __int64 v69; // rcx
  __int64 v70; // rcx
  unsigned __int16 v71; // [rsp+0h] [rbp-108h]
  unsigned __int16 v72; // [rsp+2h] [rbp-106h]
  unsigned __int16 v73; // [rsp+4h] [rbp-104h]
  int v74; // [rsp+8h] [rbp-100h]
  _WORD *v75; // [rsp+10h] [rbp-F8h]
  int v76; // [rsp+18h] [rbp-F0h]
  int v77; // [rsp+1Ch] [rbp-ECh]
  int v78; // [rsp+20h] [rbp-E8h]
  int v79; // [rsp+24h] [rbp-E4h]
  _WORD *v80; // [rsp+28h] [rbp-E0h]
  _WORD *v81; // [rsp+30h] [rbp-D8h]
  _WORD *v82; // [rsp+38h] [rbp-D0h]
  __int64 v83; // [rsp+40h] [rbp-C8h]
  _WORD *v84; // [rsp+40h] [rbp-C8h]
  _WORD *v85; // [rsp+40h] [rbp-C8h]
  _WORD *v86; // [rsp+48h] [rbp-C0h]
  _WORD *v87; // [rsp+48h] [rbp-C0h]
  _WORD *v88; // [rsp+48h] [rbp-C0h]
  __int64 v89; // [rsp+50h] [rbp-B8h]
  _WORD *v90; // [rsp+50h] [rbp-B8h]
  _WORD *v91; // [rsp+50h] [rbp-B8h]
  _WORD *v92; // [rsp+50h] [rbp-B8h]
  __int64 v93; // [rsp+58h] [rbp-B0h]
  _WORD *v94; // [rsp+60h] [rbp-A8h]
  _WORD *v95; // [rsp+68h] [rbp-A0h]
  unsigned int v96; // [rsp+70h] [rbp-98h]
  int v97; // [rsp+74h] [rbp-94h]
  unsigned int v98; // [rsp+78h] [rbp-90h]
  int v99; // [rsp+7Ch] [rbp-8Ch]
  unsigned int v100; // [rsp+80h] [rbp-88h]
  int v101; // [rsp+84h] [rbp-84h]
  __int64 v102; // [rsp+88h] [rbp-80h]
  __int64 v103; // [rsp+90h] [rbp-78h]
  __int64 v104; // [rsp+98h] [rbp-70h]
  __int64 v105; // [rsp+A8h] [rbp-60h]
  char v107; // [rsp+118h] [rbp+10h]
  char v109; // [rsp+128h] [rbp+20h]

  v3 = a2[3];
  v4 = a3;
  v103 = v3;
  v5 = a1;
  if ( !v3 )
    return 87;
  v7 = (_WORD *)a1[4];
  v8 = (_WORD *)a1[5];
  v9 = (_WORD *)a1[6];
  v10 = (_WORD *)a1[16];
  v11 = (_WORD *)a1[12];
  v12 = (_WORD *)a1[13];
  v13 = (_WORD *)a1[15];
  v94 = (_WORD *)a1[7];
  v95 = (_WORD *)a1[14];
  v93 = a2[5];
  v102 = a2[8];
  v75 = v7;
  v80 = v8;
  v81 = v9;
  v82 = v10;
  v14 = (a3 != 0) + 3;
  v74 = v14;
  v100 = 273 * v14;
  v96 = 16 * v14;
  v97 = 257 * v14;
  v99 = 272 * v14;
  v98 = v14 << 8;
  v76 = *((_DWORD *)v5 + 6) / 2;
  v77 = *((_DWORD *)v5 + 7) / 2;
  v15 = *((_DWORD *)v5 + 2);
  v107 = *((_BYTE *)v5 + 161);
  if ( *((_DWORD *)v5 + 6) * v15 == *((_DWORD *)v5 + 4) && *((_DWORD *)v5 + 7) * v15 == *((_DWORD *)v5 + 5) )
  {
    v15 *= *((_DWORD *)v5 + 3);
    v16 = 1;
  }
  else
  {
    v16 = *((_DWORD *)v5 + 3);
  }
  v78 = v16;
  v79 = v15;
  if ( *((_BYTE *)v5 + 160) )
    v109 = 4;
  else
    v109 = (*((_BYTE *)v5 + 161) != 0) + 1;
  v17 = 0;
  v101 = 0;
  if ( !v16 )
    return 0;
  while ( 2 )
  {
    v18 = v15;
    if ( !v15 )
      goto LABEL_83;
    v19 = v74;
    do
    {
      while ( 1 )
      {
        v71 = *v7;
        v72 = *v8;
        v20 = ((unsigned __int8)(v71 - HIBYTE(v71))
             * *(unsigned __int16 *)(v3 + 2 * ((unsigned __int64)(unsigned __int16)(v71 - HIBYTE(v71)) >> 8) + 2)
             + (256 - (unsigned __int8)(v71 - HIBYTE(v71)))
             * (unsigned int)*(unsigned __int16 *)(v3
                                                 + 2 * ((unsigned __int64)(unsigned __int16)(v71 - HIBYTE(v71)) >> 8))) >> 8;
        v73 = *v9;
        v21 = ((unsigned __int8)(v72 - HIBYTE(v72))
             * *(unsigned __int16 *)(v3
                                   + 2LL * (unsigned __int16)(((unsigned __int16)(v72 - HIBYTE(v72)) >> 8) + 256)
                                   + 2)
             + (256 - (unsigned __int8)(v72 - HIBYTE(v72)))
             * (unsigned int)*(unsigned __int16 *)(v3
                                                 + 2LL
                                                 * (unsigned __int16)(((unsigned __int16)(v72 - HIBYTE(v72)) >> 8) + 256))) >> 8;
        v22 = ((unsigned __int8)(v73 - HIBYTE(v73))
             * *(unsigned __int16 *)(v103
                                   + 2LL * (unsigned __int16)(((unsigned __int16)(v73 - HIBYTE(v73)) >> 8) + 512)
                                   + 2)
             + (256 - (unsigned __int8)(v73 - HIBYTE(v73)))
             * (unsigned int)*(unsigned __int16 *)(v3
                                                 + 2LL
                                                 * (unsigned __int16)(((unsigned __int16)(v73 - HIBYTE(v73)) >> 8) + 512))) >> 8;
        v23 = v19 * ((v22 >> 12) + (((v21 & 0xF000) + 16 * (v20 & 0xF000)) >> 8));
        v104 = v23;
        v24 = v20 & 0xFFF;
        v25 = v21 & 0xFFF;
        v26 = v22 & 0xFFF;
        if ( v26 < v24 )
        {
          if ( v25 < v24 )
          {
            v28 = v98;
            v27 = 4096 - v24;
            if ( v26 >= v25 )
            {
              v29 = v24 - v26;
              v32 = v26;
              goto LABEL_25;
            }
            v29 = v24 - v25;
            v33 = v25;
          }
          else
          {
            v28 = v96;
            v27 = 4096 - v25;
            v33 = v24;
            v29 = v25 - v24;
          }
          v31 = v99;
          v30 = v33 - v26;
          goto LABEL_28;
        }
        if ( v25 < v24 )
        {
          v27 = 4096 - v26;
          v28 = v19;
          v32 = v24;
          v29 = v26 - v24;
LABEL_25:
          v31 = v97;
          v26 = v25;
          v30 = v32 - v25;
          goto LABEL_28;
        }
        if ( v26 < v25 )
        {
          v28 = v96;
          v29 = v25 - v26;
          v27 = 4096 - v25;
          v30 = v26 - v24;
        }
        else
        {
          v27 = 4096 - v26;
          v28 = v19;
          v29 = v26 - v25;
          v30 = v25 - v24;
        }
        v26 = v24;
        v31 = 17 * v19;
LABEL_28:
        v83 = v28;
        v34 = v31;
        v89 = v31;
        v35 = v27 * *(unsigned __int16 *)(v102 + 2 * v23)
            + v30 * *(unsigned __int16 *)(v102 + 2 * v23 + 2LL * v31)
            + v29 * *(unsigned __int16 *)(v102 + 2 * v23 + 2 * v28)
            + v26 * *(unsigned __int16 *)(v102 + 2LL * v100 + 2 * v23);
        v36 = v35 + HIWORD(v35) - ((v35 + HIWORD(v35)) >> 10);
        *v11 = (((v36 >> 8) & 0x3FF) * *(unsigned __int16 *)(v93 + 2LL * ((v36 >> 18) + 1))
              + (1024 - ((v36 >> 8) & 0x3FF)) * *(unsigned __int16 *)(v93 + 2LL * (v36 >> 18))) >> 10;
        v105 = v102 + 2 * (v100 + 1LL);
        v37 = ((v26 * *(unsigned __int16 *)(v105 + 2 * v23)
              + v30 * *(unsigned __int16 *)(v102 + 2 * v23 + 2 * v34 + 2)
              + v29 * *(unsigned __int16 *)(v102 + 2 * v23 + 2 * v83 + 2)
              + v27 * *(unsigned __int16 *)(v102 + 2 * v23 + 2)) >> 16)
            + v26 * *(unsigned __int16 *)(v105 + 2 * v23)
            + v30 * *(unsigned __int16 *)(v102 + 2 * v23 + 2 * v34 + 2)
            + v29 * *(unsigned __int16 *)(v102 + 2 * v23 + 2 * v83 + 2)
            + v27 * *(unsigned __int16 *)(v102 + 2 * v23 + 2)
            - ((((v26 * *(unsigned __int16 *)(v105 + 2 * v23)
                + v30 * *(unsigned __int16 *)(v102 + 2 * v23 + 2 * v34 + 2)
                + v29 * *(unsigned __int16 *)(v102 + 2 * v23 + 2 * v83 + 2)
                + v27 * *(unsigned __int16 *)(v102 + 2 * v23 + 2)) >> 16)
              + v26 * *(unsigned __int16 *)(v105 + 2 * v23)
              + v30 * *(unsigned __int16 *)(v102 + 2 * v23 + 2 * v34 + 2)
              + v29 * *(unsigned __int16 *)(v102 + 2 * v23 + 2 * v83 + 2)
              + v27 * *(unsigned __int16 *)(v102 + 2 * v23 + 2)) >> 10);
        *v12 = (((v37 >> 8) & 0x3FF) * *(unsigned __int16 *)(v93 + 2LL * ((v37 >> 18) + 1025))
              + (1024 - ((v37 >> 8) & 0x3FF)) * *(unsigned __int16 *)(v93 + 2LL * ((v37 >> 18) + 1024))) >> 10;
        v38 = v27 * *(unsigned __int16 *)(v102 + 2 * v23 + 4)
            + v30 * *(unsigned __int16 *)(v102 + 2 * v23 + 2 * v34 + 4)
            + v29 * *(unsigned __int16 *)(v102 + 2 * v23 + 2 * v28 + 4)
            + v26 * *(unsigned __int16 *)(v102 + 2 * (v100 + 2LL) + 2 * v23);
        v39 = HIWORD(v38) + v38 - ((HIWORD(v38) + v38) >> 10);
        v40 = (v39 >> 18) + 2048;
        v41 = (v39 >> 8) & 0x3FF;
        v42 = (1024 - v41) * *(unsigned __int16 *)(v93 + 2 * v40);
        v43 = *(unsigned __int16 *)(v93 + 2LL * (unsigned int)(v40 + 1));
        v44 = v95;
        v4 = a3;
        *v95 = (unsigned int)(v41 * v43 + v42) >> 10;
        if ( a3 )
        {
          v45 = v102 + 2 * v104;
          v46 = v27 * *(unsigned __int16 *)(v45 + 6)
              + v30 * *(unsigned __int16 *)(v45 + 2 * v89 + 6)
              + v29 * *(unsigned __int16 *)(v45 + 2 * v83 + 6)
              + v26 * *(unsigned __int16 *)(v45 + 2LL * v100 + 6);
          v47 = HIWORD(v46) + v46 - ((HIWORD(v46) + v46) >> 10);
          v48 = (v47 >> 18) + 3072;
          v49 = (v47 >> 8) & 0x3FF;
          LODWORD(v45) = (1024 - v49) * *(unsigned __int16 *)(v93 + 2 * v48);
          v50 = *(unsigned __int16 *)(v93 + 2LL * (unsigned int)(v48 + 1));
          v44 = v95;
          *v13 = (unsigned int)(v49 * v50 + v45) >> 10;
        }
        if ( v109 == 1 )
        {
          if ( !--v18 )
            goto LABEL_82;
          v51 = 2LL * v76;
          v8 = v80;
          v52 = 2LL * v77;
          v9 = v81;
          v7 = v75;
          do
          {
            v7 = (_WORD *)((char *)v7 + v51);
            v86 = v12;
            v12 = (_WORD *)((char *)v12 + v52);
            v90 = v11;
            v11 = (_WORD *)((char *)v11 + v52);
            v53 = &v13[(unsigned __int64)v52 / 2];
            v8 = (_WORD *)((char *)v8 + v51);
            v9 = (_WORD *)((char *)v9 + v51);
            v54 = v44;
            v44 = (_WORD *)((char *)v44 + v52);
            if ( !a3 )
              v53 = v13;
            v13 = v53;
            if ( v71 != *v7 || v72 != *v8 || v73 != *v9 )
              break;
            *v11 = *v90;
            *v12 = *v86;
            *v44 = *v54;
            if ( a3 )
              *v53 = v53[-v77];
            --v18;
          }
          while ( v18 );
          v10 = v82;
          goto LABEL_66;
        }
        if ( v109 == 2 )
          break;
        v62 = v94;
        v63 = *v94;
        if ( a3 )
          *v10 = v63;
        else
          *v13 = v63;
        if ( !--v18 )
          goto LABEL_82;
        v64 = 2LL * v76;
        v8 = v80;
        v65 = 2LL * v77;
        v9 = v81;
        v7 = v75;
        while ( 1 )
        {
          v7 = (_WORD *)((char *)v7 + v64);
          v94 = &v62[(unsigned __int64)v64 / 2];
          v8 = (_WORD *)((char *)v8 + v64);
          v85 = v13;
          v9 = (_WORD *)((char *)v9 + v64);
          v88 = v44;
          v44 = (_WORD *)((char *)v44 + v65);
          v92 = v12;
          v12 = (_WORD *)((char *)v12 + v65);
          v75 = v7;
          v13 = (_WORD *)((char *)v13 + v65);
          v80 = v8;
          v66 = &v10[(unsigned __int64)v65 / 2];
          v81 = v9;
          v67 = v11;
          v95 = v44;
          v11 = (_WORD *)((char *)v11 + v65);
          if ( !a3 )
            v66 = v10;
          v19 = v74;
          v10 = v66;
          v82 = v66;
          if ( v71 != *v7 )
            break;
          v19 = v74;
          v82 = v66;
          if ( v72 == *v8 )
          {
            v82 = v66;
            if ( v73 == *v9 )
            {
              *v11 = *v67;
              *v12 = *v92;
              *v44 = *v88;
              if ( a3 )
              {
                *v13 = *v85;
                *v66 = *v94;
              }
              else
              {
                *v13 = *v94;
              }
              v82 = v66;
              v62 = v94;
              if ( --v18 )
                continue;
            }
          }
          goto LABEL_81;
        }
        v3 = v103;
      }
      v55 = 0;
      if ( a3 )
      {
        if ( !v107 )
          v55 = *v10;
        *v10 = v55;
      }
      else
      {
        if ( !v107 )
          v55 = *v13;
        *v13 = v55;
      }
      if ( !--v18 )
        break;
      v56 = 2LL * v76;
      v8 = v80;
      v57 = 2LL * v77;
      v9 = v81;
      v7 = v75;
      do
      {
        v7 = (_WORD *)((char *)v7 + v56);
        v84 = v13;
        v13 = (_WORD *)((char *)v13 + v57);
        v87 = v12;
        v12 = (_WORD *)((char *)v12 + v57);
        v91 = v11;
        v11 = (_WORD *)((char *)v11 + v57);
        v58 = &v10[(unsigned __int64)v57 / 2];
        v8 = (_WORD *)((char *)v8 + v56);
        v9 = (_WORD *)((char *)v9 + v56);
        v59 = v44;
        v44 = (_WORD *)((char *)v44 + v57);
        if ( !a3 )
          v58 = v10;
        v10 = v58;
        if ( v71 != *v7 || v72 != *v8 || v73 != *v9 )
          break;
        *v11 = *v91;
        *v12 = *v87;
        *v44 = *v59;
        if ( a3 )
        {
          *v13 = *v84;
          v60 = 0;
          if ( !v107 )
            v60 = *v10;
          *v10 = v60;
        }
        else
        {
          v61 = 0;
          if ( !v107 )
            v61 = *v13;
          *v13 = v61;
        }
        --v18;
      }
      while ( v18 );
      v82 = v10;
LABEL_66:
      v19 = v74;
      v95 = v44;
      v80 = v8;
      v81 = v9;
      v75 = v7;
LABEL_81:
      v3 = v103;
    }
    while ( v18 );
LABEL_82:
    v5 = a1;
    v16 = v78;
    v17 = v101;
    v3 = v103;
LABEL_83:
    v68 = v16-- == 1;
    v78 = v16;
    if ( !v68 )
    {
      ++v17;
      v69 = (unsigned int)(*((_DWORD *)v5 + 4) * v17);
      v7 = (_WORD *)(v69 + v5[4]);
      v94 = (_WORD *)(v69 + v5[7]);
      v8 = (_WORD *)(v69 + v5[5]);
      v9 = (_WORD *)(v69 + v5[6]);
      v101 = v17;
      v75 = v7;
      v70 = (unsigned int)(*((_DWORD *)v5 + 5) * v17);
      v80 = v8;
      v81 = v9;
      v11 = (_WORD *)(v70 + v5[12]);
      v12 = (_WORD *)(v70 + v5[13]);
      v95 = (_WORD *)(v70 + v5[14]);
      v15 = v79;
      v13 = (_WORD *)(v70 + v5[15]);
      if ( v4 )
      {
        v10 = (_WORD *)(v70 + v5[16]);
        v82 = v10;
      }
      continue;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18002c300  mov     [rsp+arg_10], r8b
0x18002c305  mov     [rsp+arg_0], rcx
0x18002c30a  push    rbx
0x18002c30b  push    rbp
0x18002c30c  push    rsi
0x18002c30d  push    rdi
0x18002c30e  push    r12
0x18002c310  push    r13
0x18002c312  push    r14
0x18002c314  push    r15
0x18002c316  sub     rsp, 0C8h
0x18002c31d  mov     r10, [rdx+18h]
0x18002c321  mov     bpl, r8b
0x18002c324  mov     [rsp+108h+var_78], r10
0x18002c32c  mov     r9, rcx
0x18002c32f  test    r10, r10
0x18002c332  jnz     short loc_18002C33D
0x18002c334  lea     eax, [r10+57h]
0x18002c338  jmp     loc_18002CCBD
0x18002c33d  mov     rax, [rcx+38h]
0x18002c341  mov     rsi, [rcx+20h]
0x18002c345  mov     rbx, [rcx+28h]
0x18002c349  mov     rdi, [rcx+30h]
0x18002c34d  mov     r14, [rcx+80h]
0x18002c354  mov     r12, [rcx+60h]
0x18002c358  mov     r13, [rcx+68h]
0x18002c35c  mov     r11, [rcx+78h]
0x18002c360  mov     [rsp+108h+var_A8], rax
0x18002c365  mov     rax, [rcx+70h]
0x18002c369  mov     [rsp+108h+var_A0], rax
0x18002c36e  mov     rax, [rdx+28h]
0x18002c372  mov     [rsp+108h+var_B0], rax
0x18002c377  mov     rax, [rdx+40h]
0x18002c37b  mov     [rsp+108h+var_80], rax
0x18002c383  mov     al, r8b
0x18002c386  neg     al
0x18002c388  mov     [rsp+108h+var_F8], rsi
0x18002c38d  mov     [rsp+108h+var_E0], rbx
0x18002c392  sbb     ecx, ecx
0x18002c394  mov     [rsp+108h+var_D8], rdi
0x18002c399  neg     ecx
0x18002c39b  mov     [rsp+108h+var_D0], r14
0x18002c3a0  add     ecx, 3
0x18002c3a3  imul    eax, ecx, 111h
0x18002c3a9  mov     [rsp+108h+var_100], ecx
0x18002c3ad  mov     [rsp+108h+var_88], eax
0x18002c3b4  mov     eax, ecx
0x18002c3b6  shl     eax, 4
0x18002c3b9  mov     [rsp+108h+var_98], eax
0x18002c3bd  imul    eax, ecx, 101h
0x18002c3c3  mov     [rsp+108h+var_94], eax
0x18002c3c7  imul    eax, ecx, 110h
0x18002c3cd  mov     [rsp+108h+var_8C], eax
0x18002c3d1  mov     eax, ecx
0x18002c3d3  shl     eax, 8
0x18002c3d6  mov     ecx, 2
0x18002c3db  mov     [rsp+108h+var_90], eax
0x18002c3df  mov     eax, [r9+18h]
0x18002c3e3  cdq
0x18002c3e4  idiv    ecx
0x18002c3e6  mov     [rsp+108h+var_F0], eax
0x18002c3ea  mov     eax, [r9+1Ch]
0x18002c3ee  cdq
0x18002c3ef  idiv    ecx
0x18002c3f1  mov     dl, [r9+0A1h]
0x18002c3f8  mov     [rsp+108h+var_EC], eax
0x18002c3fc  mov     eax, [r9+8]
0x18002c400  mov     ecx, eax
0x18002c402  imul    ecx, [r9+18h]
0x18002c407  mov     [rsp+108h+arg_8], dl
0x18002c40e  cmp     ecx, [r9+10h]
0x18002c412  jnz     short loc_18002C42E
0x18002c414  mov     ecx, eax
0x18002c416  imul    ecx, [r9+1Ch]
0x18002c41b  cmp     ecx, [r9+14h]
0x18002c41f  jnz     short loc_18002C42E
0x18002c421  imul    eax, [r9+0Ch]
0x18002c426  mov     r8d, 1
0x18002c42c  jmp     short loc_18002C432
0x18002c42e  mov     r8d, [r9+0Ch]
0x18002c432  cmp     byte ptr [r9+0A0h], 0
0x18002c43a  mov     [rsp+108h+var_E8], r8d
0x18002c43f  mov     [rsp+108h+var_E4], eax
0x18002c443  jz      short loc_18002C44F
0x18002c445  mov     [rsp+108h+arg_18], 4
0x18002c44d  jmp     short loc_18002C45D
0x18002c44f  test    dl, dl
0x18002c451  setnz   cl
0x18002c454  inc     cl
0x18002c456  mov     [rsp+108h+arg_18], cl
0x18002c45d  xor     edx, edx
0x18002c45f  mov     [rsp+108h+var_84], edx
0x18002c466  test    r8d, r8d
0x18002c469  jz      loc_18002CCBB
0x18002c46f  mov     r15d, eax
0x18002c472  test    eax, eax
0x18002c474  jz      loc_18002CC23
0x18002c47a  mov     eax, [rsp+108h+var_88]
0x18002c481  mov     rcx, [rsp+108h+var_80]
0x18002c489  mov     r9d, [rsp+108h+var_100]
0x18002c48e  lea     rdx, [rcx+rax*2]
0x18002c492  mov     [rsp+108h+var_68], rdx
0x18002c49a  lea     rdx, [rax+1]
0x18002c49e  add     rax, 2
0x18002c4a2  lea     rdx, [rcx+rdx*2]
0x18002c4a6  mov     [rsp+108h+var_60], rdx
0x18002c4ae  lea     rax, [rcx+rax*2]
0x18002c4b2  mov     [rsp+108h+var_58], rax
0x18002c4ba  jmp     short loc_18002C4C4
0x18002c4bc  mov     r10, [rsp+108h+var_78]
0x18002c4c4  movzx   eax, word ptr [rsi]
0x18002c4c7  mov     esi, 100h
0x18002c4cc  movzx   ecx, ax
0x18002c4cf  mov     [rsp+108h+var_108], ax
0x18002c4d3  shr     cx, 8
0x18002c4d7  sub     ax, cx
0x18002c4da  movzx   edx, al
0x18002c4dd  movzx   ecx, ax
0x18002c4e0  mov     eax, esi
0x18002c4e2  sub     eax, edx
0x18002c4e4  shr     rcx, 8
0x18002c4e8  movzx   ebp, word ptr [r10+rcx*2]
0x18002c4ed  imul    ebp, eax
0x18002c4f0  movzx   eax, word ptr [r10+rcx*2+2]
0x18002c4f6  imul    eax, edx
0x18002c4f9  add     ebp, eax
0x18002c4fb  movzx   eax, word ptr [rbx]
0x18002c4fe  movzx   ecx, ax
0x18002c501  mov     [rsp+108h+var_106], ax
0x18002c506  shr     cx, 8
0x18002c50a  sub     ax, cx
0x18002c50d  shr     ebp, 8
0x18002c510  movzx   edx, al
0x18002c513  shr     ax, 8
0x18002c517  add     ax, si
0x18002c51a  movzx   ecx, ax
0x18002c51d  mov     eax, esi
0x18002c51f  sub     eax, edx
0x18002c521  movzx   r8d, word ptr [r10+rcx*2]
0x18002c526  imul    r8d, eax
0x18002c52a  movzx   eax, word ptr [r10+rcx*2+2]
0x18002c530  imul    eax, edx
0x18002c533  add     r8d, eax
0x18002c536  movzx   eax, word ptr [rdi]
0x18002c539  movzx   ecx, ax
0x18002c53c  mov     [rsp+108h+var_104], ax
0x18002c541  shr     cx, 8
0x18002c545  sub     ax, cx
0x18002c548  shr     r8d, 8
0x18002c54c  movzx   edx, al
0x18002c54f  mov     ecx, 200h
0x18002c554  shr     ax, 8
0x18002c558  add     ax, cx
0x18002c55b  movzx   ecx, ax
0x18002c55e  mov     eax, esi
0x18002c560  sub     eax, edx
0x18002c562  movzx   r10d, word ptr [r10+rcx*2]
0x18002c567  imul    r10d, eax
0x18002c56b  mov     rax, [rsp+108h+var_78]
0x18002c573  movzx   eax, word ptr [rax+rcx*2+2]
0x18002c578  mov     ecx, ebp
0x18002c57a  imul    eax, edx
0x18002c57d  mov     edx, 0F000h
0x18002c582  and     ecx, edx
0x18002c584  shl     ecx, 4
0x18002c587  add     r10d, eax
0x18002c58a  mov     eax, r8d
0x18002c58d  and     eax, edx
0x18002c58f  shr     r10d, 8
0x18002c593  add     ecx, eax
0x18002c595  mov     eax, r10d
0x18002c598  shr     eax, 0Ch
0x18002c59b  shr     ecx, 8
0x18002c59e  add     ecx, eax
0x18002c5a0  mov     rax, [rsp+108h+var_80]
0x18002c5a8  imul    ecx, r9d
0x18002c5ac  mov     edx, ecx
0x18002c5ae  mov     [rsp+108h+var_70], rdx
0x18002c5b6  lea     rax, [rax+rcx*2]
0x18002c5ba  mov     [rsp+108h+var_C0], rax
0x18002c5bf  mov     eax, 0FFFh
0x18002c5c4  and     ebp, eax
0x18002c5c6  and     r8d, eax
0x18002c5c9  and     r10d, eax
0x18002c5cc  lea     ebx, [rax+1]
0x18002c5cf  cmp     r10d, ebp
0x18002c5d2  jb      short loc_18002C61C
0x18002c5d4  cmp     r8d, ebp
0x18002c5d7  jb      short loc_18002C60D
0x18002c5d9  cmp     r10d, r8d
0x18002c5dc  jb      short loc_18002C5F2
0x18002c5de  sub     ebx, r10d
0x18002c5e1  mov     eax, r9d
0x18002c5e4  sub     r10d, r8d
0x18002c5e7  sub     r8d, ebp
0x18002c5ea  mov     edi, r10d
0x18002c5ed  mov     esi, r8d
0x18002c5f0  jmp     short loc_18002C604
0x18002c5f2  mov     eax, [rsp+108h+var_98]
0x18002c5f6  mov     edi, r8d
0x18002c5f9  sub     edi, r10d
0x18002c5fc  sub     ebx, r8d
0x18002c5ff  mov     esi, r10d
0x18002c602  sub     esi, ebp
0x18002c604  mov     r10d, ebp
0x18002c607  imul    ecx, r9d, 11h
0x18002c60b  jmp     short loc_18002C65D
0x18002c60d  sub     ebx, r10d
0x18002c610  mov     eax, r9d
0x18002c613  mov     edi, r10d
0x18002c616  mov     esi, ebp
0x18002c618  sub     edi, ebp
0x18002c61a  jmp     short loc_18002C644
0x18002c61c  cmp     r8d, ebp
0x18002c61f  jb      short loc_18002C631
0x18002c621  mov     eax, [rsp+108h+var_98]
0x18002c625  sub     ebx, r8d
0x18002c628  mov     edi, r8d
0x18002c62b  mov     esi, ebp
0x18002c62d  sub     edi, ebp
0x18002c62f  jmp     short loc_18002C656
0x18002c631  mov     eax, [rsp+108h+var_90]
0x18002c635  sub     ebx, ebp
0x18002c637  mov     edi, ebp
0x18002c639  cmp     r10d, r8d
0x18002c63c  jb      short loc_18002C650
0x18002c63e  sub     edi, r10d
0x18002c641  mov     esi, r10d
0x18002c644  mov     ecx, [rsp+108h+var_94]
0x18002c648  mov     r10d, r8d
0x18002c64b  sub     esi, r8d
0x18002c64e  jmp     short loc_18002C65D
0x18002c650  sub     edi, r8d
0x18002c653  mov     esi, r8d
0x18002c656  mov     ecx, [rsp+108h+var_8C]
0x18002c65a  sub     esi, r10d
0x18002c65d  mov     [rsp+108h+var_C8], rax
0x18002c662  mov     ebp, ecx
0x18002c664  mov     rcx, [rsp+108h+var_68]
0x18002c66c  mov     [rsp+108h+var_B8], rbp
0x18002c671  movzx   ecx, word ptr [rcx+rdx*2]
0x18002c675  mov     rdx, [rsp+108h+var_C0]
0x18002c67a  imul    ecx, r10d
0x18002c67e  movzx   eax, word ptr [rdx+rax*2]
0x18002c682  imul    eax, edi
0x18002c685  add     ecx, eax
0x18002c687  movzx   eax, word ptr [rdx+rbp*2]
0x18002c68b  imul    eax, esi
0x18002c68e  add     ecx, eax
0x18002c690  movzx   eax, word ptr [rdx]
0x18002c693  imul    eax, ebx
0x18002c696  add     ecx, eax
0x18002c698  mov     edx, ecx
0x18002c69a  shr     edx, 10h
0x18002c69d  add     edx, ecx
0x18002c69f  mov     eax, edx
0x18002c6a1  shr     eax, 0Ah
0x18002c6a4  sub     edx, eax
0x18002c6a6  mov     eax, 400h
0x18002c6ab  mov     r8d, edx
0x18002c6ae  shr     edx, 12h
0x18002c6b1  mov     ecx, edx
0x18002c6b3  mov     rdx, [rsp+108h+var_B0]
0x18002c6b8  shr     r8d, 8
0x18002c6bc  and     r8d, 3FFh
0x18002c6c3  sub     eax, r8d
0x18002c6c6  movzx   edx, word ptr [rdx+rcx*2]
0x18002c6ca  inc     ecx
0x18002c6cc  imul    edx, eax
0x18002c6cf  mov     rax, [rsp+108h+var_B0]
0x18002c6d4  movzx   eax, word ptr [rax+rcx*2]
0x18002c6d8  imul    eax, r8d
0x18002c6dc  mov     r8, [rsp+108h+var_70]
0x18002c6e4  add     edx, eax
0x18002c6e6  mov     rax, [rsp+108h+var_80]
0x18002c6ee  shr     edx, 0Ah
0x18002c6f1  mov     [r12], dx
0x18002c6f6  lea     rcx, [rax+r8*2]
0x18002c6fa  mov     rax, [rsp+108h+var_C8]
0x18002c6ff  movzx   edx, word ptr [rcx+rax*2+2]
0x18002c704  movzx   eax, word ptr [rcx+rbp*2+2]
0x18002c709  movzx   ecx, word ptr [rcx+2]
0x18002c70d  imul    eax, esi
0x18002c710  imul    ecx, ebx
0x18002c713  imul    edx, edi
0x18002c716  add     edx, eax
0x18002c718  mov     rax, [rsp+108h+var_60]
0x18002c720  movzx   eax, word ptr [rax+r8*2]
0x18002c725  imul    eax, r10d
0x18002c729  add     edx, eax
0x18002c72b  add     ecx, edx
0x18002c72d  mov     rdx, [rsp+108h+var_B0]
0x18002c732  mov     eax, ecx
0x18002c734  shr     eax, 10h
0x18002c737  add     ecx, eax
0x18002c739  mov     eax, ecx
0x18002c73b  shr     eax, 0Ah
0x18002c73e  sub     ecx, eax
0x18002c740  mov     eax, 400h
0x18002c745  mov     r8d, ecx
  ... truncated ...
```
