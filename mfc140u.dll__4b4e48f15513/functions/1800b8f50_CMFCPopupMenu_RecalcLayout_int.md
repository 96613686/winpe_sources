# CMFCPopupMenu::RecalcLayout(int)

- ea: `0x1800b8f50`
- end: `0x1800b9f5a`
- name: `?RecalcLayout@CMFCPopupMenu@@UEAAXH@Z`
- size: `4106`
- prototype: `void __fastcall(CMFCPopupMenu *this, int __formal)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update`

## callees

- `0x180009844`
- `0x180010900`
- `0x18002f840`
- `0x18006cab0`
- `0x180090b30`
- `0x1800b8f50`
- `0x1800ba970`
- `0x18023f820`
- `0x180280be0`
- `0x1802afdb0`
- `0x1802afe10`
- `0x1802b6310`
- `0x1802b66c0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1800b91e2`
- `USER32!GetSystemMetrics` at `0x1800b9205`
- `USER32!GetSystemMetrics` at `0x1800b925e`
- `USER32!GetSystemMetrics` at `0x1800b926c`
- `USER32!GetSystemMetrics` at `0x1800b9cb0`
- `USER32!GetSystemMetrics` at `0x1800b9cd0`
- `USER32!GetSystemMetrics` at `0x1800b91e2`
- `USER32!GetSystemMetrics` at `0x1800b9205`
- `USER32!GetSystemMetrics` at `0x1800b925e`
- `USER32!GetSystemMetrics` at `0x1800b926c`
- `USER32!GetSystemMetrics` at `0x1800b9cb0`
- `USER32!GetSystemMetrics` at `0x1800b9cd0`
- `USER32!GetMonitorInfoW` at `0x1800b9030`
- `USER32!GetMonitorInfoW` at `0x1800b9030`
- `USER32!MonitorFromPoint` at `0x1800b9023`
- `USER32!MonitorFromPoint` at `0x1800b9023`
- `USER32!SystemParametersInfoW` at `0x1800b9056`
- `USER32!SystemParametersInfoW` at `0x1800b9056`
- `USER32!IntersectRect` at `0x1800b9e4e`
- `USER32!IntersectRect` at `0x1800b9ec2`
- `USER32!IntersectRect` at `0x1800b9e4e`
- `USER32!IntersectRect` at `0x1800b9ec2`
- `USER32!SetRectEmpty` at `0x1800b95da`
- `USER32!SetRectEmpty` at `0x1800b95da`
- `USER32!GetWindowRect` at `0x1800b9722`
- `USER32!GetWindowRect` at `0x1800b9def`
- `USER32!GetWindowRect` at `0x1800b9722`
- `USER32!GetWindowRect` at `0x1800b9def`
- `USER32!SendMessageW` at `0x1800b9309`
- `USER32!SendMessageW` at `0x1800b936d`
- `USER32!SendMessageW` at `0x1800b9309`
- `USER32!SendMessageW` at `0x1800b936d`
- `USER32!InvalidateRect` at `0x1800b9e6a`
- `USER32!InvalidateRect` at `0x1800b9ede`
- `USER32!InvalidateRect` at `0x1800b9e6a`
- `USER32!InvalidateRect` at `0x1800b9ede`
- `USER32!IsWindow` at `0x1800b8f9f`
- `USER32!IsWindow` at `0x1800b8fbd`
- `USER32!IsWindow` at `0x1800b8f9f`
- `USER32!IsWindow` at `0x1800b8fbd`
- `USER32!CopyRect` at `0x1800b9042`
- `USER32!CopyRect` at `0x1800b9042`
- `USER32!ClientToScreen` at `0x1800b9962`
- `USER32!ClientToScreen` at `0x1800b997c`
- `USER32!ClientToScreen` at `0x1800b9bd3`
- `USER32!ClientToScreen` at `0x1800b9bf9`
- `USER32!ClientToScreen` at `0x1800b9962`
- `USER32!ClientToScreen` at `0x1800b997c`
- `USER32!ClientToScreen` at `0x1800b9bd3`
- `USER32!ClientToScreen` at `0x1800b9bf9`
- `USER32!IsRectEmpty` at `0x1800b91f8`
- `USER32!IsRectEmpty` at `0x1800b9cc4`
- `USER32!IsRectEmpty` at `0x1800b91f8`
- `USER32!IsRectEmpty` at `0x1800b9cc4`
- `USER32!UpdateWindow` at `0x1800b9e74`
- `USER32!UpdateWindow` at `0x1800b9ee8`
- `USER32!UpdateWindow` at `0x1800b9e74`
- `USER32!UpdateWindow` at `0x1800b9ee8`
- `USER32!RedrawWindow` at `0x1800b964d`
- `USER32!RedrawWindow` at `0x1800b9f27`
- `USER32!RedrawWindow` at `0x1800b964d`
- `USER32!RedrawWindow` at `0x1800b9f27`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __fastcall CMFCPopupMenu::RecalcLayout(CMFCPopupMenu *this, __int64 __formal)
{
  __int64 v3; // rax
  HWND__ *m_hWnd; // rcx
  __int64 v5; // r13
  CMFCToolBarMenuButton *m_pParentBtn; // rcx
  int v7; // ebx
  CPoint m_ptLocation; // rcx
  HMONITOR v9; // rax
  int v10; // r12d
  unsigned int v11; // eax
  int v12; // r8d
  int v13; // eax
  int v14; // edx
  int v15; // r11d
  int x; // r10d
  bool v17; // zf
  int cx; // r9d
  int v19; // eax
  int v20; // r10d
  int v21; // ecx
  int v22; // ecx
  __int64 y; // r9
  int v24; // ecx
  int v25; // eax
  int v26; // ecx
  int v27; // ecx
  int v28; // eax
  int v29; // ecx
  int v30; // eax
  unsigned int v31; // r14d
  int cy; // esi
  CMFCPopupMenu::LOGO_LOCATION m_nLogoLocation; // ecx
  __int32 v34; // ecx
  int v35; // ebx
  int m_bInitialized; // ecx
  int m_nMaxToolTipWidth; // eax
  int m_nMaxHeight; // r15d
  int v39; // eax
  CWnd *v40; // r15
  bool v41; // cc
  int v42; // edx
  unsigned int v43; // eax
  int v44; // eax
  CMFCToolBarMenuButton *v45; // rbx
  CMFCMenuBar *m_pWndParent; // rbx
  int v47; // eax
  int v48; // eax
  CMFCToolBarMenuButton *v49; // rax
  int v50; // ecx
  int v51; // ecx
  int v52; // eax
  int v53; // ecx
  int v54; // eax
  int v55; // eax
  CMFCToolBarMenuButton *v56; // rdx
  int v57; // ecx
  int v58; // ecx
  int v59; // ecx
  int v60; // ecx
  CMFCVisualManager *Instance; // rax
  CMFCPopupMenu *ParentPopupMenu; // rax
  CMFCPopupMenu *v63; // r13
  CMFCToolBarMenuButton *v64; // rbx
  CWnd *v65; // rcx
  int v66; // eax
  int v67; // ecx
  CMFCPopupMenu *v68; // rax
  CWnd *v69; // r13
  HWND v70; // rcx
  CMFCRibbonBaseElement *m_pParentRibbonElement; // rax
  int v72; // ebx
  int v73; // edx
  int v74; // eax
  int v75; // edx
  CMFCPopupMenu::DROP_DIRECTION v76; // r8d
  int v77; // ecx
  int v78; // ecx
  int v79; // r13d
  CMFCPopupMenu_vtbl *v80; // rax
  __int64 v81; // rax
  __int64 v82; // rbx
  HWND v83; // rcx
  int v84; // edx
  int v85; // r9d
  CMFCToolBarMenuButton *v86; // rbx
  CObject *v87; // rbx
  int v88; // r8d
  CMFCPopupMenu::DROP_DIRECTION v89; // eax
  __int64 v90; // r12
  int v91; // edx
  int v92; // ebx
  int v93; // eax
  CMFCToolBarMenuButton *v94; // rax
  CMFCToolBarMenuButton *v95; // rcx
  CMFCToolBarMenuButton *v96; // rcx
  int bottom; // eax
  CMFCPopupMenu::DROP_DIRECTION v98; // eax
  int v99; // edx
  CMFCPopupMenu::ANIMATION_TYPE AnimationType; // eax
  int v101; // ecx
  int m_iShadowSize; // eax
  CMFCToolBarMenuButton *v103; // rbx
  int m_bShown; // esi
  HWND__ *v105; // rcx
  CWnd *v106; // rbx
  int v107; // edx
  int v108; // eax
  int v109; // r9d
  int size; // [rsp+48h] [rbp-79h]
  unsigned __int64 m_sizeCurrent; // [rsp+50h] [rbp-71h]
  int v112; // [rsp+58h] [rbp-69h]
  int v113; // [rsp+58h] [rbp-69h]
  int v114; // [rsp+5Ch] [rbp-65h]
  _BYTE rectMenu[48]; // [rsp+60h] [rbp-61h] OVERLAPPED BYREF
  CRect rectShadowBottom; // [rsp+90h] [rbp-31h] BYREF
  _BYTE rectQCParent[61]; // [rsp+A0h] [rbp-21h] OVERLAPPED BYREF

  v3 = ((__int64 (__fastcall *)(CMFCPopupMenu *, __int64))this->GetMenuBar)(this, __formal);
  m_hWnd = this->m_hWnd;
  v5 = v3;
  *(_QWORD *)&rectShadowBottom.right = v3;
  if ( !IsWindow(m_hWnd) || !v5 || !IsWindow(*(HWND *)(v5 + 64)) || *(_DWORD *)(v5 + 4380) )
    return;
  m_pParentBtn = this->m_pParentBtn;
  if ( !m_pParentBtn || !m_pParentBtn->IsTearOffMenu(m_pParentBtn) || (v7 = 1, CMFCToolBar::m_bCustomizeMode) )
    v7 = 0;
  m_ptLocation = this->m_ptLocation;
  *(_DWORD *)&rectQCParent[40] = 40;
  *(_OWORD *)&rectMenu[24] = 0;
  v9 = MonitorFromPoint(m_ptLocation.tagPOINT, 2u);
  if ( GetMonitorInfoW(v9, (LPMONITORINFO)&rectQCParent[40]) )
    CopyRect((LPRECT)&rectMenu[24], (const RECT *)&rectQCParent[60]);
  else
    SystemParametersInfoW(0x30u, 0, &rectMenu[24], 0);
  v10 = this->GetBorderSize(this);
  v11 = CWnd::GetExStyle(this);
  v12 = *(_DWORD *)&rectMenu[36];
  v13 = v11 & 0x400000;
  v14 = *(_DWORD *)&rectMenu[32];
  v15 = *(_DWORD *)&rectMenu[24];
  size = v13;
  if ( this->m_bResizeTracking )
  {
    x = this->m_ptLocation.x;
    v17 = v13 == 0;
    cx = this->m_sizeCurrent.cx;
    v19 = 2 * v10;
    if ( v17 )
    {
      v21 = *(_DWORD *)&rectMenu[32] - v19;
      v19 = 2 * v10;
      v22 = v21 - x;
      if ( cx >= v22 )
        cx = v22;
    }
    else
    {
      v20 = x - v19 - *(_DWORD *)&rectMenu[24];
      if ( cx >= v20 )
        cx = v20;
    }
    this->m_sizeCurrent.cx = cx;
    y = (unsigned int)this->m_ptLocation.y;
    v24 = this->m_rectResize.top - this->m_rectResize.bottom - y - v19;
    v25 = this->m_sizeCurrent.cy;
    v26 = v12 + v24;
    if ( v25 >= v26 )
      v25 = v26;
    this->m_sizeCurrent.cy = v25;
  }
  else
  {
    y = (unsigned int)this->m_ptLocation.y;
  }
  v27 = this->m_ptLocation.x;
  v28 = v14;
  if ( v27 < v14 )
    v28 = this->m_ptLocation.x;
  if ( v15 <= v28 )
  {
    if ( v27 < v14 )
      v14 = this->m_ptLocation.x;
    v15 = v14;
  }
  this->m_ptLocation.x = v15;
  if ( !this->m_pParentBtn )
  {
    v29 = *(_DWORD *)&rectMenu[28];
    v30 = v12;
    if ( (int)y < v12 )
      v30 = y;
    if ( *(int *)&rectMenu[28] <= v30 )
    {
      if ( (int)y < v12 )
        v12 = y;
      v29 = v12;
    }
    this->m_ptLocation.y = v29;
  }
  m_sizeCurrent = (unsigned __int64)this->m_sizeCurrent;
  if ( !this->m_bResizeTracking && !this->m_bWasResized )
    m_sizeCurrent = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)v5 + 1368LL))(
                                 v5,
                                 &rectMenu[8],
                                 1,
                                 y);
  *(_DWORD *)rectMenu = 0;
  if ( this->m_bResizeTracking || this->m_bWasResized )
  {
    cy = HIDWORD(m_sizeCurrent);
    v31 = m_sizeCurrent;
  }
  else
  {
    v31 = 2 * v10 + m_sizeCurrent;
    cy = 2 * v10 + HIDWORD(m_sizeCurrent);
    m_sizeCurrent = __PAIR64__(cy, v31);
    if ( this->m_bScrollable && this->m_bShowScrollBar )
    {
      v31 += GetSystemMetrics(2);
      LODWORD(m_sizeCurrent) = v31;
      if ( !IsRectEmpty(&this->m_rectResize) )
        this->m_rectResize.right += GetSystemMetrics(2);
      *(_DWORD *)rectMenu = 1;
    }
    m_nLogoLocation = this->m_nLogoLocation;
    if ( m_nLogoLocation && (v34 = m_nLogoLocation - 1) != 0 )
    {
      if ( (unsigned int)(v34 - 1) <= 1 )
      {
        cy += this->m_iLogoWidth;
        HIDWORD(m_sizeCurrent) = cy;
      }
    }
    else
    {
      v31 += this->m_iLogoWidth;
      LODWORD(m_sizeCurrent) = v31;
    }
  }
  if ( this->m_pMenuCustomizationPage )
  {
    v35 = cy + GetSystemMetrics(51);
    cy = v35 + 2 * GetSystemMetrics(6) + 5;
    HIDWORD(m_sizeCurrent) = cy;
  }
  else if ( v7 )
  {
    *(_DWORD *)&rectMenu[8] = v10;
    cy += 10;
    *(_DWORD *)&rectMenu[12] = v10;
    HIDWORD(m_sizeCurrent) = cy;
    *(_DWORD *)&rectMenu[16] = v31 - 2 * v10 + v10;
    *(_DWORD *)&rectMenu[20] = v10 + 10;
    this->m_rectTearOffCaption = *(CRect *)&rectMenu[8];
    if ( !CMFCToolBar::m_bCustomizeMode && (this == (CMFCPopupMenu *)-6232LL || !this->m_wndToolTip.m_hWnd) )
    {
      ((void (__fastcall *)(CToolTipCtrl *, CMFCPopupMenu *, _QWORD, __int64))this->m_wndToolTip.Create)(
        &this->m_wndToolTip,
        this,
        0,
        y);
      SendMessageW(this->m_wndToolTip.m_hWnd, 0x401u, 1u, 0);
      m_bInitialized = afxGlobalData.m_bInitialized;
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        m_bInitialized = 1;
        afxGlobalData.m_bInitialized = 1;
      }
      m_nMaxToolTipWidth = afxGlobalData.m_nMaxToolTipWidth;
      if ( afxGlobalData.m_nMaxToolTipWidth != -1 )
      {
        if ( !m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          m_nMaxToolTipWidth = afxGlobalData.m_nMaxToolTipWidth;
          afxGlobalData.m_bInitialized = 1;
        }
        SendMessageW(this->m_wndToolTip.m_hWnd, 0x418u, 0, m_nMaxToolTipWidth);
      }
      CToolTipCtrl::AddTool(&this->m_wndToolTip, this, 0x3E9Cu, &this->m_rectTearOffCaption, 1u);
    }
  }
  m_nMaxHeight = this->m_nMaxHeight;
  if ( m_nMaxHeight != -1 && cy > m_nMaxHeight )
  {
    if ( !this->m_bResizeTracking && !this->m_bWasResized )
    {
      v39 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 1720LL))(v5);
      this->m_bHasBeenResized = 1;
      cy = 2 * v10 - (m_nMaxHeight - 2 * v10) % v39 + m_nMaxHeight - 2 * v10 + 2;
      HIDWORD(m_sizeCurrent) = cy;
    }
    this->m_bScrollable = 1;
  }
  v40 = 0;
  if ( this->m_bIsResizable )
  {
    v41 = this->m_sizeMinResize.cx <= 0;
    v42 = 9;
    *(_DWORD *)&rectMenu[8] = v10;
    if ( !v41 )
      v42 = 12;
    v43 = v31 - 2 * v10;
    if ( this->m_bIsResizeBarOnTop )
    {
      *(_DWORD *)&rectMenu[12] = v10;
      *(_DWORD *)&rectMenu[16] = v10 + v43;
      v44 = v42 + v10;
    }
    else
    {
      *(_DWORD *)&rectMenu[12] = cy - v10;
      *(_DWORD *)&rectMenu[16] = v10 + v43;
      v44 = cy - v10 + v42;
    }
    *(_DWORD *)&rectMenu[20] = v44;
    cy += v42;
    HIDWORD(m_sizeCurrent) = cy;
    this->m_rectResize = *(CRect *)&rectMenu[8];
  }
  if ( size || (v112 = 0, this->m_bRightAlign) )
    v112 = 1;
  v45 = this->m_pParentBtn;
  if ( !v45 )
    goto LABEL_100;
  m_pWndParent = (CMFCMenuBar *)v45->m_pWndParent;
  if ( !m_pWndParent )
    goto LABEL_100;
  if ( !CObject::IsKindOf(m_pWndParent, &CMFCMenuBar::classCMFCMenuBar) )
    goto LABEL_100;
  v40 = m_pWndParent;
  if ( !m_pWndParent->IsFloating(m_pWndParent) )
    goto LABEL_100;
  v47 = CMFCMenuBar::GetFloatPopupDirection(m_pWndParent, this->m_pParentBtn) - 2;
  if ( !v47 )
  {
    v60 = this->m_pParentBtn->m_rect.top + this->m_ptLocationInitial.y - this->m_pParentBtn->m_rect.bottom - cy;
    this->m_DropDirection = DROP_DIRECTION_TOP;
    v59 = v60 + 1;
LABEL_99:
    this->m_ptLocation.y = v59;
    goto LABEL_100;
  }
  v48 = v47 - 1;
  if ( !v48 )
  {
    v56 = this->m_pParentBtn;
    v57 = this->m_ptLocationInitial.x;
    if ( size )
      v58 = v56->m_rect.left + v57 - v56->m_rect.right;
    else
      v58 = v56->m_rect.right - v56->m_rect.left + v57;
    this->m_ptLocation.x = v58;
    v59 = v56->m_rect.top + this->m_ptLocationInitial.y - v56->m_rect.bottom + 1;
    this->m_DropDirection = DROP_DIRECTION_RIGHT;
    goto LABEL_99;
  }
  if ( v48 == 1 )
  {
    v49 = this->m_pParentBtn;
    v50 = this->m_ptLocationInitial.y - v49->m_rect.bottom;
    LODWORD(v49) = v49->m_rect.top + 1;
    this->m_DropDirection = DROP_DIRECTION_LEFT;
    v51 = (_DWORD)v49 + v50;
    v52 = this->m_ptLocationInitial.x;
    this->m_ptLocation.y = v51;
    if ( size )
    {
      v53 = *(_DWORD *)&rectMenu[32];
      v54 = v31 + v52;
      this->m_ptLocation.x = v54;
      if ( v54 > v53 )
        goto LABEL_93;
    }
    else
    {
      v53 = *(_DWORD *)&rectMenu[24];
      v55 = v52 - v31;
      this->m_ptLocation.x = v55;
      if ( v55 < v53 )
      {
LABEL_93:
        this->m_DropDirection = DROP_DIRECTION_NONE;
        this->m_ptLocation.x = v53;
      }
    }
  }
