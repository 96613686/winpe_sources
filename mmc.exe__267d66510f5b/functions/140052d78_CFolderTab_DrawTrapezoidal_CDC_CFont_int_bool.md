# CFolderTab::DrawTrapezoidal(CDC &,CFont &,int,bool)

- ea: `0x140052d78`
- end: `0x140053088`
- name: `?DrawTrapezoidal@CFolderTab@@AEAAHAEAVCDC@@AEAVCFont@@H_N@Z`
- size: `784`
- prototype: `int(CFolderTab *__hidden this, struct CDC *, struct CFont *, int, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140052b54`

## callees

- `0x1400253a4`
- `0x140052d78`
- `0x1400575d8`
- `0x14005aa90`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `GDI32!FillRgn` at `0x140052ec8`
- `GDI32!FillRgn` at `0x140052ec8`
- `USER32!DrawFocusRect` at `0x140053027`
- `USER32!DrawFocusRect` at `0x140053027`
- `USER32!GetSysColor` at `0x140052db6`
- `USER32!GetSysColor` at `0x140052dcb`
- `USER32!GetSysColor` at `0x140052e07`
- `USER32!GetSysColor` at `0x140052e26`
- `USER32!GetSysColor` at `0x140052db6`
- `USER32!GetSysColor` at `0x140052dcb`
- `USER32!GetSysColor` at `0x140052e07`
- `USER32!GetSysColor` at `0x140052e26`
- `USER32!InflateRect` at `0x140052fca`
- `USER32!InflateRect` at `0x140052fca`
- `MFC42u!__imp_??0CBrush@@QEAA@K@Z` at `0x140052dd9`
- `MFC42u!__imp_??0CBrush@@QEAA@K@Z` at `0x140052dd9`
- `MFC42u!__imp_??0CPen@@QEAA@HHK@Z` at `0x140052e1a`
- `MFC42u!__imp_??0CPen@@QEAA@HHK@Z` at `0x140052e39`
- `MFC42u!__imp_??0CPen@@QEAA@HHK@Z` at `0x140052e1a`
- `MFC42u!__imp_??0CPen@@QEAA@HHK@Z` at `0x140052e39`
- `MFC42u!__imp_?LineTo@CDC@@QEAAHHH@Z` at `0x140052f02`
- `MFC42u!__imp_?LineTo@CDC@@QEAAHHH@Z` at `0x140052f40`
- `MFC42u!__imp_?LineTo@CDC@@QEAAHHH@Z` at `0x140052f63`
- `MFC42u!__imp_?LineTo@CDC@@QEAAHHH@Z` at `0x140052fac`
- `MFC42u!__imp_?LineTo@CDC@@QEAAHHH@Z` at `0x140052f02`
- `MFC42u!__imp_?LineTo@CDC@@QEAAHHH@Z` at `0x140052f40`
- `MFC42u!__imp_?LineTo@CDC@@QEAAHHH@Z` at `0x140052f63`
- `MFC42u!__imp_?LineTo@CDC@@QEAAHHH@Z` at `0x140052fac`
- `MFC42u!__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z` at `0x140052eec`
- `MFC42u!__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z` at `0x140052f2a`
- `MFC42u!__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z` at `0x140052f96`
- `MFC42u!__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z` at `0x140052eec`
- `MFC42u!__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z` at `0x140052f2a`
- `MFC42u!__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z` at `0x140052f96`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x140052ea6`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x140052f0f`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x140052f4d`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x140052f7b`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x140052fb8`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x140052ea6`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x140052f0f`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x140052f4d`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x140052f7b`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x140052fb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFolderTab::DrawTrapezoidal(CFolderTab *this, HDC *a2, struct CFont *a3, int a4, bool a5)
{
  DWORD SysColor; // edi
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD v12; // eax
  CRect *v13; // rbx
  __int64 v14; // rdi
  __int64 v15; // rcx
  struct CPen *v16; // rbx
  HRGN v17; // rdx
  __int64 v18; // rbx
  unsigned int v19; // ebx
  _BYTE v21[8]; // [rsp+20h] [rbp-51h] BYREF
  _QWORD v22[2]; // [rsp+28h] [rbp-49h] BYREF
  _QWORD v23[2]; // [rsp+38h] [rbp-39h] BYREF
  _QWORD v24[2]; // [rsp+48h] [rbp-29h] BYREF
  struct tagRECT rc; // [rsp+58h] [rbp-19h] BYREF
  unsigned __int64 v26; // [rsp+68h] [rbp-9h] BYREF
  unsigned __int64 v27; // [rsp+70h] [rbp-1h]
  unsigned __int64 v28; // [rsp+78h] [rbp+7h]
  int v29; // [rsp+80h] [rbp+Fh]
  LONG top; // [rsp+84h] [rbp+13h]

  SysColor = GetSysColor(a4 != 0 ? 5 : 15);
  v10 = GetSysColor(a4 != 0 ? 8 : 18);
  CBrush::CBrush((CBrush *)v24, SysColor);
  (*((void (__fastcall **)(HDC *, _QWORD))*a2 + 13))(a2, SysColor);
  (*((void (__fastcall **)(HDC *, _QWORD))*a2 + 14))(a2, v10);
  v11 = GetSysColor(6);
  CPen::CPen((CPen *)v23, 0, 1, v11);
  v12 = GetSysColor(16);
  CPen::CPen((CPen *)v22, 0, 1, v12);
  v13 = (CRect *)&v26;
  v14 = 4;
  do
  {
    CRect::CRect(v13);
    v13 = (CRect *)((char *)v13 + 8);
    --v14;
  }
  while ( v14 );
  rc = (struct tagRECT)*((_OWORD *)this + 1);
  v26 = __PAIR64__(rc.top, _mm_cvtsi128_si32((__m128i)rc));
  v15 = *((_QWORD *)this + 3);
  LODWORD(v27) = v26 + 8;
  HIDWORD(v27) = HIDWORD(v15);
  LODWORD(v28) = v15 - 9;
  HIDWORD(v28) = HIDWORD(v15);
  v29 = v15 - 1;
  top = rc.top;
  v16 = CDC::SelectObject((CDC *)a2, (struct CPen *)v23);
  if ( this == (CFolderTab *)-32LL )
    v17 = 0;
  else
    v17 = (HRGN)*((_QWORD *)this + 5);
  FillRgn(a2[1], v17, (HBRUSH)v24[1]);
  --HIDWORD(v27);
  --HIDWORD(v28);
  --top;
  CDC::MoveTo(a2, v21, (unsigned int)v26, HIDWORD(v26));
  CDC::LineTo((CDC *)a2, v27, HIDWORD(v27));
  CDC::SelectObject((CDC *)a2, (struct CPen *)v22);
  CDC::MoveTo(a2, v21, (unsigned int)v27, HIDWORD(v27));
  CDC::LineTo((CDC *)a2, v28, HIDWORD(v28));
  CDC::SelectObject((CDC *)a2, (struct CPen *)v23);
  CDC::LineTo((CDC *)a2, v29, top);
  if ( !a4 )
  {
    LODWORD(v28) = v28 - 1;
    --v29;
    CDC::SelectObject((CDC *)a2, (struct CPen *)v22);
    CDC::MoveTo(a2, v21, (unsigned int)v28, HIDWORD(v28));
    CDC::LineTo((CDC *)a2, v29, top);
  }
  CDC::SelectObject((CDC *)a2, v16);
  InflateRect(&rc, -10, -1);
  v18 = (*((__int64 (__fastcall **)(HDC *, struct CFont *))*a2 + 12))(a2, a3);
  CDC::DrawTextW((CDC *)a2, (CFolderTab *)((char *)this + 8), &rc, 0x8025u);
  (*((void (__fastcall **)(HDC *, __int64))*a2 + 12))(a2, v18);
  if ( a5 )
  {
    --rc.top;
    ++rc.bottom;
    --rc.left;
    ++rc.right;
    DrawFocusRect(a2[1], &rc);
  }
  v19 = *((_DWORD *)this + 6);
  v22[0] = &CPen::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)v22);
  v23[0] = &CPen::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)v23);
  v24[0] = &CBrush::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)v24);
  return v19;
}

```

