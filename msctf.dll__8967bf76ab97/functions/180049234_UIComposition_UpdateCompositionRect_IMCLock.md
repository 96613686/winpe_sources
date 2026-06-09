# UIComposition::UpdateCompositionRect(IMCLock &)

- ea: `0x180049234`
- end: `0x180049cf3`
- name: `?UpdateCompositionRect@UIComposition@@AEAAJAEAVIMCLock@@@Z`
- size: `2751`
- prototype: `__int64 __fastcall(UIComposition *__hidden this, struct IMCLock *)`
- caller_count: `4`
- callee_count: `32`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001a9e0`
- `0x180047a70`
- `0x18008c58c`
- `0x1800e3960`

## callees

- `0x180015850`
- `0x1800185f0`
- `0x18001cc80`
- `0x18003a8b0`
- `0x18003d290`
- `0x180045520`
- `0x180045578`
- `0x1800458f0`
- `0x180045cd0`
- `0x18004683c`
- `0x180046b3c`
- `0x180046db8`
- `0x180049234`
- `0x180049ddc`
- `0x18004d850`
- `0x18005221c`
- `0x180065f08`
- `0x18006bd54`
- `0x18006bde4`
- `0x18006f880`
- `0x18006f98c`
- `0x180075154`
- `0x180078a08`
- `0x18007c01c`
- `0x18008bab0`
- `0x18009eac6`
- `0x1800e2884`
- `0x1800e2974`
- `0x1800e29c4`
- `0x1800e349c`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `USER32!SendMessageW` at `0x180049677`
- `USER32!SendMessageW` at `0x180049677`
- `USER32!UnionRect` at `0x180049a21`
- `USER32!UnionRect` at `0x180049a21`
- `USER32!SetWindowPos` at `0x1800499b6`
- `USER32!SetWindowPos` at `0x1800499b6`
- `USER32!ShowWindow` at `0x18004962f`
- `USER32!ShowWindow` at `0x180049afe`
- `USER32!ShowWindow` at `0x180049bc0`
- `USER32!ShowWindow` at `0x180049bf5`
- `USER32!ShowWindow` at `0x18004962f`
- `USER32!ShowWindow` at `0x180049afe`
- `USER32!ShowWindow` at `0x180049bc0`
- `USER32!ShowWindow` at `0x180049bf5`
- `USER32!ClientToScreen` at `0x1800496e0`
- `USER32!ClientToScreen` at `0x1800496e0`
- `USER32!InvalidateRect` at `0x180049603`
- `USER32!InvalidateRect` at `0x180049b37`
- `USER32!InvalidateRect` at `0x180049603`
- `USER32!InvalidateRect` at `0x180049b37`
- `USER32!ReleaseDC` at `0x1800495f1`
- `USER32!ReleaseDC` at `0x180049b27`
- `USER32!ReleaseDC` at `0x1800495f1`
- `USER32!ReleaseDC` at `0x180049b27`
- `USER32!GetDC` at `0x1800493b3`
- `USER32!GetDC` at `0x18004986f`
- `USER32!GetDC` at `0x1800493b3`
- `USER32!GetDC` at `0x18004986f`
- `USER32!MapWindowPoints` at `0x1800496fc`
- `USER32!MapWindowPoints` at `0x1800496fc`
- `USER32!GetClientRect` at `0x1800496cf`
- `USER32!GetClientRect` at `0x1800496cf`
- `USER32!GetSystemMetrics` at `0x1800493e7`
- `USER32!GetSystemMetrics` at `0x1800493fc`
- `USER32!GetSystemMetrics` at `0x1800493e7`
- `USER32!GetSystemMetrics` at `0x1800493fc`
- `USER32!IsRectEmpty` at `0x1800499f1`
- `USER32!IsRectEmpty` at `0x180049c4f`
- `USER32!IsRectEmpty` at `0x1800499f1`
- `USER32!IsRectEmpty` at `0x180049c4f`
- `USER32!IsWindow` at `0x180049288`
- `USER32!IsWindow` at `0x180049377`
- `USER32!IsWindow` at `0x18004961e`
- `USER32!IsWindow` at `0x18004985c`
- `USER32!IsWindow` at `0x180049baf`
- `USER32!IsWindow` at `0x180049be2`
- `USER32!IsWindow` at `0x180049288`
- `USER32!IsWindow` at `0x180049377`
- `USER32!IsWindow` at `0x18004961e`
- `USER32!IsWindow` at `0x18004985c`
- `USER32!IsWindow` at `0x180049baf`
- `USER32!IsWindow` at `0x180049be2`
- `USER32!PtInRect` at `0x18004970d`
- `USER32!PtInRect` at `0x18004970d`
- `GDI32!SelectObject` at `0x1800493c6`
- `GDI32!SelectObject` at `0x1800495e1`
- `GDI32!SelectObject` at `0x180049886`
- `GDI32!SelectObject` at `0x180049b18`
- `GDI32!SelectObject` at `0x1800493c6`
- `GDI32!SelectObject` at `0x1800495e1`
- `GDI32!SelectObject` at `0x180049886`
- `GDI32!SelectObject` at `0x180049b18`
- `GDI32!GetTextExtentPoint32W` at `0x1800493dd`
- `GDI32!GetTextExtentPoint32W` at `0x1800493dd`

## string_xrefs

- `0x180049292`: `UIComposition::UpdateCompositionRect. imc->hWNd==NULL`
- `0x180049cb6`: `UIComposition::UpdateCompositionRect. imc==NULL`
- `0x180049c95`: `UIComposition::UpdateCompositionRect. comp==NULL`

## pseudocode

```c
__int64 __fastcall UIComposition::UpdateCompositionRect(UIComposition *this, struct IMCLock *a2)
{
  HWND *v3; // rcx
  int v5; // ebx
  UIComposition *v7; // rcx
  _DWORD *v8; // rsi
  unsigned __int16 *CompStrBuffer; // rax
  const WCHAR *v10; // r12
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int LevelFromIMC; // eax
  int v15; // r15d
  HWND v16; // rcx
  HDC DC; // r13
  int v18; // r12d
  int v19; // r8d
  int v20; // eax
  CDefCompFrameWindow *v21; // rcx
  int v22; // eax
  char *v23; // rbx
  tagSIZE v24; // rbx
  HGDIOBJ v25; // rdx
  unsigned int i; // ebx
  CCompButtonFrameWindow *v27; // rcx
  HWND *v28; // rcx
  __int64 v29; // rcx
  unsigned int v30; // eax
  char *v31; // rax
  unsigned __int8 *v32; // r9
  struct TLS *TLS; // rax
  CicProfile *v34; // rcx
  LONG top; // esi
  int v36; // r9d
  int v37; // ebx
  int j; // r12d
  __int64 v39; // r13
  HWND v40; // rcx
  HDC v41; // rax
  void *v42; // rdx
  HDC v43; // rsi
  HGDIOBJ v44; // rax
  UIComposition *v45; // rcx
  unsigned int v46; // eax
  unsigned int v47; // esi
  int v48; // eax
  int v49; // r9d
  int v50; // edx
  int v51; // ecx
  int cy; // r8d
  int v53; // ebx
  int v54; // ecx
  int v55; // eax
  unsigned int v56; // r9d
  int v57; // edx
  int v58; // ecx
  int v59; // r8d
  __int64 v60; // rbx
  __int64 v61; // rcx
  CCompButtonFrameWindow *v62; // rcx
  int Y; // [rsp+60h] [rbp-A0h] BYREF
  int c; // [rsp+64h] [rbp-9Ch] BYREF
  int v65; // [rsp+68h] [rbp-98h]
  int v66; // [rsp+6Ch] [rbp-94h] BYREF
  int v67; // [rsp+70h] [rbp-90h]
  int v68; // [rsp+74h] [rbp-8Ch]
  int v69; // [rsp+78h] [rbp-88h] BYREF
  int v70; // [rsp+7Ch] [rbp-84h]
  int X; // [rsp+80h] [rbp-80h]
  HGDIOBJ h; // [rsp+88h] [rbp-78h] BYREF
  int v73; // [rsp+90h] [rbp-70h]
  unsigned int v74; // [rsp+94h] [rbp-6Ch]
  unsigned __int8 *v75; // [rsp+98h] [rbp-68h]
  struct tagSIZE psizl; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v77; // [rsp+A8h] [rbp-58h]
  void **v78; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v79; // [rsp+B8h] [rbp-48h]
  int v80; // [rsp+C0h] [rbp-40h]
  HDC hdc[2]; // [rsp+C8h] [rbp-38h] BYREF
  HGDIOBJ v82; // [rsp+D8h] [rbp-28h]
  void **v83; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD *v84; // [rsp+E8h] [rbp-18h]
  int v85; // [rsp+F8h] [rbp-8h]
  __int128 v86; // [rsp+100h] [rbp+0h]
  __int128 v87; // [rsp+110h] [rbp+10h]
  __int128 v88; // [rsp+120h] [rbp+20h]
  struct tagPOLYTEXTW v89; // [rsp+140h] [rbp+40h] BYREF
  struct tagRECT Rect; // [rsp+180h] [rbp+80h] BYREF
  RECT rc; // [rsp+190h] [rbp+90h] BYREF
  RECT rcSrc2; // [rsp+1A0h] [rbp+A0h] BYREF

  v3 = (HWND *)*((_QWORD *)a2 + 1);
  if ( !v3 )
  {
    v5 = -2147467259;
    goto LABEL_117;
  }
  v5 = *((_DWORD *)a2 + 6);
  if ( v5 < 0 )
  {
LABEL_117:
    CicTrace(2u, "UIComposition::UpdateCompositionRect. imc==NULL");
    return (unsigned int)v5;
  }
  if ( !IsWindow(*v3) )
  {
    CicTrace(2u, "UIComposition::UpdateCompositionRect. imc->hWNd==NULL");
    return 2147500037LL;
  }
  InternalIMCCLock::InternalIMCCLock((InternalIMCCLock *)&v83, *(HIMCC *)(*((_QWORD *)a2 + 1) + 288LL));
  v8 = v84;
  v83 = &IMCCLock<tagCANDIDATEINFO>::`vftable';
  if ( !v84 )
  {
    v5 = -2147467259;
    goto LABEL_114;
  }
  v5 = v85;
  if ( v85 < 0 )
  {
LABEL_114:
    CicTrace(2u, "UIComposition::UpdateCompositionRect. comp==NULL");
    goto LABEL_115;
  }
  v66 = 0;
  v69 = 0;
  UIComposition::GetSelection(v7, a2, &v66, &v69);
  c = 0;
  UIComposition::UpdateShowCompWndFlag(this, a2, (unsigned int *)&c);
  CompStrBuffer = UIComposition::GetCompStrBuffer(this, v8[11]);
  v77 = CompStrBuffer;
  v10 = CompStrBuffer;
  if ( !CompStrBuffer )
  {
    v5 = -2147024882;
LABEL_115:
    InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v83);
    return (unsigned int)v5;
  }
  v11 = c;
  v12 = (unsigned int)v8[12];
  v70 = c;
  memcpy_0(CompStrBuffer, (char *)v8 + v12, 2LL * (unsigned int)c);
  v73 = *((_DWORD *)this + 164);
  LevelFromIMC = UIComposition::GetLevelFromIMC(v13, a2);
  v15 = 1;
  if ( LevelFromIMC == 1 )
  {
    if ( IsWindow(*((HWND *)this + 57)) )
    {
      v16 = (HWND)*((_QWORD *)this + 57);
      *(_QWORD *)&v87 = v10;
      v86 = 0;
      DWORD2(v86) = v11;
      *((_QWORD *)&v87 + 1) = 2;
      v75 = 0;
      v88 = 0;
      psizl = 0;
      DC = GetDC(v16);
      h = SelectObject(DC, *((HGDIOBJ *)this + 75));
      GetTextExtentPoint32W(DC, v10, v11, &psizl);
      v18 = psizl.cx + 2 * GetSystemMetrics(45);
      DWORD1(v88) = v18;
      v19 = psizl.cy + 2 * GetSystemMetrics(46);
      v20 = v8[13];
      DWORD2(v88) = v19;
      v68 = v20;
      v65 = v20 == v11;
      v21 = (CDefCompFrameWindow *)*((_QWORD *)this + 83);
      if ( v21 )
      {
        v22 = v20 == v11 ? 2 * *((_DWORD *)this + 157) : 0;
        CDefCompFrameWindow::SetCompStrRect(v21, v18 + v22, v19 + 2, -(*((_DWORD *)this + 164) & 1));
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImeCompositionWindowLifeTimeTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ImeCompositionWindowLifeTimeTest>::GetImpl'::`2'::impl) )
        {
          if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_CompositionWindowLifeTimeTest,_tip_CompositionWindowLifeTimeTest>>::operator bool((char *)this + 776)
            && (*((_BYTE *)this + 656) & 1) != 0 )
          {
            *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CompositionWindowLifeTimeTest,_tip_CompositionWindowLifeTimeTest>>::operator->(
                                    (char *)this + 776,
                                    hdc)
                     + 280LL) = 1;
            tip2::test_data_control<tip2::details::merged_data<_tip_CompositionWindowLifeTimeTest,_tip_CompositionWindowLifeTimeTest>>::~test_data_control<tip2::details::merged_data<_tip_CompositionWindowLifeTimeTest,_tip_CompositionWindowLifeTimeTest>>(hdc);
          }
        }
      }
      if ( v8[23] < 0x10u )
        v23 = 0;
      else
        v23 = (char *)v8 + (unsigned int)v8[24];
      CPolyText::RemoveAll((UIComposition *)((char *)this + 464));
      if ( v23 )
      {
        v24 = (tagSIZE)&v23[*((unsigned int *)v23 + 3)];
        v79 = 0;
        v80 = 0;
        v78 = &CCompClauseStore::`vftable';
        CCompClauseStore::Set((CCompClauseStore *)&v78);
        *(_OWORD *)&v89.x = v86;
        *(_OWORD *)&v89.lpstr = v87;
        *(_OWORD *)&v89.rcl.top = v88;
        v89.pdx = (int *)v75;
        CPolyText::SplitPolyStringAndAttr(
          (UIComposition *)((char *)this + 464),
          a2,
          DC,
          &v89,
          v24,
          (struct CCompClauseStore *)&v78);
        v78 = &CCompClauseStore::`vftable';
        CCompClauseStore::ClearString((CCompClauseStore *)&v78);
      }
      else
      {
        *(_OWORD *)&v89.x = v86;
        *(_OWORD *)&v89.lpstr = v87;
        *(_OWORD *)&v89.rcl.top = v88;
        v89.pdx = (int *)v75;
        CPolyText::AppendPolyStringAndAttr((UIComposition *)((char *)this + 464), &v89, 0);
      }
      if ( v68 <= (unsigned int)c )
        UIComposition::SetCaretPos(
          (UIComposition *)(unsigned int)c,
          DC,
          (UIComposition *)((char *)this + 536),
          0,
          0,
          v77,
          c,
          v8[13],
          0,
          v65);
      v25 = h;
      *((_DWORD *)this + 146) = v66;
      *((_DWORD *)this + 147) = v69;
      SelectObject(DC, v25);
      ReleaseDC(*((HWND *)this + 57), DC);
      InvalidateRect(*((HWND *)this + 57), 0, 0);
    }
    for ( i = 0; i < 3; ++i )
    {
      if ( IsWindow(*((HWND *)this + 18 * (int)i + 3)) )
        ShowWindow(*((HWND *)this + 18 * (int)i + 3), 0);
    }
    v27 = (CCompButtonFrameWindow *)*((_QWORD *)this + 84);
    if ( v27 )
      CCompButtonFrameWindow::MoveShow(v27, 0, 0, 0);
    goto LABEL_34;
  }
  if ( LevelFromIMC == 2 )
  {
    v29 = *((_QWORD *)a2 + 1);
    psizl = *(struct tagSIZE *)(v29 + 132);
    Rect = 0;
    if ( (*(_BYTE *)(v29 + 128) & 1) != 0 )
      Rect = *(struct tagRECT *)(v29 + 140);
    else
      GetClientRect(*(HWND *)v29, &Rect);
    ClientToScreen(**((HWND **)a2 + 1), (LPPOINT)&psizl);
    MapWindowPoints(**((HWND **)a2 + 1), 0, (LPPOINT)&Rect, 2u);
    if ( !PtInRect(&Rect, (POINT)psizl) )
      goto LABEL_43;
    v30 = v8[13];
    v78 = &CCompClauseStore::`vftable';
    v74 = v30;
    v79 = 0;
    v80 = 0;
    CCompClauseStore::Set((CCompClauseStore *)&v78);
    if ( v8[23] < 0x10u )
      v31 = 0;
    else
      v31 = (char *)v8 + (unsigned int)v8[24];
    rc = 0;
    if ( v31 )
    {
      v32 = (unsigned __int8 *)&v31[*((unsigned int *)v31 + 3)];
      c = 1;
      v75 = v32;
    }
    else
    {
      TLS = TLS::GetTLS();
      if ( !TLS
        || (v34 = (CicProfile *)*((_QWORD *)TLS + 1)) == 0
        || (LOWORD(Y) = 0, CicProfile::GetLangId(v34, (unsigned __int16 *)&Y), (Y & 0x3FF) != 0x12) )
      {
        v78 = &CCompClauseStore::`vftable';
        CCompClauseStore::ClearString((CCompClauseStore *)&v78);
LABEL_43:
        v5 = -2147467259;
        goto LABEL_115;
      }
      v75 = 0;
      c = 0;
    }
    top = psizl.cy;
    v68 = 0;
    v67 = 0;
    v73 = -(v73 & 1);
    v65 = 0;
    X = psizl.cx;
    Y = psizl.cy;
    if ( (unsigned int)IMCLock::UseVerticalCompWindow(a2) )
      v37 = Rect.bottom - top;
    else
      v37 = Rect.right - v36;
    for ( j = 0; (unsigned int)j < 3; ++j )
    {
      if ( !v70 )
        break;
      v39 = 144LL * j;
      CCaret::HideCaret((UIComposition *)((char *)this + v39 + 104));
      CPolyText::RemoveAll((UIComposition *)((char *)this + v39 + 32));
      v40 = *(HWND *)((char *)this + v39 + 24);
      *(_QWORD *)((char *)this + v39 + 152) = 0;
      h = 0;
      if ( IsWindow(v40) )
      {
        v41 = GetDC(*(HWND *)((char *)this + v39 + 24));
        v42 = (void *)*((_QWORD *)this + 77);
        v43 = v41;
        hdc[0] = v41;
        v44 = SelectObject(v41, v42);
        v45 = (UIComposition *)((char *)this + v39 + 32);
        v82 = v44;
        if ( j == 1 )
          v46 = UIComposition::CalcMultiTextExtentPoint(
                  v45,
                  a2,
                  v43,
                  v77,
                  v70,
                  v75,
                  c,
                  (struct CCompClauseStore *)&v78,
                  v37,
                  (struct tagSIZE *)&h,
                  (UIComposition *)((char *)this + v39 + 32));
        else
          v46 = UIComposition::CalcSingleTextExtentPoint(
                  v45,
                  a2,
                  v43,
                  v77,
                  v70,
                  v75,
                  c,
                  (struct CCompClauseStore *)&v78,
                  v37,
                  (struct tagSIZE *)&h,
                  (UIComposition *)((char *)this + v39 + 32),
                  0);
        v47 = v46;
        if ( v46 )
        {
          v68 = v74 == v46;
          v48 = IMCLock::UseVerticalCompWindow(a2);
          v50 = X;
          if ( v48 )
          {
            v53 = (int)h;
            v50 = X - (_DWORD)h;
            v67 = X - (_DWORD)h;
            if ( v49 == v47 )
              v54 = *((_DWORD *)this + 158);
            else
              v54 = 0;
            cy = v54 + HIDWORD(h);
          }
          else
          {
            v67 = X;
            if ( v49 == v47 )
              v51 = *((_DWORD *)this + 157);
            else
              v51 = 0;
            cy = HIDWORD(h);
            v53 = v51 + (_DWORD)h;
          }
          v65 = cy;
          SetWindowPos(*(HWND *)((char *)this + v39 + 24), 0, v50, Y, v53, cy, v73 != 0 ? 1620 : 1684);
          if ( v73 )
          {
            rcSrc2.left = v67;
            rcSrc2.right = v53 + v67;
            rcSrc2.top = Y;
            rcSrc2.bottom = Y + v65;
            if ( IsRectEmpty(&rc) )
              rc = rcSrc2;
            else
              UnionRect(&rc, &rc, &rcSrc2);
          }
          if ( v74 > v47 )
          {
            v74 -= v47;
          }
          else
          {
            v55 = IMCLock::UseVerticalCompWindow(a2);
            UIComposition::UpdateCaretRect(this, hdc[0], j, v56, v55, v68);
            v74 = -1;
          }
          v57 = v69;
          v58 = v66;
          if ( v69 && v66 < (int)v47 )
          {
            *(_DWORD *)((char *)this + v39 + 152) = v66;
            v59 = v57;
            if ( v57 + v58 > (int)v47 )
              v57 = v47 - v58;
            *(_DWORD *)((char *)this + v39 + 156) = v57;
            v69 = v59 - v57;
            if ( v59 - v57 < 0 )
              v69 = 0;
          }
          v70 -= v47;
          v68 = v53 + v67;
          v67 = Y;
          v65 = 1;
          v77 += v47;
          if ( c )
          {
            v75 += v47;
            CCompClauseStore::Shift((CCompClauseStore *)&v78, v47);
            v58 = v66;
          }
          v66 = v58 - v47;
          if ( (int)(v58 - v47) < 0 )
            v66 = 0;
        }
        else
        {
          ShowWindow(*(HWND *)((char *)this + v39 + 24), 0);
          CPolyText::RemoveAll((UIComposition *)((char *)this + v39 + 32));
        }
        SelectObject(hdc[0], v82);
        ReleaseDC(*(HWND *)((char *)this + v39 + 24), hdc[0]);
        InvalidateRect(*(HWND *)((char *)this + v39 + 24), 0, 0);
        top = Y;
      }
      if ( (unsigned int)IMCLock::UseVerticalCompWindow(a2) )
      {
        top = Rect.top;
        v37 = Rect.bottom - Rect.top;
        X -= (int)h;
        Rect.left -= (int)h;
      }
      else
      {
        top += HIDWORD(h);
        v37 = Rect.right - Rect.left;
        X = Rect.left;
        Rect.top += HIDWORD(h);
      }
      Y = top;
    }
    while ( (unsigned int)j < 3 )
    {
      v60 = 144LL * j;
      if ( IsWindow(*(HWND *)((char *)this + v60 + 24)) )
        ShowWindow(*(HWND *)((char *)this + v60 + 24), 0);
      CPolyText::RemoveAll((UIComposition *)((char *)this + v60 + 32));
      ++j;
    }
    if ( IsWindow(*((HWND *)this + 57)) )
      ShowWindow(*((HWND *)this + 57), 0);
    v61 = *((_QWORD *)this + 83);
    if ( v61 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v61 + 296LL))(v61, 0);
    v62 = (CCompButtonFrameWindow *)*((_QWORD *)this + 84);
    if ( v62 )
    {
      if ( (*((_BYTE *)this + 656) & 1) == 0 || !v65 )
        v15 = 0;
      CCompButtonFrameWindow::MoveShow(v62, v68, v67, v15);
    }
    if ( !IsRectEmpty(&rc) )
      SetLevel2CompositionRect(&rc);
    v78 = &CCompClauseStore::`vftable';
    CCompClauseStore::ClearString((CCompClauseStore *)&v78);
  }
LABEL_34:
  v28 = (HWND *)*((_QWORD *)a2 + 1);
  if ( v28 )
  {
    if ( *((int *)a2 + 6) >= 0 )
      SendMessageW(*v28, 0x282u, 0xFu, *((_QWORD *)a2 + 2));
  }
  InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v83);
  return 0;
}

```

