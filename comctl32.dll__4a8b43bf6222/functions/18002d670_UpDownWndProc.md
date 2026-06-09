# UpDownWndProc

- ea: `0x18002d670`
- end: `0x18002de94`
- name: `UpDownWndProc`
- size: `2084`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, HWND, LPARAM lParam)`
- caller_count: `0`
- callee_count: `22`
- tags: ``

## callees

- `0x1800115f0`
- `0x180017bac`
- `0x180018158`
- `0x1800183dc`
- `0x180018464`
- `0x1800184b8`
- `0x18001923c`
- `0x1800197bc`
- `0x18002d2f4`
- `0x18002d524`
- `0x18002d5c4`
- `0x18002d670`
- `0x18002de9c`
- `0x18002e0ac`
- `0x18002e1e4`
- `0x18002e41c`
- `0x18002e4b4`
- `0x18002e5d8`
- `0x18002e878`
- `0x18002e940`
- `0x180030800`
- `0x18003a400`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18002d7fa`
- `KERNEL32!LocalFree` at `0x18002d7fa`
- `KERNEL32!LocalAlloc` at `0x18002d81d`
- `KERNEL32!LocalAlloc` at `0x18002d81d`
- `KERNEL32!LocalReAlloc` at `0x18002dc52`
- `KERNEL32!LocalReAlloc` at `0x18002dc52`
- `USER32!SetCapture` at `0x18002daa2`
- `USER32!SetCapture` at `0x18002daa2`
- `USER32!ReleaseCapture` at `0x18002da2b`
- `USER32!ReleaseCapture` at `0x18002da2b`
- `USER32!PtInRect` at `0x18002d966`
- `USER32!PtInRect` at `0x18002d966`
- `USER32!GetCapture` at `0x18002d8c2`
- `USER32!GetCapture` at `0x18002da0f`
- `USER32!GetCapture` at `0x18002d8c2`
- `USER32!GetCapture` at `0x18002da0f`
- `USER32!SendMessageW` at `0x18002da53`
- `USER32!SendMessageW` at `0x18002da7d`
- `USER32!SendMessageW` at `0x18002da53`
- `USER32!SendMessageW` at `0x18002da7d`
- `USER32!SetWindowLongPtrW` at `0x18002d808`
- `USER32!SetWindowLongPtrW` at `0x18002d83c`
- `USER32!SetWindowLongPtrW` at `0x18002dc6c`
- `USER32!SetWindowLongPtrW` at `0x18002d808`
- `USER32!SetWindowLongPtrW` at `0x18002d83c`
- `USER32!SetWindowLongPtrW` at `0x18002dc6c`
- `USER32!SetFocus` at `0x18002dac3`
- `USER32!SetFocus` at `0x18002dac3`
- `USER32!InvalidateRect` at `0x18002d7d7`
- `USER32!InvalidateRect` at `0x18002d7d7`
- `USER32!IsWindowEnabled` at `0x18002da01`
- `USER32!IsWindowEnabled` at `0x18002da91`
- `USER32!IsWindowEnabled` at `0x18002da01`
- `USER32!IsWindowEnabled` at `0x18002da91`
- `USER32!GetWindowLongPtrW` at `0x18002d6b2`
- `USER32!GetWindowLongPtrW` at `0x18002d6b2`
- `USER32!DefWindowProcW` at `0x18002dba3`
- `USER32!DefWindowProcW` at `0x18002dba3`
- `USER32!InflateRect` at `0x18002d94e`
- `USER32!InflateRect` at `0x18002d94e`
- `USER32!GetCaretBlinkTime` at `0x18002db0e`
- `USER32!GetCaretBlinkTime` at `0x18002db1f`
- `USER32!GetCaretBlinkTime` at `0x18002db0e`
- `USER32!GetCaretBlinkTime` at `0x18002db1f`
- `USER32!SetTimer` at `0x18002d8de`
- `USER32!SetTimer` at `0x18002db31`
- `USER32!SetTimer` at `0x18002d8de`
- `USER32!SetTimer` at `0x18002db31`
- `USER32!GetCursorPos` at `0x18002d958`
- `USER32!GetCursorPos` at `0x18002d958`
- `USER32!KillTimer` at `0x18002da37`
- `USER32!KillTimer` at `0x18002da37`
- `USER32!GetWindowRect` at `0x18002d8eb`
- `USER32!GetWindowRect` at `0x18002d8eb`

## pseudocode

