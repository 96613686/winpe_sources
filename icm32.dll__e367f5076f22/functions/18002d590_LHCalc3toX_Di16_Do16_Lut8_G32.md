# LHCalc3toX_Di16_Do16_Lut8_G32

- ea: `0x18002d590`
- end: `0x18002de41`
- name: `LHCalc3toX_Di16_Do16_Lut8_G32`
- size: `2225`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800268f0`
- `0x180028b80`

## callees

- `0x18002d590`

## pseudocode

```c
__int64 __fastcall LHCalc3toX_Di16_Do16_Lut8_G32(__int64 a1, _QWORD *a2, char a3)
{
  char v3; // bl
  __int64 v4; // r9
  _WORD *v6; // rbp
  _WORD *v7; // rdi
  _WORD *v8; // rsi
  _WORD *v9; // r14
  _WORD *v10; // r12
  _WORD *v11; // r13
  _WORD *v12; // r8
  __int64 v13; // r11
  char v14; // r10
  int v15; // ecx
  int v16; // eax
  int v17; // edx
  int v18; // r10d
  int v19; // r15d
  unsigned int v20; // r9d
  __int64 v21; // rdx
  unsigned int v22; // ebp
  unsigned int v23; // ebx
  unsigned int v24; // r10d
  unsigned int v25; // r11d
  unsigned int v26; // eax
  unsigned int v27; // edi
  unsigned int v28; // esi
  unsigned int v29; // ecx
  unsigned int v30; // esi
  unsigned int v31; // esi
  __int64 v32; // rdx
  _WORD *v33; // r11
  __int64 v34; // rdx
  __int64 v35; // rcx
  _WORD *v36; // rax
  _WORD *v37; // r10
  __int16 v38; // ax
  __int64 v39; // rdx
  __int64 v40; // rcx
  _WORD *v41; // rax
  _WORD *v42; // r10
  __int16 v43; // ax
  __int16 v44; // ax
  _WORD *v45; // rcx
  __int16 v46; // ax
  __int64 v47; // r10
  __int64 v48; // rdx
  _WORD *v49; // rcx
  _WORD *v50; // rax
  bool v51; // zf
  __int64 v52; // rcx
  __int64 v53; // rcx
  unsigned __int16 v54; // [rsp+0h] [rbp-F8h]
  unsigned __int16 v55; // [rsp+2h] [rbp-F6h]
  unsigned __int16 v56; // [rsp+4h] [rbp-F4h]
  int v57; // [rsp+8h] [rbp-F0h]
  __int64 v58; // [rsp+10h] [rbp-E8h]
  _WORD *v59; // [rsp+10h] [rbp-E8h]
  _WORD *v60; // [rsp+10h] [rbp-E8h]
  _WORD *v61; // [rsp+10h] [rbp-E8h]
  _WORD *v62; // [rsp+18h] [rbp-E0h]
  _WORD *v63; // [rsp+20h] [rbp-D8h]
  _WORD *v64; // [rsp+20h] [rbp-D8h]
  int v65; // [rsp+28h] [rbp-D0h]
  int v66; // [rsp+2Ch] [rbp-CCh]
  int v67; // [rsp+30h] [rbp-C8h]
  int v68; // [rsp+34h] [rbp-C4h]
  __int64 v69; // [rsp+38h] [rbp-C0h]
  _WORD *v70; // [rsp+40h] [rbp-B8h]
  _WORD *v71; // [rsp+48h] [rbp-B0h]
  _WORD *v72; // [rsp+50h] [rbp-A8h]
  _WORD *v73; // [rsp+58h] [rbp-A0h]
  _WORD *v74; // [rsp+58h] [rbp-A0h]
  _WORD *v75; // [rsp+58h] [rbp-A0h]
  _WORD *v76; // [rsp+60h] [rbp-98h]
  int v77; // [rsp+68h] [rbp-90h]
  int v78; // [rsp+6Ch] [rbp-8Ch]
  int v79; // [rsp+70h] [rbp-88h]
  int v80; // [rsp+74h] [rbp-84h]
  unsigned int v81; // [rsp+78h] [rbp-80h]
  int v82; // [rsp+7Ch] [rbp-7Ch]
  __int64 v83; // [rsp+80h] [rbp-78h]
  __int64 v84; // [rsp+88h] [rbp-70h]
  __int64 v85; // [rsp+90h] [rbp-68h]
  __int64 v86; // [rsp+98h] [rbp-60h]
  __int64 v87; // [rsp+A0h] [rbp-58h]
  _WORD *v88; // [rsp+A8h] [rbp-50h]
  char v90; // [rsp+108h] [rbp+10h]
  char v92; // [rsp+118h] [rbp+20h]

  v3 = a3;
  v84 = a2[3];
  v4 = a1;
  if ( !v84 )
    return 87;
  v6 = *(_WORD **)(a1 + 32);
  v7 = *(_WORD **)(a1 + 40);
  v8 = *(_WORD **)(a1 + 48);
  v9 = *(_WORD **)(a1 + 128);
  v10 = *(_WORD **)(a1 + 96);
  v11 = *(_WORD **)(a1 + 104);
  v12 = *(_WORD **)(a1 + 120);
  v13 = a2[8];
  v76 = *(_WORD **)(a1 + 56);
  v83 = a2[5];
  v63 = *(_WORD **)(a1 + 112);
  v14 = *(_BYTE *)(a1 + 161);
  v62 = v6;
  v15 = (v3 != 0) + 3;
  v70 = v7;
  v57 = v15;
  v71 = v8;
  v72 = v9;
  v69 = v13;
  v81 = 1057 * v15;
  v77 = 32 * v15;
  v90 = *(_BYTE *)(v4 + 161);
  v78 = 1025 * v15;
  v80 = 1056 * v15;
  v79 = v15 << 10;
  v65 = *(_DWORD *)(v4 + 24) / 2;
  v66 = *(_DWORD *)(v4 + 28) / 2;
  v16 = *(_DWORD *)(v4 + 8);
  if ( *(_DWORD *)(v4 + 24) * v16 == *(_DWORD *)(v4 + 16) && *(_DWORD *)(v4 + 28) * v16 == *(_DWORD *)(v4 + 20) )
  {
    v16 *= *(_DWORD *)(v4 + 12);
    v17 = 1;
  }
  else
  {
    v17 = *(_DWORD *)(v4 + 12);
  }
  v67 = v17;
  v68 = v16;
  if ( *(_BYTE *)(v4 + 160) )
    v92 = 4;
  else
    v92 = (v14 != 0) + 1;
  v18 = 0;
  v82 = 0;
  if ( !v17 )
    return 0;
  while ( 2 )
  {
    v19 = v16;
    if ( !v16 )
      goto LABEL_84;
    v20 = v57;
    v85 = v81 + v13;
    v86 = v13 + v81 + 1LL;
    v87 = v13 + v81 + 2LL;
    do
    {
      while ( 1 )
      {
        v54 = *v6;
        v55 = *v7;
        v56 = *v8;
        v21 = v20
            * ((((unsigned __int8)(v56 - HIBYTE(v56))
               * *(unsigned __int16 *)(v84
                                     + 2LL * (unsigned __int16)(((unsigned __int16)(v56 - HIBYTE(v56)) >> 8) + 512)
                                     + 2)
               + (256 - (unsigned __int8)(v56 - HIBYTE(v56)))
               * (unsigned int)*(unsigned __int16 *)(v84
                                                   + 2LL
                                                   * (unsigned __int16)(((unsigned __int16)(v56 - HIBYTE(v56)) >> 8)
                                                                      + 512))) >> 13)
             + ((32
               * ((((unsigned __int8)(v54 - HIBYTE(v54))
                  * *(unsigned __int16 *)(v84 + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8) + 2)
                  + (256 - (unsigned __int8)(v54 - HIBYTE(v54)))
                  * (unsigned int)*(unsigned __int16 *)(v84
                                                      + 2
                                                      * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8))) >> 2)
                & 0xF800)
               + ((((unsigned __int8)(v55 - HIBYTE(v55))
                  * *(unsigned __int16 *)(v84
                                        + 2LL * (unsigned __int16)(((unsigned __int16)(v55 - HIBYTE(v55)) >> 8) + 256)
                                        + 2)
                  + (256 - (unsigned __int8)(v55 - HIBYTE(v55)))
                  * (unsigned int)*(unsigned __int16 *)(v84
                                                      + 2LL
                                                      * (unsigned __int16)(((unsigned __int16)(v55 - HIBYTE(v55)) >> 8)
                                                                         + 256))) >> 2)
                & 0xF800)) >> 6));
        v22 = (((unsigned __int8)(v54 - HIBYTE(v54))
              * *(unsigned __int16 *)(v84 + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8) + 2)
              + (256 - (unsigned __int8)(v54 - HIBYTE(v54)))
              * (unsigned int)*(unsigned __int16 *)(v84
                                                  + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8))) >> 2)
            & 0x7FF;
        v23 = (((unsigned __int8)(v55 - HIBYTE(v55))
              * *(unsigned __int16 *)(v84
                                    + 2LL * (unsigned __int16)(((unsigned __int16)(v55 - HIBYTE(v55)) >> 8) + 256)
                                    + 2)
              + (256 - (unsigned __int8)(v55 - HIBYTE(v55)))
              * (unsigned int)*(unsigned __int16 *)(v84
                                                  + 2LL
                                                  * (unsigned __int16)(((unsigned __int16)(v55 - HIBYTE(v55)) >> 8) + 256))) >> 2)
            & 0x7FF;
        v24 = (((unsigned __int8)(v56 - HIBYTE(v56))
              * *(unsigned __int16 *)(v84
                                    + 2LL * (unsigned __int16)(((unsigned __int16)(v56 - HIBYTE(v56)) >> 8) + 512)
                                    + 2)
              + (256 - (unsigned __int8)(v56 - HIBYTE(v56)))
              * (unsigned int)*(unsigned __int16 *)(v84
                                                  + 2LL
                                                  * (unsigned __int16)(((unsigned __int16)(v56 - HIBYTE(v56)) >> 8) + 512))) >> 2)
            & 0x7FF;
        v58 = (unsigned int)v21;
        if ( v24 < v22 )
        {
          if ( v23 < v22 )
          {
            v26 = v79;
            v25 = 2048 - v22;
            if ( v24 >= v23 )
            {
              v27 = v22 - v24;
              v30 = (((unsigned __int8)(v56 - HIBYTE(v56))
                    * *(unsigned __int16 *)(v84
                                          + 2LL * (unsigned __int16)(((unsigned __int16)(v56 - HIBYTE(v56)) >> 8) + 512)
                                          + 2)
                    + (256 - (unsigned __int8)(v56 - HIBYTE(v56)))
                    * (unsigned int)*(unsigned __int16 *)(v84
                                                        + 2LL
                                                        * (unsigned __int16)(((unsigned __int16)(v56 - HIBYTE(v56)) >> 8)
                                                                           + 512))) >> 2)
                  & 0x7FF;
              goto LABEL_24;
            }
            v27 = v22 - v23;
            v31 = (((unsigned __int8)(v55 - HIBYTE(v55))
                  * *(unsigned __int16 *)(v84
                                        + 2LL * (unsigned __int16)(((unsigned __int16)(v55 - HIBYTE(v55)) >> 8) + 256)
                                        + 2)
                  + (256 - (unsigned __int8)(v55 - HIBYTE(v55)))
                  * (unsigned int)*(unsigned __int16 *)(v84
                                                      + 2LL
                                                      * (unsigned __int16)(((unsigned __int16)(v55 - HIBYTE(v55)) >> 8)
                                                                         + 256))) >> 2)
                & 0x7FF;
          }
          else
          {
            v26 = v77;
            v25 = 2048 - v23;
            v31 = (((unsigned __int8)(v54 - HIBYTE(v54))
                  * *(unsigned __int16 *)(v84 + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8) + 2)
                  + (256 - (unsigned __int8)(v54 - HIBYTE(v54)))
                  * (unsigned int)*(unsigned __int16 *)(v84
                                                      + 2
                                                      * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8))) >> 2)
                & 0x7FF;
            v27 = v23 - v22;
          }
          v29 = v80;
          v28 = v31 - v24;
          goto LABEL_27;
        }
        if ( v23 < v22 )
        {
          v25 = 2048 - v24;
          v27 = v24 - v22;
          v30 = (((unsigned __int8)(v54 - HIBYTE(v54))
                * *(unsigned __int16 *)(v84 + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8) + 2)
                + (256 - (unsigned __int8)(v54 - HIBYTE(v54)))
                * (unsigned int)*(unsigned __int16 *)(v84
                                                    + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8))) >> 2)
              & 0x7FF;
          v26 = v20;