## disassembly

```asm
0x180049234  mov     [rsp-8+arg_10], rbx
0x180049239  push    rbp
0x18004923a  push    rsi
0x18004923b  push    rdi
0x18004923c  push    r12
0x18004923e  push    r13
0x180049240  push    r14
0x180049242  push    r15
0x180049244  lea     rbp, [rsp-0C0h]
0x18004924c  sub     rsp, 1C0h
0x180049253  mov     rax, cs:__security_cookie
0x18004925a  xor     rax, rsp
0x18004925d  mov     [rbp+0F0h+var_40], rax
0x180049264  mov     rdi, rcx
0x180049267  xor     r13d, r13d
0x18004926a  mov     rcx, [rdx+8]
0x18004926e  mov     r14, rdx
0x180049271  test    rcx, rcx
0x180049274  jz      loc_180049CB1
0x18004927a  mov     ebx, [rdx+18h]
0x18004927d  test    ebx, ebx
0x18004927f  js      loc_180049CB6
0x180049285  mov     rcx, [rcx]; hWnd
0x180049288  call    cs:__imp_IsWindow
0x18004928e  test    eax, eax
0x180049290  jnz     short loc_1800492AB
0x180049292  lea     rdx, aUicompositionU_1; "UIComposition::UpdateCompositionRect. i"...
0x180049299  lea     ecx, [rax+2]; unsigned int
0x18004929c  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x1800492a1  mov     eax, 80004005h
0x1800492a6  jmp     loc_180049CC9
0x1800492ab  mov     rdx, [r14+8]
0x1800492af  lea     rcx, [rbp+0F0h+var_110]; this
0x1800492b3  mov     rdx, [rdx+120h]; HIMCC
0x1800492ba  call    ??0InternalIMCCLock@@QEAA@PEAUHIMCC__@@@Z; InternalIMCCLock::InternalIMCCLock(HIMCC__ *)
0x1800492bf  mov     rsi, [rbp+0F0h+var_108]
0x1800492c3  lea     rax, ??_7?$IMCCLock@UtagCANDIDATEINFO@@@@6B@; const IMCCLock<tagCANDIDATEINFO>::`vftable'
0x1800492ca  mov     [rbp+0F0h+var_110], rax
0x1800492ce  test    rsi, rsi
0x1800492d1  jz      loc_180049C90
0x1800492d7  mov     ebx, [rbp+0F0h+var_F8]
0x1800492da  test    ebx, ebx
0x1800492dc  js      loc_180049C95
0x1800492e2  lea     r9, [rsp+1F0h+var_178]; int *
0x1800492e7  mov     [rsp+1F0h+var_184], r13d
0x1800492ec  lea     r8, [rsp+1F0h+var_184]; int *
0x1800492f1  mov     [rsp+1F0h+var_178], r13d
0x1800492f6  mov     rdx, r14; struct IMCLock *
0x1800492f9  call    ?GetSelection@UIComposition@@QEAAJAEAVIMCLock@@PEAJ1@Z; UIComposition::GetSelection(IMCLock &,long *,long *)
0x1800492fe  lea     r8, [rsp+1F0h+c]; unsigned int *
0x180049303  mov     [rsp+1F0h+c], r13d
0x180049308  mov     rdx, r14; struct IMCLock *
0x18004930b  mov     rcx, rdi; this
0x18004930e  call    ?UpdateShowCompWndFlag@UIComposition@@AEAAJAEAVIMCLock@@PEAK@Z; UIComposition::UpdateShowCompWndFlag(IMCLock &,ulong *)
0x180049313  mov     edx, [rsi+2Ch]; int
0x180049316  mov     rcx, rdi; this
0x180049319  call    ?GetCompStrBuffer@UIComposition@@AEAAPEAGH@Z; UIComposition::GetCompStrBuffer(int)
0x18004931e  mov     [rbp+0F0h+var_148], rax
0x180049322  mov     r12, rax
0x180049325  test    rax, rax
0x180049328  jnz     short loc_180049334
0x18004932a  mov     ebx, 8007000Eh
0x18004932f  jmp     loc_180049CA6
0x180049334  mov     ebx, [rsp+1F0h+c]
0x180049338  mov     rcx, r12; void *
0x18004933b  mov     edx, [rsi+30h]
0x18004933e  mov     r8d, ebx
0x180049341  add     r8, r8; Size
0x180049344  mov     [rsp+1F0h+var_174], ebx
0x180049348  add     rdx, rsi; Src
0x18004934b  call    memcpy_0
0x180049350  mov     eax, [rdi+290h]
0x180049356  mov     rdx, r14
0x180049359  mov     [rbp+0F0h+var_160], eax
0x18004935c  call    ?GetLevelFromIMC@UIComposition@@AEAA?AW4IME_UIWND_STATE@@AEAVIMCLock@@@Z; UIComposition::GetLevelFromIMC(IMCLock &)
0x180049361  mov     r15d, 1
0x180049367  cmp     eax, r15d
0x18004936a  jnz     loc_18004968D
0x180049370  mov     rcx, [rdi+1C8h]; hWnd
0x180049377  call    cs:__imp_IsWindow
0x18004937d  test    eax, eax
0x18004937f  jz      loc_18004960C
0x180049385  mov     rcx, [rdi+1C8h]; hWnd
0x18004938c  xorps   xmm0, xmm0
0x18004938f  movups  [rbp+0F0h+var_E0], xmm0
0x180049393  xor     eax, eax
0x180049395  mov     qword ptr [rbp+0F0h+var_E0], r12
0x180049399  movups  [rbp+0F0h+var_F0], xmm0
0x18004939d  mov     dword ptr [rbp+0F0h+var_F0+8], ebx
0x1800493a0  mov     dword ptr [rbp+0F0h+var_E0+8], 2
0x1800493a7  mov     [rbp+0F0h+var_158], rax
0x1800493ab  movups  [rbp+0F0h+var_D0], xmm0
0x1800493af  mov     qword ptr [rbp+0F0h+psizl.cx], r13
0x1800493b3  call    cs:__imp_GetDC
0x1800493b9  mov     rdx, [rdi+258h]; h
0x1800493c0  mov     rcx, rax; hdc
0x1800493c3  mov     r13, rax
0x1800493c6  call    cs:__imp_SelectObject
0x1800493cc  lea     r9, [rbp+0F0h+psizl]; psizl
0x1800493d0  mov     r8d, ebx; c
0x1800493d3  mov     rdx, r12; lpString
0x1800493d6  mov     [rbp+0F0h+h], rax
0x1800493da  mov     rcx, r13; hdc
0x1800493dd  call    cs:__imp_GetTextExtentPoint32W
0x1800493e3  lea     ecx, [r15+2Ch]; nIndex
0x1800493e7  call    cs:__imp_GetSystemMetrics
0x1800493ed  mov     ecx, [rbp+0F0h+psizl.cx]
0x1800493f0  lea     r12d, [rcx+rax*2]
0x1800493f4  lea     ecx, [r15+2Dh]; nIndex
0x1800493f8  mov     dword ptr [rbp+0F0h+var_D0+4], r12d
0x1800493fc  call    cs:__imp_GetSystemMetrics
0x180049402  mov     ecx, [rbp+0F0h+psizl.cy]
0x180049405  lea     r8d, [rcx+rax*2]
0x180049409  mov     eax, [rsi+34h]
0x18004940c  xor     ecx, ecx
0x18004940e  mov     dword ptr [rbp+0F0h+var_D0+8], r8d
0x180049412  cmp     eax, ebx
0x180049414  mov     [rsp+1F0h+var_17C], eax
0x180049418  setz    cl
0x18004941b  mov     [rsp+1F0h+var_188], ecx
0x18004941f  mov     rcx, [rdi+298h]; this
0x180049426  test    rcx, rcx
0x180049429  jz      short loc_1800494A0
0x18004942b  mov     r9d, [rdi+290h]
0x180049432  shr     r9d, 1
0x180049435  sbb     r9d, r9d; int
0x180049438  cmp     eax, ebx
0x18004943a  jnz     short loc_180049446
0x18004943c  mov     eax, [rdi+274h]
0x180049442  add     eax, eax
0x180049444  jmp     short loc_180049448
0x180049446  xor     eax, eax
0x180049448  add     r8d, 2; int
0x18004944c  lea     edx, [r12+rax]; int
0x180049450  call    ?SetCompStrRect@CDefCompFrameWindow@@QEAAXHHH@Z; CDefCompFrameWindow::SetCompStrRect(int,int,int)
0x180049455  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ImeCompositionWindowLifeTimeTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ImeCompositionWindowLifeTimeTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImeCompositionWindowLifeTimeTest> `wil::Feature<__WilFeatureTraits_Feature_ImeCompositionWindowLifeTimeTest>::GetImpl(void)'::`2'::impl
0x18004945c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ImeCompositionWindowLifeTimeTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImeCompositionWindowLifeTimeTest>::__private_IsEnabled(void)
0x180049461  test    al, al
0x180049463  jz      short loc_1800494A0
0x180049465  lea     rbx, [rdi+308h]
0x18004946c  mov     rcx, rbx
0x18004946f  call    ??B?$tip_test@V?$merged_data@U_tip_CompositionWindowLifeTimeTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_CompositionWindowLifeTimeTest,_tip_CompositionWindowLifeTimeTest>>::operator bool(void)
0x180049474  test    al, al
0x180049476  jz      short loc_1800494A0
0x180049478  test    [rdi+290h], r15b
0x18004947f  jz      short loc_1800494A0
0x180049481  lea     rdx, [rbp+0F0h+hdc]
0x180049485  mov     rcx, rbx
0x180049488  call    ??C?$tip_test@V?$merged_data@U_tip_CompositionWindowLifeTimeTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CompositionWindowLifeTimeTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CompositionWindowLifeTimeTest,_tip_CompositionWindowLifeTimeTest>>::operator->(void)
0x18004948d  mov     rcx, [rax]
0x180049490  mov     [rcx+118h], r15b
0x180049497  lea     rcx, [rbp+0F0h+hdc]
0x18004949b  call    ??1?$test_data_control@V?$merged_data@U_tip_CompositionWindowLifeTimeTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CompositionWindowLifeTimeTest,_tip_CompositionWindowLifeTimeTest>>::~test_data_control<tip2::details::merged_data<_tip_CompositionWindowLifeTimeTest,_tip_CompositionWindowLifeTimeTest>>(void)
0x1800494a0  cmp     dword ptr [rsi+5Ch], 10h
0x1800494a4  jb      short loc_1800494AE
0x1800494a6  mov     ebx, [rsi+60h]
0x1800494a9  add     rbx, rsi
0x1800494ac  jmp     short loc_1800494B0
0x1800494ae  xor     ebx, ebx
0x1800494b0  lea     r12, [rdi+1D0h]
0x1800494b7  mov     rcx, r12; this
0x1800494ba  call    ?RemoveAll@CPolyText@@QEAAXXZ; CPolyText::RemoveAll(void)
0x1800494bf  test    rbx, rbx
0x1800494c2  jz      loc_18004954D
0x1800494c8  mov     eax, [rbx+0Ch]
0x1800494cb  lea     rdx, [rbp+0F0h+var_110]
0x1800494cf  add     rbx, rax
0x1800494d2  mov     [rbp+0F0h+var_138], 0
0x1800494da  lea     rax, ??_7CCompClauseStore@@6B@; const CCompClauseStore::`vftable'
0x1800494e1  mov     [rbp+0F0h+var_130], 0
0x1800494e8  lea     rcx, [rbp+0F0h+var_140]; this
0x1800494ec  mov     [rbp+0F0h+var_140], rax
0x1800494f0  call    ?Set@CCompClauseStore@@QEAAJAEAV?$IMCCLock@UtagCOMPOSITIONSTRING@@@@@Z; CCompClauseStore::Set(IMCCLock<tagCOMPOSITIONSTRING> &)
0x1800494f5  movups  xmm0, [rbp+0F0h+var_F0]
0x1800494f9  lea     rax, [rbp+0F0h+var_140]
0x1800494fd  mov     r8, r13; HDC
0x180049500  movups  xmm1, [rbp+0F0h+var_E0]
0x180049504  lea     r9, [rbp+0F0h+var_B0]; struct tagPOLYTEXTW *
0x180049508  mov     qword ptr [rsp+1F0h+cy], rax; struct CCompClauseStore *
0x18004950d  movaps  xmmword ptr [rbp+0F0h+var_B0.x], xmm0
0x180049511  mov     rdx, r14; struct IMCLock *
0x180049514  movups  xmm0, [rbp+0F0h+var_D0]
0x180049518  mov     rcx, r12; this
0x18004951b  mov     qword ptr [rsp+1F0h+var_1D0.cx], rbx; psizl
0x180049520  movaps  xmmword ptr [rbp+0F0h+var_B0.lpstr], xmm1
0x180049524  movsd   xmm1, [rbp+0F0h+var_158]
0x180049529  movaps  xmmword ptr [rbp+0F0h+var_B0.rcl.top], xmm0
0x18004952d  movsd   [rbp+0F0h+var_B0.pdx], xmm1
0x180049532  call    ?SplitPolyStringAndAttr@CPolyText@@QEAAJAEAVIMCLock@@PEAUHDC__@@UtagPOLYTEXTW@@PEAEPEAVCCompClauseStore@@@Z; CPolyText::SplitPolyStringAndAttr(IMCLock &,HDC__ *,tagPOLYTEXTW,uchar *,CCompClauseStore *)
0x180049537  lea     rax, ??_7CCompClauseStore@@6B@; const CCompClauseStore::`vftable'
0x18004953e  lea     rcx, [rbp+0F0h+var_140]; this
0x180049542  mov     [rbp+0F0h+var_140], rax
0x180049546  call    ?ClearString@CCompClauseStore@@QEAAXXZ; CCompClauseStore::ClearString(void)
0x18004954b  jmp     short loc_18004957E
0x18004954d  movups  xmm0, [rbp+0F0h+var_F0]
0x180049551  xor     r8d, r8d; unsigned int
0x180049554  lea     rdx, [rbp+0F0h+var_B0]; struct tagPOLYTEXTW
0x180049558  movups  xmm1, [rbp+0F0h+var_E0]
0x18004955c  mov     rcx, r12; this
0x18004955f  movaps  xmmword ptr [rbp+0F0h+var_B0.x], xmm0
0x180049563  movups  xmm0, [rbp+0F0h+var_D0]
0x180049567  movaps  xmmword ptr [rbp+0F0h+var_B0.lpstr], xmm1
0x18004956b  movsd   xmm1, [rbp+0F0h+var_158]
0x180049570  movaps  xmmword ptr [rbp+0F0h+var_B0.rcl.top], xmm0
0x180049574  movsd   [rbp+0F0h+var_B0.pdx], xmm1
0x180049579  call    ?AppendPolyStringAndAttr@CPolyText@@QEAAJUtagPOLYTEXTW@@K@Z; CPolyText::AppendPolyStringAndAttr(tagPOLYTEXTW,ulong)
0x18004957e  mov     ecx, [rsp+1F0h+c]; this
0x180049582  cmp     [rsp+1F0h+var_17C], ecx
0x180049586  ja      short loc_1800495C6
0x180049588  mov     eax, [rsp+1F0h+var_188]
0x18004958c  lea     r8, [rdi+218h]; struct CCaret *
0x180049593  mov     dword ptr [rsp+1F0h+var_1A8], eax; int
0x180049597  xor     r9d, r9d; int
0x18004959a  mov     eax, [rsi+34h]
0x18004959d  mov     rdx, r13; HDC
0x1800495a0  mov     [rsp+1F0h+var_1B0], 0; int
0x1800495a8  mov     dword ptr [rsp+1F0h+var_1B8], eax; unsigned int
0x1800495ac  mov     rax, [rbp+0F0h+var_148]
0x1800495b0  mov     [rsp+1F0h+uFlags], ecx; unsigned int
0x1800495b4  mov     qword ptr [rsp+1F0h+cy], rax; unsigned __int16 *
0x1800495b9  mov     [rsp+1F0h+var_1D0.cx], 0; int
0x1800495c1  call    ?SetCaretPos@UIComposition@@AEAAJPEAUHDC__@@AEAVCCaret@@HHPEBGKKHH@Z; UIComposition::SetCaretPos(HDC__ *,CCaret &,int,int,ushort const *,ulong,ulong,int,int)
0x1800495c6  mov     eax, [rsp+1F0h+var_184]
0x1800495ca  mov     rcx, r13; hdc
0x1800495cd  mov     rdx, [rbp+0F0h+h]; h
0x1800495d1  mov     [rdi+248h], eax
0x1800495d7  mov     eax, [rsp+1F0h+var_178]
0x1800495db  mov     [rdi+24Ch], eax
0x1800495e1  call    cs:__imp_SelectObject
0x1800495e7  mov     rcx, [rdi+1C8h]; hWnd
0x1800495ee  mov     rdx, r13; hDC
0x1800495f1  call    cs:__imp_ReleaseDC
0x1800495f7  mov     rcx, [rdi+1C8h]; hWnd
0x1800495fe  xor     r8d, r8d; bErase
0x180049601  xor     edx, edx; lpRect
0x180049603  call    cs:__imp_InvalidateRect
0x180049609  xor     r13d, r13d
0x18004960c  mov     ebx, r13d
0x18004960f  movsxd  rax, ebx
0x180049612  lea     rsi, [rax+rax*8]
0x180049616  add     rsi, rsi
0x180049619  mov     rcx, [rdi+rsi*8+18h]; hWnd
0x18004961e  call    cs:__imp_IsWindow
0x180049624  test    eax, eax
0x180049626  jz      short loc_180049635
0x180049628  mov     rcx, [rdi+rsi*8+18h]; hWnd
0x18004962d  xor     edx, edx; nCmdShow
0x18004962f  call    cs:__imp_ShowWindow
0x180049635  add     ebx, r15d
0x180049638  cmp     ebx, 3
0x18004963b  jb      short loc_18004960F
0x18004963d  mov     rcx, [rdi+2A0h]; this
0x180049644  test    rcx, rcx
0x180049647  jz      short loc_180049656
0x180049649  xor     r9d, r9d; int
0x18004964c  xor     r8d, r8d; int
0x18004964f  xor     edx, edx; int
0x180049651  call    ?MoveShow@CCompButtonFrameWindow@@QEAAXHHH@Z; CCompButtonFrameWindow::MoveShow(int,int,int)
0x180049656  mov     rcx, [r14+8]
0x18004965a  test    rcx, rcx
0x18004965d  jz      short loc_18004967D
0x18004965f  cmp     [r14+18h], r13d
0x180049663  jl      short loc_18004967D
0x180049665  mov     r9, [r14+10h]; lParam
0x180049669  mov     edx, 282h; Msg
0x18004966e  mov     rcx, [rcx]; hWnd
0x180049671  mov     r8d, 0Fh; wParam
0x180049677  call    cs:__imp_SendMessageW
0x18004967d  lea     rcx, [rbp+0F0h+var_110]; this
0x180049681  call    ??1InternalIMCCLock@@UEAA@XZ; InternalIMCCLock::~InternalIMCCLock(void)
0x180049686  xor     eax, eax
0x180049688  jmp     loc_180049CC9
0x18004968d  cmp     eax, 2
0x180049690  jnz     short loc_180049656
0x180049692  mov     rcx, [r14+8]
0x180049696  xorps   xmm0, xmm0
0x180049699  mov     rax, [rcx+84h]
0x1800496a0  mov     qword ptr [rbp+0F0h+psizl.cx], rax
0x1800496a4  movups  xmmword ptr [rbp+0F0h+Rect.left], xmm0
0x1800496ab  test    [rcx+80h], r15b
0x1800496b2  jz      short loc_1800496C5
0x1800496b4  movups  xmm0, xmmword ptr [rcx+8Ch]
0x1800496bb  movdqu  xmmword ptr [rbp+0F0h+Rect.left], xmm0
0x1800496c3  jmp     short loc_1800496D5
0x1800496c5  mov     rcx, [rcx]; hWnd
0x1800496c8  lea     rdx, [rbp+0F0h+Rect]; lpRect
0x1800496cf  call    cs:__imp_GetClientRect
0x1800496d5  mov     rcx, [r14+8]
0x1800496d9  lea     rdx, [rbp+0F0h+psizl]; lpPoint
0x1800496dd  mov     rcx, [rcx]; hWnd
0x1800496e0  call    cs:__imp_ClientToScreen
0x1800496e6  mov     rcx, [r14+8]
0x1800496ea  lea     r8, [rbp+0F0h+Rect]; lpPoints
0x1800496f1  mov     r9d, 2; cPoints
0x1800496f7  xor     edx, edx; hWndTo
0x1800496f9  mov     rcx, [rcx]; hWndFrom
0x1800496fc  call    cs:__imp_MapWindowPoints
0x180049702  mov     rdx, qword ptr [rbp+0F0h+psizl.cx]; pt
0x180049706  lea     rcx, [rbp+0F0h+Rect]; lprc
0x18004970d  call    cs:__imp_PtInRect
  ... truncated ...
```
