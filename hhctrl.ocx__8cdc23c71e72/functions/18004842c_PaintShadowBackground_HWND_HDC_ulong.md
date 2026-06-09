# PaintShadowBackground(HWND__ *,HDC__ *,ulong)

- ea: `0x18004842c`
- end: `0x180048708`
- name: `?PaintShadowBackground@@YAHPEAUHWND__@@PEAUHDC__@@K@Z`
- size: `732`
- prototype: `__int64 __fastcall(HWND hWnd, HDC hdc, COLORREF color)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180048710`
- `0x180058e00`

## callees

- `0x18004842c`
- `0x180075c90`

## import_xrefs

- `USER32!InflateRect` at `0x180048558`
- `USER32!InflateRect` at `0x180048558`
- `USER32!FillRect` at `0x1800484f4`
- `USER32!FillRect` at `0x1800484f4`
- `USER32!FrameRect` at `0x180048548`
- `USER32!FrameRect` at `0x180048575`
- `USER32!FrameRect` at `0x180048548`
- `USER32!FrameRect` at `0x180048575`
- `USER32!GetSysColor` at `0x18004849d`
- `USER32!GetSysColor` at `0x18004849d`
- `USER32!GetClientRect` at `0x180048461`
- `USER32!GetClientRect` at `0x180048461`
- `USER32!ClientToScreen` at `0x1800484d1`
- `USER32!ClientToScreen` at `0x1800484d1`
- `GDI32!DeleteObject` at `0x1800484fd`
- `GDI32!DeleteObject` at `0x1800485b1`
- `GDI32!DeleteObject` at `0x1800486db`
- `GDI32!DeleteObject` at `0x1800484fd`
- `GDI32!DeleteObject` at `0x1800485b1`
- `GDI32!DeleteObject` at `0x1800486db`
- `GDI32!GetStockObject` at `0x180048538`
- `GDI32!GetStockObject` at `0x180048565`
- `GDI32!GetStockObject` at `0x1800485c1`
- `GDI32!GetStockObject` at `0x1800485f2`
- `GDI32!GetStockObject` at `0x180048538`
- `GDI32!GetStockObject` at `0x180048565`
- `GDI32!GetStockObject` at `0x1800485c1`
- `GDI32!GetStockObject` at `0x1800485f2`
- `GDI32!SelectObject` at `0x180048603`
- `GDI32!SelectObject` at `0x18004860f`
- `GDI32!SelectObject` at `0x1800486ce`
- `GDI32!SelectObject` at `0x180048603`
- `GDI32!SelectObject` at `0x18004860f`
- `GDI32!SelectObject` at `0x1800486ce`
- `GDI32!PatBlt` at `0x180048661`
- `GDI32!PatBlt` at `0x1800486bd`
- `GDI32!PatBlt` at `0x180048661`
- `GDI32!PatBlt` at `0x1800486bd`
- `GDI32!CreateSolidBrush` at `0x1800484a7`
- `GDI32!CreateSolidBrush` at `0x1800484a7`
- `GDI32!SetBkMode` at `0x1800485e7`
- `GDI32!SetBkMode` at `0x1800485e7`
- `GDI32!UnrealizeObject` at `0x1800484bc`
- `GDI32!UnrealizeObject` at `0x1800484bc`
- `GDI32!SetBrushOrgEx` at `0x1800484e4`
- `GDI32!SetBrushOrgEx` at `0x1800484e4`
- `GDI32!CreateBitmap` at `0x180048594`
- `GDI32!CreateBitmap` at `0x180048594`
- `GDI32!CreatePatternBrush` at `0x1800485a5`
- `GDI32!CreatePatternBrush` at `0x1800485a5`
- `GDI32!SetROP2` at `0x1800485db`
- `GDI32!SetROP2` at `0x1800485db`

## pseudocode

