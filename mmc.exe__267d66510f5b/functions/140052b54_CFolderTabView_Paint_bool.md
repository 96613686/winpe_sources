# CFolderTabView::Paint(bool)

- ea: `0x140052b54`
- end: `0x140052d72`
- name: `?Paint@CFolderTabView@@IEAAX_N@Z`
- size: `542`
- prototype: `void(CFolderTabView *__hidden this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400b7480`

## callees

- `0x1400253a4`
- `0x140052b54`
- `0x140052d78`
- `0x14005aa90`
- `0x1400e9e10`

## import_xrefs

- `USER32!GetSysColor` at `0x140052c96`
- `USER32!GetSysColor` at `0x140052c96`
- `USER32!GetClientRect` at `0x140052b9e`
- `USER32!GetClientRect` at `0x140052b9e`
- `USER32!CopyRect` at `0x140052c59`
- `USER32!CopyRect` at `0x140052c59`
- `MFC42u!__imp_??0CPaintDC@@QEAA@PEAVCWnd@@@Z` at `0x140052b8e`
- `MFC42u!__imp_??0CPaintDC@@QEAA@PEAVCWnd@@@Z` at `0x140052b8e`
- `MFC42u!__imp_??0CPen@@QEAA@HHK@Z` at `0x140052caa`
- `MFC42u!__imp_??0CPen@@QEAA@HHK@Z` at `0x140052caa`
- `MFC42u!__imp_??1CPaintDC@@UEAA@XZ` at `0x140052d44`
- `MFC42u!__imp_??1CPaintDC@@UEAA@XZ` at `0x140052d44`
- `MFC42u!__imp_?LineTo@CDC@@QEAAHHH@Z` at `0x140052cea`
- `MFC42u!__imp_?LineTo@CDC@@QEAAHHH@Z` at `0x140052d13`
- `MFC42u!__imp_?LineTo@CDC@@QEAAHHH@Z` at `0x140052cea`
- `MFC42u!__imp_?LineTo@CDC@@QEAAHHH@Z` at `0x140052d13`
- `MFC42u!__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z` at `0x140052cd9`
- `MFC42u!__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z` at `0x140052d01`
- `MFC42u!__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z` at `0x140052cd9`
- `MFC42u!__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z` at `0x140052d01`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x140052cbb`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x140052d21`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x140052cbb`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x140052d21`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CFolderTabView::Paint(HWND *this, bool a2)
{
  HWND v4; // rdi
  int v5; // r14d
  char v6; // r15
  _QWORD *v7; // rbx
  HWND v8; // rax
  LONG v9; // eax
  CRect *v10; // rbx
  __int64 v11; // rsi
  DWORD SysColor; // eax
  struct CPen *v13; // rdi
  unsigned int v14; // ebx
  _QWORD v15[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct tagRECT rcDst; // [rsp+40h] [rbp-C0h] BYREF
  struct tagRECT Rect; // [rsp+50h] [rbp-B0h] BYREF
  RECT rcSrc; // [rsp+60h] [rbp-A0h] BYREF
  HDC v19[14]; // [rsp+70h] [rbp-90h] BYREF
  LONG left; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int top; // [rsp+E4h] [rbp-1Ch]
  int v22; // [rsp+E8h] [rbp-18h]
  LONG bottom; // [rsp+ECh] [rbp-14h]
  int v24; // [rsp+F0h] [rbp-10h]
  LONG v25; // [rsp+F4h] [rbp-Ch]
  unsigned int v26; // [rsp+F8h] [rbp-8h]
  LONG v27; // [rsp+FCh] [rbp-4h]

  CPaintDC::CPaintDC((CPaintDC *)v19, (struct CWnd *)this);
  GetClientRect(this[8], &Rect);
  v4 = this[21];
  v5 = 0;
  v6 = 1;
  v7 = *(_QWORD **)v4;
  while ( 1 )
  {
    v8 = this[21];
    if ( v7 == (_QWORD *)v8 )
      break;
    if ( v5 == *((_DWORD *)this + 46) )
    {
      v4 = (HWND)v7;
    }
    else if ( v6 )
    {
      v9 = CFolderTab::DrawTrapezoidal((CFolderTab *)(v7 + 2), v19, (struct CFont *)(this + 24), 0, 0);
      if ( v9 > Rect.right )
        v6 = 0;
    }
    v7 = (_QWORD *)*v7;
    ++v5;
  }
  if ( v4 != v8 )
  {
    CFolderTab::DrawTrapezoidal((CFolderTab *)(v4 + 4), v19, (struct CFont *)(this + 24), 1, a2);
    v10 = (CRect *)&left;
    v11 = 4;
    do
    {
      CRect::CRect(v10);
      v10 = (CRect *)((char *)v10 + 8);
      --v11;
    }
    while ( v11 );
    rcSrc = (RECT)*((_OWORD *)v4 + 2);
    CopyRect(&rcDst, &rcSrc);
    left = rcDst.left;
    top = rcDst.top;
    v22 = rcDst.left + 8;
    bottom = rcDst.bottom;
    v24 = rcDst.right - 9;
    v25 = rcDst.bottom;
    v26 = rcDst.right - 1;
    v27 = rcDst.top;
    SysColor = GetSysColor(6);
    CPen::CPen((CPen *)v15, 0, 1, SysColor);
    v13 = CDC::SelectObject((CDC *)v19, (struct CPen *)v15);
    v14 = top;
    CDC::MoveTo(v19, &rcDst, (unsigned int)Rect.left, top);
    CDC::LineTo((CDC *)v19, left, v14);
    CDC::MoveTo(v19, &rcDst, v26, v14);
    CDC::LineTo((CDC *)v19, Rect.right, v14);
    CDC::SelectObject((CDC *)v19, v13);
    v15[0] = &CPen::`vftable';
    CGdiObject::~CGdiObject((CGdiObject *)v15);
  }
  CPaintDC::~CPaintDC((CPaintDC *)v19);
}

```

## disassembly

```asm
0x140052b54  mov     [rsp-8+arg_8], rbx
0x140052b59  mov     [rsp-8+arg_10], rsi
0x140052b5e  push    rbp
0x140052b5f  push    rdi
0x140052b60  push    r12
0x140052b62  push    r14
0x140052b64  push    r15
0x140052b66  lea     rbp, [rsp-10h]
0x140052b6b  sub     rsp, 110h
0x140052b72  mov     rax, cs:__security_cookie
0x140052b79  xor     rax, rsp
0x140052b7c  mov     [rbp+30h+var_30], rax
0x140052b80  mov     r12b, dl
0x140052b83  mov     rsi, rcx
0x140052b86  mov     rdx, rcx
0x140052b89  lea     rcx, [rsp+130h+var_C0]
0x140052b8e  call    cs:__imp_??0CPaintDC@@QEAA@PEAVCWnd@@@Z; CPaintDC::CPaintDC(CWnd *)
0x140052b94  nop
0x140052b95  lea     rdx, [rsp+130h+Rect]; lpRect
0x140052b9a  mov     rcx, [rsi+40h]; hWnd
0x140052b9e  call    cs:__imp_GetClientRect
0x140052ba4  mov     rdi, [rsi+0A8h]
0x140052bab  xor     r14d, r14d
0x140052bae  mov     r15b, 1
0x140052bb1  mov     rbx, [rdi]
0x140052bb4  mov     rax, [rsi+0A8h]
0x140052bbb  cmp     rbx, rax
0x140052bbe  jz      short loc_140052C01
0x140052bc0  cmp     r14d, [rsi+0B8h]
0x140052bc7  jz      short loc_140052BF6
0x140052bc9  test    r15b, r15b
0x140052bcc  jz      short loc_140052BF9
0x140052bce  lea     r8, [rsi+0C0h]; struct CFont *
0x140052bd5  lea     rcx, [rbx+10h]; this
0x140052bd9  mov     [rsp+130h+var_110], 0; bool
0x140052bde  xor     r9d, r9d; int
0x140052be1  lea     rdx, [rsp+130h+var_C0]; struct CDC *
0x140052be6  call    ?DrawTrapezoidal@CFolderTab@@AEAAHAEAVCDC@@AEAVCFont@@H_N@Z; CFolderTab::DrawTrapezoidal(CDC &,CFont &,int,bool)
0x140052beb  cmp     eax, [rsp+130h+Rect.right]
0x140052bef  jle     short loc_140052BF9
0x140052bf1  xor     r15b, r15b
0x140052bf4  jmp     short loc_140052BF9
0x140052bf6  mov     rdi, rbx
0x140052bf9  mov     rbx, [rbx]
0x140052bfc  inc     r14d
0x140052bff  jmp     short loc_140052BB4
0x140052c01  cmp     rdi, rax
0x140052c04  jz      loc_140052D3F
0x140052c0a  lea     rcx, [rdi+10h]; this
0x140052c0e  lea     r8, [rsi+0C0h]; struct CFont *
0x140052c15  mov     [rsp+130h+var_110], r12b; bool
0x140052c1a  mov     r9d, 1; int
0x140052c20  lea     rdx, [rsp+130h+var_C0]; struct CDC *
0x140052c25  call    ?DrawTrapezoidal@CFolderTab@@AEAAHAEAVCDC@@AEAVCFont@@H_N@Z; CFolderTab::DrawTrapezoidal(CDC &,CFont &,int,bool)
0x140052c2a  lea     rbx, [rbp+30h+var_50]
0x140052c2e  mov     esi, 4
0x140052c33  mov     rcx, rbx; this
0x140052c36  call    ??0CRect@@QEAA@XZ; CRect::CRect(void)
0x140052c3b  add     rbx, 8
0x140052c3f  sub     rsi, 1
0x140052c43  jnz     short loc_140052C33
0x140052c45  movups  xmm0, xmmword ptr [rdi+20h]
0x140052c49  movdqu  xmmword ptr [rsp+130h+rcSrc.left], xmm0
0x140052c4f  lea     rdx, [rsp+130h+rcSrc]; lprcSrc
0x140052c54  lea     rcx, [rsp+130h+rcDst]; lprcDst
0x140052c59  call    cs:__imp_CopyRect
0x140052c5f  mov     eax, [rsp+130h+rcDst.left]
0x140052c63  mov     r9d, [rsp+130h+rcDst.top]
0x140052c68  mov     [rbp+30h+var_50], eax
0x140052c6b  mov     [rbp+30h+var_4C], r9d
0x140052c6f  mov     edx, [rsp+130h+rcDst.bottom]
0x140052c73  add     eax, 8
0x140052c76  mov     [rbp+30h+var_48], eax
0x140052c79  mov     [rbp+30h+var_44], edx
0x140052c7c  mov     ecx, [rsp+130h+rcDst.right]
0x140052c80  lea     eax, [rcx-9]
0x140052c83  mov     [rbp+30h+var_40], eax
0x140052c86  mov     [rbp+30h+var_3C], edx
0x140052c89  lea     eax, [rcx-1]
0x140052c8c  mov     [rbp+30h+var_38], eax
0x140052c8f  mov     [rbp+30h+var_34], r9d
0x140052c93  lea     ecx, [rsi+6]; nIndex
0x140052c96  call    cs:__imp_GetSysColor
0x140052c9c  mov     r9d, eax
0x140052c9f  xor     edx, edx
0x140052ca1  lea     r8d, [rsi+1]
0x140052ca5  lea     rcx, [rsp+130h+var_100]
0x140052caa  call    cs:__imp_??0CPen@@QEAA@HHK@Z; CPen::CPen(int,int,ulong)
0x140052cb0  nop
0x140052cb1  lea     rdx, [rsp+130h+var_100]
0x140052cb6  lea     rcx, [rsp+130h+var_C0]
0x140052cbb  call    cs:__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x140052cc1  mov     rdi, rax
0x140052cc4  mov     ebx, [rbp+30h+var_4C]
0x140052cc7  mov     r9d, ebx
0x140052cca  mov     r8d, [rsp+130h+Rect.left]
0x140052ccf  lea     rdx, [rsp+130h+rcDst]
0x140052cd4  lea     rcx, [rsp+130h+var_C0]
0x140052cd9  call    cs:__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z; CDC::MoveTo(int,int)
0x140052cdf  mov     r8d, ebx
0x140052ce2  mov     edx, [rbp+30h+var_50]
0x140052ce5  lea     rcx, [rsp+130h+var_C0]
0x140052cea  call    cs:__imp_?LineTo@CDC@@QEAAHHH@Z; CDC::LineTo(int,int)
0x140052cf0  mov     r9d, ebx
0x140052cf3  mov     r8d, [rbp+30h+var_38]
0x140052cf7  lea     rdx, [rsp+130h+rcDst]
0x140052cfc  lea     rcx, [rsp+130h+var_C0]
0x140052d01  call    cs:__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z; CDC::MoveTo(int,int)
0x140052d07  mov     r8d, ebx
0x140052d0a  mov     edx, [rsp+130h+Rect.right]
0x140052d0e  lea     rcx, [rsp+130h+var_C0]
0x140052d13  call    cs:__imp_?LineTo@CDC@@QEAAHHH@Z; CDC::LineTo(int,int)
0x140052d19  mov     rdx, rdi
0x140052d1c  lea     rcx, [rsp+130h+var_C0]
0x140052d21  call    cs:__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x140052d27  nop
0x140052d28  lea     rax, ??_7CPen@@6B@; const CPen::`vftable'
0x140052d2f  mov     [rsp+130h+var_100], rax
0x140052d34  lea     rcx, [rsp+130h+var_100]; this
0x140052d39  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x140052d3e  nop
0x140052d3f  lea     rcx, [rsp+130h+var_C0]
0x140052d44  call    cs:__imp_??1CPaintDC@@UEAA@XZ; CPaintDC::~CPaintDC(void)
0x140052d4a  mov     rcx, [rbp+30h+var_30]
0x140052d4e  xor     rcx, rsp; StackCookie
0x140052d51  call    __security_check_cookie
0x140052d56  lea     r11, [rsp+130h+var_20]
0x140052d5e  mov     rbx, [r11+38h]
0x140052d62  mov     rsi, [r11+40h]
0x140052d66  mov     rsp, r11
0x140052d69  pop     r15
0x140052d6b  pop     r14
0x140052d6d  pop     r12
0x140052d6f  pop     rdi
0x140052d70  pop     rbp
0x140052d71  retn
```