LABEL_100:
  *(_OWORD *)&rectQCParent[8] = 0;
  SetRectEmpty((LPRECT)&rectQCParent[8]);
  v114 = 0;
  Instance = CMFCVisualManager::GetInstance();
  if ( Instance->IsOfficeXPStyleMenus(Instance) )
  {
    ParentPopupMenu = CMFCPopupMenu::GetParentPopupMenu(this);
    v63 = ParentPopupMenu;
    if ( ParentPopupMenu )
    {
      v64 = this->m_pParentBtn;
      if ( v64 )
      {
        if ( v64->m_bQuickCustomMode )
        {
          if ( !size )
            RedrawWindow(ParentPopupMenu->m_hWnd, 0, 0, 0x105u);
          if ( v63->m_bQuickCusomize )
          {
            if ( !this->m_bQuickCusomize )
            {
              *(CRect *)&rectQCParent[8] = v64->m_rect;
              v65 = v64->m_pWndParent;
              if ( v65 )
              {
                if ( v65->m_hWnd )
                {
                  CWnd::ClientToScreen(v65, (tagRECT *)&rectQCParent[8]);
                  v17 = this->m_DropDirection == DROP_DIRECTION_LEFT;
                  this->m_ptLocation.y = *(_DWORD *)&rectQCParent[12];
                  v114 = 1;
                  if ( v17 )
                  {
                    v66 = *(_DWORD *)&rectQCParent[8] - v31;
                    if ( size )
                      v66 = *(_DWORD *)&rectQCParent[8];
                    this->m_ptLocation.x = v66;
                  }
                  else
                  {
                    v67 = *(_DWORD *)&rectQCParent[16];
                    if ( size )
                      v67 = *(_DWORD *)&rectQCParent[16] + v31;
                    this->m_ptLocation.x = v67;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( size && (int)(this->m_ptLocation.x - v31) < *(int *)&rectMenu[24]
    || !v112 && (int)(v31 + this->m_ptLocation.x) > *(int *)&rectMenu[32] )
  {
    v68 = CMFCPopupMenu::GetParentPopupMenu(this);
    v69 = v68;
    if ( v68 )
    {
      v70 = v68->m_hWnd;
      *(_OWORD *)&rectMenu[8] = 0;
      GetWindowRect(v70, (LPRECT)&rectMenu[8]);
      m_pParentRibbonElement = this->m_pParentRibbonElement;
      v72 = *(_DWORD *)&rectMenu[8] - v31;
      if ( size )
        v72 = v31 + *(_DWORD *)&rectMenu[16];
      this->m_ptLocation.x = v72;
      if ( !m_pParentRibbonElement || CMFCRibbonBaseElement::IsMenuMode(m_pParentRibbonElement) )
      {
        v73 = size;
      }
      else
      {
        *(CRect *)&rectMenu[8] = this->m_pParentRibbonElement->m_rect;
        CWnd::ClientToScreen(v69, (tagRECT *)&rectMenu[8]);
        v73 = size;
        v72 = *(_DWORD *)&rectMenu[16] - v31;
        if ( size )
          v72 = v31 + *(_DWORD *)&rectMenu[8];
        this->m_ptLocation.x = v72;
      }
      v74 = v73;
      v75 = *(_DWORD *)&rectMenu[32];
      v76 = 4 - (v74 != 0);
    }
    else
    {
      if ( !v40 || v40->__vftable[1].GetRuntimeClass(v40) )
      {
        v75 = *(_DWORD *)&rectMenu[32];
        v77 = *(_DWORD *)&rectMenu[24];
        if ( size )
        {
          v72 = v31 + *(_DWORD *)&rectMenu[24] + 1;
        }
        else
        {
          v72 = *(_DWORD *)&rectMenu[32] - v31 - 1;
          if ( this->m_bRightAlign )
            v72 = *(_DWORD *)&rectMenu[24] + 1;
        }
        this->m_ptLocation.x = v72;
        v76 = DROP_DIRECTION_NONE;
LABEL_144:
        this->m_DropDirection = v76;
        if ( size )
        {
          if ( v72 <= v75 )
            goto LABEL_150;
          this->m_ptLocation.x = v75;
        }
        else
        {
          if ( v72 >= v77 )
            goto LABEL_150;
          this->m_ptLocation.x = v77;
        }
        this->m_DropDirection = DROP_DIRECTION_NONE;
LABEL_150:
        if ( !this->m_bDisableAnimation )
        {
          if ( CMFCPopupMenu::GetAnimationType(0) == UNFOLD )
          {
            this->m_bIsAnimRight = 0;
          }
          else if ( CMFCPopupMenu::GetAnimationType(0) == FADE )
          {
            this->m_bIsAnimRight = 0;
            this->m_bIsAnimDown = 0;
          }
        }
        goto LABEL_155;
      }
      *(CRect *)&rectMenu[8] = this->m_pParentBtn->m_rect;
      CWnd::ClientToScreen(v40, (tagRECT *)&rectMenu[8]);
      v75 = *(_DWORD *)&rectMenu[32];
      v72 = *(_DWORD *)&rectMenu[8] - v31;
      if ( size )
        v72 = v31 + *(_DWORD *)&rectMenu[16];
      this->m_ptLocation.x = v72;
      if ( (int)(v72 + v31) >= v75 )
      {
        v72 = v75 - v31 - 1;
        this->m_ptLocation.x = v72;
      }
      v76 = DROP_DIRECTION_LEFT;
    }
    v77 = *(_DWORD *)&rectMenu[24];
    goto LABEL_144;
  }
LABEL_155:
  v78 = this->m_ptLocation.y;
  if ( v78 + cy <= *(int *)&rectMenu[36] )
  {
    v88 = *(_DWORD *)&rectMenu[28];
    v90 = *(_QWORD *)&rectShadowBottom.right;
    goto LABEL_192;
  }
  v79 = this->m_rectResize.bottom - this->m_rectResize.top;
  if ( this->m_bIsResizable )
  {
    *(_DWORD *)&rectMenu[8] = v10;
    *(_DWORD *)&rectMenu[12] = v10;
    this->m_bIsResizeBarOnTop = 1;
    *(_DWORD *)&rectMenu[16] = v31 - 2 * v10 + v10;
    *(_DWORD *)&rectMenu[20] = v10 + v79;
    this->m_rectResize = *(CRect *)&rectMenu[8];
  }
  v80 = this->__vftable;
  this->m_bIsAnimDown = 0;
  *(_OWORD *)&rectQCParent[24] = 0;
  v81 = (__int64)v80->GetParentArea(this, (CRect *)&rectQCParent[24]);
  v82 = v81;
  if ( v81 && (unsigned int)(this->m_DropDirection - 3) > 1 )
  {
    *(_DWORD *)&rectMenu[12] = 0;
    *(_DWORD *)&rectMenu[8] = *(_DWORD *)&rectQCParent[32];
    ClientToScreen(*(HWND *)(v81 + 64), (LPPOINT)&rectMenu[8]);
    v83 = *(HWND *)(v82 + 64);
    *(_DWORD *)&rectMenu[40] = 0;
    *(_DWORD *)&rectMenu[44] = *(_DWORD *)&rectQCParent[28] - cy;
    ClientToScreen(v83, (LPPOINT)&rectMenu[40]);
    v84 = *(_DWORD *)&rectMenu[44];
    if ( *(int *)&rectMenu[44] < 0 )
    {
      v85 = 1;
      v113 = *(_DWORD *)&rectMenu[44] + cy;
      if ( !this->m_bScrollable )
        goto LABEL_170;
      v86 = this->m_pParentBtn;
      if ( v86 )
      {
        v87 = v86->m_pWndParent;
        if ( v87 )
        {
          if ( CObject::IsKindOf(v87, &CMFCToolBar::classCMFCToolBar)
            && ((unsigned int (__fastcall *)(CObject *))v87->__vftable[18].~CObject)(v87)
            && !CMFCPopupMenu::GetParentPopupMenu(this) )
          {
            v84 = *(_DWORD *)&rectMenu[44];
            v85 = 1;
            goto LABEL_170;
          }
          v84 = *(_DWORD *)&rectMenu[44];
        }
      }
      v85 = 0;
LABEL_170:
      v88 = *(_DWORD *)&rectMenu[28];
      if ( *(_DWORD *)&rectMenu[36] - v113 < v113 - *(_DWORD *)&rectMenu[28] && v85 )
      {
        this->m_DropDirection = DROP_DIRECTION_NONE;
        cy += v84;
        this->m_ptLocation.y = v88;
        HIDWORD(m_sizeCurrent) = cy;
      }
      else
      {
        cy = *(_DWORD *)&rectMenu[36] - this->m_ptLocation.y;
        v17 = this->m_bIsResizable == 0;
        HIDWORD(m_sizeCurrent) = cy;
        this->m_bIsAnimDown = 1;
        if ( !v17 )
        {
          this->m_bIsResizeBarOnTop = 0;
          *(_DWORD *)&rectMenu[8] = v10;
          *(_DWORD *)&rectMenu[12] = cy - v79 - v10;
          *(_DWORD *)&rectMenu[16] = v31 - 2 * v10 + v10;
          *(_DWORD *)&rectMenu[20] = cy - v10;
          this->m_rectResize = *(CRect *)&rectMenu[8];
        }
      }
      this->m_bHasBeenResized = 1;
      this->m_bScrollable = 1;
      goto LABEL_182;
    }
    this->m_ptLocation.y = *(_DWORD *)&rectMenu[44];
    if ( v40 && v40->__vftable[1].GetRuntimeClass(v40) )
      v89 = DROP_DIRECTION_TOP;
    else
      v89 = DROP_DIRECTION_NONE;
    this->m_DropDirection = v89;
  }
  else if ( v114 )
  {
    this->m_ptLocation.y = *(_DWORD *)&rectQCParent[20] - cy - 1;
  }
  else
  {
    this->m_ptLocation.y -= cy;
    if ( CMFCPopupMenu::GetParentPopupMenu(this) )
    {
      v92 = 2 * v10;
      v90 = *(_QWORD *)&rectShadowBottom.right;
      v93 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&rectShadowBottom.right + 1720LL))(*(_QWORD *)&rectShadowBottom.right);
      v88 = *(_DWORD *)&rectMenu[28];
      this->m_ptLocation.y += v92 + v93;
      goto LABEL_183;
    }
  }
  v88 = *(_DWORD *)&rectMenu[28];
LABEL_182:
  v90 = *(_QWORD *)&rectShadowBottom.right;
LABEL_183:
  v78 = this->m_ptLocation.y;
  if ( v78 < v88 )
  {
    this->m_DropDirection = DROP_DIRECTION_NONE;
    v78 = v88;
    this->m_ptLocation.y = v88;
  }
  v91 = *(_DWORD *)&rectMenu[36];
  if ( v78 + cy > *(int *)&rectMenu[36] )
  {
    this->m_bHasBeenResized = 1;
    cy = v91 - v78;
    this->m_bScrollable = 1;
    HIDWORD(m_sizeCurrent) = v91 - v78;
  }
LABEL_192:
  if ( v78 < v88 )
  {
    v94 = this->m_pParentBtn;
    if ( v94 && v94->m_pWndParent )
    {
      if ( !CMFCPopupMenu::GetParentPopupMenu(this) )
      {
        v95 = this->m_pParentBtn;
        *(_DWORD *)&rectMenu[8] = v95->m_rect.right;
        *(_DWORD *)&rectMenu[12] = 0;
        ClientToScreen(v95->m_pWndParent->m_hWnd, (LPPOINT)&rectMenu[8]);
        v96 = this->m_pParentBtn;
        bottom = v96->m_rect.bottom;
        *(_DWORD *)&rectMenu[40] = 0;
        *(_DWORD *)&rectMenu[44] = bottom;
        ClientToScreen(v96->m_pWndParent->m_hWnd, (LPPOINT)&rectMenu[40]);
        this->m_ptLocation.y = *(_DWORD *)&rectMenu[44];
        if ( !v40 || (v17 = v40->__vftable[1].GetRuntimeClass(v40) == 0, v98 = DROP_DIRECTION_BOTTOM, v17) )
          v98 = DROP_DIRECTION_NONE;
        v88 = *(_DWORD *)&rectMenu[28];
        this->m_DropDirection = v98;
        goto LABEL_202;
      }
      v88 = *(_DWORD *)&rectMenu[28];
    }
    this->m_ptLocation.y = v88;
LABEL_202:
    if ( cy + this->m_ptLocation.y > *(int *)&rectMenu[36] )
    {
      v99 = *(_DWORD *)&rectMenu[36] - v88;
      this->m_ptLocation.y = v88;
      if ( cy > v99 )
      {
        cy = v99;
        HIDWORD(m_sizeCurrent) = v99;
        this->m_bHasBeenResized = 1;
        this->m_bScrollable = 1;
      }
      this->m_DropDirection = DROP_DIRECTION_NONE;
    }
  }
  if ( !*(_DWORD *)rectMenu )
  {
    if ( this->m_bScrollable )
    {
      if ( this->m_bShowScrollBar )
      {
        if ( !this->m_bResizeTracking && !this->m_bWasResized )
        {
          v31 += GetSystemMetrics(2);
          LODWORD(m_sizeCurrent) = v31;
          if ( !IsRectEmpty(&this->m_rectResize) )
            this->m_rectResize.right += GetSystemMetrics(2);
        }
      }
    }
  }
  this->m_FinalSize = (CSize)m_sizeCurrent;
  AnimationType = CMFCPopupMenu::GetAnimationType(0);
  v101 = CMFCToolBar::m_bCustomizeMode;
  if ( AnimationType || this->m_bAnimationIsDone || CMFCToolBar::m_bCustomizeMode )
  {
    if ( !CMFCToolBar::m_bCustomizeMode )
    {
      m_iShadowSize = this->m_iShadowSize;
      v31 += m_iShadowSize;
      cy += m_iShadowSize;
    }
    if ( this->m_pMenuCustomizationPage )
      CWnd::SetWindowPos(this, 0, -1, -1, v31, cy, 0x16u);
    else
      CWnd::SetWindowPos(this, 0, this->m_ptLocation.x - (size != 0 ? v31 : 0), this->m_ptLocation.y, v31, cy, 0x14u);
    v101 = CMFCToolBar::m_bCustomizeMode;
    if ( CMFCToolBar::m_bCustomizeMode )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 2008LL))(v90);
      v101 = CMFCToolBar::m_bCustomizeMode;
    }
  }
  if ( this->m_iShadowSize )
  {
    if ( !v101 )
    {
      v103 = this->m_pParentBtn;
      if ( v103 )
      {
        if ( v103->m_pWndParent )
        {
          m_bShown = this->m_bShown;
          v105 = this->m_hWnd;
          this->m_bShown = 1;
          v106 = v103->m_pWndParent;
          *(_OWORD *)&rectQCParent[24] = 0;
          *(_OWORD *)&rectMenu[8] = 0;
          GetWindowRect(v105, (LPRECT)&rectMenu[8]);
          v107 = this->m_iShadowSize;
          if ( size )
            v108 = *(_DWORD *)&rectMenu[8] - v107 - 1;
          else
            v108 = *(_DWORD *)&rectMenu[16] + 1;
          *(_DWORD *)&rectMenu[40] = v108;
          rectShadowBottom.left = v107 + v108;
          *(_DWORD *)&rectMenu[44] = *(_DWORD *)&rectMenu[12];
          rectShadowBottom.top = *(_DWORD *)&rectMenu[20] + v107;
          CWnd::ScreenToClient(v106, (tagRECT *)&rectMenu[40]);
          if ( IntersectRect((LPRECT)&rectQCParent[24], (const RECT *)&rectMenu[40], &this->m_pParentBtn->m_rect) )
          {
            InvalidateRect(v106->m_hWnd, &this->m_pParentBtn->m_rect, 1);
            UpdateWindow(v106->m_hWnd);
          }
          v109 = this->m_iShadowSize;
          rectShadowBottom.right = *(_DWORD *)&rectMenu[8];
          *(_DWORD *)rectQCParent = *(_DWORD *)&rectMenu[16] + v109;
          rectShadowBottom.bottom = *(_DWORD *)&rectMenu[20] + 1;
          *(_DWORD *)&rectQCParent[4] = v109 + *(_DWORD *)&rectMenu[20] + 1;
          CWnd::ScreenToClient(v106, (tagRECT *)&rectShadowBottom.right);
          if ( IntersectRect(
                 (LPRECT)&rectQCParent[24],
                 (const RECT *)&rectShadowBottom.right,
                 &this->m_pParentBtn->m_rect) )
          {
            InvalidateRect(v106->m_hWnd, &this->m_pParentBtn->m_rect, 1);
            UpdateWindow(v106->m_hWnd);
          }
          this->m_bShown = m_bShown;
        }
      }
    }
  }
  if ( this->m_bScrollable && this->m_bShowScrollBar && !this->m_bResizeTracking && !this->m_bWasResized )
    RedrawWindow(this->m_hWnd, 0, 0, 0x105u);
}

```

## disassembly

```asm
0x1800b8f50  mov     rax, rsp
0x1800b8f53  mov     [rax+10h], rbx
0x1800b8f57  mov     [rax+18h], rsi
0x1800b8f5b  mov     [rax+20h], rdi
0x1800b8f5f  push    rbp
0x1800b8f60  push    r12
0x1800b8f62  push    r13
0x1800b8f64  push    r14
0x1800b8f66  push    r15
0x1800b8f68  lea     rbp, [rax-5Fh]
0x1800b8f6c  sub     rsp, 0F0h
0x1800b8f73  mov     rax, cs:__security_cookie
0x1800b8f7a  xor     rax, rsp
0x1800b8f7d  mov     [rbp+57h+var_28], rax
0x1800b8f81  mov     rax, [this]
0x1800b8f84  mov     rdi, this
0x1800b8f87  mov     rax, [rax+3A0h]
0x1800b8f8e  call    cs:__guard_dispatch_icall_fptr
0x1800b8f94  mov     this, [rdi+40h]; hWnd
0x1800b8f98  mov     r13, rax
0x1800b8f9b  mov     qword ptr [rbp+57h+rectShadowBottom.right], rax
0x1800b8f9f  call    cs:__imp_IsWindow
0x1800b8fa5  xor     r15d, r15d
0x1800b8fa8  test    eax, eax
0x1800b8faa  jz      loc_1800B9F2D
0x1800b8fb0  test    r13, r13
0x1800b8fb3  jz      loc_1800B9F2D
0x1800b8fb9  mov     this, [r13+40h]; hWnd
0x1800b8fbd  call    cs:__imp_IsWindow
0x1800b8fc3  test    eax, eax
0x1800b8fc5  jz      loc_1800B9F2D
0x1800b8fcb  cmp     [r13+111Ch], r15d
0x1800b8fd2  jnz     loc_1800B9F2D
0x1800b8fd8  mov     this, [rdi+228h]
0x1800b8fdf  test    this, this
0x1800b8fe2  jz      short loc_1800B9005
0x1800b8fe4  mov     rax, [this]
0x1800b8fe7  mov     rax, [rax+1F8h]
0x1800b8fee  call    cs:__guard_dispatch_icall_fptr
0x1800b8ff4  test    eax, eax
0x1800b8ff6  jz      short loc_1800B9005
0x1800b8ff8  cmp     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, r15d; int CMFCToolBar::m_bCustomizeMode
0x1800b8fff  lea     ebx, [r15+1]
0x1800b9003  jz      short loc_1800B9008
0x1800b9005  mov     ebx, r15d
0x1800b9008  mov     this, [rdi+200h]; pt
0x1800b900f  xorps   xmm0, xmm0
0x1800b9012  mov     __formal, 2; dwFlags
0x1800b9017  mov     [rbp+57h+mi.rcMonitor.top], 28h ; '('
0x1800b901e  movdqu  xmmword ptr [rbp+57h+rectScreen.right], xmm0
0x1800b9023  call    cs:__imp_MonitorFromPoint
0x1800b9029  mov     this, rax; hMonitor
0x1800b902c  lea     rdx, [rbp+57h+mi.rcMonitor.top]; lpmi
0x1800b9030  call    cs:__imp_GetMonitorInfoW
0x1800b9036  test    eax, eax
0x1800b9038  jz      short loc_1800B904A
0x1800b903a  lea     rdx, [rbp+57h+mi.rcWork.right]; lprcSrc
0x1800b903e  lea     this, [rbp+57h+rectScreen.right]; lprcDst
0x1800b9042  call    cs:__imp_CopyRect
0x1800b9048  jmp     short loc_1800B905C
0x1800b904a  xor     __formal, __formal; uiParam
0x1800b904c  lea     r8, [rbp+57h+rectScreen.right]; pvParam
0x1800b9050  xor     r9d, r9d; fWinIni
0x1800b9053  lea     ecx, [rdx+30h]; uiAction
0x1800b9056  call    cs:__imp_SystemParametersInfoW
0x1800b905c  mov     rax, [rdi]
0x1800b905f  mov     this, rdi
0x1800b9062  mov     rax, [rax+428h]
0x1800b9069  call    cs:__guard_dispatch_icall_fptr
0x1800b906f  mov     this, rdi; this
0x1800b9072  mov     r12d, eax
0x1800b9075  call    ?GetExStyle@CWnd@@QEBAKXZ; CWnd::GetExStyle(void)
0x1800b907a  mov     r8d, [rbp+57h+rectShadowRight.top]
0x1800b907e  and     eax, 400000h
0x1800b9083  mov     __formal, [rbp+57h+rectShadowRight.left]
0x1800b9086  mov     r11d, [rbp+57h+rectScreen.right]
0x1800b908a  mov     [rbp+57h+size.cx], eax
0x1800b908d  cmp     [rdi+1978h], r15d
0x1800b9094  jz      short loc_1800B9102
0x1800b9096  mov     r10d, [rdi+200h]
0x1800b909d  test    eax, eax
0x1800b909f  mov     r9d, [rdi+1990h]
0x1800b90a6  lea     eax, [r12+r12]
0x1800b90aa  jz      short loc_1800B90BB
0x1800b90ac  sub     r10d, eax
0x1800b90af  sub     r10d, r11d
0x1800b90b2  cmp     r9d, r10d
0x1800b90b5  cmovge  r9d, r10d
0x1800b90b9  jmp     short loc_1800B90CD
0x1800b90bb  mov     ecx, __formal
0x1800b90bd  sub     ecx, eax
0x1800b90bf  lea     eax, [r12+r12]
0x1800b90c3  sub     ecx, r10d
0x1800b90c6  cmp     r9d, ecx
0x1800b90c9  cmovge  r9d, ecx
0x1800b90cd  mov     [rdi+1990h], r9d
0x1800b90d4  mov     ecx, [rdi+199Ch]
0x1800b90da  sub     ecx, [rdi+19A4h]
0x1800b90e0  mov     r9d, [rdi+204h]
0x1800b90e7  sub     ecx, r9d
0x1800b90ea  sub     ecx, eax
0x1800b90ec  mov     eax, [rdi+1994h]
0x1800b90f2  add     ecx, r8d
0x1800b90f5  cmp     eax, ecx
0x1800b90f7  cmovge  eax, ecx
0x1800b90fa  mov     [rdi+1994h], eax
0x1800b9100  jmp     short loc_1800B9109
0x1800b9102  mov     r9d, [rdi+204h]
0x1800b9109  mov     ecx, [rdi+200h]
0x1800b910f  mov     eax, __formal
0x1800b9111  cmp     ecx, __formal
0x1800b9113  cmovl   eax, ecx
0x1800b9116  cmp     r11d, eax
0x1800b9119  jg      short loc_1800B9123
0x1800b911b  cmp     ecx, __formal
0x1800b911d  cmovl   __formal, ecx
0x1800b9120  mov     r11d, __formal
0x1800b9123  mov     [rdi+200h], r11d
0x1800b912a  cmp     [rdi+228h], r15
0x1800b9131  jnz     short loc_1800B9154
0x1800b9133  mov     ecx, [rbp+57h+rectScreen.bottom]
0x1800b9136  cmp     r9d, r8d
0x1800b9139  mov     eax, r8d
0x1800b913c  cmovl   eax, r9d
0x1800b9140  cmp     ecx, eax
0x1800b9142  jg      short loc_1800B914E
0x1800b9144  cmp     r9d, r8d
0x1800b9147  cmovl   r8d, r9d
0x1800b914b  mov     ecx, r8d
0x1800b914e  mov     [rdi+204h], ecx
0x1800b9154  mov     rax, [rdi+1990h]
0x1800b915b  mov     [rbp+57h+var_C8], rax
0x1800b915f  cmp     [rdi+1978h], r15d
0x1800b9166  jnz     short loc_1800B9196
0x1800b9168  cmp     [rdi+197Ch], r15d
0x1800b916f  jnz     short loc_1800B9196
0x1800b9171  mov     rax, [r13+0]
0x1800b9175  lea     rdx, [rbp+57h+rectMenu.right]
0x1800b9179  mov     r8d, 1
0x1800b917f  mov     this, r13
0x1800b9182  mov     rax, [rax+558h]
0x1800b9189  call    cs:__guard_dispatch_icall_fptr
0x1800b918f  mov     this, [rax]
0x1800b9192  mov     [rbp+57h+var_C8], this
0x1800b9196  mov     [rbp+57h+rectMenu.left], r15d
0x1800b919a  cmp     [rdi+1978h], r15d
0x1800b91a1  jnz     loc_1800B9249
0x1800b91a7  cmp     [rdi+197Ch], r15d
0x1800b91ae  jnz     loc_1800B9249
0x1800b91b4  mov     r14d, dword ptr [rbp+57h+var_C8]
0x1800b91b8  lea     ecx, [r12+r12]
0x1800b91bc  mov     esi, dword ptr [rbp+57h+var_C8+4]
0x1800b91bf  add     r14d, ecx
0x1800b91c2  add     esi, ecx
0x1800b91c4  mov     dword ptr [rbp+57h+var_C8], r14d
0x1800b91c8  mov     dword ptr [rbp+57h+var_C8+4], esi
0x1800b91cb  cmp     [rdi+16A4h], r15d
0x1800b91d2  jz      short loc_1800B9218
0x1800b91d4  cmp     [rdi+16A8h], r15d
0x1800b91db  jz      short loc_1800B9218
0x1800b91dd  mov     ecx, 2; nIndex
0x1800b91e2  call    cs:__imp_GetSystemMetrics
0x1800b91e8  add     eax, r14d
0x1800b91eb  lea     this, [rdi+1998h]; lprc
0x1800b91f2  mov     r14d, eax
0x1800b91f5  mov     dword ptr [rbp+57h+var_C8], eax
0x1800b91f8  call    cs:__imp_IsRectEmpty
0x1800b91fe  test    eax, eax
0x1800b9200  jnz     short loc_1800B9211
0x1800b9202  lea     ecx, [rax+2]; nIndex
0x1800b9205  call    cs:__imp_GetSystemMetrics
0x1800b920b  add     [rdi+19A0h], eax
0x1800b9211  mov     [rbp+57h+rectMenu.left], 1
0x1800b9218  mov     ecx, [rdi+1688h]
0x1800b921e  test    ecx, ecx
0x1800b9220  jz      short loc_1800B923C
0x1800b9222  sub     ecx, 1
0x1800b9225  jz      short loc_1800B923C
0x1800b9227  sub     ecx, 1
0x1800b922a  jz      short loc_1800B9231
0x1800b922c  cmp     ecx, 1
0x1800b922f  jnz     short loc_1800B9250
0x1800b9231  add     esi, [rdi+1680h]
0x1800b9237  mov     dword ptr [rbp+57h+var_C8+4], esi
0x1800b923a  jmp     short loc_1800B9250
0x1800b923c  add     r14d, [rdi+1680h]
0x1800b9243  mov     dword ptr [rbp+57h+var_C8], r14d
0x1800b9247  jmp     short loc_1800B9250
0x1800b9249  mov     esi, dword ptr [rbp+57h+var_C8+4]
0x1800b924c  mov     r14d, dword ptr [rbp+57h+var_C8]
0x1800b9250  cmp     [rdi+220h], r15
0x1800b9257  jz      short loc_1800B9283
0x1800b9259  mov     ecx, 33h ; '3'; nIndex
0x1800b925e  call    cs:__imp_GetSystemMetrics
0x1800b9264  mov     ecx, 6; nIndex
0x1800b9269  lea     ebx, [rsi+rax]
0x1800b926c  call    cs:__imp_GetSystemMetrics
0x1800b9272  lea     esi, ds:5[rax*2]
0x1800b9279  add     esi, ebx
0x1800b927b  mov     dword ptr [rbp+57h+var_C8+4], esi
0x1800b927e  jmp     loc_1800B9398
0x1800b9283  test    ebx, ebx
0x1800b9285  jz      loc_1800B9398
0x1800b928b  lea     eax, [r12+r12]
0x1800b928f  mov     [rbp+57h+rectMenu.right], r12d
0x1800b9293  add     esi, 0Ah
0x1800b9296  mov     [rbp+57h+rectMenu.bottom], r12d
0x1800b929a  mov     ecx, r14d
0x1800b929d  mov     dword ptr [rbp+57h+var_C8+4], esi
0x1800b92a0  sub     ecx, eax
0x1800b92a2  lea     eax, [this+r12]
0x1800b92a6  mov     [rbp+57h+rectScreen.left], eax
0x1800b92a9  lea     eax, [r12+0Ah]
0x1800b92ae  mov     [rbp+57h+rectScreen.top], eax
0x1800b92b1  movups  xmm0, xmmword ptr [rbp+57h+rectMenu.right]
0x1800b92b5  movdqu  xmmword ptr [rdi+1848h], xmm0
0x1800b92bd  cmp     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, r15d; int CMFCToolBar::m_bCustomizeMode
0x1800b92c4  jnz     loc_1800B9398
0x1800b92ca  lea     this, [rdi+1858h]
0x1800b92d1  test    this, this
0x1800b92d4  jz      short loc_1800B92E0
0x1800b92d6  cmp     [this+40h], r15
0x1800b92da  jnz     loc_1800B9398
0x1800b92e0  mov     rax, [this]
0x1800b92e3  xor     r8d, r8d
0x1800b92e6  mov     rdx, rdi
0x1800b92e9  mov     rax, [rax+2D8h]
0x1800b92f0  call    cs:__guard_dispatch_icall_fptr
0x1800b92f6  mov     this, [rdi+1898h]; hWnd
0x1800b92fd  xor     r9d, r9d; lParam
0x1800b9300  mov     __formal, 401h; Msg
0x1800b9305  lea     r8d, [r9+1]; wParam
0x1800b9309  call    cs:__imp_SendMessageW
0x1800b930f  mov     ecx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized; AFX_GLOBAL_DATA afxGlobalData ...
0x1800b9315  test    ecx, ecx
0x1800b9317  jnz     short loc_1800B9330
0x1800b9319  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1800b9320  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800b9325  mov     ecx, 1
0x1800b932a  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ecx; AFX_GLOBAL_DATA afxGlobalData ...
0x1800b9330  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nMaxToolTipWidth; AFX_GLOBAL_DATA afxGlobalData ...
0x1800b9336  cmp     eax, 0FFFFFFFFh
0x1800b9339  jz      short loc_1800B9373
0x1800b933b  test    ecx, ecx
0x1800b933d  jnz     short loc_1800B935B
0x1800b933f  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1800b9346  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800b934b  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nMaxToolTipWidth; AFX_GLOBAL_DATA afxGlobalData ...
0x1800b9351  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x1800b935b  mov     this, [rdi+1898h]; hWnd
0x1800b9362  xor     r8d, r8d; wParam
0x1800b9365  movsxd  r9, eax; lParam
0x1800b9368  mov     __formal, 418h; Msg
0x1800b936d  call    cs:__imp_SendMessageW
0x1800b9373  lea     r9, [rdi+1848h]; lpRectTool
0x1800b937a  mov     [rsp+110h+nIDTool], 1; nIDTool
0x1800b9383  lea     this, [rdi+1858h]; this
0x1800b938a  mov     r8d, 3E9Ch; nIDText
0x1800b9390  mov     rdx, rdi; pWnd
0x1800b9393  call    ?AddTool@CToolTipCtrl@@QEAAHPEAVCWnd@@IPEBUtagRECT@@_K@Z; CToolTipCtrl::AddTool(CWnd *,uint,tagRECT const *,unsigned __int64)
0x1800b9398  mov     r15d, [rdi+16D4h]
0x1800b939f  cmp     r15d, 0FFFFFFFFh
0x1800b93a3  jz      short loc_1800B93FE
0x1800b93a5  cmp     esi, r15d
0x1800b93a8  jle     short loc_1800B93FE
0x1800b93aa  cmp     dword ptr [rdi+1978h], 0
0x1800b93b1  jnz     short loc_1800B93F4
0x1800b93b3  cmp     dword ptr [rdi+197Ch], 0
0x1800b93ba  jnz     short loc_1800B93F4
0x1800b93bc  mov     rax, [r13+0]
0x1800b93c0  lea     ebx, [r12+r12]
0x1800b93c4  mov     this, r13
0x1800b93c7  sub     r15d, ebx
0x1800b93ca  mov     rax, [rax+6B8h]
0x1800b93d1  call    cs:__guard_dispatch_icall_fptr
0x1800b93d7  lea     esi, [r15+2]
0x1800b93db  mov     dword ptr [rdi+1668h], 1
0x1800b93e5  mov     ecx, eax
0x1800b93e7  mov     eax, r15d
0x1800b93ea  cdq
0x1800b93eb  idiv    ecx
0x1800b93ed  sub     ebx, __formal
0x1800b93ef  add     esi, ebx
0x1800b93f1  mov     dword ptr [rbp+57h+var_C8+4], esi
0x1800b93f4  mov     dword ptr [rdi+16A4h], 1
0x1800b93fe  xor     r15d, r15d
0x1800b9401  cmp     [rdi+1984h], r15d
0x1800b9408  jz      short loc_1800B9466
0x1800b940a  cmp     [rdi+1988h], r15d
0x1800b9411  lea     __formal, [r15+9]
0x1800b9415  lea     eax, [rdx+3]
0x1800b9418  mov     [rbp+57h+rectMenu.right], r12d
0x1800b941c  cmovg   __formal, eax
0x1800b941f  lea     ecx, [r12+r12]
0x1800b9423  mov     eax, r14d
0x1800b9426  sub     eax, ecx
0x1800b9428  cmp     [rdi+1980h], r15d
0x1800b942f  jz      short loc_1800B9441
0x1800b9431  add     eax, r12d
0x1800b9434  mov     [rbp+57h+rectMenu.bottom], r12d
  ... truncated ...
```
