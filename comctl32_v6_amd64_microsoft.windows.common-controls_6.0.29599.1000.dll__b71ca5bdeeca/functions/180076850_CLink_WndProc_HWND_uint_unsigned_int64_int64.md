# CLink::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180076850`
- end: `0x180077260`
- name: `?WndProc@CLink@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `2576`
- prototype: `__int64 __fastcall(HWND, UINT Msg, HDC, struct tagLITEM *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callees

- `0x180011f44`
- `0x180026340`
- `0x180055e0c`
- `0x180076850`
- `0x180077cec`
- `0x1800ef96c`
- `0x1800f175c`
- `0x180114520`
- `0x180114ebc`
- `0x18013efbc`
- `0x18013f2dc`
- `0x18013f5d0`
- `0x18013f70c`
- `0x18013f800`
- `0x1801d1010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180076ea1`
- `GDI32!DeleteObject` at `0x180076ea1`
- `USER32!GetMessagePos` at `0x180076eb7`
- `USER32!GetMessagePos` at `0x180076eb7`
- `USER32!MapVirtualKeyW` at `0x18007704a`
- `USER32!MapVirtualKeyW` at `0x18007704a`
- `USER32!MapWindowPoints` at `0x180076a39`
- `USER32!MapWindowPoints` at `0x180076ed8`
- `USER32!MapWindowPoints` at `0x180076a39`
- `USER32!MapWindowPoints` at `0x180076ed8`
- `USER32!GetParent` at `0x180076c20`
- `USER32!GetParent` at `0x180076c20`
- `USER32!DefWindowProcW` at `0x18007699e`
- `USER32!DefWindowProcW` at `0x180076bfb`
- `USER32!DefWindowProcW` at `0x180076d7a`
- `USER32!DefWindowProcW` at `0x18007699e`
- `USER32!DefWindowProcW` at `0x180076bfb`
- `USER32!DefWindowProcW` at `0x180076d7a`
- `USER32!GetDC` at `0x18007715a`
- `USER32!GetDC` at `0x18007715a`
- `USER32!SetWindowLongPtrW` at `0x180076af1`
- `USER32!SetWindowLongPtrW` at `0x180076b09`
- `USER32!SetWindowLongPtrW` at `0x180076d8b`
- `USER32!SetWindowLongPtrW` at `0x180076af1`
- `USER32!SetWindowLongPtrW` at `0x180076b09`
- `USER32!SetWindowLongPtrW` at `0x180076d8b`
- `USER32!SendMessageW` at `0x180076c34`
- `USER32!SendMessageW` at `0x180076c34`
- `USER32!GetWindowLongPtrW` at `0x180076891`
- `USER32!GetWindowLongPtrW` at `0x180076891`
- `USER32!RedrawWindow` at `0x18007701e`
- `USER32!RedrawWindow` at `0x18007701e`
- `USER32!GetClientRect` at `0x180076e8d`
- `USER32!GetClientRect` at `0x180076e8d`
- `USER32!InvalidateRect` at `0x180076b77`
- `USER32!InvalidateRect` at `0x180076e73`
- `USER32!InvalidateRect` at `0x180076b77`
- `USER32!InvalidateRect` at `0x180076e73`
- `USER32!ReleaseDC` at `0x1800771c6`
- `USER32!ReleaseDC` at `0x1800771c6`
- `USER32!BeginPaint` at `0x180076a6c`
- `USER32!BeginPaint` at `0x180076a6c`
- `USER32!EndPaint` at `0x180076d43`
- `USER32!EndPaint` at `0x180076d43`
- `UxTheme!OpenThemeData` at `0x180076c94`
- `UxTheme!OpenThemeData` at `0x180076c94`
- `UxTheme!CloseThemeData` at `0x180076db5`
- `UxTheme!CloseThemeData` at `0x180076db5`
- `OLEACC!LresultFromObject` at `0x180076abf`
- `OLEACC!LresultFromObject` at `0x180076abf`

## pseudocode

```c
LONG_PTR __fastcall CLink::WndProc(HWND a1, unsigned __int64 Msg, unsigned __int64 a3, struct tagLITEM *a4)
{
  UINT v6; // r13d
  __int64 v8; // rsi
  LONG_PTR WindowLongPtrW; // rdi
  const struct tagRECT *v10; // r8
  const struct tagRECT *v11; // r9
  int v12; // r15d
  __int64 v13; // rcx
  void *v15; // rcx
  HFONT v16; // rdx
  HFONT v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  HDC v20; // rax
  const struct tagRECT *v21; // r8
  const struct tagRECT *v22; // r9
  CLink *v23; // rax
  CLink *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  LRESULT v28; // r13
  HWND Parent; // rax
  int v30; // eax
  __int64 v31; // rcx
  int v32; // ebx
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 *v35; // rcx
  __int64 v36; // rax
  LRESULT v37; // rbx
  __int64 v38; // rcx
  void *v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 *v42; // rcx
  __int64 v43; // rax
  HWND v44; // rcx
  DWORD MessagePos; // eax
  __int64 v46; // rcx
  __int64 v47; // rcx
  int v48; // edx
  int v49; // ecx
  UINT state; // ecx
  int v51; // r13d
  __int64 *v52; // rcx
  struct tagPOINT v53; // rbx
  __int64 v54; // rdx
  __int64 v55; // rcx
  HDC hDC; // [rsp+40h] [rbp-69h] BYREF
  struct tagPOINT Points; // [rsp+48h] [rbp-61h] BYREF
  struct tagRECT Rect; // [rsp+50h] [rbp-59h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+60h] [rbp-49h] BYREF

  v6 = Msg;
  if ( (_DWORD)Msg == 129 )
  {
    v23 = (CLink *)DirectUI::AccHAllocAndZero((DirectUI *)0x80, Msg);
    if ( v23 )
    {
      v24 = CLink::CLink(v23, a1);
      if ( v24 )
      {
        SetWindowLongPtrW(a1, 0, (LONG_PTR)v24);
        return 1;
      }
    }
    SetWindowLongPtrW(a1, 0, 0);
    return 0;
  }
  v8 = 0;
  WindowLongPtrW = GetWindowLongPtrW(a1, 0);
  if ( !WindowLongPtrW )
    return DefWindowProcW(a1, v6, a3, (LPARAM)a4);
  v12 = 1;
  if ( v6 <= 0x84 )
  {
    if ( v6 == 132 )
    {
      Points.x = (__int16)a4;
      Points.y = SWORD1(a4);
      LODWORD(hDC) = 0;
      MapWindowPoints(0, a1, &Points, 1u);
      v19 = *(_QWORD *)(WindowLongPtrW + 88);
      if ( !v19
        || (*(unsigned int (__fastcall **)(__int64, struct tagPOINT, HDC *))(*(_QWORD *)v19 + 216LL))(v19, Points, &hDC) )
      {
        return -1;
      }
    }
    else
    {
      if ( v6 <= 0xF )
      {
        if ( v6 == 15 )
        {
          memset_0(&Paint, 0, sizeof(Paint));
          v20 = BeginPaint(*(HWND *)(WindowLongPtrW + 24), &Paint);
          if ( v20 )
          {
            CLink::Paint((CLink *)WindowLongPtrW, v20, v21, v22);
            EndPaint(*(HWND *)(WindowLongPtrW + 24), &Paint);
          }
          return 0;
        }
        if ( v6 != 1 )
        {
          switch ( v6 )
          {
            case 5u:
              CLink::Paint((CLink *)WindowLongPtrW, 0, v10, v11);
              return DefWindowProcW(a1, v6, a3, (LPARAM)a4);
            case 7u:
              v27 = *(_QWORD *)(WindowLongPtrW + 88);
              *(_DWORD *)(WindowLongPtrW + 80) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 168LL))(v27);
              CLink::SendNotify((CLink *)WindowLongPtrW, 0xFFFFFFF9, 0, 0);
              (*(void (__fastcall **)(LONG_PTR, _QWORD, _QWORD))(*(_QWORD *)(WindowLongPtrW + 32) + 40LL))(
                WindowLongPtrW + 32,
                0,
                0);
              break;
            case 8u:
              v26 = *(_QWORD *)(WindowLongPtrW + 88);
              *(_DWORD *)(WindowLongPtrW + 80) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 176LL))(v26);
              break;
            case 0xCu:
              (*(void (__fastcall **)(_QWORD, struct tagLITEM *))(**(_QWORD **)(WindowLongPtrW + 88) + 72LL))(
                *(_QWORD *)(WindowLongPtrW + 88),
                a4);
              CLink::UpdateTabstop((CLink *)WindowLongPtrW);
              InvalidateRect(*(HWND *)(WindowLongPtrW + 24), 0, 0);
              return DefWindowProcW(a1, v6, a3, (LPARAM)a4);
            case 0xDu:
              LODWORD(hDC) = a3;
              if ( a4 )
              {
                v25 = *(_QWORD *)(WindowLongPtrW + 88);
                if ( v25 )
                {
                  if ( (*(int (__fastcall **)(__int64, __int64, struct tagLITEM *, HDC *))(*(_QWORD *)v25 + 80LL))(
                         v25,
                         1,
                         a4,
                         &hDC) >= 0 )
                    return (unsigned int)hDC;
                }
              }
              break;
            case 0xEu:
              v13 = *(_QWORD *)(WindowLongPtrW + 88);
              LODWORD(hDC) = 1;
              if ( v13 )
              {
                (*(void (__fastcall **)(__int64, __int64, _QWORD, HDC *))(*(_QWORD *)v13 + 80LL))(v13, 1, 0, &hDC);
                v12 = (int)hDC;
              }
              return (unsigned int)(v12 - 1);
            default:
              return DefWindowProcW(a1, v6, a3, (LPARAM)a4);
          }
          return 0;
        }
        v28 = DefWindowProcW(a1, 1u, a3, (LPARAM)a4);
        if ( v28 )
          return v28;
        if ( (int)CLink::Initialize((CLink *)WindowLongPtrW) >= 0 )
        {
          Parent = GetParent(a1);
          v30 = SendMessageW(Parent, 0x129u, 0, 0);
          v31 = *(_QWORD *)(WindowLongPtrW + 88);
          *(_DWORD *)(WindowLongPtrW + 56) = v30;
          *(_DWORD *)(WindowLongPtrW + 76) = *(_DWORD *)&a4->szID[16] & 0x10000;
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v31 + 72LL))(v31, *(_QWORD *)&a4->szID[20]);
          CLink::UpdateTabstop((CLink *)WindowLongPtrW);
          *(_DWORD *)(WindowLongPtrW + 60) = *(_DWORD *)&a4->szID[16] & 1;
          *(_DWORD *)(WindowLongPtrW + 64) = *(_DWORD *)&a4->szID[16] & 2;
          *(_DWORD *)(WindowLongPtrW + 68) = *(_DWORD *)&a4->szID[16] & 0x10;
          if ( (a4->szID[16] & 8) != 0 )
            *(_QWORD *)(WindowLongPtrW + 104) = OpenThemeData(a1, L"Link");
          v32 = *(_DWORD *)&a4->szID[16] & 0x20;
          if ( (a4->szID[16] & 0xC) != 0 || v32 )
          {
            v33 = *(_QWORD *)(WindowLongPtrW + 88);
            LODWORD(hDC) = 0;
            (*(void (__fastcall **)(__int64, HDC *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v33 + 112LL))(
              v33,
              &hDC,
              0,
              0,
              0,
              0);
            v34 = (unsigned int)hDC;
            if ( (a4->szID[16] & 4) != 0 )
            {
              LODWORD(v34) = (unsigned int)hDC | 0x800;
              LODWORD(hDC) = (unsigned int)hDC | 0x800;
            }
            if ( v32 )
            {
              v34 = (unsigned int)v34 | 2;
              LODWORD(hDC) = v34;
            }
            v35 = *(__int64 **)(WindowLongPtrW + 88);
            v36 = *v35;
            if ( (a4->szID[16] & 8) != 0 )
              (*(void (__fastcall **)(__int64 *, __int64, _QWORD, __int64, int, int))(v36 + 120))(
                v35,
                v34,
                *(_QWORD *)(WindowLongPtrW + 104),
                1,
                1,
                2);
            else
              (*(void (__fastcall **)(__int64 *, __int64))(v36 + 104))(v35, v34);
          }
          return v28;
        }
        return -1;
      }
      if ( v6 != 32 )
      {
        switch ( v6 )
        {
          case '0':
            v15 = *(void **)(WindowLongPtrW + 48);
            if ( v15 )
            {
              DeleteObject(v15);
              *(_QWORD *)(WindowLongPtrW + 48) = 0;
            }
            *(_QWORD *)(WindowLongPtrW + 40) = a3;
            if ( a3 )
            {
              v16 = (HFONT)a3;
            }
            else
            {
              v16 = (HFONT)g_hfontSystem;
              *(_QWORD *)(WindowLongPtrW + 40) = g_hfontSystem;
              if ( !v16 )
              {
                v17 = 0;
LABEL_24:
                v18 = *(_QWORD *)(WindowLongPtrW + 88);
                if ( v18 )
                  (*(void (__fastcall **)(__int64, _QWORD, HFONT))(*(_QWORD *)v18 + 56LL))(
                    v18,
                    *(_QWORD *)(WindowLongPtrW + 40),
                    v17);
                return DefWindowProcW(a1, v6, a3, (LPARAM)a4);
              }
            }
            v17 = DPISCALEINFO::EnsureHotFont((DPISCALEINFO *)v15, v16, 0);
            *(_QWORD *)(WindowLongPtrW + 48) = v17;
            goto LABEL_24;
          case '1':
            return *(_QWORD *)(WindowLongPtrW + 40);
          case 'F':
            v44 = *(HWND *)(WindowLongPtrW + 24);
            Rect = 0;
            GetClientRect(v44, &Rect);
            return DefWindowProcW(a1, v6, a3, (LPARAM)a4);
          case '}':
            if ( (a3 & 0xFFFFFFFFFFFFFFF0uLL) != 0 && ((LOBYTE(a4->iLink) ^ LOBYTE(a4->mask)) & 0xC) != 0 )
            {
              v40 = *(_QWORD *)(WindowLongPtrW + 88);
              LODWORD(hDC) = 0;
              (*(void (__fastcall **)(__int64, HDC *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v40 + 112LL))(
                v40,
                &hDC,
                0,
                0,
                0,
                0);
              v41 = (unsigned int)hDC;
              if ( ((LOBYTE(a4->mask) ^ LOBYTE(a4->iLink)) & 4) != 0 )
              {
                LODWORD(v41) = (unsigned int)hDC ^ 0x800;
                LODWORD(hDC) = (unsigned int)hDC ^ 0x800;
              }
              v42 = *(__int64 **)(WindowLongPtrW + 88);
              v43 = *v42;
              if ( (a4->iLink & 8) != 0 )
                (*(void (__fastcall **)(__int64 *, __int64, _QWORD, __int64, int, int))(v43 + 120))(
                  v42,
                  v41,
                  *(_QWORD *)(WindowLongPtrW + 104),
                  1,
                  1,
                  2);
              else
                (*(void (__fastcall **)(__int64 *, __int64))(v43 + 104))(v42, v41);
              InvalidateRect(a1, 0, 1);
            }
            return 0;
        }
        if ( v6 != 130 )
        {
          if ( v6 == 61 && (_DWORD)a4 == -4 )
            return LresultFromObject(&IID_IAccessible, a3, (LPUNKNOWN)WindowLongPtrW);
          return DefWindowProcW(a1, v6, a3, (LPARAM)a4);
        }
        v37 = DefWindowProcW(a1, 0x82u, a3, (LPARAM)a4);
        SetWindowLongPtrW(a1, 0, 0);
        v38 = *(_QWORD *)(WindowLongPtrW + 88);
        if ( v38 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 24LL))(v38, 0);
        v39 = *(void **)(WindowLongPtrW + 104);
        *(_QWORD *)(WindowLongPtrW + 24) = 0;
        if ( v39 )
          CloseThemeData(v39);
        (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)WindowLongPtrW + 16LL))(WindowLongPtrW);
        return v37;
      }
      LODWORD(hDC) = 0;
      MessagePos = GetMessagePos();
      Points.x = (__int16)MessagePos;
      Points.y = SHIWORD(MessagePos);
      MapWindowPoints(0, a1, &Points, 1u);
      if ( (*(unsigned int (__fastcall **)(_QWORD, struct tagPOINT, HDC *))(**(_QWORD **)(WindowLongPtrW + 88) + 216LL))(
             *(_QWORD *)(WindowLongPtrW + 88),
             Points,
             &hDC) )
      {
        return 0;
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(WindowLongPtrW + 88) + 152LL))(*(_QWORD *)(WindowLongPtrW + 88));
    }
    return 1;
  }
  if ( v6 <= 0x2E2 )
  {
    if ( v6 == 738 )
    {
      if ( !(unsigned int)DPISCALEINFO::HandleDPIChanged(WindowLongPtrW + 112, a1, 13) )
        return DefWindowProcW(a1, v6, a3, (LPARAM)a4);
      ResetThemeData(a1);
      return 0;
    }
    if ( v6 != 135 )
    {
      if ( v6 == 256 )
      {
        if ( (_DWORD)a3 == 229 )
          LODWORD(a3) = MapVirtualKeyW(BYTE2(a4), 1u);
        if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(WindowLongPtrW + 88) + 208LL))(
                *(_QWORD *)(WindowLongPtrW + 88),
                (unsigned int)a3) )
        {
          *(_DWORD *)(WindowLongPtrW + 80) = 1;
          return 0;
        }
        *(_DWORD *)(WindowLongPtrW + 80) = 0;
      }
      else
      {
        if ( v6 != 257 && v6 != 258 )
        {
          if ( v6 != 296 )
          {
            if ( v6 == 513 )
            {
              v47 = *(_QWORD *)(WindowLongPtrW + 88);
              Points.x = (__int16)a4;
              Points.y = SWORD1(a4);
              (*(void (__fastcall **)(__int64, struct tagPOINT))(*(_QWORD *)v47 + 192LL))(v47, Points);
            }
            else if ( v6 == 514 )
            {
              v46 = *(_QWORD *)(WindowLongPtrW + 88);
              Points.x = (__int16)a4;
              Points.y = SWORD1(a4);
              (*(void (__fastcall **)(__int64, struct tagPOINT))(*(_QWORD *)v46 + 200LL))(v46, Points);
            }
            return DefWindowProcW(a1, v6, a3, (LPARAM)a4);
          }
          v48 = *(_DWORD *)(WindowLongPtrW + 56);
          if ( (unsigned __int16)a3 == 1 )
          {
            v49 = v48 | WORD1(a3);
          }
          else
          {
            if ( (unsigned __int16)a3 != 2 )
              return DefWindowProcW(a1, v6, a3, (LPARAM)a4);
            v49 = v48 & ~WORD1(a3);
          }
          *(_DWORD *)(WindowLongPtrW + 56) = v49;
          if ( v48 != v49 )
            RedrawWindow(a1, 0, 0, 0x105u);
          return DefWindowProcW(a1, v6, a3, (LPARAM)a4);
        }
        if ( *(_DWORD *)(WindowLongPtrW + 80) )
          return 0;
      }
      return 1;
    }
    v37 = 256;
    if ( !a4 )
      return v37;
    state = a4->state;
    if ( state - 256 <= 1 )
    {
      switch ( *(_QWORD *)a4->szID )
      {
        case 9LL:
          if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(WindowLongPtrW + 88) + 184LL))(*(_QWORD *)(WindowLongPtrW + 88)) )
            return v37;
          *(_DWORD *)(WindowLongPtrW + 72) = 1;
          return 258;
        case 0xDLL:
          if ( *(_DWORD *)(WindowLongPtrW + 64) )
            return v37;
          break;
        case 0x20LL:
          break;
        default:
          return v37;
      }
    }
    else
    {
      if ( state != 258 )
        return v37;
      if ( *(_QWORD *)a4->szID != 13 )
      {
        if ( *(_QWORD *)a4->szID != 9 || !*(_DWORD *)(WindowLongPtrW + 72) )
          return v37;
        *(_DWORD *)(WindowLongPtrW + 72) = 0;
        return 258;
      }
    }
    return 260;
  }
  switch ( v6 )
  {
    case 0x318u:
      CLink::Paint((CLink *)WindowLongPtrW, (HDC)a3, v10, v11);
      return 0;
    case 0x31Au:
      ResetThemeData(a1);
      return DefWindowProcW(a1, v6, a3, (LPARAM)a4);
    case 0x700u:
      if ( a4
        && (*(int (__fastcall **)(_QWORD, _QWORD, UINT *))(**(_QWORD **)(WindowLongPtrW + 88) + 216LL))(
             *(_QWORD *)(WindowLongPtrW + 88),
             *(_QWORD *)&a4->mask,
             &a4->stateMask) >= 0 )
      {
        v55 = *(_QWORD *)(WindowLongPtrW + 88);
        LODWORD(hDC) = 48;
        LOBYTE(v8) = (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64, WCHAR *, HDC *))(*(_QWORD *)v55 + 96LL))(
                       v55,
                       a4->stateMask,
                       1,
                       &a4->szID[4],
                       &hDC) == 0;
        return v8;
      }
      return 0;
  }
  if ( v6 != 1793 )
  {
    if ( v6 == 1794 )
      return CLink::SetItem((CLink *)WindowLongPtrW, a4);
    if ( v6 == 1795 )
      return CLink::GetItem((CLink *)WindowLongPtrW, a4);
    return DefWindowProcW(a1, v6, a3, (LPARAM)a4);
  }
  v51 = -1;
  hDC = GetDC(a1);
  if ( hDC )
  {
    v52 = *(__int64 **)(WindowLongPtrW + 88);
    Rect = 0;
    Rect.right = a3;
    v53 = 0;
    v54 = *v52;
    Points = 0;
    if ( (*(int (__fastcall **)(__int64 *, HDC, __int64, struct tagRECT *))(v54 + 160))(v52, hDC, 1, &Rect) >= 0 )
    {
      v51 = Rect.bottom - Rect.top;
      Points.x = Rect.right - Rect.left;
      Points.y = Rect.bottom - Rect.top;
      v53 = Points;
    }
    if ( a4 )
      *(struct tagPOINT *)&a4->mask = v53;
    ReleaseDC(a1, hDC);
  }
  return v51;
}

```

## disassembly

```asm
0x180076850  push    rbp
0x180076852  push    rbx
0x180076853  push    rsi
0x180076854  push    rdi
0x180076855  push    r12
0x180076857  push    r13
0x180076859  push    r14
0x18007685b  push    r15
0x18007685d  lea     rbp, [rsp-1Fh]
0x180076862  sub     rsp, 0C8h
0x180076869  mov     rax, cs:__security_cookie
0x180076870  xor     rax, rsp
0x180076873  mov     [rbp+57h+var_50], rax
0x180076877  mov     r14, r9
0x18007687a  mov     rbx, r8
0x18007687d  mov     r13d, edx
0x180076880  mov     r12, rcx
0x180076883  cmp     edx, 81h
0x180076889  jz      loc_180076ACA
0x18007688f  xor     edx, edx; nIndex
0x180076891  call    cs:__imp_GetWindowLongPtrW
0x180076897  xor     esi, esi
0x180076899  mov     rdi, rax
0x18007689c  test    rax, rax
0x18007689f  jz      loc_180076992
0x1800768a5  mov     eax, 84h
0x1800768aa  lea     r15d, [rsi+1]
0x1800768ae  cmp     r13d, eax
0x1800768b1  ja      loc_1800769C4
0x1800768b7  jz      loc_180076A18
0x1800768bd  cmp     r13d, 0Fh
0x1800768c1  ja      short loc_180076938
0x1800768c3  jz      loc_180076A55
0x1800768c9  mov     eax, r13d
0x1800768cc  sub     eax, r15d
0x1800768cf  jz      loc_180076BEF
0x1800768d5  sub     eax, 4
0x1800768d8  jz      loc_180076BE0
0x1800768de  sub     eax, 2
0x1800768e1  jz      loc_180076B9D
0x1800768e7  sub     eax, r15d
0x1800768ea  jz      loc_180076B82
0x1800768f0  sub     eax, 4
0x1800768f3  jz      loc_180076B53
0x1800768f9  sub     eax, r15d
0x1800768fc  jz      loc_180076B14
0x180076902  cmp     eax, r15d
0x180076905  jnz     loc_180076992
0x18007690b  mov     rcx, [rdi+58h]
0x18007690f  mov     dword ptr [rbp+57h+hDC], r15d
0x180076913  test    rcx, rcx
0x180076916  jz      short loc_180076932
0x180076918  mov     rax, [rcx]
0x18007691b  lea     r9, [rbp+57h+hDC]
0x18007691f  xor     r8d, r8d
0x180076922  mov     edx, r15d
0x180076925  mov     rax, [rax+50h]
0x180076929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007692e  mov     r15d, dword ptr [rbp+57h+hDC]
0x180076932  lea     eax, [r15-1]
0x180076936  jmp     short loc_1800769A4
0x180076938  mov     eax, r13d
0x18007693b  sub     eax, 20h ; ' '
0x18007693e  jz      loc_180076EB0
0x180076944  sub     eax, 10h
0x180076947  jnz     loc_180076D4E
0x18007694d  mov     rcx, [rdi+30h]; this
0x180076951  test    rcx, rcx
0x180076954  jnz     loc_180076EA1
0x18007695a  mov     [rdi+28h], rbx
0x18007695e  test    rbx, rbx
0x180076961  jz      loc_180076A82
0x180076967  mov     rdx, rbx; HFONT
0x18007696a  xor     r8d, r8d; HFONT *
0x18007696d  call    ?EnsureHotFont@DPISCALEINFO@@QEBAPEAUHFONT__@@PEAU2@PEAPEAU2@@Z; DPISCALEINFO::EnsureHotFont(HFONT__ *,HFONT__ * *)
0x180076972  mov     r8, rax
0x180076975  mov     [rdi+30h], rax
0x180076979  mov     rcx, [rdi+58h]
0x18007697d  test    rcx, rcx
0x180076980  jz      short loc_180076992
0x180076982  mov     rax, [rcx]
0x180076985  mov     rdx, [rdi+28h]
0x180076989  mov     rax, [rax+38h]
0x18007698d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076992  mov     r9, r14; lParam
0x180076995  mov     r8, rbx; wParam
0x180076998  mov     edx, r13d; Msg
0x18007699b  mov     rcx, r12; hWnd
0x18007699e  call    cs:__imp_DefWindowProcW
0x1800769a4  mov     rcx, [rbp+57h+var_50]
0x1800769a8  xor     rcx, rsp; StackCookie
0x1800769ab  call    __security_check_cookie
0x1800769b0  add     rsp, 0C8h
0x1800769b7  pop     r15
0x1800769b9  pop     r14
0x1800769bb  pop     r13
0x1800769bd  pop     r12
0x1800769bf  pop     rdi
0x1800769c0  pop     rsi
0x1800769c1  pop     rbx
0x1800769c2  pop     rbp
0x1800769c3  retn
0x1800769c4  mov     eax, 2E2h
0x1800769c9  cmp     r13d, eax
0x1800769cc  jbe     loc_180076F41
0x1800769d2  mov     eax, r13d
0x1800769d5  sub     eax, 318h
0x1800769da  jz      loc_180077250
0x1800769e0  sub     eax, 2
0x1800769e3  jz      loc_180077238
0x1800769e9  sub     eax, 3E6h
0x1800769ee  jz      loc_1800771D4
0x1800769f4  sub     eax, r15d
0x1800769f7  jz      loc_180077153
0x1800769fd  sub     eax, r15d
0x180076a00  jz      loc_180077143
0x180076a06  cmp     eax, r15d
0x180076a09  jnz     short loc_180076992
0x180076a0b  mov     rdx, r14; struct tagLITEM *
0x180076a0e  mov     rcx, rdi; this
0x180076a11  call    ?GetItem@CLink@@AEAA_JPEAUtagLITEM@@@Z; CLink::GetItem(tagLITEM *)
0x180076a16  jmp     short loc_1800769A4
0x180076a18  movsx   eax, r14w
0x180076a1c  lea     r8, [rbp+57h+Points]; lpPoints
0x180076a20  mov     [rbp+57h+Points.x], eax
0x180076a23  mov     r9d, r15d; cPoints
0x180076a26  shr     r14d, 10h
0x180076a2a  mov     rdx, r12; hWndTo
0x180076a2d  movsx   eax, r14w
0x180076a31  xor     ecx, ecx; hWndFrom
0x180076a33  mov     [rbp+57h+Points.y], eax
0x180076a36  mov     dword ptr [rbp+57h+hDC], esi
0x180076a39  call    cs:__imp_MapWindowPoints
0x180076a3f  mov     rcx, [rdi+58h]
0x180076a43  test    rcx, rcx
0x180076a46  jnz     loc_180076F21
0x180076a4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180076a50  jmp     loc_1800769A4
0x180076a55  xor     edx, edx; Val
0x180076a57  lea     rcx, [rbp+57h+Paint]; void *
0x180076a5b  lea     r8d, [rdx+48h]; Size
0x180076a5f  call    memset_0
0x180076a64  mov     rcx, [rdi+18h]; hWnd
0x180076a68  lea     rdx, [rbp+57h+Paint]; lpPaint
0x180076a6c  call    cs:__imp_BeginPaint
0x180076a72  test    rax, rax
0x180076a75  jnz     loc_180076D30
0x180076a7b  xor     eax, eax
0x180076a7d  jmp     loc_1800769A4
0x180076a82  mov     rdx, cs:g_hfontSystem
0x180076a89  mov     [rdi+28h], rdx
0x180076a8d  test    rdx, rdx
0x180076a90  jnz     loc_18007696A
0x180076a96  mov     r8, rsi
0x180076a99  jmp     loc_180076979
0x180076a9e  cmp     r13d, 3Dh ; '='
0x180076aa2  jnz     loc_180076992
0x180076aa8  cmp     r14d, 0FFFFFFFCh
0x180076aac  jnz     loc_180076992
0x180076ab2  mov     r8, rdi; punk
0x180076ab5  lea     rcx, IID_IAccessible; riid
0x180076abc  mov     rdx, rbx; wParam
0x180076abf  call    cs:__imp_LresultFromObject
0x180076ac5  jmp     loc_1800769A4
0x180076aca  mov     ecx, 80h; this
0x180076acf  call    ?AccHAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::AccHAllocAndZero(unsigned __int64)
0x180076ad4  test    rax, rax
0x180076ad7  jz      short loc_180076B01
0x180076ad9  mov     rdx, r12; HWND
0x180076adc  mov     rcx, rax; this
0x180076adf  call    ??0CLink@@QEAA@PEAUHWND__@@@Z; CLink::CLink(HWND__ *)
0x180076ae4  test    rax, rax
0x180076ae7  jz      short loc_180076B01
0x180076ae9  mov     r8, rax; dwNewLong
0x180076aec  xor     edx, edx; nIndex
0x180076aee  mov     rcx, r12; hWnd
0x180076af1  call    cs:__imp_SetWindowLongPtrW
0x180076af7  mov     eax, 1
0x180076afc  jmp     loc_1800769A4
0x180076b01  xor     r8d, r8d; dwNewLong
0x180076b04  xor     edx, edx; nIndex
0x180076b06  mov     rcx, r12; hWnd
0x180076b09  call    cs:__imp_SetWindowLongPtrW
0x180076b0f  jmp     loc_180076A7B
0x180076b14  mov     dword ptr [rbp+57h+hDC], ebx
0x180076b17  test    r14, r14
0x180076b1a  jz      loc_180076A7B
0x180076b20  mov     rcx, [rdi+58h]
0x180076b24  test    rcx, rcx
0x180076b27  jz      loc_180076A7B
0x180076b2d  mov     rax, [rcx]
0x180076b30  lea     r9, [rbp+57h+hDC]
0x180076b34  mov     r8, r14
0x180076b37  mov     edx, r15d
0x180076b3a  mov     rax, [rax+50h]
0x180076b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b43  test    eax, eax
0x180076b45  js      loc_180076A7B
0x180076b4b  mov     eax, dword ptr [rbp+57h+hDC]
0x180076b4e  jmp     loc_1800769A4
0x180076b53  mov     rcx, [rdi+58h]
0x180076b57  mov     rdx, r14
0x180076b5a  mov     rax, [rcx]
0x180076b5d  mov     rax, [rax+48h]
0x180076b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b66  mov     rcx, rdi; this
0x180076b69  call    ?UpdateTabstop@CLink@@AEAAXXZ; CLink::UpdateTabstop(void)
0x180076b6e  mov     rcx, [rdi+18h]; hWnd
0x180076b72  xor     r8d, r8d; bErase
0x180076b75  xor     edx, edx; lpRect
0x180076b77  call    cs:__imp_InvalidateRect
0x180076b7d  jmp     loc_180076992
0x180076b82  mov     rcx, [rdi+58h]
0x180076b86  mov     [rdi+50h], esi
0x180076b89  mov     rax, [rcx]
0x180076b8c  mov     rax, [rax+0B0h]
0x180076b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b98  jmp     loc_180076A7B
0x180076b9d  mov     rcx, [rdi+58h]
0x180076ba1  mov     [rdi+50h], esi
0x180076ba4  mov     rax, [rcx]
0x180076ba7  mov     rax, [rax+0A8h]
0x180076bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076bb3  xor     r9d, r9d; int
0x180076bb6  xor     r8d, r8d; int
0x180076bb9  mov     edx, 0FFFFFFF9h; unsigned int
0x180076bbe  mov     rcx, rdi; this
0x180076bc1  call    ?SendNotify@CLink@@AEBA_JIHH@Z; CLink::SendNotify(uint,int,int)
0x180076bc6  lea     rcx, [rdi+20h]
0x180076bca  xor     r8d, r8d
0x180076bcd  mov     rax, [rcx]
0x180076bd0  xor     edx, edx
0x180076bd2  mov     rax, [rax+28h]
0x180076bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076bdb  jmp     loc_180076A7B
0x180076be0  xor     edx, edx; HDC
0x180076be2  mov     rcx, rdi; this
0x180076be5  call    ?Paint@CLink@@AEAAXPEAUHDC__@@PEBUtagRECT@@1@Z; CLink::Paint(HDC__ *,tagRECT const *,tagRECT const *)
0x180076bea  jmp     loc_180076992
0x180076bef  mov     r9, r14; lParam
0x180076bf2  mov     r8, rbx; wParam
0x180076bf5  mov     edx, r15d; Msg
0x180076bf8  mov     rcx, r12; hWnd
0x180076bfb  call    cs:__imp_DefWindowProcW
0x180076c01  mov     r13, rax
0x180076c04  test    rax, rax
0x180076c07  jnz     loc_180076D28
0x180076c0d  mov     rcx, rdi; this
0x180076c10  call    ?Initialize@CLink@@AEAAJXZ; CLink::Initialize(void)
0x180076c15  test    eax, eax
0x180076c17  js      loc_180076A4C
0x180076c1d  mov     rcx, r12; hWnd
0x180076c20  call    cs:__imp_GetParent
0x180076c26  xor     r9d, r9d; lParam
0x180076c29  xor     r8d, r8d; wParam
0x180076c2c  mov     rcx, rax; hWnd
0x180076c2f  mov     edx, 129h; Msg
0x180076c34  call    cs:__imp_SendMessageW
0x180076c3a  mov     rcx, [rdi+58h]
0x180076c3e  mov     [rdi+38h], eax
0x180076c41  mov     eax, [r14+30h]
0x180076c45  and     eax, 10000h
0x180076c4a  mov     [rdi+4Ch], eax
0x180076c4d  mov     rax, [rcx]
0x180076c50  mov     rdx, [r14+38h]
0x180076c54  mov     rax, [rax+48h]
0x180076c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c5d  mov     rcx, rdi; this
0x180076c60  call    ?UpdateTabstop@CLink@@AEAAXXZ; CLink::UpdateTabstop(void)
0x180076c65  mov     eax, [r14+30h]
0x180076c69  and     eax, r15d
0x180076c6c  mov     [rdi+3Ch], eax
0x180076c6f  mov     eax, [r14+30h]
0x180076c73  and     eax, 2
0x180076c76  mov     [rdi+40h], eax
0x180076c79  mov     eax, [r14+30h]
0x180076c7d  and     eax, 10h
0x180076c80  mov     [rdi+44h], eax
0x180076c83  test    byte ptr [r14+30h], 8
0x180076c88  jz      short loc_180076C9E
0x180076c8a  lea     rdx, aLink; "Link"
0x180076c91  mov     rcx, r12; hwnd
0x180076c94  call    cs:__imp_OpenThemeData
0x180076c9a  mov     [rdi+68h], rax
0x180076c9e  mov     ebx, [r14+30h]
0x180076ca2  and     ebx, 20h
0x180076ca5  test    byte ptr [r14+30h], 0Ch
0x180076caa  jnz     short loc_180076CB0
0x180076cac  test    ebx, ebx
0x180076cae  jz      short loc_180076D28
0x180076cb0  mov     rcx, [rdi+58h]
0x180076cb4  lea     rdx, [rbp+57h+hDC]
0x180076cb8  mov     dword ptr [rbp+57h+hDC], esi
0x180076cbb  xor     r9d, r9d
0x180076cbe  mov     [rsp+100h+var_D8], rsi
0x180076cc3  xor     r8d, r8d
0x180076cc6  mov     [rsp+100h+var_E0], rsi
0x180076ccb  mov     rax, [rcx]
0x180076cce  mov     rax, [rax+70h]
0x180076cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
