# MCHandleKeydown

- ea: `0x180043970`
- end: `0x180043cc0`
- name: `MCHandleKeydown`
- size: `848`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180046d90`

## callees

- `0x1800115f0`
- `0x1800423c8`
- `0x180043970`
- `0x180043cc8`
- `0x180046348`
- `0x180072058`
- `0x18007222c`
- `0x1800724e0`

## import_xrefs

- `USER32!GetDC` at `0x180043be6`
- `USER32!GetDC` at `0x180043c7e`
- `USER32!GetDC` at `0x180043be6`
- `USER32!GetDC` at `0x180043c7e`
- `USER32!ReleaseDC` at `0x180043c01`
- `USER32!ReleaseDC` at `0x180043c99`
- `USER32!ReleaseDC` at `0x180043c01`
- `USER32!ReleaseDC` at `0x180043c99`
- `USER32!InvalidateRect` at `0x180043c48`
- `USER32!InvalidateRect` at `0x180043c57`
- `USER32!InvalidateRect` at `0x180043c48`
- `USER32!InvalidateRect` at `0x180043c57`
- `USER32!UpdateWindow` at `0x180043c60`
- `USER32!UpdateWindow` at `0x180043c60`
- `USER32!DrawFocusRect` at `0x180043bf5`
- `USER32!DrawFocusRect` at `0x180043c8d`
- `USER32!DrawFocusRect` at `0x180043bf5`
- `USER32!DrawFocusRect` at `0x180043c8d`

## pseudocode

```c
__int64 __fastcall MCHandleKeydown(__int64 a1, unsigned __int64 a2)
{
  __int128 v3; // xmm6
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rdx
  __int16 v8; // r11
  unsigned __int16 v9; // bx
  __int16 DaysForMonth; // r8
  unsigned __int16 v11; // r11
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  __int16 v18; // ax
  unsigned int v19; // eax
  __int128 *v20; // rsi
  __int128 *v21; // r15
  HDC DC; // rbx
  int v23; // r14d
  __int128 v24; // xmm0
  HWND v25; // rcx
  HDC v26; // rbx
  __int128 v27; // [rsp+20h] [rbp-38h] BYREF

  v3 = 0;
  v27 = 0;
  if ( a2 > 0x24 )
  {
    v15 = a2 - 37;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( !v16 )
      {
        v12 = 0xFFFFFFFFLL;
LABEL_29:
        v13 = 4;
        goto LABEL_32;
      }
      v17 = v16 - 1;
      if ( v17 )
      {
        if ( v17 != 1 )
          return 0;
        v12 = 1;
        goto LABEL_29;
      }
      v12 = 1;
    }
    else
    {
      v12 = 0xFFFFFFFFLL;
    }
    v13 = 8;
    goto LABEL_32;
  }
  if ( a2 == 36 )
  {
    if ( *(_DWORD *)(a1 + 2348) )
    {
      v8 = *(_WORD *)(a1 + 1932);
      v9 = *(_WORD *)(a1 + 1934);
      DaysForMonth = *(_WORD *)(a1 + 1938);
    }
    else
    {
      v8 = *(_WORD *)(a1 + 1820);
      DaysForMonth = 1;
      v9 = *(_WORD *)(a1 + 1822);
    }
LABEL_20:
    LOWORD(v27) = v8;
    WORD1(v27) = v9;
    WORD3(v27) = DaysForMonth;
    goto LABEL_36;
  }
  v4 = a2 - 16;
  if ( !v4 )
  {
    *(_DWORD *)(a1 + 2352) = 1;
    return 1;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    *(_DWORD *)(a1 + 2348) = 1;
    return 1;
  }
  v6 = v5 - 16;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        if ( !*(_DWORD *)(a1 + 2348) )
        {
          v9 = *(_WORD *)(a1 + 1822);
          v11 = *(_WORD *)(a1 + 1820);
          LOWORD(v27) = v11;
          WORD1(v27) = v9;
          DaysForMonth = GetDaysForMonth(v11, v9);
          WORD3(v27) = DaysForMonth;
          goto LABEL_36;
        }
        v8 = *(_WORD *)(a1 + 1948);
        v9 = *(_WORD *)(a1 + 1950);
        DaysForMonth = *(_WORD *)(a1 + 1954);
        goto LABEL_20;
      }
      return 0;
    }
    v12 = 1;
  }
  else
  {
    v12 = 0xFFFFFFFFLL;
  }
  v13 = 2 - (unsigned int)(*(_DWORD *)(a1 + 2348) != 0);