LABEL_24:
          v29 = v78;
          v24 = (((unsigned __int8)(v55 - HIBYTE(v55))
                * *(unsigned __int16 *)(v84
                                      + 2LL * (unsigned __int16)(((unsigned __int16)(v55 - HIBYTE(v55)) >> 8) + 256)
                                      + 2)
                + (256 - (unsigned __int8)(v55 - HIBYTE(v55)))
                * (unsigned int)*(unsigned __int16 *)(v84
                                                    + 2LL
                                                    * (unsigned __int16)(((unsigned __int16)(v55 - HIBYTE(v55)) >> 8)
                                                                       + 256))) >> 2)
              & 0x7FF;
          v28 = v30 - v23;
          goto LABEL_27;
        }
        if ( v24 < v23 )
        {
          v26 = v77;
          v27 = v23 - v24;
          v25 = 2048 - v23;
          v28 = v24 - v22;
        }
        else
        {
          v25 = 2048 - v24;
          v26 = v20;
          v27 = v24 - v23;
          v28 = v23 - v22;
        }
        v24 = (((unsigned __int8)(v54 - HIBYTE(v54))
              * *(unsigned __int16 *)(v84 + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8) + 2)
              + (256 - (unsigned __int8)(v54 - HIBYTE(v54)))
              * (unsigned int)*(unsigned __int16 *)(v84
                                                  + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8))) >> 2)
            & 0x7FF;
        v29 = 33 * v20;
