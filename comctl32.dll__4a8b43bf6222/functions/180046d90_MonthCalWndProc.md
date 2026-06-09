# MonthCalWndProc

- ea: `0x180046d90`
- end: `0x180047b94`
- name: `MonthCalWndProc`
- size: `3588`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `38`
- tags: `loader_planting, installer_update`

## callees

- `0x1800115f0`
- `0x180017bac`
- `0x1800183dc`
- `0x180018464`
- `0x1800190a4`
- `0x18001923c`
- `0x18003a6b8`
- `0x180042274`
- `0x180042794`
- `0x180042b14`
- `0x180042bec`
- `0x180043604`
- `0x180043670`
- `0x180043970`
- `0x180043fe4`
- `0x1800440e8`
- `0x1800442cc`
- `0x180044574`
- `0x180044d48`
- `0x180044fd4`
- `0x1800451c8`
- `0x1800452a0`
- `0x180045370`
- `0x180046298`
- `0x180046348`
- `0x1800463d4`
- `0x1800464fc`
- `0x18004661c`
- `0x18004669c`
- `0x180046874`
- `0x180046cd8`
- `0x180046d90`
- `0x180049c98`
- `0x180072058`
- `0x1800720fc`
- `0x1800722a0`
- `0x180072690`
- `0x18008ea60`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180046ddb`
- `KERNEL32!LocalAlloc` at `0x180046ddb`
- `USER32!GetClientRect` at `0x1800472c0`
- `USER32!GetClientRect` at `0x1800472c0`
- `USER32!MessageBeep` at `0x180046f9a`
- `USER32!MessageBeep` at `0x180046f9a`
- `USER32!SetWindowLongPtrW` at `0x180046df2`
- `USER32!SetWindowLongPtrW` at `0x180046df2`
- `USER32!InvalidateRect` at `0x180046ed1`
- `USER32!InvalidateRect` at `0x180047053`
- `USER32!InvalidateRect` at `0x1800473d8`
- `USER32!InvalidateRect` at `0x1800473e7`
- `USER32!InvalidateRect` at `0x18004777b`
- `USER32!InvalidateRect` at `0x180047835`
- `USER32!InvalidateRect` at `0x180046ed1`
- `USER32!InvalidateRect` at `0x180047053`
- `USER32!InvalidateRect` at `0x1800473d8`
- `USER32!InvalidateRect` at `0x1800473e7`
- `USER32!InvalidateRect` at `0x18004777b`
- `USER32!InvalidateRect` at `0x180047835`
- `USER32!GetWindowLongPtrW` at `0x180046e07`
- `USER32!GetWindowLongPtrW` at `0x180046e07`
- `USER32!BeginPaint` at `0x180047261`
- `USER32!BeginPaint` at `0x180047261`
- `USER32!EndPaint` at `0x180047279`
- `USER32!EndPaint` at `0x180047279`
- `USER32!DefWindowProcW` at `0x180046e21`
- `USER32!DefWindowProcW` at `0x180047b03`
- `USER32!DefWindowProcW` at `0x180046e21`
- `USER32!DefWindowProcW` at `0x180047b03`
- `USER32!UpdateWindow` at `0x1800473f0`
- `USER32!UpdateWindow` at `0x1800476c9`
- `USER32!UpdateWindow` at `0x1800473f0`
- `USER32!UpdateWindow` at `0x1800476c9`
- `USER32!PostMessageW` at `0x180046ffa`
- `USER32!PostMessageW` at `0x180047134`
- `USER32!PostMessageW` at `0x180046ffa`
- `USER32!PostMessageW` at `0x180047134`
- `USER32!AdjustWindowRect` at `0x1800477b3`
- `USER32!AdjustWindowRect` at `0x1800477ec`
- `USER32!AdjustWindowRect` at `0x1800477b3`
- `USER32!AdjustWindowRect` at `0x1800477ec`

## pseudocode

```c
unsigned __int64 __fastcall MonthCalWndProc(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  __int64 v4; // r15
  HLOCAL v9; // rax
  unsigned __int64 v10; // rbx
  __int64 v12; // rdx
  LONG_PTR WindowLongPtrW; // rdi
  int v14; // r9d
  BOOL v15; // edx
  int v17; // edx
  unsigned int v18; // eax
  unsigned int v19; // ecx
  LPARAM v20; // r9
  UINT v21; // edx
  int v22; // ebx
  WPARAM v23; // r14
  HDC v24; // rax
  int v25; // eax
  bool v26; // zf
  struct tagRECT *v27; // r14
  __int128 v28; // xmm0
  struct tagRECT v29; // xmm1
  __int128 *v30; // r12
  __int128 v31; // xmm0
  int v32; // eax
  __int128 v33; // xmm1
  __int64 i; // rdx
  int v35; // eax
  int v36; // ecx
  DWORD v37; // edx
  BOOL v38; // r8d
  int v39; // ecx
  WPARAM v40; // r12
  int v41; // r14d
  __int128 v42; // xmm0
  int v43; // eax
  __int128 v44; // xmm0
  unsigned int v45; // eax
  __int128 *v46; // rdx
  __int128 *v47; // rcx
  __int128 v48; // xmm0
  int v49; // eax
  unsigned int v50; // eax
  WPARAM v51; // r8
  struct tagRECT Rect; // [rsp+30h] [rbp-69h] BYREF
  __int128 v53; // [rsp+40h] [rbp-59h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+50h] [rbp-49h] BYREF

  v4 = 0;
  *(_QWORD *)&Rect.left = 0;
  if ( Msg != 129 )
  {
    WindowLongPtrW = GetWindowLongPtrW(hWnd, 0);
    if ( !WindowLongPtrW )
      return DefWindowProcW(hWnd, Msg, wParam, lParam);
    if ( Msg > 0x318 )
    {
      v10 = 1;
      switch ( Msg )
      {
        case 0xFFFu:
          goto LABEL_97;
        case 0x1001u:
          if ( (*(_BYTE *)(WindowLongPtrW + 16) & 2) != 0 || !lParam )
            return v4;
          *(_OWORD *)lParam = 0;
          *(_OWORD *)lParam = *(_OWORD *)(WindowLongPtrW + 1820);
          *(_WORD *)(lParam + 4) = ((int)(GetStartDowForMonth(
                                            *(unsigned __int16 *)lParam,
                                            *(unsigned __int16 *)(lParam + 2))
                                        + *(unsigned __int16 *)(lParam + 6)
                                        - 1)
                                  % 7
                                  + 1)
                                 % 7;
          return 1;
        case 0x1002u:
          if ( (*(_BYTE *)(WindowLongPtrW + 16) & 2) != 0 || !(unsigned int)IsValidDate(lParam) )
            return v4;
          if ( !(unsigned int)CmpDate(lParam, WindowLongPtrW + 1820) )
            return 1;
          *(_DWORD *)(WindowLongPtrW + 2392) |= 0x40u;
          *(_OWORD *)(WindowLongPtrW + 2116) = *(_OWORD *)(WindowLongPtrW + 2100);
          v25 = MCSetDate(WindowLongPtrW, lParam);
          *(_DWORD *)(WindowLongPtrW + 2392) &= ~0x40u;
          v4 = v25;
          if ( v25 )
          {
            InvalidateRect(*(HWND *)WindowLongPtrW, (const RECT *)(WindowLongPtrW + 2116), 0);
            InvalidateRect(*(HWND *)WindowLongPtrW, (const RECT *)(WindowLongPtrW + 2100), 0);
          }
          UpdateWindow(*(HWND *)WindowLongPtrW);
          return v4;
        case 0x1003u:
          if ( (*(_BYTE *)(WindowLongPtrW + 16) & 2) != 0 )
            LODWORD(v10) = *(_DWORD *)(WindowLongPtrW + 1800);
          return (unsigned int)v10;
        case 0x1004u:
          if ( (*(_BYTE *)(WindowLongPtrW + 16) & 2) == 0 || (int)wParam < 1 )
            return v4;
          *(_DWORD *)(WindowLongPtrW + 1800) = wParam;
          return 1;
        case 0x1005u:
          if ( !lParam )
            return v4;
          *(_OWORD *)lParam = 0;
          *(_OWORD *)(lParam + 16) = 0;
          if ( (*(_BYTE *)(WindowLongPtrW + 16) & 2) == 0 )
            return v4;
          *(_OWORD *)lParam = *(_OWORD *)(WindowLongPtrW + 1820);
          *(_WORD *)(lParam + 4) = ((int)(GetStartDowForMonth(
                                            *(unsigned __int16 *)lParam,
                                            *(unsigned __int16 *)(lParam + 2))
                                        + *(unsigned __int16 *)(lParam + 6)
                                        - 1)
                                  % 7
                                  + 1)
                                 % 7;
          *(_OWORD *)(lParam + 16) = *(_OWORD *)(WindowLongPtrW + 1836);
          *(_WORD *)(lParam + 20) = ((int)(GetStartDowForMonth(
                                             *(unsigned __int16 *)(lParam + 16),
                                             *(unsigned __int16 *)(lParam + 18))
                                         + *(unsigned __int16 *)(lParam + 22)
                                         - 1)
                                   % 7
                                   + 1)
                                  % 7;
          return 1;
        case 0x1006u:
          v26 = (*(_BYTE *)(WindowLongPtrW + 16) & 2) == 0;
          Rect = 0;
          v53 = 0;
          if ( v26 )
            return v4;
          if ( !(unsigned int)IsValidDate(lParam) )
            return v4;
          v27 = (struct tagRECT *)(lParam + 16);
          if ( !(unsigned int)IsValidDate(lParam + 16) )
            return v4;
          if ( *(_WORD *)(lParam + 8) > 0x17u || *(_WORD *)(lParam + 10) > 0x3Bu || *(_WORD *)(lParam + 12) > 0x3Bu )
          {
            *(_WORD *)(lParam + 8) = *(_WORD *)(WindowLongPtrW + 1828);
            *(_WORD *)(lParam + 10) = *(_WORD *)(WindowLongPtrW + 1830);
            *(_WORD *)(lParam + 12) = *(_WORD *)(WindowLongPtrW + 1832);
          }
          if ( *(_WORD *)(lParam + 24) > 0x17u || *(_WORD *)(lParam + 26) > 0x3Bu || *(_WORD *)(lParam + 28) > 0x3Bu )
          {
            *(_WORD *)(lParam + 24) = *(_WORD *)(WindowLongPtrW + 1844);
            *(_WORD *)(lParam + 26) = *(_WORD *)(WindowLongPtrW + 1846);
            *(_WORD *)(lParam + 28) = *(_WORD *)(WindowLongPtrW + 1848);
          }
          if ( (int)CmpDate(lParam, lParam + 16) > 0 )
          {
            v28 = *(_OWORD *)lParam;
            lParam = (LPARAM)&Rect;
            v29 = *v27;
            v27 = (struct tagRECT *)&v53;
            v53 = v28;
            Rect = v29;
          }
          if ( (int)CmpDate(lParam, WindowLongPtrW + 1768) < 0
            || (int)CmpDate(v27, WindowLongPtrW + 1784) > 0
            || (unsigned int)DaysBetweenDates(lParam, v27) >= *(_DWORD *)(WindowLongPtrW + 1800) )
          {
            return v4;
          }
          v30 = (__int128 *)(WindowLongPtrW + 1820);
          if ( !(unsigned int)CmpDate(lParam, WindowLongPtrW + 1820)
            && !(unsigned int)CmpDate(v27, WindowLongPtrW + 1836) )
          {
            return 1;
          }
          v31 = *v30;
          *(_DWORD *)(WindowLongPtrW + 2392) |= 0x40u;
          *(_OWORD *)(WindowLongPtrW + 1852) = v31;
          *(_OWORD *)(WindowLongPtrW + 1868) = *(_OWORD *)(WindowLongPtrW + 1836);
          v32 = MCSetDate(WindowLongPtrW, v27);
          v4 = v32;
          if ( v32 )
          {
            *v30 = *(_OWORD *)lParam;
            *(struct tagRECT *)(WindowLongPtrW + 1836) = *v27;
            MCInvalidateDates(WindowLongPtrW, WindowLongPtrW + 1852, WindowLongPtrW + 1868);
            MCInvalidateDates(WindowLongPtrW, WindowLongPtrW + 1820, WindowLongPtrW + 1836);
            UpdateWindow(*(HWND *)WindowLongPtrW);
          }
          *(_DWORD *)(WindowLongPtrW + 2392) &= ~0x40u;
          return v4;
        case 0x1007u:
          if ( !lParam )
            goto LABEL_147;
          *(_OWORD *)lParam = 0;
          *(_OWORD *)(lParam + 16) = 0;
          if ( wParam )
          {
            if ( wParam != 1 )
              goto LABEL_147;
            *(_OWORD *)lParam = *(_OWORD *)(WindowLongPtrW + 1900);
            v33 = *(_OWORD *)(WindowLongPtrW + 1916);
          }
          else
          {
            *(_OWORD *)lParam = *(_OWORD *)(WindowLongPtrW + 1932);
            v33 = *(_OWORD *)(WindowLongPtrW + 1948);
          }
          *(_OWORD *)(lParam + 16) = v33;
LABEL_147:
          v4 = *(int *)(WindowLongPtrW + 1964);
          if ( wParam == 1 )
            v4 += 2;
          break;
        case 0x1008u:
          if ( (*(_BYTE *)(WindowLongPtrW + 16) & 1) == 0 || (_DWORD)wParam != *(_DWORD *)(WindowLongPtrW + 1964) + 2 )
            return v4;
          for ( i = 0; (int)i < (int)wParam; i = (unsigned int)(i + 1) )
          {
            v35 = *(_DWORD *)lParam;
            lParam += 4LL;
            *(_DWORD *)(WindowLongPtrW + 4 * i + 2288) = v35;
          }
          InvalidateRect(*(HWND *)WindowLongPtrW, (const RECT *)(WindowLongPtrW + 2148), 0);
          return 1;
        case 0x1009u:
          *(_QWORD *)lParam = 0;
          *(_DWORD *)(lParam + 8) = *(_DWORD *)(WindowLongPtrW + 1720);
          v36 = *(_DWORD *)(WindowLongPtrW + 1724);
          *(_DWORD *)(lParam + 12) = v36;
          if ( (*(_BYTE *)(WindowLongPtrW + 16) & 0x10) == 0 )
            *(_DWORD *)(lParam + 12) = *(_DWORD *)(WindowLongPtrW + 1732) + v36;
          AdjustWindowRect((LPRECT)lParam, *(_DWORD *)(WindowLongPtrW + 16), 0);
          *(_DWORD *)(lParam + 8) -= *(_DWORD *)lParam;
          *(_DWORD *)(lParam + 12) -= *(_DWORD *)(lParam + 4);
          *(_QWORD *)lParam = 0;
          return 1;
        case 0x100Au:
          if ( wParam >= 6 )
            return -1;
          v10 = *(unsigned int *)(WindowLongPtrW + 4 * wParam + 1688);
          *(_DWORD *)(WindowLongPtrW + 4 * wParam + 1688) = lParam;
          v38 = wParam == 0;
          goto LABEL_161;
        case 0x100Bu:
          if ( wParam >= 6 )
            return -1;
          else
            return *(unsigned int *)(WindowLongPtrW + 4 * wParam + 1688);
        case 0x100Cu:
          MCSetToday(WindowLongPtrW, lParam);
          return v4;
        case 0x100Du:
          if ( !lParam )
            return 0;
          *(_OWORD *)lParam = *(_OWORD *)(WindowLongPtrW + 1804);
          return v10;
        case 0x100Eu:
          return MCHandleHitTest(WindowLongPtrW, lParam);
        case 0x100Fu:
          v39 = *(_DWORD *)(WindowLongPtrW + 2392);
          v10 = *(unsigned __int16 *)(WindowLongPtrW + 1468) | (unsigned __int64)((unsigned __int16)(v39 & 0x200) << 7);
          if ( lParam == -1 )
          {
            *(_DWORD *)(WindowLongPtrW + 2392) = v39 & 0xFFFFFDFF;
          }
          else if ( lParam < 7 )
          {
            *(_DWORD *)(WindowLongPtrW + 2392) = v39 | 0x200;
            *(_DWORD *)(WindowLongPtrW + 1468) = (unsigned __int16)lParam;
          }
          UpdateLocaleInfo(WindowLongPtrW, WindowLongPtrW + 56);
          v38 = 0;
LABEL_161:
          InvalidateRect(hWnd, 0, v38);
          return v10;
        case 0x1010u:
          return *(unsigned __int16 *)(WindowLongPtrW + 1468)
               | (unsigned __int64)((*(_DWORD *)(WindowLongPtrW + 2392) & 0x200u) << 7);
        case 0x1011u:
          if ( lParam )
          {
            *(_OWORD *)lParam = 0;
            *(_OWORD *)(lParam + 16) = 0;
            if ( (*(_DWORD *)(WindowLongPtrW + 2392) & 0x800) != 0 )
            {
              v4 = 1;
              *(_OWORD *)lParam = *(_OWORD *)(WindowLongPtrW + 1768);
            }
            if ( (*(_DWORD *)(WindowLongPtrW + 2392) & 0x1000) != 0 )
            {
              v4 |= 2uLL;
              *(_OWORD *)(lParam + 16) = *(_OWORD *)(WindowLongPtrW + 1784);
            }
          }
          return v4;
        case 0x1012u:
          if ( !lParam )
            return v4;
          v40 = wParam & 1;
          if ( (wParam & 1) != 0 && !(unsigned int)IsValidDate(lParam) )
            return v4;
          v41 = wParam & 2;
          if ( v41 )
          {
            if ( !(unsigned int)IsValidDate(lParam + 16) )
              return v4;
          }
          if ( v40
            && (*(_WORD *)(lParam + 8) > 0x17u || *(_WORD *)(lParam + 10) > 0x3Bu || *(_WORD *)(lParam + 12) > 0x3Bu) )
          {
            *(_WORD *)(lParam + 8) = *(_WORD *)(WindowLongPtrW + 1812);
            *(_WORD *)(lParam + 10) = *(_WORD *)(WindowLongPtrW + 1814);
            *(_WORD *)(lParam + 12) = *(_WORD *)(WindowLongPtrW + 1816);
          }
          if ( v41
            && (*(_WORD *)(lParam + 24) > 0x17u || *(_WORD *)(lParam + 26) > 0x3Bu || *(_WORD *)(lParam + 28) > 0x3Bu) )
          {
            *(_WORD *)(lParam + 24) = *(_WORD *)(WindowLongPtrW + 1812);
            *(_WORD *)(lParam + 26) = *(_WORD *)(WindowLongPtrW + 1814);
            *(_WORD *)(lParam + 28) = *(_WORD *)(WindowLongPtrW + 1816);
          }
          if ( v40 )
          {
            v42 = *(_OWORD *)lParam;
            *(_DWORD *)(WindowLongPtrW + 2392) |= 0x800u;
          }
          else
          {
            v42 = c_stEpoch;
            *(_DWORD *)(WindowLongPtrW + 2392) &= ~0x800u;
          }
          v43 = *(_DWORD *)(WindowLongPtrW + 2392);
          *(_OWORD *)(WindowLongPtrW + 1768) = v42;
          if ( v41 )
          {
            v44 = *(_OWORD *)(lParam + 16);
            v45 = v43 | 0x1000;
          }
          else
          {
            v44 = c_stArmageddon;
            v45 = v43 & 0xFFFFEFFF;
          }
          *(_OWORD *)(WindowLongPtrW + 1784) = v44;
          *(_DWORD *)(WindowLongPtrW + 2392) = v45;
          if ( (v45 & 0x1800) == 0x1800 && (int)((__int64 (*)(void))CmpDate)() > 0 )
          {
            v48 = *v46;
            *v46 = *v47;
            *v47 = v48;
          }
          return 1;
        case 0x1013u:
          return *(int *)(((*(_DWORD *)(WindowLongPtrW + 2392) & 0x2000) != 0 ? 0x17C : 0) + WindowLongPtrW + 1964);
        case 0x1014u:
          v49 = *(_DWORD *)(WindowLongPtrW + 2392);
          if ( (v49 & 0x2000) != 0 )
            v4 = *(int *)(WindowLongPtrW + 2344);
          if ( (_DWORD)wParam )
          {
            *(_DWORD *)(WindowLongPtrW + 2344) = wParam;
            v50 = v49 | 0x2000;
          }
          else
          {
            v50 = v49 & 0xFFFFDFFF;
          }
          *(_DWORD *)(WindowLongPtrW + 2392) = v50;
          return v4;
        case 0x1015u:
          v37 = *(_DWORD *)(WindowLongPtrW + 16);
          Rect.right = *(_DWORD *)(WindowLongPtrW + 1736);
          Rect.bottom = *(_DWORD *)(WindowLongPtrW + 1732);
          *(_QWORD *)&Rect.left = 0;
          AdjustWindowRect(&Rect, v37, 0);
          return Rect.right - Rect.left;
        default:
          goto LABEL_210;
      }
      return v4;
    }
    if ( Msg == 792 )
      goto LABEL_92;
    if ( Msg <= 0x55 )
    {
      if ( Msg == 85 )
        return CIHandleNotifyFormat(WindowLongPtrW, lParam);
      if ( Msg <= 0x15 )
      {
        switch ( Msg )
        {
          case 0x15u:
            InitGlobalColors();
            return v4;
          case 1u:
            CCCreateWindow();
            return MCCreateHandler(WindowLongPtrW, hWnd, lParam);
          case 5u:
LABEL_97:
            Rect = 0;
            if ( Msg == 4095 )
            {
              GetClientRect(*(HWND *)WindowLongPtrW, &Rect);
            }
            else
            {
              Rect.right = (__int16)lParam;
              Rect.bottom = SWORD1(lParam);
            }
            return MCSizeHandler(WindowLongPtrW, &Rect);
          case 0xAu:
            v15 = wParam != 0;
            if ( ((*(_DWORD *)(WindowLongPtrW + 2392) >> 1) & 1) == v15 )
              return v4;
            *(_DWORD *)(WindowLongPtrW + 2392) = (2 * v15) | *(_DWORD *)(WindowLongPtrW + 2392) & 0xFFFFFFFD;
LABEL_22:
            InvalidateRect(*(HWND *)WindowLongPtrW, 0, 1);
            return v4;
          case 0xFu:
LABEL_92:
            if ( wParam )
            {
              MCPaint(WindowLongPtrW, (HDC)wParam);
            }
            else
            {
              memset(&Paint, 0, sizeof(Paint));
              v24 = BeginPaint(*(HWND *)WindowLongPtrW, &Paint);
              MCPaint(WindowLongPtrW, v24);
              EndPaint(*(HWND *)WindowLongPtrW, &Paint);
            }
            return 0;
          case 0x14u:
            return (unsigned int)MCHandleEraseBkgnd(WindowLongPtrW, wParam);
          default:
LABEL_210:
            if ( (unsigned int)CCWndProc(WindowLongPtrW, Msg, wParam, v14, (__int64)&Rect) )
              return *(_QWORD *)&Rect.left;
            return DefWindowProcW(hWnd, Msg, v51, lParam);
        }
      }
      switch ( Msg )
      {
        case 0x1Au:
          InitGlobalMetrics(wParam);
          if ( lParam && StrCmpICW((LPCWSTR)lParam, L"Intl") )
          {
            if ( wParam && wParam != 42 )
              return v4;
          }
          else
          {
            UpdateLocaleInfo(WindowLongPtrW, WindowLongPtrW + 56);
            MCReloadMenus(WindowLongPtrW);
            InvalidateRect(hWnd, 0, 1);
          }
          MCCalcSizes(WindowLongPtrW);
          v20 = 0;
          v21 = 4095;
          break;
        case 0x1Fu:
          v20 = 0xFFFFFFFFLL;
          v21 = 514;
          break;
        case 0x30u:
          MCHandleSetFont(WindowLongPtrW, (HGDIOBJ)wParam, (unsigned __int16)lParam);
          MCSizeHandler(WindowLongPtrW, WindowLongPtrW + 2132);
          goto LABEL_43;
        case 0x31u:
          return *(_QWORD *)(WindowLongPtrW + 1672);
        case 0x4Eu:
          if ( *(_DWORD *)(lParam + 16) == -722 && *(_QWORD *)lParam == *(_QWORD *)(WindowLongPtrW + 1648) )
          {
            v17 = *(unsigned __int16 *)(WindowLongPtrW + 1820);
            v18 = *(unsigned __int16 *)(WindowLongPtrW + 1768);
            if ( v17 + *(_DWORD *)(lParam + 28) >= v18 )
              v18 = v17 + *(_DWORD *)(lParam + 28);
            v19 = *(unsigned __int16 *)(WindowLongPtrW + 1784);
            if ( v18 <= v19 )
              v19 = v18;
            *(_WORD *)(WindowLongPtrW + 1820) = v19;
            if ( v19 != v17 )
            {
              if ( !(unsigned int)FIncrStartMonth(WindowLongPtrW, 12 * (v19 - v17), 0) )
                MessageBeep(0);
              MCNotifySelChange(WindowLongPtrW, 4294966547LL);
            }
          }
          return v4;
        default:
          goto LABEL_210;
      }
      PostMessageW(*(HWND *)WindowLongPtrW, v21, 0, v20);
      return v4;
    }
    if ( Msg > 0x101 )
    {
      switch ( Msg )
      {
        case 0x113u:
          MCHandleTimer(WindowLongPtrW, wParam);
          return v4;
        case 0x115u:
          MCUpdateEditYear(WindowLongPtrW);
          return v4;
        case 0x200u:
          MCMouseMove(WindowLongPtrW, v12, lParam);
          return v4;
        case 0x201u:
          MCLButtonDown(WindowLongPtrW, wParam, lParam);
          return v4;
        case 0x202u:
          MCLButtonUp(WindowLongPtrW, v12, lParam);
          return v4;
      }
      goto LABEL_210;
    }
    switch ( Msg )
    {
      case 0x101u:
        v23 = wParam - 16;
        if ( v23 )
        {
          if ( v23 == 1 )
            *(_DWORD *)(WindowLongPtrW + 2348) = 0;
        }
        else
        {
          *(_DWORD *)(WindowLongPtrW + 2352) = 0;
        }
        return v4;
      case 0x7Bu:
        MCContextMenu(WindowLongPtrW, v12, lParam);
        return v4;
      case 0x7Cu:
        if ( (_DWORD)wParam == -16 )
          *(_DWORD *)(lParam + 4) ^= (*(_DWORD *)(WindowLongPtrW + 16) ^ *(_DWORD *)(lParam + 4)) & 0xFE03;
        return v4;
    }
    if ( Msg != 125 )
    {
      if ( Msg == 130 )
      {
        _InterlockedDecrement(&g_dwWindowCount);
        MCNcDestroyHandler(hWnd, (HLOCAL)WindowLongPtrW);
        return v4;
      }
      if ( Msg == 256 )
      {
        MCHandleKeydown(WindowLongPtrW, wParam);
        return v4;
      }
      goto LABEL_210;
    }
    if ( (_DWORD)wParam == -16 )
    {
      v22 = *(_DWORD *)(WindowLongPtrW + 16) ^ *(_DWORD *)(lParam + 4);
      *(_DWORD *)(WindowLongPtrW + 16) = *(_DWORD *)(lParam + 4);
      if ( (v22 & 4) != 0 )
      {
        MCCalcSizes(WindowLongPtrW);
        MCUpdateRcDayCur(WindowLongPtrW, WindowLongPtrW + 1820);
      }
      if ( (v22 & 0x1C) != 0 )
        MCUpdateToday(WindowLongPtrW);
      if ( (v22 & 0xC40000) != 0 )
        PostMessageW(*(HWND *)WindowLongPtrW, 0xFFFu, 0, 0);
      if ( !v22 )
        return v4;
      goto LABEL_22;
    }
    if ( (_DWORD)wParam != -20 || ((*(_DWORD *)lParam ^ *(_DWORD *)(lParam + 4)) & 0x400000) == 0 )
      return v4;
LABEL_43:
    MCUpdateMonthNamePos(WindowLongPtrW);
    return v4;
  }
  v9 = LocalAlloc(0x40u, 0xA50u);
  if ( !v9 )
    return 0;
  SetWindowLongPtrW(hWnd, 0, (LONG_PTR)v9);
  return 1;
}

