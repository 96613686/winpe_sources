# CIconControl::OnDraw(ATL_DRAWINFO &)

- ea: `0x180093c10`
- end: `0x180093e8c`
- name: `?OnDraw@CIconControl@@UEAAJAEAUATL_DRAWINFO@@@Z`
- size: `636`
- prototype: `__int64 __fastcall(CIconControl *__hidden this, struct ATL_DRAWINFO *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800732a0`
- `0x180093be0`
- `0x180093c10`
- `0x180093e94`

## import_xrefs

- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x180093e24`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x180093e24`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180093ca0`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180093e54`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180093ca0`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180093e54`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180093c31`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180093c31`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x180093c96`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x180093e2e`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x180093c96`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x180093e2e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180093c6a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180093c6a`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180093c43`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180093c43`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180093c7f`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180093c7f`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180093c75`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180093e74`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180093c75`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180093e74`
- `USER32!FillRect` at `0x180093cd2`
- `USER32!FillRect` at `0x180093cd2`
- `USER32!DrawIconEx` at `0x180093e16`
- `USER32!DrawIconEx` at `0x180093e16`
- `USER32!GetSysColor` at `0x180093cb2`
- `USER32!GetSysColor` at `0x180093d2d`
- `USER32!GetSysColor` at `0x180093cb2`
- `USER32!GetSysColor` at `0x180093d2d`
- `GDI32!DPtoLP` at `0x180093dd5`
- `GDI32!DPtoLP` at `0x180093dd5`
- `GDI32!GetLayout` at `0x180093d98`
- `GDI32!GetLayout` at `0x180093d98`
- `GDI32!LPtoDP` at `0x180093db2`
- `GDI32!LPtoDP` at `0x180093db2`
- `GDI32!SetLayout` at `0x180093dc1`
- `GDI32!SetLayout` at `0x180093e4a`
- `GDI32!SetLayout` at `0x180093dc1`
- `GDI32!SetLayout` at `0x180093e4a`
- `GDI32!FillRgn` at `0x180093d48`
- `GDI32!FillRgn` at `0x180093d48`
- `GDI32!CreateRoundRectRgn` at `0x180093d1b`
- `GDI32!CreateRoundRectRgn` at `0x180093d1b`
- `GDI32!CreateSolidBrush` at `0x180093cbb`
- `GDI32!CreateSolidBrush` at `0x180093d35`
- `GDI32!CreateSolidBrush` at `0x180093cbb`
- `GDI32!CreateSolidBrush` at `0x180093d35`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CIconControl::OnDraw(HICON *this, struct ATL_DRAWINFO *a2)
{
  const RECT *v4; // r15
  __int64 v5; // rax
  unsigned int v6; // ebx
  COLORREF SysColor; // eax
  HDC v8; // rdi
  const RECT *p_right; // r8
  LONG left; // ecx
  HRGN RoundRectRgn; // rbx
  COLORREF v12; // eax
  char v13; // cl
  LONG v14; // eax
  DWORD Layout; // ebx
  _BYTE v17[24]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v18[72]; // [rsp+68h] [rbp+Fh] BYREF
  struct tagPOINT pt; // [rsp+C0h] [rbp+67h] BYREF
  HBRUSH v20; // [rsp+C8h] [rbp+6Fh] BYREF
  HBRUSH SolidBrush; // [rsp+D0h] [rbp+77h] BYREF
  HRGN v22; // [rsp+D8h] [rbp+7Fh] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v17, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v17, L"CIconControl::OnDraw");
  v4 = (const RECT *)*((_QWORD *)a2 + 5);
  if ( ((_BYTE)this[37] & 2) == 0 )
  {
    v5 = CIconControl::ScConnectToAMCViewForImageInfo(this, v18);
    mmcerror::SC::operator=(v17, v5);
    mmcerror::SC::~SC((mmcerror::SC *)v18);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v17) )
      goto LABEL_5;
  }
  if ( ((_BYTE)this[37] & 1) == 0 )
  {
    mmcerror::SC::TraceAndClear((mmcerror::SC *)v17);
LABEL_5:
    v6 = mmcerror::SC::ToHr((mmcerror::SC *)v17);
    goto LABEL_23;
  }
  SysColor = GetSysColor(2);
  SolidBrush = CreateSolidBrush(SysColor);
  v8 = (HDC)*((_QWORD *)a2 + 4);
  FillRect(v8, v4, SolidBrush);
  if ( *((_DWORD *)this + 75) )
  {
    if ( *((_BYTE *)this + 304) )
    {
      left = v4->left;
      p_right = v4;
    }
    else
    {
      p_right = (const RECT *)&v4->right;
      left = v4->right;
    }
    RoundRectRgn = CreateRoundRectRgn(left - 10, v4->bottom - 10, p_right->left + 10, v4->bottom + 10, 20, 20);
    v22 = RoundRectRgn;
    v12 = GetSysColor(5);
    v20 = CreateSolidBrush(v12);
    FillRgn(v8, RoundRectRgn, v20);
    WTL::CRgnT<1>::~CRgnT<1>(&v20);
    WTL::CRgnT<1>::~CRgnT<1>(&v22);
  }
  v20 = 0;
  v13 = *((_BYTE *)this + 304);
  if ( v13 )
    v14 = v4->right - 11;
  else
    v14 = v4->left + 10;
  pt.x = v14;
  pt.y = v4->top + 5;
  Layout = 0;
  if ( v13 )
  {
    Layout = GetLayout(*((HDC *)a2 + 4));
    if ( (Layout & 1) == 0 )
    {
      LPtoDP(*((HDC *)a2 + 4), &pt, 1);
      SetLayout(*((HDC *)a2 + 4), Layout | 1);
      DPtoLP(*((HDC *)a2 + 4), &pt, 1);
    }
  }
  if ( DrawIconEx(*((HDC *)a2 + 4), pt.x, pt.y, this[36], 0, 0, 0, 0, 3u) )
  {
    if ( *((_BYTE *)this + 304) && (Layout & 1) == 0 )
      SetLayout(*((HDC *)a2 + 4), Layout);
  }
  else
  {
    mmcerror::SC::FromLastError((mmcerror::SC *)v17);
    mmcerror::SC::TraceAndClear((mmcerror::SC *)v17);
  }
  v6 = mmcerror::SC::ToHr((mmcerror::SC *)v17);
  WTL::CDCT<1>::~CDCT<1>(&v20);
  WTL::CRgnT<1>::~CRgnT<1>(&SolidBrush);
