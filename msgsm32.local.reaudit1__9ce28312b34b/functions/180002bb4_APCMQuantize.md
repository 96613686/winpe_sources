# APCMQuantize

- ea: `0x180002bb4`
- end: `0x180002e2b`
- name: `APCMQuantize`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004c24`

## callees

- `0x180002bb4`

## pseudocode

```c
__int64 __fastcall APCMQuantize(__int64 a1, __int64 a2, _WORD *a3, __int64 a4, _WORD *a5, _WORD *a6)
{
  __int16 v7; // r10
  __int64 i; // rcx
  __int16 v11; // ax
  __int16 v12; // dx
  __int16 v13; // cx
  __int16 v14; // r8
  int v15; // r9d
  bool v16; // cc
  int v17; // eax
  int v18; // ecx
  int v19; // eax
  int v20; // ecx
  _WORD *v21; // rdi
  __int16 v22; // r9
  int v23; // r8d
  int v24; // edx
  __int16 v25; // dx
  int v26; // r9d
  int v27; // eax
  int v28; // ecx
  int v29; // r11d
  __int16 v30; // dx
  __int64 v31; // r8
  int v32; // r9d
  int v33; // eax
  int v34; // eax
  int v35; // eax
  __int64 result; // rax

  v7 = 0;
  for ( i = 0; i != 13; ++i )
  {
    v11 = *(_WORD *)(a2 + 2 * i);
    if ( v11 < 0 )
    {
      if ( v11 == (__int16)0x8000 )
        v11 = 0x7FFF;
      else
        v11 = -v11;
    }
    if ( v11 > v7 )
      v7 = v11;
  }
  v12 = v7 >> 9;
  v13 = 0;
  v14 = 0;
  v15 = 6;
  do
  {
    v16 = v12 <= 0;
    v12 >>= 1;
    if ( v16 )
    {
      v13 = 1;
    }
    else if ( !v13 )
    {
      v17 = v14 + 1;
      if ( v17 >= -32768 )
      {
        if ( v17 > 0x7FFF )
          LOWORD(v17) = 0x7FFF;
      }
      else
      {
        LOWORD(v17) = 0x8000;
      }
      v14 = v17;
    }
    --v15;
  }
  while ( v15 );
  v18 = v14 + 5;
  if ( v18 >= -32768 )
  {
    if ( v18 > 0x7FFF )
      LOWORD(v18) = 0x7FFF;
  }
  else
  {
    LOWORD(v18) = 0x8000;
  }
  if ( (v18 & 0x8000u) != 0 )
    v19 = v7 << -(char)v18;
  else
    v19 = v7 >> v18;
  v20 = (__int16)v19 + (__int16)(8 * v14);
  if ( v20 >= -32768 )
  {
    if ( v20 > 0x7FFF )
      LOWORD(v20) = 0x7FFF;
  }
  else
  {
    LOWORD(v20) = 0x8000;
  }
  v21 = a5;
  v22 = 15;
  *a3 = v20;
  *a5 = 0;
  if ( (__int16)v20 <= 15 )
  {
    LOWORD(v23) = 0;
  }
  else
  {
    v23 = ((__int16)v20 >> 3) - 1;
    if ( v23 >= -32768 )
    {
      if ( v23 > 0x7FFF )
        LOWORD(v23) = 0x7FFF;
    }
    else
    {
      LOWORD(v23) = 0x8000;
    }
    *a5 = v23;
  }
  v24 = (__int16)v20 - (__int16)(8 * v23);
  if ( v24 >= -32768 )
  {
    if ( v24 <= 0x7FFF )
    {
      *a6 = v24;
      if ( !(_WORD)v24 )
      {
        LOWORD(v23) = -4;
        goto LABEL_59;
      }
      LOWORD(v20) = v20 - 8 * v23;
    }
    else
    {
      LOWORD(v20) = 0x7FFF;
    }
  }
  else
  {
    LOWORD(v20) = 0x8000;
  }
  v25 = 0;
  v26 = 3;
  do
  {
    if ( (__int16)v20 <= 7 )
    {
      if ( !v25 )
      {
        v20 = (__int16)(2 * v20) + 1;
        if ( v20 >= -32768 )
        {
          if ( v20 > 0x7FFF )
            LOWORD(v20) = 0x7FFF;
        }
        else
        {
          LOWORD(v20) = 0x8000;
        }
        v27 = (__int16)v23 - 1;
        if ( v27 >= -32768 )
        {
          if ( v27 > 0x7FFF )
            LOWORD(v27) = 0x7FFF;
        }
        else
        {
          LOWORD(v27) = 0x8000;
        }
        LOWORD(v23) = v27;
      }
    }
    else
    {
      v25 = 1;
    }
    --v26;
  }
  while ( v26 );
  v21 = a5;
  v22 = v20;
LABEL_59:
  v28 = v22 - 8;
  *v21 = v23;
  if ( v28 >= -32768 )
  {
    if ( v28 > 0x7FFF )
      LOWORD(v28) = 0x7FFF;
  }
  else
  {
    LOWORD(v28) = 0x8000;
  }
  v29 = 6 - (__int16)v23;
  *a6 = v28;
  if ( v29 >= -32768 )
  {
    if ( v29 <= 0x7FFF )
      v30 = 6 - v23;
    else
      v30 = 0x7FFF;
  }
  else
  {
    v30 = 0x8000;
  }
  v31 = 0;
  v32 = *((__int16 *)NRFAC + (__int16)v28);
  do
  {
    v33 = *(__int16 *)(a2 + 2 * v31);
    if ( v30 < 0 )
      v34 = v33 >> -(char)v30;
    else
      v34 = v33 << v30;
    v35 = v32 * (__int16)v34;
    if ( v35 >= 0x40000000 )
      v35 = 0x3FFFFFFF;
    result = (unsigned int)(((__int16)((unsigned int)v35 >> 15) >> 12) + 4);
    if ( (int)result >= -32768 )
    {
      if ( (int)result > 0x7FFF )
        result = 0x7FFF;
    }
    else
    {
      result = 0x8000;
    }
    *(_WORD *)(a4 + 2 * v31++) = result;
  }
  while ( v31 != 13 );
  return result;
}