```c
unsigned __int64 __fastcall UpDownWndProc(HWND hWnd, UINT Msg, unsigned __int64 a3, _DWORD *lParam)
{
  __int64 v8; // rdx
  _QWORD *WindowLongPtrW; // rdi
  int v10; // r9d
  int v11; // eax
  __int64 v13; // rax
  HLOCAL v14; // rax
  DWORD_PTR v15; // rbx
  HWND v16; // rcx
  UINT v17; // edx
  HWND v18; // rcx
  int v19; // eax
  int v20; // eax
  __int64 v21; // r8
  __int64 v22; // rdx
  UINT CaretBlinkTime; // eax
  UINT v24; // r8d
  int v25; // ebx
  _QWORD *v26; // rax
  HWND v27; // rcx
  int i; // edx
  __int64 v29; // rcx
  unsigned __int16 v30; // ax
  int v31; // ecx
  int v32; // eax
  int v33; // edx
  int v34; // edx
  __int64 v35; // rcx
  __int64 v36; // rbx
  unsigned int v37; // esi
  struct tagPOINT Point; // [rsp+30h] [rbp-48h] BYREF
  __int64 v39; // [rsp+38h] [rbp-40h] BYREF
  struct tagTRACKMOUSEEVENT EventTrack; // [rsp+40h] [rbp-38h] BYREF
  struct tagRECT Rect; // [rsp+58h] [rbp-20h] BYREF

  Rect = 0;
  Point.x = 0;
  v39 = 0;
  WindowLongPtrW = (_QWORD *)GetWindowLongPtrW(hWnd, 0);
  if ( WindowLongPtrW )
  {
    if ( Msg - 512 <= 0xD && (WindowLongPtrW[2] & 0x100) != 0 )
    {
      v11 = *((_DWORD *)WindowLongPtrW + 16);
      if ( (v11 & 0x40) == 0 )
      {
        *(_QWORD *)&EventTrack.dwHoverTime = 0;
        *((_DWORD *)WindowLongPtrW + 16) = v11 | 0x40;
        EventTrack.hwndTrack = (HWND)*WindowLongPtrW;
        EventTrack.cbSize = 24;
        EventTrack.dwFlags = 2;
        TrackMouseEvent(&EventTrack);
      }
    }
  }
  else if ( Msg != 1 )
  {
    return DefWindowProcW(hWnd, Msg, a3, (LPARAM)lParam);
  }
  if ( Msg <= 0x465 )
  {
    if ( Msg == 1125 )
    {
      *((_DWORD *)WindowLongPtrW + 18) = (__int16)lParam;
      *((_DWORD *)WindowLongPtrW + 19) = SWORD1(lParam);
      nudge(WindowLongPtrW);
      return 0;
    }
    if ( Msg <= 0x113 )
    {
      if ( Msg != 275 )
      {
        switch ( Msg )
        {
          case 1u:
            CCCreateWindow();
            v14 = LocalAlloc(0x40u, 0x88u);
            v15 = (DWORD_PTR)v14;
            if ( !v14 )
              return -1;
            SetWindowLongPtrW(hWnd, 0, (LONG_PTR)v14);
            CIInitialize(v15, hWnd, lParam);
            if ( (lParam[12] & 0x200) != 0 )
              *(_DWORD *)(v15 + 64) |= 4u;
            if ( (lParam[18] & 0x200) != 0 )
              *(_DWORD *)(v15 + 64) |= 0x10u;
            *(_QWORD *)(v15 + 68) = 10;
            *(_QWORD *)(v15 + 76) = 100;
            *(_QWORD *)(v15 + 56) = 0;
            *(_DWORD *)(v15 + 84) = 0;
            *(_QWORD *)(v15 + 96) = 3;
            *(_DWORD *)(v15 + 104) = 1;
            *(_DWORD *)(v15 + 108) = 2;
            *(_DWORD *)(v15 + 112) = 5;
            *(_DWORD *)(v15 + 116) = 5;
            *(_DWORD *)(v15 + 120) = 20;
            setbuddy(v15, 0);
            setint(v15);
            return 0;
          case 2u:
            _InterlockedDecrement(&g_dwWindowCount);
            if ( WindowLongPtrW )
            {
              if ( WindowLongPtrW[7] )
                *((_DWORD *)WindowLongPtrW + 16) |= 0x20u;
              else
                LocalFree(WindowLongPtrW);
              SetWindowLongPtrW(hWnd, 0, 0);
            }
            return 0;
          case 0xAu:
            InvalidateRect(hWnd, 0, 1);
            return 0;
        }
        if ( Msg != 15 )
        {
          if ( Msg != 26 )
          {
            if ( Msg == 61 )
            {
              if ( (_DWORD)lParam == -12 )
                return 65558;
              return DefWindowProcW(hWnd, Msg, a3, (LPARAM)lParam);
            }
            if ( Msg == 85 )
              return CIHandleNotifyFormat(WindowLongPtrW, lParam);
            goto LABEL_123;
          }
          if ( WindowLongPtrW && a3 <= 0x2A )
          {
            v13 = 0x40400000001LL;
            if ( _bittest64(&v13, a3) )
            {
              InitGlobalMetrics(a3);
              unachor(WindowLongPtrW);
              anchor(WindowLongPtrW);
            }
          }
          return 0;
        }
LABEL_56:
        PaintUpDownControl(WindowLongPtrW, a3);
        return 0;
      }
      Point = 0;
      if ( GetCapture() == hWnd )
      {
        SetTimer(hWnd, 1u, 0x64u, 0);
        GetWindowRect(hWnd, &Rect);
        if ( (WindowLongPtrW[2] & 0x40) != 0 )
        {
          if ( *((_DWORD *)WindowLongPtrW + 22) )
            Rect.right = (Rect.right + Rect.left) / 2;
          else
            Rect.left = (Rect.right + Rect.left) / 2;
        }
        else if ( *((_DWORD *)WindowLongPtrW + 22) )
        {
          Rect.top = (Rect.bottom + Rect.top) / 2;
        }
        else
        {
          Rect.bottom = (Rect.bottom + Rect.top) / 2;
        }
        InflateRect(&Rect, (g_cxFrame + 1) / 2, (g_cyFrame + 1) / 2);
        GetCursorPos(&Point);
        if ( !PtInRect(&Rect, Point) )
        {
          squish(WindowLongPtrW, 0, 0);
          return 0;
        }
        squish(WindowLongPtrW, *((_DWORD *)WindowLongPtrW + 22) == 0, *((unsigned int *)WindowLongPtrW + 22));
LABEL_80:
        bump(WindowLongPtrW);
        return 0;
      }
LABEL_61:
      squish(WindowLongPtrW, 0, 0);
      ReleaseCapture();
      KillTimer(hWnd, 1u);
      if ( *((_DWORD *)WindowLongPtrW + 21) == 1 )
        SendMessageW((HWND)WindowLongPtrW[7], 0xB1u, 0, -1);
      v17 = 276;
      if ( (WindowLongPtrW[2] & 0x40) == 0 )
        v17 = 277;
      SendMessageW(
        (HWND)WindowLongPtrW[1],
        v17,
        ((unsigned __int64)*((unsigned __int16 *)WindowLongPtrW + 40) << 16) | 8,
        *WindowLongPtrW);
      return 0;
    }
    if ( Msg == 296 )
    {
      CCOnUIState(WindowLongPtrW, v8, a3);
      return DefWindowProcW(hWnd, Msg, a3, (LPARAM)lParam);
    }
    if ( Msg == 512 )
    {
      if ( (WindowLongPtrW[2] & 0x100) != 0 )
      {
        v25 = UD_HitTest(WindowLongPtrW, (unsigned int)(__int16)lParam, (unsigned int)SWORD1(lParam));
        if ( v25 != *((_DWORD *)WindowLongPtrW + 31) )
        {
          UD_Invalidate(WindowLongPtrW);
          UD_Invalidate(WindowLongPtrW);
          *((_DWORD *)WindowLongPtrW + 31) = v25;
        }
      }
      return 0;
    }
    if ( Msg != 513 )
    {
      switch ( Msg )
      {
        case 0x202u:
          v16 = (HWND)WindowLongPtrW[7];
          if ( v16 && !IsWindowEnabled(v16) || GetCapture() != hWnd )
            return 0;
          goto LABEL_61;
        case 0x2A3u:
          *((_DWORD *)WindowLongPtrW + 16) &= ~0x40u;
          UD_Invalidate(WindowLongPtrW);
          *((_DWORD *)WindowLongPtrW + 31) = 0;
          return 0;
        case 0x318u:
          goto LABEL_56;
      }
LABEL_123:
      if ( (unsigned int)CCWndProc((_DWORD)WindowLongPtrW, Msg, a3, v10, (__int64)&v39) )
        return v39;
      return DefWindowProcW(hWnd, Msg, a3, (LPARAM)lParam);
    }
    v18 = (HWND)WindowLongPtrW[7];
    if ( v18 && !IsWindowEnabled(v18) )
      return 0;
    SetCapture(hWnd);
    getint(WindowLongPtrW, 0);
    if ( *((_DWORD *)WindowLongPtrW + 21) == 1 || *((_DWORD *)WindowLongPtrW + 21) == 2 )
      SetFocus((HWND)WindowLongPtrW[7]);
    v19 = UD_HitTest(WindowLongPtrW, (unsigned int)(__int16)lParam, (unsigned int)SWORD1(lParam));
    if ( !v19 )
      return 0;
    v20 = v19 - 1;
    if ( v20 )
    {
      if ( v20 != 1 )
      {
LABEL_77:
        CaretBlinkTime = GetCaretBlinkTime();
        v24 = 1300;
        if ( CaretBlinkTime < 0x514 )
          v24 = GetCaretBlinkTime();
        SetTimer(hWnd, 1u, v24, 0);
        goto LABEL_80;
      }
      *((_DWORD *)WindowLongPtrW + 22) = 0;
      v21 = 0;
      v22 = 1;
    }
    else
    {
      *((_DWORD *)WindowLongPtrW + 22) = 1;
      v21 = 1;
      v22 = 0;
    }
    squish(WindowLongPtrW, v22, v21);
    goto LABEL_77;
  }
  if ( Msg <= 0x46C )
  {
    if ( Msg == 1132 )
    {
      v34 = 0;
      if ( a3 > *((unsigned int *)WindowLongPtrW + 24) )
        LODWORD(a3) = *((_DWORD *)WindowLongPtrW + 24);
      if ( (int)a3 > 0 )
      {
        do
        {
          v35 = v34++;
          *(_QWORD *)&lParam[2 * v35] = *(_QWORD *)((char *)&WindowLongPtrW[v35 + 12] + 4);
        }
        while ( v34 < (int)a3 );
      }
      return *((unsigned int *)WindowLongPtrW + 24);
    }
    if ( Msg == 1126 )
      return (*((unsigned __int16 *)WindowLongPtrW + 38) << 16) | *((unsigned __int16 *)WindowLongPtrW + 36);
    if ( Msg != 1127 )
    {
      switch ( Msg )
      {
        case 0x468u:
          v30 = getint(WindowLongPtrW, &Point);
          return v30 | (unsigned __int64)(LOWORD(Point.x) << 16);
        case 0x469u:
          return setbuddy((DWORD_PTR)WindowLongPtrW, (HWND)a3);
        case 0x46Au:
          return WindowLongPtrW[7];
      }
      if ( !a3 )
        return 0;
      if ( a3 >= 3 )
      {
        v26 = LocalReAlloc(WindowLongPtrW, 8 * a3 + 112, 2u);
        WindowLongPtrW = v26;
        if ( !v26 )
          return 0;
        SetWindowLongPtrW(hWnd, 0, (LONG_PTR)v26);
        if ( (WindowLongPtrW[2] & 0x20) != 0 )
        {
          v27 = (HWND)WindowLongPtrW[7];
          if ( v27 )
          {
            *((_DWORD *)WindowLongPtrW + 16) |= 0x80u;
            SetWindowSubclass(v27, ArrowKeyProc, 0, (DWORD_PTR)WindowLongPtrW);
          }
        }
      }
      *((_DWORD *)WindowLongPtrW + 24) = a3;
      for ( i = 0; i < (int)a3; *(_QWORD *)((char *)&WindowLongPtrW[v29 + 12] + 4) = *(_QWORD *)&lParam[2 * v29] )
        v29 = i++;
      return 1;
    }
    LODWORD(lParam) = (__int16)lParam;
LABEL_107:
    v31 = *((_DWORD *)WindowLongPtrW + 18);
    v32 = *((_DWORD *)WindowLongPtrW + 19);
    v33 = WindowLongPtrW[8] & 4;
    if ( v33 )
    {
      if ( v32 < (unsigned int)v31 )
      {
        if ( (unsigned int)lParam <= v31 )
          goto LABEL_131;
LABEL_130:
        LODWORD(lParam) = *((_DWORD *)WindowLongPtrW + 18);
        if ( v33 )
        {
LABEL_131:
          if ( (unsigned int)lParam < v32 )
            goto LABEL_140;
          goto LABEL_141;
        }
LABEL_133:
        if ( (int)lParam < v32 )
          goto LABEL_140;
        goto LABEL_141;
      }
      if ( (unsigned int)lParam >= v31 )
      {
LABEL_137:
        if ( (unsigned int)lParam > v32 )
          goto LABEL_140;
        goto LABEL_141;
      }
    }
    else
    {
      if ( v32 < v31 )
      {
        if ( (int)lParam <= v31 )
          goto LABEL_133;
        goto LABEL_130;
      }
      if ( (int)lParam >= v31 )
        goto LABEL_139;
    }
    LODWORD(lParam) = *((_DWORD *)WindowLongPtrW + 18);
    if ( v33 )
      goto LABEL_137;
LABEL_139:
    if ( (int)lParam > v32 )
LABEL_140:
      LODWORD(lParam) = *((_DWORD *)WindowLongPtrW + 19);
LABEL_141:
    v36 = *((int *)WindowLongPtrW + 20);
    *((_DWORD *)WindowLongPtrW + 20) = (_DWORD)lParam;
    setint(WindowLongPtrW);
    MyNotifyWinEvent(32782, *WindowLongPtrW, 4294967292LL);
    return v36;
  }
  switch ( Msg )
  {
    case 0x46Du:
      if ( (_DWORD)a3 == 10 || (_DWORD)a3 == 16 )
      {
        *((_DWORD *)WindowLongPtrW + 16) &= ~4u;
        v37 = *((_DWORD *)WindowLongPtrW + 17);
        *((_DWORD *)WindowLongPtrW + 17) = a3;
        *((_DWORD *)WindowLongPtrW + 16) |= (_DWORD)a3 != 10 ? 4 : 0;
        setint(WindowLongPtrW);
      }
      else
      {
        return 0;
      }
      return v37;
    case 0x46Eu:
      return *((unsigned int *)WindowLongPtrW + 17);
    case 0x46Fu:
      *((_DWORD *)WindowLongPtrW + 18) = (_DWORD)lParam;
      *((_DWORD *)WindowLongPtrW + 19) = a3;
      return 0;
    case 0x470u:
      if ( lParam )
        *lParam = *((_DWORD *)WindowLongPtrW + 18);
      if ( a3 )
        *(_DWORD *)a3 = *((_DWORD *)WindowLongPtrW + 19);
      return 0;
    case 0x471u:
      goto LABEL_107;
  }
  if ( Msg != 1138 )
    goto LABEL_123;
  return getint(WindowLongPtrW, lParam);
}

```

