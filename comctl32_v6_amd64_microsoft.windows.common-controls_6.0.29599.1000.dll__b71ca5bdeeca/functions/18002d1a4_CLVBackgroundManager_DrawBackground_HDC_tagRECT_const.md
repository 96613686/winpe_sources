# CLVBackgroundManager::DrawBackground(HDC__ *,tagRECT const *)

- ea: `0x18002d1a4`
- end: `0x18002d97a`
- name: `?DrawBackground@CLVBackgroundManager@@QEAAXPEAUHDC__@@PEBUtagRECT@@@Z`
- size: `2006`
- prototype: `void __fastcall(CLVBackgroundManager *__hidden this, HDC, const struct tagRECT *)`
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18002d9a0`
- `0x18005fe40`
- `0x1800be680`

## callees

- `0x180007fc4`
- `0x18002d1a4`
- `0x180091cf0`
- `0x180091ed0`
- `0x180092010`
- `0x1800a975c`
- `0x1800b1d5c`
- `0x1800be478`
- `0x1801038ac`
- `0x180114520`
- `0x1801c70f8`
- `0x1801c73f8`
- `0x1801c74c8`
- `0x1801d1010`

## import_xrefs

- `GDI32!IntersectClipRect` at `0x18002d37d`
- `GDI32!IntersectClipRect` at `0x18002d37d`
- `GDI32!DeleteObject` at `0x18002d3db`
- `GDI32!DeleteObject` at `0x18002d4a1`
- `GDI32!DeleteObject` at `0x18002d3db`
- `GDI32!DeleteObject` at `0x18002d4a1`
- `GDI32!RectVisible` at `0x18002d3ab`
- `GDI32!RectVisible` at `0x18002d6a9`
- `GDI32!RectVisible` at `0x18002d3ab`
- `GDI32!RectVisible` at `0x18002d6a9`
- `GDI32!SelectObject` at `0x18002d84a`
- `GDI32!SelectObject` at `0x18002d8ef`
- `GDI32!SelectObject` at `0x18002d84a`
- `GDI32!SelectObject` at `0x18002d8ef`
- `GDI32!ExcludeClipRect` at `0x18002d728`
- `GDI32!ExcludeClipRect` at `0x18002d728`
- `GDI32!SelectClipRgn` at `0x18002d3c9`
- `GDI32!SelectClipRgn` at `0x18002d3c9`
- `GDI32!DeleteDC` at `0x18002d8f8`
- `GDI32!DeleteDC` at `0x18002d8f8`
- `GDI32!CreateCompatibleDC` at `0x18002d831`
- `GDI32!CreateCompatibleDC` at `0x18002d831`
- `GDI32!GetClipBox` at `0x18002d46d`
- `GDI32!GetClipBox` at `0x18002d46d`
- `GDI32!BitBlt` at `0x18002d5c4`
- `GDI32!BitBlt` at `0x18002d701`
- `GDI32!BitBlt` at `0x18002d8e3`
- `GDI32!BitBlt` at `0x18002d5c4`
- `GDI32!BitBlt` at `0x18002d701`
- `GDI32!BitBlt` at `0x18002d8e3`
- `GDI32!OffsetWindowOrgEx` at `0x18002d296`
- `GDI32!OffsetWindowOrgEx` at `0x18002d296`
- `GDI32!SetWindowOrgEx` at `0x18002d2ee`
- `GDI32!SetWindowOrgEx` at `0x18002d2ee`
- `GDI32!GdiAlphaBlend` at `0x18002d8bd`
- `GDI32!GdiAlphaBlend` at `0x18002d8bd`
- `GDI32!GetClipRgn` at `0x18002d490`
- `GDI32!GetClipRgn` at `0x18002d490`
- `GDI32!CreateRectRgnIndirect` at `0x18002d357`
- `GDI32!CreateRectRgnIndirect` at `0x18002d357`
- `USER32!FillRect` at `0x18002d3f3`
- `USER32!FillRect` at `0x18002d3f3`
- `USER32!OffsetRect` at `0x18002d77a`
- `USER32!OffsetRect` at `0x18002d935`
- `USER32!OffsetRect` at `0x18002d77a`
- `USER32!OffsetRect` at `0x18002d935`
- `USER32!IntersectRect` at `0x18002d7a5`
- `USER32!IntersectRect` at `0x18002d7a5`
- `USER32!MapWindowPoints` at `0x18002d282`
- `USER32!MapWindowPoints` at `0x18002d282`
- `USER32!SendMessageW` at `0x18002d2be`
- `USER32!SendMessageW` at `0x18002d2db`
- `USER32!SendMessageW` at `0x18002d2be`
- `USER32!SendMessageW` at `0x18002d2db`
- `USER32!GetClientRect` at `0x18002d61e`
- `USER32!GetClientRect` at `0x18002d866`
- `USER32!GetClientRect` at `0x18002d61e`
- `USER32!GetClientRect` at `0x18002d866`

## pseudocode

```c
void __fastcall CLVBackgroundManager::DrawBackground(CLVBackgroundManager *this, HDC a2, struct tagRECT *a3)
{
  struct tagRECT *p_rect; // rsi
  __int64 v6; // r10
  __int16 v7; // r8
  _DWORD *v8; // rax
  LONG v9; // r14d
  LONG v10; // r15d
  UINT v11; // edx
  int v12; // r12d
  __int64 v13; // rcx
  HRGN RectRgnIndirect; // rax
  HRGN v15; // r13
  __int64 v16; // rcx
  struct tagPOINT *v17; // r8
  __int64 v18; // rdx
  bool HasCustomTheme; // al
  __int64 v20; // rax
  HDC hdcSrc; // r14
  HBITMAP v22; // r15
  HDC v23; // rax
  HDC v24; // rdx
  LONG bottom; // eax
  LONG right; // r9d
  LONG top; // r8d
  int left; // edx
  __int64 v29; // rcx
  int v30; // r8d
  LONG v31; // r9d
  int v32; // edx
  LONG v33; // eax
  LONG v34; // ecx
  RECT v35; // xmm0
  LONG x; // eax
  LONG v37; // eax
  struct tagPOINT *v38; // r8
  HDC v39; // r14
  int v40; // edx
  HDC CompatibleDC; // rax
  HDC v42; // r15
  HGDIOBJ v43; // rax
  __int64 v44; // rcx
  void *v45; // r13
  int v46; // r9d
  int v47; // edx
  int hSrc; // ecx
  int v49; // r8d
  __int64 v50; // rcx
  CListView *v51; // rcx
  int v52; // eax
  LONG v53; // eax
  COLORREF SortColumnColor; // eax
  struct tagPOINT v55; // [rsp+60h] [rbp-59h] BYREF
  UINT v56; // [rsp+68h] [rbp-51h]
  HBITMAP v57; // [rsp+70h] [rbp-49h] BYREF
  RECT rcDst; // [rsp+78h] [rbp-41h] BYREF
  BLENDFUNCTION v59; // [rsp+88h] [rbp-31h] BYREF
  struct tagPOINT pt; // [rsp+90h] [rbp-29h] BYREF
  struct tagPOINT Points[2]; // [rsp+98h] [rbp-21h] BYREF
  RECT v62; // [rsp+A8h] [rbp-11h] BYREF
  struct tagRECT Rect; // [rsp+B8h] [rbp-1h] BYREF
  struct tagRECT rect; // [rsp+C8h] [rbp+Fh] BYREF

  v55 = 0;
  p_rect = a3;
  rect = 0;
  if ( !a3 )
  {
    GetClipBox(a2, &rect);
    p_rect = &rect;
  }
  v6 = *((_QWORD *)this + 9);
  v7 = *(_WORD *)(v6 + 164);
  if ( v7 == 1 )
  {
    v18 = *(_QWORD *)(v6 + 640);
    v9 = -*(_DWORD *)(v18 + 28);
    v10 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 608) + 16LL) + 20LL) - *(_DWORD *)(v18 + 32);
  }
  else
  {
    v8 = *(_DWORD **)(v6 + 448);
    if ( *(_WORD *)(v6 + 164) == 3 )
    {
      v10 = 0;
      v9 = -v8[1];
      v55.y = 0;
      goto LABEL_7;
    }
    v9 = -v8[2];
    v10 = -v8[3];
  }
  v55.y = v10;