```c
__int64 __fastcall PaintShadowBackground(HWND hWnd, HDC hdc, COLORREF color)
{
  LONG v6; // ecx
  LONG v7; // ecx
  HBRUSH SolidBrush; // rax
  HBRUSH v9; // rdi
  LONG v10; // ecx
  LONG v11; // ecx
  HBRUSH StockObject; // rax
  HBRUSH v13; // rax
  HBRUSH PatternBrush; // rdi
  HBITMAP Bitmap; // rax
  HBITMAP v16; // rsi
  int v17; // esi
  HGDIOBJ v18; // rax
  HGDIOBJ v19; // rax
  void *v20; // r14
  LONG v21; // edx
  LONG v22; // r8d
  LONG v23; // r9d
  struct tagPOINT Point; // [rsp+30h] [rbp-40h] BYREF
  RECT rc; // [rsp+40h] [rbp-30h] BYREF
  struct tagRECT Rect; // [rsp+50h] [rbp-20h] BYREF

  Rect = 0;
  GetClientRect(hWnd, &Rect);
  rc = Rect;
  v6 = _mm_srli_si128(*(__m128i *)&Rect, 8).m128i_i32[1] - 6;
  if ( v6 < 0 )
    v6 = 0;
  rc.bottom = v6;
  v7 = rc.right - 6;
  if ( rc.right - 6 < 0 )
    v7 = 0;
  rc.right = v7;
  if ( color == -1 )
    color = GetSysColor(5);
  SolidBrush = CreateSolidBrush(color);
  v9 = SolidBrush;
  if ( !SolidBrush )
    return 0;
  UnrealizeObject(SolidBrush);
  Point = 0;
  ClientToScreen(hWnd, &Point);
  SetBrushOrgEx(hdc, Point.x, Point.y, 0);
  FillRect(hdc, &rc, v9);
  DeleteObject(v9);
  rc = Rect;
  v10 = _mm_srli_si128(*(__m128i *)&Rect, 8).m128i_i32[1] - 6;
  if ( v10 < 0 )
    v10 = 0;
  rc.bottom = v10;
  v11 = rc.right - 6;
  if ( rc.right - 6 < 0 )
    v11 = 0;
  rc.right = v11;
  StockObject = (HBRUSH)GetStockObject(4);
  FrameRect(hdc, &rc, StockObject);
  InflateRect(&rc, -1, -1);
  v13 = (HBRUSH)GetStockObject(1);
  FrameRect(hdc, &rc, v13);
  PatternBrush = 0;
  Bitmap = CreateBitmap(8, 8, 1u, 1u, "U");
  v16 = Bitmap;
  if ( Bitmap )
  {
    PatternBrush = CreatePatternBrush(Bitmap);
    DeleteObject(v16);
  }
  v17 = 0;
  if ( PatternBrush )
    goto LABEL_17;
  if ( GetStockObject(4) )
    return 0;
  v17 = 1;
LABEL_17:
  SetROP2(hdc, 9);
  SetBkMode(hdc, 1);
  v18 = GetStockObject(8);
  if ( v18 )
    SelectObject(hdc, v18);
  v19 = SelectObject(hdc, PatternBrush);
  rc = Rect;
  v20 = v19;
  v21 = Rect.right - 6;
  rc.top = Rect.top + 6;
  if ( Rect.right - 6 < 0 )
    v21 = 0;
  rc.left = v21;
  PatBlt(hdc, v21, Rect.top + 6, Rect.right - v21, Rect.bottom - (Rect.top + 6), 0xA000C9u);
  rc = Rect;
  v22 = _mm_srli_si128(*(__m128i *)&Rect, 8).m128i_i32[1] - 6;
  if ( v22 < 0 )
    v22 = 0;
  v23 = Rect.right - 5;
  rc.top = v22;
  rc.left = Rect.left + 6;
  if ( Rect.right - 5 < 0 )
    v23 = 0;
  rc.right = v23;
  PatBlt(hdc, Rect.left + 6, v22, v23 - (Rect.left + 6), rc.bottom - v22, 0xA000C9u);
  if ( v20 )
    SelectObject(hdc, v20);
  if ( !v17 )
    DeleteObject(PatternBrush);
  return 1;
}

```

## disassembly

