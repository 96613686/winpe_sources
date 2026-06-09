# CMFCToolBar::OnLButtonDown(uint,CPoint)

- ea: `0x180156dc0`
- end: `0x1801576a3`
- name: `?OnLButtonDown@CMFCToolBar@@IEAAXIVCPoint@@@Z`
- size: `2275`
- prototype: `void __fastcall(CMFCToolBar *this, unsigned int nFlags, CPoint point)`
- caller_count: `4`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180027f50`
- `0x18008f2c0`
- `0x1800c1d10`
- `0x18015cb60`

## callees

- `0x18006cab0`
- `0x1800a2780`
- `0x180155920`
- `0x1801567a0`
- `0x1801567f0`
- `0x180156dc0`
- `0x180158810`
- `0x1801591a0`
- `0x180162690`
- `0x180231d70`
- `0x18023f820`
- `0x18025e0a0`
- `0x18025e0e0`
- `0x180265960`
- `0x180296d00`
- `0x1802b67c0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!labs` at `0x1801570e0`
- `api-ms-win-crt-utility-l1-1-0!labs` at `0x1801570e0`
- `USER32!ScreenToClient` at `0x180157289`
- `USER32!ScreenToClient` at `0x180157289`
- `USER32!GetCursorPos` at `0x18015727b`
- `USER32!GetCursorPos` at `0x18015727b`
- `USER32!InvalidateRect` at `0x180157460`
- `USER32!InvalidateRect` at `0x180157460`
- `USER32!IsWindow` at `0x18015723d`
- `USER32!IsWindow` at `0x18015723d`
- `USER32!GetAsyncKeyState` at `0x180156fa8`
- `USER32!GetAsyncKeyState` at `0x180156fa8`
- `USER32!SetCursor` at `0x180156f2a`
- `USER32!SetCursor` at `0x18015717b`
- `USER32!SetCursor` at `0x180156f2a`
- `USER32!SetCursor` at `0x18015717b`
- `USER32!NotifyWinEvent` at `0x1801575f9`
- `USER32!NotifyWinEvent` at `0x18015760e`
- `USER32!NotifyWinEvent` at `0x1801575f9`
- `USER32!NotifyWinEvent` at `0x18015760e`
- `USER32!SetCapture` at `0x180157143`
- `USER32!SetCapture` at `0x18015762e`
- `USER32!SetCapture` at `0x180157143`
- `USER32!SetCapture` at `0x18015762e`
- `USER32!GetParent` at `0x180156e4f`
- `USER32!GetParent` at `0x180156e79`
- `USER32!GetParent` at `0x180157361`
- `USER32!GetParent` at `0x18015737e`
- `USER32!GetParent` at `0x1801573d0`
- `USER32!GetParent` at `0x1801573f9`
- `USER32!GetParent` at `0x18015740b`
- `USER32!GetParent` at `0x180156e4f`
- `USER32!GetParent` at `0x180156e79`
- `USER32!GetParent` at `0x180157361`
- `USER32!GetParent` at `0x18015737e`
- `USER32!GetParent` at `0x1801573d0`
- `USER32!GetParent` at `0x1801573f9`
- `USER32!GetParent` at `0x18015740b`
- `USER32!InflateRect` at `0x180157139`
- `USER32!InflateRect` at `0x180157139`
- `USER32!PtInRect` at `0x1801572a4`
- `USER32!PtInRect` at `0x1801572a4`
- `USER32!UpdateWindow` at `0x180156ece`
- `USER32!UpdateWindow` at `0x1801570b6`
- `USER32!UpdateWindow` at `0x18015750b`
- `USER32!UpdateWindow` at `0x1801575af`
- `USER32!UpdateWindow` at `0x180156ece`
- `USER32!UpdateWindow` at `0x1801570b6`
- `USER32!UpdateWindow` at `0x18015750b`
- `USER32!UpdateWindow` at `0x1801575af`
- `USER32!RedrawWindow` at `0x180157341`
- `USER32!RedrawWindow` at `0x180157398`
- `USER32!RedrawWindow` at `0x1801573c6`
- `USER32!RedrawWindow` at `0x180157670`
- `USER32!RedrawWindow` at `0x180157341`
- `USER32!RedrawWindow` at `0x180157398`
- `USER32!RedrawWindow` at `0x1801573c6`
- `USER32!RedrawWindow` at `0x180157670`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMFCToolBar::OnLButtonDown(CMFCToolBar *this, unsigned int nFlags, CPoint point)
{
  int v6; // esi
  CMFCToolBar *v7; // rcx
  int m_iSelected; // edx
  HWND Parent; // rax
  CWnd *v10; // rax
  HWND v11; // rax
  CWnd *v12; // rax
  int v13; // edx
  CMFCToolBarButton *Button; // r14
  int v15; // r12d
  CMFCToolBarButton *v16; // rax
  CMFCToolBarButton *m_pDragButton; // rcx
  HWND v18; // rax
  HWND__ *m_hWnd; // r14
  unsigned int v20; // ebx
  CMFCToolBarButton *v21; // rdx
  int (__fastcall *RemoveButton)(CMFCToolBar *, int); // rbx
  unsigned int v23; // eax
  HWND v24; // rax
  CWnd *v25; // rax
  HWND v26; // rax
  CWnd *v27; // rax
  HWND v28; // rax
  CWnd *v29; // rax
  HWND v30; // rax
  CWnd *v31; // rax
  HWND v32; // rax
  CWnd *v33; // rax
  CWnd *v34; // rbx
  CMFCToolBarButton *v35; // rdx
  int v36; // r12d
  int v37; // ebx
  CObList::CNode *i; // rax
  LONG ChildIdByButtonIndex; // eax
  LONG v40; // ebx
  HWND v41; // rax
  CPoint ptDrop; // [rsp+20h] [rbp-69h] BYREF
  __int64 v43; // [rsp+28h] [rbp-61h]
  COleDataSource srcItem; // [rsp+30h] [rbp-59h] BYREF
  CRect rect; // [rsp+90h] [rbp+7h] BYREF

  v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD))this->HitTest)(this, point);
  v7 = CMFCToolBar::m_pSelToolbar;
  if ( CMFCToolBar::m_pSelToolbar == this )
    goto LABEL_5;
  if ( CMFCToolBar::m_bCustomizeMode )
  {
    CMFCToolBar::m_pSelToolbar = this;
    if ( v7 )
    {
      m_iSelected = v7->m_iSelected;
      v7->m_iSelected = -1;
      CMFCToolBar::InvalidateButton(v7, m_iSelected);
    }
LABEL_5:
    if ( CMFCToolBar::m_bCustomizeMode )
      goto LABEL_9;
  }
  Parent = GetParent(this->m_hWnd);
  v10 = CWnd::FromHandle(Parent);
  if ( v10 && CObject::IsKindOf(v10, &CPane::classCPane) )
  {
    v11 = GetParent(this->m_hWnd);
    v12 = CWnd::FromHandle(v11);
    CWnd::SetFocus(v12);
  }
LABEL_9:
  if ( v6 < 0 )
  {
    this->m_iButtonCapture = -1;
    if ( CMFCToolBar::m_bCustomizeMode && !this->m_bLocked )
    {
      v13 = this->m_iSelected;
      this->m_iSelected = -1;
      if ( v13 != -1 )
      {
        CMFCToolBar::InvalidateButton(this, v13);
        UpdateWindow(this->m_hWnd);
      }
      this->OnChangeHot(this, -1);
    }
    if ( this->CanFloat(this) )
    {
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      SetCursor(afxGlobalData.m_hcurSizeAll);
    }
    CPane::OnLButtonDown(this, nFlags, point);
    return;
  }
  Button = CMFCToolBar::GetButton(this, v6);
  if ( !Button )
    return;
  this->AccNotifyObjectFocusEvent(this, v6);
  CMFCToolBar::m_bAltCustomizeMode = 0;
  if ( CMFCToolBar::m_bAltCustomization && this->AllowAltCustomization(this) )
  {
    if ( CMFCToolBar::m_bCustomizeMode )
      goto LABEL_28;
    if ( GetAsyncKeyState(18) < 0 )
    {
      CMFCToolBar::m_bAltCustomizeMode = 1;
      this->m_iSelected = v6;
      this->m_iHighlighted = -1;
      CMFCToolBar::m_pSelToolbar = this;
    }
  }
  if ( !CMFCToolBar::m_bCustomizeMode && !CMFCToolBar::m_bAltCustomizeMode )
    goto LABEL_72;
LABEL_28:
  if ( this->m_bLocked || this->m_bDisableCustomize )
  {
LABEL_72:
    this->m_iButtonCapture = v6;
    CMFCToolBar::UpdateButton(this, v6);
    if ( (Button->m_nStyle & 0x40000) != 0
      && !CObject::IsKindOf(Button, &CMFCDropDownToolbarButton::classCMFCDropDownToolbarButton) )
    {
      this->m_iButtonCapture = -1;
      return;
    }
    Button->m_nStyle |= 0x20000u;
    CMFCToolBar::InvalidateButton(this, v6);
    UpdateWindow(this->m_hWnd);
    this->ShowCommandMessageString(this, Button->m_nID);
    v36 = Button->IsDroppedDown(Button);
    if ( Button->OnClick(Button, this, 0) )
    {
      v37 = 0;
      for ( i = this->m_Buttons.m_pNodeHead; ; i = i->pNext )
      {
        if ( !i )
        {
          v37 = 1;
          goto LABEL_81;
        }
        if ( i->data == Button )
          break;
      }
      Button->m_nStyle &= ~0x20000u;
LABEL_81:
      this->m_iButtonCapture = -1;
      this->m_iHighlighted = -1;
      this->OnChangeHot(this, -1);
      CMFCToolBar::InvalidateButton(this, v6);
      UpdateWindow(this->m_hWnd);
      if ( !v37 && v36 != Button->IsDroppedDown(Button) )
      {
        ChildIdByButtonIndex = CMFCToolBar::AccGetChildIdByButtonIndex(this, v6);
        v40 = ChildIdByButtonIndex;
        if ( ChildIdByButtonIndex > 0 )
        {
          NotifyWinEvent(0x800Au, this->m_hWnd, -4, ChildIdByButtonIndex);
          NotifyWinEvent(0x8005u, this->m_hWnd, -4, v40);
        }
      }
    }
    else
    {
      v41 = SetCapture(this->m_hWnd);
      this->m_pWndLastCapture = CWnd::FromHandle(v41);
    }
    goto LABEL_87;
  }
  v15 = this->m_iSelected;
  this->m_iSelected = v6;
  rect = 0;
  this->GetItemRect(this, v6, &rect);
  if ( v15 != -1 )
    CMFCToolBar::InvalidateButton(this, v15);
  v16 = CMFCToolBar::GetButton(this, this->m_iSelected);
  this->m_pDragButton = v16;
  if ( !v16 )
    AfxThrowInvalidArgException();
  this->m_bIsDragCopy = nFlags & 8;
  if ( !v16->IsEditable(v16) )
  {
    this->m_iSelected = -1;
    this->m_pDragButton = 0;
    if ( v15 != -1 )
      CMFCToolBar::InvalidateButton(this, v15);
    return;
  }
  CMFCToolBar::InvalidateButton(this, v6);
  UpdateWindow(this->m_hWnd);
  if ( this->m_pDragButton->CanBeStretched(this->m_pDragButton)
    && labs(point.x - rect.right) <= 6
    && !CMFCToolBar::m_bAltCustomizeMode )
  {
    this->m_bStretchButton = 1;
    m_pDragButton = this->m_pDragButton;
    this->m_rectTrack = m_pDragButton->m_rect;
    if ( m_pDragButton->GetHwnd(m_pDragButton) )
      InflateRect(&this->m_rectTrack, 2, 2);
    v18 = SetCapture(this->m_hWnd);
    this->m_pWndLastCapture = CWnd::FromHandle(v18);
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    SetCursor(afxGlobalData.m_hcurStretch);
    goto LABEL_87;
  }
  if ( !this->m_pDragButton->CanBeStored(this->m_pDragButton) || !this->m_pDragButton->OnBeforeDrag(this->m_pDragButton) )
  {
    this->m_pDragButton = 0;
LABEL_87:
    if ( CMFCToolBar::m_bAltCustomizeMode )
    {
      CMFCToolBar::m_bAltCustomizeMode = 0;
      CMFCToolBar::m_pSelToolbar = 0;
      CMFCToolBar::SetCustomizeMode(0);
      RedrawWindow(this->m_hWnd, 0, 0, 0x505u);
    }
    return;
  }
  COleDataSource::COleDataSource(&srcItem);
  this->m_pDragButton->PrepareDrag(this->m_pDragButton, &srcItem);
  this->ShowCommandMessageString(this, Button->m_nID);
  CMFCToolBar::m_DropSource.m_bDragStarted = 0;
  this->m_ptStartDrag = point;
  m_hWnd = this->m_hWnd;
  if ( CMFCToolBar::m_bAltCustomizeMode )
    CMFCToolBar::m_bCustomizeMode = 1;
  v20 = COleDataSource::DoDragDrop(&srcItem, 3u, &rect, &CMFCToolBar::m_DropSource);
  if ( IsWindow(m_hWnd) )
  {
    ptDrop = 0;
    GetCursorPos(&ptDrop);
    ScreenToClient(this->m_hWnd, &ptDrop);
    if ( !CMFCToolBar::m_DropSource.m_bDragStarted || PtInRect(&rect, ptDrop.tagPOINT) )
    {
      this->m_iHighlighted = v6;
      this->OnChangeHot(this, v6);
    }
    else if ( v20 == 1
           || (v21 = this->m_pDragButton) == 0
           || CMFCToolBar::m_DropSource.m_bEscapePressed
           || !this->OnBeforeRemoveButton(this, v21, v20) )
    {
      v35 = this->m_pDragButton;
      if ( v35 )
        InvalidateRect(this->m_hWnd, &v35->m_rect, 1);
    }
    else
    {
      RemoveButton = this->RemoveButton;
      v23 = CMFCToolBar::ButtonToIndex(this, this->m_pDragButton);
      RemoveButton(this, v23);
      this->AdjustLocations(this);
      RedrawWindow(this->m_hWnd, 0, 0, 0x505u);
      this->AdjustSizeImmediate(this, 1);
      v24 = GetParent(this->m_hWnd);
      v25 = CWnd::FromHandle(v24);
      if ( v25 && v25->m_hWnd )
      {
        v26 = GetParent(this->m_hWnd);
        v27 = CWnd::FromHandle(v26);
        RedrawWindow(v27->m_hWnd, 0, 0, 0x505u);
      }
      if ( !CMFCToolBar::m_bAltCustomizeMode )
      {
        this->AdjustLayout(this);
        RedrawWindow(this->m_hWnd, 0, 0, 0x505u);
      }
      v28 = GetParent(this->m_hWnd);
      v29 = CWnd::FromHandle(v28);
      if ( CObject::IsKindOf(v29, &CMFCTabCtrl::classCMFCTabCtrl) )
      {
        v30 = GetParent(this->m_hWnd);
        v31 = CWnd::FromHandle(v30);
        v32 = GetParent(v31->m_hWnd);
        v33 = CWnd::FromHandle(v32);
        v34 = v33;
        if ( v33 )
        {
          if ( CObject::IsKindOf(v33, &CMFCToolBar::classCMFCToolBar) )
            ((void (__fastcall *)(CWnd *))v34->__vftable[1].get_accName)(v34);
        }
      }
    }
    this->m_pDragButton = 0;
    v43 = -1;
    this->m_ptStartDrag = (CPoint)-1LL;
    COleDataSource::~COleDataSource(&srcItem);
    goto LABEL_87;
  }
  if ( CMFCToolBar::m_bAltCustomizeMode )
  {
    CMFCToolBar::m_bCustomizeMode = 0;
    CMFCToolBar::m_bAltCustomizeMode = 0;
    CMFCToolBar::m_pSelToolbar = 0;
  }
  COleDataSource::~COleDataSource(&srcItem);
}

```

