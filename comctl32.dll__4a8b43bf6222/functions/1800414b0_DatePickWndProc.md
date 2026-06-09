# DatePickWndProc

- ea: `0x1800414b0`
- end: `0x18004200e`
- name: `DatePickWndProc`
- size: `2910`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, HDC hdc, LPCCH lpMultiByteStr)`
- caller_count: `0`
- callee_count: `37`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800115f0`
- `0x180017a0c`
- `0x180017bac`
- `0x1800183dc`
- `0x180018464`
- `0x1800190a4`
- `0x18001a590`
- `0x180035fe0`
- `0x18003a530`
- `0x18003a6b8`
- `0x18004021c`
- `0x18004042c`
- `0x180040560`
- `0x180040730`
- `0x1800407b0`
- `0x180040df8`
- `0x180040f80`
- `0x180041110`
- `0x180041258`
- `0x1800413a8`
- `0x180041448`
- `0x1800414b0`
- `0x180042570`
- `0x180042724`
- `0x180042f3c`
- `0x1800483a0`
- `0x180048840`
- `0x180048a2c`
- `0x18004978c`
- `0x1800497e4`
- `0x18004983c`
- `0x180049a2c`
- `0x180072058`
- `0x1800722a0`
- `0x180072690`
- `0x1800726d8`
- `0x18008ea60`

## import_xrefs

- `GDI32!GetClipBox` at `0x1800417a1`
- `GDI32!GetClipBox` at `0x1800417a1`
- `KERNEL32!LocalFree` at `0x180041706`
- `KERNEL32!LocalFree` at `0x180041722`
- `KERNEL32!LocalFree` at `0x180041f0a`
- `KERNEL32!LocalFree` at `0x180041706`
- `KERNEL32!LocalFree` at `0x180041722`
- `KERNEL32!LocalFree` at `0x180041f0a`
- `KERNEL32!lstrlenW` at `0x180041829`
- `KERNEL32!lstrlenW` at `0x180041829`
- `KERNEL32!LocalAlloc` at `0x180041522`
- `KERNEL32!LocalAlloc` at `0x180041522`
- `USER32!GetClientRect` at `0x180041e8d`
- `USER32!GetClientRect` at `0x180041e8d`
- `USER32!SendMessageW` at `0x180041927`
- `USER32!SendMessageW` at `0x180041b47`
- `USER32!SendMessageW` at `0x180041b6e`
- `USER32!SendMessageW` at `0x180041f8f`
- `USER32!SendMessageW` at `0x180041927`
- `USER32!SendMessageW` at `0x180041b47`
- `USER32!SendMessageW` at `0x180041b6e`
- `USER32!SendMessageW` at `0x180041f8f`
- `USER32!MessageBeep` at `0x1800419ce`
- `USER32!MessageBeep` at `0x180041b0c`
- `USER32!MessageBeep` at `0x1800419ce`
- `USER32!MessageBeep` at `0x180041b0c`
- `USER32!SetWindowLongPtrW` at `0x180041538`
- `USER32!SetWindowLongPtrW` at `0x180041730`
- `USER32!SetWindowLongPtrW` at `0x180041538`
- `USER32!SetWindowLongPtrW` at `0x180041730`
- `USER32!EnableWindow` at `0x1800415f3`
- `USER32!EnableWindow` at `0x1800415f3`
- `USER32!SetFocus` at `0x18004197c`
- `USER32!SetFocus` at `0x18004197c`
- `USER32!InvalidateRect` at `0x180041602`
- `USER32!InvalidateRect` at `0x180041697`
- `USER32!InvalidateRect` at `0x180041afc`
- `USER32!InvalidateRect` at `0x180041daf`
- `USER32!InvalidateRect` at `0x180041ebd`
- `USER32!InvalidateRect` at `0x180041602`
- `USER32!InvalidateRect` at `0x180041697`
- `USER32!InvalidateRect` at `0x180041afc`
- `USER32!InvalidateRect` at `0x180041daf`
- `USER32!InvalidateRect` at `0x180041ebd`
- `USER32!GetWindowLongPtrW` at `0x180041548`
- `USER32!GetWindowLongPtrW` at `0x180041548`
- `USER32!BeginPaint` at `0x180041bc6`
- `USER32!BeginPaint` at `0x180041bc6`
- `USER32!EndPaint` at `0x180041bdf`
- `USER32!EndPaint` at `0x180041bdf`
- `USER32!DefWindowProcW` at `0x180041562`
- `USER32!DefWindowProcW` at `0x180041fd8`
- `USER32!DefWindowProcW` at `0x180041562`
- `USER32!DefWindowProcW` at `0x180041fd8`
- `USER32!UpdateWindow` at `0x180041ec6`
- `USER32!UpdateWindow` at `0x180041ec6`
- `USER32!PostMessageW` at `0x180041a52`
- `USER32!PostMessageW` at `0x180041a52`

## pseudocode

