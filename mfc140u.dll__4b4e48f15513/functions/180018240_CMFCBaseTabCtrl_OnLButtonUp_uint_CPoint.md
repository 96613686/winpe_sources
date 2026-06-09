# CMFCBaseTabCtrl::OnLButtonUp(uint,CPoint)

- ea: `0x180018240`
- end: `0x1800185a1`
- name: `?OnLButtonUp@CMFCBaseTabCtrl@@IEAAXIVCPoint@@@Z`
- size: `865`
- prototype: `void __fastcall(CMFCBaseTabCtrl *this, unsigned int nFlags, CPoint point)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800a0e70`
- `0x180140f20`

## callees

- `0x180018240`
- `0x1800189c0`
- `0x18006e040`
- `0x18023f820`
- `0x180296c00`
- `0x180296d00`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!SendMessageW` at `0x1800182db`
- `USER32!SendMessageW` at `0x180018325`
- `USER32!SendMessageW` at `0x180018376`
- `USER32!SendMessageW` at `0x1800182db`
- `USER32!SendMessageW` at `0x180018325`
- `USER32!SendMessageW` at `0x180018376`
- `USER32!InvalidateRect` at `0x180018541`
- `USER32!InvalidateRect` at `0x180018562`
- `USER32!InvalidateRect` at `0x180018541`
- `USER32!InvalidateRect` at `0x180018562`
- `USER32!ReleaseCapture` at `0x180018390`
- `USER32!ReleaseCapture` at `0x180018462`
- `USER32!ReleaseCapture` at `0x1800184bf`
- `USER32!ReleaseCapture` at `0x180018390`
- `USER32!ReleaseCapture` at `0x180018462`
- `USER32!ReleaseCapture` at `0x1800184bf`
- `USER32!IsRectEmpty` at `0x18001852b`
- `USER32!IsRectEmpty` at `0x18001854c`
- `USER32!IsRectEmpty` at `0x18001852b`
- `USER32!IsRectEmpty` at `0x18001854c`
- `USER32!GetParent` at `0x1800182fc`
- `USER32!GetParent` at `0x1800182fc`
- `USER32!PtInRect` at `0x1800182a7`
- `USER32!PtInRect` at `0x1800182a7`
- `USER32!UpdateWindow` at `0x18001856c`
- `USER32!UpdateWindow` at `0x18001856c`
- `USER32!RedrawWindow` at `0x18001829b`
- `USER32!RedrawWindow` at `0x18001829b`

## pseudocode

```c
void __fastcall CMFCBaseTabCtrl::OnLButtonUp(CMFCBaseTabCtrl *this, __int64 nFlags, CPoint point)
{
  CRect *p_m_rectCloseButton; // rdi
  CWnd *v6; // rax
  HWND Parent; // rax
  CWnd *v8; // rbx
  CFrameWnd *v9; // rax
  int m_iHighlighted; // ebx
  int m_iActiveTab; // r14d
  CMFCBaseTabCtrl_vtbl *v12; // rax
  int v13; // eax
  CMFCBaseTabCtrl_vtbl *v14; // r8
  int (__fastcall *IsOneNoteStyle)(CMFCBaseTabCtrl *); // rax
  CMFCBaseTabCtrl_vtbl *v16; // rax
  int m_iPressed; // edi
  int v18; // ebp
  CMFCBaseTabCtrl_vtbl *v19; // rax
  void (__fastcall *GetTabArea)(CMFCBaseTabCtrl *, CRect *, CRect *); // rax
  CRect rectTabAreaTop; // [rsp+20h] [rbp-48h] BYREF
  CRect rectTabAreaBottom; // [rsp+30h] [rbp-38h] BYREF

  if ( this->m_bTabCloseButtonPressed )
  {
    this->m_bTabCloseButtonPressed = 0;
    p_m_rectCloseButton = &this->m_rectCloseButton;
    this->m_bTabCloseButtonHighlighted = 0;
    RedrawWindow(this->m_hWnd, &this->m_rectCloseButton, 0, 0x105u);
    if ( PtInRect(p_m_rectCloseButton, point.tagPOINT) )
    {
      v6 = this->GetActiveWnd(this);
      if ( v6 )
        SendMessageW(v6->m_hWnd, 0x10u, 0, 0);
      return;
    }
  }
  if ( this->m_iTabBeforeDrag != this->m_iActiveTab )
  {
    Parent = GetParent(this->m_hWnd);
    v8 = CWnd::FromHandle(Parent);
    SendMessageW(v8->m_hWnd, AFX_WM_ON_MOVE_TAB, this->m_iTabBeforeDrag, this->m_iActiveTab);
    if ( CObject::IsKindOf(v8, &CBaseTabbedPane::classCBaseTabbedPane)
      || CObject::IsKindOf(v8, &CMDIClientAreaWnd::classCMDIClientAreaWnd) )
    {
      v9 = AFXGetParentFrame(v8);
      if ( v9 )
        SendMessageW(v9->m_hWnd, AFX_WM_ON_MOVE_TAB, this->m_iTabBeforeDrag, this->m_iActiveTab);
    }
  }
  if ( this->m_bReadyToDetach )
  {
    this->m_bReadyToDetach = 0;
    ReleaseCapture();
    if ( !this->ActivateOnBtnUp(this) )
    {
      this->m_iPressed = -1;
      this->m_iHighlighted = -1;
    }
  }
  if ( ((unsigned int (__fastcall *)(CMFCBaseTabCtrl *, __int64))this->ActivateOnBtnUp)(this, nFlags) )
  {
    m_iHighlighted = this->m_iHighlighted;
    m_iActiveTab = this->m_iActiveTab;
    if ( m_iHighlighted == this->m_iPressed && m_iHighlighted >= 0 && m_iHighlighted != m_iActiveTab )
    {
      v12 = this->__vftable;
      this->m_bUserSelectedTab = 0;
      this->m_iLastActiveTab = m_iActiveTab;
      this->m_bSetActiveTabByMouseClick = 1;
      v13 = v12->SetActiveTab(this, m_iHighlighted);
      v14 = this->__vftable;
      if ( !v13 )
      {
        this->m_bSetActiveTabByMouseClick = 0;
        this->m_bUserSelectedTab = 0;
        IsOneNoteStyle = v14->IsOneNoteStyle;
        this->m_iPressed = -1;
        if ( !IsOneNoteStyle(this) )
          this->m_iHighlighted = -1;
        ReleaseCapture();
        return;
      }
      v14->FireChangeActiveTab(this, this->m_iActiveTab);
      this->m_bSetActiveTabByMouseClick = 0;
      this->m_bUserSelectedTab = 0;
    }
    v16 = this->__vftable;
    m_iPressed = this->m_iPressed;
    v18 = this->m_iHighlighted;
    this->m_iPressed = -1;
    if ( !v16->IsOneNoteStyle(this) )
      this->m_iHighlighted = -1;
    ReleaseCapture();
    if ( m_iActiveTab != m_iHighlighted )
    {
      CMFCBaseTabCtrl::InvalidateTab(this, v18);
      if ( m_iPressed != v18 )
        CMFCBaseTabCtrl::InvalidateTab(this, m_iPressed);
    }
  }
  if ( this->IsOneNoteStyle(this) )
  {
    v19 = this->__vftable;
    rectTabAreaTop = 0;
    GetTabArea = v19->GetTabArea;
    rectTabAreaBottom = 0;
    GetTabArea(this, &rectTabAreaTop, &rectTabAreaBottom);
    if ( !IsRectEmpty(&rectTabAreaTop) )
      InvalidateRect(this->m_hWnd, &rectTabAreaTop, 0);
    if ( !IsRectEmpty(&rectTabAreaBottom) )
      InvalidateRect(this->m_hWnd, &rectTabAreaBottom, 0);
    UpdateWindow(this->m_hWnd);
  }
  CWnd::Default(this);
}

