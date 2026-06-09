# CCandidatePosition::GetRectFromCompFont(IMCLock &,tagPOINT *,tagRECT *)

- ea: `0x180056bd8`
- end: `0x180056d9d`
- name: `?GetRectFromCompFont@CCandidatePosition@@AEAAJAEAVIMCLock@@PEAUtagPOINT@@PEAUtagRECT@@@Z`
- size: `453`
- prototype: `int(CCandidatePosition *__hidden this, struct IMCLock *, struct tagPOINT *, struct tagRECT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001bbd0`
- `0x180056af0`

## callees

- `0x180056bd8`
- `0x18009eaea`
- `0x180106a60`

## import_xrefs

- `USER32!ClientToScreen` at `0x180056d40`
- `USER32!ClientToScreen` at `0x180056d40`
- `USER32!ReleaseDC` at `0x180056cb2`
- `USER32!ReleaseDC` at `0x180056cb2`
- `USER32!GetDC` at `0x180056c18`
- `USER32!GetDC` at `0x180056c18`
- `USER32!SetRect` at `0x180056d25`
- `USER32!SetRect` at `0x180056d25`
- `GDI32!DeleteObject` at `0x180056ca2`
- `GDI32!DeleteObject` at `0x180056ca2`
- `GDI32!SelectObject` at `0x180056c63`
- `GDI32!SelectObject` at `0x180056c99`
- `GDI32!SelectObject` at `0x180056c63`
- `GDI32!SelectObject` at `0x180056c99`
- `GDI32!CreateFontIndirectW` at `0x180056c4f`
- `GDI32!CreateFontIndirectW` at `0x180056c4f`
- `GDI32!GetTextMetricsW` at `0x180056c89`
- `GDI32!GetTextMetricsW` at `0x180056c89`
- `ext-ms-win-imm-l1-1-0!ImmGetCompositionFontW` at `0x180056c41`
- `ext-ms-win-imm-l1-1-0!ImmGetCompositionFontW` at `0x180056c41`

## pseudocode

```c
__int64 __fastcall CCandidatePosition::GetRectFromCompFont(
        CCandidatePosition *this,
        struct IMCLock *a2,
        struct tagPOINT *a3,
        struct tagRECT *a4)
{
  unsigned int v7; // r12d
  HDC DC; // rsi
  HFONT v9; // rax
  HFONT v10; // r15
  HGDIOBJ v11; // r13
  int v13; // edx
  LONG x; // edx
  LONG v15; // r9d
  LONG y; // r8d
  LONG yBottom; // eax
  HWND *v18; // rcx
  LONG v19; // eax
  LONG v20; // eax
  int v21; // edx
  int v22; // edx
  struct tagPOINT Point; // [rsp+30h] [rbp-99h] BYREF
  tagTEXTMETRICW tm; // [rsp+38h] [rbp-91h] BYREF
  struct tagLOGFONTW lf; // [rsp+80h] [rbp-49h] BYREF

  v7 = -2147467259;
  DC = GetDC(**((HWND **)a2 + 1));
  if ( DC )
  {
    memset_0(&lf, 0, sizeof(lf));
    if ( !ImmGetCompositionFontW(*((HIMC *)a2 + 2), &lf) )
      goto LABEL_6;
    v9 = CreateFontIndirectW(&lf);
    v10 = v9;
    if ( !v9 )
      goto LABEL_6;
    v11 = SelectObject(DC, v9);
    memset(&tm, 0, sizeof(tm));
    if ( !GetTextMetricsW(DC, &tm) )
    {
LABEL_5:
      SelectObject(DC, v11);
      DeleteObject(v10);
LABEL_6:
      ReleaseDC(**((HWND **)a2 + 1), DC);
      return v7;
    }
    v13 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 44LL) / 900 % 4;
    if ( v13 )
    {
      v21 = v13 - 1;
      if ( !v21 )
      {
        yBottom = a3->y;
        x = a3->x;
        v15 = a3->x + tm.tmMaxCharWidth;
        y = yBottom - tm.tmHeight;
        goto LABEL_11;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        yBottom = a3->y;
        y = yBottom - tm.tmHeight;
        x = a3->x - tm.tmMaxCharWidth;
        v15 = a3->x;
        goto LABEL_11;
      }
      if ( v22 != 1 )
        goto LABEL_12;
      x = a3->x - tm.tmMaxCharWidth;
      v15 = a3->x;
    }
    else
    {
      x = a3->x;
      v15 = a3->x + tm.tmMaxCharWidth;
    }
    y = a3->y;
    yBottom = y + tm.tmHeight;
LABEL_11:
    SetRect(a4, x, y, v15, yBottom);
LABEL_12:
    v18 = (HWND *)*((_QWORD *)a2 + 1);
    Point = 0;
    ClientToScreen(*v18, &Point);
    v19 = Point.x;
    a4->left += Point.x;
    a4->right += v19;
    v20 = Point.y;
    a4->top += Point.y;
    a4->bottom += v20;
    v7 = 0;
    goto LABEL_5;
  }
  return v7;
}

```

