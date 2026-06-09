# CAnimate::OnOpen(HINSTANCE__ *,ushort const *,int)

- ea: `0x1800b8bdc`
- end: `0x1800b8f61`
- name: `?OnOpen@CAnimate@@IEAAHPEAUHINSTANCE__@@PEBGH@Z`
- size: `901`
- prototype: `__int64 __fastcall(CAnimate *__hidden this, HINSTANCE hModule, LPCWSTR lpName, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800b9078`
- `0x180139144`

## callees

- `0x1800b8bdc`
- `0x1800b9548`
- `0x1800b991c`
- `0x1800b9990`
- `0x1800dfd9c`
- `0x180114520`
- `0x180150878`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b8c65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b8c95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b8ce7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b8c65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b8c95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b8ce7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b8ca9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b8ca9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b8c73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b8cf5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b8c73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b8cf5`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800b8d54`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800b8d64`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800b8d54`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800b8d64`
- `GDI32!DeleteObject` at `0x1800b8e41`
- `GDI32!DeleteObject` at `0x1800b8e41`
- `GDI32!SelectObject` at `0x1800b8de0`
- `GDI32!SelectObject` at `0x1800b8e38`
- `GDI32!SelectObject` at `0x1800b8de0`
- `GDI32!SelectObject` at `0x1800b8e38`
- `GDI32!DeleteDC` at `0x1800b8e4f`
- `GDI32!DeleteDC` at `0x1800b8e4f`
- `GDI32!CreateCompatibleDC` at `0x1800b8daf`
- `GDI32!CreateCompatibleDC` at `0x1800b8daf`
- `GDI32!CreateCompatibleBitmap` at `0x1800b8dcc`
- `GDI32!CreateCompatibleBitmap` at `0x1800b8dcc`
- `GDI32!GetPixel` at `0x1800b8e29`
- `GDI32!GetPixel` at `0x1800b8e29`
- `USER32!AdjustWindowRectEx` at `0x1800b8ef3`
- `USER32!AdjustWindowRectEx` at `0x1800b8ef3`
- `USER32!OffsetRect` at `0x1800b8eb9`
- `USER32!OffsetRect` at `0x1800b8eb9`
- `USER32!SetWindowPos` at `0x1800b8f24`
- `USER32!SetWindowPos` at `0x1800b8f24`
- `USER32!GetWindowTextW` at `0x1800b8c2b`
- `USER32!GetWindowTextW` at `0x1800b8c2b`
- `USER32!GetWindowLongW` at `0x1800b8ed0`
- `USER32!GetWindowLongW` at `0x1800b8ee0`
- `USER32!GetWindowLongW` at `0x1800b8ed0`
- `USER32!GetWindowLongW` at `0x1800b8ee0`
- `USER32!GetDC` at `0x1800b8da3`
- `USER32!GetDC` at `0x1800b8da3`
- `USER32!SendMessageW` at `0x1800b8e64`
- `USER32!SendMessageW` at `0x1800b8e64`
- `USER32!GetWindowLongPtrW` at `0x1800b8c42`
- `USER32!GetWindowLongPtrW` at `0x1800b8c42`
- `USER32!GetClientRect` at `0x1800b8e97`
- `USER32!GetClientRect` at `0x1800b8e97`
- `USER32!SetRect` at `0x1800b8d7f`
- `USER32!SetRect` at `0x1800b8d7f`
- `USER32!InvalidateRect` at `0x1800b8f51`
- `USER32!InvalidateRect` at `0x1800b8f51`
- `USER32!ReleaseDC` at `0x1800b8e70`
- `USER32!ReleaseDC` at `0x1800b8e70`
- `USER32!PostMessageW` at `0x1800b8f43`
- `USER32!PostMessageW` at `0x1800b8f43`

## pseudocode

```c
__int64 __fastcall CAnimate::OnOpen(CAnimate *this, HINSTANCE hModule, WCHAR *lpName, int a4)
{
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v9; // rax
  struct _RLEFILE *v10; // rax
  void *v11; // rbx
  HANDLE v12; // rax
  bool v14; // zf
  _DWORD *v15; // rcx
  int v16; // ebx
  int yBottom; // esi
  struct tagRECT *v18; // r15
  COLORREF Pixel; // r13d
  HDC DC; // rsi
  HDC CompatibleDC; // r14
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v23; // r12
  HGDIOBJ v24; // rbx
  HWND v25; // rcx
  LONG WindowLongW; // ebx
  LONG v27; // eax
  HWND v28; // rcx
  struct tagRECT Rect; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( a4 )
  {
    GetWindowTextW(*(HWND *)this, String, 260);
    lpName = String;
  }
  if ( !hModule )
    hModule = (HINSTANCE)GetWindowLongPtrW(*(HWND *)this, -6);
  CAnimate::OnStop(this);
  if ( *((_QWORD *)this + 4) )
  {
    ((void (*)(void))RleFile_Close)();
    v7 = (void *)*((_QWORD *)this + 4);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
    *((_QWORD *)this + 4) = 0;
  }
  *((_QWORD *)this + 7) = 0;
  if ( !lpName || (unsigned __int64)lpName >= 0x10000 && !*lpName )
    return 0;
  v9 = GetProcessHeap();
  v10 = (struct _RLEFILE *)HeapAlloc(v9, 8u, 0x4B8u);
  *((_QWORD *)this + 4) = v10;
  if ( !v10 )
    return 0;
  if ( !(unsigned int)RleFile_OpenFromResource(v10, hModule, lpName)
    && !(unsigned int)RleFile_OpenFromFile(*((struct _RLEFILE **)this + 4), lpName) )
  {
    RleFile_Close(*((_QWORD *)this + 4));
    v11 = (void *)*((_QWORD *)this + 4);
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
    *((_QWORD *)this + 4) = 0;
    return 0;
  }
  v14 = (*((_BYTE *)this + 96) & 1) == 0;
  v15 = (_DWORD *)*((_QWORD *)this + 4);
  v16 = v15[1];
  yBottom = v15[2];
  *((_DWORD *)this + 15) = *v15;
  *((_DWORD *)this + 16) = v15[3];
  if ( !v14 )
  {
    v16 = MulDiv(v16, *((_DWORD *)this + 22), 96);
    yBottom = MulDiv(yBottom, *((_DWORD *)this + 23), 96);
  }
  v18 = (struct tagRECT *)((char *)this + 40);
  SetRect((LPRECT)((char *)this + 40), 0, 0, v16, yBottom);
  if ( (*((_BYTE *)this + 24) & 2) != 0 && *((_QWORD *)this + 2) )
  {
    Pixel = 0;
    DC = GetDC(*(HWND *)this);
    CompatibleDC = CreateCompatibleDC(DC);
    if ( CompatibleDC )
    {
      CompatibleBitmap = CreateCompatibleBitmap(DC, 1, 1);
      v23 = CompatibleBitmap;
      if ( CompatibleBitmap )
      {
        v24 = SelectObject(CompatibleDC, CompatibleBitmap);
        RleFile_Paint(
          *((struct _RLEFILE **)this + 4),
          CompatibleDC,
          *((_DWORD *)this + 11),
          *((_DWORD *)this + 12) - v18->left,
          *((_DWORD *)this + 13) - *((_DWORD *)this + 11),
          1);
        Pixel = GetPixel(CompatibleDC, 0, 0);
        SelectObject(CompatibleDC, v24);
        DeleteObject(v23);
      }
      DeleteDC(CompatibleDC);
    }
    SendMessageW(*((HWND *)this + 2), 0x138u, (WPARAM)DC, *(_QWORD *)this);
    ReleaseDC(*(HWND *)this, DC);
    *(_DWORD *)(*((_QWORD *)this + 4) + 1184LL) = Pixel;
  }
  v25 = *(HWND *)this;
  if ( (*((_BYTE *)this + 24) & 1) != 0 )
  {
    Rect = 0;
    GetClientRect(v25, &Rect);
    OffsetRect(
      (LPRECT)((char *)this + 40),
      (Rect.right - *((_DWORD *)this + 12)) / 2,
      (Rect.bottom - *((_DWORD *)this + 13)) / 2);
  }
  else
  {
    Rect = *v18;
    WindowLongW = GetWindowLongW(v25, -20);
    v27 = GetWindowLongW(*(HWND *)this, -16);
    AdjustWindowRectEx(&Rect, v27, 0, WindowLongW);
    SetWindowPos(*(HWND *)this, 0, 0, 0, Rect.right - Rect.left, Rect.bottom - Rect.top, 0x16u);
  }
  v28 = *(HWND *)this;
  if ( (*((_BYTE *)this + 24) & 4) != 0 )
    PostMessageW(v28, 0x465u, 0xFFFFFFFFFFFFFFFFuLL, -65536);
  else
    InvalidateRect(v28, 0, 1);
  return 1;
}