```

## disassembly

```asm
0x180018240  mov     [rsp+arg_8], rbx
0x180018245  mov     [rsp+arg_10], rbp
0x18001824a  mov     [rsp+arg_18], rsi
0x18001824f  push    rdi
0x180018250  push    r12
0x180018252  push    r14
0x180018254  sub     rsp, 50h
0x180018258  mov     rax, cs:__security_cookie
0x18001825f  xor     rax, rsp
0x180018262  mov     [rsp+68h+var_28], rax
0x180018267  cmp     dword ptr [this+348h], 0
0x18001826e  mov     rbx, point
0x180018271  mov     rsi, this
0x180018274  jz      short loc_1800182E6
0x180018276  and     dword ptr [this+348h], 0
0x18001827d  lea     rdi, [this+34Ch]
0x180018284  and     dword ptr [this+344h], 0
0x18001828b  mov     rdx, rdi; lprcUpdate
0x18001828e  mov     this, [this+40h]; hWnd
0x180018292  mov     r9d, 105h; flags
0x180018298  xor     r8d, r8d; hrgnUpdate
0x18001829b  call    cs:__imp_RedrawWindow
0x1800182a1  mov     rdx, rbx; pt
0x1800182a4  mov     this, rdi; lprc
0x1800182a7  call    cs:__imp_PtInRect
0x1800182ad  test    eax, eax
0x1800182af  jz      short loc_1800182E6
0x1800182b1  mov     rax, [rsi]
0x1800182b4  mov     this, rsi
0x1800182b7  mov     rax, [rax+430h]
0x1800182be  call    cs:__guard_dispatch_icall_fptr
0x1800182c4  test    rax, rax
0x1800182c7  jz      loc_18001857A
0x1800182cd  mov     this, [rax+40h]; hWnd
0x1800182d1  xor     r9d, r9d; lParam
0x1800182d4  xor     r8d, r8d; wParam
0x1800182d7  lea     nFlags, [r9+10h]; Msg
0x1800182db  call    cs:__imp_SendMessageW
0x1800182e1  jmp     loc_18001857A
0x1800182e6  mov     eax, [rsi+154h]
0x1800182ec  cmp     [rsi+158h], eax
0x1800182f2  jz      loc_18001837C
0x1800182f8  mov     this, [rsi+40h]; hWnd
0x1800182fc  call    cs:__imp_GetParent
0x180018302  mov     this, rax; hWnd
0x180018305  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18001830a  movsxd  r9, dword ptr [rsi+154h]; lParam
0x180018311  mov     rbx, rax
0x180018314  movsxd  point, dword ptr [rsi+158h]; wParam
0x18001831b  mov     nFlags, cs:?AFX_WM_ON_MOVE_TAB@@3IA; Msg
0x180018321  mov     this, [rax+40h]; hWnd
0x180018325  call    cs:__imp_SendMessageW
0x18001832b  lea     rdx, ?classCBaseTabbedPane@CBaseTabbedPane@@2UCRuntimeClass@@B; pClass
0x180018332  mov     this, rbx; this
0x180018335  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18001833a  test    eax, eax
0x18001833c  jnz     short loc_180018351
0x18001833e  lea     rdx, ?classCMDIClientAreaWnd@CMDIClientAreaWnd@@2UCRuntimeClass@@B; pClass
0x180018345  mov     this, rbx; this
0x180018348  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18001834d  test    eax, eax
0x18001834f  jz      short loc_18001837C
0x180018351  mov     this, rbx; pWnd
0x180018354  call    ?AFXGetParentFrame@@YAPEAVCFrameWnd@@PEBVCWnd@@@Z; AFXGetParentFrame(CWnd const *)
0x180018359  test    rax, rax
0x18001835c  jz      short loc_18001837C
0x18001835e  movsxd  r9, dword ptr [rsi+154h]; lParam
0x180018365  movsxd  point, dword ptr [rsi+158h]; wParam
0x18001836c  mov     nFlags, cs:?AFX_WM_ON_MOVE_TAB@@3IA; Msg
0x180018372  mov     this, [rax+40h]; hWnd
0x180018376  call    cs:__imp_SendMessageW
0x18001837c  or      r12d, 0FFFFFFFFh
0x180018380  cmp     dword ptr [rsi+234h], 0
0x180018387  jz      short loc_1800183BB
0x180018389  and     dword ptr [rsi+234h], 0
0x180018390  call    cs:__imp_ReleaseCapture
0x180018396  mov     rax, [rsi]
0x180018399  mov     this, rsi
0x18001839c  mov     rax, [rax+5A8h]
0x1800183a3  call    cs:__guard_dispatch_icall_fptr
0x1800183a9  test    eax, eax
0x1800183ab  jnz     short loc_1800183BB
0x1800183ad  mov     [rsi+1E0h], r12d
0x1800183b4  mov     [rsi+1DCh], r12d
0x1800183bb  mov     rax, [rsi]
0x1800183be  mov     this, rsi
0x1800183c1  mov     rax, [rax+5A8h]
0x1800183c8  call    cs:__guard_dispatch_icall_fptr
0x1800183ce  test    eax, eax
0x1800183d0  jz      loc_1800184E2
0x1800183d6  mov     ebx, [rsi+1DCh]
0x1800183dc  mov     r14d, [rsi+154h]
0x1800183e3  cmp     ebx, [rsi+1E0h]
0x1800183e9  jnz     loc_18001848E
0x1800183ef  test    ebx, ebx
0x1800183f1  js      loc_18001848E
0x1800183f7  cmp     ebx, r14d
0x1800183fa  jz      loc_18001848E
0x180018400  mov     rax, [rsi]
0x180018403  mov     nFlags, ebx
0x180018405  and     dword ptr [rsi+3B8h], 0
0x18001840c  mov     this, rsi
0x18001840f  mov     [rsi+330h], r14d
0x180018416  mov     dword ptr [rsi+33Ch], 1
0x180018420  mov     rax, [rax+438h]
0x180018427  call    cs:__guard_dispatch_icall_fptr
0x18001842d  mov     point, [rsi]
0x180018430  mov     this, rsi
0x180018433  test    eax, eax
0x180018435  jnz     short loc_18001846D
0x180018437  and     [rsi+33Ch], eax
0x18001843d  and     [rsi+3B8h], eax
0x180018443  mov     rax, [point+520h]
0x18001844a  mov     [rsi+1E0h], r12d
0x180018451  call    cs:__guard_dispatch_icall_fptr
0x180018457  test    eax, eax
0x180018459  jnz     short loc_180018462
0x18001845b  mov     [rsi+1DCh], r12d
0x180018462  call    cs:__imp_ReleaseCapture
0x180018468  jmp     loc_18001857A
0x18001846d  mov     nFlags, [rsi+154h]
0x180018473  mov     rax, [point+4F0h]
0x18001847a  call    cs:__guard_dispatch_icall_fptr
0x180018480  and     dword ptr [rsi+33Ch], 0
0x180018487  and     dword ptr [rsi+3B8h], 0
0x18001848e  mov     rax, [rsi]
0x180018491  mov     this, rsi
0x180018494  mov     edi, [rsi+1E0h]
0x18001849a  mov     ebp, [rsi+1DCh]
0x1800184a0  mov     [rsi+1E0h], r12d
0x1800184a7  mov     rax, [rax+520h]
0x1800184ae  call    cs:__guard_dispatch_icall_fptr
0x1800184b4  test    eax, eax
0x1800184b6  jnz     short loc_1800184BF
0x1800184b8  mov     [rsi+1DCh], r12d
0x1800184bf  call    cs:__imp_ReleaseCapture
0x1800184c5  cmp     r14d, ebx
0x1800184c8  jz      short loc_1800184E2
0x1800184ca  mov     nFlags, ebp; iTab
0x1800184cc  mov     this, rsi; this
0x1800184cf  call    ?InvalidateTab@CMFCBaseTabCtrl@@QEAAXH@Z; CMFCBaseTabCtrl::InvalidateTab(int)
0x1800184d4  cmp     edi, ebp
0x1800184d6  jz      short loc_1800184E2
0x1800184d8  mov     nFlags, edi; iTab
0x1800184da  mov     this, rsi; this
0x1800184dd  call    ?InvalidateTab@CMFCBaseTabCtrl@@QEAAXH@Z; CMFCBaseTabCtrl::InvalidateTab(int)
0x1800184e2  mov     rax, [rsi]
0x1800184e5  mov     this, rsi
0x1800184e8  mov     rax, [rax+520h]
0x1800184ef  call    cs:__guard_dispatch_icall_fptr
0x1800184f5  test    eax, eax
0x1800184f7  jz      short loc_180018572
0x1800184f9  mov     rax, [rsi]
0x1800184fc  lea     point, [rsp+68h+rectTabAreaBottom]
0x180018501  xorps   xmm0, xmm0
0x180018504  lea     rdx, [rsp+68h+rectTabAreaTop]
0x180018509  xorps   xmm1, xmm1
0x18001850c  mov     this, rsi
0x18001850f  movups  xmmword ptr [rsp+68h+rectTabAreaTop.left], xmm0
0x180018514  mov     rax, [rax+2E0h]
0x18001851b  movups  xmmword ptr [rsp+68h+rectTabAreaBottom.left], xmm1
0x180018520  call    cs:__guard_dispatch_icall_fptr
0x180018526  lea     this, [rsp+68h+rectTabAreaTop]; lprc
0x18001852b  call    cs:__imp_IsRectEmpty
0x180018531  test    eax, eax
0x180018533  jnz     short loc_180018547
0x180018535  mov     this, [rsi+40h]; hWnd
0x180018539  lea     rdx, [rsp+68h+rectTabAreaTop]; lpRect
0x18001853e  xor     r8d, r8d; bErase
0x180018541  call    cs:__imp_InvalidateRect
0x180018547  lea     this, [rsp+68h+rectTabAreaBottom]; lprc
0x18001854c  call    cs:__imp_IsRectEmpty
0x180018552  test    eax, eax
0x180018554  jnz     short loc_180018568
0x180018556  mov     this, [rsi+40h]; hWnd
0x18001855a  lea     rdx, [rsp+68h+rectTabAreaBottom]; lpRect
0x18001855f  xor     r8d, r8d; bErase
0x180018562  call    cs:__imp_InvalidateRect
0x180018568  mov     this, [rsi+40h]; hWnd
0x18001856c  call    cs:__imp_UpdateWindow
0x180018572  mov     this, rsi; this
0x180018575  call    ?Default@CWnd@@IEAA_JXZ; CWnd::Default(void)
0x18001857a  mov     this, [rsp+68h+var_28]
0x18001857f  xor     this, rsp; StackCookie
0x180018582  call    __security_check_cookie
0x180018587  lea     r11, [rsp+68h+var_18]
0x18001858c  mov     rbx, [r11+28h]
0x180018590  mov     rbp, [r11+30h]
0x180018594  mov     rsi, [r11+38h]
0x180018598  mov     rsp, r11
0x18001859b  pop     r14
0x18001859d  pop     r12
0x18001859f  pop     rdi
0x1800185a0  retn
```
