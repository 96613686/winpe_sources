# encodeLPCAnalysis

- ea: `0x1800041b4`
- end: `0x1800044e8`
- name: `encodeLPCAnalysis`
- size: `820`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005350`

## callees

- `0x180001400`
- `0x180002f40`
- `0x1800041b4`

## pseudocode

```c
__int64 __fastcall encodeLPCAnalysis(__int64 a1, __int64 a2, __int64 a3)
{
  __int16 v5; // cx
  __int64 i; // r8
  __int16 v7; // ax
  __int16 v8; // r10
  __int16 v9; // dx
  int v10; // ecx
  int v11; // ecx
  __int64 v12; // rdx
  char v13; // cl
  unsigned int j; // r9d
  int v15; // r8d
  __int64 v16; // rdi
  unsigned int k; // r11d
  __int64 v18; // rcx
  int v19; // eax
  __m128i v20; // xmm1
  __int64 m; // rax
  __int64 v22; // rdx
  __int16 v23; // cx
  __int16 v24; // ax
  int v25; // eax
  int v26; // ecx
  int v27; // r8d
  __int64 n; // r8
  int v29; // edx
  int v30; // eax
  int v31; // ecx
  __int16 v32; // cx
  int v33; // edx
  __int64 result; // rax
  int v35[10]; // [rsp+20h] [rbp-88h] BYREF
  _WORD v36[12]; // [rsp+48h] [rbp-60h] BYREF

  v5 = 0;
  for ( i = 0; i != 160; ++i )
  {
    v7 = *(_WORD *)(a2 + 2 * i);
    if ( v7 < 0 )
    {
      if ( v7 == (__int16)0x8000 )
        v7 = 0x7FFF;
      else
        v7 = -v7;
    }
    if ( v7 > v5 )
      v5 = v7;
  }
  if ( v5 )
  {
    v9 = 0;
    v10 = v5 << 16;
    if ( v10 > 0 )
    {
      while ( v10 < 0x40000000 )
      {
        ++v9;
        v10 *= 2;
      }
    }
    else if ( (unsigned int)(v10 + 0x3FFFFFFF) <= 0x3FFFFFFE )
    {
      do
      {
        ++v9;
        v10 *= 2;
      }
      while ( v10 > -1073741824 );
    }
    v11 = 4 - v9;
    if ( v11 >= -32768 )
    {
      if ( v11 <= 0x7FFF )
      {
        v8 = 4 - v9;
        if ( (__int16)v11 <= 0 )
          goto LABEL_24;
      }
      else
      {
        LOBYTE(v11) = -1;
        v8 = 0x7FFF;
      }
      v12 = 0;
      v13 = 15 - v11;
      do
      {
        *(_WORD *)(a2 + 2 * v12) = (unsigned int)(2 * (*(__int16 *)(a2 + 2 * v12) << v13) + 0x8000) >> 16;
        ++v12;
      }
      while ( v12 != 160 );
      goto LABEL_24;
    }
    v8 = 0x8000;
  }
  else
  {
    v8 = 0;
  }
LABEL_24:
  for ( j = 0; j < 9; ++j )
  {
    v15 = 0;
    v16 = j;
    for ( k = j; k < 0xA0; ++k )
    {
      v18 = (unsigned int)*(__int16 *)(a2 + 2LL * k);
      v19 = 2 * v18 * *(__int16 *)(a2 + 2LL * (k - j)) + v15;
      if ( v15 < 0 )
      {
        if ( (((_DWORD)v18 * *(__int16 *)(a2 + 2LL * (k - j))) & 0x40000000) != 0 && v19 >= 0 )
        {
          v15 = 0x80000000;
          continue;
        }
LABEL_32:
        v15 = v19;
        continue;
      }
      if ( (((_DWORD)v18 * *(__int16 *)(a2 + 2LL * (k - j))) & 0x40000000) != 0 )
        goto LABEL_32;
      v15 = 0x7FFFFFFF;
      if ( v19 >= 0 )
        goto LABEL_32;
    }
    v35[v16] = v15;
  }
  if ( v8 > 0 )
  {
    v20 = _mm_cvtsi32_si128(v8);
    for ( m = 0; m != 160; m += 8 )
      *(__m128i *)(a2 + 2 * m) = _mm_sll_epi16(_mm_loadu_si128((const __m128i *)(a2 + 2 * m)), v20);
  }
  Compr(v18, v35, (__int64)v36);
  v22 = 1;
  while ( 2 )
  {
    v23 = v36[v22];
    if ( v23 >= 0 )
    {
      v24 = v36[v22];
      goto LABEL_50;
    }
    if ( v23 == (__int16)0x8000 )
    {
      v25 = 6655;
LABEL_43:
      if ( v25 > 0x7FFF )
        LOWORD(v25) = 0x7FFF;
      goto LABEL_45;
    }
    v24 = -v23;
LABEL_50:
    if ( v24 >= 22118 )
    {
      v27 = v24;
      if ( v24 >= 31130 )
      {
        v25 = v24 - 26112;
        if ( v27 - 26112 >= -32768 )
          goto LABEL_43;
        LOWORD(v25) = 0x8000;
LABEL_45:
        LOWORD(v25) = 4 * v25;
      }
      else
      {
        v25 = v24 - 11059;
        if ( v27 - 11059 >= -32768 )
        {
          if ( v25 > 0x7FFF )
            LOWORD(v25) = 0x7FFF;
        }
        else
        {
          LOWORD(v25) = 0x8000;
        }
      }
    }
    else
    {
      LOWORD(v25) = v24 >> 1;
    }
    *((_WORD *)v35 + v22) = v25;
    if ( v23 < 0 )
    {
      v26 = -(__int16)v25;
      if ( v26 >= -32768 )
      {
        if ( v26 > 0x7FFF )
          LOWORD(v26) = 0x7FFF;
      }
      else
      {
        LOWORD(v26) = 0x8000;
      }
      *((_WORD *)v35 + v22) = v26;
    }
    if ( ++v22 != 9 )
      continue;
    break;
  }
  for ( n = 1; n != 9; ++n )
  {
    v29 = *((__int16 *)v35 + n) * A[n];
    if ( v29 >= 0x40000000 )
      v29 = 0x3FFFFFFF;
    v30 = B[n] + (__int16)((unsigned int)v29 >> 15);
    if ( v30 >= -32768 )
    {
      if ( v30 > 0x7FFF )
        LOWORD(v30) = 0x7FFF;
    }
    else
    {
      LOWORD(v30) = 0x8000;
    }
    v31 = (__int16)v30 + 256;
    if ( v31 >= -32768 )
    {
      if ( v31 > 0x7FFF )
        LOWORD(v31) = 0x7FFF;
    }
    else
    {
      LOWORD(v31) = 0x8000;
    }
    v32 = (__int16)v31 >> 9;
    if ( v32 > MAC[n] )
      v32 = MAC[n];
    if ( v32 < MIC[n] )
      v32 = MIC[n];
    v33 = v32 - MIC[n];
    if ( v33 >= -32768 )
    {
      if ( v33 <= 0x7FFF )
        result = (unsigned __int16)v33;
      else
        result = 0x7FFF;
    }
    else
    {
      result = 0x8000;
    }
    *(_WORD *)(a3 + 2 * n) = result;
  }
  return result;
}

