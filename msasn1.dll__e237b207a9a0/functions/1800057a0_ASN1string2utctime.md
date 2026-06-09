# ASN1string2utctime

- ea: `0x1800057a0`
- end: `0x180005ad8`
- name: `ASN1string2utctime`
- size: `824`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005250`

## callees

- `0x1800057a0`
- `0x180008b44`

## pseudocode

```c
_BOOL8 __fastcall ASN1string2utctime(__int64 a1, char *a2, unsigned int a3)
{
  char *v3; // r10
  int v4; // r11d
  char v5; // al
  int v6; // r9d
  char v7; // bl
  char v8; // al
  char v9; // al
  char v10; // al
  unsigned int v11; // r9d
  _WORD *v12; // r11
  char v13; // al
  char v14; // al
  int v16; // ebx
  char v17; // r9
  int v18; // ebx
  char v19; // r9
  char v20; // al
  int v21; // ebx
  char v22; // r9
  int v23; // ebx
  char v24; // r9
  char v25; // r8
  double v26; // xmm2_8
  double v27; // xmm1_8
  int v28; // ecx
  double v29; // xmm0_8
  _WORD *v30; // r11
  unsigned int v31; // [rsp+30h] [rbp+8h] BYREF
  char *v32; // [rsp+48h] [rbp+20h] BYREF

  v3 = a2;
  if ( !a1 || !a2 || a3 < 0xA )
    return 0;
  v4 = 2;
  v5 = 0;
  v6 = 2;
  do
  {
    v7 = *v3;
    if ( !*v3 )
      break;
    --a3;
    ++v3;
    v5 = v7 + 2 * (5 * v5 - 24);
    --v6;
  }
  while ( v6 );
  *(_BYTE *)a1 = v5;
  v8 = 0;
  if ( a3 < 2 )
  {
    *(_BYTE *)(a1 + 1) = 0;
LABEL_10:
    *(_BYTE *)(a1 + 2) = 0;
LABEL_11:
    *(_BYTE *)(a1 + 3) = 0;
    v10 = 0;
    goto LABEL_12;
  }
  v16 = 2;
  do
  {
    v17 = *v3;
    if ( !*v3 )
      break;
    --a3;
    ++v3;
    v8 = v17 + 2 * (5 * v8 - 24);
    --v16;
  }
  while ( v16 );
  *(_BYTE *)(a1 + 1) = v8;
  v9 = 0;
  if ( a3 < 2 )
    goto LABEL_10;
  v18 = 2;
  do
  {
    v19 = *v3;
    if ( !*v3 )
      break;
    --a3;
    ++v3;
    v9 = v19 + 2 * (5 * v9 - 24);
    --v18;
  }
  while ( v18 );
  *(_BYTE *)(a1 + 2) = v9;
  v20 = 0;
  if ( a3 < 2 )
    goto LABEL_11;
  v21 = 2;
  do
  {
    v22 = *v3;
    if ( !*v3 )
      break;
    --a3;
    ++v3;
    v20 = v22 + 2 * (5 * v20 - 24);
    --v21;
  }
  while ( v21 );
  *(_BYTE *)(a1 + 3) = v20;
  v10 = 0;
  if ( a3 >= 2 )
  {
    v23 = 2;
    do
    {
      v24 = *v3;
      if ( !*v3 )
        break;
      --a3;
      ++v3;
      v10 = v24 + 2 * (5 * v10 - 24);
      --v23;
    }
    while ( v23 );
  }
LABEL_12:
  *(_BYTE *)(a1 + 4) = v10;
  if ( !*v3 )
  {
    if ( a3 )
      return 0;
    *(_BYTE *)(a1 + 5) = 0;
    *(_WORD *)(a1 + 8) = 0;
    *(_BYTE *)(a1 + 6) = 0;
    return !a3 || !*v3;
  }
  if ( !a3 )
    return 0;
  *(_BYTE *)(a1 + 5) = 0;
  v11 = a3;
  if ( (unsigned __int8)(*v3 - 48) > 9u )
  {
    v12 = (_WORD *)(a1 + 8);
    *(_BYTE *)(a1 + 6) = 0;
    *(_WORD *)(a1 + 8) = 0;
LABEL_16:
    v13 = *v3;
    if ( *v3 == 90 )
    {
      *(_BYTE *)(a1 + 6) = 1;
      a3 = v11 - 1;
      ++v3;
    }
    else if ( v13 == 43 )
    {
      v32 = v3 + 1;
      v31 = v11 - 1;
      v29 = scanfrac(v3 + 1, v11 - 1, &v32, &v31);
      v3 = v32;
      a3 = v31;
      *v30 = (int)((double)((int)(v29 * 10000.0) % 100) + v29 * 100.0 * 60.0);
    }
    else if ( v13 == 45 )
    {
      ++v3;
      a3 = v11 - 1;
      v26 = 0.0;
      if ( v11 != 1 )
      {
        v27 = DOUBLE_1_0;
        do
        {
          v28 = *v3;
          if ( (unsigned __int8)(*v3 - 48) > 9u )
            break;
          v27 = v27 / 10.0;
          ++v3;
          v26 = v26 + (double)(v28 - 48) * v27;
          --a3;
        }
        while ( a3 );
      }
      *v12 = -(__int16)(int)((double)((int)(v26 * 10000.0) % 100) + v26 * 100.0 * 60.0);
    }
    return !a3 || !*v3;
  }
  v14 = 0;
  if ( a3 >= 2 )
  {
    do
    {
      v25 = *v3;
      if ( !*v3 )
        break;
      --v11;
      ++v3;
      v14 = v25 + 2 * (5 * v14 - 24);
      --v4;
    }
    while ( v4 );
  }
  *(_BYTE *)(a1 + 5) = v14;
  v12 = (_WORD *)(a1 + 8);
  *(_BYTE *)(a1 + 6) = 0;
  *(_WORD *)(a1 + 8) = 0;
  a3 = v11;
  if ( v11 )
    goto LABEL_16;
  return !a3 || !*v3;
}

