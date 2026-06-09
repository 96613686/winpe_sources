# CLVSelectionManager::DragSelect(int,int)

- ea: `0x18002b17c`
- end: `0x18002bec6`
- name: `?DragSelect@CLVSelectionManager@@QEAAXHH@Z`
- size: `3402`
- prototype: `void __fastcall(CLVSelectionManager *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `25`
- tags: `installer_update`

## callers

- `0x18003ed74`

## callees

- `0x18002b17c`
- `0x18002becc`
- `0x18002d980`
- `0x1800303a0`
- `0x180031a40`
- `0x180032a54`
- `0x1800394fc`
- `0x18003d5fc`
- `0x18003fe20`
- `0x1800925bc`
- `0x1800925dc`
- `0x1800932c4`
- `0x180093648`
- `0x1800b6988`
- `0x1800e472c`
- `0x1800ea75c`
- `0x180105bb4`
- `0x180105fec`
- `0x18010f7e0`
- `0x180114520`
- `0x18014b38c`
- `0x18014d1bc`
- `0x1801ca8b4`
- `0x1801ca950`
- `0x1801caa58`

## import_xrefs

- `USER32!CallMsgFilterW` at `0x18002b59e`
- `USER32!CallMsgFilterW` at `0x18002b59e`
- `USER32!OffsetRect` at `0x18002b6bb`
- `USER32!OffsetRect` at `0x18002b6bb`
- `USER32!DrawFocusRect` at `0x18002b972`
- `USER32!DrawFocusRect` at `0x18002b984`
- `USER32!DrawFocusRect` at `0x18002ba06`
- `USER32!DrawFocusRect` at `0x18002ba18`
- `USER32!DrawFocusRect` at `0x18002b972`
- `USER32!DrawFocusRect` at `0x18002b984`
- `USER32!DrawFocusRect` at `0x18002ba06`
- `USER32!DrawFocusRect` at `0x18002ba18`
- `USER32!IntersectRect` at `0x18002b454`
- `USER32!IntersectRect` at `0x18002b472`
- `USER32!IntersectRect` at `0x18002baaf`
- `USER32!IntersectRect` at `0x18002baca`
- `USER32!IntersectRect` at `0x18002b454`
- `USER32!IntersectRect` at `0x18002b472`
- `USER32!IntersectRect` at `0x18002baaf`
- `USER32!IntersectRect` at `0x18002baca`
- `USER32!WaitMessage` at `0x18002b786`
- `USER32!WaitMessage` at `0x18002b786`
- `USER32!DispatchMessageW` at `0x18002b8f5`
- `USER32!DispatchMessageW` at `0x18002b8f5`
- `USER32!TranslateMessage` at `0x18002b8eb`
- `USER32!TranslateMessage` at `0x18002b8eb`
- `USER32!PeekMessageW` at `0x18002b587`
- `USER32!PeekMessageW` at `0x18002b587`
- `USER32!SetCursorPos` at `0x18002bbc5`
- `USER32!SetCursorPos` at `0x18002bbc5`
- `USER32!UnionRect` at `0x18002b4f7`
- `USER32!UnionRect` at `0x18002b6cd`
- `USER32!UnionRect` at `0x18002b4f7`
- `USER32!UnionRect` at `0x18002b6cd`
- `USER32!GetCapture` at `0x18002b564`
- `USER32!GetCapture` at `0x18002b564`
- `USER32!SetCapture` at `0x18002b25e`
- `USER32!SetCapture` at `0x18002b25e`
- `USER32!GetCursorPos` at `0x18002b74a`
- `USER32!GetCursorPos` at `0x18002b74a`
- `USER32!GetWindowRect` at `0x18002b2ad`
- `USER32!GetWindowRect` at `0x18002b2ad`
- `USER32!InflateRect` at `0x18002b442`
- `USER32!InflateRect` at `0x18002b506`
- `USER32!InflateRect` at `0x18002b9ae`
- `USER32!InflateRect` at `0x18002b442`
- `USER32!InflateRect` at `0x18002b506`
- `USER32!InflateRect` at `0x18002b9ae`
- `USER32!GetDC` at `0x18002b24e`
- `USER32!GetDC` at `0x18002b24e`
- `USER32!ScreenToClient` at `0x18002b611`
- `USER32!ScreenToClient` at `0x18002bca0`
- `USER32!ScreenToClient` at `0x18002b611`
- `USER32!ScreenToClient` at `0x18002bca0`
- `USER32!GetSystemMetrics` at `0x18002b2b8`
- `USER32!GetSystemMetrics` at `0x18002b2c8`
- `USER32!GetSystemMetrics` at `0x18002b2b8`
- `USER32!GetSystemMetrics` at `0x18002b2c8`
- `USER32!GetClientRect` at `0x18002b2a0`
- `USER32!GetClientRect` at `0x18002b2a0`
- `USER32!PtInRect` at `0x18002b758`
- `USER32!PtInRect` at `0x18002b758`
- `USER32!UpdateWindow` at `0x18002b245`
- `USER32!UpdateWindow` at `0x18002b53e`
- `USER32!UpdateWindow` at `0x18002b245`
- `USER32!UpdateWindow` at `0x18002b53e`
- `USER32!InvalidateRect` at `0x18002b293`
- `USER32!InvalidateRect` at `0x18002b530`
- `USER32!InvalidateRect` at `0x18002b9c3`
- `USER32!InvalidateRect` at `0x18002b293`
- `USER32!InvalidateRect` at `0x18002b530`
- `USER32!InvalidateRect` at `0x18002b9c3`
- `USER32!ReleaseDC` at `0x18002b9cf`
- `USER32!ReleaseDC` at `0x18002b9cf`
- `USER32!EqualRect` at `0x18002b687`
- `USER32!EqualRect` at `0x18002b687`

## pseudocode

```c
void __fastcall CLVSelectionManager::DragSelect(CLVSelectionManager *this, LONG a2, LONG a3)
{
  CListView *v4; // rcx
  int v7; // r13d
  int v8; // r15d
  HWND v9; // r14
  unsigned int v10; // edx
  CListView *v11; // rcx
  __int64 v12; // rcx
  HDC v13; // r12
  __int64 v14; // rcx
  int v15; // edi
  int v16; // esi
  _DWORD *v17; // rcx
  int v18; // r9d
  int v19; // r8d
  __int64 v20; // r9
  int v21; // r14d
  int iItem; // edi
  bool v23; // zf
  int v24; // r15d
  struct CLVDrawState *DrawStateForItem; // rax
  __int64 v26; // rcx
  struct CLVDrawState *v27; // r12
  __int64 v28; // rcx
  __int16 v29; // r8
  int v30; // ecx
  BOOL v31; // r13d
  int v32; // r12d
  LONG v33; // eax
  char wParam; // dl
  int v35; // ecx
  int v36; // esi
  int v37; // r15d
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  int v41; // edi
  int v42; // esi
  LONG v43; // edx
  LONG x; // ecx
  LONG v45; // r8d
  LONG y; // eax
  LONG v47; // ecx
  LONG v48; // eax
  __int64 v49; // r10
  int v50; // r12d
  __int16 v51; // cx
  int v52; // edi
  __int64 v53; // rax
  CListGroup *v54; // r13
  int v55; // edx
  __int64 v56; // rax
  CListGroup *v57; // rdi
  int v58; // r14d
  BOOL v59; // eax
  char v60; // cl
  BOOL v61; // r12d
  int v62; // eax
  __int64 v63; // rcx
  CLVGroupManager *v64; // rcx
  __int64 v65; // rcx
  int v66; // r8d
  _DWORD *v67; // r15
  int v68; // r14d
  int ListviewItemIndex; // eax
  struct CLVDrawState *v70; // rdx
  int v71; // [rsp+50h] [rbp-B0h] BYREF
  int v72; // [rsp+54h] [rbp-ACh]
  int v73; // [rsp+58h] [rbp-A8h] BYREF
  int v74; // [rsp+5Ch] [rbp-A4h] BYREF
  LONG v75; // [rsp+60h] [rbp-A0h]
  int v76; // [rsp+64h] [rbp-9Ch] BYREF
  int v77; // [rsp+68h] [rbp-98h]
  struct tagLVITEMINDEX v78; // [rsp+70h] [rbp-90h] BYREF
  int v79; // [rsp+78h] [rbp-88h] BYREF
  int v80; // [rsp+7Ch] [rbp-84h] BYREF
  int v81; // [rsp+80h] [rbp-80h] BYREF
  int v82; // [rsp+84h] [rbp-7Ch]
  LONG v83; // [rsp+88h] [rbp-78h]
  LONG v84; // [rsp+8Ch] [rbp-74h]
  int v85; // [rsp+90h] [rbp-70h]
  int SystemMetrics; // [rsp+94h] [rbp-6Ch]
  int v87; // [rsp+98h] [rbp-68h]
  struct tagLVITEMINDEX v88; // [rsp+A0h] [rbp-60h]
  struct tagLVITEMINDEX v89; // [rsp+A8h] [rbp-58h]
  HDC hDC; // [rsp+B0h] [rbp-50h]
  HWND v91; // [rsp+B8h] [rbp-48h]
  struct tagPOINT Point; // [rsp+C0h] [rbp-40h] BYREF
  POINT pt; // [rsp+C8h] [rbp-38h] BYREF
  RECT rcSrc2; // [rsp+D0h] [rbp-30h] BYREF
  struct tagRECT rc; // [rsp+E0h] [rbp-20h] BYREF
  RECT rcSrc1; // [rsp+F0h] [rbp-10h] BYREF
  struct tagRECT Rect; // [rsp+100h] [rbp+0h] BYREF
  struct tagRECT v98; // [rsp+110h] [rbp+10h] BYREF
  RECT v99; // [rsp+120h] [rbp+20h] BYREF
  struct tagRECT rcDst; // [rsp+130h] [rbp+30h] BYREF
  struct tagMSG Msg; // [rsp+140h] [rbp+40h] BYREF
  RECT v102; // [rsp+170h] [rbp+70h] BYREF

  v83 = a3;
  Point = 0;
  v84 = a2;
  rcSrc2 = 0;
  v4 = (CListView *)*((_QWORD *)this + 6);
  v102 = 0;
  rcSrc1 = 0;
  v71 = 0;
  v7 = 0;
  v98 = 0;
  v78.iItem = 0;
  v8 = 0;
  v99 = 0;
  v73 = 0;
  Rect = 0;
  v74 = 0;
  memset(&Msg, 0, sizeof(Msg));
  v72 = 0;
  v85 = 0;
  v9 = (HWND)*((_QWORD *)v4 + 12);
  v91 = v9;
  if ( CListView::IsDoubleBuffer(v4) && (unsigned int)CListView::AreAllMonitorsAtLeast(v11, v10) )
  {
    v8 = *(_DWORD *)this;
    v85 = *(_DWORD *)this;
  }
  v12 = *((_QWORD *)this + 6);
  rcSrc2.right = a2;
  rcSrc2.left = a2;
  rcSrc2.bottom = a3;
  rcSrc2.top = a3;
  rcSrc1 = rcSrc2;
  UpdateWindow(*(HWND *)(v12 + 96));
  hDC = GetDC(v9);
  v13 = hDC;
  SetCapture(v9);
  if ( v8 )
  {
    *(_DWORD *)(*((_QWORD *)this + 6) + 168LL) |= 0x40000u;
    v14 = *((_QWORD *)this + 6);
    *((RECT *)this + 2) = rcSrc2;
    InvalidateRect(*(HWND *)(v14 + 96), (const RECT *)this + 2, 1);
  }
  else
  {
    DrawFocusRect(hDC, &rcSrc2);
  }
  GetClientRect(v9, &Rect);
  GetWindowRect(v9, &v102);
  SystemMetrics = GetSystemMetrics(78);
  v15 = SystemMetrics;
  v16 = GetSystemMetrics(79);
  v87 = v16;
  while ( GetCapture() == v9 )
  {
    if ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
    {
      if ( !CallMsgFilterW(&Msg, 16898) )
      {
        if ( Msg.message > 0x201 )
        {
          if ( Msg.message == 514 || Msg.message == 516 || Msg.message == 517 || Msg.message - 519 < 2 )
          {
LABEL_159:
            CCReleaseCapture(*((_QWORD *)this + 6) + 96LL);
            break;
          }
          if ( ((Msg.message - 522) & 0xFFFFFFFB) != 0 )
            goto LABEL_89;
        }
        else
        {
          if ( Msg.message == 513 )
            goto LABEL_159;
          if ( Msg.message == 256 )
          {
            if ( Msg.wParam == 27 )
            {
              CLVSelectionManager::DeselectAll(this, -1, -1);
              break;
            }
          }
          else if ( Msg.message != 257 && Msg.message != 258 )
          {
            if ( Msg.message == 275 )
            {
              if ( Msg.wParam != 44 )
                goto LABEL_89;
LABEL_41:
              v40 = *((_QWORD *)this + 6);
              v75 = -1;
              pt.x = -1;
              Point = Msg.pt;
              if ( (*(_DWORD *)(v40 + 112) & 0x300000) != 0 )
              {
                CLVScrollingManager::GetBaseScrollDeltas(*(CLVScrollingManager **)(v40 + 448), &v73, &v74);
                if ( Msg.pt.y >= v16 - 1 )
                  Point.y = v74 + Msg.pt.y;
                if ( Point.x >= v15 - 1 )
                  Point.x += v73;
                ScreenToClient(v9, &Point);
                CLVScrollingManager::ScrollDetect(
                  *(CLVScrollingManager **)(*((_QWORD *)this + 6) + 448LL),
                  Point,
                  &v73,
                  &v74);
                v42 = v73;
                v41 = v74;
              }
              else
              {
                ScreenToClient(v9, &Point);
                v41 = 0;
                v42 = 0;
                v74 = 0;
                v73 = 0;
              }
              v43 = v83 - v41;
              x = Point.x;
              v45 = v84 - v42;
              y = Point.y;
              if ( Point.x > Rect.right )
                x = Rect.right;
              v83 -= v41;
              if ( x < Rect.left )
                x = Rect.left;
              v84 -= v42;
              if ( Point.y > Rect.bottom )
                y = Rect.bottom;
              rcSrc2.left = v45;
              if ( y < Rect.top )
                y = Rect.top;
              v47 = v42 + x;
              v48 = v41 + y;
              rcSrc2.top = v43;
              rcSrc2.bottom = v48;
              rcSrc2.right = v47;
              if ( v45 > v47 )
              {
                rcSrc2.left = v47;
                rcSrc2.right = v45;
              }
              if ( v48 < v43 )
              {
                rcSrc2.bottom = v43;
                rcSrc2.top = v48;
              }
              if ( !EqualRect(&rcSrc2, &rcSrc1) )
              {
                if ( !v8 )
                  DrawFocusRect(v13, &rcSrc1);
                if ( v42 || v41 )
                  CLVScrollingManager::OnScrollSelectSmooth(
                    *(CLVScrollingManager **)(*((_QWORD *)this + 6) + 448LL),
                    v42,
                    v41,
                    0);
                OffsetRect(&rcSrc1, -v42, -v41);
                UnionRect(&v98, &rcSrc2, &rcSrc1);
                v49 = *((_QWORD *)this + 6);
                v36 = -1;
                v82 = -1;
                v79 = -1;
                v37 = -1;
                v81 = -1;
                v50 = -1;
                v51 = *(_WORD *)(v49 + 164);
                v77 = -1;
                v80 = -1;
                v76 = -1;
                if ( v51 == 1 )
                {
                  if ( (*(_DWORD *)(v49 + 160) & 2) != 0 )
                    goto LABEL_72;
                  v65 = *(_QWORD *)(*(_QWORD *)(v49 + 608) + 16LL);
                  v66 = *(_DWORD *)(*(_QWORD *)(v49 + 640) + 32LL) - *(_DWORD *)(v65 + 20);
                  iItem = (v66 + v98.top) / *(_DWORD *)(v65 + 64);
                  v21 = (v66 + v98.bottom) / *(_DWORD *)(v65 + 64);
                }
                else
                {
                  if ( v51 == 3 )
                  {
                    v17 = *(_DWORD **)(*(_QWORD *)(v49 + 608) + 16LL);
                    v18 = *(_DWORD *)(*(_QWORD *)(v49 + 616) + 24LL);
                    v19 = *(_DWORD *)(*(_QWORD *)(v49 + 448) + 4LL) - v17[7];
                    iItem = (v98.top - v17[8]) / v17[16] + v18 * ((v19 + v98.left) / v17[15]);
                    v21 = (v98.bottom - v17[8]) / v17[16] + v18 * ((v19 + v98.right) / v17[15]);
                    goto LABEL_5;
                  }
LABEL_72:
                  if ( (*(_DWORD *)(v49 + 112) & 0x1000) == 0 )
                  {
                    iItem = 0;
                    v21 = **(_DWORD **)(v49 + 512) - 1;
                    goto LABEL_5;
                  }
                  if ( (*(_DWORD *)(v49 + 160) & 2) == 0 )
                  {
                    CLVSlotsManager::CalcMinMaxIndex(*(CLVSlotsManager **)(v49 + 464), &v98, &v71, (int *)&v78);
                    iItem = v71;
                    goto LABEL_92;
                  }
                  v21 = 0;
                  iItem = 0;
                  v62 = CLVGroupManager::HitTestRect(*(CLVGroupManager **)(v49 + 336), 1, &v98, &v79, &v81, &v80, &v76);
                  v36 = v79;
                  v82 = v79;
                  if ( v62 )
                  {
                    v63 = *((_QWORD *)this + 6);
                    v78 = 0;
                    CLVGroupManager::GetItemIndexFromGroupItem(*(CLVGroupManager **)(v63 + 336), v79, v81, &v78);
                    v37 = v80;
                    iItem = v78.iItem;
                    v50 = v76;
                    v64 = *(CLVGroupManager **)(*((_QWORD *)this + 6) + 336LL);
                    v78 = 0;
                    v77 = v80;
                    CLVGroupManager::GetItemIndexFromGroupItem(v64, v80, v76, &v78);
LABEL_92:
                    v21 = v78.iItem;
                  }
                  else
                  {
                    v37 = v80;
                    v50 = v76;
                    v77 = v80;
                  }
                }
LABEL_5:
                v20 = *((_QWORD *)this + 6);
                if ( v21 > **(_DWORD **)(v20 + 512) - 1 )
                  v21 = **(_DWORD **)(v20 + 512) - 1;
                v78.iItem = v21;
                if ( iItem < 0 )
                  iItem = 0;
                v23 = (*(_DWORD *)(v20 + 112) & 0x1000) == 0;
                v71 = iItem;
                if ( !v23 && iItem <= v21 )
                {
                  v89 = (struct tagLVITEMINDEX)__PAIR64__(v36, iItem);
                  v88 = (struct tagLVITEMINDEX)__PAIR64__(v37, v21);
                  CListView::NotifyCacheHint(
                    (CListView *)v20,
                    (struct tagLVITEMINDEX)__PAIR64__(v36, iItem),
                    (struct tagLVITEMINDEX)__PAIR64__(v37, v21));
                  v20 = *((_QWORD *)this + 6);
                }
                if ( v7 && (Msg.wParam & 0xC) == 0 )
                  *((_DWORD *)this + 1) = -1;
                if ( (*(_DWORD *)(v20 + 112) & 0x1000) != 0
                  && (*(_DWORD *)(v20 + 160) & 2) != 0
                  && *(_WORD *)(v20 + 164) != 3 )
                {
                  if ( v36 != -1 && v37 != -1 )
                  {
                    v52 = v36;
                    if ( v36 <= v37 )
                    {
                      do
                      {
                        v53 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 336LL) + 72LL) + 8LL);
                        v54 = *(CListGroup **)(v53 + 8LL * v52);
                        if ( (*((_BYTE *)v54 + 96) & 1) == 0 )
                        {
                          v68 = 0;
                          if ( v52 == v36 )
                            v68 = v81;
                          if ( v52 != v37 )
                            v50 = CListGroup::GetSubsetItemCount(*(CListGroup **)(v53 + 8LL * v52)) - 1;
                          if ( v68 <= v50 )
                          {
                            do
                            {
                              ListviewItemIndex = CListGroup::GetListviewItemIndex(v54, v52, v68);
                              v70 = (struct CLVDrawState *)(*((_QWORD *)this + 6) + 240LL);
                              v71 = ListviewItemIndex;
                              CLVSelectionManager::_DragSelectItem(
                                this,
                                v70,
                                ListviewItemIndex,
                                v52,
                                &Msg,
                                &Point,
                                (int *)&pt,
                                &rcSrc1,
                                &rcSrc2);
                              ++v68;
                            }
                            while ( v68 <= v50 );
                            v37 = v77;
                          }
                        }
                        v50 = v76;
                        ++v52;
                      }
                      while ( v52 <= v37 );
                      v75 = pt.x;
                      goto LABEL_23;
                    }
                  }
                }
                else if ( iItem <= v21 )
                {
                  v24 = v75;
                  do
                  {
                    DrawStateForItem = CLVItemStore::GetDrawStateForItem(
                                         *(CLVItemStore **)(*((_QWORD *)this + 6) + 512LL),
                                         iItem);
                    v26 = *((_QWORD *)this + 6);
                    v27 = DrawStateForItem;
                    rcDst = 0;
                    rc = 0;
                    CLVView::GetRects(*(CLVView **)(v26 + 608), DrawStateForItem, iItem, -1, 0, 0, 0, 0, &rc);
                    v28 = *((_QWORD *)this + 6);
                    v29 = *(_WORD *)(v28 + 164);
                    if ( v29 != 1
                      || (*(_BYTE *)(v28 + 176) & 0x20) == 0 && !CListView::IsExtendedTileView((CListView *)v28) )
                    {
                      v30 = (rc.right - rc.left) / 4;
                      if ( v29 == 3 && v30 >= *((_DWORD *)v27 + 2) )
                        v30 = *((_DWORD *)v27 + 2);
                      InflateRect(&rc, -v30, (rc.bottom - rc.top) / -4);
                    }
                    v31 = IntersectRect(&rcDst, &rcSrc1, &rc);
                    v32 = v31;
                    v33 = IntersectRect(&rcDst, &rcSrc2, &rc);
                    wParam = Msg.wParam;
                    pt.x = v33;
                    v35 = v33 != 0;
                    if ( (Msg.wParam & 8) != 0 )
                    {
                      if ( v32 != v35 )
                        CLVSelectionManager::ToggleSelection(this, iItem, -1);
                    }
                    else
                    {
                      if ( v32 != v35 )
                      {
                        CLVItemStore::OnSetItemState(
                          *(CLVItemStore **)(*((_QWORD *)this + 6) + 512LL),
                          iItem,
                          -1,
                          !v31 ? 2 : 0,
                          2u);
                        wParam = Msg.wParam;
                        v33 = pt.x;
                      }
                      if ( v33
                        && (wParam & 0xC) == 0
                        && (rc.top - Point.y) * (rc.top - Point.y) + (rc.left - Point.x) * (rc.left - Point.x) > v24 )
                      {
                        v24 = (rc.top - Point.y) * (rc.top - Point.y) + (rc.left - Point.x) * (rc.left - Point.x);
                        *((_DWORD *)this + 1) = iItem;
                        *((_DWORD *)this + 2) = -1;
                      }
                    }
                    ++iItem;
                  }
                  while ( iItem <= v21 );
                  v36 = v82;
                  v75 = v24;
                  v37 = v77;
                  v71 = iItem;
LABEL_23:
                  v7 = v72;
                }
                v38 = *((_QWORD *)this + 6);
                if ( (*(_DWORD *)(v38 + 160) & 2) != 0 && *(_WORD *)(v38 + 164) != 3 )
                {
                  if ( v36 == -1 )
                    v36 = 0;
                  if ( v37 == -1 )
                  {
                    v67 = *(_DWORD **)(*(_QWORD *)(v38 + 336) + 72LL);
                    if ( v67 )
                      LODWORD(v67) = *v67;
                    v37 = (_DWORD)v67 - 1;
                  }
                  v71 = v36;
                  if ( v36 <= v37 )
                  {
                    v55 = v36;
                    do
                    {
                      v56 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 336LL) + 72LL) + 8LL);
                      v57 = *(CListGroup **)(v56 + 8LL * v55);
                      if ( v57
                        && (*((_BYTE *)v57 + 96) & 1) != 0
                        && (unsigned int)CListGroup::Visible(*(CListGroup **)(v56 + 8LL * v55)) )
                      {
                        rcDst = 0;
                        CListGroup::GetHeaderRect(v57, &v99);
                        v58 = IntersectRect(&rcDst, &rcSrc1, &v99);
                        v59 = IntersectRect(&rcDst, &rcSrc2, &v99);
                        v60 = Msg.wParam;
                        v61 = v59;
                        v7 = v59;
                        if ( (Msg.wParam & 8) != 0 )
                        {
                          if ( v58 != v7 )
                            CListGroup::Select(v57, v36, 1, *((_DWORD *)v57 + 24) & 0x20, 0);
                        }
                        else
                        {
                          if ( v58 != v7 )
                          {
                            CListGroup::Select(v57, v36, 1, v58, 0);
                            v60 = Msg.wParam;
                          }
                          if ( v61
                            && (v60 & 0xC) == 0
                            && (v99.top - Point.y) * (v99.top - Point.y) + (v99.left - Point.x) * (v99.left - Point.x) > v75 )
                          {
                            v75 = (v99.top - Point.y) * (v99.top - Point.y)
                                + (v99.left - Point.x) * (v99.left - Point.x);
                            *((_DWORD *)this + 1) = CListGroup::GetListviewItemIndex(v57, v36, 0);
                            *((_DWORD *)this + 2) = v36;
                          }
                        }
                      }
                      v55 = ++v36;
                    }
                    while ( v36 <= v37 );
                    v71 = v36;
                    v72 = v7;
                  }
                }
                v8 = v85;
                if ( v85 )
                {
                  rc = 0;
                  UnionRect(&rc, &rcSrc1, &rcSrc2);
                  InflateRect(&rc, 1, 1);
                  *(_DWORD *)(*((_QWORD *)this + 6) + 168LL) |= 0x40000u;
                  v39 = *((_QWORD *)this + 6);
                  *((RECT *)this + 2) = rcSrc2;
                  InvalidateRect(*(HWND *)(v39 + 96), &rc, 1);
                }
                UpdateWindow(*(HWND *)(*((_QWORD *)this + 6) + 96LL));
                v13 = hDC;
                if ( !v8 )
                  DrawFocusRect(hDC, &rcSrc2);
                v9 = v91;
                rcSrc1 = rcSrc2;
              }
              v16 = v87;
              v15 = SystemMetrics;
            }
            else
            {
              if ( Msg.message == 512 )
                goto LABEL_41;
LABEL_89:
              TranslateMessage(&Msg);
              DispatchMessageW(&Msg);
            }
          }
        }
      }
    }
    else
    {
      pt = 0;
      GetCursorPos(&pt);
      if ( (!PtInRect(&v102, pt) || pt.x <= 0 || pt.y <= 0 || pt.x >= v15 - 1 || pt.y >= v16 - 1)
        && (unsigned int)CLVScrollingManager::ShouldScroll(
                           *(CLVScrollingManager **)(*((_QWORD *)this + 6) + 448LL),
                           &pt,
                           &v102) )
      {
        SetCursorPos(pt.x, pt.y);
      }
      else
      {
        WaitMessage();
      }
    }
  }
  *(_DWORD *)(*((_QWORD *)this + 6) + 168LL) &= ~0x40000u;
  if ( v8 )
  {
    InflateRect(&rcSrc1, 1, 1);
    InvalidateRect(*(HWND *)(*((_QWORD *)this + 6) + 96LL), &rcSrc1, 1);
  }
  else
  {
    DrawFocusRect(v13, &rcSrc1);
  }
  ReleaseDC(v9, v13);
}

