# CMFCOutlookBarTabCtrl::RecalcLayout(void)

- ea: `0x18009ebf0`
- end: `0x18009f353`
- name: `?RecalcLayout@CMFCOutlookBarTabCtrl@@UEAAXXZ`
- size: `1891`
- prototype: `void __fastcall(CMFCOutlookBarTabCtrl *this)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x18006cab0`
- `0x18009ebf0`
- `0x1800a0d60`
- `0x1800a1010`
- `0x180231d70`
- `0x18023f820`
- `0x180296d00`
- `0x1802b66c0`
- `0x1802b6730`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetClientRect` at `0x18009ed5c`
- `USER32!GetClientRect` at `0x18009ed5c`
- `USER32!SetRectEmpty` at `0x18009ee7d`
- `USER32!SetRectEmpty` at `0x18009ee8a`
- `USER32!SetRectEmpty` at `0x18009ef49`
- `USER32!SetRectEmpty` at `0x18009ef5b`
- `USER32!SetRectEmpty` at `0x18009ee7d`
- `USER32!SetRectEmpty` at `0x18009ee8a`
- `USER32!SetRectEmpty` at `0x18009ef49`
- `USER32!SetRectEmpty` at `0x18009ef5b`
- `USER32!SendMessageW` at `0x18009ed31`
- `USER32!SendMessageW` at `0x18009ed46`
- `USER32!SendMessageW` at `0x18009ed31`
- `USER32!SendMessageW` at `0x18009ed46`
- `USER32!GetParent` at `0x18009f282`
- `USER32!GetParent` at `0x18009f282`
- `USER32!InflateRect` at `0x18009ed71`
- `USER32!InflateRect` at `0x18009eeb5`
- `USER32!InflateRect` at `0x18009ed71`
- `USER32!InflateRect` at `0x18009eeb5`
- `USER32!RedrawWindow` at `0x18009f263`
- `USER32!RedrawWindow` at `0x18009f278`
- `USER32!RedrawWindow` at `0x18009f29c`
- `USER32!RedrawWindow` at `0x18009f2de`
- `USER32!RedrawWindow` at `0x18009f263`
- `USER32!RedrawWindow` at `0x18009f278`
- `USER32!RedrawWindow` at `0x18009f29c`
- `USER32!RedrawWindow` at `0x18009f2de`

## pseudocode

```c
void __fastcall CMFCOutlookBarTabCtrl::RecalcLayout(CMFCOutlookBarTabCtrl *this)
{
  int v1; // r12d
  int v3; // r13d
  int v4; // r14d
  CSize *p_m_sizeToolbarImage; // rdx
  int v6; // edi
  double m_dblRibbonImageScale; // xmm0_8
  int v8; // eax
  HWND__ *m_hWnd; // rcx
  int (__fastcall *GetVisibleTabsNum)(CMFCBaseTabCtrl *); // rax
  int v11; // eax
  int v12; // esi
  int m_nVisiblePageButtons; // edi
  int v14; // eax
  int top; // edx
  int v16; // edi
  tagRECT v17; // xmm0
  int v18; // r8d
  int v19; // eax
  int v20; // eax
  int bottom; // r15d
  int v22; // r14d
  __int64 v23; // r13
  tagRECT *v24; // rdi
  int v25; // eax
  int m_iActiveTab; // eax
  tagRECT v27; // xmm0
  int v28; // r8d
  CMFCOutlookBarScrollButton *p_m_btnUp; // rcx
  int v30; // r8d
  int m_iTabsNum; // r10d
  int v32; // edx
  __int64 v33; // rcx
  _DWORD *v34; // r9
  int v35; // eax
  int cy; // eax
  int right; // r8d
  int v38; // r9d
  __int64 v39; // r14
  CObject *v40; // rdi
  CObject **v41; // rax
  CObject *v42; // r15
  CObject *v43; // rax
  CMFCOutlookBarToolBar *p_m_wndToolBar; // rdi
  HWND Parent; // rax
  CWnd *v46; // rax
  int IsMode2003; // [rsp+50h] [rbp-9h]
  CWnd **v48; // [rsp+50h] [rbp-9h]
  int v49; // [rsp+58h] [rbp-1h]
  CSize m_sizeToolbarImage; // [rsp+58h] [rbp-1h]
  int y[4]; // [rsp+60h] [rbp+7h] BYREF
  tagRECT Rect; // [rsp+70h] [rbp+17h] BYREF

  if ( this )
  {
    v1 = 0;
    if ( this->m_hWnd )
    {
      if ( this->m_nTabsHeight )
      {
        IsMode2003 = CMFCOutlookBarTabCtrl::IsMode2003(this);
        v3 = IsMode2003;
        v49 = 0;
        v4 = 0;
        if ( IsMode2003 )
        {
          if ( this == (CMFCOutlookBarTabCtrl *)-1048LL || !this->m_imagesToolbar.m_hImageList )
          {
            p_m_sizeToolbarImage = this->GetImageSize(this, y);
            m_sizeToolbarImage = *p_m_sizeToolbarImage;
          }
          else
          {
            p_m_sizeToolbarImage = &this->m_sizeToolbarImage;
            m_sizeToolbarImage = this->m_sizeToolbarImage;
          }
          v6 = m_sizeToolbarImage.cy;
          if ( !HIDWORD(*(unsigned __int64 *)p_m_sizeToolbarImage) )
            v6 = 16;
          if ( !afxGlobalData.m_bInitialized )
          {
            AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
            afxGlobalData.m_bInitialized = 1;
          }
          if ( afxGlobalData.m_bIsRibbonImageScale )
            m_dblRibbonImageScale = afxGlobalData.m_dblRibbonImageScale;
          else
            m_dblRibbonImageScale = DOUBLE_1_0;
          v8 = 12;
          if ( m_dblRibbonImageScale != 1.0 )
            v8 = (int)(m_dblRibbonImageScale * 12.0 + 0.5);
          v4 = v8 + v6;
          v49 = v8 + v6;
        }
        SendMessageW(this->m_btnUp.m_hWnd, 0x1Fu, 0, 0);
        SendMessageW(this->m_btnDown.m_hWnd, 0x1Fu, 0, 0);
        m_hWnd = this->m_hWnd;
        Rect = 0;
        GetClientRect(m_hWnd, &Rect);
        InflateRect(&Rect, ~this->m_nBorderSize, ~this->m_nBorderSize);
        GetVisibleTabsNum = this->GetVisibleTabsNum;
        this->m_rectWndArea = (CRect)Rect;
        v11 = GetVisibleTabsNum(this);
        v12 = v11;
        if ( IsMode2003 )
        {
          m_nVisiblePageButtons = this->m_nVisiblePageButtons;
          if ( m_nVisiblePageButtons == -1 || m_nVisiblePageButtons > v11 )
          {
            m_nVisiblePageButtons = v11;
            this->m_nVisiblePageButtons = v11;
          }
          v14 = (Rect.bottom - this->m_nTabsHeight - Rect.top - v4) / (2 * this->m_nTabsHeight);
          this->m_rectCaption = (CRect)Rect;
          if ( v12 < v14 )
            v14 = v12;
          this->m_nMaxVisiblePageButtons = v14;
          if ( v14 < m_nVisiblePageButtons )
            m_nVisiblePageButtons = v14;
          if ( !afxGlobalData.m_bInitialized )
          {
            AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
            afxGlobalData.m_bInitialized = 1;
          }
          top = this->m_rectCaption.top;
          v16 = this->m_nTabsHeight * m_nVisiblePageButtons;
          v17 = Rect;
          v18 = afxGlobalData.m_nTextHeightHorz + top + 2 * CMFCBaseTabCtrl::AFX_TAB_TEXT_MARGIN;
          this->m_rectCaption.top = top + 3;
          this->m_rectSplitter = (CRect)v17;
          v19 = this->m_rectSplitter.bottom - v16;
          this->m_rectCaption.bottom = v18;
          v20 = v19 - v4;
          this->m_rectWndArea.top = v18;
          this->m_rectSplitter.bottom = v20;
          v20 -= 8;
          bottom = this->m_rectSplitter.bottom;
          this->m_rectSplitter.top = v20;
          this->m_rectWndArea.bottom = v20;
        }
        else
        {
          SetRectEmpty(&this->m_rectCaption);
          SetRectEmpty(&this->m_rectSplitter);
          if ( v12 > 1 || !this->IsHideSingleTab(this) )
            InflateRect(&this->m_rectWndArea, 0, -1);
          bottom = Rect.top;
        }
        if ( v12 > 1 || !this->IsHideSingleTab(this) )
        {
          v22 = 0;
          if ( this->m_iTabsNum > 0 )
          {
            v23 = 0;
            do
            {
              if ( v23 < 0 || v23 >= this->m_arTabs.m_nSize )
                goto LABEL_93;
              v24 = (tagRECT *)this->m_arTabs.m_pData[v23];
              v24[2] = Rect;
              ++v24[2].right;
              v24[2].top = bottom;
              v24[2].bottom = bottom + this->m_nTabsHeight;
              v25 = IsMode2003;
              if ( bottom >= Rect.bottom - v49 && IsMode2003 )
              {
                SetRectEmpty(v24 + 2);
                v25 = IsMode2003;
              }
              if ( v24[4].right )
              {
                v1 = 0;
                if ( this->m_bScrollButtons )
                {
                  if ( !v25 )
                  {
                    m_iActiveTab = this->m_iActiveTab;
                    if ( v22 == m_iActiveTab || v22 == m_iActiveTab + 1 )
                    {
                      v27 = v24[2];
                      v28 = v24[2].right - this->m_nTabsHeight;
                      v24[2].right = v28;
                      *(tagRECT *)y = v27;
                      if ( v22 == this->m_iActiveTab )
                        p_m_btnUp = &this->m_btnUp;
                      else
                        p_m_btnUp = &this->m_btnDown;
                      CWnd::SetWindowPos(p_m_btnUp, 0, v28, v27.top, y[2] - v28, y[3] - v27.top, 0x14u);
                    }
                  }
                }
                if ( v22 != this->m_iActiveTab || IsMode2003 )
                {
                  bottom += this->m_nTabsHeight;
                }
                else
                {
                  v30 = v22 + 1;
                  m_iTabsNum = this->m_iTabsNum;
                  this->m_rectWndArea.top = bottom + this->m_nTabsHeight;
                  v32 = 0;
                  v33 = v23 + 1;
                  while ( v30 < m_iTabsNum )
                  {
                    if ( v33 < 0 )
                      goto LABEL_93;
                    if ( v33 >= this->m_arTabs.m_nSize )
                      goto LABEL_93;
                    v34 = this->m_arTabs.m_pData[v33];
                    if ( !v34 )
                      goto LABEL_93;
                    if ( v34[18] )
                      ++v32;
                    ++v30;
                    ++v33;
                  }
                  v35 = Rect.bottom - this->m_nTabsHeight * v32;
                  this->m_rectWndArea.bottom = v35;
                  bottom = v35 + 1;
                }
              }
              else
              {
                SetRectEmpty(v24 + 2);
                v1 = 0;
              }
              ++v22;
              ++v23;
            }
            while ( v22 < this->m_iTabsNum );
            v3 = IsMode2003;
          }
        }
        if ( this->m_bScrollButtons && !v3 && this->m_iActiveTab == v12 - 1 )
        {
          cy = this->m_nTabsHeight;
          right = Rect.right;
          v38 = Rect.bottom - cy;
          this->m_rectWndArea.bottom -= cy;
          CWnd::SetWindowPos(&this->m_btnDown, 0, right - cy + 1, v38 + 1, cy, cy, 0x15u);
        }
        if ( this->m_iTabsNum > 0 )
        {
          v39 = 0;
          while ( v39 >= 0 && v39 < this->m_arTabs.m_nSize )
          {
            v40 = 0;
            v41 = (CObject **)this->m_arTabs.m_pData[v39];
            v48 = (CWnd **)v41;
            if ( *((_DWORD *)v41 + 18) )
            {
              v42 = v41[6];
              if ( v42 && CObject::IsKindOf(v41[6], &CDockablePaneAdapter::classCDockablePaneAdapter) )
              {
                v43 = (CObject *)v42->__vftable[47].GetRuntimeClass(v42);
                v40 = v43;
                if ( v43 && CObject::IsKindOf(v43, &CMFCOutlookBarPane::classCMFCOutlookBarPane) )
                {
                  HIDWORD(v40[1383].__vftable) = this->m_rectWndArea.right - this->m_rectWndArea.left;
                  LODWORD(v40[554].__vftable) = this->m_rectWndArea.bottom - this->m_rectWndArea.top;
                  if ( this->m_bDontAdjustLayout )
                    LODWORD(v40[1388].__vftable) = 1;
                }
                else
                {
                  v40 = 0;
                }
              }
              CWnd::SetWindowPos(
                v48[6],
                0,
                this->m_rectWndArea.left,
                this->m_rectWndArea.top,
                this->m_rectWndArea.right - this->m_rectWndArea.left,
                this->m_rectWndArea.bottom - this->m_rectWndArea.top,
                0x14u);
              if ( v40 )
                LODWORD(v40[1388].__vftable) = 0;
            }
            ++v1;
            ++v39;
            if ( v1 >= this->m_iTabsNum )
              goto LABEL_86;
          }
LABEL_93:
          AfxThrowInvalidArgException();
        }
LABEL_86:
        if ( v12 || v3 )
        {
          RedrawWindow(this->m_hWnd, 0, 0, 0x585u);
          p_m_wndToolBar = &this->m_wndToolBar;
          if ( v3 )
          {
            CWnd::ShowWindow(&this->m_wndToolBar, 4);
            p_m_wndToolBar->SetWindowPos(
              &this->m_wndToolBar,
              0,
              Rect.left,
              Rect.bottom - v49,
              Rect.right - Rect.left,
              v49,
              20u,
              0);
            CMFCOutlookBarTabCtrl::RebuildToolBar(this);
            return;
          }
        }
        else
        {
          CWnd::ShowWindow(this, 0);
          p_m_wndToolBar = &this->m_wndToolBar;
        }
        CWnd::ShowWindow(p_m_wndToolBar, 0);
        RedrawWindow(this->m_btnUp.m_hWnd, 0, 0, 0x105u);
        RedrawWindow(this->m_btnDown.m_hWnd, 0, 0, 0x105u);
        Parent = GetParent(this->m_hWnd);
        v46 = CWnd::FromHandle(Parent);
        RedrawWindow(v46->m_hWnd, 0, 0, 0x105u);
      }
    }
  }
}

