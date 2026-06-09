# CMFCTabCtrl::OnLButtonDown(uint,CPoint)

- ea: `0x18013f5e0`
- end: `0x18013f7f2`
- name: `?OnLButtonDown@CMFCTabCtrl@@IEAAXIVCPoint@@@Z`
- size: `530`
- prototype: `void __fastcall(CMFCTabCtrl *this, unsigned int nFlags, CPoint point)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180017dd0`
- `0x18013f5e0`
- `0x180143120`
- `0x180296d00`
- `0x1802afe10`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!SetRectEmpty` at `0x18013f6fc`
- `USER32!SetRectEmpty` at `0x18013f6fc`
- `USER32!SendMessageW` at `0x18013f68d`
- `USER32!SendMessageW` at `0x18013f7cc`
- `USER32!SendMessageW` at `0x18013f68d`
- `USER32!SendMessageW` at `0x18013f7cc`
- `USER32!CopyRect` at `0x18013f6a4`
- `USER32!CopyRect` at `0x18013f6a4`
- `USER32!MapWindowPoints` at `0x18013f7aa`
- `USER32!MapWindowPoints` at `0x18013f7aa`
- `USER32!SetCapture` at `0x18013f62e`
- `USER32!SetCapture` at `0x18013f6ca`
- `USER32!SetCapture` at `0x18013f62e`
- `USER32!SetCapture` at `0x18013f6ca`
- `USER32!IsRectEmpty` at `0x18013f6b2`
- `USER32!IsRectEmpty` at `0x18013f6b2`
- `USER32!GetParent` at `0x18013f66e`
- `USER32!GetParent` at `0x18013f66e`
- `USER32!PtInRect` at `0x18013f616`
- `USER32!PtInRect` at `0x18013f65c`
- `USER32!PtInRect` at `0x18013f616`
- `USER32!PtInRect` at `0x18013f65c`

## pseudocode

```c
void __fastcall CMFCTabCtrl::OnLButtonDown(CMFCTabCtrl *this, unsigned int nFlags, CPoint point)
{
  WPARAM v3; // r14
  HWND__ *m_hWnd; // rcx
  HWND v6; // rax
  HWND Parent; // rax
  CWnd *v8; // rax
  LRESULT v9; // rbx
  HWND__ *v10; // rcx
  HWND v11; // rax
  int v12; // eax
  CWnd *v13; // rax
  CWnd *v14; // rbx
  CRect rectEmpty; // [rsp+20h] [rbp-30h] BYREF
  tagRECT rectBounds; // [rsp+30h] [rbp-20h] BYREF
  POINT pt; // [rsp+90h] [rbp+40h] BYREF

  pt = point.tagPOINT;
  v3 = nFlags;
  if ( PtInRect(&this->m_rectTabSplitter, point.tagPOINT) )
  {
    m_hWnd = this->m_hWnd;
    this->m_bTrackSplitter = 1;
    v6 = SetCapture(m_hWnd);
    CWnd::FromHandle(v6);
  }
  else if ( this->m_ResizeMode
         && PtInRect(&this->m_rectResize, pt)
         && (Parent = GetParent(this->m_hWnd),
             v8 = CWnd::FromHandle(Parent),
             v9 = SendMessageW(v8->m_hWnd, AFX_WM_GETDRAGBOUNDS, (WPARAM)this, (LPARAM)&rectBounds),
             CopyRect(&this->m_rectResizeBounds, &rectBounds),
             v9)
         && !IsRectEmpty(&this->m_rectResizeBounds) )
  {
    v10 = this->m_hWnd;
    this->m_bResize = 1;
    v11 = SetCapture(v10);
    CWnd::FromHandle(v11);
    this->m_rectResizeDrag = this->m_rectResize;
    CWnd::ClientToScreen(this, &this->m_rectResizeDrag);
    rectEmpty = 0;
    SetRectEmpty(&rectEmpty);
    this->DrawResizeDragRect(this, &this->m_rectResizeDrag, &rectEmpty);
  }
  else
  {
    if ( this->IsMDITabGroup(this) )
    {
      v12 = this->GetTabFromPoint(this, (CPoint *)&pt);
      if ( v12 == this->m_iActiveTab )
        CMFCTabCtrl::ActivateMDITab(this, v12);
    }
    CMFCBaseTabCtrl::OnLButtonDown(this, v3, (CPoint)pt);
    if ( !this->m_bReadyToDetach )
    {
      v13 = this->FindTargetWnd(this, &pt);
      v14 = v13;
      if ( v13 )
      {
        MapWindowPoints(this->m_hWnd, v13->m_hWnd, &pt, 1u);
        SendMessageW(v14->m_hWnd, 0x201u, v3, LOWORD(pt.x) | (unsigned __int64)(LOWORD(pt.y) << 16));
      }
    }
  }
}

