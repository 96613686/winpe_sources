# ASN1string2generalizedtime

- ea: `0x180005ae0`
- end: `0x180005f45`
- name: `ASN1string2generalizedtime`
- size: `1125`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800051a0`

## callees

- `0x180005ae0`
- `0x180008b44`

## pseudocode

```c
__int64 __fastcall ASN1string2generalizedtime(__int64 a1, char *a2, unsigned int a3)
{
  unsigned int v3; // r10d
  char *v4; // r11
  int v6; // edx
  __int16 v7; // r13
  __int16 v8; // ax
  int v9; // r9d
  char v10; // si
  __int64 result; // rax
  char v12; // r14
  char v13; // dl
  __int16 v14; // r8
  int v15; // ecx
  char v16; // r12
  int v17; // r15d
  int v18; // edi
  char v19; // al
  int v20; // edx
  char v21; // al
  int v22; // r8d
  char v23; // dl
  char v24; // cl
  int v25; // edx
  char v26; // al
  int v27; // r8d
  unsigned int v28; // edx
  char v29; // al
  char v30; // al
  double v31; // xmm1_8
  double v32; // xmm2_8
  int v33; // ecx
  __int64 v34; // rdx
  double v35; // xmm0_8
  double v36; // xmm0_8
  double v37; // xmm0_8
  double v38; // xmm0_8
  int v39; // r8d
  double v40; // xmm0_8
  char v41; // [rsp+24h] [rbp-Ch]
  char *v42; // [rsp+28h] [rbp-8h] BYREF
  unsigned int v43; // [rsp+70h] [rbp+40h] BYREF
  int v44; // [rsp+88h] [rbp+58h]

  v3 = a3;
  v4 = a2;
  if ( !a1 || !a2 || a3 < 0xA )
    return 0;
  v6 = 4;
  v7 = 0;
  do
  {
    v8 = *v4;
    if ( !*v4 )
      break;
    --v3;
    ++v4;
    v7 = v8 + 2 * (5 * v7 - 24);
    --v6;
  }
  while ( v6 );
  v9 = 2;
  if ( v3 < 2 )
  {
    v41 = 0;
    v10 = 0;
LABEL_11:
    v12 = 0;
    goto LABEL_12;
  }
  v24 = 0;
  v25 = 2;
  do
  {
    v26 = *v4;
    if ( !*v4 )
      break;
    --v3;
    ++v4;
    v24 = v26 + 2 * (5 * v24 - 24);
    --v25;
  }
  while ( v25 );
  v10 = 0;
  v41 = v24;
  if ( v3 < 2 )
    goto LABEL_11;
  v20 = 2;
  do
  {
    v21 = *v4;
    if ( !*v4 )
      break;
    --v3;
    ++v4;
    v10 = v21 + 2 * (5 * v10 - 24);
    --v20;
  }
  while ( v20 );
  v12 = 0;
  if ( v3 >= 2 )
  {
    v22 = 2;
    do
    {
      v23 = *v4;
      if ( !*v4 )
        goto LABEL_61;
      --v3;
      ++v4;
      v12 = v23 + 2 * (5 * v12 - 24);
    }
    while ( --v22 );
  }
LABEL_12:
  v13 = *v4;
  if ( !*v4 )
  {
LABEL_61:
    if ( v3 )
      return 0;
    v14 = 0;
    v16 = 0;
    LOBYTE(v17) = 0;
    LOBYTE(v18) = 0;
    LOWORD(v15) = 0;
    goto LABEL_20;
  }
  if ( !v3 )
    return 0;
  v14 = 0;
  LOWORD(v15) = 0;
  v16 = 0;
  LOBYTE(v17) = 0;
  v44 = 0;
  LOBYTE(v18) = 0;
  if ( ((v13 - 44) & 0xFD) == 0 )
  {
    v42 = v4 + 1;
    v43 = v3 - 1;
    v36 = scanfrac(v4 + 1, v3 - 1, &v42, &v43) * 60.0;
    v4 = v42;
    v3 = v43;
    v17 = (int)v36;
    v37 = (v36 - (double)(int)v36) * 60.0;
    v18 = (int)v37;
    v15 = (int)((v37 - (double)(int)v37) * 1000.0);
    v44 = v15;
    goto LABEL_37;
  }
  if ( (unsigned __int8)(v13 - 48) > 9u )
    goto LABEL_16;
  v27 = 2;
  v28 = v3;
  if ( v3 >= 2 )
  {
    do
    {
      v29 = *v4;
      v16 = 0;
      LOBYTE(v18) = 0;
      v44 = 0;
      if ( !v29 )
        break;
      --v28;
      ++v4;
      LOBYTE(v17) = v29 + 2 * (v17 + 4 * (v17 - 6));
      v16 = 0;
      v44 = 0;
      LOBYTE(v18) = 0;
      --v27;
    }
    while ( v27 );
  }
  v3 = v28;
  if ( ((*v4 - 44) & 0xFD) == 0 )
  {
    v34 = v28 - 1;
    v42 = v4 + 1;
    v43 = v34;
    v35 = scanfrac(v4 + 1, v34, &v42, &v43) * 60.0;
    v4 = v42;
    v3 = v43;
    v18 = (int)v35;
    v15 = (int)((v35 - (double)(int)v35) * 1000.0);
    v44 = v15;
    goto LABEL_37;
  }
  if ( (unsigned __int8)(*v4 - 48) > 9u )
    goto LABEL_36;
  LOBYTE(v18) = 0;
  if ( v28 < 2 )
    goto LABEL_36;
  while ( 1 )
  {
    v30 = *v4;
    if ( !*v4 )
      break;
    --v3;
    ++v4;
    LOBYTE(v18) = v30 + 2 * (5 * v18 - 24);
    if ( !--v9 )
    {
      v30 = *v4;
      break;
    }
  }
  if ( ((v30 - 44) & 0xFD) != 0 )
  {
LABEL_36:
    LOWORD(v15) = v44;
LABEL_37:
    v14 = 0;
    goto LABEL_16;
  }
  ++v4;
  v31 = 0.0;
  if ( --v3 )
  {
    v32 = DOUBLE_1_0;
    do
    {
      v33 = *v4;
      if ( (unsigned __int8)(*v4 - 48) > 9u )
        break;
      v32 = v32 / 10.0;
      ++v4;
      v31 = v31 + (double)(v33 - 48) * v32;
      --v3;
    }
    while ( v3 );
  }
  v14 = 0;
  v15 = (int)(v31 * 1000.0);
  v44 = v15;
LABEL_16:
  if ( v3 )
  {
    v19 = *v4;
    if ( *v4 == 90 )
    {
      ++v4;
      v16 = 1;
      --v3;
LABEL_19:
      if ( !v3 || !*v4 )
        goto LABEL_20;
      return 0;
    }
    if ( v19 == 43 )
    {
      v42 = v4 + 1;
      v43 = v3 - 1;
      v38 = scanfrac(v4 + 1, v3 - 1, &v42, &v43);
      v39 = (int)(v38 * 10000.0) % 100;
      v15 = 60 * (int)(v38 * -100.0);
    }
    else
    {
      if ( v19 != 45 )
        goto LABEL_19;
      v42 = v4 + 1;
      v43 = v3 - 1;
      v40 = scanfrac(v4 + 1, v3 - 1, &v42, &v43);
      v15 = (int)(v40 * 10000.0) % 100;
      v39 = -60 * (int)(v40 * 100.0);
    }
    v3 = v43;
    v14 = v39 - v15;
    LOWORD(v15) = v44;
    v4 = v42;
    goto LABEL_19;
  }
LABEL_20:
  *(_BYTE *)(a1 + 2) = v41;
  result = 1;
  *(_WORD *)a1 = v7;
  *(_BYTE *)(a1 + 3) = v10;
  *(_BYTE *)(a1 + 4) = v12;
  *(_BYTE *)(a1 + 5) = v17;
  *(_BYTE *)(a1 + 6) = v18;
  *(_WORD *)(a1 + 8) = v15;
  *(_BYTE *)(a1 + 10) = v16;
  *(_WORD *)(a1 + 12) = v14;
  return result;
}

