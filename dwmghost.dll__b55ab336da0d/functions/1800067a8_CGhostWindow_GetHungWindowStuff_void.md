# CGhostWindow::GetHungWindowStuff(void)

- ea: `0x1800067a8`
- end: `0x180006ba3`
- name: `?GetHungWindowStuff@CGhostWindow@@AEAAHXZ`
- size: `1019`
- prototype: `__int64 __fastcall(CGhostWindow *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800061fc`

## callees

- `0x180001190`
- `0x1800067a8`
- `0x18000a0b4`
- `0x18000a374`
- `0x18000a468`
- `0x18000a4b8`

## import_xrefs

- `USER32!GetUpdateRgn` at `0x1800069b1`
- `USER32!GetUpdateRgn` at `0x1800069b1`
- `USER32!OffsetRect` at `0x180006a91`
- `USER32!OffsetRect` at `0x180006a91`
- `USER32!InternalGetWindowIcon` at `0x180006b27`
- `USER32!InternalGetWindowIcon` at `0x180006b59`
- `USER32!InternalGetWindowIcon` at `0x180006b27`
- `USER32!InternalGetWindowIcon` at `0x180006b59`
- `USER32!GetDCEx` at `0x1800068fd`
- `USER32!GetDCEx` at `0x1800068fd`
- `USER32!ReleaseDC` at `0x180006afe`
- `USER32!ReleaseDC` at `0x180006afe`
- `GDI32!BitBlt` at `0x180006acb`
- `GDI32!BitBlt` at `0x180006acb`
- `GDI32!SelectObject` at `0x180006a21`
- `GDI32!SelectObject` at `0x180006ada`
- `GDI32!SelectObject` at `0x180006a21`
- `GDI32!SelectObject` at `0x180006ada`
- `GDI32!CreateCompatibleDC` at `0x180006a05`
- `GDI32!CreateCompatibleDC` at `0x180006a05`
- `GDI32!OffsetRgn` at `0x180006984`
- `GDI32!OffsetRgn` at `0x1800069cd`
- `GDI32!OffsetRgn` at `0x180006a6f`
- `GDI32!OffsetRgn` at `0x180006984`
- `GDI32!OffsetRgn` at `0x1800069cd`
- `GDI32!OffsetRgn` at `0x180006a6f`
- `GDI32!CreateRectRgn` at `0x180006934`
- `GDI32!CreateRectRgn` at `0x180006994`
- `GDI32!CreateRectRgn` at `0x180006934`
- `GDI32!CreateRectRgn` at `0x180006994`
- `GDI32!DeleteDC` at `0x180006ae3`
- `GDI32!DeleteDC` at `0x180006ae3`
- `GDI32!SelectClipRgn` at `0x180006a7b`
- `GDI32!SelectClipRgn` at `0x180006a7b`
- `GDI32!DeleteObject` at `0x1800069f3`
- `GDI32!DeleteObject` at `0x180006af1`
- `GDI32!DeleteObject` at `0x180006b10`
- `GDI32!DeleteObject` at `0x1800069f3`
- `GDI32!DeleteObject` at `0x180006af1`
- `GDI32!DeleteObject` at `0x180006b10`
- `GDI32!GetRandomRgn` at `0x180006951`
- `GDI32!GetRandomRgn` at `0x180006951`
- `GDI32!CombineRgn` at `0x1800069e1`
- `GDI32!CombineRgn` at `0x1800069e1`
- `GDI32!GetRgnBox` at `0x180006966`
- `GDI32!GetRgnBox` at `0x180006966`
- `ext-ms-win-ntuser-gui-l1-1-1!GetSysColorBrush` at `0x180006a4a`
- `ext-ms-win-ntuser-gui-l1-1-1!GetSysColorBrush` at `0x180006a4a`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x180006a5a`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x180006a5a`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180006b4a`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180006b7a`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180006b4a`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180006b7a`
- `ext-ms-win-ntuser-window-l1-1-0!IsIconic` at `0x180006883`
- `ext-ms-win-ntuser-window-l1-1-0!IsIconic` at `0x180006883`
- `dwmapi!DwmIsCompositionEnabled` at `0x1800067fb`
- `dwmapi!DwmIsCompositionEnabled` at `0x1800067fb`
- `dwmapi!DwmUpdateThumbnailProperties` at `0x18000685d`
- `dwmapi!DwmUpdateThumbnailProperties` at `0x18000685d`
- `dwmapi!__imp_DwmpRegisterThumbnail` at `0x18000682b`
- `dwmapi!__imp_DwmpRegisterThumbnail` at `0x18000682b`