```

## disassembly

```asm
0x18013f5e0  mov     [rsp-28h+arg_18], rbx
0x18013f5e5  mov     qword ptr [rsp-28h+pt.x], point
0x18013f5ea  push    rbp
0x18013f5eb  push    rsi
0x18013f5ec  push    rdi
0x18013f5ed  push    r14
0x18013f5ef  push    r15
0x18013f5f1  mov     rbp, rsp
0x18013f5f4  sub     rsp, 50h
0x18013f5f8  mov     rax, cs:__security_cookie
0x18013f5ff  xor     rax, rsp
0x18013f602  mov     [rbp+var_10], rax
0x18013f606  mov     r14d, nFlags
0x18013f609  mov     rdi, this
0x18013f60c  add     this, 42Ch; lprc
0x18013f613  mov     rdx, point; pt
0x18013f616  call    cs:__imp_PtInRect
0x18013f61c  test    eax, eax
0x18013f61e  jz      short loc_18013F641
0x18013f620  mov     this, [rdi+40h]; hWnd
0x18013f624  mov     dword ptr [rdi+3DCh], 1
0x18013f62e  call    cs:__imp_SetCapture
0x18013f634  mov     this, rax; hWnd
0x18013f637  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18013f63c  jmp     loc_18013F7D2
0x18013f641  cmp     dword ptr [rdi+3D28h], 0
0x18013f648  jz      loc_18013F721
0x18013f64e  mov     rdx, qword ptr [rbp+pt.x]; pt
0x18013f652  lea     rsi, [rdi+46Ch]
0x18013f659  mov     this, rsi; lprc
0x18013f65c  call    cs:__imp_PtInRect
0x18013f662  test    eax, eax
0x18013f664  jz      loc_18013F721
0x18013f66a  mov     this, [rdi+40h]; hWnd
0x18013f66e  call    cs:__imp_GetParent
0x18013f674  mov     this, rax; hWnd
0x18013f677  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18013f67c  mov     nFlags, cs:?AFX_WM_GETDRAGBOUNDS@@3IA; Msg
0x18013f682  lea     r9, [rbp+rectBounds]; lParam
0x18013f686  mov     point, rdi; wParam
0x18013f689  mov     this, [rax+40h]; hWnd
0x18013f68d  call    cs:__imp_SendMessageW
0x18013f693  lea     r15, [rdi+48Ch]
0x18013f69a  mov     rbx, rax
0x18013f69d  mov     this, r15; lprcDst
0x18013f6a0  lea     rdx, [rbp+rectBounds]; lprcSrc
0x18013f6a4  call    cs:__imp_CopyRect
0x18013f6aa  test    rbx, rbx
0x18013f6ad  jz      short loc_18013F721
0x18013f6af  mov     this, r15; lprc
0x18013f6b2  call    cs:__imp_IsRectEmpty
0x18013f6b8  test    eax, eax
0x18013f6ba  jnz     short loc_18013F721
0x18013f6bc  mov     this, [rdi+40h]; hWnd
0x18013f6c0  mov     dword ptr [rdi+40Ch], 1
0x18013f6ca  call    cs:__imp_SetCapture
0x18013f6d0  mov     this, rax; hWnd
0x18013f6d3  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18013f6d8  movups  xmm0, xmmword ptr [rsi]
0x18013f6db  lea     rbx, [rdi+47Ch]
0x18013f6e2  mov     this, rdi; this
0x18013f6e5  mov     rdx, rbx; lpRect
0x18013f6e8  movdqu  xmmword ptr [rbx], xmm0
0x18013f6ec  call    ?ClientToScreen@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ClientToScreen(tagRECT *)
0x18013f6f1  xorps   xmm0, xmm0
0x18013f6f4  lea     this, [rbp+rectEmpty]; lprc
0x18013f6f8  movups  xmmword ptr [rbp+rectEmpty.left], xmm0
0x18013f6fc  call    cs:__imp_SetRectEmpty
0x18013f702  mov     rax, [rdi]
0x18013f705  lea     point, [rbp+rectEmpty]
0x18013f709  mov     rdx, rbx
0x18013f70c  mov     this, rdi
0x18013f70f  mov     rax, [rax+608h]
0x18013f716  call    cs:__guard_dispatch_icall_fptr
0x18013f71c  jmp     loc_18013F7D2
0x18013f721  mov     rax, [rdi]
0x18013f724  mov     this, rdi
0x18013f727  mov     rax, [rax+5F0h]
0x18013f72e  call    cs:__guard_dispatch_icall_fptr
0x18013f734  test    eax, eax
0x18013f736  jz      short loc_18013F761
0x18013f738  mov     rax, [rdi]
0x18013f73b  lea     rdx, [rbp+pt]
0x18013f73f  mov     this, rdi
0x18013f742  mov     rax, [rax+440h]
0x18013f749  call    cs:__guard_dispatch_icall_fptr
0x18013f74f  cmp     eax, [rdi+154h]
0x18013f755  jnz     short loc_18013F761
0x18013f757  mov     nFlags, eax; nTab
0x18013f759  mov     this, rdi; this
0x18013f75c  call    ?ActivateMDITab@CMFCTabCtrl@@QEAAXH@Z; CMFCTabCtrl::ActivateMDITab(int)
0x18013f761  mov     point, qword ptr [rbp+pt.x]; point
0x18013f765  mov     nFlags, r14d; nFlags
0x18013f768  mov     this, rdi; this
0x18013f76b  call    ?OnLButtonDown@CMFCBaseTabCtrl@@IEAAXIVCPoint@@@Z; CMFCBaseTabCtrl::OnLButtonDown(uint,CPoint)
0x18013f770  cmp     dword ptr [rdi+234h], 0
0x18013f777  jnz     short loc_18013F7D2
0x18013f779  mov     rax, [rdi]
0x18013f77c  lea     rdx, [rbp+pt]
0x18013f780  mov     this, rdi
0x18013f783  mov     rax, [rax+4A8h]
0x18013f78a  call    cs:__guard_dispatch_icall_fptr
0x18013f790  mov     rbx, rax
0x18013f793  test    rax, rax
0x18013f796  jz      short loc_18013F7D2
0x18013f798  mov     rdx, [rax+40h]; hWndTo
0x18013f79c  lea     point, [rbp+pt]; lpPoints
0x18013f7a0  mov     this, [rdi+40h]; hWndFrom
0x18013f7a4  mov     r9d, 1; cPoints
0x18013f7aa  call    cs:__imp_MapWindowPoints
0x18013f7b0  movzx   r9d, word ptr [rbp+pt.y]
0x18013f7b5  mov     point, r14; wParam
0x18013f7b8  movzx   eax, word ptr [rbp+pt.x]
0x18013f7bc  mov     nFlags, 201h; Msg
0x18013f7c1  mov     this, [rbx+40h]; hWnd
0x18013f7c5  shl     r9d, 10h
0x18013f7c9  or      r9, rax; lParam
0x18013f7cc  call    cs:__imp_SendMessageW
0x18013f7d2  mov     this, [rbp+var_10]
0x18013f7d6  xor     this, rsp; StackCookie
0x18013f7d9  call    __security_check_cookie
0x18013f7de  mov     rbx, [rsp+50h+arg_18]
0x18013f7e6  add     rsp, 50h
0x18013f7ea  pop     r15
0x18013f7ec  pop     r14
0x18013f7ee  pop     rdi
0x18013f7ef  pop     rsi
0x18013f7f0  pop     rbp
0x18013f7f1  retn
```
