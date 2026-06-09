# TrackBarWndProc

- ea: `0x18006e230`
- end: `0x18006ee90`
- name: `TrackBarWndProc`
- size: `3168`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, HDC hdc, LPARAM lParam)`
- caller_count: `0`
- callee_count: `28`
- tags: `broker_com_uri`

## callees

- `0x1800115f0`
- `0x1800180c8`
- `0x180018110`
- `0x180018158`
- `0x1800183dc`
- `0x180018464`
- `0x180018e04`
- `0x1800190a4`
- `0x18001923c`
- `0x18001ac40`
- `0x180035f8c`
- `0x180037080`
- `0x18006cd18`
- `0x18006cda0`
- `0x18006d4a0`
- `0x18006d85c`
- `0x18006d978`
- `0x18006dadc`
- `0x18006dd50`
- `0x18006deb4`
- `0x18006e070`
- `0x18006e0fc`
- `0x18006e230`
- `0x18006ee98`
- `0x1800852a0`
- `0x18008698c`
- `0x18008ea60`
- `0x180090020`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18006e8f9`
- `GDI32!CreateCompatibleDC` at `0x18006e8f9`
- `GDI32!SelectObject` at `0x18006e92f`
- `GDI32!SelectObject` at `0x18006e9a5`
- `GDI32!SelectObject` at `0x18006e92f`
- `GDI32!SelectObject` at `0x18006e9a5`
- `GDI32!BitBlt` at `0x18006e998`
- `GDI32!BitBlt` at `0x18006e998`
- `GDI32!DeleteObject` at `0x18006e3a8`
- `GDI32!DeleteObject` at `0x18006e463`
- `GDI32!DeleteObject` at `0x18006e3a8`
- `GDI32!DeleteObject` at `0x18006e463`
- `GDI32!DeleteDC` at `0x18006e9af`
- `GDI32!DeleteDC` at `0x18006e9af`
- `GDI32!GetClipBox` at `0x18006e947`
- `GDI32!GetClipBox` at `0x18006e947`
- `KERNEL32!LocalFree` at `0x18006e3c4`
- `KERNEL32!LocalFree` at `0x18006e3cd`
- `KERNEL32!LocalFree` at `0x18006eab0`
- `KERNEL32!LocalFree` at `0x18006e3c4`
- `KERNEL32!LocalFree` at `0x18006e3cd`
- `KERNEL32!LocalFree` at `0x18006eab0`
- `USER32!GetClientRect` at `0x18006e913`
- `USER32!GetClientRect` at `0x18006e95d`
- `USER32!GetClientRect` at `0x18006e913`
- `USER32!GetClientRect` at `0x18006e95d`
- `USER32!IsWindow` at `0x18006e388`
- `USER32!IsWindow` at `0x18006e388`
- `USER32!GetCapture` at `0x18006e661`
- `USER32!GetCapture` at `0x18006e661`
- `USER32!DestroyWindow` at `0x18006e399`
- `USER32!DestroyWindow` at `0x18006e399`
- `USER32!SetWindowLongPtrW` at `0x18006e3db`
- `USER32!SetWindowLongPtrW` at `0x18006e3db`
- `USER32!SetFocus` at `0x18006e68d`
- `USER32!SetFocus` at `0x18006e784`
- `USER32!SetFocus` at `0x18006e68d`
- `USER32!SetFocus` at `0x18006e784`
- `USER32!InvalidateRect` at `0x18006e316`
- `USER32!InvalidateRect` at `0x18006e6c2`
- `USER32!InvalidateRect` at `0x18006ea40`
- `USER32!InvalidateRect` at `0x18006ecb6`
- `USER32!InvalidateRect` at `0x18006e316`
- `USER32!InvalidateRect` at `0x18006e6c2`
- `USER32!InvalidateRect` at `0x18006ea40`
- `USER32!InvalidateRect` at `0x18006ecb6`
- `USER32!GetWindowLongPtrW` at `0x18006e272`
- `USER32!GetWindowLongPtrW` at `0x18006e272`
- `USER32!BeginPaint` at `0x18006e8ed`
- `USER32!BeginPaint` at `0x18006e8ed`
- `USER32!EndPaint` at `0x18006e9c1`
- `USER32!EndPaint` at `0x18006e9c1`
- `USER32!DefWindowProcW` at `0x18006e6d3`
- `USER32!DefWindowProcW` at `0x18006e6d3`

## pseudocode