```c
__int64 __fastcall DatePickWndProc(HWND hWnd, UINT Msg, HDC hdc, WCHAR *lpMultiByteStr)
{
  __int64 v4; // r15
  UINT v7; // r14d
  HLOCAL v9; // rax
  HLOCAL v10; // rbx
  __int64 v12; // rdx
  HWND *WindowLongPtrW; // rdi
  int v14; // r9d
  BOOL v15; // edx
  HWND v16; // rcx
  int v17; // edx
  int v18; // ebx
  int v19; // eax
  HWND v20; // rcx
  HWND v21; // rcx
  HWND v23; // r13
  int i; // r12d
  const WCHAR *v25; // rax
  __int64 v26; // r11
  HWND v27; // rcx
  int v28; // ecx
  int v29; // eax
  int v30; // ebx
  unsigned int v31; // ecx
  int v32; // eax
  HWND v33; // rcx
  HWND v34; // rcx
  UINT v35; // edx
  HWND v36; // rbx
  HDC v37; // rax
  __int128 *v38; // r14
  LPCCH v39; // rbx
  __int128 *v40; // rdx
  __int128 *v41; // rcx
  __int128 v42; // xmm1
  bool v43; // zf
  unsigned int v44; // edx
  char *v45; // rsi
  __int64 v46; // r14
  HWND v47; // rcx
  __int128 v48; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v49; // [rsp+48h] [rbp-B8h]
  struct tagRECT rect; // [rsp+50h] [rbp-B0h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v52[256]; // [rsp+B0h] [rbp-50h] BYREF

  v4 = 0;
  v49 = 0;
  *(_QWORD *)&rect.left = 0;
  v7 = Msg;
  v48 = 0;
  if ( Msg == 129 )
  {
    SetWindowBits(hWnd, -20);
    v9 = LocalAlloc(0x40u, 0x180u);
    v10 = v9;
    if ( v9 )
      SetWindowLongPtrW(hWnd, 0, (LONG_PTR)v9);
    return (__int64)v10;
  }
  WindowLongPtrW = (HWND *)GetWindowLongPtrW(hWnd, 0);
  if ( !WindowLongPtrW )
    return DefWindowProcW(hWnd, v7, (WPARAM)hdc, (LPARAM)lpMultiByteStr);
  if ( v7 <= 0x1A )
  {
    if ( v7 == 26 )
    {
      if ( !lpMultiByteStr || !StrCmpICW(lpMultiByteStr, L"Intl") )
        DPHandleLocaleChange(WindowLongPtrW);
      return v4;
    }
    if ( v7 <= 0xC )
    {
      if ( v7 != 12 )
      {
        if ( v7 != 1 )
        {
          if ( v7 == 2 )
          {
            _InterlockedDecrement(&g_dwWindowCount);
            v21 = WindowLongPtrW[28];
            if ( v21 )
            {
              LocalFree(v21);
              WindowLongPtrW[28] = 0;
            }
            MCFreeCalendarInfo(WindowLongPtrW + 34);
            LocalFree(WindowLongPtrW);
            SetWindowLongPtrW(hWnd, 0, 0);
            return v4;
          }
          if ( v7 != 5 )
          {
            if ( v7 == 7 || v7 == 8 )
            {
              v18 = v7 == 7;
              if ( v18 != ((*((_DWORD *)WindowLongPtrW + 94) >> 2) & 1) )
              {
                v19 = *((_DWORD *)WindowLongPtrW + 49);
                v17 = *((_DWORD *)WindowLongPtrW + 94);
                *((_DWORD *)WindowLongPtrW + 94) = v17 & 0xFFFFFFFB | (4 * v18);
                if ( v19 < 0 )
                {
                  if ( ((_BYTE)WindowLongPtrW[2] & 2) != 0 )
                  {
                    v20 = *WindowLongPtrW;
                    *((_DWORD *)WindowLongPtrW + 94) = v17 & 0xFFFFFF7B | (4 * v18) & 0xFFFFFF7F | (v18 << 7);
                    InvalidateRect(v20, (const RECT *)(WindowLongPtrW + 39), 1);
                  }
                  else if ( v7 == 7 )
                  {
                    SECIncrFocus(WindowLongPtrW, 1);
                  }
                }
                else
                {
                  InvalidateScrollRect(*WindowLongPtrW);
                }
                CCSendNotify((__int64)WindowLongPtrW, v18 - 8, (LPARAM)&v48);
              }
              if ( v7 == 7 )
              {
                SECSafeSetCurSubed(WindowLongPtrW, *((unsigned int *)WindowLongPtrW + 90));
              }
              else
              {
                *((_DWORD *)WindowLongPtrW + 90) = *((_DWORD *)WindowLongPtrW + 49);
                SECSetCurSubed(WindowLongPtrW, 0xFFFFFFFFLL);
              }
              return v4;
            }
            if ( v7 == 10 )
            {
              v15 = hdc != 0;
              if ( ((_DWORD)WindowLongPtrW[47] & 1) != v15 )
              {
                *((_DWORD *)WindowLongPtrW + 94) = v15 | (_DWORD)WindowLongPtrW[47] & 0xFFFFFFFE;
                v16 = WindowLongPtrW[7];
                if ( v16 )
                  EnableWindow(v16, v15);
                InvalidateRect(*WindowLongPtrW, 0, 1);
              }
              return v4;
            }
LABEL_187:
            if ( (unsigned int)CCWndProc((_DWORD)WindowLongPtrW, v7, (_DWORD)hdc, v14, (__int64)&rect) )
              return *(_QWORD *)&rect.left;
            return DefWindowProcW(hWnd, v7, (WPARAM)hdc, (LPARAM)lpMultiByteStr);
          }
LABEL_161:
          rect = 0;
          if ( v7 == 4095 )
          {
            GetClientRect(*WindowLongPtrW, &rect);
          }
          else
          {
            rect.right = (__int16)lpMultiByteStr;
            rect.bottom = SWORD1(lpMultiByteStr);
          }
          DPRecomputeSizing(WindowLongPtrW, &rect);
          InvalidateRect(*WindowLongPtrW, 0, 1);
          UpdateWindow(*WindowLongPtrW);
          return v4;
        }
        CCCreateWindow();
        return DPCreateHandler(WindowLongPtrW, hWnd, lpMultiByteStr);
      }
      return -1;
    }
    switch ( v7 )
    {
      case 0xDu:
        if ( lpMultiByteStr && hdc )
          *lpMultiByteStr = 0;
        else
          v7 = 14;
        break;
      case 0xEu:
        break;
      case 0xFu:
LABEL_118:
        memset(&Paint, 0, sizeof(Paint));
        if ( hdc )
        {
          DPPaint(WindowLongPtrW, hdc);
        }
        else
        {
          v36 = *WindowLongPtrW;
          v37 = BeginPaint(*WindowLongPtrW, &Paint);
          DPPaint(WindowLongPtrW, v37);
          EndPaint(v36, &Paint);
        }
        return v4;
      case 0x14u:
        if ( ((_BYTE)WindowLongPtrW[47] & 1) == 0 )
        {
          rect = 0;
          GetClipBox(hdc, &rect);
          FillRectClr(hdc, &rect, g_clrBtnFace);
          return v4;
        }
        return DefWindowProcW(hWnd, v7, (WPARAM)hdc, (LPARAM)lpMultiByteStr);
      case 0x15u:
        InitGlobalColors();
        return v4;
      default:
        goto LABEL_187;
    }
    v23 = WindowLongPtrW[29];
    for ( i = 0; i < *((_DWORD *)WindowLongPtrW + 50); v23 += 20 )
    {
      if ( *(_DWORD *)v23 == 11 )
      {
        v25 = (const WCHAR *)*((_QWORD *)v23 + 8);
        *(_QWORD *)&rect.left = v25;
      }
      else
      {
        *(_QWORD *)&rect.left = v52;
        SEGetTimeDateFormat(v23, WindowLongPtrW + 19, v52, 128);
        v25 = (const WCHAR *)v52;
      }
      LODWORD(v26) = lstrlenW(v25);
      if ( v7 == 13 )
      {
        if ( (unsigned int)(v26 + v4) >= (unsigned __int64)hdc )
          return v4;
        StringCchCopyW(lpMultiByteStr, (size_t)hdc - (unsigned int)v4, *(STRSAFE_LPCWSTR *)&rect.left);
        lpMultiByteStr += v26;
      }
      v4 = (unsigned int)(v26 + v4);
      ++i;
    }
    return v4;
  }
  if ( v7 <= 0x318 )
  {
    if ( v7 == 792 )
      goto LABEL_118;
    if ( v7 <= 0x7D )
    {
      switch ( v7 )
      {
        case '}':
          if ( (_DWORD)hdc == -16 )
          {
            v29 = *((_DWORD *)lpMultiByteStr + 1);
            v30 = *((_DWORD *)WindowLongPtrW + 4) ^ v29;
            *((_DWORD *)WindowLongPtrW + 4) = v29;
            if ( (v30 & 0xFFCD) != 0 )
              DPHandleLocaleChange(WindowLongPtrW);
            if ( (v30 & 0xC40000) != 0 )
              PostMessageW(*WindowLongPtrW, 0xFFFu, 0, 0);
          }
          return v4;
        case '0':
          DPHandleSetFont(WindowLongPtrW, hdc, (unsigned __int16)lpMultiByteStr);
          return v4;
        case '1':
          return (__int64)WindowLongPtrW[21];
      }
      if ( v7 != 78 )
      {
        if ( v7 == 85 )
          return CIHandleNotifyFormat(WindowLongPtrW, lpMultiByteStr);
        if ( v7 != 123 )
        {
          if ( v7 == 124 )
          {
            if ( (_DWORD)hdc == -16 )
              *((_DWORD *)lpMultiByteStr + 1) ^= (*((_DWORD *)WindowLongPtrW + 4)
                                                ^ *((_DWORD *)lpMultiByteStr + 1))
                                               & 0xFFC3;
            return v4;
          }
          goto LABEL_187;
        }
        v27 = WindowLongPtrW[8];
        if ( !v27 )
          return DefWindowProcW(hWnd, v7, (WPARAM)hdc, (LPARAM)lpMultiByteStr);
        return SendMessageW(v27, v7, (WPARAM)hdc, (LPARAM)lpMultiByteStr);
      }
      if ( *((_DWORD *)lpMultiByteStr + 4) == -749 || *((_DWORD *)lpMultiByteStr + 4) == -746 )
      {
        if ( !(unsigned int)DPSetDate(WindowLongPtrW, lpMultiByteStr + 12, 1) )
          MessageBeep(0x10u);
        v28 = 0;
        if ( *((_DWORD *)lpMultiByteStr + 4) == -749 )
          v28 = 32;
        *((_DWORD *)WindowLongPtrW + 94) = (_DWORD)WindowLongPtrW[47] & 0xFFFFFFDF | v28;
        return v4;
      }
      if ( *((_DWORD *)lpMultiByteStr + 4) != -722 || (_DWORD)hdc != 1000 )
        return v4;
      if ( ((_BYTE)WindowLongPtrW[47] & 4) == 0 )
        SetFocus(*WindowLongPtrW);
      SECSaveResetSubeditEdit(WindowLongPtrW, 1);
      if ( !(unsigned int)SECIncrementSubedit(WindowLongPtrW + 19, (unsigned int)-*((_DWORD *)lpMultiByteStr + 7)) )
        return v4;
LABEL_83:
      DPNotifyDateChange(WindowLongPtrW);
      return v4;
    }
    if ( v7 == 135 )
      return 129;
    if ( v7 == 256 )
    {
      if ( ((_BYTE)WindowLongPtrW[47] & 0x20) != 0 )
      {
        SendMessageW(WindowLongPtrW[8], 0x100u, (WPARAM)hdc, (LPARAM)lpMultiByteStr);
        return 0;
      }
      return DPHandleKeydown(WindowLongPtrW, hdc);
    }
    if ( v7 != 257 )
    {
      if ( v7 != 258 )
      {
        if ( v7 == 260 )
        {
          if ( hdc == (HDC)40 && ((_BYTE)WindowLongPtrW[47] & 2) == 0 )
          {
            DPLBD_MonthCal((__int64)WindowLongPtrW, 0);
            return v4;
          }
          return DefWindowProcW(hWnd, v7, (WPARAM)hdc, (LPARAM)lpMultiByteStr);
        }
        if ( v7 == 513 )
        {
          DPLButtonDown(WindowLongPtrW, v12, lpMultiByteStr);
          return v4;
        }
        goto LABEL_187;
      }
      v31 = *((_DWORD *)WindowLongPtrW + 94);
      if ( (v31 & 0x80u) == 0 )
      {
        SECHandleChar(WindowLongPtrW, (unsigned __int16)hdc);
        return v4;
      }
      if ( (_WORD)hdc != 32 )
      {
        MessageBeep(0x10u);
        return v4;
      }
      v32 = v31 ^ ((unsigned __int8)v31 ^ (unsigned __int8)(~(unsigned __int8)(v31 >> 6) << 6)) & 0x40;
      v33 = *WindowLongPtrW;
      *((_DWORD *)WindowLongPtrW + 94) = v32;
      InvalidateRect(v33, 0, 1);
      goto LABEL_83;
    }
    if ( ((_BYTE)WindowLongPtrW[47] & 0x20) == 0 )
      return v4;
    v34 = WindowLongPtrW[8];
    v35 = 257;
LABEL_113:
    SendMessageW(v34, v35, (WPARAM)hdc, (LPARAM)lpMultiByteStr);
    return v4;
  }
  if ( v7 > 0x1032 )
    goto LABEL_187;
  if ( v7 == 4146 )
    return DTM_OnSetFormat(WindowLongPtrW, lpMultiByteStr);
  if ( v7 <= 0x1005 )
  {
    if ( v7 == 4101 )
    {
      v45 = 0;
      if ( lpMultiByteStr && *(_BYTE *)lpMultiByteStr )
        v45 = (char *)ProduceWFromA(*((_DWORD *)WindowLongPtrW + 7), (LPCCH)lpMultiByteStr);
      v4 = DTM_OnSetFormat(WindowLongPtrW, v45);
      if ( (unsigned __int64)(v45 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        LocalFree(v45);
      return v4;
    }
    if ( v7 != 4095 )
    {
      switch ( v7 )
      {
        case 0x1001u:
          if ( ((_BYTE)WindowLongPtrW[47] & 0x40) != 0 )
          {
            SECSaveResetSubeditEdit(WindowLongPtrW, 0);
            *(_OWORD *)lpMultiByteStr = *(_OWORD *)((char *)WindowLongPtrW + 204);
            lpMultiByteStr[2] = ((int)(GetStartDowForMonth(*lpMultiByteStr, lpMultiByteStr[1]) + lpMultiByteStr[3] - 1)
                               % 7
                               + 1)
                              % 7;
            return v4;
          }
          break;
        case 0x1002u:
          if ( hdc == (HDC)1 )
          {
            v43 = ((_BYTE)WindowLongPtrW[2] & 2) == 0;
          }
          else
          {
            if ( hdc )
              return v4;
            v43 = (unsigned int)IsValidSystemtime(lpMultiByteStr) == 0;
          }
          if ( !v43 )
          {
            SECSaveResetSubeditEdit(WindowLongPtrW, 1);
            *((_DWORD *)WindowLongPtrW + 94) |= 8u;
            v44 = *((_DWORD *)WindowLongPtrW + 94);
            if ( ((_BYTE)WindowLongPtrW[2] & 2) != 0 )
            {
              if ( hdc == (HDC)1 || (v44 & 0x40) != 0 )
              {
                SECSetCurSubed(WindowLongPtrW, 0xFFFFFFFFLL);
                v44 = *((_DWORD *)WindowLongPtrW + 94) | 0x80;
              }
              *((_DWORD *)WindowLongPtrW + 94) = v44 & 0xFFFFFFBF | (hdc != (HDC)1 ? 0x40 : 0);
              InvalidateRect(*WindowLongPtrW, 0, 1);
              v44 = *((_DWORD *)WindowLongPtrW + 94);
            }
            if ( !hdc )
            {
              *((_DWORD *)WindowLongPtrW + 94) = v44 | 8;
              DPSetDate(WindowLongPtrW, lpMultiByteStr, 0);
              v44 = (_DWORD)WindowLongPtrW[47] & 0xFFFFFFF7;
            }
            v4 = 1;
            *((_DWORD *)WindowLongPtrW + 94) = v44 & 0xFFFFFFF7;
          }
          return v4;
        case 0x1003u:
          *(_OWORD *)lpMultiByteStr = 0;
          *((_OWORD *)lpMultiByteStr + 1) = 0;
          v4 = (__int64)WindowLongPtrW[46];
          if ( (v4 & 1) != 0 )
            *(_OWORD *)lpMultiByteStr = *(_OWORD *)(WindowLongPtrW + 13);
          if ( (v4 & 2) != 0 )
            *((_OWORD *)lpMultiByteStr + 1) = *(_OWORD *)(WindowLongPtrW + 15);
          return v4;
        case 0x1004u:
          v38 = (__int128 *)lpMultiByteStr;
          if ( ((unsigned __int8)hdc & 1) == 0 )
            v38 = &c_stEpoch;
          if ( ((unsigned __int8)hdc & 2) != 0 )
            v39 = (LPCCH)(lpMultiByteStr + 8);
          else
            v39 = (LPCCH)&c_stArmageddon;
          if ( !(unsigned int)IsValidDate(v38) || !(unsigned int)IsValidDate(v39) )
            return v4;
          WindowLongPtrW[46] = (HWND)((unsigned __int8)hdc & 3);
          if ( (int)CmpDate(WindowLongPtrW + 13, WindowLongPtrW + 15) > 0 )
          {
            *v41 = *(_OWORD *)v39;
            v42 = *v38;
          }
          else
          {
            *v41 = *v38;
            v42 = *(_OWORD *)v39;
          }
          *((_DWORD *)WindowLongPtrW + 94) |= 8u;
          *v40 = v42;
          DPSetDate(WindowLongPtrW, (char *)WindowLongPtrW + 204, 1);
          *((_DWORD *)WindowLongPtrW + 94) &= ~8u;
          break;
        default:
          goto LABEL_187;
      }
      return 1;
    }
    goto LABEL_161;
  }
  if ( v7 != 4102 )
  {
    if ( v7 == 4103 )
    {
      if ( (unsigned __int64)hdc < 6 )
        return *((unsigned int *)WindowLongPtrW + (_QWORD)hdc + 20);
      return -1;
    }
    if ( v7 == 4104 )
      return (__int64)WindowLongPtrW[8];
    if ( v7 != 4105 )
    {
      if ( v7 == 4106 )
        return (__int64)WindowLongPtrW[9];
      goto LABEL_187;
    }
    v34 = WindowLongPtrW[8];
    WindowLongPtrW[9] = (HWND)hdc;
    if ( !v34 )
      return v4;
    v35 = 48;
    goto LABEL_113;
  }
  if ( (unsigned __int64)hdc >= 6 )
    return -1;
  v46 = *((unsigned int *)WindowLongPtrW + (_QWORD)hdc + 20);
  *((_DWORD *)WindowLongPtrW + (_QWORD)hdc + 20) = (_DWORD)lpMultiByteStr;
  v47 = WindowLongPtrW[8];
  if ( v47 )
    SendMessageW(v47, 0x100Au, (WPARAM)hdc, (LPARAM)lpMultiByteStr);
  return v46;
}

```

