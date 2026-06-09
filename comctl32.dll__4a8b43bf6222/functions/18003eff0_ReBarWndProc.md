# ReBarWndProc

- ea: `0x18003eff0`
- end: `0x18003ff88`
- name: `ReBarWndProc`
- size: `3992`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, HDC hdc, LPRECT lprc)`
- caller_count: `0`
- callee_count: `58`
- tags: ``

## callees

- `0x1800115f0`
- `0x180017aa8`
- `0x180017bac`
- `0x180017cac`
- `0x180018090`
- `0x180018158`
- `0x1800183dc`
- `0x180018464`
- `0x1800184b8`
- `0x180018e04`
- `0x1800190a4`
- `0x18001923c`
- `0x180019aa8`
- `0x180035f8c`
- `0x180035fe0`
- `0x180037080`
- `0x18003a530`
- `0x18003a700`
- `0x18003a814`
- `0x18003a8a0`
- `0x18003ac04`
- `0x18003ac68`
- `0x18003ae28`
- `0x18003aed8`
- `0x18003b7f0`
- `0x18003bb78`
- `0x18003bc34`
- `0x18003bf48`
- `0x18003c14c`
- `0x18003c184`
- `0x18003c1f4`
- `0x18003c3d8`
- `0x18003c7e8`
- `0x18003c9a8`
- `0x18003ca78`
- `0x18003cc4c`
- `0x18003ccb0`
- `0x18003cde4`
- `0x18003ced8`
- `0x18003cfb8`
- `0x18003d0dc`
- `0x18003d1d0`
- `0x18003d820`
- `0x18003dcf0`
- `0x18003dd5c`
- `0x18003e504`
- `0x18003e5bc`
- `0x18003e684`
- `0x18003e754`
- `0x18003e7c4`

## import_xrefs

- `GDI32!DeleteObject` at `0x18003f306`
- `GDI32!DeleteObject` at `0x18003f306`
- `KERNEL32!LocalFree` at `0x18003fa25`
- `KERNEL32!LocalFree` at `0x18003fac8`
- `KERNEL32!LocalFree` at `0x18003fa25`
- `KERNEL32!LocalFree` at `0x18003fac8`
- `KERNEL32!LocalAlloc` at `0x18003f347`
- `KERNEL32!LocalAlloc` at `0x18003f347`
- `KERNEL32!WideCharToMultiByte` at `0x18003fabb`
- `KERNEL32!WideCharToMultiByte` at `0x18003fabb`
- `USER32!ReleaseDC` at `0x18003f5fe`
- `USER32!ReleaseDC` at `0x18003f5fe`
- `USER32!SetCapture` at `0x18003f85f`
- `USER32!SetCapture` at `0x18003f85f`
- `USER32!SendMessageW` at `0x18003f180`
- `USER32!SendMessageW` at `0x18003f588`
- `USER32!SendMessageW` at `0x18003f98f`
- `USER32!SendMessageW` at `0x18003f180`
- `USER32!SendMessageW` at `0x18003f588`
- `USER32!SendMessageW` at `0x18003f98f`
- `USER32!ScreenToClient` at `0x18003f624`
- `USER32!ScreenToClient` at `0x18003f624`
- `USER32!SetWindowLongW` at `0x18003f3c2`
- `USER32!SetWindowLongW` at `0x18003f3c2`
- `USER32!SetWindowLongPtrW` at `0x18003f23e`
- `USER32!SetWindowLongPtrW` at `0x18003f361`
- `USER32!SetWindowLongPtrW` at `0x18003f23e`
- `USER32!SetWindowLongPtrW` at `0x18003f361`
- `USER32!CreateWindowExW` at `0x18003f976`
- `USER32!CreateWindowExW` at `0x18003f976`
- `USER32!InvalidateRect` at `0x18003f193`
- `USER32!InvalidateRect` at `0x18003f570`
- `USER32!InvalidateRect` at `0x18003fb13`
- `USER32!InvalidateRect` at `0x18003fec2`
- `USER32!InvalidateRect` at `0x18003f193`
- `USER32!InvalidateRect` at `0x18003f570`
- `USER32!InvalidateRect` at `0x18003fb13`
- `USER32!InvalidateRect` at `0x18003fec2`
- `USER32!GetWindowLongPtrW` at `0x18003f025`
- `USER32!GetWindowLongPtrW` at `0x18003f935`
- `USER32!GetWindowLongPtrW` at `0x18003f025`
- `USER32!GetWindowLongPtrW` at `0x18003f935`
- `USER32!DefWindowProcW` at `0x18003f0d9`
- `USER32!DefWindowProcW` at `0x18003f1bd`
- `USER32!DefWindowProcW` at `0x18003f0d9`
- `USER32!DefWindowProcW` at `0x18003f1bd`
- `USER32!InflateRect` at `0x18003f6a1`
- `USER32!InflateRect` at `0x18003f6a1`
- `USER32!GetWindowDC` at `0x18003f5cd`
- `USER32!GetWindowDC` at `0x18003f5cd`
- `USER32!PostMessageW` at `0x18003f257`
- `USER32!PostMessageW` at `0x18003f257`
- `USER32!OffsetRect` at `0x18003f5c4`
- `USER32!OffsetRect` at `0x18003f5c4`
- `USER32!GetWindowRect` at `0x18003f5ae`
- `USER32!GetWindowRect` at `0x18003f5ae`

## pseudocode

```c
__int64 __fastcall ReBarWndProc(HDC hWnd, UINT Msg, __int64 hdc, __int64 lprc)
{
  __int64 v8; // rdx
  _QWORD *WindowLongPtrW; // rdi
  int v10; // r9d
  char *v11; // r13
  __int64 v12; // rcx
  __int64 v13; // r14
  HWND v14; // rcx
  unsigned __int64 v15; // rbx
  __int64 v16; // r9
  HWND v17; // rcx
  UINT v18; // edx
  HWND v19; // rcx
  __int64 result; // rax
  HLOCAL v21; // rax
  __int64 v22; // rdi
  int v23; // r8d
  LONG v24; // r8d
  unsigned int j; // ebx
  HDC WindowDC; // rbx
  HWND v27; // rcx
  int v28; // eax
  LRESULT v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rsi
  char *v32; // rbx
  __int64 v33; // r9
  __int64 v34; // r8
  bool v35; // zf
  LONG left; // eax
  HINSTANCE hInstance; // rax
  HWND Window; // rax
  __int64 v39; // r12
  __int64 v40; // rax
  int v41; // eax
  int v42; // edi
  void *v43; // r14
  CHAR *v44; // r12
  __int64 v45; // rax
  __int64 v46; // rsi
  unsigned int v47; // ebx
  unsigned int v48; // r9d
  unsigned int v49; // r8d
  __int64 v50; // r10
  unsigned int i; // ecx
  __int64 v52; // rcx
  __int64 v53; // rdx
  int *v54; // r14
  int v55; // ecx
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 DragProxy; // rax
  _BYTE lParam[112]; // [rsp+60h] [rbp-79h] BYREF
  struct tagRECT Rect; // [rsp+D0h] [rbp-9h] BYREF

  WindowLongPtrW = (_QWORD *)GetWindowLongPtrW((HWND)hWnd, 0);
  v11 = 0;
  if ( !WindowLongPtrW && Msg != 129 )
    return DefWindowProcW((HWND)hWnd, Msg, hdc, lprc);
  v12 = 1028;
  if ( Msg > 0x404 )
  {
    if ( Msg > 0x42B )
    {
      if ( Msg == 8194 )
      {
        if ( lprc )
        {
          if ( *(_DWORD *)lprc == 12 )
          {
            *((_DWORD *)WindowLongPtrW + 45) = *(_DWORD *)(lprc + 4);
            *((_DWORD *)WindowLongPtrW + 46) = *(_DWORD *)(lprc + 8);
            InvalidateRect((HWND)hWnd, 0, 0);
            if ( (WindowLongPtrW[2] & 0x800000) != 0 )
              CCInvalidateFrame(hWnd);
          }
        }
        return 0;
      }
      if ( Msg != 8195 )
      {
        if ( Msg != 8196 )
          goto LABEL_224;
        v57 = WindowLongPtrW[9];
        if ( v57
          || (DragProxy = CreateDragProxy(*WindowLongPtrW, RebarDragCallback, 0),
              WindowLongPtrW[9] = DragProxy,
              (v57 = DragProxy) != 0) )
        {
          *(_QWORD *)lprc = v57;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 8LL))(v57);
        }
        else
        {
          *(_QWORD *)lprc = 0;
        }
        return 0;
      }
      if ( lprc && *(_DWORD *)lprc == 12 )
      {
        *(_QWORD *)lprc = WindowLongPtrW[22];
        *(_DWORD *)(lprc + 8) = *((_DWORD *)WindowLongPtrW + 46);
      }
      return lprc;
    }
    if ( Msg != 1067 )
    {
      switch ( Msg )
      {
        case 0x405u:
        case 0x41Cu:
          LODWORD(result) = RBGetBandInfo(WindowLongPtrW, (unsigned int)hdc, lprc);
          return (int)result;
        case 0x406u:
          goto LABEL_144;
        case 0x407u:
          result = WindowLongPtrW[1];
          WindowLongPtrW[1] = hdc;
          return result;
        case 0x408u:
          LODWORD(result) = RBHitTest(WindowLongPtrW, lprc);
          return (int)result;
        case 0x409u:
          if ( (unsigned int)hdc >= *((_DWORD *)WindowLongPtrW + 22) )
            return 0;
          v52 = WindowLongPtrW[19];
          v53 = 144LL * (int)hdc;
          *(_DWORD *)lprc = *(_DWORD *)(v53 + v52 + 64);
          *(_DWORD *)(lprc + 4) = *(_DWORD *)(v53 + v52 + 68);
          *(_DWORD *)(lprc + 8) = *(_DWORD *)(v53 + v52 + 64) + *(_DWORD *)(v53 + v52 + 72);
          *(_DWORD *)(lprc + 12) = *(_DWORD *)(v53 + v52 + 68) + *(_DWORD *)(v53 + v52 + 76);
          return 1;
        case 0x40Au:
          goto LABEL_156;
        case 0x40Bu:
          LODWORD(result) = RBSetBandInfo(WindowLongPtrW, (unsigned int)hdc, lprc, 1);
          return (int)result;
        case 0x40Cu:
          return *((unsigned int *)WindowLongPtrW + 22);
        case 0x40Du:
          v48 = *((_DWORD *)WindowLongPtrW + 22);
          v49 = 0;
          if ( v48 )
          {
            v50 = WindowLongPtrW[19];
            for ( i = 0; i < v48; ++i )
            {
              if ( (*(_BYTE *)(v50 + 144LL * i) & 8) == 0 && !*(_DWORD *)(v50 + 144LL * i + 64) )
                ++v49;
            }
          }
          return v49;
        case 0x40Eu:
          return RBGetRowHeight(WindowLongPtrW, (unsigned int)hdc);
        case 0x410u:
          memset(&lParam[8], 0, 0x68u);
          v47 = 0;
          *(_QWORD *)lParam = 0x10000000070LL;
          if ( !*((_DWORD *)WindowLongPtrW + 22) )
            return -1;
          break;
        case 0x411u:
          return WindowLongPtrW[10];
        case 0x412u:
          WindowLongPtrW[10] = hdc;
          return 0;
        case 0x413u:
          v46 = *((unsigned int *)WindowLongPtrW + 40);
          *((_DWORD *)WindowLongPtrW + 40) = lprc;
          if ( (_DWORD)v46 != (_DWORD)lprc )
            InvalidateRect((HWND)*WindowLongPtrW, 0, 1);
          return v46;
        case 0x414u:
          return *((unsigned int *)WindowLongPtrW + 40);
        case 0x415u:
          result = *((unsigned int *)WindowLongPtrW + 41);
          *((_DWORD *)WindowLongPtrW + 41) = lprc;
          return result;
        case 0x416u:
          return *((unsigned int *)WindowLongPtrW + 41);
        case 0x417u:
          return RBSizeBarToRect(WindowLongPtrW, lprc);
        case 0x418u:
          if ( (unsigned int)hdc >= *((_DWORD *)WindowLongPtrW + 22) )
            return 0;
          if ( lprc != -2 )
          {
            v54 = (int *)WindowLongPtrW + 35;
            if ( lprc == -1 )
            {
              GetMessagePosClient((HWND)*WindowLongPtrW, (LPPOINT)((char *)WindowLongPtrW + 140));
            }
            else
            {
              *v54 = (__int16)lprc;
              *((_DWORD *)WindowLongPtrW + 36) = SWORD1(lprc);
            }
            if ( *((char *)WindowLongPtrW + 16) < 0 )
            {
              v55 = *v54;
              *v54 = *((_DWORD *)WindowLongPtrW + 36);
              *((_DWORD *)WindowLongPtrW + 36) = v55;
            }
          }
          v56 = (unsigned int)hdc;
          *((_DWORD *)WindowLongPtrW + 37) = *(_DWORD *)(WindowLongPtrW[19] + 144LL * (unsigned int)hdc + 64);
          goto LABEL_202;
        case 0x419u:
          v56 = 0xFFFFFFFFLL;
LABEL_202:
          RBOnBeginDrag(WindowLongPtrW, v56);
          return 0;
        case 0x41Au:
          if ( *((_DWORD *)WindowLongPtrW + 34) != -1 )
          {
            if ( lprc == -1 )
              LODWORD(lprc) = GetMessagePosClient((HWND)*WindowLongPtrW, 0);
            RBDragBand(WindowLongPtrW, (unsigned int)(__int16)lprc, (unsigned int)SWORD1(lprc));
          }
          return 0;
        case 0x41Bu:
          if ( !*((_DWORD *)WindowLongPtrW + 22) || *((_DWORD *)WindowLongPtrW + 33) )
            LODWORD(result) = *((_DWORD *)WindowLongPtrW + 33);
          else
            LODWORD(result) = RBRecalc(WindowLongPtrW);
          return (unsigned int)result;
        case 0x41Du:
          v43 = 0;
          v44 = *(CHAR **)(lprc + 24);
          if ( (*(_BYTE *)(lprc + 4) & 4) == 0 )
            goto LABEL_161;
          v45 = CCLocalAllocArray_WCHAR(*(unsigned int *)(lprc + 32));
          v43 = (void *)v45;
          if ( !v45 )
            return 0;
          *(_QWORD *)(lprc + 24) = v45;
LABEL_161:
          v46 = (int)RBGetBandInfo(WindowLongPtrW, (unsigned int)hdc, lprc);
          if ( v43 )
          {
            WideCharToMultiByte(
              *((_DWORD *)WindowLongPtrW + 7),
              0,
              *(LPCWCH *)(lprc + 24),
              -1,
              v44,
              *(_DWORD *)(lprc + 32),
              0,
              0);
            *(_QWORD *)(lprc + 24) = v44;
            LocalFree(v43);
          }
          return v46;
        case 0x41Eu:
          RBMinimizeBand(WindowLongPtrW, (unsigned int)hdc, 0);
          return 0;
        case 0x41Fu:
          RBMaximizeBand(WindowLongPtrW, (unsigned int)hdc, lprc != 0, 0);
          return 0;
        case 0x422u:
          return RBGetBandBorders(WindowLongPtrW, (unsigned int)hdc, lprc);
        case 0x423u:
          LODWORD(result) = RBShowBand(WindowLongPtrW, (unsigned int)hdc, lprc != 0);
          return (int)result;
        case 0x424u:
          if ( (WindowLongPtrW[2] & 0x1000) != 0 )
            WindowLongPtrW[9] = CreateDragProxy(*WindowLongPtrW, RebarDragCallback, 1);
          if ( (WindowLongPtrW[2] & 0x100) != 0 )
          {
            memset(&lParam[24], 0, 40);
            *(_QWORD *)lParam = 0x100000040LL;
            *(_QWORD *)&lParam[8] = hWnd;
            *(_QWORD *)&lParam[16] = hWnd;
            hInstance = (HINSTANCE)GetWindowLongPtrW((HWND)hWnd, -6);
            Window = CreateWindowExW(
                       0,
                       L"tooltips_class32",
                       0,
                       0x80000000,
                       0x80000000,
                       0x80000000,
                       0x80000000,
                       0x80000000,
                       (HWND)hWnd,
                       0,
                       hInstance,
                       0);
            WindowLongPtrW[10] = Window;
            SendMessageW(Window, 0x432u, 0, (LPARAM)lParam);
          }
          RBInitPaletteHack((__int64)WindowLongPtrW);
          return 0;
        case 0x425u:
          return RBSetPalette(WindowLongPtrW, lprc);
        case 0x426u:
          return WindowLongPtrW[7];
        case 0x427u:
          if ( (unsigned int)hdc >= *((_DWORD *)WindowLongPtrW + 22)
            || (unsigned int)lprc >= *((_DWORD *)WindowLongPtrW + 22) )
          {
            return 0;
          }
          LODWORD(result) = RBMoveBand(WindowLongPtrW, (unsigned int)hdc, (unsigned int)lprc);
          return (int)result;
        default:
          goto LABEL_224;
      }
      while ( !(unsigned int)RBGetBandInfo(WindowLongPtrW, v47, lParam)
           || *(_DWORD *)&lParam[72] != (unsigned __int16)hdc )
      {
        if ( ++v47 >= *((_DWORD *)WindowLongPtrW + 22) )
          return -1;
      }
      return v47;
    }
    if ( (unsigned int)hdc >= *((_DWORD *)WindowLongPtrW + 22) )
      return 0;
    v33 = lprc;
    v34 = WindowLongPtrW[19] + 144 * hdc;
    goto LABEL_220;
  }
  if ( Msg == 1028 )
  {
    LODWORD(result) = RBSetBarInfo(WindowLongPtrW, lprc);
    return (int)result;
  }
  if ( Msg > 0x81 )
  {
    if ( Msg > 0x203 )
    {
      if ( Msg != 516 )
      {
        if ( Msg != 517 )
        {
          if ( Msg != 783 )
          {
            if ( Msg != 785 )
            {
              if ( Msg == 792 )
                goto LABEL_114;
              if ( Msg != 1025 )
              {
                if ( Msg != 1026 )
                {
                  if ( Msg == 1027 )
                  {
                    if ( !WindowLongPtrW || *(_DWORD *)lprc != 16 )
                      return 0;
                    v13 = 1;
                    if ( (*(_BYTE *)(lprc + 4) & 1) != 0 )
                      *(_QWORD *)(lprc + 8) = WindowLongPtrW[13];
                    return v13;
                  }
                  goto LABEL_224;
                }
                LODWORD(result) = RBDeleteBand(WindowLongPtrW, (unsigned int)hdc);
                return (int)result;
              }
LABEL_144:
              if ( !lprc )
              {
LABEL_156:
                LODWORD(result) = RBInsertBand(WindowLongPtrW, (unsigned int)hdc, lprc);
                return (int)result;
              }
              v39 = *(_QWORD *)(lprc + 24);
              if ( (*(_BYTE *)(lprc + 4) & 4) != 0 && v39 )
              {
                v40 = ProduceWFromA(*((_DWORD *)WindowLongPtrW + 7), *(LPCCH *)(lprc + 24));
                v11 = (char *)v40;
                if ( !v40 )
                  return -1;
                *(_QWORD *)(lprc + 24) = v40;
              }
              if ( Msg == 1025 )
                v41 = RBInsertBand(WindowLongPtrW, (unsigned int)hdc, lprc);
              else
                v41 = RBSetBandInfo(WindowLongPtrW, (unsigned int)hdc, lprc, 1);
              v42 = v41;
              *(_QWORD *)(lprc + 24) = v39;
              if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                LocalFree(v11);
              return v42;
            }
            if ( (HDC)hdc == hWnd )
              return 0;
          }
          RBRealize(WindowLongPtrW, 0, Msg == 785, Msg == 785);
          return 1;
        }
        if ( (WindowLongPtrW[8] & 0x840) == 0 )
        {
          CCReleaseCapture(WindowLongPtrW);
          RBOnBeginDrag(WindowLongPtrW, 0xFFFFFFFFLL);
          return DefWindowProcW((HWND)hWnd, Msg, hdc, lprc);
        }
LABEL_77:
        RelayToToolTips(WindowLongPtrW[10], (_DWORD)hWnd, Msg, hdc, lprc);
        if ( *((_DWORD *)WindowLongPtrW + 34) != -1 )
        {
          if ( (WindowLongPtrW[8] & 0x40) == 0 )
            CCReleaseCapture(WindowLongPtrW);
          if ( (WindowLongPtrW[2] & 0x8000) == 0 && (WindowLongPtrW[8] & 0x800) == 0 )
            RBToggleBand(WindowLongPtrW);
          *(_DWORD *)(144LL * *((int *)WindowLongPtrW + 34) + WindowLongPtrW[19]) &= ~0x80000000;
          CCSendNotify((__int64)WindowLongPtrW, -833, 0);
          RBSendNotify(WindowLongPtrW, *((unsigned int *)WindowLongPtrW + 34), 4294966460LL);
          RBOnBeginDrag(WindowLongPtrW, 0xFFFFFFFFLL);
          for ( j = 0; j < *((_DWORD *)WindowLongPtrW + 22); ++j )
          {
            if ( (*(_BYTE *)(WindowLongPtrW[19] + 144LL * j) & 8) == 0 )
              RBBCalcMinWidth(WindowLongPtrW);
          }
          RBSizeBandsToRect(WindowLongPtrW, 0);
          RBInvalidateRect(WindowLongPtrW, 0);
        }
        return 0;
      }
    }
    else if ( Msg != 515 )
    {
      switch ( Msg )
      {
        case 0x83u:
          if ( (WindowLongPtrW[2] & 0x800000) == 0 )
            return DefWindowProcW((HWND)hWnd, Msg, hdc, lprc);
          InflateRect((LPRECT)lprc, -g_cxEdge, -g_cyEdge);
          return 0;
        case 0x84u:
          v27 = (HWND)*WindowLongPtrW;
          Rect.left = (__int16)lprc;
          Rect.top = SWORD1(lprc);
          *(_QWORD *)&Rect.right = 0;
          ScreenToClient(v27, (LPPOINT)&Rect);
          memset(lParam, 0, 24);
          *(_QWORD *)&lParam[32] = 0;
          v28 = RBHitTest(WindowLongPtrW, &Rect);
          *(_QWORD *)&lParam[40] = *(_QWORD *)&Rect.left;
          *(_QWORD *)&lParam[24] = v28;
          *(_QWORD *)&lParam[48] = (unsigned int)Rect.right;
          v29 = CCSendNotify((__int64)WindowLongPtrW, -14, (LPARAM)lParam);
          v13 = 1;
          if ( v29 )
            return v29;
          return v13;
        case 0x85u:
          if ( (WindowLongPtrW[2] & 0x800000) == 0 )
            return DefWindowProcW((HWND)hWnd, Msg, hdc, lprc);
          Rect = 0;
          GetWindowRect((HWND)hWnd, &Rect);
          OffsetRect(&Rect, -Rect.left, -Rect.top);
          WindowDC = GetWindowDC((HWND)hWnd);
          CCDrawEdge(WindowDC, &Rect, (__int64)(WindowLongPtrW + 22));
          ReleaseDC((HWND)hWnd, WindowDC);
          return 0;
        case 0x111u:
          goto LABEL_91;
        case 0x128u:
          if ( (unsigned int)CCOnUIState(WindowLongPtrW, v8, hdc) )
            InvalidateRect((HWND)hWnd, 0, 1);
          return DefWindowProcW((HWND)hWnd, Msg, hdc, lprc);
        case 0x200u:
          RBOnMouseMove((HWND)hWnd, (__int64)WindowLongPtrW);
          return 0;
      }
      if ( Msg != 513 )
      {
        if ( Msg != 514 )
          goto LABEL_224;
        goto LABEL_77;
      }
    }
    v30 = WindowLongPtrW[10];
    Rect.left = (__int16)lprc;
    Rect.bottom = 0;
    *(_QWORD *)&Rect.top = (unsigned int)SWORD1(lprc);
    RelayToToolTips(v30, (_DWORD)hWnd, Msg, hdc, lprc);
    v31 = (int)RBHitTest(WindowLongPtrW, &Rect);
    if ( (_DWORD)v31 == -1 )
      return 0;
    v32 = (char *)(WindowLongPtrW[19] + 144 * v31);
    if ( !v32 )
      return 0;
    if ( (Rect.right & 8) == 0 )
    {
      if ( Rect.right != 3
        && (*(_DWORD *)v32 & 0x100) == 0
        && (*v32 < 0 || (unsigned int)RBCanBandMove(WindowLongPtrW, WindowLongPtrW[19] + 144 * v31)) )
      {
        v35 = *((_BYTE *)WindowLongPtrW + 16) >= 0;
        left = Rect.left;
        *(_QWORD *)((char *)WindowLongPtrW + 140) = *(_QWORD *)&Rect.left;
        *((_DWORD *)WindowLongPtrW + 34) = v31;
        if ( !v35 )
        {
          *((_DWORD *)WindowLongPtrW + 35) = *((_DWORD *)WindowLongPtrW + 36);
          *((_DWORD *)WindowLongPtrW + 36) = left;
        }
        *((_DWORD *)WindowLongPtrW + 37) = *((_DWORD *)v32 + 16);
        SetCapture((HWND)hWnd);
        *((_DWORD *)WindowLongPtrW + 16) &= ~0x800u;
        if ( Msg == 515 && (WindowLongPtrW[2] & 0x8000) != 0 )
          RBToggleBand(WindowLongPtrW);
      }
      return 0;
    }
    v33 = 0;
    v34 = WindowLongPtrW[19] + 144 * v31;
LABEL_220:
    RBOnPushChevron(v12, WindowLongPtrW, v34, v33);
    return 0;
  }
  v13 = 1;
  if ( Msg == 129 )
  {
    CCCreateWindow();
    InitGlobalColors();
    v21 = LocalAlloc(0x40u, 0xD0u);
    v22 = (__int64)v21;
    if ( v21 )
    {
      SetWindowLongPtrW((HWND)hWnd, 0, (LONG_PTR)v21);
      *(_DWORD *)(v22 + 64) |= 0x28u;
      *(_DWORD *)(v22 + 184) = -16777216;
      *(_DWORD *)(v22 + 180) = -16777216;
      *(_DWORD *)(v22 + 136) = -1;
      *(_QWORD *)(v22 + 160) = -1;
      *(_DWORD *)(v22 + 176) = 12;
      CIInitialize(v22, hWnd, lprc);
      v23 = *(_DWORD *)(v22 + 16);
      if ( (v23 & 3) == 0 )
      {
        v24 = v23 | 1;
        *(_DWORD *)(v22 + 16) = v24;
        SetWindowLongW((HWND)hWnd, -16, v24);
      }
      RBSetFont(v22, 0);
      if ( *(_QWORD *)lprc )
        RBSetBarInfo(v22, *(_QWORD *)lprc);
      return v13;
    }
    return 0;
  }
  if ( Msg <= 0x2B )
  {
    if ( Msg != 43 )
    {
      switch ( Msg )
      {
        case 1u:
          PostMessageW((HWND)hWnd, 0x424u, 0, 0);
          return DefWindowProcW((HWND)hWnd, Msg, hdc, lprc);
        case 2u:
          _InterlockedAdd(&g_dwWindowCount, 0xFFFFFFFF);
          RBDestroy(WindowLongPtrW);
          SetWindowLongPtrW((HWND)hWnd, 0, 0);
          break;
        case 5u:
          RBAutoSize(WindowLongPtrW);
          RBResize(WindowLongPtrW, 0);
          break;
        case 0xBu:
          if ( (__int64)WindowLongPtrW[5] >= 5 )
          {
            *((_DWORD *)WindowLongPtrW + 16) &= ~0x20u;
            *((_DWORD *)WindowLongPtrW + 16) |= hdc != 0 ? 0x20 : 0;
            if ( hdc )
            {
              if ( (WindowLongPtrW[8] & 0x10) != 0 )
                RBRecalc(WindowLongPtrW);
            }
          }
          LODWORD(result) = RBSetRedraw(WindowLongPtrW, hdc != 0);
          return (int)result;
        case 0xFu:
LABEL_114:
          RBPaint(WindowLongPtrW, hdc);
          return 0;
        case 0x14u:
          if ( (unsigned int)RBEraseBkgnd((int)WindowLongPtrW, (HDC)hdc) )
            return v13;
          return DefWindowProcW((HWND)hWnd, Msg, hdc, lprc);
        case 0x15u:
          RBInitPaletteHack((__int64)WindowLongPtrW);
          v19 = (HWND)WindowLongPtrW[10];
          if ( v19 )
            SendMessageW(v19, 0x15u, hdc, lprc);
          InitGlobalColors();
          InvalidateRect((HWND)*WindowLongPtrW, 0, 1);
          return 0;
        case 0x1Au:
          InitGlobalMetrics(hdc);
          if ( (WindowLongPtrW[8] & 0x400) != 0 )
            RBSetFont((__int64)WindowLongPtrW, hdc);
          v17 = (HWND)WindowLongPtrW[10];
          if ( !v17 )
            return 0;
          v18 = 26;
          goto LABEL_92;
        case 0x20u:
          if ( !DefWindowProcW((HWND)hWnd, 0x20u, hdc, lprc) && hWnd == (HDC)hdc )
          {
            v14 = (HWND)*WindowLongPtrW;
            *(_QWORD *)&Rect.left = 0;
            GetMessagePosClient(v14, (LPPOINT)&Rect);
            v15 = (unsigned __int64)lprc >> 16;
            if ( (_WORD)v15 == 513 || (v16 = 0, (_WORD)v15 == 516) )
              v16 = 1;
            RBSetCursor(WindowLongPtrW, (unsigned int)Rect.left, (unsigned int)Rect.top, v16);
          }
          return v13;
        default:
LABEL_224:
          *(_QWORD *)&Rect.left = 0;
          if ( (unsigned int)CCWndProc((_DWORD)WindowLongPtrW, Msg, hdc, v10, (__int64)&Rect) )
            return *(_QWORD *)&Rect.left;
          return DefWindowProcW((HWND)hWnd, Msg, hdc, lprc);
      }
      return 0;
    }
LABEL_91:
    v17 = (HWND)WindowLongPtrW[1];
    v18 = Msg;
LABEL_92:
    SendMessageW(v17, v18, hdc, lprc);
    return 0;
  }
  if ( Msg == 44 || Msg == 46 || Msg == 47 )
    goto LABEL_91;
  if ( Msg == 48 )
  {
    if ( (WindowLongPtrW[8] & 0x400) != 0 )
      DeleteObject((HGDIOBJ)WindowLongPtrW[15]);
    *((_DWORD *)WindowLongPtrW + 16) &= ~0x400u;
    WindowLongPtrW[15] = hdc;
    if ( hdc )
      RBAfterSetFont(WindowLongPtrW);
    else
      RBSetFont((__int64)WindowLongPtrW, 0);
    return 0;
  }
  if ( Msg != 49 )
  {
    if ( Msg == 78 )
      return SendNotifyEx(WindowLongPtrW[1], -1, *(unsigned int *)(lprc + 16), lprc, WindowLongPtrW[3] & 1);
    if ( Msg == 85 )
      return CIHandleNotifyFormat(WindowLongPtrW, lprc);
    if ( Msg != 125 )
      goto LABEL_224;
    RBOnStyleChanged(WindowLongPtrW, hdc, lprc);
    return 0;
  }
  if ( WindowLongPtrW )
    return WindowLongPtrW[15];
  else
    return 0;
}