LABEL_27:
        *v10 = *(unsigned __int8 *)(((unsigned __int64)(v24 * *(unsigned __int8 *)(v21 + v85)
                                                      + v28 * *(unsigned __int8 *)(v21 + v69 + v29)
                                                      + v27 * *(unsigned __int8 *)(v21 + v69 + v26)
                                                      + v25 * *(unsigned __int8 *)(v69 + v21)) >> 9)
                                  + v83);
        v32 = v69 + v21;
        *v11 = *(unsigned __int8 *)(((v25 * *(unsigned __int8 *)(v32 + 1)
                                    + v24 * *(unsigned __int8 *)(v58 + v86)
                                    + v28 * *(unsigned __int8 *)(v32 + v29 + 1)
                                    + v27 * *(unsigned __int8 *)(v26 + v32 + 1)) >> 9)
                                  + 1024
                                  + v83);
        v3 = a3;
        *v63 = *(unsigned __int8 *)(((v25 * *(unsigned __int8 *)(v69 + v58 + 2)
                                    + v24 * *(unsigned __int8 *)(v58 + v87)
                                    + v28 * *(unsigned __int8 *)(v69 + v58 + v29 + 2)
                                    + v27 * *(unsigned __int8 *)(v26 + v69 + v58 + 2)) >> 9)
                                  + 2048
                                  + v83);
        if ( a3 )
          *v12 = *(unsigned __int8 *)(((v28 * *(unsigned __int8 *)(v32 + v29 + 3)
                                      + v27 * *(unsigned __int8 *)(v32 + v26 + 3)
                                      + v24 * *(unsigned __int8 *)(v81 + v32 + 3)
                                      + v25 * *(unsigned __int8 *)(v32 + 3)) >> 9)
                                    + 3072
                                    + v83);
        v33 = v63;
        *v10 |= *v10 << 8;
        *v11 |= *v11 << 8;
        *v63 |= *v63 << 8;
        if ( a3 )
          *v12 |= *v12 << 8;
        if ( v92 == 1 )
        {
          if ( !--v19 )
            goto LABEL_83;
          v34 = 2LL * v65;
          v7 = v70;
          v35 = 2LL * v66;
          v8 = v71;
          v6 = v62;
          do
          {
            v6 = (_WORD *)((char *)v6 + v34);
            v59 = v11;
            v11 = (_WORD *)((char *)v11 + v35);
            v73 = v10;
            v10 = (_WORD *)((char *)v10 + v35);
            v36 = &v12[(unsigned __int64)v35 / 2];
            v7 = (_WORD *)((char *)v7 + v34);
            v8 = (_WORD *)((char *)v8 + v34);
            v37 = v33;
            v33 = (_WORD *)((char *)v33 + v35);
            if ( !a3 )
              v36 = v12;
            v12 = v36;
            if ( v54 != *v6 || v55 != *v7 || v56 != *v8 )
              break;
            *v10 = *v73;
            *v11 = *v59;
            *v33 = *v37;
            if ( a3 )
              *v36 = v36[-v66];
            --v19;
          }
          while ( v19 );
          v9 = v72;
          goto LABEL_67;
        }
        if ( v92 == 2 )
          break;
        v45 = v76;
        v46 = *v76;
        if ( a3 )
          *v9 = v46;
        else
          *v12 = v46;
        if ( !--v19 )
          goto LABEL_83;
        v47 = 2LL * v65;
        v7 = v70;
        v48 = 2LL * v66;
        v8 = v71;
        v6 = v62;
        while ( 1 )
        {
          v6 = (_WORD *)((char *)v6 + v47);
          v76 = &v45[(unsigned __int64)v47 / 2];
          v7 = (_WORD *)((char *)v7 + v47);
          v88 = v12;
          v8 = (_WORD *)((char *)v8 + v47);
          v61 = v33;
          v33 = (_WORD *)((char *)v33 + v48);
          v75 = v11;
          v11 = (_WORD *)((char *)v11 + v48);
          v62 = v6;
          v12 = (_WORD *)((char *)v12 + v48);
          v70 = v7;
          v49 = &v9[(unsigned __int64)v48 / 2];
          v71 = v8;
          v50 = v10;
          v63 = v33;
          v10 = (_WORD *)((char *)v10 + v48);
          if ( !a3 )
            v49 = v9;
          v20 = v57;
          v9 = v49;
          v72 = v49;
          if ( v54 != *v6 )
            break;
          v20 = v57;
          v72 = v49;
          if ( v55 == *v7 )
          {
            v72 = v49;
            if ( v56 == *v8 )
            {
              *v10 = *v50;
              *v11 = *v75;
              *v33 = *v61;
              if ( a3 )
              {
                *v12 = *v88;
                *v49 = *v76;
              }
              else
              {
                *v12 = *v76;
              }
              v72 = v49;
              v45 = v76;
              if ( --v19 )
                continue;
            }
          }
          goto LABEL_82;
        }
      }
      v38 = 0;
      if ( a3 )
      {
        if ( !v90 )
          v38 = *v9;
        *v9 = v38;
      }
      else
      {
        if ( !v90 )
          v38 = *v12;
        *v12 = v38;
      }
      if ( !--v19 )
        break;
      v39 = 2LL * v65;
      v7 = v70;
      v40 = 2LL * v66;
      v8 = v71;
      v6 = v62;
      do
      {
        v6 = (_WORD *)((char *)v6 + v39);
        v64 = v12;
        v12 = (_WORD *)((char *)v12 + v40);
        v60 = v11;
        v11 = (_WORD *)((char *)v11 + v40);
        v74 = v10;
        v10 = (_WORD *)((char *)v10 + v40);
        v41 = &v9[(unsigned __int64)v40 / 2];
        v7 = (_WORD *)((char *)v7 + v39);
        v8 = (_WORD *)((char *)v8 + v39);
        v42 = v33;
        v33 = (_WORD *)((char *)v33 + v40);
        if ( !a3 )
          v41 = v9;
        v9 = v41;
        if ( v54 != *v6 || v55 != *v7 || v56 != *v8 )
          break;
        *v10 = *v74;
        *v11 = *v60;
        *v33 = *v42;
        if ( a3 )
        {
          *v12 = *v64;
          v43 = 0;
          if ( !v90 )
            v43 = *v9;
          *v9 = v43;
        }
        else
        {
          v44 = 0;
          if ( !v90 )
            v44 = *v12;
          *v12 = v44;
        }
        --v19;
      }
      while ( v19 );
      v72 = v9;
