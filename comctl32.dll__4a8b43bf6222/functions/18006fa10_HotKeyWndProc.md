# HotKeyWndProc

- ea: `0x18006fa10`
- end: `0x18006fea3`
- name: `HotKeyWndProc`
- size: `1171`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, HGDIOBJ h, LPARAM lParam)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800115f0`
- `0x180017bac`
- `0x1800190a4`
- `0x18001a590`
- `0x18006f944`
- `0x18006fa10`
- `0x18006ff18`
- `0x1800701e8`

## import_xrefs

- `USER32!GetClientRect` at `0x18006fc04`
- `USER32!GetClientRect` at `0x18006fc04`
- `USER32!GetDC` at `0x18006fbf3`
- `USER32!GetDC` at `0x18006fbf3`
- `USER32!ReleaseDC` at `0x18006fc39`
- `USER32!ReleaseDC` at `0x18006fc39`
- `USER32!SetWindowLongPtrW` at `0x18006fb32`
- `USER32!SetWindowLongPtrW` at `0x18006fb42`
- `USER32!SetWindowLongPtrW` at `0x18006fe22`
- `USER32!SetWindowLongPtrW` at `0x18006fe34`
- `USER32!SetWindowLongPtrW` at `0x18006fb32`
- `USER32!SetWindowLongPtrW` at `0x18006fb42`
- `USER32!SetWindowLongPtrW` at `0x18006fe22`
- `USER32!SetWindowLongPtrW` at `0x18006fe34`
- `USER32!SetFocus` at `0x18006fe7d`
- `USER32!SetFocus` at `0x18006fe7d`
- `USER32!InvalidateRect` at `0x18006fa99`
- `USER32!InvalidateRect` at `0x18006fad9`
- `USER32!InvalidateRect` at `0x18006fa99`
- `USER32!InvalidateRect` at `0x18006fad9`
- `USER32!IsWindowEnabled` at `0x18006fc0d`
- `USER32!IsWindowEnabled` at `0x18006fc0d`
- `USER32!GetKeyState` at `0x18006fd2c`
- `USER32!GetKeyState` at `0x18006fd41`
- `USER32!GetKeyState` at `0x18006fd5c`
- `USER32!GetKeyState` at `0x18006fd2c`
- `USER32!GetKeyState` at `0x18006fd41`
- `USER32!GetKeyState` at `0x18006fd5c`
- `USER32!FillRect` at `0x18006fc2d`
- `USER32!FillRect` at `0x18006fc2d`
- `USER32!GetWindowLongPtrW` at `0x18006faa9`
- `USER32!GetWindowLongPtrW` at `0x18006fae7`
- `USER32!GetWindowLongPtrW` at `0x18006fbcc`
- `USER32!GetWindowLongPtrW` at `0x18006fc8d`
- `USER32!GetWindowLongPtrW` at `0x18006fd9d`
- `USER32!GetWindowLongPtrW` at `0x18006fdae`
- `USER32!GetWindowLongPtrW` at `0x18006fe3e`
- `USER32!GetWindowLongPtrW` at `0x18006fe4f`
- `USER32!GetWindowLongPtrW` at `0x18006faa9`
- `USER32!GetWindowLongPtrW` at `0x18006fae7`
- `USER32!GetWindowLongPtrW` at `0x18006fbcc`
- `USER32!GetWindowLongPtrW` at `0x18006fc8d`
- `USER32!GetWindowLongPtrW` at `0x18006fd9d`
- `USER32!GetWindowLongPtrW` at `0x18006fdae`
- `USER32!GetWindowLongPtrW` at `0x18006fe3e`
- `USER32!GetWindowLongPtrW` at `0x18006fe4f`
- `USER32!DefWindowProcW` at `0x18006fdfa`
- `USER32!DefWindowProcW` at `0x18006fdfa`
- `USER32!HideCaret` at `0x18006fbea`
- `USER32!HideCaret` at `0x18006fbea`
- `USER32!ShowCaret` at `0x18006fb01`
- `USER32!ShowCaret` at `0x18006fc42`
- `USER32!ShowCaret` at `0x18006fb01`
- `USER32!ShowCaret` at `0x18006fc42`
- `USER32!CreateCaret` at `0x18006faf8`
- `USER32!CreateCaret` at `0x18006faf8`
- `USER32!DestroyCaret` at `0x18006fac5`
- `USER32!DestroyCaret` at `0x18006fac5`

## pseudocode

```c
LONG_PTR __fastcall HotKeyWndProc(HWND hWnd, UINT Msg, char *h, LPARAM lParam)
{
  WPARAM v5; // r14
  HWND v7; // rsi
  int WindowLongPtrW; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  HDC DC; // rbx
  BOOL v15; // eax
  HBRUSH v16; // r8
  unsigned __int16 v17; // bx
  unsigned __int16 v18; // di
  unsigned __int16 v19; // r13
  __int64 v20; // rbx
  unsigned __int8 v21; // bl
  struct tagRECT Rect; // [rsp+20h] [rbp-68h] BYREF

  v5 = (WPARAM)h;
  v7 = hWnd;
  Rect = 0;
  if ( Msg <= 0x87 )
  {
    if ( Msg == 135 )
      return 129;
    if ( Msg <= 0xF )
    {
      if ( Msg == 15 )
      {
        PaintHotKey(hWnd);
      }
      else if ( Msg == 1 )
      {
        SetHotKey((LPARAM)hWnd);
        SetWindowLongPtrW(v7, 16, 0);
        SetWindowLongPtrW(v7, 24, 0);
        HKMSetFont(v7, g_hfontSystem);
      }
      else if ( Msg == 2 )
      {
        _InterlockedDecrement(&g_dwWindowCount);
      }
      else if ( Msg == 7 )
      {
        InvalidateRect(hWnd, 0, 1);
        WindowLongPtrW = GetWindowLongPtrW(v7, 40);
        CreateCaret(v7, 0, 0, WindowLongPtrW);
        ShowCaret(v7);
      }
      else
      {
        if ( Msg != 8 )
        {
          if ( Msg == 10 )
            InvalidateRect(hWnd, 0, 1);
          return DefWindowProcW(v7, Msg, v5, lParam);
        }
        if ( !GetWindowLongPtrW(hWnd, 0) )
          SetHotKey((LPARAM)v7);
        DestroyCaret();
      }
      return 0;
    }
    switch ( Msg )
    {
      case 0x14u:
        HideCaret(hWnd);
        DC = GetDC(v7);
        GetClientRect(v7, &Rect);
        v15 = IsWindowEnabled(v7);
        v16 = g_hbrWindow;
        if ( !v15 )
          v16 = g_hbrBtnFace;
        FillRect(DC, &Rect, v16);
        ReleaseDC(v7, DC);
        ShowCaret(v7);
        return 1;
      case 0x30u:
        return HKMSetFont(hWnd, h);
      case 0x31u:
        return GetWindowLongPtrW(hWnd, 32);
      case 0x3Du:
        if ( (_DWORD)lParam == -12 )
          return 65552;
        return DefWindowProcW(v7, Msg, v5, lParam);
      case 0x81u:
        SetWindowBits(hWnd, -20);
        CCCreateWindow(v10, v9);
        InitGlobalColors(v12, v11);
        return 1;
    }
    return DefWindowProcW(v7, Msg, v5, lParam);
  }
  if ( Msg > 0x106 )
  {
    switch ( Msg )
    {
      case 0x201u:
        SetFocus(hWnd);
        return 0;
      case 0x401u:
        goto LABEL_71;
      case 0x402u:
        v21 = GetWindowLongPtrW(hWnd, 0);
        return v21 + ((unsigned __int64)(unsigned __int8)GetWindowLongPtrW(v7, 8) << 8);
    }
    if ( Msg != 1027 )
      return DefWindowProcW(v7, Msg, v5, lParam);
    SetWindowLongPtrW(hWnd, 16, (LONG_PTR)h);
    SetWindowLongPtrW(v7, 24, (unsigned __int16)lParam);
    return 0;
  }
  if ( Msg != 262 )
  {
    if ( Msg != 256 )
    {
      if ( Msg == 257 || Msg == 258 )
        goto LABEL_40;
      if ( Msg != 260 )
      {
        if ( Msg != 261 )
          return DefWindowProcW(v7, Msg, v5, lParam);
        goto LABEL_40;
      }
    }
    if ( (unsigned __int64)h > 0x1B )
    {
      if ( h != (char *)32 && h != (char *)46 && h != (char *)91 && (unsigned __int64)(h - 92) >= 2 )
      {
LABEL_54:
        v17 = (GetKeyState(17) >> 15) & 2;
        v18 = v17 | 1;
        if ( GetKeyState(16) >= 0 )
          v18 = v17;
        v19 = v18 | 4;
        if ( GetKeyState(18) >= 0 )
          v19 = v18;
        if ( (unsigned __int16)(v5 - 112) > 0x17u && (unsigned __int16)(v5 - 96) > 0xFu )
        {
          v20 = *((unsigned int *)s_Combos + v19);
          if ( (GetWindowLongPtrW(v7, 16) & v20) != 0 )
            GetWindowLongPtrW(v7, 24);
        }
        goto LABEL_62;
      }
    }
    else if ( h != (char *)27 && h != (char *)8 && h != (char *)9 && h != (char *)13 )
    {
      if ( h == (char *)16 || (unsigned __int64)(h - 17) <= 1 )
        LOWORD(v5) = 0;
      goto LABEL_54;
    }
    SetHotKey((LPARAM)hWnd);
    return DefWindowProcW(v7, Msg, v5, lParam);
  }
LABEL_40:
  if ( !GetWindowLongPtrW(hWnd, 0) )
  {
LABEL_62:
    hWnd = v7;
LABEL_71:
    SetHotKey((LPARAM)hWnd);
  }
  return 0;
}