LABEL_32:
  if ( (*(_DWORD *)(a1 + 2392) & 0x180) == 0x180 )
  {
    LODWORD(v27) = *(_DWORD *)(a1 + 1836);
    v18 = *(_WORD *)(a1 + 1842);
  }
  else
  {
    LODWORD(v27) = *(_DWORD *)(a1 + 1820);
    v18 = *(_WORD *)(a1 + 1826);
  }
  WORD3(v27) = v18;
  IncrSystemTime(&v27, &v27, v12, v13);
  DaysForMonth = WORD3(v27);
  v8 = v27;
  v9 = WORD1(v27);
LABEL_36:
  if ( (*(_BYTE *)(a1 + 16) & 2) != 0 && *(_DWORD *)(a1 + 2352) )
  {
    v19 = CmpDate(a1 + 1820, a1 + 1884);
    *(_DWORD *)(a1 + 2392) &= ~0x100u;
    *(_DWORD *)(a1 + 2392) |= ~(v19 >> 23) & 0x100 | 0x80;
  }
  else
  {
    *(_DWORD *)(a1 + 2392) &= ~0x80u;
    *(_WORD *)(a1 + 1884) = v8;
    *(_WORD *)(a1 + 1886) = v9;
    *(_WORD *)(a1 + 1890) = DaysForMonth;
  }
  v20 = (__int128 *)(a1 + 2100);
  v21 = (__int128 *)(a1 + 2116);
  if ( (*(_DWORD *)(a1 + 2392) & 0x10) != 0 )
  {
    DC = GetDC(*(HWND *)a1);
    DrawFocusRect(DC, (const RECT *)(a1 + 2100));
    ReleaseDC(*(HWND *)a1, DC);
    v3 = *v20;
  }
  else
  {
    *v21 = *v20;
  }
  if ( (*(_BYTE *)(a1 + 16) & 2) != 0 )
  {
    v23 = 0;
    MCHandleMultiSelect(a1, (__int16 *)&v27);
    FScrollIntoView(a1);
  }
  else
  {
    v23 = MCSetDate(a1, &v27);
    if ( v23 )
    {
      InvalidateRect(*(HWND *)a1, (const RECT *)(a1 + 2116), 0);
      InvalidateRect(*(HWND *)a1, (const RECT *)(a1 + 2100), 0);
      UpdateWindow(*(HWND *)a1);
    }
  }
  if ( (*(_BYTE *)(a1 + 2392) & 0x10) != 0 )
  {
    v24 = *v20;
    v25 = *(HWND *)a1;
    *v20 = v3;
    *v21 = v24;
    v26 = GetDC(v25);
    DrawFocusRect(v26, (const RECT *)(a1 + 2100));
    ReleaseDC(*(HWND *)a1, v26);
  }
  return v23;
}

