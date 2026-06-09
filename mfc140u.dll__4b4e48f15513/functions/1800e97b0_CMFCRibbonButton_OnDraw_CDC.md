# CMFCRibbonButton::OnDraw(CDC *)

- ea: `0x1800e97b0`
- end: `0x1800ea60a`
- name: `?OnDraw@CMFCRibbonButton@@UEAAXPEAVCDC@@@Z`
- size: `3674`
- prototype: `void __fastcall(CMFCRibbonButton *this, CDC *pDC)`
- caller_count: `4`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180113f30`
- `0x180118380`
- `0x18011a850`
- `0x18012dd80`

## callees

- `0x180009844`
- `0x18000e0e0`
- `0x180010510`
- `0x180010900`
- `0x18006cab0`
- `0x180091f60`
- `0x180092100`
- `0x1800e97b0`
- `0x1800ed830`
- `0x180179bc0`
- `0x18017a050`
- `0x18017a4c0`
- `0x180231d70`
- `0x1802b6310`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!SetRectEmpty` at `0x1800e99fa`
- `USER32!SetRectEmpty` at `0x1800ea25e`
- `USER32!SetRectEmpty` at `0x1800e99fa`
- `USER32!SetRectEmpty` at `0x1800ea25e`
- `USER32!IsRectEmpty` at `0x1800e97f5`
- `USER32!IsRectEmpty` at `0x1800e9b74`
- `USER32!IsRectEmpty` at `0x1800ea4c7`
- `USER32!IsRectEmpty` at `0x1800e97f5`
- `USER32!IsRectEmpty` at `0x1800e9b74`
- `USER32!IsRectEmpty` at `0x1800ea4c7`
- `USER32!InflateRect` at `0x1800e9d3c`
- `USER32!InflateRect` at `0x1800ea448`
- `USER32!InflateRect` at `0x1800e9d3c`
- `USER32!InflateRect` at `0x1800ea448`
- `USER32!OffsetRect` at `0x1800e9ba5`
- `USER32!OffsetRect` at `0x1800e9e99`
- `USER32!OffsetRect` at `0x1800ea532`
- `USER32!OffsetRect` at `0x1800e9ba5`
- `USER32!OffsetRect` at `0x1800e9e99`
- `USER32!OffsetRect` at `0x1800ea532`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=1
void __fastcall CMFCRibbonButton::OnDraw(CMFCRibbonButton *this, CDC *pDC)
{
  CRect *p_m_rect; // r14
  CMenuImages::IMAGE_STATE v5; // edi
  int v6; // eax
  int m_bDefault; // ecx
  int m_bIsHighlighted; // r15d
  int bHighlight; // eax
  int v10; // r15d
  CRect v11; // xmm0
  int m_nMenuArrowMargin; // ecx
  int v13; // eax
  int v14; // eax
  int *p_m_bQuickAccessMode; // r15
  int *p_m_bFloatyMode; // r14
  int v17; // edx
  int cx; // r13d
  CRect *p_m_rectMenu; // r14
  BOOL v20; // eax
  int v21; // ecx
  int v22; // eax
  int m_bInitialized; // ecx
  double m_dblRibbonImageScale; // xmm1_8
  int m_bIsRibbonImageScale; // edx
  double v26; // xmm0_8
  double v27; // xmm2_8
  int v28; // r14d
  int v29; // ecx
  double v30; // xmm1_8
  int v31; // edx
  double v32; // xmm0_8
  int v33; // r8d
  double v34; // xmm2_8
  CMFCVisualManager *Instance; // rax
  int v36; // r8d
  int v37; // eax
  CRect m_rect; // xmm0
  int v39; // eax
  unsigned int v40; // r15d
  CMFCVisualManager *v41; // rax
  CMFCVisualManager *v42; // rax
  int v43; // r14d
  CMFCRibbonPanelMenuBar *m_pParentMenu; // rcx
  CMFCRibbonPanel *m_pPanel; // rcx
  CFont *v46; // r14
  unsigned int v47; // r13d
  CMFCVisualManager *v48; // rax
  unsigned int (__fastcall *SetTextColor)(CDC *, unsigned int); // r13
  CMFCVisualManager *v50; // rax
  unsigned int v51; // eax
  int m_nImageOffset; // edx
  int v53; // eax
  int v54; // r15d
  CFont *(__fastcall *SelectObject)(CDC *, CFont *); // r14
  int v56; // ecx
  CMFCRibbonButton_vtbl *v57; // rax
  int v58; // r15d
  wchar_t *m_pszData; // rdx
  CSize *v60; // rax
  CSize *v61; // rax
  CMenuImages::IMAGES_IDS v62; // r14d
  CMFCRibbonBar *TopLevelRibbonBar; // rax
  int sizeImage; // [rsp+58h] [rbp-B0h]
  __int64 v65; // [rsp+60h] [rbp-A8h] BYREF
  int v66; // [rsp+68h] [rbp-A0h]
  CSize sizeImageDest; // [rsp+6Ch] [rbp-9Ch] BYREF
  int m_bIsDisabled; // [rsp+74h] [rbp-94h]
  int m_bIsDroppedDown; // [rsp+78h] [rbp-90h]
  int v70; // [rsp+7Ch] [rbp-8Ch]
  CSize sizeImageLarge; // [rsp+80h] [rbp-88h]
  CSize sizeImageSmall; // [rsp+88h] [rbp-80h] BYREF
  CMFCToolBarMenuButton dummy; // [rsp+90h] [rbp-78h] BYREF
  _BYTE rectImage_8[64]; // [rsp+1C8h] [rbp+C0h] OVERLAPPED BYREF

  p_m_rect = &this->m_rect;
  v5 = ImageBlack;
  if ( IsRectEmpty(&this->m_rect) )
    return;
  if ( this->m_bIsDefaultMenuLook && !this->m_bQuickAccessMode && !this->m_bIsLargeImage )
  {
    CMFCToolBarMenuButton::CMFCToolBarMenuButton((CMFCToolBarMenuButton *)&dummy.m_bUserButton);
    ATL::CSimpleStringT<wchar_t,1>::operator=(
      &dummy.m_strTextCustom,
      (const ATL::CSimpleStringT<wchar_t,0> *)&this->m_strText);
    *(&dummy.m_nStyle + 1) = this->m_nID;
    dummy.m_bClickedOnMenu = 1;
    dummy.m_listCommands.__vftable = (CObList_vtbl *)this->GetParentWnd(this);
    dummy.m_bQuickCustomMode = this->m_bIsRadio;
    if ( this->IsChecked(this) )
      LODWORD(dummy.m_dwdItemData) |= 0x10000u;
    v6 = this->HasMenu(this);
    m_bDefault = dummy.m_bDefault;
    if ( v6 )
      m_bDefault = 1;
    dummy.m_bDefault = m_bDefault;
    m_bIsHighlighted = this->m_bIsHighlighted;
    if ( this->IsDisabled(this) )
    {
      LODWORD(dummy.m_dwdItemData) |= 0x40000u;
      m_bIsHighlighted = this->IsFocused(this);
    }
    if ( m_bIsHighlighted || (bHighlight = 0, this->m_bIsFocused) )
      bHighlight = 1;
    CMFCToolBarMenuButton::OnDraw(
      (CMFCToolBarMenuButton *)&dummy.m_bUserButton,
      pDC,
      p_m_rect,
      0,
      1,
      0,
      bHighlight,
      1,
      1);
    CMFCToolBarMenuButton::~CMFCToolBarMenuButton((CMFCToolBarMenuButton *)&dummy.m_bUserButton);
    return;
  }
  m_bIsDisabled = this->m_bIsDisabled;
  m_bIsDroppedDown = this->m_bIsDroppedDown;
  v70 = this->m_bIsHighlighted;
  sizeImageLarge = *(CSize *)&this->m_bIsMenuHighlighted;
  v10 = this->GetDropDownImageWidth(this);
  v66 = v10;
  if ( this->m_bIsDisabled && this->HasMenu(this) )
  {
    if ( this->m_bIsDefaultCommand || ((this->m_nID + 1) & 0xFFFFFFFE) != 0 )
      this->m_bIsHighlighted = 0;
    else
      this->m_bIsDisabled = 0;
  }
  if ( this->m_bToBeClosed )
    this->m_bIsDroppedDown = 0;
  if ( this->m_bIsFocused )
  {
    this->m_bIsHighlighted = 1;
    this->m_bIsMenuHighlighted = 1;
    this->m_bIsCommandHighlighted = 1;
  }
  *(_OWORD *)&rectImage_8[16] = 0;
  SetRectEmpty((LPRECT)&rectImage_8[16]);
  if ( this->HasMenu(this) )
  {
    v11 = *p_m_rect;
    *(CRect *)&rectImage_8[16] = *p_m_rect;
    m_nMenuArrowMargin = this->m_nMenuArrowMargin;
    v13 = p_m_rect->right - m_nMenuArrowMargin - v10;
    *(_DWORD *)&rectImage_8[16] = v13;
    if ( !this->m_sizeTextRight.cx && !this->m_bQuickAccessMode )
      *(_DWORD *)&rectImage_8[16] = v13 - 2;
    *(_DWORD *)&rectImage_8[28] -= m_nMenuArrowMargin;
    if ( this->m_bIsDefaultCommand )
    {
      this->m_rectMenu = v11;
      v14 = this->m_rectMenu.right - m_nMenuArrowMargin - v10 - 1;
      this->m_rectMenu.left = v14;
      this->m_rectCommand = v11;
      this->m_rectCommand.right = v14;
      this->m_bMenuOnBottom = 0;
    }
  }
  this->GetImageSize(this, &sizeImageSmall, RibbonImageLarge);
  this->GetImageSize(this, (CSize *)&dummy, RibbonImageSmall);
  *(CRect *)&rectImage_8[48] = *p_m_rect;
  if ( this->IsApplicationButton(this)
    || (p_m_bQuickAccessMode = &this->m_bQuickAccessMode, this->m_bQuickAccessMode)
    || (p_m_bFloatyMode = &this->m_bFloatyMode, this->m_bFloatyMode) )
  {
    p_m_bFloatyMode = &this->m_bFloatyMode;
    p_m_bQuickAccessMode = &this->m_bQuickAccessMode;
    v17 = 0;
    sizeImage = 0;
    if ( this->m_bQuickAccessMode || this->m_bFloatyMode )
      goto LABEL_38;
  }
  else
  {
    v17 = 1;
    sizeImage = 1;
  }
  *(_QWORD *)&rectImage_8[32] = p_m_bFloatyMode;
  sizeImageDest.cx = v17;
  if ( this->m_bCompactMode )
  {
LABEL_38:
    cx = 0;
    goto LABEL_48;
  }
  if ( sizeImageSmall.cx || sizeImageSmall.cy )
  {
    if ( this->m_bMenuOnBottom || !this->m_bIsLargeImage )
    {
      cx = v17;
    }
    else
    {
      p_m_rectMenu = &this->m_rectMenu;
      v20 = IsRectEmpty(&this->m_rectMenu);
      v21 = v66;
      if ( !v20 )
      {
        v22 = p_m_rectMenu->left - v66;
        p_m_rectMenu->left = v22;
        this->m_rectCommand.right = v22;
      }
      OffsetRect((LPRECT)&rectImage_8[16], v21 / -2, 0);
      cx = sizeImageDest.cx;
      p_m_bFloatyMode = *(int **)&rectImage_8[32];
    }
  }
  else
  {
    cx = sizeImage;
  }
LABEL_48:
  sizeImageDest.cx = this->m_bIsLargeImage == 0;
  this->GetImageSize(this, (CSize *)&v65, (CMFCRibbonBaseElement::RibbonImageType)sizeImageDest.cx);
  if ( (*p_m_bQuickAccessMode || *p_m_bFloatyMode) && !v65 )
  {
    v65 = 0x1000000010LL;
    m_bInitialized = afxGlobalData.m_bInitialized;
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      m_bInitialized = 1;
      afxGlobalData.m_bInitialized = 1;
    }
    m_dblRibbonImageScale = afxGlobalData.m_dblRibbonImageScale;
    m_bIsRibbonImageScale = afxGlobalData.m_bIsRibbonImageScale;
    if ( afxGlobalData.m_bIsRibbonImageScale )
      v26 = afxGlobalData.m_dblRibbonImageScale;
    else
      v26 = DOUBLE_1_0;
    if ( v26 != 1.0 )
    {
      if ( !m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
        m_bIsRibbonImageScale = afxGlobalData.m_bIsRibbonImageScale;
        m_dblRibbonImageScale = afxGlobalData.m_dblRibbonImageScale;
      }
      if ( m_bIsRibbonImageScale )
        v27 = m_dblRibbonImageScale;
      else
        v27 = DOUBLE_1_0;
      LODWORD(v65) = (int)((double)(int)v65 * v27 + 0.5);
      if ( !m_bIsRibbonImageScale )
        m_dblRibbonImageScale = DOUBLE_1_0;
      HIDWORD(v65) = (int)((double)SHIDWORD(v65) * m_dblRibbonImageScale + 0.5);
    }
    v28 = 1;
  }
  else
  {
    v28 = 0;
  }
  *(CRect *)rectImage_8 = this->m_rect;
  InflateRect((LPRECT)rectImage_8, -this->m_szMargin.cx, -HIDWORD(*(_QWORD *)&this->m_szMargin));
  if ( !this->IsApplicationButton(this) )
  {
    if ( !this->m_bIsLargeImage || this->m_bTextAlwaysOnRight )
    {
      v37 = *(_DWORD *)&rectImage_8[4] + *(_DWORD *)&rectImage_8[12];
    }
    else
    {
      *(_DWORD *)rectImage_8 = (*(_DWORD *)rectImage_8 + *(_DWORD *)&rectImage_8[8]) / 2 - (int)v65 / 2;
      v36 = this->m_szMargin.cy + *(_DWORD *)&rectImage_8[4] + 1;
      *(_DWORD *)&rectImage_8[4] = v36;
      if ( cx )
        goto LABEL_90;
      v37 = v36 + *(_DWORD *)&rectImage_8[12];
    }
    v36 = v37 / 2 - SHIDWORD(v65) / 2;
    *(_DWORD *)&rectImage_8[4] = v36;
    goto LABEL_90;
  }
  v29 = afxGlobalData.m_bInitialized;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    v29 = 1;
    afxGlobalData.m_bInitialized = 1;
  }
  v30 = afxGlobalData.m_dblRibbonImageScale;
  v31 = afxGlobalData.m_bIsRibbonImageScale;
  if ( afxGlobalData.m_bIsRibbonImageScale )
    v32 = afxGlobalData.m_dblRibbonImageScale;
  else
    v32 = DOUBLE_1_0;
  if ( v32 == 1.0 )
  {
    v33 = HIDWORD(v65);
  }
  else
  {
    if ( !v29 )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
      v31 = afxGlobalData.m_bIsRibbonImageScale;
      v30 = afxGlobalData.m_dblRibbonImageScale;
    }
    if ( v31 )
      v34 = v30;
    else
      v34 = DOUBLE_1_0;
    LODWORD(v65) = (int)(v34 * 0.8 * (double)(int)v65);
    if ( !v31 )
      v30 = DOUBLE_1_0;
    v33 = (int)(v30 * 0.8 * (double)SHIDWORD(v65));
    HIDWORD(v65) = v33;
  }
  *(_DWORD *)rectImage_8 += (*(_DWORD *)&rectImage_8[8] - *(_DWORD *)rectImage_8 - (int)v65) / 2;
  *(_DWORD *)&rectImage_8[4] += (*(_DWORD *)&rectImage_8[12] - *(_DWORD *)&rectImage_8[4] - v33) / 2;
  Instance = CMFCVisualManager::GetInstance();
  OffsetRect(
    (LPRECT)rectImage_8,
    *(_QWORD *)&Instance->m_ptRibbonMainImageOffset,
    HIDWORD(*(_QWORD *)&Instance->m_ptRibbonMainImageOffset));
  v36 = *(_DWORD *)&rectImage_8[4];