LABEL_7:
  v11 = 1;
  v55.x = v9;
  v12 = 0;
  if ( v7 != 1
    || (LOBYTE(v12) = *(_DWORD *)(*(_QWORD *)(v6 + 640) + 24LL) != -1,
        HasCustomTheme = CLVThemesManager::HasCustomTheme(*(CLVThemesManager **)(v6 + 472)),
        v56 = v11,
        !HasCustomTheme) )
  {
    v56 = 0;
  }
  if ( *((_QWORD *)this + 1) && *(_DWORD *)this || (*(_DWORD *)(v6 + 176) & 0x400000) != 0 && v12 )
  {
    RectRgnIndirect = CreateRectRgnIndirect(p_rect);
    v15 = RectRgnIndirect;
    if ( RectRgnIndirect && GetClipRgn(a2, RectRgnIndirect) <= 0 )
    {
      DeleteObject(v15);
      v15 = 0;
    }
    IntersectClipRect(a2, p_rect->left, p_rect->top, p_rect->right, p_rect->bottom);
    if ( *((_QWORD *)this + 1) && *(_DWORD *)this )
    {
      v59 = 0;
      Points[0] = 0;
      rcDst = 0;
      Rect = 0;
      CLVBackgroundManager::Realize(this, a2, 1, 0);
      if ( (*((_BYTE *)this + 16) & 0x10) != 0 )
      {
        v20 = *((_QWORD *)this + 9);
        *(_QWORD *)&v62.left = 0;
        hdcSrc = a2;
        pt = 0;
        v22 = 0;
        v57 = 0;
        if ( *(_WORD *)(v20 + 164) == 1 && *(_DWORD *)(*(_QWORD *)(v20 + 640) + 24LL) != -1 )
        {
          v23 = PrepBackgroundDIBSection(a2, p_rect, (void **)&v62, &v57);
          v22 = v57;
          hdcSrc = v23;
          if ( !v23 )
            hdcSrc = a2;
        }
        if ( (*((_DWORD *)this + 4) & 0x100) != 0 )
        {
          pt.x -= *((_DWORD *)this + 10);
          pt.y -= *((_DWORD *)this + 11);
        }
        (*(void (__fastcall **)(_QWORD, HDC, struct tagPOINT *, struct tagRECT *, _QWORD))(**((_QWORD **)this + 1) + 88LL))(
          *((_QWORD *)this + 1),
          hdcSrc,
          &pt,
          p_rect,
          0);
        if ( hdcSrc != a2 )
        {
          if ( *(_QWORD *)&v62.left )
            SaturateSortColumn(*((struct CListView **)this + 9), v24, *(void **)&v62.left, &v55, p_rect);
          BitBlt(
            a2,
            p_rect->left,
            p_rect->top,
            p_rect->right - p_rect->left,
            p_rect->bottom - p_rect->top,
            hdcSrc,
            p_rect->left,
            p_rect->top,
            0xCC0020u);
          CleanupBackgroundDIBSection(hdcSrc, v22);
        }
        bottom = p_rect->bottom;
        right = p_rect->right;
        top = p_rect->top;
        left = p_rect->left;
        goto LABEL_61;
      }
      (*(void (__fastcall **)(_QWORD, BLENDFUNCTION *, struct tagPOINT *, _QWORD))(**((_QWORD **)this + 1) + 64LL))(
        *((_QWORD *)this + 1),
        &v59,
        Points,
        0);
      v29 = *((_QWORD *)this + 9);
      *(struct tagPOINT *)&rcDst.right = Points[0];
      *(_QWORD *)&rcDst.left = 0;
      GetClientRect(*(HWND *)(v29 + 96), &Rect);
      v30 = 0;
      v31 = rcDst.right;
      if ( *((_DWORD *)this + 10) )
      {
        v30 = *((_DWORD *)this + 10) * (Rect.right - Points[0].x) / 100;
        v31 = v30 + rcDst.right;
      }
      if ( *((_DWORD *)this + 11) )
      {
        v32 = *((_DWORD *)this + 11) * (Rect.bottom - Points[0].y) / 100;
        v33 = v32 + rcDst.top;
        v34 = v32 + rcDst.bottom;
      }
      else
      {
        v34 = rcDst.bottom;
        v33 = rcDst.top;
      }
      rcDst.bottom = v10 + v34;
      rcDst.left = v9 + v30;
      rcDst.top = v10 + v33;
      rcDst.right = v9 + v31;
      if ( !RectVisible(a2, &rcDst) )
        goto LABEL_25;
      (*(void (__fastcall **)(_QWORD, HDC, RECT *))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1), a2, &rcDst);
    }
    else
    {
      v16 = *((_QWORD *)this + 9);
      if ( (*(_DWORD *)(v16 + 176) & 0x400000) == 0 || !v12 )
        goto LABEL_25;
      v35 = *p_rect;
      *(_QWORD *)&v62.left = 0;
      rcDst = v35;
      v57 = 0;
      *(_OWORD *)&Points[0].x = 0;
      CLVHeaderControlManager::GetItemRect(
        *(CLVHeaderControlManager **)(v16 + 392),
        *(_DWORD *)(*(_QWORD *)(v16 + 640) + 24LL),
        (struct tagRECT *)Points);
      OffsetRect((LPRECT)Points, v9, 0);
      x = v35.left;
      if ( v35.left < Points[0].x )
        x = Points[0].x;
      rcDst.left = x;
      v37 = rcDst.right;
      if ( rcDst.right > Points[1].x )
        v37 = Points[1].x;
      rcDst.right = v37;
      if ( !IntersectRect(&rcDst, &rcDst, p_rect) )
        goto LABEL_25;
      v39 = PrepBackgroundDIBSection(a2, &rcDst, (void **)&v62, &v57);
      if ( !v39 )
        v39 = a2;
      CLVBackgroundManager::DrawSimpleBackground(this, v39, v38, &rcDst);
      if ( *(_QWORD *)&v62.left )
        SaturateDC(*(void **)&v62.left, v40, &rcDst, &rcDst);
      if ( v39 != a2 )
      {
        BitBlt(
          a2,
          rcDst.left,
          rcDst.top,
          rcDst.right - rcDst.left,
          rcDst.bottom - rcDst.top,
          v39,
          rcDst.left,
          rcDst.top,
          0xCC0020u);
        CleanupBackgroundDIBSection(v39, v57);
      }
    }
    bottom = rcDst.bottom;
    right = rcDst.right;
    top = rcDst.top;
    left = rcDst.left;
