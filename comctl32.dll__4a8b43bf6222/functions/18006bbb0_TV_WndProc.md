# TV_WndProc

- ea: `0x18006bbb0`
- end: `0x18006cc9c`
- name: `TV_WndProc`
- size: `4332`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, LPCCH lpMultiByteStr, LPARAM lParam)`
- caller_count: `0`
- callee_count: `66`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800115f0`
- `0x180017bac`
- `0x180018158`
- `0x1800183dc`
- `0x180018464`
- `0x180018d24`
- `0x180018d90`
- `0x1800190a4`
- `0x1800197bc`
- `0x180035fe0`
- `0x18003a400`
- `0x18003a530`
- `0x180067db0`
- `0x180068158`
- `0x180068398`
- `0x18006864c`
- `0x180068910`
- `0x180068e44`
- `0x180068edc`
- `0x180068f88`
- `0x180069110`
- `0x1800692d0`
- `0x180069454`
- `0x180069560`
- `0x18006976c`
- `0x1800697d0`
- `0x1800698a4`
- `0x180069940`
- `0x180069d54`
- `0x180069fbc`
- `0x18006a00c`
- `0x18006a0c4`
- `0x18006a414`
- `0x18006a4e0`
- `0x18006a710`
- `0x18006a770`
- `0x18006a954`
- `0x18006a9c4`
- `0x18006ab0c`
- `0x18006ab4c`
- `0x18006af90`
- `0x18006b160`
- `0x18006b208`
- `0x18006b33c`
- `0x18006b3b8`
- `0x18006b42c`
- `0x18006b754`
- `0x18006b8a8`
- `0x18006b9b0`
- `0x18006ba34`

## import_xrefs

- `GDI32!GetClipBox` at `0x18006be7f`
- `GDI32!GetClipBox` at `0x18006be7f`
- `KERNEL32!LocalFree` at `0x18006c6a0`
- `KERNEL32!LocalFree` at `0x18006c864`
- `KERNEL32!LocalFree` at `0x18006c950`
- `KERNEL32!LocalFree` at `0x18006c6a0`
- `KERNEL32!LocalFree` at `0x18006c864`
- `KERNEL32!LocalFree` at `0x18006c950`
- `USER32!GetWindowLongW` at `0x18006c434`
- `USER32!GetWindowLongW` at `0x18006c434`
- `USER32!IsWindow` at `0x18006c231`
- `USER32!IsWindow` at `0x18006c231`
- `USER32!SendMessageW` at `0x18006c259`
- `USER32!SendMessageW` at `0x18006c259`
- `USER32!ScreenToClient` at `0x18006c518`
- `USER32!ScreenToClient` at `0x18006c518`
- `USER32!SetWindowLongPtrW` at `0x18006c1fe`
- `USER32!SetWindowLongPtrW` at `0x18006c1fe`
- `USER32!SetFocus` at `0x18006c359`
- `USER32!SetFocus` at `0x18006c359`
- `USER32!GetFocus` at `0x18006c8f6`
- `USER32!GetFocus` at `0x18006cbb4`
- `USER32!GetFocus` at `0x18006c8f6`
- `USER32!GetFocus` at `0x18006cbb4`
- `USER32!SetCursor` at `0x18006bf3c`
- `USER32!SetCursor` at `0x18006bf3c`
- `USER32!LoadCursorW` at `0x18006bf17`
- `USER32!LoadCursorW` at `0x18006bf2c`
- `USER32!LoadCursorW` at `0x18006bf17`
- `USER32!LoadCursorW` at `0x18006bf2c`
- `USER32!FillRect` at `0x18006be93`
- `USER32!FillRect` at `0x18006be93`
- `USER32!GetWindowLongPtrW` at `0x18006bbe4`
- `USER32!GetWindowLongPtrW` at `0x18006bbe4`
- `USER32!DefWindowProcW` at `0x18006bfe9`
- `USER32!DefWindowProcW` at `0x18006bfe9`
- `USER32!UpdateWindow` at `0x18006bd27`
- `USER32!UpdateWindow` at `0x18006bd27`
- `USER32!GetKeyboardLayout` at `0x18006c273`
- `USER32!GetKeyboardLayout` at `0x18006c273`

## pseudocode

