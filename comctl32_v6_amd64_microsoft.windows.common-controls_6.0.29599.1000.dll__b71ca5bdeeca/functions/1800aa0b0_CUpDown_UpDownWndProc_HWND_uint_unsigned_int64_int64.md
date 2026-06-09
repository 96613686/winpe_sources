# CUpDown::UpDownWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800aa0b0`
- end: `0x1800aaa61`
- name: `?UpDownWndProc@CUpDown@@IEAA_JPEAUHWND__@@I_K_J@Z`
- size: `2481`
- prototype: `__int64 __fastcall(CUpDown *__hidden this, HWND hWnd, UINT Msg, HDC, LPARAM lParam)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800a9f80`

## callees

- `0x180005914`
- `0x180005b30`
- `0x180026340`
- `0x18006a640`
- `0x1800aa0b0`
- `0x1800d4364`
- `0x1800db5f8`
- `0x1800ed220`
- `0x180114520`
- `0x180114ebc`
- `0x180117828`
- `0x1801179d8`
- `0x180117a9c`
- `0x180117c6c`
- `0x180117d08`
- `0x180117dac`
- `0x180117e3c`
- `0x180117e94`
- `0x1801182ac`
- `0x18011840c`
- `0x180118718`
- `0x1801187e0`
- `0x1801188a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aa43b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aa4bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aa43b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aa4bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aa449`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aa449`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800aa84a`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800aa84a`
- `USER32!IsWindowVisible` at `0x1800aa3b2`
- `USER32!IsWindowVisible` at `0x1800aa3b2`
- `USER32!RemovePropW` at `0x1800aa459`
- `USER32!RemovePropW` at `0x1800aa459`
- `USER32!GetCapture` at `0x1800aa568`
- `USER32!GetCapture` at `0x1800aa6ac`
- `USER32!GetCapture` at `0x1800aa568`
- `USER32!GetCapture` at `0x1800aa6ac`
- `USER32!SetTimer` at `0x1800aa585`
- `USER32!SetTimer` at `0x1800aa7ce`
- `USER32!SetTimer` at `0x1800aa585`
- `USER32!SetTimer` at `0x1800aa7ce`
- `USER32!TrackMouseEvent` at `0x1800aa2da`
- `USER32!TrackMouseEvent` at `0x1800aa2da`
- `USER32!IsWindowEnabled` at `0x1800aa69e`
- `USER32!IsWindowEnabled` at `0x1800aa730`
- `USER32!IsWindowEnabled` at `0x1800aa69e`
- `USER32!IsWindowEnabled` at `0x1800aa730`
- `USER32!SetFocus` at `0x1800aa762`
- `USER32!SetFocus` at `0x1800aa762`
- `USER32!SetPropW` at `0x1800aa559`
- `USER32!SetPropW` at `0x1800aa559`
- `USER32!SetCapture` at `0x1800aa741`
- `USER32!SetCapture` at `0x1800aa741`
- `USER32!GetCaretBlinkTime` at `0x1800aa7b1`
- `USER32!GetCaretBlinkTime` at `0x1800aa7b1`
- `USER32!KillTimer` at `0x1800aa6d6`
- `USER32!KillTimer` at `0x1800aa6d6`
- `USER32!ReleaseCapture` at `0x1800aa6c8`
- `USER32!ReleaseCapture` at `0x1800aa6c8`
- `USER32!GetCursorPos` at `0x1800aa615`
- `USER32!GetCursorPos` at `0x1800aa615`
- `USER32!DefWindowProcW` at `0x1800aa179`
- `USER32!DefWindowProcW` at `0x1800aa179`
- `USER32!GetWindowRect` at `0x1800aa592`
- `USER32!GetWindowRect` at `0x1800aa592`
- `USER32!InflateRect` at `0x1800aa60b`
- `USER32!InflateRect` at `0x1800aa60b`
- `USER32!SendMessageW` at `0x1800aa6f2`
- `USER32!SendMessageW` at `0x1800aa71c`
- `USER32!SendMessageW` at `0x1800aa6f2`
- `USER32!SendMessageW` at `0x1800aa71c`
- `USER32!PtInRect` at `0x1800aa623`
- `USER32!PtInRect` at `0x1800aa623`
- `USER32!InvalidateRect` at `0x1800aa3f5`
- `USER32!InvalidateRect` at `0x1800aa3f5`
- `USER32!BeginPaint` at `0x1800aa3a6`
- `USER32!BeginPaint` at `0x1800aa3a6`
- `USER32!EndPaint` at `0x1800aa3e1`
- `USER32!EndPaint` at `0x1800aa3e1`
- `USER32!GetSystemMetricsForDpi` at `0x1800aa5e0`
- `USER32!GetSystemMetricsForDpi` at `0x1800aa5f6`
- `USER32!GetSystemMetricsForDpi` at `0x1800aa5e0`
- `USER32!GetSystemMetricsForDpi` at `0x1800aa5f6`
- `USER32!NotifyWinEvent` at `0x1800aa9fb`
- `USER32!NotifyWinEvent` at `0x1800aa9fb`
- `UxTheme!OpenThemeData` at `0x1800aa481`
- `UxTheme!OpenThemeData` at `0x1800aa481`
- `UxTheme!CloseThemeData` at `0x1800aa40c`
- `UxTheme!CloseThemeData` at `0x1800aa425`
- `UxTheme!CloseThemeData` at `0x1800aa40c`
- `UxTheme!CloseThemeData` at `0x1800aa425`

## pseudocode

```c
unsigned __int64 __fastcall CUpDown::UpDownWndProc(
        CUpDown *this,
        HWND hWnd,
        UINT Msg,
        unsigned __int64 a4,
        int *lParam)
{
  int v5; // r14d
  HDC v6; // rbx
  unsigned __int64 result; // rax
  unsigned __int64 v11; // rax
  DPISCALEINFO *v12; // rcx
  int v13; // eax
  __int64 v14; // rax
  HDC v15; // rsi
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rbx
  HANDLE v19; // rax
  HWND v20; // rcx
  HANDLE ProcessHeap; // rax
  _DWORD *v22; // rax
  int v23; // r8d
  int v24; // ebx
  int SystemMetricsForDpi; // eax
  HWND v26; // rcx
  UINT v27; // edx
  HWND v28; // rcx
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // r8d
  unsigned int v32; // edx
  UINT CaretBlinkTime; // eax
  HLOCAL v34; // rax
  int j; // r8d
  __int64 v36; // rdx
  unsigned __int16 Pos; // ax
  int v38; // r8d
  unsigned int v39; // r9d
  unsigned int v40; // r9d
  int v41; // r10d
  int v42; // r11d
  int v43; // r10d
  int v44; // r11d
  int i; // r8d
  __int64 v46; // rdx
  unsigned int v47; // r9d
  int v48; // r10d
  int v49; // r11d
  int v50; // r11d
  __int64 v51; // rbx
  unsigned int v52; // esi
  struct tagTRACKMOUSEEVENT EventTrack; // [rsp+20h] [rbp-81h] BYREF
  struct tagPOINT Point; // [rsp+38h] [rbp-69h] BYREF
  struct tagRECT Rect; // [rsp+40h] [rbp-61h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+50h] [rbp-51h] BYREF

  v5 = (int)lParam;
  Point.x = 0;
  v6 = (HDC)a4;
  Rect = 0;
  if ( Msg - 512 <= 0xE )
  {
    if ( (*((_DWORD *)this + 4) & 0x100) != 0 )
    {
      v13 = *((_DWORD *)this + 18);
      if ( (v13 & 0x40) == 0 )
      {
        *(_QWORD *)&EventTrack.dwHoverTime = 0;
        *((_DWORD *)this + 18) = v13 | 0x40;
        EventTrack.hwndTrack = *(HWND *)this;
        EventTrack.cbSize = 24;
        EventTrack.dwFlags = 2;
        TrackMouseEvent(&EventTrack);
      }
    }
    goto LABEL_41;
  }
  if ( Msg <= 0x31A )
  {
    if ( Msg == 794 )
      goto LABEL_91;
    if ( Msg <= 0x113 )
    {
      if ( Msg != 275 )
      {
        switch ( Msg )
        {
          case 1u:
            CIInitialize(this);
            v20 = *(HWND *)this;
            *((_QWORD *)this + 56) = -1;
            *((_QWORD *)this + 16) = OpenThemeData(v20, L"Spin");
            if ( (lParam[12] & 0x200) != 0 )
              *((_DWORD *)this + 18) |= 4u;
            if ( (lParam[18] & 0x200) != 0 )
              *((_DWORD *)this + 18) |= 0x10u;
            *(_QWORD *)((char *)this + 76) = 10;
            *(_QWORD *)((char *)this + 84) = 100;
            *((_QWORD *)this + 8) = 0;
            *((_DWORD *)this + 23) = 0;
            ProcessHeap = GetProcessHeap();
            v22 = (_DWORD *)CCHeapAllocArraySize(ProcessHeap, 8, 8, 3);
            *((_QWORD *)this + 14) = v22;
            if ( v22 )
            {
              *((_DWORD *)this + 26) = 3;
              *v22 = 0;
              *(_DWORD *)(*((_QWORD *)this + 14) + 4LL) = 1;
              *(_DWORD *)(*((_QWORD *)this + 14) + 8LL) = 2;
              *(_DWORD *)(*((_QWORD *)this + 14) + 12LL) = 5;
              *(_DWORD *)(*((_QWORD *)this + 14) + 16LL) = 5;
              *(_DWORD *)(*((_QWORD *)this + 14) + 20LL) = 20;
            }
            else
            {
              *((_DWORD *)this + 26) = 0;
            }
            CUpDown::SetBuddy(this, 0);
            CUpDown::SetPos(this);
            if ( *((_QWORD *)this + 16) )
              *((_DWORD *)this + 4) |= 0x100u;
            SetPropW(hWnd, (LPCWSTR)(unsigned __int16)g_atomTabletPcPenService, (HANDLE)0x10001);
            return 0;
          case 2u:
            v16 = (void *)*((_QWORD *)this + 16);
            if ( v16 )
            {
              CloseThemeData(v16);
              *((_QWORD *)this + 16) = 0;
            }
            v17 = (void *)*((_QWORD *)this + 17);
            if ( v17 )
            {
              CloseThemeData(v17);
              *((_QWORD *)this + 17) = 0;
            }
            v18 = (void *)*((_QWORD *)this + 14);
            if ( v18 )
            {
              v19 = GetProcessHeap();
              HeapFree(v19, 0, v18);
            }
            RemovePropW(hWnd, (LPCWSTR)(unsigned __int16)g_atomTabletPcPenService);
            return 0;
          case 0xAu:
            InvalidateRect(hWnd, 0, 1);
            return 0;
          case 0xFu:
            memset_0(&Paint, 0, sizeof(Paint));
            if ( v6 )
              v15 = v6;
            else
              v15 = BeginPaint(hWnd, &Paint);
            if ( IsWindowVisible(*(HWND *)this) )
              CUpDown::OnPaint(this, v15, v6 == 0);
            if ( !v6 )
              EndPaint(hWnd, &Paint);
            return 0;
          case 0x1Au:
            if ( a4 <= 0x2A )
            {
              v14 = 0x40400000001LL;
              if ( _bittest64(&v14, a4) )
              {
                g_systemMetrics = 0;
                CUpDown::UnAnchor(this);
                CUpDown::Anchor(this);
              }
            }
            return 0;
          case 0x3Du:
            if ( (_DWORD)lParam == -12 )
              return 65558;
            break;
          case 0x55u:
            return CIHandleNotifyFormat(this, lParam);
        }
        return DefWindowProcW(hWnd, Msg, (WPARAM)v6, (LPARAM)lParam);
      }
      Point = 0;
      if ( GetCapture() == hWnd )
      {
        SetTimer(hWnd, 1u, 0x64u, 0);
        GetWindowRect(hWnd, &Rect);
        v23 = *((_DWORD *)this + 24);
        if ( (*((_BYTE *)this + 16) & 0x40) != 0 )
        {
          if ( v23 )
            Rect.right = (Rect.right + Rect.left) / 2;
          else
            Rect.left = (Rect.right + Rect.left) / 2;
        }
        else if ( v23 )
        {
          Rect.top = (Rect.top + Rect.bottom) / 2;
        }
        else
        {
          Rect.bottom = (Rect.top + Rect.bottom) / 2;
        }
        v24 = (int)(GetSystemMetricsForDpi(33, *((unsigned int *)this + 14)) + 1) / 2;
        SystemMetricsForDpi = GetSystemMetricsForDpi(32, *((unsigned int *)this + 13));
        InflateRect(&Rect, (SystemMetricsForDpi + 1) / 2, v24);
        GetCursorPos(&Point);
        if ( !PtInRect(&Rect, Point) )
        {
          CUpDown::Squish(this, 0, 0);
          return 0;
        }
        CUpDown::Squish(this, *((_DWORD *)this + 24) == 0, *((_DWORD *)this + 24));
LABEL_115:
        CUpDown::Bump(this);
        return 0;
      }
LABEL_96:
      CUpDown::Squish(this, 0, 0);
      ReleaseCapture();
      KillTimer(hWnd, 1u);
      if ( *((_DWORD *)this + 23) == 1 )
        SendMessageW(*((HWND *)this + 8), 0xB1u, 0, -1);
      v27 = 276;
      if ( (*((_BYTE *)this + 16) & 0x40) == 0 )
        v27 = 277;
      SendMessageW(
        *((HWND *)this + 1),
        v27,
        ((unsigned __int64)*((unsigned __int16 *)this + 44) << 16) | 8,
        *(_QWORD *)this);
      return 0;
    }
LABEL_41:
    if ( Msg == 296 )
    {
      CCOnUIState(this, hWnd, v6);
      return DefWindowProcW(hWnd, Msg, (WPARAM)v6, (LPARAM)lParam);
    }
    if ( Msg == 512 )
    {
      CUpDown::OnMouseMove(this, (unsigned int)lParam);
      return 0;
    }
    if ( Msg != 513 )
    {
      if ( Msg == 514 )
      {
        v26 = (HWND)*((_QWORD *)this + 8);
        if ( v26 && !IsWindowEnabled(v26) || GetCapture() != hWnd )
          return 0;
        goto LABEL_96;
      }
      if ( Msg == 675 )
      {
        *((_DWORD *)this + 18) &= ~0x40u;
        CUpDown::Invalidate(this, *((_DWORD *)this + 30), Msg);
        *((_DWORD *)this + 30) = 0;
        return 0;
      }
      if ( Msg != 738 )
      {
        if ( Msg == 792 )
        {
          CUpDown::OnPaint(this, v6, 0);
          return 0;
        }
        return DefWindowProcW(hWnd, Msg, (WPARAM)v6, (LPARAM)lParam);
      }
      if ( !(unsigned int)DPISCALEINFO::HandleDPIChanged((char *)this + 52, hWnd, 29) )
        return 0;
LABEL_91:
      CUpDown::UpdateTheme(this);
      return 0;
    }
    v28 = (HWND)*((_QWORD *)this + 8);
    if ( v28 && !IsWindowEnabled(v28) )
      return 0;
    SetCapture(hWnd);
    CUpDown::GetPos(this, 0);
    if ( *((_DWORD *)this + 23) == 1 || *((_DWORD *)this + 23) == 2 )
      SetFocus(*((HWND *)this + 8));
    v29 = CUpDown::HitTest(this, (__int16)lParam, SWORD1(lParam));
    if ( !v29 )
      return 0;
    v30 = v29 - 1;
    if ( v30 )
    {
      if ( v30 != 1 )
      {
LABEL_112:
        CaretBlinkTime = GetCaretBlinkTime();
        if ( CaretBlinkTime >= 0x514 )
          CaretBlinkTime = 1300;
        SetTimer(hWnd, 1u, CaretBlinkTime, 0);
        goto LABEL_115;
      }
      *((_DWORD *)this + 24) = 0;
      v31 = 0;
      v32 = 1;
    }
    else
    {
      v32 = 0;
      *((_DWORD *)this + 24) = 1;
      v31 = 1;
    }
    CUpDown::Squish(this, v32, v31);
    goto LABEL_112;
  }
  if ( Msg <= 0x46C )
  {
    switch ( Msg )
    {
      case 0x46Cu:
        if ( a4 > *((unsigned int *)this + 26) )
          LODWORD(v6) = *((_DWORD *)this + 26);
        if ( *((_QWORD *)this + 14) )
        {
          if ( lParam )
          {
            for ( i = 0; i < (int)v6; *(_QWORD *)&lParam[2 * v46] = *(_QWORD *)(*((_QWORD *)this + 14) + 8 * v46) )
              v46 = (unsigned int)i++;
          }
        }
        return *((unsigned int *)this + 26);
      case 0x465u:
        *((_DWORD *)this + 20) = (__int16)lParam;
        *((_DWORD *)this + 21) = SWORD1(lParam);
        CUpDown::Nudge(this);
        return 0;
      case 0x466u:
        return (*((unsigned __int16 *)this + 42) << 16) | *((unsigned __int16 *)this + 40);
      case 0x467u:
        v5 = (__int16)lParam;
        goto LABEL_138;
      case 0x468u:
        Pos = CUpDown::GetPos(this, (int *)&Point);
        return Pos | (unsigned __int64)(LOWORD(Point.x) << 16);
      case 0x469u:
        return CUpDown::SetBuddy(this, (HWND)a4);
      case 0x46Au:
        return *((_QWORD *)this + 8);
      case 0x46Bu:
        if ( !a4 || !lParam )
          return 0;
        if ( a4 < 3 )
        {
LABEL_128:
          if ( *((_QWORD *)this + 14) )
          {
            *((_DWORD *)this + 26) = (_DWORD)v6;
            for ( j = 0; j < (int)v6; *(_QWORD *)(*((_QWORD *)this + 14) + 8 * v36) = *(_QWORD *)&lParam[2 * v36] )
              v36 = (unsigned int)j++;
          }
          return 1;
        }
        v34 = LocalReAlloc(*((HLOCAL *)this + 14), 8 * a4, 2u);
        if ( v34 )
        {
          *((_QWORD *)this + 14) = v34;
          goto LABEL_128;
        }
        return 0;
    }
    return DefWindowProcW(hWnd, Msg, (WPARAM)v6, (LPARAM)lParam);
  }
  switch ( Msg )
  {
    case 0x46Du:
      if ( (_DWORD)a4 == 10 || (v52 = 0, (_DWORD)a4 == 16) )
      {
        *((_DWORD *)this + 18) &= ~4u;
        v52 = *((_DWORD *)this + 19);
        *((_DWORD *)this + 19) = a4;
        *((_DWORD *)this + 18) |= (_DWORD)a4 != 10 ? 4 : 0;
        CUpDown::SetPos(this);
      }
      return v52;
    case 0x46Eu:
      return *((unsigned int *)this + 19);
    case 0x46Fu:
      *((_DWORD *)this + 20) = (_DWORD)lParam;
      *((_DWORD *)this + 21) = a4;
      return 0;
    case 0x470u:
      if ( lParam )
        *lParam = *((_DWORD *)this + 20);
      if ( a4 )
        *(_DWORD *)a4 = *((_DWORD *)this + 21);
      return 0;
    case 0x471u:
LABEL_138:
      if ( (int)CUpDown::Compare(this, *((_DWORD *)this + 21), *((_DWORD *)this + 20), 0) >= 0 )
      {
        if ( (int)CUpDown::Compare(this, v5, v38, v39) >= 0 )
          v48 = v5;
        if ( (int)CUpDown::Compare(this, v48, v49, v47) > 0 )
          v43 = v50;
      }
      else
      {
        if ( (int)CUpDown::Compare(this, v5, v38, v39) <= 0 )
          v41 = v5;
        if ( (int)CUpDown::Compare(this, v41, v42, v40) < 0 )
          v43 = v44;
      }
      v51 = *((int *)this + 22);
      *((_DWORD *)this + 22) = v43;
      CUpDown::SetPos(this);
      NotifyWinEvent(0x800Eu, *(HWND *)this, -4, 0);
      return v51;
    case 0x472u:
      return CUpDown::GetPos(this, lParam);
  }
  if ( Msg - 0x2000 > 0x1FF )
    return DefWindowProcW(hWnd, Msg, (WPARAM)v6, (LPARAM)lParam);
  result = 0;
  switch ( Msg )
  {
    case 0x2005u:
      result = *((_DWORD *)this + 6) & 1;
      *((_DWORD *)this + 6) = *((_DWORD *)this + 6) & 0xFFFFFFFE | (a4 != 0);
      return result;
    case 0x2006u:
      LODWORD(v11) = *((_DWORD *)this + 6);
      return v11 & 1;
    case 0x2007u:
    case 0x2008u:
      return 6;
    case 0x200Cu:
      *((_DWORD *)this + 15) ^= (*((_DWORD *)this + 15) ^ a4) & 1;
      return 1;
    case 0x200Du:
      v12 = (CUpDown *)((char *)this + 52);
      *((_DWORD *)v12 + 2) ^= (*((_DWORD *)v12 + 2) ^ (16 * a4)) & 0x10;
      DPISCALEINFO::EvaluateMagicNumberScaling(v12);
      return 1;
    case 0x200Eu:
      v11 = (unsigned __int64)*((unsigned int *)this + 15) >> 5;
      return v11 & 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800aa0b0  push    rbp
0x1800aa0b2  push    rbx
0x1800aa0b3  push    rsi
0x1800aa0b4  push    rdi
0x1800aa0b5  push    r12
0x1800aa0b7  push    r13
0x1800aa0b9  push    r14
0x1800aa0bb  push    r15
0x1800aa0bd  lea     rbp, [rsp-17h]
0x1800aa0c2  sub     rsp, 0B8h
0x1800aa0c9  mov     rax, cs:__security_cookie
0x1800aa0d0  xor     rax, rsp
0x1800aa0d3  mov     [rbp+4Fh+var_50], rax
0x1800aa0d7  mov     r14, [rbp+4Fh+lParam]
0x1800aa0db  lea     eax, [r8-200h]
0x1800aa0e2  xor     r13d, r13d
0x1800aa0e5  xorps   xmm0, xmm0
0x1800aa0e8  mov     [rbp+4Fh+Point.x], r13d
0x1800aa0ec  mov     rbx, r9
0x1800aa0ef  mov     esi, r8d
0x1800aa0f2  mov     r15, rdx
0x1800aa0f5  mov     rdi, rcx
0x1800aa0f8  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x1800aa0fc  cmp     eax, 0Eh
0x1800aa0ff  jbe     loc_1800AA2A2
0x1800aa105  mov     eax, 31Ah
0x1800aa10a  cmp     r8d, eax
0x1800aa10d  jbe     loc_1800AA19F
0x1800aa113  mov     eax, 46Ch
0x1800aa118  cmp     r8d, eax
0x1800aa11b  jbe     loc_1800AA206
0x1800aa121  mov     eax, r8d
0x1800aa124  sub     eax, 46Dh
0x1800aa129  jz      loc_1800AAA30
0x1800aa12f  sub     eax, 1
0x1800aa132  jz      loc_1800AAA28
0x1800aa138  sub     eax, 1
0x1800aa13b  jz      loc_1800AA88D
0x1800aa141  sub     eax, 1
0x1800aa144  jz      loc_1800AAA09
0x1800aa14a  sub     eax, 1
0x1800aa14d  jz      loc_1800AA8D0
0x1800aa153  cmp     eax, 1
0x1800aa156  jz      loc_1800AA9B0
0x1800aa15c  lea     eax, [r8-2000h]
0x1800aa163  cmp     eax, 1FFh
0x1800aa168  jbe     loc_1800AA236
0x1800aa16e  mov     r9, r14; lParam
0x1800aa171  mov     r8, rbx; wParam
0x1800aa174  mov     edx, esi; Msg
0x1800aa176  mov     rcx, r15; hWnd
0x1800aa179  call    cs:__imp_DefWindowProcW
0x1800aa17f  mov     rcx, [rbp+4Fh+var_50]
0x1800aa183  xor     rcx, rsp; StackCookie
0x1800aa186  call    __security_check_cookie
0x1800aa18b  add     rsp, 0B8h
0x1800aa192  pop     r15
0x1800aa194  pop     r14
0x1800aa196  pop     r13
0x1800aa198  pop     r12
0x1800aa19a  pop     rdi
0x1800aa19b  pop     rsi
0x1800aa19c  pop     rbx
0x1800aa19d  pop     rbp
0x1800aa19e  retn
0x1800aa19f  jz      loc_1800AA670
0x1800aa1a5  mov     eax, 113h
0x1800aa1aa  cmp     esi, eax
0x1800aa1ac  ja      loc_1800AA2E0
0x1800aa1b2  jz      loc_1800AA564
0x1800aa1b8  mov     eax, esi
0x1800aa1ba  sub     eax, 1
0x1800aa1bd  jz      loc_1800AA464
0x1800aa1c3  sub     eax, 1
0x1800aa1c6  jz      loc_1800AA400
0x1800aa1cc  sub     eax, 8
0x1800aa1cf  jz      loc_1800AA3EC
0x1800aa1d5  sub     eax, 5
0x1800aa1d8  jz      loc_1800AA386
0x1800aa1de  sub     eax, 0Bh
0x1800aa1e1  jz      loc_1800AA34E
0x1800aa1e7  sub     eax, 23h ; '#'
0x1800aa1ea  jz      loc_1800AA33A
0x1800aa1f0  cmp     eax, 18h
0x1800aa1f3  jnz     loc_1800AA16E
0x1800aa1f9  mov     rdx, r14
0x1800aa1fc  call    CIHandleNotifyFormat
0x1800aa201  jmp     loc_1800AA17F
0x1800aa206  jz      loc_1800AA934
0x1800aa20c  mov     eax, esi
0x1800aa20e  sub     eax, 465h
0x1800aa213  jz      loc_1800AA918
0x1800aa219  sub     eax, 1
0x1800aa21c  jnz     loc_1800AA801
0x1800aa222  movzx   eax, word ptr [rdi+50h]
0x1800aa226  movzx   ecx, word ptr [rcx+54h]
0x1800aa22a  shl     ecx, 10h
0x1800aa22d  or      eax, ecx
0x1800aa22f  cdqe
0x1800aa231  jmp     loc_1800AA17F
0x1800aa236  mov     rax, r13
0x1800aa239  sub     esi, 2005h
0x1800aa23f  jz      loc_1800AA992
0x1800aa245  sub     esi, 1
0x1800aa248  jz      loc_1800AA987
0x1800aa24e  sub     esi, 1
0x1800aa251  jz      loc_1800AA97D
0x1800aa257  sub     esi, 1
0x1800aa25a  jz      loc_1800AA97D
0x1800aa260  sub     esi, 4
0x1800aa263  jz      loc_1800AA96F
0x1800aa269  sub     esi, 1
0x1800aa26c  jz      short loc_1800AA283
0x1800aa26e  cmp     esi, 1
0x1800aa271  jnz     loc_1800AA17F
0x1800aa277  mov     eax, [rcx+3Ch]
0x1800aa27a  shr     rax, 5
0x1800aa27e  jmp     loc_1800AA98A
0x1800aa283  add     rcx, 34h ; '4'; this
0x1800aa287  shl     ebx, 4
0x1800aa28a  xor     ebx, [rcx+8]
0x1800aa28d  and     ebx, 10h
0x1800aa290  xor     [rcx+8], ebx
0x1800aa293  call    ?EvaluateMagicNumberScaling@DPISCALEINFO@@AEAAXXZ; DPISCALEINFO::EvaluateMagicNumberScaling(void)
0x1800aa298  mov     eax, 1
0x1800aa29d  jmp     loc_1800AA17F
0x1800aa2a2  test    dword ptr [rcx+10h], 100h
0x1800aa2a9  jz      short loc_1800AA2E0
0x1800aa2ab  mov     eax, [rcx+48h]
0x1800aa2ae  test    al, 40h
0x1800aa2b0  jnz     short loc_1800AA2E0
0x1800aa2b2  or      eax, 40h
0x1800aa2b5  mov     qword ptr [rbp+4Fh+EventTrack.dwHoverTime], r13
0x1800aa2b9  mov     [rcx+48h], eax
0x1800aa2bc  mov     r12d, 2
0x1800aa2c2  mov     rax, [rcx]
0x1800aa2c5  lea     rcx, [rsp+0F0h+EventTrack]; lpEventTrack
0x1800aa2ca  mov     [rbp+4Fh+EventTrack.hwndTrack], rax
0x1800aa2ce  mov     [rsp+0F0h+EventTrack.cbSize], 18h
0x1800aa2d6  mov     [rbp+4Fh+EventTrack.dwFlags], r12d
0x1800aa2da  call    cs:__imp_TrackMouseEvent
0x1800aa2e0  mov     eax, esi
0x1800aa2e2  sub     eax, 128h
0x1800aa2e7  jz      loc_1800AA7F1
0x1800aa2ed  sub     eax, 0D8h
0x1800aa2f2  jz      loc_1800AA7E1
0x1800aa2f8  sub     eax, 1
0x1800aa2fb  jz      loc_1800AA727
0x1800aa301  sub     eax, 1
0x1800aa304  jz      loc_1800AA695
0x1800aa30a  sub     eax, 0A1h
0x1800aa30f  jz      loc_1800AA67D
0x1800aa315  sub     eax, 3Fh ; '?'
0x1800aa318  jz      loc_1800AA656
0x1800aa31e  cmp     eax, 36h ; '6'
0x1800aa321  jnz     loc_1800AA16E
0x1800aa327  xor     r8d, r8d; int
0x1800aa32a  mov     rdx, rbx; HDC
0x1800aa32d  mov     rcx, rdi; this
0x1800aa330  call    ?OnPaint@CUpDown@@IEAAXPEAUHDC__@@H@Z; CUpDown::OnPaint(HDC__ *,int)
0x1800aa335  jmp     loc_1800AA894
0x1800aa33a  cmp     r14d, 0FFFFFFF4h
0x1800aa33e  jnz     loc_1800AA16E
0x1800aa344  mov     eax, 10016h
0x1800aa349  jmp     loc_1800AA17F
0x1800aa34e  cmp     rbx, 2Ah ; '*'
0x1800aa352  ja      loc_1800AA894
0x1800aa358  mov     rax, 40400000001h
0x1800aa362  bt      rax, rbx
0x1800aa366  jnb     loc_1800AA894
0x1800aa36c  mov     cs:?g_systemMetrics@@3VCSystemMetrics@@A, r13w; CSystemMetrics g_systemMetrics
0x1800aa374  call    ?UnAnchor@CUpDown@@IEAAXXZ; CUpDown::UnAnchor(void)
0x1800aa379  mov     rcx, rdi; this
0x1800aa37c  call    ?Anchor@CUpDown@@IEAAXXZ; CUpDown::Anchor(void)
0x1800aa381  jmp     loc_1800AA894
0x1800aa386  xor     edx, edx; Val
0x1800aa388  lea     rcx, [rbp+4Fh+Paint]; void *
0x1800aa38c  lea     r8d, [rdx+48h]; Size
0x1800aa390  call    memset_0
0x1800aa395  test    rbx, rbx
0x1800aa398  jz      short loc_1800AA39F
0x1800aa39a  mov     rsi, rbx
0x1800aa39d  jmp     short loc_1800AA3AF
0x1800aa39f  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x1800aa3a3  mov     rcx, r15; hWnd
0x1800aa3a6  call    cs:__imp_BeginPaint
0x1800aa3ac  mov     rsi, rax
0x1800aa3af  mov     rcx, [rdi]; hWnd
0x1800aa3b2  call    cs:__imp_IsWindowVisible
0x1800aa3b8  test    eax, eax
0x1800aa3ba  jz      short loc_1800AA3D1
0x1800aa3bc  test    rbx, rbx
0x1800aa3bf  mov     r8d, r13d
0x1800aa3c2  mov     rdx, rsi; HDC
0x1800aa3c5  mov     rcx, rdi; this
0x1800aa3c8  setz    r8b; int
0x1800aa3cc  call    ?OnPaint@CUpDown@@IEAAXPEAUHDC__@@H@Z; CUpDown::OnPaint(HDC__ *,int)
0x1800aa3d1  test    rbx, rbx
0x1800aa3d4  jnz     loc_1800AA894
0x1800aa3da  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x1800aa3de  mov     rcx, r15; hWnd
0x1800aa3e1  call    cs:__imp_EndPaint
0x1800aa3e7  jmp     loc_1800AA894
0x1800aa3ec  xor     edx, edx; lpRect
0x1800aa3ee  mov     rcx, r15; hWnd
0x1800aa3f1  lea     r8d, [rdx+1]; bErase
0x1800aa3f5  call    cs:__imp_InvalidateRect
0x1800aa3fb  jmp     loc_1800AA894
0x1800aa400  mov     rcx, [rcx+80h]; hTheme
0x1800aa407  test    rcx, rcx
0x1800aa40a  jz      short loc_1800AA419
0x1800aa40c  call    cs:__imp_CloseThemeData
0x1800aa412  mov     [rdi+80h], r13
0x1800aa419  mov     rcx, [rdi+88h]; hTheme
0x1800aa420  test    rcx, rcx
0x1800aa423  jz      short loc_1800AA432
0x1800aa425  call    cs:__imp_CloseThemeData
0x1800aa42b  mov     [rdi+88h], r13
0x1800aa432  mov     rbx, [rdi+70h]
0x1800aa436  test    rbx, rbx
0x1800aa439  jz      short loc_1800AA44F
0x1800aa43b  call    cs:__imp_GetProcessHeap
0x1800aa441  mov     r8, rbx; lpMem
0x1800aa444  xor     edx, edx; dwFlags
0x1800aa446  mov     rcx, rax; hHeap
0x1800aa449  call    cs:__imp_HeapFree
0x1800aa44f  movzx   edx, cs:g_atomTabletPcPenService; lpString
0x1800aa456  mov     rcx, r15; hWnd
0x1800aa459  call    cs:__imp_RemovePropW
0x1800aa45f  jmp     loc_1800AA894
0x1800aa464  mov     r8, r14
0x1800aa467  call    CIInitialize
0x1800aa46c  mov     rcx, [rdi]; hwnd
0x1800aa46f  lea     rdx, aSpin; "Spin"
0x1800aa476  mov     qword ptr [rdi+1C0h], 0FFFFFFFFFFFFFFFFh
0x1800aa481  call    cs:__imp_OpenThemeData
0x1800aa487  mov     [rdi+80h], rax
0x1800aa48e  mov     eax, 200h
0x1800aa493  test    [r14+30h], eax
0x1800aa497  jz      short loc_1800AA49D
0x1800aa499  or      dword ptr [rdi+48h], 4
0x1800aa49d  test    [r14+48h], eax
0x1800aa4a1  jz      short loc_1800AA4A7
0x1800aa4a3  or      dword ptr [rdi+48h], 10h
0x1800aa4a7  mov     qword ptr [rdi+4Ch], 0Ah
0x1800aa4af  mov     qword ptr [rdi+54h], 64h ; 'd'
0x1800aa4b7  mov     [rdi+40h], r13
0x1800aa4bb  mov     [rdi+5Ch], r13d
0x1800aa4bf  call    cs:__imp_GetProcessHeap
0x1800aa4c5  mov     edx, 8
0x1800aa4ca  mov     rcx, rax
0x1800aa4cd  mov     r8d, edx
0x1800aa4d0  lea     r9d, [rdx-5]
0x1800aa4d4  call    CCHeapAllocArraySize
0x1800aa4d9  mov     [rdi+70h], rax
0x1800aa4dd  test    rax, rax
0x1800aa4e0  jz      short loc_1800AA525
0x1800aa4e2  mov     dword ptr [rdi+68h], 3
0x1800aa4e9  mov     [rax], r13d
0x1800aa4ec  mov     rax, [rdi+70h]
0x1800aa4f0  mov     dword ptr [rax+4], 1
0x1800aa4f7  mov     rax, [rdi+70h]
0x1800aa4fb  mov     dword ptr [rax+8], 2
0x1800aa502  mov     rax, [rdi+70h]
0x1800aa506  mov     dword ptr [rax+0Ch], 5
0x1800aa50d  mov     rax, [rdi+70h]
0x1800aa511  mov     dword ptr [rax+10h], 5
0x1800aa518  mov     rax, [rdi+70h]
0x1800aa51c  mov     dword ptr [rax+14h], 14h
0x1800aa523  jmp     short loc_1800AA529
0x1800aa525  mov     [rdi+68h], r13d
0x1800aa529  xor     edx, edx; hwnd
0x1800aa52b  mov     rcx, rdi; this
0x1800aa52e  call    ?SetBuddy@CUpDown@@IEAA_JPEAUHWND__@@@Z; CUpDown::SetBuddy(HWND__ *)
0x1800aa533  mov     rcx, rdi; this
0x1800aa536  call    ?SetPos@CUpDown@@IEAAXXZ; CUpDown::SetPos(void)
0x1800aa53b  cmp     [rdi+80h], r13
0x1800aa542  jz      short loc_1800AA549
0x1800aa544  bts     dword ptr [rdi+10h], 8
0x1800aa549  movzx   edx, cs:g_atomTabletPcPenService; lpString
0x1800aa550  mov     r8d, 10001h; hData
0x1800aa556  mov     rcx, r15; hWnd
0x1800aa559  call    cs:__imp_SetPropW
0x1800aa55f  jmp     loc_1800AA894
0x1800aa564  mov     qword ptr [rbp+4Fh+Point.x], r13
0x1800aa568  call    cs:__imp_GetCapture
0x1800aa56e  cmp     rax, r15
0x1800aa571  jnz     loc_1800AA6BB
0x1800aa577  xor     r9d, r9d; lpTimerFunc
0x1800aa57a  mov     rcx, r15; hWnd
0x1800aa57d  lea     edx, [r9+1]; nIDEvent
0x1800aa581  lea     r8d, [r9+64h]; uElapse
0x1800aa585  call    cs:__imp_SetTimer
0x1800aa58b  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x1800aa58f  mov     rcx, r15; hWnd
0x1800aa592  call    cs:__imp_GetWindowRect
0x1800aa598  test    byte ptr [rdi+10h], 40h
0x1800aa59c  mov     r12d, 2
0x1800aa5a2  mov     r8d, [rdi+60h]
0x1800aa5a6  jz      short loc_1800AA5C1
  ... truncated ...
```
