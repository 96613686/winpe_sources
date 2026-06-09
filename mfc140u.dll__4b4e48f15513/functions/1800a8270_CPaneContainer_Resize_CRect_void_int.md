# CPaneContainer::Resize(CRect,void * &,int)

- ea: `0x1800a8270`
- end: `0x1800a8e9d`
- name: `?Resize@CPaneContainer@@UEAAXVCRect@@AEAPEAXH@Z`
- size: `3117`
- prototype: `void __fastcall(CPaneContainer *this, CRect rect, void **hdwp, int bRedraw)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800a8270`
- `0x1800a9bc0`
- `0x1800a9c30`
- `0x1800a9ca0`
- `0x1800aaa00`
- `0x180231d70`
- `0x180296d00`
- `0x1802afdb0`
- `0x1802b62e0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!SetRectEmpty` at `0x1800a82b9`
- `USER32!SetRectEmpty` at `0x1800a82cb`
- `USER32!SetRectEmpty` at `0x1800a8358`
- `USER32!SetRectEmpty` at `0x1800a836a`
- `USER32!SetRectEmpty` at `0x1800a82b9`
- `USER32!SetRectEmpty` at `0x1800a82cb`
- `USER32!SetRectEmpty` at `0x1800a8358`
- `USER32!SetRectEmpty` at `0x1800a836a`
- `USER32!GetWindowRect` at `0x1800a832f`
- `USER32!GetWindowRect` at `0x1800a839f`
- `USER32!GetWindowRect` at `0x1800a8428`
- `USER32!GetWindowRect` at `0x1800a832f`
- `USER32!GetWindowRect` at `0x1800a839f`
- `USER32!GetWindowRect` at `0x1800a8428`
- `USER32!GetCapture` at `0x1800a88cf`
- `USER32!GetCapture` at `0x1800a8d97`
- `USER32!GetCapture` at `0x1800a88cf`
- `USER32!GetCapture` at `0x1800a8d97`
- `USER32!IsRectEmpty` at `0x1800a8669`
- `USER32!IsRectEmpty` at `0x1800a8677`
- `USER32!IsRectEmpty` at `0x1800a89f5`
- `USER32!IsRectEmpty` at `0x1800a8a03`
- `USER32!IsRectEmpty` at `0x1800a8669`
- `USER32!IsRectEmpty` at `0x1800a8677`
- `USER32!IsRectEmpty` at `0x1800a89f5`
- `USER32!IsRectEmpty` at `0x1800a8a03`
- `USER32!GetParent` at `0x1800a88f3`
- `USER32!GetParent` at `0x1800a8dbb`
- `USER32!GetParent` at `0x1800a88f3`
- `USER32!GetParent` at `0x1800a8dbb`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __fastcall CPaneContainer::Resize(CPaneContainer *this, CRect *rect, void **hdwp, unsigned int bRedraw)
{
  CPaneDivider *m_pDefaultSlider; // rcx
  int v9; // r14d
  int v10; // esi
  CPaneDivider *m_pSlider; // rcx
  CDockablePane *m_pBarLeftTop; // rcx
  CPaneContainer *m_pLeftContainer; // rcx
  CDockablePane *m_pBarRightBottom; // rcx
  CPaneContainer *m_pRightContainer; // rcx
  CDockablePane *v16; // rcx
  int v17; // edx
  int top; // r8d
  CPaneContainer *v19; // rcx
  CDockablePane *v20; // rcx
  int v21; // edx
  int v22; // r8d
  void (__fastcall *Resize)(CPaneContainer *, CRect, void **, int); // rax
  int m_nLastPercent; // esi
  int v25; // edx
  int v26; // r11d
  int v27; // r9d
  int v28; // r14d
  int v29; // r8d
  int v30; // r15d
  int v31; // r10d
  CDockablePane *v32; // rax
  CPaneContainer *v33; // rax
  CDockablePane *v34; // rax
  CPaneContainer *v35; // rax
  int v36; // ecx
  double v37; // xmm2_8
  int v38; // edx
  int v39; // ecx
  CPaneDivider *v40; // rdi
  int v41; // r8d
  int m_nWidth; // edi
  int v43; // r8d
  int v44; // eax
  HWND Capture; // rax
  CWnd *v46; // rax
  CPaneDivider *v47; // rcx
  HWND Parent; // rax
  CWnd *v49; // rax
  int v50; // eax
  int v51; // r8d
  int v52; // r9d
  int v53; // r10d
  int v54; // r14d
  int v55; // edx
  int v56; // r15d
  int v57; // r11d
  CDockablePane *v58; // rax
  int m_nRecentPercent; // r9d
  CPaneContainer *v60; // rax
  CDockablePane *v61; // rax
  CPaneContainer *v62; // rax
  int v63; // edx
  int v64; // ecx
  int v65; // ecx
  int v66; // r8d
  CPaneDivider *v67; // rdi
  int v68; // edx
  int v69; // edi
  int v70; // edx
  int v71; // eax
  CDockablePane *v72; // rcx
  unsigned int v73; // esi
  int v74; // edi
  CPaneContainer *v75; // rcx
  CPaneContainer_vtbl *v76; // rax
  CDockablePane *v77; // rcx
  CPaneContainer *v78; // rcx
  CPaneContainer_vtbl *v79; // rax
  HWND v80; // rax
  CWnd *v81; // rax
  CPaneDivider *v82; // rcx
  HWND v83; // rax
  CWnd *v84; // rax
  int v85; // eax
  CSize sizeMinRight; // [rsp+38h] [rbp-A9h] BYREF
  __int64 v87; // [rsp+40h] [rbp-A1h] BYREF
  unsigned int v88; // [rsp+48h] [rbp-99h]
  _BYTE rectFinalLeft_8[128]; // [rsp+58h] [rbp-89h] OVERLAPPED BYREF

  v88 = bRedraw;
  *(_OWORD *)&rectFinalLeft_8[48] = 0;
  SetRectEmpty((LPRECT)&rectFinalLeft_8[48]);
  *(_OWORD *)&rectFinalLeft_8[112] = 0;
  SetRectEmpty((LPRECT)&rectFinalLeft_8[112]);
  m_pDefaultSlider = this->m_pContainerManager->m_pDefaultSlider;
  if ( m_pDefaultSlider && m_pDefaultSlider->IsAutoHideMode(m_pDefaultSlider) )
  {
    v9 = 1;
    v10 = 0;
  }
  else
  {
    v9 = 0;
    v10 = 1;
  }
  m_pSlider = this->m_pSlider;
  if ( m_pSlider && ((CWnd::GetStyle(m_pSlider) & 0x10000000) != 0 || v9) )
    GetWindowRect(this->m_pSlider->m_hWnd, (LPRECT)&rectFinalLeft_8[112]);
  this->GetWindowRect(this, (CRect *)&rectFinalLeft_8[48], 0);
  *(_OWORD *)&rectFinalLeft_8[32] = 0;
  SetRectEmpty((LPRECT)&rectFinalLeft_8[32]);
  *(_OWORD *)&rectFinalLeft_8[64] = 0;
  SetRectEmpty((LPRECT)&rectFinalLeft_8[64]);
  m_pBarLeftTop = this->m_pBarLeftTop;
  sizeMinRight = 0;
  v87 = 0;
  if ( m_pBarLeftTop && ((CWnd::GetStyle(&m_pBarLeftTop->CPane) & 0x10000000) != 0 || v9) )
  {
    GetWindowRect(this->m_pBarLeftTop->m_hWnd, (LPRECT)&rectFinalLeft_8[32]);
    this->m_pBarLeftTop->GetMinSize((CPane *)this->m_pBarLeftTop, &sizeMinRight);
  }
  m_pLeftContainer = this->m_pLeftContainer;
  if ( m_pLeftContainer && (CPaneContainer::IsVisible(m_pLeftContainer) || v9) )
  {
    this->m_pLeftContainer->GetWindowRect(this->m_pLeftContainer, (CRect *)&rectFinalLeft_8[32], 0);
    this->m_pLeftContainer->GetMinSize(this->m_pLeftContainer, &sizeMinRight);
  }
  m_pBarRightBottom = this->m_pBarRightBottom;
  if ( m_pBarRightBottom && ((CWnd::GetStyle(&m_pBarRightBottom->CPane) & 0x10000000) != 0 || v9) )
  {
    GetWindowRect(this->m_pBarRightBottom->m_hWnd, (LPRECT)&rectFinalLeft_8[64]);
    this->m_pBarRightBottom->GetMinSize((CPane *)this->m_pBarRightBottom, (CSize *)&v87);
  }
  m_pRightContainer = this->m_pRightContainer;
  if ( m_pRightContainer && (CPaneContainer::IsVisible(m_pRightContainer) || v9) )
  {
    this->m_pRightContainer->GetWindowRect(this->m_pRightContainer, (CRect *)&rectFinalLeft_8[64], 0);
    this->m_pRightContainer->GetMinSize(this->m_pRightContainer, (CSize *)&v87);
  }
  if ( !CPaneContainer::IsLeftPartEmpty(this, v10) && CPaneContainer::IsRightPartEmpty(this, v10) )
  {
    v16 = this->m_pBarLeftTop;
    if ( v16 )
    {
      v17 = CPane::m_bHandleMinSize;
      if ( rect->right - rect->left < sizeMinRight.cx && CPane::m_bHandleMinSize )
        rect->right = rect->left + sizeMinRight.cx;
      top = rect->top;
      if ( rect->bottom - top < sizeMinRight.cy && v17 )
        rect->bottom = top + sizeMinRight.cy;
      *hdwp = v16->MoveWindow(&v16->CPane, rect, bRedraw, *hdwp);
    }
    v19 = this->m_pLeftContainer;
LABEL_47:
    if ( v19 )
    {
      Resize = v19->Resize;
      *(CRect *)&rectFinalLeft_8[80] = *rect;
      ((void (__fastcall *)(CPaneContainer *, _BYTE *, void **, _QWORD))Resize)(
        v19,
        &rectFinalLeft_8[80],
        hdwp,
        bRedraw);
    }
    return;
  }
  if ( CPaneContainer::IsLeftPartEmpty(this, v10) && !CPaneContainer::IsRightPartEmpty(this, v10) )
  {
    v20 = this->m_pBarRightBottom;
    if ( v20 )
    {
      v21 = CPane::m_bHandleMinSize;
      if ( rect->right - rect->left < (int)v87 && CPane::m_bHandleMinSize )
        rect->right = rect->left + v87;
      v22 = rect->top;
      if ( rect->bottom - v22 < SHIDWORD(v87) && v21 )
        rect->bottom = v22 + HIDWORD(v87);
      *hdwp = v20->MoveWindow(&v20->CPane, rect, bRedraw, *hdwp);
    }
    v19 = this->m_pRightContainer;
    goto LABEL_47;
  }
  if ( !CPaneContainer::IsLeftPartEmpty(this, v10) && !CPaneContainer::IsRightPartEmpty(this, v10) )
  {
    *(CRect *)rectFinalLeft_8 = *rect;
    *(_OWORD *)&rectFinalLeft_8[16] = *(_OWORD *)rectFinalLeft_8;
    *(_OWORD *)&rectFinalLeft_8[96] = *(_OWORD *)rectFinalLeft_8;
    if ( !this->m_pSlider )
      AfxThrowInvalidArgException();
    m_nLastPercent = -1;
    if ( CPaneContainer::IsPaneDividerHorz(this) )
    {
      v25 = *(_DWORD *)&rectFinalLeft_8[76];
      v26 = *(_DWORD *)&rectFinalLeft_8[68];
      v27 = *(_DWORD *)&rectFinalLeft_8[36];
      v28 = *(_DWORD *)&rectFinalLeft_8[60];
      v29 = *(_DWORD *)&rectFinalLeft_8[44];
      v30 = *(_DWORD *)&rectFinalLeft_8[52];
      if ( *(_DWORD *)&rectFinalLeft_8[44]
         + *(_DWORD *)&rectFinalLeft_8[76]
         - *(_DWORD *)&rectFinalLeft_8[68]
         - *(_DWORD *)&rectFinalLeft_8[36] <= *(_DWORD *)&rectFinalLeft_8[60] - *(_DWORD *)&rectFinalLeft_8[52] )
      {
        if ( !IsRectEmpty((const RECT *)&rectFinalLeft_8[32]) && !IsRectEmpty((const RECT *)&rectFinalLeft_8[64]) )
        {
          v28 = *(_DWORD *)&rectFinalLeft_8[60];
          v30 = *(_DWORD *)&rectFinalLeft_8[52];
          v29 = *(_DWORD *)&rectFinalLeft_8[44];
          v27 = *(_DWORD *)&rectFinalLeft_8[36];
LABEL_77:
          v36 = v30 + rect->bottom - rect->top - v28;
          v37 = (double)(v29 - v27) / (double)(v28 - v30) * 100.0;
          if ( v37 == 100.0 || v37 == 0.0 )
            v37 = DOUBLE_50_0;
          if ( CPaneContainer::m_bMaintainPercentage )
          {
            v38 = *(_DWORD *)&rectFinalLeft_8[4];
            if ( !v36 )
              goto LABEL_82;
          }
          else
          {
            if ( CPaneContainer::m_bRetainInternalSliderPosition )
            {
              *(_DWORD *)&rectFinalLeft_8[12] = v29 + *(_DWORD *)&rectFinalLeft_8[4] - v27;
              Capture = GetCapture();
              v46 = CWnd::FromHandle(Capture);
              v47 = this->m_pSlider;
              if ( v46 == v47 )
              {
                v39 = *(_DWORD *)&rectFinalLeft_8[12];
              }
              else
              {
                *(_OWORD *)&rectFinalLeft_8[80] = *(_OWORD *)&rectFinalLeft_8[112];
                Parent = GetParent(v47->m_hWnd);
                v49 = CWnd::FromHandle(Parent);
                CWnd::ScreenToClient(v49, (tagRECT *)&rectFinalLeft_8[80]);
                v39 = *(_DWORD *)&rectFinalLeft_8[84];
                *(_DWORD *)&rectFinalLeft_8[12] = *(_DWORD *)&rectFinalLeft_8[84];
              }
              v38 = *(_DWORD *)&rectFinalLeft_8[4];
              v28 = *(_DWORD *)&rectFinalLeft_8[60];
              v30 = *(_DWORD *)&rectFinalLeft_8[52];
              v37 = (double)(v39 - *(_DWORD *)&rectFinalLeft_8[4])
                  / (double)(*(_DWORD *)&rectFinalLeft_8[60] - *(_DWORD *)&rectFinalLeft_8[52]);
              goto LABEL_84;
            }
            v38 = *(_DWORD *)&rectFinalLeft_8[4];
            if ( v36 > 0 )
            {
              v50 = (int)((100.0 - v37) * (double)v36 / -100.0);
LABEL_102:
              v39 = v29 + v38 - v50 - v27;
              *(_DWORD *)&rectFinalLeft_8[12] = v39;
              goto LABEL_84;
            }
            if ( v36 >= 0 )
            {
LABEL_82:
              v39 = v29 + v38 - v27;
              *(_DWORD *)&rectFinalLeft_8[12] = v39;
              if ( m_nLastPercent != -1 )
                v37 = (double)m_nLastPercent;
LABEL_84:
              v40 = this->m_pSlider;
              *(_DWORD *)&rectFinalLeft_8[100] = v39;
              v41 = v39 + v40->m_nWidth;
              *(_DWORD *)&rectFinalLeft_8[108] = v41;
              *(_DWORD *)&rectFinalLeft_8[20] = v41;
              if ( CPane::m_bHandleMinSize )
              {
                m_nWidth = v40->m_nWidth;
                v43 = HIDWORD(v87) + v41 - *(_DWORD *)&rectFinalLeft_8[28];
                if ( sizeMinRight.cy + v38 - v39 > 0 )
                {
                  if ( v43 <= 0 )
                  {
                    v39 = sizeMinRight.cy + v38;
                    *(_DWORD *)&rectFinalLeft_8[12] = sizeMinRight.cy + v38;
                    v44 = m_nWidth + sizeMinRight.cy + v38;
                    *(_DWORD *)&rectFinalLeft_8[20] = v44;
                    if ( *(_DWORD *)&rectFinalLeft_8[28] - v44 >= SHIDWORD(v87) )
                    {
LABEL_91:
                      *(_DWORD *)&rectFinalLeft_8[100] = v39;
                      *(_DWORD *)&rectFinalLeft_8[108] = m_nWidth + v39;
                      v37 = (double)(v39 - v38) / (double)(v28 - v30) * 100.0;
                      if ( *(_DWORD *)&rectFinalLeft_8[8] - *(_DWORD *)rectFinalLeft_8 < sizeMinRight.cx )
                      {
                        *(_DWORD *)&rectFinalLeft_8[24] = *(_DWORD *)&rectFinalLeft_8[16] + sizeMinRight.cx;
                        *(_DWORD *)&rectFinalLeft_8[8] = *(_DWORD *)rectFinalLeft_8 + sizeMinRight.cx;
                      }
                      goto LABEL_146;
                    }
LABEL_90:
                    *(_DWORD *)&rectFinalLeft_8[28] = HIDWORD(v87) + v44;
                    goto LABEL_91;
                  }
                }
                else
                {
                  if ( v43 <= 0 )
                    goto LABEL_91;
                  v39 -= v43;
                  *(_DWORD *)&rectFinalLeft_8[12] = v39;
                  if ( v39 - v38 >= sizeMinRight.cy )
                    goto LABEL_89;
                }
                v39 = v38 + sizeMinRight.cy;
                *(_DWORD *)&rectFinalLeft_8[12] = v38 + sizeMinRight.cy;
LABEL_89:
                v44 = m_nWidth + v39;
                *(_DWORD *)&rectFinalLeft_8[20] = m_nWidth + v39;
                goto LABEL_90;
              }
LABEL_146:
              v72 = this->m_pBarLeftTop;
              v73 = v88;
              v74 = (int)v37;
              if ( v72 )
              {
                *hdwp = v72->MoveWindow(&v72->CPane, (const CRect *)rectFinalLeft_8, v88, *hdwp);
                this->m_pBarLeftTop->m_nLastPercent = v74;
              }
              v75 = this->m_pLeftContainer;
              if ( v75 )
              {
                v76 = v75->__vftable;
                *(_OWORD *)&rectFinalLeft_8[80] = *(_OWORD *)rectFinalLeft_8;
                ((void (__fastcall *)(CPaneContainer *, _BYTE *, void **, _QWORD))v76->Resize)(
                  v75,
                  &rectFinalLeft_8[80],
                  hdwp,
                  v73);
                this->m_pLeftContainer->m_nRecentPercent = v74;
              }
              v77 = this->m_pBarRightBottom;
              if ( v77 )
              {
                *hdwp = v77->MoveWindow(&v77->CPane, (const CRect *)&rectFinalLeft_8[16], v73, *hdwp);
                this->m_pBarRightBottom->m_nLastPercent = 100 - v74;
              }
              v78 = this->m_pRightContainer;
              if ( v78 )
              {
                v79 = v78->__vftable;
                *(_OWORD *)&rectFinalLeft_8[80] = *(_OWORD *)&rectFinalLeft_8[16];
                ((void (__fastcall *)(CPaneContainer *, _BYTE *, void **, _QWORD))v79->Resize)(
                  v78,
                  &rectFinalLeft_8[80],
                  hdwp,
                  v73);
                this->m_pRightContainer->m_nRecentPercent = 100 - v74;
              }
              if ( (CWnd::GetStyle(this->m_pSlider) & 0x10000000) != 0 )
                *hdwp = this->m_pSlider->MoveWindow(this->m_pSlider, &rectFinalLeft_8[96], v73, *hdwp);
              return;
            }
          }
          v50 = (int)((double)v36 * v37 / -100.0);
          goto LABEL_102;
        }
        v28 = *(_DWORD *)&rectFinalLeft_8[60];
        v30 = *(_DWORD *)&rectFinalLeft_8[52];
        v29 = *(_DWORD *)&rectFinalLeft_8[44];
        v27 = *(_DWORD *)&rectFinalLeft_8[36];
        v25 = *(_DWORD *)&rectFinalLeft_8[76];
        v26 = *(_DWORD *)&rectFinalLeft_8[68];
      }
      v31 = v28 - v30;
      m_nLastPercent = 50;
      if ( v29 - v27 == v28 - v30 )
      {
        v32 = this->m_pBarRightBottom;
        if ( v32 )
        {
          m_nLastPercent = v32->m_nLastPercent;
        }
        else
        {
          v33 = this->m_pRightContainer;
          if ( !v33 )
          {
LABEL_66:
            v29 = v27 + v28 - m_nLastPercent * v31 / 100 - v30;
            m_nLastPercent = 100 - m_nLastPercent;
LABEL_76:
            *(_DWORD *)&rectFinalLeft_8[44] = v29;
            goto LABEL_77;
          }
          m_nLastPercent = v33->m_nRecentPercent;
        }
        if ( m_nLastPercent == 100 || !m_nLastPercent )
          m_nLastPercent = 50;
        goto LABEL_66;
      }
      if ( v25 - v26 != v31 )
        goto LABEL_77;
      v34 = this->m_pBarLeftTop;
      if ( v34 )
      {
        m_nLastPercent = v34->m_nLastPercent;
      }
      else
      {
        v35 = this->m_pLeftContainer;
        if ( !v35 )
        {
LABEL_75:
          v29 = v27 + m_nLastPercent * v31 / 100;
          goto LABEL_76;
        }
        m_nLastPercent = v35->m_nRecentPercent;
      }
      if ( m_nLastPercent == 100 || !m_nLastPercent )
        m_nLastPercent = 50;
      goto LABEL_75;
    }
    v51 = *(_DWORD *)&rectFinalLeft_8[40];
    v52 = *(_DWORD *)&rectFinalLeft_8[64];
    v53 = *(_DWORD *)&rectFinalLeft_8[32];
    v54 = *(_DWORD *)&rectFinalLeft_8[56];
    v55 = *(_DWORD *)&rectFinalLeft_8[72];
    v56 = *(_DWORD *)&rectFinalLeft_8[48];
    if ( *(_DWORD *)&rectFinalLeft_8[72]
       + *(_DWORD *)&rectFinalLeft_8[40]
       - *(_DWORD *)&rectFinalLeft_8[64]
       - *(_DWORD *)&rectFinalLeft_8[32] <= *(_DWORD *)&rectFinalLeft_8[56] - *(_DWORD *)&rectFinalLeft_8[48] )
    {
      if ( !IsRectEmpty((const RECT *)&rectFinalLeft_8[32]) && !IsRectEmpty((const RECT *)&rectFinalLeft_8[64]) )
      {
        v54 = *(_DWORD *)&rectFinalLeft_8[56];
        v56 = *(_DWORD *)&rectFinalLeft_8[48];
        v51 = *(_DWORD *)&rectFinalLeft_8[40];
        v53 = *(_DWORD *)&rectFinalLeft_8[32];
LABEL_130:
        v63 = v51 - v53;
        v64 = v56 + rect->right - rect->left - v54;
        v37 = (double)(v51 - v53) / (double)(v54 - v56) * 100.0;
        if ( v37 == 100.0 || v37 == 0.0 )
          v37 = DOUBLE_50_0;
        if ( CPaneContainer::m_bMaintainPercentage )
        {
          if ( !v64 )
            goto LABEL_135;
        }
        else
        {
          if ( CPaneContainer::m_bRetainInternalSliderPosition )
          {
            *(_DWORD *)&rectFinalLeft_8[8] = v63 + *(_DWORD *)rectFinalLeft_8;
            v80 = GetCapture();
            v81 = CWnd::FromHandle(v80);
            v82 = this->m_pSlider;
            if ( v81 == v82 )
            {
              v66 = *(_DWORD *)&rectFinalLeft_8[8];
            }
            else
            {
              *(_OWORD *)&rectFinalLeft_8[80] = *(_OWORD *)&rectFinalLeft_8[112];
              v83 = GetParent(v82->m_hWnd);
              v84 = CWnd::FromHandle(v83);
              CWnd::ScreenToClient(v84, (tagRECT *)&rectFinalLeft_8[80]);
              v66 = *(_DWORD *)&rectFinalLeft_8[80];
              *(_DWORD *)&rectFinalLeft_8[8] = *(_DWORD *)&rectFinalLeft_8[80];
            }
            v65 = *(_DWORD *)rectFinalLeft_8;
            v54 = *(_DWORD *)&rectFinalLeft_8[56];
            v56 = *(_DWORD *)&rectFinalLeft_8[48];
            v37 = (double)(v66 - *(_DWORD *)rectFinalLeft_8)
                / (double)(*(_DWORD *)&rectFinalLeft_8[56] - *(_DWORD *)&rectFinalLeft_8[48]);
            goto LABEL_137;
          }
          if ( v64 > 0 )
          {
            v85 = (int)((100.0 - v37) * (double)v64 / -100.0);
LABEL_166:
            v65 = *(_DWORD *)rectFinalLeft_8;
            v66 = *(_DWORD *)rectFinalLeft_8 + v51 - v85 - v53;
            *(_DWORD *)&rectFinalLeft_8[8] = v66;
            goto LABEL_137;
          }
          if ( v64 >= 0 )
          {
LABEL_135:
            v65 = *(_DWORD *)rectFinalLeft_8;
            v66 = *(_DWORD *)rectFinalLeft_8 + v63;
            *(_DWORD *)&rectFinalLeft_8[8] = *(_DWORD *)rectFinalLeft_8 + v63;
            if ( m_nLastPercent != -1 )
              v37 = (double)m_nLastPercent;
LABEL_137:
            v67 = this->m_pSlider;
            *(_DWORD *)&rectFinalLeft_8[96] = v66;
            v68 = v66 + v67->m_nWidth;
            *(_DWORD *)&rectFinalLeft_8[104] = v68;
            *(_DWORD *)&rectFinalLeft_8[16] = v68;
            if ( !CPane::m_bHandleMinSize )
              goto LABEL_146;
            v69 = v67->m_nWidth;
            v70 = v87 + v68 - *(_DWORD *)&rectFinalLeft_8[24];
            if ( sizeMinRight.cx + v65 - v66 > 0 )
            {
              if ( v70 <= 0 )
              {
                v66 = sizeMinRight.cx + v65;
                *(_DWORD *)&rectFinalLeft_8[8] = sizeMinRight.cx + v65;
                v71 = v69 + sizeMinRight.cx + v65;
                *(_DWORD *)&rectFinalLeft_8[16] = v71;
                if ( *(_DWORD *)&rectFinalLeft_8[24] - v71 >= (int)v87 )
                {
LABEL_144:
                  *(_DWORD *)&rectFinalLeft_8[96] = v66;
                  *(_DWORD *)&rectFinalLeft_8[104] = v69 + v66;
                  v37 = (double)(v66 - v65) / (double)(v54 - v56) * 100.0;
                  if ( *(_DWORD *)&rectFinalLeft_8[12] - *(_DWORD *)&rectFinalLeft_8[4] < sizeMinRight.cy )
                  {
                    *(_DWORD *)&rectFinalLeft_8[28] = *(_DWORD *)&rectFinalLeft_8[20] + sizeMinRight.cy;
                    *(_DWORD *)&rectFinalLeft_8[12] = *(_DWORD *)&rectFinalLeft_8[4] + sizeMinRight.cy;
                  }
                  goto LABEL_146;
                }
LABEL_143:
                *(_DWORD *)&rectFinalLeft_8[24] = v87 + v71;
                goto LABEL_144;
              }
            }
            else
            {
              if ( v70 <= 0 )
                goto LABEL_144;
              v66 -= v70;
              *(_DWORD *)&rectFinalLeft_8[8] = v66;
              if ( v66 - v65 >= sizeMinRight.cx )
                goto LABEL_142;
            }
            v66 = v65 + sizeMinRight.cx;
            *(_DWORD *)&rectFinalLeft_8[8] = v65 + sizeMinRight.cx;
LABEL_142:
            v71 = v69 + v66;
            *(_DWORD *)&rectFinalLeft_8[16] = v69 + v66;
            goto LABEL_143;
          }
        }
        v85 = (int)((double)v64 * v37 / -100.0);
        goto LABEL_166;
      }
      v54 = *(_DWORD *)&rectFinalLeft_8[56];
      v56 = *(_DWORD *)&rectFinalLeft_8[48];
      v51 = *(_DWORD *)&rectFinalLeft_8[40];
      v53 = *(_DWORD *)&rectFinalLeft_8[32];
      v55 = *(_DWORD *)&rectFinalLeft_8[72];
      v52 = *(_DWORD *)&rectFinalLeft_8[64];
    }
    v57 = v54 - v56;
    if ( v51 - v53 == v54 - v56 )
    {
      v58 = this->m_pBarRightBottom;
      m_nRecentPercent = 50;
      if ( v58 )
      {
        m_nRecentPercent = v58->m_nLastPercent;
      }
      else
      {
        v60 = this->m_pRightContainer;
        if ( !v60 )
        {
LABEL_119:
          v51 = v54 + v53 - v57 * m_nRecentPercent / 100 - v56;
          m_nLastPercent = 100 - m_nRecentPercent;
LABEL_129:
          *(_DWORD *)&rectFinalLeft_8[40] = v51;
          goto LABEL_130;
        }
        m_nRecentPercent = v60->m_nRecentPercent;
      }
      if ( m_nRecentPercent == 100 || !m_nRecentPercent )
        m_nRecentPercent = 50;
      goto LABEL_119;
    }
    if ( v55 - v52 != v57 )
      goto LABEL_130;
    v61 = this->m_pBarLeftTop;
    m_nLastPercent = 50;
    if ( v61 )
    {
      m_nLastPercent = v61->m_nLastPercent;
    }
    else
    {
      v62 = this->m_pLeftContainer;
      if ( !v62 )
      {
LABEL_128:
        v51 = v53 + v57 * m_nLastPercent / 100;
        goto LABEL_129;
      }
      m_nLastPercent = v62->m_nRecentPercent;
    }
    if ( m_nLastPercent == 100 || !m_nLastPercent )
      m_nLastPercent = 50;
    goto LABEL_128;
  }
}