```c
__int64 __fastcall TV_WndProc(HWND hWnd, UINT Msg, CHAR *lpMultiByteStr, LPARAM lParam)
{
  LONG_PTR WindowLongPtrW; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // r9d
  __int64 v12; // rdi
  int v13; // eax
  unsigned int v14; // ecx
  __int64 result; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  HCURSOR CursorW; // rax
  int v21; // eax
  int v22; // ecx
  HWND v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rdx
  int v26; // r15d
  LONG WindowLongW; // eax
  unsigned int v28; // edx
  __int64 v29; // r8
  int v30; // eax
  int v31; // ecx
  int v32; // eax
  __int64 v33; // r8
  int v34; // edx
  int v35; // r9d
  __int64 v36; // r14
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 inserted; // rbx
  char *v40; // rcx
  __int64 v41; // rdx
  int v42; // r15d
  __int64 v43; // r14
  __int64 v44; // rbx
  __int64 v45; // rax
  char *v46; // rcx
  HWND v47; // rbx
  char *v48; // rbx
  __int64 v49; // rdi
  unsigned int v50; // ecx
  __int64 (__fastcall *v51)(); // r9
  struct tagTRACKMOUSEEVENT *p_EventTrack; // rdx
  int v53; // ebx
  int v54; // r15d
  HWND v55; // rbx
  _DWORD v56[4]; // [rsp+30h] [rbp-59h] BYREF
  __int128 v57; // [rsp+40h] [rbp-49h] BYREF
  __int128 v58; // [rsp+50h] [rbp-39h]
  _OWORD v59[2]; // [rsp+60h] [rbp-29h] BYREF
  struct tagTRACKMOUSEEVENT EventTrack; // [rsp+80h] [rbp-9h] BYREF

  WindowLongPtrW = GetWindowLongPtrW(hWnd, 0);
  v12 = WindowLongPtrW;
  if ( !WindowLongPtrW )
  {
    if ( Msg == 1 )
    {
      CCCreateWindow();
      return TV_OnCreate(hWnd);
    }
    return DefWindowProcW(hWnd, Msg, (WPARAM)lpMultiByteStr, lParam);
  }
  if ( Msg - 512 > 0xD
    || (*(_DWORD *)(WindowLongPtrW + 16) & 0x200) == 0
    || (v13 = *(_DWORD *)(WindowLongPtrW + 56), (v13 & 0x200) != 0) )
  {
    if ( Msg == g_uDragImages )
      return TV_GenerateDragImage(v12, lParam);
  }
  else
  {
    *(_QWORD *)&EventTrack.dwHoverTime = 0;
    *(_DWORD *)(v12 + 56) = v13 | 0x200;
    EventTrack.hwndTrack = *(HWND *)v12;
    EventTrack.cbSize = 24;
    EventTrack.dwFlags = 2;
    TrackMouseEvent(&EventTrack);
  }
  if ( Msg > 0x1108 )
  {
    if ( Msg <= 0x1132 )
    {
      if ( Msg != 4402 )
      {
        switch ( Msg )
        {
          case 0x1109u:
            return TV_SetImageList(v12, lParam, (unsigned int)lpMultiByteStr);
          case 0x110Au:
            return TV_GetNextItem(v12, lParam, lpMultiByteStr);
          case 0x110Bu:
            LODWORD(result) = TV_SelectItem((HWND *)v12, (__int64)lpMultiByteStr, (HWND)lParam, 3, 0);
            return (int)result;
          case 0x110Cu:
            if ( !lParam )
              return 0;
            LODWORD(result) = TV_OnGetItemA(v12, lParam);
            return (int)result;
          case 0x110Du:
            if ( !lParam )
              return 0;
            v42 = -1;
            v43 = 0;
            if ( lParam == -1 )
              goto LABEL_227;
            if ( (*(_BYTE *)lParam & 1) == 0 )
              goto LABEL_227;
            v44 = *(_QWORD *)(lParam + 24);
            if ( (unsigned __int64)(v44 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
              goto LABEL_227;
            v45 = ProduceWFromA(*(_DWORD *)(v12 + 28), *(LPCCH *)(lParam + 24));
            *(_QWORD *)(lParam + 24) = v45;
            if ( v45 )
            {
              v43 = v44;
LABEL_227:
              v42 = TV_SetItem(v12, lParam);
              if ( v43 )
              {
                v46 = *(char **)(lParam + 24);
                if ( (unsigned __int64)(v46 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                  LocalFree(v46);
                *(_QWORD *)(lParam + 24) = v43;
              }
            }
            else
            {
              *(_QWORD *)(lParam + 24) = v44;
            }
            return v42;
          case 0x110Eu:
            v48 = 0;
            if ( lpMultiByteStr )
              v48 = (char *)ProduceWFromA(*(_DWORD *)(v12 + 28), lpMultiByteStr);
            v49 = TV_EditLabel(v12, lParam, v48);
            if ( (unsigned __int64)(v48 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              LocalFree(v48);
            return v49;
          case 0x110Fu:
            return *(_QWORD *)(v12 + 344);
          case 0x1110u:
            result = *(unsigned __int16 *)(v12 + 316);
            if ( (_DWORD)lpMultiByteStr )
            {
              v50 = result + 1;
              if ( *(__int16 *)(v12 + 312) == (_DWORD)result * *(__int16 *)(v12 + 302) )
                return *(unsigned __int16 *)(v12 + 316);
              return v50;
            }
            return result;
          case 0x1111u:
            if ( !lParam )
              return 0;
            result = TV_CheckHit(v12, *(unsigned int *)lParam, *(unsigned int *)(lParam + 4), lParam + 8);
            *(_QWORD *)(lParam + 16) = result;
            return result;
          case 0x1112u:
            return (__int64)TV_CreateDragImage(v12, lParam);
          case 0x1113u:
            *(_QWORD *)&EventTrack.cbSize = lParam;
            *(_OWORD *)&EventTrack.hwndTrack = 0;
            v51 = 0;
            p_EventTrack = &EventTrack;
            goto LABEL_252;
          case 0x1114u:
            if ( !(unsigned int)ValidateTreeItem(lParam, 0) )
              return 0;
            TV_ExpandParents(v12, lParam, 1);
            LODWORD(result) = TV_ScrollIntoView(v12, lParam);
            return (int)result;
          case 0x1115u:
            v51 = TV_CompareItems;
            p_EventTrack = (struct tagTRACKMOUSEEVENT *)lParam;
LABEL_252:
            LODWORD(result) = TV_SortCB(v12, p_EventTrack, v10, v51);
            return (int)result;
          case 0x1116u:
            LODWORD(result) = TV_DismissEdit(v12, (unsigned int)lpMultiByteStr);
            return (int)result;
          case 0x1117u:
            v47 = *(HWND *)v12;
            if ( GetFocus() != v47 )
              return 0;
            LODWORD(result) = GetIncrementSearchStringA(v12 + 384, *(unsigned int *)(v12 + 28), lParam);
            return (int)result;
          case 0x1118u:
            result = *(_QWORD *)(v12 + 360);
            *(_QWORD *)(v12 + 360) = lpMultiByteStr;
            return result;
          case 0x1119u:
            return *(_QWORD *)(v12 + 360);
          case 0x111Au:
            LODWORD(result) = TV_SetInsertMark(v12, lParam, (unsigned int)lpMultiByteStr);
            return (int)result;
          case 0x111Bu:
            *(_DWORD *)(v12 + 56) &= ~0x800u;
            inserted = *(__int16 *)(v12 + 302);
            *(_WORD *)(v12 + 302) = (_WORD)lpMultiByteStr;
            *(_DWORD *)(v12 + 56) |= lpMultiByteStr + 1 != 0 ? 0x800 : 0;
            TV_SetItemHeight(v12);
            return inserted;
          case 0x111Cu:
            return *(__int16 *)(v12 + 302);
          case 0x111Du:
            inserted = *(unsigned int *)(v12 + 284);
            TV_OnSetBkColor(v12, lParam);
            return inserted;
          case 0x111Eu:
            inserted = *(unsigned int *)(v12 + 280);
            *(_DWORD *)(v12 + 280) = lParam;
            goto LABEL_212;
          case 0x111Fu:
            return *(unsigned int *)(v12 + 284);
          case 0x1120u:
            return *(unsigned int *)(v12 + 280);
          case 0x1121u:
            result = *(unsigned int *)(v12 + 336);
            *(_DWORD *)(v12 + 336) = (_DWORD)lpMultiByteStr;
            return result;
          case 0x1122u:
            return *(unsigned int *)(v12 + 336);
          case 0x1123u:
            v53 = *(unsigned __int16 *)(v12 + 306);
            v54 = *(unsigned __int16 *)(v12 + 304);
            if ( ((unsigned __int8)lpMultiByteStr & 2) != 0 )
              *(_WORD *)(v12 + 306) = WORD1(lParam);
            if ( ((unsigned __int8)lpMultiByteStr & 1) != 0 )
              *(_WORD *)(v12 + 304) = lParam;
            TV_CalcScrollBars(v12);
            return (v53 << 16) | v54;
          case 0x1124u:
            LODWORD(result) = *(_DWORD *)(v12 + 304);
            return (int)result;
          case 0x1125u:
            inserted = *(unsigned int *)(v12 + 288);
            *(_DWORD *)(v12 + 288) = lParam;
            TV_InvalidateInsertMarkRect(v12, 0);
            return inserted;
          case 0x1126u:
            return *(unsigned int *)(v12 + 288);
          case 0x1127u:
            v58 = 0;
            *(_QWORD *)&v57 = 8;
            memset(v59, 0, 28);
            DWORD1(v58) = lParam;
            *((_QWORD *)&v57 + 1) = lpMultiByteStr;
            if ( !(unsigned int)TV_OnGetItem(v12, &v57) )
              return 0;
            return (unsigned int)v58;
          case 0x1128u:
            inserted = *(unsigned int *)(v12 + 292);
            *(_DWORD *)(v12 + 292) = lParam;
LABEL_212:
            TV_CreateIndentBmps(v12);
            return inserted;
          case 0x1129u:
            return *(unsigned int *)(v12 + 292);
          default:
            goto LABEL_278;
        }
      }
      return TV_InsertItem(v12, lParam);
    }
    switch ( Msg )
    {
      case 0x113Eu:
        LODWORD(result) = TV_OnGetItem(v12, lParam);
        break;
      case 0x113Fu:
        LODWORD(result) = TV_SetItem(v12, lParam);
        break;
      case 0x1140u:
        v55 = *(HWND *)v12;
        if ( GetFocus() != v55 )
          return 0;
        LODWORD(result) = GetIncrementSearchString(v12 + 384, lParam);
        break;
      case 0x1141u:
        return TV_EditLabel(v12, lParam, lpMultiByteStr);
      case 0x200Au:
        LODWORD(result) = TV_TranslateAccelerator(hWnd, lParam);
        break;
      case 0x2100u:
        TV_CalcScrollBars(v12);
        return 0;
      default:
        goto LABEL_278;
    }
    return (int)result;
  }
  if ( Msg == 4360 )
  {
    if ( !lpMultiByteStr )
      return *(_QWORD *)(v12 + 152);
    if ( lpMultiByteStr != (CHAR *)2 )
      return 0;
    return *(_QWORD *)(v12 + 160);
  }
  if ( Msg > 0x104 )
  {
    if ( Msg <= 0x207 )
    {
      if ( Msg == 519 )
      {
        SetFocus(hWnd);
        return DefWindowProcW(hWnd, Msg, (WPARAM)lpMultiByteStr, lParam);
      }
      if ( Msg > 0x128 )
      {
        switch ( Msg )
        {
          case 0x200u:
            TV_OnMouseMove(v12, (unsigned int)lParam, lpMultiByteStr);
            return 0;
          case 0x201u:
          case 0x203u:
            TV_ButtonDown(v12, Msg, (_DWORD)lpMultiByteStr, (__int16)lParam, SWORD1(lParam), 0);
            return 0;
          case 0x204u:
            TV_SendRButtonDown(v12, (unsigned int)(__int16)lParam, (unsigned int)SWORD1(lParam));
            return 0;
        }
        goto LABEL_278;
      }
      if ( Msg == 296 )
      {
        if ( (unsigned int)CCOnUIState(v12, v9, (unsigned int)lpMultiByteStr & 0x1FFFF) )
        {
          v25 = *(_QWORD *)(v12 + 72);
          if ( v25 )
            TV_InvalidateItem(v24, v25, 1);
        }
        return DefWindowProcW(hWnd, Msg, (WPARAM)lpMultiByteStr, lParam);
      }
      if ( Msg == 271 )
      {
        if ( g_fDBCSInputEnabled && ((unsigned __int64)GetKeyboardLayout(0) & 0xF000FFFF) == 0xE0000412 )
        {
          if ( !(unsigned int)TV_OnImeComposition(v12, lpMultiByteStr, lParam) )
            return 0;
          lParam &= ~0x800uLL;
        }
        return DefWindowProcW(hWnd, Msg, (WPARAM)lpMultiByteStr, lParam);
      }
      if ( Msg != 273 )
      {
        switch ( Msg )
        {
          case 0x113u:
            TV_Timer(v12, (unsigned int)lpMultiByteStr);
            return 0;
          case 0x114u:
            TV_HorzScroll(v12, (unsigned __int16)lpMultiByteStr, WORD1(lpMultiByteStr));
            return 0;
          case 0x115u:
            TV_VertScroll(v12, (unsigned __int16)lpMultiByteStr, WORD1(lpMultiByteStr));
            return 0;
        }
        goto LABEL_278;
      }
      v23 = *(HWND *)(v12 + 344);
      if ( (HWND)lParam == v23 )
      {
        switch ( WORD1(lpMultiByteStr) )
        {
          case 0x28u:
            *(_DWORD *)(v12 + 56) |= 0x80u;
            break;
          case 0x29u:
            *(_DWORD *)(v12 + 56) &= ~0x80u;
            break;
          case 0x200u:
            if ( !(unsigned int)TV_DismissEdit(v12, 0) )
              return 0;
            break;
          case 0x400u:
            SetWindowLongPtrW(v23, -12, 1);
            TV_SetEditSize(v12);
            break;
        }
        if ( IsWindow((HWND)lParam) )
          SendMessageW(*(HWND *)(v12 + 8), 0x111u, (unsigned int)lpMultiByteStr, lParam);
        return 0;
      }
      return 0;
    }
    if ( Msg == 675 )
    {
      v41 = *(_QWORD *)(v12 + 104);
      *(_DWORD *)(v12 + 56) &= ~0x200u;
      TV_InvalidateItem(v12, v41, 1);
      *(_QWORD *)(v12 + 104) = 0;
      TV_PopBubble(v12);
      return 0;
    }
    if ( Msg == 792 )
      goto LABEL_198;
    if ( Msg != 4352 )
    {
      switch ( Msg )
      {
        case 0x1101u:
          TV_DismissEdit(v12, 1);
          LODWORD(result) = TV_DeleteItem(v12, lParam, 0);
          break;
        case 0x1102u:
          if ( !(unsigned int)ValidateTreeItem(lParam, 0) )
            return 0;
          LODWORD(result) = TV_Expand(v12, lpMultiByteStr, lParam, 0);
          break;
        case 0x1104u:
          if ( !lParam || !(unsigned int)ValidateTreeItem(*(_QWORD *)lParam, 0) )
            return 0;
          LODWORD(result) = TV_GetItemRect(v12, *(_QWORD *)lParam, lParam, (unsigned int)lpMultiByteStr);
          break;
        case 0x1105u:
          return *(unsigned int *)(v12 + 324);
        case 0x1106u:
          return *(__int16 *)(v12 + 308);
        case 0x1107u:
          TV_SetIndent(v12, lpMultiByteStr);
          *(_DWORD *)(v12 + 56) |= 0x100u;
          return 0;
        case 0x20Au:
          gcWheelDelta -= SWORD1(lpMultiByteStr);
          v26 = gcWheelDelta / 120;
          if ( gcWheelDelta / 120 )
            gcWheelDelta %= 120;
          if ( ((unsigned __int8)lpMultiByteStr & 0xC) == 0 )
          {
            if ( g_ucScrollLines )
            {
              if ( v26 )
              {
                WindowLongW = GetWindowLongW(hWnd, -16);
                if ( (WindowLongW & 0x300000) != 0 )
                {
                  if ( (WindowLongW & 0x200000) != 0 )
                  {
                    v28 = 1;
                    if ( *(unsigned __int16 *)(v12 + 316) - 1 >= 1 )
                      v28 = *(unsigned __int16 *)(v12 + 316) - 1;
                    if ( g_ucScrollLines < v28 )
                      v28 = g_ucScrollLines;
                    v29 = 0;
                    v30 = v28 * v26 + *(unsigned __int16 *)(*(_QWORD *)(v12 + 328) + 48LL);
                    if ( v30 >= 0 )
                      v29 = (unsigned int)v30;
                    TV_VertScroll(v12, 4, v29);
                  }
                  else
                  {
                    v31 = 5;
                    if ( *(__int16 *)(v12 + 310) - 5 >= 5 )
                      v31 = *(__int16 *)(v12 + 310) - 5;
                    v32 = g_ucScrollLines;
                    if ( v31 / 5 < (unsigned int)g_ucScrollLines )
                      v32 = v31 / 5;
                    v33 = 0;
                    v34 = 5 * v32 * v26 + *(__int16 *)(v12 + 318);
                    if ( v34 >= 0 )
                      v33 = (unsigned int)v34;
                    TV_HorzScroll(v12, 4, v33);
                  }
                }
              }
            }
            return 1;
          }
          if ( ((unsigned __int8)lpMultiByteStr & 4) != 0 )
          {
            EventTrack.cbSize = (__int16)lParam;
            v56[0] = 0;
            EventTrack.dwFlags = SWORD1(lParam);
            ScreenToClient(hWnd, (LPPOINT)&EventTrack);
            if ( TV_CheckHit(v12, EventTrack.cbSize, EventTrack.dwFlags, v56) )
            {
              if ( (v56[0] & 0x56) != 0 )
              {
                v35 = 3;
                if ( SWORD1(lpMultiByteStr) <= 0 )
                  v35 = 5;
                if ( (v35 & 2) != 0 || v56[0] == 16 )
                {
                  TV_ButtonDown(v12, 513, 0, EventTrack.cbSize, EventTrack.dwFlags, v35);
                  return 1;
                }
              }
            }
          }
          return DefWindowProcW(hWnd, Msg, (WPARAM)lpMultiByteStr, lParam);
        default:
LABEL_278:
          *(_QWORD *)&EventTrack.cbSize = 0;
          if ( (unsigned int)CCWndProc(v12, Msg, (_DWORD)lpMultiByteStr, v11, (__int64)&EventTrack) )
            return *(_QWORD *)&EventTrack.cbSize;
          return DefWindowProcW(hWnd, Msg, (WPARAM)lpMultiByteStr, lParam);
      }
      return (int)result;
    }
    if ( !lParam )
      return 0;
    v36 = 0;
    if ( lParam != -1 && (*(_BYTE *)(lParam + 16) & 1) != 0 )
    {
      v37 = *(_QWORD *)(lParam + 40);
      if ( (unsigned __int64)(v37 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v38 = ProduceWFromA(*(_DWORD *)(v12 + 28), *(LPCCH *)(lParam + 40));
        *(_QWORD *)(lParam + 40) = v38;
        if ( !v38 )
        {
          *(_QWORD *)(lParam + 40) = v37;
          return 0;
        }
        v36 = v37;
      }
    }
    inserted = TV_InsertItem(v12, lParam);
    if ( v36 )
    {
      v40 = *(char **)(lParam + 40);
      if ( (unsigned __int64)(v40 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        LocalFree(v40);
      *(_QWORD *)(lParam + 40) = v36;
    }
    return inserted;
  }
  if ( Msg == 260 )
  {
    TV_KeyDown(v12, lpMultiByteStr);
    goto LABEL_278;
  }
  if ( Msg <= 0x20 )
  {
    if ( Msg != 32 )
    {
      if ( Msg <= 0xB )
      {
        if ( Msg == 11 )
        {
          TV_OnSetRedraw(v12, (unsigned int)lpMultiByteStr);
          return 0;
        }
        if ( Msg == 2 )
        {
          _InterlockedAdd(&g_dwWindowCount, 0xFFFFFFFF);
          TV_DestroyTree((char *)v12);
          return 0;
        }
        v11 = 3;
        switch ( Msg )
        {
          case 5u:
            TV_SizeWnd(v12, (unsigned int)(__int16)lParam, (unsigned int)SWORD1(lParam));
            return 0;
          case 7u:
            *(_DWORD *)(v12 + 56) |= 4u;
            v17 = *(_QWORD *)(v12 + 72);
            if ( v17 )
            {
              TV_InvalidateItem(v12, v17, 1);
              MyNotifyWinEvent(32773, hWnd, 4294967292LL);
            }
            else
            {
              TV_SelectItem((HWND *)v12, 9, *(HWND *)(v12 + 328), 3, 4096);
            }
            CCSendNotify(v12, -7, 0);
            return 0;
          case 8u:
            *(_DWORD *)(v12 + 56) &= ~4u;
            v16 = *(_QWORD *)(v12 + 72);
            gcWheelDelta = 0;
            if ( v16 )
            {
              TV_InvalidateItem(v12, v16, 1);
              UpdateWindow(*(HWND *)v12);
            }
            CCSendNotify(v12, -8, 0);
            *(_DWORD *)(v12 + 404) = 0;
            *(_DWORD *)(v12 + 384) = 0;
            return 0;
          case 0xAu:
            v14 = *(_DWORD *)(v12 + 16) & 0xF7FFFFFF;
            if ( !lpMultiByteStr )
              v14 = *(_DWORD *)(v12 + 16) | 0x8000000;
            *(_DWORD *)(v12 + 16) = v14;
            goto LABEL_22;
        }
        goto LABEL_278;
      }
      if ( Msg != 15 )
      {
        if ( Msg != 20 )
        {
          if ( Msg == 21 )
          {
            InitGlobalColors();
LABEL_22:
            TV_CreateIndentBmps(v12);
            return 0;
          }
          if ( Msg == 26 )
          {
            if ( (unsigned __int64)lpMultiByteStr <= 0x2A )
            {
              v18 = 0x40400000001LL;
              if ( _bittest64(&v18, (unsigned __int64)lpMultiByteStr) )
              {
                if ( (*(_BYTE *)(v12 + 56) & 0x40) != 0 )
                  TV_OnSetFont(v12, 0);
                if ( (*(_DWORD *)(v12 + 56) & 0x100) == 0 )
                  TV_SetIndent(v12, 0);
              }
            }
            return 0;
          }
          goto LABEL_278;
        }
        *(_OWORD *)&EventTrack.cbSize = 0;
        TV_GetBackgroundBrush(v12, lpMultiByteStr);
        GetClipBox((HDC)lpMultiByteStr, (LPRECT)&EventTrack);
        FillRect((HDC)lpMultiByteStr, (const RECT *)&EventTrack, *(HBRUSH *)(v12 + 192));
        return 1;
      }
LABEL_198:
      TV_Paint(v12, lpMultiByteStr);
      return 0;
    }
    *(_QWORD *)&v59[1] = lParam;
    v57 = 0;
    v58 = 0;
    v59[0] = 0;
    v19 = TV_ItemAtCursor(v12, 0);
    if ( v19 )
    {
      *((_QWORD *)&v58 + 1) = v19;
      *(_QWORD *)&v59[0] = *(_QWORD *)(v19 + 32);
    }
    else
    {
      *((_QWORD *)&v58 + 1) = 0;
      *(_QWORD *)&v59[0] = 0;
    }
    if ( CCSendNotify(v12, -17, (LPARAM)&v57) )
      return 0;
    if ( (*(_DWORD *)(v12 + 16) & 0x200) != 0 && *(_QWORD *)(v12 + 104) )
    {
      CursorW = *(HCURSOR *)(v12 + 168);
      if ( !CursorW )
      {
        CursorW = LoadCursorW(0, (LPCWSTR)0x7F89);
        if ( !CursorW )
          CursorW = LoadCursorW(g_hinst, (LPCWSTR)0x6C);
        *(_QWORD *)(v12 + 168) = CursorW;
      }
      SetCursor(CursorW);
      return 1;
    }
    return DefWindowProcW(hWnd, Msg, (WPARAM)lpMultiByteStr, lParam);
  }
  switch ( Msg )
  {
    case '0':
      TV_OnSetFont(v12, (HFONT)lpMultiByteStr);
      return 0;
    case '1':
      return *(_QWORD *)(v12 + 200);
    case '=':
      if ( (_DWORD)lParam == -12 )
        return 65561;
      return DefWindowProcW(hWnd, Msg, (WPARAM)lpMultiByteStr, lParam);
  }
  if ( Msg != 78 )
  {
    switch ( Msg )
    {
      case 0x55u:
        return CIHandleNotifyFormat(v12, lParam);
      case 0x7Du:
        TV_OnStyleChanged(v12, lpMultiByteStr, lParam);
        return 0;
      case 0x87u:
        return 129;
    }
    if ( Msg != 256 )
    {
      if ( Msg != 258 )
        goto LABEL_278;
      v21 = *(_DWORD *)(v12 + 176);
      if ( !v21 )
      {
        TV_OnChar(v12, (unsigned __int16)lpMultiByteStr, (unsigned int)(__int16)lParam);
        return 0;
      }
      *(_DWORD *)(v12 + 176) = v21 - 1;
      return 1;
    }
    if ( (unsigned int)TV_KeyDown(v12, lpMultiByteStr) )
    {
      *(_DWORD *)(v12 + 404) = 0;
      *(_DWORD *)(v12 + 384) = 0;
    }
    return DefWindowProcW(hWnd, Msg, (WPARAM)lpMultiByteStr, lParam);
  }
  v22 = *(_DWORD *)(lParam + 16);
  if ( (unsigned int)(v22 + 950) > 0x32 )
  {
    if ( *(_QWORD *)lParam != *(_QWORD *)(v12 + 360) )
      return 0;
    switch ( v22 )
    {
      case -530:
        TV_HandleNeedText(v12, lParam);
        return 0;
      case -521:
        LODWORD(result) = TV_HandleTTNShow(v12, lParam);
        return (int)result;
      case -520:
        TV_HandleNeedTextA(v12, lParam);
        return 0;
      case -12:
        LODWORD(result) = TV_HandleTTCustomDraw(v12, lParam);
        return (int)result;
    }
    return 0;
  }
  if ( v22 == -902 )
  {
    if ( *(_DWORD *)(lParam + 24) == 2 )
      *(_DWORD *)(lParam + 32) = *(_DWORD *)(v12 + 320) * *(__int16 *)(v12 + 302);
  }
  else if ( v22 == -901 )
  {
    return TV_OnScroll(v12, lParam);
  }
  return 0;
}

```

