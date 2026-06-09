# CCDrawNonClientTheme

- ea: `0x1800d70d4`
- end: `0x1800d72d3`
- name: `CCDrawNonClientTheme`
- size: `511`
- prototype: `__int64 __usercall@<rax>(HTHEME hTheme@<rcx>, HWND hWnd@<rdx>, HRGN hrgnSrc1@<r8>, int iPartId, int iStateId, int, int dy)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d900`
- `0x18005fe40`
- `0x18009f150`
- `0x1800d8a60`
- `0x18011bc80`

## callees

- `0x1800d70d4`
- `0x180114520`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800d72a3`
- `GDI32!DeleteObject` at `0x1800d72a3`
- `GDI32!CombineRgn` at `0x1800d71da`
- `GDI32!CombineRgn` at `0x1800d71da`
- `GDI32!ExcludeClipRect` at `0x1800d721e`
- `GDI32!ExcludeClipRect` at `0x1800d721e`
- `GDI32!CreateRectRgn` at `0x1800d71b1`
- `GDI32!CreateRectRgn` at `0x1800d71b1`
- `USER32!GetDCEx` at `0x1800d7125`
- `USER32!GetDCEx` at `0x1800d7125`
- `USER32!FillRect` at `0x1800d7286`
- `USER32!FillRect` at `0x1800d7286`
- `USER32!OffsetRect` at `0x1800d71f0`
- `USER32!OffsetRect` at `0x1800d7203`
- `USER32!OffsetRect` at `0x1800d71f0`
- `USER32!OffsetRect` at `0x1800d7203`
- `USER32!DefWindowProcW` at `0x1800d729a`
- `USER32!DefWindowProcW` at `0x1800d729a`
- `USER32!GetWindowRect` at `0x1800d7187`
- `USER32!GetWindowRect` at `0x1800d7187`
- `USER32!InflateRect` at `0x1800d719d`
- `USER32!InflateRect` at `0x1800d722e`
- `USER32!InflateRect` at `0x1800d7275`
- `USER32!InflateRect` at `0x1800d719d`
- `USER32!InflateRect` at `0x1800d722e`
- `USER32!InflateRect` at `0x1800d7275`
- `USER32!GetSystemMetrics` at `0x1800d7143`
- `USER32!GetSystemMetrics` at `0x1800d7151`
- `USER32!GetSystemMetrics` at `0x1800d7143`
- `USER32!GetSystemMetrics` at `0x1800d7151`
- `USER32!ReleaseDC` at `0x1800d72af`
- `USER32!ReleaseDC` at `0x1800d72af`
- `UxTheme!DrawThemeBackground` at `0x1800d7255`
- `UxTheme!DrawThemeBackground` at `0x1800d7255`
- `UxTheme!GetThemeInt` at `0x1800d7173`
- `UxTheme!GetThemeInt` at `0x1800d7173`

## pseudocode

```c
__int64 __fastcall CCDrawNonClientTheme(
        HTHEME hTheme,
        HWND hWnd,
        HRGN hrgnSrc1,
        HBRUSH a4,
        int iPartId,
        int iStateId,
        int a7,
        int dy)
{
  unsigned int v11; // r12d
  HDC DCEx; // rsi
  int SystemMetrics; // r14d
  HRGN RectRgn; // rax
  HRGN v15; // rdi
  struct tagRECT Rect; // [rsp+40h] [rbp-20h] BYREF
  int piVal; // [rsp+50h] [rbp-10h] BYREF

  v11 = 0;
  DCEx = GetDCEx(hWnd, hrgnSrc1, hrgnSrc1 != 0 ? 328833 : 66561);
  if ( DCEx )
  {
    Rect = 0;
    piVal = GetSystemMetrics(5);
    SystemMetrics = GetSystemMetrics(6);
    if ( GetThemeInt(hTheme, iPartId, iStateId, 1201, &piVal) >= 0 )
      SystemMetrics = piVal;
    GetWindowRect(hWnd, &Rect);
    InflateRect(&Rect, -a7, -dy);
    RectRgn = CreateRectRgn(Rect.left, Rect.top, Rect.right, Rect.bottom);
    v15 = RectRgn;
    v11 = 1;
    if ( RectRgn )
    {
      if ( hrgnSrc1 )
        CombineRgn(RectRgn, hrgnSrc1, RectRgn, 1);
      OffsetRect(&Rect, -Rect.left, -Rect.top);
      OffsetRect(&Rect, a7, dy);
      ExcludeClipRect(DCEx, Rect.left, Rect.top, Rect.right, Rect.bottom);
      InflateRect(&Rect, a7, dy);
      DrawThemeBackground(hTheme, DCEx, iPartId, iStateId, &Rect, 0);
      if ( SystemMetrics < dy && piVal < a7 )
      {
        InflateRect(&Rect, piVal - a7, SystemMetrics - dy);
        FillRect(DCEx, &Rect, a4);
      }
      DefWindowProcW(hWnd, 0x85u, (WPARAM)v15, 0);
      DeleteObject(v15);
    }
    ReleaseDC(hWnd, DCEx);
  }
  return v11;
}

