# PreviewSize

- ea: `0x18000f41c`
- end: `0x18000f6fd`
- name: `PreviewSize`
- size: `737`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f0b8`

## callees

- `0x1800014b0`
- `0x18000f41c`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000f581`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000f5c8`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000f581`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000f5c8`
- `GDI32!SelectObject` at `0x18000f4b0`
- `GDI32!SelectObject` at `0x18000f4b0`
- `USER32!SetWindowPos` at `0x18000f6c3`
- `USER32!SetWindowPos` at `0x18000f6c3`
- `USER32!SendMessageW` at `0x18000f507`
- `USER32!SendMessageW` at `0x18000f535`
- `USER32!SendMessageW` at `0x18000f507`
- `USER32!SendMessageW` at `0x18000f535`
- `USER32!ShowWindow` at `0x18000f6d2`
- `USER32!ShowWindow` at `0x18000f6d2`
- `USER32!GetDC` at `0x18000f4a0`
- `USER32!GetDC` at `0x18000f4a0`
- `USER32!ReleaseDC` at `0x18000f4e9`
- `USER32!ReleaseDC` at `0x18000f4e9`
- `USER32!GetWindowRect` at `0x18000f515`
- `USER32!GetWindowRect` at `0x18000f543`
- `USER32!GetWindowRect` at `0x18000f515`
- `USER32!GetWindowRect` at `0x18000f543`
- `USER32!DrawTextW` at `0x18000f4dc`
- `USER32!DrawTextW` at `0x18000f4dc`
- `USER32!SetRectEmpty` at `0x18000f45c`
- `USER32!SetRectEmpty` at `0x18000f466`
- `USER32!SetRectEmpty` at `0x18000f45c`
- `USER32!SetRectEmpty` at `0x18000f466`
- `USER32!OffsetRect` at `0x18000f5fe`
- `USER32!OffsetRect` at `0x18000f61b`
- `USER32!OffsetRect` at `0x18000f648`
- `USER32!OffsetRect` at `0x18000f662`
- `USER32!OffsetRect` at `0x18000f5fe`
- `USER32!OffsetRect` at `0x18000f61b`
- `USER32!OffsetRect` at `0x18000f648`
- `USER32!OffsetRect` at `0x18000f662`

## pseudocode

```c
__int64 __fastcall PreviewSize(__int64 a1)
{
  __int64 result; // rax
  LONG v3; // r13d
  int v4; // r15d
  LONG v5; // r14d
  LONG v6; // r12d
  HDC DC; // rbx
  int v8; // ebx
  int v9; // esi
  int v10; // eax
  int v11; // r15d
  int v12; // r13d
  LONG top; // r8d
  int v14; // eax
  LONG bottom; // ecx
  LONG v16; // eax
  int v17; // edx
  int v18; // eax
  int v19; // ebx
  struct tagRECT v20; // xmm2
  int v21; // r8d
  int v22; // ecx
  struct tagRECT v23; // xmm1
  int v24; // r9d
  LONG v25; // [rsp+40h] [rbp-29h]
  int v26; // [rsp+44h] [rbp-25h]
  struct tagRECT v27; // [rsp+48h] [rbp-21h] BYREF
  struct tagRECT rc; // [rsp+58h] [rbp-11h] BYREF
  struct tagRECT Rect; // [rsp+68h] [rbp-1h] BYREF

  Rect = 0;
  v27 = 0;
  rc = 0;
  SetRectEmpty((LPRECT)(a1 + 80));
  SetRectEmpty((LPRECT)(a1 + 64));
  result = 0;
  if ( *(_WORD *)(a1 + 128) || *(_QWORD *)(a1 + 120) )
  {
    v3 = *(_DWORD *)(a1 + 56);
    v4 = *(_DWORD *)(a1 + 60);
    v5 = *(_DWORD *)(a1 + 48);
    v6 = *(_DWORD *)(a1 + 52);
    v25 = v3;
    v26 = v4;
    DC = GetDC(*(HWND *)(a1 + 8));
    SelectObject(DC, *(HGDIOBJ *)(a1 + 104));
    rc.left = v5;
    rc.top = v6;
    rc.right = v3;
    rc.bottom = v6;
    DrawTextW(DC, (LPCWSTR)(a1 + 128), -1, &rc, 0x410u);
    ReleaseDC(*(HWND *)(a1 + 8), DC);
    SendMessageW(*(HWND *)(a1 + 96), 0x487u, 2u, 2);
    GetWindowRect(*(HWND *)(a1 + 96), &Rect);
    v8 = Rect.right - Rect.left;
    v9 = Rect.bottom - Rect.top;
    SendMessageW(*(HWND *)(a1 + 96), 0x487u, 2u, 0);
    GetWindowRect(*(HWND *)(a1 + 96), &Rect);
    v10 = v4;
    v11 = v3 - v5;
    v12 = Rect.bottom - Rect.top - v9;
    v27.left = v5;
    v27.top = v6;
    v27.right = v25;
    top = v6;
    v27.bottom = v10 - v12;
    if ( v8 <= v25 - v5 )
    {
      if ( 2 * v8 >= v11 )
      {
        v16 = v5 + v8;
        bottom = v6 + v9;
      }
      else
      {
        v16 = v5 + 2 * v8;
        bottom = v6 + 2 * v9;
      }
      v27.right = v16;
    }
    else
    {
      v14 = MulDiv(v9, v11, v8);
      top = v27.top;
      bottom = v27.top + v14;
    }
    v17 = rc.top + v26 - v12 - rc.bottom;
    if ( bottom > v17 )
    {
      v27.bottom = rc.top + v26 - v12 - rc.bottom;
      v18 = MulDiv(v8, v17 - top, v9);
      bottom = v27.bottom;
      v27.right = v5 + v18;
      v27.left = v5;
    }
    v27.bottom = v12 + bottom;
    OffsetRect(&rc, (rc.left + v25 - v5 - rc.right) / 2, 0);
    OffsetRect(&v27, (v27.left + v11 - v27.right) / 2, 0);
    v19 = 0;
    if ( rc.top + v27.top + v26 - v6 - v27.bottom - rc.bottom >= 0 )
      v19 = (rc.top + v27.top + v26 - v6 - v27.bottom - rc.bottom) / 2;
    OffsetRect(&v27, 0, v19);
    OffsetRect(&rc, 0, v19 - v27.top + v27.bottom + 2);
    v20 = v27;
    v21 = _mm_cvtsi128_si32((__m128i)v27);
    v22 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v27, 12));
    v23 = v27;
    *(struct tagRECT *)(a1 + 80) = rc;
    v24 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v23, 4));
    *(struct tagRECT *)(a1 + 64) = v20;
    SetWindowPos(
      *(HWND *)(a1 + 96),
      0,
      v21,
      v24,
      _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v23, 8)) - v21,
      v22 - v24,
      0x14u);
    ShowWindow(*(HWND *)(a1 + 96), 5);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000f41c  push    rbp
