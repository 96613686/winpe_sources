# sbrdecUpdateFreqScale

- ea: `0x18003dc20`
- end: `0x18003e204`
- name: `sbrdecUpdateFreqScale`
- size: `1508`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18003d9b0`
- `0x180042140`

## callees

- `0x1800017b0`
- `0x1800021a8`
- `0x18003d900`
- `0x18003dc20`
- `0x18003e210`

## pseudocode

```c
__int64 __fastcall sbrdecUpdateFreqScale(unsigned __int8 *a1, unsigned __int8 *a2, __int64 a3)
{
  unsigned __int16 v3; // bx
  struct HINSTANCE__ *v4; // r9
  __int64 v5; // rax
  unsigned __int8 *v7; // r15
  unsigned __int8 v8; // r12
  __int64 v9; // r14
  unsigned __int8 v11; // si
  __int64 v12; // rdx
  unsigned __int8 v13; // cl
  unsigned __int8 v14; // r14
  int v15; // esi
  int v16; // eax
  bool v17; // cc
  char v18; // cl
  float v19; // xmm2_4
  float v20; // xmm1_4
  unsigned __int8 v21; // r15
  float v22; // xmm0_4
  float v23; // xmm3_4
  unsigned __int8 v24; // r13
  float v25; // xmm0_4
  float v26; // xmm0_4
  unsigned __int8 v27; // si
  int v28; // ebx
  int v29; // edx
  __int64 v30; // rcx
  int v31; // edx
  int v32; // r8d
  char v33; // cl
  char v34; // dl
  unsigned __int8 *v35; // rdx
  __int64 v36; // rcx
  unsigned __int8 v37; // si
  float v38; // xmm0_4
  int v39; // ebx
  __int64 v40; // rcx
  int v41; // ebx
  int v42; // ecx
  int v43; // r14d
  unsigned __int8 v44; // r14
  unsigned __int8 v45; // r15
  int v46; // esi
  unsigned __int8 v47; // cl
  int v48; // edx
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v52; // [rsp+38h] [rbp-41h]
  _BYTE v53[2]; // [rsp+40h] [rbp-39h] BYREF
  char v54; // [rsp+42h] [rbp-37h]
  char v55; // [rsp+43h] [rbp-36h]
  char v56; // [rsp+44h] [rbp-35h]
  char v57; // [rsp+45h] [rbp-34h]
  char v58; // [rsp+46h] [rbp-33h]
  char v59; // [rsp+47h] [rbp-32h]
  char v60; // [rsp+48h] [rbp-31h]
  char v61; // [rsp+49h] [rbp-30h]
  char v62; // [rsp+4Ah] [rbp-2Fh]
  char v63; // [rsp+4Bh] [rbp-2Eh]
  char v64; // [rsp+4Ch] [rbp-2Dh]
  _BYTE v66[2]; // [rsp+5Dh] [rbp-1Ch] BYREF
  char v67; // [rsp+5Fh] [rbp-1Ah]
  char v68; // [rsp+60h] [rbp-19h]
  char v69; // [rsp+61h] [rbp-18h]
  char v70; // [rsp+62h] [rbp-17h]
  char v71; // [rsp+63h] [rbp-16h]
  char v72; // [rsp+64h] [rbp-15h]
  char v73; // [rsp+65h] [rbp-14h]
  char v74; // [rsp+66h] [rbp-13h]
  char v75; // [rsp+67h] [rbp-12h]
  char v76; // [rsp+68h] [rbp-11h]
  char v77; // [rsp+69h] [rbp-10h]
  char v78; // [rsp+6Ah] [rbp-Fh]

  v3 = *(_WORD *)(a3 + 10);
  v4 = &_ImageBase;
  v5 = *(unsigned __int8 *)(a3 + 17);
  v52 = a3;
  v7 = a2;
  if ( v3 <= 0x7D00u )
  {
    switch ( v3 )
    {
      case 0x7D00u:
        v8 = *((_BYTE *)sbr_start_freq_32 + v5);
        goto LABEL_15;
      case 0x3E80u:
        v8 = *((_BYTE *)sbr_start_freq_16 + v5);
        goto LABEL_15;
      case 0x5622u:
        v8 = *((_BYTE *)sbr_start_freq_22 + v5);
        goto LABEL_15;
      case 0x5DC0u:
        v8 = *((_BYTE *)sbr_start_freq_24 + v5);
        goto LABEL_15;
    }
    goto LABEL_12;
  }
  if ( v3 == 0xAC44 )
  {
    v8 = *((_BYTE *)sbr_start_freq_44 + v5);
  }
  else
  {
    if ( v3 != 0xBB80 )
    {
LABEL_12:
      v8 = -1;
      goto LABEL_15;
    }
    v8 = *((_BYTE *)sbr_start_freq_48 + v5);
  }
LABEL_15:
  v9 = *(unsigned __int8 *)(a3 + 18);
  if ( (unsigned __int8)v9 < 0xEu )
  {
    if ( v3 > 0x7D00u )
    {
      if ( v3 == 0xAC44 )
      {
        v11 = 23;
      }
      else
      {
        if ( v3 != 0xBB80 )
          return 0xFFFFFFFFLL;
        v11 = 21;
      }
      goto LABEL_29;
    }
    switch ( v3 )
    {
      case 0x7D00u:
        goto LABEL_24;
      case 0x3E80u:
        v11 = 48;
        break;
      case 0x5622u:
        v11 = 35;
        break;
      case 0x5DC0u:
LABEL_24:
        v11 = 32;
        break;
      default:
        return 0xFFFFFFFFLL;
    }
LABEL_29:
    LOBYTE(v4) = 64;
    CalcBands((unsigned int)v53, 79, v11, (_DWORD)v4, 13);
    LOBYTE(v12) = 13;
    shellsort(v53, v12);
    a3 = v52;
    v66[1] = v11 + v53[0];
    v67 = v53[1] + v11 + v53[0];
    v68 = v67 + v54;
    v69 = v67 + v54 + v55;
    v70 = v69 + v56;
    v71 = v69 + v56 + v57;
    v72 = v71 + v58;
    v73 = v71 + v58 + v59;
    v74 = v73 + v60;
    v75 = v73 + v60 + v61;
    v76 = v75 + v62;
    v66[0] = v11;
    v78 = v75 + v62 + v63 + v64;
    v77 = v75 + v62 + v63;
    v13 = v66[v9];
    goto LABEL_33;
  }
  if ( (_BYTE)v9 == 14 )
    v13 = 2 * v8;
  else
    v13 = 3 * v8;
LABEL_33:
  v14 = v13;
  if ( v13 > 0x40u )
    v14 = 64;
  v15 = v14;
  v16 = v14 - v8;
  if ( v16 > 48 || v14 <= v8 )
    return 0xFFFFFFFFLL;
  if ( v3 == 0xAC44 )
  {
    v17 = v16 <= 35;
  }
  else
  {
    if ( v3 < 0xBB80u )
      goto LABEL_42;
    v17 = v16 <= 32;
  }
  if ( !v17 )
    return 0xFFFFFFFFLL;
LABEL_42:
  v18 = *(_BYTE *)(a3 + 20);
  if ( v18 )
  {
    if ( v18 == 1 )
    {
      v19 = FLOAT_6_0;
    }
    else if ( v18 == 2 )
    {
      v19 = FLOAT_5_0;
    }
    else
    {
      v19 = FLOAT_4_0;
    }
    v20 = 0.0;
    if ( 1000 * (unsigned int)v14 <= 2245 * (unsigned int)v8 )
    {
      if ( v14 >= 0x41u )
        v38 = 0.0;
      else
        v38 = *(float *)&dword_1800A39A0[v14];
      if ( v8 < 0x41u )
        v20 = *(float *)&dword_1800A39A0[v8];
      v37 = 2 * (int)(float)((float)((float)(v38 - v20) * v19) + 0.5);
      if ( !v37 )
        return 0xFFFFFFFFLL;
      CalcBands((unsigned int)v53, 79, v8, v14, v37);
      shellsort(v53, v37);
      if ( !v53[0] )
        return 0xFFFFFFFFLL;
      v39 = 1;
      *a1 = v8;
      do
      {
        v40 = v39++;
        a1[v40] = a1[v40 - 1] + v53[v40 - 1];
      }
      while ( v39 <= v37 );
    }
    else
    {
      v21 = 2 * v8;
      if ( (unsigned __int8)(2 * v8) >= 0x41u )
      {
        v22 = 0.0;
      }
      else
      {
        _mm_lfence();
        v22 = *(float *)&dword_1800A39A0[v21];
      }
      if ( v8 >= 0x41u )
      {
        v23 = 0.0;
      }
      else
      {
        _mm_lfence();
        v23 = *(float *)&dword_1800A39A0[v8];
      }
      v24 = 2 * (int)(float)((float)((float)(v22 - v23) * v19) + 0.5);
      if ( v14 >= 0x41u )
      {
        v25 = 0.0;
      }
      else
      {
        _mm_lfence();
        v25 = *(float *)&dword_1800A39A0[v14];
      }
      if ( v21 < 0x41u )
      {
        _mm_lfence();
        v20 = *(float *)&dword_1800A39A0[v21];
      }
      v26 = (float)(v25 - v20) * v19;
      if ( *(_BYTE *)(a3 + 21) )
        v26 = v26 * 0.76904297;
      v27 = 2 * (int)(float)(v26 + 0.5);
      if ( !v24 )
        return 0xFFFFFFFFLL;
      if ( !v27 )
        return 0xFFFFFFFFLL;
      CalcBands((unsigned int)v53, 79, v8, v21, v24);
      shellsort(v53, v24);
      if ( !v53[0] )
        return 0xFFFFFFFFLL;
      v28 = 1;
      *a1 = v8;
      v29 = 1;
      do
      {
        v30 = v29++;
        a1[v30] = a1[v30 - 1] + v53[v30 - 1];
      }
      while ( v29 <= v24 );
      CalcBands((unsigned int)v66, 50, v21, v14, v27);
      shellsort(v66, v27);
      v31 = (unsigned __int8)v53[v24 - 1];
      if ( (unsigned __int8)v31 > v66[0] )
      {
        v32 = v31 - v66[0];
        v33 = v31 - v66[0];
        v34 = ((unsigned __int8)v66[v27 - 1] - v66[0]) / 2;
        if ( v32 <= ((unsigned __int8)v66[v27 - 1] - v66[0]) / 2 )
          v34 = v33;
        v66[0] += v34;
        v66[v27 - 1] -= v34;
        shellsort(v66, v27);
      }
      v35 = &a1[v24];
      *v35 = v21;
      do
      {
        v36 = v28++;
        v35[v36] = v35[v36 - 1] + v66[v36 - 1];
      }
      while ( v28 <= v27 );
      v7 = a2;
      v37 = v24 + v27;
    }
    *v7 = v37;
    if ( !v37 )
      return 0xFFFFFFFFLL;
    return 0;
  }
  else
  {
    v41 = 1;
    if ( *(_BYTE *)(a3 + 21) )
    {
      v42 = 2;
      v43 = (v16 >> 1) + 1;
    }
    else
    {
      v42 = 1;
      LOBYTE(v43) = v14 - v8;
    }
    v44 = v43 & 0xFE;
    if ( !v44 )
      return 0xFFFFFFFFLL;
    v45 = 0;
    v46 = v15 - v42 * v44 - v8;
    memset_0(v53, (unsigned __int8)v42, v44);
    do
      ++v45;
    while ( v45 < v44 );
    v47 = 0;
    if ( v46 >= 0 )
      v47 = v45;
    if ( v46 > 0 )
    {
      v48 = -1;
      v47 = v44 - 1;
      goto LABEL_96;
    }
    v48 = (unsigned int)v46 >> 31;
    if ( v46 )
    {
LABEL_96:
      while ( v47 < 0x4Fu )
      {
        v49 = v47;
        v47 += v48;
        v53[v49] -= v48;
        v46 += v48;
        if ( !v46 )
          goto LABEL_98;
      }
      return 0xFFFFFFFFLL;
    }
LABEL_98:
    *a1 = v8;
    do
    {
      v50 = v41++;
      a1[v50] = a1[v50 - 1] + v53[v50 - 1];
    }
    while ( v41 <= v44 );
    *a2 = v44;
    return 0;
  }
}