```

## disassembly

```asm
0x1800041b4  mov     [rsp+arg_0], rbx
0x1800041b9  push    rbp
0x1800041ba  push    rsi
0x1800041bb  push    rdi
0x1800041bc  push    r12
0x1800041be  push    r13
0x1800041c0  push    r14
0x1800041c2  push    r15
0x1800041c4  sub     rsp, 70h
0x1800041c8  mov     rax, cs:__security_cookie
0x1800041cf  xor     rax, rsp
0x1800041d2  mov     [rsp+0A8h+var_48], rax
0x1800041d7  xor     ebp, ebp
0x1800041d9  mov     rsi, r8
0x1800041dc  mov     rbx, rdx
0x1800041df  mov     ecx, ebp
0x1800041e1  mov     r8d, ebp
0x1800041e4  mov     r15d, 0FFFF8000h
0x1800041ea  mov     r14d, 7FFFh
0x1800041f0  mov     r13d, 0A0h
0x1800041f6  lea     r12d, [rbp+1]
0x1800041fa  movzx   eax, word ptr [rdx+r8*2]
0x1800041ff  test    ax, ax
0x180004202  jns     short loc_180004212
0x180004204  cmp     ax, r15w
0x180004208  jnz     short loc_18000420F
0x18000420a  mov     eax, r14d
0x18000420d  jmp     short loc_180004212
0x18000420f  neg     ax
0x180004212  cmp     ax, cx
0x180004215  cmovg   cx, ax
0x180004219  add     r8, r12
0x18000421c  cmp     r8, r13
0x18000421f  jnz     short loc_1800041FA
0x180004221  mov     eax, 40000000h
0x180004226  test    cx, cx
0x180004229  jnz     short loc_180004233
0x18000422b  mov     r10d, ebp
0x18000422e  jmp     loc_1800042BB
0x180004233  movsx   ecx, cx
0x180004236  mov     edx, ebp
0x180004238  shl     ecx, 10h
0x18000423b  test    ecx, ecx
0x18000423d  jg      short loc_180004273
0x18000423f  lea     eax, [rcx+3FFFFFFFh]
0x180004245  cmp     eax, 3FFFFFFEh
0x18000424a  ja      short loc_180004259
0x18000424c  add     edx, r12d
0x18000424f  add     ecx, ecx
0x180004251  cmp     ecx, 0C0000000h
0x180004257  jg      short loc_18000424C
0x180004259  movsx   eax, dx
0x18000425c  mov     ecx, 4
0x180004261  sub     ecx, eax
0x180004263  cmp     ecx, r15d
0x180004266  jge     short loc_180004279
0x180004268  movzx   r10d, r15w
0x18000426c  jmp     short loc_1800042BB
0x18000426e  add     edx, r12d
0x180004271  add     ecx, ecx
0x180004273  cmp     ecx, eax
0x180004275  jl      short loc_18000426E
0x180004277  jmp     short loc_180004259
0x180004279  cmp     ecx, r14d
0x18000427c  jle     short loc_180004288
0x18000427e  movzx   ecx, r14w
0x180004282  movzx   r10d, r14w
0x180004286  jmp     short loc_180004291
0x180004288  movzx   r10d, cx
0x18000428c  test    cx, cx
0x18000428f  jle     short loc_1800042BB
0x180004291  movzx   eax, cx
0x180004294  mov     rdx, rbp
0x180004297  mov     ecx, 0Fh
0x18000429c  sub     ecx, eax
0x18000429e  movsx   eax, word ptr [rbx+rdx*2]
0x1800042a2  shl     eax, cl
0x1800042a4  lea     eax, ds:8000h[rax*2]
0x1800042ab  shr     rax, 10h
0x1800042af  mov     [rbx+rdx*2], ax
0x1800042b3  add     rdx, r12
0x1800042b6  cmp     rdx, r13
0x1800042b9  jnz     short loc_18000429E
0x1800042bb  mov     r9d, ebp
0x1800042be  mov     r8d, ebp
0x1800042c1  mov     edi, r9d
0x1800042c4  mov     r11d, r9d
0x1800042c7  mov     eax, r11d
0x1800042ca  sub     eax, r9d
0x1800042cd  movsx   edx, word ptr [rbx+rax*2]
0x1800042d1  mov     eax, r11d
0x1800042d4  movsx   ecx, word ptr [rbx+rax*2]
0x1800042d8  imul    edx, ecx
0x1800042db  add     edx, edx
0x1800042dd  lea     eax, [rdx+r8]
0x1800042e1  test    r8d, r8d
0x1800042e4  jns     short loc_1800042F6
0x1800042e6  test    edx, edx
0x1800042e8  jns     short loc_180004304
0x1800042ea  test    eax, eax
0x1800042ec  js      short loc_180004304
0x1800042ee  mov     r8d, 80000000h
0x1800042f4  jmp     short loc_180004307
0x1800042f6  test    edx, edx
0x1800042f8  js      short loc_180004304
0x1800042fa  mov     r8d, 7FFFFFFFh
0x180004300  test    eax, eax
0x180004302  js      short loc_180004307
0x180004304  mov     r8d, eax
0x180004307  add     r11d, r12d
0x18000430a  cmp     r11d, r13d
0x18000430d  jb      short loc_1800042C7
0x18000430f  add     r9d, r12d
0x180004312  mov     [rsp+rdi*4+0A8h+var_88], r8d
0x180004317  cmp     r9d, 9
0x18000431b  jb      short loc_1800042BE
0x18000431d  test    r10w, r10w
0x180004321  jle     short loc_180004345
0x180004323  movsx   eax, r10w
0x180004327  movd    xmm1, eax
0x18000432b  mov     rax, rbp
0x18000432e  movdqu  xmm0, xmmword ptr [rbx+rax*2]
0x180004333  psllw   xmm0, xmm1
0x180004337  movdqu  xmmword ptr [rbx+rax*2], xmm0
0x18000433c  add     rax, 8
0x180004340  cmp     rax, r13
0x180004343  jnz     short loc_18000432E
0x180004345  lea     r8, [rsp+0A8h+var_60]
0x18000434a  lea     rdx, [rsp+0A8h+var_88]
0x18000434f  call    Compr
0x180004354  mov     rdx, r12
0x180004357  movzx   ecx, [rsp+rdx*2+0A8h+var_60]
0x18000435c  test    cx, cx
0x18000435f  js      short loc_180004366
0x180004361  movzx   eax, cx
0x180004364  jmp     short loc_18000439D
0x180004366  cmp     cx, r15w
0x18000436a  jnz     short loc_180004397
0x18000436c  mov     eax, 19FFh
0x180004371  cmp     eax, r14d
0x180004374  jle     short loc_180004379
0x180004376  mov     eax, r14d
0x180004379  shl     ax, 2
0x18000437d  mov     word ptr [rsp+rdx*2+0A8h+var_88], ax
0x180004382  test    cx, cx
0x180004385  jns     short loc_1800043F9
0x180004387  movsx   ecx, ax
0x18000438a  neg     ecx
0x18000438c  cmp     ecx, r15d
0x18000438f  jge     short loc_1800043EC
0x180004391  movzx   ecx, r15w
0x180004395  jmp     short loc_1800043F4
0x180004397  movzx   eax, cx
0x18000439a  neg     ax
0x18000439d  mov     r8d, 5666h
0x1800043a3  cmp     ax, r8w
0x1800043a7  jge     short loc_1800043AE
0x1800043a9  sar     ax, 1
0x1800043ac  jmp     short loc_18000437D
0x1800043ae  mov     r9d, 799Ah
0x1800043b4  movsx   r8d, ax
0x1800043b8  cmp     ax, r9w
0x1800043bc  jge     short loc_1800043DA
0x1800043be  lea     eax, [r8-2B33h]
0x1800043c5  cmp     eax, r15d
0x1800043c8  jge     short loc_1800043CF
0x1800043ca  mov     eax, r15d
0x1800043cd  jmp     short loc_18000437D
0x1800043cf  cmp     eax, r14d
0x1800043d2  jle     short loc_18000437D
0x1800043d4  movzx   eax, r14w
0x1800043d8  jmp     short loc_18000437D
0x1800043da  lea     eax, [r8-6600h]
0x1800043e1  cmp     eax, r15d
0x1800043e4  jge     short loc_180004371
0x1800043e6  movzx   eax, r15w
0x1800043ea  jmp     short loc_180004379
0x1800043ec  cmp     ecx, r14d
0x1800043ef  jle     short loc_1800043F4
0x1800043f1  mov     ecx, r14d
0x1800043f4  mov     word ptr [rsp+rdx*2+0A8h+var_88], cx
0x1800043f9  add     rdx, r12
0x1800043fc  cmp     rdx, 9
0x180004400  jnz     loc_180004357
0x180004406  mov     r8, r12
0x180004409  lea     r9, __ImageBase
0x180004410  movsx   eax, word ptr [rsp+r8*2+0A8h+var_88]
0x180004416  movsx   edx, ds:rva A[r9+r8*2]
0x18000441f  movsx   ecx, ds:rva B[r9+r8*2]
0x180004428  imul    edx, eax
0x18000442b  mov     eax, 3FFFFFFFh
0x180004430  cmp     edx, 40000000h
0x180004436  cmovge  edx, eax
0x180004439  shr     edx, 0Fh
0x18000443c  movsx   eax, dx
0x18000443f  add     eax, ecx
0x180004441  cmp     eax, r15d
0x180004444  jge     short loc_18000444C
0x180004446  movzx   eax, r15w
0x18000444a  jmp     short loc_180004454
0x18000444c  cmp     eax, r14d
0x18000444f  jle     short loc_180004454
0x180004451  mov     eax, r14d
0x180004454  movsx   ecx, ax
0x180004457  add     ecx, 100h
0x18000445d  cmp     ecx, r15d
0x180004460  jge     short loc_180004468
0x180004462  movzx   ecx, r15w
0x180004466  jmp     short loc_180004470
0x180004468  cmp     ecx, r14d
0x18000446b  jle     short loc_180004470
0x18000446d  mov     ecx, r14d
0x180004470  movzx   eax, ds:rva MAC[r9+r8*2]
0x180004479  sar     cx, 9
0x18000447d  cmp     cx, ax
0x180004480  cmovg   cx, ax
0x180004484  movsx   eax, ds:rva MIC[r9+r8*2]
0x18000448d  cmp     cx, ax
0x180004490  cmovl   cx, ax
0x180004494  movsx   edx, cx
0x180004497  sub     edx, eax
0x180004499  cmp     edx, r15d
0x18000449c  jge     short loc_1800044A4
0x18000449e  movzx   eax, r15w
0x1800044a2  jmp     short loc_1800044B1
0x1800044a4  cmp     edx, r14d
0x1800044a7  jle     short loc_1800044AE
0x1800044a9  mov     eax, r14d
0x1800044ac  jmp     short loc_1800044B1
0x1800044ae  movzx   eax, dx
0x1800044b1  mov     [rsi+r8*2], ax
0x1800044b6  add     r8, r12
0x1800044b9  cmp     r8, 9
0x1800044bd  jnz     loc_180004410
0x1800044c3  mov     rcx, [rsp+0A8h+var_48]
0x1800044c8  xor     rcx, rsp; StackCookie
0x1800044cb  call    __security_check_cookie
0x1800044d0  mov     rbx, [rsp+0A8h+arg_0]
0x1800044d8  add     rsp, 70h
0x1800044dc  pop     r15
0x1800044de  pop     r14
0x1800044e0  pop     r13
0x1800044e2  pop     r12
0x1800044e4  pop     rdi
0x1800044e5  pop     rsi
0x1800044e6  pop     rbp
0x1800044e7  retn
```
