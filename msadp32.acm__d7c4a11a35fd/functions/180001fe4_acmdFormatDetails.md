# acmdFormatDetails

- ea: `0x180001fe4`
- end: `0x1800021b2`
- name: `acmdFormatDetails`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001cd0`

## callees

- `0x180001fe4`
- `0x1800028b8`
- `0x180002910`
- `0x180002988`

## pseudocode

```c
__int64 __fastcall acmdFormatDetails(__int64 a1, __int64 a2, char a3)
{
  __int64 v3; // rbx
  int v5; // r8d
  unsigned int v7; // ecx
  unsigned __int64 v8; // rax
  unsigned int v9; // ecx
  unsigned int v10; // r10d
  unsigned int v11; // ecx
  unsigned int v12; // edx
  unsigned __int16 v13; // cx
  unsigned int v14; // eax
  __int64 v15; // rcx
  unsigned int v16; // ecx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rdx
  int v19; // r8d
  int IsValidFormat; // eax
  int v21; // eax

  v3 = *(_QWORD *)(a2 + 16);
  v5 = a3 & 0xF;
  if ( v5 )
  {
    if ( v5 != 1 )
      return 8;
  }
  else if ( *(_DWORD *)(a2 + 8) == 1 )
  {
    v16 = *(_DWORD *)(a2 + 4);
    if ( v16 >= 0x10 )
      return 512;
    *(_WORD *)v3 = 1;
    v17 = (unsigned __int64)v16 >> 2;
    v18 = ((unsigned __int64)v16 >> 1) & 1;
    LOWORD(v16) = (v16 & 1) + 1;
    v19 = gauFormatIndexToSampleRate[v17];
    *(_WORD *)(v3 + 2) = v16;
    *(_DWORD *)(v3 + 4) = v19;
    LOWORD(v17) = gauFormatIndexToBitsPerSample[2 * v18];
    *(_WORD *)(v3 + 14) = v17;
    LODWORD(v17) = (unsigned __int16)((unsigned __int16)v17 >> 3 << (v16 >> 1));
    *(_WORD *)(v3 + 12) = v17;
    *(_DWORD *)(v3 + 8) = v19 * v17;
  }
  else
  {
    if ( *(_DWORD *)(a2 + 8) != 2 )
      return 512;
    v7 = *(_DWORD *)(a2 + 4);
    if ( v7 >= 8 )
      return 512;
    v8 = (unsigned __int64)v7 >> 1;
    v9 = (unsigned __int16)((v7 & 1) + 1);
    *(_WORD *)v3 = 2;
    v10 = gauFormatIndexToSampleRate[v8];
    *(_WORD *)(v3 + 2) = v9;
    v11 = v9 >> 1;
    *(_DWORD *)(v3 + 4) = v10;
    *(_WORD *)(v3 + 14) = 4;
    if ( v10 <= 0x2B11 )
      LOWORD(v12) = 256 << v11;
    else
      v12 = (256 << v11) * (v10 / 0x2AF8);
    *(_WORD *)(v3 + 12) = v12;
    *(_WORD *)(v3 + 16) = 32;
    v13 = 8 * ((unsigned int)(unsigned __int16)v12 - (7 << v11)) / (4 << v11) + 2;
    *(_WORD *)(v3 + 18) = v13;
    *(_WORD *)(v3 + 20) = 7;
    v14 = v10 * (unsigned __int16)v12 / v13;
    v15 = 0;
    *(_DWORD *)(v3 + 8) = v14;
    do
    {
      *(_WORD *)(v3 + 4 * v15 + 22) = gaiCoef1[v15];
      *(_WORD *)(v3 + 4 * v15 + 24) = gaiCoef2[v15];
      ++v15;
    }
    while ( v15 != 7 );
  }
  if ( *(_WORD *)v3 == 1 )
  {
    IsValidFormat = pcmIsValidFormat(v3);
  }
  else
  {
    if ( *(_WORD *)v3 != 2 || !(unsigned int)adpcmIsValidFormat(v3) )
      return 512;
    IsValidFormat = adpcmIsMagicFormat(v3);
  }
  if ( !IsValidFormat )
    return 512;
  *(_DWORD *)(a2 + 12) = 1;
  *(_WORD *)(a2 + 28) = 0;
  v21 = 284;
  if ( *(_DWORD *)a2 < 0x11Cu )
    v21 = *(_DWORD *)a2;
  *(_DWORD *)a2 = v21;
  return 0;
}

