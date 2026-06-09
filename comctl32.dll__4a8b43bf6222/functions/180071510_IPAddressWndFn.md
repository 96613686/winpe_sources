# IPAddressWndFn

- ea: `0x180071510`
- end: `0x180071d74`
- name: `IPAddressWndFn`
- size: `2148`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x1800115f0`
- `0x180017a0c`
- `0x180017bac`
- `0x18001a590`
- `0x18001ac40`
- `0x180042570`
- `0x180070fac`
- `0x1800710a0`
- `0x180071510`
- `0x180071d7c`
- `0x180071f88`
- `0x18008ea60`

## import_xrefs

- `GDI32!SelectObject` at `0x180071602`
- `GDI32!SelectObject` at `0x1800716e9`
- `GDI32!SelectObject` at `0x180071602`
- `GDI32!SelectObject` at `0x1800716e9`
- `GDI32!ExtTextOutW` at `0x1800716d3`
- `GDI32!ExtTextOutW` at `0x1800716d3`
- `GDI32!SetBkColor` at `0x18007167d`
- `GDI32!SetBkColor` at `0x18007167d`
- `GDI32!SetTextColor` at `0x180071689`
- `GDI32!SetTextColor` at `0x180071689`
- `KERNEL32!LocalFree` at `0x180071903`
- `KERNEL32!LocalFree` at `0x180071903`
- `KERNEL32!lstrlenW` at `0x180071786`
- `KERNEL32!lstrlenW` at `0x180071786`
- `KERNEL32!LocalAlloc` at `0x18007191b`
- `KERNEL32!LocalAlloc` at `0x18007191b`
- `USER32!GetClientRect` at `0x180071612`
- `USER32!GetClientRect` at `0x180071612`
- `USER32!GetSysColor` at `0x180071623`
- `USER32!GetSysColor` at `0x180071635`
- `USER32!GetSysColor` at `0x180071642`
- `USER32!GetSysColor` at `0x180071623`
- `USER32!GetSysColor` at `0x180071635`
- `USER32!GetSysColor` at `0x180071642`
- `USER32!SetRect` at `0x180071671`
- `USER32!SetRect` at `0x180071671`
- `USER32!SendMessageW` at `0x180071823`
- `USER32!SendMessageW` at `0x180071855`
- `USER32!SendMessageW` at `0x1800718d8`
- `USER32!SendMessageW` at `0x1800719d2`
- `USER32!SendMessageW` at `0x180071c52`
- `USER32!SendMessageW` at `0x180071cf1`
- `USER32!SendMessageW` at `0x180071d3f`
- `USER32!SendMessageW` at `0x180071823`
- `USER32!SendMessageW` at `0x180071855`
- `USER32!SendMessageW` at `0x1800718d8`
- `USER32!SendMessageW` at `0x1800719d2`
- `USER32!SendMessageW` at `0x180071c52`
- `USER32!SendMessageW` at `0x180071cf1`
- `USER32!SendMessageW` at `0x180071d3f`
- `USER32!DestroyWindow` at `0x180071a5d`
- `USER32!DestroyWindow` at `0x180071a5d`
- `USER32!ShowWindow` at `0x180071a4c`
- `USER32!ShowWindow` at `0x180071a4c`
- `USER32!SetWindowLongPtrW` at `0x1800718f1`
- `USER32!SetWindowLongPtrW` at `0x1800719bc`
- `USER32!SetWindowLongPtrW` at `0x180071a02`
- `USER32!SetWindowLongPtrW` at `0x180071a28`
- `USER32!SetWindowLongPtrW` at `0x1800718f1`
- `USER32!SetWindowLongPtrW` at `0x1800719bc`
- `USER32!SetWindowLongPtrW` at `0x180071a02`
- `USER32!SetWindowLongPtrW` at `0x180071a28`
- `USER32!CreateWindowExW` at `0x1800719a6`
- `USER32!CreateWindowExW` at `0x1800719a6`
- `USER32!EnableWindow` at `0x18007187a`
- `USER32!EnableWindow` at `0x18007187a`
- `USER32!GetDlgCtrlID` at `0x180071839`
- `USER32!GetDlgCtrlID` at `0x180071942`
- `USER32!GetDlgCtrlID` at `0x180071cd7`
- `USER32!GetDlgCtrlID` at `0x180071d25`
- `USER32!GetDlgCtrlID` at `0x180071839`
- `USER32!GetDlgCtrlID` at `0x180071942`
- `USER32!GetDlgCtrlID` at `0x180071cd7`
- `USER32!GetDlgCtrlID` at `0x180071d25`
- `USER32!SetFocus` at `0x180071c69`
- `USER32!SetFocus` at `0x180071c69`
- `USER32!GetFocus` at `0x180071cb3`
- `USER32!GetFocus` at `0x180071cb3`
- `USER32!InvalidateRect` at `0x18007189b`
- `USER32!InvalidateRect` at `0x18007189b`
- `USER32!GetWindowLongPtrW` at `0x18007154a`
- `USER32!GetWindowLongPtrW` at `0x1800719e2`
- `USER32!GetWindowLongPtrW` at `0x18007154a`
- `USER32!GetWindowLongPtrW` at `0x1800719e2`
- `USER32!BeginPaint` at `0x1800715f4`
- `USER32!BeginPaint` at `0x1800715f4`
- `USER32!EndPaint` at `0x1800716f6`
- `USER32!EndPaint` at `0x1800716f6`
- `USER32!DefWindowProcW` at `0x180071ae6`
- `USER32!DefWindowProcW` at `0x180071ae6`

## pseudocode

```c
LRESULT __fastcall IPAddressWndFn(HWND hWnd, UINT Msg, WPARAM wParam, HWND lParam)
{
  HWND *WindowLongPtrW; // rsi
  unsigned __int64 v9; // r15
  int v10; // r13d
  HGDIOBJ v12; // r12
  DWORD SysColor; // eax
  int v14; // ecx
  COLORREF v15; // edi
  DWORD v16; // ebx
  int v17; // ecx
  HDC hdc; // rcx
  __int64 v19; // r14
  int FieldValue; // eax
  int v21; // ecx
  struct tagPAINTSTRUCT *p_Paint; // rcx
  int v23; // r9d
  int k; // r8d
  int v25; // r10d
  __int64 m; // rbx
  unsigned __int16 v27; // ax
  __int64 j; // rdi
  HWND *v29; // rcx
  __int64 i; // rdi
  _DWORD *v31; // rax
  LONG_PTR v32; // rbx
  int DlgCtrlID; // eax
  HMENU hMenu; // rcx
  LONG_PTR v35; // r15
  __int64 v36; // rsi
  HWND Window; // rax
  __int64 n; // rsi
  unsigned int v39; // ebx
  int v40; // ebx
  __int64 kk; // r14
  int v42; // eax
  int v43; // ecx
  unsigned int jj; // ebx
  __int64 ii; // rdi
  WPARAM v46; // rbx
  HWND Focus; // rax
  unsigned int v48; // edi
  unsigned __int16 v49; // ax
  unsigned int v50; // edi
  unsigned __int16 v51; // ax
  struct tagPAINTSTRUCT Paint; // [rsp+60h] [rbp-69h] BYREF
  struct tagRECT Rect; // [rsp+B0h] [rbp-19h] BYREF
  __int128 v54; // [rsp+C0h] [rbp-9h]

  Rect.left = Msg;
  WindowLongPtrW = (HWND *)GetWindowLongPtrW(hWnd, -21);
  v9 = 1;
  if ( Msg <= 0x81 )
  {
    if ( Msg == 129 )
    {
      SetWindowBits(hWnd, -20);
      return v9;
    }
    if ( Msg != 1 )
    {
      if ( Msg == 2 )
      {
        _InterlockedDecrement(&g_dwWindowCount);
        for ( i = 0; i != 4; ++i )
        {
          SendMessageW(WindowLongPtrW[3 * i + 5], 2u, 0, 0);
          SetWindowLongPtrW(WindowLongPtrW[3 * i + 5], -4, (LONG_PTR)WindowLongPtrW[3 * i + 6]);
        }
        LocalFree(WindowLongPtrW);
        return v9;
      }
      if ( Msg != 7 )
      {
        v10 = 3;
        if ( Msg == 10 )
        {
          *((_DWORD *)WindowLongPtrW + 6) = wParam ^ (*((_DWORD *)WindowLongPtrW + 6) ^ wParam) & 0xFFFFFFFE;
          for ( j = 0; j != 4; ++j )
            EnableWindow(WindowLongPtrW[3 * j + 5], wParam);
          if ( ((_BYTE)WindowLongPtrW[3] & 2) != 0 )
            InvalidateRect(hWnd, 0, 0);
          return v9;
        }
        if ( Msg != 12 )
        {
          switch ( Msg )
          {
            case 0xDu:
            case 0xEu:
              LOWORD(Paint.hdc) = 0;
              v19 = 0;
              v54 = 0;
              do
              {
                FieldValue = GetFieldValue(&WindowLongPtrW[2 * v19 + 5] + v19);
                v21 = 0;
                if ( FieldValue != -1 )
                  v21 = FieldValue;
                *((_DWORD *)&v54 + v19++) = v21;
              }
              while ( v19 != 4 );
              StringCchPrintfW(
                (wchar_t *)&Paint,
                0x1Eu,
                L"%d.%d.%d.%d",
                (unsigned int)v54,
                DWORD1(v54),
                DWORD2(v54),
                HIDWORD(v54));
              if ( Rect.left == 13 )
              {
                StringCchCopyW((STRSAFE_LPWSTR)lParam, (int)wParam, (STRSAFE_LPCWSTR)&Paint);
                p_Paint = (struct tagPAINTSTRUCT *)lParam;
              }
              else
              {
                p_Paint = &Paint;
              }
              return lstrlenW((LPCWSTR)p_Paint);
            case 0xFu:
              memset(&Paint, 0, sizeof(Paint));
              Rect = 0;
              BeginPaint(hWnd, &Paint);
              v12 = SelectObject(Paint.hdc, WindowLongPtrW[4]);
              GetClientRect(hWnd, &Rect);
              if ( ((_BYTE)WindowLongPtrW[3] & 1) != 0 )
              {
                SysColor = GetSysColor(8);
                v14 = 5;
              }
              else
              {
                SysColor = GetSysColor(17);
                v14 = 15;
              }
              v15 = SysColor;
              v16 = GetSysColor(v14);
              FillRectClr(Paint.hdc, &Rect, v16);
              SetRect(&Rect, 0, 1, *((_DWORD *)WindowLongPtrW + 5), Rect.bottom - Rect.top);
              SetBkColor(Paint.hdc, v16);
              SetTextColor(Paint.hdc, v15);
              do
              {
                v17 = *((_DWORD *)WindowLongPtrW + 5);
                Rect.left += v17 + *((_DWORD *)WindowLongPtrW + 4);
                Rect.right += Rect.left + v17;
                ExtTextOutW(Paint.hdc, Rect.left, 1, 2u, &Rect, L".", 1u, 0);
                --v10;
              }
              while ( v10 );
              hdc = Paint.hdc;
              *((_DWORD *)WindowLongPtrW + 6) |= 2u;
              SelectObject(hdc, v12);
              EndPaint(hWnd, &Paint);
              return v9;
            case 0x30u:
              IP_OnSetFont(WindowLongPtrW, wParam, (unsigned int)lParam);
              return 0;
          }
          return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
        }
        v54 = 0;
        if ( *(_WORD *)lParam )
        {
          v23 = 0;
          for ( k = 0; ; ++k )
          {
            v25 = *((unsigned __int16 *)lParam + k);
            if ( (unsigned __int16)(v25 - 48) > 9u )
            {
              if ( ++v23 == 4 )
                break;
            }
            else
            {
              *((_DWORD *)&v54 + v23) = v25 + 2 * (*((_DWORD *)&v54 + v23) + 4 * (*((_DWORD *)&v54 + v23) - 6));
            }
          }
        }
        *((_DWORD *)WindowLongPtrW + 6) |= 8u;
        for ( m = 0; m != 4; ++m )
        {
          if ( *(_WORD *)lParam )
            StringCchPrintfW((wchar_t *)&Rect, 4u, L"%d", *((unsigned int *)&v54 + m));
          else
            LOWORD(Rect.left) = 0;
          SendMessageW(WindowLongPtrW[3 * m + 5], 0xCu, 0, (LPARAM)&Rect);
        }
        goto LABEL_38;
      }
      v29 = WindowLongPtrW + 5;
LABEL_45:
      EnterField(v29, 0, 3);
      return v9;
    }
    CCCreateWindow();
    v31 = LocalAlloc(0x40u, 0x88u);
    v32 = (LONG_PTR)v31;
    if ( v31 )
    {
      v31[6] |= 1u;
      *(_QWORD *)v31 = *((_QWORD *)lParam + 3);
      *((_QWORD *)v31 + 1) = hWnd;
      DlgCtrlID = GetDlgCtrlID(hWnd);
      hMenu = (HMENU)DlgCtrlID;
      v35 = 0;
      *(_QWORD *)&Rect.left = DlgCtrlID;
      v36 = 0;
      do
      {
        *(_WORD *)(v36 + v32 + 56) = -256;
        Window = CreateWindowExW(
                   0,
                   L"Edit",
                   0,
                   0x40000001u,
                   0,
                   10,
                   100,
                   100,
                   hWnd,
                   hMenu,
                   *((HINSTANCE *)lParam + 1),
                   0);
        *(_QWORD *)(v36 + v32 + 40) = Window;
        SetWindowLongPtrW(Window, -21, v35);
        SendMessageW(*(HWND *)(v36 + v32 + 40), 0xC5u, 3u, 0);
        *(_QWORD *)(v32 + 24 * v35 + 48) = GetWindowLongPtrW(*(HWND *)(v36 + v32 + 40), -4);
        SetWindowLongPtrW(*(HWND *)(v36 + v32 + 40), -4, (LONG_PTR)IPAddressFieldProc);
        hMenu = *(HMENU *)&Rect.left;
        v36 += 24;
        ++v35;
      }
      while ( v35 != 4 );
      SetWindowLongPtrW(hWnd, -21, v32);
      IP_OnSetFont(v32, 0, 0);
      for ( n = 0; n != 4; ++n )
        ShowWindow(*(HWND *)(v32 + 24 * n + 40), 5);
    }
    else
    {
      DestroyWindow(hWnd);
    }
    return 0;
  }
  if ( Msg == 135 )
    return 128;
  if ( Msg != 273 )
  {
    switch ( Msg )
    {
      case 0x201u:
        SetFocus(hWnd);
        return v9;
      case 0x464u:
        *((_DWORD *)WindowLongPtrW + 6) |= 8u;
        for ( ii = 0; ii != 4; ++ii )
          SendMessageW(WindowLongPtrW[3 * ii + 5], 0xCu, 0, (LPARAM)&WindowName);
        break;
      case 0x465u:
        *((_DWORD *)WindowLongPtrW + 6) |= 8u;
        for ( jj = 0; (int)jj < 4; ++jj )
        {
          if ( LOBYTE(WindowLongPtrW[3 * jj + 7]) > BYTE3(lParam) || BYTE3(lParam) > BYTE1(WindowLongPtrW[3 * jj + 7]) )
            v9 = 0;
          else
            SetFieldValue(WindowLongPtrW, jj, BYTE3(lParam));
          LODWORD(lParam) = (_DWORD)lParam << 8;
        }
        break;
      default:
        switch ( Msg )
        {
          case 0x466u:
            v9 = 0;
            v40 = 0;
            for ( kk = 0; kk != 4; ++kk )
            {
              v42 = GetFieldValue(&WindowLongPtrW[2 * kk + 5] + kk);
              if ( v42 != -1 )
                ++v9;
              v43 = 0;
              if ( v42 != -1 )
                v43 = v42;
              v40 = v43 + (v40 << 8);
            }
            *(_DWORD *)lParam = v40;
            return v9;
          case 0x467u:
            if ( wParam < 4 && (unsigned __int8)lParam <= BYTE1(lParam) )
            {
              v9 = LOBYTE(WindowLongPtrW[3 * wParam + 7])
                 + ((unsigned __int64)BYTE1(WindowLongPtrW[3 * wParam + 7]) << 8);
              LOWORD(WindowLongPtrW[3 * wParam + 7]) = (_WORD)lParam;
              return v9;
            }
            break;
          case 0x468u:
            if ( wParam >= 4 )
            {
              wParam = 0;
              while ( (unsigned int)GetFieldValue(&WindowLongPtrW[2 * wParam + 5] + wParam) != -1 )
              {
                if ( ++wParam >= 4 )
                {
                  wParam = 0;
                  break;
                }
              }
            }
            v29 = &WindowLongPtrW[2 * wParam + 5] + wParam;
            goto LABEL_45;
          case 0x469u:
            v39 = 0;
            while ( (unsigned int)GetFieldValue(&WindowLongPtrW[2 * v39 + 5] + v39) == -1 )
            {
              if ( (int)++v39 >= 4 )
                return v9;
            }
            break;
          default:
            return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
        }
        return 0;
    }
LABEL_38:
    *((_DWORD *)WindowLongPtrW + 6) &= ~8u;
LABEL_39:
    v27 = GetDlgCtrlID(hWnd);
    SendMessageW(*WindowLongPtrW, 0x111u, v27 | 0x3000000LL, (LPARAM)hWnd);
    return v9;
  }
  v46 = wParam >> 16;
  if ( (_WORD)v46 == 256 )
  {
    if ( ((_BYTE)WindowLongPtrW[3] & 0x10) == 0 )
    {
      v50 = 0;
      while ( WindowLongPtrW[3 * v50 + 5] != lParam )
      {
        if ( (int)++v50 >= 4 )
          return v9;
      }
      if ( ((_BYTE)WindowLongPtrW[3] & 4) == 0 )
      {
        v51 = GetDlgCtrlID(hWnd);
        SendMessageW(*WindowLongPtrW, 0x111u, v51 | 0x1000000LL, (LPARAM)hWnd);
        *((_DWORD *)WindowLongPtrW + 6) |= 4u;
      }
    }
    return v9;
  }
  if ( (_WORD)v46 == 512 )
  {
    if ( ((_BYTE)WindowLongPtrW[3] & 0x10) == 0 )
    {
      Focus = GetFocus();
      v48 = 0;
      while ( WindowLongPtrW[3 * v48 + 5] != Focus )
      {
        if ( (int)++v48 >= 4 )
        {
          v49 = GetDlgCtrlID(hWnd);
          SendMessageW(*WindowLongPtrW, 0x111u, v49 | 0x2000000LL, (LPARAM)hWnd);
          *((_DWORD *)WindowLongPtrW + 6) &= ~4u;
          return v9;
        }
      }
    }
    return v9;
  }
  if ( (_WORD)v46 == 768 && ((_BYTE)WindowLongPtrW[3] & 8) == 0 )
    goto LABEL_39;
  return v9;
}

