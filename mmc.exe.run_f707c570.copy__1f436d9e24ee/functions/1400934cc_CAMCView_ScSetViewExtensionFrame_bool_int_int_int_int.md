# CAMCView::ScSetViewExtensionFrame(bool,int,int,int,int)

- ea: `0x1400934cc`
- end: `0x1400936ba`
- name: `?ScSetViewExtensionFrame@CAMCView@@QEAA?AVSC@mmcerror@@_NHHHH@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400c3e78`

## callees

- `0x14000c1d0`
- `0x14003e644`
- `0x1400934cc`
- `0x1400e9e10`

## import_xrefs

- `USER32!MoveWindow` at `0x140093689`
- `USER32!MoveWindow` at `0x140093689`
- `USER32!InflateRect` at `0x14009355d`
- `USER32!InflateRect` at `0x14009355d`
- `USER32!OffsetRect` at `0x140093573`
- `USER32!OffsetRect` at `0x140093573`
- `MFC42u!__imp_?GetExStyle@CWnd@@QEBAKXZ` at `0x1400935ad`
- `MFC42u!__imp_?GetExStyle@CWnd@@QEBAKXZ` at `0x1400935ad`
- `MFC42u!__imp_?ShowWindow@CWnd@@QEAAHH@Z` at `0x14009365b`
- `MFC42u!__imp_?ShowWindow@CWnd@@QEAAHH@Z` at `0x14009365b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140093626`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140093626`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14009362f`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14009362f`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140093512`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140093512`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14009361b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14009361b`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140093526`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140093526`

## string_xrefs

