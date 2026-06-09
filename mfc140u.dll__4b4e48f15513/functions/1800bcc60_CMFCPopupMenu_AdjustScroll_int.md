# CMFCPopupMenu::AdjustScroll(int)

- ea: `0x1800bcc60`
- end: `0x1800bcfd9`
- name: `?AdjustScroll@CMFCPopupMenu@@IEAAHH@Z`
- size: `889`
- prototype: `int __fastcall(CMFCPopupMenu *this, int bForceMenuBarResize)`
- caller_count: `8`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18005e7c0`
- `0x1800b8d90`
- `0x1800ba4d0`
- `0x1800bafa0`
- `0x1800bb560`
- `0x1800be610`
- `0x180121320`
- `0x180126d90`

## callees

- `0x1800bcc60`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1800bcdca`
- `USER32!GetSystemMetrics` at `0x1800bcdca`
- `USER32!GetClientRect` at `0x1800bccba`
- `USER32!GetClientRect` at `0x1800bccba`
- `USER32!KillTimer` at `0x1800bce84`
- `USER32!KillTimer` at `0x1800bce84`
- `USER32!SetRectEmpty` at `0x1800bcd9b`
- `USER32!SetRectEmpty` at `0x1800bcda4`
- `USER32!SetRectEmpty` at `0x1800bcd9b`
- `USER32!SetRectEmpty` at `0x1800bcda4`
- `USER32!InvalidateRect` at `0x1800bcf42`
- `USER32!InvalidateRect` at `0x1800bcf56`
- `USER32!InvalidateRect` at `0x1800bcf7e`
- `USER32!InvalidateRect` at `0x1800bcf92`
- `USER32!InvalidateRect` at `0x1800bcf42`
- `USER32!InvalidateRect` at `0x1800bcf56`
- `USER32!InvalidateRect` at `0x1800bcf7e`
- `USER32!InvalidateRect` at `0x1800bcf92`
- `USER32!EqualRect` at `0x1800bcea1`
- `USER32!EqualRect` at `0x1800bceb6`
- `USER32!EqualRect` at `0x1800bcf2a`
- `USER32!EqualRect` at `0x1800bcf69`
- `USER32!EqualRect` at `0x1800bcea1`
- `USER32!EqualRect` at `0x1800bceb6`
- `USER32!EqualRect` at `0x1800bcf2a`
- `USER32!EqualRect` at `0x1800bcf69`
- `USER32!InflateRect` at `0x1800bccf6`
- `USER32!InflateRect` at `0x1800bccf6`
- `USER32!UpdateWindow` at `0x1800bcfa4`
- `USER32!UpdateWindow` at `0x1800bcfa4`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall CMFCPopupMenu::AdjustScroll(CMFCPopupMenu *this, int bForceMenuBarResize)
{
  CMFCPopupMenuBar *v4; // rax
  HWND__ *m_hWnd; // rcx
  CMFCPopupMenuBar *v6; // r15
  int m_iShadowSize; // ecx
  int v8; // r12d
  CMFCPopupMenu::LOGO_LOCATION m_nLogoLocation; // edx
  __int32 v10; // edx
  __int32 v11; // edx
  int v12; // edx
  bool v13; // zf
  CRect v14; // xmm0
  int m_iScrollBtnHeight; // ecx
  CRect v16; // xmm0
  int v17; // ecx
  int v18; // esi
  unsigned int v19; // edi
  _BYTE rectClient_8[48]; // [rsp+60h] [rbp-1h] OVERLAPPED BYREF

  v4 = this->GetMenuBar(this);
  m_hWnd = this->m_hWnd;
  v6 = v4;
  *(_OWORD *)rectClient_8 = 0;
  GetClientRect(m_hWnd, (LPRECT)rectClient_8);
  if ( !CMFCToolBar::m_bCustomizeMode )
  {
    m_iShadowSize = this->m_iShadowSize;
    *(_DWORD *)&rectClient_8[8] -= m_iShadowSize;
    *(_DWORD *)&rectClient_8[12] -= m_iShadowSize;
  }
  v8 = this->GetBorderSize(this);
  InflateRect((LPRECT)rectClient_8, -v8, -v8);
  m_nLogoLocation = this->m_nLogoLocation;
  if ( m_nLogoLocation )
  {
    v10 = m_nLogoLocation - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        if ( v11 == 1 )
          *(_DWORD *)&rectClient_8[12] -= this->m_iLogoWidth;
      }
      else
      {
        *(_DWORD *)&rectClient_8[4] += this->m_iLogoWidth;
      }
    }
    else
    {
      *(_DWORD *)&rectClient_8[8] -= this->m_iLogoWidth;
    }
  }
  else
  {
    *(_DWORD *)rectClient_8 += this->m_iLogoWidth;
  }
  v12 = *(_DWORD *)&rectClient_8[4] + this->m_rectTearOffCaption.bottom - this->m_rectTearOffCaption.top;
  v13 = this->m_bIsResizeBarOnTop == 0;
  *(_DWORD *)&rectClient_8[4] = v12;
  if ( v13 )
    *(_DWORD *)&rectClient_8[12] += this->m_rectResize.top - this->m_rectResize.bottom;
  else
    *(_DWORD *)&rectClient_8[4] = this->m_rectResize.bottom + v12 - this->m_rectResize.top;
  *(CRect *)&rectClient_8[16] = this->m_rectScrollUp;
  *(CRect *)&rectClient_8[32] = this->m_rectScrollDn;
  SetRectEmpty(&this->m_rectScrollUp);
  SetRectEmpty(&this->m_rectScrollDn);
  if ( this->m_bScrollable )
  {
    if ( this->m_bShowScrollBar )
    {
      *(_DWORD *)&rectClient_8[8] -= GetSystemMetrics(2);
    }
    else
    {
      if ( this->IsScrollUpAvailable(this) )
      {
        v14 = (CRect)_mm_loadu_si128((const __m128i *)rectClient_8);
        m_iScrollBtnHeight = this->m_iScrollBtnHeight;
        this->m_rectScrollUp = v14;
        this->m_rectScrollUp.top += v8;
        this->m_rectScrollUp.bottom = m_iScrollBtnHeight + this->m_rectScrollUp.top;
        *(_DWORD *)&rectClient_8[4] = m_iScrollBtnHeight + v8 + _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v14, 4));
      }
      if ( this->IsScrollDnAvailable(this) )
      {
        v16 = (CRect)_mm_loadu_si128((const __m128i *)rectClient_8);
        v17 = this->m_iScrollBtnHeight;
        this->m_rectScrollDn = v16;
        this->m_rectScrollDn.top = this->m_rectScrollDn.bottom - v17;
        *(_DWORD *)&rectClient_8[12] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v16, 12));
        *(_DWORD *)&rectClient_8[12] -= v17 + v8;
      }
    }
  }
  else if ( !this->m_bAnimationIsDone )
  {
    KillTimer(this->m_hWnd, 0xEC16u);
    this->m_iScrollMode = 0;
  }
  if ( !bForceMenuBarResize
    && EqualRect((const RECT *)&rectClient_8[16], &this->m_rectScrollUp)
    && EqualRect((const RECT *)&rectClient_8[32], &this->m_rectScrollDn) )
  {
    v6->AdjustLayout(v6);
  }
  else
  {
    ((void (__fastcall *)(CMFCPopupMenuBar *, _QWORD))v6->SetWindowPos)(v6, 0);
    this->m_nMenuBarHeight = *(_DWORD *)&rectClient_8[12] - *(_DWORD *)&rectClient_8[4];
  }
  v18 = 0;
  v19 = 1;
  if ( !EqualRect((const RECT *)&rectClient_8[16], &this->m_rectScrollUp) )
  {
    InvalidateRect(this->m_hWnd, (const RECT *)&rectClient_8[16], 1);
    InvalidateRect(this->m_hWnd, &this->m_rectScrollUp, 1);
    v18 = 1;
  }
  if ( !EqualRect((const RECT *)&rectClient_8[32], &this->m_rectScrollDn) )
  {
    InvalidateRect(this->m_hWnd, (const RECT *)&rectClient_8[32], 1);
    InvalidateRect(this->m_hWnd, &this->m_rectScrollDn, 1);
LABEL_33:
    UpdateWindow(this->m_hWnd);
    return v19;
  }
  v19 = v18;
  if ( v18 )
    goto LABEL_33;
  return v19;
}