## pseudocode

```c
__int64 __fastcall CGhostWindow::GetHungWindowStuff(CGhostWindow *this)
{
  int started; // eax
  __int64 v3; // rcx
  void *v4; // rcx
  unsigned int v5; // r15d
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // edx
  __int64 AlphaBitmap; // rax
  int v11; // r12d
  HWND v12; // rcx
  HDC hdcSrc; // r14
  HRGN v14; // rdi
  HRGN RectRgn; // rax
  HRGN v16; // rax
  HRGN v17; // rsi
  BOOL v18; // r13d
  HDC CompatibleDC; // rax
  HDC v20; // rsi
  HGDIOBJ v21; // r13
  HBRUSH SysColorBrush; // rax
  LPARAM WindowIcon; // rax
  LPARAM v24; // rax
  BOOL pfEnabled; // [rsp+50h] [rbp-49h] BYREF
  struct tagRECT x1; // [rsp+58h] [rbp-41h] BYREF
  struct tagRECT rc; // [rsp+68h] [rbp-31h] BYREF
  DWM_THUMBNAIL_PROPERTIES ptnProperties; // [rsp+78h] [rbp-21h] BYREF

  pfEnabled = 0;
  started = IsStartButtonWindow(*((HWND *)this + 5));
  v3 = *((_QWORD *)this + 5);
  *((_DWORD *)this + 51) = started;
  *((_DWORD *)this + 52) = IsTrayWindow(v3);
  DwmIsCompositionEnabled(&pfEnabled);
  if ( !pfEnabled
    || *((_DWORD *)this + 51)
    || (int)DwmpRegisterThumbnail(*((_QWORD *)this + 6), *((_QWORD *)this + 5), 1) < 0
    || (v4 = (void *)*((_QWORD *)this + 18),
        memset(&ptnProperties.rcDestination.bottom, 0, 29),
        ptnProperties.opacity = -1,
        *(_OWORD *)&ptnProperties.dwFlags = 0,
        ptnProperties.fVisible = 1,
        ptnProperties.dwFlags = 12,
        DwmUpdateThumbnailProperties(v4, &ptnProperties) < 0) )
  {
    v5 = 0;
    if ( !IsIconic(*((HWND *)this + 5)) )
    {
      v6 = *((unsigned int *)this + 28);
      v7 = *((unsigned int *)this + 27);
      v8 = *((_QWORD *)this + 5);
      x1 = 0;
      if ( (unsigned int)GetExtendedClientRect(v8, v7, v6, &x1) )
      {
        v9 = x1.bottom - x1.top;
        *((_DWORD *)this + 43) = x1.right - x1.left;
        *((_DWORD *)this + 44) = v9;
        AlphaBitmap = CreateAlphaBitmap();
        *((_QWORD *)this + 17) = AlphaBitmap;
        if ( AlphaBitmap )
        {
          v11 = *((_DWORD *)this + 51);
          v12 = v11 ? 0LL : (HWND)*((_QWORD *)this + 5);
          hdcSrc = GetDCEx(v12, 0, 0x10001u);
          if ( !hdcSrc )
            goto LABEL_31;
          v14 = 0;
          rc = 0;
          if ( !pfEnabled && !v11 )
          {
            RectRgn = CreateRectRgn(0, 0, 0, 0);
            v14 = RectRgn;
            if ( RectRgn )
            {
              if ( !GetRandomRgn(hdcSrc, RectRgn, 4) || GetRgnBox(v14, &rc) == 1 )
                goto LABEL_29;
              OffsetRgn(v14, -*((_DWORD *)this + 19), -*((_DWORD *)this + 20));
              v16 = CreateRectRgn(0, 0, 0, 0);
              v17 = v16;
              if ( v16 )
              {
                v18 = 1;
                if ( GetUpdateRgn(*((HWND *)this + 5), v16, 0) != 1 )
                {
                  OffsetRgn(
                    v17,
                    *((_DWORD *)this + 23) - *((_DWORD *)this + 19),
                    *((_DWORD *)this + 24) - *((_DWORD *)this + 20));
                  v18 = CombineRgn(v14, v14, v17, 4) != 1;
                }
                DeleteObject(v17);
                if ( !v18 )
                  goto LABEL_29;
              }
            }
          }
          CompatibleDC = CreateCompatibleDC(hdcSrc);
          v20 = CompatibleDC;
          if ( CompatibleDC )
          {
            v21 = SelectObject(CompatibleDC, *((HGDIOBJ *)this + 17));
            if ( v14 )
            {
              rc.right = *((_DWORD *)this + 43);
              rc.bottom = *((_DWORD *)this + 44);
              *(_QWORD *)&rc.left = 0;
              SysColorBrush = GetSysColorBrush(5);
              FillRect(v20, &rc, SysColorBrush);
              OffsetRgn(v14, -x1.left, -x1.top);
              SelectClipRgn(v20, v14);
            }
            if ( v11 )
              OffsetRect(&x1, *((_DWORD *)this + 19), *((_DWORD *)this + 20));
            v5 = BitBlt(v20, 0, 0, *((_DWORD *)this + 43), *((_DWORD *)this + 44), hdcSrc, x1.left, x1.top, 0x40CC0020u);
            SelectObject(v20, v21);
            DeleteDC(v20);
          }
          if ( v14 )
LABEL_29:
            DeleteObject(v14);
          ReleaseDC(*((HWND *)this + 5), hdcSrc);
          if ( !v5 )
          {
LABEL_31:
            DeleteObject(*((HGDIOBJ *)this + 17));
            *((_QWORD *)this + 17) = 0;
          }
        }
      }
    }
  }
  else
  {
    *((_DWORD *)this + 38) = 1;
    v5 = 1;
  }
  WindowIcon = InternalGetWindowIcon(*((_QWORD *)this + 5), 0);
  *((_QWORD *)this + 23) = WindowIcon;
  if ( WindowIcon )
    SendMessageW(*((HWND *)this + 6), 0x80u, 0, WindowIcon);
  v24 = InternalGetWindowIcon(*((_QWORD *)this + 5), 1);
  *((_QWORD *)this + 24) = v24;
  if ( v24 )
    SendMessageW(*((HWND *)this + 6), 0x80u, 1u, v24);
  return v5;
}

```