LABEL_90:
  *(_DWORD *)&rectImage_8[8] = *(_DWORD *)rectImage_8 + v65;
  *(_DWORD *)&rectImage_8[12] = v36 + HIDWORD(v65);
  if ( this->m_bIsLargeImage && !this->m_bTextAlwaysOnRight && this->HasMenu(this) && this->m_bIsDefaultCommand )
  {
    m_rect = this->m_rect;
    this->m_rectMenu = m_rect;
    v39 = *(_DWORD *)&rectImage_8[12] + 3;
    this->m_rectMenu.top = *(_DWORD *)&rectImage_8[12] + 3;
    this->m_rectCommand = m_rect;
    this->m_rectCommand.bottom = v39;
    this->m_bMenuOnBottom = 1;
  }
  v40 = -1;
  if ( !this->IsApplicationButton(this) )
    v40 = this->OnFillBackground(this, pDC);
  if ( CMFCRibbonBaseElement::IsMenuMode(this) && this->IsChecked(this) && v65 )
  {
    v41 = CMFCVisualManager::GetInstance();
    *(_OWORD *)&rectImage_8[32] = *(_OWORD *)rectImage_8;
    ((void (__fastcall *)(CMFCVisualManager *, CDC *, CMFCRibbonButton *, _BYTE *))v41->OnDrawRibbonMenuCheckFrame)(
      v41,
      pDC,
      this,
      &rectImage_8[32]);
  }
  if ( v28 )
  {
    v42 = CMFCVisualManager::GetInstance();
    *(_OWORD *)&rectImage_8[32] = *(_OWORD *)rectImage_8;
    ((void (__fastcall *)(CMFCVisualManager *, CDC *, _BYTE *, _QWORD, int, int))v42->OnDrawDefaultRibbonImage)(
      v42,
      pDC,
      &rectImage_8[32],
      (unsigned int)this->m_bIsDisabled,
      this->m_bIsPressed,
      this->m_bIsHighlighted);
    goto LABEL_117;
  }
  v43 = afxGlobalData.m_bInitialized;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    v43 = 1;
    afxGlobalData.m_bInitialized = 1;
  }
  v66 = afxGlobalData.m_bIsRibbonImageScale;
  if ( CMFCRibbonBaseElement::IsMenuMode(this) && !this->m_bIsLargeImage )
  {
    m_pParentMenu = this->m_pParentMenu;
    if ( !m_pParentMenu )
      goto LABEL_111;
    m_pPanel = m_pParentMenu->m_pPanel;
    if ( !m_pPanel )
      goto LABEL_111;
    if ( !m_pPanel->IsMainPanel(m_pPanel) )
    {
      v43 = afxGlobalData.m_bInitialized;
LABEL_111:
      if ( !v43 )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      afxGlobalData.m_bIsRibbonImageScale = 0;
    }
  }
  *(_OWORD *)&rectImage_8[32] = *(_OWORD *)rectImage_8;
  ((void (__fastcall *)(CMFCRibbonButton *, CDC *, _QWORD, _BYTE *))this->DrawImage)(
    this,
    pDC,
    (unsigned int)sizeImageDest.cx,
    &rectImage_8[32]);
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  afxGlobalData.m_bIsRibbonImageScale = v66;
LABEL_117:
  if ( cx )
  {
    v46 = 0;
    *(CRect *)&rectImage_8[48] = this->m_rect;
    v47 = -1;
    if ( m_bIsDisabled && (this->m_bIsDefaultCommand || this->m_nID - 1 <= 0xFFFFFFFD) )
    {
      if ( this->m_bQuickAccessMode )
      {
        v48 = CMFCVisualManager::GetInstance();
        v48->GetRibbonQuickAccessToolBarTextColor(v48, 1);
        goto LABEL_129;
      }
      SetTextColor = pDC->SetTextColor;
      if ( v40 == -1 )
      {
        v50 = CMFCVisualManager::GetInstance();
        v40 = v50->GetToolbarDisabledTextColor(v50);
      }
      v51 = SetTextColor(pDC, v40);
    }
    else
    {
      if ( v40 == -1 )
        goto LABEL_129;
      v51 = pDC->SetTextColor(pDC, v40);
    }
    v47 = v51;
LABEL_129:
    if ( !this->m_bIsLargeImage || this->m_bTextAlwaysOnRight )
    {
      *(_DWORD *)&rectImage_8[48] = *(_DWORD *)&rectImage_8[8];
      m_nImageOffset = this->m_nImageOffset;
      if ( m_nImageOffset <= 0 )
      {
        if ( (_DWORD)v65 )
        {
          v53 = this->GetTextOffset(this);
          *(_DWORD *)&rectImage_8[48] += v53;
        }
      }
      else
      {
        *(_DWORD *)&rectImage_8[48] = m_nImageOffset + this->m_rect.left + 3 * this->m_szMargin.cx;
      }
      v54 = 32800;
      if ( this->m_bAlwaysShowDescription && *((_DWORD *)this->m_strDescription.m_pszData - 4) )
      {
        SelectObject = pDC->SelectObject;
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          afxGlobalData.m_bInitialized = 1;
        }
        v46 = SelectObject(pDC, &afxGlobalData.fontBold);
        if ( !v46 )
          AfxThrowInvalidArgException();
        v56 = 0;
        if ( (this->m_rect.bottom - this->m_rect.top - this->m_sizeTextRight.cy) / 2 >= 0 )
          v56 = (this->m_rect.bottom - this->m_rect.top - this->m_sizeTextRight.cy) / 2;
        *(_DWORD *)&rectImage_8[52] += v56;
      }
      else
      {
        v54 = 32804;
      }
      v57 = this->__vftable;
      *(_OWORD *)&rectImage_8[32] = *(_OWORD *)&rectImage_8[48];
      v58 = ((__int64 (__fastcall *)(CMFCRibbonButton *, CDC *, ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *, _BYTE *, int, int))v57->DrawRibbonText)(
              this,
              pDC,
              &this->m_strText,
              &rectImage_8[32],
              v54,
              -1);
      if ( v46 )
        pDC->SelectObject(pDC, v46);
      if ( this->m_bAlwaysShowDescription )
      {
        m_pszData = this->m_strDescription.m_pszData;
        if ( *((_DWORD *)m_pszData - 4) )
        {
          *(_DWORD *)&rectImage_8[52] += v58 + this->m_szMargin.cy;
          *(_DWORD *)&rectImage_8[56] = this->m_rect.right - this->m_szMargin.cx;
          pDC->DrawTextW(pDC, m_pszData, *((unsigned int *)m_pszData - 4), (tagRECT *)&rectImage_8[48], 32784u);
        }
      }
      if ( v58 == this->m_sizeTextRight.cy && this->m_bIsLargeImage && this->HasMenu(this) )
      {
        *(CRect *)&rectImage_8[16] = this->m_rect;
        InflateRect((LPRECT)&rectImage_8[16], -this->m_nMenuArrowMargin, -2 * this->m_nMenuArrowMargin);
        *(_DWORD *)&rectImage_8[24] -= 2;
        v60 = CMenuImages::Size((CSize *)&rectImage_8[32]);
        *(_DWORD *)&rectImage_8[20] = *(_DWORD *)&rectImage_8[28] - v60->cy;
        v61 = CMenuImages::Size((CSize *)&rectImage_8[32]);
        *(_DWORD *)&rectImage_8[28] = *(_DWORD *)&rectImage_8[20] + v61->cy;
      }
    }
    else
    {
      CMFCRibbonButton::DrawBottomText(this, (CSize *)&rectImage_8[32], pDC, 0);
      SetRectEmpty((LPRECT)&rectImage_8[16]);
    }
    if ( v47 != -1 )
      pDC->SetTextColor(pDC, v47);
  }
  if ( !this->IsApplicationButton(this) )
  {
    if ( !IsRectEmpty((const RECT *)&rectImage_8[16]) )
    {
      v62 = IdArrowDown;
      if ( CMFCRibbonBaseElement::IsMenuMode(this) )
      {
        TopLevelRibbonBar = CMFCRibbonBaseElement::GetTopLevelRibbonBar(this);
        if ( TopLevelRibbonBar && TopLevelRibbonBar->m_hWnd )
          v62 = CWnd::GetExStyle(TopLevelRibbonBar) & 0x400000;
        v62 = v62 != IdArrowDown ? IdArrowLeftLarge : IdArrowRightLarge;
      }
      *(_OWORD *)&rectImage_8[32] = *(_OWORD *)&rectImage_8[16];
      OffsetRect((LPRECT)&rectImage_8[32], 0, 1);
      sizeImageDest = 0;
      CMenuImages::Draw(pDC, v62, (const CRect *)&rectImage_8[32], ImageWhite, &sizeImageDest);
      sizeImageDest = 0;
      LOBYTE(v5) = this->m_bIsDisabled != 0;
      CMenuImages::Draw(pDC, v62, (const CRect *)&rectImage_8[16], v5, &sizeImageDest);
    }
    this->OnDrawBorder(this, pDC);
  }
  this->m_bIsDisabled = m_bIsDisabled;
  this->m_bIsDroppedDown = m_bIsDroppedDown;
  this->m_bIsHighlighted = v70;
  *(CSize *)&this->m_bIsMenuHighlighted = sizeImageLarge;
}

