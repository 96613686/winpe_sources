# CMFCDragFrameImpl::MoveDragFrame(int)

- ea: `0x180057170`
- end: `0x180057707`
- name: `?MoveDragFrame@CMFCDragFrameImpl@@QEAAXH@Z`
- size: `1431`
- prototype: `void __fastcall(CMFCDragFrameImpl *this, int bForceMove)`
- caller_count: `5`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x1800177b0`
- `0x180042cd0`
- `0x1800a2c80`
- `0x1800b11d0`
- `0x1800b1cc0`

## callees

- `0x1800027e0`
- `0x180041460`
- `0x18004a670`
- `0x18004ed00`
- `0x180057170`
- `0x180057710`
- `0x1800579f0`
- `0x180057b20`
- `0x180057c30`
- `0x180057f70`
- `0x18006cab0`
- `0x18023f820`
- `0x18029a620`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!labs` at `0x1800572a0`
- `api-ms-win-crt-utility-l1-1-0!labs` at `0x1800572ad`
- `api-ms-win-crt-utility-l1-1-0!labs` at `0x1800572a0`
- `api-ms-win-crt-utility-l1-1-0!labs` at `0x1800572ad`
- `USER32!GetCursorPos` at `0x180057281`
- `USER32!GetCursorPos` at `0x180057281`
- `USER32!SetRectEmpty` at `0x180057404`
- `USER32!SetRectEmpty` at `0x180057404`
- `USER32!GetWindowRect` at `0x180057336`
- `USER32!GetWindowRect` at `0x18005737f`
- `USER32!GetWindowRect` at `0x180057336`
- `USER32!GetWindowRect` at `0x18005737f`
- `USER32!IsRectEmpty` at `0x1800572bc`
- `USER32!IsRectEmpty` at `0x1800572e6`
- `USER32!IsRectEmpty` at `0x180057309`
- `USER32!IsRectEmpty` at `0x1800575ee`
- `USER32!IsRectEmpty` at `0x180057651`
- `USER32!IsRectEmpty` at `0x1800576af`
- `USER32!IsRectEmpty` at `0x1800572bc`
- `USER32!IsRectEmpty` at `0x1800572e6`
- `USER32!IsRectEmpty` at `0x180057309`
- `USER32!IsRectEmpty` at `0x1800575ee`
- `USER32!IsRectEmpty` at `0x180057651`
- `USER32!IsRectEmpty` at `0x1800576af`
- `USER32!OffsetRect` at `0x1800573e5`
- `USER32!OffsetRect` at `0x1800575d3`
- `USER32!OffsetRect` at `0x180057691`
- `USER32!OffsetRect` at `0x1800573e5`
- `USER32!OffsetRect` at `0x1800575d3`
- `USER32!OffsetRect` at `0x180057691`
- `USER32!PtInRect` at `0x1800573cb`
- `USER32!PtInRect` at `0x180057663`
- `USER32!PtInRect` at `0x1800573cb`
- `USER32!PtInRect` at `0x180057663`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=1
void __fastcall CMFCDragFrameImpl::MoveDragFrame(CMFCDragFrameImpl *this, int bForceMove)
{
  int v4; // r15d
  CDockablePane *v5; // rax
  CDockablePane *v6; // rbx
  int (__fastcall *CreateEx)(CDockablePane *, unsigned int, const wchar_t *, CWnd *, const tagRECT *, int, unsigned int, unsigned int, unsigned int, unsigned int, CCreateContext *); // rsi
  CFrameWnd *TopLevelFrame; // rax
  int cx; // ebx
  CPoint m_ptHot; // rax
  int v11; // r13d
  int v12; // r12d
  int v13; // esi
  int IsKindOf; // eax
  CWnd *m_pDraggedWnd; // rcx
  CWnd *v16; // rbx
  CDockablePane *m_pTargetBar; // rbx
  CDockingManager *m_pDockManager; // rcx
  CSmartDockingManager *m_pSDManager; // rax
  int v20; // r14d
  CWnd *v21; // rbx
  CBaseTabbedPane *v22; // rbx
  int m_nDragFrameThicknessFloat; // ebx
  CRect m_rectDrag; // xmm0
  CPoint ptMouse; // [rsp+68h] [rbp-29h] BYREF
  CSize szSensitivity; // [rsp+70h] [rbp-21h] BYREF
  _BYTE v27[64]; // [rsp+78h] [rbp-19h] OVERLAPPED BYREF

  v4 = 0;
  this->m_pFinalTargetBar = 0;
  if ( this->m_pDraggedWnd && this->m_pDockManager )
  {
    if ( !this->m_pWndDummy )
    {
      v5 = (CDockablePane *)operator new(0x4E0u);
      v6 = v5;
      *(_QWORD *)v27 = v5;
      if ( v5 )
      {
        CDockablePane::CDockablePane(v5);
        v6->__vftable = (CDockablePane_vtbl *)CDummyDockablePane::`vftable';
      }
      else
      {
        v6 = 0;
      }
      this->m_pWndDummy = v6;
      CreateEx = v6->CreateEx;
      *(_OWORD *)v27 = 0;
      TopLevelFrame = g_pTopLevelFrame;
      if ( !g_pTopLevelFrame )
        TopLevelFrame = CWnd::GetTopLevelFrame(this->m_pDraggedWnd);
      CreateEx(v6, 0, &CmdLine, TopLevelFrame, (const tagRECT *)v27, 0, -2u, 0x40000000u, 32u, 15u, 0);
    }
    cx = CDockablePane::m_sizeDragSensitivity.cx;
    *(CSize *)v27 = CDockablePane::m_sizeDragSensitivity;
    szSensitivity = 0;
    GetCursorPos((LPPOINT)&szSensitivity);
    m_ptHot = this->m_ptHot;
    v11 = szSensitivity.cx - m_ptHot.x;
    v12 = szSensitivity.cy - m_ptHot.y;
    if ( labs(szSensitivity.cx - m_ptHot.x) >= cx
      || labs(v12) >= *(int *)&v27[4]
      || !IsRectEmpty(&this->m_rectDrag)
      || bForceMove )
    {
      this->m_bDragStarted = 1;
      CDockingManager::LockUpdate(this->m_pDockManager, 1);
      *(CRect *)&v27[48] = *(CRect *)((char *)&this->m_rectExpectedDocked
                                    + (-(__int64)IsRectEmpty(&this->m_rectExpectedDocked) & 0xFFFFFFFFFFFFFFF0uLL));
      v13 = 0;
      if ( IsRectEmpty(&this->m_rectDrag) )
      {
        IsKindOf = CObject::IsKindOf(this->m_pDraggedWnd, &CPaneFrameWnd::classCPaneFrameWnd);
        m_pDraggedWnd = this->m_pDraggedWnd;
        if ( IsKindOf )
        {
          GetWindowRect(m_pDraggedWnd->m_hWnd, &this->m_rectDrag);
        }
        else if ( CObject::IsKindOf(m_pDraggedWnd, &CPane::classCPane) )
        {
          v16 = this->m_pDraggedWnd;
          if ( !v16 || !CObject::IsKindOf(this->m_pDraggedWnd, &CPane::classCPane) )
            v16 = 0;
          GetWindowRect(this->m_pDraggedWnd->m_hWnd, &this->m_rectDrag);
          if ( !((__int64 (__fastcall *)(CWnd *, _QWORD))v16->__vftable[1].get_accHelpTopic)(v16, 0) )
          {
            this->m_rectDrag.right = LODWORD(v16[3].m_pOuterUnknown) + this->m_rectDrag.left - v16[3].m_dwRef;
            this->m_rectDrag.bottom = this->m_rectDrag.top + HIDWORD(v16[3].m_pOuterUnknown) - *(&v16[3].m_dwRef + 1);
          }
          if ( !PtInRect(&this->m_rectDrag, this->m_ptHot.tagPOINT) )
            OffsetRect(&this->m_rectDrag, this->m_ptHot.x - this->m_rectDrag.left - 5, 0);
        }
        v13 = 1;
      }
      ptMouse.x = 0;
      m_pTargetBar = this->m_pTargetBar;
      *(_OWORD *)&v27[16] = 0;
      SetRectEmpty((LPRECT)&v27[16]);
      m_pDockManager = this->m_pDockManager;
      if ( m_pDockManager )
      {
        m_pSDManager = m_pDockManager->m_pSDManager;
        if ( m_pSDManager )
        {
          if ( m_pSDManager->m_bCreated && m_pSDManager->m_bStarted )
            v4 = 1;
        }
      }
      CDockingManager::CalcExpectedDockedRect(
        m_pDockManager,
        this->m_pDraggedWnd,
        (CPoint)szSensitivity,
        (CRect *)&v27[16],
        (int *)&ptMouse,
        &this->m_pTargetBar);
      if ( m_pTargetBar && this->m_nInsertedTabID != -1 && (m_pTargetBar != this->m_pTargetBar || !ptMouse.x) )
      {
        CMFCDragFrameImpl::RemoveTabPreDocking(this, m_pTargetBar);
        v13 = 1;
      }
      v20 = 1;
      if ( !CObject::IsKindOf(this->m_pDraggedWnd, &CPaneFrameWnd::classCPaneFrameWnd)
        && CObject::IsKindOf(this->m_pDraggedWnd, &CPane::classCPane) )
      {
        v21 = this->m_pDraggedWnd;
        if ( !v21 || !CObject::IsKindOf(this->m_pDraggedWnd, &CPane::classCPane) )
          v21 = 0;
        v20 = (int)v21->__vftable[1].GetTypeLibCache(v21);
      }
      v22 = (CBaseTabbedPane *)this->m_pTargetBar;
      if ( v22 && v20 )
      {
        if ( !CObject::IsKindOf(&this->m_pTargetBar->CPane, &CBaseTabbedPane::classCBaseTabbedPane) )
          goto LABEL_51;
        if ( ptMouse.x )
        {
          if ( v22->GetVisibleTabsNum(v22) > 1 && v22->IsHideSingleTab(v22)
            || v22->GetVisibleTabsNum(v22) > 0 && !v22->IsHideSingleTab(v22) )
          {
            CMFCDragFrameImpl::PlaceTabPreDocking(this, v22, v13);
            return;
          }
LABEL_51:
          if ( ptMouse.x )
          {
            if ( this->m_nInsertedTabID == -1 )
            {
              if ( !v13 )
                CMFCDragFrameImpl::EndDrawDragFrame(this, 0);
              CMFCDragFrameImpl::DrawFrameTab(this, this->m_pTargetBar, 0);
              this->m_nInsertedTabID = 1;
            }
            return;
          }
        }
      }
      OffsetRect(&this->m_rectDrag, v11, v12);
      this->m_ptHot = (CPoint)szSensitivity;
      this->m_rectExpectedDocked = *(CRect *)&v27[16];
      if ( IsRectEmpty(&this->m_rectExpectedDocked) )
      {
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          afxGlobalData.m_bInitialized = 1;
        }
        m_nDragFrameThicknessFloat = afxGlobalData.m_nDragFrameThicknessFloat;
      }
      else
      {
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          afxGlobalData.m_bInitialized = 1;
        }
        m_nDragFrameThicknessFloat = afxGlobalData.m_nDragFrameThicknessDock;
      }
      *(_OWORD *)&v27[32] = 0;
      if ( IsRectEmpty(&this->m_rectExpectedDocked) )
      {
        if ( !PtInRect(&this->m_rectDrag, (POINT)szSensitivity) )
          OffsetRect(
            &this->m_rectDrag,
            szSensitivity.cx - (this->m_rectDrag.left + (this->m_rectDrag.right - this->m_rectDrag.left) / 2),
            szSensitivity.cy - (this->m_rectDrag.top + 5));
        m_rectDrag = this->m_rectDrag;
      }
      else
      {
        m_rectDrag = this->m_rectExpectedDocked;
      }
      *(CRect *)&v27[32] = m_rectDrag;
      if ( !v4 || !IsRectEmpty(&this->m_rectExpectedDocked) )
      {
        CMFCDragFrameImpl::DrawDragFrame(
          this,
          (const tagRECT *)&v27[48],
          (const tagRECT *)&v27[32],
          v13,
          m_nDragFrameThicknessFloat,
          this->m_nOldThickness);
        this->m_nOldThickness = m_nDragFrameThicknessFloat;
      }
    }
  }
}

```

## disassembly

```asm
0x180057170  mov     rax, rsp
0x180057173  mov     [rax+10h], rbx
0x180057177  mov     [rax+18h], rsi
0x18005717b  mov     [rax+20h], rdi
0x18005717f  push    rbp
0x180057180  push    r12
0x180057182  push    r13
0x180057184  push    r14
0x180057186  push    r15
0x180057188  lea     rbp, [rax-5Fh]
0x18005718c  sub     rsp, 0C0h
0x180057193  mov     rax, cs:__security_cookie
0x18005719a  xor     rax, rsp
0x18005719d  mov     [rbp+57h+var_30], rax
0x1800571a1  mov     r14d, bForceMove
0x1800571a4  mov     rdi, this
0x1800571a7  xor     r15d, r15d
0x1800571aa  mov     [this+40h], r15
0x1800571ae  cmp     [this+58h], r15
0x1800571b2  jz      loc_1800576DA
0x1800571b8  cmp     [this+60h], r15
0x1800571bc  jz      loc_1800576DA
0x1800571c2  cmp     [this+70h], r15
0x1800571c6  jnz     loc_18005726E
0x1800571cc  mov     ecx, 4E0h; nSize
0x1800571d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800571d6  mov     rbx, rax
0x1800571d9  mov     [rbp+57h+var_70], rax
0x1800571dd  test    rax, rax
0x1800571e0  jz      short loc_1800571F6
0x1800571e2  mov     this, rax; this
0x1800571e5  call    ??0CDockablePane@@QEAA@XZ; CDockablePane::CDockablePane(void)
0x1800571ea  lea     rax, ??_7CDummyDockablePane@@6B@; const CDummyDockablePane::`vftable'
0x1800571f1  mov     [rbx], rax
0x1800571f4  jmp     short loc_1800571F9
0x1800571f6  mov     rbx, r15
0x1800571f9  mov     [rdi+70h], rbx
0x1800571fd  mov     rax, [rbx]
0x180057200  mov     rsi, [rax+660h]
0x180057207  xorps   xmm0, xmm0
0x18005720a  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18005720e  mov     rax, cs:?g_pTopLevelFrame@@3PEAVCFrameWnd@@EA; CFrameWnd * g_pTopLevelFrame
0x180057215  test    rax, rax
0x180057218  jnz     short loc_180057223
0x18005721a  mov     this, [rdi+58h]; this
0x18005721e  call    ?GetTopLevelFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ; CWnd::GetTopLevelFrame(void)
0x180057223  mov     [rsp+0E0h+var_90], r15
0x180057228  mov     dword ptr [rsp+0E0h+var_98], 0Fh
0x180057230  mov     [rsp+0E0h+var_A0], 20h ; ' '
0x180057238  mov     [rsp+0E0h+var_A8], 40000000h
0x180057240  mov     [rsp+0E0h+var_B0], 0FFFFFFFEh
0x180057248  mov     dword ptr [rsp+0E0h+ppTargetBar], r15d
0x18005724d  lea     this, [rbp+57h+var_70]
0x180057251  mov     [rsp+0E0h+var_C0], this
0x180057256  mov     r9, rax
0x180057259  lea     r8, CmdLine
0x180057260  xor     bForceMove, bForceMove
0x180057262  mov     this, rbx
0x180057265  mov     rax, rsi
0x180057268  call    cs:__guard_dispatch_icall_fptr
0x18005726e  mov     rbx, qword ptr cs:?m_sizeDragSensitivity@CDockablePane@@1VCSize@@A.cx; CSize CDockablePane::m_sizeDragSensitivity ...
0x180057275  mov     [rbp+57h+var_70], rbx
0x180057279  mov     qword ptr [rbp+57h+szSensitivity.cx], r15
0x18005727d  lea     this, [rbp+57h+szSensitivity]; lpPoint
0x180057281  call    cs:__imp_GetCursorPos
0x180057287  mov     rax, [rdi+8]
0x18005728b  mov     r13d, [rbp+57h+szSensitivity.cx]
0x18005728f  sub     r13d, eax
0x180057292  shr     rax, 20h
0x180057296  mov     r12d, [rbp+57h+szSensitivity.cy]
0x18005729a  sub     r12d, eax
0x18005729d  mov     ecx, r13d; Number
0x1800572a0  call    cs:__imp_labs
0x1800572a6  cmp     eax, ebx
0x1800572a8  jge     short loc_1800572CF
0x1800572aa  mov     ecx, r12d; Number
0x1800572ad  call    cs:__imp_labs
0x1800572b3  cmp     eax, dword ptr [rbp+57h+var_70+4]
0x1800572b6  jge     short loc_1800572CF
0x1800572b8  lea     this, [rdi+10h]; lprc
0x1800572bc  call    cs:__imp_IsRectEmpty
0x1800572c2  test    eax, eax
0x1800572c4  jz      short loc_1800572CF
0x1800572c6  test    r14d, r14d
0x1800572c9  jz      loc_1800576DA
0x1800572cf  mov     eax, 1
0x1800572d4  mov     [rdi+34h], eax
0x1800572d7  mov     bForceMove, eax; bLock
0x1800572d9  mov     this, [rdi+60h]; this
0x1800572dd  call    ?LockUpdate@CDockingManager@@QEAAXH@Z; CDockingManager::LockUpdate(int)
0x1800572e2  lea     this, [rdi+20h]; lprc
0x1800572e6  call    cs:__imp_IsRectEmpty
0x1800572ec  lea     r14, [rdi+10h]
0x1800572f0  neg     eax
0x1800572f2  sbb     this, this
0x1800572f5  and     this, 0FFFFFFFFFFFFFFF0h
0x1800572f9  movups  xmm0, xmmword ptr [this+rdi+20h]
0x1800572fe  movdqu  xmmword ptr [rbp+57h+rectOld.right], xmm0
0x180057303  mov     esi, r15d
0x180057306  mov     this, r14; lprc
0x180057309  call    cs:__imp_IsRectEmpty
0x18005730f  test    eax, eax
0x180057311  jz      loc_1800573F0
0x180057317  lea     rdx, ?classCPaneFrameWnd@CPaneFrameWnd@@2UCRuntimeClass@@A; pClass
0x18005731e  mov     this, [rdi+58h]; this
0x180057322  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180057327  mov     this, [rdi+58h]; this
0x18005732b  test    eax, eax
0x18005732d  jz      short loc_180057341
0x18005732f  mov     rdx, r14; lpRect
0x180057332  mov     this, [this+40h]; hWnd
0x180057336  call    cs:__imp_GetWindowRect
0x18005733c  jmp     loc_1800573EB
0x180057341  lea     rdx, ?classCPane@CPane@@2UCRuntimeClass@@B; pClass
0x180057348  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18005734d  test    eax, eax
0x18005734f  jz      loc_1800573EB
0x180057355  mov     rbx, [rdi+58h]
0x180057359  test    rbx, rbx
0x18005735c  jz      short loc_180057371
0x18005735e  lea     rdx, ?classCPane@CPane@@2UCRuntimeClass@@B; pClass
0x180057365  mov     this, rbx; this
0x180057368  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18005736d  test    eax, eax
0x18005736f  jnz     short loc_180057374
0x180057371  mov     rbx, r15
0x180057374  mov     this, [rdi+58h]
0x180057378  mov     rdx, r14; lpRect
0x18005737b  mov     this, [this+40h]; hWnd
0x18005737f  call    cs:__imp_GetWindowRect
0x180057385  mov     rax, [rbx]
0x180057388  xor     bForceMove, bForceMove
0x18005738a  mov     this, rbx
0x18005738d  mov     rax, [rax+460h]
0x180057394  call    cs:__guard_dispatch_icall_fptr
0x18005739a  test    rax, rax
0x18005739d  jnz     short loc_1800573C3
0x18005739f  mov     eax, [rdi+10h]
0x1800573a2  add     eax, [rbx+2C8h]
0x1800573a8  sub     eax, [rbx+2C0h]
0x1800573ae  mov     [rdi+18h], eax
0x1800573b1  mov     eax, [rbx+2CCh]
0x1800573b7  sub     eax, [rbx+2C4h]
0x1800573bd  add     eax, [rdi+14h]
0x1800573c0  mov     [rdi+1Ch], eax
0x1800573c3  lea     this, [rdi+10h]; lprc
0x1800573c7  mov     rdx, [rdi+8]; pt
0x1800573cb  call    cs:__imp_PtInRect
0x1800573d1  test    eax, eax
0x1800573d3  jnz     short loc_1800573EB
0x1800573d5  mov     bForceMove, [rdi+8]
0x1800573d8  sub     bForceMove, [rdi+10h]
0x1800573db  sub     bForceMove, 5; dx
0x1800573de  lea     this, [rdi+10h]; lprc
0x1800573e2  xor     r8d, r8d; dy
0x1800573e5  call    cs:__imp_OffsetRect
0x1800573eb  mov     esi, 1
0x1800573f0  mov     [rbp+57h+ptMouse.x], r15d
0x1800573f4  mov     rbx, [rdi+68h]
0x1800573f8  xorps   xmm0, xmm0
0x1800573fb  movdqu  xmmword ptr [rbp+57h+rectExpected.right], xmm0
0x180057400  lea     this, [rbp+57h+rectExpected.right]; lprc
0x180057404  call    cs:__imp_SetRectEmpty
0x18005740a  mov     this, [rdi+60h]; this
0x18005740e  xor     r14d, r14d
0x180057411  test    this, this
0x180057414  jz      short loc_180057434
0x180057416  mov     rax, [this+308h]
0x18005741d  test    rax, rax
0x180057420  jz      short loc_180057434
0x180057422  cmp     [rax+0Ch], r14d
0x180057426  jz      short loc_180057434
0x180057428  cmp     [rax+8], r14d
0x18005742c  lea     eax, [r14+1]
0x180057430  cmovnz  r15d, eax
0x180057434  lea     rax, [rdi+68h]
0x180057438  mov     [rsp+0E0h+ppTargetBar], rax; ppTargetBar
0x18005743d  lea     rax, [rbp+57h+ptMouse]
0x180057441  mov     [rsp+0E0h+var_C0], rax; bDrawTab
0x180057446  lea     r9, [rbp+57h+rectExpected.right]; rectResult
0x18005744a  mov     r8, qword ptr [rbp+57h+szSensitivity.cx]; ptMouse
0x18005744e  mov     rdx, [rdi+58h]; pWnd
0x180057452  call    ?CalcExpectedDockedRect@CDockingManager@@QEAAXPEAVCWnd@@VCPoint@@AEAVCRect@@AEAHPEAPEAVCDockablePane@@@Z; CDockingManager::CalcExpectedDockedRect(CWnd *,CPoint,CRect &,int &,CDockablePane * *)
0x180057457  test    rbx, rbx
0x18005745a  jz      short loc_18005747E
0x18005745c  cmp     dword ptr [rdi+38h], 0FFFFFFFFh
0x180057460  jz      short loc_18005747E
0x180057462  cmp     rbx, [rdi+68h]
0x180057466  jnz     short loc_18005746E
0x180057468  cmp     [rbp+57h+ptMouse.x], r14d
0x18005746c  jnz     short loc_18005747E
0x18005746e  mov     rdx, rbx; pOldTargetBar
0x180057471  mov     this, rdi; this
0x180057474  call    ?RemoveTabPreDocking@CMFCDragFrameImpl@@QEAAXPEAVCDockablePane@@@Z; CMFCDragFrameImpl::RemoveTabPreDocking(CDockablePane *)
0x180057479  mov     esi, 1
0x18005747e  mov     r14d, 1
0x180057484  lea     rdx, ?classCPaneFrameWnd@CPaneFrameWnd@@2UCRuntimeClass@@A; pClass
0x18005748b  mov     this, [rdi+58h]; this
0x18005748f  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180057494  test    eax, eax
0x180057496  jnz     short loc_1800574E0
0x180057498  lea     rdx, ?classCPane@CPane@@2UCRuntimeClass@@B; pClass
0x18005749f  mov     this, [rdi+58h]; this
0x1800574a3  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1800574a8  test    eax, eax
0x1800574aa  jz      short loc_1800574E0
0x1800574ac  mov     rbx, [rdi+58h]
0x1800574b0  test    rbx, rbx
0x1800574b3  jz      short loc_1800574C8
0x1800574b5  lea     rdx, ?classCPane@CPane@@2UCRuntimeClass@@B; pClass
0x1800574bc  mov     this, rbx; this
0x1800574bf  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1800574c4  test    eax, eax
0x1800574c6  jnz     short loc_1800574CA
0x1800574c8  xor     ebx, ebx
0x1800574ca  mov     rax, [rbx]
0x1800574cd  mov     this, rbx
0x1800574d0  mov     rax, [rax+328h]
0x1800574d7  call    cs:__guard_dispatch_icall_fptr
0x1800574dd  mov     r14d, eax
0x1800574e0  mov     rbx, [rdi+68h]
0x1800574e4  test    rbx, rbx
0x1800574e7  jz      loc_1800575C9
0x1800574ed  test    r14d, r14d
0x1800574f0  jz      loc_1800575C9
0x1800574f6  lea     rdx, ?classCBaseTabbedPane@CBaseTabbedPane@@2UCRuntimeClass@@B; pClass
0x1800574fd  mov     this, rbx; this
0x180057500  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180057505  test    eax, eax
0x180057507  jz      loc_18005758D
0x18005750d  cmp     [rbp+57h+ptMouse.x], 0
0x180057511  jz      loc_1800575C9
0x180057517  mov     rax, [rbx]
0x18005751a  mov     this, rbx
0x18005751d  mov     rax, [rax+760h]
0x180057524  call    cs:__guard_dispatch_icall_fptr
0x18005752a  mov     r14d, 1
0x180057530  cmp     eax, r14d
0x180057533  jle     short loc_18005754C
0x180057535  mov     rax, [rbx]
0x180057538  mov     this, rbx
0x18005753b  mov     rax, [rax+768h]
0x180057542  call    cs:__guard_dispatch_icall_fptr
0x180057548  test    eax, eax
0x18005754a  jnz     short loc_18005757A
0x18005754c  mov     rax, [rbx]
0x18005754f  mov     this, rbx
0x180057552  mov     rax, [rax+760h]
0x180057559  call    cs:__guard_dispatch_icall_fptr
0x18005755f  test    eax, eax
0x180057561  jle     short loc_180057593
0x180057563  mov     rax, [rbx]
0x180057566  mov     this, rbx
0x180057569  mov     rax, [rax+768h]
0x180057570  call    cs:__guard_dispatch_icall_fptr
0x180057576  test    eax, eax
0x180057578  jnz     short loc_180057593
0x18005757a  mov     r8d, esi; bFirstTime
0x18005757d  mov     rdx, rbx; pTabbedBar
0x180057580  mov     this, rdi; this
0x180057583  call    ?PlaceTabPreDocking@CMFCDragFrameImpl@@QEAAXPEAVCBaseTabbedPane@@H@Z; CMFCDragFrameImpl::PlaceTabPreDocking(CBaseTabbedPane *,int)
0x180057588  jmp     loc_1800576DA
0x18005758d  mov     r14d, 1
0x180057593  cmp     [rbp+57h+ptMouse.x], 0
0x180057597  jz      short loc_1800575C9
0x180057599  cmp     dword ptr [rdi+38h], 0FFFFFFFFh
0x18005759d  jnz     loc_1800576DA
0x1800575a3  test    esi, esi
0x1800575a5  jnz     short loc_1800575B1
0x1800575a7  xor     bForceMove, bForceMove; bClearInternalRects
0x1800575a9  mov     this, rdi; this
0x1800575ac  call    ?EndDrawDragFrame@CMFCDragFrameImpl@@QEAAXH@Z; CMFCDragFrameImpl::EndDrawDragFrame(int)
0x1800575b1  xor     r8d, r8d; bErase
0x1800575b4  mov     rdx, [rdi+68h]; pTargetBar
0x1800575b8  mov     this, rdi; this
0x1800575bb  call    ?DrawFrameTab@CMFCDragFrameImpl@@IEAAXPEAVCDockablePane@@H@Z; CMFCDragFrameImpl::DrawFrameTab(CDockablePane *,int)
0x1800575c0  mov     [rdi+38h], r14d
0x1800575c4  jmp     loc_1800576DA
0x1800575c9  lea     this, [rdi+10h]; lprc
0x1800575cd  mov     r8d, r12d; dy
0x1800575d0  mov     bForceMove, r13d; dx
0x1800575d3  call    cs:__imp_OffsetRect
0x1800575d9  mov     rax, qword ptr [rbp+57h+szSensitivity.cx]
0x1800575dd  mov     [rdi+8], rax
0x1800575e1  movups  xmm0, xmmword ptr [rbp+57h+rectExpected.right]
0x1800575e5  movdqu  xmmword ptr [rdi+20h], xmm0
0x1800575ea  lea     this, [rdi+20h]; lprc
0x1800575ee  call    cs:__imp_IsRectEmpty
0x1800575f4  test    eax, eax
0x1800575f6  jz      short loc_180057620
0x1800575f8  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x1800575ff  jnz     short loc_180057618
0x180057601  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180057608  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18005760d  mov     eax, 1
0x180057612  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, eax; AFX_GLOBAL_DATA afxGlobalData ...
0x180057618  mov     ebx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nDragFrameThicknessFloat; AFX_GLOBAL_DATA afxGlobalData ...
0x18005761e  jmp     short loc_180057646
0x180057620  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x180057627  jnz     short loc_180057640
  ... truncated ...
```
