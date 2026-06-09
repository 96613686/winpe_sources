# MCIWndiSize

- ea: `0x180014cc8`
- end: `0x180014ea7`
- name: `MCIWndiSize`
- size: `479`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180010194`
- `0x180010cc0`
- `0x180012da8`
- `0x180012f08`
- `0x180013edc`

## callees

- `0x1800014b0`
- `0x1800127bc`
- `0x1800129a0`
- `0x180014cc8`
- `0x180014eb0`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180014d48`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180014d5c`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180014d48`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180014d5c`
- `USER32!SetWindowPos` at `0x180014e33`
- `USER32!SetWindowPos` at `0x180014e33`
- `USER32!AdjustWindowRect` at `0x180014df9`
- `USER32!AdjustWindowRect` at `0x180014df9`
- `USER32!GetClientRect` at `0x180014dcc`
- `USER32!GetClientRect` at `0x180014dcc`
- `USER32!GetWindowRect` at `0x180014e06`
- `USER32!GetWindowRect` at `0x180014e40`
- `USER32!GetWindowRect` at `0x180014e06`
- `USER32!GetWindowRect` at `0x180014e40`
- `USER32!GetWindowLongW` at `0x180014dea`
- `USER32!GetWindowLongW` at `0x180014dea`
- `USER32!SetRect` at `0x180014d32`
- `USER32!SetRect` at `0x180014d32`
- `USER32!IsRectEmpty` at `0x180014d69`
- `USER32!IsRectEmpty` at `0x180014dbb`
- `USER32!IsRectEmpty` at `0x180014d69`
- `USER32!IsRectEmpty` at `0x180014dbb`
- `USER32!PostMessageW` at `0x180014e83`
- `USER32!PostMessageW` at `0x180014e83`

## pseudocode

```c
int __fastcall MCIWndiSize(__int64 a1, int a2)
{
  int v2; // edi
  int result; // eax
  LONG WindowLongW; // eax
  struct tagRECT rc; // [rsp+40h] [rbp-30h] BYREF
  struct tagRECT Rect; // [rsp+50h] [rbp-20h] BYREF

  v2 = a2;
  rc = 0;
  Rect = 0;
  if ( a2 )
  {
    rc = *(struct tagRECT *)(a1 + 140);
  }
  else
  {
    if ( *(_DWORD *)(a1 + 20) )
      MCIWndRect(a1, &rc, 0);
    else
      SetRect(&rc, 0, 0, 0, 0);
    v2 = 100;
  }
  rc.bottom = MulDiv(rc.bottom, v2, 100);
  rc.right = MulDiv(rc.right, v2, 100);
  if ( !IsRectEmpty(&rc) )
    MCIWndString(a1, 0, szPutDest, 0, 0, rc.right - rc.left, rc.bottom - rc.top);
  if ( (*(_BYTE *)(a1 + 32) & 1) != 0 )
    return MCIWndiSizePlaybar(a1);
  if ( IsRectEmpty(&rc) )
  {
    GetClientRect(*(HWND *)a1, &Rect);
    rc.right = Rect.right;
  }
  if ( (*(_BYTE *)(a1 + 32) & 2) == 0 )
    rc.bottom += 26;
  WindowLongW = GetWindowLongW(*(HWND *)a1, -16);
  AdjustWindowRect(&rc, WindowLongW, 0);
  GetWindowRect(*(HWND *)a1, &Rect);
  SetWindowPos(*(HWND *)a1, 0, 0, 0, rc.right - rc.left, rc.bottom - rc.top, 0x16u);
  GetWindowRect(*(HWND *)a1, &rc);
  result = -(rc.left + Rect.right - Rect.left - rc.right);
  if ( rc.left + Rect.right - Rect.left - rc.right > 0 )
    result = rc.left + Rect.right - Rect.left - rc.right;
  if ( result < 2 )
  {
    result = -(rc.top + Rect.bottom - Rect.top - rc.bottom);
    if ( rc.top + Rect.bottom - Rect.top - rc.bottom > 0 )
      result = rc.top + Rect.bottom - Rect.top - rc.bottom;
    if ( result < 2 )
      return PostMessageW(*(HWND *)a1, 5u, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x180014cc8  mov     [rsp-8+arg_10], rbx
0x180014ccd  mov     [rsp-8+arg_18], rdi
0x180014cd2  push    rbp
0x180014cd3  mov     rbp, rsp
0x180014cd6  sub     rsp, 70h
0x180014cda  mov     rax, cs:__security_cookie
0x180014ce1  xor     rax, rsp
0x180014ce4  mov     [rbp+var_10], rax
0x180014ce8  xorps   xmm0, xmm0
0x180014ceb  xorps   xmm1, xmm1
0x180014cee  mov     edi, edx
0x180014cf0  mov     rbx, rcx
0x180014cf3  movups  xmmword ptr [rbp+rc.left], xmm0
0x180014cf7  movups  xmmword ptr [rbp+Rect.left], xmm1
0x180014cfb  test    edx, edx
0x180014cfd  jz      short loc_180014D0D
0x180014cff  movups  xmm0, xmmword ptr [rcx+8Ch]
0x180014d06  movdqu  xmmword ptr [rbp+rc.left], xmm0
0x180014d0b  jmp     short loc_180014D3D
0x180014d0d  xor     r8d, r8d; yTop
0x180014d10  cmp     [rcx+14h], r8d
0x180014d14  jz      short loc_180014D21
0x180014d16  lea     rdx, [rbp+rc]
0x180014d1a  call    MCIWndRect
0x180014d1f  jmp     short loc_180014D38
0x180014d21  xor     r9d, r9d; xRight
0x180014d24  mov     [rsp+70h+yBottom], 0; yBottom
0x180014d2c  xor     edx, edx; xLeft
0x180014d2e  lea     rcx, [rbp+rc]; lprc
0x180014d32  call    cs:__imp_SetRect
0x180014d38  mov     edi, 64h ; 'd'
0x180014d3d  mov     ecx, [rbp+rc.bottom]; nNumber
0x180014d40  mov     r8d, 64h ; 'd'; nDenominator
0x180014d46  mov     edx, edi; nNumerator
0x180014d48  call    cs:__imp_MulDiv
0x180014d4e  mov     ecx, [rbp+rc.right]; nNumber
0x180014d51  mov     r8d, 64h ; 'd'; nDenominator
0x180014d57  mov     edx, edi; nNumerator
0x180014d59  mov     [rbp+rc.bottom], eax
0x180014d5c  call    cs:__imp_MulDiv
0x180014d62  lea     rcx, [rbp+rc]; lprc
0x180014d66  mov     [rbp+rc.right], eax
0x180014d69  call    cs:__imp_IsRectEmpty
0x180014d6f  test    eax, eax
0x180014d71  jnz     short loc_180014DA4
0x180014d73  mov     ecx, [rbp+rc.bottom]
0x180014d76  lea     r8, szPutDest; "put destination at %d %d %d %d"
0x180014d7d  sub     ecx, [rbp+rc.top]
0x180014d80  xor     r9d, r9d
0x180014d83  mov     eax, [rbp+rc.right]
0x180014d86  xor     edx, edx
0x180014d88  sub     eax, [rbp+rc.left]
0x180014d8b  mov     [rsp+70h+uFlags], ecx
0x180014d8f  mov     rcx, rbx
0x180014d92  mov     [rsp+70h+cy], eax
0x180014d96  mov     qword ptr [rsp+70h+yBottom], 0
0x180014d9f  call    MCIWndString
0x180014da4  test    byte ptr [rbx+20h], 1
0x180014da8  jz      short loc_180014DB7
0x180014daa  mov     rcx, rbx
0x180014dad  call    MCIWndiSizePlaybar
0x180014db2  jmp     loc_180014E89
0x180014db7  lea     rcx, [rbp+rc]; lprc
0x180014dbb  call    cs:__imp_IsRectEmpty
0x180014dc1  test    eax, eax
0x180014dc3  jz      short loc_180014DD8
0x180014dc5  mov     rcx, [rbx]; hWnd
0x180014dc8  lea     rdx, [rbp+Rect]; lpRect
0x180014dcc  call    cs:__imp_GetClientRect
0x180014dd2  mov     eax, [rbp+Rect.right]
0x180014dd5  mov     [rbp+rc.right], eax
0x180014dd8  test    byte ptr [rbx+20h], 2
0x180014ddc  jnz     short loc_180014DE2
0x180014dde  add     [rbp+rc.bottom], 1Ah
0x180014de2  mov     rcx, [rbx]; hWnd
0x180014de5  mov     edx, 0FFFFFFF0h; nIndex
0x180014dea  call    cs:__imp_GetWindowLongW
0x180014df0  xor     r8d, r8d; bMenu
0x180014df3  lea     rcx, [rbp+rc]; lpRect
0x180014df7  mov     edx, eax; dwStyle
0x180014df9  call    cs:__imp_AdjustWindowRect
0x180014dff  mov     rcx, [rbx]; hWnd
0x180014e02  lea     rdx, [rbp+Rect]; lpRect
0x180014e06  call    cs:__imp_GetWindowRect
0x180014e0c  mov     ecx, [rbp+rc.bottom]
0x180014e0f  xor     r9d, r9d; Y
0x180014e12  sub     ecx, [rbp+rc.top]
0x180014e15  xor     r8d, r8d; X
0x180014e18  mov     eax, [rbp+rc.right]
0x180014e1b  xor     edx, edx; hWndInsertAfter
0x180014e1d  sub     eax, [rbp+rc.left]
0x180014e20  mov     [rsp+70h+uFlags], 16h; uFlags
0x180014e28  mov     [rsp+70h+cy], ecx; cy
0x180014e2c  mov     rcx, [rbx]; hWnd
0x180014e2f  mov     [rsp+70h+yBottom], eax; cx
0x180014e33  call    cs:__imp_SetWindowPos
0x180014e39  mov     rcx, [rbx]; hWnd
0x180014e3c  lea     rdx, [rbp+rc]; lpRect
0x180014e40  call    cs:__imp_GetWindowRect
0x180014e46  mov     ecx, [rbp+Rect.right]
0x180014e49  sub     ecx, [rbp+Rect.left]
0x180014e4c  sub     ecx, [rbp+rc.right]
0x180014e4f  add     ecx, [rbp+rc.left]
0x180014e52  mov     eax, ecx
0x180014e54  neg     eax
0x180014e56  cmovs   eax, ecx
0x180014e59  cmp     eax, 2
0x180014e5c  jge     short loc_180014E89
0x180014e5e  mov     ecx, [rbp+Rect.bottom]
0x180014e61  sub     ecx, [rbp+Rect.top]
0x180014e64  sub     ecx, [rbp+rc.bottom]
0x180014e67  add     ecx, [rbp+rc.top]
0x180014e6a  mov     eax, ecx
0x180014e6c  neg     eax
0x180014e6e  cmovs   eax, ecx
0x180014e71  cmp     eax, 2
0x180014e74  jge     short loc_180014E89
0x180014e76  mov     rcx, [rbx]; hWnd
0x180014e79  xor     r9d, r9d; lParam
0x180014e7c  xor     r8d, r8d; wParam
0x180014e7f  lea     edx, [r9+5]; Msg
0x180014e83  call    cs:__imp_PostMessageW
0x180014e89  mov     rcx, [rbp+var_10]
0x180014e8d  xor     rcx, rsp; StackCookie
0x180014e90  call    __security_check_cookie
0x180014e95  lea     r11, [rsp+70h+var_s0]
0x180014e9a  mov     rbx, [r11+20h]
0x180014e9e  mov     rdi, [r11+28h]
0x180014ea2  mov     rsp, r11
0x180014ea5  pop     rbp
0x180014ea6  retn
```