## disassembly

```asm
0x18006bbb0  push    rbp
0x18006bbb2  push    rbx
0x18006bbb3  push    rsi
0x18006bbb4  push    rdi
0x18006bbb5  push    r12
0x18006bbb7  push    r13
0x18006bbb9  push    r14
0x18006bbbb  push    r15
0x18006bbbd  lea     rbp, [rsp-1Fh]
0x18006bbc2  sub     rsp, 0A8h
0x18006bbc9  mov     rax, cs:__security_cookie
0x18006bbd0  xor     rax, rsp
0x18006bbd3  mov     [rbp+57h+var_48], rax
0x18006bbd7  mov     ebx, edx
0x18006bbd9  mov     rsi, r9
0x18006bbdc  xor     edx, edx; nIndex
0x18006bbde  mov     r14, r8
0x18006bbe1  mov     r12, rcx
0x18006bbe4  call    cs:__imp_GetWindowLongPtrW
0x18006bbea  xor     r13d, r13d
0x18006bbed  mov     rdi, rax
0x18006bbf0  test    rax, rax
0x18006bbf3  jz      loc_18006CBF7
0x18006bbf9  lea     ecx, [rbx-200h]
0x18006bbff  mov     r15d, 200h
0x18006bc05  cmp     ecx, 0Dh
0x18006bc08  ja      loc_18006BCE6
0x18006bc0e  test    [rax+10h], r15d
0x18006bc12  jz      loc_18006BCE6
0x18006bc18  mov     eax, [rax+38h]
0x18006bc1b  test    r15d, eax
0x18006bc1e  jnz     loc_18006BCE6
0x18006bc24  or      eax, r15d
0x18006bc27  mov     qword ptr [rbp+57h+EventTrack.dwHoverTime], r13
0x18006bc2b  mov     [rdi+38h], eax
0x18006bc2e  lea     rcx, [rbp+57h+EventTrack]; lpEventTrack
0x18006bc32  mov     rax, [rdi]
0x18006bc35  mov     [rbp+57h+EventTrack.hwndTrack], rax
0x18006bc39  mov     [rbp+57h+EventTrack.cbSize], 18h
0x18006bc40  mov     [rbp+57h+EventTrack.dwFlags], 2
0x18006bc47  call    _TrackMouseEvent
0x18006bc4c  mov     eax, 1108h
0x18006bc51  cmp     ebx, eax
0x18006bc53  ja      loc_18006C70E
0x18006bc59  jz      loc_18006C6E7
0x18006bc5f  mov     eax, 104h
0x18006bc64  cmp     ebx, eax
0x18006bc66  ja      loc_18006C130
0x18006bc6c  jz      loc_18006C120
0x18006bc72  cmp     ebx, 20h ; ' '
0x18006bc75  ja      loc_18006BF44
0x18006bc7b  jz      loc_18006BE9E
0x18006bc81  cmp     ebx, 0Bh
0x18006bc84  ja      loc_18006BDF1
0x18006bc8a  jz      loc_18006BDE1
0x18006bc90  mov     eax, ebx
0x18006bc92  sub     eax, 2
0x18006bc95  jz      loc_18006BDC8
0x18006bc9b  mov     r9d, 3
0x18006bca1  sub     eax, r9d
0x18006bca4  jz      loc_18006BDAD
0x18006bcaa  sub     eax, 2
0x18006bcad  jz      loc_18006BD4C
0x18006bcb3  sub     eax, 1
0x18006bcb6  jz      short loc_18006BD02
0x18006bcb8  cmp     eax, 2
0x18006bcbb  jnz     def_18006C741; jumptable 000000018006C741 default case
0x18006bcc1  mov     ecx, [rdi+10h]
0x18006bcc4  mov     eax, ecx
0x18006bcc6  bts     eax, 1Bh
0x18006bcca  btr     ecx, 1Bh
0x18006bcce  test    r14, r14
0x18006bcd1  cmovz   ecx, eax
0x18006bcd4  mov     [rdi+10h], ecx
0x18006bcd7  mov     rcx, rdi
0x18006bcda  call    TV_CreateIndentBmps
0x18006bcdf  xor     eax, eax
0x18006bce1  jmp     loc_18006BFEF
0x18006bce6  cmp     ebx, cs:g_uDragImages
0x18006bcec  jnz     loc_18006BC4C
0x18006bcf2  mov     rdx, rsi
0x18006bcf5  mov     rcx, rdi
0x18006bcf8  call    TV_GenerateDragImage
0x18006bcfd  jmp     loc_18006BFEF
0x18006bd02  and     dword ptr [rdi+38h], 0FFFFFFFBh
0x18006bd06  mov     rdx, [rdi+48h]
0x18006bd0a  mov     cs:gcWheelDelta, r13d
0x18006bd11  test    rdx, rdx
0x18006bd14  jz      short loc_18006BD2D
0x18006bd16  mov     r8d, 1
0x18006bd1c  mov     rcx, rdi
0x18006bd1f  call    TV_InvalidateItem
0x18006bd24  mov     rcx, [rdi]; hWnd
0x18006bd27  call    cs:__imp_UpdateWindow
0x18006bd2d  xor     r8d, r8d
0x18006bd30  mov     rcx, rdi
0x18006bd33  lea     edx, [r8-8]
0x18006bd37  call    CCSendNotify
0x18006bd3c  mov     [rdi+194h], r13d
0x18006bd43  mov     [rdi+180h], r13d
0x18006bd4a  jmp     short loc_18006BCDF
0x18006bd4c  or      dword ptr [rdi+38h], 4
0x18006bd50  mov     rcx, rdi
0x18006bd53  mov     rdx, [rdi+48h]
0x18006bd57  test    rdx, rdx
0x18006bd5a  jz      short loc_18006BD80
0x18006bd5c  mov     r8d, 1
0x18006bd62  call    TV_InvalidateItem
0x18006bd67  mov     r9, [rdi+48h]
0x18006bd6b  mov     r8d, 0FFFFFFFCh
0x18006bd71  mov     rdx, r12
0x18006bd74  mov     ecx, 8005h
0x18006bd79  call    MyNotifyWinEvent
0x18006bd7e  jmp     short loc_18006BD99
0x18006bd80  mov     r8, [rdi+148h]
0x18006bd87  mov     edx, 9
0x18006bd8c  mov     dword ptr [rsp+0E0h+var_C0], 1000h
0x18006bd94  call    TV_SelectItem
0x18006bd99  xor     r8d, r8d
0x18006bd9c  mov     rcx, rdi
0x18006bd9f  lea     edx, [r8-7]
0x18006bda3  call    CCSendNotify
0x18006bda8  jmp     loc_18006BCDF
0x18006bdad  mov     rax, rsi
0x18006bdb0  movsx   edx, si
0x18006bdb3  shr     rax, 10h
0x18006bdb7  mov     rcx, rdi
0x18006bdba  movsx   r8d, ax
0x18006bdbe  call    TV_SizeWnd
0x18006bdc3  jmp     loc_18006BCDF
0x18006bdc8  or      r15, 0FFFFFFFFFFFFFFFFh
0x18006bdcc  lock add cs:g_dwWindowCount, r15d
0x18006bdd4  mov     rcx, rdi; hMem
0x18006bdd7  call    TV_DestroyTree
0x18006bddc  jmp     loc_18006BCDF
0x18006bde1  mov     edx, r14d
0x18006bde4  mov     rcx, rdi
0x18006bde7  call    TV_OnSetRedraw
0x18006bdec  jmp     loc_18006BCDF
0x18006bdf1  mov     eax, ebx
0x18006bdf3  sub     eax, 0Fh
0x18006bdf6  jz      loc_18006C6AF
0x18006bdfc  mov     ecx, 5
0x18006be01  sub     eax, ecx
0x18006be03  jz      short loc_18006BE66
0x18006be05  sub     eax, 1
0x18006be08  jz      short loc_18006BE5C
0x18006be0a  cmp     eax, ecx
0x18006be0c  jnz     def_18006C741; jumptable 000000018006C741 default case
0x18006be12  cmp     r14, 2Ah ; '*'
0x18006be16  ja      loc_18006BCDF
0x18006be1c  mov     rax, 40400000001h
0x18006be26  bt      rax, r14
0x18006be2a  jnb     loc_18006BCDF
0x18006be30  test    byte ptr [rdi+38h], 40h
0x18006be34  jz      short loc_18006BE40
0x18006be36  xor     edx, edx
0x18006be38  mov     rcx, rdi
0x18006be3b  call    TV_OnSetFont
0x18006be40  test    dword ptr [rdi+38h], 100h
0x18006be47  jnz     loc_18006BCDF
0x18006be4d  xor     edx, edx
0x18006be4f  mov     rcx, rdi
0x18006be52  call    TV_SetIndent
0x18006be57  jmp     loc_18006BCDF
0x18006be5c  call    InitGlobalColors
0x18006be61  jmp     loc_18006BCD7
0x18006be66  xorps   xmm0, xmm0
0x18006be69  mov     rdx, r14
0x18006be6c  mov     rcx, rdi
0x18006be6f  movups  xmmword ptr [rbp+57h+EventTrack.cbSize], xmm0
0x18006be73  call    TV_GetBackgroundBrush
0x18006be78  lea     rdx, [rbp+57h+EventTrack]; lprect
0x18006be7c  mov     rcx, r14; hdc
0x18006be7f  call    cs:__imp_GetClipBox
0x18006be85  mov     r8, [rdi+0C0h]; hbr
0x18006be8c  lea     rdx, [rbp+57h+EventTrack]; lprc
0x18006be90  mov     rcx, r14; hDC
0x18006be93  call    cs:__imp_FillRect
0x18006be99  jmp     loc_18006BFA5
0x18006be9e  xorps   xmm0, xmm0
0x18006bea1  mov     [rbp+57h+var_70], rsi
0x18006bea5  xor     edx, edx
0x18006bea7  mov     rcx, rdi
0x18006beaa  movups  [rbp+57h+var_A0], xmm0
0x18006beae  movups  [rbp+57h+var_90], xmm0
0x18006beb2  movups  [rbp+57h+var_80], xmm0
0x18006beb6  call    TV_ItemAtCursor
0x18006bebb  test    rax, rax
0x18006bebe  jz      short loc_18006BECE
0x18006bec0  mov     qword ptr [rbp+57h+var_90+8], rax
0x18006bec4  mov     rax, [rax+20h]
0x18006bec8  mov     qword ptr [rbp+57h+var_80], rax
0x18006becc  jmp     short loc_18006BED6
0x18006bece  mov     qword ptr [rbp+57h+var_90+8], r13
0x18006bed2  mov     qword ptr [rbp+57h+var_80], r13
0x18006bed6  lea     r8, [rbp+57h+var_A0]
0x18006beda  mov     edx, 0FFFFFFEFh
0x18006bedf  mov     rcx, rdi
0x18006bee2  call    CCSendNotify
0x18006bee7  test    rax, rax
0x18006beea  jnz     loc_18006BCDF
0x18006bef0  test    [rdi+10h], r15d
0x18006bef4  jz      loc_18006BFDE
0x18006befa  cmp     [rdi+68h], r13
0x18006befe  jz      loc_18006BFDE
0x18006bf04  mov     rax, [rdi+0A8h]
0x18006bf0b  test    rax, rax
0x18006bf0e  jnz     short loc_18006BF39
0x18006bf10  mov     edx, 7F89h; lpCursorName
0x18006bf15  xor     ecx, ecx; hInstance
0x18006bf17  call    cs:__imp_LoadCursorW
0x18006bf1d  test    rax, rax
0x18006bf20  jnz     short loc_18006BF32
0x18006bf22  mov     rcx, cs:g_hinst; hInstance
0x18006bf29  lea     edx, [rax+6Ch]; lpCursorName
0x18006bf2c  call    cs:__imp_LoadCursorW
0x18006bf32  mov     [rdi+0A8h], rax
0x18006bf39  mov     rcx, rax; hCursor
0x18006bf3c  call    cs:__imp_SetCursor
0x18006bf42  jmp     short loc_18006BFA5
0x18006bf44  mov     eax, ebx
0x18006bf46  sub     eax, 30h ; '0'
0x18006bf49  jz      loc_18006C110
0x18006bf4f  sub     eax, 1
0x18006bf52  jz      loc_18006C104
0x18006bf58  sub     eax, 0Ch
0x18006bf5b  jz      loc_18006C0F1
0x18006bf61  sub     eax, 11h
0x18006bf64  jz      loc_18006C036
0x18006bf6a  sub     eax, 7
0x18006bf6d  jz      loc_18006C029
0x18006bf73  sub     eax, 28h ; '('
0x18006bf76  jz      loc_18006C016
0x18006bf7c  sub     eax, 0Ah
0x18006bf7f  jz      loc_18006C00F
0x18006bf85  sub     eax, 79h ; 'y'
0x18006bf88  jz      short loc_18006BFC1
0x18006bf8a  cmp     eax, 2
0x18006bf8d  jnz     def_18006C741; jumptable 000000018006C741 default case
0x18006bf93  mov     eax, [rdi+0B0h]
0x18006bf99  test    eax, eax
0x18006bf9b  jz      short loc_18006BFAC
0x18006bf9d  dec     eax
0x18006bf9f  mov     [rdi+0B0h], eax
0x18006bfa5  mov     eax, 1
0x18006bfaa  jmp     short loc_18006BFEF
0x18006bfac  movsx   r8d, si
0x18006bfb0  mov     rcx, rdi
0x18006bfb3  movzx   edx, r14w
0x18006bfb7  call    TV_OnChar
0x18006bfbc  jmp     loc_18006BCDF
0x18006bfc1  mov     rdx, r14
0x18006bfc4  mov     rcx, rdi
0x18006bfc7  call    TV_KeyDown
0x18006bfcc  test    eax, eax
0x18006bfce  jz      short loc_18006BFDE
0x18006bfd0  mov     [rdi+194h], r13d
0x18006bfd7  mov     [rdi+180h], r13d
0x18006bfde  mov     r9, rsi; lParam
0x18006bfe1  mov     r8, r14; wParam
0x18006bfe4  mov     edx, ebx; Msg
0x18006bfe6  mov     rcx, r12; hWnd
0x18006bfe9  call    cs:__imp_DefWindowProcW
0x18006bfef  mov     rcx, [rbp+57h+var_48]
0x18006bff3  xor     rcx, rsp; StackCookie
0x18006bff6  call    __security_check_cookie
0x18006bffb  add     rsp, 0A8h
0x18006c002  pop     r15
0x18006c004  pop     r14
0x18006c006  pop     r13
0x18006c008  pop     r12
0x18006c00a  pop     rdi
0x18006c00b  pop     rsi
0x18006c00c  pop     rbx
0x18006c00d  pop     rbp
0x18006c00e  retn
0x18006c00f  mov     eax, 81h
0x18006c014  jmp     short loc_18006BFEF
0x18006c016  mov     r8, rsi
0x18006c019  mov     rdx, r14
0x18006c01c  mov     rcx, rdi
0x18006c01f  call    TV_OnStyleChanged
0x18006c024  jmp     loc_18006BCDF
0x18006c029  mov     rdx, rsi
0x18006c02c  mov     rcx, rdi
0x18006c02f  call    CIHandleNotifyFormat
0x18006c034  jmp     short loc_18006BFEF
0x18006c036  mov     ecx, [rsi+10h]
0x18006c039  lea     eax, [rcx+3B6h]
0x18006c03f  cmp     eax, 32h ; '2'
0x18006c042  ja      short loc_18006C080
0x18006c044  cmp     ecx, 0FFFFFC7Ah
0x18006c04a  jz      short loc_18006C061
0x18006c04c  cmp     ecx, 0FFFFFC7Bh
0x18006c052  jnz     short loc_18006C078
0x18006c054  mov     rdx, rsi
0x18006c057  mov     rcx, rdi
0x18006c05a  call    TV_OnScroll
0x18006c05f  jmp     short loc_18006BFEF
  ... truncated ...
```