```c
__int64 __fastcall TrackBarWndProc(HWND hWnd, UINT Msg, HDC hdc, LPARAM lParam)
{
  __int64 v8; // rdx
  LONG_PTR WindowLongPtrW; // rsi
  int v10; // r9d
  __int64 result; // rax
  HWND v12; // rcx
  int v13; // eax
  unsigned int v14; // ecx
  int v15; // eax
  void *v16; // rcx
  void *v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  char *v27; // rbx
  char *v28; // rbx
  char *v29; // rbx
  char *v30; // rbx
  char *v31; // rbx
  char *v32; // rbx
  int v33; // edx
  int v34; // r8d
  int v35; // ebx
  int v36; // eax
  __int64 v37; // rax
  HDC v38; // rdi
  void *ColorBitmap; // rax
  HGDIOBJ v40; // r14
  __int64 v41; // rax
  __int64 v42; // rcx
  void *v43; // rcx
  __int64 v44; // rdx
  int v45; // ecx
  unsigned int v46; // ebx
  int v47; // edi
  __int64 v48; // rdx
  int v49; // ecx
  int v50; // eax
  int v51; // edx
  int v52; // ecx
  LPARAM v53; // rcx
  LPARAM v54; // rcx
  int v55; // ecx
  int v56; // eax
  int v57; // edx
  int v58; // ecx
  int v59; // eax
  int v60; // ecx
  __int64 v61; // rbx
  struct tagRECT Rect; // [rsp+50h] [rbp-49h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+60h] [rbp-39h] BYREF

  memset(&Paint, 0, sizeof(Paint));
  WindowLongPtrW = GetWindowLongPtrW(hWnd, 0);
  if ( !WindowLongPtrW )
  {
    if ( Msg == 1 )
      return TrackOnCreate(hWnd);
    return DefWindowProcW(hWnd, Msg, (WPARAM)hdc, lParam);
  }
  if ( Msg > 0x404 )
  {
    switch ( Msg )
    {
      case 0x405u:
        if ( !hdc
          || (v46 = *(_DWORD *)(WindowLongPtrW + 80),
              v47 = TBLogToPhys(WindowLongPtrW, (unsigned int)lParam),
              v47 == (unsigned int)TBLogToPhys(WindowLongPtrW, v46)) )
        {
          v49 = *(_DWORD *)(WindowLongPtrW + 76);
          v50 = v49;
          if ( (int)lParam < v49 )
            v50 = lParam;
          if ( v50 <= *(_DWORD *)(WindowLongPtrW + 72) )
          {
            v49 = *(_DWORD *)(WindowLongPtrW + 72);
          }
          else if ( (int)lParam < v49 )
          {
            v49 = lParam;
          }
          *(_DWORD *)(WindowLongPtrW + 80) = v49;
        }
        else
        {
          v48 = (unsigned int)lParam;
LABEL_230:
          MoveThumb(WindowLongPtrW, v48);
        }
        break;
      case 0x406u:
        *(_DWORD *)(WindowLongPtrW + 76) = SWORD1(lParam);
        *(_DWORD *)(WindowLongPtrW + 72) = (__int16)lParam;
        if ( *(_DWORD *)(WindowLongPtrW + 84) < (__int16)lParam )
          *(_DWORD *)(WindowLongPtrW + 84) = (__int16)lParam;
        if ( *(_DWORD *)(WindowLongPtrW + 88) > SWORD1(lParam) )
          *(_DWORD *)(WindowLongPtrW + 88) = SWORD1(lParam);
        goto LABEL_223;
      case 0x407u:
        *(_DWORD *)(WindowLongPtrW + 72) = lParam;
        if ( *(_DWORD *)(WindowLongPtrW + 84) < (int)lParam )
          *(_DWORD *)(WindowLongPtrW + 84) = lParam;
        goto LABEL_223;
      case 0x408u:
        *(_DWORD *)(WindowLongPtrW + 76) = lParam;
        if ( *(_DWORD *)(WindowLongPtrW + 88) > (int)lParam )
          *(_DWORD *)(WindowLongPtrW + 88) = lParam;
        goto LABEL_223;
      case 0x409u:
        v43 = *(void **)(WindowLongPtrW + 152);
        if ( v43 )
          LocalFree(v43);
        *(_QWORD *)(WindowLongPtrW + 152) = 0;
        *(_DWORD *)(WindowLongPtrW + 144) = 0;
        goto LABEL_224;
      case 0x40Au:
        if ( (*(_BYTE *)(WindowLongPtrW + 16) & 0x20) == 0 )
          return 0;
        *(_DWORD *)(WindowLongPtrW + 192) |= 2u;
        v51 = *(_DWORD *)(WindowLongPtrW + 72);
        if ( (__int16)lParam >= v51 )
          v51 = (__int16)lParam;
        *(_DWORD *)(WindowLongPtrW + 84) = v51;
        v52 = *(_DWORD *)(WindowLongPtrW + 76);
        if ( SWORD1(lParam) <= v52 )
          v52 = SWORD1(lParam);
        *(_DWORD *)(WindowLongPtrW + 88) = v52;
        if ( v52 < v51 )
          *(_DWORD *)(WindowLongPtrW + 88) = v51;
        goto LABEL_224;
      case 0x40Bu:
        if ( (*(_BYTE *)(WindowLongPtrW + 16) & 0x20) == 0 )
          return 0;
        *(_DWORD *)(WindowLongPtrW + 192) |= 2u;
        v53 = *(int *)(WindowLongPtrW + 72);
        if ( lParam >= v53 )
        {
          *(_DWORD *)(WindowLongPtrW + 84) = lParam;
          LODWORD(v53) = lParam;
        }
        else
        {
          *(_DWORD *)(WindowLongPtrW + 84) = v53;
        }
        if ( *(_DWORD *)(WindowLongPtrW + 88) < (int)v53 || *(_DWORD *)(WindowLongPtrW + 88) == -1 )
          *(_DWORD *)(WindowLongPtrW + 88) = v53;
        goto LABEL_224;
      case 0x40Cu:
        if ( (*(_BYTE *)(WindowLongPtrW + 16) & 0x20) == 0 )
          return 0;
        *(_DWORD *)(WindowLongPtrW + 192) |= 2u;
        v54 = *(int *)(WindowLongPtrW + 76);
        if ( lParam <= v54 )
        {
          *(_DWORD *)(WindowLongPtrW + 88) = lParam;
          LODWORD(v54) = lParam;
        }
        else
        {
          *(_DWORD *)(WindowLongPtrW + 88) = v54;
        }
        if ( *(_DWORD *)(WindowLongPtrW + 84) > (int)v54 || *(_DWORD *)(WindowLongPtrW + 84) == -1 )
          *(_DWORD *)(WindowLongPtrW + 84) = v54;
        goto LABEL_224;
      case 0x40Eu:
        return *(_QWORD *)(WindowLongPtrW + 152);
      case 0x40Fu:
        v44 = *(_QWORD *)(WindowLongPtrW + 152);
        if ( !v44 || (int)hdc >= *(_DWORD *)(WindowLongPtrW + 144) )
          return -1;
        LODWORD(result) = TBLogToPhys(WindowLongPtrW, *(unsigned int *)(v44 + 4LL * (_QWORD)hdc));
        return (int)result;
      case 0x410u:
        if ( (*(_BYTE *)(WindowLongPtrW + 16) & 0x10) != 0 )
          return 0;
        v45 = *(_DWORD *)(WindowLongPtrW + 160);
        if ( !v45 )
          return 2;
        LODWORD(result) = *(_DWORD *)(WindowLongPtrW + 144) / v45 + 2;
        return (int)result;
      case 0x411u:
        return *(int *)(WindowLongPtrW + 84);
      case 0x412u:
        return *(int *)(WindowLongPtrW + 88);
      case 0x413u:
        *(_DWORD *)(WindowLongPtrW + 192) &= ~2u;
        *(_QWORD *)(WindowLongPtrW + 84) = -1;
        goto LABEL_224;
      case 0x414u:
        *(_DWORD *)(WindowLongPtrW + 160) = (_DWORD)hdc;
LABEL_223:
        DoAutoTics(WindowLongPtrW);
LABEL_224:
        v55 = *(_DWORD *)(WindowLongPtrW + 80);
        v56 = *(_DWORD *)(WindowLongPtrW + 72);
        if ( v55 >= *(_DWORD *)(WindowLongPtrW + 76) )
          v55 = *(_DWORD *)(WindowLongPtrW + 76);
        if ( v55 > v56 )
          v56 = v55;
        *(_DWORD *)(WindowLongPtrW + 184) |= 0xFu;
        *(_DWORD *)(WindowLongPtrW + 80) = v56;
        if ( !hdc )
          return 0;
        InvalidateRect(hWnd, 0, 0);
        v48 = *(unsigned int *)(WindowLongPtrW + 80);
        goto LABEL_230;
      case 0x415u:
        v57 = *(_DWORD *)(WindowLongPtrW + 164);
        if ( v57 == -1 )
          v57 = (*(_DWORD *)(WindowLongPtrW + 76) - *(_DWORD *)(WindowLongPtrW + 72)) / 5;
        *(_DWORD *)(WindowLongPtrW + 164) = lParam;
        return v57;
      case 0x416u:
        v57 = *(_DWORD *)(WindowLongPtrW + 164);
        if ( v57 == -1 )
          return (*(_DWORD *)(WindowLongPtrW + 76) - *(_DWORD *)(WindowLongPtrW + 72)) / 5;
        return v57;
      case 0x417u:
        result = *(int *)(WindowLongPtrW + 168);
        *(_DWORD *)(WindowLongPtrW + 168) = lParam;
        return result;
      case 0x418u:
        return *(int *)(WindowLongPtrW + 168);
      case 0x419u:
        if ( lParam )
        {
          *(_OWORD *)lParam = *(_OWORD *)(WindowLongPtrW + 120);
          if ( (*(_BYTE *)(WindowLongPtrW + 16) & 2) != 0 )
          {
            v58 = *(_DWORD *)lParam;
            *(_DWORD *)lParam = *(_DWORD *)(lParam + 4);
            v59 = *(_DWORD *)(lParam + 12);
            *(_DWORD *)(lParam + 4) = v58;
            v60 = *(_DWORD *)(lParam + 8);
            *(_DWORD *)(lParam + 8) = v59;
            *(_DWORD *)(lParam + 12) = v60;
          }
        }
        return 0;
      case 0x41Au:
        GetChannelRect(WindowLongPtrW, lParam);
        return 0;
      case 0x41Bu:
        if ( (*(_BYTE *)(WindowLongPtrW + 16) & 0x40) == 0 )
          return 0;
        *(_DWORD *)(WindowLongPtrW + 96) = (_DWORD)hdc;
        goto LABEL_34;
      case 0x41Cu:
        return *(int *)(WindowLongPtrW + 96);
      case 0x41Du:
        *(_QWORD *)(WindowLongPtrW + 176) = hdc;
        return 0;
      case 0x41Eu:
        return *(_QWORD *)(WindowLongPtrW + 176);
      case 0x41Fu:
        result = *(unsigned int *)(WindowLongPtrW + 188);
        *(_DWORD *)(WindowLongPtrW + 188) = (_DWORD)hdc;
        return result;
      case 0x420u:
        if ( (_DWORD)hdc )
        {
          v61 = *(_QWORD *)(WindowLongPtrW + 208);
          *(_QWORD *)(WindowLongPtrW + 208) = lParam;
        }
        else
        {
          v61 = *(_QWORD *)(WindowLongPtrW + 216);
          *(_QWORD *)(WindowLongPtrW + 216) = lParam;
        }
        TBResize(WindowLongPtrW);
        return v61;
      case 0x421u:
        return *(_QWORD *)((-(__int64)(hdc != 0) & 0xFFFFFFFFFFFFFFF8uLL) + WindowLongPtrW + 216);
      default:
        goto LABEL_41;
    }
    return 0;
  }
  if ( Msg == 1028 )
  {
    if ( (int)lParam < *(_DWORD *)(WindowLongPtrW + 72) )
      return 0;
    if ( (int)lParam > *(_DWORD *)(WindowLongPtrW + 76) )
      return 0;
    v41 = CCLocalReAlloc(*(_QWORD *)(WindowLongPtrW + 152), 4LL * *(int *)(WindowLongPtrW + 144) + 4);
    if ( !v41 )
      return 0;
    v42 = *(int *)(WindowLongPtrW + 144);
    *(_QWORD *)(WindowLongPtrW + 152) = v41;
    *(_DWORD *)(v41 + 4 * v42) = lParam;
    ++*(_DWORD *)(WindowLongPtrW + 144);
    *(_DWORD *)(WindowLongPtrW + 184) |= 0xFu;
    InvalidateRect(*(HWND *)WindowLongPtrW, 0, 0);
    return 1;
  }
  if ( Msg <= 0x100 )
  {
    if ( Msg != 256 )
    {
      if ( Msg <= 0x1A )
      {
        switch ( Msg )
        {
          case 0x1Au:
            InitGlobalMetrics((__int64)hdc);
            break;
          case 2u:
            TerminateDitherBrush();
            if ( g_fDBCSInputEnabled && g_pfnImmAssociateContext )
              g_pfnImmAssociateContext(hWnd, *(_QWORD *)(WindowLongPtrW + 200));
            if ( (*(_DWORD *)(WindowLongPtrW + 16) & 0x100) != 0 && IsWindow(*(HWND *)(WindowLongPtrW + 176)) )
              DestroyWindow(*(HWND *)(WindowLongPtrW + 176));
            v16 = *(void **)(WindowLongPtrW + 64);
            if ( v16 )
            {
              DeleteObject(v16);
              *(_DWORD *)(WindowLongPtrW + 184) |= 0xFu;
              *(_QWORD *)(WindowLongPtrW + 64) = 0;
            }
            LocalFree(*(HLOCAL *)(WindowLongPtrW + 152));
            LocalFree((HLOCAL)WindowLongPtrW);
            SetWindowLongPtrW(hWnd, 0, 0);
            return 0;
          case 5u:
            break;
          case 7u:
LABEL_18:
            *(_DWORD *)(WindowLongPtrW + 184) |= 0xFu;
            v12 = *(HWND *)WindowLongPtrW;
LABEL_19:
            InvalidateRect(v12, 0, 0);
            return 0;
          case 8u:
            gcWheelDelta = 0;
            goto LABEL_18;
          case 0xAu:
            v13 = *(_DWORD *)(WindowLongPtrW + 16);
            v14 = v13 & 0xF7FFFFFF;
            v15 = v13 | 0x8000000;
            if ( !hdc )
              v14 = v15;
            *(_DWORD *)(WindowLongPtrW + 184) |= 2u;
            *(_DWORD *)(WindowLongPtrW + 16) = v14;
            v12 = hWnd;
            goto LABEL_19;
          case 0xFu:
LABEL_148:
            Rect = 0;
            if ( hdc )
              v38 = hdc;
            else
              v38 = BeginPaint(hWnd, &Paint);
            *(_QWORD *)(WindowLongPtrW + 56) = CreateCompatibleDC(v38);
            ColorBitmap = *(void **)(WindowLongPtrW + 64);
            if ( !ColorBitmap )
            {
              GetClientRect(hWnd, &Rect);
              ColorBitmap = (void *)CreateColorBitmap(Rect.right, Rect.bottom);
              *(_QWORD *)(WindowLongPtrW + 64) = ColorBitmap;
            }
            v40 = SelectObject(*(HDC *)(WindowLongPtrW + 56), ColorBitmap);
            FlushChanges(WindowLongPtrW);
            if ( (unsigned int)GetClipBox(v38, &Rect) <= 1 )
              GetClientRect(*(HWND *)WindowLongPtrW, &Rect);
            BitBlt(
              v38,
              Rect.left,
              Rect.top,
              Rect.right - Rect.left,
              Rect.bottom - Rect.top,
              *(HDC *)(WindowLongPtrW + 56),
              Rect.left,
              Rect.top,
              0xCC0020u);
            SelectObject(*(HDC *)(WindowLongPtrW + 56), v40);
            DeleteDC(*(HDC *)(WindowLongPtrW + 56));
            if ( !hdc )
              EndPaint(hWnd, &Paint);
            *(_QWORD *)(WindowLongPtrW + 56) = 0;
            return 0;
          case 0x15u:
            InitGlobalColors();
            goto LABEL_18;
          default:
LABEL_41:
            *(_QWORD *)&Rect.left = 0;
            if ( (unsigned int)CCWndProc(WindowLongPtrW, Msg, (_DWORD)hdc, v10, (__int64)&Rect) )
              return *(_QWORD *)&Rect.left;
            return DefWindowProcW(hWnd, Msg, (WPARAM)hdc, lParam);
        }
LABEL_34:
        TBResize(WindowLongPtrW);
        return 0;
      }
      switch ( Msg )
      {
        case '=':
          if ( (_DWORD)lParam == -12 )
            return 65554;
          return DefWindowProcW(hWnd, Msg, (WPARAM)hdc, lParam);
        case 'N':
          if ( *(_QWORD *)lParam == *(_QWORD *)(WindowLongPtrW + 176) )
          {
            if ( *(_DWORD *)(lParam + 16) == -530 )
              StringCchPrintfW((wchar_t *)(lParam + 32), 0x50u, L"%d", *(unsigned int *)(WindowLongPtrW + 80));
            SendNotifyEx(
              *(_QWORD *)(WindowLongPtrW + 8),
              -1,
              *(unsigned int *)(lParam + 16),
              lParam,
              *(_DWORD *)(WindowLongPtrW + 24) & 1);
          }
          return 0;
        case 'U':
          return CIHandleNotifyFormat(WindowLongPtrW, lParam);
        case '}':
          if ( hdc != (HDC)-16LL )
            return 0;
          *(_DWORD *)(WindowLongPtrW + 16) = *(_DWORD *)(lParam + 4);
          goto LABEL_34;
        case '~':
          v17 = *(void **)(WindowLongPtrW + 64);
          if ( v17 )
          {
            DeleteObject(v17);
            *(_DWORD *)(WindowLongPtrW + 184) |= 0xFu;
            *(_QWORD *)(WindowLongPtrW + 64) = 0;
          }
          return 0;
      }
      if ( Msg != 135 )
        goto LABEL_41;
      return 1;
    }
    if ( (*(_DWORD *)(WindowLongPtrW + 16) & 0x8000000) != 0 )
      return 0;
    v18 = 39;
    if ( (*(_DWORD *)(WindowLongPtrW + 32) & 0x400000) != 0 )
    {
      if ( hdc == (HDC)37 )
      {
        LODWORD(hdc) = 39;
      }
      else if ( hdc == (HDC)39 )
      {
        LODWORD(hdc) = 37;
      }
    }
    v19 = (unsigned int)hdc;
    if ( (*(_DWORD *)(WindowLongPtrW + 16) & 0x400) != 0 )
    {
      if ( (*(_BYTE *)(WindowLongPtrW + 16) & 2) != 0 )
      {
        if ( (unsigned int)hdc != 37 )
        {
          if ( (unsigned int)hdc == 39 )
            v19 = 37;
          goto LABEL_73;
        }
LABEL_72:
        v19 = v18;
        goto LABEL_73;
      }
      v18 = 40;
      switch ( (unsigned int)hdc )
      {
        case '&':
          goto LABEL_72;
        case '(':
          v18 = 38;
          goto LABEL_72;
        case '!':
          v19 = 34;
          goto LABEL_73;
      }
      v18 = (unsigned int)hdc;
      v19 = 33;
      if ( (unsigned int)hdc != 34 )
        goto LABEL_72;
    }
LABEL_73:
    v20 = v19 - 33;
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( v22 )
        {
          v23 = v22 - 1;
          if ( v23 )
          {
            v24 = v23 - 1;
            if ( v24 && (v25 = v24 - 1) != 0 )
            {
              if ( (unsigned __int64)(v25 - 1) > 1 )
                return 0;
              v26 = 1;
            }
            else
            {
              v26 = 0;
            }
          }
          else
          {
            v26 = 6;
          }
        }
        else
        {
          v26 = 7;
        }
      }
      else
      {
        v26 = 3;
      }
    }
    else
    {
      v26 = 2;
    }
    DoTrack(WindowLongPtrW, v26, 0);
    CCNotifyNavigationKeyUsage(WindowLongPtrW, 1);
    return 0;
  }
  if ( Msg <= 0x207 )
  {
    switch ( Msg )
    {
      case 0x207u:
        SetFocus(hWnd);
        return 0;
      case 0x101u:
        if ( (*(_DWORD *)(WindowLongPtrW + 16) & 0x8000000) == 0 )
        {
          v27 = (char *)hdc - 33;
          if ( !v27
            || (v28 = v27 - 1) == 0
            || (v29 = v28 - 1) == 0
            || (v30 = v29 - 1) == 0
            || (v31 = v30 - 1) == 0
            || (v32 = v31 - 1) == 0
            || (unsigned __int64)(v32 - 1) <= 1 )
          {
            DoTrack(WindowLongPtrW, 8, 0);
          }
        }
        return 0;
      case 0x113u:
        lParam = (int)GetMessagePosClient(*(HWND *)WindowLongPtrW, 0);
        goto LABEL_105;
    }
    if ( Msg != 296 )
    {
      if ( Msg != 512 )
      {
        if ( Msg == 513 )
        {
          if ( (*(_DWORD *)(WindowLongPtrW + 16) & 0x8000000) == 0 )
          {
            SetFocus(hWnd);
            TBTrackInit(WindowLongPtrW, lParam);
          }
          return 0;
        }
        if ( Msg == 514 )
        {
          if ( (*(_DWORD *)(WindowLongPtrW + 16) & 0x8000000) == 0 )
          {
            TBTrackEnd(WindowLongPtrW);
            if ( GetCapture() == hWnd )
              CCReleaseCapture(WindowLongPtrW);
          }
          return 0;
        }
        goto LABEL_41;
      }
LABEL_105:
      if ( *(_DWORD *)(WindowLongPtrW + 196) != -1 && (*(_DWORD *)(WindowLongPtrW + 16) & 0x8000000) == 0 )
        TBTrack(WindowLongPtrW, lParam);
      return 0;
    }
    if ( (unsigned int)CCOnUIState(WindowLongPtrW, v8, (unsigned int)hdc & 0x1FFFF) )
      InvalidateRect(hWnd, 0, 1);
    return DefWindowProcW(hWnd, Msg, (WPARAM)hdc, lParam);
  }
  switch ( Msg )
  {
    case 0x215u:
      TBTrackEnd(WindowLongPtrW);
      return 0;
    case 0x318u:
      goto LABEL_148;
    case 0x400u:
      return *(int *)(WindowLongPtrW + 80);
    case 0x401u:
      return *(int *)(WindowLongPtrW + 72);
    case 0x402u:
      return *(int *)(WindowLongPtrW + 76);
  }
  if ( Msg != 1027 )
  {
    if ( Msg != 522 )
      goto LABEL_41;
    gcWheelDelta -= SWORD1(hdc);
    v33 = gcWheelDelta / 120;
    if ( gcWheelDelta / 120 )
      gcWheelDelta %= 120;
    if ( ((unsigned __int8)hdc & 0xC) == 0 )
    {
      v34 = *(_DWORD *)(WindowLongPtrW + 80);
      if ( (unsigned int)(v34 + 0x8000) <= 0xFFFF )
      {
        v35 = *(_DWORD *)(WindowLongPtrW + 76);
        v36 = v33 + v34;
        if ( v33 + v34 >= v35 )
          v36 = *(_DWORD *)(WindowLongPtrW + 76);
        if ( v36 <= *(_DWORD *)(WindowLongPtrW + 72) )
        {
          v35 = *(_DWORD *)(WindowLongPtrW + 72);
        }
        else if ( v33 + v34 < v35 )
        {
          v35 = v33 + v34;
        }
        if ( v35 >= 0x7FFF )
        {
          v35 = 0x7FFF;
        }
        else if ( v35 <= -32768 )
        {
          v35 = -32768;
        }
        if ( v35 != v34 )
        {
          MoveThumb(WindowLongPtrW, (unsigned int)v35);
          DoTrack(WindowLongPtrW, 4, (unsigned int)v35);
        }
      }
      return 1;
    }
    return DefWindowProcW(hWnd, Msg, (WPARAM)hdc, lParam);
  }
  v37 = *(_QWORD *)(WindowLongPtrW + 152);
  if ( v37 && (int)hdc < *(_DWORD *)(WindowLongPtrW + 144) )
    return *(unsigned int *)(v37 + 4LL * (_QWORD)hdc);
  else
    return -1;
}

```

