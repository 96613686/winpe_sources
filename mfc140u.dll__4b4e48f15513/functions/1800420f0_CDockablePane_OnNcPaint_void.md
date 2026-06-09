# CDockablePane::OnNcPaint(void)

- ea: `0x1800420f0`
- end: `0x180042558`
- name: `?OnNcPaint@CDockablePane@@IEAAXXZ`
- size: `1128`
- prototype: `void __fastcall(CDockablePane *this)`
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180009844`
- `0x18001d090`
- `0x1800420f0`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aef40`
- `0x1802af8a0`
- `0x1802af990`
- `0x1802afa90`
- `0x1802afdb0`
- `0x1802afe10`
- `0x1802b0720`
- `0x1802b07d0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800424ea`
- `KERNEL32!LeaveCriticalSection` at `0x1800424ea`
- `KERNEL32!EnterCriticalSection` at `0x180042137`
- `KERNEL32!EnterCriticalSection` at `0x180042137`
- `USER32!GetUpdateRect` at `0x18004215c`
- `USER32!GetUpdateRect` at `0x18004215c`
- `USER32!GetClientRect` at `0x180042177`
- `USER32!GetClientRect` at `0x180042177`
- `USER32!GetWindowRect` at `0x180042191`
- `USER32!GetWindowRect` at `0x180042335`
- `USER32!GetWindowRect` at `0x180042191`
- `USER32!GetWindowRect` at `0x180042335`
- `USER32!IsRectEmpty` at `0x18004228b`
- `USER32!IsRectEmpty` at `0x18004228b`
- `USER32!InflateRect` at `0x180042367`
- `USER32!InflateRect` at `0x180042367`
- `USER32!OffsetRect` at `0x1800421a7`
- `USER32!OffsetRect` at `0x1800421bd`
- `USER32!OffsetRect` at `0x180042357`
- `USER32!OffsetRect` at `0x1800421a7`
- `USER32!OffsetRect` at `0x1800421bd`
- `USER32!OffsetRect` at `0x180042357`
- `GDI32!CreateRectRgnIndirect` at `0x180042298`
- `GDI32!CreateRectRgnIndirect` at `0x180042298`
- `GDI32!BitBlt` at `0x1800424ab`
- `GDI32!BitBlt` at `0x1800424ab`
- `GDI32!CreateCompatibleBitmap` at `0x180042225`
- `GDI32!CreateCompatibleBitmap` at `0x180042225`
- `GDI32!SelectObject` at `0x18004224d`
- `GDI32!SelectObject` at `0x1800424c1`
- `GDI32!SelectObject` at `0x18004224d`
- `GDI32!SelectObject` at `0x1800424c1`
- `GDI32!CreateCompatibleDC` at `0x1800421fc`
- `GDI32!CreateCompatibleDC` at `0x1800421fc`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=4
void __fastcall CDockablePane::OnNcPaint(CDockablePane *this)
{
  int m_bPinState; // r15d
  HDC__ **p_m_hDC; // r12
  CGdiObject *v4; // r13
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v7; // rax
  HRGN RectRgnIndirect; // rax
  CMFCVisualManager *Instance; // r10
  void (__fastcall *OnFillBarBackground)(CMFCVisualManager *, CDC *, CBasePane *, CRect, CRect, int); // rax
  int v11; // ebx
  CDockablePane_vtbl *v12; // rax
  __int64 m_nSize; // rcx
  __int64 v14; // rsi
  CObject *v15; // r14
  void (__fastcall *v16)(CObject *); // rbx
  unsigned int v17; // eax
  void *m_hObject; // rdx
  HGDIOBJ v19; // rax
  CRgn rgn; // [rsp+58h] [rbp-B0h] BYREF
  CBitmap bmp; // [rsp+68h] [rbp-A0h] BYREF
  CDC dcMem; // [rsp+78h] [rbp-90h] BYREF
  int v23; // [rsp+98h] [rbp-70h]
  __m256i v24; // [rsp+A8h] [rbp-60h] OVERLAPPED BYREF
  _BYTE rcBar_8[64]; // [rsp+E8h] [rbp-20h] OVERLAPPED BYREF

  m_bPinState = 0;
  if ( CBasePane::m_bMultiThreaded )
    EnterCriticalSection(&CBasePane::m_CriticalSection.m_sect);
  CWindowDC::CWindowDC((CWindowDC *)&v24.m256i_u64[2], &this->CPane);
  *(_OWORD *)&rcBar_8[48] = 0;
  GetUpdateRect(this->m_hWnd, (LPRECT)&rcBar_8[48], 0);
  *(_OWORD *)&rcBar_8[32] = 0;
  *(_OWORD *)rcBar_8 = 0;
  GetClientRect(this->m_hWnd, (LPRECT)&rcBar_8[32]);
  CWnd::ClientToScreen(&this->CPane, (tagRECT *)&rcBar_8[32]);
  GetWindowRect(this->m_hWnd, (LPRECT)rcBar_8);
  OffsetRect((LPRECT)&rcBar_8[32], -*(_DWORD *)rcBar_8, -*(_DWORD *)&rcBar_8[4]);
  OffsetRect((LPRECT)rcBar_8, -*(_DWORD *)rcBar_8, -*(_DWORD *)&rcBar_8[4]);
  p_m_hDC = (HDC__ **)&v24.m256i_i64[2];
  HIDWORD(rgn.__vftable) = 0;
  dcMem.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&dcMem.m_hAttribDC = 0;
  v23 = 0;
  dcMem.__vftable = 0;
  bmp.m_hObject = (void *)CBitmap::`vftable';
  v4 = 0;
  CompatibleDC = CreateCompatibleDC((HDC)v24.m256i_i64[3]);
  if ( CDC::Attach((CDC *)&dcMem.m_hDC, CompatibleDC) )
  {
    CompatibleBitmap = CreateCompatibleBitmap(
                         (HDC)v24.m256i_i64[3],
                         *(_DWORD *)&rcBar_8[8] - *(_DWORD *)rcBar_8,
                         *(_DWORD *)&rcBar_8[12] - *(_DWORD *)&rcBar_8[4]);
    if ( CGdiObject::Attach((CGdiObject *)&bmp.m_hObject, CompatibleBitmap) )
    {
      HIDWORD(rgn.__vftable) = 1;
      v7 = SelectObject(dcMem.m_hAttribDC, dcMem.__vftable);
      v4 = CGdiObject::FromHandle(v7);
      p_m_hDC = &dcMem.m_hDC;
    }
  }
  CDC::ExcludeClipRect((CDC *)&v24.m256i_u64[2], (const tagRECT *)&rcBar_8[32]);
  bmp.__vftable = 0;
  rgn.m_hObject = (void *)CRgn::`vftable';
  if ( !IsRectEmpty(&this->m_rectRedraw) )
  {
    RectRgnIndirect = CreateRectRgnIndirect(&this->m_rectRedraw);
    CGdiObject::Attach((CGdiObject *)&rgn.m_hObject, RectRgnIndirect);
    CDC::SelectClipRgn((CDC *)&v24.m256i_u64[2], (CRgn *)&rgn.m_hObject);
  }
  CDC::IntersectClipRect((CDC *)&v24.m256i_u64[2], (const tagRECT *)rcBar_8);
  Instance = CMFCVisualManager::GetInstance();
  OnFillBarBackground = Instance->OnFillBarBackground;
  *(__m128i *)&rcBar_8[16] = _mm_load_si128((const __m128i *)rcBar_8);
  *(_OWORD *)v24.m256i_i8 = *(_OWORD *)&rcBar_8[16];
  ((void (__fastcall *)(CMFCVisualManager *, HDC__ **, CDockablePane *, __m256i *, _BYTE *, int))OnFillBarBackground)(
    Instance,
    p_m_hDC,
    this,
    &v24,
    &rcBar_8[16],
    1);
  v11 = this->GetCaptionHeight((CBasePane *)this);
  if ( v11 > 0 )
  {
    *(_OWORD *)&rcBar_8[16] = 0;
    GetWindowRect(this->m_hWnd, (LPRECT)&rcBar_8[16]);
    CWnd::ScreenToClient(&this->CPane, (tagRECT *)&rcBar_8[16]);
    OffsetRect((LPRECT)&rcBar_8[16], -*(_DWORD *)&rcBar_8[16], -*(_DWORD *)&rcBar_8[20]);
    InflateRect((LPRECT)&rcBar_8[16], 0, -1);
    *(_DWORD *)&rcBar_8[16] = *(_DWORD *)&rcBar_8[32];
    *(_DWORD *)&rcBar_8[28] = v11 + --*(_DWORD *)&rcBar_8[20] - 2;
    v12 = this->__vftable;
    *(_OWORD *)v24.m256i_i8 = *(_OWORD *)&rcBar_8[16];
    ((void (__fastcall *)(CDockablePane *, HDC__ **, __m256i *))v12->DrawCaption)(this, p_m_hDC, &v24);
    LODWORD(rgn.__vftable) = 0;
    m_nSize = this->m_arrButtons.m_nSize;
    if ( m_nSize > 0 )
    {
      v14 = 0;
      do
      {
        if ( v14 < 0 || v14 >= m_nSize )
          AfxThrowInvalidArgException();
        v15 = this->m_arrButtons.m_pData[v14];
        if ( LODWORD(v15[4].__vftable) == 8 )
        {
          m_bPinState = 1;
        }
        else if ( LODWORD(v15[4].__vftable) == 9 )
        {
          m_bPinState = this->m_bPinState;
        }
        v16 = v15->__vftable[1].~CObject;
        v17 = this->IsHorizontal((CBasePane *)this);
        ((void (__fastcall *)(CObject *, HDC__ **, _QWORD, _QWORD, int, _DWORD))v16)(
          v15,
          p_m_hDC,
          (unsigned int)this->m_bActive,
          v17,
          m_bPinState,
          0);
        HIDWORD(v15[4].__vftable) = -1;
        ++LODWORD(rgn.__vftable);
        ++v14;
        m_nSize = this->m_arrButtons.m_nSize;
        m_bPinState = 0;
      }
      while ( SLODWORD(rgn.__vftable) < m_nSize );
    }
  }
  if ( HIDWORD(rgn.__vftable) )
  {
    BitBlt(
      (HDC)v24.m256i_i64[3],
      *(int *)rcBar_8,
      *(int *)&rcBar_8[4],
      *(_DWORD *)&rcBar_8[8] - *(_DWORD *)rcBar_8,
      *(_DWORD *)&rcBar_8[12] - *(_DWORD *)&rcBar_8[4],
      dcMem.m_hAttribDC,
      *(int *)rcBar_8,
      *(int *)&rcBar_8[4],
      0xCC0020u);
    m_hObject = 0;
    if ( v4 )
      m_hObject = v4->m_hObject;
    v19 = SelectObject(dcMem.m_hAttribDC, m_hObject);
    CGdiObject::FromHandle(v19);
  }
  CDC::SelectClipRgn((CDC *)&v24.m256i_u64[2], 0);
  if ( CBasePane::m_bMultiThreaded )
    LeaveCriticalSection(&CBasePane::m_CriticalSection.m_sect);
  rgn.m_hObject = (void *)CRgn::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&rgn.m_hObject);
  bmp.m_hObject = (void *)CBitmap::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&bmp.m_hObject);
  CDC::~CDC((CDC *)&dcMem.m_hDC);
  CWindowDC::~CWindowDC((CWindowDC *)&v24.m256i_u64[2]);
}

