# ToolbarWndProc

- ea: `0x18002aab0`
- end: `0x18002c8cc`
- name: `ToolbarWndProc`
- size: `7708`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, void *Buf1, MSG *lpMsg)`
- caller_count: `0`
- callee_count: `84`
- tags: `installer_update`

## callees

- `0x1800115f0`
- `0x180017a0c`
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
- `0x1800197bc`
- `0x180023a58`
- `0x180023b9c`
- `0x180023c98`
- `0x18002405c`
- `0x180025afc`
- `0x180025d1c`
- `0x1800260b8`
- `0x18002613c`
- `0x180026230`
- `0x180026364`
- `0x1800263e8`
- `0x1800264a0`
- `0x180026628`
- `0x180026820`
- `0x180026a14`
- `0x180026b08`
- `0x180026cc4`
- `0x180026f00`
- `0x180026f30`
- `0x180026ff0`
- `0x1800270a8`
- `0x180027220`
- `0x1800272fc`
- `0x18002743c`
- `0x180027784`
- `0x1800278c4`
- `0x1800279d0`
- `0x180027b80`
- `0x180027cbc`
- `0x180027e40`
- `0x180027f8c`
- `0x1800280b4`
- `0x1800282dc`
- `0x18002851c`
- `0x180028594`
- `0x180028800`
- `0x180028e1c`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x18002c529`
- `GDI32!GetDeviceCaps` at `0x18002c529`
- `KERNEL32!LocalFree` at `0x18002abfc`
- `KERNEL32!LocalFree` at `0x18002bb21`
- `KERNEL32!LocalFree` at `0x18002bb84`
- `KERNEL32!LocalFree` at `0x18002abfc`
- `KERNEL32!LocalFree` at `0x18002bb21`
- `KERNEL32!LocalFree` at `0x18002bb84`
- `KERNEL32!lstrlenW` at `0x18002bef5`
- `KERNEL32!lstrlenW` at `0x18002bf4d`
- `KERNEL32!lstrlenW` at `0x18002c4f1`
- `KERNEL32!lstrlenW` at `0x18002bef5`
- `KERNEL32!lstrlenW` at `0x18002bf4d`
- `KERNEL32!lstrlenW` at `0x18002c4f1`
- `KERNEL32!LocalAlloc` at `0x18002ab16`
- `KERNEL32!LocalAlloc` at `0x18002bad0`
- `KERNEL32!LocalAlloc` at `0x18002ab16`
- `KERNEL32!LocalAlloc` at `0x18002bad0`
- `KERNEL32!WideCharToMultiByte` at `0x18002bf83`
- `KERNEL32!WideCharToMultiByte` at `0x18002c481`
- `KERNEL32!WideCharToMultiByte` at `0x18002c4ab`
- `KERNEL32!WideCharToMultiByte` at `0x18002bf83`
- `KERNEL32!WideCharToMultiByte` at `0x18002c481`
- `KERNEL32!WideCharToMultiByte` at `0x18002c4ab`
- `KERNEL32!MultiByteToWideChar` at `0x18002baf2`
- `KERNEL32!MultiByteToWideChar` at `0x18002bdf2`
- `KERNEL32!MultiByteToWideChar` at `0x18002baf2`
- `KERNEL32!MultiByteToWideChar` at `0x18002bdf2`
- `USER32!GetParent` at `0x18002b380`
- `USER32!GetParent` at `0x18002b380`
- `USER32!SetWindowPos` at `0x18002bcc4`
- `USER32!SetWindowPos` at `0x18002bcc4`
- `USER32!GetDC` at `0x18002c518`
- `USER32!GetDC` at `0x18002c518`
- `USER32!ReleaseDC` at `0x18002b44b`
- `USER32!ReleaseDC` at `0x18002c53b`
- `USER32!ReleaseDC` at `0x18002b44b`
- `USER32!ReleaseDC` at `0x18002c53b`
- `USER32!GetSystemMetrics` at `0x18002ab76`
- `USER32!GetSystemMetrics` at `0x18002aef8`
- `USER32!GetSystemMetrics` at `0x18002ab76`
- `USER32!GetSystemMetrics` at `0x18002aef8`
- `USER32!MapWindowPoints` at `0x18002b40c`
- `USER32!MapWindowPoints` at `0x18002b40c`
- `USER32!SetCapture` at `0x18002b718`
- `USER32!SetCapture` at `0x18002b718`
- `USER32!IsWindow` at `0x18002b742`
- `USER32!IsWindow` at `0x18002b742`
- `USER32!TranslateMessage` at `0x18002c732`
- `USER32!TranslateMessage` at `0x18002c732`
- `USER32!DispatchMessageW` at `0x18002c73b`
- `USER32!DispatchMessageW` at `0x18002c73b`
- `USER32!GetCapture` at `0x18002b684`
- `USER32!GetCapture` at `0x18002b684`
- `USER32!SendMessageW` at `0x18002aee8`
- `USER32!SendMessageW` at `0x18002afae`
- `USER32!SendMessageW` at `0x18002aee8`
- `USER32!SendMessageW` at `0x18002afae`
- `USER32!RedrawWindow` at `0x18002ae14`
- `USER32!RedrawWindow` at `0x18002b0e3`
- `USER32!RedrawWindow` at `0x18002ae14`
- `USER32!RedrawWindow` at `0x18002b0e3`
- `USER32!SetWindowLongW` at `0x18002ac34`
- `USER32!SetWindowLongW` at `0x18002ac34`
- `USER32!SetWindowLongPtrW` at `0x18002ac11`
- `USER32!SetWindowLongPtrW` at `0x18002ac11`
- `USER32!GetFocus` at `0x18002c670`
- `USER32!GetFocus` at `0x18002c670`
- `USER32!InvalidateRect` at `0x18002af14`
- `USER32!InvalidateRect` at `0x18002b314`
- `USER32!InvalidateRect` at `0x18002b8d3`
- `USER32!InvalidateRect` at `0x18002bcd2`
- `USER32!InvalidateRect` at `0x18002c555`
- `USER32!InvalidateRect` at `0x18002c593`
- `USER32!InvalidateRect` at `0x18002c79c`
- `USER32!InvalidateRect` at `0x18002af14`
- `USER32!InvalidateRect` at `0x18002b314`
- `USER32!InvalidateRect` at `0x18002b8d3`
- `USER32!InvalidateRect` at `0x18002bcd2`
- `USER32!InvalidateRect` at `0x18002c555`
- `USER32!InvalidateRect` at `0x18002c593`
- `USER32!InvalidateRect` at `0x18002c79c`
- `USER32!GetWindowLongPtrW` at `0x18002aae8`
- `USER32!GetWindowLongPtrW` at `0x18002aae8`
- `USER32!BeginPaint` at `0x18002b517`
- `USER32!BeginPaint` at `0x18002b517`
- `USER32!EndPaint` at `0x18002b524`
- `USER32!EndPaint` at `0x18002b524`
- `USER32!DefWindowProcW` at `0x18002adac`
- `USER32!DefWindowProcW` at `0x18002b043`
- `USER32!DefWindowProcW` at `0x18002b0ce`
- `USER32!DefWindowProcW` at `0x18002b129`
- `USER32!DefWindowProcW` at `0x18002adac`
- `USER32!DefWindowProcW` at `0x18002b043`
- `USER32!DefWindowProcW` at `0x18002b0ce`
- `USER32!DefWindowProcW` at `0x18002b129`
- `USER32!GetUpdateRect` at `0x18002b103`
- `USER32!GetUpdateRect` at `0x18002b103`
- `USER32!GetWindowDC` at `0x18002b3e7`
- `USER32!GetWindowDC` at `0x18002b3e7`
- `USER32!PostMessageW` at `0x18002b58a`
- `USER32!PostMessageW` at `0x18002b58a`
- `USER32!GetAsyncKeyState` at `0x18002b6ee`
- `USER32!GetAsyncKeyState` at `0x18002b6ee`
- `USER32!EnumChildWindows` at `0x18002b116`
- `USER32!EnumChildWindows` at `0x18002b116`
- `USER32!GetWindowRect` at `0x18002b3f7`
- `USER32!GetWindowRect` at `0x18002b3f7`

## pseudocode

