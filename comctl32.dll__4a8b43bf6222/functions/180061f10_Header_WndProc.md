# Header_WndProc

- ea: `0x180061f10`
- end: `0x1800628e4`
- name: `Header_WndProc`
- size: `2516`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `45`
- tags: `installer_update`

## callees

- `0x1800115f0`
- `0x180018110`
- `0x1800183dc`
- `0x180018464`
- `0x1800197bc`
- `0x18002f950`
- `0x18002f9d0`
- `0x180035f8c`
- `0x180035fe0`
- `0x18003a400`
- `0x18005e4a0`
- `0x18005e7ec`
- `0x18005ea94`
- `0x18005f6f0`
- `0x18005f8fc`
- `0x18005fbb0`
- `0x18005fc74`
- `0x18005fd80`
- `0x18005fed8`
- `0x18005ffa0`
- `0x1800602d4`
- `0x180060484`
- `0x1800605a0`
- `0x1800607c8`
- `0x180060924`
- `0x180060990`
- `0x1800609e8`
- `0x180060cec`
- `0x180060e18`
- `0x180060ff8`
- `0x1800611c4`
- `0x180061440`
- `0x18006151c`
- `0x180061568`
- `0x1800616ac`
- `0x180061a0c`
- `0x180061b38`
- `0x180061c2c`
- `0x180061c78`
- `0x180061de4`
- `0x180061f10`
- `0x180062bfc`
- `0x180085890`
- `0x180085c90`
- `0x18008ea60`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180062026`
- `KERNEL32!LocalFree` at `0x180062026`
- `KERNEL32!LocalAlloc` at `0x180061f63`
- `KERNEL32!LocalAlloc` at `0x180061f63`
- `USER32!GetClientRect` at `0x18006256d`
- `USER32!GetClientRect` at `0x18006256d`
- `USER32!RedrawWindow` at `0x18006215e`
- `USER32!RedrawWindow` at `0x18006215e`
- `USER32!SetWindowLongPtrW` at `0x180061f85`
- `USER32!SetWindowLongPtrW` at `0x180062034`
- `USER32!SetWindowLongPtrW` at `0x180061f85`
- `USER32!SetWindowLongPtrW` at `0x180062034`
- `USER32!InvalidateRect` at `0x180062300`
- `USER32!InvalidateRect` at `0x180062300`
- `USER32!GetWindowLongPtrW` at `0x180061f45`
- `USER32!GetWindowLongPtrW` at `0x180061f45`
- `USER32!BeginPaint` at `0x180062579`
- `USER32!BeginPaint` at `0x180062579`
- `USER32!EndPaint` at `0x1800625a1`
- `USER32!EndPaint` at `0x1800625a1`
- `USER32!DefWindowProcW` at `0x180061f97`
- `USER32!DefWindowProcW` at `0x180061f97`
- `USER32!UpdateWindow` at `0x180062271`
- `USER32!UpdateWindow` at `0x18006241f`
- `USER32!UpdateWindow` at `0x180062271`
- `USER32!UpdateWindow` at `0x18006241f`
- `USER32!GetAsyncKeyState` at `0x180062061`
- `USER32!GetAsyncKeyState` at `0x180062061`
- `USER32!KillTimer` at `0x180062105`
- `USER32!KillTimer` at `0x180062105`

## pseudocode

```c
__int64 __fastcall Header_WndProc(HWND hWnd, UINT Msg, WPARAM wParam, unsigned __int64 lParam)
{
  LONG_PTR WindowLongPtrW; // rax
  int v9; // r9d
  unsigned int *v10; // rdi
  _QWORD *v11; // rax
  __int64 result; // rax
  struct _IMAGELIST *v13; // rcx
  struct _DSA *v14; // rbx
  struct _DSA *v15; // rcx
  int v16; // r12d
  __int64 v17; // r14
  HWND v18; // rcx
  __int64 v19; // rdx
  unsigned int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // r8d
  int v27; // edx
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rdx
  HWND v33; // rcx
  HDC v34; // rbx
  __int64 v35; // r8
  _DWORD *v36; // rdx
  int v37; // r9d
  bool v38; // zf
  int v39; // ecx
  unsigned int ItemOrder; // eax
  int *v41; // rax
  unsigned int v42; // esi
  __int64 i; // r15
  __int64 v44; // [rsp+30h] [rbp-69h] BYREF
  struct tagTRACKMOUSEEVENT EventTrack; // [rsp+38h] [rbp-61h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+50h] [rbp-49h] BYREF

  WindowLongPtrW = GetWindowLongPtrW(hWnd, 0);
  v10 = (unsigned int *)WindowLongPtrW;
  if ( !WindowLongPtrW )
  {
    if ( Msg != 129 )
      return DefWindowProcW(hWnd, Msg, wParam, lParam);
    v11 = LocalAlloc(0x40u, 0xE8u);
    if ( v11 )
    {
      *v11 = hWnd;
      v11[1] = *(_QWORD *)(lParam + 24);
      SetWindowLongPtrW(hWnd, 0, (LONG_PTR)v11);
      return DefWindowProcW(hWnd, Msg, wParam, lParam);
    }
    return 0;
  }
  if ( Msg == 130 )
  {
    v13 = *(struct _IMAGELIST **)(WindowLongPtrW + 80);
    if ( v13 )
      ImageList_Destroy(v13);
    Header_StopFilterEdit(v10, 1);
    v14 = (struct _DSA *)*((_QWORD *)v10 + 11);
    DSA_EnumCallback(v14, Header_DestroyItemCallback, 0);
    DSA_Destroy(v14);
    v15 = (struct _DSA *)*((_QWORD *)v10 + 17);
    *((_QWORD *)v10 + 11) = 0;
    if ( v15 )
    {
      DSA_Destroy(v15);
      *((_QWORD *)v10 + 17) = 0;
    }
    LocalFree(v10);
    SetWindowLongPtrW(hWnd, 0, 0);
    return 0;
  }
  v16 = -1;
  v17 = 1;
  if ( Msg == 533 || Msg == 516 || (GetAsyncKeyState(27) & 1) != 0 )
  {
    if ( *((_QWORD *)v10 + 19) )
    {
      memset(&Paint, 0, 0x40u);
      LODWORD(Paint.hdc) = 128;
      *(_DWORD *)&Paint.rgbReserved[8] = -1;
      ImageList_EndDrag();
      ImageList_Destroy(*((HIMAGELIST *)v10 + 19));
      *((_QWORD *)v10 + 19) = 0;
      Header_SetHotDivider(v10, 0xFFFFFFFFLL);
      Header_SendChange(v10, v10[24], 4294966985LL, &Paint);
    }
    else if ( (v10[26] & 0xC) != 0 )
    {
      memset(&Paint, 0, 0x40u);
      v18 = *(HWND *)v10;
      HIDWORD(Paint.hdc) = v10[30];
      LODWORD(Paint.hdc) = 1;
      v10[26] = 0;
      KillTimer(v18, 1u);
      CCReleaseCapture(v10);
      Header_SendChange(v10, v10[24], 4294966969LL, &Paint);
      if ( g_fDragFullWindows && *((char *)v10 + 16) < 0 )
      {
        v19 = v10[24];
        HIDWORD(Paint.hdc) = v10[30];
        LODWORD(Paint.hdc) = 1;
        Header_OnSetItem(v10, v19, &Paint);
        RedrawWindow(*(HWND *)v10, 0, 0, 5u);
      }
      else
      {
        Header_DrawDivider(v10, v10[28]);
      }
    }
  }
  if ( Msg - 512 <= 0xD && (v10[4] & 4) != 0 )
  {
    v20 = v10[25];
    if ( (v20 & 2) == 0 )
    {
      *(_QWORD *)&EventTrack.dwHoverTime = 0;
      v10[25] = v20 | 2;
      EventTrack.hwndTrack = *(HWND *)v10;
      EventTrack.cbSize = 24;
      EventTrack.dwFlags = 2;
      TrackMouseEvent(&EventTrack);
    }
  }
  if ( Msg > 0x1201 )
  {
    switch ( Msg )
    {
      case 0x1202u:
        LODWORD(result) = Header_OnDeleteItem(v10, (unsigned int)wParam);
        return (int)result;
      case 0x1203u:
        LODWORD(result) = Header_OnGetItemA(v10, (unsigned int)wParam, lParam);
        return (int)result;
      case 0x1204u:
        LODWORD(result) = Header_OnSetItemA(v10, (unsigned int)wParam, lParam);
        return (int)result;
      case 0x1205u:
        if ( !lParam )
          goto LABEL_122;
        v35 = *(_QWORD *)(lParam + 8);
        if ( !v35 )
          goto LABEL_122;
        v36 = *(_DWORD **)lParam;
        if ( !*(_QWORD *)lParam )
          goto LABEL_122;
        v37 = v10[17] + 2 * g_cyEdge;
        if ( (v10[4] & 0x100) != 0 )
          v37 = 2 * v37 + 1;
        v38 = (v10[4] & 8) == 0;
        v39 = 0;
        *(_QWORD *)(v35 + 8) = 0;
        *(_DWORD *)(v35 + 32) = 20;
        if ( v38 )
          v39 = v37;
        *(_DWORD *)(v35 + 16) = *v36;
        *(_DWORD *)(v35 + 24) = v36[2] - *v36;
        *(_DWORD *)(v35 + 20) = v36[1];
        *(_DWORD *)(v35 + 28) = v39;
        v36[1] += v39;
        goto LABEL_123;
      case 0x1206u:
        if ( lParam )
        {
          v16 = Header_HitTest(v10, *(unsigned int *)lParam, *(unsigned int *)(lParam + 4), lParam + 8);
          *(_DWORD *)(lParam + 12) = v16;
        }
        return v16;
      case 0x1207u:
        LODWORD(result) = Header_OnGetItemRect(v10, (unsigned int)wParam, lParam);
        return (int)result;
      case 0x1208u:
        result = *((_QWORD *)v10 + 16);
        *((_QWORD *)v10 + 16) = lParam;
        return result;
      case 0x1209u:
        return *((_QWORD *)v10 + 16);
      case 0x120Au:
        LODWORD(result) = Header_OnInsertItem(v10, (unsigned int)wParam, lParam);
        return (int)result;
      case 0x120Bu:
        LODWORD(result) = Header_OnGetItem(v10, (unsigned int)wParam, lParam);
        return (int)result;
      case 0x120Cu:
        LODWORD(result) = Header_OnSetItem(v10, (unsigned int)wParam, lParam);
        return (int)result;
      case 0x120Fu:
        LODWORD(result) = Header_ItemOrderToIndex(v10, (unsigned int)wParam);
        return (int)result;
      case 0x1210u:
        ItemOrder = Header_OnGetItemOrder(v10, (unsigned int)wParam);
        return (__int64)Header_OnCreateDragImage((__int64)v10, ItemOrder);
      case 0x1211u:
        if ( **((_DWORD **)v10 + 11) != (_DWORD)wParam )
          goto LABEL_122;
        for ( i = 0; (int)i < (int)wParam; i = (unsigned int)(i + 1) )
          *(_DWORD *)(lParam + 4 * i) = Header_ItemOrderToIndex(v10, (unsigned int)i);
        goto LABEL_123;
      case 0x1212u:
        v41 = (int *)*((_QWORD *)v10 + 11);
        if ( *v41 == (_DWORD)wParam )
        {
          v42 = 0;
          if ( *v41 > 0 )
          {
            do
            {
              Header_OnSetItemOrder(v10, *(unsigned int *)(lParam + 4LL * (int)v42), v42);
              ++v42;
            }
            while ( (signed int)v42 < **((_DWORD **)v10 + 11) );
          }
          MyNotifyWinEvent(32772, *(_QWORD *)v10, 4294967292LL);
        }
        else
        {
LABEL_122:
          v17 = 0;
        }
        goto LABEL_123;
      case 0x1213u:
        return Header_OnSetHotDivider(v10, (unsigned int)wParam, lParam);
      case 0x1214u:
        v10[42] = wParam;
LABEL_123:
        result = v17;
        break;
      case 0x1215u:
        result = (int)v10[42];
        break;
      case 0x1216u:
        result = (int)v10[46];
        if ( lParam )
          v10[46] = lParam;
        break;
      case 0x1217u:
        Header_StopFilterEdit(v10, (unsigned __int16)lParam);
        LODWORD(result) = Header_BeginFilterEdit(v10, (unsigned int)wParam);
        return (int)result;
      case 0x1218u:
        result = Header_OnClearFilter(v10, (unsigned int)wParam);
        break;
      default:
        goto LABEL_149;
    }
  }
  else
  {
    if ( Msg != 4609 )
    {
      if ( Msg <= 0x100 )
      {
        if ( Msg != 256 )
        {
          if ( Msg <= 0x30 )
          {
            switch ( Msg )
            {
              case 0x30u:
                Header_OnSetFont(v10, wParam, (unsigned int)lParam);
                return 0;
              case 1u:
                return ((unsigned int)Header_OnCreate(v10, lParam) != 0) - 1LL;
              case 7u:
              case 8u:
                if ( (v10[4] & 0x100) == 0 )
                  return DefWindowProcW(hWnd, Msg, wParam, lParam);
                v10[25] &= ~8u;
                v21 = 0;
                v22 = v10[43];
                if ( Msg == 7 )
                  v21 = 8;
                v10[25] |= v21;
                v23 = Header_ItemOrderToIndex(v10, v22);
                Header_InvalidateItem(v10, v23, 1);
                UpdateWindow(*(HWND *)v10);
                return 0;
            }
            if ( Msg != 15 )
            {
              if ( Msg == 32 )
                return (unsigned int)Header_OnSetCursor(v10, wParam, (unsigned __int16)lParam, WORD1(lParam));
              goto LABEL_149;
            }
LABEL_99:
            memset(&Paint, 0, sizeof(Paint));
            v33 = *(HWND *)v10;
            if ( wParam )
            {
              v34 = (HDC)wParam;
              GetClientRect(v33, &Paint.rcPaint);
            }
            else
            {
              v34 = BeginPaint(v33, &Paint);
            }
            Header_Draw(v10, v34, &Paint.rcPaint);
            if ( !wParam )
              EndPaint(*(HWND *)v10, &Paint);
            return 0;
          }
          switch ( Msg )
          {
            case 0x31u:
              return *((_QWORD *)v10 + 9);
            case 0x3Du:
              if ( (_DWORD)lParam == -12 )
                return 65553;
              return DefWindowProcW(hWnd, Msg, wParam, lParam);
            case 0x55u:
              return CIHandleNotifyFormat(v10, lParam);
            case 0x7Du:
              if ( wParam == -16 )
              {
                v10[4] = *(_DWORD *)(lParam + 4);
                if ( ((*(_DWORD *)lParam ^ *(_DWORD *)(lParam + 4)) & 0x100) != 0 )
                  Header_StopFilterEdit(v10, 1);
                InvalidateRect(*(HWND *)v10, 0, 1);
              }
              return 0;
            case 0x87u:
              return 3;
          }
LABEL_149:
          v44 = 0;
          if ( (unsigned int)CCWndProc((_DWORD)v10, Msg, wParam, v9, (__int64)&v44) )
            return v44;
          return DefWindowProcW(hWnd, Msg, wParam, lParam);
        }
        if ( (v10[25] & 8) == 0 )
          return DefWindowProcW(hWnd, Msg, wParam, lParam);
        if ( wParam == 113 )
        {
          v24 = Header_ItemOrderToIndex(v10, v10[43]);
          Header_BeginFilterEdit(v10, v24);
LABEL_63:
          CCNotifyNavigationKeyUsage(v10, 1);
          return 0;
        }
        if ( wParam == 115 )
        {
          v25 = Header_ItemOrderToIndex(v10, v10[43]);
          Header_OnFilterButton(v10, v25);
          goto LABEL_63;
        }
        if ( ((wParam - 37) & 0xFFFFFFFFFFFFFFFDuLL) != 0 )
          return DefWindowProcW(hWnd, Msg, wParam, lParam);
        v26 = v10[43];
        if ( wParam == 39 )
        {
          v27 = (int)(v26 + 1) % **((_DWORD **)v10 + 11);
        }
        else
        {
          v27 = v26 - 1;
          v10[43] = v26 - 1;
          if ( (int)(v26 - 1) >= 0 )
            goto LABEL_73;
          v27 = **((_DWORD **)v10 + 11) - 1;
          if ( v27 <= 0 )
            v27 = 0;
        }
        v10[43] = v27;
LABEL_73:
        if ( v26 != v27 )
        {
          v28 = Header_ItemOrderToIndex(v10, v26);
          Header_InvalidateItem(v10, v28, 1);
          v29 = Header_ItemOrderToIndex(v10, v10[43]);
          Header_InvalidateItem(v10, v29, 1);
          UpdateWindow(*(HWND *)v10);
        }
        goto LABEL_63;
      }
      if ( Msg > 0x203 )
      {
        switch ( Msg )
        {
          case 0x205u:
            if ( !CCSendNotify((__int64)v10, -5, 0) )
              return DefWindowProcW(hWnd, Msg, wParam, lParam);
            return 0;
          case 0x2A3u:
            Header_SetHotItem(v10, 0xFFFFFFFFLL);
            v10[25] &= ~2u;
            return DefWindowProcW(hWnd, Msg, wParam, lParam);
          case 0x318u:
            goto LABEL_99;
          case 0x1200u:
            return **((unsigned int **)v10 + 11);
        }
        goto LABEL_149;
      }
      if ( Msg != 515 )
      {
        switch ( Msg )
        {
          case 0x111u:
            if ( (v10[44] & 0x80000000) != 0 || lParam != *((_QWORD *)v10 + 24) || WORD1(wParam) != 768 )
              return DefWindowProcW(hWnd, Msg, wParam, lParam);
            v32 = 1;
            break;
          case 0x113u:
            if ( wParam != 256 )
              return DefWindowProcW(hWnd, Msg, wParam, lParam);
            v32 = 0;
            break;
          case 0x200u:
            Header_OnMouseMove(v10, (unsigned int)(__int16)lParam, (unsigned int)SWORD1(lParam), (unsigned int)wParam);
            return 0;
          case 0x201u:
            v30 = lParam >> 16;
            v31 = 0;
LABEL_84:
            Header_OnLButtonDown(v10, v31, (unsigned int)(__int16)lParam, (unsigned int)(__int16)v30, wParam);
            return 0;
          case 0x202u:
            Header_OnLButtonUp(v10, (unsigned int)(__int16)lParam, (unsigned int)SWORD1(lParam), (unsigned int)wParam);
            return 0;
          default:
            goto LABEL_149;
        }
        Header_FilterChanged(v10, v32);
        return 0;
      }
      v31 = 1;
      v30 = lParam >> 16;
      goto LABEL_84;
    }
    LODWORD(result) = Header_OnInsertItemA(v10, (unsigned int)wParam, lParam);
    return (int)result;
  }
  return result;
}