## disassembly

```asm
0x140052d78  push    rbp
0x140052d7a  push    rbx
0x140052d7b  push    rsi
0x140052d7c  push    rdi
0x140052d7d  push    r12
0x140052d7f  push    r14
0x140052d81  push    r15
0x140052d83  lea     rbp, [rsp-1Fh]
0x140052d88  sub     rsp, 90h
0x140052d8f  mov     rax, cs:__security_cookie
0x140052d96  xor     rax, rsp
0x140052d99  mov     [rbp+4Fh+var_38], rax
0x140052d9d  mov     r15d, r9d
0x140052da0  mov     r12, r8
0x140052da3  mov     rsi, rdx
0x140052da6  mov     r14, rcx
0x140052da9  mov     eax, r9d
0x140052dac  neg     eax
0x140052dae  sbb     ecx, ecx
0x140052db0  and     ecx, 0FFFFFFF6h
0x140052db3  add     ecx, 0Fh; nIndex
0x140052db6  call    cs:__imp_GetSysColor
0x140052dbc  mov     edi, eax
0x140052dbe  mov     ecx, r15d
0x140052dc1  neg     ecx
0x140052dc3  sbb     ecx, ecx
0x140052dc5  and     ecx, 0FFFFFFF6h
0x140052dc8  add     ecx, 12h; nIndex
0x140052dcb  call    cs:__imp_GetSysColor
0x140052dd1  mov     ebx, eax
0x140052dd3  mov     edx, edi
0x140052dd5  lea     rcx, [rbp+4Fh+var_78]
0x140052dd9  call    cs:__imp_??0CBrush@@QEAA@K@Z; CBrush::CBrush(ulong)
0x140052ddf  nop
0x140052de0  mov     rcx, [rsi]
0x140052de3  mov     rax, [rcx+68h]
0x140052de7  mov     edx, edi
0x140052de9  mov     rcx, rsi
0x140052dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052df1  mov     rcx, [rsi]
0x140052df4  mov     rax, [rcx+70h]
0x140052df8  mov     edx, ebx
0x140052dfa  mov     rcx, rsi
0x140052dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052e02  mov     ecx, 6; nIndex
0x140052e07  call    cs:__imp_GetSysColor
0x140052e0d  mov     r9d, eax
0x140052e10  xor     edx, edx
0x140052e12  lea     r8d, [rdx+1]
0x140052e16  lea     rcx, [rbp+4Fh+var_88]
0x140052e1a  call    cs:__imp_??0CPen@@QEAA@HHK@Z; CPen::CPen(int,int,ulong)
0x140052e20  nop
0x140052e21  mov     ecx, 10h; nIndex
0x140052e26  call    cs:__imp_GetSysColor
0x140052e2c  mov     r9d, eax
0x140052e2f  xor     edx, edx
0x140052e31  lea     r8d, [rdx+1]
0x140052e35  lea     rcx, [rbp+4Fh+var_98]
0x140052e39  call    cs:__imp_??0CPen@@QEAA@HHK@Z; CPen::CPen(int,int,ulong)
0x140052e3f  nop
0x140052e40  lea     rbx, [rbp+4Fh+var_58]
0x140052e44  mov     edi, 4
0x140052e49  mov     rcx, rbx; this
0x140052e4c  call    ??0CRect@@QEAA@XZ; CRect::CRect(void)
0x140052e51  add     rbx, 8
0x140052e55  sub     rdi, 1
0x140052e59  jnz     short loc_140052E49
0x140052e5b  movups  xmm0, xmmword ptr [r14+10h]
0x140052e60  movups  xmmword ptr [rbp+4Fh+rc.left], xmm0
0x140052e64  movd    eax, xmm0
0x140052e68  movq    r8, xmm0
0x140052e6d  shr     r8, 20h
0x140052e71  mov     dword ptr [rbp+4Fh+var_58], eax
0x140052e74  mov     dword ptr [rbp+4Fh+var_58+4], r8d
0x140052e78  mov     rcx, [r14+18h]
0x140052e7c  mov     rdx, rcx
0x140052e7f  shr     rdx, 20h
0x140052e83  add     eax, 8
0x140052e86  mov     dword ptr [rbp+4Fh+var_50], eax
0x140052e89  mov     dword ptr [rbp+4Fh+var_50+4], edx
0x140052e8c  lea     eax, [rcx-9]
0x140052e8f  mov     dword ptr [rbp+4Fh+var_48], eax
0x140052e92  mov     dword ptr [rbp+4Fh+var_48+4], edx
0x140052e95  lea     eax, [rcx-1]
0x140052e98  mov     dword ptr [rbp+4Fh+var_40], eax
0x140052e9b  mov     dword ptr [rbp+4Fh+var_40+4], r8d
0x140052e9f  lea     rdx, [rbp+4Fh+var_88]
0x140052ea3  mov     rcx, rsi
0x140052ea6  call    cs:__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x140052eac  mov     rbx, rax
0x140052eaf  lea     rcx, [r14+20h]
0x140052eb3  test    rcx, rcx
0x140052eb6  jnz     short loc_140052EBC
0x140052eb8  xor     edx, edx
0x140052eba  jmp     short loc_140052EC0
0x140052ebc  mov     rdx, [rcx+8]; hrgn
0x140052ec0  mov     r8, [rbp+4Fh+hbr]; hbr
0x140052ec4  mov     rcx, [rsi+8]; hdc
0x140052ec8  call    cs:__imp_FillRgn
0x140052ece  dec     dword ptr [rbp+4Fh+var_50+4]
0x140052ed1  dec     dword ptr [rbp+4Fh+var_48+4]
0x140052ed4  dec     dword ptr [rbp+4Fh+var_40+4]
0x140052ed7  mov     rax, [rbp+4Fh+var_58]
0x140052edb  mov     r9, rax
0x140052ede  shr     r9, 20h
0x140052ee2  mov     r8d, eax
0x140052ee5  lea     rdx, [rbp+4Fh+var_A0]
0x140052ee9  mov     rcx, rsi
0x140052eec  call    cs:__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z; CDC::MoveTo(int,int)
0x140052ef2  mov     rax, [rbp+4Fh+var_50]
0x140052ef6  mov     r8, rax
0x140052ef9  shr     r8, 20h
0x140052efd  mov     edx, eax
0x140052eff  mov     rcx, rsi
0x140052f02  call    cs:__imp_?LineTo@CDC@@QEAAHHH@Z; CDC::LineTo(int,int)
0x140052f08  lea     rdx, [rbp+4Fh+var_98]
0x140052f0c  mov     rcx, rsi
0x140052f0f  call    cs:__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x140052f15  mov     rax, [rbp+4Fh+var_50]
0x140052f19  mov     r9, rax
0x140052f1c  shr     r9, 20h
0x140052f20  mov     r8d, eax
0x140052f23  lea     rdx, [rbp+4Fh+var_A0]
0x140052f27  mov     rcx, rsi
0x140052f2a  call    cs:__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z; CDC::MoveTo(int,int)
0x140052f30  mov     rax, [rbp+4Fh+var_48]
0x140052f34  mov     r8, rax
0x140052f37  shr     r8, 20h
0x140052f3b  mov     edx, eax
0x140052f3d  mov     rcx, rsi
0x140052f40  call    cs:__imp_?LineTo@CDC@@QEAAHHH@Z; CDC::LineTo(int,int)
0x140052f46  lea     rdx, [rbp+4Fh+var_88]
0x140052f4a  mov     rcx, rsi
0x140052f4d  call    cs:__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x140052f53  mov     rax, [rbp+4Fh+var_40]
0x140052f57  mov     r8, rax
0x140052f5a  shr     r8, 20h
0x140052f5e  mov     edx, eax
0x140052f60  mov     rcx, rsi
0x140052f63  call    cs:__imp_?LineTo@CDC@@QEAAHHH@Z; CDC::LineTo(int,int)
0x140052f69  test    r15d, r15d
0x140052f6c  jnz     short loc_140052FB2
0x140052f6e  dec     dword ptr [rbp+4Fh+var_48]
0x140052f71  dec     dword ptr [rbp+4Fh+var_40]
0x140052f74  lea     rdx, [rbp+4Fh+var_98]
0x140052f78  mov     rcx, rsi
0x140052f7b  call    cs:__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x140052f81  mov     rax, [rbp+4Fh+var_48]
0x140052f85  mov     r9, rax
0x140052f88  shr     r9, 20h
0x140052f8c  mov     r8d, eax
0x140052f8f  lea     rdx, [rbp+4Fh+var_A0]
0x140052f93  mov     rcx, rsi
0x140052f96  call    cs:__imp_?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z; CDC::MoveTo(int,int)
0x140052f9c  mov     rax, [rbp+4Fh+var_40]
0x140052fa0  mov     r8, rax
0x140052fa3  shr     r8, 20h
0x140052fa7  mov     edx, eax
0x140052fa9  mov     rcx, rsi
0x140052fac  call    cs:__imp_?LineTo@CDC@@QEAAHHH@Z; CDC::LineTo(int,int)
0x140052fb2  mov     rdx, rbx
0x140052fb5  mov     rcx, rsi
0x140052fb8  call    cs:__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x140052fbe  or      r8d, 0FFFFFFFFh; dy
0x140052fc2  lea     edx, [r8-9]; dx
0x140052fc6  lea     rcx, [rbp+4Fh+rc]; lprc
0x140052fca  call    cs:__imp_InflateRect
0x140052fd0  mov     rax, [rsi]
0x140052fd3  mov     rdx, r12
0x140052fd6  mov     rcx, rsi
0x140052fd9  mov     rax, [rax+60h]
0x140052fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052fe2  mov     rbx, rax
0x140052fe5  lea     rdx, [r14+8]; struct CString *
0x140052fe9  mov     r9d, 8025h; unsigned int
0x140052fef  lea     r8, [rbp+4Fh+rc]; struct tagRECT *
0x140052ff3  mov     rcx, rsi; this
0x140052ff6  call    ?DrawTextW@CDC@@QEAAHAEBVCString@@PEAUtagRECT@@I@Z; CDC::DrawTextW(CString const &,tagRECT *,uint)
0x140052ffb  mov     rcx, [rsi]
0x140052ffe  mov     rax, [rcx+60h]
0x140053002  mov     rdx, rbx
0x140053005  mov     rcx, rsi
0x140053008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005300d  cmp     [rbp+4Fh+arg_20], 0
0x140053011  jz      short loc_14005302D
0x140053013  dec     [rbp+4Fh+rc.top]
0x140053016  inc     [rbp+4Fh+rc.bottom]
0x140053019  dec     [rbp+4Fh+rc.left]
0x14005301c  inc     [rbp+4Fh+rc.right]
0x14005301f  lea     rdx, [rbp+4Fh+rc]; lprc
0x140053023  mov     rcx, [rsi+8]; hDC
0x140053027  call    cs:__imp_DrawFocusRect
0x14005302d  mov     ebx, [r14+18h]
0x140053031  lea     rdi, ??_7CPen@@6B@; const CPen::`vftable'
0x140053038  mov     [rbp+4Fh+var_98], rdi
0x14005303c  lea     rcx, [rbp+4Fh+var_98]; this
0x140053040  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x140053045  nop
0x140053046  mov     [rbp+4Fh+var_88], rdi
0x14005304a  lea     rcx, [rbp+4Fh+var_88]; this
0x14005304e  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x140053053  nop
0x140053054  lea     rax, ??_7CBrush@@6B@; const CBrush::`vftable'
0x14005305b  mov     [rbp+4Fh+var_78], rax
0x14005305f  lea     rcx, [rbp+4Fh+var_78]; this
0x140053063  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x140053068  mov     eax, ebx
0x14005306a  mov     rcx, [rbp+4Fh+var_38]
0x14005306e  xor     rcx, rsp; StackCookie
0x140053071  call    __security_check_cookie
0x140053076  add     rsp, 90h
0x14005307d  pop     r15
0x14005307f  pop     r14
0x140053081  pop     r12
0x140053083  pop     rdi
0x140053084  pop     rsi
0x140053085  pop     rbx
0x140053086  pop     rbp
0x140053087  retn
```
