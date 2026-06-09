# CMFCRibbonStatusBar::RecalcLayout(void)

- ea: `0x18012b960`
- end: `0x18012bee1`
- name: `?RecalcLayout@CMFCRibbonStatusBar@@UEAAXXZ`
- size: `1409`
- prototype: `void __fastcall(CMFCRibbonStatusBar *this)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x18006e040`
- `0x18012b960`
- `0x180231d70`
- `0x18023f820`
- `0x1802af110`
- `0x1802b0630`
- `0x1802b06e0`
- `0x1802b09a0`
- `0x1802b62e0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x18012b9b7`
- `USER32!GetSystemMetrics` at `0x18012b9c5`
- `USER32!GetSystemMetrics` at `0x18012bafb`
- `USER32!GetSystemMetrics` at `0x18012b9b7`
- `USER32!GetSystemMetrics` at `0x18012b9c5`
- `USER32!GetSystemMetrics` at `0x18012bafb`
- `USER32!IsZoomed` at `0x18012b9ef`
- `USER32!IsZoomed` at `0x18012b9ef`
- `USER32!GetClientRect` at `0x18012b9a4`
- `USER32!GetClientRect` at `0x18012b9a4`
- `USER32!SetRectEmpty` at `0x18012ba6d`
- `USER32!SetRectEmpty` at `0x18012bb11`
- `USER32!SetRectEmpty` at `0x18012bce9`
- `USER32!SetRectEmpty` at `0x18012ba6d`
- `USER32!SetRectEmpty` at `0x18012bb11`
- `USER32!SetRectEmpty` at `0x18012bce9`
- `USER32!SendMessageW` at `0x18012ba30`
- `USER32!SendMessageW` at `0x18012ba30`
- `USER32!InflateRect` at `0x18012bb20`
- `USER32!InflateRect` at `0x18012bb20`
- `USER32!OffsetRect` at `0x18012bae9`
- `USER32!OffsetRect` at `0x18012bae9`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=1
void __fastcall CMFCRibbonStatusBar::RecalcLayout(CMFCRibbonStatusBar *this)
{
  int v2; // ebx
  int v3; // eax
  CFrameWnd *v4; // rax
  __int64 v5; // r15
  void *v6; // rax
  CFont *v7; // rax
  int left; // ebx
  int m_cxSizeBox; // r9d
  CRect *p_m_rectSizeBox; // rcx
  __m128i v11; // xmm1
  int v12; // r8d
  int v13; // edx
  int v14; // eax
  __int64 i; // r14
  CMFCRibbonBaseElement *v16; // rsi
  CRect v17; // xmm0
  int v18; // edx
  int v19; // r12d
  unsigned int v20; // r14d
  CRect *p_m_rectInfo; // rcx
  int v22; // eax
  __int64 v23; // rdx
  CObject *v24; // rsi
  int v25; // r13d
  CMFCRibbonBaseElement *v26; // rbx
  CRect v27; // xmm0
  int v28; // edx
  int v29; // eax
  int v30; // edx
  int v31; // [rsp+28h] [rbp-49h] BYREF
  int v32; // [rsp+2Ch] [rbp-45h]
  int v33; // [rsp+30h] [rbp-41h]
  CRect v34; // [rsp+38h] [rbp-39h]
  CRect v35; // [rsp+48h] [rbp-29h]
  CClientDC dc; // [rsp+58h] [rbp-19h] BYREF
  _BYTE rect[24]; // [rsp+88h] [rbp+17h] OVERLAPPED BYREF

  *(_OWORD *)&rect[8] = 0;
  GetClientRect(this->m_hWnd, (LPRECT)&rect[8]);
  v2 = *(_DWORD *)&rect[20] - *(_DWORD *)&rect[12];
  if ( GetSystemMetrics(2) + 1 >= v2 )
    v3 = *(_DWORD *)&rect[20] - *(_DWORD *)&rect[12];
  else
    v3 = GetSystemMetrics(2) + 1;
  this->m_cxSizeBox = v3;
  v4 = AFXGetParentFrame(this);
  v5 = 0;
  if ( v4 && IsZoomed(v4->m_hWnd) )
    this->m_cxSizeBox = 0;
  if ( (CWnd::GetStyle(this) & 0x100) == 0 )
    this->m_cxSizeBox = 0;
  CClientDC::CClientDC((CClientDC *)&dc.m_hDC, this);
  v6 = (void *)SendMessageW(this->m_hWnd, 0x31u, 0, 0);
  v7 = (CFont *)CGdiObject::FromHandle(v6);
  *(_QWORD *)rect = CDC::SelectObject((CDC *)&dc.m_hDC, v7);
  if ( !*(_QWORD *)rect )
    goto LABEL_56;
  left = *(_DWORD *)&rect[16] - this->m_cxSizeBox;
  *(_DWORD *)&rect[16] = left;
  SetRectEmpty(&this->m_rectResizeBottom);
  m_cxSizeBox = this->m_cxSizeBox;
  p_m_rectSizeBox = &this->m_rectSizeBox;
  if ( m_cxSizeBox )
  {
    v11 = _mm_loadu_si128((const __m128i *)&rect[8]);
    *p_m_rectSizeBox = (CRect)v11;
    v12 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 8));
    p_m_rectSizeBox->left = v12;
    v13 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 12)) + this->m_cyTopBorder - _mm_cvtsi128_si32(_mm_srli_si128(v11, 4));
    if ( m_cxSizeBox >= v13 )
      m_cxSizeBox = v13;
    this->m_rectSizeBox.right = v12 + m_cxSizeBox;
    if ( this->m_bBottomFrame )
    {
      OffsetRect(p_m_rectSizeBox, 0, -2);
      this->m_rectResizeBottom = *(CRect *)&rect[8];
      this->m_rectResizeBottom.top = this->m_rectResizeBottom.bottom - GetSystemMetrics(33);
    }
  }
  else
  {
    SetRectEmpty(p_m_rectSizeBox);
  }
  InflateRect((LPRECT)&rect[8], 0, -2);
  v14 = LODWORD(this->m_arExElements.m_nSize) - 1;
  for ( i = v14; i >= 0; --i )
  {
    if ( i >= this->m_arExElements.m_nSize )
      AfxThrowInvalidArgException();
    v16 = this->m_arExElements.m_pData[i];
    v16->OnCalcTextSize(v16, (CDC *)&dc.m_hDC);
    v16->GetSize(v16, (CSize *)&v31, (CDC *)&dc.m_hDC);
    if ( left - v31 >= *(int *)&rect[8] && v16->m_bIsVisible )
    {
      if ( v16->CanBeStretched(v16) )
      {
        v34.left = left - v31;
        *(_QWORD *)&v34.top = __PAIR64__(left, *(unsigned int *)&rect[12]);
        v34.bottom = *(_DWORD *)&rect[20];
        v17 = v34;
      }
      else
      {
        v18 = 0;
        if ( (*(_DWORD *)&rect[20] - v32 - *(_DWORD *)&rect[12]) / 2 >= 0 )
          v18 = (*(_DWORD *)&rect[20] - v32 - *(_DWORD *)&rect[12]) / 2;
        v35.left = left - v31;
        v35.right = left;
        v35.top = *(_DWORD *)&rect[12] + v18;
        v35.bottom = *(_DWORD *)&rect[12] + v18 + v32;
        v17 = v35;
      }
      v16->m_rect = v17;
      left = v16->m_rect.left;
    }
    else
    {
      v16->m_rect = 0;
    }
    v16->OnAfterChangeRect(v16, (CDC *)&dc.m_hDC);
  }
  v19 = left - 10;
  v20 = *(_DWORD *)&rect[8];
  p_m_rectInfo = &this->m_rectInfo;
  if ( *((_DWORD *)this->m_strInfo.m_pszData - 4) )
  {
    *p_m_rectInfo = *(CRect *)&rect[8];
    this->m_rectInfo.right = v19;
    v22 = LODWORD(this->m_arElements.m_nSize) - 1;
    v23 = v22;
    if ( v22 >= 0 )
    {
      while ( v23 < this->m_arElements.m_nSize )
      {
        this->m_arElements.m_pData[v23--]->m_rect = 0;
        if ( v23 < 0 )
          goto LABEL_32;
      }
LABEL_56:
      AfxThrowInvalidArgException();
    }
  }
  else
  {
    SetRectEmpty(p_m_rectInfo);
    this->m_cxFree = v19 - *(_DWORD *)&rect[8];
    v33 = 1;
    v24 = 0;
    v25 = 0;
    if ( SLODWORD(this->m_arElements.m_nSize) > 0 )
    {
      do
      {
        if ( v5 < 0 || v5 >= this->m_arElements.m_nSize )
          AfxThrowInvalidArgException();
        v26 = this->m_arElements.m_pData[v5];
        LODWORD(dc.__vftable) = CObject::IsKindOf(v26, (const CRuntimeClass *)&CMFCRibbonSeparator::`vftable'[149]);
        if ( LODWORD(dc.__vftable) && v33 )
        {
          v26->m_rect = 0;
        }
        else
        {
          v26->OnCalcTextSize(v26, (CDC *)&dc.m_hDC);
          v26->GetSize(v26, (CSize *)&v31, (CDC *)&dc.m_hDC);
          if ( (int)(v20 + v31) <= v19 && v26->m_bIsVisible )
          {
            if ( v26->CanBeStretched(v26) )
            {
              *(_QWORD *)&v35.left = __PAIR64__(*(unsigned int *)&rect[12], v20);
              v35.right = v20 + v31;
              v35.bottom = *(_DWORD *)&rect[20];
              v27 = v35;
            }
            else
            {
              v28 = v32;
              if ( v32 >= *(_DWORD *)&rect[20] - *(_DWORD *)&rect[12] )
                v28 = *(_DWORD *)&rect[20] - *(_DWORD *)&rect[12];
              v32 = v28;
              v29 = (*(_DWORD *)&rect[20] - v28 - *(_DWORD *)&rect[12]) / 2;
              v30 = 0;
              if ( v29 >= 0 )
                v30 = v29;
              v34.left = v20;
              v34.right = v20 + v31;
              v34.top = *(_DWORD *)&rect[12] + v30;
              v34.bottom = *(_DWORD *)&rect[12] + v30 + v32;
              v27 = v34;
            }
            v26->m_rect = v27;
            v20 += v31;
            this->m_cxFree = v19 - v20;
            v33 = (int)dc.__vftable;
            v24 = v26;
          }
          else
          {
            v26->m_rect = 0;
          }
          v26->OnAfterChangeRect(v26, (CDC *)&dc.m_hDC);
        }
        ++v25;
        ++v5;
      }
      while ( v25 < SLODWORD(this->m_arElements.m_nSize) );
      if ( v24 && CObject::IsKindOf(v24, (const CRuntimeClass *)&CMFCRibbonSeparator::`vftable'[149]) )
      {
        *(_OWORD *)&v24[25].__vftable = 0;
        ((void (__fastcall *)(CObject *, HDC__ **))v24->__vftable[15].GetRuntimeClass)(v24, &dc.m_hDC);
      }
    }
  }
LABEL_32:
  CDC::SelectObject((CDC *)&dc.m_hDC, *(CFont **)rect);
  CClientDC::~CClientDC((CClientDC *)&dc.m_hDC);
}

```

## disassembly

```asm
0x18012b960  mov     rax, rsp
0x18012b963  mov     [rax+10h], rbx
0x18012b967  mov     [rax+18h], rsi
0x18012b96b  mov     [rax+20h], rdi
0x18012b96f  push    rbp
0x18012b970  push    r12
0x18012b972  push    r13
0x18012b974  push    r14
0x18012b976  push    r15
0x18012b978  lea     rbp, [rax-5Fh]
0x18012b97c  sub     rsp, 0A0h
0x18012b983  mov     rax, cs:__security_cookie
0x18012b98a  xor     rax, rsp
0x18012b98d  mov     [rbp+57h+var_28], rax
0x18012b991  mov     rdi, this
0x18012b994  xorps   xmm0, xmm0
0x18012b997  movdqu  xmmword ptr [rbp+57h+rect.right], xmm0
0x18012b99c  lea     rdx, [rbp+57h+rect.right]; lpRect
0x18012b9a0  mov     this, [this+40h]; hWnd
0x18012b9a4  call    cs:__imp_GetClientRect
0x18012b9aa  mov     ebx, [rbp+57h+var_2C]
0x18012b9ad  sub     ebx, [rbp+57h+rect.bottom]
0x18012b9b0  mov     esi, 2
0x18012b9b5  mov     ecx, esi; nIndex
0x18012b9b7  call    cs:__imp_GetSystemMetrics
0x18012b9bd  inc     eax
0x18012b9bf  cmp     eax, ebx
0x18012b9c1  jge     short loc_18012B9CF
0x18012b9c3  mov     ecx, esi; nIndex
0x18012b9c5  call    cs:__imp_GetSystemMetrics
0x18012b9cb  inc     eax
0x18012b9cd  jmp     short loc_18012B9D5
0x18012b9cf  mov     eax, [rbp+57h+var_2C]
0x18012b9d2  sub     eax, [rbp+57h+rect.bottom]
0x18012b9d5  mov     [rdi+20D0h], eax
0x18012b9db  mov     this, rdi; pWnd
0x18012b9de  call    ?AFXGetParentFrame@@YAPEAVCFrameWnd@@PEBVCWnd@@@Z; AFXGetParentFrame(CWnd const *)
0x18012b9e3  xor     r15d, r15d
0x18012b9e6  test    rax, rax
0x18012b9e9  jz      short loc_18012BA00
0x18012b9eb  mov     this, [rax+40h]; hWnd
0x18012b9ef  call    cs:__imp_IsZoomed
0x18012b9f5  test    eax, eax
0x18012b9f7  jz      short loc_18012BA00
0x18012b9f9  mov     [rdi+20D0h], r15d
0x18012ba00  mov     this, rdi; this
0x18012ba03  call    ?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x18012ba08  bt      eax, 8
0x18012ba0c  jb      short loc_18012BA15
0x18012ba0e  mov     [rdi+20D0h], r15d
0x18012ba15  mov     rdx, rdi; pWnd
0x18012ba18  lea     this, [rbp+57h+dc.m_hDC]; this
0x18012ba1c  call    ??0CClientDC@@QEAA@PEAVCWnd@@@Z; CClientDC::CClientDC(CWnd *)
0x18012ba21  nop
0x18012ba22  xor     r9d, r9d; lParam
0x18012ba25  xor     r8d, r8d; wParam
0x18012ba28  lea     edx, [r9+31h]; Msg
0x18012ba2c  mov     this, [rdi+40h]; hWnd
0x18012ba30  call    cs:__imp_SendMessageW
0x18012ba36  mov     this, rax; h
0x18012ba39  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18012ba3e  mov     rdx, rax; pFont
0x18012ba41  lea     this, [rbp+57h+dc.m_hDC]; this
0x18012ba45  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18012ba4a  mov     qword ptr [rbp+57h+rect.left], rax
0x18012ba4e  test    rax, rax
0x18012ba51  jz      loc_18012BED5
0x18012ba57  mov     ebx, [rbp+57h+var_30]
0x18012ba5a  sub     ebx, [rdi+20D0h]
0x18012ba60  mov     [rbp+57h+var_30], ebx
0x18012ba63  lea     rsi, [rdi+20E8h]
0x18012ba6a  mov     this, rsi; lprc
0x18012ba6d  call    cs:__imp_SetRectEmpty
0x18012ba73  mov     r9d, [rdi+20D0h]
0x18012ba7a  lea     this, [rdi+20D8h]; lprc
0x18012ba81  mov     r14d, 0FFFFFFFEh
0x18012ba87  test    r9d, r9d
0x18012ba8a  jz      loc_18012BB11
0x18012ba90  movdqu  xmm1, xmmword ptr [rbp+57h+rect.right]
0x18012ba95  movdqu  xmmword ptr [this], xmm1
0x18012ba99  movdqa  xmm0, xmm1
0x18012ba9d  psrldq  xmm0, 8
0x18012baa2  movd    r8d, xmm0
0x18012baa7  mov     [this], r8d
0x18012baaa  mov     edx, [rdi+1D0h]
0x18012bab0  movdqa  xmm0, xmm1
0x18012bab4  psrldq  xmm0, 4
0x18012bab9  movd    eax, xmm0
0x18012babd  sub     edx, eax
0x18012babf  psrldq  xmm1, 0Ch
0x18012bac4  movd    eax, xmm1
0x18012bac8  add     edx, eax
0x18012baca  cmp     r9d, edx
0x18012bacd  cmovge  r9d, edx
0x18012bad1  add     r9d, r8d
0x18012bad4  mov     [rdi+20E0h], r9d
0x18012badb  cmp     [rdi+2108h], r15d
0x18012bae2  jz      short loc_18012BB17
0x18012bae4  mov     r8d, r14d; dy
0x18012bae7  xor     edx, edx; dx
0x18012bae9  call    cs:__imp_OffsetRect
0x18012baef  movups  xmm0, xmmword ptr [rbp+57h+rect.right]
0x18012baf3  movdqu  xmmword ptr [rsi], xmm0
0x18012baf7  lea     ecx, [r14+23h]; nIndex
0x18012bafb  call    cs:__imp_GetSystemMetrics
0x18012bb01  mov     ecx, [rdi+20F4h]
0x18012bb07  sub     ecx, eax
0x18012bb09  mov     [rdi+20ECh], ecx
0x18012bb0f  jmp     short loc_18012BB17
0x18012bb11  call    cs:__imp_SetRectEmpty
0x18012bb17  mov     r8d, r14d; dy
0x18012bb1a  xor     edx, edx; dx
0x18012bb1c  lea     this, [rbp+57h+rect.right]; lprc
0x18012bb20  call    cs:__imp_InflateRect
0x18012bb26  mov     eax, [rdi+21A0h]
0x18012bb2c  sub     eax, 1
0x18012bb2f  movsxd  r14, eax
0x18012bb32  js      loc_18012BC3F
0x18012bb38  cmp     r14, [rdi+21A0h]
0x18012bb3f  jge     loc_18012BEDB
0x18012bb45  mov     rax, [rdi+2198h]
0x18012bb4c  mov     rsi, [rax+r14*8]
0x18012bb50  mov     rax, [rsi]
0x18012bb53  lea     rdx, [rbp+57h+dc.m_hDC]
0x18012bb57  mov     this, rsi
0x18012bb5a  mov     rax, [rax+310h]
0x18012bb61  call    cs:__guard_dispatch_icall_fptr
0x18012bb67  mov     rax, [rsi]
0x18012bb6a  lea     r8, [rbp+57h+dc.m_hDC]
0x18012bb6e  lea     rdx, [rbp+57h+var_A0]
0x18012bb72  mov     this, rsi
0x18012bb75  mov     rax, [rax+1F8h]
0x18012bb7c  call    cs:__guard_dispatch_icall_fptr
0x18012bb82  mov     eax, ebx
0x18012bb84  sub     eax, dword ptr [rbp+57h+var_A0]
0x18012bb87  cmp     eax, [rbp+57h+rect.right]
0x18012bb8a  jl      loc_18012BC13
0x18012bb90  cmp     [rsi+15Ch], r15d
0x18012bb97  jz      short loc_18012BC13
0x18012bb99  mov     rax, [rsi]
0x18012bb9c  mov     this, rsi
0x18012bb9f  mov     rax, [rax+320h]
0x18012bba6  call    cs:__guard_dispatch_icall_fptr
0x18012bbac  test    eax, eax
0x18012bbae  jz      short loc_18012BBCD
0x18012bbb0  mov     eax, ebx
0x18012bbb2  sub     eax, dword ptr [rbp+57h+var_A0]
0x18012bbb5  mov     dword ptr [rbp+57h+var_90], eax
0x18012bbb8  mov     eax, [rbp+57h+rect.bottom]
0x18012bbbb  mov     dword ptr [rbp+57h+var_90+4], eax
0x18012bbbe  mov     dword ptr [rbp+57h+var_90+8], ebx
0x18012bbc1  mov     eax, [rbp+57h+var_2C]
0x18012bbc4  mov     dword ptr [rbp+57h+var_90+0Ch], eax
0x18012bbc7  movups  xmm0, [rbp+57h+var_90]
0x18012bbcb  jmp     short loc_18012BC03
0x18012bbcd  mov     eax, [rbp+57h+var_2C]
0x18012bbd0  sub     eax, dword ptr [rbp+57h+var_A0+4]
0x18012bbd3  sub     eax, [rbp+57h+rect.bottom]
0x18012bbd6  cdq
0x18012bbd7  sub     eax, edx
0x18012bbd9  sar     eax, 1
0x18012bbdb  mov     edx, r15d
0x18012bbde  cmovns  edx, eax
0x18012bbe1  add     edx, [rbp+57h+rect.bottom]
0x18012bbe4  mov     rax, [rbp+57h+var_A0]
0x18012bbe8  sub     ebx, eax
0x18012bbea  mov     dword ptr [rbp+57h+var_80], ebx
0x18012bbed  lea     ecx, [rbx+rax]
0x18012bbf0  mov     dword ptr [rbp+57h+var_80+8], ecx
0x18012bbf3  mov     dword ptr [rbp+57h+var_80+4], edx
0x18012bbf6  shr     rax, 20h
0x18012bbfa  add     eax, edx
0x18012bbfc  mov     dword ptr [rbp+57h+var_80+0Ch], eax
0x18012bbff  movups  xmm0, [rbp+57h+var_80]
0x18012bc03  movdqu  xmmword ptr [rsi+0C8h], xmm0
0x18012bc0b  mov     ebx, [rsi+0C8h]
0x18012bc11  jmp     short loc_18012BC1E
0x18012bc13  xorps   xmm0, xmm0
0x18012bc16  movdqu  xmmword ptr [rsi+0C8h], xmm0
0x18012bc1e  mov     rax, [rsi]
0x18012bc21  lea     rdx, [rbp+57h+dc.m_hDC]
0x18012bc25  mov     this, rsi
0x18012bc28  mov     rax, [rax+258h]
0x18012bc2f  call    cs:__guard_dispatch_icall_fptr
0x18012bc35  sub     r14, 1
0x18012bc39  jns     loc_18012BB38
0x18012bc3f  lea     r12d, [rbx-0Ah]
0x18012bc43  mov     r14d, [rbp+57h+rect.right]
0x18012bc47  lea     this, [rdi+20F8h]; lprc
0x18012bc4e  mov     rax, [rdi+2110h]
0x18012bc55  cmp     [rax-10h], r15d
0x18012bc59  jz      loc_18012BCE9
0x18012bc5f  movups  xmm0, xmmword ptr [rbp+57h+rect.right]
0x18012bc63  movdqu  xmmword ptr [this], xmm0
0x18012bc67  mov     [rdi+2100h], r12d
0x18012bc6e  mov     eax, [rdi+2178h]
0x18012bc74  sub     eax, 1
0x18012bc77  movsxd  rdx, eax
0x18012bc7a  js      short loc_18012BCA5
0x18012bc7c  cmp     rdx, [rdi+2178h]
0x18012bc83  jge     loc_18012BED5
0x18012bc89  mov     rax, [rdi+2170h]
0x18012bc90  mov     this, [rax+rdx*8]
0x18012bc94  xorps   xmm0, xmm0
0x18012bc97  movdqu  xmmword ptr [this+0C8h], xmm0
0x18012bc9f  sub     rdx, 1
0x18012bca3  jns     short loc_18012BC7C
0x18012bca5  mov     rdx, qword ptr [rbp+57h+rect.left]; pFont
0x18012bca9  lea     this, [rbp+57h+dc.m_hDC]; this
0x18012bcad  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18012bcb2  nop
0x18012bcb3  lea     this, [rbp+57h+dc.m_hDC]; this
0x18012bcb7  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x18012bcbc  mov     this, [rbp+57h+var_28]
0x18012bcc0  xor     this, rsp; StackCookie
0x18012bcc3  call    __security_check_cookie
0x18012bcc8  lea     r11, [rsp+0C0h+var_20]
0x18012bcd0  mov     rbx, [r11+38h]
0x18012bcd4  mov     rsi, [r11+40h]
0x18012bcd8  mov     rdi, [r11+48h]
0x18012bcdc  mov     rsp, r11
0x18012bcdf  pop     r15
0x18012bce1  pop     r14
0x18012bce3  pop     r13
0x18012bce5  pop     r12
0x18012bce7  pop     rbp
0x18012bce8  retn
0x18012bce9  call    cs:__imp_SetRectEmpty
0x18012bcef  nop
0x18012bcf0  mov     eax, r12d
0x18012bcf3  sub     eax, [rbp+57h+rect.right]
0x18012bcf6  mov     [rdi+20D4h], eax
0x18012bcfc  mov     [rbp+57h+var_98], 1
0x18012bd03  mov     rsi, r15
0x18012bd06  mov     r13d, r15d
0x18012bd09  cmp     [rdi+2178h], r15d
0x18012bd10  jle     short loc_18012BCA5
0x18012bd12  test    r15, r15
0x18012bd15  js      loc_18012BECF
0x18012bd1b  cmp     r15, [rdi+2178h]
0x18012bd22  jge     loc_18012BECF
0x18012bd28  mov     rax, [rdi+2170h]
0x18012bd2f  mov     rbx, [rax+r15*8]
0x18012bd33  lea     rdx, ??_7CMFCRibbonSeparator@@6B@+4A8h; pClass
0x18012bd3a  mov     this, rbx; this
0x18012bd3d  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18012bd42  mov     dword ptr [rbp+57h+dc.__vftable], eax
0x18012bd45  test    eax, eax
0x18012bd47  jz      short loc_18012BD5F
0x18012bd49  cmp     [rbp+57h+var_98], 0
0x18012bd4d  jz      short loc_18012BD5F
0x18012bd4f  xorps   xmm0, xmm0
0x18012bd52  movdqu  xmmword ptr [rbx+0C8h], xmm0
0x18012bd5a  jmp     loc_18012BE75
0x18012bd5f  mov     rax, [rbx]
0x18012bd62  lea     rdx, [rbp+57h+dc.m_hDC]
0x18012bd66  mov     this, rbx
0x18012bd69  mov     rax, [rax+310h]
0x18012bd70  call    cs:__guard_dispatch_icall_fptr
0x18012bd76  mov     rax, [rbx]
0x18012bd79  lea     r8, [rbp+57h+dc.m_hDC]
0x18012bd7d  lea     rdx, [rbp+57h+var_A0]
0x18012bd81  mov     this, rbx
0x18012bd84  mov     rax, [rax+1F8h]
0x18012bd8b  call    cs:__guard_dispatch_icall_fptr
0x18012bd91  mov     ecx, dword ptr [rbp+57h+var_A0]
0x18012bd94  add     ecx, r14d
0x18012bd97  cmp     ecx, r12d
0x18012bd9a  jg      loc_18012BE53
0x18012bda0  cmp     dword ptr [rbx+15Ch], 0
0x18012bda7  jz      loc_18012BE53
0x18012bdad  mov     rax, [rbx]
0x18012bdb0  mov     this, rbx
0x18012bdb3  mov     rax, [rax+320h]
0x18012bdba  call    cs:__guard_dispatch_icall_fptr
0x18012bdc0  test    eax, eax
0x18012bdc2  jz      short loc_18012BDE3
0x18012bdc4  mov     ecx, dword ptr [rbp+57h+var_A0]
0x18012bdc7  add     ecx, r14d
0x18012bdca  mov     dword ptr [rbp+57h+var_80], r14d
0x18012bdce  mov     eax, [rbp+57h+rect.bottom]
0x18012bdd1  mov     dword ptr [rbp+57h+var_80+4], eax
0x18012bdd4  mov     dword ptr [rbp+57h+var_80+8], ecx
0x18012bdd7  mov     eax, [rbp+57h+var_2C]
0x18012bdda  mov     dword ptr [rbp+57h+var_80+0Ch], eax
0x18012bddd  movups  xmm0, [rbp+57h+var_80]
0x18012bde1  jmp     short loc_18012BE30
0x18012bde3  mov     eax, [rbp+57h+var_2C]
0x18012bde6  mov     ecx, eax
0x18012bde8  mov     r8d, [rbp+57h+rect.bottom]
0x18012bdec  sub     ecx, r8d
0x18012bdef  mov     edx, dword ptr [rbp+57h+var_A0+4]
0x18012bdf2  cmp     edx, ecx
0x18012bdf4  cmovge  edx, ecx
0x18012bdf7  mov     dword ptr [rbp+57h+var_A0+4], edx
0x18012bdfa  sub     eax, edx
0x18012bdfc  sub     eax, r8d
0x18012bdff  cdq
0x18012be00  sub     eax, edx
0x18012be02  sar     eax, 1
  ... truncated ...
```
