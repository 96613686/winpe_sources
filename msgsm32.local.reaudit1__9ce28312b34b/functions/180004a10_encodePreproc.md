# encodePreproc

- ea: `0x180004a10`
- end: `0x180004c1b`
- name: `encodePreproc`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005350`

## callees

- `0x180001400`
- `0x180004a10`

## pseudocode

```c
__int64 __fastcall encodePreproc(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 i; // rax
  int v5; // ecx
  __int64 v6; // r10
  __int16 v7; // ax
  __int16 v8; // bx
  int v9; // edx
  int v10; // r11d
  int v11; // r8d
  int v12; // eax
  int v13; // ecx
  unsigned int v14; // ecx
  int v15; // edx
  int v16; // eax
  unsigned int v17; // edx
  __int64 v18; // rdx
  int v19; // r8d
  int v20; // eax
  __int64 result; // rax
  _WORD v23[320]; // [rsp+10h] [rbp-2B8h]

  for ( i = 0; i != 160; i += 8 )
    *(__m128i *)&v23[i + 160] = _mm_slli_epi16(_mm_srai_epi16(_mm_loadu_si128((const __m128i *)(a2 + 2 * i)), 3u), 2u);
  v5 = *(_DWORD *)(a1 + 574);
  v6 = 0;
  v7 = *(_WORD *)(a1 + 572);
  do
  {
    v8 = v23[v6 + 160];
    v9 = v8 - v7;
    if ( v9 >= -32768 )
    {
      if ( v9 > 0x7FFF )
        LOWORD(v9) = 0x7FFF;
    }
    else
    {
      LOWORD(v9) = 0x8000;
    }
    v10 = (__int16)(v5 >> 15);
    v11 = (__int16)v9 << 15;
    v12 = v5 - (v10 << 15);
    if ( v5 >= 0 )
    {
      if ( v5 > 0 && ((__int16)(v5 >> 15) & 0x10000) != 0 && v12 < 0 )
        LOWORD(v12) = -1;
    }
    else if ( v10 << 15 > 0 && v12 > 0 )
    {
      LOWORD(v12) = 0;
    }
    v13 = 32735 * (__int16)v12 + 0x4000;
    if ( v13 >= 0x40000000 )
      v13 = 0x3FFFFFFF;
    v14 = (unsigned int)v13 >> 15;
    v15 = v11 + (__int16)v14;
    if ( v11 >= 0 )
    {
      if ( (v14 & 0x8000u) == 0 && v15 < 0 )
        v15 = 0x7FFFFFFF;
    }
    else if ( (v14 & 0x8000u) != 0 && v15 >= 0 )
    {
      v15 = 0x80000000;
    }
    v5 = ((65470 * v10) >> 1) + v15;
    if ( (65470 * v10) >> 1 >= 0 )
    {
      if ( v15 >= 0 && v5 < 0 )
      {
        v5 = 0x7FFFFFFF;
        v17 = 0x7FFFFFFF;
LABEL_34:
        v16 = 0x7FFFFFFF;
        goto LABEL_35;
      }
    }
    else if ( v15 < 0 && v5 >= 0 )
    {
      v5 = 0x80000000;
      v16 = -2147467264;
      v17 = 0x80000000;
      goto LABEL_35;
    }
    v16 = v5 + 0x4000;
    v17 = ((65470 * v10) >> 1) + v15;
    if ( v5 >= 0 && v16 < 0 )
      goto LABEL_34;
LABEL_35:
    v23[v6++] = v16 >> 15;
    v7 = v8;
  }
  while ( v6 != 160 );
  *(_DWORD *)(a1 + 574) = v17;
  v18 = 0;
  *(_WORD *)(a1 + 572) = v8;
  do
  {
    v19 = (__int16)v23[v18];
    v20 = 0x4000 - 28180 * *(__int16 *)(a1 + 578);
    if ( v20 >= 0x40000000 )
      v20 = 0x3FFFFFFF;
    result = (unsigned int)(v19 + (__int16)((unsigned int)v20 >> 15));
    if ( (int)result >= -32768 )
    {
      if ( (int)result > 0x7FFF )
        result = 0x7FFF;
    }
    else
    {
      result = 0x8000;
    }
    *(_WORD *)(a3 + 2 * v18++) = result;
    *(_WORD *)(a1 + 578) = v19;
  }
  while ( v18 != 160 );
  return result;
}