## disassembly

```asm
0x180156dc0  mov     [rsp-8+arg_10], rbx
0x180156dc5  push    rbp
0x180156dc6  push    rsi
0x180156dc7  push    rdi
0x180156dc8  push    r12
0x180156dca  push    r13
0x180156dcc  push    r14
0x180156dce  push    r15
0x180156dd0  lea     rbp, [rsp-27h]
0x180156dd5  sub     rsp, 0B0h
0x180156ddc  mov     rax, cs:__security_cookie
0x180156de3  xor     rax, rsp
0x180156de6  mov     [rbp+57h+var_40], rax
0x180156dea  mov     rbx, point
0x180156ded  mov     r13d, nFlags
0x180156df0  mov     rdi, this
0x180156df3  mov     rax, [this]
0x180156df6  mov     rdx, point
0x180156df9  mov     rax, [rax+730h]
0x180156e00  call    cs:__guard_dispatch_icall_fptr
0x180156e06  mov     esi, eax
0x180156e08  or      r14d, 0FFFFFFFFh
0x180156e0c  xor     r12d, r12d
0x180156e0f  mov     this, cs:?m_pSelToolbar@CMFCToolBar@@1PEAV1@EA; this
0x180156e16  cmp     this, rdi
0x180156e19  jz      short loc_180156E42
0x180156e1b  cmp     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, r12d; int CMFCToolBar::m_bCustomizeMode
0x180156e22  jz      short loc_180156E4B
0x180156e24  mov     cs:?m_pSelToolbar@CMFCToolBar@@1PEAV1@EA, rdi; CMFCToolBar * CMFCToolBar::m_pSelToolbar
0x180156e2b  test    this, this
0x180156e2e  jz      short loc_180156E42
0x180156e30  mov     nFlags, [this+113Ch]; nIndex
0x180156e36  mov     [this+113Ch], r14d
0x180156e3d  call    ?InvalidateButton@CMFCToolBar@@QEAAPEAVCMFCToolBarButton@@H@Z; CMFCToolBar::InvalidateButton(int)
0x180156e42  cmp     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, r12d; int CMFCToolBar::m_bCustomizeMode
0x180156e49  jnz     short loc_180156E8F
0x180156e4b  mov     this, [rdi+40h]; hWnd
0x180156e4f  call    cs:__imp_GetParent
0x180156e55  mov     this, rax; hWnd
0x180156e58  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x180156e5d  test    rax, rax
0x180156e60  jz      short loc_180156E8F
0x180156e62  lea     rdx, ?classCPane@CPane@@2UCRuntimeClass@@B; pClass
0x180156e69  mov     this, rax; this
0x180156e6c  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180156e71  test    eax, eax
0x180156e73  jz      short loc_180156E8F
0x180156e75  mov     this, [rdi+40h]; hWnd
0x180156e79  call    cs:__imp_GetParent
0x180156e7f  mov     this, rax; hWnd
0x180156e82  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x180156e87  mov     this, rax; this
0x180156e8a  call    ?SetFocus@CWnd@@QEAAPEAV1@XZ; CWnd::SetFocus(void)
0x180156e8f  test    esi, esi
0x180156e91  jns     loc_180156F43
0x180156e97  mov     [rdi+1134h], r14d
0x180156e9e  cmp     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, r12d; int CMFCToolBar::m_bCustomizeMode
0x180156ea5  jz      short loc_180156EEA
0x180156ea7  cmp     [rdi+10B8h], r12d
0x180156eae  jnz     short loc_180156EEA
0x180156eb0  mov     nFlags, [rdi+113Ch]; nIndex
0x180156eb6  mov     [rdi+113Ch], r14d
0x180156ebd  cmp     nFlags, r14d
0x180156ec0  jz      short loc_180156ED4
0x180156ec2  mov     this, rdi; this
0x180156ec5  call    ?InvalidateButton@CMFCToolBar@@QEAAPEAVCMFCToolBarButton@@H@Z; CMFCToolBar::InvalidateButton(int)
0x180156eca  mov     this, [rdi+40h]; hWnd
0x180156ece  call    cs:__imp_UpdateWindow
0x180156ed4  mov     rax, [rdi]
0x180156ed7  mov     nFlags, r14d
0x180156eda  mov     this, rdi
0x180156edd  mov     rax, [rax+770h]
0x180156ee4  call    cs:__guard_dispatch_icall_fptr
0x180156eea  mov     rax, [rdi]
0x180156eed  mov     this, rdi
0x180156ef0  mov     rax, [rax+3A8h]
0x180156ef7  call    cs:__guard_dispatch_icall_fptr
0x180156efd  test    eax, eax
0x180156eff  jz      short loc_180156F30
0x180156f01  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r12d; AFX_GLOBAL_DATA afxGlobalData ...
0x180156f08  jnz     short loc_180156F23
0x180156f0a  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180156f11  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180156f16  mov     r15d, 1
0x180156f1c  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r15d; AFX_GLOBAL_DATA afxGlobalData ...
0x180156f23  mov     this, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_hcurSizeAll; hCursor
0x180156f2a  call    cs:__imp_SetCursor
0x180156f30  mov     point, rbx; point
0x180156f33  mov     nFlags, r13d; nFlags
0x180156f36  mov     this, rdi; this
0x180156f39  call    ?OnLButtonDown@CPane@@IEAAXIVCPoint@@@Z; CPane::OnLButtonDown(uint,CPoint)
0x180156f3e  jmp     loc_180157676
0x180156f43  mov     nFlags, esi; nIndex
0x180156f45  mov     this, rdi; this
0x180156f48  call    ?GetButton@CMFCToolBar@@QEBAPEAVCMFCToolBarButton@@H@Z; CMFCToolBar::GetButton(int)
0x180156f4d  mov     r14, rax
0x180156f50  test    rax, rax
0x180156f53  jz      loc_180157676
0x180156f59  mov     this, [rdi]
0x180156f5c  mov     rax, [this+4C8h]
0x180156f63  mov     nFlags, esi
0x180156f65  mov     this, rdi
0x180156f68  call    cs:__guard_dispatch_icall_fptr
0x180156f6e  mov     cs:?m_bAltCustomizeMode@CMFCToolBar@@1HA, r12d; int CMFCToolBar::m_bAltCustomizeMode
0x180156f75  mov     r15d, 1
0x180156f7b  cmp     cs:?m_bAltCustomization@CMFCToolBar@@1HA, r12d; int CMFCToolBar::m_bAltCustomization
0x180156f82  jz      short loc_180156FCE
0x180156f84  mov     rax, [rdi]
0x180156f87  mov     this, rdi
0x180156f8a  mov     rax, [rax+850h]
0x180156f91  call    cs:__guard_dispatch_icall_fptr
0x180156f97  test    eax, eax
0x180156f99  jz      short loc_180156FCE
0x180156f9b  cmp     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, r12d; int CMFCToolBar::m_bCustomizeMode
0x180156fa2  jnz     short loc_180156FE4
0x180156fa4  lea     ecx, [r15+11h]; vKey
0x180156fa8  call    cs:__imp_GetAsyncKeyState
0x180156fae  test    ax, ax
0x180156fb1  jns     short loc_180156FCE
0x180156fb3  mov     cs:?m_bAltCustomizeMode@CMFCToolBar@@1HA, r15d; int CMFCToolBar::m_bAltCustomizeMode
0x180156fba  mov     [rdi+113Ch], esi
0x180156fc0  or      dword ptr [rdi+1138h], 0FFFFFFFFh
0x180156fc7  mov     cs:?m_pSelToolbar@CMFCToolBar@@1PEAV1@EA, rdi; CMFCToolBar * CMFCToolBar::m_pSelToolbar
0x180156fce  cmp     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, r12d; int CMFCToolBar::m_bCustomizeMode
0x180156fd5  jnz     short loc_180156FE4
0x180156fd7  cmp     cs:?m_bAltCustomizeMode@CMFCToolBar@@1HA, r12d; int CMFCToolBar::m_bAltCustomizeMode
0x180156fde  jz      loc_1801574B8
0x180156fe4  cmp     [rdi+10B8h], r12d
0x180156feb  jnz     loc_1801574B8
0x180156ff1  cmp     [rdi+10F8h], r12d
0x180156ff8  jnz     loc_1801574B8
0x180156ffe  mov     r12d, [rdi+113Ch]
0x180157005  mov     [rdi+113Ch], esi
0x18015700b  xorps   xmm0, xmm0
0x18015700e  movdqu  xmmword ptr [rbp+57h+rect.left], xmm0
0x180157013  mov     rax, [rdi]
0x180157016  lea     point, [rbp+57h+rect]
0x18015701a  mov     nFlags, esi
0x18015701c  mov     this, rdi
0x18015701f  mov     rax, [rax+6E8h]
0x180157026  call    cs:__guard_dispatch_icall_fptr
0x18015702c  cmp     r12d, 0FFFFFFFFh
0x180157030  jz      short loc_18015703D
0x180157032  mov     nFlags, r12d; nIndex
0x180157035  mov     this, rdi; this
0x180157038  call    ?InvalidateButton@CMFCToolBar@@QEAAPEAVCMFCToolBarButton@@H@Z; CMFCToolBar::InvalidateButton(int)
0x18015703d  mov     nFlags, [rdi+113Ch]; nIndex
0x180157043  mov     this, rdi; this
0x180157046  call    ?GetButton@CMFCToolBar@@QEBAPEAVCMFCToolBarButton@@H@Z; CMFCToolBar::GetButton(int)
0x18015704b  mov     this, rax
0x18015704e  mov     [rdi+12F0h], rax
0x180157055  test    rax, rax
0x180157058  jz      loc_18015769D
0x18015705e  and     r13d, 8
0x180157062  mov     [rdi+10E0h], r13d
0x180157069  mov     rax, [rax]
0x18015706c  mov     rax, [rax+0D0h]
0x180157073  call    cs:__guard_dispatch_icall_fptr
0x180157079  xor     r13d, r13d
0x18015707c  test    eax, eax
0x18015707e  jnz     short loc_1801570A8
0x180157080  or      dword ptr [rdi+113Ch], 0FFFFFFFFh
0x180157087  mov     [rdi+12F0h], r13
0x18015708e  cmp     r12d, 0FFFFFFFFh
0x180157092  jz      loc_180157676
0x180157098  mov     nFlags, r12d; nIndex
0x18015709b  mov     this, rdi; this
0x18015709e  call    ?InvalidateButton@CMFCToolBar@@QEAAPEAVCMFCToolBarButton@@H@Z; CMFCToolBar::InvalidateButton(int)
0x1801570a3  jmp     loc_180157676
0x1801570a8  mov     nFlags, esi; nIndex
0x1801570aa  mov     this, rdi; this
0x1801570ad  call    ?InvalidateButton@CMFCToolBar@@QEAAPEAVCMFCToolBarButton@@H@Z; CMFCToolBar::InvalidateButton(int)
0x1801570b2  mov     this, [rdi+40h]; hWnd
0x1801570b6  call    cs:__imp_UpdateWindow
0x1801570bc  mov     this, [rdi+12F0h]
0x1801570c3  mov     rax, [this]
0x1801570c6  mov     rax, [rax+88h]
0x1801570cd  call    cs:__guard_dispatch_icall_fptr
0x1801570d3  test    eax, eax
0x1801570d5  jz      loc_180157186
0x1801570db  mov     ecx, ebx
0x1801570dd  sub     ecx, [rbp+57h+rect.right]; Number
0x1801570e0  call    cs:__imp_labs
0x1801570e6  cmp     eax, 6
0x1801570e9  jg      loc_180157186
0x1801570ef  cmp     cs:?m_bAltCustomizeMode@CMFCToolBar@@1HA, r13d; int CMFCToolBar::m_bAltCustomizeMode
0x1801570f6  jnz     loc_180157186
0x1801570fc  mov     [rdi+10E4h], r15d
0x180157103  mov     this, [rdi+12F0h]
0x18015710a  lea     rbx, [rdi+12B0h]
0x180157111  movups  xmm0, xmmword ptr [this+68h]
0x180157115  movdqu  xmmword ptr [rbx], xmm0
0x180157119  mov     rax, [this]
0x18015711c  mov     rax, [rax+80h]
0x180157123  call    cs:__guard_dispatch_icall_fptr
0x180157129  test    rax, rax
0x18015712c  jz      short loc_18015713F
0x18015712e  mov     nFlags, 2; dx
0x180157133  mov     r8d, nFlags; dy
0x180157136  mov     this, rbx; lprc
0x180157139  call    cs:__imp_InflateRect
0x18015713f  mov     this, [rdi+40h]; hWnd
0x180157143  call    cs:__imp_SetCapture
0x180157149  mov     this, rax; hWnd
0x18015714c  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x180157151  mov     [rdi+12E0h], rax
0x180157158  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r13d; AFX_GLOBAL_DATA afxGlobalData ...
0x18015715f  jnz     short loc_180157174
0x180157161  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180157168  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18015716d  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r15d; AFX_GLOBAL_DATA afxGlobalData ...
0x180157174  mov     this, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_hcurStretch; hCursor
0x18015717b  call    cs:__imp_SetCursor
0x180157181  jmp     loc_180157643
0x180157186  mov     this, [rdi+12F0h]
0x18015718d  mov     rax, [this]
0x180157190  mov     rax, [rax+0B0h]
0x180157197  call    cs:__guard_dispatch_icall_fptr
0x18015719d  test    eax, eax
0x18015719f  jz      loc_1801574AC
0x1801571a5  mov     this, [rdi+12F0h]
0x1801571ac  mov     rax, [this]
0x1801571af  mov     rax, [rax+0F8h]
0x1801571b6  call    cs:__guard_dispatch_icall_fptr
0x1801571bc  test    eax, eax
0x1801571be  jz      loc_1801574AC
0x1801571c4  lea     this, [rbp+57h+srcItem]; this
0x1801571c8  call    ??0COleDataSource@@QEAA@XZ; COleDataSource::COleDataSource(void)
0x1801571cd  nop
0x1801571ce  mov     this, [rdi+12F0h]
0x1801571d5  mov     rax, [this]
0x1801571d8  lea     rdx, [rbp+57h+srcItem]
0x1801571dc  mov     rax, [rax+28h]
0x1801571e0  call    cs:__guard_dispatch_icall_fptr
0x1801571e6  mov     rax, [rdi]
0x1801571e9  mov     nFlags, [r14+24h]
0x1801571ed  mov     this, rdi
0x1801571f0  mov     rax, [rax+840h]
0x1801571f7  call    cs:__guard_dispatch_icall_fptr
0x1801571fd  mov     cs:?m_DropSource@CMFCToolBar@@1VCMFCToolBarDropSource@@A.m_bDragStarted, r13d; CMFCToolBarDropSource CMFCToolBar::m_DropSource ...
0x180157204  mov     [rdi+12D0h], rbx
0x18015720b  mov     r14, [rdi+40h]
0x18015720f  cmp     cs:?m_bAltCustomizeMode@CMFCToolBar@@1HA, r13d; int CMFCToolBar::m_bAltCustomizeMode
0x180157216  jz      short loc_18015721F
0x180157218  mov     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, r15d; int CMFCToolBar::m_bCustomizeMode
0x18015721f  lea     r9, ?m_DropSource@CMFCToolBar@@1VCMFCToolBarDropSource@@A; pDropSource
0x180157226  lea     point, [rbp+57h+rect]; lpRectStartDrag
0x18015722a  mov     nFlags, 3; dwEffects
0x18015722f  lea     this, [rbp+57h+srcItem]; this
0x180157233  call    ?DoDragDrop@COleDataSource@@QEAAKKPEBUtagRECT@@PEAVCOleDropSource@@@Z; COleDataSource::DoDragDrop(ulong,tagRECT const *,COleDropSource *)
0x180157238  mov     ebx, eax
0x18015723a  mov     this, r14; hWnd
0x18015723d  call    cs:__imp_IsWindow
0x180157243  test    eax, eax
0x180157245  jnz     short loc_180157273
0x180157247  cmp     cs:?m_bAltCustomizeMode@CMFCToolBar@@1HA, r13d; int CMFCToolBar::m_bAltCustomizeMode
0x18015724e  jz      short loc_180157265
0x180157250  mov     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, r13d; int CMFCToolBar::m_bCustomizeMode
0x180157257  mov     cs:?m_bAltCustomizeMode@CMFCToolBar@@1HA, r13d; int CMFCToolBar::m_bAltCustomizeMode
0x18015725e  mov     cs:?m_pSelToolbar@CMFCToolBar@@1PEAV1@EA, r13; CMFCToolBar * CMFCToolBar::m_pSelToolbar
0x180157265  lea     this, [rbp+57h+srcItem]; this
0x180157269  call    ??1COleDataSource@@UEAA@XZ; COleDataSource::~COleDataSource(void)
0x18015726e  jmp     loc_180157676
0x180157273  mov     qword ptr [rbp+57h+ptDrop.x], r13
0x180157277  lea     this, [rbp+57h+ptDrop]; lpPoint
0x18015727b  call    cs:__imp_GetCursorPos
0x180157281  lea     rdx, [rbp+57h+ptDrop]; lpPoint
0x180157285  mov     this, [rdi+40h]; hWnd
0x180157289  call    cs:__imp_ScreenToClient
0x18015728f  cmp     cs:?m_DropSource@CMFCToolBar@@1VCMFCToolBarDropSource@@A.m_bDragStarted, r13d; CMFCToolBarDropSource CMFCToolBar::m_DropSource ...
0x180157296  jz      loc_180157468
0x18015729c  mov     rdx, qword ptr [rbp+57h+ptDrop.x]; pt
0x1801572a0  lea     this, [rbp+57h+rect]; lprc
0x1801572a4  call    cs:__imp_PtInRect
0x1801572aa  test    eax, eax
0x1801572ac  jnz     loc_180157468
0x1801572b2  cmp     ebx, r15d
0x1801572b5  jz      loc_180157449
0x1801572bb  mov     rdx, [rdi+12F0h]
0x1801572c2  test    rdx, rdx
0x1801572c5  jz      loc_180157449
0x1801572cb  cmp     cs:?m_DropSource@CMFCToolBar@@1VCMFCToolBarDropSource@@A.m_bEscapePressed, r13d; CMFCToolBarDropSource CMFCToolBar::m_DropSource ...
0x1801572d2  jnz     loc_180157449
0x1801572d8  mov     rax, [rdi]
0x1801572db  mov     r8d, ebx
0x1801572de  mov     this, rdi
0x1801572e1  mov     rax, [rax+708h]
0x1801572e8  call    cs:__guard_dispatch_icall_fptr
0x1801572ee  test    eax, eax
0x1801572f0  jz      loc_180157449
0x1801572f6  mov     rax, [rdi]
0x1801572f9  mov     rbx, [rax+6A8h]
0x180157300  mov     rdx, [rdi+12F0h]; pButton
0x180157307  mov     this, rdi; this
0x18015730a  call    ?ButtonToIndex@CMFCToolBar@@QEBAHPEBVCMFCToolBarButton@@@Z; CMFCToolBar::ButtonToIndex(CMFCToolBarButton const *)
0x18015730f  mov     nFlags, eax
0x180157311  mov     this, rdi
0x180157314  mov     rax, rbx
0x180157317  call    cs:__guard_dispatch_icall_fptr
0x18015731d  mov     rax, [rdi]
  ... truncated ...
```