```c
__int64 __fastcall ToolbarWndProc(HWND hWnd, UINT Msg, unsigned __int64 Buf1, MSG *lpMsg)
{
  UINT v4; // r12d
  LONG_PTR WindowLongPtrW; // rax
  __int64 v9; // rdx
  int v10; // r9d
  __int64 v11; // rbx
  __int64 v12; // rdi
  _DWORD *v13; // rax
  _DWORD *v14; // rdi
  int SystemMetrics; // eax
  int v16; // eax
  int v17; // eax
  __int64 result; // rax
  int v19; // r8d
  LONG v20; // r8d
  __int64 v21; // r14
  unsigned int v22; // r8d
  int v23; // r8d
  __int64 v24; // r8
  unsigned int v25; // ecx
  _BOOL8 v26; // rsi
  unsigned int v27; // ecx
  HWND v28; // rcx
  UINT v29; // edx
  HWND v30; // rcx
  int i; // r13d
  struct _IMAGELIST *v32; // rax
  COLORREF v33; // edx
  struct _IMAGELIST *v34; // rax
  COLORREF v35; // edx
  HWND v36; // rcx
  __int64 v37; // rdx
  int v38; // ecx
  _OWORD *v39; // rsi
  __int64 wParam_low; // r8
  int v42; // eax
  __int64 v43; // r15
  __int64 v44; // rdx
  _WORD *lParam; // rcx
  LPARAM v46; // rax
  HDC WindowDC; // rbx
  struct tagPAINTSTRUCT *p_Paint; // r8
  int v49; // edx
  int v50; // eax
  __int64 v51; // rcx
  int v52; // eax
  __int64 v53; // rbx
  __int64 v54; // rax
  int v55; // eax
  __int64 v56; // rdx
  int v57; // eax
  int v58; // eax
  int v59; // r11d
  __int64 v60; // r8
  char v61; // r9
  char v62; // al
  char v63; // al
  int v64; // r8d
  int v65; // edx
  int v66; // eax
  int v67; // eax
  __int64 v68; // r8
  MSG *v69; // r12
  int v70; // eax
  int cchWideChar; // r13d
  WCHAR *v72; // rax
  __int64 v73; // rdi
  void *v74; // rcx
  WCHAR *v75; // r14
  const WCHAR *v76; // rbx
  UINT v77; // eax
  UINT v78; // kr08_4
  int v79; // r12d
  __int16 v80; // edx^2
  LONG bottom; // eax
  int v82; // eax
  int v83; // edx
  __int64 v84; // rcx
  int v85; // ebx
  int v86; // ecx
  int v87; // edx
  int v88; // eax
  __int64 v89; // rax
  __int64 v90; // r8
  __int64 v91; // rdx
  __int64 v92; // rdx
  HWND v93; // rcx
  __int64 DragProxy; // rax
  HIMAGELIST *v95; // rax
  int ImageCount; // ebx
  int hwnd_high; // r13d
  int ButtonInfo; // eax
  __int64 v99; // r8
  const WCHAR *v100; // r8
  int v101; // eax
  int v102; // eax
  int v103; // eax
  const WCHAR *v104; // rax
  const WCHAR *v105; // rbx
  int v106; // eax
  int v107; // edi
  int v108; // eax
  const WCHAR *v109; // rax
  const wchar_t *v110; // rbx
  unsigned int v111; // eax
  __int64 v112; // r11
  HDC DC; // rbx
  WPARAM wParam; // rax
  __int64 v115; // rcx
  int lpWideCharStr; // [rsp+20h] [rbp-89h]
  LONG lpWideCharStra; // [rsp+20h] [rbp-89h]
  WCHAR WideCharStr[2]; // [rsp+40h] [rbp-69h] BYREF
  CHAR MultiByteStr[8]; // [rsp+48h] [rbp-61h] BYREF
  struct tagRECT Rect; // [rsp+50h] [rbp-59h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+60h] [rbp-49h] BYREF

  v4 = Msg;
  *(_DWORD *)WideCharStr = Msg;
  WindowLongPtrW = GetWindowLongPtrW(hWnd, 0);
  v11 = 1;
  v12 = WindowLongPtrW;
  if ( v4 == 129 )
  {
    CCCreateWindow();
    InitDitherBrush();
    v13 = LocalAlloc(0x40u, 0x158u);
    v14 = v13;
    if ( !v13 )
      return 0;
    CIInitialize(v13, hWnd, lpMsg);
    v14[79] |= 0x20000u;
    v14[71] = -1;
    v14[72] = -1;
    v14[73] = -1;
    v14[74] = -16777216;
    v14[53] = 0;
    InitGlobalColors();
    SystemMetrics = GetSystemMetrics(72);
    v14[79] |= 0x8040u;
    v14[52] = SystemMetrics;
    v16 = 2 * g_cxEdge;
    v14[54] = 7;
    v14[56] = v16;
    v14[57] = v16;
    v17 = v14[4];
    v14[55] = 6;
    v14[66] = -16777216;
    v14[65] = -16777216;
    v14[41] = 1;
    if ( (v17 & 0x800) != 0 )
      v14[4] = v17 | 0x8000;
    TBChangeFont((__int64)v14, 0, 0);
    if ( !(unsigned int)SetBitmapSize(v14, 16, 16) )
    {
      LocalFree(v14);
      return 0;
    }
    SetWindowLongPtrW(hWnd, 0, (LONG_PTR)v14);
    v19 = v14[4];
    if ( (v19 & 3) == 0 )
    {
      v20 = v19 | 1;
      v14[4] = v20;
      SetWindowLongW(hWnd, -16, v20);
    }
    return v11;
  }
  v21 = 0;
  if ( !WindowLongPtrW )
    return DefWindowProcW(hWnd, v4, Buf1, (LPARAM)lpMsg);
  if ( v4 > 0x420 )
  {
    if ( v4 <= 0x900 )
    {
      if ( v4 == 2304 )
      {
        if ( *(_QWORD *)(WindowLongPtrW + 88) )
        {
          TBOnMouseMove(WindowLongPtrW, hWnd, 512, 0, -1);
          *(_QWORD *)(v12 + 88) = 0;
        }
        return 0;
      }
      v77 = v4 - 1057;
      v78 = v4;
      v79 = -1;
      switch ( v77 )
      {
        case 0u:
          goto LABEL_35;
        case 1u:
        case 0x40u:
          v4 = *(_DWORD *)WideCharStr;
          goto LABEL_444;
        case 2u:
          TB_ForceCreateTooltips(v12);
          return *(_QWORD *)(v12 + 104);
        case 3u:
          *(_QWORD *)(v12 + 104) = Buf1;
          return 0;
        case 4u:
          result = *(_QWORD *)(v12 + 8);
          *(_QWORD *)(v12 + 8) = Buf1;
          return result;
        case 5u:
          goto LABEL_315;
        case 6u:
          Rect = 0;
          if ( (unsigned int)BoxIt(v12, (unsigned __int16)Buf1, WORD1(Buf1), &Rect) )
          {
            bottom = Rect.bottom;
            *(_DWORD *)(v12 + 316) &= ~0x10000u;
            *(_DWORD *)(v12 + 316) |= 0x10u;
            lpWideCharStra = Rect.right;
            *(_DWORD *)(v12 + 232) = -1;
            *(_DWORD *)(v12 + 236) = -1;
            SetWindowPos(hWnd, 0, 0, 0, lpWideCharStra, bottom, 0x16u);
            InvalidateRect(hWnd, 0, 1);
          }
          if ( lpMsg )
            *(struct tagRECT *)&lpMsg->hwnd = Rect;
          return 0;
        case 7u:
          LODWORD(result) = CountRows(v12);
          return (int)result;
        case 8u:
          DC = GetDC(0);
          LOBYTE(v21) = GetDeviceCaps(DC, 90) >= 120;
          ReleaseDC(0, DC);
          return v21;
        case 9u:
          if ( Buf1 >= *(unsigned int *)(v12 + 200) )
            return 0;
          TB_OnSetCmdID(v12, *(_QWORD *)(v12 + 80) + 40 * Buf1, (unsigned int)lpMsg);
          return v11;
        case 0xAu:
          v101 = PositionFromID(v12, Buf1);
          if ( v101 < 0 )
            return 0;
          return TB_OnSetImage(v12, *(_QWORD *)(v12 + 80) + 40LL * v101, (unsigned __int16)lpMsg);
        case 0xBu:
          v102 = PositionFromID(v12, Buf1);
          if ( v102 < 0 )
            return 0;
          return *(int *)(*(_QWORD *)(v12 + 80) + 40LL * v102);
        case 0xCu:
          v103 = PositionFromID(v12, Buf1);
          if ( v103 < 0 )
            return -1;
          v104 = (const WCHAR *)TB_StrForButton(v12, *(_QWORD *)(v12 + 80) + 40LL * v103);
          v105 = v104;
          if ( !v104 )
            return -1;
          v106 = WideCharToMultiByte(0, 0, v104, -1, 0, 0, 0, 0);
          v107 = v106;
          if ( lpMsg )
            WideCharToMultiByte(0, 0, v105, -1, (LPSTR)lpMsg, v106, 0, 0);
          LODWORD(result) = v107 - 1;
          return (int)result;
        case 0xDu:
          MapToStandardBitmaps(lpMsg, &lpMsg->message, WideCharStr);
          MapToStandardBitmaps(&lpMsg->wParam, &lpMsg->lParam, &lpMsg->time);
          v83 = *(_DWORD *)(v12 + 136);
          if ( v83 <= 0 )
            return 0;
          v84 = *(_QWORD *)(v12 + 144);
          break;
        case 0xEu:
          *(_DWORD *)(v12 + 212) = Buf1;
          InvalidateRect(hWnd, 0, 1);
          *(_DWORD *)(v12 + 316) &= ~0x10000u;
          *(_DWORD *)(v12 + 316) |= 0x10u;
          goto LABEL_252;
        case 0xFu:
          v89 = TBSetImageList(v12, 0, (unsigned int)Buf1, lpMsg);
          *(_DWORD *)(v12 + 316) |= 2u;
          v11 = v89;
          if ( !*(_DWORD *)(v12 + 168) )
            *(_DWORD *)(v12 + 168) = 20;
          if ( !Buf1 )
          {
            *(_DWORD *)MultiByteStr = 0;
            v90 = 0;
            *(_DWORD *)WideCharStr = 0;
            if ( lpMsg )
            {
              ImageList_GetIconSize((HIMAGELIST)lpMsg, (int *)MultiByteStr, (int *)WideCharStr);
              v90 = *(unsigned int *)WideCharStr;
              LODWORD(v21) = *(_DWORD *)MultiByteStr;
            }
            SetBitmapSize(v12, (unsigned int)v21, v90);
          }
          return v11;
        case 0x10u:
          v91 = 0;
          return TBGetImageList(v12, v91);
        case 0x11u:
          *(_QWORD *)MultiByteStr = lpMsg;
          *(_QWORD *)&Rect.left = Buf1;
          *(_DWORD *)WideCharStr = 0;
          HIDWORD(Paint.hdc) = 0;
          MapToStandardBitmaps(MultiByteStr, &Rect, WideCharStr);
          *(_QWORD *)&Paint.rcPaint.top = *(_QWORD *)&Rect.left;
          LODWORD(Paint.hdc) = *(_DWORD *)WideCharStr;
          *(_QWORD *)&Paint.fErase = *(_QWORD *)MultiByteStr;
          if ( *(int *)(v12 + 280) > 0 && (v95 = *(HIMAGELIST **)(v12 + 272), *v95) )
            ImageCount = ImageList_GetImageCount(*v95);
          else
            ImageCount = 0;
          if ( (unsigned int)TBAddBitmapToImageList(v12, (__int64)&Paint) )
          {
            *(_DWORD *)(v12 + 316) |= 2u;
            return ImageCount;
          }
          return v79;
        case 0x12u:
          LODWORD(Buf1) = PositionFromID(v12, Buf1);
          goto LABEL_363;
        case 0x13u:
          v92 = 1;
          return TBSetImageList(v12, v92, (unsigned int)Buf1, lpMsg);
        case 0x14u:
          v91 = 1;
          return TBGetImageList(v12, v91);
        case 0x15u:
          v92 = 2;
          return TBSetImageList(v12, v92, (unsigned int)Buf1, lpMsg);
        case 0x16u:
          v91 = 2;
          return TBGetImageList(v12, v91);
        case 0x17u:
          v37 = (unsigned int)lpMsg;
          goto LABEL_305;
        case 0x18u:
          return *(unsigned int *)(v12 + 16);
        case 0x19u:
          LODWORD(result) = (*(unsigned __int16 *)(v12 + 184) << 16) | *(unsigned __int16 *)(v12 + 180);
          return (int)result;
        case 0x1Au:
          if ( *(_QWORD *)(v12 + 188) == __PAIR64__(WORD1(lpMsg), (unsigned __int16)lpMsg) )
            return v11;
          *(_DWORD *)(v12 + 192) = WORD1(lpMsg);
          *(_DWORD *)(v12 + 188) = (unsigned __int16)lpMsg;
          *(_DWORD *)(v12 + 180) = 0;
          goto LABEL_420;
        case 0x1Bu:
          if ( *(_DWORD *)(v12 + 164) == (_DWORD)Buf1 )
            return v11;
          *(_DWORD *)(v12 + 164) = Buf1;
LABEL_420:
          TBRecalc(v12);
          v36 = hWnd;
          goto LABEL_421;
        case 0x1Cu:
          return *(int *)(v12 + 164);
        case 0x1Du:
          if ( !memcmp((const void *)Buf1, &IID_IDropTarget, 0x10u) )
          {
            v93 = *(HWND *)(v12 + 240);
            if ( v93
              || (DragProxy = CreateDragProxy(*(_QWORD *)v12, &ToolbarDragCallback, 0),
                  *(_QWORD *)(v12 + 240) = DragProxy,
                  (v93 = (HWND)DragProxy) != 0) )
            {
              lpMsg->hwnd = v93;
              (*(void (__fastcall **)(HWND))(*(_QWORD *)v93 + 8LL))(v93);
              return 0;
            }
          }
          return -2147467259;
        case 0x1Eu:
          return TB_OnGetButtonInfo(v12, (unsigned int)Buf1, lpMsg);
        case 0x1Fu:
          return TB_OnSetButtonInfo(v12, (unsigned int)Buf1, lpMsg);
        case 0x20u:
          hwnd_high = HIDWORD(lpMsg->hwnd);
          HIDWORD(lpMsg->hwnd) = hwnd_high & 0xFFFFFFFD;
          ButtonInfo = TB_OnGetButtonInfo(v12, (unsigned int)Buf1, lpMsg);
          v85 = ButtonInfo;
          if ( ButtonInfo != -1 )
          {
            v99 = *(_QWORD *)(v12 + 80);
            HIDWORD(lpMsg->hwnd) = hwnd_high;
            if ( (hwnd_high & 2) != 0 )
            {
              v100 = *(const WCHAR **)(v99 + 40LL * ButtonInfo + 24);
              if ( v100 == (const WCHAR *)-1LL || (unsigned __int64)v100 < 0x10000 )
                **(_BYTE **)&lpMsg->time = 0;
              else
                WideCharToMultiByte(0, 0, v100, -1, *(LPSTR *)&lpMsg->time, lpMsg->pt.y, 0, 0);
            }
          }
          return v85;
        case 0x21u:
          return TB_OnSetButtonInfoA(v12, (unsigned int)Buf1, lpMsg);
        case 0x22u:
          lpWideCharStr = 1;
          goto LABEL_338;
        case 0x23u:
          lpWideCharStr = 1;
          goto LABEL_246;
        case 0x24u:
          LODWORD(result) = TBHitTest(v12, LODWORD(lpMsg->hwnd), HIDWORD(lpMsg->hwnd));
          return (int)result;
        case 0x25u:
          result = *(unsigned int *)(v12 + 248);
          *(_DWORD *)(v12 + 248) = Buf1 & (unsigned int)lpMsg;
          *(_DWORD *)(v12 + 252) = Buf1;
          return result;
        case 0x26u:
          return *(int *)(v12 + 284);
        case 0x27u:
          LODWORD(lpMsg) = 0;
          goto LABEL_343;
        case 0x28u:
          result = ((unsigned __int64)*(unsigned int *)(v12 + 316) >> 7) & 1;
          *(_DWORD *)(v12 + 316) = *(_DWORD *)(v12 + 316) & 0xFFFFFF7F | (Buf1 != 0 ? 0x80 : 0);
          return result;
        case 0x29u:
          return ((unsigned __int64)*(unsigned int *)(v12 + 316) >> 7) & 1;
        case 0x2Au:
          v108 = PositionFromID(v12, Buf1);
          if ( v108 < 0 )
            return -1;
          v109 = (const WCHAR *)TB_StrForButton(v12, *(_QWORD *)(v12 + 80) + 40LL * v108);
          v110 = v109;
          if ( !v109 )
            return -1;
          v111 = lstrlenW(v109);
          v112 = v111;
          if ( lpMsg )
            StringCchCopyW((STRSAFE_LPWSTR)lpMsg, v111 + 1, v110);
          return v112;
        case 0x2Bu:
          LODWORD(result) = SaveRestoreFromReg(
                              v12,
                              Buf1,
                              (HKEY)lpMsg->hwnd,
                              *(const WCHAR **)&lpMsg->message,
                              (const WCHAR *)lpMsg->wParam);
          return (int)result;
        case 0x2Cu:
          LODWORD(result) = TBAddStrings(v12, Buf1, lpMsg);
          return (int)result;
        case 0x2Du:
          MultiByteStr[0] = Buf1;
          MultiByteStr[1] = 0;
          MultiByteToWideChar(0, 0, MultiByteStr, 2, WideCharStr, 2);
          LODWORD(Buf1) = WideCharStr[0];
          goto LABEL_313;
        case 0x2Eu:
          LODWORD(lpMsg->hwnd) = *(_DWORD *)(v12 + 292);
          HIDWORD(lpMsg->hwnd) = (*(_DWORD *)(v12 + 316) >> 10) & 1;
          return v11;
        case 0x2Fu:
          v86 = *(_DWORD *)(v12 + 292);
          if ( LODWORD(lpMsg->hwnd) != v86
            || ((BYTE4(lpMsg->hwnd) ^ (unsigned __int8)(*(_DWORD *)(v12 + 316) >> 10)) & 1) != 0 )
          {
            if ( v86 != -1 )
              TBInvalidateMark(v12);
            v87 = (int)lpMsg->hwnd;
            v88 = *(_DWORD *)(v12 + 316);
            *(_DWORD *)(v12 + 292) = lpMsg->hwnd;
            *(_DWORD *)(v12 + 316) = v88
                                   ^ ((unsigned __int16)v88
                                    ^ (unsigned __int16)((unsigned __int16)HIDWORD(lpMsg->hwnd) << 10))
                                   & 0x400;
            if ( v87 != -1 )
              TBInvalidateMark(v12);
          }
          return 0;
        case 0x30u:
          LODWORD(result) = TBInsertMarkHitTest(v12, *(unsigned int *)Buf1, *(unsigned int *)(Buf1 + 4), lpMsg);
          return (int)result;
        case 0x31u:
          LODWORD(result) = TBMoveButton(v12, (unsigned int)Buf1, (unsigned int)lpMsg);
          return (int)result;
        case 0x32u:
          LODWORD(result) = TBGetMaxSize(v12, lpMsg);
          return (int)result;
        case 0x33u:
          v11 = *(unsigned int *)(v12 + 56);
          TBSetStyleEx(v12, (unsigned int)lpMsg, (unsigned int)Buf1);
          return v11;
        case 0x34u:
          return *(unsigned int *)(v12 + 56);
        case 0x35u:
          LOWORD(lpMsg) = -1;
          v80 = -1;
          goto LABEL_295;
        case 0x36u:
          v80 = WORD1(lpMsg);
LABEL_295:
          result = (*(unsigned __int16 *)(v12 + 220) << 16) | *(unsigned __int16 *)(v12 + 216);
          if ( (__int16)lpMsg != -1 )
            *(_DWORD *)(v12 + 216) = (__int16)lpMsg;
          if ( v80 != -1 )
            *(_DWORD *)(v12 + 220) = v80;
          return result;
        case 0x37u:
          result = *(unsigned int *)(v12 + 296);
          *(_DWORD *)(v12 + 296) = (_DWORD)lpMsg;
          if ( (_DWORD)result == -16777216 )
            return g_clrBtnText;
          return result;
        case 0x38u:
          result = *(unsigned int *)(v12 + 296);
          if ( (_DWORD)result == -16777216 )
            return g_clrBtnText;
          return result;
        case 0x39u:
LABEL_313:
          *(_DWORD *)WideCharStr = 0;
          v82 = TBItemFromAccelerator(v12, (unsigned int)Buf1, WideCharStr);
          if ( v82 == -1 )
            return 0;
          LODWORD(lpMsg->hwnd) = *(_DWORD *)(*(_QWORD *)(v12 + 80) + 40LL * v82 + 4);
          return v11;
        case 0x3Au:
          if ( lpMsg )
            LOWORD(lpMsg->hwnd) = 0;
          if ( WORD1(Buf1) < *(int *)(v12 + 160) )
          {
            v79 = lstrlenW(*(LPCWSTR *)(*(_QWORD *)(v12 + 152) + 8LL * WORD1(Buf1)));
            if ( lpMsg )
              StringCchCopyW(
                (STRSAFE_LPWSTR)lpMsg,
                (unsigned __int16)Buf1,
                *(STRSAFE_LPCWSTR *)(*(_QWORD *)(v12 + 152) + 8LL * WORD1(Buf1)));
          }
          return v79;
        case 0x3Bu:
          v85 = -1;
          if ( lpMsg )
            LOBYTE(lpMsg->hwnd) = 0;
          if ( WORD1(Buf1) < *(int *)(v12 + 160) )
          {
            v85 = lstrlenW(*(LPCWSTR *)(*(_QWORD *)(v12 + 152) + 8LL * WORD1(Buf1)));
            if ( lpMsg )
              WideCharToMultiByte(
                0,
                0,
                *(LPCWCH *)(*(_QWORD *)(v12 + 152) + 8LL * WORD1(Buf1)),
                -1,
                (LPSTR)lpMsg,
                (unsigned __int16)Buf1,
                0,
                0);
          }
          return v85;
        case 0x3Cu:
          *(_QWORD *)(v12 + 336) = lpMsg->hwnd;
          return 0;
        case 0x3Du:
LABEL_343:
          v11 = *(int *)(v12 + 284);
          TBSetHotItem(v12, (unsigned int)Buf1, (unsigned int)lpMsg);
          return v11;
        case 0x3Eu:
          LODWORD(lpMsg->hwnd) = TBHasAccelerator(v12, (unsigned int)Buf1);
          return 0;
        case 0x3Fu:
          *(_DWORD *)(v12 + 224) = Buf1;
          goto LABEL_69;
        case 0x41u:
          return *(int *)(v12 + 280);
        case 0x42u:
          memset(&Paint, 0, 24);
          *(_DWORD *)Paint.rgbReserved = 0;
          Paint.rcPaint.bottom = (Buf1 != 0) + 1;
          Paint.fRestore = (BOOL)lpMsg->hwnd;
          Paint.fIncUpdate = HIDWORD(lpMsg->hwnd);
          TB_OnCalcSize(v12, &Paint);
          HIDWORD(lpMsg->hwnd) = Paint.fIncUpdate;
          LODWORD(lpMsg->hwnd) = Paint.fRestore;
          return v11;
        case 0x43u:
          *(_DWORD *)(v12 + 228) = Buf1;
          goto LABEL_69;
        default:
          v4 = v78;
          goto LABEL_444;
      }
      while ( *(HWND *)(v84 + 8) != lpMsg->hwnd || *(_QWORD *)(v84 + 16) != *(_QWORD *)&lpMsg->message )
      {
        --v83;
        v84 += 24;
        if ( v83 <= 0 )
          return 0;
      }
      *(_QWORD *)(v84 + 8) = lpMsg->wParam;
      *(_QWORD *)(v84 + 16) = lpMsg->lParam;
      *(_DWORD *)v84 = lpMsg->time;
      *(_DWORD *)(v12 + 316) &= ~1u;
      return v11;
    }
    if ( v4 == 8194 )
    {
      if ( lpMsg )
      {
        if ( LODWORD(lpMsg->hwnd) == 12 )
        {
          *(_DWORD *)(WindowLongPtrW + 260) = HIDWORD(lpMsg->hwnd);
          *(_DWORD *)(WindowLongPtrW + 264) = lpMsg->message;
          InvalidateRect(hWnd, 0, 0);
          if ( (*(_DWORD *)(v12 + 16) & 0x800000) != 0 )
            CCInvalidateFrame(hWnd);
        }
      }
      return 0;
    }
    if ( v4 != 8195 )
    {
      if ( v4 != 8202 )
        goto LABEL_444;
      if ( lpMsg && GetFocus() == hWnd )
      {
        if ( lpMsg->message == 256 || lpMsg->message == 257 )
        {
          if ( lpMsg->wParam != 13
            && lpMsg->wParam != 27
            && lpMsg->wParam != 32
            && lpMsg->wParam != 37
            && lpMsg->wParam != 38
            && lpMsg->wParam - 39 > 1 )
          {
            return v21;
          }
        }
        else
        {
          if ( lpMsg->message != 258 )
            return v21;
          wParam = lpMsg->wParam;
          if ( wParam > 0x20 )
            return v21;
          v115 = 0x108002000LL;
          if ( !_bittest64(&v115, wParam) )
            return v21;
        }
        TranslateMessage(lpMsg);
        DispatchMessageW(lpMsg);
        return 1;
      }
      return v21;
    }
    if ( lpMsg && LODWORD(lpMsg->hwnd) == 12 )
    {
      lpMsg->hwnd = *(HWND *)(WindowLongPtrW + 256);
      lpMsg->message = *(_DWORD *)(WindowLongPtrW + 264);
    }
    return (__int64)lpMsg;
  }
  if ( v4 == 1056 )
  {
    LODWORD(result) = SetBitmapSize(WindowLongPtrW, (unsigned int)(__int16)lpMsg, (unsigned int)SWORD1(lpMsg));
    return (int)result;
  }
  if ( v4 > 0x201 )
  {
    if ( v4 <= 0x40C )
    {
      if ( v4 != 1036 )
      {
        if ( v4 <= 0x401 )
        {
          if ( v4 != 1025 )
          {
            if ( v4 == 514 )
            {
              TBOnLButtonUp(WindowLongPtrW, hWnd, 514, Buf1, lpMsg);
              return 0;
            }
            if ( v4 != 515 )
            {
              switch ( v4 )
              {
                case 0x204u:
                  if ( *(_QWORD *)(WindowLongPtrW + 88) && hWnd == GetCapture() )
                  {
                    if ( !(unsigned int)CCReleaseCapture(v12) )
                      return 0;
                    TBOnMouseMove(v12, hWnd, 512, 0, -1);
                  }
                  v52 = TBHitTest(v12, (unsigned int)(__int16)lpMsg, (unsigned int)SWORD1(lpMsg));
                  v53 = v52;
                  if ( v52 >= 0 && v52 < *(_DWORD *)(v12 + 200) && GetAsyncKeyState(2) < 0 )
                  {
                    v54 = *(_QWORD *)(v12 + 80);
                    *(_DWORD *)(v12 + 316) |= 0x100u;
                    *(_QWORD *)(v12 + 88) = v54 + 40 * v53;
                    SetCapture(hWnd);
                    GetMessagePosClient(*(HWND *)v12, (LPPOINT)(v12 + 96));
                    SendItemNotify(v12, *(unsigned int *)(*(_QWORD *)(v12 + 88) + 4LL), 4294966595LL);
                    if ( IsWindow(hWnd) )
                      *(_DWORD *)(v12 + 316) &= ~0x200u;
                  }
                  return 0;
                case 0x205u:
                  memset(&Paint, 0, 56);
                  if ( *(_QWORD *)(WindowLongPtrW + 88) )
                  {
                    if ( !(unsigned int)CCReleaseCapture(WindowLongPtrW) )
                      return 0;
                    *(_DWORD *)(v12 + 316) &= ~0x100u;
                    *(_QWORD *)(v12 + 88) = 0;
                  }
                  v50 = TBHitTest(v12, (unsigned int)(__int16)lpMsg, (unsigned int)SWORD1(lpMsg));
                  if ( v50 < 0 || v50 >= *(_DWORD *)(v12 + 200) )
                  {
                    *(_QWORD *)&Paint.rcPaint.bottom = -1;
                    v4 = *(_DWORD *)WideCharStr;
                  }
                  else
                  {
                    v51 = *(_QWORD *)(v12 + 80);
                    *(_QWORD *)&Paint.rcPaint.bottom = *(int *)(v51 + 40LL * v50 + 4);
                    *(_QWORD *)&Paint.fIncUpdate = *(_QWORD *)(v51 + 40LL * v50 + 16);
                  }
                  p_Paint = &Paint;
                  *(_DWORD *)&Paint.rgbReserved[4] = (unsigned __int16)lpMsg;
                  v49 = -5;
                  *(_DWORD *)&Paint.rgbReserved[8] = WORD1(lpMsg);
                  break;
                case 0x206u:
                  p_Paint = 0;
                  v49 = -6;
                  break;
                case 0x215u:
                  if ( *(__int64 *)(WindowLongPtrW + 40) < 5 )
                  {
                    if ( (*(_DWORD *)(WindowLongPtrW + 316) & 0x100) != 0 && *(_QWORD *)(WindowLongPtrW + 88) )
                    {
                      CCReleaseCapture(WindowLongPtrW);
                      *(_DWORD *)(v12 + 316) &= ~0x100u;
                    }
                  }
                  else
                  {
                    PostMessageW(hWnd, 0x900u, 0, 0);
                  }
                  return 0;
                case 0x2A3u:
                  *(_QWORD *)&Paint.rcPaint.top = 0;
                  Paint.hdc = (HDC)0x8000000200000018LL;
                  *(_QWORD *)&Paint.fErase = hWnd;
                  TrackMouseEvent((LPTRACKMOUSEEVENT)&Paint);
                  *(_DWORD *)(v12 + 316) &= ~0x20u;
                  v24 = 1;
                  goto LABEL_31;
                case 0x318u:
                  goto LABEL_174;
                default:
                  goto LABEL_444;
              }
              if ( CCSendNotify(v12, v49, (LPARAM)p_Paint) )
                return 0;
              return DefWindowProcW(hWnd, v4, Buf1, (LPARAM)lpMsg);
            }
            v55 = TBHitTest(WindowLongPtrW, (unsigned int)(__int16)lpMsg, (unsigned int)SWORD1(lpMsg));
            if ( v55 >= 0 || (*(_BYTE *)(v12 + 16) & 0x20) == 0 )
            {
              TBHandleLButtonDown(v12, lpMsg, (unsigned int)v55);
              return 0;
            }
            v56 = (unsigned int)~v55;
LABEL_280:
            CustomizeTB(v12, v56);
            return 0;
          }
LABEL_221:
          v58 = PositionFromID(WindowLongPtrW, Buf1);
          *(_DWORD *)WideCharStr = v58;
          if ( v58 < 0 )
            return 0;
          v60 = *(_QWORD *)(v12 + 80) + 40LL * v58;
          v61 = *(_BYTE *)(v60 + 8);
          *(_QWORD *)&Rect.left = v60;
          v62 = wStateMasks[v4 - 1025];
          if ( (_WORD)lpMsg )
            v63 = v61 | v62;
          else
            v63 = v61 & ~v62;
          *(_BYTE *)(v60 + 8) = v63;
          if ( v61 == v63 )
            return v11;
          if ( v4 == v59 )
          {
            if ( (*(_BYTE *)(v60 + 9) & 4) != 0 )
              MakeGroupConsistant(v12, (unsigned int)Buf1);
          }
          else if ( v4 == 1028 )
          {
            InvalidateRect(hWnd, 0, 1);
            *(_DWORD *)(v12 + 316) &= ~0x10000u;
            *(_DWORD *)(v12 + 316) |= 0x10u;
            *(_DWORD *)(v12 + 232) = -1;
            *(_DWORD *)(v12 + 236) = -1;
            goto LABEL_230;
          }
          InvalidateButton(v12, *(_QWORD *)&Rect.left, 1);
LABEL_230:
          MyNotifyWinEvent(32778, hWnd, 4294967292LL);
          return v11;
        }
        if ( v4 == 1026 || v4 == 1027 || v4 == 1028 || v4 == 1029 || v4 == 1030 )
          goto LABEL_221;
        if ( v4 != 1033 && v4 - 1034 > 1 )
          goto LABEL_444;
      }
      goto LABEL_219;
    }
    if ( v4 <= 0x417 )
    {
      switch ( v4 )
      {
        case 0x417u:
          if ( Buf1 >= *(unsigned int *)(WindowLongPtrW + 200) )
            return 0;
          TBOutputStruct(WindowLongPtrW, *(_QWORD *)(WindowLongPtrW + 80) + 40 * Buf1, lpMsg);
          return v11;
        case 0x40Du:
        case 0x40Eu:
LABEL_219:
          v57 = PositionFromID(WindowLongPtrW, Buf1);
          if ( v57 >= 0 )
            return (unsigned int)wStateMasks[v4 - 1033]
                 & (unsigned __int64)*(unsigned __int8 *)(*(_QWORD *)(v12 + 80) + 40LL * v57 + 8);
          return -1;
        case 0x411u:
          v67 = PositionFromID(WindowLongPtrW, Buf1);
          if ( v67 < 0 )
            return 0;
          LOBYTE(v68) = (_BYTE)lpMsg;
          TB_OnSetState(v12, *(_QWORD *)(v12 + 80) + 40LL * v67, v68, (unsigned int)v67);
          *(_DWORD *)(v12 + 316) &= ~0x10000u;
          *(_DWORD *)(v12 + 316) |= 0x10u;
LABEL_252:
          *(_DWORD *)(v12 + 232) = -1;
          *(_DWORD *)(v12 + 236) = -1;
          return v11;
        case 0x412u:
          v66 = PositionFromID(WindowLongPtrW, Buf1);
          if ( v66 >= 0 )
            return *(unsigned __int8 *)(*(_QWORD *)(v12 + 80) + 40LL * v66 + 8);
          return -1;
        case 0x413u:
LABEL_315:
          LODWORD(result) = AddBitmap(v12, (unsigned int)Buf1, lpMsg->hwnd, *(_QWORD *)&lpMsg->message);
          return (int)result;
        case 0x414u:
          lpWideCharStr = 0;
LABEL_246:
          v64 = Buf1;
          v65 = -1;
          break;
        case 0x415u:
          lpWideCharStr = 0;
LABEL_338:
          v65 = Buf1;
          v64 = 1;
          break;
        case 0x416u:
          LODWORD(result) = DeleteButton(WindowLongPtrW, (unsigned int)Buf1);
          return (int)result;
        default:
          goto LABEL_444;
      }
      LODWORD(result) = TBInsertButtons(v12, v65, v64, (_DWORD)lpMsg, lpWideCharStr);
      return (int)result;
    }
    if ( v4 == 1048 )
      return *(int *)(WindowLongPtrW + 200);
    if ( v4 == 1049 )
    {
      LODWORD(result) = PositionFromID(WindowLongPtrW, Buf1);
      return (int)result;
    }
    if ( v4 == 1050 )
    {
      v75 = (WCHAR *)ProduceWFromA(0, *(LPCCH *)&lpMsg->message);
      v76 = (const WCHAR *)ProduceWFromA(0, (LPCCH)lpMsg->wParam);
      v73 = (int)SaveRestoreFromReg(v12, Buf1, (HKEY)lpMsg->hwnd, v75, v76);
      if ( (unsigned __int64)v75 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        LocalFree(v75);
      if ( (unsigned __int64)v76 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
        return v73;
      v74 = (void *)v76;
    }
    else
    {
      if ( v4 == 1051 )
      {
        v56 = *(unsigned int *)(WindowLongPtrW + 200);
        goto LABEL_280;
      }
      if ( v4 != 1052 )
      {
        if ( v4 == 1053 )
        {
LABEL_363:
          if ( !lpMsg )
            return 0;
          LODWORD(result) = TB_GetItemRect(v12, (unsigned int)Buf1, lpMsg);
        }
        else
        {
          if ( v4 == 1054 )
          {
            if ( !*(_DWORD *)(WindowLongPtrW + 200) )
              *(_DWORD *)(WindowLongPtrW + 168) = Buf1;
            return 0;
          }
          LODWORD(result) = (unsigned int)GrowToolbar(WindowLongPtrW, (__int16)lpMsg, SWORD1(lpMsg), 0);
        }
        return (int)result;
      }
      v69 = lpMsg;
      if ( Buf1 || (unsigned __int64)lpMsg < 0x10000 )
      {
        LODWORD(v11) = 0;
      }
      else
      {
        v70 = 0;
        while ( 1 )
        {
          ++v70;
          if ( !LOBYTE(v69->hwnd) && !BYTE1(v69->hwnd) )
            break;
          v69 = (MSG *)((char *)v69 + 1);
        }
        cchWideChar = v70 + 1;
        v72 = (WCHAR *)LocalAlloc(0x40u, 2LL * (unsigned int)(v70 + 1));
        v69 = (MSG *)v72;
        if ( !v72 )
          return -1;
        MultiByteToWideChar(0, 0, (LPCCH)lpMsg, cchWideChar, v72, cchWideChar);
      }
      v73 = (int)TBAddStrings(v12, Buf1, v69);
      if ( !(_DWORD)v11 )
        return v73;
      v74 = v69;
    }
    LocalFree(v74);
    return v73;
  }
  if ( v4 == 513 )
  {
    TBOnLButtonDown(WindowLongPtrW, v9, 513, Buf1, (__int64)lpMsg);
    return 0;
  }
  if ( v4 <= 0x30 )
  {
    if ( v4 == 48 )
    {
      TBChangeFont(WindowLongPtrW, 0, (HFONT)Buf1);
      if ( (_DWORD)lpMsg )
      {
        v36 = *(HWND *)v12;
LABEL_421:
        InvalidateRect(v36, 0, 1);
      }
      return v11;
    }
    if ( v4 <= 0xB )
    {
      if ( v4 != 11 )
      {
        switch ( v4 )
        {
          case 0u:
            return 0;
          case 1u:
            if ( (*(_DWORD *)(WindowLongPtrW + 16) & 0x4000) != 0 )
              *(_QWORD *)(WindowLongPtrW + 240) = CreateDragProxy(*(_QWORD *)WindowLongPtrW, &ToolbarDragCallback, 1);
            return DefWindowProcW(hWnd, v4, Buf1, (LPARAM)lpMsg);
          case 2u:
            _InterlockedAdd(&g_dwWindowCount, 0xFFFFFFFF);
            TB_OnDestroy((char *)WindowLongPtrW);
            return 0;
        }
        if ( v4 != 3 )
        {
          if ( v4 == 5 )
          {
            TB_OnSize(WindowLongPtrW, (unsigned __int16)lpMsg, WORD1(lpMsg));
LABEL_35:
            TBAutoSize(v12);
            return 0;
          }
          if ( v4 == 7 )
          {
            if ( *(_DWORD *)(WindowLongPtrW + 284) == -1 )
              TBCycleHotItem(WindowLongPtrW, 0xFFFFFFFFLL, 1, 0);
            return 0;
          }
          if ( v4 != 8 )
          {
            if ( v4 == 10 )
            {
              v22 = *(_DWORD *)(WindowLongPtrW + 16) & 0xF7FFFFFF;
              if ( !Buf1 )
                v22 = *(_DWORD *)(WindowLongPtrW + 16) | 0x8000000;
              *(_DWORD *)(WindowLongPtrW + 16) = v22;
              v23 = v22 & 0x8000;
              goto LABEL_148;
            }
LABEL_444:
            *(_QWORD *)&Rect.left = 0;
            if ( g_uDragImages == v4 )
              return TBGenerateDragImage(v12, (__int64)lpMsg);
            if ( (unsigned int)CCWndProc(v12, v4, Buf1, v10, (__int64)&Rect) )
              return *(_QWORD *)&Rect.left;
            return DefWindowProcW(hWnd, v4, Buf1, (LPARAM)lpMsg);
          }
          v24 = 0;
LABEL_31:
          TBSetHotItem(v12, -1, v24);
          return 0;
        }
        if ( (*(_DWORD *)(WindowLongPtrW + 16) & 0x8000) != 0 )
        {
          v23 = 1;
LABEL_148:
          InvalidateRect(hWnd, 0, v23);
          return DefWindowProcW(hWnd, v4, Buf1, (LPARAM)lpMsg);
        }
        return DefWindowProcW(hWnd, v4, Buf1, (LPARAM)lpMsg);
      }
      if ( (*(_DWORD *)(WindowLongPtrW + 16) & 0x800) == 0
        && (*(_BYTE *)(WindowLongPtrW + 56) & 4) == 0
        && *(__int64 *)(WindowLongPtrW + 40) < 5 )
      {
        return DefWindowProcW(hWnd, v4, Buf1, (LPARAM)lpMsg);
      }
      v25 = *(_DWORD *)(WindowLongPtrW + 316);
      v26 = (v25 & 0x800) == 0;
      if ( Buf1 && (v25 & 0x800) != 0 )
      {
        if ( (v25 & 0x1000) != 0 )
        {
          RedrawWindow(hWnd, 0, 0, 1u);
          v25 = *(_DWORD *)(v12 + 316) & 0xFFFFEFFF;
        }
        v27 = v25 & 0xFFFFF7FF;
        *(_DWORD *)(v12 + 316) = v27;
        if ( (v27 & 0x2000) != 0 )
        {
          TBRecalc(v12);
          TBAutoSize(v12);
          *(_DWORD *)(v12 + 316) &= ~0x2000u;
        }
      }
      else
      {
        *(_DWORD *)(WindowLongPtrW + 316) = v25 & 0xFFFFF7FF | (Buf1 == 0 ? 0x800 : 0);
      }
      if ( *(__int64 *)(v12 + 40) >= 5 )
        return v26;
      return v21;
    }
    if ( v4 != 15 )
    {
      if ( v4 != 20 )
      {
        if ( v4 == 21 )
        {
          InitGlobalColors();
          for ( i = 0; i < *(_DWORD *)(v12 + 280); ++i )
          {
            v32 = (struct _IMAGELIST *)TBGetImageList(v12, 0);
            if ( v32 )
            {
              v33 = g_clrBtnFace;
              if ( (*(_DWORD *)(v12 + 16) & 0x8000) != 0 )
                v33 = -1;
              ImageList_SetBkColor(v32, v33);
            }
            v34 = (struct _IMAGELIST *)TBGetImageList(v12, 1);
            if ( v34 )
            {
              v35 = g_clrBtnFace;
              if ( (*(_DWORD *)(v12 + 16) & 0x8000) != 0 )
                v35 = -1;
              ImageList_SetBkColor(v34, v35);
            }
          }
          v28 = *(HWND *)(v12 + 104);
          if ( !v28 )
            return 0;
          v29 = 21;
          goto LABEL_82;
        }
        if ( v4 == 26 )
        {
          InitGlobalMetrics(Buf1);
          if ( (*(_BYTE *)(v12 + 316) & 4) != 0 )
            TBChangeFont(v12, Buf1, 0);
          v30 = *(HWND *)(v12 + 104);
          if ( v30 )
            SendMessageW(v30, 0x1Au, Buf1, (LPARAM)lpMsg);
          InitGlobalColors();
          *(_DWORD *)(v12 + 208) = GetSystemMetrics(72);
          TBRecalc(v12);
LABEL_69:
          InvalidateRect(hWnd, 0, 1);
          return 0;
        }
        if ( v4 != 43 && v4 != 44 && v4 - 46 > 1 )
          goto LABEL_444;
LABEL_63:
        v28 = *(HWND *)(WindowLongPtrW + 8);
        v29 = v4;
LABEL_82:
        SendMessageW(v28, v29, Buf1, (LPARAM)lpMsg);
        return 0;
      }
      TB_OnEraseBkgnd(WindowLongPtrW, Buf1);
      return v11;
    }
LABEL_174:
    if ( (*(_BYTE *)(WindowLongPtrW + 316) & 0x10) != 0 )
      FlushToolTipsMgrNow(WindowLongPtrW);
    if ( (*(_DWORD *)(v12 + 316) & 0x800) != 0 )
    {
      if ( !Buf1 )
      {
        memset(&Paint, 0, sizeof(Paint));
        BeginPaint(hWnd, &Paint);
        EndPaint(hWnd, &Paint);
      }
      *(_DWORD *)(v12 + 316) |= 0x1000u;
    }
    else
    {
      TBPaint(v12, Buf1);
    }
    return 0;
  }
  if ( v4 > 0x85 )
  {
    if ( v4 != 134 )
    {
      switch ( v4 )
      {
        case 0x87u:
          return 129;
        case 0x100u:
          if ( (unsigned int)TBOnKey(WindowLongPtrW, (unsigned int)Buf1, WORD1(lpMsg)) )
            return 0;
          return DefWindowProcW(hWnd, v4, Buf1, (LPARAM)lpMsg);
        case 0x102u:
        case 0x106u:
          if ( (unsigned int)TBOnChar(WindowLongPtrW, (unsigned int)Buf1) || *(__int64 *)(v12 + 40) < 5 )
            return 0;
          return DefWindowProcW(hWnd, v4, Buf1, (LPARAM)lpMsg);
      }
      if ( v4 != 273 )
      {
        if ( v4 != 296 )
        {
          if ( v4 == 512 )
          {
            TBOnMouseMove(WindowLongPtrW, hWnd, 512, Buf1, lpMsg);
            return 0;
          }
          goto LABEL_444;
        }
        if ( (unsigned int)CCOnUIState(WindowLongPtrW, v9, Buf1) )
        {
          LOBYTE(v21) = (_WORD)Buf1 == 1;
          v23 = v21;
          goto LABEL_148;
        }
        return DefWindowProcW(hWnd, v4, Buf1, (LPARAM)lpMsg);
      }
      goto LABEL_63;
    }
    if ( ((*(_DWORD *)(WindowLongPtrW + 316) >> 6) & 1) != (_DWORD)Buf1 && !GetParent(hWnd) )
    {
      *(_DWORD *)(v12 + 316) ^= ((unsigned __int8)*(_DWORD *)(v12 + 316) ^ (unsigned __int8)((_BYTE)Buf1 << 6)) & 0x40;
      if ( *(int *)(v12 + 200) > 0 )
      {
        do
        {
          InvalidateButton(v12, *(_QWORD *)(v12 + 80) + 40LL * (int)v21, 0);
          LODWORD(v21) = v21 + 1;
        }
        while ( (int)v21 < *(_DWORD *)(v12 + 200) );
      }
    }
LABEL_159:
    if ( (*(_BYTE *)(v12 + 16) & 0x40) == 0 )
    {
      Rect = 0;
      WindowDC = GetWindowDC(hWnd);
      GetWindowRect(hWnd, &Rect);
      MapWindowPoints(0, hWnd, (LPPOINT)&Rect, 2u);
      Rect.bottom = -Rect.top;
      Rect.top = -Rect.top - g_cyEdge;
      CCDrawEdge(WindowDC, &Rect, 2, 10, v12 + 256);
      ReleaseDC(hWnd, WindowDC);
    }
    return DefWindowProcW(hWnd, v4, Buf1, (LPARAM)lpMsg);
  }
  switch ( v4 )
  {
    case 0x85u:
      goto LABEL_159;
    case 0x31u:
      return *(_QWORD *)(WindowLongPtrW + 128);
    case 0x3Du:
      if ( (_DWORD)lpMsg == -12 )
        return 65548;
      return DefWindowProcW(hWnd, v4, Buf1, (LPARAM)lpMsg);
    case 0x4Eu:
      wParam_low = LODWORD(lpMsg->wParam);
      if ( (unsigned int)(wParam_low + 950) > 0x32 )
      {
        if ( (_DWORD)wParam_low == -530 )
        {
          v42 = PositionFromID(WindowLongPtrW, *(_QWORD *)&lpMsg->message);
          if ( v42 != -1 )
          {
            v43 = 5LL * v42;
            if ( !(unsigned int)TBGetInfoTip(v12, lpMsg, *(_QWORD *)(v12 + 80) + 40LL * v42) )
              SendNotifyEx(*(_QWORD *)(v12 + 8), -1, LODWORD(lpMsg->wParam), lpMsg, *(_DWORD *)(v12 + 24) & 1);
            if ( LODWORD(lpMsg->wParam) == -530 )
            {
              if ( (v44 = *(_QWORD *)(v12 + 80) + 8 * v43, !*(_DWORD *)(v12 + 164))
                || (*(_BYTE *)(v12 + 56) & 8) != 0
                && (*(_DWORD *)(v12 + 16) & 0x1000) != 0
                && (*(_BYTE *)(v44 + 9) & 0x40) == 0
                || (*(_BYTE *)(v44 + 8) & 0x40) != 0 )
              {
                lParam = (_WORD *)lpMsg->lParam;
                if ( (unsigned __int64)(lParam - 0x8000) <= 0xFFFFFFFFFFFEFFFEuLL && !*lParam )
                {
                  v46 = TB_StrForButton(v12, v44);
                  if ( v46 )
                    lpMsg->lParam = v46;
                }
              }
            }
          }
          return v21;
        }
        return SendNotifyEx(
                 *(_QWORD *)(WindowLongPtrW + 8),
                 -1,
                 wParam_low,
                 lpMsg,
                 *(_DWORD *)(WindowLongPtrW + 24) & 1);
      }
      else if ( (_DWORD)wParam_low == -902 )
      {
        return TB_OnCalcSize(WindowLongPtrW, lpMsg);
      }
      else
      {
        if ( (_DWORD)wParam_low != -901 )
          return v21;
        return TB_OnScroll(WindowLongPtrW, lpMsg);
      }
    case 0x55u:
      return CIHandleNotifyFormat(WindowLongPtrW, lpMsg);
    case 0x7Cu:
      if ( Buf1 == -16 )
      {
        v38 = HIDWORD(lpMsg->hwnd);
        if ( (LODWORD(lpMsg->hwnd) ^ v38) == 0x10000000 )
        {
          v39 = (_OWORD *)(WindowLongPtrW + 300);
          if ( (v38 & 0x10000000) != 0 )
          {
            DefWindowProcW(hWnd, 0xBu, 1u, 0);
            RedrawWindow(hWnd, (const RECT *)(v12 + 300), 0, 0x81u);
            *v39 = 0;
          }
          else
          {
            *v39 = 0;
            GetUpdateRect(*(HWND *)WindowLongPtrW, (LPRECT)(WindowLongPtrW + 300), 0);
            EnumChildWindows(*(HWND *)v12, GetUpdateRectEnumProc, v12);
            DefWindowProcW(hWnd, 0xBu, 0, 0);
          }
        }
      }
      return 0;
    case 0x7Du:
      if ( Buf1 == -16 )
      {
        v37 = HIDWORD(lpMsg->hwnd);
LABEL_305:
        TBSetStyle(v12, v37);
      }
      else if ( Buf1 == -20 )
      {
        if ( ((HIDWORD(lpMsg->hwnd) ^ *(_DWORD *)(WindowLongPtrW + 32)) & 0x400000) != 0 )
          TBAutoSize(WindowLongPtrW);
        *(_DWORD *)(v12 + 32) = HIDWORD(lpMsg->hwnd);
      }
      return 0;
  }
  if ( v4 != 131 )
  {
    if ( v4 != 132 )
      goto LABEL_444;
    return v11;
  }
  result = DefWindowProcW(hWnd, 0x83u, Buf1, (LPARAM)lpMsg);
  if ( (*(_BYTE *)(v12 + 16) & 0x40) == 0 )
    HIDWORD(lpMsg->hwnd) += g_cyEdge;
  return result;
}

```

