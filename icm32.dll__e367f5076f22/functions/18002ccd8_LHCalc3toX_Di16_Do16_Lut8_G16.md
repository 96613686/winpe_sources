# LHCalc3toX_Di16_Do16_Lut8_G16

- ea: `0x18002ccd8`
- end: `0x18002d589`
- name: `LHCalc3toX_Di16_Do16_Lut8_G16`
- size: `2225`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800268e0`
- `0x180028b70`

## callees

- `0x18002ccd8`

## pseudocode

```c
__int64 __fastcall LHCalc3toX_Di16_Do16_Lut8_G16(__int64 a1, _QWORD *a2, char a3)
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
  v81 = 273 * v15;
  v77 = 16 * v15;
  v90 = *(_BYTE *)(v4 + 161);
  v78 = 257 * v15;
  v80 = 272 * v15;
  v79 = v15 << 8;
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
                                                                      + 512))) >> 14)
             + ((16
               * ((((unsigned __int8)(v54 - HIBYTE(v54))
                  * *(unsigned __int16 *)(v84 + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8) + 2)
                  + (256 - (unsigned __int8)(v54 - HIBYTE(v54)))
                  * (unsigned int)*(unsigned __int16 *)(v84
                                                      + 2
                                                      * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8))) >> 2)
                & 0xF000)
               + ((((unsigned __int8)(v55 - HIBYTE(v55))
                  * *(unsigned __int16 *)(v84
                                        + 2LL * (unsigned __int16)(((unsigned __int16)(v55 - HIBYTE(v55)) >> 8) + 256)
                                        + 2)
                  + (256 - (unsigned __int8)(v55 - HIBYTE(v55)))
                  * (unsigned int)*(unsigned __int16 *)(v84
                                                      + 2LL
                                                      * (unsigned __int16)(((unsigned __int16)(v55 - HIBYTE(v55)) >> 8)
                                                                         + 256))) >> 2)
                & 0xF000)) >> 8));
        v22 = (((unsigned __int8)(v54 - HIBYTE(v54))
              * *(unsigned __int16 *)(v84 + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8) + 2)
              + (256 - (unsigned __int8)(v54 - HIBYTE(v54)))
              * (unsigned int)*(unsigned __int16 *)(v84
                                                  + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8))) >> 2)
            & 0xFFF;
        v23 = (((unsigned __int8)(v55 - HIBYTE(v55))
              * *(unsigned __int16 *)(v84
                                    + 2LL * (unsigned __int16)(((unsigned __int16)(v55 - HIBYTE(v55)) >> 8) + 256)
                                    + 2)
              + (256 - (unsigned __int8)(v55 - HIBYTE(v55)))
              * (unsigned int)*(unsigned __int16 *)(v84
                                                  + 2LL
                                                  * (unsigned __int16)(((unsigned __int16)(v55 - HIBYTE(v55)) >> 8) + 256))) >> 2)
            & 0xFFF;
        v24 = (((unsigned __int8)(v56 - HIBYTE(v56))
              * *(unsigned __int16 *)(v84
                                    + 2LL * (unsigned __int16)(((unsigned __int16)(v56 - HIBYTE(v56)) >> 8) + 512)
                                    + 2)
              + (256 - (unsigned __int8)(v56 - HIBYTE(v56)))
              * (unsigned int)*(unsigned __int16 *)(v84
                                                  + 2LL
                                                  * (unsigned __int16)(((unsigned __int16)(v56 - HIBYTE(v56)) >> 8) + 512))) >> 2)
            & 0xFFF;
        v58 = (unsigned int)v21;
        if ( v24 < v22 )
        {
          if ( v23 < v22 )
          {
            v26 = v79;
            v25 = 4096 - v22;
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
                  & 0xFFF;
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
                & 0xFFF;
          }
          else
          {
            v26 = v77;
            v25 = 4096 - v23;
            v31 = (((unsigned __int8)(v54 - HIBYTE(v54))
                  * *(unsigned __int16 *)(v84 + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8) + 2)
                  + (256 - (unsigned __int8)(v54 - HIBYTE(v54)))
                  * (unsigned int)*(unsigned __int16 *)(v84
                                                      + 2
                                                      * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8))) >> 2)
                & 0xFFF;
            v27 = v23 - v22;
          }
          v29 = v80;
          v28 = v31 - v24;
          goto LABEL_27;
        }
        if ( v23 < v22 )
        {
          v25 = 4096 - v24;
          v27 = v24 - v22;
          v30 = (((unsigned __int8)(v54 - HIBYTE(v54))
                * *(unsigned __int16 *)(v84 + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8) + 2)
                + (256 - (unsigned __int8)(v54 - HIBYTE(v54)))
                * (unsigned int)*(unsigned __int16 *)(v84
                                                    + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8))) >> 2)
              & 0xFFF;
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
              & 0xFFF;
          v28 = v30 - v23;
          goto LABEL_27;
        }
        if ( v24 < v23 )
        {
          v26 = v77;
          v27 = v23 - v24;
          v25 = 4096 - v23;
          v28 = v24 - v22;
        }
        else
        {
          v25 = 4096 - v24;
          v26 = v20;
          v27 = v24 - v23;
          v28 = v23 - v22;
        }
        v24 = (((unsigned __int8)(v54 - HIBYTE(v54))
              * *(unsigned __int16 *)(v84 + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8) + 2)
              + (256 - (unsigned __int8)(v54 - HIBYTE(v54)))
              * (unsigned int)*(unsigned __int16 *)(v84
                                                  + 2 * ((unsigned __int64)(unsigned __int16)(v54 - HIBYTE(v54)) >> 8))) >> 2)
            & 0xFFF;
        v29 = 17 * v20;
