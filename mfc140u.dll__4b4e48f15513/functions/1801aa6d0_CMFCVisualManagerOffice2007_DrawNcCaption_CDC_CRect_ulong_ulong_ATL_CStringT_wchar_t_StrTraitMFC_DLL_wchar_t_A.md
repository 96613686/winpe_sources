# CMFCVisualManagerOffice2007::DrawNcCaption(CDC *,CRect,ulong,ulong,ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,HICON__ *,int,int,int,CObList const &)

- ea: `0x1801aa6d0`
- end: `0x1801aaca4`
- name: `?DrawNcCaption@CMFCVisualManagerOffice2007@@IEAAXPEAVCDC@@VCRect@@KKAEBV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@2PEAUHICON__@@HHHAEBVCObList@@@Z`
- size: `1492`
- prototype: `void __fastcall(CMFCVisualManagerOffice2007 *this, CDC *pDC, CRect rectCaption, unsigned int dwStyle, unsigned int dwStyleEx, const ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *strTitle, const ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *strDocument, HICON__ *hIcon, int bPrefix, int bActive, int bTextCenter, const CObList *lstSysButtons)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801aad70`

## callees

- `0x18001d090`
- `0x180059e30`
- `0x180070230`
- `0x1801aa030`
- `0x1801aa2b0`
- `0x1801aa6d0`
- `0x1802aee60`
- `0x1802aef40`
- `0x1802af110`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1801aa755`
- `USER32!GetSystemMetrics` at `0x1801aa98f`
- `USER32!GetSystemMetrics` at `0x1801aa99c`
- `USER32!GetSystemMetrics` at `0x1801aa755`
- `USER32!GetSystemMetrics` at `0x1801aa98f`
- `USER32!GetSystemMetrics` at `0x1801aa99c`
- `USER32!DrawIconEx` at `0x1801aaa09`
- `USER32!DrawIconEx` at `0x1801aaa09`
- `USER32!OffsetRect` at `0x1801aaad1`
- `USER32!OffsetRect` at `0x1801aaad1`
- `GDI32!BitBlt` at `0x1801aa82c`
- `GDI32!BitBlt` at `0x1801aac36`
- `GDI32!BitBlt` at `0x1801aa82c`
- `GDI32!BitBlt` at `0x1801aac36`
- `GDI32!CreateCompatibleBitmap` at `0x1801aa7d5`
- `GDI32!CreateCompatibleBitmap` at `0x1801aa7d5`
- `GDI32!SelectObject` at `0x1801aa7ef`
- `GDI32!SelectObject` at `0x1801aac50`
- `GDI32!SelectObject` at `0x1801aa7ef`
- `GDI32!SelectObject` at `0x1801aac50`
- `GDI32!CreateCompatibleDC` at `0x1801aa798`
- `GDI32!CreateCompatibleDC` at `0x1801aa798`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CMFCVisualManagerOffice2007::DrawNcCaption(
        CMFCVisualManagerOffice2007 *this,
        CDC *pDC,
        __m128i *rectCaption,
        unsigned int dwStyle,
        unsigned int dwStyleEx,
        ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *strTitle,
        ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *strDocument,
        HICON hIcon,
        int bPrefix,
        int bActive,
        int bTextCenter,
        const CObList *lstSysButtons)
{
  __m128i *v13; // r12
  void *m_hObject; // r14
  HDC__ *m_hDC; // rcx
  HDC CompatibleDC; // rax
  int v19; // edi
  int v20; // ebx
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v22; // rax
  unsigned int m_clrAppCaptionActiveStart; // r8d
  unsigned int m_clrAppCaptionActiveFinish; // r9d
  __int64 v25; // r11
  int v26; // r10d
  __int64 v27; // rax
  int v28; // edx
  __m128i v29; // xmm2
  CMFCControlRenderer *p_m_ctrlMainBorderCaption; // rcx
  bool v31; // zf
  void (__fastcall *Draw)(CMFCControlRenderer *, CDC *, CRect, unsigned int, unsigned __int8); // rax
  __m128i v33; // xmm0
  int cx; // ebx
  int v35; // edi
  int right; // r13d
  int v37; // esi
  int v38; // r11d
  int v39; // ecx
  int v40; // edi
  int v41; // r10d
  int v42; // r10d
  int v43; // r8d
  const CObList **m_pNodeHead; // rcx
  int v45; // edi
  CObList *v46; // rsi
  CMFCVisualManager::AFX_BUTTON_STATE v47; // r13d
  unsigned int v48; // edi
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *v49; // rsi
  CFont *v50; // rbx
  HGDIOBJ v51; // rax
  int cy; // [rsp+20h] [rbp-E0h]
  int SystemMetrics; // [rsp+60h] [rbp-A0h]
  int v54; // [rsp+60h] [rbp-A0h]
  CRect rect; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v56; // [rsp+80h] [rbp-80h]
  CDC memDC; // [rsp+88h] [rbp-78h] BYREF
  CSize szSysBorder; // [rsp+A8h] [rbp-58h] BYREF
  const CObList *v59; // [rsp+B0h] [rbp-50h]
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *v60; // [rsp+B8h] [rbp-48h]
  CBitmap memBmp; // [rsp+C0h] [rbp-40h] BYREF
  CRect *v62; // [rsp+D0h] [rbp-30h]
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *v63; // [rsp+D8h] [rbp-28h]
  CDC *v64; // [rsp+E0h] [rbp-20h]
  CGdiObject *v65; // [rsp+E8h] [rbp-18h]
  CRect rectText; // [rsp+F0h] [rbp-10h] BYREF
  HICON v67[2]; // [rsp+100h] [rbp+0h] BYREF
  char v68[16]; // [rsp+110h] [rbp+10h] BYREF
  unsigned int bIsRTL; // [rsp+190h] [rbp+90h]

  v56 = dwStyle;
  v13 = rectCaption;
  v62 = (CRect *)rectCaption;
  v64 = pDC;
  v63 = strTitle;
  v60 = strDocument;
  v67[0] = hIcon;
  v59 = lstSysButtons;
  bIsRTL = (dwStyleEx >> 22) & 1;
  SystemMetrics = GetSystemMetrics(4);
  CGlobalUtils::GetSystemBorders(&afxGlobalUtils, &szSysBorder, dwStyle);
  memDC.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&memDC.m_hDC, 0, 20);
  m_hObject = 0;
  m_hDC = 0;
  if ( pDC )
    m_hDC = pDC->m_hDC;
  CompatibleDC = CreateCompatibleDC(m_hDC);
  CDC::Attach(&memDC, CompatibleDC);
  memBmp.m_hObject = 0;
  memBmp.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  v19 = v13->m128i_i32[3] - v13->m128i_i32[1];
  v20 = v13->m128i_i32[2] - v13->m128i_i32[0];
  CompatibleBitmap = CreateCompatibleBitmap(pDC->m_hDC, v20, v19);
  CGdiObject::Attach(&memBmp, CompatibleBitmap);
  v22 = SelectObject(memDC.m_hDC, memBmp.m_hObject);
  v65 = CGdiObject::FromHandle(v22);
  BitBlt(memDC.m_hDC, 0, 0, v20, v19, pDC->m_hDC, 0, 0, 0xCC0020u);
  if ( this->m_nType >= 20 )
  {
    p_m_ctrlMainBorderCaption = &this->m_ctrlMainBorderCaption;
    v31 = bActive == 0;
    Draw = this->m_ctrlMainBorderCaption.Draw;
  }
  else
  {
    if ( bActive )
    {
      m_clrAppCaptionActiveStart = this->m_clrAppCaptionActiveStart;
      m_clrAppCaptionActiveFinish = this->m_clrAppCaptionActiveFinish;
    }
    else
    {
      m_clrAppCaptionActiveStart = this->m_clrAppCaptionInactiveStart;
      m_clrAppCaptionActiveFinish = this->m_clrAppCaptionInactiveFinish;
    }
    v25 = *(_QWORD *)&this->m_ctrlMainBorderCaption.m_Params.m_rectSides.left;
    v26 = v25 + *(_OWORD *)v13;
    LODWORD(v25) = _mm_cvtsi128_si32(_mm_srli_si128(*v13, 4)) + HIDWORD(v25);
    v27 = *(_QWORD *)&this->m_ctrlMainBorderCaption.m_Params.m_rectSides.right;
    v28 = v13->m128i_i64[1] - v27;
    v29 = _mm_srli_si128(*v13, 12);
    *(_QWORD *)&rectText.left = CDrawingManager::`vftable';
    *(_QWORD *)&rectText.right = &memDC;
    rect.left = v26;
    rect.top = v25;
    rect.right = v28;
    rect.bottom = _mm_cvtsi128_si32(v29) - HIDWORD(v27);
    CDrawingManager::Fill4ColorsGradient(
      (CDrawingManager *)&rectText,
      &rect,
      m_clrAppCaptionActiveStart,
      m_clrAppCaptionActiveFinish,
      m_clrAppCaptionActiveFinish,
      m_clrAppCaptionActiveStart,
      0,
      50);
    p_m_ctrlMainBorderCaption = &this->m_ctrlMainBorderCaption;
    v31 = bActive == 0;
    Draw = this->m_ctrlMainBorderCaption.DrawFrame;
  }
  LOBYTE(cy) = -1;
  rectText = (CRect)*v13;
  ((void (__fastcall *)(CMFCControlRenderer *, CDC *, CRect *, bool, int))Draw)(
    p_m_ctrlMainBorderCaption,
    &memDC,
    &rectText,
    v31,
    cy);
  v33 = *v13;
  rect.bottom = HIDWORD(*(unsigned __int128 *)v13);
  cx = szSysBorder.cx;
  rect.left = szSysBorder.cx + _mm_cvtsi128_si32(v33);
  v35 = ((dwStyle & 0x1000000) != 0 ? szSysBorder.cy : 0) + v33.m128i_i32[1];
  rect.top = v35;
  right = v33.m128i_i32[2] - szSysBorder.cx;
  rect.right = v33.m128i_i32[2] - szSysBorder.cx;
  if ( v67[0] )
  {
    v37 = GetSystemMetrics(50);
    v38 = GetSystemMetrics(49);
    v39 = rect.bottom - v35;
    v40 = rect.left + SystemMetrics;
    v41 = 0;
    if ( (SystemMetrics - v38) / 2 >= 0 )
      v41 = (SystemMetrics - v38) / 2;
    v42 = rect.left + v41;
    v43 = 0;
    if ( (v39 - v37) / 2 >= 0 )
      v43 = (v39 - v37) / 2;
    DrawIconEx(memDC.m_hDC, v42, rect.top + v43, v67[0], v38, v37, 0, 0, 3u);
    rect.left = v40;
  }
  m_pNodeHead = (const CObList **)v59->m_pNodeHead;
  v45 = right;
  if ( m_pNodeHead )
  {
    v54 = right;
    do
    {
      v46 = (CObList *)m_pNodeHead[2];
      v59 = *m_pNodeHead;
      v47 = ButtonsIsRegular;
      if ( LODWORD(v46->m_pNodeHead) )
      {
        v47 = HIDWORD(v46->m_pNodeHead) != 0;
      }
      else if ( HIDWORD(v46->m_pNodeHead) )
      {
        v47 = ButtonsIsHighlighted;
      }
      v48 = 0;
      switch ( LODWORD(v46->m_pNodeFree) )
      {
        case 0x13:
          v48 = 61536;
          break;
        case 0x1A:
          v48 = (v56 & 0x1000000) != 0 ? 61728 : 61488;
          break;
        case 0x1B:
          v48 = (v56 >> 21) & 0x100 | 0xF020;
          break;
      }
      ((void (__fastcall *)(CObList *, CRect *))v46->__vftable[1].GetRuntimeClass)(v46, &rectText);
      if ( (v56 & 0x1000000) != 0 )
        OffsetRect(&rectText, cx, szSysBorder.cy);
      CMFCVisualManagerOffice2007::DrawNcBtn(this, &memDC, &rectText, v48, v47, 0, bActive, 0);
      v45 = v54;
      if ( v54 >= *(_DWORD *)((__int64 (__fastcall *)(CObList *, HICON *))v46->__vftable[1].GetRuntimeClass)(v46, v67) )
      {
        v45 = *(_DWORD *)((__int64 (__fastcall *)(CObList *, char *))v46->__vftable[1].GetRuntimeClass)(v46, v68);
        v54 = v45;
      }
      m_pNodeHead = (const CObList **)v59;
    }
    while ( v59 );
    v13 = (__m128i *)v62;
    right = rect.right;
  }
  v49 = v63;
  if ( (*((_DWORD *)v63->m_pszData - 4) || *((_DWORD *)v60->m_pszData - 4)) && rect.left < right )
  {
    v50 = CDC::SelectObject(&memDC, &this->m_AppCaptionFont);
    rectText = rect;
    rectText.right = v45 - 1;
    CMFCVisualManagerOffice2007::DrawNcText(
      this,
      &memDC,
      &rectText,
      v49,
      v60,
      bPrefix,
      bActive,
      bIsRTL,
      bTextCenter,
      0,
      0,
      0xFFFFFFFF);
    CDC::SelectObject(&memDC, v50);
  }
  BitBlt(
    v64->m_hDC,
    v13->m128i_i32[0],
    v13->m128i_i32[1],
    v13->m128i_i32[2] - v13->m128i_i32[0],
    v13->m128i_i32[3] - v13->m128i_i32[1],
    memDC.m_hDC,
    0,
    0,
    0xCC0020u);
  if ( v65 )
    m_hObject = v65->m_hObject;
  v51 = SelectObject(memDC.m_hDC, m_hObject);
  CGdiObject::FromHandle(v51);
  memBmp.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CGdiObject::~CGdiObject(&memBmp);
  CDC::~CDC(&memDC);
}