```

## disassembly

```asm
0x180043970  push    rbp
0x180043972  push    rbx
0x180043973  push    rsi
0x180043974  push    rdi
0x180043975  push    r14
0x180043977  push    r15
0x180043979  mov     rbp, rsp
0x18004397c  sub     rsp, 58h
0x180043980  movaps  [rsp+58h+var_18], xmm6
0x180043985  mov     rax, cs:__security_cookie
0x18004398c  xor     rax, rsp
0x18004398f  mov     [rbp+var_28], rax
0x180043993  xorps   xmm0, xmm0
0x180043996  mov     rdi, rcx
0x180043999  xorps   xmm6, xmm6
0x18004399c  movups  [rbp+var_38], xmm0
0x1800439a0  cmp     rdx, 24h ; '$'
0x1800439a4  ja      loc_180043ABB
0x1800439aa  jz      loc_180043A71
0x1800439b0  sub     rdx, 10h
0x1800439b4  jz      loc_180043A62
0x1800439ba  sub     rdx, 1
0x1800439be  jz      loc_180043A4D
0x1800439c4  sub     rdx, 10h
0x1800439c8  jz      short loc_180043A47
0x1800439ca  sub     rdx, 1
0x1800439ce  jz      short loc_180043A2D
0x1800439d0  cmp     rdx, 1
0x1800439d4  jnz     loc_180043AD3
0x1800439da  cmp     dword ptr [rcx+92Ch], 0
0x1800439e1  jz      short loc_1800439FF
0x1800439e3  movzx   r11d, word ptr [rcx+79Ch]
0x1800439eb  movzx   ebx, word ptr [rcx+79Eh]
0x1800439f2  movzx   r8d, word ptr [rcx+7A2h]
0x1800439fa  jmp     loc_180043AA8
0x1800439ff  movzx   ebx, word ptr [rcx+71Eh]
0x180043a06  movzx   r11d, word ptr [rcx+71Ch]
0x180043a0e  mov     edx, ebx
0x180043a10  mov     ecx, r11d
0x180043a13  mov     word ptr [rbp+var_38], r11w
0x180043a18  mov     word ptr [rbp+var_38+2], bx
0x180043a1c  call    GetDaysForMonth
0x180043a21  mov     r8d, eax
0x180043a24  mov     word ptr [rbp+var_38+6], ax
0x180043a28  jmp     loc_180043B6C
0x180043a2d  mov     r8d, 1
0x180043a33  mov     eax, [rcx+92Ch]
0x180043a39  neg     eax
0x180043a3b  sbb     r9d, r9d
0x180043a3e  add     r9d, 2
0x180043a42  jmp     loc_180043B00
0x180043a47  or      r8d, 0FFFFFFFFh
0x180043a4b  jmp     short loc_180043A33
0x180043a4d  mov     r8d, 1
0x180043a53  mov     [rcx+92Ch], r8d
0x180043a5a  mov     rax, r8
0x180043a5d  jmp     loc_180043CA2
0x180043a62  mov     r8d, 1
0x180043a68  mov     [rcx+930h], r8d
0x180043a6f  jmp     short loc_180043A5A
0x180043a71  cmp     dword ptr [rcx+92Ch], 0
0x180043a78  jz      short loc_180043A93
0x180043a7a  movzx   r11d, word ptr [rcx+78Ch]
0x180043a82  movzx   ebx, word ptr [rcx+78Eh]
0x180043a89  movzx   r8d, word ptr [rcx+792h]
0x180043a91  jmp     short loc_180043AA8
0x180043a93  movzx   r11d, word ptr [rcx+71Ch]
0x180043a9b  mov     r8d, 1
0x180043aa1  movzx   ebx, word ptr [rcx+71Eh]
0x180043aa8  mov     word ptr [rbp+var_38], r11w
0x180043aad  mov     word ptr [rbp+var_38+2], bx
0x180043ab1  mov     word ptr [rbp+var_38+6], r8w
0x180043ab6  jmp     loc_180043B6C
0x180043abb  sub     rdx, 25h ; '%'
0x180043abf  jz      short loc_180043AF6
0x180043ac1  sub     rdx, 1
0x180043ac5  jz      short loc_180043AEA
0x180043ac7  sub     rdx, 1
0x180043acb  jz      short loc_180043AE2
0x180043acd  cmp     rdx, 1
0x180043ad1  jz      short loc_180043ADA
0x180043ad3  xor     eax, eax
0x180043ad5  jmp     loc_180043CA2
0x180043ada  mov     r8d, 1
0x180043ae0  jmp     short loc_180043AEE
0x180043ae2  mov     r8d, 1
0x180043ae8  jmp     short loc_180043AFA
0x180043aea  or      r8d, 0FFFFFFFFh
0x180043aee  mov     r9d, 4
0x180043af4  jmp     short loc_180043B00
0x180043af6  or      r8d, 0FFFFFFFFh
0x180043afa  mov     r9d, 8
0x180043b00  mov     eax, [rcx+958h]
0x180043b06  mov     ecx, 180h
0x180043b0b  and     eax, ecx
0x180043b0d  cmp     eax, ecx
0x180043b0f  jnz     short loc_180043B30
0x180043b11  movzx   eax, word ptr [rdi+72Ch]
0x180043b18  mov     word ptr [rbp+var_38], ax
0x180043b1c  movzx   eax, word ptr [rdi+72Eh]
0x180043b23  mov     word ptr [rbp+var_38+2], ax
0x180043b27  movzx   eax, word ptr [rdi+732h]
0x180043b2e  jmp     short loc_180043B4D
0x180043b30  movzx   eax, word ptr [rdi+71Ch]
0x180043b37  mov     word ptr [rbp+var_38], ax
0x180043b3b  movzx   eax, word ptr [rdi+71Eh]
0x180043b42  mov     word ptr [rbp+var_38+2], ax
0x180043b46  movzx   eax, word ptr [rdi+722h]
0x180043b4d  lea     rdx, [rbp+var_38]
0x180043b51  mov     word ptr [rbp+var_38+6], ax
0x180043b55  lea     rcx, [rbp+var_38]
0x180043b59  call    IncrSystemTime
0x180043b5e  movzx   r8d, word ptr [rbp+var_38+6]
0x180043b63  movzx   r11d, word ptr [rbp+var_38]
0x180043b68  movzx   ebx, word ptr [rbp+var_38+2]
0x180043b6c  test    byte ptr [rdi+10h], 2
0x180043b70  jz      short loc_180043BAC
0x180043b72  cmp     dword ptr [rdi+930h], 0
0x180043b79  jz      short loc_180043BAC
0x180043b7b  lea     rdx, [rdi+75Ch]
0x180043b82  lea     rcx, [rdi+71Ch]
0x180043b89  call    CmpDate
0x180043b8e  btr     dword ptr [rdi+958h], 8
0x180043b96  shr     eax, 17h
0x180043b99  not     eax
0x180043b9b  and     eax, 100h
0x180043ba0  bts     eax, 7
0x180043ba4  or      [rdi+958h], eax
0x180043baa  jmp     short loc_180043BCB
0x180043bac  btr     dword ptr [rdi+958h], 7
0x180043bb4  mov     [rdi+75Ch], r11w
0x180043bbc  mov     [rdi+75Eh], bx
0x180043bc3  mov     [rdi+762h], r8w
0x180043bcb  mov     eax, [rdi+958h]
0x180043bd1  lea     rsi, [rdi+834h]
0x180043bd8  lea     r15, [rdi+844h]
0x180043bdf  test    al, 10h
0x180043be1  jz      short loc_180043C0C
0x180043be3  mov     rcx, [rdi]; hWnd
0x180043be6  call    cs:__imp_GetDC
0x180043bec  mov     rcx, rax; hDC
0x180043bef  mov     rdx, rsi; lprc
0x180043bf2  mov     rbx, rax
0x180043bf5  call    cs:__imp_DrawFocusRect
0x180043bfb  mov     rcx, [rdi]; hWnd
0x180043bfe  mov     rdx, rbx; hDC
0x180043c01  call    cs:__imp_ReleaseDC
0x180043c07  movups  xmm6, xmmword ptr [rsi]
0x180043c0a  jmp     short loc_180043C14
0x180043c0c  movups  xmm0, xmmword ptr [rsi]
0x180043c0f  movdqu  xmmword ptr [r15], xmm0
0x180043c14  test    byte ptr [rdi+10h], 2
0x180043c18  lea     rdx, [rbp+var_38]
0x180043c1c  mov     rcx, rdi
0x180043c1f  jz      short loc_180043C33
0x180043c21  xor     r14d, r14d
0x180043c24  call    MCHandleMultiSelect
0x180043c29  mov     rcx, rdi
0x180043c2c  call    FScrollIntoView
0x180043c31  jmp     short loc_180043C66
0x180043c33  call    MCSetDate
0x180043c38  mov     r14d, eax
0x180043c3b  test    eax, eax
0x180043c3d  jz      short loc_180043C66
0x180043c3f  mov     rcx, [rdi]; hWnd
0x180043c42  xor     r8d, r8d; bErase
0x180043c45  mov     rdx, r15; lpRect
0x180043c48  call    cs:__imp_InvalidateRect
0x180043c4e  mov     rcx, [rdi]; hWnd
0x180043c51  xor     r8d, r8d; bErase
0x180043c54  mov     rdx, rsi; lpRect
0x180043c57  call    cs:__imp_InvalidateRect
0x180043c5d  mov     rcx, [rdi]; hWnd
0x180043c60  call    cs:__imp_UpdateWindow
0x180043c66  test    byte ptr [rdi+958h], 10h
0x180043c6d  jz      short loc_180043C9F
0x180043c6f  movups  xmm0, xmmword ptr [rsi]
0x180043c72  mov     rcx, [rdi]; hWnd
0x180043c75  movdqu  xmmword ptr [rsi], xmm6
0x180043c79  movdqu  xmmword ptr [r15], xmm0
0x180043c7e  call    cs:__imp_GetDC
0x180043c84  mov     rcx, rax; hDC
0x180043c87  mov     rdx, rsi; lprc
0x180043c8a  mov     rbx, rax
0x180043c8d  call    cs:__imp_DrawFocusRect
0x180043c93  mov     rcx, [rdi]; hWnd
0x180043c96  mov     rdx, rbx; hDC
0x180043c99  call    cs:__imp_ReleaseDC
0x180043c9f  movsxd  rax, r14d
0x180043ca2  mov     rcx, [rbp+var_28]
0x180043ca6  xor     rcx, rsp; StackCookie
0x180043ca9  call    __security_check_cookie
0x180043cae  movaps  xmm6, [rsp+58h+var_18]
0x180043cb3  add     rsp, 58h
0x180043cb7  pop     r15
0x180043cb9  pop     r14
0x180043cbb  pop     rdi
0x180043cbc  pop     rsi
0x180043cbd  pop     rbx
0x180043cbe  pop     rbp
0x180043cbf  retn
```
