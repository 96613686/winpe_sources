# LHCalc3toX_Di16_Do16_Lut16_G32

- ea: `0x1800120d0`
- end: `0x180012ae9`
- name: `LHCalc3toX_Di16_Do16_Lut16_G32`
- size: `2585`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a480`
- `0x18001c490`

## callees

- `0x1800120d0`

## pseudocode

```c
__int64 __fastcall LHCalc3toX_Di16_Do16_Lut16_G32(__int64 a1, _QWORD *a2, char a3)
{
  __int64 v3; // r15
  __int64 v5; // r13
  _WORD *v6; // r9
  _WORD *v7; // r10
  _WORD *v8; // r11
  __int16 *v9; // rbx
  int v10; // ebp
  unsigned __int16 *v11; // rsi
  unsigned __int16 *v12; // rdi
  unsigned __int16 *v13; // r14
  int v14; // eax
  char v15; // dl
  int v16; // eax
  int v17; // ecx
  int v18; // edx
  unsigned __int16 v20; // r13
  unsigned int v21; // ebp
  unsigned __int16 v22; // ax
  unsigned int v23; // r8d
  int v24; // edx
  __int64 v25; // rcx
  int v26; // r15d
  int v27; // eax
  unsigned int v28; // ebp
  unsigned int v29; // r15d
  unsigned int v30; // r8d
  unsigned int v31; // eax
  unsigned int v32; // r15d
  __int64 v33; // rdx
  unsigned int v34; // ecx
  unsigned int v35; // eax
  __int64 v36; // rax
  unsigned int v37; // edx
  unsigned int v38; // ecx
  unsigned int v39; // r8d
  int v40; // eax
  int v41; // ecx
  unsigned int v42; // ecx
  __int64 v43; // rdx
  __int64 v44; // rax
  __int16 *v45; // rcx
  _WORD *v46; // r8
  _WORD *v47; // r15
  _WORD *v48; // rbp
  __int64 v49; // rcx
  __int64 v50; // rcx
  int v51; // eax
  unsigned int v52; // r8d
  int v53; // eax
  unsigned int v54; // eax
  unsigned int v55; // eax
  __int16 *v56; // rdx
  __int16 v57; // ax
  __int64 v58; // rbp
  __int64 v59; // r8
  _WORD *v60; // r15
  _WORD *v61; // rax
  bool v62; // zf
  __int16 v63; // ax
  int v64; // ecx
  __int64 v65; // r8
  __int64 v66; // rdx
  __int16 *v67; // rax
  _WORD *v68; // r15
  _WORD *v69; // rbp
  __int16 v70; // ax
  __int16 v71; // ax
  int v72; // [rsp+0h] [rbp-F8h]
  unsigned int v73; // [rsp+4h] [rbp-F4h]
  unsigned int v74; // [rsp+8h] [rbp-F0h]
  __int16 *v75; // [rsp+10h] [rbp-E8h]
  unsigned __int16 v76; // [rsp+18h] [rbp-E0h]
  unsigned __int16 v77; // [rsp+1Ah] [rbp-DEh]
  unsigned int v78; // [rsp+1Ch] [rbp-DCh]
  int v79; // [rsp+20h] [rbp-D8h]
  int v80; // [rsp+24h] [rbp-D4h]
  int v81; // [rsp+28h] [rbp-D0h]
  __int64 v82; // [rsp+30h] [rbp-C8h]
  unsigned __int16 *v83; // [rsp+30h] [rbp-C8h]
  _WORD *v84; // [rsp+30h] [rbp-C8h]
  _WORD *v85; // [rsp+30h] [rbp-C8h]
  int v86; // [rsp+38h] [rbp-C0h]
  int v87; // [rsp+3Ch] [rbp-BCh]
  __int64 v88; // [rsp+40h] [rbp-B8h]
  __int64 v89; // [rsp+48h] [rbp-B0h]
  __int16 *v90; // [rsp+48h] [rbp-B0h]
  __int16 *v91; // [rsp+48h] [rbp-B0h]
  __int64 v92; // [rsp+50h] [rbp-A8h]
  __int16 *v93; // [rsp+58h] [rbp-A0h]
  int v94; // [rsp+60h] [rbp-98h]
  unsigned int v95; // [rsp+64h] [rbp-94h]
  int v96; // [rsp+68h] [rbp-90h]
  unsigned int v97; // [rsp+6Ch] [rbp-8Ch]
  int v98; // [rsp+70h] [rbp-88h]
  unsigned int v99; // [rsp+74h] [rbp-84h]
  __int64 v100; // [rsp+78h] [rbp-80h]
  __int64 v101; // [rsp+80h] [rbp-78h]
  __int64 v102; // [rsp+88h] [rbp-70h]
  __int64 v103; // [rsp+B8h] [rbp-40h]
  char v105; // [rsp+108h] [rbp+10h]
  char v106; // [rsp+118h] [rbp+20h]

  v3 = a2[3];
  v92 = v3;
  v5 = a1;
  if ( !v3 )
    return 87;
  v6 = *(_WORD **)(a1 + 96);
  v7 = *(_WORD **)(a1 + 104);
  v8 = *(_WORD **)(a1 + 112);
  v9 = *(__int16 **)(a1 + 120);
  v10 = *(_DWORD *)(a1 + 28);
  v11 = *(unsigned __int16 **)(a1 + 40);
  v12 = *(unsigned __int16 **)(a1 + 32);
  v13 = *(unsigned __int16 **)(a1 + 48);
  v93 = *(__int16 **)(a1 + 56);
  v75 = *(__int16 **)(a1 + 128);
  v88 = a2[5];
  v100 = a2[8];
  v14 = (a3 != 0) + 3;
  v80 = v14;
  v99 = 1057 * v14;
  v94 = 32 * v14;
  v95 = 1025 * v14;
  v96 = v14 << 10;
  v97 = 1056 * v14;
  v86 = *(_DWORD *)(a1 + 24) / 2;
  v15 = *(_BYTE *)(a1 + 161);
  v87 = v10 / 2;
  v16 = *(_DWORD *)(a1 + 8);
  v105 = v15;
  if ( *(_DWORD *)(a1 + 24) * v16 == *(_DWORD *)(a1 + 16) && v10 * v16 == *(_DWORD *)(a1 + 20) )
  {
    v16 *= *(_DWORD *)(a1 + 12);
    v17 = 1;
  }
  else
  {
    v17 = *(_DWORD *)(a1 + 12);
  }
  v79 = v17;
  v81 = v16;
  if ( *(_BYTE *)(v5 + 160) )
    v106 = 4;
  else
    v106 = (v15 != 0) + 1;
  v18 = 0;
  v98 = 0;
  if ( !v17 )
    return 0;
  while ( 2 )
  {
    v72 = v16;
    if ( !v16 )
      goto LABEL_33;
    v102 = v3 + 2;
    v103 = v99;
    while ( 1 )
    {
      v20 = *v12;
      v76 = *v11;
      v21 = ((unsigned __int8)(*(_BYTE *)v12 - HIBYTE(v20))
           * *(unsigned __int16 *)(v3 + 2 * ((unsigned __int64)(unsigned __int16)(*v12 - HIBYTE(v20)) >> 8) + 2)
           + (256 - (unsigned __int8)(*(_BYTE *)v12 - HIBYTE(v20)))
           * (unsigned int)*(unsigned __int16 *)(2 * ((unsigned __int64)(unsigned __int16)(*v12 - HIBYTE(v20)) >> 8) + v3)) >> 8;
      v77 = *v13;
      v22 = v77 - HIBYTE(v77);
      v23 = ((unsigned __int8)(v76 - HIBYTE(v76))
           * *(unsigned __int16 *)(v3 + 2LL * (unsigned __int16)(((unsigned __int16)(v76 - HIBYTE(v76)) >> 8) + 256) + 2)
           + (256 - (unsigned __int8)(v76 - HIBYTE(v76)))
           * (unsigned int)*(unsigned __int16 *)(2LL
                                               * (unsigned __int16)(((unsigned __int16)(v76 - HIBYTE(v76)) >> 8) + 256)
                                               + v3)) >> 8;
      v24 = (unsigned __int8)v22;
      v25 = 2LL * (unsigned __int16)(HIBYTE(v22) + 512);
      v26 = (256 - (unsigned __int8)v22) * *(unsigned __int16 *)(v25 + v3);
      v27 = *(unsigned __int16 *)(v102 + v25);
      LODWORD(v25) = 32 * (v21 & 0xF800);
      v28 = v21 & 0x7FF;
      v29 = (unsigned int)(v24 * v27 + v26) >> 8;
      LODWORD(v25) = (v23 & 0xF800) + v25;
      v30 = v23 & 0x7FF;
      v31 = v29 >> 11;
      v32 = v29 & 0x7FF;
      v33 = 2LL * v80 * (v31 + ((unsigned int)v25 >> 6));
      v82 = v33;
      if ( v32 >= v28 )
      {
        if ( v30 < v28 )
        {
          v34 = v80;
          v78 = 2048 - v32;
          v55 = v32 - v28;
          v32 = v30;
          v73 = v55;
          v74 = v28 - v30;
          v36 = v95;
        }
        else
        {
          if ( v32 < v30 )
          {
            v34 = v94;
            v78 = 2048 - v30;
            v73 = v30 - v32;
            v74 = v32 - v28;
            v53 = v80;
          }
          else
          {
            v78 = 2048 - v32;
            v53 = v80;
            v34 = v80;
            v74 = v30 - v28;
            v73 = v32 - v30;
          }
          v32 = v28;
          v36 = (unsigned int)(33 * v53);
        }
      }
      else
      {
        if ( v30 >= v28 )
        {
          v34 = v94;
          v78 = 2048 - v30;
          v73 = v30 - v28;
          v35 = v28;
LABEL_18:
          v74 = v35 - v32;
          v36 = v97;
          goto LABEL_19;
        }
        v34 = v96;
        v78 = 2048 - v28;
        if ( v32 < v30 )
        {
          v78 = 2048 - v28;
          v73 = v28 - v30;
          v35 = v30;
          goto LABEL_18;
        }
        v73 = v28 - v32;
        v54 = v32 - v30;
        v32 = v30;
        v74 = v54;
        v36 = v95;
      }
LABEL_19:
      v89 = v36;
      v101 = v34;
      v37 = v78 * *(unsigned __int16 *)(v33 + v100)
          + v32 * *(unsigned __int16 *)(v33 + v103 * 2 + v100)
          + v74 * *(unsigned __int16 *)(2 * v36 + v33 + v100)
          + v73 * *(unsigned __int16 *)(v101 * 2 + v33 + v100)
          + ((v78 * *(unsigned __int16 *)(v33 + v100)
            + v32 * *(unsigned __int16 *)(v33 + v103 * 2 + v100)
            + v74 * *(unsigned __int16 *)(2 * v36 + v33 + v100)
            + v73 * *(unsigned __int16 *)(v101 * 2 + v33 + v100)) >> 16);
      *v6 = ((((v37 - (v37 >> 10)) >> 8) & 0x1FF) * *(unsigned __int16 *)(v88 + 2LL * (((v37 - (v37 >> 10)) >> 17) + 1))
           + (512 - (((v37 - (v37 >> 10)) >> 8) & 0x1FF))
           * *(unsigned __int16 *)(v88 + 2LL * ((v37 - (v37 >> 10)) >> 17))) >> 9;
      v38 = v74 * *(unsigned __int16 *)(v82 + v100 + 2 + 2 * v36)
          + v73 * *(unsigned __int16 *)(v82 + v100 + 2 + v101 * 2)
          + v32 * *(unsigned __int16 *)(v103 * 2 + v100 + 2 + v82)
          + v78 * *(unsigned __int16 *)(v82 + v100 + 2);
      v39 = HIWORD(v38) + v38 - ((HIWORD(v38) + v38) >> 10);
      *v7 = (((v39 >> 8) & 0x1FF) * *(unsigned __int16 *)(v88 + 2LL * ((v39 >> 17) + 1025))
           + (512 - ((v39 >> 8) & 0x1FF)) * *(unsigned __int16 *)(v88 + 2LL * ((v39 >> 17) + 1024))) >> 9;
      v40 = v32 * *(unsigned __int16 *)(v103 * 2 + v100 + 4 + v82);
      v83 = (unsigned __int16 *)(v82 + v100 + 4);
      v41 = v73 * v83[v101] + v40 + v74 * v83[v89];
      v42 = ((v78 * *v83 + v41) >> 16) + v78 * *v83 + v41;
      *v8 = ((((v42 - (v42 >> 10)) >> 8) & 0x1FF)
           * *(unsigned __int16 *)(v88 + 2LL * (((v42 - (v42 >> 10)) >> 17) + 2049))
           + (512 - (((v42 - (v42 >> 10)) >> 8) & 0x1FF))
           * *(unsigned __int16 *)(v88 + 2LL * (((v42 - (v42 >> 10)) >> 17) + 2048))) >> 9;
      if ( a3 )
      {
        v51 = v78 * v83[1];
        v52 = ((v51 + v74 * v83[v89 + 1] + v73 * v83[v101 + 1] + v32 * v83[v103 + 1]) >> 16)
            + v51
            + v74 * v83[v89 + 1]
            + v73 * v83[v101 + 1]
            + v32 * v83[v103 + 1]
            - ((((v51 + v74 * v83[v89 + 1] + v73 * v83[v101 + 1] + v32 * v83[v103 + 1]) >> 16)
              + v51
              + v74 * v83[v89 + 1]
              + v73 * v83[v101 + 1]
              + v32 * v83[v103 + 1]) >> 10);
        *v9 = (((v52 >> 8) & 0x1FF) * *(unsigned __int16 *)(v88 + 2LL * ((v52 >> 17) + 3073))
             + (512 - ((v52 >> 8) & 0x1FF)) * *(unsigned __int16 *)(v88 + 2LL * ((v52 >> 17) + 3072))) >> 9;
      }
      if ( v106 == 1 )
      {
        if ( !--v72 )
          goto LABEL_32;
        v43 = 2LL * v86;
        v44 = 2LL * v87;
        while ( 1 )
        {
          v12 = (unsigned __int16 *)((char *)v12 + v43);
          v45 = &v9[(unsigned __int64)v44 / 2];
          v11 = (unsigned __int16 *)((char *)v11 + v43);
          v13 = (unsigned __int16 *)((char *)v13 + v43);
          v46 = v8;
          v47 = v7;
          v7 = (_WORD *)((char *)v7 + v44);
          v8 = (_WORD *)((char *)v8 + v44);
          v48 = v6;
          v6 = (_WORD *)((char *)v6 + v44);
          if ( !a3 )
            v45 = v9;
          v9 = v45;
          if ( v20 != *v12 || v76 != *v11 || v77 != *v13 )
            goto LABEL_14;
          *v6 = *v48;
          *v7 = *v47;
          *v8 = *v46;
          if ( a3 )
            *v45 = v45[-v87];
          if ( !--v72 )
            goto LABEL_32;
        }
      }
      if ( v106 == 2 )
        break;
      v56 = v75;
      v57 = *v93;
      if ( a3 )
        *v75 = v57;
      else
        *v9 = v57;
      if ( !--v72 )
        goto LABEL_32;
      v58 = 2LL * v86;
      v59 = 2LL * v87;
      while ( 1 )
      {
        v93 = (__int16 *)((char *)v93 + v58);
        v56 = (__int16 *)((char *)v56 + v59);
        v12 = (unsigned __int16 *)((char *)v12 + v58);
        v90 = v9;
        v9 = (__int16 *)((char *)v9 + v59);
        v84 = v7;
        v7 = (_WORD *)((char *)v7 + v59);
        v11 = (unsigned __int16 *)((char *)v11 + v58);
        v13 = (unsigned __int16 *)((char *)v13 + v58);
        v60 = v8;
        v8 = (_WORD *)((char *)v8 + v59);
        v61 = v6;
        v6 = (_WORD *)((char *)v6 + v59);
        if ( !a3 )
          v56 = v75;
        v75 = v56;
        if ( v20 != *v12 )
          break;
        v75 = v56;
        if ( v76 != *v11 )
          break;
        v75 = v56;
        if ( v77 != *v13 )
          break;
        *v6 = *v61;
        *v7 = *v84;
        *v8 = *v60;
        if ( a3 )
        {
          *v9 = *v90;
          *v56 = *v93;
        }
        else
        {
          *v9 = *v93;
        }
        v62 = v72-- == 1;
        v75 = v56;
        if ( v62 )
          goto LABEL_32;
      }
LABEL_14:
      v3 = v92;
    }
    v63 = 0;
    if ( a3 )
    {
      if ( !v105 )
        v63 = *v75;
      *v75 = v63;
    }
    else
    {
      if ( !v105 )
        v63 = *v9;
      *v9 = v63;
    }
    v62 = v72 == 1;
    v64 = --v72;
    if ( !v62 )
    {
      v65 = 2LL * v86;
      v66 = 2LL * v87;
      while ( 1 )
      {
        v12 = (unsigned __int16 *)((char *)v12 + v65);
        v67 = &v75[(unsigned __int64)v66 / 2];
        v91 = v9;
        v11 = (unsigned __int16 *)((char *)v11 + v65);
        v85 = v6;
        v13 = (unsigned __int16 *)((char *)v13 + v65);
        v6 = (_WORD *)((char *)v6 + v66);
        v9 = (__int16 *)((char *)v9 + v66);
        v68 = v8;
        v8 = (_WORD *)((char *)v8 + v66);
        v69 = v7;
        v7 = (_WORD *)((char *)v7 + v66);
        if ( !a3 )
          v67 = v75;
        v75 = v67;
        if ( v20 != *v12 || v76 != *v11 || v77 != *v13 )
          break;
        *v6 = *v85;
        *v7 = *v69;
        *v8 = *v68;
        if ( a3 )
        {
          *v9 = *v91;
          v70 = 0;
          if ( !v105 )
            v70 = *v75;
          *v75 = v70;
        }
        else
        {
          v71 = 0;
          if ( !v105 )
            v71 = *v9;
          *v9 = v71;
        }
        v62 = v64-- == 1;
        v72 = v64;
        if ( v62 )
          goto LABEL_32;
      }
      v75 = v67;
      goto LABEL_14;
    }
LABEL_32:
    v3 = v92;
    v5 = a1;
    v17 = v79;
    v18 = v98;
LABEL_33:
    v79 = v17 - 1;
    if ( v17 != 1 )
    {
      ++v18;
      v49 = (unsigned int)(*(_DWORD *)(v5 + 16) * v18);
      v12 = (unsigned __int16 *)(v49 + *(_QWORD *)(v5 + 32));
      v11 = (unsigned __int16 *)(v49 + *(_QWORD *)(v5 + 40));
      v93 = (__int16 *)(v49 + *(_QWORD *)(v5 + 56));
      v16 = v81;
      v13 = (unsigned __int16 *)(v49 + *(_QWORD *)(v5 + 48));
      v98 = v18;
      v50 = (unsigned int)(*(_DWORD *)(v5 + 20) * v18);
      v6 = (_WORD *)(v50 + *(_QWORD *)(v5 + 96));
      v7 = (_WORD *)(v50 + *(_QWORD *)(v5 + 104));
      v8 = (_WORD *)(v50 + *(_QWORD *)(v5 + 112));
      v9 = (__int16 *)(v50 + *(_QWORD *)(v5 + 120));
      if ( a3 )
      {
        v75 = (__int16 *)(v50 + *(_QWORD *)(v5 + 128));
        v16 = v81;
      }
      v17 = v79;
      continue;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800120d0  mov     rax, rsp
0x1800120d3  mov     [rax+8], rcx
0x1800120d7  push    r12
0x1800120d9  push    r13
0x1800120db  push    r15
0x1800120dd  sub     rsp, 0E0h
0x1800120e4  mov     r15, [rdx+18h]
0x1800120e8  movzx   r12d, r8b
0x1800120ec  mov     [rsp+0F8h+var_A8], r15
0x1800120f1  mov     r13, rcx
0x1800120f4  test    r15, r15
0x1800120f7  jz      loc_1800129BB
0x1800120fd  mov     r9, [rcx+60h]
0x180012101  mov     r10, [rcx+68h]
0x180012105  mov     r11, [rcx+70h]
0x180012109  mov     [rax+18h], rbx
0x18001210d  mov     rbx, [rcx+78h]
0x180012111  mov     [rax-20h], rbp
0x180012115  mov     ebp, [r13+1Ch]
0x180012119  mov     [rax-28h], rsi
0x18001211d  mov     rsi, [rcx+28h]
0x180012121  mov     [rax-30h], rdi
0x180012125  mov     rdi, [rcx+20h]
0x180012129  mov     [rax-38h], r14
0x18001212d  mov     rax, [rcx+38h]
0x180012131  mov     r14, [rcx+30h]
0x180012135  mov     [rsp+0F8h+var_A0], rax
0x18001213a  mov     rax, [rcx+80h]
0x180012141  mov     [rsp+0F8h+var_E8], rax
0x180012146  mov     rax, [rdx+28h]
0x18001214a  mov     [rsp+0F8h+var_B8], rax
0x18001214f  mov     rax, [rdx+40h]
0x180012153  mov     [rsp+0F8h+var_80], rax
0x180012158  xor     eax, eax
0x18001215a  test    r8b, r8b
0x18001215d  setnz   al
0x180012160  add     eax, 3
0x180012163  imul    ecx, eax, 421h
0x180012169  mov     [rsp+0F8h+var_D4], eax
0x18001216d  mov     [rsp+0F8h+var_84], ecx
0x180012171  mov     ecx, eax
0x180012173  shl     ecx, 5
0x180012176  mov     [rsp+0F8h+var_98], ecx
0x18001217a  imul    ecx, eax, 401h
0x180012180  mov     [rsp+0F8h+var_94], ecx
0x180012184  imul    ecx, eax, 420h
0x18001218a  shl     eax, 0Ah
0x18001218d  mov     [rsp+0F8h+var_90], eax
0x180012191  mov     eax, [r13+18h]
0x180012195  cdq
0x180012196  sub     eax, edx
0x180012198  mov     [rsp+0F8h+var_8C], ecx
0x18001219c  sar     eax, 1
0x18001219e  mov     [rsp+0F8h+var_C0], eax
0x1800121a2  mov     eax, ebp
0x1800121a4  cdq
0x1800121a5  sub     eax, edx
0x1800121a7  movzx   edx, byte ptr [r13+0A1h]
0x1800121af  sar     eax, 1
0x1800121b1  mov     [rsp+0F8h+var_BC], eax
0x1800121b5  mov     eax, [r13+8]
0x1800121b9  mov     ecx, eax
0x1800121bb  imul    ecx, [r13+18h]
0x1800121c0  mov     [rsp+0F8h+arg_8], dl
0x1800121c7  cmp     ecx, [r13+10h]
0x1800121cb  jz      short loc_18001222D
0x1800121cd  mov     ecx, [r13+0Ch]
0x1800121d1  cmp     byte ptr [r13+0A0h], 0
0x1800121d9  mov     [rsp+0F8h+var_D8], ecx
0x1800121dd  mov     [rsp+0F8h+var_D0], eax
0x1800121e1  jz      short loc_180012244
0x1800121e3  mov     [rsp+0F8h+arg_18], 4
0x1800121eb  xor     edx, edx
0x1800121ed  mov     [rsp+0F8h+var_88], edx
0x1800121f1  test    ecx, ecx
0x1800121f3  jnz     short loc_180012258
0x1800121f5  mov     r14, [rsp+0F8h+var_38]
0x1800121fd  xor     eax, eax
0x1800121ff  mov     rdi, [rsp+0F8h+var_30]
0x180012207  mov     rsi, [rsp+0F8h+var_28]
0x18001220f  mov     rbp, [rsp+0F8h+var_20]
0x180012217  mov     rbx, [rsp+0F8h+arg_10]
0x18001221f  add     rsp, 0E0h
0x180012226  pop     r15
0x180012228  pop     r13
0x18001222a  pop     r12
0x18001222c  retn
0x18001222d  mov     ecx, eax
0x18001222f  imul    ecx, ebp
0x180012232  cmp     ecx, [r13+14h]
0x180012236  jnz     short loc_1800121CD
0x180012238  imul    eax, [r13+0Ch]
0x18001223d  mov     ecx, 1
0x180012242  jmp     short loc_1800121D1
0x180012244  test    dl, dl
0x180012246  setnz   al
0x180012249  inc     al
0x18001224b  mov     [rsp+0F8h+arg_18], al
0x180012252  mov     eax, [rsp+0F8h+var_D0]
0x180012256  jmp     short loc_1800121EB
0x180012258  mov     r8d, 100h
0x18001225e  mov     [rsp+0F8h+var_F8], eax
0x180012261  test    eax, eax
0x180012263  jz      loc_1800126D2
0x180012269  lea     rax, [r15+2]
0x18001226d  mov     [rsp+0F8h+var_70], rax
0x180012275  mov     eax, [rsp+0F8h+var_84]
0x180012279  lea     rdx, [rax+rax]
0x18001227d  mov     rax, [rsp+0F8h+var_80]
0x180012282  mov     [rsp+0F8h+var_40], rdx
0x18001228a  lea     rcx, [rdx+rax]
0x18001228e  mov     [rsp+0F8h+var_68], rcx
0x180012296  lea     rcx, [rax+2]
0x18001229a  add     rax, 2
0x18001229e  mov     [rsp+0F8h+var_60], rcx
0x1800122a6  add     rax, rdx
0x1800122a9  mov     [rsp+0F8h+var_58], rax
0x1800122b1  lea     rax, [rcx+2]
0x1800122b5  mov     [rsp+0F8h+var_50], rax
0x1800122bd  lea     rax, [rcx+2]
0x1800122c1  add     rax, rdx
0x1800122c4  mov     [rsp+0F8h+var_48], rax
0x1800122cc  jmp     short loc_1800122DE
0x1800122ce  mov     [rsp+0F8h+var_E8], rax
0x1800122d3  mov     r15, [rsp+0F8h+var_A8]
0x1800122d8  mov     r8d, 100h
0x1800122de  movzx   r13d, word ptr [rdi]
0x1800122e2  movzx   ecx, r13w
0x1800122e6  movzx   eax, r13w
0x1800122ea  shr     cx, 8
0x1800122ee  sub     ax, cx
0x1800122f1  movzx   edx, al
0x1800122f4  movzx   eax, ax
0x1800122f7  shr     rax, 8
0x1800122fb  lea     rcx, [rax+rax]
0x1800122ff  mov     eax, r8d
0x180012302  movzx   ebp, word ptr [rcx+r15]
0x180012307  sub     eax, edx
0x180012309  imul    ebp, eax
0x18001230c  movzx   eax, word ptr [r15+rcx+2]
0x180012312  imul    eax, edx
0x180012315  add     ebp, eax
0x180012317  movzx   eax, word ptr [rsi]
0x18001231a  movzx   ecx, ax
0x18001231d  mov     [rsp+0F8h+var_E0], ax
0x180012322  shr     cx, 8
0x180012326  sub     ax, cx
0x180012329  shr     ebp, 8
0x18001232c  movzx   edx, al
0x18001232f  shr     ax, 8
0x180012333  add     ax, r8w
0x180012337  movzx   eax, ax
0x18001233a  lea     rcx, [rax+rax]
0x18001233e  mov     eax, 100h
0x180012343  movzx   r8d, word ptr [rcx+r15]
0x180012348  sub     eax, edx
0x18001234a  imul    r8d, eax
0x18001234e  movzx   eax, word ptr [r15+rcx+2]
0x180012354  imul    eax, edx
0x180012357  add     r8d, eax
0x18001235a  movzx   eax, word ptr [r14]
0x18001235e  movzx   ecx, ax
0x180012361  mov     [rsp+0F8h+var_DE], ax
0x180012366  shr     cx, 8
0x18001236a  sub     ax, cx
0x18001236d  shr     r8d, 8
0x180012371  movzx   edx, al
0x180012374  mov     ecx, 200h
0x180012379  shr     ax, 8
0x18001237d  add     ax, cx
0x180012380  movzx   eax, ax
0x180012383  lea     rcx, [rax+rax]
0x180012387  mov     eax, 100h
0x18001238c  movzx   r15d, word ptr [rcx+r15]
0x180012391  sub     eax, edx
0x180012393  imul    r15d, eax
0x180012397  mov     rax, [rsp+0F8h+var_70]
0x18001239f  movzx   eax, word ptr [rax+rcx]
0x1800123a3  mov     ecx, ebp
0x1800123a5  imul    eax, edx
0x1800123a8  and     ecx, 0F800h
0x1800123ae  shl     ecx, 5
0x1800123b1  and     ebp, 7FFh
0x1800123b7  add     r15d, eax
0x1800123ba  mov     eax, r8d
0x1800123bd  and     eax, 0F800h
0x1800123c2  shr     r15d, 8
0x1800123c6  add     ecx, eax
0x1800123c8  and     r8d, 7FFh
0x1800123cf  shr     ecx, 6
0x1800123d2  mov     eax, r15d
0x1800123d5  shr     eax, 0Bh
0x1800123d8  and     r15d, 7FFh
0x1800123df  add     ecx, eax
0x1800123e1  mov     eax, 800h
0x1800123e6  imul    ecx, [rsp+0F8h+var_D4]
0x1800123eb  lea     rdx, [rcx+rcx]
0x1800123ef  mov     [rsp+0F8h+var_C8], rdx
0x1800123f4  cmp     r15d, ebp
0x1800123f7  jnb     loc_1800127EC
0x1800123fd  cmp     r8d, ebp
0x180012400  jb      loc_180012822
0x180012406  mov     ecx, [rsp+0F8h+var_98]
0x18001240a  sub     eax, r8d
0x18001240d  mov     [rsp+0F8h+var_DC], eax
0x180012411  mov     eax, r8d
0x180012414  sub     eax, ebp
0x180012416  mov     [rsp+0F8h+var_F4], eax
0x18001241a  mov     eax, ebp
0x18001241c  sub     eax, r15d
0x18001241f  mov     [rsp+0F8h+var_F0], eax
0x180012423  mov     eax, [rsp+0F8h+var_8C]
0x180012427  lea     r8, [rax+rax]
0x18001242b  mov     rbp, [rsp+0F8h+var_80]
0x180012430  add     rbp, rdx
0x180012433  mov     eax, ecx
0x180012435  add     rax, rax
0x180012438  mov     [rsp+0F8h+var_B0], r8
0x18001243d  mov     [rsp+0F8h+var_78], rax
0x180012445  movzx   ecx, word ptr [rax+rbp]
0x180012449  imul    ecx, [rsp+0F8h+var_F4]
0x18001244e  movzx   eax, word ptr [r8+rbp]
0x180012453  imul    eax, [rsp+0F8h+var_F0]
0x180012458  add     ecx, eax
0x18001245a  mov     rax, [rsp+0F8h+var_68]
0x180012462  movzx   eax, word ptr [rdx+rax]
0x180012466  imul    eax, r15d
0x18001246a  add     ecx, eax
0x18001246c  movzx   eax, word ptr [rbp+0]
0x180012470  mov     ebp, [rsp+0F8h+var_DC]
0x180012474  imul    eax, ebp
0x180012477  add     ecx, eax
0x180012479  mov     edx, ecx
0x18001247b  shr     edx, 10h
0x18001247e  add     edx, ecx
0x180012480  mov     eax, edx
0x180012482  shr     eax, 0Ah
0x180012485  sub     edx, eax
0x180012487  mov     eax, 200h
0x18001248c  mov     r8d, edx
0x18001248f  shr     edx, 11h
0x180012492  mov     ecx, edx
0x180012494  mov     rdx, [rsp+0F8h+var_B8]
0x180012499  shr     r8d, 8
0x18001249d  and     r8d, 1FFh
0x1800124a4  sub     eax, r8d
0x1800124a7  movzx   edx, word ptr [rdx+rcx*2]
0x1800124ab  inc     ecx
0x1800124ad  imul    edx, eax
0x1800124b0  mov     rax, [rsp+0F8h+var_B8]
0x1800124b5  movzx   eax, word ptr [rax+rcx*2]
0x1800124b9  mov     rcx, [rsp+0F8h+var_60]
0x1800124c1  imul    eax, r8d
0x1800124c5  add     edx, eax
0x1800124c7  mov     rax, [rsp+0F8h+var_C8]
0x1800124cc  add     rcx, rax
0x1800124cf  shr     edx, 9
0x1800124d2  mov     [r9], dx
0x1800124d6  mov     rdx, [rsp+0F8h+var_58]
0x1800124de  movzx   edx, word ptr [rdx+rax]
0x1800124e2  mov     rax, [rsp+0F8h+var_78]
0x1800124ea  imul    edx, r15d
0x1800124ee  movzx   eax, word ptr [rcx+rax]
0x1800124f2  imul    eax, [rsp+0F8h+var_F4]
0x1800124f7  add     edx, eax
0x1800124f9  mov     rax, [rsp+0F8h+var_B0]
0x1800124fe  movzx   eax, word ptr [rcx+rax]
0x180012502  imul    eax, [rsp+0F8h+var_F0]
0x180012507  movzx   ecx, word ptr [rcx]
0x18001250a  imul    ecx, ebp
0x18001250d  add     edx, eax
0x18001250f  add     ecx, edx
0x180012511  mov     rdx, [rsp+0F8h+var_B8]
0x180012516  mov     eax, ecx
0x180012518  shr     eax, 10h
0x18001251b  add     ecx, eax
0x18001251d  mov     eax, ecx
0x18001251f  shr     eax, 0Ah
0x180012522  sub     ecx, eax
0x180012524  mov     eax, 200h
0x180012529  mov     r8d, ecx
0x18001252c  shr     ecx, 11h
0x18001252f  add     ecx, 400h
0x180012535  shr     r8d, 8
0x180012539  and     r8d, 1FFh
0x180012540  sub     eax, r8d
0x180012543  movzx   edx, word ptr [rdx+rcx*2]
0x180012547  inc     ecx
0x180012549  imul    edx, eax
0x18001254c  mov     rax, [rsp+0F8h+var_B8]
0x180012551  movzx   eax, word ptr [rax+rcx*2]
0x180012555  imul    eax, r8d
0x180012559  add     edx, eax
0x18001255b  mov     rax, [rsp+0F8h+var_C8]
0x180012560  mov     rcx, [rsp+0F8h+var_B0]
0x180012565  mov     r8, [rsp+0F8h+var_48]
0x18001256d  shr     edx, 9
0x180012570  mov     [r10], dx
0x180012574  mov     rdx, [rsp+0F8h+var_50]
0x18001257c  add     rdx, rax
  ... truncated ...
```