```

## disassembly

```asm
0x1800a8270  mov     rax, rsp
0x1800a8273  push    rbp
0x1800a8274  push    rbx
0x1800a8275  push    rsi
0x1800a8276  push    rdi
0x1800a8277  push    r12
0x1800a8279  push    r13
0x1800a827b  push    r14
0x1800a827d  push    r15
0x1800a827f  lea     rbp, [rax-5Fh]
0x1800a8283  sub     rsp, 0F8h
0x1800a828a  movaps  xmmword ptr [rax-58h], xmm6
0x1800a828e  mov     rax, cs:__security_cookie
0x1800a8295  xor     rax, rsp
0x1800a8298  mov     [rbp+57h+var_60], rax
0x1800a829c  mov     rbx, this
0x1800a829f  mov     [rsp+130h+var_F0], bRedraw
0x1800a82a4  xorps   xmm0, xmm0
0x1800a82a7  lea     this, [rbp+57h+rectContainer.right]; lprc
0x1800a82ab  movdqu  xmmword ptr [rbp+57h+rectContainer.right], xmm0
0x1800a82b0  mov     r15d, bRedraw
0x1800a82b3  mov     r13, hdwp
0x1800a82b6  mov     rdi, rect
0x1800a82b9  call    cs:__imp_SetRectEmpty
0x1800a82bf  xorps   xmm0, xmm0
0x1800a82c2  lea     this, [rbp+57h+rectSlider.right]; lprc
0x1800a82c6  movdqa  xmmword ptr [rbp+57h+rectSlider.right], xmm0
0x1800a82cb  call    cs:__imp_SetRectEmpty
0x1800a82d1  mov     rax, [rbx+38h]
0x1800a82d5  xor     r12d, r12d
0x1800a82d8  mov     this, [rax+88h]
0x1800a82df  test    this, this
0x1800a82e2  jz      short loc_1800A8302
0x1800a82e4  mov     rax, [this]
0x1800a82e7  mov     rax, [rax+3C8h]
0x1800a82ee  call    cs:__guard_dispatch_icall_fptr
0x1800a82f4  test    eax, eax
0x1800a82f6  jz      short loc_1800A8302
0x1800a82f8  lea     r14d, [r12+1]
0x1800a82fd  mov     esi, r12d
0x1800a8300  jmp     short loc_1800A830A
0x1800a8302  mov     r14d, r12d
0x1800a8305  mov     esi, 1
0x1800a830a  mov     this, [rbx+18h]; this
0x1800a830e  test    this, this
0x1800a8311  jz      short loc_1800A8335
0x1800a8313  call    ?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x1800a8318  bt      eax, 1Ch
0x1800a831c  jb      short loc_1800A8323
0x1800a831e  test    r14d, r14d
0x1800a8321  jz      short loc_1800A8335
0x1800a8323  mov     this, [rbx+18h]
0x1800a8327  lea     rect, [rbp+57h+rectSlider.right]; lpRect
0x1800a832b  mov     this, [this+40h]; hWnd
0x1800a832f  call    cs:__imp_GetWindowRect
0x1800a8335  mov     rax, [rbx]
0x1800a8338  lea     rect, [rbp+57h+rectContainer.right]
0x1800a833c  xor     r8d, r8d
0x1800a833f  mov     this, rbx
0x1800a8342  mov     rax, [rax+28h]
0x1800a8346  call    cs:__guard_dispatch_icall_fptr
0x1800a834c  xorps   xmm0, xmm0
0x1800a834f  lea     this, [rbp+57h+rectLeft.right]; lprc
0x1800a8353  movdqu  xmmword ptr [rbp+57h+rectLeft.right], xmm0
0x1800a8358  call    cs:__imp_SetRectEmpty
0x1800a835e  xorps   xmm0, xmm0
0x1800a8361  lea     this, [rbp+57h+rectRight.right]; lprc
0x1800a8365  movdqu  xmmword ptr [rbp+57h+rectRight.right], xmm0
0x1800a836a  call    cs:__imp_SetRectEmpty
0x1800a8370  mov     this, [rbx+8]; this
0x1800a8374  mov     qword ptr [rsp+130h+sizeMinRight.cx], r12
0x1800a8379  mov     [rsp+130h+var_F8], r12
0x1800a837e  test    this, this
0x1800a8381  jz      short loc_1800A83BE
0x1800a8383  call    ?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x1800a8388  bt      eax, 1Ch
0x1800a838c  jb      short loc_1800A8393
0x1800a838e  test    r14d, r14d
0x1800a8391  jz      short loc_1800A83BE
0x1800a8393  mov     this, [rbx+8]
0x1800a8397  lea     rect, [rbp+57h+rectLeft.right]; lpRect
0x1800a839b  mov     this, [this+40h]; hWnd
0x1800a839f  call    cs:__imp_GetWindowRect
0x1800a83a5  mov     this, [rbx+8]
0x1800a83a9  lea     rect, [rsp+130h+sizeMinRight]
0x1800a83ae  mov     rax, [this]
0x1800a83b1  mov     rax, [rax+4F0h]
0x1800a83b8  call    cs:__guard_dispatch_icall_fptr
0x1800a83be  mov     this, [rbx+20h]; this
0x1800a83c2  test    this, this
0x1800a83c5  jz      short loc_1800A8403
0x1800a83c7  call    ?IsVisible@CPaneContainer@@QEBAHXZ; CPaneContainer::IsVisible(void)
0x1800a83cc  test    eax, eax
0x1800a83ce  jnz     short loc_1800A83D5
0x1800a83d0  test    r14d, r14d
0x1800a83d3  jz      short loc_1800A8403
0x1800a83d5  mov     this, [rbx+20h]
0x1800a83d9  lea     rect, [rbp+57h+rectLeft.right]
0x1800a83dd  xor     r8d, r8d
0x1800a83e0  mov     rax, [this]
0x1800a83e3  mov     rax, [rax+28h]
0x1800a83e7  call    cs:__guard_dispatch_icall_fptr
0x1800a83ed  mov     this, [rbx+20h]
0x1800a83f1  lea     rect, [rsp+130h+sizeMinRight]
0x1800a83f6  mov     rax, [this]
0x1800a83f9  mov     rax, [rax+30h]
0x1800a83fd  call    cs:__guard_dispatch_icall_fptr
0x1800a8403  mov     this, [rbx+10h]; this
0x1800a8407  test    this, this
0x1800a840a  jz      short loc_1800A8447
0x1800a840c  call    ?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x1800a8411  bt      eax, 1Ch
0x1800a8415  jb      short loc_1800A841C
0x1800a8417  test    r14d, r14d
0x1800a841a  jz      short loc_1800A8447
0x1800a841c  mov     this, [rbx+10h]
0x1800a8420  lea     rect, [rbp+57h+rectRight.right]; lpRect
0x1800a8424  mov     this, [this+40h]; hWnd
0x1800a8428  call    cs:__imp_GetWindowRect
0x1800a842e  mov     this, [rbx+10h]
0x1800a8432  lea     rect, [rsp+130h+var_F8]
0x1800a8437  mov     rax, [this]
0x1800a843a  mov     rax, [rax+4F0h]
0x1800a8441  call    cs:__guard_dispatch_icall_fptr
0x1800a8447  mov     this, [rbx+28h]; this
0x1800a844b  test    this, this
0x1800a844e  jz      short loc_1800A848C
0x1800a8450  call    ?IsVisible@CPaneContainer@@QEBAHXZ; CPaneContainer::IsVisible(void)
0x1800a8455  test    eax, eax
0x1800a8457  jnz     short loc_1800A845E
0x1800a8459  test    r14d, r14d
0x1800a845c  jz      short loc_1800A848C
0x1800a845e  mov     this, [rbx+28h]
0x1800a8462  lea     rect, [rbp+57h+rectRight.right]
0x1800a8466  xor     r8d, r8d
0x1800a8469  mov     rax, [this]
0x1800a846c  mov     rax, [rax+28h]
0x1800a8470  call    cs:__guard_dispatch_icall_fptr
0x1800a8476  mov     this, [rbx+28h]
0x1800a847a  lea     rect, [rsp+130h+var_F8]
0x1800a847f  mov     rax, [this]
0x1800a8482  mov     rax, [rax+30h]
0x1800a8486  call    cs:__guard_dispatch_icall_fptr
0x1800a848c  mov     edx, esi; bCheckVisibility
0x1800a848e  mov     this, rbx; this
0x1800a8491  call    ?IsLeftPartEmpty@CPaneContainer@@QEBAHH@Z; CPaneContainer::IsLeftPartEmpty(int)
0x1800a8496  test    eax, eax
0x1800a8498  jnz     loc_1800A851F
0x1800a849e  mov     edx, esi; bCheckVisibility
0x1800a84a0  mov     this, rbx; this
0x1800a84a3  call    ?IsRightPartEmpty@CPaneContainer@@QEBAHH@Z; CPaneContainer::IsRightPartEmpty(int)
0x1800a84a8  test    eax, eax
0x1800a84aa  jz      short loc_1800A851F
0x1800a84ac  mov     this, [rbx+8]
0x1800a84b0  test    this, this
0x1800a84b3  jz      short loc_1800A8516
0x1800a84b5  mov     eax, [rdi+8]
0x1800a84b8  mov     r8d, [rdi]
0x1800a84bb  sub     eax, r8d
0x1800a84be  mov     bRedraw, [rsp+130h+sizeMinRight.cx]
0x1800a84c3  mov     edx, cs:?m_bHandleMinSize@CPane@@2HA; int CPane::m_bHandleMinSize
0x1800a84c9  cmp     eax, bRedraw
0x1800a84cc  jge     short loc_1800A84D9
0x1800a84ce  test    edx, edx
0x1800a84d0  jz      short loc_1800A84D9
0x1800a84d2  lea     eax, [hdwp+r9]
0x1800a84d6  mov     [rdi+8], eax
0x1800a84d9  mov     eax, [rdi+0Ch]
0x1800a84dc  mov     r8d, [rdi+4]
0x1800a84e0  sub     eax, r8d
0x1800a84e3  mov     bRedraw, [rsp+130h+sizeMinRight.cy]
0x1800a84e8  cmp     eax, bRedraw
0x1800a84eb  jge     short loc_1800A84F8
0x1800a84ed  test    edx, edx
0x1800a84ef  jz      short loc_1800A84F8
0x1800a84f1  lea     eax, [hdwp+r9]
0x1800a84f5  mov     [rdi+0Ch], eax
0x1800a84f8  mov     rax, [this]
0x1800a84fb  mov     r8d, r15d
0x1800a84fe  mov     r9, [r13+0]
0x1800a8502  mov     rect, rdi
0x1800a8505  mov     rax, [rax+478h]
0x1800a850c  call    cs:__guard_dispatch_icall_fptr
0x1800a8512  mov     [r13+0], rax
0x1800a8516  mov     this, [rbx+20h]
0x1800a851a  jmp     loc_1800A85B1
0x1800a851f  mov     edx, esi; bCheckVisibility
0x1800a8521  mov     this, rbx; this
0x1800a8524  call    ?IsLeftPartEmpty@CPaneContainer@@QEBAHH@Z; CPaneContainer::IsLeftPartEmpty(int)
0x1800a8529  test    eax, eax
0x1800a852b  jz      loc_1800A85E1
0x1800a8531  mov     edx, esi; bCheckVisibility
0x1800a8533  mov     this, rbx; this
0x1800a8536  call    ?IsRightPartEmpty@CPaneContainer@@QEBAHH@Z; CPaneContainer::IsRightPartEmpty(int)
0x1800a853b  test    eax, eax
0x1800a853d  jnz     loc_1800A85E1
0x1800a8543  mov     this, [rbx+10h]
0x1800a8547  test    this, this
0x1800a854a  jz      short loc_1800A85AD
0x1800a854c  mov     eax, [rdi+8]
0x1800a854f  mov     r8d, [rdi]
0x1800a8552  sub     eax, r8d
0x1800a8555  mov     bRedraw, dword ptr [rsp+130h+var_F8]
0x1800a855a  mov     edx, cs:?m_bHandleMinSize@CPane@@2HA; int CPane::m_bHandleMinSize
0x1800a8560  cmp     eax, bRedraw
0x1800a8563  jge     short loc_1800A8570
0x1800a8565  test    edx, edx
0x1800a8567  jz      short loc_1800A8570
0x1800a8569  lea     eax, [hdwp+r9]
0x1800a856d  mov     [rdi+8], eax
0x1800a8570  mov     eax, [rdi+0Ch]
0x1800a8573  mov     r8d, [rdi+4]
0x1800a8577  sub     eax, r8d
0x1800a857a  mov     bRedraw, dword ptr [rsp+130h+var_F8+4]
0x1800a857f  cmp     eax, bRedraw
0x1800a8582  jge     short loc_1800A858F
0x1800a8584  test    edx, edx
0x1800a8586  jz      short loc_1800A858F
0x1800a8588  lea     eax, [hdwp+r9]
0x1800a858c  mov     [rdi+0Ch], eax
0x1800a858f  mov     rax, [this]
0x1800a8592  mov     r8d, r15d
0x1800a8595  mov     r9, [r13+0]
0x1800a8599  mov     rect, rdi
0x1800a859c  mov     rax, [rax+478h]
0x1800a85a3  call    cs:__guard_dispatch_icall_fptr
0x1800a85a9  mov     [r13+0], rax
0x1800a85ad  mov     this, [rbx+28h]
0x1800a85b1  test    this, this
0x1800a85b4  jz      loc_1800A8D58
0x1800a85ba  mov     rax, [this]
0x1800a85bd  lea     rect, [rbp+57h+rc.right]
0x1800a85c1  movups  xmm0, xmmword ptr [rdi]
0x1800a85c4  mov     bRedraw, r15d
0x1800a85c7  mov     hdwp, r13
0x1800a85ca  mov     rax, [rax+0A0h]
0x1800a85d1  movdqu  xmmword ptr [rbp+57h+rc.right], xmm0
0x1800a85d6  call    cs:__guard_dispatch_icall_fptr
0x1800a85dc  jmp     loc_1800A8D58
0x1800a85e1  mov     edx, esi; bCheckVisibility
0x1800a85e3  mov     this, rbx; this
0x1800a85e6  call    ?IsLeftPartEmpty@CPaneContainer@@QEBAHH@Z; CPaneContainer::IsLeftPartEmpty(int)
0x1800a85eb  test    eax, eax
0x1800a85ed  jnz     loc_1800A8D58
0x1800a85f3  mov     edx, esi; bCheckVisibility
0x1800a85f5  mov     this, rbx; this
0x1800a85f8  call    ?IsRightPartEmpty@CPaneContainer@@QEBAHH@Z; CPaneContainer::IsRightPartEmpty(int)
0x1800a85fd  test    eax, eax
0x1800a85ff  jnz     loc_1800A8D58
0x1800a8605  movups  xmm0, xmmword ptr [rdi]
0x1800a8608  movdqu  xmmword ptr [rsp+130h+rectFinalLeft.right], xmm0
0x1800a860e  movdqu  xmmword ptr [rbp+57h+rectFinalRight.right], xmm0
0x1800a8613  movdqu  xmmword ptr [rbp+57h+rectFinalSlider.right], xmm0
0x1800a8618  cmp     [rbx+18h], r12
0x1800a861c  jz      loc_1800A8E97
0x1800a8622  mov     this, rbx; this
0x1800a8625  call    ?IsPaneDividerHorz@CPaneContainer@@IEBAHXZ; CPaneContainer::IsPaneDividerHorz(void)
0x1800a862a  or      esi, 0FFFFFFFFh
0x1800a862d  lea     r12d, [rsi+65h]
0x1800a8631  test    eax, eax
0x1800a8633  jz      loc_1800A89C5
0x1800a8639  mov     edx, [rbp+57h+rc.top]
0x1800a863c  mov     ecx, edx
0x1800a863e  mov     r11d, [rbp+57h+rectRight.bottom]
0x1800a8642  sub     ecx, r11d
0x1800a8645  mov     bRedraw, [rbp+57h+rectLeft.bottom]
0x1800a8649  sub     ecx, bRedraw
0x1800a864c  mov     r14d, [rbp+57h+rectRight.top]
0x1800a8650  mov     eax, r14d
0x1800a8653  mov     r8d, [rbp+57h+rectContainer.top]
0x1800a8657  add     ecx, r8d
0x1800a865a  mov     r15d, [rbp+57h+rectContainer.bottom]
0x1800a865e  sub     eax, r15d
0x1800a8661  cmp     ecx, eax
0x1800a8663  jg      short loc_1800A86AD
0x1800a8665  lea     this, [rbp+57h+rectLeft.right]; lprc
0x1800a8669  call    cs:__imp_IsRectEmpty
0x1800a866f  test    eax, eax
0x1800a8671  jnz     short loc_1800A8696
0x1800a8673  lea     this, [rbp+57h+rectRight.right]; lprc
0x1800a8677  call    cs:__imp_IsRectEmpty
0x1800a867d  test    eax, eax
0x1800a867f  jnz     short loc_1800A8696
0x1800a8681  mov     r14d, [rbp+57h+rectRight.top]
0x1800a8685  mov     r15d, [rbp+57h+rectContainer.bottom]
0x1800a8689  mov     r8d, [rbp+57h+rectContainer.top]
0x1800a868d  mov     bRedraw, [rbp+57h+rectLeft.bottom]
0x1800a8691  jmp     loc_1800A876B
0x1800a8696  mov     r14d, [rbp+57h+rectRight.top]
0x1800a869a  mov     r15d, [rbp+57h+rectContainer.bottom]
0x1800a869e  mov     r8d, [rbp+57h+rectContainer.top]
0x1800a86a2  mov     bRedraw, [rbp+57h+rectLeft.bottom]
0x1800a86a6  mov     edx, [rbp+57h+rc.top]
0x1800a86a9  mov     r11d, [rbp+57h+rectRight.bottom]
0x1800a86ad  mov     r10d, r14d
0x1800a86b0  mov     eax, r8d
0x1800a86b3  sub     r10d, r15d
0x1800a86b6  sub     eax, bRedraw
0x1800a86b9  mov     ecx, 32h ; '2'
0x1800a86be  mov     esi, ecx
  ... truncated ...
```