```

## disassembly

```asm
0x1800bcc60  mov     rax, rsp
0x1800bcc63  mov     [rax+10h], rbx
0x1800bcc67  mov     [rax+18h], rsi
0x1800bcc6b  mov     [rax+20h], rdi
0x1800bcc6f  push    rbp
0x1800bcc70  push    r12
0x1800bcc72  push    r13
0x1800bcc74  push    r14
0x1800bcc76  push    r15
0x1800bcc78  lea     rbp, [rax-5Fh]
0x1800bcc7c  sub     rsp, 90h
0x1800bcc83  mov     rax, cs:__security_cookie
0x1800bcc8a  xor     rax, rsp
0x1800bcc8d  mov     [rbp+57h+var_28], rax
0x1800bcc91  mov     rax, [this]
0x1800bcc94  mov     r13d, bForceMenuBarResize
0x1800bcc97  mov     rbx, this
0x1800bcc9a  mov     rax, [rax+3A0h]
0x1800bcca1  call    cs:__guard_dispatch_icall_fptr
0x1800bcca7  mov     this, [rbx+40h]; hWnd
0x1800bccab  lea     rdx, [rbp+57h+rectClient.right]; lpRect
0x1800bccaf  xorps   xmm0, xmm0
0x1800bccb2  mov     r15, rax
0x1800bccb5  movdqu  xmmword ptr [rbp+57h+rectClient.right], xmm0
0x1800bccba  call    cs:__imp_GetClientRect
0x1800bccc0  cmp     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, 0; int CMFCToolBar::m_bCustomizeMode
0x1800bccc7  jnz     short loc_1800BCCD5
0x1800bccc9  mov     ecx, [rbx+1810h]
0x1800bcccf  sub     [rbp+57h+rectScrollUpOld.left], ecx
0x1800bccd2  sub     [rbp+57h+rectScrollUpOld.top], ecx
0x1800bccd5  mov     rax, [rbx]
0x1800bccd8  mov     this, rbx
0x1800bccdb  mov     rax, [rax+428h]
0x1800bcce2  call    cs:__guard_dispatch_icall_fptr
0x1800bcce8  mov     bForceMenuBarResize, eax
0x1800bccea  lea     this, [rbp+57h+rectClient.right]; lprc
0x1800bccee  neg     bForceMenuBarResize; dx
0x1800bccf0  mov     r12d, eax
0x1800bccf3  mov     r8d, bForceMenuBarResize; dy
0x1800bccf6  call    cs:__imp_InflateRect
0x1800bccfc  mov     bForceMenuBarResize, [rbx+1688h]
0x1800bcd02  test    bForceMenuBarResize, bForceMenuBarResize
0x1800bcd04  jz      short loc_1800BCD36
0x1800bcd06  sub     bForceMenuBarResize, 1
0x1800bcd09  jz      short loc_1800BCD2B
0x1800bcd0b  sub     bForceMenuBarResize, 1
0x1800bcd0e  jz      short loc_1800BCD20
0x1800bcd10  cmp     bForceMenuBarResize, 1
0x1800bcd13  jnz     short loc_1800BCD3F
0x1800bcd15  mov     eax, [rbx+1680h]
0x1800bcd1b  sub     [rbp+57h+rectScrollUpOld.top], eax
0x1800bcd1e  jmp     short loc_1800BCD3F
0x1800bcd20  mov     eax, [rbx+1680h]
0x1800bcd26  add     [rbp+57h+rectClient.bottom], eax
0x1800bcd29  jmp     short loc_1800BCD3F
0x1800bcd2b  mov     eax, [rbx+1680h]
0x1800bcd31  sub     [rbp+57h+rectScrollUpOld.left], eax
0x1800bcd34  jmp     short loc_1800BCD3F
0x1800bcd36  mov     eax, [rbx+1680h]
0x1800bcd3c  add     [rbp+57h+rectClient.right], eax
0x1800bcd3f  mov     bForceMenuBarResize, [rbx+1854h]
0x1800bcd45  sub     bForceMenuBarResize, [rbx+184Ch]
0x1800bcd4b  add     bForceMenuBarResize, [rbp+57h+rectClient.bottom]
0x1800bcd4e  cmp     dword ptr [rbx+1980h], 0
0x1800bcd55  mov     [rbp+57h+rectClient.bottom], bForceMenuBarResize
0x1800bcd58  jz      short loc_1800BCD6B
0x1800bcd5a  sub     bForceMenuBarResize, [rbx+199Ch]
0x1800bcd60  add     bForceMenuBarResize, [rbx+19A4h]
0x1800bcd66  mov     [rbp+57h+rectClient.bottom], bForceMenuBarResize
0x1800bcd69  jmp     short loc_1800BCD7A
0x1800bcd6b  mov     eax, [rbx+199Ch]
0x1800bcd71  sub     eax, [rbx+19A4h]
0x1800bcd77  add     [rbp+57h+rectScrollUpOld.top], eax
0x1800bcd7a  lea     rdi, [rbx+16ACh]
0x1800bcd81  movups  xmm0, xmmword ptr [rdi]
0x1800bcd84  lea     rsi, [rbx+16BCh]
0x1800bcd8b  mov     this, rdi; lprc
0x1800bcd8e  movdqu  xmmword ptr [rbp+57h+rectScrollUpOld.right], xmm0
0x1800bcd93  movups  xmm0, xmmword ptr [rsi]
0x1800bcd96  movdqu  xmmword ptr [rbp+57h+rectScrollDnOld.right], xmm0
0x1800bcd9b  call    cs:__imp_SetRectEmpty
0x1800bcda1  mov     this, rsi; lprc
0x1800bcda4  call    cs:__imp_SetRectEmpty
0x1800bcdaa  cmp     dword ptr [rbx+16A4h], 0
0x1800bcdb1  mov     r14d, 14h
0x1800bcdb7  jz      loc_1800BCE6C
0x1800bcdbd  cmp     dword ptr [rbx+16A8h], 0
0x1800bcdc4  jz      short loc_1800BCDD8
0x1800bcdc6  lea     ecx, [r14-12h]; nIndex
0x1800bcdca  call    cs:__imp_GetSystemMetrics
0x1800bcdd0  sub     [rbp+57h+rectScrollUpOld.left], eax
0x1800bcdd3  jmp     loc_1800BCE91
0x1800bcdd8  mov     rax, [rbx]
0x1800bcddb  mov     this, rbx
0x1800bcdde  mov     rax, [rax+3D8h]
0x1800bcde5  call    cs:__guard_dispatch_icall_fptr
0x1800bcdeb  test    eax, eax
0x1800bcded  jz      short loc_1800BCE25
0x1800bcdef  movdqu  xmm0, xmmword ptr [rbp+57h+rectClient.right]
0x1800bcdf4  mov     ecx, [rbx+16D0h]
0x1800bcdfa  movdqu  xmmword ptr [rdi], xmm0
0x1800bcdfe  add     [rbx+16B0h], r12d
0x1800bce05  mov     eax, [rbx+16B0h]
0x1800bce0b  lea     bForceMenuBarResize, [this+r12]
0x1800bce0f  add     eax, ecx
0x1800bce11  psrldq  xmm0, 4
0x1800bce16  mov     [rbx+16B8h], eax
0x1800bce1c  movd    eax, xmm0
0x1800bce20  add     eax, bForceMenuBarResize
0x1800bce22  mov     [rbp+57h+rectClient.bottom], eax
0x1800bce25  mov     rax, [rbx]
0x1800bce28  mov     this, rbx
0x1800bce2b  mov     rax, [rax+3E0h]
0x1800bce32  call    cs:__guard_dispatch_icall_fptr
0x1800bce38  test    eax, eax
0x1800bce3a  jz      short loc_1800BCE91
0x1800bce3c  movdqu  xmm0, xmmword ptr [rbp+57h+rectClient.right]
0x1800bce41  mov     ecx, [rbx+16D0h]
0x1800bce47  movdqu  xmmword ptr [rsi], xmm0
0x1800bce4b  mov     eax, [rbx+16C8h]
0x1800bce51  sub     eax, ecx
0x1800bce53  psrldq  xmm0, 0Ch
0x1800bce58  mov     [rbx+16C0h], eax
0x1800bce5e  lea     eax, [this+r12]
0x1800bce62  movd    [rbp+57h+rectScrollUpOld.top], xmm0
0x1800bce67  sub     [rbp+57h+rectScrollUpOld.top], eax
0x1800bce6a  jmp     short loc_1800BCE91
0x1800bce6c  cmp     dword ptr [rbx+169Ch], 0
0x1800bce73  jnz     short loc_1800BCE91
0x1800bce75  mov     this, [rbx+40h]; hWnd
0x1800bce79  mov     bForceMenuBarResize, 0EC16h; uIDEvent
0x1800bce7e  mov     r14d, 1Ch
0x1800bce84  call    cs:__imp_KillTimer
0x1800bce8a  and     dword ptr [rbx+16CCh], 0
0x1800bce91  test    r13d, r13d
0x1800bce94  jnz     short loc_1800BCED5
0x1800bce96  lea     rdx, [rbx+16ACh]; lprc2
0x1800bce9d  lea     this, [rbp+57h+rectScrollUpOld.right]; lprc1
0x1800bcea1  call    cs:__imp_EqualRect
0x1800bcea7  test    eax, eax
0x1800bcea9  jz      short loc_1800BCED5
0x1800bceab  lea     rdx, [rbx+16BCh]; lprc2
0x1800bceb2  lea     this, [rbp+57h+rectScrollDnOld.right]; lprc1
0x1800bceb6  call    cs:__imp_EqualRect
0x1800bcebc  test    eax, eax
0x1800bcebe  jz      short loc_1800BCED5
0x1800bcec0  mov     rax, [r15]
0x1800bcec3  mov     this, r15
0x1800bcec6  mov     rax, [rax+428h]
0x1800bcecd  call    cs:__guard_dispatch_icall_fptr
0x1800bced3  jmp     short loc_1800BCF1D
0x1800bced5  mov     bForceMenuBarResize, [rbp+57h+rectScrollUpOld.top]
0x1800bced8  mov     ecx, [rbp+57h+rectScrollUpOld.left]
0x1800bcedb  and     [rsp+0B0h+var_78], 0
0x1800bcee1  mov     rax, [r15]
0x1800bcee4  mov     r9d, [rbp+57h+rectClient.bottom]
0x1800bcee8  sub     bForceMenuBarResize, r9d
0x1800bceeb  mov     r8d, [rbp+57h+rectClient.right]
0x1800bceef  sub     ecx, r8d
0x1800bcef2  mov     dword ptr [rsp+0B0h+var_80], r14d
0x1800bcef7  mov     rax, [rax+480h]
0x1800bcefe  mov     [rsp+0B0h+var_88], bForceMenuBarResize
0x1800bcf02  xor     bForceMenuBarResize, bForceMenuBarResize
0x1800bcf04  mov     [rsp+0B0h+var_90], ecx
0x1800bcf08  mov     this, r15
0x1800bcf0b  call    cs:__guard_dispatch_icall_fptr
0x1800bcf11  mov     eax, [rbp+57h+rectScrollUpOld.top]
0x1800bcf14  sub     eax, [rbp+57h+rectClient.bottom]
0x1800bcf17  mov     [rbx+1678h], eax
0x1800bcf1d  lea     rdx, [rbx+16ACh]; lprc2
0x1800bcf24  xor     esi, esi
0x1800bcf26  lea     this, [rbp+57h+rectScrollUpOld.right]; lprc1
0x1800bcf2a  call    cs:__imp_EqualRect
0x1800bcf30  lea     edi, [rsi+1]
0x1800bcf33  test    eax, eax
0x1800bcf35  jnz     short loc_1800BCF5E
0x1800bcf37  mov     this, [rbx+40h]; hWnd
0x1800bcf3b  lea     rdx, [rbp+57h+rectScrollUpOld.right]; lpRect
0x1800bcf3f  mov     r8d, edi; bErase
0x1800bcf42  call    cs:__imp_InvalidateRect
0x1800bcf48  mov     this, [rbx+40h]; hWnd
0x1800bcf4c  lea     rdx, [rbx+16ACh]; lpRect
0x1800bcf53  mov     r8d, edi; bErase
0x1800bcf56  call    cs:__imp_InvalidateRect
0x1800bcf5c  mov     esi, edi
0x1800bcf5e  lea     rdx, [rbx+16BCh]; lprc2
0x1800bcf65  lea     this, [rbp+57h+rectScrollDnOld.right]; lprc1
0x1800bcf69  call    cs:__imp_EqualRect
0x1800bcf6f  test    eax, eax
0x1800bcf71  jnz     short loc_1800BCF9A
0x1800bcf73  mov     this, [rbx+40h]; hWnd
0x1800bcf77  lea     rdx, [rbp+57h+rectScrollDnOld.right]; lpRect
0x1800bcf7b  mov     r8d, edi; bErase
0x1800bcf7e  call    cs:__imp_InvalidateRect
0x1800bcf84  mov     this, [rbx+40h]; hWnd
0x1800bcf88  lea     rdx, [rbx+16BCh]; lpRect
0x1800bcf8f  mov     r8d, edi; bErase
0x1800bcf92  call    cs:__imp_InvalidateRect
0x1800bcf98  jmp     short loc_1800BCFA0
0x1800bcf9a  mov     edi, esi
0x1800bcf9c  test    esi, esi
0x1800bcf9e  jz      short loc_1800BCFAA
0x1800bcfa0  mov     this, [rbx+40h]; hWnd
0x1800bcfa4  call    cs:__imp_UpdateWindow
0x1800bcfaa  mov     eax, edi
0x1800bcfac  mov     this, [rbp+57h+var_28]
0x1800bcfb0  xor     this, rsp; StackCookie
0x1800bcfb3  call    __security_check_cookie
0x1800bcfb8  lea     r11, [rsp+0B0h+var_20]
0x1800bcfc0  mov     rbx, [r11+38h]
0x1800bcfc4  mov     rsi, [r11+40h]
0x1800bcfc8  mov     rdi, [r11+48h]
0x1800bcfcc  mov     rsp, r11
0x1800bcfcf  pop     r15
0x1800bcfd1  pop     r14
0x1800bcfd3  pop     r13
0x1800bcfd5  pop     r12
0x1800bcfd7  pop     rbp
0x1800bcfd8  retn
```
