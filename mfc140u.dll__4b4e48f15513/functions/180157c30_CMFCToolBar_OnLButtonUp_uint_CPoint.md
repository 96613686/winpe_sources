# CMFCToolBar::OnLButtonUp(uint,CPoint)

- ea: `0x180157c30`
- end: `0x180158090`
- name: `?OnLButtonUp@CMFCToolBar@@IEAAXIVCPoint@@@Z`
- size: `1120`
- prototype: `void __fastcall(CMFCToolBar *this, unsigned int nFlags, CPoint point)`
- caller_count: `4`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180027fb0`
- `0x18005f080`
- `0x18009c910`
- `0x1800c1e00`

## callees

- `0x180023e80`
- `0x1800a2a20`
- `0x1801567a0`
- `0x1801567f0`
- `0x1801576b0`
- `0x180157c30`
- `0x180158810`
- `0x18018b740`
- `0x18023f820`
- `0x180296d00`
- `0x1802c7020`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!labs` at `0x180157c94`
- `api-ms-win-crt-utility-l1-1-0!labs` at `0x180157c94`
- `USER32!IsIconic` at `0x180157fc3`
- `USER32!IsIconic` at `0x180157fc3`
- `USER32!IsZoomed` at `0x180157fd0`
- `USER32!IsZoomed` at `0x180157fd0`
- `USER32!SetRectEmpty` at `0x180157ccf`
- `USER32!SetRectEmpty` at `0x180157ccf`
- `USER32!SendMessageW` at `0x180157ead`
- `USER32!SendMessageW` at `0x180157fab`
- `USER32!SendMessageW` at `0x180157ead`
- `USER32!SendMessageW` at `0x180157fab`
- `USER32!IsWindow` at `0x180157fb6`
- `USER32!IsWindow` at `0x180157fed`
- `USER32!IsWindow` at `0x180157fb6`
- `USER32!IsWindow` at `0x180157fed`
- `USER32!SetCapture` at `0x180157d0e`
- `USER32!SetCapture` at `0x180157dac`
- `USER32!SetCapture` at `0x180157d0e`
- `USER32!SetCapture` at `0x180157dac`
- `USER32!ReleaseCapture` at `0x180157cf8`
- `USER32!ReleaseCapture` at `0x180157d96`
- `USER32!ReleaseCapture` at `0x180157cf8`
- `USER32!ReleaseCapture` at `0x180157d96`
- `USER32!GetParent` at `0x180157e8d`
- `USER32!GetParent` at `0x180157f8e`
- `USER32!GetParent` at `0x180157e8d`
- `USER32!GetParent` at `0x180157f8e`
- `USER32!UpdateWindow` at `0x180157f39`
- `USER32!UpdateWindow` at `0x180158049`
- `USER32!UpdateWindow` at `0x180157f39`
- `USER32!UpdateWindow` at `0x180158049`
- `USER32!RedrawWindow` at `0x180157cf2`
- `USER32!RedrawWindow` at `0x180157cf2`

## pseudocode

