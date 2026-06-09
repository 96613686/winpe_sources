# CPaneContainer::GetWindowRect(CRect &,int)

- ea: `0x1800a6470`
- end: `0x1800a66a0`
- name: `?GetWindowRect@CPaneContainer@@UEBAXAEAVCRect@@H@Z`
- size: `560`
- prototype: `void __fastcall(CPaneContainer *this, CRect *rect, int bIgnoreVisibility)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800a6470`
- `0x1800a9ca0`
- `0x1802b62e0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!UnionRect` at `0x1800a65f5`
- `USER32!UnionRect` at `0x1800a6637`
- `USER32!UnionRect` at `0x1800a6679`
- `USER32!UnionRect` at `0x1800a65f5`
- `USER32!UnionRect` at `0x1800a6637`
- `USER32!UnionRect` at `0x1800a6679`
- `USER32!SetRectEmpty` at `0x1800a64b3`
- `USER32!SetRectEmpty` at `0x1800a64bd`
- `USER32!SetRectEmpty` at `0x1800a64c7`
- `USER32!SetRectEmpty` at `0x1800a64b3`
- `USER32!SetRectEmpty` at `0x1800a64bd`
- `USER32!SetRectEmpty` at `0x1800a64c7`
- `USER32!GetWindowRect` at `0x1800a6522`
- `USER32!GetWindowRect` at `0x1800a659a`
- `USER32!GetWindowRect` at `0x1800a6522`
- `USER32!GetWindowRect` at `0x1800a659a`
- `USER32!IsRectEmpty` at `0x1800a652c`
- `USER32!IsRectEmpty` at `0x1800a65a4`
- `USER32!IsRectEmpty` at `0x1800a652c`
- `USER32!IsRectEmpty` at `0x1800a65a4`

## pseudocode

```c
void __fastcall CPaneContainer::GetWindowRect(CPaneContainer *this, CRect *rect, int bIgnoreVisibility)
{
  CPaneDivider *m_pDefaultSlider; // rcx
  BOOL v7; // edi
  CDockablePane *m_pBarLeftTop; // rcx
  CDockablePane *v9; // rcx
  CDockablePane *m_pBarRightBottom; // rcx
  CDockablePane *v11; // rcx
  CPaneContainer *m_pLeftContainer; // rcx
  CPaneContainer *m_pRightContainer; // rcx
  CSize sz; // [rsp+20h] [rbp-40h] BYREF
  CRect rectRight; // [rsp+28h] [rbp-38h] BYREF
  CRect rectLeft; // [rsp+38h] [rbp-28h] BYREF
  CRect rectContainer; // [rsp+48h] [rbp-18h] BYREF

  rectLeft = 0;
  rectRight = 0;
  rectContainer = 0;
  SetRectEmpty(rect);
  SetRectEmpty(&rectLeft);
  SetRectEmpty(&rectRight);
  m_pDefaultSlider = this->m_pContainerManager->m_pDefaultSlider;
  v7 = m_pDefaultSlider && m_pDefaultSlider->IsAutoHideMode(m_pDefaultSlider);
  m_pBarLeftTop = this->m_pBarLeftTop;
  if ( m_pBarLeftTop && ((CWnd::GetStyle(&m_pBarLeftTop->CPane) & 0x10000000) != 0 || bIgnoreVisibility || v7) )
  {
    GetWindowRect(this->m_pBarLeftTop->m_hWnd, &rectLeft);
    if ( IsRectEmpty(&rectLeft) )
    {
      v9 = this->m_pBarLeftTop;
      sz.cx = 0;
      sz.cy = 0;
      v9->GetMinSize(&v9->CPane, &sz);
      if ( rectLeft.right == rectLeft.left )
        rectLeft.right += sz.cx;
      if ( rectLeft.bottom == rectLeft.top )
        rectLeft.bottom += sz.cy;
    }
  }
  m_pBarRightBottom = this->m_pBarRightBottom;
  if ( m_pBarRightBottom && ((CWnd::GetStyle(&m_pBarRightBottom->CPane) & 0x10000000) != 0 || bIgnoreVisibility || v7) )
  {
    GetWindowRect(this->m_pBarRightBottom->m_hWnd, &rectRight);
    if ( IsRectEmpty(&rectRight) )
    {
      v11 = this->m_pBarRightBottom;
      sz.cx = 0;
      sz.cy = 0;
      v11->GetMinSize(&v11->CPane, &sz);
      if ( rectRight.right == rectRight.left )
        rectRight.right += sz.cx;
      if ( rectRight.bottom == rectRight.top )
        rectRight.bottom += sz.cy;
    }
  }
  UnionRect(rect, &rectLeft, &rectRight);
  m_pLeftContainer = this->m_pLeftContainer;
  if ( m_pLeftContainer && (CPaneContainer::IsVisible(m_pLeftContainer) || bIgnoreVisibility || v7) )
  {
    this->m_pLeftContainer->GetWindowRect(this->m_pLeftContainer, &rectContainer, 0);
    UnionRect(rect, rect, &rectContainer);
  }
  m_pRightContainer = this->m_pRightContainer;
  if ( m_pRightContainer && (CPaneContainer::IsVisible(m_pRightContainer) || bIgnoreVisibility || v7) )
  {
    this->m_pRightContainer->GetWindowRect(this->m_pRightContainer, &rectContainer, 0);
    UnionRect(rect, rect, &rectContainer);
  }
}

```

