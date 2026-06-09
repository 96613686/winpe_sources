# CMFCTasksPane::AdjustScroll(void)

- ea: `0x18014e820`
- end: `0x18014ec48`
- name: `?AdjustScroll@CMFCTasksPane@@IEAAXXZ`
- size: `1064`
- prototype: `void __fastcall(CMFCTasksPane *this)`
- caller_count: `26`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x18014ac40`
- `0x18014bc80`
- `0x18014bf90`
- `0x18014c400`
- `0x18014c660`
- `0x18014c700`
- `0x18014c7d0`
- `0x18014c960`
- `0x18014c9c0`
- `0x18014ca30`
- `0x18014cb40`
- `0x18014cda0`
- `0x18014ced0`
- `0x18014cfd0`
- `0x18014d1d0`
- `0x18014d2d0`
- `0x18014d420`
- `0x18014d5e0`
- `0x18014dd20`
- `0x18014e230`
- `0x18014e530`
- `0x18014efb0`
- `0x18014f5d0`
- `0x1801508d0`
- `0x180150be0`
- `0x1801520d0`

## callees

- `0x18000cb30`
- `0x18014e610`
- `0x18014e820`
- `0x18023f820`
- `0x1802b66c0`
- `0x1802b6730`
- `0x1802b6790`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x18014ea01`
- `USER32!GetSystemMetrics` at `0x18014ea01`
- `USER32!GetClientRect` at `0x18014e871`
- `USER32!GetClientRect` at `0x18014e871`
- `USER32!KillTimer` at `0x18014eb46`
- `USER32!KillTimer` at `0x18014eb46`
- `USER32!SetRectEmpty` at `0x18014e9a5`
- `USER32!SetRectEmpty` at `0x18014ea83`
- `USER32!SetRectEmpty` at `0x18014ea8c`
- `USER32!SetRectEmpty` at `0x18014e9a5`
- `USER32!SetRectEmpty` at `0x18014ea83`
- `USER32!SetRectEmpty` at `0x18014ea8c`
- `USER32!InvalidateRect` at `0x18014eb76`
- `USER32!InvalidateRect` at `0x18014eb87`
- `USER32!InvalidateRect` at `0x18014ebb9`
- `USER32!InvalidateRect` at `0x18014ebcd`
- `USER32!InvalidateRect` at `0x18014ebf6`
- `USER32!InvalidateRect` at `0x18014ec0a`
- `USER32!InvalidateRect` at `0x18014eb76`
- `USER32!InvalidateRect` at `0x18014eb87`
- `USER32!InvalidateRect` at `0x18014ebb9`
- `USER32!InvalidateRect` at `0x18014ebcd`
- `USER32!InvalidateRect` at `0x18014ebf6`
- `USER32!InvalidateRect` at `0x18014ec0a`
- `USER32!EqualRect` at `0x18014eb5e`
- `USER32!EqualRect` at `0x18014eba4`
- `USER32!EqualRect` at `0x18014ebe1`
- `USER32!EqualRect` at `0x18014eb5e`
- `USER32!EqualRect` at `0x18014eba4`
- `USER32!EqualRect` at `0x18014ebe1`
- `USER32!InflateRect` at `0x18014e89a`
- `USER32!InflateRect` at `0x18014e89a`
- `USER32!UpdateWindow` at `0x18014eb91`
- `USER32!UpdateWindow` at `0x18014ec1a`
- `USER32!UpdateWindow` at `0x18014eb91`
- `USER32!UpdateWindow` at `0x18014ec1a`

## pseudocode