```

## disassembly

```asm
0x18002b17c  mov     [rsp-8+arg_18], rbx
0x18002b181  push    rbp
0x18002b182  push    rsi
0x18002b183  push    rdi
0x18002b184  push    r12
0x18002b186  push    r13
0x18002b188  push    r14
0x18002b18a  push    r15
0x18002b18c  lea     rbp, [rsp-90h]
0x18002b194  sub     rsp, 190h
0x18002b19b  mov     rax, cs:__security_cookie
0x18002b1a2  xor     rax, rsp
0x18002b1a5  mov     [rbp+0C0h+var_40], rax
0x18002b1ac  xor     r12d, r12d
0x18002b1af  mov     [rbp+0C0h+var_138], r8d
0x18002b1b3  xorps   xmm0, xmm0
0x18002b1b6  mov     qword ptr [rbp+0C0h+Point.x], r12
0x18002b1ba  xorps   xmm1, xmm1
0x18002b1bd  mov     [rbp+0C0h+var_134], edx
0x18002b1c0  movups  xmmword ptr [rbp+0C0h+rcSrc2.left], xmm0
0x18002b1c4  mov     rbx, rcx
0x18002b1c7  mov     rcx, [rcx+30h]; this
0x18002b1cb  movups  xmmword ptr [rbp+0C0h+var_50.left], xmm1
0x18002b1cf  mov     edi, r8d
0x18002b1d2  mov     esi, edx
0x18002b1d4  movups  xmmword ptr [rbp+0C0h+rcSrc1.left], xmm0
0x18002b1d8  mov     [rsp+1C0h+var_170], r12d
0x18002b1dd  mov     r13d, r12d
0x18002b1e0  movups  xmmword ptr [rbp+0C0h+var_B0.left], xmm1
0x18002b1e4  mov     [rsp+1C0h+var_150.iItem], r12d
0x18002b1e9  mov     r15d, r12d
0x18002b1ec  movups  xmmword ptr [rbp+0C0h+var_A0.left], xmm0
0x18002b1f0  mov     [rsp+1C0h+var_168], r12d
0x18002b1f5  movups  xmmword ptr [rbp+0C0h+Rect.left], xmm1
0x18002b1f9  mov     [rsp+1C0h+var_164], r12d
0x18002b1fe  movups  xmmword ptr [rbp+0C0h+Msg.hwnd], xmm0
0x18002b202  mov     [rsp+1C0h+var_16C], r12d
0x18002b207  movups  xmmword ptr [rbp+0C0h+Msg.wParam], xmm0
0x18002b20b  mov     [rbp+0C0h+var_130], r12d
0x18002b20f  movups  xmmword ptr [rbp+0C0h+Msg.time], xmm0
0x18002b213  mov     r14, [rcx+60h]
0x18002b217  mov     [rbp+0C0h+var_108], r14
0x18002b21b  call    ?IsDoubleBuffer@CListView@@QEBA_NXZ; CListView::IsDoubleBuffer(void)
0x18002b220  test    al, al
0x18002b222  jnz     loc_18002BC36
0x18002b228  mov     rcx, [rbx+30h]
0x18002b22c  mov     [rbp+0C0h+rcSrc2.right], esi
0x18002b22f  mov     [rbp+0C0h+rcSrc2.left], esi
0x18002b232  mov     [rbp+0C0h+rcSrc2.bottom], edi
0x18002b235  mov     [rbp+0C0h+rcSrc2.top], edi
0x18002b238  movaps  xmm0, xmmword ptr [rbp+0C0h+rcSrc2.left]
0x18002b23c  movdqa  xmmword ptr [rbp+0C0h+rcSrc1.left], xmm0
0x18002b241  mov     rcx, [rcx+60h]; hWnd
0x18002b245  call    cs:__imp_UpdateWindow
0x18002b24b  mov     rcx, r14; hWnd
0x18002b24e  call    cs:__imp_GetDC
0x18002b254  mov     rcx, r14; hWnd
0x18002b257  mov     [rbp+0C0h+hDC], rax
0x18002b25b  mov     r12, rax
0x18002b25e  call    cs:__imp_SetCapture
0x18002b264  test    r15d, r15d
0x18002b267  jz      loc_18002B9FF
0x18002b26d  mov     rcx, [rbx+30h]
0x18002b271  lea     rdx, [rbx+20h]; lpRect
0x18002b275  mov     r8d, 1; bErase
0x18002b27b  bts     dword ptr [rcx+0A8h], 12h
0x18002b283  mov     rcx, [rbx+30h]
0x18002b287  movaps  xmm0, xmmword ptr [rbp+0C0h+rcSrc2.left]
0x18002b28b  movdqu  xmmword ptr [rdx], xmm0
0x18002b28f  mov     rcx, [rcx+60h]; hWnd
0x18002b293  call    cs:__imp_InvalidateRect
0x18002b299  lea     rdx, [rbp+0C0h+Rect]; lpRect
0x18002b29d  mov     rcx, r14; hWnd
0x18002b2a0  call    cs:__imp_GetClientRect
0x18002b2a6  lea     rdx, [rbp+0C0h+var_50]; lpRect
0x18002b2aa  mov     rcx, r14; hWnd
0x18002b2ad  call    cs:__imp_GetWindowRect
0x18002b2b3  mov     ecx, 4Eh ; 'N'; nIndex
0x18002b2b8  call    cs:__imp_GetSystemMetrics
0x18002b2be  mov     ecx, 4Fh ; 'O'; nIndex
0x18002b2c3  mov     [rbp+0C0h+var_12C], eax
0x18002b2c6  mov     edi, eax
0x18002b2c8  call    cs:__imp_GetSystemMetrics
0x18002b2ce  mov     esi, eax
0x18002b2d0  mov     [rbp+0C0h+var_128], eax
0x18002b2d3  jmp     loc_18002B564
0x18002b2d8  mov     rax, [r10+260h]
0x18002b2df  mov     rcx, [rax+10h]
0x18002b2e3  mov     rax, [r10+268h]
0x18002b2ea  mov     r9d, [rax+18h]
0x18002b2ee  mov     rax, [r10+1C0h]
0x18002b2f5  mov     r8d, [rax+4]
0x18002b2f9  sub     r8d, [rcx+1Ch]
0x18002b2fd  mov     eax, [rbp+0C0h+var_B0.left]
0x18002b300  add     eax, r8d
0x18002b303  cdq
0x18002b304  idiv    dword ptr [rcx+3Ch]
0x18002b307  mov     edi, eax
0x18002b309  mov     eax, [rbp+0C0h+var_B0.top]
0x18002b30c  sub     eax, [rcx+20h]
0x18002b30f  cdq
0x18002b310  imul    edi, r9d
0x18002b314  idiv    dword ptr [rcx+40h]
0x18002b317  add     edi, eax
0x18002b319  mov     eax, [rbp+0C0h+var_B0.right]
0x18002b31c  add     eax, r8d
0x18002b31f  cdq
0x18002b320  idiv    dword ptr [rcx+3Ch]
0x18002b323  mov     r14d, eax
0x18002b326  mov     eax, [rbp+0C0h+var_B0.bottom]
0x18002b329  sub     eax, [rcx+20h]
0x18002b32c  cdq
0x18002b32d  imul    r14d, r9d
0x18002b331  idiv    dword ptr [rcx+40h]
0x18002b334  add     r14d, eax
0x18002b337  mov     r9, [rbx+30h]
0x18002b33b  mov     rax, [r9+200h]
0x18002b342  mov     ecx, [rax]
0x18002b344  dec     ecx
0x18002b346  cmp     r14d, ecx
0x18002b349  cmovg   r14d, ecx
0x18002b34d  xor     eax, eax
0x18002b34f  test    edi, edi
0x18002b351  mov     [rsp+1C0h+var_150.iItem], r14d
0x18002b356  cmovs   edi, eax
0x18002b359  test    dword ptr [r9+70h], 1000h
0x18002b361  mov     [rsp+1C0h+var_170], edi
0x18002b365  jnz     loc_18002B7F2
0x18002b36b  test    r13d, r13d
0x18002b36e  jnz     loc_18002BD02
0x18002b374  test    dword ptr [r9+70h], 1000h
0x18002b37c  jnz     loc_18002B822
0x18002b382  cmp     edi, r14d
0x18002b385  jg      loc_18002B4C1
0x18002b38b  mov     r15d, [rsp+1C0h+var_160]
0x18002b390  mov     esi, 1
0x18002b395  mov     rcx, [rbx+30h]
0x18002b399  mov     edx, edi; int
0x18002b39b  mov     rcx, [rcx+200h]; this
0x18002b3a2  call    ?GetDrawStateForItem@CLVItemStore@@QEAAPEAVCLVDrawState@@H@Z; CLVItemStore::GetDrawStateForItem(int)
0x18002b3a7  mov     rcx, [rbx+30h]
0x18002b3ab  xor     r13d, r13d
0x18002b3ae  mov     r12, rax
0x18002b3b1  xorps   xmm0, xmm0
0x18002b3b4  lea     rax, [rbp+0C0h+rc]
0x18002b3b8  xorps   xmm1, xmm1
0x18002b3bb  mov     [rsp+1C0h+var_180], rax; struct tagRECT *
0x18002b3c0  or      r9d, 0FFFFFFFFh; int
0x18002b3c4  mov     [rsp+1C0h+lprcSrc1], r13; struct tagRECT *
0x18002b3c9  mov     r8d, edi; int
0x18002b3cc  mov     [rsp+1C0h+var_190], r13; struct tagRECT *
0x18002b3d1  mov     rdx, r12; struct CLVDrawState *
0x18002b3d4  movups  xmmword ptr [rbp+0C0h+rcDst.left], xmm0
0x18002b3d8  mov     [rsp+1C0h+var_198], r13; LPRECT
0x18002b3dd  movups  xmmword ptr [rbp+0C0h+rc.left], xmm1
0x18002b3e1  mov     rcx, [rcx+260h]; this
0x18002b3e8  mov     [rsp+1C0h+wRemoveMsg], r13d; unsigned int
0x18002b3ed  call    ?GetRects@CLVView@@QEAAHPEAVCLVDrawState@@HHKPEAUtagRECT@@111@Z; CLVView::GetRects(CLVDrawState *,int,int,ulong,tagRECT *,tagRECT *,tagRECT *,tagRECT *)
0x18002b3f2  mov     rcx, [rbx+30h]; this
0x18002b3f6  movzx   r8d, word ptr [rcx+0A4h]
0x18002b3fe  cmp     r8w, si
0x18002b402  jz      loc_18002B71F
0x18002b408  mov     eax, [rbp+0C0h+rc.right]
0x18002b40b  mov     ecx, 4
0x18002b410  sub     eax, [rbp+0C0h+rc.left]
0x18002b413  cdq
0x18002b414  idiv    ecx
0x18002b416  mov     ecx, eax
0x18002b418  mov     eax, 3
0x18002b41d  cmp     r8w, ax
0x18002b421  jz      loc_18002BDB1
0x18002b427  mov     eax, [rbp+0C0h+rc.bottom]
0x18002b42a  mov     r8d, 0FFFFFFFCh
0x18002b430  sub     eax, [rbp+0C0h+rc.top]
0x18002b433  neg     ecx
0x18002b435  cdq
0x18002b436  idiv    r8d
0x18002b439  mov     edx, ecx; dx
0x18002b43b  lea     rcx, [rbp+0C0h+rc]; lprc
0x18002b43f  mov     r8d, eax; dy
0x18002b442  call    cs:__imp_InflateRect
0x18002b448  lea     r8, [rbp+0C0h+rc]; lprcSrc2
0x18002b44c  lea     rdx, [rbp+0C0h+rcSrc1]; lprcSrc1
0x18002b450  lea     rcx, [rbp+0C0h+rcDst]; lprcDst
0x18002b454  call    cs:__imp_IntersectRect
0x18002b45a  xor     r12d, r12d
0x18002b45d  lea     r8, [rbp+0C0h+rc]; lprcSrc2
0x18002b461  test    eax, eax
0x18002b463  lea     rdx, [rbp+0C0h+rcSrc2]; lprcSrc1
0x18002b467  lea     rcx, [rbp+0C0h+rcDst]; lprcDst
0x18002b46b  mov     r13d, eax
0x18002b46e  setnz   r12b
0x18002b472  call    cs:__imp_IntersectRect
0x18002b478  mov     rdx, [rbp+0C0h+Msg.wParam]
0x18002b47c  xor     ecx, ecx
0x18002b47e  test    eax, eax
0x18002b480  mov     [rbp+0C0h+pt.x], eax
0x18002b483  setnz   cl
0x18002b486  test    dl, 8
0x18002b489  jnz     loc_18002BDC1
0x18002b48f  cmp     r12d, ecx
0x18002b492  jnz     loc_18002BDDD
0x18002b498  test    eax, eax
0x18002b49a  jnz     loc_18002B791
0x18002b4a0  add     edi, esi
0x18002b4a2  cmp     edi, r14d
0x18002b4a5  jle     loc_18002B395
0x18002b4ab  mov     esi, [rbp+0C0h+var_13C]
0x18002b4ae  mov     [rsp+1C0h+var_160], r15d
0x18002b4b3  mov     r15d, [rsp+1C0h+var_158]
0x18002b4b8  mov     [rsp+1C0h+var_170], edi
0x18002b4bc  mov     r13d, [rsp+1C0h+var_16C]
0x18002b4c1  mov     rcx, [rbx+30h]
0x18002b4c5  mov     edi, 1
0x18002b4ca  mov     eax, [rcx+0A0h]
0x18002b4d0  shr     eax, 1
0x18002b4d2  test    dil, al
0x18002b4d5  jnz     loc_18002BA20
0x18002b4db  mov     r15d, [rbp+0C0h+var_130]
0x18002b4df  test    r15d, r15d
0x18002b4e2  jz      short loc_18002B536
0x18002b4e4  xorps   xmm0, xmm0
0x18002b4e7  lea     r8, [rbp+0C0h+rcSrc2]; lprcSrc2
0x18002b4eb  lea     rdx, [rbp+0C0h+rcSrc1]; lprcSrc1
0x18002b4ef  lea     rcx, [rbp+0C0h+rc]; lprcDst
0x18002b4f3  movups  xmmword ptr [rbp+0C0h+rc.left], xmm0
0x18002b4f7  call    cs:__imp_UnionRect
0x18002b4fd  mov     r8d, edi; dy
0x18002b500  lea     rcx, [rbp+0C0h+rc]; lprc
0x18002b504  mov     edx, edi; dx
0x18002b506  call    cs:__imp_InflateRect
0x18002b50c  mov     rax, [rbx+30h]
0x18002b510  lea     rdx, [rbp+0C0h+rc]; lpRect
0x18002b514  mov     r8d, edi; bErase
0x18002b517  bts     dword ptr [rax+0A8h], 12h
0x18002b51f  mov     rcx, [rbx+30h]
0x18002b523  movaps  xmm0, xmmword ptr [rbp+0C0h+rcSrc2.left]
0x18002b527  movdqu  xmmword ptr [rbx+20h], xmm0
0x18002b52c  mov     rcx, [rcx+60h]; hWnd
0x18002b530  call    cs:__imp_InvalidateRect
0x18002b536  mov     rcx, [rbx+30h]
0x18002b53a  mov     rcx, [rcx+60h]; hWnd
0x18002b53e  call    cs:__imp_UpdateWindow
0x18002b544  mov     r12, [rbp+0C0h+hDC]
0x18002b548  test    r15d, r15d
0x18002b54b  jz      loc_18002B96B
0x18002b551  movaps  xmm0, xmmword ptr [rbp+0C0h+rcSrc2.left]
0x18002b555  mov     r14, [rbp+0C0h+var_108]
0x18002b559  movdqa  xmmword ptr [rbp+0C0h+rcSrc1.left], xmm0
0x18002b55e  mov     esi, [rbp+0C0h+var_128]
0x18002b561  mov     edi, [rbp+0C0h+var_12C]
0x18002b564  call    cs:__imp_GetCapture
0x18002b56a  cmp     rax, r14
0x18002b56d  jnz     loc_18002B98F
0x18002b573  xor     r9d, r9d; wMsgFilterMax
0x18002b576  mov     [rsp+1C0h+wRemoveMsg], 1; wRemoveMsg
0x18002b57e  xor     r8d, r8d; wMsgFilterMin
0x18002b581  lea     rcx, [rbp+0C0h+Msg]; lpMsg
0x18002b585  xor     edx, edx; hWnd
0x18002b587  call    cs:__imp_PeekMessageW
0x18002b58d  test    eax, eax
0x18002b58f  jz      loc_18002B73E
0x18002b595  mov     edx, 4202h; nCode
0x18002b59a  lea     rcx, [rbp+0C0h+Msg]; lpMsg
0x18002b59e  call    cs:__imp_CallMsgFilterW
0x18002b5a4  test    eax, eax
0x18002b5a6  jnz     short loc_18002B564
0x18002b5a8  mov     eax, [rbp+0C0h+Msg.message]
0x18002b5ab  mov     ecx, 201h
0x18002b5b0  cmp     eax, ecx
0x18002b5b2  ja      loc_18002B8A5
0x18002b5b8  jz      loc_18002BEB4
0x18002b5be  sub     eax, 100h
0x18002b5c3  jz      loc_18002BE94
0x18002b5c9  sub     eax, 1
0x18002b5cc  jz      short loc_18002B564
0x18002b5ce  sub     eax, 1
0x18002b5d1  jz      short loc_18002B564
0x18002b5d3  sub     eax, 11h
0x18002b5d6  jz      loc_18002BC4F
0x18002b5dc  cmp     eax, 0EDh
0x18002b5e1  jnz     loc_18002B8E7
0x18002b5e7  mov     rcx, [rbx+30h]
0x18002b5eb  or      eax, 0FFFFFFFFh
0x18002b5ee  mov     [rsp+1C0h+var_160], eax
0x18002b5f2  mov     [rbp+0C0h+pt.x], eax
0x18002b5f5  mov     rax, qword ptr [rbp+0C0h+Msg.pt.x]
0x18002b5f9  mov     qword ptr [rbp+0C0h+Point.x], rax
0x18002b5fd  test    dword ptr [rcx+70h], 300000h
0x18002b604  jnz     loc_18002BC5F
0x18002b60a  lea     rdx, [rbp+0C0h+Point]; lpPoint
0x18002b60e  mov     rcx, r14; hWnd
0x18002b611  call    cs:__imp_ScreenToClient
0x18002b617  xor     edi, edi
0x18002b619  xor     esi, esi
0x18002b61b  mov     [rsp+1C0h+var_164], edi
0x18002b61f  mov     [rsp+1C0h+var_168], esi
0x18002b623  mov     edx, [rbp+0C0h+var_138]
0x18002b626  mov     r8d, [rbp+0C0h+var_134]
0x18002b62a  sub     edx, edi
  ... truncated ...
```