```

## disassembly

```asm
0x180005ae0  mov     [rsp-38h+arg_8], rbx
0x180005ae5  push    rbp
0x180005ae6  push    rsi
0x180005ae7  push    rdi
0x180005ae8  push    r12
0x180005aea  push    r13
0x180005aec  push    r14
0x180005aee  push    r15
0x180005af0  mov     rbp, rsp
0x180005af3  sub     rsp, 30h
0x180005af7  mov     r10d, r8d
0x180005afa  mov     r11, rdx
0x180005afd  mov     rbx, rcx
0x180005b00  test    rcx, rcx
0x180005b03  jz      short loc_180005B52
0x180005b05  test    rdx, rdx
0x180005b08  jz      short loc_180005B52
0x180005b0a  cmp     r8d, 0Ah
0x180005b0e  jb      short loc_180005B52
0x180005b10  mov     edx, 4
0x180005b15  xor     r13d, r13d
0x180005b18  movsx   eax, byte ptr [r11]
0x180005b1c  test    al, al
0x180005b1e  jz      short loc_180005B38
0x180005b20  lea     r13d, [r13+r13*4+0]
0x180005b25  dec     r10d
0x180005b28  inc     r11
0x180005b2b  lea     r13d, [r13-18h]
0x180005b2f  lea     r13d, [rax+r13*2]
0x180005b33  add     edx, 0FFFFFFFFh
0x180005b36  jnz     short loc_180005B18
0x180005b38  mov     r9d, 2
0x180005b3e  cmp     r10d, r9d
0x180005b41  jnb     loc_180005C69
0x180005b47  mov     [rbp+var_C], 0
0x180005b4e  xor     esi, esi
0x180005b50  jmp     short loc_180005B67
0x180005b52  xor     eax, eax
0x180005b54  jmp     loc_180005BFD
0x180005b59  xor     esi, esi
0x180005b5b  mov     [rbp+var_C], ecx
0x180005b5e  cmp     r10d, r9d
0x180005b61  jnb     loc_180005C12
0x180005b67  xor     r14d, r14d
0x180005b6a  movzx   edx, byte ptr [r11]
0x180005b6e  test    dl, dl
0x180005b70  jz      loc_180005F2A
0x180005b76  test    r10d, r10d
0x180005b79  jz      short loc_180005B52
0x180005b7b  xor     r8d, r8d
0x180005b7e  xor     ecx, ecx
0x180005b80  xor     r12d, r12d
0x180005b83  mov     [rbp+var_10], r8d
0x180005b87  xor     r15d, r15d
0x180005b8a  mov     [rbp+arg_18], ecx
0x180005b8d  xor     edi, edi
0x180005b8f  test    r10d, r10d
0x180005b92  jz      short loc_180005BD1
0x180005b94  lea     eax, [rdx-2Ch]
0x180005b97  test    al, 0FDh
0x180005b99  jz      loc_180005DE2
0x180005b9f  sub     dl, 30h ; '0'
0x180005ba2  cmp     dl, 9
0x180005ba5  jbe     loc_180005C96
0x180005bab  test    r10d, r10d
0x180005bae  jz      short loc_180005BD1
0x180005bb0  movzx   eax, byte ptr [r11]
0x180005bb4  cmp     al, 5Ah ; 'Z'
0x180005bb6  jnz     loc_180005E4C
0x180005bbc  inc     r11
0x180005bbf  mov     r12d, 1
0x180005bc5  dec     r10d
0x180005bc8  test    r10d, r10d
0x180005bcb  jnz     loc_180005F1B
0x180005bd1  mov     eax, [rbp+var_C]
0x180005bd4  mov     [rbx+2], al
0x180005bd7  mov     eax, 1
0x180005bdc  mov     [rbx], r13w
0x180005be0  mov     [rbx+3], sil
0x180005be4  mov     [rbx+4], r14b
0x180005be8  mov     [rbx+5], r15b
0x180005bec  mov     [rbx+6], dil
0x180005bf0  mov     [rbx+8], cx
0x180005bf4  mov     [rbx+0Ah], r12b
0x180005bf8  mov     [rbx+0Ch], r8w
0x180005bfd  mov     rbx, [rsp+30h+arg_8]
0x180005c02  add     rsp, 30h
0x180005c06  pop     r15
0x180005c08  pop     r14
0x180005c0a  pop     r13
0x180005c0c  pop     r12
0x180005c0e  pop     rdi
0x180005c0f  pop     rsi
0x180005c10  pop     rbp
0x180005c11  retn
0x180005c12  mov     edx, r9d
0x180005c15  movsx   eax, byte ptr [r11]
0x180005c19  test    al, al
0x180005c1b  jz      short loc_180005C31
0x180005c1d  lea     esi, [rsi+rsi*4]
0x180005c20  dec     r10d
0x180005c23  inc     r11
0x180005c26  lea     esi, [rsi-18h]
0x180005c29  lea     esi, [rax+rsi*2]
0x180005c2c  add     edx, 0FFFFFFFFh
0x180005c2f  jnz     short loc_180005C15
0x180005c31  xor     r14d, r14d
0x180005c34  cmp     r10d, r9d
0x180005c37  jb      loc_180005B6A
0x180005c3d  mov     r8d, r9d
0x180005c40  movsx   edx, byte ptr [r11]
0x180005c44  test    dl, dl
0x180005c46  jz      loc_180005F2A
0x180005c4c  lea     r14d, [r14+r14*4]
0x180005c50  dec     r10d
0x180005c53  inc     r11
0x180005c56  lea     r14d, [r14-18h]
0x180005c5a  lea     r14d, [rdx+r14*2]
0x180005c5e  add     r8d, 0FFFFFFFFh
0x180005c62  jnz     short loc_180005C40
0x180005c64  jmp     loc_180005B6A
0x180005c69  xor     ecx, ecx
0x180005c6b  mov     edx, r9d
0x180005c6e  mov     [rbp+var_C], ecx
0x180005c71  movsx   eax, byte ptr [r11]
0x180005c75  test    al, al
0x180005c77  jz      loc_180005B59
0x180005c7d  lea     ecx, [rcx+rcx*4]
0x180005c80  dec     r10d
0x180005c83  inc     r11
0x180005c86  lea     ecx, [rcx-18h]
0x180005c89  lea     ecx, [rax+rcx*2]
0x180005c8c  add     edx, 0FFFFFFFFh
0x180005c8f  jnz     short loc_180005C71
0x180005c91  jmp     loc_180005B59
0x180005c96  mov     r8d, r9d
0x180005c99  mov     edx, r10d
0x180005c9c  cmp     r10d, r9d
0x180005c9f  jnb     short loc_180005CD0
0x180005ca1  movzx   ecx, byte ptr [r11]
0x180005ca5  mov     r10d, edx
0x180005ca8  lea     eax, [rcx-2Ch]
0x180005cab  test    al, 0FDh
0x180005cad  jz      loc_180005D94
0x180005cb3  sub     cl, 30h ; '0'
0x180005cb6  cmp     cl, 9
0x180005cb9  jbe     short loc_180005D09
0x180005cbb  mov     ecx, [rbp+arg_18]
0x180005cbe  mov     r8d, [rbp+var_10]
0x180005cc2  jmp     loc_180005BAB
0x180005cd0  movsx   eax, byte ptr [r11]
0x180005cd4  mov     r12d, ecx
0x180005cd7  mov     [rbp+var_10], ecx
0x180005cda  mov     edi, ecx
0x180005cdc  mov     [rbp+arg_18], ecx
0x180005cdf  test    al, al
0x180005ce1  jz      short loc_180005CA1
0x180005ce3  lea     ecx, [r15-6]
0x180005ce7  dec     edx
0x180005ce9  lea     ecx, [r15+rcx*4]
0x180005ced  inc     r11
0x180005cf0  lea     r15d, [rax+rcx*2]
0x180005cf4  xor     ecx, ecx
0x180005cf6  mov     [rbp+var_10], ecx
0x180005cf9  mov     r12d, ecx
0x180005cfc  mov     [rbp+arg_18], ecx
0x180005cff  mov     edi, ecx
0x180005d01  add     r8d, 0FFFFFFFFh
0x180005d05  jnz     short loc_180005CD0
0x180005d07  jmp     short loc_180005CA1
0x180005d09  xor     edi, edi
0x180005d0b  cmp     edx, r9d
0x180005d0e  jb      short loc_180005CBB
0x180005d10  movsx   eax, byte ptr [r11]
0x180005d14  test    al, al
0x180005d16  jz      short loc_180005D31
0x180005d18  lea     edi, [rdi+rdi*4]
0x180005d1b  dec     r10d
0x180005d1e  inc     r11
0x180005d21  lea     edi, [rdi-18h]
0x180005d24  lea     edi, [rax+rdi*2]
0x180005d27  add     r9d, 0FFFFFFFFh
0x180005d2b  jnz     short loc_180005D10
0x180005d2d  movzx   eax, byte ptr [r11]
0x180005d31  sub     al, 2Ch ; ','
0x180005d33  test    al, 0FDh
0x180005d35  jnz     short loc_180005CBB
0x180005d37  inc     r11
0x180005d3a  xorps   xmm1, xmm1
0x180005d3d  sub     r10d, 1
0x180005d41  jz      short loc_180005D56
0x180005d43  movsd   xmm2, cs:__real@3ff0000000000000
0x180005d4b  movsx   ecx, byte ptr [r11]
0x180005d4f  lea     eax, [rcx-30h]
0x180005d52  cmp     al, 9
0x180005d54  jbe     short loc_180005D6E
0x180005d56  mulsd   xmm1, cs:__real@408f400000000000
0x180005d5e  mov     r8d, [rbp+var_10]
0x180005d62  cvttsd2si ecx, xmm1
0x180005d66  mov     [rbp+arg_18], ecx
0x180005d69  jmp     loc_180005BAB
0x180005d6e  divsd   xmm2, cs:__real@4024000000000000
0x180005d76  lea     eax, [rcx-30h]
0x180005d79  inc     r11
0x180005d7c  movd    xmm0, eax
0x180005d80  cvtdq2pd xmm0, xmm0
0x180005d84  mulsd   xmm0, xmm2
0x180005d88  addsd   xmm1, xmm0
0x180005d8c  add     r10d, 0FFFFFFFFh
0x180005d90  jnz     short loc_180005D4B
0x180005d92  jmp     short loc_180005D56
0x180005d94  lea     rcx, [r11+1]
0x180005d98  dec     edx
0x180005d9a  lea     r9, [rbp+arg_0]
0x180005d9e  mov     [rbp+var_8], rcx
0x180005da2  lea     r8, [rbp+var_8]
0x180005da6  mov     [rbp+arg_0], edx
0x180005da9  call    scanfrac
0x180005dae  mulsd   xmm0, cs:__real@404e000000000000
0x180005db6  mov     r11, [rbp+var_8]
0x180005dba  mov     r10d, [rbp+arg_0]
0x180005dbe  cvttsd2si edi, xmm0
0x180005dc2  movd    xmm1, edi
0x180005dc6  cvtdq2pd xmm1, xmm1
0x180005dca  subsd   xmm0, xmm1
0x180005dce  mulsd   xmm0, cs:__real@408f400000000000
0x180005dd6  cvttsd2si ecx, xmm0
0x180005dda  mov     [rbp+arg_18], ecx
0x180005ddd  jmp     loc_180005CBE
0x180005de2  lea     rcx, [r11+1]
0x180005de6  lea     edx, [r10-1]
0x180005dea  mov     [rbp+var_8], rcx
0x180005dee  lea     r9, [rbp+arg_0]
0x180005df2  mov     [rbp+arg_0], edx
0x180005df5  lea     r8, [rbp+var_8]
0x180005df9  call    scanfrac
0x180005dfe  mulsd   xmm0, cs:__real@404e000000000000
0x180005e06  mov     r11, [rbp+var_8]
0x180005e0a  mov     r10d, [rbp+arg_0]
0x180005e0e  cvttsd2si r15d, xmm0
0x180005e13  movd    xmm1, r15d
0x180005e18  cvtdq2pd xmm1, xmm1
0x180005e1c  subsd   xmm0, xmm1
0x180005e20  mulsd   xmm0, cs:__real@404e000000000000
0x180005e28  cvttsd2si edi, xmm0
0x180005e2c  movd    xmm1, edi
0x180005e30  cvtdq2pd xmm1, xmm1
0x180005e34  subsd   xmm0, xmm1
0x180005e38  mulsd   xmm0, cs:__real@408f400000000000
0x180005e40  cvttsd2si ecx, xmm0
0x180005e44  mov     [rbp+arg_18], ecx
0x180005e47  jmp     loc_180005CBE
0x180005e4c  cmp     al, 2Bh ; '+'
0x180005e4e  jnz     short loc_180005EAA
0x180005e50  inc     r11
0x180005e53  lea     r9, [rbp+arg_0]
0x180005e57  dec     r10d
0x180005e5a  mov     [rbp+var_8], r11
0x180005e5e  mov     edx, r10d
0x180005e61  mov     [rbp+arg_0], r10d
0x180005e65  mov     rcx, r11
0x180005e68  lea     r8, [rbp+var_8]
0x180005e6c  call    scanfrac
0x180005e71  movaps  xmm3, xmm0
0x180005e74  mov     eax, 51EB851Fh
0x180005e79  mulsd   xmm3, cs:__real@40c3880000000000
0x180005e81  mulsd   xmm0, cs:__real@c059000000000000
0x180005e89  cvttsd2si r8d, xmm3
0x180005e8e  imul    r8d
0x180005e91  sar     edx, 5
0x180005e94  mov     eax, edx
0x180005e96  shr     eax, 1Fh
0x180005e99  add     edx, eax
0x180005e9b  imul    eax, edx, 64h ; 'd'
0x180005e9e  sub     r8d, eax
0x180005ea1  cvttsd2si eax, xmm0
0x180005ea5  imul    ecx, eax, 3Ch ; '<'
0x180005ea8  jmp     short loc_180005F08
0x180005eaa  cmp     al, 2Dh ; '-'
0x180005eac  jnz     loc_180005BC8
0x180005eb2  inc     r11
0x180005eb5  lea     r9, [rbp+arg_0]
0x180005eb9  dec     r10d
0x180005ebc  mov     [rbp+var_8], r11
0x180005ec0  mov     edx, r10d
0x180005ec3  mov     [rbp+arg_0], r10d
0x180005ec7  mov     rcx, r11
0x180005eca  lea     r8, [rbp+var_8]
0x180005ece  call    scanfrac
0x180005ed3  movaps  xmm3, xmm0
0x180005ed6  mov     eax, 51EB851Fh
0x180005edb  mulsd   xmm3, cs:__real@40c3880000000000
0x180005ee3  mulsd   xmm0, cs:__real@4059000000000000
0x180005eeb  cvttsd2si ecx, xmm3
0x180005eef  imul    ecx
0x180005ef1  sar     edx, 5
0x180005ef4  mov     eax, edx
0x180005ef6  shr     eax, 1Fh
0x180005ef9  add     edx, eax
0x180005efb  imul    eax, edx, 64h ; 'd'
  ... truncated ...
```
