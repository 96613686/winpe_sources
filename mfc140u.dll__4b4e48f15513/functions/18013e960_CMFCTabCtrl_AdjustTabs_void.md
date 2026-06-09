# CMFCTabCtrl::AdjustTabs(void)

- ea: `0x18013e960`
- end: `0x18013f478`
- name: `?AdjustTabs@CMFCTabCtrl@@MEAAXXZ`
- size: `2840`
- prototype: `void __fastcall(CMFCTabCtrl *this)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180009844`
- `0x18006cab0`
- `0x18013e960`
- `0x180231d70`
- `0x180280b50`
- `0x180280f60`
- `0x1802af110`
- `0x1802b0630`
- `0x1802b06e0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!SetRectEmpty` at `0x18013e9a5`
- `USER32!SetRectEmpty` at `0x18013ea24`
- `USER32!SetRectEmpty` at `0x18013ee8f`
- `USER32!SetRectEmpty` at `0x18013e9a5`
- `USER32!SetRectEmpty` at `0x18013ea24`
- `USER32!SetRectEmpty` at `0x18013ee8f`
- `USER32!SendMessageW` at `0x18013ea85`
- `USER32!SendMessageW` at `0x18013ea85`
- `USER32!IsRectEmpty` at `0x18013f430`
- `USER32!IsRectEmpty` at `0x18013f430`
- `USER32!InflateRect` at `0x18013f383`
- `USER32!InflateRect` at `0x18013f383`
- `USER32!OffsetRect` at `0x18013edd7`
- `USER32!OffsetRect` at `0x18013f243`
- `USER32!OffsetRect` at `0x18013f3c7`
- `USER32!OffsetRect` at `0x18013edd7`
- `USER32!OffsetRect` at `0x18013f243`
- `USER32!OffsetRect` at `0x18013f3c7`
- `GDI32!GetTextExtentPoint32W` at `0x18013ec1e`
- `GDI32!GetTextExtentPoint32W` at `0x18013ec1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMFCTabCtrl::AdjustTabs(CMFCTabCtrl *this)
{
  int v2; // ebx
  int v3; // esi
  __int64 v4; // rbx
  CToolTipCtrl *m_pToolTipClose; // rax
  HWND m_hWnd; // rcx
  int v7; // r13d
  int v8; // r8d
  int m_iTabsNum; // r9d
  __int64 v10; // rdx
  __int64 m_nSize; // rcx
  int v12; // r12d
  char *v13; // rbx
  int left; // esi
  int v15; // r14d
  int cx; // ecx
  int v17; // r8d
  int v18; // eax
  int v19; // eax
  int m_nTabMaxWidth; // ecx
  int top; // ecx
  int *v22; // r15
  int v23; // esi
  CToolTipCtrl *v24; // rcx
  int right; // r8d
  CToolTipCtrl *m_pToolTip; // rcx
  tagRECT *v27; // r9
  int v28; // edx
  __int64 v29; // rax
  bool v30; // zf
  int v31; // r10d
  int v32; // r14d
  int v33; // r8d
  int v34; // edx
  __int64 v35; // rcx
  __int64 v36; // rbx
  int v37; // r11d
  _DWORD *v38; // r11
  int v39; // r8d
  int v40; // r14d
  int v41; // ebx
  int v42; // eax
  __int64 v43; // r12
  __int64 v44; // rcx
  int v45; // r13d
  int *v46; // rbx
  CToolTipCtrl *v47; // rcx
  int v48; // edx
  int v49; // r15d
  int v50; // esi
  int v51; // ecx
  CToolTipCtrl *v52; // rcx
  int v53; // r15d
  tagRECT *v54; // r9
  __int64 m_iActiveTab; // rdx
  int v56; // esi
  CMFCVisualManager *Instance; // rax
  int v58; // eax
  CToolTipCtrl *v59; // rcx
  __int64 v60; // rcx
  int *v61; // rbx
  CToolTipCtrl *v62; // rax
  int v63; // [rsp+38h] [rbp-79h]
  int v64; // [rsp+38h] [rbp-79h]
  int v65; // [rsp+3Ch] [rbp-75h]
  __int64 v66; // [rsp+40h] [rbp-71h]
  int v67; // [rsp+40h] [rbp-71h]
  tagSIZE psizl; // [rsp+48h] [rbp-69h] BYREF
  CClientDC dc; // [rsp+50h] [rbp-61h] BYREF
  tagRECT RectTool; // [rsp+80h] [rbp-31h] BYREF
  tagRECT Rect; // [rsp+90h] [rbp-21h] BYREF
  RECT rc; // [rsp+A0h] [rbp-11h] BYREF
  __int128 v73; // [rsp+B0h] [rbp-1h] BYREF
  tagRECT v74; // [rsp+C0h] [rbp+Fh] BYREF
  tagRECT v75; // [rsp+D0h] [rbp+1Fh] BYREF

  this->m_bHiddenDocuments = 0;
  SetRectEmpty(&this->m_rectCloseButton);
  v2 = this->GetVisibleTabsNum(this);
  v65 = v2;
  if ( !v2 || !this->GetTabsHeight(this) )
    return;
  if ( !this->m_bHideSingleTab || v2 > 1 )
  {
    m_pToolTipClose = this->m_pToolTipClose;
    if ( m_pToolTipClose )
    {
      m_hWnd = m_pToolTipClose->m_hWnd;
      if ( m_hWnd )
      {
        if ( !(unsigned int)SendMessageW(m_hWnd, 0x40Du, 0, 0) )
        {
          RectTool = 0;
          CToolTipCtrl::AddTool(this->m_pToolTipClose, this, (const wchar_t *)0xFFFFFFFFFFFFFFFFLL, &RectTool, 1u);
        }
      }
    }
    rc = 0;
    CClientDC::CClientDC((CClientDC *)&dc.m_hDC, this);
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    dc.__vftable = (CClientDC_vtbl *)CDC::SelectObject((CDC *)&dc.m_hDC, &afxGlobalData.fontBold);
    if ( dc.__vftable )
    {
      this->m_nTabsTotalWidth = 0;
      v7 = this->m_rectTabsArea.left - this->m_nTabsHorzOffset;
      v8 = 0;
      v63 = 0;
      m_iTabsNum = this->m_iTabsNum;
      if ( m_iTabsNum > 0 )
      {
        v10 = 0;
        v66 = 0;
        while ( 1 )
        {
          m_nSize = this->m_arTabIndices.m_nSize;
          if ( m_nSize == m_iTabsNum )
          {
            if ( v10 < 0 || v10 >= m_nSize )
              goto LABEL_182;
            v12 = this->m_arTabIndices.m_pData[v10];
          }
          else
          {
            v12 = v8;
          }
          if ( v12 < 0 || v12 >= this->m_arTabs.m_nSize )
            goto LABEL_182;
          v13 = (char *)this->m_arTabs.m_pData[v12];
          left = 0;
          if ( *((_QWORD *)v13 + 3) || *((_DWORD *)v13 + 4) != -1 )
          {
            *(CSize *)&Rect.left = this->m_sizeImage;
            left = Rect.left;
          }
          if ( this->m_bIsActiveTabBold
            && (this->m_bIsOneNoteStyle || this->m_bIsVS2005Style || v12 == this->m_iActiveTab) )
          {
            if ( !afxGlobalData.m_bInitialized )
            {
              AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
              afxGlobalData.m_bInitialized = 1;
            }
            CDC::SelectObject((CDC *)&dc.m_hDC, &afxGlobalData.fontBold);
          }
          v15 = 0;
          if ( !*((_DWORD *)v13 + 18) )
          {
            *((_DWORD *)v13 + 14) = 0;
            goto LABEL_52;
          }
          if ( *((_DWORD *)v13 + 20) )
          {
            cx = 0;
          }
          else
          {
            GetTextExtentPoint32W(
              *(HDC *)&dc.m_bPrinting,
              *((LPCWSTR *)v13 + 1),
              *(_DWORD *)(*((_QWORD *)v13 + 1) - 16LL),
              &psizl);
            cx = psizl.cx;
          }
          v17 = left + CMFCBaseTabCtrl::AFX_TAB_IMAGE_MARGIN + cx + 2 * CMFCBaseTabCtrl::AFX_TAB_TEXT_MARGIN;
          *((_DWORD *)v13 + 14) = v17;
          if ( this->m_bLeftRightRounded )
          {
            v17 += (this->m_rectTabsArea.bottom - this->m_rectTabsArea.top) / 2;
            *((_DWORD *)v13 + 14) = v17;
            v15 = (this->m_rectTabsArea.bottom - this->m_rectTabsArea.top) / 2;
          }
          else
          {
            if ( this->m_bIsOneNoteStyle )
            {
              v18 = this->m_rectTabsArea.bottom + 2 * CMFCBaseTabCtrl::AFX_TAB_IMAGE_MARGIN - this->m_rectTabsArea.top;
LABEL_47:
              v17 += v18;
              *((_DWORD *)v13 + 14) = v17;
              v15 = this->m_rectTabsArea.bottom - this->m_rectTabsArea.top - CMFCBaseTabCtrl::AFX_TAB_IMAGE_MARGIN - 1;
              goto LABEL_48;
            }
            if ( this->m_bIsVS2005Style )
            {
              v18 = this->m_rectTabsArea.bottom - this->m_rectTabsArea.top;
              goto LABEL_47;
            }
          }
LABEL_48:
          if ( this->m_bActiveTabCloseButton && v12 == this->m_iActiveTab )
            *((_DWORD *)v13 + 14) = v17 + this->m_rectTabsArea.bottom - this->m_rectTabsArea.top - 2;
LABEL_52:
          if ( this->m_bIsActiveTabBold && v12 == this->m_iActiveTab )
          {
            if ( !afxGlobalData.m_bInitialized )
            {
              AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
              afxGlobalData.m_bInitialized = 1;
            }
            CDC::SelectObject((CDC *)&dc.m_hDC, &afxGlobalData.fontRegular);
          }
          v19 = *((_DWORD *)v13 + 14);
          if ( this->m_bScroll )
          {
            m_nTabMaxWidth = this->m_nTabMaxWidth;
            if ( m_nTabMaxWidth > 0 && v19 >= m_nTabMaxWidth )
              v19 = this->m_nTabMaxWidth;
          }
          top = this->m_rectTabsArea.top;
          RectTool.left = v7;
          RectTool.right = v7 + v19;
          RectTool.top = top;
          RectTool.bottom = this->m_rectTabsArea.bottom - 2;
          v22 = (int *)(v13 + 32);
          *((tagRECT *)v13 + 2) = RectTool;
          v23 = 0;
          if ( *((_DWORD *)v13 + 18) )
          {
            if ( this->m_location == LOCATION_TOP )
              OffsetRect((LPRECT)v13 + 2, 0, 2);
            if ( !this->m_bTabDocumentsMenu )
              goto LABEL_73;
            right = this->m_rectTabsArea.right;
            if ( *((_DWORD *)v13 + 10) <= right )
              goto LABEL_73;
            if ( v12 == this->m_iActiveTab && !v63 && right - *v22 >= v15 + 2 * CMFCBaseTabCtrl::AFX_TAB_TEXT_MARGIN )
            {
              *((_DWORD *)v13 + 10) = right;
LABEL_73:
              m_pToolTip = this->m_pToolTip;
              if ( m_pToolTip && m_pToolTip->m_hWnd )
              {
                if ( *((_DWORD *)v13 + 21) || this->m_bCustomToolTips )
                  v23 = 1;
                if ( *v22 < this->m_rectTabsArea.left || *((_DWORD *)v13 + 10) > this->m_rectTabsArea.right )
                  v23 = 1;
                if ( this->m_bScroll && this->m_nTabMaxWidth > 0 && *((_DWORD *)v13 + 10) - *v22 < *((_DWORD *)v13 + 14) )
                {
                  v23 = 1;
                  goto LABEL_87;
                }
                if ( v23 )
                {
LABEL_87:
                  v73 = *((_OWORD *)v13 + 2);
                  v27 = (tagRECT *)&v73;
                }
                else
                {
                  v74 = 0;
                  v27 = &v74;
                }
                CToolTipCtrl::SetToolRect(m_pToolTip, this, *((int *)v13 + 15), v27);
                if ( v23 && v12 == this->m_iActiveTab )
                  rc = (RECT)*((_OWORD *)v13 + 2);
              }
              v7 += *((_DWORD *)v13 + 10) - *((_DWORD *)v13 + 8) - v15 + 1;
              v28 = *((_DWORD *)v13 + 10) - *((_DWORD *)v13 + 8) + this->m_nTabsTotalWidth + 1;
              this->m_nTabsTotalWidth = v28;
              v29 = this->m_arTabIndices.m_nSize;
              if ( v29 == this->m_arTabs.m_nSize )
              {
                if ( v29 <= 0 )
                  goto LABEL_182;
                v30 = *this->m_arTabIndices.m_pData == v12;
              }
              else
              {
                v30 = v12 == 0;
              }
              if ( !v30 )
                this->m_nTabsTotalWidth = v28 - v15;
              if ( this->m_bFlat )
                *((_DWORD *)v13 + 10) += this->m_nTabsHeight / 2;
              goto LABEL_100;
            }
            *((_DWORD *)v13 + 14) = 0;
            SetRectEmpty((LPRECT)v13 + 2);
            this->m_bHiddenDocuments = 1;
          }
          else
          {
            v24 = this->m_pToolTip;
            if ( v24 && v24->m_hWnd )
            {
              Rect = 0;
              CToolTipCtrl::SetToolRect(v24, this, *((int *)v13 + 15), &Rect);
            }
          }
LABEL_100:
          v8 = v63 + 1;
          v63 = v8;
          v10 = ++v66;
          m_iTabsNum = this->m_iTabsNum;
          if ( v8 >= m_iTabsNum )
          {
            v2 = v65;
            break;
          }
        }
      }
      if ( this->m_bScroll || v7 < this->m_rectTabsArea.right )
      {
        this->m_nTabsTotalWidth += this->m_nTabsHeight / 2;
      }
      else
      {
        v31 = (this->m_rectTabsArea.right - this->m_rectTabsArea.left) / v2 - 1;
        if ( this->m_bLeftRightRounded )
        {
          v31 = (this->m_rectTabsArea.right
               - this->m_rectTabsArea.left
               - (this->m_rectTabsArea.bottom - this->m_rectTabsArea.top) / 3)
              / v2;
          if ( (this->m_rectTabsArea.bottom - this->m_rectTabsArea.top) / 2 + this->m_sizeImage.cx > v31 )
            v31 = (this->m_rectTabsArea.bottom - this->m_rectTabsArea.top) / 2 + this->m_sizeImage.cx;
        }
        v32 = 0;
        Rect.left = 0;
        v33 = v2;
        v34 = 0;
        if ( m_iTabsNum > 0 )
        {
          v35 = 0;
          v36 = this->m_arTabIndices.m_nSize;
          do
          {
            if ( v36 == m_iTabsNum )
            {
              if ( v35 < 0 || v35 >= v36 )
                goto LABEL_182;
              v37 = this->m_arTabIndices.m_pData[v35];
            }
            else
            {
              v37 = v34;
            }
            if ( v37 < 0LL || v37 >= this->m_arTabs.m_nSize )
              goto LABEL_182;
            v38 = this->m_arTabs.m_pData[v37];
            if ( v38[18] && v38[14] < v31 )
            {
              v32 += v31 - v38[14];
              Rect.left = v32;
              --v33;
            }
            ++v34;
            ++v35;
          }
          while ( v34 < m_iTabsNum );
        }
        if ( v33 > 0 )
        {
          v39 = v32 / v33 + v31;
          v64 = v39;
          v40 = this->m_rectTabsArea.left;
          v41 = 0;
          v67 = 0;
          v42 = this->m_iTabsNum;
          if ( v42 > 0 )
          {
            v43 = 0;
            do
            {
              v44 = this->m_arTabIndices.m_nSize;
              if ( v44 == v42 )
              {
                if ( v43 < 0 || v43 >= v44 )
                  goto LABEL_182;
                v45 = this->m_arTabIndices.m_pData[v43];
              }
              else
              {
                v45 = v41;
              }
              if ( v45 < 0 || v45 >= this->m_arTabs.m_nSize )
                goto LABEL_182;
              v46 = (int *)this->m_arTabs.m_pData[v45];
              if ( v46[18] )
              {
                v48 = 0;
                if ( *((_QWORD *)v46 + 3) || v46[4] != -1 )
                {
                  psizl = (tagSIZE)this->m_sizeImage;
                  v48 = psizl.cx;
                }
                v49 = v46[14];
                v50 = v49;
                if ( v49 > v39 )
                  v50 = v39;
                if ( v39 >= v48 + CMFCBaseTabCtrl::AFX_TAB_IMAGE_MARGIN )
                {
                  if ( !*(_DWORD *)(*((_QWORD *)v46 + 1) - 16LL) || v46[20] )
                    v50 = v48 + 2 * CMFCBaseTabCtrl::AFX_TAB_TEXT_MARGIN;
                }
                else
                {
                  v50 = (this->m_rectTabsArea.right + 2 * this->m_nTabBorderSize - this->m_rectTabsArea.left) / v65;
                }
                if ( this->m_bLeftRightRounded )
                  v50 = (this->m_rectTabsArea.bottom - this->m_rectTabsArea.top) / 2 + v50 - 1;
                v51 = this->m_rectTabsArea.top;
                RectTool.left = v40;
                RectTool.right = v50 + v40;
                RectTool.top = v51;
                RectTool.bottom = this->m_rectTabsArea.bottom - 2;
                *((tagRECT *)v46 + 2) = RectTool;
                if ( !this->m_bFlat )
                {
                  if ( this->m_location == LOCATION_TOP )
                  {
                    OffsetRect((LPRECT)v46 + 2, 0, 2);
                    v39 = v64;
                  }
                  v52 = this->m_pToolTip;
                  if ( v52 && v52->m_hWnd )
                  {
                    if ( v49 > v39 || v46[21] || this->m_bCustomToolTips )
                    {
                      v53 = 1;
                      v75 = (tagRECT)*((_OWORD *)v46 + 2);
                      v54 = &v75;
                    }
                    else
                    {
                      v53 = 0;
                      v73 = 0;
                      v54 = (tagRECT *)&v73;
                    }
                    CToolTipCtrl::SetToolRect(v52, this, v46[15], v54);
                    if ( v53 )
                    {
                      if ( v45 == this->m_iActiveTab )
                        rc = (RECT)*((_OWORD *)v46 + 2);
                    }
                  }
                }
                v40 += v50;
                if ( this->m_bLeftRightRounded )
                  v40 += (this->m_rectTabsArea.bottom - this->m_rectTabsArea.top) / -2;
                if ( Rect.left > 0 )
                  ++v40;
              }
              else
              {
                v47 = this->m_pToolTip;
                if ( !v47 || !v47->m_hWnd )
                  goto LABEL_164;
                v74 = 0;
                CToolTipCtrl::SetToolRect(v47, this, v46[15], &v74);
              }
              v39 = v64;
LABEL_164:
              v41 = v67 + 1;
              v67 = v41;
              ++v43;
              v42 = this->m_iTabsNum;
            }
            while ( v41 < v42 );
          }
        }
      }
      CDC::SelectObject((CDC *)&dc.m_hDC, (CFont *)dc.__vftable);
      if ( !this->m_bActiveTabCloseButton )
        goto LABEL_180;
      m_iActiveTab = (unsigned int)this->m_iActiveTab;
      if ( (int)m_iActiveTab < 0 )
        goto LABEL_180;
      this->GetTabRect(this, m_iActiveTab, &this->m_rectCloseButton);
      this->m_rectCloseButton.left = this->m_rectCloseButton.right
                                   + this->m_rectCloseButton.top
                                   - this->m_rectCloseButton.bottom;
      InflateRect(&this->m_rectCloseButton, -2, -2);
      v56 = -1;
      if ( this->m_location == LOCATION_TOP )
        v56 = 1;
      Instance = CMFCVisualManager::GetInstance();
      v58 = Instance->GetTabHorzMargin(Instance, this);
      OffsetRect(&this->m_rectCloseButton, -v58, v56);
      v59 = this->m_pToolTipClose;
      if ( !v59 || !v59->m_hWnd )
      {
LABEL_180:
        CClientDC::~CClientDC((CClientDC *)&dc.m_hDC);
        return;
      }
      CToolTipCtrl::SetToolRect(v59, this, 1u, &this->m_rectCloseButton);
      v60 = this->m_iActiveTab;
      if ( v60 >= 0 && v60 < this->m_arTabs.m_nSize )
      {
        v61 = (int *)this->m_arTabs.m_pData[v60];
        v62 = this->m_pToolTip;
        if ( v62 && v62->m_hWnd && v61 && !IsRectEmpty(&rc) )
        {
          rc.right = this->m_rectCloseButton.left - 1;
          CToolTipCtrl::SetToolRect(this->m_pToolTip, this, v61[15], &rc);
        }
        goto LABEL_180;
      }
    }
LABEL_182:
    AfxThrowInvalidArgException();
  }
  v3 = 0;
  if ( this->m_iTabsNum > 0 )
  {
    v4 = 0;
    do
    {
      if ( v4 < 0 || v4 >= this->m_arTabs.m_nSize )
        AfxThrowInvalidArgException();
      SetRectEmpty((LPRECT)this->m_arTabs.m_pData[v4] + 2);
      ++v3;
      ++v4;
    }
    while ( v3 < this->m_iTabsNum );
  }
}

```