0x18000f41e  push    rbx
0x18000f41f  push    rsi
0x18000f420  push    rdi
0x18000f421  push    r12
0x18000f423  push    r13
0x18000f425  push    r14
0x18000f427  push    r15
0x18000f429  lea     rbp, [rsp-1Fh]
0x18000f42e  sub     rsp, 88h
0x18000f435  mov     rax, cs:__security_cookie
0x18000f43c  xor     rax, rsp
0x18000f43f  mov     [rbp+57h+var_48], rax
0x18000f443  xorps   xmm0, xmm0
0x18000f446  mov     rdi, rcx
0x18000f449  xorps   xmm1, xmm1
0x18000f44c  add     rcx, 50h ; 'P'; lprc
0x18000f450  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18000f454  movups  xmmword ptr [rbp+57h+var_78.left], xmm1
0x18000f458  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18000f45c  call    cs:__imp_SetRectEmpty
0x18000f462  lea     rcx, [rdi+40h]; lprc
0x18000f466  call    cs:__imp_SetRectEmpty
0x18000f46c  xor     eax, eax
0x18000f46e  lea     rsi, [rdi+80h]
0x18000f475  cmp     [rsi], ax
0x18000f478  jnz     short loc_18000F484
0x18000f47a  cmp     [rdi+78h], rax
0x18000f47e  jz      loc_18000F6DD
0x18000f484  mov     r13d, [rdi+38h]
0x18000f488  mov     r15d, [rdi+3Ch]
0x18000f48c  mov     rcx, [rdi+8]; hWnd
0x18000f490  mov     r14d, [rdi+30h]
0x18000f494  mov     r12d, [rdi+34h]
0x18000f498  mov     [rbp+57h+var_80], r13d
0x18000f49c  mov     [rbp+57h+var_7C], r15d
0x18000f4a0  call    cs:__imp_GetDC
0x18000f4a6  mov     rdx, [rdi+68h]; h
0x18000f4aa  mov     rcx, rax; hdc
0x18000f4ad  mov     rbx, rax
0x18000f4b0  call    cs:__imp_SelectObject
0x18000f4b6  lea     r9, [rbp+57h+rc]; lprc
0x18000f4ba  mov     [rbp+57h+rc.left], r14d
0x18000f4be  or      r8d, 0FFFFFFFFh; cchText
0x18000f4c2  mov     [rbp+57h+rc.top], r12d
0x18000f4c6  mov     rdx, rsi; lpchText
0x18000f4c9  mov     [rbp+57h+rc.right], r13d
0x18000f4cd  mov     rcx, rbx; hdc
0x18000f4d0  mov     [rbp+57h+rc.bottom], r12d
0x18000f4d4  mov     [rsp+0C0h+format], 410h; format
0x18000f4dc  call    cs:__imp_DrawTextW
0x18000f4e2  mov     rcx, [rdi+8]; hWnd
0x18000f4e6  mov     rdx, rbx; hDC
0x18000f4e9  call    cs:__imp_ReleaseDC
0x18000f4ef  mov     rcx, [rdi+60h]; hWnd
0x18000f4f3  mov     eax, 2
0x18000f4f8  mov     r13d, 487h
0x18000f4fe  mov     r9d, eax; lParam
0x18000f501  mov     r8d, eax; wParam
0x18000f504  mov     edx, r13d; Msg
0x18000f507  call    cs:__imp_SendMessageW
0x18000f50d  mov     rcx, [rdi+60h]; hWnd
0x18000f511  lea     rdx, [rbp+57h+Rect]; lpRect
0x18000f515  call    cs:__imp_GetWindowRect
0x18000f51b  mov     ebx, [rbp+57h+Rect.right]
0x18000f51e  xor     r9d, r9d; lParam
0x18000f521  mov     esi, [rbp+57h+Rect.bottom]
0x18000f524  mov     edx, r13d; Msg
0x18000f527  mov     rcx, [rdi+60h]; hWnd
0x18000f52b  sub     ebx, [rbp+57h+Rect.left]
0x18000f52e  sub     esi, [rbp+57h+Rect.top]
0x18000f531  lea     r8d, [r9+2]; wParam
0x18000f535  call    cs:__imp_SendMessageW
0x18000f53b  mov     rcx, [rdi+60h]; hWnd
0x18000f53f  lea     rdx, [rbp+57h+Rect]; lpRect
0x18000f543  call    cs:__imp_GetWindowRect
0x18000f549  mov     ecx, [rbp+57h+var_80]
0x18000f54c  mov     eax, r15d
0x18000f54f  mov     r13d, [rbp+57h+Rect.bottom]
0x18000f553  mov     r15d, ecx
0x18000f556  sub     r13d, [rbp+57h+Rect.top]
0x18000f55a  sub     r15d, r14d
0x18000f55d  sub     r13d, esi
0x18000f560  mov     [rbp+57h+var_78.left], r14d
0x18000f564  sub     eax, r13d
0x18000f567  mov     [rbp+57h+var_78.top], r12d
0x18000f56b  mov     [rbp+57h+var_78.right], ecx
0x18000f56e  mov     r8d, r12d
0x18000f571  mov     [rbp+57h+var_78.bottom], eax
0x18000f574  cmp     ebx, r15d
0x18000f577  jle     short loc_18000F591
0x18000f579  mov     r8d, ebx; nDenominator
0x18000f57c  mov     edx, r15d; nNumerator
0x18000f57f  mov     ecx, esi; nNumber
0x18000f581  call    cs:__imp_MulDiv
0x18000f587  mov     r8d, [rbp+57h+var_78.top]
0x18000f58b  lea     ecx, [r8+rax]
0x18000f58f  jmp     short loc_18000F5AD
0x18000f591  lea     eax, [rbx+rbx]
0x18000f594  cmp     eax, r15d
0x18000f597  jge     short loc_18000F5A2
0x18000f599  add     eax, r14d
0x18000f59c  lea     ecx, [r12+rsi*2]
0x18000f5a0  jmp     short loc_18000F5AA
0x18000f5a2  lea     eax, [r14+rbx]
0x18000f5a6  lea     ecx, [r12+rsi]
0x18000f5aa  mov     [rbp+57h+var_78.right], eax
0x18000f5ad  mov     edx, [rbp+57h+var_7C]
0x18000f5b0  sub     edx, r13d
0x18000f5b3  sub     edx, [rbp+57h+rc.bottom]
0x18000f5b6  add     edx, [rbp+57h+rc.top]
0x18000f5b9  cmp     ecx, edx
0x18000f5bb  jle     short loc_18000F5DB
0x18000f5bd  mov     [rbp+57h+var_78.bottom], edx
0x18000f5c0  mov     ecx, ebx; nNumber
0x18000f5c2  sub     edx, r8d; nNumerator
0x18000f5c5  mov     r8d, esi; nDenominator
0x18000f5c8  call    cs:__imp_MulDiv
0x18000f5ce  mov     ecx, [rbp+57h+var_78.bottom]
0x18000f5d1  add     eax, r14d
0x18000f5d4  mov     [rbp+57h+var_78.right], eax
0x18000f5d7  mov     [rbp+57h+var_78.left], r14d
0x18000f5db  mov     eax, [rbp+57h+var_80]
0x18000f5de  add     ecx, r13d
0x18000f5e1  sub     eax, r14d
0x18000f5e4  mov     [rbp+57h+var_78.bottom], ecx
0x18000f5e7  sub     eax, [rbp+57h+rc.right]
0x18000f5ea  lea     rcx, [rbp+57h+rc]; lprc
0x18000f5ee  add     eax, [rbp+57h+rc.left]
0x18000f5f1  mov     ebx, 2
0x18000f5f6  cdq
0x18000f5f7  xor     r8d, r8d; dy
0x18000f5fa  idiv    ebx
0x18000f5fc  mov     edx, eax; dx
0x18000f5fe  call    cs:__imp_OffsetRect
0x18000f604  sub     r15d, [rbp+57h+var_78.right]
0x18000f608  lea     rcx, [rbp+57h+var_78]; lprc
0x18000f60c  add     r15d, [rbp+57h+var_78.left]
0x18000f610  xor     r8d, r8d; dy
0x18000f613  mov     eax, r15d
0x18000f616  cdq
0x18000f617  idiv    ebx
0x18000f619  mov     edx, eax; dx
0x18000f61b  call    cs:__imp_OffsetRect
0x18000f621  mov     ecx, [rbp+57h+var_7C]
0x18000f624  sub     ecx, r12d
0x18000f627  sub     ecx, [rbp+57h+var_78.bottom]
0x18000f62a  sub     ecx, [rbp+57h+rc.bottom]
0x18000f62d  add     ecx, [rbp+57h+var_78.top]
0x18000f630  add     ecx, [rbp+57h+rc.top]
0x18000f633  mov     eax, ecx
0x18000f635  cdq
0x18000f636  idiv    ebx
0x18000f638  xor     ebx, ebx
0x18000f63a  test    ecx, ecx
0x18000f63c  lea     rcx, [rbp+57h+var_78]; lprc
0x18000f640  cmovns  ebx, eax
0x18000f643  xor     edx, edx; dx
0x18000f645  mov     r8d, ebx; dy
0x18000f648  call    cs:__imp_OffsetRect
0x18000f64e  mov     r8d, [rbp+57h+var_78.bottom]
0x18000f652  lea     rcx, [rbp+57h+rc]; lprc
0x18000f656  sub     ebx, [rbp+57h+var_78.top]
0x18000f659  add     r8d, 2
0x18000f65d  add     r8d, ebx; dy
0x18000f660  xor     edx, edx; dx
0x18000f662  call    cs:__imp_OffsetRect
0x18000f668  movups  xmm2, xmmword ptr [rbp+57h+var_78.left]
0x18000f66c  mov     [rsp+0C0h+uFlags], 14h; uFlags
0x18000f674  xor     edx, edx; hWndInsertAfter
0x18000f676  movups  xmm0, xmmword ptr [rbp+57h+rc.left]
0x18000f67a  movdqa  xmm1, xmm2
0x18000f67e  movd    r8d, xmm2; X
0x18000f683  psrldq  xmm1, 0Ch
0x18000f688  movd    ecx, xmm1
0x18000f68c  movdqa  xmm1, xmm2
0x18000f690  movdqu  xmmword ptr [rdi+50h], xmm0
0x18000f695  movdqa  xmm0, xmm2
0x18000f699  psrldq  xmm1, 8
0x18000f69e  psrldq  xmm0, 4
0x18000f6a3  movd    r9d, xmm0; Y
0x18000f6a8  movd    eax, xmm1
0x18000f6ac  movdqu  xmmword ptr [rdi+40h], xmm2
0x18000f6b1  sub     ecx, r9d
0x18000f6b4  mov     [rsp+0C0h+cy], ecx; cy
0x18000f6b8  sub     eax, r8d
0x18000f6bb  mov     rcx, [rdi+60h]; hWnd
0x18000f6bf  mov     [rsp+0C0h+format], eax; cx
0x18000f6c3  call    cs:__imp_SetWindowPos
0x18000f6c9  mov     rcx, [rdi+60h]; hWnd
0x18000f6cd  mov     edx, 5; nCmdShow
0x18000f6d2  call    cs:__imp_ShowWindow
0x18000f6d8  mov     eax, 1
0x18000f6dd  mov     rcx, [rbp+57h+var_48]
0x18000f6e1  xor     rcx, rsp; StackCookie
0x18000f6e4  call    __security_check_cookie
0x18000f6e9  add     rsp, 88h
0x18000f6f0  pop     r15
0x18000f6f2  pop     r14
0x18000f6f4  pop     r13
0x18000f6f6  pop     r12
0x18000f6f8  pop     rdi
0x18000f6f9  pop     rsi
0x18000f6fa  pop     rbx
0x18000f6fb  pop     rbp
0x18000f6fc  retn
```