```c
void __fastcall CMFCTasksPane::AdjustScroll(CMFCTasksPane *this)
{
  HWND__ *m_hWnd; // rcx
  bool v3; // zf
  CRect *p_m_rectToolbar; // rbx
  __int64 m_nCount; // r14
  CBaseTabbedPane *ParentTabbedPane; // r15
  CPaneFrameWnd *v7; // rax
  int v8; // eax
  CMFCTasksPaneToolBar *p_m_wndToolBar; // r14
  CSize *v10; // rax
  __m128i v11; // xmm0
  int v12; // edx
  __int64 left; // r8
  int v14; // edx
  int SystemMetrics; // eax
  int top; // r9d
  int v17; // ebx
  int right; // r8d
  int cy; // ecx
  CRect m_rectScrollDn; // xmm1
  int m_nVertScrollOffset; // edx
  CRect v22; // xmm0
  int m_iScrollBtnHeight; // ecx
  CRect v24; // xmm0
  int v25; // ecx
  int v26; // ebx
  _BYTE v27[8]; // [rsp+50h] [rbp-19h] BYREF
  tagRECT Rect; // [rsp+58h] [rbp-11h] BYREF
  RECT rc1; // [rsp+68h] [rbp-1h] BYREF
  RECT m_rectScrollUp; // [rsp+78h] [rbp+Fh] BYREF
  RECT v31; // [rsp+88h] [rbp+1Fh] BYREF

  if ( this )
  {
    m_hWnd = this->m_hWnd;
    if ( m_hWnd )
    {
      Rect = 0;
      GetClientRect(m_hWnd, &Rect);
      if ( this->IsToolBox(this) )
        InflateRect(&Rect, -1, -1);
      v3 = this->m_bUseNavigationToolbar == 0;
      p_m_rectToolbar = &this->m_rectToolbar;
      m_nCount = this->m_lstTasksPanes.m_nCount;
      rc1 = (RECT)this->m_rectToolbar;
      if ( (!v3
         || ((ParentTabbedPane = CBasePane::GetParentTabbedPane(this), (v7 = this->GetParentMiniFrame(this, 1)) == 0)
          || CObject::IsKindOf(v7, &CMFCTasksPaneFrameWnd::classCMFCTasksPaneFrameWnd)
           ? (v8 = 0)
           : (v8 = 1),
             ParentTabbedPane || v8))
        && m_nCount > 1 )
      {
        p_m_wndToolBar = &this->m_wndToolBar;
        v10 = this->m_wndToolBar.CalcFixedLayout(&this->m_wndToolBar, v27, 0, 1);
        v11 = _mm_loadu_si128((const __m128i *)&Rect);
        v12 = v10->cy;
        *p_m_rectToolbar = (CRect)v11;
        this->m_rectToolbar.bottom = this->m_rectToolbar.top + v12;
        left = (unsigned int)p_m_rectToolbar->left;
        Rect.top = v12 + _mm_cvtsi128_si32(_mm_srli_si128(v11, 4));
        ((void (__fastcall *)(CMFCTasksPaneToolBar *, _QWORD, __int64))this->m_wndToolBar.SetWindowPos)(
          &this->m_wndToolBar,
          0,
          left);
        v14 = 1;
      }
      else
      {
        SetRectEmpty(&this->m_rectToolbar);
        v14 = 0;
        p_m_wndToolBar = &this->m_wndToolBar;
      }
      CWnd::ShowWindow(p_m_wndToolBar, v14);
      this->m_rectTasks = (CRect)Rect;
      CMFCTasksPane::SetScrollSizes(this);
      CWnd::EnableWindow(&this->m_wndScrollVert, this->m_bUseScrollButtons == 0);
      if ( this->m_bUseScrollButtons || this->m_nVertScrollTotal <= 0 )
      {
        CWnd::SetWindowPos(&this->m_wndScrollVert, 0, 0, 0, 0, 0, 0x80u);
      }
      else
      {
        SystemMetrics = GetSystemMetrics(21);
        top = Rect.top;
        v17 = SystemMetrics;
        right = Rect.right;
        cy = Rect.bottom - Rect.top;
        this->m_rectTasks.right -= SystemMetrics;
        CWnd::SetWindowPos(&this->m_wndScrollVert, 0, right - SystemMetrics, top, SystemMetrics, cy, 0x54u);
        Rect.right -= v17;
      }
      m_rectScrollDn = this->m_rectScrollDn;
      m_rectScrollUp = (RECT)this->m_rectScrollUp;
      v31 = m_rectScrollDn.tagRECT;
      SetRectEmpty(&this->m_rectScrollUp);
      SetRectEmpty(&this->m_rectScrollDn);
      if ( this->m_bUseScrollButtons )
      {
        m_nVertScrollOffset = this->m_nVertScrollOffset;
        if ( m_nVertScrollOffset > 0 )
        {
          v22 = (CRect)_mm_loadu_si128((const __m128i *)&Rect);
          m_iScrollBtnHeight = this->m_iScrollBtnHeight;
          this->m_rectScrollUp = v22;
          ++this->m_rectScrollUp.top;
          this->m_rectScrollUp.bottom = m_iScrollBtnHeight + this->m_rectScrollUp.top;
          Rect.top = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v22, 4)) + m_iScrollBtnHeight + 1;
        }
        if ( m_nVertScrollOffset <= this->m_nVertScrollTotal - this->m_nVertScrollPage && this->m_nVertScrollTotal > 0 )
        {
          v24 = (CRect)_mm_loadu_si128((const __m128i *)&Rect);
          v25 = this->m_iScrollBtnHeight;
          this->m_rectScrollDn = v24;
          this->m_rectScrollDn.top = this->m_rectScrollDn.bottom - v25;
          Rect.bottom = -1 - v25 + _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v24, 12));
        }
        this->m_rectTasks = (CRect)Rect;
      }
      else if ( this->m_pAnimatedGroup )
      {
        KillTimer(this->m_hWnd, 0xEC0Cu);
        this->m_iScrollMode = 0;
      }
      if ( !EqualRect(&rc1, &this->m_rectToolbar) )
      {
        InvalidateRect(this->m_hWnd, &this->m_rectToolbar, 1);
        InvalidateRect(this->m_hWnd, &rc1, 1);
        UpdateWindow(this->m_hWnd);
      }
      v26 = 0;
      if ( !EqualRect(&m_rectScrollUp, &this->m_rectScrollUp) )
      {
        InvalidateRect(this->m_hWnd, &m_rectScrollUp, 1);
        InvalidateRect(this->m_hWnd, &this->m_rectScrollUp, 1);
        v26 = 1;
      }
      if ( EqualRect(&v31, &this->m_rectScrollDn) )
      {
        if ( !v26 )
          return;
      }
      else
      {
        InvalidateRect(this->m_hWnd, &v31, 1);
        InvalidateRect(this->m_hWnd, &this->m_rectScrollDn, 1);
      }
      UpdateWindow(this->m_hWnd);
    }
  }
}

```