```

## disassembly

```asm
0x18003dc20  mov     [rsp-8+arg_18], rbx
0x18003dc25  push    rbp
0x18003dc26  push    rsi
0x18003dc27  push    rdi
0x18003dc28  push    r12
0x18003dc2a  push    r13
0x18003dc2c  push    r14
0x18003dc2e  push    r15
0x18003dc30  lea     rbp, [rsp-27h]
0x18003dc35  sub     rsp, 0A0h
0x18003dc3c  mov     rax, cs:__security_cookie
0x18003dc43  xor     rax, rsp
0x18003dc46  mov     [rbp+57h+var_40], rax
0x18003dc4a  movzx   ebx, word ptr [r8+0Ah]
0x18003dc4f  lea     r9, __ImageBase
0x18003dc56  movzx   eax, byte ptr [r8+11h]
0x18003dc5b  mov     rdi, rcx
0x18003dc5e  mov     ecx, 7D00h
0x18003dc63  mov     [rbp+57h+var_A0], rdx
0x18003dc67  mov     [rbp+57h+var_98], r8
0x18003dc6b  mov     r15, rdx
0x18003dc6e  mov     edx, 3E80h
0x18003dc73  mov     esi, 5DC0h
0x18003dc78  mov     r11d, 5622h
0x18003dc7e  mov     r13d, 0AC44h
0x18003dc84  mov     r10d, 0BB80h
0x18003dc8a  cmp     bx, cx
0x18003dc8d  ja      short loc_18003DCCD
0x18003dc8f  jz      short loc_18003DCC2
0x18003dc91  cmp     bx, dx
0x18003dc94  jz      short loc_18003DCB7
0x18003dc96  cmp     bx, r11w
0x18003dc9a  jz      short loc_18003DCAC
0x18003dc9c  cmp     bx, si
0x18003dc9f  jnz     short loc_18003DCD9
0x18003dca1  movzx   r12d, byte ptr [rax+r9+96018h]
0x18003dcaa  jmp     short loc_18003DCF2
0x18003dcac  movzx   r12d, byte ptr [rax+r9+96028h]
0x18003dcb5  jmp     short loc_18003DCF2
0x18003dcb7  movzx   r12d, byte ptr [rax+r9+96008h]
0x18003dcc0  jmp     short loc_18003DCF2
0x18003dcc2  movzx   r12d, byte ptr [rax+r9+96140h]
0x18003dccb  jmp     short loc_18003DCF2
0x18003dccd  cmp     bx, r13w
0x18003dcd1  jz      short loc_18003DCE9
0x18003dcd3  cmp     bx, r10w
0x18003dcd7  jz      short loc_18003DCDE
0x18003dcd9  mov     r12b, 0FFh
0x18003dcdc  jmp     short loc_18003DCF2
0x18003dcde  movzx   r12d, byte ptr [rax+r9+96130h]
0x18003dce7  jmp     short loc_18003DCF2
0x18003dce9  movzx   r12d, byte ptr [rax+r9+96120h]
0x18003dcf2  movzx   r14d, byte ptr [r8+12h]
0x18003dcf7  cmp     r14b, 0Eh
0x18003dcfb  jnb     loc_18003DE1D
0x18003dd01  cmp     bx, cx
0x18003dd04  ja      short loc_18003DD54
0x18003dd06  jz      short loc_18003DD4F
0x18003dd08  cmp     bx, dx
0x18003dd0b  jz      short loc_18003DD4A
0x18003dd0d  cmp     bx, r11w
0x18003dd11  jz      short loc_18003DD45
0x18003dd13  cmp     bx, si
0x18003dd16  jz      short loc_18003DD4F
0x18003dd18  mov     eax, 0FFFFFFFFh
0x18003dd1d  mov     rcx, [rbp+57h+var_40]
0x18003dd21  xor     rcx, rsp; StackCookie
0x18003dd24  call    __security_check_cookie
0x18003dd29  mov     rbx, [rsp+0D0h+arg_18]
0x18003dd31  add     rsp, 0A0h
0x18003dd38  pop     r15
0x18003dd3a  pop     r14
0x18003dd3c  pop     r13
0x18003dd3e  pop     r12
0x18003dd40  pop     rdi
0x18003dd41  pop     rsi
0x18003dd42  pop     rbp
0x18003dd43  retn
0x18003dd45  mov     sil, 23h ; '#'
0x18003dd48  jmp     short loc_18003DD68
0x18003dd4a  mov     sil, 30h ; '0'
0x18003dd4d  jmp     short loc_18003DD68
0x18003dd4f  mov     sil, 20h ; ' '
0x18003dd52  jmp     short loc_18003DD68
0x18003dd54  cmp     bx, r13w
0x18003dd58  jz      short loc_18003DD65
0x18003dd5a  cmp     bx, r10w
0x18003dd5e  jnz     short loc_18003DD18
0x18003dd60  mov     sil, 15h
0x18003dd63  jmp     short loc_18003DD68
0x18003dd65  mov     sil, 17h
0x18003dd68  mov     r9b, 40h ; '@'
0x18003dd6b  mov     [rsp+0D0h+var_B0], 0Dh
0x18003dd70  movzx   r8d, sil
0x18003dd74  lea     rcx, [rbp+57h+var_90]
0x18003dd78  mov     edx, 4Fh ; 'O'
0x18003dd7d  call    CalcBands
0x18003dd82  mov     dl, 0Dh
0x18003dd84  lea     rcx, [rbp+57h+var_90]
0x18003dd88  call    shellsort
0x18003dd8d  movzx   ecx, [rbp+57h+var_90]
0x18003dd91  lea     r9, __ImageBase
0x18003dd98  movzx   eax, [rbp+57h+var_8E]
0x18003dd9c  add     cl, sil
0x18003dd9f  mov     r8, [rbp+57h+var_98]
0x18003dda3  mov     r10d, 0BB80h
0x18003dda9  mov     [rbp+57h+var_72], cl
0x18003ddac  add     cl, [rbp+57h+var_8F]
0x18003ddaf  add     al, cl
0x18003ddb1  mov     [rbp+57h+var_71], cl
0x18003ddb4  movzx   ecx, [rbp+57h+var_8D]
0x18003ddb8  add     cl, al
0x18003ddba  mov     [rbp+57h+var_70], al
0x18003ddbd  movzx   eax, [rbp+57h+var_8C]
0x18003ddc1  add     al, cl
0x18003ddc3  mov     [rbp+57h+var_6F], cl
0x18003ddc6  movzx   ecx, [rbp+57h+var_8B]
0x18003ddca  add     cl, al
0x18003ddcc  mov     [rbp+57h+var_6E], al
0x18003ddcf  movzx   eax, [rbp+57h+var_8A]
0x18003ddd3  add     al, cl
0x18003ddd5  mov     [rbp+57h+var_6D], cl
0x18003ddd8  movzx   ecx, [rbp+57h+var_89]
0x18003dddc  add     cl, al
0x18003ddde  mov     [rbp+57h+var_6C], al
0x18003dde1  movzx   eax, [rbp+57h+var_88]
0x18003dde5  add     al, cl
0x18003dde7  mov     [rbp+57h+var_6B], cl
0x18003ddea  movzx   ecx, [rbp+57h+var_87]
0x18003ddee  add     cl, al
0x18003ddf0  mov     [rbp+57h+var_6A], al
0x18003ddf3  movzx   eax, [rbp+57h+var_86]
0x18003ddf7  add     al, cl
0x18003ddf9  mov     [rbp+57h+var_69], cl
0x18003ddfc  movzx   ecx, [rbp+57h+var_85]
0x18003de00  add     cl, al
0x18003de02  mov     [rbp+57h+var_68], al
0x18003de05  movzx   eax, [rbp+57h+var_84]
0x18003de09  add     al, cl
0x18003de0b  mov     [rbp+57h+var_73], sil
0x18003de0f  mov     [rbp+57h+var_66], al
0x18003de12  mov     [rbp+57h+var_67], cl
0x18003de15  movzx   ecx, [rbp+r14+57h+var_73]
0x18003de1b  jmp     short loc_18003DE31
0x18003de1d  jnz     short loc_18003DE27
0x18003de1f  movzx   ecx, r12b
0x18003de23  add     cl, cl
0x18003de25  jmp     short loc_18003DE31
0x18003de27  movzx   eax, r12b
0x18003de2b  add     al, al
0x18003de2d  lea     ecx, [rax+r12]
0x18003de31  mov     eax, 40h ; '@'
0x18003de36  movzx   r14d, cl
0x18003de3a  cmp     cl, al
0x18003de3c  movzx   edx, r12b
0x18003de40  cmova   r14d, eax
0x18003de44  movzx   esi, r14b
0x18003de48  mov     eax, esi
0x18003de4a  sub     eax, edx
0x18003de4c  cmp     eax, 30h ; '0'
0x18003de4f  jg      loc_18003DD18
0x18003de55  cmp     r14b, r12b
0x18003de58  jbe     loc_18003DD18
0x18003de5e  cmp     bx, r13w
0x18003de62  jnz     short loc_18003DE69
0x18003de64  cmp     eax, 23h ; '#'
0x18003de67  jmp     short loc_18003DE72
0x18003de69  cmp     bx, r10w
0x18003de6d  jb      short loc_18003DE78
0x18003de6f  cmp     eax, 20h ; ' '
0x18003de72  jg      loc_18003DD18
0x18003de78  movzx   ecx, byte ptr [r8+14h]
0x18003de7d  test    cl, cl
0x18003de7f  jz      loc_18003E149
0x18003de85  cmp     cl, 1
0x18003de88  jnz     short loc_18003DE94
0x18003de8a  movss   xmm2, cs:__real@40c00000
0x18003de92  jmp     short loc_18003DEAB
0x18003de94  cmp     cl, 2
0x18003de97  jnz     short loc_18003DEA3
0x18003de99  movss   xmm2, cs:__real@40a00000
0x18003dea1  jmp     short loc_18003DEAB
0x18003dea3  movss   xmm2, cs:__real@40800000
0x18003deab  imul    ecx, edx, 8C5h
0x18003deb1  xorps   xmm1, xmm1
0x18003deb4  imul    eax, esi, 3E8h
0x18003deba  cmp     eax, ecx
0x18003debc  jbe     loc_18003E092
0x18003dec2  movzx   r15d, r12b
0x18003dec6  add     r15b, r15b
0x18003dec9  cmp     r15b, 41h ; 'A'
0x18003decd  jnb     short loc_18003DEE2
0x18003decf  lfence
0x18003ded2  movzx   eax, r15b
0x18003ded6  movss   xmm0, ds:rva dword_1800A39A0[r9+rax*4]
0x18003dee0  jmp     short loc_18003DEE5
0x18003dee2  xorps   xmm0, xmm0
0x18003dee5  cmp     edx, 41h ; 'A'
0x18003dee8  jnb     short loc_18003DEFC
0x18003deea  lfence
0x18003deed  movsxd  rax, edx
0x18003def0  movss   xmm3, ds:rva dword_1800A39A0[r9+rax*4]
0x18003defa  jmp     short loc_18003DEFF
0x18003defc  xorps   xmm3, xmm3
0x18003deff  subss   xmm0, xmm3
0x18003df03  movss   xmm3, cs:__real@3f000000
0x18003df0b  mulss   xmm0, xmm2
0x18003df0f  addss   xmm0, xmm3
0x18003df13  cvttss2si r13d, xmm0
0x18003df18  add     r13b, r13b
0x18003df1b  cmp     esi, 41h ; 'A'
0x18003df1e  jnb     short loc_18003DF32
0x18003df20  lfence
0x18003df23  movsxd  rax, esi
0x18003df26  movss   xmm0, ds:rva dword_1800A39A0[r9+rax*4]
0x18003df30  jmp     short loc_18003DF35
0x18003df32  xorps   xmm0, xmm0
0x18003df35  cmp     r15b, 41h ; 'A'
0x18003df39  jnb     short loc_18003DF4C
0x18003df3b  lfence
0x18003df3e  movzx   eax, r15b
0x18003df42  movss   xmm1, ds:rva dword_1800A39A0[r9+rax*4]
0x18003df4c  cmp     byte ptr [r8+15h], 0
0x18003df51  subss   xmm0, xmm1
0x18003df55  mulss   xmm0, xmm2
0x18003df59  jz      short loc_18003DF63
0x18003df5b  mulss   xmm0, cs:__real@3f44e000
0x18003df63  addss   xmm0, xmm3
0x18003df67  cvttss2si esi, xmm0
0x18003df6b  add     sil, sil
0x18003df6e  cmp     r13b, 1
0x18003df72  jb      loc_18003DD18
0x18003df78  cmp     sil, 1
0x18003df7c  jb      loc_18003DD18
0x18003df82  movzx   r9d, r15b
0x18003df86  mov     [rsp+0D0h+var_B0], r13b
0x18003df8b  movzx   r8d, r12b
0x18003df8f  lea     rcx, [rbp+57h+var_90]
0x18003df93  mov     edx, 4Fh ; 'O'
0x18003df98  call    CalcBands
0x18003df9d  movzx   edx, r13b
0x18003dfa1  lea     rcx, [rbp+57h+var_90]
0x18003dfa5  call    shellsort
0x18003dfaa  cmp     [rbp+57h+var_90], 0
0x18003dfae  jz      loc_18003DD18
0x18003dfb4  mov     ebx, 1
0x18003dfb9  mov     [rdi], r12b
0x18003dfbc  movzx   r12d, r13b
0x18003dfc0  mov     edx, ebx
0x18003dfc2  cmp     r12d, ebx
0x18003dfc5  jb      short loc_18003DFE6
0x18003dfc7  nop     word ptr [rax+rax+00000000h]
0x18003dfd0  movsxd  rcx, edx
0x18003dfd3  inc     edx
0x18003dfd5  movzx   eax, byte ptr [rbp+rcx+57h+var_98+7]
0x18003dfda  add     al, [rcx+rdi-1]
0x18003dfde  mov     [rcx+rdi], al
0x18003dfe1  cmp     edx, r12d
0x18003dfe4  jle     short loc_18003DFD0
0x18003dfe6  movzx   r9d, r14b
0x18003dfea  mov     [rsp+0D0h+var_B0], sil
0x18003dfef  movzx   r8d, r15b
0x18003dff3  lea     rcx, [rbp+57h+var_73]
0x18003dff7  mov     edx, 32h ; '2'
0x18003dffc  call    CalcBands
0x18003e001  movzx   edx, sil
0x18003e005  lea     rcx, [rbp+57h+var_73]
0x18003e009  call    shellsort
0x18003e00e  movzx   edx, byte ptr [rbp+r12+57h+var_98+7]
0x18003e014  movzx   r10d, [rbp+57h+var_73]
0x18003e019  cmp     dl, r10b
0x18003e01c  jbe     short loc_18003E05C
0x18003e01e  mov     r8d, edx
0x18003e021  movzx   r9d, sil
0x18003e025  sub     r8d, r10d
0x18003e028  movzx   ecx, r8b
0x18003e02c  movzx   eax, [rbp+r9+57h+var_74]
0x18003e032  sub     eax, r10d
0x18003e035  cdq
0x18003e036  sub     eax, edx
0x18003e038  sar     eax, 1
0x18003e03a  cmp     r8d, eax
0x18003e03d  movzx   edx, al
0x18003e040  cmovle  edx, ecx
0x18003e043  lea     rcx, [rbp+57h+var_73]
0x18003e047  add     r10b, dl
0x18003e04a  mov     [rbp+57h+var_73], r10b
0x18003e04e  sub     [rbp+r9+57h+var_74], dl
0x18003e053  movzx   edx, sil
0x18003e057  call    shellsort
0x18003e05c  movzx   edx, r13b
0x18003e060  add     rdx, rdi
0x18003e063  movzx   r8d, sil
0x18003e067  mov     [rdx], r15b
0x18003e06a  cmp     r8d, ebx
0x18003e06d  jb      short loc_18003E086
0x18003e06f  nop
0x18003e070  movsxd  rcx, ebx
0x18003e073  inc     ebx
0x18003e075  movzx   eax, [rbp+rcx+57h+var_74]
  ... truncated ...
```