## disassembly

```asm
0x1800414b0  push    rbp
0x1800414b2  push    rbx
0x1800414b3  push    rsi
0x1800414b4  push    rdi
0x1800414b5  push    r12
0x1800414b7  push    r13
0x1800414b9  push    r14
0x1800414bb  push    r15
0x1800414bd  lea     rbp, [rsp-0C8h]
0x1800414c5  sub     rsp, 1C8h
0x1800414cc  mov     rax, cs:__security_cookie
0x1800414d3  xor     rax, rsp
0x1800414d6  mov     [rbp+100h+var_50], rax
0x1800414dd  xor     eax, eax
0x1800414df  xor     r15d, r15d
0x1800414e2  mov     [rsp+200h+var_1B8], rax
0x1800414e7  xorps   xmm0, xmm0
0x1800414ea  mov     qword ptr [rsp+200h+rect.left], r15
0x1800414ef  mov     rbx, r9
0x1800414f2  mov     rsi, r8
0x1800414f5  mov     r14d, edx
0x1800414f8  mov     r12, rcx
0x1800414fb  movups  [rsp+200h+var_1C8], xmm0
0x180041500  cmp     edx, 81h
0x180041506  jnz     short loc_180041546
0x180041508  mov     r8d, 200h
0x18004150e  lea     edx, [rax-14h]; nIndex
0x180041511  mov     r9d, r8d
0x180041514  call    SetWindowBits
0x180041519  mov     edx, 180h; uBytes
0x18004151e  lea     ecx, [r14-41h]; uFlags
0x180041522  call    cs:__imp_LocalAlloc
0x180041528  mov     rbx, rax
0x18004152b  test    rax, rax
0x18004152e  jz      short loc_18004153E
0x180041530  mov     r8, rax; dwNewLong
0x180041533  xor     edx, edx; nIndex
0x180041535  mov     rcx, r12; hWnd
0x180041538  call    cs:__imp_SetWindowLongPtrW
0x18004153e  mov     rax, rbx
0x180041541  jmp     loc_180041FEB
0x180041546  xor     edx, edx; nIndex
0x180041548  call    cs:__imp_GetWindowLongPtrW
0x18004154e  mov     rdi, rax
0x180041551  test    rax, rax
0x180041554  jnz     short loc_18004156D
0x180041556  mov     r9, rbx; lParam
0x180041559  mov     r8, rsi; wParam
0x18004155c  mov     edx, r14d; Msg
0x18004155f  mov     rcx, r12; hWnd
0x180041562  call    cs:__imp_DefWindowProcW
0x180041568  jmp     loc_180041FEB
0x18004156d  mov     r13d, 0FFFh
0x180041573  cmp     r14d, 1Ah
0x180041577  ja      loc_1800418A4
0x18004157d  jz      loc_18004187B
0x180041583  cmp     r14d, 0Ch
0x180041587  ja      loc_180041756
0x18004158d  jz      loc_180041F9A
0x180041593  mov     eax, r14d
0x180041596  sub     eax, 1
0x180041599  jz      loc_18004173B
0x18004159f  sub     eax, 1
0x1800415a2  jz      loc_1800416F3
0x1800415a8  sub     eax, 3
0x1800415ab  jz      loc_180041E78
0x1800415b1  sub     eax, 2
0x1800415b4  jz      short loc_18004160D
0x1800415b6  sub     eax, 1
0x1800415b9  jz      short loc_18004160D
0x1800415bb  cmp     eax, 2
0x1800415be  jnz     loc_180041FB0
0x1800415c4  mov     ecx, [rdi+178h]
0x1800415ca  xor     edx, edx
0x1800415cc  test    rsi, rsi
0x1800415cf  mov     eax, ecx
0x1800415d1  setnz   dl; bEnable
0x1800415d4  and     eax, 1
0x1800415d7  cmp     eax, edx
0x1800415d9  jz      loc_180041FE8
0x1800415df  and     ecx, 0FFFFFFFEh
0x1800415e2  or      ecx, edx
0x1800415e4  mov     [rdi+178h], ecx
0x1800415ea  mov     rcx, [rdi+38h]; hWnd
0x1800415ee  test    rcx, rcx
0x1800415f1  jz      short loc_1800415F9
0x1800415f3  call    cs:__imp_EnableWindow
0x1800415f9  mov     rcx, [rdi]; hWnd
0x1800415fc  xor     edx, edx; lpRect
0x1800415fe  lea     r8d, [rdx+1]; bErase
0x180041602  call    cs:__imp_InvalidateRect
0x180041608  jmp     loc_180041FE8
0x18004160d  mov     edx, [rdi+178h]
0x180041613  xor     ebx, ebx
0x180041615  cmp     r14d, 7
0x180041619  mov     eax, edx
0x18004161b  setz    bl
0x18004161e  shr     eax, 2
0x180041621  and     eax, 1
0x180041624  cmp     ebx, eax
0x180041626  jz      loc_1800416C1
0x18004162c  movsxd  rax, dword ptr [rdi+0C4h]
0x180041633  lea     ecx, ds:0[rbx*4]
0x18004163a  and     edx, 0FFFFFFFBh
0x18004163d  or      ecx, edx
0x18004163f  mov     [rdi+178h], ecx
0x180041645  test    eax, eax
0x180041647  js      short loc_180041670
0x180041649  mov     rdx, [rdi+0E8h]
0x180041650  lea     rcx, [rax+rax*4]
0x180041654  mov     r8d, [rdi+0C0h]
0x18004165b  shl     rcx, 4
0x18004165f  add     rcx, 4
0x180041663  add     rdx, rcx
0x180041666  mov     rcx, [rdi]; hWnd
0x180041669  call    InvalidateScrollRect
0x18004166e  jmp     short loc_1800416B1
0x180041670  test    byte ptr [rdi+10h], 2
0x180041674  jz      short loc_18004169F
0x180041676  btr     ecx, 7
0x18004167a  lea     rdx, [rdi+138h]; lpRect
0x180041681  mov     eax, ebx
0x180041683  mov     r8d, 1; bErase
0x180041689  shl     eax, 7
0x18004168c  or      eax, ecx
0x18004168e  mov     rcx, [rdi]; hWnd
0x180041691  mov     [rdi+178h], eax
0x180041697  call    cs:__imp_InvalidateRect
0x18004169d  jmp     short loc_1800416B1
0x18004169f  cmp     r14d, 7
0x1800416a3  jnz     short loc_1800416B1
0x1800416a5  lea     edx, [r14-6]
0x1800416a9  mov     rcx, rdi
0x1800416ac  call    SECIncrFocus
0x1800416b1  lea     edx, [rbx-8]
0x1800416b4  mov     rcx, rdi
0x1800416b7  lea     r8, [rsp+200h+var_1C8]
0x1800416bc  call    CCSendNotify
0x1800416c1  mov     rcx, rdi
0x1800416c4  cmp     r14d, 7
0x1800416c8  jnz     short loc_1800416DA
0x1800416ca  mov     edx, [rdi+168h]
0x1800416d0  call    SECSafeSetCurSubed
0x1800416d5  jmp     loc_180041FE8
0x1800416da  mov     eax, [rdi+0C4h]
0x1800416e0  or      edx, 0FFFFFFFFh
0x1800416e3  mov     [rdi+168h], eax
0x1800416e9  call    SECSetCurSubed
0x1800416ee  jmp     loc_180041FE8
0x1800416f3  lock dec cs:g_dwWindowCount
0x1800416fa  mov     rcx, [rdi+0E0h]; hMem
0x180041701  test    rcx, rcx
0x180041704  jz      short loc_180041713
0x180041706  call    cs:__imp_LocalFree
0x18004170c  mov     [rdi+0E0h], r15
0x180041713  lea     rcx, [rdi+110h]
0x18004171a  call    MCFreeCalendarInfo
0x18004171f  mov     rcx, rdi; hMem
0x180041722  call    cs:__imp_LocalFree
0x180041728  xor     r8d, r8d; dwNewLong
0x18004172b  xor     edx, edx; nIndex
0x18004172d  mov     rcx, r12; hWnd
0x180041730  call    cs:__imp_SetWindowLongPtrW
0x180041736  jmp     loc_180041FE8
0x18004173b  call    CCCreateWindow
0x180041740  mov     r8, rbx
0x180041743  mov     rdx, r12
0x180041746  mov     rcx, rdi
0x180041749  call    DPCreateHandler
0x18004174e  mov     r15, rax
0x180041751  jmp     loc_180041FE8
0x180041756  mov     eax, r14d
0x180041759  sub     eax, 0Dh
0x18004175c  jz      short loc_1800417C0
0x18004175e  sub     eax, 1
0x180041761  jz      short loc_1800417D7
0x180041763  sub     eax, 1
0x180041766  jz      loc_180041B96
0x18004176c  sub     eax, 5
0x18004176f  jz      short loc_180041784
0x180041771  cmp     eax, 1
0x180041774  jnz     loc_180041FB0
0x18004177a  call    InitGlobalColors
0x18004177f  jmp     loc_180041FE8
0x180041784  test    byte ptr [rdi+178h], 1
0x18004178b  jnz     loc_180041FCC
0x180041791  xorps   xmm0, xmm0
0x180041794  lea     rdx, [rsp+200h+rect]; lprect
0x180041799  mov     rcx, rsi; hdc
0x18004179c  movups  xmmword ptr [rsp+200h+rect.left], xmm0
0x1800417a1  call    cs:__imp_GetClipBox
0x1800417a7  mov     r8d, cs:g_clrBtnFace; color
0x1800417ae  lea     rdx, [rsp+200h+rect]; lprect
0x1800417b3  mov     rcx, rsi; hdc
0x1800417b6  call    FillRectClr
0x1800417bb  jmp     loc_180041FE8
0x1800417c0  test    rbx, rbx
0x1800417c3  jz      short loc_1800417D1
0x1800417c5  test    rsi, rsi
0x1800417c8  jz      short loc_1800417D1
0x1800417ca  xor     eax, eax
0x1800417cc  mov     [rbx], ax
0x1800417cf  jmp     short loc_1800417D7
0x1800417d1  mov     r14d, 0Eh
0x1800417d7  mov     r13, [rdi+0E8h]
0x1800417de  xor     r12d, r12d
0x1800417e1  cmp     [rdi+0C8h], r12d
0x1800417e8  jle     loc_180041FE8
0x1800417ee  cmp     dword ptr [r13+0], 0Bh
0x1800417f3  jnz     short loc_180041800
0x1800417f5  mov     rax, [r13+40h]
0x1800417f9  mov     qword ptr [rsp+200h+rect.left], rax
0x1800417fe  jmp     short loc_180041826
0x180041800  lea     rax, [rbp+100h+var_150]
0x180041804  mov     r9d, 80h
0x18004180a  lea     rdx, [rdi+98h]
0x180041811  mov     qword ptr [rsp+200h+rect.left], rax
0x180041816  lea     r8, [rbp+100h+var_150]
0x18004181a  mov     rcx, r13
0x18004181d  call    SEGetTimeDateFormat
0x180041822  lea     rax, [rbp+100h+var_150]
0x180041826  mov     rcx, rax; lpString
0x180041829  call    cs:__imp_lstrlenW
0x18004182f  mov     r11d, eax
0x180041832  cmp     r14d, 0Dh
0x180041836  jnz     short loc_18004185F
0x180041838  lea     edx, [r11+r15]
0x18004183c  cmp     rdx, rsi
0x18004183f  jnb     loc_180041FE8
0x180041845  mov     r8, qword ptr [rsp+200h+rect.left]; pszSrc
0x18004184a  mov     rdx, rsi
0x18004184d  mov     ecx, r15d
0x180041850  sub     rdx, rcx; cchDest
0x180041853  mov     rcx, rbx; pszDest
0x180041856  call    StringCchCopyW
0x18004185b  lea     rbx, [rbx+r11*2]
0x18004185f  add     r15d, r11d
0x180041862  inc     r12d
0x180041865  add     r13, 50h ; 'P'
0x180041869  cmp     r12d, [rdi+0C8h]
0x180041870  jl      loc_1800417EE
0x180041876  jmp     loc_180041FE8
0x18004187b  test    rbx, rbx
0x18004187e  jz      short loc_180041897
0x180041880  lea     rdx, aIntl; "Intl"
0x180041887  mov     rcx, rbx; pszStr1
0x18004188a  call    StrCmpICW
0x18004188f  test    eax, eax
0x180041891  jnz     loc_180041FE8
0x180041897  mov     rcx, rdi
0x18004189a  call    DPHandleLocaleChange
0x18004189f  jmp     loc_180041FE8
0x1800418a4  mov     eax, 318h
0x1800418a9  cmp     r14d, eax
0x1800418ac  ja      loc_180041BEA
0x1800418b2  jz      loc_180041B96
0x1800418b8  cmp     r14d, 7Dh ; '}'
0x1800418bc  ja      loc_180041A5D
0x1800418c2  jz      loc_180041A16
0x1800418c8  mov     eax, r14d
0x1800418cb  sub     eax, 30h ; '0'
0x1800418ce  jz      loc_180041A02
0x1800418d4  sub     eax, 1
0x1800418d7  jz      loc_1800419F6
0x1800418dd  sub     eax, 1Dh
0x1800418e0  jz      short loc_180041942
0x1800418e2  sub     eax, 7
0x1800418e5  jz      short loc_180041932
0x1800418e7  sub     eax, 26h ; '&'
0x1800418ea  jz      short loc_180041911
0x1800418ec  cmp     eax, 1
0x1800418ef  jnz     loc_180041FB0
0x1800418f5  cmp     esi, 0FFFFFFF0h
0x1800418f8  jnz     loc_180041FE8
0x1800418fe  mov     eax, [rbx+4]
0x180041901  xor     eax, [rdi+10h]
0x180041904  and     eax, 0FFC3h
0x180041909  xor     [rbx+4], eax
0x18004190c  jmp     loc_180041FE8
0x180041911  mov     rcx, [rdi+40h]; hWnd
0x180041915  test    rcx, rcx
0x180041918  jz      loc_180041FCC
0x18004191e  mov     r9, rbx; lParam
0x180041921  mov     r8, rsi; wParam
0x180041924  mov     edx, r14d; Msg
0x180041927  call    cs:__imp_SendMessageW
0x18004192d  jmp     loc_18004174E
0x180041932  mov     rdx, rbx
0x180041935  mov     rcx, rdi
0x180041938  call    CIHandleNotifyFormat
0x18004193d  jmp     loc_180041FEB
0x180041942  mov     r14d, 0FFFFFD13h
0x180041948  cmp     [rbx+10h], r14d
0x18004194c  jz      short loc_1800419B5
0x18004194e  cmp     dword ptr [rbx+10h], 0FFFFFD16h
0x180041955  jz      short loc_1800419B5
0x180041957  cmp     dword ptr [rbx+10h], 0FFFFFD2Eh
0x18004195e  jnz     loc_180041FE8
0x180041964  cmp     esi, 3E8h
0x18004196a  jnz     loc_180041FE8
  ... truncated ...
```
