# ListView_DragSelect

- ea: `0x180051bec`
- end: `0x180052382`
- name: `ListView_DragSelect`
- size: `1942`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800530b4`

## callees

- `0x1800115f0`
- `0x180035f8c`
- `0x18005044c`
- `0x180051ac4`
- `0x180051bec`
- `0x180052cf8`
- `0x18005490c`
- `0x180057f4c`
- `0x1800590f4`
- `0x18005bb20`
- `0x18005e2c4`
- `0x180072c94`

## import_xrefs

- `GDI32!DeleteObject` at `0x18005233b`
- `GDI32!DeleteObject` at `0x180052349`
- `GDI32!DeleteObject` at `0x18005233b`
- `GDI32!DeleteObject` at `0x180052349`
- `GDI32!CreateRectRgn` at `0x180051ca4`
- `GDI32!CreateRectRgn` at `0x180051cc4`
- `GDI32!CreateRectRgn` at `0x180051ca4`
- `GDI32!CreateRectRgn` at `0x180051cc4`
- `GDI32!SelectClipRgn` at `0x180052261`
- `GDI32!SelectClipRgn` at `0x180052280`
- `GDI32!SelectClipRgn` at `0x180052261`
- `GDI32!SelectClipRgn` at `0x180052280`
- `GDI32!CombineRgn` at `0x180052255`
- `GDI32!CombineRgn` at `0x180052255`
- `USER32!GetClientRect` at `0x180051d4d`
- `USER32!GetClientRect` at `0x180051d4d`
- `USER32!GetParent` at `0x180051cde`
- `USER32!GetParent` at `0x180051cde`
- `USER32!GetDC` at `0x180051d23`
- `USER32!GetDC` at `0x180051d23`
- `USER32!ReleaseDC` at `0x18005232d`
- `USER32!ReleaseDC` at `0x18005232d`
- `USER32!SetCapture` at `0x180051d33`
- `USER32!SetCapture` at `0x180051d33`
- `USER32!PeekMessageW` at `0x180051d87`
- `USER32!PeekMessageW` at `0x180051d87`
- `USER32!CallMsgFilterW` at `0x180051e40`
- `USER32!CallMsgFilterW` at `0x180051e40`
- `USER32!PtInRect` at `0x180051d9d`
- `USER32!PtInRect` at `0x180051d9d`
- `USER32!TranslateMessage` at `0x1800522e5`
- `USER32!TranslateMessage` at `0x1800522e5`
- `USER32!DispatchMessageW` at `0x1800522f0`
- `USER32!DispatchMessageW` at `0x1800522f0`
- `USER32!WaitMessage` at `0x180051e2b`
- `USER32!WaitMessage` at `0x180051e2b`
- `USER32!GetCapture` at `0x180051d60`
- `USER32!GetCapture` at `0x1800522fc`
- `USER32!GetCapture` at `0x180051d60`
- `USER32!GetCapture` at `0x1800522fc`
- `USER32!SendMessageW` at `0x180052275`
- `USER32!SendMessageW` at `0x180052275`
- `USER32!UnionRect` at `0x180051f91`
- `USER32!UnionRect` at `0x180051f91`
- `USER32!ScreenToClient` at `0x180051eae`
- `USER32!ScreenToClient` at `0x180051eae`
- `USER32!InflateRect` at `0x180052134`
- `USER32!InflateRect` at `0x180052134`
- `USER32!UpdateWindow` at `0x180051c8b`
- `USER32!UpdateWindow` at `0x180052288`
- `USER32!UpdateWindow` at `0x180051c8b`
- `USER32!UpdateWindow` at `0x180052288`
- `USER32!IntersectRect` at `0x180052146`
- `USER32!IntersectRect` at `0x180052164`
- `USER32!IntersectRect` at `0x180052146`
- `USER32!IntersectRect` at `0x180052164`
- `USER32!EqualRect` at `0x180051f3a`
- `USER32!EqualRect` at `0x180051f3a`
- `USER32!SetCursorPos` at `0x180051e20`
- `USER32!SetCursorPos` at `0x180051e20`
- `USER32!DrawFocusRect` at `0x180051d40`
- `USER32!DrawFocusRect` at `0x180051f57`
- `USER32!DrawFocusRect` at `0x180052295`
- `USER32!DrawFocusRect` at `0x180052321`
- `USER32!DrawFocusRect` at `0x180051d40`
- `USER32!DrawFocusRect` at `0x180051f57`
- `USER32!DrawFocusRect` at `0x180052295`
- `USER32!DrawFocusRect` at `0x180052321`
- `USER32!OffsetRect` at `0x180051f7f`
- `USER32!OffsetRect` at `0x180051f7f`
- `USER32!GetWindowRgn` at `0x18005223e`
- `USER32!GetWindowRgn` at `0x18005223e`
- `USER32!GetUpdateRgn` at `0x180052220`
- `USER32!GetUpdateRgn` at `0x180052220`
- `USER32!LockWindowUpdate` at `0x180051ce7`
- `USER32!LockWindowUpdate` at `0x180052355`
- `USER32!LockWindowUpdate` at `0x180051ce7`
- `USER32!LockWindowUpdate` at `0x180052355`
- `USER32!GetDCEx` at `0x180051d00`
- `USER32!GetDCEx` at `0x180051d00`
- `USER32!ValidateRect` at `0x180052230`
- `USER32!ValidateRect` at `0x180052230`
- `USER32!GetWindowRect` at `0x180051d5a`
- `USER32!GetWindowRect` at `0x180051d5a`

## pseudocode

```c
int __fastcall ListView_DragSelect(__int64 a1, LONG a2, LONG a3)
{
  HWND v3; // r14
  int v5; // esi
  HRGN RectRgn; // rax
  HRGN v7; // r15
  HRGN v8; // rdi
  HWND Parent; // rax
  HDC DCEx; // rax
  HDC v11; // r12
  int v12; // r13d
  __int64 v13; // r8
  __int64 v14; // r8
  LONG x; // eax
  LONG y; // ecx
  unsigned int v17; // edi
  LONG v18; // edx
  unsigned int v19; // esi
  LONG v20; // r8d
  int v21; // r11d
  int v22; // r9d
  int v23; // r8d
  int v24; // edi
  int v25; // esi
  int v26; // ecx
  int v27; // r8d
  int v28; // r10d
  int v29; // r9d
  int v30; // r14d
  int v31; // ecx
  int v32; // r9d
  BOOL v33; // r13d
  int v34; // r12d
  BOOL v35; // eax
  char wParam; // cl
  int v37; // r15d
  HWND v38; // rcx
  int v40; // [rsp+30h] [rbp-D0h] BYREF
  int v41; // [rsp+34h] [rbp-CCh] BYREF
  int v42; // [rsp+38h] [rbp-C8h]
  int v43; // [rsp+3Ch] [rbp-C4h]
  struct tagPOINT Point; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v45; // [rsp+48h] [rbp-B8h] BYREF
  LONG v46; // [rsp+4Ch] [rbp-B4h]
  unsigned int v47; // [rsp+50h] [rbp-B0h] BYREF
  LONG v48; // [rsp+54h] [rbp-ACh]
  HRGN hRgn; // [rsp+58h] [rbp-A8h]
  int v50; // [rsp+60h] [rbp-A0h]
  struct tagMSG Msg; // [rsp+68h] [rbp-98h] BYREF
  HRGN v52; // [rsp+98h] [rbp-68h]
  HDC v53; // [rsp+A0h] [rbp-60h]
  HWND v54; // [rsp+A8h] [rbp-58h]
  RECT rc; // [rsp+B0h] [rbp-50h] BYREF
  RECT rcSrc2; // [rsp+C0h] [rbp-40h] BYREF
  struct tagRECT Rect; // [rsp+D0h] [rbp-30h] BYREF
  struct tagRECT rcDst; // [rsp+E0h] [rbp-20h] BYREF
  RECT rc2; // [rsp+F0h] [rbp-10h] BYREF
  RECT v60; // [rsp+100h] [rbp+0h] BYREF
  struct tagRECT v61; // [rsp+110h] [rbp+10h] BYREF

  v3 = *(HWND *)a1;
  rc.right = a2;
  rc.left = a2;
  v60 = 0;
  rc.bottom = a3;
  rcSrc2 = 0;
  rc.top = a3;
  memset(&Msg, 0, sizeof(Msg));
  v46 = a3;
  v5 = 0;
  v48 = a2;
  Point = 0;
  rc2 = rc;
  rcDst = 0;
  v54 = v3;
  Rect = 0;
  v40 = 0;
  v41 = 0;
  v47 = 0;
  v45 = 0;
  v42 = 0;
  UpdateWindow(v3);
  if ( (*(_DWORD *)(a1 + 76) & 0x200) != 0 )
  {
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    v52 = RectRgn;
    v7 = RectRgn;
    if ( !RectRgn )
      return (int)RectRgn;
    hRgn = CreateRectRgn(0, 0, 0, 0);
    v8 = hRgn;
    if ( !hRgn )
      goto LABEL_106;
    Parent = GetParent(v3);
    if ( !LockWindowUpdate(Parent) )
      goto LABEL_106;
    DCEx = GetDCEx(v3, 0, 0x420u);
    v5 = 1;
    v42 = 1;
  }
  else
  {
    hRgn = 0;
    v8 = 0;
    v52 = 0;
    v7 = 0;
    DCEx = GetDC(v3);
  }
  v53 = DCEx;
  v11 = DCEx;
  SetCapture(v3);
  DrawFocusRect(v11, &rc);
  GetClientRect(v3, &Rect);
  GetWindowRect(v3, &v60);
  if ( GetCapture() != v3 )
    goto LABEL_105;
  v12 = 0;
  while ( !PeekMessageW(&Msg, 0, 0, 0, 1u) )
  {
    if ( PtInRect(&v60, Msg.pt) )
    {
      WaitMessage();
      goto LABEL_101;
    }
    if ( (*(_DWORD *)(a1 + 16) & 0x200000) != 0 )
    {
      if ( Msg.pt.y < v60.bottom )
      {
        if ( Msg.pt.y > v60.top )
          goto LABEL_15;
        v13 = 0;
      }
      else
      {
        v13 = 1;
      }
      if ( (unsigned int)CanScroll(a1, 1, v13) )
        goto LABEL_23;
    }
LABEL_15:
    if ( (*(_DWORD *)(a1 + 16) & 0x100000) != 0 )
    {
      if ( Msg.pt.x < v60.right )
      {
        if ( Msg.pt.x > v60.left )
          goto LABEL_101;
        v14 = 0;
      }
      else
      {
        v14 = 1;
      }
      if ( (unsigned int)CanScroll(a1, 0, v14) )
LABEL_23:
        SetCursorPos(Msg.pt.x, Msg.pt.y);
    }
LABEL_101:
    if ( GetCapture() != v3 )
      goto LABEL_104;
  }
  if ( CallMsgFilterW(&Msg, 16898) )
    goto LABEL_101;
  if ( Msg.message <= 0x201 )
  {
    if ( Msg.message == 513 )
      goto LABEL_103;
    if ( Msg.message != 256 )
    {
      switch ( Msg.message )
      {
        case 0x101u:
        case 0x102u:
          goto LABEL_101;
        case 0x113u:
          if ( Msg.wParam == 44 )
          {
LABEL_35:
            Point = Msg.pt;
            ScreenToClient(v3, &Point);
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ScrollDetect)(a1, Point, &v47, &v45);
            x = Point.x;
            y = Point.y;
            v17 = v45;
            v18 = v46 - v45;
            v19 = v47;
            v20 = v48 - v47;
            v46 -= v45;
            if ( Point.x > Rect.right )
              x = Rect.right;
            v48 -= v47;
            if ( x < Rect.left )
              x = Rect.left;
            rc.left = v20;
            if ( Point.y > Rect.bottom )
              y = Rect.bottom;
            rc.top = v18;
            if ( y < Rect.top )
              y = Rect.top;
            rc.bottom = y;
            rc.right = x;
            if ( v20 > x )
            {
              rc.left = x;
              rc.right = v20;
            }
            if ( y < v18 )
            {
              rc.bottom = v18;
              rc.top = y;
            }
            if ( EqualRect(&rc, &rc2) )
            {
              v5 = v42;
            }
            else
            {
              v43 = -1;
              DrawFocusRect(v11, &rc2);
              if ( v19 || v17 )
                ListView_OnScroll(a1, v19, v17);
              OffsetRect(&rc2, -v19, -v17);
              UnionRect(&rcDst, &rc, &rc2);
              v21 = *(_DWORD *)(a1 + 16);
              if ( (v21 & 3) == 1 )
              {
                v22 = *(_DWORD *)(a1 + 256);
                v23 = *(_DWORD *)(a1 + 460) - *(_DWORD *)(a1 + 448);
                v24 = (v23 + rcDst.top) / v22;
                v25 = (v23 + rcDst.bottom) / v22 + 1;
              }
              else if ( (v21 & 3) == 3 )
              {
                v26 = *(_DWORD *)(a1 + 248);
                v27 = *(_DWORD *)(a1 + 252);
                v28 = *(_DWORD *)(a1 + 256);
                v29 = *(_DWORD *)(a1 + 260);
                v24 = rcDst.top / v28 + v29 * ((v26 + rcDst.left) / v27);
                v25 = v29 * ((v26 + rcDst.right) / v27) + rcDst.bottom / v28 + 1;
              }
              else if ( (v21 & 0x1000) != 0 )
              {
                ListView_CalcMinMaxIndex(a1, &rcDst, &v40, &v41);
                v21 = *(_DWORD *)(a1 + 16);
                v24 = v40;
                v25 = v41;
              }
              else
              {
                v25 = *(_DWORD *)(a1 + 512);
                v24 = 0;
              }
              if ( v25 > *(_DWORD *)(a1 + 512) )
                v25 = *(_DWORD *)(a1 + 512);
              v41 = v25;
              if ( v24 < 0 )
                v24 = 0;
              v40 = v24;
              if ( (v21 & 0x1000) != 0 && v24 < v25 )
                ListView_NotifyCacheHint(a1, (unsigned int)v24, (unsigned int)(v25 - 1));
              if ( v12 && (Msg.wParam & 0xC) == 0 )
                *(_DWORD *)(a1 + 148) = -1;
              if ( v24 < v25 )
              {
                v30 = v43;
                do
                {
                  v61 = 0;
                  ListView_GetRects(a1, v24, 0, 0, 0, &rcSrc2);
                  v31 = *(_DWORD *)(a1 + 16) & 3;
                  if ( v31 != 1 || (*(_BYTE *)(a1 + 76) & 0x20) == 0 )
                  {
                    v32 = (rcSrc2.right - rcSrc2.left) / 4;
                    if ( v31 == 3 && v32 >= *(_DWORD *)(a1 + 240) )
                      v32 = *(_DWORD *)(a1 + 240);
                    InflateRect(&rcSrc2, -v32, (rcSrc2.bottom - rcSrc2.top) / -4);
                  }
                  v33 = IntersectRect(&v61, &rc2, &rcSrc2);
                  v34 = v33;
                  v35 = IntersectRect(&v61, &rc, &rcSrc2);
                  wParam = Msg.wParam;
                  v43 = v35;
                  v37 = v35;
                  v50 = v37;
                  if ( (Msg.wParam & 8) != 0 )
                  {
                    if ( v34 != v37 )
                      ListView_ToggleSelection(a1, (unsigned int)v24);
                  }
                  else
                  {
                    if ( v34 != v37 )
                    {
                      ListView_OnSetItemState(a1, (unsigned int)v24, !v33 ? 2 : 0, 2);
                      wParam = Msg.wParam;
                      v35 = v43;
                    }
                    if ( v35
                      && (wParam & 0xC) == 0
                      && (rcSrc2.left - Point.x) * (rcSrc2.left - Point.x)
                       + (rcSrc2.top - Point.y) * (rcSrc2.top - Point.y) > v30 )
                    {
                      v30 = (rcSrc2.left - Point.x) * (rcSrc2.left - Point.x)
                          + (rcSrc2.top - Point.y) * (rcSrc2.top - Point.y);
                      *(_DWORD *)(a1 + 148) = v24;
                    }
                  }
                  ++v24;
                }
                while ( v24 < v25 );
                v3 = v54;
                v7 = v52;
                v11 = v53;
                v12 = v50;
                v40 = v24;
              }
              v5 = v42;
              v38 = *(HWND *)a1;
              if ( v42 )
              {
                if ( GetUpdateRgn(v38, v7, 0) > 1 )
                {
                  ValidateRect(*(HWND *)a1, 0);
                  GetWindowRgn(*(HWND *)a1, hRgn);
                  CombineRgn(v7, v7, hRgn, 1);
                  SelectClipRgn(v11, v7);
                  SendMessageW(*(HWND *)a1, 0x318u, (WPARAM)v11, 0);
                  SelectClipRgn(v11, 0);
                }
              }
              else
              {
                UpdateWindow(v38);
              }
              DrawFocusRect(v11, &rc);
              rc2 = rc;
            }
            goto LABEL_101;
          }
          break;
        case 0x200u:
          goto LABEL_35;
      }
LABEL_99:
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
      goto LABEL_101;
    }
    if ( Msg.wParam == 27 )
    {
      ListView_DeselectAll(a1);
      goto LABEL_104;
    }
    goto LABEL_101;
  }
  if ( Msg.message != 514 && Msg.message != 516 && Msg.message != 517 && Msg.message - 519 >= 2 )
  {
    if ( Msg.message != 522 )
      goto LABEL_99;
    goto LABEL_101;
  }