```asm
0x18004842c  mov     [rsp-28h+arg_18], rbx
0x180048431  push    rbp
0x180048432  push    rsi
0x180048433  push    rdi
0x180048434  push    r12
0x180048436  push    r14
0x180048438  mov     rbp, rsp
0x18004843b  sub     rsp, 70h
0x18004843f  mov     rax, cs:__security_cookie
0x180048446  xor     rax, rsp
0x180048449  mov     [rbp+var_10], rax
0x18004844d  mov     rbx, rdx
0x180048450  xorps   xmm0, xmm0
0x180048453  lea     rdx, [rbp+Rect]; lpRect
0x180048457  mov     edi, r8d
0x18004845a  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18004845e  mov     rsi, rcx
0x180048461  call    cs:__imp_GetClientRect
0x180048467  movaps  xmm0, xmmword ptr [rbp+Rect.left]
0x18004846b  xor     eax, eax
0x18004846d  movdqa  xmmword ptr [rbp+rc.left], xmm0
0x180048472  psrldq  xmm0, 8
0x180048477  movq    rcx, xmm0
0x18004847c  shr     rcx, 20h
0x180048480  add     ecx, 0FFFFFFFAh
0x180048483  cmovs   ecx, eax
0x180048486  mov     [rbp+rc.bottom], ecx
0x180048489  mov     ecx, [rbp+rc.right]
0x18004848c  add     ecx, 0FFFFFFFAh
0x18004848f  cmovs   ecx, eax
0x180048492  mov     [rbp+rc.right], ecx
0x180048495  cmp     edi, 0FFFFFFFFh
0x180048498  jnz     short loc_1800484A5
0x18004849a  lea     ecx, [rax+5]; nIndex
0x18004849d  call    cs:__imp_GetSysColor
0x1800484a3  mov     edi, eax
0x1800484a5  mov     ecx, edi; color
0x1800484a7  call    cs:__imp_CreateSolidBrush
0x1800484ad  mov     rdi, rax
0x1800484b0  test    rax, rax
0x1800484b3  jz      loc_1800486E6
0x1800484b9  mov     rcx, rax; h
0x1800484bc  call    cs:__imp_UnrealizeObject
0x1800484c2  lea     rdx, [rbp+Point]; lpPoint
0x1800484c6  mov     qword ptr [rbp+Point.x], 0
0x1800484ce  mov     rcx, rsi; hWnd
0x1800484d1  call    cs:__imp_ClientToScreen
0x1800484d7  mov     r8d, [rbp+Point.y]; y
0x1800484db  xor     r9d, r9d; lppt
0x1800484de  mov     edx, [rbp+Point.x]; x
0x1800484e1  mov     rcx, rbx; hdc
0x1800484e4  call    cs:__imp_SetBrushOrgEx
0x1800484ea  mov     r8, rdi; hbr
0x1800484ed  lea     rdx, [rbp+rc]; lprc
0x1800484f1  mov     rcx, rbx; hDC
0x1800484f4  call    cs:__imp_FillRect
0x1800484fa  mov     rcx, rdi; ho
0x1800484fd  call    cs:__imp_DeleteObject
0x180048503  movaps  xmm0, xmmword ptr [rbp+Rect.left]
0x180048507  xor     eax, eax
0x180048509  movdqa  xmmword ptr [rbp+rc.left], xmm0
0x18004850e  psrldq  xmm0, 8
0x180048513  movq    rcx, xmm0
0x180048518  shr     rcx, 20h
0x18004851c  lea     r14d, [rax+4]
0x180048520  add     ecx, 0FFFFFFFAh
0x180048523  cmovs   ecx, eax
0x180048526  mov     [rbp+rc.bottom], ecx
0x180048529  mov     ecx, [rbp+rc.right]
0x18004852c  add     ecx, 0FFFFFFFAh
0x18004852f  cmovs   ecx, eax
0x180048532  mov     [rbp+rc.right], ecx
0x180048535  mov     ecx, r14d; i
0x180048538  call    cs:__imp_GetStockObject
0x18004853e  lea     rdx, [rbp+rc]; lprc
0x180048542  mov     rcx, rbx; hDC
0x180048545  mov     r8, rax; hbr
0x180048548  call    cs:__imp_FrameRect
0x18004854e  or      edx, 0FFFFFFFFh; dx
0x180048551  lea     rcx, [rbp+rc]; lprc
0x180048555  mov     r8d, edx; dy
0x180048558  call    cs:__imp_InflateRect
0x18004855e  lea     r12d, [r14-3]
0x180048562  mov     ecx, r12d; i
0x180048565  call    cs:__imp_GetStockObject
0x18004856b  lea     rdx, [rbp+rc]; lprc
0x18004856f  mov     rcx, rbx; hDC
0x180048572  mov     r8, rax; hbr
0x180048575  call    cs:__imp_FrameRect
0x18004857b  lea     rax, aU; "U"
0x180048582  xor     edi, edi
0x180048584  mov     r9d, r12d; nBitCount
0x180048587  mov     [rsp+70h+lpBits], rax; lpBits
0x18004858c  mov     r8d, r12d; nPlanes
0x18004858f  lea     edx, [rdi+8]; nHeight
0x180048592  mov     ecx, edx; nWidth
0x180048594  call    cs:__imp_CreateBitmap
0x18004859a  mov     rsi, rax
0x18004859d  test    rax, rax
0x1800485a0  jz      short loc_1800485B7
0x1800485a2  mov     rcx, rax; hbm
0x1800485a5  call    cs:__imp_CreatePatternBrush
0x1800485ab  mov     rcx, rsi; ho
0x1800485ae  mov     rdi, rax
0x1800485b1  call    cs:__imp_DeleteObject
0x1800485b7  xor     esi, esi
0x1800485b9  test    rdi, rdi
0x1800485bc  jnz     short loc_1800485D3
0x1800485be  mov     ecx, r14d; i
0x1800485c1  call    cs:__imp_GetStockObject
0x1800485c7  test    rax, rax
0x1800485ca  jnz     loc_1800486E6
0x1800485d0  mov     esi, r12d
0x1800485d3  mov     edx, 9; rop2
0x1800485d8  mov     rcx, rbx; hdc
0x1800485db  call    cs:__imp_SetROP2
0x1800485e1  mov     edx, r12d; mode
0x1800485e4  mov     rcx, rbx; hdc
0x1800485e7  call    cs:__imp_SetBkMode
0x1800485ed  mov     ecx, 8; i
0x1800485f2  call    cs:__imp_GetStockObject
0x1800485f8  test    rax, rax
0x1800485fb  jz      short loc_180048609
0x1800485fd  mov     rdx, rax; h
0x180048600  mov     rcx, rbx; hdc
0x180048603  call    cs:__imp_SelectObject
0x180048609  mov     rdx, rdi; h
0x18004860c  mov     rcx, rbx; hdc
0x18004860f  call    cs:__imp_SelectObject
0x180048615  movaps  xmm0, xmmword ptr [rbp+Rect.left]
0x180048619  xor     ecx, ecx
0x18004861b  movdqa  xmmword ptr [rbp+rc.left], xmm0
0x180048620  mov     r14, rax
0x180048623  mov     r9d, [rbp+rc.right]
0x180048627  movq    r8, xmm0
0x18004862c  mov     rax, qword ptr [rbp+rc.right]
0x180048630  shr     r8, 20h
0x180048634  add     r8d, 6; y
0x180048638  mov     [rsp+70h+rop], 0A000C9h; rop
0x180048640  lea     edx, [r9-6]
0x180048644  mov     [rbp+rc.top], r8d
0x180048648  test    edx, edx
0x18004864a  cmovs   edx, ecx; x
0x18004864d  shr     rax, 20h
0x180048651  sub     eax, r8d
0x180048654  mov     [rbp+rc.left], edx
0x180048657  sub     r9d, edx; w
0x18004865a  mov     dword ptr [rsp+70h+lpBits], eax; h
0x18004865e  mov     rcx, rbx; hdc
0x180048661  call    cs:__imp_PatBlt
0x180048667  movaps  xmm0, xmmword ptr [rbp+Rect.left]
0x18004866b  xor     eax, eax
0x18004866d  movdqa  xmmword ptr [rbp+rc.left], xmm0
0x180048672  mov     rcx, rbx; hdc
0x180048675  mov     edx, [rbp+rc.left]
0x180048678  mov     r9d, [rbp+rc.right]
0x18004867c  psrldq  xmm0, 8
0x180048681  movq    r8, xmm0
0x180048686  mov     [rsp+70h+rop], 0A000C9h; rop
0x18004868e  shr     r8, 20h
0x180048692  add     r8d, 0FFFFFFFAh
0x180048696  cmovs   r8d, eax; y
0x18004869a  add     edx, 6; x
0x18004869d  add     r9d, 0FFFFFFFBh
0x1800486a1  mov     [rbp+rc.top], r8d
0x1800486a5  mov     [rbp+rc.left], edx
0x1800486a8  cmovs   r9d, eax
0x1800486ac  mov     eax, [rbp+rc.bottom]
0x1800486af  sub     eax, r8d
0x1800486b2  mov     [rbp+rc.right], r9d
0x1800486b6  sub     r9d, edx; w
0x1800486b9  mov     dword ptr [rsp+70h+lpBits], eax; h
0x1800486bd  call    cs:__imp_PatBlt
0x1800486c3  test    r14, r14
0x1800486c6  jz      short loc_1800486D4
0x1800486c8  mov     rdx, r14; h
0x1800486cb  mov     rcx, rbx; hdc
0x1800486ce  call    cs:__imp_SelectObject
0x1800486d4  test    esi, esi
0x1800486d6  jnz     short loc_1800486E1
0x1800486d8  mov     rcx, rdi; ho
0x1800486db  call    cs:__imp_DeleteObject
0x1800486e1  mov     eax, r12d
0x1800486e4  jmp     short loc_1800486E8
0x1800486e6  xor     eax, eax
0x1800486e8  mov     rcx, [rbp+var_10]
0x1800486ec  xor     rcx, rsp; StackCookie
0x1800486ef  call    __security_check_cookie
0x1800486f4  mov     rbx, [rsp+70h+arg_18]
0x1800486fc  add     rsp, 70h
0x180048700  pop     r14
0x180048702  pop     r12
0x180048704  pop     rdi
0x180048705  pop     rsi
0x180048706  pop     rbp
0x180048707  retn
```