```

## disassembly

```asm
0x1800420f0  mov     rax, rsp
0x1800420f3  mov     [rax+10h], rbx
0x1800420f7  mov     [rax+18h], rsi
0x1800420fb  mov     [rax+20h], rdi
0x1800420ff  push    rbp
0x180042100  push    r12
0x180042102  push    r13
0x180042104  push    r14
0x180042106  push    r15
0x180042108  lea     rbp, [rax-58h]
0x18004210c  sub     rsp, 130h
0x180042113  mov     rax, cs:__security_cookie
0x18004211a  xor     rax, rsp
0x18004211d  mov     [rbp+50h+var_30], rax
0x180042121  mov     rdi, this
0x180042124  xor     r15d, r15d
0x180042127  cmp     cs:?m_bMultiThreaded@CBasePane@@2HA, r15d; int CBasePane::m_bMultiThreaded
0x18004212e  jz      short loc_18004213D
0x180042130  lea     this, ?m_CriticalSection@CBasePane@@1VCCriticalSection@@A.m_sect; lpCriticalSection
0x180042137  call    cs:__imp_EnterCriticalSection
0x18004213d  mov     rdx, rdi; pWnd
0x180042140  lea     this, [rbp+50h+dcPaint.m_hDC]; this
0x180042144  call    ??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x180042149  nop
0x18004214a  xorps   xmm0, xmm0
0x18004214d  movups  xmmword ptr [rbp+50h+rectUpd.right], xmm0
0x180042151  xor     r8d, r8d; bErase
0x180042154  lea     rdx, [rbp+50h+rectUpd.right]; lpRect
0x180042158  mov     this, [rdi+40h]; hWnd
0x18004215c  call    cs:__imp_GetUpdateRect
0x180042162  xorps   xmm0, xmm0
0x180042165  movdqu  xmmword ptr [rbp+50h+rcClient.right], xmm0
0x18004216a  movdqa  xmmword ptr [rbp+50h+rcBar.right], xmm0
0x18004216f  lea     rdx, [rbp+50h+rcClient.right]; lpRect
0x180042173  mov     this, [rdi+40h]; hWnd
0x180042177  call    cs:__imp_GetClientRect
0x18004217d  lea     rdx, [rbp+50h+rcClient.right]; lpRect
0x180042181  mov     this, rdi; this
0x180042184  call    ?ClientToScreen@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ClientToScreen(tagRECT *)
0x180042189  lea     rdx, [rbp+50h+rcBar.right]; lpRect
0x18004218d  mov     this, [rdi+40h]; hWnd
0x180042191  call    cs:__imp_GetWindowRect
0x180042197  mov     r8d, [rbp+50h+rcBar.bottom]
0x18004219b  neg     r8d; dy
0x18004219e  mov     edx, [rbp+50h+rcBar.right]
0x1800421a1  neg     edx; dx
0x1800421a3  lea     this, [rbp+50h+rcClient.right]; lprc
0x1800421a7  call    cs:__imp_OffsetRect
0x1800421ad  mov     r8d, [rbp+50h+rcBar.bottom]
0x1800421b1  neg     r8d; dy
0x1800421b4  mov     edx, [rbp+50h+rcBar.right]
0x1800421b7  neg     edx; dx
0x1800421b9  lea     this, [rbp+50h+rcBar.right]; lprc
0x1800421bd  call    cs:__imp_OffsetRect
0x1800421c3  lea     r12, [rbp+50h+dcPaint.m_hDC]
0x1800421c7  mov     dword ptr [rsp+150h+rgn.__vftable+4], r15d
0x1800421cc  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1800421d3  mov     [rsp+150h+dcMem.m_hDC], rax
0x1800421d8  xorps   xmm0, xmm0
0x1800421db  movdqu  xmmword ptr [rbp+50h+dcMem.m_hAttribDC], xmm0
0x1800421e0  mov     [rbp+50h+var_C0], r15d
0x1800421e4  mov     [rsp+150h+dcMem.__vftable], r15
0x1800421e9  lea     r14, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1800421f0  mov     [rsp+150h+bmp.m_hObject], r14
0x1800421f5  mov     r13, r15
0x1800421f8  mov     this, [rbp+50h+dcPaint.m_hAttribDC]; hdc
0x1800421fc  call    cs:__imp_CreateCompatibleDC
0x180042202  mov     rdx, rax; hDC
0x180042205  lea     this, [rsp+150h+dcMem.m_hDC]; this
0x18004220a  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18004220f  test    eax, eax
0x180042211  jz      short loc_180042263
0x180042213  mov     r8d, [rbp+50h+rectCaption.top]
0x180042217  sub     r8d, [rbp+50h+rcBar.bottom]; cy
0x18004221b  mov     edx, [rbp+50h+rectCaption.left]
0x18004221e  sub     edx, [rbp+50h+rcBar.right]; cx
0x180042221  mov     this, [rbp+50h+dcPaint.m_hAttribDC]; hdc
0x180042225  call    cs:__imp_CreateCompatibleBitmap
0x18004222b  mov     rdx, rax; hObject
0x18004222e  lea     this, [rsp+150h+bmp.m_hObject]; this
0x180042233  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x180042238  test    eax, eax
0x18004223a  jz      short loc_180042263
0x18004223c  mov     dword ptr [rsp+150h+rgn.__vftable+4], 1
0x180042244  mov     rdx, [rsp+150h+dcMem.__vftable]; h
0x180042249  mov     this, [rbp+50h+dcMem.m_hAttribDC]; hdc
0x18004224d  call    cs:__imp_SelectObject
0x180042253  mov     this, rax; h
0x180042256  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18004225b  mov     r13, rax
0x18004225e  lea     r12, [rsp+150h+dcMem.m_hDC]
0x180042263  lea     rdx, [rbp+50h+rcClient.right]; lpRect
0x180042267  lea     this, [rbp+50h+dcPaint.m_hDC]; this
0x18004226b  call    ?ExcludeClipRect@CDC@@QEAAHPEBUtagRECT@@@Z; CDC::ExcludeClipRect(tagRECT const *)
0x180042270  mov     [rsp+150h+bmp.__vftable], r15
0x180042275  lea     rsi, ??_7CRgn@@6B@; const CRgn::`vftable'
0x18004227c  mov     [rsp+150h+rgn.m_hObject], rsi
0x180042281  lea     rbx, [rdi+428h]
0x180042288  mov     this, rbx; lprc
0x18004228b  call    cs:__imp_IsRectEmpty
0x180042291  test    eax, eax
0x180042293  jnz     short loc_1800422B9
0x180042295  mov     this, rbx; lprect
0x180042298  call    cs:__imp_CreateRectRgnIndirect
0x18004229e  mov     rdx, rax; hObject
0x1800422a1  lea     this, [rsp+150h+rgn.m_hObject]; this
0x1800422a6  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1800422ab  lea     rdx, [rsp+150h+rgn.m_hObject]; pRgn
0x1800422b0  lea     this, [rbp+50h+dcPaint.m_hDC]; this
0x1800422b4  call    ?SelectClipRgn@CDC@@QEAAHPEAVCRgn@@@Z; CDC::SelectClipRgn(CRgn *)
0x1800422b9  lea     rdx, [rbp+50h+rcBar.right]; lpRect
0x1800422bd  lea     this, [rbp+50h+dcPaint.m_hDC]; this
0x1800422c1  call    ?IntersectClipRect@CDC@@QEAAHPEBUtagRECT@@@Z; CDC::IntersectClipRect(tagRECT const *)
0x1800422c6  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x1800422cb  mov     r10, rax
0x1800422ce  mov     this, [rax]
0x1800422d1  mov     rax, [this+78h]
0x1800422d5  movdqa  xmm0, xmmword ptr [rbp+50h+rcBar.right]
0x1800422da  movdqa  xmmword ptr [rbp+50h+rectCaption.right], xmm0
0x1800422df  movdqa  xmmword ptr [rbp+50h+var_B0], xmm0
0x1800422e4  mov     dword ptr [rsp+150h+hdcSrc], 1
0x1800422ec  lea     this, [rbp+50h+rectCaption.right]
0x1800422f0  mov     qword ptr [rsp+150h+cy], this
0x1800422f5  lea     r9, [rbp+50h+var_B0]
0x1800422f9  mov     r8, rdi
0x1800422fc  mov     rdx, r12
0x1800422ff  mov     this, r10
0x180042302  call    cs:__guard_dispatch_icall_fptr
0x180042308  mov     rax, [rdi]
0x18004230b  mov     this, rdi
0x18004230e  mov     rax, [rax+358h]
0x180042315  call    cs:__guard_dispatch_icall_fptr
0x18004231b  mov     ebx, eax
0x18004231d  test    eax, eax
0x18004231f  jle     loc_18004246E
0x180042325  xorps   xmm0, xmm0
0x180042328  movdqa  xmmword ptr [rbp+50h+rectCaption.right], xmm0
0x18004232d  lea     rdx, [rbp+50h+rectCaption.right]; lpRect
0x180042331  mov     this, [rdi+40h]; hWnd
0x180042335  call    cs:__imp_GetWindowRect
0x18004233b  lea     rdx, [rbp+50h+rectCaption.right]; lpRect
0x18004233f  mov     this, rdi; this
0x180042342  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x180042347  mov     r8d, [rbp+50h+rectCaption.bottom]
0x18004234b  neg     r8d; dy
0x18004234e  mov     edx, [rbp+50h+rectCaption.right]
0x180042351  neg     edx; dx
0x180042353  lea     this, [rbp+50h+rectCaption.right]; lprc
0x180042357  call    cs:__imp_OffsetRect
0x18004235d  or      r8d, 0FFFFFFFFh; dy
0x180042361  xor     edx, edx; dx
0x180042363  lea     this, [rbp+50h+rectCaption.right]; lprc
0x180042367  call    cs:__imp_InflateRect
0x18004236d  mov     eax, [rbp+50h+rcClient.right]
0x180042370  mov     [rbp+50h+rectCaption.right], eax
0x180042373  mov     eax, [rbp+50h+rectCaption.bottom]
0x180042376  dec     eax
0x180042378  mov     [rbp+50h+rectCaption.bottom], eax
0x18004237b  add     eax, 0FFFFFFFEh
0x18004237e  add     eax, ebx
0x180042380  mov     [rbp+50h+rcClient.top], eax
0x180042383  mov     rax, [rdi]
0x180042386  movaps  xmm0, xmmword ptr [rbp+50h+rectCaption.right]
0x18004238a  movdqa  xmmword ptr [rbp+50h+var_B0], xmm0
0x18004238f  lea     r8, [rbp+50h+var_B0]
0x180042393  mov     rdx, r12
0x180042396  mov     this, rdi
0x180042399  mov     rax, [rax+710h]
0x1800423a0  call    cs:__guard_dispatch_icall_fptr
0x1800423a6  mov     dword ptr [rsp+150h+rgn.__vftable], r15d
0x1800423ab  mov     this, [rdi+498h]
0x1800423b2  test    this, this
0x1800423b5  jle     loc_18004246E
0x1800423bb  mov     rsi, r15
0x1800423be  test    rsi, rsi
0x1800423c1  js      loc_180042552
0x1800423c7  cmp     rsi, this
0x1800423ca  jge     loc_180042552
0x1800423d0  mov     rax, [rdi+490h]
0x1800423d7  mov     r14, [rax+rsi*8]
0x1800423db  mov     ecx, [r14+20h]
0x1800423df  sub     ecx, 8
0x1800423e2  jz      short loc_1800423F2
0x1800423e4  cmp     ecx, 1
0x1800423e7  jnz     short loc_1800423F8
0x1800423e9  mov     r15d, [rdi+438h]
0x1800423f0  jmp     short loc_1800423F8
0x1800423f2  mov     r15d, 1
0x1800423f8  mov     rax, [r14]
0x1800423fb  mov     rbx, [rax+30h]
0x1800423ff  mov     rax, [rdi]
0x180042402  mov     this, rdi
0x180042405  mov     rax, [rax+2D8h]
0x18004240c  call    cs:__guard_dispatch_icall_fptr
0x180042412  and     dword ptr [rsp+150h+hdcSrc], 0
0x180042417  mov     [rsp+150h+cy], r15d
0x18004241c  mov     r9d, eax
0x18004241f  mov     r8d, [rdi+41Ch]
0x180042426  mov     rdx, r12
0x180042429  mov     this, r14
0x18004242c  mov     rax, rbx
0x18004242f  call    cs:__guard_dispatch_icall_fptr
0x180042435  or      dword ptr [r14+24h], 0FFFFFFFFh
0x18004243a  mov     edx, dword ptr [rsp+150h+rgn.__vftable]
0x18004243e  inc     edx
0x180042440  mov     dword ptr [rsp+150h+rgn.__vftable], edx
0x180042444  inc     rsi
0x180042447  mov     this, [rdi+498h]
0x18004244e  movsxd  rax, edx
0x180042451  cmp     rax, this
0x180042454  mov     r15d, 0
0x18004245a  jl      loc_1800423BE
0x180042460  lea     rsi, ??_7CRgn@@6B@; const CRgn::`vftable'
0x180042467  lea     r14, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18004246e  cmp     dword ptr [rsp+150h+rgn.__vftable+4], r15d
0x180042473  jz      short loc_1800424CF
0x180042475  mov     ecx, [rbp+50h+rectCaption.top]
0x180042478  mov     r8, qword ptr [rbp+50h+rcBar.bottom]; y
0x18004247c  sub     ecx, r8d
0x18004247f  mov     r9d, [rbp+50h+rectCaption.left]
0x180042483  mov     edx, [rbp+50h+rcBar.right]; x
0x180042486  sub     r9d, edx; cx
0x180042489  mov     [rsp+150h+rop], 0CC0020h; rop
0x180042491  mov     [rsp+150h+y1], r8d; y1
0x180042496  mov     [rsp+150h+x1], edx; x1
0x18004249a  mov     rax, [rbp+50h+dcMem.m_hAttribDC]
0x18004249e  mov     [rsp+150h+hdcSrc], rax; hdcSrc
0x1800424a3  mov     [rsp+150h+cy], ecx; cy
0x1800424a7  mov     this, [rbp+50h+dcPaint.m_hAttribDC]; hdc
0x1800424ab  call    cs:__imp_BitBlt
0x1800424b1  test    r13, r13
0x1800424b4  mov     rdx, r15
0x1800424b7  jz      short loc_1800424BD
0x1800424b9  mov     rdx, [r13+8]; h
0x1800424bd  mov     this, [rbp+50h+dcMem.m_hAttribDC]; hdc
0x1800424c1  call    cs:__imp_SelectObject
0x1800424c7  mov     this, rax; h
0x1800424ca  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1800424cf  xor     edx, edx; pRgn
0x1800424d1  lea     this, [rbp+50h+dcPaint.m_hDC]; this
0x1800424d5  call    ?SelectClipRgn@CDC@@QEAAHPEAVCRgn@@@Z; CDC::SelectClipRgn(CRgn *)
0x1800424da  cmp     cs:?m_bMultiThreaded@CBasePane@@2HA, r15d; int CBasePane::m_bMultiThreaded
0x1800424e1  jz      short loc_1800424F1
0x1800424e3  lea     this, ?m_CriticalSection@CBasePane@@1VCCriticalSection@@A.m_sect; lpCriticalSection
0x1800424ea  call    cs:__imp_LeaveCriticalSection
0x1800424f0  nop
0x1800424f1  mov     [rsp+150h+rgn.m_hObject], rsi
0x1800424f6  lea     this, [rsp+150h+rgn.m_hObject]; this
0x1800424fb  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180042500  nop
0x180042501  mov     [rsp+150h+bmp.m_hObject], r14
0x180042506  lea     this, [rsp+150h+bmp.m_hObject]; this
0x18004250b  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180042510  nop
0x180042511  lea     this, [rsp+150h+dcMem.m_hDC]; this
0x180042516  call    ??1CDC@@UEAA@XZ; CDC::~CDC(void)
0x18004251b  nop
0x18004251c  lea     this, [rbp+50h+dcPaint.m_hDC]; this
0x180042520  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x180042525  mov     this, [rbp+50h+var_30]
0x180042529  xor     this, rsp; StackCookie
0x18004252c  call    __security_check_cookie
0x180042531  lea     r11, [rsp+150h+var_20]
0x180042539  mov     rbx, [r11+38h]
0x18004253d  mov     rsi, [r11+40h]
0x180042541  mov     rdi, [r11+48h]
0x180042545  mov     rsp, r11
0x180042548  pop     r15
0x18004254a  pop     r14
0x18004254c  pop     r13
0x18004254e  pop     r12
0x180042550  pop     rbp
0x180042551  retn
0x180042552  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