LABEL_23:
  mmcerror::SC::~SC((mmcerror::SC *)v17);
  return v6;
}

```

## disassembly

```asm
0x180093c10  push    rbp
0x180093c12  push    rbx
0x180093c13  push    rsi
0x180093c14  push    rdi
0x180093c15  push    r14
0x180093c17  push    r15
0x180093c19  lea     rbp, [rsp-2Fh]
0x180093c1e  sub     rsp, 88h
0x180093c25  mov     r14, rdx
0x180093c28  mov     rsi, rcx
0x180093c2b  xor     edx, edx
0x180093c2d  lea     rcx, [rbp+57h+var_60]
0x180093c31  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x180093c37  nop
0x180093c38  lea     rdx, aCiconcontrolOn; "CIconControl::OnDraw"
0x180093c3f  lea     rcx, [rbp+57h+var_60]
0x180093c43  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x180093c49  mov     r15, [r14+28h]
0x180093c4d  test    byte ptr [rsi+128h], 2
0x180093c54  jnz     short loc_180093C89
0x180093c56  lea     rdx, [rbp+57h+var_48]
0x180093c5a  mov     rcx, rsi
0x180093c5d  call    ?ScConnectToAMCViewForImageInfo@CIconControl@@AEAA?AVSC@mmcerror@@XZ; CIconControl::ScConnectToAMCViewForImageInfo(void)
0x180093c62  nop
0x180093c63  mov     rdx, rax
0x180093c66  lea     rcx, [rbp+57h+var_60]
0x180093c6a  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180093c70  nop
0x180093c71  lea     rcx, [rbp+57h+var_48]
0x180093c75  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180093c7b  lea     rcx, [rbp+57h+var_60]
0x180093c7f  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180093c85  test    al, al
0x180093c87  jnz     short loc_180093C9C
0x180093c89  test    byte ptr [rsi+128h], 1
0x180093c90  jnz     short loc_180093CAD
0x180093c92  lea     rcx, [rbp+57h+var_60]
0x180093c96  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x180093c9c  lea     rcx, [rbp+57h+var_60]
0x180093ca0  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180093ca6  mov     ebx, eax
0x180093ca8  jmp     loc_180093E70
0x180093cad  mov     ecx, 2; nIndex
0x180093cb2  call    cs:__imp_GetSysColor
0x180093cb8  nop
0x180093cb9  mov     ecx, eax; color
0x180093cbb  call    cs:__imp_CreateSolidBrush
0x180093cc1  mov     [rbp+57h+arg_10], rax
0x180093cc5  mov     rdi, [r14+20h]
0x180093cc9  mov     r8, rax; hbr
0x180093ccc  mov     rdx, r15; lprc
0x180093ccf  mov     rcx, rdi; hDC
0x180093cd2  call    cs:__imp_FillRect
0x180093cd8  cmp     dword ptr [rsi+12Ch], 0
0x180093cdf  jz      short loc_180093D60
0x180093ce1  cmp     byte ptr [rsi+130h], 0
0x180093ce8  jnz     short loc_180093CF3
0x180093cea  lea     r8, [r15+8]
0x180093cee  mov     ecx, [r8]
0x180093cf1  jmp     short loc_180093CF9
0x180093cf3  mov     ecx, [r15]
0x180093cf6  mov     r8, r15
0x180093cf9  mov     edx, [r15+0Ch]
0x180093cfd  lea     r9d, [rdx+0Ah]; y2
0x180093d01  mov     r8d, [r8]
0x180093d04  add     r8d, 0Ah; x2
0x180093d08  add     edx, 0FFFFFFF6h; y1
0x180093d0b  add     ecx, 0FFFFFFF6h; x1
0x180093d0e  mov     eax, 14h
0x180093d13  mov     [rsp+0B0h+h], eax; h
0x180093d17  mov     [rsp+0B0h+w], eax; w
0x180093d1b  call    cs:__imp_CreateRoundRectRgn
0x180093d21  mov     rbx, rax
0x180093d24  mov     [rbp+57h+arg_18], rax
0x180093d28  mov     ecx, 5; nIndex
0x180093d2d  call    cs:__imp_GetSysColor
0x180093d33  mov     ecx, eax; color
0x180093d35  call    cs:__imp_CreateSolidBrush
0x180093d3b  mov     [rbp+57h+arg_8], rax
0x180093d3f  mov     r8, rax; hbr
0x180093d42  mov     rdx, rbx; hrgn
0x180093d45  mov     rcx, rdi; hdc
0x180093d48  call    cs:__imp_FillRgn
0x180093d4e  lea     rcx, [rbp+57h+arg_8]
0x180093d52  call    ??1?$CRgnT@$00@WTL@@QEAA@XZ; WTL::CRgnT<1>::~CRgnT<1>(void)
0x180093d57  lea     rcx, [rbp+57h+arg_18]
0x180093d5b  call    ??1?$CRgnT@$00@WTL@@QEAA@XZ; WTL::CRgnT<1>::~CRgnT<1>(void)
0x180093d60  mov     [rbp+57h+arg_8], 0
0x180093d68  mov     cl, [rsi+130h]
0x180093d6e  test    cl, cl
0x180093d70  jnz     short loc_180093D7A
0x180093d72  mov     eax, [r15]
0x180093d75  add     eax, 0Ah
0x180093d78  jmp     short loc_180093D81
0x180093d7a  mov     eax, [r15+8]
0x180093d7e  sub     eax, 0Bh
0x180093d81  mov     [rbp+57h+pt.x], eax
0x180093d84  mov     eax, [r15+4]
0x180093d88  add     eax, 5
0x180093d8b  mov     [rbp+57h+pt.y], eax
0x180093d8e  xor     ebx, ebx
0x180093d90  test    cl, cl
0x180093d92  jz      short loc_180093DDB
0x180093d94  mov     rcx, [r14+20h]; hdc
0x180093d98  call    cs:__imp_GetLayout
0x180093d9e  mov     ebx, eax
0x180093da0  test    al, 1
0x180093da2  jnz     short loc_180093DDB
0x180093da4  mov     r8d, 1; c
0x180093daa  lea     rdx, [rbp+57h+pt]; lppt
0x180093dae  mov     rcx, [r14+20h]; hdc
0x180093db2  call    cs:__imp_LPtoDP
0x180093db8  mov     edx, ebx
0x180093dba  or      edx, 1; l
0x180093dbd  mov     rcx, [r14+20h]; hdc
0x180093dc1  call    cs:__imp_SetLayout
0x180093dc7  mov     r8d, 1; c
0x180093dcd  lea     rdx, [rbp+57h+pt]; lppt
0x180093dd1  mov     rcx, [r14+20h]; hdc
0x180093dd5  call    cs:__imp_DPtoLP
0x180093ddb  mov     [rsp+0B0h+diFlags], 3; diFlags
0x180093de3  mov     [rsp+0B0h+hbrFlickerFreeDraw], 0; hbrFlickerFreeDraw
0x180093dec  mov     [rsp+0B0h+istepIfAniCur], 0; istepIfAniCur
0x180093df4  mov     [rsp+0B0h+h], 0; cyWidth
0x180093dfc  mov     [rsp+0B0h+w], 0; cxWidth
0x180093e04  mov     r9, [rsi+120h]; hIcon
0x180093e0b  mov     r8d, [rbp+57h+pt.y]; yTop
0x180093e0f  mov     edx, [rbp+57h+pt.x]; xLeft
0x180093e12  mov     rcx, [r14+20h]; hdc
0x180093e16  call    cs:__imp_DrawIconEx
0x180093e1c  test    eax, eax
0x180093e1e  jnz     short loc_180093E36
0x180093e20  lea     rcx, [rbp+57h+var_60]
0x180093e24  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x180093e2a  lea     rcx, [rbp+57h+var_60]
0x180093e2e  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x180093e34  jmp     short loc_180093E50
0x180093e36  cmp     byte ptr [rsi+130h], 0
0x180093e3d  jz      short loc_180093E50
0x180093e3f  test    bl, 1
0x180093e42  jnz     short loc_180093E50
0x180093e44  mov     edx, ebx; l
0x180093e46  mov     rcx, [r14+20h]; hdc
0x180093e4a  call    cs:__imp_SetLayout
0x180093e50  lea     rcx, [rbp+57h+var_60]
0x180093e54  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180093e5a  mov     ebx, eax
0x180093e5c  lea     rcx, [rbp+57h+arg_8]
0x180093e60  call    ??1?$CDCT@$00@WTL@@QEAA@XZ; WTL::CDCT<1>::~CDCT<1>(void)
0x180093e65  nop
0x180093e66  lea     rcx, [rbp+57h+arg_10]
0x180093e6a  call    ??1?$CRgnT@$00@WTL@@QEAA@XZ; WTL::CRgnT<1>::~CRgnT<1>(void)
0x180093e6f  nop
0x180093e70  lea     rcx, [rbp+57h+var_60]
0x180093e74  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180093e7a  mov     eax, ebx
0x180093e7c  add     rsp, 88h
0x180093e83  pop     r15
0x180093e85  pop     r14
0x180093e87  pop     rdi
0x180093e88  pop     rsi
0x180093e89  pop     rbx
0x180093e8a  pop     rbp
0x180093e8b  retn
```