```c
void __fastcall CMFCToolBar::OnLButtonUp(CMFCToolBar *this, unsigned int nFlags, CPoint point)
{
  CPoint v3; // rbx
  unsigned int v4; // edi
  CMFCToolBar *v5; // rsi
  CMFCToolBarButton *m_pDragButton; // rcx
  int v7; // ebp
  HWND m_hWnd; // rcx
  CWnd *m_pWndLastCapture; // rcx
  HWND v10; // rax
  CWnd *v11; // rcx
  HWND v12; // rax
  int v13; // eax
  int m_iButtonCapture; // edx
  CMFCToolBarButton *Button; // rax
  CMFCToolBarButton *v16; // rdi
  int IsKindOf; // r13d
  unsigned int v18; // ebp
  unsigned int m_nID; // r15d
  int v20; // r14d
  unsigned int v21; // ecx
  HWND m_hWndOwner; // rax
  CWnd *v23; // rax
  __int64 v24; // r14
  HWND v25; // r12
  HWND Parent; // rax
  CWnd *v27; // rax
  CMFCToolBarButton *v28; // rax

  v3 = point;
  v4 = nFlags;
  v5 = this;
  if ( CMFCToolBar::m_bCustomizeMode && !this->m_bLocked )
  {
    if ( this->m_bStretchButton )
    {
      m_pDragButton = this->m_pDragButton;
      v7 = point.x - m_pDragButton->m_rect.left;
      if ( v7 >= 5 && labs(m_pDragButton->m_rect.right - point.x) > 6 )
      {
        v5->m_pDragButton->OnSize(v5->m_pDragButton, v7);
        v5->AdjustLayout(v5);
      }
      SetRectEmpty(&v5->m_rectTrack);
      m_hWnd = v5->m_hWnd;
      v5->m_pDragButton = 0;
      v5->m_bStretchButton = 0;
      RedrawWindow(m_hWnd, 0, 0, 0x505u);
      ReleaseCapture();
      m_pWndLastCapture = v5->m_pWndLastCapture;
      if ( m_pWndLastCapture )
      {
        v10 = SetCapture(m_pWndLastCapture->m_hWnd);
        CWnd::FromHandle(v10);
        v5->m_pWndLastCapture = 0;
      }
      v5->AdjustSizeImmediate(v5, 1);
    }
    point = v3;
    nFlags = v4;
    this = v5;
    goto LABEL_11;
  }
  if ( this->m_bDragMode )
  {
LABEL_11:
    CPane::OnLButtonUp(this, nFlags, point);
    return;
  }
  if ( this->m_iButtonCapture == -1 )
  {
    if ( ((__int64 (__fastcall *)(_QWORD, _QWORD))this->HitTest)(this, point) != -1 )
      return;
    CPane::OnLButtonUp(v5, v4, v3);
    goto LABEL_50;
  }
  ReleaseCapture();
  v11 = v5->m_pWndLastCapture;
  if ( v11 )
  {
    v12 = SetCapture(v11->m_hWnd);
    CWnd::FromHandle(v12);
    v5->m_pWndLastCapture = 0;
  }
  v13 = v5->HitTest(v5, v3);
  m_iButtonCapture = v5->m_iButtonCapture;
  v5->m_iHighlighted = v13;
  Button = CMFCToolBar::GetButton(v5, m_iButtonCapture);
  v16 = Button;
  if ( Button )
  {
    IsKindOf = CObject::IsKindOf(Button, &CMFCToolBarMenuButtonsButton::classCMFCToolBarMenuButtonsButton);
    v18 = v16->m_nStyle & 0xFFFDFFFF;
    m_nID = 0;
    if ( v5->m_iButtonCapture == v5->m_iHighlighted )
    {
      v20 = v5->m_iButtonCapture;
      if ( v5->HitTest(v5, v3) == v20 )
      {
        CMFCToolBar::UpdateButton(v5, v20);
        if ( (v16->m_nStyle & 0x40000) == 0 )
        {
          m_nID = v16->m_nID;
          if ( (v16->m_nStyle & 2) != 0 )
          {
            v21 = v18 & 0xFFEFFFFF;
            if ( (v18 & 0x100000) == 0 )
              v21 = v18;
            v18 = v21 ^ 0x10000;
          }
        }
      }
    }
    if ( !CMFCToolBar::m_hookMouseHelp )
    {
      m_hWndOwner = v5->m_hWndOwner;
      if ( !m_hWndOwner )
        m_hWndOwner = GetParent(v5->m_hWnd);
      v23 = CWnd::FromHandle(m_hWndOwner);
      SendMessageW(v23->m_hWnd, 0x362u, 0xE001u, 0);
    }
    v24 = v5->m_iButtonCapture;
    v25 = v5->m_hWnd;
    v5->m_iButtonCapture = -1;
    v5->m_iHighlighted = -1;
    v5->RestoreFocus(v5);
    if ( v5->HitTest(v5, v3) != (_DWORD)v24 || v5->OnSendCommand(v5, v16) || m_nID - 1 > 0xFFFFFFFD )
    {
      if ( IsWindow(v25) && !IsIconic(v25) && IsZoomed(v25) )
        v16->OnClickUp(v16);
    }
    else
    {
      CMFCToolBar::InvalidateButton(v5, v24);
      UpdateWindow(v5->m_hWnd);
      CMFCCmdUsageCount::AddCmd(&CMFCToolBar::m_UsageCount, m_nID);
      if ( !v16->OnClickUp(v16) && (!afxUserToolsManager || !CUserToolsManager::InvokeTool(afxUserToolsManager, m_nID)) )
      {
        Parent = v5->m_hWndOwner;
        if ( !Parent )
          Parent = GetParent(v5->m_hWnd);
        v27 = CWnd::FromHandle(Parent);
        SendMessageW(v27->m_hWnd, 0x111u, m_nID, 0);
      }
    }
    if ( IsWindow(v25) && v24 < v5->m_Buttons.m_nCount )
    {
      if ( IsKindOf )
      {
        v28 = CMFCToolBar::GetButton(v5, v24);
        if ( v28 )
          v28->m_nStyle &= ~0x20000u;
      }
      else
      {
        v5->SetButtonStyle(v5, v24, v18);
      }
      CMFCToolBar::UpdateButton(v5, v24);
      CMFCToolBar::InvalidateButton(v5, v24);
      UpdateWindow(v5->m_hWnd);
LABEL_50:
      v5->m_ptLastMouse = (CPoint)-1LL;
      CMFCToolBar::OnMouseMove(v5, 0, v3);
    }
  }
}

```