## disassembly

```asm
0x1800067a8  push    rbp
0x1800067aa  push    rbx
0x1800067ab  push    rsi
0x1800067ac  push    rdi
0x1800067ad  push    r12
0x1800067af  push    r13
0x1800067b1  push    r14
0x1800067b3  push    r15
0x1800067b5  lea     rbp, [rsp-1Fh]
0x1800067ba  sub     rsp, 0B8h
0x1800067c1  mov     rax, cs:__security_cookie
0x1800067c8  xor     rax, rsp
0x1800067cb  mov     [rbp+57h+var_48], rax
0x1800067cf  mov     rbx, rcx
0x1800067d2  mov     [rbp+57h+pfEnabled], 0
0x1800067d9  mov     rcx, [rcx+28h]; hWnd
0x1800067dd  call    IsStartButtonWindow
0x1800067e2  mov     rcx, [rbx+28h]
0x1800067e6  mov     [rbx+0CCh], eax
0x1800067ec  call    IsTrayWindow
0x1800067f1  lea     rcx, [rbp+57h+pfEnabled]; pfEnabled
0x1800067f5  mov     [rbx+0D0h], eax
0x1800067fb  call    cs:__imp_DwmIsCompositionEnabled
0x180006801  cmp     [rbp+57h+pfEnabled], 0
0x180006805  jz      short loc_18000687C
0x180006807  cmp     dword ptr [rbx+0CCh], 0
0x18000680e  jnz     short loc_18000687C
0x180006810  mov     rdx, [rbx+28h]
0x180006814  lea     rdi, [rbx+90h]
0x18000681b  mov     rcx, [rbx+30h]
0x18000681f  xor     r9d, r9d
0x180006822  mov     qword ptr [rsp+0F0h+cy], rdi
0x180006827  lea     r8d, [r9+1]
0x18000682b  call    cs:__imp_DwmpRegisterThumbnail
0x180006831  test    eax, eax
0x180006833  js      short loc_18000687C
0x180006835  mov     rcx, [rdi]; hThumbnailId
0x180006838  lea     rdx, [rbp+57h+ptnProperties]; ptnProperties
0x18000683c  xorps   xmm0, xmm0
0x18000683f  movups  xmmword ptr [rbp+57h+ptnProperties.rcDestination.bottom], xmm0
0x180006843  movups  xmmword ptr [rbp+57h+ptnProperties.rcSource.right+1], xmm0
0x180006847  mov     [rbp+57h+ptnProperties.opacity], 0FFh
0x18000684b  movups  xmmword ptr [rbp+57h+ptnProperties.dwFlags], xmm0
0x18000684f  mov     [rbp+57h+ptnProperties.fVisible], 1
0x180006856  mov     [rbp+57h+ptnProperties.dwFlags], 0Ch
0x18000685d  call    cs:__imp_DwmUpdateThumbnailProperties
0x180006863  test    eax, eax
0x180006865  js      short loc_18000687C
0x180006867  mov     dword ptr [rbx+98h], 1
0x180006871  mov     r15d, 1
0x180006877  jmp     loc_180006B21
0x18000687c  mov     rcx, [rbx+28h]; hWnd
0x180006880  xor     r15d, r15d
0x180006883  call    cs:__imp_IsIconic
0x180006889  test    eax, eax
0x18000688b  jnz     loc_180006B21
0x180006891  mov     r8d, [rbx+70h]
0x180006895  lea     r9, [rbp+57h+var_98]
0x180006899  mov     edx, [rbx+6Ch]
0x18000689c  xorps   xmm0, xmm0
0x18000689f  mov     rcx, [rbx+28h]
0x1800068a3  movups  xmmword ptr [rbp+57h+var_98.left], xmm0
0x1800068a7  call    GetExtendedClientRect
0x1800068ac  test    eax, eax
0x1800068ae  jz      loc_180006B21
0x1800068b4  mov     ecx, [rbp+57h+var_98.right]
0x1800068b7  mov     edx, [rbp+57h+var_98.bottom]
0x1800068ba  sub     ecx, [rbp+57h+var_98.left]
0x1800068bd  sub     edx, [rbp+57h+var_98.top]
0x1800068c0  mov     [rbx+0ACh], ecx
0x1800068c6  mov     [rbx+0B0h], edx
0x1800068cc  call    CreateAlphaBitmap
0x1800068d1  mov     [rbx+88h], rax
0x1800068d8  test    rax, rax
0x1800068db  jz      loc_180006B21
0x1800068e1  mov     r12d, [rbx+0CCh]
0x1800068e8  test    r12d, r12d
0x1800068eb  jz      short loc_1800068F1
0x1800068ed  xor     ecx, ecx
0x1800068ef  jmp     short loc_1800068F5
0x1800068f1  mov     rcx, [rbx+28h]; hWnd
0x1800068f5  xor     edx, edx; hrgnClip
0x1800068f7  mov     r8d, 10001h; flags
0x1800068fd  call    cs:__imp_GetDCEx
0x180006903  mov     r14, rax
0x180006906  test    rax, rax
0x180006909  jz      loc_180006B09
0x18000690f  xor     edi, edi
0x180006911  xorps   xmm0, xmm0
0x180006914  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x180006918  cmp     [rbp+57h+pfEnabled], edi
0x18000691b  jnz     loc_180006A02
0x180006921  test    r12d, r12d
0x180006924  jnz     loc_180006A02
0x18000692a  xor     r9d, r9d; y2
0x18000692d  xor     r8d, r8d; x2
0x180006930  xor     edx, edx; y1
0x180006932  xor     ecx, ecx; x1
0x180006934  call    cs:__imp_CreateRectRgn
0x18000693a  mov     rdi, rax
0x18000693d  test    rax, rax
0x180006940  jz      loc_180006A02
0x180006946  lea     r8d, [r12+4]; i
0x18000694b  mov     rdx, rax; hrgn
0x18000694e  mov     rcx, r14; hdc
0x180006951  call    cs:__imp_GetRandomRgn
0x180006957  test    eax, eax
0x180006959  jz      loc_180006AEE
0x18000695f  lea     rdx, [rbp+57h+rc]; lprc
0x180006963  mov     rcx, rdi; hrgn
0x180006966  call    cs:__imp_GetRgnBox
0x18000696c  cmp     eax, 1
0x18000696f  jz      loc_180006AEE
0x180006975  mov     r8d, [rbx+50h]
0x180006979  mov     rcx, rdi; hrgn
0x18000697c  mov     edx, [rbx+4Ch]
0x18000697f  neg     r8d; y
0x180006982  neg     edx; x
0x180006984  call    cs:__imp_OffsetRgn
0x18000698a  xor     r9d, r9d; y2
0x18000698d  xor     r8d, r8d; x2
0x180006990  xor     edx, edx; y1
0x180006992  xor     ecx, ecx; x1
0x180006994  call    cs:__imp_CreateRectRgn
0x18000699a  mov     rsi, rax
0x18000699d  test    rax, rax
0x1800069a0  jz      short loc_180006A02
0x1800069a2  mov     rcx, [rbx+28h]; hWnd
0x1800069a6  lea     r13d, [r12+1]
0x1800069ab  xor     r8d, r8d; bErase
0x1800069ae  mov     rdx, rax; hRgn
0x1800069b1  call    cs:__imp_GetUpdateRgn
0x1800069b7  cmp     eax, r13d
0x1800069ba  jz      short loc_1800069F0
0x1800069bc  mov     r8d, [rbx+60h]
0x1800069c0  mov     rcx, rsi; hrgn
0x1800069c3  mov     edx, [rbx+5Ch]
0x1800069c6  sub     r8d, [rbx+50h]; y
0x1800069ca  sub     edx, [rbx+4Ch]; x
0x1800069cd  call    cs:__imp_OffsetRgn
0x1800069d3  lea     r9d, [r12+4]; iMode
0x1800069d8  mov     r8, rsi; hrgnSrc2
0x1800069db  mov     rdx, rdi; hrgnSrc1
0x1800069de  mov     rcx, rdi; hrgnDst
0x1800069e1  call    cs:__imp_CombineRgn
0x1800069e7  xor     ecx, ecx
0x1800069e9  cmp     eax, r13d
0x1800069ec  cmovz   r13d, ecx
0x1800069f0  mov     rcx, rsi; ho
0x1800069f3  call    cs:__imp_DeleteObject
0x1800069f9  test    r13d, r13d
0x1800069fc  jz      loc_180006AEE
0x180006a02  mov     rcx, r14; hdc
0x180006a05  call    cs:__imp_CreateCompatibleDC
0x180006a0b  mov     rsi, rax
0x180006a0e  test    rax, rax
0x180006a11  jz      loc_180006AE9
0x180006a17  mov     rdx, [rbx+88h]; h
0x180006a1e  mov     rcx, rax; hdc
0x180006a21  call    cs:__imp_SelectObject
0x180006a27  mov     r13, rax
0x180006a2a  test    rdi, rdi
0x180006a2d  jz      short loc_180006A81
0x180006a2f  mov     ecx, [rbx+0ACh]
0x180006a35  mov     [rbp+57h+rc.right], ecx
0x180006a38  mov     ecx, [rbx+0B0h]
0x180006a3e  mov     [rbp+57h+rc.bottom], ecx
0x180006a41  mov     ecx, 5; nIndex
0x180006a46  mov     qword ptr [rbp+57h+rc.left], r15
0x180006a4a  call    cs:__imp_GetSysColorBrush
0x180006a50  lea     rdx, [rbp+57h+rc]; lprc
0x180006a54  mov     rcx, rsi; hDC
0x180006a57  mov     r8, rax; hbr
0x180006a5a  call    cs:__imp_FillRect
0x180006a60  mov     r8d, [rbp+57h+var_98.top]
0x180006a64  mov     rcx, rdi; hrgn
0x180006a67  mov     edx, [rbp+57h+var_98.left]
0x180006a6a  neg     r8d; y
0x180006a6d  neg     edx; x
0x180006a6f  call    cs:__imp_OffsetRgn
0x180006a75  mov     rdx, rdi; hrgn
0x180006a78  mov     rcx, rsi; hdc
0x180006a7b  call    cs:__imp_SelectClipRgn
0x180006a81  test    r12d, r12d
0x180006a84  jz      short loc_180006A97
0x180006a86  mov     r8d, [rbx+50h]; dy
0x180006a8a  lea     rcx, [rbp+57h+var_98]; lprc
0x180006a8e  mov     edx, [rbx+4Ch]; dx
0x180006a91  call    cs:__imp_OffsetRect
0x180006a97  mov     eax, [rbp+57h+var_98.top]
0x180006a9a  xor     r8d, r8d; y
0x180006a9d  mov     r9d, [rbx+0ACh]; cx
0x180006aa4  xor     edx, edx; x
0x180006aa6  mov     [rsp+0F0h+rop], 40CC0020h; rop
0x180006aae  mov     rcx, rsi; hdc
0x180006ab1  mov     [rsp+0F0h+y1], eax; y1
0x180006ab5  mov     eax, [rbp+57h+var_98.left]
0x180006ab8  mov     [rsp+0F0h+x1], eax; x1
0x180006abc  mov     eax, [rbx+0B0h]
0x180006ac2  mov     [rsp+0F0h+hdcSrc], r14; hdcSrc
0x180006ac7  mov     [rsp+0F0h+cy], eax; cy
0x180006acb  call    cs:__imp_BitBlt
0x180006ad1  mov     rdx, r13; h
0x180006ad4  mov     rcx, rsi; hdc
0x180006ad7  mov     r15d, eax
0x180006ada  call    cs:__imp_SelectObject
0x180006ae0  mov     rcx, rsi; hdc
0x180006ae3  call    cs:__imp_DeleteDC
0x180006ae9  test    rdi, rdi
0x180006aec  jz      short loc_180006AF7
0x180006aee  mov     rcx, rdi; ho
0x180006af1  call    cs:__imp_DeleteObject
0x180006af7  mov     rcx, [rbx+28h]; hWnd
0x180006afb  mov     rdx, r14; hDC
0x180006afe  call    cs:__imp_ReleaseDC
0x180006b04  test    r15d, r15d
0x180006b07  jnz     short loc_180006B21
0x180006b09  mov     rcx, [rbx+88h]; ho
0x180006b10  call    cs:__imp_DeleteObject
0x180006b16  mov     qword ptr [rbx+88h], 0
0x180006b21  mov     rcx, [rbx+28h]
0x180006b25  xor     edx, edx
0x180006b27  call    cs:__imp_InternalGetWindowIcon
0x180006b2d  mov     [rbx+0B8h], rax
0x180006b34  mov     edi, 80h
0x180006b39  test    rax, rax
0x180006b3c  jz      short loc_180006B50
0x180006b3e  mov     rcx, [rbx+30h]; hWnd
0x180006b42  mov     r9, rax; lParam
0x180006b45  xor     r8d, r8d; wParam
0x180006b48  mov     edx, edi; Msg
0x180006b4a  call    cs:__imp_SendMessageW
0x180006b50  mov     rcx, [rbx+28h]
0x180006b54  mov     edx, 1
0x180006b59  call    cs:__imp_InternalGetWindowIcon
0x180006b5f  mov     [rbx+0C0h], rax
0x180006b66  test    rax, rax
0x180006b69  jz      short loc_180006B80
0x180006b6b  mov     rcx, [rbx+30h]; hWnd
0x180006b6f  mov     r9, rax; lParam
0x180006b72  mov     r8d, 1; wParam
0x180006b78  mov     edx, edi; Msg
0x180006b7a  call    cs:__imp_SendMessageW
0x180006b80  mov     eax, r15d
0x180006b83  mov     rcx, [rbp+57h+var_48]
0x180006b87  xor     rcx, rsp; StackCookie
0x180006b8a  call    __security_check_cookie
0x180006b8f  add     rsp, 0B8h
0x180006b96  pop     r15
0x180006b98  pop     r14
0x180006b9a  pop     r13
0x180006b9c  pop     r12
0x180006b9e  pop     rdi
0x180006b9f  pop     rsi
0x180006ba0  pop     rbx
0x180006ba1  pop     rbp
0x180006ba2  retn
```