```

## disassembly

```asm
0x18006fa10  push    rbx
0x18006fa12  push    rbp
0x18006fa13  push    rsi
0x18006fa14  push    rdi
0x18006fa15  push    r12
0x18006fa17  push    r13
0x18006fa19  push    r14
0x18006fa1b  push    r15
0x18006fa1d  sub     rsp, 48h
0x18006fa21  mov     rax, cs:__security_cookie
0x18006fa28  xor     rax, rsp
0x18006fa2b  mov     [rsp+88h+var_58], rax
0x18006fa30  mov     eax, 87h
0x18006fa35  xorps   xmm0, xmm0
0x18006fa38  mov     r12, r9
0x18006fa3b  mov     r14, r8
0x18006fa3e  mov     ebx, edx
0x18006fa40  mov     rsi, rcx
0x18006fa43  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x18006fa48  cmp     edx, eax
0x18006fa4a  ja      loc_18006FC57
0x18006fa50  jz      loc_18006FC4D
0x18006fa56  lea     ecx, [rax-78h]
0x18006fa59  cmp     edx, ecx
0x18006fa5b  ja      loc_18006FB69
0x18006fa61  jz      loc_18006FB5C
0x18006fa67  mov     eax, edx
0x18006fa69  sub     eax, 1
0x18006fa6c  jz      loc_18006FB18
0x18006fa72  sub     eax, 1
0x18006fa75  jz      loc_18006FB0C
0x18006fa7b  sub     eax, 5
0x18006fa7e  jz      short loc_18006FAD0
0x18006fa80  sub     eax, 1
0x18006fa83  jz      short loc_18006FAA4
0x18006fa85  lea     edi, [rcx-0Dh]
0x18006fa88  cmp     eax, edi
0x18006fa8a  jnz     loc_18006FDEF
0x18006fa90  lea     r8d, [rcx-0Eh]; bErase
0x18006fa94  xor     edx, edx; lpRect
0x18006fa96  mov     rcx, rsi; hWnd
0x18006fa99  call    cs:__imp_InvalidateRect
0x18006fa9f  jmp     loc_18006FDEF
0x18006faa4  xor     edx, edx; nIndex
0x18006faa6  mov     rcx, rsi; hWnd
0x18006faa9  call    cs:__imp_GetWindowLongPtrW
0x18006faaf  test    rax, rax
0x18006fab2  jnz     short loc_18006FAC5
0x18006fab4  xor     r8d, r8d
0x18006fab7  lea     r9d, [rax+1]
0x18006fabb  xor     edx, edx
0x18006fabd  mov     rcx, rsi; lParam
0x18006fac0  call    SetHotKey
0x18006fac5  call    cs:__imp_DestroyCaret
0x18006facb  jmp     loc_18006FE83
0x18006fad0  xor     edx, edx; lpRect
0x18006fad2  mov     rcx, rsi; hWnd
0x18006fad5  lea     r8d, [rdx+1]; bErase
0x18006fad9  call    cs:__imp_InvalidateRect
0x18006fadf  mov     edx, 28h ; '('; nIndex
0x18006fae4  mov     rcx, rsi; hWnd
0x18006fae7  call    cs:__imp_GetWindowLongPtrW
0x18006faed  xor     r8d, r8d; nWidth
0x18006faf0  xor     edx, edx; hBitmap
0x18006faf2  mov     r9, rax; nHeight
0x18006faf5  mov     rcx, rsi; hWnd
0x18006faf8  call    cs:__imp_CreateCaret
0x18006fafe  mov     rcx, rsi; hWnd
0x18006fb01  call    cs:__imp_ShowCaret
0x18006fb07  jmp     loc_18006FE83
0x18006fb0c  lock dec cs:g_dwWindowCount
0x18006fb13  jmp     loc_18006FE83
0x18006fb18  xor     r8d, r8d
0x18006fb1b  xor     edx, edx
0x18006fb1d  xor     r9d, r9d
0x18006fb20  mov     rcx, rsi; lParam
0x18006fb23  call    SetHotKey
0x18006fb28  xor     r8d, r8d; dwNewLong
0x18006fb2b  mov     rcx, rsi; hWnd
0x18006fb2e  lea     edx, [r8+10h]; nIndex
0x18006fb32  call    cs:__imp_SetWindowLongPtrW
0x18006fb38  xor     r8d, r8d; dwNewLong
0x18006fb3b  mov     rcx, rsi; hWnd
0x18006fb3e  lea     edx, [r8+18h]; nIndex
0x18006fb42  call    cs:__imp_SetWindowLongPtrW
0x18006fb48  mov     rdx, cs:g_hfontSystem; h
0x18006fb4f  mov     rcx, rsi; hWnd
0x18006fb52  call    HKMSetFont
0x18006fb57  jmp     loc_18006FE83
0x18006fb5c  mov     rcx, rsi; hWnd
0x18006fb5f  call    PaintHotKey
0x18006fb64  jmp     loc_18006FE83
0x18006fb69  mov     eax, ebx
0x18006fb6b  sub     eax, 14h
0x18006fb6e  jz      short loc_18006FBE7
0x18006fb70  sub     eax, 1Ch
0x18006fb73  jz      short loc_18006FBD7
0x18006fb75  sub     eax, 1
0x18006fb78  jz      short loc_18006FBC4
0x18006fb7a  sub     eax, 0Ch
0x18006fb7d  jz      short loc_18006FBB0
0x18006fb7f  cmp     eax, 44h ; 'D'
0x18006fb82  jnz     loc_18006FDEF
0x18006fb88  mov     r9d, 200h
0x18006fb8e  lea     edx, [rax-58h]; nIndex
0x18006fb91  mov     r8d, r9d
0x18006fb94  mov     rcx, rsi; hWnd
0x18006fb97  call    SetWindowBits
0x18006fb9c  call    CCCreateWindow
0x18006fba1  call    InitGlobalColors
0x18006fba6  mov     eax, 1
0x18006fbab  jmp     loc_18006FE85
0x18006fbb0  cmp     r12d, 0FFFFFFF4h
0x18006fbb4  jnz     loc_18006FDEF
0x18006fbba  mov     eax, 10010h
0x18006fbbf  jmp     loc_18006FE85
0x18006fbc4  mov     edx, 20h ; ' '; nIndex
0x18006fbc9  mov     rcx, rsi; hWnd
0x18006fbcc  call    cs:__imp_GetWindowLongPtrW
0x18006fbd2  jmp     loc_18006FE85
0x18006fbd7  mov     rdx, r14; h
0x18006fbda  mov     rcx, rsi; hWnd
0x18006fbdd  call    HKMSetFont
0x18006fbe2  jmp     loc_18006FE85
0x18006fbe7  mov     rcx, rsi; hWnd
0x18006fbea  call    cs:__imp_HideCaret
0x18006fbf0  mov     rcx, rsi; hWnd
0x18006fbf3  call    cs:__imp_GetDC
0x18006fbf9  lea     rdx, [rsp+88h+Rect]; lpRect
0x18006fbfe  mov     rcx, rsi; hWnd
0x18006fc01  mov     rbx, rax
0x18006fc04  call    cs:__imp_GetClientRect
0x18006fc0a  mov     rcx, rsi; hWnd
0x18006fc0d  call    cs:__imp_IsWindowEnabled
0x18006fc13  mov     r8, cs:g_hbrWindow
0x18006fc1a  lea     rdx, [rsp+88h+Rect]; lprc
0x18006fc1f  mov     rcx, rbx; hDC
0x18006fc22  test    eax, eax
0x18006fc24  jnz     short loc_18006FC2D
0x18006fc26  mov     r8, cs:g_hbrBtnFace; hbr
0x18006fc2d  call    cs:__imp_FillRect
0x18006fc33  mov     rdx, rbx; hDC
0x18006fc36  mov     rcx, rsi; hWnd
0x18006fc39  call    cs:__imp_ReleaseDC
0x18006fc3f  mov     rcx, rsi; hWnd
0x18006fc42  call    cs:__imp_ShowCaret
0x18006fc48  jmp     loc_18006FBA6
0x18006fc4d  mov     eax, 81h
0x18006fc52  jmp     loc_18006FE85
0x18006fc57  mov     eax, 106h
0x18006fc5c  cmp     ebx, eax
0x18006fc5e  ja      loc_18006FE05
0x18006fc64  jz      short loc_18006FC8B
0x18006fc66  mov     eax, ebx
0x18006fc68  mov     edi, 2
0x18006fc6d  sub     eax, 100h
0x18006fc72  jz      short loc_18006FCAA
0x18006fc74  sub     eax, 1
0x18006fc77  jz      short loc_18006FC8B
0x18006fc79  sub     eax, 1
0x18006fc7c  jz      short loc_18006FC8B
0x18006fc7e  sub     eax, edi
0x18006fc80  jz      short loc_18006FCAA
0x18006fc82  cmp     eax, 1
0x18006fc85  jnz     loc_18006FDEF
0x18006fc8b  xor     edx, edx; nIndex
0x18006fc8d  call    cs:__imp_GetWindowLongPtrW
0x18006fc93  test    rax, rax
0x18006fc96  jnz     loc_18006FE83
0x18006fc9c  xor     r8d, r8d
0x18006fc9f  lea     r9d, [rax+1]
0x18006fca3  xor     edx, edx
0x18006fca5  jmp     loc_18006FDD9
0x18006fcaa  xor     r15d, r15d
0x18006fcad  cmp     r14, 1Bh
0x18006fcb1  ja      short loc_18006FCF2
0x18006fcb3  jz      loc_18006FDE1
0x18006fcb9  mov     rax, r14
0x18006fcbc  sub     rax, 8
0x18006fcc0  jz      loc_18006FDE1
0x18006fcc6  sub     rax, 1
0x18006fcca  jz      loc_18006FDE1
0x18006fcd0  sub     rax, 4
0x18006fcd4  jz      loc_18006FDE1
0x18006fcda  sub     rax, 3
0x18006fcde  jz      short loc_18006FCEC
0x18006fce0  sub     rax, 1
0x18006fce4  jz      short loc_18006FCEC
0x18006fce6  cmp     rax, 1
0x18006fcea  jnz     short loc_18006FD27
0x18006fcec  movzx   r14d, r15w
0x18006fcf0  jmp     short loc_18006FD27
0x18006fcf2  mov     rax, r14
0x18006fcf5  sub     rax, 20h ; ' '
0x18006fcf9  jz      loc_18006FDE1
0x18006fcff  sub     rax, 0Eh
0x18006fd03  jz      loc_18006FDE1
0x18006fd09  sub     rax, 2Dh ; '-'
0x18006fd0d  jz      loc_18006FDE1
0x18006fd13  sub     rax, 1
0x18006fd17  jz      loc_18006FDE1
0x18006fd1d  cmp     rax, 1
0x18006fd21  jz      loc_18006FDE1
0x18006fd27  mov     ecx, 11h; nVirtKey
0x18006fd2c  call    cs:__imp_GetKeyState
0x18006fd32  movzx   ebx, ax
0x18006fd35  mov     ecx, 10h; nVirtKey
0x18006fd3a  sar     bx, 0Fh
0x18006fd3e  and     bx, di
0x18006fd41  call    cs:__imp_GetKeyState
0x18006fd47  mov     ebp, 1
0x18006fd4c  movzx   edi, bx
0x18006fd4f  or      di, bp
0x18006fd52  test    ax, ax
0x18006fd55  lea     ecx, [rbp+11h]; nVirtKey
0x18006fd58  cmovns  di, bx
0x18006fd5c  call    cs:__imp_GetKeyState
0x18006fd62  movzx   r13d, di
0x18006fd66  or      r13w, 4
0x18006fd6b  test    ax, ax
0x18006fd6e  lea     eax, [r14-70h]
0x18006fd72  cmovns  r13w, di
0x18006fd77  cmp     ax, 17h
0x18006fd7b  jbe     short loc_18006FDB6
0x18006fd7d  lea     eax, [r14-60h]
0x18006fd81  lea     ecx, [rbp+0Eh]
0x18006fd84  cmp     ax, cx
0x18006fd87  jbe     short loc_18006FDB6
0x18006fd89  movzx   eax, r13w
0x18006fd8d  lea     rcx, s_Combos
0x18006fd94  lea     edx, [rbp+0Fh]; nIndex
0x18006fd97  mov     ebx, [rcx+rax*4]
0x18006fd9a  mov     rcx, rsi; hWnd
0x18006fd9d  call    cs:__imp_GetWindowLongPtrW
0x18006fda3  test    rbx, rax
0x18006fda6  jz      short loc_18006FDB6
0x18006fda8  lea     edx, [rbp+17h]; nIndex
0x18006fdab  mov     rcx, rsi; hWnd
0x18006fdae  call    cs:__imp_GetWindowLongPtrW
0x18006fdb4  jmp     short loc_18006FDBA
0x18006fdb6  movzx   eax, r13w
0x18006fdba  movzx   r8d, ax
0x18006fdbe  and     r12d, 1000000h
0x18006fdc5  or      r8w, 8
0x18006fdca  mov     r9d, ebp
0x18006fdcd  test    r12, r12
0x18006fdd0  movzx   edx, r14w
0x18006fdd4  cmovz   r8w, ax
0x18006fdd9  mov     rcx, rsi; lParam
0x18006fddc  jmp     loc_18006FE76
0x18006fde1  xor     r8d, r8d
0x18006fde4  xor     edx, edx
0x18006fde6  lea     r9d, [r8+1]
0x18006fdea  call    SetHotKey
0x18006fdef  mov     r9, r12; lParam
0x18006fdf2  mov     r8, r14; wParam
0x18006fdf5  mov     edx, ebx; Msg
0x18006fdf7  mov     rcx, rsi; hWnd
0x18006fdfa  call    cs:__imp_DefWindowProcW
0x18006fe00  jmp     loc_18006FE85
0x18006fe05  mov     eax, ebx
0x18006fe07  sub     eax, 201h
0x18006fe0c  jz      short loc_18006FE7D
0x18006fe0e  sub     eax, 200h
0x18006fe13  jz      short loc_18006FE64
0x18006fe15  sub     eax, 1
0x18006fe18  jz      short loc_18006FE3C
0x18006fe1a  cmp     eax, 1
0x18006fe1d  jnz     short loc_18006FDEF
0x18006fe1f  lea     edx, [rax+0Fh]; nIndex
0x18006fe22  call    cs:__imp_SetWindowLongPtrW
0x18006fe28  movzx   r8d, r12w; dwNewLong
0x18006fe2c  mov     edx, 18h; nIndex
0x18006fe31  mov     rcx, rsi; hWnd
0x18006fe34  call    cs:__imp_SetWindowLongPtrW
0x18006fe3a  jmp     short loc_18006FE83
0x18006fe3c  xor     edx, edx; nIndex
0x18006fe3e  call    cs:__imp_GetWindowLongPtrW
0x18006fe44  mov     edx, 8; nIndex
0x18006fe49  mov     rcx, rsi; hWnd
0x18006fe4c  mov     rbx, rax
0x18006fe4f  call    cs:__imp_GetWindowLongPtrW
0x18006fe55  movzx   eax, al
0x18006fe58  shl     rax, 8
0x18006fe5c  movzx   ecx, bl; lParam
0x18006fe5f  add     rax, rcx
0x18006fe62  jmp     short loc_18006FE85
0x18006fe64  mov     rax, r14
0x18006fe67  movzx   edx, r14b
0x18006fe6b  shr     rax, 8
0x18006fe6f  movzx   r8d, al
0x18006fe73  xor     r9d, r9d
0x18006fe76  call    SetHotKey
0x18006fe7b  jmp     short loc_18006FE83
0x18006fe7d  call    cs:__imp_SetFocus
0x18006fe83  xor     eax, eax
0x18006fe85  mov     rcx, [rsp+88h+var_58]
0x18006fe8a  xor     rcx, rsp; StackCookie
0x18006fe8d  call    __security_check_cookie
0x18006fe92  add     rsp, 48h
  ... truncated ...
```
