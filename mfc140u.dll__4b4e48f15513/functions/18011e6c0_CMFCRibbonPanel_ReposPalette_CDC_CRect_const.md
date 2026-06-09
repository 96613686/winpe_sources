# CMFCRibbonPanel::ReposPalette(CDC *,CRect const &)

- ea: `0x18011e6c0`
- end: `0x18011f504`
- name: `?ReposPalette@CMFCRibbonPanel@@MEAAXPEAVCDC@@AEBVCRect@@@Z`
- size: `3652`
- prototype: `void __fastcall(CMFCRibbonPanel *this, CDC *pDC, const CRect *rect)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009844`
- `0x18000df50`
- `0x18011e6c0`
- `0x18015df60`
- `0x180231d70`
- `0x18023f820`
- `0x1802b66c0`
- `0x1802b6790`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `VCRUNTIME140!memset` at `0x18011f41b`
- `VCRUNTIME140!memset` at `0x18011f41b`
- `USER32!GetSystemMetrics` at `0x18011e7a5`
- `USER32!GetSystemMetrics` at `0x18011e7a5`
- `USER32!EnableScrollBar` at `0x18011f480`
- `USER32!EnableScrollBar` at `0x18011f4ae`
- `USER32!EnableScrollBar` at `0x18011f480`
- `USER32!EnableScrollBar` at `0x18011f4ae`
- `USER32!SetScrollInfo` at `0x18011f468`
- `USER32!SetScrollInfo` at `0x18011f468`
- `USER32!SetRectEmpty` at `0x18011f155`
- `USER32!SetRectEmpty` at `0x18011f169`
- `USER32!SetRectEmpty` at `0x18011f155`
- `USER32!SetRectEmpty` at `0x18011f169`
- `USER32!IsRectEmpty` at `0x18011f1f0`
- `USER32!IsRectEmpty` at `0x18011f1f0`
- `USER32!EqualRect` at `0x18011e708`
- `USER32!EqualRect` at `0x18011e708`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=1
void __fastcall CMFCRibbonPanel::ReposPalette(CMFCRibbonPanel *this, CDC *pDC, const CRect *rect)
{
  int v5; // eax
  CRect v6; // xmm6
  int v7; // r15d
  int SystemMetrics; // edx
  int m_pszData; // r13d
  int cx; // esi
  int m_bSizeIsLocked; // eax
  int v12; // ecx
  CSize m_sizeImage; // rbx
  __int64 m_nSize; // rdx
  CRect m_rect; // xmm0
  int v16; // r13d
  __int64 v17; // rcx
  int v18; // r12d
  CMFCRibbonBaseElement *v19; // r14
  CSize *v20; // rax
  CRect v21; // xmm0
  __int64 v22; // r12
  CMFCRibbonBaseElement *v23; // r14
  CSize *v24; // rax
  int v25; // eax
  CMFCVisualManager *Instance; // rax
  int v27; // ebx
  CMFCRibbonCategory *m_pParent; // rax
  __int64 v29; // r12
  CMFCRibbonBaseElement *v30; // r14
  int v31; // eax
  int v32; // edx
  unsigned __int64 v33; // rcx
  __int64 v34; // r12
  CMFCRibbonBaseElement *v35; // r14
  int v36; // eax
  __m128i v37; // xmm6
  int v38; // eax
  int v39; // r8d
  int v40; // ecx
  int v41; // eax
  _QWORD *v42; // rdx
  unsigned __int64 v43; // rcx
  int v44; // r9d
  int v45; // r8d
  int v46; // ecx
  int v47; // r14d
  int v48; // r13d
  __int64 v49; // r12
  CMFCRibbonBaseElement *v50; // rsi
  int v51; // r8d
  int v52; // ecx
  int v53; // edx
  int v54; // eax
  int m_pszData_high; // ebx
  int v56; // r12d
  __int64 v57; // rcx
  __int64 v58; // rsi
  CMFCRibbonBaseElement **m_pData; // rax
  CMFCRibbonBaseElement *v60; // rbx
  CMFCRibbonBaseElement *(__fastcall *HitTest)(CMFCRibbonPanel *, CPoint, int); // r9
  CObject *v62; // rax
  CObject *v63; // r14
  CMFCRibbonBaseElement *(__fastcall *v64)(CMFCRibbonPanel *, CPoint, int); // r9
  CObject *v65; // rax
  CObject *v66; // r14
  CMFCRibbonBaseElement *(__fastcall *v67)(CMFCRibbonPanel *, CPoint, int); // r9
  CObject *v68; // rax
  CObject *v69; // r14
  CMFCRibbonBaseElement *(__fastcall *v70)(CMFCRibbonPanel *, CPoint, int); // r9
  CObject *v71; // rax
  CObject *v72; // r14
  int v73; // esi
  bool v74; // zf
  int v75; // ebx
  int v76; // r9d
  int v77; // eax
  int v78; // r15d
  int v79; // [rsp+48h] [rbp-C0h]
  int v80; // [rsp+48h] [rbp-C0h]
  int v81; // [rsp+48h] [rbp-C0h]
  unsigned __int64 v82; // [rsp+50h] [rbp-B8h] OVERLAPPED BYREF
  int v83; // [rsp+58h] [rbp-B0h]
  int v84; // [rsp+5Ch] [rbp-ACh]
  __int64 v85; // [rsp+60h] [rbp-A8h] BYREF
  CDC *v86; // [rsp+68h] [rbp-A0h]
  CSize sizeElem; // [rsp+70h] [rbp-98h]
  int bottom; // [rsp+78h] [rbp-90h] BYREF
  int v89; // [rsp+7Ch] [rbp-8Ch]
  int v90; // [rsp+80h] [rbp-88h]
  int v91; // [rsp+84h] [rbp-84h]
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strLabel; // [rsp+88h] [rbp-80h]
  CSize result; // [rsp+90h] [rbp-78h] BYREF
  int v94; // [rsp+98h] [rbp-70h]
  int v95; // [rsp+9Ch] [rbp-6Ch]
  int v96; // [rsp+A0h] [rbp-68h]
  int v97; // [rsp+A4h] [rbp-64h] BYREF
  _BYTE v98[52]; // [rsp+B8h] [rbp-50h] OVERLAPPED BYREF

  v86 = pDC;
  *(_OWORD *)&v98[32] = 0;
  if ( !EqualRect(rect, (const RECT *)&v98[32]) )
  {
    LODWORD(v82) = CObject::IsKindOf(this->m_pPaletteButton, &CMFCRibbonUndoButton::classCMFCRibbonUndoButton);
    v5 = 0;
    v95 = 0;
    this->m_nScrollOffset = 0;
    v6 = *rect;
    *(CRect *)&v98[16] = *rect;
    if ( (int)HIDWORD(*(_QWORD *)&rect->right) > 0 )
    {
      v7 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v6, 12));
    }
    else
    {
      v7 = *(_DWORD *)&v98[20] + 32676;
      *(_DWORD *)&v98[28] = *(_DWORD *)&v98[20] + 32676;
      v5 = 1;
      v95 = 1;
      v6 = *(CRect *)&v98[16];
    }
    this->m_nXMargin = 0;
    this->m_nYMargin = 0;
    if ( !v5 || this->m_pPaletteButton->m_bEnableMenuResize )
      SystemMetrics = GetSystemMetrics(2);
    else
      SystemMetrics = 0;
    v96 = SystemMetrics;
    v84 = 0;
    m_pszData = _mm_cvtsi128_si32((__m128i)v6);
    LODWORD(strLabel.m_pszData) = m_pszData;
    v90 = m_pszData;
    sizeElem.cx = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v6, 4));
    cx = sizeElem.cx;
    this->m_rect = v6;
    m_bSizeIsLocked = this->m_bSizeIsLocked;
    v12 = *(_DWORD *)&v98[24];
    if ( m_bSizeIsLocked )
      v12 = *(_DWORD *)&v98[24] - SystemMetrics;
    else
      this->m_rect.right += SystemMetrics;
    v94 = v12;
    v83 = 0;
    HIDWORD(strLabel.m_pszData) = 0;
    v91 = 0;
    m_sizeImage.cx = 0;
    m_nSize = this->m_arElements.m_nSize;
    m_rect = this->m_rect;
    v79 = 0;
    this->m_rectMenuAreaTop = m_rect;
    if ( m_bSizeIsLocked )
    {
      v16 = v7;
      this->m_rectMenuAreaBottom = m_rect;
      if ( m_nSize > 0 )
      {
        v17 = 0;
        v85 = 0;
        v18 = cx;
        do
        {
          if ( v17 < 0 || v17 >= m_nSize )
            AfxThrowInvalidArgException();
          v19 = this->m_arElements.m_pData[v17];
          LODWORD(v82) = CObject::IsKindOf(v19, &CMFCRibbonLabel::classCMFCRibbonLabel);
          if ( !CObject::IsKindOf(v19, (const CRuntimeClass *)&CMFCRibbonGalleryIcon::`vftable'[162]) && !(_DWORD)v82 )
          {
            if ( v19->m_bIsOnPaletteTop )
              HIDWORD(strLabel.m_pszData) = 1;
            else
              v83 = 1;
            v19->OnCalcTextSize(v19, v86);
            v19->SetCompactMode(v19, 1);
            v20 = v19->GetImageSize(v19, &result, RibbonImageLarge);
            if ( !v20->cx && !v20->cy )
              v19->SetCompactMode(v19, 0);
            v19->SetTextAlwaysOnRight(v19, 1);
            v19->GetSize(v19, (CSize *)&bottom, v86);
            bottom = this->m_rect.right - this->m_rect.left;
            if ( v19->m_bIsOnPaletteTop )
            {
              *(_DWORD *)&v98[16] = strLabel.m_pszData;
              *(_DWORD *)&v98[24] = LODWORD(strLabel.m_pszData) + bottom;
              *(_DWORD *)&v98[20] = v18;
              *(_DWORD *)&v98[28] = v18 + v89;
              v21 = *(CRect *)&v98[16];
              v18 += v89;
              sizeElem.cx = v18 + 4;
              this->m_rectMenuAreaTop.bottom = v18;
              cx += v89;
            }
            else
            {
              v16 -= v89;
              *(_DWORD *)v98 = strLabel.m_pszData;
              *(_DWORD *)&v98[8] = LODWORD(strLabel.m_pszData) + bottom;
              *(_DWORD *)&v98[4] = v16;
              *(_DWORD *)&v98[12] = v16 + v89;
              v21 = *(CRect *)v98;
              v7 = v16 - 4;
              this->m_rectMenuAreaBottom.top = v16;
            }
            v19->m_rect = v21;
          }
          ++v79;
          v17 = ++v85;
          m_nSize = this->m_arElements.m_nSize;
        }
        while ( v79 < m_nSize );
      }
      m_pszData = (int)strLabel.m_pszData;
    }
    else
    {
      if ( m_nSize <= 0 )
        goto LABEL_158;
      v22 = 0;
      do
      {
        if ( v22 < 0 || v22 >= m_nSize )
          AfxThrowInvalidArgException();
        v23 = this->m_arElements.m_pData[v22];
        if ( !CObject::IsKindOf(v23, (const CRuntimeClass *)&CMFCRibbonGalleryIcon::`vftable'[162])
          && !CObject::IsKindOf(v23, &CMFCRibbonLabel::classCMFCRibbonLabel) )
        {
          v23->OnCalcTextSize(v23, v86);
          v23->SetCompactMode(v23, 1);
          v24 = v23->GetImageSize(v23, &result, RibbonImageLarge);
          if ( !v24->cx && !v24->cy )
            v23->SetCompactMode(v23, 0);
          v23->SetTextAlwaysOnRight(v23, 1);
          v23->GetSize(v23, (CSize *)&v85, v86);
          LODWORD(v85) = v85 + 6;
          v25 = HIDWORD(v85);
          if ( v91 > SHIDWORD(v85) )
            v25 = v91;
          v91 = v25;
          if ( m_sizeImage.cx <= v23->GetImageSize(v23, (CSize *)&bottom, RibbonImageSmall)->cx )
            m_sizeImage.cx = v23->GetImageSize(v23, (CSize *)&v97, RibbonImageSmall)->cx;
        }
        ++v79;
        ++v22;
        m_nSize = this->m_arElements.m_nSize;
      }
      while ( v79 < m_nSize );
      if ( !m_sizeImage.cx )
      {
LABEL_158:
        if ( !(_DWORD)v82 )
        {
          Instance = CMFCVisualManager::GetInstance();
          v27 = 2 * ((__int64 (__fastcall *)(CMFCVisualManager *))Instance->GetMenuImageMargin)(Instance);
          m_sizeImage.cx = CMFCToolBar::GetMenuImageSize(&result)->cx + v27;
          m_pParent = this->m_pParent;
          if ( m_pParent )
            m_sizeImage = m_pParent->m_SmallImages.m_sizeImage;
        }
      }
      v80 = 0;
      m_nSize = this->m_arElements.m_nSize;
      if ( m_nSize > 0 )
      {
        v29 = 0;
        do
        {
          if ( v29 < 0 || v29 >= m_nSize )
            AfxThrowInvalidArgException();
          v30 = this->m_arElements.m_pData[v29];
          if ( !CObject::IsKindOf(v30, (const CRuntimeClass *)&CMFCRibbonGalleryIcon::`vftable'[162])
            && !CObject::IsKindOf(v30, &CMFCRibbonLabel::classCMFCRibbonLabel)
            && v30->m_bIsOnPaletteTop )
          {
            v30->GetSize(v30, (CSize *)&v82, v86);
            if ( v82 )
            {
              v30->m_nImageOffset = m_sizeImage.cx;
              LODWORD(v82) = this->m_rect.right - this->m_rect.left;
              v31 = v82;
              HIDWORD(v82) = v91;
              v32 = cx + sizeElem.cx;
              v33 = HIDWORD(v82);
              v30->m_rect.left = m_pszData;
              v30->m_rect.top = v32;
              v30->m_rect.right = m_pszData + v31;
              v30->m_rect.bottom = v33 + v32;
              cx += HIDWORD(v82);
            }
            else
            {
              *(_OWORD *)&v98[32] = 0;
              v30->m_rect = 0;
            }
          }
          ++v80;
          ++v29;
          m_nSize = this->m_arElements.m_nSize;
        }
        while ( v80 < m_nSize );
      }
      this->m_rectMenuAreaTop.bottom = cx;
    }
    bottom = this->m_rect.bottom;
    v97 = 1;
    if ( !this->m_bSizeIsLocked )
      this->m_rect.bottom = cx;
    v81 = 0;
    if ( m_nSize > 0 )
    {
      v34 = 0;
      while ( 1 )
      {
        if ( v34 < 0 || v34 >= m_nSize )
          AfxThrowInvalidArgException();
        v35 = this->m_arElements.m_pData[v34];
        LODWORD(v82) = CObject::IsKindOf(v35, &CMFCRibbonLabel::classCMFCRibbonLabel);
        if ( CObject::IsKindOf(v35, (const CRuntimeClass *)&CMFCRibbonGalleryIcon::`vftable'[162]) )
          break;
        if ( (_DWORD)v82 )
          goto LABEL_73;
        if ( v35->m_bIsOnPaletteTop )
          HIDWORD(strLabel.m_pszData) = 1;
        else
          v83 = 1;
LABEL_93:
        ++v81;
        ++v34;
        m_nSize = this->m_arElements.m_nSize;
        if ( v81 >= m_nSize )
          goto LABEL_94;
      }
      if ( !(_DWORD)v82 )
      {
        v97 = 0;
        v35->SetCompactMode(v35, 0);
        v43 = (unsigned __int64)*v35->GetSize(v35, (CSize *)&v98[16], v86);
        v82 = v43;
        v44 = v90;
        if ( (int)v43 + v90 > v94 && v90 != m_pszData )
        {
          v44 = m_pszData;
          cx += HIDWORD(v43);
        }
        v84 = HIDWORD(v43) + cx;
        v35->m_rect.left = v44;
        v35->m_rect.top = cx;
        v35->m_rect.right = v43 + v44;
        v35->m_rect.bottom = HIDWORD(v43) + cx;
        if ( !this->m_bSizeIsLocked )
          this->m_rect.bottom = HIDWORD(v43) + cx;
        bottom = HIDWORD(v43) + cx;
        v90 = v43 + v44;
        goto LABEL_93;
      }
LABEL_73:
      if ( v90 > m_pszData )
        cx = bottom;
      v36 = cx++;
      if ( v81 <= 0 )
        cx = v36;
      LODWORD(v82) = cx;
      ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
        (ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *)&result,
        v35->m_strText.m_pszData);
      v37 = 0;
      if ( *(_DWORD *)(*(_QWORD *)&result - 16LL) )
      {
        v35->OnCalcTextSize(v35, v86);
        HIDWORD(v82) = HIDWORD(*(unsigned __int64 *)v35->GetSize(v35, (CSize *)v98, v86));
        LODWORD(v82) = v94 - m_pszData;
        *(_DWORD *)&v98[32] = m_pszData;
        *(_DWORD *)&v98[40] = v94;
        *(_DWORD *)&v98[36] = cx;
        v84 = cx + HIDWORD(v82);
        *(_DWORD *)&v98[44] = cx + HIDWORD(v82);
        v37 = *(__m128i *)&v98[32];
        v41 = this->m_pPaletteButton->GetGroupOffset(this->m_pPaletteButton);
        cx += HIDWORD(v82) + v41;
        v97 = 0;
        v39 = v84;
        v40 = v84;
      }
      else
      {
        if ( !v97 )
        {
          v38 = this->m_pPaletteButton->GetGroupOffset(this->m_pPaletteButton);
          cx = v82 + v38;
        }
        v39 = 0;
        v84 = 0;
        v40 = 0;
      }
      v35->m_rect = (CRect)v37;
      if ( !this->m_bSizeIsLocked )
      {
        this->m_rect.bottom = _mm_cvtsi128_si32(_mm_srli_si128(v37, 12));
        v39 = v40;
        v84 = v40;
      }
      v90 = m_pszData;
      v42 = (_QWORD *)(*(_QWORD *)&result - 24LL);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&result - 24LL + 16), 0xFFFFFFFF) <= 1 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v42 + 8LL))(*v42);
        v39 = v84;
      }
      bottom = v39;
      goto LABEL_93;
    }
