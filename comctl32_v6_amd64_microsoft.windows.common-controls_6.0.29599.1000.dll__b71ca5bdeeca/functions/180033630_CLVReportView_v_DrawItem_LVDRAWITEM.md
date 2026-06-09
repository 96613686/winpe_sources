# CLVReportView::v_DrawItem(LVDRAWITEM *)

- ea: `0x180033630`
- end: `0x1800347eb`
- name: `?v_DrawItem@CLVReportView@@UEAAHPEAULVDRAWITEM@@@Z`
- size: `4539`
- prototype: `__int64 __fastcall(CLVReportView *__hidden this, struct LVDRAWITEM *)`
- caller_count: `0`
- callee_count: `28`
- tags: `broker_com_uri`

## callees

- `0x1800099c0`
- `0x180019bfc`
- `0x180029610`
- `0x180032c4c`
- `0x180033630`
- `0x1800347f4`
- `0x180034830`
- `0x180034ac0`
- `0x180035bc0`
- `0x180036850`
- `0x18003c818`
- `0x18003e370`
- `0x180041954`
- `0x18006e140`
- `0x180092010`
- `0x180092034`
- `0x180092b34`
- `0x180092d60`
- `0x1800a8ee8`
- `0x1800aba4c`
- `0x1800abadc`
- `0x1800be478`
- `0x180114520`
- `0x180114ebc`
- `0x1801cdbd4`
- `0x1801cecbc`
- `0x1801d0c48`
- `0x1801d1010`

## import_xrefs

- `GDI32!SetBkColor` at `0x1800343f9`
- `GDI32!SetBkColor` at `0x180034424`
- `GDI32!SetBkColor` at `0x1800343f9`
- `GDI32!SetBkColor` at `0x180034424`
- `GDI32!SetTextColor` at `0x1800343ea`
- `GDI32!SetTextColor` at `0x180034417`
- `GDI32!SetTextColor` at `0x1800343ea`
- `GDI32!SetTextColor` at `0x180034417`
- `GDI32!SelectObject` at `0x18003400b`
- `GDI32!SelectObject` at `0x180034029`
- `GDI32!SelectObject` at `0x1800347c8`
- `GDI32!SelectObject` at `0x18003400b`
- `GDI32!SelectObject` at `0x180034029`
- `GDI32!SelectObject` at `0x1800347c8`
- `GDI32!GetTextExtentPointW` at `0x18003392c`
- `GDI32!GetTextExtentPointW` at `0x18003392c`
- `USER32!SetRectEmpty` at `0x180034067`
- `USER32!SetRectEmpty` at `0x180034067`
- `USER32!OffsetRect` at `0x180033b87`
- `USER32!OffsetRect` at `0x180033b9b`
- `USER32!OffsetRect` at `0x18003469e`
- `USER32!OffsetRect` at `0x180033b87`
- `USER32!OffsetRect` at `0x180033b9b`
- `USER32!OffsetRect` at `0x18003469e`
- `USER32!IsRectEmpty` at `0x180033daa`
- `USER32!IsRectEmpty` at `0x180033daa`
- `USER32!IntersectRect` at `0x180033742`
- `USER32!IntersectRect` at `0x180033742`
- `USER32!UnionRect` at `0x180033d3a`
- `USER32!UnionRect` at `0x1800340be`
- `USER32!UnionRect` at `0x18003437e`
- `USER32!UnionRect` at `0x180033d3a`
- `USER32!UnionRect` at `0x1800340be`
- `USER32!UnionRect` at `0x18003437e`
- `USER32!SendMessageW` at `0x180033c6c`
- `USER32!SendMessageW` at `0x180033e03`
- `USER32!SendMessageW` at `0x180033ee3`
- `USER32!SendMessageW` at `0x180033c6c`
- `USER32!SendMessageW` at `0x180033e03`
- `USER32!SendMessageW` at `0x180033ee3`
- `USER32!GetSystemMetrics` at `0x180033ddc`
- `USER32!GetSystemMetrics` at `0x180033ddc`
- `USER32!GetDlgCtrlID` at `0x180033e4d`
- `USER32!GetDlgCtrlID` at `0x180033e4d`
- `USER32!GetSysColor` at `0x180033892`
- `USER32!GetSysColor` at `0x180033892`

## pseudocode