```

## disassembly

```asm
0x1800e97b0  mov     rax, rsp
0x1800e97b3  mov     [rax+18h], rbx
0x1800e97b7  push    rbp
0x1800e97b8  push    rsi
0x1800e97b9  push    rdi
0x1800e97ba  push    r12
0x1800e97bc  push    r13
0x1800e97be  push    r14
0x1800e97c0  push    r15
0x1800e97c2  lea     rbp, [rax-158h]
0x1800e97c9  sub     rsp, 220h
0x1800e97d0  movaps  xmmword ptr [rax-48h], xmm6
0x1800e97d4  mov     rax, cs:__security_cookie
0x1800e97db  xor     rax, rsp
0x1800e97de  mov     [rbp+150h+var_50], rax
0x1800e97e5  mov     r12, pDC
0x1800e97e8  mov     rbx, this
0x1800e97eb  lea     r14, [this+0C8h]
0x1800e97f2  mov     this, r14; lprc
0x1800e97f5  call    cs:__imp_IsRectEmpty
0x1800e97fb  xor     edi, edi
0x1800e97fd  test    eax, eax
0x1800e97ff  jnz     loc_1800EA5D5
0x1800e9805  cmp     [rbx+160h], edi
0x1800e980b  jz      loc_1800E992B
0x1800e9811  cmp     [rbx+138h], edi
0x1800e9817  jnz     loc_1800E992B
0x1800e981d  cmp     [rbx+214h], edi
0x1800e9823  jnz     loc_1800E992B
0x1800e9829  lea     this, [rbp+150h+dummy.m_bUserButton]; this
0x1800e982d  call    ??0CMFCToolBarMenuButton@@QEAA@XZ; CMFCToolBarMenuButton::CMFCToolBarMenuButton(void)
0x1800e9832  nop
0x1800e9833  lea     pDC, [rbx+0A0h]; strSrc
0x1800e983a  lea     this, [rbp+150h+dummy.m_strTextCustom]; this
0x1800e983e  call    ??4?$CSimpleStringT@_W$00@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<wchar_t,1>::operator=(ATL::CSimpleStringT<wchar_t,1> const &)
0x1800e9843  mov     eax, [rbx+118h]
0x1800e9849  mov     dword ptr [rbp+150h+dummy+2Ch], eax
0x1800e984c  lea     esi, [rdi+1]
0x1800e984f  mov     [rbp+150h+dummy.m_bClickedOnMenu], esi
0x1800e9852  mov     rax, [rbx]
0x1800e9855  mov     this, rbx
0x1800e9858  mov     rax, [rax+158h]
0x1800e985f  call    cs:__guard_dispatch_icall_fptr
0x1800e9865  mov     [rbp+150h+dummy.m_listCommands.__vftable], rax
0x1800e9869  mov     eax, [rbx+150h]
0x1800e986f  mov     [rbp+150h+dummy.m_bQuickCustomMode], eax
0x1800e9872  mov     rax, [rbx]
0x1800e9875  mov     this, rbx
0x1800e9878  mov     rax, [rax+1D0h]
0x1800e987f  call    cs:__guard_dispatch_icall_fptr
0x1800e9885  test    eax, eax
0x1800e9887  jz      short loc_1800E988E
0x1800e9889  bts     dword ptr [rbp+150h+dummy.m_dwdItemData], 10h
0x1800e988e  mov     rax, [rbx]
0x1800e9891  mov     this, rbx
0x1800e9894  mov     rax, [rax+280h]
0x1800e989b  call    cs:__guard_dispatch_icall_fptr
0x1800e98a1  mov     ecx, [rbp+150h+dummy.m_bDefault]
0x1800e98a4  test    eax, eax
0x1800e98a6  cmovnz  ecx, esi
0x1800e98a9  mov     [rbp+150h+dummy.m_bDefault], ecx
0x1800e98ac  mov     r15d, [rbx+13Ch]
0x1800e98b3  mov     rax, [rbx]
0x1800e98b6  mov     this, rbx
0x1800e98b9  mov     rax, [rax+1C8h]
0x1800e98c0  call    cs:__guard_dispatch_icall_fptr
0x1800e98c6  test    eax, eax
0x1800e98c8  jz      short loc_1800E98E5
0x1800e98ca  bts     dword ptr [rbp+150h+dummy.m_dwdItemData], 12h
0x1800e98cf  mov     rax, [rbx]
0x1800e98d2  mov     this, rbx
0x1800e98d5  mov     rax, [rax+1B8h]
0x1800e98dc  call    cs:__guard_dispatch_icall_fptr
0x1800e98e2  mov     r15d, eax
0x1800e98e5  test    r15d, r15d
0x1800e98e8  jnz     short loc_1800E98F4
0x1800e98ea  cmp     [rbx+140h], edi
0x1800e98f0  mov     eax, edi
0x1800e98f2  jz      short loc_1800E98F6
0x1800e98f4  mov     eax, esi
0x1800e98f6  mov     [rsp+250h+bGrayDisabledButtons], esi; bGrayDisabledButtons
0x1800e98fa  mov     [rsp+250h+bDrawBorder], esi; bDrawBorder
0x1800e98fe  mov     [rsp+250h+bHighlight], eax; bHighlight
0x1800e9902  mov     [rsp+250h+bCustomizeMode], edi; bCustomizeMode
0x1800e9906  mov     [rsp+250h+bHorz], esi; bHorz
0x1800e990a  xor     r9d, r9d; pImages
0x1800e990d  mov     r8, r14; rect
0x1800e9910  mov     pDC, r12; pDC
0x1800e9913  lea     this, [rbp+150h+dummy.m_bUserButton]; this
0x1800e9917  call    ?OnDraw@CMFCToolBarMenuButton@@UEAAXPEAVCDC@@AEBVCRect@@PEAVCMFCToolBarImages@@HHHHH@Z; CMFCToolBarMenuButton::OnDraw(CDC *,CRect const &,CMFCToolBarImages *,int,int,int,int,int)
0x1800e991c  nop
0x1800e991d  lea     this, [rbp+150h+dummy.m_bUserButton]; this
0x1800e9921  call    ??1CMFCToolBarMenuButton@@UEAA@XZ; CMFCToolBarMenuButton::~CMFCToolBarMenuButton(void)
0x1800e9926  jmp     loc_1800EA5D5
0x1800e992b  mov     eax, [rbx+148h]
0x1800e9931  mov     [rsp+250h+var_1E4], eax
0x1800e9935  mov     eax, [rbx+154h]
0x1800e993b  mov     [rsp+250h+var_1E0], eax
0x1800e993f  mov     eax, [rbx+13Ch]
0x1800e9945  mov     [rsp+250h+var_1DC], eax
0x1800e9949  mov     eax, [rbx+1F8h]
0x1800e994f  mov     [rsp+250h+sizeImageLarge.cx], eax
0x1800e9953  mov     eax, [rbx+1FCh]
0x1800e9959  mov     [rsp+250h+sizeImageLarge.cy], eax
0x1800e995d  mov     rax, [rbx]
0x1800e9960  mov     this, rbx
0x1800e9963  mov     rax, [rax+490h]
0x1800e996a  call    cs:__guard_dispatch_icall_fptr
0x1800e9970  mov     r15d, eax
0x1800e9973  mov     dword ptr [rsp+250h+var_1F4+4], eax
0x1800e9977  mov     esi, 1
0x1800e997c  cmp     [rbx+148h], edi
0x1800e9982  jz      short loc_1800E99C0
0x1800e9984  mov     this, [rbx]
0x1800e9987  mov     rax, [this+280h]
0x1800e998e  mov     this, rbx
0x1800e9991  call    cs:__guard_dispatch_icall_fptr
0x1800e9997  test    eax, eax
0x1800e9999  jz      short loc_1800E99C0
0x1800e999b  cmp     [rbx+1ECh], edi
0x1800e99a1  jnz     short loc_1800E99BA
0x1800e99a3  mov     eax, [rbx+118h]
0x1800e99a9  add     eax, esi
0x1800e99ab  test    eax, 0FFFFFFFEh
0x1800e99b0  jnz     short loc_1800E99BA
0x1800e99b2  mov     [rbx+148h], edi
0x1800e99b8  jmp     short loc_1800E99C0
0x1800e99ba  mov     [rbx+13Ch], edi
0x1800e99c0  cmp     [rbx+20Ch], edi
0x1800e99c6  jz      short loc_1800E99CE
0x1800e99c8  mov     [rbx+154h], edi
0x1800e99ce  cmp     [rbx+140h], edi
0x1800e99d4  jz      short loc_1800E99E8
0x1800e99d6  mov     [rbx+13Ch], esi
0x1800e99dc  mov     [rbx+1F8h], esi
0x1800e99e2  mov     [rbx+1FCh], esi
0x1800e99e8  xorps   xmm0, xmm0
0x1800e99eb  movdqa  xmmword ptr [rbp+150h+rectMenuArrow.right], xmm0
0x1800e99f3  lea     this, [rbp+150h+rectMenuArrow.right]; lprc
0x1800e99fa  call    cs:__imp_SetRectEmpty
0x1800e9a00  mov     rax, [rbx]
0x1800e9a03  mov     this, rbx
0x1800e9a06  mov     rax, [rax+280h]
0x1800e9a0d  call    cs:__guard_dispatch_icall_fptr
0x1800e9a13  test    eax, eax
0x1800e9a15  jz      loc_1800E9A9F
0x1800e9a1b  movups  xmm0, xmmword ptr [r14]
0x1800e9a1f  movdqa  xmmword ptr [rbp+150h+rectMenuArrow.right], xmm0
0x1800e9a27  mov     ecx, [rbx+1C0h]
0x1800e9a2d  mov     eax, [r14+8]
0x1800e9a31  sub     eax, ecx
0x1800e9a33  sub     eax, r15d
0x1800e9a36  mov     [rbp+150h+rectMenuArrow.right], eax
0x1800e9a3c  cmp     [rbx+180h], edi
0x1800e9a42  jnz     short loc_1800E9A55
0x1800e9a44  cmp     [rbx+138h], edi
0x1800e9a4a  jnz     short loc_1800E9A55
0x1800e9a4c  add     eax, 0FFFFFFFEh
0x1800e9a4f  mov     [rbp+150h+rectMenuArrow.right], eax
0x1800e9a55  mov     rax, qword ptr [rbp+150h+rectWhite.left]
0x1800e9a5c  shr     rax, 20h
0x1800e9a60  sub     eax, ecx
0x1800e9a62  mov     [rbp+150h+rectWhite.top], eax
0x1800e9a68  cmp     [rbx+1ECh], edi
0x1800e9a6e  jz      short loc_1800E9A9F
0x1800e9a70  movdqu  xmmword ptr [rbx+198h], xmm0
0x1800e9a78  mov     eax, [rbx+1A0h]
0x1800e9a7e  sub     eax, ecx
0x1800e9a80  sub     eax, r15d
0x1800e9a83  sub     eax, esi
0x1800e9a85  mov     [rbx+198h], eax
0x1800e9a8b  movdqu  xmmword ptr [rbx+1A8h], xmm0
0x1800e9a93  mov     [rbx+1B0h], eax
0x1800e9a99  mov     [rbx+1F4h], edi
0x1800e9a9f  mov     rax, [rbx]
0x1800e9aa2  xor     r8d, r8d
0x1800e9aa5  lea     pDC, [rbp+150h+sizeImageSmall]
0x1800e9aa9  mov     this, rbx
0x1800e9aac  mov     rax, [rax+238h]
0x1800e9ab3  call    cs:__guard_dispatch_icall_fptr
0x1800e9ab9  mov     rax, [rbx]
0x1800e9abc  mov     r8d, esi
0x1800e9abf  lea     pDC, [rbp+150h+dummy]
0x1800e9ac3  mov     this, rbx
0x1800e9ac6  mov     rax, [rax+238h]
0x1800e9acd  call    cs:__guard_dispatch_icall_fptr
0x1800e9ad3  movups  xmm0, xmmword ptr [r14]
0x1800e9ad7  movdqu  xmmword ptr [rbp+150h+rectText.right], xmm0
0x1800e9adf  mov     rax, [rbx]
0x1800e9ae2  mov     this, rbx
0x1800e9ae5  mov     rax, [rax+4B0h]
0x1800e9aec  call    cs:__guard_dispatch_icall_fptr
0x1800e9af2  test    eax, eax
0x1800e9af4  jnz     short loc_1800E9B16
0x1800e9af6  lea     r15, [rbx+138h]
0x1800e9afd  cmp     [r15], edi
0x1800e9b00  jnz     short loc_1800E9B16
0x1800e9b02  lea     r14, [rbx+134h]
0x1800e9b09  cmp     [r14], edi
0x1800e9b0c  jnz     short loc_1800E9B16
0x1800e9b0e  mov     edx, esi
0x1800e9b10  mov     [rsp+250h+sizeImage.cx], edx
0x1800e9b14  jmp     short loc_1800E9B38
0x1800e9b16  lea     rax, [rbx+138h]
0x1800e9b1d  lea     this, [rbx+134h]
0x1800e9b24  mov     r14, this
0x1800e9b27  mov     r15, rax
0x1800e9b2a  mov     edx, edi
0x1800e9b2c  mov     [rsp+250h+sizeImage.cx], edx
0x1800e9b30  cmp     [rax], edi
0x1800e9b32  jnz     short loc_1800E9B4B
0x1800e9b34  cmp     [this], edi
0x1800e9b36  jnz     short loc_1800E9B4B
0x1800e9b38  mov     qword ptr [rbp+150h+rectWhite.right], r14
0x1800e9b3f  mov     [rsp+250h+sizeImageDest.cx], edx
0x1800e9b43  cmp     [rbx+12Ch], edi
0x1800e9b49  jz      short loc_1800E9B50
0x1800e9b4b  mov     r13d, edi
0x1800e9b4e  jmp     short loc_1800E9BC3
0x1800e9b50  cmp     [rbp+150h+sizeImageSmall.cx], edi
0x1800e9b53  jnz     short loc_1800E9B5A
0x1800e9b55  cmp     [rbp+150h+sizeImageSmall.cy], edi
0x1800e9b58  jz      short loc_1800E9BB9
0x1800e9b5a  cmp     [rbx+1F4h], edi
0x1800e9b60  jnz     short loc_1800E9BC0
0x1800e9b62  cmp     [rbx+214h], edi
0x1800e9b68  jz      short loc_1800E9BC0
0x1800e9b6a  lea     r14, [rbx+198h]
0x1800e9b71  mov     this, r14; lprc
0x1800e9b74  call    cs:__imp_IsRectEmpty
0x1800e9b7a  mov     ecx, dword ptr [rsp+250h+var_1F4+4]
0x1800e9b7e  test    eax, eax
0x1800e9b80  jnz     short loc_1800E9B90
0x1800e9b82  mov     eax, [r14]
0x1800e9b85  sub     eax, ecx
0x1800e9b87  mov     [r14], eax
0x1800e9b8a  mov     [rbx+1B0h], eax
0x1800e9b90  mov     eax, ecx
0x1800e9b92  cdq
0x1800e9b93  sub     eax, edx
0x1800e9b95  sar     eax, 1
0x1800e9b97  neg     eax
0x1800e9b99  mov     edx, eax; dx
0x1800e9b9b  xor     r8d, r8d; dy
0x1800e9b9e  lea     this, [rbp+150h+rectMenuArrow.right]; lprc
0x1800e9ba5  call    cs:__imp_OffsetRect
0x1800e9bab  mov     r13d, [rsp+250h+sizeImageDest.cx]
0x1800e9bb0  mov     r14, qword ptr [rbp+150h+rectWhite.right]
0x1800e9bb7  jmp     short loc_1800E9BC3
0x1800e9bb9  mov     r13d, [rsp+250h+sizeImage.cx]
0x1800e9bbe  jmp     short loc_1800E9BC3
0x1800e9bc0  mov     r13d, edx
0x1800e9bc3  mov     ecx, edi
0x1800e9bc5  cmp     [rbx+214h], edi
0x1800e9bcb  setz    cl
0x1800e9bce  mov     [rsp+250h+sizeImageDest.cx], ecx
0x1800e9bd2  mov     rax, [rbx]
0x1800e9bd5  mov     r8d, ecx
0x1800e9bd8  lea     pDC, [rsp+250h+var_1F8]
0x1800e9bdd  mov     this, rbx
0x1800e9be0  mov     rax, [rax+238h]
0x1800e9be7  call    cs:__guard_dispatch_icall_fptr
0x1800e9bed  movsd   xmm6, cs:__real@3ff0000000000000
0x1800e9bf5  cmp     [r15], edi
0x1800e9bf8  jnz     short loc_1800E9C03
0x1800e9bfa  cmp     [r14], edi
0x1800e9bfd  jz      loc_1800E9D10
0x1800e9c03  cmp     [rsp+250h+var_1F8], edi
0x1800e9c07  jnz     loc_1800E9D10
0x1800e9c0d  cmp     dword ptr [rsp+250h+var_1F4], edi
0x1800e9c11  jnz     loc_1800E9D10
0x1800e9c17  mov     eax, 10h
0x1800e9c1c  mov     [rsp+250h+var_1F8], eax
0x1800e9c20  mov     dword ptr [rsp+250h+var_1F4], eax
0x1800e9c24  mov     rax, qword ptr [rsp+250h+var_1F8]
0x1800e9c29  mov     qword ptr [rsp+250h+var_1F8], rax
0x1800e9c2e  mov     ecx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized; AFX_GLOBAL_DATA afxGlobalData ...
0x1800e9c34  test    ecx, ecx
0x1800e9c36  jnz     short loc_1800E9C4C
0x1800e9c38  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1800e9c3f  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800e9c44  mov     ecx, esi
0x1800e9c46  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ecx; AFX_GLOBAL_DATA afxGlobalData ...
0x1800e9c4c  movsd   xmm1, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_dblRibbonImageScale; AFX_GLOBAL_DATA afxGlobalData ...
0x1800e9c54  mov     edx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bIsRibbonImageScale; AFX_GLOBAL_DATA afxGlobalData ...
0x1800e9c5a  test    edx, edx
0x1800e9c5c  jz      short loc_1800E9C63
0x1800e9c5e  movaps  xmm0, xmm1
0x1800e9c61  jmp     short loc_1800E9C66
0x1800e9c63  movaps  xmm0, xmm6
0x1800e9c66  ucomisd xmm0, xmm6
0x1800e9c6a  jp      short loc_1800E9C72
0x1800e9c6c  jz      loc_1800E9D0B
0x1800e9c72  test    ecx, ecx
0x1800e9c74  jnz     short loc_1800E9C98
0x1800e9c76  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1800e9c7d  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800e9c82  mov     ecx, esi
0x1800e9c84  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ecx; AFX_GLOBAL_DATA afxGlobalData ...
0x1800e9c8a  mov     edx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bIsRibbonImageScale; AFX_GLOBAL_DATA afxGlobalData ...
  ... truncated ...
```