```

## disassembly

```asm
0x1801aa6d0  mov     [rsp-8+arg_18], rbx
0x1801aa6d5  push    rbp
0x1801aa6d6  push    rsi
0x1801aa6d7  push    rdi
0x1801aa6d8  push    r12
0x1801aa6da  push    r13
0x1801aa6dc  push    r14
0x1801aa6de  push    r15
0x1801aa6e0  lea     rbp, [rsp-30h]
0x1801aa6e5  sub     rsp, 130h
0x1801aa6ec  mov     rax, cs:__security_cookie
0x1801aa6f3  xor     rax, rsp
0x1801aa6f6  mov     [rbp+60h+var_40], rax
0x1801aa6fa  mov     esi, dwStyle
0x1801aa6fd  mov     [rbp+60h+var_E0], dwStyle
0x1801aa701  mov     r12, rectCaption
0x1801aa704  mov     [rbp+60h+var_90], rectCaption
0x1801aa708  mov     r13, pDC
0x1801aa70b  mov     [rbp+60h+var_80], pDC
0x1801aa70f  mov     r15, this
0x1801aa712  mov     rax, [rbp+60h+arg_28]
0x1801aa719  mov     [rbp+60h+var_88], rax
0x1801aa71d  mov     rax, [rbp+60h+arg_30]
0x1801aa724  mov     [rbp+60h+var_A8], rax
0x1801aa728  mov     rax, [rbp+60h+arg_38]
0x1801aa72f  mov     [rbp+60h+var_60], rax
0x1801aa733  mov     rax, [rbp+60h+arg_58]
0x1801aa73a  mov     [rbp+60h+var_B0], rax
0x1801aa73e  mov     eax, [rbp+60h+bIsRTL]
0x1801aa744  shr     eax, 16h
0x1801aa747  and     eax, 1
0x1801aa74a  mov     [rbp+60h+bIsRTL], eax
0x1801aa750  mov     ecx, 4; nIndex
0x1801aa755  call    cs:__imp_GetSystemMetrics
0x1801aa75b  mov     [rsp+160h+var_100], eax
0x1801aa75f  mov     r8d, esi; dwStyle
0x1801aa762  lea     pDC, [rbp+60h+szSysBorder]; result
0x1801aa766  lea     this, ?afxGlobalUtils@@3VCGlobalUtils@@A; this
0x1801aa76d  call    ?GetSystemBorders@CGlobalUtils@@QEAA?AVCSize@@K@Z; CGlobalUtils::GetSystemBorders(ulong)
0x1801aa772  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1801aa779  mov     [rbp+60h+memDC.__vftable], rax
0x1801aa77d  xorps   xmm0, xmm0
0x1801aa780  movdqu  xmmword ptr [rbp+60h+memDC.m_hDC], xmm0
0x1801aa785  xor     r14d, r14d
0x1801aa788  mov     [rbp+60h+memDC.m_bPrinting], r14d
0x1801aa78c  test    r13, r13
0x1801aa78f  mov     ecx, r14d
0x1801aa792  jz      short loc_1801AA798
0x1801aa794  mov     this, [r13+8]; hdc
0x1801aa798  call    cs:__imp_CreateCompatibleDC
0x1801aa79e  mov     pDC, rax; hDC
0x1801aa7a1  lea     this, [rbp+60h+memDC]; this
0x1801aa7a5  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1801aa7aa  mov     [rbp+60h+memBmp.m_hObject], r14
0x1801aa7ae  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1801aa7b5  mov     [rbp+60h+memBmp.__vftable], rax
0x1801aa7b9  mov     edi, [r12+0Ch]
0x1801aa7be  sub     edi, [r12+4]
0x1801aa7c3  mov     ebx, [r12+8]
0x1801aa7c8  sub     ebx, [r12]
0x1801aa7cc  mov     r8d, edi; cy
0x1801aa7cf  mov     edx, ebx; cx
0x1801aa7d1  mov     this, [r13+8]; hdc
0x1801aa7d5  call    cs:__imp_CreateCompatibleBitmap
0x1801aa7db  mov     pDC, rax; hObject
0x1801aa7de  lea     this, [rbp+60h+memBmp]; this
0x1801aa7e2  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1801aa7e7  mov     pDC, [rbp+60h+memBmp.m_hObject]; h
0x1801aa7eb  mov     this, [rbp+60h+memDC.m_hDC]; hdc
0x1801aa7ef  call    cs:__imp_SelectObject
0x1801aa7f5  mov     this, rax; h
0x1801aa7f8  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1801aa7fd  mov     [rbp+60h+var_78], rax
0x1801aa801  mov     this, [r13+8]
0x1801aa805  mov     [rsp+160h+rop], 0CC0020h; rop
0x1801aa80d  mov     [rsp+160h+y1], r14d; y1
0x1801aa812  mov     [rsp+160h+x1], r14d; x1
0x1801aa817  mov     [rsp+160h+hdcSrc], this; hdcSrc
0x1801aa81c  mov     [rsp+160h+cy], edi; cy
0x1801aa820  mov     dwStyle, ebx; cx
0x1801aa823  xor     r8d, r8d; y
0x1801aa826  xor     edx, edx; x
0x1801aa828  mov     this, [rbp+60h+memDC.m_hDC]; hdc
0x1801aa82c  call    cs:__imp_BitBlt
0x1801aa832  cmp     dword ptr [r15+10A38h], 14h
0x1801aa83a  jge     loc_1801AA90A
0x1801aa840  mov     ebx, [rbp+60h+arg_48]
0x1801aa846  test    ebx, ebx
0x1801aa848  jz      short loc_1801AA85A
0x1801aa84a  mov     r8d, [r15+0C580h]
0x1801aa851  mov     dwStyle, [r15+0C584h]
0x1801aa858  jmp     short loc_1801AA868
0x1801aa85a  mov     r8d, [r15+0C588h]
0x1801aa861  mov     dwStyle, [r15+0C58Ch]
0x1801aa868  movups  xmm2, xmmword ptr [r12]
0x1801aa86d  movq    r10, xmm2
0x1801aa872  mov     r11, [r15+34C0h]
0x1801aa879  add     r10d, r11d
0x1801aa87c  shr     r11, 20h
0x1801aa880  movdqa  xmm0, xmm2
0x1801aa884  psrldq  xmm0, 4
0x1801aa889  movd    eax, xmm0
0x1801aa88d  add     r11d, eax
0x1801aa890  mov     pDC, [r12+8]
0x1801aa895  mov     rax, [r15+34C8h]
0x1801aa89c  sub     edx, eax
0x1801aa89e  shr     rax, 20h
0x1801aa8a2  psrldq  xmm2, 0Ch
0x1801aa8a7  movd    ecx, xmm2
0x1801aa8ab  sub     ecx, eax
0x1801aa8ad  lea     rax, ??_7CDrawingManager@@6B@; const CDrawingManager::`vftable'
0x1801aa8b4  mov     qword ptr [rbp+60h+rectText.left], rax
0x1801aa8b8  lea     rax, [rbp+60h+memDC]
0x1801aa8bc  mov     qword ptr [rbp+60h+rectText.right], rax
0x1801aa8c0  mov     [rsp+160h+rect.left], r10d
0x1801aa8c5  mov     [rsp+160h+rect.top], r11d
0x1801aa8ca  mov     [rsp+160h+rect.right], edx
0x1801aa8ce  mov     [rsp+160h+rect.bottom], ecx
0x1801aa8d2  mov     [rsp+160h+y1], 32h ; '2'
0x1801aa8da  mov     [rsp+160h+x1], r14d
0x1801aa8df  mov     dword ptr [rsp+160h+hdcSrc], r8d
0x1801aa8e4  mov     [rsp+160h+cy], dwStyle
0x1801aa8e9  lea     pDC, [rsp+160h+rect]
0x1801aa8ee  lea     this, [rbp+60h+rectText]
0x1801aa8f2  call    ?Fill4ColorsGradient@CDrawingManager@@QEAAXVCRect@@KKKKHH@Z; CDrawingManager::Fill4ColorsGradient(CRect,ulong,ulong,ulong,ulong,int,int)
0x1801aa8f7  nop
0x1801aa8f8  lea     this, [r15+32F0h]
0x1801aa8ff  mov     rax, [this]
0x1801aa902  test    ebx, ebx
0x1801aa904  mov     rax, [rax+38h]
0x1801aa908  jmp     short loc_1801AA91F
0x1801aa90a  lea     this, [r15+32F0h]
0x1801aa911  mov     rax, [this]
0x1801aa914  cmp     [rbp+60h+arg_48], r14d
0x1801aa91b  mov     rax, [rax+30h]
0x1801aa91f  movups  xmm0, xmmword ptr [r12]
0x1801aa924  mov     dwStyle, r14d
0x1801aa927  mov     byte ptr [rsp+160h+cy], 0FFh
0x1801aa92c  movdqu  xmmword ptr [rbp+60h+rectText.left], xmm0
0x1801aa931  setz    r9b
0x1801aa935  lea     rectCaption, [rbp+60h+rectText]
0x1801aa939  lea     pDC, [rbp+60h+memDC]
0x1801aa93d  call    cs:__guard_dispatch_icall_fptr
0x1801aa943  movups  xmm0, xmmword ptr [r12]
0x1801aa948  movaps  xmmword ptr [rsp+160h+rect.left], xmm0
0x1801aa94d  mov     eax, esi
0x1801aa94f  and     eax, 1000000h
0x1801aa954  neg     eax
0x1801aa956  sbb     ecx, ecx
0x1801aa958  and     ecx, [rbp+60h+szSysBorder.cy]
0x1801aa95b  movd    edx, xmm0
0x1801aa95f  mov     rbx, qword ptr [rbp+60h+szSysBorder.cx]
0x1801aa963  add     edx, ebx
0x1801aa965  mov     [rsp+160h+rect.left], edx
0x1801aa969  mov     edi, [rsp+160h+rect.top]
0x1801aa96d  add     edi, ecx
0x1801aa96f  mov     [rsp+160h+rect.top], edi
0x1801aa973  mov     r13d, [rsp+160h+rect.right]
0x1801aa978  sub     r13d, ebx
0x1801aa97b  mov     [rsp+160h+rect.right], r13d
0x1801aa980  cmp     [rbp+60h+var_60], r14
0x1801aa984  jz      loc_1801AAA13
0x1801aa98a  mov     ecx, 32h ; '2'; nIndex
0x1801aa98f  call    cs:__imp_GetSystemMetrics
0x1801aa995  mov     esi, eax
0x1801aa997  mov     ecx, 31h ; '1'; nIndex
0x1801aa99c  call    cs:__imp_GetSystemMetrics
0x1801aa9a2  mov     r11d, eax
0x1801aa9a5  mov     ecx, [rsp+160h+rect.bottom]
0x1801aa9a9  sub     ecx, edi
0x1801aa9ab  mov     r8d, [rsp+160h+rect.left]
0x1801aa9b0  mov     edi, [rsp+160h+var_100]
0x1801aa9b4  add     edi, r8d
0x1801aa9b7  mov     eax, edi
0x1801aa9b9  sub     eax, r8d
0x1801aa9bc  sub     eax, r11d
0x1801aa9bf  cdq
0x1801aa9c0  sub     eax, edx
0x1801aa9c2  sar     eax, 1
0x1801aa9c4  mov     r10d, r14d
0x1801aa9c7  cmovns  r10d, eax
0x1801aa9cb  add     r10d, r8d
0x1801aa9ce  sub     ecx, esi
0x1801aa9d0  mov     eax, ecx
0x1801aa9d2  cdq
0x1801aa9d3  sub     eax, edx
0x1801aa9d5  sar     eax, 1
0x1801aa9d7  mov     r8d, r14d
0x1801aa9da  cmovns  r8d, eax
0x1801aa9de  add     r8d, [rsp+160h+rect.top]; yTop
0x1801aa9e3  mov     [rsp+160h+rop], 3; diFlags
0x1801aa9eb  mov     qword ptr [rsp+160h+y1], r14; hbrFlickerFreeDraw
0x1801aa9f0  mov     [rsp+160h+x1], r14d; istepIfAniCur
0x1801aa9f5  mov     dword ptr [rsp+160h+hdcSrc], esi; cyWidth
0x1801aa9f9  mov     [rsp+160h+cy], r11d; cxWidth
0x1801aa9fe  mov     r9, [rbp+60h+var_60]; hIcon
0x1801aaa02  mov     edx, r10d; xLeft
0x1801aaa05  mov     this, [rbp+60h+memDC.m_hDC]; hdc
0x1801aaa09  call    cs:__imp_DrawIconEx
0x1801aaa0f  mov     [rsp+160h+rect.left], edi
0x1801aaa13  mov     this, [rbp+60h+var_B0]
0x1801aaa17  mov     this, [this+8]
0x1801aaa1b  mov     edi, r13d
0x1801aaa1e  test    this, this
0x1801aaa21  jz      loc_1801AAB4A
0x1801aaa27  mov     [rsp+160h+var_100], r13d
0x1801aaa2c  mov     r12d, [rbp+60h+arg_48]
0x1801aaa33  mov     rsi, [this+10h]
0x1801aaa37  mov     this, [this]
0x1801aaa3a  mov     [rbp+60h+var_B0], this
0x1801aaa3e  mov     r13d, r14d
0x1801aaa41  cmp     [rsi+8], r14d
0x1801aaa45  jz      short loc_1801AAA55
0x1801aaa47  cmp     [rsi+0Ch], r14d
0x1801aaa4b  jz      short loc_1801AAA62
0x1801aaa4d  mov     r13d, 1
0x1801aaa53  jmp     short loc_1801AAA62
0x1801aaa55  mov     eax, 2
0x1801aaa5a  cmp     [rsi+0Ch], r14d
0x1801aaa5e  cmovnz  r13d, eax
0x1801aaa62  mov     eax, [rsi+20h]
0x1801aaa65  mov     edi, r14d
0x1801aaa68  sub     eax, 13h
0x1801aaa6b  jz      short loc_1801AAAA5
0x1801aaa6d  sub     eax, 7
0x1801aaa70  jz      short loc_1801AAA8B
0x1801aaa72  cmp     eax, 1
0x1801aaa75  jnz     short loc_1801AAAAA
0x1801aaa77  mov     edi, [rbp+60h+var_E0]
0x1801aaa7a  shr     edi, 15h
0x1801aaa7d  and     edi, 100h
0x1801aaa83  or      edi, 0F020h
0x1801aaa89  jmp     short loc_1801AAAAA
0x1801aaa8b  mov     eax, [rbp+60h+var_E0]
0x1801aaa8e  and     eax, 1000000h
0x1801aaa93  neg     eax
0x1801aaa95  sbb     edi, edi
0x1801aaa97  and     edi, 0F0h
0x1801aaa9d  add     edi, 0F030h
0x1801aaaa3  jmp     short loc_1801AAAAA
0x1801aaaa5  mov     edi, 0F060h
0x1801aaaaa  mov     rax, [rsi]
0x1801aaaad  lea     pDC, [rbp+60h+rectText]
0x1801aaab1  mov     this, rsi
0x1801aaab4  mov     rax, [rax+28h]
0x1801aaab8  call    cs:__guard_dispatch_icall_fptr
0x1801aaabe  test    [rbp+60h+var_E0], 1000000h
0x1801aaac5  jz      short loc_1801AAAD7
0x1801aaac7  mov     r8d, [rbp+60h+szSysBorder.cy]; dy
0x1801aaacb  mov     edx, ebx; dx
0x1801aaacd  lea     this, [rbp+60h+rectText]; lprc
0x1801aaad1  call    cs:__imp_OffsetRect
0x1801aaad7  mov     [rsp+160h+y1], r14d; bMDI
0x1801aaadc  mov     [rsp+160h+x1], r12d; bActive
0x1801aaae1  mov     dword ptr [rsp+160h+hdcSrc], r14d; bSmall
0x1801aaae6  mov     [rsp+160h+cy], r13d; state
0x1801aaaeb  mov     dwStyle, edi; nButton
0x1801aaaee  lea     rectCaption, [rbp+60h+rectText]; rect
0x1801aaaf2  lea     pDC, [rbp+60h+memDC]; pDC
0x1801aaaf6  mov     this, r15; this
0x1801aaaf9  call    ?DrawNcBtn@CMFCVisualManagerOffice2007@@IEAAXPEAVCDC@@AEBVCRect@@IW4AFX_BUTTON_STATE@CMFCVisualManager@@HHH@Z; CMFCVisualManagerOffice2007::DrawNcBtn(CDC *,CRect const &,uint,CMFCVisualManager::AFX_BUTTON_STATE,int,int,int)
0x1801aaafe  mov     rax, [rsi]
0x1801aab01  lea     pDC, [rbp+60h+var_60]
0x1801aab05  mov     this, rsi
0x1801aab08  mov     rax, [rax+28h]
0x1801aab0c  call    cs:__guard_dispatch_icall_fptr
0x1801aab12  mov     edi, [rsp+160h+var_100]
0x1801aab16  cmp     edi, [rax]
0x1801aab18  jl      short loc_1801AAB34
0x1801aab1a  mov     rax, [rsi]
0x1801aab1d  lea     pDC, [rbp+60h+var_50]
0x1801aab21  mov     this, rsi
0x1801aab24  mov     rax, [rax+28h]
0x1801aab28  call    cs:__guard_dispatch_icall_fptr
0x1801aab2e  mov     edi, [rax]
0x1801aab30  mov     [rsp+160h+var_100], edi
0x1801aab34  mov     this, [rbp+60h+var_B0]
0x1801aab38  test    this, this
0x1801aab3b  jnz     loc_1801AAA33
0x1801aab41  mov     r12, [rbp+60h+var_90]
0x1801aab45  mov     r13d, [rsp+160h+rect.right]
0x1801aab4a  mov     rsi, [rbp+60h+var_88]
0x1801aab4e  mov     rax, [rsi]
0x1801aab51  cmp     [rax-10h], r14d
0x1801aab55  jnz     short loc_1801AAB68
0x1801aab57  mov     rax, [rbp+60h+var_A8]
0x1801aab5b  mov     rax, [rax]
0x1801aab5e  cmp     [rax-10h], r14d
0x1801aab62  jz      loc_1801AABF5
0x1801aab68  cmp     [rsp+160h+rect.left], r13d
0x1801aab6d  jge     loc_1801AABF5
0x1801aab73  lea     pDC, [r15+0C550h]; pFont
0x1801aab7a  lea     this, [rbp+60h+memDC]; this
0x1801aab7e  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x1801aab83  mov     rbx, rax
0x1801aab86  movaps  xmm0, xmmword ptr [rsp+160h+rect.left]
0x1801aab8b  movdqa  xmmword ptr [rbp+60h+rectText.left], xmm0
0x1801aab90  lea     edx, [rdi-1]
0x1801aab93  mov     [rbp+60h+rectText.right], edx
0x1801aab96  or      [rsp+160h+var_108], 0FFFFFFFFh
  ... truncated ...
```