LABEL_61:
    ExcludeClipRect(a2, left, top, right, bottom);
LABEL_25:
    if ( RectVisible(a2, p_rect) )
      CLVBackgroundManager::DrawSimpleBackground(this, a2, v17, p_rect);
    if ( v56 )
      CLVBackgroundManager::_DrawColumnEdges(this, a2, p_rect, &v55);
    SelectClipRgn(a2, v15);
    if ( v15 )
      DeleteObject(v15);
    return;
  }
  if ( *(_DWORD *)(v6 + 180) == -1 )
  {
    Points[0] = 0;
    pt = 0;
    MapWindowPoints(*(HWND *)(v6 + 96), *(HWND *)(v6 + 104), Points, v11);
    OffsetWindowOrgEx(a2, Points[0].x, Points[0].y, &pt);
    v13 = *((_QWORD *)this + 9);
    if ( (*(_DWORD *)(v13 + 176) & 0x400000) == 0 || !SendMessageW(*(HWND *)(v13 + 104), 0x318u, (WPARAM)a2, 8) )
      SendMessageW(*(HWND *)(*((_QWORD *)this + 9) + 104LL), 0x14u, (WPARAM)a2, 0);
    SetWindowOrgEx(a2, pt.x, pt.y, 0);
  }
  else
  {
    FillRect(a2, p_rect, *(HBRUSH *)(v6 + 208));
  }
  if ( *((_QWORD *)this + 7) )
  {
    CompatibleDC = CreateCompatibleDC(a2);
    v42 = CompatibleDC;
    if ( CompatibleDC )
    {
      v43 = SelectObject(CompatibleDC, *((HGDIOBJ *)this + 7));
      v44 = *((_QWORD *)this + 9);
      v45 = v43;
      rcDst = 0;
      GetClientRect(*(HWND *)(v44 + 96), &rcDst);
      v46 = *((_DWORD *)this + 16);
      v47 = rcDst.right - v46;
      hSrc = *((_DWORD *)this + 17);
      v49 = rcDst.bottom - hSrc;
      rcDst.left = rcDst.right - v46;
      rcDst.top = rcDst.bottom - hSrc;
      if ( *((_DWORD *)this + 1) )
      {
        v59 = (BLENDFUNCTION)33488896;
        GdiAlphaBlend(a2, v47, v49, v46, hSrc, v42, 0, 0, v46, hSrc, (BLENDFUNCTION)33488896);
      }
      else
      {
        BitBlt(a2, v47, v49, v46, hSrc, v42, 0, 0, 0xCC0020u);
      }
      SelectObject(v42, v45);
      DeleteDC(v42);
    }
  }
  if ( v12 )
  {
    v50 = *((_QWORD *)this + 9);
    rcDst = 0;
    CLVHeaderControlManager::GetItemRect(
      *(CLVHeaderControlManager **)(v50 + 392),
      *(_DWORD *)(*(_QWORD *)(v50 + 640) + 24LL),
      &rcDst);
    OffsetRect(&rcDst, v9, 0);
    v51 = (CListView *)*((_QWORD *)this + 9);
    v62 = *p_rect;
    v52 = _mm_cvtsi128_si32((__m128i)v62);
    if ( v52 < rcDst.left )
      v52 = rcDst.left;
    v62.left = v52;
    v53 = v62.right;
    if ( v62.right > rcDst.right )
      v53 = rcDst.right;
    v62.right = v53;
    SortColumnColor = CListView::GetSortColumnColor(v51);
    FillRectClr(a2, &v62, SortColumnColor);
  }
  if ( v56 )
    CLVBackgroundManager::_DrawColumnEdges(this, a2, p_rect, &v55);
}