## disassembly

```asm
0x18002aab0  push    rbp
0x18002aab2  push    rbx
0x18002aab3  push    rsi
0x18002aab4  push    rdi
0x18002aab5  push    r12
0x18002aab7  push    r13
0x18002aab9  push    r14
0x18002aabb  push    r15
0x18002aabd  lea     rbp, [rsp-1Fh]
0x18002aac2  sub     rsp, 0C8h
0x18002aac9  mov     rax, cs:__security_cookie
0x18002aad0  xor     rax, rsp
0x18002aad3  mov     [rbp+57h+var_50], rax
0x18002aad7  mov     r12d, edx
0x18002aada  mov     dword ptr [rbp+57h+WideCharStr], edx
0x18002aadd  xor     edx, edx; nIndex
0x18002aadf  mov     rsi, r9
0x18002aae2  mov     r15, r8
0x18002aae5  mov     r13, rcx
0x18002aae8  call    cs:__imp_GetWindowLongPtrW
0x18002aaee  mov     ecx, 81h
0x18002aaf3  mov     ebx, 1
0x18002aaf8  mov     rdi, rax
0x18002aafb  cmp     r12d, ecx
0x18002aafe  jnz     loc_18002AC3F
0x18002ab04  call    CCCreateWindow
0x18002ab09  call    InitDitherBrush
0x18002ab0e  mov     edx, 158h; uBytes
0x18002ab13  lea     ecx, [rbx+3Fh]; uFlags
0x18002ab16  call    cs:__imp_LocalAlloc
0x18002ab1c  xor     r14d, r14d
0x18002ab1f  mov     rdi, rax
0x18002ab22  test    rax, rax
0x18002ab25  jz      loc_18002AC02
0x18002ab2b  mov     r8, rsi
0x18002ab2e  mov     rdx, r13
0x18002ab31  mov     rcx, rax
0x18002ab34  call    CIInitialize
0x18002ab39  bts     dword ptr [rdi+13Ch], 11h
0x18002ab41  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002ab45  mov     r15d, 0FF000000h
0x18002ab4b  mov     [rdi+11Ch], r12d
0x18002ab52  mov     [rdi+120h], r12d
0x18002ab59  mov     [rdi+124h], r12d
0x18002ab60  mov     [rdi+128h], r15d
0x18002ab67  mov     [rdi+0D4h], r14d
0x18002ab6e  call    InitGlobalColors
0x18002ab73  lea     ecx, [rbx+47h]; nIndex
0x18002ab76  call    cs:__imp_GetSystemMetrics
0x18002ab7c  or      dword ptr [rdi+13Ch], 8040h
0x18002ab86  mov     [rdi+0D0h], eax
0x18002ab8c  mov     eax, cs:g_cxEdge
0x18002ab92  add     eax, eax
0x18002ab94  mov     dword ptr [rdi+0D8h], 7
0x18002ab9e  mov     [rdi+0E0h], eax
0x18002aba4  mov     [rdi+0E4h], eax
0x18002abaa  mov     eax, [rdi+10h]
0x18002abad  bt      eax, 0Bh
0x18002abb1  mov     dword ptr [rdi+0DCh], 6
0x18002abbb  mov     [rdi+108h], r15d
0x18002abc2  mov     [rdi+104h], r15d
0x18002abc9  mov     [rdi+0A4h], ebx
0x18002abcf  jnb     short loc_18002ABD8
0x18002abd1  bts     eax, 0Fh
0x18002abd5  mov     [rdi+10h], eax
0x18002abd8  xor     r8d, r8d
0x18002abdb  xor     edx, edx
0x18002abdd  mov     rcx, rdi
0x18002abe0  call    TBChangeFont
0x18002abe5  mov     edx, 10h
0x18002abea  mov     rcx, rdi
0x18002abed  mov     r8d, edx
0x18002abf0  call    SetBitmapSize
0x18002abf5  test    eax, eax
0x18002abf7  jnz     short loc_18002AC09
0x18002abf9  mov     rcx, rdi; hMem
0x18002abfc  call    cs:__imp_LocalFree
0x18002ac02  xor     eax, eax
0x18002ac04  jmp     loc_18002ADB2
0x18002ac09  mov     r8, rdi; dwNewLong
0x18002ac0c  xor     edx, edx; nIndex
0x18002ac0e  mov     rcx, r13; hWnd
0x18002ac11  call    cs:__imp_SetWindowLongPtrW
0x18002ac17  mov     r8d, [rdi+10h]
0x18002ac1b  test    r8b, 3
0x18002ac1f  jnz     loc_18002AFC4
0x18002ac25  or      r8d, ebx; dwNewLong
0x18002ac28  mov     edx, 0FFFFFFF0h; nIndex
0x18002ac2d  mov     rcx, r13; hWnd
0x18002ac30  mov     [rdi+10h], r8d
0x18002ac34  call    cs:__imp_SetWindowLongW
0x18002ac3a  jmp     loc_18002AFC4
0x18002ac3f  xor     r14d, r14d
0x18002ac42  test    rdi, rdi
0x18002ac45  jz      loc_18002ADA0
0x18002ac4b  mov     eax, 420h
0x18002ac50  cmp     r12d, eax
0x18002ac53  ja      loc_18002BBCA
0x18002ac59  jz      loc_18002BBB2
0x18002ac5f  mov     r8d, 201h
0x18002ac65  cmp     r12d, r8d
0x18002ac68  ja      loc_18002B46B
0x18002ac6e  jz      loc_18002B456
0x18002ac74  cmp     r12d, 30h ; '0'
0x18002ac78  ja      loc_18002AFE5
0x18002ac7e  jz      loc_18002AFCC
0x18002ac84  cmp     r12d, 0Bh
0x18002ac88  ja      loc_18002AE71
0x18002ac8e  jz      loc_18002ADD2
0x18002ac94  mov     eax, r12d
0x18002ac97  test    r12d, r12d
0x18002ac9a  jz      loc_18002AC02
0x18002aca0  sub     eax, ebx
0x18002aca2  jz      loc_18002AD7E
0x18002aca8  sub     eax, ebx
0x18002acaa  jz      loc_18002AD65
0x18002acb0  sub     eax, ebx
0x18002acb2  jz      loc_18002AD54
0x18002acb8  sub     eax, 2
0x18002acbb  jz      short loc_18002AD31
0x18002acbd  sub     eax, 2
0x18002acc0  jz      short loc_18002AD0A
0x18002acc2  sub     eax, ebx
0x18002acc4  jz      short loc_18002ACF6
0x18002acc6  cmp     eax, 2
0x18002acc9  jnz     def_18002BC04; jumptable 000000018002BC04 default case
0x18002accf  mov     r8d, [rdi+10h]
0x18002acd3  mov     eax, r8d
0x18002acd6  bts     eax, 1Bh
0x18002acda  btr     r8d, 1Bh
0x18002acdf  test    r15, r15
0x18002ace2  cmovz   r8d, eax
0x18002ace6  mov     [rdi+10h], r8d
0x18002acea  and     r8d, 8000h
0x18002acf1  jmp     loc_18002B30F
0x18002acf6  xor     r8d, r8d
0x18002acf9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002acfd  mov     rcx, rdi
0x18002ad00  call    TBSetHotItem
0x18002ad05  jmp     loc_18002AC02
0x18002ad0a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002ad0e  cmp     [rdi+11Ch], r12d
0x18002ad15  jnz     loc_18002AC02
0x18002ad1b  xor     r9d, r9d
0x18002ad1e  mov     r8d, ebx
0x18002ad21  mov     edx, r12d
0x18002ad24  mov     rcx, rdi
0x18002ad27  call    TBCycleHotItem
0x18002ad2c  jmp     loc_18002AC02
0x18002ad31  mov     rax, rsi
0x18002ad34  movzx   edx, si
0x18002ad37  shr     rax, 10h
0x18002ad3b  mov     rcx, rdi
0x18002ad3e  movzx   r8d, ax
0x18002ad42  call    TB_OnSize
0x18002ad47  mov     rcx, rdi; jumptable 000000018002BC04 case 1057
0x18002ad4a  call    TBAutoSize
0x18002ad4f  jmp     loc_18002AC02
0x18002ad54  test    dword ptr [rdi+10h], 8000h
0x18002ad5b  jz      short loc_18002ADA0
0x18002ad5d  mov     r8d, ebx
0x18002ad60  jmp     loc_18002B30F
0x18002ad65  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002ad69  lock add cs:g_dwWindowCount, r12d
0x18002ad71  mov     rcx, rdi; hMem
0x18002ad74  call    TB_OnDestroy
0x18002ad79  jmp     loc_18002AC02
0x18002ad7e  test    dword ptr [rdi+10h], 4000h
0x18002ad85  jz      short loc_18002ADA0
0x18002ad87  mov     rcx, [rdi]
0x18002ad8a  lea     rdx, ToolbarDragCallback
0x18002ad91  mov     r8d, ebx
0x18002ad94  call    CreateDragProxy
0x18002ad99  mov     [rdi+0F0h], rax
0x18002ada0  mov     r9, rsi; lParam
0x18002ada3  mov     r8, r15; wParam
0x18002ada6  mov     edx, r12d; Msg
0x18002ada9  mov     rcx, r13; hWnd
0x18002adac  call    cs:__imp_DefWindowProcW
0x18002adb2  mov     rcx, [rbp+57h+var_50]
0x18002adb6  xor     rcx, rsp; StackCookie
0x18002adb9  call    __security_check_cookie
0x18002adbe  add     rsp, 0C8h
0x18002adc5  pop     r15
0x18002adc7  pop     r14
0x18002adc9  pop     r13
0x18002adcb  pop     r12
0x18002adcd  pop     rdi
0x18002adce  pop     rsi
0x18002adcf  pop     rbx
0x18002add0  pop     rbp
0x18002add1  retn
0x18002add2  mov     edx, 800h
0x18002add7  test    [rdi+10h], edx
0x18002adda  jnz     short loc_18002ADE9
0x18002addc  test    byte ptr [rdi+38h], 4
0x18002ade0  jnz     short loc_18002ADE9
0x18002ade2  cmp     qword ptr [rdi+28h], 5
0x18002ade7  jl      short loc_18002ADA0
0x18002ade9  mov     ecx, [rdi+13Ch]
0x18002adef  mov     rsi, r14
0x18002adf2  mov     eax, ecx
0x18002adf4  and     eax, edx
0x18002adf6  setz    sil
0x18002adfa  test    r15, r15
0x18002adfd  jz      short loc_18002AE4E
0x18002adff  test    eax, eax
0x18002ae01  jz      short loc_18002AE4E
0x18002ae03  bt      ecx, 0Ch
0x18002ae07  jnb     short loc_18002AE24
0x18002ae09  mov     r9d, ebx; flags
0x18002ae0c  xor     r8d, r8d; hrgnUpdate
0x18002ae0f  xor     edx, edx; lprcUpdate
0x18002ae11  mov     rcx, r13; hWnd
0x18002ae14  call    cs:__imp_RedrawWindow
0x18002ae1a  mov     ecx, [rdi+13Ch]
0x18002ae20  btr     ecx, 0Ch
0x18002ae24  btr     ecx, 0Bh
0x18002ae28  mov     [rdi+13Ch], ecx
0x18002ae2e  bt      ecx, 0Dh
0x18002ae32  jnb     short loc_18002AE63
0x18002ae34  mov     rcx, rdi
0x18002ae37  call    TBRecalc
0x18002ae3c  mov     rcx, rdi
0x18002ae3f  call    TBAutoSize
0x18002ae44  btr     dword ptr [rdi+13Ch], 0Dh
0x18002ae4c  jmp     short loc_18002AE63
0x18002ae4e  neg     r15
0x18002ae51  sbb     eax, eax
0x18002ae53  btr     ecx, 0Bh
0x18002ae57  not     eax
0x18002ae59  and     eax, edx
0x18002ae5b  or      eax, ecx
0x18002ae5d  mov     [rdi+13Ch], eax
0x18002ae63  cmp     qword ptr [rdi+28h], 5
0x18002ae68  cmovge  r14, rsi
0x18002ae6c  jmp     loc_18002B181
0x18002ae71  mov     eax, r12d
0x18002ae74  sub     eax, 0Fh
0x18002ae77  jz      loc_18002B4DE
0x18002ae7d  sub     eax, 5
0x18002ae80  jz      loc_18002AFB9
0x18002ae86  sub     eax, ebx
0x18002ae88  jz      loc_18002AF1F
0x18002ae8e  sub     eax, 5
0x18002ae91  jz      short loc_18002AEB5
0x18002ae93  sub     eax, 11h
0x18002ae96  jz      short loc_18002AEA9
0x18002ae98  sub     eax, ebx
0x18002ae9a  jz      short loc_18002AEA9
0x18002ae9c  sub     eax, 2
0x18002ae9f  jz      short loc_18002AEA9
0x18002aea1  cmp     eax, ebx
0x18002aea3  jnz     def_18002BC04; jumptable 000000018002BC04 default case
0x18002aea9  mov     rcx, [rdi+8]
0x18002aead  mov     edx, r12d
0x18002aeb0  jmp     loc_18002AFA8
0x18002aeb5  mov     rcx, r15
0x18002aeb8  call    InitGlobalMetrics
0x18002aebd  test    byte ptr [rdi+13Ch], 4
0x18002aec4  jz      short loc_18002AED4
0x18002aec6  xor     r8d, r8d
0x18002aec9  mov     rdx, r15
0x18002aecc  mov     rcx, rdi
0x18002aecf  call    TBChangeFont
0x18002aed4  mov     rcx, [rdi+68h]; hWnd
0x18002aed8  test    rcx, rcx
0x18002aedb  jz      short loc_18002AEEE
0x18002aedd  mov     r9, rsi; lParam
0x18002aee0  mov     r8, r15; wParam
0x18002aee3  mov     edx, 1Ah; Msg
0x18002aee8  call    cs:__imp_SendMessageW
0x18002aeee  call    InitGlobalColors
0x18002aef3  mov     ecx, 48h ; 'H'; nIndex
0x18002aef8  call    cs:__imp_GetSystemMetrics
0x18002aefe  mov     rcx, rdi
0x18002af01  mov     [rdi+0D0h], eax
0x18002af07  call    TBRecalc
0x18002af0c  mov     r8d, ebx; bErase
0x18002af0f  xor     edx, edx; lpRect
0x18002af11  mov     rcx, r13; hWnd
0x18002af14  call    cs:__imp_InvalidateRect
0x18002af1a  jmp     loc_18002AC02
0x18002af1f  call    InitGlobalColors
0x18002af24  mov     r13d, r14d
0x18002af27  cmp     [rdi+118h], r14d
0x18002af2e  jle     short loc_18002AF96
0x18002af30  or      r12d, 0FFFFFFFFh
0x18002af34  mov     r8d, r13d
0x18002af37  xor     edx, edx
0x18002af39  mov     rcx, rdi
0x18002af3c  call    TBGetImageList
0x18002af41  test    rax, rax
0x18002af44  jz      short loc_18002AF5F
0x18002af46  test    dword ptr [rdi+10h], 8000h
0x18002af4d  mov     rcx, rax; himl
0x18002af50  mov     edx, cs:g_clrBtnFace
0x18002af56  cmovnz  edx, r12d; clrBk
0x18002af5a  call    ImageList_SetBkColor
0x18002af5f  mov     r8d, r13d
  ... truncated ...
```