```

## disassembly

```asm
0x180046d90  push    rbp
0x180046d92  push    rbx
0x180046d93  push    rsi
0x180046d94  push    rdi
0x180046d95  push    r12
0x180046d97  push    r13
0x180046d99  push    r14
0x180046d9b  push    r15
0x180046d9d  lea     rbp, [rsp-1Fh]
0x180046da2  sub     rsp, 0B8h
0x180046da9  mov     rax, cs:__security_cookie
0x180046db0  xor     rax, rsp
0x180046db3  mov     [rbp+57h+var_50], rax
0x180046db7  xor     r15d, r15d
0x180046dba  mov     rsi, r9
0x180046dbd  mov     qword ptr [rbp+57h+Rect.left], r15
0x180046dc1  mov     r14, r8
0x180046dc4  mov     r13d, edx
0x180046dc7  mov     r12, rcx
0x180046dca  cmp     edx, 81h
0x180046dd0  jnz     short loc_180046E05
0x180046dd2  mov     edx, 0A50h; uBytes
0x180046dd7  lea     ecx, [r13-41h]; uFlags
0x180046ddb  call    cs:__imp_LocalAlloc
0x180046de1  test    rax, rax
0x180046de4  jnz     short loc_180046DEA
0x180046de6  xor     ebx, ebx
0x180046de8  jmp     short loc_180046DFD
0x180046dea  mov     r8, rax; dwNewLong
0x180046ded  xor     edx, edx; nIndex
0x180046def  mov     rcx, r12; hWnd
0x180046df2  call    cs:__imp_SetWindowLongPtrW
0x180046df8  mov     ebx, 1
0x180046dfd  mov     rax, rbx
0x180046e00  jmp     loc_180047B15
0x180046e05  xor     edx, edx; nIndex
0x180046e07  call    cs:__imp_GetWindowLongPtrW
0x180046e0d  mov     rdi, rax
0x180046e10  test    rax, rax
0x180046e13  jnz     short loc_180046E2C
0x180046e15  mov     r9, rsi; lParam
0x180046e18  mov     r8, r14; wParam
0x180046e1b  mov     edx, r13d; Msg
0x180046e1e  mov     rcx, r12; hWnd
0x180046e21  call    cs:__imp_DefWindowProcW
0x180046e27  jmp     loc_180047B15
0x180046e2c  mov     eax, 318h
0x180046e31  cmp     r13d, eax
0x180046e34  ja      loc_180047281
0x180046e3a  jz      loc_180047234
0x180046e40  cmp     r13d, 55h ; 'U'
0x180046e44  ja      loc_18004707B
0x180046e4a  jz      loc_18004706B
0x180046e50  cmp     r13d, 15h
0x180046e54  ja      loc_180046F01
0x180046e5a  jz      loc_180046EF7
0x180046e60  mov     eax, r13d
0x180046e63  sub     eax, 1
0x180046e66  jz      short loc_180046EDC
0x180046e68  sub     eax, 4
0x180046e6b  jz      loc_1800472A9; jumptable 00000001800472A7 case 4095
0x180046e71  sub     eax, 5
0x180046e74  jz      short loc_180046E9A
0x180046e76  sub     eax, 5
0x180046e79  jz      loc_180047234
0x180046e7f  cmp     eax, 5
0x180046e82  jnz     def_1800472A7; jumptable 00000001800472A7 default case, case 4096
0x180046e88  mov     rdx, r14
0x180046e8b  mov     rcx, rdi
0x180046e8e  call    MCHandleEraseBkgnd
0x180046e93  mov     eax, eax
0x180046e95  jmp     loc_180047B15
0x180046e9a  mov     ecx, [rdi+958h]
0x180046ea0  xor     edx, edx
0x180046ea2  test    r14, r14
0x180046ea5  mov     eax, ecx
0x180046ea7  mov     ebx, 1
0x180046eac  setnz   dl
0x180046eaf  shr     eax, 1
0x180046eb1  and     eax, ebx
0x180046eb3  cmp     eax, edx
0x180046eb5  jz      loc_180047B12
0x180046ebb  and     ecx, 0FFFFFFFDh
0x180046ebe  lea     eax, [rdx+rdx]
0x180046ec1  or      ecx, eax
0x180046ec3  mov     r8d, ebx; bErase
0x180046ec6  mov     [rdi+958h], ecx
0x180046ecc  mov     rcx, [rdi]; hWnd
0x180046ecf  xor     edx, edx; lpRect
0x180046ed1  call    cs:__imp_InvalidateRect
0x180046ed7  jmp     loc_180047B12
0x180046edc  call    CCCreateWindow
0x180046ee1  mov     r8, rsi
0x180046ee4  mov     rdx, r12
0x180046ee7  mov     rcx, rdi
0x180046eea  call    MCCreateHandler
0x180046eef  mov     r15, rax
0x180046ef2  jmp     loc_180047B12
0x180046ef7  call    InitGlobalColors
0x180046efc  jmp     loc_180047B12
0x180046f01  mov     eax, r13d
0x180046f04  sub     eax, 1Ah
0x180046f07  jz      loc_180047005
0x180046f0d  sub     eax, 5
0x180046f10  jz      loc_180046FE9
0x180046f16  sub     eax, 11h
0x180046f19  jz      loc_180046FBE
0x180046f1f  sub     eax, 1
0x180046f22  jz      loc_180046FB2
0x180046f28  cmp     eax, 1Dh
0x180046f2b  jnz     def_1800472A7; jumptable 00000001800472A7 default case, case 4096
0x180046f31  cmp     dword ptr [rsi+10h], 0FFFFFD2Eh
0x180046f38  jnz     loc_180047B12
0x180046f3e  mov     rax, [rdi+670h]
0x180046f45  cmp     [rsi], rax
0x180046f48  jnz     loc_180047B12
0x180046f4e  movzx   edx, word ptr [rdi+71Ch]
0x180046f55  mov     ecx, [rsi+1Ch]
0x180046f58  movzx   eax, word ptr [rdi+6E8h]
0x180046f5f  add     ecx, edx
0x180046f61  cmp     ecx, eax
0x180046f63  cmovnb  eax, ecx
0x180046f66  movzx   ecx, word ptr [rdi+6F8h]
0x180046f6d  cmp     eax, ecx
0x180046f6f  cmovbe  ecx, eax
0x180046f72  mov     eax, ecx
0x180046f74  mov     [rdi+71Ch], cx
0x180046f7b  sub     eax, edx
0x180046f7d  jz      loc_180047B12
0x180046f83  lea     edx, [rax+rax*2]
0x180046f86  xor     r8d, r8d
0x180046f89  shl     edx, 2
0x180046f8c  mov     rcx, rdi
0x180046f8f  call    FIncrStartMonth
0x180046f94  test    eax, eax
0x180046f96  jnz     short loc_180046FA0
0x180046f98  xor     ecx, ecx; uType
0x180046f9a  call    cs:__imp_MessageBeep
0x180046fa0  mov     edx, 0FFFFFD13h
0x180046fa5  mov     rcx, rdi
0x180046fa8  call    MCNotifySelChange
0x180046fad  jmp     loc_180047B12
0x180046fb2  mov     r15, [rdi+688h]
0x180046fb9  jmp     loc_180047B12
0x180046fbe  movzx   r8d, si
0x180046fc2  mov     rdx, r14
0x180046fc5  mov     rcx, rdi
0x180046fc8  call    MCHandleSetFont
0x180046fcd  lea     rdx, [rdi+854h]
0x180046fd4  mov     rcx, rdi
0x180046fd7  call    MCSizeHandler
0x180046fdc  mov     rcx, rdi
0x180046fdf  call    MCUpdateMonthNamePos
0x180046fe4  jmp     loc_180047B12
0x180046fe9  mov     r9d, 0FFFFFFFFh; lParam
0x180046fef  mov     edx, 202h; Msg
0x180046ff4  mov     rcx, [rdi]; hWnd
0x180046ff7  xor     r8d, r8d; wParam
0x180046ffa  call    cs:__imp_PostMessageW
0x180047000  jmp     loc_180047B12
0x180047005  mov     rcx, r14
0x180047008  call    InitGlobalMetrics
0x18004700d  test    rsi, rsi
0x180047010  jz      short loc_180047036
0x180047012  lea     rdx, aIntl; "Intl"
0x180047019  mov     rcx, rsi; pszStr1
0x18004701c  call    StrCmpICW
0x180047021  test    eax, eax
0x180047023  jz      short loc_180047036
0x180047025  test    r14, r14
0x180047028  jz      short loc_180047059
0x18004702a  cmp     r14, 2Ah ; '*'
0x18004702e  jnz     loc_180047B12
0x180047034  jmp     short loc_180047059
0x180047036  lea     rdx, [rdi+38h]
0x18004703a  mov     rcx, rdi
0x18004703d  call    UpdateLocaleInfo
0x180047042  mov     rcx, rdi
0x180047045  call    MCReloadMenus
0x18004704a  xor     edx, edx; lpRect
0x18004704c  mov     rcx, r12; hWnd
0x18004704f  lea     r8d, [rdx+1]; bErase
0x180047053  call    cs:__imp_InvalidateRect
0x180047059  mov     rcx, rdi
0x18004705c  call    MCCalcSizes
0x180047061  xor     r9d, r9d
0x180047064  mov     edx, 0FFFh
0x180047069  jmp     short loc_180046FF4
0x18004706b  mov     rdx, rsi
0x18004706e  mov     rcx, rdi
0x180047071  call    CIHandleNotifyFormat
0x180047076  jmp     loc_180047B15
0x18004707b  mov     eax, 101h
0x180047080  cmp     r13d, eax
0x180047083  ja      loc_1800471C0
0x180047089  jz      loc_180047198
0x18004708f  mov     eax, r13d
0x180047092  sub     eax, 7Bh ; '{'
0x180047095  jz      loc_180047188
0x18004709b  sub     eax, 1
0x18004709e  jz      loc_18004716B
0x1800470a4  sub     eax, 1
0x1800470a7  jz      short loc_1800470E4
0x1800470a9  sub     eax, 5
0x1800470ac  jz      short loc_1800470C7
0x1800470ae  cmp     eax, 7Eh ; '~'
0x1800470b1  jnz     def_1800472A7; jumptable 00000001800472A7 default case, case 4096
0x1800470b7  mov     rdx, r14
0x1800470ba  mov     rcx, rdi
0x1800470bd  call    MCHandleKeydown
0x1800470c2  jmp     loc_180047B12
0x1800470c7  lock dec cs:g_dwWindowCount
0x1800470ce  mov     r9, rsi
0x1800470d1  mov     r8, r14
0x1800470d4  mov     rdx, rdi; hMem
0x1800470d7  mov     rcx, r12; hWnd
0x1800470da  call    MCNcDestroyHandler
0x1800470df  jmp     loc_180047B12
0x1800470e4  cmp     r14d, 0FFFFFFF0h
0x1800470e8  jnz     short loc_18004714D
0x1800470ea  mov     eax, [rsi+4]
0x1800470ed  mov     ebx, eax
0x1800470ef  xor     ebx, [rdi+10h]
0x1800470f2  mov     [rdi+10h], eax
0x1800470f5  test    bl, 4
0x1800470f8  jz      short loc_180047111
0x1800470fa  mov     rcx, rdi
0x1800470fd  call    MCCalcSizes
0x180047102  lea     rdx, [rdi+71Ch]
0x180047109  mov     rcx, rdi
0x18004710c  call    MCUpdateRcDayCur
0x180047111  test    bl, 1Ch
0x180047114  jz      short loc_18004711E
0x180047116  mov     rcx, rdi
0x180047119  call    MCUpdateToday
0x18004711e  test    ebx, 0C40000h
0x180047124  jz      short loc_18004713A
0x180047126  mov     rcx, [rdi]; hWnd
0x180047129  xor     r9d, r9d; lParam
0x18004712c  xor     r8d, r8d; wParam
0x18004712f  mov     edx, 0FFFh; Msg
0x180047134  call    cs:__imp_PostMessageW
0x18004713a  test    ebx, ebx
0x18004713c  jz      loc_180047B12
0x180047142  mov     r8d, 1
0x180047148  jmp     loc_180046ECC
0x18004714d  cmp     r14d, 0FFFFFFECh
0x180047151  jnz     loc_180047B12
0x180047157  mov     eax, [rsi+4]
0x18004715a  xor     eax, [rsi]
0x18004715c  bt      eax, 16h
0x180047160  jnb     loc_180047B12
0x180047166  jmp     loc_180046FDC
0x18004716b  cmp     r14d, 0FFFFFFF0h
0x18004716f  jnz     loc_180047B12
0x180047175  mov     eax, [rsi+4]
0x180047178  xor     eax, [rdi+10h]
0x18004717b  and     eax, 0FE03h
0x180047180  xor     [rsi+4], eax
0x180047183  jmp     loc_180047B12
0x180047188  mov     r8, rsi
0x18004718b  mov     rcx, rdi
0x18004718e  call    MCContextMenu
0x180047193  jmp     loc_180047B12
0x180047198  sub     r14, 10h
0x18004719c  jz      short loc_1800471B4
0x18004719e  cmp     r14, 1
0x1800471a2  jnz     loc_180047B12
0x1800471a8  mov     [rdi+92Ch], r15d
0x1800471af  jmp     loc_180047B12
0x1800471b4  mov     [rdi+930h], r15d
0x1800471bb  jmp     loc_180047B12
0x1800471c0  mov     eax, r13d
0x1800471c3  sub     eax, 113h
0x1800471c8  jz      short loc_180047224
0x1800471ca  sub     eax, 2
0x1800471cd  jz      short loc_180047217
0x1800471cf  sub     eax, 0EBh
0x1800471d4  jz      short loc_180047207
0x1800471d6  sub     eax, 1
0x1800471d9  jz      short loc_1800471F4
0x1800471db  cmp     eax, 1
0x1800471de  jnz     def_1800472A7; jumptable 00000001800472A7 default case, case 4096
0x1800471e4  mov     r8, rsi
0x1800471e7  mov     rcx, rdi
0x1800471ea  call    MCLButtonUp
0x1800471ef  jmp     loc_180047B12
0x1800471f4  mov     r8, rsi
0x1800471f7  mov     rdx, r14
0x1800471fa  mov     rcx, rdi
0x1800471fd  call    MCLButtonDown
0x180047202  jmp     loc_180047B12
0x180047207  mov     r8, rsi
0x18004720a  mov     rcx, rdi
0x18004720d  call    MCMouseMove
0x180047212  jmp     loc_180047B12
0x180047217  mov     rcx, rdi
0x18004721a  call    MCUpdateEditYear
0x18004721f  jmp     loc_180047B12
0x180047224  mov     rdx, r14
  ... truncated ...
```