```

## disassembly

```asm
0x18009ebf0  test    this, this
0x18009ebf3  jz      locret_18009F2CE
0x18009ebf9  mov     rax, rsp
0x18009ebfc  mov     [rax+10h], rbx
0x18009ec00  mov     [rax+18h], rsi
0x18009ec04  mov     [rax+20h], rdi
0x18009ec08  push    rbp
0x18009ec09  push    r12
0x18009ec0b  push    r13
0x18009ec0d  push    r14
0x18009ec0f  push    r15
0x18009ec11  lea     rbp, [rax-5Fh]
0x18009ec15  sub     rsp, 90h
0x18009ec1c  mov     rax, cs:__security_cookie
0x18009ec23  xor     rax, rsp
0x18009ec26  mov     [rbp+57h+var_30], rax
0x18009ec2a  xor     r12d, r12d
0x18009ec2d  mov     rbx, this
0x18009ec30  cmp     [this+40h], r12
0x18009ec34  jz      loc_18009F2A2
0x18009ec3a  cmp     [this+1D8h], r12d
0x18009ec41  jz      loc_18009F2A2
0x18009ec47  call    ?IsMode2003@CMFCOutlookBarTabCtrl@@QEBAHXZ; CMFCOutlookBarTabCtrl::IsMode2003(void)
0x18009ec4c  mov     dword ptr [rbp+57h+var_60], eax
0x18009ec4f  mov     r13d, eax
0x18009ec52  mov     dword ptr [rbp+57h+var_58], r12d
0x18009ec56  mov     r14d, r12d
0x18009ec59  test    eax, eax
0x18009ec5b  jz      loc_18009ED1E
0x18009ec61  lea     this, [rbx+418h]
0x18009ec68  test    this, this
0x18009ec6b  jz      short loc_18009EC83
0x18009ec6d  cmp     [this+8], r12
0x18009ec71  jz      short loc_18009EC83
0x18009ec73  lea     rdx, [rbx+40Ch]
0x18009ec7a  mov     rax, [rdx]
0x18009ec7d  mov     [rbp+57h+var_58], rax
0x18009ec81  jmp     short loc_18009ECA4
0x18009ec83  mov     rax, [rbx]
0x18009ec86  lea     rdx, [rbp+57h+y]
0x18009ec8a  mov     this, rbx
0x18009ec8d  mov     rax, [rax+480h]
0x18009ec94  call    cs:__guard_dispatch_icall_fptr
0x18009ec9a  mov     rdx, rax
0x18009ec9d  mov     this, [rax]
0x18009eca0  mov     [rbp+57h+var_58], this
0x18009eca4  mov     rax, [rdx]
0x18009eca7  mov     ecx, 10h
0x18009ecac  mov     edi, dword ptr [rbp+57h+var_58+4]
0x18009ecaf  shr     rax, 20h
0x18009ecb3  test    eax, eax
0x18009ecb5  cmovz   edi, ecx
0x18009ecb8  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r12d; AFX_GLOBAL_DATA afxGlobalData ...
0x18009ecbf  jnz     short loc_18009ECD7
0x18009ecc1  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18009ecc8  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18009eccd  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18009ecd7  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bIsRibbonImageScale, r12d; AFX_GLOBAL_DATA afxGlobalData ...
0x18009ecde  movsd   xmm1, cs:__real@3ff0000000000000
0x18009ece6  jz      short loc_18009ECF2
0x18009ece8  movsd   xmm0, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_dblRibbonImageScale; AFX_GLOBAL_DATA afxGlobalData ...
0x18009ecf0  jmp     short loc_18009ECF5
0x18009ecf2  movaps  xmm0, xmm1
0x18009ecf5  ucomisd xmm0, xmm1
0x18009ecf9  mov     eax, 0Ch
0x18009ecfe  jp      short loc_18009ED02
0x18009ed00  jz      short loc_18009ED16
0x18009ed02  mulsd   xmm0, cs:__real@4028000000000000
0x18009ed0a  addsd   xmm0, cs:__real@3fe0000000000000
0x18009ed12  cvttsd2si eax, xmm0
0x18009ed16  lea     r14d, [rax+rdi]
0x18009ed1a  mov     dword ptr [rbp+57h+var_58], r14d
0x18009ed1e  mov     this, [rbx+17F8h]; hWnd
0x18009ed25  xor     r9d, r9d; lParam
0x18009ed28  xor     r8d, r8d; wParam
0x18009ed2b  lea     edi, [r9+1Fh]
0x18009ed2f  mov     edx, edi; Msg
0x18009ed31  call    cs:__imp_SendMessageW
0x18009ed37  mov     this, [rbx+2318h]; hWnd
0x18009ed3e  xor     r9d, r9d; lParam
0x18009ed41  xor     r8d, r8d; wParam
0x18009ed44  mov     edx, edi; Msg
0x18009ed46  call    cs:__imp_SendMessageW
0x18009ed4c  mov     this, [rbx+40h]; hWnd
0x18009ed50  lea     rdx, [rbp+57h+Rect]; lpRect
0x18009ed54  xorps   xmm0, xmm0
0x18009ed57  movdqu  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18009ed5c  call    cs:__imp_GetClientRect
0x18009ed62  mov     edx, [rbx+3C0h]
0x18009ed68  lea     this, [rbp+57h+Rect]; lprc
0x18009ed6c  not     edx; dx
0x18009ed6e  mov     r8d, edx; dy
0x18009ed71  call    cs:__imp_InflateRect
0x18009ed77  mov     rax, [rbx]
0x18009ed7a  lea     rdi, [rbx+3DCh]
0x18009ed81  movups  xmm0, xmmword ptr [rbp+57h+Rect.left]
0x18009ed85  mov     this, rbx
0x18009ed88  mov     rax, [rax+358h]
0x18009ed8f  movdqu  xmmword ptr [rdi], xmm0
0x18009ed93  call    cs:__guard_dispatch_icall_fptr
0x18009ed99  mov     esi, eax
0x18009ed9b  test    r13d, r13d
0x18009ed9e  jz      loc_18009EE76
0x18009eda4  mov     edi, [rbx+3C4h]
0x18009edaa  cmp     edi, 0FFFFFFFFh
0x18009edad  jz      short loc_18009EDB3
0x18009edaf  cmp     edi, eax
0x18009edb1  jle     short loc_18009EDBB
0x18009edb3  mov     edi, esi
0x18009edb5  mov     [rbx+3C4h], esi
0x18009edbb  mov     ecx, [rbx+1D8h]
0x18009edc1  mov     eax, [rbp+57h+Rect.bottom]
0x18009edc4  movups  xmm0, xmmword ptr [rbp+57h+Rect.left]
0x18009edc8  sub     eax, ecx
0x18009edca  add     ecx, ecx
0x18009edcc  sub     eax, [rbp+57h+Rect.top]
0x18009edcf  sub     eax, r14d
0x18009edd2  cdq
0x18009edd3  idiv    ecx
0x18009edd5  movdqu  xmmword ptr [rbx+3ECh], xmm0
0x18009eddd  cmp     esi, eax
0x18009eddf  cmovl   eax, esi
0x18009ede2  cmp     eax, edi
0x18009ede4  mov     [rbx+3C8h], eax
0x18009edea  cmovl   edi, eax
0x18009eded  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r12d; AFX_GLOBAL_DATA afxGlobalData ...
0x18009edf4  jnz     short loc_18009EE0C
0x18009edf6  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18009edfd  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18009ee02  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18009ee0c  mov     eax, cs:?AFX_TAB_TEXT_MARGIN@CMFCBaseTabCtrl@@2HA; int CMFCBaseTabCtrl::AFX_TAB_TEXT_MARGIN
0x18009ee12  mov     edx, [rbx+3F0h]
0x18009ee18  imul    edi, [rbx+1D8h]
0x18009ee1f  movups  xmm0, xmmword ptr [rbp+57h+Rect.left]
0x18009ee23  lea     r8d, [rdx+rax*2]
0x18009ee27  add     r8d, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nTextHeightHorz; AFX_GLOBAL_DATA afxGlobalData ...
0x18009ee2e  lea     eax, [rdx+3]
0x18009ee31  mov     [rbx+3F0h], eax
0x18009ee37  movdqu  xmmword ptr [rbx+3FCh], xmm0
0x18009ee3f  mov     eax, [rbx+408h]
0x18009ee45  sub     eax, edi
0x18009ee47  mov     [rbx+3F8h], r8d
0x18009ee4e  sub     eax, r14d
0x18009ee51  mov     [rbx+3E0h], r8d
0x18009ee58  mov     [rbx+408h], eax
0x18009ee5e  add     eax, 0FFFFFFF8h
0x18009ee61  mov     r15d, [rbx+408h]
0x18009ee68  mov     [rbx+400h], eax
0x18009ee6e  mov     [rbx+3E8h], eax
0x18009ee74  jmp     short loc_18009EEBF
0x18009ee76  lea     this, [rbx+3ECh]; lprc
0x18009ee7d  call    cs:__imp_SetRectEmpty
0x18009ee83  lea     this, [rbx+3FCh]; lprc
0x18009ee8a  call    cs:__imp_SetRectEmpty
0x18009ee90  cmp     esi, 1
0x18009ee93  jg      short loc_18009EEAC
0x18009ee95  mov     rax, [rbx]
0x18009ee98  mov     this, rbx
0x18009ee9b  mov     rax, [rax+550h]
0x18009eea2  call    cs:__guard_dispatch_icall_fptr
0x18009eea8  test    eax, eax
0x18009eeaa  jnz     short loc_18009EEBB
0x18009eeac  or      r8d, 0FFFFFFFFh; dy
0x18009eeb0  xor     edx, edx; dx
0x18009eeb2  mov     this, rdi; lprc
0x18009eeb5  call    cs:__imp_InflateRect
0x18009eebb  mov     r15d, [rbp+57h+Rect.top]
0x18009eebf  cmp     esi, 1
0x18009eec2  jg      short loc_18009EEDF
0x18009eec4  mov     rax, [rbx]
0x18009eec7  mov     this, rbx
0x18009eeca  mov     rax, [rax+550h]
0x18009eed1  call    cs:__guard_dispatch_icall_fptr
0x18009eed7  test    eax, eax
0x18009eed9  jnz     loc_18009F0A9
0x18009eedf  mov     r14d, r12d
0x18009eee2  cmp     [rbx+150h], r12d
0x18009eee9  jle     loc_18009F0A9
0x18009eeef  mov     r13, r12
0x18009eef2  test    r13, r13
0x18009eef5  js      loc_18009F34D
0x18009eefb  cmp     r13, [rbx+110h]
0x18009ef02  jge     loc_18009F34D
0x18009ef08  mov     rax, [rbx+108h]
0x18009ef0f  movups  xmm0, xmmword ptr [rbp+57h+Rect.left]
0x18009ef13  mov     rdi, [rax+r13*8]
0x18009ef17  lea     r12, [rdi+20h]
0x18009ef1b  movdqu  xmmword ptr [r12], xmm0
0x18009ef21  inc     dword ptr [rdi+28h]
0x18009ef24  mov     [rdi+24h], r15d
0x18009ef28  mov     ecx, [rbx+1D8h]
0x18009ef2e  add     ecx, r15d
0x18009ef31  mov     [rdi+2Ch], ecx
0x18009ef34  mov     eax, [rbp+57h+Rect.bottom]
0x18009ef37  sub     eax, dword ptr [rbp+57h+var_58]
0x18009ef3a  cmp     r15d, eax
0x18009ef3d  mov     eax, dword ptr [rbp+57h+var_60]
0x18009ef40  jl      short loc_18009EF52
0x18009ef42  test    eax, eax
0x18009ef44  jz      short loc_18009EF52
0x18009ef46  mov     this, r12; lprc
0x18009ef49  call    cs:__imp_SetRectEmpty
0x18009ef4f  mov     eax, dword ptr [rbp+57h+var_60]
0x18009ef52  cmp     dword ptr [rdi+48h], 0
0x18009ef56  jnz     short loc_18009EF69
0x18009ef58  mov     this, r12; lprc
0x18009ef5b  call    cs:__imp_SetRectEmpty
0x18009ef61  xor     r12d, r12d
0x18009ef64  jmp     loc_18009F092
0x18009ef69  xor     r12d, r12d
0x18009ef6c  cmp     [rbx+3D4h], r12d
0x18009ef73  jz      loc_18009F004
0x18009ef79  test    eax, eax
0x18009ef7b  jnz     loc_18009F004
0x18009ef81  mov     eax, [rbx+154h]
0x18009ef87  cmp     r14d, eax
0x18009ef8a  jz      short loc_18009EF93
0x18009ef8c  inc     eax
0x18009ef8e  cmp     r14d, eax
0x18009ef91  jnz     short loc_18009F004
0x18009ef93  mov     r8d, [rdi+28h]
0x18009ef97  movups  xmm0, xmmword ptr [rdi+20h]
0x18009ef9b  sub     r8d, [rbx+1D8h]; x
0x18009efa2  mov     [rdi+28h], r8d
0x18009efa6  movdqu  xmmword ptr [rbp+57h+y], xmm0
0x18009efab  mov     r9d, [rbp+57h+y+4]; y
0x18009efaf  mov     [rsp+0B0h+nFlags], 14h; nFlags
0x18009efb7  cmp     r14d, [rbx+154h]
0x18009efbe  jnz     short loc_18009EFE2
0x18009efc0  mov     rdx, qword ptr [rbp+57h+y+8]
0x18009efc4  lea     this, [rbx+17B8h]
0x18009efcb  mov     rax, rdx
0x18009efce  shr     rax, 20h
0x18009efd2  sub     eax, r9d
0x18009efd5  sub     edx, r8d
0x18009efd8  mov     [rsp+0B0h+cy], eax
0x18009efdc  mov     [rsp+0B0h+var_90], edx
0x18009efe0  jmp     short loc_18009EFFD
0x18009efe2  mov     edx, [rbp+57h+y+0Ch]
0x18009efe5  lea     this, [rbx+22D8h]; this
0x18009efec  mov     eax, [rbp+57h+y+8]
0x18009efef  sub     edx, r9d
0x18009eff2  sub     eax, r8d
0x18009eff5  mov     [rsp+0B0h+cy], edx; cy
0x18009eff9  mov     [rsp+0B0h+var_90], eax; cx
0x18009effd  xor     edx, edx; pWndInsertAfter
0x18009efff  call    ?SetWindowPos@CWnd@@QEAAHPEBV1@HHHHI@Z; CWnd::SetWindowPos(CWnd const *,int,int,int,int,uint)
0x18009f004  cmp     r14d, [rbx+154h]
0x18009f00b  jnz     short loc_18009F08B
0x18009f00d  cmp     dword ptr [rbp+57h+var_60], r12d
0x18009f011  jnz     short loc_18009F08B
0x18009f013  mov     ecx, [rbx+1D8h]
0x18009f019  lea     r8d, [r14+1]
0x18009f01d  mov     r10d, [rbx+150h]
0x18009f024  add     ecx, r15d
0x18009f027  mov     [rbx+3E0h], ecx
0x18009f02d  mov     edx, r12d
0x18009f030  lea     this, [r13+1]
0x18009f034  jmp     short loc_18009F06E
0x18009f036  test    this, this
0x18009f039  js      loc_18009F34D
0x18009f03f  cmp     this, [rbx+110h]
0x18009f046  jge     loc_18009F34D
0x18009f04c  mov     rax, [rbx+108h]
0x18009f053  mov     r9, [rax+this*8]
0x18009f057  test    r9, r9
0x18009f05a  jz      loc_18009F34D
0x18009f060  cmp     [r9+48h], r12d
0x18009f064  jz      short loc_18009F068
0x18009f066  inc     edx
0x18009f068  inc     r8d
0x18009f06b  inc     this
0x18009f06e  cmp     r8d, r10d
0x18009f071  jl      short loc_18009F036
0x18009f073  imul    edx, [rbx+1D8h]
0x18009f07a  mov     eax, [rbp+57h+Rect.bottom]
0x18009f07d  sub     eax, edx
0x18009f07f  mov     [rbx+3E8h], eax
0x18009f085  lea     r15d, [rax+1]
0x18009f089  jmp     short loc_18009F092
0x18009f08b  add     r15d, [rbx+1D8h]
0x18009f092  inc     r14d
0x18009f095  inc     r13
0x18009f098  cmp     r14d, [rbx+150h]
0x18009f09f  jl      loc_18009EEF2
0x18009f0a5  mov     r13d, dword ptr [rbp+57h+var_60]
0x18009f0a9  cmp     [rbx+3D4h], r12d
0x18009f0b0  jz      short loc_18009F100
0x18009f0b2  test    r13d, r13d
0x18009f0b5  jnz     short loc_18009F100
0x18009f0b7  lea     eax, [rsi-1]
0x18009f0ba  cmp     [rbx+154h], eax
0x18009f0c0  jnz     short loc_18009F100
0x18009f0c2  mov     eax, [rbx+1D8h]
0x18009f0c8  lea     this, [rbx+22D8h]; this
0x18009f0cf  mov     r9d, [rbp+57h+Rect.bottom]
0x18009f0d3  xor     edx, edx; pWndInsertAfter
0x18009f0d5  mov     r8d, [rbp+57h+Rect.right]
0x18009f0d9  sub     r9d, eax
0x18009f0dc  sub     [rbx+3E8h], eax
  ... truncated ...
```