```c
__int64 __fastcall CLVReportView::v_DrawItem(CListView **this, struct LVDRAWITEM *a2)
{
  int v4; // r9d
  struct CLVDrawState *v5; // rdx
  CListView *v6; // rcx
  unsigned int v7; // r14d
  const RECT *v8; // r8
  _DWORD *v9; // rax
  CListView *v10; // rax
  int v11; // r13d
  LONG v12; // r12d
  __int64 v13; // rax
  __int64 v14; // rcx
  CListView *v15; // r10
  int v16; // edx
  int v17; // r12d
  unsigned int v18; // r12d
  char v19; // r8
  __int16 v20; // r9
  struct CListView *v21; // r10
  LONG right; // eax
  unsigned int v23; // r15d
  CListView *v24; // rcx
  int v25; // eax
  CListView *v26; // r11
  unsigned int v27; // ebx
  __int64 v28; // rcx
  __int64 v29; // rcx
  HDC v30; // rcx
  const unsigned __int16 *pszText; // r15
  CLVDrawItemManager **v32; // r11
  CLVDrawItemManager *v33; // r10
  CLVDrawItemManager *v34; // rcx
  void *v35; // r8
  unsigned int v36; // r12d
  CListView *v37; // rcx
  __int64 v38; // rbx
  _QWORD *v39; // rax
  __int64 v40; // rcx
  LONG cx; // eax
  CListView *v42; // rcx
  CListView *v43; // rax
  CLVHeaderControlManager *v44; // rbx
  struct HD *HDPtr; // rax
  int v46; // r12d
  CListView *v47; // rcx
  int v48; // ebx
  LONG v49; // r8d
  _DWORD *v50; // rdx
  int iImage; // r9d
  unsigned int v52; // r15d
  CListView *v53; // rbx
  int v54; // ecx
  __int64 v55; // rax
  int v56; // r10d
  CListView *v57; // r8
  __int64 v58; // r11
  int v59; // eax
  int v60; // edx
  __int64 v61; // r8
  CLVImageListManager *v62; // r10
  struct CLVDrawState *v63; // r11
  unsigned int v64; // ecx
  int v65; // ebx
  CListView *v66; // rbx
  unsigned int DlgCtrlID; // eax
  CListView *v68; // rdx
  WPARAM v69; // r10
  __int64 v70; // rax
  int v71; // ecx
  __int64 v72; // r8
  __int64 v74; // rcx
  HGDIOBJ v75; // rax
  __int64 v76; // rcx
  __int16 v77; // ax
  LONG v78; // r8d
  unsigned int v79; // r12d
  int v80; // edx
  CListView *v81; // rcx
  unsigned int SortColumnColor; // eax
  CLVInPlaceEditingManager **v83; // r8
  CLVInPlaceEditingManager **v84; // r8
  __int64 v85; // r10
  __int16 CXLabelSubItem; // ax
  CListView *v87; // rcx
  __int64 v88; // rdx
  __int128 v89; // xmm6
  int v90; // r14d
  int v91; // r15d
  COLORREF v92; // r12d
  COLORREF v93; // r13d
  __int64 v94; // rcx
  const struct tagLVITEMINDEX *v95; // rdx
  CListView *v96; // rcx
  int v97; // r10d
  LPARAM *v98; // r9
  LONG v99; // edx
  CLVInPlaceEditingManager *v100; // r10
  __int64 v101; // r10
  __int64 v102; // r10
  int v103; // [rsp+30h] [rbp-D8h]
  unsigned int lprcDst; // [rsp+40h] [rbp-C8h]
  int v105; // [rsp+48h] [rbp-C0h]
  int v106; // [rsp+68h] [rbp-A0h]
  unsigned int v107; // [rsp+88h] [rbp-80h]
  char v108; // [rsp+8Ch] [rbp-7Ch]
  int v109; // [rsp+90h] [rbp-78h]
  int v110; // [rsp+94h] [rbp-74h]
  unsigned int v111; // [rsp+98h] [rbp-70h]
  int dy; // [rsp+9Ch] [rbp-6Ch]
  int v113; // [rsp+A0h] [rbp-68h]
  __int16 v114; // [rsp+A8h] [rbp-60h]
  int v115; // [rsp+B0h] [rbp-58h]
  int v116; // [rsp+B8h] [rbp-50h]
  HGDIOBJ h; // [rsp+C0h] [rbp-48h]
  tagLVITEMINDEX v118; // [rsp+C8h] [rbp-40h] BYREF
  struct tagLVITEMINDEX v119; // [rsp+D0h] [rbp-38h] BYREF
  struct IDrawPropertyControl *v120; // [rsp+D8h] [rbp-30h] BYREF
  struct tagLVITEMW v121; // [rsp+E8h] [rbp-20h] BYREF
  LPARAM v122; // [rsp+148h] [rbp+40h] BYREF
  int iItem; // [rsp+150h] [rbp+48h]
  int v124; // [rsp+154h] [rbp+4Ch]
  int v125; // [rsp+158h] [rbp+50h]
  __int64 v126; // [rsp+160h] [rbp+58h]
  __int64 v127; // [rsp+168h] [rbp+60h]
  LONG left; // [rsp+170h] [rbp+68h]
  LONG top; // [rsp+174h] [rbp+6Ch]
  __int64 v130; // [rsp+178h] [rbp+70h]
  __int64 v131; // [rsp+180h] [rbp+78h]
  int v132; // [rsp+198h] [rbp+90h]
  int v133; // [rsp+19Ch] [rbp+94h]
  RECT rcSrc2; // [rsp+1A8h] [rbp+A0h] BYREF
  struct tagSIZE sz; // [rsp+1B8h] [rbp+B0h] BYREF
  RECT rcSrc1; // [rsp+1C0h] [rbp+B8h] BYREF
  struct tagRECT rc; // [rsp+1D0h] [rbp+C8h] BYREF
  struct tagRECT rcDst; // [rsp+1E0h] [rbp+D8h] BYREF
  struct tagRECT v139; // [rsp+1F0h] [rbp+E8h] BYREF
  struct _HD_ITEMW lParam; // [rsp+208h] [rbp+100h] BYREF
  char v141; // [rsp+258h] [rbp+150h] BYREF

  rc = 0;
  rcSrc2 = 0;
  rcSrc1 = 0;
  v139 = 0;
  rcDst = 0;
  memset_0(&v121, 0, sizeof(v121));
  memset_0(&lParam, 0, sizeof(lParam));
  v4 = *((_DWORD *)a2 + 12);
  v5 = (struct CLVDrawState *)*((_QWORD *)a2 + 1);
  v121.iItem = *((_DWORD *)a2 + 28);
  CLVReportView::GetRects((CLVReportView *)this, v5, v121.iItem, v4, 0, 0, &rcSrc1, &v139);
  v6 = this[1];
  v7 = 1;
  if ( rcSrc1.bottom <= *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v6 + 76) + 16LL) + 20LL) )
    return v7;
  v8 = (const RECT *)*((_QWORD *)a2 + 3);
  if ( v8 )
  {
    if ( rcSrc1.top >= v8->bottom )
      goto LABEL_133;
    if ( !IntersectRect(&rcDst, &rcSrc1, v8) )
      return v7;
  }
  v6 = this[1];
  if ( rcSrc1.top < *((_DWORD *)v6 + 56) )
  {
    v9 = (_DWORD *)*((_QWORD *)a2 + 2);
    v113 = 0;
    if ( v9 )
    {
      v115 = *v9 - rcSrc1.left;
      dy = v9[1] - rcSrc1.top;
      OffsetRect(&rcSrc1, v115, dy);
    }
    else
    {
      v115 = 0;
      dy = 0;
    }
    v10 = this[1];
    v121.stateMask = 0xFFFF;
    v121.state = 0;
    if ( (*((_DWORD *)v10 + 28) & 0x400) == 0 )
    {
      SetRectEmpty(&rcDst);
      if ( CListView::IsFullRowSelect(this[1]) )
      {
        *((struct tagRECT *)a2 + 6) = v139;
        CLVThemesManager::DrawCustomTheme(*((CLVThemesManager **)this[1] + 59), a2);
      }
      v12 = 0;
      goto LABEL_48;
    }
    v11 = 0;
    v12 = 0;
    v110 = 0;
    while ( 1 )
    {
      v42 = this[1];
      if ( v11 && CListView::IsFullRowSelect(v42) && (*((_DWORD *)v42 + 42) & 0x20000) != 0 )
        goto LABEL_47;
      v116 = *((_DWORD *)v42 + 45);
      v121.iImage = -1;
      v121.iGroup = *((_DWORD *)a2 + 12);
      v121.iSubItem = v11;
      v121.cchTextMax = 260;
      v121.mask = v11 != 0 ? 11 : 31;
      v121.pszText = (LPWSTR)&v141;
      CLVItemStore::OnGetItem(*((CLVItemStore **)v42 + 64), &v121);
      v43 = this[1];
      lParam.mask = 5;
      v44 = (CLVHeaderControlManager *)*((_QWORD *)v43 + 49);
      HDPtr = (struct HD *)CLVHeaderControlManager::_GetHDPtr(v44);
      if ( HDPtr )
        Header_OnGetItem(HDPtr, v11, &lParam);
      else
        SendMessageW(*(HWND *)v44, 0x120Bu, v11, (LPARAM)&lParam);
      if ( !v11 )
      {
        v66 = this[1];
        if ( (*((_DWORD *)v66 + 28) & 0x400) != 0 )
        {
          memset_0(&v122, 0, 0x40u);
          LODWORD(v122) = 102;
          DlgCtrlID = GetDlgCtrlID(*((HWND *)v66 + 12));
          v68 = this[1];
          v69 = DlgCtrlID;
          HIDWORD(v122) = DlgCtrlID;
          iItem = v121.iItem;
          v124 = 1;
          v126 = *((_QWORD *)v68 + 12);
          v127 = *((_QWORD *)a2 + 11);
          left = rcSrc1.left;
          v70 = *((_QWORD *)a2 + 5);
          top = rcSrc1.top;
          v130 = *(_QWORD *)&rcSrc1.right;
          if ( v70 )
            v131 = *(_QWORD *)(v70 + 32);
          v71 = v125;
          if ( (v121.state & 1) != 0 )
          {
            v71 = v125 | 0x10;
            v125 |= 0x10u;
          }
          if ( (v121.state & 2) != 0 )
          {
            v71 |= 1u;
            v125 = v71;
            if ( (*((_DWORD *)v68 + 44) & 0x8000000) != 0 )
            {
              v71 |= 8u;
              v125 = v71;
            }
          }
          v72 = *((_QWORD *)v68 + 48);
          if ( *(_DWORD *)(v72 + 16) == v121.iItem
            && ((*((_DWORD *)v68 + 40) & 2) == 0
             || *((_WORD *)v68 + 82) == 3
             || !*((_QWORD *)v68 + 93)
             || *(_DWORD *)(v72 + 20) == *((_DWORD *)a2 + 12)) )
          {
            v125 = v71 | 0x40;
          }
          SendMessageW(*((HWND *)v68 + 13), 0x2Bu, v69, (LPARAM)&v122);
          return v7;
        }
      }
      v46 = *((_DWORD *)a2 + 8);
      v114 = 0;
      v108 = v46;
      CLVReportView::GetRectsEx((CLVReportView *)this, v121.iItem, *((_DWORD *)a2 + 12), v11, &rc, &rcSrc2);
      if ( v110 > 0 && !v11 && IsRectEmpty(&rc) && !*(_DWORD *)(*((_QWORD *)a2 + 1) + 24LL) )
      {
        v65 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this[1] + 76) + 16LL) + 44LL);
        rcSrc2.left += -2 - v65 - GetSystemMetrics(45);
      }
      OffsetRect(&rc, v115, dy);
      OffsetRect(&rcSrc2, v115, dy);
      if ( !CListView::IsFullRowSelect(this[1]) && !v11 )
      {
        v89 = *((_OWORD *)a2 + 6);
        UnionRect((LPRECT)a2 + 6, &rc, &rcSrc2);
        *((_DWORD *)a2 + 26) -= *((_DWORD *)this + 9);
        CLVThemesManager::DrawCustomTheme(*((CLVThemesManager **)this[1] + 59), a2);
        *((_OWORD *)a2 + 6) = v89;
      }
      v47 = this[1];
      v48 = *((_DWORD *)a2 + 30);
      v49 = v48 & 0xFFFFFFBF;
      sz.cx = v48 & 0xFFFFFFBF;
      v50 = (_DWORD *)*((_QWORD *)v47 + 48);
      if ( v50[4] == v121.iItem
        && ((*((_DWORD *)v47 + 40) & 2) == 0
         || *((_WORD *)v47 + 82) == 3
         || !*((_QWORD *)v47 + 93)
         || v50[5] == *((_DWORD *)a2 + 12))
        && v50[7] == v110 )
      {
        v49 |= 0x40u;
        sz.cx = v49;
      }
      if ( (*((_BYTE *)a2 + 52) & 0x20) != 0 )
      {
        *((_DWORD *)a2 + 30) = v49;
        *((_DWORD *)a2 + 36) = v11;
        UnionRect((LPRECT)a2 + 6, &rcSrc2, &rc);
        *((_DWORD *)a2 + 26) -= *((_DWORD *)this + 9);
        v76 = (__int64)this[1] + 96;
        if ( (*((_BYTE *)this[1] + 116) & 0x20) != 0 )
        {
          *((_DWORD *)a2 + 20) = 196609;
          v77 = CCSendNotify(v76, -12, (LPARAM)a2 + 56);
          if ( (v77 & 0xFE01) != 0 )
            v77 = 0;
        }
        else
        {
          v77 = 0;
        }
        v78 = *((_DWORD *)a2 + 30);
        sz.cx = v78;
        *((_DWORD *)a2 + 30) = v48;
        v114 = v77;
        if ( (v77 & 4) != 0 )
          goto LABEL_46;
        v79 = v46 & 0xFFFFFF87;
        v80 = v79 | 8;
        if ( (v78 & 0x10) == 0 )
          v80 = v79;
        if ( (v78 & 1) != 0 )
        {
          v87 = this[1];
          v46 = v80 | (16 * (((*((_DWORD *)v87 + 42) & 1) == 0) + 1));
          v88 = *((_QWORD *)v87 + 48);
          if ( *(_DWORD *)(v88 + 16) == v121.iItem
            && ((*((_DWORD *)v87 + 40) & 2) == 0
             || *((_WORD *)v87 + 82) == 3
             || !*((_QWORD *)v87 + 93)
             || *(_DWORD *)(v88 + 20) == *((_DWORD *)a2 + 12))
            && (*((_BYTE *)v87 + 176) & 0xC0) != 0 )
          {
            v46 |= 0x40u;
          }
          v108 = v46;
        }
        else
        {
          v46 = v80;
          v108 = v80;
        }
      }
      iImage = v121.iImage;
      if ( v11 && v121.iImage != -1 )
        rcSrc2.left += 2 + *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL);
      v52 = v46;
      v53 = this[1];
      if ( (v121.state & 8) != 0 || (v54 = 16, (v46 & 0x10) != 0) && (v121.state & 2) != 0 )
        v54 = 8;
      if ( (v46 & 0x20) != 0 && (v121.state & 2) != 0 )
        v54 = 256;
      v55 = *((_QWORD *)v53 + 59);
      v56 = v54 | 0x200000;
      if ( (*((_DWORD *)v53 + 42) & 0x20000) == 0 )
        v56 = v54;
      if ( *(_DWORD *)v55 && (*(_DWORD *)(*(_QWORD *)(v55 + 48) + 168LL) & 0x20000) == 0 )
        v56 |= 0x10000u;
      v13 = *((_QWORD *)v53 + 43);
      v109 = v56;
      v14 = *(_QWORD *)(v13 + 8);
      if ( v14 || *(_QWORD *)(v13 + 56) || (*((_DWORD *)v53 + 44) & 0x400000) != 0 )
        v107 = -1;
      else
        v107 = *((_DWORD *)a2 + 35);
      if ( v11 == *((_DWORD *)this + 6)
        && (!v14 || !*(_DWORD *)v13)
        && (*((_DWORD *)v53 + 44) & 0x400000) == 0
        && (!CListView::IsFullRowSelect(v53) || (v56 & 0x108) == 0) )
      {
        SortColumnColor = CListView::GetSortColumnColor(v81);
        v56 = v109;
        *((_DWORD *)v53 + 45) = SortColumnColor;
        iImage = v121.iImage;
        v107 = *((_DWORD *)this[1] + 45);
      }
      if ( iImage == -1 && v11 )
        v52 = v46 | 1;
      if ( (*((_BYTE *)a2 + 32) & 2) != 0 )
      {
        v107 = -1;
        v109 = v56 | 0x80;
      }
      if ( (v114 & 8) == 0 )
      {
        v57 = this[1];
        v58 = *((_QWORD *)a2 + 1);
        v59 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v57 + 76) + 16LL) + 64LL);
        if ( v59 > *(_DWORD *)(v58 + 12) )
          rc.top += (v59 - *(_DWORD *)(v58 + 12)) / 2;
        if ( CLVThemesManager::HasCustomTheme(*((CLVThemesManager **)v57 + 59)) )
          v64 = -1;
        else
          v64 = *(_DWORD *)(v61 + 180);
        CLVImageListManager::DrawImageEx2(
          v62,
          v63,
          &v121,
          *((HDC *)a2 + 11),
          rc.left,
          v60,
          v64,
          v52,
          rcSrc2.right,
          0,
          0);
      }
      if ( CListView::IsFullRowSelect(this[1]) && (v46 & 8) != 0 )
      {
        UnionRect(&rcDst, &rcDst, &rcSrc2);
        v15 = this[1];
      }
      v16 = (v11 != 0 ? 525381 : 525317) | 0x400000;
      if ( (lParam.fmt & 3) == 0 )
        v16 = v11 != 0 ? 525381 : 525317;
      v17 = v16 | 0x800;
      if ( (*((_DWORD *)v15 + 32) & 0x2000) == 0 )
        v17 = v16;
      v18 = v109 | v17;
      if ( CListView::IsFullRowSelect(v15) || (v20 & 0x108) == 0 && (v19 & 1) == 0 )
      {
        right = rcSrc2.right;
        goto LABEL_24;
      }
      if ( v11 )
      {
        CXLabelSubItem = CLVReportView::GetCXLabelSubItem((CLVReportView *)this, v121.pszText, *((HDC *)a2 + 11));
        goto LABEL_195;
      }
      LODWORD(v126) = v126 & 0xFFFFFFFE;
      v132 = 0x7FFFFFFF;
      v133 = 0x7FFFFFFF;
      if ( (*((_DWORD *)v21 + 28) & 0x1000) != 0 )
        break;
      v98 = (LPARAM *)*((_QWORD *)a2 + 5);
      if ( !v98 )
        goto LABEL_193;
LABEL_194:
      CXLabelSubItem = CLVReportView::_GetCXLabel(
                         (CLVReportView *)this,
                         v121.iItem,
                         *((_DWORD *)a2 + 12),
                         (struct _LISTITEM *)v98,
                         *((HDC *)a2 + 11),
                         1);
LABEL_195:
      v99 = rcSrc2.left + CXLabelSubItem;
      right = rcSrc2.right;
      if ( rcSrc2.right > v99 )
        right = v99;
LABEL_24:
      v23 = *((_DWORD *)a2 + 34);
      rcSrc2.right = right - *((_DWORD *)this + 9);
      h = 0;
      v111 = v23;
      if ( v23 == GetSysColor(26)
        || (v24 = this[1], v25 = *((_DWORD *)v24 + 44), (v25 & 0x800) != 0)
        && ((v25 & 0x40) != 0
         || (v25 & 0x80u) != 0
         && CLVItemStore::OnGetItemState(*((CLVItemStore **)v24 + 64), v121.iItem, *((_DWORD *)a2 + 12), 2u)) )
      {
        if ( v11 && !CListView::IsFullRowSelect(this[1]) )
        {
          v75 = SelectObject(*((HDC *)a2 + 11), *(HGDIOBJ *)(v74 + 280));
          h = v75;
          if ( v75 != *((HGDIOBJ *)this[1] + 36) )
          {
            SelectObject(*((HDC *)a2 + 11), v75);
            h = 0;
          }
          v23 = *((_DWORD *)this[1] + 47);
          v111 = v23;
        }
      }
      if ( (v18 & 8) != 0 && (v108 & 0x40) != 0 )
        v18 |= 0x200u;
      v26 = this[1];
      v27 = v121.iItem;
      v28 = *((_QWORD *)v26 + 52);
      if ( *(_QWORD *)(v28 + 32) )
      {
        v95 = (const struct tagLVITEMINDEX *)(v28 + 8);
        if ( *(_DWORD *)(v28 + 8) != -1 && *(_DWORD *)(v28 + 40) != -1 )
        {
          v96 = *(CListView **)(v28 + 72);
          v118.iGroup = *((_DWORD *)a2 + 12);
          v118.iItem = v121.iItem;
          if ( (unsigned int)CListView::IsEqualIndexes(v96, v95, &v118) )
          {
            if ( v11 == v97 )
            {
              v120 = 0;
LABEL_30:
              if ( ((*((_BYTE *)a2 + 52) | (unsigned __int8)v114) & 2) != 0 )
              {
                v30 = (HDC)*((_QWORD *)a2 + 11);
                sz = 0;
                GetTextExtentPointW(v30, L"...", 3, &sz);
                v27 = v121.iItem;
              }
              pszText = v121.pszText;
              if ( v121.pszText && (v11 > 0 || (*((_DWORD *)this[1] + 44) & 0x20000) == 0) )
              {
                if ( (v114 & 8) != 0 )
                {
                  if ( !v11 || (v109 & 0x80u) == 0 )
                    CLVDrawItemManager::DrawTextW(
                      *((CLVDrawItemManager **)this[1] + 47),
                      (struct CLVDrawState *)(lParam.fmt & 3),
                      *((HDC *)a2 + 11),
                      &WindowName,
                      &rcSrc2,
                      lParam.fmt & 3,
                      v18,
                      *(_DWORD *)(*((_QWORD *)a2 + 1) + 20LL),
                      v105,
                      v107,
                      v107);
                }
                else
                {
                  v32 = (CLVDrawItemManager **)this[1];
                  v33 = v32[52];
                  if ( (*(_QWORD *)v33 || (unsigned int)CLVInPlaceEditingManager::IsInSubItemEdit(v32[52]))
                    && (v119.iGroup = *((_DWORD *)a2 + 12),
                        v119.iItem = v27,
                        (unsigned int)CListView::IsEqualIndexes(
                                        (CListView *)v32,
                                        (const struct tagLVITEMINDEX *)v33 + 1,
                                        &v119))
                    && (!(unsigned int)CLVInPlaceEditingManager::IsInSubItemEdit(v100) || *(_DWORD *)(v101 + 40) == v11)
                    && (!*(_QWORD *)v101 || !v11) )
                  {
                    CLVDrawItemManager::DrawTextW(
                      v32[47],
                      (struct CLVDrawState *)(lParam.fmt & 3),
                      *((HDC *)a2 + 11),
                      &WindowName,
                      &rcSrc2,
                      lParam.fmt & 3,
                      v18,
                      *(_DWORD *)(*((_QWORD *)a2 + 1) + 20LL),
                      v105,
                      v111,
                      v107);
                  }
                  else
                  {
                    v34 = v32[47];
                    if ( *(_DWORD *)(*(_QWORD *)v34 + 48LL) )
                      v35 = *(void **)(*(_QWORD *)(*(_QWORD *)v34 + 472LL) + 24LL);
                    else
                      v35 = 0;
                    CLVDrawItemManager::ThemeDrawText(
                      v34,
                      (struct CLVDrawState *)*(unsigned int *)(*((_QWORD *)a2 + 1) + 20LL),
                      v35,
                      *((HDC *)a2 + 11),
                      0,
                      v103,
                      0,
                      pszText,
                      &rcSrc2,
                      lParam.fmt & 3,
                      v18,
                      *(_DWORD *)(*((_QWORD *)a2 + 1) + 20LL),
                      v106,
                      v111,
                      v107);
                  }
                }
              }
              v36 = v107;
              goto LABEL_41;
            }
          }
        }
      }
      v120 = 0;
      if ( !v11 )
        goto LABEL_30;
      v29 = *(_QWORD *)(**((_QWORD **)v26 + 65) + 752LL);
      if ( !v29 )
        goto LABEL_30;
      if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, GUID *, struct IDrawPropertyControl **))(*(_QWORD *)v29 + 32LL))(
             v29,
             v27,
             (unsigned int)v11,
             &GUID_1572dd51_443c_44b0_ace4_38a005fc697e,
             &v120) < 0 )
      {
        v27 = v121.iItem;
        goto LABEL_30;
      }
      lprcDst = v18;
      v36 = v107;
      CLVDrawItemManager::DrawSubItemControl(
        *((CLVDrawItemManager **)this[1] + 47),
        *((HDC *)a2 + 11),
        v120,
        sz.cx,
        v23,
        v107,
        &rcSrc2,
        lprcDst,
        lParam.fmt,
        *((_DWORD *)a2 + 28),
        *((_DWORD *)a2 + 12));
      (*(void (__fastcall **)(struct IDrawPropertyControl *))(*(_QWORD *)v120 + 16LL))(v120);
LABEL_41:
      if ( (v108 & 8) != 0 && (*((_WORD *)this[1] + 72) & 1) == 0 && (v114 & 0x100) == 0 )
      {
        if ( !CListView::IsFullRowSelect(this[1])
          || (unsigned int)CLVInPlaceEditingManager::CanEditSubItems(*v83)
          && *(int *)(*(_QWORD *)(v102 + 384) + 12LL) >= 1 )
        {
          v113 = 0;
          if ( (unsigned int)CLVInPlaceEditingManager::CanEditSubItems(*v83)
            && v11 == *(_DWORD *)(*(_QWORD *)(v85 + 384) + 12LL)
            || !(unsigned int)CLVInPlaceEditingManager::CanEditSubItems(*v84) && !v11 )
          {
            CLVThemesManager::DrawThemedFocusRect(
              *(CLVThemesManager **)(v85 + 472),
              *((HDC *)a2 + 11),
              &rcSrc2,
              &rcSrc2);
          }
        }
        else
        {
          v113 = 1;
        }
      }
      if ( (v114 & 0x10) != 0 )
      {
        v90 = *((_DWORD *)a2 + 34);
        v91 = *((_DWORD *)a2 + 35);
        *((_DWORD *)a2 + 35) = v36;
        *((_DWORD *)a2 + 34) = v111;
        SHThemeComputeTextColors(0, v109, (_DWORD)a2 + 136, (_DWORD)a2 + 140, 0);
        v92 = SetTextColor(*((HDC *)a2 + 11), *((_DWORD *)a2 + 34));
        v93 = SetBkColor(*((HDC *)a2 + 11), *((_DWORD *)a2 + 35));
        v94 = (__int64)this[1] + 96;
        if ( (*((_BYTE *)this[1] + 116) & 0x20) != 0 )
        {
          *((_DWORD *)a2 + 20) = 196610;
          CCSendNotify(v94, -12, (LPARAM)a2 + 56);
        }
        SetTextColor(*((HDC *)a2 + 11), v92);
        SetBkColor(*((HDC *)a2 + 11), v93);
        *((_DWORD *)a2 + 34) = v90;
        v7 = 1;
        *((_DWORD *)a2 + 35) = v91;
      }
      if ( h )
        SelectObject(*((HDC *)a2 + 11), h);
      *((_DWORD *)this[1] + 45) = v116;
LABEL_46:
      v12 = v110;
LABEL_47:
      ++v12;
LABEL_48:
      v37 = this[1];
      v110 = v12;
      v38 = *((_QWORD *)v37 + 49);
      if ( v12 >= *(_DWORD *)(v38 + 16) )
      {
        if ( v113 )
          CLVThemesManager::DrawThemedFocusRect(*((CLVThemesManager **)v37 + 59), *((HDC *)a2 + 11), &rcDst, &v139);
        return v7;
      }
      v39 = CLVHeaderControlManager::_GetHDPtr(*((CLVHeaderControlManager **)v37 + 49));
      if ( v39 )
      {
        v40 = v39[21];
        cx = v12;
        sz.cx = v12;
        if ( v40 && v12 >= 0 && v12 < *(_DWORD *)v40 )
        {
          memcpy_0(
            &sz,
            (const void *)(*(_QWORD *)(v40 + 8) + (unsigned int)(v12 * *(_DWORD *)(v40 + 20))),
            *(unsigned int *)(v40 + 20));
          cx = sz.cx;
        }
        v11 = cx;
      }
      else
      {
        v11 = SendMessageW(*(HWND *)v38, 0x120Fu, v12, 0);
      }
    }
    _LISTITEM::InitOwnerData((_LISTITEM *)&v122, v21, v121.iItem, *((_DWORD *)a2 + 12));
LABEL_193:
    v98 = &v122;
    v122 = (LPARAM)v121.pszText;
    goto LABEL_194;
  }
LABEL_133:
  if ( (*((_DWORD *)v6 + 40) & 2) == 0 || *((_WORD *)v6 + 82) == 3 )
    return 0;
  return v7;
}

```