LABEL_94:
    v45 = this->m_bSizeIsLocked;
    if ( !v45 )
    {
      v46 = v7;
      if ( this->m_rect.bottom < v7 )
        v46 = this->m_rect.bottom;
      this->m_rect.bottom = v46;
    }
    this->m_nFullWidth = this->m_rect.right - this->m_rect.left;
    if ( v83 )
    {
      if ( !v45 )
      {
        v47 = this->m_rect.bottom + 4;
        this->m_rectMenuAreaBottom = this->m_rect;
        this->m_rectMenuAreaBottom.top = v47;
        v48 = 0;
        if ( m_nSize > 0 )
        {
          v49 = 0;
          do
          {
            if ( v49 < 0 || v49 >= m_nSize )
              AfxThrowInvalidArgException();
            v50 = this->m_arElements.m_pData[v49];
            if ( !CObject::IsKindOf(v50, (const CRuntimeClass *)&CMFCRibbonGalleryIcon::`vftable'[162])
              && !CObject::IsKindOf(v50, &CMFCRibbonLabel::classCMFCRibbonLabel)
              && !v50->m_bIsOnPaletteTop )
            {
              v50->GetSize(v50, (CSize *)&v85, v86);
              if ( v85 )
              {
                v50->m_nImageOffset = m_sizeImage.cx;
                LODWORD(v85) = this->m_rect.right - this->m_rect.left;
                v51 = v85;
                HIDWORD(v85) = v91;
                v52 = v47 + sizeElem.cx;
                v53 = v47 + sizeElem.cx + v91;
                this->m_rect.bottom = v53;
                v54 = (int)strLabel.m_pszData;
                v50->m_rect.left = (int)strLabel.m_pszData;
                v50->m_rect.top = v52;
                v50->m_rect.right = v51 + v54;
                v50->m_rect.bottom = v53;
                v47 += HIDWORD(v85);
              }
              else
              {
                v50->m_rect = 0;
              }
            }
            ++v48;
            ++v49;
            m_nSize = this->m_arElements.m_nSize;
          }
          while ( v48 < m_nSize );
        }
        this->m_rectMenuAreaBottom.bottom = v47;
      }
    }
    else
    {
      SetRectEmpty(&this->m_rectMenuAreaBottom);
    }
    m_pszData_high = HIDWORD(strLabel.m_pszData);
    if ( !HIDWORD(strLabel.m_pszData) )
      SetRectEmpty(&this->m_rectMenuAreaTop);
    v56 = 0;
    v57 = this->m_arElements.m_nSize;
    if ( v57 > 0 )
    {
      v58 = 0;
      do
      {
        if ( v58 < 0 || v58 >= v57 )
          AfxThrowInvalidArgException();
        m_pData = this->m_arElements.m_pData;
        v60 = m_pData[v58];
        if ( v60 )
        {
          if ( CObject::IsKindOf(m_pData[v58], (const CRuntimeClass *)&CMFCRibbonGalleryIcon::`vftable'[162]) )
          {
            HIDWORD(v60[1].m_pParentMenu) = 0;
            v60[1].m_Location = RibbonElementNotInGroup;
            *((_DWORD *)&v60[1].m_Location + 1) = 0;
            LODWORD(v60[1].m_pPopupMenu) = 0;
            *(CRect *)&v98[16] = v60->m_rect;
            if ( !IsRectEmpty((const RECT *)&v98[16]) )
            {
              HitTest = this->HitTest;
              result.cx = *(_DWORD *)&v98[16] - 2;
              result.cy = (*(_DWORD *)&v98[20] + *(_DWORD *)&v98[28]) / 2;
              v62 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))HitTest)(this, (CPoint)result, 0);
              v63 = v62;
              if ( !v62 || !CObject::IsKindOf(v62, (const CRuntimeClass *)&CMFCRibbonGalleryIcon::`vftable'[162]) )
                v63 = 0;
              HIDWORD(v60[1].m_pParentMenu) = v63 == 0;
              v64 = this->HitTest;
              LODWORD(v85) = *(_DWORD *)&v98[24] + 2;
              HIDWORD(v85) = (*(_DWORD *)&v98[20] + *(_DWORD *)&v98[28]) / 2;
              v65 = (CObject *)((__int64 (__fastcall *)(CMFCRibbonPanel *, __int64, _QWORD))v64)(this, v85, 0);
              v66 = v65;
              if ( !v65 || !CObject::IsKindOf(v65, (const CRuntimeClass *)&CMFCRibbonGalleryIcon::`vftable'[162]) )
                v66 = 0;
              v60[1].m_Location = v66 == 0;
              v67 = this->HitTest;
              LODWORD(v86) = (*(_DWORD *)&v98[16] + *(_DWORD *)&v98[24]) / 2;
              HIDWORD(v86) = *(_DWORD *)&v98[20] - 2;
              v68 = (CObject *)((__int64 (__fastcall *)(CMFCRibbonPanel *, CDC *, _QWORD))v67)(this, v86, 0);
              v69 = v68;
              if ( !v68 || !CObject::IsKindOf(v68, (const CRuntimeClass *)&CMFCRibbonGalleryIcon::`vftable'[162]) )
                v69 = 0;
              *((_DWORD *)&v60[1].m_Location + 1) = v69 == 0;
              v70 = this->HitTest;
              LODWORD(v82) = (*(_DWORD *)&v98[16] + *(_DWORD *)&v98[24]) / 2;
              HIDWORD(v82) = *(_DWORD *)&v98[28] + 2;
              v71 = (CObject *)((__int64 (__fastcall *)(CMFCRibbonPanel *, unsigned __int64, _QWORD))v70)(this, v82, 0);
              v72 = v71;
              if ( !v71 || !CObject::IsKindOf(v71, (const CRuntimeClass *)&CMFCRibbonGalleryIcon::`vftable'[162]) )
                v72 = 0;
              LODWORD(v60[1].m_pPopupMenu) = v72 == 0;
            }
          }
        }
        ++v56;
        ++v58;
        v57 = this->m_arElements.m_nSize;
      }
      while ( v56 < v57 );
      m_pszData_high = HIDWORD(strLabel.m_pszData);
    }
    v73 = v95;
    if ( !v95 || this->m_pPaletteButton->m_bEnableMenuResize )
    {
      v74 = m_pszData_high == 0;
      v75 = sizeElem.cx;
      if ( v74 )
        v76 = sizeElem.cx;
      else
        v76 = this->m_rectMenuAreaTop.bottom + 1;
      if ( v83 )
        v77 = this->m_rectMenuAreaBottom.top - 1;
      else
        v77 = this->m_rect.bottom;
      CWnd::SetWindowPos(this->m_pScrollBar, 0, this->m_rect.right - v96, v76, v96, v77 - v76 - 1, 0x14u);
      memset(&v98[32], 0, 0x1Cu);
      *(_DWORD *)&v98[32] = 28;
      *(_DWORD *)&v98[36] = 7;
      *(_DWORD *)&v98[40] = 0;
      v78 = v7 - v75;
      if ( this->m_rectMenuAreaTop.top - this->m_rectMenuAreaTop.bottom + v84 <= v78 )
      {
        if ( !v73 )
          EnableScrollBar(this->m_pScrollBar->m_hWnd, 2u, 3u);
      }
      else
      {
        *(_DWORD *)&v98[44] = this->m_rectMenuAreaTop.top - this->m_rectMenuAreaTop.bottom + v84;
        *(_DWORD *)&v98[48] = v78;
        SetScrollInfo(this->m_pScrollBar->m_hWnd, 2, (LPCSCROLLINFO)&v98[32], 1);
        EnableScrollBar(this->m_pScrollBar->m_hWnd, 2u, 0);
        CWnd::EnableWindow(this->m_pScrollBar, 1);
      }
    }
  }
}

```

## disassembly

```asm
0x18011e6c0  mov     rax, rsp
0x18011e6c3  mov     [rax+20h], rbx
0x18011e6c7  push    rbp
0x18011e6c8  push    rsi
0x18011e6c9  push    rdi
0x18011e6ca  push    r12
0x18011e6cc  push    r13
0x18011e6ce  push    r14
0x18011e6d0  push    r15
0x18011e6d2  lea     rbp, [rax-48h]
0x18011e6d6  sub     rsp, 110h
0x18011e6dd  movaps  xmmword ptr [rax-48h], xmm6
0x18011e6e1  mov     rax, cs:__security_cookie
0x18011e6e8  xor     rax, rsp
0x18011e6eb  mov     [rbp+40h+var_50], rax
0x18011e6ef  mov     rbx, rect
0x18011e6f2  mov     qword ptr [rsp+140h+var_E0], pDC
0x18011e6f7  mov     rdi, this
0x18011e6fa  xorps   xmm0, xmm0
0x18011e6fd  movups  xmmword ptr [rbp+40h+var_78.nMin], xmm0
0x18011e701  lea     pDC, [rbp+40h+var_78.nMin]; lprc2
0x18011e705  mov     this, rect; lprc1
0x18011e708  call    cs:__imp_EqualRect
0x18011e70e  test    eax, eax
0x18011e710  jnz     loc_18011F4B4
0x18011e716  lea     pDC, ?classCMFCRibbonUndoButton@CMFCRibbonUndoButton@@2UCRuntimeClass@@B; pClass
0x18011e71d  mov     this, [rdi+168h]; this
0x18011e724  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18011e729  mov     [rsp+140h+var_F8], eax
0x18011e72d  xor     eax, eax
0x18011e72f  mov     [rbp+40h+var_AC], eax
0x18011e732  and     [rdi+0F8h], eax
0x18011e738  movups  xmm6, xmmword ptr [rbx]
0x18011e73b  movups  xmmword ptr [rbp+40h+rectIcon.right], xmm6
0x18011e73f  mov     this, [rbx+8]
0x18011e743  shr     this, 20h
0x18011e747  test    ecx, ecx
0x18011e749  jg      short loc_18011E76C
0x18011e74b  mov     r15, qword ptr [rbp+40h+rectIcon.right]
0x18011e74f  shr     r15, 20h
0x18011e753  add     r15d, 7FA4h
0x18011e75a  mov     [rbp+40h+var_78.fMask], r15d
0x18011e75e  mov     eax, 1
0x18011e763  mov     [rbp+40h+var_AC], eax
0x18011e766  movups  xmm6, xmmword ptr [rbp+40h+rectIcon.right]
0x18011e76a  jmp     short loc_18011E77A
0x18011e76c  movdqa  xmm0, xmm6
0x18011e770  psrldq  xmm0, 0Ch
0x18011e775  movd    r15d, xmm0
0x18011e77a  and     dword ptr [rdi+0F0h], 0
0x18011e781  and     dword ptr [rdi+0F4h], 0
0x18011e788  test    eax, eax
0x18011e78a  jz      short loc_18011E7A0
0x18011e78c  mov     rax, [rdi+168h]
0x18011e793  cmp     dword ptr [rax+4D8h], 0
0x18011e79a  jnz     short loc_18011E7A0
0x18011e79c  xor     edx, edx
0x18011e79e  jmp     short loc_18011E7AD
0x18011e7a0  mov     ecx, 2; nIndex
0x18011e7a5  call    cs:__imp_GetSystemMetrics
0x18011e7ab  mov     edx, eax
0x18011e7ad  mov     [rbp+40h+var_A8], edx
0x18011e7b0  xor     ecx, ecx
0x18011e7b2  mov     dword ptr [rsp+140h+var_F0+4], ecx
0x18011e7b6  movd    r13d, xmm6
0x18011e7bb  mov     dword ptr [rbp+40h+strLabel.m_pszData], r13d
0x18011e7bf  mov     [rsp+140h+var_C8], r13d
0x18011e7c4  movdqa  xmm0, xmm6
0x18011e7c8  psrldq  xmm0, 4
0x18011e7cd  movd    [rsp+140h+sizeElem.cx], xmm0
0x18011e7d3  movd    esi, xmm0
0x18011e7d7  movdqu  xmmword ptr [rdi+10Ch], xmm6
0x18011e7df  mov     eax, [rdi+0D4h]
0x18011e7e5  mov     ecx, [rbp+40h+var_78.cbSize]
0x18011e7e8  test    eax, eax
0x18011e7ea  jz      short loc_18011E7F0
0x18011e7ec  sub     ecx, edx
0x18011e7ee  jmp     short loc_18011E7F6
0x18011e7f0  add     [rdi+114h], edx
0x18011e7f6  mov     [rbp+40h+var_B0], ecx
0x18011e7f9  and     dword ptr [rsp+140h+var_F0], 0
0x18011e7fe  and     dword ptr [rbp+40h+strLabel.m_pszData+4], 0
0x18011e802  and     [rsp+140h+var_C4], 0
0x18011e807  xor     ebx, ebx
0x18011e809  mov     pDC, [rdi+6E0h]
0x18011e810  movups  xmm0, xmmword ptr [rdi+10Ch]
0x18011e817  and     dword ptr [rsp+140h+var_100], ebx
0x18011e81b  movdqu  xmmword ptr [rdi+11Ch], xmm0
0x18011e823  test    eax, eax
0x18011e825  jz      loc_18011EA16
0x18011e82b  mov     r13d, r15d
0x18011e82e  movups  xmm1, xmm0
0x18011e831  movdqu  xmmword ptr [rdi+12Ch], xmm0
0x18011e839  test    pDC, pDC
0x18011e83c  jle     loc_18011EA0D
0x18011e842  xor     ecx, ecx
0x18011e844  mov     [rsp+140h+var_E8], this
0x18011e849  mov     r12d, esi
0x18011e84c  test    this, this
0x18011e84f  js      loc_18011F4E6
0x18011e855  cmp     this, pDC
0x18011e858  jge     loc_18011F4E6
0x18011e85e  mov     rax, [rdi+6D8h]
0x18011e865  mov     r14, [rax+this*8]
0x18011e869  lea     pDC, ?classCMFCRibbonLabel@CMFCRibbonLabel@@2UCRuntimeClass@@B; pClass
0x18011e870  mov     this, r14; this
0x18011e873  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18011e878  mov     [rsp+140h+var_F8], eax
0x18011e87c  lea     pDC, ??_7CMFCRibbonGalleryIcon@@6B@+510h; pClass
0x18011e883  mov     this, r14; this
0x18011e886  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18011e88b  test    eax, eax
0x18011e88d  jnz     loc_18011E9E0
0x18011e893  cmp     [rsp+140h+var_F8], ebx
0x18011e897  jnz     loc_18011E9E0
0x18011e89d  cmp     [r14+16Ch], ebx
0x18011e8a4  jz      short loc_18011E8AF
0x18011e8a6  mov     dword ptr [rbp+40h+strLabel.m_pszData+4], 1
0x18011e8ad  jmp     short loc_18011E8B7
0x18011e8af  mov     dword ptr [rsp+140h+var_F0], 1
0x18011e8b7  mov     rax, [r14]
0x18011e8ba  mov     pDC, qword ptr [rsp+140h+var_E0]
0x18011e8bf  mov     this, r14
0x18011e8c2  mov     rax, [rax+310h]
0x18011e8c9  call    cs:__guard_dispatch_icall_fptr
0x18011e8cf  mov     rax, [r14]
0x18011e8d2  mov     edx, 1
0x18011e8d7  mov     this, r14
0x18011e8da  mov     rax, [rax+1E8h]
0x18011e8e1  call    cs:__guard_dispatch_icall_fptr
0x18011e8e7  mov     rax, [r14]
0x18011e8ea  xor     r8d, r8d
0x18011e8ed  lea     pDC, [rbp+40h+result]
0x18011e8f1  mov     this, r14
0x18011e8f4  mov     rax, [rax+238h]
0x18011e8fb  call    cs:__guard_dispatch_icall_fptr
0x18011e901  cmp     [rax], ebx
0x18011e903  jnz     short loc_18011E91F
0x18011e905  cmp     [rax+4], ebx
0x18011e908  jnz     short loc_18011E91F
0x18011e90a  mov     rax, [r14]
0x18011e90d  xor     edx, edx
0x18011e90f  mov     this, r14
0x18011e912  mov     rax, [rax+1E8h]
0x18011e919  call    cs:__guard_dispatch_icall_fptr
0x18011e91f  mov     rax, [r14]
0x18011e922  mov     edx, 1
0x18011e927  mov     this, r14
0x18011e92a  mov     rax, [rax+188h]
0x18011e931  call    cs:__guard_dispatch_icall_fptr
0x18011e937  mov     rax, [r14]
0x18011e93a  mov     rect, qword ptr [rsp+140h+var_E0]
0x18011e93f  lea     pDC, [rsp+140h+var_D0]
0x18011e944  mov     this, r14
0x18011e947  mov     rax, [rax+1F8h]
0x18011e94e  call    cs:__guard_dispatch_icall_fptr
0x18011e954  mov     eax, [rdi+114h]
0x18011e95a  sub     eax, [rdi+10Ch]
0x18011e960  mov     [rsp+140h+var_D0], eax
0x18011e964  mov     ecx, dword ptr [rbp+40h+strLabel.m_pszData]
0x18011e967  add     eax, ecx
0x18011e969  cmp     [r14+16Ch], ebx
0x18011e970  jz      short loc_18011E9AA
0x18011e972  mov     [rbp+40h+rectIcon.right], ecx
0x18011e975  mov     [rbp+40h+var_78.cbSize], eax
0x18011e978  mov     [rbp+40h+rectIcon.bottom], r12d
0x18011e97c  mov     rax, qword ptr [rsp+140h+var_D0]
0x18011e981  shr     rax, 20h
0x18011e985  add     eax, r12d
0x18011e988  mov     [rbp+40h+var_78.fMask], eax
0x18011e98b  movaps  xmm0, xmmword ptr [rbp+40h+rectIcon.right]
0x18011e98f  add     r12d, [rsp+140h+var_CC]
0x18011e994  lea     eax, [r12+4]
0x18011e999  mov     [rsp+140h+sizeElem.cx], eax
0x18011e99d  mov     [rdi+128h], r12d
0x18011e9a4  add     esi, [rsp+140h+var_CC]
0x18011e9a8  jmp     short loc_18011E9D7
0x18011e9aa  sub     r13d, [rsp+140h+var_CC]
0x18011e9af  mov     [rbp+40h+var_90], ecx
0x18011e9b2  mov     [rbp+40h+rectIcon.left], eax
0x18011e9b5  mov     [rbp+40h+var_8C], r13d
0x18011e9b9  mov     rax, qword ptr [rsp+140h+var_D0]
0x18011e9be  shr     rax, 20h
0x18011e9c2  add     eax, r13d
0x18011e9c5  mov     [rbp+40h+rectIcon.top], eax
0x18011e9c8  movaps  xmm0, xmmword ptr [rbp+40h+var_90]
0x18011e9cc  lea     r15d, [r13-4]
0x18011e9d0  mov     [rdi+130h], r13d
0x18011e9d7  movdqu  xmmword ptr [r14+0C8h], xmm0
0x18011e9e0  mov     r8d, dword ptr [rsp+140h+var_100]
0x18011e9e5  inc     r8d
0x18011e9e8  mov     dword ptr [rsp+140h+var_100], r8d
0x18011e9ed  mov     this, [rsp+140h+var_E8]
0x18011e9f2  inc     this
0x18011e9f5  mov     [rsp+140h+var_E8], this
0x18011e9fa  mov     pDC, [rdi+6E0h]
0x18011ea01  movsxd  rax, r8d
0x18011ea04  cmp     rax, pDC
0x18011ea07  jl      loc_18011E84C
0x18011ea0d  mov     r13d, dword ptr [rbp+40h+strLabel.m_pszData]
0x18011ea11  jmp     loc_18011ECF2
0x18011ea16  test    pDC, pDC
0x18011ea19  jle     loc_18011EB87
0x18011ea1f  xor     r12d, r12d
0x18011ea22  test    r12, r12
0x18011ea25  js      loc_18011F4EC
0x18011ea2b  cmp     r12, pDC
0x18011ea2e  jge     loc_18011F4EC
0x18011ea34  mov     rax, [rdi+6D8h]
0x18011ea3b  mov     r14, [rax+r12*8]
0x18011ea3f  lea     pDC, ??_7CMFCRibbonGalleryIcon@@6B@+510h; pClass
0x18011ea46  mov     this, r14; this
0x18011ea49  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18011ea4e  test    eax, eax
0x18011ea50  jnz     loc_18011EB63
0x18011ea56  lea     pDC, ?classCMFCRibbonLabel@CMFCRibbonLabel@@2UCRuntimeClass@@B; pClass
0x18011ea5d  mov     this, r14; this
0x18011ea60  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18011ea65  test    eax, eax
0x18011ea67  jnz     loc_18011EB63
0x18011ea6d  mov     rax, [r14]
0x18011ea70  mov     pDC, qword ptr [rsp+140h+var_E0]
0x18011ea75  mov     this, r14
0x18011ea78  mov     rax, [rax+310h]
0x18011ea7f  call    cs:__guard_dispatch_icall_fptr
0x18011ea85  mov     rax, [r14]
0x18011ea88  mov     edx, 1
0x18011ea8d  mov     this, r14
0x18011ea90  mov     rax, [rax+1E8h]
0x18011ea97  call    cs:__guard_dispatch_icall_fptr
0x18011ea9d  mov     rax, [r14]
0x18011eaa0  xor     r8d, r8d
0x18011eaa3  lea     pDC, [rbp+40h+result]
0x18011eaa7  mov     this, r14
0x18011eaaa  mov     rax, [rax+238h]
0x18011eab1  call    cs:__guard_dispatch_icall_fptr
0x18011eab7  cmp     dword ptr [rax], 0
0x18011eaba  jnz     short loc_18011EAD7
0x18011eabc  cmp     dword ptr [rax+4], 0
0x18011eac0  jnz     short loc_18011EAD7
0x18011eac2  mov     rax, [r14]
0x18011eac5  xor     edx, edx
0x18011eac7  mov     this, r14
0x18011eaca  mov     rax, [rax+1E8h]
0x18011ead1  call    cs:__guard_dispatch_icall_fptr
0x18011ead7  mov     rax, [r14]
0x18011eada  mov     edx, 1
0x18011eadf  mov     this, r14
0x18011eae2  mov     rax, [rax+188h]
0x18011eae9  call    cs:__guard_dispatch_icall_fptr
0x18011eaef  mov     rax, [r14]
0x18011eaf2  mov     rect, qword ptr [rsp+140h+var_E0]
0x18011eaf7  lea     pDC, [rsp+140h+var_E8]
0x18011eafc  mov     this, r14
0x18011eaff  mov     rax, [rax+1F8h]
0x18011eb06  call    cs:__guard_dispatch_icall_fptr
0x18011eb0c  add     dword ptr [rsp+140h+var_E8], 6
0x18011eb11  mov     eax, dword ptr [rsp+140h+var_E8+4]
0x18011eb15  cmp     [rsp+140h+var_C4], eax
0x18011eb19  cmovg   eax, [rsp+140h+var_C4]
0x18011eb1e  mov     [rsp+140h+var_C4], eax
0x18011eb22  mov     rax, [r14]
0x18011eb25  mov     r8d, 1
0x18011eb2b  lea     pDC, [rsp+140h+var_D0]
0x18011eb30  mov     this, r14
0x18011eb33  mov     rax, [rax+238h]
0x18011eb3a  call    cs:__guard_dispatch_icall_fptr
0x18011eb40  cmp     ebx, [rax]
0x18011eb42  jg      short loc_18011EB63
0x18011eb44  mov     rax, [r14]
0x18011eb47  mov     r8d, 1
0x18011eb4d  lea     pDC, [rbp+40h+var_A4]
0x18011eb51  mov     this, r14
0x18011eb54  mov     rax, [rax+238h]
0x18011eb5b  call    cs:__guard_dispatch_icall_fptr
0x18011eb61  mov     ebx, [rax]
0x18011eb63  mov     ecx, dword ptr [rsp+140h+var_100]
0x18011eb67  inc     ecx
0x18011eb69  mov     dword ptr [rsp+140h+var_100], ecx
0x18011eb6d  inc     r12
0x18011eb70  mov     pDC, [rdi+6E0h]
0x18011eb77  movsxd  rax, ecx
0x18011eb7a  cmp     rax, pDC
0x18011eb7d  jl      loc_18011EA22
0x18011eb83  test    ebx, ebx
0x18011eb85  jnz     short loc_18011EBCB
0x18011eb87  cmp     [rsp+140h+var_F8], 0
0x18011eb8c  jnz     short loc_18011EBCB
0x18011eb8e  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x18011eb93  mov     pDC, rax
0x18011eb96  mov     this, [rax]
0x18011eb99  mov     rax, [this+5C8h]
0x18011eba0  mov     this, pDC
0x18011eba3  call    cs:__guard_dispatch_icall_fptr
0x18011eba9  mov     ebx, eax
0x18011ebab  add     ebx, ebx
0x18011ebad  lea     this, [rbp+40h+result]; result
0x18011ebb1  call    ?GetMenuImageSize@CMFCToolBar@@SA?AVCSize@@XZ; CMFCToolBar::GetMenuImageSize(void)
0x18011ebb6  add     ebx, [rax]
0x18011ebb8  mov     rax, [rdi+158h]
  ... truncated ...
```