```

## disassembly

```asm
0x1800d70d4  push    rbp
0x1800d70d6  push    rbx
0x1800d70d7  push    rsi
0x1800d70d8  push    rdi
0x1800d70d9  push    r12
0x1800d70db  push    r14
0x1800d70dd  push    r15
0x1800d70df  mov     rbp, rsp
0x1800d70e2  sub     rsp, 60h
0x1800d70e6  mov     rax, cs:__security_cookie
0x1800d70ed  xor     rax, rsp
0x1800d70f0  mov     [rbp+var_8], rax
0x1800d70f4  mov     rax, r8
0x1800d70f7  mov     [rbp+hTheme], rcx
0x1800d70fb  mov     rbx, r8
0x1800d70fe  mov     [rbp+hbr], r9
0x1800d7102  mov     r15, rdx
0x1800d7105  mov     rdi, rcx
0x1800d7108  xor     r12d, r12d
0x1800d710b  mov     rdx, rbx; hrgnClip
0x1800d710e  neg     rax
0x1800d7111  mov     rcx, r15; hWnd
0x1800d7114  sbb     r8d, r8d
0x1800d7117  and     r8d, 40080h
0x1800d711e  add     r8d, 10401h; flags
0x1800d7125  call    cs:__imp_GetDCEx
0x1800d712b  mov     rsi, rax
0x1800d712e  test    rax, rax
0x1800d7131  jz      loc_1800D72B5
0x1800d7137  xorps   xmm0, xmm0
0x1800d713a  lea     ecx, [r12+5]; nIndex
0x1800d713f  movups  xmmword ptr [rbp+Rect.left], xmm0
0x1800d7143  call    cs:__imp_GetSystemMetrics
0x1800d7149  lea     ecx, [r12+6]; nIndex
0x1800d714e  mov     [rbp+var_10], eax
0x1800d7151  call    cs:__imp_GetSystemMetrics
0x1800d7157  mov     r8d, [rbp+iStateId]; iStateId
0x1800d715b  mov     r9d, 4B1h; iPropId
0x1800d7161  mov     edx, [rbp+iPartId]; iPartId
0x1800d7164  mov     r14d, eax
0x1800d7167  lea     rax, [rbp+var_10]
0x1800d716b  mov     rcx, rdi; hTheme
0x1800d716e  mov     [rsp+60h+piVal], rax; piVal
0x1800d7173  call    cs:__imp_GetThemeInt
0x1800d7179  lea     rdx, [rbp+Rect]; lpRect
0x1800d717d  mov     rcx, r15; hWnd
0x1800d7180  test    eax, eax
0x1800d7182  cmovns  r14d, [rbp+var_10]
0x1800d7187  call    cs:__imp_GetWindowRect
0x1800d718d  mov     r8d, [rbp+dy]
0x1800d7191  lea     rcx, [rbp+Rect]; lprc
0x1800d7195  mov     edx, [rbp+arg_30]
0x1800d7198  neg     r8d; dy
0x1800d719b  neg     edx; dx
0x1800d719d  call    cs:__imp_InflateRect
0x1800d71a3  mov     r9d, [rbp+Rect.bottom]; y2
0x1800d71a7  mov     r8d, [rbp+Rect.right]; x2
0x1800d71ab  mov     edx, [rbp+Rect.top]; y1
0x1800d71ae  mov     ecx, [rbp+Rect.left]; x1
0x1800d71b1  call    cs:__imp_CreateRectRgn
0x1800d71b7  mov     rdi, rax
0x1800d71ba  mov     r12d, 1
0x1800d71c0  test    rax, rax
0x1800d71c3  jz      loc_1800D72A9
0x1800d71c9  test    rbx, rbx
0x1800d71cc  jz      short loc_1800D71E0
0x1800d71ce  mov     r9d, r12d; iMode
0x1800d71d1  mov     r8, rax; hrgnSrc2
0x1800d71d4  mov     rdx, rbx; hrgnSrc1
0x1800d71d7  mov     rcx, rax; hrgnDst
0x1800d71da  call    cs:__imp_CombineRgn
0x1800d71e0  mov     r8d, [rbp+Rect.top]
0x1800d71e4  lea     rcx, [rbp+Rect]; lprc
0x1800d71e8  mov     edx, [rbp+Rect.left]
0x1800d71eb  neg     r8d; dy
0x1800d71ee  neg     edx; dx
0x1800d71f0  call    cs:__imp_OffsetRect
0x1800d71f6  mov     ebx, [rbp+arg_30]
0x1800d71f9  lea     rcx, [rbp+Rect]; lprc
0x1800d71fd  mov     r8d, [rbp+dy]; dy
0x1800d7201  mov     edx, ebx; dx
0x1800d7203  call    cs:__imp_OffsetRect
0x1800d7209  mov     eax, [rbp+Rect.bottom]
0x1800d720c  mov     rcx, rsi; hdc
0x1800d720f  mov     r9d, [rbp+Rect.right]; right
0x1800d7213  mov     r8d, [rbp+Rect.top]; top
0x1800d7217  mov     edx, [rbp+Rect.left]; left
0x1800d721a  mov     dword ptr [rsp+60h+piVal], eax; bottom
0x1800d721e  call    cs:__imp_ExcludeClipRect
0x1800d7224  mov     r8d, [rbp+dy]; dy
0x1800d7228  lea     rcx, [rbp+Rect]; lprc
0x1800d722c  mov     edx, ebx; dx
0x1800d722e  call    cs:__imp_InflateRect
0x1800d7234  mov     r9d, [rbp+iStateId]; iStateId
0x1800d7238  lea     rax, [rbp+Rect]
0x1800d723c  mov     r8d, [rbp+iPartId]; iPartId
0x1800d7240  mov     rdx, rsi; hdc
0x1800d7243  mov     rcx, [rbp+hTheme]; hTheme
0x1800d7247  mov     [rsp+60h+pClipRect], 0; pClipRect
0x1800d7250  mov     [rsp+60h+piVal], rax; pRect
0x1800d7255  call    cs:__imp_DrawThemeBackground
0x1800d725b  mov     edx, [rbp+var_10]
0x1800d725e  cmp     r14d, [rbp+dy]
0x1800d7262  jge     short loc_1800D728C
0x1800d7264  cmp     edx, ebx
0x1800d7266  jge     short loc_1800D728C
0x1800d7268  sub     r14d, [rbp+dy]
0x1800d726c  lea     rcx, [rbp+Rect]; lprc
0x1800d7270  mov     r8d, r14d; dy
0x1800d7273  sub     edx, ebx; dx
0x1800d7275  call    cs:__imp_InflateRect
0x1800d727b  mov     r8, [rbp+hbr]; hbr
0x1800d727f  lea     rdx, [rbp+Rect]; lprc
0x1800d7283  mov     rcx, rsi; hDC
0x1800d7286  call    cs:__imp_FillRect
0x1800d728c  xor     r9d, r9d; lParam
0x1800d728f  mov     r8, rdi; wParam
0x1800d7292  mov     edx, 85h; Msg
0x1800d7297  mov     rcx, r15; hWnd
0x1800d729a  call    cs:__imp_DefWindowProcW
0x1800d72a0  mov     rcx, rdi; ho
0x1800d72a3  call    cs:__imp_DeleteObject
0x1800d72a9  mov     rdx, rsi; hDC
0x1800d72ac  mov     rcx, r15; hWnd
0x1800d72af  call    cs:__imp_ReleaseDC
0x1800d72b5  mov     eax, r12d
0x1800d72b8  mov     rcx, [rbp+var_8]
0x1800d72bc  xor     rcx, rsp; StackCookie
0x1800d72bf  call    __security_check_cookie
0x1800d72c4  add     rsp, 60h
0x1800d72c8  pop     r15
0x1800d72ca  pop     r14
0x1800d72cc  pop     r12
0x1800d72ce  pop     rdi
0x1800d72cf  pop     rsi
0x1800d72d0  pop     rbx
0x1800d72d1  pop     rbp
0x1800d72d2  retn
```