```

## disassembly

```asm
0x180004a10  mov     [rsp+arg_8], rbx
0x180004a15  push    rbp
0x180004a16  push    rsi
0x180004a17  push    rdi
0x180004a18  push    r12
0x180004a1a  push    r13
0x180004a1c  sub     rsp, 2A0h
0x180004a23  mov     rax, cs:__security_cookie
0x180004a2a  xor     rax, rsp
0x180004a2d  mov     [rsp+2C8h+var_38], rax
0x180004a35  xor     esi, esi
0x180004a37  mov     [rsp+2C8h+var_2C8], r8
0x180004a3b  mov     eax, esi
0x180004a3d  mov     r9, rcx
0x180004a40  mov     r13d, 0A0h
0x180004a46  movdqu  xmm0, xmmword ptr [rdx+rax*2]
0x180004a4b  psraw   xmm0, 3
0x180004a50  psllw   xmm0, 2
0x180004a55  movdqu  [rsp+rax*2+2C8h+var_178], xmm0
0x180004a5e  add     rax, 8
0x180004a62  cmp     rax, r13
0x180004a65  jnz     short loc_180004A46
0x180004a67  mov     ecx, [rcx+23Eh]
0x180004a6d  mov     r10, rsi
0x180004a70  movzx   eax, word ptr [r9+23Ch]
0x180004a78  mov     ebp, 7FFFFFFFh
0x180004a7d  mov     edi, 3FFFFFFFh
0x180004a82  mov     r12d, 0FFFF8000h
0x180004a88  movsx   ebx, word ptr [rsp+r10*2+2C8h+var_178]
0x180004a91  mov     edx, ebx
0x180004a93  cwde
0x180004a94  sub     edx, eax
0x180004a96  cmp     edx, r12d
0x180004a99  jge     short loc_180004AA1
0x180004a9b  movzx   edx, r12w
0x180004a9f  jmp     short loc_180004AAE
0x180004aa1  cmp     edx, 7FFFh
0x180004aa7  jle     short loc_180004AAE
0x180004aa9  mov     edx, 7FFFh
0x180004aae  movsx   r8d, dx
0x180004ab2  mov     eax, ecx
0x180004ab4  sar     eax, 0Fh
0x180004ab7  movsx   r11d, ax
0x180004abb  mov     eax, ecx
0x180004abd  mov     edx, r11d
0x180004ac0  shl     r8d, 0Fh
0x180004ac4  shl     edx, 0Fh
0x180004ac7  sub     eax, edx
0x180004ac9  test    ecx, ecx
0x180004acb  jns     short loc_180004ADC
0x180004acd  test    edx, edx
0x180004acf  jle     short loc_180004AE7
0x180004ad1  test    eax, eax
0x180004ad3  jle     short loc_180004AE7
0x180004ad5  mov     eax, 80000000h
0x180004ada  jmp     short loc_180004AE7
0x180004adc  jle     short loc_180004AE7
0x180004ade  test    edx, edx
0x180004ae0  jns     short loc_180004AE7
0x180004ae2  test    eax, eax
0x180004ae4  cmovs   eax, ebp
0x180004ae7  cwde
0x180004ae8  imul    ecx, eax, 7FDFh
0x180004aee  add     ecx, 4000h
0x180004af4  cmp     ecx, 40000000h
0x180004afa  cmovge  ecx, edi
0x180004afd  shr     ecx, 0Fh
0x180004b00  movsx   edx, cx
0x180004b03  add     edx, r8d
0x180004b06  test    r8d, r8d
0x180004b09  jns     short loc_180004B1B
0x180004b0b  test    cx, cx
0x180004b0e  jns     short loc_180004B26
0x180004b10  test    edx, edx
0x180004b12  js      short loc_180004B26
0x180004b14  mov     edx, 80000000h
0x180004b19  jmp     short loc_180004B26
0x180004b1b  test    cx, cx
0x180004b1e  js      short loc_180004B26
0x180004b20  test    edx, edx
0x180004b22  jns     short loc_180004B26
0x180004b24  mov     edx, ebp
0x180004b26  imul    ecx, r11d, 0FFBEh
0x180004b2d  sar     ecx, 1
0x180004b2f  lea     ecx, [rcx+rdx]
0x180004b32  jns     short loc_180004B4A
0x180004b34  test    edx, edx
0x180004b36  jns     short loc_180004B58
0x180004b38  test    ecx, ecx
0x180004b3a  js      short loc_180004B58
0x180004b3c  mov     ecx, 80000000h
0x180004b41  mov     eax, 80004000h
0x180004b46  mov     edx, ecx
0x180004b48  jmp     short loc_180004B6A
0x180004b4a  test    edx, edx
0x180004b4c  js      short loc_180004B58
0x180004b4e  test    ecx, ecx
0x180004b50  jns     short loc_180004B58
0x180004b52  mov     ecx, ebp
0x180004b54  mov     edx, ebp
0x180004b56  jmp     short loc_180004B68
0x180004b58  lea     eax, [rcx+4000h]
0x180004b5e  mov     edx, ecx
0x180004b60  test    ecx, ecx
0x180004b62  js      short loc_180004B6A
0x180004b64  test    eax, eax
0x180004b66  jns     short loc_180004B6A
0x180004b68  mov     eax, ebp
0x180004b6a  sar     eax, 0Fh
0x180004b6d  mov     [rsp+r10*2+2C8h+var_2B8], ax
0x180004b73  inc     r10
0x180004b76  movzx   eax, bx
0x180004b79  cmp     r10, r13
0x180004b7c  jnz     loc_180004A88
0x180004b82  mov     rdi, [rsp+2C8h+var_2C8]
0x180004b86  mov     r10d, 3FFFFFFFh
0x180004b8c  mov     [r9+23Eh], edx
0x180004b93  mov     rdx, rsi
0x180004b96  mov     [r9+23Ch], bx
0x180004b9e  movsx   eax, word ptr [r9+242h]
0x180004ba6  movsx   r8d, [rsp+rdx*2+2C8h+var_2B8]
0x180004bac  imul    ecx, eax, 6E14h
0x180004bb2  mov     eax, 4000h
0x180004bb7  sub     eax, ecx
0x180004bb9  cmp     eax, 40000000h
0x180004bbe  cmovge  eax, r10d
0x180004bc2  shr     eax, 0Fh
0x180004bc5  cwde
0x180004bc6  add     eax, r8d
0x180004bc9  cmp     eax, r12d
0x180004bcc  jge     short loc_180004BD4
0x180004bce  movzx   eax, r12w
0x180004bd2  jmp     short loc_180004BE0
0x180004bd4  cmp     eax, 7FFFh
0x180004bd9  jle     short loc_180004BE0
0x180004bdb  mov     eax, 7FFFh
0x180004be0  mov     [rdi+rdx*2], ax
0x180004be4  inc     rdx
0x180004be7  mov     [r9+242h], r8w
0x180004bef  cmp     rdx, r13
0x180004bf2  jnz     short loc_180004B9E
0x180004bf4  mov     rcx, [rsp+2C8h+var_38]
0x180004bfc  xor     rcx, rsp; StackCookie
0x180004bff  call    __security_check_cookie
0x180004c04  mov     rbx, [rsp+2C8h+arg_8]
0x180004c0c  add     rsp, 2A0h
0x180004c13  pop     r13
0x180004c15  pop     r12
0x180004c17  pop     rdi
0x180004c18  pop     rsi
0x180004c19  pop     rbp
0x180004c1a  retn
```