## disassembly

```asm
0x18006e230  push    rbp
0x18006e232  push    rbx
0x18006e233  push    rsi
0x18006e234  push    rdi
0x18006e235  push    r14
0x18006e237  push    r15
0x18006e239  lea     rbp, [rsp-2Fh]
0x18006e23e  sub     rsp, 0C8h
0x18006e245  mov     rax, cs:__security_cookie
0x18006e24c  xor     rax, rsp
0x18006e24f  mov     [rbp+57h+var_40], rax
0x18006e253  mov     edi, edx
0x18006e255  mov     rbx, r8
0x18006e258  xor     edx, edx; Val
0x18006e25a  mov     r15, rcx
0x18006e25d  lea     rcx, [rbp+57h+Paint]; void *
0x18006e261  mov     r14, r9
0x18006e264  lea     r8d, [rdx+48h]; Size
0x18006e268  call    memset
0x18006e26d  xor     edx, edx; nIndex
0x18006e26f  mov     rcx, r15; hWnd
0x18006e272  call    cs:__imp_GetWindowLongPtrW
0x18006e278  mov     rsi, rax
0x18006e27b  test    rax, rax
0x18006e27e  jnz     short loc_18006E299
0x18006e280  cmp     edi, 1
0x18006e283  jnz     loc_18006E6C8
0x18006e289  mov     rdx, r14
0x18006e28c  mov     rcx, r15; hWnd
0x18006e28f  call    TrackOnCreate
0x18006e294  jmp     loc_18006E6D9
0x18006e299  mov     eax, 404h
0x18006e29e  cmp     edi, eax
0x18006e2a0  ja      loc_18006EA50
0x18006e2a6  jz      loc_18006E9E1
0x18006e2ac  cmp     edi, 100h
0x18006e2b2  ja      loc_18006E605
0x18006e2b8  jz      loc_18006E50D
0x18006e2be  cmp     edi, 1Ah
0x18006e2c1  ja      loc_18006E3FB
0x18006e2c7  jz      loc_18006E3E6
0x18006e2cd  mov     eax, edi
0x18006e2cf  sub     eax, 2
0x18006e2d2  jz      short loc_18006E34F
0x18006e2d4  sub     eax, 3
0x18006e2d7  jz      loc_18006E3EE
0x18006e2dd  sub     eax, 2
0x18006e2e0  jz      short loc_18006E307
0x18006e2e2  sub     eax, 1
0x18006e2e5  jz      short loc_18006E343
0x18006e2e7  sub     eax, 2
0x18006e2ea  jz      short loc_18006E321
0x18006e2ec  sub     eax, 5
0x18006e2ef  jz      loc_18006E8D5
0x18006e2f5  mov     edx, 6
0x18006e2fa  cmp     eax, edx
0x18006e2fc  jnz     def_18006EA70; jumptable 000000018006EA70 default case, case 1037
0x18006e302  call    InitGlobalColors
0x18006e307  or      dword ptr [rsi+0B8h], 0Fh
0x18006e30e  mov     rcx, [rsi]; hWnd
0x18006e311  xor     r8d, r8d; bErase
0x18006e314  xor     edx, edx; lpRect
0x18006e316  call    cs:__imp_InvalidateRect
0x18006e31c  jmp     loc_18006EB05
0x18006e321  mov     ecx, [rsi+10h]
0x18006e324  mov     eax, ecx
0x18006e326  btr     ecx, 1Bh
0x18006e32a  bts     eax, 1Bh
0x18006e32e  test    rbx, rbx
0x18006e331  cmovz   ecx, eax
0x18006e334  or      dword ptr [rsi+0B8h], 2
0x18006e33b  mov     [rsi+10h], ecx
0x18006e33e  mov     rcx, r15
0x18006e341  jmp     short loc_18006E311
0x18006e343  mov     cs:gcWheelDelta, 0
0x18006e34d  jmp     short loc_18006E307
0x18006e34f  call    TerminateDitherBrush
0x18006e354  cmp     cs:g_fDBCSInputEnabled, 0
0x18006e35b  jz      short loc_18006E378
0x18006e35d  mov     rax, cs:g_pfnImmAssociateContext
0x18006e364  test    rax, rax
0x18006e367  jz      short loc_18006E378
0x18006e369  mov     rdx, [rsi+0C8h]
0x18006e370  mov     rcx, r15
0x18006e373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e378  test    dword ptr [rsi+10h], 100h
0x18006e37f  jz      short loc_18006E39F
0x18006e381  mov     rcx, [rsi+0B0h]; hWnd
0x18006e388  call    cs:__imp_IsWindow
0x18006e38e  test    eax, eax
0x18006e390  jz      short loc_18006E39F
0x18006e392  mov     rcx, [rsi+0B0h]; hWnd
0x18006e399  call    cs:__imp_DestroyWindow
0x18006e39f  mov     rcx, [rsi+40h]; ho
0x18006e3a3  test    rcx, rcx
0x18006e3a6  jz      short loc_18006E3BD
0x18006e3a8  call    cs:__imp_DeleteObject
0x18006e3ae  or      dword ptr [rsi+0B8h], 0Fh
0x18006e3b5  mov     qword ptr [rsi+40h], 0
0x18006e3bd  mov     rcx, [rsi+98h]; hMem
0x18006e3c4  call    cs:__imp_LocalFree
0x18006e3ca  mov     rcx, rsi; hMem
0x18006e3cd  call    cs:__imp_LocalFree
0x18006e3d3  xor     r8d, r8d; dwNewLong
0x18006e3d6  xor     edx, edx; nIndex
0x18006e3d8  mov     rcx, r15; hWnd
0x18006e3db  call    cs:__imp_SetWindowLongPtrW
0x18006e3e1  jmp     loc_18006EB05
0x18006e3e6  mov     rcx, rbx
0x18006e3e9  call    InitGlobalMetrics
0x18006e3ee  mov     rcx, rsi
0x18006e3f1  call    TBResize
0x18006e3f6  jmp     loc_18006EB05
0x18006e3fb  mov     eax, edi
0x18006e3fd  sub     eax, 3Dh ; '='
0x18006e400  jz      loc_18006E4F9
0x18006e406  sub     eax, 11h
0x18006e409  jz      loc_18006E4A3
0x18006e40f  sub     eax, 7
0x18006e412  jz      short loc_18006E493
0x18006e414  sub     eax, 28h ; '('
0x18006e417  jz      short loc_18006E47D
0x18006e419  sub     eax, 1
0x18006e41c  jz      short loc_18006E456
0x18006e41e  cmp     eax, 9
0x18006e421  jz      loc_18006EA46
0x18006e427  lea     rax, [rbp+57h+Rect]; jumptable 000000018006EA70 default case, case 1037
0x18006e42b  mov     qword ptr [rbp+57h+Rect.left], 0
0x18006e433  mov     r8, rbx
0x18006e436  mov     qword ptr [rsp+0F0h+cy], rax
0x18006e43b  mov     edx, edi
0x18006e43d  mov     rcx, rsi
0x18006e440  call    CCWndProc
0x18006e445  test    eax, eax
0x18006e447  jz      loc_18006E6C8
0x18006e44d  mov     rax, qword ptr [rbp+57h+Rect.left]
0x18006e451  jmp     loc_18006E6D9
0x18006e456  mov     rcx, [rsi+40h]; ho
0x18006e45a  test    rcx, rcx
0x18006e45d  jz      loc_18006EB05
0x18006e463  call    cs:__imp_DeleteObject
0x18006e469  or      dword ptr [rsi+0B8h], 0Fh
0x18006e470  mov     qword ptr [rsi+40h], 0
0x18006e478  jmp     loc_18006EB05
0x18006e47d  cmp     rbx, 0FFFFFFFFFFFFFFF0h
0x18006e481  jnz     loc_18006EB05
0x18006e487  mov     eax, [r14+4]
0x18006e48b  mov     [rsi+10h], eax
0x18006e48e  jmp     loc_18006E3EE
0x18006e493  mov     rdx, r14
0x18006e496  mov     rcx, rsi
0x18006e499  call    CIHandleNotifyFormat
0x18006e49e  jmp     loc_18006E6D9
0x18006e4a3  mov     rax, [rsi+0B0h]
0x18006e4aa  cmp     [r14], rax
0x18006e4ad  jnz     loc_18006EB05
0x18006e4b3  cmp     dword ptr [r14+10h], 0FFFFFDEEh
0x18006e4bb  jnz     short loc_18006E4D6
0x18006e4bd  mov     r9d, [rsi+50h]
0x18006e4c1  lea     rcx, [r14+20h]; Buffer
0x18006e4c5  lea     r8, aD; "%d"
0x18006e4cc  mov     edx, 50h ; 'P'; unsigned __int64
0x18006e4d1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006e4d6  mov     eax, [rsi+18h]
0x18006e4d9  mov     r9, r14
0x18006e4dc  mov     r8d, [r14+10h]
0x18006e4e0  and     eax, 1
0x18006e4e3  mov     rcx, [rsi+8]
0x18006e4e7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006e4eb  mov     [rsp+0F0h+cy], eax
0x18006e4ef  call    SendNotifyEx
0x18006e4f4  jmp     loc_18006EB05
0x18006e4f9  cmp     r14d, 0FFFFFFF4h
0x18006e4fd  jnz     loc_18006E6C8
0x18006e503  mov     eax, 10012h
0x18006e508  jmp     loc_18006E6D9
0x18006e50d  test    dword ptr [rsi+10h], 8000000h
0x18006e514  jnz     loc_18006EB05
0x18006e51a  test    dword ptr [rsi+20h], 400000h
0x18006e521  mov     edx, 25h ; '%'
0x18006e526  lea     ecx, [rdx+2]
0x18006e529  jz      short loc_18006E53B
0x18006e52b  cmp     rbx, rdx
0x18006e52e  jnz     short loc_18006E534
0x18006e530  mov     ebx, ecx
0x18006e532  jmp     short loc_18006E53B
0x18006e534  cmp     rbx, rcx
0x18006e537  cmovz   rbx, rdx
0x18006e53b  test    dword ptr [rsi+10h], 400h
0x18006e542  mov     eax, ebx
0x18006e544  jz      short loc_18006E58F
0x18006e546  test    byte ptr [rsi+10h], 2
0x18006e54a  jz      short loc_18006E55A
0x18006e54c  cmp     rax, rdx
0x18006e54f  jz      short loc_18006E58C
0x18006e551  cmp     rax, rcx
0x18006e554  cmovz   rax, rdx
0x18006e558  jmp     short loc_18006E58F
0x18006e55a  mov     ecx, 28h ; '('
0x18006e55f  cmp     rax, 26h ; '&'
0x18006e563  jz      short loc_18006E58C
0x18006e565  cmp     rax, rcx
0x18006e568  jnz     short loc_18006E571
0x18006e56a  mov     ecx, 26h ; '&'
0x18006e56f  jmp     short loc_18006E58C
0x18006e571  cmp     rax, 21h ; '!'
0x18006e575  jnz     short loc_18006E57E
0x18006e577  mov     eax, 22h ; '"'
0x18006e57c  jmp     short loc_18006E58F
0x18006e57e  mov     rcx, rax
0x18006e581  cmp     rax, 22h ; '"'
0x18006e585  mov     eax, 21h ; '!'
0x18006e58a  jz      short loc_18006E58F
0x18006e58c  mov     rax, rcx
0x18006e58f  sub     rax, 21h ; '!'
0x18006e593  jz      short loc_18006E5E3
0x18006e595  sub     rax, 1
0x18006e599  jz      short loc_18006E5DC
0x18006e59b  sub     rax, 1
0x18006e59f  jz      short loc_18006E5D5
0x18006e5a1  sub     rax, 1
0x18006e5a5  jz      short loc_18006E5CE
0x18006e5a7  sub     rax, 1
0x18006e5ab  jz      short loc_18006E5CA
0x18006e5ad  sub     rax, 1
0x18006e5b1  jz      short loc_18006E5CA
0x18006e5b3  sub     rax, 1
0x18006e5b7  jz      short loc_18006E5C3
0x18006e5b9  cmp     rax, 1
0x18006e5bd  jnz     loc_18006EB05
0x18006e5c3  mov     edx, 1
0x18006e5c8  jmp     short loc_18006E5E8
0x18006e5ca  xor     edx, edx
0x18006e5cc  jmp     short loc_18006E5E8
0x18006e5ce  mov     edx, 6
0x18006e5d3  jmp     short loc_18006E5E8
0x18006e5d5  mov     edx, 7
0x18006e5da  jmp     short loc_18006E5E8
0x18006e5dc  mov     edx, 3
0x18006e5e1  jmp     short loc_18006E5E8
0x18006e5e3  mov     edx, 2
0x18006e5e8  xor     r8d, r8d
0x18006e5eb  mov     rcx, rsi
0x18006e5ee  call    DoTrack
0x18006e5f3  mov     edx, 1
0x18006e5f8  mov     rcx, rsi
0x18006e5fb  call    CCNotifyNavigationKeyUsage
0x18006e600  jmp     loc_18006EB05
0x18006e605  mov     eax, 207h
0x18006e60a  cmp     edi, eax
0x18006e60c  ja      loc_18006E78F
0x18006e612  jz      loc_18006E781
0x18006e618  mov     eax, edi
0x18006e61a  sub     eax, 101h
0x18006e61f  jz      loc_18006E72C
0x18006e625  sub     eax, 12h
0x18006e628  jz      loc_18006E6F5
0x18006e62e  sub     eax, 15h
0x18006e631  jz      short loc_18006E6A3
0x18006e633  sub     eax, 0D8h
0x18006e638  jz      loc_18006E702
0x18006e63e  sub     eax, 1
0x18006e641  jz      short loc_18006E67D
0x18006e643  cmp     eax, 1
0x18006e646  jnz     def_18006EA70; jumptable 000000018006EA70 default case, case 1037
0x18006e64c  test    dword ptr [rsi+10h], 8000000h
0x18006e653  jnz     loc_18006EB05
0x18006e659  mov     rcx, rsi
0x18006e65c  call    TBTrackEnd
0x18006e661  call    cs:__imp_GetCapture
0x18006e667  cmp     rax, r15
0x18006e66a  jnz     loc_18006EB05
0x18006e670  mov     rcx, rsi
0x18006e673  call    CCReleaseCapture
0x18006e678  jmp     loc_18006EB05
0x18006e67d  test    dword ptr [rsi+10h], 8000000h
0x18006e684  jnz     loc_18006EB05
0x18006e68a  mov     rcx, r15; hWnd
0x18006e68d  call    cs:__imp_SetFocus
0x18006e693  mov     rdx, r14
0x18006e696  mov     rcx, rsi
0x18006e699  call    TBTrackInit
0x18006e69e  jmp     loc_18006EB05
0x18006e6a3  mov     r8, rbx
0x18006e6a6  mov     rcx, rsi
0x18006e6a9  and     r8d, 1FFFFh
0x18006e6b0  call    CCOnUIState
0x18006e6b5  test    eax, eax
0x18006e6b7  jz      short loc_18006E6C8
0x18006e6b9  xor     edx, edx; lpRect
0x18006e6bb  mov     rcx, r15; hWnd
0x18006e6be  lea     r8d, [rdx+1]; bErase
0x18006e6c2  call    cs:__imp_InvalidateRect
0x18006e6c8  mov     r9, r14; lParam
0x18006e6cb  mov     r8, rbx; wParam
0x18006e6ce  mov     edx, edi; Msg
0x18006e6d0  mov     rcx, r15; hWnd
0x18006e6d3  call    cs:__imp_DefWindowProcW
0x18006e6d9  mov     rcx, [rbp+57h+var_40]
0x18006e6dd  xor     rcx, rsp; StackCookie
  ... truncated ...
```