```

## disassembly

```asm
0x180071510  push    rbp
0x180071512  push    rbx
0x180071513  push    rsi
0x180071514  push    rdi
0x180071515  push    r12
0x180071517  push    r13
0x180071519  push    r14
0x18007151b  push    r15
0x18007151d  lea     rbp, [rsp-1Fh]
0x180071522  sub     rsp, 0E8h
0x180071529  mov     rax, cs:__security_cookie
0x180071530  xor     rax, rsp
0x180071533  mov     [rbp+57h+var_50], rax
0x180071537  mov     edi, edx
0x180071539  mov     [rbp+57h+Rect.left], edx
0x18007153c  mov     edx, 0FFFFFFEBh; nIndex
0x180071541  mov     r12, r9
0x180071544  mov     rbx, r8
0x180071547  mov     r14, rcx
0x18007154a  call    cs:__imp_GetWindowLongPtrW
0x180071550  mov     rsi, rax
0x180071553  mov     r13d, 1
0x180071559  mov     eax, 81h
0x18007155e  mov     r15d, r13d
0x180071561  cmp     edi, eax
0x180071563  ja      loc_180071A88
0x180071569  jz      loc_180071A6B
0x18007156f  mov     eax, edi
0x180071571  sub     eax, r13d
0x180071574  jz      loc_18007190E
0x18007157a  sub     eax, r13d
0x18007157d  jz      loc_1800718BC
0x180071583  sub     eax, 5
0x180071586  jz      loc_1800718A6
0x18007158c  lea     r13d, [r15+2]
0x180071590  sub     eax, r13d
0x180071593  jz      loc_180071860
0x180071599  sub     eax, 2
0x18007159c  jz      loc_180071794
0x1800715a2  sub     eax, r15d
0x1800715a5  jz      loc_180071701
0x1800715ab  sub     eax, r15d
0x1800715ae  jz      loc_180071701
0x1800715b4  sub     eax, r15d
0x1800715b7  jz      short loc_1800715D7
0x1800715b9  cmp     eax, 21h ; '!'
0x1800715bc  jnz     loc_180071ADB
0x1800715c2  mov     r8d, r12d
0x1800715c5  mov     rdx, rbx
0x1800715c8  mov     rcx, rsi
0x1800715cb  call    IP_OnSetFont
0x1800715d0  xor     eax, eax
0x1800715d2  jmp     loc_180071D54
0x1800715d7  xor     edx, edx; Val
0x1800715d9  lea     rcx, [rbp+57h+Paint]; void *
0x1800715dd  lea     r8d, [rdx+48h]; Size
0x1800715e1  call    memset
0x1800715e6  xorps   xmm0, xmm0
0x1800715e9  lea     rdx, [rbp+57h+Paint]; lpPaint
0x1800715ed  mov     rcx, r14; hWnd
0x1800715f0  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x1800715f4  call    cs:__imp_BeginPaint
0x1800715fa  mov     rdx, [rsi+20h]; h
0x1800715fe  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x180071602  call    cs:__imp_SelectObject
0x180071608  lea     rdx, [rbp+57h+Rect]; lpRect
0x18007160c  mov     rcx, r14; hWnd
0x18007160f  mov     r12, rax
0x180071612  call    cs:__imp_GetClientRect
0x180071618  test    [rsi+18h], r15b
0x18007161c  jz      short loc_180071630
0x18007161e  mov     ecx, 8; nIndex
0x180071623  call    cs:__imp_GetSysColor
0x180071629  mov     ecx, 5
0x18007162e  jmp     short loc_180071640
0x180071630  mov     ecx, 11h; nIndex
0x180071635  call    cs:__imp_GetSysColor
0x18007163b  mov     ecx, 0Fh; nIndex
0x180071640  mov     edi, eax
0x180071642  call    cs:__imp_GetSysColor
0x180071648  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x18007164c  lea     rdx, [rbp+57h+Rect]; lprect
0x180071650  mov     r8d, eax; color
0x180071653  mov     ebx, eax
0x180071655  call    FillRectClr
0x18007165a  mov     eax, [rbp+57h+Rect.bottom]
0x18007165d  lea     rcx, [rbp+57h+Rect]; lprc
0x180071661  sub     eax, [rbp+57h+Rect.top]
0x180071664  xor     edx, edx; xLeft
0x180071666  mov     r9d, [rsi+14h]; xRight
0x18007166a  mov     r8d, r15d; yTop
0x18007166d  mov     [rsp+120h+yBottom], eax; yBottom
0x180071671  call    cs:__imp_SetRect
0x180071677  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x18007167b  mov     edx, ebx; color
0x18007167d  call    cs:__imp_SetBkColor
0x180071683  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x180071687  mov     edx, edi; color
0x180071689  call    cs:__imp_SetTextColor
0x18007168f  xor     edi, edi
0x180071691  mov     ecx, [rsi+14h]
0x180071694  mov     r9d, 2; options
0x18007169a  mov     eax, [rsi+10h]
0x18007169d  mov     r8d, r15d; y
0x1800716a0  mov     edx, [rbp+57h+Rect.left]
0x1800716a3  add     eax, ecx
0x1800716a5  add     edx, eax; x
0x1800716a7  mov     [rsp+120h+lpDx], rdi; lpDx
0x1800716ac  mov     [rsp+120h+c], r15d; c
0x1800716b1  mov     [rbp+57h+Rect.left], edx
0x1800716b4  lea     eax, [rdx+rcx]
0x1800716b7  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x1800716bb  add     [rbp+57h+Rect.right], eax
0x1800716be  lea     rax, asc_18009B084; "."
0x1800716c5  mov     [rsp+120h+lpString], rax; lpString
0x1800716ca  lea     rax, [rbp+57h+Rect]
0x1800716ce  mov     qword ptr [rsp+120h+yBottom], rax; lprect
0x1800716d3  call    cs:__imp_ExtTextOutW
0x1800716d9  sub     r13d, r15d
0x1800716dc  jnz     short loc_180071691
0x1800716de  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x1800716e2  mov     rdx, r12; h
0x1800716e5  or      dword ptr [rsi+18h], 2
0x1800716e9  call    cs:__imp_SelectObject
0x1800716ef  lea     rdx, [rbp+57h+Paint]; lpPaint
0x1800716f3  mov     rcx, r14; hWnd
0x1800716f6  call    cs:__imp_EndPaint
0x1800716fc  jmp     loc_180071D51
0x180071701  xor     edi, edi
0x180071703  xorps   xmm0, xmm0
0x180071706  mov     word ptr [rbp+57h+Paint.hdc], di
0x18007170a  mov     r14d, edi
0x18007170d  movups  [rbp+57h+var_60], xmm0
0x180071711  lea     rax, ds:5[r14*2]
0x180071719  add     rax, r14
0x18007171c  lea     rcx, [rsi+rax*8]
0x180071720  call    GetFieldValue
0x180071725  cmp     eax, 0FFFFFFFFh
0x180071728  mov     ecx, edi
0x18007172a  cmovnz  ecx, eax
0x18007172d  mov     dword ptr [rbp+r14*4+57h+var_60], ecx
0x180071732  inc     r14
0x180071735  cmp     r14, 4
0x180071739  jnz     short loc_180071711
0x18007173b  mov     eax, dword ptr [rbp+57h+var_60+0Ch]
0x18007173e  lea     r8, aDDDD; "%d.%d.%d.%d"
0x180071745  mov     r9d, dword ptr [rbp+57h+var_60]
0x180071749  lea     edx, [r14+1Ah]; unsigned __int64
0x18007174d  mov     [rsp+120h+c], eax
0x180071751  lea     rcx, [rbp+57h+Paint]; Buffer
0x180071755  mov     eax, dword ptr [rbp+57h+var_60+8]
0x180071758  mov     dword ptr [rsp+120h+lpString], eax
0x18007175c  mov     eax, dword ptr [rbp+57h+var_60+4]
0x18007175f  mov     [rsp+120h+yBottom], eax
0x180071763  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180071768  cmp     [rbp+57h+Rect.left], 0Dh
0x18007176c  jnz     short loc_180071782
0x18007176e  movsxd  rdx, ebx; cchDest
0x180071771  lea     r8, [rbp+57h+Paint]; pszSrc
0x180071775  mov     rcx, r12; pszDest
0x180071778  call    StringCchCopyW
0x18007177d  mov     rcx, r12
0x180071780  jmp     short loc_180071786
0x180071782  lea     rcx, [rbp+57h+Paint]; lpString
0x180071786  call    cs:__imp_lstrlenW
0x18007178c  movsxd  r15, eax
0x18007178f  jmp     loc_180071D51
0x180071794  xor     edi, edi
0x180071796  xorps   xmm0, xmm0
0x180071799  movups  [rbp+57h+var_60], xmm0
0x18007179d  cmp     [r12], di
0x1800717a2  jz      short loc_1800717E1
0x1800717a4  mov     r9d, edi
0x1800717a7  mov     r8d, edi
0x1800717aa  movsxd  rax, r8d
0x1800717ad  movzx   r10d, word ptr [r12+rax*2]
0x1800717b2  lea     eax, [r10-30h]
0x1800717b6  cmp     ax, 9
0x1800717ba  ja      short loc_1800717D3
0x1800717bc  movsxd  rdx, r9d
0x1800717bf  mov     eax, dword ptr [rbp+rdx*4+57h+var_60]
0x1800717c3  lea     ecx, [rax-6]
0x1800717c6  lea     ecx, [rax+rcx*4]
0x1800717c9  lea     ecx, [r10+rcx*2]
0x1800717cd  mov     dword ptr [rbp+rdx*4+57h+var_60], ecx
0x1800717d1  jmp     short loc_1800717DC
0x1800717d3  inc     r9d
0x1800717d6  cmp     r9d, 4
0x1800717da  jz      short loc_1800717E1
0x1800717dc  inc     r8d
0x1800717df  jmp     short loc_1800717AA
0x1800717e1  or      dword ptr [rsi+18h], 8
0x1800717e5  mov     rbx, rdi
0x1800717e8  cmp     [r12], di
0x1800717ed  jnz     short loc_1800717F5
0x1800717ef  mov     word ptr [rbp+57h+Rect.left], di
0x1800717f3  jmp     short loc_18007180F
0x1800717f5  mov     r9d, dword ptr [rbp+rbx*4+57h+var_60]
0x1800717fa  lea     r8, aD; "%d"
0x180071801  mov     edx, 4; unsigned __int64
0x180071806  lea     rcx, [rbp+57h+Rect]; Buffer
0x18007180a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007180f  xor     r8d, r8d; wParam
0x180071812  lea     rcx, [rbx+rbx*2]
0x180071816  mov     rcx, [rsi+rcx*8+28h]; hWnd
0x18007181b  lea     r9, [rbp+57h+Rect]; lParam
0x18007181f  lea     edx, [r8+0Ch]; Msg
0x180071823  call    cs:__imp_SendMessageW
0x180071829  inc     rbx
0x18007182c  cmp     rbx, 4
0x180071830  jnz     short loc_1800717E8
0x180071832  and     dword ptr [rsi+18h], 0FFFFFFF7h
0x180071836  mov     rcx, r14; hWnd
0x180071839  call    cs:__imp_GetDlgCtrlID
0x18007183f  mov     rcx, [rsi]; hWnd
0x180071842  mov     r9, r14; lParam
0x180071845  movzx   r8d, ax
0x180071849  mov     edx, 111h; Msg
0x18007184e  or      r8, 3000000h; wParam
0x180071855  call    cs:__imp_SendMessageW
0x18007185b  jmp     loc_180071D51
0x180071860  mov     eax, ebx
0x180071862  xor     eax, [rsi+18h]
0x180071865  and     eax, 0FFFFFFFEh
0x180071868  xor     eax, ebx
0x18007186a  mov     [rsi+18h], eax
0x18007186d  xor     edi, edi
0x18007186f  lea     rcx, [rdi+rdi*2]
0x180071873  mov     edx, ebx; bEnable
0x180071875  mov     rcx, [rsi+rcx*8+28h]; hWnd
0x18007187a  call    cs:__imp_EnableWindow
0x180071880  inc     rdi
0x180071883  cmp     rdi, 4
0x180071887  jnz     short loc_18007186F
0x180071889  test    byte ptr [rsi+18h], 2
0x18007188d  jz      loc_180071D51
0x180071893  xor     r8d, r8d; bErase
0x180071896  xor     edx, edx; lpRect
0x180071898  mov     rcx, r14; hWnd
0x18007189b  call    cs:__imp_InvalidateRect
0x1800718a1  jmp     loc_180071D51
0x1800718a6  xor     edx, edx
0x1800718a8  lea     rcx, [rsi+28h]
0x1800718ac  mov     r8d, 3
0x1800718b2  call    EnterField
0x1800718b7  jmp     loc_180071D51
0x1800718bc  lock dec cs:g_dwWindowCount
0x1800718c3  xor     edi, edi
0x1800718c5  xor     r9d, r9d; lParam
0x1800718c8  lea     rbx, [rdi+rdi*2]
0x1800718cc  mov     rcx, [rsi+rbx*8+28h]; hWnd
0x1800718d1  xor     r8d, r8d; wParam
0x1800718d4  lea     edx, [r9+2]; Msg
0x1800718d8  call    cs:__imp_SendMessageW
0x1800718de  mov     rcx, [rsi+rbx*8+28h]; hWnd
0x1800718e3  lea     r8, [rdi+rdi*2]
0x1800718e7  mov     r8, [rsi+r8*8+30h]; dwNewLong
0x1800718ec  mov     edx, 0FFFFFFFCh; nIndex
0x1800718f1  call    cs:__imp_SetWindowLongPtrW
0x1800718f7  add     rdi, r13
0x1800718fa  cmp     rdi, 4
0x1800718fe  jnz     short loc_1800718C5
0x180071900  mov     rcx, rsi; hMem
0x180071903  call    cs:__imp_LocalFree
0x180071909  jmp     loc_180071D51
0x18007190e  call    CCCreateWindow
0x180071913  mov     edx, 88h; uBytes
0x180071918  lea     ecx, [rdx-48h]; uFlags
0x18007191b  call    cs:__imp_LocalAlloc
0x180071921  xor     edi, edi
0x180071923  mov     rcx, r14; hWnd
0x180071926  mov     rbx, rax
0x180071929  test    rax, rax
0x18007192c  jz      loc_180071A5D
0x180071932  or      [rax+18h], r13d
0x180071936  mov     rax, [r12+18h]
0x18007193b  mov     [rbx], rax
0x18007193e  mov     [rbx+8], r14
0x180071942  call    cs:__imp_GetDlgCtrlID
0x180071948  movsxd  rcx, eax
0x18007194b  mov     r15d, edi
0x18007194e  mov     qword ptr [rbp+57h+Rect.left], rcx
0x180071952  lea     r13d, [rdi+3]
0x180071956  mov     esi, edi
0x180071958  mov     [rsp+120h+lpParam], rdi; lpParam
0x18007195d  lea     rdx, aEdit_0; "Edit"
0x180071964  mov     word ptr [rsi+rbx+38h], 0FF00h
0x18007196b  mov     r9d, 40000001h; dwStyle
0x180071971  mov     rax, [r12+8]
0x180071976  xor     r8d, r8d; lpWindowName
0x180071979  mov     [rsp+120h+hInstance], rax; hInstance
0x18007197e  mov     [rsp+120h+hMenu], rcx; hMenu
0x180071983  xor     ecx, ecx; dwExStyle
0x180071985  mov     [rsp+120h+hWndParent], r14; hWndParent
0x18007198a  mov     dword ptr [rsp+120h+lpDx], 64h ; 'd'; nHeight
0x180071992  mov     [rsp+120h+c], 64h ; 'd'; nWidth
0x18007199a  mov     dword ptr [rsp+120h+lpString], 0Ah; Y
0x1800719a2  mov     [rsp+120h+yBottom], edi; X
0x1800719a6  call    cs:__imp_CreateWindowExW
0x1800719ac  mov     r8, r15; dwNewLong
  ... truncated ...
```