```

## disassembly

```asm
0x18002d1a4  mov     [rsp-8+arg_18], rbx
0x18002d1a9  push    rbp
0x18002d1aa  push    rsi
0x18002d1ab  push    rdi
0x18002d1ac  push    r12
0x18002d1ae  push    r13
0x18002d1b0  push    r14
0x18002d1b2  push    r15
0x18002d1b4  lea     rbp, [rsp-27h]
0x18002d1b9  sub     rsp, 0E0h
0x18002d1c0  mov     rax, cs:__security_cookie
0x18002d1c7  xor     rax, rsp
0x18002d1ca  mov     [rbp+57h+var_38], rax
0x18002d1ce  xor     r13d, r13d
0x18002d1d1  xorps   xmm0, xmm0
0x18002d1d4  mov     qword ptr [rbp+57h+var_B0.x], r13
0x18002d1d8  mov     rsi, r8
0x18002d1db  mov     rbx, rdx
0x18002d1de  mov     rdi, rcx
0x18002d1e1  movups  xmmword ptr [rbp+57h+rect.left], xmm0
0x18002d1e5  test    r8, r8
0x18002d1e8  jz      loc_18002D466
0x18002d1ee  mov     r10, [rdi+48h]
0x18002d1f2  movzx   r8d, word ptr [r10+0A4h]
0x18002d1fa  mov     ecx, r8d
0x18002d1fd  sub     ecx, 1
0x18002d200  jz      loc_18002D415
0x18002d206  mov     rax, [r10+1C0h]
0x18002d20d  cmp     ecx, 2
0x18002d210  jz      loc_18002D338
0x18002d216  mov     r14d, [rax+8]
0x18002d21a  mov     r15d, [rax+0Ch]
0x18002d21e  neg     r14d
0x18002d221  neg     r15d
0x18002d224  mov     [rbp+57h+var_B0.y], r15d
0x18002d228  mov     edx, 1
0x18002d22d  mov     [rbp+57h+var_B0.x], r14d
0x18002d231  mov     r12d, r13d
0x18002d234  cmp     r8w, dx
0x18002d238  jz      loc_18002D43B
0x18002d23e  mov     [rbp+57h+var_A8], r13d
0x18002d242  cmp     [rdi+8], r13
0x18002d246  jnz     loc_18002D47C
0x18002d24c  test    dword ptr [r10+0B0h], 400000h
0x18002d257  jnz     loc_18002D34B
0x18002d25d  cmp     dword ptr [r10+0B4h], 0FFFFFFFFh
0x18002d265  jnz     loc_18002D3E6
0x18002d26b  mov     qword ptr [rbp+57h+Points.x], r13
0x18002d26f  lea     r8, [rbp+57h+Points]; lpPoints
0x18002d273  mov     qword ptr [rbp+57h+pt.x], r13
0x18002d277  mov     r9d, edx; cPoints
0x18002d27a  mov     rdx, [r10+68h]; hWndTo
0x18002d27e  mov     rcx, [r10+60h]; hWndFrom
0x18002d282  call    cs:__imp_MapWindowPoints
0x18002d288  mov     r8d, [rbp+57h+Points.y]; y
0x18002d28c  lea     r9, [rbp+57h+pt]; lppt
0x18002d290  mov     edx, [rbp+57h+Points.x]; x
0x18002d293  mov     rcx, rbx; hdc
0x18002d296  call    cs:__imp_OffsetWindowOrgEx
0x18002d29c  mov     rcx, [rdi+48h]
0x18002d2a0  test    dword ptr [rcx+0B0h], 400000h
0x18002d2aa  jz      short loc_18002D2C9
0x18002d2ac  mov     rcx, [rcx+68h]; hWnd
0x18002d2b0  mov     r9d, 8; lParam
0x18002d2b6  mov     r8, rbx; wParam
0x18002d2b9  mov     edx, 318h; Msg
0x18002d2be  call    cs:__imp_SendMessageW
0x18002d2c4  test    rax, rax
0x18002d2c7  jnz     short loc_18002D2E1
0x18002d2c9  mov     rcx, [rdi+48h]
0x18002d2cd  xor     r9d, r9d; lParam
0x18002d2d0  mov     r8, rbx; wParam
0x18002d2d3  mov     rcx, [rcx+68h]; hWnd
0x18002d2d7  lea     edx, [r9+14h]; Msg
0x18002d2db  call    cs:__imp_SendMessageW
0x18002d2e1  mov     r8d, [rbp+57h+pt.y]; y
0x18002d2e5  xor     r9d, r9d; lppt
0x18002d2e8  mov     edx, [rbp+57h+pt.x]; x
0x18002d2eb  mov     rcx, rbx; hdc
0x18002d2ee  call    cs:__imp_SetWindowOrgEx
0x18002d2f4  cmp     [rdi+38h], r13
0x18002d2f8  jnz     loc_18002D82E
0x18002d2fe  test    r12d, r12d
0x18002d301  jnz     loc_18002D906
0x18002d307  cmp     [rbp+57h+var_A8], r13d
0x18002d30b  jnz     loc_18002D3FE
0x18002d311  mov     rcx, [rbp+57h+var_38]
0x18002d315  xor     rcx, rsp; StackCookie
0x18002d318  call    __security_check_cookie
0x18002d31d  mov     rbx, [rsp+110h+arg_18]
0x18002d325  add     rsp, 0E0h
0x18002d32c  pop     r15
0x18002d32e  pop     r14
0x18002d330  pop     r13
0x18002d332  pop     r12
0x18002d334  pop     rdi
0x18002d335  pop     rsi
0x18002d336  pop     rbp
0x18002d337  retn
0x18002d338  mov     r14d, [rax+4]
0x18002d33c  mov     r15d, r13d
0x18002d33f  neg     r14d
0x18002d342  mov     [rbp+57h+var_B0.y], r13d
0x18002d346  jmp     loc_18002D228
0x18002d34b  test    r12d, r12d
0x18002d34e  jz      loc_18002D25D
0x18002d354  mov     rcx, rsi; lprect
0x18002d357  call    cs:__imp_CreateRectRgnIndirect
0x18002d35d  mov     r13, rax
0x18002d360  test    rax, rax
0x18002d363  jnz     loc_18002D48A
0x18002d369  mov     eax, [rsi+0Ch]
0x18002d36c  mov     rcx, rbx; hdc
0x18002d36f  mov     r9d, [rsi+8]; right
0x18002d373  mov     r8d, [rsi+4]; top
0x18002d377  mov     edx, [rsi]; left
0x18002d379  mov     [rsp+110h+bottom], eax; bottom
0x18002d37d  call    cs:__imp_IntersectClipRect
0x18002d383  cmp     qword ptr [rdi+8], 0
0x18002d388  jnz     loc_18002D4AF
0x18002d38e  mov     rcx, [rdi+48h]
0x18002d392  test    dword ptr [rcx+0B0h], 400000h
0x18002d39c  jnz     loc_18002D733
0x18002d3a2  xor     r12d, r12d
0x18002d3a5  mov     rdx, rsi; lprect
0x18002d3a8  mov     rcx, rbx; hdc
0x18002d3ab  call    cs:__imp_RectVisible
0x18002d3b1  test    eax, eax
0x18002d3b3  jnz     loc_18002D804
0x18002d3b9  cmp     [rbp+57h+var_A8], r12d
0x18002d3bd  jnz     loc_18002D817
0x18002d3c3  mov     rdx, r13; hrgn
0x18002d3c6  mov     rcx, rbx; hdc
0x18002d3c9  call    cs:__imp_SelectClipRgn
0x18002d3cf  test    r13, r13
0x18002d3d2  jz      loc_18002D311
0x18002d3d8  mov     rcx, r13; ho
0x18002d3db  call    cs:__imp_DeleteObject
0x18002d3e1  jmp     loc_18002D311
0x18002d3e6  mov     r8, [r10+0D0h]; hbr
0x18002d3ed  mov     rdx, rsi; lprc
0x18002d3f0  mov     rcx, rbx; hDC
0x18002d3f3  call    cs:__imp_FillRect
0x18002d3f9  jmp     loc_18002D2F4
0x18002d3fe  lea     r9, [rbp+57h+var_B0]; struct tagPOINT *
0x18002d402  mov     r8, rsi; struct tagRECT *
0x18002d405  mov     rdx, rbx; HDC
0x18002d408  mov     rcx, rdi; this
0x18002d40b  call    ?_DrawColumnEdges@CLVBackgroundManager@@IEAAXPEAUHDC__@@PEBUtagRECT@@PEBUtagPOINT@@@Z; CLVBackgroundManager::_DrawColumnEdges(HDC__ *,tagRECT const *,tagPOINT const *)
0x18002d410  jmp     loc_18002D311
0x18002d415  mov     rdx, [r10+280h]
0x18002d41c  mov     rax, [r10+260h]
0x18002d423  mov     r14d, [rdx+1Ch]
0x18002d427  mov     rcx, [rax+10h]
0x18002d42b  neg     r14d
0x18002d42e  mov     r15d, [rcx+14h]
0x18002d432  sub     r15d, [rdx+20h]
0x18002d436  jmp     loc_18002D224
0x18002d43b  mov     rax, [r10+280h]
0x18002d442  mov     rcx, [r10+1D8h]; this
0x18002d449  cmp     dword ptr [rax+18h], 0FFFFFFFFh
0x18002d44d  setnz   r12b
0x18002d451  call    ?HasCustomTheme@CLVThemesManager@@QEBA_NXZ; CLVThemesManager::HasCustomTheme(void)
0x18002d456  mov     [rbp+57h+var_A8], edx
0x18002d459  test    al, al
0x18002d45b  jnz     loc_18002D242
0x18002d461  jmp     loc_18002D23E
0x18002d466  lea     rdx, [rbp+57h+rect]; lprect
0x18002d46a  mov     rcx, rbx; hdc
0x18002d46d  call    cs:__imp_GetClipBox
0x18002d473  lea     rsi, [rbp+57h+rect]
0x18002d477  jmp     loc_18002D1EE
0x18002d47c  cmp     [rdi], r13d
0x18002d47f  jnz     loc_18002D354
0x18002d485  jmp     loc_18002D24C
0x18002d48a  mov     rdx, r13; hrgn
0x18002d48d  mov     rcx, rbx; hdc
0x18002d490  call    cs:__imp_GetClipRgn
0x18002d496  test    eax, eax
0x18002d498  jg      loc_18002D369
0x18002d49e  mov     rcx, r13; ho
0x18002d4a1  call    cs:__imp_DeleteObject
0x18002d4a7  xor     r13d, r13d
0x18002d4aa  jmp     loc_18002D369
0x18002d4af  cmp     dword ptr [rdi], 0
0x18002d4b2  jz      loc_18002D38E
0x18002d4b8  xor     r12d, r12d
0x18002d4bb  xorps   xmm0, xmm0
0x18002d4be  xorps   xmm1, xmm1
0x18002d4c1  mov     dword ptr [rbp+57h+var_88.BlendOp], r12d
0x18002d4c5  xor     r9d, r9d; int
0x18002d4c8  mov     qword ptr [rbp+57h+Points.x], r12
0x18002d4cc  mov     rdx, rbx; HDC
0x18002d4cf  mov     rcx, rdi; this
0x18002d4d2  lea     r8d, [r12+1]; int
0x18002d4d7  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x18002d4db  movups  xmmword ptr [rbp+57h+Rect.left], xmm1
0x18002d4df  call    ?Realize@CLVBackgroundManager@@QEAAXPEAUHDC__@@HH@Z; CLVBackgroundManager::Realize(HDC__ *,int,int)
0x18002d4e4  test    byte ptr [rdi+10h], 10h
0x18002d4e8  jz      loc_18002D5E7
0x18002d4ee  mov     rax, [rdi+48h]
0x18002d4f2  lea     ecx, [r12+1]
0x18002d4f7  mov     qword ptr [rbp+57h+var_68.left], r12
0x18002d4fb  mov     r14, rbx
0x18002d4fe  mov     qword ptr [rbp+57h+pt.x], r12
0x18002d502  mov     r15d, r12d
0x18002d505  mov     [rbp+57h+var_A0], r12
0x18002d509  cmp     [rax+0A4h], cx
0x18002d510  jnz     short loc_18002D540
0x18002d512  mov     rax, [rax+280h]
0x18002d519  cmp     dword ptr [rax+18h], 0FFFFFFFFh
0x18002d51d  jz      short loc_18002D540
0x18002d51f  lea     r9, [rbp+57h+var_A0]; HBITMAP *
0x18002d523  mov     rdx, rsi; struct tagRECT *
0x18002d526  lea     r8, [rbp+57h+var_68]; void **
0x18002d52a  mov     rcx, rbx; HDC
0x18002d52d  call    ?PrepBackgroundDIBSection@@YAPEAUHDC__@@PEAU1@PEBUtagRECT@@PEAPEAXPEAPEAUHBITMAP__@@@Z; PrepBackgroundDIBSection(HDC__ *,tagRECT const *,void * *,HBITMAP__ * *)
0x18002d532  mov     r15, [rbp+57h+var_A0]
0x18002d536  test    rax, rax
0x18002d539  mov     r14, rax
0x18002d53c  cmovz   r14, rbx
0x18002d540  test    dword ptr [rdi+10h], 100h
0x18002d547  jz      short loc_18002D555
0x18002d549  mov     eax, [rdi+28h]
0x18002d54c  sub     [rbp+57h+pt.x], eax
0x18002d54f  mov     eax, [rdi+2Ch]
0x18002d552  sub     [rbp+57h+pt.y], eax
0x18002d555  mov     rcx, [rdi+8]
0x18002d559  lea     r8, [rbp+57h+pt]
0x18002d55d  mov     r9, rsi
0x18002d560  mov     qword ptr [rsp+110h+bottom], r12
0x18002d565  mov     rdx, r14
0x18002d568  mov     rax, [rcx]
0x18002d56b  mov     rax, [rax+58h]
0x18002d56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d574  cmp     r14, rbx
0x18002d577  jz      short loc_18002D5D5
0x18002d579  mov     r8, qword ptr [rbp+57h+var_68.left]; void *
0x18002d57d  test    r8, r8
0x18002d580  jz      short loc_18002D594
0x18002d582  mov     rcx, [rdi+48h]; struct CListView *
0x18002d586  lea     r9, [rbp+57h+var_B0]; struct tagPOINT *
0x18002d58a  mov     qword ptr [rsp+110h+bottom], rsi; struct tagRECT *
0x18002d58f  call    ?SaturateSortColumn@@YAXPEAVCListView@@PEAUHDC__@@PEAXPEBUtagPOINT@@PEBUtagRECT@@@Z; SaturateSortColumn(CListView *,HDC__ *,void *,tagPOINT const *,tagRECT const *)
0x18002d594  mov     r8d, [rsi+4]; y
0x18002d598  mov     rcx, rbx; hdc
0x18002d59b  mov     edx, [rsi]; x
0x18002d59d  mov     eax, [rsi+0Ch]
0x18002d5a0  mov     r9d, [rsi+8]
0x18002d5a4  sub     eax, r8d
0x18002d5a7  mov     [rsp+110h+rop], 0CC0020h; rop
0x18002d5af  sub     r9d, edx; cx
0x18002d5b2  mov     [rsp+110h+y1], r8d; y1
0x18002d5b7  mov     [rsp+110h+x1], edx; x1
0x18002d5bb  mov     [rsp+110h+hdcSrc], r14; hdcSrc
0x18002d5c0  mov     [rsp+110h+bottom], eax; cy
0x18002d5c4  call    cs:__imp_BitBlt
0x18002d5ca  mov     rdx, r15; HBITMAP
0x18002d5cd  mov     rcx, r14; hdc
0x18002d5d0  call    ?CleanupBackgroundDIBSection@@YAXPEAUHDC__@@PEAUHBITMAP__@@@Z; CleanupBackgroundDIBSection(HDC__ *,HBITMAP__ *)
0x18002d5d5  mov     eax, [rsi+0Ch]
0x18002d5d8  mov     r9d, [rsi+8]
0x18002d5dc  mov     r8d, [rsi+4]
0x18002d5e0  mov     edx, [rsi]
0x18002d5e2  jmp     loc_18002D721
0x18002d5e7  mov     rcx, [rdi+8]
0x18002d5eb  lea     r8, [rbp+57h+Points]
0x18002d5ef  xor     r9d, r9d
0x18002d5f2  lea     rdx, [rbp+57h+var_88]
0x18002d5f6  mov     rax, [rcx]
0x18002d5f9  mov     rax, [rax+40h]
0x18002d5fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d602  mov     eax, [rbp+57h+Points.x]
0x18002d605  lea     rdx, [rbp+57h+Rect]; lpRect
0x18002d609  mov     rcx, [rdi+48h]
0x18002d60d  mov     [rbp+57h+rcDst.right], eax
0x18002d610  mov     eax, [rbp+57h+Points.y]
0x18002d613  mov     qword ptr [rbp+57h+rcDst.left], r12
0x18002d617  mov     [rbp+57h+rcDst.bottom], eax
0x18002d61a  mov     rcx, [rcx+60h]; hWnd
0x18002d61e  call    cs:__imp_GetClientRect
0x18002d624  mov     r10d, 51EB851Fh
0x18002d62a  mov     r8d, [rbp+57h+rcDst.left]
0x18002d62e  mov     r9d, [rbp+57h+rcDst.right]
0x18002d632  cmp     [rdi+28h], r12d
0x18002d636  jz      short loc_18002D657
0x18002d638  mov     ecx, [rbp+57h+Rect.right]
0x18002d63b  mov     eax, r10d
0x18002d63e  sub     ecx, [rbp+57h+Points.x]
0x18002d641  imul    ecx, [rdi+28h]
0x18002d645  imul    ecx
0x18002d647  sar     edx, 5
0x18002d64a  mov     eax, edx
0x18002d64c  shr     eax, 1Fh
0x18002d64f  add     edx, eax
0x18002d651  add     r8d, edx
0x18002d654  add     r9d, edx
0x18002d657  cmp     [rdi+2Ch], r12d
0x18002d65b  jz      short loc_18002D682
0x18002d65d  mov     ecx, [rbp+57h+Rect.bottom]
  ... truncated ...
```