LABEL_27:
        *v10 = *(unsigned __int8 *)(((unsigned __int64)(v24 * *(unsigned __int8 *)(v21 + v85)
                                                      + v28 * *(unsigned __int8 *)(v21 + v69 + v29)
                                                      + v27 * *(unsigned __int8 *)(v21 + v69 + v26)
                                                      + v25 * *(unsigned __int8 *)(v69 + v21)) >> 10)
                                  + v83);
        v32 = v69 + v21;
        *v11 = *(unsigned __int8 *)(((v25 * *(unsigned __int8 *)(v32 + 1)
                                    + v24 * *(unsigned __int8 *)(v58 + v86)
                                    + v28 * *(unsigned __int8 *)(v32 + v29 + 1)
                                    + v27 * *(unsigned __int8 *)(v26 + v32 + 1)) >> 10)
                                  + 1024
                                  + v83);
        v3 = a3;
        *v63 = *(unsigned __int8 *)(((v25 * *(unsigned __int8 *)(v69 + v58 + 2)
                                    + v24 * *(unsigned __int8 *)(v58 + v87)
                                    + v28 * *(unsigned __int8 *)(v69 + v58 + v29 + 2)
                                    + v27 * *(unsigned __int8 *)(v26 + v69 + v58 + 2)) >> 10)
                                  + 2048
                                  + v83);
        if ( a3 )
          *v12 = *(unsigned __int8 *)(((v28 * *(unsigned __int8 *)(v32 + v29 + 3)
                                      + v27 * *(unsigned __int8 *)(v32 + v26 + 3)
                                      + v24 * *(unsigned __int8 *)(v81 + v32 + 3)
                                      + v25 * *(unsigned __int8 *)(v32 + 3)) >> 10)
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
0x18002ccd8  mov     [rsp+arg_10], r8b
0x18002ccdd  mov     [rsp+arg_0], rcx
0x18002cce2  push    rbx
0x18002cce3  push    rbp
0x18002cce4  push    rsi
0x18002cce5  push    rdi
0x18002cce6  push    r12
0x18002cce8  push    r13
0x18002ccea  push    r14
0x18002ccec  push    r15
0x18002ccee  sub     rsp, 0B8h
0x18002ccf5  mov     rax, [rdx+18h]
0x18002ccf9  mov     bl, r8b
0x18002ccfc  mov     [rsp+0F8h+var_70], rax
0x18002cd04  mov     r9, rcx
0x18002cd07  test    rax, rax
0x18002cd0a  jnz     short loc_18002CD16
0x18002cd0c  mov     eax, 57h ; 'W'
0x18002cd11  jmp     loc_18002D575
0x18002cd16  mov     rax, [rcx+38h]
0x18002cd1a  mov     r10, [rcx+70h]
0x18002cd1e  mov     rbp, [rcx+20h]
0x18002cd22  mov     rdi, [rcx+28h]
0x18002cd26  mov     rsi, [rcx+30h]
0x18002cd2a  mov     r14, [rcx+80h]
0x18002cd31  mov     r12, [rcx+60h]
0x18002cd35  mov     r13, [rcx+68h]
0x18002cd39  mov     r8, [rcx+78h]
0x18002cd3d  mov     rcx, [rdx+28h]
0x18002cd41  mov     r11, [rdx+40h]
0x18002cd45  mov     [rsp+0F8h+var_98], rax
0x18002cd4a  mov     al, bl
0x18002cd4c  neg     al
0x18002cd4e  mov     [rsp+0F8h+var_78], rcx
0x18002cd56  mov     [rsp+0F8h+var_D8], r10
0x18002cd5b  mov     r10b, [r9+0A1h]
0x18002cd62  sbb     ecx, ecx
0x18002cd64  neg     ecx
0x18002cd66  mov     [rsp+0F8h+var_E0], rbp
0x18002cd6b  add     ecx, 3
0x18002cd6e  mov     [rsp+0F8h+var_B8], rdi
0x18002cd73  imul    eax, ecx, 111h
0x18002cd79  mov     [rsp+0F8h+var_F0], ecx
0x18002cd7d  mov     [rsp+0F8h+var_B0], rsi
0x18002cd82  mov     [rsp+0F8h+var_A8], r14
0x18002cd87  mov     [rsp+0F8h+var_C0], r11
0x18002cd8c  mov     [rsp+0F8h+var_80], eax
0x18002cd90  mov     eax, ecx
0x18002cd92  shl     eax, 4
0x18002cd95  mov     [rsp+0F8h+var_90], eax
0x18002cd99  imul    eax, ecx, 101h
0x18002cd9f  mov     [rsp+0F8h+arg_8], r10b
0x18002cda7  mov     [rsp+0F8h+var_8C], eax
0x18002cdab  imul    eax, ecx, 110h
0x18002cdb1  mov     [rsp+0F8h+var_84], eax
0x18002cdb5  mov     eax, ecx
0x18002cdb7  shl     eax, 8
0x18002cdba  mov     ecx, 2
0x18002cdbf  mov     [rsp+0F8h+var_88], eax
0x18002cdc3  mov     eax, [r9+18h]
0x18002cdc7  cdq
0x18002cdc8  idiv    ecx
0x18002cdca  mov     [rsp+0F8h+var_D0], eax
0x18002cdce  mov     eax, [r9+1Ch]
0x18002cdd2  cdq
0x18002cdd3  idiv    ecx
0x18002cdd5  mov     [rsp+0F8h+var_CC], eax
0x18002cdd9  mov     eax, [r9+8]
0x18002cddd  mov     ecx, eax
0x18002cddf  imul    ecx, [r9+18h]
0x18002cde4  cmp     ecx, [r9+10h]
0x18002cde8  jnz     short loc_18002CE03
0x18002cdea  mov     ecx, eax
0x18002cdec  imul    ecx, [r9+1Ch]
0x18002cdf1  cmp     ecx, [r9+14h]
0x18002cdf5  jnz     short loc_18002CE03
0x18002cdf7  imul    eax, [r9+0Ch]
0x18002cdfc  mov     edx, 1
0x18002ce01  jmp     short loc_18002CE07
0x18002ce03  mov     edx, [r9+0Ch]
0x18002ce07  cmp     byte ptr [r9+0A0h], 0
0x18002ce0f  mov     [rsp+0F8h+var_C8], edx
0x18002ce13  mov     [rsp+0F8h+var_C4], eax
0x18002ce17  jz      short loc_18002CE23
0x18002ce19  mov     [rsp+0F8h+arg_18], 4
0x18002ce21  jmp     short loc_18002CE32
0x18002ce23  test    r10b, r10b
0x18002ce26  setnz   cl
0x18002ce29  inc     cl
0x18002ce2b  mov     [rsp+0F8h+arg_18], cl
0x18002ce32  xor     r10d, r10d
0x18002ce35  mov     [rsp+0F8h+var_7C], r10d
0x18002ce3a  test    edx, edx
0x18002ce3c  jz      loc_18002D573
0x18002ce42  mov     r15d, eax
0x18002ce45  test    eax, eax
0x18002ce47  jz      loc_18002D4DD
0x18002ce4d  mov     eax, [rsp+0F8h+var_80]
0x18002ce51  mov     r9d, [rsp+0F8h+var_F0]
0x18002ce56  lea     rcx, [rax+r11]
0x18002ce5a  mov     [rsp+0F8h+var_68], rcx
0x18002ce62  lea     rcx, [rax+1]
0x18002ce66  add     rcx, r11
0x18002ce69  add     rax, 2
0x18002ce6d  add     rax, r11
0x18002ce70  mov     [rsp+0F8h+var_60], rcx
0x18002ce78  mov     [rsp+0F8h+var_58], rax
0x18002ce80  movzx   eax, word ptr [rbp+0]
0x18002ce84  mov     r10, [rsp+0F8h+var_70]
0x18002ce8c  movzx   ecx, ax
0x18002ce8f  mov     [rsp+0F8h+var_F8], ax
0x18002ce93  shr     cx, 8
0x18002ce97  sub     ax, cx
0x18002ce9a  movzx   edx, al
0x18002ce9d  movzx   ecx, ax
0x18002cea0  mov     eax, 100h
0x18002cea5  sub     eax, edx
0x18002cea7  shr     rcx, 8
0x18002ceab  movzx   ebp, word ptr [r10+rcx*2]
0x18002ceb0  imul    ebp, eax
0x18002ceb3  movzx   eax, word ptr [r10+rcx*2+2]
0x18002ceb9  imul    eax, edx
0x18002cebc  add     ebp, eax
0x18002cebe  movzx   eax, word ptr [rdi]
0x18002cec1  movzx   ecx, ax
0x18002cec4  mov     [rsp+0F8h+var_F6], ax
0x18002cec9  shr     cx, 8
0x18002cecd  mov     edi, 100h
0x18002ced2  sub     ax, cx
0x18002ced5  shr     ebp, 2
0x18002ced8  movzx   edx, al
0x18002cedb  shr     ax, 8
0x18002cedf  add     ax, di
0x18002cee2  movzx   ecx, ax
0x18002cee5  mov     eax, edi
0x18002cee7  sub     eax, edx
0x18002cee9  movzx   ebx, word ptr [r10+rcx*2]
0x18002ceee  imul    ebx, eax
0x18002cef1  movzx   eax, word ptr [r10+rcx*2+2]
0x18002cef7  imul    eax, edx
0x18002cefa  add     ebx, eax
0x18002cefc  movzx   eax, word ptr [rsi]
0x18002ceff  movzx   ecx, ax
0x18002cf02  mov     [rsp+0F8h+var_F4], ax
0x18002cf07  shr     cx, 8
0x18002cf0b  sub     ax, cx
0x18002cf0e  shr     ebx, 2
0x18002cf11  movzx   edx, al
0x18002cf14  mov     ecx, 200h
0x18002cf19  shr     ax, 8
0x18002cf1d  add     ax, cx
0x18002cf20  movzx   ecx, ax
0x18002cf23  mov     eax, edi
0x18002cf25  sub     eax, edx
0x18002cf27  movzx   r10d, word ptr [r10+rcx*2]
0x18002cf2c  imul    r10d, eax
0x18002cf30  mov     rax, [rsp+0F8h+var_70]
0x18002cf38  movzx   eax, word ptr [rax+rcx*2+2]
0x18002cf3d  mov     ecx, ebp
0x18002cf3f  imul    eax, edx
0x18002cf42  mov     edx, 0F000h
0x18002cf47  and     ecx, edx
0x18002cf49  and     edx, ebx
0x18002cf4b  shl     ecx, 4
0x18002cf4e  add     edx, ecx
0x18002cf50  shr     edx, 8
0x18002cf53  add     r10d, eax
0x18002cf56  shr     r10d, 2
0x18002cf5a  mov     eax, r10d
0x18002cf5d  shr     eax, 0Ch
0x18002cf60  add     edx, eax
0x18002cf62  mov     eax, 0FFFh
0x18002cf67  imul    edx, r9d
0x18002cf6b  and     ebp, eax
0x18002cf6d  and     ebx, eax
0x18002cf6f  and     r10d, eax
0x18002cf72  lea     r11d, [rax+1]
0x18002cf76  mov     [rsp+0F8h+var_E8], rdx
0x18002cf7b  cmp     r10d, ebp
0x18002cf7e  jb      short loc_18002CFC4
0x18002cf80  cmp     ebx, ebp
0x18002cf82  jb      short loc_18002CFB5
0x18002cf84  cmp     r10d, ebx
0x18002cf87  jb      short loc_18002CF9B
0x18002cf89  sub     r11d, r10d
0x18002cf8c  mov     eax, r9d
0x18002cf8f  sub     r10d, ebx
0x18002cf92  sub     ebx, ebp
0x18002cf94  mov     edi, r10d
0x18002cf97  mov     esi, ebx
0x18002cf99  jmp     short loc_18002CFAC
0x18002cf9b  mov     eax, [rsp+0F8h+var_90]
0x18002cf9f  mov     edi, ebx
0x18002cfa1  sub     edi, r10d
0x18002cfa4  sub     r11d, ebx
0x18002cfa7  mov     esi, r10d
0x18002cfaa  sub     esi, ebp
0x18002cfac  mov     r10d, ebp
0x18002cfaf  imul    ecx, r9d, 11h
0x18002cfb3  jmp     short loc_18002D001
0x18002cfb5  sub     r11d, r10d
0x18002cfb8  mov     edi, r10d
0x18002cfbb  sub     edi, ebp
0x18002cfbd  mov     esi, ebp
0x18002cfbf  mov     eax, r9d
0x18002cfc2  jmp     short loc_18002CFEB
0x18002cfc4  cmp     ebx, ebp
0x18002cfc6  jb      short loc_18002CFD7
0x18002cfc8  mov     eax, [rsp+0F8h+var_90]
0x18002cfcc  sub     r11d, ebx
0x18002cfcf  mov     edi, ebx
0x18002cfd1  mov     esi, ebp
0x18002cfd3  sub     edi, ebp
0x18002cfd5  jmp     short loc_18002CFFA
0x18002cfd7  mov     eax, [rsp+0F8h+var_88]
0x18002cfdb  sub     r11d, ebp
0x18002cfde  mov     edi, ebp
0x18002cfe0  cmp     r10d, ebx
0x18002cfe3  jb      short loc_18002CFF6
0x18002cfe5  sub     edi, r10d
0x18002cfe8  mov     esi, r10d
0x18002cfeb  mov     ecx, [rsp+0F8h+var_8C]
0x18002cfef  mov     r10d, ebx
0x18002cff2  sub     esi, ebx
0x18002cff4  jmp     short loc_18002D001
0x18002cff6  sub     edi, ebx
0x18002cff8  mov     esi, ebx
0x18002cffa  mov     ecx, [rsp+0F8h+var_84]
0x18002cffe  sub     esi, r10d
0x18002d001  mov     ebx, eax
0x18002d003  mov     rax, [rsp+0F8h+var_C0]
0x18002d008  add     rax, rdx
0x18002d00b  mov     r9, [rsp+0F8h+var_78]
0x18002d013  mov     ebp, ecx
0x18002d015  mov     [rsp+0F8h+var_A0], rbx
0x18002d01a  movzx   ecx, byte ptr [rax+rbx]
0x18002d01e  movzx   eax, byte ptr [rax+rbp]
0x18002d022  imul    eax, esi
0x18002d025  imul    ecx, edi
0x18002d028  add     ecx, eax
0x18002d02a  mov     rax, [rsp+0F8h+var_68]
0x18002d032  movzx   eax, byte ptr [rdx+rax]
0x18002d036  imul    eax, r10d
0x18002d03a  add     ecx, eax
0x18002d03c  mov     rax, [rsp+0F8h+var_C0]
0x18002d041  movzx   eax, byte ptr [rax+rdx]
0x18002d045  imul    eax, r11d
0x18002d049  add     eax, ecx
0x18002d04b  mov     rcx, [rsp+0F8h+var_C0]
0x18002d050  add     rcx, rdx
0x18002d053  shr     rax, 0Ah
0x18002d057  movzx   eax, byte ptr [rax+r9]
0x18002d05c  mov     r9, [rsp+0F8h+var_60]
0x18002d064  mov     [r12], ax
0x18002d069  movzx   edx, byte ptr [rbx+rcx+1]
0x18002d06e  movzx   eax, byte ptr [rcx+rbp+1]
0x18002d073  imul    eax, esi
0x18002d076  imul    edx, edi
0x18002d079  add     edx, eax
0x18002d07b  mov     rax, [rsp+0F8h+var_E8]
0x18002d080  movzx   eax, byte ptr [rax+r9]
0x18002d085  mov     r9, [rsp+0F8h+var_78]
0x18002d08d  imul    eax, r10d
0x18002d091  add     edx, eax
0x18002d093  movzx   eax, byte ptr [rcx+1]
0x18002d097  imul    eax, r11d
0x18002d09b  add     edx, eax
0x18002d09d  shr     edx, 0Ah
0x18002d0a0  add     edx, 400h
0x18002d0a6  movzx   ecx, byte ptr [rdx+r9]
0x18002d0ab  mov     rdx, [rsp+0F8h+var_E8]
0x18002d0b0  add     rdx, [rsp+0F8h+var_C0]
0x18002d0b5  mov     [r13+0], cx
0x18002d0ba  movzx   ecx, byte ptr [rbx+rdx+2]
0x18002d0bf  movzx   eax, byte ptr [rdx+rbp+2]
0x18002d0c4  mov     rbx, [rsp+0F8h+var_58]
0x18002d0cc  imul    eax, esi
0x18002d0cf  imul    ecx, edi
0x18002d0d2  add     ecx, eax
0x18002d0d4  mov     rax, [rsp+0F8h+var_E8]
0x18002d0d9  movzx   eax, byte ptr [rax+rbx]
0x18002d0dd  mov     bl, [rsp+0F8h+arg_10]
0x18002d0e4  imul    eax, r10d
0x18002d0e8  add     ecx, eax
0x18002d0ea  movzx   eax, byte ptr [rdx+2]
0x18002d0ee  imul    eax, r11d
0x18002d0f2  add     ecx, eax
0x18002d0f4  mov     rax, [rsp+0F8h+var_D8]
0x18002d0f9  shr     ecx, 0Ah
0x18002d0fc  add     ecx, 800h
0x18002d102  movzx   ecx, byte ptr [rcx+r9]
0x18002d107  mov     [rax], cx
0x18002d10a  test    bl, bl
0x18002d10c  jz      short loc_18002D151
0x18002d10e  mov     ecx, [rsp+0F8h+var_80]
0x18002d112  mov     rax, [rsp+0F8h+var_A0]
0x18002d117  movzx   ecx, byte ptr [rcx+rdx+3]
0x18002d11c  movzx   eax, byte ptr [rdx+rax+3]
0x18002d121  imul    eax, edi
0x18002d124  imul    ecx, r10d
  ... truncated ...
```