```

## disassembly

```asm
0x180001fe4  push    rbx
0x180001fe6  push    rbp
0x180001fe7  push    rsi
0x180001fe8  push    rdi
0x180001fe9  push    r14
0x180001feb  sub     rsp, 20h
0x180001fef  mov     rbx, [rdx+10h]
0x180001ff3  mov     rdi, rdx
0x180001ff6  mov     esi, 1
0x180001ffb  and     r8d, 0Fh
0x180001fff  jz      short loc_180002012
0x180002001  cmp     r8d, esi
0x180002004  jz      loc_18000215C
0x18000200a  lea     eax, [rsi+7]
0x18000200d  jmp     loc_1800021A7
0x180002012  mov     ecx, [rdx+8]
0x180002015  sub     ecx, esi
0x180002017  jz      loc_1800020FE
0x18000201d  cmp     ecx, esi
0x18000201f  jnz     loc_1800021A2
0x180002025  mov     ecx, [rdx+4]
0x180002028  cmp     ecx, 8
0x18000202b  jnb     loc_1800021A2
0x180002031  mov     eax, ecx
0x180002033  lea     r9, cs:180000000h
0x18000203a  and     cx, si
0x18000203d  shr     rax, 1
0x180002040  add     cx, si
0x180002043  mov     r14d, 2
0x180002049  movzx   ecx, cx
0x18000204c  mov     r8d, 100h
0x180002052  mov     [rbx], r14w
0x180002056  mov     r10d, ds:rva gauFormatIndexToSampleRate[r9+rax*4]
0x18000205e  mov     [rbx+2], cx
0x180002062  lea     r11d, [r14+2]
0x180002066  shr     ecx, 1
0x180002068  shl     r8d, cl
0x18000206b  mov     [rbx+4], r10d
0x18000206f  mov     [rbx+0Eh], r11w
0x180002074  cmp     r10d, 2B11h
0x18000207b  jbe     short loc_18000208E
0x18000207d  mov     eax, 0BEA67251h
0x180002082  mul     r10d
0x180002085  shr     edx, 0Dh
0x180002088  imul    edx, r8d
0x18000208c  jmp     short loc_180002091
0x18000208e  mov     edx, r8d
0x180002091  movzx   r8d, dx
0x180002095  mov     ebp, 7
0x18000209a  shl     r11d, cl
0x18000209d  mov     edx, ebp
0x18000209f  shl     edx, cl
0x1800020a1  mov     eax, r8d
0x1800020a4  sub     eax, edx
0x1800020a6  mov     [rbx+0Ch], r8w
0x1800020ab  shl     eax, 3
0x1800020ae  xor     edx, edx
0x1800020b0  div     r11d
0x1800020b3  imul    r8d, r10d
0x1800020b7  xor     edx, edx
0x1800020b9  add     ax, r14w
0x1800020bd  mov     word ptr [rbx+10h], 20h ; ' '
0x1800020c3  movzx   ecx, ax
0x1800020c6  mov     [rbx+12h], cx
0x1800020ca  mov     [rbx+14h], bp
0x1800020ce  mov     eax, r8d
0x1800020d1  div     ecx
0x1800020d3  xor     ecx, ecx
0x1800020d5  mov     [rbx+8], eax
0x1800020d8  movzx   eax, word ptr ds:rva gaiCoef1[r9+rcx*4]
0x1800020e1  mov     [rbx+rcx*4+16h], ax
0x1800020e6  movzx   eax, word ptr ds:rva gaiCoef2[r9+rcx*4]
0x1800020ef  mov     [rbx+rcx*4+18h], ax
0x1800020f4  add     rcx, rsi
0x1800020f7  cmp     rcx, rbp
0x1800020fa  jnz     short loc_1800020D8
0x1800020fc  jmp     short loc_18000215C
0x1800020fe  mov     ecx, [rdx+4]
0x180002101  cmp     ecx, 10h
0x180002104  jnb     loc_1800021A2
0x18000210a  mov     edx, ecx
0x18000210c  mov     [rbx], si
0x18000210f  mov     eax, ecx
0x180002111  shr     rdx, 1
0x180002114  shr     rax, 2
0x180002118  lea     r9, cs:180000000h
0x18000211f  and     cx, si
0x180002122  and     rdx, rsi
0x180002125  add     cx, si
0x180002128  mov     r8d, ds:rva gauFormatIndexToSampleRate[r9+rax*4]
0x180002130  mov     [rbx+2], cx
0x180002134  shr     ecx, 1
0x180002136  mov     [rbx+4], r8d
0x18000213a  movzx   eax, ds:rva gauFormatIndexToBitsPerSample[r9+rdx*4]
0x180002143  mov     [rbx+0Eh], ax
0x180002147  shr     ax, 3
0x18000214b  shl     ax, cl
0x18000214e  movzx   eax, ax
0x180002151  mov     [rbx+0Ch], ax
0x180002155  imul    eax, r8d
0x180002159  mov     [rbx+8], eax
0x18000215c  movzx   edx, word ptr [rbx]
0x18000215f  sub     edx, esi
0x180002161  jz      short loc_18000217D
0x180002163  cmp     edx, esi
0x180002165  jnz     short loc_1800021A2
0x180002167  mov     rcx, rbx
0x18000216a  call    adpcmIsValidFormat
0x18000216f  test    eax, eax
0x180002171  jz      short loc_1800021A2
0x180002173  mov     rcx, rbx
0x180002176  call    adpcmIsMagicFormat
0x18000217b  jmp     short loc_180002185
0x18000217d  mov     rcx, rbx
0x180002180  call    pcmIsValidFormat
0x180002185  test    eax, eax
0x180002187  jz      short loc_1800021A2
0x180002189  xor     eax, eax
0x18000218b  mov     [rdi+0Ch], esi
0x18000218e  mov     [rdi+1Ch], ax
0x180002192  mov     eax, 11Ch
0x180002197  cmp     [rdi], eax
0x180002199  cmovb   eax, [rdi]
0x18000219c  mov     [rdi], eax
0x18000219e  xor     eax, eax
0x1800021a0  jmp     short loc_1800021A7
0x1800021a2  mov     eax, 200h
0x1800021a7  add     rsp, 20h
0x1800021ab  pop     r14
0x1800021ad  pop     rdi
0x1800021ae  pop     rsi
0x1800021af  pop     rbp
0x1800021b0  pop     rbx
0x1800021b1  retn
```