```

## disassembly

```asm
0x18003eff0  push    rbp
0x18003eff2  push    rbx
0x18003eff3  push    rsi
0x18003eff4  push    rdi
0x18003eff5  push    r12
0x18003eff7  push    r13
0x18003eff9  push    r14
0x18003effb  push    r15
0x18003effd  lea     rbp, [rsp-1Fh]
0x18003f002  sub     rsp, 0F8h
0x18003f009  mov     rax, cs:__security_cookie
0x18003f010  xor     rax, rsp
0x18003f013  mov     [rbp+57h+var_50], rax
0x18003f017  mov     r15d, edx
0x18003f01a  mov     rbx, r9
0x18003f01d  xor     edx, edx; nIndex
0x18003f01f  mov     rsi, r8
0x18003f022  mov     r12, rcx
0x18003f025  call    cs:__imp_GetWindowLongPtrW
0x18003f02b  mov     rdi, rax
0x18003f02e  xor     r13d, r13d
0x18003f031  mov     eax, 81h
0x18003f036  test    rdi, rdi
0x18003f039  jnz     short loc_18003F044
0x18003f03b  cmp     r15d, eax
0x18003f03e  jnz     loc_18003F1B1
0x18003f044  mov     ecx, 404h
0x18003f049  cmp     r15d, ecx
0x18003f04c  ja      loc_18003F89D
0x18003f052  jz      loc_18003F88D
0x18003f058  cmp     r15d, eax
0x18003f05b  ja      loc_18003F3EA
0x18003f061  mov     r14d, 1
0x18003f067  jz      loc_18003F333
0x18003f06d  cmp     r15d, 2Bh ; '+'
0x18003f071  ja      loc_18003F262
0x18003f077  jz      loc_18003F57B
0x18003f07d  mov     eax, r15d
0x18003f080  sub     eax, r14d
0x18003f083  jz      loc_18003F249
0x18003f089  sub     eax, r14d
0x18003f08c  jz      loc_18003F223
0x18003f092  sub     eax, 3
0x18003f095  jz      loc_18003F20C
0x18003f09b  sub     eax, 6
0x18003f09e  jz      loc_18003F1C8
0x18003f0a4  sub     eax, 4
0x18003f0a7  jz      loc_18003F72A
0x18003f0ad  sub     eax, 5
0x18003f0b0  jz      loc_18003F19E
0x18003f0b6  sub     eax, r14d
0x18003f0b9  jz      loc_18003F164
0x18003f0bf  sub     eax, 5
0x18003f0c2  jz      short loc_18003F131
0x18003f0c4  cmp     eax, 6
0x18003f0c7  jnz     def_18003F8D2; jumptable 000000018003F8D2 default case, cases 1039,1056,1057
0x18003f0cd  mov     r9, rbx; lParam
0x18003f0d0  lea     edx, [rax+1Ah]; Msg
0x18003f0d3  mov     r8, rsi; wParam
0x18003f0d6  mov     rcx, r12; hWnd
0x18003f0d9  call    cs:__imp_DefWindowProcW
0x18003f0df  test    rax, rax
0x18003f0e2  jnz     loc_18003F3E2
0x18003f0e8  cmp     r12, rsi
0x18003f0eb  jnz     loc_18003F3E2
0x18003f0f1  mov     rcx, [rdi]; hWnd
0x18003f0f4  lea     rdx, [rbp+57h+Rect]; lpPoint
0x18003f0f8  mov     qword ptr [rbp+57h+Rect.left], r13
0x18003f0fc  call    GetMessagePosClient
0x18003f101  mov     eax, 201h
0x18003f106  shr     rbx, 10h
0x18003f10a  cmp     bx, ax
0x18003f10d  jz      short loc_18003F11A
0x18003f10f  lea     ecx, [rax+3]
0x18003f112  mov     r9d, r13d
0x18003f115  cmp     bx, cx
0x18003f118  jnz     short loc_18003F11D
0x18003f11a  mov     r9d, r14d
0x18003f11d  mov     r8d, [rbp+57h+Rect.top]
0x18003f121  mov     rcx, rdi
0x18003f124  mov     edx, [rbp+57h+Rect.left]
0x18003f127  call    RBSetCursor
0x18003f12c  jmp     loc_18003F3E2
0x18003f131  mov     rcx, rsi
0x18003f134  call    InitGlobalMetrics
0x18003f139  test    dword ptr [rdi+40h], 400h
0x18003f140  jz      short loc_18003F14D
0x18003f142  mov     rdx, rsi
0x18003f145  mov     rcx, rdi
0x18003f148  call    RBSetFont
0x18003f14d  mov     rcx, [rdi+50h]
0x18003f151  test    rcx, rcx
0x18003f154  jz      loc_18003FED9
0x18003f15a  mov     edx, 1Ah
0x18003f15f  jmp     loc_18003F582
0x18003f164  mov     rcx, rdi
0x18003f167  call    RBInitPaletteHack
0x18003f16c  mov     rcx, [rdi+50h]; hWnd
0x18003f170  test    rcx, rcx
0x18003f173  jz      short loc_18003F186
0x18003f175  mov     r9, rbx; lParam
0x18003f178  mov     r8, rsi; wParam
0x18003f17b  mov     edx, 15h; Msg
0x18003f180  call    cs:__imp_SendMessageW
0x18003f186  call    InitGlobalColors
0x18003f18b  mov     rcx, [rdi]; hWnd
0x18003f18e  mov     r8d, r14d; bErase
0x18003f191  xor     edx, edx; lpRect
0x18003f193  call    cs:__imp_InvalidateRect
0x18003f199  jmp     loc_18003FED9
0x18003f19e  mov     rdx, rsi; hdc
0x18003f1a1  mov     rcx, rdi; int
0x18003f1a4  call    RBEraseBkgnd
0x18003f1a9  test    eax, eax
0x18003f1ab  jnz     loc_18003F3E2
0x18003f1b1  mov     r9, rbx; lParam
0x18003f1b4  mov     r8, rsi; wParam
0x18003f1b7  mov     edx, r15d; Msg
0x18003f1ba  mov     rcx, r12; hWnd
0x18003f1bd  call    cs:__imp_DefWindowProcW
0x18003f1c3  jmp     loc_18003FEDB
0x18003f1c8  cmp     qword ptr [rdi+28h], 5
0x18003f1cd  jl      short loc_18003F1F4
0x18003f1cf  and     dword ptr [rdi+40h], 0FFFFFFDFh
0x18003f1d3  mov     rax, rsi
0x18003f1d6  neg     rax
0x18003f1d9  sbb     ecx, ecx
0x18003f1db  and     ecx, 20h
0x18003f1de  or      [rdi+40h], ecx
0x18003f1e1  test    rsi, rsi
0x18003f1e4  jz      short loc_18003F1F4
0x18003f1e6  test    byte ptr [rdi+40h], 10h
0x18003f1ea  jz      short loc_18003F1F4
0x18003f1ec  mov     rcx, rdi
0x18003f1ef  call    RBRecalc
0x18003f1f4  test    rsi, rsi
0x18003f1f7  mov     edx, r13d
0x18003f1fa  mov     rcx, rdi
0x18003f1fd  setnz   dl
0x18003f200  call    RBSetRedraw
0x18003f205  cdqe
0x18003f207  jmp     loc_18003FEDB
0x18003f20c  mov     rcx, rdi
0x18003f20f  call    RBAutoSize
0x18003f214  xor     edx, edx
0x18003f216  mov     rcx, rdi
0x18003f219  call    RBResize
0x18003f21e  jmp     loc_18003FED9
0x18003f223  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f227  lock add cs:g_dwWindowCount, eax
0x18003f22e  mov     rcx, rdi; hMem
0x18003f231  call    RBDestroy
0x18003f236  xor     r8d, r8d; dwNewLong
0x18003f239  xor     edx, edx; nIndex
0x18003f23b  mov     rcx, r12; hWnd
0x18003f23e  call    cs:__imp_SetWindowLongPtrW
0x18003f244  jmp     loc_18003FED9
0x18003f249  xor     r9d, r9d; lParam
0x18003f24c  xor     r8d, r8d; wParam
0x18003f24f  mov     edx, 424h; Msg
0x18003f254  mov     rcx, r12; hWnd
0x18003f257  call    cs:__imp_PostMessageW
0x18003f25d  jmp     loc_18003F1B1
0x18003f262  mov     eax, r15d
0x18003f265  sub     eax, 2Ch ; ','
0x18003f268  jz      loc_18003F57B
0x18003f26e  sub     eax, 2
0x18003f271  jz      loc_18003F57B
0x18003f277  sub     eax, r14d
0x18003f27a  jz      loc_18003F57B
0x18003f280  sub     eax, r14d
0x18003f283  jz      short loc_18003F2F9
0x18003f285  sub     eax, r14d
0x18003f288  jz      short loc_18003F2E3
0x18003f28a  sub     eax, 1Dh
0x18003f28d  jz      short loc_18003F2C0
0x18003f28f  sub     eax, 7
0x18003f292  jz      short loc_18003F2B0
0x18003f294  cmp     eax, 28h ; '('
0x18003f297  jnz     def_18003F8D2; jumptable 000000018003F8D2 default case, cases 1039,1056,1057
0x18003f29d  mov     r8, rbx
0x18003f2a0  mov     rdx, rsi
0x18003f2a3  mov     rcx, rdi
0x18003f2a6  call    RBOnStyleChanged
0x18003f2ab  jmp     loc_18003FED9
0x18003f2b0  mov     rdx, rbx
0x18003f2b3  mov     rcx, rdi
0x18003f2b6  call    CIHandleNotifyFormat
0x18003f2bb  jmp     loc_18003FEDB
0x18003f2c0  mov     eax, [rdi+18h]
0x18003f2c3  mov     r9, rbx
0x18003f2c6  mov     r8d, [rbx+10h]
0x18003f2ca  and     eax, r14d
0x18003f2cd  mov     rcx, [rdi+8]
0x18003f2d1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003f2d5  mov     [rsp+130h+X], eax
0x18003f2d9  call    SendNotifyEx
0x18003f2de  jmp     loc_18003FEDB
0x18003f2e3  test    rdi, rdi
0x18003f2e6  jz      short loc_18003F2F1
0x18003f2e8  mov     rax, [rdi+78h]
0x18003f2ec  jmp     loc_18003FEDB
0x18003f2f1  mov     rax, r13
0x18003f2f4  jmp     loc_18003FEDB
0x18003f2f9  test    dword ptr [rdi+40h], 400h
0x18003f300  jz      short loc_18003F30C
0x18003f302  mov     rcx, [rdi+78h]; ho
0x18003f306  call    cs:__imp_DeleteObject
0x18003f30c  btr     dword ptr [rdi+40h], 0Ah
0x18003f311  mov     rcx, rdi
0x18003f314  mov     [rdi+78h], rsi
0x18003f318  test    rsi, rsi
0x18003f31b  jnz     short loc_18003F329
0x18003f31d  xor     edx, edx
0x18003f31f  call    RBSetFont
0x18003f324  jmp     loc_18003FED9
0x18003f329  call    RBAfterSetFont
0x18003f32e  jmp     loc_18003FED9
0x18003f333  call    CCCreateWindow
0x18003f338  call    InitGlobalColors
0x18003f33d  mov     edx, 0D0h; uBytes
0x18003f342  mov     ecx, 40h ; '@'; uFlags
0x18003f347  call    cs:__imp_LocalAlloc
0x18003f34d  mov     rdi, rax
0x18003f350  test    rax, rax
0x18003f353  jz      loc_18003FED9
0x18003f359  mov     r8, rax; dwNewLong
0x18003f35c  xor     edx, edx; nIndex
0x18003f35e  mov     rcx, r12; hWnd
0x18003f361  call    cs:__imp_SetWindowLongPtrW
0x18003f367  or      dword ptr [rdi+40h], 28h
0x18003f36b  mov     eax, 0FF000000h
0x18003f370  mov     r8, rbx
0x18003f373  mov     [rdi+0B8h], eax
0x18003f379  mov     rdx, r12
0x18003f37c  mov     [rdi+0B4h], eax
0x18003f382  mov     rcx, rdi
0x18003f385  mov     dword ptr [rdi+88h], 0FFFFFFFFh
0x18003f38f  mov     qword ptr [rdi+0A0h], 0FFFFFFFFFFFFFFFFh
0x18003f39a  mov     dword ptr [rdi+0B0h], 0Ch
0x18003f3a4  call    CIInitialize
0x18003f3a9  mov     r8d, [rdi+10h]
0x18003f3ad  test    r8b, 3
0x18003f3b1  jnz     short loc_18003F3C8
0x18003f3b3  or      r8d, r14d; dwNewLong
0x18003f3b6  mov     edx, 0FFFFFFF0h; nIndex
0x18003f3bb  mov     rcx, r12; hWnd
0x18003f3be  mov     [rdi+10h], r8d
0x18003f3c2  call    cs:__imp_SetWindowLongW
0x18003f3c8  xor     edx, edx
0x18003f3ca  mov     rcx, rdi
0x18003f3cd  call    RBSetFont
0x18003f3d2  mov     rdx, [rbx]
0x18003f3d5  test    rdx, rdx
0x18003f3d8  jz      short loc_18003F3E2
0x18003f3da  mov     rcx, rdi
0x18003f3dd  call    RBSetBarInfo
0x18003f3e2  mov     rax, r14
0x18003f3e5  jmp     loc_18003FEDB
0x18003f3ea  mov     r14d, 203h
0x18003f3f0  cmp     r15d, r14d
0x18003f3f3  ja      loc_18003F6AC
0x18003f3f9  jz      loc_18003F78D
0x18003f3ff  mov     eax, r15d
0x18003f402  sub     eax, 83h
0x18003f407  jz      loc_18003F67F
0x18003f40d  sub     eax, 1
0x18003f410  jz      loc_18003F609
0x18003f416  sub     eax, 1
0x18003f419  jz      loc_18003F593
0x18003f41f  sub     eax, 8Ch
0x18003f424  jz      loc_18003F57B
0x18003f42a  sub     eax, 17h
0x18003f42d  jz      loc_18003F554
0x18003f433  sub     eax, 0D8h
0x18003f438  jz      loc_18003F537
0x18003f43e  sub     eax, 1
0x18003f441  jz      loc_18003F78D
0x18003f447  cmp     eax, 1
0x18003f44a  jnz     def_18003F8D2; jumptable 000000018003F8D2 default case, cases 1039,1056,1057
0x18003f450  mov     rcx, [rdi+50h]
0x18003f454  mov     r9, rsi
0x18003f457  mov     r8d, r15d
0x18003f45a  mov     qword ptr [rsp+130h+X], rbx
0x18003f45f  mov     rdx, r12
0x18003f462  call    RelayToToolTips
0x18003f467  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f46b  cmp     [rdi+88h], eax
0x18003f471  jz      loc_18003FED9
0x18003f477  test    byte ptr [rdi+40h], 40h
0x18003f47b  jnz     short loc_18003F485
0x18003f47d  mov     rcx, rdi
0x18003f480  call    CCReleaseCapture
0x18003f485  test    dword ptr [rdi+10h], 8000h
0x18003f48c  jnz     short loc_18003F49F
0x18003f48e  test    dword ptr [rdi+40h], 800h
0x18003f495  jnz     short loc_18003F49F
0x18003f497  mov     rcx, rdi
0x18003f49a  call    RBToggleBand
0x18003f49f  movsxd  rax, dword ptr [rdi+88h]
  ... truncated ...
```
