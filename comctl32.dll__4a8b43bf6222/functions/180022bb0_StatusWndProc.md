# StatusWndProc

- ea: `0x180022bb0`
- end: `0x18002394b`
- name: `StatusWndProc`
- size: `3483`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, HDC hdc, LPCCH lpMultiByteStr)`
- caller_count: `0`
- callee_count: `22`
- tags: `installer_update`

## callees

- `0x1800115f0`
- `0x180017bac`
- `0x1800183dc`
- `0x180018464`
- `0x1800190a4`
- `0x18001923c`
- `0x180019844`
- `0x180019aa8`
- `0x180021c80`
- `0x180021dc4`
- `0x180021f10`
- `0x1800222e4`
- `0x180022470`
- `0x1800225f8`
- `0x1800226b0`
- `0x180022a00`
- `0x180022bb0`
- `0x180023954`
- `0x18002fd4c`
- `0x180037080`
- `0x18003a530`
- `0x180042570`

## import_xrefs

- `GDI32!DeleteObject` at `0x180022fef`
- `GDI32!DeleteObject` at `0x1800237e5`
- `GDI32!DeleteObject` at `0x1800237ef`
- `GDI32!DeleteObject` at `0x180022fef`
- `GDI32!DeleteObject` at `0x1800237e5`
- `GDI32!DeleteObject` at `0x1800237ef`
- `GDI32!GetObjectW` at `0x1800237db`
- `GDI32!GetObjectW` at `0x1800237db`
- `KERNEL32!LocalFree` at `0x180022e80`
- `KERNEL32!LocalFree` at `0x180022eb0`
- `KERNEL32!LocalFree` at `0x180022ee8`
- `KERNEL32!LocalFree` at `0x180022ef1`
- `KERNEL32!LocalFree` at `0x18002345f`
- `KERNEL32!LocalFree` at `0x180023639`
- `KERNEL32!LocalFree` at `0x180022e80`
- `KERNEL32!LocalFree` at `0x180022eb0`
- `KERNEL32!LocalFree` at `0x180022ee8`
- `KERNEL32!LocalFree` at `0x180022ef1`
- `KERNEL32!LocalFree` at `0x18002345f`
- `KERNEL32!LocalFree` at `0x180023639`
- `KERNEL32!WideCharToMultiByte` at `0x180023910`
- `KERNEL32!WideCharToMultiByte` at `0x180023910`
- `USER32!GetClientRect` at `0x180022de2`
- `USER32!GetClientRect` at `0x180023068`
- `USER32!GetClientRect` at `0x180022de2`
- `USER32!GetClientRect` at `0x180023068`
- `USER32!GetWindowLongW` at `0x180022d2a`
- `USER32!GetWindowLongW` at `0x180022d2a`
- `USER32!IsWindow` at `0x180022eba`
- `USER32!IsWindow` at `0x180022eba`
- `USER32!PtInRect` at `0x180023332`
- `USER32!PtInRect` at `0x180023332`
- `USER32!SendMessageW` at `0x180022fb3`
- `USER32!SendMessageW` at `0x180023039`
- `USER32!SendMessageW` at `0x180022fb3`
- `USER32!SendMessageW` at `0x180023039`
- `USER32!RedrawWindow` at `0x180022f89`
- `USER32!RedrawWindow` at `0x180023018`
- `USER32!RedrawWindow` at `0x180022f89`
- `USER32!RedrawWindow` at `0x180023018`
- `USER32!ScreenToClient` at `0x180022cea`
- `USER32!ScreenToClient` at `0x180022cea`
- `USER32!DestroyWindow` at `0x180022ec8`
- `USER32!DestroyWindow` at `0x180022ec8`
- `USER32!SetWindowLongPtrW` at `0x180022f04`
- `USER32!SetWindowLongPtrW` at `0x180022f04`
- `USER32!InvalidateRect` at `0x180022dbd`
- `USER32!InvalidateRect` at `0x180022e20`
- `USER32!InvalidateRect` at `0x180023163`
- `USER32!InvalidateRect` at `0x18002356e`
- `USER32!InvalidateRect` at `0x18002373e`
- `USER32!InvalidateRect` at `0x18002381d`
- `USER32!InvalidateRect` at `0x180022dbd`
- `USER32!InvalidateRect` at `0x180022e20`
- `USER32!InvalidateRect` at `0x180023163`
- `USER32!InvalidateRect` at `0x18002356e`
- `USER32!InvalidateRect` at `0x18002373e`
- `USER32!InvalidateRect` at `0x18002381d`
- `USER32!GetWindowLongPtrW` at `0x180022bf3`
- `USER32!GetWindowLongPtrW` at `0x180022bf3`
- `USER32!DefWindowProcW` at `0x180023925`
- `USER32!DefWindowProcW` at `0x180023925`
- `USER32!IsZoomed` at `0x1800230e6`
- `USER32!IsZoomed` at `0x1800230e6`
- `USER32!UpdateWindow` at `0x180023826`
- `USER32!UpdateWindow` at `0x180023826`
- `USER32!GetIconInfo` at `0x1800237c8`
- `USER32!GetIconInfo` at `0x1800237c8`
- `USER32!GetWindowRect` at `0x180022ccb`
- `USER32!GetWindowRect` at `0x180023102`
- `USER32!GetWindowRect` at `0x180022ccb`
- `USER32!GetWindowRect` at `0x180023102`

## pseudocode

```c
__int64 __fastcall StatusWndProc(HWND hWnd, UINT Msg, unsigned __int64 hdc, CHAR *lpMultiByteStr)
{
  HICON v5; // r14
  unsigned __int64 v6; // rsi
  struct HICON__ *WindowLongPtrW; // rdi
  int v9; // r9d
  int v10; // r12d
  int v11; // r9d
  int v12; // r8d
  __int64 result; // rax
  HWND v14; // rcx
  __int64 v15; // r13
  unsigned int v16; // r14d
  _WORD *v17; // rax
  int v18; // edx
  LONG right; // eax
  int v20; // eax
  LONG v21; // eax
  HWND v22; // rcx
  __int64 v23; // r13
  int v24; // r14d
  void *v25; // rcx
  HWND v26; // rdi
  HWND v27; // rcx
  void *v28; // rcx
  HWND v29; // rcx
  HWND v30; // rcx
  int v31; // ecx
  __int64 v32; // r8
  __int64 v33; // rbx
  __int64 v34; // rax
  _WORD *v35; // rcx
  unsigned int v36; // r13d
  bool v37; // cc
  int v38; // eax
  bool v39; // zf
  int v40; // ecx
  int v41; // eax
  int v42; // ebx
  __int64 v43; // r8
  int v44; // eax
  __int64 v45; // rcx
  int v46; // eax
  int v47; // eax
  __int64 v48; // rbx
  __int64 v49; // rax
  void *v50; // rdi
  int v51; // r9d
  int v52; // r8d
  __int64 v53; // rcx
  unsigned int v54; // ebx
  __int64 v55; // rbx
  __int64 v56; // rcx
  unsigned __int64 v57; // rdx
  _WORD *v58; // r9
  __int64 v59; // r8
  _WORD *v60; // rax
  _WORD *v61; // rcx
  __int64 v62; // r8
  char lpMultiByteStra; // [rsp+20h] [rbp-B9h]
  int v65; // [rsp+48h] [rbp-91h]
  LPCCH v66; // [rsp+50h] [rbp-89h] BYREF
  ICONINFO piconinfo; // [rsp+58h] [rbp-81h] BYREF
  __int128 v68; // [rsp+78h] [rbp-61h] BYREF
  __int128 v69; // [rsp+88h] [rbp-51h]
  POINT pt[2]; // [rsp+98h] [rbp-41h]
  __int64 v71; // [rsp+A8h] [rbp-31h]
  struct tagRECT pv[2]; // [rsp+B0h] [rbp-29h] BYREF
  struct tagRECT Rect; // [rsp+D0h] [rbp-9h] BYREF

  v66 = lpMultiByteStr;
  *(_QWORD *)&Rect.left = hdc;
  v5 = (HICON)lpMultiByteStr;
  v6 = hdc;
  WindowLongPtrW = (struct HICON__ *)GetWindowLongPtrW(hWnd, 0);
  v71 = 0;
  v68 = 0;
  v10 = 1;
  v69 = 0;
  *(_OWORD *)&pt[0].x = 0;
  if ( !WindowLongPtrW && Msg != 1 )
    goto LABEL_252;
  if ( Msg <= 0x206 )
  {
    if ( Msg == 518 )
    {
      v36 = -6;
    }
    else
    {
      if ( Msg <= 0x31 )
      {
        if ( Msg == 49 )
        {
          if ( WindowLongPtrW )
            return *((_QWORD *)WindowLongPtrW + 8);
          return 0;
        }
        if ( Msg <= 0xE )
        {
          switch ( Msg )
          {
            case 0xEu:
              v11 = 0;
              v12 = 0;
              return (unsigned __int16)SBGetText((_DWORD)WindowLongPtrW, 0, v12, v11, 1);
            case 1u:
              CCCreateWindow();
              return InitStatusWnd(hWnd);
            case 2u:
              _InterlockedDecrement(&g_dwWindowCount);
              if ( WindowLongPtrW )
              {
                NewFont(WindowLongPtrW, -1, 0);
                v23 = *((_QWORD *)WindowLongPtrW + 21);
                if ( *((_DWORD *)WindowLongPtrW + 40) - 1 >= 0 )
                {
                  v24 = *((_DWORD *)WindowLongPtrW + 40) - 1;
                  do
                  {
                    if ( (*(_DWORD *)(v23 + 8) & 0xF000) == 0xF000 )
                      LocalFree(*(HLOCAL *)v23);
                    Str_Set(v23 + 32, 0);
                    v23 += 48;
                    --v24;
                  }
                  while ( v24 >= 0 );
                  v6 = *(_QWORD *)&Rect.left;
                  v5 = (HICON)v66;
                }
                if ( ((_DWORD)WindowLongPtrW[30] & 0xF000) == 0xF000 )
                  LocalFree(*((HLOCAL *)WindowLongPtrW + 14));
                if ( IsWindow(*((HWND *)WindowLongPtrW + 7)) )
                  DestroyWindow(*((HWND *)WindowLongPtrW + 7));
                Str_Set(WindowLongPtrW + 36, 0);
                v25 = (void *)*((_QWORD *)WindowLongPtrW + 21);
                if ( v25 )
                  LocalFree(v25);
                LocalFree(WindowLongPtrW);
                v26 = hWnd;
                SetWindowLongPtrW(hWnd, 0, 0);
                return DefWindowProcW(v26, Msg, v6, (LPARAM)v5);
              }
              goto LABEL_252;
          }
          if ( Msg != 5 )
          {
            if ( Msg != 12 )
            {
              if ( Msg == 13 )
              {
                v11 = v6;
                v12 = (int)v5;
                return (unsigned __int16)SBGetText((_DWORD)WindowLongPtrW, 0, v12, v11, 1);
              }
LABEL_217:
              v66 = 0;
              if ( (unsigned int)CCWndProc((_DWORD)WindowLongPtrW, Msg, v6, v9, (__int64)&v66) )
                return (__int64)v66;
              goto LABEL_252;
            }
            v6 = 0;
            goto LABEL_17;
          }
          Rect = 0;
          if ( WindowLongPtrW )
          {
            GetWindowRect(*(HWND *)WindowLongPtrW, &Rect);
            Rect.right -= Rect.left;
            Rect.bottom -= Rect.top;
            v14 = (HWND)*((_QWORD *)WindowLongPtrW + 1);
            if ( v14 )
            {
              ScreenToClient(v14, (LPPOINT)&Rect);
              if ( ((_DWORD)WindowLongPtrW[8] & 0x400000) != 0 )
                Rect.left -= Rect.right;
            }
            GetWindowLongW(*(HWND *)WindowLongPtrW, -16);
            NewSize(*(HWND *)WindowLongPtrW, Rect.top, Rect.right, Rect.bottom);
            v15 = *((_QWORD *)WindowLongPtrW + 21);
            if ( *((int *)WindowLongPtrW + 40) > 0 )
            {
              v16 = 0;
              do
              {
                if ( (*(_DWORD *)(v15 + 8) & 0xF000) == 0xF000 )
                {
                  v17 = *(_WORD **)v15;
                  if ( *(_QWORD *)v15 )
                  {
                    v18 = 0;
                    while ( *v17 )
                    {
                      if ( *v17 == 9 )
                      {
                        if ( !v17 )
                          break;
                        ++v18;
                      }
                      ++v17;
                    }
                    if ( v18 >= 2 )
                    {
                      Status_GetRect(WindowLongPtrW, v16, &Rect);
                      InvalidateRect(*(HWND *)WindowLongPtrW, &Rect, 0);
                    }
                  }
                }
                ++v16;
                v15 += 48;
              }
              while ( (signed int)v16 < *((_DWORD *)WindowLongPtrW + 40) );
              v5 = (HICON)v66;
            }
            GetClientRect(*(HWND *)WindowLongPtrW, &Rect);
            right = Rect.right;
            if ( Rect.right > *((_DWORD *)WindowLongPtrW + 24) )
              right = *((_DWORD *)WindowLongPtrW + 24);
            v20 = right - *((_DWORD *)WindowLongPtrW + 21) - g_cxBorder;
            if ( *((_DWORD *)WindowLongPtrW + 25) )
              v21 = v20 - *((_DWORD *)WindowLongPtrW + 25);
            else
              v21 = v20 - *((_DWORD *)WindowLongPtrW + 23);
            v22 = *(HWND *)WindowLongPtrW;
            Rect.left = v21;
            InvalidateRect(v22, &Rect, 1);
            RecalcTooltipRects(WindowLongPtrW);
            *(_DWORD *)(WindowLongPtrW + 24) = Rect.right;
            goto LABEL_199;
          }
          return 0;
        }
        if ( Msg != 15 )
        {
          switch ( Msg )
          {
            case 0x14u:
              if ( WindowLongPtrW && *((_DWORD *)WindowLongPtrW + 41) != -16777216 )
              {
                Rect = 0;
                GetClientRect(hWnd, &Rect);
                FillRectClr((HDC)v6, &Rect, *((_DWORD *)WindowLongPtrW + 41));
                return 1;
              }
              break;
            case 0x15u:
              v29 = (HWND)*((_QWORD *)WindowLongPtrW + 7);
              if ( v29 )
                SendMessageW(v29, Msg, v6, (LPARAM)v5);
              break;
            case 0x1Au:
              InitGlobalColors();
              InitGlobalMetrics(v6);
              v27 = (HWND)*((_QWORD *)WindowLongPtrW + 7);
              if ( v27 )
                SendMessageW(v27, Msg, v6, (LPARAM)v5);
              if ( *((_DWORD *)WindowLongPtrW + 25) )
                *((_DWORD *)WindowLongPtrW + 25) = g_cxBorder + g_cxVScroll;
              if ( v6 == 42 )
              {
                if ( *((_DWORD *)WindowLongPtrW + 18) )
                {
                  v28 = (void *)*((_QWORD *)WindowLongPtrW + 8);
                  if ( v28 )
                  {
                    DeleteObject(v28);
                    *((_QWORD *)WindowLongPtrW + 8) = 0;
                    *((_DWORD *)WindowLongPtrW + 18) = 0;
                    NewFont(WindowLongPtrW, 0, 1);
                    RedrawWindow(*(HWND *)WindowLongPtrW, 0, 0, 0x101u);
                  }
                }
              }
              break;
            case 0x30u:
              if ( !WindowLongPtrW )
                return 0;
              NewFont(WindowLongPtrW, v6, 1);
              if ( (_DWORD)v5 )
                RedrawWindow(*(HWND *)WindowLongPtrW, 0, 0, 0x101u);
              return 1;
            default:
              goto LABEL_217;
          }
LABEL_252:
          v26 = hWnd;
          return DefWindowProcW(v26, Msg, v6, (LPARAM)v5);
        }
LABEL_161:
        if ( WindowLongPtrW )
        {
          if ( *((_BYTE *)WindowLongPtrW + 120) )
          {
            v43 = *((_QWORD *)WindowLongPtrW + 21);
            v10 = *((_DWORD *)WindowLongPtrW + 40);
            v44 = *((_DWORD *)WindowLongPtrW + 21);
          }
          else
          {
            LODWORD(v43) = (_DWORD)WindowLongPtrW + 112;
            v44 = 0;
          }
          PaintStatusWnd((_DWORD)WindowLongPtrW, v6, v43, v10, v44);
          return 0;
        }
        goto LABEL_252;
      }
      if ( Msg <= 0x200 )
      {
        if ( Msg != 512 )
        {
          if ( Msg == 61 )
          {
            if ( (_DWORD)v5 == -12 )
              return 65547;
            goto LABEL_252;
          }
          if ( Msg != 78 )
          {
            if ( Msg == 85 )
              return CIHandleNotifyFormat(WindowLongPtrW, v5);
            if ( Msg == 125 )
            {
              if ( v6 == -20 )
              {
                if ( ((*((_DWORD *)v5 + 1) ^ *((_DWORD *)WindowLongPtrW + 8)) & 0x400000) != 0 )
                  InvalidateRect(*(HWND *)WindowLongPtrW, 0, 1);
                WindowLongPtrW[8] = v5[1];
              }
              return 0;
            }
            if ( Msg != 132 )
              goto LABEL_217;
            if ( *((_DWORD *)WindowLongPtrW + 25) && !IsZoomed(*((HWND *)WindowLongPtrW + 1)) )
            {
              v30 = *(HWND *)WindowLongPtrW;
              Rect = 0;
              GetWindowRect(v30, &Rect);
              v31 = *((_DWORD *)WindowLongPtrW + 25);
              if ( ((_DWORD)WindowLongPtrW[8] & 0x400000) != 0 )
              {
                if ( (__int16)v5 < Rect.left + v31 )
                  return 16;
              }
              else if ( (__int16)v5 > Rect.right - v31 )
              {
                return 17;
              }
            }
            goto LABEL_252;
          }
          v32 = *((unsigned int *)v5 + 4);
          v33 = 0;
          if ( (_DWORD)v32 != -530 )
          {
LABEL_110:
            SendNotifyEx(*((_QWORD *)WindowLongPtrW + 1), -1, v32, v5, (_DWORD)WindowLongPtrW[6] & 1);
            if ( *((_DWORD *)v5 + 4) == -530 )
            {
              v35 = (_WORD *)*((_QWORD *)v5 + 3);
              if ( (unsigned __int64)(v35 - 0x8000) <= 0xFFFFFFFFFFFEFFFEuLL && !*v35 )
              {
                v26 = hWnd;
                if ( v33 )
                  *((_QWORD *)v5 + 3) = *(_QWORD *)(v33 + 32);
                return DefWindowProcW(v26, Msg, v6, (LPARAM)v5);
              }
            }
            goto LABEL_199;
          }
          v34 = *((int *)v5 + 2);
          if ( (_DWORD)v34 == 255 )
          {
            v33 = (__int64)(WindowLongPtrW + 28);
          }
          else
          {
            if ( (int)v34 < 0 || (int)v34 >= *((_DWORD *)WindowLongPtrW + 40) )
              goto LABEL_199;
            v33 = *((_QWORD *)WindowLongPtrW + 21) + 48 * v34;
          }
          if ( v33 && *(_DWORD *)(v33 + 40) )
            goto LABEL_110;
LABEL_199:
          v26 = hWnd;
          return DefWindowProcW(v26, Msg, v6, (LPARAM)v5);
        }
LABEL_124:
        StatusForceCreateTooltips(WindowLongPtrW);
        RelayToToolTips(*((_QWORD *)WindowLongPtrW + 7), (_DWORD)hWnd, Msg, v6, (__int64)v5);
        goto LABEL_252;
      }
      switch ( Msg )
      {
        case 0x201u:
          goto LABEL_124;
        case 0x202u:
          v36 = -2;
          StatusForceCreateTooltips(WindowLongPtrW);
          RelayToToolTips(*((_QWORD *)WindowLongPtrW + 7), (_DWORD)hWnd, 514, v6, (__int64)v5);
          break;
        case 0x203u:
          v36 = -3;
          break;
        case 0x205u:
          v36 = -5;
          break;
        default:
          goto LABEL_217;
      }
    }
    pt[1].x = (unsigned __int16)v5;
    pt[1].y = WORD1(v5);
    v37 = *((_QWORD *)WindowLongPtrW + 5) < 5LL;
    v38 = *((_DWORD *)WindowLongPtrW + 30);
    Rect = 0;
    if ( v37 )
      v39 = v38 == 0;
    else
      v39 = (_BYTE)v38 == 0;
    if ( v39 )
    {
      v40 = 255;
    }
    else
    {
      v41 = 0;
      v65 = 0;
      if ( *((int *)WindowLongPtrW + 40) <= 0 )
      {
LABEL_134:
        v40 = -2;
      }
      else
      {
        while ( 1 )
        {
          Status_GetRect(WindowLongPtrW, (unsigned int)v41, &Rect);
          if ( PtInRect(&Rect, pt[1]) )
            break;
          v41 = v65 + 1;
          v65 = v41;
          if ( v41 >= *((_DWORD *)WindowLongPtrW + 40) )
            goto LABEL_134;
        }
        v40 = v65;
      }
    }
    *((_QWORD *)&v69 + 1) = v40;
    if ( !SendNotifyEx(*((_QWORD *)WindowLongPtrW + 1), *(_QWORD *)WindowLongPtrW, v36, &v68, 0) )
      goto LABEL_199;
    return 0;
  }
  if ( Msg > 0x40B )
  {
    if ( Msg > 0x411 )
    {
      if ( Msg == 1042 )
      {
        if ( (unsigned __int16)v6 == 255 )
        {
          v62 = (__int64)(WindowLongPtrW + 28);
        }
        else
        {
          if ( (unsigned __int16)v6 >= *((int *)WindowLongPtrW + 40) )
            goto LABEL_252;
          v62 = *((_QWORD *)WindowLongPtrW + 21) + 48LL * (unsigned __int16)v6;
        }
        if ( v62 )
          WideCharToMultiByte(0, 0, *(LPCWCH *)(v62 + 32), -1, (LPSTR)v5, WORD1(v6), 0, 0);
        goto LABEL_252;
      }
      if ( Msg == 1043 )
      {
        if ( (unsigned __int16)v6 == 255 )
        {
          v56 = (__int64)(WindowLongPtrW + 28);
        }
        else
        {
          if ( (unsigned __int16)v6 >= *((int *)WindowLongPtrW + 40) )
            goto LABEL_252;
          v56 = *((_QWORD *)WindowLongPtrW + 21) + 48LL * (unsigned __int16)v6;
        }
        if ( v56 )
        {
          v57 = (unsigned __int64)WORD1(v6) >> 1;
          if ( v57 )
          {
            v58 = *(_WORD **)(v56 + 32);
            v59 = 2147483646;
            v60 = v5;
            do
            {
              if ( !v59 )
                break;
              if ( !*v58 )
                break;
              *v60++ = *v58++;
              --v59;
              --v57;
            }
            while ( v57 );
            v61 = v60 - 1;
            if ( v57 )
              v61 = v60;
            *v61 = 0;
          }
        }
        goto LABEL_252;
      }
      if ( Msg != 1044 )
      {
        if ( Msg == 8193 )
        {
          v54 = *((_DWORD *)WindowLongPtrW + 41);
          *((_DWORD *)WindowLongPtrW + 41) = (_DWORD)v5;
          InvalidateRect(hWnd, 0, 1);
          return v54;
        }
        goto LABEL_217;
      }
    }
    else
    {
      switch ( Msg )
      {
        case 0x411u:
          if ( (_DWORD)v6 == 255 )
          {
            v53 = (__int64)(WindowLongPtrW + 28);
          }
          else
          {
            if ( (v6 & 0x80000000) != 0LL || (int)v6 >= *((_DWORD *)WindowLongPtrW + 40) )
              goto LABEL_252;
            v53 = *((_QWORD *)WindowLongPtrW + 21) + 48LL * (int)v6;
          }
          if ( v53 )
            Str_Set(v53 + 32, v5);
          goto LABEL_252;
        case 0x40Cu:
          lpMultiByteStra = 1;
LABEL_205:
          v51 = 0;
          v52 = 0;
          return SBGetText((_DWORD)WindowLongPtrW, v6, v52, v51, lpMultiByteStra);
        case 0x40Du:
          lpMultiByteStra = 3;
          goto LABEL_202;
        case 0x40Eu:
          return *((_BYTE *)WindowLongPtrW + 120) == 0;
      }
      if ( Msg != 1039 )
      {
        if ( (_DWORD)v6 == 255 )
        {
          v48 = (__int64)(WindowLongPtrW + 28);
        }
        else
        {
          v48 = 0;
          if ( (v6 & 0x80000000) == 0LL && (int)v6 < *((_DWORD *)WindowLongPtrW + 40) )
            v48 = *((_QWORD *)WindowLongPtrW + 21) + 48LL * (int)v6;
        }
        v49 = ProduceWFromA(*((_DWORD *)WindowLongPtrW + 26), (LPCCH)v5);
        v50 = (void *)v49;
        if ( v48 )
          Str_Set(v48 + 32, v49);
        LocalFree(v50);
        goto LABEL_199;
      }
    }
    if ( v6 == -1 )
    {
      v55 = (__int64)(WindowLongPtrW + 28);
    }
    else
    {
      v55 = 0;
      if ( v6 < *((unsigned int *)WindowLongPtrW + 40) )
        v55 = *((_QWORD *)WindowLongPtrW + 21) + 48 * v6;
    }
    if ( Msg != 1044 )
    {
      if ( v55 && *(HICON *)(v55 + 16) != v5 )
      {
        memset(pv, 0, sizeof(pv));
        Rect = 0;
        if ( v5 )
        {
          memset(&piconinfo, 0, sizeof(piconinfo));
          GetIconInfo(v5, &piconinfo);
          GetObjectW(piconinfo.hbmColor, 32, pv);
          DeleteObject(piconinfo.hbmColor);
          DeleteObject(piconinfo.hbmMask);
        }
        *(_QWORD *)(v55 + 24) = *(_QWORD *)&pv[0].top;
        *(_QWORD *)(v55 + 16) = v5;
        Status_GetRect(WindowLongPtrW, (unsigned int)v6, &Rect);
        InvalidateRect(*(HWND *)WindowLongPtrW, &Rect, 1);
        UpdateWindow(*(HWND *)WindowLongPtrW);
      }
      return 1;
    }
    if ( v55 )
      return *(_QWORD *)(v55 + 16);
    else
      return 0;
  }
  else
  {
    if ( Msg == 1035 )
    {
LABEL_17:
      LODWORD(result) = SBSetText(WindowLongPtrW, v6, v5);
      return (int)result;
    }
    if ( Msg > 0x406 )
    {
      if ( Msg == 1031 )
      {
        *(_DWORD *)v5 = WindowLongPtrW[21];
        v5[1] = WindowLongPtrW[22];
        v5[2] = WindowLongPtrW[23];
        return 1;
      }
      if ( Msg == 1032 )
      {
        *((_DWORD *)WindowLongPtrW + 20) = v6;
        RecalcTooltipRects(WindowLongPtrW);
        goto LABEL_252;
      }
      if ( Msg != 1033 )
      {
        LODWORD(result) = Status_GetRect(WindowLongPtrW, (unsigned int)v6, v5);
        return (int)result;
      }
      v47 = *((_DWORD *)WindowLongPtrW + 30);
      if ( v6 )
      {
        if ( !(_BYTE)v47 )
          goto LABEL_252;
        *((_BYTE *)WindowLongPtrW + 120) = 0;
      }
      else
      {
        if ( (_BYTE)v47 )
          goto LABEL_252;
        *((_DWORD *)WindowLongPtrW + 30) = v47 | 0xFF;
      }
      RecalcTooltipRects(WindowLongPtrW);
      SendNotifyEx(*((_QWORD *)WindowLongPtrW + 1), *(_QWORD *)WindowLongPtrW, 4294966416LL, 0, 0);
      InvalidateRect(*(HWND *)WindowLongPtrW, 0, 1);
      goto LABEL_252;
    }
    switch ( Msg )
    {
      case 0x406u:
        if ( v5 )
        {
          v45 = *((_QWORD *)WindowLongPtrW + 21);
          if ( v6 > *((int *)WindowLongPtrW + 40) )
            v6 = *((int *)WindowLongPtrW + 40);
          for ( ; v6; --v6 )
          {
            v46 = *(_DWORD *)(v45 + 12);
            v45 += 48;
            *(_DWORD *)v5++ = v46;
          }
        }
        return *((int *)WindowLongPtrW + 40);
      case 0x318u:
        goto LABEL_161;
      case 0x401u:
        if ( (v6 & 0x1000) != 0 )
          v10 = 0;
        else
          v5 = (HICON)ProduceWFromA(*((_DWORD *)WindowLongPtrW + 26), (LPCCH)v5);
        if ( WindowLongPtrW )
          v42 = SBSetText(WindowLongPtrW, v6, v5);
        else
          v42 = 0;
        if ( v10 && (unsigned __int64)v5 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          LocalFree(v5);
        return v42;
      case 0x402u:
        lpMultiByteStra = 2;
LABEL_202:
        v51 = 0xFFFF;
        v52 = (int)v5;
        return SBGetText((_DWORD)WindowLongPtrW, v6, v52, v51, lpMultiByteStra);
      case 0x403u:
        lpMultiByteStra = 0;
        goto LABEL_205;
      case 0x404u:
        if ( v6 - 1 <= 0xFF )
        {
          LODWORD(result) = SetStatusParts(WindowLongPtrW, (unsigned int)v6, v5);
          return (int)result;
        }
        return 0;
      default:
        goto LABEL_217;
    }
  }
}

```

## disassembly

```asm
0x180022bb0  push    rbp
0x180022bb2  push    rbx
0x180022bb3  push    rsi
0x180022bb4  push    rdi
0x180022bb5  push    r12
0x180022bb7  push    r13
0x180022bb9  push    r14
0x180022bbb  push    r15
0x180022bbd  lea     rbp, [rsp-1Fh]
0x180022bc2  sub     rsp, 0F8h
0x180022bc9  mov     rax, cs:__security_cookie
0x180022bd0  xor     rax, rsp
0x180022bd3  mov     [rbp+57h+var_50], rax
0x180022bd7  mov     r15d, edx
0x180022bda  mov     [rsp+130h+var_E0], r9
0x180022bdf  xor     edx, edx; nIndex
0x180022be1  mov     qword ptr [rbp+57h+Rect.left], r8
0x180022be5  mov     r14, r9
0x180022be8  mov     [rsp+130h+hWnd], rcx
0x180022bed  mov     rsi, r8
0x180022bf0  mov     rbx, rcx
0x180022bf3  call    cs:__imp_GetWindowLongPtrW
0x180022bf9  xorps   xmm0, xmm0
0x180022bfc  xor     r13d, r13d
0x180022bff  mov     rdi, rax
0x180022c02  xor     eax, eax
0x180022c04  mov     [rbp+57h+var_88], rax
0x180022c08  movups  [rbp+57h+var_B8], xmm0
0x180022c0c  lea     r12d, [rax+1]
0x180022c10  movups  [rbp+57h+var_A8], xmm0
0x180022c14  movups  xmmword ptr [rbp+57h+pt.x], xmm0
0x180022c18  test    rdi, rdi
0x180022c1b  jnz     short loc_180022C26
0x180022c1d  cmp     r15d, r12d
0x180022c20  jnz     loc_180023916
0x180022c26  mov     eax, 206h
0x180022c2b  cmp     r15d, eax
0x180022c2e  ja      loc_180023388
0x180022c34  jz      loc_1800232CF
0x180022c3a  cmp     r15d, 31h ; '1'
0x180022c3e  ja      loc_180023098
0x180022c44  jz      loc_180023086
0x180022c4a  cmp     r15d, 0Eh
0x180022c4e  ja      loc_180022F2F
0x180022c54  jz      loc_180022F24
0x180022c5a  mov     eax, r15d
0x180022c5d  sub     eax, r12d
0x180022c60  jz      loc_180022F0F
0x180022c66  sub     eax, r12d
0x180022c69  jz      loc_180022E39
0x180022c6f  sub     eax, 3
0x180022c72  jz      short loc_180022CB7
0x180022c74  sub     eax, 7
0x180022c77  jz      short loc_180022C9F
0x180022c79  cmp     eax, r12d
0x180022c7c  jnz     loc_1800236F8
0x180022c82  mov     r9d, esi
0x180022c85  mov     r8, r14
0x180022c88  xor     edx, edx
0x180022c8a  mov     dword ptr [rsp+130h+lpMultiByteStr], r12d
0x180022c8f  mov     rcx, rdi
0x180022c92  call    SBGetText
0x180022c97  movzx   eax, ax
0x180022c9a  jmp     loc_18002392B
0x180022c9f  mov     rsi, r13
0x180022ca2  mov     r8, r14
0x180022ca5  mov     rdx, rsi
0x180022ca8  mov     rcx, rdi
0x180022cab  call    SBSetText
0x180022cb0  cdqe
0x180022cb2  jmp     loc_18002392B
0x180022cb7  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180022cbb  test    rdi, rdi
0x180022cbe  jz      loc_180023170
0x180022cc4  mov     rcx, [rdi]; hWnd
0x180022cc7  lea     rdx, [rbp+57h+Rect]; lpRect
0x180022ccb  call    cs:__imp_GetWindowRect
0x180022cd1  mov     eax, [rbp+57h+Rect.left]
0x180022cd4  sub     [rbp+57h+Rect.right], eax
0x180022cd7  mov     eax, [rbp+57h+Rect.top]
0x180022cda  sub     [rbp+57h+Rect.bottom], eax
0x180022cdd  mov     rcx, [rdi+8]; hWnd
0x180022ce1  test    rcx, rcx
0x180022ce4  jz      short loc_180022CFF
0x180022ce6  lea     rdx, [rbp+57h+Rect]; lpPoint
0x180022cea  call    cs:__imp_ScreenToClient
0x180022cf0  test    dword ptr [rdi+20h], 400000h
0x180022cf7  jz      short loc_180022CFF
0x180022cf9  mov     eax, [rbp+57h+Rect.right]
0x180022cfc  sub     [rbp+57h+Rect.left], eax
0x180022cff  mov     ecx, cs:g_cySmIcon
0x180022d05  cmp     [rdi+4Ch], ecx
0x180022d08  mov     edx, [rdi+50h]
0x180022d0b  cmovg   ecx, [rdi+4Ch]
0x180022d0f  mov     eax, cs:g_cyBorder
0x180022d15  mov     ebx, [rdi+58h]
0x180022d18  lea     ecx, [rcx+rax*2]
0x180022d1b  cmp     ecx, edx
0x180022d1d  cmovge  edx, ecx
0x180022d20  mov     rcx, [rdi]; hWnd
0x180022d23  add     ebx, edx
0x180022d25  mov     edx, 0FFFFFFF0h; nIndex
0x180022d2a  call    cs:__imp_GetWindowLongW
0x180022d30  mov     r9d, [rbp+57h+Rect.left]
0x180022d34  mov     edx, ebx
0x180022d36  mov     rcx, [rdi]; hWnd
0x180022d39  mov     r8d, eax
0x180022d3c  mov     eax, [rbp+57h+Rect.bottom]
0x180022d3f  or      r8d, 40h
0x180022d43  mov     dword ptr [rsp+130h+lpDefaultChar], eax; int
0x180022d47  mov     eax, [rbp+57h+Rect.right]
0x180022d4a  mov     [rsp+130h+cbMultiByte], eax; int
0x180022d4e  mov     eax, [rbp+57h+Rect.top]
0x180022d51  mov     dword ptr [rsp+130h+lpMultiByteStr], eax; int
0x180022d55  call    NewSize
0x180022d5a  mov     r13, [rdi+0A8h]
0x180022d61  xor     r8d, r8d
0x180022d64  cmp     [rdi+0A0h], r8d
0x180022d6b  jle     short loc_180022DDB
0x180022d6d  mov     ebx, 0F000h
0x180022d72  mov     r14d, r8d
0x180022d75  mov     eax, [r13+8]
0x180022d79  and     eax, ebx
0x180022d7b  cmp     eax, ebx
0x180022d7d  jnz     short loc_180022DC6
0x180022d7f  mov     rax, [r13+0]
0x180022d83  test    rax, rax
0x180022d86  jz      short loc_180022DC6
0x180022d88  mov     edx, r8d
0x180022d8b  jmp     short loc_180022D97
0x180022d8d  cmp     cx, 9
0x180022d91  jz      short loc_180022E06
0x180022d93  add     rax, 2
0x180022d97  movzx   ecx, word ptr [rax]
0x180022d9a  test    cx, cx
0x180022d9d  jnz     short loc_180022D8D
0x180022d9f  cmp     edx, 2
0x180022da2  jl      short loc_180022DC6
0x180022da4  lea     r8, [rbp+57h+Rect]
0x180022da8  mov     edx, r14d
0x180022dab  mov     rcx, rdi
0x180022dae  call    Status_GetRect
0x180022db3  mov     rcx, [rdi]; hWnd
0x180022db6  lea     rdx, [rbp+57h+Rect]; lpRect
0x180022dba  xor     r8d, r8d; bErase
0x180022dbd  call    cs:__imp_InvalidateRect
0x180022dc3  xor     r8d, r8d
0x180022dc6  add     r14d, r12d
0x180022dc9  add     r13, 30h ; '0'
0x180022dcd  cmp     r14d, [rdi+0A0h]
0x180022dd4  jl      short loc_180022D75
0x180022dd6  mov     r14, [rsp+130h+var_E0]
0x180022ddb  mov     rcx, [rdi]; hWnd
0x180022dde  lea     rdx, [rbp+57h+Rect]; lpRect
0x180022de2  call    cs:__imp_GetClientRect
0x180022de8  mov     eax, [rbp+57h+Rect.right]
0x180022deb  cmp     eax, [rdi+60h]
0x180022dee  cmovg   eax, [rdi+60h]
0x180022df2  sub     eax, [rdi+54h]
0x180022df5  sub     eax, cs:g_cxBorder
0x180022dfb  cmp     dword ptr [rdi+64h], 0
0x180022dff  jz      short loc_180022E10
0x180022e01  sub     eax, [rdi+64h]
0x180022e04  jmp     short loc_180022E13
0x180022e06  test    rax, rax
0x180022e09  jz      short loc_180022D9F
0x180022e0b  add     edx, r12d
0x180022e0e  jmp     short loc_180022D93
0x180022e10  sub     eax, [rdi+5Ch]
0x180022e13  mov     rcx, [rdi]; hWnd
0x180022e16  lea     rdx, [rbp+57h+Rect]; lpRect
0x180022e1a  mov     r8d, r12d; bErase
0x180022e1d  mov     [rbp+57h+Rect.left], eax
0x180022e20  call    cs:__imp_InvalidateRect
0x180022e26  mov     rcx, rdi
0x180022e29  call    RecalcTooltipRects
0x180022e2e  mov     eax, [rbp+57h+Rect.right]
0x180022e31  mov     [rdi+60h], eax
0x180022e34  jmp     loc_18002363F
0x180022e39  lock dec cs:g_dwWindowCount
0x180022e40  test    rdi, rdi
0x180022e43  jz      loc_180023916
0x180022e49  xor     r8d, r8d
0x180022e4c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180022e50  mov     rcx, rdi
0x180022e53  call    NewFont
0x180022e58  mov     ecx, [rdi+0A0h]
0x180022e5e  mov     ebx, 0F000h
0x180022e63  sub     ecx, r12d
0x180022e66  mov     r13, [rdi+0A8h]
0x180022e6d  js      short loc_180022EA3
0x180022e6f  mov     r14d, ecx
0x180022e72  mov     eax, [r13+8]
0x180022e76  and     eax, ebx
0x180022e78  cmp     eax, ebx
0x180022e7a  jnz     short loc_180022E86
0x180022e7c  mov     rcx, [r13+0]; hMem
0x180022e80  call    cs:__imp_LocalFree
0x180022e86  lea     rcx, [r13+20h]
0x180022e8a  xor     edx, edx
0x180022e8c  call    Str_Set
0x180022e91  add     r13, 30h ; '0'
0x180022e95  sub     r14d, r12d
0x180022e98  jns     short loc_180022E72
0x180022e9a  mov     rsi, qword ptr [rbp+57h+Rect.left]
0x180022e9e  mov     r14, [rsp+130h+var_E0]
0x180022ea3  mov     eax, [rdi+78h]
0x180022ea6  and     eax, ebx
0x180022ea8  cmp     eax, ebx
0x180022eaa  jnz     short loc_180022EB6
0x180022eac  mov     rcx, [rdi+70h]; hMem
0x180022eb0  call    cs:__imp_LocalFree
0x180022eb6  mov     rcx, [rdi+38h]; hWnd
0x180022eba  call    cs:__imp_IsWindow
0x180022ec0  test    eax, eax
0x180022ec2  jz      short loc_180022ECE
0x180022ec4  mov     rcx, [rdi+38h]; hWnd
0x180022ec8  call    cs:__imp_DestroyWindow
0x180022ece  lea     rcx, [rdi+90h]
0x180022ed5  xor     edx, edx
0x180022ed7  call    Str_Set
0x180022edc  mov     rcx, [rdi+0A8h]; hMem
0x180022ee3  test    rcx, rcx
0x180022ee6  jz      short loc_180022EEE
0x180022ee8  call    cs:__imp_LocalFree
0x180022eee  mov     rcx, rdi; hMem
0x180022ef1  call    cs:__imp_LocalFree
0x180022ef7  mov     rdi, [rsp+130h+hWnd]
0x180022efc  xor     r8d, r8d; dwNewLong
0x180022eff  mov     rcx, rdi; hWnd
0x180022f02  xor     edx, edx; nIndex
0x180022f04  call    cs:__imp_SetWindowLongPtrW
0x180022f0a  jmp     loc_180023919
0x180022f0f  call    CCCreateWindow
0x180022f14  mov     rdx, r14
0x180022f17  mov     rcx, rbx; hWnd
0x180022f1a  call    InitStatusWnd
0x180022f1f  jmp     loc_18002392B
0x180022f24  xor     r9d, r9d
0x180022f27  xor     r8d, r8d
0x180022f2a  jmp     loc_180022C88
0x180022f2f  mov     eax, r15d
0x180022f32  sub     eax, 0Fh
0x180022f35  jz      loc_18002346D
0x180022f3b  sub     eax, 5
0x180022f3e  jz      loc_180023044
0x180022f44  sub     eax, r12d
0x180022f47  jz      loc_180023023
0x180022f4d  sub     eax, 5
0x180022f50  jz      short loc_180022F94
0x180022f52  cmp     eax, 16h
0x180022f55  jnz     loc_1800236F8
0x180022f5b  test    rdi, rdi
0x180022f5e  jz      loc_180023170
0x180022f64  mov     r8d, r12d
0x180022f67  mov     rdx, rsi
0x180022f6a  mov     rcx, rdi
0x180022f6d  call    NewFont
0x180022f72  test    r14d, r14d
0x180022f75  jz      loc_18002359D
0x180022f7b  mov     rcx, [rdi]; hWnd
0x180022f7e  mov     r9d, 101h; flags
0x180022f84  xor     r8d, r8d; hrgnUpdate
0x180022f87  xor     edx, edx; lprcUpdate
0x180022f89  call    cs:__imp_RedrawWindow
0x180022f8f  jmp     loc_18002359D
0x180022f94  call    InitGlobalColors
0x180022f99  mov     rcx, rsi
0x180022f9c  call    InitGlobalMetrics
0x180022fa1  mov     rcx, [rdi+38h]; hWnd
0x180022fa5  test    rcx, rcx
0x180022fa8  jz      short loc_180022FB9
0x180022faa  mov     r9, r14; lParam
0x180022fad  mov     r8, rsi; wParam
0x180022fb0  mov     edx, r15d; Msg
0x180022fb3  call    cs:__imp_SendMessageW
0x180022fb9  cmp     [rdi+64h], r13d
0x180022fbd  jz      short loc_180022FCE
0x180022fbf  mov     ecx, cs:g_cxVScroll
0x180022fc5  add     ecx, cs:g_cxBorder
0x180022fcb  mov     [rdi+64h], ecx
0x180022fce  cmp     rsi, 2Ah ; '*'
0x180022fd2  jnz     loc_180023916
0x180022fd8  cmp     [rdi+48h], r13d
0x180022fdc  jz      loc_180023916
0x180022fe2  mov     rcx, [rdi+40h]; ho
0x180022fe6  test    rcx, rcx
0x180022fe9  jz      loc_180023916
0x180022fef  call    cs:__imp_DeleteObject
0x180022ff5  mov     r8d, r12d
0x180022ff8  mov     [rdi+40h], r13
0x180022ffc  xor     edx, edx
0x180022ffe  mov     [rdi+48h], r13d
0x180023002  mov     rcx, rdi
0x180023005  call    NewFont
0x18002300a  mov     rcx, [rdi]; hWnd
0x18002300d  mov     r9d, 101h; flags
0x180023013  xor     r8d, r8d; hrgnUpdate
0x180023016  xor     edx, edx; lprcUpdate
0x180023018  call    cs:__imp_RedrawWindow
  ... truncated ...
```