- `0x14009351c`: `CAMCView::ScSetViewExtensionFrame`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
mmcerror::SC *__fastcall CAMCView::ScSetViewExtensionFrame(
        __int64 a1,
        mmcerror::SC *a2,
        char a3,
        LONG top,
        LONG a5,
        LONG a6,
        LONG a7)
{
  LONG left; // r15d
  LONG right; // r12d
  LONG bottom; // eax
  int v13; // esi
  int v14; // edi
  int v15; // r13d
  int v16; // r15d
  CWnd *PaneView; // r14
  __int64 v18; // rax
  int v19; // r15d
  HWND v20; // rcx
  LONG v23; // [rsp+38h] [rbp-48h]
  int v24; // [rsp+3Ch] [rbp-44h]
  _BYTE v25[24]; // [rsp+48h] [rbp-38h] BYREF
  struct tagRECT rc; // [rsp+60h] [rbp-20h] BYREF
  LONG v27; // [rsp+E8h] [rbp+68h]

  mmcerror::SC::SC(a2, 0);
  mmcerror::SC::SetFunctionName(a2, L"CAMCView::ScSetViewExtensionFrame");
  if ( *(_BYTE *)(a1 + 867) )
  {
    rc = *(struct tagRECT *)(a1 + 1256);
    InflateRect(&rc, -CAMCView::m_sizEdge, -dword_1401621CC);
    OffsetRect(&rc, -rc.left, -rc.top);
    left = a5;
    if ( a5 < rc.left )
      left = rc.left;
    right = a7;
    if ( a7 > rc.right )
      right = rc.right;
    if ( top < rc.top )
      top = rc.top;
    v23 = top;
    bottom = a6;
    if ( a6 > rc.bottom )
      bottom = rc.bottom;
    v27 = bottom;
    if ( (CWnd::GetExStyle((CWnd *)a1) & 0x400000) != 0 )
    {
      v13 = rc.left + rc.right - right;
      v14 = rc.left + rc.right - left;
    }
    else
    {
      v13 = left;
      v14 = right;
    }
    v15 = dword_1401621CC + *(_DWORD *)(a1 + 1260);
    v16 = CAMCView::m_sizEdge + *(_DWORD *)(a1 + 1256);
    v24 = v16;
    PaneView = (CWnd *)CAMCView::GetPaneView(a1, 1);
    v18 = ScCheckPointers(v25, PaneView, 2147942487LL);
    mmcerror::SC::operator=(a2, v18);
    mmcerror::SC::~SC((mmcerror::SC *)v25);
    if ( !(unsigned __int8)mmcerror::SC::operator bool(a2) )
    {
      v19 = v13 + v16;
      if ( a3 )
        CWnd::ShowWindow(PaneView, 5);
      if ( PaneView )
        v20 = (HWND)*((_QWORD *)PaneView + 8);
      else
        v20 = 0;
      MoveWindow(v20, v19, v15 + v23, v14 + v24 - v19, v27 - v23, 1);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1400934cc  mov     [rsp-38h+arg_10], rbx
0x1400934d1  push    rbp
0x1400934d2  push    rsi
0x1400934d3  push    rdi
0x1400934d4  push    r12
0x1400934d6  push    r13
0x1400934d8  push    r14
0x1400934da  push    r15
0x1400934dc  mov     rbp, rsp
0x1400934df  sub     rsp, 80h
0x1400934e6  mov     rax, cs:__security_cookie
0x1400934ed  xor     rax, rsp
0x1400934f0  mov     [rbp+var_10], rax
0x1400934f4  mov     edi, r9d
0x1400934f7  mov     [rbp+var_50], r8b
0x1400934fb  mov     rbx, rdx
0x1400934fe  mov     r14, rcx
0x140093501  mov     [rbp+var_40], rdx
0x140093505  mov     esi, 1
0x14009350a  mov     [rbp+var_4C], esi
0x14009350d  xor     edx, edx
0x14009350f  mov     rcx, rbx
0x140093512  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x140093518  nop
0x140093519  mov     [rbp+var_4C], esi
0x14009351c  lea     rdx, aCamcviewScsetv; "CAMCView::ScSetViewExtensionFrame"
0x140093523  mov     rcx, rbx
0x140093526  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14009352c  cmp     byte ptr [r14+363h], 0
0x140093534  jz      loc_140093690
0x14009353a  movups  xmm0, xmmword ptr [r14+4E8h]
0x140093542  movdqu  xmmword ptr [rbp+rc.left], xmm0
0x140093547  mov     edx, cs:?m_sizEdge@CAMCView@@1VCSize@@B; CSize const CAMCView::m_sizEdge
0x14009354d  mov     r8d, cs:dword_1401621CC
0x140093554  neg     r8d; dy
0x140093557  neg     edx; dx
0x140093559  lea     rcx, [rbp+rc]; lprc
0x14009355d  call    cs:__imp_InflateRect
0x140093563  mov     r8d, [rbp+rc.top]
0x140093567  neg     r8d; dy
0x14009356a  mov     edx, [rbp+rc.left]
0x14009356d  neg     edx; dx
0x14009356f  lea     rcx, [rbp+rc]; lprc
0x140093573  call    cs:__imp_OffsetRect
0x140093579  mov     r15d, [rbp+arg_20]
0x14009357d  cmp     r15d, [rbp+rc.left]
0x140093581  cmovl   r15d, [rbp+rc.left]
0x140093586  mov     r12d, [rbp+arg_30]
0x14009358a  cmp     r12d, [rbp+rc.right]
0x14009358e  cmovg   r12d, [rbp+rc.right]
0x140093593  cmp     edi, [rbp+rc.top]
0x140093596  cmovl   edi, [rbp+rc.top]
0x14009359a  mov     [rbp+var_48], edi
0x14009359d  mov     eax, [rbp+arg_28]
0x1400935a0  cmp     eax, [rbp+rc.bottom]
0x1400935a3  cmovg   eax, [rbp+rc.bottom]
0x1400935a7  mov     [rbp+arg_28], eax
0x1400935aa  mov     rcx, r14
0x1400935ad  call    cs:__imp_?GetExStyle@CWnd@@QEBAKXZ; CWnd::GetExStyle(void)
0x1400935b3  bt      eax, 16h
0x1400935b7  jnb     short loc_1400935CC
0x1400935b9  mov     edi, [rbp+rc.right]
0x1400935bc  mov     esi, edi
0x1400935be  sub     esi, r12d
0x1400935c1  add     esi, [rbp+rc.left]
0x1400935c4  sub     edi, r15d
0x1400935c7  add     edi, [rbp+rc.left]
0x1400935ca  jmp     short loc_1400935D2
0x1400935cc  mov     esi, r15d
0x1400935cf  mov     edi, r12d
0x1400935d2  mov     r13d, [r14+4ECh]
0x1400935d9  add     r13d, cs:dword_1401621CC
0x1400935e0  mov     r15d, [r14+4E8h]
0x1400935e7  add     r15d, cs:?m_sizEdge@CAMCView@@1VCSize@@B; CSize const CAMCView::m_sizEdge
0x1400935ee  mov     [rbp+var_44], r15d
0x1400935f2  mov     edx, 1
0x1400935f7  mov     rcx, r14
0x1400935fa  call    ?GetPaneView@CAMCView@@QEAAPEAVCView@@W4ViewPane@CConsoleView@@@Z; CAMCView::GetPaneView(CConsoleView::ViewPane)
0x1400935ff  mov     r14, rax
0x140093602  mov     r8d, 80070057h
0x140093608  mov     rdx, rax
0x14009360b  lea     rcx, [rbp+var_38]
0x14009360f  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x140093614  nop
0x140093615  mov     rdx, rax
0x140093618  mov     rcx, rbx
0x14009361b  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140093621  nop
0x140093622  lea     rcx, [rbp+var_38]
0x140093626  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14009362c  mov     rcx, rbx
0x14009362f  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140093635  test    al, al
0x140093637  jnz     short loc_140093690
0x140093639  add     r15d, esi
0x14009363c  mov     r12d, [rbp+var_48]
0x140093640  add     r12d, r13d
0x140093643  mov     esi, [rbp+var_44]
0x140093646  add     esi, edi
0x140093648  mov     edi, [rbp+arg_28]
0x14009364b  add     edi, r13d
0x14009364e  cmp     [rbp+var_50], al
0x140093651  jz      short loc_140093661
0x140093653  mov     edx, 5
0x140093658  mov     rcx, r14
0x14009365b  call    cs:__imp_?ShowWindow@CWnd@@QEAAHH@Z; CWnd::ShowWindow(int)
0x140093661  test    r14, r14
0x140093664  jnz     short loc_14009366A
0x140093666  xor     ecx, ecx
0x140093668  jmp     short loc_14009366E
0x14009366a  mov     rcx, [r14+40h]; hWnd
0x14009366e  sub     edi, r12d
0x140093671  sub     esi, r15d
0x140093674  mov     [rsp+80h+bRepaint], 1; bRepaint
0x14009367c  mov     [rsp+80h+nHeight], edi; nHeight
0x140093680  mov     r9d, esi; nWidth
0x140093683  mov     r8d, r12d; Y
0x140093686  mov     edx, r15d; X
0x140093689  call    cs:__imp_MoveWindow
0x14009368f  nop
0x140093690  mov     rax, rbx
0x140093693  mov     rcx, [rbp+var_10]
0x140093697  xor     rcx, rsp; StackCookie
0x14009369a  call    __security_check_cookie
0x14009369f  mov     rbx, [rsp+80h+arg_10]
0x1400936a7  add     rsp, 80h
0x1400936ae  pop     r15
0x1400936b0  pop     r14
0x1400936b2  pop     r13
0x1400936b4  pop     r12
0x1400936b6  pop     rdi
0x1400936b7  pop     rsi
0x1400936b8  pop     rbp
0x1400936b9  retn
```