LABEL_103:
  CCReleaseCapture(a1);
LABEL_104:
  v8 = hRgn;
LABEL_105:
  DrawFocusRect(v11, &rc2);
  LODWORD(RectRgn) = ReleaseDC(v3, v11);
  if ( v7 )
LABEL_106:
    LODWORD(RectRgn) = DeleteObject(v7);
  if ( v8 )
    LODWORD(RectRgn) = DeleteObject(v8);
  if ( v5 )
    LODWORD(RectRgn) = LockWindowUpdate(0);
  return (int)RectRgn;
}

```

## disassembly

```asm
0x180051bec  mov     [rsp-8+arg_18], rbx
0x180051bf1  push    rbp
0x180051bf2  push    rsi
0x180051bf3  push    rdi
0x180051bf4  push    r12
0x180051bf6  push    r13
0x180051bf8  push    r14
0x180051bfa  push    r15
0x180051bfc  lea     rbp, [rsp-30h]
0x180051c01  sub     rsp, 130h
0x180051c08  mov     rax, cs:__security_cookie
0x180051c0f  xor     rax, rsp
0x180051c12  mov     [rbp+60h+var_40], rax
0x180051c16  mov     r14, [rcx]
0x180051c19  xorps   xmm0, xmm0
0x180051c1c  xor     r12d, r12d
0x180051c1f  mov     [rbp+60h+rc.right], edx
0x180051c22  xorps   xmm1, xmm1
0x180051c25  mov     [rbp+60h+rc.left], edx
0x180051c28  movups  xmmword ptr [rbp+60h+var_60.left], xmm0
0x180051c2c  mov     [rbp+60h+rc.bottom], r8d
0x180051c30  mov     rbx, rcx
0x180051c33  movups  xmmword ptr [rbp+60h+rcSrc2.left], xmm0
0x180051c37  mov     [rbp+60h+rc.top], r8d
0x180051c3b  mov     rcx, r14; hWnd
0x180051c3e  movups  xmmword ptr [rsp+160h+Msg.hwnd], xmm0
0x180051c43  mov     [rsp+160h+var_114], r8d
0x180051c48  mov     esi, r12d
0x180051c4b  movups  xmmword ptr [rsp+160h+Msg.wParam], xmm0
0x180051c50  mov     [rsp+160h+var_10C], edx
0x180051c54  movups  xmmword ptr [rbp+60h+Msg.time], xmm0
0x180051c58  mov     qword ptr [rsp+160h+Point.x], r12
0x180051c5d  movaps  xmm0, xmmword ptr [rbp+60h+rc.left]
0x180051c61  movdqa  xmmword ptr [rbp+60h+rc2.left], xmm0
0x180051c66  movups  xmmword ptr [rbp+60h+rcDst.left], xmm1
0x180051c6a  mov     [rbp+60h+var_B8], r14
0x180051c6e  movups  xmmword ptr [rbp+60h+Rect.left], xmm1
0x180051c72  mov     [rsp+160h+var_130], r12d
0x180051c77  mov     [rsp+160h+var_12C], r12d
0x180051c7c  mov     [rsp+160h+var_110], r12d
0x180051c81  mov     [rsp+160h+var_118], r12d
0x180051c86  mov     [rsp+160h+var_128], r12d
0x180051c8b  call    cs:__imp_UpdateWindow
0x180051c91  test    dword ptr [rbx+4Ch], 200h
0x180051c98  jz      short loc_180051D11
0x180051c9a  xor     r9d, r9d; y2
0x180051c9d  xor     r8d, r8d; x2
0x180051ca0  xor     edx, edx; y1
0x180051ca2  xor     ecx, ecx; x1
0x180051ca4  call    cs:__imp_CreateRectRgn
0x180051caa  mov     [rbp+60h+var_C8], rax
0x180051cae  mov     r15, rax
0x180051cb1  test    rax, rax
0x180051cb4  jz      loc_18005235B
0x180051cba  xor     r9d, r9d; y2
0x180051cbd  xor     r8d, r8d; x2
0x180051cc0  xor     edx, edx; y1
0x180051cc2  xor     ecx, ecx; x1
0x180051cc4  call    cs:__imp_CreateRectRgn
0x180051cca  mov     [rsp+160h+hRgn], rax
0x180051ccf  mov     rdi, rax
0x180051cd2  test    rax, rax
0x180051cd5  jz      loc_180052338
0x180051cdb  mov     rcx, r14; hWnd
0x180051cde  call    cs:__imp_GetParent
0x180051ce4  mov     rcx, rax; hWndLock
0x180051ce7  call    cs:__imp_LockWindowUpdate
0x180051ced  test    eax, eax
0x180051cef  jz      loc_180052338
0x180051cf5  xor     edx, edx; hrgnClip
0x180051cf7  mov     r8d, 420h; flags
0x180051cfd  mov     rcx, r14; hWnd
0x180051d00  call    cs:__imp_GetDCEx
0x180051d06  lea     esi, [r12+1]
0x180051d0b  mov     [rsp+160h+var_128], esi
0x180051d0f  jmp     short loc_180051D29
0x180051d11  mov     rcx, r14; hWnd
0x180051d14  mov     [rsp+160h+hRgn], r12
0x180051d19  mov     rdi, r12
0x180051d1c  mov     [rbp+60h+var_C8], r12
0x180051d20  mov     r15, r12
0x180051d23  call    cs:__imp_GetDC
0x180051d29  mov     rcx, r14; hWnd
0x180051d2c  mov     [rbp+60h+var_C0], rax
0x180051d30  mov     r12, rax
0x180051d33  call    cs:__imp_SetCapture
0x180051d39  lea     rdx, [rbp+60h+rc]; lprc
0x180051d3d  mov     rcx, r12; hDC
0x180051d40  call    cs:__imp_DrawFocusRect
0x180051d46  lea     rdx, [rbp+60h+Rect]; lpRect
0x180051d4a  mov     rcx, r14; hWnd
0x180051d4d  call    cs:__imp_GetClientRect
0x180051d53  lea     rdx, [rbp+60h+var_60]; lpRect
0x180051d57  mov     rcx, r14; hWnd
0x180051d5a  call    cs:__imp_GetWindowRect
0x180051d60  call    cs:__imp_GetCapture
0x180051d66  cmp     rax, r14
0x180051d69  jnz     loc_18005231A
0x180051d6f  xor     r13d, r13d
0x180051d72  xor     r9d, r9d; wMsgFilterMax
0x180051d75  mov     [rsp+160h+wRemoveMsg], 1; wRemoveMsg
0x180051d7d  xor     r8d, r8d; wMsgFilterMin
0x180051d80  lea     rcx, [rsp+160h+Msg]; lpMsg
0x180051d85  xor     edx, edx; hWnd
0x180051d87  call    cs:__imp_PeekMessageW
0x180051d8d  test    eax, eax
0x180051d8f  jnz     loc_180051E36
0x180051d95  mov     rdx, qword ptr [rbp+60h+Msg.pt.x]; pt
0x180051d99  lea     rcx, [rbp+60h+var_60]; lprc
0x180051d9d  call    cs:__imp_PtInRect
0x180051da3  test    eax, eax
0x180051da5  jnz     loc_180051E2B
0x180051dab  test    dword ptr [rbx+10h], 200000h
0x180051db2  jz      short loc_180051DD0
0x180051db4  mov     eax, [rbp+60h+Msg.pt.y]
0x180051db7  cmp     eax, [rbp+60h+var_60.bottom]
0x180051dba  jl      short loc_180051DEE
0x180051dbc  mov     edx, 1
0x180051dc1  mov     r8d, edx
0x180051dc4  mov     rcx, rbx
0x180051dc7  call    CanScroll
0x180051dcc  test    eax, eax
0x180051dce  jnz     short loc_180051E1A
0x180051dd0  test    dword ptr [rbx+10h], 100000h
0x180051dd7  jz      loc_1800522FC
0x180051ddd  mov     rax, qword ptr [rbp+60h+Msg.pt.x]
0x180051de1  cmp     eax, [rbp+60h+var_60.right]
0x180051de4  jl      short loc_180051DFC
0x180051de6  mov     r8d, 1
0x180051dec  jmp     short loc_180051E08
0x180051dee  cmp     eax, [rbp+60h+var_60.top]
0x180051df1  jg      short loc_180051DD0
0x180051df3  xor     r8d, r8d
0x180051df6  lea     edx, [r8+1]
0x180051dfa  jmp     short loc_180051DC4
0x180051dfc  cmp     eax, [rbp+60h+var_60.left]
0x180051dff  jg      loc_1800522FC
0x180051e05  xor     r8d, r8d
0x180051e08  xor     edx, edx
0x180051e0a  mov     rcx, rbx
0x180051e0d  call    CanScroll
0x180051e12  test    eax, eax
0x180051e14  jz      loc_1800522FC
0x180051e1a  mov     edx, [rbp+60h+Msg.pt.y]; Y
0x180051e1d  mov     ecx, [rbp+60h+Msg.pt.x]; X
0x180051e20  call    cs:__imp_SetCursorPos
0x180051e26  jmp     loc_1800522FC
0x180051e2b  call    cs:__imp_WaitMessage
0x180051e31  jmp     loc_1800522FC
0x180051e36  mov     edx, 4202h; nCode
0x180051e3b  lea     rcx, [rsp+160h+Msg]; lpMsg
0x180051e40  call    cs:__imp_CallMsgFilterW
0x180051e46  test    eax, eax
0x180051e48  jnz     loc_1800522FC
0x180051e4e  mov     eax, [rsp+160h+Msg.message]
0x180051e52  cmp     eax, 201h
0x180051e57  ja      loc_1800522BB
0x180051e5d  jz      loc_18005230D
0x180051e63  sub     eax, 100h
0x180051e68  jz      loc_1800522A6
0x180051e6e  sub     eax, 1
0x180051e71  jz      loc_1800522FC
0x180051e77  sub     eax, 1
0x180051e7a  jz      loc_1800522FC
0x180051e80  sub     eax, 11h
0x180051e83  jz      short loc_180051E91
0x180051e85  cmp     eax, 0EDh
0x180051e8a  jz      short loc_180051E9D
0x180051e8c  jmp     loc_1800522E0
0x180051e91  cmp     [rsp+160h+Msg.wParam], 2Ch ; ','
0x180051e97  jnz     loc_1800522E0
0x180051e9d  mov     rax, qword ptr [rbp+60h+Msg.pt.x]
0x180051ea1  lea     rdx, [rsp+160h+Point]; lpPoint
0x180051ea6  mov     rcx, r14; hWnd
0x180051ea9  mov     qword ptr [rsp+160h+Point.x], rax
0x180051eae  call    cs:__imp_ScreenToClient
0x180051eb4  mov     rdx, qword ptr [rsp+160h+Point.x]
0x180051eb9  lea     r9, [rsp+160h+var_118]
0x180051ebe  lea     r8, [rsp+160h+var_110]
0x180051ec3  mov     rcx, rbx
0x180051ec6  call    ScrollDetect
0x180051ecb  mov     edx, [rsp+160h+var_114]
0x180051ecf  mov     r8d, [rsp+160h+var_10C]
0x180051ed4  mov     rax, qword ptr [rsp+160h+Point.x]
0x180051ed9  mov     ecx, [rsp+160h+Point.y]
0x180051edd  mov     edi, [rsp+160h+var_118]
0x180051ee1  sub     edx, edi
0x180051ee3  mov     esi, [rsp+160h+var_110]
0x180051ee7  sub     r8d, esi
0x180051eea  cmp     eax, [rbp+60h+Rect.right]
0x180051eed  mov     [rsp+160h+var_114], edx
0x180051ef1  cmovg   eax, [rbp+60h+Rect.right]
0x180051ef5  cmp     eax, [rbp+60h+Rect.left]
0x180051ef8  mov     [rsp+160h+var_10C], r8d
0x180051efd  cmovl   eax, [rbp+60h+Rect.left]
0x180051f01  cmp     ecx, [rbp+60h+Rect.bottom]
0x180051f04  mov     [rbp+60h+rc.left], r8d
0x180051f08  cmovg   ecx, [rbp+60h+Rect.bottom]
0x180051f0c  cmp     ecx, [rbp+60h+Rect.top]
0x180051f0f  mov     [rbp+60h+rc.top], edx
0x180051f12  cmovl   ecx, [rbp+60h+Rect.top]
0x180051f16  mov     [rbp+60h+rc.bottom], ecx
0x180051f19  mov     [rbp+60h+rc.right], eax
0x180051f1c  cmp     r8d, eax
0x180051f1f  jle     short loc_180051F28
0x180051f21  mov     [rbp+60h+rc.left], eax
0x180051f24  mov     [rbp+60h+rc.right], r8d
0x180051f28  cmp     ecx, edx
0x180051f2a  jge     short loc_180051F32
0x180051f2c  mov     [rbp+60h+rc.bottom], edx
0x180051f2f  mov     [rbp+60h+rc.top], ecx
0x180051f32  lea     rdx, [rbp+60h+rc2]; lprc2
0x180051f36  lea     rcx, [rbp+60h+rc]; lprc1
0x180051f3a  call    cs:__imp_EqualRect
0x180051f40  test    eax, eax
0x180051f42  jnz     loc_1800522F8
0x180051f48  lea     rdx, [rbp+60h+rc2]; lprc
0x180051f4c  mov     [rsp+160h+var_124], 0FFFFFFFFh
0x180051f54  mov     rcx, r12; hDC
0x180051f57  call    cs:__imp_DrawFocusRect
0x180051f5d  test    esi, esi
0x180051f5f  jnz     short loc_180051F65
0x180051f61  test    edi, edi
0x180051f63  jz      short loc_180051F72
0x180051f65  mov     r8d, edi
0x180051f68  mov     edx, esi
0x180051f6a  mov     rcx, rbx
0x180051f6d  call    ListView_OnScroll
0x180051f72  neg     edi
0x180051f74  lea     rcx, [rbp+60h+rc2]; lprc
0x180051f78  neg     esi
0x180051f7a  mov     r8d, edi; dy
0x180051f7d  mov     edx, esi; dx
0x180051f7f  call    cs:__imp_OffsetRect
0x180051f85  lea     r8, [rbp+60h+rc2]; lprcSrc2
0x180051f89  lea     rdx, [rbp+60h+rc]; lprcSrc1
0x180051f8d  lea     rcx, [rbp+60h+rcDst]; lprcDst
0x180051f91  call    cs:__imp_UnionRect
0x180051f97  mov     r11d, [rbx+10h]
0x180051f9b  mov     eax, r11d
0x180051f9e  and     eax, 3
0x180051fa1  cmp     eax, 1
0x180051fa4  jnz     short loc_180051FD9
0x180051fa6  mov     r9d, [rbx+100h]
0x180051fad  mov     r8d, [rbx+1CCh]
0x180051fb4  sub     r8d, [rbx+1C0h]
0x180051fbb  mov     eax, [rbp+60h+rcDst.top]
0x180051fbe  add     eax, r8d
0x180051fc1  cdq
0x180051fc2  idiv    r9d
0x180051fc5  mov     edi, eax
0x180051fc7  mov     eax, [rbp+60h+rcDst.bottom]
0x180051fca  add     eax, r8d
0x180051fcd  cdq
0x180051fce  idiv    r9d
0x180051fd1  lea     esi, [rax+1]
0x180051fd4  jmp     loc_180052061
0x180051fd9  cmp     eax, 3
0x180051fdc  jnz     short loc_18005202E
0x180051fde  mov     ecx, [rbx+0F8h]
0x180051fe4  mov     r8d, [rbx+0FCh]
0x180051feb  mov     eax, [rbp+60h+rcDst.left]
0x180051fee  mov     r10d, [rbx+100h]
0x180051ff5  add     eax, ecx
0x180051ff7  mov     r9d, [rbx+104h]
0x180051ffe  cdq
0x180051fff  idiv    r8d
0x180052002  mov     edi, eax
0x180052004  mov     eax, [rbp+60h+rcDst.top]
0x180052007  cdq
0x180052008  imul    edi, r9d
0x18005200c  idiv    r10d
0x18005200f  add     edi, eax
0x180052011  mov     eax, [rbp+60h+rcDst.right]
0x180052014  add     eax, ecx
0x180052016  cdq
0x180052017  idiv    r8d
0x18005201a  mov     ecx, eax
0x18005201c  mov     eax, [rbp+60h+rcDst.bottom]
0x18005201f  cdq
0x180052020  imul    ecx, r9d
0x180052024  idiv    r10d
0x180052027  lea     esi, [rax+1]
0x18005202a  add     esi, ecx
0x18005202c  jmp     short loc_180052061
0x18005202e  bt      r11d, 0Ch
0x180052033  jnb     short loc_180052059
0x180052035  lea     r9, [rsp+160h+var_12C]
0x18005203a  mov     rcx, rbx
0x18005203d  lea     r8, [rsp+160h+var_130]
0x180052042  lea     rdx, [rbp+60h+rcDst]
0x180052046  call    ListView_CalcMinMaxIndex
0x18005204b  mov     r11d, [rbx+10h]
0x18005204f  mov     edi, [rsp+160h+var_130]
0x180052053  mov     esi, [rsp+160h+var_12C]
0x180052057  jmp     short loc_180052061
0x180052059  mov     esi, [rbx+200h]
0x18005205f  xor     edi, edi
0x180052061  mov     eax, [rbx+200h]
0x180052067  cmp     esi, eax
  ... truncated ...
```
