# CAMCView::ScSetFrameCoord(int,CAMCView::coord_t)

- ea: `0x140092df4`
- end: `0x140092f6d`
- name: `?ScSetFrameCoord@CAMCView@@QEAA?AVSC@mmcerror@@HW4coord_t@1@@Z`
- size: `377`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x1400967cc`
- `0x140096868`
- `0x140096900`
- `0x140096b44`

## callees

- `0x14000c1d0`
- `0x140029a60`
- `0x14004dcdc`
- `0x140083804`
- `0x140092df4`
- `0x140092f74`
- `0x1400e9e10`

## import_xrefs

- `MFC42u!__imp_?MoveWindow@CWnd@@QEAAXHHHHH@Z` at `0x140092f4a`
- `MFC42u!__imp_?MoveWindow@CWnd@@QEAAXHHHHH@Z` at `0x140092f4a`
- `MFC42u!__imp_?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z` at `0x140092ee7`
- `MFC42u!__imp_?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z` at `0x140092ee7`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140092e7b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140092ec1`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140092f14`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140092e7b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140092ec1`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140092f14`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140092e84`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140092eca`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140092f1d`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140092e84`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140092eca`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140092f1d`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140092e2e`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140092e2e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140092e70`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140092eb6`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140092f09`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140092e70`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140092eb6`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140092f09`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140092e46`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140092e46`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
mmcerror::SC *__fastcall CAMCView::ScSetFrameCoord(CAMCView *a1, mmcerror::SC *a2, unsigned int a3, int a4)
{
  CWnd *ParentFrame; // rbx
  __int64 v9; // rax
  CWnd *Parent; // rsi
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  _BYTE v15[24]; // [rsp+38h] [rbp-40h] BYREF
  mmcerror::SC *v16; // [rsp+50h] [rbp-28h]
  struct tagRECT Rect; // [rsp+58h] [rbp-20h] BYREF

  v16 = a2;
  mmcerror::SC::SC(a2, 0);
  mmcerror::SC::SetFunctionName(a2, L"CAMCView::ScSetFrameCoord");
  ParentFrame = CAMCView::GetParentFrame(a1);
  v9 = ScCheckPointers(v15, ParentFrame, 2147500037LL);
  mmcerror::SC::operator=(a2, v9);
  mmcerror::SC::~SC((mmcerror::SC *)v15);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(a2) )
  {
    Parent = CWnd::GetParent(ParentFrame);
    v11 = ScCheckPointers(v15, Parent, 2147500037LL);
    mmcerror::SC::operator=(a2, v11);
    mmcerror::SC::~SC((mmcerror::SC *)v15);
    if ( !(unsigned __int8)mmcerror::SC::operator bool(a2) )
    {
      CWindowRect::CWindowRect(&Rect, ParentFrame);
      CWnd::ScreenToClient(Parent, &Rect);
      v13 = CAMCView::ScSetRectCoord(v12, v15, &Rect, a3, a4);
      mmcerror::SC::operator=(a2, v13);
      mmcerror::SC::~SC((mmcerror::SC *)v15);
      if ( !(unsigned __int8)mmcerror::SC::operator bool(a2) )
        CWnd::MoveWindow(ParentFrame, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 1);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140092df4  push    rbp
0x140092df6  push    rbx
0x140092df7  push    rsi
0x140092df8  push    rdi
0x140092df9  push    r14
0x140092dfb  push    r15
0x140092dfd  mov     rbp, rsp
0x140092e00  sub     rsp, 78h
0x140092e04  mov     rax, cs:__security_cookie
0x140092e0b  xor     rax, rsp
0x140092e0e  mov     [rbp+var_10], rax
0x140092e12  mov     r15d, r9d
0x140092e15  mov     r14d, r8d
0x140092e18  mov     rdi, rdx
0x140092e1b  mov     rbx, rcx
0x140092e1e  mov     [rbp+var_28], rdx
0x140092e22  mov     [rbp+var_48], 1
0x140092e29  xor     edx, edx
0x140092e2b  mov     rcx, rdi
0x140092e2e  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x140092e34  nop
0x140092e35  mov     [rbp+var_48], 1
0x140092e3c  lea     rdx, aCamcviewScsetf_0; "CAMCView::ScSetFrameCoord"
0x140092e43  mov     rcx, rdi
0x140092e46  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x140092e4c  mov     rcx, rbx; this
0x140092e4f  call    ?GetParentFrame@CAMCView@@IEBAPEAVCChildFrame@@XZ; CAMCView::GetParentFrame(void)
0x140092e54  mov     rbx, rax
0x140092e57  mov     r8d, 80004005h
0x140092e5d  mov     rdx, rax
0x140092e60  lea     rcx, [rbp+var_40]
0x140092e64  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x140092e69  nop
0x140092e6a  mov     rdx, rax
0x140092e6d  mov     rcx, rdi
0x140092e70  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140092e76  nop
0x140092e77  lea     rcx, [rbp+var_40]
0x140092e7b  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140092e81  mov     rcx, rdi
0x140092e84  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140092e8a  test    al, al
0x140092e8c  jnz     loc_140092F51
0x140092e92  mov     rcx, rbx; this
0x140092e95  call    ?GetParent@CWnd@@QEBAPEAV1@XZ; CWnd::GetParent(void)
0x140092e9a  mov     rsi, rax
0x140092e9d  mov     r8d, 80004005h
0x140092ea3  mov     rdx, rax
0x140092ea6  lea     rcx, [rbp+var_40]
0x140092eaa  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x140092eaf  nop
0x140092eb0  mov     rdx, rax
0x140092eb3  mov     rcx, rdi
0x140092eb6  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140092ebc  nop
0x140092ebd  lea     rcx, [rbp+var_40]
0x140092ec1  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140092ec7  mov     rcx, rdi
0x140092eca  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140092ed0  test    al, al
0x140092ed2  jnz     short loc_140092F51
0x140092ed4  mov     rdx, rbx; struct CWnd *
0x140092ed7  lea     rcx, [rbp+Rect]; lpRect
0x140092edb  call    ??0CWindowRect@@QEAA@PEBVCWnd@@@Z; CWindowRect::CWindowRect(CWnd const *)
0x140092ee0  lea     rdx, [rbp+Rect]
0x140092ee4  mov     rcx, rsi
0x140092ee7  call    cs:__imp_?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x140092eed  mov     [rsp+78h+var_58], r15d
0x140092ef2  mov     r9d, r14d
0x140092ef5  lea     r8, [rbp+Rect]
0x140092ef9  lea     rdx, [rbp+var_40]
0x140092efd  call    ?ScSetRectCoord@CAMCView@@QEAA?AVSC@mmcerror@@AEAUtagRECT@@HW4coord_t@1@@Z; CAMCView::ScSetRectCoord(tagRECT &,int,CAMCView::coord_t)
0x140092f02  nop
0x140092f03  mov     rdx, rax
0x140092f06  mov     rcx, rdi
0x140092f09  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140092f0f  nop
0x140092f10  lea     rcx, [rbp+var_40]
0x140092f14  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140092f1a  mov     rcx, rdi
0x140092f1d  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140092f23  test    al, al
0x140092f25  jnz     short loc_140092F51
0x140092f27  mov     ecx, [rbp+Rect.bottom]
0x140092f2a  mov     r8d, [rbp+Rect.top]
0x140092f2e  sub     ecx, r8d
0x140092f31  mov     r9d, [rbp+Rect.right]
0x140092f35  mov     edx, [rbp+Rect.left]
0x140092f38  sub     r9d, edx
0x140092f3b  mov     [rsp+78h+var_50], 1
0x140092f43  mov     [rsp+78h+var_58], ecx
0x140092f47  mov     rcx, rbx
0x140092f4a  call    cs:__imp_?MoveWindow@CWnd@@QEAAXHHHHH@Z; CWnd::MoveWindow(int,int,int,int,int)
0x140092f50  nop
0x140092f51  mov     rax, rdi
0x140092f54  mov     rcx, [rbp+var_10]
0x140092f58  xor     rcx, rsp; StackCookie
0x140092f5b  call    __security_check_cookie
0x140092f60  add     rsp, 78h
0x140092f64  pop     r15
0x140092f66  pop     r14
0x140092f68  pop     rdi
0x140092f69  pop     rsi
0x140092f6a  pop     rbx
0x140092f6b  pop     rbp
0x140092f6c  retn
```
