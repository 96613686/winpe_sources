# CMFCPropertyGridCtrl::OnDrawProperty(CDC *,CMFCPropertyGridProperty *)

- ea: `0x1800cab40`
- end: `0x1800cb142`
- name: `?OnDrawProperty@CMFCPropertyGridCtrl@@UEBAHPEAVCDC@@PEAVCMFCPropertyGridProperty@@@Z`
- size: `1538`
- prototype: `int __fastcall(CMFCPropertyGridCtrl *this, CDC *pDC, CMFCPropertyGridProperty *pProp)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18001d090`
- `0x18006cab0`
- `0x1800cab40`
- `0x1802af8a0`
- `0x1802afbb0`
- `0x1802afc20`
- `0x1802b09d0`
- `0x1802b0b50`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!FillRect` at `0x1800cac4f`
- `USER32!FillRect` at `0x1800cad88`
- `USER32!FillRect` at `0x1800caeb2`
- `USER32!FillRect` at `0x1800cac4f`
- `USER32!FillRect` at `0x1800cad88`
- `USER32!FillRect` at `0x1800caeb2`
- `USER32!IsRectEmpty` at `0x1800cab7f`
- `USER32!IsRectEmpty` at `0x1800cb04c`
- `USER32!IsRectEmpty` at `0x1800cab7f`
- `USER32!IsRectEmpty` at `0x1800cb04c`
- `GDI32!CreateRectRgnIndirect` at `0x1800cadf0`
- `GDI32!CreateRectRgnIndirect` at `0x1800caf0d`
- `GDI32!CreateRectRgnIndirect` at `0x1800cb00e`
- `GDI32!CreateRectRgnIndirect` at `0x1800cadf0`
- `GDI32!CreateRectRgnIndirect` at `0x1800caf0d`
- `GDI32!CreateRectRgnIndirect` at `0x1800cb00e`
- `GDI32!SelectObject` at `0x1800caf5c`
- `GDI32!SelectObject` at `0x1800caf95`
- `GDI32!SelectObject` at `0x1800caf5c`
- `GDI32!SelectObject` at `0x1800caf95`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMFCPropertyGridCtrl::OnDrawProperty(
        CMFCPropertyGridCtrl *this,
        CDC *pDC,
        CMFCPropertyGridProperty *pProp)
{
  CRect *p_m_Rect; // r12
  int bottom; // r8d
  int left; // r10d
  int v9; // r13d
  int v10; // r9d
  int v11; // ecx
  int v12; // edx
  unsigned int m_clrGroupBackground; // edx
  unsigned int (__fastcall *SetTextColor)(CDC *, unsigned int); // r14
  __m128i v15; // xmm6
  int m_hObject; // r15d
  int v17; // eax
  HBRUSH v18; // r8
  int v19; // r14d
  __int128 v20; // xmm6
  int v21; // eax
  HRGN RectRgnIndirect; // rax
  CMFCPropertyGridProperty_vtbl *v23; // rax
  HBRUSH v24; // r8
  int v25; // eax
  HRGN v26; // rax
  HGDIOBJ v27; // r14
  void *v28; // rdx
  HDC__ *m_hDC; // rcx
  void (__fastcall *OnDrawName)(CMFCPropertyGridProperty *, CDC *, CRect); // rax
  HDC__ *v31; // rcx
  __int128 v32; // xmm6
  int v33; // eax
  HRGN v34; // rax
  CMFCPropertyGridProperty_vtbl *v35; // rax
  CMFCPropertyGridProperty_vtbl *v36; // rax
  CList<CMFCPropertyGridProperty *,CMFCPropertyGridProperty *>::CNode *m_pNodeHead; // rbx
  CMFCPropertyGridProperty *data; // r8
  CRgn rgnClipName_8; // [rsp+28h] [rbp-69h] OVERLAPPED BYREF
  CRgn rgnClipVal; // [rsp+38h] [rbp-59h] BYREF
  _BYTE rgnClipExpand[24]; // [rsp+48h] [rbp-49h] OVERLAPPED BYREF
  _BYTE rectFill_8[48]; // [rsp+68h] [rbp-29h] OVERLAPPED BYREF

  p_m_Rect = &pProp->m_Rect;
  if ( !IsRectEmpty(&pProp->m_Rect) )
  {
    bottom = this->m_rectList.bottom;
    if ( pProp->m_Rect.top >= bottom )
      return 0;
    if ( pProp->m_Rect.bottom >= this->m_rectList.top )
    {
      left = this->m_rectList.left;
      v9 = left + this->m_nLeftColumnWidth;
      LODWORD(rgnClipVal.__vftable) = -1;
      if ( this->m_bVSDotNetLook )
      {
        *(CRect *)&rgnClipExpand[8] = *p_m_Rect;
        v10 = _mm_cvtsi128_si32(*(__m128i *)&rgnClipExpand[8]);
        if ( pProp->m_bGroup )
        {
          v11 = *(_DWORD *)&rgnClipExpand[16];
        }
        else
        {
          v11 = v10;
          if ( v9 < v10 )
            v11 = v9;
          *(_DWORD *)&rgnClipExpand[16] = v11;
        }
        v12 = *(_DWORD *)&rgnClipExpand[20];
        if ( pProp->m_bIsValueList )
        {
          v11 = v10 + *(_DWORD *)&rgnClipExpand[20] - *(_DWORD *)&rgnClipExpand[12];
          *(_DWORD *)&rgnClipExpand[16] = v11;
        }
        *(_DWORD *)&rgnClipExpand[8] = left;
        if ( *(int *)&rgnClipExpand[20] >= bottom )
          v12 = bottom;
        *(_DWORD *)&rgnClipExpand[20] = v12;
        if ( left < v11 )
        {
          m_clrGroupBackground = this->m_clrGroupBackground;
          if ( m_clrGroupBackground == -1 )
            m_clrGroupBackground = this->m_clrGray;
          CBrush::CBrush((CBrush *)&rgnClipName_8, m_clrGroupBackground);
          FillRect(pDC->m_hDC, (const RECT *)&rgnClipExpand[8], (HBRUSH)rgnClipName_8.m_hObject);
          rgnClipName_8.__vftable = (CRgn_vtbl *)CBrush::`vftable';
          CGdiObject::~CGdiObject(&rgnClipName_8);
        }
      }
      if ( !pProp->m_bEnabled )
      {
        SetTextColor = pDC->SetTextColor;
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          afxGlobalData.m_bInitialized = 1;
        }
        LODWORD(rgnClipVal.__vftable) = SetTextColor(pDC, afxGlobalData.clrGrayedText);
      }
      v15 = *(__m128i *)p_m_Rect;
      rgnClipName_8 = (CRgn)*p_m_Rect;
      if ( pProp->m_bGroup && !pProp->m_bIsValueList && this->m_bGroupNameFullWidth )
      {
        m_hObject = _mm_cvtsi128_si32(_mm_srli_si128(v15, 8));
      }
      else
      {
        v17 = pProp->HasValueField(pProp);
        m_hObject = (int)rgnClipName_8.m_hObject;
        if ( v17 )
          m_hObject = v9;
        LODWORD(rgnClipName_8.m_hObject) = m_hObject;
        v15 = (__m128i)rgnClipName_8;
      }
      if ( pProp->m_bGroup )
      {
        if ( this->m_bGroupNameFullWidth && !this->m_bVSDotNetLook && !pProp->m_bIsValueList )
        {
          *(__m128i *)rectFill_8 = v15;
          *(_DWORD *)&rectFill_8[4] = v15.m128i_i32[1] + 1;
          if ( this == (CMFCPropertyGridCtrl *)-1696LL || (v18 = (HBRUSH)this->m_brBackground.m_hObject) == 0 )
          {
            if ( !afxGlobalData.m_bInitialized )
            {
              AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
              afxGlobalData.m_bInitialized = 1;
            }
            v18 = (HBRUSH)afxGlobalData.brWindow.m_hObject;
          }
          FillRect(pDC->m_hDC, (const RECT *)rectFill_8, v18);
        }
        *(__m128i *)rectFill_8 = v15;
        v19 = this->m_nRowHeight + _mm_cvtsi128_si32(v15);
        LODWORD(rgnClipName_8.__vftable) = v19;
        *(_DWORD *)&rectFill_8[8] = v19;
        *(_QWORD *)&rgnClipExpand[16] = 0;
        *(_QWORD *)&rgnClipExpand[8] = CRgn::`vftable';
        v20 = *(_OWORD *)rectFill_8;
        *(_OWORD *)&rectFill_8[16] = *(_OWORD *)rectFill_8;
        v21 = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)rectFill_8, 12));
        if ( _mm_srli_si128(*(__m128i *)rectFill_8, 8).m128i_i32[1] >= this->m_rectList.bottom )
          v21 = this->m_rectList.bottom;
        *(_DWORD *)&rectFill_8[28] = v21;
        RectRgnIndirect = CreateRectRgnIndirect((const RECT *)&rectFill_8[16]);
        CGdiObject::Attach((CGdiObject *)&rgnClipExpand[8], RectRgnIndirect);
        CDC::SelectClipRgn(pDC, (CRgn *)&rgnClipExpand[8]);
        v23 = pProp->__vftable;
        *(_OWORD *)rectFill_8 = v20;
        ((void (__fastcall *)(CMFCPropertyGridProperty *, CDC *, _BYTE *))v23->OnDrawExpandBox)(pProp, pDC, rectFill_8);
        *(_QWORD *)&rgnClipExpand[8] = CRgn::`vftable';
        CGdiObject::~CGdiObject((CGdiObject *)&rgnClipExpand[8]);
        v15 = (__m128i)rgnClipName_8;
      }
      else
      {
        if ( !pProp->HasValueField(pProp) )
        {
          *(__m128i *)rectFill_8 = v15;
          *(_DWORD *)&rectFill_8[4] = v15.m128i_i32[1] + 1;
          if ( this == (CMFCPropertyGridCtrl *)-1696LL || (v24 = (HBRUSH)this->m_brBackground.m_hObject) == 0 )
          {
            if ( !afxGlobalData.m_bInitialized )
            {
              AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
              afxGlobalData.m_bInitialized = 1;
            }
            v24 = (HBRUSH)afxGlobalData.brWindow.m_hObject;
          }
          FillRect(pDC->m_hDC, (const RECT *)rectFill_8, v24);
        }
        v19 = _mm_cvtsi128_si32(v15);
      }
      if ( m_hObject > v19 )
      {
        rgnClipName_8.m_hObject = 0;
        rgnClipName_8.__vftable = (CRgn_vtbl *)CRgn::`vftable';
        *(__m128i *)&rectFill_8[16] = v15;
        v25 = _mm_cvtsi128_si32(_mm_srli_si128(v15, 12));
        if ( _mm_srli_si128(v15, 8).m128i_i32[1] >= this->m_rectList.bottom )
          v25 = this->m_rectList.bottom;
        *(_DWORD *)&rectFill_8[28] = v25;
        v26 = CreateRectRgnIndirect((const RECT *)&rectFill_8[16]);
        CGdiObject::Attach(&rgnClipName_8, v26);
        CDC::SelectClipRgn(pDC, &rgnClipName_8);
        v27 = 0;
        if ( pProp->m_bGroup && !pProp->m_bIsValueList )
        {
          v28 = 0;
          if ( this != (CMFCPropertyGridCtrl *)-1408LL )
            v28 = this->m_fontBold.m_hObject;
          m_hDC = 0;
          if ( pDC )
            m_hDC = pDC->m_hDC;
          v27 = SelectObject(m_hDC, v28);
        }
        OnDrawName = pProp->OnDrawName;
        *(__m128i *)rectFill_8 = v15;
        ((void (__fastcall *)(CMFCPropertyGridProperty *, CDC *, _BYTE *))OnDrawName)(pProp, pDC, rectFill_8);
        if ( v27 )
        {
          v31 = 0;
          if ( pDC )
            v31 = pDC->m_hDC;
          SelectObject(v31, v27);
        }
        rgnClipName_8.__vftable = (CRgn_vtbl *)CRgn::`vftable';
        CGdiObject::~CGdiObject(&rgnClipName_8);
      }
      *(CRect *)&rectFill_8[16] = *p_m_Rect;
      *(_DWORD *)&rectFill_8[16] = v9 + 1;
      *(_QWORD *)rgnClipExpand = 0;
      rgnClipVal.m_hObject = (void *)CRgn::`vftable';
      v32 = *(_OWORD *)&rectFill_8[16];
      *(_OWORD *)&rectFill_8[32] = *(_OWORD *)&rectFill_8[16];
      v33 = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)&rectFill_8[16], 12));
      if ( _mm_srli_si128(*(__m128i *)(rectFill_8 + 16), 8).m128i_i32[1] >= this->m_rectList.bottom )
        v33 = this->m_rectList.bottom;
      *(_DWORD *)&rectFill_8[44] = v33;
      v34 = CreateRectRgnIndirect((const RECT *)&rectFill_8[32]);
      CGdiObject::Attach((CGdiObject *)&rgnClipVal.m_hObject, v34);
      CDC::SelectClipRgn(pDC, (CRgn *)&rgnClipVal.m_hObject);
      v35 = pProp->__vftable;
      *(_OWORD *)&rectFill_8[16] = v32;
      ((void (__fastcall *)(CMFCPropertyGridProperty *, CDC *, _BYTE *))v35->OnDrawValue)(pProp, pDC, &rectFill_8[16]);
      if ( !IsRectEmpty(&pProp->m_rectButton) )
      {
        v36 = pProp->__vftable;
        *(CRect *)&rectFill_8[16] = pProp->m_rectButton;
        ((void (__fastcall *)(CMFCPropertyGridProperty *, CDC *, _BYTE *))v36->OnDrawButton)(
          pProp,
          pDC,
          &rectFill_8[16]);
      }
      CDC::SelectClipRgn(pDC, 0);
      CDC::MoveTo(pDC, (CPoint *)&rgnClipExpand[8], this->m_rectList.left, pProp->m_Rect.bottom);
      CDC::LineTo(pDC, this->m_rectList.right, pProp->m_Rect.bottom);
      if ( LODWORD(rgnClipVal.__vftable) != -1 )
        ((void (__fastcall *)(CDC *))pDC->SetTextColor)(pDC);
      rgnClipVal.m_hObject = (void *)CRgn::`vftable';
      CGdiObject::~CGdiObject((CGdiObject *)&rgnClipVal.m_hObject);
    }
  }
  if ( pProp->m_bExpanded || this->m_bAlphabeticMode )
  {
    m_pNodeHead = pProp->m_lstSubItems.m_pNodeHead;
    while ( m_pNodeHead )
    {
      data = m_pNodeHead->data;
      m_pNodeHead = m_pNodeHead->pNext;
      if ( !this->OnDrawProperty(this, pDC, data) )
        return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800cab40  mov     rax, rsp
0x1800cab43  mov     [rax+20h], rbx
0x1800cab47  push    rbp
0x1800cab48  push    rsi
0x1800cab49  push    rdi
0x1800cab4a  push    r12
0x1800cab4c  push    r13
0x1800cab4e  push    r14
0x1800cab50  push    r15
0x1800cab52  lea     rbp, [rax-5Fh]
0x1800cab56  sub     rsp, 0B0h
0x1800cab5d  movaps  xmmword ptr [rax-48h], xmm6
0x1800cab61  mov     rax, cs:__security_cookie
0x1800cab68  xor     rax, rsp
0x1800cab6b  mov     [rbp+57h+var_50], rax
0x1800cab6f  mov     rbx, pProp
0x1800cab72  mov     rdi, pDC
0x1800cab75  mov     rsi, this
0x1800cab78  lea     r12, [pProp+44h]
0x1800cab7c  mov     this, r12; lprc
0x1800cab7f  call    cs:__imp_IsRectEmpty
0x1800cab85  xor     r15d, r15d
0x1800cab88  test    eax, eax
0x1800cab8a  jnz     loc_1800CB0CF
0x1800cab90  mov     r8d, [rsi+59Ch]
0x1800cab97  cmp     [rbx+48h], r8d
0x1800cab9b  jge     loc_1800CB13E
0x1800caba1  mov     eax, [rsi+594h]
0x1800caba7  cmp     [rbx+50h], eax
0x1800cabaa  jl      loc_1800CB0CF
0x1800cabb0  mov     r10d, [rsi+590h]
0x1800cabb7  mov     r13d, [rsi+5C0h]
0x1800cabbe  add     r13d, r10d
0x1800cabc1  or      dword ptr [rbp+57h+rgnClipVal.__vftable], 0FFFFFFFFh
0x1800cabc5  cmp     [rsi+558h], r15d
0x1800cabcc  jz      loc_1800CAC69
0x1800cabd2  movups  xmm0, xmmword ptr [r12]
0x1800cabd7  movups  xmmword ptr [rbp+57h+rgnClipExpand.m_hObject], xmm0
0x1800cabdb  movd    r9d, xmm0
0x1800cabe0  cmp     [rbx+70h], r15d
0x1800cabe4  jnz     short loc_1800CABF5
0x1800cabe6  mov     ecx, r9d
0x1800cabe9  cmp     r13d, r9d
0x1800cabec  cmovl   ecx, r13d
0x1800cabf0  mov     dword ptr [rbp+57h+var_90], ecx
0x1800cabf3  jmp     short loc_1800CABF8
0x1800cabf5  mov     ecx, dword ptr [rbp+57h+var_90]
0x1800cabf8  mov     edx, dword ptr [rbp+57h+var_90+4]
0x1800cabfb  cmp     [rbx+80h], r15d
0x1800cac02  jz      short loc_1800CAC16
0x1800cac04  mov     rax, [rbp+57h+rgnClipExpand.m_hObject]
0x1800cac08  shr     rax, 20h
0x1800cac0c  mov     ecx, edx
0x1800cac0e  sub     ecx, eax
0x1800cac10  add     ecx, r9d
0x1800cac13  mov     dword ptr [rbp+57h+var_90], ecx
0x1800cac16  mov     dword ptr [rbp+57h+rgnClipExpand.m_hObject], r10d
0x1800cac1a  cmp     edx, r8d
0x1800cac1d  cmovge  edx, r8d
0x1800cac21  mov     dword ptr [rbp+57h+var_90+4], edx
0x1800cac24  cmp     r10d, ecx
0x1800cac27  jge     short loc_1800CAC69
0x1800cac29  mov     edx, [rsi+68Ch]
0x1800cac2f  cmp     edx, 0FFFFFFFFh
0x1800cac32  jnz     short loc_1800CAC3A
0x1800cac34  mov     edx, [rsi+680h]; crColor
0x1800cac3a  lea     this, [rbp+57h+rgnClipName.m_hObject]; this
0x1800cac3e  call    ??0CBrush@@QEAA@K@Z; CBrush::CBrush(ulong)
0x1800cac43  mov     pProp, [rbp+57h+hbr]; hbr
0x1800cac47  lea     pDC, [rbp+57h+rgnClipExpand.m_hObject]; lprc
0x1800cac4b  mov     this, [rdi+8]; hDC
0x1800cac4f  call    cs:__imp_FillRect
0x1800cac55  lea     rax, ??_7CBrush@@6B@; const CBrush::`vftable'
0x1800cac5c  mov     [rbp+57h+rgnClipName.m_hObject], rax
0x1800cac60  lea     this, [rbp+57h+rgnClipName.m_hObject]; this
0x1800cac64  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1800cac69  cmp     [rbx+78h], r15d
0x1800cac6d  jnz     short loc_1800CACAA
0x1800cac6f  mov     rax, [rdi]
0x1800cac72  mov     r14, [rax+70h]
0x1800cac76  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r15d; AFX_GLOBAL_DATA afxGlobalData ...
0x1800cac7d  jnz     short loc_1800CAC95
0x1800cac7f  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1800cac86  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800cac8b  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x1800cac95  mov     edx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrGrayedText; AFX_GLOBAL_DATA afxGlobalData ...
0x1800cac9b  mov     this, rdi
0x1800cac9e  mov     rax, r14
0x1800caca1  call    cs:__guard_dispatch_icall_fptr
0x1800caca7  mov     dword ptr [rbp+57h+rgnClipVal.__vftable], eax
0x1800cacaa  movups  xmm6, xmmword ptr [r12]
0x1800cacaf  movaps  xmmword ptr [rbp+57h+rgnClipName.m_hObject], xmm6
0x1800cacb3  cmp     [rbx+70h], r15d
0x1800cacb7  jz      short loc_1800CACDE
0x1800cacb9  cmp     [rbx+80h], r15d
0x1800cacc0  jnz     short loc_1800CACDE
0x1800cacc2  cmp     [rsi+600h], r15d
0x1800cacc9  jz      short loc_1800CACDE
0x1800caccb  movdqa  xmm0, xmm6
0x1800caccf  psrldq  xmm0, 8
0x1800cacd4  movd    r15d, xmm0
0x1800cacd9  xor     r14d, r14d
0x1800cacdc  jmp     short loc_1800CAD06
0x1800cacde  mov     rax, [rbx]
0x1800cace1  mov     this, rbx
0x1800cace4  mov     rax, [rax+148h]
0x1800caceb  call    cs:__guard_dispatch_icall_fptr
0x1800cacf1  mov     r15d, dword ptr [rbp+57h+hbr]
0x1800cacf5  xor     r14d, r14d
0x1800cacf8  test    eax, eax
0x1800cacfa  cmovnz  r15d, r13d
0x1800cacfe  mov     dword ptr [rbp+57h+hbr], r15d
0x1800cad02  movaps  xmm6, xmmword ptr [rbp+57h+rgnClipName.m_hObject]
0x1800cad06  lea     rax, ??_7CRgn@@6B@; const CRgn::`vftable'
0x1800cad0d  cmp     [rbx+70h], r14d
0x1800cad11  jz      loc_1800CAE45
0x1800cad17  cmp     [rsi+600h], r14d
0x1800cad1e  jz      short loc_1800CAD95
0x1800cad20  cmp     [rsi+558h], r14d
0x1800cad27  jnz     short loc_1800CAD95
0x1800cad29  cmp     [rbx+80h], r14d
0x1800cad30  jnz     short loc_1800CAD95
0x1800cad32  movdqa  xmmword ptr [rbp+57h+rectFill.right], xmm6
0x1800cad37  movq    rax, xmm6
0x1800cad3c  shr     rax, 20h
0x1800cad40  inc     eax
0x1800cad42  mov     [rbp+57h+rectFill.bottom], eax
0x1800cad45  lea     pProp, [rsi+6A0h]
0x1800cad4c  test    pProp, pProp
0x1800cad4f  jz      short loc_1800CAD5A
0x1800cad51  mov     pProp, [pProp+8]
0x1800cad55  test    pProp, pProp
0x1800cad58  jnz     short loc_1800CAD80
0x1800cad5a  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r14d; AFX_GLOBAL_DATA afxGlobalData ...
0x1800cad61  jnz     short loc_1800CAD79
0x1800cad63  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1800cad6a  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800cad6f  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x1800cad79  mov     pProp, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.brWindow.m_hObject; hbr
0x1800cad80  lea     pDC, [rbp+57h+rectFill.right]; lprc
0x1800cad84  mov     this, [rdi+8]; hDC
0x1800cad88  call    cs:__imp_FillRect
0x1800cad8e  lea     rax, ??_7CRgn@@6B@; const CRgn::`vftable'
0x1800cad95  movdqa  xmmword ptr [rbp+57h+rectFill.right], xmm6
0x1800cad9a  movd    r14d, xmm6
0x1800cad9f  add     r14d, [rsi+5BCh]
0x1800cada6  mov     dword ptr [rbp+57h+rgnClipName.m_hObject], r14d
0x1800cadaa  mov     [rbp+57h+rectNameClip.left], r14d
0x1800cadae  and     [rbp+57h+var_90], 0
0x1800cadb3  mov     [rbp+57h+rgnClipExpand.m_hObject], rax
0x1800cadb7  movaps  xmm6, xmmword ptr [rbp+57h+rectFill.right]
0x1800cadbb  movaps  xmmword ptr [rbp+57h+rectNameClip.right], xmm6
0x1800cadbf  mov     edx, [rsi+59Ch]
0x1800cadc5  movdqa  xmm0, xmm6
0x1800cadc9  psrldq  xmm0, 8
0x1800cadce  movq    this, xmm0
0x1800cadd3  shr     this, 20h
0x1800cadd7  movdqa  xmm0, xmm6
0x1800caddb  psrldq  xmm0, 0Ch
0x1800cade0  movd    eax, xmm0
0x1800cade4  cmp     ecx, edx
0x1800cade6  cmovge  eax, edx
0x1800cade9  mov     [rbp+57h+rectValClip.top], eax
0x1800cadec  lea     this, [rbp+57h+rectNameClip.right]; lprect
0x1800cadf0  call    cs:__imp_CreateRectRgnIndirect
0x1800cadf6  mov     pDC, rax; hObject
0x1800cadf9  lea     this, [rbp+57h+rgnClipExpand.m_hObject]; this
0x1800cadfd  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1800cae02  lea     pDC, [rbp+57h+rgnClipExpand.m_hObject]; pRgn
0x1800cae06  mov     this, rdi; this
0x1800cae09  call    ?SelectClipRgn@CDC@@QEAAHPEAVCRgn@@@Z; CDC::SelectClipRgn(CRgn *)
0x1800cae0e  mov     rax, [rbx]
0x1800cae11  movdqa  xmmword ptr [rbp+57h+rectFill.right], xmm6
0x1800cae16  lea     pProp, [rbp+57h+rectFill.right]
0x1800cae1a  mov     pDC, rdi
0x1800cae1d  mov     this, rbx
0x1800cae20  mov     rax, [rax+40h]
0x1800cae24  call    cs:__guard_dispatch_icall_fptr
0x1800cae2a  nop
0x1800cae2b  lea     rax, ??_7CRgn@@6B@; const CRgn::`vftable'
0x1800cae32  mov     [rbp+57h+rgnClipExpand.m_hObject], rax
0x1800cae36  lea     this, [rbp+57h+rgnClipExpand.m_hObject]; this
0x1800cae3a  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1800cae3f  movaps  xmm6, xmmword ptr [rbp+57h+rgnClipName.m_hObject]
0x1800cae43  jmp     short loc_1800CAEBD
0x1800cae45  mov     rax, [rbx]
0x1800cae48  mov     this, rbx
0x1800cae4b  mov     rax, [rax+148h]
0x1800cae52  call    cs:__guard_dispatch_icall_fptr
0x1800cae58  test    eax, eax
0x1800cae5a  jnz     short loc_1800CAEB8
0x1800cae5c  movdqa  xmmword ptr [rbp+57h+rectFill.right], xmm6
0x1800cae61  movq    rax, xmm6
0x1800cae66  shr     rax, 20h
0x1800cae6a  inc     eax
0x1800cae6c  mov     [rbp+57h+rectFill.bottom], eax
0x1800cae6f  lea     pProp, [rsi+6A0h]
0x1800cae76  test    pProp, pProp
0x1800cae79  jz      short loc_1800CAE84
0x1800cae7b  mov     pProp, [pProp+8]
0x1800cae7f  test    pProp, pProp
0x1800cae82  jnz     short loc_1800CAEAA
0x1800cae84  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r14d; AFX_GLOBAL_DATA afxGlobalData ...
0x1800cae8b  jnz     short loc_1800CAEA3
0x1800cae8d  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1800cae94  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800cae99  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x1800caea3  mov     pProp, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.brWindow.m_hObject; hbr
0x1800caeaa  lea     pDC, [rbp+57h+rectFill.right]; lprc
0x1800caeae  mov     this, [rdi+8]; hDC
0x1800caeb2  call    cs:__imp_FillRect
0x1800caeb8  movd    r14d, xmm6
0x1800caebd  cmp     r15d, r14d
0x1800caec0  jle     loc_1800CAFB2
0x1800caec6  xor     r15d, r15d
0x1800caec9  mov     [rbp+57h+hbr], r15
0x1800caecd  lea     rax, ??_7CRgn@@6B@; const CRgn::`vftable'
0x1800caed4  mov     [rbp+57h+rgnClipName.m_hObject], rax
0x1800caed8  movaps  xmmword ptr [rbp+57h+rectNameClip.right], xmm6
0x1800caedc  mov     edx, [rsi+59Ch]
0x1800caee2  movdqa  xmm0, xmm6
0x1800caee6  psrldq  xmm0, 8
0x1800caeeb  movq    this, xmm0
0x1800caef0  shr     this, 20h
0x1800caef4  movdqa  xmm0, xmm6
0x1800caef8  psrldq  xmm0, 0Ch
0x1800caefd  movd    eax, xmm0
0x1800caf01  cmp     ecx, edx
0x1800caf03  cmovge  eax, edx
0x1800caf06  mov     [rbp+57h+rectValClip.top], eax
0x1800caf09  lea     this, [rbp+57h+rectNameClip.right]; lprect
0x1800caf0d  call    cs:__imp_CreateRectRgnIndirect
0x1800caf13  mov     pDC, rax; hObject
0x1800caf16  lea     this, [rbp+57h+rgnClipName.m_hObject]; this
0x1800caf1a  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1800caf1f  lea     pDC, [rbp+57h+rgnClipName.m_hObject]; pRgn
0x1800caf23  mov     this, rdi; this
0x1800caf26  call    ?SelectClipRgn@CDC@@QEAAHPEAVCRgn@@@Z; CDC::SelectClipRgn(CRgn *)
0x1800caf2b  mov     r14d, r15d
0x1800caf2e  cmp     [rbx+70h], r15d
0x1800caf32  jz      short loc_1800CAF65
0x1800caf34  cmp     [rbx+80h], r15d
0x1800caf3b  jnz     short loc_1800CAF65
0x1800caf3d  lea     rax, [rsi+580h]
0x1800caf44  test    rax, rax
0x1800caf47  mov     edx, r15d
0x1800caf4a  jz      short loc_1800CAF50
0x1800caf4c  mov     pDC, [rax+8]; h
0x1800caf50  test    rdi, rdi
0x1800caf53  mov     this, r15
0x1800caf56  jz      short loc_1800CAF5C
0x1800caf58  mov     this, [rdi+8]; hdc
0x1800caf5c  call    cs:__imp_SelectObject
0x1800caf62  mov     r14, rax
0x1800caf65  mov     this, [rbx]
0x1800caf68  mov     rax, [this+30h]
0x1800caf6c  movdqa  xmmword ptr [rbp+57h+rectFill.right], xmm6
0x1800caf71  lea     pProp, [rbp+57h+rectFill.right]
0x1800caf75  mov     pDC, rdi
0x1800caf78  mov     this, rbx
0x1800caf7b  call    cs:__guard_dispatch_icall_fptr
0x1800caf81  test    r14, r14
0x1800caf84  jz      short loc_1800CAF9C
0x1800caf86  test    rdi, rdi
0x1800caf89  mov     this, r15
0x1800caf8c  jz      short loc_1800CAF92
0x1800caf8e  mov     this, [rdi+8]; hdc
0x1800caf92  mov     pDC, r14; h
0x1800caf95  call    cs:__imp_SelectObject
0x1800caf9b  nop
0x1800caf9c  lea     rax, ??_7CRgn@@6B@; const CRgn::`vftable'
0x1800cafa3  mov     [rbp+57h+rgnClipName.m_hObject], rax
0x1800cafa7  lea     this, [rbp+57h+rgnClipName.m_hObject]; this
0x1800cafab  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1800cafb0  jmp     short loc_1800CAFB5
0x1800cafb2  xor     r15d, r15d
0x1800cafb5  movups  xmm0, xmmword ptr [r12]
0x1800cafba  movdqu  xmmword ptr [rbp+57h+rectNameClip.right], xmm0
0x1800cafbf  lea     eax, [r13+1]
0x1800cafc3  mov     [rbp+57h+rectNameClip.right], eax
0x1800cafc6  mov     [rbp+57h+rgnClipExpand.__vftable], r15
0x1800cafca  lea     r12, ??_7CRgn@@6B@; const CRgn::`vftable'
0x1800cafd1  mov     [rbp+57h+rgnClipVal.m_hObject], r12
0x1800cafd5  movaps  xmm6, xmmword ptr [rbp+57h+rectNameClip.right]
0x1800cafd9  movaps  xmmword ptr [rbp+57h+rectValClip.right], xmm6
0x1800cafdd  mov     edx, [rsi+59Ch]
0x1800cafe3  movdqa  xmm0, xmm6
0x1800cafe7  psrldq  xmm0, 8
0x1800cafec  movq    this, xmm0
0x1800caff1  shr     this, 20h
0x1800caff5  movdqa  xmm0, xmm6
0x1800caff9  psrldq  xmm0, 0Ch
0x1800caffe  movd    eax, xmm0
0x1800cb002  cmp     ecx, edx
0x1800cb004  cmovge  eax, edx
0x1800cb007  mov     [rbp+57h+var_54], eax
0x1800cb00a  lea     this, [rbp+57h+rectValClip.right]; lprect
0x1800cb00e  call    cs:__imp_CreateRectRgnIndirect
0x1800cb014  mov     pDC, rax; hObject
0x1800cb017  lea     this, [rbp+57h+rgnClipVal.m_hObject]; this
  ... truncated ...
```