```

## disassembly

```asm
0x1800b8bdc  mov     [rsp-8+arg_18], rbx
0x1800b8be1  push    rbp
0x1800b8be2  push    rsi
0x1800b8be3  push    rdi
0x1800b8be4  push    r12
0x1800b8be6  push    r13
0x1800b8be8  push    r14
0x1800b8bea  push    r15
0x1800b8bec  lea     rbp, [rsp-170h]
0x1800b8bf4  sub     rsp, 270h
0x1800b8bfb  mov     rax, cs:__security_cookie
0x1800b8c02  xor     rax, rsp
0x1800b8c05  mov     [rbp+1A0h+var_40], rax
0x1800b8c0c  xor     r12d, r12d
0x1800b8c0f  mov     rsi, r8
0x1800b8c12  mov     r14, rdx
0x1800b8c15  mov     rdi, rcx
0x1800b8c18  test    r9d, r9d
0x1800b8c1b  jz      short loc_1800B8C36
0x1800b8c1d  mov     rcx, [rcx]; hWnd
0x1800b8c20  lea     rdx, [rsp+2A0h+String]; lpString
0x1800b8c25  mov     r8d, 104h; nMaxCount
0x1800b8c2b  call    cs:__imp_GetWindowTextW
0x1800b8c31  lea     rsi, [rsp+2A0h+String]
0x1800b8c36  test    r14, r14
0x1800b8c39  jnz     short loc_1800B8C4B
0x1800b8c3b  mov     rcx, [rdi]; hWnd
0x1800b8c3e  lea     edx, [r14-6]; nIndex
0x1800b8c42  call    cs:__imp_GetWindowLongPtrW
0x1800b8c48  mov     r14, rax
0x1800b8c4b  mov     rcx, rdi; this
0x1800b8c4e  call    ?OnStop@CAnimate@@IEAAHXZ; CAnimate::OnStop(void)
0x1800b8c53  mov     rcx, [rdi+20h]
0x1800b8c57  test    rcx, rcx
0x1800b8c5a  jz      short loc_1800B8C7D
0x1800b8c5c  call    RleFile_Close
0x1800b8c61  mov     rbx, [rdi+20h]
0x1800b8c65  call    cs:__imp_GetProcessHeap
0x1800b8c6b  mov     r8, rbx; lpMem
0x1800b8c6e  xor     edx, edx; dwFlags
0x1800b8c70  mov     rcx, rax; hHeap
0x1800b8c73  call    cs:__imp_HeapFree
0x1800b8c79  mov     [rdi+20h], r12
0x1800b8c7d  mov     [rdi+38h], r12
0x1800b8c81  test    rsi, rsi
0x1800b8c84  jz      short loc_1800B8CFF
0x1800b8c86  cmp     rsi, 10000h
0x1800b8c8d  jb      short loc_1800B8C95
0x1800b8c8f  cmp     [rsi], r12w
0x1800b8c93  jz      short loc_1800B8CFF
0x1800b8c95  call    cs:__imp_GetProcessHeap
0x1800b8c9b  mov     edx, 8; dwFlags
0x1800b8ca0  mov     r8d, 4B8h; dwBytes
0x1800b8ca6  mov     rcx, rax; hHeap
0x1800b8ca9  call    cs:__imp_HeapAlloc
0x1800b8caf  mov     [rdi+20h], rax
0x1800b8cb3  test    rax, rax
0x1800b8cb6  jz      short loc_1800B8CFF
0x1800b8cb8  mov     r8, rsi; lpName
0x1800b8cbb  mov     rdx, r14; hModule
0x1800b8cbe  mov     rcx, rax; struct _RLEFILE *
0x1800b8cc1  call    RleFile_OpenFromResource
0x1800b8cc6  test    eax, eax
0x1800b8cc8  jnz     short loc_1800B8D2B
0x1800b8cca  mov     rcx, [rdi+20h]; struct _RLEFILE *
0x1800b8cce  mov     rdx, rsi; unsigned __int16 *
0x1800b8cd1  call    RleFile_OpenFromFile
0x1800b8cd6  test    eax, eax
0x1800b8cd8  jnz     short loc_1800B8D2B
0x1800b8cda  mov     rcx, [rdi+20h]
0x1800b8cde  call    RleFile_Close
0x1800b8ce3  mov     rbx, [rdi+20h]
0x1800b8ce7  call    cs:__imp_GetProcessHeap
0x1800b8ced  mov     r8, rbx; lpMem
0x1800b8cf0  xor     edx, edx; dwFlags
0x1800b8cf2  mov     rcx, rax; hHeap
0x1800b8cf5  call    cs:__imp_HeapFree
0x1800b8cfb  mov     [rdi+20h], r12
0x1800b8cff  xor     eax, eax
0x1800b8d01  mov     rcx, [rbp+1A0h+var_40]
0x1800b8d08  xor     rcx, rsp; StackCookie
0x1800b8d0b  call    __security_check_cookie
0x1800b8d10  mov     rbx, [rsp+2A0h+arg_18]
0x1800b8d18  add     rsp, 270h
0x1800b8d1f  pop     r15
0x1800b8d21  pop     r14
0x1800b8d23  pop     r13
0x1800b8d25  pop     r12
0x1800b8d27  pop     rdi
0x1800b8d28  pop     rsi
0x1800b8d29  pop     rbp
0x1800b8d2a  retn
0x1800b8d2b  test    byte ptr [rdi+60h], 1
0x1800b8d2f  mov     rcx, [rdi+20h]
0x1800b8d33  mov     eax, [rcx]
0x1800b8d35  mov     ebx, [rcx+4]
0x1800b8d38  mov     esi, [rcx+8]
0x1800b8d3b  mov     [rdi+3Ch], eax
0x1800b8d3e  mov     eax, [rcx+0Ch]
0x1800b8d41  mov     [rdi+40h], eax
0x1800b8d44  jz      short loc_1800B8D6C
0x1800b8d46  mov     edx, [rdi+58h]; nNumerator
0x1800b8d49  mov     r14d, 60h ; '`'
0x1800b8d4f  mov     r8d, r14d; nDenominator
0x1800b8d52  mov     ecx, ebx; nNumber
0x1800b8d54  call    cs:__imp_MulDiv
0x1800b8d5a  mov     edx, [rdi+5Ch]; nNumerator
0x1800b8d5d  mov     r8d, r14d; nDenominator
0x1800b8d60  mov     ecx, esi; nNumber
0x1800b8d62  mov     ebx, eax
0x1800b8d64  call    cs:__imp_MulDiv
0x1800b8d6a  mov     esi, eax
0x1800b8d6c  lea     r15, [rdi+28h]
0x1800b8d70  mov     [rsp+2A0h+yBottom], esi; yBottom
0x1800b8d74  mov     rcx, r15; lprc
0x1800b8d77  mov     r9d, ebx; xRight
0x1800b8d7a  xor     r8d, r8d; yTop
0x1800b8d7d  xor     edx, edx; xLeft
0x1800b8d7f  call    cs:__imp_SetRect
0x1800b8d85  mov     ebx, 2
0x1800b8d8a  test    [rdi+18h], bl
0x1800b8d8d  jz      loc_1800B8E81
0x1800b8d93  cmp     [rdi+10h], r12
0x1800b8d97  jz      loc_1800B8E81
0x1800b8d9d  mov     rcx, [rdi]; hWnd
0x1800b8da0  mov     r13d, r12d
0x1800b8da3  call    cs:__imp_GetDC
0x1800b8da9  mov     rcx, rax; hdc
0x1800b8dac  mov     rsi, rax
0x1800b8daf  call    cs:__imp_CreateCompatibleDC
0x1800b8db5  mov     r14, rax
0x1800b8db8  test    rax, rax
0x1800b8dbb  jz      loc_1800B8E55
0x1800b8dc1  lea     eax, [rbx-1]
0x1800b8dc4  mov     rcx, rsi; hdc
0x1800b8dc7  mov     r8d, eax; cy
0x1800b8dca  mov     edx, eax; cx
0x1800b8dcc  call    cs:__imp_CreateCompatibleBitmap
0x1800b8dd2  mov     r12, rax
0x1800b8dd5  test    rax, rax
0x1800b8dd8  jz      short loc_1800B8E4C
0x1800b8dda  mov     rdx, rax; h
0x1800b8ddd  mov     rcx, r14; hdc
0x1800b8de0  call    cs:__imp_SelectObject
0x1800b8de6  mov     r8d, [rdi+2Ch]
0x1800b8dea  mov     rbx, rax
0x1800b8ded  mov     edx, [rdi+34h]
0x1800b8df0  mov     ecx, [rdi+30h]
0x1800b8df3  sub     edx, r8d
0x1800b8df6  sub     ecx, [r15]
0x1800b8df9  mov     r9d, [r15]
0x1800b8dfc  mov     [rsp+2A0h+var_268], 1; int
0x1800b8e04  mov     [rsp+2A0h+uFlags], edx; hDest
0x1800b8e08  mov     rdx, r14; hdcDest
0x1800b8e0b  mov     [rsp+2A0h+cy], ecx; wDest
0x1800b8e0f  mov     rcx, [rdi+20h]; struct _RLEFILE *
0x1800b8e13  mov     [rsp+2A0h+yBottom], r8d; y
0x1800b8e18  mov     r8d, [rdi+38h]
0x1800b8e1c  call    RleFile_Paint
0x1800b8e21  xor     r8d, r8d; y
0x1800b8e24  xor     edx, edx; x
0x1800b8e26  mov     rcx, r14; hdc
0x1800b8e29  call    cs:__imp_GetPixel
0x1800b8e2f  mov     rdx, rbx; h
0x1800b8e32  mov     rcx, r14; hdc
0x1800b8e35  mov     r13d, eax
0x1800b8e38  call    cs:__imp_SelectObject
0x1800b8e3e  mov     rcx, r12; ho
0x1800b8e41  call    cs:__imp_DeleteObject
0x1800b8e47  mov     ebx, 2
0x1800b8e4c  mov     rcx, r14; hdc
0x1800b8e4f  call    cs:__imp_DeleteDC
0x1800b8e55  mov     r9, [rdi]; lParam
0x1800b8e58  mov     r8, rsi; wParam
0x1800b8e5b  mov     rcx, [rdi+10h]; hWnd
0x1800b8e5f  mov     edx, 138h; Msg
0x1800b8e64  call    cs:__imp_SendMessageW
0x1800b8e6a  mov     rcx, [rdi]; hWnd
0x1800b8e6d  mov     rdx, rsi; hDC
0x1800b8e70  call    cs:__imp_ReleaseDC
0x1800b8e76  mov     rax, [rdi+20h]
0x1800b8e7a  mov     [rax+4A0h], r13d
0x1800b8e81  test    byte ptr [rdi+18h], 1
0x1800b8e85  mov     rcx, [rdi]; hWnd
0x1800b8e88  jz      short loc_1800B8EC1
0x1800b8e8a  xorps   xmm0, xmm0
0x1800b8e8d  lea     rdx, [rsp+2A0h+Rect]; lpRect
0x1800b8e92  movups  xmmword ptr [rsp+2A0h+Rect.left], xmm0
0x1800b8e97  call    cs:__imp_GetClientRect
0x1800b8e9d  mov     eax, [rsp+2A0h+Rect.bottom]
0x1800b8ea1  mov     rcx, r15; lprc
0x1800b8ea4  sub     eax, [rdi+34h]
0x1800b8ea7  cdq
0x1800b8ea8  idiv    ebx
0x1800b8eaa  mov     r8d, eax; dy
0x1800b8ead  mov     eax, [rsp+2A0h+Rect.right]
0x1800b8eb1  sub     eax, [rdi+30h]
0x1800b8eb4  cdq
0x1800b8eb5  idiv    ebx
0x1800b8eb7  mov     edx, eax; dx
0x1800b8eb9  call    cs:__imp_OffsetRect
0x1800b8ebf  jmp     short loc_1800B8F2A
0x1800b8ec1  movups  xmm0, xmmword ptr [r15]
0x1800b8ec5  mov     edx, 0FFFFFFECh; nIndex
0x1800b8eca  movdqu  xmmword ptr [rsp+2A0h+Rect.left], xmm0
0x1800b8ed0  call    cs:__imp_GetWindowLongW
0x1800b8ed6  mov     rcx, [rdi]; hWnd
0x1800b8ed9  mov     edx, 0FFFFFFF0h; nIndex
0x1800b8ede  mov     ebx, eax
0x1800b8ee0  call    cs:__imp_GetWindowLongW
0x1800b8ee6  mov     r9d, ebx; dwExStyle
0x1800b8ee9  lea     rcx, [rsp+2A0h+Rect]; lpRect
0x1800b8eee  mov     edx, eax; dwStyle
0x1800b8ef0  xor     r8d, r8d; bMenu
0x1800b8ef3  call    cs:__imp_AdjustWindowRectEx
0x1800b8ef9  mov     ecx, [rsp+2A0h+Rect.bottom]
0x1800b8efd  xor     r9d, r9d; Y
0x1800b8f00  sub     ecx, [rsp+2A0h+Rect.top]
0x1800b8f04  xor     r8d, r8d; X
0x1800b8f07  mov     eax, [rsp+2A0h+Rect.right]
0x1800b8f0b  xor     edx, edx; hWndInsertAfter
0x1800b8f0d  sub     eax, [rsp+2A0h+Rect.left]
0x1800b8f11  mov     [rsp+2A0h+uFlags], 16h; uFlags
0x1800b8f19  mov     [rsp+2A0h+cy], ecx; cy
0x1800b8f1d  mov     rcx, [rdi]; hWnd
0x1800b8f20  mov     [rsp+2A0h+yBottom], eax; cx
0x1800b8f24  call    cs:__imp_SetWindowPos
0x1800b8f2a  test    byte ptr [rdi+18h], 4
0x1800b8f2e  mov     rcx, [rdi]; hWnd
0x1800b8f31  jz      short loc_1800B8F4B
0x1800b8f33  mov     r9, 0FFFFFFFFFFFF0000h; lParam
0x1800b8f3a  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1800b8f3e  mov     edx, 465h; Msg
0x1800b8f43  call    cs:__imp_PostMessageW
0x1800b8f49  jmp     short loc_1800B8F57
0x1800b8f4b  xor     edx, edx; lpRect
0x1800b8f4d  lea     r8d, [rdx+1]; bErase
0x1800b8f51  call    cs:__imp_InvalidateRect
0x1800b8f57  mov     eax, 1
0x1800b8f5c  jmp     loc_1800B8D01
```