## disassembly

```asm
0x180157c30  mov     [rsp+arg_0], rbx
0x180157c35  mov     [rsp+arg_8], rbp
0x180157c3a  mov     [rsp+arg_10], rsi
0x180157c3f  push    rdi
0x180157c40  push    r12
0x180157c42  push    r13
0x180157c44  push    r14
0x180157c46  push    r15
0x180157c48  sub     rsp, 20h
0x180157c4c  xor     r12d, r12d
0x180157c4f  mov     rbx, point
0x180157c52  cmp     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, r12d; int CMFCToolBar::m_bCustomizeMode
0x180157c59  mov     edi, nFlags
0x180157c5b  mov     rsi, this
0x180157c5e  jz      loc_180157D4D
0x180157c64  cmp     [this+10B8h], r12d
0x180157c6b  jnz     loc_180157D4D
0x180157c71  cmp     [this+10E4h], r12d
0x180157c78  jz      loc_180157D3B
0x180157c7e  mov     this, [this+12F0h]
0x180157c85  mov     ebp, ebx
0x180157c87  sub     ebp, [this+68h]
0x180157c8a  cmp     ebp, 5
0x180157c8d  jl      short loc_180157CC8
0x180157c8f  mov     ecx, [this+70h]
0x180157c92  sub     ecx, ebx; Number
0x180157c94  call    cs:__imp_labs
0x180157c9a  cmp     eax, 6
0x180157c9d  jle     short loc_180157CC8
0x180157c9f  mov     this, [rsi+12F0h]
0x180157ca6  mov     nFlags, ebp
0x180157ca8  mov     rax, [this]
0x180157cab  mov     rax, [rax+78h]
0x180157caf  call    cs:__guard_dispatch_icall_fptr
0x180157cb5  mov     rax, [rsi]
0x180157cb8  mov     this, rsi
0x180157cbb  mov     rax, [rax+428h]
0x180157cc2  call    cs:__guard_dispatch_icall_fptr
0x180157cc8  lea     this, [rsi+12B0h]; lprc
0x180157ccf  call    cs:__imp_SetRectEmpty
0x180157cd5  mov     this, [rsi+40h]; hWnd
0x180157cd9  mov     r9d, 505h; flags
0x180157cdf  xor     r8d, r8d; hrgnUpdate
0x180157ce2  mov     [rsi+12F0h], r12
0x180157ce9  xor     nFlags, nFlags; lprcUpdate
0x180157ceb  mov     [rsi+10E4h], r12d
0x180157cf2  call    cs:__imp_RedrawWindow
0x180157cf8  call    cs:__imp_ReleaseCapture
0x180157cfe  mov     this, [rsi+12E0h]
0x180157d05  test    this, this
0x180157d08  jz      short loc_180157D23
0x180157d0a  mov     this, [this+40h]; hWnd
0x180157d0e  call    cs:__imp_SetCapture
0x180157d14  mov     this, rax; hWnd
0x180157d17  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x180157d1c  mov     [rsi+12E0h], r12
0x180157d23  mov     rax, [rsi]
0x180157d26  mov     nFlags, 1
0x180157d2b  mov     this, rsi
0x180157d2e  mov     rax, [rax+5B8h]
0x180157d35  call    cs:__guard_dispatch_icall_fptr
0x180157d3b  mov     point, rbx; point
0x180157d3e  mov     nFlags, edi; nFlags
0x180157d40  mov     this, rsi; this
0x180157d43  call    ?OnLButtonUp@CPane@@IEAAXIVCPoint@@@Z; CPane::OnLButtonUp(uint,CPoint)
0x180157d48  jmp     loc_180158073
0x180157d4d  cmp     [this+214h], r12d
0x180157d54  jnz     short loc_180157D43
0x180157d56  or      ebp, 0FFFFFFFFh
0x180157d59  cmp     [this+1134h], ebp
0x180157d5f  jnz     short loc_180157D96
0x180157d61  mov     rax, [this]
0x180157d64  mov     rdx, rbx
0x180157d67  mov     rax, [rax+730h]
0x180157d6e  call    cs:__guard_dispatch_icall_fptr
0x180157d74  cmp     eax, ebp
0x180157d76  jnz     loc_180158073
0x180157d7c  mov     point, rbx; point
0x180157d7f  mov     nFlags, edi; nFlags
0x180157d81  mov     this, rsi; this
0x180157d84  call    ?OnLButtonUp@CPane@@IEAAXIVCPoint@@@Z; CPane::OnLButtonUp(uint,CPoint)
0x180157d89  mov     dword ptr [rsp+48h+arg_18], ebp
0x180157d8d  mov     dword ptr [rsp+48h+arg_18+4], ebp
0x180157d91  jmp     loc_18015805A
0x180157d96  call    cs:__imp_ReleaseCapture
0x180157d9c  mov     this, [rsi+12E0h]
0x180157da3  test    this, this
0x180157da6  jz      short loc_180157DC1
0x180157da8  mov     this, [this+40h]; hWnd
0x180157dac  call    cs:__imp_SetCapture
0x180157db2  mov     this, rax; hWnd
0x180157db5  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x180157dba  mov     [rsi+12E0h], r12
0x180157dc1  mov     rax, [rsi]
0x180157dc4  mov     rdx, rbx
0x180157dc7  mov     this, rsi
0x180157dca  mov     rax, [rax+730h]
0x180157dd1  call    cs:__guard_dispatch_icall_fptr
0x180157dd7  mov     nFlags, [rsi+1134h]; nIndex
0x180157ddd  mov     this, rsi; this
0x180157de0  mov     [rsi+1138h], eax
0x180157de6  call    ?GetButton@CMFCToolBar@@QEBAPEAVCMFCToolBarButton@@H@Z; CMFCToolBar::GetButton(int)
0x180157deb  mov     rdi, rax
0x180157dee  test    rax, rax
0x180157df1  jz      loc_180158073
0x180157df7  lea     rdx, ?classCMFCToolBarMenuButtonsButton@CMFCToolBarMenuButtonsButton@@2UCRuntimeClass@@B; pClass
0x180157dfe  mov     this, rax; this
0x180157e01  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180157e06  mov     ebp, [rdi+28h]
0x180157e09  mov     r13d, eax
0x180157e0c  mov     ecx, [rsi+1138h]
0x180157e12  btr     ebp, 11h
0x180157e16  mov     r15d, r12d
0x180157e19  cmp     [rsi+1134h], ecx
0x180157e1f  jnz     short loc_180157E74
0x180157e21  mov     this, [rsi]
0x180157e24  mov     rdx, rbx
0x180157e27  mov     r14d, [rsi+1134h]
0x180157e2e  mov     rax, [this+730h]
0x180157e35  mov     this, rsi
0x180157e38  call    cs:__guard_dispatch_icall_fptr
0x180157e3e  cmp     eax, r14d
0x180157e41  jnz     short loc_180157E74
0x180157e43  mov     nFlags, r14d; nIndex
0x180157e46  mov     this, rsi; this
0x180157e49  call    ?UpdateButton@CMFCToolBar@@QEAAXH@Z; CMFCToolBar::UpdateButton(int)
0x180157e4e  test    dword ptr [rdi+28h], 40000h
0x180157e55  jnz     short loc_180157E74
0x180157e57  test    byte ptr [rdi+28h], 2
0x180157e5b  mov     r15d, [rdi+24h]
0x180157e5f  jz      short loc_180157E74
0x180157e61  mov     ecx, ebp
0x180157e63  btr     ecx, 14h
0x180157e67  bt      ebp, 14h
0x180157e6b  cmovnb  ecx, ebp
0x180157e6e  mov     ebp, ecx
0x180157e70  btc     ebp, 10h
0x180157e74  cmp     cs:?m_hookMouseHelp@CMFCToolBar@@1PEAUHHOOK__@@EA, r12; HHOOK__ * CMFCToolBar::m_hookMouseHelp
0x180157e7b  jnz     short loc_180157EB3
0x180157e7d  mov     rax, [rsi+0A0h]
0x180157e84  test    rax, rax
0x180157e87  jnz     short loc_180157E93
0x180157e89  mov     this, [rsi+40h]; hWnd
0x180157e8d  call    cs:__imp_GetParent
0x180157e93  mov     this, rax; hWnd
0x180157e96  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x180157e9b  xor     r9d, r9d; lParam
0x180157e9e  mov     nFlags, 362h; Msg
0x180157ea3  mov     r8d, 0E001h; wParam
0x180157ea9  mov     this, [rax+40h]; hWnd
0x180157ead  call    cs:__imp_SendMessageW
0x180157eb3  movsxd  r14, dword ptr [rsi+1134h]
0x180157eba  or      eax, 0FFFFFFFFh
0x180157ebd  mov     r12, [rsi+40h]
0x180157ec1  mov     this, rsi
0x180157ec4  mov     [rsi+1134h], eax
0x180157eca  mov     [rsi+1138h], eax
0x180157ed0  mov     rax, [rsi]
0x180157ed3  mov     rax, [rax+6D8h]
0x180157eda  call    cs:__guard_dispatch_icall_fptr
0x180157ee0  mov     rax, [rsi]
0x180157ee3  mov     rdx, rbx
0x180157ee6  mov     this, rsi
0x180157ee9  mov     rax, [rax+730h]
0x180157ef0  call    cs:__guard_dispatch_icall_fptr
0x180157ef6  cmp     eax, r14d
0x180157ef9  jnz     loc_180157FB3
0x180157eff  mov     rax, [rsi]
0x180157f02  mov     rdx, rdi
0x180157f05  mov     this, rsi
0x180157f08  mov     rax, [rax+7E0h]
0x180157f0f  call    cs:__guard_dispatch_icall_fptr
0x180157f15  test    eax, eax
0x180157f17  jnz     loc_180157FB3
0x180157f1d  lea     eax, [r15-1]
0x180157f21  cmp     eax, 0FFFFFFFDh
0x180157f24  ja      loc_180157FB3
0x180157f2a  mov     nFlags, r14d; nIndex
0x180157f2d  mov     this, rsi; this
0x180157f30  call    ?InvalidateButton@CMFCToolBar@@QEAAPEAVCMFCToolBarButton@@H@Z; CMFCToolBar::InvalidateButton(int)
0x180157f35  mov     this, [rsi+40h]; hWnd
0x180157f39  call    cs:__imp_UpdateWindow
0x180157f3f  mov     nFlags, r15d; uiCmd
0x180157f42  lea     this, ?m_UsageCount@CMFCToolBar@@1VCMFCCmdUsageCount@@A; this
0x180157f49  call    ?AddCmd@CMFCCmdUsageCount@@QEAAXI@Z; CMFCCmdUsageCount::AddCmd(uint)
0x180157f4e  mov     rax, [rdi]
0x180157f51  mov     this, rdi
0x180157f54  mov     rax, [rax+58h]
0x180157f58  call    cs:__guard_dispatch_icall_fptr
0x180157f5e  test    eax, eax
0x180157f60  jnz     loc_180157FEA
0x180157f66  mov     this, cs:?afxUserToolsManager@@3PEAVCUserToolsManager@@EA; this
0x180157f6d  test    this, this
0x180157f70  jz      short loc_180157F7E
0x180157f72  mov     nFlags, r15d; uiCmdId
0x180157f75  call    ?InvokeTool@CUserToolsManager@@QEAAHI@Z; CUserToolsManager::InvokeTool(uint)
0x180157f7a  test    eax, eax
0x180157f7c  jnz     short loc_180157FEA
0x180157f7e  mov     rax, [rsi+0A0h]
0x180157f85  test    rax, rax
0x180157f88  jnz     short loc_180157F94
0x180157f8a  mov     this, [rsi+40h]; hWnd
0x180157f8e  call    cs:__imp_GetParent
0x180157f94  mov     this, rax; hWnd
0x180157f97  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x180157f9c  xor     r9d, r9d; lParam
0x180157f9f  mov     r8d, r15d; wParam
0x180157fa2  mov     nFlags, 111h; Msg
0x180157fa7  mov     this, [rax+40h]; hWnd
0x180157fab  call    cs:__imp_SendMessageW
0x180157fb1  jmp     short loc_180157FEA
0x180157fb3  mov     this, r12; hWnd
0x180157fb6  call    cs:__imp_IsWindow
0x180157fbc  test    eax, eax
0x180157fbe  jz      short loc_180157FEA
0x180157fc0  mov     this, r12; hWnd
0x180157fc3  call    cs:__imp_IsIconic
0x180157fc9  test    eax, eax
0x180157fcb  jnz     short loc_180157FEA
0x180157fcd  mov     this, r12; hWnd
0x180157fd0  call    cs:__imp_IsZoomed
0x180157fd6  test    eax, eax
0x180157fd8  jz      short loc_180157FEA
0x180157fda  mov     rax, [rdi]
0x180157fdd  mov     this, rdi
0x180157fe0  mov     rax, [rax+58h]
0x180157fe4  call    cs:__guard_dispatch_icall_fptr
0x180157fea  mov     this, r12; hWnd
0x180157fed  call    cs:__imp_IsWindow
0x180157ff3  test    eax, eax
0x180157ff5  jz      short loc_180158073
0x180157ff7  cmp     r14, [rsi+11A0h]
0x180157ffe  jge     short loc_180158073
0x180158000  mov     nFlags, r14d; nIndex
0x180158003  mov     this, rsi; this
0x180158006  test    r13d, r13d
0x180158009  jz      short loc_18015801C
0x18015800b  call    ?GetButton@CMFCToolBar@@QEBAPEAVCMFCToolBarButton@@H@Z; CMFCToolBar::GetButton(int)
0x180158010  test    rax, rax
0x180158013  jz      short loc_18015802F
0x180158015  btr     dword ptr [rax+28h], 11h
0x18015801a  jmp     short loc_18015802F
0x18015801c  mov     rax, [rsi]
0x18015801f  mov     r8d, ebp
0x180158022  mov     rax, [rax+6F8h]
0x180158029  call    cs:__guard_dispatch_icall_fptr
0x18015802f  mov     nFlags, r14d; nIndex
0x180158032  mov     this, rsi; this
0x180158035  call    ?UpdateButton@CMFCToolBar@@QEAAXH@Z; CMFCToolBar::UpdateButton(int)
0x18015803a  mov     nFlags, r14d; nIndex
0x18015803d  mov     this, rsi; this
0x180158040  call    ?InvalidateButton@CMFCToolBar@@QEAAPEAVCMFCToolBarButton@@H@Z; CMFCToolBar::InvalidateButton(int)
0x180158045  mov     this, [rsi+40h]; hWnd
0x180158049  call    cs:__imp_UpdateWindow
0x18015804f  or      eax, 0FFFFFFFFh
0x180158052  mov     dword ptr [rsp+48h+arg_18], eax
0x180158056  mov     dword ptr [rsp+48h+arg_18+4], eax
0x18015805a  mov     rax, [rsp+48h+arg_18]
0x18015805f  mov     point, rbx; point
0x180158062  xor     nFlags, nFlags; nFlags
0x180158064  mov     [rsi+12D8h], rax
0x18015806b  mov     this, rsi; this
0x18015806e  call    ?OnMouseMove@CMFCToolBar@@IEAAXIVCPoint@@@Z; CMFCToolBar::OnMouseMove(uint,CPoint)
0x180158073  mov     rbx, [rsp+48h+arg_0]
0x180158078  mov     rbp, [rsp+48h+arg_8]
0x18015807d  mov     rsi, [rsp+48h+arg_10]
0x180158082  add     rsp, 20h
0x180158086  pop     r15
0x180158088  pop     r14
0x18015808a  pop     r13
0x18015808c  pop     r12
0x18015808e  pop     rdi
0x18015808f  retn
```