## disassembly

```asm
0x18002d670  push    rbp
0x18002d672  push    rbx
0x18002d673  push    rsi
0x18002d674  push    rdi
0x18002d675  push    r12
0x18002d677  push    r13
0x18002d679  push    r14
0x18002d67b  push    r15
0x18002d67d  mov     rbp, rsp
0x18002d680  sub     rsp, 78h
0x18002d684  mov     rax, cs:__security_cookie
0x18002d68b  xor     rax, rsp
0x18002d68e  mov     [rbp+var_10], rax
0x18002d692  mov     r14d, edx
0x18002d695  xorps   xmm0, xmm0
0x18002d698  xor     r12d, r12d
0x18002d69b  xor     edx, edx; nIndex
0x18002d69d  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18002d6a1  mov     [rbp+Point.x], r12d
0x18002d6a5  mov     rsi, r9
0x18002d6a8  mov     [rbp+var_40], r12
0x18002d6ac  mov     rbx, r8
0x18002d6af  mov     r15, rcx
0x18002d6b2  call    cs:__imp_GetWindowLongPtrW
0x18002d6b8  lea     r13d, [r12+1]
0x18002d6bd  mov     rdi, rax
0x18002d6c0  test    rax, rax
0x18002d6c3  jz      short loc_18002D70B
0x18002d6c5  lea     eax, [r14-200h]
0x18002d6cc  cmp     eax, 0Dh
0x18002d6cf  ja      short loc_18002D714
0x18002d6d1  test    dword ptr [rdi+10h], 100h
0x18002d6d8  jz      short loc_18002D714
0x18002d6da  mov     eax, [rdi+40h]
0x18002d6dd  test    al, 40h
0x18002d6df  jnz     short loc_18002D714
0x18002d6e1  or      eax, 40h
0x18002d6e4  mov     qword ptr [rbp+EventTrack.dwHoverTime], r12
0x18002d6e8  mov     [rdi+40h], eax
0x18002d6eb  lea     rcx, [rbp+EventTrack]; lpEventTrack
0x18002d6ef  mov     rax, [rdi]
0x18002d6f2  mov     [rbp+EventTrack.hwndTrack], rax
0x18002d6f6  mov     [rbp+EventTrack.cbSize], 18h
0x18002d6fd  mov     [rbp+EventTrack.dwFlags], 2
0x18002d704  call    _TrackMouseEvent
0x18002d709  jmp     short loc_18002D714
0x18002d70b  cmp     r14d, r13d
0x18002d70e  jnz     loc_18002DB97
0x18002d714  mov     eax, 465h
0x18002d719  cmp     r14d, eax
0x18002d71c  ja      loc_18002DBE3
0x18002d722  jz      loc_18002DBC6
0x18002d728  mov     eax, 113h
0x18002d72d  cmp     r14d, eax
0x18002d730  ja      loc_18002D999
0x18002d736  jz      loc_18002D8BE
0x18002d73c  mov     eax, r14d
0x18002d73f  sub     eax, r13d
0x18002d742  jz      loc_18002D810
0x18002d748  sub     eax, r13d
0x18002d74b  jz      loc_18002D7DF
0x18002d751  sub     eax, 8
0x18002d754  jz      short loc_18002D7CF
0x18002d756  sub     eax, 5
0x18002d759  jz      loc_18002D9D0
0x18002d75f  sub     eax, 0Bh
0x18002d762  jz      short loc_18002D795
0x18002d764  sub     eax, 23h ; '#'
0x18002d767  jz      short loc_18002D782
0x18002d769  cmp     eax, 18h
0x18002d76c  jnz     loc_18002DD96
0x18002d772  mov     rdx, rsi
0x18002d775  mov     rcx, rdi
0x18002d778  call    CIHandleNotifyFormat
0x18002d77d  jmp     loc_18002DBA9
0x18002d782  cmp     esi, 0FFFFFFF4h
0x18002d785  jnz     loc_18002DB97
0x18002d78b  mov     eax, 10016h
0x18002d790  jmp     loc_18002DBA9
0x18002d795  test    rdi, rdi
0x18002d798  jz      short loc_18002D7C8
0x18002d79a  cmp     rbx, 2Ah ; '*'
0x18002d79e  ja      short loc_18002D7C8
0x18002d7a0  mov     rax, 40400000001h
0x18002d7aa  bt      rax, rbx
0x18002d7ae  jnb     short loc_18002D7C8
0x18002d7b0  mov     rcx, rbx
0x18002d7b3  call    InitGlobalMetrics
0x18002d7b8  mov     rcx, rdi
0x18002d7bb  call    unachor
0x18002d7c0  mov     rcx, rdi
0x18002d7c3  call    anchor
0x18002d7c8  xor     eax, eax
0x18002d7ca  jmp     loc_18002DBA9
0x18002d7cf  mov     r8d, r13d; bErase
0x18002d7d2  xor     edx, edx; lpRect
0x18002d7d4  mov     rcx, r15; hWnd
0x18002d7d7  call    cs:__imp_InvalidateRect
0x18002d7dd  jmp     short loc_18002D7C8
0x18002d7df  lock dec cs:g_dwWindowCount
0x18002d7e6  test    rdi, rdi
0x18002d7e9  jz      short loc_18002D7C8
0x18002d7eb  cmp     [rdi+38h], r12
0x18002d7ef  jz      short loc_18002D7F7
0x18002d7f1  or      dword ptr [rdi+40h], 20h
0x18002d7f5  jmp     short loc_18002D800
0x18002d7f7  mov     rcx, rdi; hMem
0x18002d7fa  call    cs:__imp_LocalFree
0x18002d800  xor     r8d, r8d; dwNewLong
0x18002d803  xor     edx, edx; nIndex
0x18002d805  mov     rcx, r15; hWnd
0x18002d808  call    cs:__imp_SetWindowLongPtrW
0x18002d80e  jmp     short loc_18002D7C8
0x18002d810  call    CCCreateWindow
0x18002d815  mov     edx, 88h; uBytes
0x18002d81a  lea     ecx, [rdx-48h]; uFlags
0x18002d81d  call    cs:__imp_LocalAlloc
0x18002d823  mov     rbx, rax
0x18002d826  test    rax, rax
0x18002d829  jnz     short loc_18002D834
0x18002d82b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d82f  jmp     loc_18002DBA9
0x18002d834  mov     r8, rbx; dwNewLong
0x18002d837  xor     edx, edx; nIndex
0x18002d839  mov     rcx, r15; hWnd
0x18002d83c  call    cs:__imp_SetWindowLongPtrW
0x18002d842  mov     r8, rsi
0x18002d845  mov     rdx, r15
0x18002d848  mov     rcx, rbx
0x18002d84b  call    CIInitialize
0x18002d850  mov     ecx, 200h
0x18002d855  test    [rsi+30h], ecx
0x18002d858  jz      short loc_18002D85E
0x18002d85a  or      dword ptr [rbx+40h], 4
0x18002d85e  test    [rsi+48h], ecx
0x18002d861  jz      short loc_18002D867
0x18002d863  or      dword ptr [rbx+40h], 10h
0x18002d867  xor     edx, edx; hWnd
0x18002d869  mov     qword ptr [rbx+44h], 0Ah
0x18002d871  mov     rcx, rbx; dwRefData
0x18002d874  mov     qword ptr [rbx+4Ch], 64h ; 'd'
0x18002d87c  mov     [rbx+38h], r12
0x18002d880  mov     [rbx+54h], r12d
0x18002d884  mov     qword ptr [rbx+60h], 3
0x18002d88c  mov     [rbx+68h], r13d
0x18002d890  mov     dword ptr [rbx+6Ch], 2
0x18002d897  mov     dword ptr [rbx+70h], 5
0x18002d89e  mov     dword ptr [rbx+74h], 5
0x18002d8a5  mov     dword ptr [rbx+78h], 14h
0x18002d8ac  call    setbuddy
0x18002d8b1  mov     rcx, rbx
0x18002d8b4  call    setint
0x18002d8b9  jmp     loc_18002D7C8
0x18002d8be  mov     qword ptr [rbp+Point.x], r12
0x18002d8c2  call    cs:__imp_GetCapture
0x18002d8c8  cmp     rax, r15
0x18002d8cb  jnz     loc_18002DA1E
0x18002d8d1  xor     r9d, r9d; lpTimerFunc
0x18002d8d4  mov     rdx, r13; nIDEvent
0x18002d8d7  mov     rcx, r15; hWnd
0x18002d8da  lea     r8d, [r9+64h]; uElapse
0x18002d8de  call    cs:__imp_SetTimer
0x18002d8e4  lea     rdx, [rbp+Rect]; lpRect
0x18002d8e8  mov     rcx, r15; hWnd
0x18002d8eb  call    cs:__imp_GetWindowRect
0x18002d8f1  test    byte ptr [rdi+10h], 40h
0x18002d8f5  jz      short loc_18002D912
0x18002d8f7  mov     eax, [rbp+Rect.left]
0x18002d8fa  add     eax, [rbp+Rect.right]
0x18002d8fd  cdq
0x18002d8fe  sub     eax, edx
0x18002d900  sar     eax, 1
0x18002d902  cmp     [rdi+58h], r12d
0x18002d906  jz      short loc_18002D90D
0x18002d908  mov     [rbp+Rect.right], eax
0x18002d90b  jmp     short loc_18002D92B
0x18002d90d  mov     [rbp+Rect.left], eax
0x18002d910  jmp     short loc_18002D92B
0x18002d912  mov     eax, [rbp+Rect.top]
0x18002d915  add     eax, [rbp+Rect.bottom]
0x18002d918  cdq
0x18002d919  sub     eax, edx
0x18002d91b  sar     eax, 1
0x18002d91d  cmp     [rdi+58h], r12d
0x18002d921  jz      short loc_18002D928
0x18002d923  mov     [rbp+Rect.top], eax
0x18002d926  jmp     short loc_18002D92B
0x18002d928  mov     [rbp+Rect.bottom], eax
0x18002d92b  mov     eax, cs:g_cyFrame
0x18002d931  lea     rcx, [rbp+Rect]; lprc
0x18002d935  inc     eax
0x18002d937  cdq
0x18002d938  sub     eax, edx
0x18002d93a  sar     eax, 1
0x18002d93c  mov     r8d, eax; dy
0x18002d93f  mov     eax, cs:g_cxFrame
0x18002d945  inc     eax
0x18002d947  cdq
0x18002d948  sub     eax, edx
0x18002d94a  sar     eax, 1
0x18002d94c  mov     edx, eax; dx
0x18002d94e  call    cs:__imp_InflateRect
0x18002d954  lea     rcx, [rbp+Point]; lpPoint
0x18002d958  call    cs:__imp_GetCursorPos
0x18002d95e  mov     rdx, qword ptr [rbp+Point.x]; pt
0x18002d962  lea     rcx, [rbp+Rect]; lprc
0x18002d966  call    cs:__imp_PtInRect
0x18002d96c  mov     rcx, rdi
0x18002d96f  test    eax, eax
0x18002d971  jz      short loc_18002D98A
0x18002d973  mov     r8d, [rdi+58h]
0x18002d977  mov     edx, r12d
0x18002d97a  test    r8d, r8d
0x18002d97d  setz    dl
0x18002d980  call    squish
0x18002d985  jmp     loc_18002DB37
0x18002d98a  xor     r8d, r8d
0x18002d98d  xor     edx, edx
0x18002d98f  call    squish
0x18002d994  jmp     loc_18002D7C8
0x18002d999  mov     eax, r14d
0x18002d99c  sub     eax, 128h
0x18002d9a1  jz      loc_18002DB8C
0x18002d9a7  sub     eax, 0D8h
0x18002d9ac  jz      loc_18002DB44
0x18002d9b2  sub     eax, r13d
0x18002d9b5  jz      loc_18002DA88
0x18002d9bb  sub     eax, r13d
0x18002d9be  jz      short loc_18002D9F8
0x18002d9c0  sub     eax, 0A1h
0x18002d9c5  jz      short loc_18002D9E0
0x18002d9c7  cmp     eax, 75h ; 'u'
0x18002d9ca  jnz     loc_18002DD96
0x18002d9d0  mov     rdx, rbx
0x18002d9d3  mov     rcx, rdi
0x18002d9d6  call    PaintUpDownControl
0x18002d9db  jmp     loc_18002D7C8
0x18002d9e0  and     dword ptr [rdi+40h], 0FFFFFFBFh
0x18002d9e4  mov     rcx, rdi
0x18002d9e7  mov     edx, [rdi+7Ch]
0x18002d9ea  call    UD_Invalidate
0x18002d9ef  mov     [rdi+7Ch], r12d
0x18002d9f3  jmp     loc_18002D7C8
0x18002d9f8  mov     rcx, [rdi+38h]; hWnd
0x18002d9fc  test    rcx, rcx
0x18002d9ff  jz      short loc_18002DA0F
0x18002da01  call    cs:__imp_IsWindowEnabled
0x18002da07  test    eax, eax
0x18002da09  jz      loc_18002D7C8
0x18002da0f  call    cs:__imp_GetCapture
0x18002da15  cmp     rax, r15
0x18002da18  jnz     loc_18002D7C8
0x18002da1e  xor     r8d, r8d
0x18002da21  xor     edx, edx
0x18002da23  mov     rcx, rdi
0x18002da26  call    squish
0x18002da2b  call    cs:__imp_ReleaseCapture
0x18002da31  mov     rdx, r13; uIDEvent
0x18002da34  mov     rcx, r15; hWnd
0x18002da37  call    cs:__imp_KillTimer
0x18002da3d  cmp     [rdi+54h], r13d
0x18002da41  jnz     short loc_18002DA59
0x18002da43  mov     rcx, [rdi+38h]; hWnd
0x18002da47  or      r9, 0FFFFFFFFFFFFFFFFh; lParam
0x18002da4b  xor     r8d, r8d; wParam
0x18002da4e  mov     edx, 0B1h; Msg
0x18002da53  call    cs:__imp_SendMessageW
0x18002da59  movzx   r8d, word ptr [rdi+50h]
0x18002da5e  mov     edx, 114h
0x18002da63  mov     rcx, [rdi+8]; hWnd
0x18002da67  mov     r9, [rdi]; lParam
0x18002da6a  shl     r8, 10h
0x18002da6e  or      r8, 8; wParam
0x18002da72  test    byte ptr [rdi+10h], 40h
0x18002da76  jnz     short loc_18002DA7D
0x18002da78  mov     edx, 115h; Msg
0x18002da7d  call    cs:__imp_SendMessageW
0x18002da83  jmp     loc_18002D7C8
0x18002da88  mov     rcx, [rdi+38h]; hWnd
0x18002da8c  test    rcx, rcx
0x18002da8f  jz      short loc_18002DA9F
0x18002da91  call    cs:__imp_IsWindowEnabled
0x18002da97  test    eax, eax
0x18002da99  jz      loc_18002D7C8
0x18002da9f  mov     rcx, r15; hWnd
0x18002daa2  call    cs:__imp_SetCapture
0x18002daa8  xor     edx, edx
0x18002daaa  mov     rcx, rdi
0x18002daad  call    getint
0x18002dab2  mov     ecx, [rdi+54h]
0x18002dab5  sub     ecx, r13d
0x18002dab8  jz      short loc_18002DABF
0x18002daba  cmp     ecx, r13d
0x18002dabd  jnz     short loc_18002DAC9
0x18002dabf  mov     rcx, [rdi+38h]; hWnd
0x18002dac3  call    cs:__imp_SetFocus
0x18002dac9  mov     rax, rsi
0x18002dacc  movsx   edx, si
0x18002dacf  shr     rax, 10h
0x18002dad3  mov     rcx, rdi
  ... truncated ...
```
