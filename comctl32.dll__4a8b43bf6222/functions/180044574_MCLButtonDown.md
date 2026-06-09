# MCLButtonDown

- ea: `0x180044574`
- end: `0x180044d42`
- name: `MCLButtonDown`
- size: `1998`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x180046d90`

## callees

- `0x1800115f0`
- `0x18002d220`
- `0x180035f8c`
- `0x180042014`
- `0x180042170`
- `0x180042274`
- `0x180042488`
- `0x1800425d8`
- `0x1800433fc`
- `0x1800434c4`
- `0x180043574`
- `0x180043cc8`
- `0x1800440e8`
- `0x180044574`
- `0x180044fd4`
- `0x1800452a0`
- `0x18004661c`
- `0x180072058`

## import_xrefs

- `USER32!GetWindowLongW` at `0x180044984`
- `USER32!GetWindowLongW` at `0x1800449a2`
- `USER32!GetWindowLongW` at `0x180044984`
- `USER32!GetWindowLongW` at `0x1800449a2`
- `USER32!ClientToScreen` at `0x1800448d6`
- `USER32!ClientToScreen` at `0x1800448d6`
- `USER32!GetDC` at `0x180044666`
- `USER32!GetDC` at `0x1800447cc`
- `USER32!GetDC` at `0x180044666`
- `USER32!GetDC` at `0x1800447cc`
- `USER32!ReleaseDC` at `0x180044688`
- `USER32!ReleaseDC` at `0x1800447ee`
- `USER32!ReleaseDC` at `0x180044688`
- `USER32!ReleaseDC` at `0x1800447ee`
- `USER32!MapWindowPoints` at `0x180044b5c`
- `USER32!MapWindowPoints` at `0x180044b7d`
- `USER32!MapWindowPoints` at `0x180044b5c`
- `USER32!MapWindowPoints` at `0x180044b7d`
- `USER32!SetCapture` at `0x180044619`
- `USER32!SetCapture` at `0x1800446ae`
- `USER32!SetCapture` at `0x180044619`
- `USER32!SetCapture` at `0x1800446ae`
- `USER32!PeekMessageW` at `0x180044ba2`
- `USER32!PeekMessageW` at `0x180044ba2`
- `USER32!PtInRect` at `0x180044608`
- `USER32!PtInRect` at `0x1800446c6`
- `USER32!PtInRect` at `0x180044702`
- `USER32!PtInRect` at `0x18004484a`
- `USER32!PtInRect` at `0x1800448b6`
- `USER32!PtInRect` at `0x180044922`
- `USER32!PtInRect` at `0x180044bf3`
- `USER32!PtInRect` at `0x180044c63`
- `USER32!PtInRect` at `0x180044608`
- `USER32!PtInRect` at `0x1800446c6`
- `USER32!PtInRect` at `0x180044702`
- `USER32!PtInRect` at `0x18004484a`
- `USER32!PtInRect` at `0x1800448b6`
- `USER32!PtInRect` at `0x180044922`
- `USER32!PtInRect` at `0x180044bf3`
- `USER32!PtInRect` at `0x180044c63`
- `USER32!TranslateMessage` at `0x180044c39`
- `USER32!TranslateMessage` at `0x180044c39`
- `USER32!DispatchMessageW` at `0x180044c43`
- `USER32!DispatchMessageW` at `0x180044c43`
- `USER32!WaitMessage` at `0x180044c4b`
- `USER32!WaitMessage` at `0x180044c4b`
- `USER32!SendMessageW` at `0x180044a35`
- `USER32!SendMessageW` at `0x180044a4f`
- `USER32!SendMessageW` at `0x180044c8d`
- `USER32!SendMessageW` at `0x180044a35`
- `USER32!SendMessageW` at `0x180044a4f`
- `USER32!SendMessageW` at `0x180044c8d`
- `USER32!MessageBeep` at `0x180044cf9`
- `USER32!MessageBeep` at `0x180044cf9`
- `USER32!DestroyWindow` at `0x180044b01`
- `USER32!DestroyWindow` at `0x180044cab`
- `USER32!DestroyWindow` at `0x180044cb4`
- `USER32!DestroyWindow` at `0x180044b01`
- `USER32!DestroyWindow` at `0x180044cab`
- `USER32!DestroyWindow` at `0x180044cb4`
- `USER32!CreateWindowExW` at `0x180044a0b`
- `USER32!CreateWindowExW` at `0x180044a0b`
- `USER32!SetFocus` at `0x180044b16`
- `USER32!SetFocus` at `0x180044cdc`
- `USER32!SetFocus` at `0x180044b16`
- `USER32!SetFocus` at `0x180044cdc`
- `USER32!GetFocus` at `0x180044b83`
- `USER32!GetFocus` at `0x180044b83`
- `USER32!GetMessageW` at `0x180044c2f`
- `USER32!GetMessageW` at `0x180044c79`
- `USER32!GetMessageW` at `0x180044c2f`
- `USER32!GetMessageW` at `0x180044c79`
- `USER32!UpdateWindow` at `0x180044cce`
- `USER32!UpdateWindow` at `0x180044cce`
- `USER32!DrawFocusRect` at `0x180044675`
- `USER32!DrawFocusRect` at `0x1800447db`
- `USER32!DrawFocusRect` at `0x180044675`
- `USER32!DrawFocusRect` at `0x1800447db`
- `USER32!TrackPopupMenu` at `0x180044902`
- `USER32!TrackPopupMenu` at `0x180044902`

## pseudocode

```c
__int64 __fastcall MCLButtonDown(__int64 a1, char a2, __int64 a3)
{
  bool v3; // zf
  const RECT *v6; // r14
  int v7; // eax
  HWND v8; // rcx
  int v9; // r10d
  HDC DC; // rbx
  HWND v11; // rcx
  __int64 v12; // rdx
  POINT v13; // rdx
  bool v14; // al
  int v15; // esi
  HDC v16; // rbx
  HWND v17; // rcx
  HWND v18; // rcx
  BOOL v19; // ebx
  unsigned int v20; // ebx
  int v21; // ecx
  int v22; // edx
  DWORD v23; // ebx
  HWND Window; // rax
  HWND v25; // r14
  WPARAM v26; // r8
  int v27; // ecx
  int v28; // edx
  int v29; // eax
  int v30; // r13d
  int v31; // r10d
  HWND UpDownControl; // rax
  HWND v33; // r12
  HWND v34; // r15
  HWND v35; // rcx
  UINT message; // ecx
  int v37; // r8d
  int v38; // eax
  HWND v39; // rcx
  POINT pt; // [rsp+60h] [rbp-69h] BYREF
  unsigned int v42; // [rsp+68h] [rbp-61h] BYREF
  int v43; // [rsp+6Ch] [rbp-5Dh] BYREF
  int v44; // [rsp+70h] [rbp-59h] BYREF
  struct tagMSG Msg; // [rsp+78h] [rbp-51h] BYREF
  RECT v46; // [rsp+A8h] [rbp-21h] BYREF
  struct tagPOINT Points[2]; // [rsp+B8h] [rbp-11h] BYREF
  RECT rc; // [rsp+C8h] [rbp-1h] BYREF
  RECT v49; // [rsp+D8h] [rbp+Fh] BYREF

  v3 = (*(_BYTE *)(a1 + 2392) & 2) == 0;
  v42 = 0;
  v46 = 0;
  rc = 0;
  *(_OWORD *)&Points[0].x = 0;
  memset(&Msg, 0, sizeof(Msg));
  if ( v3 )
    return 0;
  pt.x = (__int16)a3;
  v3 = (*(_BYTE *)(a1 + 16) & 2) == 0;
  pt.y = SWORD1(a3);
  if ( !v3 && (a2 & 4) != 0 )
  {
    v6 = (const RECT *)(a1 + 2100);
    if ( !PtInRect((const RECT *)(a1 + 2100), pt) )
    {
      SetCapture(*(HWND *)a1);
      *(_DWORD *)(a1 + 2392) |= 4u;
      v7 = CmpDate(a1 + 1884, a1 + 1820);
      v8 = *(HWND *)a1;
      *(_DWORD *)(a1 + 2392) = v9 & 0xFFFFFEFF | (v7 == 0 ? 0x100 : 0) | 0x80;
      DC = GetDC(v8);
      DrawFocusRect(DC, v6);
      v11 = *(HWND *)a1;
      *(_DWORD *)(a1 + 2392) |= 0x10u;
      ReleaseDC(v11, DC);
      MCMouseMove(a1, v12, a3);
      return 0;
    }
  }
  if ( (*(_BYTE *)(a1 + 2392) & 4) != 0 )
    return 0;
  SetCapture(*(HWND *)a1);
  v13 = pt;
  *(_DWORD *)(a1 + 2392) |= 4u;
  v14 = PtInRect((const RECT *)(a1 + 1992), v13);
  v15 = 1;
  *(_DWORD *)(a1 + 2392) ^= ((unsigned __int8)*(_DWORD *)(a1 + 2392) ^ (unsigned __int8)(8 * v14)) & 8;
  if ( v14 || PtInRect((const RECT *)(a1 + 2008), pt) )
  {
    MCHandleTimer(a1, 1);
    return 0;
  }
  v3 = (*(_BYTE *)(a1 + 16) & 2) == 0;
  *(_OWORD *)(a1 + 2116) = *(_OWORD *)(a1 + 2100);
  if ( !v3 )
  {
    *(_WORD *)(a1 + 1852) = *(_WORD *)(a1 + 1820);
    *(_WORD *)(a1 + 1854) = *(_WORD *)(a1 + 1822);
    *(_WORD *)(a1 + 1858) = *(_WORD *)(a1 + 1826);
    *(_WORD *)(a1 + 1868) = *(_WORD *)(a1 + 1836);
    *(_WORD *)(a1 + 1870) = *(_WORD *)(a1 + 1838);
    *(_WORD *)(a1 + 1874) = *(_WORD *)(a1 + 1842);
  }
  if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))FUpdateRcDayCur)(a1, pt) )
  {
    if ( (*(_BYTE *)(a1 + 16) & 2) != 0 && (unsigned int)FGetDateForPt(a1, pt.x, (unsigned int)&v46, 0, 0, 0, 0) )
      MCHandleMultiSelect(a1, &v46);
    v16 = GetDC(*(HWND *)a1);
    DrawFocusRect(v16, (const RECT *)(a1 + 2100));
    v17 = *(HWND *)a1;
    *(_DWORD *)(a1 + 2392) |= 0x10u;
    ReleaseDC(v17, v16);
    *(_DWORD *)(a1 + 1884) = v46.left;
    *(_WORD *)(a1 + 1890) = HIWORD(v46.top);
    return 0;
  }
  v3 = (*(_BYTE *)(a1 + 16) & 0x10) == 0;
  v44 = 0;
  v49 = 0;
  v43 = 0;
  v46 = 0;
  if ( v3 )
  {
    MCGetTodayBtnRect(a1, &rc);
    if ( PtInRect(&rc, pt) )
    {
      CCReleaseCapture(a1);
      *(_DWORD *)(a1 + 2392) &= ~4u;
      MCGotoToday(a1);
      return 0;
    }
  }
  if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))FGetOffsetForPt)(a1, pt, &v42) )
    return 0;
  GetYrMoForOffset(a1, v42, &v44, &v43);
  MCGetTitleRcsForOffset(a1, v42, &v49, &v46);
  if ( PtInRect(&v49, pt) )
  {
    CCReleaseCapture(a1);
    v18 = *(HWND *)a1;
    *(_DWORD *)(a1 + 2392) &= ~4u;
    ClientToScreen(v18, &pt);
    v19 = TrackPopupMenu(*(HMENU *)(a1 + 1760), 0x182u, pt.x, pt.y, 0, *(HWND *)a1, 0);
    if ( v19 < 1 )
      return 0;
    v20 = v19 - v43;
    goto LABEL_69;
  }
  if ( PtInRect(&v46, pt) )
  {
    CCReleaseCapture(a1);
    *(_DWORD *)(a1 + 2392) &= ~4u;
    v21 = *(_DWORD *)(a1 + 1728);
    v22 = *(_DWORD *)(a1 + 2392) & 0x4000;
    if ( v22 )
      v46.left = v46.right - v21 - 6;
    else
      v46.right = v46.left + 6 + v21;
    --v46.top;
    ++v46.bottom;
    if ( v22 && (GetWindowLongW(*(HWND *)a1, -20) & 0x400000) == 0
      || (v23 = 0, (*(_DWORD *)(a1 + 2392) & 0x4000) == 0) && (GetWindowLongW(*(HWND *)a1, -20) & 0x400000) != 0 )
    {
      v23 = 0x2000;
    }
    Window = CreateWindowExW(
               v23,
               L"EDIT",
               0,
               0x50800880u,
               v46.left,
               v46.top,
               v46.right - v46.left,
               v46.bottom - v46.top,
               *(HWND *)a1,
               0,
               *(HINSTANCE *)(a1 + 1632),
               0);
    v25 = Window;
    if ( Window )
    {
      v26 = *(_QWORD *)(a1 + 1680);
      *(_QWORD *)(a1 + 1640) = Window;
      SendMessageW(Window, 0x30u, v26, 0);
      SendMessageW(v25, 0xD3u, 3u, 65537);
      MCUpdateEditYear(a1);
      v27 = *(_DWORD *)(a1 + 2368);
      v28 = 9999;
      v29 = *(_DWORD *)(a1 + 2392);
      v30 = v27 + v44;
      if ( (v29 & 0x1000) != 0 )
        v28 = v27 + *(unsigned __int16 *)(a1 + 1784);
      if ( (v29 & 0x4000) != 0 )
        v31 = v46.top - v46.bottom + v46.left - 1;
      else
        v31 = v46.right + 1;
      UpDownControl = CreateUpDownControl(
                        0x508000A0u,
                        v31,
                        v46.top,
                        v46.bottom - v46.top,
                        v46.bottom - v46.top,
                        *(HWND *)a1,
                        1,
                        *(HINSTANCE *)(a1 + 1632),
                        v25,
                        v28,
                        v27 + (unsigned int)*(unsigned __int16 *)(a1 + 1768),
                        v30);
      v33 = UpDownControl;
      if ( !UpDownControl )
      {
        DestroyWindow(v25);
        return 0;
      }
      v20 = 0;
      *(_QWORD *)(a1 + 1648) = UpDownControl;
      v34 = SetFocus(v25);
      if ( (*(_DWORD *)(a1 + 2392) & 0x4000) != 0 )
        v46.left = v46.left - 1 + v46.top - v46.bottom;
      else
        v46.right += 1 + v46.bottom - v46.top;
      MapWindowPoints(*(HWND *)a1, 0, (LPPOINT)&v46, 2u);
      v35 = *(HWND *)a1;
      *(_OWORD *)&Points[0].x = *(_OWORD *)(a1 + 2132);
      MapWindowPoints(v35, 0, Points, 2u);
      while ( GetFocus() == v25 )
      {
        if ( PeekMessageW(&Msg, 0, 0, 0, 0) )
        {
          message = Msg.message;
          if ( Msg.message == 8 || Msg.message - 260 <= 3 )
            goto LABEL_58;
          v37 = 73;
          if ( Msg.message - 513 <= 6 && _bittest(&v37, Msg.message - 513)
            || Msg.message - 161 <= 6 && _bittest(&v37, Msg.message - 161) )
          {
            if ( !PtInRect(&v46, Msg.pt) )
            {
              if ( PtInRect((const RECT *)Points, Msg.pt) )
                GetMessageW(&Msg, 0, 0, 0);
              break;
            }
            message = Msg.message;
          }
          if ( message == 18 )
            break;
          if ( message == 258 )
          {
            if ( Msg.wParam == 27 )
              goto LABEL_67;
            if ( Msg.wParam == 13 )
LABEL_58:
              v15 = 0;
          }
          GetMessageW(&Msg, 0, 0, 0);
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
        else
        {
          WaitMessage();
        }
        if ( !v15 )
          break;
      }
      v38 = SendMessageW(v33, 0x468u, 0, 0);
      if ( !HIWORD(v38) )
        v20 = 12 * ((unsigned __int16)v38 - v30);
LABEL_67:
      DestroyWindow(v33);
      DestroyWindow(v25);
      v39 = *(HWND *)a1;
      *(_QWORD *)(a1 + 1648) = 0;
      *(_QWORD *)(a1 + 1640) = 0;
      UpdateWindow(v39);
      if ( v34 )
        SetFocus(v34);
LABEL_69:
      if ( v20 )
      {
        if ( !(unsigned int)FIncrStartMonth(a1, v20, 0) )
          MessageBeep(0);
        MCNotifySelChange(a1, 4294966547LL);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180044574  mov     [rsp-8+arg_8], rbx
0x180044579  push    rbp
0x18004457a  push    rsi
0x18004457b  push    rdi
0x18004457c  push    r12
0x18004457e  push    r13
0x180044580  push    r14
0x180044582  push    r15
0x180044584  lea     rbp, [rsp-27h]
0x180044589  sub     rsp, 0F0h
0x180044590  mov     rax, cs:__security_cookie
0x180044597  xor     rax, rsp
0x18004459a  mov     [rbp+57h+var_38], rax
0x18004459e  xorps   xmm1, xmm1
0x1800445a1  xor     r15d, r15d
0x1800445a4  test    byte ptr [rcx+958h], 2
0x1800445ab  xorps   xmm0, xmm0
0x1800445ae  mov     rsi, r8
0x1800445b1  mov     [rbp+57h+var_B8], r15d
0x1800445b5  mov     rdi, rcx
0x1800445b8  movups  xmmword ptr [rbp+57h+var_78.left], xmm0
0x1800445bc  movups  xmmword ptr [rbp+57h+rc.left], xmm1
0x1800445c0  movups  xmmword ptr [rbp+57h+Points.x], xmm0
0x1800445c4  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm1
0x1800445c8  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm1
0x1800445cc  movups  xmmword ptr [rbp+57h+Msg.time], xmm1
0x1800445d0  jz      loc_180044D19
0x1800445d6  movsx   eax, si
0x1800445d9  mov     [rbp+57h+pt.x], eax
0x1800445dc  mov     rax, r8
0x1800445df  shr     rax, 10h
0x1800445e3  test    byte ptr [rcx+10h], 2
0x1800445e7  cwde
0x1800445e8  mov     [rbp+57h+pt.y], eax
0x1800445eb  jz      loc_18004469E
0x1800445f1  test    dl, 4
0x1800445f4  jz      loc_18004469E
0x1800445fa  mov     rdx, qword ptr [rbp+57h+pt.x]; pt
0x1800445fe  lea     r14, [rcx+834h]
0x180044605  mov     rcx, r14; lprc
0x180044608  call    cs:__imp_PtInRect
0x18004460e  test    eax, eax
0x180044610  jnz     loc_18004469E
0x180044616  mov     rcx, [rdi]; hWnd
0x180044619  call    cs:__imp_SetCapture
0x18004461f  or      dword ptr [rdi+958h], 4
0x180044626  lea     rdx, [rdi+71Ch]
0x18004462d  mov     r10d, [rdi+958h]
0x180044634  lea     rcx, [rdi+75Ch]
0x18004463b  call    CmpDate
0x180044640  mov     rcx, [rdi]; hWnd
0x180044643  neg     eax
0x180044645  sbb     r9d, r9d
0x180044648  btr     r10d, 8
0x18004464d  not     r9d
0x180044650  and     r9d, 100h
0x180044657  or      r9d, r10d
0x18004465a  bts     r9d, 7
0x18004465f  mov     [rdi+958h], r9d
0x180044666  call    cs:__imp_GetDC
0x18004466c  mov     rcx, rax; hDC
0x18004466f  mov     rdx, r14; lprc
0x180044672  mov     rbx, rax
0x180044675  call    cs:__imp_DrawFocusRect
0x18004467b  mov     rcx, [rdi]; hWnd
0x18004467e  mov     rdx, rbx; hDC
0x180044681  or      dword ptr [rdi+958h], 10h
0x180044688  call    cs:__imp_ReleaseDC
0x18004468e  mov     r8, rsi
0x180044691  mov     rcx, rdi
0x180044694  call    MCMouseMove
0x180044699  jmp     loc_180044D19
0x18004469e  test    byte ptr [rdi+958h], 4
0x1800446a5  jnz     loc_180044D19
0x1800446ab  mov     rcx, [rdi]; hWnd
0x1800446ae  call    cs:__imp_SetCapture
0x1800446b4  mov     rdx, qword ptr [rbp+57h+pt.x]; pt
0x1800446b8  lea     rcx, [rdi+7C8h]; lprc
0x1800446bf  or      dword ptr [rdi+958h], 4
0x1800446c6  call    cs:__imp_PtInRect
0x1800446cc  mov     ecx, [rdi+958h]
0x1800446d2  mov     esi, 1
0x1800446d7  movzx   edx, ax
0x1800446da  lea     eax, ds:0[rdx*8]
0x1800446e1  xor     eax, ecx
0x1800446e3  and     eax, 8
0x1800446e6  xor     eax, ecx
0x1800446e8  mov     [rdi+958h], eax
0x1800446ee  test    sil, dl
0x1800446f1  jnz     loc_180044D0E
0x1800446f7  mov     rdx, qword ptr [rbp+57h+pt.x]; pt
0x1800446fb  lea     rcx, [rdi+7D8h]; lprc
0x180044702  call    cs:__imp_PtInRect
0x180044708  test    eax, eax
0x18004470a  jnz     loc_180044D0E
0x180044710  test    byte ptr [rdi+10h], 2
0x180044714  lea     r14, [rdi+834h]
0x18004471b  movups  xmm0, xmmword ptr [r14]
0x18004471f  movdqu  xmmword ptr [rdi+844h], xmm0
0x180044727  jz      short loc_18004477D
0x180044729  movzx   eax, word ptr [rdi+71Ch]
0x180044730  mov     [rdi+73Ch], ax
0x180044737  movzx   eax, word ptr [rdi+71Eh]
0x18004473e  mov     [rdi+73Eh], ax
0x180044745  movzx   eax, word ptr [rdi+722h]
0x18004474c  mov     [rdi+742h], ax
0x180044753  movzx   eax, word ptr [rdi+72Ch]
0x18004475a  mov     [rdi+74Ch], ax
0x180044761  movzx   eax, word ptr [rdi+72Eh]
0x180044768  mov     [rdi+74Eh], ax
0x18004476f  movzx   eax, word ptr [rdi+732h]
0x180044776  mov     [rdi+752h], ax
0x18004477d  mov     rdx, qword ptr [rbp+57h+pt.x]
0x180044781  mov     rcx, rdi
0x180044784  call    FUpdateRcDayCur
0x180044789  test    eax, eax
0x18004478b  jz      loc_18004481A
0x180044791  test    byte ptr [rdi+10h], 2
0x180044795  jz      short loc_1800447C9
0x180044797  mov     rdx, qword ptr [rbp+57h+pt.x]
0x18004479b  lea     r8, [rbp+57h+var_78]
0x18004479f  mov     [rsp+120h+prcRect], r15
0x1800447a4  xor     r9d, r9d
0x1800447a7  mov     [rsp+120h+hWnd], r15
0x1800447ac  mov     rcx, rdi
0x1800447af  mov     qword ptr [rsp+120h+nReserved], r15
0x1800447b4  call    FGetDateForPt
0x1800447b9  test    eax, eax
0x1800447bb  jz      short loc_1800447C9
0x1800447bd  lea     rdx, [rbp+57h+var_78]
0x1800447c1  mov     rcx, rdi
0x1800447c4  call    MCHandleMultiSelect
0x1800447c9  mov     rcx, [rdi]; hWnd
0x1800447cc  call    cs:__imp_GetDC
0x1800447d2  mov     rcx, rax; hDC
0x1800447d5  mov     rdx, r14; lprc
0x1800447d8  mov     rbx, rax
0x1800447db  call    cs:__imp_DrawFocusRect
0x1800447e1  mov     rcx, [rdi]; hWnd
0x1800447e4  mov     rdx, rbx; hDC
0x1800447e7  or      dword ptr [rdi+958h], 10h
0x1800447ee  call    cs:__imp_ReleaseDC
0x1800447f4  movzx   eax, word ptr [rbp+57h+var_78.left]
0x1800447f8  mov     [rdi+75Ch], ax
0x1800447ff  movzx   eax, word ptr [rbp+57h+var_78.left+2]
0x180044803  mov     [rdi+75Eh], ax
0x18004480a  movzx   eax, word ptr [rbp+57h+var_78.top+2]
0x18004480e  mov     [rdi+762h], ax
0x180044815  jmp     loc_180044D19
0x18004481a  test    byte ptr [rdi+10h], 10h
0x18004481e  xorps   xmm0, xmm0
0x180044821  xorps   xmm1, xmm1
0x180044824  mov     [rbp+57h+var_B0], r15d
0x180044828  movups  xmmword ptr [rbp+57h+var_48.left], xmm0
0x18004482c  mov     [rbp+57h+var_B4], r15d
0x180044830  movups  xmmword ptr [rbp+57h+var_78.left], xmm1
0x180044834  jnz     short loc_180044870
0x180044836  lea     rdx, [rbp+57h+rc]
0x18004483a  mov     rcx, rdi
0x18004483d  call    MCGetTodayBtnRect
0x180044842  mov     rdx, qword ptr [rbp+57h+pt.x]; pt
0x180044846  lea     rcx, [rbp+57h+rc]; lprc
0x18004484a  call    cs:__imp_PtInRect
0x180044850  test    eax, eax
0x180044852  jz      short loc_180044870
0x180044854  mov     rcx, rdi
0x180044857  call    CCReleaseCapture
0x18004485c  and     dword ptr [rdi+958h], 0FFFFFFFBh
0x180044863  mov     rcx, rdi
0x180044866  call    MCGotoToday
0x18004486b  jmp     loc_180044D19
0x180044870  mov     rdx, qword ptr [rbp+57h+pt.x]
0x180044874  lea     r8, [rbp+57h+var_B8]
0x180044878  mov     rcx, rdi
0x18004487b  call    FGetOffsetForPt
0x180044880  test    eax, eax
0x180044882  jz      loc_180044D19
0x180044888  mov     edx, [rbp+57h+var_B8]
0x18004488b  lea     r9, [rbp+57h+var_B4]
0x18004488f  lea     r8, [rbp+57h+var_B0]
0x180044893  mov     rcx, rdi
0x180044896  call    GetYrMoForOffset
0x18004489b  mov     edx, [rbp+57h+var_B8]
0x18004489e  lea     r9, [rbp+57h+var_78]
0x1800448a2  lea     r8, [rbp+57h+var_48]
0x1800448a6  mov     rcx, rdi
0x1800448a9  call    MCGetTitleRcsForOffset
0x1800448ae  mov     rdx, qword ptr [rbp+57h+pt.x]; pt
0x1800448b2  lea     rcx, [rbp+57h+var_48]; lprc
0x1800448b6  call    cs:__imp_PtInRect
0x1800448bc  test    eax, eax
0x1800448be  jz      short loc_18004491A
0x1800448c0  mov     rcx, rdi
0x1800448c3  call    CCReleaseCapture
0x1800448c8  mov     rcx, [rdi]; hWnd
0x1800448cb  lea     rdx, [rbp+57h+pt]; lpPoint
0x1800448cf  and     dword ptr [rdi+958h], 0FFFFFFFBh
0x1800448d6  call    cs:__imp_ClientToScreen
0x1800448dc  mov     rax, [rdi]
0x1800448df  mov     edx, 182h; uFlags
0x1800448e4  mov     r9d, [rbp+57h+pt.y]; y
0x1800448e8  mov     r8d, [rbp+57h+pt.x]; x
0x1800448ec  mov     rcx, [rdi+6E0h]; hMenu
0x1800448f3  mov     [rsp+120h+prcRect], r15; prcRect
0x1800448f8  mov     [rsp+120h+hWnd], rax; hWnd
0x1800448fd  mov     [rsp+120h+nReserved], r15d; nReserved
0x180044902  call    cs:__imp_TrackPopupMenu
0x180044908  mov     ebx, eax
0x18004490a  cmp     eax, esi
0x18004490c  jl      loc_180044D19
0x180044912  sub     ebx, [rbp+57h+var_B4]
0x180044915  jmp     loc_180044CE2
0x18004491a  mov     rdx, qword ptr [rbp+57h+pt.x]; pt
0x18004491e  lea     rcx, [rbp+57h+var_78]; lprc
0x180044922  call    cs:__imp_PtInRect
0x180044928  test    eax, eax
0x18004492a  jz      loc_180044D19
0x180044930  mov     rcx, rdi
0x180044933  call    CCReleaseCapture
0x180044938  and     dword ptr [rdi+958h], 0FFFFFFFBh
0x18004493f  mov     r13d, 4000h
0x180044945  mov     edx, [rdi+958h]
0x18004494b  mov     ecx, [rdi+6C0h]
0x180044951  and     edx, r13d
0x180044954  jz      short loc_180044963
0x180044956  mov     eax, [rbp+57h+var_78.right]
0x180044959  sub     eax, ecx
0x18004495b  sub     eax, 6
0x18004495e  mov     [rbp+57h+var_78.left], eax
0x180044961  jmp     short loc_18004496E
0x180044963  mov     eax, [rbp+57h+var_78.left]
0x180044966  add     eax, 6
0x180044969  add     ecx, eax
0x18004496b  mov     [rbp+57h+var_78.right], ecx
0x18004496e  sub     [rbp+57h+var_78.top], esi
0x180044971  mov     r14d, 0FFFFFFECh
0x180044977  add     [rbp+57h+var_78.bottom], esi
0x18004497a  test    edx, edx
0x18004497c  jz      short loc_180044990
0x18004497e  mov     rcx, [rdi]; hWnd
0x180044981  mov     edx, r14d; nIndex
0x180044984  call    cs:__imp_GetWindowLongW
0x18004498a  bt      eax, 16h
0x18004498e  jnb     short loc_1800449AE
0x180044990  mov     ebx, r15d
0x180044993  test    [rdi+958h], r13d
0x18004499a  jnz     short loc_1800449B3
0x18004499c  mov     rcx, [rdi]; hWnd
0x18004499f  mov     edx, r14d; nIndex
0x1800449a2  call    cs:__imp_GetWindowLongW
0x1800449a8  bt      eax, 16h
0x1800449ac  jnb     short loc_1800449B3
0x1800449ae  mov     ebx, 2000h
0x1800449b3  mov     r8d, [rbp+57h+var_78.left]
0x1800449b7  mov     ecx, ebx; dwExStyle
0x1800449b9  mov     rax, [rdi+660h]
0x1800449c0  mov     r10d, [rbp+57h+var_78.top]
0x1800449c4  mov     edx, [rbp+57h+var_78.right]
0x1800449c7  mov     r9d, [rbp+57h+var_78.bottom]
0x1800449cb  sub     edx, r8d
0x1800449ce  mov     [rsp+120h+lpParam], r15; lpParam
0x1800449d3  sub     r9d, r10d
0x1800449d6  mov     [rsp+120h+hInstance], rax; hInstance
0x1800449db  mov     rax, [rdi]
0x1800449de  mov     [rsp+120h+hMenu], r15; hMenu
0x1800449e3  mov     [rsp+120h+hWndParent], rax; hWndParent
0x1800449e8  mov     [rsp+120h+nHeight], r9d; nHeight
0x1800449ed  mov     r9d, 50800880h; dwStyle
0x1800449f3  mov     dword ptr [rsp+120h+prcRect], edx; nWidth
0x1800449f7  lea     rdx, aEdit; "EDIT"
0x1800449fe  mov     dword ptr [rsp+120h+hWnd], r10d; Y
0x180044a03  mov     [rsp+120h+nReserved], r8d; X
0x180044a08  xor     r8d, r8d; lpWindowName
0x180044a0b  call    cs:__imp_CreateWindowExW
0x180044a11  mov     r14, rax
0x180044a14  test    rax, rax
0x180044a17  jz      loc_180044D19
0x180044a1d  mov     r8, [rdi+690h]; wParam
0x180044a24  xor     r9d, r9d; lParam
0x180044a27  mov     rcx, rax; hWnd
0x180044a2a  mov     [rdi+668h], rax
0x180044a31  lea     edx, [r9+30h]; Msg
0x180044a35  call    cs:__imp_SendMessageW
0x180044a3b  mov     edx, 0D3h; Msg
0x180044a40  mov     r9d, 10001h; lParam
0x180044a46  mov     r8d, 3; wParam
0x180044a4c  mov     rcx, r14; hWnd
0x180044a4f  call    cs:__imp_SendMessageW
0x180044a55  mov     rcx, rdi
0x180044a58  call    MCUpdateEditYear
0x180044a5d  mov     ecx, [rdi+940h]
0x180044a63  mov     edx, 270Fh
0x180044a68  movzx   r11d, word ptr [rdi+6E8h]
0x180044a70  mov     r13d, [rbp+57h+var_B0]
0x180044a74  add     r11d, ecx
0x180044a77  mov     eax, [rdi+958h]
0x180044a7d  add     r13d, ecx
0x180044a80  bt      eax, 0Ch
0x180044a84  jnb     short loc_180044A8F
0x180044a86  movzx   edx, word ptr [rdi+6F8h]
  ... truncated ...
```