## disassembly

```asm
0x1800a6470  mov     [rsp-18h+arg_10], rbx
0x1800a6475  mov     [rsp-18h+arg_18], rsi
0x1800a647a  push    rbp
0x1800a647b  push    rdi
0x1800a647c  push    r14
0x1800a647e  mov     rbp, rsp
0x1800a6481  sub     rsp, 60h
0x1800a6485  mov     rax, cs:__security_cookie
0x1800a648c  xor     rax, rsp
0x1800a648f  mov     [rbp+var_8], rax
0x1800a6493  xorps   xmm0, xmm0
0x1800a6496  mov     rbx, this
0x1800a6499  xorps   xmm1, xmm1
0x1800a649c  mov     this, rect; lprc
0x1800a649f  movdqu  xmmword ptr [rbp+rectLeft.left], xmm0
0x1800a64a4  mov     esi, bIgnoreVisibility
0x1800a64a7  mov     r14, rect
0x1800a64aa  movdqu  xmmword ptr [rbp+rectRight.left], xmm1
0x1800a64af  movups  xmmword ptr [rbp+rectContainer.left], xmm0
0x1800a64b3  call    cs:__imp_SetRectEmpty
0x1800a64b9  lea     this, [rbp+rectLeft]; lprc
0x1800a64bd  call    cs:__imp_SetRectEmpty
0x1800a64c3  lea     this, [rbp+rectRight]; lprc
0x1800a64c7  call    cs:__imp_SetRectEmpty
0x1800a64cd  mov     rax, [rbx+38h]
0x1800a64d1  mov     this, [rax+88h]
0x1800a64d8  test    this, this
0x1800a64db  jz      short loc_1800A64F8
0x1800a64dd  mov     rax, [this]
0x1800a64e0  mov     rax, [rax+3C8h]
0x1800a64e7  call    cs:__guard_dispatch_icall_fptr
0x1800a64ed  test    eax, eax
0x1800a64ef  jz      short loc_1800A64F8
0x1800a64f1  mov     edi, 1
0x1800a64f6  jmp     short loc_1800A64FA
0x1800a64f8  xor     edi, edi
0x1800a64fa  mov     this, [rbx+8]; this
0x1800a64fe  test    this, this
0x1800a6501  jz      short loc_1800A6572
0x1800a6503  call    ?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x1800a6508  bt      eax, 1Ch
0x1800a650c  jb      short loc_1800A6516
0x1800a650e  test    esi, esi
0x1800a6510  jnz     short loc_1800A6516
0x1800a6512  test    edi, edi
0x1800a6514  jz      short loc_1800A6572
0x1800a6516  mov     this, [rbx+8]
0x1800a651a  lea     rect, [rbp+rectLeft]; lpRect
0x1800a651e  mov     this, [this+40h]; hWnd
0x1800a6522  call    cs:__imp_GetWindowRect
0x1800a6528  lea     this, [rbp+rectLeft]; lprc
0x1800a652c  call    cs:__imp_IsRectEmpty
0x1800a6532  test    eax, eax
0x1800a6534  jz      short loc_1800A6572
0x1800a6536  mov     this, [rbx+8]
0x1800a653a  lea     rect, [rbp+sz]
0x1800a653e  and     [rbp+sz.cx], 0
0x1800a6542  and     [rbp+sz.cy], 0
0x1800a6546  mov     rax, [this]
0x1800a6549  mov     rax, [rax+4F0h]
0x1800a6550  call    cs:__guard_dispatch_icall_fptr
0x1800a6556  mov     ecx, [rbp+rectLeft.right]
0x1800a6559  cmp     ecx, [rbp+rectLeft.left]
0x1800a655c  jnz     short loc_1800A6564
0x1800a655e  add     ecx, [rbp+sz.cx]
0x1800a6561  mov     [rbp+rectLeft.right], ecx
0x1800a6564  mov     ecx, [rbp+rectLeft.bottom]
0x1800a6567  cmp     ecx, [rbp+rectLeft.top]
0x1800a656a  jnz     short loc_1800A6572
0x1800a656c  add     ecx, [rbp+sz.cy]
0x1800a656f  mov     [rbp+rectLeft.bottom], ecx
0x1800a6572  mov     this, [rbx+10h]; this
0x1800a6576  test    this, this
0x1800a6579  jz      short loc_1800A65EA
0x1800a657b  call    ?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x1800a6580  bt      eax, 1Ch
0x1800a6584  jb      short loc_1800A658E
0x1800a6586  test    esi, esi
0x1800a6588  jnz     short loc_1800A658E
0x1800a658a  test    edi, edi
0x1800a658c  jz      short loc_1800A65EA
0x1800a658e  mov     this, [rbx+10h]
0x1800a6592  lea     rect, [rbp+rectRight]; lpRect
0x1800a6596  mov     this, [this+40h]; hWnd
0x1800a659a  call    cs:__imp_GetWindowRect
0x1800a65a0  lea     this, [rbp+rectRight]; lprc
0x1800a65a4  call    cs:__imp_IsRectEmpty
0x1800a65aa  test    eax, eax
0x1800a65ac  jz      short loc_1800A65EA
0x1800a65ae  mov     this, [rbx+10h]
0x1800a65b2  lea     rect, [rbp+sz]
0x1800a65b6  and     [rbp+sz.cx], 0
0x1800a65ba  and     [rbp+sz.cy], 0
0x1800a65be  mov     rax, [this]
0x1800a65c1  mov     rax, [rax+4F0h]
0x1800a65c8  call    cs:__guard_dispatch_icall_fptr
0x1800a65ce  mov     ecx, [rbp+rectRight.right]
0x1800a65d1  cmp     ecx, [rbp+rectRight.left]
0x1800a65d4  jnz     short loc_1800A65DC
0x1800a65d6  add     ecx, [rbp+sz.cx]
0x1800a65d9  mov     [rbp+rectRight.right], ecx
0x1800a65dc  mov     ecx, [rbp+rectRight.bottom]
0x1800a65df  cmp     ecx, [rbp+rectRight.top]
0x1800a65e2  jnz     short loc_1800A65EA
0x1800a65e4  add     ecx, [rbp+sz.cy]
0x1800a65e7  mov     [rbp+rectRight.bottom], ecx
0x1800a65ea  lea     r8, [rbp+rectRight]; lprcSrc2
0x1800a65ee  mov     this, r14; lprcDst
0x1800a65f1  lea     rect, [rbp+rectLeft]; lprcSrc1
0x1800a65f5  call    cs:__imp_UnionRect
0x1800a65fb  mov     this, [rbx+20h]; this
0x1800a65ff  test    this, this
0x1800a6602  jz      short loc_1800A663D
0x1800a6604  call    ?IsVisible@CPaneContainer@@QEBAHXZ; CPaneContainer::IsVisible(void)
0x1800a6609  test    eax, eax
0x1800a660b  jnz     short loc_1800A6615
0x1800a660d  test    esi, esi
0x1800a660f  jnz     short loc_1800A6615
0x1800a6611  test    edi, edi
0x1800a6613  jz      short loc_1800A663D
0x1800a6615  mov     this, [rbx+20h]
0x1800a6619  lea     rect, [rbp+rectContainer]
0x1800a661d  xor     bIgnoreVisibility, bIgnoreVisibility
0x1800a6620  mov     rax, [this]
0x1800a6623  mov     rax, [rax+28h]
0x1800a6627  call    cs:__guard_dispatch_icall_fptr
0x1800a662d  lea     r8, [rbp+rectContainer]; lprcSrc2
0x1800a6631  mov     rect, r14; lprcSrc1
0x1800a6634  mov     this, r14; lprcDst
0x1800a6637  call    cs:__imp_UnionRect
0x1800a663d  mov     this, [rbx+28h]; this
0x1800a6641  test    this, this
0x1800a6644  jz      short loc_1800A667F
0x1800a6646  call    ?IsVisible@CPaneContainer@@QEBAHXZ; CPaneContainer::IsVisible(void)
0x1800a664b  test    eax, eax
0x1800a664d  jnz     short loc_1800A6657
0x1800a664f  test    esi, esi
0x1800a6651  jnz     short loc_1800A6657
0x1800a6653  test    edi, edi
0x1800a6655  jz      short loc_1800A667F
0x1800a6657  mov     this, [rbx+28h]
0x1800a665b  lea     rect, [rbp+rectContainer]
0x1800a665f  xor     bIgnoreVisibility, bIgnoreVisibility
0x1800a6662  mov     rax, [this]
0x1800a6665  mov     rax, [rax+28h]
0x1800a6669  call    cs:__guard_dispatch_icall_fptr
0x1800a666f  lea     r8, [rbp+rectContainer]; lprcSrc2
0x1800a6673  mov     rect, r14; lprcSrc1
0x1800a6676  mov     this, r14; lprcDst
0x1800a6679  call    cs:__imp_UnionRect
0x1800a667f  mov     this, [rbp+var_8]
0x1800a6683  xor     this, rsp; StackCookie
0x1800a6686  call    __security_check_cookie
0x1800a668b  lea     r11, [rsp+60h+var_s0]
0x1800a6690  mov     rbx, [r11+30h]
0x1800a6694  mov     rsi, [r11+38h]
0x1800a6698  mov     rsp, r11
0x1800a669b  pop     r14
0x1800a669d  pop     rdi
0x1800a669e  pop     rbp
0x1800a669f  retn
```
