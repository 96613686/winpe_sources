# BitmapMCI

- ea: `0x18000f704`
- end: `0x18000f8e3`
- name: `BitmapMCI`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010578`

## callees

- `0x1800014b0`
- `0x18000f704`
- `0x1800127bc`

## import_xrefs

- `GDI32!DeleteObject` at `0x18000f84a`
- `GDI32!DeleteObject` at `0x18000f84a`
- `GDI32!DeleteDC` at `0x18000f8b5`
- `GDI32!DeleteDC` at `0x18000f8b5`
- `GDI32!CreateCompatibleDC` at `0x18000f7a4`
- `GDI32!CreateCompatibleDC` at `0x18000f7a4`
- `GDI32!SelectObject` at `0x18000f7ec`
- `GDI32!SelectObject` at `0x18000f811`
- `GDI32!SelectObject` at `0x18000f841`
- `GDI32!SelectObject` at `0x18000f8ac`
- `GDI32!SelectObject` at `0x18000f7ec`
- `GDI32!SelectObject` at `0x18000f811`
- `GDI32!SelectObject` at `0x18000f841`
- `GDI32!SelectObject` at `0x18000f8ac`
- `GDI32!CreateCompatibleBitmap` at `0x18000f7c9`
- `GDI32!CreateCompatibleBitmap` at `0x18000f7c9`
- `GDI32!PatBlt` at `0x18000f835`
- `GDI32!PatBlt` at `0x18000f835`
- `GDI32!CreateSolidBrush` at `0x18000f802`
- `GDI32!CreateSolidBrush` at `0x18000f802`
- `USER32!GetDC` at `0x18000f78d`
- `USER32!GetDC` at `0x18000f78d`
- `USER32!ReleaseDC` at `0x18000f7b7`
- `USER32!ReleaseDC` at `0x18000f7d7`
- `USER32!ReleaseDC` at `0x18000f7b7`
- `USER32!ReleaseDC` at `0x18000f7d7`
- `USER32!GetSystemMetrics` at `0x18000f73a`
- `USER32!GetSystemMetrics` at `0x18000f747`
- `USER32!GetSystemMetrics` at `0x18000f73a`
- `USER32!GetSystemMetrics` at `0x18000f747`
- `USER32!SetRect` at `0x18000f785`
- `USER32!SetRect` at `0x18000f785`
- `USER32!GetSysColor` at `0x18000f7fa`
- `USER32!GetSysColor` at `0x18000f7fa`
- `USER32!DrawIcon` at `0x18000f89b`
- `USER32!DrawIcon` at `0x18000f89b`
- `WINMM!mciSendCommandW` at `0x18000f882`
- `WINMM!mciSendCommandW` at `0x18000f882`

## pseudocode

```c
HBITMAP __fastcall BitmapMCI(__int64 a1)
{
  int SystemMetrics; // edi
  int v3; // ebx
  int yBottom; // ecx
  int v5; // r9d
  HDC DC; // rbx
  HDC CompatibleDC; // rsi
  HBITMAP CompatibleBitmap; // r14
  HGDIOBJ v10; // r12
  DWORD SysColor; // eax
  HBRUSH SolidBrush; // rdi
  HGDIOBJ v13; // rbx
  MCIDEVICEID v14; // ecx
  struct tagRECT rc; // [rsp+30h] [rbp-40h] BYREF
  DWORD_PTR dwParam2; // [rsp+40h] [rbp-30h] BYREF
  __int128 v17; // [rsp+48h] [rbp-28h]
  HDC v18; // [rsp+58h] [rbp-18h]

  rc = 0;
  SystemMetrics = GetSystemMetrics(11);
  v3 = GetSystemMetrics(12);
  MCIWndRect(a1, &rc, 0);
  yBottom = rc.bottom - rc.top;
  if ( v3 > rc.bottom - rc.top )
    yBottom = v3;
  v5 = rc.right - rc.left;
  if ( SystemMetrics > rc.right - rc.left )
    v5 = SystemMetrics;
  SetRect(&rc, 0, 0, v5, yBottom);
  DC = GetDC(0);
  if ( !DC )
    return 0;
  CompatibleDC = CreateCompatibleDC(0);
  if ( !CompatibleDC )
  {
    ReleaseDC(0, DC);
    return 0;
  }
  CompatibleBitmap = CreateCompatibleBitmap(DC, rc.right, rc.bottom);
  ReleaseDC(0, DC);
  if ( CompatibleBitmap )
  {
    v10 = SelectObject(CompatibleDC, CompatibleBitmap);
    SysColor = GetSysColor(5);
    SolidBrush = CreateSolidBrush(SysColor);
    v13 = SelectObject(CompatibleDC, SolidBrush);
    PatBlt(CompatibleDC, 0, 0, rc.right, rc.bottom, 0xF00021u);
    SelectObject(CompatibleDC, v13);
    DeleteObject(SolidBrush);
    v14 = *(_DWORD *)(a1 + 20);
    if ( v14 && *(_DWORD *)(a1 + 60) )
    {
      dwParam2 = 0;
      v18 = CompatibleDC;
      v17 = 0;
      mciSendCommandW(v14, 0x854u, 0x20002u, (DWORD_PTR)&dwParam2);
    }
    else
    {
      DrawIcon(CompatibleDC, rc.left, rc.top, *(HICON *)(a1 + 936));
    }
    if ( v10 )
      SelectObject(CompatibleDC, v10);
  }
  DeleteDC(CompatibleDC);
  return CompatibleBitmap;
}