LABEL_67:
      v20 = v57;
      v63 = v33;
      v70 = v7;
      v71 = v8;
      v62 = v6;
LABEL_82:
      ;
    }
    while ( v19 );
LABEL_83:
    v4 = a1;
    v17 = v67;
    v18 = v82;
    v13 = v69;
LABEL_84:
    v51 = v17-- == 1;
    v67 = v17;
    if ( !v51 )
    {
      ++v18;
      v52 = (unsigned int)(*(_DWORD *)(v4 + 16) * v18);
      v6 = (_WORD *)(v52 + *(_QWORD *)(v4 + 32));
      v76 = (_WORD *)(v52 + *(_QWORD *)(v4 + 56));
      v7 = (_WORD *)(v52 + *(_QWORD *)(v4 + 40));
      v8 = (_WORD *)(v52 + *(_QWORD *)(v4 + 48));
      v82 = v18;
      v62 = v6;
      v53 = (unsigned int)(*(_DWORD *)(v4 + 20) * v18);
      v70 = v7;
      v71 = v8;
      v10 = (_WORD *)(v53 + *(_QWORD *)(v4 + 96));
      v11 = (_WORD *)(v53 + *(_QWORD *)(v4 + 104));
      v63 = (_WORD *)(v53 + *(_QWORD *)(v4 + 112));
      v16 = v68;
      v12 = (_WORD *)(v53 + *(_QWORD *)(v4 + 120));
      if ( v3 )
      {
        v9 = (_WORD *)(v53 + *(_QWORD *)(v4 + 128));
        v72 = v9;
      }
      continue;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18002d590  mov     [rsp+arg_10], r8b
0x18002d595  mov     [rsp+arg_0], rcx
0x18002d59a  push    rbx
0x18002d59b  push    rbp
0x18002d59c  push    rsi
0x18002d59d  push    rdi
0x18002d59e  push    r12
0x18002d5a0  push    r13
0x18002d5a2  push    r14
0x18002d5a4  push    r15
0x18002d5a6  sub     rsp, 0B8h
0x18002d5ad  mov     rax, [rdx+18h]
0x18002d5b1  mov     bl, r8b
0x18002d5b4  mov     [rsp+0F8h+var_70], rax
0x18002d5bc  mov     r9, rcx
0x18002d5bf  test    rax, rax
0x18002d5c2  jnz     short loc_18002D5CE
0x18002d5c4  mov     eax, 57h ; 'W'
0x18002d5c9  jmp     loc_18002DE2D
0x18002d5ce  mov     rax, [rcx+38h]
0x18002d5d2  mov     r10, [rcx+70h]
0x18002d5d6  mov     rbp, [rcx+20h]
0x18002d5da  mov     rdi, [rcx+28h]
0x18002d5de  mov     rsi, [rcx+30h]
0x18002d5e2  mov     r14, [rcx+80h]
0x18002d5e9  mov     r12, [rcx+60h]
0x18002d5ed  mov     r13, [rcx+68h]
0x18002d5f1  mov     r8, [rcx+78h]
0x18002d5f5  mov     rcx, [rdx+28h]
0x18002d5f9  mov     r11, [rdx+40h]
0x18002d5fd  mov     [rsp+0F8h+var_98], rax
0x18002d602  mov     al, bl
0x18002d604  neg     al
0x18002d606  mov     [rsp+0F8h+var_78], rcx
0x18002d60e  mov     [rsp+0F8h+var_D8], r10
0x18002d613  mov     r10b, [r9+0A1h]
0x18002d61a  sbb     ecx, ecx
0x18002d61c  neg     ecx
0x18002d61e  mov     [rsp+0F8h+var_E0], rbp
0x18002d623  add     ecx, 3
0x18002d626  mov     [rsp+0F8h+var_B8], rdi
0x18002d62b  imul    eax, ecx, 421h
0x18002d631  mov     [rsp+0F8h+var_F0], ecx
0x18002d635  mov     [rsp+0F8h+var_B0], rsi
0x18002d63a  mov     [rsp+0F8h+var_A8], r14
0x18002d63f  mov     [rsp+0F8h+var_C0], r11
0x18002d644  mov     [rsp+0F8h+var_80], eax
0x18002d648  mov     eax, ecx
0x18002d64a  shl     eax, 5
0x18002d64d  mov     [rsp+0F8h+var_90], eax
0x18002d651  imul    eax, ecx, 401h
0x18002d657  mov     [rsp+0F8h+arg_8], r10b
0x18002d65f  mov     [rsp+0F8h+var_8C], eax
0x18002d663  imul    eax, ecx, 420h
0x18002d669  mov     [rsp+0F8h+var_84], eax
0x18002d66d  mov     eax, ecx
0x18002d66f  shl     eax, 0Ah
0x18002d672  mov     ecx, 2
0x18002d677  mov     [rsp+0F8h+var_88], eax
0x18002d67b  mov     eax, [r9+18h]
0x18002d67f  cdq
0x18002d680  idiv    ecx
0x18002d682  mov     [rsp+0F8h+var_D0], eax
0x18002d686  mov     eax, [r9+1Ch]
0x18002d68a  cdq
0x18002d68b  idiv    ecx
0x18002d68d  mov     [rsp+0F8h+var_CC], eax
0x18002d691  mov     eax, [r9+8]
0x18002d695  mov     ecx, eax
0x18002d697  imul    ecx, [r9+18h]
0x18002d69c  cmp     ecx, [r9+10h]
0x18002d6a0  jnz     short loc_18002D6BB
0x18002d6a2  mov     ecx, eax
0x18002d6a4  imul    ecx, [r9+1Ch]
0x18002d6a9  cmp     ecx, [r9+14h]
0x18002d6ad  jnz     short loc_18002D6BB
0x18002d6af  imul    eax, [r9+0Ch]
0x18002d6b4  mov     edx, 1
0x18002d6b9  jmp     short loc_18002D6BF
0x18002d6bb  mov     edx, [r9+0Ch]
0x18002d6bf  cmp     byte ptr [r9+0A0h], 0
0x18002d6c7  mov     [rsp+0F8h+var_C8], edx
0x18002d6cb  mov     [rsp+0F8h+var_C4], eax
0x18002d6cf  jz      short loc_18002D6DB
0x18002d6d1  mov     [rsp+0F8h+arg_18], 4
0x18002d6d9  jmp     short loc_18002D6EA
0x18002d6db  test    r10b, r10b
0x18002d6de  setnz   cl
0x18002d6e1  inc     cl
0x18002d6e3  mov     [rsp+0F8h+arg_18], cl
0x18002d6ea  xor     r10d, r10d
0x18002d6ed  mov     [rsp+0F8h+var_7C], r10d
0x18002d6f2  test    edx, edx
0x18002d6f4  jz      loc_18002DE2B
0x18002d6fa  mov     r15d, eax
0x18002d6fd  test    eax, eax
0x18002d6ff  jz      loc_18002DD95
0x18002d705  mov     eax, [rsp+0F8h+var_80]
0x18002d709  mov     r9d, [rsp+0F8h+var_F0]
0x18002d70e  lea     rcx, [rax+r11]
0x18002d712  mov     [rsp+0F8h+var_68], rcx
0x18002d71a  lea     rcx, [rax+1]
0x18002d71e  add     rcx, r11
0x18002d721  add     rax, 2
0x18002d725  add     rax, r11
0x18002d728  mov     [rsp+0F8h+var_60], rcx
0x18002d730  mov     [rsp+0F8h+var_58], rax
0x18002d738  movzx   eax, word ptr [rbp+0]
0x18002d73c  mov     r10, [rsp+0F8h+var_70]
0x18002d744  movzx   ecx, ax
0x18002d747  mov     [rsp+0F8h+var_F8], ax
0x18002d74b  shr     cx, 8
0x18002d74f  sub     ax, cx
0x18002d752  movzx   edx, al
0x18002d755  movzx   ecx, ax
0x18002d758  mov     eax, 100h
0x18002d75d  sub     eax, edx
0x18002d75f  shr     rcx, 8
0x18002d763  movzx   ebp, word ptr [r10+rcx*2]
0x18002d768  imul    ebp, eax
0x18002d76b  movzx   eax, word ptr [r10+rcx*2+2]
0x18002d771  imul    eax, edx
0x18002d774  add     ebp, eax
0x18002d776  movzx   eax, word ptr [rdi]
0x18002d779  movzx   ecx, ax
0x18002d77c  mov     [rsp+0F8h+var_F6], ax
0x18002d781  shr     cx, 8
0x18002d785  mov     edi, 100h
0x18002d78a  sub     ax, cx
0x18002d78d  shr     ebp, 2
0x18002d790  movzx   edx, al
0x18002d793  shr     ax, 8
0x18002d797  add     ax, di
0x18002d79a  movzx   ecx, ax
0x18002d79d  mov     eax, edi
0x18002d79f  sub     eax, edx
0x18002d7a1  movzx   ebx, word ptr [r10+rcx*2]
0x18002d7a6  imul    ebx, eax
0x18002d7a9  movzx   eax, word ptr [r10+rcx*2+2]
0x18002d7af  imul    eax, edx
0x18002d7b2  add     ebx, eax
0x18002d7b4  movzx   eax, word ptr [rsi]
0x18002d7b7  movzx   ecx, ax
0x18002d7ba  mov     [rsp+0F8h+var_F4], ax
0x18002d7bf  shr     cx, 8
0x18002d7c3  sub     ax, cx
0x18002d7c6  shr     ebx, 2
0x18002d7c9  movzx   edx, al
0x18002d7cc  mov     ecx, 200h
0x18002d7d1  shr     ax, 8
0x18002d7d5  add     ax, cx
0x18002d7d8  movzx   ecx, ax
0x18002d7db  mov     eax, edi
0x18002d7dd  sub     eax, edx
0x18002d7df  movzx   r10d, word ptr [r10+rcx*2]
0x18002d7e4  imul    r10d, eax
0x18002d7e8  mov     rax, [rsp+0F8h+var_70]
0x18002d7f0  movzx   eax, word ptr [rax+rcx*2+2]
0x18002d7f5  mov     ecx, ebp
0x18002d7f7  imul    eax, edx
0x18002d7fa  mov     edx, 0F800h
0x18002d7ff  and     ecx, edx
0x18002d801  and     edx, ebx
0x18002d803  shl     ecx, 5
0x18002d806  add     edx, ecx
0x18002d808  shr     edx, 6
0x18002d80b  add     r10d, eax
0x18002d80e  shr     r10d, 2
0x18002d812  mov     eax, r10d
0x18002d815  shr     eax, 0Bh
0x18002d818  add     edx, eax
0x18002d81a  mov     eax, 7FFh
0x18002d81f  imul    edx, r9d
0x18002d823  and     ebp, eax
0x18002d825  and     ebx, eax
0x18002d827  and     r10d, eax
0x18002d82a  lea     r11d, [rax+1]
0x18002d82e  mov     [rsp+0F8h+var_E8], rdx
0x18002d833  cmp     r10d, ebp
0x18002d836  jb      short loc_18002D87C
0x18002d838  cmp     ebx, ebp
0x18002d83a  jb      short loc_18002D86D
0x18002d83c  cmp     r10d, ebx
0x18002d83f  jb      short loc_18002D853
0x18002d841  sub     r11d, r10d
0x18002d844  mov     eax, r9d
0x18002d847  sub     r10d, ebx
0x18002d84a  sub     ebx, ebp
0x18002d84c  mov     edi, r10d
0x18002d84f  mov     esi, ebx
0x18002d851  jmp     short loc_18002D864
0x18002d853  mov     eax, [rsp+0F8h+var_90]
0x18002d857  mov     edi, ebx
0x18002d859  sub     edi, r10d
0x18002d85c  sub     r11d, ebx
0x18002d85f  mov     esi, r10d
0x18002d862  sub     esi, ebp
0x18002d864  mov     r10d, ebp
0x18002d867  imul    ecx, r9d, 21h ; '!'
0x18002d86b  jmp     short loc_18002D8B9
0x18002d86d  sub     r11d, r10d
0x18002d870  mov     edi, r10d
0x18002d873  sub     edi, ebp
0x18002d875  mov     esi, ebp
0x18002d877  mov     eax, r9d
0x18002d87a  jmp     short loc_18002D8A3
0x18002d87c  cmp     ebx, ebp
0x18002d87e  jb      short loc_18002D88F
0x18002d880  mov     eax, [rsp+0F8h+var_90]
0x18002d884  sub     r11d, ebx
0x18002d887  mov     edi, ebx
0x18002d889  mov     esi, ebp
0x18002d88b  sub     edi, ebp
0x18002d88d  jmp     short loc_18002D8B2
0x18002d88f  mov     eax, [rsp+0F8h+var_88]
0x18002d893  sub     r11d, ebp
0x18002d896  mov     edi, ebp
0x18002d898  cmp     r10d, ebx
0x18002d89b  jb      short loc_18002D8AE
0x18002d89d  sub     edi, r10d
0x18002d8a0  mov     esi, r10d
0x18002d8a3  mov     ecx, [rsp+0F8h+var_8C]
0x18002d8a7  mov     r10d, ebx
0x18002d8aa  sub     esi, ebx
0x18002d8ac  jmp     short loc_18002D8B9
0x18002d8ae  sub     edi, ebx
0x18002d8b0  mov     esi, ebx
0x18002d8b2  mov     ecx, [rsp+0F8h+var_84]
0x18002d8b6  sub     esi, r10d
0x18002d8b9  mov     ebx, eax
0x18002d8bb  mov     rax, [rsp+0F8h+var_C0]
0x18002d8c0  add     rax, rdx
0x18002d8c3  mov     r9, [rsp+0F8h+var_78]
0x18002d8cb  mov     ebp, ecx
0x18002d8cd  mov     [rsp+0F8h+var_A0], rbx
0x18002d8d2  movzx   ecx, byte ptr [rax+rbx]
0x18002d8d6  movzx   eax, byte ptr [rax+rbp]
0x18002d8da  imul    eax, esi
0x18002d8dd  imul    ecx, edi
0x18002d8e0  add     ecx, eax
0x18002d8e2  mov     rax, [rsp+0F8h+var_68]
0x18002d8ea  movzx   eax, byte ptr [rdx+rax]
0x18002d8ee  imul    eax, r10d
0x18002d8f2  add     ecx, eax
0x18002d8f4  mov     rax, [rsp+0F8h+var_C0]
0x18002d8f9  movzx   eax, byte ptr [rax+rdx]
0x18002d8fd  imul    eax, r11d
0x18002d901  add     eax, ecx
0x18002d903  mov     rcx, [rsp+0F8h+var_C0]
0x18002d908  add     rcx, rdx
0x18002d90b  shr     rax, 9
0x18002d90f  movzx   eax, byte ptr [rax+r9]
0x18002d914  mov     r9, [rsp+0F8h+var_60]
0x18002d91c  mov     [r12], ax
0x18002d921  movzx   edx, byte ptr [rbx+rcx+1]
0x18002d926  movzx   eax, byte ptr [rcx+rbp+1]
0x18002d92b  imul    eax, esi
0x18002d92e  imul    edx, edi
0x18002d931  add     edx, eax
0x18002d933  mov     rax, [rsp+0F8h+var_E8]
0x18002d938  movzx   eax, byte ptr [rax+r9]
0x18002d93d  mov     r9, [rsp+0F8h+var_78]
0x18002d945  imul    eax, r10d
0x18002d949  add     edx, eax
0x18002d94b  movzx   eax, byte ptr [rcx+1]
0x18002d94f  imul    eax, r11d
0x18002d953  add     edx, eax
0x18002d955  shr     edx, 9
0x18002d958  add     edx, 400h
0x18002d95e  movzx   ecx, byte ptr [rdx+r9]
0x18002d963  mov     rdx, [rsp+0F8h+var_E8]
0x18002d968  add     rdx, [rsp+0F8h+var_C0]
0x18002d96d  mov     [r13+0], cx
0x18002d972  movzx   ecx, byte ptr [rbx+rdx+2]
0x18002d977  movzx   eax, byte ptr [rdx+rbp+2]
0x18002d97c  mov     rbx, [rsp+0F8h+var_58]
0x18002d984  imul    eax, esi
0x18002d987  imul    ecx, edi
0x18002d98a  add     ecx, eax
0x18002d98c  mov     rax, [rsp+0F8h+var_E8]
0x18002d991  movzx   eax, byte ptr [rax+rbx]
0x18002d995  mov     bl, [rsp+0F8h+arg_10]
0x18002d99c  imul    eax, r10d
0x18002d9a0  add     ecx, eax
0x18002d9a2  movzx   eax, byte ptr [rdx+2]
0x18002d9a6  imul    eax, r11d
0x18002d9aa  add     ecx, eax
0x18002d9ac  mov     rax, [rsp+0F8h+var_D8]
0x18002d9b1  shr     ecx, 9
0x18002d9b4  add     ecx, 800h
0x18002d9ba  movzx   ecx, byte ptr [rcx+r9]
0x18002d9bf  mov     [rax], cx
0x18002d9c2  test    bl, bl
0x18002d9c4  jz      short loc_18002DA09
0x18002d9c6  mov     ecx, [rsp+0F8h+var_80]
0x18002d9ca  mov     rax, [rsp+0F8h+var_A0]
0x18002d9cf  movzx   ecx, byte ptr [rcx+rdx+3]
0x18002d9d4  movzx   eax, byte ptr [rdx+rax+3]
0x18002d9d9  imul    eax, edi
0x18002d9dc  imul    ecx, r10d
  ... truncated ...
```