```

## disassembly

```asm
0x180002bb4  push    rbx
0x180002bb6  push    rbp
0x180002bb7  push    rsi
0x180002bb8  push    rdi
0x180002bb9  push    r12
0x180002bbb  push    r14
0x180002bbd  push    r15
0x180002bbf  xor     r12d, r12d
0x180002bc2  mov     r14, r9
0x180002bc5  mov     r10d, r12d
0x180002bc8  mov     ecx, r12d
0x180002bcb  mov     rbx, r8
0x180002bce  mov     rsi, rdx
0x180002bd1  mov     ebp, 7FFFh
0x180002bd6  mov     r15d, 0FFFF8000h
0x180002bdc  movzx   eax, word ptr [rdx+rcx*2]
0x180002be0  test    ax, ax
0x180002be3  jns     short loc_180002BF2
0x180002be5  cmp     ax, r15w
0x180002be9  jnz     short loc_180002BEF
0x180002beb  mov     eax, ebp
0x180002bed  jmp     short loc_180002BF2
0x180002bef  neg     ax
0x180002bf2  cmp     ax, r10w
0x180002bf6  cmovg   r10w, ax
0x180002bfb  inc     rcx
0x180002bfe  cmp     rcx, 0Dh
0x180002c02  jnz     short loc_180002BDC
0x180002c04  mov     r11d, 6
0x180002c0a  movzx   edx, r10w
0x180002c0e  sar     dx, 9
0x180002c12  mov     ecx, r12d
0x180002c15  mov     r8d, r12d
0x180002c18  mov     r9d, r11d
0x180002c1b  lea     edi, [r11-5]
0x180002c1f  movzx   eax, dx
0x180002c22  sar     ax, 1
0x180002c25  test    dx, dx
0x180002c28  movzx   edx, ax
0x180002c2b  jg      short loc_180002C32
0x180002c2d  movzx   ecx, di
0x180002c30  jmp     short loc_180002C52
0x180002c32  test    cx, cx
0x180002c35  jnz     short loc_180002C52
0x180002c37  movsx   eax, r8w
0x180002c3b  inc     eax
0x180002c3d  cmp     eax, r15d
0x180002c40  jge     short loc_180002C48
0x180002c42  movzx   eax, r15w
0x180002c46  jmp     short loc_180002C4E
0x180002c48  cmp     eax, ebp
0x180002c4a  jle     short loc_180002C4E
0x180002c4c  mov     eax, ebp
0x180002c4e  movzx   r8d, ax
0x180002c52  add     r9d, 0FFFFFFFFh
0x180002c56  jnz     short loc_180002C1F
0x180002c58  movsx   ecx, r8w
0x180002c5c  add     ecx, 5
0x180002c5f  cmp     ecx, r15d
0x180002c62  jge     short loc_180002C6A
0x180002c64  movzx   ecx, r15w
0x180002c68  jmp     short loc_180002C70
0x180002c6a  cmp     ecx, ebp
0x180002c6c  jle     short loc_180002C70
0x180002c6e  mov     ecx, ebp
0x180002c70  movsx   edx, cx
0x180002c73  movsx   eax, r10w
0x180002c77  test    cx, cx
0x180002c7a  js      short loc_180002C82
0x180002c7c  mov     ecx, edx
0x180002c7e  sar     eax, cl
0x180002c80  jmp     short loc_180002C88
0x180002c82  neg     edx
0x180002c84  mov     cl, dl
0x180002c86  shl     eax, cl
0x180002c88  shl     r8w, 3
0x180002c8d  movsx   ecx, r8w
0x180002c91  cwde
0x180002c92  add     ecx, eax
0x180002c94  cmp     ecx, r15d
0x180002c97  jge     short loc_180002C9F
0x180002c99  movzx   ecx, r15w
0x180002c9d  jmp     short loc_180002CA5
0x180002c9f  cmp     ecx, ebp
0x180002ca1  jle     short loc_180002CA5
0x180002ca3  mov     ecx, ebp
0x180002ca5  mov     rdi, [rsp+38h+arg_20]
0x180002caa  mov     r9d, 0Fh
0x180002cb0  mov     [rbx], cx
0x180002cb3  movsx   edx, cx
0x180002cb6  mov     [rdi], r12w
0x180002cba  cmp     cx, r9w
0x180002cbe  jle     short loc_180002CE3
0x180002cc0  mov     r8d, edx
0x180002cc3  sar     r8d, 3
0x180002cc7  dec     r8d
0x180002cca  cmp     r8d, r15d
0x180002ccd  jge     short loc_180002CD5
0x180002ccf  movzx   r8d, r15w
0x180002cd3  jmp     short loc_180002CDD
0x180002cd5  cmp     r8d, ebp
0x180002cd8  jle     short loc_180002CDD
0x180002cda  mov     r8d, ebp
0x180002cdd  mov     [rdi], r8w
0x180002ce1  jmp     short loc_180002CE6
0x180002ce3  mov     r8d, r12d
0x180002ce6  mov     r10, [rsp+38h+arg_28]
0x180002ceb  movzx   eax, r8w
0x180002cef  shl     ax, 3
0x180002cf3  movsx   ecx, ax
0x180002cf6  sub     edx, ecx
0x180002cf8  cmp     edx, r15d
0x180002cfb  jge     short loc_180002D03
0x180002cfd  movzx   ecx, r15w
0x180002d01  jmp     short loc_180002D1F
0x180002d03  cmp     edx, ebp
0x180002d05  jle     short loc_180002D0B
0x180002d07  mov     ecx, ebp
0x180002d09  jmp     short loc_180002D1F
0x180002d0b  mov     [r10], dx
0x180002d0f  test    dx, dx
0x180002d12  jnz     short loc_180002D1C
0x180002d14  mov     r8d, 0FFFFFFFCh
0x180002d1a  jmp     short loc_180002D7F
0x180002d1c  movzx   ecx, dx
0x180002d1f  mov     edi, 1
0x180002d24  mov     edx, r12d
0x180002d27  lea     r9d, [rdi+2]
0x180002d2b  cmp     cx, 7
0x180002d2f  jle     short loc_180002D36
0x180002d31  movzx   edx, di
0x180002d34  jmp     short loc_180002D70
0x180002d36  test    dx, dx
0x180002d39  jnz     short loc_180002D70
0x180002d3b  add     cx, cx
0x180002d3e  movsx   ecx, cx
0x180002d41  inc     ecx
0x180002d43  cmp     ecx, r15d
0x180002d46  jge     short loc_180002D4E
0x180002d48  movzx   ecx, r15w
0x180002d4c  jmp     short loc_180002D55
0x180002d4e  cmp     ecx, ebp
0x180002d50  jle     short loc_180002D55
0x180002d52  movzx   ecx, bp
0x180002d55  movsx   eax, r8w
0x180002d59  dec     eax
0x180002d5b  cmp     eax, r15d
0x180002d5e  jge     short loc_180002D66
0x180002d60  movzx   eax, r15w
0x180002d64  jmp     short loc_180002D6C
0x180002d66  cmp     eax, ebp
0x180002d68  jle     short loc_180002D6C
0x180002d6a  mov     eax, ebp
0x180002d6c  movzx   r8d, ax
0x180002d70  add     r9d, 0FFFFFFFFh
0x180002d74  jnz     short loc_180002D2B
0x180002d76  mov     rdi, [rsp+38h+arg_20]
0x180002d7b  movzx   r9d, cx
0x180002d7f  movsx   ecx, r9w
0x180002d83  add     ecx, 0FFFFFFF8h
0x180002d86  mov     [rdi], r8w
0x180002d8a  cmp     ecx, r15d
0x180002d8d  jge     short loc_180002D95
0x180002d8f  movzx   ecx, r15w
0x180002d93  jmp     short loc_180002D9B
0x180002d95  cmp     ecx, ebp
0x180002d97  jle     short loc_180002D9B
0x180002d99  mov     ecx, ebp
0x180002d9b  movsx   eax, r8w
0x180002d9f  sub     r11d, eax
0x180002da2  mov     [r10], cx
0x180002da6  cmp     r11d, r15d
0x180002da9  jge     short loc_180002DB1
0x180002dab  movzx   edx, r15w
0x180002daf  jmp     short loc_180002DBE
0x180002db1  cmp     r11d, ebp
0x180002db4  jle     short loc_180002DBA
0x180002db6  mov     edx, ebp
0x180002db8  jmp     short loc_180002DBE
0x180002dba  movzx   edx, r11w
0x180002dbe  movsx   rax, cx
0x180002dc2  mov     r8, r12
0x180002dc5  lea     rcx, NRFAC
0x180002dcc  movsx   r9d, word ptr [rcx+rax*2]
0x180002dd1  movsx   eax, word ptr [rsi+r8*2]
0x180002dd6  mov     cl, dl
0x180002dd8  test    dx, dx
0x180002ddb  js      short loc_180002DE1
0x180002ddd  shl     eax, cl
0x180002ddf  jmp     short loc_180002DE5
0x180002de1  neg     cl
0x180002de3  sar     eax, cl
0x180002de5  cwde
0x180002de6  mov     ecx, 3FFFFFFFh
0x180002deb  imul    eax, r9d
0x180002def  cmp     eax, 40000000h
0x180002df4  cmovge  eax, ecx
0x180002df7  shr     eax, 0Fh
0x180002dfa  cwde
0x180002dfb  sar     eax, 0Ch
0x180002dfe  add     eax, 4
0x180002e01  cmp     eax, r15d
0x180002e04  jge     short loc_180002E0C
0x180002e06  movzx   eax, r15w
0x180002e0a  jmp     short loc_180002E12
0x180002e0c  cmp     eax, ebp
0x180002e0e  jle     short loc_180002E12
0x180002e10  mov     eax, ebp
0x180002e12  mov     [r14+r8*2], ax
0x180002e17  inc     r8
0x180002e1a  cmp     r8, 0Dh
0x180002e1e  jnz     short loc_180002DD1
0x180002e20  pop     r15
0x180002e22  pop     r14
0x180002e24  pop     r12
0x180002e26  pop     rdi
0x180002e27  pop     rsi
0x180002e28  pop     rbp
0x180002e29  pop     rbx
0x180002e2a  retn
```