```

## disassembly

```asm
0x18000f704  mov     [rsp-28h+arg_8], rbx
0x18000f709  mov     [rsp-28h+arg_10], rsi
0x18000f70e  push    rbp
0x18000f70f  push    rdi
0x18000f710  push    r12
0x18000f712  push    r14
0x18000f714  push    r15
0x18000f716  mov     rbp, rsp
0x18000f719  sub     rsp, 70h
0x18000f71d  mov     rax, cs:__security_cookie
0x18000f724  xor     rax, rsp
0x18000f727  mov     [rbp+var_10], rax
0x18000f72b  mov     r15, rcx
0x18000f72e  xorps   xmm0, xmm0
0x18000f731  mov     ecx, 0Bh; nIndex
0x18000f736  movups  xmmword ptr [rbp+rc.left], xmm0
0x18000f73a  call    cs:__imp_GetSystemMetrics
0x18000f740  mov     ecx, 0Ch; nIndex
0x18000f745  mov     edi, eax
0x18000f747  call    cs:__imp_GetSystemMetrics
0x18000f74d  xor     r8d, r8d
0x18000f750  lea     rdx, [rbp+rc]
0x18000f754  mov     rcx, r15
0x18000f757  mov     ebx, eax
0x18000f759  call    MCIWndRect
0x18000f75e  mov     ecx, [rbp+rc.bottom]
0x18000f761  sub     ecx, [rbp+rc.top]
0x18000f764  mov     r9d, [rbp+rc.right]
0x18000f768  cmp     ebx, ecx
0x18000f76a  cmovg   ecx, ebx
0x18000f76d  sub     r9d, [rbp+rc.left]
0x18000f771  cmp     edi, r9d
0x18000f774  mov     [rsp+70h+yBottom], ecx; yBottom
0x18000f778  lea     rcx, [rbp+rc]; lprc
0x18000f77c  cmovg   r9d, edi; xRight
0x18000f780  xor     r8d, r8d; yTop
0x18000f783  xor     edx, edx; xLeft
0x18000f785  call    cs:__imp_SetRect
0x18000f78b  xor     ecx, ecx; hWnd
0x18000f78d  call    cs:__imp_GetDC
0x18000f793  mov     rbx, rax
0x18000f796  test    rax, rax
0x18000f799  jnz     short loc_18000F7A2
0x18000f79b  xor     eax, eax
0x18000f79d  jmp     loc_18000F8BE
0x18000f7a2  xor     ecx, ecx; hdc
0x18000f7a4  call    cs:__imp_CreateCompatibleDC
0x18000f7aa  mov     rsi, rax
0x18000f7ad  test    rax, rax
0x18000f7b0  jnz     short loc_18000F7BF
0x18000f7b2  mov     rdx, rbx; hDC
0x18000f7b5  xor     ecx, ecx; hWnd
0x18000f7b7  call    cs:__imp_ReleaseDC
0x18000f7bd  jmp     short loc_18000F79B
0x18000f7bf  mov     r8d, [rbp+rc.bottom]; cy
0x18000f7c3  mov     rcx, rbx; hdc
0x18000f7c6  mov     edx, [rbp+rc.right]; cx
0x18000f7c9  call    cs:__imp_CreateCompatibleBitmap
0x18000f7cf  mov     rdx, rbx; hDC
0x18000f7d2  xor     ecx, ecx; hWnd
0x18000f7d4  mov     r14, rax
0x18000f7d7  call    cs:__imp_ReleaseDC
0x18000f7dd  test    r14, r14
0x18000f7e0  jz      loc_18000F8B2
0x18000f7e6  mov     rdx, r14; h
0x18000f7e9  mov     rcx, rsi; hdc
0x18000f7ec  call    cs:__imp_SelectObject
0x18000f7f2  mov     ecx, 5; nIndex
0x18000f7f7  mov     r12, rax
0x18000f7fa  call    cs:__imp_GetSysColor
0x18000f800  mov     ecx, eax; color
0x18000f802  call    cs:__imp_CreateSolidBrush
0x18000f808  mov     rdx, rax; h
0x18000f80b  mov     rcx, rsi; hdc
0x18000f80e  mov     rdi, rax
0x18000f811  call    cs:__imp_SelectObject
0x18000f817  mov     ecx, [rbp+rc.bottom]
0x18000f81a  xor     r8d, r8d; y
0x18000f81d  mov     r9d, [rbp+rc.right]; w
0x18000f821  xor     edx, edx; x
0x18000f823  mov     [rsp+70h+rop], 0F00021h; rop
0x18000f82b  mov     rbx, rax
0x18000f82e  mov     [rsp+70h+yBottom], ecx; h
0x18000f832  mov     rcx, rsi; hdc
0x18000f835  call    cs:__imp_PatBlt
0x18000f83b  mov     rdx, rbx; h
0x18000f83e  mov     rcx, rsi; hdc
0x18000f841  call    cs:__imp_SelectObject
0x18000f847  mov     rcx, rdi; ho
0x18000f84a  call    cs:__imp_DeleteObject
0x18000f850  mov     ecx, [r15+14h]; mciId
0x18000f854  test    ecx, ecx
0x18000f856  jz      short loc_18000F88A
0x18000f858  cmp     dword ptr [r15+3Ch], 0
0x18000f85d  jz      short loc_18000F88A
0x18000f85f  xorps   xmm0, xmm0
0x18000f862  mov     [rbp+dwParam2], 0
0x18000f86a  lea     r9, [rbp+dwParam2]; dwParam2
0x18000f86e  mov     [rbp+var_18], rsi
0x18000f872  mov     edx, 854h; uMsg
0x18000f877  mov     r8d, 20002h; dwParam1
0x18000f87d  movdqu  [rbp+var_28], xmm0
0x18000f882  call    cs:__imp_mciSendCommandW
0x18000f888  jmp     short loc_18000F8A1
0x18000f88a  mov     r9, [r15+3A8h]; hIcon
0x18000f891  mov     rcx, rsi; hDC
0x18000f894  mov     r8d, [rbp+rc.top]; Y
0x18000f898  mov     edx, [rbp+rc.left]; X
0x18000f89b  call    cs:__imp_DrawIcon
0x18000f8a1  test    r12, r12
0x18000f8a4  jz      short loc_18000F8B2
0x18000f8a6  mov     rdx, r12; h
0x18000f8a9  mov     rcx, rsi; hdc
0x18000f8ac  call    cs:__imp_SelectObject
0x18000f8b2  mov     rcx, rsi; hdc
0x18000f8b5  call    cs:__imp_DeleteDC
0x18000f8bb  mov     rax, r14
0x18000f8be  mov     rcx, [rbp+var_10]
0x18000f8c2  xor     rcx, rsp; StackCookie
0x18000f8c5  call    __security_check_cookie
0x18000f8ca  lea     r11, [rsp+70h+var_s0]
0x18000f8cf  mov     rbx, [r11+38h]
0x18000f8d3  mov     rsi, [r11+40h]
0x18000f8d7  mov     rsp, r11
0x18000f8da  pop     r15
0x18000f8dc  pop     r14
0x18000f8de  pop     r12
0x18000f8e0  pop     rdi
0x18000f8e1  pop     rbp
0x18000f8e2  retn
```