## disassembly

```asm
0x180033630  mov     rax, rsp
0x180033633  mov     [rax+18h], rbx
0x180033637  push    rbp
0x180033638  push    rsi
0x180033639  push    rdi
0x18003363a  push    r12
0x18003363c  push    r13
0x18003363e  push    r14
0x180033640  push    r15
0x180033642  lea     rbp, [rax-3B8h]
0x180033649  sub     rsp, 480h
0x180033650  movaps  xmmword ptr [rax-48h], xmm6
0x180033654  mov     rax, cs:__security_cookie
0x18003365b  xor     rax, rsp
0x18003365e  mov     [rbp+3B0h+var_50], rax
0x180033665  xorps   xmm0, xmm0
0x180033668  xorps   xmm1, xmm1
0x18003366b  mov     rdi, rdx
0x18003366e  mov     rsi, rcx
0x180033671  xor     edx, edx; Val
0x180033673  lea     rcx, [rbp+3B0h+var_3D0]; void *
0x180033677  movups  xmmword ptr [rbp+3B0h+rc.left], xmm0
0x18003367e  movups  xmmword ptr [rbp+3B0h+rcSrc2.left], xmm1
0x180033685  lea     r8d, [rdx+58h]; Size
0x180033689  movups  xmmword ptr [rbp+3B0h+rcSrc1.left], xmm0
0x180033690  movups  xmmword ptr [rbp+3B0h+var_2C8.left], xmm1
0x180033697  movups  xmmword ptr [rbp+3B0h+rcDst.left], xmm0
0x18003369e  call    memset_0
0x1800336a3  xor     edx, edx; Val
0x1800336a5  lea     rcx, [rbp+3B0h+lParam]; void *
0x1800336ac  lea     r8d, [rdx+48h]; Size
0x1800336b0  call    memset_0
0x1800336b5  mov     r8d, [rdi+70h]; int
0x1800336b9  lea     rax, [rbp+3B0h+var_2C8]
0x1800336c0  mov     r9d, [rdi+30h]; int
0x1800336c4  mov     rcx, rsi; this
0x1800336c7  mov     rdx, [rdi+8]; struct CLVDrawState *
0x1800336cb  mov     [rsp+4B0h+lprcDst], rax; lprcDst
0x1800336d0  lea     rax, [rbp+3B0h+rcSrc1]
0x1800336d7  mov     [rsp+4B0h+lprc], rax; lprc
0x1800336dc  mov     [rsp+4B0h+var_488], 0; LPRECT
0x1800336e5  mov     [rsp+4B0h+var_490], 0; struct tagRECT *
0x1800336ee  mov     [rbp+3B0h+var_3D0.iItem], r8d
0x1800336f2  call    ?GetRects@CLVReportView@@QEAAHPEAVCLVDrawState@@HHPEAUtagRECT@@111@Z; CLVReportView::GetRects(CLVDrawState *,int,int,tagRECT *,tagRECT *,tagRECT *,tagRECT *)
0x1800336f7  mov     rcx, [rsi+8]
0x1800336fb  mov     r14d, 1
0x180033701  mov     rax, [rcx+260h]
0x180033708  mov     rax, [rax+10h]
0x18003370c  mov     eax, [rax+14h]
0x18003370f  cmp     [rbp+3B0h+rcSrc1.bottom], eax
0x180033715  jle     loc_180033EE9
0x18003371b  mov     r8, [rdi+18h]; lprcSrc2
0x18003371f  test    r8, r8
0x180033722  jz      short loc_180033750
0x180033724  mov     eax, [r8+0Ch]
0x180033728  cmp     [rbp+3B0h+rcSrc1.top], eax
0x18003372e  jge     loc_1800341A2
0x180033734  lea     rdx, [rbp+3B0h+rcSrc1]; lprcSrc1
0x18003373b  lea     rcx, [rbp+3B0h+rcDst]; lprcDst
0x180033742  call    cs:__imp_IntersectRect
0x180033748  test    eax, eax
0x18003374a  jz      loc_180033EE9
0x180033750  mov     rcx, [rsi+8]
0x180033754  mov     edx, [rbp+3B0h+rcSrc1.top]
0x18003375a  cmp     edx, [rcx+0E0h]
0x180033760  jge     loc_1800341A2
0x180033766  mov     rax, [rdi+10h]
0x18003376a  mov     [rbp+3B0h+var_418], 0
0x180033771  test    rax, rax
0x180033774  jnz     loc_18003467C
0x18003377a  mov     [rbp+3B0h+var_408], eax
0x18003377d  mov     [rbp+3B0h+dy], eax
0x180033780  mov     rax, [rsi+8]
0x180033784  mov     r15d, 3
0x18003378a  mov     [rbp+3B0h+var_3D0.stateMask], 0FFFFh
0x180033791  mov     [rbp+3B0h+var_3D0.state], 0
0x180033798  test    dword ptr [rax+70h], 400h
0x18003379f  jz      loc_180034060
0x1800337a5  xor     r13d, r13d
0x1800337a8  xor     r12d, r12d
0x1800337ab  mov     [rbp+3B0h+var_424], r12d
0x1800337af  jmp     loc_180033A9C
0x1800337b4  bts     r10d, 10h
0x1800337b9  mov     rax, [rbx+158h]
0x1800337c0  mov     [rbp+3B0h+var_428], r10d
0x1800337c4  mov     rcx, [rax+8]
0x1800337c8  test    rcx, rcx
0x1800337cb  jz      loc_180033D4D
0x1800337d1  mov     [rbp+3B0h+var_430], 0FFFFFFFFh
0x1800337d8  cmp     r13d, [rsi+18h]
0x1800337dc  jz      loc_1800341BB
0x1800337e2  cmp     r9d, 0FFFFFFFFh
0x1800337e6  jz      loc_180033E11
0x1800337ec  mov     ebx, 2
0x1800337f1  test    [rdi+20h], bl
0x1800337f4  jnz     loc_18003404B
0x1800337fa  mov     eax, dword ptr [rbp+3B0h+var_410]
0x1800337fd  and     eax, 8
0x180033800  mov     [rbp+3B0h+var_404], eax
0x180033803  jz      loc_180033C77
0x180033809  mov     r10, [rsi+8]
0x18003380d  mov     rcx, r10; this
0x180033810  call    ?IsFullRowSelect@CListView@@QEBA_NXZ; CListView::IsFullRowSelect(void)
0x180033815  test    al, al
0x180033817  jnz     loc_180033D1B
0x18003381d  mov     r9d, [rbp+3B0h+var_428]
0x180033821  mov     eax, r13d
0x180033824  neg     eax
0x180033826  sbb     ecx, ecx
0x180033828  and     ecx, 40h
0x18003382b  add     ecx, 80405h
0x180033831  mov     edx, ecx
0x180033833  bts     edx, 16h
0x180033837  test    byte ptr [rbp+3B0h+var_294], 3
0x18003383e  cmovz   edx, ecx
0x180033841  mov     rcx, r10; this
0x180033844  mov     r12d, edx
0x180033847  bts     r12d, 0Bh
0x18003384c  test    dword ptr [r10+80h], 2000h
0x180033857  cmovz   r12d, edx
0x18003385b  or      r12d, r9d
0x18003385e  call    ?IsFullRowSelect@CListView@@QEBA_NXZ; CListView::IsFullRowSelect(void)
0x180033863  test    al, al
0x180033865  jz      loc_1800342F6
0x18003386b  mov     eax, [rbp+3B0h+rcSrc2.right]
0x180033871  sub     eax, [rsi+24h]
0x180033874  mov     ecx, 1Ah; nIndex
0x180033879  mov     r15d, [rdi+88h]
0x180033880  mov     [rbp+3B0h+rcSrc2.right], eax
0x180033886  mov     [rbp+3B0h+h], 0
0x18003388e  mov     [rbp+3B0h+var_420], r15d
0x180033892  call    cs:__imp_GetSysColor
0x180033898  cmp     r15d, eax
0x18003389b  jz      loc_180033FE6
0x1800338a1  mov     rcx, [rsi+8]
0x1800338a5  mov     eax, [rcx+0B0h]
0x1800338ab  bt      eax, 0Bh
0x1800338af  jb      loc_180033FDE
0x1800338b5  test    r12b, 8
0x1800338b9  jnz     loc_1800346D0
0x1800338bf  mov     r11, [rsi+8]
0x1800338c3  mov     ebx, [rbp+3B0h+var_3D0.iItem]
0x1800338c6  mov     rcx, [r11+1A0h]
0x1800338cd  cmp     qword ptr [rcx+20h], 0
0x1800338d2  jnz     loc_180034476
0x1800338d8  mov     [rbp+3B0h+var_3E0], 0
0x1800338e0  test    r13d, r13d
0x1800338e3  jz      short loc_1800338FF
0x1800338e5  mov     rax, [r11+208h]
0x1800338ec  mov     rcx, [rax]
0x1800338ef  mov     rcx, [rcx+2F0h]
0x1800338f6  test    rcx, rcx
0x1800338f9  jnz     loc_180033F4A
0x1800338ff  mov     eax, dword ptr [rbp+3B0h+var_410]
0x180033902  or      eax, [rdi+34h]
0x180033905  test    al, 2
0x180033907  jz      short loc_180033935
0x180033909  mov     rcx, [rdi+58h]; hdc
0x18003390d  lea     r9, [rbp+3B0h+sz]; lpsz
0x180033914  mov     r8d, 3; c
0x18003391a  mov     qword ptr [rbp+3B0h+sz.cx], 0
0x180033925  lea     rdx, c_szEllipses; "..."
0x18003392c  call    cs:__imp_GetTextExtentPointW
0x180033932  mov     ebx, [rbp+3B0h+var_3D0.iItem]
0x180033935  mov     r15, [rbp+3B0h+var_3D0.pszText]
0x180033939  test    r15, r15
0x18003393c  jz      loc_1800339EC
0x180033942  test    r13d, r13d
0x180033945  jle     loc_18003414B
0x18003394b  cmp     [rbp+3B0h+var_404], 0
0x18003394f  jnz     loc_18003473A
0x180033955  mov     r11, [rsi+8]
0x180033959  mov     r10, [r11+1A0h]
0x180033960  cmp     qword ptr [r10], 0
0x180033964  jnz     loc_1800346EC
0x18003396a  mov     rcx, r10; this
0x18003396d  call    ?IsInSubItemEdit@CLVInPlaceEditingManager@@QEAAHXZ; CLVInPlaceEditingManager::IsInSubItemEdit(void)
0x180033972  test    eax, eax
0x180033974  jnz     loc_1800346EC
0x18003397a  mov     rax, [rdi+8]
0x18003397e  mov     r10d, [rbp+3B0h+var_430]
0x180033982  mov     rcx, [r11+178h]; this
0x180033989  mov     r9, [rdi+58h]; HDC
0x18003398d  mov     edx, [rax+14h]; struct CLVDrawState *
0x180033990  mov     eax, [rbp+3B0h+var_294]
0x180033996  mov     r8, [rcx]
0x180033999  and     eax, 3
0x18003399c  mov     [rsp+4B0h+var_440], r10d; unsigned int
0x1800339a1  mov     r10d, [rbp+3B0h+var_420]
0x1800339a5  mov     [rsp+4B0h+var_448], r10d; unsigned int
0x1800339aa  cmp     dword ptr [r8+30h], 0
0x1800339af  mov     [rsp+4B0h+var_458], edx; int
0x1800339b3  mov     [rsp+4B0h+var_460], r12d; unsigned int
0x1800339b8  mov     [rsp+4B0h+var_468], eax; int
0x1800339bc  lea     rax, [rbp+3B0h+rcSrc2]
0x1800339c3  mov     [rsp+4B0h+var_470], rax; int
0x1800339c8  mov     [rsp+4B0h+lprcDst], r15; unsigned __int16 *
0x1800339cd  mov     [rsp+4B0h+lprc], 0; struct _DTTOPTS *
0x1800339d6  mov     dword ptr [rsp+4B0h+var_490], 0; int
0x1800339de  jnz     loc_18003457C
0x1800339e4  xor     r8d, r8d; void *
0x1800339e7  call    ?ThemeDrawText@CLVDrawItemManager@@QEAAXPEAVCLVDrawState@@PEAXPEAUHDC__@@HHPEAU_DTTOPTS@@PEBGPEBUtagRECT@@HIHHKK@Z; CLVDrawItemManager::ThemeDrawText(CLVDrawState *,void *,HDC__ *,int,int,_DTTOPTS *,ushort const *,tagRECT const *,int,uint,int,int,ulong,ulong)
0x1800339ec  mov     r12d, [rbp+3B0h+var_430]
0x1800339f0  test    byte ptr [rbp+3B0h+var_42C], 8
0x1800339f4  jnz     loc_180034285
0x1800339fa  test    byte ptr [rbp+3B0h+var_410], 10h
0x1800339fe  jnz     loc_1800343A6
0x180033a04  mov     rax, [rbp+3B0h+h]
0x180033a08  test    rax, rax
0x180033a0b  jnz     loc_1800347C1
0x180033a11  mov     rax, [rsi+8]
0x180033a15  mov     r15d, 3
0x180033a1b  mov     ecx, [rbp+3B0h+var_400]
0x180033a1e  mov     [rax+0B4h], ecx
0x180033a24  mov     r12d, [rbp+3B0h+var_424]
0x180033a28  add     r12d, r14d
0x180033a2b  mov     rcx, [rsi+8]
0x180033a2f  mov     [rbp+3B0h+var_424], r12d
0x180033a33  mov     rbx, [rcx+188h]
0x180033a3a  cmp     r12d, [rbx+10h]
0x180033a3e  jge     loc_18003411E
0x180033a44  mov     rcx, rbx; this
0x180033a47  call    ?_GetHDPtr@CLVHeaderControlManager@@IEBAPEAXXZ; CLVHeaderControlManager::_GetHDPtr(void)
0x180033a4c  mov     rcx, rax
0x180033a4f  test    rax, rax
0x180033a52  jz      loc_180033DF5
0x180033a58  mov     rcx, [rcx+0A8h]
0x180033a5f  mov     eax, r12d
0x180033a62  mov     [rbp+3B0h+sz.cx], eax
0x180033a68  test    rcx, rcx
0x180033a6b  jz      short loc_180033A99
0x180033a6d  test    r12d, r12d
0x180033a70  js      short loc_180033A99
0x180033a72  cmp     r12d, [rcx]
0x180033a75  jge     short loc_180033A99
0x180033a77  mov     eax, [rcx+14h]
0x180033a7a  mov     r8d, eax; Size
0x180033a7d  imul    eax, r12d
0x180033a81  mov     edx, eax
0x180033a83  add     rdx, [rcx+8]; Src
0x180033a87  lea     rcx, [rbp+3B0h+sz]; void *
0x180033a8e  call    memcpy_0
0x180033a93  mov     eax, [rbp+3B0h+sz.cx]
0x180033a99  mov     r13d, eax
0x180033a9c  mov     rcx, [rsi+8]; this
0x180033aa0  test    r13d, r13d
0x180033aa3  jnz     loc_180033D78
0x180033aa9  mov     eax, [rcx+0B4h]
0x180033aaf  mov     [rbp+3B0h+var_400], eax
0x180033ab2  mov     eax, r13d
0x180033ab5  neg     eax
0x180033ab7  mov     [rbp+3B0h+var_3D0.iImage], 0FFFFFFFFh
0x180033abe  mov     eax, [rdi+30h]
0x180033ac1  sbb     edx, edx
0x180033ac3  mov     [rbp+3B0h+var_3D0.iGroup], eax
0x180033ac6  and     edx, 0FFFFFFECh
0x180033ac9  mov     [rbp+3B0h+var_3D0.iSubItem], r13d
0x180033acd  add     edx, 1Fh
0x180033ad0  mov     [rbp+3B0h+var_3D0.cchTextMax], 104h
0x180033ad7  mov     [rbp+3B0h+var_3D0.mask], edx
0x180033ada  lea     rax, [rbp+3B0h+var_260]
0x180033ae1  mov     [rbp+3B0h+var_3D0.pszText], rax
0x180033ae5  lea     rdx, [rbp+3B0h+var_3D0]; struct tagLVITEMW *
0x180033ae9  mov     rcx, [rcx+200h]; this
0x180033af0  call    ?OnGetItem@CLVItemStore@@QEAAHPEAUtagLVITEMW@@@Z; CLVItemStore::OnGetItem(tagLVITEMW *)
0x180033af5  mov     rax, [rsi+8]
0x180033af9  mov     dword ptr [rbp+3B0h+lParam], 5
0x180033b03  mov     rbx, [rax+188h]
0x180033b0a  mov     rcx, rbx; this
0x180033b0d  call    ?_GetHDPtr@CLVHeaderControlManager@@IEBAPEAXXZ; CLVHeaderControlManager::_GetHDPtr(void)
0x180033b12  test    rax, rax
0x180033b15  jz      loc_180033C5A
0x180033b1b  lea     r8, [rbp+3B0h+lParam]; struct _HD_ITEMW *
0x180033b22  mov     edx, r13d; int
0x180033b25  mov     rcx, rax; struct HD *
0x180033b28  call    ?Header_OnGetItem@@YAHPEAUHD@@HPEAU_HD_ITEMW@@@Z; Header_OnGetItem(HD *,int,_HD_ITEMW *)
0x180033b2d  test    r13d, r13d
0x180033b30  jz      loc_180033E22
0x180033b36  mov     r12d, [rdi+20h]
0x180033b3a  lea     rax, [rbp+3B0h+rcSrc2]
0x180033b41  mov     r8d, [rdi+30h]; int
0x180033b45  mov     r9d, r13d; int
0x180033b48  mov     edx, [rbp+3B0h+var_3D0.iItem]; int
0x180033b4b  mov     rcx, rsi; this
0x180033b4e  mov     [rsp+4B0h+var_488], rax; LPRECT
0x180033b53  lea     rax, [rbp+3B0h+rc]
0x180033b5a  mov     [rsp+4B0h+var_490], rax; lprc
0x180033b5f  mov     dword ptr [rbp+3B0h+var_410], 0
0x180033b66  mov     [rbp+3B0h+var_42C], r12d
0x180033b6a  call    ?GetRectsEx@CLVReportView@@QEAAXHHHPEAUtagRECT@@0@Z; CLVReportView::GetRectsEx(int,int,int,tagRECT *,tagRECT *)
0x180033b6f  cmp     [rbp+3B0h+var_424], 0
0x180033b73  jg      loc_180033D9A
0x180033b79  mov     r8d, [rbp+3B0h+dy]; dy
0x180033b7d  lea     rcx, [rbp+3B0h+rc]; lprc
0x180033b84  mov     edx, [rbp+3B0h+var_408]; dx
0x180033b87  call    cs:__imp_OffsetRect
0x180033b8d  mov     r8d, [rbp+3B0h+dy]; dy
0x180033b91  lea     rcx, [rbp+3B0h+rcSrc2]; lprc
0x180033b98  mov     edx, [rbp+3B0h+var_408]; dx
0x180033b9b  call    cs:__imp_OffsetRect
  ... truncated ...
```