## disassembly

```asm
0x180056bd8  mov     [rsp-8+arg_0], rbx
0x180056bdd  push    rbp
0x180056bde  push    rsi
0x180056bdf  push    rdi
0x180056be0  push    r12
0x180056be2  push    r13
0x180056be4  push    r14
0x180056be6  push    r15
0x180056be8  lea     rbp, [rsp-27h]
0x180056bed  sub     rsp, 0F0h
0x180056bf4  mov     rax, cs:__security_cookie
0x180056bfb  xor     rax, rsp
0x180056bfe  mov     [rbp+57h+var_40], rax
0x180056c02  mov     rcx, [rdx+8]
0x180056c06  mov     rbx, r9
0x180056c09  mov     rdi, r8
0x180056c0c  mov     r14, rdx
0x180056c0f  mov     r12d, 80004005h
0x180056c15  mov     rcx, [rcx]; hWnd
0x180056c18  call    cs:__imp_GetDC
0x180056c1e  mov     rsi, rax
0x180056c21  test    rax, rax
0x180056c24  jz      loc_180056CB8
0x180056c2a  xor     edx, edx; Val
0x180056c2c  lea     rcx, [rbp+57h+lf]; void *
0x180056c30  lea     r8d, [rdx+5Ch]; Size
0x180056c34  call    memset_0
0x180056c39  mov     rcx, [r14+10h]; HIMC
0x180056c3d  lea     rdx, [rbp+57h+lf]; lplf
0x180056c41  call    cs:__imp_ImmGetCompositionFontW
0x180056c47  test    eax, eax
0x180056c49  jz      short loc_180056CA8
0x180056c4b  lea     rcx, [rbp+57h+lf]; lplf
0x180056c4f  call    cs:__imp_CreateFontIndirectW
0x180056c55  mov     r15, rax
0x180056c58  test    rax, rax
0x180056c5b  jz      short loc_180056CA8
0x180056c5d  mov     rdx, rax; h
0x180056c60  mov     rcx, rsi; hdc
0x180056c63  call    cs:__imp_SelectObject
0x180056c69  xorps   xmm0, xmm0
0x180056c6c  lea     rdx, [rsp+120h+tm]; lptm
0x180056c71  movups  xmmword ptr [rbp+57h+tm.tmOverhang], xmm0
0x180056c75  mov     rcx, rsi; hdc
0x180056c78  mov     r13, rax
0x180056c7b  movups  xmmword ptr [rbp+57h+tm.tmFirstChar], xmm0
0x180056c7f  movups  xmmword ptr [rsp+120h+tm.tmHeight], xmm0
0x180056c84  movups  xmmword ptr [rsp+120h+tm.tmExternalLeading], xmm0
0x180056c89  call    cs:__imp_GetTextMetricsW
0x180056c8f  test    eax, eax
0x180056c91  jnz     short loc_180056CE2
0x180056c93  mov     rdx, r13; h
0x180056c96  mov     rcx, rsi; hdc
0x180056c99  call    cs:__imp_SelectObject
0x180056c9f  mov     rcx, r15; ho
0x180056ca2  call    cs:__imp_DeleteObject
0x180056ca8  mov     rcx, [r14+8]
0x180056cac  mov     rdx, rsi; hDC
0x180056caf  mov     rcx, [rcx]; hWnd
0x180056cb2  call    cs:__imp_ReleaseDC
0x180056cb8  mov     eax, r12d
0x180056cbb  mov     rcx, [rbp+57h+var_40]
0x180056cbf  xor     rcx, rsp; StackCookie
0x180056cc2  call    __security_check_cookie
0x180056cc7  mov     rbx, [rsp+120h+arg_0]
0x180056ccf  add     rsp, 0F0h
0x180056cd6  pop     r15
0x180056cd8  pop     r14
0x180056cda  pop     r13
0x180056cdc  pop     r12
0x180056cde  pop     rdi
0x180056cdf  pop     rsi
0x180056ce0  pop     rbp
0x180056ce1  retn
0x180056ce2  mov     rax, [r14+8]
0x180056ce6  mov     r9d, [rbp+57h+tm.tmMaxCharWidth]
0x180056cea  mov     r10d, [rsp+120h+tm.tmHeight]
0x180056cef  mov     ecx, [rax+2Ch]
0x180056cf2  mov     eax, 91A2B3C5h
0x180056cf7  imul    ecx
0x180056cf9  add     edx, ecx
0x180056cfb  mov     ecx, 4
0x180056d00  sar     edx, 9
0x180056d03  mov     eax, edx
0x180056d05  shr     eax, 1Fh
0x180056d08  add     eax, edx
0x180056d0a  cdq
0x180056d0b  idiv    ecx
0x180056d0d  test    edx, edx
0x180056d0f  jnz     short loc_180056D61
0x180056d11  mov     edx, [rdi]; xLeft
0x180056d13  add     r9d, edx; xRight
0x180056d16  mov     r8d, [rdi+4]; yTop
0x180056d1a  lea     eax, [r8+r10]
0x180056d1e  mov     rcx, rbx; lprc
0x180056d21  mov     [rsp+120h+yBottom], eax; yBottom
0x180056d25  call    cs:__imp_SetRect
0x180056d2b  mov     rcx, [r14+8]
0x180056d2f  lea     rdx, [rsp+120h+Point]; lpPoint
0x180056d34  mov     qword ptr [rsp+120h+Point.x], 0
0x180056d3d  mov     rcx, [rcx]; hWnd
0x180056d40  call    cs:__imp_ClientToScreen
0x180056d46  mov     eax, [rsp+120h+Point.x]
0x180056d4a  add     [rbx], eax
0x180056d4c  add     [rbx+8], eax
0x180056d4f  mov     eax, [rsp+120h+Point.y]
0x180056d53  add     [rbx+4], eax
0x180056d56  add     [rbx+0Ch], eax
0x180056d59  xor     r12d, r12d
0x180056d5c  jmp     loc_180056C93
0x180056d61  sub     edx, 1
0x180056d64  jz      short loc_180056D8D
0x180056d66  sub     edx, 1
0x180056d69  jz      short loc_180056D7A
0x180056d6b  cmp     edx, 1
0x180056d6e  jnz     short loc_180056D2B
0x180056d70  mov     edx, [rdi]
0x180056d72  sub     edx, r9d
0x180056d75  mov     r9d, [rdi]
0x180056d78  jmp     short loc_180056D16
0x180056d7a  mov     eax, [rdi+4]
0x180056d7d  mov     r8d, eax
0x180056d80  mov     edx, [rdi]
0x180056d82  sub     r8d, r10d
0x180056d85  sub     edx, r9d
0x180056d88  mov     r9d, [rdi]
0x180056d8b  jmp     short loc_180056D1E
0x180056d8d  mov     eax, [rdi+4]
0x180056d90  mov     r8d, eax
0x180056d93  mov     edx, [rdi]
0x180056d95  add     r9d, edx
0x180056d98  sub     r8d, r10d
0x180056d9b  jmp     short loc_180056D1E
```