```

## disassembly

```asm
0x180061f10  push    rbp
0x180061f12  push    rbx
0x180061f13  push    rsi
0x180061f14  push    rdi
0x180061f15  push    r12
0x180061f17  push    r13
0x180061f19  push    r14
0x180061f1b  push    r15
0x180061f1d  lea     rbp, [rsp-1Fh]
0x180061f22  sub     rsp, 0B8h
0x180061f29  mov     rax, cs:__security_cookie
0x180061f30  xor     rax, rsp
0x180061f33  mov     [rbp+57h+var_50], rax
0x180061f37  mov     r15d, edx
0x180061f3a  mov     rbx, r9
0x180061f3d  xor     edx, edx; nIndex
0x180061f3f  mov     rsi, r8
0x180061f42  mov     r13, rcx
0x180061f45  call    cs:__imp_GetWindowLongPtrW
0x180061f4b  mov     rdi, rax
0x180061f4e  test    rax, rax
0x180061f51  jnz     short loc_180061FBD
0x180061f53  cmp     r15d, 81h
0x180061f5a  jnz     short loc_180061F8B
0x180061f5c  lea     edx, [r15+67h]; uBytes
0x180061f60  lea     ecx, [rax+40h]; uFlags
0x180061f63  call    cs:__imp_LocalAlloc
0x180061f69  test    rax, rax
0x180061f6c  jz      loc_18006203A
0x180061f72  mov     [rax], r13
0x180061f75  mov     r8, rax; dwNewLong
0x180061f78  mov     r10, [rbx+18h]
0x180061f7c  xor     edx, edx; nIndex
0x180061f7e  mov     rcx, r13; hWnd
0x180061f81  mov     [rax+8], r10
0x180061f85  call    cs:__imp_SetWindowLongPtrW
0x180061f8b  mov     r9, rbx; lParam
0x180061f8e  mov     r8, rsi; wParam
0x180061f91  mov     edx, r15d; Msg
0x180061f94  mov     rcx, r13; hWnd
0x180061f97  call    cs:__imp_DefWindowProcW
0x180061f9d  mov     rcx, [rbp+57h+var_50]
0x180061fa1  xor     rcx, rsp; StackCookie
0x180061fa4  call    __security_check_cookie
0x180061fa9  add     rsp, 0B8h
0x180061fb0  pop     r15
0x180061fb2  pop     r14
0x180061fb4  pop     r13
0x180061fb6  pop     r12
0x180061fb8  pop     rdi
0x180061fb9  pop     rsi
0x180061fba  pop     rbx
0x180061fbb  pop     rbp
0x180061fbc  retn
0x180061fbd  cmp     r15d, 82h
0x180061fc4  jnz     short loc_180062041
0x180061fc6  mov     rcx, [rax+50h]; himl
0x180061fca  test    rcx, rcx
0x180061fcd  jz      short loc_180061FD4
0x180061fcf  call    ImageList_Destroy
0x180061fd4  mov     edx, 1
0x180061fd9  mov     rcx, rdi
0x180061fdc  call    Header_StopFilterEdit
0x180061fe1  mov     rbx, [rdi+58h]
0x180061fe5  lea     rdx, Header_DestroyItemCallback; pfnCB
0x180061fec  mov     rcx, rbx; hdsa
0x180061fef  xor     r8d, r8d; pData
0x180061ff2  call    DSA_EnumCallback
0x180061ff7  mov     rcx, rbx; hdsa
0x180061ffa  call    DSA_Destroy
0x180061fff  mov     rcx, [rdi+88h]; hdsa
0x180062006  mov     qword ptr [rdi+58h], 0
0x18006200e  test    rcx, rcx
0x180062011  jz      short loc_180062023
0x180062013  call    DSA_Destroy
0x180062018  mov     qword ptr [rdi+88h], 0
0x180062023  mov     rcx, rdi; hMem
0x180062026  call    cs:__imp_LocalFree
0x18006202c  xor     r8d, r8d; dwNewLong
0x18006202f  xor     edx, edx; nIndex
0x180062031  mov     rcx, r13; hWnd
0x180062034  call    cs:__imp_SetWindowLongPtrW
0x18006203a  xor     eax, eax
0x18006203c  jmp     loc_180061F9D
0x180062041  or      r12d, 0FFFFFFFFh
0x180062045  lea     r14d, [r12+2]
0x18006204a  cmp     r15d, 215h
0x180062051  jz      short loc_180062070
0x180062053  cmp     r15d, 204h
0x18006205a  jz      short loc_180062070
0x18006205c  lea     ecx, [r12+1Ch]; vKey
0x180062061  call    cs:__imp_GetAsyncKeyState
0x180062067  test    r14b, al
0x18006206a  jz      loc_180062171
0x180062070  cmp     qword ptr [rdi+98h], 0
0x180062078  jz      short loc_1800620D5
0x18006207a  xor     edx, edx; Val
0x18006207c  lea     rcx, [rbp+57h+Paint]; void *
0x180062080  lea     r8d, [rdx+40h]; Size
0x180062084  call    memset
0x180062089  mov     dword ptr [rbp+57h+Paint.hdc], 80h
0x180062090  mov     dword ptr [rbp+57h+Paint.rgbReserved+8], r12d
0x180062094  call    ImageList_EndDrag
0x180062099  mov     rcx, [rdi+98h]; himl
0x1800620a0  call    ImageList_Destroy
0x1800620a5  mov     edx, r12d
0x1800620a8  mov     qword ptr [rdi+98h], 0
0x1800620b3  mov     rcx, rdi
0x1800620b6  call    _Header_SetHotDivider
0x1800620bb  mov     edx, [rdi+60h]
0x1800620be  lea     r9, [rbp+57h+Paint]
0x1800620c2  mov     r8d, 0FFFFFEC9h
0x1800620c8  mov     rcx, rdi
0x1800620cb  call    Header_SendChange
0x1800620d0  jmp     loc_180062171
0x1800620d5  test    byte ptr [rdi+68h], 0Ch
0x1800620d9  jz      loc_180062171
0x1800620df  xor     edx, edx; Val
0x1800620e1  lea     rcx, [rbp+57h+Paint]; void *
0x1800620e5  lea     r8d, [rdx+40h]; Size
0x1800620e9  call    memset
0x1800620ee  mov     eax, [rdi+78h]
0x1800620f1  mov     rdx, r14; uIDEvent
0x1800620f4  mov     rcx, [rdi]; hWnd
0x1800620f7  mov     dword ptr [rbp+57h+Paint.hdc+4], eax
0x1800620fa  mov     dword ptr [rbp+57h+Paint.hdc], r14d
0x1800620fe  mov     dword ptr [rdi+68h], 0
0x180062105  call    cs:__imp_KillTimer
0x18006210b  mov     rcx, rdi
0x18006210e  call    CCReleaseCapture
0x180062113  mov     edx, [rdi+60h]
0x180062116  lea     r9, [rbp+57h+Paint]
0x18006211a  mov     r8d, 0FFFFFEB9h
0x180062120  mov     rcx, rdi
0x180062123  call    Header_SendChange
0x180062128  cmp     cs:g_fDragFullWindows, 0
0x18006212f  jz      short loc_180062166
0x180062131  test    byte ptr [rdi+10h], 80h
0x180062135  jz      short loc_180062166
0x180062137  mov     eax, [rdi+78h]
0x18006213a  lea     r8, [rbp+57h+Paint]
0x18006213e  mov     edx, [rdi+60h]
0x180062141  mov     rcx, rdi
0x180062144  mov     dword ptr [rbp+57h+Paint.hdc+4], eax
0x180062147  mov     dword ptr [rbp+57h+Paint.hdc], r14d
0x18006214b  call    Header_OnSetItem
0x180062150  mov     rcx, [rdi]; hWnd
0x180062153  mov     r9d, 5; flags
0x180062159  xor     r8d, r8d; hrgnUpdate
0x18006215c  xor     edx, edx; lprcUpdate
0x18006215e  call    cs:__imp_RedrawWindow
0x180062164  jmp     short loc_180062171
0x180062166  mov     edx, [rdi+70h]
0x180062169  mov     rcx, rdi
0x18006216c  call    Header_DrawDivider
0x180062171  lea     eax, [r15-200h]
0x180062178  cmp     eax, 0Dh
0x18006217b  ja      short loc_1800621B6
0x18006217d  test    byte ptr [rdi+10h], 4
0x180062181  jz      short loc_1800621B6
0x180062183  mov     eax, [rdi+64h]
0x180062186  test    al, 2
0x180062188  jnz     short loc_1800621B6
0x18006218a  or      eax, 2
0x18006218d  mov     qword ptr [rbp+57h+EventTrack.dwHoverTime], 0
0x180062195  mov     [rdi+64h], eax
0x180062198  lea     rcx, [rbp+57h+EventTrack]; lpEventTrack
0x18006219c  mov     rax, [rdi]
0x18006219f  mov     [rbp+57h+EventTrack.hwndTrack], rax
0x1800621a3  mov     [rbp+57h+EventTrack.cbSize], 18h
0x1800621aa  mov     [rbp+57h+EventTrack.dwFlags], 2
0x1800621b1  call    _TrackMouseEvent
0x1800621b6  mov     eax, 1201h
0x1800621bb  cmp     r15d, eax
0x1800621be  ja      loc_1800625EC
0x1800621c4  jz      loc_1800625DD
0x1800621ca  mov     ecx, 100h
0x1800621cf  cmp     r15d, ecx
0x1800621d2  ja      loc_18006242A
0x1800621d8  jz      loc_180062337
0x1800621de  cmp     r15d, 30h ; '0'
0x1800621e2  ja      loc_1800622AA
0x1800621e8  jz      loc_180062297
0x1800621ee  mov     eax, r15d
0x1800621f1  sub     eax, r14d
0x1800621f4  jz      loc_18006227C
0x1800621fa  sub     eax, 6
0x1800621fd  jz      short loc_180062237
0x1800621ff  sub     eax, r14d
0x180062202  jz      short loc_180062237
0x180062204  sub     eax, 7
0x180062207  jz      loc_18006254F
0x18006220d  cmp     eax, 11h
0x180062210  jnz     def_18006260D; jumptable 000000018006260D default case, cases 4621,4622
0x180062216  mov     rax, rbx
0x180062219  movzx   r8d, bx
0x18006221d  shr     rax, 10h
0x180062221  mov     rdx, rsi
0x180062224  movzx   r9d, ax
0x180062228  mov     rcx, rdi
0x18006222b  call    Header_OnSetCursor
0x180062230  mov     eax, eax
0x180062232  jmp     loc_180061F9D
0x180062237  test    [rdi+10h], ecx
0x18006223a  jz      loc_180061F8B
0x180062240  and     dword ptr [rdi+64h], 0FFFFFFF7h
0x180062244  xor     eax, eax
0x180062246  mov     edx, [rdi+0ACh]
0x18006224c  cmp     r15d, 7
0x180062250  lea     ecx, [rax+8]
0x180062253  cmovz   eax, ecx
0x180062256  mov     rcx, rdi
0x180062259  or      [rdi+64h], eax
0x18006225c  call    Header_ItemOrderToIndex
0x180062261  mov     edx, eax
0x180062263  mov     r8d, r14d
0x180062266  mov     rcx, rdi
0x180062269  call    Header_InvalidateItem
0x18006226e  mov     rcx, [rdi]; hWnd
0x180062271  call    cs:__imp_UpdateWindow
0x180062277  jmp     loc_18006203A
0x18006227c  mov     rdx, rbx
0x18006227f  mov     rcx, rdi
0x180062282  call    Header_OnCreate
0x180062287  neg     eax
0x180062289  sbb     rax, rax
0x18006228c  neg     rax
0x18006228f  sub     rax, r14
0x180062292  jmp     loc_180061F9D
0x180062297  mov     r8d, ebx
0x18006229a  mov     rdx, rsi
0x18006229d  mov     rcx, rdi
0x1800622a0  call    Header_OnSetFont
0x1800622a5  jmp     loc_18006203A
0x1800622aa  mov     eax, r15d
0x1800622ad  sub     eax, 31h ; '1'
0x1800622b0  jz      short loc_18006232E
0x1800622b2  sub     eax, 0Ch
0x1800622b5  jz      short loc_18006231B
0x1800622b7  sub     eax, 18h
0x1800622ba  jz      short loc_18006230B
0x1800622bc  sub     eax, 28h ; '('
0x1800622bf  jz      short loc_1800622D4
0x1800622c1  cmp     eax, 0Ah
0x1800622c4  jnz     def_18006260D; jumptable 000000018006260D default case, cases 4621,4622
0x1800622ca  mov     eax, 3
0x1800622cf  jmp     loc_180061F9D
0x1800622d4  cmp     rsi, 0FFFFFFFFFFFFFFF0h
0x1800622d8  jnz     loc_18006203A
0x1800622de  mov     eax, [rbx+4]
0x1800622e1  mov     [rdi+10h], eax
0x1800622e4  mov     eax, [rbx+4]
0x1800622e7  xor     eax, [rbx]
0x1800622e9  test    ecx, eax
0x1800622eb  jz      short loc_1800622F8
0x1800622ed  mov     edx, r14d
0x1800622f0  mov     rcx, rdi
0x1800622f3  call    Header_StopFilterEdit
0x1800622f8  mov     rcx, [rdi]; hWnd
0x1800622fb  mov     r8d, r14d; bErase
0x1800622fe  xor     edx, edx; lpRect
0x180062300  call    cs:__imp_InvalidateRect
0x180062306  jmp     loc_18006203A
0x18006230b  mov     rdx, rbx
0x18006230e  mov     rcx, rdi
0x180062311  call    CIHandleNotifyFormat
0x180062316  jmp     loc_180061F9D
0x18006231b  cmp     ebx, 0FFFFFFF4h
0x18006231e  jnz     loc_180061F8B
0x180062324  mov     eax, 10011h
0x180062329  jmp     loc_180061F9D
0x18006232e  mov     rax, [rdi+48h]
0x180062332  jmp     loc_180061F9D
0x180062337  mov     ecx, 8
0x18006233c  test    [rdi+64h], cl
0x18006233f  jz      loc_180061F8B
0x180062345  cmp     rsi, 71h ; 'q'
0x180062349  jnz     short loc_180062373
0x18006234b  mov     edx, [rdi+0ACh]
0x180062351  mov     rcx, rdi
0x180062354  call    Header_ItemOrderToIndex
0x180062359  mov     edx, eax
0x18006235b  mov     rcx, rdi
0x18006235e  call    Header_BeginFilterEdit
0x180062363  mov     edx, r14d
0x180062366  mov     rcx, rdi
0x180062369  call    CCNotifyNavigationKeyUsage
0x18006236e  jmp     loc_18006203A
0x180062373  cmp     rsi, 73h ; 's'
0x180062377  jnz     short loc_180062393
0x180062379  mov     edx, [rdi+0ACh]
0x18006237f  mov     rcx, rdi
0x180062382  call    Header_ItemOrderToIndex
0x180062387  mov     edx, eax
0x180062389  mov     rcx, rdi
0x18006238c  call    Header_OnFilterButton
0x180062391  jmp     short loc_180062363
0x180062393  lea     rax, [rsi-25h]
0x180062397  test    rax, 0FFFFFFFFFFFFFFFDh
0x18006239d  jnz     loc_180061F8B
  ... truncated ...
```