```

## disassembly

```asm
0x1800057a0  push    rbx
0x1800057a2  sub     rsp, 20h
0x1800057a6  mov     r10, rdx
0x1800057a9  test    rcx, rcx
0x1800057ac  jz      loc_18000589C
0x1800057b2  test    rdx, rdx
0x1800057b5  jz      loc_18000589C
0x1800057bb  cmp     r8d, 0Ah
0x1800057bf  jb      loc_18000589C
0x1800057c5  mov     r11d, 2
0x1800057cb  xor     eax, eax
0x1800057cd  mov     r9d, r11d
0x1800057d0  movsx   ebx, byte ptr [r10]
0x1800057d4  test    bl, bl
0x1800057d6  jz      short loc_1800057ED
0x1800057d8  lea     eax, [rax+rax*4]
0x1800057db  dec     r8d
0x1800057de  inc     r10
0x1800057e1  lea     eax, [rax-18h]
0x1800057e4  lea     eax, [rbx+rax*2]
0x1800057e7  add     r9d, 0FFFFFFFFh
0x1800057eb  jnz     short loc_1800057D0
0x1800057ed  mov     [rcx], al
0x1800057ef  xor     eax, eax
0x1800057f1  cmp     r8d, r11d
0x1800057f4  jnb     loc_1800058A0
0x1800057fa  mov     [rcx+1], al
0x1800057fd  jmp     short loc_18000580D
0x1800057ff  mov     [rcx+1], al
0x180005802  xor     eax, eax
0x180005804  cmp     r8d, r11d
0x180005807  jnb     loc_1800058CA
0x18000580d  mov     [rcx+2], al
0x180005810  xor     eax, eax
0x180005812  mov     [rcx+3], al
0x180005815  xor     eax, eax
0x180005817  mov     [rcx+4], al
0x18000581a  cmp     byte ptr [r10], 0
0x18000581e  jz      loc_180005AAD
0x180005824  test    r8d, r8d
0x180005827  jz      short loc_18000589C
0x180005829  mov     byte ptr [rcx+5], 0
0x18000582d  mov     r9d, r8d
0x180005830  movzx   eax, byte ptr [r10]
0x180005834  sub     al, 30h ; '0'
0x180005836  cmp     al, 9
0x180005838  jbe     short loc_180005864
0x18000583a  lea     r11, [rcx+8]
0x18000583e  mov     byte ptr [rcx+6], 0
0x180005842  xor     eax, eax
0x180005844  mov     [r11], ax
0x180005848  movzx   eax, byte ptr [r10]
0x18000584c  mov     rbx, r11
0x18000584f  cmp     al, 5Ah ; 'Z'
0x180005851  jnz     loc_180005988
0x180005857  mov     byte ptr [rcx+6], 1
0x18000585b  lea     r8d, [r9-1]
0x18000585f  inc     r10
0x180005862  jmp     short loc_180005888
0x180005864  xor     eax, eax
0x180005866  cmp     r8d, r11d
0x180005869  jnb     loc_180005960
0x18000586f  mov     [rcx+5], al
0x180005872  lea     r11, [rcx+8]
0x180005876  xor     eax, eax
0x180005878  mov     byte ptr [rcx+6], 0
0x18000587c  mov     [r11], ax
0x180005880  mov     r8d, r9d
0x180005883  test    r9d, r9d
0x180005886  jnz     short loc_180005848
0x180005888  test    r8d, r8d
0x18000588b  jnz     loc_180005AC9
0x180005891  mov     eax, 1
0x180005896  add     rsp, 20h
0x18000589a  pop     rbx
0x18000589b  retn
0x18000589c  xor     eax, eax
0x18000589e  jmp     short loc_180005896
0x1800058a0  mov     ebx, r11d
0x1800058a3  movsx   r9d, byte ptr [r10]
0x1800058a7  test    r9b, r9b
0x1800058aa  jz      loc_1800057FF
0x1800058b0  lea     eax, [rax+rax*4]
0x1800058b3  dec     r8d
0x1800058b6  inc     r10
0x1800058b9  lea     eax, [rax-18h]
0x1800058bc  lea     eax, [r9+rax*2]
0x1800058c0  add     ebx, 0FFFFFFFFh
0x1800058c3  jnz     short loc_1800058A3
0x1800058c5  jmp     loc_1800057FF
0x1800058ca  mov     ebx, r11d
0x1800058cd  nop     dword ptr [rax]
0x1800058d0  movsx   r9d, byte ptr [r10]
0x1800058d4  test    r9b, r9b
0x1800058d7  jz      short loc_1800058EE
0x1800058d9  lea     eax, [rax+rax*4]
0x1800058dc  dec     r8d
0x1800058df  inc     r10
0x1800058e2  lea     eax, [rax-18h]
0x1800058e5  lea     eax, [r9+rax*2]
0x1800058e9  add     ebx, 0FFFFFFFFh
0x1800058ec  jnz     short loc_1800058D0
0x1800058ee  mov     [rcx+2], al
0x1800058f1  xor     eax, eax
0x1800058f3  cmp     r8d, r11d
0x1800058f6  jb      loc_180005812
0x1800058fc  mov     ebx, r11d
0x1800058ff  nop
0x180005900  movsx   r9d, byte ptr [r10]
0x180005904  test    r9b, r9b
0x180005907  jz      short loc_18000591E
0x180005909  lea     eax, [rax+rax*4]
0x18000590c  dec     r8d
0x18000590f  inc     r10
0x180005912  lea     eax, [rax-18h]
0x180005915  lea     eax, [r9+rax*2]
0x180005919  add     ebx, 0FFFFFFFFh
0x18000591c  jnz     short loc_180005900
0x18000591e  mov     [rcx+3], al
0x180005921  xor     eax, eax
0x180005923  cmp     r8d, r11d
0x180005926  jb      loc_180005817
0x18000592c  mov     ebx, r11d
0x18000592f  nop
0x180005930  movsx   r9d, byte ptr [r10]
0x180005934  test    r9b, r9b
0x180005937  jz      loc_180005817
0x18000593d  lea     eax, [rax+rax*4]
0x180005940  dec     r8d
0x180005943  inc     r10
0x180005946  lea     eax, [rax-18h]
0x180005949  lea     eax, [r9+rax*2]
0x18000594d  add     ebx, 0FFFFFFFFh
0x180005950  jnz     short loc_180005930
0x180005952  jmp     loc_180005817
0x180005960  movsx   r8d, byte ptr [r10]
0x180005964  test    r8b, r8b
0x180005967  jz      loc_18000586F
0x18000596d  lea     eax, [rax+rax*4]
0x180005970  dec     r9d
0x180005973  inc     r10
0x180005976  lea     eax, [rax-18h]
0x180005979  lea     eax, [r8+rax*2]
0x18000597d  add     r11d, 0FFFFFFFFh
0x180005981  jnz     short loc_180005960
0x180005983  jmp     loc_18000586F
0x180005988  cmp     al, 2Bh ; '+'
0x18000598a  jz      loc_180005A30
0x180005990  cmp     al, 2Dh ; '-'
0x180005992  jnz     loc_180005888
0x180005998  inc     r10
0x18000599b  lea     r8d, [r9-1]
0x18000599f  xorps   xmm2, xmm2
0x1800059a2  test    r8d, r8d
0x1800059a5  jz      short loc_1800059BA
0x1800059a7  movsd   xmm1, cs:__real@3ff0000000000000
0x1800059af  movsx   ecx, byte ptr [r10]
0x1800059b3  lea     eax, [rcx-30h]
0x1800059b6  cmp     al, 9
0x1800059b8  jbe     short loc_180005A0A
0x1800059ba  movaps  xmm0, xmm2
0x1800059bd  mov     eax, 51EB851Fh
0x1800059c2  mulsd   xmm0, cs:__real@40c3880000000000
0x1800059ca  mulsd   xmm2, cs:__real@4059000000000000
0x1800059d2  cvttsd2si ecx, xmm0
0x1800059d6  mulsd   xmm2, cs:__real@404e000000000000
0x1800059de  imul    ecx
0x1800059e0  sar     edx, 5
0x1800059e3  mov     eax, edx
0x1800059e5  shr     eax, 1Fh
0x1800059e8  add     edx, eax
0x1800059ea  imul    eax, edx, 64h ; 'd'
0x1800059ed  sub     ecx, eax
0x1800059ef  movd    xmm0, ecx
0x1800059f3  cvtdq2pd xmm0, xmm0
0x1800059f7  addsd   xmm0, xmm2
0x1800059fb  cvttsd2si eax, xmm0
0x1800059ff  neg     ax
0x180005a02  mov     [rbx], ax
0x180005a05  jmp     loc_180005888
0x180005a0a  divsd   xmm1, cs:__real@4024000000000000
0x180005a12  lea     eax, [rcx-30h]
0x180005a15  inc     r10
0x180005a18  movd    xmm0, eax
0x180005a1c  cvtdq2pd xmm0, xmm0
0x180005a20  mulsd   xmm0, xmm1
0x180005a24  addsd   xmm2, xmm0
0x180005a28  add     r8d, 0FFFFFFFFh
0x180005a2c  jnz     short loc_1800059AF
0x180005a2e  jmp     short loc_1800059BA
0x180005a30  lea     edx, [r9-1]
0x180005a34  inc     r10
0x180005a37  mov     rcx, r10
0x180005a3a  mov     [rsp+28h+arg_18], r10
0x180005a3f  lea     r9, [rsp+28h+arg_0]
0x180005a44  mov     [rsp+28h+arg_0], edx
0x180005a48  lea     r8, [rsp+28h+arg_18]
0x180005a4d  call    scanfrac
0x180005a52  mov     r10, [rsp+28h+arg_18]
0x180005a57  movaps  xmm3, xmm0
0x180005a5a  mulsd   xmm3, cs:__real@40c3880000000000
0x180005a62  movaps  xmm4, xmm0
0x180005a65  mov     eax, 51EB851Fh
0x180005a6a  mov     r8d, [rsp+28h+arg_0]
0x180005a6f  mulsd   xmm4, cs:__real@4059000000000000
0x180005a77  cvttsd2si ecx, xmm3
0x180005a7b  mulsd   xmm4, cs:__real@404e000000000000
0x180005a83  imul    ecx
0x180005a85  sar     edx, 5
0x180005a88  mov     eax, edx
0x180005a8a  shr     eax, 1Fh
0x180005a8d  add     edx, eax
0x180005a8f  imul    eax, edx, 64h ; 'd'
0x180005a92  sub     ecx, eax
0x180005a94  movd    xmm0, ecx
0x180005a98  cvtdq2pd xmm0, xmm0
0x180005a9c  addsd   xmm0, xmm4
0x180005aa0  cvttsd2si eax, xmm0
0x180005aa4  mov     [r11], ax
0x180005aa8  jmp     loc_180005888
0x180005aad  test    r8d, r8d
0x180005ab0  jnz     loc_18000589C
0x180005ab6  xor     eax, eax
0x180005ab8  mov     [rcx+5], r8b
0x180005abc  mov     [rcx+8], ax
0x180005ac0  mov     [rcx+6], r8b
0x180005ac4  jmp     loc_180005888
0x180005ac9  cmp     byte ptr [r10], 0
0x180005acd  jnz     loc_18000589C
0x180005ad3  jmp     loc_180005891
```