## disassembly

```asm
0x18014e820  test    this, this
0x18014e823  jz      locret_18014EC47
0x18014e829  mov     [rsp-8+arg_8], rbx
0x18014e82e  mov     [rsp-8+arg_10], rsi
0x18014e833  push    rbp
0x18014e834  push    rdi
0x18014e835  push    r13
0x18014e837  push    r14
0x18014e839  push    r15
0x18014e83b  lea     rbp, [rsp+20h+rc1.left+1]
0x18014e840  sub     rsp, 0A0h
0x18014e847  mov     rax, cs:__security_cookie
0x18014e84e  xor     rax, rsp
0x18014e851  mov     [rbp+57h+var_28], rax
0x18014e855  mov     rdi, this
0x18014e858  mov     this, [this+40h]; hWnd
0x18014e85c  test    this, this
0x18014e85f  jz      loc_18014EC20
0x18014e865  xorps   xmm0, xmm0
0x18014e868  lea     rdx, [rbp+57h+Rect]; lpRect
0x18014e86c  movdqu  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18014e871  call    cs:__imp_GetClientRect
0x18014e877  mov     rax, [rdi]
0x18014e87a  mov     this, rdi
0x18014e87d  mov     rax, [rax+798h]
0x18014e884  call    cs:__guard_dispatch_icall_fptr
0x18014e88a  or      esi, 0FFFFFFFFh
0x18014e88d  test    eax, eax
0x18014e88f  jz      short loc_18014E8A0
0x18014e891  mov     r8d, esi; dy
0x18014e894  lea     this, [rbp+57h+Rect]; lprc
0x18014e898  mov     edx, esi; dx
0x18014e89a  call    cs:__imp_InflateRect
0x18014e8a0  cmp     dword ptr [rdi+4E4h], 0
0x18014e8a7  lea     rbx, [rdi+5A8h]
0x18014e8ae  movups  xmm0, xmmword ptr [rbx]
0x18014e8b1  mov     r14, [rdi+620h]
0x18014e8b8  mov     r13d, 1
0x18014e8be  movdqu  xmmword ptr [rbp+57h+rc1.left], xmm0
0x18014e8c3  jnz     short loc_18014E912
0x18014e8c5  mov     this, rdi; this
0x18014e8c8  call    ?GetParentTabbedPane@CBasePane@@QEBAPEAVCBaseTabbedPane@@XZ; CBasePane::GetParentTabbedPane(void)
0x18014e8cd  mov     this, [rdi]
0x18014e8d0  mov     r15, rax
0x18014e8d3  mov     edx, r13d
0x18014e8d6  mov     rax, [this+460h]
0x18014e8dd  mov     this, rdi
0x18014e8e0  call    cs:__guard_dispatch_icall_fptr
0x18014e8e6  test    rax, rax
0x18014e8e9  jz      short loc_18014E903
0x18014e8eb  lea     rdx, ?classCMFCTasksPaneFrameWnd@CMFCTasksPaneFrameWnd@@2UCRuntimeClass@@A; pClass
0x18014e8f2  mov     this, rax; this
0x18014e8f5  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18014e8fa  test    eax, eax
0x18014e8fc  jnz     short loc_18014E903
0x18014e8fe  mov     eax, r13d
0x18014e901  jmp     short loc_18014E905
0x18014e903  xor     eax, eax
0x18014e905  test    r15, r15
0x18014e908  jnz     short loc_18014E912
0x18014e90a  test    eax, eax
0x18014e90c  jz      loc_18014E9A2
0x18014e912  cmp     r14, r13
0x18014e915  jle     loc_18014E9A2
0x18014e91b  lea     r14, [rdi+7B8h]
0x18014e922  mov     r9d, r13d
0x18014e925  mov     rax, [r14]
0x18014e928  lea     rdx, [rbp+57h+var_70]
0x18014e92c  xor     r8d, r8d
0x18014e92f  mov     this, r14
0x18014e932  mov     rax, [rax+4D0h]
0x18014e939  call    cs:__guard_dispatch_icall_fptr
0x18014e93f  movdqu  xmm0, xmmword ptr [rbp+57h+Rect.left]
0x18014e944  and     [rsp+0C0h+var_88], 0
0x18014e94a  mov     [rsp+0C0h+nFlags], 14h
0x18014e952  mov     edx, [rax+4]
0x18014e955  movdqu  xmmword ptr [rbx], xmm0
0x18014e959  mov     r9d, [rdi+5ACh]
0x18014e960  mov     [rsp+0C0h+cy], edx
0x18014e964  psrldq  xmm0, 4
0x18014e969  lea     eax, [r9+rdx]
0x18014e96d  mov     [rdi+5B4h], eax
0x18014e973  mov     ecx, [rbx+8]
0x18014e976  sub     ecx, [rbx]
0x18014e978  mov     r8d, [rbx]
0x18014e97b  movd    eax, xmm0
0x18014e97f  mov     [rsp+0C0h+var_A0], ecx
0x18014e983  mov     this, r14
0x18014e986  add     eax, edx
0x18014e988  xor     edx, edx
0x18014e98a  mov     [rbp+57h+Rect.top], eax
0x18014e98d  mov     rax, [r14]
0x18014e990  mov     rax, [rax+480h]
0x18014e997  call    cs:__guard_dispatch_icall_fptr
0x18014e99d  mov     edx, r13d
0x18014e9a0  jmp     short loc_18014E9B4
0x18014e9a2  mov     this, rbx; lprc
0x18014e9a5  call    cs:__imp_SetRectEmpty
0x18014e9ab  xor     edx, edx; nCmdShow
0x18014e9ad  lea     r14, [rdi+7B8h]
0x18014e9b4  mov     this, r14; this
0x18014e9b7  call    ?ShowWindow@CWnd@@QEAAHH@Z; CWnd::ShowWindow(int)
0x18014e9bc  movups  xmm0, xmmword ptr [rbp+57h+Rect.left]
0x18014e9c0  mov     this, rdi; this
0x18014e9c3  movdqu  xmmword ptr [rdi+5D8h], xmm0
0x18014e9cb  call    ?SetScrollSizes@CMFCTasksPane@@IEAAXXZ; CMFCTasksPane::SetScrollSizes(void)
0x18014e9d0  xor     edx, edx
0x18014e9d2  lea     r14, [rdi+680h]
0x18014e9d9  cmp     [rdi+4ECh], edx
0x18014e9df  mov     this, r14; this
0x18014e9e2  setz    dl; bEnable
0x18014e9e5  call    ?EnableWindow@CWnd@@QEAAHH@Z; CWnd::EnableWindow(int)
0x18014e9ea  cmp     dword ptr [rdi+4ECh], 0
0x18014e9f1  jnz     short loc_18014EA3F
0x18014e9f3  cmp     dword ptr [rdi+514h], 0
0x18014e9fa  jle     short loc_18014EA3F
0x18014e9fc  mov     ecx, 15h; nIndex
0x18014ea01  call    cs:__imp_GetSystemMetrics
0x18014ea07  mov     ecx, [rbp+57h+Rect.bottom]
0x18014ea0a  xor     edx, edx; pWndInsertAfter
0x18014ea0c  mov     r9d, [rbp+57h+Rect.top]; y
0x18014ea10  mov     ebx, eax
0x18014ea12  mov     r8d, [rbp+57h+Rect.right]
0x18014ea16  sub     ecx, r9d
0x18014ea19  sub     [rdi+5E0h], eax
0x18014ea1f  sub     r8d, eax; x
0x18014ea22  mov     [rsp+0C0h+nFlags], 54h ; 'T'; nFlags
0x18014ea2a  mov     [rsp+0C0h+cy], ecx; cy
0x18014ea2e  mov     this, r14; this
0x18014ea31  mov     [rsp+0C0h+var_A0], eax; cx
0x18014ea35  call    ?SetWindowPos@CWnd@@QEAAHPEBV1@HHHHI@Z; CWnd::SetWindowPos(CWnd const *,int,int,int,int,uint)
0x18014ea3a  sub     [rbp+57h+Rect.right], ebx
0x18014ea3d  jmp     short loc_18014EA61
0x18014ea3f  mov     [rsp+0C0h+nFlags], 80h; nFlags
0x18014ea47  xor     r9d, r9d; y
0x18014ea4a  and     [rsp+0C0h+cy], 0
0x18014ea4f  xor     r8d, r8d; x
0x18014ea52  and     [rsp+0C0h+var_A0], 0
0x18014ea57  xor     edx, edx; pWndInsertAfter
0x18014ea59  mov     this, r14; this
0x18014ea5c  call    ?SetWindowPos@CWnd@@QEAAHPEBV1@HHHHI@Z; CWnd::SetWindowPos(CWnd const *,int,int,int,int,uint)
0x18014ea61  lea     r14, [rdi+5B8h]
0x18014ea68  movups  xmm0, xmmword ptr [r14]
0x18014ea6c  lea     rbx, [rdi+5C8h]
0x18014ea73  mov     this, r14; lprc
0x18014ea76  movups  xmm1, xmmword ptr [rbx]
0x18014ea79  movdqu  xmmword ptr [rbp+57h+var_48.left], xmm0
0x18014ea7e  movdqu  xmmword ptr [rbp+57h+var_38.left], xmm1
0x18014ea83  call    cs:__imp_SetRectEmpty
0x18014ea89  mov     this, rbx; lprc
0x18014ea8c  call    cs:__imp_SetRectEmpty
0x18014ea92  cmp     dword ptr [rdi+4ECh], 0
0x18014ea99  jz      loc_18014EB33
0x18014ea9f  mov     edx, [rdi+510h]
0x18014eaa5  test    edx, edx
0x18014eaa7  jle     short loc_18014EADE
0x18014eaa9  movdqu  xmm0, xmmword ptr [rbp+57h+Rect.left]
0x18014eaae  mov     ecx, [rdi+50Ch]
0x18014eab4  movdqu  xmmword ptr [r14], xmm0
0x18014eab9  add     [rdi+5BCh], r13d
0x18014eac0  mov     eax, [rdi+5BCh]
0x18014eac6  add     eax, ecx
0x18014eac8  psrldq  xmm0, 4
0x18014eacd  mov     [rdi+5C4h], eax
0x18014ead3  inc     ecx
0x18014ead5  movd    eax, xmm0
0x18014ead9  add     ecx, eax
0x18014eadb  mov     [rbp+57h+Rect.top], ecx
0x18014eade  mov     ecx, [rdi+514h]
0x18014eae4  mov     eax, ecx
0x18014eae6  sub     eax, [rdi+518h]
0x18014eaec  cmp     edx, eax
0x18014eaee  jg      short loc_18014EB25
0x18014eaf0  test    ecx, ecx
0x18014eaf2  jle     short loc_18014EB25
0x18014eaf4  movdqu  xmm0, xmmword ptr [rbp+57h+Rect.left]
0x18014eaf9  mov     ecx, [rdi+50Ch]
0x18014eaff  sub     esi, ecx
0x18014eb01  movdqu  xmmword ptr [rdi+5C8h], xmm0
0x18014eb09  mov     eax, [rdi+5D4h]
0x18014eb0f  sub     eax, ecx
0x18014eb11  psrldq  xmm0, 0Ch
0x18014eb16  mov     [rdi+5CCh], eax
0x18014eb1c  movd    eax, xmm0
0x18014eb20  add     eax, esi
0x18014eb22  mov     [rbp+57h+Rect.bottom], eax
0x18014eb25  movups  xmm0, xmmword ptr [rbp+57h+Rect.left]
0x18014eb29  movdqu  xmmword ptr [rdi+5D8h], xmm0
0x18014eb31  jmp     short loc_18014EB53
0x18014eb33  cmp     qword ptr [rdi+7B0h], 0
0x18014eb3b  jz      short loc_18014EB53
0x18014eb3d  mov     this, [rdi+40h]; hWnd
0x18014eb41  mov     edx, 0EC0Ch; uIDEvent
0x18014eb46  call    cs:__imp_KillTimer
0x18014eb4c  and     dword ptr [rdi+508h], 0
0x18014eb53  lea     rdx, [rdi+5A8h]; lprc2
0x18014eb5a  lea     this, [rbp+57h+rc1]; lprc1
0x18014eb5e  call    cs:__imp_EqualRect
0x18014eb64  test    eax, eax
0x18014eb66  jnz     short loc_18014EB97
0x18014eb68  mov     this, [rdi+40h]; hWnd
0x18014eb6c  lea     rdx, [rdi+5A8h]; lpRect
0x18014eb73  mov     r8d, r13d; bErase
0x18014eb76  call    cs:__imp_InvalidateRect
0x18014eb7c  mov     this, [rdi+40h]; hWnd
0x18014eb80  lea     rdx, [rbp+57h+rc1]; lpRect
0x18014eb84  mov     r8d, r13d; bErase
0x18014eb87  call    cs:__imp_InvalidateRect
0x18014eb8d  mov     this, [rdi+40h]; hWnd
0x18014eb91  call    cs:__imp_UpdateWindow
0x18014eb97  lea     rdx, [rdi+5B8h]; lprc2
0x18014eb9e  xor     ebx, ebx
0x18014eba0  lea     this, [rbp+57h+var_48]; lprc1
0x18014eba4  call    cs:__imp_EqualRect
0x18014ebaa  test    eax, eax
0x18014ebac  jnz     short loc_18014EBD6
0x18014ebae  mov     this, [rdi+40h]; hWnd
0x18014ebb2  lea     rdx, [rbp+57h+var_48]; lpRect
0x18014ebb6  mov     r8d, r13d; bErase
0x18014ebb9  call    cs:__imp_InvalidateRect
0x18014ebbf  mov     this, [rdi+40h]; hWnd
0x18014ebc3  lea     rdx, [rdi+5B8h]; lpRect
0x18014ebca  mov     r8d, r13d; bErase
0x18014ebcd  call    cs:__imp_InvalidateRect
0x18014ebd3  mov     ebx, r13d
0x18014ebd6  lea     rdx, [rdi+5C8h]; lprc2
0x18014ebdd  lea     this, [rbp+57h+var_38]; lprc1
0x18014ebe1  call    cs:__imp_EqualRect
0x18014ebe7  test    eax, eax
0x18014ebe9  jnz     short loc_18014EC12
0x18014ebeb  mov     this, [rdi+40h]; hWnd
0x18014ebef  lea     rdx, [rbp+57h+var_38]; lpRect
0x18014ebf3  mov     r8d, r13d; bErase
0x18014ebf6  call    cs:__imp_InvalidateRect
0x18014ebfc  mov     this, [rdi+40h]; hWnd
0x18014ec00  lea     rdx, [rdi+5C8h]; lpRect
0x18014ec07  mov     r8d, r13d; bErase
0x18014ec0a  call    cs:__imp_InvalidateRect
0x18014ec10  jmp     short loc_18014EC16
0x18014ec12  test    ebx, ebx
0x18014ec14  jz      short loc_18014EC20
0x18014ec16  mov     this, [rdi+40h]; hWnd
0x18014ec1a  call    cs:__imp_UpdateWindow
0x18014ec20  mov     this, [rbp+57h+var_28]
0x18014ec24  xor     this, rsp; StackCookie
0x18014ec27  call    __security_check_cookie
0x18014ec2c  lea     r11, [rsp+0C0h+var_20]
0x18014ec34  mov     rbx, [r11+38h]
0x18014ec38  mov     rsi, [r11+40h]
0x18014ec3c  mov     rsp, r11
0x18014ec3f  pop     r15
0x18014ec41  pop     r14
0x18014ec43  pop     r13
0x18014ec45  pop     rdi
0x18014ec46  pop     rbp
0x18014ec47  retn
```