## disassembly

```asm
0x18013e960  mov     rax, rsp
0x18013e963  mov     [rax+10h], rbx
0x18013e967  mov     [rax+18h], rsi
0x18013e96b  mov     [rax+20h], rdi
0x18013e96f  push    rbp
0x18013e970  push    r12
0x18013e972  push    r13
0x18013e974  push    r14
0x18013e976  push    r15
0x18013e978  lea     rbp, [rax-5Fh]
0x18013e97c  sub     rsp, 0E0h
0x18013e983  mov     rax, cs:__security_cookie
0x18013e98a  xor     rax, rsp
0x18013e98d  mov     [rbp+57h+var_28], rax
0x18013e991  mov     rdi, this
0x18013e994  xor     r15d, r15d
0x18013e997  mov     [this+404h], r15d
0x18013e99e  add     this, 34Ch; lprc
0x18013e9a5  call    cs:__imp_SetRectEmpty
0x18013e9ab  mov     rax, [rdi]
0x18013e9ae  mov     this, rdi
0x18013e9b1  mov     rax, [rax+358h]
0x18013e9b8  call    cs:__guard_dispatch_icall_fptr
0x18013e9be  mov     ebx, eax
0x18013e9c0  mov     [rbp+57h+var_CC], eax
0x18013e9c3  test    eax, eax
0x18013e9c5  jz      short loc_18013EA38
0x18013e9c7  mov     this, [rdi]
0x18013e9ca  mov     rax, [this+308h]
0x18013e9d1  mov     this, rdi
0x18013e9d4  call    cs:__guard_dispatch_icall_fptr
0x18013e9da  test    eax, eax
0x18013e9dc  jz      short loc_18013EA38
0x18013e9de  lea     r12d, [r15+1]
0x18013e9e2  cmp     [rdi+1F4h], r15d
0x18013e9e9  jz      short loc_18013EA65
0x18013e9eb  cmp     ebx, r12d
0x18013e9ee  jg      short loc_18013EA65
0x18013e9f0  mov     esi, r15d
0x18013e9f3  cmp     [rdi+150h], r15d
0x18013e9fa  jle     short loc_18013EA38
0x18013e9fc  mov     ebx, r15d
0x18013e9ff  test    rbx, rbx
0x18013ea02  js      loc_18013F46C
0x18013ea08  cmp     rbx, [rdi+110h]
0x18013ea0f  jge     loc_18013F46C
0x18013ea15  mov     rax, [rdi+108h]
0x18013ea1c  mov     this, [rax+rbx*8]
0x18013ea20  add     this, 20h ; ' '; lprc
0x18013ea24  call    cs:__imp_SetRectEmpty
0x18013ea2a  add     esi, r12d
0x18013ea2d  add     rbx, r12
0x18013ea30  cmp     esi, [rdi+150h]
0x18013ea36  jl      short loc_18013E9FF
0x18013ea38  mov     this, [rbp+57h+var_28]
0x18013ea3c  xor     this, rsp; StackCookie
0x18013ea3f  call    __security_check_cookie
0x18013ea44  lea     r11, [rsp+100h+var_20]
0x18013ea4c  mov     rbx, [r11+38h]
0x18013ea50  mov     rsi, [r11+40h]
0x18013ea54  mov     rdi, [r11+48h]
0x18013ea58  mov     rsp, r11
0x18013ea5b  pop     r15
0x18013ea5d  pop     r14
0x18013ea5f  pop     r13
0x18013ea61  pop     r12
0x18013ea63  pop     rbp
0x18013ea64  retn
0x18013ea65  mov     rax, [rdi+1C0h]
0x18013ea6c  test    rax, rax
0x18013ea6f  jz      short loc_18013EAB2
0x18013ea71  mov     this, [rax+40h]; hWnd
0x18013ea75  test    this, this
0x18013ea78  jz      short loc_18013EAB2
0x18013ea7a  xor     r9d, r9d; lParam
0x18013ea7d  xor     r8d, r8d; wParam
0x18013ea80  mov     edx, 40Dh; Msg
0x18013ea85  call    cs:__imp_SendMessageW
0x18013ea8b  test    eax, eax
0x18013ea8d  jnz     short loc_18013EAB2
0x18013ea8f  xorps   xmm0, xmm0
0x18013ea92  movups  xmmword ptr [rbp+57h+RectTool.left], xmm0
0x18013ea96  mov     [rsp+100h+nIDTool], r12; nIDTool
0x18013ea9b  lea     r9, [rbp+57h+RectTool]; lpRectTool
0x18013ea9f  or      r8, 0FFFFFFFFFFFFFFFFh; lpszText
0x18013eaa3  mov     rdx, rdi; pWnd
0x18013eaa6  mov     this, [rdi+1C0h]; this
0x18013eaad  call    ?AddTool@CToolTipCtrl@@QEAAHPEAVCWnd@@PEB_WPEBUtagRECT@@_K@Z; CToolTipCtrl::AddTool(CWnd *,wchar_t const *,tagRECT const *,unsigned __int64)
0x18013eab2  xorps   xmm0, xmm0
0x18013eab5  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18013eab9  mov     rdx, rdi; pWnd
0x18013eabc  lea     this, [rbp+57h+dc.m_hDC]; this
0x18013eac0  call    ??0CClientDC@@QEAA@PEAVCWnd@@@Z; CClientDC::CClientDC(CWnd *)
0x18013eac5  nop
0x18013eac6  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r15d; AFX_GLOBAL_DATA afxGlobalData ...
0x18013eacd  jnz     short loc_18013EAE2
0x18013eacf  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18013ead6  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18013eadb  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r12d; AFX_GLOBAL_DATA afxGlobalData ...
0x18013eae2  lea     rdx, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.fontBold; pFont
0x18013eae9  lea     this, [rbp+57h+dc.m_hDC]; this
0x18013eaed  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18013eaf2  mov     [rbp+57h+dc.__vftable], rax
0x18013eaf6  test    rax, rax
0x18013eaf9  jz      loc_18013F472
0x18013eaff  mov     [rdi+41Ch], r15d
0x18013eb06  mov     r13d, [rdi+44Ch]
0x18013eb0d  sub     r13d, [rdi+414h]
0x18013eb14  mov     r8d, r15d
0x18013eb17  mov     [rbp+57h+var_D0], r15d
0x18013eb1b  mov     r9d, [rdi+150h]
0x18013eb22  test    r9d, r9d
0x18013eb25  jle     loc_18013EF90
0x18013eb2b  mov     rdx, r15
0x18013eb2e  mov     [rbp+57h+var_C8], rdx
0x18013eb32  mov     this, [rdi+138h]
0x18013eb39  movsxd  rax, r9d
0x18013eb3c  cmp     this, rax
0x18013eb3f  jnz     short loc_18013EB60
0x18013eb41  test    rdx, rdx
0x18013eb44  js      loc_18013F472
0x18013eb4a  cmp     rdx, this
0x18013eb4d  jge     loc_18013F472
0x18013eb53  mov     rax, [rdi+130h]
0x18013eb5a  mov     r12d, [rax+rdx*4]
0x18013eb5e  jmp     short loc_18013EB63
0x18013eb60  mov     r12d, r8d
0x18013eb63  movsxd  rbx, r12d
0x18013eb66  test    r12d, r12d
0x18013eb69  js      loc_18013F472
0x18013eb6f  cmp     rbx, [rdi+110h]
0x18013eb76  jge     loc_18013F472
0x18013eb7c  mov     rax, [rdi+108h]
0x18013eb83  mov     rbx, [rax+rbx*8]
0x18013eb87  mov     esi, r15d
0x18013eb8a  cmp     [rbx+18h], r15
0x18013eb8e  jnz     short loc_18013EB96
0x18013eb90  cmp     dword ptr [rbx+10h], 0FFFFFFFFh
0x18013eb94  jz      short loc_18013EBA3
0x18013eb96  mov     rax, [rdi+178h]
0x18013eb9d  mov     qword ptr [rbp+57h+Rect.left], rax
0x18013eba1  mov     esi, eax
0x18013eba3  cmp     [rdi+3F8h], r15d
0x18013ebaa  jz      short loc_18013EBF6
0x18013ebac  cmp     [rdi+3C4h], r15d
0x18013ebb3  jnz     short loc_18013EBC7
0x18013ebb5  cmp     [rdi+3C8h], r15d
0x18013ebbc  jnz     short loc_18013EBC7
0x18013ebbe  cmp     r12d, [rdi+154h]
0x18013ebc5  jnz     short loc_18013EBF6
0x18013ebc7  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r15d; AFX_GLOBAL_DATA afxGlobalData ...
0x18013ebce  jnz     short loc_18013EBE6
0x18013ebd0  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18013ebd7  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18013ebdc  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18013ebe6  lea     rdx, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.fontBold; pFont
0x18013ebed  lea     this, [rbp+57h+dc.m_hDC]; this
0x18013ebf1  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18013ebf6  mov     r14d, r15d
0x18013ebf9  cmp     [rbx+48h], r15d
0x18013ebfd  jz      loc_18013ECF3
0x18013ec03  cmp     [rbx+50h], r15d
0x18013ec07  jz      short loc_18013EC0E
0x18013ec09  mov     ecx, r15d
0x18013ec0c  jmp     short loc_18013EC27
0x18013ec0e  mov     rdx, [rbx+8]; lpString
0x18013ec12  lea     r9, [rbp+57h+psizl]; psizl
0x18013ec16  mov     r8d, [rdx-10h]; c
0x18013ec1a  mov     this, qword ptr [rbp+57h+dc.m_bPrinting]; hdc
0x18013ec1e  call    cs:__imp_GetTextExtentPoint32W
0x18013ec24  mov     ecx, [rbp+57h+psizl.cx]
0x18013ec27  mov     eax, cs:?AFX_TAB_TEXT_MARGIN@CMFCBaseTabCtrl@@2HA; int CMFCBaseTabCtrl::AFX_TAB_TEXT_MARGIN
0x18013ec2d  lea     r8d, [this+rax*2]
0x18013ec31  add     r8d, cs:?AFX_TAB_IMAGE_MARGIN@CMFCBaseTabCtrl@@2HA; int CMFCBaseTabCtrl::AFX_TAB_IMAGE_MARGIN
0x18013ec38  add     r8d, esi
0x18013ec3b  mov     [rbx+38h], r8d
0x18013ec3f  cmp     [rdi+3CCh], r15d
0x18013ec46  jz      short loc_18013EC77
0x18013ec48  mov     eax, [rdi+458h]
0x18013ec4e  sub     eax, [rdi+450h]
0x18013ec54  jns     short loc_18013EC58
0x18013ec56  inc     eax
0x18013ec58  sar     eax, 1
0x18013ec5a  add     r8d, eax
0x18013ec5d  mov     [rbx+38h], r8d
0x18013ec61  mov     eax, [rdi+458h]
0x18013ec67  sub     eax, [rdi+450h]
0x18013ec6d  cdq
0x18013ec6e  sub     eax, edx
0x18013ec70  sar     eax, 1
0x18013ec72  mov     r14d, eax
0x18013ec75  jmp     short loc_18013ECCA
0x18013ec77  cmp     [rdi+3C4h], r15d
0x18013ec7e  jz      short loc_18013EC96
0x18013ec80  mov     eax, cs:?AFX_TAB_IMAGE_MARGIN@CMFCBaseTabCtrl@@2HA; int CMFCBaseTabCtrl::AFX_TAB_IMAGE_MARGIN
0x18013ec86  add     eax, eax
0x18013ec88  sub     eax, [rdi+450h]
0x18013ec8e  add     eax, [rdi+458h]
0x18013ec94  jmp     short loc_18013ECAB
0x18013ec96  cmp     [rdi+3C8h], r15d
0x18013ec9d  jz      short loc_18013ECCA
0x18013ec9f  mov     eax, [rdi+458h]
0x18013eca5  sub     eax, [rdi+450h]
0x18013ecab  add     r8d, eax
0x18013ecae  mov     [rbx+38h], r8d
0x18013ecb2  mov     r14d, [rdi+458h]
0x18013ecb9  sub     r14d, [rdi+450h]
0x18013ecc0  sub     r14d, cs:?AFX_TAB_IMAGE_MARGIN@CMFCBaseTabCtrl@@2HA; int CMFCBaseTabCtrl::AFX_TAB_IMAGE_MARGIN
0x18013ecc7  dec     r14d
0x18013ecca  cmp     [rdi+3FCh], r15d
0x18013ecd1  jz      short loc_18013ECF7
0x18013ecd3  cmp     r12d, [rdi+154h]
0x18013ecda  jnz     short loc_18013ECF7
0x18013ecdc  mov     eax, [rdi+458h]
0x18013ece2  sub     eax, [rdi+450h]
0x18013ece8  add     eax, 0FFFFFFFEh
0x18013eceb  add     eax, r8d
0x18013ecee  mov     [rbx+38h], eax
0x18013ecf1  jmp     short loc_18013ECF7
0x18013ecf3  mov     [rbx+38h], r15d
0x18013ecf7  cmp     [rdi+3F8h], r15d
0x18013ecfe  jz      short loc_18013ED38
0x18013ed00  cmp     r12d, [rdi+154h]
0x18013ed07  jnz     short loc_18013ED38
0x18013ed09  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r15d; AFX_GLOBAL_DATA afxGlobalData ...
0x18013ed10  jnz     short loc_18013ED28
0x18013ed12  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18013ed19  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18013ed1e  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18013ed28  lea     rdx, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.fontRegular; pFont
0x18013ed2f  lea     this, [rbp+57h+dc.m_hDC]; this
0x18013ed33  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18013ed38  mov     eax, [rbx+38h]
0x18013ed3b  cmp     [rdi+3D4h], r15d
0x18013ed42  jz      short loc_18013ED53
0x18013ed44  mov     ecx, [rdi+428h]
0x18013ed4a  test    ecx, ecx
0x18013ed4c  jle     short loc_18013ED53
0x18013ed4e  cmp     eax, ecx
0x18013ed50  cmovge  eax, ecx
0x18013ed53  mov     ecx, [rdi+450h]
0x18013ed59  mov     [rbp+57h+RectTool.left], r13d
0x18013ed5d  add     eax, r13d
0x18013ed60  mov     [rbp+57h+RectTool.right], eax
0x18013ed63  mov     [rbp+57h+RectTool.top], ecx
0x18013ed66  mov     eax, [rdi+458h]
0x18013ed6c  sub     eax, 2
0x18013ed6f  mov     [rbp+57h+RectTool.bottom], eax
0x18013ed72  lea     r15, [rbx+20h]
0x18013ed76  movups  xmm0, xmmword ptr [rbp+57h+RectTool.left]
0x18013ed7a  movdqu  xmmword ptr [r15], xmm0
0x18013ed7f  xor     esi, esi
0x18013ed81  cmp     [rbx+48h], esi
0x18013ed84  jnz     short loc_18013EDBF
0x18013ed86  mov     this, [rdi+1B8h]; this
0x18013ed8d  xor     r15d, r15d
0x18013ed90  test    this, this
0x18013ed93  jz      loc_18013EF61
0x18013ed99  cmp     [this+40h], r15
0x18013ed9d  jz      loc_18013EF61
0x18013eda3  xorps   xmm0, xmm0
0x18013eda6  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18013edaa  movsxd  r8, dword ptr [rbx+3Ch]; nIDTool
0x18013edae  lea     r9, [rbp+57h+Rect]; lpRect
0x18013edb2  mov     rdx, rdi; pWnd
0x18013edb5  call    ?SetToolRect@CToolTipCtrl@@QEAAXPEAVCWnd@@_KPEBUtagRECT@@@Z; CToolTipCtrl::SetToolRect(CWnd *,unsigned __int64,tagRECT const *)
0x18013edba  jmp     loc_18013EF61
0x18013edbf  mov     r9d, 1
0x18013edc5  cmp     [rdi+0F8h], r9d
0x18013edcc  jnz     short loc_18013EDE3
0x18013edce  xor     edx, edx; dx
0x18013edd0  lea     r8d, [r9+1]; dy
0x18013edd4  mov     this, r15; lprc
0x18013edd7  call    cs:__imp_OffsetRect
0x18013eddd  mov     r9d, 1
0x18013ede3  cmp     [rdi+400h], esi
0x18013ede9  jz      short loc_18013EE22
0x18013edeb  mov     r8d, [rdi+454h]
0x18013edf2  cmp     [rbx+28h], r8d
0x18013edf6  jle     short loc_18013EE22
0x18013edf8  cmp     r12d, [rdi+154h]
0x18013edff  jnz     loc_18013EE89
0x18013ee05  cmp     [rbp+57h+var_D0], esi
0x18013ee08  jnz     short loc_18013EE89
0x18013ee0a  mov     edx, r8d
0x18013ee0d  sub     edx, [r15]
0x18013ee10  mov     eax, cs:?AFX_TAB_TEXT_MARGIN@CMFCBaseTabCtrl@@2HA; int CMFCBaseTabCtrl::AFX_TAB_TEXT_MARGIN
0x18013ee16  lea     ecx, [r14+rax*2]
0x18013ee1a  cmp     edx, ecx
0x18013ee1c  jl      short loc_18013EE89
0x18013ee1e  mov     [rbx+28h], r8d
0x18013ee22  mov     this, [rdi+1B8h]; this
0x18013ee29  test    this, this
0x18013ee2c  jz      loc_18013EEEC
0x18013ee32  cmp     [this+40h], rsi
0x18013ee36  jz      loc_18013EEEC
0x18013ee3c  cmp     [rbx+54h], esi
0x18013ee3f  jnz     short loc_18013EE49
0x18013ee41  cmp     [rdi+1C8h], esi
0x18013ee47  jz      short loc_18013EE4C
  ... truncated ...
```
